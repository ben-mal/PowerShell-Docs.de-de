---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet-Attribute
description: Cmdlet-Attribute
ms.openlocfilehash: 6a106f33cb34c6c33b88a981815543bc9af4e4ba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653520"
---
# <a name="cmdlet-attributes"></a><span data-ttu-id="7848c-103">Cmdlet-Attribute</span><span class="sxs-lookup"><span data-stu-id="7848c-103">Cmdlet Attributes</span></span>

<span data-ttu-id="7848c-104">Windows PowerShell definiert mehrere Attribute, die Sie verwenden können, um Ihren Cmdlets allgemeine Funktionen hinzuzufügen, ohne diese Funktionalität in Ihrem eigenen Code implementieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7848c-104">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="7848c-105">Dies schließt das Cmdlet-Attribut ein, das eine Microsoft .NET Frameworkklasse als Cmdlet-Klasse identifiziert, das OutputType-Attribut, das die vom Cmdlet zurückgegebenen .NET Framework Typen angibt, das Parameter Attribut, das öffentliche Eigenschaften als Cmdlet-Parameter identifiziert, usw.</span><span class="sxs-lookup"><span data-stu-id="7848c-105">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7848c-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7848c-106">In This Section</span></span>

<span data-ttu-id="7848c-107">[Attribute im Cmdlet-Code](./attributes-in-cmdlet-code.md) Beschreibt den Vorteil der Verwendung von Attributen in Cmdlet-Code.</span><span class="sxs-lookup"><span data-stu-id="7848c-107">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="7848c-108">[Attributtypen](./attribute-types.md) Beschreibt die unterschiedlichen Attribute, die eine Cmdlet-Klasse ergänzen können.</span><span class="sxs-lookup"><span data-stu-id="7848c-108">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="7848c-109">[Alias Attribut Deklaration](./alias-attribute-declaration.md) Beschreibt, wie Aliase für einen Cmdlet-Parameternamen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7848c-109">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="7848c-110">[Cmdlet-Attribut Deklaration](./cmdlet-attribute-declaration.md) Beschreibt, wie eine .NET Framework Klasse als Cmdlet definiert wird.</span><span class="sxs-lookup"><span data-stu-id="7848c-110">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="7848c-111">[Deklaration der Credential-Attribute](./credential-attribute-declaration.md) Beschreibt das Hinzufügen von Unterstützung für das konvertiert von Zeichen folgen Eingaben in ein [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="7848c-111">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="7848c-112">[OutputType-Attribut Deklaration](./outputtype-attribute-declaration.md) Beschreibt, wie die vom Cmdlet zurückgegebenen .NET Framework Typen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7848c-112">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="7848c-113">[Parameter Attribut Deklaration](./parameter-attribute-declaration.md) Beschreibt, wie die Parameter eines Cmdlets definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7848c-113">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="7848c-114">[Validatecount-Attribut Deklaration](./validatecount-attribute-declaration.md) Beschreibt, wie Sie definieren, wie viele Argumente für einen Parameter zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="7848c-114">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="7848c-115">[ValidateLength-Attribut Deklaration](./validatelength-attribute-declaration.md) Beschreibt, wie die Länge (in Zeichen) eines Parameter Arguments definiert wird.</span><span class="sxs-lookup"><span data-stu-id="7848c-115">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="7848c-116">[Validatepattern-Attribut Deklaration](./validatepattern-attribute-declaration.md) Beschreibt, wie die gültigen Muster für ein Parameter Argument definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7848c-116">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="7848c-117">[Validaterange-Attribut Deklaration](./validaterange-attribute-declaration.md) Beschreibt, wie der gültige Bereich für ein Parameter Argument definiert wird.</span><span class="sxs-lookup"><span data-stu-id="7848c-117">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="7848c-118">[Validateset-Attribut Deklaration](./validateset-attribute-declaration.md) Beschreibt, wie die möglichen Werte für ein Parameter Argument definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7848c-118">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="7848c-119">Verweis</span><span class="sxs-lookup"><span data-stu-id="7848c-119">Reference</span></span>

[<span data-ttu-id="7848c-120">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="7848c-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
