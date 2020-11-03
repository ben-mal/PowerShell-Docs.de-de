---
description: PowerShell protokolliert interne Vorgänge von der Engine, den Anbietern und den Cmdlets.
keywords: powershell
Locale: en-US
ms.date: 12/14/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging
ms.openlocfilehash: 5d061b38b5b0fa45cf0a86c2f5b7e0efcb8d1f7b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222703"
---
# <a name="about-logging"></a><span data-ttu-id="57780-104">Informationen zur Protokollierung</span><span class="sxs-lookup"><span data-stu-id="57780-104">About Logging</span></span>

## <a name="short-description"></a><span data-ttu-id="57780-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57780-105">Short description</span></span>

<span data-ttu-id="57780-106">PowerShell protokolliert interne Vorgänge von der Engine, den Anbietern und den Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="57780-106">PowerShell logs internal operations from the engine, providers, and cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="57780-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57780-107">Long description</span></span>

<span data-ttu-id="57780-108">PowerShell protokolliert Details zu PowerShell-Vorgängen, z. b. das Starten und Beenden der Engine und Anbieter und das Ausführen von PowerShell-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="57780-108">PowerShell logs details about PowerShell operations, such as starting and stopping the engine and providers, and executing PowerShell commands.</span></span>

> [!NOTE]
> <span data-ttu-id="57780-109">Windows PowerShell-Versionen 3,0, 4,0, 5,0 und 5,1 enthalten **EventLog** -Cmdlets für die Windows-Ereignisprotokolle.</span><span class="sxs-lookup"><span data-stu-id="57780-109">Windows PowerShell versions 3.0, 4.0, 5.0, and 5.1 include **EventLog** cmdlets for the Windows event logs.</span></span> <span data-ttu-id="57780-110">Geben Sie in diesen Versionen Folgendes ein, um die Liste der **EventLog** -Cmdlets anzuzeigen: `Get-Command -Noun EventLog` .</span><span class="sxs-lookup"><span data-stu-id="57780-110">In those versions, to display the list of **EventLog** cmdlets type: `Get-Command -Noun EventLog`.</span></span> <span data-ttu-id="57780-111">Weitere Informationen finden Sie in der Cmdlet-Dokumentation und about_EventLogs für Ihre Version von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57780-111">For more information, see the cmdlet documentation and about_EventLogs for your version of Windows PowerShell.</span></span>

## <a name="viewing-the-powershell-event-log-entries-on-windows"></a><span data-ttu-id="57780-112">Anzeigen der PowerShell-Ereignisprotokoll Einträge unter Windows</span><span class="sxs-lookup"><span data-stu-id="57780-112">Viewing the PowerShell event log entries on Windows</span></span>

