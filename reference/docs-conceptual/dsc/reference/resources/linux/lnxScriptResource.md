---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC für Linux-Resource „nxScript“
ms.openlocfilehash: e39808e110d5ee4bf9d0ccd418ca3b15ac9fe420
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463651"
---
# <a name="dsc-for-linux-nxscript-resource"></a><span data-ttu-id="4ab79-103">DSC für Linux-Resource „nxScript“</span><span class="sxs-lookup"><span data-stu-id="4ab79-103">DSC for Linux nxScript Resource</span></span>

<span data-ttu-id="4ab79-104">Die Ressource **nxScript** in PowerShell DSC bietet einen Mechanismus zum Ausführen von Linux-Skripts auf einem Linux-Knoten.</span><span class="sxs-lookup"><span data-stu-id="4ab79-104">The **nxScript** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to run Linux scripts on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ab79-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ab79-105">Syntax</span></span>

```Syntax
nxScript <string> #ResourceName
{
    GetScript = <string>
    SetScript = <string>
    TestScript = <string>
    [ User = <string> ]
    [ Group = <string> ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a><span data-ttu-id="4ab79-106">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4ab79-106">Properties</span></span>

|<span data-ttu-id="4ab79-107">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4ab79-107">Property</span></span> |<span data-ttu-id="4ab79-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4ab79-108">Description</span></span> |
|---|---|
|<span data-ttu-id="4ab79-109">GetScript</span><span class="sxs-lookup"><span data-stu-id="4ab79-109">GetScript</span></span> |<span data-ttu-id="4ab79-110">Stellt ein Skript bereit, um den aktuellen Status des Computers zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4ab79-110">Provides a script to return current status of the machine.</span></span> <span data-ttu-id="4ab79-111">Dieses Skript wird ausgeführt, wenn Sie das Skript [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4ab79-111">This script runs when you invoke the [GetDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script.</span></span> <span data-ttu-id="4ab79-112">Das Skript muss mit einem Shebang, z. B. `#!/bin/bash`, beginnen.</span><span class="sxs-lookup"><span data-stu-id="4ab79-112">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="4ab79-113">SetScript</span><span class="sxs-lookup"><span data-stu-id="4ab79-113">SetScript</span></span> |<span data-ttu-id="4ab79-114">Stellt ein Skript bereit, das den Computer in den richtigen Zustand versetzt.</span><span class="sxs-lookup"><span data-stu-id="4ab79-114">Provides a script that puts the machine in the correct state.</span></span> <span data-ttu-id="4ab79-115">Wenn Sie das Skript [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) aufrufen, wird **TestScript** zuerst ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4ab79-115">When you invoke the [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script, the **TestScript** runs first.</span></span> <span data-ttu-id="4ab79-116">Wenn der **TestScript**-Block einen Exitcode ungleich 0 zurückgibt, wird der **SetScript**-Block ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4ab79-116">If the **TestScript** block returns an exit code other than 0, the **SetScript** block will run.</span></span> <span data-ttu-id="4ab79-117">Wenn der **TestScript**-Block den Exitcode 0 zurückgibt, wird der **SetScript**-Block nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4ab79-117">If the **TestScript** returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="4ab79-118">Das Skript muss mit einem Shebang, z. B. `#!/bin/bash`, beginnen.</span><span class="sxs-lookup"><span data-stu-id="4ab79-118">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="4ab79-119">TestScript</span><span class="sxs-lookup"><span data-stu-id="4ab79-119">TestScript</span></span> |<span data-ttu-id="4ab79-120">Stellt ein Skript bereit, das auswertet, ob sich der Knoten derzeit im richtigen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="4ab79-120">Provides a script that evaluates whether the node is currently in the correct state.</span></span> <span data-ttu-id="4ab79-121">Wenn Sie das Skript [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) aufrufen, wird dieses Skript ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4ab79-121">When you invoke the [StartDscConfiguration.py](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script, this script runs.</span></span> <span data-ttu-id="4ab79-122">Wenn es einen Exitcode ungleich 0 zurückgibt, wird der **SetScript**-Block ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4ab79-122">If it returns an exit code other than 0, the **SetScript** will run.</span></span> <span data-ttu-id="4ab79-123">Wenn es den Exitcode 0 zurückgibt, wird der **SetScript**-Block nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4ab79-123">If it returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="4ab79-124">**TestScript** wird auch ausgeführt, wenn Sie das Skript [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4ab79-124">The **TestScript** also runs when you invoke the [TestDscConfiguration](https://github.com/Microsoft/PowerShell-DSC-for-Linux#performing-dsc-operations-from-the-linux-computer) script.</span></span> <span data-ttu-id="4ab79-125">In diesem Fall wird der **SetScript**-Block jedoch nicht ausgeführt, ganz gleich, welcher Exitcode vom **TestScript**-Block zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4ab79-125">However, in this case, the **SetScript** will not run, no matter what exit code is returned from the **TestScript**.</span></span> <span data-ttu-id="4ab79-126">**TestScript** muss Inhalte enthalten und den Exitcode 0 zurückgeben, wenn die tatsächliche Konfiguration der aktuellen Konfiguration des gewünschten Zustands entspricht. Andernfalls muss ein Exitcode ungleich 0 zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4ab79-126">The **TestScript** must contain content and must return an exit code of 0 if the actual configuration matches the current desired state configuration, and an exit code other than 0 if it does not match.</span></span> <span data-ttu-id="4ab79-127">Die aktuelle Konfiguration des gewünschten Zustands ist die letzte Konfiguration, die auf den Knoten angewendet wurde, der DSC verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ab79-127">The current desired state configuration is the last configuration enacted on the node that is using DSC.</span></span> <span data-ttu-id="4ab79-128">Das Skript muss mit einem Shebang, z. B. `#!/bin/bash`, beginnen.</span><span class="sxs-lookup"><span data-stu-id="4ab79-128">The script must begin with a shebang, such as `#!/bin/bash`.</span></span> |
|<span data-ttu-id="4ab79-129">Benutzer</span><span class="sxs-lookup"><span data-stu-id="4ab79-129">User</span></span> |<span data-ttu-id="4ab79-130">Der Benutzer, der das Skript ausführt.</span><span class="sxs-lookup"><span data-stu-id="4ab79-130">The user to run the script as.</span></span> |
|<span data-ttu-id="4ab79-131">Group</span><span class="sxs-lookup"><span data-stu-id="4ab79-131">Group</span></span> |<span data-ttu-id="4ab79-132">Die Gruppe, die das Skript ausführt.</span><span class="sxs-lookup"><span data-stu-id="4ab79-132">The group to run the script as.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="4ab79-133">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4ab79-133">Common properties</span></span>

|<span data-ttu-id="4ab79-134">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4ab79-134">Property</span></span> |<span data-ttu-id="4ab79-135">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4ab79-135">Description</span></span> |
|---|---|
|<span data-ttu-id="4ab79-136">DependsOn</span><span class="sxs-lookup"><span data-stu-id="4ab79-136">DependsOn</span></span> |<span data-ttu-id="4ab79-137">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="4ab79-137">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="4ab79-138">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="4ab79-138">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |

## <a name="example"></a><span data-ttu-id="4ab79-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ab79-139">Example</span></span>

<span data-ttu-id="4ab79-140">Das folgende Beispiel veranschaulicht die Verwendung der Ressource **nxScript**, um zusätzliche Konfigurationsschritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4ab79-140">The following example demonstrates the use of the **nxScript** resource to perform additional configuration management.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxScript KeepDirEmpty {

    GetScript = @"
#!/bin/bash
ls /tmp/mydir/ | wc -l
"@

    SetScript = @"
#!/bin/bash
rm -rf /tmp/mydir/*
"@

    TestScript = @'
#!/bin/bash
filecount=`ls /tmp/mydir | wc -l`
if [ $filecount -gt 0 ]
then
    exit 1
else
    exit 0
fi
'@
    }
}
```
