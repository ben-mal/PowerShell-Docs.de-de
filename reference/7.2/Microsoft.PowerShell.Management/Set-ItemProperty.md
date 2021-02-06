---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: 18383dc2b1e018e56864e412dfe75eca2b578a08
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605375"
---
# <span data-ttu-id="5c265-102">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5c265-102">Set-ItemProperty</span></span>

## <span data-ttu-id="5c265-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5c265-103">SYNOPSIS</span></span>
<span data-ttu-id="5c265-104">Erstellt oder ändert den Wert für eine Eigenschaft eines Elements.</span><span class="sxs-lookup"><span data-stu-id="5c265-104">Creates or changes the value of a property of an item.</span></span>

## <span data-ttu-id="5c265-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5c265-105">SYNTAX</span></span>

### <span data-ttu-id="5c265-106">propertyvaluepathset (Standard)</span><span class="sxs-lookup"><span data-stu-id="5c265-106">propertyValuePathSet (Default)</span></span>

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="5c265-107">propertypsobjectpathset</span><span class="sxs-lookup"><span data-stu-id="5c265-107">propertyPSObjectPathSet</span></span>

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="5c265-108">propertyvalueliteralpathset</span><span class="sxs-lookup"><span data-stu-id="5c265-108">propertyValueLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="5c265-109">propertypsobjectliteralpathset</span><span class="sxs-lookup"><span data-stu-id="5c265-109">propertyPSObjectLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

## <span data-ttu-id="5c265-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c265-110">DESCRIPTION</span></span>

<span data-ttu-id="5c265-111">Das- `Set-ItemProperty` Cmdlet ändert den Wert der-Eigenschaft des angegebenen Elements.</span><span class="sxs-lookup"><span data-stu-id="5c265-111">The `Set-ItemProperty` cmdlet changes the value of the property of the specified item.</span></span>
<span data-ttu-id="5c265-112">Sie können mit dem Cmdlet die Eigenschaften von Elementen festlegen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="5c265-112">You can use the cmdlet to establish or change the properties of items.</span></span>
<span data-ttu-id="5c265-113">Beispielsweise können Sie verwenden, `Set-ItemProperty` um den Wert der **isread only** -Eigenschaft eines Datei Objekts auf festzulegen `$True` .</span><span class="sxs-lookup"><span data-stu-id="5c265-113">For example, you can use `Set-ItemProperty` to set the value of the **IsReadOnly** property of a file object to `$True`.</span></span>

<span data-ttu-id="5c265-114">Außerdem verwenden Sie `Set-ItemProperty` , um Registrierungs Werte und-Daten zu erstellen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5c265-114">You also use `Set-ItemProperty` to create and change registry values and data.</span></span>
<span data-ttu-id="5c265-115">Sie haben z. B. die Möglichkeit, einen neuen Registrierungseintrag in einem Schlüssel hinzuzufügen und seinen Wert festzulegen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5c265-115">For example, you can add a new registry entry to a key and establish or change its value.</span></span>

## <span data-ttu-id="5c265-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5c265-116">EXAMPLES</span></span>

### <span data-ttu-id="5c265-117">Beispiel 1: Festlegen einer Eigenschaft einer Datei</span><span class="sxs-lookup"><span data-stu-id="5c265-117">Example 1: Set a property of a file</span></span>

<span data-ttu-id="5c265-118">Mit diesem Befehl wird der Wert der **isread only** -Eigenschaft der Datei "final.doc" auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5c265-118">This command sets the value of the **IsReadOnly** property of the "final.doc" file to "true".</span></span>
<span data-ttu-id="5c265-119">Dabei wird **path** verwendet, um die Datei anzugeben, den **Namen** , um den Namen der Eigenschaft anzugeben, und den **value** -Parameter, um den neuen Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5c265-119">It uses **Path** to specify the file, **Name** to specify the name of the property, and the **Value** parameter to specify the new value.</span></span>

