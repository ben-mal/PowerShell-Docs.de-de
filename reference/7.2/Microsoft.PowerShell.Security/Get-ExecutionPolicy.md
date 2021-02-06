---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: d6555f1abc824add4613654461106af34045e1a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601101"
---
# <span data-ttu-id="f8d5b-102">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="f8d5b-102">Get-ExecutionPolicy</span></span>

## <span data-ttu-id="f8d5b-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f8d5b-103">SYNOPSIS</span></span>
<span data-ttu-id="f8d5b-104">Ruft die Ausführungsrichtlinien für die aktuelle Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-104">Gets the execution policies for the current session.</span></span>

## <span data-ttu-id="f8d5b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f8d5b-105">SYNTAX</span></span>

### <span data-ttu-id="f8d5b-106">Alle</span><span class="sxs-lookup"><span data-stu-id="f8d5b-106">All</span></span>

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## <span data-ttu-id="f8d5b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f8d5b-107">DESCRIPTION</span></span>

<span data-ttu-id="f8d5b-108">Verwenden Sie, um die Ausführungsrichtlinien für jeden Bereich in der Rangfolge anzuzeigen `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="f8d5b-108">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="f8d5b-109">Um die effektive Ausführungs Richtlinie für Ihre PowerShell-Sitzung anzuzeigen, verwenden Sie `Get-ExecutionPolicy` ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-109">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

<span data-ttu-id="f8d5b-110">Die effektive Ausführungs Richtlinie wird durch die von und festgelegten Ausführungsrichtlinien `Set-ExecutionPolicy` und Gruppenrichtlinie Einstellungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-110">The effective execution policy is determined by execution policies that are set by `Set-ExecutionPolicy` and Group Policy settings.</span></span>

<span data-ttu-id="f8d5b-111">Weitere Informationen finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="f8d5b-111">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="f8d5b-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f8d5b-112">EXAMPLES</span></span>

### <span data-ttu-id="f8d5b-113">Beispiel 1: alle Ausführungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f8d5b-113">Example 1: Get all execution policies</span></span>

<span data-ttu-id="f8d5b-114">Dieser Befehl zeigt die Ausführungsrichtlinien für jeden Bereich in der Rangfolge an.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-114">This command displays the execution policies for each scope in the order of precedence.</span></span>

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

<span data-ttu-id="f8d5b-115">Das `Get-ExecutionPolicy` Cmdlet verwendet den **List** -Parameter, um die Ausführungs Richtlinie jedes Bereichs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-115">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span>

### <span data-ttu-id="f8d5b-116">Beispiel 2: Festlegen einer Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f8d5b-116">Example 2: Set an execution policy</span></span>

<span data-ttu-id="f8d5b-117">Dieses Beispiel zeigt, wie eine Ausführungs Richtlinie für den lokalen Computer festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-117">This example shows how to set an execution policy for the local computer.</span></span>

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

<span data-ttu-id="f8d5b-118">Das `Set-ExecutionPolicy` Cmdlet verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-118">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="f8d5b-119">Der **Scope** -Parameter gibt den Standard Bereichs Wert **LocalMachine** an.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-119">The **Scope** parameter specifies the default scope value, **LocalMachine**.</span></span> <span data-ttu-id="f8d5b-120">Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-120">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="f8d5b-121">Beispiel 3: erhalten der effektiven Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f8d5b-121">Example 3: Get the effective execution policy</span></span>

<span data-ttu-id="f8d5b-122">Dieses Beispiel zeigt, wie die effektive Ausführungs Richtlinie für eine PowerShell-Sitzung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-122">This example shows how to display the effective execution policy for a PowerShell session.</span></span>

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

<span data-ttu-id="f8d5b-123">Das `Get-ExecutionPolicy` Cmdlet verwendet den **List** -Parameter, um die Ausführungs Richtlinie jedes Bereichs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-123">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span> <span data-ttu-id="f8d5b-124">Das `Get-ExecutionPolicy` Cmdlet wird ohne einen Parameter ausgeführt, um die effektive Ausführungs Richtlinie " **AllSigned**" anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-124">The `Get-ExecutionPolicy` cmdlet is run without a parameter to display the effective execution policy, **AllSigned**.</span></span>

### <span data-ttu-id="f8d5b-125">Beispiel 4: Entsperren eines Skripts, um es auszuführen, ohne die Ausführungs Richtlinie zu ändern</span><span class="sxs-lookup"><span data-stu-id="f8d5b-125">Example 4: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="f8d5b-126">Dieses Beispiel zeigt, wie die **RemoteSigned** -Ausführungs Richtlinie verhindert, dass nicht signierte Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-126">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="f8d5b-127">Eine bewährte Vorgehensweise besteht darin, den Skriptcode zu lesen und zu überprüfen, ob er sicher ist, **bevor** Sie das `Unblock-File` Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-127">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="f8d5b-128">Das- `Unblock-File` Cmdlet entsperrt Skripts, sodass Sie ausgeführt werden können, ändert jedoch nicht die Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-128">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="f8d5b-129">Der `Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-129">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="f8d5b-130">Die Richtlinie wird für den Standardbereich **LocalMachine** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-130">The policy is set for the default scope, **LocalMachine**.</span></span>

