---
title: Cmdlet-Attribute | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- attributes [PowerShell SDK]
- attributes [PowerShell SDK], described
ms.openlocfilehash: f22c2882fbe5b2f51ca5ea218b921192b0a7d41f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784519"
---
# <a name="cmdlet-attributes"></a><span data-ttu-id="62f37-102">Cmdlet-Attribute</span><span class="sxs-lookup"><span data-stu-id="62f37-102">Cmdlet Attributes</span></span>

<span data-ttu-id="62f37-103">Windows PowerShell definiert mehrere Attribute, die Sie verwenden können, um Ihren Cmdlets allgemeine Funktionen hinzuzufügen, ohne diese Funktionalität in Ihrem eigenen Code implementieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="62f37-103">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="62f37-104">Dies schließt das Cmdlet-Attribut ein, das eine Microsoft .NET Frameworkklasse als Cmdlet-Klasse identifiziert, das OutputType-Attribut, das die vom Cmdlet zurückgegebenen .NET Framework Typen angibt, das Parameter Attribut, das öffentliche Eigenschaften als Cmdlet-Parameter identifiziert, usw.</span><span class="sxs-lookup"><span data-stu-id="62f37-104">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="62f37-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="62f37-105">In This Section</span></span>

<span data-ttu-id="62f37-106">[Attribute im Cmdlet-Code](./attributes-in-cmdlet-code.md) Beschreibt den Vorteil der Verwendung von Attributen in Cmdlet-Code.</span><span class="sxs-lookup"><span data-stu-id="62f37-106">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="62f37-107">[Attributtypen](./attribute-types.md) Beschreibt die unterschiedlichen Attribute, die eine Cmdlet-Klasse ergänzen können.</span><span class="sxs-lookup"><span data-stu-id="62f37-107">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="62f37-108">[Alias Attribut Deklaration](./alias-attribute-declaration.md) Beschreibt, wie Aliase für einen Cmdlet-Parameternamen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="62f37-108">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="62f37-109">[Cmdlet-Attribut Deklaration](./cmdlet-attribute-declaration.md) Beschreibt, wie eine .NET Framework Klasse als Cmdlet definiert wird.</span><span class="sxs-lookup"><span data-stu-id="62f37-109">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="62f37-110">[Deklaration der Credential-Attribute](./credential-attribute-declaration.md) Beschreibt das Hinzufügen von Unterstützung für das konvertiert von Zeichen folgen Eingaben in ein [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="62f37-110">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="62f37-111">[OutputType-Attribut Deklaration](./outputtype-attribute-declaration.md) Beschreibt, wie die vom Cmdlet zurückgegebenen .NET Framework Typen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="62f37-111">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="62f37-112">[Parameter Attribut Deklaration](./parameter-attribute-declaration.md) Beschreibt, wie die Parameter eines Cmdlets definiert werden.</span><span class="sxs-lookup"><span data-stu-id="62f37-112">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="62f37-113">[Validatecount-Attribut Deklaration](./validatecount-attribute-declaration.md) Beschreibt, wie Sie definieren, wie viele Argumente für einen Parameter zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="62f37-113">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="62f37-114">[ValidateLength-Attribut Deklaration](./validatelength-attribute-declaration.md) Beschreibt, wie die Länge (in Zeichen) eines Parameter Arguments definiert wird.</span><span class="sxs-lookup"><span data-stu-id="62f37-114">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="62f37-115">[Validatepattern-Attribut Deklaration](./validatepattern-attribute-declaration.md) Beschreibt, wie die gültigen Muster für ein Parameter Argument definiert werden.</span><span class="sxs-lookup"><span data-stu-id="62f37-115">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="62f37-116">[Validaterange-Attribut Deklaration](./validaterange-attribute-declaration.md) Beschreibt, wie der gültige Bereich für ein Parameter Argument definiert wird.</span><span class="sxs-lookup"><span data-stu-id="62f37-116">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="62f37-117">[Validateset-Attribut Deklaration](./validateset-attribute-declaration.md) Beschreibt, wie die möglichen Werte für ein Parameter Argument definiert werden.</span><span class="sxs-lookup"><span data-stu-id="62f37-117">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="62f37-118">Verweis</span><span class="sxs-lookup"><span data-stu-id="62f37-118">Reference</span></span>

[<span data-ttu-id="62f37-119">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="62f37-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
