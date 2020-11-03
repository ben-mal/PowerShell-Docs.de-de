---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: 14b1c5d0f37301a5312f37a115f0abc1c7b5990e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216348"
---
# <span data-ttu-id="3d0a8-103">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="3d0a8-103">Get-ChildItem</span></span>

## <span data-ttu-id="3d0a8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3d0a8-104">SYNOPSIS</span></span>

<span data-ttu-id="3d0a8-105">Ruft die Elemente und untergeordneten Elemente an angegebenen Speicherorten ab.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-105">Gets the items and child items in one or more specified locations.</span></span>

## <span data-ttu-id="3d0a8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3d0a8-106">SYNTAX</span></span>

### <span data-ttu-id="3d0a8-107">Elemente (Standard)</span><span class="sxs-lookup"><span data-stu-id="3d0a8-107">Items (Default)</span></span>

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>]
 [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="3d0a8-108">Literalitems</span><span class="sxs-lookup"><span data-stu-id="3d0a8-108">LiteralItems</span></span>

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name]
 [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden]
 [-ReadOnly] [-System] [<CommonParameters>]
```

## <span data-ttu-id="3d0a8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3d0a8-109">DESCRIPTION</span></span>

<span data-ttu-id="3d0a8-110">Mit dem- `Get-ChildItem` Cmdlet werden die Elemente an einem oder mehreren angegebenen Speicherorten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-110">The `Get-ChildItem` cmdlet gets the items in one or more specified locations.</span></span> <span data-ttu-id="3d0a8-111">Wenn es sich bei dem Element um einen Container handelt, werden die darin enthaltenen (untergeordneten) Elemente abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-111">If the item is a container, it gets the items inside the container, known as child items.</span></span> <span data-ttu-id="3d0a8-112">Sie können den **recurse** -Parameter verwenden, um Elemente in allen untergeordneten Containern zu erhalten, und den **tiefen** Parameter verwenden, um die Anzahl der Ebenen auf Rekurse zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-112">You can use the **Recurse** parameter to get items in all child containers and use the **Depth** parameter to limit the number of levels to recurse.</span></span>

<span data-ttu-id="3d0a8-113">`Get-ChildItem` zeigt keine leeren Verzeichnisse an.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-113">`Get-ChildItem` doesn't display empty directories.</span></span> <span data-ttu-id="3d0a8-114">Wenn ein `Get-ChildItem` Befehl die **Tiefe** oder die **recurse** -Parameter enthält, sind leere Verzeichnisse nicht in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-114">When a `Get-ChildItem` command includes the **Depth** or **Recurse** parameters, empty directories aren't included in the output.</span></span>

<span data-ttu-id="3d0a8-115">Standorte werden `Get-ChildItem` von PowerShell-Anbietern für verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-115">Locations are exposed to `Get-ChildItem` by PowerShell providers.</span></span> <span data-ttu-id="3d0a8-116">Bei einem Speicherort kann es sich um ein Dateisystem Verzeichnis, eine Registrierungs Struktur oder einen Zertifikat Speicher handeln.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-116">A location can be a file system directory, registry hive, or a certificate store.</span></span> <span data-ttu-id="3d0a8-117">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-117">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="3d0a8-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3d0a8-118">EXAMPLES</span></span>

### <span data-ttu-id="3d0a8-119">Beispiel 1: erhalten von untergeordneten Elementen aus einem Dateisystem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="3d0a8-119">Example 1: Get child items from a file system directory</span></span>

<span data-ttu-id="3d0a8-120">In diesem Beispiel werden die untergeordneten Elemente aus einem Dateisystem Verzeichnis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-120">This example gets the child items from a file system directory.</span></span> <span data-ttu-id="3d0a8-121">Die Namen der Dateinamen und Unterverzeichnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-121">The filenames and subdirectory names are displayed.</span></span> <span data-ttu-id="3d0a8-122">Für leere Speicherorte gibt der Befehl keine Ausgabe zurück und kehrt zur PowerShell-Eingabeaufforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-122">For empty locations, the command doesn't return any output and returns to the PowerShell prompt.</span></span>

<span data-ttu-id="3d0a8-123">Das- `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis anzugeben `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-123">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span>
<span data-ttu-id="3d0a8-124">`Get-ChildItem` zeigt die Dateien und Verzeichnisse in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-124">`Get-ChildItem` displays the files and directories in the PowerShell console.</span></span>

```powershell
Get-ChildItem -Path C:\Test
```

```Output
   Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     08:29                Logs
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="3d0a8-125">In der Standardeinstellung werden `Get-ChildItem` der Modus ( **Attribute** ), **lastschreitezeit** , Dateigröße ( **Länge** ) und der **Name** des Elements aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-125">By default `Get-ChildItem` lists the mode ( **Attributes** ), **LastWriteTime** , file size ( **Length** ), and the **Name** of the item.</span></span> <span data-ttu-id="3d0a8-126">Die Buchstaben in der **Mode** -Eigenschaft können wie folgt interpretiert werden:</span><span class="sxs-lookup"><span data-stu-id="3d0a8-126">The letters in the **Mode** property can be interpreted as follows:</span></span>

