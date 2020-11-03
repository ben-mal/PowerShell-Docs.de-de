---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: d5856ead8fa3f0f30e7509c43aeeb73013b7a801
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200916"
---
# <span data-ttu-id="732ae-103">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="732ae-103">Stop-Transcript</span></span>

## <span data-ttu-id="732ae-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="732ae-104">SYNOPSIS</span></span>
<span data-ttu-id="732ae-105">Beendet eine Aufzeichnung.</span><span class="sxs-lookup"><span data-stu-id="732ae-105">Stops a transcript.</span></span>

## <span data-ttu-id="732ae-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="732ae-106">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="732ae-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="732ae-107">DESCRIPTION</span></span>

<span data-ttu-id="732ae-108">Das- `Stop-Transcript` Cmdlet beendet eine Aufzeichnung, die vom `Start-Transcript` Cmdlet gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="732ae-108">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="732ae-109">Alternativ können Sie eine Sitzung beenden, um eine Aufzeichnung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="732ae-109">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="732ae-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="732ae-110">EXAMPLES</span></span>

### <span data-ttu-id="732ae-111">Beispiel 1: alle Transkriptionen Abbrechen</span><span class="sxs-lookup"><span data-stu-id="732ae-111">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="732ae-112">Dieser Befehl beendet alle Transkriptionen.</span><span class="sxs-lookup"><span data-stu-id="732ae-112">This command stops all transcripts.</span></span>

## <span data-ttu-id="732ae-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="732ae-113">PARAMETERS</span></span>

### <span data-ttu-id="732ae-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="732ae-114">CommonParameters</span></span>

<span data-ttu-id="732ae-115">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="732ae-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="732ae-116">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="732ae-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="732ae-117">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="732ae-117">INPUTS</span></span>

### <span data-ttu-id="732ae-118">Keine</span><span class="sxs-lookup"><span data-stu-id="732ae-118">None</span></span>

<span data-ttu-id="732ae-119">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="732ae-119">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="732ae-120">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="732ae-120">OUTPUTS</span></span>

### <span data-ttu-id="732ae-121">System.String</span><span class="sxs-lookup"><span data-stu-id="732ae-121">System.String</span></span>

<span data-ttu-id="732ae-122">Dieses Cmdlet gibt eine Zeichenfolge zurück, die eine Statusmeldung und den Pfad zur Ausgabedatei enthält.</span><span class="sxs-lookup"><span data-stu-id="732ae-122">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="732ae-123">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="732ae-123">NOTES</span></span>

* <span data-ttu-id="732ae-124">Wenn eine Aufzeichnung nicht gestartet wurde, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="732ae-124">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="732ae-125">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="732ae-125">RELATED LINKS</span></span>

[<span data-ttu-id="732ae-126">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="732ae-126">Start-Transcript</span></span>](Start-Transcript.md)
