---
description: Hier wird beschrieben, wie Skripts in PowerShell ausgeführt und geschrieben werden.
Locale: en-US
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scripts
ms.openlocfilehash: 2fc81d1d43b8cdddaacb917deaa5d58536a541cb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600315"
---
# <a name="about-scripts"></a><span data-ttu-id="fea0c-103">Informationen zu Skripts</span><span class="sxs-lookup"><span data-stu-id="fea0c-103">About Scripts</span></span>

## <a name="short-description"></a><span data-ttu-id="fea0c-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fea0c-104">Short description</span></span>
<span data-ttu-id="fea0c-105">Hier wird beschrieben, wie Skripts in PowerShell ausgeführt und geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fea0c-105">Describes how to run and write scripts in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="fea0c-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fea0c-106">Long description</span></span>

<span data-ttu-id="fea0c-107">Bei einem Skript handelt es sich um eine einfache Textdatei, die mindestens einen PowerShell-Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="fea0c-107">A script is a plain text file that contains one or more PowerShell commands.</span></span>
<span data-ttu-id="fea0c-108">PowerShell-Skripts haben eine `.ps1` Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="fea0c-108">PowerShell scripts have a `.ps1` file extension.</span></span>

<span data-ttu-id="fea0c-109">Das Ausführen eines Skripts ist sehr ähnlich wie das Ausführen eines Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fea0c-109">Running a script is a lot like running a cmdlet.</span></span> <span data-ttu-id="fea0c-110">Geben Sie den Pfad und den Dateinamen des Skripts ein, und verwenden Sie Parameter, um Daten zu senden und Optionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-110">You type the path and file name of the script and use parameters to submit data and set options.</span></span> <span data-ttu-id="fea0c-111">Sie können Skripts auf dem Computer oder in einer Remote Sitzung auf einem anderen Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-111">You can run scripts on your computer or in a remote session on a different computer.</span></span>

<span data-ttu-id="fea0c-112">Das Schreiben eines Skripts speichert einen Befehl für die spätere Verwendung und erleichtert die Freigabe für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="fea0c-112">Writing a script saves a command for later use and makes it easy to share with others.</span></span> <span data-ttu-id="fea0c-113">Am wichtigsten ist, dass Sie die Befehle ausführen können, indem Sie einfach den Skript Pfad und den Dateinamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="fea0c-113">Most importantly, it lets you run the commands simply by typing the script path and the filename.</span></span> <span data-ttu-id="fea0c-114">Skripts können so einfach wie ein einzelner Befehl in einer Datei oder so umfangreich wie ein komplexes Programm sein.</span><span class="sxs-lookup"><span data-stu-id="fea0c-114">Scripts can be as simple as a single command in a file or as extensive as a complex program.</span></span>

<span data-ttu-id="fea0c-115">Skripts verfügen über zusätzliche Funktionen, wie z. b. den `#Requires` speziellen Kommentar, die Verwendung von Parametern, die Unterstützung von Daten Abschnitten und die digitale Signatur für die Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="fea0c-115">Scripts have additional features, such as the `#Requires` special comment, the use of parameters, support for data sections, and digital signing for security.</span></span>
<span data-ttu-id="fea0c-116">Sie können auch Hilfe Themen für Skripts und für alle Funktionen im Skript schreiben.</span><span class="sxs-lookup"><span data-stu-id="fea0c-116">You can also write Help topics for scripts and for any functions in the script.</span></span>

## <a name="how-to-run-a-script"></a><span data-ttu-id="fea0c-117">Ausführen eines Skripts</span><span class="sxs-lookup"><span data-stu-id="fea0c-117">How to run a script</span></span>

<span data-ttu-id="fea0c-118">Bevor Sie ein Skript unter Windows ausführen können, müssen Sie die Standard-PowerShell-Ausführungs Richtlinie ändern.</span><span class="sxs-lookup"><span data-stu-id="fea0c-118">Before you can run a script on Windows, you need to change the default PowerShell execution policy.</span></span> <span data-ttu-id="fea0c-119">Die Ausführungs Richtlinie gilt nicht für PowerShell, die auf nicht-Windows-Plattformen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fea0c-119">Execution policy does not apply to PowerShell running on non-Windows platforms.</span></span>

<span data-ttu-id="fea0c-120">Die Standard Ausführungs Richtlinie, `Restricted` , verhindert, dass alle Skripts ausgeführt werden, einschließlich der Skripts, die Sie auf dem lokalen Computer schreiben.</span><span class="sxs-lookup"><span data-stu-id="fea0c-120">The default execution policy, `Restricted`, prevents all scripts from running, including scripts that you write on the local computer.</span></span> <span data-ttu-id="fea0c-121">Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="fea0c-121">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="fea0c-122">Die Ausführungs Richtlinie wird in der Registrierung gespeichert, sodass Sie Sie nur einmal auf jedem Computer ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-122">The execution policy is saved in the registry, so you need to change it only once on each computer.</span></span>

<span data-ttu-id="fea0c-123">Verwenden Sie das folgende Verfahren, um die Ausführungs Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fea0c-123">To change the execution policy, use the following procedure.</span></span>

