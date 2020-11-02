---
ms.date: 07/16/2020
ms.topic: reference
title: WaitForSome-Ressource in DSC
description: WaitForSome-Ressource in DSC
ms.openlocfilehash: bc9c3df2b476e7046ccfe6257acc1d1641e7594b
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143091"
---
# <a name="dsc-waitforsome-resource"></a><span data-ttu-id="adbc6-103">WaitForSome-Ressource in DSC</span><span class="sxs-lookup"><span data-stu-id="adbc6-103">DSC WaitForSome Resource</span></span>

> <span data-ttu-id="adbc6-104">Gilt für: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="adbc6-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="adbc6-105">Die DSC-Ressource (Desired State Configuration) **WaitForSome** kann innerhalb eines Knotenblocks in einer [DSC-Konfiguration](../../../configurations/configurations.md) verwendet werden, um Abhängigkeiten von Konfigurationen auf anderen Knoten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="adbc6-105">The **WaitForSome** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

<span data-ttu-id="adbc6-106">Diese Ressource ist erfolgreich, wenn sich die mit der Eigenschaft **ResourceName** angegebene Ressource auf einer Mindestanzahl von Knoten (angegeben durch **NodeCount** ), die durch die Eigenschaft **NodeName** definiert sind, im gewünschten Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="adbc6-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on a minimum number of nodes (specified by **NodeCount** ) defined by the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="adbc6-107">Die Ressource **WaitForSome** verwendet die Windows-Remoteverwaltung, um den Status anderer Knoten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="adbc6-107">**WaitForSome** resource uses Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="adbc6-108">Weitere Informationen zu Anforderungen zur Portierung und Sicherheit für WinRM finden Sie unter [Sicherheitsaspekte von PowerShell-Remoting](/powershell/scripting/learn/remoting/winrmsecurity).</span><span class="sxs-lookup"><span data-stu-id="adbc6-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity).</span></span>

## <a name="syntax"></a><span data-ttu-id="adbc6-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="adbc6-109">Syntax</span></span>

```Syntax
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [ RetryCount = [UInt32] ]
    [ RetryIntervalSec = [UInt64] ]
    [ ThrottleLimit = [UInt32] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="adbc6-110">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="adbc6-110">Properties</span></span>

|<span data-ttu-id="adbc6-111">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="adbc6-111">Property</span></span> |<span data-ttu-id="adbc6-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="adbc6-112">Description</span></span> |
|---|---|
|<span data-ttu-id="adbc6-113">NodeCount</span><span class="sxs-lookup"><span data-stu-id="adbc6-113">NodeCount</span></span> |<span data-ttu-id="adbc6-114">Die Mindestanzahl von Knoten, die sich im gewünschten Zustand befinden muss, damit diese Ressource erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="adbc6-114">The minimum number of nodes that must be in the desired state for this resource to succeed.</span></span> |
|<span data-ttu-id="adbc6-115">NodeName</span><span class="sxs-lookup"><span data-stu-id="adbc6-115">NodeName</span></span> |<span data-ttu-id="adbc6-116">Die Zielknoten der Ressource für die Abhängigkeit.</span><span class="sxs-lookup"><span data-stu-id="adbc6-116">The target nodes of the resource to depend on.</span></span> |
|<span data-ttu-id="adbc6-117">Ressourcenname</span><span class="sxs-lookup"><span data-stu-id="adbc6-117">ResourceName</span></span> |<span data-ttu-id="adbc6-118">Der Ressourcenname für die Abhängigkeit.</span><span class="sxs-lookup"><span data-stu-id="adbc6-118">The resource name to depend on.</span></span> <span data-ttu-id="adbc6-119">Wenn diese Ressource zu einer anderen Konfiguration gehört, formatieren Sie den Namen als `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span><span class="sxs-lookup"><span data-stu-id="adbc6-119">If this resource belongs to a different configuration, format the name as `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> |
|<span data-ttu-id="adbc6-120">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="adbc6-120">RetryIntervalSec</span></span> |<span data-ttu-id="adbc6-121">Die Anzahl von Sekunden bis zu einem Neuversuch.</span><span class="sxs-lookup"><span data-stu-id="adbc6-121">The number of seconds before retrying.</span></span> <span data-ttu-id="adbc6-122">Der Mindestwert lautet 1.</span><span class="sxs-lookup"><span data-stu-id="adbc6-122">Minimum is 1.</span></span> |
|<span data-ttu-id="adbc6-123">RetryCount</span><span class="sxs-lookup"><span data-stu-id="adbc6-123">RetryCount</span></span> |<span data-ttu-id="adbc6-124">Die maximal zulässige Anzahl von Neuversuchen.</span><span class="sxs-lookup"><span data-stu-id="adbc6-124">The maximum number of times to retry.</span></span> |
|<span data-ttu-id="adbc6-125">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="adbc6-125">ThrottleLimit</span></span> |<span data-ttu-id="adbc6-126">Die Anzahl von Computern, die gleichzeitig eine Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="adbc6-126">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="adbc6-127">Die Standardeinstellung lautet `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="adbc6-127">Default is `New-CimSession` default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="adbc6-128">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="adbc6-128">Common properties</span></span>

|<span data-ttu-id="adbc6-129">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="adbc6-129">Property</span></span> |<span data-ttu-id="adbc6-130">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="adbc6-130">Description</span></span> |
|---|---|
|<span data-ttu-id="adbc6-131">DependsOn</span><span class="sxs-lookup"><span data-stu-id="adbc6-131">DependsOn</span></span> |<span data-ttu-id="adbc6-132">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="adbc6-132">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="adbc6-133">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="adbc6-133">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="adbc6-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="adbc6-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="adbc6-135">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="adbc6-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="adbc6-136">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="adbc6-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="adbc6-137">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="adbc6-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="adbc6-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="adbc6-138">Example</span></span>

<span data-ttu-id="adbc6-139">Ein Beispiel zur Verwendung dieser Ressource finden Sie unter [Angeben knotenübergreifender Abhängigkeiten](../../../configurations/crossNodeDependencies.md).</span><span class="sxs-lookup"><span data-stu-id="adbc6-139">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
