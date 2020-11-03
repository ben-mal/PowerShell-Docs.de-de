---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transaction
ms.openlocfilehash: 53be131f45f15e5d2053b183040dc7b3dca4a14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214391"
---
# <span data-ttu-id="bd8ba-103">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="bd8ba-103">Start-Transaction</span></span>

## <span data-ttu-id="bd8ba-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bd8ba-104">SYNOPSIS</span></span>
<span data-ttu-id="bd8ba-105">Startet eine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-105">Starts a transaction.</span></span>

## <span data-ttu-id="bd8ba-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd8ba-106">SYNTAX</span></span>

```
Start-Transaction [-Timeout <Int32>] [-Independent] [-RollbackPreference <RollbackSeverity>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bd8ba-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd8ba-107">DESCRIPTION</span></span>
<span data-ttu-id="bd8ba-108">Mit dem " **Start-Transaction"-** Cmdlet wird eine Transaktion gestartet, bei der es sich um eine Reihe von Befehlen handelt, die als Einheit verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-108">The **Start-Transaction** cmdlet starts a transaction, which is a series of commands that are managed as a unit.</span></span>
<span data-ttu-id="bd8ba-109">Eine Transaktion kann abgeschlossen oder ein Commit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-109">A transaction can be completed, or committed.</span></span>
<span data-ttu-id="bd8ba-110">Alternativ kann Sie vollständig rückgängig gemacht oder ein Rollback ausgeführt werden, sodass alle von der Transaktion geänderten Daten im ursprünglichen Zustand wieder hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-110">Alternatively, it can be completely undone, or rolled back, so that any data changed by the transaction is restored to its original state.</span></span>
<span data-ttu-id="bd8ba-111">Da die Befehle in einer Transaktion als Einheit verwaltet werden, wird entweder für alle Befehle ein Commit ausgeführt, oder alle Befehle werden zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-111">Because the commands in a transaction are managed as a unit, either all commands are committed or all commands are rolled back.</span></span>

<span data-ttu-id="bd8ba-112">Wenn ein Befehl in der Transaktion einen Fehler generiert, werden für Transaktionen standardmäßig automatisch ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-112">By default, if any command in the transaction generates an error, transactions are rolled back automatically.</span></span>
<span data-ttu-id="bd8ba-113">Sie können den *Rollback Preference* -Parameter verwenden, um dieses Verhalten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-113">You can use the *RollbackPreference* parameter to change this behavior.</span></span>

<span data-ttu-id="bd8ba-114">Die in einer Transaktion verwendeten Cmdlets müssen zum Unterstützen von Transaktionen geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-114">The cmdlets used in a transaction must be designed to support transactions.</span></span>
<span data-ttu-id="bd8ba-115">Cmdlets, die Transaktionen unterstützen, verfügen über einen *UseTransaction* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-115">Cmdlets that support transactions have a *UseTransaction* parameter.</span></span>
<span data-ttu-id="bd8ba-116">Damit Transaktionen in einem Anbieter ausgeführt werden können, muss der Anbieter Transaktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-116">To perform transactions in a provider, the provider must support transactions.</span></span>
<span data-ttu-id="bd8ba-117">Der Windows PowerShell-Registrierungs Anbieter in Windows Vista und höheren Versionen des Windows-Betriebssystems unterstützt Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-117">The Windows PowerShell Registry provider in Windows Vista and later versions of the Windows operating system supports transactions.</span></span>
<span data-ttu-id="bd8ba-118">Sie können auch die **Microsoft. PowerShell. Commands. Management. transactedstring** -Klasse verwenden, um Ausdrücke in Transaktionen für jede Version des Windows-Systems einzuschließen, das Windows PowerShell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-118">You can also use the **Microsoft.PowerShell.Commands.Management.TransactedString** class to include expressions in transactions on any version of the Windows system that supports Windows PowerShell.</span></span>
<span data-ttu-id="bd8ba-119">Andere Windows PowerShell-Anbieter können ebenfalls Transaktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-119">Other Windows PowerShell providers can also support transactions.</span></span>

<span data-ttu-id="bd8ba-120">Es kann jeweils nur eine Transaktion aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-120">Only one transaction can be active at a time.</span></span>
<span data-ttu-id="bd8ba-121">Wenn Sie eine neue, unabhängige Transaktion starten, während eine Transaktion ausgeführt wird, wird die neue Transaktion zur aktiven Transaktion, und Sie müssen ein Commit oder ein Rollback der neuen Transaktion ausführen, bevor Sie Änderungen an der ursprünglichen Transaktion vornehmen.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-121">If you start a new, independent transaction while a transaction is in progress, the new transaction becomes the active transaction, and you must commit or roll back the new transaction before you make any changes to the original transaction.</span></span>

<span data-ttu-id="bd8ba-122">Das Cmdlet " **Start-Transaction** " ist eine Reihe von Cmdlets, die das Transaktions Feature in Windows PowerShell unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-122">**Start-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="bd8ba-123">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-123">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="bd8ba-124">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bd8ba-124">EXAMPLES</span></span>

### <span data-ttu-id="bd8ba-125">Beispiel 1: starten und Rollback einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="bd8ba-125">Example 1: Start and roll back a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Undo-Transaction
```

