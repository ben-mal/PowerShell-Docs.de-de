---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-localizeddata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-LocalizedData
ms.openlocfilehash: d19279133a42e3aea17f02348e44aec161ba5a23
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239991"
---
# Import-LocalizedData

## ZUSAMMENFASSUNG
Importiert sprachspezifische Daten in Skripts und Funktionen, basierend auf der Benutzeroberflächenkultur, die für das Betriebssystem ausgewählt ist.

## SYNTAX

```
Import-LocalizedData [[-BindingVariable] <String>] [[-UICulture] <String>] [-BaseDirectory <String>]
 [-FileName <String>] [-SupportedCommand <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Import-LocalizedData` Cmdlet werden Zeichen folgen dynamisch aus einem Unterverzeichnis abgerufen, dessen Name mit der Benutzeroberflächen Sprache übereinstimmt, die für den aktuellen Benutzer des Betriebssystems festgelegt wurde. Es dient der Aktivierung von Skripts, um Benutzermeldungen in der vom aktuellen Benutzer ausgewählten Benutzeroberflächensprache anzuzeigen.

`Import-LocalizedData` importiert Daten aus `.psd1` Dateien in sprachspezifischen Unterverzeichnissen des Skript Verzeichnisses und speichert Sie in einer lokalen Variablen, die im Befehl angegeben wird. Das-Cmdlet wählt das Unterverzeichnis und die Datei basierend auf dem Wert der `$PSUICulture` automatischen Variablen aus. Wenn Sie die lokale Variable im Skript verwenden, um eine Benutzermeldung anzuzeigen, wird die Meldung in der Benutzeroberflächensprache des Benutzers angezeigt.

Sie können mit den Parametern von `Import-LocalizedData` eine Alternative Benutzeroberflächen Kultur, einen Pfad und einen Dateinamen angeben, unterstützte Befehle hinzufügen und die Fehlermeldung unterdrücken, die angezeigt wird, wenn die `.psd1` Dateien nicht gefunden werden.

Das `Import-LocalizedData` Cmdlet unterstützt die Skript Internationalisierungs Initiative, die in Windows PowerShell 2,0 eingeführt wurde. Ziel dieser Initiative ist es, Benutzern weltweit einen besseren Dienst zu bieten, indem es Skripts erleichtert wird, Benutzermeldungen in der Sprache der Benutzeroberfläche des aktuellen Benutzers anzuzeigen. Weitere Informationen zu diesem und zum Format der `.psd1` Dateien finden Sie unter [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).

## BEISPIELE

### Beispiel 1: Importieren von Text Zeichenfolgen

In diesem Beispiel werden Text Zeichenfolgen in die- `$Messages` Variable importiert. Es werden die Standardwerte aller anderen Cmdlet-Parameter verwendet.

```powershell
Import-LocalizedData -BindingVariable "Messages"
```

Wenn der Befehl im Archives.ps1 Skript im Verzeichnis enthalten ist `C:\Test` und der Wert der `$PsUICulture` automatischen Variablen zh-cn ist, `Import-LocalizedData` importiert die `Archives.psd1` Datei im `C:\test\zh-CN` Verzeichnis in die `$Messages` Variable.

### Beispiel 2: Importieren lokalisierter Daten Zeichenfolgen

Dieses Beispiel wird in der Befehlszeile ausgeführt, die nicht in einem Skript ausgeführt wird. Er ruft lokalisierte Datenzeichenfolgen aus der Datei „Test.psd1“ ab, und zeigt sie in der Befehlszeile an. Da der Befehl nicht in einem Skript verwendet wird, ist der **FileName** -Parameter erforderlich. Der Befehl verwendet den **UICulture** -Parameter, um die Kultur "en-US" anzugeben.

```powershell
Import-LocalizedData -FileName "Test.psd1" -UICulture "en-US"
```

```Output
Name                           Value
----                           -----
Msg3                           "Use $_ to represent the object that is being processed."
Msg2                           "This command requires the credentials of a member of the Administrators group on the...
Msg1                           "The Name parameter is missing from the command."
```

`Import-LocalizedData` gibt eine Hash Tabelle mit den lokalisierten Daten Zeichenfolgen zurück.

### Beispiel 3: Importieren von UI-Kultur Zeichenfolgen

```powershell
Import-LocalizedData -BindingVariable "MsgTbl" -UICulture "ar-SA" -FileName "Simple" -BaseDirectory "C:\Data\Localized"
```

Dieser Befehl importiert Text Zeichenfolgen in die- `$MsgTbl` Variable eines Skripts.

Er verwendet den **UICulture** -Parameter, um das Cmdlet anzuweisen, Daten aus der `Simple.psd1` Datei in das `ar-SA` Unterverzeichnis von zu importieren `C:\Data\Localized` .

