---
description: Beschreibt das Hidden-Schlüsselwort, das Klassenmember aus Standard Get-Member Ergebnissen verbirgt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hidden?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hidden
ms.openlocfilehash: b43f5d137f139cd7578f03b0429815e595b2fc58
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222268"
---
# <a name="about_hidden"></a>about_Hidden

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt das Hidden-Schlüsselwort, das Klassenmember aus Standard Get-Member Ergebnissen verbirgt.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Wenn Sie das Hidden-Schlüsselwort in einem Skript verwenden, blenden Sie die Member einer Klasse standardmäßig aus. Mit dem Schlüsselwort Hidden können Eigenschaften, Methoden (einschließlich Konstruktoren, Ereignisse, Alias Eigenschaften und andere Elementtypen, einschließlich statischer Member, aus den Standard Ergebnissen des Get-Member Cmdlets) und aus den Ergebnissen von IntelliSense und der Vervollständigung von Registerkarten ausgeblendet werden. Fügen Sie zum Anzeigen von Membern, die Sie mit dem Hidden-Schlüsselwort ausgeblendet haben, den-Force-Parameter einem Get-Member-Befehl hinzu.

Ausgeblendete Member werden nicht mit der Vervollständigung mit der Tab-Taste oder mit IntelliSense angezeigt, es sei denn, der Abschluss tritt in der Klasse auf, die

Das neue Attribut System. Management. Automation. hiddenattribute wurde hinzugefügt, sodass C- \# Code in PowerShell die gleiche Semantik aufweisen kann.

Das Hidden-Schlüsselwort ist nützlich zum Erstellen von Eigenschaften und Methoden in einer Klasse, die von anderen Benutzern der Klasse nicht unbedingt angezeigt werden sollen, oder die Sie problemlos bearbeiten können.

Das Hidden-Schlüsselwort hat keine Auswirkung darauf, wie Sie Member einer Klasse anzeigen oder ändern können. Wie bei allen Sprach Schlüsselwörtern in PowerShell wird bei Hidden nicht zwischen Groß-und Kleinschreibung unterschieden

Hidden wurde zusammen mit benutzerdefinierten Klassen in PowerShell 5,0 eingeführt.

## <a name="example"></a>BEISPIEL

Im folgenden Beispiel wird gezeigt, wie das Hidden-Schlüsselwort in einer Klassendefinition verwendet wird. Die Auto-Klassenmethode, Laufwerk, verfügt über eine Eigenschaft, "Rides", die nicht angezeigt oder geändert werden muss (es gibt lediglich an, wie oft das Laufwerk auf der Auto-Klasse aufgerufen wird, eine Metrik, die für Benutzer der Klasse nicht wichtig ist. Wenn Sie z. b. ein Auto kaufen, Fragen Sie den Verkäufer nicht, wie viele Laufwerke das Auto beansprucht hat.

Da es für Benutzer der-Klasse wenig erforderlich ist, diese Eigenschaft zu ändern, können Sie die-Eigenschaft aus Get-Member ausblenden und die Ergebnisse für die automatische Vervollständigung mithilfe des Hidden-Schlüssel Worts ausblenden.

Fügen Sie das Hidden-Schlüsselwort hinzu, indem Sie es in derselben Anweisungs Zeile wie die-Eigenschaft und den zugehörigen Datentyp eingeben. Obwohl das-Schlüsselwort in einer beliebigen Reihenfolge in dieser Zeile angegeben werden kann, ist es für Sie später einfacher, alle Elemente zu identifizieren, die Sie ausgeblendet haben, wenn Sie die Anweisung mit dem Schlüsselwort Hidden starten.

```powershell
class Car
{
   # Properties
   [String] $Color
   [String] $ModelYear
   [int] $Distance

   # Method
   [int] Drive ([int]$miles)
   {
      $this.Distance += $miles
      $this.rides++
      return $this.Distance
   }

   # Hidden property of the Drive method
    hidden [int] $rides = 0
}
```

Erstellen Sie jetzt eine neue Instanz der Car-Klasse, und speichern Sie Sie in einer Variablen, \$ testcar.

```powershell
$TestCar = [Car]::new()
```

Nachdem Sie die neue Instanz erstellt haben, übergeben Sie den Inhalt der $TestCar-Variablen an Get-Member. Beachten Sie, dass die Rides-Eigenschaft nicht zu den in den Get-Member Befehls Ergebnissen aufgelisteten Membern gehört.

```output
PS C:\Windows\system32> $TestCar | Get-Member

   TypeName: Car

Name        MemberType Definition
----        ---------- ----------
Drive       Method     int Drive(int miles)
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
ToString    Method     string ToString()
Color       Property   string Color {get;set;}
Distance    Property   int Distance {get;set;}
ModelYear   Property   string ModelYear {get;set;}

```

Versuchen Sie jetzt, Get-Member erneut auszuführen, aber fügen Sie dieses Mal den-Force-Parameter hinzu.
Beachten Sie, dass die Ergebnisse die ausgeblendete Rides-Eigenschaft enthalten, darunter andere Member, die standardmäßig ausgeblendet sind.

```output
PS C:\Windows\system32> $TestCar | Get-Member -Force

   TypeName: Car

Name          MemberType   Definition
----          ----------   ----------
pstypenames   CodeProperty System.Collections.ObjectModel.Collection`1
psadapted     MemberSet    psadapted {Color, ModelYear, Distance,
psbase        MemberSet    psbase {Color, ModelYear, Distance,...
psextended    MemberSet    psextended {}
psobject      MemberSet    psobject {BaseObject, Members,...
Drive         Method       int Drive(int miles)
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
get_Color     Method       string get_Color()
get_Distance  Method       int get_Distance()
get_ModelYear Method       string get_ModelYear()
get_rides     Method       int get_rides()
set_Color     Method       void set_Color(string )
set_Distance  Method       void set_Distance(int )
set_ModelYear Method       void set_ModelYear(string )
set_rides     Method       void set_rides(int )
ToString      Method       string ToString()
Color         Property     string Color {get;set;}
Distance      Property     int Distance {get;set;}
ModelYear     Property     string ModelYear {get;set;}
rides         Property     int rides {get;set;}

```

## <a name="see-also"></a>SIEHE AUCH

[about_Classes](about_Classes.md)

[about_Language_Keywords](about_Language_Keywords.md)

[about_Wildcards](about_Wildcards.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)
