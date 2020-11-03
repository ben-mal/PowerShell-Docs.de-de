---
description: Beschreibt die WMI-Abfragesprache (WQL), die zum Abrufen von WMI-Objekten in Windows PowerShell verwendet werden kann.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wql?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WQL
ms.openlocfilehash: c6fd523864d419fb400b7041e92ec8f0733724b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223188"
---
# <a name="about-wql"></a><span data-ttu-id="86e2a-104">Informationen zu WQL</span><span class="sxs-lookup"><span data-stu-id="86e2a-104">About WQL</span></span>

## <a name="short-description"></a><span data-ttu-id="86e2a-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="86e2a-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="86e2a-106">Beschreibt die WMI-Abfragesprache (WQL), die zum Abrufen von WMI-Objekten in Windows PowerShell verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="86e2a-106">Describes WMI Query Language (WQL), which can be used to get WMI objects in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="86e2a-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="86e2a-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="86e2a-108">WQL ist die WMI-Abfragesprache (Windows-Verwaltungsinstrumentation), die zum erhalten von Informationen aus WMI verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86e2a-108">WQL is the Windows Management Instrumentation (WMI) query language, which is the language used to get information from WMI.</span></span>

<span data-ttu-id="86e2a-109">Es ist nicht erforderlich, WQL zum Ausführen einer WMI-Abfrage in Windows PowerShell zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-109">You are not required to use WQL to perform a WMI query in Windows PowerShell.</span></span>
<span data-ttu-id="86e2a-110">Stattdessen können Sie die Parameter der Get-WmiObject oder Get-CimInstance-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-110">Instead, you can use the parameters of the Get-WmiObject or Get-CimInstance cmdlets.</span></span> <span data-ttu-id="86e2a-111">WQL-Abfragen sind etwas schneller als Standard Get-WmiObject Befehle, und die verbesserte Leistung ist offensichtlich, wenn die Befehle auf Hunderten von Systemen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-111">WQL queries are somewhat faster than standard Get-WmiObject commands and the improved performance is evident when the commands run on hundreds of systems.</span></span> <span data-ttu-id="86e2a-112">Achten Sie jedoch darauf, dass die Zeit, die Sie für das Schreiben einer erfolgreichen WQL-Abfrage aufwenden, die Leistungsverbesserung nicht aufwiegen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-112">However, be sure that the time you spend to write a successful WQL query doesn't outweigh the performance improvement.</span></span>

<span data-ttu-id="86e2a-113">Die grundlegenden WQL-Anweisungen, die Sie für die Verwendung von WQL benötigen, sind SELECT, WHERE und from.</span><span class="sxs-lookup"><span data-stu-id="86e2a-113">The basic WQL statements you need to use WQL are Select, Where, and From.</span></span>

## <a name="when-to-use-wql"></a><span data-ttu-id="86e2a-114">Verwendungszwecke von WQL</span><span class="sxs-lookup"><span data-stu-id="86e2a-114">WHEN TO USE WQL</span></span>

<span data-ttu-id="86e2a-115">Vergessen Sie beim Arbeiten mit WMI und insbesondere bei WQL nicht, dass Sie auch Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-115">When working with WMI, and especially with WQL, do not forget that you are also using Windows PowerShell.</span></span> <span data-ttu-id="86e2a-116">Wenn eine WQL-Abfrage nicht erwartungsgemäß funktioniert, ist es einfacher, einen standardmäßigen Windows PowerShell-Befehl zu verwenden, als die WQL-Abfrage zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-116">Often, if a WQL query does not work as expected, it's easier to use a standard Windows PowerShell command than to debug the WQL query.</span></span>

<span data-ttu-id="86e2a-117">Wenn Sie keine großen Datenmengen aus einem Remote System mit Bandbreitenbeschränkung zurückgeben, ist es selten produktiv, Stunden zu verbringen, eine komplizierte und bearbeiteme WQL-Abfrage zu optimieren, wenn ein absolut akzeptables Windows-Cmdlet vorhanden ist, das das gleiche tut, wenn es etwas langsamer ist.</span><span class="sxs-lookup"><span data-stu-id="86e2a-117">Unless you are returning massive amounts of data from across bandwidth-constrained remote systems, it is rarely productive to spend hours trying to perfect a complicated and convoluted WQL query when there is a perfectly acceptable Windows cmdlet that does the same thing, if a bit more slowly.</span></span>

## <a name="using-the-select-statement"></a><span data-ttu-id="86e2a-118">Verwenden der SELECT-Anweisung</span><span class="sxs-lookup"><span data-stu-id="86e2a-118">USING THE SELECT STATEMENT</span></span>

<span data-ttu-id="86e2a-119">Eine typische WMI-Abfrage beginnt mit einer SELECT-Anweisung, die alle Eigenschaften oder bestimmte Eigenschaften einer WMI-Klasse abruft.</span><span class="sxs-lookup"><span data-stu-id="86e2a-119">A typical WMI query begins with a Select statement that gets all properties or particular properties of a WMI class.</span></span> <span data-ttu-id="86e2a-120">Wenn Sie alle Eigenschaften einer WMI-Klasse auswählen möchten, verwenden Sie ein Sternchen ( \* ).</span><span class="sxs-lookup"><span data-stu-id="86e2a-120">To select all properties of a WMI class, use an asterisk (\*).</span></span> <span data-ttu-id="86e2a-121">Das from-Schlüsselwort gibt die WMI-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="86e2a-121">The From keyword specifies the WMI class.</span></span>

<span data-ttu-id="86e2a-122">Eine SELECT-Anweisung weist das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="86e2a-122">A Select statement has the following format:</span></span>

```
Select <property> from <WMI-class>
```

<span data-ttu-id="86e2a-123">Mit der folgenden SELECT-Anweisung werden z. b. alle Eigenschaften (\*) aus den Instanzen der WMI-Klasse Win32_Bios ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-123">For example, the following Select statement selects all properties (\*) from the instances of the Win32_Bios WMI class.</span></span>

```
Select * from Win32_Bios
```

