---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
keywords: powershell
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: a404461e2b92f269d581b18c3ebe7643aa86c3a4
ms.sourcegitcommit: 9d95532afe81c235c8094eae28ab84b2f77f8c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "93220391"
---
# <span data-ttu-id="2e6b6-103">Psread-Line-Modul</span><span class="sxs-lookup"><span data-stu-id="2e6b6-103">PSReadLine Module</span></span>

## <span data-ttu-id="2e6b6-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2e6b6-104">Description</span></span>

<span data-ttu-id="2e6b6-105">Das psleline-Modul enthält Cmdlets, mit denen Sie die Bearbeitungsumgebung für die Befehlszeile in PowerShell anpassen können.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-105">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="2e6b6-106">In diesen Artikeln wird psread Line v 2.0 dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-106">These articles documents PSReadLine v2.0.</span></span> <span data-ttu-id="2e6b6-107">Diese Version wird in PowerShell V6 und dem Windows 10-Update vom Oktober 2018 (Build 1809) ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-107">This version ships in PowerShell v6 and the Windows 10 October 2018 Update (Build 1809).</span></span>

> [!NOTE]
> <span data-ttu-id="2e6b6-108">Ab PowerShell 7,0 überspringt PowerShell das automatische Laden von psleseline unter Windows, wenn ein Bildschirm Leseprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-108">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="2e6b6-109">Derzeit funktioniert psread Line nicht gut mit den Bildschirmlesern.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-109">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="2e6b6-110">Das Standard Rendering und die Formatierung von PowerShell 7,0 unter Windows funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-110">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="2e6b6-111">Sie können das Modul ggf. manuell laden.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-111">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="2e6b6-112">Psleline-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2e6b6-112">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="2e6b6-113">Psconsolehostread-Zeile</span><span class="sxs-lookup"><span data-stu-id="2e6b6-113">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="2e6b6-114">Der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-114">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="2e6b6-115">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="2e6b6-115">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="2e6b6-116">Ruft die gebundenen Schlüsselfunktionen für das psread Line-Modul ab.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-116">Gets the bound key functions for the PSReadLine module.</span></span>

### [<span data-ttu-id="2e6b6-117">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="2e6b6-117">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="2e6b6-118">Ruft Werte für die Optionen ab, die konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-118">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="2e6b6-119">Psconsolehostread-Zeile</span><span class="sxs-lookup"><span data-stu-id="2e6b6-119">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="2e6b6-120">Diese Funktion ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-120">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="2e6b6-121">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="2e6b6-121">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="2e6b6-122">Entfernt eine tastenbindung.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-122">Removes a key binding.</span></span>

### [<span data-ttu-id="2e6b6-123">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="2e6b6-123">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="2e6b6-124">Bindet Schlüssel an benutzerdefinierte oder psread Line-schlüsselhandlerfunktionen.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-124">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="2e6b6-125">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="2e6b6-125">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="2e6b6-126">Passt das Verhalten der Befehlszeilen Bearbeitung in **psread Line** an.</span><span class="sxs-lookup"><span data-stu-id="2e6b6-126">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

