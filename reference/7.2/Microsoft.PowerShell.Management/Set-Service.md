---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: 0c6cac03f1acbda35069780f0c53eaf6685813ff
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601318"
---
# <span data-ttu-id="ff1eb-102">Set-Service</span><span class="sxs-lookup"><span data-stu-id="ff1eb-102">Set-Service</span></span>

## <span data-ttu-id="ff1eb-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ff1eb-103">SYNOPSIS</span></span>
<span data-ttu-id="ff1eb-104">Startet, beendet und hält einen Dienst an und ändert seine Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-104">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="ff1eb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ff1eb-105">SYNTAX</span></span>

### <span data-ttu-id="ff1eb-106">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="ff1eb-106">Name (Default)</span></span>

```
Set-Service [-Name] <String> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>]
 [-SecurityDescriptorSddl <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ff1eb-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="ff1eb-107">InputObject</span></span>

```
Set-Service [-InputObject] <ServiceController> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-SecurityDescriptorSddl <String>]
 [-Status <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ff1eb-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ff1eb-108">DESCRIPTION</span></span>

<span data-ttu-id="ff1eb-109">Das- `Set-Service` Cmdlet ändert die Eigenschaften eines Dienstanbieter, z. b. **Status**, **Beschreibung**, **Display Name** und **startupType**.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-109">The `Set-Service` cmdlet changes the properties of a service such as the **Status**, **Description**, **DisplayName**, and **StartupType**.</span></span> <span data-ttu-id="ff1eb-110">`Set-Service` ein Dienst kann gestartet, beendet, angehalten oder angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-110">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="ff1eb-111">Um einen Dienst zu identifizieren, geben Sie seinen Dienstnamen ein, oder übermitteln Sie ein Dienst Objekt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-111">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="ff1eb-112">Oder senden Sie einen Dienstnamen oder ein Dienst Objekt über die Pipeline an `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-112">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="ff1eb-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ff1eb-113">EXAMPLES</span></span>

### <span data-ttu-id="ff1eb-114">Beispiel 1: Ändern eines anzeigen Amens</span><span class="sxs-lookup"><span data-stu-id="ff1eb-114">Example 1: Change a display name</span></span>

<span data-ttu-id="ff1eb-115">In diesem Beispiel wird der Anzeige Name eines dienstaners geändert.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-115">In this example, a service's display name is changed.</span></span> <span data-ttu-id="ff1eb-116">Verwenden Sie, um den ursprünglichen anzeigen Amen anzuzeigen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-116">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="ff1eb-117">`Set-Service` verwendet den **Name** -Parameter, um den Namen des dienstanders ( **LanmanWorkstation**) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-117">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation**.</span></span> <span data-ttu-id="ff1eb-118">Der **DisplayName** -Parameter gibt den neuen anzeigen Amen, **LanMan Workstation**, an.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-118">The **DisplayName** parameter specifies the new display name, **LanMan Workstation**.</span></span>

### <span data-ttu-id="ff1eb-119">Beispiel 2: Ändern des Starttyps der Dienste</span><span class="sxs-lookup"><span data-stu-id="ff1eb-119">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="ff1eb-120">In diesem Beispiel wird gezeigt, wie der Starttyp eines dienstaners geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-120">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="ff1eb-121">`Set-Service` verwendet den **Name** -Parameter zum Angeben des Dienst namens ( **Bits**).</span><span class="sxs-lookup"><span data-stu-id="ff1eb-121">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS**.</span></span> <span data-ttu-id="ff1eb-122">Der **startupType** -Parameter legt den Dienst auf " **automatisch**" fest.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-122">The **StartupType** parameter sets the service to **Automatic**.</span></span>

<span data-ttu-id="ff1eb-123">`Get-Service` verwendet den **Name** -Parameter, um den **Bits** -Dienst anzugeben, und sendet das Objekt über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-123">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="ff1eb-124">`Select-Object` verwendet den **Property** -Parameter, um den **Bits** -Dienststatus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-124">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="ff1eb-125">Beispiel 3: Ändern der Beschreibung eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="ff1eb-125">Example 3: Change the description of a service</span></span>

<span data-ttu-id="ff1eb-126">In diesem Beispiel wird die Beschreibung des Bits-diendienstanders geändert und das Ergebnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-126">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="ff1eb-127">Das- `Get-CimInstance` Cmdlet wird verwendet, da es ein **Win32_Service** Objekt zurückgibt, das **die Beschreibung** des dienstaners enthält.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-127">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description**.</span></span>

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

<span data-ttu-id="ff1eb-128">`Get-CimInstance` sendet das Objekt über die Pipeline an `Format-List` und zeigt den Namen und die Beschreibung des dienstanders an.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-128">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="ff1eb-129">Zu Vergleichszwecken wird der Befehl vor und nach dem Aktualisieren der Beschreibung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-129">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="ff1eb-130">`Set-Service` verwendet den **Name** -Parameter, um den **Bits** -Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-130">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="ff1eb-131">Der **Description** -Parameter gibt den aktualisierten Text für die Beschreibung der Dienste an.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-131">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="ff1eb-132">Beispiel 4: Starten eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="ff1eb-132">Example 4: Start a service</span></span>

<span data-ttu-id="ff1eb-133">In diesem Beispiel wird ein-Dienst gestartet.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-133">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="ff1eb-134">`Set-Service` verwendet den **Name** -Parameter, um den Dienst ( **WinRM**) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-134">`Set-Service` uses the **Name** parameter to specify the service, **WinRM**.</span></span> <span data-ttu-id="ff1eb-135">Der **Status** Parameter verwendet den-Wert, der **ausgeführt** wird, um den Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-135">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="ff1eb-136">Der **passthru** -Parameter gibt ein **ServiceController** -Objekt aus, das die Ergebnisse anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-136">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="ff1eb-137">Beispiel 5: aussetzen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="ff1eb-137">Example 5: Suspend a service</span></span>

<span data-ttu-id="ff1eb-138">In diesem Beispiel wird die Pipeline verwendet, um den Dienst anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-138">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="ff1eb-139">`Get-Service` verwendet den **Name** -Parameter, um den Zeit **Plan** Dienst anzugeben, und sendet das Objekt über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-139">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="ff1eb-140">`Set-Service` verwendet den **Status** Parameter, um den Dienst auf **angeh** alten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-140">`Set-Service` uses the **Status** parameter to set the service to **Paused**.</span></span>

### <span data-ttu-id="ff1eb-141">Beispiel 6: Dienst Beendigung</span><span class="sxs-lookup"><span data-stu-id="ff1eb-141">Example 6: Stop a service</span></span>

<span data-ttu-id="ff1eb-142">In diesem Beispiel wird eine-Variable verwendet, um einen Dienst zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-142">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="ff1eb-143">`Get-Service` verwendet den **Name** -Parameter, um den Dienst ( **Schedule**) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-143">`Get-Service` uses the **Name** parameter to specify the service, **Schedule**.</span></span> <span data-ttu-id="ff1eb-144">Das-Objekt wird in der-Variable gespeichert `$S` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-144">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="ff1eb-145">`Set-Service` verwendet den **Inputobject** -Parameter und gibt das gespeicherte Objekt an `$S` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-145">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="ff1eb-146">Der **Status** Parameter legt den Dienst auf " **beendet**" fest.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-146">The **Status** parameter sets the service to **Stopped**.</span></span>

### <span data-ttu-id="ff1eb-147">Beispiel 7: Beendigung eines Dienstanbieter auf einem Remote System</span><span class="sxs-lookup"><span data-stu-id="ff1eb-147">Example 7: Stop a service on a remote system</span></span>

<span data-ttu-id="ff1eb-148">In diesem Beispiel wird ein Dienst auf einem Remote Computer angehalten.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-148">This example stops a service on a remote computer.</span></span>
<span data-ttu-id="ff1eb-149">Weitere Informationen finden Sie unter " [aufrufen-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="ff1eb-149">For more information, see [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```powershell
$Cred = Get-Credential
$S = Get-Service -Name Schedule
Invoke-Command -ComputerName server01.contoso.com -Credential $Cred -ScriptBlock {
  Set-Service -InputObject $S -Status Stopped
}
```

<span data-ttu-id="ff1eb-150">`Get-Credential` fordert zur Eingabe eines Benutzernamens und Kennworts auf und speichert die Anmelde Informationen in der `$Cred` Variablen.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-150">`Get-Credential` prompts for a username and password, and stores the credentials in the `$Cred` variable.</span></span> <span data-ttu-id="ff1eb-151">`Get-Service` verwendet den **Name** -Parameter, um den Zeit **Plan** Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-151">`Get-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="ff1eb-152">Das-Objekt wird in der-Variable gespeichert `$S` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-152">The object is stored in the variable, `$S`.</span></span>

<span data-ttu-id="ff1eb-153">`Invoke-Command` verwendet den **Computername** -Parameter, um einen Remote Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-153">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer.</span></span> <span data-ttu-id="ff1eb-154">Der **Credential** -Parameter verwendet die- `$Cred` Variable, um sich am Computer anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-154">The **Credential** parameter uses the `$Cred` variable to sign on to the computer.</span></span> <span data-ttu-id="ff1eb-155">Der **ScriptBlock** Ruft auf `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-155">The **ScriptBlock** calls `Set-Service`.</span></span> <span data-ttu-id="ff1eb-156">Der **Inputobject** -Parameter gibt das gespeicherte Dienst Objekt an `$S` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-156">The **InputObject** parameter specifies the service object stored `$S`.</span></span> <span data-ttu-id="ff1eb-157">Der **Status** Parameter legt den Dienst auf " **beendet**" fest.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-157">The **Status** parameter sets the service to **Stopped**.</span></span>

### <span data-ttu-id="ff1eb-158">Beispiel 8: Ändern der Anmelde Informationen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="ff1eb-158">Example 8: Change credential of a service</span></span>

<span data-ttu-id="ff1eb-159">In diesem Beispiel werden die Anmelde Informationen geändert, die zum Verwalten eines Dienstanbieter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-159">This example changes the credentials that are used to manage a service.</span></span>

```powershell
$credential = Get-Credential
Set-Service -Name Schedule -Credential $credential
```

<span data-ttu-id="ff1eb-160">`Get-Credential` fordert zur Eingabe eines Benutzernamens und Kennworts auf und speichert die Anmelde Informationen in der `$credential` Variablen.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-160">`Get-Credential` prompts for a username and password, and stores the credentials in the `$credential` variable.</span></span> <span data-ttu-id="ff1eb-161">`Set-Service` verwendet den **Name** -Parameter, um den Zeit **Plan** Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-161">`Set-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="ff1eb-162">Der **Credential** -Parameter verwendet die `$credential` -Variable und aktualisiert den Zeit **Plan** Dienst.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-162">The **Credential** parameter uses the `$credential` variable and updates the **Schedule** service.</span></span>

### <span data-ttu-id="ff1eb-163">Beispiel 9: Ändern des securitydescriptors eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="ff1eb-163">Example 9: Change the SecurityDescriptor of a service</span></span>

<span data-ttu-id="ff1eb-164">In diesem Beispiel wird der **securityDescriptor** eines dienstanders geändert.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-164">This example changes a service's **SecurityDescriptor**.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
Set-Service -Name "BITS" -SecurityDescriptorSddl $SDDL
```

<span data-ttu-id="ff1eb-165">Der **securityDescriptor** wird in der `$SDDL` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-165">The **SecurityDescriptor** is stored in the `$SDDL` variable.</span></span> <span data-ttu-id="ff1eb-166">`Set-Service` verwendet den **Name** -Parameter, um den **Bits** -Dienst anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-166">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="ff1eb-167">Der **securitydescriptorsddl** -Parameter verwendet `$SDDL` , um den **securityDescriptor** für den **Bits** -Dienst zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-167">The **SecurityDescriptorSddl** parameter uses `$SDDL` to change the **SecurityDescriptor** for the **BITS** service.</span></span>

## <span data-ttu-id="ff1eb-168">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ff1eb-168">PARAMETERS</span></span>

### <span data-ttu-id="ff1eb-169">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ff1eb-169">-Confirm</span></span>

<span data-ttu-id="ff1eb-170">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-170">Prompts you for confirmation before running `Set-Service`.</span></span>

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

### <span data-ttu-id="ff1eb-171">-Credential</span><span class="sxs-lookup"><span data-stu-id="ff1eb-171">-Credential</span></span>

<span data-ttu-id="ff1eb-172">Gibt das Konto an, das vom Dienst als [Dienst Anmelde Konto](/windows/desktop/ad/about-service-logon-accounts)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-172">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="ff1eb-173">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-173">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ff1eb-174">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-174">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="ff1eb-175">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-175">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="ff1eb-176">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="ff1eb-176">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="ff1eb-177">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-177">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="ff1eb-178">-Description</span><span class="sxs-lookup"><span data-stu-id="ff1eb-178">-Description</span></span>

<span data-ttu-id="ff1eb-179">Gibt eine neue Beschreibung für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-179">Specifies a new description for the service.</span></span>

<span data-ttu-id="ff1eb-180">Die Dienst Beschreibung wird in **Computer Verwaltung, Dienste** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-180">The service description appears in **Computer Management, Services**.</span></span> <span data-ttu-id="ff1eb-181">Die **Beschreibung** ist keine Eigenschaft des `Get-Service` **ServiceController** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-181">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="ff1eb-182">Um die Dienst Beschreibung anzuzeigen, verwenden Sie `Get-CimInstance` , die ein **Win32_Service** Objekt zurückgibt, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-182">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

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

### <span data-ttu-id="ff1eb-183">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="ff1eb-183">-DisplayName</span></span>

<span data-ttu-id="ff1eb-184">Gibt einen neuen Anzeigenamen für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-184">Specifies a new display name for the service.</span></span>

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

### <span data-ttu-id="ff1eb-185">-Force</span><span class="sxs-lookup"><span data-stu-id="ff1eb-185">-Force</span></span>

<span data-ttu-id="ff1eb-186">Gibt den Stoppmodus des Dienstanbieter an.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-186">Specifies the Stop mode of the service.</span></span> <span data-ttu-id="ff1eb-187">Dieser Parameter funktioniert nur, wenn `-Status Stopped` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-187">This parameter only works when `-Status Stopped` is used.</span></span> <span data-ttu-id="ff1eb-188">Wenn diese Option aktiviert ist, werden `Set-Service` die abhängigen Dienste beendet, bevor der Ziel Dienst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-188">If enabled, `Set-Service` stops the dependent services before the target service is stopped.</span></span> <span data-ttu-id="ff1eb-189">Standardmäßig werden Ausnahmen ausgelöst, wenn andere laufende Dienste vom Ziel Dienst abhängen.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-189">By default, exceptions are raised when other running services depend on the target service.</span></span>

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

### <span data-ttu-id="ff1eb-190">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ff1eb-190">-InputObject</span></span>

<span data-ttu-id="ff1eb-191">Gibt ein **ServiceController** -Objekt an, das den zu ändernden Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-191">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="ff1eb-192">Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl oder Ausdruck ein, der das Objekt abruft, z `Get-Service` . b. einen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-192">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="ff1eb-193">Sie können die Pipeline verwenden, um ein Dienst Objekt an zu senden `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-193">You can use the pipeline to send a service object to `Set-Service`.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ff1eb-194">-Name</span><span class="sxs-lookup"><span data-stu-id="ff1eb-194">-Name</span></span>

<span data-ttu-id="ff1eb-195">Gibt den Dienstnamen des zu ändernden Diensts an.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-195">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="ff1eb-196">Platzhalter Zeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-196">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="ff1eb-197">Sie können die Pipeline verwenden, um einen Dienstnamen an zu senden `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-197">You can use the pipeline to send a service name to `Set-Service`.</span></span>

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

### <span data-ttu-id="ff1eb-198">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ff1eb-198">-PassThru</span></span>

<span data-ttu-id="ff1eb-199">Gibt ein **ServiceController** -Objekt zurück, das die geänderten Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-199">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="ff1eb-200">Standardmäßig `Set-Service` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-200">By default, `Set-Service` doesn't generate any output.</span></span>

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

### <span data-ttu-id="ff1eb-201">-StartupType</span><span class="sxs-lookup"><span data-stu-id="ff1eb-201">-StartupType</span></span>

<span data-ttu-id="ff1eb-202">Gibt den Startmodus des Diensts an</span><span class="sxs-lookup"><span data-stu-id="ff1eb-202">Specifies the start mode of the service.</span></span>

<span data-ttu-id="ff1eb-203">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ff1eb-203">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="ff1eb-204">**Automatisch** : der Dienst wurde gestartet oder vom Betriebssystem beim Systemstart gestartet.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-204">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="ff1eb-205">Wenn ein automatisch gestarteter Dienst von einem manuell gestarteten Dienst abhängig ist, wird der manuell gestartete Dienst beim Systemstart ebenfalls automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-205">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="ff1eb-206">**Automaticdelayedstart** : startet kurz nach dem Systemstart.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-206">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="ff1eb-207">**Deaktiviert** : der Dienst ist deaktiviert und kann nicht von einem Benutzer oder einer Anwendung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-207">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="ff1eb-208">**Invalidvalue** : hat keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-208">**InvalidValue** - Has no effect.</span></span> <span data-ttu-id="ff1eb-209">Das Cmdlet gibt keinen Fehler zurück, aber der startupType des Dienstanbieter wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-209">The cmdlet does not return an error but the StartupType of the service is not changed.</span></span>
- <span data-ttu-id="ff1eb-210">**Manuell: der** Dienst wird nur manuell von einem Benutzer, über den Dienststeuerungs-Manager oder durch eine Anwendung gestartet.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-210">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases: StartMode, SM, ST, StartType
Accepted values: Automatic, AutomaticDelayedStart, Disabled, InvalidValue, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ff1eb-211">-Status</span><span class="sxs-lookup"><span data-stu-id="ff1eb-211">-Status</span></span>

<span data-ttu-id="ff1eb-212">Gibt den Status für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-212">Specifies the status for the service.</span></span>

<span data-ttu-id="ff1eb-213">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ff1eb-213">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="ff1eb-214">**Angeh** alten.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-214">**Paused**.</span></span> <span data-ttu-id="ff1eb-215">Hält den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-215">Suspends the service.</span></span>
- <span data-ttu-id="ff1eb-216">**Wird ausgeführt**.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-216">**Running**.</span></span> <span data-ttu-id="ff1eb-217">Startet den Dienst.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-217">Starts the service.</span></span>
- <span data-ttu-id="ff1eb-218">**Stopped**(Beendet): Dies ist der anfängliche Status des Kanals nach seiner Erstellung (es sei denn, im Portal wurde das automatische Starten gewählt).</span><span class="sxs-lookup"><span data-stu-id="ff1eb-218">**Stopped**.</span></span> <span data-ttu-id="ff1eb-219">Beendet den Dienst.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-219">Stops the service.</span></span>

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

### <span data-ttu-id="ff1eb-220">-SecurityDescriptor SDDL</span><span class="sxs-lookup"><span data-stu-id="ff1eb-220">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="ff1eb-221">Gibt den **securityDescriptor** für den Dienst im **SDDL** -Format an.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-221">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

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

### <span data-ttu-id="ff1eb-222">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ff1eb-222">-WhatIf</span></span>

<span data-ttu-id="ff1eb-223">Zeigt, was geschieht, wenn ausgeführt wird `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-223">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="ff1eb-224">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-224">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="ff1eb-225">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ff1eb-225">CommonParameters</span></span>

<span data-ttu-id="ff1eb-226">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-226">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ff1eb-227">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ff1eb-227">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ff1eb-228">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ff1eb-228">INPUTS</span></span>

### <span data-ttu-id="ff1eb-229">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="ff1eb-229">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="ff1eb-230">Sie können die Pipeline verwenden, um ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, an zu senden `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-230">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="ff1eb-231">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ff1eb-231">OUTPUTS</span></span>

### <span data-ttu-id="ff1eb-232">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="ff1eb-232">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="ff1eb-233">Standardmäßig `Set-Service` gibt keine-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-233">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="ff1eb-234">Verwenden Sie den **passthru** -Parameter, um ein **ServiceController** -Objekt auszugeben.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-234">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="ff1eb-235">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ff1eb-235">NOTES</span></span>

<span data-ttu-id="ff1eb-236">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-236">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="ff1eb-237">`Set-Service` erfordert erweiterte Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-237">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="ff1eb-238">Verwenden Sie die Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-238">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="ff1eb-239">`Set-Service` Es können nur Dienste gesteuert werden, wenn der aktuelle Benutzer über Berechtigungen zum Verwalten von Diensten verfügt.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-239">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="ff1eb-240">Wenn ein Befehl nicht ordnungsgemäß funktioniert, verfügen Sie möglicherweise nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="ff1eb-240">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="ff1eb-241">Verwenden Sie, um den Dienstnamen oder anzeigen Amen eines Dienstanbieter zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-241">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="ff1eb-242">Die Dienstnamen befinden sich in der Spalte **Name** und die anzeigen Amen in der Spalte **Display Name** .</span><span class="sxs-lookup"><span data-stu-id="ff1eb-242">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="ff1eb-243">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ff1eb-243">RELATED LINKS</span></span>

[<span data-ttu-id="ff1eb-244">Get-Service</span><span class="sxs-lookup"><span data-stu-id="ff1eb-244">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="ff1eb-245">New-Service</span><span class="sxs-lookup"><span data-stu-id="ff1eb-245">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="ff1eb-246">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="ff1eb-246">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="ff1eb-247">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="ff1eb-247">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="ff1eb-248">Start-Service</span><span class="sxs-lookup"><span data-stu-id="ff1eb-248">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="ff1eb-249">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="ff1eb-249">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="ff1eb-250">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="ff1eb-250">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="ff1eb-251">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="ff1eb-251">Remove-Service</span></span>](Remove-Service.md)
