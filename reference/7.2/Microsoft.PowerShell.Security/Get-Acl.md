---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-acl?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Acl
ms.openlocfilehash: ed458e7f58ebb61611e2fd9e60430a7330087e8a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602948"
---
# <span data-ttu-id="6301d-102">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="6301d-102">Get-Acl</span></span>

## <span data-ttu-id="6301d-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6301d-103">SYNOPSIS</span></span>
<span data-ttu-id="6301d-104">Ruft die Sicherheitsbeschreibung für eine Ressource ab, z. B. eine Datei oder einen Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="6301d-104">Gets the security descriptor for a resource, such as a file or registry key.</span></span>

## <span data-ttu-id="6301d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6301d-105">SYNTAX</span></span>

### <span data-ttu-id="6301d-106">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="6301d-106">ByPath (Default)</span></span>

```
Get-Acl [[-Path] <String[]>] [-Audit] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="6301d-107">Byinputobject</span><span class="sxs-lookup"><span data-stu-id="6301d-107">ByInputObject</span></span>

```
Get-Acl -InputObject <PSObject> [-Audit] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6301d-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="6301d-108">ByLiteralPath</span></span>

```
Get-Acl [-LiteralPath <String[]>] [-Audit] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="6301d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6301d-109">DESCRIPTION</span></span>

<span data-ttu-id="6301d-110">Mit dem- `Get-Acl` Cmdlet werden Objekte abgerufen, die die Sicherheits Beschreibung einer Datei oder Ressource darstellen.</span><span class="sxs-lookup"><span data-stu-id="6301d-110">The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="6301d-111">Die Sicherheitsbeschreibung enthält die Zugriffssteuerungslisten (Access Control Lists, ACLs) der Ressource.</span><span class="sxs-lookup"><span data-stu-id="6301d-111">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="6301d-112">Die ACL gibt die Berechtigungen an, über die Benutzer und Benutzergruppen für den Zugriff auf die Ressource verfügen.</span><span class="sxs-lookup"><span data-stu-id="6301d-112">The ACL specifies the permissions that users and user groups have to access the resource.</span></span>

<span data-ttu-id="6301d-113">Ab Windows PowerShell 3,0 können Sie den **Inputobject** -Parameter von verwenden, `Get-Acl` um die Sicherheits Beschreibung von Objekten mit einem Pfad zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6301d-113">Beginning in Windows PowerShell 3.0, you can use the **InputObject** parameter of `Get-Acl` to get the security descriptor of objects that do not have a path.</span></span>

## <span data-ttu-id="6301d-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6301d-114">EXAMPLES</span></span>

### <span data-ttu-id="6301d-115">Beispiel 1: erhalten einer ACL für einen Ordner</span><span class="sxs-lookup"><span data-stu-id="6301d-115">Example 1- Get an ACL for a folder</span></span>

<span data-ttu-id="6301d-116">In diesem Beispiel wird die Sicherheits Beschreibung des `C:\Windows` Verzeichnisses abgerufen.</span><span class="sxs-lookup"><span data-stu-id="6301d-116">This example gets the security descriptor of the `C:\Windows` directory.</span></span>

```powershell
Get-Acl C:\Windows
```

### <span data-ttu-id="6301d-117">Beispiel 2: erhalten einer ACL für einen Ordner mithilfe von Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="6301d-117">Example 2 - Get an ACL for a folder using wildcards</span></span>

<span data-ttu-id="6301d-118">In diesem Beispiel werden der PowerShell-Pfad und die SDDL für alle `.log` Dateien im `C:\Windows` Verzeichnis abgerufen, deren Namen mit beginnen `s` .</span><span class="sxs-lookup"><span data-stu-id="6301d-118">This example gets the PowerShell path and SDDL for all of the `.log` files in the `C:\Windows` directory whose names begin with `s`.</span></span>

```powershell
Get-Acl C:\Windows\s*.log | Format-List -Property PSPath, Sddl
```

<span data-ttu-id="6301d-119">Der Befehl verwendet das `Get-Acl` Cmdlet, um Objekte zu erhalten, die die Sicherheits Deskriptoren der einzelnen Protokolldateien darstellen.</span><span class="sxs-lookup"><span data-stu-id="6301d-119">The command uses the `Get-Acl` cmdlet to get objects representing the security descriptors of each log file.</span></span> <span data-ttu-id="6301d-120">Er verwendet einen Pipeline Operator ( `|` ), um die Ergebnisse an das `Format-List` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="6301d-120">It uses a pipeline operator (`|`) to send the results to the `Format-List` cmdlet.</span></span> <span data-ttu-id="6301d-121">Der Befehl verwendet den **Property** -Parameter von `Format-List` , um nur die **pspath** -und **SDDL** -Eigenschaften der einzelnen Sicherheits deskriptorobjekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6301d-121">The command uses the **Property** parameter of `Format-List` to display only the **PsPath** and **SDDL** properties of each security descriptor object.</span></span>

<span data-ttu-id="6301d-122">Listen werden häufig in PowerShell verwendet, da lange Werte in Tabellen abgeschnitten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6301d-122">Lists are often used in PowerShell, because long values appear truncated in tables.</span></span>

<span data-ttu-id="6301d-123">Die **SDDL**-Werte sind für Systemadministratoren hilfreich, da es sich dabei um einfache Textzeichenfolgen handelt, die alle Informationen in der Sicherheitsbeschreibung enthalten.</span><span class="sxs-lookup"><span data-stu-id="6301d-123">The **SDDL** values are valuable to system administrators, because they are simple text strings that contain all of the information in the security descriptor.</span></span> <span data-ttu-id="6301d-124">Daher können sie einfach übergeben und gespeichert und bei Bedarf analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="6301d-124">As such, they are easy to pass and store, and they can be parsed when needed.</span></span>

### <span data-ttu-id="6301d-125">Beispiel 3: Abruf der Anzahl der Überwachungs Einträge für eine ACL</span><span class="sxs-lookup"><span data-stu-id="6301d-125">Example 3 - Get count of Audit entries for an ACL</span></span>

<span data-ttu-id="6301d-126">In diesem Beispiel werden die Sicherheits Deskriptoren der `.log` Dateien im Verzeichnis abgerufen, `C:\Windows` deren Namen mit beginnen `s` .</span><span class="sxs-lookup"><span data-stu-id="6301d-126">This example gets the security descriptors of the `.log` files in the `C:\Windows` directory whose names begin with `s`.</span></span>

```powershell
Get-Acl C:\Windows\s*.log -Audit | ForEach-Object { $_.Audit.Count }
```

<span data-ttu-id="6301d-127">Mit dem **Audit**-Parameter werden die Überwachungsdatensätze aus der SACL in der Sicherheitsbeschreibung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="6301d-127">It uses the **Audit** parameter to get the audit records from the SACL in the security descriptor.</span></span>
<span data-ttu-id="6301d-128">Anschließend wird mit dem `ForEach-Object` Cmdlet die Anzahl der Überwachungsdaten Sätze gezählt, die den einzelnen Dateien zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6301d-128">Then it uses the `ForEach-Object` cmdlet to count the number of audit records associated with each file.</span></span> <span data-ttu-id="6301d-129">Das Ergebnis ist eine Liste von Zahlen, die die Anzahl der Überwachungsdatensätze für jede Protokolldatei darstellen.</span><span class="sxs-lookup"><span data-stu-id="6301d-129">The result is a list of numbers representing the number of audit records for each log file.</span></span>

### <span data-ttu-id="6301d-130">Beispiel 4: erhalten einer Zugriffs Steuerungs Liste (ACL) für einen Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="6301d-130">Example 4 - Get an ACL for a registry key</span></span>

<span data-ttu-id="6301d-131">In diesem Beispiel wird das- `Get-Acl` Cmdlet verwendet, um die Sicherheits Beschreibung des Control-unter Schlüssels ( `HKLM:\SYSTEM\CurrentControlSet\Control` ) der Registrierung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6301d-131">This example uses the `Get-Acl` cmdlet to get the security descriptor of the Control subkey (`HKLM:\SYSTEM\CurrentControlSet\Control`) of the registry.</span></span>

```powershell
Get-Acl -Path HKLM:\System\CurrentControlSet\Control | Format-List
```

<span data-ttu-id="6301d-132">Der **path** -Parameter gibt den Steuerelement Unterschlüssel an.</span><span class="sxs-lookup"><span data-stu-id="6301d-132">The **Path** parameter specifies the Control subkey.</span></span> <span data-ttu-id="6301d-133">Der Pipeline Operator ( `|` ) übergibt die Sicherheits Beschreibung, die `Get-Acl` an den `Format-List` Befehl gelangt, der die Eigenschaften der Sicherheits Beschreibung als Liste formatiert, sodass Sie leicht lesbar sind.</span><span class="sxs-lookup"><span data-stu-id="6301d-133">The pipeline operator (`|`) passes the security descriptor that `Get-Acl` gets to the `Format-List` command, which formats the properties of the security descriptor as a list so that they are easy to read.</span></span>

### <span data-ttu-id="6301d-134">Beispiel 5: erhalten einer ACL mithilfe von **Inputobject**</span><span class="sxs-lookup"><span data-stu-id="6301d-134">Example 5 - Get an ACL using **InputObject**</span></span>

<span data-ttu-id="6301d-135">In diesem Beispiel wird der **Inputobject** -Parameter von verwendet `Get-Acl` , um die Sicherheits Beschreibung für ein Speichersubsystem-Objekt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6301d-135">This example uses the **InputObject** parameter of `Get-Acl` to get the security descriptor of a storage subsystem object.</span></span>

```powershell
Get-Acl -InputObject (Get-StorageSubSystem -Name S087)
```

## <span data-ttu-id="6301d-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6301d-136">PARAMETERS</span></span>

### <span data-ttu-id="6301d-137">-Überprüfung</span><span class="sxs-lookup"><span data-stu-id="6301d-137">-Audit</span></span>

<span data-ttu-id="6301d-138">Ruft die Überwachungsdaten für die Sicherheitsbeschreibung aus der System-Zugriffssteuerungsliste (SACL) ab.</span><span class="sxs-lookup"><span data-stu-id="6301d-138">Gets the audit data for the security descriptor from the system access control list (SACL).</span></span>

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

### <span data-ttu-id="6301d-139">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="6301d-139">-Exclude</span></span>

<span data-ttu-id="6301d-140">Lässt die angegebenen Elemente aus.</span><span class="sxs-lookup"><span data-stu-id="6301d-140">Omits the specified items.</span></span> <span data-ttu-id="6301d-141">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6301d-141">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6301d-142">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="6301d-142">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="6301d-143">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="6301d-143">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="6301d-144">-Filter</span><span class="sxs-lookup"><span data-stu-id="6301d-144">-Filter</span></span>

<span data-ttu-id="6301d-145">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="6301d-145">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="6301d-146">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6301d-146">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6301d-147">Die Syntax des Filters einschließlich der Verwendung von Platzhaltern ist vom Anbieter abhängig.</span><span class="sxs-lookup"><span data-stu-id="6301d-147">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="6301d-148">Filter sind effizienter als andere Parameter, da Sie vom Anbieter beim Abrufen der Objekte angewendet werden, anstatt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="6301d-148">Filters are more efficient than other parameters, because the provider applies them when getting the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="6301d-149">-Include</span><span class="sxs-lookup"><span data-stu-id="6301d-149">-Include</span></span>

<span data-ttu-id="6301d-150">Ruft nur die angegebenen Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="6301d-150">Gets only the specified items.</span></span> <span data-ttu-id="6301d-151">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6301d-151">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6301d-152">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="6301d-152">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="6301d-153">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="6301d-153">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="6301d-154">-Path</span><span class="sxs-lookup"><span data-stu-id="6301d-154">-Path</span></span>

<span data-ttu-id="6301d-155">Gibt den Pfad zu einer Ressource an.</span><span class="sxs-lookup"><span data-stu-id="6301d-155">Specifies the path to a resource.</span></span> <span data-ttu-id="6301d-156">`Get-Acl` Ruft die Sicherheits Beschreibung der Ressource ab, die durch den Pfad angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6301d-156">`Get-Acl` gets the security descriptor of the resource indicated by the path.</span></span> <span data-ttu-id="6301d-157">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="6301d-157">Wildcards are permitted.</span></span> <span data-ttu-id="6301d-158">Wenn Sie den **path** -Parameter weglassen, ruft `Get-Acl` die Sicherheits Beschreibung des aktuellen Verzeichnisses ab.</span><span class="sxs-lookup"><span data-stu-id="6301d-158">If you omit the **Path** parameter, `Get-Acl` gets the security descriptor of the current directory.</span></span>

<span data-ttu-id="6301d-159">Der Parametername (Path) ist optional.</span><span class="sxs-lookup"><span data-stu-id="6301d-159">The parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="6301d-160">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6301d-160">-InputObject</span></span>

<span data-ttu-id="6301d-161">Ruft die Sicherheitsbeschreibung für das angegebene Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="6301d-161">Gets the security descriptor for the specified object.</span></span> <span data-ttu-id="6301d-162">Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl ein, mit dem das Objekt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6301d-162">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="6301d-163">Ein Objekt, das kein Pfad ist, kann nicht an übergeben werden `Get-Acl` .</span><span class="sxs-lookup"><span data-stu-id="6301d-163">You cannot pipe an object, other than a path, to `Get-Acl`.</span></span> <span data-ttu-id="6301d-164">Verwenden Sie stattdessen den **InputObject**-Parameter explizit im Befehl.</span><span class="sxs-lookup"><span data-stu-id="6301d-164">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="6301d-165">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6301d-165">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6301d-166">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="6301d-166">-LiteralPath</span></span>

<span data-ttu-id="6301d-167">Gibt den Pfad zu einer Ressource an.</span><span class="sxs-lookup"><span data-stu-id="6301d-167">Specifies the path to a resource.</span></span> <span data-ttu-id="6301d-168">Im Gegensatz zu **Path** wird der Wert des **LiteralPath**-Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6301d-168">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="6301d-169">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="6301d-169">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="6301d-170">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="6301d-170">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="6301d-171">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="6301d-171">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="6301d-172">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6301d-172">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6301d-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6301d-173">CommonParameters</span></span>

<span data-ttu-id="6301d-174">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6301d-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6301d-175">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6301d-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6301d-176">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6301d-176">INPUTS</span></span>

### <span data-ttu-id="6301d-177">System.String</span><span class="sxs-lookup"><span data-stu-id="6301d-177">System.String</span></span>

<span data-ttu-id="6301d-178">Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Get-Acl` .</span><span class="sxs-lookup"><span data-stu-id="6301d-178">You can pipe a string that contains a path to `Get-Acl`.</span></span>

