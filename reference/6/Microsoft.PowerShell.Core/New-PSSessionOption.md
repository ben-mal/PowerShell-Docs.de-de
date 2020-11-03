---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionOption
ms.openlocfilehash: 10f086c3fc2090681f669d481eb880d81ea9d245
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216407"
---
# <span data-ttu-id="10432-103">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="10432-103">New-PSSessionOption</span></span>

## <span data-ttu-id="10432-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="10432-104">SYNOPSIS</span></span>
<span data-ttu-id="10432-105">Erstellt ein Objekt, das erweiterte Optionen für eine PSSession enthält.</span><span class="sxs-lookup"><span data-stu-id="10432-105">Creates an object that contains advanced options for a PSSession.</span></span>

## <span data-ttu-id="10432-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="10432-106">SYNTAX</span></span>

```
New-PSSessionOption [-MaximumRedirection <Int32>] [-NoCompression] [-NoMachineProfile] [-Culture <CultureInfo>]
 [-UICulture <CultureInfo>] [-MaximumReceivedDataSizePerCommand <Int32>] [-MaximumReceivedObjectSize <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-MaxConnectionRetryCount <Int32>]
 [-ApplicationArguments <PSPrimitiveDictionary>] [-OpenTimeout <Int32>] [-CancelTimeout <Int32>]
 [-IdleTimeout <Int32>] [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <AuthenticationMechanism>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [-IncludePortInSPN] [<CommonParameters>]
```

## <span data-ttu-id="10432-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10432-107">DESCRIPTION</span></span>

<span data-ttu-id="10432-108">Das- `New-PSSessionOption` Cmdlet erstellt ein Objekt, das erweiterte Optionen für eine vom Benutzer verwaltete Sitzung ( **PSSession** ) enthält.</span><span class="sxs-lookup"><span data-stu-id="10432-108">The `New-PSSessionOption` cmdlet creates an object that contains advanced options for a user-managed session ( **PSSession** ).</span></span> <span data-ttu-id="10432-109">Sie können das-Objekt als Wert des **sessionoption** -Parameters von Cmdlets verwenden, die eine **PSSession** erstellen, `New-PSSession` z `Enter-PSSession` . b `Invoke-Command` ., und.</span><span class="sxs-lookup"><span data-stu-id="10432-109">You can use the object as the value of the **SessionOption** parameter of cmdlets that create a **PSSession** , such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

<span data-ttu-id="10432-110">Ohne Parameter `New-PSSessionOption` generiert ein Objekt, das die Standardwerte für alle Optionen enthält.</span><span class="sxs-lookup"><span data-stu-id="10432-110">Without parameters, `New-PSSessionOption` generates an object that contains the default values for all of the options.</span></span> <span data-ttu-id="10432-111">Da alle Eigenschaften bearbeitet werden können, können Sie das resultierende Objekt als Vorlage verwenden und Standardoptionsobjekte für Ihr Unternehmen erstellen.</span><span class="sxs-lookup"><span data-stu-id="10432-111">Because all of the properties can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="10432-112">Sie können ein Sitzungs Options Objekt auch in der `$PSSessionOption` Preference-Variablen speichern.</span><span class="sxs-lookup"><span data-stu-id="10432-112">You can also save a session option object in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="10432-113">Die Werte dieser Variablen richten neue Standardwerte für die Sitzungsoptionen ein.</span><span class="sxs-lookup"><span data-stu-id="10432-113">The values of this variable establish new default values for the session options.</span></span> <span data-ttu-id="10432-114">Sie sind gültig, wenn keine Sitzungsoptionen für die Sitzung festgelegt sind, und haben Vorrang vor Optionen, die in der Sitzungskonfiguration festgelegt sind. Durch Angabe von Sitzungsoptionen oder einem Sitzungsoptionsobjekt in einem Cmdlet, das eine Sitzung erstellt, können Sie sie jedoch überschreiben.</span><span class="sxs-lookup"><span data-stu-id="10432-114">They effective when no session options are set for the session and they take precedence over options set in the session configuration, but you can override them by specifying session options or a session option object in a cmdlet that creates a session.</span></span> <span data-ttu-id="10432-115">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="10432-115">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="10432-116">Wenn Sie ein Sitzungsoptionsobjekt in einem Cmdlet verwenden, das eine Sitzung erstellt, haben die Sitzungsoptionswerte Vorrang vor Standardwerten für Sitzungen, die in der $PSSessionOption-Einstellungsvariablen und der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="10432-116">When you use a session option object in a cmdlet that creates a session, the session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="10432-117">Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="10432-117">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="10432-118">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="10432-118">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="10432-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="10432-119">EXAMPLES</span></span>

### <span data-ttu-id="10432-120">Beispiel 1: Erstellen einer Standard Sitzungs Option</span><span class="sxs-lookup"><span data-stu-id="10432-120">Example 1: Create a default session option</span></span>

<span data-ttu-id="10432-121">Mit diesem Befehl wird ein Sitzungs Options Objekt erstellt, das alle Standardwerte aufweist.</span><span class="sxs-lookup"><span data-stu-id="10432-121">This command creates a session option object that has all of the default values.</span></span>

```powershell
New-PSSessionOption
```

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

### <span data-ttu-id="10432-122">Beispiel 2: Konfigurieren einer Sitzung mithilfe eines Sitzungs Options Objekts</span><span class="sxs-lookup"><span data-stu-id="10432-122">Example 2: Configure a session by using a session option object</span></span>

<span data-ttu-id="10432-123">In diesem Beispiel wird gezeigt, wie Sie eine Sitzung mit einem Sitzungsoptionsobjekt konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="10432-123">This example shows how to use a session option object to configure a session.</span></span>

```powershell
$pso = New-PSSessionOption -Culture "fr-fr" -MaximumReceivedObjectSize 10MB
New-PSSession -ComputerName Server01 -SessionOption $pso
```

