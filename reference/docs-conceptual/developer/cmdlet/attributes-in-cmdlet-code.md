---
title: Attribute im Cmdlet-Code | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 1f92e329d304754d5596cef0c95dc597aca3a538
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774914"
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
