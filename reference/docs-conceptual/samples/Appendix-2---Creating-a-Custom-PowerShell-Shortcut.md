---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Anhang 2 – Erstellen einer benutzerdefinierten PowerShell-Verknüpfung
description: In der folgenden Vorgehensweise wird beschrieben, wie Sie eine Verknüpfung zu Windows PowerShell erstellen, in der mehrere praktische Optionen angepasst sind.
ms.openlocfilehash: abdab517dec1357050bf431b6f2e35311ad49976
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500724"
---
# <a name="appendix-2---creating-a-custom-powershell-shortcut"></a><span data-ttu-id="2e829-104">Anhang 2: Erstellen einer benutzerdefinierten PowerShell-Verknüpfung</span><span class="sxs-lookup"><span data-stu-id="2e829-104">Appendix 2 - Creating a Custom PowerShell Shortcut</span></span>

<span data-ttu-id="2e829-105">In der folgenden Vorgehensweise wird beschrieben, wie Sie eine Verknüpfung zu Windows PowerShell erstellen, in der mehrere praktische Optionen angepasst sind.</span><span class="sxs-lookup"><span data-stu-id="2e829-105">The following procedure describes how to create a shortcut to Windows PowerShell that has several convenient options customized.</span></span>

1. <span data-ttu-id="2e829-106">Erstellen Sie eine Verknüpfung, die auf „Powershell.exe“ verweist.</span><span class="sxs-lookup"><span data-stu-id="2e829-106">Create a shortcut that points to Powershell.exe.</span></span>

1. <span data-ttu-id="2e829-107">Klicken Sie mit der rechten Maustaste auf die Verknüpfung, und klicken Sie dann auf **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="2e829-107">Right-click the shortcut, and then click **Properties** .</span></span>

1. <span data-ttu-id="2e829-108">Klicken Sie auf die Registerkarte **Options** .</span><span class="sxs-lookup"><span data-stu-id="2e829-108">Click the **Options** tab.</span></span>

1. <span data-ttu-id="2e829-109">Aktivieren Sie im Abschnitt **Bearbeitungsoptionen** das Kontrollkästchen **QuickEdit** .</span><span class="sxs-lookup"><span data-stu-id="2e829-109">In the **Edit Options** section, select the **QuickEdit** check box.</span></span>

    <span data-ttu-id="2e829-110">Diese Einstellung ermöglicht es Ihnen, Text im Windows PowerShell-Konsolenfenster durch Ziehen bei gedrückter linker Maustaste zu markieren sowie Text in die Zwischenablage zu kopieren, indem Sie die EINGABETASTE drücken oder mit der rechten Maustaste klicken.</span><span class="sxs-lookup"><span data-stu-id="2e829-110">This setting lets you select text in the Windows PowerShell console window by dragging the left  mouse button, and it lets you copy text to the clipboard by pressing ENTER or by right-clicking  the mouse.</span></span>

1. <span data-ttu-id="2e829-111">Aktivieren Sie im Abschnitt **Bearbeitungsoptionen** das Kontrollkästchen **Einfügemodus** .</span><span class="sxs-lookup"><span data-stu-id="2e829-111">In the **Edit Options** section, select the **Insert Mode** check box.</span></span> <span data-ttu-id="2e829-112">Diese Einstellung ermöglicht es Ihnen, Text aus der Zwischenablage automatisch durch Klicken mit der rechten Maustaste im Konsolenfenster einzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e829-112">This setting lets you right-click in the console window to automatically paste text from the clipboard.</span></span>

1. <span data-ttu-id="2e829-113">Geben Sie im Abschnitt **Befehlsspeicher** direkt oder durch Auswählen eine Zahl zwischen 1 und 999 in das Feld **Puffergröße** ein.</span><span class="sxs-lookup"><span data-stu-id="2e829-113">In the **Command History** section, type or select a number between 1 and 999 in the **Buffer Size** box.</span></span> <span data-ttu-id="2e829-114">Hiermit wird die Anzahl von eingegebenen Befehlen festgelegt, die im Konsolenpuffer aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="2e829-114">This sets the number of typed commands that will be kept in the console buffer.</span></span>

