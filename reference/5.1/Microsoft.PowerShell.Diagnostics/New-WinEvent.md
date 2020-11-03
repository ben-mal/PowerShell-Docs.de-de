---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 202d1792769dcdcda7a156621bfc50c89a1a92ac
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211948"
---
# <span data-ttu-id="f1314-103">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="f1314-103">New-WinEvent</span></span>

## <span data-ttu-id="f1314-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f1314-104">SYNOPSIS</span></span>

<span data-ttu-id="f1314-105">Es erstellt ein neues Windows-Ereignis für den angegebenen Ereignisanbieter.</span><span class="sxs-lookup"><span data-stu-id="f1314-105">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="f1314-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f1314-106">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="f1314-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f1314-107">DESCRIPTION</span></span>

<span data-ttu-id="f1314-108">Das **New-WinEvent** -Cmdlet erstellt ein ETW-Ereignis (Event Tracing for Windows, Ereignisablaufverfolgung für Windows) für einen Ereignisanbieter.</span><span class="sxs-lookup"><span data-stu-id="f1314-108">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="f1314-109">Mit diesem Cmdlet können Sie ETW-Kanälen aus Windows PowerShell Ereignisse hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f1314-109">You can use this cmdlet to add events to ETW channels from Windows PowerShell.</span></span>

## <span data-ttu-id="f1314-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f1314-110">EXAMPLES</span></span>

### <span data-ttu-id="f1314-111">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="f1314-111">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="f1314-112">Dieser Befehl verwendet das **New-WinEvent** -Cmdlet, um Ereignis 45090 für den Microsoft-Windows-PowerShell-Anbieter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f1314-112">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="f1314-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f1314-113">PARAMETERS</span></span>

### <span data-ttu-id="f1314-114">-Id</span><span class="sxs-lookup"><span data-stu-id="f1314-114">-Id</span></span>

<span data-ttu-id="f1314-115">Gibt eine Ereignis-ID an, die über ein Instrumentationsmanifest registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="f1314-115">Specifies an event id that was registered through an instrumentation manifest.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f1314-116">-Nutzlast</span><span class="sxs-lookup"><span data-stu-id="f1314-116">-Payload</span></span>

<span data-ttu-id="f1314-117">Gibt die Meldung für das Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="f1314-117">Specifies the message for the event.</span></span> <span data-ttu-id="f1314-118">Wenn das Ereignis in ein Ereignisprotokoll geschrieben wird, wird die Nutzlast in der **Message** -Eigenschaft des Ereignisobjekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f1314-118">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="f1314-119">Wenn die angegebene Nutzlast nicht mit der Nutzlast in der Ereignisdefinition übereinstimmt, wird von Windows PowerShell zwar eine Warnung generiert, der Befehl wird jedoch trotzdem erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f1314-119">When the specified payload does not match the payload in the event definition, Windows PowerShell generates a warning, but the command still succeeds.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f1314-120">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="f1314-120">-ProviderName</span></span>

<span data-ttu-id="f1314-121">Gibt den Ereignisanbieter an, der das Ereignis in ein Ereignisprotokoll schreibt, z. B. „Microsoft-Windows-PowerShell“.</span><span class="sxs-lookup"><span data-stu-id="f1314-121">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="f1314-122">Ein ETW-Ereignisanbieter ist eine logische Entität, die Ereignisse in ETW-Sitzungen schreibt.</span><span class="sxs-lookup"><span data-stu-id="f1314-122">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f1314-123">-Version</span><span class="sxs-lookup"><span data-stu-id="f1314-123">-Version</span></span>

<span data-ttu-id="f1314-124">Gibt die Versionsnummer des Ereignisses an.</span><span class="sxs-lookup"><span data-stu-id="f1314-124">Specifies the version number of the event.</span></span> <span data-ttu-id="f1314-125">Geben Sie die Ereignisnummer ein.</span><span class="sxs-lookup"><span data-stu-id="f1314-125">Type the event number.</span></span> <span data-ttu-id="f1314-126">Windows PowerShell konvertiert die Nummer in den erforderlichen Byte-Typ.</span><span class="sxs-lookup"><span data-stu-id="f1314-126">Windows PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="f1314-127">Mit diesem Parameter können Sie ein Ereignis angeben, wenn verschiedene Versionen des gleichen Ereignisses definiert sind.</span><span class="sxs-lookup"><span data-stu-id="f1314-127">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

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

### <span data-ttu-id="f1314-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f1314-128">CommonParameters</span></span>

<span data-ttu-id="f1314-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f1314-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f1314-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f1314-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f1314-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f1314-131">INPUTS</span></span>

### <span data-ttu-id="f1314-132">Keine</span><span class="sxs-lookup"><span data-stu-id="f1314-132">None</span></span>

<span data-ttu-id="f1314-133">Dieses Cmdlet nimmt keine Eingabe von der Pipeline an.</span><span class="sxs-lookup"><span data-stu-id="f1314-133">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="f1314-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f1314-134">OUTPUTS</span></span>

### <span data-ttu-id="f1314-135">Keine</span><span class="sxs-lookup"><span data-stu-id="f1314-135">None</span></span>

<span data-ttu-id="f1314-136">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="f1314-136">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="f1314-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f1314-137">NOTES</span></span>

* <span data-ttu-id="f1314-138">Nachdem der Anbieter das-Ereignis in ein Ereignisprotokoll geschrieben hat, können Sie mit dem Get-WinEvent-Cmdlet das Ereignis aus dem Ereignisprotokoll erhalten.</span><span class="sxs-lookup"><span data-stu-id="f1314-138">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="f1314-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f1314-139">RELATED LINKS</span></span>

[<span data-ttu-id="f1314-140">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="f1314-140">Get-WinEvent</span></span>](Get-WinEvent.md)
