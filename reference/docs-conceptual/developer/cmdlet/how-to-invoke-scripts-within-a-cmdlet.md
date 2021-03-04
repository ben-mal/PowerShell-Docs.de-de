---
ms.date: 09/13/2016
ms.topic: reference
title: Aufrufen von Skripts in einem Cmdlet
description: Aufrufen von Skripts in einem Cmdlet
ms.openlocfilehash: 503ecb8913fe61ef3f5ec6fe969c22c2319a4f12
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685346"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="429e5-103">Aufrufen von Skripts in einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="429e5-103">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="429e5-104">Dieses Beispiel zeigt, wie ein Skript aufgerufen wird, das für ein Cmdlet bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="429e5-104">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="429e5-105">Das Skript wird vom Cmdlet ausgeführt, und die Ergebnisse werden an das Cmdlet als Sammlung von [System. Management. Automation. psobject](/dotnet/api/System.Management.Automation.PSObject) -Objekten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="429e5-105">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="429e5-106">So rufen Sie einen Skriptblock auf</span><span class="sxs-lookup"><span data-stu-id="429e5-106">To invoke a script block</span></span>

1. <span data-ttu-id="429e5-107">Mit dem Befehl wird überprüft, ob ein Skriptblock für das Cmdlet bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="429e5-107">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="429e5-108">Wenn ein Skriptblock angegeben wurde, ruft der Befehl den Skriptblock mit den erforderlichen Parametern auf.</span><span class="sxs-lookup"><span data-stu-id="429e5-108">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

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

2. <span data-ttu-id="429e5-109">Anschließend durchläuft das Skript die zurückgegebene Auflistung von [System. Management. Automation. psobject](/dotnet/api/System.Management.Automation.PSObject) -Objekten und führt die erforderlichen Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="429e5-109">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

    ```csharp
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

## <a name="see-also"></a><span data-ttu-id="429e5-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="429e5-110">See Also</span></span>

[<span data-ttu-id="429e5-111">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="429e5-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
