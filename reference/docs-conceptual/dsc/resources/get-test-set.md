---
ms.date: 07/08/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Get-Test-Set
ms.openlocfilehash: f7b7e947a85832365a783e40c25a25bfaa9fff8d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771514"
---
# <a name="get-test-set"></a><span data-ttu-id="9e759-103">Get-Test-Set</span><span class="sxs-lookup"><span data-stu-id="9e759-103">Get-Test-Set</span></span>

><span data-ttu-id="9e759-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="9e759-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="9e759-105">PowerShell Desired State Configuration ist um einen **Get**-, **Test**- und **Set**-Prozess herum konstruiert.</span><span class="sxs-lookup"><span data-stu-id="9e759-105">PowerShell Desired State Configuration is constructed around a **Get**, **Test**, and **Set** process.</span></span> <span data-ttu-id="9e759-106">Die DSC-[Ressourcen](resources.md) enthalten Methoden, um jeden dieser Vorgänge abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9e759-106">DSC [resources](resources.md) each contains methods to complete each of these operations.</span></span>
<span data-ttu-id="9e759-107">In einer [Konfiguration](../configurations/configurations.md) definieren Sie Ressourcenblöcke, um Schlüssel auszufüllen, die Parameter für **Get**-, **Test**- und **Set**-Methoden einer Ressource werden.</span><span class="sxs-lookup"><span data-stu-id="9e759-107">In a [Configuration](../configurations/configurations.md), you define resource blocks to fill in keys that become parameters for a resource's **Get**, **Test**, and **Set** methods.</span></span>

<span data-ttu-id="9e759-108">Dies ist die Syntax für einen **Service**-Ressourcenblock.</span><span class="sxs-lookup"><span data-stu-id="9e759-108">This is the syntax for a **Service** resource block.</span></span> <span data-ttu-id="9e759-109">Die **Service**-Ressource konfiguriert Windows-Dienste.</span><span class="sxs-lookup"><span data-stu-id="9e759-109">The **Service** resource configures Windows services.</span></span>

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

<span data-ttu-id="9e759-110">Die Parameterblöcke der **Get**-, **Test**- und **Set**-Methoden der **Service**-Ressource akzeptieren diese Werte.</span><span class="sxs-lookup"><span data-stu-id="9e759-110">The **Get**, **Test**, and **Set** methods of the **Service** resource will have parameter blocks that accept these values.</span></span>

```powershell
param
(
    [parameter(Mandatory = $true)]
    [ValidateNotNullOrEmpty()]
    [System.String]
    $Name,

    [System.String]
    [ValidateSet("Automatic", "Manual", "Disabled")]
    $StartupType,

    [System.String]
    [ValidateSet("LocalSystem", "LocalService", "NetworkService")]
    $BuiltInAccount,

    [System.Management.Automation.PSCredential]
    [ValidateNotNull()]
    $Credential,

    [System.String]
    [ValidateSet("Running", "Stopped")]
    $State="Running",

    [System.String]
    [ValidateNotNullOrEmpty()]
    $DisplayName,

    [System.String]
    [ValidateNotNullOrEmpty()]
    $Description,

    [System.String]
    [ValidateNotNullOrEmpty()]
    $Path,

    [System.String[]]
    [ValidateNotNullOrEmpty()]
    $Dependencies,

    [System.String]
    [ValidateSet("Present", "Absent")]
    $Ensure="Present"
)
```

> [!NOTE]
> <span data-ttu-id="9e759-111">Die zum Definieren der Ressource verwendete Sprache und Methode bestimmt, wie die **Get**-, **Test**- und **Set**-Methoden definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9e759-111">The language and method used to define the resource determines how the **Get**, **Test**, and **Set** methods will be defined.</span></span>

<span data-ttu-id="9e759-112">Da die **Service**-Ressource nur einen einzigen Schlüssel (`Name`) benötigt, könnte eine **Service**-Blockressource so einfach sein wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9e759-112">Because the **Service** resource only has one required key (`Name`), a **Service** block resource could be as simple as this:</span></span>

```powershell
Configuration TestConfig
{
    Import-DSCResource -Name Service
    Node localhost
    {
        Service "MyService"
        {
            Name = "Spooler"
        }
    }
}
```

