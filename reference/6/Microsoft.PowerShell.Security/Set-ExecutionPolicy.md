---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: f8575c97c4279f285598e2b1bdf94786d92c841a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216879"
---
# <span data-ttu-id="6129b-103">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="6129b-103">Set-ExecutionPolicy</span></span>

## <span data-ttu-id="6129b-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6129b-104">SYNOPSIS</span></span>
<span data-ttu-id="6129b-105">Legt die PowerShell-Ausführungsrichtlinien für Windows-Computer fest.</span><span class="sxs-lookup"><span data-stu-id="6129b-105">Sets the PowerShell execution policies for Windows computers.</span></span>

## <span data-ttu-id="6129b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6129b-106">SYNTAX</span></span>

### <span data-ttu-id="6129b-107">Alle</span><span class="sxs-lookup"><span data-stu-id="6129b-107">All</span></span>

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6129b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6129b-108">DESCRIPTION</span></span>

<span data-ttu-id="6129b-109">Mit dem- `Set-ExecutionPolicy` Cmdlet werden die PowerShell-Ausführungsrichtlinien für Windows-Computer geändert.</span><span class="sxs-lookup"><span data-stu-id="6129b-109">The `Set-ExecutionPolicy` cmdlet changes PowerShell execution policies for Windows computers.</span></span> <span data-ttu-id="6129b-110">Weitere Informationen finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="6129b-110">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="6129b-111">Ab PowerShell 6,0 für nicht-Windows-Computer ist die Standard Ausführungs Richtlinie **uneingeschränkt** und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6129b-111">Beginning in PowerShell 6.0 for non-Windows computers, the default execution policy is **Unrestricted** and can't be changed.</span></span> <span data-ttu-id="6129b-112">Das `Set-ExecutionPolicy` -Cmdlet ist verfügbar, aber PowerShell zeigt eine Konsolen Meldung an, dass dies nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6129b-112">The `Set-ExecutionPolicy` cmdlet is available, but PowerShell displays a console message that it's not supported.</span></span>

<span data-ttu-id="6129b-113">Eine Ausführungs Richtlinie ist Bestandteil der PowerShell-Sicherheitsstrategie.</span><span class="sxs-lookup"><span data-stu-id="6129b-113">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="6129b-114">Ausführungsrichtlinien legen fest, ob Sie Konfigurationsdateien, z. b. Ihr PowerShell-Profil, laden oder Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="6129b-114">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="6129b-115">Und, ob Skripts vor der Durchführung digital signiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6129b-115">And, whether scripts must be digitally signed before they are run.</span></span>

<span data-ttu-id="6129b-116">Der `Set-ExecutionPolicy` Standardbereich des Cmdlets ist " **LocalMachine** ", was sich auf alle Benutzer auswirkt, die den Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="6129b-116">The `Set-ExecutionPolicy` cmdlet's default scope is **LocalMachine** , which affects everyone who uses the computer.</span></span> <span data-ttu-id="6129b-117">Um die Ausführungs Richtlinie für **LocalMachine** zu ändern, starten Sie PowerShell mit **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="6129b-117">To change the execution policy for **LocalMachine** , start PowerShell with **Run as Administrator** .</span></span>

