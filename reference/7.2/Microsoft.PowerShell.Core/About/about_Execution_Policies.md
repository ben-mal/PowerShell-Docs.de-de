---
description: Beschreibt die PowerShell-Ausführungsrichtlinien und erläutert, wie Sie verwaltet werden.
Locale: en-US
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Execution_Policies
ms.openlocfilehash: 1a2b8458b39233f96d47a52e3fea21b31e9b3c42
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599639"
---
# <a name="about-execution-policies"></a><span data-ttu-id="cb214-103">Informationen zu Ausführungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="cb214-103">About Execution Policies</span></span>

## <a name="short-description"></a><span data-ttu-id="cb214-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb214-104">Short Description</span></span>
<span data-ttu-id="cb214-105">Beschreibt die PowerShell-Ausführungsrichtlinien und erläutert, wie Sie verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-105">Describes the PowerShell execution policies and explains how to manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="cb214-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb214-106">Long Description</span></span>

<span data-ttu-id="cb214-107">Die PowerShell-Ausführungs Richtlinie ist ein Sicherheits Feature, mit dem die Bedingungen gesteuert werden, unter denen PowerShell Konfigurationsdateien lädt und Skripts ausführt.</span><span class="sxs-lookup"><span data-stu-id="cb214-107">PowerShell's execution policy is a safety feature that controls the conditions under which PowerShell loads configuration files and runs scripts.</span></span> <span data-ttu-id="cb214-108">Diese Funktion verhindert, dass böswillige Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-108">This feature helps prevent the execution of malicious scripts.</span></span>

<span data-ttu-id="cb214-109">Auf einem Windows-Computer können Sie eine Ausführungs Richtlinie für den lokalen Computer, für den aktuellen Benutzer oder für eine bestimmte Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="cb214-109">On a Windows computer you can set an execution policy for the local computer, for the current user, or for a particular session.</span></span> <span data-ttu-id="cb214-110">Sie können auch eine Gruppenrichtlinie Einstellung verwenden, um Ausführungsrichtlinien für Computer und Benutzer festzulegen.</span><span class="sxs-lookup"><span data-stu-id="cb214-110">You can also use a Group Policy setting to set execution policies for computers and users.</span></span>

<span data-ttu-id="cb214-111">Ausführungsrichtlinien für den lokalen Computer und den aktuellen Benutzer werden in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cb214-111">Execution policies for the local computer and current user are stored in the registry.</span></span> <span data-ttu-id="cb214-112">Sie müssen keine Ausführungsrichtlinien in Ihrem PowerShell-Profil festlegen.</span><span class="sxs-lookup"><span data-stu-id="cb214-112">You don't need to set execution policies in your PowerShell profile.</span></span>
<span data-ttu-id="cb214-113">Die Ausführungs Richtlinie für eine bestimmte Sitzung wird nur im Arbeitsspeicher gespeichert und geht verloren, wenn die Sitzung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="cb214-113">The execution policy for a particular session is stored only in memory and is lost when the session is closed.</span></span>

<span data-ttu-id="cb214-114">Die Ausführungs Richtlinie ist kein Sicherheitssystem, das Benutzeraktionen einschränkt.</span><span class="sxs-lookup"><span data-stu-id="cb214-114">The execution policy isn't a security system that restricts user actions.</span></span> <span data-ttu-id="cb214-115">Beispielsweise können Benutzer eine Richtlinie problemlos umgehen, indem Sie den Skript Inhalt in der Befehlszeile eingeben, wenn Sie ein Skript nicht ausführen können.</span><span class="sxs-lookup"><span data-stu-id="cb214-115">For example, users can easily bypass a policy by typing the script contents at the command line when they cannot run a script.</span></span> <span data-ttu-id="cb214-116">Stattdessen unterstützt die Ausführungs Richtlinie Benutzer beim Festlegen grundlegender Regeln und verhindert, dass Sie unbeabsichtigt gegen Sie verstoßen.</span><span class="sxs-lookup"><span data-stu-id="cb214-116">Instead, the execution policy helps users to set basic rules and prevents them from violating them unintentionally.</span></span>

<span data-ttu-id="cb214-117">Auf nicht-Windows-Computern ist die Standard Ausführungs Richtlinie **uneingeschränkt** und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-117">On non-Windows computers, the default execution policy is **Unrestricted** and cannot be changed.</span></span> <span data-ttu-id="cb214-118">Das `Set-ExecutionPolicy` -Cmdlet ist verfügbar, aber PowerShell zeigt eine Konsolen Meldung an, dass dies nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="cb214-118">The `Set-ExecutionPolicy` cmdlet is available, but PowerShell displays a console message that it's not supported.</span></span> <span data-ttu-id="cb214-119">Obwohl `Get-ExecutionPolicy` bei nicht-Windows-Plattformen **uneingeschränkt** zurückgibt, stimmt das Verhalten tatsächlich mit der **Umgehung** überein, da diese Plattformen die Windows-Sicherheitszonen nicht implementieren.</span><span class="sxs-lookup"><span data-stu-id="cb214-119">While `Get-ExecutionPolicy` returns **Unrestricted** on non-Windows platforms, the behavior really matches **Bypass** because those platforms do not implement the Windows Security Zones.</span></span>

## <a name="powershell-execution-policies"></a><span data-ttu-id="cb214-120">PowerShell-Ausführungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="cb214-120">PowerShell execution policies</span></span>

