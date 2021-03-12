---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: b31d12f06a8d2e8e226908db9663446baf09a124
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194253"
---
# <span data-ttu-id="d22ef-102">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="d22ef-102">Import-BinaryMiLog</span></span>

## <span data-ttu-id="d22ef-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d22ef-103">SYNOPSIS</span></span>
<span data-ttu-id="d22ef-104">Wird verwendet, um die gespeicherten Objekte basierend auf dem Inhalt einer Exportdatei neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d22ef-104">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="d22ef-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d22ef-105">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="d22ef-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d22ef-106">DESCRIPTION</span></span>

<span data-ttu-id="d22ef-107">Verwenden Sie dieses Cmdlet, um gespeicherte Objekte auf der Grundlage des Inhalts einer von erstellten Exportdatei neu zu erstellen `Export-BinaryMILog` .</span><span class="sxs-lookup"><span data-stu-id="d22ef-107">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="d22ef-108">Dieses Cmdlet ähnelt `Import-Clixml` , mit der Ausnahme, dass `Export-BinaryMILog` das resultierende Objekt in einer binär codierten Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="d22ef-108">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="d22ef-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d22ef-109">EXAMPLES</span></span>

### <span data-ttu-id="d22ef-110">Beispiel 1: Wiederherstellen von in eine Datei exportierten Objekten</span><span class="sxs-lookup"><span data-stu-id="d22ef-110">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="d22ef-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d22ef-111">PARAMETERS</span></span>

### <span data-ttu-id="d22ef-112">-Path</span><span class="sxs-lookup"><span data-stu-id="d22ef-112">-Path</span></span>

<span data-ttu-id="d22ef-113">Gibt den Pfad der Datei an, in der die binäre Darstellung des-Objekts gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d22ef-113">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="d22ef-114">Der **path** -Parameter unterstützt Platzhalter und relative Pfade.</span><span class="sxs-lookup"><span data-stu-id="d22ef-114">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="d22ef-115">Dieses Cmdlet generiert einen Fehler, wenn der Pfad zu mehr als einer Datei aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="d22ef-115">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="d22ef-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d22ef-116">CommonParameters</span></span>
<span data-ttu-id="d22ef-117">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d22ef-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d22ef-118">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d22ef-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d22ef-119">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d22ef-119">INPUTS</span></span>

### <span data-ttu-id="d22ef-120">Keine</span><span class="sxs-lookup"><span data-stu-id="d22ef-120">None</span></span>

## <span data-ttu-id="d22ef-121">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d22ef-121">OUTPUTS</span></span>

### <span data-ttu-id="d22ef-122">System.Object</span><span class="sxs-lookup"><span data-stu-id="d22ef-122">System.Object</span></span>

## <span data-ttu-id="d22ef-123">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d22ef-123">NOTES</span></span>

## <span data-ttu-id="d22ef-124">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d22ef-124">RELATED LINKS</span></span>
