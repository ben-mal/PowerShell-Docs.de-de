---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: df4fda68508e21700235d2b772c6dd43c8e1fe1e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214415"
---
# <span data-ttu-id="608ae-103">Set-Service</span><span class="sxs-lookup"><span data-stu-id="608ae-103">Set-Service</span></span>

## <span data-ttu-id="608ae-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="608ae-104">SYNOPSIS</span></span>
<span data-ttu-id="608ae-105">Startet, beendet und hält einen Dienst an und ändert seine Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="608ae-105">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="608ae-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="608ae-106">SYNTAX</span></span>

### <span data-ttu-id="608ae-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="608ae-107">Name (Default)</span></span>

```
Set-Service [-ComputerName <String[]>] [-Name] <String> [-DisplayName <String>]
 [-Description <String>] [-StartupType <ServiceStartMode>] [-Status <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="608ae-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="608ae-108">InputObject</span></span>

```
Set-Service [-ComputerName <String[]>] [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Status <String>] [-InputObject <ServiceController>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="608ae-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="608ae-109">DESCRIPTION</span></span>

<span data-ttu-id="608ae-110">Das- `Set-Service` Cmdlet ändert die Eigenschaften eines Dienstanbieter, z. b. **Status** , **Beschreibung** , **Display Name** und **startupType** .</span><span class="sxs-lookup"><span data-stu-id="608ae-110">The `Set-Service` cmdlet changes the properties of a service such as the **Status** , **Description** , **DisplayName** , and **StartupType** .</span></span> <span data-ttu-id="608ae-111">`Set-Service` ein Dienst kann gestartet, beendet, angehalten oder angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="608ae-111">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="608ae-112">Um einen Dienst zu identifizieren, geben Sie seinen Dienstnamen ein, oder übermitteln Sie ein Dienst Objekt.</span><span class="sxs-lookup"><span data-stu-id="608ae-112">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="608ae-113">Oder senden Sie einen Dienstnamen oder ein Dienst Objekt über die Pipeline an `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="608ae-113">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="608ae-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="608ae-114">EXAMPLES</span></span>

### <span data-ttu-id="608ae-115">Beispiel 1: Ändern eines anzeigen Amens</span><span class="sxs-lookup"><span data-stu-id="608ae-115">Example 1: Change a display name</span></span>

<span data-ttu-id="608ae-116">In diesem Beispiel wird der Anzeige Name eines dienstaners geändert.</span><span class="sxs-lookup"><span data-stu-id="608ae-116">In this example, a service's display name is changed.</span></span> <span data-ttu-id="608ae-117">Verwenden Sie, um den ursprünglichen anzeigen Amen anzuzeigen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="608ae-117">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="608ae-118">`Set-Service` verwendet den **Name** -Parameter, um den Namen des dienstanders ( **LanmanWorkstation** ) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="608ae-118">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation** .</span></span> <span data-ttu-id="608ae-119">Der **DisplayName** -Parameter gibt den neuen anzeigen Amen, **LanMan Workstation** , an.</span><span class="sxs-lookup"><span data-stu-id="608ae-119">The **DisplayName** parameter specifies the new display name, **LanMan Workstation** .</span></span>

### <span data-ttu-id="608ae-120">Beispiel 2: Ändern des Starttyps der Dienste</span><span class="sxs-lookup"><span data-stu-id="608ae-120">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="608ae-121">In diesem Beispiel wird gezeigt, wie der Starttyp eines dienstaners geändert wird.</span><span class="sxs-lookup"><span data-stu-id="608ae-121">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="608ae-122">`Set-Service` verwendet den **Name** -Parameter zum Angeben des Dienst namens ( **Bits** ).</span><span class="sxs-lookup"><span data-stu-id="608ae-122">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS** .</span></span> <span data-ttu-id="608ae-123">Der **startupType** -Parameter legt den Dienst auf " **automatisch** " fest.</span><span class="sxs-lookup"><span data-stu-id="608ae-123">The **StartupType** parameter sets the service to **Automatic** .</span></span>

<span data-ttu-id="608ae-124">`Get-Service` verwendet den **Name** -Parameter, um den **Bits** -Dienst anzugeben, und sendet das Objekt über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="608ae-124">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="608ae-125">`Select-Object` verwendet den **Property** -Parameter, um den **Bits** -Dienststatus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="608ae-125">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="608ae-126">Beispiel 3: Ändern der Beschreibung eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="608ae-126">Example 3: Change the description of a service</span></span>

<span data-ttu-id="608ae-127">In diesem Beispiel wird die Beschreibung des Bits-diendienstanders geändert und das Ergebnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="608ae-127">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="608ae-128">Das- `Get-CimInstance` Cmdlet wird verwendet, da es ein **Win32_Service** Objekt zurückgibt, das **die Beschreibung** des dienstaners enthält.</span><span class="sxs-lookup"><span data-stu-id="608ae-128">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description** .</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

<span data-ttu-id="608ae-129">`Get-CimInstance` sendet das Objekt über die Pipeline an `Format-List` und zeigt den Namen und die Beschreibung des dienstanders an.</span><span class="sxs-lookup"><span data-stu-id="608ae-129">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="608ae-130">Zu Vergleichszwecken wird der Befehl vor und nach dem Aktualisieren der Beschreibung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="608ae-130">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="608ae-131">`Set-Service` verwendet den **Name** -Parameter, um den **Bits** -Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="608ae-131">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="608ae-132">Der **Description** -Parameter gibt den aktualisierten Text für die Beschreibung der Dienste an.</span><span class="sxs-lookup"><span data-stu-id="608ae-132">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="608ae-133">Beispiel 4: Starten eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="608ae-133">Example 4: Start a service</span></span>

<span data-ttu-id="608ae-134">In diesem Beispiel wird ein-Dienst gestartet.</span><span class="sxs-lookup"><span data-stu-id="608ae-134">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="608ae-135">`Set-Service` verwendet den **Name** -Parameter, um den Dienst ( **WinRM** ) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="608ae-135">`Set-Service` uses the **Name** parameter to specify the service, **WinRM** .</span></span> <span data-ttu-id="608ae-136">Der **Status** Parameter verwendet den-Wert, der **ausgeführt** wird, um den Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="608ae-136">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="608ae-137">Der **passthru** -Parameter gibt ein **ServiceController** -Objekt aus, das die Ergebnisse anzeigt.</span><span class="sxs-lookup"><span data-stu-id="608ae-137">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="608ae-138">Beispiel 5: aussetzen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="608ae-138">Example 5: Suspend a service</span></span>

<span data-ttu-id="608ae-139">In diesem Beispiel wird die Pipeline verwendet, um den Dienst anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="608ae-139">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="608ae-140">`Get-Service` verwendet den **Name** -Parameter, um den Zeit **Plan** Dienst anzugeben, und sendet das Objekt über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="608ae-140">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="608ae-141">`Set-Service` verwendet den **Status** Parameter, um den Dienst auf **angeh** alten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="608ae-141">`Set-Service` uses the **Status** parameter to set the service to **Paused** .</span></span>

### <span data-ttu-id="608ae-142">Beispiel 6: Dienst Beendigung</span><span class="sxs-lookup"><span data-stu-id="608ae-142">Example 6: Stop a service</span></span>

<span data-ttu-id="608ae-143">In diesem Beispiel wird eine-Variable verwendet, um einen Dienst zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="608ae-143">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="608ae-144">`Get-Service` verwendet den **Name** -Parameter, um den Dienst ( **Schedule** ) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="608ae-144">`Get-Service` uses the **Name** parameter to specify the service, **Schedule** .</span></span> <span data-ttu-id="608ae-145">Das-Objekt wird in der-Variable gespeichert `$S` .</span><span class="sxs-lookup"><span data-stu-id="608ae-145">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="608ae-146">`Set-Service` verwendet den **Inputobject** -Parameter und gibt das gespeicherte Objekt an `$S` .</span><span class="sxs-lookup"><span data-stu-id="608ae-146">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="608ae-147">Der **Status** Parameter legt den Dienst auf " **beendet** " fest.</span><span class="sxs-lookup"><span data-stu-id="608ae-147">The **Status** parameter sets the service to **Stopped** .</span></span>

## <span data-ttu-id="608ae-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="608ae-148">PARAMETERS</span></span>

### <span data-ttu-id="608ae-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="608ae-149">-ComputerName</span></span>

<span data-ttu-id="608ae-150">Gibt Computer an.</span><span class="sxs-lookup"><span data-stu-id="608ae-150">Specifies one or more computers.</span></span> <span data-ttu-id="608ae-151">Geben Sie für Remote Computer den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="608ae-151">For remote computers, type the NetBIOS name, an IP address, or a fully qualified domain name.</span></span> <span data-ttu-id="608ae-152">Wenn der **Computername** -Parameter nicht angegeben wird, wird der Befehl auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="608ae-152">If the **ComputerName** parameter isn't specified, the command runs on the local computer.</span></span>

<span data-ttu-id="608ae-153">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="608ae-153">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="608ae-154">Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="608ae-154">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="608ae-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="608ae-155">-Confirm</span></span>

<span data-ttu-id="608ae-156">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="608ae-156">Prompts you for confirmation before running `Set-Service`.</span></span>

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

### <span data-ttu-id="608ae-157">-Description</span><span class="sxs-lookup"><span data-stu-id="608ae-157">-Description</span></span>

<span data-ttu-id="608ae-158">Gibt eine neue Beschreibung für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="608ae-158">Specifies a new description for the service.</span></span>

<span data-ttu-id="608ae-159">Die Dienst Beschreibung wird in **Computer Verwaltung, Dienste** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="608ae-159">The service description appears in **Computer Management, Services** .</span></span> <span data-ttu-id="608ae-160">Die **Beschreibung** ist keine Eigenschaft des `Get-Service` **ServiceController** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="608ae-160">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="608ae-161">Um die Dienst Beschreibung anzuzeigen, verwenden Sie `Get-CimInstance` , die ein **Win32_Service** Objekt zurückgibt, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="608ae-161">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

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

### <span data-ttu-id="608ae-162">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="608ae-162">-DisplayName</span></span>

<span data-ttu-id="608ae-163">Gibt einen neuen Anzeigenamen für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="608ae-163">Specifies a new display name for the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="608ae-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="608ae-164">-InputObject</span></span>

<span data-ttu-id="608ae-165">Gibt ein **ServiceController** -Objekt an, das den zu ändernden Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="608ae-165">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="608ae-166">Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl oder Ausdruck ein, der das Objekt abruft, z `Get-Service` . b. einen Befehl.</span><span class="sxs-lookup"><span data-stu-id="608ae-166">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="608ae-167">Sie können die Pipeline verwenden, um ein Dienst Objekt an zu senden `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="608ae-167">You can use the pipeline to send a service object to `Set-Service`.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="608ae-168">-Name</span><span class="sxs-lookup"><span data-stu-id="608ae-168">-Name</span></span>

<span data-ttu-id="608ae-169">Gibt den Dienstnamen des zu ändernden Diensts an.</span><span class="sxs-lookup"><span data-stu-id="608ae-169">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="608ae-170">Platzhalter Zeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="608ae-170">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="608ae-171">Sie können die Pipeline verwenden, um einen Dienstnamen an zu senden `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="608ae-171">You can use the pipeline to send a service name to `Set-Service`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="608ae-172">-PassThru</span><span class="sxs-lookup"><span data-stu-id="608ae-172">-PassThru</span></span>

<span data-ttu-id="608ae-173">Gibt ein **ServiceController** -Objekt zurück, das die geänderten Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="608ae-173">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="608ae-174">Standardmäßig `Set-Service` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="608ae-174">By default, `Set-Service` doesn't generate any output.</span></span>

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

### <span data-ttu-id="608ae-175">-StartupType</span><span class="sxs-lookup"><span data-stu-id="608ae-175">-StartupType</span></span>

<span data-ttu-id="608ae-176">Legt den Starttyp des Diensts fest.</span><span class="sxs-lookup"><span data-stu-id="608ae-176">Sets the startup type of the service.</span></span> <span data-ttu-id="608ae-177">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="608ae-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="608ae-178">**Automatisch** : der Dienst wurde gestartet oder vom Betriebssystem beim Systemstart gestartet.</span><span class="sxs-lookup"><span data-stu-id="608ae-178">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="608ae-179">Wenn ein automatisch gestarteter Dienst von einem manuell gestarteten Dienst abhängig ist, wird der manuell gestartete Dienst beim Systemstart ebenfalls automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="608ae-179">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="608ae-180">**Deaktiviert** : der Dienst ist deaktiviert und kann nicht von einem Benutzer oder einer Anwendung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="608ae-180">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="608ae-181">**Manuell: der** Dienst wird nur manuell von einem Benutzer, über den Dienststeuerungs-Manager oder durch eine Anwendung gestartet.</span><span class="sxs-lookup"><span data-stu-id="608ae-181">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="608ae-182">**Boot** : gibt an, dass der Dienst ein Gerätetreiber ist, der vom System Lade Modul gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="608ae-182">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="608ae-183">Dieser Wert gilt nur für Gerätetreiber.</span><span class="sxs-lookup"><span data-stu-id="608ae-183">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="608ae-184">**System** : gibt an, dass es sich bei dem Dienst um einen Gerätetreiber handelt, der von der IoInitSystem ()-Funktion gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="608ae-184">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="608ae-185">Dieser Wert gilt nur für Gerätetreiber.</span><span class="sxs-lookup"><span data-stu-id="608ae-185">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="608ae-186">Der Standardwert ist **automatisch** .</span><span class="sxs-lookup"><span data-stu-id="608ae-186">The default value is **Automatic** .</span></span>

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="608ae-187">-Status</span><span class="sxs-lookup"><span data-stu-id="608ae-187">-Status</span></span>

<span data-ttu-id="608ae-188">Gibt den Status für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="608ae-188">Specifies the status for the service.</span></span>

<span data-ttu-id="608ae-189">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="608ae-189">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="608ae-190">**Angeh** alten.</span><span class="sxs-lookup"><span data-stu-id="608ae-190">**Paused** .</span></span> <span data-ttu-id="608ae-191">Hält den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="608ae-191">Suspends the service.</span></span>
- <span data-ttu-id="608ae-192">**Wird ausgeführt** .</span><span class="sxs-lookup"><span data-stu-id="608ae-192">**Running** .</span></span> <span data-ttu-id="608ae-193">Startet den Dienst.</span><span class="sxs-lookup"><span data-stu-id="608ae-193">Starts the service.</span></span>
- <span data-ttu-id="608ae-194">**Stopped** (Beendet): Dies ist der anfängliche Status des Kanals nach seiner Erstellung (es sei denn, im Portal wurde das automatische Starten gewählt).</span><span class="sxs-lookup"><span data-stu-id="608ae-194">**Stopped** .</span></span> <span data-ttu-id="608ae-195">Beendet den Dienst.</span><span class="sxs-lookup"><span data-stu-id="608ae-195">Stops the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="608ae-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="608ae-196">-WhatIf</span></span>

<span data-ttu-id="608ae-197">Zeigt, was geschieht, wenn ausgeführt wird `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="608ae-197">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="608ae-198">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="608ae-198">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="608ae-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="608ae-199">CommonParameters</span></span>

<span data-ttu-id="608ae-200">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="608ae-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="608ae-201">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="608ae-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="608ae-202">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="608ae-202">INPUTS</span></span>

### <span data-ttu-id="608ae-203">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="608ae-203">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="608ae-204">Sie können die Pipeline verwenden, um ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, an zu senden `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="608ae-204">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="608ae-205">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="608ae-205">OUTPUTS</span></span>

### <span data-ttu-id="608ae-206">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="608ae-206">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="608ae-207">Standardmäßig `Set-Service` gibt keine-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="608ae-207">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="608ae-208">Verwenden Sie den **passthru** -Parameter, um ein **ServiceController** -Objekt auszugeben.</span><span class="sxs-lookup"><span data-stu-id="608ae-208">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="608ae-209">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="608ae-209">NOTES</span></span>

<span data-ttu-id="608ae-210">`Set-Service` erfordert erweiterte Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="608ae-210">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="608ae-211">Verwenden Sie die Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="608ae-211">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="608ae-212">`Set-Service` Es können nur Dienste gesteuert werden, wenn der aktuelle Benutzer über Berechtigungen zum Verwalten von Diensten verfügt.</span><span class="sxs-lookup"><span data-stu-id="608ae-212">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="608ae-213">Wenn ein Befehl nicht ordnungsgemäß funktioniert, verfügen Sie möglicherweise nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="608ae-213">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="608ae-214">Verwenden Sie, um den Dienstnamen oder anzeigen Amen eines Dienstanbieter zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="608ae-214">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="608ae-215">Die Dienstnamen befinden sich in der Spalte **Name** und die anzeigen Amen in der Spalte **Display Name** .</span><span class="sxs-lookup"><span data-stu-id="608ae-215">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="608ae-216">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="608ae-216">RELATED LINKS</span></span>

[<span data-ttu-id="608ae-217">Get-Service</span><span class="sxs-lookup"><span data-stu-id="608ae-217">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="608ae-218">New-Service</span><span class="sxs-lookup"><span data-stu-id="608ae-218">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="608ae-219">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="608ae-219">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="608ae-220">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="608ae-220">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="608ae-221">Start-Service</span><span class="sxs-lookup"><span data-stu-id="608ae-221">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="608ae-222">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="608ae-222">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="608ae-223">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="608ae-223">Suspend-Service</span></span>](Suspend-Service.md)
