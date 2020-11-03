---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-default?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Default
ms.openlocfilehash: 19871bcfd1e045ab30bfef0dc88aa42a4c4aecf4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216391"
---
# Out-Default

## ZUSAMMENFASSUNG
Sendet die Ausgabe an das Standardformatierungsprogramm und das Standard-Ausgabe-Cmdlet.

## SYNTAX

```
Out-Default [-Transcript] [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

PowerShell wird automatisch `Out-Default` am Ende jeder Pipeline hinzugefügt. `Out-Default` bestimmt, wie der Objektstream formatiert und ausgegeben wird. Wenn es sich bei dem Objektdaten Strom um einen Stream von Zeichen folgen handelt, werden `Out-Default` diese direkt an die Pipeline geleitet, die `Out-Host` die vom Host bereitgestellten entsprechenden APIs aufruft Wenn der Objektstream keine Zeichen folgen enthält, wird `Out-Default` das Objekt von überprüft, um zu bestimmen, was zu tun ist.
Zuerst wird der Objekttyp untersucht, und es wird ermittelt, ob für diesen Objekttyp eine registrierte _Sicht_ vorhanden ist.

PowerShell definiert das XML-Schema und einen Mechanismus (das `Update-FormatData` Cmdlet), in dem jeder Benutzer Sichten für einen Objekttyp registrieren kann. Sie können für jeden Objekttyp eine **Breite** , eine **Liste** , eine **Tabelle** oder eine **benutzerdefinierte** Ansicht angeben. Die Ansichten geben an, welche Eigenschaften angezeigt werden sollen und wie Sie angezeigt werden sollen. Wenn eine Sicht registriert ist, definiert Sie den zu verwendenden Formatierer. Wenn die registrierte Sicht also eine **Tabellen** Ansicht ist, werden `Out-Default` die Objekte von in gestreamt `Format-Table | Out-Host` . `Format-Table` Transformiert die Objekte in einen Stream von Formatierungsdaten Sätzen (gesteuert durch die Daten in der Sicht Definition) und `Out-Host` transformiert die Formatierungsdaten Sätze in Aufrufe der Host Schnittstelle.

## BEISPIELE

### Beispiel 1

Obwohl dieses Cmdlet nicht direkt vom Endbenutzer ausgeführt werden soll, kann es sein.

```powershell
Get-Process | Select-Object -First 5 | Out-Default
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     12     2.56       5.20       0.00    7376   0 aesm_service
     48    34.32      18.10      26.64    9320  13 AlertusDesktopAlert
     24    13.97      12.74       0.77   12656  13 ApplicationFrameHost
      8     1.79       4.41       0.00    8180   0 AppVShNotify
      9     1.99       5.07       0.19   19320  13 AppVShNotify
```

## PARAMETERS

### -InputObject

Akzeptiert Eingaben für das Cmdlet.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Transkripts

Bestimmt, ob die Ausgabe an die Transkriptions Dienste von PowerShell gesendet werden soll.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[Format-Custom](../Microsoft.PowerShell.Utility/Format-Custom.md)

[Format-List](../Microsoft.PowerShell.Utility/Format-List.md)

[Format-Table](../Microsoft.PowerShell.Utility/Format-Table.md)

[Format-Wide](../Microsoft.PowerShell.Utility/Format-Wide.md)

[about_Format.ps1xml](About/about_Format.ps1xml.md)

[Funktionsweise von PowerShell-Formatierung und-Ausgabe](https://devblogs.microsoft.com/powershell/how-powershell-formatting-and-outputting-really-works/)