<span data-ttu-id="6129b-118">Verwenden Sie, um die Ausführungsrichtlinien für jeden Bereich in der Rangfolge anzuzeigen `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="6129b-118">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="6129b-119">Um die effektive Ausführungs Richtlinie für Ihre PowerShell-Sitzung anzuzeigen, verwenden Sie `Get-ExecutionPolicy` ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="6129b-119">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

## <span data-ttu-id="6129b-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6129b-120">EXAMPLES</span></span>

### <span data-ttu-id="6129b-121">Beispiel 1: Festlegen einer Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="6129b-121">Example 1: Set an execution policy</span></span>

<span data-ttu-id="6129b-122">In diesem Beispiel wird gezeigt, wie die Ausführungs Richtlinie für den lokalen Computer festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="6129b-122">This example shows how to set the execution policy for the local computer.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="6129b-123">Das `Set-ExecutionPolicy` Cmdlet verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6129b-123">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="6129b-124">Der **Scope** -Parameter gibt den Standard Bereichs Wert **LocalMachine** an.</span><span class="sxs-lookup"><span data-stu-id="6129b-124">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span> <span data-ttu-id="6129b-125">Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6129b-125">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="6129b-126">Beispiel 2: Festlegen einer Ausführungs Richtlinie, die in Konflikt mit einer Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6129b-126">Example 2: Set an execution policy that conflicts with a Group Policy</span></span>

<span data-ttu-id="6129b-127">Dieser Befehl versucht, die Ausführungs Richtlinie für den **LocalMachine** -Bereich auf " **restricted** " festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6129b-127">This command attempts to set the **LocalMachine** scope's execution policy to **Restricted** .</span></span>
<span data-ttu-id="6129b-128">" **LocalMachine** " ist restriktiver, aber nicht die wirksame Richtlinie, da Sie mit einer Gruppenrichtlinie in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="6129b-128">**LocalMachine** is more restrictive, but isn't the effective policy because it conflicts with a Group Policy.</span></span> <span data-ttu-id="6129b-129">Die **Eingeschränkte** Richtlinie wird in die Registrierungs Struktur **HKEY_LOCAL_MACHINE** geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6129b-129">The **Restricted** policy is written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

```
PS> Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine

Set-ExecutionPolicy : PowerShell updated your local preference successfully, but the setting is
overridden by the Group Policy applied to your system. Due to the override, your shell will retain
its current effective execution policy of "AllSigned". Contact your Group Policy administrator for
more information. At line:1 char:20 + Set-ExecutionPolicy <<<< restricted

PS> Get-ChildItem -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\1\ShellIds

Name                    Property
----                    --------
Microsoft.PowerShell    Path            : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
                        ExecutionPolicy : Restricted
ScriptedDiagnostics     ExecutionPolicy : Unrestricted
```

<span data-ttu-id="6129b-130">Das `Set-ExecutionPolicy` Cmdlet verwendet den **ExecutionPolicy** -Parameter zum Angeben der **eingeschränkten** Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="6129b-130">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **Restricted** policy.</span></span> <span data-ttu-id="6129b-131">Der **Scope** -Parameter gibt den Standard Bereichs Wert **LocalMachine** an.</span><span class="sxs-lookup"><span data-stu-id="6129b-131">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span>
<span data-ttu-id="6129b-132">Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter mit dem **HKLM** -Anbieter, um den Registrierungs Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6129b-132">The `Get-ChildItem` cmdlet uses the **Path** parameter with the **HKLM** provider to specify registry location.</span></span>

### <span data-ttu-id="6129b-133">Beispiel 3: Anwenden der Ausführungs Richtlinie von einem Remote Computer auf einen lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="6129b-133">Example 3: Apply the execution policy from a remote computer to a local computer</span></span>

<span data-ttu-id="6129b-134">Mit diesem Befehl wird das Objekt der Ausführungs Richtlinie von einem Remote Computer abgerufen, und die Richtlinie wird auf dem lokalen Computer festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6129b-134">This command gets the execution policy object from a remote computer and sets the policy on the local computer.</span></span> <span data-ttu-id="6129b-135">`Get-ExecutionPolicy` sendet ein **Microsoft.PowerShell.Executionpolicy** -Objekt über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="6129b-135">`Get-ExecutionPolicy` sends a **Microsoft.PowerShell.ExecutionPolicy** object down the pipeline.</span></span> <span data-ttu-id="6129b-136">`Set-ExecutionPolicy` akzeptiert Pipeline Eingaben und erfordert keinen **ExecutionPolicy** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="6129b-136">`Set-ExecutionPolicy` accepts pipeline input and doesn't require the **ExecutionPolicy** parameter.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

<span data-ttu-id="6129b-137">Das `Invoke-Command` -Cmdlet wird auf dem lokalen Computer ausgeführt und sendet den **ScriptBlock** an den Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="6129b-137">The `Invoke-Command` cmdlet is executed at the local computer and sends the **ScriptBlock** to the remote computer.</span></span> <span data-ttu-id="6129b-138">Der **Computername** -Parameter gibt den Remote Computer an, **Server01** .</span><span class="sxs-lookup"><span data-stu-id="6129b-138">The **ComputerName** parameter specifies the remote computer, **Server01** .</span></span> <span data-ttu-id="6129b-139">Der **ScriptBlock** -Parameter wird `Get-ExecutionPolicy` auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6129b-139">The **ScriptBlock** parameter runs `Get-ExecutionPolicy` on the remote computer.</span></span> <span data-ttu-id="6129b-140">Das `Get-ExecutionPolicy` Objekt wird über die Pipeline an das-Objekt gesendet `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="6129b-140">The `Get-ExecutionPolicy` object is sent down the pipeline to the `Set-ExecutionPolicy`.</span></span>
<span data-ttu-id="6129b-141">`Set-ExecutionPolicy` wendet die Ausführungs Richtlinie auf den Standardbereich " **LocalMachine** " des lokalen Computers an.</span><span class="sxs-lookup"><span data-stu-id="6129b-141">`Set-ExecutionPolicy` applies the execution policy to the local computer's default scope, **LocalMachine** .</span></span>