<span data-ttu-id="fea0c-124">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fea0c-124">At the command prompt, type:</span></span>

```powershell
Set-ExecutionPolicy AllSigned
```

<span data-ttu-id="fea0c-125">oder</span><span class="sxs-lookup"><span data-stu-id="fea0c-125">or</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

<span data-ttu-id="fea0c-126">Die Änderung wird sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="fea0c-126">The change is effective immediately.</span></span>

<span data-ttu-id="fea0c-127">Zum Ausführen eines Skripts geben Sie den vollständigen Namen und den vollständigen Pfad zur Skriptdatei ein.</span><span class="sxs-lookup"><span data-stu-id="fea0c-127">To run a script, type the full name and the full path to the script file.</span></span>

<span data-ttu-id="fea0c-128">Wenn Sie z. b. das Get-ServiceLog.ps1 Skript im Verzeichnis c:\Scripts ausführen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fea0c-128">For example, to run the Get-ServiceLog.ps1 script in the C:\Scripts directory, type:</span></span>

```powershell
C:\Scripts\Get-ServiceLog.ps1
```

<span data-ttu-id="fea0c-129">Um ein Skript im aktuellen Verzeichnis auszuführen, geben Sie den Pfad zum aktuellen Verzeichnis ein, oder verwenden Sie einen Punkt, um das aktuelle Verzeichnis darzustellen, gefolgt von einem Pfad umgekehrten Schrägstrich ( `.\` ).</span><span class="sxs-lookup"><span data-stu-id="fea0c-129">To run a script in the current directory, type the path to the current directory, or use a dot to represent the current directory, followed by a path backslash (`.\`).</span></span>

<span data-ttu-id="fea0c-130">Wenn Sie z. b. das ServicesLog.ps1 Skript im lokalen Verzeichnis ausführen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fea0c-130">For example, to run the ServicesLog.ps1 script in the local directory, type:</span></span>

```powershell
.\Get-ServiceLog.ps1
```

<span data-ttu-id="fea0c-131">Wenn das Skript über Parameter verfügt, geben Sie die Parameter und Parameterwerte nach dem Skript Dateiname ein.</span><span class="sxs-lookup"><span data-stu-id="fea0c-131">If the script has parameters, type the parameters and parameter values after the script filename.</span></span>

<span data-ttu-id="fea0c-132">Der folgende Befehl verwendet z. b. den ServiceName-Parameter des Get-ServiceLog Skripts, um ein Protokoll der WinRM-Dienst Aktivität anzufordern.</span><span class="sxs-lookup"><span data-stu-id="fea0c-132">For example, the following command uses the ServiceName parameter of the Get-ServiceLog script to request a log of WinRM service activity.</span></span>

```powershell
.\Get-ServiceLog.ps1 -ServiceName WinRM
```

<span data-ttu-id="fea0c-133">Als Sicherheits Feature führt PowerShell keine Skripts aus, wenn Sie im Datei-Explorer auf das Skript Symbol doppelklicken oder wenn Sie den Skriptnamen ohne vollständigen Pfad eingeben, auch wenn sich das Skript im aktuellen Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="fea0c-133">As a security feature, PowerShell does not run scripts when you double-click the script icon in File Explorer or when you type the script name without a full path, even when the script is in the current directory.</span></span> <span data-ttu-id="fea0c-134">Weitere Informationen zum Ausführen von Befehlen und Skripts in PowerShell finden Sie unter [about_Command_Precedence](about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="fea0c-134">For more information about running commands and scripts in PowerShell, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

### <a name="run-with-powershell"></a><span data-ttu-id="fea0c-135">Ausführen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="fea0c-135">Run with PowerShell</span></span>

<span data-ttu-id="fea0c-136">Ab PowerShell 3,0 können Sie Skripts aus dem Datei-Explorer ausführen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-136">Beginning in PowerShell 3.0, you can run scripts from File Explorer.</span></span>

<span data-ttu-id="fea0c-137">So verwenden Sie die Funktion "mit PowerShell ausführen":</span><span class="sxs-lookup"><span data-stu-id="fea0c-137">To use the "Run with PowerShell" feature:</span></span>

<span data-ttu-id="fea0c-138">Führen Sie den Datei-Explorer aus, klicken Sie mit der rechten Maustaste auf den Dateinamen des Skripts, und wählen Sie dann die Option</span><span class="sxs-lookup"><span data-stu-id="fea0c-138">Run File Explorer, right-click the script filename and then select "Run with PowerShell".</span></span>

<span data-ttu-id="fea0c-139">Die Funktion "mit PowerShell ausführen" dient zum Ausführen von Skripts, die nicht über erforderliche Parameter verfügen und keine Ausgabe an die Eingabeaufforderung zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="fea0c-139">The "Run with PowerShell" feature is designed to run scripts that do not have required parameters and do not return output to the command prompt.</span></span>

<span data-ttu-id="fea0c-140">Weitere Informationen finden Sie unter [Informationen zum Ausführen mit PowerShell](about_Run_With_PowerShell.md).</span><span class="sxs-lookup"><span data-stu-id="fea0c-140">For more information, see [about_Run_With_PowerShell](about_Run_With_PowerShell.md).</span></span>

### <a name="running-scripts-on-other-computers"></a><span data-ttu-id="fea0c-141">Ausführen von Skripts auf anderen Computern</span><span class="sxs-lookup"><span data-stu-id="fea0c-141">Running scripts on other computers</span></span>

<span data-ttu-id="fea0c-142">Verwenden Sie zum Ausführen eines Skripts auf einem oder mehreren Remote Computern den **FilePath** -Parameter des `Invoke-Command` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fea0c-142">To run a script on one or more remote computers, use the **FilePath** parameter of the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="fea0c-143">Geben Sie den Pfad und den Dateinamen des Skripts als Wert für den **FilePath** -Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="fea0c-143">Enter the path and filename of the script as the value of the **FilePath** parameter.</span></span> <span data-ttu-id="fea0c-144">Das Skript muss sich auf dem lokalen Computer oder in einem Verzeichnis befinden, auf das der lokale Computer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="fea0c-144">The script must reside on the local computer or in a directory that the local computer can access.</span></span>

<span data-ttu-id="fea0c-145">Der folgende Befehl führt das `Get-ServiceLog.ps1` Skript auf den Remote Computern namens SERVER01 und Server02 aus.</span><span class="sxs-lookup"><span data-stu-id="fea0c-145">The following command runs the `Get-ServiceLog.ps1` script on the remote computers named Server01 and Server02.</span></span>

```powershell
Invoke-Command -ComputerName Server01,Server02 -FilePath `
  C:\Scripts\Get-ServiceLog.ps1
```

## <a name="get-help-for-scripts"></a><span data-ttu-id="fea0c-146">Hilfe zu Skripts</span><span class="sxs-lookup"><span data-stu-id="fea0c-146">Get help for scripts</span></span>

<span data-ttu-id="fea0c-147">Das Get-Help-Cmdlet ruft die Hilfe Themen für Skripts sowie für Cmdlets und andere Befehls Typen ab.</span><span class="sxs-lookup"><span data-stu-id="fea0c-147">The Get-Help cmdlet gets the help topics for scripts as well as for cmdlets and other types of commands.</span></span> <span data-ttu-id="fea0c-148">Um das Hilfethema für ein Skript zu erhalten, geben Sie `Get-Help` gefolgt vom Pfad und Dateinamen des Skripts ein.</span><span class="sxs-lookup"><span data-stu-id="fea0c-148">To get the help topic for a script, type `Get-Help` followed by the path and filename of the script.</span></span> <span data-ttu-id="fea0c-149">Wenn sich der Skript Pfad in der `Path` Umgebungsvariablen befindet, können Sie den Pfad weglassen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-149">If the script path is in your `Path` environment variable, you can omit the path.</span></span>

<span data-ttu-id="fea0c-150">Wenn Sie z. b. Hilfe zum ServicesLog.ps1 Skript benötigen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fea0c-150">For example, to get help for the ServicesLog.ps1 script, type:</span></span>

```powershell
get-help C:\admin\scripts\ServicesLog.ps1
```

## <a name="how-to-write-a-script"></a><span data-ttu-id="fea0c-151">Schreiben eines Skripts</span><span class="sxs-lookup"><span data-stu-id="fea0c-151">How to write a script</span></span>

<span data-ttu-id="fea0c-152">Ein Skript kann beliebige gültige PowerShell-Befehle enthalten, einschließlich einzelner Befehle, Befehle, die die Pipeline, Funktionen und Steuerungsstrukturen verwenden, z. b. if-Anweisungen und for-Schleifen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-152">A script can contain any valid PowerShell commands, including single commands, commands that use the pipeline, functions, and control structures such as If statements and For loops.</span></span>

<span data-ttu-id="fea0c-153">Öffnen Sie zum Schreiben eines Skripts eine neue Datei in einem Text-Editor, geben Sie die Befehle ein, und speichern Sie Sie in einer Datei mit einem gültigen Dateinamen mit der `.ps1` Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="fea0c-153">To write a script, open a new file in a text editor, type the commands, and save them in a file with a valid filename with the `.ps1` file extension.</span></span>

<span data-ttu-id="fea0c-154">Das folgende Beispiel ist ein einfaches Skript, mit dem die Dienste abgerufen werden, die auf dem aktuellen System ausgeführt werden, und in einer Protokolldatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="fea0c-154">The following example is a simple script that gets the services that are running on the current system and saves them to a log file.</span></span> <span data-ttu-id="fea0c-155">Der Protokoll Dateiname wird aus dem aktuellen Datum erstellt.</span><span class="sxs-lookup"><span data-stu-id="fea0c-155">The log filename is created from the current date.</span></span>

```powershell
$date = (get-date).dayofyear
get-service | out-file "$date.log"
```

<span data-ttu-id="fea0c-156">Öffnen Sie zum Erstellen dieses Skripts einen Text-Editor oder einen Skript-Editor, geben Sie diese Befehle ein, und speichern Sie Sie in einer Datei mit dem Namen `ServiceLog.ps1` .</span><span class="sxs-lookup"><span data-stu-id="fea0c-156">To create this script, open a text editor or a script editor, type these commands, and then save them in a file named `ServiceLog.ps1`.</span></span>

### <a name="parameters-in-scripts"></a><span data-ttu-id="fea0c-157">Parameter in Skripts</span><span class="sxs-lookup"><span data-stu-id="fea0c-157">Parameters in scripts</span></span>

<span data-ttu-id="fea0c-158">Verwenden Sie zum Definieren von Parametern in einem Skript eine Param-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="fea0c-158">To define parameters in a script, use a Param statement.</span></span> <span data-ttu-id="fea0c-159">Die `Param` Anweisung muss die erste Anweisung in einem Skript sein, mit Ausnahme von Kommentaren und `#Require` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-159">The `Param` statement must be the first statement in a script, except for comments and any `#Require` statements.</span></span>

<span data-ttu-id="fea0c-160">Skript Parameter funktionieren wie Funktionsparameter.</span><span class="sxs-lookup"><span data-stu-id="fea0c-160">Script parameters work like function parameters.</span></span> <span data-ttu-id="fea0c-161">Die Parameterwerte sind für alle Befehle im Skript verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fea0c-161">The parameter values are available to all of the commands in the script.</span></span> <span data-ttu-id="fea0c-162">Alle Funktionen von Funktionsparametern, einschließlich des Parameter Attributs und der benannten Argumente, sind ebenfalls in Skripts gültig.</span><span class="sxs-lookup"><span data-stu-id="fea0c-162">All of the features of function parameters, including the Parameter attribute and its named arguments, are also valid in scripts.</span></span>

<span data-ttu-id="fea0c-163">Beim Ausführen des Skripts geben Skript Benutzer die Parameter nach dem Skriptnamen ein.</span><span class="sxs-lookup"><span data-stu-id="fea0c-163">When running the script, script users type the parameters after the script name.</span></span>

<span data-ttu-id="fea0c-164">Das folgende Beispiel zeigt ein `Test-Remote.ps1` Skript, das über einen **Computername** -Parameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="fea0c-164">The following example shows a `Test-Remote.ps1` script that has a **ComputerName** parameter.</span></span> <span data-ttu-id="fea0c-165">Beide Skriptfunktionen können auf den Wert des **Computername** -Parameters zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-165">Both of the script functions can access the **ComputerName** parameter value.</span></span>

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

<span data-ttu-id="fea0c-166">Um dieses Skript auszuführen, geben Sie den Namen des Parameters nach dem Skriptnamen ein.</span><span class="sxs-lookup"><span data-stu-id="fea0c-166">To run this script, type the parameter name after the script name.</span></span> <span data-ttu-id="fea0c-167">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fea0c-167">For example:</span></span>

```powershell
C:\PS> .\test-remote.ps1 -computername Server01

Ping succeeded: Server01
Remote test failed: Server01
```

<span data-ttu-id="fea0c-168">Weitere Informationen zur Param-Anweisung und zu den Funktionsparametern finden Sie unter [about_Functions](about_Functions.md) und [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="fea0c-168">For more information about the Param statement and the function parameters, see [about_Functions](about_Functions.md) and [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="writing-help-for-scripts"></a><span data-ttu-id="fea0c-169">Schreiben von Hilfe für Skripts</span><span class="sxs-lookup"><span data-stu-id="fea0c-169">Writing help for scripts</span></span>

<span data-ttu-id="fea0c-170">Sie können ein Hilfethema für ein Skript schreiben, indem Sie eine der beiden folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="fea0c-170">You can write a help topic for a script by using either of the two following methods:</span></span>

- <span data-ttu-id="fea0c-171">Comment-Based Hilfe zu Skripts</span><span class="sxs-lookup"><span data-stu-id="fea0c-171">Comment-Based Help for Scripts</span></span>

  <span data-ttu-id="fea0c-172">Erstellen Sie ein Hilfethema mithilfe von speziellen Schlüsselwörtern in den Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="fea0c-172">Create a Help topic by using special keywords in the comments.</span></span> <span data-ttu-id="fea0c-173">Um die Kommentar basierte Hilfe für ein Skript zu erstellen, müssen die Kommentare am Anfang oder Ende der Skriptdatei abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fea0c-173">To create comment-based Help for a script, the comments must be placed at the beginning or end of the script file.</span></span> <span data-ttu-id="fea0c-174">Weitere Informationen zur Kommentar basierten Hilfe finden Sie unter [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="fea0c-174">For more information about comment-based Help, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span>

- <span data-ttu-id="fea0c-175">XML-Based Hilfe zu Skripts</span><span class="sxs-lookup"><span data-stu-id="fea0c-175">XML-Based Help  for Scripts</span></span>

  <span data-ttu-id="fea0c-176">Erstellen Sie ein XML-basiertes Hilfethema, z. b. den Typ, der in der Regel für Cmdlets erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fea0c-176">Create an XML-based Help topic, such as the type that is typically created for cmdlets.</span></span> <span data-ttu-id="fea0c-177">Die XML-basierte Hilfe ist erforderlich, wenn Sie Hilfe Themen in mehrere Sprachen übersetzen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-177">XML-based Help is required if you are translating Help topics into multiple languages.</span></span>

<span data-ttu-id="fea0c-178">Um das Skript dem XML-basierten Hilfethema zuzuordnen, verwenden Sie die. Externalhelp-Kommentar Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="fea0c-178">To associate the script with the XML-based Help topic, use the .ExternalHelp Help comment keyword.</span></span> <span data-ttu-id="fea0c-179">Weitere Informationen zum externalhelp-Schlüsselwort finden Sie unter [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="fea0c-179">For more information about the ExternalHelp keyword, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span> <span data-ttu-id="fea0c-180">Weitere Informationen zur XML-basierten Hilfe finden Sie unter [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="fea0c-180">For more information about XML-based help, see [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

### <a name="returning-an-exit-value"></a><span data-ttu-id="fea0c-181">Zurückgeben eines Exit-Werts</span><span class="sxs-lookup"><span data-stu-id="fea0c-181">Returning an exit value</span></span>

<span data-ttu-id="fea0c-182">Standardmäßig geben Skripts beim Ende des Skripts keinen Beendigungs Status zurück.</span><span class="sxs-lookup"><span data-stu-id="fea0c-182">By default, scripts do not return an exit status when the script ends.</span></span> <span data-ttu-id="fea0c-183">Sie müssen die- `exit` Anweisung verwenden, um einen Exitcode von einem Skript zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fea0c-183">You must use the `exit` statement to return an exit code from a script.</span></span> <span data-ttu-id="fea0c-184">Standardmäßig gibt die- `exit` Anweisung zurück `0` .</span><span class="sxs-lookup"><span data-stu-id="fea0c-184">By default, the `exit` statement returns `0`.</span></span> <span data-ttu-id="fea0c-185">Sie können einen numerischen Wert angeben, um einen anderen Beendigungs Status zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fea0c-185">You can provide a numeric value to return a different exit status.</span></span> <span data-ttu-id="fea0c-186">Ein Exitcode ungleich NULL signalisiert in der Regel einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="fea0c-186">A nonzero exit code typically signals a failure.</span></span>

<span data-ttu-id="fea0c-187">Unter Windows ist eine beliebige Zahl zwischen `[int]::MinValue` und `[int]::MaxValue` zulässig.</span><span class="sxs-lookup"><span data-stu-id="fea0c-187">On Windows, any number between `[int]::MinValue` and `[int]::MaxValue` is allowed.</span></span>

<span data-ttu-id="fea0c-188">Unter Unix sind nur positive Zahlen zwischen `[byte]::MinValue` (0) und `[byte]::MaxValue` (255) zulässig.</span><span class="sxs-lookup"><span data-stu-id="fea0c-188">On Unix, only positive numbers between `[byte]::MinValue` (0) and `[byte]::MaxValue` (255) are allowed.</span></span> <span data-ttu-id="fea0c-189">Eine negative Zahl im Bereich von `-1` bis `-255` wird durch Hinzufügen von automatisch in eine positive Zahl übersetzt.</span><span class="sxs-lookup"><span data-stu-id="fea0c-189">A negative number in the range of `-1` through `-255` is automatically translated into a positive number by adding</span></span>
256. <span data-ttu-id="fea0c-190">Beispielsweise `-2` wird in umgewandelt `254` .</span><span class="sxs-lookup"><span data-stu-id="fea0c-190">For example, `-2` is transformed to `254`.</span></span>

<span data-ttu-id="fea0c-191">In PowerShell legt die- `exit` Anweisung den Wert der- `$LASTEXITCODE` Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="fea0c-191">In PowerShell, the `exit` statement sets the value of the `$LASTEXITCODE` variable.</span></span> <span data-ttu-id="fea0c-192">In der Windows-Befehlsshell (cmd.exe) legt die Exit-Anweisung den Wert der `%ERRORLEVEL%` Umgebungsvariablen fest.</span><span class="sxs-lookup"><span data-stu-id="fea0c-192">In the Windows Command Shell (cmd.exe), the exit statement sets the value of the `%ERRORLEVEL%` environment variable.</span></span>

<span data-ttu-id="fea0c-193">Jedes Argument, das nicht numerisch oder außerhalb des plattformspezifischen Bereichs ist, wird in den Wert von übersetzt `0` .</span><span class="sxs-lookup"><span data-stu-id="fea0c-193">Any argument that is non-numeric or outside the platform-specific range is translated to the value of `0`.</span></span>

## <a name="script-scope-and-dot-sourcing"></a><span data-ttu-id="fea0c-194">Skript Bereich und dotsourcing</span><span class="sxs-lookup"><span data-stu-id="fea0c-194">Script scope and dot sourcing</span></span>

<span data-ttu-id="fea0c-195">Jedes Skript wird in einem eigenen Bereich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fea0c-195">Each script runs in its own scope.</span></span> <span data-ttu-id="fea0c-196">Die im Skript erstellten Funktionen, Variablen, Aliase und Laufwerke sind nur im Skript Bereich vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fea0c-196">The functions, variables, aliases, and drives that are created in the script exist only in the script scope.</span></span> <span data-ttu-id="fea0c-197">Sie können nicht auf diese Elemente oder deren Werte in dem Bereich zugreifen, in dem das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fea0c-197">You cannot access these items or their values in the scope in which the script runs.</span></span>

<span data-ttu-id="fea0c-198">Wenn Sie ein Skript in einem anderen Bereich ausführen möchten, können Sie einen Bereich angeben, z. b. Global oder local, oder Sie können ein Punkt für das Skript erstellen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-198">To run a script in a different scope, you can specify a scope, such as Global or Local, or you can dot source the script.</span></span>

<span data-ttu-id="fea0c-199">Mit dem Feature für die Punkt Ermittlung können Sie ein Skript im aktuellen Bereich statt im Skript Bereich ausführen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-199">The dot sourcing feature lets you run a script in the current scope instead of in the script scope.</span></span> <span data-ttu-id="fea0c-200">Wenn Sie ein Skript ausführen, das Punkt basiert ist, werden die Befehle im Skript so ausgeführt, als würden Sie es an der Eingabeaufforderung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="fea0c-200">When you run a script that is dot sourced, the commands in the script run as though you had typed them at the command prompt.</span></span> <span data-ttu-id="fea0c-201">Die vom Skript erstellten Funktionen, Variablen, Aliase und Laufwerke werden in dem Bereich erstellt, in dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="fea0c-201">The functions, variables, aliases, and drives that the script creates are created in the scope in which you are working.</span></span> <span data-ttu-id="fea0c-202">Nachdem das Skript ausgeführt wurde, können Sie die erstellten Elemente verwenden und auf ihre Werte in Ihrer Sitzung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-202">After the script runs, you can use the created items and access their values in your session.</span></span>

<span data-ttu-id="fea0c-203">Um die Quelle eines Skripts zu überschreiben, geben Sie einen Punkt (.) und ein Leerzeichen vor dem Skript Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="fea0c-203">To dot source a script, type a dot (.) and a space before the script path.</span></span>

<span data-ttu-id="fea0c-204">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fea0c-204">For example:</span></span>

```powershell
. C:\scripts\UtilityFunctions.ps1
```

<span data-ttu-id="fea0c-205">oder</span><span class="sxs-lookup"><span data-stu-id="fea0c-205">or</span></span>

```powershell
. .\UtilityFunctions.ps1
```

<span data-ttu-id="fea0c-206">Nachdem das `UtilityFunctions.ps1` Skript ausgeführt wurde, werden die Funktionen und Variablen, die das Skript erstellt, dem aktuellen Gültigkeitsbereich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fea0c-206">After the `UtilityFunctions.ps1` script runs, the functions and variables that the script creates are added to the current scope.</span></span>

<span data-ttu-id="fea0c-207">Das `UtilityFunctions.ps1` Skript erstellt z `New-Profile` . b. die-Funktion und die- `$ProfileName` Variable.</span><span class="sxs-lookup"><span data-stu-id="fea0c-207">For example, the `UtilityFunctions.ps1` script creates the `New-Profile` function and the `$ProfileName` variable.</span></span>

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

<span data-ttu-id="fea0c-208">Wenn Sie das `UtilityFunctions.ps1` Skript in einem eigenen Skript Bereich ausführen, sind die `New-Profile` -Funktion und die- `$ProfileName` Variable nur vorhanden, während das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fea0c-208">If you run the `UtilityFunctions.ps1` script in its own script scope, the `New-Profile` function and the `$ProfileName` variable exist only while the script is running.</span></span> <span data-ttu-id="fea0c-209">Wenn das Skript beendet wird, werden die Funktion und die Variable entfernt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fea0c-209">When the script exits, the function and variable are removed, as shown in the following example.</span></span>

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

<span data-ttu-id="fea0c-210">Wenn Sie das Skript auf das Skript angleichen und es ausführen, erstellt das Skript die `New-Profile` Funktion und die `$ProfileName` Variable in Ihrer Sitzung in Ihrem Bereich.</span><span class="sxs-lookup"><span data-stu-id="fea0c-210">When you dot source the script and run it, the script creates the `New-Profile` function and the `$ProfileName` variable in your session in your scope.</span></span> <span data-ttu-id="fea0c-211">Nachdem das Skript ausgeführt wurde, können Sie die- `New-Profile` Funktion in der Sitzung verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fea0c-211">After the script runs, you can use the `New-Profile` function in your session, as shown in the following example.</span></span>

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

<span data-ttu-id="fea0c-212">Weitere Informationen zum Gültigkeitsbereich finden Sie unter about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="fea0c-212">For more information about scope, see about_Scopes.</span></span>

## <a name="scripts-in-modules"></a><span data-ttu-id="fea0c-213">Skripts in Modulen</span><span class="sxs-lookup"><span data-stu-id="fea0c-213">Scripts in modules</span></span>

<span data-ttu-id="fea0c-214">Ein Modul ist ein Satz verwandter PowerShell-Ressourcen, die als Einheit verteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="fea0c-214">A module is a set of related PowerShell resources that can be distributed as a unit.</span></span> <span data-ttu-id="fea0c-215">Sie können Module verwenden, um Ihre Skripts, Funktionen und andere Ressourcen zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="fea0c-215">You can use modules to organize your scripts, functions, and other resources.</span></span> <span data-ttu-id="fea0c-216">Sie können auch Module verwenden, um Ihren Code an andere zu verteilen und um Code aus vertrauenswürdigen Quellen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fea0c-216">You can also use modules to distribute your code to others, and to get code from trusted sources.</span></span>

<span data-ttu-id="fea0c-217">Sie können Skripts in Ihre Module einschließen, oder Sie können ein Skript Modul erstellen, bei dem es sich um ein Modul handelt, das vollständig oder primär von einem Skript und unterstützenden Ressourcen besteht.</span><span class="sxs-lookup"><span data-stu-id="fea0c-217">You can include scripts in your modules, or you can create a script module, which is a module that consists entirely or primarily of a script and supporting resources.</span></span> <span data-ttu-id="fea0c-218">Ein Skript Modul ist nur ein Skript mit der Dateierweiterung ". psm1".</span><span class="sxs-lookup"><span data-stu-id="fea0c-218">A script module is just a script with a .psm1 file extension.</span></span>

<span data-ttu-id="fea0c-219">Weitere Informationen zu Modulen finden Sie unter [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="fea0c-219">For more information about modules, see [about_Modules](about_Modules.md).</span></span>

## <a name="other-script-features"></a><span data-ttu-id="fea0c-220">Weitere Skript Features</span><span class="sxs-lookup"><span data-stu-id="fea0c-220">Other script features</span></span>

<span data-ttu-id="fea0c-221">PowerShell bietet viele nützliche Funktionen, die Sie in Skripts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fea0c-221">PowerShell has many useful features that you can use in scripts.</span></span>

- <span data-ttu-id="fea0c-222">`#Requires` -Sie können eine- `#Requires` Anweisung verwenden, um zu verhindern, dass ein Skript ohne angegebene Module, Snap-Ins und eine bestimmte Version von PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fea0c-222">`#Requires` - You can use a `#Requires` statement to prevent a script from running without specified modules or snap-ins and a specified version of PowerShell.</span></span> <span data-ttu-id="fea0c-223">Weitere Informationen finden Sie unter about_Requires.</span><span class="sxs-lookup"><span data-stu-id="fea0c-223">For more information, see about_Requires.</span></span>

- <span data-ttu-id="fea0c-224">`$PSCommandPath` -Enthält den vollständigen Pfad und den Namen des Skripts, das gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fea0c-224">`$PSCommandPath` - Contains the full path and name of the script that is being run.</span></span> <span data-ttu-id="fea0c-225">Dieser Parameter ist in allen Skripts gültig.</span><span class="sxs-lookup"><span data-stu-id="fea0c-225">This parameter is valid in all scripts.</span></span> <span data-ttu-id="fea0c-226">Diese automatische Variable wird in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fea0c-226">This automatic variable is introduced in PowerShell 3.0.</span></span>

- <span data-ttu-id="fea0c-227">`$PSScriptRoot` -Enthält das Verzeichnis, in dem ein Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fea0c-227">`$PSScriptRoot` - Contains the directory from which a script is being run.</span></span> <span data-ttu-id="fea0c-228">In PowerShell 2,0 ist diese Variable nur in Skript Modulen () gültig `.psm1` .</span><span class="sxs-lookup"><span data-stu-id="fea0c-228">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
  <span data-ttu-id="fea0c-229">Ab PowerShell 3,0 ist Sie in allen Skripts gültig.</span><span class="sxs-lookup"><span data-stu-id="fea0c-229">Beginning in PowerShell 3.0, it is valid in all scripts.</span></span>

- <span data-ttu-id="fea0c-230">`$MyInvocation` -Die `$MyInvocation` Automatische Variable enthält Informationen zum aktuellen Skript, einschließlich Informationen zum Starten oder "aufrufen".</span><span class="sxs-lookup"><span data-stu-id="fea0c-230">`$MyInvocation` - The `$MyInvocation` automatic variable contains information about the current script, including information about how it was started or "invoked."</span></span> <span data-ttu-id="fea0c-231">Sie können diese Variable und ihre Eigenschaften verwenden, um während der Ausführung Informationen über das Skript zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fea0c-231">You can use this variable and its properties to get information about the script while it is running.</span></span> <span data-ttu-id="fea0c-232">Beispielsweise `$MyInvocation` . Die myCommand. Path-Variable enthält den Pfad und den Dateinamen des Skripts.</span><span class="sxs-lookup"><span data-stu-id="fea0c-232">For example, the `$MyInvocation`.MyCommand.Path variable contains the path and filename of the script.</span></span> <span data-ttu-id="fea0c-233">`$MyInvocation`. Die Zeile enthält den Befehl, der das Skript gestartet hat, einschließlich aller Parameter und Werte.</span><span class="sxs-lookup"><span data-stu-id="fea0c-233">`$MyInvocation`.Line contains the command that started the script, including all parameters and values.</span></span>

  <span data-ttu-id="fea0c-234">Ab PowerShell 3,0 verfügt über `$MyInvocation` zwei neue Eigenschaften, die Informationen über das Skript bereitstellen, das das aktuelle Skript aufgerufen oder aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="fea0c-234">Beginning in PowerShell 3.0, `$MyInvocation` has two new properties that provide information about the script that called or invoked the current script.</span></span> <span data-ttu-id="fea0c-235">Die Werte dieser Eigenschaften werden nur aufgefüllt, wenn der aufrufende oder der Aufrufer ein Skript ist.</span><span class="sxs-lookup"><span data-stu-id="fea0c-235">The values of these properties are populated only when the invoker or caller is a script.</span></span>

  - <span data-ttu-id="fea0c-236">**Pscommandpath** enthält den vollständigen Pfad und den Namen des Skripts, das das aktuelle Skript aufgerufen oder aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="fea0c-236">**PSCommandPath** contains the full path and name of the script that called or invoked the current script.</span></span>

  - <span data-ttu-id="fea0c-237">**Psscriptroot** enthält das Verzeichnis des Skripts, das das aktuelle Skript aufgerufen oder aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="fea0c-237">**PSScriptRoot** contains the directory of the script that called or invoked the current script.</span></span>

  <span data-ttu-id="fea0c-238">Im Gegensatz zu den `$PSCommandPath` `$PSScriptRoot` automatischen Variablen und, die Informationen zum aktuellen Skript enthalten, enthalten die Eigenschaften **pscommandpath** und **psscriptroot** der `$MyInvocation` Variablen Informationen über das Skript, das das aktuelle Skript aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="fea0c-238">Unlike the `$PSCommandPath` and `$PSScriptRoot` automatic variables, which contain information about the current script, the **PSCommandPath** and **PSScriptRoot** properties of the `$MyInvocation` variable contain information about the script that called the current script.</span></span>

- <span data-ttu-id="fea0c-239">Datenabschnitte: Sie können das `Data` Schlüsselwort verwenden, um Daten von der Logik in Skripts zu trennen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-239">Data sections - You can use the `Data` keyword to separate data from logic in scripts.</span></span> <span data-ttu-id="fea0c-240">Datenabschnitte können auch die Lokalisierung vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-240">Data sections can also make localization easier.</span></span> <span data-ttu-id="fea0c-241">Weitere Informationen finden Sie unter [about_Data_Sections](about_Data_Sections.md) und [about_Script_Internationalization](about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="fea0c-241">For more information, see [about_Data_Sections](about_Data_Sections.md) and [about_Script_Internationalization](about_Script_Internationalization.md).</span></span>

- <span data-ttu-id="fea0c-242">Skript Signatur-Sie können einem Skript eine digitale Signatur hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fea0c-242">Script Signing - You can add a digital signature to a script.</span></span> <span data-ttu-id="fea0c-243">Abhängig von der Ausführungs Richtlinie können Sie digitale Signaturen verwenden, um die Ausführung von Skripts einzuschränken, die unsichere Befehle enthalten könnten.</span><span class="sxs-lookup"><span data-stu-id="fea0c-243">Depending on the execution policy, you can use digital signatures to restrict the running of scripts that could include unsafe commands.</span></span> <span data-ttu-id="fea0c-244">Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md) und [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="fea0c-244">For more information, see [about_Execution_Policies](about_Execution_Policies.md) and [about_Signing](about_Signing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fea0c-245">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fea0c-245">See also</span></span>

[<span data-ttu-id="fea0c-246">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="fea0c-246">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="fea0c-247">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="fea0c-247">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="fea0c-248">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="fea0c-248">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="fea0c-249">about_Functions</span><span class="sxs-lookup"><span data-stu-id="fea0c-249">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="fea0c-250">about_Modules</span><span class="sxs-lookup"><span data-stu-id="fea0c-250">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="fea0c-251">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="fea0c-251">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="fea0c-252">about_Requires</span><span class="sxs-lookup"><span data-stu-id="fea0c-252">about_Requires</span></span>](about_Requires.md)

[<span data-ttu-id="fea0c-253">about_Run_With_PowerShell</span><span class="sxs-lookup"><span data-stu-id="fea0c-253">about_Run_With_PowerShell</span></span>](about_Run_With_PowerShell.md)

[<span data-ttu-id="fea0c-254">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="fea0c-254">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="fea0c-255">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="fea0c-255">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="fea0c-256">about_Signing</span><span class="sxs-lookup"><span data-stu-id="fea0c-256">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="fea0c-257">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="fea0c-257">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
