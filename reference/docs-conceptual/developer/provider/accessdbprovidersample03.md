---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample03
description: AccessDBProviderSample03
ms.openlocfilehash: bfd402903a9023b58dec8865663e3d649a50e1e1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667401"
---
# <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

In diesem Beispiel wird gezeigt, wie die Methoden [System. Management. Automation. Provider. itemcmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) und [System. Management. Automation. Provider. itemcmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) überschrieben werden, um Aufrufe der `Get-Item` -und- `Set-Item` Cmdlets zu unterstützen. Die Anbieter Klasse in diesem Beispiel wird von der [System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse abgeleitet.

## <a name="demonstrates"></a>Zeigt

> [!IMPORTANT]
> Ihre Anbieter Klasse wird wahrscheinlich von einer der folgenden Klassen abgeleitet und kann möglicherweise andere Anbieter Schnittstellen implementieren:
>
> - [System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse.
> - [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse. Siehe [AccessDBProviderSample04](./accessdbprovidersample04.md).
> - [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse. Siehe [AccessDBProviderSample05](./accessdbprovidersample05.md).
>
> Weitere Informationen zum Auswählen der Anbieter Klasse, von der basierend auf den Anbieter Features abgeleitet werden soll, finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./provider-types.md).

Dieses Beispiel zeigt Folgendes:

- Deklarieren des `CmdletProvider` Attributs.
- Definieren einer Anbieter Klasse, die von der [System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse abgeleitet wird.
- Überschreiben der [System. Management. Automation. Provider. drivecmdletprovider. newdrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) -Methode, um das Verhalten des `New-PSDrive` Cmdlets zu ändern, sodass der Benutzer neue Laufwerke erstellen kann.
  (Dieses Beispiel zeigt nicht, wie dem Cmdlet dynamische Parameter hinzugefügt werden `New-PSDrive` .)
- Überschreiben der [System. Management. Automation. Provider. drivecmdletprovider. removedrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) -Methode, um das Entfernen vorhandener Laufwerke zu unterstützen.
- Überschreiben der [System. Management. Automation. Provider. itemcmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) -Methode, um das Verhalten des `Get-Item` Cmdlets zu ändern, sodass der Benutzer Elemente aus dem Datenspeicher abrufen kann. (Dieses Beispiel zeigt nicht, wie dem Cmdlet dynamische Parameter hinzugefügt werden `Get-Item` .)
- Überschreiben der [System. Management. Automation. Provider. itemcmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) -Methode, um das Verhalten des `Set-Item` Cmdlets zu ändern, sodass der Benutzer die Elemente im Datenspeicher aktualisieren kann. (Dieses Beispiel zeigt nicht, wie dem Cmdlet dynamische Parameter hinzugefügt werden `Get-Item` .)
- Überschreiben der [System. Management. Automation. Provider. itemcmdletprovider. itemexists *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) -Methode, um das Verhalten des `Test-Path` Cmdlets zu ändern. (Dieses Beispiel zeigt nicht, wie dem Cmdlet dynamische Parameter hinzugefügt werden `Test-Path` .)
- Überschreiben der [System. Management. Automation. Provider. itemcmdletprovider. IsValidPath *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath) -Methode, um zu bestimmen, ob der angegebene Pfad gültig ist.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie Sie die Methoden überschreiben, die zum Abrufen und Festlegen von Elementen in einer Microsoft Access-Datenbank erforderlich sind.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample03/AccessDBProviderSample03.cs" range="11-976":::

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Entwerfen eines Windows PowerShell-Anbieters](./provider-types.md)
