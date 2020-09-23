---
ms.date: 08/28/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressource „WindowsOptionalFeature“
ms.openlocfilehash: f24173c1a9ed605bac43767a9da2d4dbded78883
ms.sourcegitcommit: 06b6f4012e4eca71d414733cdba23ef75535223c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "89093249"
---
# <a name="dsc-windowsoptionalfeature-resource"></a><span data-ttu-id="33979-103">DSC-Ressource „WindowsOptionalFeature“</span><span class="sxs-lookup"><span data-stu-id="33979-103">DSC WindowsOptionalFeature Resource</span></span>

> <span data-ttu-id="33979-104">Gilt für: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="33979-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="33979-105">Die Ressource **WindowsOptionalFeature** in Windows PowerShell DSC (Desired State Configuration) bietet einen Mechanismus, um sicherzustellen, dass optionale Features auf einem Zielknoten aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="33979-105">The **WindowsOptionalFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span>

> [!NOTE]
> <span data-ttu-id="33979-106">**WindowsOptionalFeature** funktioniert nur auf Windows-Clientcomputern wie Windows 10.</span><span class="sxs-lookup"><span data-stu-id="33979-106">**WindowsOptionalFeature** only works on Windows client machines like Windows 10.</span></span>

## <a name="syntax"></a><span data-ttu-id="33979-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="33979-107">Syntax</span></span>

```Syntax
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="33979-108">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="33979-108">Properties</span></span>

|<span data-ttu-id="33979-109">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="33979-109">Property</span></span> |<span data-ttu-id="33979-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33979-110">Description</span></span> |
|---|---|
|<span data-ttu-id="33979-111">Name</span><span class="sxs-lookup"><span data-stu-id="33979-111">Name</span></span> |<span data-ttu-id="33979-112">Gibt den Namen des Features an, das aktiviert oder deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="33979-112">Indicates the name of the feature that you want to ensure is enabled or disabled.</span></span> |
|<span data-ttu-id="33979-113">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="33979-113">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="33979-114">Gibt an, ob Windows Update (WU) von DISM kontaktiert wird, wenn die Quelldateien zum Aktivieren eines Features gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="33979-114">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable a feature.</span></span> <span data-ttu-id="33979-115">Falls `$true`, wird WU nicht von DISM kontaktiert.</span><span class="sxs-lookup"><span data-stu-id="33979-115">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="33979-116">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="33979-116">RemoveFilesOnDisable</span></span> |<span data-ttu-id="33979-117">Legen Sie diese Einstellung auf `$true` fest, um alle zu dem Feature gehörigen Dateien zu entfernen, wenn **Ensure** auf **Absent** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="33979-117">Set to `$true` to remove all files associated with the feature when **Ensure** is set to **Absent**.</span></span> |
|<span data-ttu-id="33979-118">LogLevel</span><span class="sxs-lookup"><span data-stu-id="33979-118">LogLevel</span></span> |<span data-ttu-id="33979-119">Die maximale Ausgabeebene, die in den Protokollen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="33979-119">The maximum output level shown in the logs.</span></span> <span data-ttu-id="33979-120">Zulässige Werte: **ErrorsOnly**, **ErrorsAndWarning** und **ErrorsAndWarningAndInformation**.</span><span class="sxs-lookup"><span data-stu-id="33979-120">The accepted values are: **ErrorsOnly**, **ErrorsAndWarning**, and **ErrorsAndWarningAndInformation**.</span></span> |
|<span data-ttu-id="33979-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="33979-121">LogPath</span></span> |<span data-ttu-id="33979-122">Der Pfad zu einer Protokolldatei, in der der Ressourcenanbieter den Vorgang protokollieren soll.</span><span class="sxs-lookup"><span data-stu-id="33979-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="33979-123">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="33979-123">Common properties</span></span>

|<span data-ttu-id="33979-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="33979-124">Property</span></span> |<span data-ttu-id="33979-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="33979-125">Description</span></span> |
|---|---|
|<span data-ttu-id="33979-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="33979-126">DependsOn</span></span> |<span data-ttu-id="33979-127">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="33979-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="33979-128">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="33979-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="33979-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="33979-129">Ensure</span></span> |<span data-ttu-id="33979-130">Gibt an, ob die Funktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="33979-130">Specifies whether the feature is enabled.</span></span> <span data-ttu-id="33979-131">Um sicherzustellen, dass das Feature aktiviert ist, legen Sie diese Eigenschaft auf _Enable_ fest.</span><span class="sxs-lookup"><span data-stu-id="33979-131">To ensure that the feature is enabled, set this property to _Enable_.</span></span> <span data-ttu-id="33979-132">Um sicherzustellen, dass das Feature deaktiviert ist, legen Sie diese Eigenschaft auf _Disable_ fest.</span><span class="sxs-lookup"><span data-stu-id="33979-132">To ensure that the feature is disabled, set the property to _Disable_.</span></span> <span data-ttu-id="33979-133">Der Standardwert ist _Enable_.</span><span class="sxs-lookup"><span data-stu-id="33979-133">The default value is _Enable_.</span></span> |
|<span data-ttu-id="33979-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="33979-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="33979-135">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="33979-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="33979-136">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="33979-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="33979-137">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="33979-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
