---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 2ff87c8d4b714be3b5be3bfe8f384b4c89c25272
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "93225236"
---
# <span data-ttu-id="679a8-103">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="679a8-103">Get-Credential</span></span>

## <span data-ttu-id="679a8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="679a8-104">SYNOPSIS</span></span>
<span data-ttu-id="679a8-105">Ruft ein Anmeldeinformationsobjekt basierend auf einem Benutzernamen und Kennwort ab.</span><span class="sxs-lookup"><span data-stu-id="679a8-105">Gets a credential object based on a user name and password.</span></span>

## <span data-ttu-id="679a8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="679a8-106">SYNTAX</span></span>

### <span data-ttu-id="679a8-107">"Kredentialset" (Standard)</span><span class="sxs-lookup"><span data-stu-id="679a8-107">CredentialSet (Default)</span></span>

```
Get-Credential [[-Credential] <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="679a8-108">Messageset</span><span class="sxs-lookup"><span data-stu-id="679a8-108">MessageSet</span></span>

```
Get-Credential [-Message <String>] [[-UserName] <String>] [-Title <String>] [<CommonParameters>]
```

## <span data-ttu-id="679a8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="679a8-109">DESCRIPTION</span></span>

<span data-ttu-id="679a8-110">Mit dem `Get-Credential` -Cmdlet wird ein Anmelde Informationsobjekt für einen angegebenen Benutzernamen und ein bestimmtes Kennwort erstellt.</span><span class="sxs-lookup"><span data-stu-id="679a8-110">The `Get-Credential` cmdlet creates a credential object for a specified user name and password.</span></span> <span data-ttu-id="679a8-111">Sie können das Anmeldeinformationsobjekt für Sicherheitsvorgänge verwenden.</span><span class="sxs-lookup"><span data-stu-id="679a8-111">You can use the credential object in security operations.</span></span>

<span data-ttu-id="679a8-112">Das `Get-Credential` Cmdlet fordert den Benutzer auf, ein Kennwort oder einen Benutzernamen und ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="679a8-112">The `Get-Credential` cmdlet prompts the user for a password or a user name and password.</span></span> <span data-ttu-id="679a8-113">Sie können den **Message** -Parameter verwenden, um in der Eingabeaufforderung eine angepasste Meldung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="679a8-113">You can use the **Message** parameter to specify a customized message in the command line prompt.</span></span>

## <span data-ttu-id="679a8-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="679a8-114">EXAMPLES</span></span>

### <span data-ttu-id="679a8-115">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="679a8-115">Example 1</span></span>

```powershell
$c = Get-Credential
```

<span data-ttu-id="679a8-116">Dieser Befehl ruft ein Anmelde Informationsobjekt ab und speichert es in der `$c` Variablen.</span><span class="sxs-lookup"><span data-stu-id="679a8-116">This command gets a credential object and saves it in the `$c` variable.</span></span>

<span data-ttu-id="679a8-117">Wenn Sie den Befehl eingeben, werden Sie aufgefordert, einen Benutzernamen und ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="679a8-117">When you enter the command, you are prompted for a user name and password.</span></span> <span data-ttu-id="679a8-118">Wenn Sie die angeforderten Informationen eingeben, erstellt das Cmdlet ein **PSCredential** -Objekt, das die Anmelde Informationen des Benutzers darstellt, und speichert es in der `$c` Variablen.</span><span class="sxs-lookup"><span data-stu-id="679a8-118">When you enter the requested information, the cmdlet creates a **PSCredential** object representing the credentials of the user and saves it in the `$c` variable.</span></span>

<span data-ttu-id="679a8-119">Sie können das Objekt als Eingabe für Cmdlets verwenden, die eine Benutzerauthentifizierung anfordern, z. b. solche mit einem **Credential** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="679a8-119">You can use the object as input to cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span> <span data-ttu-id="679a8-120">Einige Anbieter, die mit PowerShell installiert werden, unterstützen jedoch nicht den **Credential** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="679a8-120">However, some providers that are installed with PowerShell do not support the **Credential** parameter.</span></span>

### <span data-ttu-id="679a8-121">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="679a8-121">Example 2</span></span>

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

<span data-ttu-id="679a8-122">Diese Befehle verwenden ein Anmelde Informationen-Objekt, das vom `Get-Credential` Cmdlet zurückgegeben wird, um einen Benutzer auf einem Remote Computer zu authentifizieren, sodass der Computer mit Windows-Verwaltungsinstrumentation (WMI) verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="679a8-122">These commands use a credential object that the `Get-Credential` cmdlet returns to authenticate a user on a remote computer so they can use Windows Management Instrumentation (WMI) to manage the computer.</span></span>

<span data-ttu-id="679a8-123">Der erste Befehl ruft ein Anmelde Informationsobjekt ab und speichert es in der `$c` Variablen.</span><span class="sxs-lookup"><span data-stu-id="679a8-123">The first command gets a credential object and saves it in the `$c` variable.</span></span> <span data-ttu-id="679a8-124">Der zweite Befehl verwendet das Anmelde Informationen-Objekt in einem `Get-CimInstance` Befehl.</span><span class="sxs-lookup"><span data-stu-id="679a8-124">The second command uses the credential object in a `Get-CimInstance` command.</span></span> <span data-ttu-id="679a8-125">Dieser Befehl ruft Informationen zu den Festplattenlaufwerken auf dem Computer „Server01“ ab.</span><span class="sxs-lookup"><span data-stu-id="679a8-125">This command gets information about the disk drives on the Server01 computer.</span></span>

### <span data-ttu-id="679a8-126">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="679a8-126">Example 3</span></span>

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

<span data-ttu-id="679a8-127">Dieser Befehl zeigt, wie Sie einen `Get-Credential` Befehl in einen  `Get-CimInstance` Befehl einschließen.</span><span class="sxs-lookup"><span data-stu-id="679a8-127">This command shows how to include a `Get-Credential` command in a  `Get-CimInstance` command.</span></span>

<span data-ttu-id="679a8-128">Dieser Befehl verwendet das `Get-CimInstance` Cmdlet, um Informationen über das BIOS auf dem Server01-Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="679a8-128">This command uses the `Get-CimInstance` cmdlet to get information about the BIOS on the Server01 computer.</span></span> <span data-ttu-id="679a8-129">Er verwendet den **Credential** -Parameter, um den Benutzer, Domain01\User01 und einen `Get-Credential` Befehl als Wert des **Credential** -Parameters zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="679a8-129">It uses the **Credential** parameter to authenticate the user, Domain01\User01, and a `Get-Credential` command as the value of the **Credential** parameter.</span></span>

### <span data-ttu-id="679a8-130">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="679a8-130">Example 4</span></span>

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

<span data-ttu-id="679a8-131">In diesem Beispiel werden die Anmeldeinformationen erstellt, die einen Benutzernamen ohne Domänennamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="679a8-131">This example creates a credential that includes a user name without a domain name.</span></span>

<span data-ttu-id="679a8-132">Mit dem ersten Befehl werden Anmelde Informationen mit dem Benutzernamen USER01 abgerufen und in der `$c` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="679a8-132">The first command gets a credential with the user name User01 and stores it in the `$c` variable.</span></span>
<span data-ttu-id="679a8-133">Der zweite Befehl zeigt den Wert der **Username** -Eigenschaft des resultierenden Credential-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="679a8-133">The second command displays the value of the **Username** property of the resulting credential object.</span></span>

### <span data-ttu-id="679a8-134">Beispiel 5</span><span class="sxs-lookup"><span data-stu-id="679a8-134">Example 5</span></span>

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

<span data-ttu-id="679a8-135">Dieser Befehl verwendet die **PromptForCredential** -Methode, um den Benutzer zu Eingabe des Benutzernamens und Kennworts aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="679a8-135">This command uses the **PromptForCredential** method to prompt the user for their user name and password.</span></span> <span data-ttu-id="679a8-136">Der Befehl speichert die resultierenden Anmelde Informationen in der `$Credential` Variablen.</span><span class="sxs-lookup"><span data-stu-id="679a8-136">The command saves the resulting credentials in the `$Credential` variable.</span></span>

<span data-ttu-id="679a8-137">Die **promptforcredential** -Methode ist eine Alternative zur Verwendung des- `Get-Credential` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="679a8-137">The **PromptForCredential** method is an alternative to using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="679a8-138">Wenn Sie **promptforcredential** verwenden, können Sie die Beschriftung, die Meldungen und den Benutzernamen angeben, die in der Eingabeaufforderung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="679a8-138">When you use **PromptForCredential** , you can specify the caption, messages, and user name that appear in the prompt.</span></span>

<span data-ttu-id="679a8-139">Weitere Informationen finden Sie in der Dokumentation zu [promptforcredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) im SDK.</span><span class="sxs-lookup"><span data-stu-id="679a8-139">For more information, see the [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) documentation in the SDK.</span></span>

### <span data-ttu-id="679a8-140">Beispiel 6</span><span class="sxs-lookup"><span data-stu-id="679a8-140">Example 6</span></span>

<span data-ttu-id="679a8-141">Dieses Beispiel zeigt, wie Sie ein Anmelde Informationsobjekt erstellen, das mit dem Objekt identisch ist, das `Get-Credential` zurückgibt, ohne den Benutzer aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="679a8-141">This example shows how to create a credential object that is identical to the object that `Get-Credential` returns without prompting the user.</span></span> <span data-ttu-id="679a8-142">Für diese Methode ist nur ein Nur-Text-Kennwort erforderlich, was in manchen Unternehmen gegen die Sicherheitsstandards verstoßen könnte.</span><span class="sxs-lookup"><span data-stu-id="679a8-142">This method requires a plain text password, which might violate the security standards in some enterprises.</span></span>

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

<span data-ttu-id="679a8-143">Der erste Befehl speichert den Namen des Benutzerkontos im- `$User` Parameter.</span><span class="sxs-lookup"><span data-stu-id="679a8-143">The first command saves the user account name in the `$User` parameter.</span></span> <span data-ttu-id="679a8-144">Der Wert muss das Format „Domäne\Benutzer“ oder „Computername\Benutzer“ haben.</span><span class="sxs-lookup"><span data-stu-id="679a8-144">The value must have the "Domain\User" or "ComputerName\User" format.</span></span>

<span data-ttu-id="679a8-145">Der zweite Befehl verwendet das `ConvertTo-SecureString` Cmdlet, um eine sichere Zeichenfolge aus einem nur-Text-Kennwort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="679a8-145">The second command uses the `ConvertTo-SecureString` cmdlet to create a secure string from a plain text password.</span></span> <span data-ttu-id="679a8-146">Der Befehl verwendet den **AsPlainText** -Parameter, um anzugeben, dass die Zeichenfolge Nur-Text ist, und den **Force** -Parameter, um zu bestätigen, dass Sie die Risiken beim Einsatz von Nur-Text verstanden haben.</span><span class="sxs-lookup"><span data-stu-id="679a8-146">The command uses the **AsPlainText** parameter to indicate that the string is plain text and the **Force** parameter to confirm that you understand the risks of using plain text.</span></span>

<span data-ttu-id="679a8-147">Der dritte Befehl verwendet das `New-Object` Cmdlet, um ein **PSCredential** -Objekt aus den Werten in den `$User` Variablen und zu erstellen `$PWord` .</span><span class="sxs-lookup"><span data-stu-id="679a8-147">The third command uses the `New-Object` cmdlet to create a **PSCredential** object from the values in the `$User` and `$PWord` variables.</span></span>

### <span data-ttu-id="679a8-148">Beispiel 7</span><span class="sxs-lookup"><span data-stu-id="679a8-148">Example 7</span></span>

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

<span data-ttu-id="679a8-149">Dieser Befehl verwendet die Parameter " **Message** " und " **username** " des `Get-Credential` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="679a8-149">This command uses the **Message** and **UserName** parameters of the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="679a8-150">Dieses Befehlsformat wurde für gemeinsam genutzte Skripts und Funktionen entwickelt.</span><span class="sxs-lookup"><span data-stu-id="679a8-150">This command format is designed for shared scripts and functions.</span></span> <span data-ttu-id="679a8-151">In diesem Fall erfährt der Benutzer in der Meldung, warum Anmeldeinformationen erforderlich sind, und bietet ihm die Sicherheit, dass die Anforderung legitim ist.</span><span class="sxs-lookup"><span data-stu-id="679a8-151">In this case, the message tells the user why credentials are needed and gives them confidence that the request is legitimate.</span></span>

### <span data-ttu-id="679a8-152">Beispiel 8</span><span class="sxs-lookup"><span data-stu-id="679a8-152">Example 8</span></span>

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

<span data-ttu-id="679a8-153">Dieser Befehl ruft die Anmeldeinformationen vom Remotecomputer „Server01“ ab.</span><span class="sxs-lookup"><span data-stu-id="679a8-153">This command gets a credential from the Server01 remote computer.</span></span> <span data-ttu-id="679a8-154">Der Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Get-Credential` Befehls auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="679a8-154">The command uses the `Invoke-Command` cmdlet to run a `Get-Credential` command on the remote computer.</span></span> <span data-ttu-id="679a8-155">Die Ausgabe zeigt die Remote Sicherheitsnachricht, die `Get-Credential` in der Authentifizierungs Aufforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="679a8-155">The output shows the remote security message that `Get-Credential` includes in the authentication prompt.</span></span>