<span data-ttu-id="bd8ba-126">Mit diesen Befehlen wird eine Transaktion gestartet und dann zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-126">These commands start and then roll back a transaction.</span></span>
<span data-ttu-id="bd8ba-127">Da die Transaktion zurückgesetzt wird, werden keine Änderungen in der Registrierung vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-127">Because the transaction is rolled back, no changes are made to the registry.</span></span>

### <span data-ttu-id="bd8ba-128">Beispiel 2: starten und Beenden einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="bd8ba-128">Example 2: Start and complete a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
```

<span data-ttu-id="bd8ba-129">Mit diesen Befehlen wird eine Transaktion gestartet und dann abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-129">These commands start and then complete a transaction.</span></span>
<span data-ttu-id="bd8ba-130">Es werden keine Änderungen an der Registrierung vorgenommen, bis der **Complete-Transaction-** Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-130">No changes are made to the registry until the **Complete-Transaction** command is used.</span></span>

### <span data-ttu-id="bd8ba-131">Beispiel 3: Verwenden von unterschiedlichen Roll Back Einstellungen</span><span class="sxs-lookup"><span data-stu-id="bd8ba-131">Example 3: Use different rollback preferences</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

# Start-Transaction (-rollbackpreference error)

PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name ContosoCompany -UseTransaction

PS HKCU:\software> New-Item -Path . -Name "Contoso" -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  -Path . -Name ContosoCompany -UseTransaction

# Start-Transaction (-rollbackpreference never)

PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction

New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany                 {}
PS HKCU:\Software> Complete-Transaction

# Succeeds
```

<span data-ttu-id="bd8ba-132">In diesem Beispiel werden die Auswirkungen der Änderung des *Roll Back Preference* -Parameter Werts veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-132">This example demonstrates the effect of changing the *RollbackPreference* parameter value.</span></span>

<span data-ttu-id="bd8ba-133">In der ersten Befehls Reihe verwendet **Start-Transaction** keine *Rollback Preference* .</span><span class="sxs-lookup"><span data-stu-id="bd8ba-133">In the first set of commands, **Start-Transaction** does not use *RollbackPreference* .</span></span>
<span data-ttu-id="bd8ba-134">Daher wird der Standardwert (Error) verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-134">As a result, the default value (Error) is used.</span></span>
<span data-ttu-id="bd8ba-135">Wenn ein Fehler in einem Transaktions Befehl auftritt, d. h. der angegebene Pfad nicht vorhanden ist, wird für die Transaktion automatisch ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-135">When an error occurs in a transaction command, that is, the specified path does not exist, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="bd8ba-136">Im zweiten Satz von Befehlen verwendet **Start-Transaction** *Roll Back Preference* mit dem Wert Never.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-136">In the second set of commands, **Start-Transaction** uses *RollbackPreference* with a value of Never.</span></span>
<span data-ttu-id="bd8ba-137">Wenn ein Fehler in einem Transaktionsbefehl auftritt, ist die Transaktion daher weiterhin aktiv und kann erfolgreich abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-137">As a result, when an error occurs in a transaction command, the transaction is still active and can be completed successfully.</span></span>

<span data-ttu-id="bd8ba-138">Da die meisten Transaktionen ohne Fehler ausgeführt werden müssen, wird in der Regel der Standardwert von *Rollback Preference* bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-138">Because most transactions must be performed without error, the default value of *RollbackPreference* is typically preferred.</span></span>

### <span data-ttu-id="bd8ba-139">Beispiel 4: Verwenden Sie dieses Cmdlet, während eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-139">Example 4: Use this cmdlet while a transaction is in progress</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction
PS HKCU:\software> Get-Transaction
PS HKCU:\software> New-Item "ContosoCompany2" -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\Software> Get-Transaction
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

