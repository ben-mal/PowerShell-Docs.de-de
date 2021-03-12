---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: 1d202b7bbda359f859838475eb9f37730506bd1f
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194361"
---
# <span data-ttu-id="a0313-103">Export-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="a0313-103">Export-BinaryMiLog</span></span>

## <span data-ttu-id="a0313-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a0313-104">SYNOPSIS</span></span>
<span data-ttu-id="a0313-105">Erstellt eine Binär codierte Darstellung eines Objekts oder von Objekten und speichert Sie in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="a0313-105">Creates a binary encoded representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="a0313-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a0313-106">SYNTAX</span></span>

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="a0313-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a0313-107">DESCRIPTION</span></span>

<span data-ttu-id="a0313-108">Das `Export-BinaryMILog` -Cmdlet erstellt eine Binär basierte Darstellung eines Objekts oder von Objekten und speichert Sie in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="a0313-108">The `Export-BinaryMILog` cmdlet creates a binary-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="a0313-109">Sie können dann das `Import-BinaryMiLog` -Cmdlet verwenden, um das gespeicherte Objekt basierend auf dem Inhalt dieser Datei neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a0313-109">You can then use the `Import-BinaryMiLog` cmdlet to re-create the saved object based on the contents of that file.</span></span>

<span data-ttu-id="a0313-110">Dieses Cmdlet ähnelt `Import-Clixml` , mit der Ausnahme, dass `Export-BinaryMILog` das resultierende Objekt in einer binär codierten Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="a0313-110">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="a0313-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a0313-111">EXAMPLES</span></span>

### <span data-ttu-id="a0313-112">Beispiel 1: Erstellen einer binären Darstellung von ciminhaltungen</span><span class="sxs-lookup"><span data-stu-id="a0313-112">Example 1 - Create a binary representation of CimInstances</span></span>

```powershell
Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

<span data-ttu-id="a0313-113">Dieser Befehl exportiert **ciminhaltungen** in eine binäre Mi-Protokolldatei, die durch den path-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a0313-113">This command exports **CimInstances** to a binary MI log file specified by the Path parameter.</span></span> <span data-ttu-id="a0313-114">Im Beispiel für Import-BinaryMiLog erfahren Sie, wie Sie die **ciminhaltungen** durch Importieren dieser Datei neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a0313-114">See the example for Import-BinaryMiLog to see how to recreate the **CimInstances** by importing this file.</span></span>

## <span data-ttu-id="a0313-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a0313-115">PARAMETERS</span></span>

### <span data-ttu-id="a0313-116">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a0313-116">-InputObject</span></span>

<span data-ttu-id="a0313-117">Gibt die Eingabe für dieses Cmdlet an.</span><span class="sxs-lookup"><span data-stu-id="a0313-117">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="a0313-118">Verwenden Sie diesen Parameter, außerdem können Sie die Eingabe für dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="a0313-118">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a0313-119">-Path</span><span class="sxs-lookup"><span data-stu-id="a0313-119">-Path</span></span>

<span data-ttu-id="a0313-120">Gibt den Pfad der Datei an, in der die binäre Darstellung des-Objekts gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0313-120">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="a0313-121">Der **path** -Parameter unterstützt Platzhalter und relative Pfade.</span><span class="sxs-lookup"><span data-stu-id="a0313-121">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="a0313-122">Dieses Cmdlet generiert einen Fehler, wenn der Pfad zu mehr als einer Datei aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a0313-122">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="a0313-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a0313-123">CommonParameters</span></span>

<span data-ttu-id="a0313-124">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a0313-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a0313-125">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a0313-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a0313-126">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a0313-126">INPUTS</span></span>

### <span data-ttu-id="a0313-127">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="a0313-127">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="a0313-128">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a0313-128">OUTPUTS</span></span>

### <span data-ttu-id="a0313-129">System.Object</span><span class="sxs-lookup"><span data-stu-id="a0313-129">System.Object</span></span>

## <span data-ttu-id="a0313-130">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a0313-130">NOTES</span></span>

## <span data-ttu-id="a0313-131">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a0313-131">RELATED LINKS</span></span>

[<span data-ttu-id="a0313-132">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="a0313-132">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="a0313-133">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="a0313-133">Import-BinaryMiLog</span></span>](import-binarymilog.md)

[<span data-ttu-id="a0313-134">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="a0313-134">Import-Clixml</span></span>](../microsoft.powershell.utility/import-clixml.md)
