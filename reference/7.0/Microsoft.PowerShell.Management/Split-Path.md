---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: b0366e9d84826d84dcdc341a9e83e4ed7dc45059
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210612"
---
# <span data-ttu-id="9f662-103">Split-Path</span><span class="sxs-lookup"><span data-stu-id="9f662-103">Split-Path</span></span>

## <span data-ttu-id="9f662-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9f662-104">SYNOPSIS</span></span>
<span data-ttu-id="9f662-105">Gibt den angegebenen Teil eines Pfads zurück.</span><span class="sxs-lookup"><span data-stu-id="9f662-105">Returns the specified part of a path.</span></span>

## <span data-ttu-id="9f662-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f662-106">SYNTAX</span></span>

### <span data-ttu-id="9f662-107">Parametriset (Standard)</span><span class="sxs-lookup"><span data-stu-id="9f662-107">ParentSet (Default)</span></span>

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="9f662-108">Blätter Satz</span><span class="sxs-lookup"><span data-stu-id="9f662-108">LeafSet</span></span>

```
Split-Path [-Path] <String[]> [-Leaf] [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="9f662-109">Leafbaseset</span><span class="sxs-lookup"><span data-stu-id="9f662-109">LeafBaseSet</span></span>

```
Split-Path [-Path] <String[]> [-LeafBase] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="9f662-110">ExtensionSet</span><span class="sxs-lookup"><span data-stu-id="9f662-110">ExtensionSet</span></span>

```
Split-Path [-Path] <String[]> [-Extension] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="9f662-111">Qualifierset</span><span class="sxs-lookup"><span data-stu-id="9f662-111">QualifierSet</span></span>

```
Split-Path [-Path] <String[]> [[-Qualifier]] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="9f662-112">Noqualifierset</span><span class="sxs-lookup"><span data-stu-id="9f662-112">NoQualifierSet</span></span>

```
Split-Path [-Path] <String[]> [-NoQualifier] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="9f662-113">Isabsoluteset</span><span class="sxs-lookup"><span data-stu-id="9f662-113">IsAbsoluteSet</span></span>

```
Split-Path [-Path] <String[]> [-Resolve] [-IsAbsolute] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="9f662-114">Literalpathset</span><span class="sxs-lookup"><span data-stu-id="9f662-114">LiteralPathSet</span></span>

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="9f662-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9f662-115">DESCRIPTION</span></span>

<span data-ttu-id="9f662-116">Das **Split-Path-** Cmdlet gibt nur den angegebenen Teil eines Pfads zurück, z. b. den übergeordneten Ordner, einen Unterordner oder einen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="9f662-116">The **Split-Path** cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a file name.</span></span>
<span data-ttu-id="9f662-117">Außerdem können Elemente abgerufen werden, auf die von dem geteilten Pfad verwiesen wird, und es kann angegeben werden, ob es sich um einen relativen oder absoluten Pfad handelt.</span><span class="sxs-lookup"><span data-stu-id="9f662-117">It can also get items that are referenced by the split path and tell whether the path is relative or absolute.</span></span>

<span data-ttu-id="9f662-118">Sie können mit diesem Cmdlet nur einen ausgewählten Teil eines Pfads abrufen oder senden.</span><span class="sxs-lookup"><span data-stu-id="9f662-118">You can use this cmdlet to get or submit only a selected part of a path.</span></span>

## <span data-ttu-id="9f662-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9f662-119">EXAMPLES</span></span>

### <span data-ttu-id="9f662-120">Beispiel 1: Holen Sie sich den Qualifizierer eines Pfads.</span><span class="sxs-lookup"><span data-stu-id="9f662-120">Example 1: Get the qualifier of a path</span></span>

```
PS C:\> Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
HKCU:
```

<span data-ttu-id="9f662-121">Mit diesem Befehl wird nur der Qualifizierer des Pfads zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9f662-121">This command returns only the qualifier of the path.</span></span>
<span data-ttu-id="9f662-122">Der Qualifizierer ist das Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="9f662-122">The qualifier is the drive.</span></span>

