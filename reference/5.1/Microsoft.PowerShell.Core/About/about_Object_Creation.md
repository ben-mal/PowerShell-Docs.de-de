---
description: Erläutert das Erstellen von-Objekten in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_object_creation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Object_Creation
ms.openlocfilehash: 8903af794c83e4c84709e3eeb21489557458e988
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223428"
---
# <a name="about-object-creation"></a>Informationen zur Objekt Erstellung

## <a name="short-description"></a>Kurze Beschreibung

Erläutert das Erstellen von-Objekten in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

Sie können-Objekte in PowerShell erstellen und die Objekte verwenden, die Sie in Befehlen und Skripts erstellen.

Es gibt viele Möglichkeiten, Objekte zu erstellen. diese Liste ist nicht definitiv:

- [New-Object](xref:Microsoft.PowerShell.Utility.New-Object): erstellt eine Instanz eines .NET Framework Objekts oder eines COM-Objekts.
- [Import-CSV](xref:Microsoft.PowerShell.Utility.Import-Csv) /
   [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): erstellt benutzerdefinierte Objekte ( **pscustomobject** ) aus den Elementen, die als durch Trennzeichen getrennte Werte definiert sind.
- [ConvertFrom-JSON](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): erstellt benutzerdefinierte Objekte, die in JavaScript Object Notation (JSON) definiert sind.
- [ConvertFrom-String](xref:Microsoft.PowerShell.Utility.ConvertFrom-String): basiert auf " [Flash Extract](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples)" und `ConvertFrom-String` erstellt benutzerdefinierte Objekte aus strukturierten Zeichen folgen Daten.
  In diesem Thema werden die einzelnen Methoden erläutert und erläutert.
- [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): erstellt benutzerdefinierte Objekte, die als Schlüssel-Wert-Paare definiert sind.
- [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type): ermöglicht Ihnen das Definieren einer Klasse in der PowerShell-Sitzung, die Sie mit instanziieren können `New-Object` .
- [New-Module](xref:Microsoft.PowerShell.Core.New-Module): der **ascustomobject** -Parameter erstellt ein benutzerdefiniertes Objekt, das Sie mit dem Skriptblock definieren.
- [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member): fügt vorhandenen Objekten Eigenschaften hinzu. Sie können verwenden, `Add-Member` um ein benutzerdefiniertes Objekt aus einem einfachen Typ zu erstellen, wie z `[System.Int32]` . b..
- [Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): wählt Eigenschaften für ein Objekt aus. Sie können verwenden `Select-Object` , um benutzerdefinierte und berechnete Eigenschaften für ein bereits instanziertes Objekt zu erstellen.

Die folgenden zusätzlichen Methoden werden in diesem Artikel behandelt:

- Durch Aufrufen des Konstruktors eines Typs mit einer statischen `new()` Methode
- Durch Typecasting von Hash Tabellen mit Eigenschaftsnamen und Eigenschafts Werten

## <a name="static-new-method"></a>Static New ()-Methode

Alle .NET-Typen verfügen über eine- `new()` Methode, die es Ihnen ermöglicht,-Instanzen einfacher zu erstellen. Sie können auch alle verfügbaren Konstruktoren für einen bestimmten Typ anzeigen.

Geben Sie den `new` Methodennamen nach dem Typnamen an, und drücken Sie, um die Konstruktoren für einen Typ anzuzeigen `<ENTER>` .

```powershell
[System.Uri]::new
```

```Output
OverloadDefinitions
-------------------
uri new(string uriString)
uri new(string uriString, bool dontEscape)
uri new(uri baseUri, string relativeUri, bool dontEscape)
uri new(string uriString, System.UriKind uriKind)
uri new(uri baseUri, string relativeUri)
uri new(uri baseUri, uri relativeUri)
```

Nun können Sie einen **System. Uri** erstellen, indem Sie den entsprechenden Konstruktor angeben.

```powershell
[System.Uri]::new("https://www.bing.com")
```

```Output
AbsolutePath   : /
AbsoluteUri    : https://www.bing.com/
LocalPath      : /
Authority      : www.bing.com
...
```

Sie können das folgende Beispiel verwenden, um zu bestimmen, welche .NET-Typen derzeit für die instanziieren geladen werden.

```powershell
[AppDomain]::CurrentDomain.GetAssemblies() |
  ForEach-Object {
    $_.GetExportedTypes() |
      ForEach-Object { $_.FullName }
  }
```

Objekte, die mit der-Methode erstellt wurden `new()` , haben möglicherweise nicht dieselben Eigenschaften wie Objekte desselben Typs, die von PowerShell-Cmdlets erstellt werden. PowerShell-Cmdlets,-Anbieter und das erweiterte Typsystem können der-Instanz zusätzliche Eigenschaften hinzufügen.

Beispielsweise fügt der File System-Anbieter in PowerShell sechs **NoteProperty** -Werte zum **DirectoryInfo** -Objekt hinzu, das von zurückgegeben wird `Get-Item` .

```powershell
$PSDirInfo = Get-Item /
$PSDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    6 NoteProperty
    1 ScriptProperty
   18 Method
```

Wenn Sie ein **DirectoryInfo** -Objekt direkt erstellen, verfügt es nicht über diese sechs **NoteProperty** -Werte.

```powershell
$NewDirInfo = [System.IO.DirectoryInfo]::new('/')
$NewDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    1 ScriptProperty
   18 Method
```

Weitere Informationen zum erweiterten Typsystem finden Sie unter [about_Types.ps1XML](about_Types.ps1xml.md).

Diese Funktion wurde in PowerShell 5,0 hinzugefügt.

