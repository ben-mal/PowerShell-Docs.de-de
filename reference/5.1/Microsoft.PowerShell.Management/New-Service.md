---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 758b0a8ef9a5f65f0e7cfa7f3633086cf9f0445d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891767"
---
# <span data-ttu-id="79fdb-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="79fdb-103">New-Service</span></span>

## <span data-ttu-id="79fdb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="79fdb-104">SYNOPSIS</span></span>
<span data-ttu-id="79fdb-105">Erstellt einen neuen Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="79fdb-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="79fdb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="79fdb-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="79fdb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="79fdb-107">DESCRIPTION</span></span>

<span data-ttu-id="79fdb-108">`New-Service`Mit dem-Cmdlet wird ein neuer Eintrag für einen Windows-Dienst in der Registrierung und in der Dienst Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="79fdb-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="79fdb-109">Ein neuer Dienst erfordert eine ausführbare Datei, die während des Dienstanbieter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="79fdb-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="79fdb-110">Mit den Parametern dieses Cmdlets können Sie den Anzeigenamen, die Beschreibung, den Starttyp und die Abhängigkeiten des Diensts festlegen.</span><span class="sxs-lookup"><span data-stu-id="79fdb-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="79fdb-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="79fdb-111">EXAMPLES</span></span>

### <span data-ttu-id="79fdb-112">Beispiel 1: Erstellen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="79fdb-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
```

<span data-ttu-id="79fdb-113">Dieser Befehl erstellt einen Dienst mit dem Namen "TestService".</span><span class="sxs-lookup"><span data-stu-id="79fdb-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="79fdb-114">Beispiel 2: Erstellen eines diensnamens, der Beschreibung, Starttyp und Anzeige Name enthält</span><span class="sxs-lookup"><span data-stu-id="79fdb-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

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

<span data-ttu-id="79fdb-115">Dieser Befehl erstellt einen Dienst mit dem Namen "TestService".</span><span class="sxs-lookup"><span data-stu-id="79fdb-115">This command creates a service named TestService.</span></span> <span data-ttu-id="79fdb-116">Er verwendet die Parameter von, `New-Service` um eine Beschreibung, einen Starttyp und den anzeigen Amen für den neuen Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="79fdb-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="79fdb-117">Beispiel 3: Anzeigen des neuen Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="79fdb-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="79fdb-118">Dieser Befehl verwendet `Get-CimInstance` , um das **Win32_Service** -Objekt für den neuen Dienst zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="79fdb-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="79fdb-119">Dieses Objekt enthält den Startmodus und die Dienstbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="79fdb-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="79fdb-120">Beispiel 4: Löschen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="79fdb-120">Example 4: Delete a service</span></span>

```powershell
sc.exe delete TestService
# - or -
(Get-CimInstance -Class Win32_Service -Filter "name='TestService'").delete()
```

<span data-ttu-id="79fdb-121">In diesem Beispiel werden zwei Möglichkeiten zum Löschen des Diensts %%amp;quot;TestService%%amp;quot; veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="79fdb-121">This example shows two ways to delete the TestService service.</span></span> <span data-ttu-id="79fdb-122">Der erste Befehl verwendet die Delete-Option von `Sc.exe` .</span><span class="sxs-lookup"><span data-stu-id="79fdb-122">The first command uses the delete option of `Sc.exe`.</span></span> <span data-ttu-id="79fdb-123">Der zweite Befehl verwendet die **Delete** -Methode der **Win32_Service** -Objekte, die `Get-CimInstance` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="79fdb-123">The second command uses the **Delete** method of the **Win32_Service** objects that `Get-CimInstance` returns.</span></span>

## <span data-ttu-id="79fdb-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="79fdb-124">PARAMETERS</span></span>

### <span data-ttu-id="79fdb-125">-Binarypathname</span><span class="sxs-lookup"><span data-stu-id="79fdb-125">-BinaryPathName</span></span>

<span data-ttu-id="79fdb-126">Gibt den Pfad der ausführbaren Datei für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="79fdb-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="79fdb-127">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="79fdb-127">This parameter is required.</span></span>

<span data-ttu-id="79fdb-128">Der voll qualifizierte Pfad der Dienst Binärdatei.</span><span class="sxs-lookup"><span data-stu-id="79fdb-128">The fully qualified path to the service binary file.</span></span> <span data-ttu-id="79fdb-129">Wenn der Pfad ein Leerzeichen enthält, muss er in Anführungszeichen eingeschlossen werden, damit er ordnungsgemäß interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="79fdb-129">If the path contains a space, it must be quoted so that it is correctly interpreted.</span></span> <span data-ttu-id="79fdb-130">Beispielsweise muss `d:\my share\myservice.exe` als angegeben werden `'"d:\my share\myservice.exe"'` .</span><span class="sxs-lookup"><span data-stu-id="79fdb-130">For example, `d:\my share\myservice.exe` should be specified as `'"d:\my share\myservice.exe"'`.</span></span>

<span data-ttu-id="79fdb-131">Der Pfad kann auch Argumente für einen automatischen Start Dienst enthalten.</span><span class="sxs-lookup"><span data-stu-id="79fdb-131">The path can also include arguments for an auto-start service.</span></span> <span data-ttu-id="79fdb-132">Beispielsweise `'"d:\myshare\myservice.exe arg1 arg2"'`.</span><span class="sxs-lookup"><span data-stu-id="79fdb-132">For example, `'"d:\myshare\myservice.exe arg1 arg2"'`.</span></span> <span data-ttu-id="79fdb-133">Diese Argumente werden an den Dienst Einstiegspunkt übermittelt.</span><span class="sxs-lookup"><span data-stu-id="79fdb-133">These arguments are passed to the service entry point.</span></span>

<span data-ttu-id="79fdb-134">Weitere Informationen finden Sie unter dem **lpbinarypathname** -Parameter der " [feateservicew](/windows/win32/api/winsvc/nf-winsvc-createservicew) "-API.</span><span class="sxs-lookup"><span data-stu-id="79fdb-134">For more information, see the **lpBinaryPathName** parameter of [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) API.</span></span>

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

### <span data-ttu-id="79fdb-135">-Credential</span><span class="sxs-lookup"><span data-stu-id="79fdb-135">-Credential</span></span>

<span data-ttu-id="79fdb-136">Gibt das Konto an, das vom Dienst als [Dienst Anmelde Konto](/windows/desktop/ad/about-service-logon-accounts)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="79fdb-136">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="79fdb-137">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="79fdb-137">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="79fdb-138">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="79fdb-138">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="79fdb-139">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="79fdb-139">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="79fdb-140">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="79fdb-140">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="79fdb-141">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="79fdb-141">-DependsOn</span></span>

<span data-ttu-id="79fdb-142">Gibt die Namen anderer Dienste an, von denen der neue Dienst abhängt.</span><span class="sxs-lookup"><span data-stu-id="79fdb-142">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="79fdb-143">Trennen Sie zum Eingeben mehrerer Dienstnamen die Namen durch Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="79fdb-143">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="79fdb-144">-Description</span><span class="sxs-lookup"><span data-stu-id="79fdb-144">-Description</span></span>

<span data-ttu-id="79fdb-145">Gibt eine Beschreibung des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="79fdb-145">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="79fdb-146">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="79fdb-146">-DisplayName</span></span>

<span data-ttu-id="79fdb-147">Gibt einen Anzeigenamen für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="79fdb-147">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="79fdb-148">-Name</span><span class="sxs-lookup"><span data-stu-id="79fdb-148">-Name</span></span>

<span data-ttu-id="79fdb-149">Gibt den Namen des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="79fdb-149">Specifies the name of the service.</span></span> <span data-ttu-id="79fdb-150">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="79fdb-150">This parameter is required.</span></span>

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

### <span data-ttu-id="79fdb-151">-StartupType</span><span class="sxs-lookup"><span data-stu-id="79fdb-151">-StartupType</span></span>

<span data-ttu-id="79fdb-152">Legt den Starttyp des Diensts fest.</span><span class="sxs-lookup"><span data-stu-id="79fdb-152">Sets the startup type of the service.</span></span> <span data-ttu-id="79fdb-153">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="79fdb-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="79fdb-154">**Automatisch** : der Dienst wurde gestartet oder vom Betriebssystem beim Systemstart gestartet.</span><span class="sxs-lookup"><span data-stu-id="79fdb-154">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="79fdb-155">Wenn ein automatisch gestarteter Dienst von einem manuell gestarteten Dienst abhängig ist, wird der manuell gestartete Dienst beim Systemstart ebenfalls automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="79fdb-155">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="79fdb-156">**Deaktiviert** : der Dienst ist deaktiviert und kann nicht von einem Benutzer oder einer Anwendung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="79fdb-156">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="79fdb-157">**Manuell: der** Dienst wird nur manuell von einem Benutzer, über den Dienststeuerungs-Manager oder durch eine Anwendung gestartet.</span><span class="sxs-lookup"><span data-stu-id="79fdb-157">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="79fdb-158">**Boot** : gibt an, dass der Dienst ein Gerätetreiber ist, der vom System Lade Modul gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="79fdb-158">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="79fdb-159">Dieser Wert gilt nur für Gerätetreiber.</span><span class="sxs-lookup"><span data-stu-id="79fdb-159">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="79fdb-160">**System** : gibt an, dass es sich bei dem Dienst um einen Gerätetreiber handelt, der von der IoInitSystem ()-Funktion gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="79fdb-160">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="79fdb-161">Dieser Wert gilt nur für Gerätetreiber.</span><span class="sxs-lookup"><span data-stu-id="79fdb-161">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="79fdb-162">Der Standardwert ist **automatisch**.</span><span class="sxs-lookup"><span data-stu-id="79fdb-162">The default value is **Automatic**.</span></span>

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

### <span data-ttu-id="79fdb-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="79fdb-163">-Confirm</span></span>

<span data-ttu-id="79fdb-164">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="79fdb-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="79fdb-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="79fdb-165">-WhatIf</span></span>

<span data-ttu-id="79fdb-166">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="79fdb-166">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="79fdb-167">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="79fdb-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="79fdb-168">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="79fdb-168">CommonParameters</span></span>

<span data-ttu-id="79fdb-169">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="79fdb-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="79fdb-170">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="79fdb-170">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="79fdb-171">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="79fdb-171">INPUTS</span></span>

### <span data-ttu-id="79fdb-172">Keine</span><span class="sxs-lookup"><span data-stu-id="79fdb-172">None</span></span>

<span data-ttu-id="79fdb-173">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="79fdb-173">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="79fdb-174">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="79fdb-174">OUTPUTS</span></span>

### <span data-ttu-id="79fdb-175">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="79fdb-175">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="79fdb-176">Dieses Cmdlet gibt ein Objekt zurück, das den neuen Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="79fdb-176">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="79fdb-177">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="79fdb-177">NOTES</span></span>

<span data-ttu-id="79fdb-178">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="79fdb-178">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="79fdb-179">Um einen Dienst zu löschen, verwenden Sie Sc.exe, oder verwenden Sie das `Get-CimInstance` Cmdlet, um das **Win32_Service** Objekt zu erhalten, das den Dienst darstellt, und verwenden Sie dann die **Delete** -Methode, um den Dienst zu löschen.</span><span class="sxs-lookup"><span data-stu-id="79fdb-179">To delete a service, use Sc.exe, or use the `Get-CimInstance` cmdlet to get the **Win32_Service** object that represents the service and then use the **Delete** method to delete the service.</span></span> <span data-ttu-id="79fdb-180">Das Objekt, das `Get-Service` zurückgibt, verfügt nicht über eine Delete-Methode.</span><span class="sxs-lookup"><span data-stu-id="79fdb-180">The object that `Get-Service` returns does not have a delete method.</span></span>

## <span data-ttu-id="79fdb-181">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="79fdb-181">RELATED LINKS</span></span>

[<span data-ttu-id="79fdb-182">Get-Service</span><span class="sxs-lookup"><span data-stu-id="79fdb-182">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="79fdb-183">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="79fdb-183">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="79fdb-184">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="79fdb-184">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="79fdb-185">Set-Service</span><span class="sxs-lookup"><span data-stu-id="79fdb-185">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="79fdb-186">Start-Service</span><span class="sxs-lookup"><span data-stu-id="79fdb-186">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="79fdb-187">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="79fdb-187">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="79fdb-188">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="79fdb-188">Suspend-Service</span></span>](Suspend-Service.md)
