---
description: Hier wird beschrieben, wie transaktive Vorgänge in PowerShell verwaltet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_transactions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Transactions
ms.openlocfilehash: 522e0f727754b0b0153571039f3bf3966d0abf20
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222479"
---
# <a name="about-transactions"></a><span data-ttu-id="63e4d-104">Informationen zu Transaktionen</span><span class="sxs-lookup"><span data-stu-id="63e4d-104">About Transactions</span></span>

## <a name="short-description"></a><span data-ttu-id="63e4d-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="63e4d-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="63e4d-106">Hier wird beschrieben, wie transaktive Vorgänge in PowerShell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-106">Describes how to manage transacted operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="63e4d-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="63e4d-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="63e4d-108">Transaktionen werden in PowerShell ab PowerShell 2,0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-108">Transactions are supported in PowerShell beginning in PowerShell 2.0.</span></span> <span data-ttu-id="63e4d-109">Diese Funktion ermöglicht es Ihnen, eine Transaktion zu starten, anzugeben, welche Befehle Teil der Transaktion sind, und einen Commit oder Rollback für eine Transaktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-109">This feature enables you to start a transaction, to indicate which commands are part of the transaction, and to commit or roll back a transaction.</span></span>

## <a name="about-transactions"></a><span data-ttu-id="63e4d-110">Informationen zu Transaktionen</span><span class="sxs-lookup"><span data-stu-id="63e4d-110">ABOUT TRANSACTIONS</span></span>

<span data-ttu-id="63e4d-111">In PowerShell besteht eine Transaktion aus einer Reihe von Befehlen, die als logische Einheit verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-111">In PowerShell, a transaction is a set of one or more commands that are managed as a logical unit.</span></span> <span data-ttu-id="63e4d-112">Eine Transaktion kann abgeschlossen werden ("Commit"), wodurch die von der Transaktion betroffenen Daten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-112">A transaction can be completed ("committed"), which changes data affected by the transaction.</span></span> <span data-ttu-id="63e4d-113">Oder eine Transaktion kann vollständig rückgängig gemacht werden ("Rollback"), damit die betroffenen Daten von der Transaktion nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-113">Or, a transaction can be completely undone ("rolled back") so that the affected data is not changed by the transaction.</span></span>

<span data-ttu-id="63e4d-114">Da die Befehle in einer Transaktion als Einheit verwaltet werden, wird entweder für alle Befehle ein Commit ausgeführt, oder für alle Befehle wird ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-114">Because the commands in a transaction are managed as a unit, either all commands are committed, or all commands are rolled back.</span></span>

<span data-ttu-id="63e4d-115">Transaktionen werden häufig in der Datenverarbeitung verwendet, insbesondere bei Daten Bank Vorgängen und für Finanztransaktionen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-115">Transactions are widely used in data processing, most notably in database operations and for financial transactions.</span></span> <span data-ttu-id="63e4d-116">Transaktionen werden meistens verwendet, wenn es sich bei dem ungünstigsten Szenario für einen Satz von Befehlen nicht um alle Fehler handelt, aber dass einige Befehle erfolgreich sind, während andere fehlschlagen, sodass das System in einem beschädigten, falschen oder nicht interpretierbaren Zustand ist, der schwer zu reparieren ist.</span><span class="sxs-lookup"><span data-stu-id="63e4d-116">Transactions are most often used when the worst-case scenario for a set of commands is not that they all fail, but that some commands succeed while others fail, leaving the system in a damaged, false, or uninterpretable state that is difficult to repair.</span></span>

## <a name="transaction-cmdlets"></a><span data-ttu-id="63e4d-117">Transaktions-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="63e4d-117">TRANSACTION CMDLETS</span></span>

<span data-ttu-id="63e4d-118">PowerShell umfasst mehrere Cmdlets, die für die Verwaltung von Transaktionen konzipiert sind.</span><span class="sxs-lookup"><span data-stu-id="63e4d-118">PowerShell includes several cmdlets designed for managing transactions.</span></span>

- <span data-ttu-id="63e4d-119">Start-Transaction: startet eine neue Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-119">Start-Transaction: Starts a new transaction.</span></span>
- <span data-ttu-id="63e4d-120">Use-Transaction: Fügt der Transaktion einen Befehl oder einen Ausdruck hinzu.</span><span class="sxs-lookup"><span data-stu-id="63e4d-120">Use-Transaction: Adds a command or expression to the transaction.</span></span> <span data-ttu-id="63e4d-121">Für den Befehl müssen Transaktions aktivierte Objekte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-121">The command must use transaction-enabled objects.</span></span>
- <span data-ttu-id="63e4d-122">Rückgängig-Transaktion: führt einen Rollback für die Transaktion aus, sodass keine Daten von der Transaktion geändert werden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-122">Undo-Transaction: Rolls back the transaction so that no data is changed by the transaction.</span></span>
- <span data-ttu-id="63e4d-123">Complete-Transaction: führt einen Commit für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="63e4d-123">Complete-Transaction: Commits the transaction.</span></span> <span data-ttu-id="63e4d-124">Die Daten, die von der Transaktion betroffen sind, werden geändert.</span><span class="sxs-lookup"><span data-stu-id="63e4d-124">The data affected by the transaction is changed.</span></span>
- <span data-ttu-id="63e4d-125">Get-Transaction: Ruft Informationen über die aktive Transaktion ab.</span><span class="sxs-lookup"><span data-stu-id="63e4d-125">Get-Transaction: Gets information about the active transaction.</span></span>

<span data-ttu-id="63e4d-126">Eine Liste der Transaktions-Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="63e4d-126">For a list of transaction cmdlets, type:</span></span>

```powershell
get-command *transaction
```

<span data-ttu-id="63e4d-127">Ausführliche Informationen zu den-Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="63e4d-127">For detailed information about the cmdlets, type:</span></span>

```powershell
get-help use-transaction -detailed
```

## <a name="transaction-enabled-elements"></a><span data-ttu-id="63e4d-128">transaktionsaktivierte Elemente</span><span class="sxs-lookup"><span data-stu-id="63e4d-128">TRANSACTION-ENABLED ELEMENTS</span></span>

<span data-ttu-id="63e4d-129">Um an einer Transaktion teilnehmen zu können, müssen sowohl das Cmdlet als auch der Anbieter Transaktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-129">To participate in a transaction, both the cmdlet and the provider must support transactions.</span></span> <span data-ttu-id="63e4d-130">Diese Funktion ist in die Objekte integriert, die von der Transaktion betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="63e4d-130">This feature is built in to the objects that are affected by the transaction.</span></span>

<span data-ttu-id="63e4d-131">Der PowerShell-Registrierungs Anbieter unterstützt Transaktionen in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="63e4d-131">The PowerShell Registry provider supports transactions in Windows Vista.</span></span> <span data-ttu-id="63e4d-132">Das transactedstring-Objekt (Microsoft. PowerShell. Commands. Management. transactedstring) funktioniert mit jedem Betriebssystem, auf dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="63e4d-132">The TransactedString object (Microsoft.PowerShell.Commands.Management.TransactedString) works with any operating system that runs PowerShell.</span></span>

