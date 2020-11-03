---
description: Beschreibt die PowerShell-Ausführungsrichtlinien und erläutert, wie Sie verwaltet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Execution_Policies
ms.openlocfilehash: 3332adb76c76fa644d23060abe2af43bd45a15a6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223511"
---
# <a name="about-execution-policies"></a><span data-ttu-id="00785-104">Informationen zu Ausführungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="00785-104">About Execution Policies</span></span>

## <a name="short-description"></a><span data-ttu-id="00785-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00785-105">Short Description</span></span>

<span data-ttu-id="00785-106">Beschreibt die PowerShell-Ausführungsrichtlinien und erläutert, wie Sie verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="00785-106">Describes the PowerShell execution policies and explains how to manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="00785-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00785-107">Long Description</span></span>

<span data-ttu-id="00785-108">Die PowerShell-Ausführungs Richtlinie ist ein Sicherheits Feature, mit dem die Bedingungen gesteuert werden, unter denen PowerShell Konfigurationsdateien lädt und Skripts ausführt.</span><span class="sxs-lookup"><span data-stu-id="00785-108">PowerShell's execution policy is a safety feature that controls the conditions under which PowerShell loads configuration files and runs scripts.</span></span> <span data-ttu-id="00785-109">Diese Funktion verhindert, dass böswillige Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00785-109">This feature helps prevent the execution of malicious scripts.</span></span>

<span data-ttu-id="00785-110">Auf einem Windows-Computer können Sie eine Ausführungs Richtlinie für den lokalen Computer, für den aktuellen Benutzer oder für eine bestimmte Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="00785-110">On a Windows computer you can set an execution policy for the local computer, for the current user, or for a particular session.</span></span> <span data-ttu-id="00785-111">Sie können auch eine Gruppenrichtlinie Einstellung verwenden, um Ausführungsrichtlinien für Computer und Benutzer festzulegen.</span><span class="sxs-lookup"><span data-stu-id="00785-111">You can also use a Group Policy setting to set execution policies for computers and users.</span></span>

<span data-ttu-id="00785-112">Ausführungsrichtlinien für den lokalen Computer und den aktuellen Benutzer werden in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00785-112">Execution policies for the local computer and current user are stored in the registry.</span></span> <span data-ttu-id="00785-113">Sie müssen keine Ausführungsrichtlinien in Ihrem PowerShell-Profil festlegen.</span><span class="sxs-lookup"><span data-stu-id="00785-113">You don't need to set execution policies in your PowerShell profile.</span></span>
<span data-ttu-id="00785-114">Die Ausführungs Richtlinie für eine bestimmte Sitzung wird nur im Arbeitsspeicher gespeichert und geht verloren, wenn die Sitzung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="00785-114">The execution policy for a particular session is stored only in memory and is lost when the session is closed.</span></span>

<span data-ttu-id="00785-115">Die Ausführungs Richtlinie ist kein Sicherheitssystem, das Benutzeraktionen einschränkt.</span><span class="sxs-lookup"><span data-stu-id="00785-115">The execution policy isn't a security system that restricts user actions.</span></span> <span data-ttu-id="00785-116">Beispielsweise können Benutzer eine Richtlinie problemlos umgehen, indem Sie den Skript Inhalt in der Befehlszeile eingeben, wenn Sie ein Skript nicht ausführen können.</span><span class="sxs-lookup"><span data-stu-id="00785-116">For example, users can easily bypass a policy by typing the script contents at the command line when they cannot run a script.</span></span> <span data-ttu-id="00785-117">Stattdessen unterstützt die Ausführungs Richtlinie Benutzer beim Festlegen grundlegender Regeln und verhindert, dass Sie unbeabsichtigt gegen Sie verstoßen.</span><span class="sxs-lookup"><span data-stu-id="00785-117">Instead, the execution policy helps users to set basic rules and prevents them from violating them unintentionally.</span></span>

## <a name="powershell-execution-policies"></a><span data-ttu-id="00785-118">PowerShell-Ausführungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="00785-118">PowerShell execution policies</span></span>

<span data-ttu-id="00785-119">Die PowerShell-Ausführungsrichtlinien lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="00785-119">The PowerShell execution policies are as follows:</span></span>

### <a name="allsigned"></a><span data-ttu-id="00785-120">AllSigned</span><span class="sxs-lookup"><span data-stu-id="00785-120">AllSigned</span></span>

- <span data-ttu-id="00785-121">Skripts können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00785-121">Scripts can run.</span></span>
- <span data-ttu-id="00785-122">Erfordert, dass alle Skripts und Konfigurationsdateien von einem vertrauenswürdigen Herausgeber signiert sind, einschließlich Skripts, die auf dem lokalen Computer geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="00785-122">Requires that all scripts and configuration files be signed by a trusted publisher, including scripts that you write on the local computer.</span></span>
- <span data-ttu-id="00785-123">Sie werden vor dem Ausführen von Skripts von Verlegern aufgefordert, die Sie noch nicht als vertrauenswürdig eingestuft haben.</span><span class="sxs-lookup"><span data-stu-id="00785-123">Prompts you before running scripts from publishers that you haven't yet classified as trusted or untrusted.</span></span>
- <span data-ttu-id="00785-124">Risiken, die mit signierten, aber bösartigen Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00785-124">Risks running signed, but malicious, scripts.</span></span>

