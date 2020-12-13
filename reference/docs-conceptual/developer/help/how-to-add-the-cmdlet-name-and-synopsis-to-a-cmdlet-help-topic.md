---
ms.date: 09/13/2016
ms.topic: reference
title: Hinzufügen von Cmdlet-Namen und -Übersicht zu einem Cmdlet-Hilfethema
description: Hinzufügen von Cmdlet-Namen und -Übersicht zu einem Cmdlet-Hilfethema
ms.openlocfilehash: aeeb0cdd1d6d17b88067928ff952dc57a9441917
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659058"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a><span data-ttu-id="717a6-103">Hinzufügen von Cmdlet-Namen und -Übersicht zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="717a6-103">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>

<span data-ttu-id="717a6-104">In diesem Abschnitt wird beschrieben, wie Sie Inhalte hinzufügen, die in den Abschnitten " **Name** " und " **Synopsis** " der Cmdlet-Hilfe angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="717a6-104">This section describes how to add content that is displayed in the **NAME** and **SYNOPSIS** sections of the cmdlet help.</span></span> <span data-ttu-id="717a6-105">In der Hilfedatei wird dieser Inhalt dem Befehls Knoten für jedes Cmdlet hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="717a6-105">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="717a6-106">Eine umfassende Ansicht einer Hilfedatei erhalten Sie, indem Sie eine der `dll-Help.xml` Dateien im PowerShell-Installationsverzeichnis öffnen.</span><span class="sxs-lookup"><span data-stu-id="717a6-106">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="717a6-107">Die `Microsoft.PowerShell.Commands.Management.dll-Help.xml` Datei enthält z. b. Inhalte für mehrere PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="717a6-107">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

## <a name="to-add-the-cmdlet-name-and-a-synopsis"></a><span data-ttu-id="717a6-108">So fügen Sie den Cmdlet-Namen und eine Synchronisierungs Datei hinzu</span><span class="sxs-lookup"><span data-stu-id="717a6-108">To Add the Cmdlet Name and a Synopsis</span></span>

- <span data-ttu-id="717a6-109">Die Cmdlet-Hilfe kann zwei Beschreibungen für das Cmdlet anzeigen.</span><span class="sxs-lookup"><span data-stu-id="717a6-109">The cmdlet Help can display two descriptions for the cmdlet.</span></span> <span data-ttu-id="717a6-110">Die erste Beschreibung ist eine kurze Beschreibung, die als Synopsis bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="717a6-110">The first description is a short description that is referred to as the synopsis.</span></span> <span data-ttu-id="717a6-111">Die zweite Beschreibung ist eine ausführlichere Beschreibung, die im [Thema Hinzufügen der ausführlichen Beschreibung zu einem Cmdlet-Hilfethema](./how-to-add-a-cmdlet-description.md)erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="717a6-111">The second description is a more detailed description that is discussed in [Adding the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>
  <span data-ttu-id="717a6-112">Beide Beschreibungen sollten als einzelner Absatz geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="717a6-112">Both these descriptions should be written as a single paragraph.</span></span>

- <span data-ttu-id="717a6-113">Wiederholen Sie in der Synchronisierungs Datei den Namen des Cmdlets nicht.</span><span class="sxs-lookup"><span data-stu-id="717a6-113">In the synopsis do not repeat the cmdlet name.</span></span> <span data-ttu-id="717a6-114">Der Benutzer wird darüber informiert, dass das `Get-Server` Cmdlet einen Server erhält, aber nicht informativ ist.</span><span class="sxs-lookup"><span data-stu-id="717a6-114">Informing the user that the `Get-Server` cmdlet gets a server is brief, but not informative.</span></span> <span data-ttu-id="717a6-115">Verwenden Sie stattdessen Synonyme, und fügen Sie der Beschreibung Details hinzu.</span><span class="sxs-lookup"><span data-stu-id="717a6-115">Instead, use synonyms and add details to the description.</span></span>

  <span data-ttu-id="717a6-116">Beispiel: "Ruft ein Objekt ab, das einen lokalen oder Remote Computer darstellt."</span><span class="sxs-lookup"><span data-stu-id="717a6-116">Example: "Gets an object that represents a local or remote computer."</span></span>

- <span data-ttu-id="717a6-117">Verwenden Sie einfache Verben wie "Get", "Create" und "Change" in der Synchronisierungs Datei.</span><span class="sxs-lookup"><span data-stu-id="717a6-117">Use simple verbs like "get", "create", and "change" in the synopsis.</span></span> <span data-ttu-id="717a6-118">Vermeiden Sie die Verwendung von "Set", da sie ungenau ist, und achten Sie auf die Verwendung von "ändern".</span><span class="sxs-lookup"><span data-stu-id="717a6-118">Avoid using "set" because it is vague, and fancy words such as "modify."</span></span>

  <span data-ttu-id="717a6-119">Beispiel: "Ruft Informationen über die Authenticode-Signatur in einer Datei ab."</span><span class="sxs-lookup"><span data-stu-id="717a6-119">Example: "Gets information about the Authenticode signature in a file."</span></span>

- <span data-ttu-id="717a6-120">Schreiben Sie in die aktive Sprache.</span><span class="sxs-lookup"><span data-stu-id="717a6-120">Write in active voice.</span></span> <span data-ttu-id="717a6-121">Beispiel: "verwenden Sie das TimeSpan-Objekt..." ist viel klarer als "das TimeSpan-Objekt kann verwendet werden..."</span><span class="sxs-lookup"><span data-stu-id="717a6-121">For example, "Use the TimeSpan object..." is much clearer than "the TimeSpan object can be used to..."</span></span>

- <span data-ttu-id="717a6-122">Vermeiden Sie das Verb "Display", wenn Sie Cmdlets beschreiben, die Objekte erhalten.</span><span class="sxs-lookup"><span data-stu-id="717a6-122">Avoid the verb "display" when describing cmdlets that get objects.</span></span> <span data-ttu-id="717a6-123">Obwohl in Windows PowerShell Cmdlet-Daten angezeigt werden, ist es wichtig, Benutzer zu dem Konzept zu bringen, das vom Cmdlet zurückgegeben wird, .NET Framework Objekte, deren Daten möglicherweise nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="717a6-123">Although Windows PowerShell displays cmdlet data, it is important to introduce users to the concept that the cmdlet returns .NET Framework objects whose data may not be displayed.</span></span> <span data-ttu-id="717a6-124">Wenn Sie die Anzeige hervorheben, erkennt der Benutzer möglicherweise nicht, dass das Cmdlet möglicherweise viele andere nützliche Eigenschaften und Methoden zurückgegeben hat, die nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="717a6-124">If you emphasize the display, the user might not realize that the cmdlet may have returned many other useful properties and methods that are not displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="717a6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="717a6-125">See Also</span></span>

[<span data-ttu-id="717a6-126">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="717a6-126">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
