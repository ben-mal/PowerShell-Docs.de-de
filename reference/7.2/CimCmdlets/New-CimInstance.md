---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimInstance
ms.openlocfilehash: d81117ad6885d660e31f031bd8134096db91b7da
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598809"
---
# <span data-ttu-id="4d766-102">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="4d766-102">New-CimInstance</span></span>

## <span data-ttu-id="4d766-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4d766-103">SYNOPSIS</span></span>
<span data-ttu-id="4d766-104">Erstellt eine CIM-Instanz.</span><span class="sxs-lookup"><span data-stu-id="4d766-104">Creates a CIM instance.</span></span>

## <span data-ttu-id="4d766-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4d766-105">SYNTAX</span></span>

### <span data-ttu-id="4d766-106">Classnamecomputerset (Standard)</span><span class="sxs-lookup"><span data-stu-id="4d766-106">ClassNameComputerSet (Default)</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4d766-107">Classnamesessionset</span><span class="sxs-lookup"><span data-stu-id="4d766-107">ClassNameSessionSet</span></span>

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4d766-108">Resourceurisessionset</span><span class="sxs-lookup"><span data-stu-id="4d766-108">ResourceUriSessionSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4d766-109">Resourceuricomputerset</span><span class="sxs-lookup"><span data-stu-id="4d766-109">ResourceUriComputerSet</span></span>

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4d766-110">Cimclasssessionset</span><span class="sxs-lookup"><span data-stu-id="4d766-110">CimClassSessionSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4d766-111">Cimclasscomputerset</span><span class="sxs-lookup"><span data-stu-id="4d766-111">CimClassComputerSet</span></span>

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4d766-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4d766-112">DESCRIPTION</span></span>

<span data-ttu-id="4d766-113">Das- `New-CimInstance` Cmdlet erstellt eine Instanz einer CIM-Klasse auf der Grundlage der Klassendefinition auf dem lokalen Computer oder einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="4d766-113">The `New-CimInstance` cmdlet creates an instance of a CIM class based on the class definition on either the local computer or a remote computer.</span></span> <span data-ttu-id="4d766-114">Standardmäßig erstellt das `New-CimInstance` Cmdlet eine Instanz auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="4d766-114">By default, the `New-CimInstance` cmdlet creates an instance on the local computer.</span></span>

## <span data-ttu-id="4d766-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4d766-115">EXAMPLES</span></span>

### <span data-ttu-id="4d766-116">Beispiel 1: Erstellen einer Instanz einer CIM-Klasse</span><span class="sxs-lookup"><span data-stu-id="4d766-116">Example 1: Create an instance of a CIM class</span></span>

<span data-ttu-id="4d766-117">In diesem Beispiel wird eine Instanz einer CIM-Klasse mit dem Namen Win32_Environment im root/cimv2-Namespace auf dem Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="4d766-117">This example creates an instance of a CIM Class named win32_environment in the root/cimv2 namespace on the computer.</span></span>

```powershell
New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";VariableValue="testvalue";UserName="domain\user"}
```

<span data-ttu-id="4d766-118">Es wird keine Client seitige Validierung ausgeführt, wenn die Klasse nicht vorhanden ist, die Eigenschaften falsch sind oder der Server den-Befehl ablehnt.</span><span class="sxs-lookup"><span data-stu-id="4d766-118">No client side validation is performed if the class does not exist, the properties are wrong, or if the server rejects the call.</span></span> <span data-ttu-id="4d766-119">Wenn die Instanz erfolgreich erstellt wurde, gibt das Cmdlet die neu erstellte Instanz aus.</span><span class="sxs-lookup"><span data-stu-id="4d766-119">If the instance is created successfully, the cmdlet outputs the newly created instance.</span></span>

### <span data-ttu-id="4d766-120">Beispiel 2: Erstellen einer Instanz einer CIM-Klasse mithilfe eines Klassen Schemas</span><span class="sxs-lookup"><span data-stu-id="4d766-120">Example 2: Create an instance of a CIM class using a class schema</span></span>

<span data-ttu-id="4d766-121">In diesem Beispiel wird ein CIM-Klassenobjekt abgerufen und in einer Variablen mit dem Namen gespeichert `$class` .</span><span class="sxs-lookup"><span data-stu-id="4d766-121">This example retrieves a CIM class object and stores it in a variable named `$class`.</span></span> <span data-ttu-id="4d766-122">Der Inhalt der Variablen wird dann an das `New-CimInstance` Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="4d766-122">The contents of the variable are then passed to the `New-CimInstance` cmdlet.</span></span>