### <a name="bypass"></a><span data-ttu-id="00785-125">Umgehung</span><span class="sxs-lookup"><span data-stu-id="00785-125">Bypass</span></span>

- <span data-ttu-id="00785-126">Es findet keine Blockierung statt und es werden keine Warnungen oder Eingabeaufforderungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="00785-126">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="00785-127">Diese Ausführungs Richtlinie ist für Konfigurationen konzipiert, in denen ein PowerShell-Skript in eine größere Anwendung integriert ist, oder für Konfigurationen, in denen PowerShell die Grundlage für ein Programm ist, das über ein eigenes Sicherheitsmodell verfügt.</span><span class="sxs-lookup"><span data-stu-id="00785-127">This execution policy is designed for configurations in which a PowerShell script is built in to a larger application or for configurations in which PowerShell is the foundation for a program that has its own security model.</span></span>

### <a name="default"></a><span data-ttu-id="00785-128">Standard</span><span class="sxs-lookup"><span data-stu-id="00785-128">Default</span></span>

- <span data-ttu-id="00785-129">Legt die Standard Ausführungs Richtlinie fest.</span><span class="sxs-lookup"><span data-stu-id="00785-129">Sets the default execution policy.</span></span>
- <span data-ttu-id="00785-130">Für Windows-Clients **beschränkt** .</span><span class="sxs-lookup"><span data-stu-id="00785-130">**Restricted** for Windows clients.</span></span>
- <span data-ttu-id="00785-131">**RemoteSigned** für Windows-Server.</span><span class="sxs-lookup"><span data-stu-id="00785-131">**RemoteSigned** for Windows servers.</span></span>

### <a name="remotesigned"></a><span data-ttu-id="00785-132">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="00785-132">RemoteSigned</span></span>

- <span data-ttu-id="00785-133">Die Standard Ausführungs Richtlinie für Windows Server-Computer.</span><span class="sxs-lookup"><span data-stu-id="00785-133">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="00785-134">Skripts können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00785-134">Scripts can run.</span></span>
- <span data-ttu-id="00785-135">Erfordert eine digitale Signatur von einem vertrauenswürdigen Herausgeber für Skripts und Konfigurationsdateien, die aus dem Internet heruntergeladen werden, einschließlich e-Mail-und Instant Messaging-Programme.</span><span class="sxs-lookup"><span data-stu-id="00785-135">Requires a digital signature from a trusted publisher on scripts and configuration files that are downloaded from the internet which includes email and instant messaging programs.</span></span>
- <span data-ttu-id="00785-136">Erfordert keine digitalen Signaturen für Skripts, die auf dem lokalen Computer geschrieben und nicht aus dem Internet heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="00785-136">Doesn't require digital signatures on scripts that are written on the local computer and not downloaded from the internet.</span></span>
- <span data-ttu-id="00785-137">Führt Skripts aus, die aus dem Internet heruntergeladen und nicht signiert sind, wenn die Blockierung der Skripts aufgehoben wird, z. b. mithilfe des- `Unblock-File` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="00785-137">Runs scripts that are downloaded from the internet and not signed, if the scripts are unblocked, such as by using the `Unblock-File` cmdlet.</span></span>
- <span data-ttu-id="00785-138">Risiken bei der Ausführung nicht signierter Skripts aus anderen Quellen als dem Internet und signierten Skripts, die bösartig sein könnten.</span><span class="sxs-lookup"><span data-stu-id="00785-138">Risks running unsigned scripts from sources other than the internet and signed scripts that could be malicious.</span></span>

### <a name="restricted"></a><span data-ttu-id="00785-139">Eingeschränkt</span><span class="sxs-lookup"><span data-stu-id="00785-139">Restricted</span></span>

- <span data-ttu-id="00785-140">Die Standard Ausführungs Richtlinie für Windows-Client Computer.</span><span class="sxs-lookup"><span data-stu-id="00785-140">The default execution policy for Windows client computers.</span></span>
- <span data-ttu-id="00785-141">Lässt einzelne Befehle zu, erlaubt aber keine Skripts.</span><span class="sxs-lookup"><span data-stu-id="00785-141">Permits individual commands, but does not allow scripts.</span></span>
- <span data-ttu-id="00785-142">Verhindert die Ausführung aller Skriptdateien, einschließlich Formatierungs-und Konfigurationsdateien ( `.ps1xml` ), Modul Skriptdateien ( `.psm1` ) und PowerShell-Profilen ( `.ps1` ).</span><span class="sxs-lookup"><span data-stu-id="00785-142">Prevents running of all script files, including formatting and configuration files (`.ps1xml`), module script files (`.psm1`), and PowerShell profiles (`.ps1`).</span></span>

### <a name="undefined"></a><span data-ttu-id="00785-143">Nicht definiert</span><span class="sxs-lookup"><span data-stu-id="00785-143">Undefined</span></span>

