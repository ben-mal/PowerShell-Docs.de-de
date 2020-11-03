---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: b1ee17e09a85c7f8afd3b41e7f9fb8b8dd5f019e
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210967"
---
# <span data-ttu-id="dff21-103">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dff21-103">New-ItemProperty</span></span>

## <span data-ttu-id="dff21-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dff21-104">SYNOPSIS</span></span>
<span data-ttu-id="dff21-105">Erstellt eine neue Eigenschaft für ein Element und legt den Wert fest.</span><span class="sxs-lookup"><span data-stu-id="dff21-105">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="dff21-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dff21-106">SYNTAX</span></span>

### <span data-ttu-id="dff21-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="dff21-107">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dff21-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="dff21-108">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="dff21-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dff21-109">DESCRIPTION</span></span>

<span data-ttu-id="dff21-110">Das `New-ItemProperty` -Cmdlet erstellt eine neue Eigenschaft für ein angegebenes Element und legt seinen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="dff21-110">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="dff21-111">Normalerweise werden mit diesem Cmdlet neue Registrierungswerte erstellt, da Registrierungswerte Eigenschaften eines Registrierungsschlüsselelements sind.</span><span class="sxs-lookup"><span data-stu-id="dff21-111">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="dff21-112">Dieses Cmdlet fügt einem Objekt keine Eigenschaften hinzu.</span><span class="sxs-lookup"><span data-stu-id="dff21-112">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="dff21-113">Zum Hinzufügen einer Eigenschaft zu einer Instanz eines Objekts verwenden Sie das- `Add-Member` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dff21-113">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="dff21-114">Um allen Objekten eines bestimmten Typs eine Eigenschaft hinzuzufügen, ändern Sie die Types.ps1XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="dff21-114">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="dff21-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dff21-115">EXAMPLES</span></span>

### <span data-ttu-id="dff21-116">Beispiel 1: Hinzufügen eines Registrierungs Eintrags</span><span class="sxs-lookup"><span data-stu-id="dff21-116">Example 1: Add a registry entry</span></span>

<span data-ttu-id="dff21-117">Mit diesem Befehl wird der neue Registrierungs Eintrag "noofemployees" dem Schlüssel "MyCompany" von "HKLM: \ Software Hive" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dff21-117">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="dff21-118">Der erste Befehl verwendet den **path** -Parameter, um den Pfad des Registrierungsschlüssels "MyCompany" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dff21-118">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="dff21-119">Er verwendet den **Name** -Parameter, um einen Namen für den Eintrag anzugeben, und den **value** -Parameter, um seinen Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dff21-119">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="dff21-120">Der zweite Befehl verwendet das `Get-ItemProperty` Cmdlet, um den neuen Registrierungs Eintrag anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dff21-120">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

