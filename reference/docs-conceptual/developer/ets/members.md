---
ms.date: 07/09/2020
ms.topic: reference
title: Erweiterte Typsystem-Klassenmember
description: Erweiterte Typsystem-Klassenmember
ms.openlocfilehash: 06488ce423f363a285ab53b21ab45989654346dc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666840"
---
# <a name="extended-type-system-class-members"></a><span data-ttu-id="37ff3-103">Erweiterte Typsystem-Klassenmember</span><span class="sxs-lookup"><span data-stu-id="37ff3-103">Extended Type System class members</span></span>

<span data-ttu-id="37ff3-104">ETS verweist auf eine Reihe verschiedener Arten von Membern, deren Typen durch die **psmembership Types** -Enumeration definiert werden.</span><span class="sxs-lookup"><span data-stu-id="37ff3-104">ETS refers to a number of different kinds of members whose types are defined by the **PSMemberTypes** enumeration.</span></span> <span data-ttu-id="37ff3-105">Diese Elementtypen umfassen Eigenschaften, Methoden, Member und Element Sätze, die jeweils durch ihren eigenen CLR-Typ definiert sind.</span><span class="sxs-lookup"><span data-stu-id="37ff3-105">These member types include properties, methods, members, and member sets that are each defined by their own CLR type.</span></span> <span data-ttu-id="37ff3-106">Beispielsweise wird eine **NoteProperty** durch ihren eigenen **psnoteproperty** -Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="37ff3-106">For example, a **NoteProperty** is defined by its own **PSNoteProperty** type.</span></span> <span data-ttu-id="37ff3-107">Diese einzelnen CLR-Typen verfügen sowohl über eigene eindeutige Eigenschaften als auch über gemeinsame Eigenschaften, die von der [psmembership Info-Klasse](/dotnet/api/system.management.automation.psmemberinfo)geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="37ff3-107">These individual CLR types have both their own unique properties and common properties that are inherited from the [PSMemberInfo class](/dotnet/api/system.management.automation.psmemberinfo).</span></span>

## <a name="the-psmemberinfo-class"></a><span data-ttu-id="37ff3-108">Die psmembership Info-Klasse</span><span class="sxs-lookup"><span data-stu-id="37ff3-108">The PSMemberInfo class</span></span>

<span data-ttu-id="37ff3-109">Die **psmembership Info** -Klasse dient als Basisklasse für alle ETS-Elementtypen.</span><span class="sxs-lookup"><span data-stu-id="37ff3-109">The **PSMemberInfo** class serves as a base class for all ETS member types.</span></span> <span data-ttu-id="37ff3-110">Diese Klasse stellt die folgenden Basis Eigenschaften für alle Member CLR-Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="37ff3-110">This class provides the following base properties to all member CLR types.</span></span>

- <span data-ttu-id="37ff3-111">**Name** -Eigenschaft: der Name des Members.</span><span class="sxs-lookup"><span data-stu-id="37ff3-111">**Name** property: The name of the member.</span></span> <span data-ttu-id="37ff3-112">Dieser Name kann vom Basisobjekt definiert oder von PowerShell definiert werden, wenn angepasste Member oder Erweiterte Member verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="37ff3-112">This name can be defined by the base-object or defined by PowerShell when adapted members or extended members are exposed.</span></span>
- <span data-ttu-id="37ff3-113">**Value** -Eigenschaft: der Wert, der vom jeweiligen Member zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="37ff3-113">**Value** property: The value returned from the particular member.</span></span> <span data-ttu-id="37ff3-114">Jeder Elementtyp definiert, wie er seinen Elementwert behandelt.</span><span class="sxs-lookup"><span data-stu-id="37ff3-114">Each member type defines how it handles its member value.</span></span>
- <span data-ttu-id="37ff3-115">**Typameofvalue** -Eigenschaft: Dies ist der Name des CLR-Typs des Werts, der von der Value-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="37ff3-115">**TypeNameOfValue** property: This is the name of the CLR type of the value that is returned by the Value property.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="37ff3-116">Zugreifen auf Member</span><span class="sxs-lookup"><span data-stu-id="37ff3-116">Accessing members</span></span>

<span data-ttu-id="37ff3-117">Auf Auflistungen von Membern kann **über die Eigenschaften**, **Methoden** und **Eigenschaften** des **psobject** -Objekts zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="37ff3-117">Collections of members can be accessed through the **Members**, **Methods**, and **Properties** properties of the **PSObject** object.</span></span>

## <a name="ets-properties"></a><span data-ttu-id="37ff3-118">ETS-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="37ff3-118">ETS properties</span></span>

<span data-ttu-id="37ff3-119">ETS-Eigenschaften sind Elemente, die als Eigenschaft behandelt werden können.</span><span class="sxs-lookup"><span data-stu-id="37ff3-119">ETS properties are members that can be treated as a property.</span></span> <span data-ttu-id="37ff3-120">Im Wesentlichen können Sie auf der linken Seite eines Ausdrucks angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="37ff3-120">Essentially, they can appear on the left-hand side of an expression.</span></span> <span data-ttu-id="37ff3-121">Dazu zählen Alias Eigenschaften, Code Eigenschaften, PowerShell-Eigenschaften, Notiz Eigenschaften und Skript Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="37ff3-121">They include alias properties, code properties, PowerShell properties, note properties, and script properties.</span></span> <span data-ttu-id="37ff3-122">Weitere Informationen zu diesen Eigenschaften Typen finden Sie unter [ETS-Eigenschaften](properties.md).</span><span class="sxs-lookup"><span data-stu-id="37ff3-122">For more information about these types of properties, see [ETS properties](properties.md).</span></span>

## <a name="ets-methods"></a><span data-ttu-id="37ff3-123">ETS-Methoden</span><span class="sxs-lookup"><span data-stu-id="37ff3-123">ETS methods</span></span>

<span data-ttu-id="37ff3-124">ETS-Methoden sind Member, die Argumente annehmen, möglicherweise Ergebnisse zurückgeben und nicht auf der linken Seite eines Ausdrucks angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="37ff3-124">ETS methods are members that can take arguments, may return results, and cannot appear on the left-hand side of an expression.</span></span> <span data-ttu-id="37ff3-125">Dazu zählen Code Methoden, PowerShell-Methoden und Skript Methoden.</span><span class="sxs-lookup"><span data-stu-id="37ff3-125">They include code methods, PowerShell methods, and script methods.</span></span>
<span data-ttu-id="37ff3-126">Weitere Informationen zu diesen Methoden Typen finden Sie unter [ETS-Methoden](methods.md).</span><span class="sxs-lookup"><span data-stu-id="37ff3-126">For more information about these types of methods, see [ETS methods](methods.md).</span></span>
