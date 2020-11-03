---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/use-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Use-Transaction
ms.openlocfilehash: db8423aef6dc4b25c4ddd13f9b29b774463c6a6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214356"
---
# <span data-ttu-id="50b99-103">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="50b99-103">Use-Transaction</span></span>

## <span data-ttu-id="50b99-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="50b99-104">SYNOPSIS</span></span>
<span data-ttu-id="50b99-105">Fügt den Skriptblock der aktiven Transaktion hinzu.</span><span class="sxs-lookup"><span data-stu-id="50b99-105">Adds the script block to the active transaction.</span></span>

## <span data-ttu-id="50b99-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="50b99-106">SYNTAX</span></span>

```
Use-Transaction [-TransactedScript] <ScriptBlock> [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="50b99-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="50b99-107">DESCRIPTION</span></span>
<span data-ttu-id="50b99-108">Das **use-Transaction-** Cmdlet fügt einer aktiven Transaktion einen Skriptblock hinzu.</span><span class="sxs-lookup"><span data-stu-id="50b99-108">The **Use-Transaction** cmdlet adds a script block to an active transaction.</span></span>
<span data-ttu-id="50b99-109">Dies ermöglicht eine transaktive Skripterstellung mithilfe von Transaktions aktivierten Microsoft .net Frameworkobjekten.</span><span class="sxs-lookup"><span data-stu-id="50b99-109">This enables you to do transacted scripting by using transaction-enabled Microsoft .NET Framework objects.</span></span>
<span data-ttu-id="50b99-110">Der Skriptblock darf nur transaktionsfähige .NET Framework-Objekte enthalten, z. B. Instanzen der Microsoft.PowerShell.Commands.Management.TransactedString-Klasse.</span><span class="sxs-lookup"><span data-stu-id="50b99-110">The script block can contain only transaction-enabled .NET Framework objects, such as instances of the Microsoft.PowerShell.Commands.Management.TransactedString class.</span></span>

<span data-ttu-id="50b99-111">Der *UseTransaction* -Parameter, der für die meisten Cmdlets optional ist, ist erforderlich, wenn Sie dieses Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="50b99-111">The *UseTransaction* parameter, which is optional for most cmdlets, is required when you use this cmdlet.</span></span>

<span data-ttu-id="50b99-112">**Use-Transaction** ist ein Satz von Cmdlets, die das Transaktions Feature in Windows PowerShell unterstützen.</span><span class="sxs-lookup"><span data-stu-id="50b99-112">**Use-Transaction** is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="50b99-113">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="50b99-113">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="50b99-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="50b99-114">EXAMPLES</span></span>

### <span data-ttu-id="50b99-115">Beispiel 1: Skripterstellung mithilfe eines transaktionsfähigen Objekts</span><span class="sxs-lookup"><span data-stu-id="50b99-115">Example 1: Script by using a transaction-enabled object</span></span>

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> $transactedString.ToString()
Hello
PS C:\> Use-Transaction -TransactedScript { $transactedString.ToString() } -UseTransaction
Hello, World
PS C:\> Complete-Transaction
PS C:\> $transactedString.ToString()
Hello, World
```

<span data-ttu-id="50b99-116">In diesem Beispiel wird gezeigt, wie **use-Transaction** verwendet wird, um ein Skript für ein Transaktions fähiges .NET Framework Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="50b99-116">This example shows how to use **Use-Transaction** to script against a transaction-enabled .NET Framework object.</span></span>
<span data-ttu-id="50b99-117">In diesem Fall ist das Objekt ein **transactedstring** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="50b99-117">In this case, the object is a **TransactedString** object.</span></span>

<span data-ttu-id="50b99-118">Der erste Befehl startet mit dem Cmdlet %%amp;quot;Start-Transaction%%amp;quot; eine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="50b99-118">The first command uses the Start-Transaction cmdlet to start a transaction.</span></span>

