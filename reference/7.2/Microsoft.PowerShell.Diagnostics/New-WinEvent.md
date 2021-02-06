---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 5b4b150a1c02e5d0689b44db9b2a984e297db766
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600515"
---
# <span data-ttu-id="c1eaa-102">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="c1eaa-102">New-WinEvent</span></span>

## <span data-ttu-id="c1eaa-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c1eaa-103">SYNOPSIS</span></span>
<span data-ttu-id="c1eaa-104">Es erstellt ein neues Windows-Ereignis für den angegebenen Ereignisanbieter.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-104">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="c1eaa-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c1eaa-105">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="c1eaa-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c1eaa-106">DESCRIPTION</span></span>

<span data-ttu-id="c1eaa-107">Das **New-WinEvent**-Cmdlet erstellt ein ETW-Ereignis (Event Tracing for Windows, Ereignisablaufverfolgung für Windows) für einen Ereignisanbieter.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-107">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="c1eaa-108">Mit diesem Cmdlet können Sie etw-Kanälen Ereignisse aus PowerShell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-108">You can use this cmdlet to add events to ETW channels from PowerShell.</span></span>

## <span data-ttu-id="c1eaa-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c1eaa-109">EXAMPLES</span></span>

### <span data-ttu-id="c1eaa-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="c1eaa-110">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="c1eaa-111">Dieser Befehl verwendet das **New-WinEvent**-Cmdlet, um Ereignis 45090 für den Microsoft-Windows-PowerShell-Anbieter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-111">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="c1eaa-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c1eaa-112">PARAMETERS</span></span>

### <span data-ttu-id="c1eaa-113">-Id</span><span class="sxs-lookup"><span data-stu-id="c1eaa-113">-Id</span></span>

<span data-ttu-id="c1eaa-114">Gibt eine Ereignis-ID an, die über ein Instrumentationsmanifest registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-114">Specifies an event id that was registered through an instrumentation manifest.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1eaa-115">-Nutzlast</span><span class="sxs-lookup"><span data-stu-id="c1eaa-115">-Payload</span></span>

<span data-ttu-id="c1eaa-116">Gibt die Meldung für das Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-116">Specifies the message for the event.</span></span> <span data-ttu-id="c1eaa-117">Wenn das Ereignis in ein Ereignisprotokoll geschrieben wird, wird die Nutzlast in der **Message**-Eigenschaft des Ereignisobjekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-117">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="c1eaa-118">Wenn die angegebene Nutzlast nicht mit der Nutzlast in der Ereignis Definition übereinstimmt, generiert PowerShell eine Warnung, der Befehl wird jedoch trotzdem erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-118">When the specified payload does not match the payload in the event definition, PowerShell generates a warning, but the command still succeeds.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1eaa-119">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="c1eaa-119">-ProviderName</span></span>

<span data-ttu-id="c1eaa-120">Gibt den Ereignisanbieter an, der das Ereignis in ein Ereignisprotokoll schreibt, z. B. „Microsoft-Windows-PowerShell“.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-120">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="c1eaa-121">Ein ETW-Ereignisanbieter ist eine logische Entität, die Ereignisse in ETW-Sitzungen schreibt.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-121">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1eaa-122">-Version</span><span class="sxs-lookup"><span data-stu-id="c1eaa-122">-Version</span></span>

<span data-ttu-id="c1eaa-123">Gibt die Versionsnummer des Ereignisses an.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-123">Specifies the version number of the event.</span></span> <span data-ttu-id="c1eaa-124">Geben Sie die Ereignisnummer ein.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-124">Type the event number.</span></span> <span data-ttu-id="c1eaa-125">PowerShell konvertiert die Nummer in den erforderlichen Byte-Typ.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-125">PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="c1eaa-126">Mit diesem Parameter können Sie ein Ereignis angeben, wenn verschiedene Versionen des gleichen Ereignisses definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-126">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1eaa-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c1eaa-127">CommonParameters</span></span>

<span data-ttu-id="c1eaa-128">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c1eaa-129">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c1eaa-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c1eaa-130">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c1eaa-130">INPUTS</span></span>

### <span data-ttu-id="c1eaa-131">Keine</span><span class="sxs-lookup"><span data-stu-id="c1eaa-131">None</span></span>

<span data-ttu-id="c1eaa-132">Dieses Cmdlet nimmt keine Eingabe von der Pipeline an.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-132">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="c1eaa-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c1eaa-133">OUTPUTS</span></span>

### <span data-ttu-id="c1eaa-134">Keine</span><span class="sxs-lookup"><span data-stu-id="c1eaa-134">None</span></span>

<span data-ttu-id="c1eaa-135">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-135">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="c1eaa-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c1eaa-136">NOTES</span></span>

* <span data-ttu-id="c1eaa-137">Nachdem der Anbieter das-Ereignis in ein Ereignisprotokoll geschrieben hat, können Sie mit dem Get-WinEvent-Cmdlet das Ereignis aus dem Ereignisprotokoll erhalten.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-137">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="c1eaa-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c1eaa-138">RELATED LINKS</span></span>

[<span data-ttu-id="c1eaa-139">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="c1eaa-139">Get-WinEvent</span></span>](Get-WinEvent.md)

