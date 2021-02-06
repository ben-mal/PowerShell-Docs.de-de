---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/21/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimInstance
ms.openlocfilehash: 0e4a148601f3ef2212f9c97128c54258906106d7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596767"
---
# <span data-ttu-id="36b35-102">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="36b35-102">Get-CimInstance</span></span>

## <span data-ttu-id="36b35-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="36b35-103">SYNOPSIS</span></span>
<span data-ttu-id="36b35-104">Ruft die CIM-Instanzen einer Klasse von einem CIM-Server ab.</span><span class="sxs-lookup"><span data-stu-id="36b35-104">Gets the CIM instances of a class from a CIM server.</span></span>

## <span data-ttu-id="36b35-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="36b35-105">SYNTAX</span></span>

### <span data-ttu-id="36b35-106">Classnamecomputerset (Standard)</span><span class="sxs-lookup"><span data-stu-id="36b35-106">ClassNameComputerSet (Default)</span></span>

```
Get-CimInstance [-ClassName] <String> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="36b35-107">Resourceurisessionset</span><span class="sxs-lookup"><span data-stu-id="36b35-107">ResourceUriSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> -ResourceUri <Uri> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="36b35-108">Querysessionset</span><span class="sxs-lookup"><span data-stu-id="36b35-108">QuerySessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

### <span data-ttu-id="36b35-109">Classnamesessionset</span><span class="sxs-lookup"><span data-stu-id="36b35-109">ClassNameSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ClassName] <String> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="36b35-110">Ciminstancesessionset</span><span class="sxs-lookup"><span data-stu-id="36b35-110">CimInstanceSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="36b35-111">Ciminstancecomputerset</span><span class="sxs-lookup"><span data-stu-id="36b35-111">CimInstanceComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="36b35-112">Resourceuricomputerset</span><span class="sxs-lookup"><span data-stu-id="36b35-112">ResourceUriComputerSet</span></span>

```
Get-CimInstance -ResourceUri <Uri> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="36b35-113">Querycomputerset</span><span class="sxs-lookup"><span data-stu-id="36b35-113">QueryComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

## <span data-ttu-id="36b35-114">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="36b35-114">DESCRIPTION</span></span>

<span data-ttu-id="36b35-115">Mit dem- `Get-CimInstance` Cmdlet werden die CIM-Instanzen einer Klasse von einem CIM-Server abgerufen.</span><span class="sxs-lookup"><span data-stu-id="36b35-115">The `Get-CimInstance` cmdlet gets the CIM instances of a class from a CIM server.</span></span> <span data-ttu-id="36b35-116">Sie können entweder den Klassennamen oder eine Abfrage für dieses Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="36b35-116">You can specify either the class name or a query for this cmdlet.</span></span> <span data-ttu-id="36b35-117">Dieses Cmdlet gibt mindestens ein CIM-Instanzobjekt zurück, das eine Momentaufnahme der CIM-Instanzen darstellt, die auf dem CIM-Server vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="36b35-117">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances present on the CIM server.</span></span>

<span data-ttu-id="36b35-118">Wenn der **Inputobject** -Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="36b35-118">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="36b35-119">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="36b35-119">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="36b35-120">Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="36b35-120">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="36b35-121">Wenn der **Inputobject** -Parameter angegeben wird, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="36b35-121">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="36b35-122">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, verwendet dieses Cmdlet die CIM-Sitzung oder den Computernamen aus dem Eingabe Objekt.</span><span class="sxs-lookup"><span data-stu-id="36b35-122">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="36b35-123">Wenn der **Computername** -Parameter oder der **cimsession** -Parameter angegeben wird, verwendet dieses Cmdlet entweder den Wert des cimsession-Parameter Werts oder den Wert des **Computername** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="36b35-123">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the CimSession parameter value or **ComputerName** parameter value.</span></span>

## <span data-ttu-id="36b35-124">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="36b35-124">EXAMPLES</span></span>

### <span data-ttu-id="36b35-125">Beispiel 1: Holen Sie sich die CIM-Instanzen einer bestimmten Klasse.</span><span class="sxs-lookup"><span data-stu-id="36b35-125">Example 1: Get the CIM instances of a specified class</span></span>

