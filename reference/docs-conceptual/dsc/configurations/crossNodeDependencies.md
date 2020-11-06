---
ms.date: 12/12/2018
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Angeben knotenübergreifender Abhängigkeiten
description: DSC bietet spezielle Ressourcen, die in Konfigurationen zum Angeben von Abhängigkeiten von Konfigurationen auf anderen Knoten verwendet werden.
ms.openlocfilehash: a9fc09af922839b37db476c24c113efc5e3e8cb1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658491"
---
# <a name="specifying-cross-node-dependencies"></a><span data-ttu-id="fa572-104">Angeben knotenübergreifender Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="fa572-104">Specifying cross-node dependencies</span></span>

> <span data-ttu-id="fa572-105">Gilt für: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="fa572-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="fa572-106">DSC bietet spezielle Ressourcen **WaitForAll** , **WaitForAny** und **WaitForSome** , die in Konfigurationen zum Angeben von Abhängigkeiten von Konfigurationen auf anderen Knoten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fa572-106">DSC provides special resources, **WaitForAll** , **WaitForAny** , and **WaitForSome** that can be used in configurations to specify dependencies on configurations on other nodes.</span></span> <span data-ttu-id="fa572-107">Die Ressourcen verhalten sich wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fa572-107">The behavior of these resources is as follows:</span></span>

- <span data-ttu-id="fa572-108">**WaitForAll** : Ist erfolgreich, wenn die angegebene Ressource auf allen Zielknoten, die in der **NodeName** -Eigenschaft definiert sind, den gewünschten Zustand hat.</span><span class="sxs-lookup"><span data-stu-id="fa572-108">**WaitForAll** : Succeeds if the specified resource is in the desired state on all target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="fa572-109">**WaitForAny** : Ist erfolgreich, wenn die angegebene Ressource auf mindestens einem der Zielknoten, die in der **NodeName** -Eigenschaft definiert sind, den gewünschten Zustand hat.</span><span class="sxs-lookup"><span data-stu-id="fa572-109">**WaitForAny** : Succeeds if the specified resource is in the desired state on at least one of the target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="fa572-110">**WaitForSome** : Gibt zusätzlich zu einer **NodeName** -Eigenschaft eine **NodeCount** -Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="fa572-110">**WaitForSome** : Specifies a **NodeCount** property in addition to a **NodeName** property.</span></span> <span data-ttu-id="fa572-111">Die Ressource ist erfolgreich, wenn sich die Ressource auf einer Mindestanzahl von Knoten (angegeben durch **NodeCount** ), die von der **NodeName** -Eigenschaft definiert sind, im gewünschten Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="fa572-111">The resource succeeds if the resource is in the desired state on a minimum number of nodes (specified by **NodeCount** ) defined by the **NodeName** property.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa572-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa572-112">Syntax</span></span>

