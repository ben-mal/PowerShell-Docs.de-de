---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: 0052543842f97dc1a19caae15222fd1b97d49902
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200856"
---
# <span data-ttu-id="8cee2-103">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="8cee2-103">Get-PSCallStack</span></span>

## <span data-ttu-id="8cee2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8cee2-104">SYNOPSIS</span></span>
<span data-ttu-id="8cee2-105">Zeigt die aktuelle Aufrufliste an.</span><span class="sxs-lookup"><span data-stu-id="8cee2-105">Displays the current call stack.</span></span>

## <span data-ttu-id="8cee2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8cee2-106">SYNTAX</span></span>

```
Get-PSCallStack [<CommonParameters>]
```

## <span data-ttu-id="8cee2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8cee2-107">DESCRIPTION</span></span>

<span data-ttu-id="8cee2-108">Das **Get-pscallstack-** Cmdlet zeigt die aktuelle-aufrufste an.</span><span class="sxs-lookup"><span data-stu-id="8cee2-108">The **Get-PSCallStack** cmdlet displays the current call stack.</span></span>

<span data-ttu-id="8cee2-109">Obwohl Sie für die Verwendung mit dem PowerShell-Debugger konzipiert ist, können Sie dieses Cmdlet verwenden, um die aufrufsstapel in einem Skript oder einer Funktion außerhalb des Debuggers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8cee2-109">Although it is designed to be used with the PowerShell debugger, you can use this cmdlet to display the call stack in a script or function outside of the debugger.</span></span>

<span data-ttu-id="8cee2-110">Um einen **Get-pscallstack** -Befehl im Debugger auszuführen, geben Sie `k` oder ein `Get-PSCallStack` .</span><span class="sxs-lookup"><span data-stu-id="8cee2-110">To run a **Get-PSCallStack** command while in the debugger, type `k` or `Get-PSCallStack`.</span></span>

## <span data-ttu-id="8cee2-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8cee2-111">EXAMPLES</span></span>

### <span data-ttu-id="8cee2-112">Beispiel 1: Abrufen der aufrufsstapel für eine Funktion</span><span class="sxs-lookup"><span data-stu-id="8cee2-112">Example 1: Get the call stack for a function</span></span>

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

<span data-ttu-id="8cee2-113">Dieser Befehl verwendet das **Get-pscallstack-** Cmdlet, um die Aufrufe für "My-Alias" anzuzeigen, eine einfache Funktion, die die Aliase für einen Cmdlet-Namen abruft.</span><span class="sxs-lookup"><span data-stu-id="8cee2-113">This command uses the **Get-PSCallStack** cmdlet to display the call stack for My-Alias, a simple function that gets the aliases for a cmdlet name.</span></span>

<span data-ttu-id="8cee2-114">Der erste Befehl gibt die Funktion an der PowerShell-Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="8cee2-114">The first command enters the function at the PowerShell prompt.</span></span>
<span data-ttu-id="8cee2-115">Der zweite Befehl verwendet das Set-PSBreakpoint-Cmdlet um einen Haltepunkt für die My-Alias-Funktion festzulegen.</span><span class="sxs-lookup"><span data-stu-id="8cee2-115">The second command uses the Set-PSBreakpoint cmdlet to set a breakpoint on the My-Alias function.</span></span>
<span data-ttu-id="8cee2-116">Der dritte Befehl verwendet die My-Alias-Funktion, um alle Aliase in der aktuellen Sitzung für das Get-Content-Cmdlet abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8cee2-116">The third command uses the My-Alias function to get all of the aliases in the current session for the Get-Content cmdlet.</span></span>

<span data-ttu-id="8cee2-117">Der Debugger unterbricht den Funktionsaufruf.</span><span class="sxs-lookup"><span data-stu-id="8cee2-117">The debugger breaks in at the function call.</span></span>
<span data-ttu-id="8cee2-118">Zwei aufeinander folgende step-into (s)-Befehle beginnen, die Funktion zeilenweise auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8cee2-118">Two consecutive step-into (s) commands begin executing the function line by line.</span></span>
<span data-ttu-id="8cee2-119">Anschließend wird ein **Get-pscallstack-** Befehl verwendet, um die-Rückruf Stapel abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8cee2-119">Then, a **Get-PSCallStack** command is used to retrieve the call stack.</span></span>

<span data-ttu-id="8cee2-120">Der letzte Befehl ist ein Step-Out (o)-Befehl, der den Debugger beendet und das Skript bis zu seinem Abschluss weiter ausführt.</span><span class="sxs-lookup"><span data-stu-id="8cee2-120">The final command is a Step-Out command (o) that exits the debugger and continues executing the script to completion.</span></span>

## <span data-ttu-id="8cee2-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8cee2-121">PARAMETERS</span></span>

### <span data-ttu-id="8cee2-122">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8cee2-122">CommonParameters</span></span>

<span data-ttu-id="8cee2-123">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8cee2-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8cee2-124">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8cee2-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8cee2-125">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8cee2-125">INPUTS</span></span>

### <span data-ttu-id="8cee2-126">Keine</span><span class="sxs-lookup"><span data-stu-id="8cee2-126">None</span></span>

<span data-ttu-id="8cee2-127">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="8cee2-127">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="8cee2-128">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8cee2-128">OUTPUTS</span></span>

### <span data-ttu-id="8cee2-129">System. Management. Automation. callstackframe</span><span class="sxs-lookup"><span data-stu-id="8cee2-129">System.Management.Automation.CallStackFrame</span></span>

<span data-ttu-id="8cee2-130">**Get-pscallstack** gibt ein Objekt zurück, das die Elemente in der aufrufsstapel darstellt.</span><span class="sxs-lookup"><span data-stu-id="8cee2-130">**Get-PSCallStack** returns an object that represents the items in the call stack.</span></span>

## <span data-ttu-id="8cee2-131">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8cee2-131">NOTES</span></span>

## <span data-ttu-id="8cee2-132">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8cee2-132">RELATED LINKS</span></span>

[<span data-ttu-id="8cee2-133">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8cee2-133">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="8cee2-134">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8cee2-134">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="8cee2-135">Format-Table</span><span class="sxs-lookup"><span data-stu-id="8cee2-135">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="8cee2-136">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8cee2-136">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="8cee2-137">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8cee2-137">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="8cee2-138">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8cee2-138">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
