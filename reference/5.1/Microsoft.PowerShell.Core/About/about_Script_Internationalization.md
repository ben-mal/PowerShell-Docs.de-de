---
description: Beschreibt die Skript Internationalisierungs Features, mit denen Skripts das Anzeigen von Nachrichten und Anweisungen an Benutzer in der Benutzeroberfläche (UI) erleichtern.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_internationalization?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Internationalization
ms.openlocfilehash: 51772eeb7517b5c61d9bc7a4333642684de6c37e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222535"
---
# <a name="about-script-internationalization"></a>Informationen zur Skript Internationalisierung

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt die Skript Internationalisierungs Features, mit denen Skripts das Anzeigen von Nachrichten und Anweisungen an Benutzer in der Benutzeroberfläche (UI) erleichtern.

## <a name="long-description"></a>Lange Beschreibung

Mit den Funktionen zur Internationalisierung von PowerShell-Skripts können Sie Benutzer weltweit besser bedienen, indem Sie Hilfe und Benutzer Meldungen in der Sprache des Benutzers anzeigen.

Die Skript Internationalisierungs Funktionen Fragen die Benutzeroberflächen Kultur des Betriebssystems während der Ausführung ab, importieren die entsprechenden übersetzten Text Zeichenfolgen und zeigen Sie dem Benutzer an. Mit dem Daten Abschnitt können Sie Text Zeichenfolgen getrennt von Code speichern, damit Sie leicht identifiziert und extrahiert werden können. Ein neues Cmdlet, `ConvertFrom-StringData` , konvertiert Text Zeichenfolgen in Wörterbuch ähnliche Hash Tabellen, um die Übersetzung zu vereinfachen.

Zur Unterstützung von International Help Text umfasst PowerShell die folgenden Features:

- Ein Daten Abschnitt, der Text Zeichenfolgen aus Code Anweisungen trennt. Weitere Informationen zum Abschnitt "Data" finden Sie unter [about_Data_Sections](about_Data_Sections.md).

- Neue automatische Variablen, `$PSCulture` und `$PSUICulture` . `$PSCulture` speichert den Namen der auf dem System verwendeten Benutzeroberflächen Sprache für Elemente wie Datum, Uhrzeit und Währung. Die- `$PSUICulture` Variable speichert den Namen der auf dem System verwendeten UI-Sprache für Benutzeroberflächen Elemente wie Menüs und Text Zeichenfolgen.

- Ein Cmdlet, `ConvertFrom-StringData` , das Text Zeichenfolgen in Wörterbuch ähnliche Hash Tabellen konvertiert, um die Übersetzung zu vereinfachen. Weitere Informationen finden Sie unter [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData).

- Ein neuer Dateityp, `.psd1` , der übersetzte Text Zeichenfolgen speichert. Die `.psd1` Dateien werden in sprachspezifischen Unterverzeichnissen des Skript Verzeichnisses gespeichert.

- Ein Cmdlet, `Import-LocalizedData` , das übersetzte Text Zeichenfolgen für eine angegebene Sprache zur Laufzeit in ein Skript importiert. Dieses Cmdlet erkennt und importiert Zeichen folgen in jeder von Windows unterstützten Sprache. Weitere Informationen finden Sie unter [Import-localizeddata](xref:Microsoft.PowerShell.Utility.Import-LocalizedData).

### <a name="the-data-section-storing-default-strings"></a>Der Abschnitt "Data": Speichern von Standard Zeichenfolgen

Verwenden Sie einen Daten Abschnitt im Skript, um die Text Zeichenfolgen in der Standardsprache zu speichern. Ordnen Sie die Zeichen folgen in Schlüssel-Wert-Paaren in einer here-Zeichenfolge an. Jedes Schlüssel-Wert-Paar muss sich in einer separaten Zeile befinden. Wenn Sie Kommentare einschließen, müssen sich die Kommentare in separaten Zeilen befinden.

