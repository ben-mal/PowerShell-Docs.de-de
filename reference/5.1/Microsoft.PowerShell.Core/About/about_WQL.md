---
description: Beschreibt die WMI-Abfragesprache (WQL), die zum Abrufen von WMI-Objekten in Windows PowerShell verwendet werden kann.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wql?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WQL
ms.openlocfilehash: c6fd523864d419fb400b7041e92ec8f0733724b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223188"
---
# <a name="about-wql"></a>Informationen zu WQL

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt die WMI-Abfragesprache (WQL), die zum Abrufen von WMI-Objekten in Windows PowerShell verwendet werden kann.

## <a name="long-description"></a>LANGE BESCHREIBUNG

WQL ist die WMI-Abfragesprache (Windows-Verwaltungsinstrumentation), die zum erhalten von Informationen aus WMI verwendet wird.

Es ist nicht erforderlich, WQL zum Ausführen einer WMI-Abfrage in Windows PowerShell zu verwenden.
Stattdessen können Sie die Parameter der Get-WmiObject oder Get-CimInstance-Cmdlets verwenden. WQL-Abfragen sind etwas schneller als Standard Get-WmiObject Befehle, und die verbesserte Leistung ist offensichtlich, wenn die Befehle auf Hunderten von Systemen ausgeführt werden. Achten Sie jedoch darauf, dass die Zeit, die Sie für das Schreiben einer erfolgreichen WQL-Abfrage aufwenden, die Leistungsverbesserung nicht aufwiegen.

Die grundlegenden WQL-Anweisungen, die Sie für die Verwendung von WQL benötigen, sind SELECT, WHERE und from.

## <a name="when-to-use-wql"></a>Verwendungszwecke von WQL

Vergessen Sie beim Arbeiten mit WMI und insbesondere bei WQL nicht, dass Sie auch Windows PowerShell verwenden. Wenn eine WQL-Abfrage nicht erwartungsgemäß funktioniert, ist es einfacher, einen standardmäßigen Windows PowerShell-Befehl zu verwenden, als die WQL-Abfrage zu debuggen.

Wenn Sie keine großen Datenmengen aus einem Remote System mit Bandbreitenbeschränkung zurückgeben, ist es selten produktiv, Stunden zu verbringen, eine komplizierte und bearbeiteme WQL-Abfrage zu optimieren, wenn ein absolut akzeptables Windows-Cmdlet vorhanden ist, das das gleiche tut, wenn es etwas langsamer ist.

## <a name="using-the-select-statement"></a>Verwenden der SELECT-Anweisung

Eine typische WMI-Abfrage beginnt mit einer SELECT-Anweisung, die alle Eigenschaften oder bestimmte Eigenschaften einer WMI-Klasse abruft. Wenn Sie alle Eigenschaften einer WMI-Klasse auswählen möchten, verwenden Sie ein Sternchen ( \* ). Das from-Schlüsselwort gibt die WMI-Klasse an.

Eine SELECT-Anweisung weist das folgende Format auf:

```
Select <property> from <WMI-class>
```

Mit der folgenden SELECT-Anweisung werden z. b. alle Eigenschaften (*) aus den Instanzen der WMI-Klasse Win32_Bios ausgewählt.

```
Select * from Win32_Bios
```

Um eine bestimmte Eigenschaft einer WMI-Klasse auszuwählen, platzieren Sie den Eigenschaftsnamen zwischen den Schlüsselwörtern SELECT und from.

Mit der folgenden Abfrage wird nur der Name des BIOS aus der Win32_Bios WMI-Klasse ausgewählt. Der Befehl speichert die Abfrage in der $queryName Variable.

```
Select Name from Win32_Bios
```

Wenn Sie mehr als eine Eigenschaft auswählen möchten, verwenden Sie Kommas, um die Eigenschaften Namen voneinander zu trennen.
In der folgenden WMI-Abfrage werden der Name und die Version der Win32_Bios WMI-Klasse ausgewählt. Der Befehl speichert die Abfrage in der $queryNameVersion Variable.

```
Select name, version from Win32_Bios
```

## <a name="using-the-wql-query"></a>Verwenden der WQL-Abfrage

Es gibt drei Möglichkeiten, die WQL-Abfrage im Windows PowerShell-Befehl zu verwenden.

- Verwenden Sie das Cmdlet "Get-WmiObject".
- Verwenden Sie das Cmdlet "Get-CimInstance".
- Verwenden Sie die typbeschleunigung [wmisearcher].

