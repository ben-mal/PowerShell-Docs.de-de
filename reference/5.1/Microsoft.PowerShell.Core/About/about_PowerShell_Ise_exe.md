---
description: Erläutert die Verwendung des Befehlszeilen Tools PowerShell_Ise.exe.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_ise_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Ise_exe
ms.openlocfilehash: c7500eb6d8586b9dca568edc4e805c577e94bec4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223340"
---
# <a name="about-powershell-iseexe"></a><span data-ttu-id="c3dd9-104">Informationen zu PowerShell-Ise.exe</span><span class="sxs-lookup"><span data-stu-id="c3dd9-104">About PowerShell Ise.exe</span></span>

## <a name="short-description"></a><span data-ttu-id="c3dd9-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c3dd9-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="c3dd9-106">Erläutert die Verwendung des Befehlszeilen Tools PowerShell_Ise.exe.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-106">Explains how to use the PowerShell_Ise.exe command-line tool.</span></span>

## <a name="long-description"></a><span data-ttu-id="c3dd9-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c3dd9-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="c3dd9-108">PowerShell_Ise.exe startet eine Windows PowerShell Integrated Scripting Environment Sitzung (ISE).</span><span class="sxs-lookup"><span data-stu-id="c3dd9-108">PowerShell_Ise.exe starts a Windows PowerShell Integrated Scripting Environment (ISE) session.</span></span> <span data-ttu-id="c3dd9-109">Sie können Sie in Cmd.exe und in Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-109">You can run it in Cmd.exe and in Windows PowerShell.</span></span>

<span data-ttu-id="c3dd9-110">Geben Sie PowerShell_ISE.exe, PowerShell_ISE oder ISE ein, um PowerShell_ISE.exe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-110">To run PowerShell_ISE.exe, type PowerShell_ISE.exe, PowerShell_ISE, or ISE.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3dd9-111">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c3dd9-111">SYNTAX</span></span>

```
PowerShell_Ise[.exe]
PowerShell_ISE[.exe]
ISE[.exe]
[-File]<FilePath[]> [-NoProfile] [-MTA]
-Help | ? | -? | /? Displays the syntax and describes the command-line switches.
```

## <a name="parameters"></a><span data-ttu-id="c3dd9-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c3dd9-112">PARAMETERS</span></span>

### <a name="-file"></a><span data-ttu-id="c3dd9-113">-File</span><span class="sxs-lookup"><span data-stu-id="c3dd9-113">-File</span></span>

<span data-ttu-id="c3dd9-114">Öffnet die angegebenen Dateien in Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-114">Opens the specified files in Windows PowerShell ISE.</span></span> <span data-ttu-id="c3dd9-115">Der Parameter Name ("-file") ist optional.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-115">The parameter name ("-File") is optional.</span></span> <span data-ttu-id="c3dd9-116">Um mehr als eine Datei aufzulisten, geben Sie eine Text Zeichenfolge ein, die in Anführungszeichen eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-116">To list more than one file, enter one text string enclosed in quotation marks.</span></span> <span data-ttu-id="c3dd9-117">Verwenden Sie Kommas, um die Dateinamen innerhalb der Zeichenfolge voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-117">Use commas to separate the file names within the string.</span></span>

<span data-ttu-id="c3dd9-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c3dd9-118">For example:</span></span>

<span data-ttu-id="c3dd9-119">PowerShell_ISE Datei "File1.ps1, File2.ps1 File3.xml".</span><span class="sxs-lookup"><span data-stu-id="c3dd9-119">PowerShell_ISE -File "File1.ps1,File2.ps1,File3.xml".</span></span>

<span data-ttu-id="c3dd9-120">Leerzeichen zwischen den Dateinamen sind in Windows PowerShell zulässig, werden jedoch möglicherweise nicht ordnungsgemäß von anderen Programmen, z. b. Cmd.exe, interpretiert.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-120">Spaces between the file names are permitted in Windows PowerShell, but might not be interpreted correctly by other programs, such as Cmd.exe.</span></span>

<span data-ttu-id="c3dd9-121">Sie können diesen Parameter verwenden, um eine beliebige Textdatei zu öffnen, einschließlich Windows PowerShell-Skriptdateien und XML-Dateien.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-121">You can use this parameter to open any text file, including Windows PowerShell script files and XML files.</span></span>

### <a name="-mta"></a><span data-ttu-id="c3dd9-122">-Mta</span><span class="sxs-lookup"><span data-stu-id="c3dd9-122">-Mta</span></span>

