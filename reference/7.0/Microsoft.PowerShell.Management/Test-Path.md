---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: fcfb974a360c450f474ba97d65190b019860d8c4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210580"
---
# <span data-ttu-id="f73ba-103">Test-Path</span><span class="sxs-lookup"><span data-stu-id="f73ba-103">Test-Path</span></span>

## <span data-ttu-id="f73ba-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f73ba-104">SYNOPSIS</span></span>
<span data-ttu-id="f73ba-105">Bestimmt, ob alle Elemente eines Pfads vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f73ba-105">Determines whether all elements of a path exist.</span></span>

## <span data-ttu-id="f73ba-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f73ba-106">SYNTAX</span></span>

### <span data-ttu-id="f73ba-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="f73ba-107">Path (Default)</span></span>

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="f73ba-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f73ba-108">LiteralPath</span></span>

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## <span data-ttu-id="f73ba-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f73ba-109">DESCRIPTION</span></span>

<span data-ttu-id="f73ba-110">Das- `Test-Path` Cmdlet bestimmt, ob alle Elemente des Pfads vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f73ba-110">The `Test-Path` cmdlet determines whether all elements of the path exist.</span></span> <span data-ttu-id="f73ba-111">Er gibt zurück, `$True` Wenn alle Elemente vorhanden sind und ggf `$False` . fehlende vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f73ba-111">It returns `$True` if all elements exist and `$False` if any are missing.</span></span> <span data-ttu-id="f73ba-112">Es kann auch festzustellen, ob die Pfad Syntax gültig ist und ob der Pfad zu einem Container oder einem Terminal oder einem Blatt Element führt.</span><span class="sxs-lookup"><span data-stu-id="f73ba-112">It can also tell whether the path syntax is valid and whether the path leads to a container or a terminal or leaf element.</span></span> <span data-ttu-id="f73ba-113">Wenn ein Leerraum `Path` eine leere Zeichenfolge ist, `$False` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f73ba-113">If the `Path` is whitespace an empty string, then `$False` is returned.</span></span> <span data-ttu-id="f73ba-114">Wenn `Path` `$null` , `$null` ein Array oder ein leeres Array ist, wird ein Fehler ohne Abbruch zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f73ba-114">If the `Path` is `$null`, array of `$null` or empty array, a non-terminating error is returned.</span></span>

## <span data-ttu-id="f73ba-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f73ba-115">EXAMPLES</span></span>

### <span data-ttu-id="f73ba-116">Beispiel 1: Testen eines Pfads</span><span class="sxs-lookup"><span data-stu-id="f73ba-116">Example 1: Test a path</span></span>

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

<span data-ttu-id="f73ba-117">Mit diesem Befehl wird überprüft, ob alle Elemente im Pfad vorhanden sind, d. h. das Verzeichnis "C:", das Verzeichnis "Dokumente und Einstellungen" und das Verzeichnis "DavidC".</span><span class="sxs-lookup"><span data-stu-id="f73ba-117">This command checks whether all elements in the path exist, that is, the C: directory, the Documents and Settings directory, and the DavidC directory.</span></span> <span data-ttu-id="f73ba-118">Wenn eine solche fehlt, gibt das Cmdlet zurück `$False` .</span><span class="sxs-lookup"><span data-stu-id="f73ba-118">If any are missing, the cmdlet returns `$False`.</span></span>
<span data-ttu-id="f73ba-119">Andernfalls wird `$True`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f73ba-119">Otherwise, it returns `$True`.</span></span>

### <span data-ttu-id="f73ba-120">Beispiel 2: Testen des Pfads eines Profils</span><span class="sxs-lookup"><span data-stu-id="f73ba-120">Example 2: Test the path of a profile</span></span>

```powershell
Test-Path -Path $profile
```

```Output
False
```

```powershell
Test-Path -Path $profile -IsValid
```

```Output
True
```

