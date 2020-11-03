---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerrestorepoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerRestorePoint
ms.openlocfilehash: 73819aafee9ed1911354daf9af23eedff0a3e14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215479"
---
# <span data-ttu-id="77890-103">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="77890-103">Get-ComputerRestorePoint</span></span>

## <span data-ttu-id="77890-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="77890-104">SYNOPSIS</span></span>
<span data-ttu-id="77890-105">Ruft die Wiederherstellungspunkte auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="77890-105">Gets the restore points on the local computer.</span></span>

## <span data-ttu-id="77890-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="77890-106">SYNTAX</span></span>

### <span data-ttu-id="77890-107">ID (Standard)</span><span class="sxs-lookup"><span data-stu-id="77890-107">ID (Default)</span></span>

```
Get-ComputerRestorePoint [[-RestorePoint] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="77890-108">Last Status</span><span class="sxs-lookup"><span data-stu-id="77890-108">LastStatus</span></span>

```
Get-ComputerRestorePoint -LastStatus [<CommonParameters>]
```

## <span data-ttu-id="77890-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="77890-109">DESCRIPTION</span></span>

<span data-ttu-id="77890-110">Mit dem `Get-ComputerRestorePoint` -Cmdlet werden die System Wiederherstellungspunkte des lokalen Computers abgerufen.</span><span class="sxs-lookup"><span data-stu-id="77890-110">The `Get-ComputerRestorePoint` cmdlet gets the local computer's system restore points.</span></span> <span data-ttu-id="77890-111">Außerdem kann der Status des letzten Versuchs zum Wiederherstellen des Computers angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="77890-111">And, it can display the status of the most recent attempt to restore the computer.</span></span>

<span data-ttu-id="77890-112">Mit den Informationen aus können Sie `Get-ComputerRestorePoint` einen Wiederherstellungspunkt auswählen.</span><span class="sxs-lookup"><span data-stu-id="77890-112">You can use the information from `Get-ComputerRestorePoint` to select a restore point.</span></span> <span data-ttu-id="77890-113">Verwenden Sie z. b. eine Sequenznummer, um einen Wiederherstellungspunkt für das `Restore-Computer` Cmdlet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="77890-113">For example, use a sequence number to identify a restore point for the `Restore-Computer` cmdlet.</span></span>

<span data-ttu-id="77890-114">System Wiederherstellungspunkte und das `Get-ComputerRestorePoint` Cmdlet werden nur unter Client Betriebssystemen wie Windows 10, Windows 7, Windows Vista und Windows XP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77890-114">System restore points and the `Get-ComputerRestorePoint` cmdlet are supported only on client operating systems such as Windows 10, Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="77890-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="77890-115">EXAMPLES</span></span>

### <span data-ttu-id="77890-116">Beispiel 1: alle System Wiederherstellungspunkte</span><span class="sxs-lookup"><span data-stu-id="77890-116">Example 1: Get all system restore points</span></span>

<span data-ttu-id="77890-117">In diesem Beispiel werden `Get-ComputerRestorePoint` alle System Wiederherstellungspunkte des lokalen Computers abgerufen.</span><span class="sxs-lookup"><span data-stu-id="77890-117">In this example, `Get-ComputerRestorePoint` gets all the local computer's system restore points.</span></span>

```powershell
Get-ComputerRestorePoint
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
8/7/2019  12:56:45     Installed PowerShell 6-x64     6                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

### <span data-ttu-id="77890-118">Beispiel 2: beziehen bestimmter Sequenznummern</span><span class="sxs-lookup"><span data-stu-id="77890-118">Example 2: Get specific sequence numbers</span></span>

<span data-ttu-id="77890-119">In diesem Beispiel werden System Wiederherstellungspunkte für bestimmte Sequenznummern abgerufen.</span><span class="sxs-lookup"><span data-stu-id="77890-119">This example gets system restore points for specific sequence numbers.</span></span>

