---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Transaction
ms.openlocfilehash: bb8e9e1f204c67207f31613181f856d3bcaf8dc3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200799"
---
# <span data-ttu-id="d6307-103">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="d6307-103">Get-Transaction</span></span>

## <span data-ttu-id="d6307-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d6307-104">SYNOPSIS</span></span>
<span data-ttu-id="d6307-105">Ruft die aktuelle (aktive) Transaktion ab.</span><span class="sxs-lookup"><span data-stu-id="d6307-105">Gets the current (active) transaction.</span></span>

## <span data-ttu-id="d6307-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d6307-106">SYNTAX</span></span>

```
Get-Transaction [<CommonParameters>]
```

## <span data-ttu-id="d6307-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d6307-107">DESCRIPTION</span></span>
<span data-ttu-id="d6307-108">Mit dem " **Get-Transaction"-** Cmdlet wird ein Objekt abgerufen, das die aktuelle Transaktion in der Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="d6307-108">The **Get-Transaction** cmdlet gets an object that represents the current transaction in the session.</span></span>

<span data-ttu-id="d6307-109">Dieses Cmdlet gibt nie mehr als ein Objekt zurück, da jeweils nur eine Transaktion aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="d6307-109">This cmdlet never returns more than one object, because only one transaction is active at a time.</span></span>
<span data-ttu-id="d6307-110">Wenn Sie eine oder mehrere unabhängige Transaktionen (mit dem Independent-Parameter von Start-Transaction) starten, ist die zuletzt gestartete Transaktion aktiv, und das ist die Transaktion, die von **Get-Transaction** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d6307-110">If you start one or more independent transactions (by using the Independent parameter of Start-Transaction), the most recently started transaction is active, and that is the transaction that **Get-Transaction** returns.</span></span>

<span data-ttu-id="d6307-111">Wenn für alle aktiven Transaktionen entweder ein Rollback oder ein Commit ausgeführt wurde, zeigt dieses Cmdlet die Transaktion an, die zuletzt in der Sitzung aktiv war.</span><span class="sxs-lookup"><span data-stu-id="d6307-111">When all active transactions have either been rolled back or committed, this cmdlet shows the transaction that was most recently active in the session.</span></span>

<span data-ttu-id="d6307-112">Dieses Cmdlet ist eine Reihe von Cmdlets, die das Transaktions Feature in Windows PowerShell unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d6307-112">This cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="d6307-113">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="d6307-113">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="d6307-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d6307-114">EXAMPLES</span></span>

### <span data-ttu-id="d6307-115">Beispiel 1: erhalten der aktuellen Transaktion</span><span class="sxs-lookup"><span data-stu-id="d6307-115">Example 1: Get the current transaction</span></span>

```
PS C:\> Start-Transaction
PS C:\> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="d6307-116">Dieser Befehl ruft mit dem Cmdlet %%amp;quot;Get-Transaction%%amp;quot; die aktuelle Transaktion ab.</span><span class="sxs-lookup"><span data-stu-id="d6307-116">This command uses the Get-Transaction cmdlet to get the current transaction.</span></span>

### <span data-ttu-id="d6307-117">Beispiel 2: Anzeigen der Eigenschaften und Methoden des Transaktions Objekts</span><span class="sxs-lookup"><span data-stu-id="d6307-117">Example 2: Show the properties and methods of the transaction object</span></span>

```
PS C:\> Get-Transaction | Get-Member

Name               MemberType Definition
----               ---------- ----------
Dispose            Method     System.Void Dispose(), System.Void Dispose(Boolean disposing)
Equals             Method     System.Boolean Equals(Object obj)
GetHashCode        Method     System.Int32 GetHashCode()
GetType            Method     System.Type GetType()
ToString           Method     System.String ToString()
IsCommitted        Property   System.Boolean IsCommitted {get;}
IsRolledBack       Property   System.Boolean IsRolledBack {get;}
RollbackPreference Property   System.Management.Automation.RollbackSeverity RollbackPreference {get;}
SubscriberCount    Property   System.Int32 SubscriberCount {get;set;}
```

<span data-ttu-id="d6307-118">Dieser Befehl zeigt mit dem Cmdlet %%amp;quot;Get-Member%%amp;quot; die Eigenschaften und Methoden des Transaktionsobjekts an.</span><span class="sxs-lookup"><span data-stu-id="d6307-118">This command uses the Get-Member cmdlet to show the properties and methods of the transaction object.</span></span>

### <span data-ttu-id="d6307-119">Beispiel 3: Anzeigen der Eigenschaftswerte einer Rollback-Transaktion</span><span class="sxs-lookup"><span data-stu-id="d6307-119">Example 3: Show the property values of a rolled back transaction</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Undo-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ----------
Error                0                 RolledBack
```

