---
title: Vorgehensweise beim unterstützen von Transaktionen | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 6fda27394091195b589afef5ee53c6d3bec4efc0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786610"
---
# <a name="how-to-support-transactions"></a><span data-ttu-id="e39ec-102">Unterstützen von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e39ec-102">How to Support Transactions</span></span>

<span data-ttu-id="e39ec-103">Dieses Beispiel zeigt die grundlegenden Code Elemente, die die Unterstützung für Transaktionen zu einem Cmdlet hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e39ec-103">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e39ec-104">Weitere Informationen zum Verarbeiten von Transaktionen in Windows PowerShell finden Sie unter [Informationen zu Transaktionen][about_Transactions].</span><span class="sxs-lookup"><span data-stu-id="e39ec-104">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="e39ec-105">So unterstützen Sie Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e39ec-105">To support transactions</span></span>

1. <span data-ttu-id="e39ec-106">Wenn Sie das Cmdlet-Attribut deklarieren, geben Sie an, dass das Cmdlet Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e39ec-106">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="e39ec-107">Wenn das Cmdlet Transaktionen unterstützt, fügt Windows PowerShell den `UseTransaction` Parameter zum Cmdlet hinzu, wenn es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e39ec-107">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="e39ec-108">Fügen Sie innerhalb einer der Eingabe Verarbeitungsmethoden einen- `if` Block hinzu, um zu bestimmen, ob eine Transaktion verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e39ec-108">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="e39ec-109">Wenn die- `if` Anweisung in aufgelöst `true` wird, können die Aktionen innerhalb dieser Anweisung innerhalb des Kontexts der aktuellen Transaktion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e39ec-109">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="e39ec-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e39ec-110">See Also</span></span>

[<span data-ttu-id="e39ec-111">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e39ec-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
