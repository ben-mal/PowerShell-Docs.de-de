---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 26c4f8c8dcc1fbd56e29f55a6a8c2e6aa37a2842
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "93225204"
---
# <span data-ttu-id="05b5f-103">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="05b5f-103">Get-Credential</span></span>

## <span data-ttu-id="05b5f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="05b5f-104">SYNOPSIS</span></span>
<span data-ttu-id="05b5f-105">Ruft ein Anmeldeinformationsobjekt basierend auf einem Benutzernamen und Kennwort ab.</span><span class="sxs-lookup"><span data-stu-id="05b5f-105">Gets a credential object based on a user name and password.</span></span>

## <span data-ttu-id="05b5f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="05b5f-106">SYNTAX</span></span>

### <span data-ttu-id="05b5f-107">"Kredentialset" (Standard)</span><span class="sxs-lookup"><span data-stu-id="05b5f-107">CredentialSet (Default)</span></span>

```
Get-Credential [-Credential] <PSCredential> [<CommonParameters>]
```

### <span data-ttu-id="05b5f-108">Messageset</span><span class="sxs-lookup"><span data-stu-id="05b5f-108">MessageSet</span></span>

```
Get-Credential -Message <String> [[-UserName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="05b5f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="05b5f-109">DESCRIPTION</span></span>

<span data-ttu-id="05b5f-110">Mit dem `Get-Credential` -Cmdlet wird ein Anmelde Informationsobjekt für einen angegebenen Benutzernamen und ein bestimmtes Kennwort erstellt.</span><span class="sxs-lookup"><span data-stu-id="05b5f-110">The `Get-Credential` cmdlet creates a credential object for a specified user name and password.</span></span> <span data-ttu-id="05b5f-111">Sie können das Anmeldeinformationsobjekt für Sicherheitsvorgänge verwenden.</span><span class="sxs-lookup"><span data-stu-id="05b5f-111">You can use the credential object in security operations.</span></span>

<span data-ttu-id="05b5f-112">Ab PowerShell 3,0 können Sie den **Message** -Parameter verwenden, um eine angepasste Meldung im Dialogfeld anzugeben, die den Benutzer zur Eingabe des Namens und Kennworts auffordert.</span><span class="sxs-lookup"><span data-stu-id="05b5f-112">Beginning in PowerShell 3.0, you can use the **Message** parameter to specify a customized message on the dialog box that prompts the user for their name and password.</span></span>

<span data-ttu-id="05b5f-113">Das `Get-Credential` Cmdlet fordert den Benutzer auf, ein Kennwort oder einen Benutzernamen und ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="05b5f-113">The `Get-Credential` cmdlet prompts the user for a password or a user name and password.</span></span> <span data-ttu-id="05b5f-114">Standardmäßig wird dem Benutzer ein Authentifizierungsdialogfeld mit der Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05b5f-114">By default, an authentication dialog box appears to prompt the user.</span></span> <span data-ttu-id="05b5f-115">In einigen Host Programmen, z. b. der PowerShell-Konsole, können Sie den Benutzer jedoch in der Befehlszeile auffordern, indem Sie einen Registrierungs Eintrag ändern.</span><span class="sxs-lookup"><span data-stu-id="05b5f-115">However, in some host programs, such as the PowerShell console, you can prompt the user at the command line by changing a registry entry.</span></span> <span data-ttu-id="05b5f-116">Weitere Informationen zu diesem Registrierungseintrag finden Sie in den Hinweisen und Beispielen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-116">For more information about this registry entry, see the notes and examples.</span></span>

## <span data-ttu-id="05b5f-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="05b5f-117">EXAMPLES</span></span>

### <span data-ttu-id="05b5f-118">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="05b5f-118">Example 1</span></span>

```powershell
$c = Get-Credential
```

<span data-ttu-id="05b5f-119">Dieser Befehl ruft ein Anmelde Informationsobjekt ab und speichert es in der `$c` Variablen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-119">This command gets a credential object and saves it in the `$c` variable.</span></span>

<span data-ttu-id="05b5f-120">Wenn Sie den Befehl eingeben, wird ein Dialogfeld angezeigt, in dem die Eingabe eines Benutzernamens und eines Kennworts angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="05b5f-120">When you enter the command, a dialog box appears requesting a user name and password.</span></span> <span data-ttu-id="05b5f-121">Wenn Sie die angeforderten Informationen eingeben, erstellt das Cmdlet ein **PSCredential** -Objekt, das die Anmelde Informationen des Benutzers darstellt, und speichert es in der `$c` Variablen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-121">When you enter the requested information, the cmdlet creates a **PSCredential** object representing the credentials of the user and saves it in the `$c` variable.</span></span>

<span data-ttu-id="05b5f-122">Sie können das Objekt als Eingabe für Cmdlets verwenden, die eine Benutzerauthentifizierung anfordern, z. b. solche mit einem **Credential** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="05b5f-122">You can use the object as input to cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span> <span data-ttu-id="05b5f-123">Einige Anbieter, die mit PowerShell installiert werden, unterstützen jedoch nicht den **Credential** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="05b5f-123">However, some providers that are installed with PowerShell do not support the **Credential** parameter.</span></span>

### <span data-ttu-id="05b5f-124">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="05b5f-124">Example 2</span></span>

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

<span data-ttu-id="05b5f-125">Diese Befehle verwenden ein Anmelde Informationen-Objekt, das vom `Get-Credential` Cmdlet zurückgegeben wird, um einen Benutzer auf einem Remote Computer zu authentifizieren, sodass der Computer mit Windows-Verwaltungsinstrumentation (WMI) verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="05b5f-125">These commands use a credential object that the `Get-Credential` cmdlet returns to authenticate a user on a remote computer so they can use Windows Management Instrumentation (WMI) to manage the computer.</span></span>

<span data-ttu-id="05b5f-126">Der erste Befehl ruft ein Anmelde Informationsobjekt ab und speichert es in der `$c` Variablen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-126">The first command gets a credential object and saves it in the `$c` variable.</span></span> <span data-ttu-id="05b5f-127">Der zweite Befehl verwendet das Anmelde Informationen-Objekt in einem `Get-CimInstance` Befehl.</span><span class="sxs-lookup"><span data-stu-id="05b5f-127">The second command uses the credential object in a `Get-CimInstance` command.</span></span> <span data-ttu-id="05b5f-128">Dieser Befehl ruft Informationen zu den Festplattenlaufwerken auf dem Computer „Server01“ ab.</span><span class="sxs-lookup"><span data-stu-id="05b5f-128">This command gets information about the disk drives on the Server01 computer.</span></span>

### <span data-ttu-id="05b5f-129">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="05b5f-129">Example 3</span></span>

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

<span data-ttu-id="05b5f-130">Dieser Befehl zeigt, wie Sie einen `Get-Credential` Befehl in einen  `Get-CimInstance` Befehl einschließen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-130">This command shows how to include a `Get-Credential` command in a  `Get-CimInstance` command.</span></span>

<span data-ttu-id="05b5f-131">Dieser Befehl verwendet das `Get-CimInstance` Cmdlet, um Informationen über das BIOS auf dem Server01-Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="05b5f-131">This command uses the `Get-CimInstance` cmdlet to get information about the BIOS on the Server01 computer.</span></span> <span data-ttu-id="05b5f-132">Er verwendet den **Credential** -Parameter, um den Benutzer, Domain01\User01 und einen `Get-Credential` Befehl als Wert des **Credential** -Parameters zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="05b5f-132">It uses the **Credential** parameter to authenticate the user, Domain01\User01, and a `Get-Credential` command as the value of the **Credential** parameter.</span></span>

### <span data-ttu-id="05b5f-133">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="05b5f-133">Example 4</span></span>

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

<span data-ttu-id="05b5f-134">In diesem Beispiel werden die Anmeldeinformationen erstellt, die einen Benutzernamen ohne Domänennamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="05b5f-134">This example creates a credential that includes a user name without a domain name.</span></span>

<span data-ttu-id="05b5f-135">Mit dem ersten Befehl werden Anmelde Informationen mit dem Benutzernamen USER01 abgerufen und in der `$c` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="05b5f-135">The first command gets a credential with the user name User01 and stores it in the `$c` variable.</span></span>
<span data-ttu-id="05b5f-136">Der zweite Befehl zeigt den Wert der **Username** -Eigenschaft des resultierenden Credential-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="05b5f-136">The second command displays the value of the **Username** property of the resulting credential object.</span></span>

### <span data-ttu-id="05b5f-137">Beispiel 5</span><span class="sxs-lookup"><span data-stu-id="05b5f-137">Example 5</span></span>

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

<span data-ttu-id="05b5f-138">Dieser Befehl verwendet die **PromptForCredential** -Methode, um den Benutzer zu Eingabe des Benutzernamens und Kennworts aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="05b5f-138">This command uses the **PromptForCredential** method to prompt the user for their user name and password.</span></span> <span data-ttu-id="05b5f-139">Der Befehl speichert die resultierenden Anmelde Informationen in der `$Credential` Variablen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-139">The command saves the resulting credentials in the `$Credential` variable.</span></span>

<span data-ttu-id="05b5f-140">Die **promptforcredential** -Methode ist eine Alternative zur Verwendung des- `Get-Credential` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="05b5f-140">The **PromptForCredential** method is an alternative to using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="05b5f-141">Bei Verwendung von **PromptForCredential** geben Sie die Beschriftung, die Meldungen und den Benutzernamen an, die im Meldungsfeld angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="05b5f-141">When you use **PromptForCredential** , you can specify the caption, messages, and user name that appear in the message box.</span></span>

<span data-ttu-id="05b5f-142">Weitere Informationen finden Sie in der Dokumentation zu [promptforcredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) im SDK.</span><span class="sxs-lookup"><span data-stu-id="05b5f-142">For more information, see the [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) documentation in the SDK.</span></span>

### <span data-ttu-id="05b5f-143">Beispiel 6</span><span class="sxs-lookup"><span data-stu-id="05b5f-143">Example 6</span></span>

```powershell
Set-ItemProperty "HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds" -Name ConsolePrompting -Value $true
```

<span data-ttu-id="05b5f-144">Dieses Beispiel zeigt, wie Sie die Registrierung ändern, damit der Benutzer in der Befehlszeile anstelle eines Dialogfelds zur Eingabe aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="05b5f-144">This example shows how to modify the registry so that the user is prompted at the command line, instead of by using a dialog box.</span></span>

<span data-ttu-id="05b5f-145">Der Befehl erstellt den **ConsolePrompting** -Registrierungseintrag und legt den Wert auf „true“ fest.</span><span class="sxs-lookup"><span data-stu-id="05b5f-145">The command creates the **ConsolePrompting** registry entry and sets its value to True.</span></span> <span data-ttu-id="05b5f-146">Starten Sie PowerShell mit der Option "als Administrator ausführen", um diesen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-146">To run this command, start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="05b5f-147">Wenn Sie ein Dialogfeld für die Eingabeaufforderung verwenden möchten, legen Sie den Wert von consoleforderungs auf false ($false) fest, oder verwenden `Remove-ItemProperty` Sie das Cmdlet, um ihn zu löschen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-147">To use a dialog box for prompting, set the value of the ConsolePrompting to false ($false) or use the `Remove-ItemProperty` cmdlet to delete it.</span></span>

<span data-ttu-id="05b5f-148">Der consoleforderungs-Registrierungs Eintrag funktioniert in einigen Host Programmen, z. b. in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="05b5f-148">The ConsolePrompting registry entry works in some host programs, such as the PowerShell console.</span></span> <span data-ttu-id="05b5f-149">Er funktioniert möglicherweise nicht in allen Hostprogrammen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-149">It might not work in all host programs.</span></span>

### <span data-ttu-id="05b5f-150">Beispiel 7</span><span class="sxs-lookup"><span data-stu-id="05b5f-150">Example 7</span></span>

<span data-ttu-id="05b5f-151">Dieses Beispiel zeigt, wie Sie ein Anmelde Informationsobjekt erstellen, das mit dem Objekt identisch ist, das `Get-Credential` zurückgibt, ohne den Benutzer aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="05b5f-151">This example shows how to create a credential object that is identical to the object that `Get-Credential` returns without prompting the user.</span></span> <span data-ttu-id="05b5f-152">Für diese Methode ist nur ein Nur-Text-Kennwort erforderlich, was in manchen Unternehmen gegen die Sicherheitsstandards verstoßen könnte.</span><span class="sxs-lookup"><span data-stu-id="05b5f-152">This method requires a plain text password, which might violate the security standards in some enterprises.</span></span>

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

<span data-ttu-id="05b5f-153">Der erste Befehl speichert den Namen des Benutzerkontos im- `$User` Parameter.</span><span class="sxs-lookup"><span data-stu-id="05b5f-153">The first command saves the user account name in the `$User` parameter.</span></span> <span data-ttu-id="05b5f-154">Der Wert muss das Format „Domäne\Benutzer“ oder „Computername\Benutzer“ haben.</span><span class="sxs-lookup"><span data-stu-id="05b5f-154">The value must have the "Domain\User" or "ComputerName\User" format.</span></span>

<span data-ttu-id="05b5f-155">Der zweite Befehl verwendet das `ConvertTo-SecureString` Cmdlet, um eine sichere Zeichenfolge aus einem nur-Text-Kennwort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-155">The second command uses the `ConvertTo-SecureString` cmdlet to create a secure string from a plain text password.</span></span> <span data-ttu-id="05b5f-156">Der Befehl verwendet den **AsPlainText** -Parameter, um anzugeben, dass die Zeichenfolge Nur-Text ist, und den **Force** -Parameter, um zu bestätigen, dass Sie die Risiken beim Einsatz von Nur-Text verstanden haben.</span><span class="sxs-lookup"><span data-stu-id="05b5f-156">The command uses the **AsPlainText** parameter to indicate that the string is plain text and the **Force** parameter to confirm that you understand the risks of using plain text.</span></span>

<span data-ttu-id="05b5f-157">Der dritte Befehl verwendet das `New-Object` Cmdlet, um ein **PSCredential** -Objekt aus den Werten in den `$User` Variablen und zu erstellen `$PWord` .</span><span class="sxs-lookup"><span data-stu-id="05b5f-157">The third command uses the `New-Object` cmdlet to create a **PSCredential** object from the values in the `$User` and `$PWord` variables.</span></span>

### <span data-ttu-id="05b5f-158">Beispiel 8</span><span class="sxs-lookup"><span data-stu-id="05b5f-158">Example 8</span></span>

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

<span data-ttu-id="05b5f-159">Dieser Befehl verwendet die Parameter " **Message** " und " **username** " des `Get-Credential` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="05b5f-159">This command uses the **Message** and **UserName** parameters of the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="05b5f-160">Dieses Befehlsformat wurde für gemeinsam genutzte Skripts und Funktionen entwickelt.</span><span class="sxs-lookup"><span data-stu-id="05b5f-160">This command format is designed for shared scripts and functions.</span></span> <span data-ttu-id="05b5f-161">In diesem Fall erfährt der Benutzer in der Meldung, warum Anmeldeinformationen erforderlich sind, und bietet ihm die Sicherheit, dass die Anforderung legitim ist.</span><span class="sxs-lookup"><span data-stu-id="05b5f-161">In this case, the message tells the user why credentials are needed and gives them confidence that the request is legitimate.</span></span>

### <span data-ttu-id="05b5f-162">Beispiel 9</span><span class="sxs-lookup"><span data-stu-id="05b5f-162">Example 9</span></span>

```powershell
Invoke-Command -ComputerName Server01 {Get-Credential Domain01\User02}
```

```Output
PowerShell Credential Request : PowerShell Credential Request
Warning: This credential is being requested by a script or application on the SERVER01 remote computer. Enter your credentials only if you
 trust the remote computer and the application or script requesting it.