### <span data-ttu-id="9f662-123">Beispiel 2: Anzeigen von Dateinamen</span><span class="sxs-lookup"><span data-stu-id="9f662-123">Example 2: Display file names</span></span>

```
PS C:\> Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
Pass1.log
Pass2.log
...
```

<span data-ttu-id="9f662-124">Mit diesem Befehl werden die Dateien angezeigt, auf die vom geteilten Pfad verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9f662-124">This command displays the files that are referenced by the split path.</span></span>
<span data-ttu-id="9f662-125">Da dieser Pfad auf das letzte Element aufgeteilt ist, das auch als Blatt bezeichnet wird, zeigt der Befehl nur die Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="9f662-125">Because this path is split to the last item, also known as the leaf, the command displays only the file names.</span></span>

<span data-ttu-id="9f662-126">Der *Resolve* -Parameter weist **Split-Path** an, die Elemente anzuzeigen, auf die der geteilte Pfad verweist, anstatt den geteilten Pfad anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f662-126">The *Resolve* parameter tells **Split-Path** to display the items that the split path references, instead of displaying the split path.</span></span>

<span data-ttu-id="9f662-127">Wie alle **Split-Path-** Befehle gibt dieser Befehl Zeichen folgen zurück.</span><span class="sxs-lookup"><span data-stu-id="9f662-127">Like all **Split-Path** commands, this command returns strings.</span></span>
<span data-ttu-id="9f662-128">Es werden keine **FileInfo** -Objekte zurückgegeben, die die Dateien darstellen.</span><span class="sxs-lookup"><span data-stu-id="9f662-128">It does not return **FileInfo** objects that represent the files.</span></span>

### <span data-ttu-id="9f662-129">Beispiel 3: Get the parent Container</span><span class="sxs-lookup"><span data-stu-id="9f662-129">Example 3: Get the parent container</span></span>

```
PS C:\> Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

<span data-ttu-id="9f662-130">Mit diesem Befehl werden nur die übergeordneten Container des Pfads zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9f662-130">This command returns only the parent containers of the path.</span></span>
<span data-ttu-id="9f662-131">Da keine Parameter zum Angeben der Teilung enthalten sind, verwendet **Split-Path** den Standard *Wert für Split* Location, der übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9f662-131">Because it does not include any parameters to specify the split, **Split-Path** uses the split location default, which is *Parent* .</span></span>

### <span data-ttu-id="9f662-132">Beispiel 4: bestimmt, ob ein Pfad absolut ist</span><span class="sxs-lookup"><span data-stu-id="9f662-132">Example 4: Determines whether a path is absolute</span></span>

```
PS C:\> Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
False
```

<span data-ttu-id="9f662-133">Mit diesem Befehl wird bestimmt, ob der Pfad relativ oder absolut ist.</span><span class="sxs-lookup"><span data-stu-id="9f662-133">This command determines whether the path is relative or absolute.</span></span>
<span data-ttu-id="9f662-134">In diesem Fall wird $false zurückgegeben, da der Pfad relativ zum aktuellen Ordner ist, der durch einen Punkt (.) dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9f662-134">In this case, because the path is relative to the current folder, which is represented by a dot (.), it returns $False.</span></span>

### <span data-ttu-id="9f662-135">Beispiel 5: Ändern des Speicher Orts in einen angegebenen Pfad</span><span class="sxs-lookup"><span data-stu-id="9f662-135">Example 5: Change location to a specified path</span></span>

```
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

<span data-ttu-id="9f662-136">Mit diesem Befehl wird der Speicherort in den Ordner geändert, der das PowerShell-Profil enthält.</span><span class="sxs-lookup"><span data-stu-id="9f662-136">This command changes your location to the folder that contains the PowerShell profile.</span></span>

