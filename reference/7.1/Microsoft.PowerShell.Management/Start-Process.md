---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: ade80115f85cb241fdf0dc4e829daa5b381644ef
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "93219087"
---
# <span data-ttu-id="1a8ea-103">Start-Process</span><span class="sxs-lookup"><span data-stu-id="1a8ea-103">Start-Process</span></span>

## <span data-ttu-id="1a8ea-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1a8ea-104">SYNOPSIS</span></span>
<span data-ttu-id="1a8ea-105">Startet Prozesse auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-105">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="1a8ea-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1a8ea-106">SYNTAX</span></span>

### <span data-ttu-id="1a8ea-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="1a8ea-107">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1a8ea-108">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="1a8ea-108">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="1a8ea-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1a8ea-109">DESCRIPTION</span></span>

<span data-ttu-id="1a8ea-110">Mit dem- `Start-Process` Cmdlet wird mindestens ein Prozess auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-110">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="1a8ea-111">Standardmäßig wird von `Start-Process` ein neuer Prozess erstellt, der alle Umgebungsvariablen erbt, die im aktuellen Prozess definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-111">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="1a8ea-112">Geben Sie zum Angeben des Programms, das im Prozess ausgeführt wird, eine ausführbare Datei, eine Skriptdatei oder eine Datei an, die mit einem Programm auf dem Computer geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-112">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="1a8ea-113">Wenn Sie eine nicht ausführbare Datei angeben, `Start-Process` startet das Programm, das der Datei zugeordnet ist, vergleichbar mit dem- `Invoke-Item` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-113">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="1a8ea-114">Sie können die Parameter von verwenden, `Start-Process` um Optionen anzugeben, z. b. das Laden eines Benutzerprofils, das Starten des Prozesses in einem neuen Fenster oder das Verwenden alternativer Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-114">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="1a8ea-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1a8ea-115">EXAMPLES</span></span>

### <span data-ttu-id="1a8ea-116">Beispiel 1: Starten eines Prozesses, der Standardwerte verwendet</span><span class="sxs-lookup"><span data-stu-id="1a8ea-116">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="1a8ea-117">In diesem Beispiel wird ein Prozess gestartet, der die `Sort.exe` Datei im aktuellen Ordner verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-117">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="1a8ea-118">Der Befehl verwendet alle Standardwerte, einschließlich Standardfenster Stil, Arbeitsordner und Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-118">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="1a8ea-119">Beispiel 2: Drucken einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="1a8ea-119">Example 2: Print a text file</span></span>

<span data-ttu-id="1a8ea-120">In diesem Beispiel wird ein Prozess gestartet, der die `C:\PS-Test\MyFile.txt` Datei druckt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-120">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="1a8ea-121">Beispiel 3: Starten eines Prozesses zum Sortieren von Elementen in einer neuen Datei</span><span class="sxs-lookup"><span data-stu-id="1a8ea-121">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="1a8ea-122">In diesem Beispiel wird ein Prozess gestartet, mit dem Elemente in der Datei sortiert werden `Testsort.txt` und die sortierten Elemente in den Dateien zurückgegeben werden `Sorted.txt` .</span><span class="sxs-lookup"><span data-stu-id="1a8ea-122">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="1a8ea-123">Alle Fehler werden in die `SortError.txt` Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-123">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="1a8ea-124">Der **usenewenvironment** -Parameter gibt an, dass der Prozess mit seinen eigenen Umgebungsvariablen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-124">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="1a8ea-125">Beispiel 4: Starten eines Prozesses in einem maximierten Fenster</span><span class="sxs-lookup"><span data-stu-id="1a8ea-125">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="1a8ea-126">In diesem Beispiel wird der `Notepad.exe` Prozess gestartet.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-126">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="1a8ea-127">Das Fenster wird maximiert und beibehalten, bis der Prozess abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-127">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="1a8ea-128">Beispiel 5: Starten von PowerShell als Administrator</span><span class="sxs-lookup"><span data-stu-id="1a8ea-128">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="1a8ea-129">In diesem Beispiel wird PowerShell mit der Option **als Administrator ausführen** gestartet.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-129">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="1a8ea-130">Beispiel 6: Verwenden verschiedener Verben zum Starten eines Prozesses</span><span class="sxs-lookup"><span data-stu-id="1a8ea-130">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="1a8ea-131">Dieses Beispiel zeigt, wie Sie die Verben suchen, die beim Starten eines Prozesses verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-131">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="1a8ea-132">Die verfügbaren Verben werden durch die Dateinamenerweiterung der Datei bestimmt, die im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-132">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="1a8ea-133">Im Beispiel wird verwendet, `New-Object` um ein **System. Diagnostics. ProcessStartInfo** -Objekt für **PowerShell.exe** zu erstellen, die Datei, die im PowerShell-Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-133">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe** , the file that runs in the PowerShell process.</span></span> <span data-ttu-id="1a8ea-134">Die **Verbs** -Eigenschaft des **ProcessStartInfo** -Objekts zeigt, dass Sie die " **Open** "-und " **runas** "-Verben mit `PowerShell.exe` oder mit einem beliebigen Prozess verwenden können, der eine `.exe` Datei ausführt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-134">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="1a8ea-135">Beispiel 7: Angeben von Argumenten für den Prozess</span><span class="sxs-lookup"><span data-stu-id="1a8ea-135">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="1a8ea-136">Beide Befehle starten den Windows-Befehls Interpreter und geben einen `dir` Befehl für den `Program Files` Ordner aus.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-136">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="1a8ea-137">Da dieser FolderName ein Leerzeichen enthält, muss der Wert mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-137">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="1a8ea-138">Beachten Sie, dass der erste Befehl eine Zeichenfolge als **argumentlist** angibt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-138">Note that the first command specifies a string as **ArgumentList**.</span></span> <span data-ttu-id="1a8ea-139">Der zweite Befehl ist ein Zeichen folgen Array.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-139">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