## <a name="create-objects-from-hash-tables"></a>Erstellen von Objekten aus Hash Tabellen

Sie können ein Objekt aus einer Hash Tabelle mit Eigenschaften und Eigenschafts Werten erstellen.

Die Syntax ist wie folgt:

```
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

Diese Methode funktioniert nur für Klassen, die über einen Parameter losen Konstruktor verfügen. Die Objekteigenschaften müssen öffentlich und feststellbar sein.

Diese Funktion wurde in PowerShell-Version 3,0 hinzugefügt.

## <a name="create-custom-objects-from-hash-tables"></a>Erstellen von benutzerdefinierten Objekten aus Hash Tabellen

Benutzerdefinierte Objekte sind sehr nützlich und können problemlos mithilfe der Hash Tabellen Methode erstellt werden. Die **pscustomobject** -Klasse ist speziell für diesen Zweck konzipiert.

Benutzerdefinierte Objekte sind eine hervorragende Möglichkeit, eine angepasste Ausgabe einer Funktion oder eines Skripts zurückzugeben. Dies ist nützlicher als das Zurückgeben von formatierter Ausgabe, die nicht neu formatiert oder an andere Befehle weitergeleitet werden kann.

Die Befehle im `Test-Object function` legen einige Variablen Werte fest und verwenden diese Werte dann, um ein benutzerdefiniertes Objekt zu erstellen. Dieses Objekt wird im Beispiel Abschnitt des `Update-Help` Cmdlet-Hilfe Themas verwendet.

```powershell
function Test-Object {
  $ModuleName = "PSScheduledJob"
  $HelpCulture = "en-us"
  $HelpVersion = "3.1.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
  $ModuleName = "PSWorkflow"
  $HelpCulture = "en-us"
  $HelpVersion = "3.0.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
}
Test-Object
```

Die Ausgabe dieser Funktion ist eine Auflistung benutzerdefinierter Objekte, die standardmäßig als Tabelle formatiert sind.

```Output
ModuleName        UICulture      Version
---------         ---------      -------
PSScheduledJob    en-us          3.1.0.0
PSWorkflow        en-us          3.0.0.0
```

Benutzer können die Eigenschaften der benutzerdefinierten Objekte genau wie bei Standardobjekten verwalten.

```powershell
(Test-Object).ModuleName
```

```Output
 PSScheduledJob
 PSWorkflow
```

## <a name="create-non-custom-objects-from-hash-tables"></a>Erstellen von Nichtbenutzer definierten Objekten aus Hash Tabellen

Sie können auch Hash Tabellen verwenden, um-Objekte für Nichtbenutzer definierte Klassen zu erstellen. Wenn Sie ein Objekt für eine Nichtbenutzer definierte Klasse erstellen, ist der mit einem Namespace qualifizierte Typname erforderlich, obwohl Sie möglicherweise eine anfängliche **System** -Namespace Komponente weglassen.

Der folgende Befehl erstellt z. b. ein Sitzungs Options Objekt.

```powershell
[System.Management.Automation.Remoting.PSSessionOption]@{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
```

Die Anforderungen des Hash Tabellen-Features, insbesondere die Parameter losen konstruktoranforderungen, eliminieren viele vorhandene Klassen. Die meisten PowerShell- _options_ Klassen sind jedoch für die Verwendung dieser Funktion sowie für andere sehr nützliche Klassen, wie z. b. die **ProcessStartInfo** -Klasse, konzipiert.

```powershell
[System.Diagnostics.ProcessStartInfo]@{
  CreateNoWindow="$true"
  Verb="run as"
}
```

```Output
Arguments               :
ArgumentList            : {}
CreateNoWindow          : True
EnvironmentVariables    : {OneDriveConsumer, PROCESSOR_ARCHITECTURE,
                           CommonProgramFiles(x86), APPDATA...}
Environment             : {[OneDriveConsumer, C:\Users\user1\OneDrive],
                           [PROCESSOR_ARCHITECTURE, AMD64],
                           [CommonProgramFiles(x86),
                           C:\Program Files (x86)\Common Files],
                           [APPDATA, C:\Users\user1\AppData\Roaming]...}
RedirectStandardInput   : False
RedirectStandardOutput  : False
RedirectStandardError   : False
...
```

Sie können auch die Hash Tabellen Funktion verwenden, wenn Sie Parameterwerte festlegen. Beispielsweise der Wert des **sessionoption** -Parameters von `New-PSSession` .
-Cmdlet kann eine Hash Tabelle sein.

```powershell
New-PSSession -ComputerName Server01 -SessionOption @{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
Register-ScheduledJob Name Test -FilePath .\Get-Inventory.ps1 -Trigger @{
  Frequency="Daily"
  At="15:00"
}
```

## <a name="generic-objects"></a>Generische Objekte

Sie können auch generische Objekte in PowerShell erstellen. Generics sind Klassen, Strukturen, Schnittstellen und Methoden, die über Platzhalter (Typparameter) für einen oder mehrere der Typen verfügen, die sie speichern oder verwenden.

Im folgenden Beispiel wird ein **Dictionary** -Objekt erstellt.

```powershell
$dict = New-Object 'System.Collections.Generic.Dictionary[String,Int]'
$dict.Add("One", 1)
$dict
```

```Output
Key Value
--- -----
One     1
```

Weitere Informationen zu Generika finden Sie unter [Generika in .net](/dotnet/standard/generics).

## <a name="see-also"></a>Weitere Informationen:

[about_Objects](about_Objects.md)

[about_Methods](about_Methods.md)

[about_Properties](about_Properties.md)

[about_Pipelines](about_Pipelines.md)

[about_Types.ps1xml](about_Types.ps1xml.md)