<span data-ttu-id="9f662-137">Der-Befehl in Klammern verwendet **Split-Path** , um nur das übergeordnete Element des Pfads zurückzugeben, der in der integrierten $profile Variablen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="9f662-137">The command in parentheses uses **Split-Path** to return only the parent of the path stored in the built-in $Profile variable.</span></span>
<span data-ttu-id="9f662-138">Der *Parent* -Parameter ist der standardmäßige Split Location-Parameter.</span><span class="sxs-lookup"><span data-stu-id="9f662-138">The *Parent* parameter is the default split location parameter.</span></span>
<span data-ttu-id="9f662-139">Aus diesem Grund können Sie Sie im Befehl weglassen.</span><span class="sxs-lookup"><span data-stu-id="9f662-139">Therefore, you can omit it from the command.</span></span>
<span data-ttu-id="9f662-140">Die Klammern leiten PowerShell an, den Befehl zuerst auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9f662-140">The parentheses direct PowerShell to run the command first.</span></span>
<span data-ttu-id="9f662-141">Dies ist eine hilfreiche Möglichkeit, um zu einem Ordner zu wechseln, der über einen langen Pfadnamen verfügt.</span><span class="sxs-lookup"><span data-stu-id="9f662-141">This is a useful way to move to a folder that has a long path name.</span></span>

### <span data-ttu-id="9f662-142">Beispiel 6: Aufteilen eines Pfads mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="9f662-142">Example 6: Split a path by using the pipeline</span></span>

```
PS C:\> 'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
C:\Documents and Settings\User01\My Documents
```

<span data-ttu-id="9f662-143">Dieser Befehl verwendet einen Pipeline Operator (|), um einen Pfad an **Split-Path** zu senden.</span><span class="sxs-lookup"><span data-stu-id="9f662-143">This command uses a pipeline operator (|) to send a path to **Split-Path** .</span></span>
<span data-ttu-id="9f662-144">Der Pfad ist in Anführungszeichen eingeschlossen, um anzugeben, dass es sich um ein einzelnes Token handelt.</span><span class="sxs-lookup"><span data-stu-id="9f662-144">The path is enclosed in quotation marks to indicate that it is a single token.</span></span>

## <span data-ttu-id="9f662-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f662-145">PARAMETERS</span></span>

### <span data-ttu-id="9f662-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="9f662-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="9f662-147">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f662-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="9f662-148">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="9f662-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="9f662-149">-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="9f662-149">-Extension</span></span>

<span data-ttu-id="9f662-150">Gibt an, dass dieses Cmdlet nur die Erweiterung des Blatts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9f662-150">Indicates that this cmdlet returns only the extension of the leaf.</span></span>
<span data-ttu-id="9f662-151">Im Pfad wird beispielsweise `C:\Test\Logs\Pass1.log` nur zurückgegeben `.log` .</span><span class="sxs-lookup"><span data-stu-id="9f662-151">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `.log`.</span></span>

<span data-ttu-id="9f662-152">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9f662-152">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ExtensionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9f662-153">-IsAbsolute</span><span class="sxs-lookup"><span data-stu-id="9f662-153">-IsAbsolute</span></span>

<span data-ttu-id="9f662-154">Gibt an, dass dieses Cmdlet $true zurückgibt, wenn der Pfad absolut ist, und $false, wenn er relativ ist.</span><span class="sxs-lookup"><span data-stu-id="9f662-154">Indicates that this cmdlet returns $True if the path is absolute and $False if it is relative.</span></span>
<span data-ttu-id="9f662-155">Ein absoluter Pfad weist eine Länge größer als 0 (null) auf und verwendet keinen Punkt (.), um den aktuellen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9f662-155">An absolute path has a length greater than zero and does not use a dot (.) to indicate the current path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9f662-156">-Blatt</span><span class="sxs-lookup"><span data-stu-id="9f662-156">-Leaf</span></span>

<span data-ttu-id="9f662-157">Gibt an, dass dieses Cmdlet nur das letzte Element bzw. den letzten Container im Pfad zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9f662-157">Indicates that this cmdlet returns only the last item or container in the path.</span></span>
<span data-ttu-id="9f662-158">Beispielsweise wird im Pfad `C:\Test\Logs\Pass1.log` nur Pass1. log zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9f662-158">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9f662-159">-Leafbase</span><span class="sxs-lookup"><span data-stu-id="9f662-159">-LeafBase</span></span>

