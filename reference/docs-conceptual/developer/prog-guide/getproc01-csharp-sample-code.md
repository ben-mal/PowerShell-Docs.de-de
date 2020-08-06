---
title: GetProc01 (c#)-Beispiel Code | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 883beb9dd1328a1897b9b61656a98cf515a21be7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778898"
---
# <a name="getproc01-c-sample-code"></a>GetProc01-Codebeispiel (C#)

Der folgende Code zeigt die Implementierung des GetProc01-Beispiel-Cmdlets. Beachten Sie, dass das Cmdlet vereinfacht wird, indem Sie die tatsächliche Prozess Abruf Funktion an die [System. Diagnostics. Process. GetProcesses *](/dotnet/api/System.Diagnostics.Process.GetProcesses) -Methode überlassen.

> [!NOTE]
> Sie können die c#-Quelldatei (getproc01.cs) für dieses Get-proc-Cmdlet mit dem Microsoft Windows Software Development Kit für Windows Vista und .NET Framework 3,0-Laufzeitkomponenten herunterladen. Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs" range="11-126":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell-Programmiererhandbuch](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
