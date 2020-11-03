---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/21/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-ciminstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimInstance
ms.openlocfilehash: 49838449bd2ffe949c4b2f1310c3f68c40867908
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218276"
---
# <span data-ttu-id="8295e-103">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="8295e-103">Get-CimInstance</span></span>

## <span data-ttu-id="8295e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8295e-104">SYNOPSIS</span></span>
<span data-ttu-id="8295e-105">Ruft die CIM-Instanzen einer Klasse von einem CIM-Server ab.</span><span class="sxs-lookup"><span data-stu-id="8295e-105">Gets the CIM instances of a class from a CIM server.</span></span>

## <span data-ttu-id="8295e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8295e-106">SYNTAX</span></span>

### <span data-ttu-id="8295e-107">Classnamecomputerset (Standard)</span><span class="sxs-lookup"><span data-stu-id="8295e-107">ClassNameComputerSet (Default)</span></span>

```
Get-CimInstance [-ClassName] <String> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="8295e-108">Resourceurisessionset</span><span class="sxs-lookup"><span data-stu-id="8295e-108">ResourceUriSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> -ResourceUri <Uri> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="8295e-109">Querysessionset</span><span class="sxs-lookup"><span data-stu-id="8295e-109">QuerySessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

### <span data-ttu-id="8295e-110">Classnamesessionset</span><span class="sxs-lookup"><span data-stu-id="8295e-110">ClassNameSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ClassName] <String> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="8295e-111">Ciminstancesessionset</span><span class="sxs-lookup"><span data-stu-id="8295e-111">CimInstanceSessionSet</span></span>

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="8295e-112">Ciminstancecomputerset</span><span class="sxs-lookup"><span data-stu-id="8295e-112">CimInstanceComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### <span data-ttu-id="8295e-113">Resourceuricomputerset</span><span class="sxs-lookup"><span data-stu-id="8295e-113">ResourceUriComputerSet</span></span>

```
Get-CimInstance -ResourceUri <Uri> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="8295e-114">Querycomputerset</span><span class="sxs-lookup"><span data-stu-id="8295e-114">QueryComputerSet</span></span>

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

## <span data-ttu-id="8295e-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8295e-115">DESCRIPTION</span></span>

<span data-ttu-id="8295e-116">Mit dem- `Get-CimInstance` Cmdlet werden die CIM-Instanzen einer Klasse von einem CIM-Server abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8295e-116">The `Get-CimInstance` cmdlet gets the CIM instances of a class from a CIM server.</span></span> <span data-ttu-id="8295e-117">Sie können entweder den Klassennamen oder eine Abfrage für dieses Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="8295e-117">You can specify either the class name or a query for this cmdlet.</span></span> <span data-ttu-id="8295e-118">Dieses Cmdlet gibt mindestens ein CIM-Instanzobjekt zurück, das eine Momentaufnahme der CIM-Instanzen darstellt, die auf dem CIM-Server vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8295e-118">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances present on the CIM server.</span></span>

<span data-ttu-id="8295e-119">Wenn der **Inputobject** -Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="8295e-119">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="8295e-120">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="8295e-120">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="8295e-121">Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8295e-121">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="8295e-122">Wenn der **Inputobject** -Parameter angegeben wird, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="8295e-122">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="8295e-123">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, verwendet dieses Cmdlet die CIM-Sitzung oder den Computernamen aus dem Eingabe Objekt.</span><span class="sxs-lookup"><span data-stu-id="8295e-123">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="8295e-124">Wenn der **Computername** -Parameter oder der **cimsession** -Parameter angegeben wird, verwendet dieses Cmdlet entweder den Wert des cimsession-Parameter Werts oder den Wert des **Computername** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="8295e-124">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the CimSession parameter value or **ComputerName** parameter value.</span></span>

## <span data-ttu-id="8295e-125">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8295e-125">EXAMPLES</span></span>

### <span data-ttu-id="8295e-126">Beispiel 1: Holen Sie sich die CIM-Instanzen einer bestimmten Klasse.</span><span class="sxs-lookup"><span data-stu-id="8295e-126">Example 1: Get the CIM instances of a specified class</span></span>

