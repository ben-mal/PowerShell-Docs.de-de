---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ControlPanelItem
ms.openlocfilehash: 51bc04b4de901a611330266b6b0f58471f998432
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215476"
---
# <span data-ttu-id="a726e-103">Get-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="a726e-103">Get-ControlPanelItem</span></span>

## <span data-ttu-id="a726e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a726e-104">SYNOPSIS</span></span>
<span data-ttu-id="a726e-105">Ruft Systemsteuerungselemente ab.</span><span class="sxs-lookup"><span data-stu-id="a726e-105">Gets control panel items.</span></span>

## <span data-ttu-id="a726e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a726e-106">SYNTAX</span></span>

### <span data-ttu-id="a726e-107">Regularname (Standard)</span><span class="sxs-lookup"><span data-stu-id="a726e-107">RegularName (Default)</span></span>

```
Get-ControlPanelItem [[-Name] <String[]>] [-Category <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="a726e-108">CanonicalName</span><span class="sxs-lookup"><span data-stu-id="a726e-108">CanonicalName</span></span>

```
Get-ControlPanelItem -CanonicalName <String[]> [-Category <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="a726e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a726e-109">DESCRIPTION</span></span>

<span data-ttu-id="a726e-110">Mit dem- `Get-ControlPanelItem` Cmdlet werden System Steuerungselemente auf dem lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a726e-110">The `Get-ControlPanelItem` cmdlet gets control panel items on the local computer.</span></span> <span data-ttu-id="a726e-111">Sie können damit Systemsteuerungselemente nach Name, Kategorie oder Beschreibung auch in Systemen ohne Benutzeroberfläche suchen.</span><span class="sxs-lookup"><span data-stu-id="a726e-111">You can use it to find control panel items by name, category, or description, even on systems that do not have a user interface.</span></span>

<span data-ttu-id="a726e-112">Mit diesem Cmdlet werden nur die System Steuerungselemente abgerufen, die im System geöffnet werden können.</span><span class="sxs-lookup"><span data-stu-id="a726e-112">This cmdlet gets only the control panel items that can be opened on the system.</span></span> <span data-ttu-id="a726e-113">Auf Computern ohne Systemsteuerung oder Datei-Explorer ruft dieses Cmdlet nur System Steuerungselemente ab, die ohne diese Komponenten geöffnet werden können.</span><span class="sxs-lookup"><span data-stu-id="a726e-113">On computers that do not have Control Panel or File Explorer, this cmdlet gets only control panel items that can open without these components.</span></span>

<span data-ttu-id="a726e-114">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a726e-114">This cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="a726e-115">Es funktioniert nur unter Windows 8 und Windows Server 2012 und neuer.</span><span class="sxs-lookup"><span data-stu-id="a726e-115">It works only on Windows 8 and Windows Server 2012 and newer.</span></span>

## <span data-ttu-id="a726e-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a726e-116">EXAMPLES</span></span>

### <span data-ttu-id="a726e-117">Beispiel 1: Abrufen aller Systemsteuerungselemente</span><span class="sxs-lookup"><span data-stu-id="a726e-117">Example 1: Get all control panel items</span></span>

<span data-ttu-id="a726e-118">Dieser Befehl ruft alle Systemsteuerungselemente auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="a726e-118">This command gets all control panel items on the local computer.</span></span>

```powershell
Get-ControlPanelItem
```

```Output
Name                          CanonicalName                 Category                      Description
----                          -------------                 --------                      -----------
Action Center                 Microsoft.ActionCenter        {System and Security}         Review recent messages and...
Administrative Tools          Microsoft.AdministrativeTools {System and Security}         Configure administrative s...
AutoPlay                      Microsoft.AutoPlay            {Hardware}                    Change default settings fo...
BitLocker Drive Encryption    Microsoft.BitLockerDriveEn... {System and Security}         Protect your computer usin...
Color Management              Microsoft.ColorManagement     {All Control Panel Items}     Change advanced color mana...
Credential Manager            Microsoft.CredentialManager   {User Accounts}               Manage your Windows Creden...
Date and Time                 Microsoft.DateAndTime         {Clock, Language, and Region} Set the date, time, and ti...
...
```

### <span data-ttu-id="a726e-119">Beispiel 2: Abrufen von Systemsteuerungselementen nach Name</span><span class="sxs-lookup"><span data-stu-id="a726e-119">Example 2: Get control panel items by name</span></span>

<span data-ttu-id="a726e-120">In diesem Beispiel werden System Steuerungselemente abgerufen, deren Namen Programm oder App enthalten.</span><span class="sxs-lookup"><span data-stu-id="a726e-120">This example gets control panel items that have Program or App in their names.</span></span>

```powershell
Get-ControlPanelItem -Name "*Program*", "*App*"
```

### <span data-ttu-id="a726e-121">Beispiel 3: Abrufen von Systemsteuerungselementen nach Kategorie</span><span class="sxs-lookup"><span data-stu-id="a726e-121">Example 3: Get control panel items by category</span></span>

<span data-ttu-id="a726e-122">Mit diesem Befehl werden alle System Steuerungselemente in Kategorien abgerufen, deren Namen eine Sicherheit aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a726e-122">This command gets all control panel items in categories that have Security in their names.</span></span>

```powershell
Get-ControlPanelItem -Category "*Security*"
```

### <span data-ttu-id="a726e-123">Beispiel 4: Öffnen eines Systemsteuerungselements</span><span class="sxs-lookup"><span data-stu-id="a726e-123">Example 4: Open a control panel item</span></span>

<span data-ttu-id="a726e-124">In diesem Beispiel wird das System Steuerungselement Windows-Firewall auf dem lokalen Computer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a726e-124">This example opens the Windows Firewall control panel item on the local computer.</span></span>

```powershell
Get-ControlPanelItem -Name "Windows Firewall" | Show-ControlPanelItem
```

<span data-ttu-id="a726e-125">Mit dem- `Get-ControlPanelItem` Cmdlet wird das System Steuerungselement abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a726e-125">The `Get-ControlPanelItem` cmdlet gets the control panel item.</span></span> <span data-ttu-id="a726e-126">Das `Show-ControlPanelItem` Cmdlet öffnet es.</span><span class="sxs-lookup"><span data-stu-id="a726e-126">The `Show-ControlPanelItem` cmdlet opens it.</span></span>

### <span data-ttu-id="a726e-127">Beispiel 5: Abrufen von Systemsteuerungselementen auf einem Remotecomputer</span><span class="sxs-lookup"><span data-stu-id="a726e-127">Example 5: Get control panel items on a remote computer</span></span>

<span data-ttu-id="a726e-128">In diesem Beispiel wird das BitLocker-Laufwerkverschlüsselung System Steuerungselement auf dem Remote Computer Server01 abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a726e-128">This example gets the BitLocker Drive Encryption control panel item on the Server01 remote computer.</span></span>
<span data-ttu-id="a726e-129">Das `Invoke-Command` Cmdlet führt das `Get-ControlPanelItem` Cmdlet Remote aus.</span><span class="sxs-lookup"><span data-stu-id="a726e-129">The `Invoke-Command` cmdlet runs the `Get-ControlPanelItem` cmdlet remotely.</span></span>

```powershell
Invoke-Command -ComputerName "Server01" {Get-ControlPanelItem -Name "BitLocker*" }
```

### <span data-ttu-id="a726e-130">Beispiel 6: Suchen der Beschreibungen von Systemsteuerungselementen</span><span class="sxs-lookup"><span data-stu-id="a726e-130">Example 6: Search the descriptions of control panel items</span></span>

<span data-ttu-id="a726e-131">In diesem Beispiel wird die **Description** -Eigenschaft der System Steuerungselemente durchsucht, um nur diejenigen zu erhalten, die das Name- **Gerät** enthalten.</span><span class="sxs-lookup"><span data-stu-id="a726e-131">This example searches the **Description** property of the control panel items to get only those that contain the name **Device**.</span></span>

```powershell
Get-ControlPanelItem | Where-Object {$_.Description -like "*Device*"}
```

```Output
Name                    CanonicalName                 Category    Description
----                    -------------                 --------    -----------
AutoPlay                Microsoft.AutoPlay            {Hardware}  Change default settings fo...
Devices and Printers    Microsoft.DevicesAndPrinters  {Hardware}  View and manage devices, p...
Sound                   Microsoft.Sound               {Hardware}  Configure your audio devic...
```

<span data-ttu-id="a726e-132">Mit dem- `Get-ControlPanelItem` Cmdlet werden alle System Steuerungselemente abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a726e-132">The `Get-ControlPanelItem` cmdlet gets all control panel items.</span></span> <span data-ttu-id="a726e-133">Mit dem- `Where-Object` Cmdlet werden die Elemente nach dem Wert der **Description** -Eigenschaft gefiltert.</span><span class="sxs-lookup"><span data-stu-id="a726e-133">The `Where-Object` cmdlet filters the items by the value of the **Description** property.</span></span>

## <span data-ttu-id="a726e-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a726e-134">PARAMETERS</span></span>

### <span data-ttu-id="a726e-135">-CanonicalName</span><span class="sxs-lookup"><span data-stu-id="a726e-135">-CanonicalName</span></span>

<span data-ttu-id="a726e-136">Gibt die System Steuerungselemente als Zeichen folgen Array mit ihren kanonischen Namen oder namens Mustern an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a726e-136">Specifies, as a string array, the control panel items by their canonical names or name patterns that this cmdlet gets.</span></span> <span data-ttu-id="a726e-137">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a726e-137">Wildcards are permitted.</span></span> <span data-ttu-id="a726e-138">Wenn Sie mehrere Namen eingeben, ruft dieses Cmdlet System Steuerungselemente ab, die mit einem der Namen identisch sind, als wären die Elemente in der Liste "Name" durch einen Operator "or" getrennt.</span><span class="sxs-lookup"><span data-stu-id="a726e-138">If you enter multiple names, this cmdlet gets control panel items that match any of the names, as though the items in the name list were separated by an "or" operator.</span></span>

<span data-ttu-id="a726e-139">Standardmäßig ruft dieses Cmdlet alle System Steuerungselemente im System ab.</span><span class="sxs-lookup"><span data-stu-id="a726e-139">By default, this cmdlet gets all control panel items in the system.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a726e-140">-Kategorie</span><span class="sxs-lookup"><span data-stu-id="a726e-140">-Category</span></span>

<span data-ttu-id="a726e-141">Gibt die Kategorien der System Steuerungselemente in den angegebenen Kategorien, die dieses Cmdlet abruft, als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="a726e-141">Specifies, as a string array, the categories of the control panel items in the specified categories that this cmdlet gets.</span></span> <span data-ttu-id="a726e-142">Geben Sie einen Kategorienamen oder ein Namensmuster ein.</span><span class="sxs-lookup"><span data-stu-id="a726e-142">Enter a category name or name pattern.</span></span> <span data-ttu-id="a726e-143">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a726e-143">Wildcards are permitted.</span></span> <span data-ttu-id="a726e-144">Wenn Sie mehrere Namen eingeben, ruft dieses Cmdlet System Steuerungselemente ab, die mit einem der Namen identisch sind, als wären die Elemente in der Liste "Name" durch einen Operator "or" getrennt.</span><span class="sxs-lookup"><span data-stu-id="a726e-144">If you enter multiple names, this cmdlet gets control panel items that match any of the names, as though the items in the name list were separated by an "or" operator.</span></span> <span data-ttu-id="a726e-145">Standardmäßig ruft dieses Cmdlet alle System Steuerungselemente im System ab.</span><span class="sxs-lookup"><span data-stu-id="a726e-145">By default, this cmdlet gets all control panel items in the system.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a726e-146">-Name</span><span class="sxs-lookup"><span data-stu-id="a726e-146">-Name</span></span>

<span data-ttu-id="a726e-147">Gibt die Namen oder Namensmuster der Systemsteuerung an, die von diesem Cmdlet abgerufen werden, als Zeichen folgen Array.</span><span class="sxs-lookup"><span data-stu-id="a726e-147">Specifies, as a string array, the names or name patterns of the control panel that this cmdlet gets.</span></span>
<span data-ttu-id="a726e-148">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a726e-148">Wildcards are permitted.</span></span> <span data-ttu-id="a726e-149">Sie können ein Name-oder Namensmuster auch über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="a726e-149">You can also pipe a name or name pattern to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="a726e-150">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a726e-150">CommonParameters</span></span>

<span data-ttu-id="a726e-151">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a726e-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a726e-152">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a726e-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a726e-153">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a726e-153">INPUTS</span></span>

### <span data-ttu-id="a726e-154">System.String</span><span class="sxs-lookup"><span data-stu-id="a726e-154">System.String</span></span>

<span data-ttu-id="a726e-155">Sie können einen Namen oder ein Namensmuster über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="a726e-155">You can pipe a name or name pattern to this cmdlet.</span></span>

## <span data-ttu-id="a726e-156">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a726e-156">OUTPUTS</span></span>

### <span data-ttu-id="a726e-157">Microsoft. PowerShell. Commands. controlpanelitem</span><span class="sxs-lookup"><span data-stu-id="a726e-157">Microsoft.PowerShell.Commands.ControlPanelItem</span></span>

<span data-ttu-id="a726e-158">Mit diesem Cmdlet werden System Steuerungselemente auf dem lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a726e-158">This cmdlet gets control panel items on the local computer.</span></span>

## <span data-ttu-id="a726e-159">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a726e-159">NOTES</span></span>

## <span data-ttu-id="a726e-160">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a726e-160">RELATED LINKS</span></span>

[<span data-ttu-id="a726e-161">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="a726e-161">Show-ControlPanelItem</span></span>](Show-ControlPanelItem.md)