<span data-ttu-id="36b35-126">In diesem Beispiel werden die CIM-Instanzen einer Klasse mit dem Namen **Win32_Process** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="36b35-126">This example retrieves the CIM instances of a class named **Win32_Process**.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process
```

### <span data-ttu-id="36b35-127">Beispiel 2: erhalten einer Liste von Namespaces von einem WMI-Server</span><span class="sxs-lookup"><span data-stu-id="36b35-127">Example 2: Get a list of namespaces from a WMI server</span></span>

<span data-ttu-id="36b35-128">In diesem Beispiel wird eine Liste von Namespaces **unter dem Stamm** Namespace auf einem WMI-Server abgerufen.</span><span class="sxs-lookup"><span data-stu-id="36b35-128">This example retrieves a list of namespaces under the **Root** namespace on a WMI server.</span></span>

```powershell
Get-CimInstance -Namespace root -ClassName __Namespace
```

### <span data-ttu-id="36b35-129">Beispiel 3: Abfragen von Instanzen einer Klasse, die mithilfe einer Abfrage gefiltert werden</span><span class="sxs-lookup"><span data-stu-id="36b35-129">Example 3: Get instances of a class filtered by using a query</span></span>

<span data-ttu-id="36b35-130">In diesem Beispiel werden alle CIM-Instanzen abgerufen, die mit dem Buchstaben " **P** " einer Klasse mit dem Namen " **Win32_Process** " unter Verwendung der von einem **Abfrage** Parameter angegebenen Abfrage beginnen.</span><span class="sxs-lookup"><span data-stu-id="36b35-130">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the query specified by a **Query** parameter.</span></span>

```powershell
Get-CimInstance -Query "SELECT * from Win32_Process WHERE name LIKE 'P%'"
```

### <span data-ttu-id="36b35-131">Beispiel 4: Get-Instanzen einer Klasse, gefiltert mithilfe eines Klassen namens und eines Filter Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="36b35-131">Example 4: Get instances of a class filtered by using a class name and a filter expression</span></span>

<span data-ttu-id="36b35-132">In diesem Beispiel werden alle CIM-Instanzen abgerufen, die mit dem Buchstaben " **P** " einer Klasse namens " **Win32_Process** " mit dem Filter-Parameter beginnen.</span><span class="sxs-lookup"><span data-stu-id="36b35-132">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the Filter parameter.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process -Filter "Name like 'P%'"
```

### <span data-ttu-id="36b35-133">Beispiel 5: Holen Sie sich die CIM-Instanzen, für die nur Schlüsseleigenschaften ausgefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="36b35-133">Example 5: Get the CIM instances with only key properties filled in</span></span>

<span data-ttu-id="36b35-134">In diesem Beispiel wird eine neue CIM-Instanz im Arbeitsspeicher für eine Klasse mit dem Namen **Win32_Process** mit der Schlüsseleigenschaft erstellt `@{ "Handle"=0 }` und in einer Variablen mit dem Namen gespeichert `$x` .</span><span class="sxs-lookup"><span data-stu-id="36b35-134">This example creates a new CIM instance in memory for a class named **Win32_Process** with the key property `@{ "Handle"=0 }` and stores it in a variable named `$x`.</span></span> <span data-ttu-id="36b35-135">Die Variable wird als CIM-Instanz an das `Get-CimInstance` Cmdlet übergeben, um eine bestimmte Instanz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="36b35-135">The variable is passed as a CIM instance to the `Get-CimInstance` cmdlet to get a particular instance.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Process -Namespace root\cimv2 -Property @{ "Handle"=0 } -Key Handle -ClientOnly
Get-CimInstance -CimInstance $x
```

### <span data-ttu-id="36b35-136">Beispiel 6: Abrufen von CIM-Instanzen und wieder verwenden</span><span class="sxs-lookup"><span data-stu-id="36b35-136">Example 6: Retrieve CIM instances and reuse them</span></span>

<span data-ttu-id="36b35-137">In diesem Beispiel werden die CIM-Instanzen einer Klasse mit dem Namen **Win32_Process** abgerufen und in den Variablen `$x` und gespeichert `$y` .</span><span class="sxs-lookup"><span data-stu-id="36b35-137">This example gets the CIM instances of a class named **Win32_Process** and stores them in the variables `$x` and `$y`.</span></span> <span data-ttu-id="36b35-138">Die Variable `$x` wird dann in einer Tabelle formatiert, die nur die Eigenschaften **Name** und **kernelmodetime** enthält, wobei die Tabelle auf **AutoSize** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="36b35-138">The variable `$x` is then formatted in a table containing only the **Name** and **KernelModeTime** properties, the table set to **AutoSize**.</span></span>

```powershell
$x,$y = Get-CimInstance -ClassName Win32_Process
$x | Format-Table -Property Name,KernelModeTime -AutoSize
```

```Output
Name                 KernelModeTime
----                 --------------
System Idle Process 157238797968750
```

### <span data-ttu-id="36b35-139">Beispiel 7: erhalten von CIM-Instanzen vom Remote Computer</span><span class="sxs-lookup"><span data-stu-id="36b35-139">Example 7: Get CIM instances from remote computer</span></span>

<span data-ttu-id="36b35-140">In diesem Beispiel werden die CIM-Instanzen einer Klasse mit dem Namen **Win32_ComputerSystem** von den Remote Computern namens **Server01** und **Server02** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="36b35-140">This example retrieves the CIM instances of a class named **Win32_ComputerSystem** from the remote computers named **Server01** and **Server02**.</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName Server01,Server02
```