- <span data-ttu-id="00785-144">Im aktuellen Bereich ist keine Ausführungs Richtlinie festgelegt.</span><span class="sxs-lookup"><span data-stu-id="00785-144">There is no execution policy set in the current scope.</span></span>
- <span data-ttu-id="00785-145">Wenn die Ausführungs Richtlinie in allen Bereichen nicht **definiert** ist, ist die effektive Ausführungs Richtlinie für Windows-Clients und **RemoteSigned** für Windows Server **beschränkt** .</span><span class="sxs-lookup"><span data-stu-id="00785-145">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** for Windows clients and **RemoteSigned** for Windows Server.</span></span>

### <a name="unrestricted"></a><span data-ttu-id="00785-146">Nicht eingeschränkt</span><span class="sxs-lookup"><span data-stu-id="00785-146">Unrestricted</span></span>

- <span data-ttu-id="00785-147">Nicht signierte Skripts können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00785-147">Unsigned scripts can run.</span></span> <span data-ttu-id="00785-148">Es besteht das Risiko, bösartige Skripts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="00785-148">There is a risk of running malicious scripts.</span></span>
- <span data-ttu-id="00785-149">Warnt den Benutzer vor dem Ausführen von Skripts und Konfigurationsdateien, die nicht in der lokalen Intranetzone sind.</span><span class="sxs-lookup"><span data-stu-id="00785-149">Warns the user before running scripts and configuration files that are not from the local intranet zone.</span></span>

> [!NOTE]
> <span data-ttu-id="00785-150">Auf Systemen, die Universal Naming Convention (UNC)-Pfade nicht von Internet Pfaden unterscheiden, dürfen Skripts, die von einem UNC-Pfad identifiziert werden, möglicherweise nicht mit der **RemoteSigned** -Ausführungs Richtlinie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00785-150">On systems that do not distinguish Universal Naming Convention (UNC) paths from internet paths, scripts that are identified by a UNC path might not be permitted to run with the **RemoteSigned** execution policy.</span></span>

## <a name="execution-policy-scope"></a><span data-ttu-id="00785-151">Ausführungsrichtlinien Bereich</span><span class="sxs-lookup"><span data-stu-id="00785-151">Execution policy scope</span></span>

<span data-ttu-id="00785-152">Sie können eine Ausführungs Richtlinie festlegen, die nur in einem bestimmten Bereich wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="00785-152">You can set an execution policy that is effective only in a particular scope.</span></span>

<span data-ttu-id="00785-153">Gültige Werte für den **Bereich** sind " **MachinePolicy** ", " **UserPolicy** ", " **Process** ", " **CurrentUser** " und " **LocalMachine** ".</span><span class="sxs-lookup"><span data-stu-id="00785-153">The valid values for **Scope** are **MachinePolicy** , **UserPolicy** , **Process** , **CurrentUser** , and **LocalMachine**.</span></span> <span data-ttu-id="00785-154">**LocalMachine** ist die Standardeinstellung, wenn eine Ausführungs Richtlinie festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="00785-154">**LocalMachine** is the default when setting an execution policy.</span></span>

<span data-ttu-id="00785-155">Die **Bereichs** Werte werden in der Reihenfolge der Rangfolge aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="00785-155">The **Scope** values are listed in precedence order.</span></span> <span data-ttu-id="00785-156">Die Richtlinie, die Vorrang hat, ist in der aktuellen Sitzung wirksam, auch wenn eine restriktivere Richtlinie mit einer niedrigeren Rangfolge festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="00785-156">The policy that takes precedence is effective in the current session, even if a more restrictive policy was set at a lower level of precedence.</span></span>