### Beispiel 4: Importieren lokalisierter Daten in ein Skript

In diesem Beispiel wird veranschaulicht, wie lokalisierte Daten in einem einfachen Skript verwendet werden.

```powershell
PS C:\> # In C:\Test\en-US\Test.psd1:

ConvertFrom-StringData @'

# English strings

Msg1 = "The Name parameter is missing from the command."
Msg2 = "This command requires the credentials of a member of the Administrators group on the computer."
Msg3 = "Use $_ to represent the object that is being processed."
'@

# In C:\Test\Test.ps1

Import-LocalizedData -BindingVariable "Messages"
Write-Host $Messages.Msg2

# In Windows PowerShell

PS C:\> .\Test.ps1

This command requires the credentials of a member of the Administrators group on the computer.
```

Der erste Teil des Beispiels zeigt den Inhalt der `Test.psd1` Datei. Sie enthält einen `ConvertFrom-StringData` Befehl, mit dem eine Reihe benannter Text Zeichenfolgen in eine Hash Tabelle konvertiert wird. Die `Test.psd1` Datei befindet sich im Unterverzeichnis "en-US" des `C:\Test` Verzeichnisses, das das Skript enthält.

Der zweite Teil des Beispiels zeigt den Inhalt des `Test.ps1` Skripts. Sie enthält einen `Import-LocalizedData` Befehl, mit dem die Daten aus der übereinstimmenden `.psd1` Datei in die-Variable importiert werden, `$Messages` sowie einen `Write-Host` Befehl, mit dem eine der Nachrichten in der `$Messages` Variablen in das Host Programm geschrieben wird.

Der letzte Teil des Beispiels führt das Skript aus. Die Ausgabe zeigt, dass die richtige Benutzermeldung in der Benutzeroberflächensprache angezeigt wird, die für den aktuellen Benutzer des Betriebssystems festgelegt wurde.

### Beispiel 5: Ersetzen von Standardtext Zeichenfolgen in einem Skript

In diesem Beispiel wird gezeigt, wie verwendet wird `Import-LocalizedData` , um die im Daten Abschnitt eines Skripts definierten Standardtext Zeichenfolgen zu ersetzen.

```powershell
PS C:\> # In TestScript.ps1
$UserMessages = DATA

{    ConvertFrom-StringData @'

    # English strings

        Msg1 = "Enter a name."
        Msg2 = "Enter your employee ID."
        Msg3 = "Enter your building number."
'@
}

Import-LocalizedData -BindingVariable "UserMessages"
$UserMessages.Msg1...
```

In diesem Beispiel enthält der Daten Abschnitt des TestScript.ps1 Skripts einen `ConvertFrom-StringData` Befehl, der den Inhalt des Daten Abschnitts in eine Hash Tabelle konvertiert und den Wert der `$UserMessages` Variablen speichert.

Das Skript enthält außerdem einen- `Import-LocalizedData` Befehl, der eine Hash Tabelle mit übersetzten Text Zeichenfolgen aus der TestScript.psd1-Datei in dem Unterverzeichnis importiert, das durch den Wert der-Variable angegeben wird `$PsUICulture` . Wenn der Befehl die `.psd1` Datei findet, speichert Sie die übersetzten Zeichen folgen aus der Datei im Wert derselben `$UserMessages` Variablen und überschreibt die Hash Tabelle, die von der Daten Abschnitts Logik gespeichert wird.

Der dritte Befehl zeigt die erste Meldung in der `$UserMessages` Variablen an.

Wenn der `Import-LocalizedData` Befehl eine `.psd1` Datei für die `$PsUICulture` Sprache findet, enthält der Wert der `$UserMessages` Variablen die übersetzten Text Zeichenfolgen. Wenn der Befehl aus irgendeinem Grund fehlschlägt, zeigt der Befehl die im DATA-Abschnitt des Skripts definierten Standardtextzeichenfolgen an.

### Beispiel 6: Unterdrücken von Fehlermeldungen, wenn die UI-Kultur nicht gefunden wird

In diesem Beispiel wird gezeigt, wie Sie die Fehlermeldungen unterdrücken können, die angezeigt werden, wenn `Import-LocalizedData` die Verzeichnisse, die der Benutzeroberflächen Kultur des Benutzers entsprechen, nicht finden können oder keine `.psd1` Datei für das Skript in diesen Verzeichnissen finden.