Das `ConvertFrom-StringData` -Cmdlet konvertiert die Schlüssel-Wert-Paare in der here-Zeichenfolge in eine Wörterbuch ähnliche Hash Tabelle, die im Wert der Daten Abschnitts Variablen gespeichert wird.

Im folgenden Beispiel enthält der Daten Abschnitt des `World.ps1` Skripts den English-United States (en-US) Satz von Eingabe Aufforderungs Meldungen für ein Skript. Das `ConvertFrom-StringData` Cmdlet konvertiert die Zeichen folgen in eine Hash Tabelle und speichert Sie in der `$msgtable` Variablen.

```powershell
$msgTable = Data {
    #culture="en-US"
    ConvertFrom-StringData @'
    helloWorld = Hello, World.
    errorMsg1 = You cannot leave the user name field blank.
    promptMsg = Please enter your user name.
'@
}
```

Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](about_Quoting_Rules.md).

### <a name="psd1-files-storing-translated-strings"></a>PSD1 Files: übersetzte Zeichen folgen speichern

Speichern Sie die Skript Nachrichten für jede Benutzeroberflächen Sprache in separaten Textdateien mit demselben Namen wie das Skript und die `.psd1` Dateinamenerweiterung. Speichern Sie die Dateien in den Unterverzeichnissen des Skript Verzeichnisses mit den Namen der Kulturen im folgenden Format:

`<language>-<region>`

Beispiele: de-de, AR-SA und zh-Hans

Wenn das Skript beispielsweise `World.ps1` im Verzeichnis gespeichert wird `C:\Scripts` , erstellen Sie eine Datei Verzeichnisstruktur, die der folgenden ähnelt:

```
C:\Scripts
C:\Scripts\World.ps1
C:\Scripts\de-DE\World.psd1
C:\Scripts\ar-SA\World.psd1
C:\Scripts\zh-CN\World.psd1
...
```

Die `World.psd1` Datei im Unterverzeichnis "de-de" des Skript Verzeichnisses kann folgende Anweisung enthalten:

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = Hallo, Welt.
errorMsg1 = Das Feld Benutzername darf nicht leer sein.
promptMsg = Geben Sie Ihren Benutzernamen ein.
'@
```

Ebenso kann die `World.psd1` Datei im Unterverzeichnis "ar-SA" des Skript Verzeichnisses folgende Anweisung enthalten:

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = مرحبًا أيها العالَم
errorMsg1 = لا يمكنك ترك حقل اسم المستخدم فارغًا
promptMsg = يرجى إدخال اسم المستخدم الخاص بك
'@
```

### <a name="import-localizeddata-dynamic-retrieval-of-translated-strings"></a>Import-localizeddata: Dynamisches Abrufen von übersetzten Zeichen folgen

Verwenden Sie das-Cmdlet, um die Zeichen folgen in der Benutzeroberflächen Sprache des aktuellen Benutzers abzurufen `Import-LocalizedData` .

`Import-LocalizedData` sucht den Wert der `$PSUICulture` automatischen Variablen und importiert den Inhalt der `<script-name>.psd1` Dateien im Unterverzeichnis, das mit dem Wert übereinstimmt `$PSUICulture` . Anschließend wird der importierte Inhalt in der Variablen gespeichert, die durch den Wert des **bindingvariable** -Parameters angegeben wird.

```powershell
Import-LocalizedData -BindingVariable msgTable
```

Wenn der Befehl z. b. `Import-LocalizedData` im `C:\Scripts\World.ps1` Skript angezeigt wird und der Wert von `$PSUICulture` "ar-SA" ist, sucht `Import-LocalizedData` die folgende Datei:

`C:\Scripts\ar-SA\World.psd1`

Anschließend werden die arabischen Text Zeichenfolgen aus der Datei in die-Variable importiert, wobei alle Standard Zeichenfolgen `$msgTable` ersetzt werden, die möglicherweise im Data-Abschnitt des `World.ps1` Skripts definiert werden.

Wenn das Skript die `$msgTable` Variable zum Anzeigen von Benutzer Nachrichten verwendet, werden die Nachrichten daher auf Arabisch angezeigt.