### <span data-ttu-id="36b35-141">Beispiel 8: erhalten von nur die Schlüsseleigenschaften anstelle aller Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="36b35-141">Example 8: Getting only the key properties, instead of all properties</span></span>

<span data-ttu-id="36b35-142">In diesem Beispiel werden nur die Schlüsseleigenschaften abgerufen, wodurch die Größe des Objekts und der Netzwerk Datenverkehr reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="36b35-142">This example retrieves only the key properties, which reduces the size of the object and network traffic.</span></span>

```powershell
$x = Get-CimInstance -Class Win32_Process -KeyOnly
$x | Invoke-CimMethod -MethodName GetOwner
```

### <span data-ttu-id="36b35-143">Beispiel 9: nur eine Teilmenge der Eigenschaften anstelle aller Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="36b35-143">Example 9: Getting only a subset of properties, instead of all properties</span></span>

<span data-ttu-id="36b35-144">In diesem Beispiel wird nur eine Teilmenge der Eigenschaften abgerufen, wodurch die Größe des Objekts und der Netzwerk Datenverkehr reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="36b35-144">This example retrieves only a subset of properties, which reduces the size of the object and network traffic.</span></span>

```powershell
Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x = Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x | Invoke-CimMethod -MethodName GetOwner
```

<span data-ttu-id="36b35-145">Die-Instanz, die mit dem **Property** -Parameter abgerufen wird, kann verwendet werden, um andere CIM-Vorgänge auszuführen, z.b. `Set-CimInstance` oder `Invoke-CimMethod` .</span><span class="sxs-lookup"><span data-stu-id="36b35-145">The instance retrieved with the **Property** parameter can be used to perform other CIM operations, for example `Set-CimInstance` or `Invoke-CimMethod`.</span></span>

### <span data-ttu-id="36b35-146">Beispiel 10: erhalten der CIM-Instanz mithilfe der CIM-Sitzung</span><span class="sxs-lookup"><span data-stu-id="36b35-146">Example 10: Get the CIM instance using CIM session</span></span>

<span data-ttu-id="36b35-147">In diesem Beispiel wird eine CIM-Sitzung auf den Computern namens **Server01** und **Server02** mithilfe des `New-CimSession` Cmdlets erstellt und die Sitzungsinformationen in einer Variablen mit dem Namen gespeichert `$s` .</span><span class="sxs-lookup"><span data-stu-id="36b35-147">This example creates a CIM session on the computers named **Server01** and **Server02** using the `New-CimSession` cmdlet and stores the session information in a variable named `$s`.</span></span> <span data-ttu-id="36b35-148">Der Inhalt der Variablen wird dann `Get-CimInstance` mithilfe des **cimsession** -Parameters an übergeben, um die CIM-Instanzen der Klasse mit dem Namen " **Win32_ComputerSystem**" zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="36b35-148">The contents of the variable are then passed to `Get-CimInstance` by using the **CimSession** parameter, to get the CIM instances of the class named **Win32_ComputerSystem**.</span></span>

```powershell
$s = New-CimSession -ComputerName Server01,Server02
Get-CimInstance -ClassName Win32_ComputerSystem -CimSession $s
```

## <span data-ttu-id="36b35-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="36b35-149">PARAMETERS</span></span>

### <span data-ttu-id="36b35-150">-CimSession</span><span class="sxs-lookup"><span data-stu-id="36b35-150">-CimSession</span></span>