## <span data-ttu-id="679a8-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="679a8-156">PARAMETERS</span></span>

### <span data-ttu-id="679a8-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="679a8-157">-Credential</span></span>

<span data-ttu-id="679a8-158">Gibt einen Benutzernamen für die Anmelde Informationen an, z. b. **USER01** oder **Domain01\User01**.</span><span class="sxs-lookup"><span data-stu-id="679a8-158">Specifies a user name for the credential, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="679a8-159">Der Parameter Name, `-Credential` , ist optional.</span><span class="sxs-lookup"><span data-stu-id="679a8-159">The parameter name, `-Credential`, is optional.</span></span>

<span data-ttu-id="679a8-160">Wenn Sie den Befehl übermitteln und einen Benutzernamen angeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="679a8-160">When you submit the command and specify a user name, you're prompted for a password.</span></span> <span data-ttu-id="679a8-161">Wenn Sie diesen Parameter weglassen, werden Sie aufgefordert, einen Benutzernamen und ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="679a8-161">If you omit this parameter, you're prompted for a user name and a password.</span></span>

<span data-ttu-id="679a8-162">Wenn Sie in PowerShell 3,0 einen Benutzernamen ohne Domäne eingeben, wird von kein umgekehrter `Get-Credential` Schrägstrich mehr vor dem Namen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="679a8-162">Starting in PowerShell 3.0, if you enter a user name without a domain, `Get-Credential` no longer inserts a backslash before the name.</span></span>

