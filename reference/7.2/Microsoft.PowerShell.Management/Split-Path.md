---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: e2498c02d42123e207b49e622654d3cb881fc0fc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601729"
---
# <span data-ttu-id="08210-102">Split-Path</span><span class="sxs-lookup"><span data-stu-id="08210-102">Split-Path</span></span>

## <span data-ttu-id="08210-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="08210-103">SYNOPSIS</span></span>
<span data-ttu-id="08210-104">Gibt den angegebenen Teil eines Pfads zurück.</span><span class="sxs-lookup"><span data-stu-id="08210-104">Returns the specified part of a path.</span></span>

## <span data-ttu-id="08210-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08210-105">SYNTAX</span></span>

### <span data-ttu-id="08210-106">Parametriset (Standard)</span><span class="sxs-lookup"><span data-stu-id="08210-106">ParentSet (Default)</span></span>

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="08210-107">Blätter Satz</span><span class="sxs-lookup"><span data-stu-id="08210-107">LeafSet</span></span>

```
Split-Path [-Path] <String[]> -Leaf [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="08210-108">Leafbaseset</span><span class="sxs-lookup"><span data-stu-id="08210-108">LeafBaseSet</span></span>

```
Split-Path [-Path] <String[]> -LeafBase [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="08210-109">ExtensionSet</span><span class="sxs-lookup"><span data-stu-id="08210-109">ExtensionSet</span></span>

```
Split-Path [-Path] <String[]> -Extension [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="08210-110">Qualifierset</span><span class="sxs-lookup"><span data-stu-id="08210-110">QualifierSet</span></span>

```
Split-Path [-Path] <String[]> -Qualifier [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="08210-111">Noqualifierset</span><span class="sxs-lookup"><span data-stu-id="08210-111">NoQualifierSet</span></span>

```
Split-Path [-Path] <String[]> -NoQualifier [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="08210-112">Isabsoluteset</span><span class="sxs-lookup"><span data-stu-id="08210-112">IsAbsoluteSet</span></span>

```
Split-Path [-Path] <String[]> [-Resolve] -IsAbsolute [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="08210-113">Literalpathset</span><span class="sxs-lookup"><span data-stu-id="08210-113">LiteralPathSet</span></span>

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="08210-114">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08210-114">DESCRIPTION</span></span>

<span data-ttu-id="08210-115">Das- `Split-Path` Cmdlet gibt nur den angegebenen Teil eines Pfads zurück, z. b. den übergeordneten Ordner, einen Unterordner oder einen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="08210-115">The `Split-Path` cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a file name.</span></span> <span data-ttu-id="08210-116">Außerdem können Elemente abgerufen werden, auf die von dem geteilten Pfad verwiesen wird, und es kann angegeben werden, ob es sich um einen relativen oder absoluten Pfad handelt.</span><span class="sxs-lookup"><span data-stu-id="08210-116">It can also get items that are referenced by the split path and tell whether the path is relative or absolute.</span></span>

<span data-ttu-id="08210-117">Sie können mit diesem Cmdlet nur einen ausgewählten Teil eines Pfads abrufen oder senden.</span><span class="sxs-lookup"><span data-stu-id="08210-117">You can use this cmdlet to get or submit only a selected part of a path.</span></span>

## <span data-ttu-id="08210-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="08210-118">EXAMPLES</span></span>

### <span data-ttu-id="08210-119">Beispiel 1: Holen Sie sich den Qualifizierer eines Pfads.</span><span class="sxs-lookup"><span data-stu-id="08210-119">Example 1: Get the qualifier of a path</span></span>

```powershell
Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
```

```Output
HKCU:
```

<span data-ttu-id="08210-120">Mit diesem Befehl wird nur der Qualifizierer des Pfads zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="08210-120">This command returns only the qualifier of the path.</span></span> <span data-ttu-id="08210-121">Der Qualifizierer ist das Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="08210-121">The qualifier is the drive.</span></span>

### <span data-ttu-id="08210-122">Beispiel 2: Anzeigen von Dateinamen</span><span class="sxs-lookup"><span data-stu-id="08210-122">Example 2: Display file names</span></span>

```powershell
Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
```

```Output
Pass1.log
Pass2.log
...
```

<span data-ttu-id="08210-123">Mit diesem Befehl werden die Dateien angezeigt, auf die vom geteilten Pfad verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="08210-123">This command displays the files that are referenced by the split path.</span></span> <span data-ttu-id="08210-124">Da dieser Pfad auf das letzte Element aufgeteilt ist, das auch als Blatt bezeichnet wird, zeigt der Befehl nur die Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="08210-124">Because this path is split to the last item, also known as the leaf, the command displays only the file names.</span></span>

<span data-ttu-id="08210-125">Der **Resolve** -Parameter weist `Split-Path` an, die Elemente anzuzeigen, auf die der geteilte Pfad verweist, anstatt den geteilten Pfad anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="08210-125">The **Resolve** parameter tells `Split-Path` to display the items that the split path references, instead of displaying the split path.</span></span>

<span data-ttu-id="08210-126">Wie alle `Split-Path` Befehle gibt dieser Befehl Zeichen folgen zurück.</span><span class="sxs-lookup"><span data-stu-id="08210-126">Like all `Split-Path` commands, this command returns strings.</span></span> <span data-ttu-id="08210-127">Es werden keine **FileInfo** -Objekte zurückgegeben, die die Dateien darstellen.</span><span class="sxs-lookup"><span data-stu-id="08210-127">It does not return **FileInfo** objects that represent the files.</span></span>

### <span data-ttu-id="08210-128">Beispiel 3: Get the parent Container</span><span class="sxs-lookup"><span data-stu-id="08210-128">Example 3: Get the parent container</span></span>

```powershell
Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
```

```Output
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

<span data-ttu-id="08210-129">Mit diesem Befehl werden nur die übergeordneten Container des Pfads zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="08210-129">This command returns only the parent containers of the path.</span></span> <span data-ttu-id="08210-130">Da keine Parameter zum Angeben der Teilung enthalten sind, `Split-Path` verwendet den Standard **Wert für** den geteilten Speicherort, der übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="08210-130">Because it does not include any parameters to specify the split, `Split-Path` uses the split location default, which is **Parent**.</span></span>

### <span data-ttu-id="08210-131">Beispiel 4: bestimmt, ob ein Pfad absolut ist</span><span class="sxs-lookup"><span data-stu-id="08210-131">Example 4: Determines whether a path is absolute</span></span>

```powershell
Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
```

```Output
False
```

<span data-ttu-id="08210-132">Mit diesem Befehl wird bestimmt, ob der Pfad relativ oder absolut ist.</span><span class="sxs-lookup"><span data-stu-id="08210-132">This command determines whether the path is relative or absolute.</span></span> <span data-ttu-id="08210-133">In diesem Fall wird zurückgegeben, da der Pfad relativ zum aktuellen Ordner ist, der durch einen Punkt ( `.` ) dargestellt wird `$False` .</span><span class="sxs-lookup"><span data-stu-id="08210-133">In this case, because the path is relative to the current folder, which is represented by a dot (`.`), it returns `$False`.</span></span>

### <span data-ttu-id="08210-134">Beispiel 5: Ändern des Speicher Orts in einen angegebenen Pfad</span><span class="sxs-lookup"><span data-stu-id="08210-134">Example 5: Change location to a specified path</span></span>

```powershell
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

<span data-ttu-id="08210-135">Mit diesem Befehl wird der Speicherort in den Ordner geändert, der das PowerShell-Profil enthält.</span><span class="sxs-lookup"><span data-stu-id="08210-135">This command changes your location to the folder that contains the PowerShell profile.</span></span>

<span data-ttu-id="08210-136">Der-Befehl in Klammern verwendet `Split-Path` , um nur das übergeordnete Element des Pfads zurückzugeben, der in der integrierten Variablen gespeichert ist `$Profile` .</span><span class="sxs-lookup"><span data-stu-id="08210-136">The command in parentheses uses `Split-Path` to return only the parent of the path stored in the built-in `$Profile` variable.</span></span> <span data-ttu-id="08210-137">Der **Parent** -Parameter ist der standardmäßige Split Location-Parameter.</span><span class="sxs-lookup"><span data-stu-id="08210-137">The **Parent** parameter is the default split location parameter.</span></span>
<span data-ttu-id="08210-138">Aus diesem Grund können Sie Sie im Befehl weglassen.</span><span class="sxs-lookup"><span data-stu-id="08210-138">Therefore, you can omit it from the command.</span></span> <span data-ttu-id="08210-139">Die Klammern leiten PowerShell an, den Befehl zuerst auszuführen.</span><span class="sxs-lookup"><span data-stu-id="08210-139">The parentheses direct PowerShell to run the command first.</span></span> <span data-ttu-id="08210-140">Dies ist eine hilfreiche Möglichkeit, um zu einem Ordner zu wechseln, der über einen langen Pfadnamen verfügt.</span><span class="sxs-lookup"><span data-stu-id="08210-140">This is a useful way to move to a folder that has a long path name.</span></span>

### <span data-ttu-id="08210-141">Beispiel 6: Aufteilen eines Pfads mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="08210-141">Example 6: Split a path by using the pipeline</span></span>

```powershell
'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
```

```Output
C:\Documents and Settings\User01\My Documents
```

<span data-ttu-id="08210-142">Dieser Befehl verwendet einen Pipeline Operator ( `|` ), um einen Pfad an zu senden `Split-Path` .</span><span class="sxs-lookup"><span data-stu-id="08210-142">This command uses a pipeline operator (`|`) to send a path to `Split-Path`.</span></span> <span data-ttu-id="08210-143">Der Pfad ist in Anführungszeichen eingeschlossen, um anzugeben, dass es sich um ein einzelnes Token handelt.</span><span class="sxs-lookup"><span data-stu-id="08210-143">The path is enclosed in quotation marks to indicate that it is a single token.</span></span>

## <span data-ttu-id="08210-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08210-144">PARAMETERS</span></span>

### <span data-ttu-id="08210-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="08210-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="08210-146">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08210-146">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="08210-147">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="08210-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="08210-148">-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="08210-148">-Extension</span></span>

<span data-ttu-id="08210-149">Gibt an, dass dieses Cmdlet nur die Erweiterung des Blatts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="08210-149">Indicates that this cmdlet returns only the extension of the leaf.</span></span> <span data-ttu-id="08210-150">Im Pfad wird beispielsweise `C:\Test\Logs\Pass1.log` nur zurückgegeben `.log` .</span><span class="sxs-lookup"><span data-stu-id="08210-150">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `.log`.</span></span>

<span data-ttu-id="08210-151">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="08210-151">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ExtensionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="08210-152">-IsAbsolute</span><span class="sxs-lookup"><span data-stu-id="08210-152">-IsAbsolute</span></span>

<span data-ttu-id="08210-153">Gibt an, dass dieses Cmdlet $true zurückgibt, wenn der Pfad absolut ist, und $false, wenn er relativ ist.</span><span class="sxs-lookup"><span data-stu-id="08210-153">Indicates that this cmdlet returns $True if the path is absolute and $False if it is relative.</span></span> <span data-ttu-id="08210-154">Ein absoluter Pfad weist eine Länge größer als 0 (null) auf und verwendet keinen Punkt ( `.` ), um den aktuellen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="08210-154">An absolute path has a length greater than zero and does not use a dot (`.`) to indicate the current path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08210-155">-Blatt</span><span class="sxs-lookup"><span data-stu-id="08210-155">-Leaf</span></span>

<span data-ttu-id="08210-156">Gibt an, dass dieses Cmdlet nur das letzte Element bzw. den letzten Container im Pfad zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="08210-156">Indicates that this cmdlet returns only the last item or container in the path.</span></span> <span data-ttu-id="08210-157">Beispielsweise wird im Pfad `C:\Test\Logs\Pass1.log` nur Pass1. log zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="08210-157">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="08210-158">-Leafbase</span><span class="sxs-lookup"><span data-stu-id="08210-158">-LeafBase</span></span>

<span data-ttu-id="08210-159">Gibt an, dass dieses Cmdlet nur den Basis Namen des Blatts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="08210-159">Indicates that this cmdlet returns only base name of the leaf.</span></span> <span data-ttu-id="08210-160">Im Pfad wird beispielsweise `C:\Test\Logs\Pass1.log` nur zurückgegeben `Pass1` .</span><span class="sxs-lookup"><span data-stu-id="08210-160">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `Pass1`.</span></span>

<span data-ttu-id="08210-161">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="08210-161">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafBaseSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="08210-162">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="08210-162">-LiteralPath</span></span>

<span data-ttu-id="08210-163">Gibt die zu teilenden Pfade an.</span><span class="sxs-lookup"><span data-stu-id="08210-163">Specifies the paths to be split.</span></span> <span data-ttu-id="08210-164">Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="08210-164">Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="08210-165">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="08210-165">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="08210-166">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="08210-166">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="08210-167">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="08210-167">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="08210-168">-Noqualifizierer</span><span class="sxs-lookup"><span data-stu-id="08210-168">-NoQualifier</span></span>

<span data-ttu-id="08210-169">Gibt an, dass dieses Cmdlet den Pfad ohne den Qualifizierer zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="08210-169">Indicates that this cmdlet returns the path without the qualifier.</span></span> <span data-ttu-id="08210-170">Für den Dateisystem-oder Registrierungs Anbieter ist der Qualifizierer das Laufwerk des Anbieter Pfads, z `C:` `HKCU:` . b. oder.</span><span class="sxs-lookup"><span data-stu-id="08210-170">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as `C:` or `HKCU:`.</span></span> <span data-ttu-id="08210-171">Im Pfad wird beispielsweise `C:\Test\Logs\Pass1.log` nur zurückgegeben `\Test\Logs\Pass1.log` .</span><span class="sxs-lookup"><span data-stu-id="08210-171">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `\Test\Logs\Pass1.log`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="08210-172">-Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="08210-172">-Parent</span></span>

<span data-ttu-id="08210-173">Gibt an, dass dieses Cmdlet nur die übergeordneten Container des Elements oder des Containers zurückgibt, der durch den Pfad angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="08210-173">Indicates that this cmdlet returns only the parent containers of the item or of the container specified by the path.</span></span> <span data-ttu-id="08210-174">Beispielsweise wird im Pfad `C:\Test\Logs\Pass1.log` zurückgegeben `C:\Test\Logs` .</span><span class="sxs-lookup"><span data-stu-id="08210-174">For example, in the path `C:\Test\Logs\Pass1.log`, it returns `C:\Test\Logs`.</span></span>
<span data-ttu-id="08210-175">Der **Parent** -Parameter ist der standardmäßige Split Location-Parameter.</span><span class="sxs-lookup"><span data-stu-id="08210-175">The **Parent** parameter is the default split location parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="08210-176">-Path</span><span class="sxs-lookup"><span data-stu-id="08210-176">-Path</span></span>

<span data-ttu-id="08210-177">Gibt die zu teilenden Pfade an.</span><span class="sxs-lookup"><span data-stu-id="08210-177">Specifies the paths to be split.</span></span> <span data-ttu-id="08210-178">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="08210-178">Wildcard characters are permitted.</span></span> <span data-ttu-id="08210-179">Wenn der Pfad Leerzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="08210-179">If the path includes spaces, enclose it in quotation marks.</span></span> <span data-ttu-id="08210-180">Sie können einen Pfad auch über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="08210-180">You can also pipe a path to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ParentSet, LeafSet, LeafBaseSet, ExtensionSet, QualifierSet, NoQualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="08210-181">-Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="08210-181">-Qualifier</span></span>

<span data-ttu-id="08210-182">Gibt an, dass dieses Cmdlet nur den Qualifizierer des angegebenen Pfads zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="08210-182">Indicates that this cmdlet returns only the qualifier of the specified path.</span></span> <span data-ttu-id="08210-183">Für den Dateisystem-oder Registrierungs Anbieter ist der Qualifizierer das Laufwerk des Anbieter Pfads, z `C:` `HKCU:` . b. oder.</span><span class="sxs-lookup"><span data-stu-id="08210-183">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as `C:` or `HKCU:`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="08210-184">-Auflösen</span><span class="sxs-lookup"><span data-stu-id="08210-184">-Resolve</span></span>

<span data-ttu-id="08210-185">Gibt an, dass dieses Cmdlet die Elemente anzeigt, auf die vom resultierenden geteilten Pfad verwiesen wird, anstatt die Pfad Elemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="08210-185">Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements.</span></span>

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

### <span data-ttu-id="08210-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="08210-186">CommonParameters</span></span>

<span data-ttu-id="08210-187">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="08210-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="08210-188">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="08210-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="08210-189">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="08210-189">INPUTS</span></span>

### <span data-ttu-id="08210-190">System.String</span><span class="sxs-lookup"><span data-stu-id="08210-190">System.String</span></span>

<span data-ttu-id="08210-191">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="08210-191">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="08210-192">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="08210-192">OUTPUTS</span></span>

### <span data-ttu-id="08210-193">System. String, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="08210-193">System.String, System.Boolean</span></span>

<span data-ttu-id="08210-194">`Split-Path` Gibt Text Zeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="08210-194">`Split-Path` returns text strings.</span></span> <span data-ttu-id="08210-195">Wenn Sie den **Resolve** -Parameter angeben, `Split-Path` gibt eine Zeichenfolge zurück, die den Speicherort der Elemente beschreibt. es werden keine Objekte zurückgegeben, die die Elemente darstellen, wie z. b. ein **FileInfo** -oder ein **RegistryKey** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="08210-195">When you specify the **Resolve** parameter, `Split-Path` returns a string that describes the location of the items; it does not return objects that represent the items, such as a **FileInfo** or **RegistryKey** object.</span></span>

<span data-ttu-id="08210-196">Wenn Sie den **IsAbsolute** -Parameter angeben, wird von `Split-Path` ein **boolescher** Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="08210-196">When you specify the **IsAbsolute** parameter, `Split-Path` returns a **Boolean** value.</span></span>

## <span data-ttu-id="08210-197">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="08210-197">NOTES</span></span>

- <span data-ttu-id="08210-198">Die Split Location-Parameter (**Qualifizierer**, über **geordnetes** Element, **Erweiterung**, **Blatt**, **leafbase** und **noqualifizierer**) sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="08210-198">The split location parameters (**Qualifier**, **Parent**, **Extension**, **Leaf**, **LeafBase**, and **NoQualifier**) are exclusive.</span></span> <span data-ttu-id="08210-199">In einem Befehl kann immer nur ein Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="08210-199">You can use only one in each command.</span></span>

- <span data-ttu-id="08210-200">Die Cmdlets, die das **Pfad** -Substantiv enthalten (die **path** -Cmdlets), funktionieren mit Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="08210-200">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="08210-201">Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="08210-201">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="08210-202">Verwenden Sie diese in der Weise, in der Sie **dirname**, **normpath**, **realpath**, **Join** oder andere Pfad Manipulatoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="08210-202">Use them in the way that you would use **Dirname**, **Normpath**, **Realpath**, **Join**, or other path manipulators.</span></span>

- <span data-ttu-id="08210-203">Sie können die **Pfad** -Cmdlets mit verschiedenen Anbietern verwenden.</span><span class="sxs-lookup"><span data-stu-id="08210-203">You can use the **Path** cmdlets together with several providers.</span></span> <span data-ttu-id="08210-204">Hierzu gehören das Dateisystem, die Registrierung und die Zertifikat Anbieter.</span><span class="sxs-lookup"><span data-stu-id="08210-204">These include the FileSystem, Registry, and Certificate providers.</span></span>

- <span data-ttu-id="08210-205">`Split-Path` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="08210-205">`Split-Path` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="08210-206">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="08210-206">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="08210-207">Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="08210-207">For more information, see about_Providers.</span></span>

## <span data-ttu-id="08210-208">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="08210-208">RELATED LINKS</span></span>

[<span data-ttu-id="08210-209">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="08210-209">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="08210-210">Join-Path</span><span class="sxs-lookup"><span data-stu-id="08210-210">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="08210-211">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="08210-211">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="08210-212">Test-Path</span><span class="sxs-lookup"><span data-stu-id="08210-212">Test-Path</span></span>](Test-Path.md)