<span data-ttu-id="36b35-151">Gibt die CIM-Sitzung an, die für dieses Cmdlet verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="36b35-151">Specifies the CIM session to use for this cmdlet.</span></span> <span data-ttu-id="36b35-152">Geben Sie eine Variable ein, die die CIM-Sitzung oder einen Befehl enthält, der die CIM-Sitzung erstellt `New-CimSession` oder `Get-CimSession` abruft, z. b. die Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="36b35-152">Enter a variable that contains the CIM session or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="36b35-153">Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="36b35-153">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, CimInstanceSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-154">-ClassName</span><span class="sxs-lookup"><span data-stu-id="36b35-154">-ClassName</span></span>

<span data-ttu-id="36b35-155">Gibt den Namen der CIM-Klasse an, für die die CIM-Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="36b35-155">Specifies the name of the CIM class for which to retrieve the CIM instances.</span></span> <span data-ttu-id="36b35-156">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="36b35-156">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-157">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="36b35-157">-ComputerName</span></span>

<span data-ttu-id="36b35-158">Gibt den Computer an, auf dem Sie den CIM-Vorgang ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="36b35-158">Specifies computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="36b35-159">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN), einen NetBIOS-Namen oder eine IP-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="36b35-159">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="36b35-160">Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.</span><span class="sxs-lookup"><span data-stu-id="36b35-160">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="36b35-161">Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="36b35-161">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="36b35-162">Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, stellen Sie eine Verbindung mithilfe einer CIM-Sitzung her, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="36b35-162">If multiple operations are being performed on the same computer, connect using a CIM session for better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, CimInstanceComputerSet, ResourceUriComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-163">-Filter</span><span class="sxs-lookup"><span data-stu-id="36b35-163">-Filter</span></span>

<span data-ttu-id="36b35-164">Gibt eine WHERE-Klausel an, die als Filter verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="36b35-164">Specifies a where clause to use as a filter.</span></span> <span data-ttu-id="36b35-165">Geben Sie die-Klausel entweder in der **WQL** -oder der **CQL** -Abfragesprache an.</span><span class="sxs-lookup"><span data-stu-id="36b35-165">Specify the clause in either the **WQL** or the **CQL** query language.</span></span> <span data-ttu-id="36b35-166">Fügen Sie das- `WHERE` Schlüsselwort nicht in den Wert des-Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="36b35-166">Do not include the `WHERE` keyword in the value of the parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-167">-InputObject</span><span class="sxs-lookup"><span data-stu-id="36b35-167">-InputObject</span></span>

<span data-ttu-id="36b35-168">Gibt ein CIM-Instanzobjekt an, das als Eingabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="36b35-168">Specifies a CIM instance object to use as input.</span></span>

<span data-ttu-id="36b35-169">Wenn Sie bereits mit einem CIM-Instanzobjekt arbeiten, können Sie diesen Parameter verwenden, um das CIM-Instanzobjekt zu übergeben, um die neueste Momentaufnahme vom CIM-Server zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="36b35-169">If you are already working with a CIM instance object, you can use this parameter to pass the CIM instance object in order to get the latest snapshot from the CIM server.</span></span> <span data-ttu-id="36b35-170">Wenn Sie ein CIM-Instanzobjekt als Eingabe übergeben, wird `Get-CimInstance` das Objekt vom Server mit einem Get-CIM-Vorgang anstelle eines auflisten-oder Abfrage Vorgangs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="36b35-170">When you pass a CIM instance object as an input, `Get-CimInstance` returns the object from server using a get CIM operation, instead of an enumerate or query operation.</span></span> <span data-ttu-id="36b35-171">Die Verwendung eines Get-CIM-Vorgangs ist effizienter als das Abrufen aller Instanzen und das anschließende filtern.</span><span class="sxs-lookup"><span data-stu-id="36b35-171">Using a get CIM operation is more efficient than retrieving all instances and then filtering them.</span></span>

<span data-ttu-id="36b35-172">Wenn die CIM-Klasse den Get-Vorgang nicht implementiert, gibt die Angabe des **Inputobject** -Parameters einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="36b35-172">If the CIM class does not implement the get operation, then specifying the **InputObject** parameter returns an error.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceSessionSet, CimInstanceComputerSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-173">-Keyonly</span><span class="sxs-lookup"><span data-stu-id="36b35-173">-KeyOnly</span></span>

<span data-ttu-id="36b35-174">Gibt an, dass nur Objekte mit aufgefüllten Schlüsseleigenschaften zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="36b35-174">Indicates that only objects with key properties populated are returned.</span></span> <span data-ttu-id="36b35-175">Durch die Angabe des **keyonly** -Parameters wird die Menge der über das Netzwerk übertragenen Daten reduziert.</span><span class="sxs-lookup"><span data-stu-id="36b35-175">Specifying the **KeyOnly** parameter reduces the amount of data transferred over the network.</span></span>

