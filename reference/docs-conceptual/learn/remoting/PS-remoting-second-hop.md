---
ms.date: 05/14/2020
keywords: powershell,cmdlet
title: Ausführen des zweiten Hops in PowerShell-Remoting
description: In diesem Artikel werden die verschiedenen Methoden zum Konfigurieren der Authentifizierung des zweiten Hops für PowerShell-Remoting behandelt, einschließlich der Auswirkungen auf die Sicherheit und Empfehlungen.
ms.openlocfilehash: 905b27b4e6c612249c945a741bbe0d2ba9ae28aa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501370"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a><span data-ttu-id="bdb7a-104">Ausführen des zweiten Hops in PowerShell-Remoting</span><span class="sxs-lookup"><span data-stu-id="bdb7a-104">Making the second hop in PowerShell Remoting</span></span>

<span data-ttu-id="bdb7a-105">Das sogenannte „zweite Hop-Problem“ bezieht sich auf folgende Situation:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-105">The "second hop problem" refers to a situation like the following:</span></span>

1. <span data-ttu-id="bdb7a-106">Sie sind bei _ServerA_ angemeldet.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-106">You are logged in to _ServerA_.</span></span>
2. <span data-ttu-id="bdb7a-107">Sie starten von _ServerA_ aus eine PowerShell-Remotesitzung, um eine Verbindung mit _ServerB_ herzustellen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-107">From _ServerA_, you start a remote PowerShell session to connect to _ServerB_.</span></span>
3. <span data-ttu-id="bdb7a-108">Ein auf _ServerB_ über Ihre PowerShell-Remotesitzung ausgeführter Befehl versucht, auf eine Ressource auf _ServerC_ zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-108">A command you run on _ServerB_ via your PowerShell Remoting session attempts to access a resource on _ServerC_.</span></span>
4. <span data-ttu-id="bdb7a-109">Der Zugriff auf die Ressource auf _ServerC_ wird verweigert, da die Anmeldeinformationen, die Sie zum Erstellen der PowerShell-Remotesitzung verwendet haben, nicht von _ServerB_ an _ServerC_ übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-109">Access to the resource on _ServerC_ is denied, because the credentials you used to create the PowerShell Remoting session are not passed from _ServerB_ to _ServerC_.</span></span>

<span data-ttu-id="bdb7a-110">Es gibt verschiedene Möglichkeiten, um dieses Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-110">There are several ways to address this problem.</span></span> <span data-ttu-id="bdb7a-111">In der folgenden Tabelle werden die Methoden in der Reihenfolge ihrer Präferenz aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-111">The following table lists the methods in order of preference.</span></span>

|                      <span data-ttu-id="bdb7a-112">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bdb7a-112">Configuration</span></span>                       |                                  <span data-ttu-id="bdb7a-113">Hinweis</span><span class="sxs-lookup"><span data-stu-id="bdb7a-113">Note</span></span>                                  |
| -------------------------------------------------------- | ---------------------------------------------------------------------- |
| <span data-ttu-id="bdb7a-114">CredSSP</span><span class="sxs-lookup"><span data-stu-id="bdb7a-114">CredSSP</span></span>                                                  | <span data-ttu-id="bdb7a-115">Ausgeglichene Benutzerfreundlichkeit und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bdb7a-115">Balances ease of use and security</span></span>                                      |
| <span data-ttu-id="bdb7a-116">Ressourcenbasierte eingeschränkte Kerberos-Delegierung</span><span class="sxs-lookup"><span data-stu-id="bdb7a-116">Resource-based Kerberos constrained delegation</span></span>           | <span data-ttu-id="bdb7a-117">Höhere Sicherheit mit einfacherer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bdb7a-117">Higher security with simpler configuration</span></span>                             |
| <span data-ttu-id="bdb7a-118">Eingeschränkte Kerberos-Delegierung</span><span class="sxs-lookup"><span data-stu-id="bdb7a-118">Kerberos constrained delegation</span></span>                          | <span data-ttu-id="bdb7a-119">Hohe Sicherheit, erfordert jedoch einen Domänenadministrator</span><span class="sxs-lookup"><span data-stu-id="bdb7a-119">High security but requires Domain Administrator</span></span>                         |
| <span data-ttu-id="bdb7a-120">Kerberos-Delegierung (uneingeschränkt)</span><span class="sxs-lookup"><span data-stu-id="bdb7a-120">Kerberos delegation (unconstrained)</span></span>                      | <span data-ttu-id="bdb7a-121">Nicht empfohlen</span><span class="sxs-lookup"><span data-stu-id="bdb7a-121">Not recommended</span></span>                                                        |
| <span data-ttu-id="bdb7a-122">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="bdb7a-122">Just Enough Administration (JEA)</span></span>                         | <span data-ttu-id="bdb7a-123">Kann die beste Sicherheit bieten, erfordert jedoch eine ausführlichere Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bdb7a-123">Can provide the best security but requires more detailed configuration</span></span> |
| <span data-ttu-id="bdb7a-124">PSSessionConfiguration mithilfe von RunAs</span><span class="sxs-lookup"><span data-stu-id="bdb7a-124">PSSessionConfiguration using RunAs</span></span>                       | <span data-ttu-id="bdb7a-125">Einfachere Konfiguration, erfordert jedoch Verwaltung von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="bdb7a-125">Simpler to configure but requires credential management</span></span>                |
| <span data-ttu-id="bdb7a-126">Übergeben von Anmeldeinformationen innerhalb eines `Invoke-Command`-Skriptblocks</span><span class="sxs-lookup"><span data-stu-id="bdb7a-126">Pass credentials inside an `Invoke-Command` script block</span></span> | <span data-ttu-id="bdb7a-127">Am einfachsten zu verwenden, jedoch müssen Anmeldeinformationen bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="bdb7a-127">Simplest to use but you must provide credentials</span></span>                       |