<span data-ttu-id="fa572-113">Die **WaitForAll** - und **WaitForAny** -Ressourcen verwenden die gleiche Syntax.</span><span class="sxs-lookup"><span data-stu-id="fa572-113">The **WaitForAll** and **WaitForAny** resources share the same syntax.</span></span> <span data-ttu-id="fa572-114">Ersetzen Sie `<ResourceType>` im folgenden Beispiel durch **WaitForAny** oder durch **WaitForAll**.</span><span class="sxs-lookup"><span data-stu-id="fa572-114">Replace `<ResourceType>` in the example below with either **WaitForAny** or **WaitForAll**.</span></span> <span data-ttu-id="fa572-115">Wie beim Schlüsselwort **DependsOn** müssen Sie den Namen als `[ResourceType]ResourceName` formatieren.</span><span class="sxs-lookup"><span data-stu-id="fa572-115">Like the **DependsOn** keyword, you will need to format the name as `[ResourceType]ResourceName`.</span></span> <span data-ttu-id="fa572-116">Wenn die Ressource zu einer separaten [Konfiguration](configurations.md) gehört, schließen Sie **ConfigurationName** in die formatierte Zeichenfolge `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]` ein.</span><span class="sxs-lookup"><span data-stu-id="fa572-116">If the resource belongs to a separate [Configuration](configurations.md), include the **ConfigurationName** in the formatted string `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> <span data-ttu-id="fa572-117">Der **NodeName** ist der Computer oder Knoten, auf den die aktuelle Ressource warten soll.</span><span class="sxs-lookup"><span data-stu-id="fa572-117">The **NodeName** is the computer, or Node, on which the current resource should wait.</span></span>

```
<ResourceType> [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential]]
    [ RetryCount = [Uint32] ]
    [ RetryIntervalSec = [Uint64] ]
    [ ThrottleLimit = [Uint32]]
}
```

<span data-ttu-id="fa572-118">Die Ressource **WaitForSome** hat eine ähnliche Syntax wie das Beispiel oben, fügt aber den Schlüssel **NodeCount** hinzu.</span><span class="sxs-lookup"><span data-stu-id="fa572-118">The **WaitForSome** resource has a similar syntax to the example above, but adds the **NodeCount** key.</span></span> <span data-ttu-id="fa572-119">Der **NodeCount** gibt an, auf wie viele Knoten die aktuelle Ressource warten soll.</span><span class="sxs-lookup"><span data-stu-id="fa572-119">The **NodeCount** indicates how many Nodes the current resource should wait on.</span></span>

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

<span data-ttu-id="fa572-120">Alle **WaitForXXXX** -Ressourcen verwenden die folgenden Syntaxschlüssel gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="fa572-120">All **WaitForXXXX** share the following syntax keys.</span></span>

|       <span data-ttu-id="fa572-121">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="fa572-121">Property</span></span>       |                                                                           <span data-ttu-id="fa572-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa572-122">Description</span></span>                                                                           |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="fa572-123">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="fa572-123">RetryIntervalSec</span></span>     | <span data-ttu-id="fa572-124">Die Anzahl von Sekunden bis zu einem Neuversuch.</span><span class="sxs-lookup"><span data-stu-id="fa572-124">The number of seconds before retrying.</span></span> <span data-ttu-id="fa572-125">Der Mindestwert lautet 1.</span><span class="sxs-lookup"><span data-stu-id="fa572-125">Minimum is 1.</span></span>                                                                                                            |
| <span data-ttu-id="fa572-126">RetryCount</span><span class="sxs-lookup"><span data-stu-id="fa572-126">RetryCount</span></span>           | <span data-ttu-id="fa572-127">Die maximal zulässige Anzahl von Neuversuchen.</span><span class="sxs-lookup"><span data-stu-id="fa572-127">The maximum number of times to retry.</span></span>                                                                                                                           |
| <span data-ttu-id="fa572-128">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="fa572-128">ThrottleLimit</span></span>        | <span data-ttu-id="fa572-129">Die Anzahl von Computern, die gleichzeitig eine Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="fa572-129">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="fa572-130">Die Standardeinstellung lautet `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="fa572-130">Default is `New-CimSession` default.</span></span>                                                                              |
| <span data-ttu-id="fa572-131">DependsOn</span><span class="sxs-lookup"><span data-stu-id="fa572-131">DependsOn</span></span>            | <span data-ttu-id="fa572-132">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="fa572-132">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="fa572-133">Weitere Informationen finden Sie unter [DependsOn](resource-depends-on.md).</span><span class="sxs-lookup"><span data-stu-id="fa572-133">For more information, see [DependsOn](resource-depends-on.md)</span></span> |
| <span data-ttu-id="fa572-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="fa572-134">PsDscRunAsCredential</span></span> | <span data-ttu-id="fa572-135">Informationen finden Sie unter [Verwenden von DSC mit Benutzeranmeldeinformationen](./runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="fa572-135">See [Using DSC with User Credentials](./runAsUser.md)</span></span>                                                                                                           |

## <a name="using-waitforxxxx-resources"></a><span data-ttu-id="fa572-136">Verwenden von WaitForXXXX-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="fa572-136">Using WaitForXXXX resources</span></span>