<span data-ttu-id="10432-124">Mit dem ersten Befehl wird ein neues Sitzungs Options Objekt erstellt und im Wert der Variablen gespeichert `$pso` .</span><span class="sxs-lookup"><span data-stu-id="10432-124">The first command creates a new session option object and saves it in the value of the `$pso` variable.</span></span> <span data-ttu-id="10432-125">Der zweite Befehl verwendet das `New-PSSession` Cmdlet, um eine Sitzung auf dem Remote Computer Server01 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10432-125">The second command uses the `New-PSSession` cmdlet to create a session on the Server01 remote computer.</span></span> <span data-ttu-id="10432-126">Der Befehl verwendet das Sitzungs Options Objekt im Wert der `$pso` Variablen als Wert des **sessionoption** -Parameters des-Befehls.</span><span class="sxs-lookup"><span data-stu-id="10432-126">The command uses the session option object in the value of the `$pso` variable as the value of the **SessionOption** parameter of the command.</span></span>

### <span data-ttu-id="10432-127">Beispiel 3: Starten einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="10432-127">Example 3: Start an interactive session</span></span>

<span data-ttu-id="10432-128">Dieser Befehl verwendet das `Enter-PSSession` Cmdlet, um eine interaktive Sitzung mit dem Server01-Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="10432-128">This command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

```powershell
Enter-PSSession -ComputerName Server01 -SessionOption (New-PSSessionOption -NoEncryption -NoCompression)
```

<span data-ttu-id="10432-129">Der Wert des **sessionoption** -Parameters ist ein `New-PSSessionOption` Befehl, der über die Parameter **NoEncryption** und **NoCompression** verfügt.</span><span class="sxs-lookup"><span data-stu-id="10432-129">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that has the **NoEncryption** and **NoCompression** parameters.</span></span>

<span data-ttu-id="10432-130">Der `New-PSSessionOption` Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er vor dem Befehl ausgeführt wird `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="10432-130">The `New-PSSessionOption` command is enclosed in parentheses to make sure that it runs before the `Enter-PSSession` command.</span></span>

### <span data-ttu-id="10432-131">Beispiel 4: Ändern eines Sitzungs Options Objekts</span><span class="sxs-lookup"><span data-stu-id="10432-131">Example 4: Modify a session option object</span></span>

<span data-ttu-id="10432-132">In diesem Beispiel wird veranschaulicht, dass Sie das Sitzungs Options Objekt ändern können.</span><span class="sxs-lookup"><span data-stu-id="10432-132">This example demonstrates that you can modify the session option object.</span></span> <span data-ttu-id="10432-133">Alle Eigenschaften verfügen über Lese-/Schreibwerte.</span><span class="sxs-lookup"><span data-stu-id="10432-133">All properties have read/write values.</span></span>

```powershell
$a = New-PSSessionOption
$a.OpenTimeout
```

```Output
Days              : 0
Hours             : 0
Minutes           : 3
Seconds           : 0
Milliseconds      : 0
Ticks             : 1800000000
TotalDays         : 0.00208333333333333
TotalHours        : 0.05
TotalMinutes      : 3
TotalSeconds      : 180
TotalMilliseconds : 180000
```

```powershell
$a.UICulture = (Get-UICulture)
$a.OpenTimeout = (New-Timespan -Minutes 4)
$a.MaximumConnectionRedirectionCount = 1
$a
```

```Output
MaximumConnectionRedirectionCount : 1
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         : en-US
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:04:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

<span data-ttu-id="10432-134">Verwenden Sie diese Methode, um ein Standardsitzungsobjekt für Ihr Unternehmen zu erstellen, und dann angepasste Versionen für bestimmte Verwendungszwecke anzulegen.</span><span class="sxs-lookup"><span data-stu-id="10432-134">Use this method to create a standard session object for your enterprise, and then create customized versions of it for particular uses.</span></span>

### <span data-ttu-id="10432-135">Beispiel 5: Erstellen einer Einstellungs Variablen</span><span class="sxs-lookup"><span data-stu-id="10432-135">Example 5: Create a preference variable</span></span>