## <span data-ttu-id="1a8ea-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1a8ea-140">PARAMETERS</span></span>

### <span data-ttu-id="1a8ea-141">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="1a8ea-141">-ArgumentList</span></span>

<span data-ttu-id="1a8ea-142">Gibt Parameter oder Parameterwerte an, die verwendet werden sollen, wenn dieses Cmdlet den Prozess startet.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-142">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="1a8ea-143">Argumente können als einzelne Zeichenfolge akzeptiert werden, wobei die Argumente durch Leerzeichen getrennt sind, oder als ein Array von Zeichen folgen, die durch Kommas getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-143">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="1a8ea-144">Wenn Parameter oder Parameterwerte ein Leerzeichen enthalten, müssen Sie in doppelte Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-144">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="1a8ea-145">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="1a8ea-145">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="1a8ea-146">-Credential</span></span>

<span data-ttu-id="1a8ea-147">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-147">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="1a8ea-148">Standardmäßig verwendet das Cmdlet die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-148">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="1a8ea-149">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-149">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="1a8ea-150">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-150">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="1a8ea-151">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-151">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="1a8ea-152">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="1a8ea-152">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Default
Aliases: RunAs

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-153">-FilePath</span><span class="sxs-lookup"><span data-stu-id="1a8ea-153">-FilePath</span></span>

<span data-ttu-id="1a8ea-154">Gibt den optionalen Pfad und den Dateinamen des Programms an, das im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-154">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="1a8ea-155">Geben Sie den Namen einer ausführbaren Datei oder eines Dokuments ein, z. b. eine-oder-Datei, die `.txt` `.doc` einem Programm auf dem Computer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-155">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="1a8ea-156">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-156">This parameter is required.</span></span>

<span data-ttu-id="1a8ea-157">Wenn Sie nur einen Dateinamen angeben, geben Sie den Pfad mithilfe des **WorkingDirectory** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-157">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-158">-LoadUserProfile</span><span class="sxs-lookup"><span data-stu-id="1a8ea-158">-LoadUserProfile</span></span>

<span data-ttu-id="1a8ea-159">Gibt an, dass dieses Cmdlet das im `HKEY_USERS` Registrierungsschlüssel für den aktuellen Benutzer gespeicherte Windows-Benutzerprofil lädt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-159">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span> <span data-ttu-id="1a8ea-160">Der-Parameter gilt nicht für nicht-Windows-Systeme.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-160">The parameter does not apply for non-Windows systems.</span></span>