<span data-ttu-id="bd8ba-140">Dieses Beispiel zeigt die Auswirkung der Verwendung von **Start-Transaction** , während eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-140">This example shows the effect of using **Start-Transaction** while a transaction is in progress.</span></span>
<span data-ttu-id="bd8ba-141">Dies entspricht weitgehend dem Hinzufügen der ausgeführten Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-141">The effect is much like joining the transaction in progress.</span></span>

<span data-ttu-id="bd8ba-142">Obwohl es sich hierbei um einen vereinfachten Befehl handelt, tritt dieses Szenario häufig auf, wenn die Transaktion das Ausführen eines Skripts umfasst, das eine komplette Transaktion einschließt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-142">Although this is a simplified command, this scenario frequently occurs when the transaction involves running a script that includes a complete transaction.</span></span>

<span data-ttu-id="bd8ba-143">Der erste **Start-Transaction-** Befehl startet die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-143">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="bd8ba-144">Der erste **New-Item-** Befehl ist Teil der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-144">The first **New-Item** command is part of the transaction.</span></span>

<span data-ttu-id="bd8ba-145">Der zweite **Start-Transaction-** Befehl fügt der Transaktion einen neuen Abonnenten hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-145">The second **Start-Transaction** command adds a new subscriber to the transaction.</span></span>
<span data-ttu-id="bd8ba-146">Der **Get-Transaction-** Befehl gibt nun eine Transaktion mit der Abonnenten Anzahl 2 zurück.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-146">The **Get-Transaction** command now returns a transaction with a subscriber count of 2.</span></span>
<span data-ttu-id="bd8ba-147">Der zweite **New-Item-** Befehl ist Teil derselben Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-147">The second **New-Item** command is part of the same transaction.</span></span>

<span data-ttu-id="bd8ba-148">Es werden keine Änderungen an der Registrierung vorgenommen, bis die gesamte Transaktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-148">No changes are made to the registry until the whole transaction is completed.</span></span>
<span data-ttu-id="bd8ba-149">Zum Abschließen der Transaktion müssen Sie zwei **Complete-Transaction-** Befehle eingeben, einen für jeden Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-149">To complete the transaction, you must enter two **Complete-Transaction** commands, one for each subscriber.</span></span>
<span data-ttu-id="bd8ba-150">Wenn Sie die Transaktion an einem beliebigen Punkt zurücksetzen würden, würde für beide Abonnenten ein Rollback für die Transaktion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-150">If you were to roll back the transaction at any point, all the transaction would be rolled back for both subscribers.</span></span>

