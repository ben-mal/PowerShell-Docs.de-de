---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-ciminstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimInstance
ms.openlocfilehash: f236956b1da5f9632ff163cbf8a818bf190fd29a
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218324"
---
# <span data-ttu-id="e4953-103">Remove-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e4953-103">Remove-CimInstance</span></span>

## <span data-ttu-id="e4953-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e4953-104">SYNOPSIS</span></span>
<span data-ttu-id="e4953-105">Entfernt eine CIM-Instanz von einem Computer.</span><span class="sxs-lookup"><span data-stu-id="e4953-105">Removes a CIM instance from a computer.</span></span>

## <span data-ttu-id="e4953-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e4953-106">SYNTAX</span></span>

### <span data-ttu-id="e4953-107">Ciminstancecomputerset (Standard)</span><span class="sxs-lookup"><span data-stu-id="e4953-107">CimInstanceComputerSet (Default)</span></span>

```
Remove-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e4953-108">Ciminstancesessionset</span><span class="sxs-lookup"><span data-stu-id="e4953-108">CimInstanceSessionSet</span></span>

```
Remove-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e4953-109">Querysessionset</span><span class="sxs-lookup"><span data-stu-id="e4953-109">QuerySessionSet</span></span>

```
Remove-CimInstance -CimSession <CimSession[]> [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="e4953-110">Querycomputerset</span><span class="sxs-lookup"><span data-stu-id="e4953-110">QueryComputerSet</span></span>

```
Remove-CimInstance [-ComputerName <String[]>] [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="e4953-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e4953-111">DESCRIPTION</span></span>

<span data-ttu-id="e4953-112">Mit diesem Cmdlet wird eine CIM-Instanz von einem CIM-Server entfernt.</span><span class="sxs-lookup"><span data-stu-id="e4953-112">This cmdlet removes a CIM instance from a CIM server.</span></span> <span data-ttu-id="e4953-113">Sie können die CIM-Instanz angeben, die entfernt werden soll, indem Sie entweder ein CIM-Instanzobjekt verwenden, das vom `Get-CimInstance` Cmdlet abgerufen wurde, oder eine Abfrage angeben.</span><span class="sxs-lookup"><span data-stu-id="e4953-113">You can specify the CIM instance to remove by using either a CIM instance object retrieved by the `Get-CimInstance` cmdlet, or by specifying a query.</span></span>

<span data-ttu-id="e4953-114">Wenn der **Inputobject** -Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:</span><span class="sxs-lookup"><span data-stu-id="e4953-114">If the **InputObject** parameter is not specified, the cmdlet works in one of the following ways:</span></span>

- <span data-ttu-id="e4953-115">Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="e4953-115">If neither the **ComputerName** parameter nor the **CimSession** parameter is specified, then this cmdlet works on local Windows Management Instrumentation (WMI) using a Component Object Model (COM) session.</span></span>
- <span data-ttu-id="e4953-116">Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4953-116">If either the **ComputerName** parameter or the **CimSession** parameter is specified, then this cmdlet works against the CIM server specified by either the **ComputerName** parameter or the **CimSession** parameter.</span></span>

## <span data-ttu-id="e4953-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e4953-117">EXAMPLES</span></span>

### <span data-ttu-id="e4953-118">Beispiel 1: Entfernen der CIM-Instanz</span><span class="sxs-lookup"><span data-stu-id="e4953-118">Example 1: Remove the CIM instance</span></span>

<span data-ttu-id="e4953-119">In diesem Beispiel wird der **Query** -Parameter verwendet, um CIM-Instanzen aus der Klasse mit dem Namen **Win32_Environment** zu entfernen, die mit der Zeichenfolge **TestVar** beginnen.</span><span class="sxs-lookup"><span data-stu-id="e4953-119">This example use the **Query** parameter to remove CIM instances from the class named **Win32_Environment** that start with the character string **testvar** .</span></span>

```powershell
Remove-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"'
```

### <span data-ttu-id="e4953-120">Beispiel 2: Entfernen der CIM-Instanz mithilfe des CIM-Instanzobjekts</span><span class="sxs-lookup"><span data-stu-id="e4953-120">Example 2: Remove the CIM instance using CIM instance object</span></span>

<span data-ttu-id="e4953-121">In diesem Beispiel werden die CIM-Instanzobjekte, die vom **Abfrage** Parameter gefiltert werden, abgerufen und `$var` mit dem-Cmdlet in der Variablen mit dem Namen gespeichert `Get-CimInstance` .</span><span class="sxs-lookup"><span data-stu-id="e4953-121">This example retrieves the CIM instance objects filtered by the **Query** parameter and stores them in variable named `$var` using the `Get-CimInstance` cmdlet.</span></span> <span data-ttu-id="e4953-122">Der Inhalt der Variablen wird dann an das `Remove-CimInstance` Cmdlet übergeben, das die CIM-Instanzen entfernt.</span><span class="sxs-lookup"><span data-stu-id="e4953-122">The contents of the variable are then passed to the `Remove-CimInstance` cmdlet, which removes the CIM instances.</span></span>

```powershell
notepad.exe
$var = Get-CimInstance -Query 'Select * from Win32_Process where name LIKE "notepad%"'
Remove-CimInstance -InputObject $var
```

## <span data-ttu-id="e4953-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e4953-123">PARAMETERS</span></span>

### <span data-ttu-id="e4953-124">-CimSession</span><span class="sxs-lookup"><span data-stu-id="e4953-124">-CimSession</span></span>

<span data-ttu-id="e4953-125">Führt den Befehl mit der angegebenen CIM-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="e4953-125">Runs the command using the specified CIM session.</span></span> <span data-ttu-id="e4953-126">Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, mit dem die CIM-Sitzung erstellt oder abgerufen wird, z `New-CimSession` `Get-CimSession` . b. die Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="e4953-126">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the `New-CimSession` or `Get-CimSession` cmdlets.</span></span> <span data-ttu-id="e4953-127">Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="e4953-127">For more information, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="e4953-128">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="e4953-128">-ComputerName</span></span>

<span data-ttu-id="e4953-129">Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="e4953-129">Specifies the name of the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="e4953-130">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) oder einen NetBIOS-Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="e4953-130">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

