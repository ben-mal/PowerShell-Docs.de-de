---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: cbd1229721650823d9780517934c40a2287f4227
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692668"
---
# <span data-ttu-id="d2a52-103">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2a52-103">Set-ItemProperty</span></span>

## <span data-ttu-id="d2a52-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d2a52-104">SYNOPSIS</span></span>
<span data-ttu-id="d2a52-105">Erstellt oder ändert den Wert für eine Eigenschaft eines Elements.</span><span class="sxs-lookup"><span data-stu-id="d2a52-105">Creates or changes the value of a property of an item.</span></span>

## <span data-ttu-id="d2a52-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d2a52-106">SYNTAX</span></span>

### <span data-ttu-id="d2a52-107">propertyvaluepathset (Standard)</span><span class="sxs-lookup"><span data-stu-id="d2a52-107">propertyValuePathSet (Default)</span></span>

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="d2a52-108">propertypsobjectpathset</span><span class="sxs-lookup"><span data-stu-id="d2a52-108">propertyPSObjectPathSet</span></span>

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="d2a52-109">propertyvalueliteralpathset</span><span class="sxs-lookup"><span data-stu-id="d2a52-109">propertyValueLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="d2a52-110">propertypsobjectliteralpathset</span><span class="sxs-lookup"><span data-stu-id="d2a52-110">propertyPSObjectLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="d2a52-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d2a52-111">DESCRIPTION</span></span>

<span data-ttu-id="d2a52-112">Das- `Set-ItemProperty` Cmdlet ändert den Wert der-Eigenschaft des angegebenen Elements.</span><span class="sxs-lookup"><span data-stu-id="d2a52-112">The `Set-ItemProperty` cmdlet changes the value of the property of the specified item.</span></span> <span data-ttu-id="d2a52-113">Sie können mit dem Cmdlet die Eigenschaften von Elementen festlegen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="d2a52-113">You can use the cmdlet to establish or change the properties of items.</span></span> <span data-ttu-id="d2a52-114">Beispielsweise können Sie verwenden, `Set-ItemProperty` um den Wert der **isread only** -Eigenschaft eines Datei Objekts auf festzulegen `$True` .</span><span class="sxs-lookup"><span data-stu-id="d2a52-114">For example, you can use `Set-ItemProperty` to set the value of the **IsReadOnly** property of a file object to `$True`.</span></span>

<span data-ttu-id="d2a52-115">Außerdem verwenden Sie `Set-ItemProperty` , um Registrierungs Werte und-Daten zu erstellen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d2a52-115">You also use `Set-ItemProperty` to create and change registry values and data.</span></span>
<span data-ttu-id="d2a52-116">Sie haben z. B. die Möglichkeit, einen neuen Registrierungseintrag in einem Schlüssel hinzuzufügen und seinen Wert festzulegen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d2a52-116">For example, you can add a new registry entry to a key and establish or change its value.</span></span>

## <span data-ttu-id="d2a52-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d2a52-117">EXAMPLES</span></span>

### <span data-ttu-id="d2a52-118">Beispiel 1: Festlegen einer Eigenschaft einer Datei</span><span class="sxs-lookup"><span data-stu-id="d2a52-118">Example 1: Set a property of a file</span></span>

<span data-ttu-id="d2a52-119">Mit diesem Befehl wird der Wert der **isread only** -Eigenschaft der Datei "final.doc" auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d2a52-119">This command sets the value of the **IsReadOnly** property of the "final.doc" file to "true".</span></span> <span data-ttu-id="d2a52-120">Dabei wird **path** verwendet, um die Datei anzugeben, den **Namen** , um den Namen der Eigenschaft anzugeben, und den **value** -Parameter, um den neuen Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d2a52-120">It uses **Path** to specify the file, **Name** to specify the name of the property, and the **Value** parameter to specify the new value.</span></span>

