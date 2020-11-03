---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/test-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DscConfiguration
ms.openlocfilehash: 25c8bc61976ce3940e0b9bd949fa3ee60728450d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213575"
---
# <span data-ttu-id="a38c3-103">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a38c3-103">Test-DscConfiguration</span></span>

## <span data-ttu-id="a38c3-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a38c3-104">SYNOPSIS</span></span>
<span data-ttu-id="a38c3-105">Testet, ob die tatsächliche Konfiguration auf den Knoten mit der gewünschten Konfiguration übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a38c3-105">Tests whether the actual configuration on the nodes matches the desired configuration.</span></span>

## <span data-ttu-id="a38c3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a38c3-106">SYNTAX</span></span>

### <span data-ttu-id="a38c3-107">Computernameset (Standard)</span><span class="sxs-lookup"><span data-stu-id="a38c3-107">ComputerNameSet (Default)</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Detailed] [<CommonParameters>]
```

### <span data-ttu-id="a38c3-108">Computernameandpathset</span><span class="sxs-lookup"><span data-stu-id="a38c3-108">ComputerNameAndPathSet</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="a38c3-109">Computernameandreferenceconfigurationset</span><span class="sxs-lookup"><span data-stu-id="a38c3-109">ComputerNameAndReferenceConfigurationSet</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] -ReferenceConfiguration <String> [<CommonParameters>]
```

### <span data-ttu-id="a38c3-110">Cimsessionandpathset</span><span class="sxs-lookup"><span data-stu-id="a38c3-110">CimSessionAndPathSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Path] <String>
 [<CommonParameters>]
```

### <span data-ttu-id="a38c3-111">Cimsessionandreferenceconfigurationset</span><span class="sxs-lookup"><span data-stu-id="a38c3-111">CimSessionAndReferenceConfigurationSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob]
 -ReferenceConfiguration <String> [<CommonParameters>]
```

### <span data-ttu-id="a38c3-112">Cimsessionset</span><span class="sxs-lookup"><span data-stu-id="a38c3-112">CimSessionSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Detailed]
 [<CommonParameters>]
```

## <span data-ttu-id="a38c3-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a38c3-113">DESCRIPTION</span></span>
<span data-ttu-id="a38c3-114">Das Cmdlet **Test-DscConfiguration** testet, ob die tatsächliche Konfiguration auf den Knoten mit der gewünschten Konfiguration übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a38c3-114">The **Test-DscConfiguration** cmdlet tests whether the actual configuration on the nodes matches the desired configuration.</span></span>
<span data-ttu-id="a38c3-115">Geben Sie an, für welche Computerkonfigurationen mithilfe von Computernamen oder Common Information Model (CIM)-Sitzungen getestet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a38c3-115">Specify which computers for which you want to test configurations by using computer names or Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="a38c3-116">Wenn Sie keinen Zielcomputer angeben, testet das Cmdlet die Konfiguration des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="a38c3-116">If you do not specify a target computer, the cmdlet tests configuration of the local computer.</span></span>

<span data-ttu-id="a38c3-117">Wenn die gewünschte und die tatsächliche Konfiguration entsprechen, gibt das Cmdlet den Zeichen folgen Wert "true" zurück.</span><span class="sxs-lookup"><span data-stu-id="a38c3-117">If the desired and actual configurations match, the cmdlet returns a string value of 'True'.</span></span>
<span data-ttu-id="a38c3-118">Andernfalls wird der Zeichen folgen Wert "false" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a38c3-118">Otherwise, it returns a string value of 'False'.</span></span>

## <span data-ttu-id="a38c3-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a38c3-119">EXAMPLES</span></span>

### <span data-ttu-id="a38c3-120">Beispiel 1: Test Konfiguration für den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="a38c3-120">Example 1: Test configuration for the local computer</span></span>

```
PS C:\> Test-DscConfiguration
```

<span data-ttu-id="a38c3-121">Dieser Befehl testet die Konfiguration für den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="a38c3-121">This command tests configuration for the local computer.</span></span>

### <span data-ttu-id="a38c3-122">Beispiel 2: Test Konfiguration für einen angegebenen Computer</span><span class="sxs-lookup"><span data-stu-id="a38c3-122">Example 2: Test configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Test-DscConfiguration -CimSession $Session
```

