---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 01/21/2020
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/invoke-cimmethod?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CimMethod
ms.openlocfilehash: a3636d485464aa66dce11d6a88431497ea45d6d0
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218532"
---
# <span data-ttu-id="b6409-103">Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="b6409-103">Invoke-CimMethod</span></span>

## <span data-ttu-id="b6409-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b6409-104">SYNOPSIS</span></span>
<span data-ttu-id="b6409-105">Ruft eine Methode einer CIM-Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="b6409-105">Invokes a method of a CIM class.</span></span>

## <span data-ttu-id="b6409-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b6409-106">SYNTAX</span></span>

### <span data-ttu-id="b6409-107">Classnamecomputerset (Standard)</span><span class="sxs-lookup"><span data-stu-id="b6409-107">ClassNameComputerSet (Default)</span></span>

```
Invoke-CimMethod [-ClassName] <String> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="b6409-108">Classnamesessionset</span><span class="sxs-lookup"><span data-stu-id="b6409-108">ClassNameSessionSet</span></span>

```
Invoke-CimMethod [-ClassName] <String> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="b6409-109">Resourceuricomputerset</span><span class="sxs-lookup"><span data-stu-id="b6409-109">ResourceUriComputerSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="b6409-110">Ciminstancesessionset</span><span class="sxs-lookup"><span data-stu-id="b6409-110">CimInstanceSessionSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6409-111">Ciminstancecomputerset</span><span class="sxs-lookup"><span data-stu-id="b6409-111">CimInstanceComputerSet</span></span>

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6409-112">Resourceurisessionset</span><span class="sxs-lookup"><span data-stu-id="b6409-112">ResourceUriSessionSet</span></span>

```
Invoke-CimMethod -ResourceUri <Uri> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="b6409-113">Cimclasscomputerset</span><span class="sxs-lookup"><span data-stu-id="b6409-113">CimClassComputerSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6409-114">Cimclasssessionset</span><span class="sxs-lookup"><span data-stu-id="b6409-114">CimClassSessionSet</span></span>

```
Invoke-CimMethod [-CimClass] <CimClass> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6409-115">Querycomputerset</span><span class="sxs-lookup"><span data-stu-id="b6409-115">QueryComputerSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6409-116">Querysessionset</span><span class="sxs-lookup"><span data-stu-id="b6409-116">QuerySessionSet</span></span>

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b6409-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b6409-117">DESCRIPTION</span></span>

<span data-ttu-id="b6409-118">Das `Invoke-CimMethod` Cmdlet ruft eine Methode einer CIM-Klasse oder CIM-Instanz mit den Name-Wert-Paaren auf, die durch den **Arguments** -Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b6409-118">The `Invoke-CimMethod` cmdlet invokes a method of a CIM class or CIM instance using the name-value pairs specified by the **Arguments** parameter.</span></span>

<span data-ttu-id="b6409-119">Wenn der **Inputobject** -Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="b6409-119">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="b6409-120">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="b6409-120">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="b6409-121">Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b6409-121">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="b6409-122">Wenn der **Inputobject** -Parameter angegeben wird, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="b6409-122">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="b6409-123">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, verwendet dieses Cmdlet die CIM-Sitzung oder den Computernamen aus dem Eingabe Objekt.</span><span class="sxs-lookup"><span data-stu-id="b6409-123">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="b6409-124">Wenn der **Computername** -Parameter oder der **cimsession** -Parameter angegeben wird, verwendet dieses Cmdlet entweder den Wert des **cimsession** -Parameter Werts oder den Wert des **Computername** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="b6409-124">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="b6409-125">Dies ist kein gängiges Szenario.</span><span class="sxs-lookup"><span data-stu-id="b6409-125">This is not a common scenario.</span></span>

## <span data-ttu-id="b6409-126">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b6409-126">EXAMPLES</span></span>

### <span data-ttu-id="b6409-127">Beispiel 1: Aufrufen einer Methode</span><span class="sxs-lookup"><span data-stu-id="b6409-127">Example 1: Invoke a method</span></span>

<span data-ttu-id="b6409-128">In diesem Beispiel wird die Beendigungs **Methode der** **Win32_Process** -Klasse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b6409-128">This example invokes the **Terminate** method of the **Win32_Process** class.</span></span>

```powershell
Invoke-CimMethod -Query 'select * from Win32_Process where name like "notepad%"' -MethodName "Terminate"
```

### <span data-ttu-id="b6409-129">Beispiel 2: Aufrufen einer Methode mithilfe des CIM-Instanzobjekts</span><span class="sxs-lookup"><span data-stu-id="b6409-129">Example 2: Invoke a method using CIM instance object</span></span>

