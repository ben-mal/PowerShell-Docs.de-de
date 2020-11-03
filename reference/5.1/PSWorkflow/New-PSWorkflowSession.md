---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSWorkflow
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowSession
ms.openlocfilehash: 995dd8a6df3ac8ebd7a204d2aefef3fa6aa71e14
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213364"
---
# <span data-ttu-id="43df4-103">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="43df4-103">New-PSWorkflowSession</span></span>

## <span data-ttu-id="43df4-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="43df4-104">SYNOPSIS</span></span>
<span data-ttu-id="43df4-105">Erstellt eine Workflowsitzung.</span><span class="sxs-lookup"><span data-stu-id="43df4-105">Creates a workflow session.</span></span>

## <span data-ttu-id="43df4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43df4-106">SYNTAX</span></span>

```
New-PSWorkflowSession [[-ComputerName] <String[]>] [-Credential <Object>] [-Name <String[]>] [-Port <Int32>]
 [-UseSSL] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-EnableNetworkAccess]
 [<CommonParameters>]
```

## <span data-ttu-id="43df4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="43df4-107">DESCRIPTION</span></span>

<span data-ttu-id="43df4-108">Mit dem `New-PSWorkflowSession` -Cmdlet wird eine vom Benutzer verwaltete Sitzung ( **PSSession** ) erstellt, die speziell für die Ausführung von Windows PowerShell-Workflows konzipiert ist.</span><span class="sxs-lookup"><span data-stu-id="43df4-108">The `New-PSWorkflowSession` cmdlet creates a user-managed session ( **PSSession** ) that is especially designed for running Windows PowerShell workflows.</span></span> <span data-ttu-id="43df4-109">Es verwendet die Microsoft.PowerShell.Workflow-Sitzungskonfiguration, die Skripts, Typ- und Formatierungsdateien enthält, und Optionen, die für Workflows erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="43df4-109">It uses the Microsoft.PowerShell.Workflow session configuration, which includes scripts, type and formatting files, and options that are required for workflows.</span></span>

<span data-ttu-id="43df4-110">Sie können `New-PSWorkflowSession` oder den zugehörigen Alias verwenden `nwsn` .</span><span class="sxs-lookup"><span data-stu-id="43df4-110">You can use `New-PSWorkflowSession` or its alias, `nwsn`.</span></span>

