---
description: Hier wird beschrieben, wie Skripts in PowerShell ausgeführt und geschrieben werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scripts
ms.openlocfilehash: c877627f8caeab8309326826caa4ec13d65d5d9d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220844"
---
# <a name="about-scripts"></a><span data-ttu-id="f720b-104">Informationen zu Skripts</span><span class="sxs-lookup"><span data-stu-id="f720b-104">About Scripts</span></span>

## <a name="short-description"></a><span data-ttu-id="f720b-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f720b-105">Short description</span></span>
<span data-ttu-id="f720b-106">Hier wird beschrieben, wie Skripts in PowerShell ausgeführt und geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f720b-106">Describes how to run and write scripts in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="f720b-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f720b-107">Long description</span></span>

<span data-ttu-id="f720b-108">Bei einem Skript handelt es sich um eine einfache Textdatei, die mindestens einen PowerShell-Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="f720b-108">A script is a plain text file that contains one or more PowerShell commands.</span></span>
<span data-ttu-id="f720b-109">PowerShell-Skripts haben eine `.ps1` Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="f720b-109">PowerShell scripts have a `.ps1` file extension.</span></span>

<span data-ttu-id="f720b-110">Das Ausführen eines Skripts ist sehr ähnlich wie das Ausführen eines Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f720b-110">Running a script is a lot like running a cmdlet.</span></span> <span data-ttu-id="f720b-111">Geben Sie den Pfad und den Dateinamen des Skripts ein, und verwenden Sie Parameter, um Daten zu senden und Optionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f720b-111">You type the path and file name of the script and use parameters to submit data and set options.</span></span> <span data-ttu-id="f720b-112">Sie können Skripts auf dem Computer oder in einer Remote Sitzung auf einem anderen Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="f720b-112">You can run scripts on your computer or in a remote session on a different computer.</span></span>

<span data-ttu-id="f720b-113">Das Schreiben eines Skripts speichert einen Befehl für die spätere Verwendung und erleichtert die Freigabe für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f720b-113">Writing a script saves a command for later use and makes it easy to share with others.</span></span> <span data-ttu-id="f720b-114">Am wichtigsten ist, dass Sie die Befehle ausführen können, indem Sie einfach den Skript Pfad und den Dateinamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="f720b-114">Most importantly, it lets you run the commands simply by typing the script path and the filename.</span></span> <span data-ttu-id="f720b-115">Skripts können so einfach wie ein einzelner Befehl in einer Datei oder so umfangreich wie ein komplexes Programm sein.</span><span class="sxs-lookup"><span data-stu-id="f720b-115">Scripts can be as simple as a single command in a file or as extensive as a complex program.</span></span>

<span data-ttu-id="f720b-116">Skripts verfügen über zusätzliche Funktionen, wie z. b. den `#Requires` speziellen Kommentar, die Verwendung von Parametern, die Unterstützung von Daten Abschnitten und die digitale Signatur für die Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="f720b-116">Scripts have additional features, such as the `#Requires` special comment, the use of parameters, support for data sections, and digital signing for security.</span></span>
<span data-ttu-id="f720b-117">Sie können auch Hilfe Themen für Skripts und für alle Funktionen im Skript schreiben.</span><span class="sxs-lookup"><span data-stu-id="f720b-117">You can also write Help topics for scripts and for any functions in the script.</span></span>

## <a name="how-to-run-a-script"></a><span data-ttu-id="f720b-118">Ausführen eines Skripts</span><span class="sxs-lookup"><span data-stu-id="f720b-118">How to run a script</span></span>

<span data-ttu-id="f720b-119">Bevor Sie ein Skript unter Windows ausführen können, müssen Sie die Standard-PowerShell-Ausführungs Richtlinie ändern.</span><span class="sxs-lookup"><span data-stu-id="f720b-119">Before you can run a script on Windows, you need to change the default PowerShell execution policy.</span></span> <span data-ttu-id="f720b-120">Die Ausführungs Richtlinie gilt nicht für PowerShell, die auf nicht-Windows-Plattformen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f720b-120">Execution policy does not apply to PowerShell running on non-Windows platforms.</span></span>

<span data-ttu-id="f720b-121">Die Standard Ausführungs Richtlinie, `Restricted` , verhindert, dass alle Skripts ausgeführt werden, einschließlich der Skripts, die Sie auf dem lokalen Computer schreiben.</span><span class="sxs-lookup"><span data-stu-id="f720b-121">The default execution policy, `Restricted`, prevents all scripts from running, including scripts that you write on the local computer.</span></span> <span data-ttu-id="f720b-122">Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="f720b-122">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="f720b-123">Die Ausführungs Richtlinie wird in der Registrierung gespeichert, sodass Sie Sie nur einmal auf jedem Computer ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="f720b-123">The execution policy is saved in the registry, so you need to change it only once on each computer.</span></span>

<span data-ttu-id="f720b-124">Verwenden Sie das folgende Verfahren, um die Ausführungs Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f720b-124">To change the execution policy, use the following procedure.</span></span>

<span data-ttu-id="f720b-125">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f720b-125">At the command prompt, type:</span></span>

```powershell
Set-ExecutionPolicy AllSigned
```

<span data-ttu-id="f720b-126">oder</span><span class="sxs-lookup"><span data-stu-id="f720b-126">or</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