<span data-ttu-id="50b99-119">Der zweite Befehl verwendet den New-Object-Befehl, um ein **transactedstring** -Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="50b99-119">The second command uses the New-Object command to create a **TransactedString** object.</span></span>
<span data-ttu-id="50b99-120">Das Objekt wird in der Variablen %%amp;quot;$TransactedString%%amp;quot; gespeichert.</span><span class="sxs-lookup"><span data-stu-id="50b99-120">It stores the object in the $TransactedString variable.</span></span>

<span data-ttu-id="50b99-121">Der dritte und vierte Befehl verwenden die **Append** -Methode des **transactedstring** -Objekts, um dem Wert $TransactedString Text hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="50b99-121">The third and fourth commands both use the **Append** method of the **TransactedString** object to add text to the value of $TransactedString.</span></span>
<span data-ttu-id="50b99-122">Ein Befehl ist ein Teil der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="50b99-122">One command is part of the transaction.</span></span>
<span data-ttu-id="50b99-123">Der andere Befehl ist nicht.</span><span class="sxs-lookup"><span data-stu-id="50b99-123">The other command is not.</span></span>

<span data-ttu-id="50b99-124">Der dritte Befehl verwendet die **Append** -Methode der transaktiven Zeichenfolge, um Hello zum Wert von $TransactedString hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="50b99-124">The third command uses the **Append** method of the transacted string to add Hello to the value of $TransactedString.</span></span>
<span data-ttu-id="50b99-125">Da der Befehl nicht Teil der Transaktion ist, wird die Änderung sofort übernommen.</span><span class="sxs-lookup"><span data-stu-id="50b99-125">Because the command is not part of the transaction, the change is applied immediately.</span></span>

<span data-ttu-id="50b99-126">Der vierte Befehl verwendet **use-Transaction** , um der Zeichenfolge in der Transaktion Text hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="50b99-126">The fourth command uses **Use-Transaction** to add text to the string in the transaction.</span></span>
<span data-ttu-id="50b99-127">Der Befehl verwendet die **Append** -Methode, um dem Wert von $TransactedString ", World" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="50b99-127">The command uses the **Append** method to add ", World" to the value of $TransactedString.</span></span>
<span data-ttu-id="50b99-128">Der Befehl wird in geschweifte Klammern ( {} ) eingeschlossen, um einen Skriptblock zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="50b99-128">The command is enclosed in braces ( {} ) to make it a script block.</span></span>
<span data-ttu-id="50b99-129">Der *UseTransaction* -Parameter ist in diesem Befehl erforderlich.</span><span class="sxs-lookup"><span data-stu-id="50b99-129">The *UseTransaction* parameter is required in this command.</span></span>

<span data-ttu-id="50b99-130">Der fünfte und sechste Befehl verwenden die **Methode "** -Methode" des **transactedstring** -Objekts, um den Wert von " **transactedstring** " als Zeichenfolge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="50b99-130">The fifth and sixth commands use the **ToString** method of the **TransactedString** object to display the value of the **TransactedString** as a string.</span></span>
<span data-ttu-id="50b99-131">Auch hier ist ein Befehl Teil der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="50b99-131">Again, one command is part of the transaction.</span></span>
<span data-ttu-id="50b99-132">Bei der anderen Transaktion handelt es sich nicht um.</span><span class="sxs-lookup"><span data-stu-id="50b99-132">The other transaction is not.</span></span>

<span data-ttu-id="50b99-133">Der fünfte Befehl verwendet die **Methode "** ", um den aktuellen Wert der $TransactedString Variablen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="50b99-133">The fifth command uses the **ToString** method to display the current value of the $TransactedString variable.</span></span>
<span data-ttu-id="50b99-134">Da er kein Teil der Transaktion ist, wird nur der aktuelle Status der Zeichenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="50b99-134">Because it is not part of the transaction, it displays only the current state of the string.</span></span>

