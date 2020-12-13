---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace02-Codebeispiel (C#)
description: Runspace02-Codebeispiel (C#)
ms.openlocfilehash: 9e2c0cf37d1bf12a92f4fbf781928c0241202915
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647439"
---
# <a name="runspace02-c-code-sample"></a>Runspace02-Codebeispiel (C#)

Dies ist der c#-Quellcode für das Runspace02-Beispiel. In diesem Beispiel wird die [System. Management. Automation. runspacinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) -Klasse verwendet, um das `Get-Process` Cmdlet synchron auszuführen. Windows Forms und die Datenbindung werden dann verwendet, um die Ergebnisse in einem DataGridView-Steuerelement anzuzeigen.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell SDK](../windows-powershell-reference.md)
