---
title: AccessDBProviderSample04 | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 097591528fd12cdf9f134a0fd8a0bd278f216fab
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786865"
---
# <a name="accessdbprovidersample04"></a>AccessDBProviderSample04

Dieses Beispiel zeigt, wie Sie Container Methoden überschreiben, um Aufrufe `Copy-Item` der `Get-ChildItem` `New-Item` Cmdlets,, und zu unterstützen `Remove-Item` . Diese Methoden sollten implementiert werden, wenn der Datenspeicher Elemente enthält, die Container sind. Ein Container ist eine Gruppe von untergeordneten Elementen unter einem gemeinsamen übergeordneten Element. Die Anbieter Klasse in diesem Beispiel wird von der [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse abgeleitet.

## <a name="demonstrates"></a>Zeigt

> [!IMPORTANT]
> Ihre Anbieter Klasse wird wahrscheinlich von [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) abgeleitet.

Dieses Beispiel zeigt Folgendes:

- Deklarieren des `CmdletProvider` Attributs.
- Definieren einer Anbieter Klasse, die von der [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse abgeleitet wird.
- Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) -Methode, um das Verhalten des `Copy-Item` Cmdlets zu ändern, das es dem Benutzer ermöglicht, Elemente von einem Speicherort in einen anderen zu kopieren. (Dieses Beispiel zeigt nicht, wie dem Cmdlet dynamische Parameter hinzugefügt werden `Copy-Item` .)
- Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. getchilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) -Methode, um das Verhalten des Cmdlets "Get-ChildItems" zu ändern, mit dem der Benutzer die untergeordneten Elemente des übergeordneten Elements abrufen kann. (Dieses Beispiel zeigt nicht, wie dem Cmdlet "Get-ChildItems" dynamische Parameter hinzugefügt werden.)
- Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) -Methode, um das Verhalten des Cmdlets Get-ChildItems zu ändern, wenn der- `Name` Parameter des Cmdlets angegeben wird.
- Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. netwitem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem) -Methode, um das Verhalten des `New-Item` Cmdlets zu ändern, das dem Benutzer das Hinzufügen von Elementen zum Datenspeicher ermöglicht. (Dieses Beispiel zeigt nicht, wie dem Cmdlet dynamische Parameter hinzugefügt werden `New-Item` .)
- Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. RemoveItem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) -Methode, um das Verhalten des `Remove-Item` Cmdlets zu ändern. (Dieses Beispiel zeigt nicht, wie dem Cmdlet dynamische Parameter hinzugefügt werden `Remove-Item` .)

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie Sie die Methoden überschreiben, die zum Kopieren, erstellen und Entfernen von Elementen erforderlich sind, sowie Methoden zum erhalten der untergeordneten Elemente eines übergeordneten Elements.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Entwerfen eines Windows PowerShell-Anbieters](./provider-types.md)