<span data-ttu-id="fa572-137">Jede **WaitForXXXX** -Ressource wartet darauf, dass die angegebenen Ressourcen auf dem angegebenen Knoten abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="fa572-137">Each **WaitForXXXX** resource waits for the specified resources to complete on the specified Node.</span></span>
<span data-ttu-id="fa572-138">Andere Ressourcen in derselben Konfiguration können dann von der **WaitForXXXX** -Ressource mit dem Schlüssel **DependsOn** als *abhängig* gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="fa572-138">Other resources in the same Configuration can then *depend on* the **WaitForXXXX** resource using the **DependsOn** key.</span></span>

<span data-ttu-id="fa572-139">Bei der folgenden Konfiguration wartet der Zielknoten beispielsweise, bis die Ressource **xADDomain** auf dem Knoten **MyDC** (bei einer maximalen Anzahl von 30 Wiederholungen in 15-Sekunden-Intervallen) abgeschlossen ist, ehe der Zielknoten der Domäne beitreten kann.</span><span class="sxs-lookup"><span data-stu-id="fa572-139">For example, in the following configuration, the target node is waiting for the **xADDomain** resource to finish on the **MyDC** node with maximum number of 30 retries, at 15-second intervals, before the target node can join the domain.</span></span>

<span data-ttu-id="fa572-140">Standardmäßig führen die **WaitForXXXX** -Ressourcen einen Versuch durch und verursachen dann einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="fa572-140">By default the **WaitForXXX** resources try one time and then fail.</span></span> <span data-ttu-id="fa572-141">Auch wenn dies nicht erforderlich ist, sollten Sie in der Regel **RetryCount** sowie **RetryIntervalSec** angeben.</span><span class="sxs-lookup"><span data-stu-id="fa572-141">Although it is not required, you will typically want to specify a **RetryCount** and **RetryIntervalSec**.</span></span>

```powershell
Configuration JoinDomain
{
    Import-DscResource -Module xComputerManagement, xActiveDirectory

    Node myDC
    {
        WindowsFeature InstallAD
        {
            Ensure = 'Present'
            Name = 'AD-Domain-Services'
        }

        xADDomain NewDomain
        {
            DomainName = 'Contoso.com'
            DomainAdministratorCredential = (Get-Credential)
            SafemodeAdministratorPassword = (Get-Credential)
            DatabasePath = "C:\Windows\NTDS"
            LogPath = "C:\Windows\NTDS"
            SysvolPath = "C:\Windows\Sysvol"
        }
    }

    Node myDomainJoinedServer
    {
        WaitForAll DC
        {
            ResourceName      = '[xADDomain]NewDomain'
            NodeName          = 'MyDC'
            RetryIntervalSec  = 15
            RetryCount        = 30
        }

        xComputer JoinDomain
        {
            Name             = 'myPC'
            DomainName       = 'Contoso.com'
            Credential       = (Get-Credential)
            DependsOn        ='[WaitForAll]DC'
        }
    }
}
```

<span data-ttu-id="fa572-142">Wenn Sie die Konfiguration kompilieren, werden zwei MOF-Dateien generiert.</span><span class="sxs-lookup"><span data-stu-id="fa572-142">When you compile the Configuration, two ".mof" files are generated.</span></span> <span data-ttu-id="fa572-143">Wenden Sie beide MOF-Dateien mit dem Cmdlet [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) auf die Zielknoten an.</span><span class="sxs-lookup"><span data-stu-id="fa572-143">Apply both ".mof" files to the target Nodes using the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet</span></span>

> [!NOTE]
> <span data-ttu-id="fa572-144">Die Ressource **WaitForXXX** verwendet die Windows-Remoteverwaltung, um den Status anderer Knoten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fa572-144">**WaitForXXX** resources use Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="fa572-145">Weitere Informationen zu Anforderungen zur Portierung und Sicherheit für WinRM finden Sie unter [Sicherheitsaspekte von PowerShell-Remoting](/powershell/scripting/learn/remoting/winrmsecurity).</span><span class="sxs-lookup"><span data-stu-id="fa572-145">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa572-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa572-146">See Also</span></span>

- [<span data-ttu-id="fa572-147">DSC-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="fa572-147">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="fa572-148">Verwenden von Ressourcenabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="fa572-148">Use Resource Dependencies</span></span>](resource-depends-on.md)
- [<span data-ttu-id="fa572-149">DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="fa572-149">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="fa572-150">Konfigurieren des lokalen Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="fa572-150">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
