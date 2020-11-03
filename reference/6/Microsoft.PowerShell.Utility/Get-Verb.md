---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/07/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-verb?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 516ecf2b5d6e3bce2a0cda7c36c143d2ba75933a
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "93219508"
---
# Get-Verb

## ZUSAMMENFASSUNG
Ruft genehmigte PowerShell-Verben ab.

## SYNTAX

```
Get-Verb [[-Verb] <String[]>] [[-Group] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Die `Get-Verb` Funktion ruft Verben ab, die für die Verwendung in PowerShell-Befehlen genehmigt sind.

Es wird empfohlen, dass PowerShell-Cmdlet-und Funktionsnamen das `Verb-Noun` Format aufweisen und ein genehmigtes Verb enthalten. Durch diese Vorgehensweise werden Befehlsnamen Koner, vorhersag barer und einfacher zu verwenden.

Befehle, die nicht genehmigte Verben verwenden, werden weiterhin in PowerShell ausgeführt. Wenn Sie jedoch ein Modul importieren, das einen Befehl mit einem nicht genehmigten Verb in seinem Namen enthält, `Import-Module` zeigt der Befehl eine Warnmeldung an.

> [!NOTE]
> Die von zurückgegebene Verb Liste ist `Get-Verb` möglicherweise nicht fertig. Eine aktualisierte Liste genehmigter PowerShell-Verben mit Beschreibungen finden Sie unter [genehmigte Verben](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in der Microsoft-Dokumentation.

## Beispiele

### Beispiel 1: erhalten einer Liste aller Verben

```powershell
Get-Verb
```

### Beispiel 2: erhalten einer Liste genehmigter Verben, die mit "UN" beginnen

```powershell
Get-Verb un*
```

```Output
Verb       AliasPrefix Group     Description
----       ----------- -----     -----------
Undo       un          Common    Sets a resource to its previous state
Unlock     uk          Common    Releases a resource that was locked
Unpublish  ub          Data      Makes a resource unavailable to others
Uninstall  us          Lifecycle Removes a resource from an indicated location
Unregister ur          Lifecycle Removes the entry for a resource from a repository
Unblock    ul          Security  Removes restrictions to a resource
Unprotect  up          Security  Removes safeguards from a resource that were added to prevent it from attack or loss
```

### Beispiel 3: alle genehmigten Verben in der Sicherheitsgruppe erhalten

```powershell
Get-Verb -Group Security
```

```Output
Verb      AliasPrefix Group    Description
----      ----------- -----    -----------
Block     bl          Security Restricts access to a resource
Grant     gr          Security Allows access to a resource
Protect   pt          Security Safeguards a resource from attack or loss
Revoke    rk          Security Specifies an action that does not allow access to a resource
Unblock   ul          Security Removes restrictions to a resource
Unprotect up          Security Removes safeguards from a resource that were added to prevent it from attack or loss
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

Ruft nur die angegebenen Verben ab. Geben Sie den Namen eines Verbs oder ein Namensmuster ein. Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Common, Communications, Data, Diagnostic, Lifecycle, Other, Security

Required: False
Position: 1
Default value: All groups
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Group

Ruft nur die angegebenen Gruppen ab. Geben Sie den Namen einer Gruppe ein. Platzhalter sind nicht zulässig.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All verbs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

## AUSGABEN

### System. Management. Automation. verbinfo

## HINWEISE

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

[Import-Module](../microsoft.powershell.core/import-module.md)