<span data-ttu-id="679a8-163">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="679a8-163">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="679a8-164">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="679a8-164">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="679a8-165">-Meldung</span><span class="sxs-lookup"><span data-stu-id="679a8-165">-Message</span></span>

<span data-ttu-id="679a8-166">Gibt eine Meldung an, die in der Authentifizierungsaufforderung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="679a8-166">Specifies a message that appears in the authentication prompt.</span></span> <span data-ttu-id="679a8-167">Dieser Parameter dient zur Verwendung in einer Funktion oder in einem Skript.</span><span class="sxs-lookup"><span data-stu-id="679a8-167">This parameter is designed for use in a function or script.</span></span> <span data-ttu-id="679a8-168">Sie können die Meldung verwenden, um dem Benutzer zu erklären, warum Sie Anmeldeinformationen anfordern und wie sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="679a8-168">You can use the message to explain to the user why you are requesting credentials and how they will be used.</span></span>

<span data-ttu-id="679a8-169">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="679a8-169">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="679a8-170">-Title</span><span class="sxs-lookup"><span data-stu-id="679a8-170">-Title</span></span>

<span data-ttu-id="679a8-171">Legt den Text der Titelzeile für die Authentifizierungs Aufforderung in der-Konsole fest.</span><span class="sxs-lookup"><span data-stu-id="679a8-171">Sets the text of the title line for the authentication prompt in the console.</span></span>

