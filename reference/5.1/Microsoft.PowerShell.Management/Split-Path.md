---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: 5d92acbe080b0d232047f1184c9a369b8837845c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214399"
---
# <span data-ttu-id="b1324-103">Split-Path</span><span class="sxs-lookup"><span data-stu-id="b1324-103">Split-Path</span></span>

## <span data-ttu-id="b1324-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b1324-104">SYNOPSIS</span></span>
<span data-ttu-id="b1324-105">Gibt den angegebenen Teil eines Pfads zurück.</span><span class="sxs-lookup"><span data-stu-id="b1324-105">Returns the specified part of a path.</span></span>

## <span data-ttu-id="b1324-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b1324-106">SYNTAX</span></span>

### <span data-ttu-id="b1324-107">Parametriset (Standard)</span><span class="sxs-lookup"><span data-stu-id="b1324-107">ParentSet (Default)</span></span>

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="b1324-108">Noqualifierset</span><span class="sxs-lookup"><span data-stu-id="b1324-108">NoQualifierSet</span></span>

```
Split-Path [-Path] <String[]> [-NoQualifier] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="b1324-109">Blätter Satz</span><span class="sxs-lookup"><span data-stu-id="b1324-109">LeafSet</span></span>

```
Split-Path [-Path] <String[]> [-Leaf] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="b1324-110">Qualifierset</span><span class="sxs-lookup"><span data-stu-id="b1324-110">QualifierSet</span></span>

```
Split-Path [-Path] <String[]> [-Qualifier] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="b1324-111">Isabsoluteset</span><span class="sxs-lookup"><span data-stu-id="b1324-111">IsAbsoluteSet</span></span>

```
Split-Path [-Path] <String[]> [-Resolve] [-IsAbsolute] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="b1324-112">Literalpathset</span><span class="sxs-lookup"><span data-stu-id="b1324-112">LiteralPathSet</span></span>

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="b1324-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b1324-113">DESCRIPTION</span></span>

<span data-ttu-id="b1324-114">Das **Split-Path-** Cmdlet gibt nur den angegebenen Teil eines Pfads zurück, z. b. den übergeordneten Ordner, einen Unterordner oder einen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="b1324-114">The **Split-Path** cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a file name.</span></span>
<span data-ttu-id="b1324-115">Außerdem können Elemente abgerufen werden, auf die von dem geteilten Pfad verwiesen wird, und es kann angegeben werden, ob es sich um einen relativen oder absoluten Pfad handelt.</span><span class="sxs-lookup"><span data-stu-id="b1324-115">It can also get items that are referenced by the split path and tell whether the path is relative or absolute.</span></span>

<span data-ttu-id="b1324-116">Sie können mit diesem Cmdlet nur einen ausgewählten Teil eines Pfads abrufen oder senden.</span><span class="sxs-lookup"><span data-stu-id="b1324-116">You can use this cmdlet to get or submit only a selected part of a path.</span></span>

## <span data-ttu-id="b1324-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b1324-117">EXAMPLES</span></span>

### <span data-ttu-id="b1324-118">Beispiel 1: Holen Sie sich den Qualifizierer eines Pfads.</span><span class="sxs-lookup"><span data-stu-id="b1324-118">Example 1: Get the qualifier of a path</span></span>

```
PS C:\> Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
HKCU:
```

<span data-ttu-id="b1324-119">Mit diesem Befehl wird nur der Qualifizierer des Pfads zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1324-119">This command returns only the qualifier of the path.</span></span>
<span data-ttu-id="b1324-120">Der Qualifizierer ist das Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="b1324-120">The qualifier is the drive.</span></span>

### <span data-ttu-id="b1324-121">Beispiel 2: Anzeigen von Dateinamen</span><span class="sxs-lookup"><span data-stu-id="b1324-121">Example 2: Display file names</span></span>

```
PS C:\> Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
Pass1.log
Pass2.log
...
```

