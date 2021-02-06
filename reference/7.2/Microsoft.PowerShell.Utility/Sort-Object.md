---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/sort-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sort-Object
ms.openlocfilehash: fead3b3d109a79186bc82f3c9f212f11f7b0bc57
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602525"
---
# <span data-ttu-id="2e125-102">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="2e125-102">Sort-Object</span></span>

## <span data-ttu-id="2e125-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2e125-103">SYNOPSIS</span></span>
<span data-ttu-id="2e125-104">Sortiert Objekte nach Eigenschaftenwerten.</span><span class="sxs-lookup"><span data-stu-id="2e125-104">Sorts objects by property values.</span></span>

## <span data-ttu-id="2e125-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e125-105">SYNTAX</span></span>

### <span data-ttu-id="2e125-106">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="2e125-106">Default (Default)</span></span>

```
Sort-Object [-Stable] [-Descending] [-Unique] [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

### <span data-ttu-id="2e125-107">TOP</span><span class="sxs-lookup"><span data-stu-id="2e125-107">Top</span></span>

```
Sort-Object [-Descending] [-Unique] -Top <Int32> [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

### <span data-ttu-id="2e125-108">bottom</span><span class="sxs-lookup"><span data-stu-id="2e125-108">Bottom</span></span>

```
Sort-Object [-Descending] [-Unique] -Bottom <Int32> [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="2e125-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2e125-109">DESCRIPTION</span></span>

<span data-ttu-id="2e125-110">Das- `Sort-Object` Cmdlet sortiert Objekte in aufsteigender oder absteigender Reihenfolge basierend auf Objekt Eigenschafts Werten.</span><span class="sxs-lookup"><span data-stu-id="2e125-110">The `Sort-Object` cmdlet sorts objects in ascending or descending order based on object property values.</span></span> <span data-ttu-id="2e125-111">Wenn Sortier Eigenschaften nicht in einem Befehl enthalten sind, verwendet PowerShell die Standard Sortier Eigenschaften des ersten Eingabe Objekts.</span><span class="sxs-lookup"><span data-stu-id="2e125-111">If sort properties are not included in a command, PowerShell uses default sort properties of the first input object.</span></span> <span data-ttu-id="2e125-112">Wenn der Typ des Eingabe Objekts keine Standard Sortier Eigenschaften aufweist, versucht PowerShell, die Objekte selbst zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="2e125-112">If the type of the input object has no default sort properties, PowerShell attempts to compare the objects themselves.</span></span> <span data-ttu-id="2e125-113">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="2e125-113">For more information, see the [Notes](#notes) section.</span></span>

<span data-ttu-id="2e125-114">Objekte können nach einer einzelnen Eigenschaft oder mehreren Eigenschaften sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e125-114">You can sort objects by a single property or multiple properties.</span></span> <span data-ttu-id="2e125-115">Mehrere Eigenschaften verwenden Hash Tabellen zum Sortieren in aufsteigender Reihenfolge, absteigender Reihenfolge oder in einer Kombination aus Sortier Reihenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2e125-115">Multiple properties use hash tables to sort in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="2e125-116">Eigenschaften werden nach Groß-/Kleinschreibung oder Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="2e125-116">Properties are sorted as case-sensitive or case-insensitive.</span></span> <span data-ttu-id="2e125-117">Verwenden Sie den **Unique** -Parameter, um Duplikate aus der Ausgabe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2e125-117">Use the **Unique** parameter to eliminate duplicates from the output.</span></span>

## <span data-ttu-id="2e125-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2e125-118">EXAMPLES</span></span>

### <span data-ttu-id="2e125-119">Beispiel 1: Sortieren des aktuellen Verzeichnisses nach Name</span><span class="sxs-lookup"><span data-stu-id="2e125-119">Example 1: Sort the current directory by name</span></span>

<span data-ttu-id="2e125-120">In diesem Beispiel werden die Dateien und Unterverzeichnisse in einem Verzeichnis sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-120">This example sorts the files and subdirectories in a directory.</span></span>

```
PS> Get-ChildItem -Path C:\Test | Sort-Object

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
d-----        2/25/2019     18:25                Files
d-----        2/25/2019     18:24                Logs
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
```

<span data-ttu-id="2e125-121">`Get-ChildItem`Mit dem-Cmdlet werden die Dateien und Unterverzeichnisse aus dem Verzeichnis abgerufen, das durch den **path** -Parameter **c:\test** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2e125-121">The `Get-ChildItem` cmdlet gets the files and subdirectories from the directory specified by the **Path** parameter, **C:\Test**.</span></span> <span data-ttu-id="2e125-122">Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2e125-122">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="2e125-123">`Sort-Object` gibt keine Eigenschaft an, sodass die Ausgabe nach der Standard Sortier Eigenschaft " **Name**" sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="2e125-123">`Sort-Object` does not specify a property so the output is sorted by the default sort property, **Name**.</span></span>

### <span data-ttu-id="2e125-124">Beispiel 2: Sortieren des aktuellen Verzeichnisses nach Dateilänge</span><span class="sxs-lookup"><span data-stu-id="2e125-124">Example 2: Sort the current directory by file length</span></span>

<span data-ttu-id="2e125-125">Mit diesem Befehl werden die Dateien im aktuellen Verzeichnis nach Länge in aufsteigender Reihenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e125-125">This command displays the files in the current directory by length in ascending order.</span></span>

```
PS> Get-ChildItem -Path C:\Test -File | Sort-Object -Property Length

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
-a----        2/13/2019     08:55             26 anotherfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-a----        2/12/2019     15:40         118014 Command.txt
```

<span data-ttu-id="2e125-126">Mit dem- `Get-ChildItem` Cmdlet werden die Dateien aus dem Verzeichnis abgerufen, das durch den **path** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2e125-126">The `Get-ChildItem` cmdlet gets the files from the directory specified by the **Path** parameter.</span></span>
<span data-ttu-id="2e125-127">Der **File** -Parameter gibt an, dass `Get-ChildItem` nur Datei Objekte abruft.</span><span class="sxs-lookup"><span data-stu-id="2e125-127">The **File** parameter specifies that `Get-ChildItem` only gets file objects.</span></span> <span data-ttu-id="2e125-128">Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2e125-128">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="2e125-129">`Sort-Object` verwendet den **length** -Parameter, um die Dateien nach Länge in aufsteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="2e125-129">`Sort-Object` uses the **Length** parameter to sort the files by length in ascending order.</span></span>

### <span data-ttu-id="2e125-130">Beispiel 3: Sortieren von Prozessen nach Speicherauslastung</span><span class="sxs-lookup"><span data-stu-id="2e125-130">Example 3: Sort processes by memory usage</span></span>

<span data-ttu-id="2e125-131">In diesem Beispiel werden Prozesse mit der höchsten Speicherauslastung basierend auf der Größe Ihres Arbeits Satzes (WS) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e125-131">This example displays processes with the highest memory usage based on their working set (WS) size.</span></span>

```
PS> Get-Process | Sort-Object -Property WS | Select-Object -Last 5

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    136   193.92     217.11     889.16   87492   8 OUTLOOK
    112   347.73     297.02      95.19  106908   8 Teams
    206   266.54     323.71      37.17   60620   8 MicrosoftEdgeCP
     35   552.19     549.94     131.66    6552   8 Code
      0     1.43     595.12       0.00    2780   0 Memory Compression
```

<span data-ttu-id="2e125-132">Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2e125-132">The `Get-Process` cmdlet gets the list of processes running on the computer.</span></span> <span data-ttu-id="2e125-133">Die Prozess Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2e125-133">The process objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="2e125-134">`Sort-Object` verwendet den **Property** -Parameter, um die Objekte nach **WS** zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="2e125-134">`Sort-Object` uses the **Property** parameter to sort the objects by **WS**.</span></span> <span data-ttu-id="2e125-135">Die Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2e125-135">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="2e125-136">`Select-Object` verwendet den **letzten** Parameter, um die letzten fünf Objekte anzugeben, die Objekte mit der höchsten **WS** -Verwendung sind.</span><span class="sxs-lookup"><span data-stu-id="2e125-136">`Select-Object` uses the **Last** parameter to specify the last five objects, which are the objects with the highest **WS** usage.</span></span>

<span data-ttu-id="2e125-137">In PowerShell 6 ist der- `Sort-Object` Parameter **unten** eine Alternative zu `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="2e125-137">In PowerShell 6, the `Sort-Object` parameter **Bottom** is an alternative to `Select-Object`.</span></span> <span data-ttu-id="2e125-138">Beispiel: `Get-Process | Sort-Object -Property WS -Bottom 5`.</span><span class="sxs-lookup"><span data-stu-id="2e125-138">For example, `Get-Process | Sort-Object -Property WS -Bottom 5`.</span></span>

### <span data-ttu-id="2e125-139">Beispiel 4: Sortieren von historyinfo-Objekten nach ID</span><span class="sxs-lookup"><span data-stu-id="2e125-139">Example 4: Sort HistoryInfo objects by Id</span></span>

<span data-ttu-id="2e125-140">Mit diesem Befehl werden die **historyinfo** -Objekte der PowerShell-Sitzung mithilfe der **ID** -Eigenschaft sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-140">This command sorts the PowerShell session's **HistoryInfo** objects using the **Id** property.</span></span> <span data-ttu-id="2e125-141">Jede PowerShell-Sitzung verfügt über einen eigenen Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="2e125-141">Each PowerShell session has its own command history.</span></span>

```
PS> Get-History | Sort-Object -Property Id -Descending

  Id CommandLine
  -- -----------
  10 Get-Command Sort-Object -Syntax
   9 $PSVersionTable
   8 Get-Command Sort-Object -Syntax
   7 Get-Command Sort-Object -ShowCommandInfo
   6 Get-ChildItem -Path C:\Test | Sort-Object -Property Length
   5 Get-Help Clear-History -online
   4 Get-Help Clear-History -full
   3 Get-ChildItem | Get-Member
   2 Get-Command Sort-Object -Syntax
   1 Set-Location C:\Test\
```

<span data-ttu-id="2e125-142">Mit dem- `Get-History` Cmdlet werden die Verlaufs Objekte aus der aktuellen PowerShell-Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2e125-142">The `Get-History` cmdlet gets the history objects from the current PowerShell session.</span></span> <span data-ttu-id="2e125-143">Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2e125-143">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="2e125-144">`Sort-Object` verwendet den **Property** -Parameter, um die Objekte nach **ID** zu sortieren. Der **Absteig** Ende Parameter sortiert den Befehlsverlauf vom neuesten zum ältesten.</span><span class="sxs-lookup"><span data-stu-id="2e125-144">`Sort-Object` uses the **Property** parameter to sort the objects by **Id**. The **Descending** parameter sorts the command history from newest to oldest.</span></span>

### <span data-ttu-id="2e125-145">Beispiel 5: Verwenden einer Hash Tabelle zum Sortieren von Eigenschaften in aufsteigender und absteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="2e125-145">Example 5: Use a hash table to sort properties in ascending and descending order</span></span>

<span data-ttu-id="2e125-146">In diesem Beispiel werden zwei Eigenschaften verwendet, um die Objekte " **Status** " und " **Display Name**" zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="2e125-146">This example uses two properties to sort the objects, **Status** and **DisplayName**.</span></span> <span data-ttu-id="2e125-147">Der **Status** wird in absteigender Reihenfolge sortiert, und **Display Name** wird in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-147">**Status** is sorted in descending order and **DisplayName** is sorted in ascending order.</span></span>

<span data-ttu-id="2e125-148">Eine Hash Tabelle wird verwendet, um den Wert des **Eigenschafts** Parameters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e125-148">A hash table is used to specify the **Property** parameter's value.</span></span> <span data-ttu-id="2e125-149">Die Hash Tabelle verwendet einen Ausdruck, um die Eigenschaften Namen und die Sortierreihenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e125-149">The hash table uses an expression to specify the property names and sort orders.</span></span> <span data-ttu-id="2e125-150">Weitere Informationen zu Hashtabellen finden Sie unter [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md) (Informationen zu Hashtabellen).</span><span class="sxs-lookup"><span data-stu-id="2e125-150">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="2e125-151">Die in der Hash Tabelle verwendete **Status** Eigenschaft ist eine enumerierte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2e125-151">The **Status** property used in the hash table is an enumerated property.</span></span>
<span data-ttu-id="2e125-152">Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="2e125-152">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

```
PS C:\> Get-Service | Sort-Object -Property @{Expression = "Status"; Descending = $True}, @{Expression = "DisplayName"; Descending = $False}

Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  BthAvctpSvc        AVCTP service
Running  BrokerInfrastru... Background Tasks Infrastructure Ser...
Running  BDESVC             BitLocker Drive Encryption Service
Running  CoreMessagingRe... CoreMessaging
Running  VaultSvc           Credential Manager
Running  DsSvc              Data Sharing Service
Running  Dhcp               DHCP Client
...
Stopped  ALG                Application Layer Gateway Service
Stopped  AppMgmt            Application Management
Stopped  BITS               Background Intelligent Transfer Ser...
Stopped  wbengine           Block Level Backup Engine Service
Stopped  BluetoothUserSe... Bluetooth User Support Service_14fb...
Stopped  COMSysApp          COM+ System Application
Stopped  smstsmgr           ConfigMgr Task Sequence Agent
Stopped  DeviceInstall      Device Install Service
Stopped  MSDTC              Distributed Transaction Coordinator
```

<span data-ttu-id="2e125-153">Mit dem- `Get-Service` Cmdlet wird die Liste der Dienste auf dem Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2e125-153">The `Get-Service` cmdlet gets the list of services on the computer.</span></span> <span data-ttu-id="2e125-154">Die Dienst Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2e125-154">The service objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="2e125-155">`Sort-Object` verwendet den **Property** -Parameter mit einer Hash Tabelle, um die Eigenschaften Namen und die Sortierreihenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e125-155">`Sort-Object` uses the **Property** parameter with a hash table to specify the property names and sort orders.</span></span> <span data-ttu-id="2e125-156">Der **Property** -Parameter wird nach zwei Eigenschaften sortiert: **Status** in absteigender Reihenfolge und **Display Name** in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="2e125-156">The **Property** parameter is sorted by two properties, **Status** in descending order and **DisplayName** in ascending order.</span></span>

<span data-ttu-id="2e125-157">Der **Status** ist eine aufgezählte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2e125-157">**Status** is an enumerated property.</span></span> <span data-ttu-id="2e125-158">" **Beendet** " hat den Wert " **1** " und "wird **ausgeführt** " den Wert **4**.</span><span class="sxs-lookup"><span data-stu-id="2e125-158">**Stopped** has a value of **1** and **Running** has a value of **4**.</span></span> <span data-ttu-id="2e125-159">Der **Absteig** Ende Parameter ist auf festgelegt `$True` , sodass ausgestellte  Prozesse vor beendeten Prozessen angezeigt werden. </span><span class="sxs-lookup"><span data-stu-id="2e125-159">The **Descending** parameter is set to `$True` so that **Running** processes are displayed before **Stopped** processes.</span></span> <span data-ttu-id="2e125-160">**Display Name** legt den **Absteig** enden Parameter auf fest `$False` , um die anzeigen Amen in alphabetischer Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="2e125-160">**DisplayName** sets the **Descending** parameter to `$False` to sort the display names in alphabetical order.</span></span>

### <span data-ttu-id="2e125-161">Beispiel 6: Sortieren von Textdateien nach Zeitspanne</span><span class="sxs-lookup"><span data-stu-id="2e125-161">Example 6: Sort text files by time span</span></span>

<span data-ttu-id="2e125-162">Dieser Befehl sortiert Textdateien in absteigender Reihenfolge nach der Zeitspanne zwischen " **comationtime** " und " **lastschreitetime**".</span><span class="sxs-lookup"><span data-stu-id="2e125-162">This command sorts text files in descending order by the time span between **CreationTime** and **LastWriteTime**.</span></span>

```
PS> Get-ChildItem -Path C:\Test\*.txt | Sort-Object -Property @{Expression = {$_.CreationTime - $_.LastWriteTime}; Descending = $False} | Format-Table CreationTime, LastWriteTime, FullName

CreationTime          LastWriteTime        FullName
------------          -------------        --------
11/21/2018 12:39:01   2/26/2019 08:59:36   C:\Test\test2.txt
12/4/2018 08:29:41    2/26/2019 08:57:05   C:\Test\powershell_list.txt
2/20/2019 08:15:59    2/26/2019 12:09:43   C:\Test\CreateTestFile.txt
2/20/2019 08:15:59    2/26/2019 12:07:41   C:\Test\Command.txt
2/20/2019 08:15:59    2/26/2019 08:57:52   C:\Test\ReadOnlyFile.txt
11/29/2018 15:16:50   12/4/2018 16:16:24   C:\Test\LogData.txt
2/25/2019 18:25:11    2/26/2019 12:08:47   C:\Test\Zsystemlog.txt
2/25/2019 18:25:11    2/26/2019 08:55:33   C:\Test\Bfile.txt
2/26/2019 08:46:59    2/26/2019 12:12:19   C:\Test\LogFile3.txt
```

<span data-ttu-id="2e125-163">Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis **c:\test** und alle `*.txt` Dateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e125-163">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** and all of the `*.txt` files.</span></span> <span data-ttu-id="2e125-164">Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2e125-164">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="2e125-165">`Sort-Object` verwendet den **Property** -Parameter mit einer Hash Tabelle, um die Zeitspanne zwischen " **comationtime** " und " **LastWrite-Time**" zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="2e125-165">`Sort-Object` uses the **Property** parameter with a hash table to determine each files time span between **CreationTime** and **LastWriteTime**.</span></span> <span data-ttu-id="2e125-166">Der **Absteig** Ende Parameter ist auf festgelegt, um `$False` in der Reihenfolge der längsten bis zum kürzesten Zeitspanne zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="2e125-166">The **Descending** parameter is set to `$False` to sort in the order of longest to shortest time span.</span></span>

### <span data-ttu-id="2e125-167">Beispiel 7: Sortieren von Namen in einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="2e125-167">Example 7: Sort names in a text file</span></span>

<span data-ttu-id="2e125-168">In diesem Beispiel wird gezeigt, wie eine Liste aus einer Textdatei sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="2e125-168">This example shows how to sort a list from a text file.</span></span> <span data-ttu-id="2e125-169">Die ursprüngliche Datei wird als unsortierte Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e125-169">The original file is displayed as an unsorted list.</span></span> <span data-ttu-id="2e125-170">`Sort-Object` sortiert den Inhalt und sortiert dann den Inhalt mit dem **eindeutigen** Parameter, der Duplikate entfernt.</span><span class="sxs-lookup"><span data-stu-id="2e125-170">`Sort-Object` sorts the contents and then sorts the contents with the **Unique** parameter that removes duplicates.</span></span>

```
PS> Get-Content -Path C:\Test\ServerNames.txt
localhost
server01
server25
LOCALHOST
Server19
server3
localhost

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object
localhost
LOCALHOST
localhost
server01
Server19
server25
server3

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object -Unique
localhost
server01
Server19
server25
server3
```

<span data-ttu-id="2e125-171">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis und den Dateinamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e125-171">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="2e125-172">Die Datei **ServerNames.txt** enthält eine unsortierte Liste mit Computernamen.</span><span class="sxs-lookup"><span data-stu-id="2e125-172">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span>

<span data-ttu-id="2e125-173">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis und den Dateinamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e125-173">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="2e125-174">Die Datei **ServerNames.txt** enthält eine unsortierte Liste mit Computernamen.</span><span class="sxs-lookup"><span data-stu-id="2e125-174">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="2e125-175">Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2e125-175">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="2e125-176">`Sort-Object` sortiert die Liste in der Standard Reihenfolge aufsteigend.</span><span class="sxs-lookup"><span data-stu-id="2e125-176">`Sort-Object` sorts the list in the default order, ascending.</span></span>

<span data-ttu-id="2e125-177">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis und den Dateinamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e125-177">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="2e125-178">Die Datei **ServerNames.txt** enthält eine unsortierte Liste mit Computernamen.</span><span class="sxs-lookup"><span data-stu-id="2e125-178">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="2e125-179">Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2e125-179">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="2e125-180">`Sort-Object` verwendet den **Unique** -Parameter, um doppelte Computernamen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2e125-180">`Sort-Object` uses the **Unique** parameter to remove duplicate computer names.</span></span> <span data-ttu-id="2e125-181">Die Liste wird in der Standard Reihenfolge aufsteigend sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-181">The list is sorted in the default order, ascending.</span></span>

### <span data-ttu-id="2e125-182">Beispiel 8: Sortieren einer Zeichenfolge als ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="2e125-182">Example 8: Sort a string as an integer</span></span>

<span data-ttu-id="2e125-183">In diesem Beispiel wird gezeigt, wie eine Textdatei, die Zeichen folgen Objekte enthält, als ganze Zahlen sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="2e125-183">This example shows how to sort a text file that contains string objects as integers.</span></span> <span data-ttu-id="2e125-184">Sie können jeden Befehl über die Pipeline an senden `Get-Member` und überprüfen, ob es sich bei den Objekten um Zeichen folgen anstelle von ganzen Zahlen handelt.</span><span class="sxs-lookup"><span data-stu-id="2e125-184">You can send each command down the pipeline to `Get-Member` and verify that the objects are strings instead of integers.</span></span> <span data-ttu-id="2e125-185">In diesen Beispielen enthält die `ProductId.txt` Datei eine unsortierte Liste mit Produktnummern.</span><span class="sxs-lookup"><span data-stu-id="2e125-185">For these examples, the `ProductId.txt` file contains an unsorted list of product numbers.</span></span>

<span data-ttu-id="2e125-186">Im ersten Beispiel `Get-Content` wird der Inhalt der Datei abgerufen und Zeilen an das `Sort-Object` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="2e125-186">In the first example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="2e125-187">`Sort-Object` sortiert die Zeichen folgen Objekte in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="2e125-187">`Sort-Object` sorts the string objects in ascending order.</span></span>

```
PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object
0
1
12345
1500
2
2800
3500
4100
500
6200
77
88
99999

PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object {[int]$_}
0
1
2
77
88
500
1500
2800
3500
4100
6200
12345
99999
```

<span data-ttu-id="2e125-188">Im zweiten Beispiel `Get-Content` wird der Inhalt der Datei abgerufen und Zeilen an das `Sort-Object` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="2e125-188">In the second example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="2e125-189">`Sort-Object` verwendet einen Skriptblock, um die Zeichen folgen in ganze Zahlen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2e125-189">`Sort-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="2e125-190">Im Beispielcode `[int]` konvertiert die Zeichenfolge in eine ganze Zahl und `$_` stellt jede Zeichenfolge dar, wenn Sie in der Pipeline angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2e125-190">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="2e125-191">Die ganzzahligen Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="2e125-191">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="2e125-192">`Sort-Object` sortiert die ganzzahligen Objekte in numerischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="2e125-192">`Sort-Object` sorts the integer objects in numeric order.</span></span>

### <span data-ttu-id="2e125-193">Beispiel 9: verwenden stabiler Sortierungen</span><span class="sxs-lookup"><span data-stu-id="2e125-193">Example 9: Using stable sorts</span></span>

<span data-ttu-id="2e125-194">Wenn Sie die Parameter **Top**, **Bottom** oder **stable** verwenden, werden die sortierten Objekte in der Reihenfolge zugestellt, in der Sie empfangen wurden, `Sort-Object` Wenn die Sortierkriterien gleich sind.</span><span class="sxs-lookup"><span data-stu-id="2e125-194">When you use the **Top**, **Bottom**, or **Stable** parameters, the sorted objects are delivered in the order they were received by `Sort-Object` when the sort criteria are equal.</span></span> <span data-ttu-id="2e125-195">In diesem Beispiel sortieren wir die Zahlen 1 bis 20 durch den Wert "Modulo 3".</span><span class="sxs-lookup"><span data-stu-id="2e125-195">In this example, we are sorting the numbers one through 20 by the their value 'modulo 3'.</span></span> <span data-ttu-id="2e125-196">Der Modulo-Wert liegt zwischen 0 und 2.</span><span class="sxs-lookup"><span data-stu-id="2e125-196">The modulo value ranges from zero to two.</span></span>

```powershell
PS> 1..20 |Sort-Object {$_ % 3}
18
3
15
6
12
9
1
16
13
10
7
4
19
11
8
14
5
17
2
20

PS> 1..20 |Sort-Object {$_ % 3} -Stable
3
6
9
12
15
18
1
4
7
10
13
16
19
2
5
8
11
14
17
20
```

<span data-ttu-id="2e125-197">Die Ausgabe der ersten Sortierung ist ordnungsgemäß nach dem Modulo-Wert gruppiert, aber die einzelnen Elemente werden nicht innerhalb des Modulo Bereichs sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-197">The output from the first sort is correctly grouped by the modulus value but the individual items are not sorted within the modulus range.</span></span> <span data-ttu-id="2e125-198">Die zweite Sortierung verwendet die Option **stable** , um eine stabile Sortierung zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e125-198">The second sort uses the **Stable** option to return a stable sort.</span></span>

## <span data-ttu-id="2e125-199">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e125-199">PARAMETERS</span></span>

### <span data-ttu-id="2e125-200">-Unten</span><span class="sxs-lookup"><span data-stu-id="2e125-200">-Bottom</span></span>

<span data-ttu-id="2e125-201">Gibt die Anzahl der Objekte an, die vom Ende eines sortierten Objekt Arrays abgeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2e125-201">Specifies the number of objects to get from the end of a sorted object array.</span></span> <span data-ttu-id="2e125-202">Dies führt zu einer stabilen Sortierung.</span><span class="sxs-lookup"><span data-stu-id="2e125-202">This results in a stable sort.</span></span>

<span data-ttu-id="2e125-203">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2e125-203">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Bottom
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e125-204">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="2e125-204">-CaseSensitive</span></span>

<span data-ttu-id="2e125-205">Gibt an, dass die Sortierung die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="2e125-205">Indicates that the sort is case-sensitive.</span></span> <span data-ttu-id="2e125-206">Standardmäßig wird bei Sortierungen die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="2e125-206">By default, sorts are not case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Case-insensitive
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e125-207">-Kultur</span><span class="sxs-lookup"><span data-stu-id="2e125-207">-Culture</span></span>

<span data-ttu-id="2e125-208">Gibt die Kultur Konfiguration an, die für Sortiervorgänge verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2e125-208">Specifies the cultural configuration to use for sorts.</span></span> <span data-ttu-id="2e125-209">Verwenden `Get-Culture` Sie, um die Kultur Konfiguration des Systems anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2e125-209">Use `Get-Culture` to display the system's culture configuration.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e125-210">-Absteigend</span><span class="sxs-lookup"><span data-stu-id="2e125-210">-Descending</span></span>

<span data-ttu-id="2e125-211">Gibt an, dass `Sort-Object` die Objekte in absteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-211">Indicates that `Sort-Object` sorts the objects in descending order.</span></span> <span data-ttu-id="2e125-212">Standardmäßig wird in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-212">The default is ascending order.</span></span>

<span data-ttu-id="2e125-213">Wenn Sie mehrere Eigenschaften mit unterschiedlichen Sortier Reihenfolgen sortieren möchten, verwenden Sie eine Hash Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2e125-213">To sort multiple properties with different sort orders, use a hash table.</span></span> <span data-ttu-id="2e125-214">Beispielsweise können Sie mit einer Hash Tabelle eine Eigenschaft in aufsteigender Reihenfolge und eine andere Eigenschaft in absteigender Reihenfolge sortieren.</span><span class="sxs-lookup"><span data-stu-id="2e125-214">For example, with a hash table you can sort one property in ascending order and another property in descending order.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Ascending
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e125-215">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2e125-215">-InputObject</span></span>

<span data-ttu-id="2e125-216">Um Objekte zu sortieren, senden Sie Sie über die Pipeline an `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="2e125-216">To sort objects, send them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="2e125-217">Wenn Sie den **Inputobject** -Parameter verwenden, um eine Auflistung von Elementen zu senden, `Sort-Object` empfängt ein Objekt, das die Auflistung darstellt.</span><span class="sxs-lookup"><span data-stu-id="2e125-217">If you use the **InputObject** parameter to submit a collection of items, `Sort-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="2e125-218">Da ein Objekt nicht sortiert werden kann, `Sort-Object` gibt die gesamte Auflistung unverändert zurück.</span><span class="sxs-lookup"><span data-stu-id="2e125-218">Because one object cannot be sorted, `Sort-Object` returns the entire collection unchanged.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2e125-219">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2e125-219">-Property</span></span>

<span data-ttu-id="2e125-220">Gibt die Eigenschaftsnamen `Sort-Object` an, die von zum Sortieren der Objekte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e125-220">Specifies the property names that `Sort-Object` uses to sort the objects.</span></span> <span data-ttu-id="2e125-221">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="2e125-221">Wildcards are permitted.</span></span>
<span data-ttu-id="2e125-222">Objekte werden basierend auf den Eigenschafts Werten sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-222">Objects are sorted based on the property values.</span></span> <span data-ttu-id="2e125-223">Wenn Sie keine Eigenschaft angeben, sortiert nach `Sort-Object` den Standardeigenschaften für den Objekttyp oder die Objekte.</span><span class="sxs-lookup"><span data-stu-id="2e125-223">If you do not specify a property, `Sort-Object` sorts based on default properties for the object type or the objects themselves.</span></span>

<span data-ttu-id="2e125-224">Mehrere Eigenschaften können in aufsteigender Reihenfolge, absteigender Reihenfolge oder in einer Kombination aus Sortier Reihenfolgen sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e125-224">Multiple properties can be sorted in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="2e125-225">Wenn Sie mehrere Eigenschaften angeben, werden die Objekte nach der ersten Eigenschaft sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-225">When you specify multiple properties, the objects are sorted by the first property.</span></span> <span data-ttu-id="2e125-226">Wenn mehrere Objekte denselben Wert für die erste Eigenschaft aufweisen, werden diese Objekte nach der zweiten Eigenschaft sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-226">If multiple objects have the same value for the first property, those objects are sorted by the second property.</span></span> <span data-ttu-id="2e125-227">Dieser Prozess wird fortgesetzt, bis keine weiteren angegebenen Eigenschaften oder keine Gruppen von Objekten mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2e125-227">This process continues until there are no more specified properties or no groups of objects.</span></span>

<span data-ttu-id="2e125-228">Der Wert des **Property** -Parameters kann eine berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="2e125-228">The **Property** parameter's value can be a calculated property.</span></span> <span data-ttu-id="2e125-229">Zum Erstellen einer berechneten Eigenschaft verwenden Sie eine Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="2e125-229">To create a calculated property, use a hash table.</span></span>

<span data-ttu-id="2e125-230">Gültige Schlüssel für eine Hash Tabelle sind:</span><span class="sxs-lookup"><span data-stu-id="2e125-230">Valid keys for a hash table are as follows:</span></span>

- <span data-ttu-id="2e125-231">`expression` - `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="2e125-231">`expression` - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="2e125-232">`ascending` noch `descending` - `<boolean>`</span><span class="sxs-lookup"><span data-stu-id="2e125-232">`ascending` or `descending` - `<boolean>`</span></span>

<span data-ttu-id="2e125-233">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="2e125-233">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: Default properties
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="2e125-234">-Top</span><span class="sxs-lookup"><span data-stu-id="2e125-234">-Top</span></span>

<span data-ttu-id="2e125-235">Gibt die Anzahl der Objekte an, die vom Anfang eines sortierten Objekt Arrays abzurufenden werden.</span><span class="sxs-lookup"><span data-stu-id="2e125-235">Specifies the number of objects to get from the start of a sorted object array.</span></span> <span data-ttu-id="2e125-236">Dies führt zu einer stabilen Sortierung.</span><span class="sxs-lookup"><span data-stu-id="2e125-236">This results in a stable sort.</span></span>

<span data-ttu-id="2e125-237">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2e125-237">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Top
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e125-238">-Eindeutig</span><span class="sxs-lookup"><span data-stu-id="2e125-238">-Unique</span></span>

<span data-ttu-id="2e125-239">Gibt an, dass `Sort-Object` Duplikate entfernt und nur die eindeutigen Member der Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2e125-239">Indicates that `Sort-Object` eliminates duplicates and returns only the unique members of the collection.</span></span> <span data-ttu-id="2e125-240">Die erste Instanz eines eindeutigen Werts ist in der sortierten Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="2e125-240">The first instance of a unique value is included in the sorted output.</span></span>

<span data-ttu-id="2e125-241">Bei **Unique** wird Groß-/Kleinschreibung nicht beachtet</span><span class="sxs-lookup"><span data-stu-id="2e125-241">**Unique** is case-insensitive.</span></span> <span data-ttu-id="2e125-242">Zeichen folgen, die sich nur durch Zeichen Fälle unterscheiden, werden als identisch betrachtet.</span><span class="sxs-lookup"><span data-stu-id="2e125-242">Strings that only differ by character case are considered the same.</span></span>
<span data-ttu-id="2e125-243">Beispielsweise Zeichen und Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2e125-243">For example, character and CHARACTER.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e125-244">-Stabil</span><span class="sxs-lookup"><span data-stu-id="2e125-244">-Stable</span></span>

<span data-ttu-id="2e125-245">Die sortierten Objekte werden in der Reihenfolge zugestellt, in der Sie empfangen wurden, wenn die Sortierkriterien gleich sind.</span><span class="sxs-lookup"><span data-stu-id="2e125-245">The sorted objects are delivered in the order they were received when the sort criteria are equal.</span></span>

<span data-ttu-id="2e125-246">Dieser Parameter wurde in PowerShell v 6.2.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2e125-246">This parameter was added in PowerShell v6.2.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e125-247">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2e125-247">CommonParameters</span></span>

<span data-ttu-id="2e125-248">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2e125-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e125-249">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2e125-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e125-250">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2e125-250">INPUTS</span></span>

### <span data-ttu-id="2e125-251">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="2e125-251">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2e125-252">Sie können die zu sortierenden Objekte über die Pipeline übergeben `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="2e125-252">You can pipe the objects to be sorted to `Sort-Object`.</span></span>

## <span data-ttu-id="2e125-253">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2e125-253">OUTPUTS</span></span>

### <span data-ttu-id="2e125-254">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="2e125-254">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2e125-255">`Sort-Object` Gibt die sortierten Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="2e125-255">`Sort-Object` returns the sorted objects.</span></span>

## <span data-ttu-id="2e125-256">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2e125-256">NOTES</span></span>

<span data-ttu-id="2e125-257">Das- `Sort-Object` Cmdlet sortiert Objekte auf der Grundlage der im-Befehl angegebenen Eigenschaften oder der Standard Sortierungs Eigenschaften für den Objekttyp.</span><span class="sxs-lookup"><span data-stu-id="2e125-257">The `Sort-Object` cmdlet sorts objects based on properties specified in the command or the default sort properties for the object type.</span></span> <span data-ttu-id="2e125-258">Standard Sortier Eigenschaften werden mit dem `PropertySet` benannten `DefaultKeyPropertySet` in einer `types.ps1xml` Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-258">Default sort properties are defined using the `PropertySet` named `DefaultKeyPropertySet` in a `types.ps1xml` file.</span></span> <span data-ttu-id="2e125-259">Weitere Informationen finden Sie unter [about_Types.ps1XML](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="2e125-259">For more information, see [about_Types.ps1xml](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span></span>

<span data-ttu-id="2e125-260">Wenn ein Objekt keine der angegebenen Eigenschaften aufweist, wird der Eigenschafts Wert für dieses Objekt von `Sort-Object` als **null** interpretiert und am Ende der Sortierreihenfolge platziert.</span><span class="sxs-lookup"><span data-stu-id="2e125-260">If an object does not have one of the specified properties, the property value for that object is interpreted by `Sort-Object` as **Null** and placed at the end of the sort order.</span></span>

<span data-ttu-id="2e125-261">Wenn keine Sortier Eigenschaften verfügbar sind, versucht PowerShell, die Objekte selbst zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="2e125-261">When no sort properties are available, PowerShell attempts to compare the objects themselves.</span></span>
<span data-ttu-id="2e125-262">`Sort-Object` verwendet die **Compare** -Methode für jede Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2e125-262">`Sort-Object` uses the **Compare** method for each property.</span></span> <span data-ttu-id="2e125-263">Wenn eine Eigenschaft **ivergleichbare** nicht implementiert, konvertiert das Cmdlet den Eigenschafts Wert in eine Zeichenfolge und verwendet die **Compare** -Methode für **System. String**.</span><span class="sxs-lookup"><span data-stu-id="2e125-263">If a property does not implement **IComparable**, the cmdlet converts the property value to a string and uses the **Compare** method for **System.String**.</span></span> <span data-ttu-id="2e125-264">Weitere Informationen finden Sie unter [psobject. CompareTo (Object)-Methode](/dotnet/api/system.management.automation.psobject.compareto).</span><span class="sxs-lookup"><span data-stu-id="2e125-264">For more information, see [PSObject.CompareTo(Object) Method](/dotnet/api/system.management.automation.psobject.compareto).</span></span>

<span data-ttu-id="2e125-265">Wenn Sie nach einer enumerierten Eigenschaft wie dem **Status** sortieren, `Sort-Object` sortiert nach den Enumerationswerten.</span><span class="sxs-lookup"><span data-stu-id="2e125-265">If you sort on an enumerated property such as **Status**, `Sort-Object` sorts by the enumeration values.</span></span> <span data-ttu-id="2e125-266">Für Windows-Dienste hat " **beendet** " den Wert **1** und "wird **ausgeführt** " den Wert **4**.</span><span class="sxs-lookup"><span data-stu-id="2e125-266">For Windows services, **Stopped** has a value of **1** and **Running** has a value of **4**.</span></span>
<span data-ttu-id="2e125-267">" **Beendet** " wird vor dem **Ausführen** aufgrund der aufgelisteten Werte sortiert.</span><span class="sxs-lookup"><span data-stu-id="2e125-267">**Stopped** is sorted before **Running** because of the enumerated values.</span></span> <span data-ttu-id="2e125-268">Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="2e125-268">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="2e125-269">Die Leistung des Sortieralgorithmus ist langsamer, wenn ein stabiler Sortiervorgang durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2e125-269">The performance of the sorting algorithm is slower when doing a stable sort.</span></span>

## <span data-ttu-id="2e125-270">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2e125-270">RELATED LINKS</span></span>

[<span data-ttu-id="2e125-271">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="2e125-271">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="2e125-272">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="2e125-272">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="2e125-273">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="2e125-273">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="2e125-274">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="2e125-274">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="2e125-275">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="2e125-275">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="2e125-276">Group-Object</span><span class="sxs-lookup"><span data-stu-id="2e125-276">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="2e125-277">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="2e125-277">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="2e125-278">New-Object</span><span class="sxs-lookup"><span data-stu-id="2e125-278">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="2e125-279">Select-Object</span><span class="sxs-lookup"><span data-stu-id="2e125-279">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="2e125-280">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="2e125-280">Tee-Object</span></span>](Tee-Object.md)
