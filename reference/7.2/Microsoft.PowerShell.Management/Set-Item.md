---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Item
ms.openlocfilehash: c617f4554c8e61ed6cf54b0faf0cd7d79be84595
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601721"
---
# <span data-ttu-id="e8187-102">Set-Item</span><span class="sxs-lookup"><span data-stu-id="e8187-102">Set-Item</span></span>

## <span data-ttu-id="e8187-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e8187-103">SYNOPSIS</span></span>
<span data-ttu-id="e8187-104">Ändert den Wert eines Elements in den Wert, der im Befehl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e8187-104">Changes the value of an item to the value specified in the command.</span></span>

## <span data-ttu-id="e8187-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e8187-105">SYNTAX</span></span>

### <span data-ttu-id="e8187-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="e8187-106">Path (Default)</span></span>

```
Set-Item [-Path] <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e8187-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e8187-107">LiteralPath</span></span>

```
Set-Item -LiteralPath <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e8187-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e8187-108">DESCRIPTION</span></span>

<span data-ttu-id="e8187-109">Mit dem- `Set-Item` Cmdlet wird der Wert eines Elements, z. b. einer Variablen oder eines Registrierungsschlüssels, in den im Befehl angegebenen Wert geändert.</span><span class="sxs-lookup"><span data-stu-id="e8187-109">The `Set-Item` cmdlet changes the value of an item, such as a variable or registry key, to the value specified in the command.</span></span>

## <span data-ttu-id="e8187-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e8187-110">EXAMPLES</span></span>

### <span data-ttu-id="e8187-111">Beispiel 1: Erstellen eines Alias</span><span class="sxs-lookup"><span data-stu-id="e8187-111">Example 1: Create an alias</span></span>

<span data-ttu-id="e8187-112">Dieser Befehl erstellt einen Alias von NP für Notepad.</span><span class="sxs-lookup"><span data-stu-id="e8187-112">This command creates an alias of np for Notepad.</span></span>

```powershell
Set-Item -Path alias:np -Value "c:\windows\notepad.exe"
```

### <span data-ttu-id="e8187-113">Beispiel 2: Ändern des Werts einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="e8187-113">Example 2: Change the value of an environment variable</span></span>

<span data-ttu-id="e8187-114">Dieser Befehl ändert den Wert der Umgebungsvariablen "UserRole" in "Administrator".</span><span class="sxs-lookup"><span data-stu-id="e8187-114">This command changes the value of the UserRole environment variable to Administrator.</span></span>

```powershell
Set-Item -Path env:UserRole -Value "Administrator"
```

### <span data-ttu-id="e8187-115">Beispiel 3: Ändern der prompt-Funktion</span><span class="sxs-lookup"><span data-stu-id="e8187-115">Example 3: Modify your prompt function</span></span>

<span data-ttu-id="e8187-116">Mit diesem Befehl wird die prompt-Funktion so geändert, dass Sie die Zeit vor dem Pfad anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e8187-116">This command changes the prompt function so that it displays the time before the path.</span></span>

```powershell
Set-Item -Path function:prompt -Value {'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '}
```

### <span data-ttu-id="e8187-117">Beispiel 4: Festlegen von Optionen für die prompt-Funktion</span><span class="sxs-lookup"><span data-stu-id="e8187-117">Example 4: Set options for your prompt function</span></span>

<span data-ttu-id="e8187-118">Dieser Befehl legt die Optionen " **allscope** " und "read **only** " für die prompt-Funktion fest.</span><span class="sxs-lookup"><span data-stu-id="e8187-118">This command sets the **AllScope** and **ReadOnly** options for the prompt function.</span></span>
<span data-ttu-id="e8187-119">Dieser Befehl verwendet den dynamischen **options** -Parameter von `Set-Item` .</span><span class="sxs-lookup"><span data-stu-id="e8187-119">This command uses the **Options** dynamic parameter of `Set-Item`.</span></span>
<span data-ttu-id="e8187-120">Der **options** -Parameter ist nur in verfügbar, `Set-Item` Wenn er mit dem **Alias** -oder **Funktions** Anbieter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8187-120">The **Options** parameter is available in `Set-Item` only when you use it with the **Alias** or **Function** provider.</span></span>