<span data-ttu-id="cb214-121">Die Durchsetzung dieser Richtlinien erfolgt nur auf Windows-Plattformen.</span><span class="sxs-lookup"><span data-stu-id="cb214-121">Enforcement of these policies only occurs on Windows platforms.</span></span> <span data-ttu-id="cb214-122">Die PowerShell-Ausführungsrichtlinien lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cb214-122">The PowerShell execution policies are as follows:</span></span>

### <a name="allsigned"></a><span data-ttu-id="cb214-123">AllSigned</span><span class="sxs-lookup"><span data-stu-id="cb214-123">AllSigned</span></span>

- <span data-ttu-id="cb214-124">Skripts können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-124">Scripts can run.</span></span>
- <span data-ttu-id="cb214-125">Erfordert, dass alle Skripts und Konfigurationsdateien von einem vertrauenswürdigen Herausgeber signiert sind, einschließlich Skripts, die auf dem lokalen Computer geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-125">Requires that all scripts and configuration files be signed by a trusted publisher, including scripts that you write on the local computer.</span></span>
- <span data-ttu-id="cb214-126">Sie werden vor dem Ausführen von Skripts von Verlegern aufgefordert, die Sie noch nicht als vertrauenswürdig eingestuft haben.</span><span class="sxs-lookup"><span data-stu-id="cb214-126">Prompts you before running scripts from publishers that you haven't yet classified as trusted or untrusted.</span></span>
- <span data-ttu-id="cb214-127">Risiken, die mit signierten, aber bösartigen Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-127">Risks running signed, but malicious, scripts.</span></span>

### <a name="bypass"></a><span data-ttu-id="cb214-128">Umgehung</span><span class="sxs-lookup"><span data-stu-id="cb214-128">Bypass</span></span>

- <span data-ttu-id="cb214-129">Es findet keine Blockierung statt und es werden keine Warnungen oder Eingabeaufforderungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="cb214-129">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="cb214-130">Diese Ausführungs Richtlinie ist für Konfigurationen konzipiert, in denen ein PowerShell-Skript in eine größere Anwendung integriert ist, oder für Konfigurationen, in denen PowerShell die Grundlage für ein Programm ist, das über ein eigenes Sicherheitsmodell verfügt.</span><span class="sxs-lookup"><span data-stu-id="cb214-130">This execution policy is designed for configurations in which a PowerShell script is built in to a larger application or for configurations in which PowerShell is the foundation for a program that has its own security model.</span></span>

### <a name="default"></a><span data-ttu-id="cb214-131">Standard</span><span class="sxs-lookup"><span data-stu-id="cb214-131">Default</span></span>

- <span data-ttu-id="cb214-132">Legt die Standard Ausführungs Richtlinie fest.</span><span class="sxs-lookup"><span data-stu-id="cb214-132">Sets the default execution policy.</span></span>
- <span data-ttu-id="cb214-133">Für Windows-Clients **beschränkt** .</span><span class="sxs-lookup"><span data-stu-id="cb214-133">**Restricted** for Windows clients.</span></span>
- <span data-ttu-id="cb214-134">**RemoteSigned** für Windows-Server.</span><span class="sxs-lookup"><span data-stu-id="cb214-134">**RemoteSigned** for Windows servers.</span></span>

### <a name="remotesigned"></a><span data-ttu-id="cb214-135">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="cb214-135">RemoteSigned</span></span>

- <span data-ttu-id="cb214-136">Die Standard Ausführungs Richtlinie für Windows Server-Computer.</span><span class="sxs-lookup"><span data-stu-id="cb214-136">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="cb214-137">Skripts können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-137">Scripts can run.</span></span>
- <span data-ttu-id="cb214-138">Erfordert eine digitale Signatur von einem vertrauenswürdigen Herausgeber für Skripts und Konfigurationsdateien, die aus dem Internet heruntergeladen werden, einschließlich e-Mail-und Instant Messaging-Programme.</span><span class="sxs-lookup"><span data-stu-id="cb214-138">Requires a digital signature from a trusted publisher on scripts and configuration files that are downloaded from the internet which includes email and instant messaging programs.</span></span>
- <span data-ttu-id="cb214-139">Erfordert keine digitalen Signaturen für Skripts, die auf dem lokalen Computer geschrieben und nicht aus dem Internet heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="cb214-139">Doesn't require digital signatures on scripts that are written on the local computer and not downloaded from the internet.</span></span>
- <span data-ttu-id="cb214-140">Führt Skripts aus, die aus dem Internet heruntergeladen und nicht signiert sind, wenn die Blockierung der Skripts aufgehoben wird, z. b. mithilfe des- `Unblock-File` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="cb214-140">Runs scripts that are downloaded from the internet and not signed, if the scripts are unblocked, such as by using the `Unblock-File` cmdlet.</span></span>
- <span data-ttu-id="cb214-141">Risiken bei der Ausführung nicht signierter Skripts aus anderen Quellen als dem Internet und signierten Skripts, die bösartig sein könnten.</span><span class="sxs-lookup"><span data-stu-id="cb214-141">Risks running unsigned scripts from sources other than the internet and signed scripts that could be malicious.</span></span>

### <a name="restricted"></a><span data-ttu-id="cb214-142">Eingeschränkt</span><span class="sxs-lookup"><span data-stu-id="cb214-142">Restricted</span></span>

