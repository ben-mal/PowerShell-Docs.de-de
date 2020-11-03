---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSnapin
ms.openlocfilehash: 472a4c8fbb9eb0d37827aff4fcfd6bb9a67f4743
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211999"
---
# <span data-ttu-id="947b0-103">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="947b0-103">Get-PSSnapin</span></span>

## <span data-ttu-id="947b0-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="947b0-104">SYNOPSIS</span></span>
<span data-ttu-id="947b0-105">Ruft die Windows PowerShell-Snap-Ins auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="947b0-105">Gets the Windows PowerShell snap-ins on the computer.</span></span>

## <span data-ttu-id="947b0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="947b0-106">SYNTAX</span></span>

```
Get-PSSnapin [[-Name] <String[]>] [-Registered] [<CommonParameters>]
```

## <span data-ttu-id="947b0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="947b0-107">DESCRIPTION</span></span>
<span data-ttu-id="947b0-108">Das **Get-PSSnapin** -Cmdlet ruft die Windows PowerShell-Snap-Ins ab, die der aktuellen Sitzung hinzugefügt wurden oder auf dem System registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="947b0-108">The **Get-PSSnapin** cmdlet gets the Windows PowerShell snap-ins that have been added to the current session or that have been registered on the system.</span></span>
<span data-ttu-id="947b0-109">Dieses Cmdlet listet die Snap-Ins in der Reihenfolge auf, in der Sie erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="947b0-109">This cmdlet lists the snap-ins in the order in which they are detected.</span></span>

