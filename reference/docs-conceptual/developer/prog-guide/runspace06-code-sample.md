---
title: RunSpace06-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c8767ac8dc3a3d9253c2a53a4754d9bd54304abb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784723"
---
# <a name="runspace06-code-sample"></a>RunSpace06-Codebeispiel

Im folgenden finden Sie den Quellcode für das Runspace06-Beispiel, das unter [Konfigurieren eines Runspace mithilfe eines Windows PowerShell-Snap-Ins](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83)beschrieben wird.
Diese Beispielanwendung erstellt einen Runspace auf Grundlage eines Windows PowerShell-Snap-Ins, das dann verwendet wird, um eine Pipeline mit einem einzigen Befehl auszuführen. Zu diesem Zweck erstellt die Anwendung die Runspace-Konfigurationsinformationen, erstellt einen Runspace, erstellt eine Pipeline mit einem einzigen Befehl und führt dann die Pipeline aus.

> [!NOTE]
> Sie können die c#-Quelldatei (runspace06.cs) mit dem Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0-Laufzeitkomponenten herunterladen. Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs" range="11-85":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell-Programmiererhandbuch](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