- <span data-ttu-id="cb214-143">Die Standard Ausführungs Richtlinie für Windows-Client Computer.</span><span class="sxs-lookup"><span data-stu-id="cb214-143">The default execution policy for Windows client computers.</span></span>
- <span data-ttu-id="cb214-144">Lässt einzelne Befehle zu, erlaubt aber keine Skripts.</span><span class="sxs-lookup"><span data-stu-id="cb214-144">Permits individual commands, but does not allow scripts.</span></span>
- <span data-ttu-id="cb214-145">Verhindert die Ausführung aller Skriptdateien, einschließlich Formatierungs-und Konfigurationsdateien ( `.ps1xml` ), Modul Skriptdateien ( `.psm1` ) und PowerShell-Profilen ( `.ps1` ).</span><span class="sxs-lookup"><span data-stu-id="cb214-145">Prevents running of all script files, including formatting and configuration files (`.ps1xml`), module script files (`.psm1`), and PowerShell profiles (`.ps1`).</span></span>

### <a name="undefined"></a><span data-ttu-id="cb214-146">Nicht definiert</span><span class="sxs-lookup"><span data-stu-id="cb214-146">Undefined</span></span>

- <span data-ttu-id="cb214-147">Im aktuellen Bereich ist keine Ausführungs Richtlinie festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cb214-147">There is no execution policy set in the current scope.</span></span>
- <span data-ttu-id="cb214-148">Wenn die Ausführungs Richtlinie in allen Bereichen nicht **definiert** ist, ist die effektive Ausführungs Richtlinie für Windows-Clients und **RemoteSigned** für Windows Server **beschränkt** .</span><span class="sxs-lookup"><span data-stu-id="cb214-148">If the execution policy in all scopes is **Undefined**, the effective execution policy is **Restricted** for Windows clients and **RemoteSigned** for Windows Server.</span></span>

### <a name="unrestricted"></a><span data-ttu-id="cb214-149">Nicht eingeschränkt</span><span class="sxs-lookup"><span data-stu-id="cb214-149">Unrestricted</span></span>

- <span data-ttu-id="cb214-150">Die Standard Ausführungs Richtlinie für nicht-Windows-Computer und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-150">The default execution policy for non-Windows computers and cannot be changed.</span></span>
- <span data-ttu-id="cb214-151">Nicht signierte Skripts können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-151">Unsigned scripts can run.</span></span> <span data-ttu-id="cb214-152">Es besteht das Risiko, bösartige Skripts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cb214-152">There is a risk of running malicious scripts.</span></span>
- <span data-ttu-id="cb214-153">Warnt den Benutzer vor dem Ausführen von Skripts und Konfigurationsdateien, die nicht in der lokalen Intranetzone sind.</span><span class="sxs-lookup"><span data-stu-id="cb214-153">Warns the user before running scripts and configuration files that are not from the local intranet zone.</span></span>

> [!NOTE]
> <span data-ttu-id="cb214-154">Auf Systemen, die Universal Naming Convention (UNC)-Pfade nicht von Internet Pfaden unterscheiden, dürfen Skripts, die von einem UNC-Pfad identifiziert werden, möglicherweise nicht mit der **RemoteSigned** -Ausführungs Richtlinie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-154">On systems that do not distinguish Universal Naming Convention (UNC) paths from internet paths, scripts that are identified by a UNC path might not be permitted to run with the **RemoteSigned** execution policy.</span></span>

## <a name="execution-policy-scope"></a><span data-ttu-id="cb214-155">Ausführungsrichtlinien Bereich</span><span class="sxs-lookup"><span data-stu-id="cb214-155">Execution policy scope</span></span>

<span data-ttu-id="cb214-156">Sie können eine Ausführungs Richtlinie festlegen, die nur in einem bestimmten Bereich wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="cb214-156">You can set an execution policy that is effective only in a particular scope.</span></span>

<span data-ttu-id="cb214-157">Gültige Werte für den **Bereich** sind " **MachinePolicy**", " **UserPolicy**", " **Process**", " **CurrentUser**" und " **LocalMachine**".</span><span class="sxs-lookup"><span data-stu-id="cb214-157">The valid values for **Scope** are **MachinePolicy**, **UserPolicy**, **Process**, **CurrentUser**, and **LocalMachine**.</span></span> <span data-ttu-id="cb214-158">**LocalMachine** ist die Standardeinstellung, wenn eine Ausführungs Richtlinie festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="cb214-158">**LocalMachine** is the default when setting an execution policy.</span></span>

<span data-ttu-id="cb214-159">Die **Bereichs** Werte werden in der Reihenfolge der Rangfolge aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="cb214-159">The **Scope** values are listed in precedence order.</span></span> <span data-ttu-id="cb214-160">Die Richtlinie, die Vorrang hat, ist in der aktuellen Sitzung wirksam, auch wenn eine restriktivere Richtlinie mit einer niedrigeren Rangfolge festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb214-160">The policy that takes precedence is effective in the current session, even if a more restrictive policy was set at a lower level of precedence.</span></span>

