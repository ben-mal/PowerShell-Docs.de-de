---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=2113630
Help Version: 7.0.1.0
keywords: powershell
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: fc059318507b7a875eedf47692c1b6e3572efbbc
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195562"
---
# <span data-ttu-id="262b4-103">Psread-Line-Modul</span><span class="sxs-lookup"><span data-stu-id="262b4-103">PSReadLine Module</span></span>

## <span data-ttu-id="262b4-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="262b4-104">Description</span></span>

<span data-ttu-id="262b4-105">Das psleline-Modul enthält Cmdlets, mit denen Sie die Bearbeitungsumgebung für die Befehlszeile in PowerShell anpassen können.</span><span class="sxs-lookup"><span data-stu-id="262b4-105">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="262b4-106">In diesen Artikeln wird psread Line v 2.0 dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="262b4-106">These articles document PSReadLine v2.0.</span></span> <span data-ttu-id="262b4-107">Diese Version wird in PowerShell V6 und dem Windows 10-Update vom Oktober 2018 (Build 1809) ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="262b4-107">This version ships in PowerShell v6 and the Windows 10 October 2018 Update (Build 1809).</span></span>

> [!NOTE]
> <span data-ttu-id="262b4-108">Ab PowerShell 7,0 überspringt PowerShell das automatische Laden von psleseline unter Windows, wenn ein Bildschirm Leseprogramm erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="262b4-108">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="262b4-109">Derzeit funktioniert psread Line nicht gut mit den Bildschirmlesern.</span><span class="sxs-lookup"><span data-stu-id="262b4-109">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="262b4-110">Das Standard Rendering und die Formatierung von PowerShell 7,0 unter Windows funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="262b4-110">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="262b4-111">Sie können das Modul ggf. manuell laden.</span><span class="sxs-lookup"><span data-stu-id="262b4-111">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="262b4-112">Psleline-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="262b4-112">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="262b4-113">Psconsolehostread-Zeile</span><span class="sxs-lookup"><span data-stu-id="262b4-113">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="262b4-114">Der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="262b4-114">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="262b4-115">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="262b4-115">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="262b4-116">Ruft die Tastenbindungen für das psread Line-Modul ab.</span><span class="sxs-lookup"><span data-stu-id="262b4-116">Gets the key bindings for the PSReadLine module.</span></span>

### [<span data-ttu-id="262b4-117">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="262b4-117">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="262b4-118">Ruft Werte für die Optionen ab, die konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="262b4-118">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="262b4-119">Psconsolehostread-Zeile</span><span class="sxs-lookup"><span data-stu-id="262b4-119">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="262b4-120">Diese Funktion ist der Haupteinstiegspunkt für psread Line.</span><span class="sxs-lookup"><span data-stu-id="262b4-120">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="262b4-121">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="262b4-121">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="262b4-122">Entfernt eine tastenbindung.</span><span class="sxs-lookup"><span data-stu-id="262b4-122">Removes a key binding.</span></span>

### [<span data-ttu-id="262b4-123">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="262b4-123">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="262b4-124">Bindet Schlüssel an benutzerdefinierte oder psread Line-schlüsselhandlerfunktionen.</span><span class="sxs-lookup"><span data-stu-id="262b4-124">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="262b4-125">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="262b4-125">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="262b4-126">Passt das Verhalten der Befehlszeilen Bearbeitung in **psread Line** an.</span><span class="sxs-lookup"><span data-stu-id="262b4-126">Customizes the behavior of command line editing in **PSReadLine**.</span></span>

