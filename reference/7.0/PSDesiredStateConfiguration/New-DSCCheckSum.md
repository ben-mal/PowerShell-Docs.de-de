---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: 2a66f906025f7a25609080e0b8da7f01755cd2fa
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210079"
---
# <span data-ttu-id="a45bd-103">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="a45bd-103">New-DscChecksum</span></span>

## <span data-ttu-id="a45bd-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a45bd-104">SYNOPSIS</span></span>
<span data-ttu-id="a45bd-105">Erstellt Prüfsummen Dateien für DSC-Dokumente und DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a45bd-105">Creates checksum files for DSC documents and DSC resources.</span></span>

## <span data-ttu-id="a45bd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a45bd-106">SYNTAX</span></span>

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a45bd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a45bd-107">DESCRIPTION</span></span>

<span data-ttu-id="a45bd-108">Das Cmdlet " **New-dscchecksum** " generiert Prüfsummen Dateien für PowerShell DSC-Dokumente (DSC) und komprimierte DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a45bd-108">The **New-DSCCheckSum** cmdlet generates checksum files for PowerShell Desired State Configuration (DSC) documents and compressed DSC resources.</span></span>
<span data-ttu-id="a45bd-109">Dieses Cmdlet generiert eine Prüfsummen Datei für alle Konfigurationen und Ressourcen, die im Pullmodus verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a45bd-109">This cmdlet generates a checksum file for each configuration and resource to be used in pull mode.</span></span>
<span data-ttu-id="a45bd-110">Der DSC-Dienst verwendet die Prüfsummen, um sicherzustellen, dass auf dem Zielknoten die korrekte Konfiguration und Ressourcen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a45bd-110">The DSC service uses the checksums to make sure that the correct configuration and resources exist on the target node.</span></span>
<span data-ttu-id="a45bd-111">Platzieren Sie die Prüfsummen zusammen mit den zugeordneten DSC-Dokumenten und komprimierten DSC-Ressourcen im DSC-Dienst Speicher.</span><span class="sxs-lookup"><span data-stu-id="a45bd-111">Place the checksums together with the associated DSC documents and compressed DSC resources in the DSC service store.</span></span>

## <span data-ttu-id="a45bd-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a45bd-112">EXAMPLES</span></span>

### <span data-ttu-id="a45bd-113">Beispiel 1: Erstellen von Prüfsummen Dateien für alle Konfigurationen in einem bestimmten Pfad</span><span class="sxs-lookup"><span data-stu-id="a45bd-113">Example 1: Create checksum files for all configurations in a specific path</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="a45bd-114">Dieser Befehl erstellt die Prüfsummendateien für alle Konfigurationen im Pfad C:\DSC\Configurations.</span><span class="sxs-lookup"><span data-stu-id="a45bd-114">This command creates checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="a45bd-115">Alle bereits vorhandenen Prüfsummen Dateien werden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="a45bd-115">Any checksum files that already exist are skipped.</span></span>

### <span data-ttu-id="a45bd-116">Beispiel 2: Erstellen von Prüfsummen Dateien für alle Konfigurationen in einem bestimmten Pfad und Überschreiben der vorhandenen Prüfsummen Dateien</span><span class="sxs-lookup"><span data-stu-id="a45bd-116">Example 2: Create checksum files for all configurations in a specific path and overwrite the existing checksum files</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

<span data-ttu-id="a45bd-117">Dieser Befehl erstellt neue Prüfsummendateien für alle Konfigurationen im Pfad C:\DSC\Configurations.</span><span class="sxs-lookup"><span data-stu-id="a45bd-117">This command creates new checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="a45bd-118">Wenn Sie den *Force* -Parameter angeben, überschreibt der Befehl alle Prüfsummen Dateien, die bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a45bd-118">Specifying the *Force* parameter causes the command to overwrite any checksum files that already exist.</span></span>

## <span data-ttu-id="a45bd-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a45bd-119">PARAMETERS</span></span>

### <span data-ttu-id="a45bd-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a45bd-120">-Confirm</span></span>

<span data-ttu-id="a45bd-121">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a45bd-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a45bd-122">-Force</span><span class="sxs-lookup"><span data-stu-id="a45bd-122">-Force</span></span>

<span data-ttu-id="a45bd-123">Gibt an, dass das Cmdlet die angegebene Ausgabedatei überschreibt, wenn diese bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a45bd-123">Indicates that the cmdlet overwrites the specified output file if it already exists.</span></span>

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

### <span data-ttu-id="a45bd-124">-OutPath</span><span class="sxs-lookup"><span data-stu-id="a45bd-124">-OutPath</span></span>

<span data-ttu-id="a45bd-125">Gibt den Pfad und den Dateinamen der Ausgabeprüfsummendatei an.</span><span class="sxs-lookup"><span data-stu-id="a45bd-125">Specifies the path and file name of the output checksum file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a45bd-126">-Path</span><span class="sxs-lookup"><span data-stu-id="a45bd-126">-Path</span></span>

<span data-ttu-id="a45bd-127">Gibt den Pfad der Eingabedatei an.</span><span class="sxs-lookup"><span data-stu-id="a45bd-127">Specifies the path of the input file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ConfigurationPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a45bd-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a45bd-128">-WhatIf</span></span>

<span data-ttu-id="a45bd-129">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a45bd-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a45bd-130">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a45bd-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a45bd-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a45bd-131">CommonParameters</span></span>

<span data-ttu-id="a45bd-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a45bd-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a45bd-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a45bd-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a45bd-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a45bd-134">INPUTS</span></span>

### <span data-ttu-id="a45bd-135">Keine</span><span class="sxs-lookup"><span data-stu-id="a45bd-135">None</span></span>

## <span data-ttu-id="a45bd-136">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a45bd-136">OUTPUTS</span></span>

### <span data-ttu-id="a45bd-137">System.Object</span><span class="sxs-lookup"><span data-stu-id="a45bd-137">System.Object</span></span>

## <span data-ttu-id="a45bd-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a45bd-138">NOTES</span></span>

## <span data-ttu-id="a45bd-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a45bd-139">RELATED LINKS</span></span>

[<span data-ttu-id="a45bd-140">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="a45bd-140">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)
