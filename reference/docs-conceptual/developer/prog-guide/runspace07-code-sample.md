---
title: RunSpace07-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 615bb237d26bf3a314ea7fb21e983ba2b000d105
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784706"
---
# <a name="runspace07-code-sample"></a>RunSpace07-Codebeispiel

Im folgenden finden Sie den Quellcode für das Runspace07-Beispiel [, das unter Erstellen einer Konsolenanwendung beschrieben wird, mit der einer Pipeline Befehle hinzugefügt](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e)werden.
Diese Beispielanwendung erstellt einen Runspace, erstellt eine Pipeline, fügt der Pipeline zwei Befehle hinzu und führt dann die Pipeline aus. Die Befehle, die der Pipeline hinzugefügt werden, sind die `Get-Process` `Measure-Object` Cmdlets und.

> [!NOTE]
> Sie können die c#-Quelldatei (runspace07.cs) unter Verwendung der Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 herunterladen. Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs" range="11-108":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell-Programmiererhandbuch](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
