---
description: Beschreibt die Verwendung von Objekteigenschaften in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Properties
ms.openlocfilehash: c8e711086922ea6a76978085a63380156591bb1d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222623"
---
# <a name="about-properties"></a>Informationen zu Eigenschaften

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt die Verwendung von Objekteigenschaften in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

PowerShell verwendet strukturierte Sammlungen von Informationen, die als Objekte bezeichnet werden, um die Elemente in Daten speichern oder den Status des Computers darzustellen. In der Regel arbeiten Sie mit einem Objekt, das Teil des Microsoft .NET Frameworks ist, aber Sie können auch benutzerdefinierte Objekte in PowerShell erstellen.

Die Zuordnung zwischen einem Element und seinem Objekt ist sehr nah. Wenn Sie ein Objekt ändern, ändern Sie in der Regel das Element, das es darstellt. Wenn Sie z. b. eine Datei in PowerShell erhalten, erhalten Sie nicht die tatsächliche Datei. Stattdessen erhalten Sie ein FileInfo-Objekt, das die Datei darstellt. Wenn Sie das FileInfo-Objekt ändern, wird die Datei ebenfalls geändert.

Die meisten Objekte verfügen über Eigenschaften. Eigenschaften sind die Daten, die einem Objekt zugeordnet sind. Verschiedene Objekttypen haben unterschiedliche Eigenschaften. Beispielsweise verfügt ein FileInfo-Objekt, das eine Datei darstellt, über eine **isleonly** -Eigenschaft, die $true enthält, wenn die Datei das schreibgeschützte Attribut hat, und $false, wenn dies nicht der Fall ist.
Ein DirectoryInfo-Objekt, das ein Dateisystem Verzeichnis darstellt, verfügt über eine Parent-Eigenschaft, die den Pfad zum übergeordneten Verzeichnis enthält.

### <a name="object-properties"></a>Objekteigenschaften