<span data-ttu-id="8295e-127">In diesem Beispiel werden die CIM-Instanzen einer Klasse mit dem Namen **Win32_Process** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8295e-127">This example retrieves the CIM instances of a class named **Win32_Process**.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process
```

### <span data-ttu-id="8295e-128">Beispiel 2: erhalten einer Liste von Namespaces von einem WMI-Server</span><span class="sxs-lookup"><span data-stu-id="8295e-128">Example 2: Get a list of namespaces from a WMI server</span></span>

<span data-ttu-id="8295e-129">In diesem Beispiel wird eine Liste von Namespaces **unter dem Stamm** Namespace auf einem WMI-Server abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8295e-129">This example retrieves a list of namespaces under the **Root** namespace on a WMI server.</span></span>

```powershell
Get-CimInstance -Namespace root -ClassName __Namespace
```

### <span data-ttu-id="8295e-130">Beispiel 3: Abfragen von Instanzen einer Klasse, die mithilfe einer Abfrage gefiltert werden</span><span class="sxs-lookup"><span data-stu-id="8295e-130">Example 3: Get instances of a class filtered by using a query</span></span>

<span data-ttu-id="8295e-131">In diesem Beispiel werden alle CIM-Instanzen abgerufen, die mit dem Buchstaben " **P** " einer Klasse mit dem Namen " **Win32_Process** " unter Verwendung der von einem **Abfrage** Parameter angegebenen Abfrage beginnen.</span><span class="sxs-lookup"><span data-stu-id="8295e-131">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the query specified by a **Query** parameter.</span></span>

```powershell
Get-CimInstance -Query "SELECT * from Win32_Process WHERE name LIKE 'P%'"
```

### <span data-ttu-id="8295e-132">Beispiel 4: Get-Instanzen einer Klasse, gefiltert mithilfe eines Klassen namens und eines Filter Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="8295e-132">Example 4: Get instances of a class filtered by using a class name and a filter expression</span></span>

<span data-ttu-id="8295e-133">In diesem Beispiel werden alle CIM-Instanzen abgerufen, die mit dem Buchstaben " **P** " einer Klasse namens " **Win32_Process** " mit dem Filter-Parameter beginnen.</span><span class="sxs-lookup"><span data-stu-id="8295e-133">This example retrieves all the CIM instances that start with the letter **P** of a class named **Win32_Process** using the Filter parameter.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Process -Filter "Name like 'P%'"
```

### <span data-ttu-id="8295e-134">Beispiel 5: Holen Sie sich die CIM-Instanzen, für die nur Schlüsseleigenschaften ausgefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="8295e-134">Example 5: Get the CIM instances with only key properties filled in</span></span>

<span data-ttu-id="8295e-135">In diesem Beispiel wird eine neue CIM-Instanz im Arbeitsspeicher für eine Klasse mit dem Namen **Win32_Process** mit der Schlüsseleigenschaft erstellt `@{ "Handle"=0 }` und in einer Variablen mit dem Namen gespeichert `$x` .</span><span class="sxs-lookup"><span data-stu-id="8295e-135">This example creates a new CIM instance in memory for a class named **Win32_Process** with the key property `@{ "Handle"=0 }` and stores it in a variable named `$x`.</span></span> <span data-ttu-id="8295e-136">Die Variable wird als CIM-Instanz an das `Get-CimInstance` Cmdlet übergeben, um eine bestimmte Instanz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8295e-136">The variable is passed as a CIM instance to the `Get-CimInstance` cmdlet to get a particular instance.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Process -Namespace root\cimv2 -Property @{ "Handle"=0 } -Key Handle -ClientOnly
Get-CimInstance -CimInstance $x
```

### <span data-ttu-id="8295e-137">Beispiel 6: Abrufen von CIM-Instanzen und wieder verwenden</span><span class="sxs-lookup"><span data-stu-id="8295e-137">Example 6: Retrieve CIM instances and reuse them</span></span>

<span data-ttu-id="8295e-138">In diesem Beispiel werden die CIM-Instanzen einer Klasse mit dem Namen **Win32_Process** abgerufen und in den Variablen `$x` und gespeichert `$y` .</span><span class="sxs-lookup"><span data-stu-id="8295e-138">This example gets the CIM instances of a class named **Win32_Process** and stores them in the variables `$x` and `$y`.</span></span> <span data-ttu-id="8295e-139">Die Variable `$x` wird dann in einer Tabelle formatiert, die nur die Eigenschaften **Name** und **kernelmodetime** enthält, wobei die Tabelle auf **AutoSize** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8295e-139">The variable `$x` is then formatted in a table containing only the **Name** and **KernelModeTime** properties, the table set to **AutoSize**.</span></span>

```powershell
$x,$y = Get-CimInstance -ClassName Win32_Process
$x | Format-Table -Property Name,KernelModeTime -AutoSize
```

```Output
Name                 KernelModeTime
----                 --------------
System Idle Process 157238797968750
```

### <span data-ttu-id="8295e-140">Beispiel 7: erhalten von CIM-Instanzen vom Remote Computer</span><span class="sxs-lookup"><span data-stu-id="8295e-140">Example 7: Get CIM instances from remote computer</span></span>

<span data-ttu-id="8295e-141">In diesem Beispiel werden die CIM-Instanzen einer Klasse mit dem Namen **Win32_ComputerSystem** von den Remote Computern namens **Server01** und **Server02** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8295e-141">This example retrieves the CIM instances of a class named **Win32_ComputerSystem** from the remote computers named **Server01** and **Server02**.</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName Server01,Server02
```

