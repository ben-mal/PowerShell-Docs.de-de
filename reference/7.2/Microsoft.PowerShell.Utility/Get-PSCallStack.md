---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: 607e3999a1dbe9a4f22a751f11ac93ee3f9d9409
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596762"
---
# <span data-ttu-id="a4006-102">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="a4006-102">Get-PSCallStack</span></span>

## <span data-ttu-id="a4006-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a4006-103">SYNOPSIS</span></span>
<span data-ttu-id="a4006-104">Zeigt die aktuelle Aufrufliste an.</span><span class="sxs-lookup"><span data-stu-id="a4006-104">Displays the current call stack.</span></span>

## <span data-ttu-id="a4006-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a4006-105">SYNTAX</span></span>

```
Get-PSCallStack [<CommonParameters>]
```

## <span data-ttu-id="a4006-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a4006-106">DESCRIPTION</span></span>

<span data-ttu-id="a4006-107">Das **Get-pscallstack-** Cmdlet zeigt die aktuelle-aufrufste an.</span><span class="sxs-lookup"><span data-stu-id="a4006-107">The **Get-PSCallStack** cmdlet displays the current call stack.</span></span>

<span data-ttu-id="a4006-108">Obwohl Sie für die Verwendung mit dem PowerShell-Debugger konzipiert ist, können Sie dieses Cmdlet verwenden, um die aufrufsstapel in einem Skript oder einer Funktion außerhalb des Debuggers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a4006-108">Although it is designed to be used with the PowerShell debugger, you can use this cmdlet to display the call stack in a script or function outside of the debugger.</span></span>

<span data-ttu-id="a4006-109">Um einen **Get-pscallstack** -Befehl im Debugger auszuführen, geben Sie `k` oder ein `Get-PSCallStack` .</span><span class="sxs-lookup"><span data-stu-id="a4006-109">To run a **Get-PSCallStack** command while in the debugger, type `k` or `Get-PSCallStack`.</span></span>

## <span data-ttu-id="a4006-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a4006-110">EXAMPLES</span></span>

### <span data-ttu-id="a4006-111">Beispiel 1: Abrufen der aufrufsstapel für eine Funktion</span><span class="sxs-lookup"><span data-stu-id="a4006-111">Example 1: Get the call stack for a function</span></span>

```
PS C:\> function my-alias {
$p = $args[0]
Get-Alias | where {$_.definition -like "*$p"} | format-table definition, name -auto
}
PS C:\ps-test> Set-PSBreakpoint -Command my-alias
Command    : my-alias
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : prompt PS C:\> my-alias Get-Content

Entering debug mode. Use h or ? for help.
Hit Command breakpoint on 'prompt:my-alias'
my-alias get-content
[DBG]: PS C:\ps-test> s
$p = $args[0]
DEBUG: Stepped to ':    $p = $args[0]    '
[DBG]: PS C:\ps-test> s
get-alias | Where {$_.Definition -like "*$p*"} | format-table Definition,
[DBG]: PS C:\ps-test>get-pscallstack

Name        CommandLineParameters         UnboundArguments              Location
----        ---------------------         ----------------              --------
prompt      {}                            {}                            prompt
my-alias    {}                            {get-content}                 prompt
prompt      {}                            {}                            prompt PS C:\> [DBG]: PS C:\ps-test> o
Definition  Name
----------  ----
Get-Content gc
Get-Content cat
Get-Content type
```

<span data-ttu-id="a4006-112">Dieser Befehl verwendet das **Get-pscallstack-** Cmdlet, um die Aufrufe für "My-Alias" anzuzeigen, eine einfache Funktion, die die Aliase für einen Cmdlet-Namen abruft.</span><span class="sxs-lookup"><span data-stu-id="a4006-112">This command uses the **Get-PSCallStack** cmdlet to display the call stack for My-Alias, a simple function that gets the aliases for a cmdlet name.</span></span>

<span data-ttu-id="a4006-113">Der erste Befehl gibt die Funktion an der PowerShell-Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="a4006-113">The first command enters the function at the PowerShell prompt.</span></span>
<span data-ttu-id="a4006-114">Der zweite Befehl verwendet das Set-PSBreakpoint-Cmdlet um einen Haltepunkt für die My-Alias-Funktion festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a4006-114">The second command uses the Set-PSBreakpoint cmdlet to set a breakpoint on the My-Alias function.</span></span>
<span data-ttu-id="a4006-115">Der dritte Befehl verwendet die My-Alias-Funktion, um alle Aliase in der aktuellen Sitzung für das Get-Content-Cmdlet abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a4006-115">The third command uses the My-Alias function to get all of the aliases in the current session for the Get-Content cmdlet.</span></span>

<span data-ttu-id="a4006-116">Der Debugger unterbricht den Funktionsaufruf.</span><span class="sxs-lookup"><span data-stu-id="a4006-116">The debugger breaks in at the function call.</span></span>
<span data-ttu-id="a4006-117">Zwei aufeinander folgende step-into (s)-Befehle beginnen, die Funktion zeilenweise auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a4006-117">Two consecutive step-into (s) commands begin executing the function line by line.</span></span>
<span data-ttu-id="a4006-118">Anschließend wird ein **Get-pscallstack-** Befehl verwendet, um die-Rückruf Stapel abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a4006-118">Then, a **Get-PSCallStack** command is used to retrieve the call stack.</span></span>

<span data-ttu-id="a4006-119">Der letzte Befehl ist ein Step-Out (o)-Befehl, der den Debugger beendet und das Skript bis zu seinem Abschluss weiter ausführt.</span><span class="sxs-lookup"><span data-stu-id="a4006-119">The final command is a Step-Out command (o) that exits the debugger and continues executing the script to completion.</span></span>

## <span data-ttu-id="a4006-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a4006-120">PARAMETERS</span></span>

### <span data-ttu-id="a4006-121">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a4006-121">CommonParameters</span></span>

<span data-ttu-id="a4006-122">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a4006-122">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a4006-123">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a4006-123">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a4006-124">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a4006-124">INPUTS</span></span>

### <span data-ttu-id="a4006-125">Keine</span><span class="sxs-lookup"><span data-stu-id="a4006-125">None</span></span>

<span data-ttu-id="a4006-126">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="a4006-126">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="a4006-127">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a4006-127">OUTPUTS</span></span>

### <span data-ttu-id="a4006-128">System. Management. Automation. callstackframe</span><span class="sxs-lookup"><span data-stu-id="a4006-128">System.Management.Automation.CallStackFrame</span></span>

<span data-ttu-id="a4006-129">**Get-pscallstack** gibt ein Objekt zurück, das die Elemente in der aufrufsstapel darstellt.</span><span class="sxs-lookup"><span data-stu-id="a4006-129">**Get-PSCallStack** returns an object that represents the items in the call stack.</span></span>

## <span data-ttu-id="a4006-130">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a4006-130">NOTES</span></span>

## <span data-ttu-id="a4006-131">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a4006-131">RELATED LINKS</span></span>

[<span data-ttu-id="a4006-132">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a4006-132">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="a4006-133">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a4006-133">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="a4006-134">Format-Table</span><span class="sxs-lookup"><span data-stu-id="a4006-134">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="a4006-135">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a4006-135">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="a4006-136">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a4006-136">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="a4006-137">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a4006-137">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

