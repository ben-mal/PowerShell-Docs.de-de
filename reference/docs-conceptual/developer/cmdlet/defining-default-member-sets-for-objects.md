---
ms.date: 09/13/2016
ms.topic: reference
title: Definieren von Standardelementgruppen für Objekte
description: Definieren von Standardelementgruppen für Objekte
ms.openlocfilehash: 919f7ba65322c6a56a27e046fb211bde151abf7d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653120"
---
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="8053c-103">Definieren von Standardelementgruppen für Objekte</span><span class="sxs-lookup"><span data-stu-id="8053c-103">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="8053c-104">Der psstandardmembers-Member Satz wird von Windows PowerShell verwendet, um die Standardeigenschaften Sätze für ein Objekt zu definieren.</span><span class="sxs-lookup"><span data-stu-id="8053c-104">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="8053c-105">Die Standardeigenschaften Sätze können von Befehlen wie z. b. den Formatierungs-Cmdlets verwendet werden, um nur die Eigenschaften anzuzeigen, die durch den Eigenschaften Satz definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8053c-105">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="8053c-106">Die Standard Eigenschafts Sätze umfassen defaultdisplayproperty, defaultdisplaypropertyset und defaultkeypropertyset.</span><span class="sxs-lookup"><span data-stu-id="8053c-106">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="8053c-107">Windows PowerShell ignoriert alle anderen Element Sätze und alle anderen Eigenschaften Sätze, die dem psstandardmembers-Element Satz hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8053c-107">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="8053c-108">Member festgelegt für System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="8053c-108">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="8053c-109">Im folgenden Beispiel definiert der psstandardmembers-Member Satz die defaultdisplaypropertyset-Eigenschaft, die für [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekte festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8053c-109">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="8053c-110">Dieser Eigenschaften Satz wird vom Cmdlet " [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) " verwendet.</span><span class="sxs-lookup"><span data-stu-id="8053c-110">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

```xml
<Type>
  <Name>System.Diagnostics.Process</Name>
  <Members>
    <MemberSet>
     <Name>PSStandardMembers</Name>
     <Members>
       <PropertySet>
         <Name>DefaultDisplayPropertySet</Name>
         <ReferencedProperties>
           <Name>Id</Name>
           <Name>Handles</Name>
           <Name>CPU</Name>
           <Name>Name</Name>
         </ReferencedProperties>
      </PropertySet>
    </Members>
  </MemberSet>
```

<span data-ttu-id="8053c-111">Die folgende Ausgabe zeigt die Standardeigenschaften, die vom Cmdlet " [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) " zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8053c-111">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="8053c-112">Nur die `Id` `Handles` Eigenschaften,, `CPU` und `Name` werden für jedes Prozess Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8053c-112">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

```powershell
Get-Process | format-list
```

```output
Id      : 2036
Handles : 27
CPU     :
Name    : AEADISRV

Id      : 272
Handles : 38
CPU     :
Name    : agrsmsvc
...
```

## <a name="see-also"></a><span data-ttu-id="8053c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8053c-113">See Also</span></span>

[<span data-ttu-id="8053c-114">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8053c-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
