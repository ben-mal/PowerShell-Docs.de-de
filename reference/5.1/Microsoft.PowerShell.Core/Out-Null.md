---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: 5a949629cdf0f0822866863822e82e70fc38d8c2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212844"
---
# <span data-ttu-id="3408f-103">Out-Null</span><span class="sxs-lookup"><span data-stu-id="3408f-103">Out-Null</span></span>

## <span data-ttu-id="3408f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3408f-104">SYNOPSIS</span></span>
<span data-ttu-id="3408f-105">Blendet die Ausgabe aus, anstatt Sie über die Pipeline zu senden oder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3408f-105">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="3408f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3408f-106">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="3408f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3408f-107">DESCRIPTION</span></span>
<span data-ttu-id="3408f-108">Das **out-null-** Cmdlet sendet seine Ausgabe an NULL und bewirkt, dass es aus der Pipeline entfernt wird und verhindert, dass die Ausgabe auf dem Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3408f-108">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span> <span data-ttu-id="3408f-109">Dies betrifft nur den Standardausgabestream.</span><span class="sxs-lookup"><span data-stu-id="3408f-109">This only affects the standard output stream.</span></span>
<span data-ttu-id="3408f-110">Andere Ausgabedaten Ströme, wie z. b. der fehlerstream, sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="3408f-110">Other output streams, like the Error stream are not affected.</span></span> <span data-ttu-id="3408f-111">Es werden Ausnahmen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3408f-111">Exceptions will be displayed.</span></span> <span data-ttu-id="3408f-112">Dadurch ist es einfacher, den Befehl auf Fehler zu testen.</span><span class="sxs-lookup"><span data-stu-id="3408f-112">This makes it easier to test your command for any errors.</span></span>

## <span data-ttu-id="3408f-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3408f-113">EXAMPLES</span></span>

### <span data-ttu-id="3408f-114">Beispiel 1: Löschen der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3408f-114">Example 1: Delete output</span></span>

```
PS C:\> Get-ChildItem | Out-Null
```

<span data-ttu-id="3408f-115">Mit diesem Befehl werden Elemente im aktuellen Speicherort/Verzeichnis abgerufen, aber seine Ausgabe wird nicht über die Pipeline oder in der Befehlszeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3408f-115">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="3408f-116">Dies ist nützlich, um die Ausgabe zu verbergen, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="3408f-116">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="3408f-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3408f-117">PARAMETERS</span></span>

### <span data-ttu-id="3408f-118">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3408f-118">-InputObject</span></span>
<span data-ttu-id="3408f-119">Gibt das-Objekt an, das an NULL (aus Pipeline entfernt) gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3408f-119">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="3408f-120">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3408f-120">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="3408f-121">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3408f-121">CommonParameters</span></span>
<span data-ttu-id="3408f-122">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3408f-122">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3408f-123">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3408f-123">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3408f-124">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3408f-124">INPUTS</span></span>

### <span data-ttu-id="3408f-125">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="3408f-125">System.Management.Automation.PSObject</span></span>
<span data-ttu-id="3408f-126">Sie können jedes beliebige Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="3408f-126">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="3408f-127">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3408f-127">OUTPUTS</span></span>

### <span data-ttu-id="3408f-128">Keine</span><span class="sxs-lookup"><span data-stu-id="3408f-128">None</span></span>
<span data-ttu-id="3408f-129">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="3408f-129">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3408f-130">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3408f-130">NOTES</span></span>

* <span data-ttu-id="3408f-131">Die Cmdlets, die das **out** -Verb (die **out** -Cmdlets) enthalten, haben keine Parameter für Namen oder Dateipfade.</span><span class="sxs-lookup"><span data-stu-id="3408f-131">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="3408f-132">Zum Senden von Daten an ein **Out** -Cmdlet verwenden Sie einen Pipelineoperator (|), um die Ausgabe eines Windows PowerShell-Befehls an das Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="3408f-132">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a Windows PowerShell command to the cmdlet.</span></span> <span data-ttu-id="3408f-133">Sie können auch Daten in einer Variablen speichern und den *InputObject* -Parameter verwenden, um die Daten an das Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="3408f-133">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="3408f-134">Weitere Informationen finden Sie in den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="3408f-134">For more information, see the examples.</span></span>
* <span data-ttu-id="3408f-135">**Out-null** gibt keine Ausgabe Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="3408f-135">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="3408f-136">Wenn Sie die Ausgabe von **out-null** an das Get-Member-Cmdlet weiterreichen, meldet **Get-Member** , dass keine Objekte angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="3408f-136">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="3408f-137">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3408f-137">RELATED LINKS</span></span>

[<span data-ttu-id="3408f-138">Out-Default</span><span class="sxs-lookup"><span data-stu-id="3408f-138">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="3408f-139">Out-Host</span><span class="sxs-lookup"><span data-stu-id="3408f-139">Out-Host</span></span>](Out-Host.md)
