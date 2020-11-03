---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8062210aa94cb46d5e5557ede1bac672cae39622
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218255"
---
# <span data-ttu-id="fd783-103">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="fd783-103">Stop-Computer</span></span>

## <span data-ttu-id="fd783-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fd783-104">SYNOPSIS</span></span>
<span data-ttu-id="fd783-105">Beendet den lokalen Computer und Remotecomputer (fährt sie herunter).</span><span class="sxs-lookup"><span data-stu-id="fd783-105">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="fd783-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd783-106">SYNTAX</span></span>

### <span data-ttu-id="fd783-107">Alle</span><span class="sxs-lookup"><span data-stu-id="fd783-107">All</span></span>

```
Stop-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="fd783-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd783-108">DESCRIPTION</span></span>

<span data-ttu-id="fd783-109">Mit dem `Stop-Computer` -Cmdlet werden der lokale Computer und Remote Computer heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="fd783-109">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="fd783-110">Mit den Parametern von können Sie `Stop-Computer` die Vorgänge zum Herunterfahren als Hintergrund Auftrag ausführen, die Authentifizierungs Ebenen und Alternative Anmelde Informationen angeben, die gleichzeitigen Verbindungen einschränken, die zum Ausführen des Befehls erstellt werden, und ein sofortiges Herunterfahren erzwingen.</span><span class="sxs-lookup"><span data-stu-id="fd783-110">You can use the parameters of `Stop-Computer` to run the shutdown operations as a background job, to specify the authentication levels and alternate credentials, to limit the concurrent connections that are created to run the command, and to force an immediate shut down.</span></span>

<span data-ttu-id="fd783-111">Für dieses Cmdlet ist PowerShell-Remoting nur erforderlich, wenn Sie den **AsJob** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd783-111">This cmdlet doesn't require PowerShell remoting unless you use the **AsJob** parameter.</span></span>

## <span data-ttu-id="fd783-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fd783-112">EXAMPLES</span></span>

### <span data-ttu-id="fd783-113">Beispiel 1: Herunterfahren des lokalen Computers</span><span class="sxs-lookup"><span data-stu-id="fd783-113">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="fd783-114">In diesem Beispiel wird der lokale Computer heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="fd783-114">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="fd783-115">Beispiel 2: Herunterfahren von zwei Remote Computern und dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="fd783-115">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="fd783-116">In diesem Beispiel werden zwei Remote Computer und der lokale Computer angehalten.</span><span class="sxs-lookup"><span data-stu-id="fd783-116">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="fd783-117">`Stop-Computer` verwendet den **Computername** -Parameter, um zwei Remote Computer und den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fd783-117">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="fd783-118">Jeder Computer wird heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="fd783-118">Each computer is shut down.</span></span>

### <span data-ttu-id="fd783-119">Beispiel 3: Herunterfahren von Remote Computern als Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="fd783-119">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="fd783-120">In diesem Beispiel wird `Stop-Computer` als Hintergrund Auftrag auf zwei Remote Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd783-120">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" -AsJob
$results = $j | Receive-Job
$results
```

<span data-ttu-id="fd783-121">`Stop-Computer` verwendet den **Computername** -Parameter, um zwei Remote Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fd783-121">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="fd783-122">Der **AsJob** -Parameter führt den Befehl als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="fd783-122">The **AsJob** parameter runs the command as a background job.</span></span> <span data-ttu-id="fd783-123">Die Auftrags Objekte werden in der `$j` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fd783-123">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="fd783-124">Die Auftrags Objekte in der `$j` Variablen werden an die Pipeline gesendet `Receive-Job` , die die Auftrags Ergebnisse abruft.</span><span class="sxs-lookup"><span data-stu-id="fd783-124">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="fd783-125">Die-Objekte werden in der- `$results` Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fd783-125">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="fd783-126">Die `$results` Variable zeigt die Auftrags Informationen in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="fd783-126">The `$results` variable displays the job information in the PowerShell console.</span></span>

<span data-ttu-id="fd783-127">Da **AsJob** den Auftrag auf dem lokalen Computer erstellt und die Ergebnisse automatisch an den lokalen Computer zurückgibt, können Sie ihn `Receive-Job` als lokalen Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="fd783-127">Because **AsJob** creates the job on the local computer and automatically returns the results to the local computer, you can run `Receive-Job` as a local command.</span></span>

### <span data-ttu-id="fd783-128">Beispiel 4: Herunterfahren eines Remote Computers</span><span class="sxs-lookup"><span data-stu-id="fd783-128">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="fd783-129">In diesem Beispiel wird ein Remote Computer mithilfe der angegebenen Authentifizierung heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="fd783-129">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