<span data-ttu-id="86e2a-124">Um eine bestimmte Eigenschaft einer WMI-Klasse auszuwählen, platzieren Sie den Eigenschaftsnamen zwischen den Schlüsselwörtern SELECT und from.</span><span class="sxs-lookup"><span data-stu-id="86e2a-124">To select a particular property of a WMI class, place the property name between the Select and From keywords.</span></span>

<span data-ttu-id="86e2a-125">Mit der folgenden Abfrage wird nur der Name des BIOS aus der Win32_Bios WMI-Klasse ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-125">The following query selects only the name of the BIOS from the Win32_Bios WMI class.</span></span> <span data-ttu-id="86e2a-126">Der Befehl speichert die Abfrage in der $queryName Variable.</span><span class="sxs-lookup"><span data-stu-id="86e2a-126">The command saves the query in the $queryName variable.</span></span>

```
Select Name from Win32_Bios
```

<span data-ttu-id="86e2a-127">Wenn Sie mehr als eine Eigenschaft auswählen möchten, verwenden Sie Kommas, um die Eigenschaften Namen voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-127">To select more than one property, use commas to separate the property names.</span></span>
<span data-ttu-id="86e2a-128">In der folgenden WMI-Abfrage werden der Name und die Version der Win32_Bios WMI-Klasse ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-128">The following WMI query selects the name and the version of the Win32_Bios WMI class.</span></span> <span data-ttu-id="86e2a-129">Der Befehl speichert die Abfrage in der $queryNameVersion Variable.</span><span class="sxs-lookup"><span data-stu-id="86e2a-129">The command saves the query in the $queryNameVersion variable.</span></span>

```
Select name, version from Win32_Bios
```

## <a name="using-the-wql-query"></a><span data-ttu-id="86e2a-130">Verwenden der WQL-Abfrage</span><span class="sxs-lookup"><span data-stu-id="86e2a-130">USING THE WQL QUERY</span></span>

<span data-ttu-id="86e2a-131">Es gibt drei Möglichkeiten, die WQL-Abfrage im Windows PowerShell-Befehl zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-131">There are three ways to use WQL query in Windows PowerShell command.</span></span>

- <span data-ttu-id="86e2a-132">Verwenden Sie das Cmdlet "Get-WmiObject".</span><span class="sxs-lookup"><span data-stu-id="86e2a-132">Use the Get-WmiObject cmdlet</span></span>
- <span data-ttu-id="86e2a-133">Verwenden Sie das Cmdlet "Get-CimInstance".</span><span class="sxs-lookup"><span data-stu-id="86e2a-133">Use the Get-CimInstance cmdlet</span></span>
- <span data-ttu-id="86e2a-134">Verwenden Sie die typbeschleunigung [wmisearcher].</span><span class="sxs-lookup"><span data-stu-id="86e2a-134">Use the [wmisearcher] type accelerator.</span></span>

## <a name="using-the-get-wmiobject-cmdlet"></a><span data-ttu-id="86e2a-135">Verwenden des Cmdlets "Get-WmiObject"</span><span class="sxs-lookup"><span data-stu-id="86e2a-135">USING THE GET-WMIOBJECT CMDLET</span></span>

<span data-ttu-id="86e2a-136">Die einfachste Möglichkeit, die WQL-Abfrage zu verwenden, besteht darin, Sie in Anführungszeichen (als Zeichenfolge) einzuschließen und anschließend die Abfrage Zeichenfolge als Wert des Abfrage Parameters des Get-WmiObject-Cmdlets zu verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-136">The most basic way to use the WQL query is to enclose it in quotation marks (as a string) and then use the query string as the value of the Query parameter of the Get-WmiObject cmdlet, as shown in the following example.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="86e2a-137">Sie können auch die WQL-Anweisung in einer Variablen speichern und dann die Variable als Wert des Abfrage Parameters verwenden, wie im folgenden Befehl gezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-137">You can also save the WQL statement in a variable and then use the variable as the value of the Query parameter, as shown in the following command.</span></span>

```powershell
$query = "Select * from Win32_Bios"
Get-WmiObject -Query $query
```

<span data-ttu-id="86e2a-138">Beide Formate können mit einer beliebigen WQL-Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-138">You can use either format with any WQL statement.</span></span> <span data-ttu-id="86e2a-139">Der folgende Befehl verwendet die Abfrage in der $queryName-Variablen, um nur die Namens-und Versions Eigenschaften des System-BIOS zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="86e2a-139">The following command uses the query in the $queryName variable to get only the name and version properties of the system BIOS.</span></span>