Enter your credentials.
Password for user Domain01\User02: ***************

PSComputerName     : Server01
RunspaceId         : 422bdf52-9886-4ada-ab2f-130497c6777f
PSShowComputerName : True
UserName           : Domain01\User01
Password           : System.Security.SecureString
```

<span data-ttu-id="05b5f-163">Dieser Befehl ruft die Anmeldeinformationen vom Remotecomputer „Server01“ ab.</span><span class="sxs-lookup"><span data-stu-id="05b5f-163">This command gets a credential from the Server01 remote computer.</span></span> <span data-ttu-id="05b5f-164">Der Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Get-Credential` Befehls auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="05b5f-164">The command uses the `Invoke-Command` cmdlet to run a `Get-Credential` command on the remote computer.</span></span> <span data-ttu-id="05b5f-165">Die Ausgabe zeigt die Remote Sicherheitsnachricht, die `Get-Credential` in der Authentifizierungs Aufforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="05b5f-165">The output shows the remote security message that `Get-Credential` includes in the authentication prompt.</span></span>

## <span data-ttu-id="05b5f-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="05b5f-166">PARAMETERS</span></span>

### <span data-ttu-id="05b5f-167">-Credential</span><span class="sxs-lookup"><span data-stu-id="05b5f-167">-Credential</span></span>