<span data-ttu-id="36b35-176">Verwenden Sie den **keyonly** -Parameter, um nur einen kleinen Teil des-Objekts zurückzugeben, der für andere Vorgänge, wie z `Set-CimInstance` . b. die-oder-Cmdlets, verwendet werden kann `Get-CimAssociatedInstance` .</span><span class="sxs-lookup"><span data-stu-id="36b35-176">Use the **KeyOnly** parameter to return only a small portion of the object, which can be used for other operations, such as the `Set-CimInstance` or `Get-CimAssociatedInstance` cmdlets.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-177">-Namespace</span><span class="sxs-lookup"><span data-stu-id="36b35-177">-Namespace</span></span>

<span data-ttu-id="36b35-178">Gibt den Namespace der CIM-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="36b35-178">Specifies the namespace of CIM class.</span></span>

<span data-ttu-id="36b35-179">Der Standard Namespace ist **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="36b35-179">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="36b35-180">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="36b35-180">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-181">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="36b35-181">-OperationTimeoutSec</span></span>

<span data-ttu-id="36b35-182">Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet.</span><span class="sxs-lookup"><span data-stu-id="36b35-182">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="36b35-183">Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="36b35-183">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="36b35-184">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="36b35-184">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-185">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="36b35-185">-Property</span></span>

<span data-ttu-id="36b35-186">Gibt eine Gruppe von Instanzeigenschaften an, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="36b35-186">Specifies a set of instance properties to retrieve.</span></span> <span data-ttu-id="36b35-187">Verwenden Sie diesen Parameter, wenn Sie die Größe des Objekts, das entweder im Arbeitsspeicher oder über das Netzwerk zurückgegeben wird, verringern müssen.</span><span class="sxs-lookup"><span data-stu-id="36b35-187">Use this parameter when you need to reduce the size of the object returned, either in memory or over the network.</span></span> <span data-ttu-id="36b35-188">Das zurückgegebene Objekt enthält auch die Schlüsseleigenschaften, auch wenn Sie Sie nicht mithilfe des **Property** -Parameters aufgelistet haben.</span><span class="sxs-lookup"><span data-stu-id="36b35-188">The object returned also contains the key properties even if you have not listed them using the **Property** parameter.</span></span> <span data-ttu-id="36b35-189">Es sind andere Eigenschaften der-Klasse vorhanden, die jedoch nicht aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="36b35-189">Other properties of the class are present but they are not populated.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases: SelectProperties

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-190">-Query</span><span class="sxs-lookup"><span data-stu-id="36b35-190">-Query</span></span>

<span data-ttu-id="36b35-191">Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="36b35-191">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="36b35-192">Wenn der angegebene Wert doppelte Anführungszeichen `"` , einfache Anführungszeichen `'` oder einen umgekehrten Schrägstrich enthält `\` , müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="36b35-192">If the value specified contains double quotes `"`, single quotes `'`, or a backslash `\`, you must escape those characters by prefixing them with the backslash character.</span></span> <span data-ttu-id="36b35-193">Wenn für den angegebenen Wert der WQL **like** -Operator verwendet wird, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern einschließen `[]` : Prozent `%` , unterstrich `_` oder öffnende eckige Klammer `[` .</span><span class="sxs-lookup"><span data-stu-id="36b35-193">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets `[]`: percent `%`, underscore `_`, or opening square bracket `[`.</span></span>

<span data-ttu-id="36b35-194">Es ist nicht möglich, eine Metadatenabfrage zum Abrufen einer Liste von Klassen oder einer Ereignis Abfrage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="36b35-194">You cannot use a metadata query to retrieve a list of classes or an event query.</span></span> <span data-ttu-id="36b35-195">Verwenden Sie das-Cmdlet, um eine Liste der Klassen abzurufen `Get-CimClass` .</span><span class="sxs-lookup"><span data-stu-id="36b35-195">To retrieve a list of classes, use the `Get-CimClass` cmdlet.</span></span> <span data-ttu-id="36b35-196">Verwenden Sie zum Abrufen einer Ereignis Abfrage das- `Register-CimIndicationEvent` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="36b35-196">To retrieve an event query, use the `Register-CimIndicationEvent` cmdlet.</span></span>

