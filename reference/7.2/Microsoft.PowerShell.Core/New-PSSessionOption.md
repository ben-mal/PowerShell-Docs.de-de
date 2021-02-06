---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionOption
ms.openlocfilehash: d07942797bad3666a263e017fa8372e672936041
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600311"
---
# <span data-ttu-id="c0d16-102">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="c0d16-102">New-PSSessionOption</span></span>

## <span data-ttu-id="c0d16-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c0d16-103">SYNOPSIS</span></span>
<span data-ttu-id="c0d16-104">Erstellt ein Objekt, das erweiterte Optionen für eine PSSession enthält.</span><span class="sxs-lookup"><span data-stu-id="c0d16-104">Creates an object that contains advanced options for a PSSession.</span></span>

## <span data-ttu-id="c0d16-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c0d16-105">SYNTAX</span></span>

```
New-PSSessionOption [-MaximumRedirection <Int32>] [-NoCompression] [-NoMachineProfile] [-Culture <CultureInfo>]
 [-UICulture <CultureInfo>] [-MaximumReceivedDataSizePerCommand <Int32>] [-MaximumReceivedObjectSize <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-MaxConnectionRetryCount <Int32>]
 [-ApplicationArguments <PSPrimitiveDictionary>] [-OpenTimeout <Int32>] [-CancelTimeout <Int32>]
 [-IdleTimeout <Int32>] [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <AuthenticationMechanism>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [-IncludePortInSPN] [<CommonParameters>]
```

## <span data-ttu-id="c0d16-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c0d16-106">DESCRIPTION</span></span>

<span data-ttu-id="c0d16-107">Das- `New-PSSessionOption` Cmdlet erstellt ein Objekt, das erweiterte Optionen für eine vom Benutzer verwaltete Sitzung (**PSSession**) enthält.</span><span class="sxs-lookup"><span data-stu-id="c0d16-107">The `New-PSSessionOption` cmdlet creates an object that contains advanced options for a user-managed session (**PSSession**).</span></span> <span data-ttu-id="c0d16-108">Sie können das-Objekt als Wert des **sessionoption** -Parameters von Cmdlets verwenden, die eine **PSSession** erstellen, `New-PSSession` z `Enter-PSSession` . b `Invoke-Command` ., und.</span><span class="sxs-lookup"><span data-stu-id="c0d16-108">You can use the object as the value of the **SessionOption** parameter of cmdlets that create a **PSSession**, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

<span data-ttu-id="c0d16-109">Ohne Parameter `New-PSSessionOption` generiert ein Objekt, das die Standardwerte für alle Optionen enthält.</span><span class="sxs-lookup"><span data-stu-id="c0d16-109">Without parameters, `New-PSSessionOption` generates an object that contains the default values for all of the options.</span></span> <span data-ttu-id="c0d16-110">Da alle Eigenschaften bearbeitet werden können, können Sie das resultierende Objekt als Vorlage verwenden und Standardoptionsobjekte für Ihr Unternehmen erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-110">Because all of the properties can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="c0d16-111">Sie können ein Sitzungs Options Objekt auch in der `$PSSessionOption` Preference-Variablen speichern.</span><span class="sxs-lookup"><span data-stu-id="c0d16-111">You can also save a session option object in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="c0d16-112">Die Werte dieser Variablen richten neue Standardwerte für die Sitzungsoptionen ein.</span><span class="sxs-lookup"><span data-stu-id="c0d16-112">The values of this variable establish new default values for the session options.</span></span> <span data-ttu-id="c0d16-113">Sie sind gültig, wenn keine Sitzungsoptionen für die Sitzung festgelegt sind, und haben Vorrang vor Optionen, die in der Sitzungskonfiguration festgelegt sind. Durch Angabe von Sitzungsoptionen oder einem Sitzungsoptionsobjekt in einem Cmdlet, das eine Sitzung erstellt, können Sie sie jedoch überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c0d16-113">They effective when no session options are set for the session and they take precedence over options set in the session configuration, but you can override them by specifying session options or a session option object in a cmdlet that creates a session.</span></span> <span data-ttu-id="c0d16-114">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="c0d16-114">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="c0d16-115">Wenn Sie ein Sitzungsoptionsobjekt in einem Cmdlet verwenden, das eine Sitzung erstellt, haben die Sitzungsoptionswerte Vorrang vor Standardwerten für Sitzungen, die in der $PSSessionOption-Einstellungsvariablen und der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="c0d16-115">When you use a session option object in a cmdlet that creates a session, the session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="c0d16-116">Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="c0d16-116">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="c0d16-117">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="c0d16-117">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="c0d16-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c0d16-118">EXAMPLES</span></span>

### <span data-ttu-id="c0d16-119">Beispiel 1: Erstellen einer Standard Sitzungs Option</span><span class="sxs-lookup"><span data-stu-id="c0d16-119">Example 1: Create a default session option</span></span>

<span data-ttu-id="c0d16-120">Mit diesem Befehl wird ein Sitzungs Options Objekt erstellt, das alle Standardwerte aufweist.</span><span class="sxs-lookup"><span data-stu-id="c0d16-120">This command creates a session option object that has all of the default values.</span></span>

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

### <span data-ttu-id="c0d16-121">Beispiel 2: Konfigurieren einer Sitzung mithilfe eines Sitzungs Options Objekts</span><span class="sxs-lookup"><span data-stu-id="c0d16-121">Example 2: Configure a session by using a session option object</span></span>

<span data-ttu-id="c0d16-122">In diesem Beispiel wird gezeigt, wie Sie eine Sitzung mit einem Sitzungsoptionsobjekt konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c0d16-122">This example shows how to use a session option object to configure a session.</span></span>

```powershell
$pso = New-PSSessionOption -Culture "fr-fr" -MaximumReceivedObjectSize 10MB
New-PSSession -ComputerName Server01 -SessionOption $pso
```