<span data-ttu-id="05b5f-168">Gibt einen Benutzernamen für die Anmelde Informationen an, z. b. **USER01** oder **Domain01\User01**.</span><span class="sxs-lookup"><span data-stu-id="05b5f-168">Specifies a user name for the credential, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="05b5f-169">Der Parameter Name, `-Credential` , ist optional.</span><span class="sxs-lookup"><span data-stu-id="05b5f-169">The parameter name, `-Credential`, is optional.</span></span>

<span data-ttu-id="05b5f-170">Wenn Sie den Befehl übermitteln und einen Benutzernamen angeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="05b5f-170">When you submit the command and specify a user name, you're prompted for a password.</span></span> <span data-ttu-id="05b5f-171">Wenn Sie diesen Parameter weglassen, werden Sie aufgefordert, einen Benutzernamen und ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="05b5f-171">If you omit this parameter, you're prompted for a user name and a password.</span></span>

<span data-ttu-id="05b5f-172">Wenn Sie in PowerShell 3,0 einen Benutzernamen ohne Domäne eingeben, wird von kein umgekehrter `Get-Credential` Schrägstrich mehr vor dem Namen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="05b5f-172">Starting in PowerShell 3.0, if you enter a user name without a domain, `Get-Credential` no longer inserts a backslash before the name.</span></span>

