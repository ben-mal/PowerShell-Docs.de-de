---
ms.date: 09/12/2016
ms.topic: reference
title: Festlegen von XML-Versionsnummern für HelpInfo
description: Festlegen von XML-Versionsnummern für HelpInfo
ms.openlocfilehash: 9ef1940ca05d8aa9b04770013287490b71c8065a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658835"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="e5cd4-103">Festlegen von XML-Versionsnummern für HelpInfo</span><span class="sxs-lookup"><span data-stu-id="e5cd4-103">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="e5cd4-104">In diesem Thema wird erläutert, wie die Versionsnummern in einer aktualisierbaren Hilfe Informationsdatei festgelegt und erhöht werden, die häufig als "helpinfo-XML-Datei" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-104">This topic explains how to set and increase the version numbers in an Updatable Help Information file, commonly known as a "HelpInfo XML file."</span></span>

## <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="e5cd4-105">Festlegen von XML-Versionsnummern für HelpInfo</span><span class="sxs-lookup"><span data-stu-id="e5cd4-105">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="e5cd4-106">Die Versionsnummern in einer helpinfo-XML-Datei sind wichtig für den Vorgang der aktualisierbaren Hilfe.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-106">The version numbers in a HelpInfo XML file are critical to the operation of Updatable Help.</span></span> <span data-ttu-id="e5cd4-107">Mit den Cmdlets " [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) " und " [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) " werden neue Hilfedateien nur heruntergeladen, wenn die Versionsnummer für eine Benutzeroberflächen Kultur in der XML-Datei "Remote helpinfo" größer ist als die Versionsnummer für diese Benutzeroberflächen Kultur in der lokalen helpinfo-XML-Datei, oder es gibt keine lokale helpinfo</span><span class="sxs-lookup"><span data-stu-id="e5cd4-107">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets download new help files only when the version number for a UI culture in the remote HelpInfo XML file is greater than the version number for that UI culture in the local HelpInfo XML, or there is no local HelpInfo XML file.</span></span>

<span data-ttu-id="e5cd4-108">Die helpinfo-XML-Datei verwendet die 4-teilige Versionsnummer, die in der **System. Version** -Klasse des Microsoft .NET Frameworks definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-108">The HelpInfo XML file uses the 4-part version number that is defined in the **System.Version** class of the Microsoft .NET Framework.</span></span> <span data-ttu-id="e5cd4-109">Das Format ist `N1.N2.N3.N4`.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-109">The format is `N1.N2.N3.N4`.</span></span> <span data-ttu-id="e5cd4-110">Modul Autoren können ein beliebiges Versionsnummern Schema verwenden, das von der **System. Version** -Klasse zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-110">Module authors can use any version numbering scheme that is permitted by the **System.Version** class.</span></span> <span data-ttu-id="e5cd4-111">Die aktualisierbare Hilfe erfordert nur, dass die Versionsnummer für eine Benutzeroberflächen Kultur zunimmt, wenn eine neue Version der CAB-Datei für die Benutzeroberflächen Kultur an den Speicherort hochgeladen wird, der durch das **helpcontenturi** -Element in der helpinfo-XML-Datei angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-111">Updatable Help requires only that the version number for a UI culture increase when a new version of the CAB file for that UI culture is uploaded to the location that is specified by the **HelpContentURI** element in the HelpInfo XML file.</span></span>

<span data-ttu-id="e5cd4-112">Das folgende Beispiel zeigt die Elemente der helpinfo-XML-Datei für die deutsche Benutzeroberflächen Kultur (de-de), wenn die Version 2.15.0.10 ist.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-112">The following example shows the elements of the HelpInfo XML file for the German (de-DE) UI culture when the version is 2.15.0.10.</span></span>

```xml
<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

<span data-ttu-id="e5cd4-113">Die Versionsnummer für eine Benutzeroberflächen Kultur spiegelt die Version der CAB-Datei für die Benutzeroberflächen Kultur wider.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-113">The version number for a UI culture reflects the version of the CAB file for that UI culture.</span></span> <span data-ttu-id="e5cd4-114">Die Versionsnummer gilt für die gesamte CAB-Datei.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-114">The version number applies to the entire CAB file.</span></span> <span data-ttu-id="e5cd4-115">In der CAB-Datei können keine anderen Versionsnummern für verschiedene Dateien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-115">You cannot set different version numbers for different files in the CAB file.</span></span> <span data-ttu-id="e5cd4-116">Die Versionsnummer für jede Benutzeroberflächen Kultur wird unabhängig ausgewertet und muss nicht mit den Versionsnummern für andere Benutzeroberflächen Kulturen verknüpft sein, die das Modul unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-116">The version number for each UI culture is evaluated independently and need not be related to the version numbers for other UI cultures that the module supports.</span></span>