<span data-ttu-id="c0d16-123">Mit dem ersten Befehl wird ein neues Sitzungs Options Objekt erstellt und im Wert der Variablen gespeichert `$pso` .</span><span class="sxs-lookup"><span data-stu-id="c0d16-123">The first command creates a new session option object and saves it in the value of the `$pso` variable.</span></span> <span data-ttu-id="c0d16-124">Der zweite Befehl verwendet das `New-PSSession` Cmdlet, um eine Sitzung auf dem Remote Computer Server01 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-124">The second command uses the `New-PSSession` cmdlet to create a session on the Server01 remote computer.</span></span> <span data-ttu-id="c0d16-125">Der Befehl verwendet das Sitzungs Options Objekt im Wert der `$pso` Variablen als Wert des **sessionoption** -Parameters des-Befehls.</span><span class="sxs-lookup"><span data-stu-id="c0d16-125">The command uses the session option object in the value of the `$pso` variable as the value of the **SessionOption** parameter of the command.</span></span>

### <span data-ttu-id="c0d16-126">Beispiel 3: Starten einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="c0d16-126">Example 3: Start an interactive session</span></span>

<span data-ttu-id="c0d16-127">Dieser Befehl verwendet das `Enter-PSSession` Cmdlet, um eine interaktive Sitzung mit dem Server01-Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="c0d16-127">This command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

```powershell
Enter-PSSession -ComputerName Server01 -SessionOption (New-PSSessionOption -NoEncryption -NoCompression)
```

<span data-ttu-id="c0d16-128">Der Wert des **sessionoption** -Parameters ist ein `New-PSSessionOption` Befehl, der über die Parameter **NoEncryption** und **NoCompression** verfügt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-128">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that has the **NoEncryption** and **NoCompression** parameters.</span></span>

<span data-ttu-id="c0d16-129">Der `New-PSSessionOption` Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er vor dem Befehl ausgeführt wird `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="c0d16-129">The `New-PSSessionOption` command is enclosed in parentheses to make sure that it runs before the `Enter-PSSession` command.</span></span>

### <span data-ttu-id="c0d16-130">Beispiel 4: Ändern eines Sitzungs Options Objekts</span><span class="sxs-lookup"><span data-stu-id="c0d16-130">Example 4: Modify a session option object</span></span>

<span data-ttu-id="c0d16-131">In diesem Beispiel wird veranschaulicht, dass Sie das Sitzungs Options Objekt ändern können.</span><span class="sxs-lookup"><span data-stu-id="c0d16-131">This example demonstrates that you can modify the session option object.</span></span> <span data-ttu-id="c0d16-132">Alle Eigenschaften verfügen über Lese-/Schreibwerte.</span><span class="sxs-lookup"><span data-stu-id="c0d16-132">All properties have read/write values.</span></span>

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

<span data-ttu-id="c0d16-133">Verwenden Sie diese Methode, um ein Standardsitzungsobjekt für Ihr Unternehmen zu erstellen, und dann angepasste Versionen für bestimmte Verwendungszwecke anzulegen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-133">Use this method to create a standard session object for your enterprise, and then create customized versions of it for particular uses.</span></span>

### <span data-ttu-id="c0d16-134">Beispiel 5: Erstellen einer Einstellungs Variablen</span><span class="sxs-lookup"><span data-stu-id="c0d16-134">Example 5: Create a preference variable</span></span>

<span data-ttu-id="c0d16-135">Dieser Befehl erstellt eine Einstellungs `$PSSessionOption` Variable.</span><span class="sxs-lookup"><span data-stu-id="c0d16-135">This command creates a `$PSSessionOption` preference variable.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -OpenTimeOut 120000
```

<span data-ttu-id="c0d16-136">Wenn die Einstellungs `$PSSessionOption` Variable in der Sitzung auftritt, werden Standardwerte für Optionen in den Sitzungen festgelegt, die mit den `New-PSSession` `Enter-PSSession` Cmdlets, und erstellt werden `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="c0d16-136">When the `$PSSessionOption` preference variable occurs in the session, it establishes default values for options in the sessions that are created by using the `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="c0d16-137">Um die `$PSSessionOption` Variable in allen Sitzungen verfügbar zu machen, fügen Sie Sie der PowerShell-Sitzung und Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="c0d16-137">To make the `$PSSessionOption` variable available in all sessions, add it to your PowerShell session and to your PowerShell profile.</span></span>

<span data-ttu-id="c0d16-138">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="c0d16-138">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="c0d16-139">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c0d16-139">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

### <span data-ttu-id="c0d16-140">Beispiel 6: erfüllen der Anforderungen an eine Remote Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c0d16-140">Example 6: Fulfill the requirements for a remote session configuration</span></span>

<span data-ttu-id="c0d16-141">In diesem Beispiel wird gezeigt, wie ein **SessionOption**-Objekt verwendet wird, um die Anforderungen für eine Remotesitzungskonfiguration zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-141">This example shows how to use a **SessionOption** object to fulfill the requirements for a remote session configuration.</span></span>

```powershell
$skipCN = New-PSSessionOption -SkipCNCheck
New-PSSession -ComputerName 171.09.21.207 -UseSSL -Credential Domain01\User01 -SessionOption $SkipCN
```

<span data-ttu-id="c0d16-142">Der erste Befehl verwendet das `New-PSSessionOption` Cmdlet, um ein Sitzungs Options Objekt zu erstellen, das über die **skipcncheck** -Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-142">The first command uses the `New-PSSessionOption` cmdlet to create a session option object that has the **SkipCNCheck** property.</span></span> <span data-ttu-id="c0d16-143">Der Befehl speichert das resultierende Sitzungs Objekt in der `$skipCN` Variablen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-143">The command saves the resulting session object in the `$skipCN` variable.</span></span>

<span data-ttu-id="c0d16-144">Der zweite Befehl verwendet das `New-PSSession` Cmdlet, um eine neue Sitzung auf einem Remote Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-144">The second command uses the `New-PSSession` cmdlet to create a new session on a remote computer.</span></span> <span data-ttu-id="c0d16-145">Die `$skipCN` Check-Variable wird im Wert des **sessionoption** -Parameters verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0d16-145">The `$skipCN` check variable is used in the value of the **SessionOption** parameter.</span></span>

