---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-experimentalfeature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ExperimentalFeature
ms.openlocfilehash: 1d022bd17c19d1c332b7ef49522ba29c5b7b8e6f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600697"
---
# <span data-ttu-id="9ceaa-102">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="9ceaa-102">Enable-ExperimentalFeature</span></span>

## <span data-ttu-id="9ceaa-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9ceaa-103">SYNOPSIS</span></span>
<span data-ttu-id="9ceaa-104">Aktivieren Sie eine experimentelle Funktion beim Starten einer neuen Instanz von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-104">Enable an experimental feature on startup of new instance of PowerShell.</span></span>

## <span data-ttu-id="9ceaa-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9ceaa-105">SYNTAX</span></span>

```
Enable-ExperimentalFeature [-Name] <String[]> [-Scope <ConfigScope>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9ceaa-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ceaa-106">DESCRIPTION</span></span>

<span data-ttu-id="9ceaa-107">Das- `Enable-ExperimentalFeature` Cmdlet aktiviert experimentelle Funktionen, indem die benannten experimentellen Features der Einstellungsdatei hinzugefügt werden, die `powershell.config.json` beim Start von PowerShell gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-107">The `Enable-ExperimentalFeature` cmdlet enables experimental features by adding the named experimental features to the `powershell.config.json` settings file read on PowerShell startup.</span></span>

<span data-ttu-id="9ceaa-108">Dieses Cmdlet wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-108">This cmdlet was introduced in PowerShell 6.2.</span></span>

> [!NOTE]
> <span data-ttu-id="9ceaa-109">Änderungen am experimentellen Funktionsstatus werden bei einem Neustart von PowerShell nur wirksam.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-109">Any changes to experimental feature state only takes effect on restart of PowerShell</span></span>

## <span data-ttu-id="9ceaa-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9ceaa-110">EXAMPLES</span></span>

### <span data-ttu-id="9ceaa-111">Beispiel 1: Aktivieren eines experimentellen Features</span><span class="sxs-lookup"><span data-stu-id="9ceaa-111">Example 1: Enable an experimental feature</span></span>

<span data-ttu-id="9ceaa-112">Wenn diese experimentelle Funktion in diesem Beispiel zuvor deaktiviert war, wird die `powershell.config.json` Datei aktualisiert, damit der Benutzer diese Funktion aktivieren kann, sobald PowerShell neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-112">In this example, if this experimental feature was previously disabled, then the `powershell.config.json` file is updated for the user to enable that feature once PowerShell is restarted.</span></span>
<span data-ttu-id="9ceaa-113">Bei Erfolg wird keine Ausgabe an die Pipeline ausgegeben, und es wird nur eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-113">Upon success nothing is output to the pipeline and only a warning message is displayed.</span></span>

```powershell
Enable-ExperimentalFeature PSImplicitRemotingBatching
```

```Output
WARNING: Enabling and disabling experimental features do not take effect until next start of PowerShell.
```

## <span data-ttu-id="9ceaa-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9ceaa-114">PARAMETERS</span></span>

### <span data-ttu-id="9ceaa-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9ceaa-115">-Confirm</span></span>

<span data-ttu-id="9ceaa-116">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-116">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9ceaa-117">-Name</span><span class="sxs-lookup"><span data-stu-id="9ceaa-117">-Name</span></span>

<span data-ttu-id="9ceaa-118">Der Name oder die Namen der zu aktivierenden experimentellen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-118">The name or names of the experimental features to enable.</span></span>

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

### <span data-ttu-id="9ceaa-119">-Bereich</span><span class="sxs-lookup"><span data-stu-id="9ceaa-119">-Scope</span></span>

<span data-ttu-id="9ceaa-120">Bestimmt, welche `powershell.config.json` aktualisiert werden soll, ob Sie sich auf alle Benutzer oder nur auf den aktuellen Benutzer auswirkt.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-120">Determines which `powershell.config.json` to update whether it affects all users or just the current user.</span></span>

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

### <span data-ttu-id="9ceaa-121">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9ceaa-121">-WhatIf</span></span>

<span data-ttu-id="9ceaa-122">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-122">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9ceaa-123">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-123">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9ceaa-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9ceaa-124">CommonParameters</span></span>

<span data-ttu-id="9ceaa-125">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9ceaa-126">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9ceaa-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9ceaa-127">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9ceaa-127">INPUTS</span></span>

### <span data-ttu-id="9ceaa-128">Experimentalfeature</span><span class="sxs-lookup"><span data-stu-id="9ceaa-128">ExperimentalFeature</span></span>

<span data-ttu-id="9ceaa-129">Pipeinstanzen von experimentalfeature vom `Get-ExperimentalFeature` Cmdlet zum Aktivieren von.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-129">Pipe instances of ExperimentalFeature from `Get-ExperimentalFeature` cmdlet to enable.</span></span>

## <span data-ttu-id="9ceaa-130">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9ceaa-130">OUTPUTS</span></span>

### <span data-ttu-id="9ceaa-131">Keine</span><span class="sxs-lookup"><span data-stu-id="9ceaa-131">None</span></span>

<span data-ttu-id="9ceaa-132">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="9ceaa-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9ceaa-133">NOTES</span></span>

<span data-ttu-id="9ceaa-134">Änderungen am Status eines experimentellen Features treten nur beim Neustart von PowerShell in Kraft.</span><span class="sxs-lookup"><span data-stu-id="9ceaa-134">Changes to state of an experimental feature only take effect on restart of PowerShell.</span></span>

## <span data-ttu-id="9ceaa-135">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9ceaa-135">RELATED LINKS</span></span>

[<span data-ttu-id="9ceaa-136">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="9ceaa-136">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="9ceaa-137">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="9ceaa-137">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

