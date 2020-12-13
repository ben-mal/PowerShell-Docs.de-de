---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen eines Windows PowerShell-Snap-Ins
description: Erstellen eines Windows PowerShell-Snap-Ins
ms.openlocfilehash: 29394ebcd2f7c4a547aabcb88685ff494b2c381d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657272"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a><span data-ttu-id="830e0-103">Erstellen eines Windows PowerShell-Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="830e0-103">How to Create a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="830e0-104">Ein Windows PowerShell-Snap-in bietet einen Mechanismus zum Registrieren von Cmdlets-Sätzen und eines anderen Windows PowerShell-Anbieters mit der Shell und erweitert so die Funktionalität der Shell.</span><span class="sxs-lookup"><span data-stu-id="830e0-104">A Windows PowerShell snap-in provides a mechanism for registering sets of cmdlets and another Windows PowerShell provider with the shell, thus extending the functionality of the shell.</span></span> <span data-ttu-id="830e0-105">Mit einem Windows PowerShell-Snap-in können alle Cmdlets und Anbieter in einer einzelnen Assembly registriert werden, oder es kann eine bestimmte Liste von Cmdlets und Anbietern registriert werden.</span><span class="sxs-lookup"><span data-stu-id="830e0-105">A Windows PowerShell snap-in can register all the cmdlets and providers in a single assembly, or it can register a specific list of cmdlets and providers.</span></span>

<span data-ttu-id="830e0-106">Snap-in-Assemblys sollten in einem geschützten Verzeichnis installiert werden, genauso wie bei anderen Betriebssystemen.</span><span class="sxs-lookup"><span data-stu-id="830e0-106">Snap-in assemblies should be installed in a protected directory, just as they would be with other operating systems.</span></span> <span data-ttu-id="830e0-107">Andernfalls können böswillige Benutzer eine Assembly durch unsicheren Code ersetzen.</span><span class="sxs-lookup"><span data-stu-id="830e0-107">Otherwise, malicious users can replace an assembly with unsafe code.</span></span>

## <a name="windows-powershell-snap-in-classes"></a><span data-ttu-id="830e0-108">Windows PowerShell-Snap-in-Klassen</span><span class="sxs-lookup"><span data-stu-id="830e0-108">Windows PowerShell Snap-in Classes</span></span>

<span data-ttu-id="830e0-109">Alle Windows PowerShell-Snap-in-Klassen werden von der [System. Management. Automation. PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) -Klasse oder der [System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn) -Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="830e0-109">All Windows PowerShell snap-in classes derive from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) classes.</span></span>

## <a name="examples"></a><span data-ttu-id="830e0-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="830e0-110">Examples</span></span>

<span data-ttu-id="830e0-111">[Schreiben eines Windows PowerShell-Snap-Ins](./writing-a-windows-powershell-snap-in.md): in diesem Beispiel wird gezeigt, wie ein Snap-in erstellt wird, das zum Registrieren aller Cmdlets und Anbieter in einer Assembly verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="830e0-111">[Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md): This example shows how to create a snap-in that is used to register all the cmdlets and providers in an assembly.</span></span>

<span data-ttu-id="830e0-112">[Schreiben eines benutzerdefinierten Windows PowerShell-Snap-Ins](./writing-a-custom-windows-powershell-snap-in.md): in diesem Beispiel wird gezeigt, wie ein benutzerdefiniertes Snap-in erstellt wird, das zum Registrieren eines bestimmten Satzes von Cmdlets und Anbietern verwendet wird, die in einer einzelnen Assembly vorhanden sein könnten oder nicht.</span><span class="sxs-lookup"><span data-stu-id="830e0-112">[Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md): This example shows how to create a custom snap-in that is used to register a specific set of cmdlets and providers that might or might not exist in a single assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="830e0-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="830e0-113">See Also</span></span>

[<span data-ttu-id="830e0-114">System. Management. Automation. PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="830e0-114">System.Management.Automation.PSSnapIn</span></span>](/dotnet/api/System.Management.Automation.PSSnapIn)

[<span data-ttu-id="830e0-115">System. Management. Automation. CustomPSSnapIn</span><span class="sxs-lookup"><span data-stu-id="830e0-115">System.Management.Automation.Custompssnapin</span></span>](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[<span data-ttu-id="830e0-116">Registrieren von Cmdlets</span><span class="sxs-lookup"><span data-stu-id="830e0-116">Registering Cmdlets</span></span>](./registering-cmdlets.md)

[<span data-ttu-id="830e0-117">Referenz zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="830e0-117">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
