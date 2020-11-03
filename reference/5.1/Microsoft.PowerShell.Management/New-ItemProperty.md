---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 2569f4778f54f6cdad22e10cf92e727b73c323e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214612"
---
# <span data-ttu-id="442a7-103">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="442a7-103">New-ItemProperty</span></span>

## <span data-ttu-id="442a7-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="442a7-104">SYNOPSIS</span></span>
<span data-ttu-id="442a7-105">Erstellt eine neue Eigenschaft für ein Element und legt den Wert fest.</span><span class="sxs-lookup"><span data-stu-id="442a7-105">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="442a7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="442a7-106">SYNTAX</span></span>

### <span data-ttu-id="442a7-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="442a7-107">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="442a7-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="442a7-108">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="442a7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="442a7-109">DESCRIPTION</span></span>

<span data-ttu-id="442a7-110">Das `New-ItemProperty` -Cmdlet erstellt eine neue Eigenschaft für ein angegebenes Element und legt seinen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="442a7-110">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="442a7-111">Normalerweise werden mit diesem Cmdlet neue Registrierungswerte erstellt, da Registrierungswerte Eigenschaften eines Registrierungsschlüsselelements sind.</span><span class="sxs-lookup"><span data-stu-id="442a7-111">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="442a7-112">Dieses Cmdlet fügt einem Objekt keine Eigenschaften hinzu.</span><span class="sxs-lookup"><span data-stu-id="442a7-112">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="442a7-113">Zum Hinzufügen einer Eigenschaft zu einer Instanz eines Objekts verwenden Sie das- `Add-Member` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="442a7-113">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="442a7-114">Um allen Objekten eines bestimmten Typs eine Eigenschaft hinzuzufügen, ändern Sie die Types.ps1XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="442a7-114">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="442a7-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="442a7-115">EXAMPLES</span></span>

### <span data-ttu-id="442a7-116">Beispiel 1: Hinzufügen eines Registrierungs Eintrags</span><span class="sxs-lookup"><span data-stu-id="442a7-116">Example 1: Add a registry entry</span></span>

<span data-ttu-id="442a7-117">Mit diesem Befehl wird der neue Registrierungs Eintrag "noofemployees" dem Schlüssel "MyCompany" von "HKLM: \ Software Hive" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="442a7-117">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="442a7-118">Der erste Befehl verwendet den **path** -Parameter, um den Pfad des Registrierungsschlüssels "MyCompany" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="442a7-118">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="442a7-119">Er verwendet den **Name** -Parameter, um einen Namen für den Eintrag anzugeben, und den **value** -Parameter, um seinen Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="442a7-119">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="442a7-120">Der zweite Befehl verwendet das `Get-ItemProperty` Cmdlet, um den neuen Registrierungs Eintrag anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="442a7-120">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

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

### <span data-ttu-id="442a7-121">Beispiel 2: Hinzufügen eines Registrierungs Eintrags zu einem Schlüssel</span><span class="sxs-lookup"><span data-stu-id="442a7-121">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="442a7-122">Dieser Befehl fügt einem Registrierungsschlüssel einen neuen Registrierungseintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="442a7-122">This command adds a new registry entry to a registry key.</span></span> <span data-ttu-id="442a7-123">Zum Angeben des Schlüssels wird ein Pipeline Operator (|) verwendet, um ein Objekt, das den Schlüssel darstellt, an zu senden `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="442a7-123">To specify the key, it uses a pipeline operator (|) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="442a7-124">Der erste Teil des Befehls verwendet das `Get-Item` Cmdlet, um den Registrierungsschlüssel "MyCompany" zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="442a7-124">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span> <span data-ttu-id="442a7-125">Der Pipeline Operator sendet die Ergebnisse des Befehls an `New-ItemProperty` , wodurch der neue Registrierungs Eintrag ("nooflocations") und sein Wert (3) dem Schlüssel "MyCompany" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="442a7-125">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="442a7-126">Dieser Befehl funktioniert, da das Parameter Bindungs Feature von Windows PowerShell den Pfad des Objekts zuordnet `RegistryKey` , das `Get-Item` mit dem **literalpath** -Parameter von zurückgegeben wird `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="442a7-126">This command works because the parameter-binding feature of Windows PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="442a7-127">Weitere Informationen finden Sie unter [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="442a7-127">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="442a7-128">Beispiel 3: Erstellen eines mehrteiligen Zeichen folgen Werts in der Registrierung mit einem Here-String</span><span class="sxs-lookup"><span data-stu-id="442a7-128">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="442a7-129">In diesem Beispiel wird ein mehrteilige Zeichen folgen Wert mit einer here-Zeichenfolge erstellt.</span><span class="sxs-lookup"><span data-stu-id="442a7-129">This example creates a MultiString value using a Here-String.</span></span>

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

