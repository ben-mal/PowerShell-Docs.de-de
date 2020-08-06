---
title: Definieren von Standardmember-Sätzen für Objekte | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 80e1f54890d3aac1702414699ead16fcf38271e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774625"
---
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="c42c2-102">Definieren von Standardelementgruppen für Objekte</span><span class="sxs-lookup"><span data-stu-id="c42c2-102">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="c42c2-103">Der psstandardmembers-Member Satz wird von Windows PowerShell verwendet, um die Standardeigenschaften Sätze für ein Objekt zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c42c2-103">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="c42c2-104">Die Standardeigenschaften Sätze können von Befehlen wie z. b. den Formatierungs-Cmdlets verwendet werden, um nur die Eigenschaften anzuzeigen, die durch den Eigenschaften Satz definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c42c2-104">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="c42c2-105">Die Standard Eigenschafts Sätze umfassen defaultdisplayproperty, defaultdisplaypropertyset und defaultkeypropertyset.</span><span class="sxs-lookup"><span data-stu-id="c42c2-105">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="c42c2-106">Windows PowerShell ignoriert alle anderen Element Sätze und alle anderen Eigenschaften Sätze, die dem psstandardmembers-Element Satz hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c42c2-106">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="c42c2-107">Member festgelegt für System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="c42c2-107">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="c42c2-108">Im folgenden Beispiel definiert der psstandardmembers-Member Satz die defaultdisplaypropertyset-Eigenschaft, die für [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekte festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c42c2-108">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="c42c2-109">Dieser Eigenschaften Satz wird vom Cmdlet " [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) " verwendet.</span><span class="sxs-lookup"><span data-stu-id="c42c2-109">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

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

<span data-ttu-id="c42c2-110">Die folgende Ausgabe zeigt die Standardeigenschaften, die vom Cmdlet " [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) " zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c42c2-110">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="c42c2-111">Nur die `Id` `Handles` Eigenschaften,, `CPU` und `Name` werden für jedes Prozess Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c42c2-111">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c42c2-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c42c2-112">See Also</span></span>

[<span data-ttu-id="c42c2-113">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c42c2-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