<span data-ttu-id="d2a52-121">Bei der Datei handelt es sich um ein **System. IO. FileInfo** -Objekt, und **isread only** ist nur eine seiner Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="d2a52-121">The file is a **System.IO.FileInfo** object and **IsReadOnly** is just one of its properties.</span></span>
<span data-ttu-id="d2a52-122">Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType Property` .</span><span class="sxs-lookup"><span data-stu-id="d2a52-122">To see all of the properties, type `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType Property`.</span></span>

<span data-ttu-id="d2a52-123">Die `$true` Automatische Variable stellt den Wert "true" dar.</span><span class="sxs-lookup"><span data-stu-id="d2a52-123">The `$true` automatic variable represents a value of "TRUE".</span></span>
<span data-ttu-id="d2a52-124">Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d2a52-124">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### <span data-ttu-id="d2a52-125">Beispiel 2: Erstellen eines Registrierungs Eintrags und-Werts</span><span class="sxs-lookup"><span data-stu-id="d2a52-125">Example 2: Create a registry entry and value</span></span>

<span data-ttu-id="d2a52-126">In diesem Beispiel wird gezeigt, wie verwendet wird, `Set-ItemProperty` um einen neuen Registrierungs Eintrag zu erstellen und dem Eintrag einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="d2a52-126">This example shows how to use `Set-ItemProperty` to create a new registry entry and to assign a value to the entry.</span></span> <span data-ttu-id="d2a52-127">Der Eintrag "noofemployees" im Schlüssel "contosocompany" im Schlüssel "HKLM\Software" wird erstellt, und der Wert wird auf 823 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d2a52-127">It creates the "NoOfEmployees" entry in the "ContosoCompany" key in "HKLM\Software" key and sets its value to 823.</span></span>

<span data-ttu-id="d2a52-128">Da Registrierungseinträge als Eigenschaften der Registrierungsschlüssel betrachtet werden, bei denen es sich um Elemente handelt, verwenden Sie, `Set-ItemProperty` um Registrierungseinträge zu erstellen und ihre Werte festzulegen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d2a52-128">Because registry entries are considered to be properties of the registry keys, which are items, you use `Set-ItemProperty` to create registry entries, and to establish and change their values.</span></span>

<span data-ttu-id="d2a52-129">Der erste Befehl erstellt den Registrierungs Eintrag.</span><span class="sxs-lookup"><span data-stu-id="d2a52-129">The first command creates the registry entry.</span></span>
<span data-ttu-id="d2a52-130">Dabei wird **path** verwendet, um den Pfad des `HKLM:` Laufwerks und den Schlüssel "software\mycompany" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d2a52-130">It uses **Path** to specify the path of the `HKLM:` drive and the "Software\MyCompany" key.</span></span>
<span data-ttu-id="d2a52-131">Der Befehl verwendet den **Namen** , um den Namen und den **Wert** des Eintrags anzugeben, um einen Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d2a52-131">The command uses **Name** to specify the entry name and **Value** to specify a value.</span></span>

<span data-ttu-id="d2a52-132">Der zweite Befehl verwendet das `Get-ItemProperty` Cmdlet, um den neuen Registrierungs Eintrag anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d2a52-132">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span> <span data-ttu-id="d2a52-133">Wenn Sie das- `Get-Item` `Get-ChildItem` Cmdlet oder das-Cmdlet verwenden, werden die Einträge nicht angezeigt, da es sich um Eigenschaften eines Schlüssels handelt, nicht um Elemente oder untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="d2a52-133">If you use the `Get-Item` or `Get-ChildItem` cmdlets, the entries do not appear because they are properties of a key, not items or child items.</span></span>

<span data-ttu-id="d2a52-134">Der dritte Befehl ändert den Wert des **noofemployees** -Eintrags in 824.</span><span class="sxs-lookup"><span data-stu-id="d2a52-134">The third command changes the value of the **NoOfEmployees** entry to 824.</span></span>

<span data-ttu-id="d2a52-135">Sie können auch mit dem `New-ItemProperty` Cmdlet den Registrierungs Eintrag und seinen Wert erstellen und dann verwenden `Set-ItemProperty` , um den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d2a52-135">You can also use the `New-ItemProperty` cmdlet to create the registry entry and its value and then use `Set-ItemProperty` to change the value.</span></span>

<span data-ttu-id="d2a52-136">Weitere Informationen zum Laufwerk erhalten Sie, wenn Sie `HKLM:` eingeben `Get-Help Get-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="d2a52-136">For more information about the `HKLM:` drive, type `Get-Help Get-PSDrive`.</span></span>
<span data-ttu-id="d2a52-137">Weitere Informationen zur Verwendung von PowerShell zum Verwalten der Registrierung erhalten Sie, wenn Sie eingeben `Get-Help Registry` .</span><span class="sxs-lookup"><span data-stu-id="d2a52-137">For more information about how to use PowerShell to manage the registry, type `Get-Help Registry`.</span></span>

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```output
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

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

### <span data-ttu-id="d2a52-138">Beispiel 3: Ändern eines Elements mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="d2a52-138">Example 3: Modify an item by using the pipeline</span></span>

<span data-ttu-id="d2a52-139">Diese Befehle zeigen, wie ein Pipeline Operator () verwendet wird, um `|` ein Element an zu senden `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="d2a52-139">These commands show how to use a pipeline operator (`|`) to send an item to `Set-ItemProperty`.</span></span>