<span data-ttu-id="b1324-122">Mit diesem Befehl werden die Dateien angezeigt, auf die vom geteilten Pfad verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b1324-122">This command displays the files that are referenced by the split path.</span></span>
<span data-ttu-id="b1324-123">Da dieser Pfad auf das letzte Element aufgeteilt ist, das auch als Blatt bezeichnet wird, zeigt der Befehl nur die Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="b1324-123">Because this path is split to the last item, also known as the leaf, the command displays only the file names.</span></span>

<span data-ttu-id="b1324-124">Der *Resolve* -Parameter weist **Split-Path** an, die Elemente anzuzeigen, auf die der geteilte Pfad verweist, anstatt den geteilten Pfad anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1324-124">The *Resolve* parameter tells **Split-Path** to display the items that the split path references, instead of displaying the split path.</span></span>

<span data-ttu-id="b1324-125">Wie alle **Split-Path-** Befehle gibt dieser Befehl Zeichen folgen zurück.</span><span class="sxs-lookup"><span data-stu-id="b1324-125">Like all **Split-Path** commands, this command returns strings.</span></span>
<span data-ttu-id="b1324-126">Es werden keine **FileInfo** -Objekte zurückgegeben, die die Dateien darstellen.</span><span class="sxs-lookup"><span data-stu-id="b1324-126">It does not return **FileInfo** objects that represent the files.</span></span>

### <span data-ttu-id="b1324-127">Beispiel 3: Get the parent Container</span><span class="sxs-lookup"><span data-stu-id="b1324-127">Example 3: Get the parent container</span></span>

```
PS C:\> Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

<span data-ttu-id="b1324-128">Mit diesem Befehl werden nur die übergeordneten Container des Pfads zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1324-128">This command returns only the parent containers of the path.</span></span>
<span data-ttu-id="b1324-129">Da keine Parameter zum Angeben der Teilung enthalten sind, verwendet **Split-Path** den Standard *Wert für Split* Location, der übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b1324-129">Because it does not include any parameters to specify the split, **Split-Path** uses the split location default, which is *Parent* .</span></span>

### <span data-ttu-id="b1324-130">Beispiel 4: bestimmt, ob ein Pfad absolut ist</span><span class="sxs-lookup"><span data-stu-id="b1324-130">Example 4: Determines whether a path is absolute</span></span>

```
PS C:\> Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
False
```

<span data-ttu-id="b1324-131">Mit diesem Befehl wird bestimmt, ob der Pfad relativ oder absolut ist.</span><span class="sxs-lookup"><span data-stu-id="b1324-131">This command determines whether the path is relative or absolute.</span></span>
<span data-ttu-id="b1324-132">In diesem Fall wird $false zurückgegeben, da der Pfad relativ zum aktuellen Ordner ist, der durch einen Punkt (.) dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b1324-132">In this case, because the path is relative to the current folder, which is represented by a dot (.), it returns $False.</span></span>

### <span data-ttu-id="b1324-133">Beispiel 5: Ändern des Speicher Orts in einen angegebenen Pfad</span><span class="sxs-lookup"><span data-stu-id="b1324-133">Example 5: Change location to a specified path</span></span>

```
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

<span data-ttu-id="b1324-134">Mit diesem Befehl wird der Speicherort in den Ordner geändert, der das PowerShell-Profil enthält.</span><span class="sxs-lookup"><span data-stu-id="b1324-134">This command changes your location to the folder that contains the PowerShell profile.</span></span>