```powershell
$queryNameVersion = "Select Name, Version from Win32_Bios"
Get-WmiObject -Query $queryNameVersion
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

<span data-ttu-id="86e2a-140">Beachten Sie, dass Sie die Parameter des Get-WmiObject-Cmdlets verwenden können, um das gleiche Ergebnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="86e2a-140">Remember that you can use the parameters of the Get-WmiObject cmdlet to get the same result.</span></span> <span data-ttu-id="86e2a-141">Der folgende Befehl ruft z. b. auch die Werte der Eigenschaften "Name" und "Version" der Instanzen der Win32_Bios WMI-Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="86e2a-141">For example, the following command also gets the values of the Name and Version properties of instances of the Win32_Bios WMI class.</span></span>

```powershell
Get-WmiObject -Class Win32_Bios -Property Name, Version
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
Version          : LENOVO - 1360
```

## <a name="using-the-get-ciminstance-cmdlet"></a><span data-ttu-id="86e2a-142">Verwenden des Cmdlets "Get-ciminstance"</span><span class="sxs-lookup"><span data-stu-id="86e2a-142">USING THE GET-CIMINSTANCE CMDLET</span></span>

<span data-ttu-id="86e2a-143">Ab Windows PowerShell 3,0 können Sie das Cmdlet "Get-CimInstance" verwenden, um WQL-Abfragen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-143">Beginning in Windows PowerShell 3.0, you can use the Get-CimInstance cmdlet to run WQL queries.</span></span>

<span data-ttu-id="86e2a-144">Get-CimInstance ruft Instanzen von CIM-kompatiblen Klassen ab, einschließlich WMI-Klassen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-144">Get-CimInstance gets instances of CIM-compliant classes, including WMI classes.</span></span> <span data-ttu-id="86e2a-145">Die CIM-Cmdlets, die Windows PowerShell 3,0 eingeführt haben, führen dieselben Aufgaben wie die WMI-Cmdlets aus.</span><span class="sxs-lookup"><span data-stu-id="86e2a-145">The CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="86e2a-146">Die CIM-Cmdlets entsprechen den WS-Management (WSMAN)-Standards und dem Common Information Model (CIM)-Standard, mit dem die Cmdlets dieselben Verfahren zum Verwalten von Windows-Computern und-Computern verwenden können, auf denen andere Betriebssysteme ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-146">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, which enables the cmdlets to use the same techniques to manage Windows computers and computers that are running other operating systems.</span></span>

<span data-ttu-id="86e2a-147">Der folgende Befehl verwendet das Cmdlet "Get-CimInstance", um eine WQL-Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-147">The following command uses the Get-CimInstance cmdlet to run a WQL query.</span></span>

<span data-ttu-id="86e2a-148">Jede WQL-Abfrage, die mit Get-WmiObject verwendet werden kann, kann auch mit Get-ciminstance verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-148">Any WQL query that can be used with Get-WmiObject can also be used with Get-CimInstance.</span></span>

```powershell
Get-CimInstance -Query "Select * from Win32_Bios"
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="86e2a-149">Get-CimInstance gibt ein ciminstance-Objekt zurück, anstelle des ManagementObject, das Get-WmiObject zurückgibt, aber die-Objekte sind sehr ähnlich.</span><span class="sxs-lookup"><span data-stu-id="86e2a-149">Get-CimInstance returns a CimInstance object, instead of the ManagementObject that Get-WmiObject returns, but the objects are quite similar.</span></span>

```
(Get-CimInstance -Query "Select * from Win32_Bios").GetType().FullName
Microsoft.Management.Infrastructure.CimInstance
(Get-WmiObject -Query "Select * from Win32_Bios").GetType().FullName
System.Management.ManagementObject
```

## <a name="using-the-wmisearcher-type-accelerator"></a><span data-ttu-id="86e2a-150">Verwenden der [wmisearcher]-typbeschleunigung</span><span class="sxs-lookup"><span data-stu-id="86e2a-150">USING THE [wmisearcher] TYPE ACCELERATOR</span></span>

<span data-ttu-id="86e2a-151">Die typbeschleunigung [wmisearcher] erstellt ein ManagementObjectSearcher-Objekt aus einer WQL-Anweisungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="86e2a-151">The [wmisearcher] type accelerator creates a ManagementObjectSearcher object from a WQL statement string.</span></span> <span data-ttu-id="86e2a-152">Das ManagementObjectSearcher-Objekt verfügt über viele Eigenschaften und Methoden, aber die grundlegendste Methode ist die Get-Methode, die die angegebene WMI-Abfrage aufruft und die resultierenden Objekte zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-152">The ManagementObjectSearcher object has many properties and methods, but the most basic method is the Get method, which invokes the specified WMI query and returns the resulting objects.</span></span>

<span data-ttu-id="86e2a-153">Wenn Sie [wmisearcher] verwenden, erhalten Sie einfachen Zugriff auf die ManagementObjectSearcher-.NET Framework-Klasse.</span><span class="sxs-lookup"><span data-stu-id="86e2a-153">By using the [wmisearcher], you gain easy access to the ManagementObjectSearcher .NET Framework class.</span></span> <span data-ttu-id="86e2a-154">Auf diese Weise können Sie WMI Abfragen und die Art und Weise konfigurieren, wie die Abfrage durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="86e2a-154">This lets you query WMI and to configure the way the query is conducted.</span></span>

<span data-ttu-id="86e2a-155">So verwenden Sie die "[wmisearcher]"-typbeschleunigung:</span><span class="sxs-lookup"><span data-stu-id="86e2a-155">To use the [wmisearcher] type accelerator:</span></span>

1. <span data-ttu-id="86e2a-156">Wandeln Sie die WQL-Zeichenfolge in ein ManagementObjectSearcher-Objekt um.</span><span class="sxs-lookup"><span data-stu-id="86e2a-156">Cast the  WQL string into a ManagementObjectSearcher object.</span></span>
2. <span data-ttu-id="86e2a-157">Ruft die Get-Methode des ManagementObjectSearcher-Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="86e2a-157">Call the Get method of the ManagementObjectSearcher object.</span></span>

<span data-ttu-id="86e2a-158">Der folgende Befehl wandelt z. b. die Abfrage "Select all" um, speichert das Ergebnis in der $BIOS Variable und ruft dann die Get-Methode des ManagementObjectSearcher-Objekts in der $BIOS-Variablen auf.</span><span class="sxs-lookup"><span data-stu-id="86e2a-158">For example, the following command casts the "select all" query, saves the result in the $bios variable, and then calls the Get method of the ManagementObjectSearcher object in the $bios variable.</span></span>

```powershell
$bios = [wmisearcher]"Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="86e2a-159">Hinweis: Standardmäßig werden nur ausgewählte Objekteigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-159">NOTE: Only selected object properties are displayed by default.</span></span> <span data-ttu-id="86e2a-160">Diese Eigenschaften werden in der Types.ps1-XML-Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="86e2a-160">These properties are defined in the Types.ps1xml file.</span></span>

<span data-ttu-id="86e2a-161">Sie können die typbeschleunigung [wmisearcher] zum Umwandeln der Abfrage oder der Variablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-161">You can use the [wmisearcher] type accelerator to cast the query or the variable.</span></span> <span data-ttu-id="86e2a-162">Im folgenden Beispiel wird die typbeschleunigung [wmisearcher] zum Umwandeln der Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="86e2a-162">In the following example, the [wmisearcher] type accelerator is used to cast the variable.</span></span> <span data-ttu-id="86e2a-163">Das Ergebnis ist identisch.</span><span class="sxs-lookup"><span data-stu-id="86e2a-163">The result is the same.</span></span>

```powershell
[wmisearcher]$bios = "Select * from Win32_Bios"
$bios.Get()
```

```output
SMBIOSBIOSVersion : 8BET56WW (1.36 )
Manufacturer      : LENOVO
Name              : Default System BIOS
SerialNumber      : R9FPY3P
Version           : LENOVO - 1360
```

<span data-ttu-id="86e2a-164">Wenn Sie die typbeschleunigung [wmisearcher] verwenden, wird die Abfrage Zeichenfolge in ein ManagementObjectSearcher-Objekt geändert, wie in den folgenden Befehlen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-164">When you use the [wmisearcher] type accelerator, it changes the query string into a ManagementObjectSearcher object, as shown in the following commands.</span></span>

```
$a = "Select * from Win32_Bios"
$a.GetType().FullName
System.String

