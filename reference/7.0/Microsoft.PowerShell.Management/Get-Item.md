---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: 07f8da5e6101b1d9bb1971b3c77b9747c0080a23
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210479"
---
# <span data-ttu-id="0bb15-103">Get-Item</span><span class="sxs-lookup"><span data-stu-id="0bb15-103">Get-Item</span></span>

## <span data-ttu-id="0bb15-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0bb15-104">SYNOPSIS</span></span>
<span data-ttu-id="0bb15-105">Ruft das Element am angegebenen Speicherort ab.</span><span class="sxs-lookup"><span data-stu-id="0bb15-105">Gets the item at the specified location.</span></span>

## <span data-ttu-id="0bb15-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0bb15-106">SYNTAX</span></span>

### <span data-ttu-id="0bb15-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="0bb15-107">Path (Default)</span></span>

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0bb15-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0bb15-108">LiteralPath</span></span>

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Force] [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="0bb15-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0bb15-109">DESCRIPTION</span></span>

<span data-ttu-id="0bb15-110">Mit dem- `Get-Item` Cmdlet wird das Element an der angegebenen Position abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0bb15-110">The `Get-Item` cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="0bb15-111">Der Inhalt des Elements wird nicht am Speicherort angezeigt, es sei denn, Sie verwenden ein Platzhalter Zeichen ( `*` ), um den gesamten Inhalt des Elements anzufordern.</span><span class="sxs-lookup"><span data-stu-id="0bb15-111">It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.</span></span>

<span data-ttu-id="0bb15-112">Dieses Cmdlet wird von PowerShell-Anbietern verwendet, um durch verschiedene Typen von Daten speichern zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="0bb15-112">This cmdlet is used by PowerShell providers to navigate through different types of data stores.</span></span>

## <span data-ttu-id="0bb15-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0bb15-113">EXAMPLES</span></span>

### <span data-ttu-id="0bb15-114">Beispiel 1: erhalten des aktuellen Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="0bb15-114">Example 1: Get the current directory</span></span>

<span data-ttu-id="0bb15-115">In diesem Beispiel wird das aktuelle Verzeichnis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0bb15-115">This example gets the current directory.</span></span> <span data-ttu-id="0bb15-116">Der Punkt (".") stellt das Element am aktuellen Speicherort dar (nicht seinen Inhalt).</span><span class="sxs-lookup"><span data-stu-id="0bb15-116">The dot ('.') represents the item at the current location (not its contents).</span></span>

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### <span data-ttu-id="0bb15-117">Beispiel 2: alle Elemente im aktuellen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="0bb15-117">Example 2: Get all the items in the current directory</span></span>

<span data-ttu-id="0bb15-118">In diesem Beispiel werden alle Elemente im aktuellen Verzeichnis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0bb15-118">This example gets all the items in the current directory.</span></span> <span data-ttu-id="0bb15-119">Das Platzhalter Zeichen ( `*` ) stellt den gesamten Inhalt des aktuellen Elements dar.</span><span class="sxs-lookup"><span data-stu-id="0bb15-119">The wildcard character (`*`) represents all the contents of the current item.</span></span>

```powershell
Get-Item *
```

```output
Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006   9:29 AM            Logs
d----         7/26/2006   9:26 AM            Recs
-a---         7/26/2006   9:28 AM         80 date.csv
-a---         7/26/2006  10:01 AM         30 filenoext
-a---         7/26/2006   9:30 AM      11472 process.doc
-a---         7/14/2006  10:47 AM         30 test.txt
```

### <span data-ttu-id="0bb15-120">Beispiel 3: erhalten des aktuellen Verzeichnisses eines Laufwerks</span><span class="sxs-lookup"><span data-stu-id="0bb15-120">Example 3: Get the current directory of a drive</span></span>

<span data-ttu-id="0bb15-121">In diesem Beispiel wird das aktuelle Verzeichnis des `C:` Laufwerks abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0bb15-121">This example gets the current directory of the `C:` drive.</span></span> <span data-ttu-id="0bb15-122">Das abgerufene Objekt stellt nur das Verzeichnis dar, nicht dessen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="0bb15-122">The object that is retrieved represents only the directory, not its contents.</span></span>

```powershell
Get-Item C:\
```

### <span data-ttu-id="0bb15-123">Beispiel 4: erhalten von Elementen im angegebenen Laufwerk</span><span class="sxs-lookup"><span data-stu-id="0bb15-123">Example 4: Get items in the specified drive</span></span>

<span data-ttu-id="0bb15-124">In diesem Beispiel werden die Elemente im `C:` Laufwerk abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0bb15-124">This example gets the items in the `C:` drive.</span></span> <span data-ttu-id="0bb15-125">Das Platzhalter Zeichen ( `*` ) stellt alle Elemente im Container dar, nicht nur den Container.</span><span class="sxs-lookup"><span data-stu-id="0bb15-125">The wildcard character (`*`) represents all the items in the container, not just the container.</span></span>

```powershell
Get-Item C:\*
```

<span data-ttu-id="0bb15-126">Verwenden Sie in PowerShell ein einzelnes Sternchen ( `*` ), um anstelle der herkömmlichen Inhalte Inhalte zu erhalten `*.*` .</span><span class="sxs-lookup"><span data-stu-id="0bb15-126">In PowerShell, use a single asterisk (`*`) to get contents, instead of the traditional `*.*`.</span></span> <span data-ttu-id="0bb15-127">Das Format wird buchstäblich interpretiert, sodass `*.*` keine Verzeichnisse oder Dateinamen ohne Punkt abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0bb15-127">The format is interpreted literally, so `*.*` wouldn't retrieve directories or filenames without a dot.</span></span>

### <span data-ttu-id="0bb15-128">Beispiel 5: erhalten einer Eigenschaft im angegebenen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="0bb15-128">Example 5: Get a property in the specified directory</span></span>

<span data-ttu-id="0bb15-129">In diesem Beispiel wird die **LastAccessTime** -Eigenschaft des `C:\Windows` Verzeichnisses abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0bb15-129">This example gets the **LastAccessTime** property of the `C:\Windows` directory.</span></span> <span data-ttu-id="0bb15-130">**LastAccessTime** ist nur eine Eigenschaft von Dateisystem Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="0bb15-130">**LastAccessTime** is just one property of file system directories.</span></span> <span data-ttu-id="0bb15-131">Um alle Eigenschaften eines Verzeichnisses anzuzeigen, geben Sie ein `(Get-Item <directory-name>) | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="0bb15-131">To see all the properties of a directory, type `(Get-Item <directory-name>) | Get-Member`.</span></span>

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### <span data-ttu-id="0bb15-132">Beispiel 6: Anzeigen des Inhalts eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="0bb15-132">Example 6: Show the contents of a registry key</span></span>

<span data-ttu-id="0bb15-133">Dieses Beispiel zeigt den Inhalt des **Microsoft. PowerShell** -Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="0bb15-133">This example shows the contents of the **Microsoft.PowerShell** registry key.</span></span> <span data-ttu-id="0bb15-134">Sie können dieses Cmdlet mit dem PowerShell-Registrierungs Anbieter verwenden, um Registrierungsschlüssel und-Unterschlüssel zu erhalten, aber Sie müssen das `Get-ItemProperty` Cmdlet verwenden, um die Registrierungs Werte und-Daten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bb15-134">You can use this cmdlet with the PowerShell Registry provider to get registry keys and subkeys, but you must use the `Get-ItemProperty` cmdlet to get the registry values and data.</span></span>

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### <span data-ttu-id="0bb15-135">Beispiel 7: erhalten von Elementen in einem Verzeichnis mit Ausschluss</span><span class="sxs-lookup"><span data-stu-id="0bb15-135">Example 7: Get items in a directory that have an exclusion</span></span>

<span data-ttu-id="0bb15-136">In diesem Beispiel werden Elemente im Windows-Verzeichnis mit Namen abgerufen, die einen Punkt ( `.` ) enthalten, aber nicht mit beginnen `w*` . Dieses Beispiel funktioniert nur, wenn der Pfad ein Platzhalter Zeichen ( `*` ) enthält, um den Inhalt des Elements anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0bb15-136">This example gets items in the Windows directory with names that include a dot (`.`), but don't begin with `w*`.This example works only when the path includes a wildcard character (`*`) to specify the contents of the item.</span></span>

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

### <span data-ttu-id="0bb15-137">Beispiel 8: erhalten von hardlinkinformationen</span><span class="sxs-lookup"><span data-stu-id="0bb15-137">Example 8: Getting hardlink information</span></span>

<span data-ttu-id="0bb15-138">In PowerShell 6,2 wurde eine Alternative Ansicht hinzugefügt, um hardlinkinformationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bb15-138">In PowerShell 6.2, an alternate view was added to get hardlink information.</span></span> <span data-ttu-id="0bb15-139">Um die hardlinkinformationen zu erhalten, übergeben Sie die Ausgabe an. `Format-Table -View childrenWithHardlink`</span><span class="sxs-lookup"><span data-stu-id="0bb15-139">To get the hardlink information, pipe the output to `Format-Table -View childrenWithHardlink`</span></span>

```powershell
Get-Item -Path C:\PathWhichIsAHardLink | Format-Table -View childrenWithHardlink
```

### <span data-ttu-id="0bb15-140">Beispiel 9: Ausgabe für die experimentelle Funktion psunixfilestat</span><span class="sxs-lookup"><span data-stu-id="0bb15-140">Example 9: Output for experimental feature PSUnixFileStat</span></span>

<span data-ttu-id="0bb15-141">In PowerShell 7 auf UNIX-Systemen stellt die experimentelle Funktion **psunixfilestat** eine UNIX-ähnliche Ausgabe bereit:</span><span class="sxs-lookup"><span data-stu-id="0bb15-141">In PowerShell 7 on Unix systems, the experimental feature **PSUnixFileStat** provides Unix-like output:</span></span>

```powershell
PS> Get-Item /Users
```

```Output
    Directory: /

UnixMode    User  Group   LastWriteTime      Size  Name
--------    ----  -----   -------------      ----  ----
drwxr-xr-x  root  admin   12/20/2019 11:46   192   Users
```

<span data-ttu-id="0bb15-142">Die neuen Eigenschaften, die nun Teil der Ausgabe sind, sind:</span><span class="sxs-lookup"><span data-stu-id="0bb15-142">The new properties that are now part of the output are:</span></span>

- <span data-ttu-id="0bb15-143">**Unixmode** ist die Dateiberechtigungen, die auf einem UNIX-System dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0bb15-143">**UnixMode** is the file permissions as represented on a Unix system</span></span>
- <span data-ttu-id="0bb15-144">Der **Benutzer** ist der Dateibesitzer.</span><span class="sxs-lookup"><span data-stu-id="0bb15-144">**User** is the file owner</span></span>
- <span data-ttu-id="0bb15-145">**Gruppe** ist der Gruppenbesitzer</span><span class="sxs-lookup"><span data-stu-id="0bb15-145">**Group** is the group owner</span></span>
- <span data-ttu-id="0bb15-146">**Größe** ist die Größe der Datei oder des Verzeichnisses, die auf einem UNIX-System dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0bb15-146">**Size** is the size of the file or directory as represented on a Unix system</span></span>

## <span data-ttu-id="0bb15-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0bb15-147">PARAMETERS</span></span>

### <span data-ttu-id="0bb15-148">-Stream</span><span class="sxs-lookup"><span data-stu-id="0bb15-148">-Stream</span></span>

<span data-ttu-id="0bb15-149">Ruft den angegebenen alternativen NTFS-Dateidatenstrom aus der Datei ab.</span><span class="sxs-lookup"><span data-stu-id="0bb15-149">Gets the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="0bb15-150">Geben Sie den Namen des Stroms ein.</span><span class="sxs-lookup"><span data-stu-id="0bb15-150">Enter the stream name.</span></span> <span data-ttu-id="0bb15-151">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0bb15-151">Wildcards are supported.</span></span> <span data-ttu-id="0bb15-152">Um alle Streams zu erhalten, verwenden Sie ein Sternchen ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="0bb15-152">To get all streams, use an asterisk (`*`).</span></span> <span data-ttu-id="0bb15-153">Dieser Parameter ist für Ordner nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="0bb15-153">This parameter isn't valid on folders.</span></span>

<span data-ttu-id="0bb15-154">**Stream** ist ein dynamischer Parameter, den der **File System** -Anbieter zum `Get-Item` Cmdlet hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="0bb15-154">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Item` cmdlet.</span></span>
<span data-ttu-id="0bb15-155">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="0bb15-155">This parameter works only in file system drives.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No alternate file streams
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="0bb15-156">-Credential</span><span class="sxs-lookup"><span data-stu-id="0bb15-156">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="0bb15-157">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0bb15-157">This parameter isn't supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="0bb15-158">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="0bb15-158">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0bb15-159">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="0bb15-159">-Exclude</span></span>

<span data-ttu-id="0bb15-160">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="0bb15-160">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="0bb15-161">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="0bb15-161">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0bb15-162">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="0bb15-162">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="0bb15-163">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="0bb15-163">Wildcard characters are permitted.</span></span> <span data-ttu-id="0bb15-164">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="0bb15-164">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="0bb15-165">-Filter</span><span class="sxs-lookup"><span data-stu-id="0bb15-165">-Filter</span></span>

<span data-ttu-id="0bb15-166">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="0bb15-166">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="0bb15-167">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der Filter unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0bb15-167">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="0bb15-168">Filter sind effizienter als andere Parameter.</span><span class="sxs-lookup"><span data-stu-id="0bb15-168">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="0bb15-169">Der Anbieter wendet den Filter an, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="0bb15-169">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="0bb15-170">Die Filter Zeichenfolge wird an die .NET-API zum Aufzählen von Dateien übermittelt.</span><span class="sxs-lookup"><span data-stu-id="0bb15-170">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="0bb15-171">Die API unterstützt nur `*` -und-Platzhalter `?` .</span><span class="sxs-lookup"><span data-stu-id="0bb15-171">The API only supports `*` and `?` wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="0bb15-172">-Force</span><span class="sxs-lookup"><span data-stu-id="0bb15-172">-Force</span></span>

<span data-ttu-id="0bb15-173">Gibt an, dass dieses Cmdlet Elemente abruft, auf die anderweitig nicht zugegriffen werden kann, beispielsweise ausgeblendete Elemente</span><span class="sxs-lookup"><span data-stu-id="0bb15-173">Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items.</span></span>
<span data-ttu-id="0bb15-174">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="0bb15-174">Implementation varies from provider to provider.</span></span> <span data-ttu-id="0bb15-175">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0bb15-175">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="0bb15-176">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="0bb15-176">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="0bb15-177">-Include</span><span class="sxs-lookup"><span data-stu-id="0bb15-177">-Include</span></span>

<span data-ttu-id="0bb15-178">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="0bb15-178">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="0bb15-179">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="0bb15-179">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0bb15-180">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="0bb15-180">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="0bb15-181">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="0bb15-181">Wildcard characters are permitted.</span></span> <span data-ttu-id="0bb15-182">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="0bb15-182">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="0bb15-183">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="0bb15-183">-LiteralPath</span></span>

<span data-ttu-id="0bb15-184">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="0bb15-184">Specifies a path to one or more locations.</span></span> <span data-ttu-id="0bb15-185">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0bb15-185">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="0bb15-186">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="0bb15-186">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0bb15-187">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="0bb15-187">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0bb15-188">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="0bb15-188">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="0bb15-189">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="0bb15-189">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0bb15-190">-Path</span><span class="sxs-lookup"><span data-stu-id="0bb15-190">-Path</span></span>

<span data-ttu-id="0bb15-191">Gibt den Pfad zu einem Element an.</span><span class="sxs-lookup"><span data-stu-id="0bb15-191">Specifies the path to an item.</span></span> <span data-ttu-id="0bb15-192">Dieses Cmdlet ruft das Element an der angegebenen Position ab.</span><span class="sxs-lookup"><span data-stu-id="0bb15-192">This cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="0bb15-193">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="0bb15-193">Wildcard characters are permitted.</span></span> <span data-ttu-id="0bb15-194">Dieser Parameter ist erforderlich, aber der Parameter Name **path** ist optional.</span><span class="sxs-lookup"><span data-stu-id="0bb15-194">This parameter is required, but the parameter name **Path** is optional.</span></span>

<span data-ttu-id="0bb15-195">Verwenden Sie einen Punkt ( `.` ), um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0bb15-195">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="0bb15-196">Verwenden Sie das Platzhalter Zeichen ( `*` ), um alle Elemente am aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0bb15-196">Use the wildcard character (`*`) to specify all the items in the current location.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="0bb15-197">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0bb15-197">CommonParameters</span></span>

<span data-ttu-id="0bb15-198">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="0bb15-198">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="0bb15-199">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0bb15-199">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0bb15-200">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0bb15-200">INPUTS</span></span>

### <span data-ttu-id="0bb15-201">System.String</span><span class="sxs-lookup"><span data-stu-id="0bb15-201">System.String</span></span>

<span data-ttu-id="0bb15-202">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="0bb15-202">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="0bb15-203">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0bb15-203">OUTPUTS</span></span>

### <span data-ttu-id="0bb15-204">System.Object</span><span class="sxs-lookup"><span data-stu-id="0bb15-204">System.Object</span></span>

<span data-ttu-id="0bb15-205">Dieses Cmdlet gibt die Objekte zurück, die es abruft.</span><span class="sxs-lookup"><span data-stu-id="0bb15-205">This cmdlet returns the objects that it gets.</span></span> <span data-ttu-id="0bb15-206">Der Typ wird durch den Typ der im Pfad enthaltenen Objekte bestimmt.</span><span class="sxs-lookup"><span data-stu-id="0bb15-206">The type is determined by the type of objects in the path.</span></span>

## <span data-ttu-id="0bb15-207">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0bb15-207">NOTES</span></span>

<span data-ttu-id="0bb15-208">Dieses Cmdlet weist keinen **recurse** -Parameter auf, da nur ein Element und nicht dessen Inhalt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0bb15-208">This cmdlet does not have a **Recurse** parameter, because it gets only an item, not its contents.</span></span>
<span data-ttu-id="0bb15-209">Um den Inhalt eines Elements rekursiv zu erhalten, verwenden Sie `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="0bb15-209">To get the contents of an item recursively, use `Get-ChildItem`.</span></span>

<span data-ttu-id="0bb15-210">Um durch die Registrierung zu navigieren, verwenden Sie dieses Cmdlet, um Registrierungsschlüssel zu erhalten, und, um `Get-ItemProperty` Registrierungs Werte und-Daten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bb15-210">To navigate through the registry, use this cmdlet to get registry keys and the `Get-ItemProperty` to get registry values and data.</span></span> <span data-ttu-id="0bb15-211">Die Registrierungswerte werden als Eigenschaften des Registrierungsschlüssels angesehen.</span><span class="sxs-lookup"><span data-stu-id="0bb15-211">The registry values are considered to be properties of the registry key.</span></span>
  
<span data-ttu-id="0bb15-212">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="0bb15-212">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="0bb15-213">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="0bb15-213">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="0bb15-214">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0bb15-214">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="0bb15-215">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0bb15-215">RELATED LINKS</span></span>

[<span data-ttu-id="0bb15-216">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="0bb15-216">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="0bb15-217">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="0bb15-217">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="0bb15-218">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="0bb15-218">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="0bb15-219">Move-Item</span><span class="sxs-lookup"><span data-stu-id="0bb15-219">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="0bb15-220">New-Item</span><span class="sxs-lookup"><span data-stu-id="0bb15-220">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="0bb15-221">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="0bb15-221">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="0bb15-222">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="0bb15-222">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="0bb15-223">Set-Item</span><span class="sxs-lookup"><span data-stu-id="0bb15-223">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="0bb15-224">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="0bb15-224">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="0bb15-225">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0bb15-225">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="0bb15-226">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="0bb15-226">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="0bb15-227">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0bb15-227">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
