---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/unregister-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PackageSource
ms.openlocfilehash: 6ef89e9143fe8883bc98723d10775bf739fe72f9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597375"
---
# <span data-ttu-id="14b9c-102">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="14b9c-102">Unregister-PackageSource</span></span>

## <span data-ttu-id="14b9c-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="14b9c-103">SYNOPSIS</span></span>
<span data-ttu-id="14b9c-104">Entfernt eine registrierte Paketquelle.</span><span class="sxs-lookup"><span data-stu-id="14b9c-104">Removes a registered package source.</span></span>

## <span data-ttu-id="14b9c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14b9c-105">SYNTAX</span></span>

### <span data-ttu-id="14b9c-106">Sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="14b9c-106">SourceBySearch</span></span>

```
Unregister-PackageSource [[-Source] <String>] [-Location <String>] [-Credential <PSCredential>]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="14b9c-107">Sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="14b9c-107">SourceByInputObject</span></span>

```
Unregister-PackageSource -InputObject <PackageSource[]> [-Credential <PSCredential>] [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="14b9c-108">Nuget: sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="14b9c-108">NuGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="14b9c-109">Nuget: sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="14b9c-109">NuGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="14b9c-110">PowerShellGet: sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="14b9c-110">PowerShellGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="14b9c-111">PowerShellGet: sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="14b9c-111">PowerShellGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="14b9c-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14b9c-112">DESCRIPTION</span></span>

<span data-ttu-id="14b9c-113">Mit dem- `Unregister-PackageSource` Cmdlet wird eine registrierte Paketquelle entfernt.</span><span class="sxs-lookup"><span data-stu-id="14b9c-113">The `Unregister-PackageSource` cmdlet removes a registered package source.</span></span> <span data-ttu-id="14b9c-114">Paketquellen werden immer von einem Paketanbieter verwaltet.</span><span class="sxs-lookup"><span data-stu-id="14b9c-114">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="14b9c-115">Verwenden Sie das-Cmdlet, um Paketquellen zu suchen `Get-PackageSource` .</span><span class="sxs-lookup"><span data-stu-id="14b9c-115">To find package sources, use the `Get-PackageSource` cmdlet.</span></span>

## <span data-ttu-id="14b9c-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="14b9c-116">EXAMPLES</span></span>

### <span data-ttu-id="14b9c-117">Beispiel 1: Aufheben der Registrierung einer Paketquelle für den nuget-Anbieter</span><span class="sxs-lookup"><span data-stu-id="14b9c-117">Example 1: Unregister a package source for the Nuget provider</span></span>

<span data-ttu-id="14b9c-118">Mit dem- `Unregister-PackageSource` Cmdlet wird die Registrierung einer Paketquelle auf dem lokalen Computer aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="14b9c-118">The `Unregister-PackageSource` cmdlet unregisters a package source from the local computer.</span></span> <span data-ttu-id="14b9c-119">Der **Speicherort** und die **Anbieter** Parameter können verwendet werden, um die zu entfernende Quelle weiter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="14b9c-119">The **Location** and **Provider** parameters can be used to further specify the source to remove.</span></span>

```
PS> Unregister-PackageSource -Source MyNuGet
```

<span data-ttu-id="14b9c-120">Das `Unregister-PackageSource` Cmdlet verwendet den **Source** -Parameter, um anzugeben, welche Quelle entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="14b9c-120">The `Unregister-PackageSource` cmdlet uses the **Source** parameter to specify which source to remove.</span></span>

### <span data-ttu-id="14b9c-121">Beispiel 2: Verwenden eines packagesource-Objekts zum Aufheben der Registrierung eines Pakets</span><span class="sxs-lookup"><span data-stu-id="14b9c-121">Example 2: Use a PackageSource object to unregister a package</span></span>

<span data-ttu-id="14b9c-122">In diesem Beispiel werden `Get-PackageSource` und `Unregister-PackageSource` zum Aufheben der Registrierung einer Paketquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="14b9c-122">This example uses the `Get-PackageSource` and `Unregister-PackageSource` to unregister a package source.</span></span> <span data-ttu-id="14b9c-123">Das **packagesource** -Objekt wird in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="14b9c-123">The **PackageSource** object is stored in a variable.</span></span>

```
PS> $pkgsource = Get-PackageSource -Name MyNuGet
PS> Unregister-PackageSource -InputObject $pkgsource
```

<span data-ttu-id="14b9c-124">Die `$pkgsource` Variable speichert die vom Cmdlet erstellte **packagesource** `Get-PackageSource` .</span><span class="sxs-lookup"><span data-stu-id="14b9c-124">The `$pkgsource` variable stores the **PackageSource** created by the `Get-PackageSource` cmdlet.</span></span>
<span data-ttu-id="14b9c-125">`Unregister-PackageSource` verwendet `$pkgsource` als Eingabe für den **Inputobject** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="14b9c-125">`Unregister-PackageSource` uses the `$pkgsource` as input to the **InputObject** parameter.</span></span>

<span data-ttu-id="14b9c-126">Als Alternative `Unregister-PackageSource` kann das Cmdlet einen Wert für den **Inputobject** -Parameter angeben:</span><span class="sxs-lookup"><span data-stu-id="14b9c-126">As an alternative, the `Unregister-PackageSource` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Unregister-PackageSource -InputObject ( Get-PackageSource -Name MyNuGet )`

## <span data-ttu-id="14b9c-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14b9c-127">PARAMETERS</span></span>

### <span data-ttu-id="14b9c-128">-Configfile</span><span class="sxs-lookup"><span data-stu-id="14b9c-128">-ConfigFile</span></span>

<span data-ttu-id="14b9c-129">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="14b9c-129">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-130">-Credential</span><span class="sxs-lookup"><span data-stu-id="14b9c-130">-Credential</span></span>

<span data-ttu-id="14b9c-131">Gibt ein Benutzerkonto an, das über die Berechtigung zum Zugreifen auf den Computer und zum Ausführen von Befehlen verfügt.</span><span class="sxs-lookup"><span data-stu-id="14b9c-131">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="14b9c-132">Geben Sie einen Benutzernamen ein, z. b. **USER01**, **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="14b9c-132">Type a user name, such as **User01**, **Domain01\User01**, or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="14b9c-133">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="14b9c-133">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="14b9c-134">Wenn der **Credential** -Parameter nicht angegeben wird, wird das aktuelle Benutzerkonto verwendet.</span><span class="sxs-lookup"><span data-stu-id="14b9c-134">When the **Credential** parameter isn't specified, the current user account is used.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-135">-Force</span><span class="sxs-lookup"><span data-stu-id="14b9c-135">-Force</span></span>

<span data-ttu-id="14b9c-136">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="14b9c-136">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="14b9c-137">Überschreibt Einschränkungen, die eine erfolgreiche Ausführung verhindern `Unregister-PackageSource` , mit Ausnahme der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="14b9c-137">Overrides restrictions that prevent `Unregister-PackageSource` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="14b9c-138">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="14b9c-138">-ForceBootstrap</span></span>

<span data-ttu-id="14b9c-139">Gibt an, dass `Unregister-PackageSource` **packagemanagement** zwingt, den Paketanbieter für die angegebene Paketquelle automatisch zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="14b9c-139">Indicates that `Unregister-PackageSource` forces **PackageManagement** to automatically uninstall the package provider for the specified package source.</span></span>

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

### <span data-ttu-id="14b9c-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="14b9c-140">-InputObject</span></span>

<span data-ttu-id="14b9c-141">Akzeptiert Pipeline Eingaben, die das **packagesource** -Objekt aus dem `Get-PackageSource` Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="14b9c-141">Accepts pipeline input that specifies the **PackageSource** object from the `Get-PackageSource` cmdlet.</span></span> <span data-ttu-id="14b9c-142">**Inputobject** akzeptiert das **packagesource** -Objekt als `Get-PackageSource` Wert oder eine Variable, die das Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="14b9c-142">**InputObject** accepts the **PackageSource** object as a `Get-PackageSource` value or a variable that contains the object.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource[]
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-143">-Location</span><span class="sxs-lookup"><span data-stu-id="14b9c-143">-Location</span></span>

<span data-ttu-id="14b9c-144">Gibt den Speicherort an, auf den eine Paketquelle verweist.</span><span class="sxs-lookup"><span data-stu-id="14b9c-144">Specifies the location to which a package source points.</span></span> <span data-ttu-id="14b9c-145">Der Wert dieses Parameters kann ein URI, ein Dateipfad oder ein beliebiges anderes Zielformat sein, das vom Paketanbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="14b9c-145">The value of this parameter can be a URI, a file path, or any other destination format that is supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-146">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="14b9c-146">-PackageManagementProvider</span></span>

<span data-ttu-id="14b9c-147">Gibt den **packagemanagement** -Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="14b9c-147">Specifies the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-148">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="14b9c-148">-ProviderName</span></span>

<span data-ttu-id="14b9c-149">Gibt den Anbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="14b9c-149">Specifies the provider name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-150">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="14b9c-150">-PublishLocation</span></span>

<span data-ttu-id="14b9c-151">Gibt den Veröffentlichungs Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="14b9c-151">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-152">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="14b9c-152">-ScriptPublishLocation</span></span>

<span data-ttu-id="14b9c-153">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="14b9c-153">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-154">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="14b9c-154">-ScriptSourceLocation</span></span>

<span data-ttu-id="14b9c-155">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="14b9c-155">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-156">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="14b9c-156">-SkipValidate</span></span>

<span data-ttu-id="14b9c-157">Ein Schalter, der die Validierung der Anmelde Informationen einer Paketquelle überspringt.</span><span class="sxs-lookup"><span data-stu-id="14b9c-157">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-158">-Source</span><span class="sxs-lookup"><span data-stu-id="14b9c-158">-Source</span></span>

<span data-ttu-id="14b9c-159">Gibt den anzeigen amen der Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="14b9c-159">Specifies the friendly name of the package source.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14b9c-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="14b9c-160">-Confirm</span></span>

<span data-ttu-id="14b9c-161">Fordert Sie zur Bestätigung auf, bevor `Unregister-PackageSource` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="14b9c-161">Prompts you for confirmation before `Unregister-PackageSource` is run.</span></span>

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

### <span data-ttu-id="14b9c-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="14b9c-162">-WhatIf</span></span>

<span data-ttu-id="14b9c-163">Zeigt, was geschieht, wenn das `Unregister-PackageSource` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="14b9c-163">Shows what would happen if `Unregister-PackageSource` cmdlet is run.</span></span> <span data-ttu-id="14b9c-164">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="14b9c-164">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="14b9c-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="14b9c-165">CommonParameters</span></span>

<span data-ttu-id="14b9c-166">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="14b9c-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14b9c-167">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="14b9c-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="14b9c-168">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="14b9c-168">INPUTS</span></span>

### <span data-ttu-id="14b9c-169">`Unregister-PackageSource` akzeptiert **packagesource** -Objekte aus der Pipeline als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="14b9c-169">`Unregister-PackageSource` accepts **PackageSource** objects from the pipeline as input.</span></span>

## <span data-ttu-id="14b9c-170">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="14b9c-170">OUTPUTS</span></span>

### <span data-ttu-id="14b9c-171">`Unregister-PackageSource` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="14b9c-171">`Unregister-PackageSource` doesn't generate any output.</span></span>

## <span data-ttu-id="14b9c-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="14b9c-172">NOTES</span></span>

<span data-ttu-id="14b9c-173">Durch das Einschließen eines Paket Anbieters in einen Befehl können dynamische Parameter für ein Cmdlet verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="14b9c-173">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="14b9c-174">Dynamische Parameter sind für einen Paketanbieter spezifisch.</span><span class="sxs-lookup"><span data-stu-id="14b9c-174">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="14b9c-175">Das `Get-Help` -Cmdlet listet die Parametersätze eines Cmdlets auf und schließt den Parametersatz des Anbieters ein.</span><span class="sxs-lookup"><span data-stu-id="14b9c-175">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span>

## <span data-ttu-id="14b9c-176">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="14b9c-176">RELATED LINKS</span></span>

[<span data-ttu-id="14b9c-177">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="14b9c-177">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="14b9c-178">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="14b9c-178">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="14b9c-179">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="14b9c-179">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="14b9c-180">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="14b9c-180">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="14b9c-181">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="14b9c-181">Set-PackageSource</span></span>](Set-PackageSource.md)

