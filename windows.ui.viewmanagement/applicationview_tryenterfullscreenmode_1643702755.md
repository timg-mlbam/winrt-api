---
-api-id: M:Windows.UI.ViewManagement.ApplicationView.TryEnterFullScreenMode
-api-type: winrt method
---

<!-- Method syntax
public bool TryEnterFullScreenMode()
-->

# Windows.UI.ViewManagement.ApplicationView.TryEnterFullScreenMode

## -description
Attempts to place the app in full-screen mode.

## -returns
**true** if the app is placed in full-screen mode; otherwise, **false**.

## -remarks
To preserve full screen mode when a user restarts the app, set [PreferredLaunchWindowingMode](applicationview_preferredlaunchwindowingmode.md) to **FullScreen** if the call to [TryEnterFullScreenMode](applicationview_tryenterfullscreenmode.md) returns **true**. When you call [ExitFullScreenMode](applicationview_exitfullscreenmode.md), you should set [PreferredLaunchWindowingMode](applicationview_preferredlaunchwindowingmode.md) back to **Auto** or **PreferredLaunchViewSize**.

The system raises the [CoreWindow.SizeChanged](../windows.ui.core/corewindow_sizechanged.md) event when the view enters or exits full screen mode. This is exposed to XAML apps as the [Window.SizeChanged](../windows.ui.xaml/window_sizechanged.md) event and to HTML apps as the [window.resize](https://msdn.microsoft.com/en-us/library/aa741886(v=vs.85).aspx) event.

## -examples
This example shows how to toggle full-screen mode and set the [PreferredLaunchWindowingMode](applicationview_preferredlaunchwindowingmode.md) property.

```xaml
<Button x:Name="ToggleFullScreenModeButton" Content="Toggle full screen" 
        Click="ToggleFullScreenModeButton_Click">
```

```csharp
private void ToggleFullScreenModeButton_Click(object sender, RoutedEventArgs e)
{
    var view = ApplicationView.GetForCurrentView();
    if (view.IsFullScreenMode)
    {
        view.ExitFullScreenMode();
        ApplicationView.PreferredLaunchWindowingMode = ApplicationViewWindowingMode.Auto;
        // The SizeChanged event will be raised when the exit from full-screen mode is complete.
    }
    else
    {
        if (view.TryEnterFullScreenMode())
        {
            ApplicationView.PreferredLaunchWindowingMode = ApplicationViewWindowingMode.FullScreen;
            // The SizeChanged event will be raised when the entry to full-screen mode is complete.
        }
    }
}
```



## -see-also
[IsFullScreenMode](applicationview_isfullscreenmode.md), [ExitFullScreenMode](applicationview_exitfullscreenmode.md), [PreferredLaunchWindowingMode](applicationview_preferredlaunchwindowingmode.md), [Full screen mode sample](http://go.microsoft.com/fwlink/p/?LinkId=620546), [Window resizing sample](http://go.microsoft.com/fwlink/p/?LinkId=620026)