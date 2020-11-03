---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/07/2018
Module Name: Microsoft.PowerShell.Core
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/functions/get-verb?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 4474bb50c2bf3be10e72d2554190208e956f9040
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "93219495"
---
# Get-Verb

## ZUSAMMENFASSUNG
Ruft genehmigte PowerShell-Verben ab.

## SYNTAX

```
Get-Verb [[-verb] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Die `Get-Verb` Funktion ruft Verben ab, die für die Verwendung in PowerShell-Befehlen genehmigt sind.

PowerShell empfiehlt, dass Cmdlet-und Funktionsnamen das Verb-Noun Format aufweisen und ein genehmigtes Verb enthalten. Durch diese Vorgehensweise werden Befehlsnamen Koner, vorhersag barer und einfacher zu verwenden.

Befehle, die nicht genehmigte Verben verwenden, werden in PowerShell ausgeführt. Wenn Sie jedoch ein Modul importieren, das einen Befehl mit einem nicht genehmigten Verb in seinem Namen enthält, `Import-Module` zeigt der Befehl eine Warnmeldung an.

> [!NOTE]
> Die von zurückgegebene Verb Liste ist `Get-Verb` möglicherweise nicht fertig. Eine aktualisierte Liste genehmigter PowerShell-Verben mit Beschreibungen finden Sie unter [genehmigte Verben](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in der Microsoft-Dokumentation.

## BEISPIELE

### Beispiel 1: erhalten einer Liste aller Verben

```powershell
Get-Verb
```

### Beispiel 2: erhalten einer Liste genehmigter Verben, die mit "UN" beginnen

```powershell
Get-Verb un*
```

```Output
Verb                 Group
----                 -----
Undo                 Common
Unlock               Common
Unpublish            Data
Uninstall            Lifecycle
Unregister           Lifecycle
Unblock              Security
Unprotect            Security
```

### Beispiel 3: alle genehmigten Verben in der Sicherheitsgruppe erhalten

```powershell
Get-Verb | Where-Object Group -EQ Security
```

```Output
Verb      Group
----      -----
Block     Security
Grant     Security
Protect   Security
Revoke    Security
Unblock   Security
Unprotect Security
```

### Beispiel 4: sucht alle Befehle in einem Modul, die nicht genehmigte Verben aufweisen

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## PARAMETERS

### -Verb

Ruft nur die angegebenen Verben ab.
Geben Sie den Namen eines Verbs oder ein Namensmuster ein.
Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: All verbs
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## EINGABEN

### Keine

## AUSGABEN

### Selected.Microsoft.PowerShell.Commands.MemberDefinition

## HINWEISE

`Get-Verb` gibt eine geänderte Version eines Microsoft. PowerShell. Commands. Membership Definition-Objekts zurück.
Das Objekt muss nicht die Standardeigenschaften eines MemberDefinition-Objekts besitzen. Stattdessen hat es Verb- und Gruppeneigenschaften. Die Verb-Eigenschaft enthält eine Zeichenfolge mit dem Verbnamen. Die Group-Eigenschaft enthält eine Zeichenfolge mit der Verbgruppe.

PowerShell-Verben werden einer Gruppe basierend auf Ihrer gängigsten Verwendung zugewiesen. Die Gruppen sind so gestaltet, dass die Verben leicht zu finden und zu vergleichen sind, nicht um ihre Verwendung zu beschränken. Sie können alle genehmigten Verben für jeden Typ von Befehl verwenden.

Jedes PowerShell-Verb ist einer der folgenden Gruppen zugewiesen.

- Common: definieren Sie generische Aktionen, die auf fast alle Cmdlets, z. b. Add, angewendet werden können.
- Kommunikation: definieren Sie Aktionen, die für die Kommunikation gelten, z. b. Connect.
- Daten: definieren Sie Aktionen, die für die Datenverarbeitung gelten, wie z. b. Backup.
- Diagnose: definieren Sie Aktionen, die für die Diagnose gelten, z. b. Debug.
- Lebenszyklus: definieren Sie Aktionen, die für den Lebenszyklus eines Cmdlets gelten, z. b. "Complete".
- Sicherheit: definieren Sie Aktionen, die auf Sicherheit angewendet werden, z. b. widerrufen.
- Sonstige: definieren Sie andere Arten von Aktionen.

Einige der Cmdlets, die mit PowerShell installiert werden, wie z `Tee-Object` `Where-Object` . b. und, verwenden nicht genehmigte Verben. Diese Cmdlets sind historische Ausnahmen und ihre Verben werden als **reserviert** klassifiziert.

## VERWANDTE LINKS

[Import-Module](import-module.md)
