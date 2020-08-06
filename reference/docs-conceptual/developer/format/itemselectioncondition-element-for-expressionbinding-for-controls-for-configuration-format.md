---
title: Itemselectioncondition-Element für ExpressionBinding für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 3bfd3efe916b4d88c024de8f959482cab515f777
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781221"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="1ecf7-102">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecf7-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="1ecf7-103">Definiert die Bedingung, die vorhanden sein muss, damit dieses Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="1ecf7-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="1ecf7-104">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1ecf7-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="1ecf7-105">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Configuration (Format) customentry-Element für CustomControl für Steuerelemente für Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration ExpressionBinding-Element für customItem for Controls for Configuration (Format) itemselectioncondition-Element für ExpressionBinding für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecf7-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1ecf7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ecf7-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1ecf7-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1ecf7-107">Attributes and Elements</span></span>

<span data-ttu-id="1ecf7-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ItemSelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ecf7-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1ecf7-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="1ecf7-109">Attributes</span></span>

<span data-ttu-id="1ecf7-110">Keine</span><span class="sxs-lookup"><span data-stu-id="1ecf7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1ecf7-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ecf7-111">Child Elements</span></span>

|<span data-ttu-id="1ecf7-112">Element</span><span class="sxs-lookup"><span data-stu-id="1ecf7-112">Element</span></span>|<span data-ttu-id="1ecf7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ecf7-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1ecf7-114">PropertyName-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecf7-114">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="1ecf7-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="1ecf7-115">Optional element.</span></span><br /><br /> <span data-ttu-id="1ecf7-116">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="1ecf7-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="1ecf7-117">ScriptBlock-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecf7-117">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="1ecf7-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="1ecf7-118">Optional element.</span></span><br /><br /> <span data-ttu-id="1ecf7-119">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="1ecf7-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1ecf7-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ecf7-120">Parent Elements</span></span>

|<span data-ttu-id="1ecf7-121">Element</span><span class="sxs-lookup"><span data-stu-id="1ecf7-121">Element</span></span>|<span data-ttu-id="1ecf7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ecf7-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1ecf7-123">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecf7-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="1ecf7-124">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1ecf7-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1ecf7-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1ecf7-125">Remarks</span></span>

<span data-ttu-id="1ecf7-126">Sie können einen Eigenschaftsnamen oder ein Skript für diese Bedingung angeben, aber nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="1ecf7-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ecf7-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ecf7-127">See Also</span></span>

[<span data-ttu-id="1ecf7-128">PropertyName-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecf7-128">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="1ecf7-129">ScriptBlock-Element für itemselectioncondition für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecf7-129">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="1ecf7-130">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="1ecf7-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="1ecf7-131">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="1ecf7-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
