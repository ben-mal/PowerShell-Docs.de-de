---
ms.date: 09/13/2016
ms.topic: reference
title: Anfordern der Bestätigung von Benutzern
description: Anfordern der Bestätigung von Benutzern
ms.openlocfilehash: 58dbe27635ca38886b728f585fec063645b3597e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646306"
---
# <a name="users-requesting-confirmation"></a><span data-ttu-id="64cd1-103">Anfordern der Bestätigung von Benutzern</span><span class="sxs-lookup"><span data-stu-id="64cd1-103">Users Requesting Confirmation</span></span>

<span data-ttu-id="64cd1-104">Wenn Sie `true` für den- `SupportsShouldProcess` Parameter der Cmdlet-Attribut Deklaration den Wert angeben, können Benutzer den `Confirm` Parameter an der Eingabeaufforderung angeben.</span><span class="sxs-lookup"><span data-stu-id="64cd1-104">When you specify a value of `true` for the `SupportsShouldProcess` parameter of the Cmdlet attribute declaration, users can specify the `Confirm` parameter at the command prompt.</span></span>

<span data-ttu-id="64cd1-105">In der Standardumgebung können Benutzer den- `Confirm` Parameter angeben oder festlegen `"-Confirm:$true` , dass die Bestätigung angefordert wird, wenn die [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="64cd1-105">In the default environment, users can specify the `Confirm` parameter or `"-Confirm:$true` so that confirmation is requested when the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method is called.</span></span> <span data-ttu-id="64cd1-106">Dies umgeht [System. Management. Automation. Cmdlet. tiondprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Bestätigungs Anforderungen, auch für Vorgänge mit hohen Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="64cd1-106">This bypasses [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) confirmation requests, even for high-impact operations.</span></span>

<span data-ttu-id="64cd1-107">Wenn `Confirm` nicht angegeben wird, fordert der [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Rückruf eine Bestätigung an, wenn die `$ConfirmPreference` Einstellungs Variable größer oder gleich der `ConfirmImpact` Einstellung des Cmdlets oder Anbieters ist.</span><span class="sxs-lookup"><span data-stu-id="64cd1-107">If `Confirm` is not specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation if the `$ConfirmPreference` preference variable is equal to or greater than the `ConfirmImpact` setting of the cmdlet or provider.</span></span> <span data-ttu-id="64cd1-108">Die Standardeinstellung von `$ConfirmPreference` ist hoch.</span><span class="sxs-lookup"><span data-stu-id="64cd1-108">The default setting of `$ConfirmPreference` is High.</span></span> <span data-ttu-id="64cd1-109">In der Standardumgebung gibt es daher nur Cmdlets und Anbieter, die eine Bestätigungs-Aktions Anforderungs Bestätigung angeben.</span><span class="sxs-lookup"><span data-stu-id="64cd1-109">Therefore, in the default environment, only cmdlets and providers that specify a high-impact action request confirmation.</span></span>

<span data-ttu-id="64cd1-110">Wenn `Confirm` false ist oder wenn `"-Confirm:$false` angegeben wird, fordert der [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Befehl eine Bestätigung vom Benutzer an, und die `$ConfirmPreference` Shellvariable wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="64cd1-110">If `Confirm` is false or if `"-Confirm:$false` is specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation from the user, and the `$ConfirmPreference` shell variable is ignored.</span></span>

## <a name="remarks"></a><span data-ttu-id="64cd1-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="64cd1-111">Remarks</span></span>

- <span data-ttu-id="64cd1-112">Für Cmdlets und Anbieter, die angeben `SupportsShouldProcess` , aber nicht `ConfirmImpact` , werden diese Aktionen als "mittlere Auswirkung"-Aktionen behandelt, und Sie werden nicht standardmäßig aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="64cd1-112">For cmdlets and providers that specify `SupportsShouldProcess`, but not `ConfirmImpact`, those actions are handled as "medium impact" actions, and they will not prompt by default.</span></span> <span data-ttu-id="64cd1-113">Die Auswirkungs Stufe ist kleiner als die Standardeinstellung der `$ConfirmPreference` Preference-Variablen.</span><span class="sxs-lookup"><span data-stu-id="64cd1-113">Their impact level is less than the default setting of the `$ConfirmPreference` preference variable.</span></span>

- <span data-ttu-id="64cd1-114">Wenn der Benutzer den `Verbose` Parameter angibt, wird er über den Vorgang benachrichtigt, auch wenn er nicht zur Bestätigung aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="64cd1-114">If the user specifies the `Verbose` parameter, they will be notified of the operation even if they are not prompted for confirmation.</span></span>

## <a name="see-also"></a><span data-ttu-id="64cd1-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64cd1-115">See Also</span></span>

[<span data-ttu-id="64cd1-116">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="64cd1-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
