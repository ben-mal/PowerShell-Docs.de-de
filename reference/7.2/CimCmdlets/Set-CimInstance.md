---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/set-ciminstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CimInstance
ms.openlocfilehash: 041ef2d5b5541c250b98003099fe58018df155c2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601900"
---
# <span data-ttu-id="73160-102">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="73160-102">Set-CimInstance</span></span>

## <span data-ttu-id="73160-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="73160-103">SYNOPSIS</span></span>
<span data-ttu-id="73160-104">Ändert eine CIM-Instanz auf einem CIM-Server durch Aufrufen der modifyinstance-Methode der CIM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="73160-104">Modifies a CIM instance on a CIM server by calling the ModifyInstance method of the CIM class.</span></span>

## <span data-ttu-id="73160-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73160-105">SYNTAX</span></span>

### <span data-ttu-id="73160-106">Ciminstancecomputerset (Standard)</span><span class="sxs-lookup"><span data-stu-id="73160-106">CimInstanceComputerSet (Default)</span></span>

```
Set-CimInstance [-ComputerName <String[]>] [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="73160-107">Ciminstancesessionset</span><span class="sxs-lookup"><span data-stu-id="73160-107">CimInstanceSessionSet</span></span>

```
Set-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="73160-108">Querysessionset</span><span class="sxs-lookup"><span data-stu-id="73160-108">QuerySessionSet</span></span>

```
Set-CimInstance -CimSession <CimSession[]> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="73160-109">Querycomputerset</span><span class="sxs-lookup"><span data-stu-id="73160-109">QueryComputerSet</span></span>

```
Set-CimInstance [-ComputerName <String[]>] [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="73160-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="73160-110">DESCRIPTION</span></span>

<span data-ttu-id="73160-111">Dieses Cmdlet ändert eine CIM-Instanz auf einem CIM-Server.</span><span class="sxs-lookup"><span data-stu-id="73160-111">This cmdlet modifies a CIM instance on a CIM server.</span></span>

<span data-ttu-id="73160-112">Wenn der **Inputobject** -Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="73160-112">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="73160-113">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="73160-113">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="73160-114">Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="73160-114">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="73160-115">Wenn der **Inputobject** -Parameter angegeben wird, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="73160-115">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="73160-116">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, verwendet dieses Cmdlet die CIM-Sitzung oder den Computernamen aus dem Eingabe Objekt.</span><span class="sxs-lookup"><span data-stu-id="73160-116">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="73160-117">Wenn der **Computername** -Parameter oder der **cimsession** -Parameter angegeben wird, verwendet dieses Cmdlet entweder den Wert des **cimsession** -Parameter Werts oder den Wert des **Computername** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="73160-117">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="73160-118">Dies ist nicht sehr üblich.</span><span class="sxs-lookup"><span data-stu-id="73160-118">This is not very common.</span></span>

## <span data-ttu-id="73160-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="73160-119">EXAMPLES</span></span>

### <span data-ttu-id="73160-120">Beispiel 1: Festlegen der CIM-Instanz</span><span class="sxs-lookup"><span data-stu-id="73160-120">Example 1: Set the CIM instance</span></span>

<span data-ttu-id="73160-121">In diesem Beispiel wird der Wert der **VariableValue** -Eigenschaft mithilfe des **Abfrage** Parameters auf **ABCD** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="73160-121">This example sets the value of the **VariableValue** property to **abcd** using the **Query** parameter.</span></span> <span data-ttu-id="73160-122">Sie können-Instanzen ändern, die mit einer WQL-Abfrage (Windows-Verwaltungsinstrumentation Query Language) übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73160-122">You can modify instances matching a Windows Management Instrumentation Query Language (WQL) query.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"}
```

### <span data-ttu-id="73160-123">Beispiel 2: Festlegen der CIM-Instanzeigenschaft mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="73160-123">Example 2: Set the CIM instance property using pipeline</span></span>

<span data-ttu-id="73160-124">In diesem Beispiel wird das CIM-Instanzobjekt, das durch den **Abfrage** Parameter gefiltert wird, mithilfe des- `Get-CimInstance` Cmdlets abgerufen.</span><span class="sxs-lookup"><span data-stu-id="73160-124">This example retrieves the CIM instance object filtered by the **Query** parameter using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="73160-125">Das `Set-CimInstance` Cmdlet ändert den Wert der **VariableValue** -Eigenschaft in **ABCD**.</span><span class="sxs-lookup"><span data-stu-id="73160-125">The `Set-CimInstance` cmdlet modifies the value of **VariableValue** property to **abcd**.</span></span>

```powershell
Get-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' |
  Set-CimInstance -Property @{VariableValue="abcd"}
