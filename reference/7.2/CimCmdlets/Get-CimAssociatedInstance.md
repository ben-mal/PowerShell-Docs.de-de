---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimassociatedinstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimAssociatedInstance
ms.openlocfilehash: e14ba6db4f5e93c6e2c1824ce845f82720616bc5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599858"
---
# <span data-ttu-id="a13c7-102">Get-CimAssociatedInstance</span><span class="sxs-lookup"><span data-stu-id="a13c7-102">Get-CimAssociatedInstance</span></span>

## <span data-ttu-id="a13c7-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a13c7-103">SYNOPSIS</span></span>
<span data-ttu-id="a13c7-104">Ruft die CIM-Instanzen ab, die durch eine Zuordnung mit einer bestimmten CIM-Instanz verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a13c7-104">Retrieves the CIM instances that are connected to a specific CIM instance by an association.</span></span>

## <span data-ttu-id="a13c7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a13c7-105">SYNTAX</span></span>

### <span data-ttu-id="a13c7-106">Computergruppe (Standard)</span><span class="sxs-lookup"><span data-stu-id="a13c7-106">ComputerSet (Default)</span></span>

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] [-ComputerName <String[]>] [-KeyOnly] [<CommonParameters>]
```

### <span data-ttu-id="a13c7-107">Sessionset</span><span class="sxs-lookup"><span data-stu-id="a13c7-107">SessionSet</span></span>

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] -CimSession <CimSession[]> [-KeyOnly] [<CommonParameters>]
```

## <span data-ttu-id="a13c7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a13c7-108">DESCRIPTION</span></span>

<span data-ttu-id="a13c7-109">Das- `Get-CimAssociatedInstance` Cmdlet ruft die CIM-Instanzen ab, die mit einer bestimmten CIM-Instanz, der sogenannten Quell Instanz, verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a13c7-109">The `Get-CimAssociatedInstance` cmdlet retrieves the CIM instances connected to a specific CIM instance, called the source instance, by an association.</span></span>

<span data-ttu-id="a13c7-110">In einer Zuordnung hat jede CIM-Instanz eine benannte Rolle, und dieselbe CIM-Instanz kann an einer Zuordnung in verschiedenen Rollen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="a13c7-110">In an association, each CIM instance has a named role and the same CIM instance can participate in an association in different roles.</span></span>

<span data-ttu-id="a13c7-111">Wenn der Inputobject-Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="a13c7-111">If the InputObject parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="a13c7-112">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="a13c7-112">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="a13c7-113">Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a13c7-113">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

## <span data-ttu-id="a13c7-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a13c7-114">EXAMPLES</span></span>

### <span data-ttu-id="a13c7-115">Beispiel 1: alle zugeordneten Instanzen einer bestimmten Instanz</span><span class="sxs-lookup"><span data-stu-id="a13c7-115">Example 1: Get all the associated instances of a specific instance</span></span>

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1]
```

<span data-ttu-id="a13c7-116">Dieser Satz von Befehlen ruft die Instanzen der-Klasse mit dem Namen Win32_LogicalDisk ab und speichert die Informationen in einer Variablen `$disk` mit dem Namen mithilfe des- `Get-CimInstance` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a13c7-116">This set of commands retrieves the instances of the class named Win32_LogicalDisk and stores the information in a variable named `$disk` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="a13c7-117">Die erste logische Datenträger Instanz in der Variablen wird dann als Eingabe Objekt für das `Get-CimAssociatedInstance` Cmdlet verwendet, um alle zugeordneten CIM-Instanzen der angegebenen CIM-Instanz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a13c7-117">The first logical disk instance in the variable is then used as the input object for the `Get-CimAssociatedInstance` cmdlet to get all the associated CIM instances of the specified CIM instance.</span></span>

### <span data-ttu-id="a13c7-118">Beispiel 2: alle zugeordneten Instanzen eines bestimmten Typs</span><span class="sxs-lookup"><span data-stu-id="a13c7-118">Example 2: Get all the associated instances of a specific type</span></span>

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1] -ResultClass Win32_DiskPartition
```