<span data-ttu-id="1a8ea-161">Dieser Parameter hat keine Auswirkung auf die PowerShell-Profile.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-161">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="1a8ea-162">Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1a8ea-162">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: Lup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-163">-Nonewwindow</span><span class="sxs-lookup"><span data-stu-id="1a8ea-163">-NoNewWindow</span></span>

<span data-ttu-id="1a8ea-164">Startet den neuen Prozess im aktuellen Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-164">Start the new process in the current console window.</span></span> <span data-ttu-id="1a8ea-165">In Windows wird PowerShell standardmäßig ein neues Fenster öffnen.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-165">By default on Windows, PowerShell opens a new window.</span></span> <span data-ttu-id="1a8ea-166">Auf nicht-Windows-Systemen erhalten Sie niemals ein neues Terminalfenster.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-166">On non-Windows systems, you never get a new terminal window.</span></span>

<span data-ttu-id="1a8ea-167">Der **NoNewWindow** -Parameter und der **WindowStyle** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-167">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

<span data-ttu-id="1a8ea-168">Der-Parameter gilt nicht für nicht-Windows-Systeme.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-168">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: nnw

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-169">-PassThru</span><span class="sxs-lookup"><span data-stu-id="1a8ea-169">-PassThru</span></span>

<span data-ttu-id="1a8ea-170">Gibt ein Prozessobjekt für jeden Prozess zurück, der vom Cmdlet gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-170">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="1a8ea-171">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-171">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="1a8ea-172">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="1a8ea-172">-RedirectStandardError</span></span>

<span data-ttu-id="1a8ea-173">Gibt eine Datei an.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-173">Specifies a file.</span></span> <span data-ttu-id="1a8ea-174">Dieses Cmdlet sendet alle Fehler, die vom Prozess generiert werden, in eine von Ihnen angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-174">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="1a8ea-175">Geben Sie den Pfad und den Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-175">Enter the path and filename.</span></span> <span data-ttu-id="1a8ea-176">Standardmäßig werden die Fehler in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-176">By default, the errors are displayed in the console.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-177">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="1a8ea-177">-RedirectStandardInput</span></span>

<span data-ttu-id="1a8ea-178">Gibt eine Datei an.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-178">Specifies a file.</span></span> <span data-ttu-id="1a8ea-179">Dieses Cmdlet liest Eingaben aus der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-179">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="1a8ea-180">Geben Sie den Pfad und den Dateinamen der Eingabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-180">Enter the path and filename of the input file.</span></span> <span data-ttu-id="1a8ea-181">Standardmäßig ruft der Prozess die Eingabe von der Tastatur ab.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-181">By default, the process gets its input from the keyboard.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-182">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="1a8ea-182">-RedirectStandardOutput</span></span>

<span data-ttu-id="1a8ea-183">Gibt eine Datei an.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-183">Specifies a file.</span></span> <span data-ttu-id="1a8ea-184">Dieses Cmdlet sendet die Ausgabe, die vom Prozess generiert wird, an eine von Ihnen angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-184">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="1a8ea-185">Geben Sie den Pfad und den Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-185">Enter the path and filename.</span></span> <span data-ttu-id="1a8ea-186">Standardmäßig wird die Ausgabe in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-186">By default, the output is displayed in the console.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-187">-Usenewenvironment</span><span class="sxs-lookup"><span data-stu-id="1a8ea-187">-UseNewEnvironment</span></span>

<span data-ttu-id="1a8ea-188">Gibt an, dass dieses Cmdlet für den Prozess angegebene neue Umgebungsvariablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-188">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="1a8ea-189">Standardmäßig wird der gestartete Prozess mit den Umgebungsvariablen ausgeführt, die vom übergeordneten Prozess geerbt wurden.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-189">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-190">-Verb</span><span class="sxs-lookup"><span data-stu-id="1a8ea-190">-Verb</span></span>

