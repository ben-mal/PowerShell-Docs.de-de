---
title: Cmdlet-Entwicklungs Richtlinien | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- development guidelines [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], development guidelines
ms.openlocfilehash: 5dd83b12a9052ff5f146c4c4e077a9358907cbd0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784485"
---
# <a name="cmdlet-development-guidelines"></a><span data-ttu-id="f163b-102">Cmdlet-Entwicklungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f163b-102">Cmdlet Development Guidelines</span></span>

<span data-ttu-id="f163b-103">Die Themen in diesem Abschnitt bieten Entwicklungs Richtlinien, die Sie zum Erstellen von wohlgeformten Cmdlets verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f163b-103">The topics in this section provide development guidelines that you can use to produce well-formed cmdlets.</span></span> <span data-ttu-id="f163b-104">Durch die Nutzung der allgemeinen Funktionalität der Windows PowerShell-Laufzeit und durch die Einhaltung dieser Richtlinien können Sie robuste Cmdlets mit minimalem Aufwand entwickeln und dem Benutzer eine konsistente Umgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f163b-104">By leveraging the common functionality provided by the Windows PowerShell runtime and by following these guidelines, you can develop robust cmdlets with minimal effort and provide the user with a consistent experience.</span></span> <span data-ttu-id="f163b-105">Außerdem verringern Sie den Testaufwand, da die allgemeine Funktionalität keine erneuten Tests erfordert.</span><span class="sxs-lookup"><span data-stu-id="f163b-105">Additionally, you will reduce the test burden because common functionality does not require retesting.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f163b-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f163b-106">In This Section</span></span>

- [<span data-ttu-id="f163b-107">Erforderliche Entwicklungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f163b-107">Required Development Guidelines</span></span>](./required-development-guidelines.md)

- [<span data-ttu-id="f163b-108">Ausdrücklich empfohlene Entwicklungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f163b-108">Strongly Encouraged Development Guidelines</span></span>](./strongly-encouraged-development-guidelines.md)

- [<span data-ttu-id="f163b-109">Empfohlene Entwicklungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f163b-109">Advisory Development Guidelines</span></span>](./advisory-development-guidelines.md)

## <a name="see-also"></a><span data-ttu-id="f163b-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f163b-110">See Also</span></span>

[<span data-ttu-id="f163b-111">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f163b-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="f163b-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f163b-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