<span data-ttu-id="10432-136">Dieser Befehl erstellt eine Einstellungs `$PSSessionOption` Variable.</span><span class="sxs-lookup"><span data-stu-id="10432-136">This command creates a `$PSSessionOption` preference variable.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -OpenTimeOut 120000
```

<span data-ttu-id="10432-137">Wenn die Einstellungs `$PSSessionOption` Variable in der Sitzung auftritt, werden Standardwerte für Optionen in den Sitzungen festgelegt, die mit den `New-PSSession` `Enter-PSSession` Cmdlets, und erstellt werden `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="10432-137">When the `$PSSessionOption` preference variable occurs in the session, it establishes default values for options in the sessions that are created by using the `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="10432-138">Um die `$PSSessionOption` Variable in allen Sitzungen verfügbar zu machen, fügen Sie Sie der PowerShell-Sitzung und Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="10432-138">To make the `$PSSessionOption` variable available in all sessions, add it to your PowerShell session and to your PowerShell profile.</span></span>

<span data-ttu-id="10432-139">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="10432-139">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="10432-140">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="10432-140">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

### <span data-ttu-id="10432-141">Beispiel 6: erfüllen der Anforderungen an eine Remote Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="10432-141">Example 6: Fulfill the requirements for a remote session configuration</span></span>

<span data-ttu-id="10432-142">In diesem Beispiel wird gezeigt, wie ein **SessionOption** -Objekt verwendet wird, um die Anforderungen für eine Remotesitzungskonfiguration zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="10432-142">This example shows how to use a **SessionOption** object to fulfill the requirements for a remote session configuration.</span></span>

```powershell
$skipCN = New-PSSessionOption -SkipCNCheck
New-PSSession -ComputerName 171.09.21.207 -UseSSL -Credential Domain01\User01 -SessionOption $SkipCN
```

<span data-ttu-id="10432-143">Der erste Befehl verwendet das `New-PSSessionOption` Cmdlet, um ein Sitzungs Options Objekt zu erstellen, das über die **skipcncheck** -Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="10432-143">The first command uses the `New-PSSessionOption` cmdlet to create a session option object that has the **SkipCNCheck** property.</span></span> <span data-ttu-id="10432-144">Der Befehl speichert das resultierende Sitzungs Objekt in der `$skipCN` Variablen.</span><span class="sxs-lookup"><span data-stu-id="10432-144">The command saves the resulting session object in the `$skipCN` variable.</span></span>

<span data-ttu-id="10432-145">Der zweite Befehl verwendet das `New-PSSession` Cmdlet, um eine neue Sitzung auf einem Remote Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10432-145">The second command uses the `New-PSSession` cmdlet to create a new session on a remote computer.</span></span> <span data-ttu-id="10432-146">Die `$skipCN` Check-Variable wird im Wert des **sessionoption** -Parameters verwendet.</span><span class="sxs-lookup"><span data-stu-id="10432-146">The `$skipCN` check variable is used in the value of the **SessionOption** parameter.</span></span>

<span data-ttu-id="10432-147">Da der Computer anhand seiner IP-Adresse identifiziert wird, entspricht der Wert des Computer **Name** -Parameters keinem der allgemeinen Namen im Zertifikat, das für Secure Sockets Layer (SSL) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="10432-147">Because the computer is identified by its IP address, the value of the **ComputerName** parameter does not match any of the common names in the certificate that is used for Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="10432-148">Demzufolge ist die **SkipCNCheck** -Option erforderlich.</span><span class="sxs-lookup"><span data-stu-id="10432-148">As a result, the **SkipCNCheck** option is required.</span></span>

### <span data-ttu-id="10432-149">Beispiel 7: Bereitstellen von Argumenten für eine Remote Sitzung</span><span class="sxs-lookup"><span data-stu-id="10432-149">Example 7: Make arguments available to a remote session</span></span>

<span data-ttu-id="10432-150">In diesem Beispiel wird gezeigt, wie der **applicationarguments** -Parameter des `New-PSSessionOption` Cmdlets verwendet wird, um zusätzliche Daten für die Remote Sitzung verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="10432-150">This example shows how to use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet to make additional data available to the remote session.</span></span>

```powershell
$team = @{Team="IT"; Use="Testing"}
$TeamOption = New-PSSessionOption -ApplicationArguments $team
$s = New-PSSession -ComputerName Server01 -SessionOption $TeamOption
Invoke-Command -Session $s {$PSSenderInfo.ApplicationArguments}
```

```Output
Name                 Value
----                 -----
Team                 IT
Use                  Testing
PSVersionTable       {CLRVersion, BuildVersion, PSVersion, WSManStackVersion...}
```

```powershell
Invoke-Command -Session $s {
  if ($PSSenderInfo.ApplicationArguments.Use -ne "Testing") {
    .\logFiles.ps1
  }
  else {
    "Just testing."
  }
}
```

```Output
Just testing.
```

<span data-ttu-id="10432-151">Der erste Befehl erstellt eine Hash Tabelle mit zwei Schlüsseln: " **Team** " und " **use** ".</span><span class="sxs-lookup"><span data-stu-id="10432-151">The first command creates a hash table with two keys, **Team** and **Use** .</span></span> <span data-ttu-id="10432-152">Der Befehl speichert die Hash Tabelle in der `$team` Variablen.</span><span class="sxs-lookup"><span data-stu-id="10432-152">The command saves the hash table in the `$team` variable.</span></span> <span data-ttu-id="10432-153">Weitere Informationen zu Hashtabellen finden Sie unter [about_Hash_Tables](about/about_Hash_Tables.md) (Informationen zu Hashtabellen).</span><span class="sxs-lookup"><span data-stu-id="10432-153">For more information about hash tables, see [about_Hash_Tables](about/about_Hash_Tables.md).</span></span>

<span data-ttu-id="10432-154">Im nächsten Schritt `New-PSSessionOption` erstellt das Cmdlet mit dem **applicationarguments** -Parameter ein Sitzungs Options Objekt, das in der Variablen gespeichert ist `$team` .</span><span class="sxs-lookup"><span data-stu-id="10432-154">Next, the `New-PSSessionOption` cmdlet, using the **ApplicationArguments** parameter, creates a session option object saved in the `$team` variable.</span></span> <span data-ttu-id="10432-155">Wenn `New-PSSessionOption` das Sitzungs Options Objekt erstellt, wird die Hash Tabelle im Wert des **applicationarguments** -Parameters automatisch in ein Primitives Wörterbuch konvertiert, damit die Daten zuverlässig an die Remote Sitzung übermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="10432-155">When `New-PSSessionOption` creates the session option object, it automatically converts the hash table in the value of the **ApplicationArguments** parameter to a primitive dictionary so the data can be reliably transmitted to the remote session.</span></span>

<span data-ttu-id="10432-156">Mit dem- `New-PSSession` Cmdlet wird eine Sitzung auf dem Server01-Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="10432-156">The `New-PSSession` cmdlet starts a session on the Server01 computer.</span></span> <span data-ttu-id="10432-157">Er verwendet den **sessionoption** -Parameter, um die Optionen in der `$teamOption` Variablen einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="10432-157">It uses the **SessionOption** parameter to include the options in the `$teamOption` variable.</span></span>

<span data-ttu-id="10432-158">Das `Invoke-Command` Cmdlet zeigt, dass die Daten in der `$team` Variablen für Befehle in der Remote Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="10432-158">The `Invoke-Command` cmdlet demonstrates that the data in the `$team` variable is available to commands in the remote session.</span></span> <span data-ttu-id="10432-159">Die Daten werden in der **applicationarguments** -Eigenschaft der `$PSSenderInfo` automatischen Variable angezeigt.</span><span class="sxs-lookup"><span data-stu-id="10432-159">The data appears in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span>

<span data-ttu-id="10432-160">Die letzte `Invoke-Command` zeigt, wie die Daten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="10432-160">The final `Invoke-Command` shows how the data might be used.</span></span>

## <span data-ttu-id="10432-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="10432-161">PARAMETERS</span></span>

### <span data-ttu-id="10432-162">-Applicationarguments</span><span class="sxs-lookup"><span data-stu-id="10432-162">-ApplicationArguments</span></span>

<span data-ttu-id="10432-163">Gibt ein primitives Wörterbuch an, das an die Remotesitzung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="10432-163">Specifies a primitive dictionary that is sent to the remote session.</span></span> <span data-ttu-id="10432-164">Durch Befehle und Skripts in der Remote Sitzung, einschließlich Start Skripts in der Sitzungs Konfiguration, kann dieses Wörterbuch in der **applicationarguments** -Eigenschaft der `$PSSenderInfo` automatischen Variablen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="10432-164">Commands and scripts in the remote session, including startup scripts in the session configuration, can find this dictionary in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span> <span data-ttu-id="10432-165">Sie können diesen Parameter verwenden, um Daten an die Remotesitzung zu senden.</span><span class="sxs-lookup"><span data-stu-id="10432-165">You can use this parameter to send data to the remote session.</span></span>

<span data-ttu-id="10432-166">Weitere Informationen finden Sie unter [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md)und [about_Automatic_Variables](about/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="10432-166">For more information, see [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md), and [about_Automatic_Variables](about/about_Automatic_Variables.md).</span></span>

```yaml
Type: System.Management.Automation.PSPrimitiveDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-167">-Canceltimeout</span><span class="sxs-lookup"><span data-stu-id="10432-167">-CancelTimeout</span></span>