### <span data-ttu-id="442a7-130">Beispiel 4: Erstellen eines mehrteiligen Zeichen folgen Werts in der Registrierung mithilfe eines Arrays</span><span class="sxs-lookup"><span data-stu-id="442a7-130">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="442a7-131">Im Beispiel wird gezeigt, wie ein Array von Werten verwendet wird, um den Wert zu erstellen `MultiString` .</span><span class="sxs-lookup"><span data-stu-id="442a7-131">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="442a7-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="442a7-132">PARAMETERS</span></span>

### <span data-ttu-id="442a7-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="442a7-133">-Credential</span></span>

<span data-ttu-id="442a7-134">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="442a7-134">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="442a7-135">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="442a7-135">The default is the current user.</span></span>

<span data-ttu-id="442a7-136">Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="442a7-136">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="442a7-137">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="442a7-137">If you type a user name, you are prompted for a password.</span></span>

> [!NOTE]
> <span data-ttu-id="442a7-138">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="442a7-138">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="442a7-139">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="442a7-139">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="442a7-140">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="442a7-140">-Exclude</span></span>

<span data-ttu-id="442a7-141">Gibt als Zeichen folgen Array eine Eigenschaft oder eine Eigenschaft an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="442a7-141">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="442a7-142">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="442a7-142">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="442a7-143">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="442a7-143">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="442a7-144">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="442a7-144">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="442a7-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="442a7-145">-Filter</span></span>

<span data-ttu-id="442a7-146">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="442a7-146">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="442a7-147">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="442a7-147">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="442a7-148">Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="442a7-148">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="442a7-149">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="442a7-149">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="442a7-150">-Force</span><span class="sxs-lookup"><span data-stu-id="442a7-150">-Force</span></span>

<span data-ttu-id="442a7-151">Erzwingt, dass das Cmdlet eine Eigenschaft für ein Objekt erstellt, auf das der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="442a7-151">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="442a7-152">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="442a7-152">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="442a7-153">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="442a7-153">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="442a7-154">-Include</span><span class="sxs-lookup"><span data-stu-id="442a7-154">-Include</span></span>

<span data-ttu-id="442a7-155">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="442a7-155">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="442a7-156">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="442a7-156">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="442a7-157">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="442a7-157">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="442a7-158">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="442a7-158">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="442a7-159">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="442a7-159">-LiteralPath</span></span>

<span data-ttu-id="442a7-160">Gibt den Pfad zum aktuellen Speicherort der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="442a7-160">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="442a7-161">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="442a7-161">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="442a7-162">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="442a7-162">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="442a7-163">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="442a7-163">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="442a7-164">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="442a7-164">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="442a7-165">-Name</span><span class="sxs-lookup"><span data-stu-id="442a7-165">-Name</span></span>

<span data-ttu-id="442a7-166">Gibt einen Namen für die neue Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="442a7-166">Specifies a name for the new property.</span></span>
<span data-ttu-id="442a7-167">Wenn es sich bei der Eigenschaft um einen Registrierungseintrag handelt, gibt dieser Parameter den Namen des Eintrags an.</span><span class="sxs-lookup"><span data-stu-id="442a7-167">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

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

### <span data-ttu-id="442a7-168">-Path</span><span class="sxs-lookup"><span data-stu-id="442a7-168">-Path</span></span>

<span data-ttu-id="442a7-169">Gibt den Pfad des Elements an.</span><span class="sxs-lookup"><span data-stu-id="442a7-169">Specifies the path of the item.</span></span>
<span data-ttu-id="442a7-170">Dieser Parameter identifiziert das Element, dem dieses Cmdlet die neue Eigenschaft hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="442a7-170">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="442a7-171">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="442a7-171">-PropertyType</span></span>

