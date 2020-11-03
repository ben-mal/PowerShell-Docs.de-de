---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Computer
ms.openlocfilehash: 89e43220a8d5ac675ea232db09cf3edec2ca2b97
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214559"
---
# <span data-ttu-id="8f8ce-103">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="8f8ce-103">Remove-Computer</span></span>

## <span data-ttu-id="8f8ce-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8f8ce-104">SYNOPSIS</span></span>
<span data-ttu-id="8f8ce-105">Entfernt den lokalen Computer aus seiner Domäne.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-105">Removes the local computer from its domain.</span></span>

## <span data-ttu-id="8f8ce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8f8ce-106">SYNTAX</span></span>

### <span data-ttu-id="8f8ce-107">Local (Standard)</span><span class="sxs-lookup"><span data-stu-id="8f8ce-107">Local (Default)</span></span>

```
Remove-Computer [[-UnjoinDomainCredential] <PSCredential>] [-Restart] [-Force] [-PassThru]
 [-WorkgroupName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8f8ce-108">Remote</span><span class="sxs-lookup"><span data-stu-id="8f8ce-108">Remote</span></span>

```
Remove-Computer -UnjoinDomainCredential <PSCredential> [-LocalCredential <PSCredential>] [-Restart]
 [-ComputerName <String[]>] [-Force] [-PassThru] [-WorkgroupName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="8f8ce-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8f8ce-109">DESCRIPTION</span></span>

<span data-ttu-id="8f8ce-110">Mit dem `Remove-Computer` -Cmdlet werden der lokale Computer und Remote Computer aus den aktuellen Domänen entfernt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-110">The `Remove-Computer` cmdlet removes the local computer and remote computers from their current domains.</span></span>

<span data-ttu-id="8f8ce-111">Wenn Sie einen Computer aus einer Domäne entfernen, wird `Remove-Computer` von auch das Domänen Konto des Computers deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-111">When you remove a computer from a domain, `Remove-Computer` also disables the domain account of the computer.</span></span> <span data-ttu-id="8f8ce-112">Sie müssen explizite Anmelde Informationen angeben, um den Computer aus seiner Domäne zu entfernen, selbst wenn es sich um die Anmelde Informationen des aktuellen Benutzers handelt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-112">You must provide explicit credentials to unjoin the computer from its domain, even when they are the credentials of the current user.</span></span> <span data-ttu-id="8f8ce-113">Sie müssen den Computer neu starten, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-113">You must restart the computer to make the change effective.</span></span> <span data-ttu-id="8f8ce-114">Darüber hinaus muss ein Computer, wenn er aus einer Domäne entfernt wird, in eine Arbeitsgruppe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-114">Also, when you remove a computer from a domain, you must move it to a workgroup.</span></span> <span data-ttu-id="8f8ce-115">Geben Sie mithilfe des **WorkgroupName** -Parameters die Arbeitsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-115">Use the **WorkgroupName** parameter to specify the workgroup.</span></span>

<span data-ttu-id="8f8ce-116">Mit dem Cmdlet `Add-Computer` verschieben Sie einen Computer von einer Arbeitsgruppe in eine Domäne, von einer Arbeitsgruppe in eine andere Arbeitsgruppe oder von einer Domäne in eine andere Domäne.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-116">To move a computer from a workgroup to a domain, from one workgroup to another, or from one domain to another, use the `Add-Computer` cmdlet.</span></span>

<span data-ttu-id="8f8ce-117">Rufen Sie die Ergebnisse des Befehls mit dem **Verbose** - und dem **PassThru** -Parameter ab.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-117">To get the results of the command, use the **Verbose** and **PassThru** parameters.</span></span> <span data-ttu-id="8f8ce-118">Unterdrücken Sie die Benutzerbestätigung mithilfe des **Force** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-118">To suppress the user prompt, use the **Force** parameter.</span></span>

<span data-ttu-id="8f8ce-119">`Remove-Computer` entfernt den lokalen Computer und Remote Computer aus Domänen.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-119">`Remove-Computer` removes the local computer and remote computers from domains.</span></span> <span data-ttu-id="8f8ce-120">Das Cmdlet enthält Anmeldeinformationsparameter, die alternative Anmeldeinformationen für das Herstellen einer Verbindung mit Remotecomputern und das Entfernen aus einer Domäne angeben. Außerdem enthält es einen **Restart** -Parameter zum Neustarten der betroffenen Computer und einen **WorkgroupName** -Parameter zum Angeben des Namens der Arbeitsgruppe, der Computer hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-120">It includes credential parameters that specify alternate credentials for connecting to remote computers, and unjoining from a domain, a **Restart** parameter for restarting the affected computers, and a **WorkgroupName** parameter for specifying the name of the workgroup to which computers are added.</span></span>

## <span data-ttu-id="8f8ce-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8f8ce-121">EXAMPLES</span></span>

### <span data-ttu-id="8f8ce-122">Beispiel 1: Entfernen des lokalen Computers aus seiner Domäne</span><span class="sxs-lookup"><span data-stu-id="8f8ce-122">Example 1: Remove the local computer from its domain</span></span>

<span data-ttu-id="8f8ce-123">In diesem Beispiel wird der lokale Computer aus der Domäne entfernt, der er hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-123">This example removes the local computer from the domain to which it is joined.</span></span>

```powershell
Remove-Computer -UnjoinDomaincredential Domain01\Admin01 -PassThru -Verbose -Restart
```

<span data-ttu-id="8f8ce-124">Der **unjoindomaincredential** -Parameter stellt die Anmelde Informationen eines Domänen Administrators bereit.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-124">The **UnjoinDomainCredential** parameter provides the credentials of a domain administrator.</span></span> <span data-ttu-id="8f8ce-125">Der **passthru** -Parameter und der ausführliche allgemeine Parameter zeigen Informationen zum Erfolg oder fehl **schlagen** des Befehls an.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-125">The **PassThru** and the **Verbose** common parameters display information about the success or failure of the command.</span></span> <span data-ttu-id="8f8ce-126">Mit dem **Restart** -Parameter wird der Computer neu gestartet, um den Entfernungs Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-126">The **Restart** parameter restarts the computer to complete the remove operation.</span></span>

<span data-ttu-id="8f8ce-127">Wenn kein Arbeitsgruppen Name angegeben wird, wird der Computer nach dem Entfernen aus der Domäne in die Arbeitsgruppe verschoben.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-127">When no workgroup name is specified, the computer is moved to the workgroup named after it is removed from its domain.</span></span>

### <span data-ttu-id="8f8ce-128">Beispiel 2: Verschieben mehrerer Computer in eine ältere Arbeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="8f8ce-128">Example 2: Move several computers to a legacy workgroup</span></span>

<span data-ttu-id="8f8ce-129">In diesem Beispiel werden alle Computer, die in der Datei aufgelistet sind, `OldServers.txt` aus Ihren Domänen entfernt und in die **Legacy** Arbeitsgruppe verschoben.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-129">This example removes all the computers listed in the `OldServers.txt` file from their domains and moves them into the **Legacy** workgroup.</span></span>

```powershell
Remove-Computer -ComputerName (Get-Content OldServers.txt) -LocalCredential Domain01\Admin01 -UnJoinDomainCredential Domain01\Admin01 -WorkgroupName "Legacy" -Force -Restart
```

<span data-ttu-id="8f8ce-130">Der **localcredential** -Parameter stellt die Anmelde Informationen eines Benutzers bereit, der über die Berechtigung zum Herstellen einer Verbindung mit Remote Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-130">The **LocalCredential** parameter provides the credentials of a user who has permission to connect to remote computers.</span></span> <span data-ttu-id="8f8ce-131">Der **unjoindomaincredential** -Parameter stellt die Anmelde Informationen eines Benutzers bereit, der über die Berechtigung zum Entfernen der Computer aus Ihren Domänen verfügt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-131">The **UnjoinDomainCredential** parameter provides the credentials of a user who has permission to remove the computers from their domains.</span></span> <span data-ttu-id="8f8ce-132">Der **Force** -Parameter unterdrückt die Bestätigungs Aufforderungen für die einzelnen Computer.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-132">The **Force** parameter suppresses the confirmation prompts for each computer.</span></span> <span data-ttu-id="8f8ce-133">Mit dem **Restart** -Parameter werden die Computer neu gestartet, nachdem Sie aus der Domäne entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-133">The **Restart** parameter restarts each of the computers after it is removed from its domain.</span></span>

### <span data-ttu-id="8f8ce-134">Beispiel 3: Entfernen von Computern aus einer Arbeitsgruppe ohne Bestätigung</span><span class="sxs-lookup"><span data-stu-id="8f8ce-134">Example 3: Remove computers from a workgroup without confirmation</span></span>

<span data-ttu-id="8f8ce-135">In diesem Beispiel werden der Remote Computer, Server01 und der lokale Computer aus den Domänen entfernt und der **lokalen** Arbeitsgruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-135">This example removes the remote computer, Server01, and the local computer from their domains and adds them to the **Local** workgroup.</span></span>

```powershell
Remove-Computer -ComputerName "Server01", "localhost" -UnjoinDomainCredential Domain01\Admin01 -WorkgroupName "Local" -Restart -Force
```

<span data-ttu-id="8f8ce-136">Der **Force** -Parameter unterdrückt die Bestätigungsaufforderung für jeden Computer.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-136">The **Force** parameter suppresses the confirmation prompt for each computer.</span></span> <span data-ttu-id="8f8ce-137">Mit dem **Restart** -Parameter werden die Computer neu gestartet, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-137">The **Restart** parameter restarts the computers to make the change effective.</span></span>

## <span data-ttu-id="8f8ce-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8f8ce-138">PARAMETERS</span></span>

### <span data-ttu-id="8f8ce-139">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="8f8ce-139">-ComputerName</span></span>

<span data-ttu-id="8f8ce-140">Gibt die Computer an, die aus ihren Domänen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-140">Specifies the computers to be removed from their domains.</span></span> <span data-ttu-id="8f8ce-141">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-141">The default is the local computer.</span></span>

<span data-ttu-id="8f8ce-142">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) der Remote Computer ein.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-142">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of the remote computers.</span></span> <span data-ttu-id="8f8ce-143">Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-143">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="8f8ce-144">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-144">This parameter does not rely on PowerShell remoting.</span></span> <span data-ttu-id="8f8ce-145">Sie können den **Computername** -Parameter `Remove-Computer` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-145">You can use the **ComputerName** parameter of `Remove-Computer` even if your computer is not configured to run remote commands.</span></span>