$a = [wmisearcher]"Select * from Win32_Bios"
$a.GetType().FullName
System.Management.ManagementObjectSearcher
```

<span data-ttu-id="86e2a-165">Dieses Befehls Format funktioniert bei jeder Abfrage.</span><span class="sxs-lookup"><span data-stu-id="86e2a-165">This command format works on any query.</span></span> <span data-ttu-id="86e2a-166">Der folgende Befehl ruft den Wert der Name-Eigenschaft der Win32_Bios WMI-Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="86e2a-166">The following command gets the value of the Name property of the Win32_Bios WMI class.</span></span>

```powershell
$biosname = [wmisearcher]"Select Name from Win32_Bios"
$biosname.Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

<span data-ttu-id="86e2a-167">Sie können diesen Vorgang in einem einzigen Befehl ausführen, obwohl der Befehl etwas schwieriger zu interpretieren ist.</span><span class="sxs-lookup"><span data-stu-id="86e2a-167">You can perform this operation in a single command, although the command is a bit more difficult to interpret.</span></span>

<span data-ttu-id="86e2a-168">In diesem Format verwenden Sie die typbeschleunigung [wmisearcher], um die WQL-Abfrage Zeichenfolge in einen ManagementObjectSearcher umzuwandeln. Anschließend wird die Get-Methode für das Objekt aufgerufen, und zwar in einem einzigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="86e2a-168">In this format, you use the [wmisearcher] type accelerator to cast the WQL query string to a ManagementObjectSearcher, and then call the Get method on the object -- all in a single command.</span></span> <span data-ttu-id="86e2a-169">Die Klammern (), die die eingefügte Zeichenfolge einschließen, leiten Windows PowerShell direkt in die Zeichenfolge ein, bevor die-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="86e2a-169">The parentheses () that enclose the casted string direct Windows PowerShell to cast the string before calling the method.</span></span>

```powershell
([wmisearcher]"Select name from Win32_Bios").Get()
```

```output
__GENUS          : 2
__CLASS          : Win32_BIOS
__SUPERCLASS     :
__DYNASTY        :
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Name             : Default System BIOS
```

## <a name="using-the-basic-wql-where-statement"></a><span data-ttu-id="86e2a-170">Verwenden der einfachen WQL WHERE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="86e2a-170">USING THE BASIC WQL WHERE STATEMENT</span></span>

<span data-ttu-id="86e2a-171">Eine WHERE-Anweisung legt Bedingungen für die Daten fest, die eine SELECT-Anweisung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-171">A Where statement establishes conditions for the data that a Select statement returns.</span></span>

<span data-ttu-id="86e2a-172">Die WHERE-Anweisung weist das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="86e2a-172">The Where statement has the following format:</span></span>

```
where <property> <operator> <value>
```

<span data-ttu-id="86e2a-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="86e2a-173">For example:</span></span>

```
where Name = 'Notepad.exe'
```

<span data-ttu-id="86e2a-174">Die WHERE-Anweisung wird mit der SELECT-Anweisung verwendet, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-174">The Where statement is used with the Select statement, as shown in the following example.</span></span>

```
Select * from Win32_Process where Name = 'Notepad.exe'
```

<span data-ttu-id="86e2a-175">Wenn Sie die WHERE-Anweisung verwenden, müssen der Eigenschaftsname und der Wert genau sein.</span><span class="sxs-lookup"><span data-stu-id="86e2a-175">When using the Where statement, the property name and value must be accurate.</span></span>

<span data-ttu-id="86e2a-176">Beispielsweise ruft der folgende Befehl die Notepad-Prozesse auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="86e2a-176">For example, the following command gets the Notepad processes on the local computer.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad.exe'"
```

<span data-ttu-id="86e2a-177">Der folgende Befehl schlägt jedoch fehl, da der Prozess Name die Dateinamenerweiterung ". exe" enthält.</span><span class="sxs-lookup"><span data-stu-id="86e2a-177">However, the following command fails, because the process name includes the ".exe" file name extension.</span></span>

```powershell
Get-WmiObject -Query "Select * from Win32_Process where name='Notepad'"
```

## <a name="where-statement-comparison-operators"></a><span data-ttu-id="86e2a-178">Where-Anweisungs Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="86e2a-178">WHERE STATEMENT COMPARISON OPERATORS</span></span>

<span data-ttu-id="86e2a-179">Die folgenden Operatoren sind in einer WQL WHERE-Anweisung gültig.</span><span class="sxs-lookup"><span data-stu-id="86e2a-179">The following operators are valid in a WQL Where statement.</span></span>

```
Operator    Description
-----------------------
=           Equal
!=          Not equal
<>          Not equal
<           Less than
>           Greater than
<=          Less than or equal
>=          Greater than or equal
LIKE        Wildcard match
IS          Evaluates null
ISNOT       Evaluates not null
ISA         Evaluates a member of a WMI class
```

<span data-ttu-id="86e2a-180">Es sind andere Operatoren vorhanden, die jedoch für Vergleiche verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-180">There are other operators, but these are the ones used for making comparisons.</span></span>

<span data-ttu-id="86e2a-181">Mit der folgenden Abfrage werden z. b. die Eigenschaften Name und Priorität aus Prozessen in der Win32_Process-Klasse ausgewählt, wobei die Prozesspriorität größer oder gleich 11 ist.</span><span class="sxs-lookup"><span data-stu-id="86e2a-181">For example, the following query selects the Name and Priority properties from processes in the Win32_Process class where the process priority is greater than or equal to 11.</span></span> <span data-ttu-id="86e2a-182">Das Get-WmiObject-Cmdlet führt die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="86e2a-182">The Get-WmiObject cmdlet runs the query.</span></span>

```powershell
$highPriority = "Select Name, Priority from Win32_Process " +
  "where Priority >= 11"