<span data-ttu-id="e4953-131">Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="e4953-131">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="e4953-132">Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.</span><span class="sxs-lookup"><span data-stu-id="e4953-132">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="e4953-133">Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet eine Verbindung mit einer CIM-Sitzung eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="e4953-133">If multiple operations are being performed on the same computer, connecting using a CIM session gives better performance.</span></span>

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

### <span data-ttu-id="e4953-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e4953-134">-InputObject</span></span>

<span data-ttu-id="e4953-135">Gibt ein CIM-Instanzobjekt an, das vom CIM-Server entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e4953-135">Specifies a CIM instance object to be removed from the CIM server.</span></span> <span data-ttu-id="e4953-136">Das an das Cmdlet weiter gegebene Objekt wird nicht geändert, sondern nur die Instanz auf dem CIM-Server.</span><span class="sxs-lookup"><span data-stu-id="e4953-136">The object passed to the cmdlet is not changed, only the instance in the CIM server is removed.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e4953-137">-Namespace</span><span class="sxs-lookup"><span data-stu-id="e4953-137">-Namespace</span></span>

<span data-ttu-id="e4953-138">Gibt den Namespace für den CIM-Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="e4953-138">Specifies the namespace for the CIM operation.</span></span> <span data-ttu-id="e4953-139">Der Standard Namespace ist **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="e4953-139">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="e4953-140">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e4953-140">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4953-141">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="e4953-141">-OperationTimeoutSec</span></span>

<span data-ttu-id="e4953-142">Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet.</span><span class="sxs-lookup"><span data-stu-id="e4953-142">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="e4953-143">Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4953-143">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="e4953-144">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e4953-144">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="e4953-145">-Query</span><span class="sxs-lookup"><span data-stu-id="e4953-145">-Query</span></span>

<span data-ttu-id="e4953-146">Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e4953-146">Specifies a query to run on the CIM server.</span></span> <span data-ttu-id="e4953-147">Sie können den Abfrage Dialekt mithilfe des **querydialekt** -Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="e4953-147">You can specify the query dialect using the **QueryDialect** parameter.</span></span>

