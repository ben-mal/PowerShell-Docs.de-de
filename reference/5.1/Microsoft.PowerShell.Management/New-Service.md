---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 5647f9bfa909cba9740e7be17f262b6be0e5c8e9
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342925"
---
# <span data-ttu-id="b155c-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="b155c-103">New-Service</span></span>

## <span data-ttu-id="b155c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b155c-104">SYNOPSIS</span></span>
<span data-ttu-id="b155c-105">Erstellt einen neuen Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="b155c-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="b155c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b155c-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b155c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b155c-107">DESCRIPTION</span></span>

<span data-ttu-id="b155c-108">`New-Service`Mit dem-Cmdlet wird ein neuer Eintrag für einen Windows-Dienst in der Registrierung und in der Dienst Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="b155c-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="b155c-109">Ein neuer Dienst erfordert eine ausführbare Datei, die während des Dienstanbieter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b155c-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="b155c-110">Mit den Parametern dieses Cmdlets können Sie den Anzeigenamen, die Beschreibung, den Starttyp und die Abhängigkeiten des Diensts festlegen.</span><span class="sxs-lookup"><span data-stu-id="b155c-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="b155c-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b155c-111">EXAMPLES</span></span>

### <span data-ttu-id="b155c-112">Beispiel 1: Erstellen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="b155c-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="b155c-113">Dieser Befehl erstellt einen Dienst mit dem Namen "TestService".</span><span class="sxs-lookup"><span data-stu-id="b155c-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="b155c-114">Beispiel 2: Erstellen eines diensnamens, der Beschreibung, Starttyp und Anzeige Name enthält</span><span class="sxs-lookup"><span data-stu-id="b155c-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

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

<span data-ttu-id="b155c-115">Dieser Befehl erstellt einen Dienst mit dem Namen "TestService".</span><span class="sxs-lookup"><span data-stu-id="b155c-115">This command creates a service named TestService.</span></span> <span data-ttu-id="b155c-116">Er verwendet die Parameter von, `New-Service` um eine Beschreibung, einen Starttyp und den anzeigen Amen für den neuen Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b155c-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="b155c-117">Beispiel 3: Anzeigen des neuen Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="b155c-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="b155c-118">Dieser Befehl verwendet `Get-CimInstance` , um das **Win32_Service** -Objekt für den neuen Dienst zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b155c-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="b155c-119">Dieses Objekt enthält den Startmodus und die Dienstbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="b155c-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="b155c-120">Beispiel 4: Löschen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="b155c-120">Example 4: Delete a service</span></span>

```powershell
sc.exe delete TestService
# - or -
(Get-CimInstance -Class Win32_Service -Filter "name='TestService'").delete()
```

<span data-ttu-id="b155c-121">In diesem Beispiel werden zwei Möglichkeiten zum Löschen des Diensts %%amp;quot;TestService%%amp;quot; veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b155c-121">This example shows two ways to delete the TestService service.</span></span> <span data-ttu-id="b155c-122">Der erste Befehl verwendet die Delete-Option von `Sc.exe` .</span><span class="sxs-lookup"><span data-stu-id="b155c-122">The first command uses the delete option of `Sc.exe`.</span></span> <span data-ttu-id="b155c-123">Der zweite Befehl verwendet die **Delete** -Methode der **Win32_Service** -Objekte, die `Get-CimInstance` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b155c-123">The second command uses the **Delete** method of the **Win32_Service** objects that `Get-CimInstance` returns.</span></span>

## <span data-ttu-id="b155c-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b155c-124">PARAMETERS</span></span>

### <span data-ttu-id="b155c-125">-Binarypathname</span><span class="sxs-lookup"><span data-stu-id="b155c-125">-BinaryPathName</span></span>

<span data-ttu-id="b155c-126">Gibt den Pfad der ausführbaren Datei für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="b155c-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="b155c-127">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b155c-127">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b155c-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="b155c-128">-Credential</span></span>

<span data-ttu-id="b155c-129">Gibt das Konto an, das vom Dienst als [Dienst Anmelde Konto](/windows/desktop/ad/about-service-logon-accounts)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b155c-129">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="b155c-130">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="b155c-130">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="b155c-131">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b155c-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="b155c-132">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b155c-132">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="b155c-133">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="b155c-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="b155c-134">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="b155c-134">-DependsOn</span></span>

<span data-ttu-id="b155c-135">Gibt die Namen anderer Dienste an, von denen der neue Dienst abhängt.</span><span class="sxs-lookup"><span data-stu-id="b155c-135">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="b155c-136">Trennen Sie zum Eingeben mehrerer Dienstnamen die Namen durch Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="b155c-136">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="b155c-137">-Description</span><span class="sxs-lookup"><span data-stu-id="b155c-137">-Description</span></span>

<span data-ttu-id="b155c-138">Gibt eine Beschreibung des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="b155c-138">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="b155c-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="b155c-139">-DisplayName</span></span>