<span data-ttu-id="9f662-160">Gibt an, dass dieses Cmdlet nur den Basis Namen des Blatts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9f662-160">Indicates that this cmdlet returns only base name of the leaf.</span></span>
<span data-ttu-id="9f662-161">Im Pfad wird beispielsweise `C:\Test\Logs\Pass1.log` nur zurückgegeben `Pass1` .</span><span class="sxs-lookup"><span data-stu-id="9f662-161">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `Pass1`.</span></span>

<span data-ttu-id="9f662-162">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9f662-162">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafBaseSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9f662-163">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="9f662-163">-LiteralPath</span></span>

<span data-ttu-id="9f662-164">Gibt die zu teilenden Pfade an.</span><span class="sxs-lookup"><span data-stu-id="9f662-164">Specifies the paths to be split.</span></span>
<span data-ttu-id="9f662-165">Im Gegensatz zu *Path* wird der Wert von *LiteralPath* genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9f662-165">Unlike *Path* , the value of *LiteralPath* is used exactly as it is typed.</span></span>
<span data-ttu-id="9f662-166">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="9f662-166">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="9f662-167">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="9f662-167">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="9f662-168">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="9f662-168">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="9f662-169">-Noqualifizierer</span><span class="sxs-lookup"><span data-stu-id="9f662-169">-NoQualifier</span></span>

<span data-ttu-id="9f662-170">Gibt an, dass dieses Cmdlet den Pfad ohne den Qualifizierer zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9f662-170">Indicates that this cmdlet returns the path without the qualifier.</span></span>
<span data-ttu-id="9f662-171">Für den Dateisystem- bzw. Registrierungsanbieter ist der Qualifizierer das Laufwerk des Anbieterpfads, beispielsweise %%amp;quot;C:%%amp;quot; oder %%amp;quot;HKCU:%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="9f662-171">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>
<span data-ttu-id="9f662-172">Beispielsweise wird im Pfad `C:\Test\Logs\Pass1.log` nur "\test\logs\pass1.log" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9f662-172">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only \Test\Logs\Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9f662-173">-Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="9f662-173">-Parent</span></span>

<span data-ttu-id="9f662-174">Gibt an, dass dieses Cmdlet nur die übergeordneten Container des Elements oder des Containers zurückgibt, der durch den Pfad angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9f662-174">Indicates that this cmdlet returns only the parent containers of the item or of the container specified by the path.</span></span>
<span data-ttu-id="9f662-175">Beispielsweise gibt es im Pfad den Wert `C:\Test\Logs\Pass1.log` c:\test\logs.</span><span class="sxs-lookup"><span data-stu-id="9f662-175">For example, in the path `C:\Test\Logs\Pass1.log`, it returns C:\Test\Logs.</span></span>
<span data-ttu-id="9f662-176">Der *Parent* -Parameter ist der standardmäßige Split Location-Parameter.</span><span class="sxs-lookup"><span data-stu-id="9f662-176">The *Parent* parameter is the default split location parameter.</span></span>

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

### <span data-ttu-id="9f662-177">-Path</span><span class="sxs-lookup"><span data-stu-id="9f662-177">-Path</span></span>

<span data-ttu-id="9f662-178">Gibt die zu teilenden Pfade an.</span><span class="sxs-lookup"><span data-stu-id="9f662-178">Specifies the paths to be split.</span></span>
<span data-ttu-id="9f662-179">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9f662-179">Wildcard characters are permitted.</span></span>
<span data-ttu-id="9f662-180">Wenn der Pfad Leerzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="9f662-180">If the path includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="9f662-181">Sie können einen Pfad auch über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="9f662-181">You can also pipe a path to this cmdlet.</span></span>

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

### <span data-ttu-id="9f662-182">-Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="9f662-182">-Qualifier</span></span>

<span data-ttu-id="9f662-183">Gibt an, dass dieses Cmdlet nur den Qualifizierer des angegebenen Pfads zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9f662-183">Indicates that this cmdlet returns only the qualifier of the specified path.</span></span>
<span data-ttu-id="9f662-184">Für den Dateisystem- bzw. Registrierungsanbieter ist der Qualifizierer das Laufwerk des Anbieterpfads, beispielsweise %%amp;quot;C:%%amp;quot; oder %%amp;quot;HKCU:%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="9f662-184">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9f662-185">-Auflösen</span><span class="sxs-lookup"><span data-stu-id="9f662-185">-Resolve</span></span>

