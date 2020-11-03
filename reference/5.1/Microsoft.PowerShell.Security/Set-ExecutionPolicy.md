---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: 313ff4f2d3fc89263cdf4d0ede860ef8e538a2ea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214204"
---
# <span data-ttu-id="dd661-103">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="dd661-103">Set-ExecutionPolicy</span></span>

## <span data-ttu-id="dd661-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dd661-104">SYNOPSIS</span></span>
<span data-ttu-id="dd661-105">Legt die PowerShell-Ausführungsrichtlinien für Windows-Computer fest.</span><span class="sxs-lookup"><span data-stu-id="dd661-105">Sets the PowerShell execution policies for Windows computers.</span></span>

## <span data-ttu-id="dd661-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dd661-106">SYNTAX</span></span>

### <span data-ttu-id="dd661-107">Alle</span><span class="sxs-lookup"><span data-stu-id="dd661-107">All</span></span>

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="dd661-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dd661-108">DESCRIPTION</span></span>

<span data-ttu-id="dd661-109">Mit dem- `Set-ExecutionPolicy` Cmdlet werden die PowerShell-Ausführungsrichtlinien für Windows-Computer geändert.</span><span class="sxs-lookup"><span data-stu-id="dd661-109">The `Set-ExecutionPolicy` cmdlet changes PowerShell execution policies for Windows computers.</span></span> <span data-ttu-id="dd661-110">Weitere Informationen finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="dd661-110">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="dd661-111">Eine Ausführungs Richtlinie ist Bestandteil der PowerShell-Sicherheitsstrategie.</span><span class="sxs-lookup"><span data-stu-id="dd661-111">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="dd661-112">Ausführungsrichtlinien legen fest, ob Sie Konfigurationsdateien, z. b. Ihr PowerShell-Profil, laden oder Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="dd661-112">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="dd661-113">Und, ob Skripts vor der Durchführung digital signiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="dd661-113">And, whether scripts must be digitally signed before they are run.</span></span>

<span data-ttu-id="dd661-114">Der `Set-ExecutionPolicy` Standardbereich des Cmdlets ist " **LocalMachine** ", was sich auf alle Benutzer auswirkt, die den Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd661-114">The `Set-ExecutionPolicy` cmdlet's default scope is **LocalMachine** , which affects everyone who uses the computer.</span></span> <span data-ttu-id="dd661-115">Um die Ausführungs Richtlinie für **LocalMachine** zu ändern, starten Sie PowerShell mit **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="dd661-115">To change the execution policy for **LocalMachine** , start PowerShell with **Run as Administrator** .</span></span>