<span data-ttu-id="b1324-135">Der-Befehl in Klammern verwendet **Split-Path** , um nur das übergeordnete Element des Pfads zurückzugeben, der in der integrierten $profile Variablen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="b1324-135">The command in parentheses uses **Split-Path** to return only the parent of the path stored in the built-in $Profile variable.</span></span>
<span data-ttu-id="b1324-136">Der *Parent* -Parameter ist der standardmäßige Split Location-Parameter.</span><span class="sxs-lookup"><span data-stu-id="b1324-136">The *Parent* parameter is the default split location parameter.</span></span>
<span data-ttu-id="b1324-137">Aus diesem Grund können Sie Sie im Befehl weglassen.</span><span class="sxs-lookup"><span data-stu-id="b1324-137">Therefore, you can omit it from the command.</span></span>
<span data-ttu-id="b1324-138">Die Klammern leiten PowerShell an, den Befehl zuerst auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b1324-138">The parentheses direct PowerShell to run the command first.</span></span>
<span data-ttu-id="b1324-139">Dies ist eine hilfreiche Möglichkeit, um zu einem Ordner zu wechseln, der über einen langen Pfadnamen verfügt.</span><span class="sxs-lookup"><span data-stu-id="b1324-139">This is a useful way to move to a folder that has a long path name.</span></span>

### <span data-ttu-id="b1324-140">Beispiel 6: Aufteilen eines Pfads mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="b1324-140">Example 6: Split a path by using the pipeline</span></span>

```
PS C:\> 'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
C:\Documents and Settings\User01\My Documents
```

<span data-ttu-id="b1324-141">Dieser Befehl verwendet einen Pipeline Operator (|), um einen Pfad an **Split-Path** zu senden.</span><span class="sxs-lookup"><span data-stu-id="b1324-141">This command uses a pipeline operator (|) to send a path to **Split-Path** .</span></span>
<span data-ttu-id="b1324-142">Der Pfad ist in Anführungszeichen eingeschlossen, um anzugeben, dass es sich um ein einzelnes Token handelt.</span><span class="sxs-lookup"><span data-stu-id="b1324-142">The path is enclosed in quotation marks to indicate that it is a single token.</span></span>

## <span data-ttu-id="b1324-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b1324-143">PARAMETERS</span></span>

### <span data-ttu-id="b1324-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="b1324-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="b1324-145">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1324-145">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="b1324-146">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="b1324-146">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="b1324-147">-IsAbsolute</span><span class="sxs-lookup"><span data-stu-id="b1324-147">-IsAbsolute</span></span>

<span data-ttu-id="b1324-148">Gibt an, dass dieses Cmdlet $true zurückgibt, wenn der Pfad absolut ist, und $false, wenn er relativ ist.</span><span class="sxs-lookup"><span data-stu-id="b1324-148">Indicates that this cmdlet returns $True if the path is absolute and $False if it is relative.</span></span>
<span data-ttu-id="b1324-149">Ein absoluter Pfad weist eine Länge größer als 0 (null) auf und verwendet keinen Punkt (.), um den aktuellen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b1324-149">An absolute path has a length greater than zero and does not use a dot (.) to indicate the current path.</span></span>

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

### <span data-ttu-id="b1324-150">-Blatt</span><span class="sxs-lookup"><span data-stu-id="b1324-150">-Leaf</span></span>

<span data-ttu-id="b1324-151">Gibt an, dass dieses Cmdlet nur das letzte Element bzw. den letzten Container im Pfad zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b1324-151">Indicates that this cmdlet returns only the last item or container in the path.</span></span>
<span data-ttu-id="b1324-152">Beispielsweise wird im Pfad `C:\Test\Logs\Pass1.log` nur Pass1. log zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1324-152">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only Pass1.log.</span></span>

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

### <span data-ttu-id="b1324-153">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="b1324-153">-LiteralPath</span></span>

<span data-ttu-id="b1324-154">Gibt die zu teilenden Pfade an.</span><span class="sxs-lookup"><span data-stu-id="b1324-154">Specifies the paths to be split.</span></span>
<span data-ttu-id="b1324-155">Im Gegensatz zu *Path* wird der Wert von *LiteralPath* genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b1324-155">Unlike *Path* , the value of *LiteralPath* is used exactly as it is typed.</span></span>
<span data-ttu-id="b1324-156">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="b1324-156">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="b1324-157">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="b1324-157">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="b1324-158">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="b1324-158">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b1324-159">-Noqualifizierer</span><span class="sxs-lookup"><span data-stu-id="b1324-159">-NoQualifier</span></span>

