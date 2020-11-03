---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ControlPanelItem
ms.openlocfilehash: 368e385d51437f9ac93b700c929b185dce30a644
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214404"
---
# <span data-ttu-id="c6e27-103">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="c6e27-103">Show-ControlPanelItem</span></span>

## <span data-ttu-id="c6e27-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c6e27-104">SYNOPSIS</span></span>
<span data-ttu-id="c6e27-105">Öffnet Systemsteuerungselemente.</span><span class="sxs-lookup"><span data-stu-id="c6e27-105">Opens control panel items.</span></span>

## <span data-ttu-id="c6e27-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c6e27-106">SYNTAX</span></span>

### <span data-ttu-id="c6e27-107">Regularname (Standard)</span><span class="sxs-lookup"><span data-stu-id="c6e27-107">RegularName (Default)</span></span>

```
Show-ControlPanelItem [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="c6e27-108">CanonicalName</span><span class="sxs-lookup"><span data-stu-id="c6e27-108">CanonicalName</span></span>

```
Show-ControlPanelItem -CanonicalName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="c6e27-109">ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="c6e27-109">ControlPanelItem</span></span>

```
Show-ControlPanelItem [[-InputObject] <ControlPanelItem[]>] [<CommonParameters>]
```

## <span data-ttu-id="c6e27-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c6e27-110">DESCRIPTION</span></span>

<span data-ttu-id="c6e27-111">Mit dem- `Show-ControlPanelItem` Cmdlet werden System Steuerungselemente auf dem lokalen Computer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c6e27-111">The `Show-ControlPanelItem` cmdlet opens control panel items on the local computer.</span></span> <span data-ttu-id="c6e27-112">Sie können damit System Steuerungselemente nach Name, Kategorie oder Beschreibung auch auf Systemen ohne Benutzeroberfläche öffnen.</span><span class="sxs-lookup"><span data-stu-id="c6e27-112">You can use it to open control panel items by name, category, or description, even on systems that do not have a user interface.</span></span> <span data-ttu-id="c6e27-113">Sie können System Steuerungselemente über die Pipeline aus dem `Get-ControlPanelItem` Cmdlet an übergeben `Show-ControlPanelItem` .</span><span class="sxs-lookup"><span data-stu-id="c6e27-113">You can pipe control panel items from the `Get-ControlPanelItem` cmdlet to `Show-ControlPanelItem`.</span></span>

<span data-ttu-id="c6e27-114">`Show-ControlPanelItem` durchsucht nur System Steuerungselemente, die im System geöffnet werden können.</span><span class="sxs-lookup"><span data-stu-id="c6e27-114">`Show-ControlPanelItem` searches only control panel items that can be opened on the system.</span></span> <span data-ttu-id="c6e27-115">Auf Computern ohne **Systemsteuerung** oder **Datei-Explorer** werden `Show-ControlPanelItem` nur System Steuerungselemente durchsucht, die ohne diese Komponenten geöffnet werden können.</span><span class="sxs-lookup"><span data-stu-id="c6e27-115">On computers that do not have **Control Panel** or **File Explorer** , `Show-ControlPanelItem` searches only control panel items that can open without these components.</span></span>

<span data-ttu-id="c6e27-116">Dieses Cmdlet wurde in Windows PowerShell 3,0 eingeführt und funktioniert unter Windows 8, Windows Server 2012 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="c6e27-116">This cmdlet was introduced in Windows PowerShell 3.0 and works on Windows 8, Windows Server 2012, and higher versions.</span></span>

## <span data-ttu-id="c6e27-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c6e27-117">EXAMPLES</span></span>

### <span data-ttu-id="c6e27-118">Beispiel 1: Anzeigen eines System Steuerungs Elements</span><span class="sxs-lookup"><span data-stu-id="c6e27-118">Example 1: Show a control panel item</span></span>

<span data-ttu-id="c6e27-119">In diesem Beispiel wird das System Steuerungselement " **AutoPlay** " gestartet.</span><span class="sxs-lookup"><span data-stu-id="c6e27-119">This example launches the **AutoPlay** control panel item.</span></span>

```powershell
Show-ControlPanelItem -Name "AutoPlay"
```

### <span data-ttu-id="c6e27-120">Beispiel 2: Übergeben eines System Steuerungs Elements an dieses Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c6e27-120">Example 2: Pipe a control panel item to this cmdlet</span></span>

<span data-ttu-id="c6e27-121">In diesem Beispiel wird das System Steuerungselement **Windows Defender Firewall** auf dem lokalen Computer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c6e27-121">This example opens the **Windows Defender Firewall** control panel item on the local computer.</span></span>
<span data-ttu-id="c6e27-122">Der Name des System Steuerungs Elements "Windows-Firewall" hat sich gegenüber den Versionen von Windows geändert.</span><span class="sxs-lookup"><span data-stu-id="c6e27-122">The name of the Windows Firewall control panel item has changed over the versions of Windows.</span></span> <span data-ttu-id="c6e27-123">In diesem Beispiel wird ein Platzhalter Muster verwendet, um das System Steuerungselement zu finden.</span><span class="sxs-lookup"><span data-stu-id="c6e27-123">This example uses a wildcard pattern to find the control panel item.</span></span>

```powershell
Get-ControlPanelItem -Name "*Firewall" | Show-ControlPanelItem
```

<span data-ttu-id="c6e27-124">`Get-ControlPanelItem` Ruft das System Steuerungselement ab, das vom `Show-ControlPanelItem` Cmdlet geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="c6e27-124">`Get-ControlPanelItem` gets the control panel item and the `Show-ControlPanelItem` cmdlet opens it.</span></span>

