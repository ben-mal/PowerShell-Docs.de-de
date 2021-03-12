---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: 9425f72ce4002fa871ef6b687d76f92ddf6b489e
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103193909"
---
# <span data-ttu-id="ff684-102">Psread-Line-Modul</span><span class="sxs-lookup"><span data-stu-id="ff684-102">PSReadLine Module</span></span>

## <span data-ttu-id="ff684-103">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff684-103">Description</span></span>

<span data-ttu-id="ff684-104">Das psleline-Modul enthält Cmdlets, mit denen Sie die Bearbeitungsumgebung für die Befehlszeile in PowerShell anpassen können.</span><span class="sxs-lookup"><span data-stu-id="ff684-104">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="ff684-105">In diesen Artikeln wird die aktuelle Beta Version von psread Line v 2.2.0 dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="ff684-105">These articles document the current beta version of PSReadLine v2.2.0.</span></span>

> [!NOTE]
> <span data-ttu-id="ff684-106">Ab PowerShell 7,0 überspringt PowerShell das automatische Laden von psleseline unter Windows, wenn ein Bildschirm Leseprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="ff684-106">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="ff684-107">Derzeit funktioniert psread Line nicht gut mit den Bildschirmlesern.</span><span class="sxs-lookup"><span data-stu-id="ff684-107">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="ff684-108">Das Standard Rendering und die Formatierung von PowerShell 7,0 unter Windows funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="ff684-108">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="ff684-109">Sie können das Modul ggf. manuell laden.</span><span class="sxs-lookup"><span data-stu-id="ff684-109">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="ff684-110">Psleline-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ff684-110">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="ff684-111">Psconsolehostread-Zeile</span><span class="sxs-lookup"><span data-stu-id="ff684-111">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="ff684-112">Der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="ff684-112">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="ff684-113">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="ff684-113">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="ff684-114">Ruft die gebundenen Schlüsselfunktionen für das psread Line-Modul ab.</span><span class="sxs-lookup"><span data-stu-id="ff684-114">Gets the bound key functions for the PSReadLine module.</span></span>

### [<span data-ttu-id="ff684-115">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="ff684-115">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="ff684-116">Ruft Werte für die Optionen ab, die konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="ff684-116">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="ff684-117">Psconsolehostread-Zeile</span><span class="sxs-lookup"><span data-stu-id="ff684-117">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="ff684-118">Diese Funktion ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="ff684-118">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="ff684-119">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="ff684-119">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="ff684-120">Entfernt eine tastenbindung.</span><span class="sxs-lookup"><span data-stu-id="ff684-120">Removes a key binding.</span></span>

### [<span data-ttu-id="ff684-121">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="ff684-121">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="ff684-122">Bindet Schlüssel an benutzerdefinierte oder psread Line-schlüsselhandlerfunktionen.</span><span class="sxs-lookup"><span data-stu-id="ff684-122">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="ff684-123">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="ff684-123">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="ff684-124">Passt das Verhalten der Befehlszeilen Bearbeitung in **psread Line** an.</span><span class="sxs-lookup"><span data-stu-id="ff684-124">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

