---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: ced5a5db05674c15fefada73ab55969d724117e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214332"
---
# <span data-ttu-id="aeadb-103">Test-Path</span><span class="sxs-lookup"><span data-stu-id="aeadb-103">Test-Path</span></span>

## <span data-ttu-id="aeadb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="aeadb-104">SYNOPSIS</span></span>
<span data-ttu-id="aeadb-105">Bestimmt, ob alle Elemente eines Pfads vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="aeadb-105">Determines whether all elements of a path exist.</span></span>

## <span data-ttu-id="aeadb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aeadb-106">SYNTAX</span></span>

### <span data-ttu-id="aeadb-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="aeadb-107">Path (Default)</span></span>

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>] [-UseTransaction]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="aeadb-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="aeadb-108">LiteralPath</span></span>

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>] [-UseTransaction]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## <span data-ttu-id="aeadb-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aeadb-109">DESCRIPTION</span></span>

<span data-ttu-id="aeadb-110">Das- `Test-Path` Cmdlet bestimmt, ob alle Elemente des Pfads vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="aeadb-110">The `Test-Path` cmdlet determines whether all elements of the path exist.</span></span> <span data-ttu-id="aeadb-111">Er gibt zurück, `$True` Wenn alle Elemente vorhanden sind und ggf `$False` . fehlende vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="aeadb-111">It returns `$True` if all elements exist and `$False` if any are missing.</span></span> <span data-ttu-id="aeadb-112">Es kann auch festzustellen, ob die Pfad Syntax gültig ist und ob der Pfad zu einem Container oder einem Terminal oder einem Blatt Element führt.</span><span class="sxs-lookup"><span data-stu-id="aeadb-112">It can also tell whether the path syntax is valid and whether the path leads to a container or a terminal or leaf element.</span></span> <span data-ttu-id="aeadb-113">Wenn `Path` Leerzeichen ist, `$False` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aeadb-113">If the `Path` is whitespace, then `$False` is returned.</span></span> <span data-ttu-id="aeadb-114">Wenn `Path` eine leere Zeichenfolge, ein `$null` Array oder ein `$null` leeres Array ist, wird ein Fehler ohne Abbruch zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aeadb-114">If the `Path` is an empty string, `$null`, array of `$null` or empty array, a non-terminating error is returned.</span></span>

## <span data-ttu-id="aeadb-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="aeadb-115">EXAMPLES</span></span>

### <span data-ttu-id="aeadb-116">Beispiel 1: Testen eines Pfads</span><span class="sxs-lookup"><span data-stu-id="aeadb-116">Example 1: Test a path</span></span>

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

<span data-ttu-id="aeadb-117">Mit diesem Befehl wird überprüft, ob alle Elemente im Pfad vorhanden sind, d. h. das Verzeichnis "C:", das Verzeichnis "Dokumente und Einstellungen" und das Verzeichnis "DavidC".</span><span class="sxs-lookup"><span data-stu-id="aeadb-117">This command checks whether all elements in the path exist, that is, the C: directory, the Documents and Settings directory, and the DavidC directory.</span></span> <span data-ttu-id="aeadb-118">Wenn eine solche fehlt, gibt das Cmdlet zurück `$False` .</span><span class="sxs-lookup"><span data-stu-id="aeadb-118">If any are missing, the cmdlet returns `$False`.</span></span>
<span data-ttu-id="aeadb-119">Andernfalls wird `$True`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aeadb-119">Otherwise, it returns `$True`.</span></span>

### <span data-ttu-id="aeadb-120">Beispiel 2: Testen des Pfads eines Profils</span><span class="sxs-lookup"><span data-stu-id="aeadb-120">Example 2: Test the path of a profile</span></span>

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

<span data-ttu-id="aeadb-121">Mit diesen Befehlen wird der Pfad des PowerShell-Profils getestet.</span><span class="sxs-lookup"><span data-stu-id="aeadb-121">These commands test the path of the PowerShell profile.</span></span>

