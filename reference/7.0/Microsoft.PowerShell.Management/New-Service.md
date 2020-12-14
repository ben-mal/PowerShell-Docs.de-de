---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 7ba9bf66295bcbc2d8f7b7f94007b3fb673882fb
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890973"
---
# <span data-ttu-id="2087d-102">New-Service</span><span class="sxs-lookup"><span data-stu-id="2087d-102">New-Service</span></span>

## <span data-ttu-id="2087d-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2087d-103">SYNOPSIS</span></span>
<span data-ttu-id="2087d-104">Erstellt einen neuen Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="2087d-104">Creates a new Windows service.</span></span>

## <span data-ttu-id="2087d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2087d-105">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-SecurityDescriptorSddl <String>] [-StartupType <ServiceStartupType>] [-Credential <PSCredential>]
 [-DependsOn <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2087d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2087d-106">DESCRIPTION</span></span>

<span data-ttu-id="2087d-107">`New-Service`Mit dem-Cmdlet wird ein neuer Eintrag für einen Windows-Dienst in der Registrierung und in der Dienst Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="2087d-107">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="2087d-108">Ein neuer Dienst erfordert eine ausführbare Datei, die während des Dienstanbieter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2087d-108">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="2087d-109">Mit den Parametern dieses Cmdlets können Sie den Anzeigenamen, die Beschreibung, den Starttyp und die Abhängigkeiten des Diensts festlegen.</span><span class="sxs-lookup"><span data-stu-id="2087d-109">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="2087d-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2087d-110">EXAMPLES</span></span>

### <span data-ttu-id="2087d-111">Beispiel 1: Erstellen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="2087d-111">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
```

<span data-ttu-id="2087d-112">Dieser Befehl erstellt einen Dienst mit dem Namen "TestService".</span><span class="sxs-lookup"><span data-stu-id="2087d-112">This command creates a service named TestService.</span></span>

### <span data-ttu-id="2087d-113">Beispiel 2: Erstellen eines diensnamens, der Beschreibung, Starttyp und Anzeige Name enthält</span><span class="sxs-lookup"><span data-stu-id="2087d-113">Example 2: Create a service that includes description, startup type, and display name</span></span>

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

<span data-ttu-id="2087d-114">Dieser Befehl erstellt einen Dienst mit dem Namen "TestService".</span><span class="sxs-lookup"><span data-stu-id="2087d-114">This command creates a service named TestService.</span></span> <span data-ttu-id="2087d-115">Er verwendet die Parameter von, `New-Service` um eine Beschreibung, einen Starttyp und den anzeigen Amen für den neuen Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2087d-115">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="2087d-116">Beispiel 3: Anzeigen des neuen Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="2087d-116">Example 3: View the new service</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service -Filter "Name='testservice'"
```

```Output
ExitCode  : 0
Name      : testservice
ProcessId : 0
StartMode : Auto
State     : Stopped
Status    : OK
```

<span data-ttu-id="2087d-117">Dieser Befehl verwendet `Get-CimInstance` , um das **Win32_Service** -Objekt für den neuen Dienst zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2087d-117">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="2087d-118">Dieses Objekt enthält den Startmodus und die Dienstbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="2087d-118">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="2087d-119">Beispiel 4: Festlegen des securitydescriptors eines Dienstanbieter bei der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="2087d-119">Example 4: Set the SecurityDescriptor of a service when creating.</span></span>

<span data-ttu-id="2087d-120">In diesem Beispiel wird der **securityDescriptor** des erstellten Dienstanbieter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2087d-120">This example adds the **SecurityDescriptor** of the service being created.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
$params = @{
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
  SecurityDescriptorSddl = $SDDL
}
New-Service @params
```

<span data-ttu-id="2087d-121">Der **securityDescriptor** wird in der `$SDDLToSet` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2087d-121">The **SecurityDescriptor** is stored in the `$SDDLToSet` variable.</span></span> <span data-ttu-id="2087d-122">Der **securitydescriptorsddl** -Parameter verwendet `$SDDL` , um den **securityDescriptor** des neuen Dienstanbieter festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2087d-122">The **SecurityDescriptorSddl** parameter uses `$SDDL` to set the **SecurityDescriptor** of the new service.</span></span>

## <span data-ttu-id="2087d-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2087d-123">PARAMETERS</span></span>

### <span data-ttu-id="2087d-124">-Binarypathname</span><span class="sxs-lookup"><span data-stu-id="2087d-124">-BinaryPathName</span></span>

<span data-ttu-id="2087d-125">Gibt den Pfad der ausführbaren Datei für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="2087d-125">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="2087d-126">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2087d-126">This parameter is required.</span></span>

<span data-ttu-id="2087d-127">Der voll qualifizierte Pfad der Dienst Binärdatei.</span><span class="sxs-lookup"><span data-stu-id="2087d-127">The fully qualified path to the service binary file.</span></span> <span data-ttu-id="2087d-128">Wenn der Pfad ein Leerzeichen enthält, muss er in Anführungszeichen eingeschlossen werden, damit er ordnungsgemäß interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="2087d-128">If the path contains a space, it must be quoted so that it is correctly interpreted.</span></span> <span data-ttu-id="2087d-129">Beispielsweise muss `d:\my share\myservice.exe` als angegeben werden `'"d:\my share\myservice.exe"'` .</span><span class="sxs-lookup"><span data-stu-id="2087d-129">For example, `d:\my share\myservice.exe` should be specified as `'"d:\my share\myservice.exe"'`.</span></span>

<span data-ttu-id="2087d-130">Der Pfad kann auch Argumente für einen automatischen Start Dienst enthalten.</span><span class="sxs-lookup"><span data-stu-id="2087d-130">The path can also include arguments for an auto-start service.</span></span> <span data-ttu-id="2087d-131">Beispielsweise `'"d:\myshare\myservice.exe arg1 arg2"'`.</span><span class="sxs-lookup"><span data-stu-id="2087d-131">For example, `'"d:\myshare\myservice.exe arg1 arg2"'`.</span></span> <span data-ttu-id="2087d-132">Diese Argumente werden an den Dienst Einstiegspunkt übermittelt.</span><span class="sxs-lookup"><span data-stu-id="2087d-132">These arguments are passed to the service entry point.</span></span>

<span data-ttu-id="2087d-133">Weitere Informationen finden Sie unter dem **lpbinarypathname** -Parameter der " [feateservicew](/windows/win32/api/winsvc/nf-winsvc-createservicew) "-API.</span><span class="sxs-lookup"><span data-stu-id="2087d-133">For more information, see the **lpBinaryPathName** parameter of [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) API.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2087d-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="2087d-134">-Credential</span></span>

<span data-ttu-id="2087d-135">Gibt das Konto an, das vom Dienst als [Dienst Anmelde Konto](/windows/desktop/ad/about-service-logon-accounts)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2087d-135">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="2087d-136">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="2087d-136">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2087d-137">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="2087d-137">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="2087d-138">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2087d-138">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="2087d-139">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="2087d-139">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="2087d-140">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="2087d-140">-DependsOn</span></span>

<span data-ttu-id="2087d-141">Gibt die Namen anderer Dienste an, von denen der neue Dienst abhängt.</span><span class="sxs-lookup"><span data-stu-id="2087d-141">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="2087d-142">Trennen Sie zum Eingeben mehrerer Dienstnamen die Namen durch Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="2087d-142">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="2087d-143">-Description</span><span class="sxs-lookup"><span data-stu-id="2087d-143">-Description</span></span>

<span data-ttu-id="2087d-144">Gibt eine Beschreibung des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="2087d-144">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="2087d-145">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="2087d-145">-DisplayName</span></span>

<span data-ttu-id="2087d-146">Gibt einen Anzeigenamen für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="2087d-146">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="2087d-147">-Name</span><span class="sxs-lookup"><span data-stu-id="2087d-147">-Name</span></span>

<span data-ttu-id="2087d-148">Gibt den Namen des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="2087d-148">Specifies the name of the service.</span></span> <span data-ttu-id="2087d-149">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2087d-149">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2087d-150">-StartupType</span><span class="sxs-lookup"><span data-stu-id="2087d-150">-StartupType</span></span>

<span data-ttu-id="2087d-151">Legt den Starttyp des Diensts fest.</span><span class="sxs-lookup"><span data-stu-id="2087d-151">Sets the startup type of the service.</span></span> <span data-ttu-id="2087d-152">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="2087d-152">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2087d-153">**Automatisch** : der Dienst wurde gestartet oder vom Betriebssystem beim Systemstart gestartet.</span><span class="sxs-lookup"><span data-stu-id="2087d-153">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="2087d-154">Wenn ein automatisch gestarteter Dienst von einem manuell gestarteten Dienst abhängig ist, wird der manuell gestartete Dienst beim Systemstart ebenfalls automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="2087d-154">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="2087d-155">**Automaticdelayedstart** : startet kurz nach dem Systemstart.</span><span class="sxs-lookup"><span data-stu-id="2087d-155">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="2087d-156">**Deaktiviert** : der Dienst ist deaktiviert und kann nicht von einem Benutzer oder einer Anwendung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="2087d-156">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="2087d-157">**Invalidvalue** : dieser Wert wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2087d-157">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="2087d-158">Die Verwendung dieses Werts führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="2087d-158">Using this value results in an error.</span></span>
- <span data-ttu-id="2087d-159">**Manuell: der** Dienst wird nur manuell von einem Benutzer, über den Dienststeuerungs-Manager oder durch eine Anwendung gestartet.</span><span class="sxs-lookup"><span data-stu-id="2087d-159">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="2087d-160">Der Standardwert ist **automatisch**.</span><span class="sxs-lookup"><span data-stu-id="2087d-160">The default value is **Automatic**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Disabled, AutomaticDelayedStart, InvalidValue

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2087d-161">-SecurityDescriptor SDDL</span><span class="sxs-lookup"><span data-stu-id="2087d-161">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="2087d-162">Gibt den **securityDescriptor** für den Dienst im **SDDL** -Format an.</span><span class="sxs-lookup"><span data-stu-id="2087d-162">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2087d-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2087d-163">-Confirm</span></span>

<span data-ttu-id="2087d-164">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="2087d-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2087d-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2087d-165">-WhatIf</span></span>

<span data-ttu-id="2087d-166">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2087d-166">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2087d-167">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2087d-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2087d-168">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2087d-168">CommonParameters</span></span>

<span data-ttu-id="2087d-169">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2087d-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2087d-170">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2087d-170">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2087d-171">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2087d-171">INPUTS</span></span>

### <span data-ttu-id="2087d-172">Keine</span><span class="sxs-lookup"><span data-stu-id="2087d-172">None</span></span>

<span data-ttu-id="2087d-173">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="2087d-173">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2087d-174">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2087d-174">OUTPUTS</span></span>

### <span data-ttu-id="2087d-175">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="2087d-175">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="2087d-176">Dieses Cmdlet gibt ein Objekt zurück, das den neuen Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="2087d-176">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="2087d-177">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2087d-177">NOTES</span></span>

<span data-ttu-id="2087d-178">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2087d-178">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="2087d-179">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2087d-179">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="2087d-180">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2087d-180">RELATED LINKS</span></span>

[<span data-ttu-id="2087d-181">Get-Service</span><span class="sxs-lookup"><span data-stu-id="2087d-181">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="2087d-182">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="2087d-182">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="2087d-183">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="2087d-183">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="2087d-184">Set-Service</span><span class="sxs-lookup"><span data-stu-id="2087d-184">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="2087d-185">Start-Service</span><span class="sxs-lookup"><span data-stu-id="2087d-185">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="2087d-186">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="2087d-186">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="2087d-187">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="2087d-187">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="2087d-188">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="2087d-188">Remove-Service</span></span>](Remove-Service.md)