<span data-ttu-id="57780-113">PowerShell-Protokolle können mithilfe des Windows-Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="57780-113">PowerShell logs can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="57780-114">Das Ereignisprotokoll befindet sich in der Gruppe Anwendungs-und Dienst Protokolle und hat den Namen `Microsoft-Windows-PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="57780-114">The event log is located in the Application and Services Logs group and is named `Microsoft-Windows-PowerShell`.</span></span> <span data-ttu-id="57780-115">Der zugehörige ETW-Anbieter `GUID` ist `{A0C1853B-5C40-4B15-8766-3CF1C58F985A}` .</span><span class="sxs-lookup"><span data-stu-id="57780-115">The associated ETW provider `GUID` is `{A0C1853B-5C40-4B15-8766-3CF1C58F985A}`.</span></span>

<span data-ttu-id="57780-116">Wenn die Protokollierung von Skript Blöcken aktiviert ist, protokolliert PowerShell die folgenden Ereignisse im `Microsoft-Windows-PowerShell/Operational` Protokoll:</span><span class="sxs-lookup"><span data-stu-id="57780-116">When Script Block Logging is enabled, PowerShell logs the following events to the `Microsoft-Windows-PowerShell/Operational` log:</span></span>

|<span data-ttu-id="57780-117">Feld</span><span class="sxs-lookup"><span data-stu-id="57780-117">Field</span></span>| <span data-ttu-id="57780-118">Wert</span><span class="sxs-lookup"><span data-stu-id="57780-118">Value</span></span>|
|-|-|
|<span data-ttu-id="57780-119">EventId</span><span class="sxs-lookup"><span data-stu-id="57780-119">EventId</span></span>|`4104` / `0x1008`|
|<span data-ttu-id="57780-120">Channel</span><span class="sxs-lookup"><span data-stu-id="57780-120">Channel</span></span>|`Operational`|
|<span data-ttu-id="57780-121">Ebene</span><span class="sxs-lookup"><span data-stu-id="57780-121">Level</span></span>|`Verbose`|
|<span data-ttu-id="57780-122">Opcode</span><span class="sxs-lookup"><span data-stu-id="57780-122">Opcode</span></span>|`Create`|
|<span data-ttu-id="57780-123">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="57780-123">Task</span></span>|`CommandStart`|
|<span data-ttu-id="57780-124">Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="57780-124">Keyword</span></span>|`Runspace`|

## <a name="enabling-script-block-logging"></a><span data-ttu-id="57780-125">Aktivieren der Skript Block Protokollierung</span><span class="sxs-lookup"><span data-stu-id="57780-125">Enabling Script Block Logging</span></span>

<span data-ttu-id="57780-126">Wenn Sie die Skript Block Protokollierung aktivieren, zeichnet PowerShell den Inhalt aller Skriptblöcke auf, die er verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="57780-126">When you enable Script Block Logging, PowerShell records the content of all script blocks that it processes.</span></span> <span data-ttu-id="57780-127">Nach der Aktivierung werden diese Informationen in jeder neuen PowerShell-Sitzung protokolliert.</span><span class="sxs-lookup"><span data-stu-id="57780-127">Once enabled, any new PowerShell session logs this information.</span></span>

> [!NOTE]
> <span data-ttu-id="57780-128">Es wird empfohlen, die Protokollierung geschützter Ereignisse wie unten beschrieben zu aktivieren, wenn Sie die Skript Block Protokollierung für andere Zwecke als Diagnosezwecke verwenden.</span><span class="sxs-lookup"><span data-stu-id="57780-128">It's recommended to enable Protected Event Logging, as described below, when using Script Block Logging for anything other than diagnostics purposes.</span></span>

<span data-ttu-id="57780-129">Die Skript Block Protokollierung kann über Gruppenrichtlinie oder eine Registrierungs Einstellung aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="57780-129">Script Block Logging can be enabled via Group Policy or a registry setting.</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="57780-130">Verwenden von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="57780-130">Using Group Policy</span></span>

<span data-ttu-id="57780-131">Aktivieren Sie zum Aktivieren der automatischen Aufzeichnung die `Turn on PowerShell Script Block
Logging` Funktion in Gruppenrichtlinie `Administrative Templates -> Windows
Components -> Windows PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="57780-131">To enable automatic transcription, enable the `Turn on PowerShell Script Block
Logging` feature in Group Policy through `Administrative Templates -> Windows
Components -> Windows PowerShell`.</span></span>

### <a name="using-the-registry"></a><span data-ttu-id="57780-132">Verwenden der Registrierung</span><span class="sxs-lookup"><span data-stu-id="57780-132">Using the Registry</span></span>

<span data-ttu-id="57780-133">Führen Sie die folgende Funktion aus:</span><span class="sxs-lookup"><span data-stu-id="57780-133">Run the following function:</span></span>

```powershell
function Enable-PSScriptBlockLogging
{
    $basePath = 'HKLM:\Software\Policies\Microsoft\Windows' +
      '\PowerShell\ScriptBlockLogging'

    if(-not (Test-Path $basePath))
    {
        $null = New-Item $basePath -Force
    }

    Set-ItemProperty $basePath -Name EnableScriptBlockLogging -Value "1"
}
```

## <a name="protected-event-logging"></a><span data-ttu-id="57780-134">Protokollierung geschützter Ereignisse</span><span class="sxs-lookup"><span data-stu-id="57780-134">Protected Event Logging</span></span>

<span data-ttu-id="57780-135">Das Erhöhen der Protokollierungsebene auf einem System erhöht die Wahrscheinlichkeit, dass protokollierte Inhalte vertrauliche Daten enthalten können.</span><span class="sxs-lookup"><span data-stu-id="57780-135">Increasing the level of logging on a system increases the possibility that logged content may contain sensitive data.</span></span> <span data-ttu-id="57780-136">Wenn z. b. die Skript Protokollierung aktiviert ist, können Anmelde Informationen oder andere sensible Daten, die von einem Skript verwendet werden, in das Ereignisprotokoll geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="57780-136">For example, with script logging enabled, credentials or other sensitive data used by a script can be written to the event log.</span></span> <span data-ttu-id="57780-137">Wenn ein Computer, auf dem sensible Daten protokolliert wurden, kompromittiert ist, können die Protokolle einem Angreifer Informationen zur Verfügung stellen, die zum Erweitern der Reichweite benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="57780-137">When a machine that has logged sensitive data is compromised, the logs can provide an attacker with information needed to extend their reach.</span></span>

