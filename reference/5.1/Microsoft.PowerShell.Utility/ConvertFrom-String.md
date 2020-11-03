---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-String
ms.openlocfilehash: 665a0ca8332c4052b59362c7947e408ba811c5f2
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "93219796"
---
# ConvertFrom-String

## ZUSAMMENFASSUNG
Extrahiert und analysiert strukturierte Eigenschaften aus dem Zeichen folgen Inhalt.

## SYNTAX

### Bydelimiter (Standard)

```
ConvertFrom-String [-Delimiter <String>] [-PropertyNames <String[]>] [-InputObject] <String>
 [<CommonParameters>]
```

### Templatetesing

```
ConvertFrom-String [-TemplateFile <String[]>] [-TemplateContent <String[]>] [-IncludeExtent] [-UpdateTemplate]
 [-InputObject] <String> [<CommonParameters>]
```

## DESCRIPTION

Das **ConvertFrom-String-** Cmdlet extrahiert und analysiert strukturierte Eigenschaften aus dem Zeichen folgen Inhalt.
Dieses Cmdlet generiert ein Objekt, indem es Text aus einem herkömmlichen Textstream verarbeitet.
Für jede Zeichenfolge in der Pipeline teilt das Cmdlet die Eingabe entweder durch ein Trennzeichen oder einen Analyse Ausdruck auf und weist dann jedem der resultierenden geteilten Elemente Eigenschaftsnamen zu.
Sie können diese Eigenschaftsnamen angeben. Wenn Sie dies nicht tun, werden Sie automatisch für Sie generiert.

Der Standardparametersatz des Cmdlets, **bydelimiter** , wird genau für das Trennzeichen für reguläre Ausdrücke unterteilt.
Er führt keine Anführungszeichen oder Trennzeichen aus, wie es das `Import-Csv` Cmdlet tut.

Der Alternative Parametersatz des Cmdlets, **templatearsing** , generiert Elemente aus den Gruppen, die von einem regulären Ausdruck aufgezeichnet werden. Weitere Informationen zu regulären Ausdrücken finden Sie unter [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).

Dieses Cmdlet unterstützt zwei Modi: eine einfache, durch Trennzeichen getrennte und automatisch generierte, Beispiel gesteuerte Verarbeitung.

Bei der getrennten Analyse wird die Eingabe standardmäßig bei Leerzeichen getrennt, wobei den resultierenden Gruppen Eigenschaftsnamen zugewiesen werden.

Sie können das Trennzeichen anpassen, indem Sie die `ConvertFrom-String` Ergebnisse an eines der `Format-*` Cmdlets weiterleiten, oder Sie können den **Trennzeichen** -Parameter verwenden.

Das Cmdlet unterstützt auch automatisch generierte, Beispiel gesteuerte Analyse basierend auf den unter [suchungen von Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).

## BEISPIELE

### Beispiel 1: Generieren eines Objekts mit Standard Eigenschaftsnamen

```powershell
"Hello World" | ConvertFrom-String
```

```Output
P1    P2
--    --
Hello World
```

Mit diesem Befehl wird ein Objekt mit den Standard Eigenschaftsnamen **P1** und **P2** generiert.

### Beispiel 1a: Kennenlernen des generierten Objekts

Dieser Befehl generiert ein Objekt mit den Eigenschaften **P1** , **P2** ; beide Eigenschaften haben standardmäßig den Typ " **String** ".

```powershell
"Hello World" | ConvertFrom-String | Get-Member
```

```Output

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
P1          NoteProperty string P1=Hello
P2          NoteProperty string P2=World
```

### Beispiel 2: Generieren eines Objekts mit Standard Eigenschaftsnamen mithilfe eines Trenn Zeichens