```powershell
PS C:\> # In Day1.ps1

Import-LocalizedData -BindingVariable "Day"

# In Day2.ps1

Import-LocalizedData -BindingVariable "Day" -ErrorAction:SilentlyContinue

PS C:\> .\Day1.ps1
Import-LocalizedData : Cannot find PowerShell data file 'Day1.psd1' in directory 'C:\ps-test\fr-BE\' or any parent culture directories.
At C:\ps-test\Day1.ps1:17 char:21+ Import-LocalizedData <<<<  Day
Today is Tuesday

PS C:\> .\Day2.ps1
Today is Tuesday
```

Sie können den allgemeinen **ErrorAction** -Parameter mit dem Wert SilentlyContinue verwenden, um die Fehlermeldung zu unterdrücken. Dies ist besonders nützlich, wenn Sie Benutzer Meldungen in einer Standard-oder Fall Back Sprache bereitgestellt haben und keine Fehlermeldung erforderlich ist.

In diesem Beispiel werden zwei Skripts `Day1.ps1` und Day2.ps1 verglichen, die einen- `Import-LocalizedData` Befehl enthalten. Die Skripts sind identisch, mit dem Unterschied, dass "day2 den allgemeinen **ErrorAction** -Parameter mit einem Wert von verwendet `SilentlyContinue` .

Die Beispielausgabe zeigt die Ergebnisse der Ausführung beider Skripts, wenn die Benutzeroberflächen Kultur auf festgelegt ist `fr-BE` und es keine übereinstimmenden Dateien oder Verzeichnisse für diese Benutzeroberflächen Kultur gibt. `Day1.ps1` zeigt eine Fehlermeldung und eine englische Ausgabe an. `Day2.ps1` zeigt nur die englische Ausgabe an.

## PARAMETERS

### -BaseDirectory

Gibt das Basisverzeichnis an, in dem `.psd1` sich die Dateien befinden. Der Standardwert ist das Verzeichnis, in dem das Skript gespeichert ist. `Import-LocalizedData` sucht die `.psd1` Datei für das Skript in einem sprachspezifischen Unterverzeichnis des Basisverzeichnisses.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bindingvariable

Gibt die Variable an, in die die Textzeichenfolgen importiert werden. Geben Sie einen Variablennamen ohne Dollarzeichen ( `$` ) ein.

Dieser Parameter ist in Windows PowerShell 2.0 erforderlich. Dieser Parameter ist in Windows PowerShell 3.0 optional. Wenn Sie diesen Parameter weglassen, `Import-LocalizedData` gibt eine Hash Tabelle der Text Zeichenfolgen zurück. Die Hashtabelle wird über die Pipeline übergeben oder in der Befehlszeile angezeigt.

Wenn Sie verwenden `Import-LocalizedData` , um im Data-Abschnitt eines Skripts angegebene Standardtext Zeichenfolgen zu ersetzen, weisen Sie den Daten Abschnitt einer Variablen zu, und geben Sie den Namen der Daten Abschnitts Variablen in den Wert des **bindingvariable** -Parameters ein. Wenn dann `Import-LocalizedData` den importierten Inhalt in der **bindingvariable** speichert, werden die Standardtext Zeichenfolgen durch die importierten Daten ersetzt. Wenn Sie keine Standardtextzeichenfolgen angeben, können Sie einen beliebigen Variablennamen auswählen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Variable

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dateiname

Gibt den Namen der `.psd1)` zu importierenden Datendatei an. Geben Sie einen Dateinamen ein. Sie können einen Dateinamen angeben, der die `.psd1` Dateinamenerweiterung nicht enthält, oder Sie können den Dateinamen angeben, einschließlich der `.psd1` Dateinamenerweiterung. Datendateien sollten als Unicode oder UTF-8 gespeichert werden.

Der **filename** -Parameter ist erforderlich, wenn `Import-LocalizedData` nicht in einem Skript verwendet wird.
Anderenfalls ist der Parameter optional, und der Standardwert ist der Basisname des Skripts. Sie können diesen Parameter verwenden, um `Import-LocalizedData` eine andere Datei zu suchen `.psd1` .

Wenn z. b. der **Dateiname** weggelassen wird und der Skript Name FindFiles.ps1 ist, `Import-LocalizedData` sucht nach der FindFiles.psd1-Datendatei.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Supportedcommand

Gibt Cmdlets und Funktionen an, die nur Daten generieren.

