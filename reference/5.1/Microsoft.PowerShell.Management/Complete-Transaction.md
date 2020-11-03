---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/complete-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-Transaction
ms.openlocfilehash: 20fbdd86aab07dda065492eff2da4f358fb2ffca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215556"
---
# <span data-ttu-id="ae122-103">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="ae122-103">Complete-Transaction</span></span>

## <span data-ttu-id="ae122-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ae122-104">SYNOPSIS</span></span>
<span data-ttu-id="ae122-105">Führt einen Commit für die aktive Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="ae122-105">Commits the active transaction.</span></span>

## <span data-ttu-id="ae122-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ae122-106">SYNTAX</span></span>

```
Complete-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ae122-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ae122-107">DESCRIPTION</span></span>
<span data-ttu-id="ae122-108">Das **Complete-Transaction-** Cmdlet führt einen Commit für eine aktive Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="ae122-108">The **Complete-Transaction** cmdlet commits an active transaction.</span></span>
<span data-ttu-id="ae122-109">Wenn Sie für eine Transaktion einen Commit ausführen, werden die Befehle in der Transaktion abgeschlossen, und die von den Befehlen betroffenen Daten werden geändert.</span><span class="sxs-lookup"><span data-stu-id="ae122-109">When you commit a transaction, the commands in the transaction are finalized and the data affected by the commands is changed.</span></span>

<span data-ttu-id="ae122-110">Wenn die Transaktion mehrere Abonnenten umfasst, müssen Sie für jeden Start-Transaction Befehl einen **Complete-Transaction-** Befehl eingeben, um ein Commit für die Transaktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ae122-110">If the transaction includes multiple subscribers, to commit the transaction, you must enter one **Complete-Transaction** command for every Start-Transaction command.</span></span>

<span data-ttu-id="ae122-111">Das Cmdlet **Complete-Transaction** ist einer von einem Satz von Cmdlets, die das Transaktions Feature in Windows PowerShell unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ae122-111">The **Complete-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="ae122-112">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="ae122-112">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="ae122-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ae122-113">EXAMPLES</span></span>

### <span data-ttu-id="ae122-114">Beispiel 1: Commit für eine Transaktion ausführen</span><span class="sxs-lookup"><span data-stu-id="ae122-114">Example 1: Commit a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}
```

<span data-ttu-id="ae122-115">Dieses Beispiel zeigt, was geschieht, wenn Sie mit dem Cmdlet **Complete-Transaction** einen Commit für eine Transaktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="ae122-115">This example shows what happens when you use the **Complete-Transaction** cmdlet to commit a transaction.</span></span>

<span data-ttu-id="ae122-116">Der **Start-Transaction-** Befehl startet die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="ae122-116">The **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="ae122-117">Der New-Item Befehl verwendet den *UseTransaction* -Parameter, um den Befehl in die Transaktion einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="ae122-117">The New-Item command uses the *UseTransaction* parameter to include the command in the transaction.</span></span>

<span data-ttu-id="ae122-118">Der erste dir-Befehl (Get-ChildItem) zeigt an, dass das neue Element noch nicht zur Registrierung hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="ae122-118">The first dir (Get-ChildItem) command shows that the new item has not yet been added to the registry.</span></span>

<span data-ttu-id="ae122-119">Der **Complete-Transaction-** Befehl führt einen Commit für die Transaktion aus, wodurch die Registrierungs Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="ae122-119">The **Complete-Transaction** command commits the transaction, which makes the registry change effective.</span></span>
<span data-ttu-id="ae122-120">Folglich zeigt der zweite dir-Befehl, dass die Registrierung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="ae122-120">As a result, the second dir command shows that the registry is changed.</span></span>

### <span data-ttu-id="ae122-121">Beispiel 2: Commit für eine Transaktion mit mehreren Abonnenten</span><span class="sxs-lookup"><span data-stu-id="ae122-121">Example 2: Commit a transaction that has more than one subscriber</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
0   0 MyCompany                      {}

PS HKCU:\software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                2                Active

PS HKCU:\software> New-ItemProperty -Path MyCompany -Name MyKey -Value -UseTransaction

MyKey
-----
123

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                1                Active

PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   1 MyCompany                      {MyKey}
```

<span data-ttu-id="ae122-122">In diesem Beispiel wird gezeigt, wie mit **Complete-Transaction** ein Commit für eine Transaktion ausgeführt wird, die über mehr als einen Abonnenten verfügt.</span><span class="sxs-lookup"><span data-stu-id="ae122-122">This example shows how to use **Complete-Transaction** to commit a transaction that has more than one subscriber.</span></span>

<span data-ttu-id="ae122-123">Um einen Commit für eine Transaktion mit mehreren Abonnenten auszuführen, müssen Sie für jeden **Start-Transaction** -Befehl einen **Complete-Transaction-** Befehl eingeben.</span><span class="sxs-lookup"><span data-stu-id="ae122-123">To commit a multi-subscriber transaction, you must enter one **Complete-Transaction** command for every **Start-Transaction** command.</span></span>
<span data-ttu-id="ae122-124">Die Daten werden nur geändert, wenn der abschließende **Complete-Transaction-** Befehl übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="ae122-124">The data is changed only when the final **Complete-Transaction** command is submitted.</span></span>

<span data-ttu-id="ae122-125">Für Demonstrationszwecke werden in diesem Beispiel eine Reihe von Befehlen in der Befehlszeile eingegeben.</span><span class="sxs-lookup"><span data-stu-id="ae122-125">For demonstration purposes, this example shows a series of commands entered at the command line.</span></span>
<span data-ttu-id="ae122-126">In der Praxis werden Transaktionen häufig in Skripts ausgeführt, wobei die sekundäre Transaktion von einer Funktion oder einem Hilfsskript ausgeführt wird, das vom Hauptskript aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ae122-126">In practice, transactions are likely to be run in scripts, with the secondary transaction being run by a function or helper script that is called by the main script.</span></span>

<span data-ttu-id="ae122-127">In diesem Beispiel startet ein **Start-Transaction-** Befehl die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="ae122-127">In this example, a **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="ae122-128">Ein **New-Item-** Befehl mit dem *UseTransaction* -Parameter fügt den Schlüssel MyCompany zum Software Schlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae122-128">A **New-Item** command with the *UseTransaction* parameter adds the MyCompany key to the Software key.</span></span>
<span data-ttu-id="ae122-129">Obwohl das Cmdlet " **New-Item** " ein Schlüsselobjekt zurückgibt, werden die Daten in der Registrierung noch nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="ae122-129">Although the **New-Item** cmdlet returns a key object, the data in the registry is not yet changed.</span></span>

<span data-ttu-id="ae122-130">Ein zweiter **Start-Transaction-** Befehl fügt der vorhandenen Transaktion einen zweiten Abonnenten hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae122-130">A second **Start-Transaction** command adds a second subscriber to the existing transaction.</span></span>
<span data-ttu-id="ae122-131">Das Cmdlet **Get-Transaction** bestätigt, dass die Abonnenten Anzahl 2 beträgt.</span><span class="sxs-lookup"><span data-stu-id="ae122-131">The **Get-Transaction** cmdlet confirms that the subscriber count is 2.</span></span>
<span data-ttu-id="ae122-132">Ein New-ItemProperty Befehl mit dem *UseTransaction* -Parameter fügt dem neuen MyCompany-Schlüssel einen Registrierungs Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae122-132">A New-ItemProperty command with the *UseTransaction* parameter adds a registry entry to the new MyCompany key.</span></span>
<span data-ttu-id="ae122-133">Auch hier gibt der Befehl einen Wert zurück, die Registrierung wird jedoch nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="ae122-133">Again, the command returns a value, but the registry is not changed.</span></span>

<span data-ttu-id="ae122-134">Der erste **Complete-Transaction-** Befehl reduziert die Anzahl der Abonnenten um 1.</span><span class="sxs-lookup"><span data-stu-id="ae122-134">The first **Complete-Transaction** command reduces the subscriber count by 1.</span></span>
<span data-ttu-id="ae122-135">Dies wird durch einen **Get-Transaction-** Befehl bestätigt.</span><span class="sxs-lookup"><span data-stu-id="ae122-135">This is confirmed by a **Get-Transaction** command.</span></span>
<span data-ttu-id="ae122-136">Es werden jedoch keine Daten geändert, wie durch den Befehl dir m \* ( **Get-ChildItem** ) gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ae122-136">However, no data is changed, as evidenced by a dir m\* ( **Get-ChildItem** ) command.</span></span>

<span data-ttu-id="ae122-137">Der zweite **Complete-Transaction-** Befehl führt einen Commit für die gesamte Transaktion aus und ändert die Daten in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="ae122-137">The second **Complete-Transaction** command commits the entire transaction and changes the data in the registry.</span></span>
<span data-ttu-id="ae122-138">Dies wird durch einen zweiten Befehl "dir m \*" bestätigt, der die Änderungen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ae122-138">This is confirmed by a second dir m\* command, which shows the changes.</span></span>

### <span data-ttu-id="ae122-139">Beispiel 3: Ausführen einer Transaktion, bei der keine Daten geändert werden</span><span class="sxs-lookup"><span data-stu-id="ae122-139">Example 3: Perform a transaction that does not change any data</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> dir m* -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}

PS HKCU:\software> Complete-Transaction
```

