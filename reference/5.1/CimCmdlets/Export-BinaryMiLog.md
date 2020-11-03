---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: cf03ad884121c6cf8cf65cdb791cbdc4e587c3b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212455"
---
# <span data-ttu-id="6e997-103">Export-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="6e997-103">Export-BinaryMiLog</span></span>

## <span data-ttu-id="6e997-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6e997-104">SYNOPSIS</span></span>
<span data-ttu-id="6e997-105">Erstellt eine Binär codierte Darstellung eines Objekts oder von Objekten und speichert Sie in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="6e997-105">Creates a binary encoded representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="6e997-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e997-106">SYNTAX</span></span>

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="6e997-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6e997-107">DESCRIPTION</span></span>

<span data-ttu-id="6e997-108">Das `Export-BinaryMILog` -Cmdlet erstellt eine Binär basierte Darstellung eines Objekts oder von Objekten und speichert Sie in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="6e997-108">The `Export-BinaryMILog` cmdlet creates a binary-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="6e997-109">Sie können dann das `Import-BinaryMiLog` -Cmdlet verwenden, um das gespeicherte Objekt basierend auf dem Inhalt dieser Datei neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e997-109">You can then use the `Import-BinaryMiLog` cmdlet to re-create the saved object based on the contents of that file.</span></span>

<span data-ttu-id="6e997-110">Dieses Cmdlet ähnelt `Import-Clixml` , mit der Ausnahme, dass `Export-BinaryMILog` das resultierende Objekt in einer binär codierten Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="6e997-110">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="6e997-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6e997-111">EXAMPLES</span></span>

### <span data-ttu-id="6e997-112">Beispiel 1: Erstellen einer binären Darstellung von ciminhaltungen</span><span class="sxs-lookup"><span data-stu-id="6e997-112">Example 1 - Create a binary representation of CimInstances</span></span>

```powershell
Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

<span data-ttu-id="6e997-113">Dieser Befehl exportiert **ciminhaltungen** in eine binäre Mi-Protokolldatei, die durch den path-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6e997-113">This command exports **CimInstances** to a binary MI log file specified by the Path parameter.</span></span> <span data-ttu-id="6e997-114">Im Beispiel für Import-BinaryMiLog erfahren Sie, wie Sie die **ciminhaltungen** durch Importieren dieser Datei neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e997-114">See the example for Import-BinaryMiLog to see how to recreate the **CimInstances** by importing this file.</span></span>

## <span data-ttu-id="6e997-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e997-115">PARAMETERS</span></span>

### <span data-ttu-id="6e997-116">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6e997-116">-InputObject</span></span>

<span data-ttu-id="6e997-117">Gibt die Eingabe für dieses Cmdlet an.</span><span class="sxs-lookup"><span data-stu-id="6e997-117">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="6e997-118">Verwenden Sie diesen Parameter, außerdem können Sie die Eingabe für dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="6e997-118">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

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

### <span data-ttu-id="6e997-119">-Path</span><span class="sxs-lookup"><span data-stu-id="6e997-119">-Path</span></span>

<span data-ttu-id="6e997-120">Gibt den Pfad der Datei an, in der die binäre Darstellung des-Objekts gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e997-120">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="6e997-121">Der **path** -Parameter unterstützt Platzhalter und relative Pfade.</span><span class="sxs-lookup"><span data-stu-id="6e997-121">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="6e997-122">Dieses Cmdlet generiert einen Fehler, wenn der Pfad zu mehr als einer Datei aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="6e997-122">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="6e997-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6e997-123">CommonParameters</span></span>

<span data-ttu-id="6e997-124">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6e997-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e997-125">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6e997-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e997-126">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6e997-126">INPUTS</span></span>

### <span data-ttu-id="6e997-127">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="6e997-127">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="6e997-128">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6e997-128">OUTPUTS</span></span>

### <span data-ttu-id="6e997-129">System.Object</span><span class="sxs-lookup"><span data-stu-id="6e997-129">System.Object</span></span>

## <span data-ttu-id="6e997-130">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6e997-130">NOTES</span></span>

## <span data-ttu-id="6e997-131">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6e997-131">RELATED LINKS</span></span>

[<span data-ttu-id="6e997-132">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="6e997-132">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="6e997-133">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="6e997-133">Import-BinaryMiLog</span></span>](import-binarymilog.md)

[<span data-ttu-id="6e997-134">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="6e997-134">Import-Clixml</span></span>](../microsoft.powershell.utility/import-clixml.md)