<span data-ttu-id="dd661-116">Verwenden Sie, um die Ausführungsrichtlinien für jeden Bereich in der Rangfolge anzuzeigen `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="dd661-116">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="dd661-117">Um die effektive Ausführungs Richtlinie für Ihre PowerShell-Sitzung anzuzeigen, verwenden Sie `Get-ExecutionPolicy` ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd661-117">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

## <span data-ttu-id="dd661-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dd661-118">EXAMPLES</span></span>

### <span data-ttu-id="dd661-119">Beispiel 1: Festlegen einer Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="dd661-119">Example 1: Set an execution policy</span></span>

<span data-ttu-id="dd661-120">In diesem Beispiel wird gezeigt, wie die Ausführungs Richtlinie für den lokalen Computer festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="dd661-120">This example shows how to set the execution policy for the local computer.</span></span>

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

<span data-ttu-id="dd661-121">Das `Set-ExecutionPolicy` Cmdlet verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd661-121">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="dd661-122">Der **Scope** -Parameter gibt den Standard Bereichs Wert **LocalMachine** an.</span><span class="sxs-lookup"><span data-stu-id="dd661-122">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span> <span data-ttu-id="dd661-123">Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd661-123">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="dd661-124">Beispiel 2: Festlegen einer Ausführungs Richtlinie, die in Konflikt mit einer Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="dd661-124">Example 2: Set an execution policy that conflicts with a Group Policy</span></span>

<span data-ttu-id="dd661-125">Dieser Befehl versucht, die Ausführungs Richtlinie für den **LocalMachine** -Bereich auf " **restricted** " festzulegen.</span><span class="sxs-lookup"><span data-stu-id="dd661-125">This command attempts to set the **LocalMachine** scope's execution policy to **Restricted** .</span></span>
<span data-ttu-id="dd661-126">" **LocalMachine** " ist restriktiver, aber nicht die wirksame Richtlinie, da Sie mit einer Gruppenrichtlinie in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="dd661-126">**LocalMachine** is more restrictive, but isn't the effective policy because it conflicts with a Group Policy.</span></span> <span data-ttu-id="dd661-127">Die **Eingeschränkte** Richtlinie wird in die Registrierungs Struktur **HKEY_LOCAL_MACHINE** geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd661-127">The **Restricted** policy is written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

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

<span data-ttu-id="dd661-128">Das `Set-ExecutionPolicy` Cmdlet verwendet den **ExecutionPolicy** -Parameter zum Angeben der **eingeschränkten** Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="dd661-128">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **Restricted** policy.</span></span> <span data-ttu-id="dd661-129">Der **Scope** -Parameter gibt den Standard Bereichs Wert **LocalMachine** an.</span><span class="sxs-lookup"><span data-stu-id="dd661-129">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span>
<span data-ttu-id="dd661-130">Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter mit dem **HKLM** -Anbieter, um den Registrierungs Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd661-130">The `Get-ChildItem` cmdlet uses the **Path** parameter with the **HKLM** provider to specify registry location.</span></span>

### <span data-ttu-id="dd661-131">Beispiel 3: Anwenden der Ausführungs Richtlinie von einem Remote Computer auf einen lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="dd661-131">Example 3: Apply the execution policy from a remote computer to a local computer</span></span>

<span data-ttu-id="dd661-132">Mit diesem Befehl wird das Objekt der Ausführungs Richtlinie von einem Remote Computer abgerufen, und die Richtlinie wird auf dem lokalen Computer festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dd661-132">This command gets the execution policy object from a remote computer and sets the policy on the local computer.</span></span> <span data-ttu-id="dd661-133">`Get-ExecutionPolicy` sendet ein **Microsoft.PowerShell.Executionpolicy** -Objekt über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="dd661-133">`Get-ExecutionPolicy` sends a **Microsoft.PowerShell.ExecutionPolicy** object down the pipeline.</span></span> <span data-ttu-id="dd661-134">`Set-ExecutionPolicy` akzeptiert Pipeline Eingaben und erfordert keinen **ExecutionPolicy** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd661-134">`Set-ExecutionPolicy` accepts pipeline input and doesn't require the **ExecutionPolicy** parameter.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

<span data-ttu-id="dd661-135">Das `Invoke-Command` -Cmdlet wird auf dem lokalen Computer ausgeführt und sendet den **ScriptBlock** an den Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="dd661-135">The `Invoke-Command` cmdlet is executed at the local computer and sends the **ScriptBlock** to the remote computer.</span></span> <span data-ttu-id="dd661-136">Der **Computername** -Parameter gibt den Remote Computer an, **Server01** .</span><span class="sxs-lookup"><span data-stu-id="dd661-136">The **ComputerName** parameter specifies the remote computer, **Server01** .</span></span> <span data-ttu-id="dd661-137">Der **ScriptBlock** -Parameter wird `Get-ExecutionPolicy` auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dd661-137">The **ScriptBlock** parameter runs `Get-ExecutionPolicy` on the remote computer.</span></span> <span data-ttu-id="dd661-138">Das `Get-ExecutionPolicy` Objekt wird über die Pipeline an das-Objekt gesendet `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="dd661-138">The `Get-ExecutionPolicy` object is sent down the pipeline to the `Set-ExecutionPolicy`.</span></span>
<span data-ttu-id="dd661-139">`Set-ExecutionPolicy` wendet die Ausführungs Richtlinie auf den Standardbereich " **LocalMachine** " des lokalen Computers an.</span><span class="sxs-lookup"><span data-stu-id="dd661-139">`Set-ExecutionPolicy` applies the execution policy to the local computer's default scope, **LocalMachine** .</span></span>

### <span data-ttu-id="dd661-140">Beispiel 4: Festlegen des Gültigkeits Bereichs für eine Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="dd661-140">Example 4: Set the scope for an execution policy</span></span>

<span data-ttu-id="dd661-141">Dieses Beispiel zeigt, wie eine Ausführungs Richtlinie für einen angegebenen Bereich, **CurrentUser** , festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="dd661-141">This example shows how to set an execution policy for a specified scope, **CurrentUser** .</span></span> <span data-ttu-id="dd661-142">Der Bereich " **CurrentUser** " wirkt sich nur auf den Benutzer aus, der diesen Bereich festlegt.</span><span class="sxs-lookup"><span data-stu-id="dd661-142">The **CurrentUser** scope only affects the user who sets this scope.</span></span>

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

