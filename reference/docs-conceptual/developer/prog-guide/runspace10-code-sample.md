---
title: RunSpace10-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 976df6c36a5f95d17a76dcd31d287a3f064eff24
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784655"
---
# <a name="runspace10-code-sample"></a>RunSpace10-Codebeispiel

Im folgenden finden Sie den Quellcode für das Runspace10-Beispiel. Diese Beispielanwendung fügt [System. Management. Automation. Runspaces. runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) ein Cmdlet hinzu und verwendet dann die geänderten Konfigurationsinformationen, um den Runspace zu erstellen.

> [!NOTE]
> Sie können die c#-Quelldatei (runspace10.cs) mit dem Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0-Laufzeitkomponenten herunterladen. Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace10/Runspace10.cs" range="11-118":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell-Programmiererhandbuch](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
