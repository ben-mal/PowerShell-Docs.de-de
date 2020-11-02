---
ms.date: 07/16/2020
ms.topic: reference
title: DSC-Ressource „WindowsProcess“
description: DSC-Ressource „WindowsProcess“
ms.openlocfilehash: 3076e9cb857b78953c164253351b23e7da9b40c6
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143006"
---
# <a name="dsc-windowsprocess-resource"></a><span data-ttu-id="1daf6-103">DSC-Ressource „WindowsProcess“</span><span class="sxs-lookup"><span data-stu-id="1daf6-103">DSC WindowsProcess Resource</span></span>

> <span data-ttu-id="1daf6-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="1daf6-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="1daf6-105">Die Ressource **WindowsProcess** in Windows PowerShell DSC bietet einen Mechanismus zum Konfigurieren von Prozessen auf einem Zielknoten.</span><span class="sxs-lookup"><span data-stu-id="1daf6-105">The **WindowsProcess** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="1daf6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1daf6-106">Syntax</span></span>

```Syntax
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="1daf6-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1daf6-107">Properties</span></span>

|<span data-ttu-id="1daf6-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1daf6-108">Property</span></span> |<span data-ttu-id="1daf6-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1daf6-109">Description</span></span> |
|---|---|
|<span data-ttu-id="1daf6-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="1daf6-110">Arguments</span></span> |<span data-ttu-id="1daf6-111">Gibt eine Zeichenfolge von Argumenten an, die wie vorhanden an den Prozess übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="1daf6-111">Indicates a string of arguments to pass to the process as-is.</span></span> <span data-ttu-id="1daf6-112">Wenn Sie mehrere Argumente übergeben müssen, fügen Sie sie alle dieser Zeichenfolge hinzu.</span><span class="sxs-lookup"><span data-stu-id="1daf6-112">If you need to pass several arguments, put them all in this string.</span></span> |
|<span data-ttu-id="1daf6-113">`Path`</span><span class="sxs-lookup"><span data-stu-id="1daf6-113">Path</span></span> |<span data-ttu-id="1daf6-114">Der Pfad zur ausführbaren Prozessdatei.</span><span class="sxs-lookup"><span data-stu-id="1daf6-114">The path to the process executable.</span></span> <span data-ttu-id="1daf6-115">Wenn es sich um den Namen der ausführbaren Datei (keinen vollqualifizierten Pfad) handelt, durchsucht die Ressource „DSC“ die Umgebungsvariable `$env:Path`, um die ausführbare Datei zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="1daf6-115">If this the file name of the executable (not the fully qualified path), the DSC resource will search the environment `$env:Path` variable to find the executable file.</span></span> <span data-ttu-id="1daf6-116">Wenn der Werte dieser Eigenschaft ein vollqualifizierter Pfad ist, verwendet DSC nicht die Umgebungsvariable `$env:Path`, um die Dateien zu finden, und löst einen Fehler aus, wenn der Pfad nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1daf6-116">If the value of this property is a fully qualified path, DSC will not use the `$env:Path` variable to find the file, and will throw an error if the path does not exist.</span></span> <span data-ttu-id="1daf6-117">Relative Pfade sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1daf6-117">Relative paths are not allowed.</span></span> |
|<span data-ttu-id="1daf6-118">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="1daf6-118">Credential</span></span> |<span data-ttu-id="1daf6-119">Gibt die Anmeldeinformationen zum Starten des Prozesses an.</span><span class="sxs-lookup"><span data-stu-id="1daf6-119">Indicates the credentials for starting the process.</span></span> |
|<span data-ttu-id="1daf6-120">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="1daf6-120">StandardErrorPath</span></span> |<span data-ttu-id="1daf6-121">Gibt den Verzeichnispfad an, in den der Standardfehler geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1daf6-121">Indicates the directory path to write the standard error.</span></span> <span data-ttu-id="1daf6-122">Eine vorhandene Datei wird überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1daf6-122">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="1daf6-123">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="1daf6-123">StandardInputPath</span></span> |<span data-ttu-id="1daf6-124">Gibt den Standardpfad für die Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="1daf6-124">Indicates the standard input location.</span></span> |
|<span data-ttu-id="1daf6-125">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="1daf6-125">StandardOutputPath</span></span> |<span data-ttu-id="1daf6-126">Gibt den Speicherort an, in den die Standardausgabe geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1daf6-126">Indicates the location to write the standard output.</span></span> <span data-ttu-id="1daf6-127">Eine vorhandene Datei wird überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1daf6-127">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="1daf6-128">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="1daf6-128">WorkingDirectory</span></span> |<span data-ttu-id="1daf6-129">Gibt den Speicherort an, der als das aktuelle Arbeitsverzeichnis für den Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1daf6-129">Indicates the location that will be used as the current working directory for the process.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="1daf6-130">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1daf6-130">Common properties</span></span>

|<span data-ttu-id="1daf6-131">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1daf6-131">Property</span></span> |<span data-ttu-id="1daf6-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1daf6-132">Description</span></span> |
|---|---|
|<span data-ttu-id="1daf6-133">DependsOn</span><span class="sxs-lookup"><span data-stu-id="1daf6-133">DependsOn</span></span> |<span data-ttu-id="1daf6-134">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="1daf6-134">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="1daf6-135">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="1daf6-135">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="1daf6-136">Ensure</span><span class="sxs-lookup"><span data-stu-id="1daf6-136">Ensure</span></span> |<span data-ttu-id="1daf6-137">Gibt an, ob der Prozess vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1daf6-137">Indicates if the process exists.</span></span> <span data-ttu-id="1daf6-138">Legen Sie diese Eigenschaft auf **Present** fest, um sicherzustellen, dass der Prozess vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1daf6-138">Set this property to **Present** to ensure that the process exists.</span></span> <span data-ttu-id="1daf6-139">Legen Sie sie andernfalls auf **Absent** fest.</span><span class="sxs-lookup"><span data-stu-id="1daf6-139">Otherwise, set it to **Absent** .</span></span> <span data-ttu-id="1daf6-140">Der Standardwert ist **Present** .</span><span class="sxs-lookup"><span data-stu-id="1daf6-140">The default value is **Present** .</span></span> |
|<span data-ttu-id="1daf6-141">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="1daf6-141">PsDscRunAsCredential</span></span> |<span data-ttu-id="1daf6-142">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="1daf6-142">Sets the credential for running the entire resource as.</span></span> |
