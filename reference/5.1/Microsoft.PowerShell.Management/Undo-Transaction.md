---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/undo-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Undo-Transaction
ms.openlocfilehash: 1acb06ea7b05a2127b04a22c4c51b92cd68056f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214340"
---
# <span data-ttu-id="6a7f6-103">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="6a7f6-103">Undo-Transaction</span></span>

## <span data-ttu-id="6a7f6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6a7f6-104">SYNOPSIS</span></span>
<span data-ttu-id="6a7f6-105">Setzt die aktive Transaktion zurück.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-105">Rolls back the active transaction.</span></span>

## <span data-ttu-id="6a7f6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6a7f6-106">SYNTAX</span></span>

```
Undo-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6a7f6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6a7f6-107">DESCRIPTION</span></span>
<span data-ttu-id="6a7f6-108">Das **Undo-Transaction-** Cmdlet führt einen Rollback für die aktive Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-108">The **Undo-Transaction** cmdlet rolls back the active transaction.</span></span>
<span data-ttu-id="6a7f6-109">Wenn Sie ein Rollback für eine Transaktion ausführen, werden die von den Befehlen in der Transaktion vorgenommenen Änderungen verworfen, und die Daten werden in ihrer ursprünglichen Form wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-109">When you roll back a transaction, the changes that were made by the commands in the transaction are discarded and the data is restored to its original form.</span></span>

<span data-ttu-id="6a7f6-110">Wenn die Transaktion mehrere Abonnenten umfasst, führt ein **Rückgängig-Transaction-** Befehl ein Rollback für die gesamte Transaktion für alle Abonnenten aus.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-110">If the transaction includes multiple subscribers, an **Undo-Transaction** command rolls back the whole transaction for all subscribers.</span></span>

<span data-ttu-id="6a7f6-111">Standardmäßig werden Transaktionen automatisch zurückgesetzt, wenn ein Befehl in der Transaktion einen Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-111">By default, transactions are rolled back automatically if any command in the transaction generates an error.</span></span>
<span data-ttu-id="6a7f6-112">Transaktionen können jedoch mit einer anderen Roll Back Einstellung gestartet werden, und Sie können mit diesem Cmdlet jederzeit ein Rollback für die aktive Transaktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-112">However, transactions can be started by using a different rollback preference and you can use this cmdlet to roll back the active transaction at any time.</span></span>

<span data-ttu-id="6a7f6-113">Das **Undo-Transaction-** Cmdlet ist einer der Cmdlets, die das Transaktions Feature in Windows PowerShell unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-113">The **Undo-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="6a7f6-114">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-114">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="6a7f6-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6a7f6-115">EXAMPLES</span></span>

### <span data-ttu-id="6a7f6-116">Beispiel 1: Rollback der aktuellen Transaktion</span><span class="sxs-lookup"><span data-stu-id="6a7f6-116">Example 1: Roll back the current transaction</span></span>

```
PS C:\> Undo-Transaction
```

<span data-ttu-id="6a7f6-117">Mit diesem Befehl wird ein Rollback der aktuellen aktiven Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-117">This command rolls back the current, active, transaction.</span></span>

### <span data-ttu-id="6a7f6-118">Beispiel 2: starten und Rollback einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="6a7f6-118">Example 2: Start and roll back a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Undo-Transaction
```

<span data-ttu-id="6a7f6-119">In diesem Beispiel wird eine Transaktion gestartet und anschließend ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-119">This example starts a transaction and then rolls it back.</span></span>
<span data-ttu-id="6a7f6-120">Es werden daher keine Änderungen an der Registrierung vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-120">As a result, no changes are made to the registry.</span></span>

### <span data-ttu-id="6a7f6-121">Beispiel 3: Ausführen eines Rollbacks für eine Transaktion für alle Abonnenten</span><span class="sxs-lookup"><span data-stu-id="6a7f6-121">Example 3: Roll back a transaction for all subscribers</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                1                 Active

PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                2                 Active

