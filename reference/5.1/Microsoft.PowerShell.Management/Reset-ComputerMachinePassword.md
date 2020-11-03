---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
ms.openlocfilehash: 1484bc83b9503ce43420b833a1b78b3c4215d98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214487"
---
# <span data-ttu-id="dda6e-103">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="dda6e-103">Reset-ComputerMachinePassword</span></span>

## <span data-ttu-id="dda6e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dda6e-104">SYNOPSIS</span></span>
<span data-ttu-id="dda6e-105">Setzt das Kennwort für das Computerkonto des Computers zurück.</span><span class="sxs-lookup"><span data-stu-id="dda6e-105">Resets the machine account password for the computer.</span></span>

## <span data-ttu-id="dda6e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dda6e-106">SYNTAX</span></span>

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="dda6e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dda6e-107">DESCRIPTION</span></span>
<span data-ttu-id="dda6e-108">Mit dem " **Reset-ComputerMachinePassword"-** Cmdlet wird das Computer Konto Kennwort geändert, das die Computer für die Authentifizierung bei den Domänen Controllern in der Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="dda6e-108">The **Reset-ComputerMachinePassword** cmdlet changes the computer account password that the computers use to authenticate to the domain controllers in the domain.</span></span>
<span data-ttu-id="dda6e-109">Sie können hiermit das Kennwort des lokalen Computers zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="dda6e-109">You can use it to reset the password of the local computer.</span></span>

## <span data-ttu-id="dda6e-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dda6e-110">EXAMPLES</span></span>

### <span data-ttu-id="dda6e-111">Beispiel 1: Zurücksetzen des Kennworts für den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="dda6e-111">Example 1: Reset the password for the local computer</span></span>

```
PS C:\> Reset-ComputerMachinePassword
```

<span data-ttu-id="dda6e-112">Mit diesem Befehl wird das Computer Kennwort für den lokalen Computer zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="dda6e-112">This command resets the computer password for the local computer.</span></span>
<span data-ttu-id="dda6e-113">Der Befehl wird mit den Anmeldeinformationen des aktuellen Benutzers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dda6e-113">The command runs with the credentials of the current user.</span></span>

### <span data-ttu-id="dda6e-114">Beispiel 2: Zurücksetzen des Kennworts für den lokalen Computer mithilfe eines angegebenen Domänen Controllers</span><span class="sxs-lookup"><span data-stu-id="dda6e-114">Example 2: Reset the password for the local computer by using a specified domain controller</span></span>

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

<span data-ttu-id="dda6e-115">Dieser Befehl setzt das Computer Kennwort des lokalen Computers mithilfe des DC01-Domänen Controllers zurück.</span><span class="sxs-lookup"><span data-stu-id="dda6e-115">This command resets the computer password of the local computer by using the DC01 domain controller.</span></span>
<span data-ttu-id="dda6e-116">Er verwendet den *Credential* -Parameter, um ein Benutzerkonto anzugeben, das über die Berechtigung zum Zurücksetzen eines Computer Kennworts in der Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="dda6e-116">It uses the *Credential* parameter to specify a user account that has permission to reset a computer password in the domain.</span></span>

### <span data-ttu-id="dda6e-117">Beispiel 3: Zurücksetzen des Kennworts auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="dda6e-117">Example 3: Reset the password on a remote computer</span></span>

```
$cred = Get-Credential
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword -Credential $using:cred}
```

<span data-ttu-id="dda6e-118">Dieser Befehl verwendet das Cmdlet "Invoke-Command", um einen **Reset-ComputerMachinePassword-** Befehl auf dem Remote Computer Server01 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dda6e-118">This command uses the Invoke-Command cmdlet to run a **Reset-ComputerMachinePassword** command on the Server01 remote computer.</span></span>

<span data-ttu-id="dda6e-119">Weitere Informationen zu Remotebefehlen in Windows PowerShell finden Sie unter about_Remote und **Invoke-Command** .</span><span class="sxs-lookup"><span data-stu-id="dda6e-119">For more information about remote commands in Windows PowerShell, see about_Remote and **Invoke-Command** .</span></span>

## <span data-ttu-id="dda6e-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dda6e-120">PARAMETERS</span></span>

### <span data-ttu-id="dda6e-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="dda6e-121">-Credential</span></span>
<span data-ttu-id="dda6e-122">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="dda6e-122">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="dda6e-123">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="dda6e-123">The default is the current user.</span></span>

<span data-ttu-id="dda6e-124">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. das vom Cmdlet Get-Credential generierte.</span><span class="sxs-lookup"><span data-stu-id="dda6e-124">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="dda6e-125">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="dda6e-125">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="dda6e-126">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dda6e-126">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dda6e-127">-Server</span><span class="sxs-lookup"><span data-stu-id="dda6e-127">-Server</span></span>
<span data-ttu-id="dda6e-128">Gibt den Namen eines Domänen Controllers an, der verwendet werden soll, wenn dieses Cmdlet das Kennwort des Computer Kontos festlegt.</span><span class="sxs-lookup"><span data-stu-id="dda6e-128">Specifies the name of a domain controller to use when this cmdlet sets the computer account password.</span></span>

<span data-ttu-id="dda6e-129">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="dda6e-129">This parameter is optional.</span></span>
<span data-ttu-id="dda6e-130">Wenn Sie diesen Parameter weglassen, wird ein Domänencontroller zum Behandeln des Befehls ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="dda6e-130">If you omit this parameter, a domain controller is chosen to service the command.</span></span>

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

### <span data-ttu-id="dda6e-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dda6e-131">-Confirm</span></span>
<span data-ttu-id="dda6e-132">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="dda6e-132">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="dda6e-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dda6e-133">-WhatIf</span></span>
<span data-ttu-id="dda6e-134">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dda6e-134">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="dda6e-135">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dda6e-135">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="dda6e-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dda6e-136">CommonParameters</span></span>
<span data-ttu-id="dda6e-137">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dda6e-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dda6e-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dda6e-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dda6e-139">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dda6e-139">INPUTS</span></span>

### <span data-ttu-id="dda6e-140">Keine</span><span class="sxs-lookup"><span data-stu-id="dda6e-140">None</span></span>
<span data-ttu-id="dda6e-141">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="dda6e-141">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="dda6e-142">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dda6e-142">OUTPUTS</span></span>

### <span data-ttu-id="dda6e-143">Keine</span><span class="sxs-lookup"><span data-stu-id="dda6e-143">None</span></span>
<span data-ttu-id="dda6e-144">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="dda6e-144">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="dda6e-145">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dda6e-145">NOTES</span></span>

## <span data-ttu-id="dda6e-146">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dda6e-146">RELATED LINKS</span></span>

## <span data-ttu-id="dda6e-147">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dda6e-147">RELATED LINKS</span></span>