### <span data-ttu-id="8295e-142">Beispiel 8: erhalten von nur die Schlüsseleigenschaften anstelle aller Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8295e-142">Example 8: Getting only the key properties, instead of all properties</span></span>

<span data-ttu-id="8295e-143">In diesem Beispiel werden nur die Schlüsseleigenschaften abgerufen, wodurch die Größe des Objekts und der Netzwerk Datenverkehr reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="8295e-143">This example retrieves only the key properties, which reduces the size of the object and network traffic.</span></span>

```powershell
$x = Get-CimInstance -Class Win32_Process -KeyOnly
$x | Invoke-CimMethod -MethodName GetOwner
```

### <span data-ttu-id="8295e-144">Beispiel 9: nur eine Teilmenge der Eigenschaften anstelle aller Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8295e-144">Example 9: Getting only a subset of properties, instead of all properties</span></span>

<span data-ttu-id="8295e-145">In diesem Beispiel wird nur eine Teilmenge der Eigenschaften abgerufen, wodurch die Größe des Objekts und der Netzwerk Datenverkehr reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="8295e-145">This example retrieves only a subset of properties, which reduces the size of the object and network traffic.</span></span>

```powershell
Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x = Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x | Invoke-CimMethod -MethodName GetOwner
```

<span data-ttu-id="8295e-146">Die-Instanz, die mit dem **Property** -Parameter abgerufen wird, kann verwendet werden, um andere CIM-Vorgänge auszuführen, z.b. `Set-CimInstance` oder `Invoke-CimMethod` .</span><span class="sxs-lookup"><span data-stu-id="8295e-146">The instance retrieved with the **Property** parameter can be used to perform other CIM operations, for example `Set-CimInstance` or `Invoke-CimMethod`.</span></span>

### <span data-ttu-id="8295e-147">Beispiel 10: erhalten der CIM-Instanz mithilfe der CIM-Sitzung</span><span class="sxs-lookup"><span data-stu-id="8295e-147">Example 10: Get the CIM instance using CIM session</span></span>

<span data-ttu-id="8295e-148">In diesem Beispiel wird eine CIM-Sitzung auf den Computern namens **Server01** und **Server02** mithilfe des `New-CimSession` Cmdlets erstellt und die Sitzungsinformationen in einer Variablen mit dem Namen gespeichert `$s` .</span><span class="sxs-lookup"><span data-stu-id="8295e-148">This example creates a CIM session on the computers named **Server01** and **Server02** using the `New-CimSession` cmdlet and stores the session information in a variable named `$s`.</span></span> <span data-ttu-id="8295e-149">Der Inhalt der Variablen wird dann `Get-CimInstance` mithilfe des **cimsession** -Parameters an übergeben, um die CIM-Instanzen der Klasse mit dem Namen " **Win32_ComputerSystem** " zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8295e-149">The contents of the variable are then passed to `Get-CimInstance` by using the **CimSession** parameter, to get the CIM instances of the class named **Win32_ComputerSystem**.</span></span>

```powershell
$s = New-CimSession -ComputerName Server01,Server02
Get-CimInstance -ClassName Win32_ComputerSystem -CimSession $s
```

## <span data-ttu-id="8295e-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8295e-150">PARAMETERS</span></span>

### <span data-ttu-id="8295e-151">-CimSession</span><span class="sxs-lookup"><span data-stu-id="8295e-151">-CimSession</span></span>

<span data-ttu-id="8295e-152">Gibt die CIM-Sitzung an, die für dieses Cmdlet verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8295e-152">Specifies the CIM session to use for this cmdlet.</span></span> <span data-ttu-id="8295e-153">Geben Sie eine Variable ein, die die CIM-Sitzung oder einen Befehl enthält, der die CIM-Sitzung erstellt `New-CimSession` oder `Get-CimSession` abruft, z. b. die Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="8295e-153">Enter a variable that contains the CIM session or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="8295e-154">Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="8295e-154">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="8295e-155">-ClassName</span><span class="sxs-lookup"><span data-stu-id="8295e-155">-ClassName</span></span>

