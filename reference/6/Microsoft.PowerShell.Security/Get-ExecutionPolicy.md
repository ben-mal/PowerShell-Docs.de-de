---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: f798aaef7032db450a13d79589eb7dd0ca762cd6
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344829"
---
# <span data-ttu-id="40dd6-103">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="40dd6-103">Get-ExecutionPolicy</span></span>

## <span data-ttu-id="40dd6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="40dd6-104">SYNOPSIS</span></span>
<span data-ttu-id="40dd6-105">Ruft die Ausführungsrichtlinien für die aktuelle Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="40dd6-105">Gets the execution policies for the current session.</span></span>

## <span data-ttu-id="40dd6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40dd6-106">SYNTAX</span></span>

### <span data-ttu-id="40dd6-107">Alle</span><span class="sxs-lookup"><span data-stu-id="40dd6-107">All</span></span>

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## <span data-ttu-id="40dd6-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="40dd6-108">DESCRIPTION</span></span>

<span data-ttu-id="40dd6-109">Verwenden Sie, um die Ausführungsrichtlinien für jeden Bereich in der Rangfolge anzuzeigen `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="40dd6-109">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="40dd6-110">Um die effektive Ausführungs Richtlinie für Ihre PowerShell-Sitzung anzuzeigen, verwenden Sie `Get-ExecutionPolicy` ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="40dd6-110">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

<span data-ttu-id="40dd6-111">Die effektive Ausführungs Richtlinie wird durch die von und festgelegten Ausführungsrichtlinien `Set-ExecutionPolicy` und Gruppenrichtlinie Einstellungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="40dd6-111">The effective execution policy is determined by execution policies that are set by `Set-ExecutionPolicy` and Group Policy settings.</span></span>

<span data-ttu-id="40dd6-112">Weitere Informationen finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="40dd6-112">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="40dd6-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="40dd6-113">EXAMPLES</span></span>

### <span data-ttu-id="40dd6-114">Beispiel 1: alle Ausführungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="40dd6-114">Example 1: Get all execution policies</span></span>

<span data-ttu-id="40dd6-115">Dieser Befehl zeigt die Ausführungsrichtlinien für jeden Bereich in der Rangfolge an.</span><span class="sxs-lookup"><span data-stu-id="40dd6-115">This command displays the execution policies for each scope in the order of precedence.</span></span>

```powershell
Get-ExecutionPolicy -List
```

```Output
Scope          ExecutionPolicy
-----          ---------------
MachinePolicy  Undefined
UserPolicy     Undefined
Process        Undefined
CurrentUser    AllSigned
LocalMachine   Undefined
```

<span data-ttu-id="40dd6-116">Das `Get-ExecutionPolicy` Cmdlet verwendet den **List** -Parameter, um die Ausführungs Richtlinie jedes Bereichs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="40dd6-116">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span>

### <span data-ttu-id="40dd6-117">Beispiel 2: Festlegen einer Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="40dd6-117">Example 2: Set an execution policy</span></span>

<span data-ttu-id="40dd6-118">Dieses Beispiel zeigt, wie eine Ausführungs Richtlinie für den lokalen Computer festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="40dd6-118">This example shows how to set an execution policy for the local computer.</span></span>

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
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="40dd6-119">Das `Set-ExecutionPolicy` Cmdlet verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="40dd6-119">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="40dd6-120">Der **Scope** -Parameter gibt den Standard Bereichs Wert **LocalMachine** an.</span><span class="sxs-lookup"><span data-stu-id="40dd6-120">The **Scope** parameter specifies the default scope value, **LocalMachine**.</span></span> <span data-ttu-id="40dd6-121">Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="40dd6-121">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="40dd6-122">Beispiel 3: erhalten der effektiven Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="40dd6-122">Example 3: Get the effective execution policy</span></span>

<span data-ttu-id="40dd6-123">Dieses Beispiel zeigt, wie die effektive Ausführungs Richtlinie für eine PowerShell-Sitzung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="40dd6-123">This example shows how to display the effective execution policy for a PowerShell session.</span></span>

```
PS> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned

PS> Get-ExecutionPolicy

