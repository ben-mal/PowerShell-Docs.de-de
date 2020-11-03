---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/set-ciminstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CimInstance
ms.openlocfilehash: 7f44ddf52c2ad3ce68c5eccf0e8f952a0fa1873e
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218095"
---
# <span data-ttu-id="aef32-103">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="aef32-103">Set-CimInstance</span></span>

## <span data-ttu-id="aef32-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="aef32-104">SYNOPSIS</span></span>
<span data-ttu-id="aef32-105">Ändert eine CIM-Instanz auf einem CIM-Server durch Aufrufen der modifyinstance-Methode der CIM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="aef32-105">Modifies a CIM instance on a CIM server by calling the ModifyInstance method of the CIM class.</span></span>

## <span data-ttu-id="aef32-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aef32-106">SYNTAX</span></span>

### <span data-ttu-id="aef32-107">Ciminstancecomputerset (Standard)</span><span class="sxs-lookup"><span data-stu-id="aef32-107">CimInstanceComputerSet (Default)</span></span>

```
Set-CimInstance [-ComputerName <String[]>] [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="aef32-108">Ciminstancesessionset</span><span class="sxs-lookup"><span data-stu-id="aef32-108">CimInstanceSessionSet</span></span>

```
Set-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="aef32-109">Querysessionset</span><span class="sxs-lookup"><span data-stu-id="aef32-109">QuerySessionSet</span></span>

