---
title: Subcommand: stop-Server
ms.custom: na
ms.prod: windows-server-2012
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 09f411c0-099f-4591-95fd-b77b3fd9118a
---
# Subcommand: stop-Server
Stops all services on a Windows Deployment Services server.

## Syntax

```
WDSUTIL [Options] /Stop-Server [/Server:<Server name>]
```

## Parameters

|Parameter|Description|
|-------------|---------------|
|\[\/Server:<Server name>\]|Specifies the name of the server. This can be either the NetBIOS name or the fully qualified domain name \(FQDN\). If no server name is specified, the local server will be used.|

## <a name="BKMK_examples"></a>Examples
To stop the services, type one of the following:

```
WDSUTIL /Stop-Server
WDSUTIL /Verbose /Stop-Server /Server:MyWDSServer
```

#### Additional references
[Command-Line Syntax Key](../../Command-Line-Syntax-Key.md)

[Using the disable-Server Command]()

[Using the enable-Server Command](../using-the-enable-command/Using-the-enable-Server-Command.md)

[Using the get-Server Command](../using-the-get-command/Using-the-get-Server-Command.md)

[Using the Initialize-Server Command](../Using-the-Initialize-Server-Command.md)

[Subcommand: set-Server](../the-set-command/Subcommand--set-Server.md)

[Subcommand: start-Server](../the-start-server-command/Subcommand--start-Server.md)

[The uninitialize-Server Option](../The-uninitialize-Server-Option.md)

