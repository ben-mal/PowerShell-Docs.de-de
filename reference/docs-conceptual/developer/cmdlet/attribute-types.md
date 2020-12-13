---
ms.date: 09/13/2016
ms.topic: reference
title: Attributtypen
description: Attributtypen
ms.openlocfilehash: 65640f2f8449887dedb9fae137eb16b6252f1d57
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667112"
---
# <a name="attribute-types"></a><span data-ttu-id="2eb3f-103">Attributtypen</span><span class="sxs-lookup"><span data-stu-id="2eb3f-103">Attribute Types</span></span>

<span data-ttu-id="2eb3f-104">Cmdlet-Attribute können nach Funktionalität gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-104">Cmdlet attributes can be grouped by functionality.</span></span>
<span data-ttu-id="2eb3f-105">In den folgenden Abschnitten werden die verfügbaren Attribute beschrieben, und es wird beschrieben, was die Laufzeit bewirkt, wenn das Attribut aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-105">The following sections describe the available attributes and describe what the runtime does when the attribute is invoked.</span></span>

## <a name="cmdlet-attributes"></a><span data-ttu-id="2eb3f-106">Cmdlet-Attribute</span><span class="sxs-lookup"><span data-stu-id="2eb3f-106">Cmdlet Attributes</span></span>

### <a name="cmdlet"></a><span data-ttu-id="2eb3f-107">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2eb3f-107">Cmdlet</span></span>

<span data-ttu-id="2eb3f-108">Identifiziert eine .NET Framework Klasse als Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-108">Identifies a .NET Framework class as a cmdlet.</span></span>
<span data-ttu-id="2eb3f-109">Dies ist das erforderliche Basis Attribut.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-109">This is the required base attribute.</span></span>
<span data-ttu-id="2eb3f-110">Weitere Informationen finden Sie unter [Cmdlet-Attribut Deklaration](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb3f-110">For more information, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="2eb3f-111">Parameterattribute</span><span class="sxs-lookup"><span data-stu-id="2eb3f-111">Parameter Attributes</span></span>

### <a name="parameter"></a><span data-ttu-id="2eb3f-112">Parameter</span><span class="sxs-lookup"><span data-stu-id="2eb3f-112">Parameter</span></span>

<span data-ttu-id="2eb3f-113">Identifiziert eine öffentliche Eigenschaft in der Cmdlet-Klasse als Cmdlet-Parameter.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-113">Identifies a public property in the cmdlet class as a cmdlet parameter.</span></span>
<span data-ttu-id="2eb3f-114">Weitere Informationen finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb3f-114">For more information, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

### <a name="alias"></a><span data-ttu-id="2eb3f-115">Alias</span><span class="sxs-lookup"><span data-stu-id="2eb3f-115">Alias</span></span>

<span data-ttu-id="2eb3f-116">Gibt mindestens einen Alias für einen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-116">Specifies one or more aliases for a parameter.</span></span>
<span data-ttu-id="2eb3f-117">Weitere Informationen finden Sie unter [Alias Attribut Deklaration](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb3f-117">For more information, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="argument-validation-attributes"></a><span data-ttu-id="2eb3f-118">Argument Validierungs Attribute</span><span class="sxs-lookup"><span data-stu-id="2eb3f-118">Argument Validation Attributes</span></span>

### <a name="validatecount"></a><span data-ttu-id="2eb3f-119">Validatecount</span><span class="sxs-lookup"><span data-stu-id="2eb3f-119">ValidateCount</span></span>

<span data-ttu-id="2eb3f-120">Gibt die minimale und maximale Anzahl von Argumenten an, die für einen Cmdlet-Parameter zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-120">Specifies the minimum and maximum number of arguments that are allowed for a cmdlet parameter.</span></span>
<span data-ttu-id="2eb3f-121">Weitere Informationen finden Sie unter [validatecount-Attribut Deklaration](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb3f-121">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="2eb3f-122">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="2eb3f-122">ValidateLength</span></span>

<span data-ttu-id="2eb3f-123">Gibt eine minimale und maximale Anzahl von Zeichen für ein Cmdlet-Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-123">Specifies a minimum and maximum number of characters for a cmdlet parameter argument.</span></span>
<span data-ttu-id="2eb3f-124">Weitere Informationen finden Sie unter [validateLength-Attribut Deklaration](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb3f-124">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="2eb3f-125">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="2eb3f-125">ValidatePattern</span></span>

<span data-ttu-id="2eb3f-126">Gibt ein Muster für einen regulären Ausdruck an, dem das Cmdlet-Parameter Argument entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-126">Specifies a regular expression pattern that the cmdlet parameter argument must match.</span></span>
<span data-ttu-id="2eb3f-127">Weitere Informationen finden Sie unter [validatepattern-Attribut Deklaration](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb3f-127">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="2eb3f-128">Validaterange</span><span class="sxs-lookup"><span data-stu-id="2eb3f-128">ValidateRange</span></span>

<span data-ttu-id="2eb3f-129">Gibt die minimalen und maximalen Werte für ein Cmdlet-Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-129">Specifies the minimum and maximum values for a cmdlet parameter argument.</span></span>
<span data-ttu-id="2eb3f-130">Weitere Informationen finden Sie unter [validaterange-Attribut Deklaration](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb3f-130">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="2eb3f-131">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="2eb3f-131">ValidateSet</span></span>

<span data-ttu-id="2eb3f-132">Gibt einen Satz gültiger Werte für das Cmdlet-Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="2eb3f-132">Specifies a set of valid values for the cmdlet parameter argument.</span></span>
<span data-ttu-id="2eb3f-133">Weitere Informationen finden Sie unter [validateset-Attribut Deklaration](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2eb3f-133">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2eb3f-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2eb3f-134">See Also</span></span>

[<span data-ttu-id="2eb3f-135">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="2eb3f-135">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
