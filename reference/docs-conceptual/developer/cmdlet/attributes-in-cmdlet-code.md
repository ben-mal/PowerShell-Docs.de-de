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
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="0acd5-102">Attribute im Cmdlet-Code</span><span class="sxs-lookup"><span data-stu-id="0acd5-102">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="0acd5-103">Um die von Windows PowerShell bereitgestellte allgemeine Funktionalität zu verwenden, werden die im Cmdlet-Code definierten Klassen und öffentlichen Eigenschaften mit Attributen versehen.</span><span class="sxs-lookup"><span data-stu-id="0acd5-103">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="0acd5-104">Die folgende Klassendefinition verwendet beispielsweise das Cmdlet-Attribut, um die Microsoft .NET Framework-Klasse zu identifizieren, in der das Cmdlet " **Get-proc** " implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="0acd5-104">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="0acd5-105">(Dieses Cmdlet wird in diesem Dokument als Beispiel verwendet und ähnelt dem `Get-Process` Cmdlet, das von Windows PowerShell bereitgestellt wird.)</span><span class="sxs-lookup"><span data-stu-id="0acd5-105">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="0acd5-106">Diese Attribute werden als Metadaten betrachtet, da ihre Implementierung von der Implementierung des Cmdlet-Codes getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="0acd5-106">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="0acd5-107">Wenn das Cmdlet von der Windows PowerShell-Laufzeit ausgeführt wird, werden die Attribute erkannt und anschließend die entsprechende Aktion für jedes Attribut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0acd5-107">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="0acd5-108">Obwohl Sie möglicherweise Ihre eigene Version der Funktionalität implementieren möchten, die von diesen Attributen bereitgestellt wird, verwendet ein gutes Cmdlet-Design diese gemeinsamen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="0acd5-108">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="0acd5-109">Weitere Informationen zu den verschiedenen Attributen, die in den Cmdlets deklariert werden können, finden Sie unter [Attributtypen](./attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="0acd5-109">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0acd5-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0acd5-110">See Also</span></span>

[<span data-ttu-id="0acd5-111">Attributtypen</span><span class="sxs-lookup"><span data-stu-id="0acd5-111">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="0acd5-112">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0acd5-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
