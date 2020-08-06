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
# <a name="defining-default-member-sets-for-objects"></a>Definieren von Standardelementgruppen für Objekte

Der psstandardmembers-Member Satz wird von Windows PowerShell verwendet, um die Standardeigenschaften Sätze für ein Objekt zu definieren. Die Standardeigenschaften Sätze können von Befehlen wie z. b. den Formatierungs-Cmdlets verwendet werden, um nur die Eigenschaften anzuzeigen, die durch den Eigenschaften Satz definiert werden. Die Standard Eigenschafts Sätze umfassen defaultdisplayproperty, defaultdisplaypropertyset und defaultkeypropertyset. Windows PowerShell ignoriert alle anderen Element Sätze und alle anderen Eigenschaften Sätze, die dem psstandardmembers-Element Satz hinzugefügt werden.

## <a name="member-set-for-systemdiagnosticsprocess"></a>Member festgelegt für System. Diagnostics. Process

Im folgenden Beispiel definiert der psstandardmembers-Member Satz die defaultdisplaypropertyset-Eigenschaft, die für [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekte festgelegt ist. Dieser Eigenschaften Satz wird vom Cmdlet " [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) " verwendet.

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

Die folgende Ausgabe zeigt die Standardeigenschaften, die vom Cmdlet " [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) " zurückgegeben werden. Nur die `Id` `Handles` Eigenschaften,, `CPU` und `Name` werden für jedes Prozess Objekt zurückgegeben.

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

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