```powershell
New-ItemProperty -Path "HKLM:\Software\MyCompany" -Name "NoOfEmployees" -Value 822
Get-ItemProperty "HKLM:\Software\MyCompany"
```

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\mycompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : mycompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 822
```

### <span data-ttu-id="dff21-121">Beispiel 2: Hinzufügen eines Registrierungs Eintrags zu einem Schlüssel</span><span class="sxs-lookup"><span data-stu-id="dff21-121">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="dff21-122">Dieser Befehl fügt einem Registrierungsschlüssel einen neuen Registrierungseintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="dff21-122">This command adds a new registry entry to a registry key.</span></span>
<span data-ttu-id="dff21-123">Zum Angeben des Schlüssels wird ein Pipeline Operator () verwendet, `|` um ein Objekt, das den Schlüssel darstellt, an zu senden `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="dff21-123">To specify the key, it uses a pipeline operator (`|`) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="dff21-124">Der erste Teil des Befehls verwendet das `Get-Item` Cmdlet, um den Registrierungsschlüssel "MyCompany" zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dff21-124">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span>
<span data-ttu-id="dff21-125">Der Pipeline Operator sendet die Ergebnisse des Befehls an `New-ItemProperty` , wodurch der neue Registrierungs Eintrag ("nooflocations") und sein Wert (3) dem Schlüssel "MyCompany" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dff21-125">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="dff21-126">Dieser Befehl funktioniert, da das Parameter Bindungs Feature von PowerShell den Pfad des Objekts zuordnet `RegistryKey` , das `Get-Item` mit dem **literalpath** -Parameter von zurückgegeben wird `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="dff21-126">This command works because the parameter-binding feature of PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="dff21-127">Weitere Informationen finden Sie unter [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="dff21-127">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="dff21-128">Beispiel 3: Erstellen eines mehrteiligen Zeichen folgen Werts in der Registrierung mit einem Here-String</span><span class="sxs-lookup"><span data-stu-id="dff21-128">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="dff21-129">In diesem Beispiel wird ein mehrteilige Zeichen folgen Wert mit einer here-Zeichenfolge erstellt.</span><span class="sxs-lookup"><span data-stu-id="dff21-129">This example creates a MultiString value using a Here-String.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'HereString' -PropertyType MultiString -Value @"
This is text which contains newlines
It can also contain "quoted" strings
"@
$newValue.multistring
```

```output
This is text which contains newlines
It can also contain "quoted" strings
```

### <span data-ttu-id="dff21-130">Beispiel 4: Erstellen eines mehrteiligen Zeichen folgen Werts in der Registrierung mithilfe eines Arrays</span><span class="sxs-lookup"><span data-stu-id="dff21-130">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="dff21-131">Im Beispiel wird gezeigt, wie ein Array von Werten verwendet wird, um den Wert zu erstellen `MultiString` .</span><span class="sxs-lookup"><span data-stu-id="dff21-131">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="dff21-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dff21-132">PARAMETERS</span></span>

### <span data-ttu-id="dff21-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="dff21-133">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="dff21-134">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dff21-134">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="dff21-135">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="dff21-135">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="dff21-136">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="dff21-136">-Exclude</span></span>

<span data-ttu-id="dff21-137">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="dff21-137">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="dff21-138">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dff21-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="dff21-139">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="dff21-139">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="dff21-140">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dff21-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="dff21-141">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="dff21-141">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="dff21-142">-Filter</span><span class="sxs-lookup"><span data-stu-id="dff21-142">-Filter</span></span>

<span data-ttu-id="dff21-143">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="dff21-143">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="dff21-144">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dff21-144">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="dff21-145">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="dff21-145">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="dff21-146">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="dff21-146">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="dff21-147">-Force</span><span class="sxs-lookup"><span data-stu-id="dff21-147">-Force</span></span>

<span data-ttu-id="dff21-148">Erzwingt, dass das Cmdlet eine Eigenschaft für ein Objekt erstellt, auf das der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="dff21-148">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="dff21-149">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="dff21-149">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="dff21-150">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="dff21-150">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="dff21-151">-Include</span><span class="sxs-lookup"><span data-stu-id="dff21-151">-Include</span></span>

<span data-ttu-id="dff21-152">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="dff21-152">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="dff21-153">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dff21-153">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="dff21-154">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="dff21-154">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="dff21-155">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dff21-155">Wildcard characters are permitted.</span></span> <span data-ttu-id="dff21-156">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="dff21-156">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="dff21-157">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="dff21-157">-LiteralPath</span></span>

<span data-ttu-id="dff21-158">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="dff21-158">Specifies a path to one or more locations.</span></span> <span data-ttu-id="dff21-159">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="dff21-159">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="dff21-160">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="dff21-160">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="dff21-161">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="dff21-161">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="dff21-162">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="dff21-162">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="dff21-163">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="dff21-163">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="dff21-164">-Name</span><span class="sxs-lookup"><span data-stu-id="dff21-164">-Name</span></span>

<span data-ttu-id="dff21-165">Gibt einen Namen für die neue Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="dff21-165">Specifies a name for the new property.</span></span>
<span data-ttu-id="dff21-166">Wenn es sich bei der Eigenschaft um einen Registrierungseintrag handelt, gibt dieser Parameter den Namen des Eintrags an.</span><span class="sxs-lookup"><span data-stu-id="dff21-166">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dff21-167">-Path</span><span class="sxs-lookup"><span data-stu-id="dff21-167">-Path</span></span>

<span data-ttu-id="dff21-168">Gibt den Pfad des Elements an.</span><span class="sxs-lookup"><span data-stu-id="dff21-168">Specifies the path of the item.</span></span>
<span data-ttu-id="dff21-169">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dff21-169">Wildcard characters are permitted.</span></span>
<span data-ttu-id="dff21-170">Dieser Parameter identifiziert das Element, dem dieses Cmdlet die neue Eigenschaft hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="dff21-170">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="dff21-171">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="dff21-171">-PropertyType</span></span>

<span data-ttu-id="dff21-172">Gibt den Typ der Eigenschaft an, die von diesem Cmdlet hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dff21-172">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="dff21-173">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="dff21-173">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="dff21-174">**String** : gibt eine NULL-terminierte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="dff21-174">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="dff21-175">Entspricht **REG_SZ** .</span><span class="sxs-lookup"><span data-stu-id="dff21-175">Equivalent to **REG_SZ** .</span></span>
- <span data-ttu-id="dff21-176">**ExpandString** : gibt eine NULL-terminierte Zeichenfolge an, die nicht erweiterte Verweise auf Umgebungsvariablen enthält, die erweitert werden, wenn der Wert abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dff21-176">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="dff21-177">Entspricht **REG_EXPAND_SZ** .</span><span class="sxs-lookup"><span data-stu-id="dff21-177">Equivalent to **REG_EXPAND_SZ** .</span></span>
- <span data-ttu-id="dff21-178">**Binary** : gibt Binärdaten in beliebiger Form an.</span><span class="sxs-lookup"><span data-stu-id="dff21-178">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="dff21-179">Entspricht **REG_BINARY** .</span><span class="sxs-lookup"><span data-stu-id="dff21-179">Equivalent to **REG_BINARY** .</span></span>
- <span data-ttu-id="dff21-180">**DWORD** : gibt eine 32-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="dff21-180">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="dff21-181">Entspricht **REG_DWORD** .</span><span class="sxs-lookup"><span data-stu-id="dff21-181">Equivalent to **REG_DWORD** .</span></span>
- <span data-ttu-id="dff21-182">**MultiString** : gibt ein Array von auf NULL endenden Zeichen folgen an, die mit zwei NULL-Zeichen beendet werden.</span><span class="sxs-lookup"><span data-stu-id="dff21-182">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="dff21-183">Entspricht **REG_MULTI_SZ** .</span><span class="sxs-lookup"><span data-stu-id="dff21-183">Equivalent to **REG_MULTI_SZ** .</span></span>
- <span data-ttu-id="dff21-184">**QWORD** : gibt eine 64-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="dff21-184">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="dff21-185">Entspricht **REG_QWORD** .</span><span class="sxs-lookup"><span data-stu-id="dff21-185">Equivalent to **REG_QWORD** .</span></span>
- <span data-ttu-id="dff21-186">**Unknown** : gibt einen nicht unterstützten Registrierungs Datentyp an, z. b. **REG_RESOURCE_LIST** .</span><span class="sxs-lookup"><span data-stu-id="dff21-186">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dff21-187">-Value</span><span class="sxs-lookup"><span data-stu-id="dff21-187">-Value</span></span>

<span data-ttu-id="dff21-188">Gibt den Eigenschaftenwert an.</span><span class="sxs-lookup"><span data-stu-id="dff21-188">Specifies the property value.</span></span>
<span data-ttu-id="dff21-189">Wenn es sich bei der Eigenschaft um einen Registrierungseintrag handelt, gibt dieser Parameter den Wert des Eintrags an.</span><span class="sxs-lookup"><span data-stu-id="dff21-189">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dff21-190">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dff21-190">-Confirm</span></span>

<span data-ttu-id="dff21-191">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="dff21-191">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="dff21-192">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dff21-192">-WhatIf</span></span>

<span data-ttu-id="dff21-193">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dff21-193">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="dff21-194">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dff21-194">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="dff21-195">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dff21-195">CommonParameters</span></span>

<span data-ttu-id="dff21-196">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="dff21-196">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="dff21-197">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="dff21-197">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="dff21-198">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dff21-198">INPUTS</span></span>

### <span data-ttu-id="dff21-199">Keine</span><span class="sxs-lookup"><span data-stu-id="dff21-199">None</span></span>

<span data-ttu-id="dff21-200">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="dff21-200">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="dff21-201">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dff21-201">OUTPUTS</span></span>

### <span data-ttu-id="dff21-202">System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="dff21-202">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="dff21-203">`New-ItemProperty` Gibt ein benutzerdefiniertes Objekt zurück, das die neue Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="dff21-203">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="dff21-204">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dff21-204">NOTES</span></span>

<span data-ttu-id="dff21-205">`New-ItemProperty` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="dff21-205">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="dff21-206">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="dff21-206">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="dff21-207">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="dff21-207">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="dff21-208">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dff21-208">RELATED LINKS</span></span>

[<span data-ttu-id="dff21-209">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dff21-209">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="dff21-210">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dff21-210">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="dff21-211">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dff21-211">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="dff21-212">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dff21-212">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="dff21-213">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dff21-213">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="dff21-214">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dff21-214">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="dff21-215">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dff21-215">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="dff21-216">about_Providers</span><span class="sxs-lookup"><span data-stu-id="dff21-216">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
