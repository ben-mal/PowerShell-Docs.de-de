---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: c34c581b9af74f3199437b26971b902f6b39620f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211591"
---
# <span data-ttu-id="c8dfb-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="c8dfb-103">New-Service</span></span>

## <span data-ttu-id="c8dfb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c8dfb-104">SYNOPSIS</span></span>
<span data-ttu-id="c8dfb-105">Erstellt einen neuen Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="c8dfb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c8dfb-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-SecurityDescriptorSddl <String>] [-StartupType <ServiceStartupType>] [-Credential <PSCredential>]
 [-DependsOn <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c8dfb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c8dfb-107">DESCRIPTION</span></span>

<span data-ttu-id="c8dfb-108">`New-Service`Mit dem-Cmdlet wird ein neuer Eintrag für einen Windows-Dienst in der Registrierung und in der Dienst Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="c8dfb-109">Ein neuer Dienst erfordert eine ausführbare Datei, die während des Dienstanbieter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="c8dfb-110">Mit den Parametern dieses Cmdlets können Sie den Anzeigenamen, die Beschreibung, den Starttyp und die Abhängigkeiten des Diensts festlegen.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="c8dfb-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c8dfb-111">EXAMPLES</span></span>

### <span data-ttu-id="c8dfb-112">Beispiel 1: Erstellen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="c8dfb-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="c8dfb-113">Dieser Befehl erstellt einen Dienst mit dem Namen "TestService".</span><span class="sxs-lookup"><span data-stu-id="c8dfb-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="c8dfb-114">Beispiel 2: Erstellen eines diensnamens, der Beschreibung, Starttyp und Anzeige Name enthält</span><span class="sxs-lookup"><span data-stu-id="c8dfb-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = "C:\WINDOWS\System32\svchost.exe -k netsvcs"
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

<span data-ttu-id="c8dfb-115">Dieser Befehl erstellt einen Dienst mit dem Namen "TestService".</span><span class="sxs-lookup"><span data-stu-id="c8dfb-115">This command creates a service named TestService.</span></span> <span data-ttu-id="c8dfb-116">Er verwendet die Parameter von, `New-Service` um eine Beschreibung, einen Starttyp und den anzeigen Amen für den neuen Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="c8dfb-117">Beispiel 3: Anzeigen des neuen Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="c8dfb-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="c8dfb-118">Dieser Befehl verwendet `Get-CimInstance` , um das **Win32_Service** -Objekt für den neuen Dienst zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="c8dfb-119">Dieses Objekt enthält den Startmodus und die Dienstbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="c8dfb-120">Beispiel 4: Festlegen des securitydescriptors eines Dienstanbieter bei der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-120">Example 4: Set the SecurityDescriptor of a service when creating.</span></span>

<span data-ttu-id="c8dfb-121">In diesem Beispiel wird der **securityDescriptor** des erstellten Dienstanbieter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-121">This example adds the **SecurityDescriptor** of the service being created.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
$params = @{
  BinaryPathName = "C:\WINDOWS\System32\svchost.exe -k netsvcs"
  DependsOn = "NetLogon"
  DisplayName "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
  SecurityDescriptorSddl = $SDDL
}
New-Service @params
```

<span data-ttu-id="c8dfb-122">Der **securityDescriptor** wird in der `$SDDLToSet` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-122">The **SecurityDescriptor** is stored in the `$SDDLToSet` variable.</span></span> <span data-ttu-id="c8dfb-123">Der **securitydescriptorsddl** -Parameter verwendet `$SDDL` , um den **securityDescriptor** des neuen Dienstanbieter festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-123">The **SecurityDescriptorSddl** parameter uses `$SDDL` to set the **SecurityDescriptor** of the new service.</span></span>

## <span data-ttu-id="c8dfb-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c8dfb-124">PARAMETERS</span></span>

### <span data-ttu-id="c8dfb-125">-Binarypathname</span><span class="sxs-lookup"><span data-stu-id="c8dfb-125">-BinaryPathName</span></span>

<span data-ttu-id="c8dfb-126">Gibt den Pfad der ausführbaren Datei für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="c8dfb-127">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-127">This parameter is required.</span></span>

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

### <span data-ttu-id="c8dfb-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="c8dfb-128">-Credential</span></span>

<span data-ttu-id="c8dfb-129">Gibt das Konto an, das vom Dienst als [Dienst Anmelde Konto](/windows/desktop/ad/about-service-logon-accounts)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-129">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="c8dfb-130">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-130">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="c8dfb-131">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="c8dfb-132">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-132">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="c8dfb-133">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="c8dfb-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="c8dfb-134">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="c8dfb-134">-DependsOn</span></span>

<span data-ttu-id="c8dfb-135">Gibt die Namen anderer Dienste an, von denen der neue Dienst abhängt.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-135">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="c8dfb-136">Trennen Sie zum Eingeben mehrerer Dienstnamen die Namen durch Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-136">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="c8dfb-137">-Description</span><span class="sxs-lookup"><span data-stu-id="c8dfb-137">-Description</span></span>

<span data-ttu-id="c8dfb-138">Gibt eine Beschreibung des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-138">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="c8dfb-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="c8dfb-139">-DisplayName</span></span>

<span data-ttu-id="c8dfb-140">Gibt einen Anzeigenamen für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-140">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="c8dfb-141">-Name</span><span class="sxs-lookup"><span data-stu-id="c8dfb-141">-Name</span></span>

<span data-ttu-id="c8dfb-142">Gibt den Namen des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-142">Specifies the name of the service.</span></span>
<span data-ttu-id="c8dfb-143">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-143">This parameter is required.</span></span>

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

### <span data-ttu-id="c8dfb-144">-StartupType</span><span class="sxs-lookup"><span data-stu-id="c8dfb-144">-StartupType</span></span>

<span data-ttu-id="c8dfb-145">Legt den Starttyp des Diensts fest.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-145">Sets the startup type of the service.</span></span> <span data-ttu-id="c8dfb-146">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="c8dfb-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c8dfb-147">**Automatisch** : der Dienst wurde gestartet oder vom Betriebssystem beim Systemstart gestartet.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-147">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="c8dfb-148">Wenn ein automatisch gestarteter Dienst von einem manuell gestarteten Dienst abhängig ist, wird der manuell gestartete Dienst beim Systemstart ebenfalls automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-148">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="c8dfb-149">**Automaticdelayedstart** : startet kurz nach dem Systemstart.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-149">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="c8dfb-150">**Deaktiviert** : der Dienst ist deaktiviert und kann nicht von einem Benutzer oder einer Anwendung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-150">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="c8dfb-151">**Invalidvalue** : dieser Wert wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-151">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="c8dfb-152">Die Verwendung dieses Werts führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-152">Using this value results in an error.</span></span>
- <span data-ttu-id="c8dfb-153">**Manuell: der** Dienst wird nur manuell von einem Benutzer, über den Dienststeuerungs-Manager oder durch eine Anwendung gestartet.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-153">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="c8dfb-154">Der Standardwert ist **automatisch** .</span><span class="sxs-lookup"><span data-stu-id="c8dfb-154">The default value is **Automatic** .</span></span>

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

### <span data-ttu-id="c8dfb-155">-SecurityDescriptor SDDL</span><span class="sxs-lookup"><span data-stu-id="c8dfb-155">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="c8dfb-156">Gibt den **securityDescriptor** für den Dienst im **SDDL** -Format an.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-156">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

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

### <span data-ttu-id="c8dfb-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c8dfb-157">-Confirm</span></span>

<span data-ttu-id="c8dfb-158">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c8dfb-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c8dfb-159">-WhatIf</span></span>

<span data-ttu-id="c8dfb-160">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c8dfb-161">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c8dfb-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c8dfb-162">CommonParameters</span></span>

<span data-ttu-id="c8dfb-163">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c8dfb-164">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c8dfb-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c8dfb-165">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c8dfb-165">INPUTS</span></span>

### <span data-ttu-id="c8dfb-166">Keine</span><span class="sxs-lookup"><span data-stu-id="c8dfb-166">None</span></span>

<span data-ttu-id="c8dfb-167">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-167">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c8dfb-168">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c8dfb-168">OUTPUTS</span></span>

### <span data-ttu-id="c8dfb-169">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="c8dfb-169">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="c8dfb-170">Dieses Cmdlet gibt ein Objekt zurück, das den neuen Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-170">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="c8dfb-171">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c8dfb-171">NOTES</span></span>

<span data-ttu-id="c8dfb-172">Um dieses Cmdlet unter Windows Vista und höheren Versionen des Windows-Betriebssystems auszuführen, starten Sie PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="c8dfb-172">To run this cmdlet on Windows Vista and later versions of the Windows operating system, start PowerShell by using the Run as administrator option.</span></span>

## <span data-ttu-id="c8dfb-173">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c8dfb-173">RELATED LINKS</span></span>

[<span data-ttu-id="c8dfb-174">Get-Service</span><span class="sxs-lookup"><span data-stu-id="c8dfb-174">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="c8dfb-175">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="c8dfb-175">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="c8dfb-176">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="c8dfb-176">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="c8dfb-177">Set-Service</span><span class="sxs-lookup"><span data-stu-id="c8dfb-177">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="c8dfb-178">Start-Service</span><span class="sxs-lookup"><span data-stu-id="c8dfb-178">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="c8dfb-179">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="c8dfb-179">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="c8dfb-180">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="c8dfb-180">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="c8dfb-181">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="c8dfb-181">Remove-Service</span></span>](Remove-Service.md)