```
Set-CimInstance -CimSession <CimSession[]> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="aef32-110">Querycomputerset</span><span class="sxs-lookup"><span data-stu-id="aef32-110">QueryComputerSet</span></span>

```
Set-CimInstance [-ComputerName <String[]>] [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="aef32-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aef32-111">DESCRIPTION</span></span>

<span data-ttu-id="aef32-112">Dieses Cmdlet ändert eine CIM-Instanz auf einem CIM-Server.</span><span class="sxs-lookup"><span data-stu-id="aef32-112">This cmdlet modifies a CIM instance on a CIM server.</span></span>

<span data-ttu-id="aef32-113">Wenn der **Inputobject** -Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="aef32-113">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="aef32-114">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="aef32-114">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="aef32-115">Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="aef32-115">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

<span data-ttu-id="aef32-116">Wenn der **Inputobject** -Parameter angegeben wird, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="aef32-116">If the **InputObject** parameter is specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="aef32-117">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, verwendet dieses Cmdlet die CIM-Sitzung oder den Computernamen aus dem Eingabe Objekt.</span><span class="sxs-lookup"><span data-stu-id="aef32-117">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet uses the CIM session or computer name from the input object.</span></span>
- <span data-ttu-id="aef32-118">Wenn der **Computername** -Parameter oder der **cimsession** -Parameter angegeben wird, verwendet dieses Cmdlet entweder den Wert des **cimsession** -Parameter Werts oder den Wert des **Computername** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="aef32-118">If the either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet uses the either the **CimSession** parameter value or **ComputerName** parameter value.</span></span> <span data-ttu-id="aef32-119">Dies ist nicht sehr üblich.</span><span class="sxs-lookup"><span data-stu-id="aef32-119">This is not very common.</span></span>

## <span data-ttu-id="aef32-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="aef32-120">EXAMPLES</span></span>

### <span data-ttu-id="aef32-121">Beispiel 1: Festlegen der CIM-Instanz</span><span class="sxs-lookup"><span data-stu-id="aef32-121">Example 1: Set the CIM instance</span></span>

<span data-ttu-id="aef32-122">In diesem Beispiel wird der Wert der **VariableValue** -Eigenschaft mithilfe des **Abfrage** Parameters auf **ABCD** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="aef32-122">This example sets the value of the **VariableValue** property to **abcd** using the **Query** parameter.</span></span> <span data-ttu-id="aef32-123">Sie können-Instanzen ändern, die mit einer WQL-Abfrage (Windows-Verwaltungsinstrumentation Query Language) übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="aef32-123">You can modify instances matching a Windows Management Instrumentation Query Language (WQL) query.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"}
```

### <span data-ttu-id="aef32-124">Beispiel 2: Festlegen der CIM-Instanzeigenschaft mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="aef32-124">Example 2: Set the CIM instance property using pipeline</span></span>

<span data-ttu-id="aef32-125">In diesem Beispiel wird das CIM-Instanzobjekt, das durch den **Abfrage** Parameter gefiltert wird, mithilfe des- `Get-CimInstance` Cmdlets abgerufen.</span><span class="sxs-lookup"><span data-stu-id="aef32-125">This example retrieves the CIM instance object filtered by the **Query** parameter using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="aef32-126">Das `Set-CimInstance` Cmdlet ändert den Wert der **VariableValue** -Eigenschaft in **ABCD**.</span><span class="sxs-lookup"><span data-stu-id="aef32-126">The `Set-CimInstance` cmdlet modifies the value of **VariableValue** property to **abcd**.</span></span>

```powershell
Get-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' |
  Set-CimInstance -Property @{VariableValue="abcd"}
```

### <span data-ttu-id="aef32-127">Beispiel 3: Festlegen der CIM-Instanzeigenschaft mithilfe des Eingabe Objekts</span><span class="sxs-lookup"><span data-stu-id="aef32-127">Example 3: Set the CIM instance property using input object</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where Name="testvar"'
Set-CimInstance -InputObject $x -Property @{VariableValue="somevalue"} -PassThru
```

<span data-ttu-id="aef32-128">In diesem Beispiel werden die CIM-Instanzobjekte, die vom Abfrage Parameter in gefiltert werden, mithilfe von zu einer Variablen abgerufen `$x` `Get-CimInstance` und dann der Inhalt der Variablen an das `Set-CimInstance` Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="aef32-128">This example retrieves the CIM instance objects filtered by the Query parameter in to a variable `$x` using `Get-CimInstance`, and then passes the contents of the variable to the `Set-CimInstance` cmdlet.</span></span> <span data-ttu-id="aef32-129">`Set-CimInstance` ändert dann die **VariableValue** -Eigenschaft in " **someValue** ".</span><span class="sxs-lookup"><span data-stu-id="aef32-129">`Set-CimInstance` then modifies the **VariableValue** property to **somevalue**.</span></span> <span data-ttu-id="aef32-130">Da der **passthru** -Parameter verwendet wird, gibt dieses Beispiel ein geändertes CIM-Instanzobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="aef32-130">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

### <span data-ttu-id="aef32-131">Beispiel 4: Festlegen der CIM-Instanzeigenschaft</span><span class="sxs-lookup"><span data-stu-id="aef32-131">Example 4: Set the CIM instance property</span></span>

<span data-ttu-id="aef32-132">In diesem Beispiel wird das CIM-Instanzobjekt, das im- **Abfrage** Parameter angegeben ist `$x` , mithilfe des `Get-CimInstance` -Cmdlets in eine Variable abgerufen, und der **VariableValue** -Eigenschafts Wert des-Objekts wird geändert.</span><span class="sxs-lookup"><span data-stu-id="aef32-132">This example retrieves the CIM instance object that is specified in the **Query** parameter into a variable `$x` using the `Get-CimInstance` cmdlet, and changes the **VariableValue** property value of the object to change.</span></span> <span data-ttu-id="aef32-133">Das CIM-Instanzobjekt wird dann mithilfe des `Set-CimInstance` Cmdlets gespeichert.</span><span class="sxs-lookup"><span data-stu-id="aef32-133">The CIM instance object is then saved using the `Set-CimInstance` cmdlet.</span></span>
<span data-ttu-id="aef32-134">Da der **passthru** -Parameter verwendet wird, gibt dieses Beispiel ein geändertes CIM-Instanzobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="aef32-134">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where name="testvar"'
$x.VariableValue = "Change"
Set-CimInstance -CimInstance $x -PassThru
```

### <span data-ttu-id="aef32-135">Beispiel 5: Anzeigen der Liste der CIM-Instanzen, die mit WhatIf geändert werden sollen</span><span class="sxs-lookup"><span data-stu-id="aef32-135">Example 5: Show the list of CIM instances to modify using WhatIf</span></span>

<span data-ttu-id="aef32-136">In diesem Beispiel wird der allgemeine Parameter **WhatIf** verwendet, um anzugeben, dass die Änderung nicht durchgeführt werden soll, sondern nur, was geschehen würde, wenn dies geschehen wäre.</span><span class="sxs-lookup"><span data-stu-id="aef32-136">This example uses the common parameter **WhatIf** to specify that the modification should not be done, but only output what would happen if it were done.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -WhatIf
```

### <span data-ttu-id="aef32-137">Beispiel 6: Festlegen der CIM-Instanz nach der Bestätigung durch den Benutzer</span><span class="sxs-lookup"><span data-stu-id="aef32-137">Example 6: Set the CIM instance after confirmation from the user</span></span>

<span data-ttu-id="aef32-138">In diesem Beispiel wird der allgemeine Parameter **Confirm** verwendet, um anzugeben, dass die Änderung erst nach der Bestätigung durch den Benutzer vorgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="aef32-138">This example uses the common parameter **Confirm** to specify that the modification should be done only after confirmation from the user.</span></span>

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -Confirm
```

### <span data-ttu-id="aef32-139">Beispiel 7: Festlegen der erstellten CIM-Instanz</span><span class="sxs-lookup"><span data-stu-id="aef32-139">Example 7: Set the created CIM instance</span></span>

<span data-ttu-id="aef32-140">In diesem Beispiel wird mithilfe des-Cmdlets eine CIM-Instanz mit den angegebenen Eigenschaften erstellt `New-CimInstance` und der Inhalt in eine Variable abgerufen `$x` .</span><span class="sxs-lookup"><span data-stu-id="aef32-140">This example creates a CIM instance with the specified properties using the `New-CimInstance` cmdlet, and retrieves its contents in to a variable `$x`.</span></span> <span data-ttu-id="aef32-141">Die Variable wird dann an das `Set-CimInstance` Cmdlet übergeben, das den Wert der **VariableValue** -Eigenschaft in " **someValue** " ändert.</span><span class="sxs-lookup"><span data-stu-id="aef32-141">The variable is then passed to the `Set-CimInstance` cmdlet, which modifies the value of **VariableValue** property to **somevalue**.</span></span>
<span data-ttu-id="aef32-142">Da der **passthru** -Parameter verwendet wird, gibt dieses Beispiel ein geändertes CIM-Instanzobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="aef32-142">Because the **Passthru** parameter is used, This example returns a modified CIM instance object.</span></span>

```powershell
$x = New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";UserName="domain\user"} -Keys Name,UserName -ClientOnly
Set-CimInstance -CimInstance $x -Property @{VariableValue="somevalue"} -PassThru
```

## <span data-ttu-id="aef32-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aef32-143">PARAMETERS</span></span>

### <span data-ttu-id="aef32-144">-CimSession</span><span class="sxs-lookup"><span data-stu-id="aef32-144">-CimSession</span></span>

<span data-ttu-id="aef32-145">Führt die Cmdlets auf einem Remote Computer aus.</span><span class="sxs-lookup"><span data-stu-id="aef32-145">Runs the cmdlets on a remote computer.</span></span> <span data-ttu-id="aef32-146">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines- `New-CimSession` oder- `Get-CimSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="aef32-146">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: QuerySessionSet, CimInstanceSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="aef32-147">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="aef32-147">-ComputerName</span></span>

<span data-ttu-id="aef32-148">Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="aef32-148">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="aef32-149">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) oder einen NetBIOS-Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="aef32-149">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="aef32-150">Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.</span><span class="sxs-lookup"><span data-stu-id="aef32-150">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="aef32-151">Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="aef32-151">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="aef32-152">Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet eine Verbindung mit einer CIM-Sitzung eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="aef32-152">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

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