<span data-ttu-id="c0d16-146">Da der Computer anhand seiner IP-Adresse identifiziert wird, entspricht der Wert des Computer **Name** -Parameters keinem der allgemeinen Namen im Zertifikat, das für Secure Sockets Layer (SSL) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c0d16-146">Because the computer is identified by its IP address, the value of the **ComputerName** parameter does not match any of the common names in the certificate that is used for Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="c0d16-147">Demzufolge ist die **SkipCNCheck**-Option erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c0d16-147">As a result, the **SkipCNCheck** option is required.</span></span>

### <span data-ttu-id="c0d16-148">Beispiel 7: Bereitstellen von Argumenten für eine Remote Sitzung</span><span class="sxs-lookup"><span data-stu-id="c0d16-148">Example 7: Make arguments available to a remote session</span></span>

<span data-ttu-id="c0d16-149">In diesem Beispiel wird gezeigt, wie der **applicationarguments** -Parameter des `New-PSSessionOption` Cmdlets verwendet wird, um zusätzliche Daten für die Remote Sitzung verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-149">This example shows how to use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet to make additional data available to the remote session.</span></span>

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

<span data-ttu-id="c0d16-150">Der erste Befehl erstellt eine Hash Tabelle mit zwei Schlüsseln: " **Team** " und " **use**".</span><span class="sxs-lookup"><span data-stu-id="c0d16-150">The first command creates a hash table with two keys, **Team** and **Use**.</span></span> <span data-ttu-id="c0d16-151">Der Befehl speichert die Hash Tabelle in der `$team` Variablen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-151">The command saves the hash table in the `$team` variable.</span></span> <span data-ttu-id="c0d16-152">Weitere Informationen zu Hashtabellen finden Sie unter [about_Hash_Tables](about/about_Hash_Tables.md) (Informationen zu Hashtabellen).</span><span class="sxs-lookup"><span data-stu-id="c0d16-152">For more information about hash tables, see [about_Hash_Tables](about/about_Hash_Tables.md).</span></span>

<span data-ttu-id="c0d16-153">Im nächsten Schritt `New-PSSessionOption` erstellt das Cmdlet mit dem **applicationarguments** -Parameter ein Sitzungs Options Objekt, das in der Variablen gespeichert ist `$team` .</span><span class="sxs-lookup"><span data-stu-id="c0d16-153">Next, the `New-PSSessionOption` cmdlet, using the **ApplicationArguments** parameter, creates a session option object saved in the `$team` variable.</span></span> <span data-ttu-id="c0d16-154">Wenn `New-PSSessionOption` das Sitzungs Options Objekt erstellt, wird die Hash Tabelle im Wert des **applicationarguments** -Parameters automatisch in ein Primitives Wörterbuch konvertiert, damit die Daten zuverlässig an die Remote Sitzung übermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="c0d16-154">When `New-PSSessionOption` creates the session option object, it automatically converts the hash table in the value of the **ApplicationArguments** parameter to a primitive dictionary so the data can be reliably transmitted to the remote session.</span></span>

<span data-ttu-id="c0d16-155">Mit dem- `New-PSSession` Cmdlet wird eine Sitzung auf dem Server01-Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="c0d16-155">The `New-PSSession` cmdlet starts a session on the Server01 computer.</span></span> <span data-ttu-id="c0d16-156">Er verwendet den **sessionoption** -Parameter, um die Optionen in der `$teamOption` Variablen einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-156">It uses the **SessionOption** parameter to include the options in the `$teamOption` variable.</span></span>

<span data-ttu-id="c0d16-157">Das `Invoke-Command` Cmdlet zeigt, dass die Daten in der `$team` Variablen für Befehle in der Remote Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c0d16-157">The `Invoke-Command` cmdlet demonstrates that the data in the `$team` variable is available to commands in the remote session.</span></span> <span data-ttu-id="c0d16-158">Die Daten werden in der **applicationarguments** -Eigenschaft der `$PSSenderInfo` automatischen Variable angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-158">The data appears in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span>

<span data-ttu-id="c0d16-159">Die letzte `Invoke-Command` zeigt, wie die Daten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c0d16-159">The final `Invoke-Command` shows how the data might be used.</span></span>

## <span data-ttu-id="c0d16-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c0d16-160">PARAMETERS</span></span>

### <span data-ttu-id="c0d16-161">-Applicationarguments</span><span class="sxs-lookup"><span data-stu-id="c0d16-161">-ApplicationArguments</span></span>

<span data-ttu-id="c0d16-162">Gibt ein primitives Wörterbuch an, das an die Remotesitzung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="c0d16-162">Specifies a primitive dictionary that is sent to the remote session.</span></span> <span data-ttu-id="c0d16-163">Durch Befehle und Skripts in der Remote Sitzung, einschließlich Start Skripts in der Sitzungs Konfiguration, kann dieses Wörterbuch in der **applicationarguments** -Eigenschaft der `$PSSenderInfo` automatischen Variablen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="c0d16-163">Commands and scripts in the remote session, including startup scripts in the session configuration, can find this dictionary in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span> <span data-ttu-id="c0d16-164">Sie können diesen Parameter verwenden, um Daten an die Remotesitzung zu senden.</span><span class="sxs-lookup"><span data-stu-id="c0d16-164">You can use this parameter to send data to the remote session.</span></span>