<span data-ttu-id="10432-168">Bestimmt, wie lange PowerShell darauf wartet, dass ein Abbruch Vorgang (STRG + C) beendet wird, bevor Sie beendet wird.</span><span class="sxs-lookup"><span data-stu-id="10432-168">Determines how long PowerShell waits for a cancel operation (CTRL+C) to finish before ending it.</span></span>
<span data-ttu-id="10432-169">Geben Sie einen Wert in Millisekunden ein.</span><span class="sxs-lookup"><span data-stu-id="10432-169">Enter a value in milliseconds.</span></span>

<span data-ttu-id="10432-170">Der Standardwert ist 60000 (eine Minute).</span><span class="sxs-lookup"><span data-stu-id="10432-170">The default value is 60000 (one minute).</span></span> <span data-ttu-id="10432-171">Der Wert 0 (null) bedeutet, dass kein Timeout besteht; der Befehl wird auf unbestimmte Zeit fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="10432-171">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: CancelTimeoutMSec

Required: False
Position: Named
Default value: 60000
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-172">-Kultur</span><span class="sxs-lookup"><span data-stu-id="10432-172">-Culture</span></span>

<span data-ttu-id="10432-173">Gibt die Kultur an, die für die Sitzung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10432-173">Specifies the culture to use for the session.</span></span> <span data-ttu-id="10432-174">Geben Sie einen Kultur Namen im Format (z. b `<languagecode2>-<country/regioncode2>` `ja-JP` .), eine Variable mit einem **CultureInfo** -Objekt oder einen Befehl ein, der ein **CultureInfo** -Objekt abruft.</span><span class="sxs-lookup"><span data-stu-id="10432-174">Enter a culture name in `<languagecode2>-<country/regioncode2>` format (like `ja-JP`), a variable that contains a **CultureInfo** object, or a command that gets a **CultureInfo** object.</span></span>

<span data-ttu-id="10432-175">Der Standardwert ist `$Null` , und die im Betriebssystem festgelegte Kultur wird in der Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="10432-175">The default value is `$Null`, and the culture that is set in the operating system is used in the session.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-176">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="10432-176">-IdleTimeout</span></span>

<span data-ttu-id="10432-177">Bestimmt, wie lange die Sitzung geöffnet bleibt, wenn der Remote Computer keine Kommunikation vom lokalen Computer empfängt.</span><span class="sxs-lookup"><span data-stu-id="10432-177">Determines how long the session stays open if the remote computer does not receive any communication from the local computer.</span></span> <span data-ttu-id="10432-178">Dies schließt das Taktsignal ein.</span><span class="sxs-lookup"><span data-stu-id="10432-178">This includes the heartbeat signal.</span></span> <span data-ttu-id="10432-179">Wenn das Intervall abläuft, wird die Sitzung geschlossen.</span><span class="sxs-lookup"><span data-stu-id="10432-179">When the interval expires, the session closes.</span></span>

<span data-ttu-id="10432-180">Der Wert für das Leerlauf Timeout ist von großer Wichtigkeit, wenn Sie die Verbindung mit einer Sitzung trennen und wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="10432-180">The idle time-out value is of significant importance if you intend to disconnect and reconnect to a session.</span></span> <span data-ttu-id="10432-181">Sie können die Sitzung nur dann wiederherstellen, wenn kein Timeout aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="10432-181">You can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="10432-182">Geben Sie einen Wert in Millisekunden ein.</span><span class="sxs-lookup"><span data-stu-id="10432-182">Enter a value in milliseconds.</span></span> <span data-ttu-id="10432-183">Der Mindestwert ist 60000 (1 Minute).</span><span class="sxs-lookup"><span data-stu-id="10432-183">The minimum value is 60000 (1 minute).</span></span> <span data-ttu-id="10432-184">Der Höchstwert ist der Wert der **MaxIdleTimeoutms** -Eigenschaft der Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="10432-184">The maximum is the value of the **MaxIdleTimeoutms** property of the session configuration.</span></span> <span data-ttu-id="10432-185">Der Standardwert-1 legt kein Leerlauf Timeout fest.</span><span class="sxs-lookup"><span data-stu-id="10432-185">The default value, -1, does not set an idle time-out.</span></span>

<span data-ttu-id="10432-186">Die Sitzung verwendet das Leerlauf Timeout, das in den Sitzungs Optionen festgelegt wird (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="10432-186">The session uses the idle time-out that is set in the session options, if any.</span></span> <span data-ttu-id="10432-187">Wenn keine festgelegt ist (-1), verwendet die Sitzung den Wert der **idletimeoutms** -Eigenschaft der Sitzungs Konfiguration oder den Timeout Wert der WSMAN-Shell ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ), je nachdem, welcher Wert am kürzesten ist.</span><span class="sxs-lookup"><span data-stu-id="10432-187">If none is set (-1), the session uses the value of the **IdleTimeoutMs** property of the session configuration or the WSMan shell time-out value (`WSMan:\<ComputerName>\Shell\IdleTimeout`), whichever is shortest.</span></span>

<span data-ttu-id="10432-188">Überschreitet das Leerlaufzeitlimit in den Sitzungsoptionen den Wert der **MaxIdleTimeoutMs** -Eigenschaft der Sitzungskonfiguration, tritt bei dem Befehl zum Erstellen der Sitzung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="10432-188">If the idle timeout set in the session options exceeds the value of the **MaxIdleTimeoutMs** property of the session configuration, the command to create a session fails.</span></span>

