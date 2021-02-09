---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: 1e0c8413a37a9b8877b6af9089ac311459ada20d
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975106"
---
# <span data-ttu-id="89915-103">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="89915-103">Exit-PSSession</span></span>

## <span data-ttu-id="89915-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="89915-104">Synopsis</span></span>
<span data-ttu-id="89915-105">Beendet eine interaktive Sitzung mit einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="89915-105">Ends an interactive session with a remote computer.</span></span>

## <span data-ttu-id="89915-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89915-106">SYNTAX</span></span>

```
Exit-PSSession [<CommonParameters>]
```

## <span data-ttu-id="89915-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="89915-107">Description</span></span>

<span data-ttu-id="89915-108">Das `Exit-PSSession` Cmdlet beendet interaktive Sitzungen, die Sie mithilfe des `Enter-PSSession` Cmdlets gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="89915-108">The `Exit-PSSession` cmdlet ends interactive sessions that you started by using the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="89915-109">Sie können auch das- `exit` Schlüsselwort verwenden, um eine interaktive Sitzung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="89915-109">You can also use the `exit` keyword to end an interactive session.</span></span> <span data-ttu-id="89915-110">Der Effekt ist identisch mit der Verwendung von `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="89915-110">The effect is the same as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="89915-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="89915-111">Examples</span></span>

### <span data-ttu-id="89915-112">Beispiel 1: starten und Beenden einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="89915-112">Example 1: Start and stop an interactive session</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
Server01\PS> Exit-PSSession
PS C:\>
```

<span data-ttu-id="89915-113">Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Remotecomputer Server01.</span><span class="sxs-lookup"><span data-stu-id="89915-113">These commands start and then stop an interactive session with the Server01 remote computer.</span></span>

### <span data-ttu-id="89915-114">Beispiel 2: starten und Beenden einer interaktiven Sitzung mit einem PSSession-Objekt</span><span class="sxs-lookup"><span data-stu-id="89915-114">Example 2: Start and stop an interactive session by using a PSSession object</span></span>

```powershell
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS C:\> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

<span data-ttu-id="89915-115">Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Server01-Computer, auf dem eine Windows PowerShell-Sitzung (**PSSession**) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="89915-115">These commands start and stop an interactive session with the Server01 computer that uses a Windows PowerShell session (**PSSession**).</span></span>

<span data-ttu-id="89915-116">Da die interaktive Sitzung mithilfe einer Windows PowerShell-Sitzung gestartet wurde, ist die **PSSession** weiterhin verfügbar, wenn die interaktive Sitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="89915-116">Because the interactive session was started by using a Windows PowerShell session, the **PSSession** is still available when the interactive session ends.</span></span> <span data-ttu-id="89915-117">Wenn Sie den _Computername_ -Parameter verwenden, wird von `Enter-PSSession` eine temporäre Sitzung erstellt, die beim Ende der interaktiven Sitzung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="89915-117">If you use the _ComputerName_ parameter, `Enter-PSSession` creates a temporary session that it closes when the interactive session ends.</span></span>

<span data-ttu-id="89915-118">Der erste Befehl verwendet das `New-PSSession` Cmdlet, um eine **PSSession** auf dem Server01-Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89915-118">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="89915-119">Der Befehl speichert die **PSSession** in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="89915-119">The command saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="89915-120">Der zweite Befehl verwendet `Enter-PSSession` , um mithilfe der **PSSession** in eine interaktive Sitzung zu starten `$s` .</span><span class="sxs-lookup"><span data-stu-id="89915-120">The second command uses `Enter-PSSession` to start an interactive session using the **PSSession** in `$s`.</span></span>

<span data-ttu-id="89915-121">Der dritte Befehl verwendet `Exit-PSSession` , um die interaktive Sitzung zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="89915-121">The third command uses `Exit-PSSession` to stop the interactive session.</span></span>

<span data-ttu-id="89915-122">Der letzte Befehl zeigt die **PSSession** in der `$s` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="89915-122">The final command displays the **PSSession** in the `$s` variable.</span></span> <span data-ttu-id="89915-123">Die **State** -Eigenschaft zeigt, dass die **PSSession** weiterhin geöffnet ist und zur Verwendung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="89915-123">The **State** property shows the **PSSession** is still open and available for use.</span></span>

### <span data-ttu-id="89915-124">Beispiel 3: Verwenden des Exit-Schlüssel Worts zum Beenden einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="89915-124">Example 3: Use the Exit keyword to stop a session</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
Server01\PS> exit
PS C:\>
```

<span data-ttu-id="89915-125">Dieses Beispiel verwendet das- `exit` Schlüsselwort, um eine interaktive Sitzung zu beenden, die mit gestartet wurde `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="89915-125">This example uses the `exit` keyword to stop an interactive session started by using `Enter-PSSession`.</span></span> <span data-ttu-id="89915-126">Das- `exit` Schlüsselwort hat dieselbe Auswirkung wie die Verwendung von `Exit-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="89915-126">The `exit` keyword has the same effect as using `Exit-PSSession`.</span></span>

## <span data-ttu-id="89915-127">Parameter</span><span class="sxs-lookup"><span data-stu-id="89915-127">Parameters</span></span>

### <span data-ttu-id="89915-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="89915-128">CommonParameters</span></span>

<span data-ttu-id="89915-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="89915-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="89915-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="89915-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="89915-131">Eingaben</span><span class="sxs-lookup"><span data-stu-id="89915-131">Inputs</span></span>

### <span data-ttu-id="89915-132">Keine</span><span class="sxs-lookup"><span data-stu-id="89915-132">None</span></span>

<span data-ttu-id="89915-133">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="89915-133">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="89915-134">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="89915-134">Outputs</span></span>

### <span data-ttu-id="89915-135">Keine</span><span class="sxs-lookup"><span data-stu-id="89915-135">None</span></span>

<span data-ttu-id="89915-136">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="89915-136">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="89915-137">Notizen</span><span class="sxs-lookup"><span data-stu-id="89915-137">Notes</span></span>

<span data-ttu-id="89915-138">Von diesem Cmdlet werden nur allgemeine Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="89915-138">This cmdlet takes only the common parameters.</span></span>

## <span data-ttu-id="89915-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="89915-139">RELATED LINKS</span></span>

[<span data-ttu-id="89915-140">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="89915-140">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="89915-141">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="89915-141">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="89915-142">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="89915-142">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="89915-143">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="89915-143">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="89915-144">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="89915-144">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="89915-145">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="89915-145">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="89915-146">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="89915-146">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="89915-147">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="89915-147">Remove-PSSession</span></span>](Remove-PSSession.md)
