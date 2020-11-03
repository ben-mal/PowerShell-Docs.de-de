---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/join-string?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-String
ms.openlocfilehash: bae6b8558a3e12bf161d8f0ec12037841a20cc04
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211196"
---
# Join-String

## ZUSAMMENFASSUNG
Kombiniert Objekte aus der Pipeline zu einer einzelnen Zeichenfolge.

## SYNTAX

### Standard (Standard)

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-UseCulture] [-InputObject <PSObject[]>] [<CommonParameters>]
```

### Singleanführungs Zeichen

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-SingleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### Doppeltes Anführungszeichen

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-DoubleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### Format

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-FormatString <String>] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

## DESCRIPTION

Das `Join-String` Cmdlet verknüpft oder kombiniert Text von Pipeline Objekten in einer einzelnen Zeichenfolge.

Wenn keine Parameter angegeben werden, werden die Pipeline Objekte in eine Zeichenfolge konvertiert und mit dem Standard Trennzeichen verknüpft `$OFS` .

Wenn Sie einen Eigenschaftsnamen angeben, wird der Wert der Eigenschaft in eine Zeichenfolge konvertiert und in eine Zeichenfolge aufgenommen.

Anstelle eines Eigenschafts namens kann ein Skriptblock verwendet werden. Das Ergebnis des Skript Blocks wird in eine Zeichenfolge konvertiert, bevor es verknüpft wird, um das Ergebnis zu bilden. Es kann entweder der Text der-Eigenschaft eines Objekts oder das Ergebnis des-Objekts, das in eine Zeichenfolge konvertiert wurde, kombiniert werden.

Dieses Cmdlet wurde in PowerShell 6,2 eingeführt.

## BEISPIELE

### Beispiel 1: Verknüpfen von Verzeichnisnamen

<!-- markdownlint-disable MD038 -->
In diesem Beispiel werden Verzeichnisnamen miteinander verbunden, die Ausgabe wird in doppelte Anführungszeichen eingeschlossen und die Verzeichnisnamen werden durch ein Komma und ein Leerzeichen ( `, ` ) getrennt. Bei der Ausgabe handelt es sich um ein Zeichen folgen Objekt.

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property Name -DoubleQuote -Separator ', '
```

```Output
"PerfLogs", "Program Files", "Program Files (x86)", "Users", "Windows"
```

`Get-ChildItem` verwendet den **Directory** -Parameter, um alle Verzeichnisnamen für das `C:\` Laufwerk zu erhalten.
Die Objekte werden über die Pipeline an gesendet `Join-String` . Der **Property** -Parameter gibt die Verzeichnisnamen an. Der **Double Quote** -Parameter umschließt die Verzeichnisnamen in doppelte Anführungszeichen.
Der **Separator** -Parameter gibt an, dass ein Komma und ein Leerzeichen ( `, ` ) zum Trennen der Verzeichnisnamen verwendet werden sollen.

`Get-ChildItem`Bei den Objekten handelt es sich um **System. IO. directoriyinfo** `Join-String` , und die Objekte werden in **System. String** konvertiert.

### Beispiel 2: Verwenden einer Eigenschafts Teil Zeichenfolge zum Verknüpfen von Verzeichnisnamen

In diesem Beispiel wird eine Teil Zeichenfolge-Methode verwendet, um die ersten vier Buchstaben von Verzeichnisnamen zu erhalten, die Ausgabe in einfache Anführungszeichen umschließt und die Verzeichnisnamen durch ein Semikolon () voneinander zu trennen `;` .

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property {$_.Name.SubString(0,4)} -SingleQuote -Separator ';'
```

```Output
'Perf';'Prog';'Prog';'User';'Wind'
```