<span data-ttu-id="dd661-143">`Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **AllSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd661-143">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span>
<span data-ttu-id="dd661-144">Der **Scope** -Parameter gibt den **CurrentUser** an.</span><span class="sxs-lookup"><span data-stu-id="dd661-144">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="dd661-145">Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd661-145">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

<span data-ttu-id="dd661-146">Die effektive Ausführungs Richtlinie für den Benutzer wird zu **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="dd661-146">The effective execution policy for the user becomes **AllSigned** .</span></span>

### <span data-ttu-id="dd661-147">Beispiel 5: Entfernen der Ausführungs Richtlinie für den aktuellen Benutzer</span><span class="sxs-lookup"><span data-stu-id="dd661-147">Example 5: Remove the execution policy for the current user</span></span>

<span data-ttu-id="dd661-148">In diesem Beispiel wird gezeigt, wie die nicht **definierte** Ausführungs Richtlinie verwendet wird, um eine Ausführungs Richtlinie für einen bestimmten Bereich zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="dd661-148">This example shows how use the **Undefined** execution policy to remove an execution policy for a specified scope.</span></span>

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

<span data-ttu-id="dd661-149">`Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die nicht **definierte** Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd661-149">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **Undefined** policy.</span></span>
<span data-ttu-id="dd661-150">Der **Scope** -Parameter gibt den **CurrentUser** an.</span><span class="sxs-lookup"><span data-stu-id="dd661-150">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="dd661-151">Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd661-151">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="dd661-152">Beispiel 6: Festlegen der Ausführungs Richtlinie für die aktuelle PowerShell-Sitzung</span><span class="sxs-lookup"><span data-stu-id="dd661-152">Example 6: Set the execution policy for the current PowerShell session</span></span>

<span data-ttu-id="dd661-153">Der **Prozess** Bereich wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="dd661-153">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="dd661-154">Die Ausführungs Richtlinie wird in der Umgebungsvariablen gespeichert `$env:PSExecutionPolicyPreference` und beim Schließen der Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="dd661-154">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference` and is deleted when the session is closed.</span></span>

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

<span data-ttu-id="dd661-155">Der `Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **AllSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd661-155">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span> <span data-ttu-id="dd661-156">Der **Scope** -Parameter gibt den Wert **Prozess** an.</span><span class="sxs-lookup"><span data-stu-id="dd661-156">The **Scope** parameter specifies the value **Process** .</span></span> <span data-ttu-id="dd661-157">Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd661-157">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="dd661-158">Beispiel 7: Entsperren eines Skripts, um es auszuführen, ohne die Ausführungs Richtlinie zu ändern</span><span class="sxs-lookup"><span data-stu-id="dd661-158">Example 7: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="dd661-159">Dieses Beispiel zeigt, wie die **RemoteSigned** -Ausführungs Richtlinie verhindert, dass nicht signierte Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="dd661-159">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="dd661-160">Eine bewährte Vorgehensweise besteht darin, den Skriptcode zu lesen und zu überprüfen, ob er sicher ist, **bevor** Sie das `Unblock-File` Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd661-160">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="dd661-161">Das- `Unblock-File` Cmdlet entsperrt Skripts, sodass Sie ausgeführt werden können, ändert jedoch nicht die Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="dd661-161">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="dd661-162">Der `Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd661-162">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="dd661-163">Die Richtlinie wird für den Standardbereich **LocalMachine** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dd661-163">The policy is set for the default scope, **LocalMachine** .</span></span>

<span data-ttu-id="dd661-164">Das- `Get-ExecutionPolicy` Cmdlet zeigt, dass **RemoteSigned** die effektive Ausführungs Richtlinie für die aktuelle PowerShell-Sitzung ist.</span><span class="sxs-lookup"><span data-stu-id="dd661-164">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="dd661-165">Das **Start-ActivityTracker.ps1** Skript wird aus dem aktuellen Verzeichnis ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dd661-165">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="dd661-166">Das Skript wird von **RemoteSigned** blockiert, da das Skript nicht digital signiert ist.</span><span class="sxs-lookup"><span data-stu-id="dd661-166">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="dd661-167">In diesem Beispiel wurde der Code des Skripts überprüft und als sicher für die Durchführung überprüft.</span><span class="sxs-lookup"><span data-stu-id="dd661-167">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="dd661-168">Das `Unblock-File` Cmdlet verwendet den **path** -Parameter, um die Blockierung des Skripts aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="dd661-168">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="dd661-169">Um zu überprüfen, ob `Unblock-File` die Ausführungs Richtlinie nicht geändert wurde, `Get-ExecutionPolicy` zeigt die effektive Ausführungs Richtlinie " **RemoteSigned** " an.</span><span class="sxs-lookup"><span data-stu-id="dd661-169">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned** .</span></span>

