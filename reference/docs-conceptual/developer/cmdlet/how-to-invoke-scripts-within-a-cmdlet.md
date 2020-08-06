---
title: Aufrufen von Skripts in einem Cmdlet | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 248ad7e2e35fe53682836d094a391023007fa0b7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784128"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="ed2f6-102">Aufrufen von Skripts in einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ed2f6-102">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="ed2f6-103">Dieses Beispiel zeigt, wie ein Skript aufgerufen wird, das für ein Cmdlet bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ed2f6-103">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="ed2f6-104">Das Skript wird vom Cmdlet ausgeführt, und die Ergebnisse werden an das Cmdlet als Sammlung von [System. Management. Automation. psobject](/dotnet/api/System.Management.Automation.PSObject) -Objekten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed2f6-104">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="ed2f6-105">So rufen Sie einen Skriptblock auf</span><span class="sxs-lookup"><span data-stu-id="ed2f6-105">To invoke a script block</span></span>

1. <span data-ttu-id="ed2f6-106">Mit dem Befehl wird überprüft, ob ein Skriptblock für das Cmdlet bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ed2f6-106">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="ed2f6-107">Wenn ein Skriptblock angegeben wurde, ruft der Befehl den Skriptblock mit den erforderlichen Parametern auf.</span><span class="sxs-lookup"><span data-stu-id="ed2f6-107">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

    ```csharp
    if (script != null)
    {
      WriteDebug("Executing script block.");

      // Invoke the script block with the required arguments.
      Collection<PSObject> PSObjects =
                     script.Invoke(
                                   line,
                                   simpleMatch,
                                   caseSensitive
                                  );
    ```

2. <span data-ttu-id="ed2f6-108">Anschließend durchläuft das Skript die zurückgegebene Auflistung von [System. Management. Automation. psobject](/dotnet/api/System.Management.Automation.PSObject) -Objekten und führt die erforderlichen Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="ed2f6-108">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

    ```c
    foreach (PSObject psObject in psObjects)
    {
      if (LanguagePrimitives.IsTrue(psObject))
      {
        result = new MatchInfo();
        result.Line = line;
        result.IgnoreCase = !caseSensitive;

        break;
      }
    }

    ```

## <a name="see-also"></a><span data-ttu-id="ed2f6-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed2f6-109">See Also</span></span>

[<span data-ttu-id="ed2f6-110">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ed2f6-110">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