## <a name="credssp"></a><span data-ttu-id="bdb7a-128">CredSSP</span><span class="sxs-lookup"><span data-stu-id="bdb7a-128">CredSSP</span></span>

<span data-ttu-id="bdb7a-129">Sie können den [Credential Security Support Provider (CredSSP)][credssp] für die Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-129">You can use the [Credential Security Support Provider (CredSSP)][credssp] for authentication.</span></span>
<span data-ttu-id="bdb7a-130">CredSSP speichert Anmeldeinformationen auf dem Remoteserver  _ServerB_. Der Server wird dadurch der Gefahr von Angriffen zum Diebstahl der Anmeldeinformationen ausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-130">CredSSP caches credentials on the remote server (_ServerB_), so using it opens you up to credential theft attacks.</span></span> <span data-ttu-id="bdb7a-131">Wenn der Remotecomputer kompromittiert ist, hat der Angreifer Zugriff auf die Anmeldeinformationen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-131">If the remote computer is compromised, the attacker has access to the user's credentials.</span></span> <span data-ttu-id="bdb7a-132">CredSSP ist standardmäßig sowohl auf Client- als auch auf Servercomputern deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-132">CredSSP is disabled by default on both client and server computers.</span></span> <span data-ttu-id="bdb7a-133">Sie sollten CredSSP nur in absolut vertrauenswürdigen Umgebungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-133">You should enable CredSSP only in the most trusted environments.</span></span> <span data-ttu-id="bdb7a-134">Beispielsweise wenn ein Domänenadministrator eine Verbindung mit einem Domänencontroller herstellt, weil der Domänencontroller hochgradig vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-134">For example, a domain administrator connecting to a domain controller because the domain controller is highly trusted.</span></span>

<span data-ttu-id="bdb7a-135">Weitere Informationen zu Sicherheitsaspekten bei der Verwendung von CredSSP für PowerShell-Remoting finden Sie unter [Versehentliche Sabotage: Vorsicht vor CredSSP][beware].</span><span class="sxs-lookup"><span data-stu-id="bdb7a-135">For more information about security concerns when using CredSSP for PowerShell Remoting, see [Accidental Sabotage: Beware of CredSSP][beware].</span></span>

<span data-ttu-id="bdb7a-136">Weitere Informationen zu Angriffen zum Diebstahl von Anmeldeinformationen finden Sie unter [Abschwächen von Pass-the-Hash-Angriffen (PtH) und anderen Techniken zum Diebstahl von Anmeldeinformationen][pth].</span><span class="sxs-lookup"><span data-stu-id="bdb7a-136">For more information about credential theft attacks, see [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft][pth].</span></span>

<span data-ttu-id="bdb7a-137">Ein Beispiel zum Aktivieren und Verwenden von CredSSP für PowerShell-Remoting finden Sie unter [Enable PowerShell "Second-Hop" Functionality with CredSSP][credssp-psblog] (Aktivieren der PowerShell-Funktion für zweiten Hop mit CredSSP).</span><span class="sxs-lookup"><span data-stu-id="bdb7a-137">For an example of how to enable and use CredSSP for PowerShell remoting, see [Enable PowerShell "Second-Hop" Functionality with CredSSP][credssp-psblog].</span></span>

<span data-ttu-id="bdb7a-138">**Vorteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-138">**Pros**</span></span>

- <span data-ttu-id="bdb7a-139">Die Lösung eignet sich für alle Server mit Windows Server 2008 oder höher.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-139">It works for all servers with Windows Server 2008 or later.</span></span>