<span data-ttu-id="9e759-113">Beim Kompilieren der obigen Konfiguration werden die Werte, die Sie für einen Schlüssel angeben, in der generierten `.mof`-Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9e759-113">When you compile the Configuration above, the values you specify for a key are stored in the `.mof` file that is generated.</span></span> <span data-ttu-id="9e759-114">Weitere Informationen finden Sie unter [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="9e759-114">For more information, see [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>

```
instance of MSFT_ServiceResource as $MSFT_ServiceResource1ref
{
SourceInfo = "::5::1::Service";
 ModuleName = "PsDesiredStateConfiguration";
 ResourceID = "[Service]MyService";
 Name = "Spooler";

ModuleVersion = "1.0";

 ConfigurationName = "Test";

};
```

<span data-ttu-id="9e759-115">Bei Anwendung liest der [lokale Konfigurations-Manager (Local Configuration Manager, LCM)](../managing-nodes/metaConfig.md) den Wert „Spooler“ aus der `.mof`-Datei und übergibt ihn dem **Name**-Parameter der **Get**-, **Test**- und **Set**-Methode für die Instanz „MyService“ der **Service**-Ressource.</span><span class="sxs-lookup"><span data-stu-id="9e759-115">When applied, the [Local Configuration Manager](../managing-nodes/metaConfig.md) (LCM) will read the value "Spooler" from the `.mof` file, and pass it to the **Name** parameter of the **Get**, **Test**, and **Set** methods for the "MyService" instance of the **Service** resource.</span></span>

## <a name="get"></a><span data-ttu-id="9e759-116">Herunterladen</span><span class="sxs-lookup"><span data-stu-id="9e759-116">Get</span></span>

<span data-ttu-id="9e759-117">Die **Get**-Methode einer Ressource ruft den Status der Ressource ab, wenn sie auf dem Zielknoten konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="9e759-117">The **Get** method of a resource, retrieves the state of the resource as it is configured on the target Node.</span></span> <span data-ttu-id="9e759-118">Dieser Status wird als [Hashtabelle](/powershell/module/microsoft.powershell.core/about/about_hash_tables) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9e759-118">This state is returned as a [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>
<span data-ttu-id="9e759-119">Die Schlüssel der **Hashtabelle** sind die konfigurierbaren Werte oder Parameter, die die Ressource akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="9e759-119">The keys of the **hashtable** will be the configurable values, or parameters, the resource accepts.</span></span>

<span data-ttu-id="9e759-120">Die **Get**-Methode wird direkt dem [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration)-Cmdlet zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9e759-120">The **Get** method maps directly to the [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="9e759-121">Beim Aufruf von `Get-DSCConfiguration` führt der LCM die **Get**-Methoden der einzelnen Ressourcen in der gerade angewendeten Konfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="9e759-121">When you call `Get-DSCConfiguration`, the LCM runs the **Get** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="9e759-122">Der LCM nutzt die in der `.mof`-Datei gespeicherten Schlüsselwerte als Parameter für die jeweils entsprechende Ressourceninstanz.</span><span class="sxs-lookup"><span data-stu-id="9e759-122">The LCM uses the key values stored in the `.mof` file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="9e759-123">Dies ist eine Beispielausgabe einer **Service**-Ressource, die den „Spooler“-Dienst konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9e759-123">This is sample output from a **Service** resource that configures the "Spooler" service.</span></span>

```output
ConfigurationName    : Test
DependsOn            :
ModuleName           : PsDesiredStateConfiguration
ModuleVersion        : 1.1
PsDscRunAsCredential :
ResourceId           : [Service]Spooler
SourceInfo           :
BuiltInAccount       : LocalSystem
Credential           :
Dependencies         : {RPCSS, http}
Description          : This service spools print jobs and handles interaction with the printer.  If you turn off
                       this service, you won't be able to print or see your printers.
DisplayName          : Print Spooler
Ensure               :
Name                 : Spooler
Path                 : C:\WINDOWS\System32\spoolsv.exe
StartupType          : Automatic
State                : Running
Status               :
PSComputerName       :
CimClassName         : MSFT_ServiceResource
```

