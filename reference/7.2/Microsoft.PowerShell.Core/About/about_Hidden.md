---
description: Beschreibt das Hidden-Schlüsselwort, das Klassenmember aus Standard Get-Member Ergebnissen verbirgt.
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hidden?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hidden
ms.openlocfilehash: 8340a955b7cfa540baccde0da233d6d9cf0c5552
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597371"
---
# <a name="about_hidden"></a><span data-ttu-id="99816-103">about_Hidden</span><span class="sxs-lookup"><span data-stu-id="99816-103">about_Hidden</span></span>

## <a name="short-description"></a><span data-ttu-id="99816-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="99816-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="99816-105">Beschreibt das Hidden-Schlüsselwort, das Klassenmember aus Standard Get-Member Ergebnissen verbirgt.</span><span class="sxs-lookup"><span data-stu-id="99816-105">Describes the Hidden keyword, which hides class members from default Get-Member results.</span></span>

## <a name="long-description"></a><span data-ttu-id="99816-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="99816-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="99816-107">Wenn Sie das Hidden-Schlüsselwort in einem Skript verwenden, blenden Sie die Member einer Klasse standardmäßig aus.</span><span class="sxs-lookup"><span data-stu-id="99816-107">When you use the Hidden keyword in a script, you hide the members of a class by default.</span></span> <span data-ttu-id="99816-108">Mit dem Schlüsselwort Hidden können Eigenschaften, Methoden (einschließlich Konstruktoren, Ereignisse, Alias Eigenschaften und andere Elementtypen, einschließlich statischer Member, aus den Standard Ergebnissen des Get-Member Cmdlets) und aus den Ergebnissen von IntelliSense und der Vervollständigung von Registerkarten ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="99816-108">The Hidden keyword can hide properties, methods (including constructors, events, alias properties, and other member types, including static members, from the default results of the Get-Member cmdlet, and from IntelliSense and tab completion results.</span></span> <span data-ttu-id="99816-109">Fügen Sie zum Anzeigen von Membern, die Sie mit dem Hidden-Schlüsselwort ausgeblendet haben, den-Force-Parameter einem Get-Member-Befehl hinzu.</span><span class="sxs-lookup"><span data-stu-id="99816-109">To display members that you have hidden with the Hidden keyword, add the -Force parameter to a Get-Member command.</span></span>

<span data-ttu-id="99816-110">Ausgeblendete Member werden nicht mit der Vervollständigung mit der Tab-Taste oder mit IntelliSense angezeigt, es sei denn, der Abschluss tritt in der Klasse auf, die</span><span class="sxs-lookup"><span data-stu-id="99816-110">Hidden members are not displayed by using tab completion or IntelliSense, unless the completion occurs in the class that defines the hidden member.</span></span>

<span data-ttu-id="99816-111">Das neue Attribut System. Management. Automation. hiddenattribute wurde hinzugefügt, sodass C- \# Code in PowerShell die gleiche Semantik aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="99816-111">A new attribute, System.Management.Automation.HiddenAttribute, has been added, so that C\# code can have the same semantics within PowerShell.</span></span>

<span data-ttu-id="99816-112">Das Hidden-Schlüsselwort ist nützlich zum Erstellen von Eigenschaften und Methoden in einer Klasse, die von anderen Benutzern der Klasse nicht unbedingt angezeigt werden sollen, oder die Sie problemlos bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="99816-112">The Hidden keyword is useful for creating properties and methods within a class that you do not necessarily want other users of the class to see, or readily be able to edit.</span></span>

<span data-ttu-id="99816-113">Das Hidden-Schlüsselwort hat keine Auswirkung darauf, wie Sie Member einer Klasse anzeigen oder ändern können.</span><span class="sxs-lookup"><span data-stu-id="99816-113">The Hidden keyword has no effect on how you can view or make changes to members of a class.</span></span> <span data-ttu-id="99816-114">Wie bei allen Sprach Schlüsselwörtern in PowerShell wird bei Hidden nicht zwischen Groß-und Kleinschreibung unterschieden</span><span class="sxs-lookup"><span data-stu-id="99816-114">Like all language keywords in PowerShell, Hidden is not case-sensitive, and hidden members are still public.</span></span>

<span data-ttu-id="99816-115">Hidden wurde zusammen mit benutzerdefinierten Klassen in PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="99816-115">Hidden, along with custom classes, was introduced in PowerShell 5.0.</span></span>

## <a name="example"></a><span data-ttu-id="99816-116">BEISPIEL</span><span class="sxs-lookup"><span data-stu-id="99816-116">EXAMPLE</span></span>