<span data-ttu-id="dd661-170">Das Skript, **Start-ActivityTracker.ps1** aus dem aktuellen Verzeichnis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dd661-170">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="dd661-171">Das Skript beginnt mit der Durchführung der Blockierung durch das `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dd661-171">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="dd661-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dd661-172">PARAMETERS</span></span>

### <span data-ttu-id="dd661-173">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="dd661-173">-ExecutionPolicy</span></span>

<span data-ttu-id="dd661-174">Gibt die Ausführungs Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="dd661-174">Specifies the execution policy.</span></span> <span data-ttu-id="dd661-175">Wenn keine Gruppenrichtlinien vorhanden sind und die Ausführungs Richtlinie jedes Bereichs auf "nicht **definiert** " festgelegt ist, wird die eingeschränkte Richtlinie für alle Benutzer **eingeschränkt** .</span><span class="sxs-lookup"><span data-stu-id="dd661-175">If there are no Group Policies and each scope's execution policy is set to **Undefined** , then **Restricted** becomes the effective policy for all users.</span></span>

<span data-ttu-id="dd661-176">Die zulässigen Werte für die Ausführungs Richtlinie lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="dd661-176">The acceptable execution policy values are as follows:</span></span>

- <span data-ttu-id="dd661-177">Alle **signiert** .</span><span class="sxs-lookup"><span data-stu-id="dd661-177">**AllSigned** .</span></span> <span data-ttu-id="dd661-178">Erfordert, dass alle Skripts und Konfigurationsdateien von einem vertrauenswürdigen Herausgeber signiert werden, einschließlich der auf dem lokalen Computer geschriebenen Skripts.</span><span class="sxs-lookup"><span data-stu-id="dd661-178">Requires that all scripts and configuration files are signed by a trusted publisher, including scripts written on the local computer.</span></span>
- <span data-ttu-id="dd661-179">**Umgehung** .</span><span class="sxs-lookup"><span data-stu-id="dd661-179">**Bypass** .</span></span> <span data-ttu-id="dd661-180">Es findet keine Blockierung statt und es werden keine Warnungen oder Eingabeaufforderungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="dd661-180">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="dd661-181">**Default** .</span><span class="sxs-lookup"><span data-stu-id="dd661-181">**Default** .</span></span> <span data-ttu-id="dd661-182">Legt die Standard Ausführungs Richtlinie fest.</span><span class="sxs-lookup"><span data-stu-id="dd661-182">Sets the default execution policy.</span></span> <span data-ttu-id="dd661-183">**Eingeschränkt** für Windows-Clients oder **RemoteSigned** für Windows-Server.</span><span class="sxs-lookup"><span data-stu-id="dd661-183">**Restricted** for Windows clients or **RemoteSigned** for Windows servers.</span></span>
- <span data-ttu-id="dd661-184">**RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="dd661-184">**RemoteSigned** .</span></span> <span data-ttu-id="dd661-185">Erfordert, dass alle aus dem Internet heruntergeladenen Skripts und Konfigurationsdateien von einem vertrauenswürdigen Herausgeber signiert werden.</span><span class="sxs-lookup"><span data-stu-id="dd661-185">Requires that all scripts and configuration files downloaded from the Internet are signed by a trusted publisher.</span></span> <span data-ttu-id="dd661-186">Die Standard Ausführungs Richtlinie für Windows Server-Computer.</span><span class="sxs-lookup"><span data-stu-id="dd661-186">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="dd661-187">**Eingeschränkt** .</span><span class="sxs-lookup"><span data-stu-id="dd661-187">**Restricted** .</span></span> <span data-ttu-id="dd661-188">Lädt keine Konfigurationsdateien und führt keine Skripts aus.</span><span class="sxs-lookup"><span data-stu-id="dd661-188">Doesn't load configuration files or run scripts.</span></span> <span data-ttu-id="dd661-189">Die Standard-Ausführungs Richtlinie für Windows-Client Computer.</span><span class="sxs-lookup"><span data-stu-id="dd661-189">The default execution policy Windows client computers.</span></span>
- <span data-ttu-id="dd661-190">Nicht **definiert** .</span><span class="sxs-lookup"><span data-stu-id="dd661-190">**Undefined** .</span></span> <span data-ttu-id="dd661-191">Für den Bereich wurde keine Ausführungs Richtlinie festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dd661-191">No execution policy is set for the scope.</span></span> <span data-ttu-id="dd661-192">Entfernt eine zugewiesene Ausführungs Richtlinie aus einem Bereich, der nicht von einem Gruppenrichtlinie festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="dd661-192">Removes an assigned execution policy from a scope that is not set by a Group Policy.</span></span> <span data-ttu-id="dd661-193">Wenn die Ausführungs Richtlinie in allen Bereichen nicht **definiert** ist, ist die effektive Ausführungs Richtlinie **eingeschränkt** .</span><span class="sxs-lookup"><span data-stu-id="dd661-193">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** .</span></span>
- <span data-ttu-id="dd661-194">**Uneingeschränkt** .</span><span class="sxs-lookup"><span data-stu-id="dd661-194">**Unrestricted** .</span></span> <span data-ttu-id="dd661-195">Lädt alle Konfigurationsdateien und führt alle Skripts aus.</span><span class="sxs-lookup"><span data-stu-id="dd661-195">Loads all configuration files and runs all scripts.</span></span> <span data-ttu-id="dd661-196">Wenn Sie ein unsigniertes Skript ausführen, das aus dem Internet heruntergeladen wurde, werden Sie vor dem Ausführen nach der Berechtigung gefragt.</span><span class="sxs-lookup"><span data-stu-id="dd661-196">If you run an unsigned script that was downloaded from the Internet, you are prompted for permission before it runs.</span></span>

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