<span data-ttu-id="bdb7a-140">**Nachteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-140">**Cons**</span></span>

- <span data-ttu-id="bdb7a-141">birgt Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="bdb7a-141">Has security vulnerabilities.</span></span>
- <span data-ttu-id="bdb7a-142">erfordert die Konfiguration von Client- und Serverrollen</span><span class="sxs-lookup"><span data-stu-id="bdb7a-142">Requires configuration of both client and server roles.</span></span>
- <span data-ttu-id="bdb7a-143">Funktioniert nicht mit der Gruppe „geschützte Benutzer“.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-143">Does not work with the Protected Users group.</span></span> <span data-ttu-id="bdb7a-144">Weitere Informationen finden Sie unter [Sicherheitsgruppe „Geschützte Benutzer“][protected-users].</span><span class="sxs-lookup"><span data-stu-id="bdb7a-144">For more information, see [Protected Users Security Group][protected-users].</span></span>

## <a name="kerberos-constrained-delegation"></a><span data-ttu-id="bdb7a-145">Eingeschränkte Kerberos-Delegierung</span><span class="sxs-lookup"><span data-stu-id="bdb7a-145">Kerberos constrained delegation</span></span>

<span data-ttu-id="bdb7a-146">Sie können eingeschränkte Legacydelegierung (nicht ressourcenbasiert) verwenden, um den zweiten Hop auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-146">You can use legacy constrained delegation (not resource-based) to make the second hop.</span></span> <span data-ttu-id="bdb7a-147">Konfigurieren Sie die eingeschränkte Kerberos-Delegierung mit der Option „Beliebiges Authentifizierungsprotokoll verwenden“, um den Protokollübergang zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-147">Configure Kerberos constrained delegation with the option "Use any authentication protocol" to allow protocol transition.</span></span>

<span data-ttu-id="bdb7a-148">**Vorteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-148">**Pros**</span></span>

- <span data-ttu-id="bdb7a-149">erfordert keine besondere Codierung</span><span class="sxs-lookup"><span data-stu-id="bdb7a-149">Requires no special coding</span></span>
- <span data-ttu-id="bdb7a-150">kein Speichern von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="bdb7a-150">Credentials are not stored.</span></span>

<span data-ttu-id="bdb7a-151">**Nachteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-151">**Cons**</span></span>

- <span data-ttu-id="bdb7a-152">keine Unterstützung für den zweiten Hop für WinRM</span><span class="sxs-lookup"><span data-stu-id="bdb7a-152">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="bdb7a-153">Erfordert Domänenadministratorzugriff für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bdb7a-153">Requires Domain Administrator access to configure.</span></span>
- <span data-ttu-id="bdb7a-154">muss auf dem Active Directory-Objekt des Remoteservers konfiguriert werden (_ServerB_)</span><span class="sxs-lookup"><span data-stu-id="bdb7a-154">Must be configured on the Active Directory object of the remote server (_ServerB_).</span></span>
- <span data-ttu-id="bdb7a-155">auf einen Server begrenzt;</span><span class="sxs-lookup"><span data-stu-id="bdb7a-155">Limited to one domain.</span></span> <span data-ttu-id="bdb7a-156">kann Domänen oder Gesamtstrukturen nicht überschreiten</span><span class="sxs-lookup"><span data-stu-id="bdb7a-156">Cannot cross domains or forests.</span></span>
- <span data-ttu-id="bdb7a-157">erfordert Rechte zum Aktualisieren von Objekten und Dienstprinzipalnamen (SPN)</span><span class="sxs-lookup"><span data-stu-id="bdb7a-157">Requires rights to update objects and Service Principal Names (SPNs).</span></span>
- <span data-ttu-id="bdb7a-158">_ServerB_ kann ein Kerberos-Ticket für _ServerC_ im Auftrag des Benutzers abrufen, ohne dass ein Benutzereingriff erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-158">_ServerB_ can acquire a Kerberos ticket to _ServerC_ on behalf of the user without user intervention.</span></span>

> [!NOTE]
> <span data-ttu-id="bdb7a-159">Active Directory-Konten mit dem Eigenschaftensatz **Konto ist vertraulich und kann nicht delegiert werden** können nicht delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-159">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="bdb7a-160">Weitere Informationen finden Sie unter [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] (Sicherheit im Fokus: Analyse von „Konto ist vertraulich und kann nicht delegiert werden“ für privilegierte Konten) und [Kerberos-Authentifizierungstools und -Einstellungen][ktools].</span><span class="sxs-lookup"><span data-stu-id="bdb7a-160">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

