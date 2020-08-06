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
# <a name="how-to-support-transactions"></a>Unterstützen von Transaktionen

Dieses Beispiel zeigt die grundlegenden Code Elemente, die die Unterstützung für Transaktionen zu einem Cmdlet hinzufügen.

> [!IMPORTANT]
> Weitere Informationen zum Verarbeiten von Transaktionen in Windows PowerShell finden Sie unter [Informationen zu Transaktionen][about_Transactions].

## <a name="to-support-transactions"></a>So unterstützen Sie Transaktionen

1. Wenn Sie das Cmdlet-Attribut deklarieren, geben Sie an, dass das Cmdlet Transaktionen unterstützt.
   Wenn das Cmdlet Transaktionen unterstützt, fügt Windows PowerShell den `UseTransaction` Parameter zum Cmdlet hinzu, wenn es ausgeführt wird.

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. Fügen Sie innerhalb einer der Eingabe Verarbeitungsmethoden einen- `if` Block hinzu, um zu bestimmen, ob eine Transaktion verfügbar ist.
   Wenn die- `if` Anweisung in aufgelöst `true` wird, können die Aktionen innerhalb dieser Anweisung innerhalb des Kontexts der aktuellen Transaktion ausgeführt werden.

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