<span data-ttu-id="f8d5b-131">Das- `Get-ExecutionPolicy` Cmdlet zeigt, dass **RemoteSigned** die effektive Ausführungs Richtlinie für die aktuelle PowerShell-Sitzung ist.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-131">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="f8d5b-132">Das **Start-ActivityTracker.ps1** Skript wird aus dem aktuellen Verzeichnis ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-132">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="f8d5b-133">Das Skript wird von **RemoteSigned** blockiert, da das Skript nicht digital signiert ist.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-133">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="f8d5b-134">In diesem Beispiel wurde der Code des Skripts überprüft und als sicher für die Durchführung überprüft.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-134">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="f8d5b-135">Das `Unblock-File` Cmdlet verwendet den **path** -Parameter, um die Blockierung des Skripts aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-135">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="f8d5b-136">Um zu überprüfen, ob `Unblock-File` die Ausführungs Richtlinie nicht geändert wurde, `Get-ExecutionPolicy` zeigt die effektive Ausführungs Richtlinie " **RemoteSigned**" an.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-136">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned**.</span></span>

<span data-ttu-id="f8d5b-137">Das Skript, **Start-ActivityTracker.ps1** aus dem aktuellen Verzeichnis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-137">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="f8d5b-138">Das Skript beginnt mit der Durchführung der Blockierung durch das `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-138">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="f8d5b-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f8d5b-139">PARAMETERS</span></span>

### <span data-ttu-id="f8d5b-140">-List</span><span class="sxs-lookup"><span data-stu-id="f8d5b-140">-List</span></span>

<span data-ttu-id="f8d5b-141">Ruft alle Ausführungsrichtlinienwerte für die Sitzung nach ihrer Rangfolge ab.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-141">Gets all execution policy values for the session listed in precedence order.</span></span> <span data-ttu-id="f8d5b-142">Standardmäßig ruft `Get-ExecutionPolicy` nur die effektive Ausführungs Richtlinie ab.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-142">By default, `Get-ExecutionPolicy` gets only the effective execution policy.</span></span>

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

### <span data-ttu-id="f8d5b-143">-Bereich</span><span class="sxs-lookup"><span data-stu-id="f8d5b-143">-Scope</span></span>

<span data-ttu-id="f8d5b-144">Gibt den Bereich an, der von einer Ausführungs Richtlinie betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-144">Specifies the scope that is affected by an execution policy.</span></span>

<span data-ttu-id="f8d5b-145">Die effektive Ausführungs Richtlinie wird wie folgt durch die Rangfolge bestimmt:</span><span class="sxs-lookup"><span data-stu-id="f8d5b-145">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="f8d5b-146">**MachinePolicy**.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-146">**MachinePolicy**.</span></span> <span data-ttu-id="f8d5b-147">Wird von einem Gruppenrichtlinie für alle Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-147">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="f8d5b-148">**UserPolicy**.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-148">**UserPolicy**.</span></span> <span data-ttu-id="f8d5b-149">Wird von einem Gruppenrichtlinie für den aktuellen Benutzer des Computers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-149">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="f8d5b-150">**Verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-150">**Process**.</span></span> <span data-ttu-id="f8d5b-151">Wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-151">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="f8d5b-152">**CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-152">**CurrentUser**.</span></span> <span data-ttu-id="f8d5b-153">Wirkt sich nur auf den aktuellen Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-153">Affects only the current user.</span></span>
- <span data-ttu-id="f8d5b-154">**LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-154">**LocalMachine**.</span></span> <span data-ttu-id="f8d5b-155">Standardbereich, der sich auf alle Benutzer des Computers auswirkt.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-155">Default scope that affects all users of the computer.</span></span>

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

### <span data-ttu-id="f8d5b-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f8d5b-156">CommonParameters</span></span>

<span data-ttu-id="f8d5b-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f8d5b-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f8d5b-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f8d5b-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f8d5b-159">INPUTS</span></span>

### <span data-ttu-id="f8d5b-160">Keine</span><span class="sxs-lookup"><span data-stu-id="f8d5b-160">None</span></span>

<span data-ttu-id="f8d5b-161">`Get-ExecutionPolicy` akzeptiert keine Eingaben aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-161">`Get-ExecutionPolicy` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="f8d5b-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f8d5b-162">OUTPUTS</span></span>

### <span data-ttu-id="f8d5b-163">Microsoft.PowerShell.Executionpolicy</span><span class="sxs-lookup"><span data-stu-id="f8d5b-163">Microsoft.PowerShell.ExecutionPolicy</span></span>

<span data-ttu-id="f8d5b-164">Das Cmdlet gibt immer **uneingeschränkt** auf Linux-und macOS-Plattformen zurück.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-164">The cmdlet always returns **Unrestricted** on Linux and macOS platforms.</span></span>

## <span data-ttu-id="f8d5b-165">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f8d5b-165">NOTES</span></span>

<span data-ttu-id="f8d5b-166">Eine Ausführungs Richtlinie ist Bestandteil der PowerShell-Sicherheitsstrategie.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-166">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="f8d5b-167">Ausführungsrichtlinien legen fest, ob Sie Konfigurationsdateien, z. b. Ihr PowerShell-Profil, laden oder Skripts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-167">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="f8d5b-168">Und, ob Skripts vor der Durchführung digital signiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f8d5b-168">And, whether scripts must be digitally signed before they are run.</span></span>

## <span data-ttu-id="f8d5b-169">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f8d5b-169">RELATED LINKS</span></span>

[<span data-ttu-id="f8d5b-170">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="f8d5b-170">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[<span data-ttu-id="f8d5b-171">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="f8d5b-171">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="f8d5b-172">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="f8d5b-172">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="f8d5b-173">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="f8d5b-173">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="f8d5b-174">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="f8d5b-174">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)
