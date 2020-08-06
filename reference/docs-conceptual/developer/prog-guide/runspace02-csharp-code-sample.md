---
title: Runspace02 (c#)-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 1e58f035f20baa7443d9031499062a45beae01b9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778453"
---
# <a name="runspace02-c-code-sample"></a>Runspace02-Codebeispiel (C#)

Dies ist der c#-Quellcode für das Runspace02-Beispiel. In diesem Beispiel wird die [System. Management. Automation. runspacinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) -Klasse verwendet, um das `Get-Process` Cmdlet synchron auszuführen. Windows Forms und die Datenbindung werden dann verwendet, um die Ergebnisse in einem DataGridView-Steuerelement anzuzeigen.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell SDK](../windows-powershell-reference.md)