<span data-ttu-id="d6307-120">Dieser Befehl zeigt die Eigenschaftenwerte eines Transaktionsobjekts für eine Transaktion an, die zurückgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6307-120">This command shows the property values of a transaction object for a transaction that has been rolled back.</span></span>

### <span data-ttu-id="d6307-121">Beispiel 4: Anzeigen der Eigenschaftswerte einer Transaktion mit Commit</span><span class="sxs-lookup"><span data-stu-id="d6307-121">Example 4: Show the property values of a committed transaction</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

<span data-ttu-id="d6307-122">Dieser Befehl zeigt die Eigenschaftenwerte eines Transaktionsobjekts für eine Transaktion an, für die ein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6307-122">This command shows the property values of a transaction object for a transaction that has been committed.</span></span>

### <span data-ttu-id="d6307-123">Beispiel 5: Starten einer Transaktion, während eine andere Transaktion ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="d6307-123">Example 5: Start a transaction while another is in progress</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany2 -UseTransaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

<span data-ttu-id="d6307-124">In diesem Beispiel werden die Auswirkungen auf das Transaktionsobjekt veranschaulicht, wenn eine Transaktion gestartet wird, während eine andere Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6307-124">This example shows the effect on the transaction object of starting a transaction while another transaction is in progress.</span></span>
<span data-ttu-id="d6307-125">Dies geschieht normalerweise, wenn ein Skript, das eine Transaktion ausführt, eine Funktion enthält oder ein Skript aufruft, die bzw. das eine andere vollständige Transaktion enthält.</span><span class="sxs-lookup"><span data-stu-id="d6307-125">Typically, this happens when a script that runs a transaction includes a function or calls a script that contains another complete transaction.</span></span>

<span data-ttu-id="d6307-126">Wenn der zweite **Start-Transaction-** Befehl nicht den *Independent* -Parameter enthält, wird von **Start-Transaction** keine neue Transaktion erstellt.</span><span class="sxs-lookup"><span data-stu-id="d6307-126">Unless the second **Start-Transaction** command includes the *Independent* parameter, **Start-Transaction** does not create a new transaction.</span></span>
<span data-ttu-id="d6307-127">Stattdessen wird der ursprünglichen Transaktion ein zweiter Abonnent hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d6307-127">Instead, it adds a second subscriber to the original transaction.</span></span>

<span data-ttu-id="d6307-128">Der erste **Start-Transaction-** Befehl startet die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="d6307-128">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="d6307-129">Ein New-Item Befehl mit dem *UseTransaction* -Parameter ist Teil der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="d6307-129">A New-Item command with the *UseTransaction* parameter is part of the transaction.</span></span>

<span data-ttu-id="d6307-130">Ein zweiter **Start-Transaction-** Befehl fügt der Transaktion einen Abonnenten hinzu.</span><span class="sxs-lookup"><span data-stu-id="d6307-130">A second **Start-Transaction** command adds a subscriber to the transaction.</span></span>
<span data-ttu-id="d6307-131">Der nächste Befehl %%amp;quot;New-Item%%amp;quot; ist ebenfalls Teil der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="d6307-131">The next New-Item command is also part of the transaction.</span></span>

<span data-ttu-id="d6307-132">Der erste **Get-Transaction-** Befehl zeigt die Transaktion mit mehreren Abonnenten an.</span><span class="sxs-lookup"><span data-stu-id="d6307-132">The first **Get-Transaction** command shows the multi-subscriber transaction.</span></span>
<span data-ttu-id="d6307-133">Beachten Sie, dass die Abonnentenanzahl 2 beträgt.</span><span class="sxs-lookup"><span data-stu-id="d6307-133">Notice that the subscriber count is 2.</span></span>

<span data-ttu-id="d6307-134">Der erste Befehl %%amp;quot;Complete-Transaction%%amp;quot; führt keinen Commit für die Transaktion aus, die Abonnentenanzahl wird jedoch auf 1 verringert.</span><span class="sxs-lookup"><span data-stu-id="d6307-134">The first Complete-Transaction command does not commit the transaction, but it reduces the subscriber count to 1.</span></span>