- <span data-ttu-id="3d0a8-127">`l` Verknüpfen</span><span class="sxs-lookup"><span data-stu-id="3d0a8-127">`l` (link)</span></span>
- <span data-ttu-id="3d0a8-128">`d` befinden</span><span class="sxs-lookup"><span data-stu-id="3d0a8-128">`d` (directory)</span></span>
- <span data-ttu-id="3d0a8-129">`a` archiviert</span><span class="sxs-lookup"><span data-stu-id="3d0a8-129">`a` (archive)</span></span>
- <span data-ttu-id="3d0a8-130">`r` (schreibgeschützt)</span><span class="sxs-lookup"><span data-stu-id="3d0a8-130">`r` (read-only)</span></span>
- <span data-ttu-id="3d0a8-131">`h` verbirgt</span><span class="sxs-lookup"><span data-stu-id="3d0a8-131">`h` (hidden)</span></span>
- <span data-ttu-id="3d0a8-132">`s` (System).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-132">`s` (system).</span></span>

<span data-ttu-id="3d0a8-133">Weitere Informationen zu den modusflags finden Sie unter [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-133">For more information about the mode flags, see [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span></span>

### <span data-ttu-id="3d0a8-134">Beispiel 2: erhalten von untergeordneten Elementnamen in einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="3d0a8-134">Example 2: Get child item names in a directory</span></span>

<span data-ttu-id="3d0a8-135">In diesem Beispiel werden nur die Namen der Elemente in einem Verzeichnis aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-135">This example lists only the names of items in a directory.</span></span>

<span data-ttu-id="3d0a8-136">Das- `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis anzugeben `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-136">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span> <span data-ttu-id="3d0a8-137">Der **Name** -Parameter gibt nur die Datei-oder Verzeichnisnamen aus dem angegebenen Pfad zurück.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-137">The **Name** parameter returns only the file or directory names from the specified path.</span></span>

```powershell
Get-ChildItem -Path C:\Test -Name
```

```Output
Logs
anotherfile.txt
Command.txt
CreateTestFile.ps1
ReadOnlyFile.txt
```

### <span data-ttu-id="3d0a8-138">Beispiel 3: erhalten von untergeordneten Elementen im aktuellen Verzeichnis und in den Unterverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="3d0a8-138">Example 3: Get child items in the current directory and subdirectories</span></span>

<span data-ttu-id="3d0a8-139">In diesem Beispiel werden **txt** -Dateien angezeigt, die sich im aktuellen Verzeichnis und seinen Unterverzeichnissen befinden.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-139">This example displays **.txt** files that are located in the current directory and its subdirectories.</span></span>

```powershell
Get-ChildItem -Path C:\Test\*.txt -Recurse -Force
```

```Output
    Directory: C:\Test\Logs\Adirectory

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile4.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile4.txt

    Directory: C:\Test\Logs\Backup

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 ATextFile.txt
-a----        2/12/2019     15:50             20 LogFile3.txt

    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="3d0a8-140">Das- `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um anzugeben `C:\Test\*.txt` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-140">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify `C:\Test\*.txt`.</span></span> <span data-ttu-id="3d0a8-141">**Path** verwendet das Sternchen-Platzhalter Zeichen ( `*` ), um alle Dateien mit der Dateinamenerweiterung anzugeben `.txt` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-141">**Path** uses the asterisk (`*`) wildcard to specify all files with the filename extension `.txt`.</span></span> <span data-ttu-id="3d0a8-142">Der **recurse** -Parameter durchsucht das **Pfad** Verzeichnis seiner Unterverzeichnisse, wie in den Überschriften " **Verzeichnis:** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-142">The **Recurse** parameter searches the **Path** directory its subdirectories, as shown in the **Directory:** headings.</span></span> <span data-ttu-id="3d0a8-143">Der **Force** -Parameter zeigt ausgeblendete Dateien an `hiddenfile.txt` , z. b. mit dem Modus **h** .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-143">The **Force** parameter displays hidden files such as `hiddenfile.txt` that have a mode of **h** .</span></span>

### <span data-ttu-id="3d0a8-144">Beispiel 4: Aufrufen von untergeordneten Elementen mit dem Include-Parameter</span><span class="sxs-lookup"><span data-stu-id="3d0a8-144">Example 4: Get child items using the Include parameter</span></span>

<span data-ttu-id="3d0a8-145">In diesem Beispiel `Get-ChildItem` wird der **include** -Parameter verwendet, um bestimmte Elemente aus dem Verzeichnis zu suchen, das durch den **path** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-145">In this example `Get-ChildItem` uses the **Include** parameter to find specific items from the directory specified by the **Path** parameter.</span></span>

```powershell
# When using the -Include parameter, if you don't include an asterisk in the path
# the command returns no output.
Get-ChildItem -Path C:\Test\ -Include *.txt
```

```Output

```

```powershell
Get-ChildItem -Path C:\Test\* -Include *.txt
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="3d0a8-146">Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis " **c:\test** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-146">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** .</span></span> <span data-ttu-id="3d0a8-147">Der **path** -Parameter enthält einen nachfolgenden Sternchen ( `*` )-Platzhalter, um den Inhalt des Verzeichnisses anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-147">The **Path** parameter includes a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span>
<span data-ttu-id="3d0a8-148">Der **include** -Parameter verwendet ein Sternchen-Platzhalter Zeichen ( `*` ), um alle Dateien mit der Dateinamenerweiterung **. txt** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-148">The **Include** parameter uses an asterisk (`*`) wildcard to specify all files with the file name extension **.txt** .</span></span>

<span data-ttu-id="3d0a8-149">Wenn der **include** -Parameter verwendet wird, benötigt der **path** -Parameter einen nachfolgenden Sternchen ( `*` )-Platzhalter, um den Inhalt des Verzeichnisses anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-149">When the **Include** parameter is used, the **Path** parameter needs a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span> <span data-ttu-id="3d0a8-150">Beispiel: `-Path C:\Test\*`.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-150">For example, `-Path C:\Test\*`.</span></span>

- <span data-ttu-id="3d0a8-151">Wenn der **recurse** -Parameter dem Befehl hinzugefügt wird, ist das nachfolgende Sternchen ( `*` ) im **path** -Parameter optional.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-151">If the **Recurse** parameter is added to the command, the trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="3d0a8-152">Der **recurse** -Parameter ruft Elemente aus dem **Pfad** Verzeichnis und seinen Unterverzeichnissen ab.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-152">The **Recurse** parameter gets items from the **Path** directory and its subdirectories.</span></span> <span data-ttu-id="3d0a8-153">Zum Beispiel, `-Path C:\Test\ -Recurse -Include *.txt`</span><span class="sxs-lookup"><span data-stu-id="3d0a8-153">For example, `-Path C:\Test\ -Recurse -Include *.txt`</span></span>
- <span data-ttu-id="3d0a8-154">Wenn ein nach gestelltes Sternchen ( `*` ) nicht im **path** -Parameter enthalten ist, gibt der Befehl keine Ausgabe zurück und kehrt zur PowerShell-Eingabeaufforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-154">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the command doesn't return any output and returns to the PowerShell prompt.</span></span> <span data-ttu-id="3d0a8-155">Beispiel: `-Path C:\Test\`.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-155">For example, `-Path C:\Test\`.</span></span>

### <span data-ttu-id="3d0a8-156">Beispiel 5: Aufrufen von untergeordneten Elementen mit dem Exclude-Parameter</span><span class="sxs-lookup"><span data-stu-id="3d0a8-156">Example 5: Get child items using the Exclude parameter</span></span>

<span data-ttu-id="3d0a8-157">Die Ausgabe des Beispiels zeigt den Inhalt des Verzeichnisses " **c:\test\logs** ".</span><span class="sxs-lookup"><span data-stu-id="3d0a8-157">The example's output shows the contents of the directory **C:\Test\Logs** .</span></span> <span data-ttu-id="3d0a8-158">Bei der Ausgabe handelt es sich um einen Verweis auf die anderen Befehle, die die **Exclude** -und **recurse** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-158">The output is a reference for the other commands that use the **Exclude** and **Recurse** parameters.</span></span>

```powershell
Get-ChildItem -Path C:\Test\Logs
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Adirectory
d-----        2/15/2019     08:28                AnEmptyDirectory
d-----        2/15/2019     13:21                Backup
-a----        2/12/2019     16:16             20 Afile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

```powershell
Get-ChildItem -Path C:\Test\Logs\* -Exclude A*
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Backup
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

<span data-ttu-id="3d0a8-159">Das- `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis anzugeben `C:\Test\Logs` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-159">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test\Logs`.</span></span>
<span data-ttu-id="3d0a8-160">Der **Exclude** -Parameter verwendet das Sternchen-Platzhalter Zeichen ( `*` ), um alle Dateien oder Verzeichnisse anzugeben, die mit **einem** oder **einem** beginnen, der aus der Ausgabe ausgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-160">The **Exclude** parameter uses the asterisk (`*`) wildcard to specify any files or directories that begin with **A** or **a** are excluded from the output.</span></span>

<span data-ttu-id="3d0a8-161">Wenn der **Exclude** -Parameter verwendet wird, ist das nachfolgende Sternchen ( `*` ) im **path** -Parameter optional.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-161">When the **Exclude** parameter is used, a trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="3d0a8-162">Zum Beispiel: `-Path C:\Test\Logs` oder `-Path C:\Test\Logs\*`.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-162">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span>

- <span data-ttu-id="3d0a8-163">Wenn ein nach gestelltes Sternchen ( `*` ) nicht im **path** -Parameter enthalten ist, wird der Inhalt des **path** -Parameters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-163">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="3d0a8-164">Ausnahmen sind Dateinamen oder Unterverzeichnis Namen, die dem Wert des **Exclude** -Parameters entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-164">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="3d0a8-165">Wenn ein nach gestelltes Sternchen ( `*` ) im **path** -Parameter enthalten ist, wird der Befehl in die Unterverzeichnisse des **path** -Parameters rekurdieren.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-165">If a trailing asterisk (`*`) is included in the **Path** parameter, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="3d0a8-166">Ausnahmen sind Dateinamen oder Unterverzeichnis Namen, die dem Wert des **Exclude** -Parameters entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-166">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="3d0a8-167">Wenn der **recurse** -Parameter dem Befehl hinzugefügt wird, ist die Rekursions Ausgabe gleich, unabhängig davon, ob der **path** -Parameter ein nach gestelltes Sternchen ( `*` ) enthält.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-167">If the **Recurse** parameter is added to the command, the recursion output is the same whether or not the **Path** parameter includes a trailing asterisk (`*`).</span></span>

### <span data-ttu-id="3d0a8-168">Beispiel 6: erhalten der Registrierungsschlüssel aus einer Registrierungs Struktur</span><span class="sxs-lookup"><span data-stu-id="3d0a8-168">Example 6: Get the registry keys from a registry hive</span></span>

<span data-ttu-id="3d0a8-169">In diesem Beispiel werden alle Registrierungsschlüssel aus abgerufen `HKEY_LOCAL_MACHINE\HARDWARE` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-169">This example gets all the registry keys from `HKEY_LOCAL_MACHINE\HARDWARE`.</span></span>

<span data-ttu-id="3d0a8-170">`Get-ChildItem` verwendet den **path** -Parameter, um den Registrierungsschlüssel anzugeben `HKLM:\HARDWARE` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-170">`Get-ChildItem` uses the **Path** parameter to specify the registry key `HKLM:\HARDWARE`.</span></span> <span data-ttu-id="3d0a8-171">Der Hive-Pfad und die oberste Ebene der Registrierungsschlüssel werden in der PowerShell-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-171">The hive's path and top level of registry keys are displayed in the PowerShell console.</span></span>

<span data-ttu-id="3d0a8-172">Weitere Informationen finden Sie unter [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-172">For more information, see [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span></span>

```powershell
Get-ChildItem -Path HKLM:\HARDWARE
```

```Output
    Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name             Property
----             --------
ACPI
DESCRIPTION
DEVICEMAP
RESOURCEMAP
UEFI
```

```powershell
Get-ChildItem -Path HKLM:\HARDWARE -Exclude D*
```

```Output
   Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name                           Property
----                           --------
ACPI
RESOURCEMAP
```

<span data-ttu-id="3d0a8-173">Der erste Befehl zeigt den Inhalt des `HKLM:\HARDWARE` Registrierungsschlüssels an.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-173">The first command shows the contents of the `HKLM:\HARDWARE` registry key.</span></span> <span data-ttu-id="3d0a8-174">Der **Exclude** -Parameter weist `Get-ChildItem` an, keine Unterschlüssel zurückzugeben, die mit beginnen `D*` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-174">The **Exclude** parameter tells `Get-ChildItem` not to return any subkeys that start with `D*`.</span></span> <span data-ttu-id="3d0a8-175">Derzeit funktioniert der **Exclude** -Parameter nur für Unterschlüssel, nicht für Element Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-175">Currently, the **Exclude** parameter only works on subkeys, not item properties.</span></span>

### <span data-ttu-id="3d0a8-176">Beispiel 7: alle Zertifikate mit Code Signatur Stelle erhalten</span><span class="sxs-lookup"><span data-stu-id="3d0a8-176">Example 7: Get all certificates with code-signing authority</span></span>

<span data-ttu-id="3d0a8-177">In diesem Beispiel werden alle Zertifikate im PowerShell-Zertifikat " **CERT:** " abgerufen, das über Code Signatur Autorität verfügt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-177">This example gets each certificate in the PowerShell **Cert:** drive that has code-signing authority.</span></span>

<span data-ttu-id="3d0a8-178">Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um den **CERT:** -Anbieter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-178">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the **Cert:** provider.</span></span> <span data-ttu-id="3d0a8-179">Der **recurse** -Parameter durchsucht das Verzeichnis, das von **path** und seinen Unterverzeichnissen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-179">The **Recurse** parameter searches the directory specified by **Path** and its subdirectories.</span></span> <span data-ttu-id="3d0a8-180">Mit dem **codeSigningCert** -Parameter werden nur Zertifikate abgerufen, die über eine Code Signatur Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-180">The **CodeSigningCert** parameter gets only certificates that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

<span data-ttu-id="3d0a8-181">Weitere Informationen zum Zertifikat Anbieter und zum CERT:-Laufwerk finden Sie unter [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-181">For more information about the Certificate provider and the Cert: drive, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="3d0a8-182">Beispiel 8: Get Items using the Tiefe Parameter</span><span class="sxs-lookup"><span data-stu-id="3d0a8-182">Example 8: Get items using the Depth parameter</span></span>

<span data-ttu-id="3d0a8-183">In diesem Beispiel werden die Elemente in einem Verzeichnis und seinen Unterverzeichnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-183">This example displays the items in a directory and its subdirectories.</span></span> <span data-ttu-id="3d0a8-184">Der **tiefen** Parameter bestimmt die Anzahl der Unterverzeichnis Ebenen, die in die Rekursion eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-184">The **Depth** parameter determines the number of subdirectory levels to include in the recursion.</span></span> <span data-ttu-id="3d0a8-185">Leere Verzeichnisse werden aus der Ausgabe ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-185">Empty directories are excluded from the output.</span></span>

```powershell
Get-ChildItem -Path C:\Parent -Depth 2
```

```Output
    Directory: C:\Parent

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level1
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level2
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1\SubDir_Level2

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:22                SubDir_Level3
-a----        2/13/2019     08:55             26 file.txt
```

<span data-ttu-id="3d0a8-186">Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um **c:\parent** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-186">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify **C:\Parent** .</span></span> <span data-ttu-id="3d0a8-187">Der **tiefen** Parameter gibt zwei Rekursions Ebenen an.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-187">The **Depth** parameter specifies two levels of recursion.</span></span> <span data-ttu-id="3d0a8-188">`Get-ChildItem` zeigt den Inhalt des Verzeichnisses an, das durch den **path** -Parameter und die beiden Ebenen der Unterverzeichnisse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-188">`Get-ChildItem` displays the contents of the directory specified by the **Path** parameter and the two levels of subdirectories.</span></span>

### <span data-ttu-id="3d0a8-189">Beispiel 9: erhalten von hardlinkinformationen</span><span class="sxs-lookup"><span data-stu-id="3d0a8-189">Example 9: Getting hard link information</span></span>

<span data-ttu-id="3d0a8-190">In PowerShell 6,2 wurde eine Alternative Ansicht hinzugefügt, um hardlinkinformationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-190">In PowerShell 6.2, an alternate view was added to get hard link information.</span></span>

```powershell
Get-ChildItem -Path C:\PathContainingHardLink | Format-Table -View childrenWithHardLink
```

## <span data-ttu-id="3d0a8-191">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d0a8-191">Parameters</span></span>

### <span data-ttu-id="3d0a8-192">-Attribute</span><span class="sxs-lookup"><span data-stu-id="3d0a8-192">-Attributes</span></span>

<span data-ttu-id="3d0a8-193">Ruft Dateien und Ordner mit den angegebenen Attributen ab.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-193">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="3d0a8-194">Dieser Parameter unterstützt alle Attribute und Sie können komplexe Kombinationen von Attributen angeben.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-194">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="3d0a8-195">Geben Sie z. B. Folgendes ein, um Nicht-Systemdateien (keine Verzeichnisse) zu erhalten, die verschlüsselt oder komprimiert sind:</span><span class="sxs-lookup"><span data-stu-id="3d0a8-195">For example, to get non-system files (not directories) that are encrypted or compressed, type:</span></span>

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

<span data-ttu-id="3d0a8-196">Um Dateien und Ordner mit häufig verwendeten Attributen zu suchen, verwenden Sie den **Attribute** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-196">To find files and folders with commonly used attributes, use the **Attributes** parameter.</span></span> <span data-ttu-id="3d0a8-197">Oder, das Parameter **Verzeichnis** , **Datei** , **ausgeblendet** , **schreibgeschützt und** **System** .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-197">Or, the parameters **Directory** , **File** , **Hidden** , **ReadOnly** , and **System** .</span></span>

<span data-ttu-id="3d0a8-198">Der **Attribute** -Parameter unterstützt die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3d0a8-198">The **Attributes** parameter supports the following properties:</span></span>

- <span data-ttu-id="3d0a8-199">**Archivieren**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-199">**Archive**</span></span>
- <span data-ttu-id="3d0a8-200">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-200">**Compressed**</span></span>
- <span data-ttu-id="3d0a8-201">**Device**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-201">**Device**</span></span>
- <span data-ttu-id="3d0a8-202">**Verzeichnis**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-202">**Directory**</span></span>
- <span data-ttu-id="3d0a8-203">**Verschlüsselt**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-203">**Encrypted**</span></span>
- <span data-ttu-id="3d0a8-204">**Hidden**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-204">**Hidden**</span></span>
- <span data-ttu-id="3d0a8-205">**Integritystream**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-205">**IntegrityStream**</span></span>
- <span data-ttu-id="3d0a8-206">**Normal**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-206">**Normal**</span></span>
- <span data-ttu-id="3d0a8-207">**Noscrubdata**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-207">**NoScrubData**</span></span>
- <span data-ttu-id="3d0a8-208">**Notcontentindiziert**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-208">**NotContentIndexed**</span></span>
- <span data-ttu-id="3d0a8-209">**Aufzu**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-209">**Offline**</span></span>
- <span data-ttu-id="3d0a8-210">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-210">**ReadOnly**</span></span>
- <span data-ttu-id="3d0a8-211">**Analyse Punkt**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-211">**ReparsePoint**</span></span>
- <span data-ttu-id="3d0a8-212">**Sparpfad**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-212">**SparseFile**</span></span>
- <span data-ttu-id="3d0a8-213">**System**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-213">**System**</span></span>
- <span data-ttu-id="3d0a8-214">**Temporär**</span><span class="sxs-lookup"><span data-stu-id="3d0a8-214">**Temporary**</span></span>

<span data-ttu-id="3d0a8-215">Eine Beschreibung dieser Attribute finden Sie in der [FileAttribute-Enumeration](/dotnet/api/system.io.fileattributes).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-215">For a description of these attributes, see the [FileAttributes Enumeration](/dotnet/api/system.io.fileattributes).</span></span>

<span data-ttu-id="3d0a8-216">Verwenden Sie die folgenden Operatoren, um Attribute zu kombinieren:</span><span class="sxs-lookup"><span data-stu-id="3d0a8-216">To combine attributes, use the following operators:</span></span>

- <span data-ttu-id="3d0a8-217">`!` Hätten</span><span class="sxs-lookup"><span data-stu-id="3d0a8-217">`!` (NOT)</span></span>
- <span data-ttu-id="3d0a8-218">`+` Immer</span><span class="sxs-lookup"><span data-stu-id="3d0a8-218">`+` (AND)</span></span>
- <span data-ttu-id="3d0a8-219">`,` Noch</span><span class="sxs-lookup"><span data-stu-id="3d0a8-219">`,` (OR)</span></span>

<span data-ttu-id="3d0a8-220">Verwenden Sie keine Leerzeichen zwischen einem Operator und dessen Attribut.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-220">Don't use spaces between an operator and its attribute.</span></span> <span data-ttu-id="3d0a8-221">Leerzeichen werden nach Kommas akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-221">Spaces are accepted after commas.</span></span>

<span data-ttu-id="3d0a8-222">Verwenden Sie für allgemeine Attribute die folgenden Abkürzungen:</span><span class="sxs-lookup"><span data-stu-id="3d0a8-222">For common attributes, use the following abbreviations:</span></span>

- <span data-ttu-id="3d0a8-223">`D` Befinden</span><span class="sxs-lookup"><span data-stu-id="3d0a8-223">`D` (Directory)</span></span>
- <span data-ttu-id="3d0a8-224">`H` Verbirgt</span><span class="sxs-lookup"><span data-stu-id="3d0a8-224">`H` (Hidden)</span></span>
- <span data-ttu-id="3d0a8-225">`R` (Schreibgeschützt)</span><span class="sxs-lookup"><span data-stu-id="3d0a8-225">`R` (Read-only)</span></span>
- <span data-ttu-id="3d0a8-226">`S` Anlage</span><span class="sxs-lookup"><span data-stu-id="3d0a8-226">`S` (System)</span></span>

```yaml
Type: System.Management.Automation.FlagsExpression`1[System.IO.FileAttributes]
Parameter Sets: (All)
Aliases:
Accepted values: Archive, Compressed, Device, Directory, Encrypted, Hidden, IntegrityStream, Normal, NoScrubData, NotContentIndexed, Offline, ReadOnly, ReparsePoint, SparseFile, System, Temporary

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-227">-Tiefe</span><span class="sxs-lookup"><span data-stu-id="3d0a8-227">-Depth</span></span>

<span data-ttu-id="3d0a8-228">Dieser Parameter wurde in PowerShell 5,0 hinzugefügt und ermöglicht es Ihnen, die Tiefe der Rekursion zu steuern.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-228">This parameter was added in PowerShell 5.0 and enables you to control the depth of recursion.</span></span> <span data-ttu-id="3d0a8-229">In der Standardeinstellung wird `Get-ChildItem` der Inhalt des übergeordneten Verzeichnisses angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-229">By default, `Get-ChildItem` displays the contents of the parent directory.</span></span> <span data-ttu-id="3d0a8-230">Der **tiefen** Parameter bestimmt die Anzahl der Unterverzeichnis Ebenen, die in der Rekursion enthalten sind, und zeigt die Inhalte an.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-230">The **Depth** parameter determines the number of subdirectory levels that are included in the recursion and displays the contents.</span></span>

<span data-ttu-id="3d0a8-231">Beispielsweise `Depth 2` enthält das Verzeichnis des **path** -Parameters, die erste Ebene der Unterverzeichnisse und die zweite Ebene der Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-231">For example, `Depth 2` includes the **Path** parameter's directory, first level of subdirectories, and second level of subdirectories.</span></span> <span data-ttu-id="3d0a8-232">Standardmäßig sind Verzeichnisnamen und Dateinamen in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-232">By default directory names and filenames are included in the output.</span></span>

> [!NOTE]
> <span data-ttu-id="3d0a8-233">Auf einem Windows-Computer aus PowerShell oder **cmd.exe** können Sie eine grafische Ansicht einer Verzeichnisstruktur mit dem **Tree.com** -Befehl anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-233">On a Windows computer from PowerShell or **cmd.exe** , you can display a graphical view of a directory structure with the **tree.com** command.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-234">-Directory</span><span class="sxs-lookup"><span data-stu-id="3d0a8-234">-Directory</span></span>

<span data-ttu-id="3d0a8-235">Zum Aufrufen einer Liste von Verzeichnissen verwenden Sie den **Directory** -Parameter oder **den Parameters** -Parameter mit der **Directory** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-235">To get a list of directories, use the **Directory** parameter or the **Attributes** parameter with the **Directory** property.</span></span> <span data-ttu-id="3d0a8-236">Sie können den **recurse** -Parameter mit **Directory** verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-236">You can use the **Recurse** parameter with **Directory** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ad, d

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-237">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="3d0a8-237">-Exclude</span></span>

<span data-ttu-id="3d0a8-238">Gibt als Zeichen folgen Array eine Eigenschaft oder eine Eigenschaft an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-238">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="3d0a8-239">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-239">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3d0a8-240">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` `A*` . b. oder.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-240">Enter a path element or pattern, such as `*.txt` or `A*`.</span></span> <span data-ttu-id="3d0a8-241">Platzhalterzeichen werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-241">Wildcard characters are accepted.</span></span>

<span data-ttu-id="3d0a8-242">Ein nach gestelltes Sternchen ( `*` ) im **path** -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-242">A trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="3d0a8-243">Zum Beispiel: `-Path C:\Test\Logs` oder `-Path C:\Test\Logs\*`.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-243">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span> <span data-ttu-id="3d0a8-244">Wenn ein nach gestelltes Sternchen ( `*` ) eingeschlossen ist, wird der Befehl in die Unterverzeichnisse des **path** -Parameters rekurdieren.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-244">If a trailing asterisk (`*`) is included, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="3d0a8-245">Ohne das Sternchen ( `*` ) wird der Inhalt des **path** -Parameters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-245">Without the asterisk (`*`), the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="3d0a8-246">Weitere Informationen finden Sie in Beispiel 5 und im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="3d0a8-246">More details are included in Example 5 and the Notes section.</span></span>

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

### <span data-ttu-id="3d0a8-247">-File</span><span class="sxs-lookup"><span data-stu-id="3d0a8-247">-File</span></span>

<span data-ttu-id="3d0a8-248">Verwenden Sie den **File** -Parameter, um eine Liste mit Dateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-248">To get a list of files, use the **File** parameter.</span></span> <span data-ttu-id="3d0a8-249">Sie können den **recurse** -Parameter mit **File** verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-249">You can use the **Recurse** parameter with **File** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: af

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-250">-Filter</span><span class="sxs-lookup"><span data-stu-id="3d0a8-250">-Filter</span></span>

<span data-ttu-id="3d0a8-251">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-251">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="3d0a8-252">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der Filter unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-252">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="3d0a8-253">Filter sind effizienter als andere Parameter.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-253">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="3d0a8-254">Der Anbieter wendet den Filter an, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-254">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="3d0a8-255">Die Filter Zeichenfolge wird an die .NET-API zum Aufzählen von Dateien übermittelt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-255">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="3d0a8-256">Die API unterstützt nur `*` -und-Platzhalter `?` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-256">The API only supports `*` and `?` wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3d0a8-257">-Followsymlink</span><span class="sxs-lookup"><span data-stu-id="3d0a8-257">-FollowSymlink</span></span>

<span data-ttu-id="3d0a8-258">Standardmäßig zeigt das `Get-ChildItem` Cmdlet symbolische Verknüpfungen zu Verzeichnissen an, die während der Rekursion gefunden werden, aber nicht wiederholt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-258">By default, the `Get-ChildItem` cmdlet displays symbolic links to directories found during recursion, but doesn't recurse into them.</span></span> <span data-ttu-id="3d0a8-259">Verwenden Sie den **folgenden** Parameter, um die Verzeichnisse zu durchsuchen, die diese symbolischen Verknüpfungen als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-259">Use the **FollowSymlink** parameter to search the directories that target those symbolic links.</span></span> <span data-ttu-id="3d0a8-260">Der **folgende** Parameter ist ein dynamischer Parameter, der nur im **File System** -Anbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-260">The **FollowSymlink** is a dynamic parameter and is supported only in the **FileSystem** provider.</span></span>

<span data-ttu-id="3d0a8-261">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-261">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-262">-Force</span><span class="sxs-lookup"><span data-stu-id="3d0a8-262">-Force</span></span>

<span data-ttu-id="3d0a8-263">Ermöglicht es dem Cmdlet, Elemente zu erhalten, auf die der Benutzer anderweitig nicht zugreifen kann, z. b. ausgeblendete Dateien oder Systemdateien.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-263">Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files.</span></span> <span data-ttu-id="3d0a8-264">Der **Force** -Parameter überschreibt keine Sicherheitseinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-264">The **Force** parameter doesn't override security restrictions.</span></span> <span data-ttu-id="3d0a8-265">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-265">Implementation varies among providers.</span></span> <span data-ttu-id="3d0a8-266">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-266">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-267">-Hidden</span><span class="sxs-lookup"><span data-stu-id="3d0a8-267">-Hidden</span></span>

<span data-ttu-id="3d0a8-268">Um nur ausgeblendete Elemente zu erhalten, verwenden Sie den **Hidden** -Parameter oder den **Attribute** -Parameter mit der **Hidden** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-268">To get only hidden items, use the **Hidden** parameter or the **Attributes** parameter with the **Hidden** property.</span></span> <span data-ttu-id="3d0a8-269">Standardmäßig zeigt keine ausgeblendeten `Get-ChildItem` Elemente an.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-269">By default, `Get-ChildItem` doesn't display hidden items.</span></span> <span data-ttu-id="3d0a8-270">Verwenden Sie den **Force** -Parameter, um verborgene Elemente zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-270">Use the **Force** parameter to get hidden items.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ah, h

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-271">-Include</span><span class="sxs-lookup"><span data-stu-id="3d0a8-271">-Include</span></span>

<span data-ttu-id="3d0a8-272">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-272">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="3d0a8-273">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-273">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3d0a8-274">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="3d0a8-274">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="3d0a8-275">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-275">Wildcard characters are permitted.</span></span> <span data-ttu-id="3d0a8-276">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-276">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="3d0a8-277">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="3d0a8-277">-LiteralPath</span></span>

<span data-ttu-id="3d0a8-278">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-278">Specifies a path to one or more locations.</span></span> <span data-ttu-id="3d0a8-279">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-279">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="3d0a8-280">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-280">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3d0a8-281">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-281">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3d0a8-282">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-282">Single quotation marks tell PowerShell to not interpret any characters as escape sequences.</span></span>

<span data-ttu-id="3d0a8-283">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-283">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralItems
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-284">-Name</span><span class="sxs-lookup"><span data-stu-id="3d0a8-284">-Name</span></span>

<span data-ttu-id="3d0a8-285">Ruft nur die Namen der Elemente am Speicherort ab.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-285">Gets only the names of the items in the location.</span></span> <span data-ttu-id="3d0a8-286">Bei der Ausgabe handelt es sich um ein Zeichen folgen Objekt, das über die Pipeline an andere Befehle gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-286">The output is a string object that can be sent down the pipeline to other commands.</span></span> <span data-ttu-id="3d0a8-287">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-287">Wildcards are permitted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3d0a8-288">-Path</span><span class="sxs-lookup"><span data-stu-id="3d0a8-288">-Path</span></span>

<span data-ttu-id="3d0a8-289">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-289">Specifies a path to one or more locations.</span></span> <span data-ttu-id="3d0a8-290">Platzhalter werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-290">Wildcards are accepted.</span></span> <span data-ttu-id="3d0a8-291">Der Standard Speicherort ist das aktuelle Verzeichnis ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-291">The default location is the current directory (`.`).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Items
Aliases:

Required: False
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="3d0a8-292">-ReadOnly</span><span class="sxs-lookup"><span data-stu-id="3d0a8-292">-ReadOnly</span></span>

<span data-ttu-id="3d0a8-293">Um nur schreibgeschützte Elemente zu erhalten, verwenden Sie den Parameter "read **only** " oder **die Eigenschaft "** **Attributparameter** schreibgeschützt".</span><span class="sxs-lookup"><span data-stu-id="3d0a8-293">To get only read-only items, use the **ReadOnly** parameter or the **Attributes** parameter **ReadOnly** property.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ar

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-294">-Recurse</span><span class="sxs-lookup"><span data-stu-id="3d0a8-294">-Recurse</span></span>

<span data-ttu-id="3d0a8-295">Ruft die Elemente an den angegebenen Speicherorten und alle untergeordneten Elemente der Speicherorte ab.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-295">Gets the items in the specified locations and in all child items of the locations.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-296">-System</span><span class="sxs-lookup"><span data-stu-id="3d0a8-296">-System</span></span>

<span data-ttu-id="3d0a8-297">Ruft nur Systemdateien und Verzeichnisse ab.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-297">Gets only system files and directories.</span></span> <span data-ttu-id="3d0a8-298">Um nur Systemdateien und Ordner zu erhalten, verwenden **System** Sie die System Eigenschaft System **Parameter oder** **Attribute** des Parameters.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-298">To get only system files and folders, use the **System** parameter or **Attributes** parameter **System** property.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: as

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d0a8-299">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3d0a8-299">CommonParameters</span></span>

<span data-ttu-id="3d0a8-300">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-300">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3d0a8-301">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-301">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3d0a8-302">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3d0a8-302">INPUTS</span></span>

### <span data-ttu-id="3d0a8-303">System.String</span><span class="sxs-lookup"><span data-stu-id="3d0a8-303">System.String</span></span>

<span data-ttu-id="3d0a8-304">Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-304">You can pipe a string that contains a path to `Get-ChildItem`.</span></span>

## <span data-ttu-id="3d0a8-305">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3d0a8-305">OUTPUTS</span></span>

### <span data-ttu-id="3d0a8-306">System.Object</span><span class="sxs-lookup"><span data-stu-id="3d0a8-306">System.Object</span></span>

<span data-ttu-id="3d0a8-307">Der Typ des zurückgegebenen Objekts `Get-ChildItem` wird von den Objekten im Pfad des Anbieter Laufwerks bestimmt.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-307">The type of object that `Get-ChildItem` returns is determined by the objects in the provider drive path.</span></span>

### <span data-ttu-id="3d0a8-308">System.String</span><span class="sxs-lookup"><span data-stu-id="3d0a8-308">System.String</span></span>

<span data-ttu-id="3d0a8-309">Wenn Sie den **Name** -Parameter verwenden, werden `Get-ChildItem` die Objektnamen als Zeichen folgen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-309">If you use the **Name** parameter, `Get-ChildItem` returns the object names as strings.</span></span>

## <span data-ttu-id="3d0a8-310">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3d0a8-310">NOTES</span></span>

- <span data-ttu-id="3d0a8-311">`Get-ChildItem` kann mithilfe einer der integrierten Aliase, `ls` , und ausgeführt werden `dir` `gci` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-311">`Get-ChildItem` can be run using any of the built-in aliases, `ls`, `dir`, and `gci`.</span></span> <span data-ttu-id="3d0a8-312">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-312">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="3d0a8-313">`Get-ChildItem` Standardmäßig werden keine ausgeblendeten Elemente erhalten.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-313">`Get-ChildItem` doesn't get hidden items by default.</span></span> <span data-ttu-id="3d0a8-314">Wenn Sie ausgeblendete Elemente abrufen möchten, verwenden Sie den **Force** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-314">To get hidden items, use the **Force** parameter.</span></span>
- <span data-ttu-id="3d0a8-315">Das- `Get-ChildItem` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="3d0a8-315">The `Get-ChildItem` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3d0a8-316">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="3d0a8-316">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="3d0a8-317">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="3d0a8-317">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="3d0a8-318">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3d0a8-318">RELATED LINKS</span></span>

[<span data-ttu-id="3d0a8-319">about_Certificate_Provider</span><span class="sxs-lookup"><span data-stu-id="3d0a8-319">about_Certificate_Provider</span></span>](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[<span data-ttu-id="3d0a8-320">about_Providers</span><span class="sxs-lookup"><span data-stu-id="3d0a8-320">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="3d0a8-321">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="3d0a8-321">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="3d0a8-322">about_Registry_Provider</span><span class="sxs-lookup"><span data-stu-id="3d0a8-322">about_Registry_Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[<span data-ttu-id="3d0a8-323">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="3d0a8-323">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="3d0a8-324">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="3d0a8-324">Get-Alias</span></span>](../Microsoft.PowerShell.Utility/Get-Alias.md)

[<span data-ttu-id="3d0a8-325">Get-Item</span><span class="sxs-lookup"><span data-stu-id="3d0a8-325">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="3d0a8-326">Get-Location</span><span class="sxs-lookup"><span data-stu-id="3d0a8-326">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="3d0a8-327">Get-Process</span><span class="sxs-lookup"><span data-stu-id="3d0a8-327">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="3d0a8-328">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="3d0a8-328">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="3d0a8-329">Split-Path</span><span class="sxs-lookup"><span data-stu-id="3d0a8-329">Split-Path</span></span>](Split-Path.md)
