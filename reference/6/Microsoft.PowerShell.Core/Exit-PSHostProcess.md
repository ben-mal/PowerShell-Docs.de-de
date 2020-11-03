---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 0f076d21ce590b4f1d3eb5b06e891d753dbea638
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200840"
---
# <span data-ttu-id="a218f-103">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="a218f-103">Exit-PSHostProcess</span></span>

## <span data-ttu-id="a218f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a218f-104">SYNOPSIS</span></span>
<span data-ttu-id="a218f-105">Schließt eine interaktive Sitzung mit einem lokalen Prozess.</span><span class="sxs-lookup"><span data-stu-id="a218f-105">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="a218f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a218f-106">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="a218f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a218f-107">DESCRIPTION</span></span>

<span data-ttu-id="a218f-108">Das " **Exit-pshostprocess"-** Cmdlet schließt eine interaktive Sitzung mit einem lokalen Prozess, den Sie durch Ausführen des Cmdlets "Enter-PSHostProcess" geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="a218f-108">The **Exit-PSHostProcess** cmdlet closes an interactive session with a local process that you have opened by running the Enter-PSHostProcess cmdlet.</span></span> <span data-ttu-id="a218f-109">Sie führen das Cmdlet **Exit-pshostprocess** innerhalb des Prozesses aus, wenn Sie das Debuggen abgeschlossen haben oder ein Skript ausführen möchten, das innerhalb eines Prozesses ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a218f-109">You run the **Exit-PSHostProcess** cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span>

## <span data-ttu-id="a218f-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a218f-110">EXAMPLES</span></span>

### <span data-ttu-id="a218f-111">Beispiel 1: Beenden eines Prozesses</span><span class="sxs-lookup"><span data-stu-id="a218f-111">Example 1: Exit a process</span></span>

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

<span data-ttu-id="a218f-112">In diesem Beispiel haben Sie in einem aktiven Prozess gearbeitet, um ein Skript zu debuggen, das in einem Runspace im Prozess ausgeführt wird, wie in Enter-pshostprocess beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a218f-112">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in Enter-PSHostProcess.</span></span> <span data-ttu-id="a218f-113">Nachdem Sie den Befehl **Exit** zum Beenden des Debuggers eingeben haben, führen Sie das Cmdlet **Exit-pshostprocess** aus, um die interaktive Sitzung mit dem Prozess zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a218f-113">After you type the **exit** command to exit the debugger, run the **Exit-PSHostProcess** cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="a218f-114">Das Cmdlet schließt die Sitzung im Prozess und kehrt zur PS C:- \\ \> Eingabeaufforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="a218f-114">The cmdlet closes your session in the process, and returns you to the PS C:\\\> prompt.</span></span>

## <span data-ttu-id="a218f-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a218f-115">PARAMETERS</span></span>

### <span data-ttu-id="a218f-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a218f-116">CommonParameters</span></span>

<span data-ttu-id="a218f-117">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a218f-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a218f-118">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a218f-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a218f-119">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a218f-119">INPUTS</span></span>

## <span data-ttu-id="a218f-120">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a218f-120">OUTPUTS</span></span>

## <span data-ttu-id="a218f-121">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a218f-121">NOTES</span></span>

## <span data-ttu-id="a218f-122">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a218f-122">RELATED LINKS</span></span>

[<span data-ttu-id="a218f-123">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="a218f-123">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)