<span data-ttu-id="63e4d-133">Andere PowerShell-Anbieter können Transaktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-133">Other PowerShell providers can support transactions.</span></span> <span data-ttu-id="63e4d-134">Um die PowerShell-Anbieter in Ihrer Sitzung zu finden, die Transaktionen unterstützen, verwenden Sie den folgenden Befehl, um den Wert "Transactions" in der Eigenschaft "Funktionen" der Anbieter zu finden:</span><span class="sxs-lookup"><span data-stu-id="63e4d-134">To find the PowerShell providers in your session that support transactions, use the following command to find the "Transactions" value in the Capabilities property of providers:</span></span>

```powershell
get-psprovider | where {$_.Capabilities -like "*transactions*"}
```

<span data-ttu-id="63e4d-135">Weitere Informationen zu einem Anbieter finden Sie in der Hilfe für den Anbieter.</span><span class="sxs-lookup"><span data-stu-id="63e4d-135">For more information about a provider, see the Help for the provider.</span></span> <span data-ttu-id="63e4d-136">Um die Anbieter Hilfe zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="63e4d-136">To get provider Help, type:</span></span>

```
get-help <provider-name>
```

<span data-ttu-id="63e4d-137">Wenn Sie z. B. Hilfe zum Registrierungsanbieter abrufen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="63e4d-137">For example, to get Help for the Registry provider, type:</span></span>

```powershell
get-help registry
```

## <a name="the-usetransaction-parameter"></a><span data-ttu-id="63e4d-138">der UseTransaction-Parameter.</span><span class="sxs-lookup"><span data-stu-id="63e4d-138">THE USETRANSACTION PARAMETER</span></span>

<span data-ttu-id="63e4d-139">Cmdlets, die Transaktionen unterstützen können, verfügen über einen UseTransaction-Parameter.</span><span class="sxs-lookup"><span data-stu-id="63e4d-139">Cmdlets that can support transactions have a UseTransaction parameter.</span></span> <span data-ttu-id="63e4d-140">Dieser Parameter schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="63e4d-140">This parameter includes the command in the active transaction.</span></span> <span data-ttu-id="63e4d-141">Sie können den vollständigen Parameternamen oder seinen Alias, "usetx", verwenden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-141">You can use the full parameter name or its alias, "usetx".</span></span>

<span data-ttu-id="63e4d-142">Der-Parameter kann nur verwendet werden, wenn die Sitzung eine aktive Transaktion enthält.</span><span class="sxs-lookup"><span data-stu-id="63e4d-142">The parameter can be used only when the session contains an active transaction.</span></span> <span data-ttu-id="63e4d-143">Wenn Sie einen Befehl mit dem UseTransaction-Parameter eingeben, wenn keine aktive Transaktion vorhanden ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="63e4d-143">If you enter a command with the UseTransaction parameter when there is no active transaction, the command fails.</span></span>

<span data-ttu-id="63e4d-144">Um Cmdlets mit dem UseTransaction-Parameter zu suchen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="63e4d-144">To find cmdlets with the UseTransaction parameter, type:</span></span>

```powershell
get-help * -parameter UseTransaction
```

<span data-ttu-id="63e4d-145">In PowerShell Core unterstützen alle Cmdlets, die für die Arbeit mit PowerShell-Anbietern entwickelt wurden, Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-145">In PowerShell core, all of the cmdlets designed to work with PowerShell providers support transactions.</span></span> <span data-ttu-id="63e4d-146">Daher können Sie die Anbieter-Cmdlets zum Verwalten von Transaktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-146">As a result, you can use the provider cmdlets to manage transactions.</span></span>

<span data-ttu-id="63e4d-147">Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="63e4d-147">For more information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

## <a name="the-transaction-object"></a><span data-ttu-id="63e4d-148">das Transaktions Objekt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-148">THE TRANSACTION OBJECT</span></span>

<span data-ttu-id="63e4d-149">Transaktionen werden in PowerShell durch ein Transaktions Objekt (System. Management. Automation. Transaction) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-149">Transactions are represented in PowerShell by a transaction object, System.Management.Automation.Transaction.</span></span>

<span data-ttu-id="63e4d-150">Das Objekt hat die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="63e4d-150">The object has the following properties:</span></span>

- <span data-ttu-id="63e4d-151">Rollbackpreference: enthält die Roll Back Einstellung, die für die aktuelle Transaktion festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="63e4d-151">RollbackPreference: Contains the rollback preference set for the current transaction.</span></span> <span data-ttu-id="63e4d-152">Sie können die Roll Back Einstellung festlegen, wenn Sie Start-Transaction verwenden, um die Transaktion zu starten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-152">You can set the rollback preference when you use Start-Transaction to start the transaction.</span></span>

  <span data-ttu-id="63e4d-153">Die Rollback-Einstellung bestimmt die Bedingungen, unter denen automatisch ein Rollback für die Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="63e4d-153">The rollback preference determines the conditions under which the transaction is rolled back automatically.</span></span> <span data-ttu-id="63e4d-154">Gültige Werte sind Error, terminatingerror und Never.</span><span class="sxs-lookup"><span data-stu-id="63e4d-154">Valid values are Error, TerminatingError, and Never.</span></span> <span data-ttu-id="63e4d-155">Der Standardwert ist "Error".</span><span class="sxs-lookup"><span data-stu-id="63e4d-155">The default value is Error.</span></span>

- <span data-ttu-id="63e4d-156">Status: enthält den aktuellen Status der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-156">Status: Contains the current status of the transaction.</span></span> <span data-ttu-id="63e4d-157">Gültige Werte sind "aktiv", "Commit" und "rolledback".</span><span class="sxs-lookup"><span data-stu-id="63e4d-157">Valid values are Active, Committed, and RolledBack.</span></span>

- <span data-ttu-id="63e4d-158">Abonnement Anzahl: enthält die Anzahl der Abonnenten der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-158">SubscriberCount: Contains the number of subscribers to the transaction.</span></span> <span data-ttu-id="63e4d-159">Ein Abonnent wird einer Transaktion hinzugefügt, wenn Sie eine Transaktion starten, während eine andere Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="63e4d-159">A subscriber is added to a transaction when you start a transaction while another transaction is in progress.</span></span> <span data-ttu-id="63e4d-160">Die Abonnenten Anzahl wird dekrementiert, wenn ein Abonnent einen Commit für die Transaktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-160">The subscriber count is decremented when a subscriber commits the transaction.</span></span>

## <a name="active-transactions"></a><span data-ttu-id="63e4d-161">aktive Transaktionen</span><span class="sxs-lookup"><span data-stu-id="63e4d-161">ACTIVE TRANSACTIONS</span></span>

<span data-ttu-id="63e4d-162">In PowerShell ist jeweils nur eine Transaktion aktiv, und Sie können nur die aktive Transaktion verwalten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-162">In PowerShell, only one transaction is active at a time, and you can manage only the active transaction.</span></span> <span data-ttu-id="63e4d-163">Mehrere Transaktionen können gleichzeitig in derselben Sitzung ausgeführt werden, aber nur die zuletzt gestartete Transaktion ist aktiv.</span><span class="sxs-lookup"><span data-stu-id="63e4d-163">Multiple transactions can be in progress in the same session at the same time, but only the most-recently started transaction is active.</span></span>