<span data-ttu-id="a13c7-119">Dieser Satz von Befehlen ruft alle Instanzen der **Win32_LogicalDisk** -Klasse ab und speichert Sie in einer Variablen mit dem Namen `$disk` .</span><span class="sxs-lookup"><span data-stu-id="a13c7-119">This set of commands retrieves all the instances of the **Win32_LogicalDisk** class and stores them in a variable named `$disk`.</span></span> <span data-ttu-id="a13c7-120">Die erste logische Datenträger Instanz in der Variablen wird dann als Eingabe Objekt für das `Get-CimAssociatedInstance` Cmdlet verwendet, um alle zugeordneten-Instanzen zu erhalten, die über die angegebene Association-Klasse **Win32_DiskPartition** verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="a13c7-120">The first logical disk instance in the variable is then used as the input object for the `Get-CimAssociatedInstance` cmdlet to get all the associated instances that are associated through the specified association class **Win32_DiskPartition**.</span></span>

### <span data-ttu-id="a13c7-121">Beispiel 3: alle zugeordneten Instanzen über den Qualifizierer einer bestimmten Klasse</span><span class="sxs-lookup"><span data-stu-id="a13c7-121">Example 3: Get all the associated instances through qualifier of a specific class</span></span>

```powershell
$s = Get-CimInstance -Query "Select * from Win32_Service where name like 'Winmgmt'"
Get-CimClass -ClassName *Service* -Qualifier "Association"
$c.CimClasName
```

```Output
Win32_LoadOrderGroupServiceDependencies
Win32_DependentService
Win32_SystemServices
Win32_LoadOrderGroupServiceMembers
Win32_ServiceSpecificationService
```

```powershell
Get-CimAssociatedInstance -InputObject $s -Association Win32_DependentService
```

<span data-ttu-id="a13c7-122">Dieser Satz von Befehlen ruft die Dienste ab, die vom WMI-Dienst abhängig sind, und speichert Sie in einer Variablen mit dem Namen `$s` .</span><span class="sxs-lookup"><span data-stu-id="a13c7-122">This set of commands retrieves the services that depend on WMI service and stores them in a variable named `$s`.</span></span> <span data-ttu-id="a13c7-123">Der Zuordnungs Klassenname für den **Win32_DependentService** wird mithilfe des `Get-CimClass` Cmdlets abgerufen,  indem die Zuordnung als Qualifizierer angegeben und dann mit $s an das Cmdlet übergeben wird, `Get-CimAssociatedInstance` um alle zugeordneten Instanzen der abgerufenen Zuordnungs Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a13c7-123">The association class name for the **Win32_DependentService** is retrieved using the `Get-CimClass` cmdlet by specifying **Association** as the qualifier and is then passed with $s to the `Get-CimAssociatedInstance` cmdlet to get all the associated instances of the retrieved association class.</span></span>

## <span data-ttu-id="a13c7-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a13c7-124">PARAMETERS</span></span>

### <span data-ttu-id="a13c7-125">-Association</span><span class="sxs-lookup"><span data-stu-id="a13c7-125">-Association</span></span>

<span data-ttu-id="a13c7-126">Gibt den Namen der Association-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="a13c7-126">Specifies the name of the association class.</span></span> <span data-ttu-id="a13c7-127">Wenn Sie diesen Parameter nicht angeben, gibt das Cmdlet alle vorhandenen Zuordnungs Objekte eines beliebigen Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="a13c7-127">If you do not specify this parameter, the cmdlet returns all existing association objects of any type.</span></span>