<span data-ttu-id="5c265-120">Bei der Datei handelt es sich um ein **System. IO. FileInfo** -Objekt, und **isread only** ist nur eine seiner Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="5c265-120">The file is a **System.IO.FileInfo** object and **IsReadOnly** is just one of its properties.</span></span>
<span data-ttu-id="5c265-121">Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property` .</span><span class="sxs-lookup"><span data-stu-id="5c265-121">To see all of the properties, type `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property`.</span></span>

<span data-ttu-id="5c265-122">Die `$true` Automatische Variable stellt den Wert "true" dar.</span><span class="sxs-lookup"><span data-stu-id="5c265-122">The `$true` automatic variable represents a value of "TRUE".</span></span>
<span data-ttu-id="5c265-123">Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5c265-123">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### <span data-ttu-id="5c265-124">Beispiel 2: Erstellen eines Registrierungs Eintrags und-Werts</span><span class="sxs-lookup"><span data-stu-id="5c265-124">Example 2: Create a registry entry and value</span></span>

<span data-ttu-id="5c265-125">In diesem Beispiel wird gezeigt, wie verwendet wird, `Set-ItemProperty` um einen neuen Registrierungs Eintrag zu erstellen und dem Eintrag einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="5c265-125">This example shows how to use `Set-ItemProperty` to create a new registry entry and to assign a value to the entry.</span></span> <span data-ttu-id="5c265-126">Er erstellt den Eintrag "noofemployees" im Schlüssel "contosocompany" im `HKLM\Software` Schlüssel und legt seinen Wert auf 823 fest.</span><span class="sxs-lookup"><span data-stu-id="5c265-126">It creates the "NoOfEmployees" entry in the "ContosoCompany" key in `HKLM\Software` key and sets its value to 823.</span></span>

<span data-ttu-id="5c265-127">Da Registrierungseinträge als Eigenschaften der Registrierungsschlüssel betrachtet werden, bei denen es sich um Elemente handelt, verwenden Sie, `Set-ItemProperty` um Registrierungseinträge zu erstellen und ihre Werte festzulegen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5c265-127">Because registry entries are considered to be properties of the registry keys, which are items, you use `Set-ItemProperty` to create registry entries, and to establish and change their values.</span></span>

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 823
```

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 824
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

<span data-ttu-id="5c265-128">Der erste Befehl erstellt den Registrierungs Eintrag.</span><span class="sxs-lookup"><span data-stu-id="5c265-128">The first command creates the registry entry.</span></span>
<span data-ttu-id="5c265-129">Dabei wird **path** verwendet, um den Pfad des `HKLM:` Laufwerks und den Schlüssel "software\mycompany" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5c265-129">It uses **Path** to specify the path of the `HKLM:` drive and the "Software\MyCompany" key.</span></span>
<span data-ttu-id="5c265-130">Der Befehl verwendet den **Namen** , um den Namen und den **Wert** des Eintrags anzugeben, um einen Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5c265-130">The command uses **Name** to specify the entry name and **Value** to specify a value.</span></span>

<span data-ttu-id="5c265-131">Der zweite Befehl verwendet das `Get-ItemProperty` Cmdlet, um den neuen Registrierungs Eintrag anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5c265-131">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>
<span data-ttu-id="5c265-132">Wenn Sie das- `Get-Item` `Get-ChildItem` Cmdlet oder das-Cmdlet verwenden, werden die Einträge nicht angezeigt, da es sich um Eigenschaften eines Schlüssels handelt, nicht um Elemente oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="5c265-132">If you use the `Get-Item` or `Get-ChildItem` cmdlets, the entries do not appear because they are properties of a key, not items or child items.</span></span>

<span data-ttu-id="5c265-133">Der dritte Befehl ändert den Wert des **noofemployees** -Eintrags in 824.</span><span class="sxs-lookup"><span data-stu-id="5c265-133">The third command changes the value of the **NoOfEmployees** entry to 824.</span></span>

