---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen einer Formatierungsdatei (.format.ps1xml)
description: Erstellen einer Formatierungsdatei (.format.ps1xml)
ms.openlocfilehash: 5bbc1ba40bfccf13636abc0f0751938aa724b761
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652003"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="12e7f-103">Erstellen einer Formatierungsdatei (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="12e7f-103">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="12e7f-104">In diesem Thema wird beschrieben, wie eine Formatierungs Datei (.format.ps1XML) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="12e7f-104">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="12e7f-105">Sie können auch eine Formatierungs Datei erstellen, indem Sie eine Kopie einer der von Windows PowerShell bereitgestellten Dateien erstellen.</span><span class="sxs-lookup"><span data-stu-id="12e7f-105">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="12e7f-106">Wenn Sie eine Kopie einer vorhandenen Datei erstellen, löschen Sie die vorhandene digitale Signatur, und fügen Sie der neuen Datei Ihre eigene Signatur hinzu.</span><span class="sxs-lookup"><span data-stu-id="12e7f-106">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="12e7f-107">Zum Erstellen einer .format.ps1-XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="12e7f-107">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="12e7f-108">Erstellen Sie eine Textdatei (. txt) mit einem Text-Editor, z. b. Notepad.</span><span class="sxs-lookup"><span data-stu-id="12e7f-108">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="12e7f-109">Kopieren Sie die folgenden Zeilen in die Formatierungs Datei.</span><span class="sxs-lookup"><span data-stu-id="12e7f-109">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="12e7f-110">Die `<Configuration></Configuration>` Tags definieren den Stamm `Configuration` Knoten.</span><span class="sxs-lookup"><span data-stu-id="12e7f-110">The `<Configuration></Configuration>` tags define the root `Configuration` node.</span></span> <span data-ttu-id="12e7f-111">Alle zusätzlichen XML-Tags werden in diesen Knoten eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="12e7f-111">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="12e7f-112">Die `<ViewDefinitions></ViewDefinitions>` Tags definieren den `ViewDefinitions` Knoten.</span><span class="sxs-lookup"><span data-stu-id="12e7f-112">The `<ViewDefinitions></ViewDefinitions>` tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="12e7f-113">Alle Sichten werden innerhalb dieses Knotens definiert.</span><span class="sxs-lookup"><span data-stu-id="12e7f-113">All views are defined within this node.</span></span>

3. <span data-ttu-id="12e7f-114">Speichern Sie die Datei im Installationsordner von Windows PowerShell, in Ihrem Modul Ordner oder in einem Unterordner des Modul Ordners.</span><span class="sxs-lookup"><span data-stu-id="12e7f-114">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="12e7f-115">Verwenden Sie das folgende Namensformat, wenn Sie die Datei speichern:  `MyFile.format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="12e7f-115">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="12e7f-116">Beim Formatieren von Dateien muss die Erweiterung verwendet werden `.format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="12e7f-116">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="12e7f-117">Nun können Sie der Formatierungs Datei Ansichten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="12e7f-117">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="12e7f-118">Es gibt keine Beschränkung für die Anzahl der Sichten, die in einer Formatierungs Datei definiert werden können.</span><span class="sxs-lookup"><span data-stu-id="12e7f-118">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="12e7f-119">Sie können eine einzelne Ansicht für jedes Objekt, mehrere Ansichten für dasselbe Objekt oder eine einzelne Ansicht hinzufügen, die von mehreren Objekten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="12e7f-119">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="12e7f-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12e7f-120">See Also</span></span>

[<span data-ttu-id="12e7f-121">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="12e7f-121">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