Get-WmiObject -Query $highPriority
```

## <a name="using-the-wql-operators-in-the-filter-parameter"></a><span data-ttu-id="86e2a-183">Verwenden der WQL-Operatoren im Filter-Parameter</span><span class="sxs-lookup"><span data-stu-id="86e2a-183">USING THE WQL OPERATORS IN THE FILTER PARAMETER</span></span>

<span data-ttu-id="86e2a-184">Die WQL-Operatoren können auch im Wert des Filter-Parameters der Get-WmiObject-oder Get-CimInstance-Cmdlets sowie im Wert der Abfrage Parameter dieser Cmdlets verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-184">The WQL operators can also be used in the value of the Filter parameter of the Get-WmiObject or Get-CimInstance cmdlets, as well as in the value of the Query parameters of these cmdlets.</span></span>

<span data-ttu-id="86e2a-185">Der folgende Befehl ruft z. b. die Eigenschaften "Name" und "ProcessId" der letzten fünf Prozesse ab, deren ProcessID-Werte größer als 1004 sind.</span><span class="sxs-lookup"><span data-stu-id="86e2a-185">For example, the following command gets the Name and ProcessID properties of the last five processes that have ProcessID values greater than 1004.</span></span> <span data-ttu-id="86e2a-186">Der Befehl verwendet den Filter-Parameter, um die ProcessID-Bedingung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="86e2a-186">The command uses the Filter parameter to specify the ProcessID condition.</span></span>

```powershell
Get-WmiObject -Class Win32_Process `
-Property Name, ProcessID -Filter "ProcessID >= 1004" |
Sort ProcessID | Select Name, ProcessID -Last 5
```

```output
Name                                 ProcessID
----                                 ---------
SROSVC.exe                                4220
WINWORD.EXE                               4664
TscHelp.exe                               4744
SnagIt32.exe                              4748
WmiPrvSE.exe                              5056
```

## <a name="using-the-like-operator"></a><span data-ttu-id="86e2a-187">Verwenden des LIKE-Operators</span><span class="sxs-lookup"><span data-stu-id="86e2a-187">USING THE LIKE OPERATOR</span></span>

<span data-ttu-id="86e2a-188">Mit dem Like-Operator können Sie Platzhalter Zeichen verwenden, um die Ergebnisse einer WQL-Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="86e2a-188">The Like operator lets you use wildcard characters to filter the results of a WQL query.</span></span>

```
Like Operator  Description
--------------------------------------------------
[]             Character in a range [a-f] or a set
               of characters [abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

^              Character not in a range [^a-f] or
               not in a set [^abcdef]. The items in
               a set do not need to be consecutive or
               listed in alphabetical order.

%              A string of zero or more characters

_              One character.
(underscore)   NOTE: To use a literal underscore
               in a query string, enclose it in
               square brackets [_].
```

<span data-ttu-id="86e2a-189">Wenn der Like-Operator ohne Platzhalter Zeichen oder Bereichs Operatoren verwendet wird, verhält er sich wie der Gleichheits Operator (=) und gibt nur dann Objekte zurück, wenn er eine genaue Übereinstimmung für das Muster ist.</span><span class="sxs-lookup"><span data-stu-id="86e2a-189">When the Like operator is used without any wildcard characters or range operators, it behaves like the equality operator (=) and returns objects only when they are an exact match for the pattern.</span></span>

<span data-ttu-id="86e2a-190">Sie können den Bereichs Vorgang mit dem Platzhalter Zeichen% kombinieren, um einfache, aber leistungsstarke Filter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-190">You can combine the range operation with the percent wildcard character to create simple, yet powerful filters.</span></span>

### <a name="like-operator-examples"></a><span data-ttu-id="86e2a-191">Like-Operator Beispiele</span><span class="sxs-lookup"><span data-stu-id="86e2a-191">LIKE OPERATOR EXAMPLES</span></span>

#### <a name="example-1-range"></a><span data-ttu-id="86e2a-192">Beispiel 1: [ \<range> ]</span><span class="sxs-lookup"><span data-stu-id="86e2a-192">EXAMPLE 1: [\<range>]</span></span>

<span data-ttu-id="86e2a-193">Die folgenden Befehle starten Notepad und suchen dann nach einer Instanz der Win32_Process-Klasse mit einem Namen, der mit einem Buchstaben zwischen "H" und "N" beginnt (ohne Beachtung der Groß-/Kleinschreibung).</span><span class="sxs-lookup"><span data-stu-id="86e2a-193">The following commands start Notepad and then search for an instance of the Win32_Process class that has a name that starts with a letter between "H" and "N" (case-insensitive).</span></span>

<span data-ttu-id="86e2a-194">Die Abfrage sollte jeden Prozess von Hotpad.exe durch Notepad.exe zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="86e2a-194">The query should return any process from Hotpad.exe through Notepad.exe.</span></span>

```powershell
Notepad   # Starts Notepad
$query = "Select * from win32_Process where Name LIKE '[H-N]otepad.exe'"
Get-WmiObject -Query $query | Select Name, ProcessID
```

```output
Name                                ProcessID
----                                ---------
notepad.exe                              1740
```

#### <a name="example-2-range-and-"></a><span data-ttu-id="86e2a-195">Beispiel 2: [ \<range> ] und%</span><span class="sxs-lookup"><span data-stu-id="86e2a-195">EXAMPLE 2: [\<range>] and %</span></span>

<span data-ttu-id="86e2a-196">Mit den folgenden Befehlen wird der gesamte Prozess ausgewählt, dessen Name mit einem Buchstaben zwischen a und P beginnt (ohne Beachtung der Groß-/Kleinschreibung), gefolgt von NULL oder mehr Buchstaben in beliebiger Kombination.</span><span class="sxs-lookup"><span data-stu-id="86e2a-196">The following commands select all process that have a name that begins with a letter between A and P (case-insensitive) followed by zero or more letters in any combination.</span></span>