<span data-ttu-id="57780-138">Um diese Informationen zu schützen, führt Windows 10 die Protokollierung geschützter Ereignisse ein.</span><span class="sxs-lookup"><span data-stu-id="57780-138">To protect this information, Windows 10 introduces Protected Event Logging.</span></span>
<span data-ttu-id="57780-139">Durch die Protokollierung geschützter Ereignisse können beteiligte Anwendungen vertrauliche Daten verschlüsseln, die in das Ereignisprotokoll geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="57780-139">Protected Event Logging lets participating applications encrypt sensitive data written to the event log.</span></span> <span data-ttu-id="57780-140">Später können Sie diese Protokolle auf einem sichereren und zentralisierten Protokoll Sammler entschlüsseln und verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="57780-140">Later, you can decrypt and process these logs on a more secure and centralized log collector.</span></span>

<span data-ttu-id="57780-141">Der Inhalt des Ereignis Protokolls wird mithilfe des IETF Cryptographic Message Syntax (CMS)-Standards geschützt.</span><span class="sxs-lookup"><span data-stu-id="57780-141">Event log content is protected using the IETF Cryptographic Message Syntax (CMS) standard.</span></span> <span data-ttu-id="57780-142">CMS verwendet Kryptografie mit öffentlichem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="57780-142">CMS uses public key cryptography.</span></span> <span data-ttu-id="57780-143">Die Schlüssel, die zum Verschlüsseln von Inhalten und Entschlüsseln von Inhalten verwendet werden, werden separat aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="57780-143">The keys used to encrypt content and decrypt content are kept separate.</span></span>

<span data-ttu-id="57780-144">Der öffentliche Schlüssel kann umfassend freigegeben werden, und es handelt sich nicht um vertrauliche Daten.</span><span class="sxs-lookup"><span data-stu-id="57780-144">The public key can be shared widely and isn't sensitive data.</span></span> <span data-ttu-id="57780-145">Alle Inhalte, die mit diesem öffentlichen Schlüssel verschlüsselt sind, können nur mit dem privaten Schlüssel entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="57780-145">Any content encrypted with this public key can only be decrypted by the private key.</span></span> <span data-ttu-id="57780-146">Weitere Informationen zur Kryptografie mit öffentlichem Schlüssel finden Sie unter [Kryptografie mit Wikipedia (Public Key](https://en.wikipedia.org/wiki/Public-key_cryptography)).</span><span class="sxs-lookup"><span data-stu-id="57780-146">For more information about Public Key Cryptography, see [Wikipedia - Public Key Cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).</span></span>

<span data-ttu-id="57780-147">Um eine Richtlinie für die Protokollierung geschützter Ereignisse zu aktivieren, stellen Sie einen öffentlichen Schlüssel für alle Computer bereit, die zu schützende Ereignisprotokoll Daten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="57780-147">To enable a Protected Event Logging policy, deploy a public key to all machines that have event log data to protect.</span></span> <span data-ttu-id="57780-148">Der entsprechende private Schlüssel wird verwendet, um die Ereignisprotokolle an einem sichereren Speicherort, z. b. einem zentralen Ereignisprotokoll Sammler oder einem [Siem][] -Aggregator, zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="57780-148">The corresponding private key is used to post-process the event logs at a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="57780-149">Sie können Siem in Azure einrichten.</span><span class="sxs-lookup"><span data-stu-id="57780-149">You can set up SIEM in Azure.</span></span> <span data-ttu-id="57780-150">Weitere Informationen finden Sie unter [generische Siem-Integration](/cloud-app-security/siem).</span><span class="sxs-lookup"><span data-stu-id="57780-150">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

### <a name="enabling-protected-event-logging-via-group-policy"></a><span data-ttu-id="57780-151">Aktivieren der Protokollierung geschützter Ereignisse über Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="57780-151">Enabling Protected Event Logging via Group Policy</span></span>

