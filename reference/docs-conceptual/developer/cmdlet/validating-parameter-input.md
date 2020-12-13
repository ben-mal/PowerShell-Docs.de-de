---
ms.date: 09/13/2016
ms.topic: reference
title: Überprüfen von Parametereingaben
description: Überprüfen von Parametereingaben
ms.openlocfilehash: a97b5c670e8c36463a85bbef1506f6311bdd5ec3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660400"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="5dfcf-103">Überprüfen von Parametereingaben</span><span class="sxs-lookup"><span data-stu-id="5dfcf-103">Validating Parameter Input</span></span>

<span data-ttu-id="5dfcf-104">PowerShell kann die Argumente, die an Cmdlet-Parameter übergeben werden, auf verschiedene Weise überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-104">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="5dfcf-105">PowerShell kann die Länge, den Bereich und das Muster der Zeichen des Arguments überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-105">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="5dfcf-106">Sie kann die Anzahl der verfügbaren Argumente (die Anzahl) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-106">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="5dfcf-107">Diese Validierungsregeln werden durch Validierungs Attribute definiert, die mit dem Parameter-Attribut in öffentlichen Eigenschaften der Cmdlet-Klasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-107">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="5dfcf-108">Zum Validieren eines Parameter Arguments verwendet die PowerShell-Laufzeit die Informationen, die von den Validierungs Attributen bereitgestellt werden, um den Wert des-Parameters vor dem Ausführen des Cmdlets zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-108">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="5dfcf-109">Wenn die Parameter Eingabe nicht gültig ist, erhält der Benutzer eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-109">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="5dfcf-110">Jeder Validierungs Parameter definiert eine Validierungs Regel, die von PowerShell erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-110">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="5dfcf-111">PowerShell erzwingt die Validierungsregeln basierend auf den folgenden Attributen.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-111">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="5dfcf-112">Validatecount</span><span class="sxs-lookup"><span data-stu-id="5dfcf-112">ValidateCount</span></span>

<span data-ttu-id="5dfcf-113">Gibt die minimale und maximale Anzahl von Argumenten an, die ein Parameter annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-113">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="5dfcf-114">Weitere Informationen finden Sie unter [validatecount-Attribut Deklaration](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5dfcf-114">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="5dfcf-115">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="5dfcf-115">ValidateLength</span></span>

<span data-ttu-id="5dfcf-116">Gibt die minimale und maximale Anzahl von Zeichen im Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-116">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="5dfcf-117">Weitere Informationen finden Sie unter [validateLength-Attribut Deklaration](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5dfcf-117">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="5dfcf-118">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="5dfcf-118">ValidatePattern</span></span>

<span data-ttu-id="5dfcf-119">Gibt einen regulären Ausdruck an, der das Parameter Argument überprüft.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-119">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="5dfcf-120">Weitere Informationen finden Sie unter [validatepattern-Attribut Deklaration](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5dfcf-120">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="5dfcf-121">Validaterange</span><span class="sxs-lookup"><span data-stu-id="5dfcf-121">ValidateRange</span></span>

<span data-ttu-id="5dfcf-122">Gibt den minimalen und maximalen Wert des Parameter Arguments an.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-122">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="5dfcf-123">Weitere Informationen finden Sie unter [validaterange-Attribut Deklaration](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5dfcf-123">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="5dfcf-124">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="5dfcf-124">ValidateSet</span></span>

<span data-ttu-id="5dfcf-125">Gibt die gültigen Werte für das Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="5dfcf-125">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="5dfcf-126">Weitere Informationen finden Sie unter [validateset-Attribut Deklaration](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5dfcf-126">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5dfcf-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5dfcf-127">See Also</span></span>

[<span data-ttu-id="5dfcf-128">Überprüfen einer Parametereingabe</span><span class="sxs-lookup"><span data-stu-id="5dfcf-128">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="5dfcf-129">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5dfcf-129">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