```powershell
$class = Get-CimClass -ClassName Win32_Environment
New-CimInstance -CimClass $class -Property @{Name="testvar";VariableValue="testvalue";UserName="Contoso\User1"}
```

### <span data-ttu-id="4d766-123">Beispiel 3: Erstellen einer dynamischen Instanz auf dem Client</span><span class="sxs-lookup"><span data-stu-id="4d766-123">Example 3: Create a dynamic instance on the client</span></span>

<span data-ttu-id="4d766-124">In diesem Beispiel wird eine dynamische Instanz einer CIM-Klasse mit dem Namen **Win32_Process** auf dem Client Computer erstellt, ohne die Instanz vom Server zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4d766-124">This example creates a dynamic instance of a CIM class named **Win32_Process** on the client computer without getting the instance from the server.</span></span> <span data-ttu-id="4d766-125">Die neue-Instanz wird in der-Variable gespeichert `$a` .</span><span class="sxs-lookup"><span data-stu-id="4d766-125">The new instance is stored in the variable `$a`.</span></span> <span data-ttu-id="4d766-126">Diese dynamische Instanz kann verwendet werden, um Vorgänge auszuführen, wenn die Instanz mit diesem Schlüssel auf dem Server vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4d766-126">This dynamic instance can be used to perform operations if the instance with this key exists on the server.</span></span>

```powershell
$a = New-CimInstance -ClassName Win32_Process -Property @{Handle=0} -Key Handle -ClientOnly
Get-CimInstance -CimInstance $a
Invoke-CimMethod -CimInstance $a -MethodName GetOwner
```

```Output
ProcessId Name                HandleCount WorkingSetSize VirtualSize
--------- ----                ----------- -------------- -----------
0         System Idle Process 0           8192           8192

Domain         :
ReturnValue    : 2
User           :
PSComputerName :
```

<span data-ttu-id="4d766-127">Das `Get-CimInstance` Cmdlet ruft dann eine bestimmte einzelne Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="4d766-127">The `Get-CimInstance` cmdlet then retrieves a particular single instance.</span></span> <span data-ttu-id="4d766-128">Das- `Invoke-CimMethod` Cmdlet ruft die **GetOwner** -Methode für die abgerufene-Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="4d766-128">The `Invoke-CimMethod` cmdlet calls the **GetOwner** method on the retrieved instance.</span></span>

### <span data-ttu-id="4d766-129">Beispiel 4: Erstellen einer Instanz für eine CIM-Klasse eines bestimmten Namespace</span><span class="sxs-lookup"><span data-stu-id="4d766-129">Example 4: Create an instance for a CIM class of a specific namespace</span></span>

<span data-ttu-id="4d766-130">In diesem Beispiel wird eine Instanz einer CIM-Klasse mit dem Namen **MSFT_Something** im Namespace **root/irgendwo** abgerufen und in einer Variablen mit dem Namen gespeichert `$class` .</span><span class="sxs-lookup"><span data-stu-id="4d766-130">This example gets an instance of a CIM class named **MSFT_Something** in the namespace **root/somewhere** and stores it in a variable named `$class`.</span></span> <span data-ttu-id="4d766-131">Die-Variable wird an das `New-CimInstance` Cmdlet übergeben, um eine neue CIM-Instanz zu erstellen und Client seitige Validierungen für die neue-Instanz auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4d766-131">The variable is passed to the `New-CimInstance` cmdlet to create a new CIM instance and perform client side validations on the new instance.</span></span>

```powershell
$class = Get-CimClass -ClassName MSFT_Something -Namespace root/somewhere
New-CimInstance -CimClass $class -Property @{"Prop1"=1;"Prop2"="value"} -ClientOnly
```

<span data-ttu-id="4d766-132">In diesem Beispiel überprüft die Verwendung des **cimclass** -Parameters anstelle des **className** -Parameters, ob **Eigenschaft PROP1** und **Prop2** tatsächlich vorhanden sind und dass die Schlüssel ordnungsgemäß gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="4d766-132">In this example, using the **CimClass** parameter instead of the **ClassName** parameter validates that **Prop1** and **Prop2** actually exist and that the keys are marked correctly.</span></span>