<span data-ttu-id="50b99-135">Der sechste Befehl verwendet **use-Transaction** , um denselben Befehl in der Transaktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="50b99-135">The sixth command uses **Use-Transaction** to run the same command in the transaction.</span></span>
<span data-ttu-id="50b99-136">Da der Befehl Teil der Transaktion ist, wird der aktuelle Wert der Zeichenfolge in der Transaktion angezeigt, ähnlich wie eine Vorschau der Transaktions Änderungen.</span><span class="sxs-lookup"><span data-stu-id="50b99-136">Because the command is part of the transaction, it displays the current value of the string in the transaction, much like a preview of the transaction changes.</span></span>

<span data-ttu-id="50b99-137">Der siebte Befehl führt mit dem Cmdlet %%amp;quot;Complete-Transaction%%amp;quot; einen Commit für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="50b99-137">The seventh command uses the Complete-Transaction cmdlet to commit the transaction.</span></span>

<span data-ttu-id="50b99-138">Der letzte Befehl zeigt mithilfe der Methode " **destring** " den resultierenden Wert der Variablen als Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="50b99-138">The final command uses the **ToString** method to display the resulting value of the variable as a string.</span></span>

### <span data-ttu-id="50b99-139">Beispiel 2: Rollback einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="50b99-139">Example 2: Roll back a transaction</span></span>

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> Undo-Transaction
PS C:\> $transactedString.ToString()
Hello
```

<span data-ttu-id="50b99-140">Dieses Beispiel zeigt die Auswirkungen des Rollbacks einer Transaktion, die **use-Transaction-** Befehle enthält.</span><span class="sxs-lookup"><span data-stu-id="50b99-140">This example shows the effect of rolling back a transaction that includes **Use-Transaction** commands.</span></span>
<span data-ttu-id="50b99-141">Wie alle Befehle in einer Transaktion werden die Transaktionsänderungen beim Zurücksetzen der Transaktion verworfen, und die Daten sind unverändert.</span><span class="sxs-lookup"><span data-stu-id="50b99-141">Like all commands in a transaction, when the transaction is rolled back, the transacted changes are discarded and the data is unchanged.</span></span>

<span data-ttu-id="50b99-142">Der erste Befehl verwendet **Start-Transaction** , um eine Transaktion zu starten.</span><span class="sxs-lookup"><span data-stu-id="50b99-142">The first command uses **Start-Transaction** to start a transaction.</span></span>

<span data-ttu-id="50b99-143">Der zweite Befehl verwendet **New-Object** , um ein **transactedstring** -Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="50b99-143">The second command uses **New-Object** to create a **TransactedString** object.</span></span>
<span data-ttu-id="50b99-144">Das Objekt wird in der Variablen %%amp;quot;$TransactedString%%amp;quot; gespeichert.</span><span class="sxs-lookup"><span data-stu-id="50b99-144">It stores the object in the $TransactedString variable.</span></span>

<span data-ttu-id="50b99-145">Der dritte Befehl, der nicht Teil der Transaktion ist, verwendet die **Append** -Methode, um dem Wert von $TransactedString "Hello" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="50b99-145">The third command, which is not part of the transaction, uses the **Append** method to add "Hello" to the value of $TransactedString.</span></span>

<span data-ttu-id="50b99-146">Der vierte Befehl verwendet **use-Transaction** , um einen anderen Befehl auszuführen, der die **Append** -Methode in der Transaktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="50b99-146">The fourth command uses **Use-Transaction** to run another command that uses the **Append** method in the transaction.</span></span>
<span data-ttu-id="50b99-147">Der Befehl verwendet die **Append** -Methode, um dem Wert von $TransactedString ", World" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="50b99-147">The command uses the **Append** method to add ", World" to the value of $TransactedString.</span></span>

<span data-ttu-id="50b99-148">Der fünfte Befehl setzt die Transaktion mit dem Cmdlet %%amp;quot;Undo-Transaction%%amp;quot; zurück.</span><span class="sxs-lookup"><span data-stu-id="50b99-148">The fifth command uses the Undo-Transaction cmdlet to roll back the transaction.</span></span>
<span data-ttu-id="50b99-149">Folglich werden alle Befehle, die in der Transaktion ausgeführt werden, rückgängig gemacht.</span><span class="sxs-lookup"><span data-stu-id="50b99-149">As a result, all commands performed in the transaction are reversed.</span></span>

<span data-ttu-id="50b99-150">Der letzte Befehl zeigt mithilfe der Methode " **destring** " den resultierenden Wert von "$TransactedString" als Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="50b99-150">The final command uses the **ToString** method to display the resulting value of $TransactedString as a string.</span></span>
<span data-ttu-id="50b99-151">Die Ergebnisse zeigen, dass nur die Änderungen, die außerhalb der Transaktion vorgenommen wurden, auf das-Objekt angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="50b99-151">The results show that only the changes that were made outside the transaction were applied to the object.</span></span>

## <span data-ttu-id="50b99-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="50b99-152">PARAMETERS</span></span>

### <span data-ttu-id="50b99-153">-Transactedscript</span><span class="sxs-lookup"><span data-stu-id="50b99-153">-TransactedScript</span></span>
<span data-ttu-id="50b99-154">Gibt den Skriptblock an, der in der Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50b99-154">Specifies the script block that is run in the transaction.</span></span>
<span data-ttu-id="50b99-155">Geben Sie einen beliebigen gültigen Skriptblock in geschweiften Klammern ({}) ein.</span><span class="sxs-lookup"><span data-stu-id="50b99-155">Enter any valid script block enclosed in braces ( { } ).</span></span>
<span data-ttu-id="50b99-156">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="50b99-156">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="50b99-157">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="50b99-157">-UseTransaction</span></span>
<span data-ttu-id="50b99-158">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="50b99-158">Includes the command in the active transaction.</span></span>
<span data-ttu-id="50b99-159">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50b99-159">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="50b99-160">Weitere Informationen finden Sie unter about_transactions.</span><span class="sxs-lookup"><span data-stu-id="50b99-160">For more information, see about_transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="50b99-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="50b99-161">CommonParameters</span></span>
<span data-ttu-id="50b99-162">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="50b99-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="50b99-163">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="50b99-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="50b99-164">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="50b99-164">INPUTS</span></span>

### <span data-ttu-id="50b99-165">Keine</span><span class="sxs-lookup"><span data-stu-id="50b99-165">None</span></span>
<span data-ttu-id="50b99-166">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="50b99-166">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="50b99-167">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="50b99-167">OUTPUTS</span></span>

### <span data-ttu-id="50b99-168">PSObject</span><span class="sxs-lookup"><span data-stu-id="50b99-168">PSObject</span></span>
<span data-ttu-id="50b99-169">Dieses Cmdlet gibt das Ergebnis der Transaktion zurück.</span><span class="sxs-lookup"><span data-stu-id="50b99-169">This cmdlet returns the result of the transaction.</span></span>

## <span data-ttu-id="50b99-170">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="50b99-170">NOTES</span></span>

* <span data-ttu-id="50b99-171">Der *UseTransaction* -Parameter schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="50b99-171">The *UseTransaction* parameter includes the command in the active transaction.</span></span> <span data-ttu-id="50b99-172">Da das **use-Transaction-** Cmdlet immer in Transaktionen verwendet wird, ist dieser Parameter erforderlich, damit jeder **use-Transaction-** Befehl wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="50b99-172">Because the **Use-Transaction** cmdlet is always used in transactions, this parameter is required to make any **Use-Transaction** command effective.</span></span>

*

## <span data-ttu-id="50b99-173">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="50b99-173">RELATED LINKS</span></span>

[<span data-ttu-id="50b99-174">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="50b99-174">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="50b99-175">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="50b99-175">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="50b99-176">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="50b99-176">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="50b99-177">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="50b99-177">Undo-Transaction</span></span>](Undo-Transaction.md)