<span data-ttu-id="8f8ce-146">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-146">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8f8ce-147">-Force</span><span class="sxs-lookup"><span data-stu-id="8f8ce-147">-Force</span></span>

<span data-ttu-id="8f8ce-148">Unterdrückt die Benutzeraufforderung.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-148">Suppresses the user prompt.</span></span> <span data-ttu-id="8f8ce-149">Standardmäßig werden `Remove-Computer` Sie von zur Bestätigung aufgefordert, bevor die einzelnen Computer entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-149">By default, `Remove-Computer` prompts you for confirmation before removing each computer.</span></span>

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

### <span data-ttu-id="8f8ce-150">-Localcredential</span><span class="sxs-lookup"><span data-stu-id="8f8ce-150">-LocalCredential</span></span>

<span data-ttu-id="8f8ce-151">Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit den Computern verfügt, die vom Parameter **Computername** angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-151">Specifies a user account that has permission to connect to the computers that the **ComputerName** parameter specifies.</span></span> <span data-ttu-id="8f8ce-152">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-152">The default is the current user.</span></span>

<span data-ttu-id="8f8ce-153">Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-153">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="8f8ce-154">Wenn Sie einen Benutzernamen eingeben, werden Sie vom Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-154">If you type a user name, the cmdlet prompts you for a password.</span></span> <span data-ttu-id="8f8ce-155">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Entfernen des Computers aus der aktuellen Domäne verfügt, mit dem **UnjoinDomainCredential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-155">To specify a user account that has permission to remove the computer from its current domain, use the **UnjoinDomainCredential** parameter.</span></span>

