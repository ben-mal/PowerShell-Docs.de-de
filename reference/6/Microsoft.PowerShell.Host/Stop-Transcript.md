---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 5f02f59e778c55b2292bb4533cf2f8aaab2dbb7d
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200779"
---
# <span data-ttu-id="dfa1d-103">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="dfa1d-103">Stop-Transcript</span></span>

## <span data-ttu-id="dfa1d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dfa1d-104">SYNOPSIS</span></span>
<span data-ttu-id="dfa1d-105">Beendet eine Aufzeichnung.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-105">Stops a transcript.</span></span>

## <span data-ttu-id="dfa1d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dfa1d-106">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="dfa1d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dfa1d-107">DESCRIPTION</span></span>

<span data-ttu-id="dfa1d-108">Das- `Stop-Transcript` Cmdlet beendet eine Aufzeichnung, die vom `Start-Transcript` Cmdlet gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-108">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="dfa1d-109">Alternativ können Sie eine Sitzung beenden, um eine Aufzeichnung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-109">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="dfa1d-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dfa1d-110">EXAMPLES</span></span>

### <span data-ttu-id="dfa1d-111">Beispiel 1: alle Transkriptionen Abbrechen</span><span class="sxs-lookup"><span data-stu-id="dfa1d-111">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="dfa1d-112">Dieser Befehl beendet alle Transkriptionen.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-112">This command stops all transcripts.</span></span>

## <span data-ttu-id="dfa1d-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dfa1d-113">PARAMETERS</span></span>

### <span data-ttu-id="dfa1d-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dfa1d-114">CommonParameters</span></span>

<span data-ttu-id="dfa1d-115">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dfa1d-116">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dfa1d-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dfa1d-117">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dfa1d-117">INPUTS</span></span>

### <span data-ttu-id="dfa1d-118">Keine</span><span class="sxs-lookup"><span data-stu-id="dfa1d-118">None</span></span>

<span data-ttu-id="dfa1d-119">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-119">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="dfa1d-120">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dfa1d-120">OUTPUTS</span></span>

### <span data-ttu-id="dfa1d-121">System.String</span><span class="sxs-lookup"><span data-stu-id="dfa1d-121">System.String</span></span>

<span data-ttu-id="dfa1d-122">Dieses Cmdlet gibt eine Zeichenfolge zurück, die eine Statusmeldung und den Pfad zur Ausgabedatei enthält.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-122">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="dfa1d-123">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dfa1d-123">NOTES</span></span>

* <span data-ttu-id="dfa1d-124">Wenn eine Aufzeichnung nicht gestartet wurde, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="dfa1d-124">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="dfa1d-125">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dfa1d-125">RELATED LINKS</span></span>

[<span data-ttu-id="dfa1d-126">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="dfa1d-126">Start-Transcript</span></span>](Start-Transcript.md)
