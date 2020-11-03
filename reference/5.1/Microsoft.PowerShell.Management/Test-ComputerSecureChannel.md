---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-computersecurechannel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ComputerSecureChannel
ms.openlocfilehash: 20ea76e725a8ab53d7090078dc819a6297a639ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214343"
---
# <span data-ttu-id="49732-103">Test-ComputerSecureChannel</span><span class="sxs-lookup"><span data-stu-id="49732-103">Test-ComputerSecureChannel</span></span>

## <span data-ttu-id="49732-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="49732-104">SYNOPSIS</span></span>
<span data-ttu-id="49732-105">Testet und repariert den sicheren Channel zwischen dem lokalen Computer und seiner Domäne.</span><span class="sxs-lookup"><span data-stu-id="49732-105">Tests and repairs the secure channel between the local computer and its domain.</span></span>

## <span data-ttu-id="49732-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="49732-106">SYNTAX</span></span>

```
Test-ComputerSecureChannel [-Repair] [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="49732-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="49732-107">DESCRIPTION</span></span>
<span data-ttu-id="49732-108">Mit dem Cmdlet " **Test-computersecurechannel** " wird überprüft, ob der Kanal zwischen dem lokalen Computer und seiner Domäne ordnungsgemäß funktioniert, indem der Status der Vertrauens Stellungen überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="49732-108">The **Test-ComputerSecureChannel** cmdlet verifies that the channel between the local computer and its domain is working correctly by checking the status of its trust relationships.</span></span>
<span data-ttu-id="49732-109">Wenn eine Verbindung nicht hergestellt werden kann, können Sie den *Repair* -Parameter verwenden, um Sie wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="49732-109">If a connection fails, you can use the *Repair* parameter to try to restore it.</span></span>

<span data-ttu-id="49732-110">" **Test-computersecurechannel** " gibt $true zurück, wenn der Kanal ordnungsgemäß funktioniert, und $false andernfalls.</span><span class="sxs-lookup"><span data-stu-id="49732-110">**Test-ComputerSecureChannel** returns $True if the channel is working correctly and $False if it is not.</span></span>
<span data-ttu-id="49732-111">Durch dieses Ergebnis können Sie das Cmdlet in bedingten Anweisungen in Features und Skripts verwenden.</span><span class="sxs-lookup"><span data-stu-id="49732-111">This result lets you use the cmdlet in conditional statements in functions and scripts.</span></span>
<span data-ttu-id="49732-112">Um ausführlichere Testergebnisse zu erhalten, verwenden Sie den *verbose* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="49732-112">To get more detailed test results, use the *Verbose* parameter.</span></span>

<span data-ttu-id="49732-113">Die Funktion dieses Cmdlets ist vergleichbar mit %%amp;quot;NetDom.exe%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="49732-113">This cmdlet works much like NetDom.exe.</span></span>
<span data-ttu-id="49732-114">Netdom und **Test-computersecurechannel** verwenden den **Anmelde** Dienst, um die Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="49732-114">Both NetDom and **Test-ComputerSecureChannel** use the **NetLogon** service to perform the actions.</span></span>

## <span data-ttu-id="49732-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="49732-115">EXAMPLES</span></span>

### <span data-ttu-id="49732-116">Beispiel 1: Testen eines Kanals zwischen dem lokalen Computer und seiner Domäne</span><span class="sxs-lookup"><span data-stu-id="49732-116">Example 1: Test a channel between the local computer and its domain</span></span>

```
PS C:\> Test-ComputerSecureChannel
True
```

<span data-ttu-id="49732-117">Dieser Befehl testet den Kanal zwischen dem lokalen Computer und der Domäne, der er hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="49732-117">This command tests the channel between the local computer and the domain to which it is joined.</span></span>

### <span data-ttu-id="49732-118">Beispiel 2: Testen eines Kanals zwischen dem lokalen Computer und einem Domänen Controller</span><span class="sxs-lookup"><span data-stu-id="49732-118">Example 2: Test a channel between the local computer and a domain controller</span></span>

```
PS C:\> Test-ComputerSecureChannel -Server "DCName.fabrikam.com"
True
```

<span data-ttu-id="49732-119">Dieser Befehl gibt einen bevorzugten Domänencontroller für den Test an.</span><span class="sxs-lookup"><span data-stu-id="49732-119">This command specifies a preferred domain controller for the test.</span></span>

### <span data-ttu-id="49732-120">Beispiel 3: Zurücksetzen des Kanals zwischen dem lokalen Computer und seiner Domäne</span><span class="sxs-lookup"><span data-stu-id="49732-120">Example 3: Reset the channel between the local computer and its domain</span></span>

```
PS C:\> Test-ComputerSecureChannel -Repair
True
```

<span data-ttu-id="49732-121">Dieser Befehl setzt den Kanal zwischen dem lokalen Computer und seiner Domäne zurück.</span><span class="sxs-lookup"><span data-stu-id="49732-121">This command resets the channel between the local computer and its domain.</span></span>

### <span data-ttu-id="49732-122">Beispiel 4: Anzeigen detaillierter Informationen zum Test</span><span class="sxs-lookup"><span data-stu-id="49732-122">Example 4: Display detailed information about the test</span></span>

```
PS C:\> Test-ComputerSecureChannel -verbose
VERBOSE: Performing operation "Test-ComputerSecureChannel" on Target "SERVER01".
True
VERBOSE: "The secure channel between 'SERVER01' and 'net.fabrikam.com' is alive and working correctly."
```

<span data-ttu-id="49732-123">Dieser Befehl verwendet den allgemeinen *verbose* -Parameter, um ausführliche Meldungen zum Vorgang anzufordern.</span><span class="sxs-lookup"><span data-stu-id="49732-123">This command uses the *Verbose* common parameter to request detailed messages about the operation.</span></span>
<span data-ttu-id="49732-124">Weitere Informationen zu " *verbose* " finden Sie unter about_CommonParameters.</span><span class="sxs-lookup"><span data-stu-id="49732-124">For more information about *Verbose* , see about_CommonParameters.</span></span>

### <span data-ttu-id="49732-125">Beispiel 5: Testen einer Verbindung vor dem Ausführen eines Skripts</span><span class="sxs-lookup"><span data-stu-id="49732-125">Example 5: Test a connection before you run a script</span></span>

```
PS C:\> Set-Alias tcsc Test-ComputerSecureChannel
if (!(tcsc))
{Write-Host "Connection failed. Reconnect and retry."}
else { &(.\Get-Servers.ps1) }
```

<span data-ttu-id="49732-126">Dieses Beispiel zeigt, wie Sie mit **Test-computersecurechannel** eine Verbindung testen, bevor Sie ein Skript ausführen, das die Verbindung erfordert.</span><span class="sxs-lookup"><span data-stu-id="49732-126">This example shows how to use **Test-ComputerSecureChannel** to test a connection before you run a script that requires the connection.</span></span>

<span data-ttu-id="49732-127">Der erste Befehl erstellt mit dem Cmdlet %%amp;quot;Set-Alias%%amp;quot; einen Alias für den Cmdlet-Namen.</span><span class="sxs-lookup"><span data-stu-id="49732-127">The first command uses the Set-Alias cmdlet to create an alias for the cmdlet name.</span></span>
<span data-ttu-id="49732-128">So wird Speicherplatz gespart, und Tippfehler werden verhindert.</span><span class="sxs-lookup"><span data-stu-id="49732-128">This saves space and prevents typing errors.</span></span>

<span data-ttu-id="49732-129">Die **if** -Anweisung überprüft den von **Test-computersecurechannel** zurückgegebenen Wert, bevor ein Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49732-129">The **If** statement checks the value that **Test-ComputerSecureChannel** returns before it runs a script.</span></span>

## <span data-ttu-id="49732-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="49732-130">PARAMETERS</span></span>

### <span data-ttu-id="49732-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="49732-131">-Credential</span></span>
<span data-ttu-id="49732-132">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="49732-132">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="49732-133">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. das vom Get-Credential-Cmdlet zurückgegebene.</span><span class="sxs-lookup"><span data-stu-id="49732-133">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one that the Get-Credential cmdlet returns.</span></span>
<span data-ttu-id="49732-134">Standardmäßig verwendet das Cmdlet die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="49732-134">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="49732-135">Der *Credential* -Parameter ist für die Verwendung in Befehlen konzipiert, die den *Repair* -Parameter verwenden, um den Kanal zwischen dem Computer und der Domäne zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="49732-135">The *Credential* parameter is designed for use in commands that use the *Repair* parameter to repair the channel between the computer and the domain.</span></span>

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

### <span data-ttu-id="49732-136">-Repair</span><span class="sxs-lookup"><span data-stu-id="49732-136">-Repair</span></span>
<span data-ttu-id="49732-137">Gibt an, dass dieses Cmdlet den vom Anmeldedienst eingerichteten Kanal entfernt und anschließend neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="49732-137">Indicates that this cmdlet removes and then rebuilds the channel established by the NetLogon service.</span></span>
<span data-ttu-id="49732-138">Verwenden Sie diesen Parameter, um eine Verbindung wiederherzustellen, bei der der Test nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="49732-138">Use this parameter to try to restore a connection that has failed the test.</span></span>

<span data-ttu-id="49732-139">Um diesen Parameter zu verwenden, muss der aktuelle Benutzer Mitglied der Gruppe %%amp;quot;Administratoren%%amp;quot; auf dem lokalen Computer sein.</span><span class="sxs-lookup"><span data-stu-id="49732-139">To use this parameter, the current user must be a member of the Administrators group on the local computer.</span></span>

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

### <span data-ttu-id="49732-140">-Server</span><span class="sxs-lookup"><span data-stu-id="49732-140">-Server</span></span>
<span data-ttu-id="49732-141">Gibt den Domänen Controller an, auf dem der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49732-141">Specifies the domain controller to run the command.</span></span>
<span data-ttu-id="49732-142">Wenn dieser Parameter nicht angegeben wird, wählt dieses Cmdlet einen Standard Domänen Controller für den Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="49732-142">If this parameter is not specified, this cmdlet selects a default domain controller for the operation.</span></span>

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

### <span data-ttu-id="49732-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="49732-143">-Confirm</span></span>
<span data-ttu-id="49732-144">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="49732-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="49732-145">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="49732-145">-WhatIf</span></span>
<span data-ttu-id="49732-146">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49732-146">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="49732-147">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="49732-147">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="49732-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="49732-148">CommonParameters</span></span>
<span data-ttu-id="49732-149">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="49732-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="49732-150">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="49732-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="49732-151">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="49732-151">INPUTS</span></span>

### <span data-ttu-id="49732-152">Keine</span><span class="sxs-lookup"><span data-stu-id="49732-152">None</span></span>
<span data-ttu-id="49732-153">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="49732-153">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="49732-154">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="49732-154">OUTPUTS</span></span>

### <span data-ttu-id="49732-155">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="49732-155">System.Boolean</span></span>
<span data-ttu-id="49732-156">Dieses Cmdlet gibt $true zurück, wenn die Verbindung ordnungsgemäß funktioniert, und $false andernfalls.</span><span class="sxs-lookup"><span data-stu-id="49732-156">This cmdlet returns $True if the connection is working correctly and $False if it is not.</span></span>

## <span data-ttu-id="49732-157">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="49732-157">NOTES</span></span>

* <span data-ttu-id="49732-158">Öffnen Sie Windows PowerShell mit der Option als Administrator ausführen, um einen **Test-computersecurechannel** -Befehl unter Windows Vista und höheren Versionen des Windows-Betriebssystems auszuführen.</span><span class="sxs-lookup"><span data-stu-id="49732-158">To run a **Test-ComputerSecureChannel** command on Windows Vista and later versions of the Windows operating system, open Windows PowerShell by using the Run as administrator option.</span></span>
* <span data-ttu-id="49732-159">**Test-computersecurechannel** wird mithilfe der **I_NetLogonControl2** -Funktion implementiert, die verschiedene Aspekte des Netlogon-Diensts steuert.</span><span class="sxs-lookup"><span data-stu-id="49732-159">**Test-ComputerSecureChannel** is implemented by using the **I_NetLogonControl2** function, which controls various aspects of the Netlogon service.</span></span>

## <span data-ttu-id="49732-160">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="49732-160">RELATED LINKS</span></span>

[<span data-ttu-id="49732-161">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="49732-161">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="49732-162">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="49732-162">Reset-ComputerMachinePassword</span></span>](Reset-ComputerMachinePassword.md)

[<span data-ttu-id="49732-163">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="49732-163">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="49732-164">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="49732-164">Stop-Computer</span></span>](Stop-Computer.md)