<span data-ttu-id="8f8ce-156">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-156">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f8ce-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8f8ce-157">-PassThru</span></span>

<span data-ttu-id="8f8ce-158">Gibt die Ergebnisse des Befehls zurück.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-158">Returns the results of the command.</span></span> <span data-ttu-id="8f8ce-159">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-159">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="8f8ce-160">-Restart</span><span class="sxs-lookup"><span data-stu-id="8f8ce-160">-Restart</span></span>

<span data-ttu-id="8f8ce-161">Gibt an, dass mit diesem Cmdlet die zu entfernende Computer neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-161">Indicates that this cmdlet restarts the computers that are being removed.</span></span> <span data-ttu-id="8f8ce-162">Ein Neustart ist häufig erforderlich, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-162">A restart is often required to make the change effective.</span></span>

<span data-ttu-id="8f8ce-163">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-163">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8f8ce-164">-Unjoindomaincredential</span><span class="sxs-lookup"><span data-stu-id="8f8ce-164">-UnjoinDomainCredential</span></span>

<span data-ttu-id="8f8ce-165">Gibt ein Benutzerkonto an, das über die Berechtigung zum Entfernen der Computer aus ihren aktuellen Domänen verfügt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-165">Specifies a user account that has permission to remove the computers from their current domains.</span></span>
<span data-ttu-id="8f8ce-166">Explizite Anmeldeinformationen, wie sie von diesem Parameter bereitgestellt werden, sind erforderlich, um Remotecomputer aus einer Domäne zu entfernen, auch wenn der Wert die Anmeldeinformationen des aktuellen Benutzers darstellt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-166">Explicit credentials, as provided by this parameter, are required to remove remote computers from a domain, even when the value is the credentials of the current user.</span></span>

