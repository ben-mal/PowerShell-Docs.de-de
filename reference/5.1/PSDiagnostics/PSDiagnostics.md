---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=855965
Help Version: 5.2.0.0
keywords: powershell,cmdlet
Locale: en-US
Module Guid: c61d6278-02a3-4618-ae37-a524d40a7f44
Module Name: PSDiagnostics
ms.date: 11/27/2018
schema: 2.0.0
title: Psdiagnostics-Modul
ms.openlocfilehash: 7261b46fb0c15ac128be9897503c7a6bb7d5fccc
ms.sourcegitcommit: 3571b9e87e8881adbf7984cda46a63891039a987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "93209641"
---
# <span data-ttu-id="ce16d-103">Psdiagnostics-Modul</span><span class="sxs-lookup"><span data-stu-id="ce16d-103">PSDiagnostics Module</span></span>

## <span data-ttu-id="ce16d-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ce16d-104">Description</span></span>

<span data-ttu-id="ce16d-105">Das PowerShell-Diagnose Modul enthält eine Reihe von Cmdlets, die die Verwendung der etw-Ablauf Verfolgung in PowerShell unter Windows ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ce16d-105">The PowerShell Diagnostics Module contains a set of cmdlets that enables the use of ETW tracing in PowerShell on Windows.</span></span>

## <span data-ttu-id="ce16d-106">Psdiagnostics-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ce16d-106">PSDiagnostics Cmdlets</span></span>

### [<span data-ttu-id="ce16d-107">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="ce16d-107">Disable-PSTrace</span></span>](Disable-PSTrace.md)
<span data-ttu-id="ce16d-108">Deaktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="ce16d-108">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

### [<span data-ttu-id="ce16d-109">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="ce16d-109">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
<span data-ttu-id="ce16d-110">Hält die Protokollierungs Sitzung an, die von enable-pslismancombinedtrace gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="ce16d-110">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

### [<span data-ttu-id="ce16d-111">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="ce16d-111">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
<span data-ttu-id="ce16d-112">Stoppt die von enable-wsmantrace gestartete WSMAN-Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="ce16d-112">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

### [<span data-ttu-id="ce16d-113">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="ce16d-113">Enable-PSTrace</span></span>](Enable-PSTrace.md)
<span data-ttu-id="ce16d-114">Aktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="ce16d-114">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

### [<span data-ttu-id="ce16d-115">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="ce16d-115">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
<span data-ttu-id="ce16d-116">Starten Sie eine Protokollierungs Sitzung mit aktiviertem WSMAN und PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="ce16d-116">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

### [<span data-ttu-id="ce16d-117">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="ce16d-117">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
<span data-ttu-id="ce16d-118">Starten Sie eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="ce16d-118">Start a logging session with the WSMan providers enabled.</span></span>

### [<span data-ttu-id="ce16d-119">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="ce16d-119">Get-LogProperties</span></span>](Get-LogProperties.md)
<span data-ttu-id="ce16d-120">Ruft die Eigenschaften eines Windows-Ereignis Protokolls ab.</span><span class="sxs-lookup"><span data-stu-id="ce16d-120">Retrieves the properties of a Windows event log.</span></span>

### [<span data-ttu-id="ce16d-121">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="ce16d-121">Set-LogProperties</span></span>](Set-LogProperties.md)
<span data-ttu-id="ce16d-122">Ändert die Eigenschaften eines Windows-Ereignis Protokolls.</span><span class="sxs-lookup"><span data-stu-id="ce16d-122">Changes the properties of a Windows event log.</span></span>

### [<span data-ttu-id="ce16d-123">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="ce16d-123">Start-Trace</span></span>](Start-Trace.md)
<span data-ttu-id="ce16d-124">Startet eine Protokollierungs Sitzung der Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="ce16d-124">Start an Event Trace logging session.</span></span>

### [<span data-ttu-id="ce16d-125">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="ce16d-125">Stop-Trace</span></span>](Stop-Trace.md)
<span data-ttu-id="ce16d-126">Beenden Sie eine Sitzung zur Protokollierung der Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="ce16d-126">Stop an Event Trace logging session.</span></span>
