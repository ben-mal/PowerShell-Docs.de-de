---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-console?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Console
ms.openlocfilehash: 7b643b5f9b6868a5da988b19b65dead24f986f67
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212060"
---
# <span data-ttu-id="56a93-103">Export-Console</span><span class="sxs-lookup"><span data-stu-id="56a93-103">Export-Console</span></span>

## <span data-ttu-id="56a93-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="56a93-104">SYNOPSIS</span></span>
<span data-ttu-id="56a93-105">Exportiert die Namen von Snap-Ins in der aktuellen Sitzung in eine Konsolendatei.</span><span class="sxs-lookup"><span data-stu-id="56a93-105">Exports the names of snap-ins in the current session to a console file.</span></span>

## <span data-ttu-id="56a93-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="56a93-106">SYNTAX</span></span>

```
Export-Console [[-Path] <String>] [-Force] [-NoClobber] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="56a93-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="56a93-107">DESCRIPTION</span></span>
<span data-ttu-id="56a93-108">Das **Export-Console-** Cmdlet exportiert die Namen der Windows PowerShell-Snap-Ins in der aktuellen Sitzung in eine Windows PowerShell-Konsolen Datei (. psc1).</span><span class="sxs-lookup"><span data-stu-id="56a93-108">The **Export-Console** cmdlet exports the names of the Windows PowerShell snap-ins in the current session to a Windows PowerShell console file (.psc1).</span></span>
<span data-ttu-id="56a93-109">Sie können dieses Cmdlet verwenden, um die Snap-Ins für die Verwendung in zukünftigen Sitzungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="56a93-109">You can use this cmdlet to save the snap-ins for use in future sessions.</span></span>

<span data-ttu-id="56a93-110">Wenn Sie die Snap-Ins in der Konsolen Datei. psc1 zu einer Sitzung hinzufügen möchten, starten Sie Windows PowerShell (Powershell.exe) in der Befehlszeile, indem Sie Cmd.exe oder eine andere Windows PowerShell-Sitzung verwenden, und verwenden Sie dann den *PsConsoleFile* -Parameter von Powershell.exe, um die Konsolen Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="56a93-110">To add the snap-ins in the .psc1 console file to a session, start Windows PowerShell (Powershell.exe) at the command line by using Cmd.exe or another Windows PowerShell session, and then use the *PSConsoleFile* parameter of Powershell.exe to specify the console file.</span></span>

<span data-ttu-id="56a93-111">Weitere Informationen zu Windows PowerShell-Snap-Ins finden Sie unter „about_PSSnapins“.</span><span class="sxs-lookup"><span data-stu-id="56a93-111">For more information about Windows PowerShell snap-ins, see about_PSSnapins.</span></span>

## <span data-ttu-id="56a93-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="56a93-112">EXAMPLES</span></span>

### <span data-ttu-id="56a93-113">Beispiel 1: Exportieren der Namen von Snap-Ins in der aktuellen Sitzung</span><span class="sxs-lookup"><span data-stu-id="56a93-113">Example 1: Export the names of snap-ins in the current session</span></span>

```
PS C:\> Export-Console -Path $pshome\Consoles\ConsoleS1.psc1
```

<span data-ttu-id="56a93-114">Dieser Befehl exportiert die Namen der Windows PowerShell-Snap-Ins in der aktuellen Sitzung in die Datei "consoles1. psc1 im Ordner Konsolen des Windows PowerShell-Installations Ordners, $PSHome.</span><span class="sxs-lookup"><span data-stu-id="56a93-114">This command exports the names of Windows PowerShell snap-ins in the current session to the ConsoleS1.psc1 file in the Consoles folder of the Windows PowerShell installation folder, $pshome.</span></span>

### <span data-ttu-id="56a93-115">Beispiel 2: Exportieren der Namen von Snap-Ins in die aktuellste Konsolen Datei</span><span class="sxs-lookup"><span data-stu-id="56a93-115">Example 2: Export the names of snap-ins to the most recent console file</span></span>

```
PS C:\> Export-Console
```

<span data-ttu-id="56a93-116">Dieser Befehl exportiert die Namen der Windows PowerShell-Snap-Ins aus der aktuellen Sitzung in die Windows PowerShell-Konsolendatei, die in der aktuellen Sitzung zuletzt verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="56a93-116">This command exports the names of Windows PowerShell snap-ins from current session to the Windows PowerShell console file that was most recently used in the current session.</span></span>
<span data-ttu-id="56a93-117">Der vorherige Dateiinhalt wird überschrieben.</span><span class="sxs-lookup"><span data-stu-id="56a93-117">It overwrites the previous file contents.</span></span>

<span data-ttu-id="56a93-118">Wenn Sie in der aktuellen Sitzung keine Konsolendatei exportiert haben, werden Sie vor dem Fortfahren zur Bestätigung und dann zur Eingabe eines Dateinamens aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="56a93-118">If you have not exported a console file during the current session, you are prompted for permission to continue and then prompted for a file name.</span></span>

### <span data-ttu-id="56a93-119">Beispiel 3: Hinzufügen eines Snap-Ins und Exportieren der Namen von Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="56a93-119">Example 3: Add a snap-in and export the names of snap-ins</span></span>

```
PS C:\> Add-PSSnapin NewPSSnapin
PS C:\> Export-Console -path NewPSSnapinConsole.psc1
PS C:\> powershell.exe -PsConsoleFile NewPsSnapinConsole.psc1
```

<span data-ttu-id="56a93-120">Diese Befehle fügen das Windows PowerShell-Snap-In „NewPSSnapin“ zur aktuellen Sitzung hinzu, exportieren die Namen der Windows PowerShell-Snap-Ins in der aktuellen Sitzung in eine Konsolendatei und starten dann eine Windows PowerShell-Sitzung mit der Konsolendatei.</span><span class="sxs-lookup"><span data-stu-id="56a93-120">These commands add the NewPSSnapin Windows PowerShell snap-in to the current session, export the names of Windows PowerShell snap-ins in the current session to a console file, and then start a Windows PowerShell session with the console file.</span></span>

<span data-ttu-id="56a93-121">Der erste Befehl verwendet das **Add-PSSnapin** -Cmdlet, um das newpssnapin-Snap-in zur aktuellen Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="56a93-121">The first command uses the **Add-PSSnapin** cmdlet to add the NewPSSnapin snap-in to the current session.</span></span>
<span data-ttu-id="56a93-122">Sie können nur Windows PowerShell-Snap-Ins hinzufügen, die in Ihrem System registriert sind.</span><span class="sxs-lookup"><span data-stu-id="56a93-122">You can only add Windows PowerShell snap-ins that are registered on your system.</span></span>

<span data-ttu-id="56a93-123">Der zweite Befehl exportiert die Namen der Windows PowerShell-Snap-Ins in die NewPSSnapinConsole.psc1-Datei.</span><span class="sxs-lookup"><span data-stu-id="56a93-123">The second command exports the Windows PowerShell snap-in names to the NewPSSnapinConsole.psc1 file.</span></span>

<span data-ttu-id="56a93-124">Der dritte Befehl startet Windows PowerShell mit der NewPSSnapinConsole.psc1-Datei.</span><span class="sxs-lookup"><span data-stu-id="56a93-124">The third command starts Windows PowerShell with the NewPSSnapinConsole.psc1 file.</span></span>
<span data-ttu-id="56a93-125">Da die Konsolendatei den Namen des Windows PowerShell-Snap-Ins enthält, sind die Cmdlets und Anbieter im Snap-In in der aktuellen Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="56a93-125">Because the console file includes the Windows PowerShell snap-in name, the cmdlets and providers in the snap-in are available in the current session.</span></span>

### <span data-ttu-id="56a93-126">Beispiel 4: Exportieren von Namen von Snap-Ins an einen angegebenen Speicherort</span><span class="sxs-lookup"><span data-stu-id="56a93-126">Example 4: Export names of snap-ins to a specified location</span></span>

```
PS C:\> export-console -path Console01
PS C:\> notepad console01.psc1
<?xml version="1.0" encoding="utf-8"?>
<PSConsoleFile ConsoleSchemaVersion="1.0">
  <PSVersion>2.0</PSVersion>
  <PSSnapIns>
     <PSSnapIn Name="NewPSSnapin" />
  </PSSnapIns>
