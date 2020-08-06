---
title: RunSpace09-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: fc5d8d4d182cca6bfc42d63c68a14a7a5e5f9c97
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784672"
---
# <a name="runspace09-code-sample"></a>RunSpace09-Codebeispiel

Im folgenden finden Sie den Quellcode für das Runspace09-Beispiel [, das unter Erstellen einer Konsolenanwendung beschrieben wird, die eine Pipeline asynchron](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47)aufruft.
Diese Beispielanwendung erstellt und öffnet einen Runspace, erstellt eine Pipeline und ruft Sie asynchron auf und verwendet dann Pipeline Ereignisse, um das Skript asynchron zu verarbeiten. Das Skript, das von dieser Anwendung ausgeführt wird, erstellt die ganzen Zahlen 1 bis 10 in Intervallen von 0,5 Sekunden (500 ms).

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell SDK](../windows-powershell-reference.md)