<span data-ttu-id="1a8ea-191">Gibt ein Verb an, das verwendet werden soll, wenn dieses Cmdlet den Prozess startet.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-191">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="1a8ea-192">Die verfügbaren Verben werden durch die Dateinamenerweiterung der Datei bestimmt, die im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-192">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="1a8ea-193">Die folgende Tabelle enthält die Verben für einige allgemeine Prozessdateitypen:</span><span class="sxs-lookup"><span data-stu-id="1a8ea-193">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="1a8ea-194">Dateityp</span><span class="sxs-lookup"><span data-stu-id="1a8ea-194">File type</span></span> |                <span data-ttu-id="1a8ea-195">Verben</span><span class="sxs-lookup"><span data-stu-id="1a8ea-195">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="1a8ea-196">.cmd</span><span class="sxs-lookup"><span data-stu-id="1a8ea-196">.cmd</span></span>      | <span data-ttu-id="1a8ea-197">Bearbeiten, öffnen, drucken, runas, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="1a8ea-197">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="1a8ea-198">.exe</span><span class="sxs-lookup"><span data-stu-id="1a8ea-198">.exe</span></span>      | <span data-ttu-id="1a8ea-199">Öffnen, runas, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="1a8ea-199">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="1a8ea-200">.txt</span><span class="sxs-lookup"><span data-stu-id="1a8ea-200">.txt</span></span>      | <span data-ttu-id="1a8ea-201">Öffnen, drucken, Printto</span><span class="sxs-lookup"><span data-stu-id="1a8ea-201">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="1a8ea-202">WAV</span><span class="sxs-lookup"><span data-stu-id="1a8ea-202">.wav</span></span>      | <span data-ttu-id="1a8ea-203">Öffnen, wiedergeben</span><span class="sxs-lookup"><span data-stu-id="1a8ea-203">Open, Play</span></span>                          |

<span data-ttu-id="1a8ea-204">Verwenden Sie zum Suchen der Verben, die mit der in einem Prozess ausgeführten Datei verwendet werden können, das- `New-Object` Cmdlet, um ein **System. Diagnostics. ProcessStartInfo** -Objekt für die Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-204">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="1a8ea-205">Die verfügbaren Verben sind in der **Verbs** -Eigenschaft des **ProcessStartInfo** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-205">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="1a8ea-206">Weitere Informationen finden Sie in den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-206">For details, see the examples.</span></span>

<span data-ttu-id="1a8ea-207">Der-Parameter gilt nicht für nicht-Windows-Systeme.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-207">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.String
Parameter Sets: UseShellExecute
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-208">-Wait</span><span class="sxs-lookup"><span data-stu-id="1a8ea-208">-Wait</span></span>

<span data-ttu-id="1a8ea-209">Gibt an, dass dieses Cmdlet auf den Abschluss des angegebenen Prozesses und seiner Nachfolger wartet, bevor mehr Eingaben akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-209">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="1a8ea-210">Dieser Parameter unterdrückt die Eingabeaufforderung oder behält das Fenster bei, bis die Prozesse abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-210">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

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

### <span data-ttu-id="1a8ea-211">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="1a8ea-211">-WindowStyle</span></span>

<span data-ttu-id="1a8ea-212">Gibt den Status des für den neuen Prozess verwendeten Fensters an.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-212">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="1a8ea-213">Die zulässigen Werte für diesen Parameter sind " **Normal** ", " **ausgeblendet** ", " **minimiert** " und " **maximiert** ".</span><span class="sxs-lookup"><span data-stu-id="1a8ea-213">The acceptable values for this parameter are: **Normal** , **Hidden** , **Minimized** , and **Maximized**.</span></span> <span data-ttu-id="1a8ea-214">Der Standardwert ist " **Normal** ".</span><span class="sxs-lookup"><span data-stu-id="1a8ea-214">The default value is **Normal**.</span></span>

<span data-ttu-id="1a8ea-215">Der **WindowStyle** -Parameter und der **NoNewWindow** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-215">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

<span data-ttu-id="1a8ea-216">Der-Parameter gilt nicht für nicht-Windows-Systeme.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-216">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.Diagnostics.ProcessWindowStyle
Parameter Sets: (All)
Aliases:
Accepted values: Normal, Hidden, Minimized, Maximized

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-217">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="1a8ea-217">-WorkingDirectory</span></span>

<span data-ttu-id="1a8ea-218">Gibt den Speicherort an, in dem der neue Prozess beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-218">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="1a8ea-219">Der Standardwert ist der Speicherort der ausführbaren Datei oder des Dokuments, das gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-219">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="1a8ea-220">Der angegebene Pfad wird als literalpfad behandelt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-220">The path provided is treated as a literal path.</span></span> <span data-ttu-id="1a8ea-221">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-221">Wildcards are not supported.</span></span> <span data-ttu-id="1a8ea-222">Sie müssen den Pfad in einfache Anführungszeichen ( `'` ) einschließen, wenn der Pfadname Zeichen enthält, die als Platzhalter interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-222">You must enclose the path in single quotes (`'`) if the path name contains characters that would be interpreted as wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-223">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1a8ea-223">-Confirm</span></span>