AllSigned
```

<span data-ttu-id="40dd6-124">Das `Get-ExecutionPolicy` Cmdlet verwendet den **List** -Parameter, um die Ausführungs Richtlinie jedes Bereichs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="40dd6-124">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span> <span data-ttu-id="40dd6-125">Das `Get-ExecutionPolicy` Cmdlet wird ohne einen Parameter ausgeführt, um die effektive Ausführungs Richtlinie " **AllSigned** " anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="40dd6-125">The `Get-ExecutionPolicy` cmdlet is run without a parameter to display the effective execution policy, **AllSigned**.</span></span>

### <span data-ttu-id="40dd6-126">Beispiel 4: Entsperren eines Skripts, um es auszuführen, ohne die Ausführungs Richtlinie zu ändern</span><span class="sxs-lookup"><span data-stu-id="40dd6-126">Example 4: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="40dd6-127">Dieses Beispiel zeigt, wie die **RemoteSigned** -Ausführungs Richtlinie verhindert, dass nicht signierte Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="40dd6-127">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="40dd6-128">Eine bewährte Vorgehensweise besteht darin, den Skriptcode zu lesen und zu überprüfen, ob er sicher ist, **bevor** Sie das `Unblock-File` Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="40dd6-128">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="40dd6-129">Das- `Unblock-File` Cmdlet entsperrt Skripts, sodass Sie ausgeführt werden können, ändert jedoch nicht die Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="40dd6-129">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="40dd6-130">Der `Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="40dd6-130">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="40dd6-131">Die Richtlinie wird für den Standardbereich **LocalMachine** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="40dd6-131">The policy is set for the default scope, **LocalMachine**.</span></span>

<span data-ttu-id="40dd6-132">Das- `Get-ExecutionPolicy` Cmdlet zeigt, dass **RemoteSigned** die effektive Ausführungs Richtlinie für die aktuelle PowerShell-Sitzung ist.</span><span class="sxs-lookup"><span data-stu-id="40dd6-132">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="40dd6-133">Das **Start-ActivityTracker.ps1** Skript wird aus dem aktuellen Verzeichnis ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="40dd6-133">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="40dd6-134">Das Skript wird von **RemoteSigned** blockiert, da das Skript nicht digital signiert ist.</span><span class="sxs-lookup"><span data-stu-id="40dd6-134">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="40dd6-135">In diesem Beispiel wurde der Code des Skripts überprüft und als sicher für die Durchführung überprüft.</span><span class="sxs-lookup"><span data-stu-id="40dd6-135">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="40dd6-136">Das `Unblock-File` Cmdlet verwendet den **path** -Parameter, um die Blockierung des Skripts aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="40dd6-136">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="40dd6-137">Um zu überprüfen, ob `Unblock-File` die Ausführungs Richtlinie nicht geändert wurde, `Get-ExecutionPolicy` zeigt die effektive Ausführungs Richtlinie " **RemoteSigned** " an.</span><span class="sxs-lookup"><span data-stu-id="40dd6-137">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned**.</span></span>