<span data-ttu-id="fd783-130">`Stop-Computer` verwendet den **Computername** -Parameter, um den Remote Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fd783-130">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="fd783-131">Der Identitätswechsel Parameter gibt einen angepassten Identitätswechsel an, und der **dcomauthentication** **-Parameter gibt** Einstellungen auf Authentifizierungs Ebene an.</span><span class="sxs-lookup"><span data-stu-id="fd783-131">The **Impersonation** parameter specifies a customized impersonation and the **DcomAuthentication** parameter specifies authentication-level settings.</span></span>

### <span data-ttu-id="fd783-132">Beispiel 5: Herunterfahren von Computern in einer Domäne</span><span class="sxs-lookup"><span data-stu-id="fd783-132">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="fd783-133">In diesem Beispiel erzwingen die Befehle ein sofortiges Herunterfahren aller Computer in einer angegebenen Domäne.</span><span class="sxs-lookup"><span data-stu-id="fd783-133">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -ThrottleLimit 10 -Credential $c
```

<span data-ttu-id="fd783-134">`Get-Content` verwendet den **path** -Parameter, um eine Datei im aktuellen Verzeichnis mit der Liste der Domänen Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fd783-134">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="fd783-135">Die-Objekte werden in der- `$s` Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fd783-135">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="fd783-136">`Get-Credential` verwendet den **Credential** -Parameter, um die Anmelde Informationen eines Domänen Administrators anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fd783-136">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="fd783-137">Die Anmelde Informationen werden in der `$c` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fd783-137">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="fd783-138">`Stop-Computer` fährt die Computer herunter, die mit der Liste der Computer des Computer **Name** -Parameters in der Variablen angegeben werden `$s` .</span><span class="sxs-lookup"><span data-stu-id="fd783-138">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="fd783-139">Der **Force** -Parameter erzwingt ein sofortiges Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="fd783-139">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="fd783-140">Der **throttlelimit** -Parameter schränkt den Befehl auf 10 gleichzeitige Verbindungen ein.</span><span class="sxs-lookup"><span data-stu-id="fd783-140">The **ThrottleLimit** parameter limits the command to 10 concurrent connections.</span></span> <span data-ttu-id="fd783-141">Mit dem **Credential** -Parameter werden die in der Variablen gespeicherten Anmelde Informationen übermittelt `$c` .</span><span class="sxs-lookup"><span data-stu-id="fd783-141">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="fd783-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd783-142">PARAMETERS</span></span>

### <span data-ttu-id="fd783-143">-AsJob</span><span class="sxs-lookup"><span data-stu-id="fd783-143">-AsJob</span></span>

<span data-ttu-id="fd783-144">Gibt an, dass dieses Cmdlet als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fd783-144">Indicates that this cmdlet runs as a background job.</span></span>

<span data-ttu-id="fd783-145">Um diesen Parameter verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein. unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option **als Administrator ausführen** öffnen.</span><span class="sxs-lookup"><span data-stu-id="fd783-145">To use this parameter, the local and remote computers must be configured for remoting and, on Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="fd783-146">Weitere Informationen finden Sie unter [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd783-146">For more information, see [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).</span></span>

<span data-ttu-id="fd783-147">Wenn Sie den **AsJob** -Parameter angeben, gibt der Befehl sofort ein Objekt zurück, das den Hintergrund Auftrag darstellt.</span><span class="sxs-lookup"><span data-stu-id="fd783-147">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="fd783-148">Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="fd783-148">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="fd783-149">Der Auftrag wird auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fd783-149">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="fd783-150">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="fd783-150">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="fd783-151">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) und [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).</span><span class="sxs-lookup"><span data-stu-id="fd783-151">For more information about PowerShell background jobs, see [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) and [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).</span></span>

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

### <span data-ttu-id="fd783-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="fd783-152">-ComputerName</span></span>

<span data-ttu-id="fd783-153">Gibt die zu stoppenden Computer an.</span><span class="sxs-lookup"><span data-stu-id="fd783-153">Specifies the computers to stop.</span></span> <span data-ttu-id="fd783-154">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="fd783-154">The default is the local computer.</span></span>

<span data-ttu-id="fd783-155">Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer in einer durch Trennzeichen getrennten Liste ein.</span><span class="sxs-lookup"><span data-stu-id="fd783-155">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="fd783-156">Geben Sie den Computernamen oder localhost ein, um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fd783-156">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="fd783-157">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="fd783-157">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="fd783-158">Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="fd783-158">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd783-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fd783-159">-Confirm</span></span>

<span data-ttu-id="fd783-160">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="fd783-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fd783-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="fd783-161">-Credential</span></span>

<span data-ttu-id="fd783-162">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="fd783-162">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="fd783-163">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="fd783-163">The default is the current user.</span></span>

<span data-ttu-id="fd783-164">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fd783-164">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="fd783-165">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="fd783-165">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="fd783-166">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fd783-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="fd783-167">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="fd783-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd783-168">-Dcomauthentication</span><span class="sxs-lookup"><span data-stu-id="fd783-168">-DcomAuthentication</span></span>

<span data-ttu-id="fd783-169">Gibt die Authentifizierungs Ebene an, die dieses Cmdlet mit WMI verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd783-169">Specifies the authentication level that this cmdlet uses with WMI.</span></span> <span data-ttu-id="fd783-170">`Stop-Computer` verwendet WMI.</span><span class="sxs-lookup"><span data-stu-id="fd783-170">`Stop-Computer` uses WMI.</span></span> <span data-ttu-id="fd783-171">Der Standardwert ist " **Paket** ".</span><span class="sxs-lookup"><span data-stu-id="fd783-171">The default value is **Packet**.</span></span>

<span data-ttu-id="fd783-172">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="fd783-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fd783-173">**Standard** : Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fd783-173">**Default** : Windows Authentication.</span></span>
- <span data-ttu-id="fd783-174">**None** : keine com-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fd783-174">**None** : No COM authentication.</span></span>
- <span data-ttu-id="fd783-175">**Connect** : com-Authentifizierung auf Verbindungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="fd783-175">**Connect** : Connect-level COM authentication.</span></span>
- <span data-ttu-id="fd783-176">**Aufzurufen** : com-Authentifizierung auf Aufrufebene.</span><span class="sxs-lookup"><span data-stu-id="fd783-176">**Call** : Call-level COM authentication.</span></span>
- <span data-ttu-id="fd783-177">**Paket** : com-Authentifizierung auf Paketebene.</span><span class="sxs-lookup"><span data-stu-id="fd783-177">**Packet** : Packet-level COM authentication.</span></span>
- <span data-ttu-id="fd783-178">**Packetintegrity** : com-Authentifizierung auf Paket Integritäts Ebene.</span><span class="sxs-lookup"><span data-stu-id="fd783-178">**PacketIntegrity** : Packet Integrity-level COM authentication.</span></span>
- <span data-ttu-id="fd783-179">**PacketPrivacy** : com-Authentifizierung auf Paketdaten Schutz Ebene.</span><span class="sxs-lookup"><span data-stu-id="fd783-179">**PacketPrivacy** : Packet Privacy-level COM authentication.</span></span>
- <span data-ttu-id="fd783-180">**Unverändert** : identisch mit dem vorherigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="fd783-180">**Unchanged** : Same as the previous command.</span></span>

<span data-ttu-id="fd783-181">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).</span><span class="sxs-lookup"><span data-stu-id="fd783-181">For more information about the values of this parameter, see [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd783-182">-Force</span><span class="sxs-lookup"><span data-stu-id="fd783-182">-Force</span></span>

<span data-ttu-id="fd783-183">Erzwingt ein sofortiges Herunterfahren des Computers.</span><span class="sxs-lookup"><span data-stu-id="fd783-183">Forces an immediate shut down of the computer.</span></span>

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

### <span data-ttu-id="fd783-184">-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="fd783-184">-Impersonation</span></span>

<span data-ttu-id="fd783-185">Gibt die Identitätswechsel Ebene an, die verwendet werden soll, wenn dieses Cmdlet WMI aufruft.</span><span class="sxs-lookup"><span data-stu-id="fd783-185">Specifies the impersonation level to use when this cmdlet calls WMI.</span></span> <span data-ttu-id="fd783-186">Der Standard **Wert ist "** Identitätswechsel".</span><span class="sxs-lookup"><span data-stu-id="fd783-186">The default value is **Impersonate**.</span></span>

<span data-ttu-id="fd783-187">`Stop-Computer` verwendet WMI.</span><span class="sxs-lookup"><span data-stu-id="fd783-187">`Stop-Computer` uses WMI.</span></span> <span data-ttu-id="fd783-188">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="fd783-188">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fd783-189">**Standard** : Standard Identitätswechsel.</span><span class="sxs-lookup"><span data-stu-id="fd783-189">**Default** : Default impersonation.</span></span>
- <span data-ttu-id="fd783-190">**Anonymous** : Blendet die Identität des Aufrufers aus.</span><span class="sxs-lookup"><span data-stu-id="fd783-190">**Anonymous** : Hides the identity of the caller.</span></span>
- <span data-ttu-id="fd783-191">**Identifizieren** : ermöglicht es Objekten, die Anmelde Informationen des Aufrufers abzufragen.</span><span class="sxs-lookup"><span data-stu-id="fd783-191">**Identify** : Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="fd783-192">Identität **annehmen: ermöglicht** es Objekten, die Anmelde Informationen des Aufrufers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd783-192">**Impersonate** : Allows objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd783-193">-Protocol</span><span class="sxs-lookup"><span data-stu-id="fd783-193">-Protocol</span></span>

<span data-ttu-id="fd783-194">Gibt an, welches Protokoll zum Neustarten der Computer verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd783-194">Specifies which protocol to use to restart the computers.</span></span> <span data-ttu-id="fd783-195">Die zulässigen Werte für diesen Parameter sind: **WSMAN** und **DCOM**.</span><span class="sxs-lookup"><span data-stu-id="fd783-195">The acceptable values for this parameter are: **WSMan** and **DCOM**.</span></span> <span data-ttu-id="fd783-196">Der Standardwert ist **DCOM**.</span><span class="sxs-lookup"><span data-stu-id="fd783-196">The default value is **DCOM**.</span></span>

<span data-ttu-id="fd783-197">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fd783-197">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: DCOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd783-198">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="fd783-198">-ThrottleLimit</span></span>

<span data-ttu-id="fd783-199">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="fd783-199">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="fd783-200">Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd783-200">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="fd783-201">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="fd783-201">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="fd783-202">-Wsmanauthentication</span><span class="sxs-lookup"><span data-stu-id="fd783-202">-WsmanAuthentication</span></span>

<span data-ttu-id="fd783-203">Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren, wenn dieses Cmdlet das WSMAN-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd783-203">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="fd783-204">Der Standardwert lautet **Default**.</span><span class="sxs-lookup"><span data-stu-id="fd783-204">The default value is **Default**.</span></span>

<span data-ttu-id="fd783-205">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="fd783-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fd783-206">Basic</span><span class="sxs-lookup"><span data-stu-id="fd783-206">Basic</span></span>
- <span data-ttu-id="fd783-207">CredSSP</span><span class="sxs-lookup"><span data-stu-id="fd783-207">CredSSP</span></span>
- <span data-ttu-id="fd783-208">Standard</span><span class="sxs-lookup"><span data-stu-id="fd783-208">Default</span></span>
- <span data-ttu-id="fd783-209">Digest</span><span class="sxs-lookup"><span data-stu-id="fd783-209">Digest</span></span>
- <span data-ttu-id="fd783-210">Kerberos</span><span class="sxs-lookup"><span data-stu-id="fd783-210">Kerberos</span></span>
- <span data-ttu-id="fd783-211">Negotiate</span><span class="sxs-lookup"><span data-stu-id="fd783-211">Negotiate.</span></span>

<span data-ttu-id="fd783-212">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="fd783-212">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="fd783-213">Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern</span><span class="sxs-lookup"><span data-stu-id="fd783-213">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="fd783-214">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="fd783-214">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="fd783-215">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd783-215">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="fd783-216">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fd783-216">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd783-217">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fd783-217">-WhatIf</span></span>

<span data-ttu-id="fd783-218">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fd783-218">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fd783-219">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd783-219">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="fd783-220">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fd783-220">CommonParameters</span></span>

<span data-ttu-id="fd783-221">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fd783-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd783-222">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fd783-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd783-223">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fd783-223">INPUTS</span></span>

### <span data-ttu-id="fd783-224">Keine</span><span class="sxs-lookup"><span data-stu-id="fd783-224">None</span></span>

<span data-ttu-id="fd783-225">Eingaben können nicht an dieses Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="fd783-225">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="fd783-226">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fd783-226">OUTPUTS</span></span>

### <span data-ttu-id="fd783-227">None oder System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="fd783-227">None or System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="fd783-228">Das-Cmdlet gibt ein **System. Management. Automation. remotingjob** -Objekt zurück, wenn Sie den **AsJob** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="fd783-228">The cmdlet returns a **System.Management.Automation.RemotingJob** object, if you specify the **AsJob** parameter.</span></span> <span data-ttu-id="fd783-229">Andernfalls wird keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="fd783-229">Otherwise, it doesn't generate any output.</span></span>

## <span data-ttu-id="fd783-230">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fd783-230">NOTES</span></span>

<span data-ttu-id="fd783-231">Dieses Cmdlet verwendet die **Win32Shutdown** -Methode der WMI-Klasse **Win32_OperatingSystem** .</span><span class="sxs-lookup"><span data-stu-id="fd783-231">This cmdlet uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="fd783-232">Diese Methode erfordert, dass die **SeShutdownPrivilege** -Berechtigung für das Benutzerkonto aktiviert ist, mit dem der Computer neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="fd783-232">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

## <span data-ttu-id="fd783-233">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fd783-233">RELATED LINKS</span></span>

[<span data-ttu-id="fd783-234">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="fd783-234">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="fd783-235">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="fd783-235">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="fd783-236">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="fd783-236">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="fd783-237">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="fd783-237">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="fd783-238">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="fd783-238">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="fd783-239">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="fd783-239">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="fd783-240">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="fd783-240">Test-Connection</span></span>](Test-Connection.md)
