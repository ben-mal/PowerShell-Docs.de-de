---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 16b41711e98276fee37d56f77f57e7372daa4cf3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596547"
---
# <span data-ttu-id="c7005-102">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="c7005-102">Stop-Transcript</span></span>

## <span data-ttu-id="c7005-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c7005-103">SYNOPSIS</span></span>
<span data-ttu-id="c7005-104">Beendet eine Aufzeichnung.</span><span class="sxs-lookup"><span data-stu-id="c7005-104">Stops a transcript.</span></span>

## <span data-ttu-id="c7005-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c7005-105">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="c7005-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c7005-106">DESCRIPTION</span></span>

<span data-ttu-id="c7005-107">Das- `Stop-Transcript` Cmdlet beendet eine Aufzeichnung, die vom `Start-Transcript` Cmdlet gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="c7005-107">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="c7005-108">Alternativ können Sie eine Sitzung beenden, um eine Aufzeichnung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="c7005-108">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="c7005-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c7005-109">EXAMPLES</span></span>

### <span data-ttu-id="c7005-110">Beispiel 1: alle Transkriptionen Abbrechen</span><span class="sxs-lookup"><span data-stu-id="c7005-110">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="c7005-111">Dieser Befehl beendet alle Transkriptionen.</span><span class="sxs-lookup"><span data-stu-id="c7005-111">This command stops all transcripts.</span></span>

## <span data-ttu-id="c7005-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c7005-112">PARAMETERS</span></span>

### <span data-ttu-id="c7005-113">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c7005-113">CommonParameters</span></span>

<span data-ttu-id="c7005-114">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c7005-114">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c7005-115">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c7005-115">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c7005-116">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c7005-116">INPUTS</span></span>

### <span data-ttu-id="c7005-117">Keine</span><span class="sxs-lookup"><span data-stu-id="c7005-117">None</span></span>

<span data-ttu-id="c7005-118">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="c7005-118">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c7005-119">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c7005-119">OUTPUTS</span></span>

### <span data-ttu-id="c7005-120">System.String</span><span class="sxs-lookup"><span data-stu-id="c7005-120">System.String</span></span>

<span data-ttu-id="c7005-121">Dieses Cmdlet gibt eine Zeichenfolge zurück, die eine Statusmeldung und den Pfad zur Ausgabedatei enthält.</span><span class="sxs-lookup"><span data-stu-id="c7005-121">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="c7005-122">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c7005-122">NOTES</span></span>

* <span data-ttu-id="c7005-123">Wenn eine Aufzeichnung nicht gestartet wurde, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="c7005-123">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="c7005-124">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c7005-124">RELATED LINKS</span></span>

[<span data-ttu-id="c7005-125">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="c7005-125">Start-Transcript</span></span>](Start-Transcript.md)