<span data-ttu-id="a38c3-123">In diesem Beispiel wird die Konfiguration von einem Computer von einer CIM-Sitzung angegebenen Computer getestet.</span><span class="sxs-lookup"><span data-stu-id="a38c3-123">This example test configuration from a computer specified by a CIM session.</span></span>
<span data-ttu-id="a38c3-124">Das Beispiel erstellt eine CIM-Sitzung für einen Computer namens Server01 zur Verwendung mit dem Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a38c3-124">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="a38c3-125">Erstellen Sie alternativ ein Array von CIM-Sitzungen, um das Cmdlet für mehrere angegebene Computer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="a38c3-125">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="a38c3-126">Der erste Befehl erstellt eine CIM-Sitzung mithilfe des Cmdlets **New-CimSession** und speichert dann das **CimSession** -Objekt in der Variable $Session.</span><span class="sxs-lookup"><span data-stu-id="a38c3-126">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="a38c3-127">Der Befehl fordert Sie zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="a38c3-127">The command prompts you for a password.</span></span>
<span data-ttu-id="a38c3-128">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="a38c3-128">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="a38c3-129">Der zweite Befehl teste die Konfiguration für die Computer, die durch die **CimSession** -Objekte identifiziert werden, die in der Variable $Session gespeichert sind, in diesem Fall der Computer namens Server01.</span><span class="sxs-lookup"><span data-stu-id="a38c3-129">The second command tests configuration for the computers identified by the **CimSession** objects stored in the $Session variable, in this case, the computer named Server01.</span></span>

### <span data-ttu-id="a38c3-130">Beispiel 3: Testen von Konfigurationen mit detaillierten Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a38c3-130">Example 3: Test configurations with detailed results</span></span>

```
PS C:\> Test-DscConfiguration -ComputerName "Server01", "Server02", "Server03" -Detailed
```

<span data-ttu-id="a38c3-131">Dieser Befehl testet Konfigurationen für eine Reihe von Computern, die mit dem Parameter " *Computername* " angegeben wurden, und gibt ausführliche Informationen zurück, die den Gesamtstatus, Ressourcen im gewünschten Zustand, Ressourcen, die sich nicht im gewünschten Zustand befinden, und den Computernamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a38c3-131">This command tests configurations for a set of computers specified by the *ComputerName* parameter and returns detailed information that includes the overall state, resources that are in the desired state, resources that are not in the desired state and computer name.</span></span>

### <span data-ttu-id="a38c3-132">Beispiel 4: in einem Ordner angegebene Test Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a38c3-132">Example 4: Test configurations specified in a folder</span></span>

```
PS C:\> Test-DscConfiguration -Path "C:\Dsc\Configurations"
```

<span data-ttu-id="a38c3-133">Mit diesem Befehl werden Konfigurationen getestet, die in einem durch den *path* -Parameter angegebenen Ordner definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a38c3-133">This command tests configurations that are defined in a folder specified by the *Path* parameter.</span></span>
<span data-ttu-id="a38c3-134">Die Konfigurationen werden für eine Gruppe von Computern getestet, die jeweils durch den Dateinamen der Konfigurationsdatei identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a38c3-134">The configurations are tested against a set of computers, each identified by the file name of the configuration file.</span></span>

### <span data-ttu-id="a38c3-135">Beispiel 5: in einer Datei angegebene Test Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a38c3-135">Example 5: Test configurations specified in a file</span></span>

```
PS C:\> Test-DscConfiguration -ReferenceConfiguration "C:\Dsc\Configurations\WebServer.mof" -ComputerName "Server01", "Server02", "Server03"
```

<span data-ttu-id="a38c3-136">Mit diesem Befehl wird eine in einer Datei definierte Konfiguration für eine Gruppe von Computern getestet, die durch den *Computername* -Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a38c3-136">This command tests a configuration defined in a file against a set of computers specified by the *ComputerName* parameter.</span></span>

## <span data-ttu-id="a38c3-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a38c3-137">PARAMETERS</span></span>

### <span data-ttu-id="a38c3-138">-AsJob</span><span class="sxs-lookup"><span data-stu-id="a38c3-138">-AsJob</span></span>
<span data-ttu-id="a38c3-139">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="a38c3-139">Indicates that this cmdlet runs the command as a background job.</span></span>