<span data-ttu-id="8295e-156">Gibt den Namen der CIM-Klasse an, für die die CIM-Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8295e-156">Specifies the name of the CIM class for which to retrieve the CIM instances.</span></span> <span data-ttu-id="8295e-157">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8295e-157">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="8295e-158">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="8295e-158">-ComputerName</span></span>

<span data-ttu-id="8295e-159">Gibt den Computer an, auf dem Sie den CIM-Vorgang ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="8295e-159">Specifies computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="8295e-160">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN), einen NetBIOS-Namen oder eine IP-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="8295e-160">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="8295e-161">Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.</span><span class="sxs-lookup"><span data-stu-id="8295e-161">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="8295e-162">Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="8295e-162">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="8295e-163">Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, stellen Sie eine Verbindung mithilfe einer CIM-Sitzung her, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="8295e-163">If multiple operations are being performed on the same computer, connect using a CIM session for better performance.</span></span>

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

### <span data-ttu-id="8295e-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="8295e-164">-Filter</span></span>

<span data-ttu-id="8295e-165">Gibt eine WHERE-Klausel an, die als Filter verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8295e-165">Specifies a where clause to use as a filter.</span></span> <span data-ttu-id="8295e-166">Geben Sie die-Klausel entweder in der **WQL** -oder der **CQL** -Abfragesprache an.</span><span class="sxs-lookup"><span data-stu-id="8295e-166">Specify the clause in either the **WQL** or the **CQL** query language.</span></span> <span data-ttu-id="8295e-167">Fügen Sie das- `WHERE` Schlüsselwort nicht in den Wert des-Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="8295e-167">Do not include the `WHERE` keyword in the value of the parameter.</span></span>

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

### <span data-ttu-id="8295e-168">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8295e-168">-InputObject</span></span>

<span data-ttu-id="8295e-169">Gibt ein CIM-Instanzobjekt an, das als Eingabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8295e-169">Specifies a CIM instance object to use as input.</span></span>

<span data-ttu-id="8295e-170">Wenn Sie bereits mit einem CIM-Instanzobjekt arbeiten, können Sie diesen Parameter verwenden, um das CIM-Instanzobjekt zu übergeben, um die neueste Momentaufnahme vom CIM-Server zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8295e-170">If you are already working with a CIM instance object, you can use this parameter to pass the CIM instance object in order to get the latest snapshot from the CIM server.</span></span> <span data-ttu-id="8295e-171">Wenn Sie ein CIM-Instanzobjekt als Eingabe übergeben, wird `Get-CimInstance` das Objekt vom Server mit einem Get-CIM-Vorgang anstelle eines auflisten-oder Abfrage Vorgangs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8295e-171">When you pass a CIM instance object as an input, `Get-CimInstance` returns the object from server using a get CIM operation, instead of an enumerate or query operation.</span></span> <span data-ttu-id="8295e-172">Die Verwendung eines Get-CIM-Vorgangs ist effizienter als das Abrufen aller Instanzen und das anschließende filtern.</span><span class="sxs-lookup"><span data-stu-id="8295e-172">Using a get CIM operation is more efficient than retrieving all instances and then filtering them.</span></span>

<span data-ttu-id="8295e-173">Wenn die CIM-Klasse den Get-Vorgang nicht implementiert, gibt die Angabe des **Inputobject** -Parameters einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="8295e-173">If the CIM class does not implement the get operation, then specifying the **InputObject** parameter returns an error.</span></span>

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

### <span data-ttu-id="8295e-174">-Keyonly</span><span class="sxs-lookup"><span data-stu-id="8295e-174">-KeyOnly</span></span>

<span data-ttu-id="8295e-175">Gibt an, dass nur Objekte mit aufgefüllten Schlüsseleigenschaften zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8295e-175">Indicates that only objects with key properties populated are returned.</span></span> <span data-ttu-id="8295e-176">Durch die Angabe des **keyonly** -Parameters wird die Menge der über das Netzwerk übertragenen Daten reduziert.</span><span class="sxs-lookup"><span data-stu-id="8295e-176">Specifying the **KeyOnly** parameter reduces the amount of data transferred over the network.</span></span>

