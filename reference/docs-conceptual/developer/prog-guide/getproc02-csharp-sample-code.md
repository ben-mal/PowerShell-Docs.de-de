---
title: GetProc02 (c#)-Beispiel Code | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: d9afa8fff23d99661987c067e8082a9294c12717
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787154"
---
# <a name="getproc02-c-sample-code"></a>GetProc02-Codebeispiel (C#)

Der folgende Code zeigt die Implementierung eines `Get-Process` Cmdlets, das Befehlszeilen Eingaben akzeptiert. Beachten Sie, dass diese Implementierung einen `Name` Parameter definiert, um Befehlszeilen Eingaben zuzulassen, und die Methode " [Write Object" (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) als Ausgabe Mechanismus zum Senden von Ausgabe Objekten an die Pipeline verwendet wird.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell SDK](../windows-powershell-reference.md)