<span data-ttu-id="5c265-134">Sie können auch mit dem `New-ItemProperty` Cmdlet den Registrierungs Eintrag und seinen Wert erstellen und dann verwenden `Set-ItemProperty` , um den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5c265-134">You can also use the `New-ItemProperty` cmdlet to create the registry entry and its value and then use `Set-ItemProperty` to change the value.</span></span>

<span data-ttu-id="5c265-135">Weitere Informationen zum Laufwerk erhalten Sie, wenn Sie `HKLM:` eingeben `Get-Help Get-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="5c265-135">For more information about the `HKLM:` drive, type `Get-Help Get-PSDrive`.</span></span>
<span data-ttu-id="5c265-136">Weitere Informationen zur Verwendung von PowerShell zum Verwalten der Registrierung erhalten Sie, wenn Sie eingeben `Get-Help Registry` .</span><span class="sxs-lookup"><span data-stu-id="5c265-136">For more information about how to use PowerShell to manage the registry, type `Get-Help Registry`.</span></span>

### <span data-ttu-id="5c265-137">Beispiel 3: Ändern eines Elements mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="5c265-137">Example 3: Modify an item by using the pipeline</span></span>

<span data-ttu-id="5c265-138">Diese Befehle zeigen, wie ein Pipeline Operator () verwendet wird, um `|` ein Element an zu senden `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="5c265-138">These commands show how to use a pipeline operator (`|`) to send an item to `Set-ItemProperty`.</span></span>

<span data-ttu-id="5c265-139">Der erste Teil des Befehls verwendet `Get-ChildItem` , um ein Objekt zu erhalten, das die Datei "Weekly.txt" darstellt.</span><span class="sxs-lookup"><span data-stu-id="5c265-139">The first part of the command uses `Get-ChildItem` to get an object that represents the "Weekly.txt" file.</span></span> <span data-ttu-id="5c265-140">Der Befehl verwendet einen Pipeline Operator, um das Datei Objekt an zu senden `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="5c265-140">The command uses a pipeline operator to send the file object to `Set-ItemProperty`.</span></span>
<span data-ttu-id="5c265-141">Der `Set-ItemProperty` Befehl verwendet die Parameter " **Name** " und " **value** ", um die Eigenschaft und ihren neuen Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5c265-141">The `Set-ItemProperty` command uses the **Name** and **Value** parameters to specify the property and its new value.</span></span>

<span data-ttu-id="5c265-142">Dieser Befehl entspricht der Verwendung des **Inputobject** -Parameters zum Angeben des abzurufenden Objekts `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="5c265-142">This command is equivalent to using the **InputObject** parameter to specify the object that `Get-ChildItem` gets.</span></span>

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

## <span data-ttu-id="5c265-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5c265-143">PARAMETERS</span></span>

### <span data-ttu-id="5c265-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="5c265-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="5c265-145">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5c265-145">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="5c265-146">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="5c265-146">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="5c265-147">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="5c265-147">-Exclude</span></span>

<span data-ttu-id="5c265-148">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5c265-148">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="5c265-149">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="5c265-149">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="5c265-150">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="5c265-150">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="5c265-151">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5c265-151">Wildcard characters are permitted.</span></span> <span data-ttu-id="5c265-152">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="5c265-152">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="5c265-153">-Filter</span><span class="sxs-lookup"><span data-stu-id="5c265-153">-Filter</span></span>

<span data-ttu-id="5c265-154">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="5c265-154">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="5c265-155">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5c265-155">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="5c265-156">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="5c265-156">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="5c265-157">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="5c265-157">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="5c265-158">-Force</span><span class="sxs-lookup"><span data-stu-id="5c265-158">-Force</span></span>

<span data-ttu-id="5c265-159">Zwingt das Cmdlet, eine Eigenschaft für Elemente festzulegen, auf die der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="5c265-159">Forces the cmdlet to set a property on items that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="5c265-160">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="5c265-160">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="5c265-161">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="5c265-161">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="5c265-162">-Include</span><span class="sxs-lookup"><span data-stu-id="5c265-162">-Include</span></span>