<span data-ttu-id="63e4d-164">Daher können Sie keine bestimmte Transaktion angeben, wenn Sie die Cmdlets für die Transaktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-164">As a result, you cannot specify a particular transaction when using the transaction cmdlets.</span></span> <span data-ttu-id="63e4d-165">Befehle gelten immer für die aktive Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-165">Commands always apply to the active transaction.</span></span>

<span data-ttu-id="63e4d-166">Dies ist am deutlichsten im Verhalten des Get-Transaction Cmdlets ersichtlich.</span><span class="sxs-lookup"><span data-stu-id="63e4d-166">This is most evident in the behavior of the Get-Transaction cmdlet.</span></span> <span data-ttu-id="63e4d-167">Wenn Sie einen Get-Transaction Befehl eingeben, erhält Get-Transaction immer nur ein Transaktions Objekt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-167">When you enter a Get-Transaction command, Get-Transaction always gets only one transaction object.</span></span> <span data-ttu-id="63e4d-168">Dieses Objekt ist das Objekt, das die aktive Transaktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-168">This object is the object that represents the active transaction.</span></span>

<span data-ttu-id="63e4d-169">Zum Verwalten einer anderen Transaktion müssen Sie zuerst die aktive Transaktion beenden, indem Sie entweder einen Commit durchführen oder einen Rollback ausführen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-169">To manage a different transaction, you must first finish the active transaction, either by committing it or rolling it back.</span></span> <span data-ttu-id="63e4d-170">Wenn Sie dies tun, wird die vorherige Transaktion automatisch aktiv.</span><span class="sxs-lookup"><span data-stu-id="63e4d-170">When you do this, the previous transaction becomes active automatically.</span></span> <span data-ttu-id="63e4d-171">Transaktionen werden in umgekehrter Reihenfolge aktiv, in der Sie gestartet werden, sodass die zuletzt gestartete Transaktion immer aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="63e4d-171">Transactions become active in the reverse of order of which they are started, so that the most recently started transaction is always active.</span></span>

## <a name="subscribers-and-independent-transactions"></a><span data-ttu-id="63e4d-172">Abonnenten und unabhängige Transaktionen</span><span class="sxs-lookup"><span data-stu-id="63e4d-172">SUBSCRIBERS AND INDEPENDENT TRANSACTIONS</span></span>

<span data-ttu-id="63e4d-173">Wenn Sie eine Transaktion starten, während eine andere Transaktion ausgeführt wird, wird von PowerShell standardmäßig keine neue Transaktion gestartet.</span><span class="sxs-lookup"><span data-stu-id="63e4d-173">If you start a transaction while another transaction is in progress, by default, PowerShell does not start a new transaction.</span></span> <span data-ttu-id="63e4d-174">Stattdessen wird der aktuellen Transaktion ein "Abonnent" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-174">Instead, it adds a "subscriber" to the current transaction.</span></span>

<span data-ttu-id="63e4d-175">Wenn eine Transaktion über mehrere Abonnenten verfügt, führt ein einzelner Undo-Transaction Befehl zu einem beliebigen Zeitpunkt ein Rollback für die gesamte Transaktion für alle Abonnenten aus.</span><span class="sxs-lookup"><span data-stu-id="63e4d-175">When a transaction has multiple subscribers, a single Undo-Transaction command at any point rolls back the entire transaction for all subscribers.</span></span> <span data-ttu-id="63e4d-176">Um einen Commit für die Transaktion durchführen zu können, müssen Sie jedoch einen Complete-Transaction Befehl für jeden Abonnenten eingeben.</span><span class="sxs-lookup"><span data-stu-id="63e4d-176">However, to commit the transaction, you must enter a Complete-Transaction command for every subscriber.</span></span>

<span data-ttu-id="63e4d-177">Um die Anzahl der Abonnenten einer Transaktion zu ermitteln, überprüfen Sie die Eigenschaft "abonniert" des Transaktions Objekts.</span><span class="sxs-lookup"><span data-stu-id="63e4d-177">To find the number of subscribers to a transaction, check the SubscriberCount property of the transaction object.</span></span> <span data-ttu-id="63e4d-178">Der folgende Befehl verwendet z. b. das Get-Transaction-Cmdlet, um den Wert der Eigenschaft "abonniert" der aktiven Transaktion zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="63e4d-178">For example, the following command uses the Get-Transaction cmdlet to get the value of the SubscriberCount property of the active transaction:</span></span>

```powershell
(Get-Transaction).SubscriberCount
```

<span data-ttu-id="63e4d-179">Das Hinzufügen eines Abonnenten ist das Standardverhalten, da die meisten Transaktionen, die gestartet werden, während eine andere Transaktion ausgeführt wird, mit der ursprünglichen Transaktion verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="63e4d-179">Adding a subscriber is the default behavior because most transactions that are started while another transaction is in progress are related to the original transaction.</span></span> <span data-ttu-id="63e4d-180">Im typischen Modell wird ein Skript, das eine Transaktion enthält, ein Hilfsskript aufrufen, das seine eigene Transaktion enthält.</span><span class="sxs-lookup"><span data-stu-id="63e4d-180">In the typical model, a script that contains a transaction calls a helper script that contains its own transaction.</span></span> <span data-ttu-id="63e4d-181">Da die Transaktionen verknüpft sind, sollten Sie als Einheit zurückgesetzt oder als Commit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-181">Because the transactions are related, they should be rolled back or committed as a unit.</span></span>

<span data-ttu-id="63e4d-182">Sie können jedoch eine Transaktion starten, die unabhängig von der aktuellen Transaktion ist, indem Sie den unabhängigen Parameter des Start-Transaction Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-182">However, you can start a transaction that is independent of the current transaction by using the Independent parameter of the Start-Transaction cmdlet.</span></span>

<span data-ttu-id="63e4d-183">Wenn Sie eine unabhängige Transaktion starten, erstellt Start-Transaction ein neues Transaktions Objekt, und die neue Transaktion wird zur aktiven Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-183">When you start an independent transaction, Start-Transaction creates a new transaction object, and the new transaction becomes the active transaction.</span></span>
<span data-ttu-id="63e4d-184">Für die unabhängige Transaktion kann ein Commit oder ein Rollback ausgeführt werden, ohne dass die ursprüngliche Transaktion beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="63e4d-184">The independent transaction can be committed or rolled back without affecting the original transaction.</span></span>

<span data-ttu-id="63e4d-185">Wenn die unabhängige Transaktion abgeschlossen ist (Commit oder Rollback), wird die ursprüngliche Transaktion wieder zur aktiven Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-185">When the independent transaction is finished (committed or rolled back), the original transaction becomes the active transaction again.</span></span>

## <a name="changing-data"></a><span data-ttu-id="63e4d-186">Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="63e4d-186">CHANGING DATA</span></span>

<span data-ttu-id="63e4d-187">Wenn Sie Transaktionen zum Ändern von Daten verwenden, werden die Daten, die von der Transaktion betroffen sind, erst geändert, wenn Sie einen Commit für die Transaktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-187">When you use transactions to change data, the data that is affected by the transaction is not changed until you commit the transaction.</span></span> <span data-ttu-id="63e4d-188">Die gleichen Daten können jedoch durch Befehle geändert werden, die nicht Teil der Transaktion sind.</span><span class="sxs-lookup"><span data-stu-id="63e4d-188">However, the same data can be changed by commands that are not part of the transaction.</span></span>

