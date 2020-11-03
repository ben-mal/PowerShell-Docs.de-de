---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: ff70c7dd5314fd1f123299e8f4ed14c70c7d7c9a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217420"
---
# <span data-ttu-id="ba192-103">Out-Null</span><span class="sxs-lookup"><span data-stu-id="ba192-103">Out-Null</span></span>

## <span data-ttu-id="ba192-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ba192-104">SYNOPSIS</span></span>
<span data-ttu-id="ba192-105">Blendet die Ausgabe aus, anstatt Sie über die Pipeline zu senden oder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ba192-105">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="ba192-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ba192-106">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="ba192-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ba192-107">DESCRIPTION</span></span>

<span data-ttu-id="ba192-108">Das **out-null-** Cmdlet sendet seine Ausgabe an NULL und bewirkt, dass es aus der Pipeline entfernt wird und verhindert, dass die Ausgabe auf dem Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ba192-108">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span>

## <span data-ttu-id="ba192-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ba192-109">EXAMPLES</span></span>

### <span data-ttu-id="ba192-110">Beispiel 1: Löschen der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="ba192-110">Example 1: Delete output</span></span>

```powershell
Get-ChildItem | Out-Null
```

<span data-ttu-id="ba192-111">Mit diesem Befehl werden Elemente im aktuellen Speicherort/Verzeichnis abgerufen, aber seine Ausgabe wird nicht über die Pipeline oder in der Befehlszeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba192-111">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="ba192-112">Dies ist nützlich, um die Ausgabe zu verbergen, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="ba192-112">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="ba192-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ba192-113">PARAMETERS</span></span>

### <span data-ttu-id="ba192-114">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ba192-114">-InputObject</span></span>

<span data-ttu-id="ba192-115">Gibt das-Objekt an, das an NULL (aus Pipeline entfernt) gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba192-115">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="ba192-116">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ba192-116">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ba192-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ba192-117">CommonParameters</span></span>

<span data-ttu-id="ba192-118">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ba192-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ba192-119">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ba192-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ba192-120">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ba192-120">INPUTS</span></span>

### <span data-ttu-id="ba192-121">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="ba192-121">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="ba192-122">Sie können jedes beliebige Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="ba192-122">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="ba192-123">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ba192-123">OUTPUTS</span></span>

### <span data-ttu-id="ba192-124">Keine</span><span class="sxs-lookup"><span data-stu-id="ba192-124">None</span></span>

<span data-ttu-id="ba192-125">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ba192-125">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ba192-126">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ba192-126">NOTES</span></span>

* <span data-ttu-id="ba192-127">Die Cmdlets, die das **out** -Verb (die **out** -Cmdlets) enthalten, haben keine Parameter für Namen oder Dateipfade.</span><span class="sxs-lookup"><span data-stu-id="ba192-127">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="ba192-128">Verwenden Sie zum Senden von Daten an ein **out** -Cmdlet einen Pipeline Operator (|), um die Ausgabe eines PowerShell-Befehls an das Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="ba192-128">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a PowerShell command to the cmdlet.</span></span> <span data-ttu-id="ba192-129">Sie können auch Daten in einer Variablen speichern und den *InputObject* -Parameter verwenden, um die Daten an das Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="ba192-129">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="ba192-130">Weitere Informationen finden Sie in den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="ba192-130">For more information, see the examples.</span></span>
* <span data-ttu-id="ba192-131">**Out-null** gibt keine Ausgabe Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="ba192-131">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="ba192-132">Wenn Sie die Ausgabe von **out-null** an das Get-Member-Cmdlet weiterreichen, meldet **Get-Member** , dass keine Objekte angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="ba192-132">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="ba192-133">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ba192-133">RELATED LINKS</span></span>

[<span data-ttu-id="ba192-134">Out-Default</span><span class="sxs-lookup"><span data-stu-id="ba192-134">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="ba192-135">Out-Host</span><span class="sxs-lookup"><span data-stu-id="ba192-135">Out-Host</span></span>](Out-Host.md)