<span data-ttu-id="b155c-140">Gibt einen Anzeigenamen für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="b155c-140">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="b155c-141">-Name</span><span class="sxs-lookup"><span data-stu-id="b155c-141">-Name</span></span>

<span data-ttu-id="b155c-142">Gibt den Namen des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="b155c-142">Specifies the name of the service.</span></span> <span data-ttu-id="b155c-143">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b155c-143">This parameter is required.</span></span>

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

### <span data-ttu-id="b155c-144">-StartupType</span><span class="sxs-lookup"><span data-stu-id="b155c-144">-StartupType</span></span>

<span data-ttu-id="b155c-145">Legt den Starttyp des Diensts fest.</span><span class="sxs-lookup"><span data-stu-id="b155c-145">Sets the startup type of the service.</span></span> <span data-ttu-id="b155c-146">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="b155c-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b155c-147">**Automatisch** : der Dienst wurde gestartet oder vom Betriebssystem beim Systemstart gestartet.</span><span class="sxs-lookup"><span data-stu-id="b155c-147">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="b155c-148">Wenn ein automatisch gestarteter Dienst von einem manuell gestarteten Dienst abhängig ist, wird der manuell gestartete Dienst beim Systemstart ebenfalls automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="b155c-148">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="b155c-149">**Deaktiviert** : der Dienst ist deaktiviert und kann nicht von einem Benutzer oder einer Anwendung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="b155c-149">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="b155c-150">**Manuell: der** Dienst wird nur manuell von einem Benutzer, über den Dienststeuerungs-Manager oder durch eine Anwendung gestartet.</span><span class="sxs-lookup"><span data-stu-id="b155c-150">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="b155c-151">**Boot** : gibt an, dass der Dienst ein Gerätetreiber ist, der vom System Lade Modul gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b155c-151">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="b155c-152">Dieser Wert gilt nur für Gerätetreiber.</span><span class="sxs-lookup"><span data-stu-id="b155c-152">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="b155c-153">**System** : gibt an, dass es sich bei dem Dienst um einen Gerätetreiber handelt, der von der IoInitSystem ()-Funktion gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b155c-153">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="b155c-154">Dieser Wert gilt nur für Gerätetreiber.</span><span class="sxs-lookup"><span data-stu-id="b155c-154">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="b155c-155">Der Standardwert ist **automatisch**.</span><span class="sxs-lookup"><span data-stu-id="b155c-155">The default value is **Automatic**.</span></span>

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases:
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b155c-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b155c-156">-Confirm</span></span>

<span data-ttu-id="b155c-157">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b155c-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b155c-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b155c-158">-WhatIf</span></span>

<span data-ttu-id="b155c-159">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b155c-159">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b155c-160">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b155c-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b155c-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b155c-161">CommonParameters</span></span>

<span data-ttu-id="b155c-162">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b155c-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b155c-163">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b155c-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b155c-164">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b155c-164">INPUTS</span></span>

### <span data-ttu-id="b155c-165">Keine</span><span class="sxs-lookup"><span data-stu-id="b155c-165">None</span></span>

<span data-ttu-id="b155c-166">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="b155c-166">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b155c-167">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b155c-167">OUTPUTS</span></span>

### <span data-ttu-id="b155c-168">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="b155c-168">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="b155c-169">Dieses Cmdlet gibt ein Objekt zurück, das den neuen Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="b155c-169">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="b155c-170">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b155c-170">NOTES</span></span>

<span data-ttu-id="b155c-171">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b155c-171">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="b155c-172">Um einen Dienst zu löschen, verwenden Sie Sc.exe, oder verwenden Sie das `Get-CimInstance` Cmdlet, um das **Win32_Service** Objekt zu erhalten, das den Dienst darstellt, und verwenden Sie dann die **Delete** -Methode, um den Dienst zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b155c-172">To delete a service, use Sc.exe, or use the `Get-CimInstance` cmdlet to get the **Win32_Service** object that represents the service and then use the **Delete** method to delete the service.</span></span> <span data-ttu-id="b155c-173">Das Objekt, das `Get-Service` zurückgibt, verfügt nicht über eine Delete-Methode.</span><span class="sxs-lookup"><span data-stu-id="b155c-173">The object that `Get-Service` returns does not have a delete method.</span></span>

## <span data-ttu-id="b155c-174">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b155c-174">RELATED LINKS</span></span>

[<span data-ttu-id="b155c-175">Get-Service</span><span class="sxs-lookup"><span data-stu-id="b155c-175">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="b155c-176">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="b155c-176">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="b155c-177">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="b155c-177">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="b155c-178">Set-Service</span><span class="sxs-lookup"><span data-stu-id="b155c-178">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="b155c-179">Start-Service</span><span class="sxs-lookup"><span data-stu-id="b155c-179">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="b155c-180">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="b155c-180">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="b155c-181">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="b155c-181">Suspend-Service</span></span>](Suspend-Service.md)