<span data-ttu-id="63e4d-189">Beachten Sie dies, wenn Sie Transaktionen verwenden, um freigegebene Daten zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-189">Keep this in mind when you are using transactions to manage shared data.</span></span>
<span data-ttu-id="63e4d-190">Datenbanken verfügen in der Regel über Mechanismen, die die Daten Sperren, während Sie daran arbeiten, sodass andere Benutzer und andere Befehle, Skripts und Funktionen nicht geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="63e4d-190">Typically, databases have mechanisms that lock the data while you are working on it, preventing other users, and other commands, scripts, and functions, from changing it.</span></span>

<span data-ttu-id="63e4d-191">Die Sperre ist jedoch eine Funktion der-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="63e4d-191">However, the lock is a feature of the database.</span></span> <span data-ttu-id="63e4d-192">Sie steht nicht im Zusammenhang mit Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-192">It is not related to transactions.</span></span> <span data-ttu-id="63e4d-193">Wenn Sie in einem Transaktions fähigen Dateisystem oder einem anderen Datenspeicher arbeiten, können die Daten geändert werden, während die Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="63e4d-193">If you are working in a transaction-enabled file system or other data store, the data can be changed while the transaction is in progress.</span></span>

## <a name="examples"></a><span data-ttu-id="63e4d-194">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="63e4d-194">EXAMPLES</span></span>

<span data-ttu-id="63e4d-195">In den Beispielen in diesem Abschnitt wird der PowerShell-Registrierungs Anbieter verwendet, und es wird davon ausgegangen, dass Sie damit vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="63e4d-195">The examples in this section use the PowerShell Registry provider and assume that you are familiar with it.</span></span> <span data-ttu-id="63e4d-196">Weitere Informationen zum Registrierungs Anbieter erhalten Sie, wenn Sie "Get-Help Registry" eingeben.</span><span class="sxs-lookup"><span data-stu-id="63e4d-196">For information about the Registry provider, type "get-help registry".</span></span>

### <a name="example-1-committing-a-transaction"></a><span data-ttu-id="63e4d-197">Beispiel 1: Commit für eine Transaktion</span><span class="sxs-lookup"><span data-stu-id="63e4d-197">EXAMPLE 1: COMMITTING A TRANSACTION</span></span>

<span data-ttu-id="63e4d-198">Verwenden Sie zum Erstellen einer Transaktion das Start-Transaction-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="63e4d-198">To create a transaction, use the Start-Transaction cmdlet.</span></span> <span data-ttu-id="63e4d-199">Der folgende Befehl startet eine Transaktion mit den Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-199">The following command starts a transaction with the default settings.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="63e4d-200">Wenn Sie Befehle in die Transaktion einschließen möchten, verwenden Sie den UseTransaction-Parameter des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="63e4d-200">To include commands in the transaction, use the UseTransaction parameter of the cmdlet.</span></span> <span data-ttu-id="63e4d-201">Standardmäßig sind Befehle nicht in der Transaktion enthalten,</span><span class="sxs-lookup"><span data-stu-id="63e4d-201">By default, commands are not included in the transaction,</span></span>

<span data-ttu-id="63e4d-202">Beispielsweise ist der folgende Befehl, der den aktuellen Speicherort im Software Schlüssel des HKCU:-Laufwerks festlegt, nicht in der Transaktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-202">For example, the following command, which sets the current location in the Software key of the HKCU: drive, is not included in the transaction.</span></span>

```powershell
cd hkcu:\Software
```

<span data-ttu-id="63e4d-203">Der folgende Befehl, der den Schlüssel MyCompany erstellt, verwendet den UseTransaction-Parameter des New-Item Cmdlets, um den Befehl in die aktive Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-203">The following command, which creates the MyCompany key, uses the UseTransaction parameter of the New-Item cmdlet to include the command in the active transaction.</span></span>

```powershell
new-item MyCompany -UseTransaction
```

<span data-ttu-id="63e4d-204">Der Befehl gibt ein Objekt zurück, das den neuen Schlüssel darstellt, aber da der Befehl Teil der Transaktion ist, wird die Registrierung noch nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="63e4d-204">The command returns an object that represents the new key, but because the command is part of the transaction, the registry is not yet changed.</span></span>

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyCompany                      {}
```

<span data-ttu-id="63e4d-205">Verwenden Sie das Cmdlet Complete-Transaction, um ein Commit für die Transaktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-205">To commit the transaction, use the Complete-Transaction cmdlet.</span></span> <span data-ttu-id="63e4d-206">Da Sie sich immer auf die aktive Transaktion auswirkt, können Sie die Transaktion nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="63e4d-206">Because it always affects the active transaction, you cannot specify the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="63e4d-207">Daher wird der Schlüssel "MyCompany" der Registrierung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-207">As a result, the MyCompany key is added to the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-2-rolling-back-a-transaction"></a><span data-ttu-id="63e4d-208">Beispiel 2: Rollback einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="63e4d-208">EXAMPLE 2: ROLLING BACK A TRANSACTION</span></span>

<span data-ttu-id="63e4d-209">Verwenden Sie zum Erstellen einer Transaktion das Start-Transaction-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="63e4d-209">To create a transaction, use the Start-Transaction cmdlet.</span></span> <span data-ttu-id="63e4d-210">Der folgende Befehl startet eine Transaktion mit den Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-210">The following command starts a transaction with the default settings.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="63e4d-211">Der folgende Befehl, der den myothercompany-Schlüssel erstellt, verwendet den UseTransaction-Parameter des New-Item-Cmdlets, um den Befehl in die aktive Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-211">The following command, which creates the MyOtherCompany key, uses the UseTransaction parameter of the New-Item cmdlet to include the command in the active transaction.</span></span>

```powershell
new-item MyOtherCompany -UseTransaction
```

<span data-ttu-id="63e4d-212">Der Befehl gibt ein Objekt zurück, das den neuen Schlüssel darstellt, aber da der Befehl Teil der Transaktion ist, wird die Registrierung noch nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="63e4d-212">The command returns an object that represents the new key, but because the command is part of the transaction, the registry is not yet changed.</span></span>

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyOtherCompany                 {}
```

<span data-ttu-id="63e4d-213">Verwenden Sie das Cmdlet "Undo-Transaction", um ein Rollback für die Transaktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-213">To roll back the transaction, use the Undo-Transaction cmdlet.</span></span> <span data-ttu-id="63e4d-214">Da Sie sich immer auf die aktive Transaktion auswirkt, wird die Transaktion nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="63e4d-214">Because it always affects the active transaction, you do not specify the transaction.</span></span>

```powershell
Undo-transaction
```

<span data-ttu-id="63e4d-215">Das Ergebnis ist, dass der Schlüssel "myothercompany" nicht zur Registrierung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="63e4d-215">The result is that the MyOtherCompany key is not added to the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-3-previewing-a-transaction"></a><span data-ttu-id="63e4d-216">Beispiel 3: Anzeigen einer Vorschau einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="63e4d-216">EXAMPLE 3: PREVIEWING A TRANSACTION</span></span>