<span data-ttu-id="d2a52-140">Der erste Teil des Befehls verwendet `Get-ChildItem` , um ein Objekt zu erhalten, das die Datei "Weekly.txt" darstellt.</span><span class="sxs-lookup"><span data-stu-id="d2a52-140">The first part of the command uses `Get-ChildItem` to get an object that represents the "Weekly.txt" file.</span></span>
<span data-ttu-id="d2a52-141">Der Befehl verwendet einen Pipeline Operator, um das Datei Objekt an zu senden `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="d2a52-141">The command uses a pipeline operator to send the file object to `Set-ItemProperty`.</span></span>
<span data-ttu-id="d2a52-142">Der `Set-ItemProperty` Befehl verwendet die Parameter " **Name** " und " **value** ", um die Eigenschaft und ihren neuen Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d2a52-142">The `Set-ItemProperty` command uses the **Name** and **Value** parameters to specify the property and its new value.</span></span>

<span data-ttu-id="d2a52-143">Dieser Befehl entspricht der Verwendung des **Inputobject** -Parameters zum Angeben des abzurufenden Objekts `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="d2a52-143">This command is equivalent to using the **InputObject** parameter to specify the object that `Get-ChildItem` gets.</span></span>

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

## <span data-ttu-id="d2a52-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d2a52-144">PARAMETERS</span></span>

### <span data-ttu-id="d2a52-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="d2a52-145">-Credential</span></span>

<span data-ttu-id="d2a52-146">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="d2a52-146">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="d2a52-147">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d2a52-147">The default is the current user.</span></span>

<span data-ttu-id="d2a52-148">Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential**-Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="d2a52-148">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="d2a52-149">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d2a52-149">If you type a user name, you are prompted for a password.</span></span>

> [!NOTE]
> <span data-ttu-id="d2a52-150">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d2a52-150">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="d2a52-151">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="d2a52-151">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="d2a52-152">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="d2a52-152">-Exclude</span></span>

<span data-ttu-id="d2a52-153">Gibt die Elemente an, auf die das Cmdlet nicht angewendet wird, und schließt alle anderen ein.</span><span class="sxs-lookup"><span data-stu-id="d2a52-153">Specifies those items upon which the cmdlet does not act, and includes all others.</span></span>
<span data-ttu-id="d2a52-154">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="d2a52-154">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="d2a52-155">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="d2a52-155">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="d2a52-156">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d2a52-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="d2a52-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="d2a52-157">-Filter</span></span>

<span data-ttu-id="d2a52-158">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="d2a52-158">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="d2a52-159">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="d2a52-159">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="d2a52-160">Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="d2a52-160">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="d2a52-161">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="d2a52-161">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="d2a52-162">-Force</span><span class="sxs-lookup"><span data-stu-id="d2a52-162">-Force</span></span>

<span data-ttu-id="d2a52-163">Zwingt das Cmdlet, eine Eigenschaft für Elemente festzulegen, auf die der Benutzer anderweitig nicht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d2a52-163">Forces the cmdlet to set a property on items that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="d2a52-164">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="d2a52-164">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="d2a52-165">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d2a52-165">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="d2a52-166">-Include</span><span class="sxs-lookup"><span data-stu-id="d2a52-166">-Include</span></span>

