---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: 67d9f351b8ef4936dcb4e9cff6583da0f464bc12
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "99601714"
---
# <span data-ttu-id="2c9b4-102">Get-Item</span><span class="sxs-lookup"><span data-stu-id="2c9b4-102">Get-Item</span></span>

## <span data-ttu-id="2c9b4-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2c9b4-103">SYNOPSIS</span></span>
<span data-ttu-id="2c9b4-104">Ruft das Element am angegebenen Speicherort ab.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-104">Gets the item at the specified location.</span></span>

## <span data-ttu-id="2c9b4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2c9b4-105">SYNTAX</span></span>

### <span data-ttu-id="2c9b4-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="2c9b4-106">Path (Default)</span></span>

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="2c9b4-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2c9b4-107">LiteralPath</span></span>

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Force] [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="2c9b4-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2c9b4-108">DESCRIPTION</span></span>

<span data-ttu-id="2c9b4-109">Mit dem- `Get-Item` Cmdlet wird das Element an der angegebenen Position abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-109">The `Get-Item` cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="2c9b4-110">Der Inhalt des Elements wird nicht am Speicherort angezeigt, es sei denn, Sie verwenden ein Platzhalter Zeichen ( `*` ), um den gesamten Inhalt des Elements anzufordern.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-110">It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.</span></span>

<span data-ttu-id="2c9b4-111">Dieses Cmdlet wird von PowerShell-Anbietern verwendet, um durch verschiedene Typen von Daten speichern zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-111">This cmdlet is used by PowerShell providers to navigate through different types of data stores.</span></span>

## <span data-ttu-id="2c9b4-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2c9b4-112">EXAMPLES</span></span>

### <span data-ttu-id="2c9b4-113">Beispiel 1: erhalten des aktuellen Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="2c9b4-113">Example 1: Get the current directory</span></span>

<span data-ttu-id="2c9b4-114">In diesem Beispiel wird das aktuelle Verzeichnis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-114">This example gets the current directory.</span></span> <span data-ttu-id="2c9b4-115">Der Punkt (".") stellt das Element am aktuellen Speicherort dar (nicht seinen Inhalt).</span><span class="sxs-lookup"><span data-stu-id="2c9b4-115">The dot ('.') represents the item at the current location (not its contents).</span></span>

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### <span data-ttu-id="2c9b4-116">Beispiel 2: alle Elemente im aktuellen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="2c9b4-116">Example 2: Get all the items in the current directory</span></span>

<span data-ttu-id="2c9b4-117">In diesem Beispiel werden alle Elemente im aktuellen Verzeichnis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-117">This example gets all the items in the current directory.</span></span> <span data-ttu-id="2c9b4-118">Das Platzhalter Zeichen ( `*` ) stellt den gesamten Inhalt des aktuellen Elements dar.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-118">The wildcard character (`*`) represents all the contents of the current item.</span></span>

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

### <span data-ttu-id="2c9b4-119">Beispiel 3: erhalten des aktuellen Verzeichnisses eines Laufwerks</span><span class="sxs-lookup"><span data-stu-id="2c9b4-119">Example 3: Get the current directory of a drive</span></span>

<span data-ttu-id="2c9b4-120">In diesem Beispiel wird das aktuelle Verzeichnis des `C:` Laufwerks abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-120">This example gets the current directory of the `C:` drive.</span></span> <span data-ttu-id="2c9b4-121">Das abgerufene Objekt stellt nur das Verzeichnis dar, nicht dessen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-121">The object that is retrieved represents only the directory, not its contents.</span></span>

```powershell
Get-Item C:\
```

### <span data-ttu-id="2c9b4-122">Beispiel 4: erhalten von Elementen im angegebenen Laufwerk</span><span class="sxs-lookup"><span data-stu-id="2c9b4-122">Example 4: Get items in the specified drive</span></span>

<span data-ttu-id="2c9b4-123">In diesem Beispiel werden die Elemente im `C:` Laufwerk abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-123">This example gets the items in the `C:` drive.</span></span> <span data-ttu-id="2c9b4-124">Das Platzhalter Zeichen ( `*` ) stellt alle Elemente im Container dar, nicht nur den Container.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-124">The wildcard character (`*`) represents all the items in the container, not just the container.</span></span>

```powershell
Get-Item C:\*
```

<span data-ttu-id="2c9b4-125">Verwenden Sie in PowerShell ein einzelnes Sternchen ( `*` ), um anstelle der herkömmlichen Inhalte Inhalte zu erhalten `*.*` .</span><span class="sxs-lookup"><span data-stu-id="2c9b4-125">In PowerShell, use a single asterisk (`*`) to get contents, instead of the traditional `*.*`.</span></span> <span data-ttu-id="2c9b4-126">Das Format wird buchstäblich interpretiert, sodass `*.*` keine Verzeichnisse oder Dateinamen ohne Punkt abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-126">The format is interpreted literally, so `*.*` wouldn't retrieve directories or filenames without a dot.</span></span>

### <span data-ttu-id="2c9b4-127">Beispiel 5: erhalten einer Eigenschaft im angegebenen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="2c9b4-127">Example 5: Get a property in the specified directory</span></span>

<span data-ttu-id="2c9b4-128">In diesem Beispiel wird die **LastAccessTime** -Eigenschaft des `C:\Windows` Verzeichnisses abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-128">This example gets the **LastAccessTime** property of the `C:\Windows` directory.</span></span> <span data-ttu-id="2c9b4-129">**LastAccessTime** ist nur eine Eigenschaft von Dateisystem Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-129">**LastAccessTime** is just one property of file system directories.</span></span> <span data-ttu-id="2c9b4-130">Um alle Eigenschaften eines Verzeichnisses anzuzeigen, geben Sie ein `(Get-Item <directory-name>) | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="2c9b4-130">To see all the properties of a directory, type `(Get-Item <directory-name>) | Get-Member`.</span></span>

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### <span data-ttu-id="2c9b4-131">Beispiel 6: Anzeigen des Inhalts eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="2c9b4-131">Example 6: Show the contents of a registry key</span></span>

<span data-ttu-id="2c9b4-132">Dieses Beispiel zeigt den Inhalt des **Microsoft. PowerShell** -Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-132">This example shows the contents of the **Microsoft.PowerShell** registry key.</span></span> <span data-ttu-id="2c9b4-133">Sie können dieses Cmdlet mit dem PowerShell-Registrierungs Anbieter verwenden, um Registrierungsschlüssel und-Unterschlüssel zu erhalten, aber Sie müssen das `Get-ItemProperty` Cmdlet verwenden, um die Registrierungs Werte und-Daten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-133">You can use this cmdlet with the PowerShell Registry provider to get registry keys and subkeys, but you must use the `Get-ItemProperty` cmdlet to get the registry values and data.</span></span>

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### <span data-ttu-id="2c9b4-134">Beispiel 7: erhalten von Elementen in einem Verzeichnis mit Ausschluss</span><span class="sxs-lookup"><span data-stu-id="2c9b4-134">Example 7: Get items in a directory that have an exclusion</span></span>

<span data-ttu-id="2c9b4-135">In diesem Beispiel werden Elemente im Windows-Verzeichnis mit Namen abgerufen, die einen Punkt ( `.` ) enthalten, aber nicht mit beginnen `w*` . Dieses Beispiel funktioniert nur, wenn der Pfad ein Platzhalter Zeichen ( `*` ) enthält, um den Inhalt des Elements anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-135">This example gets items in the Windows directory with names that include a dot (`.`), but don't begin with `w*`.This example works only when the path includes a wildcard character (`*`) to specify the contents of the item.</span></span>

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

### <span data-ttu-id="2c9b4-136">Beispiel 8: erhalten von hardlinkinformationen</span><span class="sxs-lookup"><span data-stu-id="2c9b4-136">Example 8: Getting hardlink information</span></span>

<span data-ttu-id="2c9b4-137">In PowerShell 6,2 wurde eine Alternative Ansicht hinzugefügt, um hardlinkinformationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-137">In PowerShell 6.2, an alternate view was added to get hardlink information.</span></span> <span data-ttu-id="2c9b4-138">Um die hardlinkinformationen zu erhalten, übergeben Sie die Ausgabe an. `Format-Table -View childrenWithHardlink`</span><span class="sxs-lookup"><span data-stu-id="2c9b4-138">To get the hardlink information, pipe the output to `Format-Table -View childrenWithHardlink`</span></span>

```powershell
Get-Item -Path C:\PathWhichIsAHardLink | Format-Table -View childrenWithHardlink
```

### <span data-ttu-id="2c9b4-139">Beispiel 9: Ausgabe für nicht-Windows-Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="2c9b4-139">Example 9: Output for Non-Windows Operating Systems</span></span>

<span data-ttu-id="2c9b4-140">In PowerShell 7,1 auf UNIX `Get-Item` -Systemen bietet das Cmdlet eine UNIX-ähnliche Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2c9b4-140">In PowerShell 7.1 on Unix systems, the `Get-Item` cmdlet provides Unix-like output:</span></span>

```powershell
PS> Get-Item /Users
```

```Output
    Directory: /

UnixMode    User  Group   LastWriteTime      Size  Name
--------    ----  -----   -------------      ----  ----
drwxr-xr-x  root  admin   12/20/2019 11:46   192   Users
```

<span data-ttu-id="2c9b4-141">Die neuen Eigenschaften, die nun Teil der Ausgabe sind, sind:</span><span class="sxs-lookup"><span data-stu-id="2c9b4-141">The new properties that are now part of the output are:</span></span>

- <span data-ttu-id="2c9b4-142">**Unixmode** ist die Dateiberechtigungen, die auf einem UNIX-System dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-142">**UnixMode** is the file permissions as represented on a Unix system</span></span>
- <span data-ttu-id="2c9b4-143">Der **Benutzer** ist der Dateibesitzer.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-143">**User** is the file owner</span></span>
- <span data-ttu-id="2c9b4-144">**Gruppe** ist der Gruppenbesitzer</span><span class="sxs-lookup"><span data-stu-id="2c9b4-144">**Group** is the group owner</span></span>
- <span data-ttu-id="2c9b4-145">**Größe** ist die Größe der Datei oder des Verzeichnisses, die auf einem UNIX-System dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-145">**Size** is the size of the file or directory as represented on a Unix system</span></span>

> [!NOTE]
> <span data-ttu-id="2c9b4-146">Diese Funktion wurde in PowerShell 7,1 von "experimentell" in "Mainstream" verlagert.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-146">This feature was moved from experimental to mainstream in PowerShell 7.1.</span></span>

## <span data-ttu-id="2c9b4-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2c9b4-147">PARAMETERS</span></span>

### <span data-ttu-id="2c9b4-148">-Stream</span><span class="sxs-lookup"><span data-stu-id="2c9b4-148">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="2c9b4-149">Dieser Parameter ist nur unter Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-149">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="2c9b4-150">Ruft den angegebenen alternativen Datenstrom aus der Datei ab.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-150">Gets the specified alternative data stream from the file.</span></span> <span data-ttu-id="2c9b4-151">Geben Sie den Namen des Stroms ein.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-151">Enter the stream name.</span></span> <span data-ttu-id="2c9b4-152">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-152">Wildcards are supported.</span></span> <span data-ttu-id="2c9b4-153">Um alle Streams zu erhalten, verwenden Sie ein Sternchen ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="2c9b4-153">To get all streams, use an asterisk (`*`).</span></span> <span data-ttu-id="2c9b4-154">Dieser Parameter ist für Verzeichnisse gültig, aber beachten Sie, dass Verzeichnisse standardmäßig nicht über Datenströme verfügen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-154">This parameter is valid on directories, but note that directories do not have data streams by default.</span></span>

<span data-ttu-id="2c9b4-155">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-155">This parameter was introduced in PowerShell 3.0.</span></span>  <span data-ttu-id="2c9b4-156">Ab PowerShell 7,2 `Get-Item` kann Alternative Datenströme aus Verzeichnissen und Dateien erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-156">As of PowerShell 7.2, `Get-Item` can get alternative data streams from directories as well as files.</span></span>

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

### <span data-ttu-id="2c9b4-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="2c9b4-157">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="2c9b4-158">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-158">This parameter isn't supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="2c9b4-159">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="2c9b4-159">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="2c9b4-160">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="2c9b4-160">-Exclude</span></span>

<span data-ttu-id="2c9b4-161">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-161">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="2c9b4-162">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-162">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2c9b4-163">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="2c9b4-163">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="2c9b4-164">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-164">Wildcard characters are permitted.</span></span> <span data-ttu-id="2c9b4-165">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-165">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="2c9b4-166">-Filter</span><span class="sxs-lookup"><span data-stu-id="2c9b4-166">-Filter</span></span>

<span data-ttu-id="2c9b4-167">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-167">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="2c9b4-168">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der Filter unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-168">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="2c9b4-169">Filter sind effizienter als andere Parameter.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-169">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="2c9b4-170">Der Anbieter wendet den Filter an, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-170">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="2c9b4-171">Die Filter Zeichenfolge wird an die .NET-API zum Aufzählen von Dateien übermittelt.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-171">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="2c9b4-172">Die API unterstützt nur `*` -und-Platzhalter `?` .</span><span class="sxs-lookup"><span data-stu-id="2c9b4-172">The API only supports `*` and `?` wildcards.</span></span>

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

### <span data-ttu-id="2c9b4-173">-Force</span><span class="sxs-lookup"><span data-stu-id="2c9b4-173">-Force</span></span>

<span data-ttu-id="2c9b4-174">Gibt an, dass dieses Cmdlet Elemente abruft, auf die anderweitig nicht zugegriffen werden kann, beispielsweise ausgeblendete Elemente</span><span class="sxs-lookup"><span data-stu-id="2c9b4-174">Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items.</span></span>
<span data-ttu-id="2c9b4-175">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-175">Implementation varies from provider to provider.</span></span> <span data-ttu-id="2c9b4-176">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="2c9b4-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="2c9b4-177">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-177">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="2c9b4-178">-Include</span><span class="sxs-lookup"><span data-stu-id="2c9b4-178">-Include</span></span>

<span data-ttu-id="2c9b4-179">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-179">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="2c9b4-180">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-180">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2c9b4-181">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="2c9b4-181">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="2c9b4-182">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-182">Wildcard characters are permitted.</span></span> <span data-ttu-id="2c9b4-183">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-183">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="2c9b4-184">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="2c9b4-184">-LiteralPath</span></span>

<span data-ttu-id="2c9b4-185">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-185">Specifies a path to one or more locations.</span></span> <span data-ttu-id="2c9b4-186">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-186">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="2c9b4-187">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-187">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="2c9b4-188">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-188">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="2c9b4-189">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-189">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="2c9b4-190">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="2c9b4-190">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="2c9b4-191">-Path</span><span class="sxs-lookup"><span data-stu-id="2c9b4-191">-Path</span></span>

<span data-ttu-id="2c9b4-192">Gibt den Pfad zu einem Element an.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-192">Specifies the path to an item.</span></span> <span data-ttu-id="2c9b4-193">Dieses Cmdlet ruft das Element an der angegebenen Position ab.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-193">This cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="2c9b4-194">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-194">Wildcard characters are permitted.</span></span> <span data-ttu-id="2c9b4-195">Dieser Parameter ist erforderlich, aber der Parameter Name **path** ist optional.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-195">This parameter is required, but the parameter name **Path** is optional.</span></span>

<span data-ttu-id="2c9b4-196">Verwenden Sie einen Punkt ( `.` ), um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-196">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="2c9b4-197">Verwenden Sie das Platzhalter Zeichen ( `*` ), um alle Elemente am aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-197">Use the wildcard character (`*`) to specify all the items in the current location.</span></span>

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

### <span data-ttu-id="2c9b4-198">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2c9b4-198">CommonParameters</span></span>

<span data-ttu-id="2c9b4-199">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2c9b4-200">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2c9b4-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2c9b4-201">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2c9b4-201">INPUTS</span></span>

### <span data-ttu-id="2c9b4-202">System.String</span><span class="sxs-lookup"><span data-stu-id="2c9b4-202">System.String</span></span>

<span data-ttu-id="2c9b4-203">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-203">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="2c9b4-204">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2c9b4-204">OUTPUTS</span></span>

### <span data-ttu-id="2c9b4-205">System.Object</span><span class="sxs-lookup"><span data-stu-id="2c9b4-205">System.Object</span></span>

<span data-ttu-id="2c9b4-206">Dieses Cmdlet gibt die Objekte zurück, die es abruft.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-206">This cmdlet returns the objects that it gets.</span></span> <span data-ttu-id="2c9b4-207">Der Typ wird durch den Typ der im Pfad enthaltenen Objekte bestimmt.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-207">The type is determined by the type of objects in the path.</span></span>

## <span data-ttu-id="2c9b4-208">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2c9b4-208">NOTES</span></span>

<span data-ttu-id="2c9b4-209">Dieses Cmdlet weist keinen **recurse** -Parameter auf, da nur ein Element und nicht dessen Inhalt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-209">This cmdlet does not have a **Recurse** parameter, because it gets only an item, not its contents.</span></span>
<span data-ttu-id="2c9b4-210">Um den Inhalt eines Elements rekursiv zu erhalten, verwenden Sie `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="2c9b4-210">To get the contents of an item recursively, use `Get-ChildItem`.</span></span>

<span data-ttu-id="2c9b4-211">Um durch die Registrierung zu navigieren, verwenden Sie dieses Cmdlet, um Registrierungsschlüssel zu erhalten, und, um `Get-ItemProperty` Registrierungs Werte und-Daten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-211">To navigate through the registry, use this cmdlet to get registry keys and the `Get-ItemProperty` to get registry values and data.</span></span> <span data-ttu-id="2c9b4-212">Die Registrierungswerte werden als Eigenschaften des Registrierungsschlüssels angesehen.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-212">The registry values are considered to be properties of the registry key.</span></span>

<span data-ttu-id="2c9b4-213">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="2c9b4-213">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="2c9b4-214">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="2c9b4-214">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="2c9b4-215">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="2c9b4-215">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="2c9b4-216">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2c9b4-216">RELATED LINKS</span></span>

[<span data-ttu-id="2c9b4-217">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="2c9b4-217">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="2c9b4-218">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="2c9b4-218">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="2c9b4-219">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="2c9b4-219">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="2c9b4-220">Move-Item</span><span class="sxs-lookup"><span data-stu-id="2c9b4-220">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="2c9b4-221">New-Item</span><span class="sxs-lookup"><span data-stu-id="2c9b4-221">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="2c9b4-222">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="2c9b4-222">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="2c9b4-223">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="2c9b4-223">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="2c9b4-224">Set-Item</span><span class="sxs-lookup"><span data-stu-id="2c9b4-224">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="2c9b4-225">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="2c9b4-225">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="2c9b4-226">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="2c9b4-226">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="2c9b4-227">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="2c9b4-227">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="2c9b4-228">about_Providers</span><span class="sxs-lookup"><span data-stu-id="2c9b4-228">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

