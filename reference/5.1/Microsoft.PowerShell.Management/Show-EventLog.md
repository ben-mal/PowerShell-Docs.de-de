---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-EventLog
ms.openlocfilehash: e8dbcf1aa4280c0481714a8a9fb24f2e5ef79ffe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214407"
---
# <span data-ttu-id="fd563-103">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="fd563-103">Show-EventLog</span></span>

## <span data-ttu-id="fd563-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fd563-104">SYNOPSIS</span></span>
<span data-ttu-id="fd563-105">Zeigt die Ereignisprotokolle des lokalen Computers oder eines Remotecomputers in der Ereignisanzeige an.</span><span class="sxs-lookup"><span data-stu-id="fd563-105">Displays the event logs of the local or a remote computer in Event Viewer.</span></span>

## <span data-ttu-id="fd563-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd563-106">SYNTAX</span></span>

```
Show-EventLog [[-ComputerName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="fd563-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd563-107">DESCRIPTION</span></span>
<span data-ttu-id="fd563-108">Das Cmdlet " **Show-EventLog** " wird Ereignisanzeige auf dem lokalen Computer geöffnet und darin alle klassischen Ereignisprotokolle auf dem lokalen Computer oder einem Remote Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd563-108">The **Show-EventLog** cmdlet opens Event Viewer on the local computer and displays in it all of the classic event logs on the local computer or a remote computer.</span></span>

<span data-ttu-id="fd563-109">Zum Öffnen von Ereignisanzeige unter Windows Vista und höheren Versionen des Windows-Betriebssystems muss der aktuelle Benutzer Mitglied der Gruppe "Administratoren" auf dem lokalen Computer sein.</span><span class="sxs-lookup"><span data-stu-id="fd563-109">To open Event Viewer on Windows Vista and later versions of the Windows operating system, the current user must be a member of the Administrators group on the local computer.</span></span>

<span data-ttu-id="fd563-110">Die Cmdlets, die das **EventLog** -Substantiv (die **EventLog** -Cmdlets) enthalten, funktionieren nur in klassischen Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="fd563-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="fd563-111">Verwenden Sie das Cmdlet "Get-WinEvent", um Ereignisse aus Protokollen zu erhalten, in denen die Windows-Ereignisprotokoll Technologie in Windows Vista und höheren Versionen des Windows-Betriebssystems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fd563-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="fd563-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fd563-112">EXAMPLES</span></span>

### <span data-ttu-id="fd563-113">Beispiel 1: Anzeigen von Ereignisprotokollen für den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="fd563-113">Example 1: Display event logs for the local computer</span></span>

```
PS C:\> Show-EventLog
```

<span data-ttu-id="fd563-114">Mit diesem Befehl wird die Ereignisanzeige geöffnet, und darin werden die klassischen Ereignisprotokolle auf dem lokalen Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd563-114">This command opens Event Viewer and displays in it the classic event logs on the local computer.</span></span>

### <span data-ttu-id="fd563-115">Beispiel 2: Anzeigen von Ereignisprotokollen für einen Remote Computer</span><span class="sxs-lookup"><span data-stu-id="fd563-115">Example 2: Display event logs for a remote computer</span></span>

```
PS C:\> Show-EventLog -ComputerName "Server01"
```

<span data-ttu-id="fd563-116">Mit diesem Befehl wird die Ereignisanzeige geöffnet, und darin werden die klassischen Ereignisprotokolle auf dem Computer %%amp;quot;Server01%%amp;quot; angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd563-116">This command opens Event Viewer and displays in it the classic event logs on the Server01 computer.</span></span>

## <span data-ttu-id="fd563-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd563-117">PARAMETERS</span></span>

### <span data-ttu-id="fd563-118">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="fd563-118">-ComputerName</span></span>
<span data-ttu-id="fd563-119">Gibt einen Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="fd563-119">Specifies a remote computer.</span></span>
<span data-ttu-id="fd563-120">" **Show-EventLog** " zeigt die Ereignisprotokolle auf dem angegebenen Computer in Ereignisanzeige auf dem lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="fd563-120">**Show-EventLog** displays the event logs from the specified computer in Event Viewer on the local computer.</span></span>
<span data-ttu-id="fd563-121">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="fd563-121">The default is the local computer.</span></span>

<span data-ttu-id="fd563-122">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.</span><span class="sxs-lookup"><span data-stu-id="fd563-122">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="fd563-123">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="fd563-123">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="fd563-124">Sie können den *ComputerName* -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="fd563-124">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd563-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fd563-125">CommonParameters</span></span>
<span data-ttu-id="fd563-126">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fd563-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd563-127">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fd563-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd563-128">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fd563-128">INPUTS</span></span>

### <span data-ttu-id="fd563-129">Keine</span><span class="sxs-lookup"><span data-stu-id="fd563-129">None</span></span>
<span data-ttu-id="fd563-130">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="fd563-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="fd563-131">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fd563-131">OUTPUTS</span></span>

### <span data-ttu-id="fd563-132">Keine</span><span class="sxs-lookup"><span data-stu-id="fd563-132">None</span></span>
<span data-ttu-id="fd563-133">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="fd563-133">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fd563-134">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fd563-134">NOTES</span></span>

* <span data-ttu-id="fd563-135">Die Windows PowerShell-Eingabeaufforderung wird zurückgegeben, sobald die Ereignisanzeige geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="fd563-135">The Windows PowerShell command prompt returns as soon as Event Viewer opens.</span></span> <span data-ttu-id="fd563-136">Sie können in der aktuellen Sitzung arbeiten, während die Ereignisanzeige geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="fd563-136">You can work in the current session while Event Viewer is open.</span></span>

  <span data-ttu-id="fd563-137">Da für dieses Cmdlet eine Benutzeroberfläche erforderlich ist, kann es nicht in Server Core-Installationen von Windows Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd563-137">Because this cmdlet requires a user interface, it does not work on Server Core installations of Windows Server.</span></span>

*

## <span data-ttu-id="fd563-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fd563-138">RELATED LINKS</span></span>

[<span data-ttu-id="fd563-139">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="fd563-139">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="fd563-140">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="fd563-140">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="fd563-141">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="fd563-141">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="fd563-142">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="fd563-142">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="fd563-143">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="fd563-143">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="fd563-144">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="fd563-144">Write-EventLog</span></span>](Write-EventLog.md)
