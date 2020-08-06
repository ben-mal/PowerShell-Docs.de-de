---
title: Anbieter Beispiele | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 9eb8eb64bbe585ebd8024c0215853ff04a5c3e54
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778430"
---
# <a name="provider-samples"></a>Anbieterbeispiele

Dieser Abschnitt enthält Beispiele von Anbietern, die auf eine Microsoft Access-Datenbank zugreifen. Diese Beispiele enthalten Anbieter Klassen, die von allen Basis Anbieter Klassen abgeleitet werden.

## <a name="in-this-section"></a>In diesem Abschnitt

Dieser Abschnitt schließt folgende Themen ein:

[AccessDBProviderSample01-Beispiel](./accessdbprovidersample01.md) Dieses Beispiel zeigt, wie Sie die Anbieter Klasse deklarieren, die direkt von der [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) -Klasse abgeleitet wird. Wird hier nur aus Gründen der Vollständigkeit aufgeführt.

[AccessDBProviderSample02](./accessdbprovidersample02.md) In diesem Beispiel wird gezeigt, wie die Methoden [System. Management. Automation. Provider. drivecmdletprovider. newdrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) und [System. Management. Automation. Provider. drivecmdletprovider. removedrive *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) überschrieben werden, um Aufrufe der `New-PSDrive` -und- `Remove-PSDrive` Cmdlets zu unterstützen. Die Anbieter Klasse in diesem Beispiel wird von der [System. Management. Automation. Provider. drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) -Klasse abgeleitet.

[AccessDBProviderSample03](./accessdbprovidersample03.md) In diesem Beispiel wird gezeigt, wie die Methoden [System. Management. Automation. Provider. itemcmdletprovider. GetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) und [System. Management. Automation. Provider. itemcmdletprovider. SetItem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) überschrieben werden, um Aufrufe der `Get-Item` -und- `Set-Item` Cmdlets zu unterstützen. Die Anbieter Klasse in diesem Beispiel wird von der [System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse abgeleitet.

[AccessDBProviderSample04](./accessdbprovidersample04.md) Dieses Beispiel zeigt, wie Sie Container Methoden überschreiben, um Aufrufe `Copy-Item` der `Get-ChildItem` `New-Item` Cmdlets,, und zu unterstützen `Remove-Item` . Diese Methoden sollten implementiert werden, wenn der Datenspeicher Elemente enthält, die Container sind. Ein Container ist eine Gruppe von untergeordneten Elementen unter einem gemeinsamen übergeordneten Element. Die Anbieter Klasse in diesem Beispiel wird von der [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse abgeleitet.

[AccessDBProviderSample05](./accessdbprovidersample05.md) Dieses Beispiel zeigt, wie Sie Container Methoden überschreiben, um Aufrufe der `Move-Item` -und- `Join-Path` Cmdlets zu unterstützen. Diese Methoden sollten implementiert werden, wenn der Benutzer Elemente innerhalb eines Containers verschieben muss, und wenn der Datenspeicher geschachtelte Container enthält. Die Anbieter Klasse in diesem Beispiel wird von der [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse abgeleitet.

[AccessDBProviderSample06](./accessdbprovidersample06.md) In diesem Beispiel wird gezeigt, wie Inhalts Methoden überschrieben werden, um Aufrufe der `Clear-Content` `Get-Content` Cmdlets, und zu unterstützen `Set-Content` . Diese Methoden sollten implementiert werden, wenn der Benutzer den Inhalt der Elemente im Datenspeicher verwaltet muss. Die Anbieter Klasse in diesem Beispiel wird von der [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse abgeleitet und implementiert die [System. Management. Automation. Provider. icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider) -Schnittstelle.

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Anbieters](./writing-a-windows-powershell-provider.md)