### <span data-ttu-id="bd8ba-151">Beispiel 5: Starten einer unabhängigen Transaktion, während eine Transaktion ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="bd8ba-151">Example 5: Start an independent transaction while one is in progress</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -Independent
PS HKCU:\software> Get-Transaction
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
MyKey
-----
123
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   1 MyCompany                      {MyKey}
```

<span data-ttu-id="bd8ba-152">Dieses Beispiel zeigt die Auswirkung der Verwendung des *unabhängigen* Parameters von **Start-Transaction** , um eine Transaktion zu starten, während eine andere Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-152">This example shows the effect of using the *Independent* parameter of **Start-Transaction** to start a transaction while another transaction is in progress.</span></span>
<span data-ttu-id="bd8ba-153">In diesem Fall wird die neue Transaktion zurückgesetzt, ohne dass dies Auswirkungen auf die ursprüngliche Transaktion hat.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-153">In this case, the new transaction is rolled back without affecting the original transaction.</span></span>

<span data-ttu-id="bd8ba-154">Obwohl die Transaktionen logisch unabhängig sind, da jeweils nur eine Transaktion aktiv sein kann, müssen Sie die neueste Transaktion zurücksetzen oder einen Commit ausführen, bevor Sie weiter mit der ursprünglichen Transaktion arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-154">Although the transactions are logically independent, because only one transaction can be active at a time, you must roll back or commit the newest transaction before resuming work on the original transaction.</span></span>

<span data-ttu-id="bd8ba-155">Mit dem ersten Satz von Befehlen wird eine Transaktion gestartet.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-155">The first set of commands starts a transaction.</span></span>
<span data-ttu-id="bd8ba-156">Der **New-Item-** Befehl ist Teil der ersten Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-156">The **New-Item** command is part of the first transaction.</span></span>

<span data-ttu-id="bd8ba-157">Im zweiten Satz von Befehlen verwendet der Befehl **Start-Transaction** den *unabhängigen* Parameter.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-157">In the second set of commands, the **Start-Transaction** command uses the *Independent* parameter.</span></span>
<span data-ttu-id="bd8ba-158">Der folgende **Get-Transaction-** Befehl zeigt das Transaktions Objekt für die aktive Transaktion, die das neueste ist.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-158">The **Get-Transaction** command that follows shows the transaction object for the active transaction, which is the newest one.</span></span>
<span data-ttu-id="bd8ba-159">Die Abonnenten Anzahl ist gleich 1 und zeigt an, dass die Transaktionen nicht verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-159">The subscriber count is equal to 1, that shows that the transactions are unrelated.</span></span>

<span data-ttu-id="bd8ba-160">Wenn ein Rollback für die aktive Transaktion mit einem Befehl **Rückgängig-Transaktion** ausgeführt wird, wird die ursprüngliche Transaktion wieder aktiv.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-160">When the active transaction is rolled back by using an **Undo-Transaction** command, the original transaction becomes active again.</span></span>

<span data-ttu-id="bd8ba-161">Der **New-ItemProperty-** Befehl, der Teil der ursprünglichen Transaktion ist, wird ohne Fehler beendet, und die ursprüngliche Transaktion kann mit dem **Complete-Transaction-** Befehl abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-161">The **New-ItemProperty** command, which is part of the original transaction, finishes without error, and the original transaction can be completed by using the **Complete-Transaction** command.</span></span>
<span data-ttu-id="bd8ba-162">Die Registrierung wird daraufhin geändert.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-162">As a result, the registry is changed.</span></span>

### <span data-ttu-id="bd8ba-163">Beispiel 6: Ausführen von Befehlen, die nicht Teil einer Transaktion sind</span><span class="sxs-lookup"><span data-stu-id="bd8ba-163">Example 6: Run commands that are not part of a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany1" -UseTransaction
PS HKCU:\software> New-Item "ContosoCompany2"
PS HKCU:\software> New-Item "ContosoCompany3" -UseTransaction
PS HKCU:\software> dir contoso*
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany2                {}

PS HKCU:\Software> Complete-Transaction
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany1                     {}
0   0 ContosoCompany2                     {}
0   0 ContosoCompany3                     {}
```

<span data-ttu-id="bd8ba-164">In diesem Beispiel wird veranschaulicht, dass Befehle, die gesendet werden, während eine Transaktion ausgeführt wird, in der Transaktion eingeschlossen oder nicht eingeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-164">This example demonstrates that commands that are submitted while a transaction is in progress can be included in the transaction or not included.</span></span>
<span data-ttu-id="bd8ba-165">Nur Befehle, die den *UseTransaction* -Parameter verwenden, sind Teil der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-165">Only commands that use the *UseTransaction* parameter are part of the transaction.</span></span>

<span data-ttu-id="bd8ba-166">Der erste und der dritte **New-Item-** Befehl verwenden den *UseTransaction* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-166">The first and third **New-Item** commands use the *UseTransaction* parameter.</span></span>
<span data-ttu-id="bd8ba-167">Diese Befehle sind Teil der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-167">These commands are part of the transaction.</span></span>
<span data-ttu-id="bd8ba-168">Da der zweite **New-Item-** Befehl den *UseTransaction* -Parameter nicht verwendet, ist er nicht Teil der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-168">Because the second **New-Item** command does not use the *UseTransaction* parameter, it is not part of the transaction.</span></span>

<span data-ttu-id="bd8ba-169">Der erste dir-Befehl zeigt den Effekt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-169">The first dir command shows the effect.</span></span>
<span data-ttu-id="bd8ba-170">Der zweite **New-Item-** Befehl wird sofort abgeschlossen, der erste und der dritte **New-Item-** Befehl werden jedoch erst wirksam, wenn für die Transaktion ein Commit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-170">The second **New-Item** command is completed immediately, but the first and third **New-Item** commands are not effective until the transaction is committed.</span></span>

<span data-ttu-id="bd8ba-171">Der **Complete-Transaction-** Befehl führt einen Commit für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-171">The **Complete-Transaction** command commits the transaction.</span></span>
<span data-ttu-id="bd8ba-172">Folglich zeigt der zweite dir-Befehl, dass alle neuen Elemente der Registrierung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-172">As a result, the second dir command shows that all of the new items are added to the registry.</span></span>