<span data-ttu-id="63e4d-217">In der Regel werden die in einer Transaktion verwendeten Befehle geändert.</span><span class="sxs-lookup"><span data-stu-id="63e4d-217">Typically, the commands used in a transaction change data.</span></span> <span data-ttu-id="63e4d-218">Die Befehle, die Daten erhalten, sind aber auch in einer Transaktion nützlich, da Sie Daten innerhalb der Transaktion erhalten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-218">However, the commands that get data are useful in a transaction, too, because they get data inside of the transaction.</span></span> <span data-ttu-id="63e4d-219">Dadurch wird eine Vorschau der Änderungen bereitstellt, die durch das committen der Transaktion verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-219">This provides a preview of the changes that committing the transaction would cause.</span></span>

<span data-ttu-id="63e4d-220">Im folgenden Beispiel wird gezeigt, wie der Get-ChildItem-Befehl (der Alias ist "dir") verwendet wird, um eine Vorschau der Änderungen in einer Transaktion anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-220">The following example shows how to use the Get-ChildItem command (the alias is "dir") to preview the changes in a transaction.</span></span>

<span data-ttu-id="63e4d-221">Der folgende Befehl startet eine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-221">The following command starts a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="63e4d-222">Der folgende Befehl verwendet das Cmdlet "New-ItemProperty", um den Registrierungs Eintrag "MyKey" dem Schlüssel "MyCompany" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-222">The following command uses the New-ItemProperty cmdlet to add the MyKey registry entry to the MyCompany key.</span></span> <span data-ttu-id="63e4d-223">Der Befehl verwendet den UseTransaction-Parameter, um den Befehl in die Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-223">The command uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-itemproperty -path MyCompany -Name MyKey -value 123 -UseTransaction
```

<span data-ttu-id="63e4d-224">Der Befehl gibt ein Objekt zurück, das den neuen Registrierungs Eintrag darstellt, der Registrierungs Eintrag wird jedoch nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="63e4d-224">The command returns an object representing the new registry entry, but the registry entry is not changed.</span></span>

```
MyKey
-----
123
```

<span data-ttu-id="63e4d-225">Um die Elemente zu erhalten, die sich derzeit in der Registrierung befinden, verwenden Sie einen Get-ChildItem Befehl ("dir") ohne den UseTransaction-Parameter.</span><span class="sxs-lookup"><span data-stu-id="63e4d-225">To get the items that are currently in the registry, use a Get-ChildItem command ("dir") without the UseTransaction parameter.</span></span> <span data-ttu-id="63e4d-226">Mit dem folgenden Befehl werden Elemente abgerufen, die mit "M" beginnen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-226">The following command gets items that begin with "M."</span></span>

```powershell
dir m*
```

<span data-ttu-id="63e4d-227">Das Ergebnis zeigt, dass dem Schlüssel MyCompany noch keine Einträge hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-227">The result shows that no entries have yet been added to the MyCompany key.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

<span data-ttu-id="63e4d-228">Geben Sie einen Get-ChildItem ("dir")-Befehl mit dem UseTransaction-Parameter ein, um eine Vorschau der Auswirkungen des Commit der Transaktion anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-228">To preview the effect of committing the transaction, enter a Get-ChildItem ("dir") command with the UseTransaction parameter.</span></span> <span data-ttu-id="63e4d-229">Dieser Befehl verfügt über eine Ansicht der Daten aus der Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-229">This command has a view of the data from within the transaction.</span></span>

```powershell
dir m* -useTransaction
```

<span data-ttu-id="63e4d-230">Das Ergebnis zeigt, dass, wenn für die Transaktion ein Commit ausgeführt wird, der MyKey-Eintrag dem Schlüssel MyCompany hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="63e4d-230">The result shows that, if the transaction is committed, the MyKey entry will be added to the MyCompany key.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   1 MyCompany                      {MyKey}
```

### <a name="example-4-combining-transacted-and-non-transacted-commands"></a><span data-ttu-id="63e4d-231">Beispiel 4: Kombinieren von transaktiven und nicht transaktionalen Befehlen</span><span class="sxs-lookup"><span data-stu-id="63e4d-231">EXAMPLE 4: COMBINING TRANSACTED AND NON-TRANSACTED COMMANDS</span></span>

<span data-ttu-id="63e4d-232">Während einer Transaktion können nicht transaktive Befehle eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-232">You can enter non-transacted commands during a transaction.</span></span> <span data-ttu-id="63e4d-233">Die nicht transaktiven Befehle wirken sich sofort auf die Daten aus, Sie wirken sich jedoch nicht auf die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="63e4d-233">The non-transacted commands affect the data immediately, but they do not affect the transaction.</span></span>
<span data-ttu-id="63e4d-234">Der folgende Befehl startet eine Transaktion im Registrierungsschlüssel "HKCU: \ Software".</span><span class="sxs-lookup"><span data-stu-id="63e4d-234">The following command starts a transaction in the HKCU:\Software registry key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="63e4d-235">Die nächsten drei Befehle verwenden das Cmdlet "New-Item", um der Registrierung Schlüssel hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-235">The next three commands use the New-Item cmdlet to add keys to the registry.</span></span>
<span data-ttu-id="63e4d-236">Der erste und der dritte Befehl verwenden den UseTransaction-Parameter, um die Befehle in die Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-236">The first and third commands use the UseTransaction parameter to include the commands in the transaction.</span></span> <span data-ttu-id="63e4d-237">Mit dem zweiten Befehl wird der-Parameter ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-237">The second command omits the parameter.</span></span> <span data-ttu-id="63e4d-238">Da der zweite Befehl nicht in der Transaktion enthalten ist, wird er sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="63e4d-238">Because the second command is not included in the transaction, it is effective immediately.</span></span>

```powershell
new-item MyCompany1 -UseTransaction
new-item MyCompany2
new-item MyCompany3 -UseTransaction
```

<span data-ttu-id="63e4d-239">Um den aktuellen Status der Registrierung anzuzeigen, verwenden Sie einen Get-ChildItem ("dir")-Befehl ohne den UseTransaction-Parameter.</span><span class="sxs-lookup"><span data-stu-id="63e4d-239">To view the current state of the registry, use a Get-ChildItem ("dir") command without the UseTransaction parameter.</span></span> <span data-ttu-id="63e4d-240">Mit diesem Befehl werden Elemente abgerufen, die mit "M" beginnen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-240">This command gets items that begin with "M."</span></span>

```powershell
dir m*
```

<span data-ttu-id="63e4d-241">Das Ergebnis zeigt, dass die MyCompany2-Taste der Registrierung hinzugefügt wird, die Schlüssel MyCompany1 und MyCompany3, die Teil der Transaktion sind, jedoch nicht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="63e4d-241">The result shows that the MyCompany2 key is added to the registry, but the MyCompany1 and MyCompany3 keys, which are part of the transaction, are not added.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0    0 MyCompany2                     {}
```

<span data-ttu-id="63e4d-242">Der folgende Befehl führt einen Commit für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="63e4d-242">The following command commits the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="63e4d-243">Nun werden die Schlüssel, die als Teil der Transaktion hinzugefügt wurden, in der Registrierung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-243">Now, the keys that were added as part of the transaction appear in the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
83   1 Microsoft                      {(default)}
0    0 MyCompany1                     {}
0    0 MyCompany2                     {}
0    0 MyCompany3                     {}
```