<span data-ttu-id="c0d16-165">Weitere Informationen finden Sie unter [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md)und [about_Automatic_Variables](about/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="c0d16-165">For more information, see [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md), and [about_Automatic_Variables](about/about_Automatic_Variables.md).</span></span>

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

### <span data-ttu-id="c0d16-166">-Canceltimeout</span><span class="sxs-lookup"><span data-stu-id="c0d16-166">-CancelTimeout</span></span>

<span data-ttu-id="c0d16-167">Bestimmt, wie lange PowerShell darauf wartet, dass ein Abbruch Vorgang (STRG + C) beendet wird, bevor Sie beendet wird.</span><span class="sxs-lookup"><span data-stu-id="c0d16-167">Determines how long PowerShell waits for a cancel operation (CTRL+C) to finish before ending it.</span></span>
<span data-ttu-id="c0d16-168">Geben Sie einen Wert in Millisekunden ein.</span><span class="sxs-lookup"><span data-stu-id="c0d16-168">Enter a value in milliseconds.</span></span>

<span data-ttu-id="c0d16-169">Der Standardwert ist 60000 (eine Minute).</span><span class="sxs-lookup"><span data-stu-id="c0d16-169">The default value is 60000 (one minute).</span></span> <span data-ttu-id="c0d16-170">Der Wert 0 (null) bedeutet, dass kein Timeout besteht; der Befehl wird auf unbestimmte Zeit fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-170">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

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

### <span data-ttu-id="c0d16-171">-Kultur</span><span class="sxs-lookup"><span data-stu-id="c0d16-171">-Culture</span></span>

<span data-ttu-id="c0d16-172">Gibt die Kultur an, die für die Sitzung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0d16-172">Specifies the culture to use for the session.</span></span> <span data-ttu-id="c0d16-173">Geben Sie einen Kultur Namen im Format (z. b `<languagecode2>-<country/regioncode2>` `ja-JP` .), eine Variable mit einem **CultureInfo** -Objekt oder einen Befehl ein, der ein **CultureInfo** -Objekt abruft.</span><span class="sxs-lookup"><span data-stu-id="c0d16-173">Enter a culture name in `<languagecode2>-<country/regioncode2>` format (like `ja-JP`), a variable that contains a **CultureInfo** object, or a command that gets a **CultureInfo** object.</span></span>

<span data-ttu-id="c0d16-174">Der Standardwert ist `$Null` , und die im Betriebssystem festgelegte Kultur wird in der Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0d16-174">The default value is `$Null`, and the culture that is set in the operating system is used in the session.</span></span>

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

### <span data-ttu-id="c0d16-175">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="c0d16-175">-IdleTimeout</span></span>

<span data-ttu-id="c0d16-176">Bestimmt, wie lange die Sitzung geöffnet bleibt, wenn der Remote Computer keine Kommunikation vom lokalen Computer empfängt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-176">Determines how long the session stays open if the remote computer does not receive any communication from the local computer.</span></span> <span data-ttu-id="c0d16-177">Dies schließt das Taktsignal ein.</span><span class="sxs-lookup"><span data-stu-id="c0d16-177">This includes the heartbeat signal.</span></span> <span data-ttu-id="c0d16-178">Wenn das Intervall abläuft, wird die Sitzung geschlossen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-178">When the interval expires, the session closes.</span></span>

<span data-ttu-id="c0d16-179">Der Wert für das Leerlauf Timeout ist von großer Wichtigkeit, wenn Sie die Verbindung mit einer Sitzung trennen und wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c0d16-179">The idle time-out value is of significant importance if you intend to disconnect and reconnect to a session.</span></span> <span data-ttu-id="c0d16-180">Sie können die Sitzung nur dann wiederherstellen, wenn kein Timeout aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c0d16-180">You can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="c0d16-181">Geben Sie einen Wert in Millisekunden ein.</span><span class="sxs-lookup"><span data-stu-id="c0d16-181">Enter a value in milliseconds.</span></span> <span data-ttu-id="c0d16-182">Der Mindestwert ist 60000 (1 Minute).</span><span class="sxs-lookup"><span data-stu-id="c0d16-182">The minimum value is 60000 (1 minute).</span></span> <span data-ttu-id="c0d16-183">Der Höchstwert ist der Wert der **MaxIdleTimeoutms**-Eigenschaft der Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="c0d16-183">The maximum is the value of the **MaxIdleTimeoutms** property of the session configuration.</span></span> <span data-ttu-id="c0d16-184">Der Standardwert-1 legt kein Leerlauf Timeout fest.</span><span class="sxs-lookup"><span data-stu-id="c0d16-184">The default value, -1, does not set an idle time-out.</span></span>

<span data-ttu-id="c0d16-185">Die Sitzung verwendet das Leerlauf Timeout, das in den Sitzungs Optionen festgelegt wird (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="c0d16-185">The session uses the idle time-out that is set in the session options, if any.</span></span> <span data-ttu-id="c0d16-186">Wenn keine festgelegt ist (-1), verwendet die Sitzung den Wert der **idletimeoutms** -Eigenschaft der Sitzungs Konfiguration oder den Timeout Wert der WSMAN-Shell ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ), je nachdem, welcher Wert am kürzesten ist.</span><span class="sxs-lookup"><span data-stu-id="c0d16-186">If none is set (-1), the session uses the value of the **IdleTimeoutMs** property of the session configuration or the WSMan shell time-out value (`WSMan:\<ComputerName>\Shell\IdleTimeout`), whichever is shortest.</span></span>

<span data-ttu-id="c0d16-187">Überschreitet das Leerlaufzeitlimit in den Sitzungsoptionen den Wert der **MaxIdleTimeoutMs**-Eigenschaft der Sitzungskonfiguration, tritt bei dem Befehl zum Erstellen der Sitzung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c0d16-187">If the idle timeout set in the session options exceeds the value of the **MaxIdleTimeoutMs** property of the session configuration, the command to create a session fails.</span></span>

<span data-ttu-id="c0d16-188">Der **idletimeoutms** -Wert der standardmäßigen **Microsoft. PowerShell** -Sitzungs Konfiguration beträgt 7,2 Millionen Millisekunden (2 Stunden).</span><span class="sxs-lookup"><span data-stu-id="c0d16-188">The **IdleTimeoutMs** value of the default **Microsoft.PowerShell** session configuration is 7200000 milliseconds (2 hours).</span></span> <span data-ttu-id="c0d16-189">Der **maxidletimeoutms** -Wert beträgt 2147483647 Millisekunden ( \> 24 Tage).</span><span class="sxs-lookup"><span data-stu-id="c0d16-189">Its **MaxIdleTimeoutMs** value is 2147483647 milliseconds (\>24 days).</span></span> <span data-ttu-id="c0d16-190">Der Standardwert des Leerlauf Timeouts () für WSMAN-Shell `WSMan:\<ComputerName>\Shell\IdleTimeout` beträgt 7,2 Millionen Millisekunden (2 Stunden).</span><span class="sxs-lookup"><span data-stu-id="c0d16-190">The default value of the WSMan shell idle time-out (`WSMan:\<ComputerName>\Shell\IdleTimeout`) is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="c0d16-191">Der Leerlauf Timeout Wert einer Sitzung kann auch geändert werden, wenn die Verbindung mit einer Sitzung getrennt oder eine Verbindung mit einer Sitzung wieder hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c0d16-191">The idle time-out value of a session can also be changed when disconnecting from a session or reconnecting to a session.</span></span> <span data-ttu-id="c0d16-192">Weitere Informationen finden Sie unter `Disconnect-PSSession` und `Connect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="c0d16-192">For more information, see `Disconnect-PSSession` and `Connect-PSSession`.</span></span>

<span data-ttu-id="c0d16-193">In Windows PowerShell 2.0 beträgt der Standardwert des **IdleTimeout**-Parameters 240000 (4 Minuten).</span><span class="sxs-lookup"><span data-stu-id="c0d16-193">In Windows PowerShell 2.0, the default value of the **IdleTimeout** parameter is 240000 (4 minutes).</span></span>

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

### <span data-ttu-id="c0d16-194">-Includeportinspn</span><span class="sxs-lookup"><span data-stu-id="c0d16-194">-IncludePortInSPN</span></span>

<span data-ttu-id="c0d16-195">Schließt die Portnummer in den Dienst Prinzipal Namen (SPN) ein, die für die Kerberos-Authentifizierung verwendet wird, z `HTTP://<ComputerName>:5985` . b..</span><span class="sxs-lookup"><span data-stu-id="c0d16-195">Includes the port number in the Service Principal Name (SPN) used for Kerberos authentication, for example, `HTTP://<ComputerName>:5985`.</span></span> <span data-ttu-id="c0d16-196">Mit dieser Option kann ein Client, der einen nicht standardmäßigen SPN verwendet, von einem Remotecomputer authentifiziert werden, der die Kerberos-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0d16-196">This option allows a client that uses a non-default SPN to authenticate against a remote computer that uses Kerberos authentication.</span></span>

<span data-ttu-id="c0d16-197">Diese Option wurde für Organisationen entwickelt, in denen mehrere Dienste, die die Kerberos-Authentifizierung unterstützen, unter verschiedenen Benutzerkonten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c0d16-197">The option is designed for enterprises where multiple services that support Kerberos authentication are running under different user accounts.</span></span> <span data-ttu-id="c0d16-198">Beispielsweise kann eine IIS-Anwendung, die die Kerberos-Authentifizierung zulässt, erfordern, dass der Standard-SPN für ein Benutzerkonto registriert ist, das sich von dem Computer Konto unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="c0d16-198">For example, an IIS application that allows for Kerberos authentication can require the default SPN to be registered to a user account that differs from the computer account.</span></span> <span data-ttu-id="c0d16-199">In solchen Fällen kann das PowerShell-Remoting Kerberos nicht für die Authentifizierung verwenden, da es einen SPN erfordert, der für das Computer Konto registriert ist.</span><span class="sxs-lookup"><span data-stu-id="c0d16-199">In such cases, PowerShell remoting cannot use Kerberos to authenticate because it requires an SPN that is registered to the computer account.</span></span> <span data-ttu-id="c0d16-200">Um dieses Problem zu beheben, können Administratoren unterschiedliche SPNs erstellen, z. b. mit **Setspn.exe**, die für unterschiedliche Benutzerkonten registriert sind, und Sie können unterscheiden, indem Sie die Portnummer in den SPN einschließen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-200">To resolve this problem, administrators can create different SPNs, such as by using **Setspn.exe**, that are registered to different user accounts and can distinguish between them by including the port number in the SPN.</span></span>

<span data-ttu-id="c0d16-201">Weitere Informationen finden Sie unter [Übersicht über Setspn](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="c0d16-201">For more information, see [Setspn Overview](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).</span></span>

<span data-ttu-id="c0d16-202">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c0d16-203">-Maxconnectionretrycount</span><span class="sxs-lookup"><span data-stu-id="c0d16-203">-MaxConnectionRetryCount</span></span>

<span data-ttu-id="c0d16-204">Gibt an, wie oft von PowerShell versucht wird, eine Verbindung mit einem Zielcomputer herzustellen, wenn der aktuelle Versuch aufgrund von Netzwerkproblemen fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-204">Specifies the number of times that PowerShell attempts to make a connection to a target machine if the current attempt fails due to network issues.</span></span> <span data-ttu-id="c0d16-205">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="c0d16-205">The default value is 5.</span></span>

<span data-ttu-id="c0d16-206">Dieser Parameter wurde für PowerShell-Version 5,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-206">This parameter was added for PowerShell version 5.0.</span></span>

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

### <span data-ttu-id="c0d16-207">-Maximumreceiveddatasizepercommand</span><span class="sxs-lookup"><span data-stu-id="c0d16-207">-MaximumReceivedDataSizePerCommand</span></span>

<span data-ttu-id="c0d16-208">Gibt die maximale Anzahl von Bytes an, die der lokale Computer von dem Remotecomputer in einem einzigen Befehl empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="c0d16-208">Specifies the maximum number of bytes that the local computer can receive from the remote computer in a single command.</span></span> <span data-ttu-id="c0d16-209">Geben Sie einen Wert in Bytes ein.</span><span class="sxs-lookup"><span data-stu-id="c0d16-209">Enter a value in bytes.</span></span> <span data-ttu-id="c0d16-210">Standardmäßig besteht keine Größenbeschränkung für Daten.</span><span class="sxs-lookup"><span data-stu-id="c0d16-210">By default, there is no data size limit.</span></span>

<span data-ttu-id="c0d16-211">Diese Option dient zum Schutz der Ressourcen auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="c0d16-211">This option is designed to protect the resources on the client computer.</span></span>

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

### <span data-ttu-id="c0d16-212">-Maximumreceivedobjectsize</span><span class="sxs-lookup"><span data-stu-id="c0d16-212">-MaximumReceivedObjectSize</span></span>

<span data-ttu-id="c0d16-213">Gibt die maximale Größe eines Objekts an, das der lokale Computer vom Remotecomputer empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="c0d16-213">Specifies the maximum size of an object that the local computer can receive from the remote computer.</span></span> <span data-ttu-id="c0d16-214">Diese Option dient zum Schutz der Ressourcen auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="c0d16-214">This option is designed to protect the resources on the client computer.</span></span> <span data-ttu-id="c0d16-215">Geben Sie einen Wert in Bytes ein.</span><span class="sxs-lookup"><span data-stu-id="c0d16-215">Enter a value in bytes.</span></span>

<span data-ttu-id="c0d16-216">In Windows PowerShell 2.0 besteht, wenn Sie diesen Parameter weglassen, keine Größenbeschränkung für Objekte.</span><span class="sxs-lookup"><span data-stu-id="c0d16-216">In Windows PowerShell 2.0, if you omit this parameter, there is no object size limit.</span></span> <span data-ttu-id="c0d16-217">Ab Windows PowerShell 3.0 beträgt, wenn Sie diesen Parameter weglassen, der Standardwert 200 MB.</span><span class="sxs-lookup"><span data-stu-id="c0d16-217">Beginning in Windows PowerShell 3.0, if you omit this parameter, the default value is 200 MB.</span></span>

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

### <span data-ttu-id="c0d16-218">-Maximumredirect</span><span class="sxs-lookup"><span data-stu-id="c0d16-218">-MaximumRedirection</span></span>

<span data-ttu-id="c0d16-219">Bestimmt, wie oft PowerShell eine Verbindung an eine Alternative Uniform Resource Identifier (URI) umleitet, bevor die Verbindung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-219">Determines how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="c0d16-220">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="c0d16-220">The default value is 5.</span></span> <span data-ttu-id="c0d16-221">Der Wert 0 (null) unterbindet sämtliche Umleitungen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-221">A value of 0 (zero) prevents all redirection.</span></span>

<span data-ttu-id="c0d16-222">Diese Option wird in der Sitzung nur verwendet, wenn der Parameter " **Zuweisung** " in dem Befehl verwendet wird, der die Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-222">This option is used in the session only when the **AllowRedirection** parameter is used in the command that creates the session.</span></span>

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

### <span data-ttu-id="c0d16-223">-NoCompression</span><span class="sxs-lookup"><span data-stu-id="c0d16-223">-NoCompression</span></span>

<span data-ttu-id="c0d16-224">Deaktiviert die Paketkomprimierung in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c0d16-224">Turns off packet compression in the session.</span></span> <span data-ttu-id="c0d16-225">Die Komprimierung verwendet mehr Prozessorzyklen, beschleunigt aber die Übertragung.</span><span class="sxs-lookup"><span data-stu-id="c0d16-225">Compression uses more processor cycles, but it makes transmission faster.</span></span>

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

### <span data-ttu-id="c0d16-226">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="c0d16-226">-NoEncryption</span></span>

<span data-ttu-id="c0d16-227">Deaktiviert die Datenverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="c0d16-227">Turns off data encryption.</span></span>

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

### <span data-ttu-id="c0d16-228">-Nomachineprofile</span><span class="sxs-lookup"><span data-stu-id="c0d16-228">-NoMachineProfile</span></span>

<span data-ttu-id="c0d16-229">Verhindert das Laden des Windows-Benutzerprofils.</span><span class="sxs-lookup"><span data-stu-id="c0d16-229">Prevents loading the user's Windows user profile.</span></span> <span data-ttu-id="c0d16-230">Daraufhin wird die Sitzung möglicherweise schneller erstellt, aber benutzerspezifische Registrierungseinstellungen wie Umgebungsvariablen und Zertifikate sind in der Sitzung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c0d16-230">As a result, the session might be created faster, but user-specific registry settings, items such as environment variables, and certificates are not available in the session.</span></span>

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

### <span data-ttu-id="c0d16-231">-OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="c0d16-231">-OpenTimeout</span></span>

<span data-ttu-id="c0d16-232">Bestimmt, wie lange der Clientcomputer auf das Einrichten der Sitzungsverbindung wartet.</span><span class="sxs-lookup"><span data-stu-id="c0d16-232">Determines how long the client computer waits for the session connection to be established.</span></span> <span data-ttu-id="c0d16-233">Wenn das Intervall abläuft, tritt bei dem Befehl zum Herstellen der Verbindung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c0d16-233">When the interval expires, the command to establish the connection fails.</span></span> <span data-ttu-id="c0d16-234">Geben Sie einen Wert in Millisekunden ein.</span><span class="sxs-lookup"><span data-stu-id="c0d16-234">Enter a value in milliseconds.</span></span>

<span data-ttu-id="c0d16-235">Der Standardwert ist 180000 (3 Minuten).</span><span class="sxs-lookup"><span data-stu-id="c0d16-235">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="c0d16-236">Der Wert 0 (null) bedeutet, dass kein Timeout besteht; der Befehl wird auf unbestimmte Zeit fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-236">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

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

### <span data-ttu-id="c0d16-237">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="c0d16-237">-OperationTimeout</span></span>

<span data-ttu-id="c0d16-238">Bestimmt die maximale Zeit, die ein Vorgang in der Sitzung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0d16-238">Determines the maximum time that any operation in the session can run.</span></span> <span data-ttu-id="c0d16-239">Wenn das Intervall abläuft, schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="c0d16-239">When the interval expires, the operation fails.</span></span> <span data-ttu-id="c0d16-240">Geben Sie einen Wert in Millisekunden ein.</span><span class="sxs-lookup"><span data-stu-id="c0d16-240">Enter a value in milliseconds.</span></span>

<span data-ttu-id="c0d16-241">Der Standardwert ist 180000 (3 Minuten).</span><span class="sxs-lookup"><span data-stu-id="c0d16-241">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="c0d16-242">Der Wert 0 (null) bedeutet, dass kein Timeout besteht; der Vorgang wird auf unbestimmte Zeit fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-242">A value of 0 (zero) means no time-out; the operation continues indefinitely.</span></span>

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

### <span data-ttu-id="c0d16-243">-Outputbufferingmode</span><span class="sxs-lookup"><span data-stu-id="c0d16-243">-OutputBufferingMode</span></span>

<span data-ttu-id="c0d16-244">Bestimmt, wie die Befehlsausgabe in getrennten Sitzungen verwaltet wird, wenn sich der Ausgabepuffer füllt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-244">Determines how command output is managed in disconnected sessions when the output buffer becomes full.</span></span>

<span data-ttu-id="c0d16-245">Wenn der Modus für die Ausgabepufferung in der Sitzung oder der Sitzungskonfiguration nicht festgelegt ist, ist der Standardwert **Block**.</span><span class="sxs-lookup"><span data-stu-id="c0d16-245">If the output buffering mode is not set in the session or in the session configuration, the default value is **Block**.</span></span> <span data-ttu-id="c0d16-246">Benutzer können den Modus für die Ausgabepufferung auch beim Trennen der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="c0d16-246">Users can also change the output buffering mode when disconnecting the session.</span></span>

<span data-ttu-id="c0d16-247">Wenn Sie diesen Parameter weglassen, ist der Wert von **outputbufferingmode** des Sitzungs Options Objekts "None".</span><span class="sxs-lookup"><span data-stu-id="c0d16-247">If you omit this parameter, the value of the **OutputBufferingMode** of the session option object is None.</span></span> <span data-ttu-id="c0d16-248">Ein Wert von **Block** oder **Drop** überschreibt die Transportoption des Modus für die Ausgabepufferung, die in der Sitzungskonfiguration festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="c0d16-248">A value of **Block** or **Drop** overrides the output buffering mode transport option set in the session configuration.</span></span> <span data-ttu-id="c0d16-249">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="c0d16-249">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c0d16-250">Blockierung.</span><span class="sxs-lookup"><span data-stu-id="c0d16-250">Block.</span></span> <span data-ttu-id="c0d16-251">Wenn der Ausgabepuffer voll ist, wird die Ausführung unterbrochen, bis der Puffer leer ist.</span><span class="sxs-lookup"><span data-stu-id="c0d16-251">When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="c0d16-252">Ablage.</span><span class="sxs-lookup"><span data-stu-id="c0d16-252">Drop.</span></span> <span data-ttu-id="c0d16-253">Wenn der Ausgabepuffer voll ist, wird die Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-253">When the output buffer is full, execution continues.</span></span> <span data-ttu-id="c0d16-254">Sobald neue Ausgabedaten gespeichert werden, wird die älteste Ausgabe verworfen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-254">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="c0d16-255">Keine</span><span class="sxs-lookup"><span data-stu-id="c0d16-255">None.</span></span> <span data-ttu-id="c0d16-256">Es wurde kein Ausgabepufferungsmodus angegeben.</span><span class="sxs-lookup"><span data-stu-id="c0d16-256">No output buffering mode is specified.</span></span>

<span data-ttu-id="c0d16-257">Weitere Informationen zur Transport Option "Output bufferingmode" finden Sie unter `New-PSTransportOption` .</span><span class="sxs-lookup"><span data-stu-id="c0d16-257">For more information about the output buffering mode transport option, see `New-PSTransportOption`.</span></span>

<span data-ttu-id="c0d16-258">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-258">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c0d16-259">-Proxyaccesstype</span><span class="sxs-lookup"><span data-stu-id="c0d16-259">-ProxyAccessType</span></span>

<span data-ttu-id="c0d16-260">Bestimmt, welcher Mechanismus verwendet wird, um den Hostnamen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-260">Determines which mechanism is used to resolve the host name.</span></span> <span data-ttu-id="c0d16-261">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="c0d16-261">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c0d16-262">Ieconfig</span><span class="sxs-lookup"><span data-stu-id="c0d16-262">IEConfig</span></span>
- <span data-ttu-id="c0d16-263">Winhttpconfig</span><span class="sxs-lookup"><span data-stu-id="c0d16-263">WinHttpConfig</span></span>
- <span data-ttu-id="c0d16-264">Auto Ermittlung</span><span class="sxs-lookup"><span data-stu-id="c0d16-264">AutoDetect</span></span>
- <span data-ttu-id="c0d16-265">Noproxyserver</span><span class="sxs-lookup"><span data-stu-id="c0d16-265">NoProxyServer</span></span>
- <span data-ttu-id="c0d16-266">Keine</span><span class="sxs-lookup"><span data-stu-id="c0d16-266">None</span></span>

<span data-ttu-id="c0d16-267">Der Standardwert lautet „Keine“.</span><span class="sxs-lookup"><span data-stu-id="c0d16-267">The default value is None.</span></span>

<span data-ttu-id="c0d16-268">Informationen zu den Werten dieses Parameters finden Sie unter [proxyaccesstype-Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype).</span><span class="sxs-lookup"><span data-stu-id="c0d16-268">For information about the values of this parameter, see [ProxyAccessType Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype).</span></span>

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

### <span data-ttu-id="c0d16-269">-Proxy Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c0d16-269">-ProxyAuthentication</span></span>

<span data-ttu-id="c0d16-270">Gibt die Authentifizierungsmethode an, die für die Proxyauflösung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c0d16-270">Specifies the authentication method that is used for proxy resolution.</span></span> <span data-ttu-id="c0d16-271">Die zulässigen Werte für diesen Parameter sind: **Basic**, **Digest** und **Aushandlungs**.</span><span class="sxs-lookup"><span data-stu-id="c0d16-271">The acceptable values for this parameter are: **Basic**, **Digest**, and **Negotiate**.</span></span> <span data-ttu-id="c0d16-272">Der Standardwert ist " **aushandeln**".</span><span class="sxs-lookup"><span data-stu-id="c0d16-272">The default value is **Negotiate**.</span></span>

<span data-ttu-id="c0d16-273">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="c0d16-273">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

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

### <span data-ttu-id="c0d16-274">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="c0d16-274">-ProxyCredential</span></span>

<span data-ttu-id="c0d16-275">Gibt die Anmeldeinformationen an, die für die Proxyauthentifizierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c0d16-275">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="c0d16-276">Geben Sie eine Variable ein, die ein **PSCredential** -Objekt enthält, oder einen Befehl, der ein **PSCredential** -Objekt abruft, z `Get-Credential` . b. einen Befehl.</span><span class="sxs-lookup"><span data-stu-id="c0d16-276">Enter a variable that contains a **PSCredential** object or a command that gets a **PSCredential** object, such as a `Get-Credential` command.</span></span> <span data-ttu-id="c0d16-277">Wenn diese Option nicht festgelegt ist, werden keine Anmeldeinformationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="c0d16-277">If this option is not set, no credentials are specified.</span></span>

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

### <span data-ttu-id="c0d16-278">-Skipcacheck</span><span class="sxs-lookup"><span data-stu-id="c0d16-278">-SkipCACheck</span></span>

<span data-ttu-id="c0d16-279">Gibt an, dass der Client beim Herstellen einer Verbindung über HTTPS nicht überprüft, ob das Serverzertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certification Authority, ca) signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c0d16-279">Specifies that when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="c0d16-280">Verwenden Sie diese Option nur, wenn der Remotecomputer vertrauenswürdig ist, weil er einen anderen Mechanismus verwendet, z. B. wenn er Teil eines physisch sicheren und isolierten Netzwerks ist oder wenn der Remotecomputer in einer WinRM-Konfiguration als vertrauenswürdiger Host aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="c0d16-280">Use this option only when the remote computer is trusted by using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

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

### <span data-ttu-id="c0d16-281">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="c0d16-281">-SkipCNCheck</span></span>

<span data-ttu-id="c0d16-282">Gibt an, dass der allgemeine Name des Zertifikats (Common Name, CN) des Servers nicht mit dem Hostnamen des Servers identisch sein muss.</span><span class="sxs-lookup"><span data-stu-id="c0d16-282">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="c0d16-283">Diese Option wird nur bei Remotevorgängen verwendet, die das HTTPS-Protokoll verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0d16-283">This option is used only in remote operations that use the HTTPS protocol.</span></span>

<span data-ttu-id="c0d16-284">Verwenden Sie diese Option nur für vertrauenswürdige Computer.</span><span class="sxs-lookup"><span data-stu-id="c0d16-284">Use this option only for trusted computers.</span></span>

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

### <span data-ttu-id="c0d16-285">-Skiprevocationcheck</span><span class="sxs-lookup"><span data-stu-id="c0d16-285">-SkipRevocationCheck</span></span>

<span data-ttu-id="c0d16-286">Der Sperrstatus des Serverzertifikats wird nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="c0d16-286">Does not validate the revocation status of the server certificate.</span></span>

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

### <span data-ttu-id="c0d16-287">-UICulture</span><span class="sxs-lookup"><span data-stu-id="c0d16-287">-UICulture</span></span>

<span data-ttu-id="c0d16-288">Gibt die Kultur der Benutzeroberfläche an, die für die Sitzung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0d16-288">Specifies the UI culture to use for the session.</span></span>

<span data-ttu-id="c0d16-289">Gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="c0d16-289">Valid values include:</span></span>

- <span data-ttu-id="c0d16-290">Ein Kultur Name im- `<languagecode2>-<country/regioncode2>` Format, z. b. `ja-JP`</span><span class="sxs-lookup"><span data-stu-id="c0d16-290">A culture name in `<languagecode2>-<country/regioncode2>` format, such as `ja-JP`</span></span>
- <span data-ttu-id="c0d16-291">Eine Variable, die ein **CultureInfo** -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="c0d16-291">A variable that contains a **CultureInfo** object</span></span>
- <span data-ttu-id="c0d16-292">Ein Befehl, der ein **CultureInfo** -Objekt abruft, z. b. `Get-Culture`</span><span class="sxs-lookup"><span data-stu-id="c0d16-292">A command that gets a **CultureInfo** object, such as `Get-Culture`</span></span>

<span data-ttu-id="c0d16-293">Der Standardwert ist `$null` , und die Benutzeroberflächen Kultur, die beim Erstellen der Sitzung im Betriebssystem festgelegt wird, wird in der Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0d16-293">The default value is `$null`, and the UI culture that is set in the operating system when the session is created is used in the session.</span></span>

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

### <span data-ttu-id="c0d16-294">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="c0d16-294">-UseUTF16</span></span>

<span data-ttu-id="c0d16-295">Gibt an, dass dieses Cmdlet die Anforderung im UTF16-Format anstatt im UTF8-Format codiert.</span><span class="sxs-lookup"><span data-stu-id="c0d16-295">Indicates that this cmdlet encodes the request in UTF16 format instead of UTF8 format.</span></span>

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

### <span data-ttu-id="c0d16-296">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c0d16-296">CommonParameters</span></span>

<span data-ttu-id="c0d16-297">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c0d16-297">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c0d16-298">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c0d16-298">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c0d16-299">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c0d16-299">INPUTS</span></span>

### <span data-ttu-id="c0d16-300">Keine</span><span class="sxs-lookup"><span data-stu-id="c0d16-300">None</span></span>

<span data-ttu-id="c0d16-301">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="c0d16-301">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c0d16-302">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c0d16-302">OUTPUTS</span></span>

### <span data-ttu-id="c0d16-303">System. Management. Automation. Remoting. pssessionoption</span><span class="sxs-lookup"><span data-stu-id="c0d16-303">System.Management.Automation.Remoting.PSSessionOption</span></span>

## <span data-ttu-id="c0d16-304">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c0d16-304">NOTES</span></span>

<span data-ttu-id="c0d16-305">Wenn der **sessionoption** -Parameter in einem Befehl zum Erstellen einer **PSSession** nicht verwendet wird, werden die Sitzungs Optionen durch die Eigenschaftswerte der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c0d16-305">If the **SessionOption** parameter is not used in a command to create a **PSSession**, the session options are determined by the property values of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="c0d16-306">Weitere Informationen zur- `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="c0d16-306">For more information about the `$PSSessionOption` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="c0d16-307">Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="c0d16-307">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="c0d16-308">Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c0d16-308">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="c0d16-309">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c0d16-309">RELATED LINKS</span></span>

[<span data-ttu-id="c0d16-310">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="c0d16-310">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="c0d16-311">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="c0d16-311">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="c0d16-312">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="c0d16-312">New-PSSession</span></span>](New-PSSession.md)
