---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-formatdata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FormatData
ms.openlocfilehash: afc6253e112bf44ba4f92b726002003cc8b594fc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216660"
---
# Get-FormatData

## ZUSAMMENFASSUNG
Ruft die Formatierungsdaten in der aktuellen Sitzung ab.

## SYNTAX

```
Get-FormatData [[-TypeName] <String[]>] [-PowerShellVersion <Version>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-FormatData` Cmdlet werden die Formatierungsdaten in der aktuellen Sitzung abgerufen.

Die Formatierungsdaten in der Sitzung umfassen das Formatieren von Daten aus `Format.ps1xml` Formatierungs Dateien, z. b. im `$PSHOME` Verzeichnis, das Formatieren von Daten für Module, die in die Sitzung importiert werden, und das Formatieren von Daten für Befehle, die Sie mithilfe des Cmdlets in die Sitzung importieren `Import-PSSession` .

Mit diesem Cmdlet können Sie die Formatierungsdaten untersuchen. Anschließend können Sie mit dem `Export-FormatData` Cmdlet die Objekte serialisieren, Sie in XML konvertieren und in `Format.ps1xml` Dateien speichern.

Weitere Informationen zum Formatieren von Dateien in PowerShell finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

## BEISPIELE

### Beispiel 1: alle Formatierungsdaten erhalten

In diesem Beispiel werden alle Formatierungsdaten in der Sitzung abgerufen.

```powershell
Get-FormatData -PowerShellVersion 5.1
```

> [!IMPORTANT]
> Um sicherzustellen, dass die vollständigen typformatierungs Informationen zurückgegeben werden, sollten Sie immer den **PowerShellVersion** -Parameter mit dem Wert einschließen, `5.1` Wenn Sie einen lokalen Aufruf von verwenden `Get-FormatData` . Wenn der-Parameter und der-Wert weggelassen werden, werden möglicherweise nicht alle richtigen Typinformationen angezeigt.

### Beispiel 2: Formatieren von Daten nach Typname

In diesem Beispiel werden die Formatierungsdaten Elemente abgerufen, deren Namen mit beginnen `System.Management.Automation.Cmd` .

```powershell
Get-FormatData -TypeName 'System.Management.Automation.Cmd*' -PowerShellVersion 5.1
```

### Beispiel 3: Untersuchen eines Formatierungsdaten Objekts

Dieses Beispiel zeigt, wie Sie ein Formatierungsdatenobjekt abrufen und seine Eigenschaften untersuchen.

```powershell
$F = Get-FormatData -TypeName 'System.Management.Automation.Cmd*' -PowerShellVersion 5.1
$F
```

```Output
TypeName        FormatViewDefinition
--------        --------------------
HelpInfoShort   {help , TableControl}
```

```powershell
$F.FormatViewDefinition[0].control
```

```Output
Headers          : {System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader}
Rows             : {System.Management.Automation.TableControlRow}
AutoSize         : False
HideTableHeaders : False
GroupBy          :
OutOfBand        : False
```

```powershell
$F.FormatViewDefinition[0].control.Headers
```

```Output
Label       Alignment Width
-----       --------- -----
CommandType Undefined    15
Name        Undefined    50
Version     Undefined    10
Source      Undefined     0
```

### Beispiel 4: erhalten von Formatierungsdaten und Exportieren der Daten

In diesem Beispiel wird gezeigt, wie `Get-FormatData` und verwendet `Export-FormatData` werden, um die Formatierungsdaten zu exportieren, die von einem Modul hinzugefügt werden.

```powershell
$A = Get-FormatData -PowerShellVersion 5.1
Import-Module bitstransfer
$B = Get-FormatData -PowerShellVersion 5.1
Compare-Object $A $B
```

```Output
InputObject                                                SideIndicator
-----------                                                -------------
Microsoft.BackgroundIntelligentTransfer.Management.BitsJob =>
```

```powershell
Get-FormatData *bits* | Export-FormatData -FilePath c:\test\bits.format.ps1xml
Get-Content c:\test\bits.format.ps1xml
```

```Output
<?xml version="1.0" encoding="utf-8"?><Configuration><ViewDefinitions>
<View><Name>Microsoft.BackgroundIntelligentTransfer.Management.BitsJob</Name>
...
```

Die ersten vier Befehle verwenden die `Get-FormatData` `Import-Module` `Compare-Object` Cmdlets, und, um den Formattyp zu identifizieren, den das **bitstransfer** -Modul zur Sitzung hinzufügt.

Der fünfte Befehl verwendet das `Get-FormatData` Cmdlet, um den Formattyp zu erhalten, den das **bitstransfer** -Modul hinzufügt. Er verwendet einen Pipeline Operator ( `|` ), um das Formattyp Objekt an das `Export-FormatData` Cmdlet zu senden, das es in XML zurück konvertiert und in der angegebenen `format.ps1xml` Datei speichert.

Der letzte Befehl zeigt einen Auszug aus dem `format.ps1xml` Dateiinhalt.

### Beispiel 5: erhalten von Formatierungsdaten basierend auf der angegebenen Version von PowerShell

In diesem Beispiel wird gezeigt, wie verwendet wird, `Get-FormatData` um Format Daten für einen angegebenen **Typnamen** und eine PowerShell-Version zu erhalten.

```powershell
Get-FormatData -TypeName 'Microsoft.Powershell.Utility.FileHash' -PowerShellVersion $PSVersionTable.PSVersion

TypeNames                               FormatViewDefinition
---------                               --------------------
{Microsoft.Powershell.Utility.FileHash} {Microsoft.Powershell.Utility.FileHash}
```

## PARAMETERS

### -PowerShellVersion

Geben Sie die PowerShell-Version an, die von diesem Cmdlet für die Formatierungsdaten abgerufen wird. Geben Sie eine zweistellige Zahl ein, die durch einen Zeitraum getrennt ist.

Dieser Parameter wurde in PowerShell 5,1 hinzugefügt, um die Kompatibilität bei Remoting-Computern zu verbessern, die ältere Versionen von PowerShell ausführen.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Typname

Gibt die Typnamen an, die dieses Cmdlet für die Formatierungsdaten abruft.
Geben Sie die Typnamen ein.
Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. extendedtypedefinition

## HINWEISE

## VERWANDTE LINKS

[Export-FormatData](Export-FormatData.md)

[Update-FormatData](Update-FormatData.md)