<span data-ttu-id="86e2a-197">Das Cmdlet "Get-WmiObject" führt die Abfrage aus, das Select-Object-Cmdlet ruft die Eigenschaften "Name" und "ProcessId" ab, und das Sort-Object-Cmdlet sortiert die Ergebnisse in alphabetischer Reihenfolge nach Namen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-197">The Get-WmiObject cmdlet runs the query, the Select-Object cmdlet gets the Name and ProcessID properties, and the Sort-Object cmdlet sorts the results in alphabetical order by name.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE '[A-P]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-3-not-in-range-"></a><span data-ttu-id="86e2a-198">Beispiel 3: nicht im Bereich (^)</span><span class="sxs-lookup"><span data-stu-id="86e2a-198">EXAMPLE 3: Not in Range (^)</span></span>

<span data-ttu-id="86e2a-199">Der folgende Befehl ruft Prozesse ab, deren Namen nicht mit einem der folgenden Buchstaben beginnen: A, S, W, P, R, C, U, N</span><span class="sxs-lookup"><span data-stu-id="86e2a-199">The following command gets processes whose names do not begin with any of the following letters: A, S, W, P, R, C, U, N</span></span>

<span data-ttu-id="86e2a-200">und gefolgt von NULL oder mehr Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="86e2a-200">and followed zero or more letters.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE '[^ASWPRCUN]%'"
Get-WmiObject -Query $query |
Select-Object -Property Name, ProcessID |
Sort-Object -Property Name
```

#### <a name="example-4-any-characters----or-none-"></a><span data-ttu-id="86e2a-201">Beispiel 4: beliebige Zeichen--oder None (%)</span><span class="sxs-lookup"><span data-stu-id="86e2a-201">EXAMPLE 4: Any characters -- or none (%)</span></span>

<span data-ttu-id="86e2a-202">Die folgenden Befehle erhalten Prozesse, deren Namen mit "Calc" beginnen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-202">The following commands get processes that have names that begin with "calc".</span></span>
<span data-ttu-id="86e2a-203">Das Symbol "%" in WQL entspricht dem Sternchen \* Symbol () in regulären Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="86e2a-203">The % symbol in WQL is equivalent to the asterisk (\*) symbol in regular expressions.</span></span>

```powershell
$query = "Select * from win32_Process where Name LIKE 'calc%'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                               ProcessID
----                               ---------
calc.exe                                4424
```

#### <a name="example-5-one-character-_"></a><span data-ttu-id="86e2a-204">Beispiel 5: ein Zeichen (_)</span><span class="sxs-lookup"><span data-stu-id="86e2a-204">EXAMPLE 5: One character (_)</span></span>

<span data-ttu-id="86e2a-205">Mit den folgenden Befehlen werden Prozesse mit Namen, die das folgende Muster aufweisen: "c_lc.exe", wobei der Unterstrich ein beliebiges Zeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-205">The following commands get processes that have names that have the following pattern, "c_lc.exe" where the underscore character represents any one character.</span></span> <span data-ttu-id="86e2a-206">Dieses Muster entspricht einem beliebigen Namen aus calc.exe durch czlc.exe oder c9lc.exe, stimmt jedoch nicht mit den Namen überein, bei denen das "c" und "l" durch mehr als ein Zeichen voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="86e2a-206">This pattern matches any name from calc.exe through czlc.exe, or c9lc.exe, but does not match names in which the "c" and "l" are separated by more than one character.</span></span>

```powershell
$query = "Select * from Win32_Process where Name LIKE 'c_lc.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```

```output
Name                                 ProcessID
----                                 ---------
calc.exe                                  4424
```

#### <a name="example-6-exact-match"></a><span data-ttu-id="86e2a-207">Beispiel 6: exakte Entsprechung</span><span class="sxs-lookup"><span data-stu-id="86e2a-207">EXAMPLE 6: Exact match</span></span>

<span data-ttu-id="86e2a-208">Mit den folgenden Befehlen werden Prozesse mit dem Namen WLIDSVC.exe erhalten.</span><span class="sxs-lookup"><span data-stu-id="86e2a-208">The following commands get processes named WLIDSVC.exe.</span></span> <span data-ttu-id="86e2a-209">Obwohl die Abfrage das LIKE-Schlüsselwort verwendet, erfordert Sie eine exakte Entsprechung, da der Wert keine Platzhalter Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="86e2a-209">Even though the query uses the Like keyword, it requires an exact match, because the value does not include any wildcard characters.</span></span>

```powershell
$query = "Select * from win32_Process where name LIKE 'WLIDSVC.exe'"
Get-WmiObject -Query $query | Select-Object -Property Name, ProcessID
```powershell

```output
Name                                 ProcessID
----                                 ---------
WLIDSVC.exe                                84
```

## <a name="using-the-or-operator"></a><span data-ttu-id="86e2a-210">Verwenden des OR-Operators</span><span class="sxs-lookup"><span data-stu-id="86e2a-210">USING THE OR OPERATOR</span></span>

<span data-ttu-id="86e2a-211">Verwenden Sie das Schlüsselwort oder, um mehrere unabhängige Bedingungen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="86e2a-211">To specify multiple independent conditions, use the Or keyword.</span></span> <span data-ttu-id="86e2a-212">Das-oder-Schlüsselwort wird in der WHERE-Klausel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-212">The Or keyword appears in the Where clause.</span></span> <span data-ttu-id="86e2a-213">Sie führt eine inklusive OR-Operation für zwei (oder mehr) Bedingungen aus und gibt die Elemente zurück, die eine der Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-213">It performs an inclusive OR operation on two (or more) conditions and returns items that meet any of the conditions.</span></span>

<span data-ttu-id="86e2a-214">Der or-Operator weist das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="86e2a-214">The Or operator has the following format:</span></span>

```
Where <property> <operator> <value> or <property> <operator> <value> ...
```