<span data-ttu-id="b1324-160">Gibt an, dass dieses Cmdlet den Pfad ohne den Qualifizierer zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b1324-160">Indicates that this cmdlet returns the path without the qualifier.</span></span>
<span data-ttu-id="b1324-161">Für den Dateisystem- bzw. Registrierungsanbieter ist der Qualifizierer das Laufwerk des Anbieterpfads, beispielsweise %%amp;quot;C:%%amp;quot; oder %%amp;quot;HKCU:%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="b1324-161">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>
<span data-ttu-id="b1324-162">Beispielsweise wird im Pfad `C:\Test\Logs\Pass1.log` nur "\test\logs\pass1.log" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1324-162">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only \Test\Logs\Pass1.log.</span></span>

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

### <span data-ttu-id="b1324-163">-Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="b1324-163">-Parent</span></span>

<span data-ttu-id="b1324-164">Gibt an, dass dieses Cmdlet nur die übergeordneten Container des Elements oder des Containers zurückgibt, der durch den Pfad angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b1324-164">Indicates that this cmdlet returns only the parent containers of the item or of the container specified by the path.</span></span>
<span data-ttu-id="b1324-165">Beispielsweise gibt es im Pfad den Wert `C:\Test\Logs\Pass1.log` c:\test\logs.</span><span class="sxs-lookup"><span data-stu-id="b1324-165">For example, in the path `C:\Test\Logs\Pass1.log`, it returns C:\Test\Logs.</span></span>
<span data-ttu-id="b1324-166">Der *Parent* -Parameter ist der standardmäßige Split Location-Parameter.</span><span class="sxs-lookup"><span data-stu-id="b1324-166">The *Parent* parameter is the default split location parameter.</span></span>

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

### <span data-ttu-id="b1324-167">-Path</span><span class="sxs-lookup"><span data-stu-id="b1324-167">-Path</span></span>

<span data-ttu-id="b1324-168">Gibt die zu teilenden Pfade an.</span><span class="sxs-lookup"><span data-stu-id="b1324-168">Specifies the paths to be split.</span></span>
<span data-ttu-id="b1324-169">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b1324-169">Wildcard characters are permitted.</span></span>
<span data-ttu-id="b1324-170">Wenn der Pfad Leerzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="b1324-170">If the path includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="b1324-171">Sie können einen Pfad auch über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="b1324-171">You can also pipe a path to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ParentSet, NoQualifierSet, LeafSet, QualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="b1324-172">-Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="b1324-172">-Qualifier</span></span>

<span data-ttu-id="b1324-173">Gibt an, dass dieses Cmdlet nur den Qualifizierer des angegebenen Pfads zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b1324-173">Indicates that this cmdlet returns only the qualifier of the specified path.</span></span>
<span data-ttu-id="b1324-174">Für den Dateisystem- bzw. Registrierungsanbieter ist der Qualifizierer das Laufwerk des Anbieterpfads, beispielsweise %%amp;quot;C:%%amp;quot; oder %%amp;quot;HKCU:%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="b1324-174">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>

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

### <span data-ttu-id="b1324-175">-Auflösen</span><span class="sxs-lookup"><span data-stu-id="b1324-175">-Resolve</span></span>

<span data-ttu-id="b1324-176">Gibt an, dass dieses Cmdlet die Elemente anzeigt, auf die vom resultierenden geteilten Pfad verwiesen wird, anstatt die Pfad Elemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1324-176">Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements.</span></span>

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

### <span data-ttu-id="b1324-177">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="b1324-177">-UseTransaction</span></span>

