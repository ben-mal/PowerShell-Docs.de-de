---
description: Die- `enum` Anweisung wird verwendet, um eine Enumeration zu deklarieren. Eine Enumeration ist ein eindeutiger Typ, der aus einem Satz benannter Bezeichnungen besteht, die als Enumeratorliste bezeichnet werden.
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_enum?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Enum
ms.openlocfilehash: 5572a717bbf9b546a30b227b3baf215196c4145d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604849"
---
# <a name="about-enum"></a><span data-ttu-id="81c03-104">Informationen über die Aufzählung</span><span class="sxs-lookup"><span data-stu-id="81c03-104">About Enum</span></span>

## <a name="short-description"></a><span data-ttu-id="81c03-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="81c03-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="81c03-106">Die- `enum` Anweisung wird verwendet, um eine Enumeration zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="81c03-106">The `enum` statement is used to declare an enumeration.</span></span> <span data-ttu-id="81c03-107">Eine Enumeration ist ein eindeutiger Typ, der aus einem Satz benannter Bezeichnungen besteht, die als Enumeratorliste bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="81c03-107">An enumeration is a distinct type that consists of a set of named labels called the enumerator list.</span></span>

## <a name="long-description"></a><span data-ttu-id="81c03-108">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="81c03-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="81c03-109">Mit der- `enum` Anweisung können Sie einen stark typisierten Satz von Bezeichnungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="81c03-109">The `enum` statement allows you to create a strongly typed set of labels.</span></span> <span data-ttu-id="81c03-110">Diese Enumeration kann im Code verwendet werden, ohne dass Rechtschreibfehler analysiert oder überprüft werden müssen.</span><span class="sxs-lookup"><span data-stu-id="81c03-110">That enumeration can be used in the code without having to parse or check for spelling errors.</span></span>

<span data-ttu-id="81c03-111">Enumerationen werden intern als ganze Zahlen mit einem Startwert von 0 (null) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="81c03-111">Enumerations are internally represented as integers with a starting value of zero.</span></span> <span data-ttu-id="81c03-112">Der ersten Bezeichnung in der Liste wird der Wert 0 (null) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="81c03-112">The first label in the list is assigned the value zero.</span></span> <span data-ttu-id="81c03-113">Die übrigen Bezeichnungen werden aufeinander folgende Zahlen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="81c03-113">The remaining labels are assigned with consecutive numbers.</span></span>

<span data-ttu-id="81c03-114">In der Definition können Bezeichnungen einen beliebigen ganzzahligen Wert erhalten.</span><span class="sxs-lookup"><span data-stu-id="81c03-114">In the definition, labels can be given any integer value.</span></span> <span data-ttu-id="81c03-115">Bezeichnungen ohne zugewiesenen Wert nehmen den nächsten ganzzahligen Wert an.</span><span class="sxs-lookup"><span data-stu-id="81c03-115">Labels with no value assigned take the next integer value.</span></span>

## <a name="syntax-basic"></a><span data-ttu-id="81c03-116">Syntax (Basic)</span><span class="sxs-lookup"><span data-stu-id="81c03-116">Syntax (basic)</span></span>

```syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

## <a name="usage-example"></a><span data-ttu-id="81c03-117">Verwendungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="81c03-117">Usage example</span></span>

<span data-ttu-id="81c03-118">Das folgende Beispiel zeigt eine Enumeration von-Objekten, die als Mediendateien angesehen werden können.</span><span class="sxs-lookup"><span data-stu-id="81c03-118">The following example shows an enumeration of objects that can be seen as media files.</span></span> <span data-ttu-id="81c03-119">Die-Definition weist den zugrunde liegenden Werten von,, explizite Werte zu `music` `picture` `video` .</span><span class="sxs-lookup"><span data-stu-id="81c03-119">The definition assigns explicit values to the underlying values of `music`, `picture`, `video`.</span></span> <span data-ttu-id="81c03-120">Bezeichnungen, die unmittelbar auf eine explizite Zuweisung folgen, erhalten den nächsten ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="81c03-120">Labels immediately following an explicit assignment get the next integer value.</span></span> <span data-ttu-id="81c03-121">Synonyme können erstellt werden, indem der gleiche Wert einer anderen Bezeichnung zugewiesen wird. sehen Sie sich die erstellten Werte für an: `ogg` , `oga` , `mogg` , oder `jpg` , `jpeg` oder `mpg` `mpeg` .</span><span class="sxs-lookup"><span data-stu-id="81c03-121">Synonyms can be created by assigning the same value to another label; see the constructed values for: `ogg`, `oga`, `mogg`, or `jpg`, `jpeg`, or `mpg`, `mpeg`.</span></span>

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

<span data-ttu-id="81c03-122">Die- `GetEnumNames()` Methode gibt die Liste der Bezeichnungen für die-Enumeration zurück.</span><span class="sxs-lookup"><span data-stu-id="81c03-122">The `GetEnumNames()` method returns the list of the labels for the enumeration.</span></span>

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

<span data-ttu-id="81c03-123">Die- `GetEnumValues()` Methode gibt die Liste der Werte für die-Enumeration zurück.</span><span class="sxs-lookup"><span data-stu-id="81c03-123">The `GetEnumValues()` method returns the list of the values for the enumeration.</span></span>

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

<span data-ttu-id="81c03-124">**Hinweis**: getenumschlag Names () und getenumschlag Values () scheinen die gleichen Ergebnisse zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="81c03-124">**Note**: GetEnumNames() and GetEnumValues() seem to return the same results.</span></span>
<span data-ttu-id="81c03-125">Intern ändert PowerShell jedoch Werte in Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="81c03-125">However, internally, PowerShell is changing values into labels.</span></span> <span data-ttu-id="81c03-126">Lesen Sie die Liste sorgfältig, und Sie werden feststellen, dass `oga` und `mogg` unter den Ergebnissen der Get-Namen aufgeführt werden, aber nicht unter der ähnlichen Ausgabe der Get-Werte für `jpg` , `jpeg` und `mpg` `mpeg` .</span><span class="sxs-lookup"><span data-stu-id="81c03-126">Read the list carefully and you'll notice that `oga` and `mogg` are mentioned under the 'Get Names' results, but not under the 'Get Values' similar output for `jpg`, `jpeg`, and `mpg`, `mpeg`.</span></span>

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

## <a name="enumerations-as-flags"></a><span data-ttu-id="81c03-127">Enumerationen als Flags</span><span class="sxs-lookup"><span data-stu-id="81c03-127">Enumerations as flags</span></span>

<span data-ttu-id="81c03-128">Enumerationen können als eine Auflistung von Bitflags definiert werden.</span><span class="sxs-lookup"><span data-stu-id="81c03-128">Enumerations can be defined as a collection of bit flags.</span></span>
<span data-ttu-id="81c03-129">Dabei stellt die Enumeration an einem beliebigen Punkt ein oder mehrere dieser Flags dar, die aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="81c03-129">Where, at any given point the enumeration represents one or more of those flags turned on.</span></span>

<span data-ttu-id="81c03-130">Damit Enumerationen als Flags ordnungsgemäß funktionieren, sollte jede Bezeichnung eine Potenz von zwei Werten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="81c03-130">For enumerations as flags to work properly, each label should have a power of two value.</span></span>

## <a name="syntax-flags"></a><span data-ttu-id="81c03-131">Syntax (Flags)</span><span class="sxs-lookup"><span data-stu-id="81c03-131">Syntax (flags)</span></span>

```syntax
[Flags()] enum <enum-name> {
    <label 0> [= 1]
    <label 1> [= 2]
    <label 2> [= 4]
    <label 3> [= 8]
    ...
}
```

## <a name="flags-usage-example"></a><span data-ttu-id="81c03-132">Beispiel zur Verwendung von Flags</span><span class="sxs-lookup"><span data-stu-id="81c03-132">Flags usage example</span></span>

<span data-ttu-id="81c03-133">Im folgenden Beispiel wird die *FileAttribute* -Enumeration erstellt.</span><span class="sxs-lookup"><span data-stu-id="81c03-133">In the following example the *FileAttributes* enumeration is created.</span></span>

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

<span data-ttu-id="81c03-134">Um zu testen, ob ein bestimmtes festgelegt ist, können Sie den binären Vergleichs Operator verwenden `-band` .</span><span class="sxs-lookup"><span data-stu-id="81c03-134">To test that a specific is set, you can use the binary comparison operator `-band`.</span></span> <span data-ttu-id="81c03-135">In diesem Beispiel testen wir das **Gerät** und die **Archiv** Attribute im Wert von `$file2` .</span><span class="sxs-lookup"><span data-stu-id="81c03-135">In this example, we test for the **Device** and the **Archive** attributes in the value of `$file2`.</span></span>

```
PS > ($file2 -band [FileAttributes]::Device) -eq [FileAttributes]::Device
True

PS > ($file2 -band [FileAttributes]::Archive) -eq [FileAttributes]::Archive
False
```