<span data-ttu-id="5c265-163">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="5c265-163">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="5c265-164">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="5c265-164">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="5c265-165">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="5c265-165">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="5c265-166">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5c265-166">Wildcard characters are permitted.</span></span> <span data-ttu-id="5c265-167">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="5c265-167">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="5c265-168">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5c265-168">-InputObject</span></span>

<span data-ttu-id="5c265-169">Gibt das-Objekt mit den Eigenschaften an, die von diesem Cmdlet geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5c265-169">Specifies the object that has the properties that this cmdlet changes.</span></span>
<span data-ttu-id="5c265-170">Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl ein, mit dem das Objekt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5c265-170">Enter a variable that contains the object or a command that gets the object.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: propertyPSObjectPathSet, propertyPSObjectLiteralPathSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5c265-171">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="5c265-171">-LiteralPath</span></span>

<span data-ttu-id="5c265-172">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="5c265-172">Specifies a path to one or more locations.</span></span> <span data-ttu-id="5c265-173">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5c265-173">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="5c265-174">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="5c265-174">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="5c265-175">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="5c265-175">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="5c265-176">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="5c265-176">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="5c265-177">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="5c265-177">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValueLiteralPathSet, propertyPSObjectLiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5c265-178">-Name</span><span class="sxs-lookup"><span data-stu-id="5c265-178">-Name</span></span>

<span data-ttu-id="5c265-179">Gibt den Namen der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="5c265-179">Specifies the name of the property.</span></span>

```yaml
Type: System.String
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5c265-180">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5c265-180">-PassThru</span></span>

<span data-ttu-id="5c265-181">Gibt ein Objekt zurück, das die Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="5c265-181">Returns an object that represents the item property.</span></span>
<span data-ttu-id="5c265-182">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="5c265-182">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5c265-183">-Path</span><span class="sxs-lookup"><span data-stu-id="5c265-183">-Path</span></span>

<span data-ttu-id="5c265-184">Gibt den Pfad der Elemente mit der Eigenschaft an, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c265-184">Specifies the path of the items with the property to modify.</span></span>
<span data-ttu-id="5c265-185">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5c265-185">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="5c265-186">-Type</span><span class="sxs-lookup"><span data-stu-id="5c265-186">-Type</span></span>

<span data-ttu-id="5c265-187">**Type** ist ein dynamischer Parameter, den der Registrierungs Anbieter dem `Set-ItemProperty` Cmdlet hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="5c265-187">**Type** is a dynamic parameter that the Registry provider adds to the `Set-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="5c265-188">Dieser Parameter funktioniert nur in den Registrierungs Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="5c265-188">This parameter only works in the registry drives.</span></span>

