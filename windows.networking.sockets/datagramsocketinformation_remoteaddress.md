---
-api-id: P:Windows.Networking.Sockets.DatagramSocketInformation.RemoteAddress
-api-type: winrt property
---

<!-- Property syntax
public Windows.Networking.HostName RemoteAddress { get; }
-->

# Windows.Networking.Sockets.DatagramSocketInformation.RemoteAddress

## -description
The IP address of the remote network destination associated with a [DatagramSocket](datagramsocket.md) object.

## -property-value
The IP address of the remote network destination.

## -remarks
The [RemoteAddress](datagramsocketinformation_remoteaddress.md) property represents the remote IP address for the remote network destination associated with a [DatagramSocket](datagramsocket.md) object.

An app can set the remote hostname or IP address and remote service name or UDP port number to use by calling the [ConnectAsync](datagramsocket_connectasync.md) or [GetOutputStreamAsync](datagramsocket_getoutputstreamasync.md) method on the [DatagramSocket](datagramsocket.md). The connect operation will bind the socket to a specific remote IP address and remote UDP port number. The [RemoteAddress](datagramsocketinformation_remoteaddress.md) property is the IP address that remote hostname resolved to.

## -examples

## -see-also
[How to use advanced socket controls ](http://msdn.microsoft.com/library/2e1071d8-a1c7-44c0-b93a-31a701d431c4), [How to use advanced socket controls ](http://msdn.microsoft.com/library/f2c5be73-3461-452e-a38f-d2ddef9b5682), [DatagramSocket](datagramsocket.md), [DatagramSocket.ConnectAsync](datagramsocket_connectasync.md), [DatagramSocket.GetOutputStreamAsync](datagramsocket_getoutputstreamasync.md), [HostName](../windows.networking/hostname.md), [LocalAddress](datagramsocketinformation_localaddress.md), [LocalPort](datagramsocketinformation_localport.md), [RemotePort](datagramsocketinformation_remoteport.md)

## -capabilities
ID_CAP_NETWORKING [Windows Phone]
