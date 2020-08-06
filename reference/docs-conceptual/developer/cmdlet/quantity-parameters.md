---
title: Mengen Parameter | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 7ff6562380bb6336b08879b31d8d9fed47bfb6a7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781816"
---
# <a name="quantity-parameters"></a><span data-ttu-id="e389f-102">Mengenparameter</span><span class="sxs-lookup"><span data-stu-id="e389f-102">Quantity Parameters</span></span>

<span data-ttu-id="e389f-103">In der folgenden Tabelle werden die empfohlenen Namen und Funktionen für die Anzahl von Parametern aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e389f-103">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="e389f-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="e389f-104">Parameter</span></span>|<span data-ttu-id="e389f-105">Funktionalität</span><span class="sxs-lookup"><span data-stu-id="e389f-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="e389f-106">**Alle**</span><span class="sxs-lookup"><span data-stu-id="e389f-106">**All**</span></span><br><span data-ttu-id="e389f-107">Datentyp: Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="e389f-107">Data type: Boolean</span></span>|<span data-ttu-id="e389f-108">Implementieren Sie diesen Parameter, damit `true` angibt, dass alle Ressourcen anstelle einer Standard Teilmenge von Ressourcen bearbeitet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="e389f-108">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="e389f-109">Implementieren Sie diesen Parameter, sodass `false` eine Teilmenge der Ressourcen angibt.</span><span class="sxs-lookup"><span data-stu-id="e389f-109">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="e389f-110">**Speicherbelegung**</span><span class="sxs-lookup"><span data-stu-id="e389f-110">**Allocation**</span></span><br><span data-ttu-id="e389f-111">Datentyp: Int32</span><span class="sxs-lookup"><span data-stu-id="e389f-111">Data type: Int32</span></span>|<span data-ttu-id="e389f-112">Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl der zuzuordnenden Elemente angeben kann.</span><span class="sxs-lookup"><span data-stu-id="e389f-112">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="e389f-113">**Blockcount**</span><span class="sxs-lookup"><span data-stu-id="e389f-113">**BlockCount**</span></span><br><span data-ttu-id="e389f-114">Datentyp: Int64</span><span class="sxs-lookup"><span data-stu-id="e389f-114">Data type: Int64</span></span>|<span data-ttu-id="e389f-115">Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl der Blöcke angeben kann.</span><span class="sxs-lookup"><span data-stu-id="e389f-115">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="e389f-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="e389f-116">**Count**</span></span><br><span data-ttu-id="e389f-117">Datentyp: Int64</span><span class="sxs-lookup"><span data-stu-id="e389f-117">Data type: Int64</span></span>|<span data-ttu-id="e389f-118">Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl angeben kann.</span><span class="sxs-lookup"><span data-stu-id="e389f-118">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="e389f-119">**Umfang**</span><span class="sxs-lookup"><span data-stu-id="e389f-119">**Scope**</span></span><br><span data-ttu-id="e389f-120">Datentyp: Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="e389f-120">Data type: Keyword</span></span>|<span data-ttu-id="e389f-121">Implementieren Sie diesen Parameter, sodass der Benutzer den Bereich angeben kann, der verarbeitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e389f-121">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="e389f-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e389f-122">See Also</span></span>

[<span data-ttu-id="e389f-123">Cmdlet-Parameter</span><span class="sxs-lookup"><span data-stu-id="e389f-123">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="e389f-124">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e389f-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="e389f-125">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="e389f-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