<span data-ttu-id="99816-117">Im folgenden Beispiel wird gezeigt, wie das Hidden-Schlüsselwort in einer Klassendefinition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="99816-117">The following example shows how to use the Hidden keyword in a class definition.</span></span> <span data-ttu-id="99816-118">Die Auto-Klassenmethode, Laufwerk, verfügt über eine Eigenschaft, "Rides", die nicht angezeigt oder geändert werden muss (es gibt lediglich an, wie oft das Laufwerk auf der Auto-Klasse aufgerufen wird, eine Metrik, die für Benutzer der Klasse nicht wichtig ist. Wenn Sie z. b. ein Auto kaufen, Fragen Sie den Verkäufer nicht, wie viele Laufwerke das Auto beansprucht hat.</span><span class="sxs-lookup"><span data-stu-id="99816-118">The Car class method, Drive, has a property, rides, that does not need to be viewed or changed (it merely tallies the number of times that Drive is called on the Car class, a metric that is not important to users of the class; consider, for example, that when you are buying a car, you do not ask the seller on how many drives the car has been taken.</span></span>

<span data-ttu-id="99816-119">Da es für Benutzer der-Klasse wenig erforderlich ist, diese Eigenschaft zu ändern, können Sie die-Eigenschaft aus Get-Member ausblenden und die Ergebnisse für die automatische Vervollständigung mithilfe des Hidden-Schlüssel Worts ausblenden.</span><span class="sxs-lookup"><span data-stu-id="99816-119">Because there is little need for users of the class to change this property, we can hide the property from Get-Member and automatic completion results by using the Hidden keyword.</span></span>

<span data-ttu-id="99816-120">Fügen Sie das Hidden-Schlüsselwort hinzu, indem Sie es in derselben Anweisungs Zeile wie die-Eigenschaft und den zugehörigen Datentyp eingeben.</span><span class="sxs-lookup"><span data-stu-id="99816-120">Add the Hidden keyword by entering it on the same statement line as the property and its data type.</span></span> <span data-ttu-id="99816-121">Obwohl das-Schlüsselwort in einer beliebigen Reihenfolge in dieser Zeile angegeben werden kann, ist es für Sie später einfacher, alle Elemente zu identifizieren, die Sie ausgeblendet haben, wenn Sie die Anweisung mit dem Schlüsselwort Hidden starten.</span><span class="sxs-lookup"><span data-stu-id="99816-121">Although the keyword can be in any order on this line, starting the statement with the Hidden keyword makes it easier for you later to identify all members that you have hidden.</span></span>

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

<span data-ttu-id="99816-122">Erstellen Sie jetzt eine neue Instanz der Car-Klasse, und speichern Sie Sie in einer Variablen, \$ testcar.</span><span class="sxs-lookup"><span data-stu-id="99816-122">Now, create a new instance of the Car class, and save it in a variable, \$TestCar.</span></span>

```powershell
$TestCar = [Car]::new()
```

<span data-ttu-id="99816-123">Nachdem Sie die neue Instanz erstellt haben, übergeben Sie den Inhalt der $TestCar-Variablen an Get-Member.</span><span class="sxs-lookup"><span data-stu-id="99816-123">After you create the new instance, pipe the contents of the $TestCar variable to Get-Member.</span></span> <span data-ttu-id="99816-124">Beachten Sie, dass die Rides-Eigenschaft nicht zu den in den Get-Member Befehls Ergebnissen aufgelisteten Membern gehört.</span><span class="sxs-lookup"><span data-stu-id="99816-124">Observe that the rides property is not among the members listed in the Get-Member command results.</span></span>

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

<span data-ttu-id="99816-125">Versuchen Sie jetzt, Get-Member erneut auszuführen, aber fügen Sie dieses Mal den-Force-Parameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="99816-125">Now, try running Get-Member again, but this time, add the -Force parameter.</span></span>
<span data-ttu-id="99816-126">Beachten Sie, dass die Ergebnisse die ausgeblendete Rides-Eigenschaft enthalten, darunter andere Member, die standardmäßig ausgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="99816-126">Note that the results contain the hidden rides property, among other members that are hidden by default.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="99816-127">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="99816-127">SEE ALSO</span></span>

[<span data-ttu-id="99816-128">about_Classes</span><span class="sxs-lookup"><span data-stu-id="99816-128">about_Classes</span></span>](about_Classes.md)

[<span data-ttu-id="99816-129">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="99816-129">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="99816-130">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="99816-130">about_Wildcards</span></span>](about_Wildcards.md)

[<span data-ttu-id="99816-131">Get-Member</span><span class="sxs-lookup"><span data-stu-id="99816-131">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

