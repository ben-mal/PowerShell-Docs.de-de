---
title: AccessDbProviderSample04-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 05509c5b36475bcd3f91c9ab7413974994d668d6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787273"
---
# <a name="accessdbprovidersample04-code-sample"></a>AccessDbProviderSample04-Codebeispiel

Der folgende Code zeigt die Implementierung des Windows PowerShell-Anbieters, der unter [Erstellen eines Windows PowerShell-Container Anbieters](./creating-a-windows-powershell-container-provider.md)beschrieben wird.
Dieser Anbieter funktioniert in Daten speichern mit mehreren Ebenen. Bei dieser Art von Datenspeicher enthält die oberste Ebene des Stores die Stamm Elemente, und jede nachfolgende Ebene wird als Knoten untergeordneter Elemente bezeichnet. Da der Benutzer an diesen untergeordneten Knoten arbeiten kann, kann er hierarchisch über den Datenspeicher interagieren.

## <a name="code-sample"></a>Codebeispiel

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell SDK](../windows-powershell-reference.md)