<span data-ttu-id="679a8-172">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="679a8-172">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="679a8-173">-UserName</span><span class="sxs-lookup"><span data-stu-id="679a8-173">-UserName</span></span>

<span data-ttu-id="679a8-174">Gibt einen Benutzernamen an.</span><span class="sxs-lookup"><span data-stu-id="679a8-174">Specifies a user name.</span></span> <span data-ttu-id="679a8-175">Die Authentifizierungsaufforderung fordert die Eingabe eines Kennworts für den Benutzernamen an.</span><span class="sxs-lookup"><span data-stu-id="679a8-175">The authentication prompt requests a password for the user name.</span></span> <span data-ttu-id="679a8-176">Standardmäßig ist der Benutzername leer, und die Authentifizierungsaufforderung fordert sowohl einen Benutzernamen als auch ein Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="679a8-176">By default, the user name is blank and the authentication prompt requests both a user name and password.</span></span>

<span data-ttu-id="679a8-177">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="679a8-177">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="679a8-178">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="679a8-178">CommonParameters</span></span>

<span data-ttu-id="679a8-179">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="679a8-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="679a8-180">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="679a8-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="679a8-181">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="679a8-181">INPUTS</span></span>

### <span data-ttu-id="679a8-182">Keine</span><span class="sxs-lookup"><span data-stu-id="679a8-182">None</span></span>