### <span data-ttu-id="6129b-142">Beispiel 4: Festlegen des Gültigkeits Bereichs für eine Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="6129b-142">Example 4: Set the scope for an execution policy</span></span>

<span data-ttu-id="6129b-143">Dieses Beispiel zeigt, wie eine Ausführungs Richtlinie für einen angegebenen Bereich, **CurrentUser** , festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="6129b-143">This example shows how to set an execution policy for a specified scope, **CurrentUser** .</span></span> <span data-ttu-id="6129b-144">Der Bereich " **CurrentUser** " wirkt sich nur auf den Benutzer aus, der diesen Bereich festlegt.</span><span class="sxs-lookup"><span data-stu-id="6129b-144">The **CurrentUser** scope only affects the user who sets this scope.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="6129b-145">`Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **AllSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6129b-145">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span>
<span data-ttu-id="6129b-146">Der **Scope** -Parameter gibt den **CurrentUser** an.</span><span class="sxs-lookup"><span data-stu-id="6129b-146">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="6129b-147">Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6129b-147">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

<span data-ttu-id="6129b-148">Die effektive Ausführungs Richtlinie für den Benutzer wird zu **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="6129b-148">The effective execution policy for the user becomes **AllSigned** .</span></span>

### <span data-ttu-id="6129b-149">Beispiel 5: Entfernen der Ausführungs Richtlinie für den aktuellen Benutzer</span><span class="sxs-lookup"><span data-stu-id="6129b-149">Example 5: Remove the execution policy for the current user</span></span>

<span data-ttu-id="6129b-150">In diesem Beispiel wird gezeigt, wie die nicht **definierte** Ausführungs Richtlinie verwendet wird, um eine Ausführungs Richtlinie für einen bestimmten Bereich zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6129b-150">This example shows how use the **Undefined** execution policy to remove an execution policy for a specified scope.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

<span data-ttu-id="6129b-151">`Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die nicht **definierte** Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6129b-151">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **Undefined** policy.</span></span>
<span data-ttu-id="6129b-152">Der **Scope** -Parameter gibt den **CurrentUser** an.</span><span class="sxs-lookup"><span data-stu-id="6129b-152">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="6129b-153">Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6129b-153">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="6129b-154">Beispiel 6: Festlegen der Ausführungs Richtlinie für die aktuelle PowerShell-Sitzung</span><span class="sxs-lookup"><span data-stu-id="6129b-154">Example 6: Set the execution policy for the current PowerShell session</span></span>

