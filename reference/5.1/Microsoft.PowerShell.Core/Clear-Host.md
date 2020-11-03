---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
Module Name: Microsoft.PowerShell.Core
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/functions/clear-host?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Host
ms.openlocfilehash: 973d8c4952b99954c3f40bfd11966b754a0607b8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212116"
---
# <span data-ttu-id="1389b-103">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="1389b-103">Clear-Host</span></span>

## <span data-ttu-id="1389b-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1389b-104">SYNOPSIS</span></span>

<span data-ttu-id="1389b-105">Löscht die Anzeige im Hostprogramm.</span><span class="sxs-lookup"><span data-stu-id="1389b-105">Clears the display in the host program.</span></span>

## <span data-ttu-id="1389b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1389b-106">SYNTAX</span></span>

```
Clear-Host [<CommonParameters>]
```

## <span data-ttu-id="1389b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1389b-107">DESCRIPTION</span></span>

<span data-ttu-id="1389b-108">Die- `Clear-Host` Funktion entfernt den gesamten Text aus der aktuellen Anzeige, einschließlich Befehle und Ausgaben, die möglicherweise gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="1389b-108">The `Clear-Host` function removes all text from the current display, including commands and output that might have accumulated.</span></span> <span data-ttu-id="1389b-109">Nach Abschluss des Vorgangs wird die Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1389b-109">When complete, it displays the command prompt.</span></span> <span data-ttu-id="1389b-110">Sie können den Funktionsnamen oder seinen Alias verwenden `cls` .</span><span class="sxs-lookup"><span data-stu-id="1389b-110">You can use the function name or its alias, `cls`.</span></span>

<span data-ttu-id="1389b-111">`Clear-Host` wirkt sich nur auf die aktuelle Anzeige aus.</span><span class="sxs-lookup"><span data-stu-id="1389b-111">`Clear-Host` affects only the current display.</span></span> <span data-ttu-id="1389b-112">Es löscht keine gespeicherten Ergebnisse oder entfernt Elemente aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="1389b-112">It does not delete saved results or remove any items from the session.</span></span> <span data-ttu-id="1389b-113">Sitzungsspezifische Objekte, z. B. Variablen und Funktionen, sind nicht von dieser Funktion betroffen.</span><span class="sxs-lookup"><span data-stu-id="1389b-113">Session-specific items, such as variables and functions, are not affected by this function.</span></span>

<span data-ttu-id="1389b-114">Da das Verhalten der- `Clear-Host` Funktion durch das Host Programm bestimmt wird, `Clear-Host` funktioniert möglicherweise in verschiedenen Host Programmen anders.</span><span class="sxs-lookup"><span data-stu-id="1389b-114">Because the behavior of the `Clear-Host` function is determined by the host program, `Clear-Host` might work differently in different host programs.</span></span>

## <span data-ttu-id="1389b-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1389b-115">EXAMPLES</span></span>

### <span data-ttu-id="1389b-116">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="1389b-116">Example 1</span></span>

```
# Before

PS C:\> Get-Process

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    843      33    14428      22556    99    17.41   1688 CcmExec
     44       6     2196       4964    52     0.23    692 conhost
    646      12     2332       4896    49     1.12    388 csrss
    189      11     2860       7084   114     0.66   2896 csrss
     78      11     1876       4008    42     0.22   4000 csrss
     76       7     1848       5064    54     0.08   1028 dwm
    610      41    23952      44048   208     4.40   2080 explorer
      0       0        0         24     0               0 Idle
    182      32     7692      15980    91     0.23   3056 LogonUI
    186      25     7832      16068    91     0.27   3996 LogonUI
   1272      32    11512      20432    58    25.07    548 lsass
    267      10     3536       6736    34     0.80    556 lsm
    137      17     3520       7472    61     0.05   1220 msdtc
    447      31    70316      84476   201 1,429.67    836 MsMpEng
    265      18     7136      15628   134     2.20   3544 msseces
    248      16     6476       4076    76     0.22   1592 NisSrv
    368      25    61312      65508   614     1.78    848 powershell
    101       8     2304       6624    70     0.64   3648 rdpclip
    258      15     6804      12156    50     2.65    536 services
...

PS C:\> cls
#After

PS C:>
```

<span data-ttu-id="1389b-117">Dieser Befehl verwendet den `cls` Alias von `Clear-Host` , um die aktuelle Anzeige zu löschen.</span><span class="sxs-lookup"><span data-stu-id="1389b-117">This command uses the `cls` alias of `Clear-Host` to clear the current display.</span></span>

## <span data-ttu-id="1389b-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1389b-118">PARAMETERS</span></span>

### <span data-ttu-id="1389b-119">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1389b-119">CommonParameters</span></span>
<span data-ttu-id="1389b-120">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1389b-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1389b-121">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1389b-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1389b-122">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1389b-122">INPUTS</span></span>

### <span data-ttu-id="1389b-123">Keine</span><span class="sxs-lookup"><span data-stu-id="1389b-123">None</span></span>

<span data-ttu-id="1389b-124">Eingaben können nicht an übergeben werden `Clear-Host` .</span><span class="sxs-lookup"><span data-stu-id="1389b-124">You cannot pipe input to `Clear-Host`.</span></span>

## <span data-ttu-id="1389b-125">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1389b-125">OUTPUTS</span></span>

### <span data-ttu-id="1389b-126">Keine</span><span class="sxs-lookup"><span data-stu-id="1389b-126">None</span></span>

<span data-ttu-id="1389b-127">`Clear-Host` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="1389b-127">`Clear-Host` does not generate any output</span></span>

## <span data-ttu-id="1389b-128">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1389b-128">NOTES</span></span>

<span data-ttu-id="1389b-129">`Clear-Host` ist eine einfache Funktion, keine erweiterte Funktion.</span><span class="sxs-lookup"><span data-stu-id="1389b-129">`Clear-Host` is a simple function, not an advanced function.</span></span> <span data-ttu-id="1389b-130">Daher können Sie in einem Befehl keine allgemeinen Parameter wie z. b. **Debuggen** verwenden `Clear-Host` .</span><span class="sxs-lookup"><span data-stu-id="1389b-130">As such, you cannot use common parameters, such as **Debug** , in a `Clear-Host` command.</span></span>

## <span data-ttu-id="1389b-131">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1389b-131">RELATED LINKS</span></span>

[<span data-ttu-id="1389b-132">Get-Host</span><span class="sxs-lookup"><span data-stu-id="1389b-132">Get-Host</span></span>](../Microsoft.PowerShell.Utility/Get-Host.md)

[<span data-ttu-id="1389b-133">Out-Host</span><span class="sxs-lookup"><span data-stu-id="1389b-133">Out-Host</span></span>](Out-Host.md)

[<span data-ttu-id="1389b-134">Read-Host</span><span class="sxs-lookup"><span data-stu-id="1389b-134">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)

[<span data-ttu-id="1389b-135">Write-Host</span><span class="sxs-lookup"><span data-stu-id="1389b-135">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)