<span data-ttu-id="f720b-127">Die Änderung wird sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="f720b-127">The change is effective immediately.</span></span>

<span data-ttu-id="f720b-128">Zum Ausführen eines Skripts geben Sie den vollständigen Namen und den vollständigen Pfad zur Skriptdatei ein.</span><span class="sxs-lookup"><span data-stu-id="f720b-128">To run a script, type the full name and the full path to the script file.</span></span>

<span data-ttu-id="f720b-129">Wenn Sie z. b. das Get-ServiceLog.ps1 Skript im Verzeichnis c:\Scripts ausführen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f720b-129">For example, to run the Get-ServiceLog.ps1 script in the C:\Scripts directory, type:</span></span>

```powershell
C:\Scripts\Get-ServiceLog.ps1
```

<span data-ttu-id="f720b-130">Um ein Skript im aktuellen Verzeichnis auszuführen, geben Sie den Pfad zum aktuellen Verzeichnis ein, oder verwenden Sie einen Punkt, um das aktuelle Verzeichnis darzustellen, gefolgt von einem Pfad umgekehrten Schrägstrich ( `.\` ).</span><span class="sxs-lookup"><span data-stu-id="f720b-130">To run a script in the current directory, type the path to the current directory, or use a dot to represent the current directory, followed by a path backslash (`.\`).</span></span>

<span data-ttu-id="f720b-131">Wenn Sie z. b. das ServicesLog.ps1 Skript im lokalen Verzeichnis ausführen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f720b-131">For example, to run the ServicesLog.ps1 script in the local directory, type:</span></span>

```powershell
.\Get-ServiceLog.ps1
```

<span data-ttu-id="f720b-132">Wenn das Skript über Parameter verfügt, geben Sie die Parameter und Parameterwerte nach dem Skript Dateiname ein.</span><span class="sxs-lookup"><span data-stu-id="f720b-132">If the script has parameters, type the parameters and parameter values after the script filename.</span></span>

<span data-ttu-id="f720b-133">Der folgende Befehl verwendet z. b. den ServiceName-Parameter des Get-ServiceLog Skripts, um ein Protokoll der WinRM-Dienst Aktivität anzufordern.</span><span class="sxs-lookup"><span data-stu-id="f720b-133">For example, the following command uses the ServiceName parameter of the Get-ServiceLog script to request a log of WinRM service activity.</span></span>

```powershell
.\Get-ServiceLog.ps1 -ServiceName WinRM
```

<span data-ttu-id="f720b-134">Als Sicherheits Feature führt PowerShell keine Skripts aus, wenn Sie im Datei-Explorer auf das Skript Symbol doppelklicken oder wenn Sie den Skriptnamen ohne vollständigen Pfad eingeben, auch wenn sich das Skript im aktuellen Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="f720b-134">As a security feature, PowerShell does not run scripts when you double-click the script icon in File Explorer or when you type the script name without a full path, even when the script is in the current directory.</span></span> <span data-ttu-id="f720b-135">Weitere Informationen zum Ausführen von Befehlen und Skripts in PowerShell finden Sie unter [about_Command_Precedence](about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="f720b-135">For more information about running commands and scripts in PowerShell, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

### <a name="run-with-powershell"></a><span data-ttu-id="f720b-136">Ausführen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f720b-136">Run with PowerShell</span></span>

<span data-ttu-id="f720b-137">Ab PowerShell 3,0 können Sie Skripts aus dem Datei-Explorer ausführen.</span><span class="sxs-lookup"><span data-stu-id="f720b-137">Beginning in PowerShell 3.0, you can run scripts from File Explorer.</span></span>

<span data-ttu-id="f720b-138">So verwenden Sie die Funktion "mit PowerShell ausführen":</span><span class="sxs-lookup"><span data-stu-id="f720b-138">To use the "Run with PowerShell" feature:</span></span>

<span data-ttu-id="f720b-139">Führen Sie den Datei-Explorer aus, klicken Sie mit der rechten Maustaste auf den Dateinamen des Skripts, und wählen Sie dann die Option</span><span class="sxs-lookup"><span data-stu-id="f720b-139">Run File Explorer, right-click the script filename and then select "Run with PowerShell".</span></span>

<span data-ttu-id="f720b-140">Die Funktion "mit PowerShell ausführen" dient zum Ausführen von Skripts, die nicht über erforderliche Parameter verfügen und keine Ausgabe an die Eingabeaufforderung zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f720b-140">The "Run with PowerShell" feature is designed to run scripts that do not have required parameters and do not return output to the command prompt.</span></span>

<span data-ttu-id="f720b-141">Weitere Informationen finden Sie unter [Informationen zum Ausführen mit PowerShell](about_Run_With_PowerShell.md).</span><span class="sxs-lookup"><span data-stu-id="f720b-141">For more information, see [about_Run_With_PowerShell](about_Run_With_PowerShell.md).</span></span>

### <a name="running-scripts-on-other-computers"></a><span data-ttu-id="f720b-142">Ausführen von Skripts auf anderen Computern</span><span class="sxs-lookup"><span data-stu-id="f720b-142">Running scripts on other computers</span></span>

<span data-ttu-id="f720b-143">Verwenden Sie zum Ausführen eines Skripts auf einem oder mehreren Remote Computern den **FilePath** -Parameter des `Invoke-Command` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f720b-143">To run a script on one or more remote computers, use the **FilePath** parameter of the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="f720b-144">Geben Sie den Pfad und den Dateinamen des Skripts als Wert für den **FilePath** -Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="f720b-144">Enter the path and filename of the script as the value of the **FilePath** parameter.</span></span> <span data-ttu-id="f720b-145">Das Skript muss sich auf dem lokalen Computer oder in einem Verzeichnis befinden, auf das der lokale Computer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="f720b-145">The script must reside on the local computer or in a directory that the local computer can access.</span></span>

<span data-ttu-id="f720b-146">Der folgende Befehl führt das `Get-ServiceLog.ps1` Skript auf den Remote Computern namens SERVER01 und Server02 aus.</span><span class="sxs-lookup"><span data-stu-id="f720b-146">The following command runs the `Get-ServiceLog.ps1` script on the remote computers named Server01 and Server02.</span></span>

```powershell
Invoke-Command -ComputerName Server01,Server02 -FilePath `
  C:\Scripts\Get-ServiceLog.ps1
```

## <a name="get-help-for-scripts"></a><span data-ttu-id="f720b-147">Hilfe zu Skripts</span><span class="sxs-lookup"><span data-stu-id="f720b-147">Get help for scripts</span></span>

<span data-ttu-id="f720b-148">Das Get-Help-Cmdlet ruft die Hilfe Themen für Skripts sowie für Cmdlets und andere Befehls Typen ab.</span><span class="sxs-lookup"><span data-stu-id="f720b-148">The Get-Help cmdlet gets the help topics for scripts as well as for cmdlets and other types of commands.</span></span> <span data-ttu-id="f720b-149">Um das Hilfethema für ein Skript zu erhalten, geben Sie `Get-Help` gefolgt vom Pfad und Dateinamen des Skripts ein.</span><span class="sxs-lookup"><span data-stu-id="f720b-149">To get the help topic for a script, type `Get-Help` followed by the path and filename of the script.</span></span> <span data-ttu-id="f720b-150">Wenn sich der Skript Pfad in der `Path` Umgebungsvariablen befindet, können Sie den Pfad weglassen.</span><span class="sxs-lookup"><span data-stu-id="f720b-150">If the script path is in your `Path` environment variable, you can omit the path.</span></span>

<span data-ttu-id="f720b-151">Wenn Sie z. b. Hilfe zum ServicesLog.ps1 Skript benötigen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f720b-151">For example, to get help for the ServicesLog.ps1 script, type:</span></span>

```powershell
get-help C:\admin\scripts\ServicesLog.ps1
```

## <a name="how-to-write-a-script"></a><span data-ttu-id="f720b-152">Schreiben eines Skripts</span><span class="sxs-lookup"><span data-stu-id="f720b-152">How to write a script</span></span>

<span data-ttu-id="f720b-153">Ein Skript kann beliebige gültige PowerShell-Befehle enthalten, einschließlich einzelner Befehle, Befehle, die die Pipeline, Funktionen und Steuerungsstrukturen verwenden, z. b. if-Anweisungen und for-Schleifen.</span><span class="sxs-lookup"><span data-stu-id="f720b-153">A script can contain any valid PowerShell commands, including single commands, commands that use the pipeline, functions, and control structures such as If statements and For loops.</span></span>

<span data-ttu-id="f720b-154">Öffnen Sie zum Schreiben eines Skripts eine neue Datei in einem Text-Editor, geben Sie die Befehle ein, und speichern Sie Sie in einer Datei mit einem gültigen Dateinamen mit der `.ps1` Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="f720b-154">To write a script, open a new file in a text editor, type the commands, and save them in a file with a valid filename with the `.ps1` file extension.</span></span>

<span data-ttu-id="f720b-155">Das folgende Beispiel ist ein einfaches Skript, mit dem die Dienste abgerufen werden, die auf dem aktuellen System ausgeführt werden, und in einer Protokolldatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f720b-155">The following example is a simple script that gets the services that are running on the current system and saves them to a log file.</span></span> <span data-ttu-id="f720b-156">Der Protokoll Dateiname wird aus dem aktuellen Datum erstellt.</span><span class="sxs-lookup"><span data-stu-id="f720b-156">The log filename is created from the current date.</span></span>

```powershell
$date = (get-date).dayofyear
get-service | out-file "$date.log"
```

<span data-ttu-id="f720b-157">Öffnen Sie zum Erstellen dieses Skripts einen Text-Editor oder einen Skript-Editor, geben Sie diese Befehle ein, und speichern Sie Sie in einer Datei mit dem Namen `ServiceLog.ps1` .</span><span class="sxs-lookup"><span data-stu-id="f720b-157">To create this script, open a text editor or a script editor, type these commands, and then save them in a file named `ServiceLog.ps1`.</span></span>

### <a name="parameters-in-scripts"></a><span data-ttu-id="f720b-158">Parameter in Skripts</span><span class="sxs-lookup"><span data-stu-id="f720b-158">Parameters in scripts</span></span>

<span data-ttu-id="f720b-159">Verwenden Sie zum Definieren von Parametern in einem Skript eine Param-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f720b-159">To define parameters in a script, use a Param statement.</span></span> <span data-ttu-id="f720b-160">Die `Param` Anweisung muss die erste Anweisung in einem Skript sein, mit Ausnahme von Kommentaren und `#Require` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="f720b-160">The `Param` statement must be the first statement in a script, except for comments and any `#Require` statements.</span></span>

<span data-ttu-id="f720b-161">Skript Parameter funktionieren wie Funktionsparameter.</span><span class="sxs-lookup"><span data-stu-id="f720b-161">Script parameters work like function parameters.</span></span> <span data-ttu-id="f720b-162">Die Parameterwerte sind für alle Befehle im Skript verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f720b-162">The parameter values are available to all of the commands in the script.</span></span> <span data-ttu-id="f720b-163">Alle Funktionen von Funktionsparametern, einschließlich des Parameter Attributs und der benannten Argumente, sind ebenfalls in Skripts gültig.</span><span class="sxs-lookup"><span data-stu-id="f720b-163">All of the features of function parameters, including the Parameter attribute and its named arguments, are also valid in scripts.</span></span>

<span data-ttu-id="f720b-164">Beim Ausführen des Skripts geben Skript Benutzer die Parameter nach dem Skriptnamen ein.</span><span class="sxs-lookup"><span data-stu-id="f720b-164">When running the script, script users type the parameters after the script name.</span></span>

<span data-ttu-id="f720b-165">Das folgende Beispiel zeigt ein `Test-Remote.ps1` Skript, das über einen **Computername** -Parameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="f720b-165">The following example shows a `Test-Remote.ps1` script that has a **ComputerName** parameter.</span></span> <span data-ttu-id="f720b-166">Beide Skriptfunktionen können auf den Wert des **Computername** -Parameters zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f720b-166">Both of the script functions can access the **ComputerName** parameter value.</span></span>

```powershell
param ($ComputerName = $(throw "ComputerName parameter is required."))

function CanPing {
   $error.clear()
   $tmp = test-connection $computername -erroraction SilentlyContinue

   if (!$?)
       {write-host "Ping failed: $ComputerName."; return $false}
   else
       {write-host "Ping succeeded: $ComputerName"; return $true}
}

function CanRemote {
    $s = new-pssession $computername -erroraction SilentlyContinue

    if ($s -is [System.Management.Automation.Runspaces.PSSession])
        {write-host "Remote test succeeded: $ComputerName."}
    else
        {write-host "Remote test failed: $ComputerName."}
}

if (CanPing $computername) {CanRemote $computername}
```

<span data-ttu-id="f720b-167">Um dieses Skript auszuführen, geben Sie den Namen des Parameters nach dem Skriptnamen ein.</span><span class="sxs-lookup"><span data-stu-id="f720b-167">To run this script, type the parameter name after the script name.</span></span> <span data-ttu-id="f720b-168">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f720b-168">For example:</span></span>

```powershell
C:\PS> .\test-remote.ps1 -computername Server01

Ping succeeded: Server01
Remote test failed: Server01
```

<span data-ttu-id="f720b-169">Weitere Informationen zur Param-Anweisung und zu den Funktionsparametern finden Sie unter [about_Functions](about_Functions.md) und [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f720b-169">For more information about the Param statement and the function parameters, see [about_Functions](about_Functions.md) and [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="writing-help-for-scripts"></a><span data-ttu-id="f720b-170">Schreiben von Hilfe für Skripts</span><span class="sxs-lookup"><span data-stu-id="f720b-170">Writing help for scripts</span></span>

<span data-ttu-id="f720b-171">Sie können ein Hilfethema für ein Skript schreiben, indem Sie eine der beiden folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="f720b-171">You can write a help topic for a script by using either of the two following methods:</span></span>

- <span data-ttu-id="f720b-172">Comment-Based Hilfe zu Skripts</span><span class="sxs-lookup"><span data-stu-id="f720b-172">Comment-Based Help for Scripts</span></span>

  <span data-ttu-id="f720b-173">Erstellen Sie ein Hilfethema mithilfe von speziellen Schlüsselwörtern in den Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="f720b-173">Create a Help topic by using special keywords in the comments.</span></span> <span data-ttu-id="f720b-174">Um die Kommentar basierte Hilfe für ein Skript zu erstellen, müssen die Kommentare am Anfang oder Ende der Skriptdatei abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f720b-174">To create comment-based Help for a script, the comments must be placed at the beginning or end of the script file.</span></span> <span data-ttu-id="f720b-175">Weitere Informationen zur Kommentar basierten Hilfe finden Sie unter [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="f720b-175">For more information about comment-based Help, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span>

- <span data-ttu-id="f720b-176">XML-Based Hilfe zu Skripts</span><span class="sxs-lookup"><span data-stu-id="f720b-176">XML-Based Help  for Scripts</span></span>

  <span data-ttu-id="f720b-177">Erstellen Sie ein XML-basiertes Hilfethema, z. b. den Typ, der in der Regel für Cmdlets erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f720b-177">Create an XML-based Help topic, such as the type that is typically created for cmdlets.</span></span> <span data-ttu-id="f720b-178">Die XML-basierte Hilfe ist erforderlich, wenn Sie Hilfe Themen in mehrere Sprachen übersetzen.</span><span class="sxs-lookup"><span data-stu-id="f720b-178">XML-based Help is required if you are translating Help topics into multiple languages.</span></span>

<span data-ttu-id="f720b-179">Um das Skript dem XML-basierten Hilfethema zuzuordnen, verwenden Sie die. Externalhelp-Kommentar Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="f720b-179">To associate the script with the XML-based Help topic, use the .ExternalHelp Help comment keyword.</span></span> <span data-ttu-id="f720b-180">Weitere Informationen zum externalhelp-Schlüsselwort finden Sie unter [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="f720b-180">For more information about the ExternalHelp keyword, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span> <span data-ttu-id="f720b-181">Weitere Informationen zur XML-basierten Hilfe finden Sie unter [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="f720b-181">For more information about XML-based help, see [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

### <a name="returning-an-exit-value"></a><span data-ttu-id="f720b-182">Zurückgeben eines Exit-Werts</span><span class="sxs-lookup"><span data-stu-id="f720b-182">Returning an exit value</span></span>

<span data-ttu-id="f720b-183">Standardmäßig geben Skripts beim Ende des Skripts keinen Beendigungs Status zurück.</span><span class="sxs-lookup"><span data-stu-id="f720b-183">By default, scripts do not return an exit status when the script ends.</span></span> <span data-ttu-id="f720b-184">Sie müssen die- `exit` Anweisung verwenden, um einen Exitcode von einem Skript zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="f720b-184">You must use the `exit` statement to return an exit code from a script.</span></span> <span data-ttu-id="f720b-185">Standardmäßig gibt die- `exit` Anweisung zurück `0` .</span><span class="sxs-lookup"><span data-stu-id="f720b-185">By default, the `exit` statement returns `0`.</span></span> <span data-ttu-id="f720b-186">Sie können einen numerischen Wert angeben, um einen anderen Beendigungs Status zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="f720b-186">You can provide a numeric value to return a different exit status.</span></span> <span data-ttu-id="f720b-187">Ein Exitcode ungleich NULL signalisiert in der Regel einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="f720b-187">A nonzero exit code typically signals a failure.</span></span>

<span data-ttu-id="f720b-188">Unter Windows ist eine beliebige Zahl zwischen `[int]::MinValue` und `[int]::MaxValue` zulässig.</span><span class="sxs-lookup"><span data-stu-id="f720b-188">On Windows, any number between `[int]::MinValue` and `[int]::MaxValue` is allowed.</span></span>

<span data-ttu-id="f720b-189">Unter Unix sind nur positive Zahlen zwischen `[byte]::MinValue` (0) und `[byte]::MaxValue` (255) zulässig.</span><span class="sxs-lookup"><span data-stu-id="f720b-189">On Unix, only positive numbers between `[byte]::MinValue` (0) and `[byte]::MaxValue` (255) are allowed.</span></span> <span data-ttu-id="f720b-190">Eine negative Zahl im Bereich von `-1` bis `-255` wird durch Hinzufügen von automatisch in eine positive Zahl übersetzt.</span><span class="sxs-lookup"><span data-stu-id="f720b-190">A negative number in the range of `-1` through `-255` is automatically translated into a positive number by adding</span></span>
256. <span data-ttu-id="f720b-191">Beispielsweise `-2` wird in umgewandelt `254` .</span><span class="sxs-lookup"><span data-stu-id="f720b-191">For example, `-2` is transformed to `254`.</span></span>

<span data-ttu-id="f720b-192">In PowerShell legt die- `exit` Anweisung den Wert der- `$LASTEXITCODE` Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="f720b-192">In PowerShell, the `exit` statement sets the value of the `$LASTEXITCODE` variable.</span></span> <span data-ttu-id="f720b-193">In der Windows-Befehlsshell (cmd.exe) legt die Exit-Anweisung den Wert der `%ERRORLEVEL%` Umgebungsvariablen fest.</span><span class="sxs-lookup"><span data-stu-id="f720b-193">In the Windows Command Shell (cmd.exe), the exit statement sets the value of the `%ERRORLEVEL%` environment variable.</span></span>

<span data-ttu-id="f720b-194">Jedes Argument, das nicht numerisch oder außerhalb des plattformspezifischen Bereichs ist, wird in den Wert von übersetzt `0` .</span><span class="sxs-lookup"><span data-stu-id="f720b-194">Any argument that is non-numeric or outside the platform-specific range is translated to the value of `0`.</span></span>

## <a name="script-scope-and-dot-sourcing"></a><span data-ttu-id="f720b-195">Skript Bereich und dotsourcing</span><span class="sxs-lookup"><span data-stu-id="f720b-195">Script scope and dot sourcing</span></span>

<span data-ttu-id="f720b-196">Jedes Skript wird in einem eigenen Bereich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f720b-196">Each script runs in its own scope.</span></span> <span data-ttu-id="f720b-197">Die im Skript erstellten Funktionen, Variablen, Aliase und Laufwerke sind nur im Skript Bereich vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f720b-197">The functions, variables, aliases, and drives that are created in the script exist only in the script scope.</span></span> <span data-ttu-id="f720b-198">Sie können nicht auf diese Elemente oder deren Werte in dem Bereich zugreifen, in dem das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f720b-198">You cannot access these items or their values in the scope in which the script runs.</span></span>

<span data-ttu-id="f720b-199">Wenn Sie ein Skript in einem anderen Bereich ausführen möchten, können Sie einen Bereich angeben, z. b. Global oder local, oder Sie können ein Punkt für das Skript erstellen.</span><span class="sxs-lookup"><span data-stu-id="f720b-199">To run a script in a different scope, you can specify a scope, such as Global or Local, or you can dot source the script.</span></span>

<span data-ttu-id="f720b-200">Mit dem Feature für die Punkt Ermittlung können Sie ein Skript im aktuellen Bereich statt im Skript Bereich ausführen.</span><span class="sxs-lookup"><span data-stu-id="f720b-200">The dot sourcing feature lets you run a script in the current scope instead of in the script scope.</span></span> <span data-ttu-id="f720b-201">Wenn Sie ein Skript ausführen, das Punkt basiert ist, werden die Befehle im Skript so ausgeführt, als würden Sie es an der Eingabeaufforderung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f720b-201">When you run a script that is dot sourced, the commands in the script run as though you had typed them at the command prompt.</span></span> <span data-ttu-id="f720b-202">Die vom Skript erstellten Funktionen, Variablen, Aliase und Laufwerke werden in dem Bereich erstellt, in dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f720b-202">The functions, variables, aliases, and drives that the script creates are created in the scope in which you are working.</span></span> <span data-ttu-id="f720b-203">Nachdem das Skript ausgeführt wurde, können Sie die erstellten Elemente verwenden und auf ihre Werte in Ihrer Sitzung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f720b-203">After the script runs, you can use the created items and access their values in your session.</span></span>

<span data-ttu-id="f720b-204">Um die Quelle eines Skripts zu überschreiben, geben Sie einen Punkt (.) und ein Leerzeichen vor dem Skript Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="f720b-204">To dot source a script, type a dot (.) and a space before the script path.</span></span>

<span data-ttu-id="f720b-205">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f720b-205">For example:</span></span>

```powershell
. C:\scripts\UtilityFunctions.ps1
```

<span data-ttu-id="f720b-206">oder</span><span class="sxs-lookup"><span data-stu-id="f720b-206">or</span></span>

```powershell
. .\UtilityFunctions.ps1
```

<span data-ttu-id="f720b-207">Nachdem das `UtilityFunctions.ps1` Skript ausgeführt wurde, werden die Funktionen und Variablen, die das Skript erstellt, dem aktuellen Gültigkeitsbereich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f720b-207">After the `UtilityFunctions.ps1` script runs, the functions and variables that the script creates are added to the current scope.</span></span>

<span data-ttu-id="f720b-208">Das `UtilityFunctions.ps1` Skript erstellt z `New-Profile` . b. die-Funktion und die- `$ProfileName` Variable.</span><span class="sxs-lookup"><span data-stu-id="f720b-208">For example, the `UtilityFunctions.ps1` script creates the `New-Profile` function and the `$ProfileName` variable.</span></span>

```powershell
#In UtilityFunctions.ps1

function New-Profile
{
  Write-Host "Running New-Profile function"
  $profileName = split-path $profile -leaf

  if (test-path $profile)
    {write-error "Profile $profileName already exists on this computer."}
  else
    {new-item -type file -path $profile -force }
}
```

<span data-ttu-id="f720b-209">Wenn Sie das `UtilityFunctions.ps1` Skript in einem eigenen Skript Bereich ausführen, sind die `New-Profile` -Funktion und die- `$ProfileName` Variable nur vorhanden, während das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f720b-209">If you run the `UtilityFunctions.ps1` script in its own script scope, the `New-Profile` function and the `$ProfileName` variable exist only while the script is running.</span></span> <span data-ttu-id="f720b-210">Wenn das Skript beendet wird, werden die Funktion und die Variable entfernt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f720b-210">When the script exits, the function and variable are removed, as shown in the following example.</span></span>

```powershell
C:\PS> .\UtilityFunctions.ps1

C:\PS> New-Profile
The term 'new-profile' is not recognized as a cmdlet, function, operable
program, or script file. Verify the term and try again.
At line:1 char:12
+ new-profile <<<<
   + CategoryInfo          : ObjectNotFound: (new-profile:String) [],
   + FullyQualifiedErrorId : CommandNotFoundException

C:\PS> $profileName
C:\PS>
```

<span data-ttu-id="f720b-211">Wenn Sie das Skript auf das Skript angleichen und es ausführen, erstellt das Skript die `New-Profile` Funktion und die `$ProfileName` Variable in Ihrer Sitzung in Ihrem Bereich.</span><span class="sxs-lookup"><span data-stu-id="f720b-211">When you dot source the script and run it, the script creates the `New-Profile` function and the `$ProfileName` variable in your session in your scope.</span></span> <span data-ttu-id="f720b-212">Nachdem das Skript ausgeführt wurde, können Sie die- `New-Profile` Funktion in der Sitzung verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f720b-212">After the script runs, you can use the `New-Profile` function in your session, as shown in the following example.</span></span>

```powershell
C:\PS> . .\UtilityFunctions.ps1

C:\PS> New-Profile

    Directory: C:\Users\juneb\Documents\WindowsPowerShell

    Mode    LastWriteTime     Length Name
    ----    -------------     ------ ----
    -a---   1/14/2009 3:08 PM      0 Microsoft.PowerShellISE_profile.ps1

C:\PS> $profileName
Microsoft.PowerShellISE_profile.ps1
```

<span data-ttu-id="f720b-213">Weitere Informationen zum Gültigkeitsbereich finden Sie unter about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="f720b-213">For more information about scope, see about_Scopes.</span></span>

## <a name="scripts-in-modules"></a><span data-ttu-id="f720b-214">Skripts in Modulen</span><span class="sxs-lookup"><span data-stu-id="f720b-214">Scripts in modules</span></span>

<span data-ttu-id="f720b-215">Ein Modul ist ein Satz verwandter PowerShell-Ressourcen, die als Einheit verteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="f720b-215">A module is a set of related PowerShell resources that can be distributed as a unit.</span></span> <span data-ttu-id="f720b-216">Sie können Module verwenden, um Ihre Skripts, Funktionen und andere Ressourcen zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="f720b-216">You can use modules to organize your scripts, functions, and other resources.</span></span> <span data-ttu-id="f720b-217">Sie können auch Module verwenden, um Ihren Code an andere zu verteilen und um Code aus vertrauenswürdigen Quellen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f720b-217">You can also use modules to distribute your code to others, and to get code from trusted sources.</span></span>

<span data-ttu-id="f720b-218">Sie können Skripts in Ihre Module einschließen, oder Sie können ein Skript Modul erstellen, bei dem es sich um ein Modul handelt, das vollständig oder primär von einem Skript und unterstützenden Ressourcen besteht.</span><span class="sxs-lookup"><span data-stu-id="f720b-218">You can include scripts in your modules, or you can create a script module, which is a module that consists entirely or primarily of a script and supporting resources.</span></span> <span data-ttu-id="f720b-219">Ein Skript Modul ist nur ein Skript mit der Dateierweiterung ". psm1".</span><span class="sxs-lookup"><span data-stu-id="f720b-219">A script module is just a script with a .psm1 file extension.</span></span>

<span data-ttu-id="f720b-220">Weitere Informationen zu Modulen finden Sie unter [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="f720b-220">For more information about modules, see [about_Modules](about_Modules.md).</span></span>

## <a name="other-script-features"></a><span data-ttu-id="f720b-221">Weitere Skript Features</span><span class="sxs-lookup"><span data-stu-id="f720b-221">Other script features</span></span>

<span data-ttu-id="f720b-222">PowerShell bietet viele nützliche Funktionen, die Sie in Skripts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f720b-222">PowerShell has many useful features that you can use in scripts.</span></span>

- <span data-ttu-id="f720b-223">`#Requires` -Sie können eine- `#Requires` Anweisung verwenden, um zu verhindern, dass ein Skript ohne angegebene Module, Snap-Ins und eine bestimmte Version von PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f720b-223">`#Requires` - You can use a `#Requires` statement to prevent a script from running without specified modules or snap-ins and a specified version of PowerShell.</span></span> <span data-ttu-id="f720b-224">Weitere Informationen finden Sie unter about_Requires.</span><span class="sxs-lookup"><span data-stu-id="f720b-224">For more information, see about_Requires.</span></span>

- <span data-ttu-id="f720b-225">`$PSCommandPath` -Enthält den vollständigen Pfad und den Namen des Skripts, das gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f720b-225">`$PSCommandPath` - Contains the full path and name of the script that is being run.</span></span> <span data-ttu-id="f720b-226">Dieser Parameter ist in allen Skripts gültig.</span><span class="sxs-lookup"><span data-stu-id="f720b-226">This parameter is valid in all scripts.</span></span> <span data-ttu-id="f720b-227">Diese automatische Variable wird in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f720b-227">This automatic variable is introduced in PowerShell 3.0.</span></span>

- <span data-ttu-id="f720b-228">`$PSScriptRoot` -Enthält das Verzeichnis, in dem ein Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f720b-228">`$PSScriptRoot` - Contains the directory from which a script is being run.</span></span> <span data-ttu-id="f720b-229">In PowerShell 2,0 ist diese Variable nur in Skript Modulen () gültig `.psm1` .</span><span class="sxs-lookup"><span data-stu-id="f720b-229">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
  <span data-ttu-id="f720b-230">Ab PowerShell 3,0 ist Sie in allen Skripts gültig.</span><span class="sxs-lookup"><span data-stu-id="f720b-230">Beginning in PowerShell 3.0, it is valid in all scripts.</span></span>

- <span data-ttu-id="f720b-231">`$MyInvocation` -Die `$MyInvocation` Automatische Variable enthält Informationen zum aktuellen Skript, einschließlich Informationen zum Starten oder "aufrufen".</span><span class="sxs-lookup"><span data-stu-id="f720b-231">`$MyInvocation` - The `$MyInvocation` automatic variable contains information about the current script, including information about how it was started or "invoked."</span></span> <span data-ttu-id="f720b-232">Sie können diese Variable und ihre Eigenschaften verwenden, um während der Ausführung Informationen über das Skript zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f720b-232">You can use this variable and its properties to get information about the script while it is running.</span></span> <span data-ttu-id="f720b-233">Beispielsweise `$MyInvocation` . Die myCommand. Path-Variable enthält den Pfad und den Dateinamen des Skripts.</span><span class="sxs-lookup"><span data-stu-id="f720b-233">For example, the `$MyInvocation`.MyCommand.Path variable contains the path and filename of the script.</span></span> <span data-ttu-id="f720b-234">`$MyInvocation`. Die Zeile enthält den Befehl, der das Skript gestartet hat, einschließlich aller Parameter und Werte.</span><span class="sxs-lookup"><span data-stu-id="f720b-234">`$MyInvocation`.Line contains the command that started the script, including all parameters and values.</span></span>

  <span data-ttu-id="f720b-235">Ab PowerShell 3,0 verfügt über `$MyInvocation` zwei neue Eigenschaften, die Informationen über das Skript bereitstellen, das das aktuelle Skript aufgerufen oder aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="f720b-235">Beginning in PowerShell 3.0, `$MyInvocation` has two new properties that provide information about the script that called or invoked the current script.</span></span> <span data-ttu-id="f720b-236">Die Werte dieser Eigenschaften werden nur aufgefüllt, wenn der aufrufende oder der Aufrufer ein Skript ist.</span><span class="sxs-lookup"><span data-stu-id="f720b-236">The values of these properties are populated only when the invoker or caller is a script.</span></span>

  - <span data-ttu-id="f720b-237">**Pscommandpath** enthält den vollständigen Pfad und den Namen des Skripts, das das aktuelle Skript aufgerufen oder aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="f720b-237">**PSCommandPath** contains the full path and name of the script that called or invoked the current script.</span></span>

  - <span data-ttu-id="f720b-238">**Psscriptroot** enthält das Verzeichnis des Skripts, das das aktuelle Skript aufgerufen oder aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="f720b-238">**PSScriptRoot** contains the directory of the script that called or invoked the current script.</span></span>

  <span data-ttu-id="f720b-239">Im Gegensatz zu den `$PSCommandPath` `$PSScriptRoot` automatischen Variablen und, die Informationen zum aktuellen Skript enthalten, enthalten die Eigenschaften **pscommandpath** und **psscriptroot** der `$MyInvocation` Variablen Informationen über das Skript, das das aktuelle Skript aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="f720b-239">Unlike the `$PSCommandPath` and `$PSScriptRoot` automatic variables, which contain information about the current script, the **PSCommandPath** and **PSScriptRoot** properties of the `$MyInvocation` variable contain information about the script that called the current script.</span></span>

- <span data-ttu-id="f720b-240">Datenabschnitte: Sie können das `Data` Schlüsselwort verwenden, um Daten von der Logik in Skripts zu trennen.</span><span class="sxs-lookup"><span data-stu-id="f720b-240">Data sections - You can use the `Data` keyword to separate data from logic in scripts.</span></span> <span data-ttu-id="f720b-241">Datenabschnitte können auch die Lokalisierung vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f720b-241">Data sections can also make localization easier.</span></span> <span data-ttu-id="f720b-242">Weitere Informationen finden Sie unter [about_Data_Sections](about_Data_Sections.md) und [about_Script_Internationalization](about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="f720b-242">For more information, see [about_Data_Sections](about_Data_Sections.md) and [about_Script_Internationalization](about_Script_Internationalization.md).</span></span>

- <span data-ttu-id="f720b-243">Skript Signatur-Sie können einem Skript eine digitale Signatur hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f720b-243">Script Signing - You can add a digital signature to a script.</span></span> <span data-ttu-id="f720b-244">Abhängig von der Ausführungs Richtlinie können Sie digitale Signaturen verwenden, um die Ausführung von Skripts einzuschränken, die unsichere Befehle enthalten könnten.</span><span class="sxs-lookup"><span data-stu-id="f720b-244">Depending on the execution policy, you can use digital signatures to restrict the running of scripts that could include unsafe commands.</span></span> <span data-ttu-id="f720b-245">Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md) und [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="f720b-245">For more information, see [about_Execution_Policies](about_Execution_Policies.md) and [about_Signing](about_Signing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f720b-246">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="f720b-246">See also</span></span>

[<span data-ttu-id="f720b-247">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="f720b-247">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="f720b-248">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="f720b-248">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="f720b-249">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="f720b-249">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="f720b-250">about_Functions</span><span class="sxs-lookup"><span data-stu-id="f720b-250">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="f720b-251">about_Modules</span><span class="sxs-lookup"><span data-stu-id="f720b-251">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="f720b-252">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="f720b-252">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="f720b-253">about_Requires</span><span class="sxs-lookup"><span data-stu-id="f720b-253">about_Requires</span></span>](about_Requires.md)

[<span data-ttu-id="f720b-254">about_Run_With_PowerShell</span><span class="sxs-lookup"><span data-stu-id="f720b-254">about_Run_With_PowerShell</span></span>](about_Run_With_PowerShell.md)

[<span data-ttu-id="f720b-255">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="f720b-255">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="f720b-256">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="f720b-256">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="f720b-257">about_Signing</span><span class="sxs-lookup"><span data-stu-id="f720b-257">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="f720b-258">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f720b-258">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
