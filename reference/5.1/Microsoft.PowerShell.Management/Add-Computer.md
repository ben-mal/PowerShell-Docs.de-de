---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Computer
ms.openlocfilehash: e3d1c5c071a334bddbfbc547ef2cc07e9e5c90aa
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388347"
---
# <span data-ttu-id="b0857-103">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="b0857-103">Add-Computer</span></span>

## <span data-ttu-id="b0857-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b0857-104">SYNOPSIS</span></span>
<span data-ttu-id="b0857-105">Fügt den lokalen Computer einer Domäne oder Arbeitsgruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="b0857-105">Add the local computer to a domain or workgroup.</span></span>

## <span data-ttu-id="b0857-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b0857-106">SYNTAX</span></span>

### <span data-ttu-id="b0857-107">Domäne (Standard)</span><span class="sxs-lookup"><span data-stu-id="b0857-107">Domain (Default)</span></span>

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>]
 [-UnjoinDomainCredential <PSCredential>] -Credential <PSCredential> [-DomainName] <String> [-OUPath <String>]
 [-Server <String>] [-Unsecure] [-Options <JoinOptions>] [-Restart] [-PassThru] [-NewName <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b0857-108">Arbeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="b0857-108">Workgroup</span></span>

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>] [-Credential <PSCredential>]
 [-WorkgroupName] <String> [-Restart] [-PassThru] [-NewName <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="b0857-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b0857-109">DESCRIPTION</span></span>

<span data-ttu-id="b0857-110">Mit dem- `Add-Computer` Cmdlet werden der lokale Computer oder Remote Computer einer Domäne oder Arbeitsgruppe hinzugefügt oder von einer Domäne in eine andere verschoben.</span><span class="sxs-lookup"><span data-stu-id="b0857-110">The `Add-Computer` cmdlet adds the local computer or remote computers to a domain or workgroup, or moves them from one domain to another.</span></span> <span data-ttu-id="b0857-111">Außerdem erstellt das Cmdlet ein Domänenkonto, falls der Computer der Domäne ohne Konto hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b0857-111">It also creates a domain account if the computer is added to the domain without an account.</span></span>

<span data-ttu-id="b0857-112">Mit den Parametern dieses Cmdlets können Sie eine Organisationseinheit und einen Domänencontroller angeben oder einen unsicheren Beitritt ausführen.</span><span class="sxs-lookup"><span data-stu-id="b0857-112">You can use the parameters of this cmdlet to specify an organizational unit (OU) and domain controller or to perform an unsecure join.</span></span>

<span data-ttu-id="b0857-113">Rufen Sie die Ergebnisse des Befehls mit dem **Verbose** - und dem **PassThru** -Parameter ab.</span><span class="sxs-lookup"><span data-stu-id="b0857-113">To get the results of the command, use the **Verbose** and **PassThru** parameters.</span></span>

## <span data-ttu-id="b0857-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b0857-114">EXAMPLES</span></span>

### <span data-ttu-id="b0857-115">Beispiel 1: Hinzufügen eines lokalen Computers zu einer Domäne und Neustarten des Computers</span><span class="sxs-lookup"><span data-stu-id="b0857-115">Example 1: Add a local computer to a domain then restart the computer</span></span>

```powershell
Add-Computer -DomainName Domain01 -Restart
```

<span data-ttu-id="b0857-116">Mit diesem Befehl wird der lokale Computer der Domäne %%amp;quot;Domain01%%amp;quot; hinzugefügt und anschließend neu gestartet, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="b0857-116">This command adds the local computer to the Domain01 domain and then restarts the computer to make the change effective.</span></span>

### <span data-ttu-id="b0857-117">Beispiel 2: Hinzufügen eines lokalen Computers zu einer Arbeitsgruppe</span><span class="sxs-lookup"><span data-stu-id="b0857-117">Example 2: Add a local computer to a workgroup</span></span>

```powershell
Add-Computer -WorkgroupName WORKGROUP-A
```

<span data-ttu-id="b0857-118">Mit diesem Befehl wird der lokale Computer der Arbeitsgruppe %%amp;quot;Workgroup-A%%amp;quot; hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-118">This command adds the local computer to the Workgroup-A workgroup.</span></span>

### <span data-ttu-id="b0857-119">Beispiel 3: Hinzufügen eines lokalen Computers zu einer Domäne</span><span class="sxs-lookup"><span data-stu-id="b0857-119">Example 3: Add a local computer to a domain</span></span>

```powershell
Add-Computer -DomainName Domain01 -Server Domain01\DC01 -PassThru -Verbose
```

<span data-ttu-id="b0857-120">Dieser Befehl fügt den lokalen Computer unter Verwendung des Domänencontrollers %%amp;quot;Domain01\DC01%%amp;quot; der Domäne %%amp;quot;Domain01%%amp;quot; hinzu.</span><span class="sxs-lookup"><span data-stu-id="b0857-120">This command adds the local computer to the Domain01 domain by using the Domain01\DC01 domain controller.</span></span>

<span data-ttu-id="b0857-121">Der Befehl ruft mit dem **PassThru** -Parameter und dem **Verbose** -Parameter ausführliche Informationen zu den Ergebnissen des Befehls ab.</span><span class="sxs-lookup"><span data-stu-id="b0857-121">The command uses the **PassThru** and **Verbose** parameters to get detailed information about the results of the command.</span></span>

### <span data-ttu-id="b0857-122">Beispiel 4: Hinzufügen eines lokalen Computers zu einer Domäne mithilfe des oupath-Parameters</span><span class="sxs-lookup"><span data-stu-id="b0857-122">Example 4: Add a local computer to a domain using the OUPath parameter</span></span>

```powershell
Add-Computer -DomainName Domain02 -OUPath "OU=testOU,DC=domain,DC=Domain,DC=com"
```

<span data-ttu-id="b0857-123">Mit diesem Befehl wird der lokale Computer der Domäne %%amp;quot;Domain02%%amp;quot; hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-123">This command adds the local computer to the Domain02 domain.</span></span>
<span data-ttu-id="b0857-124">Dabei wird mit dem Parameter %%amp;quot;OUPath%%amp;quot; die Organisationseinheit für die neuen Konten angegeben.</span><span class="sxs-lookup"><span data-stu-id="b0857-124">It uses the OUPath parameter to specify the organizational unit for the new accounts.</span></span>

### <span data-ttu-id="b0857-125">Beispiel 5: Hinzufügen eines lokalen Computers zu einer Domäne mithilfe von Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="b0857-125">Example 5: Add a local computer to a domain using credentials</span></span>

```powershell
Add-Computer -ComputerName Server01 -LocalCredential Server01\Admin01 -DomainName Domain02 -Credential Domain02\Admin02 -Restart -Force
```

<span data-ttu-id="b0857-126">Mit diesem Befehl wird der Computer %%amp;quot;Server01%%amp;quot; der Domäne %%amp;quot;Domain02%%amp;quot; hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-126">This command adds the Server01 computer to the Domain02 domain.</span></span> <span data-ttu-id="b0857-127">Mit dem **LocalCredential** -Parameter wird ein Benutzerkonto angegeben, das über die Berechtigung zum Herstellen einer Verbindung mit dem Computer %%amp;quot;Server01%%amp;quot; verfügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-127">It uses the **LocalCredential** parameter to specify a user account that has permission to connect to the Server01 computer.</span></span> <span data-ttu-id="b0857-128">Mit dem **Credential** -Parameter wird ein Benutzerkonto angegeben, das über die Berechtigung zum Hinzufügen von Computern zur Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-128">It uses the **Credential** parameter to specify a user account that has permission to join computers to the domain.</span></span> <span data-ttu-id="b0857-129">Mit dem **Restart** -Parameter wird der Computer nach Abschluss des Beitrittsvorgangs neu gestartet. Mit dem **Force** -Parameter werden Meldungen zur Benutzerbestätigung unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="b0857-129">It uses the **Restart** parameter to restart the computer after the join operation completes and the **Force** parameter to suppress user confirmation messages.</span></span>

### <span data-ttu-id="b0857-130">Beispiel 6: Verschieben einer Gruppe von Computern in eine neue Domäne</span><span class="sxs-lookup"><span data-stu-id="b0857-130">Example 6: Move a group of computers to a new domain</span></span>

```powershell
Add-Computer -ComputerName Server01, Server02, localhost -DomainName Domain02 -LocalCredential Domain01\User01 -UnjoinDomainCredential Domain01\Admin01 -Credential Domain02\Admin01 -Restart
```

<span data-ttu-id="b0857-131">Mit diesem Befehl werden der Computer %%amp;quot;Server01%%amp;quot;, der Computer %%amp;quot;Server02%%amp;quot; und der lokale Computer von %%amp;quot;Domain01%%amp;quot; in %%amp;quot;Domain02%%amp;quot; verschoben.</span><span class="sxs-lookup"><span data-stu-id="b0857-131">This command moves the Server01 and Server02 computers, and the local computer, from Domain01 to Domain02.</span></span>

<span data-ttu-id="b0857-132">Mit dem **LocalCredential** -Parameter wird ein Benutzerkonto angegeben, das über die Berechtigung zum Herstellen einer Verbindung mit den drei betroffenen Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-132">It uses the **LocalCredential** parameter to specify a user account that has permission to connect to the three affected computers.</span></span> <span data-ttu-id="b0857-133">Mit dem **UnjoinDomainCredential** -Parameter wird ein Benutzerkonto angegeben, das über die Berechtigung zum Trennen der Computer von der Domäne %%amp;quot;Domain01%%amp;quot; verfügt, und mit dem **Credential** -Parameter wird ein Benutzerkonto angegeben, das über die Berechtigung zum Entfernen der Computer aus der Domäne %%amp;quot;Domain02%%amp;quot; verfügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-133">It uses the **UnjoinDomainCredential** parameter to specify a user account that has permission to unjoin the computers from the Domain01 domain and the **Credential** parameter to specify a user account that has permission to join the computers to the Domain02 domain.</span></span> <span data-ttu-id="b0857-134">Mit dem **Restart** -Parameter werden alle drei Computer nach dem Verschieben neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="b0857-134">It uses the **Restart** parameter to restart all three computers after the move is complete.</span></span>

### <span data-ttu-id="b0857-135">Beispiel 7: Verschieben eines Computers in eine neue Domäne und Ändern des Namens des Computers</span><span class="sxs-lookup"><span data-stu-id="b0857-135">Example 7: Move a computer to a new domain and change the name of the computer</span></span>

```powershell
Add-Computer -ComputerName Server01 -DomainName Domain02 -NewName Server044 -Credential Domain02\Admin01 -Restart
```

<span data-ttu-id="b0857-136">Mit diesem Befehl wird der Computer %%amp;quot;Server01%%amp;quot; in die Domäne %%amp;quot;Domain02%%amp;quot; verschoben, und der Computername wird in %%amp;quot;Server044%%amp;quot; geändert.</span><span class="sxs-lookup"><span data-stu-id="b0857-136">This command moves the Server01 computer to the Domain02 and changes the machine name to Server044.</span></span>

<span data-ttu-id="b0857-137">Der Befehl verwendet die Anmeldeinformationen des aktuellen Benutzers, um eine Verbindung mit dem Computer %%amp;quot;Server01%%amp;quot; herzustellen und ihn aus der aktuellen Domäne zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b0857-137">The command uses the credential of the current user to connect to the Server01 computer and unjoin it from its current domain.</span></span> <span data-ttu-id="b0857-138">Er verwendet den **Credential** -Parameter, um ein Benutzerkonto anzugeben, das über die Berechtigung zum Hinzufügen des Computers zur Domain02-Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-138">It uses the **Credential** parameter to specify a user account that has permission to join the computer to the Domain02 domain.</span></span>

### <span data-ttu-id="b0857-139">Beispiel 8: Hinzufügen von in einer Datei aufgeführten Computern zu einer neuen Domäne</span><span class="sxs-lookup"><span data-stu-id="b0857-139">Example 8: Add computers listed in a file to a new domain</span></span>

```powershell
Add-Computer -ComputerName (Get-Content Servers.txt) -DomainName Domain02 -Credential Domain02\Admin02 -Options Win9xUpgrade  -Restart
```

<span data-ttu-id="b0857-140">Mit diesem Befehl werden die in der Datei %%amp;quot;Servers.txt%%amp;quot; aufgeführten Computer der Domäne %%amp;quot;Domain02%%amp;quot; hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-140">This command adds the computers that are listed in the Servers.txt file to the Domain02 domain.</span></span> <span data-ttu-id="b0857-141">Mit dem **Options** -Parameter wird die **Win9xUpgrade** -Option angegeben.</span><span class="sxs-lookup"><span data-stu-id="b0857-141">It uses the **Options** parameter to specify the **Win9xUpgrade** option.</span></span> <span data-ttu-id="b0857-142">Mit dem **Restart** -Parameter werden alle neu hinzugefügten Computer nach dem Beitrittsvorgang neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="b0857-142">The **Restart** parameter restarts all of the newly added computers after the join operation completes.</span></span>

### <span data-ttu-id="b0857-143">Beispiel 9: Hinzufügen eines Computers zu einer Domäne mithilfe vordefinierter Computer Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="b0857-143">Example 9: Add a computer to a domain using predefined computer credentials</span></span>

<span data-ttu-id="b0857-144">Der erste Befehl sollte von einem Administrator auf einem Computer ausgeführt werden, der bereits der Domäne beigetreten ist `Domain03` :</span><span class="sxs-lookup"><span data-stu-id="b0857-144">This first command should be run by an administrator from a computer that is already joined to domain `Domain03`:</span></span>

```powershell
New-ADComputer -Name "Server02" -AccountPassword (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)

# Then this command is run from `Server02` which is not yet domain-joined:

$joinCred = New-Object pscredential -ArgumentList ([pscustomobject]@{
    UserName = $null
    Password = (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)[0]
})
Add-Computer -Domain "Domain03" -Options UnsecuredJoin,PasswordPass -Credential $joinCred
```

<span data-ttu-id="b0857-145">Diese Kombination von Befehlen erstellt ein neues Computer Konto mit einem vordefinierten Namen und einem temporären joinkennwort in einer Domäne mithilfe eines vorhandenen, in die Domäne eingebundenen Computers.</span><span class="sxs-lookup"><span data-stu-id="b0857-145">This combination of commands creates a new computer account with a predefined name and temporary join password in a domain using an existing domain-joined computer.</span></span> <span data-ttu-id="b0857-146">Ein Computer mit dem vordefinierten Namen wird dann separat mit dem Computernamen und dem Kennwort für den temporären Join verknüpft.</span><span class="sxs-lookup"><span data-stu-id="b0857-146">Then separately, a computer with the predefined name joins the domain using only the computer name and the temporary join password.</span></span>
<span data-ttu-id="b0857-147">Das vordefinierte Kennwort wird nur zur Unterstützung des Join-Vorgangs verwendet und als Teil der normalen Computer Konto Prozeduren ersetzt, nachdem der Computer den Join abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="b0857-147">The predefined password is only used to support the join operation and is replaced as part of normal computer account procedures after the computer completes the join.</span></span>

## <span data-ttu-id="b0857-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b0857-148">PARAMETERS</span></span>

### <span data-ttu-id="b0857-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b0857-149">-ComputerName</span></span>

<span data-ttu-id="b0857-150">Gibt die einer Domäne oder Arbeitsgruppe hinzuzufügenden Computer an.</span><span class="sxs-lookup"><span data-stu-id="b0857-150">Specifies the computers to add to a domain or workgroup.</span></span>
<span data-ttu-id="b0857-151">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="b0857-151">The default is the local computer.</span></span>

<span data-ttu-id="b0857-152">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den voll qualifizierten Domänen Namen der einzelnen Remote Computer ein.</span><span class="sxs-lookup"><span data-stu-id="b0857-152">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name of each of the remote computers.</span></span> <span data-ttu-id="b0857-153">Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt ( `.` ) oder "localhost" ein.</span><span class="sxs-lookup"><span data-stu-id="b0857-153">To specify the local computer, type the computer name, a dot (`.`), or "localhost".</span></span>

<span data-ttu-id="b0857-154">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="b0857-154">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="b0857-155">Sie können den **Computername** -Parameter `Add-Computer` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b0857-155">You can use the **ComputerName** parameter of `Add-Computer` even if your computer is not configured to run remote commands.</span></span>

<span data-ttu-id="b0857-156">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b0857-156">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="b0857-157">-Credential</span></span>

<span data-ttu-id="b0857-158">Gibt ein Benutzerkonto an, das über die Berechtigung zum Hinzufügen der Computer zu einer neuen Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-158">Specifies a user account that has permission to join the computers to a new domain.</span></span>
<span data-ttu-id="b0857-159">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b0857-159">The default is the current user.</span></span>

<span data-ttu-id="b0857-160">Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="b0857-160">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="b0857-161">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b0857-161">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="b0857-162">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Entfernen des Computers aus der aktuellen Domäne verfügt, mit dem **UnjoinDomainCredential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b0857-162">To specify a user account that has permission to remove the computer from its current domain, use the **UnjoinDomainCredential** parameter.</span></span> <span data-ttu-id="b0857-163">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit einem Remotecomputer verfügt, mit dem **LocalCredential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b0857-163">To specify a user account that has permission to connect to a remote computer, use the **LocalCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain, Workgroup
Aliases: DomainCredential

Required: True (Domain), False (Workgroup)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-164">-DomainName</span><span class="sxs-lookup"><span data-stu-id="b0857-164">-DomainName</span></span>

<span data-ttu-id="b0857-165">Gibt die Domäne an, der die Computer hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b0857-165">Specifies the domain to which the computers are added.</span></span> <span data-ttu-id="b0857-166">Dieser Parameter ist beim Hinzufügen der Computer zu einer Domäne erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b0857-166">This parameter is required when adding the computers to a domain.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DN, Domain

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-167">-Force</span><span class="sxs-lookup"><span data-stu-id="b0857-167">-Force</span></span>

<span data-ttu-id="b0857-168">Unterdrückt die Bestätigungsaufforderung.</span><span class="sxs-lookup"><span data-stu-id="b0857-168">Suppresses the user confirmation prompt.</span></span> <span data-ttu-id="b0857-169">Ohne diesen Parameter erfordert, dass `Add-Computer` Sie das Hinzufügen jedes Computers bestätigen.</span><span class="sxs-lookup"><span data-stu-id="b0857-169">Without this parameter, `Add-Computer` requires you to confirm the addition of each computer.</span></span>

<span data-ttu-id="b0857-170">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b0857-170">This parameter is introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b0857-171">-Localcredential</span><span class="sxs-lookup"><span data-stu-id="b0857-171">-LocalCredential</span></span>

<span data-ttu-id="b0857-172">Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit den durch den **ComputerName** -Parameter angegebenen Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-172">Specifies a user account that has permission to connect to the computers that are specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="b0857-173">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b0857-173">The default is the current user.</span></span>

<span data-ttu-id="b0857-174">Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="b0857-174">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="b0857-175">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b0857-175">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="b0857-176">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Hinzufügen der Computer zu einer neuen Domäne verfügt, mit dem **Credential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b0857-176">To specify a user account that has permission to add the computers to a new domain, use the **Credential** parameter.</span></span> <span data-ttu-id="b0857-177">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Entfernen der Computer aus der aktuellen Domäne verfügt, mit dem **UnjoinDomainCredential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b0857-177">To specify a user account that has permission to remove the computers from their current domain, use the **UnjoinDomainCredential** parameter.</span></span>

<span data-ttu-id="b0857-178">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b0857-178">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-179">-Newname</span><span class="sxs-lookup"><span data-stu-id="b0857-179">-NewName</span></span>

<span data-ttu-id="b0857-180">Gibt einen neuen Namen für den Computer in der neuen Domäne an.</span><span class="sxs-lookup"><span data-stu-id="b0857-180">Specifies a new name for the computer in the new domain.</span></span> <span data-ttu-id="b0857-181">Dieser Parameter ist nur gültig, wenn ein Computer hinzugefügt oder verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="b0857-181">This parameter is valid only when one computer is being added or moved.</span></span>

<span data-ttu-id="b0857-182">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b0857-182">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-183">-Optionen</span><span class="sxs-lookup"><span data-stu-id="b0857-183">-Options</span></span>

<span data-ttu-id="b0857-184">Gibt erweiterte Optionen für den **Add-Computer-** Joinvorgang an.</span><span class="sxs-lookup"><span data-stu-id="b0857-184">Specifies advanced options for the **Add-Computer** join operation.</span></span> <span data-ttu-id="b0857-185">Geben Sie Werte in einer durch Trennzeichen getrennten Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="b0857-185">Enter one or more values in a comma-separated string.</span></span>

<span data-ttu-id="b0857-186">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="b0857-186">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b0857-187">**Accountcreate** : erstellt ein Domänen Konto.</span><span class="sxs-lookup"><span data-stu-id="b0857-187">**AccountCreate** : Creates a domain account.</span></span> <span data-ttu-id="b0857-188">Das **Add-Computer-** Cmdlet erstellt beim Hinzufügen eines Computers zu einer Domäne automatisch ein Domänen Konto.</span><span class="sxs-lookup"><span data-stu-id="b0857-188">The **Add-Computer** cmdlet automatically creates a domain account when it adds a computer to a domain.</span></span> <span data-ttu-id="b0857-189">Diese Option ist aus Gründen der Vollständigkeit enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0857-189">This option is included for completeness.</span></span>

- <span data-ttu-id="b0857-190">**Win9XUpgrade** : gibt an, dass der Joinvorgang Teil eines Upgrades für das Windows-Betriebssystem ist.</span><span class="sxs-lookup"><span data-stu-id="b0857-190">**Win9XUpgrade** : Indicates that the join operation is part of a Windows operating system upgrade.</span></span>

- <span data-ttu-id="b0857-191">**Unsecuredjoin** : führt einen ungesicherten Join aus.</span><span class="sxs-lookup"><span data-stu-id="b0857-191">**UnsecuredJoin** : Performs an unsecured join.</span></span> <span data-ttu-id="b0857-192">Verwenden Sie zum Anfordern eines unsicheren Joins den *unsecure* -Parameter oder diese Option.</span><span class="sxs-lookup"><span data-stu-id="b0857-192">To request an unsecured join, use the *Unsecure* parameter or this option.</span></span> <span data-ttu-id="b0857-193">Wenn Sie ein Computer Kennwort übergeben möchten, müssen Sie diese Option in Kombination mit der `PasswordPass` Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0857-193">If you want to pass a machine password, then you must use this option in combination with `PasswordPass` option.</span></span>

- <span data-ttu-id="b0857-194">**Passwordpass** : legt das Computer Kennwort auf den Wert des *Credential* (domaincredential)-Parameters fest, nachdem ein unsicherer Join durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="b0857-194">**PasswordPass** : Sets the machine password to the value of the *Credential* (DomainCredential) parameter after performing an unsecured join.</span></span> <span data-ttu-id="b0857-195">Diese Option gibt darüber hinaus an, dass es sich beim Wert des *Credential* (DomainCredential)-Parameters um ein Computerkennwort und nicht um ein Benutzerkennwort handelt.</span><span class="sxs-lookup"><span data-stu-id="b0857-195">This option also indicates that the value of the *Credential* (DomainCredential) parameter is a machine password, not a user password.</span></span> <span data-ttu-id="b0857-196">Diese Option ist nur gültig, wenn die `UnsecuredJoin` Option angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="b0857-196">This option is valid only when the `UnsecuredJoin` option is specified.</span></span> <span data-ttu-id="b0857-197">Wenn diese Option verwendet wird, müssen die für den-Parameter bereitgestellten Anmelde Informationen `-Credential` über einen NULL- *must* Benutzernamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="b0857-197">When using this option, the credential provided to the `-Credential` parameter *must* have a null username.</span></span>

- <span data-ttu-id="b0857-198">**Joinwithnewname** : benennt den Computernamen in der neuen Domäne in den durch den *NewName* -Parameter angegebenen Namen um.</span><span class="sxs-lookup"><span data-stu-id="b0857-198">**JoinWithNewName** : Renames the computer name in the new domain to the name specified by the *NewName* parameter.</span></span> <span data-ttu-id="b0857-199">Bei Verwendung des *NewName* -Parameters wird diese Option automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b0857-199">When you use the *NewName* parameter, this option is set automatically.</span></span> <span data-ttu-id="b0857-200">Diese Option ist für die Verwendung mit dem Cmdlet "Rename-Computer" konzipiert.</span><span class="sxs-lookup"><span data-stu-id="b0857-200">This option is designed to be used with the Rename-Computer cmdlet.</span></span> <span data-ttu-id="b0857-201">Wenn Sie das Cmdlet **Rename-Computer** zum Umbenennen des Computers verwenden, den Computer jedoch nicht neu starten, damit die Änderung wirksam wird, können Sie diesen Parameter verwenden, um den Computer einer Domäne mit dem neuen Namen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b0857-201">If you use the **Rename-Computer** cmdlet to rename the computer, but do not restart the computer to make the change effective, you can use this parameter to join the computer to a domain with its new name.</span></span>

- <span data-ttu-id="b0857-202">**Joinschreib only** : verwendet ein vorhandenes Computer Konto, um den Computer einem schreibgeschützten Domänen Controller hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b0857-202">**JoinReadOnly** : Uses an existing machine account to join the computer to a read-only domain controller.</span></span> <span data-ttu-id="b0857-203">Das Computer Konto muss der Liste der zulässigen Kenn Wort Replikations Richtlinien hinzugefügt werden, und das Konto Kennwort muss vor dem Join-Vorgang auf den schreibgeschützten Domänen Controller repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="b0857-203">The machine account must be added to the allowed list for password replication policy and the account password must be replicated to the read-only domain controller prior to the join operation.</span></span>

- <span data-ttu-id="b0857-204">**Installrufe** : legt die Create (0x2)-und DELETE (0x4)-Flags des **FJoinOptions** -Parameters der **JoinDomainOrWorkgroup** -Methode fest.</span><span class="sxs-lookup"><span data-stu-id="b0857-204">**InstallInvoke** : Sets the create (0x2) and delete (0x4) flags of the **FJoinOptions** parameter of the **JoinDomainOrWorkgroup** method.</span></span> <span data-ttu-id="b0857-205">Weitere Informationen zur **JoinDomainOrWorkgroup** -Methode finden Sie unter [JoinDomainOrWorkgroup-Methode der Win32_ComputerSystem-Klasse](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).</span><span class="sxs-lookup"><span data-stu-id="b0857-205">For more information about the **JoinDomainOrWorkgroup** method, see [JoinDomainOrWorkgroup method of the Win32_ComputerSystem class](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).</span></span>
  <span data-ttu-id="b0857-206">Weitere Informationen zu diesen Optionen finden Sie unter " [NetJoinDomain](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain)"-Funktion.</span><span class="sxs-lookup"><span data-stu-id="b0857-206">For more information about these options, see [NetJoinDomain function](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain).</span></span>

<span data-ttu-id="b0857-207">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b0857-207">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.JoinOptions
Parameter Sets: Domain
Aliases:
Accepted values: AccountCreate, Win9XUpgrade, UnsecuredJoin, PasswordPass, DeferSPNSet, JoinWithNewName, JoinReadOnly, InstallInvoke

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-208">-Oupath</span><span class="sxs-lookup"><span data-stu-id="b0857-208">-OUPath</span></span>

<span data-ttu-id="b0857-209">Gibt eine Organisationseinheit für das Domänenkonto an.</span><span class="sxs-lookup"><span data-stu-id="b0857-209">Specifies an organizational unit (OU) for the domain account.</span></span> <span data-ttu-id="b0857-210">Geben Sie den vollständigen definierten Namen der Organisationseinheit in Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="b0857-210">Enter the full distinguished name of the OU in quotation marks.</span></span> <span data-ttu-id="b0857-211">Der Standardwert ist die Standardorganisationseinheit für Computerobjekte in der Domäne.</span><span class="sxs-lookup"><span data-stu-id="b0857-211">The default value is the default OU for machine objects in the domain.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: OU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-212">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b0857-212">-PassThru</span></span>

<span data-ttu-id="b0857-213">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b0857-213">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="b0857-214">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="b0857-214">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b0857-215">-Restart</span><span class="sxs-lookup"><span data-stu-id="b0857-215">-Restart</span></span>

<span data-ttu-id="b0857-216">Startet die Computer neu, die der Domäne oder Arbeitsgruppe hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0857-216">Restarts the computers that were added to the domain or workgroup.</span></span> <span data-ttu-id="b0857-217">Ein Neustart ist häufig erforderlich, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="b0857-217">A restart is often required to make the change effective.</span></span>

<span data-ttu-id="b0857-218">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b0857-218">This parameter is introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b0857-219">-Server</span><span class="sxs-lookup"><span data-stu-id="b0857-219">-Server</span></span>

<span data-ttu-id="b0857-220">Gibt den Namen eines Domänencontrollers an, der den Computer der Domäne hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-220">Specifies the name of a domain controller that adds the computer to the domain.</span></span> <span data-ttu-id="b0857-221">Geben Sie den Namen im Format %%amp;quot;Domänenname\Computername%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="b0857-221">Enter the name in DomainName\ComputerName format.</span></span> <span data-ttu-id="b0857-222">Standardmäßig ist kein Domänencontroller angegeben.</span><span class="sxs-lookup"><span data-stu-id="b0857-222">By default, no domain controller is specified.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-223">-Unjoindomaincredential</span><span class="sxs-lookup"><span data-stu-id="b0857-223">-UnjoinDomainCredential</span></span>

<span data-ttu-id="b0857-224">Gibt ein Benutzerkonto an, das über die Berechtigung zum Entfernen der Computer aus ihren aktuellen Domänen verfügt.</span><span class="sxs-lookup"><span data-stu-id="b0857-224">Specifies a user account that has permission to remove the computers from their current domains.</span></span> <span data-ttu-id="b0857-225">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b0857-225">The default is the current user.</span></span>

<span data-ttu-id="b0857-226">Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="b0857-226">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="b0857-227">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b0857-227">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="b0857-228">Verwenden Sie diesen Parameter, wenn Sie Computer in eine andere Domäne verschieben.</span><span class="sxs-lookup"><span data-stu-id="b0857-228">Use this parameter when you are moving computers to a different domain.</span></span> <span data-ttu-id="b0857-229">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Beitreten zur neuen Domäne verfügt, mit dem **Credential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b0857-229">To specify a user account that has permission to join the new domain, use the **Credential** parameter.</span></span> <span data-ttu-id="b0857-230">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit einem Remotecomputer verfügt, mit dem **LocalCredential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b0857-230">To specify a user account that has permission to connect to a remote computer, use the **LocalCredential** parameter.</span></span>

<span data-ttu-id="b0857-231">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b0857-231">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-232">-Unsicher</span><span class="sxs-lookup"><span data-stu-id="b0857-232">-Unsecure</span></span>

<span data-ttu-id="b0857-233">Führt einen unsicheren Beitritt zur angegebenen Domäne durch.</span><span class="sxs-lookup"><span data-stu-id="b0857-233">Performs an unsecure join to the specified domain.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-234">-Workgroupname</span><span class="sxs-lookup"><span data-stu-id="b0857-234">-WorkgroupName</span></span>

<span data-ttu-id="b0857-235">Gibt den Namen einer Arbeitsgruppe an, der der Computer hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b0857-235">Specifies the name of a workgroup to which the computers are added.</span></span> <span data-ttu-id="b0857-236">Der Standardwert ist %%amp;quot;WORKGROUP%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="b0857-236">The default value is "WORKGROUP".</span></span>

```yaml
Type: System.String
Parameter Sets: Workgroup
Aliases: WGN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0857-237">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b0857-237">-Confirm</span></span>

<span data-ttu-id="b0857-238">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b0857-238">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b0857-239">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b0857-239">-WhatIf</span></span>

<span data-ttu-id="b0857-240">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0857-240">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b0857-241">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b0857-241">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b0857-242">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b0857-242">CommonParameters</span></span>

<span data-ttu-id="b0857-243">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b0857-243">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b0857-244">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b0857-244">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b0857-245">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b0857-245">INPUTS</span></span>

### <span data-ttu-id="b0857-246">System.String</span><span class="sxs-lookup"><span data-stu-id="b0857-246">System.String</span></span>

<span data-ttu-id="b0857-247">Sie können Computernamen und neue Namen über die Pipeline an das `Add-Computer` Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="b0857-247">You can pipe computer names and new names to the `Add-Computer` Cmdlet.</span></span>

## <span data-ttu-id="b0857-248">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b0857-248">OUTPUTS</span></span>

### <span data-ttu-id="b0857-249">Microsoft. PowerShell. Commands. computerchangeingefo</span><span class="sxs-lookup"><span data-stu-id="b0857-249">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="b0857-250">Wenn Sie den **passthru** -Parameter verwenden, wird `Add-Computer` ein **computerchangeinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b0857-250">When you use the **PassThru** parameter, `Add-Computer` returns a **ComputerChangeInfo** object.</span></span>
<span data-ttu-id="b0857-251">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="b0857-251">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b0857-252">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b0857-252">NOTES</span></span>

- <span data-ttu-id="b0857-253">In Windows PowerShell 2,0 schlägt der **Server** Parameter von `Add-Computer` auch dann fehl, wenn der Server vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b0857-253">In Windows PowerShell 2.0, the **Server** parameter of `Add-Computer` fails even when the server is present.</span></span> <span data-ttu-id="b0857-254">In Windows PowerShell 3.0 wurde die Implementierung des **Server** -Parameters geändert, sodass er zuverlässig funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b0857-254">In Windows PowerShell 3.0, the implementation of the **Server** parameter is changed so that it works reliably.</span></span>

## <span data-ttu-id="b0857-255">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b0857-255">RELATED LINKS</span></span>

[<span data-ttu-id="b0857-256">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="b0857-256">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="b0857-257">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="b0857-257">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="b0857-258">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="b0857-258">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="b0857-259">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="b0857-259">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="b0857-260">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="b0857-260">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="b0857-261">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="b0857-261">Stop-Computer</span></span>](Stop-Computer.md)

[<span data-ttu-id="b0857-262">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="b0857-262">Test-Connection</span></span>](Test-Connection.md)