</PSConsoleFile>
```

<span data-ttu-id="56a93-127">Dieser Befehl exportiert die Namen der Windows PowerShell-Snap-Ins in der aktuellen Sitzung in die Datei „Console01.psc1“ im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="56a93-127">This command exports the names of the Windows PowerShell snap-ins in the current session to the Console01.psc1 file in the current directory.</span></span>

<span data-ttu-id="56a93-128">Der zweite Befehl zeigt den Inhalt der Console01.psc1-Datei im Editor an.</span><span class="sxs-lookup"><span data-stu-id="56a93-128">The second command displays the contents of the Console01.psc1 file in Notepad.</span></span>

### <span data-ttu-id="56a93-129">Beispiel 5: Bestimmen der zu Aktualisier-Konsolen Datei</span><span class="sxs-lookup"><span data-stu-id="56a93-129">Example 5: Determine the console file to update</span></span>

```
PS C:\> powershell.exe -PSConsoleFile Console01.psc1
PS C:\> Add-PSSnapin MySnapin
PS C:\> Export-Console NewConsole.psc1
PS C:\> $ConsoleFileName
PS C:\> Add-PSSnapin SnapIn03
PS C:\> Export-Console
```

<span data-ttu-id="56a93-130">In diesem Beispiel wird gezeigt, wie die automatische $ConsoleFileName Variable verwendet wird, um die Konsolen Datei zu bestimmen, die aktualisiert wird, wenn Sie **Export-Console** ohne einen *path* -Parameterwert verwenden.</span><span class="sxs-lookup"><span data-stu-id="56a93-130">This example shows how to use the $ConsoleFileName automatic variable to determine the console file that will be updated if you use **Export-Console** without a *Path* parameter value.</span></span>

<span data-ttu-id="56a93-131">Der erste Befehl verwendet den *PsConsoleFile* -Parameter von PowerShell.exe, um Windows PowerShell mit der Datei Console01. psc1 zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="56a93-131">The first command uses the *PSConsoleFile* parameter of PowerShell.exe to open Windows PowerShell with the Console01.psc1 file.</span></span>

<span data-ttu-id="56a93-132">Der zweite Befehl verwendet das **Add-PSSnapin** -Cmdlet, um das Windows PowerShell-Snap-in "mysnapin" zur aktuellen Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="56a93-132">The second command uses the **Add-PSSnapin** cmdlet to add the MySnapin Windows PowerShell snap-in to the current session.</span></span>

<span data-ttu-id="56a93-133">Der dritte Befehl verwendet das **Export-Console-** Cmdlet, um die Namen aller Windows PowerShell-Snap-Ins in der Sitzung in die newconsole. psc1-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="56a93-133">The third command uses the **Export-Console** cmdlet to export the names of all the Windows PowerShell snap-ins in the session to the NewConsole.psc1 file.</span></span>

<span data-ttu-id="56a93-134">Der vierte Befehl zeigt die $ConsoleFileName Variable an.</span><span class="sxs-lookup"><span data-stu-id="56a93-134">The fourth command displays the $ConsoleFileName variable.</span></span>
<span data-ttu-id="56a93-135">Sie enthält die zuletzt verwendete Konsolen Datei.</span><span class="sxs-lookup"><span data-stu-id="56a93-135">It contains the most recently used console file.</span></span>
<span data-ttu-id="56a93-136">Die Beispielausgabe zeigt, dass NewConsole.ps1 die zuletzt verwendete Datei ist.</span><span class="sxs-lookup"><span data-stu-id="56a93-136">The sample output shows that NewConsole.ps1 is the most recently used file.</span></span>

<span data-ttu-id="56a93-137">Der fünfte Befehl fügt „SnapIn03“ zur aktuellen Konsole hinzu.</span><span class="sxs-lookup"><span data-stu-id="56a93-137">The fifth command adds SnapIn03 to the current console.</span></span>

<span data-ttu-id="56a93-138">Der sechste Befehl verwendet das **Export-Console-** Cmdlet ohne *path* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="56a93-138">The sixth command uses the **Export-Console** cmdlet without a *Path* parameter.</span></span>
<span data-ttu-id="56a93-139">Mit diesem Befehl werden die Namen aller Windows PowerShell-Snap-Ins in der aktuellen Sitzung in die zuletzt verwendete Datei (NewConsole.psc1) exportiert.</span><span class="sxs-lookup"><span data-stu-id="56a93-139">This command exports the names of all the Windows PowerShell snap-ins in the current session to the most recently used file, NewConsole.psc1.</span></span>

## <span data-ttu-id="56a93-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="56a93-140">PARAMETERS</span></span>

### <span data-ttu-id="56a93-141">-Force</span><span class="sxs-lookup"><span data-stu-id="56a93-141">-Force</span></span>
<span data-ttu-id="56a93-142">Gibt an, dass dieses Cmdlet die Daten in einer Konsolen Datei ohne Warnung überschreibt, auch wenn die Datei das schreibgeschützte Attribut aufweist.</span><span class="sxs-lookup"><span data-stu-id="56a93-142">Indicates that this cmdlet overwrites the data in a console file without warning, even if the file has the read-only attribute.</span></span>
<span data-ttu-id="56a93-143">Das Read-only-Attribut wird geändert und wird nicht zurückgesetzt, wenn der Befehl abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="56a93-143">The read-only attribute is changed and is not reset when the command finishes.</span></span>

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

### <span data-ttu-id="56a93-144">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="56a93-144">-NoClobber</span></span>
<span data-ttu-id="56a93-145">Gibt an, dass dieses Cmdlet eine vorhandene Konsolen Datei nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="56a93-145">Indicates that this cmdlet does not overwrite  an existing console file.</span></span>
<span data-ttu-id="56a93-146">Wenn eine Datei im angegebenen Pfad vorkommt, überschreibt **Export-Console** die Datei standardmäßig ohne Warnung.</span><span class="sxs-lookup"><span data-stu-id="56a93-146">By default, if a file occurs in the specified path, **Export-Console** overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="56a93-147">-Path</span><span class="sxs-lookup"><span data-stu-id="56a93-147">-Path</span></span>
<span data-ttu-id="56a93-148">Gibt einen Pfad und Dateinamen für die Konsolendatei (\*.psc1) an.</span><span class="sxs-lookup"><span data-stu-id="56a93-148">Specifies a path and file name for the console file (\*.psc1).</span></span>
<span data-ttu-id="56a93-149">Geben Sie einen optionalen Pfad und einen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="56a93-149">Enter an optional path and name.</span></span>
<span data-ttu-id="56a93-150">Platzhalterzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="56a93-150">Wildcard characters are not permitted.</span></span>

<span data-ttu-id="56a93-151">Wenn Sie nur einen Dateinamen angeben, erstellt **Export-Console** im aktuellen Verzeichnis eine Datei mit diesem Namen und der Dateinamenerweiterung ". psc1".</span><span class="sxs-lookup"><span data-stu-id="56a93-151">If you specify only a file name, **Export-Console** creates a file that has that name and the .psc1 file name extension in the current directory.</span></span>

<span data-ttu-id="56a93-152">Dieser Parameter ist erforderlich, es sei denn, Sie haben Windows PowerShell mit dem *PsConsoleFile* -Parameter geöffnet oder während der aktuellen Sitzung eine Konsolen Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="56a93-152">This parameter is required unless you have opened Windows PowerShell with the *PSConsoleFile* parameter or exported a console file during the current session.</span></span>
<span data-ttu-id="56a93-153">Dies ist auch erforderlich, wenn Sie den *noClobber* -Parameter verwenden, um zu verhindern, dass die aktuelle Konsolen Datei überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="56a93-153">It is also required when you use the *NoClobber* parameter to prevent the current console file from being overwritten.</span></span>

<span data-ttu-id="56a93-154">Wenn Sie diesen Parameter weglassen, überschreibt **Export-Console** die Konsolen Datei, die in dieser Sitzung zuletzt verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="56a93-154">If you omit this parameter, **Export-Console** overwrites the console file that was used most recently in this session.</span></span>
<span data-ttu-id="56a93-155">Der Pfad der zuletzt verwendeten Konsolen Datei wird im Wert der automatischen $ConsoleFileName Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="56a93-155">The path of the most recently used console file is stored in the value of the $ConsoleFileName automatic variable.</span></span>
<span data-ttu-id="56a93-156">Weitere Informationen finden Sie unter %%amp;quot;about_Automatic_Variables%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="56a93-156">For more information, see about_Automatic_Variables.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="56a93-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="56a93-157">-Confirm</span></span>
<span data-ttu-id="56a93-158">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="56a93-158">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="56a93-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="56a93-159">-WhatIf</span></span>
<span data-ttu-id="56a93-160">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="56a93-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="56a93-161">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="56a93-161">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="56a93-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="56a93-162">CommonParameters</span></span>
<span data-ttu-id="56a93-163">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="56a93-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="56a93-164">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="56a93-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="56a93-165">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="56a93-165">INPUTS</span></span>

### <span data-ttu-id="56a93-166">System.String</span><span class="sxs-lookup"><span data-stu-id="56a93-166">System.String</span></span>
<span data-ttu-id="56a93-167">Sie können eine Pfad Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="56a93-167">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="56a93-168">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="56a93-168">OUTPUTS</span></span>

### <span data-ttu-id="56a93-169">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="56a93-169">System.IO.FileInfo</span></span>
<span data-ttu-id="56a93-170">Mit diesem Cmdlet wird eine Datei erstellt, die die exportierten Aliase enthält.</span><span class="sxs-lookup"><span data-stu-id="56a93-170">This cmdlet creates a file that contains the exported aliases.</span></span>

## <span data-ttu-id="56a93-171">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="56a93-171">NOTES</span></span>

* <span data-ttu-id="56a93-172">Wenn eine Konsolendatei (.psc1) zum Starten der Sitzung verwendet wird, wird der Name der Konsolendatei automatisch in der automatischen $ConsoleFileName-Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="56a93-172">When a console file (.psc1) is used to start the session, the name of the console file is automatically stored in the $ConsoleFileName automatic variable.</span></span> <span data-ttu-id="56a93-173">Der Wert $ConsoleFileName wird aktualisiert, wenn Sie den *path* -Parameter von **Export-Console** verwenden, um eine neue Konsolen Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="56a93-173">The value of $ConsoleFileName is updated when you use the *Path* parameter of **Export-Console** to specify a new console file.</span></span> <span data-ttu-id="56a93-174">Wenn keine Konsolen Datei verwendet wird, hat $ConsoleFileName keinen Wert ($null).</span><span class="sxs-lookup"><span data-stu-id="56a93-174">When no console file is used, $ConsoleFileName has no value ($Null).</span></span>

  <span data-ttu-id="56a93-175">Um eine Windows PowerShell-Konsolendatei in einer neuen Sitzung zu verwenden, starten Sie Windows PowerShell mit der folgenden Syntax:</span><span class="sxs-lookup"><span data-stu-id="56a93-175">To use a Windows PowerShell console file in a new session, use the following syntax to start Windows PowerShell:</span></span>

  `powershell.exe -PsConsoleFile \<ConsoleFile\>.psc1`

  <span data-ttu-id="56a93-176">Sie können Windows PowerShell-Snap-Ins auch für zukünftige Sitzungen speichern, indem Sie einen Add-PSSnapin-Befehl zu Ihrem Windows PowerShell-Profil hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="56a93-176">You can also save Windows PowerShell snap-ins for future sessions by adding an Add-PSSnapin command to your Windows PowerShell profile.</span></span>
<span data-ttu-id="56a93-177">Weitere Informationen finden Sie unter „about_Profiles“.</span><span class="sxs-lookup"><span data-stu-id="56a93-177">For more information, see about_Profiles.</span></span>


## <span data-ttu-id="56a93-178">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="56a93-178">RELATED LINKS</span></span>

[<span data-ttu-id="56a93-179">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="56a93-179">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="56a93-180">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="56a93-180">Get-PSSnapin</span></span>](Get-PSSnapin.md)

[<span data-ttu-id="56a93-181">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="56a93-181">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
