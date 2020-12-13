---
ms.date: 09/13/2016
ms.topic: reference
title: Attribute im Cmdlet-Code
description: Attribute im Cmdlet-Code
ms.openlocfilehash: 296bb8bcb06ef660e97dc792d1ecf596cc7c2930
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653655"
---
# <a name="attributes-in-cmdlet-code"></a>Attribute im Cmdlet-Code

Um die von Windows PowerShell bereitgestellte allgemeine Funktionalität zu verwenden, werden die im Cmdlet-Code definierten Klassen und öffentlichen Eigenschaften mit Attributen versehen. Die folgende Klassendefinition verwendet beispielsweise das Cmdlet-Attribut, um die Microsoft .NET Framework-Klasse zu identifizieren, in der das Cmdlet " **Get-proc** " implementiert ist. (Dieses Cmdlet wird in diesem Dokument als Beispiel verwendet und ähnelt dem `Get-Process` Cmdlet, das von Windows PowerShell bereitgestellt wird.)

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

Diese Attribute werden als Metadaten betrachtet, da ihre Implementierung von der Implementierung des Cmdlet-Codes getrennt ist. Wenn das Cmdlet von der Windows PowerShell-Laufzeit ausgeführt wird, werden die Attribute erkannt und anschließend die entsprechende Aktion für jedes Attribut ausgeführt.

Obwohl Sie möglicherweise Ihre eigene Version der Funktionalität implementieren möchten, die von diesen Attributen bereitgestellt wird, verwendet ein gutes Cmdlet-Design diese gemeinsamen Funktionen.

Weitere Informationen zu den verschiedenen Attributen, die in den Cmdlets deklariert werden können, finden Sie unter [Attributtypen](./attribute-types.md).

## <a name="see-also"></a>Weitere Informationen

[Attributtypen](./attribute-types.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