Verwenden Sie diesen Parameter, um Cmdlets und Funktionen einzuschließen, die Sie geschrieben oder getestet haben. Weitere Informationen finden Sie unter [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UICulture

Gibt eine alternative Benutzeroberflächenkultur an.
Der Standardwert ist der Wert der `$PsUICulture` automatischen Variablen.
Geben Sie eine Benutzeroberflächen Kultur im `<language>-<region>` Format ein, z `en-US` . b `de-DE` ., oder `ar-SA` .

Der Wert des **UICulture** -Parameters bestimmt das sprachspezifische Unterverzeichnis (innerhalb des Basisverzeichnisses), von dem `Import-LocalizedData` die `.psd1` Datei für das Skript abgerufen wird.

Das-Cmdlet sucht nach einem Unterverzeichnis mit dem gleichen Namen wie der Wert des **UICulture** -Parameters oder der `$PsUICulture` automatischen Variablen, `de-DE` z `ar-SA` . b. oder. Wenn das Verzeichnis nicht gefunden werden kann oder wenn das Verzeichnis keine `.psd1` Datei für das Skript enthält, sucht es nach einem Unterverzeichnis mit dem Namen des Sprachcodes, z. b. "de" oder "ar". Wenn das Unterverzeichnis oder die Datei nicht gefunden `.psd1` werden kann, schlägt der Befehl fehl, und die Daten werden in der Standardsprache angezeigt, die im Skript angegeben ist.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System.Collections.Hashtable

`Import-LocalizedData` speichert die Hash Tabelle in der Variablen, die durch den Wert des **bindingvariable** -Parameters angegeben wird.

## HINWEISE

- Vor der Verwendung von `Import-LocalizedData` können Sie Ihre Benutzer Nachrichten lokalisieren. Formatieren Sie die Nachrichten für jedes Gebiets Schema (UI-Kultur) in einer Hash Tabelle mit Schlüssel-Wert-Paaren, und speichern Sie die Hash Tabelle in einer Datei mit dem gleichen Namen wie das Skript und einer `.psd1` Dateinamenerweiterung. Erstellen Sie für jede unterstützte Benutzeroberflächen Kultur im Skriptverzeichnis ein Verzeichnis, und speichern Sie dann die `.psd1` Datei für jede Benutzeroberflächen Kultur im Verzeichnis mit dem Namen der Benutzeroberflächen Kultur.

  Lokalisieren Sie beispielsweise Benutzermeldungen für das Gebietsschema „de-DE“, und formatieren Sie sie in einer Hashtabelle.
  Speichert die Hash Tabelle in einer `<ScriptName>.psd1` Datei. Erstellen Sie dann ein unter `de-DE` Verzeichnis unter dem Skriptverzeichnis, und speichern Sie die deutsche `<ScriptName\>.psd1` Datei im `de-DE` Unterverzeichnis.
  Wiederholen Sie diese Methode für jedes Gebietsschema, das Sie unterstützen.

- `Import-LocalizedData` führt eine strukturierte Suche nach den lokalisierten Benutzer Nachrichten für ein Skript aus.

  `Import-LocalizedData` startet die Suche in dem Verzeichnis, in dem sich die Skriptdatei befindet (oder dem Wert des **BaseDirectory** -Parameters). Anschließend wird im Basisverzeichnis nach einem Unterverzeichnis mit dem gleichen Namen wie der Wert der `$PsUICulture` Variablen (oder dem Wert des **UICulture** -Parameters) durchsucht, z `de-DE` . b `ar-SA` . oder. Anschließend sucht er in diesem Unterverzeichnis nach einer `.psd1` Datei mit dem gleichen Namen wie das Skript (oder dem Wert des **filename** -Parameters).

  Wenn `Import-LocalizedData` ein Unterverzeichnis mit dem Namen der UI-Kultur nicht finden kann oder das Unterverzeichnis keine `.psd1` Datei für das Skript enthält, sucht es nach einer `.psd1` Datei für das Skript in einem Unterverzeichnis mit dem Namen des Sprachcodes, z. b. "de" oder "ar". Wenn das Unterverzeichnis oder die Datei nicht gefunden `.psd1` werden kann, schlägt der Befehl fehl, die Daten werden in der Standardsprache im Skript angezeigt, und es wird eine Fehlermeldung mit dem Hinweis angezeigt, dass die Daten nicht importiert werden konnten. Verwenden Sie den allgemeinen **ErrorAction** -Parameter mit dem Wert SilentlyContinue, um die Meldung zu unterdrücken und ordnungsgemäß fehlschlagen.

  Wenn `Import-LocalizedData` das Unterverzeichnis und die `.psd1` Datei findet, wird die Hash Tabelle mit Benutzer Nachrichten in den Wert des **bindingvariable** -Parameters im Befehl importiert. Wenn Sie dann eine Meldung aus der Hashtabelle in der Variablen anzeigen, wird die lokalisierte Meldung angezeigt.

  Weitere Informationen finden Sie unter [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md).

## VERWANDTE LINKS

[Write-Host](Write-Host.md)

[Import-PowerShellDataFile](Import-PowerShellDataFile.md)