<span data-ttu-id="d2a52-167">Gibt nur die Elemente an, auf die das Cmdlet angewendet wird, wobei alle anderen Elemente ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d2a52-167">Specifies only those items upon which the cmdlet acts, which excludes all others.</span></span>
<span data-ttu-id="d2a52-168">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="d2a52-168">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="d2a52-169">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="d2a52-169">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="d2a52-170">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d2a52-170">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="d2a52-171">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d2a52-171">-InputObject</span></span>

<span data-ttu-id="d2a52-172">Gibt das-Objekt mit den Eigenschaften an, die von diesem Cmdlet geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d2a52-172">Specifies the object that has the properties that this cmdlet changes.</span></span>
<span data-ttu-id="d2a52-173">Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl ein, mit dem das Objekt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d2a52-173">Enter a variable that contains the object or a command that gets the object.</span></span>

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

### <span data-ttu-id="d2a52-174">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="d2a52-174">-LiteralPath</span></span>

<span data-ttu-id="d2a52-175">Gibt einen Pfad der Element Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="d2a52-175">Specifies a path of the item property.</span></span>
<span data-ttu-id="d2a52-176">Im Gegensatz zum **Path**-Parameter wird der Wert des **LiteralPath**-Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d2a52-176">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="d2a52-177">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="d2a52-177">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="d2a52-178">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="d2a52-178">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="d2a52-179">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="d2a52-179">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValueLiteralPathSet, propertyPSObjectLiteralPathSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d2a52-180">-Name</span><span class="sxs-lookup"><span data-stu-id="d2a52-180">-Name</span></span>

<span data-ttu-id="d2a52-181">Gibt den Namen der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="d2a52-181">Specifies the name of the property.</span></span>

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

### <span data-ttu-id="d2a52-182">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d2a52-182">-PassThru</span></span>

<span data-ttu-id="d2a52-183">Gibt ein Objekt zurück, das die Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="d2a52-183">Returns an object that represents the item property.</span></span>
<span data-ttu-id="d2a52-184">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="d2a52-184">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d2a52-185">-Path</span><span class="sxs-lookup"><span data-stu-id="d2a52-185">-Path</span></span>

<span data-ttu-id="d2a52-186">Gibt den Pfad der Elemente mit der Eigenschaft an, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d2a52-186">Specifies the path of the items with the property to modify.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d2a52-187">-Type</span><span class="sxs-lookup"><span data-stu-id="d2a52-187">-Type</span></span>