<span data-ttu-id="86e2a-215">Beispielsweise werden mit den folgenden Befehlen alle Instanzen der WMI-Klasse Win32_Process, aber nur zurückgegeben, wenn der Prozess Name winword.exe oder excel.exe ist.</span><span class="sxs-lookup"><span data-stu-id="86e2a-215">For example, the following commands get all instances of the Win32_Process WMI class but returns them only if the process name is winword.exe or excel.exe.</span></span>

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe'"
Get-WmiObject -Query $q
```

<span data-ttu-id="86e2a-216">Die-oder-Anweisung kann mit mehr als zwei Bedingungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-216">The Or statement can be used with more than two conditions.</span></span> <span data-ttu-id="86e2a-217">In der folgenden Abfrage wird die-oder-Anweisung Winword.exe, Excel.exe oder Powershell.exe abgerufen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-217">In the following query, the Or statement gets Winword.exe, Excel.exe, or Powershell.exe.</span></span>

```powershell
$q = "Select * from Win32_Process where Name='winword.exe'" +
  " or Name='excel.exe' or Name='powershell.exe'"
```

## <a name="using-the-and-operator"></a><span data-ttu-id="86e2a-218">Verwenden des and-Operators</span><span class="sxs-lookup"><span data-stu-id="86e2a-218">USING THE AND OPERATOR</span></span>

<span data-ttu-id="86e2a-219">Wenn Sie mehrere verwandte Bedingungen angeben möchten, verwenden Sie das Schlüsselwort und.</span><span class="sxs-lookup"><span data-stu-id="86e2a-219">To specify multiple related conditions, use the And keyword.</span></span> <span data-ttu-id="86e2a-220">Das Schlüsselwort und wird in der WHERE-Klausel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-220">The And keyword appears in the Where clause.</span></span> <span data-ttu-id="86e2a-221">Sie gibt Elemente zurück, die alle Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-221">It returns items that meet all of the conditions.</span></span>

<span data-ttu-id="86e2a-222">Der and-Operator weist das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="86e2a-222">The And operator has the following format:</span></span>

```
Where <property> <operator> <value> and <property> <operator> <value> ...
```

<span data-ttu-id="86e2a-223">Mit den folgenden Befehlen werden z. b. Prozesse mit dem Namen "Winword.exe" und der Prozess-ID 6512 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-223">For example, the following commands get processes that have a name of "Winword.exe" and the process ID of 6512.</span></span>

<span data-ttu-id="86e2a-224">Beachten Sie, dass die Befehle das Get-CimInstance-Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-224">Note that the commands use the Get-CimInstance cmdlet.</span></span>

```powershell
$q = "Select * from Win32_Process where Name = 'winword.exe' " +
  "and ProcessID =6512"
Get-CimInstance -Query $q
```

```output
ProcessId   Name             HandleCount      WorkingSetSize   VirtualSize
---------   ----             -----------      --------------   -----------
# 6512      WINWORD.EXE      768              117170176        633028608
```

<span data-ttu-id="86e2a-225">Alle Operatoren, einschließlich der Like-Operatoren, sind mit den Operatoren, und gültig.</span><span class="sxs-lookup"><span data-stu-id="86e2a-225">All operators, including the Like operators are valid with the Or and And operators.</span></span> <span data-ttu-id="86e2a-226">Außerdem können Sie die Operatoren oder und und in einer einzelnen Abfrage mit Klammern kombinieren, die Windows PowerShell mitteilen, welche Klauseln zuerst verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-226">And, you can combine the Or and And operators in a single query with parentheses that tell Windows PowerShell which clauses to process first.</span></span>

<span data-ttu-id="86e2a-227">Dieser Befehl verwendet das Windows PowerShell-Fortsetzungs Zeichen ('), dividiert den Befehl in zwei Zeilen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-227">This command uses the Windows PowerShell continuation character (\`) divide the command into two lines.</span></span>

```powershell
$q = "Select * from Win32_Process `
where (Name = 'winword.exe' or Name = 'excel.exe') and HandleCount > 700"
Get-CimInstance -Query $q
```

```output
ProcessId    Name             HandleCount      WorkingSetSize   VirtualSize
---------    ----             -----------      --------------   -----------
     6512    WINWORD.EXE      797              117268480        634425344
     9610    EXCEL.EXE        727               38858752        323227648
```

## <a name="searching-for-null-values"></a><span data-ttu-id="86e2a-228">Suchen nach NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="86e2a-228">SEARCHING FOR NULL VALUES</span></span>

<span data-ttu-id="86e2a-229">Das Suchen nach NULL-Werten in WMI ist eine Herausforderung, da dies zu unvorhersehbaren Ergebnissen führen kann.</span><span class="sxs-lookup"><span data-stu-id="86e2a-229">Searching for null values in WMI is challenging, because it can lead to unpredictable results.</span></span> <span data-ttu-id="86e2a-230">NULL ist nicht 0 (null) und entspricht nicht einer leeren Zeichenfolge oder einer leeren Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="86e2a-230">Null is not zero and it is not equivalent or to an empty string.</span></span> <span data-ttu-id="86e2a-231">Einige WMI-Klasseneigenschaften werden initialisiert, andere hingegen nicht. eine Suche nach NULL funktioniert daher möglicherweise nicht für alle Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="86e2a-231">Some WMI class properties are initialized and others are not, so a search for null might not work for all properties.</span></span>

<span data-ttu-id="86e2a-232">Um nach NULL-Werten zu suchen, verwenden Sie den is-Operator mit dem Wert "Null".</span><span class="sxs-lookup"><span data-stu-id="86e2a-232">To search for null values, use the Is operator with a value of "null".</span></span>

<span data-ttu-id="86e2a-233">Mit den folgenden Befehlen werden z. b. Prozesse mit einem NULL-Wert für die intalldate-Eigenschaft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-233">For example, the following commands get processes that have a null value for the IntallDate property.</span></span> <span data-ttu-id="86e2a-234">Die Befehle geben viele Prozesse zurück.</span><span class="sxs-lookup"><span data-stu-id="86e2a-234">The commands return many processes.</span></span>

```powershell
$q = "Select * from Win32_Process where InstallDate is null"
Get-WmiObject -Query $q
```

<span data-ttu-id="86e2a-235">Im Gegensatz dazu ruft der folgende Befehl Benutzerkonten ab, die einen NULL-Wert für die Description-Eigenschaft aufweisen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-235">In contrast, the following command, gets user accounts that have a null value for the Description property.</span></span> <span data-ttu-id="86e2a-236">Dieser Befehl gibt keine Benutzerkonten zurück, obwohl die meisten Benutzerkonten über keinen Wert für die Description-Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-236">This command does not return any user accounts, even though most user accounts do not have any value for the Description property.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Description is null"
Get-WmiObject -Query $q
```