## <a name="resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="bdb7a-161">Ressourcenbasierte eingeschränkte Kerberos-Delegierung</span><span class="sxs-lookup"><span data-stu-id="bdb7a-161">Resource-based Kerberos constrained delegation</span></span>

<span data-ttu-id="bdb7a-162">Mithilfe von ressourcenbasierter eingeschränkter Kerberos-Delegierung (in Windows Server 2012 eingeführt) können Sie die Delegierung der Anmeldeinformationen für das Serverobjekt konfigurieren, in dem sich Ressourcen befinden.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-162">Using resource-based Kerberos constrained delegation (introduced in Windows Server 2012), you configure credential delegation on the server object where resources reside.</span></span> <span data-ttu-id="bdb7a-163">Im zuvor beschriebenen zweiten Hop-Szenario konfigurieren Sie _ServerC_ und geben an, von wo aus Anmeldeinformationen akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-163">In the second hop scenario described above, you configure _ServerC_ to specify from where it accepts delegated credentials.</span></span>

<span data-ttu-id="bdb7a-164">**Vorteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-164">**Pros**</span></span>

- <span data-ttu-id="bdb7a-165">kein Speichern von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="bdb7a-165">Credentials are not stored.</span></span>
- <span data-ttu-id="bdb7a-166">Konfiguriert mithilfe von PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="bdb7a-166">Configured using PowerShell cmdlets.</span></span> <span data-ttu-id="bdb7a-167">Keine besondere Codierung erforderlich</span><span class="sxs-lookup"><span data-stu-id="bdb7a-167">No special coding required.</span></span>
- <span data-ttu-id="bdb7a-168">Erfordert keinen Domänenadministratorzugriff für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bdb7a-168">Does not require Domain Administrator access to configure.</span></span>
- <span data-ttu-id="bdb7a-169">domänen- und gesamtstrukturübergreifende Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="bdb7a-169">Works across domains and forests.</span></span>

<span data-ttu-id="bdb7a-170">**Nachteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-170">**Cons**</span></span>

- <span data-ttu-id="bdb7a-171">erfordert Windows Server 2012 oder höher</span><span class="sxs-lookup"><span data-stu-id="bdb7a-171">Requires Windows Server 2012 or later.</span></span>
- <span data-ttu-id="bdb7a-172">keine Unterstützung für den zweiten Hop für WinRM</span><span class="sxs-lookup"><span data-stu-id="bdb7a-172">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="bdb7a-173">erfordert Rechte zum Aktualisieren von Objekten und Dienstprinzipalnamen (SPN)</span><span class="sxs-lookup"><span data-stu-id="bdb7a-173">Requires rights to update objects and Service Principal Names (SPNs).</span></span>

> [!NOTE]
> <span data-ttu-id="bdb7a-174">Active Directory-Konten mit dem Eigenschaftensatz **Konto ist vertraulich und kann nicht delegiert werden** können nicht delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-174">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="bdb7a-175">Weitere Informationen finden Sie unter [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] (Sicherheit im Fokus: Analyse von „Konto ist vertraulich und kann nicht delegiert werden“ für privilegierte Konten) und [Kerberos-Authentifizierungstools und -Einstellungen][ktools].</span><span class="sxs-lookup"><span data-stu-id="bdb7a-175">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

### <a name="example"></a><span data-ttu-id="bdb7a-176">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdb7a-176">Example</span></span>

<span data-ttu-id="bdb7a-177">Sehen wir uns ein PowerShell-Beispiel an, bei dem _ServerC_ für eine ressourcenbasierte eingeschränkte Delegierung konfiguriert wird, um delegierte Anmeldeinformationen von einem _ServerB_ zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-177">Let's look at a PowerShell example that configures resource-based constrained delegation on _ServerC_ to allow delegated credentials from a _ServerB_.</span></span> <span data-ttu-id="bdb7a-178">In diesem Beispiel wird davon ausgegangen, dass alle Server Windows Server 2012 oder höher ausführen und dass für jede Domäne jedes eingesetzten Servers mindestens ein Windows Server 2012-Domänencontroller vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-178">This example assumes that all servers are running Windows Server 2012 or later, and that there is at least one Windows Server 2012 domain controller each domain to which any of the servers belong.</span></span>

<span data-ttu-id="bdb7a-179">Bevor Sie die eingeschränkte Delegierung konfigurieren können, müssen Sie das `RSAT-AD-PowerShell`-Feature hinzufügen, um das Active Directory-PowerShell-Modul zu installieren und anschließend dieses Modul in die Sitzung zu importieren:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-179">Before you can configure constrained delegation, you must add the `RSAT-AD-PowerShell` feature to install the Active Directory PowerShell module, and then import that module into your session:</span></span>

