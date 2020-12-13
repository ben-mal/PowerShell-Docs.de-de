---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet-Aliase
description: Cmdlet-Aliase
ms.openlocfilehash: 734553a9911aef256df563afa6abcdb23d7a62e6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660782"
---
# <a name="cmdlet-aliases"></a><span data-ttu-id="d52a2-103">Cmdlet-Aliase</span><span class="sxs-lookup"><span data-stu-id="d52a2-103">Cmdlet Aliases</span></span>

<span data-ttu-id="d52a2-104">Sie können Cmdlet-Aliase verwenden, um die Benutzer Darstellung des Cmdlets zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d52a2-104">You can use cmdlet aliases to improve the cmdlet user experience.</span></span> <span data-ttu-id="d52a2-105">Sie können-Aliase zu häufig verwendeten Cmdlets hinzufügen, um die Eingabe zu reduzieren und Aufgaben schneller auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d52a2-105">You can add aliases to frequently used cmdlets to reduce typing and to make it easier to complete tasks quickly.</span></span> <span data-ttu-id="d52a2-106">Sie können integrierte Aliase in ihre Cmdlets einschließen, oder Benutzer können Ihre eigenen benutzerdefinierten Aliase definieren.</span><span class="sxs-lookup"><span data-stu-id="d52a2-106">You can include built-in aliases in your cmdlets, or users can define their own custom aliases.</span></span>

<span data-ttu-id="d52a2-107">Beispielsweise verfügt das [Get-Command-](/powershell/module/microsoft.powershell.core/get-command) Cmdlet über einen integrierten `gcm` Alias.</span><span class="sxs-lookup"><span data-stu-id="d52a2-107">For example, the [Get-Command](/powershell/module/microsoft.powershell.core/get-command) cmdlet has a built-in `gcm` alias.</span></span> <span data-ttu-id="d52a2-108">Sie können Aliase auch zum Hinzufügen von Befehlsnamen aus anderen Sprachen verwenden, sodass Benutzer keine neuen Befehle erlernen müssen.</span><span class="sxs-lookup"><span data-stu-id="d52a2-108">You can also use aliases to add command names from other languages so that users do not have to learn new commands.</span></span>

## <a name="alias-guidelines"></a><span data-ttu-id="d52a2-109">Alias Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d52a2-109">Alias Guidelines</span></span>

<span data-ttu-id="d52a2-110">Befolgen Sie diese Richtlinien, wenn Sie integrierte Aliase für die Cmdlets erstellen:</span><span class="sxs-lookup"><span data-stu-id="d52a2-110">Follow these guidelines when you create built-in aliases for your cmdlets:</span></span>

- <span data-ttu-id="d52a2-111">Bevor Sie Aliase zuweisen, starten Sie Windows PowerShell, und führen Sie dann das [Get-Alias-](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) Cmdlet aus, um die bereits verwendeten Aliase anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d52a2-111">Before you assign aliases, start Windows PowerShell, and then run the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet to see the aliases that are already used.</span></span>

- <span data-ttu-id="d52a2-112">Fügen Sie ein Alias Präfix ein, das auf das Verb des Cmdlet-namens verweist, und ein Alias Suffix, das auf das Substantiv des Cmdlet-namens verweist.</span><span class="sxs-lookup"><span data-stu-id="d52a2-112">Include an alias prefix that references the verb of the cmdlet name and an alias suffix that references the noun of the cmdlet name.</span></span> <span data-ttu-id="d52a2-113">Der Alias für das `Import-Module` Cmdlet lautet z. b. "ipmo".</span><span class="sxs-lookup"><span data-stu-id="d52a2-113">For example, the alias for the `Import-Module` cmdlet is "ipmo".</span></span> <span data-ttu-id="d52a2-114">Eine Liste aller Verben und deren Aliase finden [Sie unter Cmdlet-Verben](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="d52a2-114">For a list of all the verbs and their aliases, see [Cmdlet Verbs](./approved-verbs-for-windows-powershell-commands.md).</span></span>

- <span data-ttu-id="d52a2-115">Für Cmdlets, die über das gleiche Verb verfügen, müssen Sie dasselbe Alias Präfix einschließen.</span><span class="sxs-lookup"><span data-stu-id="d52a2-115">For cmdlets that have the same verb, include the same alias prefix.</span></span> <span data-ttu-id="d52a2-116">Beispielsweise wird für die Aliase für alle Windows PowerShell-Cmdlets, die das Verb "Get" im Namen aufweisen, das Präfix "g" verwendet.</span><span class="sxs-lookup"><span data-stu-id="d52a2-116">For example, the aliases for all the Windows PowerShell cmdlets that have the "Get" verb in their name use the "g" prefix.</span></span>

- <span data-ttu-id="d52a2-117">Verwenden Sie für Cmdlets mit demselben Substantiv dasselbe Alias Suffix.</span><span class="sxs-lookup"><span data-stu-id="d52a2-117">For cmdlets that have the same noun, include the same alias suffix.</span></span> <span data-ttu-id="d52a2-118">Beispielsweise wird für die Aliase für alle Windows PowerShell-Cmdlets, die das "Session"-Substantiv in Ihrem Namen aufweisen, das "sn"-Suffix verwendet.</span><span class="sxs-lookup"><span data-stu-id="d52a2-118">For example, the aliases for all the Windows PowerShell cmdlets that have the "Session" noun in their name use the "sn" suffix.</span></span>

- <span data-ttu-id="d52a2-119">Verwenden Sie für Cmdlets, die Befehlen in anderen Sprachen entsprechen, den Namen des Befehls.</span><span class="sxs-lookup"><span data-stu-id="d52a2-119">For cmdlets that are equivalent to commands in other languages, use the name of the command.</span></span>

- <span data-ttu-id="d52a2-120">Im Allgemeinen sollten Sie Aliase so kurz wie möglich machen.</span><span class="sxs-lookup"><span data-stu-id="d52a2-120">In general, make aliases as short as possible.</span></span> <span data-ttu-id="d52a2-121">Stellen Sie sicher, dass der Alias mindestens ein unterschiedliches Zeichen für das Verb und ein eindeutiges Zeichen für das Substantiv aufweist.</span><span class="sxs-lookup"><span data-stu-id="d52a2-121">Make sure the alias has at least one distinct character for the verb and one distinct character for the noun.</span></span> <span data-ttu-id="d52a2-122">Fügen Sie nach Bedarf weitere Zeichen hinzu, um den Alias eindeutig zu machen.</span><span class="sxs-lookup"><span data-stu-id="d52a2-122">Add more characters as needed to make the alias unique.</span></span>

## <a name="see-also"></a><span data-ttu-id="d52a2-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d52a2-123">See Also</span></span>

[<span data-ttu-id="d52a2-124">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d52a2-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
