---
ms.date: 09/13/2016
ms.topic: reference
title: Anfordern der Bestätigung von Benutzern
description: Anfordern der Bestätigung von Benutzern
ms.openlocfilehash: 58dbe27635ca38886b728f585fec063645b3597e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646306"
---
# <a name="users-requesting-confirmation"></a>Anfordern der Bestätigung von Benutzern

Wenn Sie `true` für den- `SupportsShouldProcess` Parameter der Cmdlet-Attribut Deklaration den Wert angeben, können Benutzer den `Confirm` Parameter an der Eingabeaufforderung angeben.

In der Standardumgebung können Benutzer den- `Confirm` Parameter angeben oder festlegen `"-Confirm:$true` , dass die Bestätigung angefordert wird, wenn die [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Methode aufgerufen wird. Dies umgeht [System. Management. Automation. Cmdlet. tiondprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Bestätigungs Anforderungen, auch für Vorgänge mit hohen Auswirkungen.

Wenn `Confirm` nicht angegeben wird, fordert der [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Rückruf eine Bestätigung an, wenn die `$ConfirmPreference` Einstellungs Variable größer oder gleich der `ConfirmImpact` Einstellung des Cmdlets oder Anbieters ist. Die Standardeinstellung von `$ConfirmPreference` ist hoch. In der Standardumgebung gibt es daher nur Cmdlets und Anbieter, die eine Bestätigungs-Aktions Anforderungs Bestätigung angeben.

Wenn `Confirm` false ist oder wenn `"-Confirm:$false` angegeben wird, fordert der [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Befehl eine Bestätigung vom Benutzer an, und die `$ConfirmPreference` Shellvariable wird ignoriert.

## <a name="remarks"></a>Bemerkungen

- Für Cmdlets und Anbieter, die angeben `SupportsShouldProcess` , aber nicht `ConfirmImpact` , werden diese Aktionen als "mittlere Auswirkung"-Aktionen behandelt, und Sie werden nicht standardmäßig aufgefordert. Die Auswirkungs Stufe ist kleiner als die Standardeinstellung der `$ConfirmPreference` Preference-Variablen.

- Wenn der Benutzer den `Verbose` Parameter angibt, wird er über den Vorgang benachrichtigt, auch wenn er nicht zur Bestätigung aufgefordert wird.

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