### <a name="example-5-using-automatic-rollback"></a><span data-ttu-id="63e4d-244">Beispiel 5: Verwenden des automatischen Rollbacks</span><span class="sxs-lookup"><span data-stu-id="63e4d-244">EXAMPLE 5: USING AUTOMATIC ROLLBACK</span></span>

<span data-ttu-id="63e4d-245">Wenn ein Befehl in einer Transaktion einen Fehler generiert, wird für die Transaktion automatisch ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-245">When a command in a transaction generates an error of any kind, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="63e4d-246">Dieses Standardverhalten ist für Skripts konzipiert, die Transaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-246">This default behavior is designed for scripts that run transactions.</span></span> <span data-ttu-id="63e4d-247">Skripts werden in der Regel gut getestet und enthalten Fehler Behandlungs Logik, sodass keine Fehler zu erwarten sind und die Transaktion beendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="63e4d-247">Scripts are typically well tested and include error-handling logic, so errors are not expected and should terminate the transaction.</span></span>

<span data-ttu-id="63e4d-248">Der erste Befehl startet eine Transaktion im Registrierungsschlüssel "HKCU: \ Software".</span><span class="sxs-lookup"><span data-stu-id="63e4d-248">The first command starts a transaction in the HKCU:\Software registry key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="63e4d-249">Der folgende Befehl verwendet das Cmdlet "New-Item", um den Schlüssel "MyCompany" der Registrierung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-249">The following command uses the New-Item cmdlet to add the MyCompany key to the registry.</span></span> <span data-ttu-id="63e4d-250">Der Befehl verwendet den UseTransaction-Parameter (der Alias ist "usetx"), um den Befehl in die Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-250">The command uses the UseTransaction parameter (the alias is "usetx") to include the command in the transaction.</span></span>

```powershell
New-Item MyCompany -UseTX
```

<span data-ttu-id="63e4d-251">Da der Schlüssel MyCompany bereits in der Registrierung vorhanden ist, schlägt der Befehl fehl, und für die Transaktion wird ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-251">Because the MyCompany key already exists in the registry, the command fails, and the transaction is rolled back.</span></span>

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

<span data-ttu-id="63e4d-252">Ein Get-Transaction Befehl bestätigt, dass ein Rollback für die Transaktion ausgeführt wurde und dass der index count den Wert 0 aufweist.</span><span class="sxs-lookup"><span data-stu-id="63e4d-252">A Get-Transaction command confirms that the transaction has been rolled back and that the SubscriberCount is 0.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 RolledBack
```

### <a name="example-6-changing-the-rollback-preference"></a><span data-ttu-id="63e4d-253">Beispiel 6: Ändern der Roll Back Einstellung</span><span class="sxs-lookup"><span data-stu-id="63e4d-253">EXAMPLE 6: CHANGING THE ROLLBACK PREFERENCE</span></span>

<span data-ttu-id="63e4d-254">Wenn die Transaktion eher fehlertolerant sein soll, können Sie den Rollback Preference-Parameter von Start-Transaction verwenden, um die Einstellung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="63e4d-254">If you want the transaction to be more error tolerant, you can use the RollbackPreference parameter of Start-Transaction to change the preference.</span></span>

<span data-ttu-id="63e4d-255">Der folgende Befehl startet eine Transaktion mit der Rollback-Einstellung "Never".</span><span class="sxs-lookup"><span data-stu-id="63e4d-255">The following command starts a transaction with a rollback preference of "Never".</span></span>

```powershell
start-transaction -rollbackpreference Never
```

<span data-ttu-id="63e4d-256">Wenn in diesem Fall der Befehl fehlschlägt, wird für die Transaktion nicht automatisch ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-256">In this case, when the command fails, the transaction is not automatically rolled back.</span></span>

```powershell
New-Item MyCompany -UseTX
```

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

<span data-ttu-id="63e4d-257">Da die Transaktion noch aktiv ist, können Sie den Befehl als Teil der Transaktion erneut übermitteln.</span><span class="sxs-lookup"><span data-stu-id="63e4d-257">Because the transaction is still active, you can resubmit the command as part of the transaction.</span></span>

```powershell
New-Item MyOtherCompany -UseTX
```

### <a name="example-7-using-the-use-transaction-cmdlet"></a><span data-ttu-id="63e4d-258">Beispiel 7: Verwenden des Cmdlets "Use-Transaction"</span><span class="sxs-lookup"><span data-stu-id="63e4d-258">EXAMPLE 7: USING THE USE-TRANSACTION CMDLET</span></span>

<span data-ttu-id="63e4d-259">Mit dem-Cmdlet "Use-Transaction" können Sie direkte Skripts für Transaktions aktivierte Microsoft .NET Framework-Objekte ausführen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-259">The Use-Transaction cmdlet enables you to do direct scripting against transaction-enabled Microsoft .NET Framework objects.</span></span> <span data-ttu-id="63e4d-260">Use-Transaction nimmt einen Skriptblock an, der nur Befehle und Ausdrücke enthalten kann, die Transaktions fähige .NET Framework Objekte verwenden, wie z. b. Instanzen der Microsoft. PowerShell. Commands. Management. transactedstring-Klasse.</span><span class="sxs-lookup"><span data-stu-id="63e4d-260">Use-Transaction takes a script block that can only contain commands and expressions that use transaction-enabled .NET Framework objects, such as instances of the Microsoft.PowerShell.Commands.Management.TransactedString class.</span></span>

<span data-ttu-id="63e4d-261">Der folgende Befehl startet eine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-261">The following command starts a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="63e4d-262">Mit dem folgenden New-Object Befehl wird eine Instanz der transactedstring-Klasse erstellt und in der $t Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="63e4d-262">The following New-Object command creates an instance of the TransactedString class and saves it in the $t variable.</span></span>

```powershell
$t = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
```

<span data-ttu-id="63e4d-263">Der folgende Befehl verwendet die Append-Methode des transactedstring-Objekts, um der Zeichenfolge Text hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-263">The following command uses the Append method of the TransactedString object to add text to the string.</span></span> <span data-ttu-id="63e4d-264">Da der Befehl nicht Teil der Transaktion ist, wird die Änderung sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="63e4d-264">Because the command is not part of the transaction, the change is effective immediately.</span></span>

```powershell
$t.append("Windows")
```

<span data-ttu-id="63e4d-265">Der folgende Befehl verwendet die gleiche Append-Methode, um Text hinzuzufügen, fügt den Text jedoch als Teil der Transaktion hinzu.</span><span class="sxs-lookup"><span data-stu-id="63e4d-265">The following command uses the same Append method to add text, but it adds the text as part of the transaction.</span></span> <span data-ttu-id="63e4d-266">Der Befehl ist in geschweifte Klammern eingeschlossen und wird als Wert des ScriptBlock-Parameters von use-Transaction festgelegt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-266">The command is enclosed in braces, and it is set as the value of the ScriptBlock parameter of Use-Transaction.</span></span> <span data-ttu-id="63e4d-267">Der UseTransaction-Parameter (usetx) ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="63e4d-267">The UseTransaction parameter (UseTx) is required.</span></span>

```powershell
use-transaction {$t.append(" PowerShell")} -usetx
```

<span data-ttu-id="63e4d-268">Um den aktuellen Inhalt der transaktiven Zeichenfolge in $t anzuzeigen, verwenden Sie die Methode "-Methode" des transactedstring-Objekts.</span><span class="sxs-lookup"><span data-stu-id="63e4d-268">To see the current content of the transacted string in $t, use the ToString method of the TransactedString object.</span></span>

```powershell
$t.tostring()
```

<span data-ttu-id="63e4d-269">Die Ausgabe zeigt, dass nur die nicht transaktiven Änderungen wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="63e4d-269">The output shows that only the non-transacted changes are effective.</span></span>

```output
Windows
```

<span data-ttu-id="63e4d-270">Um den aktuellen Inhalt der transaktiven Zeichenfolge in $t innerhalb der Transaktion anzuzeigen, Betten Sie den Ausdruck in einen Use-Transaction-Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="63e4d-270">To see the current content of the transacted string in $t from within the transaction, embed the expression in a Use-Transaction command.</span></span>

```powershell
use-transaction {$s.tostring()} -usetx
```

<span data-ttu-id="63e4d-271">Die Ausgabe zeigt die Transaktions Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="63e4d-271">The output shows the transaction view.</span></span>

```output
PowerShell
```

<span data-ttu-id="63e4d-272">Der folgende Befehl führt einen Commit für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="63e4d-272">The following command commits the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="63e4d-273">So zeigen Sie die endgültige Zeichenfolge an:</span><span class="sxs-lookup"><span data-stu-id="63e4d-273">To see the final string:</span></span>

```
$t.tostring()
PowerShell
```

### <a name="example-8-managing-multi-subscriber-transactions"></a><span data-ttu-id="63e4d-274">Beispiel 8: Verwalten von Transaktionen mit mehreren Abonnenten</span><span class="sxs-lookup"><span data-stu-id="63e4d-274">EXAMPLE 8: MANAGING MULTI-SUBSCRIBER TRANSACTIONS</span></span>

<span data-ttu-id="63e4d-275">Wenn Sie eine Transaktion starten, während eine andere Transaktion ausgeführt wird, erstellt PowerShell standardmäßig keine zweite Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-275">When you start a transaction while another transaction is in progress, PowerShell does not create a second transaction by default.</span></span> <span data-ttu-id="63e4d-276">Stattdessen wird der aktuellen Transaktion ein Abonnent hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-276">Instead, it adds a subscriber to the current transaction.</span></span>

<span data-ttu-id="63e4d-277">Dieses Beispiel zeigt, wie Sie eine Transaktion mit mehreren Abonnenten anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-277">This example shows how to view and manage a multi-subscriber transaction.</span></span>

<span data-ttu-id="63e4d-278">Beginnen Sie, indem Sie eine Transaktion im Schlüssel "HKCU: \ Software" starten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-278">Begin by starting a transaction in the HKCU:\Software key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="63e4d-279">Der folgende Befehl verwendet den Get-Transaction-Befehl, um die aktive Transaktion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-279">The following command uses the Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="63e4d-280">Das Ergebnis zeigt das-Objekt, das die aktive Transaktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-280">The result shows the object that represents the active transaction.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="63e4d-281">Der folgende Befehl fügt der Registrierung den Schlüssel MyCompany hinzu.</span><span class="sxs-lookup"><span data-stu-id="63e4d-281">The following command adds the MyCompany key to the registry.</span></span> <span data-ttu-id="63e4d-282">Der Befehl verwendet den UseTransaction-Parameter, um den Befehl in die Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-282">The command uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-item MyCompany -UseTransaction
```