### <span data-ttu-id="bd8ba-173">Beispiel 7: Ausführen eines Rollbacks für eine Transaktion, die nicht in einem angegebenen Zeitraum beendet wird</span><span class="sxs-lookup"><span data-stu-id="bd8ba-173">Example 7: Roll back a transaction that does not finish in a specified time</span></span>

```
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> Get-Transaction
PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> > Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----------
Error                1                 RolledBack

PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  MyCompany -UseTransaction
```

<span data-ttu-id="bd8ba-174">Dieser Befehl verwendet den *Timeout* -Parameter von **Start-Transaction** , um eine Transaktion zu starten, die innerhalb von zwei Minuten abgeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-174">This command uses the *Timeout* parameter of **Start-Transaction** to start a transaction that must be completed within two minutes.</span></span>
<span data-ttu-id="bd8ba-175">Wenn die Transaktion bei Ablauf des Timeouts nicht abgeschlossen ist, wird automatisch ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-175">If the transaction is not finished when the time-out expires, it is rolled back automatically.</span></span>

<span data-ttu-id="bd8ba-176">Wenn das Timeout abläuft, werden Sie nicht benachrichtigt, die **Status** -Eigenschaft des Transaktions Objekts wird jedoch auf rolledback festgelegt, und Befehle, die den *UseTransaction* -Parameter verwenden, schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-176">When the time-out expires, you are not notified, but the **Status** property of the transaction object is set to RolledBack and commands that use the *UseTransaction* parameter fail.</span></span>

## <span data-ttu-id="bd8ba-177">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd8ba-177">PARAMETERS</span></span>

### <span data-ttu-id="bd8ba-178">-Unabhängig</span><span class="sxs-lookup"><span data-stu-id="bd8ba-178">-Independent</span></span>
<span data-ttu-id="bd8ba-179">Gibt an, dass dieses Cmdlet eine Transaktion startet, die unabhängig von Transaktionen ist, die gerade ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-179">Indicates that this cmdlet starts a transaction that is independent of any transactions in progress.</span></span>
<span data-ttu-id="bd8ba-180">Wenn Sie **Start-Transaction** verwenden, während eine andere Transaktion ausgeführt wird, wird der Transaktion standardmäßig ein neuer Abonnent hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-180">By default, if you use **Start-Transaction** while another transaction is in progress, a new subscriber is added to the transaction in progress.</span></span>
<span data-ttu-id="bd8ba-181">Dieser Parameter hat nur Auswirkungen, wenn bereits eine Transaktion in der Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-181">This parameter has an effect only when a transaction is already in progress in the session.</span></span>

<span data-ttu-id="bd8ba-182">Wenn Sie **Start-Transaction** verwenden, während eine Transaktion ausgeführt wird, wird das vorhandene Transaktions Objekt standardmäßig wieder verwendet, und die Abonnenten Anzahl wird erhöht.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-182">By default, if you use **Start-Transaction** while a transaction is in progress, the existing transaction object is reused and the subscriber count is incremented.</span></span>
<span data-ttu-id="bd8ba-183">Dies entspricht weitgehend dem Hinzufügen der ursprünglichen Transaktion.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-183">The effect is much like joining the original transaction.</span></span>
<span data-ttu-id="bd8ba-184">Ein Undo-Transaction Befehl führt einen Rollback für die gesamte Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-184">An Undo-Transaction command rolls back the whole the transaction.</span></span>
<span data-ttu-id="bd8ba-185">Zum Abschließen der Transaktion müssen Sie den Befehl %%amp;quot;Complete-Transaction%%amp;quot; für jeden Abonnenten eingeben.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-185">To complete the transaction, you must enter a Complete-Transaction command for each subscriber.</span></span>
<span data-ttu-id="bd8ba-186">Da die meisten Transaktionen, die gleichzeitig ausgeführt werden, miteinander in Zusammenhang stehen, ist der Standardwert in den meisten Fällen ausreichend.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-186">Because most transactions that are in progress at the same time are related, the default is sufficient for most uses.</span></span>

