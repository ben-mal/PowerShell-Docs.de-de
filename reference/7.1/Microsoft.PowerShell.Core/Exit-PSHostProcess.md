---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 368d29b7cdcbe2725399da0896eed87ddb372236
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342143"
---
# <span data-ttu-id="9b04b-103">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="9b04b-103">Exit-PSHostProcess</span></span>

## <span data-ttu-id="9b04b-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9b04b-104">SYNOPSIS</span></span>
<span data-ttu-id="9b04b-105">Schließt eine interaktive Sitzung mit einem lokalen Prozess.</span><span class="sxs-lookup"><span data-stu-id="9b04b-105">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="9b04b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9b04b-106">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="9b04b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b04b-107">DESCRIPTION</span></span>

<span data-ttu-id="9b04b-108">Das `Exit-PSHostProcess` Cmdlet schließt eine interaktive Sitzung mit einem lokalen Prozess, den Sie durch Ausführen des `Enter-PSHostProcess` Cmdlets geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="9b04b-108">The `Exit-PSHostProcess` cmdlet closes an interactive session with a local process that you have opened by running the `Enter-PSHostProcess` cmdlet.</span></span> <span data-ttu-id="9b04b-109">Sie führen das `Exit-PSHostProcess` Cmdlet innerhalb des Prozesses aus, wenn Sie das Debuggen oder die Problembehandlung eines Skripts abgeschlossen haben, das innerhalb eines Prozesses ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9b04b-109">You run the `Exit-PSHostProcess` cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span> <span data-ttu-id="9b04b-110">Ab PowerShell 6,2 wird dieses Cmdlet auf nicht-Windows-Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9b04b-110">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="9b04b-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9b04b-111">EXAMPLES</span></span>

### <span data-ttu-id="9b04b-112">Beispiel 1: Beenden eines Prozesses</span><span class="sxs-lookup"><span data-stu-id="9b04b-112">Example 1: Exit a process</span></span>

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

<span data-ttu-id="9b04b-113">In diesem Beispiel haben Sie in einem aktiven Prozess gearbeitet, um ein Skript zu debuggen, das in einem Runspace im Prozess ausgeführt wird, wie unter beschrieben `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="9b04b-113">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in `Enter-PSHostProcess`.</span></span> <span data-ttu-id="9b04b-114">Nachdem Sie den `exit` Befehl zum Beenden des Debuggers eingeben haben, führen Sie das `Exit-PSHostProcess` Cmdlet aus, um die interaktive Sitzung mit dem Prozess zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9b04b-114">After you type the `exit` command to exit the debugger, run the `Exit-PSHostProcess` cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="9b04b-115">Das Cmdlet schließt die Sitzung im Prozess und kehrt zur `PS C:\>` Eingabeaufforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="9b04b-115">The cmdlet closes your session in the process, and returns you to the `PS C:\>` prompt.</span></span>

## <span data-ttu-id="9b04b-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9b04b-116">PARAMETERS</span></span>

### <span data-ttu-id="9b04b-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9b04b-117">CommonParameters</span></span>

<span data-ttu-id="9b04b-118">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9b04b-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9b04b-119">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9b04b-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9b04b-120">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9b04b-120">INPUTS</span></span>

## <span data-ttu-id="9b04b-121">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9b04b-121">OUTPUTS</span></span>

## <span data-ttu-id="9b04b-122">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9b04b-122">NOTES</span></span>

## <span data-ttu-id="9b04b-123">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9b04b-123">RELATED LINKS</span></span>

[<span data-ttu-id="9b04b-124">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="9b04b-124">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)