<span data-ttu-id="947b0-110">**Get-PSSnapin** ruft nur registrierte Snap-Ins ab. Verwenden Sie zum Registrieren eines Windows PowerShell-Snap-Ins das InstallUtil-Tool, das im Microsoft .NET Framework 2,0 enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="947b0-110">**Get-PSSnapin** gets only registered snap-ins. To register a Windows PowerShell snap-in, use the InstallUtil tool included with the Microsoft .NET Framework 2.0.</span></span>
<span data-ttu-id="947b0-111">Weitere Informationen finden Sie unter [Registrieren von Cmdlets, Anbietern und Host Anwendungen](https://go.microsoft.com/fwlink/?LinkID=143619) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="947b0-111">For more information, see [How to Register Cmdlets, Providers, and Host Applications](https://go.microsoft.com/fwlink/?LinkID=143619) in the MSDN library.</span></span>

<span data-ttu-id="947b0-112">Ab Windows PowerShell 3,0 werden die in Windows PowerShell enthaltenen Hauptbefehle in Module gepackt.</span><span class="sxs-lookup"><span data-stu-id="947b0-112">Starting in Windows PowerShell 3.0, the core commands that are included in Windows PowerShell are packaged in modules.</span></span>
<span data-ttu-id="947b0-113">Eine Ausnahme ist das Snap-In **Microsoft.PowerShell.Core** (PSSnapin).</span><span class="sxs-lookup"><span data-stu-id="947b0-113">The exception is **Microsoft.PowerShell.Core** , which is a snap-in (PSSnapin).</span></span>
<span data-ttu-id="947b0-114">Standardmäßig wird nur das **Microsoft.PowerShell.Core** -Snap-In der Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="947b0-114">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span>
<span data-ttu-id="947b0-115">Module werden bei der ersten Verwendung automatisch importiert, und Sie können das Cmdlet "Import-Module" verwenden, um Sie zu importieren.</span><span class="sxs-lookup"><span data-stu-id="947b0-115">Modules are imported automatically on first use and you can use the Import-Module cmdlet to import them.</span></span>

## <span data-ttu-id="947b0-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="947b0-116">EXAMPLES</span></span>

### <span data-ttu-id="947b0-117">Beispiel 1: Get-Snap-Ins, die zurzeit geladen sind</span><span class="sxs-lookup"><span data-stu-id="947b0-117">Example 1: Get snap-ins that are currently loaded</span></span>

```
PS C:\> Get-PSSnapIn
```

<span data-ttu-id="947b0-118">Dieser Befehl ruft die Windows PowerShell-Snap-Ins ab, die derzeit in der Sitzung geladen sind.</span><span class="sxs-lookup"><span data-stu-id="947b0-118">This command gets the Windows PowerShell snap-ins that are currently loaded in the session.</span></span>
<span data-ttu-id="947b0-119">Dies umfasst die mit Windows PowerShell installierten Snap-Ins und die Snap-Ins, die der Sitzung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="947b0-119">This includes the snap-ins that are installed with Windows PowerShell and those that have been added to the session.</span></span>

### <span data-ttu-id="947b0-120">Beispiel 2: Get-Snap-Ins, die registriert wurden</span><span class="sxs-lookup"><span data-stu-id="947b0-120">Example 2: Get snap-ins that have been registered</span></span>

```
PS C:\> get-PSSnapIn -Registered
```

<span data-ttu-id="947b0-121">Dieser Befehl ruft die für den Computer registrierten Windows PowerShell-Snap-Ins ab, einschließlich der Snap-Ins, die der Sitzung bereits hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="947b0-121">This command gets the Windows PowerShell snap-ins that have been registered on the computer, including those that have already been added to the session.</span></span>
<span data-ttu-id="947b0-122">Die Ausgabe umfasst keine Snap-Ins, die mit noch nicht beim System registrierten Dynamic-Link Libraries (DLLs) von Windows PowerShell oder Windows PowerShell-Snap-Ins installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="947b0-122">The output does not include snap-ins that are installed with Windows PowerShell or Windows PowerShell snap-in dynamic-link libraries (DLLs) that have not yet been registered on the system.</span></span>

### <span data-ttu-id="947b0-123">Beispiel 3: erhalten der aktuellen Snap-Ins, die einer Zeichenfolge entsprechen</span><span class="sxs-lookup"><span data-stu-id="947b0-123">Example 3: Get current snap-ins that match a string</span></span>

```
PS C:\> Get-PSSnapIn -Name smp*
```

<span data-ttu-id="947b0-124">Dieser Befehl ruft die Windows PowerShell-Snap-Ins in der aktuellen Sitzung ab, deren Namen mit "SMP" beginnen.</span><span class="sxs-lookup"><span data-stu-id="947b0-124">This command gets the Windows PowerShell snap-ins in the current session that have names that begin with smp.</span></span>

## <span data-ttu-id="947b0-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="947b0-125">PARAMETERS</span></span>

### <span data-ttu-id="947b0-126">-Name</span><span class="sxs-lookup"><span data-stu-id="947b0-126">-Name</span></span>
<span data-ttu-id="947b0-127">Gibt ein Array von Snap-in-Namen an.</span><span class="sxs-lookup"><span data-stu-id="947b0-127">Specifies an array of snap-in names.</span></span>
<span data-ttu-id="947b0-128">Dieses Cmdlet ruft nur die angegebenen Windows PowerShell-Snap-Ins ab. Platzhalter Zeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="947b0-128">This cmdlet gets only the specified Windows PowerShell snap-ins. Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="947b0-129">-Registriert</span><span class="sxs-lookup"><span data-stu-id="947b0-129">-Registered</span></span>
<span data-ttu-id="947b0-130">Gibt an, dass mit diesem Cmdlet die Windows PowerShell-Snap-Ins abgerufen werden, die im System registriert wurden, auch wenn Sie der Sitzung noch nicht hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="947b0-130">Indicates that this cmdlet gets the Windows PowerShell snap-ins that have been registered on the system even if they have not yet been added to the session.</span></span>

<span data-ttu-id="947b0-131">Die mit Windows PowerShell installierten Snap-Ins werden in dieser Liste nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="947b0-131">The snap-ins that are installed with Windows PowerShell do not appear in this list.</span></span>

<span data-ttu-id="947b0-132">Ohne diesen Parameter ruft **Get-PSSnapin** die Windows PowerShell-Snap-Ins ab, die der Sitzung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="947b0-132">Without this parameter, **Get-PSSnapin** gets the Windows PowerShell snap-ins that have been added to the session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="947b0-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="947b0-133">CommonParameters</span></span>
<span data-ttu-id="947b0-134">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="947b0-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="947b0-135">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="947b0-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="947b0-136">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="947b0-136">INPUTS</span></span>

### <span data-ttu-id="947b0-137">Keine</span><span class="sxs-lookup"><span data-stu-id="947b0-137">None</span></span>
<span data-ttu-id="947b0-138">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="947b0-138">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="947b0-139">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="947b0-139">OUTPUTS</span></span>

### <span data-ttu-id="947b0-140">System. Management. Automation. pssnapininfo</span><span class="sxs-lookup"><span data-stu-id="947b0-140">System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="947b0-141">Get-PSSnapin gibt ein Objekt für jedes abgerufene Snap-In zurück.</span><span class="sxs-lookup"><span data-stu-id="947b0-141">Get-PSSnapin returns an object for each snap-in that it gets.</span></span>

## <span data-ttu-id="947b0-142">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="947b0-142">NOTES</span></span>

* <span data-ttu-id="947b0-143">Ab Windows PowerShell 3,0 werden die Kern Befehle, die mit Windows PowerShell installiert werden, in Module verpackt.</span><span class="sxs-lookup"><span data-stu-id="947b0-143">Starting in Windows PowerShell 3.0, the core commands that are installed with Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="947b0-144">In Windows PowerShell 2,0 und in Host Programmen, die in neueren Versionen von Windows PowerShell ältere Sitzungen erstellen, werden die Hauptbefehle in Snap-Ins ( **PSSnapIn** ) verpackt.</span><span class="sxs-lookup"><span data-stu-id="947b0-144">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of Windows PowerShell, the core commands are packaged in snap-ins ( **PSSnapin** ).</span></span> <span data-ttu-id="947b0-145">Die Ausnahme ist **Microsoft. PowerShell. Core** , bei der es sich immer um ein Snap-in handelt.</span><span class="sxs-lookup"><span data-stu-id="947b0-145">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="947b0-146">Remote Sitzungen, wie z. b. diejenigen, die mit dem Cmdlet "New-PSSession" gestartet werden, sind auch ältere Sitzungen, die Core-Snap-Ins enthalten.</span><span class="sxs-lookup"><span data-stu-id="947b0-146">Also, remote sessions, such as those started by the New-PSSession cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="947b0-147">Weitere Informationen über die **CreateDefault2** -Methode, die Sitzungen im neueren Stil mit Kernmodulen erstellt, finden Sie unter [CreateDefault2-Methode](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="947b0-147">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

## <span data-ttu-id="947b0-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="947b0-148">RELATED LINKS</span></span>

[<span data-ttu-id="947b0-149">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="947b0-149">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="947b0-150">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="947b0-150">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