### <span data-ttu-id="aef32-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="aef32-153">-InputObject</span></span>

<span data-ttu-id="aef32-154">Gibt ein CIM-Instanzobjekt an, das als Eingabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aef32-154">Specifies a CIM instance object to use as input.</span></span>

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

### <span data-ttu-id="aef32-155">-Namespace</span><span class="sxs-lookup"><span data-stu-id="aef32-155">-Namespace</span></span>

<span data-ttu-id="aef32-156">Gibt den Namespace für den CIM-Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="aef32-156">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="aef32-157">Der Standard Namespace ist root/cimv2.</span><span class="sxs-lookup"><span data-stu-id="aef32-157">The default namespace is root/cimv2.</span></span> <span data-ttu-id="aef32-158">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="aef32-158">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

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

### <span data-ttu-id="aef32-159">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="aef32-159">-OperationTimeoutSec</span></span>

<span data-ttu-id="aef32-160">Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet.</span><span class="sxs-lookup"><span data-stu-id="aef32-160">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="aef32-161">Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="aef32-161">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="aef32-162">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="aef32-162">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="aef32-163">-PassThru</span><span class="sxs-lookup"><span data-stu-id="aef32-163">-PassThru</span></span>

<span data-ttu-id="aef32-164">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="aef32-164">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="aef32-165">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="aef32-165">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="aef32-166">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="aef32-166">-Property</span></span>

<span data-ttu-id="aef32-167">Gibt die Eigenschaften der CIM-Instanz als Hash Tabelle an (unter Verwendung von Name-Wert-Paaren).</span><span class="sxs-lookup"><span data-stu-id="aef32-167">Specifies the properties of the CIM instance as a hash table (using name-value pairs).</span></span> <span data-ttu-id="aef32-168">Nur die Eigenschaften, die mit diesem Parameter angegeben werden, werden geändert.</span><span class="sxs-lookup"><span data-stu-id="aef32-168">Only the properties specified using this parameter are changed.</span></span> <span data-ttu-id="aef32-169">Andere Eigenschaften der CIM-Instanz werden nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="aef32-169">Other properties of the CIM instance are not changed.</span></span>

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