## <a name="using-the-get-wmiobject-cmdlet"></a>Verwenden des Cmdlets "Get-WmiObject"

Die einfachste Möglichkeit, die WQL-Abfrage zu verwenden, besteht darin, Sie in Anführungszeichen (als Zeichenfolge) einzuschließen und anschließend die Abfrage Zeichenfolge als Wert des Abfrage Parameters des Get-WmiObject-Cmdlets zu verwenden, wie im folgenden Beispiel gezeigt.

```powershell
Get-WmiObject -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Sie können auch die WQL-Anweisung in einer Variablen speichern und dann die Variable als Wert des Abfrage Parameters verwenden, wie im folgenden Befehl gezeigt.

```powershell
$query = "Select * from Win32_Bios"
Get-WmiObject -Query $query
```

Beide Formate können mit einer beliebigen WQL-Anweisung verwendet werden. Der folgende Befehl verwendet die Abfrage in der $queryName-Variablen, um nur die Namens-und Versions Eigenschaften des System-BIOS zu erhalten.

```powershell
$queryNameVersion = "Select Name, Version from Win32_Bios"
Get-WmiObject -Query $queryNameVersion
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

Beachten Sie, dass Sie die Parameter des Get-WmiObject-Cmdlets verwenden können, um das gleiche Ergebnis zu erhalten. Der folgende Befehl ruft z. b. auch die Werte der Eigenschaften "Name" und "Version" der Instanzen der Win32_Bios WMI-Klasse ab.

```powershell
Get-WmiObject -Class Win32_Bios -Property Name, Version
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

## <a name="using-the-get-ciminstance-cmdlet"></a>Verwenden des Cmdlets "Get-ciminstance"

Ab Windows PowerShell 3,0 können Sie das Cmdlet "Get-CimInstance" verwenden, um WQL-Abfragen auszuführen.

Get-CimInstance ruft Instanzen von CIM-kompatiblen Klassen ab, einschließlich WMI-Klassen. Die CIM-Cmdlets, die Windows PowerShell 3,0 eingeführt haben, führen dieselben Aufgaben wie die WMI-Cmdlets aus. Die CIM-Cmdlets entsprechen den WS-Management (WSMAN)-Standards und dem Common Information Model (CIM)-Standard, mit dem die Cmdlets dieselben Verfahren zum Verwalten von Windows-Computern und-Computern verwenden können, auf denen andere Betriebssysteme ausgeführt werden.

Der folgende Befehl verwendet das Cmdlet "Get-CimInstance", um eine WQL-Abfrage auszuführen.

Jede WQL-Abfrage, die mit Get-WmiObject verwendet werden kann, kann auch mit Get-ciminstance verwendet werden.

```powershell
Get-CimInstance -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Get-CimInstance gibt ein ciminstance-Objekt zurück, anstelle des ManagementObject, das Get-WmiObject zurückgibt, aber die-Objekte sind sehr ähnlich.

```
(Get-CimInstance -Query "Select * from Win32_Bios").GetType().FullName
Microsoft.Management.Infrastructure.CimInstance
(Get-WmiObject -Query "Select * from Win32_Bios").GetType().FullName
System.Management.ManagementObject
```

## <a name="using-the-wmisearcher-type-accelerator"></a>Verwenden der [wmisearcher]-typbeschleunigung

Die typbeschleunigung [wmisearcher] erstellt ein ManagementObjectSearcher-Objekt aus einer WQL-Anweisungs Zeichenfolge. Das ManagementObjectSearcher-Objekt verfügt über viele Eigenschaften und Methoden, aber die grundlegendste Methode ist die Get-Methode, die die angegebene WMI-Abfrage aufruft und die resultierenden Objekte zurückgibt.

Wenn Sie [wmisearcher] verwenden, erhalten Sie einfachen Zugriff auf die ManagementObjectSearcher-.NET Framework-Klasse. Auf diese Weise können Sie WMI Abfragen und die Art und Weise konfigurieren, wie die Abfrage durchgeführt wird.

So verwenden Sie die "[wmisearcher]"-typbeschleunigung:

1. Wandeln Sie die WQL-Zeichenfolge in ein ManagementObjectSearcher-Objekt um.
2. Ruft die Get-Methode des ManagementObjectSearcher-Objekts auf.