<span data-ttu-id="bd8ba-187">Wenn Sie den *unabhängigen* Parameter angeben, erstellt dieses Cmdlet eine neue Transaktion, die abgeschlossen oder rückgängig gemacht werden kann, ohne dass sich dies auf die ursprüngliche Transaktion auswirkt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-187">If you specify the *Independent* parameter, this cmdlet creates a new transaction that can be completed or undone without affecting the original transaction.</span></span>
<span data-ttu-id="bd8ba-188">Da jedoch nur jeweils eine Transaktion aktiv sein kann, müssen Sie die neue Transaktion abschließen oder zurücksetzen, bevor Sie mit der ursprünglichen Transaktion weiterarbeiten.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-188">However, because only one transaction can be active at a time, you must complete or roll back the new transaction before resuming work on the original transaction.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd8ba-189">-Rollbackpreference</span><span class="sxs-lookup"><span data-stu-id="bd8ba-189">-RollbackPreference</span></span>
<span data-ttu-id="bd8ba-190">Gibt die Bedingungen an, unter denen eine Transaktion automatisch zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-190">Specifies the conditions under which a transaction is automatically rolled back.</span></span>
<span data-ttu-id="bd8ba-191">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="bd8ba-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bd8ba-192">Fehler.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-192">Error.</span></span>
<span data-ttu-id="bd8ba-193">Die Transaktion wird automatisch zurückgesetzt, wenn ein Fehler mit oder ohne Abbruch auftritt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-193">The transaction is rolled back automatically if a terminating or non-terminating error occurs.</span></span>
- <span data-ttu-id="bd8ba-194">Terminatingerror.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-194">TerminatingError.</span></span>
<span data-ttu-id="bd8ba-195">Die Transaktion wird automatisch zurückgesetzt, wenn ein Fehler mit Abbruch auftritt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-195">The transaction is rolled back automatically if a terminating error occurs.</span></span>
- <span data-ttu-id="bd8ba-196">Nie</span><span class="sxs-lookup"><span data-stu-id="bd8ba-196">Never.</span></span>
<span data-ttu-id="bd8ba-197">Die Transaktion nie wird automatisch zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-197">The transaction is never rolled back automatically.</span></span>

<span data-ttu-id="bd8ba-198">Der Standardwert ist "Error".</span><span class="sxs-lookup"><span data-stu-id="bd8ba-198">The default value is Error.</span></span>

```yaml
Type: System.Management.Automation.RollbackSeverity
Parameter Sets: (All)
Aliases:
Accepted values: Error, TerminatingError, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd8ba-199">-Timeout</span><span class="sxs-lookup"><span data-stu-id="bd8ba-199">-Timeout</span></span>
<span data-ttu-id="bd8ba-200">Gibt die maximale Zeit in Minuten an, die die Transaktion aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-200">Specifies the maximum time, in minutes, that the transaction is active.</span></span>
<span data-ttu-id="bd8ba-201">Wenn das Timeout abläuft, wird die Transaktion automatisch zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-201">When the time-out expires, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="bd8ba-202">Standardmäßig gibt es kein Timeout für Transaktionen, die über die Befehlszeile gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-202">By default, there is no time-out for transactions that are started at the command line.</span></span>
<span data-ttu-id="bd8ba-203">Wenn Transaktionen von einem Skript gestartet werden, beträgt der Standardtimeoutwert 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-203">When transactions are started by a script, the default time-out is 30 minutes.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutMins

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd8ba-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bd8ba-204">-Confirm</span></span>
<span data-ttu-id="bd8ba-205">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-205">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd8ba-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bd8ba-206">-WhatIf</span></span>
<span data-ttu-id="bd8ba-207">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-207">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bd8ba-208">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-208">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd8ba-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bd8ba-209">CommonParameters</span></span>
<span data-ttu-id="bd8ba-210">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd8ba-211">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bd8ba-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd8ba-212">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bd8ba-212">INPUTS</span></span>

### <span data-ttu-id="bd8ba-213">Keine</span><span class="sxs-lookup"><span data-stu-id="bd8ba-213">None</span></span>
<span data-ttu-id="bd8ba-214">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="bd8ba-215">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bd8ba-215">OUTPUTS</span></span>

### <span data-ttu-id="bd8ba-216">Keine</span><span class="sxs-lookup"><span data-stu-id="bd8ba-216">None</span></span>
<span data-ttu-id="bd8ba-217">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="bd8ba-217">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bd8ba-218">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bd8ba-218">NOTES</span></span>

## <span data-ttu-id="bd8ba-219">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bd8ba-219">RELATED LINKS</span></span>

[<span data-ttu-id="bd8ba-220">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="bd8ba-220">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="bd8ba-221">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="bd8ba-221">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="bd8ba-222">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="bd8ba-222">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="bd8ba-223">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="bd8ba-223">Use-Transaction</span></span>](Use-Transaction.md)
