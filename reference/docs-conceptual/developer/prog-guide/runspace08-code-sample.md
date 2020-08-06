---
title: RunSpace08-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 67172a0f8d6daf2f5b9965d1a18f7698daddbe1a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784689"
---
# <a name="runspace08-code-sample"></a>RunSpace08-Codebeispiel

Im folgenden finden Sie den Quellcode für das Runspace08-Beispiel [, das unter Erstellen einer Konsolenanwendung beschrieben wird, mit der einem Befehl Parameter hinzugefügt](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba)werden.
In dieser Beispielanwendung wird ein Runspace erstellt, eine Pipeline erstellt, zwei Befehle zur Pipeline hinzugefügt, dem zweiten Befehl werden zwei Parameter hinzugefügt, und anschließend wird die Pipeline ausgeführt. Die Befehle, die der Pipeline hinzugefügt werden, sind die `Get-Process` `Sort-Object` Cmdlets und.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell SDK](../windows-powershell-reference.md)