<span data-ttu-id="f73ba-121">Mit diesen Befehlen wird der Pfad des PowerShell-Profils getestet.</span><span class="sxs-lookup"><span data-stu-id="f73ba-121">These commands test the path of the PowerShell profile.</span></span>

<span data-ttu-id="f73ba-122">Mit dem ersten Befehl wird bestimmt, ob alle Elemente im Pfad vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f73ba-122">The first command determines whether all elements in the path exist.</span></span> <span data-ttu-id="f73ba-123">Mit dem zweiten Befehl wird bestimmt, ob die Syntax des Pfads gültig ist.</span><span class="sxs-lookup"><span data-stu-id="f73ba-123">The second command determines whether the syntax of the path is correct.</span></span> <span data-ttu-id="f73ba-124">In diesem Fall ist der Pfad `$False` , aber die Syntax ist richtig `$True` .</span><span class="sxs-lookup"><span data-stu-id="f73ba-124">In this case, the path is `$False`, but the syntax is correct `$True`.</span></span> <span data-ttu-id="f73ba-125">Diese Befehle verwenden `$profile` , die automatische Variable, die auf den Speicherort für das Profil zeigt, selbst wenn das Profil nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f73ba-125">These commands use `$profile`, the automatic variable that points to the location for the profile, even if the profile does not exist.</span></span>

<span data-ttu-id="f73ba-126">Weitere Informationen zu automatischen Variablen finden Sie unter %%amp;quot;about_Automatic_Variables%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="f73ba-126">For more information about automatic variables, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="f73ba-127">Beispiel 3: überprüfen, ob neben einem angegebenen Typ Dateien vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="f73ba-127">Example 3: Check whether there are any files besides a specified type</span></span>

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

<span data-ttu-id="f73ba-128">Mit diesem Befehl wird überprüft, ob im Verzeichnis der kommerziellen Gebäude andere Dateien als DWG-Dateien vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f73ba-128">This command checks whether there are any files in the Commercial Buildings directory other than .dwg files.</span></span>

<span data-ttu-id="f73ba-129">Der Befehl verwendet den **path** -Parameter, um den Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f73ba-129">The command uses the **Path** parameter to specify the path.</span></span> <span data-ttu-id="f73ba-130">Da der Pfad ein Leerzeichen enthält, wird der Pfad in Anführungszeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f73ba-130">Because the path includes a space, the path is enclosed in quotation marks.</span></span> <span data-ttu-id="f73ba-131">Das Sternchen am Ende des Pfads gibt den Inhalt des Verzeichnisses %%amp;quot;Commercial Building%%amp;quot; an.</span><span class="sxs-lookup"><span data-stu-id="f73ba-131">The asterisk at the end of the path indicates the contents of the Commercial Building directory.</span></span> <span data-ttu-id="f73ba-132">Bei langen Pfaden, wie z. b. diesem, geben Sie die ersten Buchstaben des Pfads ein, und verwenden Sie dann die Tab-Taste, um den Pfad abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f73ba-132">With long paths, such as this one, type the first few letters of the path, and then use the TAB key to complete the path.</span></span>

<span data-ttu-id="f73ba-133">Der Befehl gibt den **Exclude** -Parameter zum Angeben von Dateien an, die in der Auswertung ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="f73ba-133">The command specifies the **Exclude** parameter to specify files that will be omitted from the evaluation.</span></span>

<span data-ttu-id="f73ba-134">Da das Verzeichnis in diesem Fall nur DWG-Dateien enthält, lautet das Ergebnis `$False` .</span><span class="sxs-lookup"><span data-stu-id="f73ba-134">In this case, because the directory contains only .dwg files, the result is `$False`.</span></span>

### <span data-ttu-id="f73ba-135">Beispiel 4: Überprüfen auf eine Datei</span><span class="sxs-lookup"><span data-stu-id="f73ba-135">Example 4: Check for a file</span></span>

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