<span data-ttu-id="05b5f-173">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="05b5f-173">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="05b5f-174">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="05b5f-174">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="05b5f-175">-Meldung</span><span class="sxs-lookup"><span data-stu-id="05b5f-175">-Message</span></span>

<span data-ttu-id="05b5f-176">Gibt eine Meldung an, die in der Authentifizierungsaufforderung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="05b5f-176">Specifies a message that appears in the authentication prompt.</span></span> <span data-ttu-id="05b5f-177">Dieser Parameter dient zur Verwendung in einer Funktion oder in einem Skript.</span><span class="sxs-lookup"><span data-stu-id="05b5f-177">This parameter is designed for use in a function or script.</span></span> <span data-ttu-id="05b5f-178">Sie können die Meldung verwenden, um dem Benutzer zu erklären, warum Sie Anmeldeinformationen anfordern und wie sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05b5f-178">You can use the message to explain to the user why you are requesting credentials and how they will be used.</span></span>

<span data-ttu-id="05b5f-179">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="05b5f-179">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="05b5f-180">-UserName</span><span class="sxs-lookup"><span data-stu-id="05b5f-180">-UserName</span></span>

<span data-ttu-id="05b5f-181">Gibt einen Benutzernamen an.</span><span class="sxs-lookup"><span data-stu-id="05b5f-181">Specifies a user name.</span></span> <span data-ttu-id="05b5f-182">Die Authentifizierungsaufforderung fordert die Eingabe eines Kennworts für den Benutzernamen an.</span><span class="sxs-lookup"><span data-stu-id="05b5f-182">The authentication prompt requests a password for the user name.</span></span> <span data-ttu-id="05b5f-183">Standardmäßig ist der Benutzername leer, und die Authentifizierungsaufforderung fordert sowohl einen Benutzernamen als auch ein Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="05b5f-183">By default, the user name is blank and the authentication prompt requests both a user name and password.</span></span>