<span data-ttu-id="cb214-161">Weitere Informationen finden Sie unter [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span><span class="sxs-lookup"><span data-stu-id="cb214-161">For more information, see [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span></span>

### <a name="machinepolicy"></a><span data-ttu-id="cb214-162">MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="cb214-162">MachinePolicy</span></span>

<span data-ttu-id="cb214-163">Wird von einem Gruppenrichtlinie für alle Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cb214-163">Set by a Group Policy for all users of the computer.</span></span>

### <a name="userpolicy"></a><span data-ttu-id="cb214-164">UserPolicy</span><span class="sxs-lookup"><span data-stu-id="cb214-164">UserPolicy</span></span>

<span data-ttu-id="cb214-165">Wird von einem Gruppenrichtlinie für den aktuellen Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cb214-165">Set by a Group Policy for the current user of the computer.</span></span>

### <a name="process"></a><span data-ttu-id="cb214-166">Prozess</span><span class="sxs-lookup"><span data-stu-id="cb214-166">Process</span></span>

<span data-ttu-id="cb214-167">Der **Prozess** Bereich wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="cb214-167">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="cb214-168">Die Ausführungs Richtlinie wird in der-Umgebungsvariablen und `$env:PSExecutionPolicyPreference` nicht in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cb214-168">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="cb214-169">Wenn die PowerShell-Sitzung geschlossen ist, werden die Variable und der Wert gelöscht.</span><span class="sxs-lookup"><span data-stu-id="cb214-169">When the PowerShell session is closed, the variable and value are deleted.</span></span>

### <a name="currentuser"></a><span data-ttu-id="cb214-170">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="cb214-170">CurrentUser</span></span>

<span data-ttu-id="cb214-171">Die Ausführungsrichtlinie wirkt sich nur auf den aktuellen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="cb214-171">The execution policy affects only the current user.</span></span> <span data-ttu-id="cb214-172">Sie wird im Registrierungs Unterschlüssel **HKEY_CURRENT_USER** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cb214-172">It's stored in the **HKEY_CURRENT_USER** registry subkey.</span></span>

### <a name="localmachine"></a><span data-ttu-id="cb214-173">LocalMachine</span><span class="sxs-lookup"><span data-stu-id="cb214-173">LocalMachine</span></span>

<span data-ttu-id="cb214-174">Die Ausführungs Richtlinie wirkt sich auf alle Benutzer des aktuellen Computers aus.</span><span class="sxs-lookup"><span data-stu-id="cb214-174">The execution policy affects all users on the current computer.</span></span> <span data-ttu-id="cb214-175">Sie wird im Registrierungs Unterschlüssel **HKEY_LOCAL_MACHINE** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cb214-175">It's stored in the **HKEY_LOCAL_MACHINE** registry subkey.</span></span>

## <a name="managing-the-execution-policy-with-powershell"></a><span data-ttu-id="cb214-176">Verwalten der Ausführungs Richtlinie mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb214-176">Managing the execution policy with PowerShell</span></span>

<span data-ttu-id="cb214-177">Verwenden Sie das-Cmdlet, um die effektive Ausführungs Richtlinie für die aktuelle PowerShell-Sitzung zu erhalten `Get-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="cb214-177">To get the effective execution policy for the current PowerShell session, use the `Get-ExecutionPolicy` cmdlet.</span></span>

<span data-ttu-id="cb214-178">Mit dem folgenden Befehl wird die effektive Ausführungs Richtlinie abgerufen:</span><span class="sxs-lookup"><span data-stu-id="cb214-178">The following command gets the effective execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="cb214-179">So erhalten Sie alle Ausführungsrichtlinien, die sich auf die aktuelle Sitzung auswirken, und zeigen Sie in der Rangfolge an:</span><span class="sxs-lookup"><span data-stu-id="cb214-179">To get all of the execution policies that affect the current session and display them in precedence order:</span></span>

```powershell
Get-ExecutionPolicy -List
```

<span data-ttu-id="cb214-180">Das Ergebnis sieht in etwa wie in der folgenden Beispielausgabe aus:</span><span class="sxs-lookup"><span data-stu-id="cb214-180">The result looks similar to the following sample output:</span></span>

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       AllSigned
```

<span data-ttu-id="cb214-181">In diesem Fall ist die effektive Ausführungs Richtlinie **RemoteSigned** , da die Ausführungs Richtlinie für den aktuellen Benutzer Vorrang vor der für den lokalen Computer festgelegten Ausführungs Richtlinie hat.</span><span class="sxs-lookup"><span data-stu-id="cb214-181">In this case, the effective execution policy is **RemoteSigned** because the execution policy for the current user takes precedence over the execution policy set for the local computer.</span></span>

<span data-ttu-id="cb214-182">Um die Ausführungs Richtlinie für einen bestimmten Bereich zu erhalten, verwenden Sie den **Scope** -Parameter von `Get-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="cb214-182">To get the execution policy set for a particular scope, use the **Scope** parameter of `Get-ExecutionPolicy`.</span></span>

<span data-ttu-id="cb214-183">Mit dem folgenden Befehl wird z. b. die Ausführungs Richtlinie für den Bereich **CurrentUser** abgerufen:</span><span class="sxs-lookup"><span data-stu-id="cb214-183">For example, the following command gets the execution policy for the **CurrentUser** scope:</span></span>

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

### <a name="change-the-execution-policy"></a><span data-ttu-id="cb214-184">Ändern der Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cb214-184">Change the execution policy</span></span>

<span data-ttu-id="cb214-185">Verwenden Sie das-Cmdlet, um die PowerShell-Ausführungs Richtlinie auf dem Windows-Computer zu ändern `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="cb214-185">To change the PowerShell execution policy on your Windows computer, use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="cb214-186">Die Änderung wird sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="cb214-186">The change is effective immediately.</span></span> <span data-ttu-id="cb214-187">PowerShell muss nicht neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-187">You don't need to restart PowerShell.</span></span>

<span data-ttu-id="cb214-188">Wenn Sie die Ausführungs Richtlinie für die Bereiche **LocalMachine** oder **CurrentUser** festlegen, wird die Änderung in der Registrierung gespeichert und bleibt wirksam, bis Sie Sie wieder ändern.</span><span class="sxs-lookup"><span data-stu-id="cb214-188">If you set the execution policy for the scopes **LocalMachine** or the **CurrentUser**, the change is saved in the registry and remains effective until you change it again.</span></span>

<span data-ttu-id="cb214-189">Wenn Sie die Ausführungs Richtlinie für den **Prozess** Bereich festlegen, wird diese nicht in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cb214-189">If you set the execution policy for the **Process** scope, it's not saved in the registry.</span></span> <span data-ttu-id="cb214-190">Die Ausführungs Richtlinie wird so lange beibehalten, bis der aktuelle Prozess und alle untergeordneten Prozesse geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-190">The execution policy is retained until the current process and any child processes are closed.</span></span>

> [!NOTE]
> <span data-ttu-id="cb214-191">Starten Sie in Windows Vista und höheren Versionen von Windows PowerShell mit der Option **als Administrator ausführen** , um Befehle auszuführen, mit denen die Ausführungs Richtlinie für den lokalen Computer, den Bereich **LocalMachine** , geändert wird.</span><span class="sxs-lookup"><span data-stu-id="cb214-191">In Windows Vista and later versions of Windows, to run commands that change the execution policy for the local computer, **LocalMachine** scope, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="cb214-192">So ändern Sie die Ausführungs Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="cb214-192">To change your execution policy:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName>
```

<span data-ttu-id="cb214-193">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cb214-193">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="cb214-194">So legen Sie die Ausführungs Richtlinie in einem bestimmten Bereich fest:</span><span class="sxs-lookup"><span data-stu-id="cb214-194">To set the execution policy in a particular scope:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName> -Scope <scope>
```

<span data-ttu-id="cb214-195">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cb214-195">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

<span data-ttu-id="cb214-196">Ein Befehl zum Ändern einer Ausführungs Richtlinie kann erfolgreich sein, aber die effektive Ausführungs Richtlinie trotzdem nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="cb214-196">A command to change an execution policy can succeed but still not change the effective execution policy.</span></span>

<span data-ttu-id="cb214-197">Beispielsweise kann ein Befehl, mit dem die Ausführungs Richtlinie für den lokalen Computer festgelegt wird, erfolgreich ausgeführt, aber von der Ausführungs Richtlinie für den aktuellen Benutzer überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cb214-197">For example, a command that sets the execution policy for the local computer can succeed but be overridden by the execution policy for the current user.</span></span>

### <a name="remove-the-execution-policy"></a><span data-ttu-id="cb214-198">Entfernen der Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cb214-198">Remove the execution policy</span></span>

<span data-ttu-id="cb214-199">Um die Ausführungs Richtlinie für einen bestimmten Bereich zu entfernen, legen Sie die Ausführungs Richtlinie auf "nicht **definiert**" fest.</span><span class="sxs-lookup"><span data-stu-id="cb214-199">To remove the execution policy for a particular scope, set the execution policy to **Undefined**.</span></span>

<span data-ttu-id="cb214-200">So entfernen Sie beispielsweise die Ausführungs Richtlinie für alle Benutzer des lokalen Computers:</span><span class="sxs-lookup"><span data-stu-id="cb214-200">For example, to remove the execution policy for all the users of the local computer:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope LocalMachine
```

<span data-ttu-id="cb214-201">So entfernen Sie die Ausführungs Richtlinie für einen **Bereich**:</span><span class="sxs-lookup"><span data-stu-id="cb214-201">To remove the execution policy for a **Scope**:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
```

<span data-ttu-id="cb214-202">Wenn in keinem Bereich eine Ausführungs Richtlinie festgelegt ist, wird die effektive Ausführungs Richtlinie **eingeschränkt**. Dies ist die Standardeinstellung für Windows-Clients.</span><span class="sxs-lookup"><span data-stu-id="cb214-202">If no execution policy is set in any scope, the effective execution policy is **Restricted**, which is the default for Windows clients.</span></span>

### <a name="set-a-different-policy-for-one-session"></a><span data-ttu-id="cb214-203">Festlegen einer anderen Richtlinie für eine Sitzung</span><span class="sxs-lookup"><span data-stu-id="cb214-203">Set a different policy for one session</span></span>

<span data-ttu-id="cb214-204">Sie können den **ExecutionPolicy** -Parameter von **pwsh.exe** verwenden, um eine Ausführungs Richtlinie für eine neue PowerShell-Sitzung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="cb214-204">You can use the **ExecutionPolicy** parameter of **pwsh.exe** to set an execution policy for a new PowerShell session.</span></span> <span data-ttu-id="cb214-205">Die Richtlinie wirkt sich nur auf die aktuelle Sitzung und untergeordnete Sitzungen aus.</span><span class="sxs-lookup"><span data-stu-id="cb214-205">The policy affects only the current session and child sessions.</span></span>

<span data-ttu-id="cb214-206">Um die Ausführungs Richtlinie für eine neue Sitzung festzulegen, starten Sie PowerShell in der Befehlszeile, z. b. **cmd.exe** oder PowerShell, und verwenden Sie dann den **ExecutionPolicy** -Parameter von **pwsh.exe** , um die Ausführungs Richtlinie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="cb214-206">To set the execution policy for a new session, start PowerShell at the command line, such as **cmd.exe** or from PowerShell, and then use the **ExecutionPolicy** parameter of **pwsh.exe** to set the execution policy.</span></span>

<span data-ttu-id="cb214-207">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cb214-207">For example:</span></span>

```powershell
pwsh.exe -ExecutionPolicy AllSigned
```

<span data-ttu-id="cb214-208">Die von Ihnen festgelegte Ausführungs Richtlinie ist nicht in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cb214-208">The execution policy that you set isn't stored in the registry.</span></span> <span data-ttu-id="cb214-209">Stattdessen wird Sie in der `$env:PSExecutionPolicyPreference` Umgebungsvariablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cb214-209">Instead, it's stored in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="cb214-210">Die Variable wird gelöscht, wenn Sie die Sitzung schließen, in der die Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cb214-210">The variable is deleted when you close the session in which the policy is set.</span></span> <span data-ttu-id="cb214-211">Sie können die Richtlinie nicht ändern, indem Sie den Variablen Wert bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="cb214-211">You cannot change the policy by editing the variable value.</span></span>

<span data-ttu-id="cb214-212">Während der Sitzung hat die Ausführungs Richtlinie, die für die Sitzung festgelegt ist, Vorrang vor einer Ausführungs Richtlinie, die in der Registrierung für den lokalen Computer oder den aktuellen Benutzer festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cb214-212">During the session, the execution policy that is set for the session takes precedence over an execution policy that is set in the registry for the local computer or current user.</span></span> <span data-ttu-id="cb214-213">Sie hat jedoch keinen Vorrang vor der Ausführungs Richtlinie, die mithilfe eines Gruppenrichtlinie festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb214-213">However, it doesn't take precedence over the execution policy set by using a Group Policy.</span></span>

## <a name="use-group-policy-to-manage-execution-policy"></a><span data-ttu-id="cb214-214">Verwalten der Ausführungs Richtlinie mit Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cb214-214">Use Group Policy to Manage Execution Policy</span></span>

<span data-ttu-id="cb214-215">Sie können die Einstellung **Skriptausführung Gruppenrichtlinie aktivieren** verwenden, um die Ausführungs Richtlinie von Computern in Ihrem Unternehmen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="cb214-215">You can use the **Turn on Script Execution** Group Policy setting to manage the execution policy of computers in your enterprise.</span></span> <span data-ttu-id="cb214-216">Die Gruppenrichtlinie Einstellung überschreibt die Ausführungsrichtlinien, die in PowerShell in allen Bereichen festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="cb214-216">The Group Policy setting overrides the execution policies set in PowerShell in all scopes.</span></span>

<span data-ttu-id="cb214-217">Die Richtlinien Einstellungen **für die Skriptausführung aktivieren** lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cb214-217">The **Turn on Script Execution** policy settings are as follows:</span></span>

- <span data-ttu-id="cb214-218">Wenn Sie die **Ausführung der Skriptausführung** deaktivieren, werden Skripts nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cb214-218">If you disable **Turn on Script Execution**, scripts do not run.</span></span> <span data-ttu-id="cb214-219">Dies entspricht der **eingeschränkten** Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="cb214-219">This is equivalent to the **Restricted** execution policy.</span></span>
- <span data-ttu-id="cb214-220">Wenn Sie die Option **Skriptausführung** aktivieren aktivieren, können Sie eine Ausführungs Richtlinie auswählen.</span><span class="sxs-lookup"><span data-stu-id="cb214-220">If you enable **Turn on Script Execution**, you can select an execution policy.</span></span> <span data-ttu-id="cb214-221">Die Gruppenrichtlinie Einstellungen entsprechen den folgenden Einstellungen für die Ausführungs Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="cb214-221">The Group Policy settings are equivalent to the following execution policy settings:</span></span>

  | <span data-ttu-id="cb214-222">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cb214-222">Group Policy</span></span>                                  | <span data-ttu-id="cb214-223">Ausführungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cb214-223">Execution Policy</span></span> |
  | --------------------------------------------- | ---------------- |
  | <span data-ttu-id="cb214-224">Alle Skripts zulassen</span><span class="sxs-lookup"><span data-stu-id="cb214-224">Allow all scripts</span></span>                             | <span data-ttu-id="cb214-225">Nicht eingeschränkt</span><span class="sxs-lookup"><span data-stu-id="cb214-225">Unrestricted</span></span>     |
  | <span data-ttu-id="cb214-226">Lokale Skripts und Remote signierte Skripts zulassen</span><span class="sxs-lookup"><span data-stu-id="cb214-226">Allow local scripts and remote signed scripts</span></span> | <span data-ttu-id="cb214-227">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="cb214-227">RemoteSigned</span></span>     |
  | <span data-ttu-id="cb214-228">Nur signierte Skripts zulassen</span><span class="sxs-lookup"><span data-stu-id="cb214-228">Allow only signed scripts</span></span>                     | <span data-ttu-id="cb214-229">AllSigned</span><span class="sxs-lookup"><span data-stu-id="cb214-229">AllSigned</span></span>        |

- <span data-ttu-id="cb214-230">Wenn die Option **Skriptausführung aktivieren** nicht konfiguriert ist, hat dies keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="cb214-230">If **Turn on Script Execution** is not configured, it has no effect.</span></span> <span data-ttu-id="cb214-231">Die in PowerShell festgelegte Ausführungs Richtlinie ist gültig.</span><span class="sxs-lookup"><span data-stu-id="cb214-231">The execution policy set in PowerShell is effective.</span></span>

<span data-ttu-id="cb214-232">Die Dateien "powershellexecutionpolicy. adm" und "powershellexecutionpolicy. ADMX" fügen die Richtlinie zum **Aktivieren der Skriptausführung** zu den Knoten "Computer Konfiguration" und "Benutzerkonfiguration" in Gruppenrichtlinie Editor in den folgenden Pfaden hinzu.</span><span class="sxs-lookup"><span data-stu-id="cb214-232">The PowerShellExecutionPolicy.adm and PowerShellExecutionPolicy.admx files add the **Turn on Script Execution** policy to the Computer Configuration and User Configuration nodes in Group Policy Editor in the following paths.</span></span>

<span data-ttu-id="cb214-233">Für Windows XP und Windows Server 2003:</span><span class="sxs-lookup"><span data-stu-id="cb214-233">For Windows XP and Windows Server 2003:</span></span>

<span data-ttu-id="cb214-234">Administrative Vorlagen\Windows-komponents\windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb214-234">Administrative Templates\Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="cb214-235">Für Windows Vista und spätere Versionen von Windows:</span><span class="sxs-lookup"><span data-stu-id="cb214-235">For Windows Vista and later versions of Windows:</span></span>

<span data-ttu-id="cb214-236">Administrative vorlagen\classic administrative Vorlagen </span><span class="sxs-lookup"><span data-stu-id="cb214-236">Administrative Templates\Classic Administrative Templates</span></span>\
<span data-ttu-id="cb214-237">Windows-Komponenten \ Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb214-237">Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="cb214-238">Im Knoten Computer Konfiguration festgelegte Richtlinien haben Vorrang vor den Richtlinien, die im Knoten Benutzerkonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="cb214-238">Policies set in the Computer Configuration node take precedence over policies set in the User Configuration node.</span></span>

<span data-ttu-id="cb214-239">Weitere Informationen finden Sie unter [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="cb214-239">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

### <a name="execution-policy-precedence"></a><span data-ttu-id="cb214-240">Rangfolge der Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cb214-240">Execution policy precedence</span></span>

<span data-ttu-id="cb214-241">Wenn Sie die effektive Ausführungs Richtlinie für eine Sitzung ermitteln, wertet PowerShell die Ausführungsrichtlinien in der folgenden Reihenfolge aus:</span><span class="sxs-lookup"><span data-stu-id="cb214-241">When determining the effective execution policy for a session, PowerShell evaluates the execution policies in the following precedence order:</span></span>

- <span data-ttu-id="cb214-242">Gruppenrichtlinie: MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="cb214-242">Group Policy: MachinePolicy</span></span>
- <span data-ttu-id="cb214-243">Gruppenrichtlinie: UserPolicy</span><span class="sxs-lookup"><span data-stu-id="cb214-243">Group Policy: UserPolicy</span></span>
- <span data-ttu-id="cb214-244">Ausführungs Richtlinie: Prozess (oder `pwsh.exe -ExecutionPolicy` )</span><span class="sxs-lookup"><span data-stu-id="cb214-244">Execution Policy: Process (or `pwsh.exe -ExecutionPolicy`)</span></span>
- <span data-ttu-id="cb214-245">Ausführungs Richtlinie: CurrentUser</span><span class="sxs-lookup"><span data-stu-id="cb214-245">Execution Policy: CurrentUser</span></span>
- <span data-ttu-id="cb214-246">Ausführungs Richtlinie: LocalMachine</span><span class="sxs-lookup"><span data-stu-id="cb214-246">Execution Policy: LocalMachine</span></span>

## <a name="manage-signed-and-unsigned-scripts"></a><span data-ttu-id="cb214-247">Verwalten von signierten und nicht signierten Skripts</span><span class="sxs-lookup"><span data-stu-id="cb214-247">Manage signed and unsigned scripts</span></span>

<span data-ttu-id="cb214-248">In Windows fügen Programme wie Internet Explorer und Microsoft Edge Dateien, die heruntergeladen werden, einen alternativen Datenstrom hinzu.</span><span class="sxs-lookup"><span data-stu-id="cb214-248">In Windows, programs like Internet Explorer and Microsoft Edge add an alternate data stream to files that are downloaded.</span></span> <span data-ttu-id="cb214-249">Dadurch wird die Datei als "aus dem Internet über das Internet" markiert.</span><span class="sxs-lookup"><span data-stu-id="cb214-249">This marks the file as "coming from the Internet".</span></span> <span data-ttu-id="cb214-250">Wenn Ihre PowerShell-Ausführungs Richtlinie **RemoteSigned** ist, führt PowerShell keine nicht signierten Skripts aus, die aus dem Internet heruntergeladen werden, einschließlich e-Mail-und Instant Messaging-Programme.</span><span class="sxs-lookup"><span data-stu-id="cb214-250">If your PowerShell execution policy is **RemoteSigned**, PowerShell won't run unsigned scripts that are downloaded from the internet which includes email and instant messaging programs.</span></span>

<span data-ttu-id="cb214-251">Sie können das Skript signieren oder ein nicht signiertes Skript ausführen, ohne die Ausführungs Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cb214-251">You can sign the script or elect to run an unsigned script without changing the execution policy.</span></span>

<span data-ttu-id="cb214-252">Ab PowerShell 3,0 können Sie den **Stream** -Parameter des `Get-Item` Cmdlets verwenden, um Dateien zu erkennen, die blockiert werden, weil Sie aus dem Internet heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="cb214-252">Beginning in PowerShell 3.0, you can use the **Stream** parameter of the `Get-Item` cmdlet to detect files that are blocked because they were downloaded from the internet.</span></span> <span data-ttu-id="cb214-253">Verwenden Sie das `Unblock-File` Cmdlet, um die Blockierung der Skripts aufzulösen, damit Sie Sie in PowerShell ausführen können.</span><span class="sxs-lookup"><span data-stu-id="cb214-253">Use the `Unblock-File` cmdlet to unblock the scripts so that you can run them in PowerShell.</span></span>

<span data-ttu-id="cb214-254">Weitere Informationen finden Sie unter [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)und [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span><span class="sxs-lookup"><span data-stu-id="cb214-254">For more information, see [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item), and [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span></span>

> [!NOTE]
> <span data-ttu-id="cb214-255">Andere Methoden zum Herunterladen von Dateien dürfen die Dateien nicht als aus der Internet Zone stammende Dateien markieren.</span><span class="sxs-lookup"><span data-stu-id="cb214-255">Other methods of downloading files may not mark the files as coming from the Internet Zone.</span></span> <span data-ttu-id="cb214-256">Beispiele hierfür sind:</span><span class="sxs-lookup"><span data-stu-id="cb214-256">Some examples include:</span></span>
>
> - `curl.exe`
> - `Invoke-RestMethod`
> - `Invoke-WebRequest`

## <a name="execution-policy-on-windows-server-core-and-window-nano-server"></a><span data-ttu-id="cb214-257">Ausführungs Richtlinie für Windows Server Core und Windows Nano Server</span><span class="sxs-lookup"><span data-stu-id="cb214-257">Execution policy on Windows Server Core and Window Nano Server</span></span>

<span data-ttu-id="cb214-258">Wenn PowerShell 6 unter bestimmten Bedingungen unter Windows Server Core oder Windows Nano Server ausgeführt wird, können Ausführungsrichtlinien mit dem folgenden Fehler fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="cb214-258">When PowerShell 6 is run on Windows Server Core or Windows Nano Server under certain conditions, execution policies can fail with the following error:</span></span>

```Output
AuthorizationManager check failed.
At line:1 char:1
+ C:\scriptpath\scriptname.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="cb214-259">PowerShell verwendet APIs in der Windows-Desktopshell ( `explorer.exe` ), um die Zone einer Skriptdatei zu validieren.</span><span class="sxs-lookup"><span data-stu-id="cb214-259">PowerShell uses APIs in the Windows Desktop Shell (`explorer.exe`) to validate the Zone of a script file.</span></span> <span data-ttu-id="cb214-260">Die Windows-Shell ist unter Windows Server Core und Windows Nano Server nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cb214-260">The Windows Shell is not available on Windows Server Core and Windows Nano Server.</span></span>

<span data-ttu-id="cb214-261">Dieser Fehler kann auch bei jedem Windows-System angezeigt werden, wenn die Windows-Desktopshell nicht verfügbar ist oder nicht reagiert.</span><span class="sxs-lookup"><span data-stu-id="cb214-261">You could also get this error on any Windows system if the Windows Desktop Shell is unavailable or unresponsive.</span></span> <span data-ttu-id="cb214-262">Beispielsweise kann während der Anmeldung die Ausführung eines PowerShell-Anmelde Skripts gestartet werden, bevor der Windows-Desktop bereit ist, was zu einem Fehler führt.</span><span class="sxs-lookup"><span data-stu-id="cb214-262">For example, during sign on, a PowerShell logon script could start execution before the Windows Desktop is ready, resulting in failure.</span></span>

<span data-ttu-id="cb214-263">Die Verwendung einer Ausführungs Richtlinie von **Bypass** oder **AllSigned** erfordert keine Zonen Überprüfung, um das Problem zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="cb214-263">Using an execution policy of **ByPass** or **AllSigned** does not require a Zone check which avoids the problem.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb214-264">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb214-264">See Also</span></span>

[<span data-ttu-id="cb214-265">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="cb214-265">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="cb214-266">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="cb214-266">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="cb214-267">about_Signing</span><span class="sxs-lookup"><span data-stu-id="cb214-267">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="cb214-268">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="cb214-268">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="cb214-269">Get-Item</span><span class="sxs-lookup"><span data-stu-id="cb214-269">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

[<span data-ttu-id="cb214-270">Hilfe zur pwsh-Konsole</span><span class="sxs-lookup"><span data-stu-id="cb214-270">Pwsh Console Help</span></span>](about_pwsh.md)

[<span data-ttu-id="cb214-271">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="cb214-271">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="cb214-272">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="cb214-272">Unblock-File</span></span>](xref:Microsoft.PowerShell.Utility.Unblock-File)

