---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample04
description: AccessDBProviderSample04
ms.openlocfilehash: 962d0ab673ff797a60b56ccae7a16a810cc43c58
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649047"
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
- Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. getchilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems) -Methode, um das Verhalten des Get-ChildItems-Cmdlets zu ändern, mit dem der Benutzer die untergeordneten Elemente des übergeordneten Elements abrufen kann. (In diesem Beispiel wird nicht gezeigt, wie dem Get-ChildItems-Cmdlet dynamische Parameter hinzugefügt werden.)
- Überschreiben der [System. Management. Automation. Provider. containercmdletprovider. getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames) -Methode, um das Verhalten des Get-ChildItems-Cmdlets zu ändern, wenn der- `Name` Parameter des Cmdlets angegeben wird.
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