<span data-ttu-id="40dd6-138">Das Skript, **Start-ActivityTracker.ps1** aus dem aktuellen Verzeichnis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="40dd6-138">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="40dd6-139">Das Skript beginnt mit der Durchführung der Blockierung durch das `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40dd6-139">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="40dd6-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40dd6-140">PARAMETERS</span></span>

### <span data-ttu-id="40dd6-141">-List</span><span class="sxs-lookup"><span data-stu-id="40dd6-141">-List</span></span>

<span data-ttu-id="40dd6-142">Ruft alle Ausführungsrichtlinienwerte für die Sitzung nach ihrer Rangfolge ab.</span><span class="sxs-lookup"><span data-stu-id="40dd6-142">Gets all execution policy values for the session listed in precedence order.</span></span> <span data-ttu-id="40dd6-143">Standardmäßig ruft `Get-ExecutionPolicy` nur die effektive Ausführungs Richtlinie ab.</span><span class="sxs-lookup"><span data-stu-id="40dd6-143">By default, `Get-ExecutionPolicy` gets only the effective execution policy.</span></span>

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

### <span data-ttu-id="40dd6-144">-Bereich</span><span class="sxs-lookup"><span data-stu-id="40dd6-144">-Scope</span></span>

<span data-ttu-id="40dd6-145">Gibt den Bereich an, der von einer Ausführungs Richtlinie betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="40dd6-145">Specifies the scope that is affected by an execution policy.</span></span>

<span data-ttu-id="40dd6-146">Die effektive Ausführungs Richtlinie wird wie folgt durch die Rangfolge bestimmt:</span><span class="sxs-lookup"><span data-stu-id="40dd6-146">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="40dd6-147">**MachinePolicy**.</span><span class="sxs-lookup"><span data-stu-id="40dd6-147">**MachinePolicy**.</span></span> <span data-ttu-id="40dd6-148">Wird von einem Gruppenrichtlinie für alle Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="40dd6-148">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="40dd6-149">**UserPolicy**.</span><span class="sxs-lookup"><span data-stu-id="40dd6-149">**UserPolicy**.</span></span> <span data-ttu-id="40dd6-150">Wird von einem Gruppenrichtlinie für den aktuellen Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="40dd6-150">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="40dd6-151">**Verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="40dd6-151">**Process**.</span></span> <span data-ttu-id="40dd6-152">Wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="40dd6-152">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="40dd6-153">**CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="40dd6-153">**CurrentUser**.</span></span> <span data-ttu-id="40dd6-154">Wirkt sich nur auf den aktuellen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="40dd6-154">Affects only the current user.</span></span>
- <span data-ttu-id="40dd6-155">**LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="40dd6-155">**LocalMachine**.</span></span> <span data-ttu-id="40dd6-156">Standardbereich, der sich auf alle Benutzer des Computers auswirkt.</span><span class="sxs-lookup"><span data-stu-id="40dd6-156">Default scope that affects all users of the computer.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 0
Default value: Effective execution policy
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="40dd6-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="40dd6-157">CommonParameters</span></span>

<span data-ttu-id="40dd6-158">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="40dd6-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40dd6-159">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="40dd6-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40dd6-160">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="40dd6-160">INPUTS</span></span>

### <span data-ttu-id="40dd6-161">Keine</span><span class="sxs-lookup"><span data-stu-id="40dd6-161">None</span></span>

<span data-ttu-id="40dd6-162">`Get-ExecutionPolicy` akzeptiert keine Eingaben aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="40dd6-162">`Get-ExecutionPolicy` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="40dd6-163">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="40dd6-163">OUTPUTS</span></span>

### <span data-ttu-id="40dd6-164">Microsoft.PowerShell.Executionpolicy</span><span class="sxs-lookup"><span data-stu-id="40dd6-164">Microsoft.PowerShell.ExecutionPolicy</span></span>

<span data-ttu-id="40dd6-165">Das Cmdlet gibt immer **uneingeschränkt** auf Linux-und macOS-Plattformen zurück.</span><span class="sxs-lookup"><span data-stu-id="40dd6-165">The cmdlet always returns **Unrestricted** on Linux and macOS platforms.</span></span>

## <span data-ttu-id="40dd6-166">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="40dd6-166">NOTES</span></span>

<span data-ttu-id="40dd6-167">Eine Ausführungs Richtlinie ist Bestandteil der PowerShell-Sicherheitsstrategie.</span><span class="sxs-lookup"><span data-stu-id="40dd6-167">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="40dd6-168">Ausführungsrichtlinien legen fest, ob Sie Konfigurationsdateien, z. b. Ihr PowerShell-Profil, laden oder Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="40dd6-168">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="40dd6-169">Und, ob Skripts vor der Durchführung digital signiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="40dd6-169">And, whether scripts must be digitally signed before they are run.</span></span>

## <span data-ttu-id="40dd6-170">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="40dd6-170">RELATED LINKS</span></span>

[<span data-ttu-id="40dd6-171">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="40dd6-171">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[<span data-ttu-id="40dd6-172">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="40dd6-172">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="40dd6-173">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="40dd6-173">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="40dd6-174">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="40dd6-174">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="40dd6-175">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="40dd6-175">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)
