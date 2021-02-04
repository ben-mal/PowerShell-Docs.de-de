---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/20/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-string?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-String
ms.openlocfilehash: 09995397e33bf3fa1facc4137f4517390d69b78e
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "98620172"
---
# Out-String

## Übersicht
Gibt Eingabe Objekte als Zeichen folgen aus.

## Syntax

### Nonewlineformatierung (Standard)

```
Out-String [-Width <Int32>] [-NoNewline] [-InputObject <PSObject>] [<CommonParameters>]
```

### Streamformatierung

```
Out-String [-Stream] [-Width <Int32>] [-InputObject <PSObject>] [<CommonParameters>]
```

## BESCHREIBUNG

Mit dem- `Out-String` Cmdlet werden Eingabe Objekte in Zeichen folgen konvertiert. Standardmäßig `Out-String` sammelt die Zeichen folgen und gibt Sie als eine einzelne Zeichenfolge zurück. Sie können jedoch den **Stream** -Parameter verwenden, um `Out-String` eine Zeile gleichzeitig zurückzugeben oder ein Array von Zeichen folgen zu erstellen. Mit diesem Cmdlet können Sie die Zeichenfolgenausgabe so wie in herkömmlichen Shells durchsuchen und bearbeiten, wenn die Objektbearbeitung ungeeignet ist.

## Beispiele

### Beispiel 1: erhalten der aktuellen Kultur und Konvertieren der Daten in Zeichen folgen

In diesem Beispiel werden die regionalen Einstellungen für den aktuellen Benutzer abgerufen und die Objektdaten in Zeichen folgen konvertiert.

```powershell
$C = Get-Culture | Select-Object -Property *
Out-String -InputObject $C -Width 100
```

```Output
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - en-US
TextInfo                       : TextInfo - en-US
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar,
                                 System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False
```

Die `$C` Variable speichert ein **Selected.System. Globalization. CultureInfo** -Objekt. Das-Objekt ist das Ergebnis des `Get-Culture` Sendens der Ausgabe in der Pipeline an `Select-Object` . Der **Property** -Parameter verwendet ein Sternchen-Platzhalter Zeichen ( `*` ), um alle Eigenschaften anzugeben, die im-Objekt enthalten sind.

`Out-String` verwendet den **Inputobject** -Parameter, um das **CultureInfo** -Objekt anzugeben, das in der Variablen gespeichert ist `$C` . Die Objekte in `$C` werden in eine Zeichenfolge konvertiert.

> [!NOTE]
> Um das `Out-String` Array anzuzeigen, speichern Sie die Ausgabe in einer Variablen, und verwenden Sie einen Array Index, um die Elemente anzuzeigen. Weitere Informationen zum Array Index finden Sie unter [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).
>
> `$str = Out-String -InputObject $C -Width 100`

### Beispiel 2: Arbeiten mit Objekten

Dieses Beispiel veranschaulicht den Unterschied zwischen dem Arbeiten mit Objekten und dem Arbeiten mit Zeichenfolgen. Der Befehl zeigt einen Alias an, der den Text **GCM** enthält, den Alias für `Get-Command` .

```powershell
Get-Alias | Out-String -Stream | Select-String -Pattern "gcm"
```

```Output
Alias           gcm -> Get-Command
```

`Get-Alias` Ruft die **System. Management. Automation. AliasInfo** -Objekte ab, eine für jeden Alias und sendet die Objekte in der Pipeline. `Out-String` verwendet den **Stream** -Parameter, um jedes-Objekt in eine Zeichenfolge zu konvertieren, indem alle-Objekte in einer einzelnen Zeichenfolge verkettet werden. Die **System. String** -Objekte werden über die Pipeline gesendet und `Select-String` verwenden den **Pattern** -Parameter, um Übereinstimmungen für den Text- **GCM** zu suchen.

> [!NOTE]
> Wenn Sie den **Stream** -Parameter weglassen, zeigt der Befehl alle Aliase an, da `Select-String` den Text- **GCM** in der einzelnen Zeichenfolge findet, die `Out-String` zurückgibt.

### Beispiel 3: Verwenden Sie den width-Parameter, um das Abschneiden zu verhindern.

Obwohl die meisten Ausgaben von `Out-String` in die nächste Zeile umschließt werden, gibt es Szenarien, in denen die Ausgabe vom Formatierungs System abgeschnitten wird, bevor Sie an weitergeleitet wird `Out-String` . Sie können das Abschneiden mithilfe des **Width** -Parameters vermeiden.

```powershell
PS> @{TestKey = ('x' * 200)} | Out-String
Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx...

PS> @{TestKey = ('x' * 200)} | Out-String -Width 250

Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## PARAMETERS

### -InputObject

Gibt die Objekte an, die in eine Zeichenfolge geschrieben werden. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

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

### -Nonewline

Entfernt alle Zeilenumbrüche aus der Ausgabe, die vom PowerShell-Formatierer generiert wurden. Zeilenumbrüche, die Teil der Zeichen folgen Objekte sind, werden beibehalten.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoNewLineFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stream

Standardmäßig `Out-String` gibt eine einzelne Zeichenfolge aus, die so formatiert ist, wie Sie in der-Konsole angezeigt wird, einschließlich leerer Header oder nachfolgender Zeilenumbruch. Der **Stream** -Parameter ermöglicht `Out-String` , jede Zeile nacheinander auszugeben. Die einzige Ausnahme hierbei sind mehrzeilige Zeichen folgen. In diesem Fall gibt `Out-String` die Zeichenfolge weiterhin als eine einzelne, mehrzeilige Zeichenfolge aus.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StreamFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Breite

Gibt die Anzahl der Zeichen in jeder Zeile der Ausgabe an. Alle zusätzlichen Zeichen werden je nach verwendetem Formatierer-Cmdlet in die nächste Zeile umschließt oder abgeschnitten. Der **Width** -Parameter gilt nur für Objekte, die formatiert werden. Wenn Sie diesen Parameter weglassen, wird die Breite durch die Merkmale des Hostprogramms bestimmt. Im Terminalfenster (Konsolenfenster) wird die aktuelle Fensterbreite als Standardwert verwendet. Bei der Installation von PowerShell-Konsolen Fenstern wird standardmäßig eine Breite von 80 Zeichen angezeigt.

```yaml
Type: System.Int32
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

### System. Management. Automation. psobject

Sie können Objekte über die Pipeline an senden `Out-String` .

## AUSGABEN

### System.String

`Out-String` Gibt die Zeichenfolge zurück, die aus dem Eingabe Objekt erstellt wird.

## HINWEISE

Die Cmdlets, die das `Out` Verb enthalten, formatieren Objekte nicht. Die- `Out` Cmdlets senden-Objekte an das Formatierer für das angegebene Anzeige Ziel.

## VERWANDTE LINKS

[about_Formatting](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[Out-Default](../Microsoft.PowerShell.Core/Out-Default.md)

[Out-File](Out-File.md)

[Out-Host](../Microsoft.PowerShell.Core/Out-Host.md)

[Out-Null](../Microsoft.PowerShell.Core/Out-Null.md)

[Out-GridView](Out-GridView.md)

[Out-Printer](Out-Printer.md)