<span data-ttu-id="a38c3-140">Wenn Sie den *AsJob* -Parameter angeben, gibt der Befehl ein Objekt zurück, das den Auftrag darstellt, und zeigt dann die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="a38c3-140">If you specify the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span>
<span data-ttu-id="a38c3-141">Sie können die Arbeit in der Sitzung fortsetzen, bis der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a38c3-141">You can continue to work in the session until the job finishes.</span></span>
<span data-ttu-id="a38c3-142">Der Auftrag wird auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a38c3-142">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="a38c3-143">Um den Auftrag zu verwalten, verwenden Sie die Job-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a38c3-143">To manage the job, use the Job cmdlets.</span></span>
<span data-ttu-id="a38c3-144">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="a38c3-144">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="a38c3-145">Um diesen Parameter verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein. unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie Windows PowerShell mit der Option als Administrator ausführen öffnen.</span><span class="sxs-lookup"><span data-stu-id="a38c3-145">To use this parameter, the local and remote computers must be configured for remoting, and on Windows Vista and later versions of the Windows operating system, you must open Windows PowerShell with the Run as administrator option.</span></span>
<span data-ttu-id="a38c3-146">Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a38c3-146">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="a38c3-147">Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a38c3-147">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="a38c3-148">-CimSession</span><span class="sxs-lookup"><span data-stu-id="a38c3-148">-CimSession</span></span>
<span data-ttu-id="a38c3-149">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="a38c3-149">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="a38c3-150">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".</span><span class="sxs-lookup"><span data-stu-id="a38c3-150">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="a38c3-151">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="a38c3-151">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndReferenceConfigurationSet, CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a38c3-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="a38c3-152">-ComputerName</span></span>
<span data-ttu-id="a38c3-153">Gibt ein Array von Computernamen an, auf denen dieses Cmdlet die Konfiguration testet.</span><span class="sxs-lookup"><span data-stu-id="a38c3-153">Specifies an array of computer names on which this cmdlet tests the configuration.</span></span>
<span data-ttu-id="a38c3-154">Mit dem-Cmdlet wird das Konfigurations Dokument an dem durch den *path* -Parameter angegebenen Speicherort auf diese Computer getestet.</span><span class="sxs-lookup"><span data-stu-id="a38c3-154">The cmdlet tests the configuration document in the location specified by the *Path* parameter to these computers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a38c3-155">-Credential</span><span class="sxs-lookup"><span data-stu-id="a38c3-155">-Credential</span></span>
<span data-ttu-id="a38c3-156">Gibt einen Benutzernamen und ein Kennwort als ein **PSCredential** -Objekt für den Zielcomputer an.</span><span class="sxs-lookup"><span data-stu-id="a38c3-156">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="a38c3-157">Zum Abrufen eines **PSCredential** -Objekts verwenden Sie das Get-Credential-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a38c3-157">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="a38c3-158">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="a38c3-158">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a38c3-159">-Detailed</span><span class="sxs-lookup"><span data-stu-id="a38c3-159">-Detailed</span></span>
<span data-ttu-id="a38c3-160">Gibt an, dass dieses Cmdlet ein detailliertes Ergebnis des Vergleichs des Konfigurations Dokuments mit dem gewünschten Zustand der Knoten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a38c3-160">Indicates that this cmdlet returns a detailed result of comparing the configuration document with the desired state of the nodes.</span></span>
<span data-ttu-id="a38c3-161">Das Ergebnis umfasst Informationen wie den Gesamtstatus, Ressourcen, die sich im gewünschten Zustand befinden, Ressourcen, die sich nicht im gewünschten Zustand befinden, und den Computernamen.</span><span class="sxs-lookup"><span data-stu-id="a38c3-161">The result includes information such as overall state, resources that are in the desired state, resources that are not in desired state, and computer name.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameSet, CimSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a38c3-162">-Path</span><span class="sxs-lookup"><span data-stu-id="a38c3-162">-Path</span></span>
<span data-ttu-id="a38c3-163">Gibt den Pfad eines Ordners an, der Konfigurations Dokument Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="a38c3-163">Specifies the path of a folder that contains configuration document files.</span></span>
<span data-ttu-id="a38c3-164">Das Cmdlet testet die Konfiguration mit dem gewünschten Zustand der Computer, die durch den Parameter " *Computername* " oder " *cimsession* " angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a38c3-164">The cmdlet tests the configuration against the desired state of computers specified by the *ComputerName* or *CimSession* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a38c3-165">-Referenceconfiguration</span><span class="sxs-lookup"><span data-stu-id="a38c3-165">-ReferenceConfiguration</span></span>
<span data-ttu-id="a38c3-166">Gibt den Pfad der Konfigurations Dokument Datei an.</span><span class="sxs-lookup"><span data-stu-id="a38c3-166">Specifies the path of the configuration document file.</span></span>
<span data-ttu-id="a38c3-167">Dieses Cmdlet testet die Konfiguration mit dem tatsächlichen Status der Computer, die durch den Parameter " *Computername* " oder " *cimsession* " angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a38c3-167">This cmdlet tests the configuration against the actual state of computers specified by the *ComputerName* or *CimSession* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndReferenceConfigurationSet, CimSessionAndReferenceConfigurationSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a38c3-168">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="a38c3-168">-ThrottleLimit</span></span>
<span data-ttu-id="a38c3-169">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="a38c3-169">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="a38c3-170">Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a38c3-170">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="a38c3-171">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="a38c3-171">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a38c3-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a38c3-172">CommonParameters</span></span>
<span data-ttu-id="a38c3-173">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a38c3-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a38c3-174">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a38c3-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a38c3-175">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a38c3-175">INPUTS</span></span>

## <span data-ttu-id="a38c3-176">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a38c3-176">OUTPUTS</span></span>

## <span data-ttu-id="a38c3-177">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a38c3-177">NOTES</span></span>

## <span data-ttu-id="a38c3-178">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a38c3-178">RELATED LINKS</span></span>

[<span data-ttu-id="a38c3-179">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="a38c3-179">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="a38c3-180">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a38c3-180">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="a38c3-181">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="a38c3-181">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="a38c3-182">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a38c3-182">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="a38c3-183">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a38c3-183">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)