Das folgende Skript zeigt z. b. die Meldung "Bitte geben Sie Ihren Benutzernamen ein" in Arabisch an:

```powershell
if (!($username)) { $msgTable.promptMsg }
```

Wenn keine `Import-LocalizedData` Datei finden kann, die `.psd1` mit dem Wert von übereinstimmt `$PSUIculture` , wird der Wert von `$msgTable` nicht ersetzt, und der-Befehl `$msgTable.promptMsg` zeigt die Fall Back-Zeichen folgen (en-US) an.

## <a name="examples"></a>Beispiele

Dieses Beispiel zeigt, wie die Skript Internationalisierungs Funktionen in einem Skript verwendet werden, um Benutzern in der Sprache, die auf dem Computer festgelegt ist, einen Wochentag anzuzeigen.

Im folgenden finden Sie eine komplette Liste der Sample1.ps1 Skriptdatei.

Das Skript beginnt mit einem Daten Abschnitt namens Day ($Day), der einen `ConvertFrom-StringData` Befehl enthält. Der an gesendete Ausdruck `ConvertFrom-StringData` ist eine here-Zeichenfolge, die die Namen der Tags in der Standard Kultur der Benutzeroberfläche, en-US, in Schlüssel/Wert-Paaren enthält. Mit dem- `ConvertFrom-StringData` Cmdlet werden die Schlüssel-Wert-Paare in der here-Zeichenfolge in eine Hash Tabelle konvertiert und dann im Wert der `$Day` Variablen gespeichert.

Der `Import-LocalizedData` Befehl importiert den Inhalt der `.psd1` Datei in das Verzeichnis, das mit dem Wert der `$PSUICulture` automatischen Variablen übereinstimmt, und speichert ihn dann in der `$Day` Variablen und ersetzt die Werte von, die `$Day` im Daten Abschnitt definiert sind.

Mit den verbleibenden Befehlen werden die Zeichen folgen in ein Array geladen und angezeigt.

```powershell
$Day = Data {
#culture="en-US"
ConvertFrom-StringData -StringData @'
    messageDate = Today is
    d0 = Sunday
    d1 = Monday
    d2 = Tuesday
    d3 = Wednesday
    d4 = Thursday
    d5 = Friday
    d6 = Saturday
'@
}

Import-LocalizedData -BindingVariable Day

#Build an array of weekdays.
$a = $Day.d0, $Day.d1, $Day.d2, $Day.d3, $Day.d4, $Day.d5, $Day.d6

# Get the day of the week as a number (Monday = 1).
# Index into $a to get the name of the day.
# Use string formatting to build a sentence.

"{0} {1}" -f $Day.messageDate, $a[(Get-Date -UFormat %u)] | Out-Host
```

Die `.psd1` Dateien, von denen das Skript unterstützt wird, werden in Unterverzeichnissen des Skript Verzeichnisses gespeichert, dessen Namen den `$PSUICulture` Werten entsprechen.

Im folgenden finden Sie eine komplette Liste von `.\de-DE\sample1.psd1` :

```powershell
# culture="de-DE"
ConvertFrom-StringData @'
    messageDate = Heute ist
    d0 = Sonntag
    d1 = Montag
    d2 = Dienstag
    d3 = Mittwoch
    d4 = Donnerstag
    d5 = Freitag
    d6 = Samstag
'@
```

Wenn Sie Sample.ps1 auf einem System ausführen, auf dem der Wert von `$PSUICulture` de-de ist, lautet die Ausgabe des Skripts folglich wie folgt:

```Output
Heute ist Freitag
```

## <a name="see-also"></a>Weitere Informationen:

- [about_Data_Sections](about_Data_Sections.md)
- [about_Automatic_Variables](about_Automatic_Variables.md)
- [about_Hash_Tables](about_Hash_Tables.md)
- [about_Quoting_Rules](about_Quoting_Rules.md)
- [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
- [Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)
