---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: c61d6278-02a3-4618-ae37-a524d40a7f44
Module Name: PSDiagnostics
ms.date: 11/27/2018
schema: 2.0.0
title: Psdiagnostics-Modul
ms.openlocfilehash: f8426e88af9e498c484ed449c2cb1b4695c1a01c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599225"
---
# <span data-ttu-id="8f3e9-102">Psdiagnostics-Modul</span><span class="sxs-lookup"><span data-stu-id="8f3e9-102">PSDiagnostics Module</span></span>

## <span data-ttu-id="8f3e9-103">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8f3e9-103">Description</span></span>

<span data-ttu-id="8f3e9-104">Das PowerShell-Diagnose Modul enthält eine Reihe von Cmdlets, die die Verwendung der etw-Ablauf Verfolgung in PowerShell unter Windows ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-104">The PowerShell Diagnostics Module contains a set of cmdlets that enables the use of ETW tracing in PowerShell on Windows.</span></span>

## <span data-ttu-id="8f3e9-105">Psdiagnostics-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8f3e9-105">PSDiagnostics Cmdlets</span></span>

### [<span data-ttu-id="8f3e9-106">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="8f3e9-106">Disable-PSTrace</span></span>](Disable-PSTrace.md)
<span data-ttu-id="8f3e9-107">Deaktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-107">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

### [<span data-ttu-id="8f3e9-108">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="8f3e9-108">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
<span data-ttu-id="8f3e9-109">Hält die Protokollierungs Sitzung an, die von enable-pslismancombinedtrace gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-109">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

### [<span data-ttu-id="8f3e9-110">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="8f3e9-110">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
<span data-ttu-id="8f3e9-111">Stoppt die von enable-wsmantrace gestartete WSMAN-Protokollierungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-111">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

### [<span data-ttu-id="8f3e9-112">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="8f3e9-112">Enable-PSTrace</span></span>](Enable-PSTrace.md)
<span data-ttu-id="8f3e9-113">Aktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-113">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

### [<span data-ttu-id="8f3e9-114">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="8f3e9-114">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
<span data-ttu-id="8f3e9-115">Starten Sie eine Protokollierungs Sitzung mit aktiviertem WSMAN und PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-115">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

### [<span data-ttu-id="8f3e9-116">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="8f3e9-116">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
<span data-ttu-id="8f3e9-117">Starten Sie eine Protokollierungs Sitzung mit aktivierten WSMAN-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-117">Start a logging session with the WSMan providers enabled.</span></span>

### [<span data-ttu-id="8f3e9-118">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="8f3e9-118">Get-LogProperties</span></span>](Get-LogProperties.md)
<span data-ttu-id="8f3e9-119">Ruft die Eigenschaften eines Windows-Ereignis Protokolls ab.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-119">Retrieves the properties of a Windows event log.</span></span>

### [<span data-ttu-id="8f3e9-120">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="8f3e9-120">Set-LogProperties</span></span>](Set-LogProperties.md)
<span data-ttu-id="8f3e9-121">Ändert die Eigenschaften eines Windows-Ereignis Protokolls.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-121">Changes the properties of a Windows event log.</span></span>

### [<span data-ttu-id="8f3e9-122">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="8f3e9-122">Start-Trace</span></span>](Start-Trace.md)
<span data-ttu-id="8f3e9-123">Startet eine Protokollierungs Sitzung der Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-123">Start an Event Trace logging session.</span></span>

### [<span data-ttu-id="8f3e9-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="8f3e9-124">Stop-Trace</span></span>](Stop-Trace.md)
<span data-ttu-id="8f3e9-125">Beenden Sie eine Sitzung zur Protokollierung der Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-125">Stop an Event Trace logging session.</span></span>

