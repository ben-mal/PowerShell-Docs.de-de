---
title: AccessDbProviderSample02-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: ca7674ba5cff601394af4df20f0dda8794c14d22
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784808"
---
# <a name="accessdbprovidersample02-code-sample"></a>AccessDbProviderSample02-Codebeispiel

Der folgende Code zeigt die Implementierung des Windows PowerShell-Anbieters, der unter [Erstellen eines Windows PowerShell-Laufwerks Anbieters](./creating-a-windows-powershell-drive-provider.md)beschrieben wird.
Diese Implementierung erstellt einen Pfad, stellt eine Verbindung mit einer Access-Datenbank her und entfernt dann das Laufwerk.

> [!NOTE]
> Sie können die c#-Quelldatei (AccessDBSampleProvider02.cs) für diesen Anbieter mithilfe der Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 herunterladen. Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar. Weitere Informationen zu anderen Windows PowerShell-Anbieter Implementierungen finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./designing-your-windows-powershell-provider.md).

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="11-154":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell-Programmiererhandbuch](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