<span data-ttu-id="6129b-155">Der **Prozess** Bereich wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="6129b-155">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="6129b-156">Die Ausführungs Richtlinie wird in der Umgebungsvariablen gespeichert `$env:PSExecutionPolicyPreference` und beim Schließen der Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6129b-156">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference` and is deleted when the session is closed.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope Process
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       AllSigned
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="6129b-157">Der `Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **AllSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6129b-157">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span> <span data-ttu-id="6129b-158">Der **Scope** -Parameter gibt den Wert **Prozess** an.</span><span class="sxs-lookup"><span data-stu-id="6129b-158">The **Scope** parameter specifies the value **Process** .</span></span> <span data-ttu-id="6129b-159">Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6129b-159">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="6129b-160">Beispiel 7: Entsperren eines Skripts, um es auszuführen, ohne die Ausführungs Richtlinie zu ändern</span><span class="sxs-lookup"><span data-stu-id="6129b-160">Example 7: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="6129b-161">Dieses Beispiel zeigt, wie die **RemoteSigned** -Ausführungs Richtlinie verhindert, dass nicht signierte Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6129b-161">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="6129b-162">Eine bewährte Vorgehensweise besteht darin, den Skriptcode zu lesen und zu überprüfen, ob er sicher ist, **bevor** Sie das `Unblock-File` Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="6129b-162">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="6129b-163">Das- `Unblock-File` Cmdlet entsperrt Skripts, sodass Sie ausgeführt werden können, ändert jedoch nicht die Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="6129b-163">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

```
PS> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

.\Start-ActivityTracker.ps1 : File .\Start-ActivityTracker.ps1 cannot be loaded.
The file .\Start-ActivityTracker.ps1 is not digitally signed.
The script will not execute on the system.
For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], PSSecurityException
+ FullyQualifiedErrorId : UnauthorizedAccess

PS> Unblock-File -Path .\Start-ActivityTracker.ps1

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

Task 1:
```

<span data-ttu-id="6129b-164">Der `Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6129b-164">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="6129b-165">Die Richtlinie wird für den Standardbereich **LocalMachine** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6129b-165">The policy is set for the default scope, **LocalMachine** .</span></span>

<span data-ttu-id="6129b-166">Das- `Get-ExecutionPolicy` Cmdlet zeigt, dass **RemoteSigned** die effektive Ausführungs Richtlinie für die aktuelle PowerShell-Sitzung ist.</span><span class="sxs-lookup"><span data-stu-id="6129b-166">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="6129b-167">Das **Start-ActivityTracker.ps1** Skript wird aus dem aktuellen Verzeichnis ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6129b-167">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="6129b-168">Das Skript wird von **RemoteSigned** blockiert, da das Skript nicht digital signiert ist.</span><span class="sxs-lookup"><span data-stu-id="6129b-168">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="6129b-169">In diesem Beispiel wurde der Code des Skripts überprüft und als sicher für die Durchführung überprüft.</span><span class="sxs-lookup"><span data-stu-id="6129b-169">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="6129b-170">Das `Unblock-File` Cmdlet verwendet den **path** -Parameter, um die Blockierung des Skripts aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="6129b-170">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="6129b-171">Um zu überprüfen, ob `Unblock-File` die Ausführungs Richtlinie nicht geändert wurde, `Get-ExecutionPolicy` zeigt die effektive Ausführungs Richtlinie " **RemoteSigned** " an.</span><span class="sxs-lookup"><span data-stu-id="6129b-171">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned** .</span></span>

<span data-ttu-id="6129b-172">Das Skript, **Start-ActivityTracker.ps1** aus dem aktuellen Verzeichnis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6129b-172">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="6129b-173">Das Skript beginnt mit der Durchführung der Blockierung durch das `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6129b-173">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="6129b-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6129b-174">PARAMETERS</span></span>

### <span data-ttu-id="6129b-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6129b-175">-Confirm</span></span>

<span data-ttu-id="6129b-176">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6129b-176">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6129b-177">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="6129b-177">-ExecutionPolicy</span></span>

<span data-ttu-id="6129b-178">Gibt die Ausführungs Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="6129b-178">Specifies the execution policy.</span></span> <span data-ttu-id="6129b-179">Wenn keine Gruppenrichtlinien vorhanden sind und die Ausführungs Richtlinie jedes Bereichs auf "nicht **definiert** " festgelegt ist, wird die eingeschränkte Richtlinie für alle Benutzer **eingeschränkt** .</span><span class="sxs-lookup"><span data-stu-id="6129b-179">If there are no Group Policies and each scope's execution policy is set to **Undefined** , then **Restricted** becomes the effective policy for all users.</span></span>