```

### <span data-ttu-id="73160-126">Beispiel 3: Festlegen der CIM-Instanzeigenschaft mithilfe des Eingabe Objekts</span><span class="sxs-lookup"><span data-stu-id="73160-126">Example 3: Set the CIM instance property using input object</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where Name="testvar"'
Set-CimInstance -InputObject $x -Property @{VariableValue="somevalue"} -PassThru
```

<span data-ttu-id="73160-127">In diesem Beispiel werden die CIM-Instanzobjekte, die vom Abfrage Parameter in gefiltert werden, mithilfe von zu einer Variablen abgerufen `$x` `Get-CimInstance` und dann der Inhalt der Variablen an das `Set-CimInstance` Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="73160-127">This example retrieves the CIM instance objects filtered by the Query parameter in to a variable `$x` using `Get-CimInstance`, and then passes the contents of the variable to the `Set-CimInstance` cmdlet.</span></span> <span data-ttu-id="73160-128">`Set-CimInstance` ändert dann die **VariableValue** -Eigenschaft in " **someValue**".</span><span class="sxs-lookup"><span data-stu-id="73160-128">`Set-CimInstance` then modifies the **VariableValue** property to **somevalue**.</span></span> <span data-ttu-id="73160-129">Da der **passthru** -Parameter verwendet wird, gibt dieses Beispiel ein geändertes CIM-Instanzobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="73160-129">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

### <span data-ttu-id="73160-130">Beispiel 4: Festlegen der CIM-Instanzeigenschaft</span><span class="sxs-lookup"><span data-stu-id="73160-130">Example 4: Set the CIM instance property</span></span>

<span data-ttu-id="73160-131">In diesem Beispiel wird das CIM-Instanzobjekt, das im- **Abfrage** Parameter angegeben ist `$x` , mithilfe des `Get-CimInstance` -Cmdlets in eine Variable abgerufen, und der **VariableValue** -Eigenschafts Wert des-Objekts wird geändert.</span><span class="sxs-lookup"><span data-stu-id="73160-131">This example retrieves the CIM instance object that is specified in the **Query** parameter into a variable `$x` using the `Get-CimInstance` cmdlet, and changes the **VariableValue** property value of the object to change.</span></span> <span data-ttu-id="73160-132">Das CIM-Instanzobjekt wird dann mithilfe des `Set-CimInstance` Cmdlets gespeichert.</span><span class="sxs-lookup"><span data-stu-id="73160-132">The CIM instance object is then saved using the `Set-CimInstance` cmdlet.</span></span>
<span data-ttu-id="73160-133">Da der **passthru** -Parameter verwendet wird, gibt dieses Beispiel ein geändertes CIM-Instanzobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="73160-133">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where name="testvar"'
$x.VariableValue = "Change"
Set-CimInstance -CimInstance $x -PassThru
```

### <span data-ttu-id="73160-134">Beispiel 5: Anzeigen der Liste der CIM-Instanzen, die mit WhatIf geändert werden sollen</span><span class="sxs-lookup"><span data-stu-id="73160-134">Example 5: Show the list of CIM instances to modify using WhatIf</span></span>

<span data-ttu-id="73160-135">In diesem Beispiel wird der allgemeine Parameter **WhatIf** verwendet, um anzugeben, dass die Änderung nicht durchgeführt werden soll, sondern nur, was geschehen würde, wenn dies geschehen wäre.</span><span class="sxs-lookup"><span data-stu-id="73160-135">This example uses the common parameter **WhatIf** to specify that the modification should not be done, but only output what would happen if it were done.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -WhatIf
```

### <span data-ttu-id="73160-136">Beispiel 6: Festlegen der CIM-Instanz nach der Bestätigung durch den Benutzer</span><span class="sxs-lookup"><span data-stu-id="73160-136">Example 6: Set the CIM instance after confirmation from the user</span></span>