PS HKCU:\Software> Undo-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                0                 RolledBack
```

<span data-ttu-id="6a7f6-122">In diesem Beispiel wird veranschaulicht, dass für die gesamte Transaktion für alle Abonnenten ein Rollback ausgeführt wird, wenn ein Abonnent eine Transaktion zurücksetzt.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-122">This example demonstrates that when any subscriber rolls back a transaction, the whole transaction is rolled back for all subscribers.</span></span>

<span data-ttu-id="6a7f6-123">Mit dem ersten Befehl wird der Speicherort des Registrierungsschlüssels %%amp;quot;HKCU:\Software%%amp;quot; geändert.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-123">The first command changes the location to the HKCU:\Software registry key.</span></span>

<span data-ttu-id="6a7f6-124">Der zweite Befehl startet eine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-124">The second command starts a transaction.</span></span>

<span data-ttu-id="6a7f6-125">Der dritte Befehl erstellt mit dem Cmdlet %%amp;quot;New-Item%%amp;quot; einen neuen Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-125">The third command uses the New-Item cmdlet to create a new registry key.</span></span>
<span data-ttu-id="6a7f6-126">Der Befehl verwendet den *UseTransaction* -Parameter, um die Änderung in die Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-126">The command uses the *UseTransaction* parameter to include the change in the transaction.</span></span>

<span data-ttu-id="6a7f6-127">Der vierte Befehl ruft mit dem Cmdlet %%amp;quot;Get-Transaction%%amp;quot; die aktive Transaktion ab.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-127">The fourth command uses the Get-Transaction cmdlet to get the active transaction.</span></span>
<span data-ttu-id="6a7f6-128">Beachten Sie, dass der Status %%amp;quot;Aktiv%%amp;quot; ist und die Anzahl der Abonnenten 1 lautet.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-128">Notice that the status is Active and the subscriber count is 1.</span></span>

<span data-ttu-id="6a7f6-129">Der fünfte Befehl verwendet wieder den Befehl %%amp;quot;Start-Transaction%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-129">The fifth command uses the Start-Transaction command again.</span></span>
<span data-ttu-id="6a7f6-130">Das Starten einer Transaktion während einer anderen Transaktion erfolgt in der Regel, wenn ein von der Haupt Transaktion verwendetes Skript eine eigene, komplette Transaktion enthält.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-130">Typically, starting a transaction while another transaction is in progress occurs when a script that is used by the main transaction includes its own complete transaction.</span></span>
<span data-ttu-id="6a7f6-131">Dieses Beispiel wird interaktiv ausgeführt, sodass Sie es in Phasen untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-131">This example is performed interactively so that you can examine it in stages.</span></span>
<span data-ttu-id="6a7f6-132">Wenn Sie einen **Start-Transaction-** Befehl ausführen, während eine andere Transaktion ausgeführt wird, verknüpfen die Befehle die vorhandene Transaktion als neuer Abonnent, und die Abonnenten Anzahl wird inkrementiert.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-132">When you run a **Start-Transaction** command while another transaction is in progress, the commands join the existing transaction as a new subscriber and the subscriber count is incremented.</span></span>

<span data-ttu-id="6a7f6-133">Der sechste Befehl verwendet das **Get-Transaction-** Cmdlet, um die aktive Transaktion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-133">The sixth command uses the **Get-Transaction** cmdlet to get the active transaction.</span></span>
<span data-ttu-id="6a7f6-134">Beachten Sie, dass die Abonnentenanzahl nun 2 lautet.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-134">Notice that the subscriber count is now 2.</span></span>

<span data-ttu-id="6a7f6-135">Der siebte Befehl verwendet die **Rückgängig-Transaktion** , um ein Rollback für die Transaktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-135">The seventh command uses **Undo-Transaction** to roll back the transaction.</span></span>
<span data-ttu-id="6a7f6-136">Dieser Befehl gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-136">This command does not return any objects.</span></span>

<span data-ttu-id="6a7f6-137">Der letzte Befehl ist ein **Get-Transaction-** Befehl, mit dem der aktive oder in diesem Fall die zuletzt aktive Transaktion abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-137">The final command is a **Get-Transaction** command that gets the active, or in this case, the most recently active, transaction.</span></span>
<span data-ttu-id="6a7f6-138">Das Ergebnis zeigt, dass die Transaktion zurückgesetzt wurde und dass die Abonnentenanzahl den Wert %%amp;quot;0%%amp;quot; aufweist. Dies gibt an, dass die Transaktion für alle Abonnenten zurückgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-138">The results show that the transaction is rolled back, and that the subscriber count is 0, showing that the transaction was rolled back for all subscribers.</span></span>

## <span data-ttu-id="6a7f6-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6a7f6-139">PARAMETERS</span></span>

### <span data-ttu-id="6a7f6-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6a7f6-140">-Confirm</span></span>
<span data-ttu-id="6a7f6-141">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6a7f6-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6a7f6-142">-WhatIf</span></span>
<span data-ttu-id="6a7f6-143">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-143">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6a7f6-144">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6a7f6-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6a7f6-145">CommonParameters</span></span>
<span data-ttu-id="6a7f6-146">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6a7f6-147">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6a7f6-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6a7f6-148">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6a7f6-148">INPUTS</span></span>

### <span data-ttu-id="6a7f6-149">Keine</span><span class="sxs-lookup"><span data-stu-id="6a7f6-149">None</span></span>
<span data-ttu-id="6a7f6-150">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-150">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="6a7f6-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6a7f6-151">OUTPUTS</span></span>

### <span data-ttu-id="6a7f6-152">Keine</span><span class="sxs-lookup"><span data-stu-id="6a7f6-152">None</span></span>
<span data-ttu-id="6a7f6-153">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="6a7f6-154">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6a7f6-154">NOTES</span></span>

* <span data-ttu-id="6a7f6-155">Sie können keine Transaktion zurücksetzen, für die ein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-155">You cannot roll back a transaction that has been committed.</span></span>

  <span data-ttu-id="6a7f6-156">Sie können keine andere Transaktion als die aktive Transaktion zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-156">You cannot roll back any transaction other than the active transaction.</span></span>
<span data-ttu-id="6a7f6-157">Zum Zurücksetzen einer anderen, unabhängigen Transaktion müssen Sie zuerst einen Commit für die aktive Transaktion ausführen oder diese zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-157">To roll back a different, independent transaction, you must first commit or roll back the active transaction.</span></span>

  <span data-ttu-id="6a7f6-158">Das Zurücksetzen der Transaktion beendet diese.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-158">Rolling back the transaction ends the transaction.</span></span>
<span data-ttu-id="6a7f6-159">Wenn Sie eine Transaktion wiederverwenden möchten, müssen Sie eine neue Transaktion starten.</span><span class="sxs-lookup"><span data-stu-id="6a7f6-159">To use a transaction again, you must start a new transaction.</span></span>

## <span data-ttu-id="6a7f6-160">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6a7f6-160">RELATED LINKS</span></span>

[<span data-ttu-id="6a7f6-161">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="6a7f6-161">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="6a7f6-162">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="6a7f6-162">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="6a7f6-163">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="6a7f6-163">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="6a7f6-164">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="6a7f6-164">Use-Transaction</span></span>](Use-Transaction.md)