<span data-ttu-id="6129b-180">Die zulässigen Werte für die Ausführungs Richtlinie lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6129b-180">The acceptable execution policy values are as follows:</span></span>

- <span data-ttu-id="6129b-181">Alle **signiert** .</span><span class="sxs-lookup"><span data-stu-id="6129b-181">**AllSigned** .</span></span> <span data-ttu-id="6129b-182">Erfordert, dass alle Skripts und Konfigurationsdateien von einem vertrauenswürdigen Herausgeber signiert werden, einschließlich der auf dem lokalen Computer geschriebenen Skripts.</span><span class="sxs-lookup"><span data-stu-id="6129b-182">Requires that all scripts and configuration files are signed by a trusted publisher, including scripts written on the local computer.</span></span>
- <span data-ttu-id="6129b-183">**Umgehung** .</span><span class="sxs-lookup"><span data-stu-id="6129b-183">**Bypass** .</span></span> <span data-ttu-id="6129b-184">Es findet keine Blockierung statt und es werden keine Warnungen oder Eingabeaufforderungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="6129b-184">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="6129b-185">**Default** .</span><span class="sxs-lookup"><span data-stu-id="6129b-185">**Default** .</span></span> <span data-ttu-id="6129b-186">Legt die Standard Ausführungs Richtlinie fest.</span><span class="sxs-lookup"><span data-stu-id="6129b-186">Sets the default execution policy.</span></span> <span data-ttu-id="6129b-187">**Eingeschränkt** für Windows-Clients oder **RemoteSigned** für Windows-Server.</span><span class="sxs-lookup"><span data-stu-id="6129b-187">**Restricted** for Windows clients or **RemoteSigned** for Windows servers.</span></span>
- <span data-ttu-id="6129b-188">**RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="6129b-188">**RemoteSigned** .</span></span> <span data-ttu-id="6129b-189">Erfordert, dass alle aus dem Internet heruntergeladenen Skripts und Konfigurationsdateien von einem vertrauenswürdigen Herausgeber signiert werden.</span><span class="sxs-lookup"><span data-stu-id="6129b-189">Requires that all scripts and configuration files downloaded from the Internet are signed by a trusted publisher.</span></span> <span data-ttu-id="6129b-190">Die Standard Ausführungs Richtlinie für Windows Server-Computer.</span><span class="sxs-lookup"><span data-stu-id="6129b-190">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="6129b-191">**Eingeschränkt** .</span><span class="sxs-lookup"><span data-stu-id="6129b-191">**Restricted** .</span></span> <span data-ttu-id="6129b-192">Lädt keine Konfigurationsdateien und führt keine Skripts aus.</span><span class="sxs-lookup"><span data-stu-id="6129b-192">Doesn't load configuration files or run scripts.</span></span> <span data-ttu-id="6129b-193">Die Standard-Ausführungs Richtlinie für Windows-Client Computer.</span><span class="sxs-lookup"><span data-stu-id="6129b-193">The default execution policy Windows client computers.</span></span>
- <span data-ttu-id="6129b-194">Nicht **definiert** .</span><span class="sxs-lookup"><span data-stu-id="6129b-194">**Undefined** .</span></span> <span data-ttu-id="6129b-195">Für den Bereich wurde keine Ausführungs Richtlinie festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6129b-195">No execution policy is set for the scope.</span></span> <span data-ttu-id="6129b-196">Entfernt eine zugewiesene Ausführungs Richtlinie aus einem Bereich, der nicht von einem Gruppenrichtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6129b-196">Removes an assigned execution policy from a scope that is not set by a Group Policy.</span></span> <span data-ttu-id="6129b-197">Wenn die Ausführungs Richtlinie in allen Bereichen nicht **definiert** ist, ist die effektive Ausführungs Richtlinie **eingeschränkt** .</span><span class="sxs-lookup"><span data-stu-id="6129b-197">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** .</span></span>
- <span data-ttu-id="6129b-198">**Uneingeschränkt** .</span><span class="sxs-lookup"><span data-stu-id="6129b-198">**Unrestricted** .</span></span> <span data-ttu-id="6129b-199">Ab PowerShell 6,0 ist dies die Standard Ausführungs Richtlinie für nicht-Windows-Computer und kann nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6129b-199">Beginning in PowerShell 6.0, this is the default execution policy for non-Windows computers and can't be changed.</span></span> <span data-ttu-id="6129b-200">Lädt alle Konfigurationsdateien und führt alle Skripts aus.</span><span class="sxs-lookup"><span data-stu-id="6129b-200">Loads all configuration files and runs all scripts.</span></span> <span data-ttu-id="6129b-201">Wenn Sie ein nicht signiertes Skript ausführen, das aus dem Internet heruntergeladen wurde, werden Sie zur Eingabe der Berechtigung aufgefordert, bevor es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6129b-201">If you run an unsigned script that was downloaded from the internet, you're prompted for permission before it runs.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: AllSigned, Bypass, Default, RemoteSigned, Restricted, Undefined, Unrestricted

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6129b-202">-Force</span><span class="sxs-lookup"><span data-stu-id="6129b-202">-Force</span></span>

