---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 04a2d18b9d663f612e8819c1d81bbfe490f4931a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213148"
---
# <span data-ttu-id="dbfe8-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="dbfe8-103">New-Service</span></span>

## <span data-ttu-id="dbfe8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dbfe8-104">SYNOPSIS</span></span>
<span data-ttu-id="dbfe8-105">Erstellt einen neuen Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="dbfe8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dbfe8-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartupType>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="dbfe8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dbfe8-107">DESCRIPTION</span></span>

<span data-ttu-id="dbfe8-108">`New-Service`Mit dem-Cmdlet wird ein neuer Eintrag für einen Windows-Dienst in der Registrierung und in der Dienst Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="dbfe8-109">Ein neuer Dienst erfordert eine ausführbare Datei, die während des Dienstanbieter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="dbfe8-110">Mit den Parametern dieses Cmdlets können Sie den Anzeigenamen, die Beschreibung, den Starttyp und die Abhängigkeiten des Diensts festlegen.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="dbfe8-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dbfe8-111">EXAMPLES</span></span>

### <span data-ttu-id="dbfe8-112">Beispiel 1: Erstellen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="dbfe8-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="dbfe8-113">Dieser Befehl erstellt einen Dienst mit dem Namen "TestService".</span><span class="sxs-lookup"><span data-stu-id="dbfe8-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="dbfe8-114">Beispiel 2: Erstellen eines diensnamens, der Beschreibung, Starttyp und Anzeige Name enthält</span><span class="sxs-lookup"><span data-stu-id="dbfe8-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

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

<span data-ttu-id="dbfe8-115">Dieser Befehl erstellt einen Dienst mit dem Namen "TestService".</span><span class="sxs-lookup"><span data-stu-id="dbfe8-115">This command creates a service named TestService.</span></span> <span data-ttu-id="dbfe8-116">Er verwendet die Parameter von, `New-Service` um eine Beschreibung, einen Starttyp und den anzeigen Amen für den neuen Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="dbfe8-117">Beispiel 3: Anzeigen des neuen Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="dbfe8-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="dbfe8-118">Dieser Befehl verwendet `Get-CimInstance` , um das **Win32_Service** -Objekt für den neuen Dienst zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="dbfe8-119">Dieses Objekt enthält den Startmodus und die Dienstbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-119">This object includes the start mode and the service description.</span></span>

## <span data-ttu-id="dbfe8-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dbfe8-120">PARAMETERS</span></span>

### <span data-ttu-id="dbfe8-121">-Binarypathname</span><span class="sxs-lookup"><span data-stu-id="dbfe8-121">-BinaryPathName</span></span>

<span data-ttu-id="dbfe8-122">Gibt den Pfad der ausführbaren Datei für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-122">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="dbfe8-123">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-123">This parameter is required.</span></span>

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

### <span data-ttu-id="dbfe8-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="dbfe8-124">-Credential</span></span>

<span data-ttu-id="dbfe8-125">Gibt das Konto an, das vom Dienst als [Dienst Anmelde Konto](/windows/desktop/ad/about-service-logon-accounts)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-125">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="dbfe8-126">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-126">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="dbfe8-127">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-127">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="dbfe8-128">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-128">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="dbfe8-129">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="dbfe8-129">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="dbfe8-130">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="dbfe8-130">-DependsOn</span></span>

<span data-ttu-id="dbfe8-131">Gibt die Namen anderer Dienste an, von denen der neue Dienst abhängt.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-131">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="dbfe8-132">Trennen Sie zum Eingeben mehrerer Dienstnamen die Namen durch Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-132">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="dbfe8-133">-Description</span><span class="sxs-lookup"><span data-stu-id="dbfe8-133">-Description</span></span>

<span data-ttu-id="dbfe8-134">Gibt eine Beschreibung des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-134">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="dbfe8-135">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="dbfe8-135">-DisplayName</span></span>

<span data-ttu-id="dbfe8-136">Gibt einen Anzeigenamen für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-136">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="dbfe8-137">-Name</span><span class="sxs-lookup"><span data-stu-id="dbfe8-137">-Name</span></span>