<span data-ttu-id="73160-137">In diesem Beispiel wird der allgemeine Parameter **Confirm** verwendet, um anzugeben, dass die Änderung erst nach der Bestätigung durch den Benutzer vorgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="73160-137">This example uses the common parameter **Confirm** to specify that the modification should be done only after confirmation from the user.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -Confirm
```

### <span data-ttu-id="73160-138">Beispiel 7: Festlegen der erstellten CIM-Instanz</span><span class="sxs-lookup"><span data-stu-id="73160-138">Example 7: Set the created CIM instance</span></span>

<span data-ttu-id="73160-139">In diesem Beispiel wird mithilfe des-Cmdlets eine CIM-Instanz mit den angegebenen Eigenschaften erstellt `New-CimInstance` und der Inhalt in eine Variable abgerufen `$x` .</span><span class="sxs-lookup"><span data-stu-id="73160-139">This example creates a CIM instance with the specified properties using the `New-CimInstance` cmdlet, and retrieves its contents in to a variable `$x`.</span></span> <span data-ttu-id="73160-140">Die Variable wird dann an das `Set-CimInstance` Cmdlet übergeben, das den Wert der **VariableValue** -Eigenschaft in " **someValue**" ändert.</span><span class="sxs-lookup"><span data-stu-id="73160-140">The variable is then passed to the `Set-CimInstance` cmdlet, which modifies the value of **VariableValue** property to **somevalue**.</span></span>
<span data-ttu-id="73160-141">Da der **passthru** -Parameter verwendet wird, gibt dieses Beispiel ein geändertes CIM-Instanzobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="73160-141">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";UserName="domain\user"} -Keys Name,UserName -ClientOnly
Set-CimInstance -CimInstance $x -Property @{VariableValue="somevalue"} -PassThru
```

## <span data-ttu-id="73160-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73160-142">PARAMETERS</span></span>

### <span data-ttu-id="73160-143">-CimSession</span><span class="sxs-lookup"><span data-stu-id="73160-143">-CimSession</span></span>

<span data-ttu-id="73160-144">Führt die Cmdlets auf einem Remote Computer aus.</span><span class="sxs-lookup"><span data-stu-id="73160-144">Runs the cmdlets on a remote computer.</span></span> <span data-ttu-id="73160-145">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines- `New-CimSession` oder- `Get-CimSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="73160-145">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimInstanceSessionSet, QuerySessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="73160-146">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="73160-146">-ComputerName</span></span>

<span data-ttu-id="73160-147">Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="73160-147">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="73160-148">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) oder einen NetBIOS-Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="73160-148">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="73160-149">Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.</span><span class="sxs-lookup"><span data-stu-id="73160-149">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="73160-150">Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="73160-150">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="73160-151">Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet eine Verbindung mit einer CIM-Sitzung eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="73160-151">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73160-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="73160-152">-InputObject</span></span>

<span data-ttu-id="73160-153">Gibt ein CIM-Instanzobjekt an, das als Eingabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="73160-153">Specifies a CIM instance object to use as input.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="73160-154">-Namespace</span><span class="sxs-lookup"><span data-stu-id="73160-154">-Namespace</span></span>

<span data-ttu-id="73160-155">Gibt den Namespace für den CIM-Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="73160-155">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="73160-156">Der Standard Namespace ist root/cimv2.</span><span class="sxs-lookup"><span data-stu-id="73160-156">The default namespace is root/cimv2.</span></span> <span data-ttu-id="73160-157">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="73160-157">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="73160-158">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="73160-158">-OperationTimeoutSec</span></span>

<span data-ttu-id="73160-159">Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet.</span><span class="sxs-lookup"><span data-stu-id="73160-159">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="73160-160">Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="73160-160">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="73160-161">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="73160-161">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="73160-162">-PassThru</span><span class="sxs-lookup"><span data-stu-id="73160-162">-PassThru</span></span>

<span data-ttu-id="73160-163">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="73160-163">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="73160-164">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="73160-164">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="73160-165">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="73160-165">-Property</span></span>

<span data-ttu-id="73160-166">Gibt die Eigenschaften der CIM-Instanz als Hash Tabelle an (unter Verwendung von Name-Wert-Paaren).</span><span class="sxs-lookup"><span data-stu-id="73160-166">Specifies the properties of the CIM instance as a hash table (using name-value pairs).</span></span> <span data-ttu-id="73160-167">Nur die Eigenschaften, die mit diesem Parameter angegeben werden, werden geändert.</span><span class="sxs-lookup"><span data-stu-id="73160-167">Only the properties specified using this parameter are changed.</span></span> <span data-ttu-id="73160-168">Andere Eigenschaften der CIM-Instanz werden nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="73160-168">Other properties of the CIM instance are not changed.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet, QuerySessionSet, QueryComputerSet
Aliases: Arguments

Required: True (QuerySessionSet, QueryComputerSet), False (CimInstanceComputerSet, CimInstanceSessionSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="73160-169">-Query</span><span class="sxs-lookup"><span data-stu-id="73160-169">-Query</span></span>

<span data-ttu-id="73160-170">Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt wird, um CIM-Instanzen abzurufen, für die das Cmdlet ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="73160-170">Specifies a query to run on the CIM server to retrieve CIM instances on which to run the cmdlet.</span></span> <span data-ttu-id="73160-171">Sie können den Abfrage Dialekt mithilfe des querydialekt-Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="73160-171">You can specify the query dialect using the QueryDialect parameter.</span></span>

<span data-ttu-id="73160-172">Wenn der angegebene Wert doppelte Anführungszeichen ( `"` ), einfache Anführungszeichen ( `'` ) oder einen umgekehrten Schrägstrich ( `\` ) enthält, müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich () vorangestellt werden `\` .</span><span class="sxs-lookup"><span data-stu-id="73160-172">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="73160-173">Wenn der angegebene Wert den WQL **like** -Operator verwendet, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern ( `[]` ) einschließen: Prozent ( `%` ), Unterstrich ( `_` ) oder öffnende eckige Klammer ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="73160-173">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="73160-174">-Querydialekt</span><span class="sxs-lookup"><span data-stu-id="73160-174">-QueryDialect</span></span>

