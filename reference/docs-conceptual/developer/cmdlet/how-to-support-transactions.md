---
ms.date: 09/13/2016
ms.topic: reference
title: Unterstützen von Transaktionen
description: Unterstützen von Transaktionen
ms.openlocfilehash: 5691c246830dab9f4808801c04353ebfb2c3e981
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666959"
---
# <a name="how-to-support-transactions"></a><span data-ttu-id="308dc-103">Unterstützen von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="308dc-103">How to Support Transactions</span></span>

<span data-ttu-id="308dc-104">Dieses Beispiel zeigt die grundlegenden Code Elemente, die die Unterstützung für Transaktionen zu einem Cmdlet hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="308dc-104">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="308dc-105">Weitere Informationen zum Verarbeiten von Transaktionen in Windows PowerShell finden Sie unter [Informationen zu Transaktionen][about_Transactions].</span><span class="sxs-lookup"><span data-stu-id="308dc-105">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="308dc-106">So unterstützen Sie Transaktionen</span><span class="sxs-lookup"><span data-stu-id="308dc-106">To support transactions</span></span>

1. <span data-ttu-id="308dc-107">Wenn Sie das Cmdlet-Attribut deklarieren, geben Sie an, dass das Cmdlet Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="308dc-107">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="308dc-108">Wenn das Cmdlet Transaktionen unterstützt, fügt Windows PowerShell den `UseTransaction` Parameter zum Cmdlet hinzu, wenn es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="308dc-108">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="308dc-109">Fügen Sie innerhalb einer der Eingabe Verarbeitungsmethoden einen- `if` Block hinzu, um zu bestimmen, ob eine Transaktion verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="308dc-109">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="308dc-110">Wenn die- `if` Anweisung in aufgelöst `true` wird, können die Aktionen innerhalb dieser Anweisung innerhalb des Kontexts der aktuellen Transaktion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="308dc-110">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="308dc-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="308dc-111">See Also</span></span>

[<span data-ttu-id="308dc-112">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="308dc-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
