---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 03/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-experimentalfeature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ExperimentalFeature
ms.openlocfilehash: e35e164f3116304efd52c71c1715ba70711f6253
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599839"
---
# <span data-ttu-id="af3d8-102">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="af3d8-102">Disable-ExperimentalFeature</span></span>

## <span data-ttu-id="af3d8-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="af3d8-103">SYNOPSIS</span></span>
<span data-ttu-id="af3d8-104">Deaktivieren Sie eine experimentelle Funktion beim Starten einer neuen Instanz von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af3d8-104">Disable an experimental feature on startup of new instance of PowerShell.</span></span>

## <span data-ttu-id="af3d8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="af3d8-105">SYNTAX</span></span>

```
Disable-ExperimentalFeature [-Name] <String[]> [-Scope <ConfigScope>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="af3d8-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="af3d8-106">DESCRIPTION</span></span>

<span data-ttu-id="af3d8-107">Mit dem- `Disable-ExperimentalFeature` Cmdlet werden experimentelle Funktionen deaktiviert, indem die benannten experimentellen Features aus der Einstellungsdatei entfernt werden, die `powershell.config.json` beim Start von PowerShell gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="af3d8-107">The `Disable-ExperimentalFeature` cmdlet disables experimental features by removing the named experimental features from the `powershell.config.json` settings file read on PowerShell startup.</span></span>

<span data-ttu-id="af3d8-108">Dieses Cmdlet wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="af3d8-108">This cmdlet was introduced in PowerShell 6.2.</span></span>

> [!NOTE]
> <span data-ttu-id="af3d8-109">Änderungen am experimentellen Funktionsstatus werden bei einem Neustart von PowerShell nur wirksam.</span><span class="sxs-lookup"><span data-stu-id="af3d8-109">Any changes to experimental feature state only takes effect on restart of PowerShell</span></span>

## <span data-ttu-id="af3d8-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="af3d8-110">EXAMPLES</span></span>

### <span data-ttu-id="af3d8-111">Beispiel 1: Deaktivieren eines experimentellen Features</span><span class="sxs-lookup"><span data-stu-id="af3d8-111">Example 1: Disable an experimental feature</span></span>

<span data-ttu-id="af3d8-112">Wenn diese experimentelle Funktion zuvor aktiviert war, `powershell.config.json` wird die Datei aktualisiert, damit der Benutzer diese Funktion nicht aktivieren kann, nachdem PowerShell neu gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="af3d8-112">In this example, if this experimental feature was previously enabled, then the `powershell.config.json` file is updated for the user to not enable that feature once PowerShell is restarted.</span></span>
<span data-ttu-id="af3d8-113">Bei Erfolg wird keine Ausgabe an die Pipeline ausgegeben, und es wird nur eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af3d8-113">Upon success nothing is output to the pipeline and only a warning message is displayed.</span></span>

```powershell
PS C:\> Disable-ExperimentalFeature PSImplicitRemotingBatching
```

```Output
WARNING: Enabling and disabling experimental features do not take effect until next start of PowerShell.
```

## <span data-ttu-id="af3d8-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="af3d8-114">PARAMETERS</span></span>

### <span data-ttu-id="af3d8-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="af3d8-115">-Confirm</span></span>

<span data-ttu-id="af3d8-116">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="af3d8-116">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af3d8-117">-Name</span><span class="sxs-lookup"><span data-stu-id="af3d8-117">-Name</span></span>

<span data-ttu-id="af3d8-118">Der Name oder die Namen der zu deaktivierenden experimentellen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="af3d8-118">The name or names of the experimental features to disable.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af3d8-119">-Bereich</span><span class="sxs-lookup"><span data-stu-id="af3d8-119">-Scope</span></span>

<span data-ttu-id="af3d8-120">Bestimmt, welche `powershell.config.json` aktualisiert werden soll, ob Sie sich auf alle Benutzer oder nur auf den aktuellen Benutzer auswirkt.</span><span class="sxs-lookup"><span data-stu-id="af3d8-120">Determines which `powershell.config.json` to update whether it affects all users or just the current user.</span></span>

```yaml
Type: System.Management.Automation.Configuration.ConfigScope
Parameter Sets: (All)
Aliases:
Accepted values: AllUsers, CurrentUser

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af3d8-121">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="af3d8-121">-WhatIf</span></span>

<span data-ttu-id="af3d8-122">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="af3d8-122">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="af3d8-123">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="af3d8-123">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af3d8-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="af3d8-124">CommonParameters</span></span>

<span data-ttu-id="af3d8-125">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="af3d8-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="af3d8-126">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="af3d8-126">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="af3d8-127">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="af3d8-127">INPUTS</span></span>

### <span data-ttu-id="af3d8-128">Experimentalfeature</span><span class="sxs-lookup"><span data-stu-id="af3d8-128">ExperimentalFeature</span></span>

<span data-ttu-id="af3d8-129">Pipeinstanzen von experimentalfeature vom `Get-ExperimentalFeature` Cmdlet zum Deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="af3d8-129">Pipe instances of ExperimentalFeature from `Get-ExperimentalFeature` cmdlet to disable.</span></span>

## <span data-ttu-id="af3d8-130">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="af3d8-130">OUTPUTS</span></span>

### <span data-ttu-id="af3d8-131">Keine</span><span class="sxs-lookup"><span data-stu-id="af3d8-131">None</span></span>

<span data-ttu-id="af3d8-132">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="af3d8-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="af3d8-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="af3d8-133">NOTES</span></span>

<span data-ttu-id="af3d8-134">Änderungen am Status eines experimentellen Features treten nur beim Neustart von PowerShell in Kraft.</span><span class="sxs-lookup"><span data-stu-id="af3d8-134">Changes to state of an experimental feature only take effect on restart of PowerShell.</span></span>

## <span data-ttu-id="af3d8-135">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="af3d8-135">RELATED LINKS</span></span>

[<span data-ttu-id="af3d8-136">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="af3d8-136">Enable-ExperimentalFeature</span></span>](Enable-ExperimentalFeature.md)

[<span data-ttu-id="af3d8-137">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="af3d8-137">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