<span data-ttu-id="57780-152">Um die Protokollierung geschützter Ereignisse zu aktivieren, aktivieren Sie die `Enable Protected Event Logging` Funktion in Gruppenrichtlinie `Administrative Templates -> Windows Components
-> Event Logging` .</span><span class="sxs-lookup"><span data-stu-id="57780-152">To enable Protected Event Logging, enable the `Enable Protected Event Logging` feature in Group Policy through `Administrative Templates -> Windows Components
-> Event Logging`.</span></span> <span data-ttu-id="57780-153">Diese Einstellung erfordert ein Verschlüsselungs Zertifikat, das Sie in einer von mehreren Formularen bereitstellen können:</span><span class="sxs-lookup"><span data-stu-id="57780-153">This setting requires an encryption certificate, which you can provide in one of several forms:</span></span>

- <span data-ttu-id="57780-154">Der Inhalt eines Base64-codierten X. 509 64-Zertifikats (z. b., wie von der- `Export` Option im Zertifikat-Manager angeboten).</span><span class="sxs-lookup"><span data-stu-id="57780-154">The content of a base-64 encoded X.509 certificate (for example, as offered by the `Export` option in Certificate Manager).</span></span>
- <span data-ttu-id="57780-155">Der Fingerabdruck eines Zertifikats, das sich im Zertifikat Speicher des lokalen Computers befindet (kann von der PKI-Infrastruktur bereitgestellt werden).</span><span class="sxs-lookup"><span data-stu-id="57780-155">The thumbprint of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>
- <span data-ttu-id="57780-156">Der vollständige Pfad zu einem Zertifikat (kann lokal oder eine Remote Freigabe sein).</span><span class="sxs-lookup"><span data-stu-id="57780-156">The full path to a certificate (can be local, or a remote share).</span></span>
- <span data-ttu-id="57780-157">Der Pfad zu einem Verzeichnis, das ein Zertifikat oder Zertifikate enthält (kann lokal oder eine Remote Freigabe sein).</span><span class="sxs-lookup"><span data-stu-id="57780-157">The path to a directory containing a certificate or certificates (can be local, or a remote share).</span></span>
- <span data-ttu-id="57780-158">Der Antragsteller Name eines Zertifikats, das sich im Zertifikat Speicher des lokalen Computers befindet (kann von der PKI-Infrastruktur bereitgestellt werden).</span><span class="sxs-lookup"><span data-stu-id="57780-158">The subject name of a certificate that can be found in the Local Machine certificate store (can be deployed by PKI infrastructure).</span></span>

<span data-ttu-id="57780-159">Das resultierende Zertifikat muss `Document Encryption` als erweiterte Schlüssel Verwendung () verwendet `1.3.6.1.4.1.311.80.1` werden, und entweder die- `Data Encipherment` oder- `Key
Encipherment` Schlüssel Verwendungen sind aktiviert.</span><span class="sxs-lookup"><span data-stu-id="57780-159">The resulting certificate must have `Document Encryption` as an enhanced key usage (`1.3.6.1.4.1.311.80.1`), and either `Data Encipherment` or `Key
Encipherment` key usages enabled.</span></span>

> [!WARNING]
> <span data-ttu-id="57780-160">Der private Schlüssel sollte nicht für die Protokollierungs Ereignisse der Computer bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="57780-160">The private key shouldn't be deployed to the machines logging events.</span></span> <span data-ttu-id="57780-161">Er sollte an einem sicheren Ort aufbewahrt werden, an dem die Nachrichten entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="57780-161">It should be kept in a secure location where you decrypt the messages.</span></span>

### <a name="decrypting-protected-event-logging-messages"></a><span data-ttu-id="57780-162">Entschlüsseln von Meldungen zur Protokollierung geschützter Ereignisse</span><span class="sxs-lookup"><span data-stu-id="57780-162">Decrypting Protected Event Logging messages</span></span>

<span data-ttu-id="57780-163">Das folgende Skript ruft ab und entschlüsselt Sie, wobei angenommen wird, dass Sie über den privaten Schlüssel verfügen:</span><span class="sxs-lookup"><span data-stu-id="57780-163">The following script will retrieve and decrypt, assuming that you have the private key:</span></span>

```powershell
Get-WinEvent Microsoft-Windows-PowerShell/Operational |
  Where-Object Id -eq 4104 | Unprotect-CmsMessage
```

## <a name="see-also"></a><span data-ttu-id="57780-164">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="57780-164">See also</span></span>

[<span data-ttu-id="57780-165">PowerShell-Blue Team</span><span class="sxs-lookup"><span data-stu-id="57780-165">PowerShell the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

[<span data-ttu-id="57780-166">Generische SIEM-Integration</span><span class="sxs-lookup"><span data-stu-id="57780-166">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management
