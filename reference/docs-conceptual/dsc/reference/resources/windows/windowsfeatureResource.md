---
ms.date: 07/16/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressource „WindowsFeature“
ms.openlocfilehash: b15b267c6898697816b386a381e5a6d59acd492a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464110"
---
# <a name="dsc-windowsfeature-resource"></a><span data-ttu-id="57778-103">DSC-Ressource „WindowsFeature“</span><span class="sxs-lookup"><span data-stu-id="57778-103">DSC WindowsFeature Resource</span></span>

> <span data-ttu-id="57778-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="57778-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="57778-105">Die Ressource **WindowsFeature** in Windows PowerShell DSC (Desired State Configuration) bietet einen Mechanismus, um sicherzustellen, dass Rollen und Features einem Knoten hinzugefügt oder entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="57778-105">The **WindowsFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="57778-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="57778-106">Syntax</span></span>

```Syntax
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="57778-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="57778-107">Properties</span></span>

|<span data-ttu-id="57778-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="57778-108">Property</span></span> |<span data-ttu-id="57778-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="57778-109">Description</span></span> |
|---|---|
|<span data-ttu-id="57778-110">Name</span><span class="sxs-lookup"><span data-stu-id="57778-110">Name</span></span> |<span data-ttu-id="57778-111">Gibt den Namen der Rolle oder des Features an, die/das hinzugefügt oder entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="57778-111">Indicates the name of the role or feature that you want to ensure is added or removed.</span></span> <span data-ttu-id="57778-112">Dies ist identisch mit der **Name**-Eigenschaft aus dem Cmdlet [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) und nicht mit dem Anzeigenamen der Rolle oder des Features.</span><span class="sxs-lookup"><span data-stu-id="57778-112">This is the same as the **Name** property from the [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) cmdlet, and not the display name of the role or feature.</span></span> |
|<span data-ttu-id="57778-113">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="57778-113">Credential</span></span> |<span data-ttu-id="57778-114">Gibt die Anmeldeinformationen zum Hinzufügen oder Entfernen der Rolle oder des Features an.</span><span class="sxs-lookup"><span data-stu-id="57778-114">Indicates the credentials to use to add or remove the role or feature.</span></span> |
|<span data-ttu-id="57778-115">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="57778-115">IncludeAllSubFeature</span></span> |<span data-ttu-id="57778-116">Legen Sie diese Eigenschaft auf `$true` fest, um den Status aller erforderlichen Teilfeatures mit dem Status des Features sicherzustellen, das Sie mit der **Name**-Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="57778-116">Set this property to `$true` to ensure the state of all required subfeatures with the state of the feature you specify with the **Name** property.</span></span> |
|<span data-ttu-id="57778-117">LogPath</span><span class="sxs-lookup"><span data-stu-id="57778-117">LogPath</span></span> |<span data-ttu-id="57778-118">Gibt den Pfad zu einer Protokolldatei an, in der der Ressourcenanbieter den Vorgang protokollieren soll.</span><span class="sxs-lookup"><span data-stu-id="57778-118">Indicates the path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="57778-119">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="57778-119">Common properties</span></span>

|<span data-ttu-id="57778-120">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="57778-120">Property</span></span> |<span data-ttu-id="57778-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="57778-121">Description</span></span> |
|---|---|
|<span data-ttu-id="57778-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="57778-122">DependsOn</span></span> |<span data-ttu-id="57778-123">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="57778-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="57778-124">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="57778-124">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="57778-125">Ensure</span><span class="sxs-lookup"><span data-stu-id="57778-125">Ensure</span></span> |<span data-ttu-id="57778-126">Gibt an, ob die Rolle oder das Feature hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="57778-126">Indicates if the role or feature is added.</span></span> <span data-ttu-id="57778-127">Um sicherzustellen, dass die Rolle oder das Feature hinzugefügt wird, legen Sie diese Eigenschaft auf **Present** fest.</span><span class="sxs-lookup"><span data-stu-id="57778-127">To ensure that the role or feature is added, set this property to **Present**.</span></span> <span data-ttu-id="57778-128">Um sicherzustellen, dass die Rolle oder das Feature entfernt wird, legen Sie diese Eigenschaft auf **Absent** fest.</span><span class="sxs-lookup"><span data-stu-id="57778-128">To ensure that the role or feature is removed, set the property to **Absent**.</span></span> <span data-ttu-id="57778-129">Der Standardwert ist **Present**.</span><span class="sxs-lookup"><span data-stu-id="57778-129">The default value is **Present**.</span></span> |
|<span data-ttu-id="57778-130">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="57778-130">PsDscRunAsCredential</span></span> |<span data-ttu-id="57778-131">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="57778-131">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="57778-132">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="57778-132">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="57778-133">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="57778-133">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="57778-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57778-134">Example</span></span>

```powershell
WindowsFeature RoleExample
{
    Ensure = "Present"
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature
}
```
