---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: efe0e6c9287b3595988aa3ffc520ce46699cafda
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212068"
---
# <span data-ttu-id="872b8-103">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="872b8-103">Exit-PSSession</span></span>

## <span data-ttu-id="872b8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="872b8-104">SYNOPSIS</span></span>
<span data-ttu-id="872b8-105">Beendet eine interaktive Sitzung mit einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="872b8-105">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="872b8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="872b8-106">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="872b8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="872b8-107">DESCRIPTION</span></span>
<span data-ttu-id="872b8-108">Das **Exit-PSSession** -Cmdlet beendet interaktive Sitzungen, die Sie mit dem Cmdlet "Enter-PSSession" gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="872b8-108">The **Exit-PSSession** cmdlet ends interactive sessions that you started by using the Enter-PSSession cmdlet.</span></span>

<span data-ttu-id="872b8-109">Sie können auch das **Exit** -Schlüsselwort verwenden, um eine interaktive Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="872b8-109">You can also use the **Exit** keyword to end an interactive session.</span></span>
<span data-ttu-id="872b8-110">Der Effekt ist mit der Verwendung von **Exit-PSSession** identisch.</span><span class="sxs-lookup"><span data-stu-id="872b8-110">The effect is the same as using **Exit-PSSession** .</span></span>

## <span data-ttu-id="872b8-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="872b8-111">EXAMPLES</span></span>

### <span data-ttu-id="872b8-112">Beispiel 1: starten und Beenden einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="872b8-112">Example 1: Start and stop an interactive session</span></span>

```
PS C:\> Enter-PSSession -computername Server01
Server01\PS> Exit-PSSession
PS C:\>
```

<span data-ttu-id="872b8-113">Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Remotecomputer Server01.</span><span class="sxs-lookup"><span data-stu-id="872b8-113">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="872b8-114">Beispiel 2: starten und Beenden einer interaktiven Sitzung mit einem PSSession-Objekt</span><span class="sxs-lookup"><span data-stu-id="872b8-114">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS C:\> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="872b8-115">Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Server01-Computer, auf dem eine Windows PowerShell-Sitzung ( **PSSession** ) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="872b8-115">These commands start and stop an interactive session with the Server01 computer that uses a Windows PowerShell session ( **PSSession** ).</span></span>

<span data-ttu-id="872b8-116">Da die interaktive Sitzung mithilfe einer Windows PowerShell-Sitzung gestartet wurde, ist die **PSSession** weiterhin verfügbar, wenn die interaktive Sitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="872b8-116">Because the interactive session was started by using a Windows PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span>
<span data-ttu-id="872b8-117">Wenn Sie den *Computername* -Parameter verwenden, erstellt **Enter-PSSession** eine temporäre Sitzung, die beim Ende der interaktiven Sitzung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="872b8-117">If you use the *ComputerName* parameter, **Enter-PSSession** creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="872b8-118">Der erste Befehl verwendet das Cmdlet "New-PSSession", um eine **PSSession** auf dem Server01-Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="872b8-118">The first command uses the New-PSSession cmdlet to create a **PSSession** on the Server01 computer.</span></span>
<span data-ttu-id="872b8-119">Der Befehl speichert die **PSSession** in der $s Variable.</span><span class="sxs-lookup"><span data-stu-id="872b8-119">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="872b8-120">Der zweite Befehl verwendet **Enter-PSSession** , um eine interaktive Sitzung mithilfe der **PSSession** in $s zu starten.</span><span class="sxs-lookup"><span data-stu-id="872b8-120">The second command uses **Enter-PSSession** to start an interactive session using the **PSSession** in $s.</span></span>

<span data-ttu-id="872b8-121">Der dritte Befehl verwendet **Exit-PSSession** , um die interaktive Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="872b8-121">The third command uses **Exit-PSSession** to stop the interactive session.</span></span>

<span data-ttu-id="872b8-122">Der letzte Befehl zeigt die **PSSession** in der $s Variable an.</span><span class="sxs-lookup"><span data-stu-id="872b8-122">The final command displays the **PSSession** in the $s variable.</span></span>
<span data-ttu-id="872b8-123">Die **State** -Eigenschaft zeigt, dass die **PSSession** weiterhin geöffnet ist und zur Verwendung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="872b8-123">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="872b8-124">Beispiel 3: Verwenden des Exit-Schlüssel Worts zum Beenden einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="872b8-124">Example 3: Use the Exit keyword to stop a session</span></span>

```
PS C:\> Enter-PSSession -computername Server01
Server01\PS> exit
PS C:\>
```

<span data-ttu-id="872b8-125">Dieses Beispiel verwendet das **Exit** -Schlüsselwort, um eine interaktive Sitzung zu beenden, die mit **Enter-PSSession** gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="872b8-125">This example uses the **Exit** keyword to stop an interactive session started by using **Enter-PSSession** .</span></span>
<span data-ttu-id="872b8-126">Das **Exit** -Schlüsselwort hat dieselbe Auswirkung wie die Verwendung von **Exit-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="872b8-126">The **Exit** keyword has the same effect as using **Exit-PSSession** .</span></span>

## <span data-ttu-id="872b8-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="872b8-127">PARAMETERS</span></span>

### <span data-ttu-id="872b8-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="872b8-128">CommonParameters</span></span>
<span data-ttu-id="872b8-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="872b8-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="872b8-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="872b8-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="872b8-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="872b8-131">INPUTS</span></span>

### <span data-ttu-id="872b8-132">Keine</span><span class="sxs-lookup"><span data-stu-id="872b8-132">None</span></span>
<span data-ttu-id="872b8-133">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="872b8-133">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="872b8-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="872b8-134">OUTPUTS</span></span>

### <span data-ttu-id="872b8-135">Keine</span><span class="sxs-lookup"><span data-stu-id="872b8-135">None</span></span>
<span data-ttu-id="872b8-136">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="872b8-136">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="872b8-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="872b8-137">NOTES</span></span>

* <span data-ttu-id="872b8-138">Von diesem Cmdlet werden nur allgemeine Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="872b8-138">This cmdlet takes only the common parameters.</span></span>


## <span data-ttu-id="872b8-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="872b8-139">RELATED LINKS</span></span>

[<span data-ttu-id="872b8-140">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="872b8-140">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="872b8-141">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="872b8-141">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="872b8-142">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="872b8-142">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="872b8-143">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="872b8-143">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="872b8-144">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="872b8-144">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="872b8-145">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="872b8-145">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="872b8-146">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="872b8-146">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="872b8-147">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="872b8-147">Remove-PSSession</span></span>](Remove-PSSession.md)
