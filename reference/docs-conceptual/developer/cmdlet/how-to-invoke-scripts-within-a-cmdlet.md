---
ms.date: 09/13/2016
ms.topic: reference
title: Aufrufen von Skripts in einem Cmdlet
description: Aufrufen von Skripts in einem Cmdlet
ms.openlocfilehash: f4a43a1e1240854e57deac5721e1e070c1a45a51
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667027"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>Aufrufen von Skripts in einem Cmdlet

Dieses Beispiel zeigt, wie ein Skript aufgerufen wird, das für ein Cmdlet bereitgestellt wird. Das Skript wird vom Cmdlet ausgeführt, und die Ergebnisse werden an das Cmdlet als Sammlung von [System. Management. Automation. psobject](/dotnet/api/System.Management.Automation.PSObject) -Objekten zurückgegeben.

## <a name="to-invoke-a-script-block"></a>So rufen Sie einen Skriptblock auf

1. Mit dem Befehl wird überprüft, ob ein Skriptblock für das Cmdlet bereitgestellt wurde. Wenn ein Skriptblock angegeben wurde, ruft der Befehl den Skriptblock mit den erforderlichen Parametern auf.

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

2. Anschließend durchläuft das Skript die zurückgegebene Auflistung von [System. Management. Automation. psobject](/dotnet/api/System.Management.Automation.PSObject) -Objekten und führt die erforderlichen Vorgänge aus.

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

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
