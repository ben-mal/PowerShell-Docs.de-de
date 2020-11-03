---
description: Erläutert Datenabschnitte, die Text Zeichenfolgen und andere schreibgeschützte Daten aus Skript Logik isolieren.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_data_sections?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Data_Sections
ms.openlocfilehash: 8532804c59ebcb7dd8f98eac7dc9e0865b21f2b3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220700"
---
# <a name="about-data-sections"></a>Informationen zu Daten Abschnitten

## <a name="short-description"></a>Kurze Beschreibung
Erläutert Datenabschnitte, die Text Zeichenfolgen und andere schreibgeschützte Daten aus Skript Logik isolieren.

## <a name="long-description"></a>Lange Beschreibung

Skripts, die für PowerShell entwickelt wurden, können über einen oder mehrere Datenabschnitte verfügen, die nur Daten enthalten. Sie können einen oder mehrere Datenabschnitte in beliebige Skripts, Funktionen oder erweiterte Funktionen einschließen. Der Inhalt des Abschnitts Daten ist auf eine bestimmte Teilmenge der PowerShell-Skriptsprache beschränkt.

Durch das Aufteilen von Daten aus Code Logik wird die Identifizierung und Verwaltung von Logik und Daten vereinfacht. Sie können separate Zeichen folgen-Ressourcen Dateien für Text wie z. b. Fehlermeldungen und Hilfe Zeichenfolgen haben. Außerdem wird die Codelogik isoliert, die Sicherheits-und Validierungstests erleichtert.

In PowerShell wird der Abschnitt "Data" verwendet, um die Skript Internationalisierung zu unterstützen.
Mithilfe von Daten Abschnitten können Sie Zeichen folgen, die in viele Benutzeroberflächen Sprachen (UI) übersetzt werden, einfacher isolieren, Auffinden und verarbeiten.

Der Abschnitt "Data" ist eine PowerShell-Funktion 2,0. Skripts mit Daten Abschnitten können nicht in PowerShell 1,0 ohne Revision ausgeführt werden.

### <a name="syntax"></a>Syntax

Die Syntax für einen Daten Abschnitt lautet wie folgt:

```
DATA [<variable-name>] [-supportedCommand <cmdlet-name>] {
    <Permitted content>
}
```

Das Schlüsselwort "Data" ist erforderlich. Es wird nicht zwischen Groß- und Kleinschreibung unterschieden. Der zulässige Inhalt ist auf die folgenden Elemente beschränkt:

- Alle PowerShell-Operatoren, außer `-match`
- `If``Else`-,-und- `ElseIf` Anweisungen
- Die folgenden automatischen Variablen: `$PsCulture` , `$PsUICulture` , `$True` , `$False` und. `$Null`
- Kommentare
- Pipelines
- Durch Semikolons getrennte Anweisungen ( `;` )
- Literale, wie z. b. die folgenden:

  ```powershell
  a
  1
  1,2,3
  "PowerShell 2.0"
  @( "red", "green", "blue" )
  @{ a = 0x1; b = "great"; c ="script" }
  [XML] @'
  <p> Hello, World </p>
  '@
  ```

- Cmdlets, die in einem Daten Abschnitt zulässig sind. Standardmäßig ist nur das `ConvertFrom-StringData` Cmdlet zulässig.
- -Cmdlets, die Sie in einem Daten Abschnitt mithilfe des- `-SupportedCommand` Parameters zulassen.

Wenn Sie das `ConvertFrom-StringData` Cmdlet in einem Daten Abschnitt verwenden, können Sie die Schlüssel-Wert-Paare in Zeichen folgen in einfachen Anführungszeichen oder in Zeichen folgen mit nur einem oder zwei Anführungszeichen einschließen. Zeichen folgen, die Variablen und Teil Ausdrücke enthalten, müssen jedoch in Zeichen folgen in einfachen Anführungszeichen oder in einfachen Zeichen folgen eingeschlossen werden, damit die Variablen nicht erweitert werden und die Teil Ausdrücke nicht ausführbar sind.

### <a name="-supportedcommand"></a>-Supportedcommand

Mit dem- `-SupportedCommand` Parameter können Sie angeben, dass ein Cmdlet oder eine Funktion nur Daten generiert. Es ist so konzipiert, dass Benutzer Cmdlets und Funktionen in einen Daten Abschnitt einschließen können, den Sie geschrieben oder getestet haben.

Der Wert von `-SupportedCommand` ist eine durch Trennzeichen getrennte Liste mit einem oder mehreren Cmdlet-oder Funktionsnamen.

Der folgende Daten Abschnitt enthält z. b. ein vom Benutzer geschriebenes Cmdlet, `Format-XML` , das Daten in einer XML-Datei formatiert:

```powershell
DATA -supportedCommand Format-Xml
{
    Format-Xml -Strings string1, string2, string3
}
```

### <a name="using-a-data-section"></a>Verwenden eines Daten Abschnitts

Um den Inhalt eines Daten Abschnitts zu verwenden, weisen Sie ihn einer Variablen zu, und verwenden Sie Variablen Notation, um auf den Inhalt zuzugreifen.

Beispielsweise enthält der folgende Daten Abschnitt einen `ConvertFrom-StringData` Befehl, der die here-Zeichenfolge in eine Hash Tabelle konvertiert. Die Hash Tabelle wird der Variablen zugewiesen `$TextMsgs` .

Die `$TextMsgs` Variable ist nicht Teil des Daten Abschnitts.

```powershell
$TextMsgs = DATA {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

Verwenden Sie die folgenden Befehle, um auf die Schlüssel und Werte in der Hash Tabelle in zuzugreifen `$TextMsgs` .

```powershell
$TextMsgs.Text001
$TextMsgs.Text002
```

Alternativ können Sie den Variablennamen in der Definition des Daten Abschnitts ablegen. Beispiel:

```powershell
DATA TextMsgs {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}

$TextMsgs
```

Das Ergebnis ist das gleiche wie das vorherige Beispiel.

```Output
Name                           Value
----                           -----
Text001                        Windows 7
Text002                        Windows Server 2008 R2
```

### <a name="examples"></a>Beispiele

Einfache Daten Zeichenfolgen.

```powershell
DATA {
    "Thank you for using my PowerShell Organize.pst script."
    "It is provided free of charge to the community."
    "I appreciate your comments and feedback."
}
```

Zeichen folgen, die zugelassene Variablen enthalten.

```powershell
DATA {
    if ($null) {
        "To get help for this cmdlet, type get-help new-dictionary."
    }
}
```

Eine here-Zeichenfolge in einfachen Anführungszeichen, die das `ConvertFrom-StringData` Cmdlet verwendet:

```powershell
DATA {
    ConvertFrom-StringData -stringdata @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

Eine here-Zeichenfolge mit doppelten Anführungszeichen, die das `ConvertFrom-StringData` Cmdlet verwendet:

```powershell
DATA  {
    ConvertFrom-StringData -stringdata @"
Msg1 = To start, press any key.
Msg2 = To exit, type "quit".
"@
}
```

Ein Daten Abschnitt, der ein vom Benutzer geschriebenes Cmdlet enthält, das Daten generiert:

```powershell
DATA -supportedCommand Format-XML {
    Format-Xml -strings string1, string2, string3
}
```

## <a name="see-also"></a>Weitere Informationen

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_If](about_If.md)

[about_Operators](about_Operators.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_Script_Internationalization](about_Script_Internationalization.md)

[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)