### <span data-ttu-id="aef32-170">-Query</span><span class="sxs-lookup"><span data-stu-id="aef32-170">-Query</span></span>

<span data-ttu-id="aef32-171">Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt wird, um CIM-Instanzen abzurufen, für die das Cmdlet ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="aef32-171">Specifies a query to run on the CIM server to retrieve CIM instances on which to run the cmdlet.</span></span> <span data-ttu-id="aef32-172">Sie können den Abfrage Dialekt mithilfe des querydialekt-Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="aef32-172">You can specify the query dialect using the QueryDialect parameter.</span></span>

<span data-ttu-id="aef32-173">Wenn der angegebene Wert doppelte Anführungszeichen ( `"` ), einfache Anführungszeichen ( `'` ) oder einen umgekehrten Schrägstrich ( `\` ) enthält, müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich () vorangestellt werden `\` .</span><span class="sxs-lookup"><span data-stu-id="aef32-173">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="aef32-174">Wenn der angegebene Wert den WQL **like** -Operator verwendet, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern ( `[]` ) einschließen: Prozent ( `%` ), Unterstrich ( `_` ) oder öffnende eckige Klammer ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="aef32-174">If the value specified uses the WQL **LIKE** operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

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

### <span data-ttu-id="aef32-175">-Querydialekt</span><span class="sxs-lookup"><span data-stu-id="aef32-175">-QueryDialect</span></span>

<span data-ttu-id="aef32-176">Gibt die Abfragesprache an, die für den Abfrage Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aef32-176">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="aef32-177">Die zulässigen Werte für diesen Parameter sind: **WQL** oder **CQL**.</span><span class="sxs-lookup"><span data-stu-id="aef32-177">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="aef32-178">Der Standardwert ist **WQL**.</span><span class="sxs-lookup"><span data-stu-id="aef32-178">The default value is **WQL**.</span></span>

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

### <span data-ttu-id="aef32-179">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="aef32-179">-ResourceUri</span></span>

<span data-ttu-id="aef32-180">Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="aef32-180">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="aef32-181">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="aef32-181">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="aef32-182">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="aef32-182">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="aef32-183">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="aef32-183">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="aef32-184">Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.</span><span class="sxs-lookup"><span data-stu-id="aef32-184">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="aef32-185">ResourceUri kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der Computername-Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt.</span><span class="sxs-lookup"><span data-stu-id="aef32-185">ResourceURI can only be used with CIM sessions created using the WSMan protocol, or when specifying the ComputerName parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="aef32-186">Wenn Sie diesen Parameter ohne Angabe des Computername-Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie eine Fehlermeldung, da das DCOM-Protokoll den resourceUri-Parameter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aef32-186">If you specify this parameter without specifying the ComputerName parameter, or if you specify a CIM session created using DCOM protocol, you will get an error, because the DCOM protocol does not support the ResourceURI parameter.</span></span>

<span data-ttu-id="aef32-187">Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="aef32-187">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

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

### <span data-ttu-id="aef32-188">-Confirm</span><span class="sxs-lookup"><span data-stu-id="aef32-188">-Confirm</span></span>

<span data-ttu-id="aef32-189">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="aef32-189">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="aef32-190">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="aef32-190">-WhatIf</span></span>

<span data-ttu-id="aef32-191">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aef32-191">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="aef32-192">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aef32-192">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="aef32-193">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aef32-193">CommonParameters</span></span>

<span data-ttu-id="aef32-194">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aef32-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aef32-195">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="aef32-195">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="aef32-196">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="aef32-196">INPUTS</span></span>

### <span data-ttu-id="aef32-197">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="aef32-197">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="aef32-198">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="aef32-198">OUTPUTS</span></span>

### <span data-ttu-id="aef32-199">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="aef32-199">Microsoft.Management.Infrastructure.CimInstance</span></span>

<span data-ttu-id="aef32-200">Wenn der **passthru** -Parameter angegeben wird, gibt dieses Cmdlet ein geändertes CIM-Instanzobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="aef32-200">When the **Passthru** parameter is specified, this cmdlet returns a modified CIM instance object.</span></span>

## <span data-ttu-id="aef32-201">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="aef32-201">NOTES</span></span>

## <span data-ttu-id="aef32-202">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="aef32-202">RELATED LINKS</span></span>

[<span data-ttu-id="aef32-203">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="aef32-203">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="aef32-204">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="aef32-204">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="aef32-205">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="aef32-205">Remove-CimInstance</span></span>](remove-ciminstance.md)