<span data-ttu-id="8295e-177">Verwenden Sie den **keyonly** -Parameter, um nur einen kleinen Teil des-Objekts zurückzugeben, der für andere Vorgänge, wie z `Set-CimInstance` . b. die-oder-Cmdlets, verwendet werden kann `Get-CimAssociatedInstance` .</span><span class="sxs-lookup"><span data-stu-id="8295e-177">Use the **KeyOnly** parameter to return only a small portion of the object, which can be used for other operations, such as the `Set-CimInstance` or `Get-CimAssociatedInstance` cmdlets.</span></span>

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

### <span data-ttu-id="8295e-178">-Namespace</span><span class="sxs-lookup"><span data-stu-id="8295e-178">-Namespace</span></span>

<span data-ttu-id="8295e-179">Gibt den Namespace der CIM-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="8295e-179">Specifies the namespace of CIM class.</span></span>

<span data-ttu-id="8295e-180">Der Standard Namespace ist **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="8295e-180">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="8295e-181">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8295e-181">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

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

### <span data-ttu-id="8295e-182">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="8295e-182">-OperationTimeoutSec</span></span>

<span data-ttu-id="8295e-183">Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet.</span><span class="sxs-lookup"><span data-stu-id="8295e-183">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="8295e-184">Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="8295e-184">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="8295e-185">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="8295e-185">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="8295e-186">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8295e-186">-Property</span></span>

<span data-ttu-id="8295e-187">Gibt eine Gruppe von Instanzeigenschaften an, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8295e-187">Specifies a set of instance properties to retrieve.</span></span> <span data-ttu-id="8295e-188">Verwenden Sie diesen Parameter, wenn Sie die Größe des Objekts, das entweder im Arbeitsspeicher oder über das Netzwerk zurückgegeben wird, verringern müssen.</span><span class="sxs-lookup"><span data-stu-id="8295e-188">Use this parameter when you need to reduce the size of the object returned, either in memory or over the network.</span></span> <span data-ttu-id="8295e-189">Das zurückgegebene Objekt enthält auch die Schlüsseleigenschaften, auch wenn Sie Sie nicht mithilfe des **Property** -Parameters aufgelistet haben.</span><span class="sxs-lookup"><span data-stu-id="8295e-189">The object returned also contains the key properties even if you have not listed them using the **Property** parameter.</span></span> <span data-ttu-id="8295e-190">Es sind andere Eigenschaften der-Klasse vorhanden, die jedoch nicht aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="8295e-190">Other properties of the class are present but they are not populated.</span></span>

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

### <span data-ttu-id="8295e-191">-Query</span><span class="sxs-lookup"><span data-stu-id="8295e-191">-Query</span></span>

