---
description: Erläutert, wie die `powershell.exe` Befehlszeilenschnittstelle verwendet wird. Zeigt die Befehlszeilenparameter an und beschreibt die Syntax.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_exe
ms.openlocfilehash: 4025630ebb3abe4c0598c85940cfce383e9c7890
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "104726654"
---
# <a name="about-powershellexe"></a><span data-ttu-id="1dab7-105">Informationen zu PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="1dab7-105">About PowerShell.exe</span></span>

## <a name="short-description"></a><span data-ttu-id="1dab7-106">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dab7-106">Short Description</span></span>
<span data-ttu-id="1dab7-107">Erläutert, wie die `powershell.exe` Befehlszeilenschnittstelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1dab7-107">Explains how to use the `powershell.exe` command-line interface.</span></span> <span data-ttu-id="1dab7-108">Zeigt die Befehlszeilenparameter an und beschreibt die Syntax.</span><span class="sxs-lookup"><span data-stu-id="1dab7-108">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="1dab7-109">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dab7-109">Long Description</span></span>

### <a name="syntax"></a><span data-ttu-id="1dab7-110">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1dab7-110">SYNTAX</span></span>

```
PowerShell[.exe]
    [-PSConsoleFile <file> | -Version <version>]
    [-NoLogo]
    [-NoExit]
    [-Sta]
    [-Mta]
    [-NoProfile]
    [-NonInteractive]
    [-InputFormat {Text | XML}]
    [-OutputFormat {Text | XML}]
    [-WindowStyle <style>]
    [-EncodedCommand <Base64EncodedCommand>]
    [-ConfigurationName <string>]
    [-File - | <filePath> <args>]
    [-ExecutionPolicy <ExecutionPolicy>]
    [-Command - | { <script-block> [-args <arg-array>] }
                | { <string> [<CommandParameters>] } ]

PowerShell[.exe] -Help | -? | /?
```

### <a name="parameters"></a><span data-ttu-id="1dab7-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="1dab7-111">Parameters</span></span>

#### <a name="-psconsolefile-filepath"></a><span data-ttu-id="1dab7-112">-PSConsoleFile \<FilePath\></span><span class="sxs-lookup"><span data-stu-id="1dab7-112">-PSConsoleFile \<FilePath\></span></span>

<span data-ttu-id="1dab7-113">Lädt die angegebene PowerShell-Konsolendatei.</span><span class="sxs-lookup"><span data-stu-id="1dab7-113">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="1dab7-114">Geben Sie den Pfad und Namen der Konsolendatei ein.</span><span class="sxs-lookup"><span data-stu-id="1dab7-114">Enter the path and name of the console file.</span></span> <span data-ttu-id="1dab7-115">Verwenden Sie zum Erstellen einer Konsolendatei das Cmdlet Export-Console in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1dab7-115">To create a console file, use the Export-Console cmdlet in PowerShell.</span></span>

#### <a name="-version-powershell-version"></a><span data-ttu-id="1dab7-116">-Version \<PowerShell Version\></span><span class="sxs-lookup"><span data-stu-id="1dab7-116">-Version \<PowerShell Version\></span></span>

