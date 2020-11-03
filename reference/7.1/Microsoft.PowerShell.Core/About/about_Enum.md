---
description: Die- `enum` Anweisung wird verwendet, um eine Enumeration zu deklarieren. Eine Enumeration ist ein eindeutiger Typ, der aus einem Satz benannter Bezeichnungen besteht, die als Enumeratorliste bezeichnet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_enum?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Enum
ms.openlocfilehash: 1ffb18ab98fbd40b407abfe32c71027315b69621
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222103"
---
# <a name="about-enum"></a>Informationen über die Aufzählung

## <a name="short-description"></a>KURZE BESCHREIBUNG
Die- `enum` Anweisung wird verwendet, um eine Enumeration zu deklarieren. Eine Enumeration ist ein eindeutiger Typ, der aus einem Satz benannter Bezeichnungen besteht, die als Enumeratorliste bezeichnet werden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Mit der- `enum` Anweisung können Sie einen stark typisierten Satz von Bezeichnungen erstellen. Diese Enumeration kann im Code verwendet werden, ohne dass Rechtschreibfehler analysiert oder überprüft werden müssen.

Enumerationen werden intern als ganze Zahlen mit einem Startwert von 0 (null) dargestellt. Der ersten Bezeichnung in der Liste wird der Wert 0 (null) zugewiesen. Die übrigen Bezeichnungen werden aufeinander folgende Zahlen zugewiesen.

In der Definition können Bezeichnungen einen beliebigen ganzzahligen Wert erhalten. Bezeichnungen ohne zugewiesenen Wert nehmen den nächsten ganzzahligen Wert an.

## <a name="syntax-basic"></a>Syntax (Basic)

```syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

## <a name="usage-example"></a>Verwendungsbeispiel

Das folgende Beispiel zeigt eine Enumeration von-Objekten, die als Mediendateien angesehen werden können. Die-Definition weist den zugrunde liegenden Werten von,, explizite Werte zu `music` `picture` `video` . Bezeichnungen, die unmittelbar auf eine explizite Zuweisung folgen, erhalten den nächsten ganzzahligen Wert. Synonyme können erstellt werden, indem der gleiche Wert einer anderen Bezeichnung zugewiesen wird. sehen Sie sich die erstellten Werte für an: `ogg` , `oga` , `mogg` , oder `jpg` , `jpeg` oder `mpg` `mpeg` .

```powershell
enum MediaTypes {
    unknown
    music = 10
    mp3
    aac
    ogg = 15
    oga = 15
    mogg = 15
    picture = 20
    jpg
    jpeg = 21
    png
    video = 40
    mpg
    mpeg = 41
    avi
    m4v
}
```

Die- `GetEnumNames()` Methode gibt die Liste der Bezeichnungen für die-Enumeration zurück.

```powershell
[MediaTypes].GetEnumNames()
unknown
music
mp3
aac
ogg
oga
mogg
picture
jpg
jpeg
png
video
mpg
mpeg
avi
m4v
```

Die- `GetEnumValues()` Methode gibt die Liste der Werte für die-Enumeration zurück.

```powershell
[MediaTypes].GetEnumValues()
unknown
music
mp3
aac
oga
oga
oga
picture
jpeg
jpeg
png
video
mpeg
mpeg
avi
m4v
```

**Hinweis** : getenumschlag Names () und getenumschlag Values () scheinen die gleichen Ergebnisse zurückzugeben.
Intern ändert PowerShell jedoch Werte in Bezeichnungen. Lesen Sie die Liste sorgfältig, und Sie werden feststellen, dass `oga` und `mogg` unter den Ergebnissen der Get-Namen aufgeführt werden, aber nicht unter der ähnlichen Ausgabe der Get-Werte für `jpg` , `jpeg` und `mpg` `mpeg` .

```powershell
[MediaTypes].GetEnumName(15)
oga

[MediaTypes].GetEnumNames() | ForEach-Object {
  "{0,-10} {1}" -f $_,[int]([MediaTypes]::$_)
}
unknown    0
music      10
mp3        11
aac        12
ogg        15
oga        15
mogg       15
picture    20
jpg        21
jpeg       21
png        22
video      40
mpg        41
mpeg       41
avi        42
m4v        43
```

## <a name="enumerations-as-flags"></a>Enumerationen als Flags

Enumerationen können als eine Auflistung von Bitflags definiert werden.
Dabei stellt die Enumeration an einem beliebigen Punkt ein oder mehrere dieser Flags dar, die aktiviert sind.

Damit Enumerationen als Flags ordnungsgemäß funktionieren, sollte jede Bezeichnung eine Potenz von zwei Werten aufweisen.

## <a name="syntax-flags"></a>Syntax (Flags)

```syntax
[Flags()] enum <enum-name> {
    <label 0> [= 1]
    <label 1> [= 2]
    <label 2> [= 4]
    <label 3> [= 8]
    ...
}
```

## <a name="flags-usage-example"></a>Beispiel zur Verwendung von Flags

Im folgenden Beispiel wird die *FileAttribute* -Enumeration erstellt.

```powershell
[Flags()] enum FileAttributes {
    Archive = 1
    Compressed = 2
    Device = 4
    Directory = 8
    Encrypted = 16
    Hidden = 32
}

[FileAttributes]$file1 = [FileAttributes]::Archive
[FileAttributes]$file1 +=[FileAttributes]::Compressed
[FileAttributes]$file1 +=  [FileAttributes]::Device
"file1 attributes are: $file1"

[FileAttributes]$file2 = [FileAttributes]28 ## => 16 + 8 + 4
"file2 attributes are: $file2"
```

```output
file1 attributes are: Archive, Compressed, Device
file2 attributes are: Device, Directory, Encrypted
```

Um zu testen, ob ein bestimmtes festgelegt ist, können Sie den binären Vergleichs Operator verwenden `-band` . In diesem Beispiel testen wir das **Gerät** und die **Archiv** Attribute im Wert von `$file2` .

```
PS > ($file2 -band [FileAttributes]::Device) -eq [FileAttributes]::Device
True

PS > ($file2 -band [FileAttributes]::Archive) -eq [FileAttributes]::Archive
False
```

