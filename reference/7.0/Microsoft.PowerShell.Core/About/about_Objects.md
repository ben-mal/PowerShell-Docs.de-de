---
description: Stellt wichtige Informationen zu Objekten in PowerShell bereit.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: b845dc8b55a19bb642c194398b0c9f5f13d24cb3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223663"
---
# <a name="about-objects"></a><span data-ttu-id="9118e-104">Informationen zu Objekten</span><span class="sxs-lookup"><span data-stu-id="9118e-104">About Objects</span></span>

## <a name="short-description"></a><span data-ttu-id="9118e-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9118e-105">Short Description</span></span>
<span data-ttu-id="9118e-106">Stellt wichtige Informationen zu Objekten in PowerShell bereit.</span><span class="sxs-lookup"><span data-stu-id="9118e-106">Provides essential information about objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="9118e-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9118e-107">Long Description</span></span>

<span data-ttu-id="9118e-108">Jede Aktion, die Sie in PowerShell ausführen, findet innerhalb des Kontexts von Objekten statt.</span><span class="sxs-lookup"><span data-stu-id="9118e-108">Every action you take in PowerShell occurs within the context of objects.</span></span> <span data-ttu-id="9118e-109">Wenn Daten von einem Befehl zum nächsten verschoben werden, werden Sie als ein oder mehrere identifizierbare Objekte verschoben.</span><span class="sxs-lookup"><span data-stu-id="9118e-109">As data moves from one command to the next, it moves as one or more identifiable objects.</span></span> <span data-ttu-id="9118e-110">Bei einem Objekt handelt es sich um eine Auflistung von Daten, die ein Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="9118e-110">An object, then, is a collection of data that represents an item.</span></span> <span data-ttu-id="9118e-111">Ein Objekt besteht aus drei Datentypen: dem Objekttyp, seinen Methoden und seinen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9118e-111">An object is made up of three types of data: the objects type, its methods, and its properties.</span></span>

## <a name="types-methods-and-properties"></a><span data-ttu-id="9118e-112">Typen, Methoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9118e-112">Types, Methods, and Properties</span></span>

<span data-ttu-id="9118e-113">Der Objekttyp gibt an, welche Art von Objekt es ist.</span><span class="sxs-lookup"><span data-stu-id="9118e-113">The object type tells what kind of object it is.</span></span> <span data-ttu-id="9118e-114">Beispielsweise ist ein Objekt, das eine Datei darstellt, ein FileInfo-Objekt.</span><span class="sxs-lookup"><span data-stu-id="9118e-114">For example, an object that represents a file is a FileInfo object.</span></span>

<span data-ttu-id="9118e-115">Die Objektmethoden sind Aktionen, die Sie für das-Objekt ausführen können.</span><span class="sxs-lookup"><span data-stu-id="9118e-115">The object methods are actions that you can perform on the object.</span></span>
<span data-ttu-id="9118e-116">Beispielsweise verfügen FileInfo-Objekte über eine CopyTo-Methode, die Sie zum Kopieren der Datei verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9118e-116">For example, FileInfo objects have a CopyTo method that you can use to copy the file.</span></span>

<span data-ttu-id="9118e-117">Objekteigenschaften speichern Informationen über das Objekt.</span><span class="sxs-lookup"><span data-stu-id="9118e-117">Object properties store information about the object.</span></span> <span data-ttu-id="9118e-118">Beispielsweise verfügen FileInfo-Objekte über eine LastWrite Time-Eigenschaft, die das Datum und die Uhrzeit speichert, zu der die Datei zuletzt aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="9118e-118">For example, FileInfo objects have a LastWriteTime property that stores the date and time that the file was most recently accessed.</span></span>

<span data-ttu-id="9118e-119">Beim Arbeiten mit-Objekten können Sie Ihre Methoden und Eigenschaften in Befehlen verwenden, um Maßnahmen zu ergreifen und Daten zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9118e-119">When working with objects, you can use their methods and properties in commands to take action and manage data.</span></span>