Verwenden Sie das-Cmdlet, um die Eigenschaften eines-Objekts zu erhalten `Get-Member` . Um z. b. die Eigenschaften eines **FileInfo** -Objekts zu erhalten, verwenden Sie das `Get-ChildItem` Cmdlet, um das FileInfo-Objekt zu erhalten, das eine Datei darstellt. Verwenden Sie dann einen Pipeline Operator (&#124;), um das **FileInfo** -Objekt an zu senden `Get-Member` . Mit dem folgenden Befehl wird die PowerShell.exe Datei abgerufen und an gesendet `Get-Member` .
Die \$ Automatische PSHome-Variable enthält den Pfad des PowerShell-Installationsverzeichnisses.

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member
```

Die Ausgabe des Befehls listet die Member des **FileInfo** -Objekts auf.
Member enthalten Eigenschaften und Methoden. Wenn Sie in PowerShell arbeiten, haben Sie Zugriff auf alle Member der Objekte.

Um nur die Eigenschaften eines-Objekts und nicht die-Methoden zu erhalten, verwenden Sie den Membership Type-Parameter des `Get-Member` Cmdlets mit dem Wert "Property", wie im folgenden Beispiel gezeigt.

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member -MemberType property
```

```Output
TypeName: System.IO.FileInfo

Name              MemberType Definition
----              ---------- ----------
Attributes        Property   System.IO.FileAttributes Attributes {get;set;}
CreationTime      Property   System.DateTime CreationTime {get;set;}
CreationTimeUtc   Property   System.DateTime CreationTimeUtc {get;set;}
Directory         Property   System.IO.DirectoryInfo Directory {get;}
DirectoryName     Property   System.String DirectoryName {get;}
Exists            Property   System.Boolean Exists {get;}
Extension         Property   System.String Extension {get;}
FullName          Property   System.String FullName {get;}
IsReadOnly        Property   System.Boolean IsReadOnly {get;set;}
LastAccessTime    Property   System.DateTime LastAccessTime {get;set;}
LastAccessTimeUtc Property   System.DateTime LastAccessTimeUtc {get;set;}
LastWriteTime     Property   System.DateTime LastWriteTime {get;set;}
LastWriteTimeUtc  Property   System.DateTime LastWriteTimeUtc {get;set;}
Length            Property   System.Int64 Length {get;}
Name              Property   System.String Name {get;}
```

Nachdem Sie die Eigenschaften gefunden haben, können Sie Sie in ihren PowerShell-Befehlen verwenden.

## <a name="property-values"></a>Eigenschaftswerte

Obwohl jedes Objekt eines bestimmten Typs über die gleichen Eigenschaften verfügt, beschreiben die Werte dieser Eigenschaften das jeweilige Objekt. Beispielsweise verfügt jedes FileInfo-Objekt über eine Eigenschaft "kreationtime", aber der Wert dieser Eigenschaft ist für jede Datei anders.

Die gängigste Methode, um die Werte der Eigenschaften eines Objekts zu erhalten, ist die Verwendung der Punkt Methode. Geben Sie einen Verweis auf das Objekt ein, z. b. eine Variable, die das Objekt enthält, oder einen Befehl, mit dem das Objekt abgerufen wird. Geben Sie dann einen Punkt (.) gefolgt vom Eigenschaftsnamen ein.

Der folgende Befehl zeigt z. b. den Wert der Eigenschaft "kreationtime" der PowerShell.exe Datei an. Der `Get-ChildItem` Befehl gibt ein FileInfo-Objekt zurück, das die PowerShell.exe Datei darstellt. Der Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er ausgeführt wird, bevor auf Eigenschaften zugegriffen wird. Auf den `Get-ChildItem` Befehl folgt ein Punkt und der Name der Eigenschaft "kreationtime" wie folgt:

```powershell
(Get-ChildItem $pshome\PowerShell.exe).creationtime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

Sie können auch ein Objekt in einer Variablen speichern und dann seine Eigenschaften mit der Punkt-Methode erhalten, wie im folgenden Beispiel gezeigt:

```powershell
$a = Get-ChildItem $pshome\PowerShell.exe
$a.CreationTime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

Sie können auch die `Select-Object` -und- `Format-List` Cmdlets verwenden, um die Eigenschaftswerte eines Objekts anzuzeigen. `Select-Object` und `Format-List` verfügen jeweils über einen **Property** -Parameter. Sie können den **Property** -Parameter verwenden, um eine oder mehrere Eigenschaften und deren Werte anzugeben. Oder Sie können das Platzhalter Zeichen ( \* ) verwenden, um alle Eigenschaften darzustellen.

Der folgende Befehl zeigt z. b. die Werte aller Eigenschaften der PowerShell.exe Datei an.

```powershell
Get-ChildItem $pshome\PowerShell.exe | Format-List -Property *
```

```output
PSPath            : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0\PowerShell.exe
PSParentPath      : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0
PSChildName       : PowerShell.exe
PSDrive           : C
PSProvider        : Microsoft.PowerShell.Core\FileSystem
PSIsContainer     : False
Mode              : -a----
VersionInfo       : File:             C:\Windows\System32\WindowsPowerShell\
                    v1.0\PowerShell.exe
                    InternalName:     POWERSHELL
                    OriginalFilename: PowerShell.EXE.MUI
                    FileVersion:      10.0.16299.15 (WinBuild.160101.0800)
                    FileDescription:  Windows PowerShell
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.16299.15
                    Debug:            False
                    Patched:          False
                    PreRelease:       False
                    PrivateBuild:     False
                    SpecialBuild:     False
                    Language:         English (United States)

BaseName          : PowerShell
Target            : {C:\Windows\WinSxS\amd64_microsoft-windows-powershell-ex
                    e_31bf3856ad364e35_10.0.16299.15_none_8c022aa6735716ae\p
                    owershell.exe}
LinkType          : HardLink
Name              : PowerShell.exe
Length            : 449024
DirectoryName     : C:\Windows\System32\WindowsPowerShell\v1.0
Directory         : C:\Windows\System32\WindowsPowerShell\v1.0
IsReadOnly        : False
Exists            : True
FullName          : C:\Windows\System32\WindowsPowerShell\v1.0\PowerShell.ex
Extension         : .exe
CreationTime      : 9/29/2017 6:43:19 AM
CreationTimeUtc   : 9/29/2017 1:43:19 PM
LastAccessTime    : 9/29/2017 6:43:19 AM
LastAccessTimeUtc : 9/29/2017 1:43:19 PM
LastWriteTime     : 9/29/2017 6:43:19 AM
LastWriteTimeUtc  : 9/29/2017 1:43:19 PM
Attributes        : Archive
```

### <a name="static-properties"></a>Statische Eigenschaften

Sie können die statischen Eigenschaften von .NET-Klassen in PowerShell verwenden. Statische Eigenschaften sind Eigenschaften der-Klasse, im Gegensatz zu Standardeigenschaften, bei denen es sich um Eigenschaften eines Objekts handelt.

Verwenden Sie den static-Parameter des Get-Member-Cmdlets, um die statischen Eigenschaften einer Klasse zu erhalten.

Beispielsweise ruft der folgende Befehl die statischen Eigenschaften der- `System.DateTime` Klasse ab.

```powershell
Get-Date | Get-Member -MemberType Property -Static
```

```Output
TypeName: System.DateTime

Name     MemberType Definition
----     ---------- ----------
MaxValue Property   static datetime MaxValue {get;}
MinValue Property   static datetime MinValue {get;}
Now      Property   datetime Now {get;}
Today    Property   datetime Today {get;}
UtcNow   Property   datetime UtcNow {get;}
```

Verwenden Sie die folgende Syntax, um den Wert einer statischen Eigenschaft zu erhalten.

```
[<ClassName>]::<Property>
```

Mit dem folgenden Befehl wird z. b. der Wert der statischen Eigenschaft UtcNow der- `System.DateTime` Klasse abgerufen.

```powershell
[System.DateTime]::UtcNow
```

### <a name="properties-of-scalar-objects-and-collections"></a>Eigenschaften von skalaren Objekten und Auflistungen

Die Eigenschaften eines Objekts ("Skalar") eines bestimmten Typs unterscheiden sich häufig von den Eigenschaften einer Auflistung von Objekten desselben Typs.
Beispielsweise verfügt jeder Dienst über die **Display Name** -Eigenschaft, aber eine Auflistung von Diensten verfügt nicht über eine **Display Name** -Eigenschaft.

Mit dem folgenden Befehl wird der Wert der **Display Name** -Eigenschaft des Dienst "AudioSrv" abgerufen.

```powershell
(Get-Service Audiosrv).DisplayName
```

```output
Windows Audio
```

Ab PowerShell 3,0 versucht PowerShell, Skript Fehler zu verhindern, die sich aus den unterschiedlichen Eigenschaften von skalaren Objekten und Auflistungen ergeben. Derselbe Befehl gibt den Wert der **DisplayName** -Eigenschaft für jeden Dienst zurück, der `Get-Service` zurückgibt.

```powershell
(Get-Service).DisplayName
```

```output
Application Experience
Application Layer Gateway Service
Windows All-User Install Agent
Application Identity
Application Information
...
```

Wenn Sie eine Sammlung übermitteln, aber eine Eigenschaft anfordern, die nur für einzelne (skalare) Objekte vorhanden ist, gibt PowerShell den Wert dieser Eigenschaft für jedes Objekt in der Auflistung zurück.

Alle Auflistungen haben eine **count** -Eigenschaft, die zurückgibt, wie viele Objekte in der Auflistung enthalten sind.

```powershell
(Get-Service).Count
```

```output
176
```

Ab PowerShell 3,0 gibt PowerShell den korrekten Wert zurück, wenn Sie die count-oder length-Eigenschaft von 0 (null) Objekten oder einem Objekt anfordern.

```powershell
(Get-Service Audiosrv).Count
```

```output
1
```

Wenn eine Eigenschaft für die einzelnen Objekte und für die Auflistung vorhanden ist, wird nur die-Eigenschaft der Auflistung zurückgegeben.

 ```powershell
 $collection = @(
 [pscustomobject]@{length = "foo"}
 [pscustomobject]@{length = "bar"}
 )
 # PowerShell returns the collection's Length.
 $collection.length
 ```

 ```output
 2
 ```

Diese Funktion funktioniert auch mit Methoden von skalaren Objekten und Auflistungen. Weitere Informationen finden Sie unter [about_Methods](about_methods.md).

## <a name="see-also"></a>Weitere Informationen:

[about_Methods](about_Methods.md)

[about_Objects](about_Objects.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)

[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object)

[Format-List](xref:Microsoft.PowerShell.Utility.Format-List)
