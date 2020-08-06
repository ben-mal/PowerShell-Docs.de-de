---
title: Runspace01 (c#)-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 418162731b4a98989642e1c61c655fdb0f002698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787054"
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