<span data-ttu-id="4d766-133">Der Parameter " **Computername** " oder " **cimsession** " kann nicht mit dem **clientonly** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d766-133">You cannot use the **ComputerName** or **CimSession** parameter with the **ClientOnly** parameter.</span></span>

## <span data-ttu-id="4d766-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4d766-134">PARAMETERS</span></span>

### <span data-ttu-id="4d766-135">-Cimclass</span><span class="sxs-lookup"><span data-stu-id="4d766-135">-CimClass</span></span>

<span data-ttu-id="4d766-136">Gibt ein CIM-Klassenobjekt an, das den Typ der Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="4d766-136">Specifies a CIM class object that represents the type of the instance.</span></span> <span data-ttu-id="4d766-137">Verwenden `Get-CimClass` Sie das Cmdlet, um die Klassen Deklaration von einem Computer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4d766-137">Use the `Get-CimClass` cmdlet to retrieve the class declaration from a computer.</span></span> <span data-ttu-id="4d766-138">Die Verwendung dieses Parameters führt zu besseren Client seitigen Schema Überprüfungen.</span><span class="sxs-lookup"><span data-stu-id="4d766-138">Using this parameter results in better client side schema validations.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassSessionSet, CimClassComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4d766-139">-CimSession</span><span class="sxs-lookup"><span data-stu-id="4d766-139">-CimSession</span></span>

<span data-ttu-id="4d766-140">Führt den Befehl mit der angegebenen CIM-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="4d766-140">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="4d766-141">Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, mit dem die CIM-Sitzung erstellt oder abgerufen wird, z `New-CimSession` `Get-CimSession` . b. die Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="4d766-141">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="4d766-142">Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="4d766-142">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, ResourceUriSessionSet, CimClassSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4d766-143">-ClassName</span><span class="sxs-lookup"><span data-stu-id="4d766-143">-ClassName</span></span>

<span data-ttu-id="4d766-144">Gibt den Namen der CIM-Klasse an, für die der Vorgang eine Instanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="4d766-144">Specifies the name of the CIM class of which the operation creates an instance.</span></span> <span data-ttu-id="4d766-145">Hinweis: mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4d766-145">NOTE: You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

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

### <span data-ttu-id="4d766-146">-Clientonly</span><span class="sxs-lookup"><span data-stu-id="4d766-146">-ClientOnly</span></span>

<span data-ttu-id="4d766-147">Gibt an, dass die Instanz nur in PowerShell erstellt wird, ohne dass der CIM-Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4d766-147">Indicates that the instance is only created in PowerShell without going to the CIM server.</span></span> <span data-ttu-id="4d766-148">Sie können diesen Parameter verwenden, um eine in-Memory-CIM-Instanz für die Verwendung in nachfolgenden PowerShell-Vorgängen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4d766-148">You can use this parameter to create an in-memory CIM instance for use in subsequent PowerShell operations.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, CimClassSessionSet, CimClassComputerSet
Aliases: Local

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d766-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="4d766-149">-ComputerName</span></span>

<span data-ttu-id="4d766-150">Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="4d766-150">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="4d766-151">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN), einen NetBIOS-Namen oder eine IP-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="4d766-151">You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="4d766-152">Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="4d766-152">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WSMan protocol.</span></span>

<span data-ttu-id="4d766-153">Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.</span><span class="sxs-lookup"><span data-stu-id="4d766-153">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="4d766-154">Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet eine Verbindung mit einer CIM-Sitzung eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="4d766-154">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4d766-155">-Key</span><span class="sxs-lookup"><span data-stu-id="4d766-155">-Key</span></span>

<span data-ttu-id="4d766-156">Gibt die Eigenschaften an, die als Schlüssel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d766-156">Specifies the properties that are used as keys.</span></span> <span data-ttu-id="4d766-157">**Cimsession** und **Computername** können nicht verwendet werden, wenn **Key** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4d766-157">**CimSession** and **ComputerName** cannot be used when **Key** is specified.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4d766-158">-Namespace</span><span class="sxs-lookup"><span data-stu-id="4d766-158">-Namespace</span></span>