<span data-ttu-id="d2a52-188">**Type** ist ein dynamischer Parameter, den der Registrierungs Anbieter dem `Set-ItemProperty` Cmdlet hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="d2a52-188">**Type** is a dynamic parameter that the Registry provider adds to the `Set-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="d2a52-189">Dieser Parameter funktioniert nur in den Registrierungs Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="d2a52-189">This parameter only works in the registry drives.</span></span>

<span data-ttu-id="d2a52-190">Gibt den Typ der Eigenschaft an, die von diesem Cmdlet hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d2a52-190">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="d2a52-191">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="d2a52-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d2a52-192">**String**: gibt eine NULL-terminierte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="d2a52-192">**String**: Specifies a null-terminated string.</span></span> <span data-ttu-id="d2a52-193">Entspricht **REG_SZ**.</span><span class="sxs-lookup"><span data-stu-id="d2a52-193">Equivalent to **REG_SZ**.</span></span>
- <span data-ttu-id="d2a52-194">**ExpandString**: gibt eine NULL-terminierte Zeichenfolge an, die nicht erweiterte Verweise auf Umgebungsvariablen enthält, die erweitert werden, wenn der Wert abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d2a52-194">**ExpandString**: Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="d2a52-195">Entspricht **REG_EXPAND_SZ**.</span><span class="sxs-lookup"><span data-stu-id="d2a52-195">Equivalent to **REG_EXPAND_SZ**.</span></span>
- <span data-ttu-id="d2a52-196">**Binary**: gibt Binärdaten in beliebiger Form an.</span><span class="sxs-lookup"><span data-stu-id="d2a52-196">**Binary**: Specifies binary data in any form.</span></span> <span data-ttu-id="d2a52-197">Entspricht **REG_BINARY**.</span><span class="sxs-lookup"><span data-stu-id="d2a52-197">Equivalent to **REG_BINARY**.</span></span>
- <span data-ttu-id="d2a52-198">**DWORD**: gibt eine 32-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="d2a52-198">**DWord**: Specifies a 32-bit binary number.</span></span> <span data-ttu-id="d2a52-199">Entspricht **REG_DWORD**.</span><span class="sxs-lookup"><span data-stu-id="d2a52-199">Equivalent to **REG_DWORD**.</span></span>
- <span data-ttu-id="d2a52-200">**MultiString**: gibt ein Array von auf NULL endenden Zeichen folgen an, die mit zwei NULL-Zeichen beendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2a52-200">**MultiString**: Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="d2a52-201">Entspricht **REG_MULTI_SZ**.</span><span class="sxs-lookup"><span data-stu-id="d2a52-201">Equivalent to **REG_MULTI_SZ**.</span></span>
- <span data-ttu-id="d2a52-202">**QWORD**: gibt eine 64-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="d2a52-202">**Qword**: Specifies a 64-bit binary number.</span></span> <span data-ttu-id="d2a52-203">Entspricht **REG_QWORD**.</span><span class="sxs-lookup"><span data-stu-id="d2a52-203">Equivalent to **REG_QWORD**.</span></span>
- <span data-ttu-id="d2a52-204">**Unknown**: gibt einen nicht unterstützten Registrierungs Datentyp an, z. b. **REG_RESOURCE_LIST**.</span><span class="sxs-lookup"><span data-stu-id="d2a52-204">**Unknown**: Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST**.</span></span>

```yaml
Type: RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d2a52-205">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="d2a52-205">-UseTransaction</span></span>

<span data-ttu-id="d2a52-206">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="d2a52-206">Includes the command in the active transaction.</span></span>
<span data-ttu-id="d2a52-207">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d2a52-207">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="d2a52-208">Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="d2a52-208">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2a52-209">-Value</span><span class="sxs-lookup"><span data-stu-id="d2a52-209">-Value</span></span>

<span data-ttu-id="d2a52-210">Gibt den Wert der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="d2a52-210">Specifies the value of the property.</span></span>

```yaml
Type: Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d2a52-211">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d2a52-211">-Confirm</span></span>

<span data-ttu-id="d2a52-212">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d2a52-212">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2a52-213">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d2a52-213">-WhatIf</span></span>

<span data-ttu-id="d2a52-214">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d2a52-214">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d2a52-215">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d2a52-215">The cmdlet is not run.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2a52-216">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d2a52-216">CommonParameters</span></span>

<span data-ttu-id="d2a52-217">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d2a52-217">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d2a52-218">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d2a52-218">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d2a52-219">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d2a52-219">INPUTS</span></span>

### <span data-ttu-id="d2a52-220">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="d2a52-220">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="d2a52-221">Sie können Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="d2a52-221">You can pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="d2a52-222">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d2a52-222">OUTPUTS</span></span>

### <span data-ttu-id="d2a52-223">None, System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="d2a52-223">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="d2a52-224">Dieses Cmdlet generiert ein **pscustomobject** -Objekt, das das geänderte Element darstellt, und den neuen Eigenschafts Wert, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="d2a52-224">This cmdlet generates a **PSCustomObject** object that represents the item that was changed and its new property value, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="d2a52-225">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="d2a52-225">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d2a52-226">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d2a52-226">NOTES</span></span>

<span data-ttu-id="d2a52-227">`Set-ItemProperty` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d2a52-227">`Set-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d2a52-228">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="d2a52-228">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d2a52-229">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d2a52-229">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d2a52-230">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d2a52-230">RELATED LINKS</span></span>

[<span data-ttu-id="d2a52-231">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2a52-231">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="d2a52-232">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2a52-232">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="d2a52-233">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2a52-233">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="d2a52-234">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2a52-234">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="d2a52-235">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2a52-235">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="d2a52-236">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2a52-236">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="d2a52-237">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d2a52-237">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)
