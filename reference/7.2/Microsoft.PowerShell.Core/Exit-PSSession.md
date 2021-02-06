---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: b76f7dc87105318285c930b6cd2ae4ae10c2b0e7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600488"
---
# <span data-ttu-id="59cf5-102">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="59cf5-102">Exit-PSSession</span></span>

## <span data-ttu-id="59cf5-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="59cf5-103">SYNOPSIS</span></span>
<span data-ttu-id="59cf5-104">Beendet eine interaktive Sitzung mit einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="59cf5-104">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="59cf5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="59cf5-105">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="59cf5-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="59cf5-106">DESCRIPTION</span></span>

<span data-ttu-id="59cf5-107">Das **Exit-PSSession** -Cmdlet beendet interaktive Sitzungen, die Sie mit dem Cmdlet "Enter-PSSession" gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="59cf5-107">The **Exit-PSSession** cmdlet ends interactive sessions that you started by using the Enter-PSSession cmdlet.</span></span>

<span data-ttu-id="59cf5-108">Sie können auch das **Exit** -Schlüsselwort verwenden, um eine interaktive Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="59cf5-108">You can also use the **Exit** keyword to end an interactive session.</span></span>
<span data-ttu-id="59cf5-109">Der Effekt ist mit der Verwendung von **Exit-PSSession** identisch.</span><span class="sxs-lookup"><span data-stu-id="59cf5-109">The effect is the same as using **Exit-PSSession**.</span></span>

## <span data-ttu-id="59cf5-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="59cf5-110">EXAMPLES</span></span>

### <span data-ttu-id="59cf5-111">Beispiel 1: starten und Beenden einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="59cf5-111">Example 1: Start and stop an interactive session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> Exit-PSSession
PS>
```

<span data-ttu-id="59cf5-112">Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Remotecomputer Server01.</span><span class="sxs-lookup"><span data-stu-id="59cf5-112">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="59cf5-113">Beispiel 2: starten und Beenden einer interaktiven Sitzung mit einem PSSession-Objekt</span><span class="sxs-lookup"><span data-stu-id="59cf5-113">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="59cf5-114">Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Server01-Computer, der eine PowerShell-Sitzung (**PSSession**) verwendet.</span><span class="sxs-lookup"><span data-stu-id="59cf5-114">These commands start and stop an interactive session with the Server01 computer that uses a PowerShell session (**PSSession**).</span></span>

<span data-ttu-id="59cf5-115">Da die interaktive Sitzung mithilfe einer PowerShell-Sitzung gestartet wurde, ist die **PSSession** weiterhin verfügbar, wenn die interaktive Sitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="59cf5-115">Because the interactive session was started by using a PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span>
<span data-ttu-id="59cf5-116">Wenn Sie den *Computername* -Parameter verwenden, erstellt **Enter-PSSession** eine temporäre Sitzung, die beim Ende der interaktiven Sitzung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="59cf5-116">If you use the *ComputerName* parameter, **Enter-PSSession** creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="59cf5-117">Der erste Befehl verwendet das Cmdlet "New-PSSession", um eine **PSSession** auf dem Server01-Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="59cf5-117">The first command uses the New-PSSession cmdlet to create a **PSSession** on the Server01 computer.</span></span>
<span data-ttu-id="59cf5-118">Der Befehl speichert die **PSSession** in der $s Variable.</span><span class="sxs-lookup"><span data-stu-id="59cf5-118">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="59cf5-119">Der zweite Befehl verwendet **Enter-PSSession** , um eine interaktive Sitzung mithilfe der **PSSession** in $s zu starten.</span><span class="sxs-lookup"><span data-stu-id="59cf5-119">The second command uses **Enter-PSSession** to start an interactive session using the **PSSession** in $s.</span></span>

<span data-ttu-id="59cf5-120">Der dritte Befehl verwendet **Exit-PSSession** , um die interaktive Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="59cf5-120">The third command uses **Exit-PSSession** to stop the interactive session.</span></span>

<span data-ttu-id="59cf5-121">Der letzte Befehl zeigt die **PSSession** in der $s Variable an.</span><span class="sxs-lookup"><span data-stu-id="59cf5-121">The final command displays the **PSSession** in the $s variable.</span></span>
<span data-ttu-id="59cf5-122">Die **State** -Eigenschaft zeigt, dass die **PSSession** weiterhin geöffnet ist und zur Verwendung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="59cf5-122">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="59cf5-123">Beispiel 3: Verwenden des Exit-Schlüssel Worts zum Beenden einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="59cf5-123">Example 3: Use the Exit keyword to stop a session</span></span>

```
PS> Enter-PSSession -computername Server01
Server01\PS> exit
PS>
```

<span data-ttu-id="59cf5-124">Dieses Beispiel verwendet das **Exit** -Schlüsselwort, um eine interaktive Sitzung zu beenden, die mit **Enter-PSSession** gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="59cf5-124">This example uses the **Exit** keyword to stop an interactive session started by using **Enter-PSSession**.</span></span>
<span data-ttu-id="59cf5-125">Das **Exit** -Schlüsselwort hat dieselbe Auswirkung wie die Verwendung von **Exit-PSSession**.</span><span class="sxs-lookup"><span data-stu-id="59cf5-125">The **Exit** keyword has the same effect as using **Exit-PSSession**.</span></span>

## <span data-ttu-id="59cf5-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="59cf5-126">PARAMETERS</span></span>

### <span data-ttu-id="59cf5-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="59cf5-127">CommonParameters</span></span>

<span data-ttu-id="59cf5-128">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="59cf5-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="59cf5-129">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="59cf5-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="59cf5-130">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="59cf5-130">INPUTS</span></span>

### <span data-ttu-id="59cf5-131">Keine</span><span class="sxs-lookup"><span data-stu-id="59cf5-131">None</span></span>

<span data-ttu-id="59cf5-132">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="59cf5-132">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="59cf5-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="59cf5-133">OUTPUTS</span></span>

### <span data-ttu-id="59cf5-134">Keine</span><span class="sxs-lookup"><span data-stu-id="59cf5-134">None</span></span>

<span data-ttu-id="59cf5-135">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="59cf5-135">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="59cf5-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="59cf5-136">NOTES</span></span>

* <span data-ttu-id="59cf5-137">Von diesem Cmdlet werden nur allgemeine Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="59cf5-137">This cmdlet takes only the common parameters.</span></span>

*

## <span data-ttu-id="59cf5-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="59cf5-138">RELATED LINKS</span></span>

[<span data-ttu-id="59cf5-139">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="59cf5-139">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="59cf5-140">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="59cf5-140">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="59cf5-141">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="59cf5-141">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="59cf5-142">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="59cf5-142">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="59cf5-143">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="59cf5-143">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="59cf5-144">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="59cf5-144">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="59cf5-145">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="59cf5-145">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="59cf5-146">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="59cf5-146">Remove-PSSession</span></span>](Remove-PSSession.md)