<span data-ttu-id="a13c7-128">Wenn z. B. Class a mit Class B über zwei Zuordnungen, AB1 und AB2, verknüpft ist, kann dieser Parameter verwendet werden, um den Typ der Zuordnung anzugeben, entweder AB1 oder AB2.</span><span class="sxs-lookup"><span data-stu-id="a13c7-128">For example, if class A is associated with class B through two associations, AB1 and AB2, then this parameter can be used to specify the type of association, either AB1 or AB2.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a13c7-129">-CimSession</span><span class="sxs-lookup"><span data-stu-id="a13c7-129">-CimSession</span></span>

<span data-ttu-id="a13c7-130">Führt den Befehl mit der angegebenen CIM-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="a13c7-130">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="a13c7-131">Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, der die CIM-Sitzung erstellt oder abruft, z `New-CimSession` `Get-CimSession` . b. oder.</span><span class="sxs-lookup"><span data-stu-id="a13c7-131">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as `New-CimSession` or `Get-CimSession`.</span></span> <span data-ttu-id="a13c7-132">Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="a13c7-132">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: SessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a13c7-133">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="a13c7-133">-ComputerName</span></span>

<span data-ttu-id="a13c7-134">Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="a13c7-134">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="a13c7-135">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) oder einen NetBIOS-Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="a13c7-135">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="a13c7-136">Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="a13c7-136">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="a13c7-137">Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.</span><span class="sxs-lookup"><span data-stu-id="a13c7-137">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="a13c7-138">Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet eine Verbindung mit einer CIM-Sitzung eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="a13c7-138">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a13c7-139">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a13c7-139">-InputObject</span></span>

<span data-ttu-id="a13c7-140">Gibt die Eingabe für dieses Cmdlet an.</span><span class="sxs-lookup"><span data-stu-id="a13c7-140">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="a13c7-141">Verwenden Sie diesen Parameter, außerdem können Sie die Eingabe für dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="a13c7-141">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a13c7-142">-Keyonly</span><span class="sxs-lookup"><span data-stu-id="a13c7-142">-KeyOnly</span></span>

<span data-ttu-id="a13c7-143">Gibt Objekte zurück, für die nur Schlüsseleigenschaften aufgefüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="a13c7-143">Returns objects with only key properties populated.</span></span> <span data-ttu-id="a13c7-144">Dadurch wird die Menge der Daten reduziert, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="a13c7-144">This reduces the amount of data that is transferred over the network.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a13c7-145">-Namespace</span><span class="sxs-lookup"><span data-stu-id="a13c7-145">-Namespace</span></span>

<span data-ttu-id="a13c7-146">Gibt den Namespace für den CIM-Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="a13c7-146">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="a13c7-147">Der Standard Namespace ist root/cimv2.</span><span class="sxs-lookup"><span data-stu-id="a13c7-147">The default namespace is root/cimv2.</span></span>

> [!NOTE]
> <span data-ttu-id="a13c7-148">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a13c7-148">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a13c7-149">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="a13c7-149">-OperationTimeoutSec</span></span>

<span data-ttu-id="a13c7-150">Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet.</span><span class="sxs-lookup"><span data-stu-id="a13c7-150">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="a13c7-151">Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="a13c7-151">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="a13c7-152">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="a13c7-152">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a13c7-153">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="a13c7-153">-ResourceUri</span></span>

<span data-ttu-id="a13c7-154">Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="a13c7-154">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="a13c7-155">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="a13c7-155">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="a13c7-156">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="a13c7-156">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="a13c7-157">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a13c7-157">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="a13c7-158">Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.</span><span class="sxs-lookup"><span data-stu-id="a13c7-158">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="a13c7-159">**ResourceUri** kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der **Computername** -Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt.</span><span class="sxs-lookup"><span data-stu-id="a13c7-159">**ResourceURI** can only be used with CIM sessions created using the WSMan protocol, or when specifying the **ComputerName** parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="a13c7-160">Wenn Sie diesen Parameter ohne Angabe des **Computername** -Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie eine Fehlermeldung, da das DCOM-Protokoll den **resourceUri** -Parameter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a13c7-160">If you specify this parameter without specifying the **ComputerName** parameter, or if you specify a CIM session created using DCOM protocol, you get an error, because the DCOM protocol does not support the **ResourceURI** parameter.</span></span>

