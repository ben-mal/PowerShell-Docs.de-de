---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 0e7b895d-2fec-43f7-8cae-11e8d16f6e40
Module Name: ThreadJob
ms.date: 07/09/2019
title: Threadjob-Modul
ms.openlocfilehash: 018c0a632b24af61256180e89de88deb2ff79d03
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595518"
---
# <span data-ttu-id="a4854-102">Threadjob-Modul</span><span class="sxs-lookup"><span data-stu-id="a4854-102">ThreadJob Module</span></span>

## <span data-ttu-id="a4854-103">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a4854-103">Description</span></span>
<span data-ttu-id="a4854-104">Dieses Modul erweitert den vorhandenen PowerShell-Backgroundjob um einen neuen Thread basierten Thread **Job** -Auftrag.</span><span class="sxs-lookup"><span data-stu-id="a4854-104">This module extends the existing PowerShell BackgroundJob to include a new thread based **ThreadJob** job.</span></span> <span data-ttu-id="a4854-105">Dies ist eine einfachere Lösung für die Ausführung gleichzeitiger PowerShell-Skripts, die in der vorhandenen PowerShell-Auftrags Infrastruktur funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a4854-105">This is a lighter weight solution for running concurrent PowerShell scripts that works within the existing PowerShell job infrastructure.</span></span>

## <span data-ttu-id="a4854-106">Threadjob-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a4854-106">ThreadJob Cmdlets</span></span>

### [<span data-ttu-id="a4854-107">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="a4854-107">Start-ThreadJob</span></span>](Start-ThreadJob.md)
<span data-ttu-id="a4854-108">Erstellt Hintergrund Aufträge, die dem- `Start-Job` Cmdlet ähneln.</span><span class="sxs-lookup"><span data-stu-id="a4854-108">Creates background jobs similar to the `Start-Job` cmdlet.</span></span>