<span data-ttu-id="5c265-189">Gibt den Typ der Eigenschaft an, die von diesem Cmdlet hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5c265-189">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="5c265-190">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="5c265-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5c265-191">**String**: gibt eine NULL-terminierte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="5c265-191">**String**: Specifies a null-terminated string.</span></span> <span data-ttu-id="5c265-192">Entspricht **REG_SZ**.</span><span class="sxs-lookup"><span data-stu-id="5c265-192">Equivalent to **REG_SZ**.</span></span>
- <span data-ttu-id="5c265-193">**ExpandString**: gibt eine NULL-terminierte Zeichenfolge an, die nicht erweiterte Verweise auf Umgebungsvariablen enthält, die erweitert werden, wenn der Wert abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5c265-193">**ExpandString**: Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="5c265-194">Entspricht **REG_EXPAND_SZ**.</span><span class="sxs-lookup"><span data-stu-id="5c265-194">Equivalent to **REG_EXPAND_SZ**.</span></span>
- <span data-ttu-id="5c265-195">**Binary**: gibt Binärdaten in beliebiger Form an.</span><span class="sxs-lookup"><span data-stu-id="5c265-195">**Binary**: Specifies binary data in any form.</span></span> <span data-ttu-id="5c265-196">Entspricht **REG_BINARY**.</span><span class="sxs-lookup"><span data-stu-id="5c265-196">Equivalent to **REG_BINARY**.</span></span>
- <span data-ttu-id="5c265-197">**DWORD**: gibt eine 32-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="5c265-197">**DWord**: Specifies a 32-bit binary number.</span></span> <span data-ttu-id="5c265-198">Entspricht **REG_DWORD**.</span><span class="sxs-lookup"><span data-stu-id="5c265-198">Equivalent to **REG_DWORD**.</span></span>
- <span data-ttu-id="5c265-199">**MultiString**: gibt ein Array von auf NULL endenden Zeichen folgen an, die mit zwei NULL-Zeichen beendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c265-199">**MultiString**: Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="5c265-200">Entspricht **REG_MULTI_SZ**.</span><span class="sxs-lookup"><span data-stu-id="5c265-200">Equivalent to **REG_MULTI_SZ**.</span></span>
- <span data-ttu-id="5c265-201">**QWORD**: gibt eine 64-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="5c265-201">**Qword**: Specifies a 64-bit binary number.</span></span> <span data-ttu-id="5c265-202">Entspricht **REG_QWORD**.</span><span class="sxs-lookup"><span data-stu-id="5c265-202">Equivalent to **REG_QWORD**.</span></span>
- <span data-ttu-id="5c265-203">**Unknown**: gibt einen nicht unterstützten Registrierungs Datentyp an, z. b. **REG_RESOURCE_LIST**.</span><span class="sxs-lookup"><span data-stu-id="5c265-203">**Unknown**: Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST**.</span></span>

```yaml
Type: Microsoft.Win32.RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5c265-204">-Value</span><span class="sxs-lookup"><span data-stu-id="5c265-204">-Value</span></span>

<span data-ttu-id="5c265-205">Gibt den Wert der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="5c265-205">Specifies the value of the property.</span></span>

```yaml
Type: System.Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5c265-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5c265-206">-Confirm</span></span>

<span data-ttu-id="5c265-207">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5c265-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5c265-208">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5c265-208">-WhatIf</span></span>

<span data-ttu-id="5c265-209">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5c265-209">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5c265-210">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5c265-210">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5c265-211">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5c265-211">CommonParameters</span></span>

<span data-ttu-id="5c265-212">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="5c265-212">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="5c265-213">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="5c265-213">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="5c265-214">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5c265-214">INPUTS</span></span>

### <span data-ttu-id="5c265-215">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="5c265-215">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="5c265-216">Sie können Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="5c265-216">You can pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="5c265-217">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5c265-217">OUTPUTS</span></span>

### <span data-ttu-id="5c265-218">None, System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="5c265-218">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="5c265-219">Dieses Cmdlet generiert ein **pscustomobject** -Objekt, das das geänderte Element darstellt, und den neuen Eigenschafts Wert, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="5c265-219">This cmdlet generates a **PSCustomObject** object that represents the item that was changed and its new property value, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="5c265-220">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="5c265-220">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5c265-221">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5c265-221">NOTES</span></span>

<span data-ttu-id="5c265-222">`Set-ItemProperty` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="5c265-222">`Set-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="5c265-223">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="5c265-223">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="5c265-224">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="5c265-224">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="5c265-225">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5c265-225">RELATED LINKS</span></span>

[<span data-ttu-id="5c265-226">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5c265-226">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="5c265-227">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5c265-227">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="5c265-228">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5c265-228">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="5c265-229">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5c265-229">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="5c265-230">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5c265-230">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="5c265-231">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5c265-231">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="5c265-232">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5c265-232">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="5c265-233">about_Providers</span><span class="sxs-lookup"><span data-stu-id="5c265-233">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