<span data-ttu-id="8295e-192">Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8295e-192">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="8295e-193">Wenn der angegebene Wert doppelte Anführungszeichen `"` , einfache Anführungszeichen `'` oder einen umgekehrten Schrägstrich enthält `\` , müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8295e-193">If the value specified contains double quotes `"`, single quotes `'`, or a backslash `\`, you must escape those characters by prefixing them with the backslash character.</span></span> <span data-ttu-id="8295e-194">Wenn für den angegebenen Wert der WQL **like** -Operator verwendet wird, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern einschließen `[]` : Prozent `%` , unterstrich `_` oder öffnende eckige Klammer `[` .</span><span class="sxs-lookup"><span data-stu-id="8295e-194">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets `[]`: percent `%`, underscore `_`, or opening square bracket `[`.</span></span>

<span data-ttu-id="8295e-195">Es ist nicht möglich, eine Metadatenabfrage zum Abrufen einer Liste von Klassen oder einer Ereignis Abfrage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8295e-195">You cannot use a metadata query to retrieve a list of classes or an event query.</span></span> <span data-ttu-id="8295e-196">Verwenden Sie das-Cmdlet, um eine Liste der Klassen abzurufen `Get-CimClass` .</span><span class="sxs-lookup"><span data-stu-id="8295e-196">To retrieve a list of classes, use the `Get-CimClass` cmdlet.</span></span> <span data-ttu-id="8295e-197">Verwenden Sie zum Abrufen einer Ereignis Abfrage das- `Register-CimIndicationEvent` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8295e-197">To retrieve an event query, use the `Register-CimIndicationEvent` cmdlet.</span></span>

<span data-ttu-id="8295e-198">Sie können den Abfrage Dialekt mithilfe des **querydialekt** -Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="8295e-198">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

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

### <span data-ttu-id="8295e-199">-Querydialekt</span><span class="sxs-lookup"><span data-stu-id="8295e-199">-QueryDialect</span></span>

<span data-ttu-id="8295e-200">Gibt die Abfragesprache an, die für den Abfrage Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8295e-200">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="8295e-201">Die zulässigen Werte für diesen Parameter sind: **WQL** oder **CQL**.</span><span class="sxs-lookup"><span data-stu-id="8295e-201">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="8295e-202">Der Standardwert ist **WQL**.</span><span class="sxs-lookup"><span data-stu-id="8295e-202">The default value is **WQL**.</span></span>

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

### <span data-ttu-id="8295e-203">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="8295e-203">-ResourceUri</span></span>

<span data-ttu-id="8295e-204">Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="8295e-204">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="8295e-205">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="8295e-205">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="8295e-206">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="8295e-206">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="8295e-207">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8295e-207">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="8295e-208">Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.</span><span class="sxs-lookup"><span data-stu-id="8295e-208">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="8295e-209">**ResourceUri** kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der **Computername** -Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt.</span><span class="sxs-lookup"><span data-stu-id="8295e-209">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="8295e-210">Wenn Sie diesen Parameter ohne Angabe des **Computername** -Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie eine Fehlermeldung, da das DCOM-Protokoll den **resourceUri** -Parameter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8295e-210">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="8295e-211">Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8295e-211">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

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

### <span data-ttu-id="8295e-212">-Flach</span><span class="sxs-lookup"><span data-stu-id="8295e-212">-Shallow</span></span>

<span data-ttu-id="8295e-213">Gibt an, dass die Instanzen einer Klasse zurückgegeben werden, ohne die Instanzen von untergeordneten Klassen einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="8295e-213">Indicates that the instances of a class are returned without including the instances of any child classes.</span></span> <span data-ttu-id="8295e-214">Standardmäßig gibt das Cmdlet die Instanzen einer Klasse und ihrer untergeordneten Klassen zurück.</span><span class="sxs-lookup"><span data-stu-id="8295e-214">By default, the cmdlet returns the instances of a class and its child classes.</span></span>

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

### <span data-ttu-id="8295e-215">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8295e-215">CommonParameters</span></span>

<span data-ttu-id="8295e-216">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8295e-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8295e-217">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8295e-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8295e-218">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8295e-218">INPUTS</span></span>

### <span data-ttu-id="8295e-219">CIM-Instanz</span><span class="sxs-lookup"><span data-stu-id="8295e-219">CIM Instance</span></span>

<span data-ttu-id="8295e-220">Dieses Cmdlet akzeptiert ein Eingabe Objekt, das mit dem Inputobject-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8295e-220">This cmdlet accepts an input objects specified with the InputObject parameter.</span></span>

## <span data-ttu-id="8295e-221">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8295e-221">OUTPUTS</span></span>

### <span data-ttu-id="8295e-222">CIM-Instanz</span><span class="sxs-lookup"><span data-stu-id="8295e-222">CIM Instance</span></span>

<span data-ttu-id="8295e-223">Dieses Cmdlet gibt ein oder mehrere CIM-Instanzobjekte zurück, die eine Momentaufnahme der CIM-Instanzen auf dem CIM-Server darstellen.</span><span class="sxs-lookup"><span data-stu-id="8295e-223">This cmdlet returns one or more CIM instance objects representing a snapshot of the CIM instances on the CIM server.</span></span>

## <span data-ttu-id="8295e-224">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8295e-224">NOTES</span></span>

## <span data-ttu-id="8295e-225">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8295e-225">RELATED LINKS</span></span>

[<span data-ttu-id="8295e-226">Format-Table</span><span class="sxs-lookup"><span data-stu-id="8295e-226">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="8295e-227">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="8295e-227">Get-CimAssociatedInstance</span></span>](Get-CimAssociatedInstance.md)

[<span data-ttu-id="8295e-228">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="8295e-228">Get-CimClass</span></span>](Get-CimClass.md)

[<span data-ttu-id="8295e-229">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="8295e-229">Invoke-CimMethod</span></span>](invoke-cimmethod.md)

[<span data-ttu-id="8295e-230">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="8295e-230">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="8295e-231">Register-CimIndicationEvent</span><span class="sxs-lookup"><span data-stu-id="8295e-231">Register-CimIndicationEvent</span></span>](Register-CimIndicationEvent.md)

[<span data-ttu-id="8295e-232">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="8295e-232">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="8295e-233">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="8295e-233">Set-CimInstance</span></span>](Set-CimInstance.md)
