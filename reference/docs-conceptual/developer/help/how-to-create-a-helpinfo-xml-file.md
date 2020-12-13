---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen einer XML-Datei HelpInfo
description: Erstellen einer XML-Datei HelpInfo
ms.openlocfilehash: d5a24306aa6488fdefad0b7b1ea9e2978a93a7b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647718"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a><span data-ttu-id="fe32d-103">Erstellen einer XML-Datei HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fe32d-103">How to Create a HelpInfo XML File</span></span>

<span data-ttu-id="fe32d-104">In diesen Themen in diesem Abschnitt wird erläutert, wie Sie eine Hilfe Informationsdatei erstellen und Auffüllen, die im Allgemeinen als "helpinfo-XML-Datei" bezeichnet wird, um das PowerShell-Feature zur aktualisierbaren Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fe32d-104">This topics in this section explains how to create and populate a help information file, commonly known as a "HelpInfo XML file," for the PowerShell Updatable Help feature.</span></span>

## <a name="helpinfo-xml-file-overview"></a><span data-ttu-id="fe32d-105">Hilfe zur helpinfo-XML-Datei</span><span class="sxs-lookup"><span data-stu-id="fe32d-105">HelpInfo XML File Overview</span></span>

<span data-ttu-id="fe32d-106">Die helpinfo-XML-Datei ist die primäre Quelle von Informationen über die aktualisierbare Hilfe für das Modul.</span><span class="sxs-lookup"><span data-stu-id="fe32d-106">The HelpInfo XML file is the primary source of information about Updatable Help for the module.</span></span> <span data-ttu-id="fe32d-107">Sie enthält den Speicherort der Hilfedateien für die Module, die unterstützten Benutzeroberflächen Kulturen und die Versionsnummern, die von der aktualisierbaren Hilfe verwendet werden, um zu bestimmen, ob der Benutzer über die neuesten Hilfedateien verfügt.</span><span class="sxs-lookup"><span data-stu-id="fe32d-107">It includes the location of the help files for the modules, the supported UI cultures, and the version numbers that Updatable Help uses to determine whether the user has the newest help files.</span></span>

<span data-ttu-id="fe32d-108">Jedes Modul verfügt nur über eine helpinfo-XML-Datei, auch wenn das Modul mehrere Hilfedateien für mehrere Benutzeroberflächen Kulturen enthält.</span><span class="sxs-lookup"><span data-stu-id="fe32d-108">Each module has just one HelpInfo XML file, even if the module includes multiple help files for multiple UI cultures.</span></span> <span data-ttu-id="fe32d-109">Der Modul Autor erstellt die helpinfo-XML-Datei und legt Sie an dem Internet Speicherort ab, der durch den **helpinfouri** -Schlüssel im Modul Manifest angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fe32d-109">The module author creates the HelpInfo XML file and places it in the internet location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="fe32d-110">Wenn die Modul Hilfedateien aktualisiert und hochgeladen werden, aktualisiert der Modul Autor die helpinfo-XML-Datei und ersetzt die ursprüngliche helpinfo-XML-Datei durch die neue Version.</span><span class="sxs-lookup"><span data-stu-id="fe32d-110">When the module help files are updated and uploaded, the module author updates the HelpInfo XML file and replaces the original HelpInfo XML file with the new version.</span></span>

<span data-ttu-id="fe32d-111">Es ist wichtig, dass die helpinfo-XML-Datei sorgfältig verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="fe32d-111">It is critical that the HelpInfo XML file is carefully maintained.</span></span> <span data-ttu-id="fe32d-112">Wenn Sie neue Dateien hochladen, aber vergessen, die Versionsnummern zu erhöhen, werden die neuen Dateien von der aktualisierbaren Hilfe nicht auf die Benutzer Computer heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="fe32d-112">If you upload new files, but forget to increment the version numbers, Updatable Help will not download the new files to users' computers.</span></span> <span data-ttu-id="fe32d-113">Wenn Sie Hilfedateien für eine neue Benutzeroberflächen Kultur hinzufügen, aber die helpinfo-XML-Datei nicht aktualisieren oder am richtigen Speicherort platzieren, werden die neuen Dateien durch die aktualisierbare Hilfe nicht heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="fe32d-113">if you add help files for a new UI culture, but don't update the HelpInfo XML file or place it in the correct location, Updatable Help will not download the new files.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="fe32d-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fe32d-114">In this section</span></span>

<span data-ttu-id="fe32d-115">In diesem Abschnitt werden folgende Themen behandelt.</span><span class="sxs-lookup"><span data-stu-id="fe32d-115">This section includes the following topics.</span></span>

- [<span data-ttu-id="fe32d-116">XML-Schema von HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fe32d-116">HelpInfo XML Schema</span></span>](./helpinfo-xml-schema.md)

- [<span data-ttu-id="fe32d-117">XML-Beispieldatei HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fe32d-117">HelpInfo XML Sample File</span></span>](./helpinfo-xml-sample-file.md)

- [<span data-ttu-id="fe32d-118">Benennen einer XML-Datei HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fe32d-118">How to Name a HelpInfo XML File</span></span>](./how-to-name-a-helpinfo-xml-file.md)

- [<span data-ttu-id="fe32d-119">Festlegen von XML-Versionsnummern für HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fe32d-119">How to Set HelpInfo XML Version Numbers</span></span>](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a><span data-ttu-id="fe32d-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe32d-120">See Also</span></span>

[<span data-ttu-id="fe32d-121">Unterstützung einer aktualisierbaren Hilfe</span><span class="sxs-lookup"><span data-stu-id="fe32d-121">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)