```powershell
Add-WindowsFeature RSAT-AD-PowerShell
Import-Module ActiveDirectory
Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="bdb7a-180">Mehrere verfügbare Cmdlets haben jetzt einen **PrincipalsAllowedToDelegateToAccount**-Parameter:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-180">Several available cmdlets now have a **PrincipalsAllowedToDelegateToAccount** parameter:</span></span>

```Output
CommandType Name                 ModuleName
----------- ----                 ----------
Cmdlet      New-ADComputer       ActiveDirectory
Cmdlet      New-ADServiceAccount ActiveDirectory
Cmdlet      New-ADUser           ActiveDirectory
Cmdlet      Set-ADComputer       ActiveDirectory
Cmdlet      Set-ADServiceAccount ActiveDirectory
Cmdlet      Set-ADUser           ActiveDirectory
```

<span data-ttu-id="bdb7a-181">Der Parameter **PrincipalsAllowedToDelegateToAccount** legt das Active Directory-Objektattribut **MsDS-AllowedToActOnBehalfOfOtherIdentity** fest, das eine Zugriffssteuerungsliste (access control list, ACL) enthält. Diese gibt an, welche Konten die Berechtigung zum Delegieren von Anmeldeinformationen für das zugehörige Konto haben (in unserem Beispiel das Computerkonto für _ServerA_).</span><span class="sxs-lookup"><span data-stu-id="bdb7a-181">The **PrincipalsAllowedToDelegateToAccount** parameter sets the Active Directory object attribute **msDS-AllowedToActOnBehalfOfOtherIdentity**, which contains an access control list (ACL) that specifies which accounts have permission to delegate credentials to the associated account (in our example, it will be the machine account for _ServerA_).</span></span>

<span data-ttu-id="bdb7a-182">Richten Sie nun die Variablen ein, die wir verwenden, um die Server darzustellen:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-182">Now let's set up the variables we'll use to represent the servers:</span></span>

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

<span data-ttu-id="bdb7a-183">WinRM (und somit die PowerShell-Remoting) wird standardmäßig als Computerkonto ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-183">WinRM (and therefore PowerShell remoting) runs as the computer account by default.</span></span> <span data-ttu-id="bdb7a-184">Dies sehen Sie anhand der **StartName**-Eigenschaft des `winrm`-Diensts:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-184">You can see this by looking at the **StartName** property of the `winrm` service:</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name="winrm"' | Select-Object StartName
```

```Output
StartName
---------
NT AUTHORITY\NetworkService
```

<span data-ttu-id="bdb7a-185">Damit _ServerC_ die Delegierung aus einer PowerShell-Remoting-Sitzung auf _ServerB_ zulässt, vergeben wir Zugriffsrechte, indem wir den Parameter **PrincipalsAllowedToDelegateToAccount** von _ServerC_ auf das Computerobjekt von _ServerB_ festlegen:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-185">For _ServerC_ to allow delegation from a PowerShell remoting session on _ServerB_, we must set the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to the computer object of _ServerB_:</span></span>

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="bdb7a-186">Das Kerberos-[Schlüsselverteilungscenter (KDC)](/windows/win32/secauthn/key-distribution-center) speichert verweigerte Zugriffsversuche (negativer Cache) über einen Zeitraum von 15 Minuten.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-186">The Kerberos [Key Distribution Center (KDC)](/windows/win32/secauthn/key-distribution-center) caches denied-access attempts (negative cache) for 15 minutes.</span></span> <span data-ttu-id="bdb7a-187">Wenn _ServerB_ zuvor versucht hat, auf _ServerC_ zuzugreifen, müssen Sie zum Löschen des Caches auf _ServerB_ folgenden Befehl aufrufen:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-187">If _ServerB_ has previously attempted to access _ServerC_, you will need to clear the cache on _ServerB_ by invoking the following command:</span></span>

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

<span data-ttu-id="bdb7a-188">Sie können den Computer auch neu starten oder mindestens 15 Minuten warten, bevor Sie den Cache löschen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-188">You could also restart the computer, or wait at least 15 minutes to clear the cache.</span></span>

<span data-ttu-id="bdb7a-189">Nach dem Löschen des Cache können Sie erfolgreich Code vom _ServerA_ über _ServerB_ auf _ServerC_ ausführen:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-189">After clearing the cache, you can successfully run code from _ServerA_ through _ServerB_ to _ServerC_:</span></span>

```powershell
# Capture a credential
$cred = Get-Credential Contoso\Alice

# Test kerberos double hop
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    Test-Path \\$($using:ServerC.Name)\C$
    Get-Process lsass -ComputerName $($using:ServerC.Name)
    Get-EventLog -LogName System -Newest 3 -ComputerName $($using:ServerC.Name)
}
```

