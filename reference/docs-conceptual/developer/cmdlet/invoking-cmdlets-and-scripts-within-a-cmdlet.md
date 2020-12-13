---
ms.date: 09/13/2016
ms.topic: reference
title: Aufrufen von Cmdlets und Skripts in einem Cmdlet
description: Aufrufen von Cmdlets und Skripts in einem Cmdlet
ms.openlocfilehash: 246c61661f2d290e7e7ac62a8ad303b05bdc7582
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652641"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a>Aufrufen von Cmdlets und Skripts in einem Cmdlet

Ein Cmdlet kann andere Cmdlets und Skripts in der Eingabe Verarbeitungsmethode des Cmdlets aufrufen. Dies ermöglicht es Ihnen, die Funktionalität vorhandener Cmdlets und Skripts zum Cmdlet hinzuzufügen, ohne den Code neu schreiben zu müssen.

## <a name="the-invoke-method"></a>Die Invoke-Methode

Alle Cmdlets können ein vorhandenes Cmdlet aufrufen, indem Sie die [System. Management. Automation. Cmdlet.](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) Call-Methode aus einer Eingabe Verarbeitungsmethode aufrufen, wie z [. b. System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), die vom Cmdlet überschrieben wird. Sie können jedoch nur die Cmdlets aufrufen, die direkt von der [System. Management. Automation. Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) -Klasse abgeleitet werden. Sie können kein Cmdlet aufrufen, das von der [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) -Klasse abgeleitet wird.

Die [System. Management. Automation. Cmdlet. aufrufen *](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) -Methode verfügt über die folgenden Varianten.

[System. Management. Automation. Cmdlet. aufrufen](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) diese Variante Ruft das Cmdlet-Objekt auf und gibt eine Auflistung von T-Objekten zurück.

[System. Management. Automation. Cmdlet. aufrufen](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) diese Variante Ruft das Cmdlet-Objekt auf und gibt einen stark typisierten emumerator zurück. Diese Variante ermöglicht dem Benutzer die Verwendung der Objekte in der Auflistung, um benutzerdefinierte Vorgänge auszuführen.

## <a name="examples"></a>Beispiele

|Beispiel|BESCHREIBUNG|
|-------------|-----------------|
|[Aufrufen von Cmdlets in einem Cmdlet](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|Dieses Beispiel zeigt, wie Sie ein Cmdlet in einem anderen Cmdlet aufrufen.|
|[Aufrufen von Skripts in einem Cmdlet](./how-to-invoke-scripts-within-a-cmdlet.md)|In diesem Beispiel wird gezeigt, wie ein Skript aufgerufen wird, das für das Cmdlet aus einem anderen Cmdlet bereitgestellt wird.|

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
