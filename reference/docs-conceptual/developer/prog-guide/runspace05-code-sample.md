---
title: RunSpace05-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 31a73f965a6e38dceec740a2f7d4adead3e2a3f9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784740"
---
# <a name="runspace05-code-sample"></a>RunSpace05-Codebeispiel

Im folgenden finden Sie den Quellcode für das Runspace05-Beispiel, das unter [Konfigurieren eines Runspace mithilfe von runspaceconfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2)beschrieben wird.
Dieses Beispiel zeigt, wie Sie die Runspace-Konfigurationsinformationen erstellen, einen Runspace erstellen, eine Pipeline mit einem einzelnen Befehl erstellen und dann die Pipeline ausführen. Der Befehl, der ausgeführt wird, ist das `Get-Process` Cmdlet.

> [!NOTE]
> Sie können die c#-Quelldatei (runspace05.cs) herunterladen, indem Sie die Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 verwenden. Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs" range="11-86":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell-Programmiererhandbuch](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