`Get-ChildItem` verwendet den **Directory** -Parameter, um alle Verzeichnisnamen für das `C:\` Laufwerk zu erhalten.
Die Objekte werden über die Pipeline an gesendet `Join-String` .

Der **Property** -Parameter Skriptblock verwendet die automatische Variable ( `$_` ), um die **Name** -Eigenschafts Teil Zeichenfolge jedes Objekts anzugeben. Die Teil Zeichenfolge Ruft die ersten vier Buchstaben jedes Verzeichnis namens ab. Die Teil Zeichenfolge gibt die Start-und Endpositionen des Zeichens an. Der **singlequote** -Parameter umschließt die Verzeichnisnamen in einfache Anführungszeichen. Der **Separator** -Parameter gibt an, dass ein Semikolon ( `;` ) zum Trennen der Verzeichnisnamen verwendet werden soll.

Weitere Informationen zu automatischen Variablen und Teil Zeichenfolgen finden Sie unter [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) und [Teil Zeichenfolge](/dotnet/api/system.string.substring).

### Beispiel 3: Anzeigen der joinausgabe in einer separaten Zeile

In diesem Beispiel werden Dienstnamen mit den einzelnen Diensten in einer separaten Zeile und eingerückt durch eine Registerkarte verbunden.

```powershell
Get-Service -Name se* | Join-String -Property Name -Separator "`r`n`t" -OutputPrefix "Services:`n`t"
```

```Output
Services:
    seclogon
    SecurityHealthService
    SEMgrSvc
    SENS
    Sense
    SensorDataService
    SensorService
    SensrSvc
    SessionEnv
```

`Get-Service` verwendet den **Name** -Parameter mit, um Dienste anzugeben, die mit beginnen `se*` . Das Sternchen ( `*` ) ist ein Platzhalter für ein beliebiges Zeichen.

Die Objekte werden an die Pipeline gesendet, die den `Join-String` **Property** -Parameter verwendet, um die Dienstnamen anzugeben. Der **Separator** -Parameter gibt drei Sonderzeichen an, die ein Wagen Rücklauf Zeichen (), Zeilenumbruch Zeichen `` `r `` ( `` `n `` ) und Tabulator Zeichen () darstellen `` `t `` . **Outputprefix** fügt einen Label- **Dienst ein:** eine neue Zeile und eine neue Registerkarte vor der ersten Zeile der Ausgabe.

Weitere Informationen zu Sonderzeichen finden Sie unter [about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md).

### Beispiel 4: Erstellen einer Klassendefinition aus einem Objekt

In diesem Beispiel wird eine PowerShell-Klassendefinition mit einem vorhandenen-Objekt als Vorlage generiert.

Dieses Codebeispiel verwendet Verteilung, um die Zeilenlänge zu verringern und die Lesbarkeit zu verbessern. Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

```powershell
$obj = [pscustomobject] @{Name = "Joe"; Age = 42}
$parms = @{
  Property = "Name"
  FormatString = '  ${0}'
  OutputPrefix = "class {`n"
  OutputSuffix = "`n}`n"
  Separator = "`n"
}
$obj.PSObject.Properties | Join-String @parms
```

```Output
class {
  $Name
  $Age
}
```

## PARAMETERS

### -Doubleanführungs Zeichen

Umschließt den Zeichen folgen Wert jedes Pipeline Objekts in doppelten Anführungszeichen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DoubleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Format Zeichenfolge

Eine Format Zeichenfolge, die angibt, wie die einzelnen Elemente formatiert werden sollen.

```yaml
Type: System.String
Parameter Sets: Format
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt den Text an, der verknüpft werden soll. Geben Sie eine Variable ein, die den Text enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden, die in Zeichen folgen

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Outputprefix

Text, der vor der Ausgabe Zeichenfolge eingefügt wird. Die Zeichenfolge kann Sonderzeichen wie z. b. Wagen Rücklauf ( `` `r `` ), Zeilenumbruch ( `` `n `` ) und Tab ( `` `t `` ) enthalten.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: op

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Outputsuffix

Text, der an die Ausgabe Zeichenfolge angefügt wird. Die Zeichenfolge kann Sonderzeichen wie z. b. Wagen Rücklauf ( `` `r `` ), Zeilenumbruch ( `` `n `` ) und Tab ( `` `t `` ) enthalten.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Eigenschaft

Der Name einer Eigenschaft oder ein Eigenschafts Ausdruck, der das Pipeline Objekt in Text projizieren soll.

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Trennzeichen

Text oder Zeichen, z. b. ein Komma oder Semikolon, das zwischen dem Text für jedes Pipeline Objekt eingefügt wird.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Singleanführungs Zeichen

Umschließt den Zeichen folgen Wert jedes Pipeline Objekts in einfache Anführungszeichen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SingleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Useculture

Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen. Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

## AUSGABEN

### System.String

## HINWEISE

## VERWANDTE LINKS

[about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md)

[about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md)

[Teil Zeichenfolge](/dotnet/api/system.string.substring)