<span data-ttu-id="8f8ce-167">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. das von generierte `Get-Credential` .</span><span class="sxs-lookup"><span data-stu-id="8f8ce-167">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by `Get-Credential`.</span></span> <span data-ttu-id="8f8ce-168">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-168">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="8f8ce-169">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit Remotecomputern verfügt, mit dem **LocalCredential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-169">To specify a user account that has permission to connect to the remote computers, use the **LocalCredential** parameter.</span></span>

<span data-ttu-id="8f8ce-170">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-170">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Local, Remote
Aliases: Credential

Required: False (Local), True (Remote)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f8ce-171">-Workgroupname</span><span class="sxs-lookup"><span data-stu-id="8f8ce-171">-WorkgroupName</span></span>

<span data-ttu-id="8f8ce-172">Gibt den Namen einer Arbeitsgruppe an, der die Computer nach dem Entfernen aus den Domänen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-172">Specifies the name of a workgroup to which the computers are added when they are removed from their domains.</span></span> <span data-ttu-id="8f8ce-173">Der Standardwert ist **Workgroup** .</span><span class="sxs-lookup"><span data-stu-id="8f8ce-173">The default value is **WORKGROUP** .</span></span> <span data-ttu-id="8f8ce-174">Wenn ein Computer aus einer Domäne entfernt wird, muss er einer Arbeitsgruppe hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-174">When you remove a computer from a domain, you must add it to a workgroup.</span></span>

<span data-ttu-id="8f8ce-175">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-175">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8f8ce-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8f8ce-176">-Confirm</span></span>

<span data-ttu-id="8f8ce-177">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8f8ce-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8f8ce-178">-WhatIf</span></span>

<span data-ttu-id="8f8ce-179">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-179">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="8f8ce-180">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8f8ce-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8f8ce-181">CommonParameters</span></span>

<span data-ttu-id="8f8ce-182">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8f8ce-183">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8f8ce-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8f8ce-184">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8f8ce-184">INPUTS</span></span>

### <span data-ttu-id="8f8ce-185">System.String</span><span class="sxs-lookup"><span data-stu-id="8f8ce-185">System.String</span></span>

<span data-ttu-id="8f8ce-186">Sie können Computernamen an das thiscmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-186">You can pipe computer names to thiscmdlet.</span></span>

## <span data-ttu-id="8f8ce-187">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8f8ce-187">OUTPUTS</span></span>

### <span data-ttu-id="8f8ce-188">Microsoft. PowerShell. Commands. computerchangeingefo</span><span class="sxs-lookup"><span data-stu-id="8f8ce-188">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="8f8ce-189">Wenn Sie den **passthru** -Parameter verwenden, wird `Remove-Computer` ein **computerchangeinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-189">When you use the **PassThru** parameter, `Remove-Computer` returns a **ComputerChangeInfo** object.</span></span>
<span data-ttu-id="8f8ce-190">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-190">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="8f8ce-191">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8f8ce-191">NOTES</span></span>

<span data-ttu-id="8f8ce-192">Mit diesem Cmdlet werden keine Computer aus Arbeitsgruppen entfernt.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-192">This cmdlet does not remove computers from workgroups.</span></span>

## <span data-ttu-id="8f8ce-193">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8f8ce-193">RELATED LINKS</span></span>

[<span data-ttu-id="8f8ce-194">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="8f8ce-194">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="8f8ce-195">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="8f8ce-195">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="8f8ce-196">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="8f8ce-196">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="8f8ce-197">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="8f8ce-197">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="8f8ce-198">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="8f8ce-198">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="8f8ce-199">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="8f8ce-199">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="8f8ce-200">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="8f8ce-200">Stop-Computer</span></span>](Stop-Computer.md)

[<span data-ttu-id="8f8ce-201">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="8f8ce-201">Test-Connection</span></span>](Test-Connection.md)