<span data-ttu-id="442a7-172">Gibt den Typ der Eigenschaft an, die von diesem Cmdlet hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="442a7-172">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="442a7-173">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="442a7-173">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="442a7-174">**String** : gibt eine NULL-terminierte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="442a7-174">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="442a7-175">Entspricht **REG_SZ** .</span><span class="sxs-lookup"><span data-stu-id="442a7-175">Equivalent to **REG_SZ** .</span></span>
- <span data-ttu-id="442a7-176">**ExpandString** : gibt eine NULL-terminierte Zeichenfolge an, die nicht erweiterte Verweise auf Umgebungsvariablen enthält, die erweitert werden, wenn der Wert abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="442a7-176">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="442a7-177">Entspricht **REG_EXPAND_SZ** .</span><span class="sxs-lookup"><span data-stu-id="442a7-177">Equivalent to **REG_EXPAND_SZ** .</span></span>
- <span data-ttu-id="442a7-178">**Binary** : gibt Binärdaten in beliebiger Form an.</span><span class="sxs-lookup"><span data-stu-id="442a7-178">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="442a7-179">Entspricht **REG_BINARY** .</span><span class="sxs-lookup"><span data-stu-id="442a7-179">Equivalent to **REG_BINARY** .</span></span>
- <span data-ttu-id="442a7-180">**DWORD** : gibt eine 32-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="442a7-180">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="442a7-181">Entspricht **REG_DWORD** .</span><span class="sxs-lookup"><span data-stu-id="442a7-181">Equivalent to **REG_DWORD** .</span></span>
- <span data-ttu-id="442a7-182">**MultiString** : gibt ein Array von auf NULL endenden Zeichen folgen an, die mit zwei NULL-Zeichen beendet werden.</span><span class="sxs-lookup"><span data-stu-id="442a7-182">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="442a7-183">Entspricht **REG_MULTI_SZ** .</span><span class="sxs-lookup"><span data-stu-id="442a7-183">Equivalent to **REG_MULTI_SZ** .</span></span>
- <span data-ttu-id="442a7-184">**QWORD** : gibt eine 64-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="442a7-184">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="442a7-185">Entspricht **REG_QWORD** .</span><span class="sxs-lookup"><span data-stu-id="442a7-185">Equivalent to **REG_QWORD** .</span></span>
- <span data-ttu-id="442a7-186">**Unknown** : gibt einen nicht unterstützten Registrierungs Datentyp an, z. b. **REG_RESOURCE_LIST** .</span><span class="sxs-lookup"><span data-stu-id="442a7-186">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST** .</span></span>

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

### <span data-ttu-id="442a7-187">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="442a7-187">-UseTransaction</span></span>

<span data-ttu-id="442a7-188">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="442a7-188">Includes the command in the active transaction.</span></span>
<span data-ttu-id="442a7-189">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="442a7-189">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="442a7-190">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="442a7-190">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="442a7-191">-Value</span><span class="sxs-lookup"><span data-stu-id="442a7-191">-Value</span></span>

<span data-ttu-id="442a7-192">Gibt den Eigenschaftenwert an.</span><span class="sxs-lookup"><span data-stu-id="442a7-192">Specifies the property value.</span></span>
<span data-ttu-id="442a7-193">Wenn es sich bei der Eigenschaft um einen Registrierungseintrag handelt, gibt dieser Parameter den Wert des Eintrags an.</span><span class="sxs-lookup"><span data-stu-id="442a7-193">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

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

### <span data-ttu-id="442a7-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="442a7-194">-Confirm</span></span>

<span data-ttu-id="442a7-195">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="442a7-195">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="442a7-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="442a7-196">-WhatIf</span></span>

<span data-ttu-id="442a7-197">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="442a7-197">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="442a7-198">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="442a7-198">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="442a7-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="442a7-199">CommonParameters</span></span>

<span data-ttu-id="442a7-200">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="442a7-200">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="442a7-201">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="442a7-201">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="442a7-202">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="442a7-202">INPUTS</span></span>

### <span data-ttu-id="442a7-203">Keine</span><span class="sxs-lookup"><span data-stu-id="442a7-203">None</span></span>

<span data-ttu-id="442a7-204">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="442a7-204">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="442a7-205">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="442a7-205">OUTPUTS</span></span>

### <span data-ttu-id="442a7-206">System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="442a7-206">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="442a7-207">`New-ItemProperty` Gibt ein benutzerdefiniertes Objekt zurück, das die neue Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="442a7-207">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="442a7-208">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="442a7-208">NOTES</span></span>

<span data-ttu-id="442a7-209">`New-ItemProperty` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="442a7-209">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="442a7-210">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="442a7-210">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="442a7-211">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="442a7-211">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="442a7-212">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="442a7-212">RELATED LINKS</span></span>

[<span data-ttu-id="442a7-213">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="442a7-213">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="442a7-214">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="442a7-214">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="442a7-215">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="442a7-215">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="442a7-216">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="442a7-216">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="442a7-217">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="442a7-217">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="442a7-218">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="442a7-218">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="442a7-219">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="442a7-219">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="442a7-220">about_Providers</span><span class="sxs-lookup"><span data-stu-id="442a7-220">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