### <span data-ttu-id="dd661-197">-Force</span><span class="sxs-lookup"><span data-stu-id="dd661-197">-Force</span></span>

<span data-ttu-id="dd661-198">Unterdrückt alle Bestätigungsaufforderungen.</span><span class="sxs-lookup"><span data-stu-id="dd661-198">Suppresses all the confirmation prompts.</span></span> <span data-ttu-id="dd661-199">Verwenden Sie diesen Parameter als Vorsicht, um unerwartete Ergebnisse zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="dd661-199">Use caution with this parameter to avoid unexpected results.</span></span>

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

### <span data-ttu-id="dd661-200">-Bereich</span><span class="sxs-lookup"><span data-stu-id="dd661-200">-Scope</span></span>

<span data-ttu-id="dd661-201">Gibt den Bereich an, der von einer Ausführungs Richtlinie betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="dd661-201">Specifies the scope that is affected by an execution policy.</span></span> <span data-ttu-id="dd661-202">Der Standardbereich ist **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="dd661-202">The default scope is **LocalMachine** .</span></span>

<span data-ttu-id="dd661-203">Die effektive Ausführungs Richtlinie wird wie folgt durch die Rangfolge bestimmt:</span><span class="sxs-lookup"><span data-stu-id="dd661-203">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="dd661-204">**MachinePolicy** .</span><span class="sxs-lookup"><span data-stu-id="dd661-204">**MachinePolicy** .</span></span> <span data-ttu-id="dd661-205">Wird von einem Gruppenrichtlinie für alle Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dd661-205">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="dd661-206">**UserPolicy** .</span><span class="sxs-lookup"><span data-stu-id="dd661-206">**UserPolicy** .</span></span> <span data-ttu-id="dd661-207">Wird von einem Gruppenrichtlinie für den aktuellen Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dd661-207">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="dd661-208">**Verarbeiten** .</span><span class="sxs-lookup"><span data-stu-id="dd661-208">**Process** .</span></span> <span data-ttu-id="dd661-209">Wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="dd661-209">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="dd661-210">**CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="dd661-210">**CurrentUser** .</span></span> <span data-ttu-id="dd661-211">Wirkt sich nur auf den aktuellen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="dd661-211">Affects only the current user.</span></span>
- <span data-ttu-id="dd661-212">**LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="dd661-212">**LocalMachine** .</span></span> <span data-ttu-id="dd661-213">Standardbereich, der sich auf alle Benutzer des Computers auswirkt.</span><span class="sxs-lookup"><span data-stu-id="dd661-213">Default scope that affects all users of the computer.</span></span>