<span data-ttu-id="b6409-130">In diesem Beispiel wird das CIM-Instanzobjekt abgerufen und `$x` mithilfe des-Cmdlets in einer Variablen mit dem Namen gespeichert `Get-CimInstance` .</span><span class="sxs-lookup"><span data-stu-id="b6409-130">This example retrieves the CIM instance object and stores it in a variable named `$x` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="b6409-131">Der Inhalt der Variablen wird dann als **Inputobject** für das `Invoke-CimMethod` Cmdlet verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6409-131">The contents of the variable are then used as the **InputObject** for the `Invoke-CimMethod` cmdlet.</span></span> <span data-ttu-id="b6409-132">Die **GetOwner** -Methode wird für die **ciminstance** aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b6409-132">The **GetOwner** method is invoked for the **CimInstance**.</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Process where name like "notepad%"'
Invoke-CimMethod -InputObject $x -MethodName GetOwner
```

### <span data-ttu-id="b6409-133">Beispiel 3: Aufrufen einer statischen Methode mithilfe von Argumenten</span><span class="sxs-lookup"><span data-stu-id="b6409-133">Example 3: Invoke a static method using arguments</span></span>

<span data-ttu-id="b6409-134">Dieses Beispiel ruft die **Create** -Methode mit dem Namen mit dem **Arguments** -Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="b6409-134">This example invokes the **Create** method named using the **Arguments** parameter.</span></span>

```powershell
Invoke-CimMethod -ClassName Win32_Process -MethodName "Create" -Arguments @{
  CommandLine = 'notepad.exe'; CurrentDirectory = "C:\windows\system32"
}
```

### <span data-ttu-id="b6409-135">Beispiel 4: Client seitige Validierung</span><span class="sxs-lookup"><span data-stu-id="b6409-135">Example 4: Client-side validation</span></span>

<span data-ttu-id="b6409-136">Dieses Beispiel führt die Client seitige Validierung für die **XYZ** -Methode durch, indem ein **cimclass** -Objekt an übergeben wird `Invoke-CimMethod` .</span><span class="sxs-lookup"><span data-stu-id="b6409-136">This example performs client-side validation for the **xyz** method by passing a **CimClass** object to `Invoke-CimMethod`.</span></span>

```powershell
$c = Get-CimClass -ClassName Win32_Process
Invoke-CimMethod -CimClass $c -MethodName "xyz" -Arguments @{ CommandLine = 'notepad.exe' }
```

## <span data-ttu-id="b6409-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b6409-137">PARAMETERS</span></span>

### <span data-ttu-id="b6409-138">-Arguments</span><span class="sxs-lookup"><span data-stu-id="b6409-138">-Arguments</span></span>

<span data-ttu-id="b6409-139">Gibt die Parameter an, die an die aufgerufene Methode übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b6409-139">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="b6409-140">Geben Sie die Werte für diesen Parameter als Name-Wert-Paare an, die in einer Hash Tabelle gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="b6409-140">Specify the values for this parameter as name-value pairs, stored in a hash table.</span></span> <span data-ttu-id="b6409-141">Die Reihenfolge der eingegebenen Werte ist nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="b6409-141">The order of the values entered isn't important.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-142">-Cimclass</span><span class="sxs-lookup"><span data-stu-id="b6409-142">-CimClass</span></span>

<span data-ttu-id="b6409-143">Gibt ein CIM-Klassenobjekt an, das eine CIM-Klassendefinition auf dem Server darstellt.</span><span class="sxs-lookup"><span data-stu-id="b6409-143">Specifies a CIM class object that represents a CIM class definition on the server.</span></span> <span data-ttu-id="b6409-144">Verwenden Sie diesen Parameter, wenn Sie eine statische Methode einer Klasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b6409-144">Use this parameter when invoking a static method of a class.</span></span>

<span data-ttu-id="b6409-145">Sie können das `Get-CimClass` Cmdlet verwenden, um eine Klassendefinition vom Server abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b6409-145">You can use the `Get-CimClass` cmdlet to retrieve a class definition from the server.</span></span>

<span data-ttu-id="b6409-146">Die Verwendung dieses Parameters führt zu besseren Client seitigen Schema Überprüfungen.</span><span class="sxs-lookup"><span data-stu-id="b6409-146">Using this parameter results in better client side schema validations.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassComputerSet, CimClassSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-147">-CimSession</span><span class="sxs-lookup"><span data-stu-id="b6409-147">-CimSession</span></span>

<span data-ttu-id="b6409-148">Führt den Befehl mit der angegebenen CIM-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="b6409-148">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="b6409-149">Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, mit dem die CIM-Sitzung erstellt oder abgerufen wird, z `New-CimSession` `Get-CimSession` . b. die Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="b6409-149">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="b6409-150">Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="b6409-150">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, CimInstanceSessionSet, CimClassSessionSet, QuerySessionSet, ResourceUriSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-151">-ClassName</span><span class="sxs-lookup"><span data-stu-id="b6409-151">-ClassName</span></span>

<span data-ttu-id="b6409-152">Gibt den Namen der CIM-Klasse an, für die der Vorgang durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6409-152">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="b6409-153">Dieser Parameter wird nur für statische Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6409-153">This parameter is only used for static methods.</span></span> <span data-ttu-id="b6409-154">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b6409-154">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases: Class

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b6409-155">-ComputerName</span></span>

<span data-ttu-id="b6409-156">Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="b6409-156">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="b6409-157">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN), einen NetBIOS-Namen oder eine IP-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="b6409-157">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="b6409-158">Wenn Sie diesen Parameter verwenden, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="b6409-158">When using this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span> <span data-ttu-id="b6409-159">Andernfalls führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.</span><span class="sxs-lookup"><span data-stu-id="b6409-159">Otherwise, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="b6409-160">Stellen Sie mithilfe einer CIM-Sitzung eine Verbindung her, um die Leistung zu verbessern, wenn mehrere Vorgänge auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b6409-160">Connect using a CIM session for better performance when multiple operations are being performed on the same computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet, CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-161">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b6409-161">-InputObject</span></span>

<span data-ttu-id="b6409-162">Gibt ein CIM-Instanzobjekt an, das als Eingabe zum Aufrufen einer Methode verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6409-162">Specifies a CIM instance object to use as input to invoke a method.</span></span> <span data-ttu-id="b6409-163">Dieser Parameter kann nur zum Aufrufen von Instanzmethoden verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b6409-163">This parameter can only be used to invoke instance methods.</span></span> <span data-ttu-id="b6409-164">Verwenden Sie den **Class** -Parameter oder den **cimclass** -Parameter, um statische Klassen Methoden aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b6409-164">To invoke class static methods, use the **Class** parameter or the **CimClass** parameter.</span></span>

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

### <span data-ttu-id="b6409-165">-MethodName</span><span class="sxs-lookup"><span data-stu-id="b6409-165">-MethodName</span></span>

<span data-ttu-id="b6409-166">Gibt den Namen der aufzurufenden CIM-Methode an.</span><span class="sxs-lookup"><span data-stu-id="b6409-166">Specifies the name of the CIM method to invoke.</span></span> <span data-ttu-id="b6409-167">Dieser Parameter ist erforderlich und kann nicht NULL oder leer sein.</span><span class="sxs-lookup"><span data-stu-id="b6409-167">This parameter is mandatory and cannot be null or empty.</span></span> <span data-ttu-id="b6409-168">Um die statische Methode einer CIM-Klasse aufzurufen, verwenden Sie den **className** -Parameter oder den **cimclass** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="b6409-168">To invoke static method of a CIM class use the **ClassName** or the **CimClass** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-169">-Namespace</span><span class="sxs-lookup"><span data-stu-id="b6409-169">-Namespace</span></span>

<span data-ttu-id="b6409-170">Gibt den Namespace für den CIM-Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="b6409-170">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="b6409-171">Der Standard Namespace ist **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="b6409-171">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="b6409-172">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b6409-172">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriComputerSet, ResourceUriSessionSet, QueryComputerSet, QuerySessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-173">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="b6409-173">-OperationTimeoutSec</span></span>

<span data-ttu-id="b6409-174">Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet.</span><span class="sxs-lookup"><span data-stu-id="b6409-174">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="b6409-175">Standardmäßig ist der Wert 0 (null), was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6409-175">By default, the value is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="b6409-176">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als das standardmäßige Verbindungs Wiederholungs Timeout von 3 Minuten ist, sind Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wiederherstellbar.</span><span class="sxs-lookup"><span data-stu-id="b6409-176">If the **OperationTimeoutSec** parameter is set to a value less than the default connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable.</span></span>

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

### <span data-ttu-id="b6409-177">-Query</span><span class="sxs-lookup"><span data-stu-id="b6409-177">-Query</span></span>

<span data-ttu-id="b6409-178">Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6409-178">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="b6409-179">Eine-Methode wird für die Instanzen aufgerufen, die als Ergebnis der Abfrage empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="b6409-179">A method is invoked on the instances received as a result of the query.</span></span> <span data-ttu-id="b6409-180">Sie können den Abfrage Dialekt mithilfe des **querydialekt** -Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="b6409-180">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="b6409-181">Wenn der angegebene Wert doppelte Anführungszeichen ( `"` ), einfache Anführungszeichen ( `'` ) oder einen umgekehrten Schrägstrich ( `\` ) enthält, müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich () vorangestellt werden `\` .</span><span class="sxs-lookup"><span data-stu-id="b6409-181">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="b6409-182">Wenn der angegebene Wert den WQL Like-Operator verwendet, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern ( `[]` ) einschließen: Prozent ( `%` ), Unterstrich ( `_` ) oder öffnende eckige Klammer ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="b6409-182">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QueryComputerSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-183">-Querydialekt</span><span class="sxs-lookup"><span data-stu-id="b6409-183">-QueryDialect</span></span>