<span data-ttu-id="9e759-124">Die Ausgabe zeigt die aktuellen, mit der **Service**-Ressource konfigurierbaren Werteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9e759-124">The output shows the current value properties configurable by the **Service** resource.</span></span>

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

## <a name="test"></a><span data-ttu-id="9e759-125">Test</span><span class="sxs-lookup"><span data-stu-id="9e759-125">Test</span></span>

<span data-ttu-id="9e759-126">Die **Test**-Methode einer Ressource bestimmt, ob der Zielknoten derzeit mit dem _gewünschten Status_ der Ressource konform ist.</span><span class="sxs-lookup"><span data-stu-id="9e759-126">The **Test** method of a resource determines if the target node is currently compliant with the resource's _desired state_.</span></span> <span data-ttu-id="9e759-127">Die **Test**-Methode gibt `$true` oder `$false` nur zurück, um anzuzeigen, ob der Knoten konform ist.</span><span class="sxs-lookup"><span data-stu-id="9e759-127">The **Test** method returns `$true` or `$false` only to indicate whether the Node is compliant.</span></span> <span data-ttu-id="9e759-128">Beim Aufruf von [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) ruft der LCM die **Test**-Methoden der einzelnen Ressourcen in der gerade angewendeten Konfiguration auf.</span><span class="sxs-lookup"><span data-stu-id="9e759-128">When you call [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), the LCM calls the **Test** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="9e759-129">Der LCM nutzt die in der MOF-Datei gespeicherten Schlüsselwerte als Parameter für die jeweilige entsprechende Ressourceninstanz.</span><span class="sxs-lookup"><span data-stu-id="9e759-129">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="9e759-130">Wenn das Ergebnis von **Test** einer beliebigen einzelnen Ressource `$false` ist, gibt `Test-DSCConfiguration``$false` zurück, um anzugeben, dass der Knoten nicht konform ist.</span><span class="sxs-lookup"><span data-stu-id="9e759-130">If the result of any individual resource's **Test** is `$false`, `Test-DSCConfiguration` returns `$false` indicating that the Node is not compliant.</span></span> <span data-ttu-id="9e759-131">Wenn die **Test**-Methoden aller Ressourcen `$true` zurückgeben, gibt `Test-DSCConfiguration``$true` zurück, um anzugeben, dass der Knoten konform ist.</span><span class="sxs-lookup"><span data-stu-id="9e759-131">If all resource's **Test** methods return `$true`, `Test-DSCConfiguration` returns `$true` to indicate that the Node is compliant.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

<span data-ttu-id="9e759-132">Ab PowerShell 5.0 wurde der **Detailed**-Parameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9e759-132">Beginning in PowerShell 5.0, the **Detailed** parameter was added.</span></span> <span data-ttu-id="9e759-133">Die Angabe von **Detailed** bewirkt, dass `Test-DSCConfiguration` ein Objekt zurückgibt, das Sammlungen von Ergebnissen für konforme und nicht konforme Ressourcen enthält.</span><span class="sxs-lookup"><span data-stu-id="9e759-133">Specifying **Detailed** causes `Test-DSCConfiguration` to return an object containing collections of results for compliant, and non-compliant resources.</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

