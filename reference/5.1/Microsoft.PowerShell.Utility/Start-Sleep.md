---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 3/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4add39c09b6123aaf8c9302529346a6b1dec391
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213663"
---
# <span data-ttu-id="6bf7c-103">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="6bf7c-103">Start-Sleep</span></span>

## <span data-ttu-id="6bf7c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6bf7c-104">SYNOPSIS</span></span>
<span data-ttu-id="6bf7c-105">Hält die Aktivität in einem Skript oder einer Sitzung für den angegebenen Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-105">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="6bf7c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6bf7c-106">SYNTAX</span></span>

### <span data-ttu-id="6bf7c-107">Sekunden (Standard)</span><span class="sxs-lookup"><span data-stu-id="6bf7c-107">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="6bf7c-108">Millisekunden</span><span class="sxs-lookup"><span data-stu-id="6bf7c-108">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="6bf7c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6bf7c-109">DESCRIPTION</span></span>

<span data-ttu-id="6bf7c-110">Das- `Start-Sleep` Cmdlet hält die Aktivität in einem Skript oder einer Sitzung für den angegebenen Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-110">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span>
<span data-ttu-id="6bf7c-111">Sie können es für viele Aufgaben verwenden, z. B. Warten auf den Abschluss eines Vorgangs oder Anhalten, bevor ein Vorgang wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-111">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="6bf7c-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6bf7c-112">EXAMPLES</span></span>

### <span data-ttu-id="6bf7c-113">Beispiel 1: alle Befehle für 15 Sekunden in den Standbymodus</span><span class="sxs-lookup"><span data-stu-id="6bf7c-113">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

<span data-ttu-id="6bf7c-114">Mit diesem Befehl werden alle Befehle in der Sitzung für 15 Sekunden in den Ruhezustand versetzt.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-114">This command makes all commands in the session sleep for 15 seconds.</span></span>

### <span data-ttu-id="6bf7c-115">Beispiel 2: alle Befehle im Standbymodus</span><span class="sxs-lookup"><span data-stu-id="6bf7c-115">Example 2: Sleep all commands</span></span>

```powershell
Start-Sleep -m 500
```

<span data-ttu-id="6bf7c-116">Mit diesem Befehl werden alle Befehle in der Sitzung für eine halbe Sekunde (500 Millisekunden) in den Ruhezustand versetzt.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-116">This command makes all the commands in the session sleep for one-half of a second (500 milliseconds).</span></span>

## <span data-ttu-id="6bf7c-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6bf7c-117">PARAMETERS</span></span>

### <span data-ttu-id="6bf7c-118">-Millisekunden</span><span class="sxs-lookup"><span data-stu-id="6bf7c-118">-Milliseconds</span></span>

<span data-ttu-id="6bf7c-119">Gibt an, wie lange die Ressource in Millisekunden im Ruhezustand ist.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-119">Specifies how long the resource sleeps in milliseconds.</span></span>
<span data-ttu-id="6bf7c-120">Der-Parameter kann als **m** abgekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-120">The parameter can be abbreviated as **m** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6bf7c-121">-Sekunden</span><span class="sxs-lookup"><span data-stu-id="6bf7c-121">-Seconds</span></span>

<span data-ttu-id="6bf7c-122">Gibt an, wie lange die Ressource in Sekunden im Ruhezustand ist.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-122">Specifies how long the resource sleeps in seconds.</span></span>
<span data-ttu-id="6bf7c-123">Sie können den Parameternamen ( **Sekunden** ) weglassen, oder Sie können ihn als **s** abkürzen.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-123">You can omit the parameter name ( **Seconds** ), or you can abbreviate it as **s** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6bf7c-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6bf7c-124">CommonParameters</span></span>

<span data-ttu-id="6bf7c-125">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6bf7c-126">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6bf7c-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="6bf7c-127">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6bf7c-127">INPUTS</span></span>

### <span data-ttu-id="6bf7c-128">System.Int32</span><span class="sxs-lookup"><span data-stu-id="6bf7c-128">System.Int32</span></span>

<span data-ttu-id="6bf7c-129">Sie können die Anzahl der Sekunden an die Pipeline übergeben `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="6bf7c-129">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="6bf7c-130">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6bf7c-130">OUTPUTS</span></span>

### <span data-ttu-id="6bf7c-131">Keine</span><span class="sxs-lookup"><span data-stu-id="6bf7c-131">None</span></span>

<span data-ttu-id="6bf7c-132">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="6bf7c-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6bf7c-133">NOTES</span></span>

- <span data-ttu-id="6bf7c-134">Sie können auch auf den `Start-Sleep` integrierten Alias verweisen `sleep` .</span><span class="sxs-lookup"><span data-stu-id="6bf7c-134">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="6bf7c-135">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="6bf7c-135">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="6bf7c-136">`Ctrl+C` bricht von ab `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="6bf7c-136">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="6bf7c-137">`Ctrl+C` bricht nicht aus `[Threading.Thread]::Sleep` .</span><span class="sxs-lookup"><span data-stu-id="6bf7c-137">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="6bf7c-138">Weitere Informationen finden Sie unter [Thread. Sleep-Methode](/dotnet/api/system.threading.thread.sleep).</span><span class="sxs-lookup"><span data-stu-id="6bf7c-138">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="6bf7c-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6bf7c-139">RELATED LINKS</span></span>
