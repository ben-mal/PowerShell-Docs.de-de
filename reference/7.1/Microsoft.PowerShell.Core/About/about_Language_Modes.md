---
description: Erläutert die sprach Modi und ihre Auswirkung auf PowerShell-Sitzungen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: 0b94125574bc65359b264225bb6c64231c1052d7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220439"
---
# <a name="about-language-modes"></a>Informationen zu sprach Modi

## <a name="short-description"></a>KURZE BESCHREIBUNG
Erläutert die sprach Modi und ihre Auswirkung auf PowerShell-Sitzungen.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Der Sprachmodus einer PowerShell-Sitzung bestimmt teilweise, welche Elemente der PowerShell-Sprache in der Sitzung verwendet werden können.

PowerShell unterstützt die folgenden sprach Modi:

- FullLanguage
- Einschräninedlanguage (eingeführt in PowerShell 3,0)
- Restrictedlanguage
- NoLanguage

### <a name="what-is-a-language-mode"></a>Was ist ein Sprachmodus?

Der Sprachmodus bestimmt die Sprachelemente, die in der Sitzung zulässig sind.

Der Sprachmodus ist tatsächlich eine Eigenschaft der Sitzungs Konfiguration (oder des "Endpunkts"), die verwendet wird, um die Sitzung zu erstellen. Alle Sitzungen, die eine bestimmte Sitzungs Konfiguration verwenden, haben den Sprachmodus der Sitzungs Konfiguration.

Alle PowerShell-Sitzungen verfügen über einen Sprachmodus, einschließlich pssessions, die Sie mithilfe des `New-PSSession` Cmdlets erstellen, temporäre Sitzungen mit dem Computername-Parameter und die Standard Sitzungen, die beim Starten von PowerShell angezeigt werden.

Remote Sitzungen werden mithilfe der Sitzungs Konfigurationen auf dem Remote Computer erstellt. Der Sprachmodus, der in der Sitzungs Konfiguration festgelegt ist, bestimmt den Sprachmodus der Sitzung. Um die Sitzungs Konfiguration einer PSSession anzugeben, verwenden Sie den ConfigurationName-Parameter von Cmdlets, die eine Sitzung erstellen.

### <a name="language-modes"></a>sprach Modi

In diesem Abschnitt werden die sprach Modi in PowerShell-Sitzungen beschrieben.

#### <a name="full-language-fulllanguage"></a>Vollständige Sprache (vollständig)

Im voll Sprachmodus sind alle Sprachelemente in der Sitzung zulässig.
Fulllanguage ist der Standard Sprachmodus für Standard Sitzungen in allen Windows-Versionen mit Ausnahme von Windows RT.

#### <a name="restricted-language-restrictedlanguage"></a>Eingeschränkte Sprache (restrictedlanguage)

Im restrictedlanguage-Modus können Benutzer Befehle (Cmdlets, Funktionen, CIM-Befehle und Workflows) ausführen, aber Sie dürfen keine Skriptblöcke verwenden.

Standardmäßig sind nur die folgenden Variablen im restrictedlanguage-Modus zulässig:

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

Modul Manifeste, die den restrictedlanguage-Modus verwenden, lassen die folgenden zusätzlichen Variablen ebenfalls zu:

- `$PSScriptRoot`
- `$PSEdition` (in PowerShell Core)
- `$EnabledExperimentalFeatures` (in PowerShell Core)

Nur die folgenden Vergleichs Operatoren sind zulässig:

- `-eq` hoch
- `-gt` (größer als)
- `-lt` (kleiner als)

Zuweisungsanweisungen, Eigenschaftsverweise und Methodenaufrufe sind nicht zulässig.

#### <a name="no-language-nolanguage"></a>Keine Sprache (nolanguage)

Der nolanguage-Modus kann nur über die API verwendet werden. Der nolanguage-Modus bedeutet, dass kein Skript Text eines beliebigen Formulars zulässig ist. Dies verhindert die Verwendung der **addScript ()** -Methode, die Fragmente von PowerShell-Skripts sendet, die analysiert und ausgeführt werden. Sie können nur **AddCommand ()** und **AddParameter ()** verwenden, die den Parser nicht durchlaufen.

#### <a name="constrained-language-constrained-language"></a>Eingeschränkte Sprache (eingeschränkte Sprache)

Der Modus "einschräninedlanguage" erlaubt alle Cmdlets und alle PowerShell-Sprachelemente, schränkt jedoch zulässige Typen ein.

Der Modus "einschränder Modus" ist für die Unterstützung der Code Integrität (User Mode Code Integrity, Umschlag Code) in Windows RT konzipiert. Dabei handelt es sich um den einzigen unterstützten Sprachmodus unter Windows RT, der jedoch auf allen unterstützten Systemen verfügbar ist.

Durch die über CI werden Arm-Geräte geschützt, da nur Microsoft-signierte und Microsoft-zertifizierte apps auf Windows RT-basierten Geräten installiert werden können.
Der Modus "einschränken" verhindert, dass Benutzer PowerShell verwenden, um umci zu umgehen oder zu verletzen.

Die Features des einschräninedlanguage-Modus lauten wie folgt:

- Alle Cmdlets in Windows-Modulen und andere umci-genehmigte Cmdlets sind voll funktionsfähig und verfügen über vollständigen Zugriff auf Systemressourcen, außer wie bereits erwähnt.

- Alle Elemente der PowerShell-Skriptsprache sind zulässig.

- Alle in Windows enthaltenen Module können importiert werden, und alle Befehle, die vom Modul exportiert werden, werden in der Sitzung ausgeführt.