<span data-ttu-id="1a8ea-224">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-224">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-225">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1a8ea-225">-WhatIf</span></span>

<span data-ttu-id="1a8ea-226">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-226">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1a8ea-227">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-227">The cmdlet is not run.</span></span>

<span data-ttu-id="1a8ea-228">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-228">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a8ea-229">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1a8ea-229">CommonParameters</span></span>

<span data-ttu-id="1a8ea-230">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1a8ea-231">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1a8ea-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1a8ea-232">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1a8ea-232">INPUTS</span></span>

### <span data-ttu-id="1a8ea-233">Keine</span><span class="sxs-lookup"><span data-stu-id="1a8ea-233">None</span></span>

<span data-ttu-id="1a8ea-234">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-234">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="1a8ea-235">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1a8ea-235">OUTPUTS</span></span>

### <span data-ttu-id="1a8ea-236">None, System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="1a8ea-236">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="1a8ea-237">Dieses Cmdlet generiert ein **System. Diagnostics. Process** -Objekt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-237">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="1a8ea-238">Andernfalls wird von diesem Cmdlet keine Ausgabe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-238">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="1a8ea-239">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1a8ea-239">NOTES</span></span>

- <span data-ttu-id="1a8ea-240">Dieses Cmdlet wird mithilfe der **Start** -Methode der **System. Diagnostics. Process** -Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-240">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="1a8ea-241">Weitere Informationen zu dieser Methode finden Sie unter [Process. Start-Methode](/dotnet/api/system.diagnostics.process.start#overloads).</span><span class="sxs-lookup"><span data-stu-id="1a8ea-241">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="1a8ea-242">Wenn Sie unter Windows **usenewenvironment** verwenden, beginnt der neue Prozess nur mit den Standard Umgebungsvariablen, die für den **Computer** Bereich definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-242">On Windows, when you use **UseNewEnvironment** , the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="1a8ea-243">Dies hat den Nebeneffekt, dass `$env:USERNAME` auf **System** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-243">This has the side affect that the `$env:USERNAME` is set to **SYSTEM**.</span></span> <span data-ttu-id="1a8ea-244">Es sind keine Variablen aus dem **Benutzer** Bereich enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-244">None of the variables from the **User** scope are included.</span></span>

- <span data-ttu-id="1a8ea-245">Unter Windows ist der häufigste Anwendungsfall, wenn `Start-Process` der **Wait** -Parameter verwendet wird, um den Fortschritt zu blockieren, bis der neue Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-245">On Windows, the most common use case for `Start-Process` is to use the **Wait** parameter to block progress until the new process exits.</span></span> <span data-ttu-id="1a8ea-246">Bei nicht-Windows-Systemen ist dies nur selten erforderlich, da das Standardverhalten für Befehlszeilen Anwendungen entspricht `Start-Process -Wait` .</span><span class="sxs-lookup"><span data-stu-id="1a8ea-246">On non-Windows system, this is rarely needed since the default behavior for command-line applications is equivalent to `Start-Process -Wait`.</span></span>

- <span data-ttu-id="1a8ea-247">Wenn `Start-Process` Sie auf nicht-Windows-Systemen verwenden, erhalten Sie niemals ein neues Terminalfenster.</span><span class="sxs-lookup"><span data-stu-id="1a8ea-247">When using `Start-Process` on non-Windows systems, you never get a new terminal window.</span></span>

## <span data-ttu-id="1a8ea-248">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1a8ea-248">RELATED LINKS</span></span>

[<span data-ttu-id="1a8ea-249">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="1a8ea-249">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="1a8ea-250">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="1a8ea-250">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="1a8ea-251">Get-Process</span><span class="sxs-lookup"><span data-stu-id="1a8ea-251">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="1a8ea-252">Start-Service</span><span class="sxs-lookup"><span data-stu-id="1a8ea-252">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="1a8ea-253">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="1a8ea-253">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="1a8ea-254">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="1a8ea-254">Wait-Process</span></span>](Wait-Process.md)
