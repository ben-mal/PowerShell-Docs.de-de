---
title: Was ist ein PowerShell-Befehl?
description: Mit PowerShell können Sie jeden Befehl ausführen, der auf Ihrem System verfügbar ist, und darüber hinaus PowerShell-spezifische Befehle, die als Cmdlets bezeichnet werden.
ms.date: 03/31/2021
ms.openlocfilehash: b6e54349ec15df3327c1f0525dce1a30ad35a6ac
ms.sourcegitcommit: eeedd4472b6cc6158494296c355579791e688baa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "106104013"
---
# <a name="powershell-commands"></a><span data-ttu-id="6de4b-103">PowerShell-Befehle</span><span class="sxs-lookup"><span data-stu-id="6de4b-103">PowerShell commands</span></span>

<span data-ttu-id="6de4b-104">Mit PowerShell können Sie jeden Befehl ausführen, der auf Ihrem System verfügbar ist, einschließlich PowerShell-spezifischer Befehle, die als Cmdlets (gesprochen „Command-Lets“) bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="6de4b-104">PowerShell allows you to run any command available on your system including PowerShell-specific commands known as cmdlets (pronounced command-lets).</span></span>

## <a name="what-is-a-cmdlet"></a><span data-ttu-id="6de4b-105">Was ist ein Cmdlet?</span><span class="sxs-lookup"><span data-stu-id="6de4b-105">What is a cmdlet?</span></span>

<span data-ttu-id="6de4b-106">Ein Cmdlet ist ein einzelner Befehl, der der Pipelinesemantik von PowerShell unterliegt und in der Regel ein .NET-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6de4b-106">A cmdlet is a single command that participates in the pipeline semantics of PowerShell and typically returns a .NET object.</span></span> <span data-ttu-id="6de4b-107">Cmdlets sind native PowerShell-Befehle, keine eigenständig ausführbaren Dateien.</span><span class="sxs-lookup"><span data-stu-id="6de4b-107">Cmdlets are native PowerShell commands, not stand-alone executables.</span></span> <span data-ttu-id="6de4b-108">Cmdlets werden in PowerShell-Modulen gesammelt, die bei Bedarf geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="6de4b-108">Cmdlets are collected into PowerShell modules that can be loaded on demand.</span></span> <span data-ttu-id="6de4b-109">Cmdlets können in jeder kompilierten .NET-Sprache oder in der eigentlichen PowerShell-Skriptsprache geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6de4b-109">Cmdlets can be written in any compiled .NET language or in the PowerShell scripting language itself.</span></span>

## <a name="cmdlet-names"></a><span data-ttu-id="6de4b-110">Cmdlet-Namen</span><span class="sxs-lookup"><span data-stu-id="6de4b-110">Cmdlet names</span></span>

<span data-ttu-id="6de4b-111">PowerShell verwendet ein _Verb-Substantiv_-Namenspaar zur Benennung von Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6de4b-111">PowerShell uses a _Verb-Noun_ name pair to name cmdlets.</span></span> <span data-ttu-id="6de4b-112">Beispielsweise wird das in PowerShell enthaltene Cmdlet `Get-Command` dazu verwendet, alle Cmdlets abzurufen, die in der Befehlsshell registriert sind.</span><span class="sxs-lookup"><span data-stu-id="6de4b-112">For example, the `Get-Command` cmdlet included in PowerShell is used to get all the cmdlets that are registered in the command shell.</span></span> <span data-ttu-id="6de4b-113">Das Verb gibt die Aktion an, die das Cmdlet ausführt, und das Substantiv identifiziert die Ressource, für die das Cmdlet seine Aktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="6de4b-113">The verb identifies the action that the cmdlet performs, and the noun identifies the resource on which the cmdlet performs its action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6de4b-114">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6de4b-114">Next steps</span></span>

<span data-ttu-id="6de4b-115">Weitere Informationen zu PowerShell und zum Auffinden anderer Cmdlets finden Sie im PowerShell-Bits-Tutorial zum [PowerShell entdecken](learn/tutorials/01-discover-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6de4b-115">To learn more about PowerShell and how to find other cmdlets, see the PowerShell Bits tutorial [Discover PowerShell](learn/tutorials/01-discover-powershell.md).</span></span>

<span data-ttu-id="6de4b-116">Informationen zum Erstellen eigener Cmdlets finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="6de4b-116">For more information about creating your own cmdlets, see the following resources:</span></span>

<span data-ttu-id="6de4b-117">Skriptbasierte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="6de4b-117">Script-based cmdlets</span></span>

- [<span data-ttu-id="6de4b-118">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="6de4b-118">about_Functions_Advanced</span></span>](/powershell/module/microsoft.powershell.core/about/about_functions_advanced)
- [<span data-ttu-id="6de4b-119">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="6de4b-119">about_Functions_CmdletBindingAttribute</span></span>](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute)
- [<span data-ttu-id="6de4b-120">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="6de4b-120">about_Functions_Advanced_Methods</span></span>](/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods)

<span data-ttu-id="6de4b-121">Kompilierte Cmdlets (PowerShell SDK-Dokumentation)</span><span class="sxs-lookup"><span data-stu-id="6de4b-121">Compiled cmdlets (PowerShell SDK docs)</span></span>

- [<span data-ttu-id="6de4b-122">Cmdlet-Übersicht</span><span class="sxs-lookup"><span data-stu-id="6de4b-122">Cmdlet overview</span></span>](developer/cmdlet/cmdlet-overview.md)