Der folgende Befehl wandelt z. b. die Abfrage "Select all" um, speichert das Ergebnis in der $BIOS Variable und ruft dann die Get-Methode des ManagementObjectSearcher-Objekts in der $BIOS-Variablen auf.

```powershell
$bios = [wmisearcher]"Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Hinweis: Standardmäßig werden nur ausgewählte Objekteigenschaften angezeigt. Diese Eigenschaften werden in der Types.ps1-XML-Datei definiert.

Sie können die typbeschleunigung [wmisearcher] zum Umwandeln der Abfrage oder der Variablen verwenden. Im folgenden Beispiel wird die typbeschleunigung [wmisearcher] zum Umwandeln der Variablen verwendet. Das Ergebnis ist identisch.

```powershell
[wmisearcher]$bios = "Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

Wenn Sie die typbeschleunigung [wmisearcher] verwenden, wird die Abfrage Zeichenfolge in ein ManagementObjectSearcher-Objekt geändert, wie in den folgenden Befehlen gezeigt.

```
$a = "Select * from Win32_Bios"
$a.GetType().FullName
System.String

$a = [wmisearcher]"Select * from Win32_Bios"
$a.GetType().FullName
System.Management.ManagementObjectSearcher
```

Dieses Befehls Format funktioniert bei jeder Abfrage. Der folgende Befehl ruft den Wert der Name-Eigenschaft der Win32_Bios WMI-Klasse ab.

```powershell
$biosname = [wmisearcher]"Select Name from Win32_Bios"
$biosname.Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

Sie können diesen Vorgang in einem einzigen Befehl ausführen, obwohl der Befehl etwas schwieriger zu interpretieren ist.

In diesem Format verwenden Sie die typbeschleunigung [wmisearcher], um die WQL-Abfrage Zeichenfolge in einen ManagementObjectSearcher umzuwandeln. Anschließend wird die Get-Methode für das Objekt aufgerufen, und zwar in einem einzigen Befehl. Die Klammern (), die die eingefügte Zeichenfolge einschließen, leiten Windows PowerShell direkt in die Zeichenfolge ein, bevor die-Methode aufgerufen wird.

```powershell
([wmisearcher]"Select name from Win32_Bios").Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

## <a name="using-the-basic-wql-where-statement"></a>Verwenden der einfachen WQL WHERE-Anweisung

Eine WHERE-Anweisung legt Bedingungen für die Daten fest, die eine SELECT-Anweisung zurückgibt.

Die WHERE-Anweisung weist das folgende Format auf:

```
where <property> <operator> <value>
```

Beispiel:

```
where Name = 'Notepad.exe'
```

Die WHERE-Anweisung wird mit der SELECT-Anweisung verwendet, wie im folgenden Beispiel gezeigt.

```
Select * from Win32_Process where Name = 'Notepad.exe'
```

Wenn Sie die WHERE-Anweisung verwenden, müssen der Eigenschaftsname und der Wert genau sein.

Beispielsweise ruft der folgende Befehl die Notepad-Prozesse auf dem lokalen Computer ab.

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad.exe'"
```

Der folgende Befehl schlägt jedoch fehl, da der Prozess Name die Dateinamenerweiterung ". exe" enthält.

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad'"
```

## <a name="where-statement-comparison-operators"></a>Where-Anweisungs Vergleichs Operatoren

Die folgenden Operatoren sind in einer WQL WHERE-Anweisung gültig.

```
Operator    Description
-----------------------
=           Equal
!=          Not equal
<>          Not equal
<           Less than
>           Greater than
<=          Less than or equal
>=          Greater than or equal
LIKE        Wildcard match
IS          Evaluates null
ISNOT       Evaluates not null
ISA         Evaluates a member of a WMI class
```

Es sind andere Operatoren vorhanden, die jedoch für Vergleiche verwendet werden.

Mit der folgenden Abfrage werden z. b. die Eigenschaften Name und Priorität aus Prozessen in der Win32_Process-Klasse ausgewählt, wobei die Prozesspriorität größer oder gleich 11 ist. Das Get-WmiObject-Cmdlet führt die Abfrage aus.

```powershell
$highPriority = "Select Name, Priority from Win32_Process " +
  "where Priority >= 11"
Get-WmiObject -Query $highPriority
```

## <a name="using-the-wql-operators-in-the-filter-parameter"></a>Verwenden der WQL-Operatoren im Filter-Parameter