<span data-ttu-id="dbfe8-138">Gibt den Namen des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-138">Specifies the name of the service.</span></span>
<span data-ttu-id="dbfe8-139">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-139">This parameter is required.</span></span>

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

### <span data-ttu-id="dbfe8-140">-StartupType</span><span class="sxs-lookup"><span data-stu-id="dbfe8-140">-StartupType</span></span>

<span data-ttu-id="dbfe8-141">Legt den Starttyp des Diensts fest.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-141">Sets the startup type of the service.</span></span> <span data-ttu-id="dbfe8-142">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="dbfe8-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="dbfe8-143">**Automatisch** : der Dienst wurde gestartet oder vom Betriebssystem beim Systemstart gestartet.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-143">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="dbfe8-144">Wenn ein automatisch gestarteter Dienst von einem manuell gestarteten Dienst abhängig ist, wird der manuell gestartete Dienst beim Systemstart ebenfalls automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-144">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="dbfe8-145">**Automaticdelayedstart** : startet kurz nach dem Systemstart.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-145">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="dbfe8-146">**Deaktiviert** : der Dienst ist deaktiviert und kann nicht von einem Benutzer oder einer Anwendung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-146">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="dbfe8-147">**Invalidvalue** : dieser Wert wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-147">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="dbfe8-148">Die Verwendung dieses Werts führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-148">Using this value results in an error.</span></span>
- <span data-ttu-id="dbfe8-149">**Manuell: der** Dienst wird nur manuell von einem Benutzer, über den Dienststeuerungs-Manager oder durch eine Anwendung gestartet.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-149">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="dbfe8-150">Der Standardwert ist **automatisch** .</span><span class="sxs-lookup"><span data-stu-id="dbfe8-150">The default value is **Automatic** .</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Disabled, AutomaticDelayedStart, InvalidValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dbfe8-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dbfe8-151">-Confirm</span></span>

<span data-ttu-id="dbfe8-152">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="dbfe8-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dbfe8-153">-WhatIf</span></span>

<span data-ttu-id="dbfe8-154">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="dbfe8-155">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="dbfe8-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dbfe8-156">CommonParameters</span></span>

<span data-ttu-id="dbfe8-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dbfe8-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dbfe8-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dbfe8-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dbfe8-159">INPUTS</span></span>

### <span data-ttu-id="dbfe8-160">Keine</span><span class="sxs-lookup"><span data-stu-id="dbfe8-160">None</span></span>

<span data-ttu-id="dbfe8-161">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-161">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="dbfe8-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dbfe8-162">OUTPUTS</span></span>

### <span data-ttu-id="dbfe8-163">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="dbfe8-163">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="dbfe8-164">Dieses Cmdlet gibt ein Objekt zurück, das den neuen Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-164">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="dbfe8-165">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dbfe8-165">NOTES</span></span>

<span data-ttu-id="dbfe8-166">Um dieses Cmdlet unter Windows Vista und höheren Versionen des Windows-Betriebssystems auszuführen, starten Sie PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="dbfe8-166">To run this cmdlet on Windows Vista and later versions of the Windows operating system, start PowerShell by using the Run as administrator option.</span></span>

## <span data-ttu-id="dbfe8-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dbfe8-167">RELATED LINKS</span></span>

[<span data-ttu-id="dbfe8-168">Get-Service</span><span class="sxs-lookup"><span data-stu-id="dbfe8-168">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="dbfe8-169">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="dbfe8-169">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="dbfe8-170">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="dbfe8-170">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="dbfe8-171">Set-Service</span><span class="sxs-lookup"><span data-stu-id="dbfe8-171">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="dbfe8-172">Start-Service</span><span class="sxs-lookup"><span data-stu-id="dbfe8-172">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="dbfe8-173">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="dbfe8-173">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="dbfe8-174">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="dbfe8-174">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="dbfe8-175">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="dbfe8-175">Remove-Service</span></span>](Remove-Service.md)