<span data-ttu-id="b6409-184">Gibt die Abfragesprache an, die für den Abfrage Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b6409-184">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="b6409-185">Die zulässigen Werte für diesen Parameter sind: **WQL** oder **CQL**.</span><span class="sxs-lookup"><span data-stu-id="b6409-185">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span>

<span data-ttu-id="b6409-186">Der Standardwert ist **WQL**.</span><span class="sxs-lookup"><span data-stu-id="b6409-186">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: QueryComputerSet, QuerySessionSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-187">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="b6409-187">-ResourceUri</span></span>

<span data-ttu-id="b6409-188">Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="b6409-188">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="b6409-189">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="b6409-189">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="b6409-190">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="b6409-190">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="b6409-191">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b6409-191">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="b6409-192">Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.</span><span class="sxs-lookup"><span data-stu-id="b6409-192">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="b6409-193">**ResourceUri** kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der **Computername** -Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt.</span><span class="sxs-lookup"><span data-stu-id="b6409-193">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span>

<span data-ttu-id="b6409-194">Wenn Sie diesen Parameter ohne Angabe des **Computername** -Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="b6409-194">When you specify this parameter without specifying the **ComputerName** parameter, or when you specify a CIM session created using DCOM protocol, you get an error.</span></span> <span data-ttu-id="b6409-195">Das DCOM-Protokoll unterstützt den **resourceUri** -Parameter nicht.</span><span class="sxs-lookup"><span data-stu-id="b6409-195">The DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="b6409-196">Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b6409-196">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b6409-197">-Confirm</span></span>