```powershell
Get-ComputerRestorePoint -RestorePoint 4, 5
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

<span data-ttu-id="77890-120">`Get-ComputerRestorePoint` verwendet den **RestorePoint** -Parameter, um ein durch Trennzeichen getrenntes Array von Sequenznummern anzugeben.</span><span class="sxs-lookup"><span data-stu-id="77890-120">`Get-ComputerRestorePoint` uses the **RestorePoint** parameter to specify a comma-separated array of sequence numbers.</span></span>

### <span data-ttu-id="77890-121">Beispiel 3: Anzeigen des Status einer Systemwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="77890-121">Example 3: Display the status of a system restore</span></span>

<span data-ttu-id="77890-122">In diesem Beispiel wird der Status der letzten Systemwiederherstellung auf dem lokalen Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="77890-122">This example displays the status of the most recent system restore on the local computer.</span></span>

```powershell
Get-ComputerRestorePoint -LastStatus
```

```Output
The last attempt to restore the computer failed.
```

<span data-ttu-id="77890-123">`Get-ComputerRestorePoint` verwendet den **laststatus** -Parameter, um das Ergebnis der letzten Systemwiederherstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="77890-123">`Get-ComputerRestorePoint` uses the **LastStatus** parameter to display the result of the most recent system restore.</span></span>

### <span data-ttu-id="77890-124">Beispiel 4: Verwenden eines Ausdrucks zum Konvertieren der "comationtime"</span><span class="sxs-lookup"><span data-stu-id="77890-124">Example 4: Use an expression to convert the CreationTime</span></span>

<span data-ttu-id="77890-125">`Get-ComputerRestorePoint` Gibt die **Zeichen** Folge "" als Windows-Verwaltungsinstrumentation (WMI)-Datums-und Uhrzeitangabe aus.</span><span class="sxs-lookup"><span data-stu-id="77890-125">`Get-ComputerRestorePoint` outputs the **CreationTime** as a Windows Management Instrumentation (WMI) date and time string.</span></span>

<span data-ttu-id="77890-126">In diesem Beispiel speichert eine Variable einen Ausdruck, der die Zeichenfolge " **comationtime** " in ein **DateTime** -Objekt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="77890-126">In this example, a variable stores an expression that converts the **CreationTime** string to a **DateTime** object.</span></span> <span data-ttu-id="77890-127">Verwenden Sie einen Befehl wie, um die vor der Konvertierung verwendeten Zeichen folgen vor dem **konvertieren anzuzeigen** `((Get-ComputerRestorePoint).CreationTime)` .</span><span class="sxs-lookup"><span data-stu-id="77890-127">To view **CreationTime** strings before they're converted, use a command such as `((Get-ComputerRestorePoint).CreationTime)`.</span></span> <span data-ttu-id="77890-128">Weitere Informationen zur Datums-und Uhrzeit Zeichenfolge von WMI finden Sie unter [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).</span><span class="sxs-lookup"><span data-stu-id="77890-128">For more information about the WMI date and time string, see [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).</span></span>

```powershell
$date = @{Label="Date"; Expression={$_.ConvertToDateTime($_.CreationTime)}}
Get-ComputerRestorePoint | Select-Object -Property SequenceNumber, $date, Description
```

```Output
SequenceNumber   Date                 Description
--------------   ----                 -----------
             4   7/30/2019 09:17:24   Windows Update
             5   8/5/2019  08:15:37   Installed PowerShell 7-preview-x64
             6   8/7/2019  12:56:45   Installed PowerShell 6-x64