<span data-ttu-id="6129b-203">Unterdrückt alle Bestätigungsaufforderungen.</span><span class="sxs-lookup"><span data-stu-id="6129b-203">Suppresses all the confirmation prompts.</span></span> <span data-ttu-id="6129b-204">Verwenden Sie diesen Parameter als Vorsicht, um unerwartete Ergebnisse zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6129b-204">Use caution with this parameter to avoid unexpected results.</span></span>

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

### <span data-ttu-id="6129b-205">-Bereich</span><span class="sxs-lookup"><span data-stu-id="6129b-205">-Scope</span></span>

<span data-ttu-id="6129b-206">Gibt den Bereich an, der von einer Ausführungs Richtlinie betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="6129b-206">Specifies the scope that is affected by an execution policy.</span></span> <span data-ttu-id="6129b-207">Der Standardbereich ist **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="6129b-207">The default scope is **LocalMachine** .</span></span>

<span data-ttu-id="6129b-208">Die effektive Ausführungs Richtlinie wird wie folgt durch die Rangfolge bestimmt:</span><span class="sxs-lookup"><span data-stu-id="6129b-208">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="6129b-209">**MachinePolicy** .</span><span class="sxs-lookup"><span data-stu-id="6129b-209">**MachinePolicy** .</span></span> <span data-ttu-id="6129b-210">Wird von einem Gruppenrichtlinie für alle Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6129b-210">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="6129b-211">**UserPolicy** .</span><span class="sxs-lookup"><span data-stu-id="6129b-211">**UserPolicy** .</span></span> <span data-ttu-id="6129b-212">Wird von einem Gruppenrichtlinie für den aktuellen Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6129b-212">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="6129b-213">**Verarbeiten** .</span><span class="sxs-lookup"><span data-stu-id="6129b-213">**Process** .</span></span> <span data-ttu-id="6129b-214">Wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="6129b-214">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="6129b-215">**CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="6129b-215">**CurrentUser** .</span></span> <span data-ttu-id="6129b-216">Wirkt sich nur auf den aktuellen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="6129b-216">Affects only the current user.</span></span>
- <span data-ttu-id="6129b-217">**LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="6129b-217">**LocalMachine** .</span></span> <span data-ttu-id="6129b-218">Standardbereich, der sich auf alle Benutzer des Computers auswirkt.</span><span class="sxs-lookup"><span data-stu-id="6129b-218">Default scope that affects all users of the computer.</span></span>

<span data-ttu-id="6129b-219">Der **Prozess** Bereich wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="6129b-219">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="6129b-220">Die Ausführungs Richtlinie wird in der-Umgebungsvariablen und `$env:PSExecutionPolicyPreference` nicht in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6129b-220">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="6129b-221">Wenn die PowerShell-Sitzung geschlossen ist, werden die Variable und der Wert gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6129b-221">When the PowerShell session is closed, the variable and value are deleted.</span></span>