<span data-ttu-id="1dab7-117">Startet die angegebene Version von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1dab7-117">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="1dab7-118">Gültige Werte sind 2.0 und 3.0.</span><span class="sxs-lookup"><span data-stu-id="1dab7-118">Valid values are 2.0 and 3.0.</span></span> <span data-ttu-id="1dab7-119">Die Version, die Sie angeben, muss auf dem System installiert sein.</span><span class="sxs-lookup"><span data-stu-id="1dab7-119">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="1dab7-120">Wenn Windows PowerShell 3,0 auf dem Computer installiert ist, ist "3,0" die Standardversion.</span><span class="sxs-lookup"><span data-stu-id="1dab7-120">If Windows PowerShell 3.0 is installed on the computer, "3.0" is the default version.</span></span>
<span data-ttu-id="1dab7-121">Andernfalls ist "2,0" die Standardversion.</span><span class="sxs-lookup"><span data-stu-id="1dab7-121">Otherwise, "2.0" is the default version.</span></span> <span data-ttu-id="1dab7-122">Weitere Informationen finden Sie unter [Installieren von PowerShell](/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1dab7-122">For more information, see [Installing PowerShell](/powershell/scripting/install/installing-windows-powershell).</span></span>

#### <a name="-nologo"></a><span data-ttu-id="1dab7-123">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="1dab7-123">-NoLogo</span></span>

<span data-ttu-id="1dab7-124">Blendet die Copyrightinformationen beim Start aus.</span><span class="sxs-lookup"><span data-stu-id="1dab7-124">Hides the copyright banner at startup.</span></span>

#### <a name="-noexit"></a><span data-ttu-id="1dab7-125">-NoExit</span><span class="sxs-lookup"><span data-stu-id="1dab7-125">-NoExit</span></span>

<span data-ttu-id="1dab7-126">Nach dem Ausführen der Startbefehle erfolgt kein Beenden.</span><span class="sxs-lookup"><span data-stu-id="1dab7-126">Does not exit after running startup commands.</span></span>

#### <a name="-sta"></a><span data-ttu-id="1dab7-127">-Sta</span><span class="sxs-lookup"><span data-stu-id="1dab7-127">-Sta</span></span>

<span data-ttu-id="1dab7-128">Startet PowerShell mit einem Singlethread-Apartment.</span><span class="sxs-lookup"><span data-stu-id="1dab7-128">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="1dab7-129">In Windows PowerShell 2.0 ist Multithread-Apartment (MTA) die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="1dab7-129">In Windows PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span> <span data-ttu-id="1dab7-130">In Windows PowerShell 3.0 ist Singlethread-Apartment (STA) die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="1dab7-130">In Windows PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span>

#### <a name="-mta"></a><span data-ttu-id="1dab7-131">-Mta</span><span class="sxs-lookup"><span data-stu-id="1dab7-131">-Mta</span></span>

<span data-ttu-id="1dab7-132">Startet PowerShell mit einem Multithread-Apartment.</span><span class="sxs-lookup"><span data-stu-id="1dab7-132">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="1dab7-133">Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1dab7-133">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="1dab7-134">In PowerShell 2.0 stellt Multithread-Apartment (MTA) die Standardeinstellung dar.</span><span class="sxs-lookup"><span data-stu-id="1dab7-134">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span> <span data-ttu-id="1dab7-135">In PowerShell 3.0 ist Singlethread-Apartment (STA) die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="1dab7-135">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span>

#### <a name="-noprofile"></a><span data-ttu-id="1dab7-136">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="1dab7-136">-NoProfile</span></span>

<span data-ttu-id="1dab7-137">Das PowerShell-Profil wird nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="1dab7-137">Does not load the PowerShell profile.</span></span>

#### <a name="-noninteractive"></a><span data-ttu-id="1dab7-138">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="1dab7-138">-NonInteractive</span></span>

<span data-ttu-id="1dab7-139">Zeigt dem Benutzer keine interaktive Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="1dab7-139">Does not present an interactive prompt to the user.</span></span>

#### <a name="-inputformat-text--xml"></a><span data-ttu-id="1dab7-140">-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="1dab7-140">-InputFormat {Text | XML}</span></span>

<span data-ttu-id="1dab7-141">Beschreibt das Format der Daten, die an PowerShell übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="1dab7-141">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="1dab7-142">Gültige Werte sind "Text" (Textzeichenfolgen) oder "XML" (serialisiertes CLIXML-Format).</span><span class="sxs-lookup"><span data-stu-id="1dab7-142">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

#### <a name="-outputformat-text--xml"></a><span data-ttu-id="1dab7-143">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="1dab7-143">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="1dab7-144">Bestimmt, wie die Ausgabe von PowerShell formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="1dab7-144">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="1dab7-145">Gültige Werte sind "Text" (Textzeichenfolgen) oder "XML" (serialisiertes CLIXML-Format).</span><span class="sxs-lookup"><span data-stu-id="1dab7-145">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

#### <a name="-windowstyle-window-style"></a><span data-ttu-id="1dab7-146">-WindowStyle \<Window style\></span><span class="sxs-lookup"><span data-stu-id="1dab7-146">-WindowStyle \<Window style\></span></span>

<span data-ttu-id="1dab7-147">Legt den Fensterstil für die Sitzung fest.</span><span class="sxs-lookup"><span data-stu-id="1dab7-147">Sets the window style for the session.</span></span> <span data-ttu-id="1dab7-148">Gültige Werte sind „Normal“, „Minimized“, „Maximized“ und „Hidden“.</span><span class="sxs-lookup"><span data-stu-id="1dab7-148">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

#### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="1dab7-149">-EncodedCommand \<Base64EncodedCommand\></span><span class="sxs-lookup"><span data-stu-id="1dab7-149">-EncodedCommand \<Base64EncodedCommand\></span></span>

<span data-ttu-id="1dab7-150">Akzeptiert eine „base-64“-codierte Zeichenfolgenversion eines Befehls.</span><span class="sxs-lookup"><span data-stu-id="1dab7-150">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="1dab7-151">Verwenden Sie diesen Parameter, um Befehle an PowerShell zu übermitteln, die komplexe Anführungszeichen oder geschweifte Klammern erfordern.</span><span class="sxs-lookup"><span data-stu-id="1dab7-151">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span> <span data-ttu-id="1dab7-152">Die Zeichenfolge muss mithilfe der UTF-16LE-Zeichencodierung formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="1dab7-152">The string must be formatted using UTF-16LE character encoding.</span></span>

#### <a name="-configurationname-string"></a><span data-ttu-id="1dab7-153">-ConfigurationName \<string\></span><span class="sxs-lookup"><span data-stu-id="1dab7-153">-ConfigurationName \<string\></span></span>

<span data-ttu-id="1dab7-154">Gibt einen Konfigurations Endpunkt an, in dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1dab7-154">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="1dab7-155">Dies kann ein beliebiger Endpunkt sein, der auf dem lokalen Computer registriert ist, einschließlich der standardmäßigen PowerShell-Remoting-Endpunkte oder ein benutzerdefinierter Endpunkt, der über bestimmte Benutzer Rollen</span><span class="sxs-lookup"><span data-stu-id="1dab7-155">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

#### <a name="-file----filepath-args"></a><span data-ttu-id="1dab7-156">-File-| \<filePath\>\<args\></span><span class="sxs-lookup"><span data-stu-id="1dab7-156">-File - | \<filePath\> \<args\></span></span>

<span data-ttu-id="1dab7-157">Wenn der Wert der **Datei** "-" ist, wird der Befehls Text aus der Standardeingabe gelesen.</span><span class="sxs-lookup"><span data-stu-id="1dab7-157">If the value of **File** is "-", the command text is read from standard input.</span></span>
<span data-ttu-id="1dab7-158">Wenn Sie `powershell -File -` ohne umgeleitete Standardeingabe ausführen, wird eine reguläre Sitzung gestartet.</span><span class="sxs-lookup"><span data-stu-id="1dab7-158">Running `powershell -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="1dab7-159">Dies ist das gleiche wie bei der Angabe des **Datei** Parameters.</span><span class="sxs-lookup"><span data-stu-id="1dab7-159">This is the same as not specifying the **File** parameter at all.</span></span>

<span data-ttu-id="1dab7-160">Wenn der Wert der **Datei** ein Dateipfad ist, wird das Skript im lokalen Gültigkeitsbereich ("Punkt-Source") ausgeführt, sodass die Funktionen und Variablen, die das Skript erstellt, in der aktuellen Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1dab7-160">If the value of **File** is a file path, the script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="1dab7-161">Geben Sie den Pfad der Skriptdatei und Parameter an.</span><span class="sxs-lookup"><span data-stu-id="1dab7-161">Enter the script file path and any parameters.</span></span> <span data-ttu-id="1dab7-162">**File** muss der letzte Parameter im Befehl sein.</span><span class="sxs-lookup"><span data-stu-id="1dab7-162">**File** must be the last parameter in the command.</span></span> <span data-ttu-id="1dab7-163">Alle Werte, die nach dem **File** -Parameter eingegeben werden, werden als Pfad der Skriptdatei und Parameter interpretiert, die an das Skript übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1dab7-163">All values typed after the **File** parameter are interpreted as the script file path and parameters passed to that script.</span></span>

<span data-ttu-id="1dab7-164">Parameter, die an das Skript übergeben werden, werden als Zeichenfolgenliterale übergeben (nach der Interpretation durch die aktuelle Shell).</span><span class="sxs-lookup"><span data-stu-id="1dab7-164">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="1dab7-165">Wenn Sie z. b. **cmd.exe** haben und einen Umgebungsvariablen Wert übergeben möchten, verwenden Sie die **cmd.exe** -Syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="1dab7-165">For example, if you are in **cmd.exe** and want to pass an environment variable value, you would use the **cmd.exe** syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="1dab7-166">Im Gegensatz dazu `powershell.exe -File .\test.ps1 -TestParam $env:windir` führt das Ausführen von in **cmd.exe** dazu, dass das Skript die Literalzeichenfolge empfängt, `$env:windir` da es für die aktuelle **cmd.exe** Shell keine besondere Bedeutung hat.</span><span class="sxs-lookup"><span data-stu-id="1dab7-166">In contrast, running `powershell.exe -File .\test.ps1 -TestParam $env:windir` in **cmd.exe** results in the script receiving the literal string `$env:windir` because it has no special meaning to the current **cmd.exe** shell.</span></span> <span data-ttu-id="1dab7-167">Der `$env:windir` Stil der Umgebungsvariablen Referenz _kann_ innerhalb eines **Befehls** Parameters verwendet werden, da er als PowerShell-Code interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="1dab7-167">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it will be interpreted as PowerShell code.</span></span>

<span data-ttu-id="1dab7-168">Wenn Sie denselben Befehl aus einem **Batch Skript** ausführen möchten, verwenden Sie auch `%~dp0` anstelle von `.\` oder, `$PSScriptRoot` um das aktuelle Ausführungs Verzeichnis darzustellen: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%` .</span><span class="sxs-lookup"><span data-stu-id="1dab7-168">Similarly, if you want to execute the same command from a **Batch script**, you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%`.</span></span>
<span data-ttu-id="1dab7-169">Wenn Sie stattdessen verwenden `.\test.ps1` , löst PowerShell einen Fehler aus, da der literalpfad nicht gefunden werden kann. `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="1dab7-169">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="1dab7-170">Wenn der Wert der **Datei** ein Dateipfad ist, _muss_ **File** der letzte Parameter im Befehl sein, da alle Zeichen, die nach dem **Datei** Parameternamen eingegeben werden, als Pfad der Skriptdatei gefolgt von den Skript Parametern interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1dab7-170">When the value of **File** is a file path, **File** _must_ be the last parameter in the command because any characters typed after the **File** parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="1dab7-171">Sie können die Skript Parameter und-Werte in den Wert des **File** -Parameters einschließen.</span><span class="sxs-lookup"><span data-stu-id="1dab7-171">You can include the script parameters and values in the value of the **File** parameter.</span></span> <span data-ttu-id="1dab7-172">Beispiel: `-File .\Get-Script.ps1 -Domain Central`</span><span class="sxs-lookup"><span data-stu-id="1dab7-172">For example: `-File .\Get-Script.ps1 -Domain Central`</span></span>

<span data-ttu-id="1dab7-173">Die Switch-Parameter eines Skripts werden in der Regel entweder einbezogen oder ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="1dab7-173">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="1dab7-174">Der folgende Befehl verwendet beispielsweise den **all** -Parameter der `Get-Script.ps1` Skriptdatei: `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="1dab7-174">For example, the following command uses the **All** parameter of the `Get-Script.ps1` script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="1dab7-175">In seltenen Fällen müssen Sie möglicherweise einen **booleschen** Wert für einen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="1dab7-175">In rare cases, you might need to provide a **Boolean** value for a parameter.</span></span>
<span data-ttu-id="1dab7-176">Beim Ausführen eines Skripts auf diese Weise ist es nicht möglich, einen expliziten booleschen Wert für einen Switch-Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="1dab7-176">It is not possible to pass an explicit boolean value for a switch parameter when running a script in this way.</span></span> <span data-ttu-id="1dab7-177">Diese Einschränkung wurde in PowerShell 6 ( `pwsh.exe` ) entfernt.</span><span class="sxs-lookup"><span data-stu-id="1dab7-177">This limitation was removed in PowerShell 6 (`pwsh.exe`).</span></span>

#### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="1dab7-178">-ExecutionPolicy \<ExecutionPolicy\></span><span class="sxs-lookup"><span data-stu-id="1dab7-178">-ExecutionPolicy \<ExecutionPolicy\></span></span>

<span data-ttu-id="1dab7-179">Legt die Standard Ausführungs Richtlinie für die aktuelle Sitzung fest und speichert Sie in der `$env:PSExecutionPolicyPreference` Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="1dab7-179">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="1dab7-180">Dieser Parameter ändert nicht die PowerShell-Ausführungsrichtlinie, die in der Registrierung festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1dab7-180">This parameter does not change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="1dab7-181">Weitere Informationen zu PowerShell-Ausführungsrichtlinien (einschließlich einer Liste gültiger Werte) finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="1dab7-181">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

#### <a name="-command"></a><span data-ttu-id="1dab7-182">-Command</span><span class="sxs-lookup"><span data-stu-id="1dab7-182">-Command</span></span>

<span data-ttu-id="1dab7-183">Führt die angegebenen Befehle (und alle Parameter) aus, als ob Sie an der PowerShell-Eingabeaufforderung eingegeben wurden, und wird dann beendet, es sei denn, der- `NoExit` Parameter wird angegeben.</span><span class="sxs-lookup"><span data-stu-id="1dab7-183">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="1dab7-184">Der Wert des **Befehls** kann `-` , ein Skriptblock oder eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="1dab7-184">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="1dab7-185">Wenn der Wert von **Command** ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.</span><span class="sxs-lookup"><span data-stu-id="1dab7-185">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="1dab7-186">Der **Command** -Parameter akzeptiert nur einen Skriptblock für die Ausführung, wenn der an den **Befehl** übergebenen Wert als **ScriptBlock** -Typ erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1dab7-186">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="1dab7-187">Dies ist _nur_ möglich, wenn `powershell.exe` von einem anderen PowerShell-Host ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1dab7-187">This is _only_ possible when running `powershell.exe` from another PowerShell host.</span></span> <span data-ttu-id="1dab7-188">Der **ScriptBlock** -Typ kann in einer vorhandenen-Variable enthalten, von einem Ausdruck zurückgegeben oder vom PowerShell-Host als literaler Skriptblock in geschweiften Klammern () analysiert werden, `{}` bevor er an übergeben wird `powershell.exe` .</span><span class="sxs-lookup"><span data-stu-id="1dab7-188">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `powershell.exe`.</span></span>

```powershell
powershell -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="1dab7-189">In `cmd.exe` gibt es keinen Skriptblock (oder einen **ScriptBlock** -Typ), sodass der an den **Befehl** übergeben Wert _immer_ eine Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="1dab7-189">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="1dab7-190">Sie können einen Skriptblock innerhalb der Zeichenfolge schreiben, aber anstatt ausgeführt zu werden, verhält er sich genau so, als ob Sie ihn an einer typischen PowerShell-Eingabeaufforderung eingegeben hätten, wobei der Inhalt des Skriptblocks wieder an Sie ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1dab7-190">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="1dab7-191">Eine an den **Befehl** weiter gegebene Zeichenfolge wird weiterhin als PowerShell-Code ausgeführt, sodass die Skriptblock geschweiften Klammern bei der Ausführung von häufig nicht erforderlich sind `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="1dab7-191">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="1dab7-192">Zum Ausführen eines Inlineskriptblocks, der in einer Zeichenfolge definiert ist, kann der [Aufrufoperator](about_operators.md#special-operators) `&` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="1dab7-192">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```cmd
powershell.exe -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="1dab7-193">Wenn der Wert von " **Command** " eine Zeichenfolge ist, muss **Command** der letzte Parameter für "pwsh" sein, da alle nachfolgenden Argumente als Teil des auszuführenden Befehls interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1dab7-193">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="1dab7-194">Wenn Sie innerhalb einer vorhandenen PowerShell-Sitzung aufgerufen werden, werden die Ergebnisse als deserialisierte XML-Objekte und nicht als Live-Objekte an die übergeordnete Shell zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1dab7-194">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="1dab7-195">Bei anderen Shells werden die Ergebnisse als Zeichen folgen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1dab7-195">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="1dab7-196">Wenn der Wert von **Command** ist `-` , wird der Befehls Text aus der Standardeingabe gelesen.</span><span class="sxs-lookup"><span data-stu-id="1dab7-196">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="1dab7-197">Sie müssen die Standardeingabe umleiten, wenn Sie den **Command** -Parameter mit der Standardeingabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="1dab7-197">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="1dab7-198">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1dab7-198">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="1dab7-199">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1dab7-199">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="1dab7-200">Der Prozessexitcode wird durch den Status des letzten (ausgeführten) Befehls im Skriptblock bestimmt.</span><span class="sxs-lookup"><span data-stu-id="1dab7-200">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="1dab7-201">Der Exitcode ist, wenn den Wert hat `0` `$?` `$true` oder `1` Wenn `$?` ist `$false` .</span><span class="sxs-lookup"><span data-stu-id="1dab7-201">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="1dab7-202">Wenn der letzte Befehl ein externes Programm oder ein PowerShell-Skript ist, das explizit einen Exitcode angibt, der nicht `0` oder ist `1` , wird der Exitcode `1` für den Prozessexitcode in konvertiert.</span><span class="sxs-lookup"><span data-stu-id="1dab7-202">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="1dab7-203">Fügen Sie der `exit $LASTEXITCODE` Befehls Zeichenfolge oder dem Skriptblock hinzu, um den spezifischen Exitcode beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="1dab7-203">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="1dab7-204">Entsprechend wird der Wert 1 zurückgegeben, wenn ein Fehler mit Skript Abbruch (Runspace-abschließende), wie z `throw` . `-ErrorAction Stop` b. oder, auftritt oder wenn die Ausführung durch <kbd>STRG</kbd> - <kbd>C</kbd>unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="1dab7-204">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

#### <a name="-help---"></a><span data-ttu-id="1dab7-205">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="1dab7-205">-Help, -?, /?</span></span>

<span data-ttu-id="1dab7-206">Zeigt die Hilfe für **PowerShell.exe** an.</span><span class="sxs-lookup"><span data-stu-id="1dab7-206">Displays help for **PowerShell.exe**.</span></span> <span data-ttu-id="1dab7-207">Wenn Sie einen **PowerShell.exe** Befehl in einer PowerShell-Sitzung eingeben, stellen Sie den Befehlsparametern einen Bindestrich (-) und keinen Schrägstrich (/) voran.</span><span class="sxs-lookup"><span data-stu-id="1dab7-207">If you are typing a **PowerShell.exe** command in a PowerShell session, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="1dab7-208">In **cmd.exe** können Sie entweder einen Bindestrich oder einen Schrägstrich verwenden.</span><span class="sxs-lookup"><span data-stu-id="1dab7-208">You can use either a hyphen or forward slash in **cmd.exe**.</span></span>

### <a name="remarks"></a><span data-ttu-id="1dab7-209">ANMERKUNGEN</span><span class="sxs-lookup"><span data-stu-id="1dab7-209">REMARKS</span></span>

<span data-ttu-id="1dab7-210">Hinweis zur Problembehandlung: in PowerShell 2,0 tritt beim Starten einiger Programme über die PowerShell-Konsole ein Fehler mit dem **lastexitcode** "0xc0000142" auf.</span><span class="sxs-lookup"><span data-stu-id="1dab7-210">Troubleshooting note: In PowerShell 2.0, starting some programs from the PowerShell console fails with a **LastExitCode** of 0xc0000142.</span></span>

### <a name="examples"></a><span data-ttu-id="1dab7-211">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1dab7-211">EXAMPLES</span></span>

```powershell
# Create a new PowerShell session and load a saved console file
PowerShell -PSConsoleFile sqlsnapin.psc1

# Create a new PowerShell V2 session with text input, XML output, and no logo
PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

# Execute a PowerShell Command in a session
PowerShell -Command "Get-EventLog -LogName security"

# Run a script block in a session
PowerShell -Command {Get-EventLog -LogName security}

# An alternate way to run a command in a new session
PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```