## <span data-ttu-id="6301d-179">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6301d-179">OUTPUTS</span></span>

### <span data-ttu-id="6301d-180">System. Security. AccessControl. File Security, System. Security. AccessControl. Director ysecurity, System. Security. AccessControl. RegistrySecurity</span><span class="sxs-lookup"><span data-stu-id="6301d-180">System.Security.AccessControl.FileSecurity, System.Security.AccessControl.DirectorySecurity, System.Security.AccessControl.RegistrySecurity</span></span>

<span data-ttu-id="6301d-181">`Get-Acl` Gibt ein-Objekt zurück, das die Abbild-ACLs darstellt.</span><span class="sxs-lookup"><span data-stu-id="6301d-181">`Get-Acl` returns an object that represents the ACLs that it gets.</span></span> <span data-ttu-id="6301d-182">Der Objekttyp richtet sich nach der ACL-Typ.</span><span class="sxs-lookup"><span data-stu-id="6301d-182">The object type depends upon the ACL type.</span></span>

## <span data-ttu-id="6301d-183">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6301d-183">NOTES</span></span>

<span data-ttu-id="6301d-184">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6301d-184">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="6301d-185">Standardmäßig `Get-Acl` zeigt den PowerShell-Pfad der Ressource ( `<provider>::<resource-path>` ), den Besitzer der Ressource und "Access", eine Liste (Array) der Zugriffs Steuerungs Einträge in der freigegebenen Zugriffs Steuerungs Liste (DACL) für die Ressource an.</span><span class="sxs-lookup"><span data-stu-id="6301d-185">By default, `Get-Acl` displays the PowerShell path to the resource (`<provider>::<resource-path>`), the owner of the resource, and "Access", a list (array) of the access control entries in the discretionary access control list (DACL) for the resource.</span></span> <span data-ttu-id="6301d-186">Die DACL-Liste wird durch den Besitzer der Ressource gesteuert.</span><span class="sxs-lookup"><span data-stu-id="6301d-186">The DACL list is controlled by the resource owner.</span></span>

