---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: fe28f52088a82b93799724de7a7a3f20ce42e36b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599230"
---
# <span data-ttu-id="3dbbc-102">Out-Null</span><span class="sxs-lookup"><span data-stu-id="3dbbc-102">Out-Null</span></span>

## <span data-ttu-id="3dbbc-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3dbbc-103">SYNOPSIS</span></span>
<span data-ttu-id="3dbbc-104">Blendet die Ausgabe aus, anstatt Sie über die Pipeline zu senden oder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-104">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="3dbbc-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3dbbc-105">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="3dbbc-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3dbbc-106">DESCRIPTION</span></span>

<span data-ttu-id="3dbbc-107">Das **out-null-** Cmdlet sendet seine Ausgabe an NULL und bewirkt, dass es aus der Pipeline entfernt wird und verhindert, dass die Ausgabe auf dem Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-107">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span>

## <span data-ttu-id="3dbbc-108">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3dbbc-108">EXAMPLES</span></span>

### <span data-ttu-id="3dbbc-109">Beispiel 1: Löschen der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3dbbc-109">Example 1: Delete output</span></span>

```powershell
Get-ChildItem | Out-Null
```

<span data-ttu-id="3dbbc-110">Mit diesem Befehl werden Elemente im aktuellen Speicherort/Verzeichnis abgerufen, aber seine Ausgabe wird nicht über die Pipeline oder in der Befehlszeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-110">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="3dbbc-111">Dies ist nützlich, um die Ausgabe zu verbergen, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-111">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="3dbbc-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3dbbc-112">PARAMETERS</span></span>

### <span data-ttu-id="3dbbc-113">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3dbbc-113">-InputObject</span></span>

<span data-ttu-id="3dbbc-114">Gibt das-Objekt an, das an NULL (aus Pipeline entfernt) gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-114">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="3dbbc-115">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-115">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="3dbbc-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3dbbc-116">CommonParameters</span></span>

<span data-ttu-id="3dbbc-117">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3dbbc-118">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3dbbc-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3dbbc-119">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3dbbc-119">INPUTS</span></span>

### <span data-ttu-id="3dbbc-120">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="3dbbc-120">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3dbbc-121">Sie können jedes beliebige Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-121">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="3dbbc-122">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3dbbc-122">OUTPUTS</span></span>

### <span data-ttu-id="3dbbc-123">Keine</span><span class="sxs-lookup"><span data-stu-id="3dbbc-123">None</span></span>

<span data-ttu-id="3dbbc-124">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-124">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3dbbc-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3dbbc-125">NOTES</span></span>

* <span data-ttu-id="3dbbc-126">Die Cmdlets, die das **out** -Verb (die **out** -Cmdlets) enthalten, haben keine Parameter für Namen oder Dateipfade.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-126">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="3dbbc-127">Verwenden Sie zum Senden von Daten an ein **out** -Cmdlet einen Pipeline Operator (|), um die Ausgabe eines PowerShell-Befehls an das Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-127">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a PowerShell command to the cmdlet.</span></span> <span data-ttu-id="3dbbc-128">Sie können auch Daten in einer Variablen speichern und den *InputObject*-Parameter verwenden, um die Daten an das Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-128">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="3dbbc-129">Weitere Informationen finden Sie in den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-129">For more information, see the examples.</span></span>
* <span data-ttu-id="3dbbc-130">**Out-null** gibt keine Ausgabe Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-130">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="3dbbc-131">Wenn Sie die Ausgabe von **out-null** an das Get-Member-Cmdlet weiterreichen, meldet **Get-Member** , dass keine Objekte angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="3dbbc-131">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="3dbbc-132">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3dbbc-132">RELATED LINKS</span></span>

[<span data-ttu-id="3dbbc-133">Out-Default</span><span class="sxs-lookup"><span data-stu-id="3dbbc-133">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="3dbbc-134">Out-Host</span><span class="sxs-lookup"><span data-stu-id="3dbbc-134">Out-Host</span></span>](Out-Host.md)

