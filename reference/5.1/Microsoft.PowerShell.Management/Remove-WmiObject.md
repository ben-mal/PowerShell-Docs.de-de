---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmiObject
ms.openlocfilehash: 287eb02e7de2f4182e0ecfd7f6b6a7cafb66969e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214543"
---
# <span data-ttu-id="69889-103">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="69889-103">Remove-WmiObject</span></span>

## <span data-ttu-id="69889-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="69889-104">SYNOPSIS</span></span>
<span data-ttu-id="69889-105">Löscht eine Instanz einer vorhandenen Klasse der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI).</span><span class="sxs-lookup"><span data-stu-id="69889-105">Deletes an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>

## <span data-ttu-id="69889-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="69889-106">SYNTAX</span></span>

### <span data-ttu-id="69889-107">Class (Standard)</span><span class="sxs-lookup"><span data-stu-id="69889-107">class (Default)</span></span>

```
Remove-WmiObject [-Class] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="69889-108">Objekt</span><span class="sxs-lookup"><span data-stu-id="69889-108">object</span></span>

```
Remove-WmiObject -InputObject <ManagementObject> [-AsJob] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="69889-109">path</span><span class="sxs-lookup"><span data-stu-id="69889-109">path</span></span>

```
Remove-WmiObject -Path <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="69889-110">Wqlquery</span><span class="sxs-lookup"><span data-stu-id="69889-110">WQLQuery</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="69889-111">Abfrage</span><span class="sxs-lookup"><span data-stu-id="69889-111">query</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="69889-112">list</span><span class="sxs-lookup"><span data-stu-id="69889-112">list</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="69889-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="69889-113">DESCRIPTION</span></span>
<span data-ttu-id="69889-114">Das **Remove-WMIObject-** Cmdlet löscht eine Instanz einer vorhandenen WMI-Klasse (Windows-Verwaltungsinstrumentation).</span><span class="sxs-lookup"><span data-stu-id="69889-114">The **Remove-WmiObject** cmdlet deletes an instance of an existing Windows Management Instrumentation (WMI)class.</span></span>

## <span data-ttu-id="69889-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="69889-115">EXAMPLES</span></span>

### <span data-ttu-id="69889-116">Beispiel 1: Schließen aller Instanzen eines Win32-Prozesses</span><span class="sxs-lookup"><span data-stu-id="69889-116">Example 1: Close all instances of a Win32 process</span></span>

```
PS C:\> notepad
PS C:\> $np = Get-WmiObject -Query "select * from win32_process where name='notepad.exe'"
PS C:\> $np | Remove-WmiObject
```

<span data-ttu-id="69889-117">In diesem Beispiel werden alle Instanzen von Notepad.exe geschlossen.</span><span class="sxs-lookup"><span data-stu-id="69889-117">This example closes all the instances of Notepad.exe.</span></span>

<span data-ttu-id="69889-118">Der erste Befehl startet eine Instanz von Editor.</span><span class="sxs-lookup"><span data-stu-id="69889-118">The first command starts an instance of Notepad.</span></span>

<span data-ttu-id="69889-119">Der zweite Befehl verwendet das Cmdlet "Get-WmiObject", um die Instanzen der Win32_Process abzurufen, die Notepad.exe entsprechen, und speichert Sie dann in der $NP Variable.</span><span class="sxs-lookup"><span data-stu-id="69889-119">The second command uses the Get-WmiObject cmdlet to retrieve the instances of the Win32_Process that correspond to Notepad.exe, and then stores them in the $np variable.</span></span>

<span data-ttu-id="69889-120">Der dritte Befehl übergibt das Objekt in der $NP-Variablen an **Remove-WMIObject** , das alle Instanzen von Notepad.exe löscht.</span><span class="sxs-lookup"><span data-stu-id="69889-120">The third command passes the object in the $np variable to **Remove-WmiObject** , which deletes all the instances of Notepad.exe.</span></span>

### <span data-ttu-id="69889-121">Beispiel 2: Löschen eines Ordners</span><span class="sxs-lookup"><span data-stu-id="69889-121">Example 2: Delete a folder</span></span>

```
PS C:\> $a = Get-WMIObject -Query "Select * From Win32_Directory Where Name ='C:\\Test'"
PS C:\> $a | Remove-WMIObject
```

<span data-ttu-id="69889-122">Mit diesem Befehl wird der Ordner "c:\Test" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="69889-122">This command deletes the C:\Test folder.</span></span>

<span data-ttu-id="69889-123">Der erste Befehl verwendet **Get-WMIObject** , um den Ordner "c:\Test" abzufragen, und speichert dann das Objekt in der $a Variable.</span><span class="sxs-lookup"><span data-stu-id="69889-123">The first command uses **Get-WMIObject** to query for the C:\Test folder, and then stores the object in the $a variable.</span></span>

<span data-ttu-id="69889-124">Mit dem zweiten Befehl wird die $a Variable an **Remove-WMIObject** übergeben, wodurch der Ordner gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="69889-124">The second command pipes the $a variable to **Remove-WMIObject** , which deletes the folder.</span></span>

## <span data-ttu-id="69889-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="69889-125">PARAMETERS</span></span>

### <span data-ttu-id="69889-126">-AsJob</span><span class="sxs-lookup"><span data-stu-id="69889-126">-AsJob</span></span>
<span data-ttu-id="69889-127">Gibt an, dass dieses Cmdlet als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="69889-127">Indicates that this cmdlet run as a background job.</span></span>
<span data-ttu-id="69889-128">Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="69889-128">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="69889-129">Mit den neuen in Windows PowerShell 3.0 eingeführten CIM-Cmdlets werden die gleichen Aufgaben wie mit WMI-Cmdlets ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="69889-129">New CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span>
<span data-ttu-id="69889-130">Die CIM-Cmdlets entsprechen den WS-Management (WSMAN)-Standards und dem CIM-Standard (Common Information Model), mit dem die Cmdlets dieselben Verfahren zum Verwalten von Computern verwenden können, auf denen das Windows-Betriebssystem ausgeführt wird, und auf denen andere Betriebssysteme ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="69889-130">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, which enables the cmdlets to use the same techniques to manage computers that run the Windows operating system and those running other operating systems.</span></span>
<span data-ttu-id="69889-131">Anstelle von **Remove-WmiObject** können Sie das Cmdlet Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 verwenden.</span><span class="sxs-lookup"><span data-stu-id="69889-131">Instead of using **Remove-WmiObject** , consider using the Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 cmdlet.</span></span>

<span data-ttu-id="69889-132">Wenn Sie den *AsJob* -Parameter verwenden, gibt der Befehl ein Objekt zurück, das den Hintergrundauftrag darstellt, und zeigt dann die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="69889-132">When you use the *AsJob* parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span>
<span data-ttu-id="69889-133">Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="69889-133">You can continue to work in the session while the job finishes.</span></span>
<span data-ttu-id="69889-134">Wenn **Remove-WmiObject** für einen Remotecomputer verwendet wird, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="69889-134">If **Remove-WmiObject** is used against a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="69889-135">Verwenden Sie zum Verwalten des Auftrags die Cmdlets, die das **Auftrags** Substantiv (die **Job** -Cmdlets) enthalten.</span><span class="sxs-lookup"><span data-stu-id="69889-135">To manage the job, use the cmdlets that contain the **Job** noun (the **Job** cmdlets).</span></span>
<span data-ttu-id="69889-136">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="69889-136">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="69889-137">Um diesen Parameter für Remote Computer zu verwenden, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="69889-137">To use this parameter for remote computers, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="69889-138">Starten Sie Windows PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="69889-138">Start Windows PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="69889-139">Weitere Informationen finden Sie unter %%amp;quot;about_Remote_Requirements%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="69889-139">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="69889-140">Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter about_Jobs und about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="69889-140">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="69889-141">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="69889-141">-Authentication</span></span>
<span data-ttu-id="69889-142">Gibt die für die WMI-Verbindung zu verwendende Authentifizierungsebene an.</span><span class="sxs-lookup"><span data-stu-id="69889-142">Specifies the authentication level to use for the WMI connection.</span></span>
<span data-ttu-id="69889-143">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="69889-143">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="69889-144">-1: unverändert.</span><span class="sxs-lookup"><span data-stu-id="69889-144">-1: Unchanged.</span></span>
- <span data-ttu-id="69889-145">0: Default.</span><span class="sxs-lookup"><span data-stu-id="69889-145">0: Default.</span></span>
- <span data-ttu-id="69889-146">1: keine.</span><span class="sxs-lookup"><span data-stu-id="69889-146">1: None.</span></span>
<span data-ttu-id="69889-147">Es wird keine Authentifizierung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="69889-147">No authentication in performed.</span></span>
- <span data-ttu-id="69889-148">2: verbinden.</span><span class="sxs-lookup"><span data-stu-id="69889-148">2: Connect.</span></span>
<span data-ttu-id="69889-149">Die Authentifizierung wird nur ausgeführt, wenn der Client eine Beziehung mit der Anwendung herstellt.</span><span class="sxs-lookup"><span data-stu-id="69889-149">Authentication is performed only when the client establishes a relationship with the application.</span></span>
- <span data-ttu-id="69889-150">3: wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="69889-150">3: Call.</span></span>
<span data-ttu-id="69889-151">Die Authentifizierung wird nur zu Beginn jedes Aufrufes ausgeführt, wenn die Anwendung die Anforderung empfängt.</span><span class="sxs-lookup"><span data-stu-id="69889-151">Authentication is performed only at the start of each call when the application receives the request.</span></span>
- <span data-ttu-id="69889-152">4: Paket.</span><span class="sxs-lookup"><span data-stu-id="69889-152">4: Packet.</span></span>
<span data-ttu-id="69889-153">Die Authentifizierung wird für alle Daten ausgeführt, die vom Client empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="69889-153">Authentication is performed on all the data that is received from the client.</span></span>
- <span data-ttu-id="69889-154">5: packetintegrity.</span><span class="sxs-lookup"><span data-stu-id="69889-154">5: PacketIntegrity.</span></span>
<span data-ttu-id="69889-155">Alle Daten, die zwischen dem Client und der Anwendung übertragen werden, werden authentifiziert und überprüft.</span><span class="sxs-lookup"><span data-stu-id="69889-155">All the data that is transferred between the client and the application is authenticated and verified.</span></span>
- <span data-ttu-id="69889-156">6: PacketPrivacy.</span><span class="sxs-lookup"><span data-stu-id="69889-156">6: PacketPrivacy.</span></span>
<span data-ttu-id="69889-157">Die Eigenschaften der anderen Authentifizierungs Ebenen werden verwendet, und alle Daten werden verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="69889-157">The properties of the other authentication levels are used, and all the data is encrypted.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-158">-Autorität</span><span class="sxs-lookup"><span data-stu-id="69889-158">-Authority</span></span>
<span data-ttu-id="69889-159">Gibt die Autorität an, die zum Authentifizieren der WMI-Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="69889-159">Specifies the authority to use to authenticate the WMI connection.</span></span>
<span data-ttu-id="69889-160">Sie können die Standard-NTLM- oder Kerberos-Authentifizierung angeben.</span><span class="sxs-lookup"><span data-stu-id="69889-160">You can specify standard NTLM or Kerberos authentication.</span></span>
<span data-ttu-id="69889-161">Legen Sie für die Verwendung von NTLM die Authority-Einstellung auf %%amp;quot;ntlmdomain:\<DomainName\>%%amp;quot; fest, wobei \<DomainName\> einen gültigen NTLM-Domänennamen darstellt.</span><span class="sxs-lookup"><span data-stu-id="69889-161">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span>
<span data-ttu-id="69889-162">Wenn Sie Kerberos verwenden möchten, geben Sie Kerberos: an \<DomainName\> \\ \<ServerName\> .</span><span class="sxs-lookup"><span data-stu-id="69889-162">To use Kerberos, specify kerberos:\<DomainName\>\\\<ServerName\>.</span></span>
<span data-ttu-id="69889-163">Sie können die Authority-Einstellung nicht einschließen, wenn Sie eine Verbindung mit dem lokalen Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="69889-163">You cannot include the authority setting when you connect to the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-164">-Klasse</span><span class="sxs-lookup"><span data-stu-id="69889-164">-Class</span></span>
<span data-ttu-id="69889-165">Gibt den Namen einer WMI-Klasse an, die von diesem Cmdlet gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="69889-165">Specifies the name of a WMI class that this cmdlet deletes.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-166">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="69889-166">-ComputerName</span></span>
<span data-ttu-id="69889-167">Gibt den Namen des Computers an, auf dem dieses Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="69889-167">Specifies the name of the computer on which this cmdlet runs.</span></span>
<span data-ttu-id="69889-168">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="69889-168">The default is the local computer.</span></span>

<span data-ttu-id="69889-169">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer ein.</span><span class="sxs-lookup"><span data-stu-id="69889-169">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span>
<span data-ttu-id="69889-170">Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="69889-170">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="69889-171">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="69889-171">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="69889-172">Sie können den *ComputerName* -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="69889-172">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="69889-173">-Credential</span></span>
<span data-ttu-id="69889-174">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="69889-174">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="69889-175">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="69889-175">The default is the current user.</span></span>

<span data-ttu-id="69889-176">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. das vom Cmdlet Get-Credential generierte.</span><span class="sxs-lookup"><span data-stu-id="69889-176">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="69889-177">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="69889-177">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-178">-Enableallprivileges</span><span class="sxs-lookup"><span data-stu-id="69889-178">-EnableAllPrivileges</span></span>
<span data-ttu-id="69889-179">Gibt an, dass dieses Cmdlet alle Berechtigungen des aktuellen Benutzers vor dem Befehl aktiviert, den der WMI aufruft.</span><span class="sxs-lookup"><span data-stu-id="69889-179">Indicates that this cmdlet enables all the permissions of the current user before the command it makes the WMI call.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-180">-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="69889-180">-Impersonation</span></span>
<span data-ttu-id="69889-181">Gibt die zu verwendende Identitätswechselebene an.</span><span class="sxs-lookup"><span data-stu-id="69889-181">Specifies the impersonation level to use.</span></span>
<span data-ttu-id="69889-182">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="69889-182">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="69889-183">0: Default.</span><span class="sxs-lookup"><span data-stu-id="69889-183">0: Default.</span></span>
<span data-ttu-id="69889-184">Liest die lokale Registrierung für die standardmäßige Identitätswechsel Ebene, die normalerweise auf 3 festgelegt ist: Identität annehmen.</span><span class="sxs-lookup"><span data-stu-id="69889-184">Reads the local registry for the default impersonation level, which is usually set to 3: Impersonate.</span></span>
- <span data-ttu-id="69889-185">1: Anonymous.</span><span class="sxs-lookup"><span data-stu-id="69889-185">1: Anonymous.</span></span>
<span data-ttu-id="69889-186">Verbirgt die Anmeldeinformationen des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="69889-186">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="69889-187">2: Identify.</span><span class="sxs-lookup"><span data-stu-id="69889-187">2: Identify.</span></span>
<span data-ttu-id="69889-188">Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers abzufragen.</span><span class="sxs-lookup"><span data-stu-id="69889-188">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="69889-189">3: Impersonate.</span><span class="sxs-lookup"><span data-stu-id="69889-189">3: Impersonate.</span></span>
<span data-ttu-id="69889-190">Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="69889-190">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="69889-191">4: Delegate.</span><span class="sxs-lookup"><span data-stu-id="69889-191">4: Delegate.</span></span>
<span data-ttu-id="69889-192">Ermöglicht es Objekten, anderen Objekten die Verwendung der Anmeldeinformationen des Aufrufers zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="69889-192">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-193">-InputObject</span><span class="sxs-lookup"><span data-stu-id="69889-193">-InputObject</span></span>
<span data-ttu-id="69889-194">Gibt ein **ManagementObject** -Objekt an, das als Eingabe verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="69889-194">Specifies a **ManagementObject** object to use as input.</span></span>
<span data-ttu-id="69889-195">Wenn dieser Parameter verwendet wird, werden alle anderen Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="69889-195">When this parameter is used, all other parameters are ignored.</span></span>

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="69889-196">-Gebiets Schema</span><span class="sxs-lookup"><span data-stu-id="69889-196">-Locale</span></span>
<span data-ttu-id="69889-197">Gibt das bevorzugte Gebietsschema für WMI-Objekte an.</span><span class="sxs-lookup"><span data-stu-id="69889-197">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="69889-198">Der *locale* -Parameter wird als Array im MS_ \<LCID\> Format in der bevorzugten Reihenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="69889-198">The *Locale* parameter is specified as an array in the MS_\<LCID\> format in the preferred order.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-199">-Namespace</span><span class="sxs-lookup"><span data-stu-id="69889-199">-Namespace</span></span>
<span data-ttu-id="69889-200">Gibt den WMI-Repository-Namespace an, in dem sich die referenzierte WMI-Klasse befindet, wenn Sie mit dem *Class* -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="69889-200">Specifies the WMI repository namespace where the referenced WMI class is located when it is used with the *Class* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-201">-Path</span><span class="sxs-lookup"><span data-stu-id="69889-201">-Path</span></span>
<span data-ttu-id="69889-202">Gibt den WMI-Objektpfad einer WMI-Klasse oder den WMI-Objektpfad einer Instanz einer zu löschenden WMI-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="69889-202">Specifies the WMI object path of a WMI class, or specifies the WMI object path of an instance of a WMI class to delete.</span></span>

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-203">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="69889-203">-ThrottleLimit</span></span>
<span data-ttu-id="69889-204">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="69889-204">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="69889-205">Dieser Parameter wird in Verbindung mit dem *AsJob* -Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="69889-205">This parameter is used together with the *AsJob* parameter.</span></span>
<span data-ttu-id="69889-206">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="69889-206">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69889-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="69889-207">-Confirm</span></span>
<span data-ttu-id="69889-208">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="69889-208">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="69889-209">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="69889-209">-WhatIf</span></span>
<span data-ttu-id="69889-210">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="69889-210">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="69889-211">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="69889-211">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="69889-212">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="69889-212">CommonParameters</span></span>
<span data-ttu-id="69889-213">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="69889-213">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="69889-214">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="69889-214">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="69889-215">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="69889-215">INPUTS</span></span>

### <span data-ttu-id="69889-216">System. Management. ManagementObject</span><span class="sxs-lookup"><span data-stu-id="69889-216">System.Management.ManagementObject</span></span>
<span data-ttu-id="69889-217">Sie können ein Verwaltungs Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="69889-217">You can pipe a management object to this cmdlet.</span></span>

## <span data-ttu-id="69889-218">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="69889-218">OUTPUTS</span></span>

### <span data-ttu-id="69889-219">Keine, System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="69889-219">None, System.Management.Automation.RemotingJob</span></span>
<span data-ttu-id="69889-220">Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den *AsJob* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="69889-220">This cmdlet returns a job object, if you specify the *AsJob* parameter.</span></span>
<span data-ttu-id="69889-221">Andernfalls wird keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="69889-221">Otherwise, it does not generate any output.</span></span>

## <span data-ttu-id="69889-222">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="69889-222">NOTES</span></span>

## <span data-ttu-id="69889-223">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="69889-223">RELATED LINKS</span></span>

[<span data-ttu-id="69889-224">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="69889-224">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="69889-225">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="69889-225">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="69889-226">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="69889-226">Set-WmiInstance</span></span>](Set-WmiInstance.md)