<span data-ttu-id="6301d-187">Wenn Sie das Ergebnis als Liste ( `Get-Acl | Format-List` ), zusätzlich zum Pfad, Besitzer und der Zugriffsliste formatieren, zeigt PowerShell die folgenden Eigenschaften und Eigenschaftswerte an:</span><span class="sxs-lookup"><span data-stu-id="6301d-187">When you format the result as a list, (`Get-Acl | Format-List`), in addition to the path, owner, and access list, PowerShell displays the following properties and property values:</span></span>

- <span data-ttu-id="6301d-188">**Gruppe**: die Sicherheitsgruppe des Besitzers.</span><span class="sxs-lookup"><span data-stu-id="6301d-188">**Group**: The security group of the owner.</span></span>
- <span data-ttu-id="6301d-189">**Audit**: eine Liste (Array) der Einträge in der System-Zugriffs Steuerungs Liste (SACL).</span><span class="sxs-lookup"><span data-stu-id="6301d-189">**Audit**:  A list (array) of entries in the system access control list (SACL).</span></span> <span data-ttu-id="6301d-190">Die SACL gibt die Arten von Zugriffsversuchen an, für die Windows Überwachungsdatensätze generiert.</span><span class="sxs-lookup"><span data-stu-id="6301d-190">The SACL specifies the types of access attempts for which Windows generates audit records.</span></span>
- <span data-ttu-id="6301d-191">**SDDL**: die Sicherheits Beschreibung der Ressource, die in einer einzelnen Text Zeichenfolge im Format der Sicherheits Deskriptor-Definitions Sprache angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6301d-191">**Sddl**: The security descriptor of the resource displayed in a single text string in Security Descriptor Definition Language format.</span></span> <span data-ttu-id="6301d-192">PowerShell verwendet die **gezddlform** -Methode von Sicherheits Deskriptoren, um diese Daten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6301d-192">PowerShell uses the **GetSddlForm** method of security descriptors to get this data.</span></span>

<span data-ttu-id="6301d-193">Da `Get-Acl` von den Dateisystem-und Registrierungs Anbietern unterstützt wird, können Sie verwenden, `Get-Acl` um die ACL von Dateisystemobjekten, wie z. b. Dateien und Verzeichnissen, und Registrierungs Objekten, wie z. b. Registrierungsschlüssel und Einträge, anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6301d-193">Because `Get-Acl` is supported by the file system and registry providers, you can use `Get-Acl` to view the ACL of file system objects, such as files and directories, and registry objects, such as registry keys and entries.</span></span>

## <span data-ttu-id="6301d-194">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6301d-194">RELATED LINKS</span></span>

[<span data-ttu-id="6301d-195">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="6301d-195">Set-Acl</span></span>](Set-Acl.md)