<span data-ttu-id="9f662-186">Gibt an, dass dieses Cmdlet die Elemente anzeigt, auf die vom resultierenden geteilten Pfad verwiesen wird, anstatt die Pfad Elemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f662-186">Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements.</span></span>

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

### <span data-ttu-id="9f662-187">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9f662-187">CommonParameters</span></span>

<span data-ttu-id="9f662-188">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9f662-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f662-189">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9f662-189">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9f662-190">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9f662-190">INPUTS</span></span>

### <span data-ttu-id="9f662-191">System.String</span><span class="sxs-lookup"><span data-stu-id="9f662-191">System.String</span></span>

<span data-ttu-id="9f662-192">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="9f662-192">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="9f662-193">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9f662-193">OUTPUTS</span></span>

### <span data-ttu-id="9f662-194">System. String, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="9f662-194">System.String, System.Boolean</span></span>

<span data-ttu-id="9f662-195">**Split-Path** gibt Text Zeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="9f662-195">**Split-Path** returns text strings.</span></span>
<span data-ttu-id="9f662-196">Wenn Sie den *Resolve* -Parameter angeben, gibt **Split-Path** eine Zeichenfolge zurück, die den Speicherort der Elemente beschreibt. Sie gibt keine Objekte zurück, die die Elemente darstellen, wie z. b. ein **FileInfo** -oder **RegistryKey** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="9f662-196">When you specify the *Resolve* parameter, **Split-Path** returns a string that describes the location of the items; it does not return objects that represent the items, such as a **FileInfo** or **RegistryKey** object.</span></span>

<span data-ttu-id="9f662-197">Wenn Sie den *IsAbsolute* -Parameter angeben, gibt **Split-Path** einen **booleschen** Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="9f662-197">When you specify the *IsAbsolute* parameter, **Split-Path** returns a **Boolean** value.</span></span>

## <span data-ttu-id="9f662-198">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9f662-198">NOTES</span></span>

* <span data-ttu-id="9f662-199">Die Split Location-Parameter ( *Qualifizierer* , über *geordnetes* Element, *Erweiterung* , *Blatt* , *leafbase* und *noqualifizierer* ) sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="9f662-199">The split location parameters ( *Qualifier* , *Parent* , *Extension* , *Leaf* , *LeafBase* , and *NoQualifier* ) are exclusive.</span></span> <span data-ttu-id="9f662-200">In einem Befehl kann immer nur ein Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9f662-200">You can use only one in each command.</span></span>

  <span data-ttu-id="9f662-201">Die Cmdlets, die das **Pfad** -Substantiv enthalten (die **path** -Cmdlets), funktionieren mit Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9f662-201">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span>
<span data-ttu-id="9f662-202">Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f662-202">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="9f662-203">Verwenden Sie diese in der Weise, in der Sie **dirname** , **normpath** , **realpath** , **Join** oder andere Pfad Manipulatoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f662-203">Use them in the way that you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

  <span data-ttu-id="9f662-204">Sie können die **Pfad** -Cmdlets mit verschiedenen Anbietern verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f662-204">You can use the **Path** cmdlets together with several providers.</span></span>
<span data-ttu-id="9f662-205">Hierzu gehören das Dateisystem, die Registrierung und die Zertifikat Anbieter.</span><span class="sxs-lookup"><span data-stu-id="9f662-205">These include the FileSystem, Registry, and Certificate providers.</span></span>

  <span data-ttu-id="9f662-206">**Split-Path** ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="9f662-206">**Split-Path** is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="9f662-207">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="9f662-207">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="9f662-208">Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="9f662-208">For more information, see about_Providers.</span></span>

## <span data-ttu-id="9f662-209">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9f662-209">RELATED LINKS</span></span>

[<span data-ttu-id="9f662-210">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="9f662-210">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="9f662-211">Join-Path</span><span class="sxs-lookup"><span data-stu-id="9f662-211">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="9f662-212">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="9f662-212">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="9f662-213">Test-Path</span><span class="sxs-lookup"><span data-stu-id="9f662-213">Test-Path</span></span>](Test-Path.md)