<span data-ttu-id="c3dd9-123">Startet Windows PowerShell ISE mit einem Multithread-Apartment.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-123">Starts Windows PowerShell ISE using a multi-threaded apartment.</span></span> <span data-ttu-id="c3dd9-124">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-124">This parameter is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="c3dd9-125">Single Thread-Apartment (STA) ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-125">Single-threaded apartment (STA) is the default.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="c3dd9-126">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="c3dd9-126">-NoProfile</span></span>

<span data-ttu-id="c3dd9-127">Führt keine Windows PowerShell-Profile aus.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-127">Does not run Windows PowerShell profiles.</span></span> <span data-ttu-id="c3dd9-128">Standardmäßig werden Windows PowerShell-Profile in jeder Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-128">By default, Windows PowerShell profiles are run in every session.</span></span>

<span data-ttu-id="c3dd9-129">Dieser Parameter wird empfohlen, wenn Sie freigegebene Inhalte schreiben, z. b. Funktionen und Skripts, die auf Systemen mit unterschiedlichen Profilen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-129">This parameter is recommended when you are writing shared content, such as functions and scripts that will be run on systems with different profiles.</span></span>
<span data-ttu-id="c3dd9-130">Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c3dd9-130">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="-help---"></a><span data-ttu-id="c3dd9-131">-Hilfe-?,/?</span><span class="sxs-lookup"><span data-stu-id="c3dd9-131">-Help -?, /?</span></span>

<span data-ttu-id="c3dd9-132">Zeigt die Hilfe für PowerShell_ISE.exe an.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-132">Displays help for PowerShell_ISE.exe.</span></span>

## <a name="examples"></a><span data-ttu-id="c3dd9-133">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c3dd9-133">EXAMPLES</span></span>

<span data-ttu-id="c3dd9-134">Mit diesen Befehlen wird Windows PowerShell ISE gestartet.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-134">These commands start Windows PowerShell ISE.</span></span> <span data-ttu-id="c3dd9-135">Diese Befehle sind gleichwertig und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-135">The commands are equivalent and can be used interchangeably.</span></span>

```
PS C:> PowerShell_ISE.exe
PS C:> PowerShell_ISE
PS C:> ISE
```

<span data-ttu-id="c3dd9-136">Mit diesen Befehlen wird das Get-Profile.ps1 Skript in Windows PowerShell ISE geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-136">These commands open the Get-Profile.ps1 script in Windows PowerShell ISE.</span></span>
<span data-ttu-id="c3dd9-137">Diese Befehle sind gleichwertig und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-137">The commands are equivalent and can be used interchangeably.</span></span>

```
PS C:> PowerShell_ISE.exe -File .\Get-Profile.ps1
PS C:> ISE -File .\Get-Profile.ps1
PS C:> ISE .\Get-Profile.ps1
```

<span data-ttu-id="c3dd9-138">Mit diesem Befehl werden die Get-Backups.ps1-und Get-BackupInstance.ps1 Skripts in Windows PowerShell ISE geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-138">This command opens the Get-Backups.ps1 and Get-BackupInstance.ps1 scripts in Windows PowerShell ISE.</span></span> <span data-ttu-id="c3dd9-139">Um mehr als eine Datei zu öffnen, verwenden Sie ein Komma, um die Dateinamen voneinander zu trennen, und schließen Sie den gesamten Dateinamen in Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-139">To open more than one file, use a comma to separate the file names and enclose the entire file name value in quotation marks.</span></span>

```
PS C:> ISE -File ".\Get-Backups.ps1,Get-BackupInstance.ps1"
```

<span data-ttu-id="c3dd9-140">Mit diesem Befehl wird Windows PowerShell ISE ohne profile gestartet.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-140">This command starts Windows PowerShell ISE with no profiles.</span></span>

```
PS C:> ISE -NoProfile
```

<span data-ttu-id="c3dd9-141">Mit diesem Befehl wird die Hilfe für PowerShell_ISE.exe abgerufen.</span><span class="sxs-lookup"><span data-stu-id="c3dd9-141">This command gets help for PowerShell_ISE.exe.</span></span>

```
PS C:> ISE -help
```

## <a name="see-also"></a><span data-ttu-id="c3dd9-142">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="c3dd9-142">SEE ALSO</span></span>

[<span data-ttu-id="c3dd9-143">about_PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="c3dd9-143">about_PowerShell.exe</span></span>](about_PowerShell_exe.md)

[<span data-ttu-id="c3dd9-144">about_Windows_PowerShell_ISE</span><span class="sxs-lookup"><span data-stu-id="c3dd9-144">about_Windows_PowerShell_ISE</span></span>](about_Windows_PowerShell_ISE.md)

[<span data-ttu-id="c3dd9-145">Windows PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="c3dd9-145">Windows PowerShell Integrated Scripting Environment (ISE)</span></span>](/powershell/scripting/windows-powershell/ise/introducing-the-windows-powershell-ise)