Mit diesem Befehl wird ein Objekt mit einer Domäne und einem Benutzernamen generiert, wobei der umgekehrte Schrägstrich ( `\` ) als Trennzeichen verwendet wird. Der umgekehrte Schrägstrich muss bei Verwendung regulärer Ausdrücke mit einem anderen umgekehrten Schrägstrich versehen werden.

```powershell
"Contoso\Administrator" | ConvertFrom-String -Delimiter "\\"
```

```Output
P1      P2
--      --
Contoso Administrator
```

### Beispiel 3: Generieren eines Objekts, das zwei benannte Eigenschaften enthält

Im folgenden Beispiel werden-Objekte aus Windows Hosts-Datei Einträge erstellt.

```powershell
$content = Get-Content C:\Windows\System32\drivers\etc\hosts
$content = $content -match "^[^#]"
$content | ConvertFrom-String -PropertyNames IP, Server
```

```Output
IP             Server
--             ------
192.168.7.10   W2012R2
192.168.7.20   W2016
192.168.7.101  WIN8
192.168.7.102  WIN10
```

Das- `Get-Content` Cmdlet speichert den Inhalt einer Windows-Hostdatei in `$content` . Mit dem zweiten Befehl werden alle Kommentare am Anfang der Hosts-Datei mit einem regulären Ausdruck entfernt, der mit einer beliebigen Zeile übereinstimmt, die nicht mit ( `#` ) beginnt. Mit dem letzten Befehl wird der verbleibende Text in Objekte mit **Server** -und **IP-** Eigenschaften konvertiert.

### Beispiel 4: Verwenden Sie einen Ausdruck als Wert des TemplateContent-Parameters, und speichern Sie die Ergebnisse in einer Variablen.

Dieser Befehl verwendet einen Ausdruck als Wert des **TemplateContent** -Parameters.
Der Ausdruck wird aus Gründen der Einfachheit in einer Variablen gespeichert.
Windows PowerShell versteht nun, dass die Zeichenfolge, die in der Pipeline verwendet wird, über `ConvertFrom-String` drei Eigenschaften verfügt:

- **Name**
- **Smartphone**
- **Eder**

```powershell
$template = @'
{Name*:Phoebe Cat}, {phone:425-123-6789}, {age:6}
{Name*:Lucky Shot}, {phone:(206) 987-4321}, {age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789    6
Lucky Shot    (206) 987-4321  12
Elephant Wise 425-888-7766    87
Wild Shrimp   (111)  222-3333 1
```

Jede Zeile in der Eingabe wird von den Beispiel Übereinstimmungen ausgewertet. Wenn die Zeile mit den im Muster angegebenen Beispielen übereinstimmt, werden die Werte extrahiert und an die OUTPUT-Variable übergeben.

Die Beispiel Daten, `$template` , bieten zwei verschiedene Telefon Formate:

- `425-123-6789`
- `(206) 987-4321`

Die Beispiel Daten stellen auch zwei verschiedene Alters Formate bereit:

- `6`
- `12`

Dies impliziert, dass Telefone wie `(206) 987 4321` nicht erkannt werden, weil es keine Stichprobendaten gibt, die diesem Muster entsprechen, da keine Bindestriche vorhanden sind.

### Beispiel 5: Angeben von Datentypen für die generierten Eigenschaften

Dies ist das gleiche Beispiel wie Beispiel 4 oben.
Der Unterschied besteht darin, dass die Muster Zeichenfolge einen Datentyp für jede gewünschte Eigenschaft enthält.

```powershell
$template = @'
{[string]Name*:Phoebe Cat}, {[string]phone:425-123-6789}, {[int]age:6}
{[string]Name*:Lucky Shot}, {[string]phone:(206) 987-4321}, {[int]age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789      6
Lucky Shot    (206) 987-4321   12
Elephant Wise 425-888-7766     87
Wild Shrimp   (111)  222-3333   1
```

```powershell
$PersonalData | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
age         NoteProperty int age=6
Name        NoteProperty string Name=Phoebe Cat
phone       NoteProperty string phone=425-123-6789
```

Das- `Get-Member` Cmdlet wird verwendet, um anzuzeigen, dass die **Age** -Eigenschaft eine ganze Zahl ist.

## PARAMETERS

### -Delimiter

Gibt einen regulären Ausdruck an, der die Grenze zwischen Elementen identifiziert.
Elemente, die von der Teilung erstellt werden, werden im resultierenden Objekt zu Eigenschaften.
Das Trennzeichen wird letztendlich in einem Aufrufe der **Split** -Methode des Typs verwendet `[System.Text.RegularExpressions.RegularExpression]` .

```yaml
Type: System.String
Parameter Sets: ByDelimiter
Aliases: DEL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Includezblock

Gibt an, dass dieses Cmdlet eine standardmäßige Text Eigenschaft enthält, die standardmäßig entfernt wird.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: IE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt von der Pipeline empfangene Zeichen folgen oder eine Variable an, die ein Zeichen folgen Objekt enthält.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PropertyNames

Gibt ein Array von Eigenschaften Namen an, denen im resultierenden-Objekt geteilte Werte zugewiesen werden sollen.
Jede Textzeile, die Sie teilen oder analysieren, generiert Elemente, die Eigenschaftswerte darstellen.
Wenn das-Element das Ergebnis einer Erfassungs Gruppe ist und diese Erfassungs Gruppe benannt ist (z. b. `(?<name>)` oder `(?'name')` ), wird der Name dieser Erfassungs Gruppe der-Eigenschaft zugewiesen.

Wenn Sie Elemente im **propertyName** -Array bereitstellen, werden diese Namen Eigenschaften zugewiesen, die noch nicht benannt wurden.

Wenn Sie weitere Eigenschaften Namen bereitstellen, als Felder vorhanden sind, ignoriert PowerShell die zusätzlichen Eigenschaftsnamen. Wenn Sie nicht genug Eigenschaftsnamen angeben, um alle Felder zu benennen, weist PowerShell alle Eigenschaften, die nicht den Namen **P1** , **P2** usw. aufweisen, automatisch numerischen Eigenschaftsnamen zu.

```yaml
Type: System.String[]
Parameter Sets: ByDelimiter
Aliases: PN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateContent

Gibt einen Ausdruck oder einen als Variable gespeicherten Ausdruck an, der die Eigenschaften beschreibt, denen dieses Cmdlet Zeichen folgen zuweist. Die Syntax einer Vorlagen Feld Spezifikation lautet wie folgt: `{[optional-typecast]<name>:<example-value>}` .

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateFile

Gibt eine Datei als Array an, die eine Vorlage für die gewünschte Analyse der Zeichenfolge enthält.
In der Vorlagen Datei werden Eigenschaften und deren Werte in eckige Klammern eingeschlossen, wie unten gezeigt.
Wenn eine Eigenschaft, z. b. die **Name** -Eigenschaft und die zugehörigen anderen Eigenschaften, mehrmals angezeigt wird, können Sie ein Sternchen () hinzufügen, `*` um anzugeben, dass dies zu mehreren Datensätzen führt. Dadurch wird vermieden, dass mehrere Eigenschaften in einen einzelnen Datensatz extrahiert werden.

```
{Name*:David Chew}
{City:Redmond}, {State:WA}
{Name*:Evan Narvaez}    {Name*:Antonio Moreno}
{City:Issaquah}, {State:WA}
```

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Updatetemplate

Gibt an, dass dieses Cmdlet die Ergebnisse eines Lernalgorithmus in einem Kommentar in der Vorlagen Datei speichert.
Dadurch wird der algorithmuslernprozess schneller.
Um diesen Parameter zu verwenden, müssen Sie auch eine Vorlagen Datei mit dem Parameter **TemplateFile** angeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: UT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[ConvertFrom-String: Beispiel basierte Textverarbeitung](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)

[ConvertFrom-StringData](ConvertFrom-StringData.md)

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[ConvertTo-Xml](ConvertTo-Xml.md)