<span data-ttu-id="9e759-134">Weitere Informationen finden Sie unter [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="9e759-134">For more information, see [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span></span>

## <a name="set"></a><span data-ttu-id="9e759-135">Set</span><span class="sxs-lookup"><span data-stu-id="9e759-135">Set</span></span>

<span data-ttu-id="9e759-136">Die **Set**-Methode einer Ressource versucht, die Konformität des Knotens mit dem *gewünschten Status* der Ressource zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="9e759-136">The **Set** method of a resource attempts to force the Node to become compliant with the resource's *desired state*.</span></span> <span data-ttu-id="9e759-137">Die **Set**-Methode soll **idempotent** sein, was bedeutet, dass **Set** mehrmals ausgeführt werden und immer ohne Fehler das gleiche Ergebnis erzielen könnte.</span><span class="sxs-lookup"><span data-stu-id="9e759-137">The **Set** method is meant to be **idempotent**, which means that **Set** could be run multiple times and always get the same result without errors.</span></span> <span data-ttu-id="9e759-138">Beim Aufruf von [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration) durchläuft der LCM die einzelnen Ressourcen in der gerade angewendeten Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="9e759-138">When you run [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), the LCM cycles through each resource in the currently applied configuration.</span></span> <span data-ttu-id="9e759-139">Der LCM ruft Schlüsselwerte für die aktuelle Ressourceninstanz aus der MOF-Datei ab und verwendet sie als Parameter für die **Test**-Methode.</span><span class="sxs-lookup"><span data-stu-id="9e759-139">The LCM retrieves key values for the current resource instance from the ".mof" file and uses them as parameters for the **Test** method.</span></span> <span data-ttu-id="9e759-140">Wenn die **Test**-Methode `$true` zurückgibt, ist der Knoten mit der aktuellen Ressource konform, und die **Set**-Methode wird übersprungen.</span><span class="sxs-lookup"><span data-stu-id="9e759-140">If the **Test** method returns `$true`, the Node is compliant with the current resource, and the **Set** method is skipped.</span></span> <span data-ttu-id="9e759-141">Wenn der **Test**`$false` zurückgibt, ist der Knoten nicht konform.</span><span class="sxs-lookup"><span data-stu-id="9e759-141">If the **Test** returns `$false`, the Node is non-compliant.</span></span> <span data-ttu-id="9e759-142">Der LCM übergibt die Schlüsselwerte der Ressourceninstanz als Parameter an die **Set**-Methode der Ressource und stellt dabei die Konformität des Knotens wieder her.</span><span class="sxs-lookup"><span data-stu-id="9e759-142">The LCM passes the resource instance's key values as parameters to the resource's **Set** method, restoring the Node to compliance.</span></span>

<span data-ttu-id="9e759-143">Durch Angabe der Parameter **Verbose** und **Wait** können Sie den Fortschritt des `Start-DSCConfiguration`-Cmdlets verfolgen.</span><span class="sxs-lookup"><span data-stu-id="9e759-143">By specifying the **Verbose** and **Wait** parameters, you can watch the progress of the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="9e759-144">In diesem Beispiel ist der Knoten bereits konform.</span><span class="sxs-lookup"><span data-stu-id="9e759-144">In this example, the Node is already compliant.</span></span> <span data-ttu-id="9e759-145">Die `Verbose`-Ausgabe gibt an, dass die **Set**-Methode übersprungen wurde.</span><span class="sxs-lookup"><span data-stu-id="9e759-145">The `Verbose` output indicates that the **Set** method was skipped.</span></span>

```
PS> Start-DSCConfiguration -Verbose -Wait -UseExisting

VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' =
ApplyConfiguration,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' =
root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer SERVER01 with user sid
S-1-5-21-124525095-708259637-1543119021-1282804.
VERBOSE: [SERVER01]:                            [] Starting consistency engine.
VERBOSE: [SERVER01]:                            [] Checking consistency for current configuration.
VERBOSE: [SERVER01]:                            [DSCEngine] Importing the module
C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\DscResources\MSFT_ServiceResource\MSFT
_ServiceResource.psm1 in force mode.
VERBOSE: [SERVER01]: LCM:  [ Start  Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ Start  Test     ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [[Service]Spooler] Importing the module MSFT_ServiceResource in
force mode.
VERBOSE: [SERVER01]: LCM:  [ End    Test     ]  [[Service]Spooler]  in 0.2540 seconds.
VERBOSE: [SERVER01]: LCM:  [ Skip   Set      ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ End    Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [] Consistency check completed.
VERBOSE: Operation 'Invoke CimMethod' complete.
VERBOSE: Time taken for configuration job to complete is 1.379 seconds
```

## <a name="see-also"></a><span data-ttu-id="9e759-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e759-146">See also</span></span>

- [<span data-ttu-id="9e759-147">Azure Automation DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="9e759-147">Azure Automation DSC Overview</span></span>](/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="9e759-148">Einrichten eines SMB-Pullservers</span><span class="sxs-lookup"><span data-stu-id="9e759-148">Setting up an SMB pull server</span></span>](../pull-server/pullServerSMB.md)
- [<span data-ttu-id="9e759-149">Konfigurieren eines Pullclients</span><span class="sxs-lookup"><span data-stu-id="9e759-149">Configuring a pull client</span></span>](../pull-server/pullClientConfigID.md)