<span data-ttu-id="36b35-197">Sie können den Abfrage Dialekt mithilfe des **querydialekt** -Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="36b35-197">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-198">-Querydialekt</span><span class="sxs-lookup"><span data-stu-id="36b35-198">-QueryDialect</span></span>

<span data-ttu-id="36b35-199">Gibt die Abfragesprache an, die für den Abfrage Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="36b35-199">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="36b35-200">Die zulässigen Werte für diesen Parameter sind: **WQL** oder **CQL**.</span><span class="sxs-lookup"><span data-stu-id="36b35-200">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="36b35-201">Der Standardwert ist **WQL**.</span><span class="sxs-lookup"><span data-stu-id="36b35-201">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QuerySessionSet, ClassNameSessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-202">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="36b35-202">-ResourceUri</span></span>

<span data-ttu-id="36b35-203">Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="36b35-203">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="36b35-204">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="36b35-204">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="36b35-205">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="36b35-205">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="36b35-206">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="36b35-206">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="36b35-207">Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.</span><span class="sxs-lookup"><span data-stu-id="36b35-207">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="36b35-208">**ResourceUri** kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der **Computername** -Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt.</span><span class="sxs-lookup"><span data-stu-id="36b35-208">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="36b35-209">Wenn Sie diesen Parameter ohne Angabe des **Computername** -Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie eine Fehlermeldung, da das DCOM-Protokoll den **resourceUri** -Parameter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36b35-209">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="36b35-210">Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="36b35-210">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-211">-Flach</span><span class="sxs-lookup"><span data-stu-id="36b35-211">-Shallow</span></span>

<span data-ttu-id="36b35-212">Gibt an, dass die Instanzen einer Klasse zurückgegeben werden, ohne die Instanzen von untergeordneten Klassen einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="36b35-212">Indicates that the instances of a class are returned without including the instances of any child classes.</span></span> <span data-ttu-id="36b35-213">Standardmäßig gibt das Cmdlet die Instanzen einer Klasse und ihrer untergeordneten Klassen zurück.</span><span class="sxs-lookup"><span data-stu-id="36b35-213">By default, the cmdlet returns the instances of a class and its child classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="36b35-214">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="36b35-214">CommonParameters</span></span>

<span data-ttu-id="36b35-215">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="36b35-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="36b35-216">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="36b35-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="36b35-217">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="36b35-217">INPUTS</span></span>

### <span data-ttu-id="36b35-218">CIM-Instanz</span><span class="sxs-lookup"><span data-stu-id="36b35-218">CIM Instance</span></span>

<span data-ttu-id="36b35-219">Dieses Cmdlet akzeptiert ein Eingabe Objekt, das mit dem Inputobject-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="36b35-219">This cmdlet accepts an input objects specified with the InputObject parameter.</span></span>

## <span data-ttu-id="36b35-220">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="36b35-220">OUTPUTS</span></span>

### <span data-ttu-id="36b35-221">CIM-Instanz</span><span class="sxs-lookup"><span data-stu-id="36b35-221">CIM Instance</span></span>

<span data-ttu-id="36b35-222">Dieses Cmdlet gibt ein oder mehrere CIM-Instanzobjekte zurück, die eine Momentaufnahme der CIM-Instanzen auf dem CIM-Server darstellen.</span><span class="sxs-lookup"><span data-stu-id="36b35-222">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances on the CIM server.</span></span>

## <span data-ttu-id="36b35-223">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="36b35-223">NOTES</span></span>

## <span data-ttu-id="36b35-224">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="36b35-224">RELATED LINKS</span></span>

[<span data-ttu-id="36b35-225">Format-Table</span><span class="sxs-lookup"><span data-stu-id="36b35-225">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="36b35-226">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="36b35-226">Get-CimAssociatedInstance</span></span>](Get-CimAssociatedInstance.md)

[<span data-ttu-id="36b35-227">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="36b35-227">Get-CimClass</span></span>](Get-CimClass.md)

[<span data-ttu-id="36b35-228">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="36b35-228">Invoke-CimMethod</span></span>](invoke-cimmethod.md)

[<span data-ttu-id="36b35-229">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="36b35-229">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="36b35-230">Register-CimIndicationEvent</span><span class="sxs-lookup"><span data-stu-id="36b35-230">Register-CimIndicationEvent</span></span>](Register-CimIndicationEvent.md)

[<span data-ttu-id="36b35-231">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="36b35-231">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="36b35-232">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="36b35-232">Set-CimInstance</span></span>](Set-CimInstance.md)