<span data-ttu-id="e4953-148">Wenn der angegebene Wert doppelte Anführungszeichen ( `"` ), einfache Anführungszeichen ( `'` ) oder einen umgekehrten Schrägstrich ( `\` ) enthält, müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich () vorangestellt werden `\` .</span><span class="sxs-lookup"><span data-stu-id="e4953-148">If the value specified contains double quotes (`"`), single quotes (`'`), or a backslash (`\`), you must escape those characters by prefixing them with the backslash (`\`) character.</span></span> <span data-ttu-id="e4953-149">Wenn der angegebene Wert den WQL Like-Operator verwendet, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern ( `[]` ) einschließen: Prozent ( `%` ), Unterstrich ( `_` ) oder öffnende eckige Klammer ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="e4953-149">If the value specified uses the WQL LIKE operator, then you must escape the following characters by enclosing them in square brackets (`[]`): percent (`%`), underscore (`_`), or opening square bracket (`[`).</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4953-150">-Querydialekt</span><span class="sxs-lookup"><span data-stu-id="e4953-150">-QueryDialect</span></span>

<span data-ttu-id="e4953-151">Gibt die Abfragesprache an, die für den Abfrage Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e4953-151">Specifies the query language used for the Query parameter.</span></span> <span data-ttu-id="e4953-152">Die zulässigen Werte für diesen Parameter sind: **WQL** oder **CQL**.</span><span class="sxs-lookup"><span data-stu-id="e4953-152">The acceptable values for this parameter are: **WQL** or **CQL**.</span></span> <span data-ttu-id="e4953-153">Der Standardwert ist **WQL**.</span><span class="sxs-lookup"><span data-stu-id="e4953-153">The default value is **WQL**.</span></span>

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4953-154">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="e4953-154">-ResourceUri</span></span>

<span data-ttu-id="e4953-155">Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="e4953-155">Specifies the resource uniform resource identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="e4953-156">Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="e4953-156">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="e4953-157">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="e4953-157">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="e4953-158">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e4953-158">For example:</span></span>

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

<span data-ttu-id="e4953-159">Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.</span><span class="sxs-lookup"><span data-stu-id="e4953-159">By default, if you do not specify this parameter, the DMTF standard resource URI `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.</span></span>

<span data-ttu-id="e4953-160">ResourceUri kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der Computername-Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt.</span><span class="sxs-lookup"><span data-stu-id="e4953-160">ResourceURI can only be used with CIM sessions created using the WSMan protocol, or when specifying the ComputerName parameter, which creates a CIM session using WSMan.</span></span> <span data-ttu-id="e4953-161">Wenn Sie diesen Parameter ohne Angabe des Computername-Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie eine Fehlermeldung, da das DCOM-Protokoll den resourceUri-Parameter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e4953-161">If you specify this parameter without specifying the ComputerName parameter, or if you specify a CIM session created using DCOM protocol, you get an error, because the DCOM protocol does not support the ResourceURI parameter.</span></span>

<span data-ttu-id="e4953-162">Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e4953-162">If both the **ResourceUri** parameter and the **Filter** parameter are specified, the **Filter** parameter is ignored.</span></span>

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

### <span data-ttu-id="e4953-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e4953-163">-Confirm</span></span>

<span data-ttu-id="e4953-164">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="e4953-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e4953-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e4953-165">-WhatIf</span></span>

<span data-ttu-id="e4953-166">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e4953-166">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e4953-167">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e4953-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e4953-168">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e4953-168">CommonParameters</span></span>

<span data-ttu-id="e4953-169">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e4953-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4953-170">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e4953-170">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e4953-171">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e4953-171">INPUTS</span></span>

### <span data-ttu-id="e4953-172">Keine</span><span class="sxs-lookup"><span data-stu-id="e4953-172">None</span></span>

<span data-ttu-id="e4953-173">Dieses Cmdlet akzeptiert keine Eingabe Objekte.</span><span class="sxs-lookup"><span data-stu-id="e4953-173">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="e4953-174">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e4953-174">OUTPUTS</span></span>

### <span data-ttu-id="e4953-175">Keine</span><span class="sxs-lookup"><span data-stu-id="e4953-175">None</span></span>

<span data-ttu-id="e4953-176">Dieses Cmdlet erzeugt keine Ausgaben.</span><span class="sxs-lookup"><span data-stu-id="e4953-176">This cmdlet produces no outputs.</span></span>

## <span data-ttu-id="e4953-177">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e4953-177">NOTES</span></span>

## <span data-ttu-id="e4953-178">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e4953-178">RELATED LINKS</span></span>

[<span data-ttu-id="e4953-179">New-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e4953-179">New-CimInstance</span></span>](New-CimInstance.md)

[<span data-ttu-id="e4953-180">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e4953-180">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="e4953-181">Set-CimInstance</span><span class="sxs-lookup"><span data-stu-id="e4953-181">Set-CimInstance</span></span>](Set-CimInstance.md)