<span data-ttu-id="d6307-135">Der zweite **Complete-Transaction-** Befehl führt einen Commit für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="d6307-135">The second **Complete-Transaction** command commits the transaction.</span></span>

### <span data-ttu-id="d6307-136">Beispiel 6: Starten einer unabhängigen Transaktion, während eine andere Transaktion ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="d6307-136">Example 6: Start an independent transaction while another is in progress</span></span>

```
PS C:\>
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Start-Transaction -Independent
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
```

<span data-ttu-id="d6307-137">In diesem Beispiel werden die Auswirkungen auf das Transaktionsobjekt veranschaulicht, wenn eine unabhängige Transaktion gestartet wird, während eine andere Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6307-137">This example shows the effect on the transaction object of starting an independent transaction while another transaction is in progress.</span></span>

<span data-ttu-id="d6307-138">Der erste **Start-Transaction-** Befehl startet die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="d6307-138">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="d6307-139">Ein **New-Item-** Befehl mit dem *UseTransaction* -Parameter ist Teil der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="d6307-139">A **New-Item** command with the *UseTransaction* parameter is part of the transaction.</span></span>

<span data-ttu-id="d6307-140">Ein zweiter **Start-Transaction-** Befehl fügt der Transaktion einen Abonnenten hinzu.</span><span class="sxs-lookup"><span data-stu-id="d6307-140">A second **Start-Transaction** command adds a subscriber to the transaction.</span></span>
<span data-ttu-id="d6307-141">Der nächste **New-Item-** Befehl ist auch Teil der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="d6307-141">The next **New-Item** command is also part of the transaction.</span></span>

<span data-ttu-id="d6307-142">Der erste **Get-Transaction-** Befehl zeigt die Transaktion mit mehreren Abonnenten an.</span><span class="sxs-lookup"><span data-stu-id="d6307-142">The first **Get-Transaction** command shows the multi-subscriber transaction.</span></span>
<span data-ttu-id="d6307-143">Beachten Sie, dass die Abonnentenanzahl 2 beträgt.</span><span class="sxs-lookup"><span data-stu-id="d6307-143">Note that the subscriber count is 2.</span></span>

<span data-ttu-id="d6307-144">Der **Complete-Transaction-** Befehl reduziert die Anzahl der Abonnenten auf 1, führt jedoch keinen Commit für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="d6307-144">The **Complete-Transaction** command reduces the subscriber count to 1, but it does not commit the transaction.</span></span>

<span data-ttu-id="d6307-145">Der zweite **Complete-Transaction-** Befehl führt einen Commit für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="d6307-145">The second **Complete-Transaction** command commits the transaction.</span></span>

## <span data-ttu-id="d6307-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d6307-146">PARAMETERS</span></span>

### <span data-ttu-id="d6307-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d6307-147">CommonParameters</span></span>
<span data-ttu-id="d6307-148">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d6307-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d6307-149">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d6307-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d6307-150">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d6307-150">INPUTS</span></span>

### <span data-ttu-id="d6307-151">Keine</span><span class="sxs-lookup"><span data-stu-id="d6307-151">None</span></span>
<span data-ttu-id="d6307-152">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="d6307-152">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="d6307-153">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d6307-153">OUTPUTS</span></span>

### <span data-ttu-id="d6307-154">System. Management. Automation. pstransaction</span><span class="sxs-lookup"><span data-stu-id="d6307-154">System.Management.Automation.PSTransaction</span></span>
<span data-ttu-id="d6307-155">Dieses Cmdlet gibt ein Objekt zurück, das die aktuelle Transaktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="d6307-155">This cmdlet returns an object that represents the current transaction.</span></span>

## <span data-ttu-id="d6307-156">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d6307-156">NOTES</span></span>

## <span data-ttu-id="d6307-157">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d6307-157">RELATED LINKS</span></span>

[<span data-ttu-id="d6307-158">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="d6307-158">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="d6307-159">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="d6307-159">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="d6307-160">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="d6307-160">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="d6307-161">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="d6307-161">Use-Transaction</span></span>](Use-Transaction.md)

[<span data-ttu-id="d6307-162">New-Item</span><span class="sxs-lookup"><span data-stu-id="d6307-162">New-Item</span></span>](New-Item.md)