<span data-ttu-id="05b5f-184">Wenn die Authentifizierungsaufforderung in einem Dialogfeld angezeigt wird, kann der Benutzer den angegebenen Benutzernamen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="05b5f-184">When the authentication prompt appears in a dialog box, the user can edit the specified user name.</span></span>
<span data-ttu-id="05b5f-185">Der Benutzer kann den Benutzernamen jedoch nicht ändern, wenn die Eingabeaufforderung in der Befehlszeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="05b5f-185">However, the user cannot change the user name when the prompt appears at the command line.</span></span> <span data-ttu-id="05b5f-186">Wenn Sie diesen Parameter in einer gemeinsam genutzten Funktion oder einem gemeinsam genutzten Skript verwenden, sollten Sie alle möglichen Darstellungen in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-186">When using this parameter in a shared function or script, consider all possible presentations.</span></span>

<span data-ttu-id="05b5f-187">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="05b5f-187">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: 1
Default value: None (blank)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="05b5f-188">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="05b5f-188">CommonParameters</span></span>

<span data-ttu-id="05b5f-189">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="05b5f-189">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="05b5f-190">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="05b5f-190">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="05b5f-191">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="05b5f-191">INPUTS</span></span>

### <span data-ttu-id="05b5f-192">Keine</span><span class="sxs-lookup"><span data-stu-id="05b5f-192">None</span></span>