```powershell
Set-Item -Path function:prompt -Options "AllScope,ReadOnly"
```

## <span data-ttu-id="e8187-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e8187-121">PARAMETERS</span></span>

### <span data-ttu-id="e8187-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="e8187-122">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="e8187-123">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8187-123">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="e8187-124">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="e8187-124">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="e8187-125">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="e8187-125">-Exclude</span></span>

<span data-ttu-id="e8187-126">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e8187-126">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="e8187-127">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="e8187-127">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e8187-128">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="e8187-128">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="e8187-129">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e8187-129">Wildcard characters are permitted.</span></span> <span data-ttu-id="e8187-130">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="e8187-130">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="e8187-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="e8187-131">-Filter</span></span>

<span data-ttu-id="e8187-132">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="e8187-132">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="e8187-133">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8187-133">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="e8187-134">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="e8187-134">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="e8187-135">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="e8187-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="e8187-136">-Force</span><span class="sxs-lookup"><span data-stu-id="e8187-136">-Force</span></span>

<span data-ttu-id="e8187-137">Zwingt das Cmdlet, Elemente festzulegen, die anderweitig nicht geändert werden können, z. b. schreibgeschützte Alias oder Variablen.</span><span class="sxs-lookup"><span data-stu-id="e8187-137">Forces the cmdlet to set items that cannot otherwise be changed, such as read-only alias or variables.</span></span> <span data-ttu-id="e8187-138">Mit diesem Cmdlet können keine konstanten Aliase oder Variablen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e8187-138">The cmdlet cannot change constant aliases or variables.</span></span>
<span data-ttu-id="e8187-139">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="e8187-139">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="e8187-140">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="e8187-140">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="e8187-141">Selbst bei Verwendung des *Force* -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="e8187-141">Even using the *Force* parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="e8187-142">-Include</span><span class="sxs-lookup"><span data-stu-id="e8187-142">-Include</span></span>

<span data-ttu-id="e8187-143">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="e8187-143">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="e8187-144">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="e8187-144">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e8187-145">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="e8187-145">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="e8187-146">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e8187-146">Wildcard characters are permitted.</span></span> <span data-ttu-id="e8187-147">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="e8187-147">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="e8187-148">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="e8187-148">-LiteralPath</span></span>

<span data-ttu-id="e8187-149">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="e8187-149">Specifies a path to one or more locations.</span></span> <span data-ttu-id="e8187-150">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e8187-150">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="e8187-151">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e8187-151">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="e8187-152">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="e8187-152">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e8187-153">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="e8187-153">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="e8187-154">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="e8187-154">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="e8187-155">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e8187-155">-PassThru</span></span>

<span data-ttu-id="e8187-156">Übergibt ein Objekt, das das Element darstellt, an die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="e8187-156">Passes an object that represents the item to the pipeline.</span></span>
<span data-ttu-id="e8187-157">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="e8187-157">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e8187-158">-Path</span><span class="sxs-lookup"><span data-stu-id="e8187-158">-Path</span></span>

<span data-ttu-id="e8187-159">Gibt einen Pfad zum Speicherort der Elemente an.</span><span class="sxs-lookup"><span data-stu-id="e8187-159">Specifies a path of the location of the items.</span></span>
<span data-ttu-id="e8187-160">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e8187-160">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="e8187-161">-Value</span><span class="sxs-lookup"><span data-stu-id="e8187-161">-Value</span></span>

<span data-ttu-id="e8187-162">Gibt einen neuen Wert für das Element an.</span><span class="sxs-lookup"><span data-stu-id="e8187-162">Specifies a new value for the item.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e8187-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e8187-163">-Confirm</span></span>