<span data-ttu-id="f73ba-136">Mit diesem Befehl wird überprüft, ob der in der Variablen gespeicherte Pfad `$profile` zu einer Datei führt.</span><span class="sxs-lookup"><span data-stu-id="f73ba-136">This command checks whether the path stored in the `$profile` variable leads to a file.</span></span> <span data-ttu-id="f73ba-137">In diesem Fall `.ps1` gibt das Cmdlet zurück, da es sich bei dem PowerShell-Profil um eine Datei handelt `$True` .</span><span class="sxs-lookup"><span data-stu-id="f73ba-137">In this case, because the PowerShell profile is a `.ps1` file, the cmdlet returns `$True`.</span></span>

### <span data-ttu-id="f73ba-138">Beispiel 5: Überprüfen der Pfade in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="f73ba-138">Example 5: Check paths in the Registry</span></span>

<span data-ttu-id="f73ba-139">Diese Befehle werden `Test-Path` mit dem PowerShell-Registrierungs Anbieter verwendet.</span><span class="sxs-lookup"><span data-stu-id="f73ba-139">These commands use `Test-Path` with the PowerShell registry provider.</span></span>

<span data-ttu-id="f73ba-140">Der erste Befehl testet, ob der Registrierungs Pfad des **Microsoft. PowerShell** -Registrierungsschlüssels auf dem System richtig ist.</span><span class="sxs-lookup"><span data-stu-id="f73ba-140">The first command tests whether the registry path of the **Microsoft.PowerShell** registry key is correct on the system.</span></span> <span data-ttu-id="f73ba-141">Wenn PowerShell ordnungsgemäß installiert ist, wird vom Cmdlet zurückgegeben `$True` .</span><span class="sxs-lookup"><span data-stu-id="f73ba-141">If PowerShell is installed correctly, the cmdlet returns `$True`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f73ba-142">`Test-Path` funktioniert nicht mit allen PowerShell-Anbietern ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="f73ba-142">`Test-Path` does not work correctly with all PowerShell providers.</span></span> <span data-ttu-id="f73ba-143">Beispielsweise können Sie verwenden, `Test-Path` um den Pfad eines Registrierungsschlüssels zu testen, aber wenn Sie ihn zum Testen des Pfads eines Registrierungs Eintrags verwenden, wird immer zurückgegeben, `$False` auch wenn der Registrierungs Eintrag vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f73ba-143">For example, you can use `Test-Path` to test the path of a registry key, but if you use it to test the path of a registry entry, it always returns `$False`, even if the registry entry is present.</span></span>

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell"
```

```Output
True
```

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell\ExecutionPolicy"
```

```Output
False
```

### <span data-ttu-id="f73ba-144">Beispiel 6: testen, ob eine Datei neuer als ein bestimmtes Datum ist</span><span class="sxs-lookup"><span data-stu-id="f73ba-144">Example 6: Test if a file is newer than a specified date</span></span>

<span data-ttu-id="f73ba-145">Dieser Befehl verwendet den dynamischen Parameter " **newerthan** ", um zu bestimmen, ob die Datei "PowerShell.exe" auf dem Computer neuer als "Juli 13, 2009" ist.</span><span class="sxs-lookup"><span data-stu-id="f73ba-145">This command uses the **NewerThan** dynamic parameter to determine whether the "PowerShell.exe" file on the computer is newer than "July 13, 2009".</span></span>

<span data-ttu-id="f73ba-146">Der Parameter NewerThan funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="f73ba-146">The NewerThan parameter works only in file system drives.</span></span>

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### <span data-ttu-id="f73ba-147">Beispiel 7: Testen eines Pfads mit NULL als Wert</span><span class="sxs-lookup"><span data-stu-id="f73ba-147">Example 7: Test a path with null as the value</span></span>