- Im PowerShell-Workflow können Sie Skript Workflows (in der PowerShell-Sprache geschriebene Workflows) schreiben und ausführen. XAML-basierte Workflows werden nicht unterstützt, und Sie können XAML nicht in einem Skript Workflow ausführen, z `Invoke-Expression -Language XAML` . b. mithilfe von. Workflows können auch keine anderen Workflows aufzurufen, obwohl es zulässig ist.

- Das `Add-Type` Cmdlet kann signierte Assemblys laden, aber keinen beliebigen c#-Code oder Win32-APIs laden.

- Das- `New-Object` Cmdlet kann nur für zulässige Typen verwendet werden (siehe unten).

- Nur zulässige Typen (unten aufgeführt) können in PowerShell verwendet werden. Andere Typen sind nicht zulässig.

- Typkonvertierung ist zulässig, jedoch nur, wenn das Ergebnis ein zulässiger Typ ist.

- Cmdlet-Parameter, die Zeichen folgen Eingaben in Typen konvertieren, funktionieren nur, wenn der resultierende Typ ein zulässiger Typ ist.

- Die **ToString ()** -Methode und die .NET-Methoden zulässiger Typen (siehe unten) können aufgerufen werden. Andere Methoden können nicht aufgerufen werden.

- Benutzer können alle Eigenschaften zulässiger Typen erhalten. Benutzer können die Werte von Eigenschaften nur für die Kerntypen festlegen. Nur die folgenden COM-Objekte sind zulässig:

  - **Scripting. Dictionary**
  - **Scripting.FileSystemObject**
  - **VBScript. RegExp**

Die folgenden Typen sind im Modus "eingeschränkt" zulässig. Benutzer können Eigenschaften erhalten, Methoden aufrufen und Objekte in diese Typen konvertieren.

Zulässige Typen:

- Aliasattribute
- ' Zubei ' zuder Zuordnung
- ' Zubei ' zuder Zuweisung
- Allownullattribute
- Array
- Bool
- byte
- char
- Cmdletbindingattribute
- DateTime
- decimal
- DirectoryEntry
- DirectorySearcher
- double
- float
- Guid
- Hashtable
- INT
- Int16
- long
- ManagementClass
- ManagementObject
- ManagementObjectSearcher
- NULL-Zeichenfolge
- Outputtypeer Attribute
- Parameter Attribute
- PSCredential
- Psdefaultvalueattribute
- Pslistmodifier
- PSObject
- Psprientschärvedictionary
- Psreference
- Pstypameattribute
- RegEx
- SByte
- string
- Supportswildcardsattribute
- SwitchParameter
- System. Globalization. CultureInfo
- System .net. IPAddress
- System .net. Mail. MailAddress
- System. Numerics. BigInteger
- System.Security.SecureString
- TimeSpan
- UInt16
- UInt32
- UInt64

### <a name="finding-the-language-mode-of-a-session-configuration"></a>Suchen des Sprachmodus einer Sitzungs Konfiguration

Wenn eine Sitzungs Konfiguration mithilfe einer Sitzungs Konfigurationsdatei erstellt wird, verfügt die Sitzungs Konfiguration über eine languagemode-Eigenschaft. Sie können den Sprachmodus suchen, indem Sie den Wert der languagemode-Eigenschaft abrufen.

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

Bei anderen Sitzungs Konfigurationen können Sie den Sprachmodus indirekt ermitteln, indem Sie den Sprachmodus einer Sitzung ermitteln, die mit der Sitzungs Konfiguration erstellt wird.

### <a name="finding-the-language-mode-of-a-session"></a>Suchen des Sprachmodus einer Sitzung

Sie können den Sprachmodus einer vollständigen Sprache oder einschräninedlanguage-Sitzung ermitteln, indem Sie den Wert der languagemode-Eigenschaft des Sitzungs Zustands abrufen.

Beispiel:

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

In Sitzungen mit den Modi restrictedlanguage und nolanguage können Sie die Punkt-Methode jedoch nicht verwenden, um Eigenschaftswerte zu erhalten. Stattdessen wird in der Fehlermeldung der Sprachmodus angezeigt.

Wenn Sie den `$ExecutionContext.SessionState.LanguageMode` Befehl in einer restrictedlanguage-Sitzung ausführen, gibt PowerShell die Fehlermeldungen propertyreferencenotsupportedindatasection und variablereferencenotsupportedindatasection zurück.

- Propertyreferencenotsupportedindatasection: Eigenschafts Verweise sind im eingeschränkten Sprachmodus oder in einem Daten Abschnitt nicht zulässig.
- Variablereferencenotsupportedindatasection eine Variable, auf die im eingeschränkten Sprachmodus nicht verwiesen werden kann, oder auf einen Daten Abschnitt wird verwiesen.

Wenn Sie den `$ExecutionContext.SessionState.LanguageMode` Befehl in einer nolanguage-Sitzung ausführen, gibt PowerShell die scripznotallowed-Fehlermeldung zurück.

- Scripznotallowed: die Syntax wird von diesem Runspace nicht unterstützt. Dies liegt möglicherweise daran, dass es sich um einen nicht Sprachmodus handelt.

## <a name="keywords"></a>Keywords

- about_ConstrainedLanguage
- about_FullLanguage
- about_NoLanguage
- about_RestrictedLanguage

## <a name="see-also"></a>SIEHE AUCH

- [about_Session_Configuration_Files](about_Session_Configuration_Files.md)
- [about_Session_Configurations](about_Session_Configurations.md)

