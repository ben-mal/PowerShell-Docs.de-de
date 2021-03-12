---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: ce777eff8b41fe6bde3c8e00050ec9db87174265
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195883"
---
# <span data-ttu-id="8d409-103">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="8d409-103">Import-BinaryMiLog</span></span>

## <span data-ttu-id="8d409-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8d409-104">SYNOPSIS</span></span>
<span data-ttu-id="8d409-105">Wird verwendet, um die gespeicherten Objekte basierend auf dem Inhalt einer Exportdatei neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d409-105">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="8d409-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8d409-106">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="8d409-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8d409-107">DESCRIPTION</span></span>

<span data-ttu-id="8d409-108">Verwenden Sie dieses Cmdlet, um gespeicherte Objekte auf der Grundlage des Inhalts einer von erstellten Exportdatei neu zu erstellen `Export-BinaryMILog` .</span><span class="sxs-lookup"><span data-stu-id="8d409-108">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="8d409-109">Dieses Cmdlet ähnelt `Import-Clixml` , mit der Ausnahme, dass `Export-BinaryMILog` das resultierende Objekt in einer binär codierten Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="8d409-109">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="8d409-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8d409-110">EXAMPLES</span></span>

### <span data-ttu-id="8d409-111">Beispiel 1: Wiederherstellen von in eine Datei exportierten Objekten</span><span class="sxs-lookup"><span data-stu-id="8d409-111">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="8d409-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8d409-112">PARAMETERS</span></span>

### <span data-ttu-id="8d409-113">-Path</span><span class="sxs-lookup"><span data-stu-id="8d409-113">-Path</span></span>

<span data-ttu-id="8d409-114">Gibt den Pfad der Datei an, in der die binäre Darstellung des-Objekts gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8d409-114">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="8d409-115">Der **path** -Parameter unterstützt Platzhalter und relative Pfade.</span><span class="sxs-lookup"><span data-stu-id="8d409-115">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="8d409-116">Dieses Cmdlet generiert einen Fehler, wenn der Pfad zu mehr als einer Datei aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="8d409-116">This cmdlet generates an error if the path resolves to more than one file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8d409-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8d409-117">CommonParameters</span></span>
<span data-ttu-id="8d409-118">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8d409-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8d409-119">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8d409-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8d409-120">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8d409-120">INPUTS</span></span>

### <span data-ttu-id="8d409-121">Keine</span><span class="sxs-lookup"><span data-stu-id="8d409-121">None</span></span>

## <span data-ttu-id="8d409-122">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8d409-122">OUTPUTS</span></span>

### <span data-ttu-id="8d409-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="8d409-123">System.Object</span></span>

## <span data-ttu-id="8d409-124">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8d409-124">NOTES</span></span>

## <span data-ttu-id="8d409-125">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8d409-125">RELATED LINKS</span></span>
