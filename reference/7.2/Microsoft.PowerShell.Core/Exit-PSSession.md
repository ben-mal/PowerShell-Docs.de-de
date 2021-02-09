---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: b1827929c53560cb261cd7b3ba1e5bd407c25700
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975089"
---
# <span data-ttu-id="080c8-102">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="080c8-102">Exit-PSSession</span></span>

## <span data-ttu-id="080c8-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="080c8-103">Synopsis</span></span>
<span data-ttu-id="080c8-104">Beendet eine interaktive Sitzung mit einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="080c8-104">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="080c8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="080c8-105">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="080c8-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="080c8-106">Description</span></span>

<span data-ttu-id="080c8-107">Das `Exit-PSSession` Cmdlet beendet interaktive Sitzungen, die Sie mithilfe des `Enter-PSSession` Cmdlets gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="080c8-107">The `Exit-PSSession` cmdlet ends interactive sessions that you started by using the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="080c8-108">Sie können auch das- `exit` Schlüsselwort verwenden, um eine interaktive Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="080c8-108">You can also use the `exit` keyword to end an interactive session.</span></span> <span data-ttu-id="080c8-109">Der Effekt ist identisch mit der Verwendung von `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="080c8-109">The effect is the same as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="080c8-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="080c8-110">Examples</span></span>

### <span data-ttu-id="080c8-111">Beispiel 1: starten und Beenden einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="080c8-111">Example 1: Start and stop an interactive session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> Exit-PSSession
PS>
```

<span data-ttu-id="080c8-112">Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Remotecomputer Server01.</span><span class="sxs-lookup"><span data-stu-id="080c8-112">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="080c8-113">Beispiel 2: starten und Beenden einer interaktiven Sitzung mit einem PSSession-Objekt</span><span class="sxs-lookup"><span data-stu-id="080c8-113">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="080c8-114">Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Server01-Computer, der eine PowerShell-Sitzung (**PSSession**) verwendet.</span><span class="sxs-lookup"><span data-stu-id="080c8-114">These commands start and stop an interactive session with the Server01 computer that uses a PowerShell session (**PSSession**).</span></span>

<span data-ttu-id="080c8-115">Da die interaktive Sitzung mithilfe einer PowerShell-Sitzung gestartet wurde, ist die **PSSession** weiterhin verfügbar, wenn die interaktive Sitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="080c8-115">Because the interactive session was started by using a PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span> <span data-ttu-id="080c8-116">Wenn Sie den _Computername_ -Parameter verwenden, wird von `Enter-PSSession` eine temporäre Sitzung erstellt, die beim Ende der interaktiven Sitzung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="080c8-116">If you use the _ComputerName_ parameter, `Enter-PSSession` creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="080c8-117">Der erste Befehl verwendet das `New-PSSession` Cmdlet, um eine **PSSession** auf dem Server01-Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="080c8-117">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="080c8-118">Der Befehl speichert die **PSSession** in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="080c8-118">The command saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="080c8-119">Der zweite Befehl verwendet `Enter-PSSession` , um mithilfe der **PSSession** in eine interaktive Sitzung zu starten `$s` .</span><span class="sxs-lookup"><span data-stu-id="080c8-119">The second command uses `Enter-PSSession` to start an interactive session using the **PSSession** in `$s`.</span></span>

<span data-ttu-id="080c8-120">Der dritte Befehl verwendet `Exit-PSSession` , um die interaktive Sitzung zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="080c8-120">The third command uses `Exit-PSSession` to stop the interactive session.</span></span>

<span data-ttu-id="080c8-121">Der letzte Befehl zeigt die **PSSession** in der `$s` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="080c8-121">The final command displays the **PSSession** in the `$s` variable.</span></span> <span data-ttu-id="080c8-122">Die **State** -Eigenschaft zeigt, dass die **PSSession** weiterhin geöffnet ist und zur Verwendung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="080c8-122">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="080c8-123">Beispiel 3: Verwenden des Exit-Schlüssel Worts zum Beenden einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="080c8-123">Example 3: Use the Exit keyword to stop a session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> exit
PS>
```

<span data-ttu-id="080c8-124">Dieses Beispiel verwendet das- `exit` Schlüsselwort, um eine interaktive Sitzung zu beenden, die mit gestartet wurde `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="080c8-124">This example uses the `exit` keyword to stop an interactive session started by using `Enter-PSSession`.</span></span> <span data-ttu-id="080c8-125">Das- `exit` Schlüsselwort hat dieselbe Auswirkung wie die Verwendung von `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="080c8-125">The `exit` keyword has the same effect as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="080c8-126">Parameter</span><span class="sxs-lookup"><span data-stu-id="080c8-126">Parameters</span></span>

### <span data-ttu-id="080c8-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="080c8-127">CommonParameters</span></span>

<span data-ttu-id="080c8-128">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="080c8-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="080c8-129">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="080c8-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="080c8-130">Eingaben</span><span class="sxs-lookup"><span data-stu-id="080c8-130">Inputs</span></span>

### <span data-ttu-id="080c8-131">Keine</span><span class="sxs-lookup"><span data-stu-id="080c8-131">None</span></span>

<span data-ttu-id="080c8-132">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="080c8-132">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="080c8-133">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="080c8-133">Outputs</span></span>

### <span data-ttu-id="080c8-134">Keine</span><span class="sxs-lookup"><span data-stu-id="080c8-134">None</span></span>

<span data-ttu-id="080c8-135">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="080c8-135">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="080c8-136">Notizen</span><span class="sxs-lookup"><span data-stu-id="080c8-136">Notes</span></span>

<span data-ttu-id="080c8-137">Von diesem Cmdlet werden nur allgemeine Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="080c8-137">This cmdlet takes only the common parameters.</span></span>

## <span data-ttu-id="080c8-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="080c8-138">RELATED LINKS</span></span>

[<span data-ttu-id="080c8-139">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="080c8-139">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="080c8-140">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="080c8-140">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="080c8-141">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="080c8-141">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="080c8-142">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="080c8-142">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="080c8-143">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="080c8-143">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="080c8-144">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="080c8-144">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="080c8-145">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="080c8-145">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="080c8-146">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="080c8-146">Remove-PSSession</span></span>](Remove-PSSession.md)