Die WQL-Operatoren können auch im Wert des Filter-Parameters der Get-WmiObject-oder Get-CimInstance-Cmdlets sowie im Wert der Abfrage Parameter dieser Cmdlets verwendet werden.

Der folgende Befehl ruft z. b. die Eigenschaften "Name" und "ProcessId" der letzten fünf Prozesse ab, deren ProcessID-Werte größer als 1004 sind. Der Befehl verwendet den Filter-Parameter, um die ProcessID-Bedingung anzugeben.

```powershell
Get-WmiObject -Class Win32_Process `
-Property Name, ProcessID -Filter "ProcessID >= 1004" |
Sort ProcessID | Select Name, ProcessID -Last 5
```

```output
Name                                 ProcessID
----                                 ---------
SROSVC.exe                                4220
WINWORD.EXE                               4664
TscHelp.exe                               4744
SnagIt32.exe                              4748
WmiPrvSE.exe                              5056
```

## <a name="using-the-like-operator"></a>Verwenden des LIKE-Operators

Mit dem Like-Operator können Sie Platzhalter Zeichen verwenden, um die Ergebnisse einer WQL-Abfrage zu filtern.

```
Like Operator  Description
--------------------------------------------------
[]             Character in a range [a-f] or a set
               of characters [abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

^              Character not in a range [^a-f] or
               not in a set [^abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

%              A string of zero or more characters

_              One character.
(underscore)   NOTE: To use a literal underscore
               in a query string, enclose it in
               square brackets [_].
```

Wenn der Like-Operator ohne Platzhalter Zeichen oder Bereichs Operatoren verwendet wird, verhält er sich wie der Gleichheits Operator (=) und gibt nur dann Objekte zurück, wenn er eine genaue Übereinstimmung für das Muster ist.

Sie können den Bereichs Vorgang mit dem Platzhalter Zeichen% kombinieren, um einfache, aber leistungsstarke Filter zu erstellen.

### <a name="like-operator-examples"></a>Like-Operator Beispiele

#### <a name="example-1-range"></a>Beispiel 1: [ \<range> ]

Die folgenden Befehle starten Notepad und suchen dann nach einer Instanz der Win32_Process-Klasse mit einem Namen, der mit einem Buchstaben zwischen "H" und "N" beginnt (ohne Beachtung der Groß-/Kleinschreibung).

Die Abfrage sollte jeden Prozess von Hotpad.exe durch Notepad.exe zurückgeben.

```powershell
Notepad   # Starts Notepad
$query = "Select * from win32_Process where Name LIKE '[H-N]otepad.exe'"
Get-WmiObject -Query $query | Select Name, ProcessID
```

```output
Name                                ProcessID
----                                ---------
notepad.exe                              1740
```

#### <a name="example-2-range-and-"></a>Beispiel 2: [ \<range> ] und%

Mit den folgenden Befehlen wird der gesamte Prozess ausgewählt, dessen Name mit einem Buchstaben zwischen a und P beginnt (ohne Beachtung der Groß-/Kleinschreibung), gefolgt von NULL oder mehr Buchstaben in beliebiger Kombination.

Das Cmdlet "Get-WmiObject" führt die Abfrage aus, das Select-Object-Cmdlet ruft die Eigenschaften "Name" und "ProcessId" ab, und das Sort-Object-Cmdlet sortiert die Ergebnisse in alphabetischer Reihenfolge nach Namen.

```powershell
$query = "Select * from win32_Process where name LIKE '[A-P]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-3-not-in-range-"></a>Beispiel 3: nicht im Bereich (^)

Der folgende Befehl ruft Prozesse ab, deren Namen nicht mit einem der folgenden Buchstaben beginnen: A, S, W, P, R, C, U, N

und gefolgt von NULL oder mehr Buchstaben.

```powershell
$query = "Select * from win32_Process where name LIKE '[^ASWPRCUN]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-4-any-characters----or-none-"></a>Beispiel 4: beliebige Zeichen--oder None (%)

Die folgenden Befehle erhalten Prozesse, deren Namen mit "Calc" beginnen.
Das Symbol "%" in WQL entspricht dem Sternchen \* Symbol () in regulären Ausdrücken.

```powershell
$query = "Select * from win32_Process where Name LIKE 'calc%'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                               ProcessID
----                               ---------
calc.exe                                4424
```

#### <a name="example-5-one-character-_"></a>Beispiel 5: ein Zeichen (_)

Mit den folgenden Befehlen werden Prozesse mit Namen, die das folgende Muster aufweisen: "c_lc.exe", wobei der Unterstrich ein beliebiges Zeichen darstellt. Dieses Muster entspricht einem beliebigen Namen aus calc.exe durch czlc.exe oder c9lc.exe, stimmt jedoch nicht mit den Namen überein, bei denen das "c" und "l" durch mehr als ein Zeichen voneinander getrennt sind.

```powershell
$query = "Select * from Win32_Process where Name LIKE 'c_lc.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                                 ProcessID
----                                 ---------
calc.exe                                  4424
```

#### <a name="example-6-exact-match"></a>Beispiel 6: exakte Entsprechung

Mit den folgenden Befehlen werden Prozesse mit dem Namen WLIDSVC.exe erhalten. Obwohl die Abfrage das LIKE-Schlüsselwort verwendet, erfordert Sie eine exakte Entsprechung, da der Wert keine Platzhalter Zeichen enthält.

```powershell
$query = "Select * from win32_Process where name LIKE 'WLIDSVC.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```powershell

```output
Name                                 ProcessID
----                                 ---------
WLIDSVC.exe                                84
```

## <a name="using-the-or-operator"></a>Verwenden des OR-Operators

Verwenden Sie das Schlüsselwort oder, um mehrere unabhängige Bedingungen anzugeben. Das-oder-Schlüsselwort wird in der WHERE-Klausel angezeigt. Sie führt eine inklusive OR-Operation für zwei (oder mehr) Bedingungen aus und gibt die Elemente zurück, die eine der Bedingungen erfüllen.

Der or-Operator weist das folgende Format auf:

```
Where <property> <operator> <value> or <property> <operator> <value> ...
```

Beispielsweise werden mit den folgenden Befehlen alle Instanzen der WMI-Klasse Win32_Process, aber nur zurückgegeben, wenn der Prozess Name winword.exe oder excel.exe ist.

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe'"
Get-WmiObject -Query $q
```

Die-oder-Anweisung kann mit mehr als zwei Bedingungen verwendet werden. In der folgenden Abfrage wird die-oder-Anweisung Winword.exe, Excel.exe oder Powershell.exe abgerufen.

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe' or Name='powershell.exe'"
```

## <a name="using-the-and-operator"></a>Verwenden des and-Operators

Wenn Sie mehrere verwandte Bedingungen angeben möchten, verwenden Sie das Schlüsselwort und. Das Schlüsselwort und wird in der WHERE-Klausel angezeigt. Sie gibt Elemente zurück, die alle Bedingungen erfüllen.

Der and-Operator weist das folgende Format auf:

```
Where <property> <operator> <value> and <property> <operator> <value> ...
```

Mit den folgenden Befehlen werden z. b. Prozesse mit dem Namen "Winword.exe" und der Prozess-ID 6512 angezeigt.

Beachten Sie, dass die Befehle das Get-CimInstance-Cmdlet verwenden.

```powershell
$q = "Select * from Win32_Process where Name = 'winword.exe' " +
  "and ProcessID =6512"
Get-CimInstance -Query $q
```

```output
ProcessId   Name             HandleCount      WorkingSetSize   VirtualSize
---------   ----             -----------      --------------   -----------
# 6512      WINWORD.EXE      768              117170176        633028608
```

Alle Operatoren, einschließlich der Like-Operatoren, sind mit den Operatoren, und gültig. Außerdem können Sie die Operatoren oder und und in einer einzelnen Abfrage mit Klammern kombinieren, die Windows PowerShell mitteilen, welche Klauseln zuerst verarbeitet werden sollen.

Dieser Befehl verwendet das Windows PowerShell-Fortsetzungs Zeichen ('), dividiert den Befehl in zwei Zeilen.

```powershell
$q = "Select * from Win32_Process `
where (Name = 'winword.exe' or Name = 'excel.exe') and HandleCount > 700"
Get-CimInstance -Query $q
```

```output
ProcessId    Name             HandleCount      WorkingSetSize   VirtualSize
---------    ----             -----------      --------------   -----------
     6512    WINWORD.EXE      797              117268480        634425344
     9610    EXCEL.EXE        727               38858752        323227648
```

## <a name="searching-for-null-values"></a>Suchen nach NULL-Werten

Das Suchen nach NULL-Werten in WMI ist eine Herausforderung, da dies zu unvorhersehbaren Ergebnissen führen kann. NULL ist nicht 0 (null) und entspricht nicht einer leeren Zeichenfolge oder einer leeren Zeichenfolge. Einige WMI-Klasseneigenschaften werden initialisiert, andere hingegen nicht. eine Suche nach NULL funktioniert daher möglicherweise nicht für alle Eigenschaften.

Um nach NULL-Werten zu suchen, verwenden Sie den is-Operator mit dem Wert "Null".

Mit den folgenden Befehlen werden z. b. Prozesse mit einem NULL-Wert für die intalldate-Eigenschaft angezeigt. Die Befehle geben viele Prozesse zurück.

```powershell
$q = "Select * from Win32_Process where InstallDate is null"
Get-WmiObject -Query $q
```

Im Gegensatz dazu ruft der folgende Befehl Benutzerkonten ab, die einen NULL-Wert für die Description-Eigenschaft aufweisen. Dieser Befehl gibt keine Benutzerkonten zurück, obwohl die meisten Benutzerkonten über keinen Wert für die Description-Eigenschaft verfügen.

```powershell
$q = "Select * from Win32_UserAccount where Description is null"
Get-WmiObject -Query $q
```

Um die Benutzerkonten zu suchen, die keinen Wert für die Description-Eigenschaft aufweisen, verwenden Sie den Gleichheits Operator, um eine leere Zeichenfolge zu erhalten. Wenn Sie die leere Zeichenfolge darstellen möchten, verwenden Sie zwei aufeinanderfolgende einfache Anführungszeichen.

```powershell
$q = "Select * from Win32_UserAccount where Description = '' "
```

## <a name="using-true-or-false"></a>Verwenden von true oder false

Verwenden Sie "true" und "false", um boolesche Werte in den Eigenschaften von WMI-Objekten zu erhalten.
Dabei wird die Groß-/Kleinschreibung nicht beachtet.

Die folgende WQL-Abfrage gibt nur lokale Benutzerkonten von einem in die Domäne eingebundener Computer zurück.

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = True"
Get-CimInstance -Query $q
```

Wenn Sie Domänen Konten suchen möchten, verwenden Sie den Wert false, wie im folgenden Beispiel gezeigt.

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = False"
Get-CimInstance -Query $q
```

## <a name="using-the-escape-character"></a>Verwenden des Escapezeichens

WQL verwendet den umgekehrten Schrägstrich ( \) als Escapezeichen). Dies unterscheidet sich von Windows PowerShell, bei dem das Graviszeichen-Zeichen (') verwendet wird.

Anführungszeichen und die Zeichen, die für Anführungszeichen verwendet werden, müssen häufig mit Escapezeichen versehen werden, damit Sie nicht falsch interpretiert werden.

Um einen Benutzer zu finden, dessen Name ein einzelnes Anführungszeichen enthält, verwenden Sie einen umgekehrten Schrägstrich, um das einfache Anführungszeichen mit Escapezeichen zu versehen, wie im folgenden Befehl gezeigt.

```powershell
$q = "Select * from Win32_UserAccount where Name = 'Tim O\'Brian'"
Get-CimInstance -Query $q
```

```output
Name             Caption          AccountType      SID              Domain
----             -------          -----------      ---              ------
Tim O'Brian      FABRIKAM\TimO    512              S-1-5-21-1457... FABRIKAM
```

In einigen Fällen muss der umgekehrte Schrägstrich ebenfalls mit Escapezeichen versehen werden. Beispielsweise generieren die folgenden Befehle aufgrund des umgekehrten Schrägstrichs im Beschriftungs Wert einen ungültigen Abfrage Fehler.

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\TimO'"
Get-CimInstance -Query $q
```

```output
Get-CimInstance : Invalid query
At line:1 char:1
+ Get-CimInstance -Query $q
+ ~~~~~~~~~~~
  + CategoryInfo          : InvalidArgument: (:) [Get-CimInstance], CimExcep
  + FullyQualifiedErrorId : HRESULT 0x80041017,Microsoft.Management.Infrastr
```

Um den umgekehrten Schrägstrich mit Escapezeichen zu versehen, verwenden Sie einen zweiten umgekehrten Schrägstrich, wie im folgenden Befehl gezeigt.

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\\TimO'"
Get-CimInstance -Query $q
```

## <a name="see-also"></a>SIEHE AUCH

[about_Special_Characters](about_Special_Characters.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_WMI](about_WMI.md)

[about_WMI_Cmdlets](about_WMI_Cmdlets.md)