<span data-ttu-id="dd661-214">Der **Prozess** Bereich wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="dd661-214">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="dd661-215">Die Ausführungs Richtlinie wird in der-Umgebungsvariablen und `$env:PSExecutionPolicyPreference` nicht in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dd661-215">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="dd661-216">Wenn die PowerShell-Sitzung geschlossen ist, werden die Variable und der Wert gelöscht.</span><span class="sxs-lookup"><span data-stu-id="dd661-216">When the PowerShell session is closed, the variable and value are deleted.</span></span>

<span data-ttu-id="dd661-217">Ausführungsrichtlinien für den Bereich **CurrentUser** werden in die Registrierungs Struktur **HKEY_LOCAL_USER** geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd661-217">Execution policies for the **CurrentUser** scope are written to the registry hive **HKEY_LOCAL_USER** .</span></span>

<span data-ttu-id="dd661-218">Ausführungsrichtlinien für den Bereich " **LocalMachine** " werden in die Registrierungs Struktur **HKEY_LOCAL_MACHINE** geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd661-218">Execution policies for the **LocalMachine** scope are written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

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

### <span data-ttu-id="dd661-219">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dd661-219">-Confirm</span></span>

<span data-ttu-id="dd661-220">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="dd661-220">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="dd661-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dd661-221">-WhatIf</span></span>

<span data-ttu-id="dd661-222">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dd661-222">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="dd661-223">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dd661-223">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="dd661-224">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dd661-224">CommonParameters</span></span>

<span data-ttu-id="dd661-225">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dd661-225">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dd661-226">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dd661-226">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dd661-227">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dd661-227">INPUTS</span></span>

### <span data-ttu-id="dd661-228">Microsoft.PowerShell.Executionpolicy, System. String</span><span class="sxs-lookup"><span data-stu-id="dd661-228">Microsoft.PowerShell.ExecutionPolicy, System.String</span></span>

<span data-ttu-id="dd661-229">Sie können ein Ausführungsrichtlinien Objekt oder eine Zeichenfolge, die den Namen einer Ausführungs Richtlinie enthält, über die Pipeline an übergeben `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="dd661-229">You can pipe an execution policy object or a string that contains the name of an execution policy to `Set-ExecutionPolicy`.</span></span>

## <span data-ttu-id="dd661-230">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dd661-230">OUTPUTS</span></span>

### <span data-ttu-id="dd661-231">Keine</span><span class="sxs-lookup"><span data-stu-id="dd661-231">None</span></span>

<span data-ttu-id="dd661-232">`Set-ExecutionPolicy` gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="dd661-232">`Set-ExecutionPolicy` doesn't return any output.</span></span>

## <span data-ttu-id="dd661-233">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dd661-233">NOTES</span></span>

<span data-ttu-id="dd661-234">`Set-ExecutionPolicy` ändert nicht die Bereiche **MachinePolicy** und **UserPolicy** , da diese durch Gruppenrichtlinien festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="dd661-234">`Set-ExecutionPolicy` doesn't change the **MachinePolicy** and **UserPolicy** scopes because they are set by Group Policies.</span></span>

<span data-ttu-id="dd661-235">`Set-ExecutionPolicy` überschreibt eine Gruppenrichtlinie nicht, auch wenn die Benutzereinstellung restriktiver als die Richtlinie ist.</span><span class="sxs-lookup"><span data-stu-id="dd661-235">`Set-ExecutionPolicy` doesn't override a Group Policy, even if the user preference is more restrictive than the policy.</span></span>

<span data-ttu-id="dd661-236">Wenn die Gruppenrichtlinie **Skriptausführung** aktivieren für den Computer oder Benutzer aktiviert ist, wird die Benutzereinstellung gespeichert, aber Sie ist nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="dd661-236">If the Group Policy **Turn on Script Execution** is enabled for the computer or user, the user preference is saved, but it is not effective.</span></span> <span data-ttu-id="dd661-237">PowerShell zeigt eine Meldung an, in der der Konflikt erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="dd661-237">PowerShell displays a message that explains the conflict.</span></span>

## <span data-ttu-id="dd661-238">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dd661-238">RELATED LINKS</span></span>

[<span data-ttu-id="dd661-239">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="dd661-239">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="dd661-240">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="dd661-240">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="dd661-241">about_Providers</span><span class="sxs-lookup"><span data-stu-id="dd661-241">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="dd661-242">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="dd661-242">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="dd661-243">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="dd661-243">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="dd661-244">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="dd661-244">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="dd661-245">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="dd661-245">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="dd661-246">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="dd661-246">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="dd661-247">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="dd661-247">Unblock-File</span></span>](../Microsoft.PowerShell.Utility/Unblock-File.md)
