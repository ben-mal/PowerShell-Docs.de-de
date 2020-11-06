---
ms.date: 12/31/2019
title: Das ISEMenuItemCollection-Objekt
description: Ein ISEMenuItemCollection-Objekt ist eine Sammlung von ISEMenuItem-Objekten.
ms.openlocfilehash: cd86768d13b1326a8f35c44f0391ab60669cee4f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655992"
---
# <a name="the-isemenuitemcollection-object"></a>Das ISEMenuItemCollection-Objekt

Ein **ISEMenuItemCollection** -Objekt ist eine Sammlung von **ISEMenuItem** -Objekten. Es handelt sich um eine Instanz der **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection** -Klasse. Ein Beispiel ist das `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus`-Objekt, das verwendet wird, um das Menü **Add-On** in Windows PowerShell&reg; Integrated Scripting Environment (ISE) anzupassen.

## <a name="method"></a>Methode

### <a name="addstring-displayname-systemmanagementautomationscriptblock-action-systemwindowsinputkeygesture-shortcut-"></a>Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)

In Windows PowerShell ISE 2.0 und höher unterstützt.

Fügt der Sammlung ein Menüelement hinzu.

**DisplayName** Der Anzeigename des hinzuzufügenden Menüs.

**Action** Das **System.Management.Automation.ScriptBlock** -Objekt, das die diesem Menüelement zugeordnete Aktion angibt.

**Shortcut** Die Tastenkombination für diese Aktion.

**Returns** Das **ISEMenuItem** -Objekt, das soeben hinzugefügt wurde.

```powershell
# Create an Add-ons menu with an fast access key and a shortcut.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
```

### <a name="clear"></a>Clear\(\)

In Windows PowerShell ISE 2.0 und höher unterstützt.

Entfernt alle Untermenüs des Menüelements.

```powershell
# Remove all custom submenu items from the AddOns menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
```

## <a name="see-also"></a>Weitere Informationen

- [Das ISEMenuItem-Objekt](The-ISEMenuItem-Object.md)
- [Zweck des Windows PowerShell ISE-Skriptobjektmodells](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Die ISE-Objektmodellhierarchie](The-ISE-Object-Model-Hierarchy.md)