<span data-ttu-id="aeadb-122">Mit dem ersten Befehl wird bestimmt, ob alle Elemente im Pfad vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="aeadb-122">The first command determines whether all elements in the path exist.</span></span> <span data-ttu-id="aeadb-123">Mit dem zweiten Befehl wird bestimmt, ob die Syntax des Pfads gültig ist.</span><span class="sxs-lookup"><span data-stu-id="aeadb-123">The second command determines whether the syntax of the path is correct.</span></span> <span data-ttu-id="aeadb-124">In diesem Fall ist der Pfad `$False` , aber die Syntax ist richtig `$True` .</span><span class="sxs-lookup"><span data-stu-id="aeadb-124">In this case, the path is `$False`, but the syntax is correct `$True`.</span></span> <span data-ttu-id="aeadb-125">Diese Befehle verwenden `$profile` , die automatische Variable, die auf den Speicherort für das Profil zeigt, selbst wenn das Profil nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="aeadb-125">These commands use `$profile`, the automatic variable that points to the location for the profile, even if the profile does not exist.</span></span>

<span data-ttu-id="aeadb-126">Weitere Informationen zu automatischen Variablen finden Sie unter %%amp;quot;about_Automatic_Variables%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="aeadb-126">For more information about automatic variables, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="aeadb-127">Beispiel 3: überprüfen, ob neben einem angegebenen Typ Dateien vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="aeadb-127">Example 3: Check whether there are any files besides a specified type</span></span>

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

<span data-ttu-id="aeadb-128">Mit diesem Befehl wird überprüft, ob im Verzeichnis der kommerziellen Gebäude andere Dateien als DWG-Dateien vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="aeadb-128">This command checks whether there are any files in the Commercial Buildings directory other than .dwg files.</span></span>

<span data-ttu-id="aeadb-129">Der Befehl verwendet den **path** -Parameter, um den Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="aeadb-129">The command uses the **Path** parameter to specify the path.</span></span> <span data-ttu-id="aeadb-130">Da der Pfad ein Leerzeichen enthält, wird der Pfad in Anführungszeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="aeadb-130">Because the path includes a space, the path is enclosed in quotation marks.</span></span> <span data-ttu-id="aeadb-131">Das Sternchen am Ende des Pfads gibt den Inhalt des Verzeichnisses %%amp;quot;Commercial Building%%amp;quot; an.</span><span class="sxs-lookup"><span data-stu-id="aeadb-131">The asterisk at the end of the path indicates the contents of the Commercial Building directory.</span></span> <span data-ttu-id="aeadb-132">Bei langen Pfaden, wie z. b. diesem, geben Sie die ersten Buchstaben des Pfads ein, und verwenden Sie dann die Tab-Taste, um den Pfad abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="aeadb-132">With long paths, such as this one, type the first few letters of the path, and then use the TAB key to complete the path.</span></span>

<span data-ttu-id="aeadb-133">Der Befehl gibt den **Exclude** -Parameter zum Angeben von Dateien an, die in der Auswertung ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="aeadb-133">The command specifies the **Exclude** parameter to specify files that will be omitted from the evaluation.</span></span>

<span data-ttu-id="aeadb-134">Da das Verzeichnis in diesem Fall nur DWG-Dateien enthält, lautet das Ergebnis `$False` .</span><span class="sxs-lookup"><span data-stu-id="aeadb-134">In this case, because the directory contains only .dwg files, the result is `$False`.</span></span>

### <span data-ttu-id="aeadb-135">Beispiel 4: Überprüfen auf eine Datei</span><span class="sxs-lookup"><span data-stu-id="aeadb-135">Example 4: Check for a file</span></span>

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

<span data-ttu-id="aeadb-136">Mit diesem Befehl wird überprüft, ob der in der Variablen gespeicherte Pfad `$profile` zu einer Datei führt.</span><span class="sxs-lookup"><span data-stu-id="aeadb-136">This command checks whether the path stored in the `$profile` variable leads to a file.</span></span> <span data-ttu-id="aeadb-137">In diesem Fall `.ps1` gibt das Cmdlet zurück, da es sich bei dem PowerShell-Profil um eine Datei handelt `$True` .</span><span class="sxs-lookup"><span data-stu-id="aeadb-137">In this case, because the PowerShell profile is a `.ps1` file, the cmdlet returns `$True`.</span></span>

