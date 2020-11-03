---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/checkpoint-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-Computer
ms.openlocfilehash: 61f8d626cd45cfe47f0e65a3043696a01c97ca20
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215607"
---
# <span data-ttu-id="173dd-103">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="173dd-103">Checkpoint-Computer</span></span>

## <span data-ttu-id="173dd-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="173dd-104">SYNOPSIS</span></span>
<span data-ttu-id="173dd-105">Erstellt einen Systemwiederherstellungspunkt auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="173dd-105">Creates a system restore point on the local computer.</span></span>

## <span data-ttu-id="173dd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="173dd-106">SYNTAX</span></span>

```
Checkpoint-Computer [-Description] <String> [[-RestorePointType] <String>] [<CommonParameters>]
```

## <span data-ttu-id="173dd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="173dd-107">DESCRIPTION</span></span>

<span data-ttu-id="173dd-108">Mit dem- `Checkpoint-Computer` Cmdlet wird ein Systemwiederherstellungspunkt auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="173dd-108">The `Checkpoint-Computer` cmdlet creates a system restore point on the local computer.</span></span>

<span data-ttu-id="173dd-109">System Wiederherstellungspunkte und das `Checkpoint-Computer` Cmdlet werden nur unter Client Betriebssystemen wie Windows 8, Windows 7, Windows Vista und Windows XP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="173dd-109">System restore points and the `Checkpoint-Computer` cmdlet are supported only on client operating systems, such as Windows 8, Windows 7, Windows Vista, and Windows XP.</span></span>

<span data-ttu-id="173dd-110">Ab Windows 8 `Checkpoint-Computer` kann nicht mehr als einen Prüfpunkt pro Tag erstellen.</span><span class="sxs-lookup"><span data-stu-id="173dd-110">Beginning in Windows 8, `Checkpoint-Computer` cannot create more than one checkpoint each day.</span></span>

## <span data-ttu-id="173dd-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="173dd-111">EXAMPLES</span></span>

### <span data-ttu-id="173dd-112">Beispiel 1: Erstellen eines System Wiederherstellungs Punkts</span><span class="sxs-lookup"><span data-stu-id="173dd-112">Example 1: Create a system restore point</span></span>

```powershell
Checkpoint-Computer -Description "Install MyApp"
```

<span data-ttu-id="173dd-113">Dieser Befehl erstellt einen Systemwiederherstellungspunkt mit dem Namen "Install MyApp".</span><span class="sxs-lookup"><span data-stu-id="173dd-113">This command creates a system restore point called Install MyApp.</span></span>
<span data-ttu-id="173dd-114">Er verwendet den Standardtyp für Wiederherstellungspunkte APPLICATION_INSTALL.</span><span class="sxs-lookup"><span data-stu-id="173dd-114">It uses the default APPLICATION_INSTALL restore point type.</span></span>

### <span data-ttu-id="173dd-115">Beispiel 2: Erstellen eines System MODIFY_SETTINGS Wiederherstellungs Punkts</span><span class="sxs-lookup"><span data-stu-id="173dd-115">Example 2: Create a system MODIFY_SETTINGS restore point</span></span>

```powershell
Checkpoint-Computer -Description "ChangeNetSettings" -RestorePointType MODIFY_SETTINGS
```

<span data-ttu-id="173dd-116">Dieser Befehl erstellt den MODIFY_SETTINGS-Systemwiederherstellungspunkt %%amp;quot;ChangeNetSettings%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="173dd-116">This command creates a MODIFY_SETTINGS system restore point called "ChangeNetSettings".</span></span>

## <span data-ttu-id="173dd-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="173dd-117">PARAMETERS</span></span>

### <span data-ttu-id="173dd-118">-Description</span><span class="sxs-lookup"><span data-stu-id="173dd-118">-Description</span></span>

<span data-ttu-id="173dd-119">Gibt einen beschreibenden Namen für den Wiederherstellungspunkt an.</span><span class="sxs-lookup"><span data-stu-id="173dd-119">Specifies a descriptive name for the restore point.</span></span>
<span data-ttu-id="173dd-120">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="173dd-120">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="173dd-121">-Restorepointtype</span><span class="sxs-lookup"><span data-stu-id="173dd-121">-RestorePointType</span></span>