<span data-ttu-id="bdb7a-190">In diesem Beispiel wird die `$using`-Variable verwendet, um die `$ServerC`-Variable für _ServerB_ sichtbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-190">In this example, the `$using` variable is used to make the `$ServerC` variable visible to _ServerB_.</span></span>
<span data-ttu-id="bdb7a-191">Weitere Informationen zur `$using`-Variable finden Sie unter [About Remote Variables (Informationen zu Remote-Variablen)](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span><span class="sxs-lookup"><span data-stu-id="bdb7a-191">For more information about the `$using` variable, see [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span></span>

<span data-ttu-id="bdb7a-192">Damit mehrere Server Anmeldeinformationen an _ServerC_ delegieren können, müssen Sie den Wert des Parameters **PrincipalsAllowedToDelegateToAccount** auf _ServerC_ auf ein Array festlegen:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-192">To allow multiple servers to delegate credentials to _ServerC_, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to an array:</span></span>

```powershell
# Set up variables for each server
$ServerB1 = Get-ADComputer -Identity ServerB1
$ServerB2 = Get-ADComputer -Identity ServerB2
$ServerB3 = Get-ADComputer -Identity ServerB3
$ServerC  = Get-ADComputer -Identity ServerC

# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC `
    -PrincipalsAllowedToDelegateToAccount @($ServerB1,$ServerB2,$ServerB3)
```

<span data-ttu-id="bdb7a-193">Wenn Sie den zweiten Hop zwischen Domänen vornehmen möchten, müssen Sie den vollqualifizierten Domänennamen (FQDN) des Domänencontrollers jener Domäne hinzufügen, zu der _ServerB_ gehört:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-193">If you want to make the second hop across domains, add fully-qualified domain name (FQDN) of the domain controller of the domain to which _ServerB_ belongs:</span></span>

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

<span data-ttu-id="bdb7a-194">Um die Delegierung von Anmeldeinformationen an ServerC zu löschen, müssen Sie den Wert des Parameters **PrincipalsAllowedToDelegateToAccount** auf _ServerC_ auf `$null` festlegen:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-194">To remove the ability to delegate credentials to ServerC, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to `$null`:</span></span>

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="bdb7a-195">Informationen zu ressourcenbasierter eingeschränkter Kerberos-Delegierung</span><span class="sxs-lookup"><span data-stu-id="bdb7a-195">Information on resource-based Kerberos constrained delegation</span></span>

- <span data-ttu-id="bdb7a-196">[Neues bei der Kerberos-Authentifizierung][whats-new]</span><span class="sxs-lookup"><span data-stu-id="bdb7a-196">[What's New in Kerberos Authentication][whats-new]</span></span>
- <span data-ttu-id="bdb7a-197">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1 (Wie Windows Server 2012 bei den Problemen mit der eingeschränkten Kerberos-Delegierung Abhilfe schafft, Teil 1)][kcd2012-1]</span><span class="sxs-lookup"><span data-stu-id="bdb7a-197">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1][kcd2012-1]</span></span>
- <span data-ttu-id="bdb7a-198">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2 (Wie Windows Server 2012 bei den Problemen mit der eingeschränkten Kerberos-Delegierung Abhilfe schafft, Teil 2)][kcd2012-2]</span><span class="sxs-lookup"><span data-stu-id="bdb7a-198">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2][kcd2012-2]</span></span>
- <span data-ttu-id="bdb7a-199">[Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication (Grundlegendes zur eingeschränkten Kerberos-Delegierung für Azure Active Directory Application Proxy-Bereitstellungen mit integrierter Windows-Authentifizierung)][kcdpaper]</span><span class="sxs-lookup"><span data-stu-id="bdb7a-199">[Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication][kcdpaper]</span></span>
- <span data-ttu-id="bdb7a-200">[[MS-ADA2] Active Directory-Schemaattribute M2.210 msDS-AllowedToActOnBehalfOfOtherIdentity-Attribut][MS-ADA2]</span><span class="sxs-lookup"><span data-stu-id="bdb7a-200">[[MS-ADA2] Active Directory Schema Attributes M2.210 Attribute msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span></span>
- <span data-ttu-id="bdb7a-201">[[MS-SFU] Kerberos-Protokollerweiterungen: Protokoll 1.3.2 S4U2proxy für Service-for-User und eingeschränkte Delegierung][MS-SFU]</span><span class="sxs-lookup"><span data-stu-id="bdb7a-201">[[MS-SFU] Kerberos Protocol Extensions: Service for User and Constrained Delegation Protocol 1.3.2 S4U2proxy][MS-SFU]</span></span>
- <span data-ttu-id="bdb7a-202">[Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount (Remoteverwaltung ohne eingeschränkte Delegierung mit PrincipalsAllowedToDelegateToAccount)][remote-admin]</span><span class="sxs-lookup"><span data-stu-id="bdb7a-202">[Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount][remote-admin]</span></span>

## <a name="kerberos-delegation-unconstrained"></a><span data-ttu-id="bdb7a-203">Kerberos-Delegierung (uneingeschränkt)</span><span class="sxs-lookup"><span data-stu-id="bdb7a-203">Kerberos delegation (unconstrained)</span></span>

<span data-ttu-id="bdb7a-204">Sie können auch die uneingeschränkte Kerberos-Delegierung verwenden, um den zweiten Hop ausführen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-204">You can also used Kerberos unconstrained delegation to make the second hop.</span></span> <span data-ttu-id="bdb7a-205">Wie in allen Kerberos-Szenarios werden Anmeldeinformationen nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-205">Like all Kerberos scenarios, credentials are not stored.</span></span> <span data-ttu-id="bdb7a-206">Diese Methode unterstützt nicht den zweiten Hop für WinRM.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-206">This method does not support the second hop for WinRM.</span></span>

> [!WARNING]
> <span data-ttu-id="bdb7a-207">Diese Methode bietet keine Kontrolle darüber, wo die delegierten Anmeldeinformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-207">This method provides no control of where delegated credentials are used.</span></span> <span data-ttu-id="bdb7a-208">Sie ist weniger sicher als CredSSP.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-208">It is less secure than CredSSP.</span></span> <span data-ttu-id="bdb7a-209">Diese Methode sollte nur für Testszenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-209">This method should only be used for testing scenarios.</span></span>

## <a name="just-enough-administration-jea"></a><span data-ttu-id="bdb7a-210">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="bdb7a-210">Just Enough Administration (JEA)</span></span>

<span data-ttu-id="bdb7a-211">Mit JEA können Sie einschränken, welche Befehle ein Administrator während einer PowerShell-Sitzung ausführen darf.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-211">JEA allows you to restrict what commands an administrator can run during a PowerShell session.</span></span> <span data-ttu-id="bdb7a-212">Das Toolkit kann verwendet werden, um das zweite Hop-Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-212">It can be used to solve the second hop problem.</span></span>

<span data-ttu-id="bdb7a-213">Informationen zu JEA finden Sie unter [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span><span class="sxs-lookup"><span data-stu-id="bdb7a-213">For information about JEA, see [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span></span>

<span data-ttu-id="bdb7a-214">**Vorteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-214">**Pros**</span></span>

- <span data-ttu-id="bdb7a-215">keine Kennwortverwaltungsaufgaben bei Verwendung eines virtuellen Kontos</span><span class="sxs-lookup"><span data-stu-id="bdb7a-215">No password maintenance when using a virtual account.</span></span>

<span data-ttu-id="bdb7a-216">**Nachteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-216">**Cons**</span></span>

- <span data-ttu-id="bdb7a-217">erfordert WMF 5.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="bdb7a-217">Requires WMF 5.0 or later.</span></span>
- <span data-ttu-id="bdb7a-218">erfordert die Konfiguration auf jedem Zwischenserver (_ServerB_).</span><span class="sxs-lookup"><span data-stu-id="bdb7a-218">Requires configuration on every intermediate server (_ServerB_).</span></span>

## <a name="pssessionconfiguration-using-runas"></a><span data-ttu-id="bdb7a-219">PSSessionConfiguration mithilfe von RunAs</span><span class="sxs-lookup"><span data-stu-id="bdb7a-219">PSSessionConfiguration using RunAs</span></span>

<span data-ttu-id="bdb7a-220">Sie können eine Sitzungskonfiguration auf _ServerB_ erstellen und ihren **RunAsCredential**-Parameter festlegen.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-220">You can create a session configuration on _ServerB_ and set its **RunAsCredential** parameter.</span></span>

<span data-ttu-id="bdb7a-221">Weitere Informationen zur Verwendung von **PSSessionConfiguration** und **RunAs**, um das zweite Hop-Problem zu lösen, finden Sie unter [Eine weitere Lösung für Multi-Hop-PowerShell-Remoting][pssessionconfig].</span><span class="sxs-lookup"><span data-stu-id="bdb7a-221">For information about using **PSSessionConfiguration** and **RunAs** to solve the second hop problem, see [Another solution to multi-hop PowerShell remoting][pssessionconfig].</span></span>

<span data-ttu-id="bdb7a-222">**Vorteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-222">**Pros**</span></span>

- <span data-ttu-id="bdb7a-223">funktioniert mit jedem Server mit WMF 3.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="bdb7a-223">Works with any server with WMF 3.0 or later.</span></span>

<span data-ttu-id="bdb7a-224">**Nachteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-224">**Cons**</span></span>

- <span data-ttu-id="bdb7a-225">erfordert die Konfiguration von **PSSessionConfiguration** und **RunAs** auf jedem Zwischenserver (_ServerB_)</span><span class="sxs-lookup"><span data-stu-id="bdb7a-225">Requires configuration of **PSSessionConfiguration** and **RunAs** on every intermediate server (_ServerB_).</span></span>
- <span data-ttu-id="bdb7a-226">erfordert Kennwortverwaltungsaufgaben bei Verwendung eines Domänen-**RunAs**-Kontos</span><span class="sxs-lookup"><span data-stu-id="bdb7a-226">Requires password maintenance when using a domain **RunAs** account</span></span>

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a><span data-ttu-id="bdb7a-227">Übergeben von Anmeldeinformationen innerhalb eines Invoke-Command-Skriptblocks</span><span class="sxs-lookup"><span data-stu-id="bdb7a-227">Pass credentials inside an Invoke-Command script block</span></span>

<span data-ttu-id="bdb7a-228">Anmeldeinformationen können innerhalb des **ScriptBlock**-Parameters für einen Aufruf des [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command)-Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-228">You can pass credentials inside the **ScriptBlock** parameter of a call to the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>

<span data-ttu-id="bdb7a-229">**Vorteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-229">**Pros**</span></span>

- <span data-ttu-id="bdb7a-230">erfordert keine spezielle Serverkonfiguration</span><span class="sxs-lookup"><span data-stu-id="bdb7a-230">Does not require special server configuration.</span></span>
- <span data-ttu-id="bdb7a-231">funktioniert auf jedem Server mit WMF 2.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="bdb7a-231">Works on any server running WMF 2.0 or later.</span></span>

<span data-ttu-id="bdb7a-232">**Nachteile**</span><span class="sxs-lookup"><span data-stu-id="bdb7a-232">**Cons**</span></span>

- <span data-ttu-id="bdb7a-233">erfordert eine umständliche Codetechnik</span><span class="sxs-lookup"><span data-stu-id="bdb7a-233">Requires an awkward code technique.</span></span>
- <span data-ttu-id="bdb7a-234">Wenn WMF 2.0 ausgeführt wird, wird eine andere Syntax zum Übergeben von Argumenten an eine Remotesitzung benötigt.</span><span class="sxs-lookup"><span data-stu-id="bdb7a-234">If running WMF 2.0, requires different syntax for passing arguments to a remote session.</span></span>

### <a name="example"></a><span data-ttu-id="bdb7a-235">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdb7a-235">Example</span></span>

<span data-ttu-id="bdb7a-236">Das folgende Beispiel zeigt, wie Anmeldeinformationen in einem **Invoke-Command**-Skriptblock übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="bdb7a-236">The following example shows how to pass credentials in an **Invoke-Command** script block:</span></span>

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a><span data-ttu-id="bdb7a-237">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bdb7a-237">See also</span></span>

[<span data-ttu-id="bdb7a-238">Sicherheitsaspekte von PowerShell-Remoting</span><span class="sxs-lookup"><span data-stu-id="bdb7a-238">PowerShell Remoting Security Considerations</span></span>](WinRMSecurity.md)

<!-- link references -->
[blog]: /archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts
[ktools]: /previous-versions/windows/it-pro/windows-server-2003/cc738673(v=ws.10)
[credssp]: /windows/win32/secauthn/credential-security-support-provider
[beware]: https://www.powershellmagazine.com/2014/03/06/accidental-sabotage-beware-of-credssp
[pth]: https://www.microsoft.com/download/details.aspx?id=36036
[credssp-psblog]: https://devblogs.microsoft.com/scripting/enable-powershell-second-hop-functionality-with-credssp/
[whats-new]: /previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831747(v=ws.11)
[kcd2012-1]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-1
[kcd2012-2]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-2
[kcdpaper]: https://aka.ms/kcdpaper
[MS-ADA2]: /openspecs/windows_protocols/ms-ada2/cea4ac11-a4b2-4f2d-84cc-aebb4a4ad405
[MS-SFU]: /openspecs/windows_protocols/ms-sfu/bde93b0e-f3c9-4ddf-9f44-e1453be7af5a
[remote-admin]: /archive/blogs/taylorb/remote-administration-without-constrained-delegation-using-principalsallowedtodelegatetoaccount
[pssessionconfig]: /archive/blogs/sergey_babkins_blog/another-solution-to-multi-hop-powershell-remoting
[protected-users]: /windows-server/security/credentials-protection-and-management/protected-users-security-group
