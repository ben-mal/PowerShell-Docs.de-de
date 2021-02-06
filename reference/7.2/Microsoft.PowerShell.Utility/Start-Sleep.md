---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4d06fdd1d5a616c24a4dd7bec10ea4dadea4062
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599203"
---
# <span data-ttu-id="3f139-102">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="3f139-102">Start-Sleep</span></span>

## <span data-ttu-id="3f139-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3f139-103">SYNOPSIS</span></span>
<span data-ttu-id="3f139-104">Hält die Aktivität in einem Skript oder einer Sitzung für den angegebenen Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="3f139-104">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="3f139-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3f139-105">SYNTAX</span></span>

### <span data-ttu-id="3f139-106">Sekunden (Standard)</span><span class="sxs-lookup"><span data-stu-id="3f139-106">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### <span data-ttu-id="3f139-107">Millisekunden</span><span class="sxs-lookup"><span data-stu-id="3f139-107">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="3f139-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3f139-108">DESCRIPTION</span></span>

<span data-ttu-id="3f139-109">Das- `Start-Sleep` Cmdlet hält die Aktivität in einem Skript oder einer Sitzung für den angegebenen Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="3f139-109">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span> <span data-ttu-id="3f139-110">Sie können es für viele Aufgaben verwenden, z. B. Warten auf den Abschluss eines Vorgangs oder Anhalten, bevor ein Vorgang wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="3f139-110">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="3f139-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3f139-111">EXAMPLES</span></span>

### <span data-ttu-id="3f139-112">Beispiel 1: alle Befehle für 15 Sekunden in den Standbymodus</span><span class="sxs-lookup"><span data-stu-id="3f139-112">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

### <span data-ttu-id="3f139-113">Beispiel 2: Standbymodus für alle Befehle für 1,5 Sekunden</span><span class="sxs-lookup"><span data-stu-id="3f139-113">Example 2: Sleep all commands for 1.5 seconds</span></span>

<span data-ttu-id="3f139-114">In diesem Beispiel werden alle Befehle in der Sitzung für eine und eine halbe Sekunde in den Standbymodus versetzt.</span><span class="sxs-lookup"><span data-stu-id="3f139-114">This example makes all the commands in the session sleep for one and one-half of a seconds.</span></span>

```powershell
Start-Sleep -Seconds 1.5
```

## <span data-ttu-id="3f139-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3f139-115">PARAMETERS</span></span>

### <span data-ttu-id="3f139-116">-Millisekunden</span><span class="sxs-lookup"><span data-stu-id="3f139-116">-Milliseconds</span></span>

<span data-ttu-id="3f139-117">Gibt an, wie lange die Ressource in Millisekunden im Ruhezustand ist.</span><span class="sxs-lookup"><span data-stu-id="3f139-117">Specifies how long the resource sleeps in milliseconds.</span></span> <span data-ttu-id="3f139-118">Der-Parameter kann als **m** abgekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="3f139-118">The parameter can be abbreviated as **m**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases: ms

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3f139-119">-Sekunden</span><span class="sxs-lookup"><span data-stu-id="3f139-119">-Seconds</span></span>

<span data-ttu-id="3f139-120">Gibt an, wie lange die Ressource in Sekunden im Ruhezustand ist.</span><span class="sxs-lookup"><span data-stu-id="3f139-120">Specifies how long the resource sleeps in seconds.</span></span> <span data-ttu-id="3f139-121">Sie können den Parameternamen weglassen, oder Sie können ihn als **s** abkürzen.</span><span class="sxs-lookup"><span data-stu-id="3f139-121">You can omit the parameter name or you can abbreviate it as **s**.</span></span> <span data-ttu-id="3f139-122">Beginnend mit der PowerShell-6.2.0 akzeptiert dieser Parameter nun Bruchzahlen.</span><span class="sxs-lookup"><span data-stu-id="3f139-122">Beginning in PowerShell 6.2.0, this parameter now accepts fractional values.</span></span>

```yaml
Type: System.Double
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3f139-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3f139-123">CommonParameters</span></span>

<span data-ttu-id="3f139-124">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3f139-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3f139-125">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="3f139-125">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3f139-126">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3f139-126">INPUTS</span></span>

### <span data-ttu-id="3f139-127">System.Int32</span><span class="sxs-lookup"><span data-stu-id="3f139-127">System.Int32</span></span>

<span data-ttu-id="3f139-128">Sie können die Anzahl der Sekunden an die Pipeline übergeben `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="3f139-128">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="3f139-129">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3f139-129">OUTPUTS</span></span>

### <span data-ttu-id="3f139-130">Keine</span><span class="sxs-lookup"><span data-stu-id="3f139-130">None</span></span>

<span data-ttu-id="3f139-131">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="3f139-131">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="3f139-132">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3f139-132">NOTES</span></span>

- <span data-ttu-id="3f139-133">Sie können auch auf den `Start-Sleep` integrierten Alias verweisen `sleep` .</span><span class="sxs-lookup"><span data-stu-id="3f139-133">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="3f139-134">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="3f139-134">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="3f139-135">`Ctrl+C` bricht von ab `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="3f139-135">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="3f139-136">`Ctrl+C` bricht nicht aus `[Threading.Thread]::Sleep` .</span><span class="sxs-lookup"><span data-stu-id="3f139-136">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="3f139-137">Weitere Informationen finden Sie unter [Thread. Sleep-Methode](/dotnet/api/system.threading.thread.sleep).</span><span class="sxs-lookup"><span data-stu-id="3f139-137">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="3f139-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3f139-138">RELATED LINKS</span></span>