<span data-ttu-id="00785-157">Weitere Informationen finden Sie unter [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span><span class="sxs-lookup"><span data-stu-id="00785-157">For more information, see [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span></span>

### <a name="machinepolicy"></a><span data-ttu-id="00785-158">MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="00785-158">MachinePolicy</span></span>

<span data-ttu-id="00785-159">Wird von einem Gruppenrichtlinie für alle Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="00785-159">Set by a Group Policy for all users of the computer.</span></span>

### <a name="userpolicy"></a><span data-ttu-id="00785-160">UserPolicy</span><span class="sxs-lookup"><span data-stu-id="00785-160">UserPolicy</span></span>

<span data-ttu-id="00785-161">Wird von einem Gruppenrichtlinie für den aktuellen Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="00785-161">Set by a Group Policy for the current user of the computer.</span></span>

### <a name="process"></a><span data-ttu-id="00785-162">Prozess</span><span class="sxs-lookup"><span data-stu-id="00785-162">Process</span></span>

<span data-ttu-id="00785-163">Der **Prozess** Bereich wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="00785-163">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="00785-164">Die Ausführungs Richtlinie wird in der-Umgebungsvariablen und `$env:PSExecutionPolicyPreference` nicht in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00785-164">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="00785-165">Wenn die PowerShell-Sitzung geschlossen ist, werden die Variable und der Wert gelöscht.</span><span class="sxs-lookup"><span data-stu-id="00785-165">When the PowerShell session is closed, the variable and value are deleted.</span></span>

### <a name="currentuser"></a><span data-ttu-id="00785-166">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="00785-166">CurrentUser</span></span>

<span data-ttu-id="00785-167">Die Ausführungsrichtlinie wirkt sich nur auf den aktuellen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="00785-167">The execution policy affects only the current user.</span></span> <span data-ttu-id="00785-168">Sie wird im Registrierungs Unterschlüssel **HKEY_CURRENT_USER** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00785-168">It's stored in the **HKEY_CURRENT_USER** registry subkey.</span></span>

### <a name="localmachine"></a><span data-ttu-id="00785-169">LocalMachine</span><span class="sxs-lookup"><span data-stu-id="00785-169">LocalMachine</span></span>

<span data-ttu-id="00785-170">Die Ausführungs Richtlinie wirkt sich auf alle Benutzer des aktuellen Computers aus.</span><span class="sxs-lookup"><span data-stu-id="00785-170">The execution policy affects all users on the current computer.</span></span> <span data-ttu-id="00785-171">Sie wird im Registrierungs Unterschlüssel **HKEY_LOCAL_MACHINE** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00785-171">It's stored in the **HKEY_LOCAL_MACHINE** registry subkey.</span></span>

## <a name="managing-the-execution-policy-with-powershell"></a><span data-ttu-id="00785-172">Verwalten der Ausführungs Richtlinie mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="00785-172">Managing the execution policy with PowerShell</span></span>

<span data-ttu-id="00785-173">Verwenden Sie das-Cmdlet, um die effektive Ausführungs Richtlinie für die aktuelle PowerShell-Sitzung zu erhalten `Get-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="00785-173">To get the effective execution policy for the current PowerShell session, use the `Get-ExecutionPolicy` cmdlet.</span></span>

<span data-ttu-id="00785-174">Mit dem folgenden Befehl wird die effektive Ausführungs Richtlinie abgerufen:</span><span class="sxs-lookup"><span data-stu-id="00785-174">The following command gets the effective execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="00785-175">So erhalten Sie alle Ausführungsrichtlinien, die sich auf die aktuelle Sitzung auswirken, und zeigen Sie in der Rangfolge an:</span><span class="sxs-lookup"><span data-stu-id="00785-175">To get all of the execution policies that affect the current session and display them in precedence order:</span></span>

```powershell
Get-ExecutionPolicy -List
```

<span data-ttu-id="00785-176">Das Ergebnis sieht in etwa wie in der folgenden Beispielausgabe aus:</span><span class="sxs-lookup"><span data-stu-id="00785-176">The result looks similar to the following sample output:</span></span>

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       AllSigned
```

<span data-ttu-id="00785-177">In diesem Fall ist die effektive Ausführungs Richtlinie **RemoteSigned** , da die Ausführungs Richtlinie für den aktuellen Benutzer Vorrang vor der für den lokalen Computer festgelegten Ausführungs Richtlinie hat.</span><span class="sxs-lookup"><span data-stu-id="00785-177">In this case, the effective execution policy is **RemoteSigned** because the execution policy for the current user takes precedence over the execution policy set for the local computer.</span></span>

<span data-ttu-id="00785-178">Um die Ausführungs Richtlinie für einen bestimmten Bereich zu erhalten, verwenden Sie den **Scope** -Parameter von `Get-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="00785-178">To get the execution policy set for a particular scope, use the **Scope** parameter of `Get-ExecutionPolicy`.</span></span>

<span data-ttu-id="00785-179">Mit dem folgenden Befehl wird z. b. die Ausführungs Richtlinie für den Bereich **CurrentUser** abgerufen:</span><span class="sxs-lookup"><span data-stu-id="00785-179">For example, the following command gets the execution policy for the **CurrentUser** scope:</span></span>

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

### <a name="change-the-execution-policy"></a><span data-ttu-id="00785-180">Ändern der Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="00785-180">Change the execution policy</span></span>

<span data-ttu-id="00785-181">Verwenden Sie das-Cmdlet, um die PowerShell-Ausführungs Richtlinie auf dem Windows-Computer zu ändern `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="00785-181">To change the PowerShell execution policy on your Windows computer, use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="00785-182">Die Änderung wird sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="00785-182">The change is effective immediately.</span></span> <span data-ttu-id="00785-183">PowerShell muss nicht neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="00785-183">You don't need to restart PowerShell.</span></span>

<span data-ttu-id="00785-184">Wenn Sie die Ausführungs Richtlinie für die Bereiche **LocalMachine** oder **CurrentUser** festlegen, wird die Änderung in der Registrierung gespeichert und bleibt wirksam, bis Sie Sie wieder ändern.</span><span class="sxs-lookup"><span data-stu-id="00785-184">If you set the execution policy for the scopes **LocalMachine** or the **CurrentUser** , the change is saved in the registry and remains effective until you change it again.</span></span>

<span data-ttu-id="00785-185">Wenn Sie die Ausführungs Richtlinie für den **Prozess** Bereich festlegen, wird diese nicht in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00785-185">If you set the execution policy for the **Process** scope, it's not saved in the registry.</span></span> <span data-ttu-id="00785-186">Die Ausführungs Richtlinie wird so lange beibehalten, bis der aktuelle Prozess und alle untergeordneten Prozesse geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="00785-186">The execution policy is retained until the current process and any child processes are closed.</span></span>

> [!NOTE]
> <span data-ttu-id="00785-187">Starten Sie in Windows Vista und höheren Versionen von Windows PowerShell mit der Option **als Administrator ausführen** , um Befehle auszuführen, mit denen die Ausführungs Richtlinie für den lokalen Computer, den Bereich **LocalMachine** , geändert wird.</span><span class="sxs-lookup"><span data-stu-id="00785-187">In Windows Vista and later versions of Windows, to run commands that change the execution policy for the local computer, **LocalMachine** scope, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="00785-188">So ändern Sie die Ausführungs Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="00785-188">To change your execution policy:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName>
```

<span data-ttu-id="00785-189">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="00785-189">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="00785-190">So legen Sie die Ausführungs Richtlinie in einem bestimmten Bereich fest:</span><span class="sxs-lookup"><span data-stu-id="00785-190">To set the execution policy in a particular scope:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName> -Scope <scope>
```

<span data-ttu-id="00785-191">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="00785-191">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

<span data-ttu-id="00785-192">Ein Befehl zum Ändern einer Ausführungs Richtlinie kann erfolgreich sein, aber die effektive Ausführungs Richtlinie trotzdem nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="00785-192">A command to change an execution policy can succeed but still not change the effective execution policy.</span></span>

<span data-ttu-id="00785-193">Beispielsweise kann ein Befehl, mit dem die Ausführungs Richtlinie für den lokalen Computer festgelegt wird, erfolgreich ausgeführt, aber von der Ausführungs Richtlinie für den aktuellen Benutzer überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="00785-193">For example, a command that sets the execution policy for the local computer can succeed but be overridden by the execution policy for the current user.</span></span>

### <a name="remove-the-execution-policy"></a><span data-ttu-id="00785-194">Entfernen der Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="00785-194">Remove the execution policy</span></span>

<span data-ttu-id="00785-195">Um die Ausführungs Richtlinie für einen bestimmten Bereich zu entfernen, legen Sie die Ausführungs Richtlinie auf "nicht **definiert** " fest.</span><span class="sxs-lookup"><span data-stu-id="00785-195">To remove the execution policy for a particular scope, set the execution policy to **Undefined**.</span></span>

<span data-ttu-id="00785-196">So entfernen Sie beispielsweise die Ausführungs Richtlinie für alle Benutzer des lokalen Computers:</span><span class="sxs-lookup"><span data-stu-id="00785-196">For example, to remove the execution policy for all the users of the local computer:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope LocalMachine
```

<span data-ttu-id="00785-197">So entfernen Sie die Ausführungs Richtlinie für einen **Bereich** :</span><span class="sxs-lookup"><span data-stu-id="00785-197">To remove the execution policy for a **Scope** :</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
```

<span data-ttu-id="00785-198">Wenn in keinem Bereich eine Ausführungs Richtlinie festgelegt ist, wird die effektive Ausführungs Richtlinie **eingeschränkt**. Dies ist die Standardeinstellung für Windows-Clients.</span><span class="sxs-lookup"><span data-stu-id="00785-198">If no execution policy is set in any scope, the effective execution policy is **Restricted** , which is the default for Windows clients.</span></span>

### <a name="set-a-different-policy-for-one-session"></a><span data-ttu-id="00785-199">Festlegen einer anderen Richtlinie für eine Sitzung</span><span class="sxs-lookup"><span data-stu-id="00785-199">Set a different policy for one session</span></span>

<span data-ttu-id="00785-200">Sie können den **ExecutionPolicy** -Parameter von **powershell.exe** verwenden, um eine Ausführungs Richtlinie für eine neue PowerShell-Sitzung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="00785-200">You can use the **ExecutionPolicy** parameter of **powershell.exe** to set an execution policy for a new PowerShell session.</span></span> <span data-ttu-id="00785-201">Die Richtlinie wirkt sich nur auf die aktuelle Sitzung und untergeordnete Sitzungen aus.</span><span class="sxs-lookup"><span data-stu-id="00785-201">The policy affects only the current session and child sessions.</span></span>

<span data-ttu-id="00785-202">Um die Ausführungs Richtlinie für eine neue Sitzung festzulegen, starten Sie PowerShell in der Befehlszeile, z. b. **cmd.exe** oder PowerShell, und verwenden Sie dann den **ExecutionPolicy** -Parameter von **powershell.exe** , um die Ausführungs Richtlinie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="00785-202">To set the execution policy for a new session, start PowerShell at the command line, such as **cmd.exe** or from PowerShell, and then use the **ExecutionPolicy** parameter of **powershell.exe** to set the execution policy.</span></span>

<span data-ttu-id="00785-203">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="00785-203">For example:</span></span>

```powershell
powershell.exe -ExecutionPolicy AllSigned
```

<span data-ttu-id="00785-204">Die von Ihnen festgelegte Ausführungs Richtlinie ist nicht in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00785-204">The execution policy that you set isn't stored in the registry.</span></span> <span data-ttu-id="00785-205">Stattdessen wird Sie in der `$env:PSExecutionPolicyPreference` Umgebungsvariablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00785-205">Instead, it's stored in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="00785-206">Die Variable wird gelöscht, wenn Sie die Sitzung schließen, in der die Richtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="00785-206">The variable is deleted when you close the session in which the policy is set.</span></span> <span data-ttu-id="00785-207">Sie können die Richtlinie nicht ändern, indem Sie den Variablen Wert bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="00785-207">You cannot change the policy by editing the variable value.</span></span>

<span data-ttu-id="00785-208">Während der Sitzung hat die Ausführungs Richtlinie, die für die Sitzung festgelegt ist, Vorrang vor einer Ausführungs Richtlinie, die in der Registrierung für den lokalen Computer oder den aktuellen Benutzer festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="00785-208">During the session, the execution policy that is set for the session takes precedence over an execution policy that is set in the registry for the local computer or current user.</span></span> <span data-ttu-id="00785-209">Sie hat jedoch keinen Vorrang vor der Ausführungs Richtlinie, die mithilfe eines Gruppenrichtlinie festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="00785-209">However, it doesn't take precedence over the execution policy set by using a Group Policy.</span></span>

## <a name="use-group-policy-to-manage-execution-policy"></a><span data-ttu-id="00785-210">Verwalten der Ausführungs Richtlinie mit Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="00785-210">Use Group Policy to Manage Execution Policy</span></span>

<span data-ttu-id="00785-211">Sie können die Einstellung **Skriptausführung Gruppenrichtlinie aktivieren** verwenden, um die Ausführungs Richtlinie von Computern in Ihrem Unternehmen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="00785-211">You can use the **Turn on Script Execution** Group Policy setting to manage the execution policy of computers in your enterprise.</span></span> <span data-ttu-id="00785-212">Die Gruppenrichtlinie Einstellung überschreibt die Ausführungsrichtlinien, die in PowerShell in allen Bereichen festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="00785-212">The Group Policy setting overrides the execution policies set in PowerShell in all scopes.</span></span>

<span data-ttu-id="00785-213">Die Richtlinien Einstellungen **für die Skriptausführung aktivieren** lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="00785-213">The **Turn on Script Execution** policy settings are as follows:</span></span>

- <span data-ttu-id="00785-214">Wenn Sie die **Ausführung der Skriptausführung** deaktivieren, werden Skripts nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="00785-214">If you disable **Turn on Script Execution** , scripts do not run.</span></span> <span data-ttu-id="00785-215">Dies entspricht der **eingeschränkten** Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="00785-215">This is equivalent to the **Restricted** execution policy.</span></span>
- <span data-ttu-id="00785-216">Wenn Sie die Option **Skriptausführung** aktivieren aktivieren, können Sie eine Ausführungs Richtlinie auswählen.</span><span class="sxs-lookup"><span data-stu-id="00785-216">If you enable **Turn on Script Execution** , you can select an execution policy.</span></span> <span data-ttu-id="00785-217">Die Gruppenrichtlinie Einstellungen entsprechen den folgenden Einstellungen für die Ausführungs Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="00785-217">The Group Policy settings are equivalent to the following execution policy settings:</span></span>

  | <span data-ttu-id="00785-218">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="00785-218">Group Policy</span></span>                                  | <span data-ttu-id="00785-219">Ausführungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="00785-219">Execution Policy</span></span> |
  | --------------------------------------------- | ---------------- |
  | <span data-ttu-id="00785-220">Alle Skripts zulassen</span><span class="sxs-lookup"><span data-stu-id="00785-220">Allow all scripts</span></span>                             | <span data-ttu-id="00785-221">Nicht eingeschränkt</span><span class="sxs-lookup"><span data-stu-id="00785-221">Unrestricted</span></span>     |
  | <span data-ttu-id="00785-222">Lokale Skripts und Remote signierte Skripts zulassen</span><span class="sxs-lookup"><span data-stu-id="00785-222">Allow local scripts and remote signed scripts</span></span> | <span data-ttu-id="00785-223">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="00785-223">RemoteSigned</span></span>     |
  | <span data-ttu-id="00785-224">Nur signierte Skripts zulassen</span><span class="sxs-lookup"><span data-stu-id="00785-224">Allow only signed scripts</span></span>                     | <span data-ttu-id="00785-225">AllSigned</span><span class="sxs-lookup"><span data-stu-id="00785-225">AllSigned</span></span>        |

- <span data-ttu-id="00785-226">Wenn die Option **Skriptausführung aktivieren** nicht konfiguriert ist, hat dies keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="00785-226">If **Turn on Script Execution** is not configured, it has no effect.</span></span> <span data-ttu-id="00785-227">Die in PowerShell festgelegte Ausführungs Richtlinie ist gültig.</span><span class="sxs-lookup"><span data-stu-id="00785-227">The execution policy set in PowerShell is effective.</span></span>

<span data-ttu-id="00785-228">Die Dateien "powershellexecutionpolicy. adm" und "powershellexecutionpolicy. ADMX" fügen die Richtlinie zum **Aktivieren der Skriptausführung** zu den Knoten "Computer Konfiguration" und "Benutzerkonfiguration" in Gruppenrichtlinie Editor in den folgenden Pfaden hinzu.</span><span class="sxs-lookup"><span data-stu-id="00785-228">The PowerShellExecutionPolicy.adm and PowerShellExecutionPolicy.admx files add the **Turn on Script Execution** policy to the Computer Configuration and User Configuration nodes in Group Policy Editor in the following paths.</span></span>

<span data-ttu-id="00785-229">Für Windows XP und Windows Server 2003:</span><span class="sxs-lookup"><span data-stu-id="00785-229">For Windows XP and Windows Server 2003:</span></span>

<span data-ttu-id="00785-230">Administrative Vorlagen\Windows-komponents\windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="00785-230">Administrative Templates\Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="00785-231">Für Windows Vista und spätere Versionen von Windows:</span><span class="sxs-lookup"><span data-stu-id="00785-231">For Windows Vista and later versions of Windows:</span></span>

<span data-ttu-id="00785-232">Administrative vorlagen\classic administrative Vorlagen </span><span class="sxs-lookup"><span data-stu-id="00785-232">Administrative Templates\Classic Administrative Templates</span></span>\
<span data-ttu-id="00785-233">Windows-Komponenten \ Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="00785-233">Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="00785-234">Im Knoten Computer Konfiguration festgelegte Richtlinien haben Vorrang vor den Richtlinien, die im Knoten Benutzerkonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="00785-234">Policies set in the Computer Configuration node take precedence over policies set in the User Configuration node.</span></span>

<span data-ttu-id="00785-235">Weitere Informationen finden Sie unter [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="00785-235">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

### <a name="execution-policy-precedence"></a><span data-ttu-id="00785-236">Rangfolge der Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="00785-236">Execution policy precedence</span></span>

<span data-ttu-id="00785-237">Wenn Sie die effektive Ausführungs Richtlinie für eine Sitzung ermitteln, wertet PowerShell die Ausführungsrichtlinien in der folgenden Reihenfolge aus:</span><span class="sxs-lookup"><span data-stu-id="00785-237">When determining the effective execution policy for a session, PowerShell evaluates the execution policies in the following precedence order:</span></span>

- <span data-ttu-id="00785-238">Gruppenrichtlinie: MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="00785-238">Group Policy: MachinePolicy</span></span>
- <span data-ttu-id="00785-239">Gruppenrichtlinie: UserPolicy</span><span class="sxs-lookup"><span data-stu-id="00785-239">Group Policy: UserPolicy</span></span>
- <span data-ttu-id="00785-240">Ausführungs Richtlinie: Prozess (oder `powershell.exe -ExecutionPolicy` )</span><span class="sxs-lookup"><span data-stu-id="00785-240">Execution Policy: Process (or `powershell.exe -ExecutionPolicy`)</span></span>
- <span data-ttu-id="00785-241">Ausführungs Richtlinie: CurrentUser</span><span class="sxs-lookup"><span data-stu-id="00785-241">Execution Policy: CurrentUser</span></span>
- <span data-ttu-id="00785-242">Ausführungs Richtlinie: LocalMachine</span><span class="sxs-lookup"><span data-stu-id="00785-242">Execution Policy: LocalMachine</span></span>

## <a name="manage-signed-and-unsigned-scripts"></a><span data-ttu-id="00785-243">Verwalten von signierten und nicht signierten Skripts</span><span class="sxs-lookup"><span data-stu-id="00785-243">Manage signed and unsigned scripts</span></span>

<span data-ttu-id="00785-244">In Windows fügen Programme wie Internet Explorer und Microsoft Edge Dateien, die heruntergeladen werden, einen alternativen Datenstrom hinzu.</span><span class="sxs-lookup"><span data-stu-id="00785-244">In Windows, programs like Internet Explorer and Microsoft Edge add an alternate data stream to files that are downloaded.</span></span> <span data-ttu-id="00785-245">Dadurch wird die Datei als "aus dem Internet über das Internet" markiert.</span><span class="sxs-lookup"><span data-stu-id="00785-245">This marks the file as "coming from the Internet".</span></span> <span data-ttu-id="00785-246">Wenn Ihre PowerShell-Ausführungs Richtlinie **RemoteSigned** ist, führt PowerShell keine nicht signierten Skripts aus, die aus dem Internet heruntergeladen werden, einschließlich e-Mail-und Instant Messaging-Programme.</span><span class="sxs-lookup"><span data-stu-id="00785-246">If your PowerShell execution policy is **RemoteSigned** , PowerShell won't run unsigned scripts that are downloaded from the internet which includes email and instant messaging programs.</span></span>

<span data-ttu-id="00785-247">Sie können das Skript signieren oder ein nicht signiertes Skript ausführen, ohne die Ausführungs Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="00785-247">You can sign the script or elect to run an unsigned script without changing the execution policy.</span></span>

<span data-ttu-id="00785-248">Ab PowerShell 3,0 können Sie den **Stream** -Parameter des `Get-Item` Cmdlets verwenden, um Dateien zu erkennen, die blockiert werden, weil Sie aus dem Internet heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="00785-248">Beginning in PowerShell 3.0, you can use the **Stream** parameter of the `Get-Item` cmdlet to detect files that are blocked because they were downloaded from the internet.</span></span> <span data-ttu-id="00785-249">Verwenden Sie das `Unblock-File` Cmdlet, um die Blockierung der Skripts aufzulösen, damit Sie Sie in PowerShell ausführen können.</span><span class="sxs-lookup"><span data-stu-id="00785-249">Use the `Unblock-File` cmdlet to unblock the scripts so that you can run them in PowerShell.</span></span>

<span data-ttu-id="00785-250">Weitere Informationen finden Sie unter [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)und [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span><span class="sxs-lookup"><span data-stu-id="00785-250">For more information, see [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item), and [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span></span>

> [!NOTE]
> <span data-ttu-id="00785-251">Andere Methoden zum Herunterladen von Dateien dürfen die Dateien nicht als aus der Internet Zone stammende Dateien markieren.</span><span class="sxs-lookup"><span data-stu-id="00785-251">Other methods of downloading files may not mark the files as coming from the Internet Zone.</span></span> <span data-ttu-id="00785-252">Beispiele hierfür sind:</span><span class="sxs-lookup"><span data-stu-id="00785-252">Some examples include:</span></span>
>
> - `curl.exe`
> - `Invoke-RestMethod`
> - `Invoke-WebRequest`

## <a name="execution-policy-on-windows-server-core-and-window-nano-server"></a><span data-ttu-id="00785-253">Ausführungs Richtlinie für Windows Server Core und Windows Nano Server</span><span class="sxs-lookup"><span data-stu-id="00785-253">Execution policy on Windows Server Core and Window Nano Server</span></span>

<span data-ttu-id="00785-254">Wenn PowerShell 5,1 unter bestimmten Bedingungen unter Windows Server Core oder Windows Nano Server ausgeführt wird, können Ausführungsrichtlinien mit dem folgenden Fehler fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="00785-254">When PowerShell 5.1 is run on Windows Server Core or Windows Nano Server under certain conditions, execution policies can fail with the following error:</span></span>

```Output
AuthorizationManager check failed.
At line:1 char:1
+ C:\scriptpath\scriptname.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="00785-255">PowerShell verwendet APIs in der Windows-Desktopshell ( `explorer.exe` ), um die Zone einer Skriptdatei zu validieren.</span><span class="sxs-lookup"><span data-stu-id="00785-255">PowerShell uses APIs in the Windows Desktop Shell (`explorer.exe`) to validate the Zone of a script file.</span></span> <span data-ttu-id="00785-256">Die Windows-Shell ist unter Windows Server Core und Windows Nano Server nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="00785-256">The Windows Shell is not available on Windows Server Core and Windows Nano Server.</span></span>

<span data-ttu-id="00785-257">Dieser Fehler kann auch bei jedem Windows-System angezeigt werden, wenn die Windows-Desktopshell nicht verfügbar ist oder nicht reagiert.</span><span class="sxs-lookup"><span data-stu-id="00785-257">You could also get this error on any Windows system if the Windows Desktop Shell is unavailable or unresponsive.</span></span> <span data-ttu-id="00785-258">Beispielsweise kann während der Anmeldung die Ausführung eines PowerShell-Anmelde Skripts gestartet werden, bevor der Windows-Desktop bereit ist, was zu einem Fehler führt.</span><span class="sxs-lookup"><span data-stu-id="00785-258">For example, during sign on, a PowerShell logon script could start execution before the Windows Desktop is ready, resulting in failure.</span></span>

<span data-ttu-id="00785-259">Die Verwendung einer Ausführungs Richtlinie von **Bypass** oder **AllSigned** erfordert keine Zonen Überprüfung, um das Problem zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="00785-259">Using an execution policy of **ByPass** or **AllSigned** does not require a Zone check which avoids the problem.</span></span>

## <a name="see-also"></a><span data-ttu-id="00785-260">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00785-260">See Also</span></span>

[<span data-ttu-id="00785-261">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="00785-261">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="00785-262">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="00785-262">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="00785-263">about_Signing</span><span class="sxs-lookup"><span data-stu-id="00785-263">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="00785-264">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="00785-264">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="00785-265">Get-Item</span><span class="sxs-lookup"><span data-stu-id="00785-265">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

[<span data-ttu-id="00785-266">PowerShell.exe Command-Line Hilfe</span><span class="sxs-lookup"><span data-stu-id="00785-266">PowerShell.exe Command-Line Help</span></span>](about_PowerShell_exe.md)

[<span data-ttu-id="00785-267">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="00785-267">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="00785-268">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="00785-268">Unblock-File</span></span>](xref:Microsoft.PowerShell.Utility.Unblock-File)
