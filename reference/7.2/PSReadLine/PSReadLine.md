---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: da71d4ef896befaadd7ed64f9a013dc19508a54c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596972"
---
# <span data-ttu-id="9b070-102">Psread-Line-Modul</span><span class="sxs-lookup"><span data-stu-id="9b070-102">PSReadLine Module</span></span>

## <span data-ttu-id="9b070-103">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9b070-103">Description</span></span>

<span data-ttu-id="9b070-104">Das psleline-Modul enthält Cmdlets, mit denen Sie die Bearbeitungsumgebung für die Befehlszeile in PowerShell anpassen können.</span><span class="sxs-lookup"><span data-stu-id="9b070-104">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="9b070-105">In diesen Artikeln wird psread Line v 2.0 dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="9b070-105">These articles documents PSReadLine v2.0.</span></span> <span data-ttu-id="9b070-106">Diese Version wird in PowerShell V6 und dem Windows 10-Update vom Oktober 2018 (Build 1809) ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="9b070-106">This version ships in PowerShell v6 and the Windows 10 October 2018 Update (Build 1809).</span></span>

> [!NOTE]
> <span data-ttu-id="9b070-107">Ab PowerShell 7,0 überspringt PowerShell das automatische Laden von psleseline unter Windows, wenn ein Bildschirm Leseprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="9b070-107">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="9b070-108">Derzeit funktioniert psread Line nicht gut mit den Bildschirmlesern.</span><span class="sxs-lookup"><span data-stu-id="9b070-108">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="9b070-109">Das Standard Rendering und die Formatierung von PowerShell 7,0 unter Windows funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="9b070-109">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="9b070-110">Sie können das Modul ggf. manuell laden.</span><span class="sxs-lookup"><span data-stu-id="9b070-110">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="9b070-111">Psleline-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9b070-111">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="9b070-112">Psconsolehostread-Zeile</span><span class="sxs-lookup"><span data-stu-id="9b070-112">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="9b070-113">Der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="9b070-113">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="9b070-114">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="9b070-114">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="9b070-115">Ruft die gebundenen Schlüsselfunktionen für das psread Line-Modul ab.</span><span class="sxs-lookup"><span data-stu-id="9b070-115">Gets the bound key functions for the PSReadLine module.</span></span>

### [<span data-ttu-id="9b070-116">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="9b070-116">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="9b070-117">Ruft Werte für die Optionen ab, die konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="9b070-117">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="9b070-118">Psconsolehostread-Zeile</span><span class="sxs-lookup"><span data-stu-id="9b070-118">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="9b070-119">Diese Funktion ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="9b070-119">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="9b070-120">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="9b070-120">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="9b070-121">Entfernt eine tastenbindung.</span><span class="sxs-lookup"><span data-stu-id="9b070-121">Removes a key binding.</span></span>

### [<span data-ttu-id="9b070-122">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="9b070-122">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="9b070-123">Bindet Schlüssel an benutzerdefinierte oder psread Line-schlüsselhandlerfunktionen.</span><span class="sxs-lookup"><span data-stu-id="9b070-123">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="9b070-124">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="9b070-124">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="9b070-125">Passt das Verhalten der Befehlszeilen Bearbeitung in **psread Line** an.</span><span class="sxs-lookup"><span data-stu-id="9b070-125">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