<span data-ttu-id="679a8-183">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="679a8-183">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="679a8-184">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="679a8-184">OUTPUTS</span></span>

### <span data-ttu-id="679a8-185">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="679a8-185">System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="679a8-186">`Get-Credential` Gibt ein Anmelde Informationen-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="679a8-186">`Get-Credential` returns a credential object.</span></span>

## <span data-ttu-id="679a8-187">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="679a8-187">NOTES</span></span>

<span data-ttu-id="679a8-188">Sie können das **PSCredential** -Objekt verwenden, das `Get-Credential` in Cmdlets erstellt, die eine Benutzerauthentifizierung anfordern, z. b. solche mit einem **Credential** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="679a8-188">You can use the **PSCredential** object that `Get-Credential` creates in cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span>

<span data-ttu-id="679a8-189">Der **Credential** -Parameter wird nicht von allen Anbietern unterstützt, die mit PowerShell installiert werden.</span><span class="sxs-lookup"><span data-stu-id="679a8-189">The **Credential** parameter is not supported by all providers that are installed with PowerShell.</span></span>
<span data-ttu-id="679a8-190">Ab PowerShell 3,0 wird es für SELECT-Cmdlets unterstützt, wie z `Get-Content` . b. die-und- `New-PSDrive` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="679a8-190">Beginning in PowerShell 3.0, it is supported on select cmdlets, such as the `Get-Content` and `New-PSDrive` cmdlets.</span></span>

## <span data-ttu-id="679a8-191">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="679a8-191">RELATED LINKS</span></span>

[<span data-ttu-id="679a8-192">PromptForCredential</span><span class="sxs-lookup"><span data-stu-id="679a8-192">PromptForCredential</span></span>](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