<span data-ttu-id="10432-189">Der **idletimeoutms** -Wert der standardmäßigen **Microsoft. PowerShell** -Sitzungs Konfiguration beträgt 7,2 Millionen Millisekunden (2 Stunden).</span><span class="sxs-lookup"><span data-stu-id="10432-189">The **IdleTimeoutMs** value of the default **Microsoft.PowerShell** session configuration is 7200000 milliseconds (2 hours).</span></span> <span data-ttu-id="10432-190">Der **maxidletimeoutms** -Wert beträgt 2147483647 Millisekunden ( \> 24 Tage).</span><span class="sxs-lookup"><span data-stu-id="10432-190">Its **MaxIdleTimeoutMs** value is 2147483647 milliseconds (\>24 days).</span></span> <span data-ttu-id="10432-191">Der Standardwert des Leerlauf Timeouts () für WSMAN-Shell `WSMan:\<ComputerName>\Shell\IdleTimeout` beträgt 7,2 Millionen Millisekunden (2 Stunden).</span><span class="sxs-lookup"><span data-stu-id="10432-191">The default value of the WSMan shell idle time-out (`WSMan:\<ComputerName>\Shell\IdleTimeout`) is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="10432-192">Der Leerlauf Timeout Wert einer Sitzung kann auch geändert werden, wenn die Verbindung mit einer Sitzung getrennt oder eine Verbindung mit einer Sitzung wieder hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="10432-192">The idle time-out value of a session can also be changed when disconnecting from a session or reconnecting to a session.</span></span> <span data-ttu-id="10432-193">Weitere Informationen finden Sie unter `Disconnect-PSSession` und `Connect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="10432-193">For more information, see `Disconnect-PSSession` and `Connect-PSSession`.</span></span>

<span data-ttu-id="10432-194">In Windows PowerShell 2.0 beträgt der Standardwert des **IdleTimeout** -Parameters 240000 (4 Minuten).</span><span class="sxs-lookup"><span data-stu-id="10432-194">In Windows PowerShell 2.0, the default value of the **IdleTimeout** parameter is 240000 (4 minutes).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: IdleTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-195">-Includeportinspn</span><span class="sxs-lookup"><span data-stu-id="10432-195">-IncludePortInSPN</span></span>

<span data-ttu-id="10432-196">Schließt die Portnummer in den Dienst Prinzipal Namen (SPN) ein, die für die Kerberos-Authentifizierung verwendet wird, z `HTTP://<ComputerName>:5985` . b..</span><span class="sxs-lookup"><span data-stu-id="10432-196">Includes the port number in the Service Principal Name (SPN) used for Kerberos authentication, for example, `HTTP://<ComputerName>:5985`.</span></span> <span data-ttu-id="10432-197">Mit dieser Option kann ein Client, der einen nicht standardmäßigen SPN verwendet, von einem Remotecomputer authentifiziert werden, der die Kerberos-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="10432-197">This option allows a client that uses a non-default SPN to authenticate against a remote computer that uses Kerberos authentication.</span></span>

<span data-ttu-id="10432-198">Diese Option wurde für Organisationen entwickelt, in denen mehrere Dienste, die die Kerberos-Authentifizierung unterstützen, unter verschiedenen Benutzerkonten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="10432-198">The option is designed for enterprises where multiple services that support Kerberos authentication are running under different user accounts.</span></span> <span data-ttu-id="10432-199">Beispielsweise kann eine IIS-Anwendung, die die Kerberos-Authentifizierung zulässt, erfordern, dass der Standard-SPN für ein Benutzerkonto registriert ist, das sich von dem Computer Konto unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="10432-199">For example, an IIS application that allows for Kerberos authentication can require the default SPN to be registered to a user account that differs from the computer account.</span></span> <span data-ttu-id="10432-200">In solchen Fällen kann das PowerShell-Remoting Kerberos nicht für die Authentifizierung verwenden, da es einen SPN erfordert, der für das Computer Konto registriert ist.</span><span class="sxs-lookup"><span data-stu-id="10432-200">In such cases, PowerShell remoting cannot use Kerberos to authenticate because it requires an SPN that is registered to the computer account.</span></span> <span data-ttu-id="10432-201">Um dieses Problem zu beheben, können Administratoren unterschiedliche SPNs erstellen, z. b. mit **Setspn.exe** , die für unterschiedliche Benutzerkonten registriert sind, und Sie können unterscheiden, indem Sie die Portnummer in den SPN einschließen.</span><span class="sxs-lookup"><span data-stu-id="10432-201">To resolve this problem, administrators can create different SPNs, such as by using **Setspn.exe** , that are registered to different user accounts and can distinguish between them by including the port number in the SPN.</span></span>