### <span data-ttu-id="aeadb-138">Beispiel 5: Überprüfen der Pfade in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="aeadb-138">Example 5: Check paths in the Registry</span></span>

<span data-ttu-id="aeadb-139">Diese Befehle werden `Test-Path` mit dem PowerShell-Registrierungs Anbieter verwendet.</span><span class="sxs-lookup"><span data-stu-id="aeadb-139">These commands use `Test-Path` with the PowerShell registry provider.</span></span>

<span data-ttu-id="aeadb-140">Der erste Befehl testet, ob der Registrierungs Pfad des **Microsoft. PowerShell** -Registrierungsschlüssels auf dem System richtig ist.</span><span class="sxs-lookup"><span data-stu-id="aeadb-140">The first command tests whether the registry path of the **Microsoft.PowerShell** registry key is correct on the system.</span></span> <span data-ttu-id="aeadb-141">Wenn PowerShell ordnungsgemäß installiert ist, wird vom Cmdlet zurückgegeben `$True` .</span><span class="sxs-lookup"><span data-stu-id="aeadb-141">If PowerShell is installed correctly, the cmdlet returns `$True`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aeadb-142">`Test-Path` funktioniert nicht mit allen PowerShell-Anbietern ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="aeadb-142">`Test-Path` does not work correctly with all PowerShell providers.</span></span> <span data-ttu-id="aeadb-143">Beispielsweise können Sie verwenden, `Test-Path` um den Pfad eines Registrierungsschlüssels zu testen, aber wenn Sie ihn zum Testen des Pfads eines Registrierungs Eintrags verwenden, wird immer zurückgegeben, `$False` auch wenn der Registrierungs Eintrag vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="aeadb-143">For example, you can use `Test-Path` to test the path of a registry key, but if you use it to test the path of a registry entry, it always returns `$False`, even if the registry entry is present.</span></span>

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

### <span data-ttu-id="aeadb-144">Beispiel 6: testen, ob eine Datei neuer als ein bestimmtes Datum ist</span><span class="sxs-lookup"><span data-stu-id="aeadb-144">Example 6: Test if a file is newer than a specified date</span></span>

<span data-ttu-id="aeadb-145">Dieser Befehl verwendet den dynamischen Parameter " **newerthan** ", um zu bestimmen, ob die Datei "PowerShell.exe" auf dem Computer neuer als "Juli 13, 2009" ist.</span><span class="sxs-lookup"><span data-stu-id="aeadb-145">This command uses the **NewerThan** dynamic parameter to determine whether the "PowerShell.exe" file on the computer is newer than "July 13, 2009".</span></span>

<span data-ttu-id="aeadb-146">Der Parameter NewerThan funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="aeadb-146">The NewerThan parameter works only in file system drives.</span></span>

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### <span data-ttu-id="aeadb-147">Beispiel 7: Testen eines Pfads mit NULL als Wert</span><span class="sxs-lookup"><span data-stu-id="aeadb-147">Example 7: Test a path with null as the value</span></span>

<span data-ttu-id="aeadb-148">Der für `null` `null` ein Array oder ein leeres Array zurückgegebene Fehler ist ein Fehler ohne Abbruch.</span><span class="sxs-lookup"><span data-stu-id="aeadb-148">The error returned for `null`, array of `null` or empty array is a non-terminating error.</span></span> <span data-ttu-id="aeadb-149">Dies kann mithilfe von unterdrückt werden `-ErrorAction SilentlyContinue` .</span><span class="sxs-lookup"><span data-stu-id="aeadb-149">It can be suppress by using `-ErrorAction SilentlyContinue`.</span></span> <span data-ttu-id="aeadb-150">Im folgenden Beispiel werden alle Fälle gezeigt, die den Fehler zurückgeben `NullPathNotPermitted` .</span><span class="sxs-lookup"><span data-stu-id="aeadb-150">The following example shows all cases which return the `NullPathNotPermitted` error.</span></span>

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