<span data-ttu-id="05b5f-193">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="05b5f-193">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="05b5f-194">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="05b5f-194">OUTPUTS</span></span>

### <span data-ttu-id="05b5f-195">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="05b5f-195">System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="05b5f-196">`Get-Credential` Gibt ein Anmelde Informationen-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="05b5f-196">`Get-Credential` returns a credential object.</span></span>

## <span data-ttu-id="05b5f-197">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="05b5f-197">NOTES</span></span>

<span data-ttu-id="05b5f-198">Sie können das **PSCredential** -Objekt verwenden, das `Get-Credential` in Cmdlets erstellt, die eine Benutzerauthentifizierung anfordern, z. b. solche mit einem **Credential** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="05b5f-198">You can use the **PSCredential** object that `Get-Credential` creates in cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span>

<span data-ttu-id="05b5f-199">Standardmäßig wird die Authentifizierungseingabeaufforderung in einem Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05b5f-199">By default, the authentication prompt appears in a dialog box.</span></span> <span data-ttu-id="05b5f-200">Fügen Sie zum Anzeigen der Authentifizierungs Aufforderung in der Befehlszeile den **consoleprompt** -Registrierungs Eintrag () hinzu, `HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting` und legen Sie den Wert auf **true** fest.</span><span class="sxs-lookup"><span data-stu-id="05b5f-200">To display the authentication prompt at the command line, add the **ConsolePrompting** registry entry (`HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting`) and set its value to **True**.</span></span>
<span data-ttu-id="05b5f-201">Wenn der **ConsolePrompting** -Registrierungseintrag nicht vorhanden ist oder wenn der Wert „False“ ist, wird die Authentifizierungsaufforderung in einem Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05b5f-201">If the **ConsolePrompting** registry entry does not exist or if its value is False, the authentication prompt appears in a dialog box.</span></span> <span data-ttu-id="05b5f-202">Anweisungen finden Sie in den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-202">For instructions, see the examples.</span></span>

<span data-ttu-id="05b5f-203">Der **consoleforderungs** -Registrierungs Eintrag funktioniert in der PowerShell-Konsole, funktioniert aber nicht in allen Host Programmen.</span><span class="sxs-lookup"><span data-stu-id="05b5f-203">The **ConsolePrompting** registry entry works in the PowerShell console, but it does not work in all host programs.</span></span>

<span data-ttu-id="05b5f-204">Dies hat beispielsweise keine Auswirkung auf die PowerShell Integrated Scripting Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="05b5f-204">For example, it has no effect in the PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="05b5f-205">Informationen zu den Auswirkungen des **ConsolePrompting** -Registrierungseintrags finden Sie in den Hilfethemen für das Hostprogramm.</span><span class="sxs-lookup"><span data-stu-id="05b5f-205">For information about the effect of the **ConsolePrompting** registry entry, see the help topics for the host program.</span></span>

<span data-ttu-id="05b5f-206">Der **Credential** -Parameter wird nicht von allen Anbietern unterstützt, die mit PowerShell installiert werden.</span><span class="sxs-lookup"><span data-stu-id="05b5f-206">The **Credential** parameter is not supported by all providers that are installed with PowerShell.</span></span>
<span data-ttu-id="05b5f-207">Ab PowerShell 3,0 wird es für SELECT-Cmdlets unterstützt, wie z `Get-Content` . b. die-und- `New-PSDrive` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="05b5f-207">Beginning in PowerShell 3.0, it is supported on select cmdlets, such as the `Get-Content` and `New-PSDrive` cmdlets.</span></span>

## <span data-ttu-id="05b5f-208">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="05b5f-208">RELATED LINKS</span></span>

[<span data-ttu-id="05b5f-209">PromptForCredential</span><span class="sxs-lookup"><span data-stu-id="05b5f-209">PromptForCredential</span></span>](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
