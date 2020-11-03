---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Clixml
ms.openlocfilehash: 4e6d7e584350d25816dbc32ea35a50d916d9ffe4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213887"
---
# Import-Clixml

## ZUSAMMENFASSUNG
Importiert eine CliXML-Datei und erstellt entsprechende Objekte in PowerShell.

## SYNTAX

### Bypath (Standard)

```
Import-Clixml [-Path] <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

### Byliteralpath

```
Import-Clixml -LiteralPath <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Import-Clixml` Cmdlet importiert eine Common Language Infrastructure (CLI)-XML-Datei mit Daten, die Microsoft .NET Framework-Objekten darstellen, und erstellt die PowerShell-Objekte. Weitere Informationen zur CLI finden Sie unter [Sprachunabhängigkeit](/dotnet/standard/language-independence).

Eine wertvolle Verwendung von `Import-Clixml` auf Windows-Computern besteht darin, Anmelde Informationen und sichere Zeichen folgen zu importieren, die mithilfe von als sicheres XML exportiert wurden `Export-Clixml` . Ein Beispiel finden Sie unter Beispiel 2.

`Import-Clixml` verwendet die Byte Reihenfolge-Markierung (BOM), um das Codierungsformat der Datei zu erkennen. Wenn die Datei keine BOM enthält, wird davon ausgegangen, dass die Codierung UTF8 ist.

## BEISPIELE

### Beispiel 1: Importieren einer serialisierten Datei und erneutes Erstellen eines Objekts

In diesem Beispiel wird das- `Export-Clixml` Cmdlet verwendet, um eine serialisierte Kopie der von zurückgegebenen Prozessinformationen zu speichern `Get-Process` . `Import-Clixml` Ruft den Inhalt der serialisierten Datei ab und erstellt ein in der Variablen gespeichertes Objekt neu `$Processes` .

```powershell
Get-Process | Export-Clixml -Path .\pi.xml
$Processes = Import-Clixml -Path .\pi.xml
```

### Beispiel 2: Importieren eines sicheren Anmelde Informationsobjekts

In diesem Beispiel können Sie mit den Anmelde Informationen, die Sie `$Credential` durch Ausführen des Cmdlets in der Variablen gespeichert haben `Get-Credential` , das `Export-Clixml` Cmdlet ausführen, um die Anmelde Informationen auf dem Datenträger zu speichern.

> [!IMPORTANT]
> `Export-Clixml` exportiert nur verschlüsselte Anmelde Informationen unter Windows. Bei nicht-Windows-Betriebssystemen wie macOS und Linux werden Anmelde Informationen als nur-Text exportiert.

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

Mit dem- `Export-Clixml` Cmdlet werden Anmelde Informationsobjekte mithilfe der Windows- [Datenschutz-API](/previous-versions/windows/apps/hh464970(v=win.10))verschlüsselt.
Durch die Verschlüsselung wird sichergestellt, dass nur Ihr Benutzerkonto den Inhalt des Anmelde Informationsobjekts entschlüsseln kann. Die exportierte `CLIXML` Datei kann nicht auf einem anderen Computer oder von einem anderen Benutzer verwendet werden.

Im Beispiel wird die Datei, in der die Anmelde Informationen gespeichert werden, durch dargestellt `TestScript.ps1.credential` . Ersetzen Sie **testScript** durch den Namen des Skripts, mit dem die Anmelde Informationen geladen werden.

Sie senden das Anmelde Informationen-Objekt über die Pipeline an `Export-Clixml` und speichern es in dem Pfad, `$Credxmlpath` , den Sie im ersten Befehl angegeben haben.

Führen Sie die letzten beiden Befehle aus, um die Anmelde Informationen automatisch in das Skript zu importieren. Führen `Import-Clixml` Sie aus, um das gesicherte Anmelde Informationsobjekt in das Skript zu importieren. Dieser Import vermeidet das Risiko, dass nur-Text-Kenn Wörter in Ihrem Skript verfügbar gemacht werden.

## PARAMETERS

### -Zuerst

Ruft nur die angegebene Anzahl von Objekten ab. Geben Sie die Anzahl der abzurufenden Objekte an.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Incluabtotalcount

Gibt die Gesamtanzahl der Objekte im DataSet an, gefolgt von den ausgewählten Objekten. Wenn das Cmdlet die Gesamtanzahl nicht ermitteln kann, wird eine **unbekannte Gesamtanzahl** angezeigt. Die Ganzzahl hat eine **Genauigkeits** Eigenschaft, die die Zuverlässigkeit des Gesamtanzahl Werts angibt. Der Wert der **Genauigkeit** reicht von bis zu, d. h., das `0.0` `1.0` `0.0` Cmdlet kann die Objekte nicht zählen, `1.0` bedeutet, dass die Anzahl exakt ist, und ein Wert zwischen `0.0` und `1.0` gibt eine immer zuverlässigere Schätzung an.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Literalpath

Gibt den Pfad zu den XML-Dateien an. Im Gegensatz zu **path** wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zu den XML-Dateien an.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Skip

Ignoriert die angegebene Anzahl an Objekten und ruft anschließend die übrigen Objekte ab. Geben Sie die Anzahl der zu überspringenden Objekte an.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge mit einem Pfad zu Pipeline Pipeline in Pipeline `Import-Clixml`

## AUSGABEN

### PSObject

`Import-Clixml` gibt Objekte zurück, die aus den gespeicherten XML-Dateien deserialisiert wurden.

## HINWEISE

Wenn Sie für einen Parameter mehrere Werte angeben, verwenden Sie Kommas zur Trennung der Werte. Beispiel: `<parameter-name> <value1>, <value2>`.

## VERWANDTE LINKS

[Export-Clixml](Export-Clixml.md)

[Einführung in die XML-Serialisierung](/dotnet/standard/serialization/introducing-xml-serialization)

[Join-Path](../Microsoft.PowerShell.Management/Join-Path.md)

[Anmelde Informationen auf dem Datenträger sicher speichern](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[Verwenden von PowerShell zum Übergeben von Anmelde Informationen an Legacy Systeme](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)
