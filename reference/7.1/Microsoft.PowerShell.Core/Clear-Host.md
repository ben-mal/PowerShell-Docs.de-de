---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ''
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-host?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Host
ms.openlocfilehash: 452e0e66cf6db746469247bf68552960517f6c32
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209271"
---
# Clear-Host

## ZUSAMMENFASSUNG

Löscht die Anzeige im Hostprogramm.

## SYNTAX

```
Clear-Host [<CommonParameters>]
```

## DESCRIPTION

Die- `Clear-Host` Funktion entfernt den gesamten Text aus der aktuellen Anzeige, einschließlich Befehle und Ausgaben, die möglicherweise gesammelt wurden. Nach Abschluss des Vorgangs wird die Eingabeaufforderung angezeigt. Sie können den Funktionsnamen oder seinen Alias verwenden `cls` .

`Clear-Host` wirkt sich nur auf die aktuelle Anzeige aus. Es löscht keine gespeicherten Ergebnisse oder entfernt Elemente aus der Sitzung. Sitzungsspezifische Objekte, z. B. Variablen und Funktionen, sind nicht von dieser Funktion betroffen.

Da das Verhalten der- `Clear-Host` Funktion durch das Host Programm bestimmt wird, `Clear-Host` funktioniert möglicherweise in verschiedenen Host Programmen anders.

## BEISPIELE

### Beispiel 1

```
# Before

PS C:\> Get-Process

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    843      33    14428      22556    99    17.41   1688 CcmExec
     44       6     2196       4964    52     0.23    692 conhost
    646      12     2332       4896    49     1.12    388 csrss
    189      11     2860       7084   114     0.66   2896 csrss
     78      11     1876       4008    42     0.22   4000 csrss
     76       7     1848       5064    54     0.08   1028 dwm
    610      41    23952      44048   208     4.40   2080 explorer
      0       0        0         24     0               0 Idle
    182      32     7692      15980    91     0.23   3056 LogonUI
    186      25     7832      16068    91     0.27   3996 LogonUI
   1272      32    11512      20432    58    25.07    548 lsass
    267      10     3536       6736    34     0.80    556 lsm
    137      17     3520       7472    61     0.05   1220 msdtc
    447      31    70316      84476   201 1,429.67    836 MsMpEng
    265      18     7136      15628   134     2.20   3544 msseces
    248      16     6476       4076    76     0.22   1592 NisSrv
    368      25    61312      65508   614     1.78    848 powershell
    101       8     2304       6624    70     0.64   3648 rdpclip
    258      15     6804      12156    50     2.65    536 services
...

PS C:\> cls
#After

PS C:>
```

Dieser Befehl verwendet den `cls` Alias von `Clear-Host` , um die aktuelle Anzeige zu löschen.

## PARAMETERS

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an übergeben werden `Clear-Host` .

## AUSGABEN

### Keine

`Clear-Host` generiert keine Ausgabe.

## HINWEISE

`Clear-Host` ist eine einfache Funktion, keine erweiterte Funktion. Daher können Sie in einem Befehl keine allgemeinen Parameter wie z. b. **Debuggen** verwenden `Clear-Host` .

## VERWANDTE LINKS

[Get-Host](../Microsoft.PowerShell.Utility/Get-Host.md)

[Out-Host](Out-Host.md)

[Read-Host](../Microsoft.PowerShell.Utility/Read-Host.md)

[Write-Host](../Microsoft.PowerShell.Utility/Write-Host.md)