<span data-ttu-id="4d766-159">Gibt den Namespace der-Klasse für die neue-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="4d766-159">Specifies the namespace of the class for the new instance.</span></span> <span data-ttu-id="4d766-160">Der Standard Namespace ist **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="4d766-160">The default namespace is **root/cimv2**.</span></span>
<span data-ttu-id="4d766-161">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4d766-161">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4d766-162">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="4d766-162">-OperationTimeoutSec</span></span>

<span data-ttu-id="4d766-163">Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort vom CIM-Server wartet.</span><span class="sxs-lookup"><span data-stu-id="4d766-163">Specifies the amount of time that the cmdlet waits for a response from the CIM server.</span></span> <span data-ttu-id="4d766-164">Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d766-164">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span> <span data-ttu-id="4d766-165">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4d766-165">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="4d766-166">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4d766-166">-Property</span></span>

<span data-ttu-id="4d766-167">Gibt die Eigenschaften der CIM-Instanz mithilfe einer Hash Tabelle (Name/Wert-Paare) an.</span><span class="sxs-lookup"><span data-stu-id="4d766-167">Specifies the properties of the CIM instance using a hash table (name-value pairs).</span></span>

<span data-ttu-id="4d766-168">Wenn Sie den **cimclass** -Parameter angeben, `New-CimInstance` führt das Cmdlet eine Eigenschafts Überprüfung auf dem Client aus, um sicherzustellen, dass die angegebenen Eigenschaften mit der Klassen Deklaration auf dem Server übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4d766-168">If you specify the **CimClass** parameter, then the `New-CimInstance` cmdlet performs a property validation on the client to make sure that the properties specified are consistent with the class declaration on the server.</span></span> <span data-ttu-id="4d766-169">Wenn der **cimclass** -Parameter nicht angegeben wird, erfolgt die Überprüfung der Eigenschaft auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="4d766-169">If the **CimClass** parameter is not specified, then the property validation is done on the server.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases: Arguments

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4d766-170">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="4d766-170">-ResourceUri</span></span>

<span data-ttu-id="4d766-171">Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="4d766-171">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="4d766-172">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="4d766-172">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="4d766-173">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="4d766-173">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="4d766-174">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4d766-174">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="4d766-175">Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.</span><span class="sxs-lookup"><span data-stu-id="4d766-175">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="4d766-176">**ResourceUri** kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der **Computername** -Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt.</span><span class="sxs-lookup"><span data-stu-id="4d766-176">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="4d766-177">Wenn Sie diesen Parameter ohne Angabe des **Computername** -Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie eine Fehlermeldung, da das DCOM-Protokoll den **resourceUri** -Parameter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4d766-177">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="4d766-178">Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="4d766-178">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4d766-179">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4d766-179">-Confirm</span></span>

<span data-ttu-id="4d766-180">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4d766-180">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4d766-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4d766-181">-WhatIf</span></span>

<span data-ttu-id="4d766-182">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4d766-182">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4d766-183">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4d766-183">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4d766-184">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4d766-184">CommonParameters</span></span>

<span data-ttu-id="4d766-185">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4d766-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4d766-186">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4d766-186">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4d766-187">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4d766-187">INPUTS</span></span>

### <span data-ttu-id="4d766-188">Keine</span><span class="sxs-lookup"><span data-stu-id="4d766-188">None</span></span>

<span data-ttu-id="4d766-189">Dieses Cmdlet akzeptiert keine Eingabe Objekte.</span><span class="sxs-lookup"><span data-stu-id="4d766-189">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="4d766-190">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4d766-190">OUTPUTS</span></span>

### <span data-ttu-id="4d766-191">System.Object</span><span class="sxs-lookup"><span data-stu-id="4d766-191">System.Object</span></span>

<span data-ttu-id="4d766-192">Dieses Cmdlet gibt ein Objekt zurück, das die CIM-Instanzinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="4d766-192">This cmdlet returns an object that contains the CIM instance information.</span></span>

## <span data-ttu-id="4d766-193">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4d766-193">NOTES</span></span>

## <span data-ttu-id="4d766-194">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4d766-194">RELATED LINKS</span></span>

[<span data-ttu-id="4d766-195">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="4d766-195">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="4d766-196">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="4d766-196">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="4d766-197">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="4d766-197">Remove-CimInstance</span></span>](remove-ciminstance.md)

[<span data-ttu-id="4d766-198">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="4d766-198">Set-CimInstance</span></span>](Set-CimInstance.md)

