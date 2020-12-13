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