<span data-ttu-id="63e4d-283">Der folgende Befehl verwendet den Start-Transaction-Befehl, um eine Transaktion zu starten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-283">The following command uses the Start-Transaction command to start a transaction.</span></span> <span data-ttu-id="63e4d-284">Obwohl dieser Befehl an der Eingabeaufforderung eingegeben wird, ist dieses Szenario wahrscheinlicher, wenn Sie ein Skript ausführen, das eine Transaktion enthält.</span><span class="sxs-lookup"><span data-stu-id="63e4d-284">Although this command is typed at the command prompt, this scenario is more likely to happen when you run a script that contains a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="63e4d-285">Mit einem Get-Transaction-Befehl wird angezeigt, dass die Anzahl der Abonnenten für das Transaktions Objekt inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="63e4d-285">A Get-Transaction command shows that the subscriber count on the transaction object is incremented.</span></span> <span data-ttu-id="63e4d-286">Der Wert ist jetzt 2.</span><span class="sxs-lookup"><span data-stu-id="63e4d-286">The value is now 2.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

<span data-ttu-id="63e4d-287">Der nächste Befehl verwendet das Cmdlet "New-ItemProperty", um den Registrierungs Eintrag "MyKey" dem Schlüssel "MyCompany" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-287">The next command uses the New-ItemProperty cmdlet to add the MyKey registry entry to the MyCompany key.</span></span> <span data-ttu-id="63e4d-288">Der Befehl verwendet den UseTransaction-Parameter, um den Befehl in die Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-288">It uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-itemproperty -path MyCompany -name MyKey -UseTransaction
```

<span data-ttu-id="63e4d-289">Der Schlüssel MyCompany ist nicht in der Registrierung vorhanden, aber dieser Befehl ist erfolgreich, da die beiden Befehle Teil derselben Transaktion sind.</span><span class="sxs-lookup"><span data-stu-id="63e4d-289">The MyCompany key does not exist in the registry, but this command succeeds because the two commands are part of the same transaction.</span></span>

<span data-ttu-id="63e4d-290">Der folgende Befehl führt einen Commit für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="63e4d-290">The following command commits the transaction.</span></span> <span data-ttu-id="63e4d-291">Wenn für die Transaktion ein Rollback ausgeführt wird, wird für alle Abonnenten ein Rollback für die Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-291">If it rolled back the transaction, the transaction would be rolled back for all the subscribers.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="63e4d-292">Ein Get-Transaction Befehl zeigt, dass die Anzahl der Abonnenten für das Transaktions Objekt 1 beträgt, der Wert des Status jedoch noch aktiv (kein Commit) ist.</span><span class="sxs-lookup"><span data-stu-id="63e4d-292">A Get-Transaction command shows that the subscriber count on the transaction object is 1, but the value of Status is still Active (not Committed).</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="63e4d-293">Geben Sie einen zweiten Complete-Transaction-Befehl ein, um den Commit der Transaktion abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-293">To finish committing the transaction, enter a second Complete- Transaction command.</span></span> <span data-ttu-id="63e4d-294">Um einen Commit für eine Transaktion mit mehreren Abonnenten durchführen zu können, müssen Sie für jeden Start-Transaction Befehl einen Complete-Transaction Befehl eingeben.</span><span class="sxs-lookup"><span data-stu-id="63e4d-294">To commit a multi-subscriber transaction, you must enter one Complete-Transaction command for each Start-Transaction command.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="63e4d-295">Ein weiterer Get-Transaction Befehl zeigt, dass für die Transaktion ein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="63e4d-295">Another Get-Transaction command shows that the transaction has been committed.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 Committed
```