<span data-ttu-id="f73ba-148">Der für `null` `null` ein Array oder ein leeres Array zurückgegebene Fehler ist ein Fehler ohne Abbruch.</span><span class="sxs-lookup"><span data-stu-id="f73ba-148">The error returned for `null`, array of `null` or empty array is a non-terminating error.</span></span> <span data-ttu-id="f73ba-149">Dies kann mithilfe von unterdrückt werden `-ErrorAction SilentlyContinue` .</span><span class="sxs-lookup"><span data-stu-id="f73ba-149">It can be suppress by using `-ErrorAction SilentlyContinue`.</span></span> <span data-ttu-id="f73ba-150">Im folgenden Beispiel werden alle Fälle gezeigt, die den Fehler zurückgeben `NullPathNotPermitted` .</span><span class="sxs-lookup"><span data-stu-id="f73ba-150">The following example shows all cases which return the `NullPathNotPermitted` error.</span></span>

```powershell
Test-Path $null
Test-Path $null, $null
Test-Path @()
```

```Output
Test-Path : Cannot bind argument to parameter 'Path' because it is null.
At line:1 char:11
+ Test-Path $null
+           ~~~~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorNullNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

### <span data-ttu-id="f73ba-151">Beispiel 8: Testen eines Pfads mit Leerraum als Wert</span><span class="sxs-lookup"><span data-stu-id="f73ba-151">Example 8: Test a path with whitespace as the value</span></span>

<span data-ttu-id="f73ba-152">Wenn ein Leerzeichen oder eine leere Zeichenfolge für den Parameter bereitgestellt wird `-Path` , wird **false** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f73ba-152">When a whitespace or empty string is provided for the the `-Path` parameter, it returns **False** .</span></span>
<span data-ttu-id="f73ba-153">Das folgende Beispiel zeigt Leerräume und eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f73ba-153">The following example show whitespace and empty string.</span></span>

```powershell
Test-Path ' '
Test-Path ''
```

```Output
False
False
```

## <span data-ttu-id="f73ba-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f73ba-154">PARAMETERS</span></span>

### <span data-ttu-id="f73ba-155">-Credential</span><span class="sxs-lookup"><span data-stu-id="f73ba-155">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="f73ba-156">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f73ba-156">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="f73ba-157">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="f73ba-157">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f73ba-158">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="f73ba-158">-Exclude</span></span>

<span data-ttu-id="f73ba-159">Gibt die Elemente an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="f73ba-159">Specifies items that this cmdlet omits.</span></span> <span data-ttu-id="f73ba-160">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f73ba-160">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f73ba-161">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="f73ba-161">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="f73ba-162">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f73ba-162">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="f73ba-163">-Filter</span><span class="sxs-lookup"><span data-stu-id="f73ba-163">-Filter</span></span>

<span data-ttu-id="f73ba-164">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="f73ba-164">Specifies a filter in the format or language of the provider.</span></span> <span data-ttu-id="f73ba-165">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f73ba-165">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f73ba-166">Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="f73ba-166">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="f73ba-167">Filter sind effizienter als andere Parameter, da Sie vom Anbieter beim Abrufen der Objekte angewendet werden, anstatt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="f73ba-167">Filters are more efficient than other parameters, because the provider applies them when it retrieves the objects instead of having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="f73ba-168">-Include</span><span class="sxs-lookup"><span data-stu-id="f73ba-168">-Include</span></span>

<span data-ttu-id="f73ba-169">Gibt die Pfade an, die von diesem Cmdlet getestet werden.</span><span class="sxs-lookup"><span data-stu-id="f73ba-169">Specifies paths that this cmdlet tests.</span></span> <span data-ttu-id="f73ba-170">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f73ba-170">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="f73ba-171">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="f73ba-171">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="f73ba-172">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f73ba-172">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="f73ba-173">-IsValid</span><span class="sxs-lookup"><span data-stu-id="f73ba-173">-IsValid</span></span>

<span data-ttu-id="f73ba-174">Gibt an, dass dieses Cmdlet die Syntax des Pfads testet, unabhängig davon, ob die Elemente des Pfads vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f73ba-174">Indicates that this cmdlet tests the syntax of the path, regardless of whether the elements of the path exist.</span></span> <span data-ttu-id="f73ba-175">Dieses Cmdlet gibt zurück, `$True` Wenn die Pfad Syntax gültig ist, `$False` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="f73ba-175">This cmdlet returns `$True` if the path syntax is valid and `$False` if it is not.</span></span>

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

### <span data-ttu-id="f73ba-176">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="f73ba-176">-LiteralPath</span></span>

<span data-ttu-id="f73ba-177">Gibt den zu testenden Pfad an.</span><span class="sxs-lookup"><span data-stu-id="f73ba-177">Specifies a path to be tested.</span></span> <span data-ttu-id="f73ba-178">Im Gegensatz zu **Path** wird der Wert des **LiteralPath** -Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f73ba-178">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="f73ba-179">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="f73ba-179">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="f73ba-180">Wenn der Pfad Zeichen enthält, die von PowerShell als Escapesequenzen interpretiert werden können, müssen Sie den Pfad in einfache Anführungszeichen einschließen, damit diese nicht interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="f73ba-180">If the path includes characters that could be interpreted by PowerShell as escape sequences, you must enclose the path in single quote so that they won't be interpreted.</span></span>

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

### <span data-ttu-id="f73ba-181">-"-Nals"</span><span class="sxs-lookup"><span data-stu-id="f73ba-181">-NewerThan</span></span>

<span data-ttu-id="f73ba-182">Geben Sie eine Uhrzeit als **DateTime** -Objekt an.</span><span class="sxs-lookup"><span data-stu-id="f73ba-182">Specify a time as a **DateTime** object.</span></span>

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f73ba-183">-Olderthan</span><span class="sxs-lookup"><span data-stu-id="f73ba-183">-OlderThan</span></span>

<span data-ttu-id="f73ba-184">Geben Sie eine Uhrzeit als **DateTime** -Objekt an.</span><span class="sxs-lookup"><span data-stu-id="f73ba-184">Specify a time as a **DateTime** object.</span></span>

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f73ba-185">-Path</span><span class="sxs-lookup"><span data-stu-id="f73ba-185">-Path</span></span>

<span data-ttu-id="f73ba-186">Gibt den zu testenden Pfad an.</span><span class="sxs-lookup"><span data-stu-id="f73ba-186">Specifies a path to be tested.</span></span> <span data-ttu-id="f73ba-187">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f73ba-187">Wildcard characters are permitted.</span></span> <span data-ttu-id="f73ba-188">Wenn der Pfad Leerzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="f73ba-188">If the path includes spaces, enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="f73ba-189">-PathType</span><span class="sxs-lookup"><span data-stu-id="f73ba-189">-PathType</span></span>

<span data-ttu-id="f73ba-190">Gibt den Typ des letzten Elements im Pfad an.</span><span class="sxs-lookup"><span data-stu-id="f73ba-190">Specifies the type of the final element in the path.</span></span> <span data-ttu-id="f73ba-191">Dieses Cmdlet gibt zurück, `$True` Wenn das Element den angegebenen Typ hat und `$False` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="f73ba-191">This cmdlet returns `$True` if the element is of the specified type and `$False` if it is not.</span></span> <span data-ttu-id="f73ba-192">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="f73ba-192">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f73ba-193">Container.</span><span class="sxs-lookup"><span data-stu-id="f73ba-193">Container.</span></span>
  <span data-ttu-id="f73ba-194">Ein Element, das andere Elemente enthält, beispielsweise ein Verzeichnis oder einen Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="f73ba-194">An element that contains other elements, such as a directory or registry key.</span></span>
- <span data-ttu-id="f73ba-195">Dach.</span><span class="sxs-lookup"><span data-stu-id="f73ba-195">Leaf.</span></span>
  <span data-ttu-id="f73ba-196">Ein Element, das keine anderen Elemente enthält, beispielsweise eine Datei.</span><span class="sxs-lookup"><span data-stu-id="f73ba-196">An element that does not contain other elements, such as a file.</span></span>
- <span data-ttu-id="f73ba-197">Irgendeiner.</span><span class="sxs-lookup"><span data-stu-id="f73ba-197">Any.</span></span>
  <span data-ttu-id="f73ba-198">Ein Container- oder Leaf-Element.</span><span class="sxs-lookup"><span data-stu-id="f73ba-198">Either a container or a leaf.</span></span>

<span data-ttu-id="f73ba-199">Gibt an, ob das letzte Element im Pfad einen bestimmten Typ aufweist.</span><span class="sxs-lookup"><span data-stu-id="f73ba-199">Tells whether the final element in the path is of a particular type.</span></span>

> [!CAUTION]
>
> <span data-ttu-id="f73ba-200">Bis zur PowerShell-Version 6.1.2, wenn die Schalter **IsValid** und **PathType** zusammen angegeben werden, `Test-Path` ignoriert das Cmdlet den **PathType** -Switch und überprüft nur den syntaktischen Pfad, ohne den Pfadtyp zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f73ba-200">Up to PowerShell version 6.1.2, when the **IsValid** and **PathType** switches are specified together, the `Test-Path` cmdlet ignores the **PathType** switch and only validates the syntactic path without validating the path type.</span></span>
>
> <span data-ttu-id="f73ba-201">Gemäß der [Problem #8607](https://github.com/PowerShell/PowerShell/issues/8607)kann das Beheben dieses Verhaltens eine Breaking Change in einer zukünftigen Version sein, bei der die " **IsValid** "-und " **PathType** "-Schalter zu separaten Parametersätzen gehören und somit nicht gleichzeitig verwendet werden können, um diese Verwirrung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f73ba-201">According to [issue #8607](https://github.com/PowerShell/PowerShell/issues/8607), fixing this behavior may be a breaking change in a future version, where the **IsValid** and **PathType** switches belong to separate parameter sets, and thus, cannot be used together avoiding this confusion.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.TestPathType
Parameter Sets: (All)
Aliases: Type
Accepted values: Any, Container, Leaf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f73ba-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f73ba-202">CommonParameters</span></span>

<span data-ttu-id="f73ba-203">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="f73ba-203">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="f73ba-204">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="f73ba-204">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f73ba-205">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f73ba-205">INPUTS</span></span>

### <span data-ttu-id="f73ba-206">System.String</span><span class="sxs-lookup"><span data-stu-id="f73ba-206">System.String</span></span>

<span data-ttu-id="f73ba-207">Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="f73ba-207">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="f73ba-208">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f73ba-208">OUTPUTS</span></span>

### <span data-ttu-id="f73ba-209">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="f73ba-209">System.Boolean</span></span>

<span data-ttu-id="f73ba-210">Mit dem-Cmdlet wird ein **boolescher** Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f73ba-210">The cmdlet returns a **Boolean** value.</span></span>

## <span data-ttu-id="f73ba-211">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f73ba-211">NOTES</span></span>

<span data-ttu-id="f73ba-212">Die Cmdlets, die das **Pfad** -Substantiv enthalten (die **path** -Cmdlets), funktionieren mit Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f73ba-212">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="f73ba-213">Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f73ba-213">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="f73ba-214">Verwenden Sie Sie wie **dirname** , **normpath** , **realpath** , **Join** oder andere Pfad Manipulatoren.</span><span class="sxs-lookup"><span data-stu-id="f73ba-214">Use them as you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="f73ba-215">Der `Test-Path` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f73ba-215">The `Test-Path` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="f73ba-216">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="f73ba-216">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="f73ba-217">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="f73ba-217">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="f73ba-218">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f73ba-218">RELATED LINKS</span></span>

[<span data-ttu-id="f73ba-219">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="f73ba-219">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="f73ba-220">Join-Path</span><span class="sxs-lookup"><span data-stu-id="f73ba-220">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="f73ba-221">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="f73ba-221">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="f73ba-222">Split-Path</span><span class="sxs-lookup"><span data-stu-id="f73ba-222">Split-Path</span></span>](Split-Path.md)