<span data-ttu-id="173dd-122">Gibt den Typ des Wiederherstellungspunkts an.</span><span class="sxs-lookup"><span data-stu-id="173dd-122">Specifies the type of restore point.</span></span>
<span data-ttu-id="173dd-123">Der Standard lautet APPLICATION_INSTALL.</span><span class="sxs-lookup"><span data-stu-id="173dd-123">The default is APPLICATION_INSTALL.</span></span>

<span data-ttu-id="173dd-124">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="173dd-124">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="173dd-125">APPLICATION_INSTALL</span><span class="sxs-lookup"><span data-stu-id="173dd-125">APPLICATION_INSTALL</span></span>
- <span data-ttu-id="173dd-126">APPLICATION_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="173dd-126">APPLICATION_UNINSTALL</span></span>
- <span data-ttu-id="173dd-127">DEVICE_DRIVER_INSTALL</span><span class="sxs-lookup"><span data-stu-id="173dd-127">DEVICE_DRIVER_INSTALL</span></span>
- <span data-ttu-id="173dd-128">MODIFY_SETTINGS</span><span class="sxs-lookup"><span data-stu-id="173dd-128">MODIFY_SETTINGS</span></span>
- <span data-ttu-id="173dd-129">CANCELLED_OPERATION</span><span class="sxs-lookup"><span data-stu-id="173dd-129">CANCELLED_OPERATION</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RPT
Accepted values: APPLICATION_INSTALL, APPLICATION_UNINSTALL, DEVICE_DRIVER_INSTALL, MODIFY_SETTINGS, CANCELLED_OPERATION

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="173dd-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="173dd-130">CommonParameters</span></span>

<span data-ttu-id="173dd-131">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="173dd-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="173dd-132">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="173dd-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="173dd-133">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="173dd-133">INPUTS</span></span>

### <span data-ttu-id="173dd-134">Keine</span><span class="sxs-lookup"><span data-stu-id="173dd-134">None</span></span>

<span data-ttu-id="173dd-135">Objekte können nicht an übergeben werden `Checkpoint-Computer` .</span><span class="sxs-lookup"><span data-stu-id="173dd-135">You cannot pipe objects to `Checkpoint-Computer`.</span></span>

## <span data-ttu-id="173dd-136">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="173dd-136">OUTPUTS</span></span>

### <span data-ttu-id="173dd-137">Keine</span><span class="sxs-lookup"><span data-stu-id="173dd-137">None</span></span>

<span data-ttu-id="173dd-138">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="173dd-138">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="173dd-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="173dd-139">NOTES</span></span>

- <span data-ttu-id="173dd-140">Dieses Cmdlet verwendet die Methode " **kreaterestorepoint** " der **SystemRestore** -Klasse mit einem **BEGIN_SYSTEM_CHANGE** -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="173dd-140">This cmdlet uses the **CreateRestorePoint** method of the **SystemRestore** class with a **BEGIN_SYSTEM_CHANGE** event.</span></span>
- <span data-ttu-id="173dd-141">Ab Windows 8 `Checkpoint-Computer` kann nicht täglich mehr als einen Systemwiederherstellungspunkt erstellen.</span><span class="sxs-lookup"><span data-stu-id="173dd-141">Beginning in Windows 8, `Checkpoint-Computer` cannot create more than one system restore point each day.</span></span> <span data-ttu-id="173dd-142">Wenn Sie einen neuen Wiederherstellungspunkt erstellen möchten, bevor die 24 Stunden abgelaufen sind, wird von Windows PowerShell der folgende Fehler ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="173dd-142">If you try to create a new restore point before the 24-hour period has elapsed, Windows PowerShell generates the following error:</span></span>

  `"A new system restore point cannot be created because one has already been created within the past 24 hours.
  Please try again later."`

## <span data-ttu-id="173dd-143">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="173dd-143">RELATED LINKS</span></span>

[<span data-ttu-id="173dd-144">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="173dd-144">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="173dd-145">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="173dd-145">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="173dd-146">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="173dd-146">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="173dd-147">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="173dd-147">Restore-Computer</span></span>](Restore-Computer.md)