<span data-ttu-id="73160-175">Gibt die Abfragesprache an, die für den Abfrage Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="73160-175">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="73160-176">Die zulässigen Werte für diesen Parameter sind: **WQL** oder **CQL**.</span><span class="sxs-lookup"><span data-stu-id="73160-176">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="73160-177">Der Standardwert ist **WQL**.</span><span class="sxs-lookup"><span data-stu-id="73160-177">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="73160-178">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="73160-178">-ResourceUri</span></span>

<span data-ttu-id="73160-179">Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="73160-179">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="73160-180">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="73160-180">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="73160-181">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="73160-181">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="73160-182">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="73160-182">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="73160-183">Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.</span><span class="sxs-lookup"><span data-stu-id="73160-183">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="73160-184">ResourceUri kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der Computername-Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt.</span><span class="sxs-lookup"><span data-stu-id="73160-184">ResourceURI can only be used with CIM sessions created using the WSMan protocol, or when specifying the ComputerName parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="73160-185">Wenn Sie diesen Parameter ohne Angabe des Computername-Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie eine Fehlermeldung, da das DCOM-Protokoll den resourceUri-Parameter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="73160-185">If you specify this parameter without specifying the ComputerName parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the ResourceURI parameter.</span></span>

<span data-ttu-id="73160-186">Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="73160-186">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="73160-187">-Confirm</span><span class="sxs-lookup"><span data-stu-id="73160-187">-Confirm</span></span>

<span data-ttu-id="73160-188">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="73160-188">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="73160-189">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="73160-189">-WhatIf</span></span>

<span data-ttu-id="73160-190">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73160-190">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="73160-191">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="73160-191">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="73160-192">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="73160-192">CommonParameters</span></span>

<span data-ttu-id="73160-193">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="73160-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="73160-194">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="73160-194">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="73160-195">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="73160-195">INPUTS</span></span>

### <span data-ttu-id="73160-196">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="73160-196">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="73160-197">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="73160-197">OUTPUTS</span></span>

### <span data-ttu-id="73160-198">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="73160-198">Microsoft.Management.Infrastructure.CimInstance</span></span>

<span data-ttu-id="73160-199">Wenn der **passthru** -Parameter angegeben wird, gibt dieses Cmdlet ein geändertes CIM-Instanzobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="73160-199">When the **Passthru** parameter is specified, this cmdlet returns a modified CIM instance object.</span></span>

## <span data-ttu-id="73160-200">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="73160-200">NOTES</span></span>

## <span data-ttu-id="73160-201">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="73160-201">RELATED LINKS</span></span>

[<span data-ttu-id="73160-202">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="73160-202">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="73160-203">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="73160-203">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="73160-204">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="73160-204">Remove-CimInstance</span></span>](remove-ciminstance.md)