### <span data-ttu-id="c6e27-125">Beispiel 3: Verwenden eines Dateinamens zum Öffnen eines Systemsteuerungselements</span><span class="sxs-lookup"><span data-stu-id="c6e27-125">Example 3: Use a file name to open a control panel item</span></span>

<span data-ttu-id="c6e27-126">In diesem Beispiel wird das System Steuerungselement " **Programme und Funktionen** " mithilfe des Anwendungs namens geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c6e27-126">This example opens the **Programs and Features** control panel item by using its application name.</span></span>

```powershell
appwiz.cpl
```

<span data-ttu-id="c6e27-127">Diese Methode ist eine Alternative zur Verwendung eines- `Show-ControlPanelItem` Befehls.</span><span class="sxs-lookup"><span data-stu-id="c6e27-127">This method is an alternative to using a `Show-ControlPanelItem` command.</span></span>

> [!NOTE]
> <span data-ttu-id="c6e27-128">In PowerShell können Sie die Dateierweiterung. cpl für System Steuerungs Dateien weglassen, da Sie im Wert der Umgebungsvariablen enthalten ist `$env:PathExt` .</span><span class="sxs-lookup"><span data-stu-id="c6e27-128">In PowerShell, you can omit the .cpl file extension for control panel files because it's included in the value of the `$env:PathExt` environment variable.</span></span>

## <span data-ttu-id="c6e27-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c6e27-129">PARAMETERS</span></span>

### <span data-ttu-id="c6e27-130">-CanonicalName</span><span class="sxs-lookup"><span data-stu-id="c6e27-130">-CanonicalName</span></span>

<span data-ttu-id="c6e27-131">Gibt System Steuerungselemente mithilfe der angegebenen kanonischen Namen oder Namensmuster an.</span><span class="sxs-lookup"><span data-stu-id="c6e27-131">Specifies control panel items by using the specified canonical names or name patterns.</span></span> <span data-ttu-id="c6e27-132">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c6e27-132">Wildcard characters are permitted.</span></span> <span data-ttu-id="c6e27-133">Wenn Sie mehrere Namen eingeben, öffnet dieses Cmdlet System Steuerungselemente, die mit einem der Namen identisch sind, als wären die Elemente in der Liste "Name" durch einen **or** -Operator getrennt.</span><span class="sxs-lookup"><span data-stu-id="c6e27-133">If you enter multiple names, this cmdlet opens control panel items that match any of the names, as if the items in the name list were separated by an **OR** operator.</span></span>

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

### <span data-ttu-id="c6e27-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c6e27-134">-InputObject</span></span>

<span data-ttu-id="c6e27-135">Gibt die zu öffnenden System Steuerungselemente durch das Senden von System Steuerungselement-Objekten an.</span><span class="sxs-lookup"><span data-stu-id="c6e27-135">Specifies control panel items to open by submitting control panel item objects.</span></span> <span data-ttu-id="c6e27-136">Geben Sie eine Variable ein, die System Steuerungselement-Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der System Steuerungselemente abruft, z `Get-ControlPanelItem` . b.</span><span class="sxs-lookup"><span data-stu-id="c6e27-136">Enter a variable that contains control panel item objects, or type a command or expression that gets control panel item objects, such as `Get-ControlPanelItem`.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ControlPanelItem[]
Parameter Sets: ControlPanelItem
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c6e27-137">-Name</span><span class="sxs-lookup"><span data-stu-id="c6e27-137">-Name</span></span>

<span data-ttu-id="c6e27-138">Gibt die Namen von System Steuerungselementen an.</span><span class="sxs-lookup"><span data-stu-id="c6e27-138">Specifies names of control panel items.</span></span> <span data-ttu-id="c6e27-139">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c6e27-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="c6e27-140">Wenn Sie mehrere Namen eingeben, öffnet dieses Cmdlet System Steuerungselemente, die mit einem der Namen identisch sind, als wären die Elemente in der Liste "Name" durch einen **or** -Operator getrennt.</span><span class="sxs-lookup"><span data-stu-id="c6e27-140">If you enter multiple names, this cmdlet opens control panel items that match any of the names, as if the items in the name list were separated by an **OR** operator.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="c6e27-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c6e27-141">CommonParameters</span></span>

<span data-ttu-id="c6e27-142">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c6e27-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c6e27-143">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c6e27-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c6e27-144">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c6e27-144">INPUTS</span></span>

### <span data-ttu-id="c6e27-145">System. String, Microsoft. PowerShell. Commands. controlpanelitem</span><span class="sxs-lookup"><span data-stu-id="c6e27-145">System.String, Microsoft.PowerShell.Commands.ControlPanelItem</span></span>

<span data-ttu-id="c6e27-146">Sie können ein Name-oder System Steuerungselement-Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="c6e27-146">You can pipe a name or control panel item object to this cmdlet.</span></span>

## <span data-ttu-id="c6e27-147">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c6e27-147">OUTPUTS</span></span>

### <span data-ttu-id="c6e27-148">Keine</span><span class="sxs-lookup"><span data-stu-id="c6e27-148">None</span></span>

<span data-ttu-id="c6e27-149">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="c6e27-149">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="c6e27-150">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c6e27-150">NOTES</span></span>

## <span data-ttu-id="c6e27-151">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c6e27-151">RELATED LINKS</span></span>

[<span data-ttu-id="c6e27-152">Get-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="c6e27-152">Get-ControlPanelItem</span></span>](Get-ControlPanelItem.md)