### <span data-ttu-id="aeadb-151">Beispiel 8: Testen eines Pfads mit Leerraum als Wert</span><span class="sxs-lookup"><span data-stu-id="aeadb-151">Example 8: Test a path with whitespace as the value</span></span>

<span data-ttu-id="aeadb-152">Wenn eine Leerzeichen-Zeichenfolge für den-Parameter bereitgestellt wird `-Path` , wird **true** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aeadb-152">When a whitespace string is provided for the the `-Path` parameter, it returns **True** .</span></span> <span data-ttu-id="aeadb-153">Wenn eine leere Zeichenfolge bereitgestellt wird, `Test-Path` gibt einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="aeadb-153">When an empty string is provided, `Test-Path` returns an error.</span></span> <span data-ttu-id="aeadb-154">Das folgende Beispiel zeigt Leerräume und eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="aeadb-154">The following example shows whitespace and empty string.</span></span>

```powershell
Test-Path ' '
Test-Path ''
```

```Output
True
Test-Path : Cannot bind argument to parameter 'Path' because it is an empty string.
At line:1 char:11
+ Test-Path ''
+           ~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorEmptyStringNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

## <span data-ttu-id="aeadb-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aeadb-155">PARAMETERS</span></span>

### <span data-ttu-id="aeadb-156">-Credential</span><span class="sxs-lookup"><span data-stu-id="aeadb-156">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="aeadb-157">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aeadb-157">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="aeadb-158">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="aeadb-158">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="aeadb-159">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="aeadb-159">-Exclude</span></span>

<span data-ttu-id="aeadb-160">Gibt die Elemente an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="aeadb-160">Specifies items that this cmdlet omits.</span></span> <span data-ttu-id="aeadb-161">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="aeadb-161">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="aeadb-162">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="aeadb-162">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="aeadb-163">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="aeadb-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="aeadb-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="aeadb-164">-Filter</span></span>

<span data-ttu-id="aeadb-165">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="aeadb-165">Specifies a filter in the format or language of the provider.</span></span> <span data-ttu-id="aeadb-166">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="aeadb-166">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="aeadb-167">Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="aeadb-167">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="aeadb-168">Filter sind effizienter als andere Parameter, da Sie vom Anbieter beim Abrufen der Objekte angewendet werden, anstatt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="aeadb-168">Filters are more efficient than other parameters, because the provider applies them when it retrieves the objects instead of having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="aeadb-169">-Include</span><span class="sxs-lookup"><span data-stu-id="aeadb-169">-Include</span></span>

<span data-ttu-id="aeadb-170">Gibt die Pfade an, die von diesem Cmdlet getestet werden.</span><span class="sxs-lookup"><span data-stu-id="aeadb-170">Specifies paths that this cmdlet tests.</span></span> <span data-ttu-id="aeadb-171">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="aeadb-171">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="aeadb-172">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="aeadb-172">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="aeadb-173">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="aeadb-173">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="aeadb-174">-IsValid</span><span class="sxs-lookup"><span data-stu-id="aeadb-174">-IsValid</span></span>

<span data-ttu-id="aeadb-175">Gibt an, dass dieses Cmdlet die Syntax des Pfads testet, unabhängig davon, ob die Elemente des Pfads vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="aeadb-175">Indicates that this cmdlet tests the syntax of the path, regardless of whether the elements of the path exist.</span></span> <span data-ttu-id="aeadb-176">Dieses Cmdlet gibt zurück, `$True` Wenn die Pfad Syntax gültig ist, `$False` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="aeadb-176">This cmdlet returns `$True` if the path syntax is valid and `$False` if it is not.</span></span>

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

### <span data-ttu-id="aeadb-177">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="aeadb-177">-LiteralPath</span></span>

<span data-ttu-id="aeadb-178">Gibt den zu testenden Pfad an.</span><span class="sxs-lookup"><span data-stu-id="aeadb-178">Specifies a path to be tested.</span></span> <span data-ttu-id="aeadb-179">Im Gegensatz zu **Path** wird der Wert des **LiteralPath** -Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="aeadb-179">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="aeadb-180">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="aeadb-180">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="aeadb-181">Wenn der Pfad Zeichen enthält, die von PowerShell als Escapesequenzen interpretiert werden können, müssen Sie den Pfad in einfache Anführungszeichen einschließen, damit diese nicht interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="aeadb-181">If the path includes characters that could be interpreted by PowerShell as escape sequences, you must enclose the path in single quote so that they won't be interpreted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="aeadb-182">-"-Nals"</span><span class="sxs-lookup"><span data-stu-id="aeadb-182">-NewerThan</span></span>

<span data-ttu-id="aeadb-183">Geben Sie eine Uhrzeit als **DateTime** -Objekt an.</span><span class="sxs-lookup"><span data-stu-id="aeadb-183">Specify a time as a **DateTime** object.</span></span>

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

### <span data-ttu-id="aeadb-184">-Olderthan</span><span class="sxs-lookup"><span data-stu-id="aeadb-184">-OlderThan</span></span>

<span data-ttu-id="aeadb-185">Geben Sie eine Uhrzeit als **DateTime** -Objekt an.</span><span class="sxs-lookup"><span data-stu-id="aeadb-185">Specify a time as a **DateTime** object.</span></span>

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

### <span data-ttu-id="aeadb-186">-Path</span><span class="sxs-lookup"><span data-stu-id="aeadb-186">-Path</span></span>

<span data-ttu-id="aeadb-187">Gibt den zu testenden Pfad an.</span><span class="sxs-lookup"><span data-stu-id="aeadb-187">Specifies a path to be tested.</span></span> <span data-ttu-id="aeadb-188">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="aeadb-188">Wildcard characters are permitted.</span></span> <span data-ttu-id="aeadb-189">Wenn der Pfad Leerzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="aeadb-189">If the path includes spaces, enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="aeadb-190">-PathType</span><span class="sxs-lookup"><span data-stu-id="aeadb-190">-PathType</span></span>

<span data-ttu-id="aeadb-191">Gibt den Typ des letzten Elements im Pfad an.</span><span class="sxs-lookup"><span data-stu-id="aeadb-191">Specifies the type of the final element in the path.</span></span> <span data-ttu-id="aeadb-192">Dieses Cmdlet gibt zurück, `$True` Wenn das Element den angegebenen Typ hat und `$False` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="aeadb-192">This cmdlet returns `$True` if the element is of the specified type and `$False` if it is not.</span></span> <span data-ttu-id="aeadb-193">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="aeadb-193">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="aeadb-194">Container.</span><span class="sxs-lookup"><span data-stu-id="aeadb-194">Container.</span></span>
  <span data-ttu-id="aeadb-195">Ein Element, das andere Elemente enthält, beispielsweise ein Verzeichnis oder einen Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="aeadb-195">An element that contains other elements, such as a directory or registry key.</span></span>
- <span data-ttu-id="aeadb-196">Dach.</span><span class="sxs-lookup"><span data-stu-id="aeadb-196">Leaf.</span></span>
  <span data-ttu-id="aeadb-197">Ein Element, das keine anderen Elemente enthält, beispielsweise eine Datei.</span><span class="sxs-lookup"><span data-stu-id="aeadb-197">An element that does not contain other elements, such as a file.</span></span>
- <span data-ttu-id="aeadb-198">Irgendeiner.</span><span class="sxs-lookup"><span data-stu-id="aeadb-198">Any.</span></span>
  <span data-ttu-id="aeadb-199">Ein Container- oder Leaf-Element.</span><span class="sxs-lookup"><span data-stu-id="aeadb-199">Either a container or a leaf.</span></span>

<span data-ttu-id="aeadb-200">Gibt an, ob das letzte Element im Pfad einen bestimmten Typ aufweist.</span><span class="sxs-lookup"><span data-stu-id="aeadb-200">Tells whether the final element in the path is of a particular type.</span></span>

> [!CAUTION]
>
> <span data-ttu-id="aeadb-201">Bis zur PowerShell-Version 6.1.2, wenn die Schalter **IsValid** und **PathType** zusammen angegeben werden, `Test-Path` ignoriert das Cmdlet den **PathType** -Switch und überprüft nur den syntaktischen Pfad, ohne den Pfadtyp zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="aeadb-201">Up to PowerShell version 6.1.2, when the **IsValid** and **PathType** switches are specified together, the `Test-Path` cmdlet ignores the **PathType** switch and only validates the syntactic path without validating the path type.</span></span>
>
> <span data-ttu-id="aeadb-202">Gemäß der [Problem #8607](https://github.com/PowerShell/PowerShell/issues/8607)kann das Beheben dieses Verhaltens eine Breaking Change in einer zukünftigen Version sein, bei der die " **IsValid** "-und " **PathType** "-Schalter zu separaten Parametersätzen gehören und somit nicht gleichzeitig verwendet werden können, um diese Verwirrung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="aeadb-202">According to [issue #8607](https://github.com/PowerShell/PowerShell/issues/8607), fixing this behavior may be a breaking change in a future version, where the **IsValid** and **PathType** switches belong to separate parameter sets, and thus, cannot be used together avoiding this confusion.</span></span>

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

### <span data-ttu-id="aeadb-203">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="aeadb-203">-UseTransaction</span></span>

<span data-ttu-id="aeadb-204">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="aeadb-204">Includes the command in the active transaction.</span></span> <span data-ttu-id="aeadb-205">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aeadb-205">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="aeadb-206">Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)</span><span class="sxs-lookup"><span data-stu-id="aeadb-206">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aeadb-207">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aeadb-207">CommonParameters</span></span>

<span data-ttu-id="aeadb-208">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="aeadb-208">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="aeadb-209">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="aeadb-209">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="aeadb-210">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="aeadb-210">INPUTS</span></span>

### <span data-ttu-id="aeadb-211">System.String</span><span class="sxs-lookup"><span data-stu-id="aeadb-211">System.String</span></span>

<span data-ttu-id="aeadb-212">Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="aeadb-212">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="aeadb-213">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="aeadb-213">OUTPUTS</span></span>

### <span data-ttu-id="aeadb-214">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="aeadb-214">System.Boolean</span></span>

<span data-ttu-id="aeadb-215">Mit dem-Cmdlet wird ein **boolescher** Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aeadb-215">The cmdlet returns a **Boolean** value.</span></span>

## <span data-ttu-id="aeadb-216">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="aeadb-216">NOTES</span></span>

<span data-ttu-id="aeadb-217">Die Cmdlets, die das **Pfad** -Substantiv enthalten (die **path** -Cmdlets), funktionieren mit Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="aeadb-217">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="aeadb-218">Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="aeadb-218">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="aeadb-219">Verwenden Sie Sie wie **dirname** , **normpath** , **realpath** , **Join** oder andere Pfad Manipulatoren.</span><span class="sxs-lookup"><span data-stu-id="aeadb-219">Use them as you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="aeadb-220">Der `Test-Path` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="aeadb-220">The `Test-Path` is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="aeadb-221">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="aeadb-221">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="aeadb-222">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="aeadb-222">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="aeadb-223">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="aeadb-223">RELATED LINKS</span></span>

[<span data-ttu-id="aeadb-224">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="aeadb-224">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="aeadb-225">Join-Path</span><span class="sxs-lookup"><span data-stu-id="aeadb-225">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="aeadb-226">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="aeadb-226">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="aeadb-227">Split-Path</span><span class="sxs-lookup"><span data-stu-id="aeadb-227">Split-Path</span></span>](Split-Path.md)
