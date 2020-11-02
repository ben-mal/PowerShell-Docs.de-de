---
ms.date: 07/16/2020
ms.topic: reference
title: DSC-Ressource „WindowsOptionalFeatureSet“
description: DSC-Ressource „WindowsOptionalFeatureSet“
ms.openlocfilehash: f72cc27bfc8847d2c87cfb289f3e2c729a21d1f4
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143040"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a><span data-ttu-id="cf33f-103">DSC-Ressource „WindowsOptionalFeatureSet“</span><span class="sxs-lookup"><span data-stu-id="cf33f-103">DSC WindowsOptionalFeatureSet Resource</span></span>

> <span data-ttu-id="cf33f-104">Gilt für: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="cf33f-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="cf33f-105">Die Ressource **WindowsOptionalFeatureSet** in Windows PowerShell DSC (Desired State Configuration) bietet einen Mechanismus, um sicherzustellen, dass optionale Features auf einem Zielknoten aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="cf33f-105">The **WindowsOptionalFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span> <span data-ttu-id="cf33f-106">Diese Ressource ist eine [zusammengesetzte Ressource](../../../resources/authoringResourceComposite.md), die die Ressource [WindowsOptionalFeature](windowsOptionalFeatureResource.md) für jedes Feature aufruft, das in der **Name** -Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="cf33f-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsOptionalFeature resource](windowsOptionalFeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="cf33f-107">Verwenden Sie diese Ressource, wenn Sie verschiedene optionale Windows-Features mit demselben Status konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cf33f-107">Use this resource when you want to configure a number of Windows optional features to the same state.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="cf33f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf33f-108">Syntax</span></span>

```Syntax
WindowsOptionalFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="cf33f-109">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cf33f-109">Properties</span></span>

|<span data-ttu-id="cf33f-110">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="cf33f-110">Property</span></span> |<span data-ttu-id="cf33f-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cf33f-111">Description</span></span> |
|---|---|
|<span data-ttu-id="cf33f-112">Name</span><span class="sxs-lookup"><span data-stu-id="cf33f-112">Name</span></span> |<span data-ttu-id="cf33f-113">Gibt den Namen der Features an, die aktiviert oder deaktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cf33f-113">Indicates the name of the features that you want to ensure are enabled or disabled.</span></span> |
|<span data-ttu-id="cf33f-114">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="cf33f-114">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="cf33f-115">Gibt an, ob Windows Update (WU) von DISM kontaktiert wird, wenn die Quelldateien zum Aktivieren von Features gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="cf33f-115">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable features.</span></span> <span data-ttu-id="cf33f-116">Falls `$true`, wird WU nicht von DISM kontaktiert.</span><span class="sxs-lookup"><span data-stu-id="cf33f-116">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="cf33f-117">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="cf33f-117">RemoveFilesOnDisable</span></span> |<span data-ttu-id="cf33f-118">Legen Sie diese Einstellung auf `$true` fest, um alle zu den Features gehörigen Dateien zu entfernen, wenn **Ensure** auf **Absent** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="cf33f-118">Set to `$true` to remove all files associated with the features when **Ensure** is set to **Absent** .</span></span> |
|<span data-ttu-id="cf33f-119">LogLevel</span><span class="sxs-lookup"><span data-stu-id="cf33f-119">LogLevel</span></span> |<span data-ttu-id="cf33f-120">Die maximale Ausgabeebene, die in den Protokollen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cf33f-120">The maximum output level shown in the logs.</span></span> <span data-ttu-id="cf33f-121">Zulässige Werte: **ErrorsOnly** , **ErrorsAndWarning** und **ErrorsAndWarningAndInformation** .</span><span class="sxs-lookup"><span data-stu-id="cf33f-121">The accepted values are: **ErrorsOnly** , **ErrorsAndWarning** , and **ErrorsAndWarningAndInformation** .</span></span> |
|<span data-ttu-id="cf33f-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="cf33f-122">LogPath</span></span> |<span data-ttu-id="cf33f-123">Der Pfad zu einer Protokolldatei, in der der Ressourcenanbieter den Vorgang protokollieren soll.</span><span class="sxs-lookup"><span data-stu-id="cf33f-123">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="cf33f-124">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cf33f-124">Common properties</span></span>

|<span data-ttu-id="cf33f-125">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="cf33f-125">Property</span></span> |<span data-ttu-id="cf33f-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cf33f-126">Description</span></span> |
|---|---|
|<span data-ttu-id="cf33f-127">DependsOn</span><span class="sxs-lookup"><span data-stu-id="cf33f-127">DependsOn</span></span> |<span data-ttu-id="cf33f-128">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="cf33f-128">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="cf33f-129">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="cf33f-129">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="cf33f-130">Ensure</span><span class="sxs-lookup"><span data-stu-id="cf33f-130">Ensure</span></span> |<span data-ttu-id="cf33f-131">Gibt an, ob die Features aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="cf33f-131">Specifies whether the features are enabled.</span></span> <span data-ttu-id="cf33f-132">Um sicherzustellen, dass die Features aktiviert sind, legen Sie diese Eigenschaft auf **Enable** fest.</span><span class="sxs-lookup"><span data-stu-id="cf33f-132">To ensure that the features are enabled, set this property to **Enable** .</span></span> <span data-ttu-id="cf33f-133">Um sicherzustellen, dass die Features deaktiviert sind, legen Sie die Eigenschaft auf **Disable** fest.</span><span class="sxs-lookup"><span data-stu-id="cf33f-133">To ensure that the features are disabled, set the property to **Disable** .</span></span> <span data-ttu-id="cf33f-134">Der Standardwert ist **Enable** .</span><span class="sxs-lookup"><span data-stu-id="cf33f-134">The default value is **Enable** .</span></span> |
|<span data-ttu-id="cf33f-135">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="cf33f-135">PsDscRunAsCredential</span></span> |<span data-ttu-id="cf33f-136">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="cf33f-136">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="cf33f-137">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cf33f-137">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="cf33f-138">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="cf33f-138">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
