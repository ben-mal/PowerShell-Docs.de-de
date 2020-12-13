---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace01-Codebeispiel (C#)
description: Runspace01-Codebeispiel (C#)
ms.openlocfilehash: e6121c144e1a4c1a1d9460d01119f44ee5835821
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657144"
---
# <a name="runspace01-c-code-sample"></a>Runspace01-Codebeispiel (C#)

Im folgenden finden Sie die Codebeispiele für den Runspace [, der unter Erstellen einer Konsolenanwendung beschrieben wird, die einen angegebenen Befehl ausführt](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).
Hierzu ruft die Anwendung einen Runspace auf und ruft dann einen Befehl auf. (Beachten Sie, dass diese Anwendung keine Informationen zur Runspace-Konfiguration angibt und keine Pipeline explizit erstellt). Der Befehl, der aufgerufen wird, ist das `Get-Process` Cmdlet.

> [!NOTE]
> Sie können die c#-Quelldatei (runspace01.cs) für diesen Runspace mithilfe der Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 herunterladen.
> Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell-Programmiererhandbuch](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