1. <span data-ttu-id="2e829-115">Aktivieren Sie im Abschnitt **Befehlsspeicher** das Kontrollkästchen **Alte Duplikate löschen** , damit wiederholte Befehle aus dem Konsolenpuffer entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="2e829-115">In the **Command History** section, select the **Discard Old Duplicates** check box to eliminate repeated commands from the console buffer.</span></span>

1. <span data-ttu-id="2e829-116">Klicken Sie auf die Registerkarte **Layout** .</span><span class="sxs-lookup"><span data-stu-id="2e829-116">Click the **Layout** tab.</span></span>

1. <span data-ttu-id="2e829-117">Geben Sie im Abschnitt **Fensterpuffergröße** eine Zahl zwischen 1 und 9999 in das Feld **Höhe** ein.</span><span class="sxs-lookup"><span data-stu-id="2e829-117">In the **Screen Buffer** section, type a number between 1 and 9999 in the **Height** box.</span></span> <span data-ttu-id="2e829-118">Diese Höhe entspricht der Anzahl von Ausgabezeilen, die gepuffert werden.</span><span class="sxs-lookup"><span data-stu-id="2e829-118">The height represents the number of lines of output that are buffered.</span></span> <span data-ttu-id="2e829-119">Dies ist die maximale Anzahl von Zeilen, die für die Anzeige beibehalten werden, wenn Sie durch das Konsolenfenster scrollen.</span><span class="sxs-lookup"><span data-stu-id="2e829-119">This is the maximum number of lines retained for viewing when you scroll through the console window.</span></span> <span data-ttu-id="2e829-120">Ist diese Anzahl kleiner als der Wert für die Höhenangabe im Abschnitt **Fenstergröße** , wird die Fensterhöhe automatisch auf denselben Wert verringert.</span><span class="sxs-lookup"><span data-stu-id="2e829-120">If this number is lower than the height shown in the **Window size** section, the window size height will automatically be reduced to the same value.</span></span>

1. <span data-ttu-id="2e829-121">Geben Sie im Abschnitt **Fenstergröße** eine Zahl zwischen 1 und 9999 für die Breite ein.</span><span class="sxs-lookup"><span data-stu-id="2e829-121">In the **Window Size** section, type a number between 1 and 9999 for the width.</span></span> <span data-ttu-id="2e829-122">Diese Zahl entspricht der Anzahl von Zeichen, die horizontal im Konsolenfenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2e829-122">This represents the number of characters that are displayed across the console window.</span></span> <span data-ttu-id="2e829-123">Die Standardbreite beträgt 80, und die Ausgabeformatierung von Windows PowerShell ist für diese Breite konzipiert.</span><span class="sxs-lookup"><span data-stu-id="2e829-123">The default width is 80, and Windows PowerShell's output formatting is designed for this width.</span></span>

1. <span data-ttu-id="2e829-124">Wenn Sie die Konsole beim Öffnen an einer bestimmten Stelle auf dem Desktop platzieren möchten, deaktivieren Sie im Abschnitt **Fensterposition** das Kontrollkästchen **Automatisch positionieren** , und ändern Sie die Werte in den Feldern **Links** und **Oben** im Abschnitt **Fensterposition** .</span><span class="sxs-lookup"><span data-stu-id="2e829-124">If you want to place the console at a particular point on the desktop when it is opened, clear  the **Let system position window** check box in the **Window position** section, and then change  the values in the **Left** and **Top** boxes in the **Window position** section.</span></span>

1. <span data-ttu-id="2e829-125">Klicken Sie auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="2e829-125">Click **OK** .</span></span>