<span data-ttu-id="43df4-111">Sie können diesem Befehl auch allgemeine Workflowparameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="43df4-111">You can also add workflow common parameters to this command.</span></span> <span data-ttu-id="43df4-112">Weitere Informationen zu allgemeinen Workflow Parametern finden Sie unter [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="43df4-112">For more information about workflow common parameters, see [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)</span></span>

<span data-ttu-id="43df4-113">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="43df4-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="43df4-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="43df4-114">EXAMPLES</span></span>

### <span data-ttu-id="43df4-115">Beispiel 1: Erstellen einer Workflow Sitzung auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="43df4-115">Example 1: Create a workflow session on a remote computer</span></span>

<span data-ttu-id="43df4-116">In diesem Beispiel wird die **workflowtests** -Sitzung auf dem Remote Computer Computern servernode01 erstellt.</span><span class="sxs-lookup"><span data-stu-id="43df4-116">This example creates the **WorkflowTests** session on the ServerNode01 remote computer.</span></span>

```powershell
$params = @{
    ComputerName = "ServerNode01"
    Name = "WorkflowTests"
    SessionOption = (New-PSSessionOption -OutputBufferingMode Drop)
}
New-PSWorkflowSession @params
```

<span data-ttu-id="43df4-117">Der Wert des **sessionoption** -Parameters ist ein `New-PSSessionOption` Befehl, mit dem der Ausgabepuffer Modus in der Sitzung auf **Drop** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="43df4-117">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that sets the output buffering mode in the session to **Drop** .</span></span>

### <span data-ttu-id="43df4-118">Beispiel 2: Erstellen von Workflow Sitzungen auf mehreren Remote Computern</span><span class="sxs-lookup"><span data-stu-id="43df4-118">Example 2: Create workflow sessions on multiple remote computers</span></span>

<span data-ttu-id="43df4-119">In diesem Beispiel werden Workflow Sitzungen auf den Computern Computern servernode01 und Server12 erstellt.</span><span class="sxs-lookup"><span data-stu-id="43df4-119">This example creates workflow sessions on the ServerNode01 and Server12 computers.</span></span> <span data-ttu-id="43df4-120">Der Befehl verwendet den **Credential** -Parameter zur Ausführung mit den Berechtigungen des Domänenadministrators.</span><span class="sxs-lookup"><span data-stu-id="43df4-120">The command uses the **Credential** parameter to run with the permissions of the domain administrator.</span></span>

```powershell
"ServerNode01", "Server12" |
    New-PSWorkflowSession -Name WorkflowSession -Credential Domain01\Admin01 -ThrottleLimit 150
```

<span data-ttu-id="43df4-121">Der Befehl verwendet den **ThrottleLimit** -Parameter, um die Drosselungsgrenze pro Befehl auf 150 zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="43df4-121">The command uses the **ThrottleLimit** parameter to increase the per-command throttle limit to 150.</span></span>
<span data-ttu-id="43df4-122">Dieser Wert hat Vorrang vor dem Standard Drosselungs Limit von 100, das in der **Microsoft. PowerShell. Workflow** -Sitzungs Konfiguration festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="43df4-122">This value takes precedence over the default throttle limit of 100 that is set in the **Microsoft.PowerShell.Workflow** session configuration.</span></span>

## <span data-ttu-id="43df4-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43df4-123">PARAMETERS</span></span>

### <span data-ttu-id="43df4-124">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="43df4-124">-ApplicationName</span></span>

<span data-ttu-id="43df4-125">Gibt das Anwendungsnamenssegment des Verbindungs-URI an.</span><span class="sxs-lookup"><span data-stu-id="43df4-125">Specifies the application name segment of the connection URI.</span></span>

<span data-ttu-id="43df4-126">Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="43df4-126">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="43df4-127">Wenn diese Einstellungsvariable nicht definiert ist, ist der Standardwert „WSMan“.</span><span class="sxs-lookup"><span data-stu-id="43df4-127">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="43df4-128">Dieser Wert ist für die meisten Verwendungsarten geeignet.</span><span class="sxs-lookup"><span data-stu-id="43df4-128">This value is appropriate for most uses.</span></span> <span data-ttu-id="43df4-129">Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="43df4-129">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="43df4-130">Der WinRM-Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="43df4-130">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="43df4-131">Der Wert dieses Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="43df4-131">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="43df4-132">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="43df4-132">-Authentication</span></span>

<span data-ttu-id="43df4-133">Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="43df4-133">Specifies the mechanism that is used to authenticate the user credentials.</span></span>
<span data-ttu-id="43df4-134">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="43df4-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="43df4-135">Standard</span><span class="sxs-lookup"><span data-stu-id="43df4-135">Default</span></span>
- <span data-ttu-id="43df4-136">Basic</span><span class="sxs-lookup"><span data-stu-id="43df4-136">Basic</span></span>
- <span data-ttu-id="43df4-137">CredSSP</span><span class="sxs-lookup"><span data-stu-id="43df4-137">Credssp</span></span>
- <span data-ttu-id="43df4-138">Digest</span><span class="sxs-lookup"><span data-stu-id="43df4-138">Digest</span></span>
- <span data-ttu-id="43df4-139">Kerberos</span><span class="sxs-lookup"><span data-stu-id="43df4-139">Kerberos</span></span>
- <span data-ttu-id="43df4-140">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="43df4-140">Negotiate</span></span>
- <span data-ttu-id="43df4-141">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="43df4-141">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="43df4-142">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="43df4-142">The default value is Default.</span></span>

<span data-ttu-id="43df4-143">Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43df4-143">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="43df4-144">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="43df4-144">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="43df4-145">Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern</span><span class="sxs-lookup"><span data-stu-id="43df4-145">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="43df4-146">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="43df4-146">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="43df4-147">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43df4-147">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df4-148">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="43df4-148">-CertificateThumbprint</span></span>

<span data-ttu-id="43df4-149">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="43df4-149">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="43df4-150">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="43df4-150">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="43df4-151">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="43df4-151">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="43df4-152">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="43df4-152">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="43df4-153">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie das `Get-Item` Cmdlet oder das `Get-ChildItem` Cmdlet im Windows PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="43df4-153">To get a certificate thumbprint, use the `Get-Item` cmdlet or the `Get-ChildItem` cmdlet in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="43df4-154">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="43df4-154">-ComputerName</span></span>

<span data-ttu-id="43df4-155">Erstellt eine permanente Verbindung ( **PSSession** ) mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="43df4-155">Creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="43df4-156">Wenn Sie mehrere Computernamen eingeben, erstellt Windows PowerShell mehrere **pssessions** , eine für jeden Computer.</span><span class="sxs-lookup"><span data-stu-id="43df4-156">If you enter multiple computer names, Windows PowerShell creates multiple **PSSessions** , one for each computer.</span></span> <span data-ttu-id="43df4-157">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="43df4-157">The default is the local computer.</span></span>

<span data-ttu-id="43df4-158">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen mindestens eines Computers ein.</span><span class="sxs-lookup"><span data-stu-id="43df4-158">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="43df4-159">Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.</span><span class="sxs-lookup"><span data-stu-id="43df4-159">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="43df4-160">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, ist der vollqualifizierte Domänenname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="43df4-160">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="43df4-161">Sie können einen Computernamen auch über die Pipeline in Anführungszeichen senden `New-PSWorkflowSession` .</span><span class="sxs-lookup"><span data-stu-id="43df4-161">You can also pipe a computer name, in quotation marks to `New-PSWorkflowSession`.</span></span>

<span data-ttu-id="43df4-162">Um eine IP-Adresse im Wert des **Computername** -Parameters zu verwenden, muss der Befehl den **Credential** -Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="43df4-162">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="43df4-163">Außerdem muss der Computer für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remotecomputers muss in der WinRM TrustedHosts-Liste auf dem lokalen Computer enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="43df4-163">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="43df4-164">Anweisungen zum Hinzufügen eines Computer namens zur Liste "Treuhänder Hosts" finden Sie unter "Vorgehensweise beim Hinzufügen eines Computers zur Liste vertrauenswürdiger Hosts" in [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="43df4-164">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="43df4-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="43df4-165">-Credential</span></span>

<span data-ttu-id="43df4-166">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="43df4-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="43df4-167">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="43df4-167">The default is the current user.</span></span> <span data-ttu-id="43df4-168">Geben Sie einen Benutzernamen ein, z. b. USER01, Domain01\User01 oder User@Domain.com , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom Cmdlet zurück gegebenes Objekt `Get-Credential` .</span><span class="sxs-lookup"><span data-stu-id="43df4-168">Type a user name, such as User01, Domain01\User01, or User@Domain.com, or enter a **PSCredential** object, such as one returned by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="43df4-169">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="43df4-169">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="43df4-170">-Enablenetworkaccess</span><span class="sxs-lookup"><span data-stu-id="43df4-170">-EnableNetworkAccess</span></span>

<span data-ttu-id="43df4-171">Gibt an, dass mit diesem Cmdlet Loopback Sitzungen ein interaktives Sicherheits Token hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="43df4-171">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="43df4-172">Mit dem interaktiven Token können Sie die Befehle in der Loopbacksitzung ausführen, um Daten von anderen Computern abzurufen.</span><span class="sxs-lookup"><span data-stu-id="43df4-172">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="43df4-173">Beispielsweise können Sie einen Befehl in der Sitzung ausführen, mit dem XML-Dateien von einem Remotecomputer auf den lokalen Computer kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="43df4-173">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="43df4-174">Eine Loopback Sitzung ist eine **PSSession** , die auf demselben computerbasiert und endet.</span><span class="sxs-lookup"><span data-stu-id="43df4-174">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="43df4-175">Um eine Loopback Sitzung zu erstellen, geben Sie den **Computername** -Parameter nicht an, oder legen Sie seinen Wert auf "dot", "localhost" oder den Namen des lokalen Computers fest.</span><span class="sxs-lookup"><span data-stu-id="43df4-175">To create a loopback session, do not specify the **ComputerName** parameter or set its value to dot, localhost, or the name of the local computer.</span></span>

<span data-ttu-id="43df4-176">Standardmäßig werden Loopback Sitzungen mit einem Netzwerk Token erstellt, das möglicherweise nicht über ausreichende Berechtigungen zum Authentifizieren bei Remote Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="43df4-176">By default, loopback sessions are created that have a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="43df4-177">Der **EnableNetworkAccess** -Parameter ist nur bei Loopbacksitzungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="43df4-177">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="43df4-178">Wenn Sie den **enablenetworkaccess** -Parameter angeben, wenn Sie eine Sitzung auf einem Remote Computer erstellen, ist der Befehl erfolgreich, aber der-Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="43df4-178">If you specify the **EnableNetworkAccess** parameter when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="43df4-179">Sie können auch Remotezugriff in einer Loopbacksitzung erlauben, indem Sie den **CredSSP** -Wert des **Authentication** -Parameters verwenden, der die Anmeldeinformationen für die Sitzung an andere Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="43df4-179">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="43df4-180">Um den Computer vor böswilligem Zugriff zu schützen, können getrennte Loopback Sitzungen mit interaktiven Tokens, die mit dem **enablenetworkaccess** -Parameter erstellt wurden, nur von dem Computer wieder hergestellt werden, auf dem die Sitzung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="43df4-180">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="43df4-181">Die Verbindung von getrennten Sitzungen, die die CredSSP-Authentifizierung verwenden, kann von anderen Computern wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="43df4-181">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="43df4-182">Weitere Informationen finden Sie unter `Disconnect-PSSession`-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43df4-182">For more information, see the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="43df4-183">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="43df4-183">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="43df4-184">-Name</span><span class="sxs-lookup"><span data-stu-id="43df4-184">-Name</span></span>

<span data-ttu-id="43df4-185">Gibt einen Anzeigenamen für die Workflowsitzung an.</span><span class="sxs-lookup"><span data-stu-id="43df4-185">Specifies a friendly name for the workflow session.</span></span> <span data-ttu-id="43df4-186">Sie können den Namen mit anderen Cmdlets verwenden, z `Get-PSSession` . b `Enter-PSSession` . und.</span><span class="sxs-lookup"><span data-stu-id="43df4-186">You can use the name with other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="43df4-187">Der Name muss für den Computer oder die aktuelle Sitzung nicht eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="43df4-187">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Session#
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df4-188">-Port</span><span class="sxs-lookup"><span data-stu-id="43df4-188">-Port</span></span>

<span data-ttu-id="43df4-189">Gibt den Netzwerkport an dem für diese Verbindung verwendeten Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="43df4-189">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="43df4-190">Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.</span><span class="sxs-lookup"><span data-stu-id="43df4-190">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="43df4-191">Die Standardports sind 5985 (WinRM-Port für http) und 5986 (WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="43df4-191">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="43df4-192">Bevor Sie einen anderen Port verwenden, müssen Sie den WinRM-Listener auf dem Remote Computer so konfigurieren, dass er an diesem Port lauscht.</span><span class="sxs-lookup"><span data-stu-id="43df4-192">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="43df4-193">Verwenden Sie die folgenden Befehle, um den Listener zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="43df4-193">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="43df4-194">Verwenden Sie den **Port** -Parameter nur, wenn es unbedingt notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="43df4-194">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="43df4-195">Die Porteinstellung im Befehl gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="43df4-195">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="43df4-196">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="43df4-196">An alternate port setting might prevent the command from running on all computers.</span></span>

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

### <span data-ttu-id="43df4-197">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="43df4-197">-SessionOption</span></span>

<span data-ttu-id="43df4-198">Gibt erweiterte Optionen für die Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="43df4-198">Specifies advanced options for the session.</span></span> <span data-ttu-id="43df4-199">Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="43df4-199">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet.</span></span>

<span data-ttu-id="43df4-200">Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="43df4-200">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="43df4-201">Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="43df4-201">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="43df4-202">Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="43df4-202">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="43df4-203">Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="43df4-203">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="43df4-204">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="43df4-204">For more information about session configurations, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="43df4-205">Eine Beschreibung der Sitzungs Optionen, einschließlich der Standardwerte, finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="43df4-205">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="43df4-206">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="43df4-206">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df4-207">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="43df4-207">-ThrottleLimit</span></span>

<span data-ttu-id="43df4-208">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="43df4-208">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="43df4-209">Wenn Sie diesen Parameter weglassen oder den Wert 0 (null) eingeben, wird der Standardwert für die **Microsoft. powershellworkflow** -Sitzungs Konfiguration 100 verwendet.</span><span class="sxs-lookup"><span data-stu-id="43df4-209">If you omit this parameter or enter a value of 0 (zero), the default value for the **Microsoft.PowerShellWorkflow** session configuration, 100, is used.</span></span>

<span data-ttu-id="43df4-210">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="43df4-210">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43df4-211">-US-</span><span class="sxs-lookup"><span data-stu-id="43df4-211">-UseSSL</span></span>

<span data-ttu-id="43df4-212">Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll verwendet, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="43df4-212">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="43df4-213">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="43df4-213">By default, SSL is not used.</span></span>

<span data-ttu-id="43df4-214">WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="43df4-214">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="43df4-215">Der Parameter " **eessl** " ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-Verbindung anstelle einer HTTP-Verbindung sendet.</span><span class="sxs-lookup"><span data-stu-id="43df4-215">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="43df4-216">Wenn Sie diesen Parameter angeben, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="43df4-216">If you specify this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="43df4-217">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="43df4-217">CommonParameters</span></span>

<span data-ttu-id="43df4-218">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="43df4-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43df4-219">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="43df4-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43df4-220">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="43df4-220">INPUTS</span></span>

### <span data-ttu-id="43df4-221">System. Management. Automation. Runspaces. PSSession [], System. String</span><span class="sxs-lookup"><span data-stu-id="43df4-221">System.Management.Automation.Runspaces.PSSession[], System.String</span></span>

<span data-ttu-id="43df4-222">Sie können eine Sitzung oder einen Computernamen über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="43df4-222">You can pipe a session or a computer name to this cmdlet.</span></span>

## <span data-ttu-id="43df4-223">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="43df4-223">OUTPUTS</span></span>

### <span data-ttu-id="43df4-224">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="43df4-224">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="43df4-225">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="43df4-225">NOTES</span></span>

<span data-ttu-id="43df4-226">Ein `New-PSWorkflowSession` Befehl entspricht dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="43df4-226">A `New-PSWorkflowSession` command is equivalent to the following command:</span></span>

`New-PSSession -ConfigurationName Microsoft.PowerShell.Workflow`

## <span data-ttu-id="43df4-227">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="43df4-227">RELATED LINKS</span></span>

[<span data-ttu-id="43df4-228">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="43df4-228">Disconnect-PSSession</span></span>](../Microsoft.PowerShell.Core/Disconnect-PSSession.md)

[<span data-ttu-id="43df4-229">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="43df4-229">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="43df4-230">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="43df4-230">New-PSTransportOption</span></span>](../Microsoft.PowerShell.Core/New-PSTransportOption.md)

[<span data-ttu-id="43df4-231">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="43df4-231">Register-PSSessionConfiguration</span></span>](../Microsoft.PowerShell.Core/Register-PSSessionConfiguration.md)

[<span data-ttu-id="43df4-232">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="43df4-232">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="43df4-233">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="43df4-233">about_Session_Configurations</span></span>](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)

[<span data-ttu-id="43df4-234">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="43df4-234">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="43df4-235">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="43df4-235">about_WorkflowCommonParameters</span></span>](About/about_WorkflowCommonParameters.md)