<span data-ttu-id="6129b-222">Ausführungsrichtlinien für den Bereich **CurrentUser** werden in die Registrierungs Struktur **HKEY_LOCAL_USER** geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6129b-222">Execution policies for the **CurrentUser** scope are written to the registry hive **HKEY_LOCAL_USER** .</span></span>

<span data-ttu-id="6129b-223">Ausführungsrichtlinien für den Bereich " **LocalMachine** " werden in die Registrierungs Struktur **HKEY_LOCAL_MACHINE** geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6129b-223">Execution policies for the **LocalMachine** scope are written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 1
Default value: LocalMachine
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6129b-224">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6129b-224">-WhatIf</span></span>

<span data-ttu-id="6129b-225">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6129b-225">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6129b-226">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6129b-226">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6129b-227">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6129b-227">CommonParameters</span></span>

<span data-ttu-id="6129b-228">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6129b-228">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6129b-229">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6129b-229">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6129b-230">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6129b-230">INPUTS</span></span>

### <span data-ttu-id="6129b-231">Microsoft.PowerShell.Executionpolicy, System. String</span><span class="sxs-lookup"><span data-stu-id="6129b-231">Microsoft.PowerShell.ExecutionPolicy, System.String</span></span>

<span data-ttu-id="6129b-232">Sie können ein Ausführungsrichtlinien Objekt oder eine Zeichenfolge, die den Namen einer Ausführungs Richtlinie enthält, über die Pipeline an übergeben `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="6129b-232">You can pipe an execution policy object or a string that contains the name of an execution policy to `Set-ExecutionPolicy`.</span></span>

## <span data-ttu-id="6129b-233">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6129b-233">OUTPUTS</span></span>

### <span data-ttu-id="6129b-234">Keine</span><span class="sxs-lookup"><span data-stu-id="6129b-234">None</span></span>

<span data-ttu-id="6129b-235">`Set-ExecutionPolicy` gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="6129b-235">`Set-ExecutionPolicy` doesn't return any output.</span></span>

## <span data-ttu-id="6129b-236">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6129b-236">NOTES</span></span>

<span data-ttu-id="6129b-237">`Set-ExecutionPolicy` ändert nicht die Bereiche **MachinePolicy** und **UserPolicy** , da diese durch Gruppenrichtlinien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="6129b-237">`Set-ExecutionPolicy` doesn't change the **MachinePolicy** and **UserPolicy** scopes because they are set by Group Policies.</span></span>

<span data-ttu-id="6129b-238">`Set-ExecutionPolicy` überschreibt eine Gruppenrichtlinie nicht, auch wenn die Benutzereinstellung restriktiver als die Richtlinie ist.</span><span class="sxs-lookup"><span data-stu-id="6129b-238">`Set-ExecutionPolicy` doesn't override a Group Policy, even if the user preference is more restrictive than the policy.</span></span>

<span data-ttu-id="6129b-239">Wenn die Gruppenrichtlinie **Skriptausführung** aktivieren für den Computer oder Benutzer aktiviert ist, wird die Benutzereinstellung gespeichert, aber Sie ist nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="6129b-239">If the Group Policy **Turn on Script Execution** is enabled for the computer or user, the user preference is saved, but it is not effective.</span></span> <span data-ttu-id="6129b-240">PowerShell zeigt eine Meldung an, in der der Konflikt erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="6129b-240">PowerShell displays a message that explains the conflict.</span></span>

## <span data-ttu-id="6129b-241">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6129b-241">RELATED LINKS</span></span>

[<span data-ttu-id="6129b-242">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="6129b-242">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="6129b-243">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="6129b-243">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="6129b-244">about_Providers</span><span class="sxs-lookup"><span data-stu-id="6129b-244">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="6129b-245">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="6129b-245">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="6129b-246">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6129b-246">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="6129b-247">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="6129b-247">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="6129b-248">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="6129b-248">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="6129b-249">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="6129b-249">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="6129b-250">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="6129b-250">Unblock-File</span></span>](../Microsoft.PowerShell.Utility/Unblock-File.md)