<span data-ttu-id="a13c7-161">Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a13c7-161">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a13c7-162">-Resultclassname</span><span class="sxs-lookup"><span data-stu-id="a13c7-162">-ResultClassName</span></span>

<span data-ttu-id="a13c7-163">Gibt den Klassennamen der zugeordneten-Instanzen an.</span><span class="sxs-lookup"><span data-stu-id="a13c7-163">Specifies the class name of the associated instances.</span></span> <span data-ttu-id="a13c7-164">Eine CIM-Instanz kann einer oder mehreren CIM-Instanzen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a13c7-164">A CIM instance can be associated with one or more CIM instances.</span></span> <span data-ttu-id="a13c7-165">Wenn Sie den Namen der Ergebnis Klasse nicht angeben, werden alle zugeordneten CIM-Instanzen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a13c7-165">All associated CIM instances are returned if you do not specify the result class name.</span></span>

<span data-ttu-id="a13c7-166">Standardmäßig ist der Wert dieses Parameters NULL, und alle zugeordneten CIM-Instanzen werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a13c7-166">By default, the value of this parameter is null, and all associated CIM instances are returned.</span></span>

<span data-ttu-id="a13c7-167">Sie können die Zuordnungs Ergebnisse nach einem bestimmten Klassennamen filtern.</span><span class="sxs-lookup"><span data-stu-id="a13c7-167">You can filter the association results to match a specific class name.</span></span> <span data-ttu-id="a13c7-168">Die Filterung erfolgt auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="a13c7-168">Filtering happens on the server.</span></span> <span data-ttu-id="a13c7-169">Wenn dieser Parameter nicht angegeben wird, `Get-CIMAssociatedInstance` gibt alle vorhandenen Zuordnungen zurück.</span><span class="sxs-lookup"><span data-stu-id="a13c7-169">If this parameter is not specified, `Get-CIMAssociatedInstance` returns all existing associations.</span></span> <span data-ttu-id="a13c7-170">Wenn class a z. b. den Klassen B, c und d zugeordnet ist, kann dieser Parameter verwendet werden, um die Ausgabe auf einen bestimmten Typ (B, c oder d) zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="a13c7-170">For example, if class A is associated with classes B, C and D, then this parameter can be used to restrict the output to a specific type (B, C or D).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a13c7-171">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a13c7-171">CommonParameters</span></span>

<span data-ttu-id="a13c7-172">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a13c7-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a13c7-173">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a13c7-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a13c7-174">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a13c7-174">INPUTS</span></span>

### <span data-ttu-id="a13c7-175">Keine</span><span class="sxs-lookup"><span data-stu-id="a13c7-175">None</span></span>

<span data-ttu-id="a13c7-176">Dieses Cmdlet akzeptiert keine Eingabe Objekte.</span><span class="sxs-lookup"><span data-stu-id="a13c7-176">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="a13c7-177">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a13c7-177">OUTPUTS</span></span>

### <span data-ttu-id="a13c7-178">System.Object</span><span class="sxs-lookup"><span data-stu-id="a13c7-178">System.Object</span></span>

<span data-ttu-id="a13c7-179">Dieses Cmdlet gibt ein Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="a13c7-179">This cmdlet returns an object.</span></span>

## <span data-ttu-id="a13c7-180">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a13c7-180">NOTES</span></span>

## <span data-ttu-id="a13c7-181">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a13c7-181">RELATED LINKS</span></span>

[<span data-ttu-id="a13c7-182">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="a13c7-182">Get-CimClass</span></span>](get-cimclass.md)

[<span data-ttu-id="a13c7-183">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="a13c7-183">Get-CimInstance</span></span>](get-ciminstance.md)