<span data-ttu-id="b1324-178">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="b1324-178">Includes the command in the active transaction.</span></span>
<span data-ttu-id="b1324-179">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b1324-179">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="b1324-180">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="b1324-180">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="b1324-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b1324-181">CommonParameters</span></span>

<span data-ttu-id="b1324-182">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b1324-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b1324-183">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b1324-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b1324-184">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b1324-184">INPUTS</span></span>

### <span data-ttu-id="b1324-185">System.String</span><span class="sxs-lookup"><span data-stu-id="b1324-185">System.String</span></span>

<span data-ttu-id="b1324-186">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="b1324-186">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="b1324-187">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b1324-187">OUTPUTS</span></span>

### <span data-ttu-id="b1324-188">System. String, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="b1324-188">System.String, System.Boolean</span></span>

<span data-ttu-id="b1324-189">**Split-Path** gibt Text Zeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="b1324-189">**Split-Path** returns text strings.</span></span>
<span data-ttu-id="b1324-190">Wenn Sie den *Resolve* -Parameter angeben, gibt **Split-Path** eine Zeichenfolge zurück, die den Speicherort der Elemente beschreibt. Sie gibt keine Objekte zurück, die die Elemente darstellen, wie z. b. ein **FileInfo** -oder **RegistryKey** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="b1324-190">When you specify the *Resolve* parameter, **Split-Path** returns a string that describes the location of the items; it does not return objects that represent the items, such as a **FileInfo** or **RegistryKey** object.</span></span>

<span data-ttu-id="b1324-191">Wenn Sie den *IsAbsolute* -Parameter angeben, gibt **Split-Path** einen **booleschen** Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1324-191">When you specify the *IsAbsolute* parameter, **Split-Path** returns a **Boolean** value.</span></span>

## <span data-ttu-id="b1324-192">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b1324-192">NOTES</span></span>

* <span data-ttu-id="b1324-193">Die Split Location-Parameter ( *Qualifizierer* , über *geordnetes* Element, *Blatt* und *noqualifizierer* ) sind exklusiv.</span><span class="sxs-lookup"><span data-stu-id="b1324-193">The split location parameters ( *Qualifier* , *Parent* , *Leaf* , and *NoQualifier* ) are exclusive.</span></span> <span data-ttu-id="b1324-194">In einem Befehl kann immer nur ein Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b1324-194">You can use only one in each command.</span></span>

  <span data-ttu-id="b1324-195">Die Cmdlets, die das **Pfad** -Substantiv enthalten (die **path** -Cmdlets), funktionieren mit Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b1324-195">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span>
<span data-ttu-id="b1324-196">Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b1324-196">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="b1324-197">Verwenden Sie diese in der Weise, in der Sie **dirname** , **normpath** , **realpath** , **Join** oder andere Pfad Manipulatoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1324-197">Use them in the way that you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

  <span data-ttu-id="b1324-198">Sie können die **Pfad** -Cmdlets mit verschiedenen Anbietern verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1324-198">You can use the **Path** cmdlets together with several providers.</span></span>
<span data-ttu-id="b1324-199">Hierzu gehören das Dateisystem, die Registrierung und die Zertifikat Anbieter.</span><span class="sxs-lookup"><span data-stu-id="b1324-199">These include the FileSystem, Registry, and Certificate providers.</span></span>

  <span data-ttu-id="b1324-200">**Split-Path** ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b1324-200">**Split-Path** is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="b1324-201">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="b1324-201">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="b1324-202">Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="b1324-202">For more information, see about_Providers.</span></span>

## <span data-ttu-id="b1324-203">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b1324-203">RELATED LINKS</span></span>

[<span data-ttu-id="b1324-204">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="b1324-204">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="b1324-205">Join-Path</span><span class="sxs-lookup"><span data-stu-id="b1324-205">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="b1324-206">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="b1324-206">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="b1324-207">Test-Path</span><span class="sxs-lookup"><span data-stu-id="b1324-207">Test-Path</span></span>](Test-Path.md)