<span data-ttu-id="ae122-140">Dieses Beispiel zeigt den Wert der Verwendung von get- \* Befehlen und anderer Befehle, die keine Daten in einer Transaktion ändern.</span><span class="sxs-lookup"><span data-stu-id="ae122-140">This example shows the value of using Get-\* commands, and other commands that do not change data, in a transaction.</span></span>
<span data-ttu-id="ae122-141">Wenn ein get- \* Command in einer Transaktion verwendet wird, werden die Objekte abgerufen, die Teil der Transaktion sind.</span><span class="sxs-lookup"><span data-stu-id="ae122-141">When a Get-\* command is used in a transaction, it gets the objects that are part of the transaction.</span></span>
<span data-ttu-id="ae122-142">So können Sie die Änderungen in der Transaktion in der Vorschau anzeigen, bevor ein Commit für die Änderungen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ae122-142">This allows you to preview the changes in the transaction before the changes are committed.</span></span>

<span data-ttu-id="ae122-143">In diesem Beispiel wird eine Transaktion gestartet.</span><span class="sxs-lookup"><span data-stu-id="ae122-143">In this example, a transaction is started.</span></span>
<span data-ttu-id="ae122-144">Ein New-Item Befehl mit dem *UseTransaction* -Parameter fügt der Registrierung als Teil der Transaktion einen neuen Schlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae122-144">A New-Item command with the *UseTransaction* parameter adds a new key to the registry as part of the transaction.</span></span>

<span data-ttu-id="ae122-145">Da der neue Registrierungsschlüssel der Registrierung erst hinzugefügt wird, wenn der Befehl **Complete-Transaction** ausgeführt wird, zeigt ein einfacher dir-Befehl ( **Get-ChildItem** ) die Registrierung ohne den neuen Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="ae122-145">Because the new registry key is not added to the registry until the **Complete-Transaction** command is run, a simple dir ( **Get-ChildItem** ) command shows the registry without the new key.</span></span>

<span data-ttu-id="ae122-146">Wenn Sie dem dir-Befehl jedoch den *UseTransaction* -Parameter hinzufügen, wird der Befehl Teil der Transaktion und ruft die Elemente in der Transaktion ab, auch wenn Sie den Daten noch nicht hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="ae122-146">However, when you add the *UseTransaction* parameter to the dir command, the command becomes part of the transaction, and it gets the items in the transaction even if they are not yet added to the data.</span></span>

## <span data-ttu-id="ae122-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ae122-147">PARAMETERS</span></span>

### <span data-ttu-id="ae122-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ae122-148">-Confirm</span></span>
<span data-ttu-id="ae122-149">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ae122-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ae122-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ae122-150">-WhatIf</span></span>
<span data-ttu-id="ae122-151">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ae122-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ae122-152">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ae122-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ae122-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ae122-153">CommonParameters</span></span>
<span data-ttu-id="ae122-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ae122-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ae122-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ae122-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ae122-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ae122-156">INPUTS</span></span>

### <span data-ttu-id="ae122-157">Keine</span><span class="sxs-lookup"><span data-stu-id="ae122-157">None</span></span>
<span data-ttu-id="ae122-158">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="ae122-158">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="ae122-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ae122-159">OUTPUTS</span></span>

### <span data-ttu-id="ae122-160">Keine</span><span class="sxs-lookup"><span data-stu-id="ae122-160">None</span></span>
<span data-ttu-id="ae122-161">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ae122-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ae122-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ae122-162">NOTES</span></span>

* <span data-ttu-id="ae122-163">Sie können keine Transaktion zurücksetzen, für die ein Commit ausgeführt wurde, oder einen Commit für eine Transaktion ausführen, die zurückgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="ae122-163">You cannot roll back a transaction that has been committed, or commit a transaction that has been rolled back.</span></span>

  <span data-ttu-id="ae122-164">Sie können keine andere Transaktion als die aktive Transaktion zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="ae122-164">You cannot roll back any transaction other than the active transaction.</span></span>
<span data-ttu-id="ae122-165">Zum Zurücksetzen einer anderen Transaktion müssen Sie zuerst einen Commit für die aktive Transaktion ausführen oder diese zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="ae122-165">To roll back a different transaction, you must first commit or roll back the active transaction.</span></span>

  <span data-ttu-id="ae122-166">Wenn für einen Teil einer Transaktion kein Commit ausgeführt werden kann, z. B. wenn ein Befehl in der Transaktion zu einem Fehler führt, wird standardmäßig die gesamte Transaktion zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ae122-166">By default, if any part of a transaction cannot be committed, such as when a command in the transaction results in an error, the entire transaction is rolled back.</span></span>

*

## <span data-ttu-id="ae122-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ae122-167">RELATED LINKS</span></span>

[<span data-ttu-id="ae122-168">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="ae122-168">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="ae122-169">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="ae122-169">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="ae122-170">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="ae122-170">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="ae122-171">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="ae122-171">Use-Transaction</span></span>](Use-Transaction.md)

[<span data-ttu-id="ae122-172">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="ae122-172">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="ae122-173">New-Item</span><span class="sxs-lookup"><span data-stu-id="ae122-173">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="ae122-174">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ae122-174">New-ItemProperty</span></span>](New-ItemProperty.md)
