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
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="380e9-103">Attribute im Cmdlet-Code</span><span class="sxs-lookup"><span data-stu-id="380e9-103">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="380e9-104">Um die von Windows PowerShell bereitgestellte allgemeine Funktionalität zu verwenden, werden die im Cmdlet-Code definierten Klassen und öffentlichen Eigenschaften mit Attributen versehen.</span><span class="sxs-lookup"><span data-stu-id="380e9-104">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="380e9-105">Die folgende Klassendefinition verwendet beispielsweise das Cmdlet-Attribut, um die Microsoft .NET Framework-Klasse zu identifizieren, in der das Cmdlet " **Get-proc** " implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="380e9-105">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="380e9-106">(Dieses Cmdlet wird in diesem Dokument als Beispiel verwendet und ähnelt dem `Get-Process` Cmdlet, das von Windows PowerShell bereitgestellt wird.)</span><span class="sxs-lookup"><span data-stu-id="380e9-106">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="380e9-107">Diese Attribute werden als Metadaten betrachtet, da ihre Implementierung von der Implementierung des Cmdlet-Codes getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="380e9-107">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="380e9-108">Wenn das Cmdlet von der Windows PowerShell-Laufzeit ausgeführt wird, werden die Attribute erkannt und anschließend die entsprechende Aktion für jedes Attribut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="380e9-108">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="380e9-109">Obwohl Sie möglicherweise Ihre eigene Version der Funktionalität implementieren möchten, die von diesen Attributen bereitgestellt wird, verwendet ein gutes Cmdlet-Design diese gemeinsamen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="380e9-109">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="380e9-110">Weitere Informationen zu den verschiedenen Attributen, die in den Cmdlets deklariert werden können, finden Sie unter [Attributtypen](./attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="380e9-110">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="380e9-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="380e9-111">See Also</span></span>

[<span data-ttu-id="380e9-112">Attributtypen</span><span class="sxs-lookup"><span data-stu-id="380e9-112">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="380e9-113">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="380e9-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