<span data-ttu-id="10432-202">Weitere Informationen finden Sie unter [Übersicht über Setspn](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="10432-202">For more information, see [Setspn Overview](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).</span></span>

<span data-ttu-id="10432-203">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="10432-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="10432-204">-Maxconnectionretrycount</span><span class="sxs-lookup"><span data-stu-id="10432-204">-MaxConnectionRetryCount</span></span>

<span data-ttu-id="10432-205">Gibt an, wie oft von PowerShell versucht wird, eine Verbindung mit einem Zielcomputer herzustellen, wenn der aktuelle Versuch aufgrund von Netzwerkproblemen fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="10432-205">Specifies the number of times that PowerShell attempts to make a connection to a target machine if the current attempt fails due to network issues.</span></span> <span data-ttu-id="10432-206">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="10432-206">The default value is 5.</span></span>

<span data-ttu-id="10432-207">Dieser Parameter wurde für PowerShell-Version 5,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="10432-207">This parameter was added for PowerShell version 5.0.</span></span>

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

### <span data-ttu-id="10432-208">-Maximumreceiveddatasizepercommand</span><span class="sxs-lookup"><span data-stu-id="10432-208">-MaximumReceivedDataSizePerCommand</span></span>

<span data-ttu-id="10432-209">Gibt die maximale Anzahl von Bytes an, die der lokale Computer von dem Remotecomputer in einem einzigen Befehl empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="10432-209">Specifies the maximum number of bytes that the local computer can receive from the remote computer in a single command.</span></span> <span data-ttu-id="10432-210">Geben Sie einen Wert in Bytes ein.</span><span class="sxs-lookup"><span data-stu-id="10432-210">Enter a value in bytes.</span></span> <span data-ttu-id="10432-211">Standardmäßig besteht keine Größenbeschränkung für Daten.</span><span class="sxs-lookup"><span data-stu-id="10432-211">By default, there is no data size limit.</span></span>

<span data-ttu-id="10432-212">Diese Option dient zum Schutz der Ressourcen auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="10432-212">This option is designed to protect the resources on the client computer.</span></span>

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

### <span data-ttu-id="10432-213">-Maximumreceivedobjectsize</span><span class="sxs-lookup"><span data-stu-id="10432-213">-MaximumReceivedObjectSize</span></span>

<span data-ttu-id="10432-214">Gibt die maximale Größe eines Objekts an, das der lokale Computer vom Remotecomputer empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="10432-214">Specifies the maximum size of an object that the local computer can receive from the remote computer.</span></span> <span data-ttu-id="10432-215">Diese Option dient zum Schutz der Ressourcen auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="10432-215">This option is designed to protect the resources on the client computer.</span></span> <span data-ttu-id="10432-216">Geben Sie einen Wert in Bytes ein.</span><span class="sxs-lookup"><span data-stu-id="10432-216">Enter a value in bytes.</span></span>

<span data-ttu-id="10432-217">In Windows PowerShell 2.0 besteht, wenn Sie diesen Parameter weglassen, keine Größenbeschränkung für Objekte.</span><span class="sxs-lookup"><span data-stu-id="10432-217">In Windows PowerShell 2.0, if you omit this parameter, there is no object size limit.</span></span> <span data-ttu-id="10432-218">Ab Windows PowerShell 3.0 beträgt, wenn Sie diesen Parameter weglassen, der Standardwert 200 MB.</span><span class="sxs-lookup"><span data-stu-id="10432-218">Beginning in Windows PowerShell 3.0, if you omit this parameter, the default value is 200 MB.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 200 MB
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-219">-Maximumredirect</span><span class="sxs-lookup"><span data-stu-id="10432-219">-MaximumRedirection</span></span>

<span data-ttu-id="10432-220">Bestimmt, wie oft PowerShell eine Verbindung an eine Alternative Uniform Resource Identifier (URI) umleitet, bevor die Verbindung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="10432-220">Determines how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="10432-221">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="10432-221">The default value is 5.</span></span> <span data-ttu-id="10432-222">Der Wert 0 (null) unterbindet sämtliche Umleitungen.</span><span class="sxs-lookup"><span data-stu-id="10432-222">A value of 0 (zero) prevents all redirection.</span></span>

<span data-ttu-id="10432-223">Diese Option wird in der Sitzung nur verwendet, wenn der Parameter " **Zuweisung** " in dem Befehl verwendet wird, der die Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="10432-223">This option is used in the session only when the **AllowRedirection** parameter is used in the command that creates the session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-224">-NoCompression</span><span class="sxs-lookup"><span data-stu-id="10432-224">-NoCompression</span></span>

<span data-ttu-id="10432-225">Deaktiviert die Paketkomprimierung in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="10432-225">Turns off packet compression in the session.</span></span> <span data-ttu-id="10432-226">Die Komprimierung verwendet mehr Prozessorzyklen, beschleunigt aber die Übertragung.</span><span class="sxs-lookup"><span data-stu-id="10432-226">Compression uses more processor cycles, but it makes transmission faster.</span></span>

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

### <span data-ttu-id="10432-227">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="10432-227">-NoEncryption</span></span>

<span data-ttu-id="10432-228">Deaktiviert die Datenverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="10432-228">Turns off data encryption.</span></span>

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

### <span data-ttu-id="10432-229">-Nomachineprofile</span><span class="sxs-lookup"><span data-stu-id="10432-229">-NoMachineProfile</span></span>

<span data-ttu-id="10432-230">Verhindert das Laden des Windows-Benutzerprofils.</span><span class="sxs-lookup"><span data-stu-id="10432-230">Prevents loading the user's Windows user profile.</span></span> <span data-ttu-id="10432-231">Daraufhin wird die Sitzung möglicherweise schneller erstellt, aber benutzerspezifische Registrierungseinstellungen wie Umgebungsvariablen und Zertifikate sind in der Sitzung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10432-231">As a result, the session might be created faster, but user-specific registry settings, items such as environment variables, and certificates are not available in the session.</span></span>

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

### <span data-ttu-id="10432-232">-OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="10432-232">-OpenTimeout</span></span>

<span data-ttu-id="10432-233">Bestimmt, wie lange der Clientcomputer auf das Einrichten der Sitzungsverbindung wartet.</span><span class="sxs-lookup"><span data-stu-id="10432-233">Determines how long the client computer waits for the session connection to be established.</span></span> <span data-ttu-id="10432-234">Wenn das Intervall abläuft, tritt bei dem Befehl zum Herstellen der Verbindung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="10432-234">When the interval expires, the command to establish the connection fails.</span></span> <span data-ttu-id="10432-235">Geben Sie einen Wert in Millisekunden ein.</span><span class="sxs-lookup"><span data-stu-id="10432-235">Enter a value in milliseconds.</span></span>

<span data-ttu-id="10432-236">Der Standardwert ist 180000 (3 Minuten).</span><span class="sxs-lookup"><span data-stu-id="10432-236">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="10432-237">Der Wert 0 (null) bedeutet, dass kein Timeout besteht; der Befehl wird auf unbestimmte Zeit fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="10432-237">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OpenTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-238">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="10432-238">-OperationTimeout</span></span>

<span data-ttu-id="10432-239">Bestimmt die maximale Zeit, die ein Vorgang in der Sitzung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="10432-239">Determines the maximum time that any operation in the session can run.</span></span> <span data-ttu-id="10432-240">Wenn das Intervall abläuft, schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="10432-240">When the interval expires, the operation fails.</span></span> <span data-ttu-id="10432-241">Geben Sie einen Wert in Millisekunden ein.</span><span class="sxs-lookup"><span data-stu-id="10432-241">Enter a value in milliseconds.</span></span>

<span data-ttu-id="10432-242">Der Standardwert ist 180000 (3 Minuten).</span><span class="sxs-lookup"><span data-stu-id="10432-242">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="10432-243">Der Wert 0 (null) bedeutet, dass kein Timeout besteht; der Vorgang wird auf unbestimmte Zeit fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="10432-243">A value of 0 (zero) means no time-out; the operation continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-244">-Outputbufferingmode</span><span class="sxs-lookup"><span data-stu-id="10432-244">-OutputBufferingMode</span></span>

<span data-ttu-id="10432-245">Bestimmt, wie die Befehlsausgabe in getrennten Sitzungen verwaltet wird, wenn sich der Ausgabepuffer füllt.</span><span class="sxs-lookup"><span data-stu-id="10432-245">Determines how command output is managed in disconnected sessions when the output buffer becomes full.</span></span>

<span data-ttu-id="10432-246">Wenn der Modus für die Ausgabepufferung in der Sitzung oder der Sitzungskonfiguration nicht festgelegt ist, ist der Standardwert **Block** .</span><span class="sxs-lookup"><span data-stu-id="10432-246">If the output buffering mode is not set in the session or in the session configuration, the default value is **Block** .</span></span> <span data-ttu-id="10432-247">Benutzer können den Modus für die Ausgabepufferung auch beim Trennen der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="10432-247">Users can also change the output buffering mode when disconnecting the session.</span></span>

<span data-ttu-id="10432-248">Wenn Sie diesen Parameter weglassen, ist der Wert von **outputbufferingmode** des Sitzungs Options Objekts "None".</span><span class="sxs-lookup"><span data-stu-id="10432-248">If you omit this parameter, the value of the **OutputBufferingMode** of the session option object is None.</span></span> <span data-ttu-id="10432-249">Ein Wert von **Block** oder **Drop** überschreibt die Transportoption des Modus für die Ausgabepufferung, die in der Sitzungskonfiguration festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="10432-249">A value of **Block** or **Drop** overrides the output buffering mode transport option set in the session configuration.</span></span> <span data-ttu-id="10432-250">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="10432-250">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="10432-251">Blockierung.</span><span class="sxs-lookup"><span data-stu-id="10432-251">Block.</span></span> <span data-ttu-id="10432-252">Wenn der Ausgabepuffer voll ist, wird die Ausführung unterbrochen, bis der Puffer leer ist.</span><span class="sxs-lookup"><span data-stu-id="10432-252">When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="10432-253">Ablage.</span><span class="sxs-lookup"><span data-stu-id="10432-253">Drop.</span></span> <span data-ttu-id="10432-254">Wenn der Ausgabepuffer voll ist, wird die Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="10432-254">When the output buffer is full, execution continues.</span></span> <span data-ttu-id="10432-255">Sobald neue Ausgabedaten gespeichert werden, wird die älteste Ausgabe verworfen.</span><span class="sxs-lookup"><span data-stu-id="10432-255">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="10432-256">Keine</span><span class="sxs-lookup"><span data-stu-id="10432-256">None.</span></span> <span data-ttu-id="10432-257">Es wurde kein Ausgabepufferungsmodus angegeben.</span><span class="sxs-lookup"><span data-stu-id="10432-257">No output buffering mode is specified.</span></span>

<span data-ttu-id="10432-258">Weitere Informationen zur Transport Option "Output bufferingmode" finden Sie unter `New-PSTransportOption` .</span><span class="sxs-lookup"><span data-stu-id="10432-258">For more information about the output buffering mode transport option, see `New-PSTransportOption`.</span></span>

<span data-ttu-id="10432-259">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="10432-259">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-260">-Proxyaccesstype</span><span class="sxs-lookup"><span data-stu-id="10432-260">-ProxyAccessType</span></span>

<span data-ttu-id="10432-261">Bestimmt, welcher Mechanismus verwendet wird, um den Hostnamen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="10432-261">Determines which mechanism is used to resolve the host name.</span></span> <span data-ttu-id="10432-262">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="10432-262">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="10432-263">Ieconfig</span><span class="sxs-lookup"><span data-stu-id="10432-263">IEConfig</span></span>
- <span data-ttu-id="10432-264">Winhttpconfig</span><span class="sxs-lookup"><span data-stu-id="10432-264">WinHttpConfig</span></span>
- <span data-ttu-id="10432-265">Auto Ermittlung</span><span class="sxs-lookup"><span data-stu-id="10432-265">AutoDetect</span></span>
- <span data-ttu-id="10432-266">Noproxyserver</span><span class="sxs-lookup"><span data-stu-id="10432-266">NoProxyServer</span></span>
- <span data-ttu-id="10432-267">Keine</span><span class="sxs-lookup"><span data-stu-id="10432-267">None</span></span>

<span data-ttu-id="10432-268">Der Standardwert lautet „Keine“.</span><span class="sxs-lookup"><span data-stu-id="10432-268">The default value is None.</span></span>

<span data-ttu-id="10432-269">Informationen zu den Werten dieses Parameters finden Sie unter [proxyaccesstype-Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype?redirectedfrom=MSDN&view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="10432-269">For information about the values of this parameter, see [ProxyAccessType Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype?redirectedfrom=MSDN&view=powershellsdk-1.1.0).</span></span>

```yaml
Type: System.Management.Automation.Remoting.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: None, IEConfig, WinHttpConfig, AutoDetect, NoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-270">-Proxy Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="10432-270">-ProxyAuthentication</span></span>

<span data-ttu-id="10432-271">Gibt die Authentifizierungsmethode an, die für die Proxyauflösung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="10432-271">Specifies the authentication method that is used for proxy resolution.</span></span> <span data-ttu-id="10432-272">Die zulässigen Werte für diesen Parameter sind: **Basic** , **Digest** und **Aushandlungs** .</span><span class="sxs-lookup"><span data-stu-id="10432-272">The acceptable values for this parameter are: **Basic** , **Digest** , and **Negotiate** .</span></span> <span data-ttu-id="10432-273">Der Standardwert ist " **aushandeln** ".</span><span class="sxs-lookup"><span data-stu-id="10432-273">The default value is **Negotiate** .</span></span>

<span data-ttu-id="10432-274">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?redirectedfrom=MSDN&view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="10432-274">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?redirectedfrom=MSDN&view=powershellsdk-1.1.0).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-275">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="10432-275">-ProxyCredential</span></span>

<span data-ttu-id="10432-276">Gibt die Anmeldeinformationen an, die für die Proxyauthentifizierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="10432-276">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="10432-277">Geben Sie eine Variable ein, die ein **PSCredential** -Objekt enthält, oder einen Befehl, der ein **PSCredential** -Objekt abruft, z `Get-Credential` . b. einen Befehl.</span><span class="sxs-lookup"><span data-stu-id="10432-277">Enter a variable that contains a **PSCredential** object or a command that gets a **PSCredential** object, such as a `Get-Credential` command.</span></span> <span data-ttu-id="10432-278">Wenn diese Option nicht festgelegt ist, werden keine Anmeldeinformationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="10432-278">If this option is not set, no credentials are specified.</span></span>

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

### <span data-ttu-id="10432-279">-Skipcacheck</span><span class="sxs-lookup"><span data-stu-id="10432-279">-SkipCACheck</span></span>

<span data-ttu-id="10432-280">Gibt an, dass der Client beim Herstellen einer Verbindung über HTTPS nicht überprüft, ob das Serverzertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certification Authority, ca) signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="10432-280">Specifies that when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="10432-281">Verwenden Sie diese Option nur, wenn der Remotecomputer vertrauenswürdig ist, weil er einen anderen Mechanismus verwendet, z. B. wenn er Teil eines physisch sicheren und isolierten Netzwerks ist oder wenn der Remotecomputer in einer WinRM-Konfiguration als vertrauenswürdiger Host aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="10432-281">Use this option only when the remote computer is trusted by using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

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

### <span data-ttu-id="10432-282">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="10432-282">-SkipCNCheck</span></span>

<span data-ttu-id="10432-283">Gibt an, dass der allgemeine Name des Zertifikats (Common Name, CN) des Servers nicht mit dem Hostnamen des Servers identisch sein muss.</span><span class="sxs-lookup"><span data-stu-id="10432-283">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="10432-284">Diese Option wird nur bei Remotevorgängen verwendet, die das HTTPS-Protokoll verwenden.</span><span class="sxs-lookup"><span data-stu-id="10432-284">This option is used only in remote operations that use the HTTPS protocol.</span></span>

<span data-ttu-id="10432-285">Verwenden Sie diese Option nur für vertrauenswürdige Computer.</span><span class="sxs-lookup"><span data-stu-id="10432-285">Use this option only for trusted computers.</span></span>

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

### <span data-ttu-id="10432-286">-Skiprevocationcheck</span><span class="sxs-lookup"><span data-stu-id="10432-286">-SkipRevocationCheck</span></span>

<span data-ttu-id="10432-287">Der Sperrstatus des Serverzertifikats wird nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="10432-287">Does not validate the revocation status of the server certificate.</span></span>

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

### <span data-ttu-id="10432-288">-UICulture</span><span class="sxs-lookup"><span data-stu-id="10432-288">-UICulture</span></span>

<span data-ttu-id="10432-289">Gibt die Kultur der Benutzeroberfläche an, die für die Sitzung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10432-289">Specifies the UI culture to use for the session.</span></span>

<span data-ttu-id="10432-290">Gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="10432-290">Valid values include:</span></span>

- <span data-ttu-id="10432-291">Ein Kultur Name im- `<languagecode2>-<country/regioncode2>` Format, z. b. `ja-JP`</span><span class="sxs-lookup"><span data-stu-id="10432-291">A culture name in `<languagecode2>-<country/regioncode2>` format, such as `ja-JP`</span></span>
- <span data-ttu-id="10432-292">Eine Variable, die ein **CultureInfo** -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="10432-292">A variable that contains a **CultureInfo** object</span></span>
- <span data-ttu-id="10432-293">Ein Befehl, der ein **CultureInfo** -Objekt abruft, z. b. `Get-Culture`</span><span class="sxs-lookup"><span data-stu-id="10432-293">A command that gets a **CultureInfo** object, such as `Get-Culture`</span></span>

<span data-ttu-id="10432-294">Der Standardwert ist `$null` , und die Benutzeroberflächen Kultur, die beim Erstellen der Sitzung im Betriebssystem festgelegt wird, wird in der Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="10432-294">The default value is `$null`, and the UI culture that is set in the operating system when the session is created is used in the session.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10432-295">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="10432-295">-UseUTF16</span></span>

<span data-ttu-id="10432-296">Gibt an, dass dieses Cmdlet die Anforderung im UTF16-Format anstatt im UTF8-Format codiert.</span><span class="sxs-lookup"><span data-stu-id="10432-296">Indicates that this cmdlet encodes the request in UTF16 format instead of UTF8 format.</span></span>

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

### <span data-ttu-id="10432-297">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="10432-297">CommonParameters</span></span>

<span data-ttu-id="10432-298">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="10432-298">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="10432-299">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="10432-299">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="10432-300">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="10432-300">INPUTS</span></span>

### <span data-ttu-id="10432-301">Keine</span><span class="sxs-lookup"><span data-stu-id="10432-301">None</span></span>

<span data-ttu-id="10432-302">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="10432-302">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="10432-303">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="10432-303">OUTPUTS</span></span>

### <span data-ttu-id="10432-304">System. Management. Automation. Remoting. pssessionoption</span><span class="sxs-lookup"><span data-stu-id="10432-304">System.Management.Automation.Remoting.PSSessionOption</span></span>

## <span data-ttu-id="10432-305">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="10432-305">NOTES</span></span>

<span data-ttu-id="10432-306">Wenn der **sessionoption** -Parameter in einem Befehl zum Erstellen einer **PSSession** nicht verwendet wird, werden die Sitzungs Optionen durch die Eigenschaftswerte der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="10432-306">If the **SessionOption** parameter is not used in a command to create a **PSSession** , the session options are determined by the property values of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="10432-307">Weitere Informationen zur- `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="10432-307">For more information about the `$PSSessionOption` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="10432-308">Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="10432-308">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="10432-309">Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="10432-309">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="10432-310">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="10432-310">RELATED LINKS</span></span>

[<span data-ttu-id="10432-311">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="10432-311">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="10432-312">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="10432-312">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="10432-313">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="10432-313">New-PSSession</span></span>](New-PSSession.md)