<span data-ttu-id="86e2a-237">Um die Benutzerkonten zu suchen, die keinen Wert für die Description-Eigenschaft aufweisen, verwenden Sie den Gleichheits Operator, um eine leere Zeichenfolge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="86e2a-237">To find the user accounts that have no value for the Description property, use the equality operator to get an empty string.</span></span> <span data-ttu-id="86e2a-238">Wenn Sie die leere Zeichenfolge darstellen möchten, verwenden Sie zwei aufeinanderfolgende einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="86e2a-238">To represent the empty string, use two consecutive single quotation marks.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Description = '' "
```

## <a name="using-true-or-false"></a><span data-ttu-id="86e2a-239">Verwenden von true oder false</span><span class="sxs-lookup"><span data-stu-id="86e2a-239">USING TRUE OR FALSE</span></span>

<span data-ttu-id="86e2a-240">Verwenden Sie "true" und "false", um boolesche Werte in den Eigenschaften von WMI-Objekten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="86e2a-240">To get Boolean values in the properties of WMI objects, use True and False.</span></span>
<span data-ttu-id="86e2a-241">Dabei wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="86e2a-241">They are not case sensitive.</span></span>

<span data-ttu-id="86e2a-242">Die folgende WQL-Abfrage gibt nur lokale Benutzerkonten von einem in die Domäne eingebundener Computer zurück.</span><span class="sxs-lookup"><span data-stu-id="86e2a-242">The following WQL query returns only local user accounts from a domain joined computer.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = True"
Get-CimInstance -Query $q
```

<span data-ttu-id="86e2a-243">Wenn Sie Domänen Konten suchen möchten, verwenden Sie den Wert false, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-243">To find domain accounts, use a value of False, as shown in the following example.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where LocalAccount = False"
Get-CimInstance -Query $q
```

## <a name="using-the-escape-character"></a><span data-ttu-id="86e2a-244">Verwenden des Escapezeichens</span><span class="sxs-lookup"><span data-stu-id="86e2a-244">USING THE ESCAPE CHARACTER</span></span>

<span data-ttu-id="86e2a-245">WQL verwendet den umgekehrten Schrägstrich ( \) als Escapezeichen).</span><span class="sxs-lookup"><span data-stu-id="86e2a-245">WQL uses the backslash (\) as its escape character.</span></span> <span data-ttu-id="86e2a-246">Dies unterscheidet sich von Windows PowerShell, bei dem das Graviszeichen-Zeichen (') verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86e2a-246">This is different from Windows PowerShell, which uses the backtick character (\`).</span></span>

<span data-ttu-id="86e2a-247">Anführungszeichen und die Zeichen, die für Anführungszeichen verwendet werden, müssen häufig mit Escapezeichen versehen werden, damit Sie nicht falsch interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-247">Quotation marks, and the characters used for quotation marks, often need to be escaped so that they are not misinterpreted.</span></span>

<span data-ttu-id="86e2a-248">Um einen Benutzer zu finden, dessen Name ein einzelnes Anführungszeichen enthält, verwenden Sie einen umgekehrten Schrägstrich, um das einfache Anführungszeichen mit Escapezeichen zu versehen, wie im folgenden Befehl gezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-248">To find a user whose name includes a single quotation mark, use a backslash to escape the single quotation mark, as shown in the following command.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Name = 'Tim O\'Brian'"
Get-CimInstance -Query $q
```

```output
Name             Caption          AccountType      SID              Domain
----             -------          -----------      ---              ------
Tim O'Brian      FABRIKAM\TimO    512              S-1-5-21-1457... FABRIKAM
```

<span data-ttu-id="86e2a-249">In einigen Fällen muss der umgekehrte Schrägstrich ebenfalls mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="86e2a-249">In some case, the backslash also needs to be escaped.</span></span> <span data-ttu-id="86e2a-250">Beispielsweise generieren die folgenden Befehle aufgrund des umgekehrten Schrägstrichs im Beschriftungs Wert einen ungültigen Abfrage Fehler.</span><span class="sxs-lookup"><span data-stu-id="86e2a-250">For example, the following commands generate an Invalid Query error due to the backslash in the Caption value.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\TimO'"
Get-CimInstance -Query $q
```

```output
Get-CimInstance : Invalid query
At line:1 char:1
+ Get-CimInstance -Query $q
+ ~~~~~~~~~~~
  + CategoryInfo          : InvalidArgument: (:) [Get-CimInstance], CimExcep
  + FullyQualifiedErrorId : HRESULT 0x80041017,Microsoft.Management.Infrastr
```

<span data-ttu-id="86e2a-251">Um den umgekehrten Schrägstrich mit Escapezeichen zu versehen, verwenden Sie einen zweiten umgekehrten Schrägstrich, wie im folgenden Befehl gezeigt.</span><span class="sxs-lookup"><span data-stu-id="86e2a-251">To escape the backslash, use a second backslash character, as shown in the following command.</span></span>

```powershell
$q = "Select * from Win32_UserAccount where Caption = 'Fabrikam\\TimO'"
Get-CimInstance -Query $q
```

## <a name="see-also"></a><span data-ttu-id="86e2a-252">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="86e2a-252">SEE ALSO</span></span>

[<span data-ttu-id="86e2a-253">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="86e2a-253">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="86e2a-254">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="86e2a-254">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="86e2a-255">about_WMI</span><span class="sxs-lookup"><span data-stu-id="86e2a-255">about_WMI</span></span>](about_WMI.md)

[<span data-ttu-id="86e2a-256">about_WMI_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="86e2a-256">about_WMI_Cmdlets</span></span>](about_WMI_Cmdlets.md)
