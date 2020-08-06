---
title: GetProc03 (c#)-Beispiel Code | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 278c3f36bb975f9ea195978853e6539c0bd15084
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787120"
---
# <a name="getproc03-c-sample-code"></a>GetProc03-Codebeispiel (C#)

Der folgende Code zeigt die Implementierung eines `Get-Process` Cmdlets, das Pipeline Eingaben akzeptieren kann. Diese Implementierung definiert einen `Name` Parameter, der Pipeline Eingaben annimmt, Prozessinformationen vom lokalen Computer auf der Grundlage der angegebenen Namen abruft und dann die Methode " [Write Object" (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) als Ausgabe Mechanismus zum Senden von Objekten an die Pipeline verwendet.

> [!NOTE]
> Sie können die c#-Quelldatei (getprov03.cs) für dieses Get-proc-Cmdlet mit dem Microsoft Windows Software Development Kit für Windows Vista und .NET Framework 3,0-Laufzeitkomponenten herunterladen. Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell-Programmiererhandbuch](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