<span data-ttu-id="b6409-198">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b6409-198">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b6409-199">-WhatIf</span></span>

<span data-ttu-id="b6409-200">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b6409-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b6409-201">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b6409-201">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b6409-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b6409-202">CommonParameters</span></span>

<span data-ttu-id="b6409-203">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b6409-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b6409-204">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b6409-204">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b6409-205">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b6409-205">INPUTS</span></span>

### <span data-ttu-id="b6409-206">CIM-Klasse</span><span class="sxs-lookup"><span data-stu-id="b6409-206">CIM class</span></span>

<span data-ttu-id="b6409-207">Dieses Cmdlet akzeptiert eine CIM-Klasse als Eingabe Objekt.</span><span class="sxs-lookup"><span data-stu-id="b6409-207">This cmdlet accepts a CIM class as an input object.</span></span>

### <span data-ttu-id="b6409-208">CIM-Instanz</span><span class="sxs-lookup"><span data-stu-id="b6409-208">CIM instance</span></span>

<span data-ttu-id="b6409-209">Dieses Cmdlet akzeptiert eine CIM-Instanz als Eingabe Objekt.</span><span class="sxs-lookup"><span data-stu-id="b6409-209">This cmdlet accepts a CIM instance as an input object.</span></span>

## <span data-ttu-id="b6409-210">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b6409-210">OUTPUTS</span></span>

### <span data-ttu-id="b6409-211">System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="b6409-211">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="b6409-212">Dieses Cmdlet gibt ein Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="b6409-212">This cmdlet returns an object.</span></span>

## <span data-ttu-id="b6409-213">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b6409-213">NOTES</span></span>

## <span data-ttu-id="b6409-214">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b6409-214">RELATED LINKS</span></span>

[<span data-ttu-id="b6409-215">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="b6409-215">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="b6409-216">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="b6409-216">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="b6409-217">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="b6409-217">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="b6409-218">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="b6409-218">New-CimSession</span></span>](New-CimSession.md)