### <a name="example-9-managing-independent-transactions"></a><span data-ttu-id="63e4d-296">Beispiel 9: Verwalten unabhängiger Transaktionen</span><span class="sxs-lookup"><span data-stu-id="63e4d-296">EXAMPLE 9: MANAGING INDEPENDENT TRANSACTIONS</span></span>

<span data-ttu-id="63e4d-297">Wenn Sie eine Transaktion starten, während eine andere Transaktion ausgeführt wird, können Sie den unabhängigen Parameter von Start-Transaction verwenden, um die neue Transaktion unabhängig von der ursprünglichen Transaktion zu machen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-297">When you start a transaction while another transaction is in progress, you can use the Independent parameter of Start-Transaction to make the new transaction independent of the original transaction.</span></span>

<span data-ttu-id="63e4d-298">Wenn Sie dies tun, erstellt Start-Transaction ein neues Transaktions Objekt und macht die neue Transaktion zur aktiven Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-298">When you do, Start-Transaction creates a new transaction object and makes the new transaction the active transaction.</span></span>

<span data-ttu-id="63e4d-299">Beginnen Sie, indem Sie eine Transaktion im Schlüssel "HKCU: Software" Starten \\ .</span><span class="sxs-lookup"><span data-stu-id="63e4d-299">Begin by starting a transaction in the HKCU:\\Software key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="63e4d-300">Der folgende Befehl verwendet den Get-Transaction-Befehl, um die aktive Transaktion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-300">The following command uses the Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="63e4d-301">Das Ergebnis zeigt das-Objekt, das die aktive Transaktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-301">The result shows the object that represents the active transaction.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="63e4d-302">Mit dem folgenden Befehl wird der Registrierungsschlüssel MyCompany als Teil der Transaktion hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-302">The following command adds the MyCompany registry key as part of the transaction.</span></span> <span data-ttu-id="63e4d-303">Der Befehl verwendet den UseTransaction-Parameter (usetx), um den Befehl in die aktive Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-303">It uses the UseTransaction parameter (UseTx) to include the command in the active transaction.</span></span>

```powershell
new-item MyCompany -use
```

<span data-ttu-id="63e4d-304">Mit dem folgenden Befehl wird eine neue Transaktion gestartet.</span><span class="sxs-lookup"><span data-stu-id="63e4d-304">The following command starts a new transaction.</span></span> <span data-ttu-id="63e4d-305">Der Befehl verwendet den unabhängigen Parameter, um anzugeben, dass es sich bei dieser Transaktion nicht um einen Abonnenten der aktiven Transaktion handelt.</span><span class="sxs-lookup"><span data-stu-id="63e4d-305">The command uses the Independent parameter to indicate that this transaction is not a subscriber to the active transaction.</span></span>

```powershell
start-transaction -independent
```

<span data-ttu-id="63e4d-306">Wenn Sie eine unabhängige Transaktion erstellen, wird die neue Transaktion (zuletzt erstellt) zur aktiven Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-306">When you create an independent transaction, the new (most-recently created) transaction becomes the active transaction.</span></span> <span data-ttu-id="63e4d-307">Sie können einen Get-Transaction Befehl verwenden, um die aktive Transaktion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="63e4d-307">You can use a Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="63e4d-308">Beachten Sie, dass der Abonnement Zähler der Transaktion 1 ist, was bedeutet, dass keine anderen Abonnenten vorhanden sind und dass die Transaktion neu ist.</span><span class="sxs-lookup"><span data-stu-id="63e4d-308">Note that the SubscriberCount of the transaction is 1, indicating that there are no other subscribers and that the transaction is new.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="63e4d-309">Die neue Transaktion muss abgeschlossen (entweder ein Commit oder ein Rollback) sein, bevor Sie die ursprüngliche Transaktion verwalten können.</span><span class="sxs-lookup"><span data-stu-id="63e4d-309">The new transaction must be finished (either committed or rolled back) before you can manage the original transaction.</span></span>

<span data-ttu-id="63e4d-310">Der folgende Befehl fügt den Schlüssel "myothercompany" der Registrierung hinzu.</span><span class="sxs-lookup"><span data-stu-id="63e4d-310">The following command adds the MyOtherCompany key to the registry.</span></span> <span data-ttu-id="63e4d-311">Der Befehl verwendet den UseTransaction-Parameter (usetx), um den Befehl in die aktive Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="63e4d-311">It uses the UseTransaction parameter (UseTx) to include the command in the active transaction.</span></span>

```powershell
new-item MyOtherCompany -usetx
```

<span data-ttu-id="63e4d-312">Führen Sie nun ein Rollback für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="63e4d-312">Now, roll back the transaction.</span></span> <span data-ttu-id="63e4d-313">Wenn eine einzelne Transaktion mit zwei Abonnenten vorhanden ist, führt ein Rollback der Transaktion für alle Abonnenten ein Rollback für die gesamte Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="63e4d-313">If there were a single transaction with two subscribers, rolling back the transaction would roll back the entire transaction for all the subscribers.</span></span>

<span data-ttu-id="63e4d-314">Da diese Transaktionen jedoch unabhängig sind, werden durch das Rollback der neuesten Transaktion die Registrierungs Änderungen abgebrochen und die ursprüngliche Transaktion zur aktiven Transaktion.</span><span class="sxs-lookup"><span data-stu-id="63e4d-314">However, because these transactions are independent, rolling back the newest transaction cancels the registry changes and makes the original transaction the active transaction.</span></span>

```powershell
undo-transaction
```

<span data-ttu-id="63e4d-315">Ein Get-Transaction Befehl bestätigt, dass die ursprüngliche Transaktion in der Sitzung noch aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="63e4d-315">A Get-Transaction command confirms that the original transaction is still active in the session.</span></span>

```powershell
get-transaction
```

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="63e4d-316">Der folgende Befehl führt einen Commit für die aktive Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="63e4d-316">The following command commits the active transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="63e4d-317">Mit einem Get-ChildItem Befehl wird angezeigt, dass die Registrierung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="63e4d-317">A Get-ChildItem command shows that the registry has been changed.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

## <a name="see-also"></a><span data-ttu-id="63e4d-318">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="63e4d-318">SEE ALSO</span></span>

[<span data-ttu-id="63e4d-319">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="63e4d-319">Start-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Start-Transaction)

[<span data-ttu-id="63e4d-320">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="63e4d-320">Get-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Get-Transaction)

[<span data-ttu-id="63e4d-321">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="63e4d-321">Complete-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Complete-Transaction)

[<span data-ttu-id="63e4d-322">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="63e4d-322">Undo-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Undo-Transaction)

[<span data-ttu-id="63e4d-323">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="63e4d-323">Use-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Use-Transaction)

[<span data-ttu-id="63e4d-324">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="63e4d-324">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

[<span data-ttu-id="63e4d-325">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="63e4d-325">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

[<span data-ttu-id="63e4d-326">about_Providers</span><span class="sxs-lookup"><span data-stu-id="63e4d-326">about_Providers</span></span>](about_Providers.md)