```

<span data-ttu-id="77890-129">Die `$date` Variable speichert eine Hash Tabelle mit dem Ausdruck, der die **ConvertTo DateTime** -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="77890-129">The `$date` variable stores a hash table with the expression that uses the **ConvertToDateTime** method.</span></span> <span data-ttu-id="77890-130">Der Ausdruck konvertiert den Wert der Eigenschaft " **kreationtime** " aus einer WMI-Zeichenfolge in ein **DateTime** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="77890-130">The expression converts the **CreationTime** property's value from a WMI string to a **DateTime** object.</span></span>

<span data-ttu-id="77890-131">`Get-ComputerRestorePoint` sendet die Systemwiederherstellungspunkt Objekte über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="77890-131">`Get-ComputerRestorePoint` sends the system restore point objects down the pipeline.</span></span> <span data-ttu-id="77890-132">`Select-Object` verwendet den **Property** -Parameter, um die anzuzeigenden Eigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="77890-132">`Select-Object` uses the **Property** parameter to specify the properties to display.</span></span> <span data-ttu-id="77890-133">Für jedes Objekt in der Pipeline konvertiert der Ausdruck in `$date` die " **deationtime** " und gibt das Ergebnis in der **Date** -Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="77890-133">For each object in the pipeline, the expression in `$date` converts the **CreationTime** and outputs the result in the **Date** property.</span></span>

### <span data-ttu-id="77890-134">Beispiel 5: Verwenden einer Eigenschaft zum erhalten einer Sequenznummer</span><span class="sxs-lookup"><span data-stu-id="77890-134">Example 5: Use a property to get a sequence number</span></span>

<span data-ttu-id="77890-135">In diesem Beispiel wird eine Sequenznummer abgerufen, indem die **sequencenumschlag** -Eigenschaft und ein Array Index verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="77890-135">This example gets a sequence number by using the **SequenceNumber** property and an array index.</span></span> <span data-ttu-id="77890-136">Die Ausgabe enthält nur die Sequenznummer.</span><span class="sxs-lookup"><span data-stu-id="77890-136">The output only contains the sequence number.</span></span>

```powershell
((Get-ComputerRestorePoint).SequenceNumber)[-1]
```

```Output
6
```

<span data-ttu-id="77890-137">`Get-ComputerRestorePoint` verwendet die **sequencenumschlag** -Eigenschaft mit einem Array Index.</span><span class="sxs-lookup"><span data-stu-id="77890-137">`Get-ComputerRestorePoint` uses the **SequenceNumber** property with an array index.</span></span> <span data-ttu-id="77890-138">Der Array Index von ruft `-1` die letzte Sequenznummer im Array ab.</span><span class="sxs-lookup"><span data-stu-id="77890-138">The array index of `-1` gets the most recent sequence number in the array.</span></span>

## <span data-ttu-id="77890-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="77890-139">PARAMETERS</span></span>

### <span data-ttu-id="77890-140">-Laststatus</span><span class="sxs-lookup"><span data-stu-id="77890-140">-LastStatus</span></span>

<span data-ttu-id="77890-141">Gibt an, dass `Get-ComputerRestorePoint` den Status des letzten System Wiederherstellungs Vorgangs abruft.</span><span class="sxs-lookup"><span data-stu-id="77890-141">Indicates that `Get-ComputerRestorePoint` gets the status of the most recent system restore operation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LastStatus
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77890-142">-RestorePoint</span><span class="sxs-lookup"><span data-stu-id="77890-142">-RestorePoint</span></span>

<span data-ttu-id="77890-143">Gibt die Sequenznummern der System Wiederherstellungspunkte an.</span><span class="sxs-lookup"><span data-stu-id="77890-143">Specifies the sequence numbers of the system restore points.</span></span> <span data-ttu-id="77890-144">Sie können entweder eine einzelne Sequenznummer oder ein durch Trennzeichen getrenntes Array von Sequenznummern angeben.</span><span class="sxs-lookup"><span data-stu-id="77890-144">You can specify either a single sequence number or a comma-separated array of sequence numbers.</span></span>

<span data-ttu-id="77890-145">Wenn der **RestorePoint** -Parameter nicht angegeben wird, werden `Get-ComputerRestorePoint` von alle System Wiederherstellungspunkte des lokalen Computers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="77890-145">If the **RestorePoint** parameter isn't specified, `Get-ComputerRestorePoint` returns all the local computer's system restore points.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: ID
Aliases:

Required: False
Position: 0
Default value: All restore points
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="77890-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="77890-146">CommonParameters</span></span>

<span data-ttu-id="77890-147">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="77890-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="77890-148">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="77890-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="77890-149">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="77890-149">INPUTS</span></span>

### <span data-ttu-id="77890-150">Keine</span><span class="sxs-lookup"><span data-stu-id="77890-150">None</span></span>

<span data-ttu-id="77890-151">Objekte können nicht über die Pipeline an gesendet werden `Get-ComputerRestorePoint` .</span><span class="sxs-lookup"><span data-stu-id="77890-151">You can't send objects down the pipeline to `Get-ComputerRestorePoint`.</span></span>

## <span data-ttu-id="77890-152">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="77890-152">OUTPUTS</span></span>

### <span data-ttu-id="77890-153">System. Management. ManagementObject # root\default\systemrestore oder String</span><span class="sxs-lookup"><span data-stu-id="77890-153">System.Management.ManagementObject#root\default\SystemRestore or String</span></span>

<span data-ttu-id="77890-154">`Get-ComputerRestorePoint` Gibt ein **SystemRestore** -Objekt zurück, das eine Instanz der Windows-Verwaltungsinstrumentation (WMI) **SystemRestore** -Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="77890-154">`Get-ComputerRestorePoint` returns a **SystemRestore** object, which is an instance of the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

<span data-ttu-id="77890-155">Wenn Sie den **laststatus** -Parameter verwenden, wird `Get-ComputerRestorePoint` eine Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="77890-155">When you use the **LastStatus** parameter, `Get-ComputerRestorePoint` returns a string.</span></span>

## <span data-ttu-id="77890-156">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="77890-156">NOTES</span></span>

<span data-ttu-id="77890-157">Wenn Sie einen `Get-ComputerRestorePoint` Befehl unter Windows Vista und höheren Versionen von Windows ausführen möchten, öffnen Sie PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="77890-157">To run a `Get-ComputerRestorePoint` command on Windows Vista and later versions of Windows, open PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="77890-158">`Get-ComputerRestorePoint` verwendet die WMI **SystemRestore** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="77890-158">`Get-ComputerRestorePoint` uses the WMI **SystemRestore** class.</span></span>

## <span data-ttu-id="77890-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="77890-159">RELATED LINKS</span></span>

[<span data-ttu-id="77890-160">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="77890-160">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="77890-161">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="77890-161">about_Arrays</span></span>](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[<span data-ttu-id="77890-162">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="77890-162">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="77890-163">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="77890-163">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="77890-164">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="77890-164">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="77890-165">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="77890-165">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="77890-166">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="77890-166">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="77890-167">SystemRestore</span><span class="sxs-lookup"><span data-stu-id="77890-167">SystemRestore</span></span>](/windows/win32/sr/systemrestore)