## <a name="objects-in-pipelines"></a><span data-ttu-id="9118e-120">Objekte in Pipelines</span><span class="sxs-lookup"><span data-stu-id="9118e-120">Objects in Pipelines</span></span>

<span data-ttu-id="9118e-121">Wenn Befehle in einer Pipeline kombiniert werden, übergeben Sie Informationen als Objekte an einander.</span><span class="sxs-lookup"><span data-stu-id="9118e-121">When commands are combined in a pipeline, they pass information to each other as objects.</span></span> <span data-ttu-id="9118e-122">Wenn der erste Befehl ausgeführt wird, sendet er ein oder mehrere Objekte in der Pipeline an den zweiten Befehl.</span><span class="sxs-lookup"><span data-stu-id="9118e-122">When the first command runs, it sends one or more objects down the pipeline to the second command.</span></span> <span data-ttu-id="9118e-123">Der zweite Befehl empfängt die Objekte vom ersten Befehl, verarbeitet die Objekte und übergibt dann neue oder überarbeitete Objekte an den nächsten Befehl in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="9118e-123">The second command receives the objects from the first command, processes the objects, and then passes new or revised objects to the next command in the pipeline.</span></span>
<span data-ttu-id="9118e-124">Dies wird fortgesetzt, bis alle Befehle in der Pipeline ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9118e-124">This continues until all commands in the pipeline run.</span></span>

<span data-ttu-id="9118e-125">Im folgenden Beispiel wird veranschaulicht, wie-Objekte von einem Befehl an den nächsten übermittelt werden:</span><span class="sxs-lookup"><span data-stu-id="9118e-125">The following example demonstrates how objects are passed from one command to the next:</span></span>

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

<span data-ttu-id="9118e-126">Der erste Befehl `Get-ChildItem C:` gibt ein Datei-oder Verzeichnis Objekt für jedes Element im Stammverzeichnis des Dateisystems zurück.</span><span class="sxs-lookup"><span data-stu-id="9118e-126">The first command `Get-ChildItem C:` returns a file or directory object for each item in the root directory of the file system.</span></span> <span data-ttu-id="9118e-127">Die Datei-und Verzeichnisobjekte werden über die Pipeline an den zweiten Befehl übermittelt.</span><span class="sxs-lookup"><span data-stu-id="9118e-127">The file and directory objects are passed down the pipeline to the second command.</span></span>

<span data-ttu-id="9118e-128">Der zweite Befehl `where { $_.PsIsContainer -eq $false }` verwendet die psiscontainer-Eigenschaft aller Dateisystem Objekte, um nur Dateien auszuwählen, deren psiscontainer-Eigenschaft den Wert false ( \$ false) hat.</span><span class="sxs-lookup"><span data-stu-id="9118e-128">The second command `where { $_.PsIsContainer -eq $false }` uses the PsIsContainer property of all file system objects to select only files, which have a value of False (\$false) in their PsIsContainer property.</span></span> <span data-ttu-id="9118e-129">Ordner, bei denen es sich um Container handelt und \$ deren psiscontainer-Eigenschaft den Wert true (true) hat, werden nicht ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="9118e-129">Folders, which are containers and, thus, have a value of True (\$true) in their PsIsContainer property, are not selected.</span></span>

<span data-ttu-id="9118e-130">Mit dem zweiten Befehl werden nur die Datei Objekte an den dritten Befehl weitergeleitet `Format-List` , der die Datei Objekte in einer Liste anzeigt.</span><span class="sxs-lookup"><span data-stu-id="9118e-130">The second command passes only the file objects to the third command `Format-List`, which displays the file objects in a list.</span></span>

## <a name="see-also"></a><span data-ttu-id="9118e-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9118e-131">See Also</span></span>

[<span data-ttu-id="9118e-132">about_Methods</span><span class="sxs-lookup"><span data-stu-id="9118e-132">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="9118e-133">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="9118e-133">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="9118e-134">about_Properties</span><span class="sxs-lookup"><span data-stu-id="9118e-134">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="9118e-135">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="9118e-135">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="9118e-136">Get-Member</span><span class="sxs-lookup"><span data-stu-id="9118e-136">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