<span data-ttu-id="e8187-164">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="e8187-164">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e8187-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e8187-165">-WhatIf</span></span>

<span data-ttu-id="e8187-166">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e8187-166">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e8187-167">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8187-167">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e8187-168">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e8187-168">CommonParameters</span></span>

<span data-ttu-id="e8187-169">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="e8187-169">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="e8187-170">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e8187-170">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e8187-171">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e8187-171">INPUTS</span></span>

### <span data-ttu-id="e8187-172">System.Object</span><span class="sxs-lookup"><span data-stu-id="e8187-172">System.Object</span></span>

<span data-ttu-id="e8187-173">Sie können ein Objekt, das den neuen Wert des Elements darstellt, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="e8187-173">You can pipe an object that represents the new value of the item to this cmdlet.</span></span>

## <span data-ttu-id="e8187-174">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e8187-174">OUTPUTS</span></span>

### <span data-ttu-id="e8187-175">None oder ein Objekt, das das neue oder geänderte Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="e8187-175">None or an object representing the new or changed item.</span></span>

<span data-ttu-id="e8187-176">Dieses Cmdlet generiert ein Objekt, das das Element darstellt, wenn Sie den *passthru* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="e8187-176">This cmdlet generates an object that represent the item, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="e8187-177">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="e8187-177">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e8187-178">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e8187-178">NOTES</span></span>

- <span data-ttu-id="e8187-179">`Set-Item` wird vom PowerShell-File System-Anbieter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8187-179">`Set-Item` is not supported by the PowerShell FileSystem provider.</span></span> <span data-ttu-id="e8187-180">Verwenden Sie das-Cmdlet, um die Werte von Elementen im Dateisystem zu ändern `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="e8187-180">To change the values of items in the file system, use the `Set-Content` cmdlet.</span></span>
- <span data-ttu-id="e8187-181">In den Registrierungs Laufwerken `HKLM:` und `HKCU:` `Set-Item` ändert die Daten im (Standardwert) eines Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="e8187-181">In the Registry drives, `HKLM:` and `HKCU:`, `Set-Item` changes the data in the (Default) value of a registry key.</span></span>
  - <span data-ttu-id="e8187-182">Verwenden Sie das `New-Item` Cmdlet und, um die Namen von Registrierungs Schlüsseln zu erstellen und zu ändern `Rename-Item` .</span><span class="sxs-lookup"><span data-stu-id="e8187-182">To create and change the names of registry keys, use the `New-Item` and `Rename-Item` cmdlet.</span></span>
  - <span data-ttu-id="e8187-183">Um die Namen und Daten in Registrierungs Werten zu ändern, verwenden Sie die `New-ItemProperty` `Set-ItemProperty` `Rename-ItemProperty` Cmdlets, und.</span><span class="sxs-lookup"><span data-stu-id="e8187-183">To change the names and data in registry values, use the `New-ItemProperty`, `Set-ItemProperty`, and `Rename-ItemProperty` cmdlets.</span></span>
- <span data-ttu-id="e8187-184">`Set-Item` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="e8187-184">`Set-Item` is designed to work with the data exposed by any provider.</span></span>
  <span data-ttu-id="e8187-185">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="e8187-185">To list the providers available in your session, type `Get-PsProvider`.</span></span>
  <span data-ttu-id="e8187-186">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="e8187-186">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="e8187-187">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e8187-187">RELATED LINKS</span></span>

[<span data-ttu-id="e8187-188">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="e8187-188">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="e8187-189">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="e8187-189">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="e8187-190">Get-Item</span><span class="sxs-lookup"><span data-stu-id="e8187-190">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="e8187-191">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="e8187-191">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="e8187-192">Move-Item</span><span class="sxs-lookup"><span data-stu-id="e8187-192">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="e8187-193">New-Item</span><span class="sxs-lookup"><span data-stu-id="e8187-193">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="e8187-194">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="e8187-194">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="e8187-195">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="e8187-195">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="e8187-196">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e8187-196">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

