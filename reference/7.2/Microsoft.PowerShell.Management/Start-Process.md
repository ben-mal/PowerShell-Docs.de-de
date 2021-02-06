---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: 28f343ddc6021e129d3eae007114b93ed17d5e95
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599636"
---
# <span data-ttu-id="a9cfd-102">Start-Process</span><span class="sxs-lookup"><span data-stu-id="a9cfd-102">Start-Process</span></span>

## <span data-ttu-id="a9cfd-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a9cfd-103">SYNOPSIS</span></span>
<span data-ttu-id="a9cfd-104">Startet Prozesse auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-104">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="a9cfd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a9cfd-105">SYNTAX</span></span>

### <span data-ttu-id="a9cfd-106">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="a9cfd-106">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a9cfd-107">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="a9cfd-107">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="a9cfd-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a9cfd-108">DESCRIPTION</span></span>

<span data-ttu-id="a9cfd-109">Mit dem- `Start-Process` Cmdlet wird mindestens ein Prozess auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-109">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="a9cfd-110">Standardmäßig wird von `Start-Process` ein neuer Prozess erstellt, der alle Umgebungsvariablen erbt, die im aktuellen Prozess definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-110">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="a9cfd-111">Geben Sie zum Angeben des Programms, das im Prozess ausgeführt wird, eine ausführbare Datei, eine Skriptdatei oder eine Datei an, die mit einem Programm auf dem Computer geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-111">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="a9cfd-112">Wenn Sie eine nicht ausführbare Datei angeben, `Start-Process` startet das Programm, das der Datei zugeordnet ist, vergleichbar mit dem- `Invoke-Item` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-112">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="a9cfd-113">Sie können die Parameter von verwenden, `Start-Process` um Optionen anzugeben, z. b. das Laden eines Benutzerprofils, das Starten des Prozesses in einem neuen Fenster oder das Verwenden alternativer Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-113">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="a9cfd-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a9cfd-114">EXAMPLES</span></span>

### <span data-ttu-id="a9cfd-115">Beispiel 1: Starten eines Prozesses, der Standardwerte verwendet</span><span class="sxs-lookup"><span data-stu-id="a9cfd-115">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="a9cfd-116">In diesem Beispiel wird ein Prozess gestartet, der die `Sort.exe` Datei im aktuellen Ordner verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-116">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="a9cfd-117">Der Befehl verwendet alle Standardwerte, einschließlich Standardfenster Stil, Arbeitsordner und Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-117">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="a9cfd-118">Beispiel 2: Drucken einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="a9cfd-118">Example 2: Print a text file</span></span>

<span data-ttu-id="a9cfd-119">In diesem Beispiel wird ein Prozess gestartet, der die `C:\PS-Test\MyFile.txt` Datei druckt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-119">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="a9cfd-120">Beispiel 3: Starten eines Prozesses zum Sortieren von Elementen in einer neuen Datei</span><span class="sxs-lookup"><span data-stu-id="a9cfd-120">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="a9cfd-121">In diesem Beispiel wird ein Prozess gestartet, mit dem Elemente in der Datei sortiert werden `Testsort.txt` und die sortierten Elemente in den Dateien zurückgegeben werden `Sorted.txt` .</span><span class="sxs-lookup"><span data-stu-id="a9cfd-121">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="a9cfd-122">Alle Fehler werden in die `SortError.txt` Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-122">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="a9cfd-123">Der **usenewenvironment** -Parameter gibt an, dass der Prozess mit seinen eigenen Umgebungsvariablen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-123">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="a9cfd-124">Beispiel 4: Starten eines Prozesses in einem maximierten Fenster</span><span class="sxs-lookup"><span data-stu-id="a9cfd-124">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="a9cfd-125">In diesem Beispiel wird der `Notepad.exe` Prozess gestartet.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-125">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="a9cfd-126">Das Fenster wird maximiert und beibehalten, bis der Prozess abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-126">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="a9cfd-127">Beispiel 5: Starten von PowerShell als Administrator</span><span class="sxs-lookup"><span data-stu-id="a9cfd-127">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="a9cfd-128">In diesem Beispiel wird PowerShell mit der Option **als Administrator ausführen** gestartet.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-128">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="a9cfd-129">Beispiel 6: Verwenden verschiedener Verben zum Starten eines Prozesses</span><span class="sxs-lookup"><span data-stu-id="a9cfd-129">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="a9cfd-130">Dieses Beispiel zeigt, wie Sie die Verben suchen, die beim Starten eines Prozesses verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-130">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="a9cfd-131">Die verfügbaren Verben werden durch die Dateinamenerweiterung der Datei bestimmt, die im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-131">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="a9cfd-132">Im Beispiel wird verwendet, `New-Object` um ein **System. Diagnostics. ProcessStartInfo** -Objekt für **PowerShell.exe** zu erstellen, die Datei, die im PowerShell-Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-132">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe**, the file that runs in the PowerShell process.</span></span> <span data-ttu-id="a9cfd-133">Die **Verbs** -Eigenschaft des **ProcessStartInfo** -Objekts zeigt, dass Sie die " **Open** "-und " **runas** "-Verben mit `PowerShell.exe` oder mit einem beliebigen Prozess verwenden können, der eine `.exe` Datei ausführt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-133">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="a9cfd-134">Beispiel 7: Angeben von Argumenten für den Prozess</span><span class="sxs-lookup"><span data-stu-id="a9cfd-134">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="a9cfd-135">Beide Befehle starten den Windows-Befehls Interpreter und geben einen `dir` Befehl für den `Program Files` Ordner aus.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-135">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="a9cfd-136">Da dieser FolderName ein Leerzeichen enthält, muss der Wert mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-136">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="a9cfd-137">Beachten Sie, dass der erste Befehl eine Zeichenfolge als **argumentlist** angibt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-137">Note that the first command specifies a string as **ArgumentList**.</span></span> <span data-ttu-id="a9cfd-138">Der zweite Befehl ist ein Zeichen folgen Array.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-138">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

### <span data-ttu-id="a9cfd-139">Beispiel 8: Erstellen eines getrennten Prozesses unter Linux</span><span class="sxs-lookup"><span data-stu-id="a9cfd-139">Example 8: Create a detached process on Linux</span></span>

<span data-ttu-id="a9cfd-140">Unter Windows `Start-Process` erstellt einen unabhängigen Prozess, der unabhängig von der startenden Shell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-140">On Windows, `Start-Process` creates an independent process that remains running independently of the launching shell.</span></span> <span data-ttu-id="a9cfd-141">Auf nicht-Windows-Plattformen wird der neu gestartete Prozess an die gestartete Shell angefügt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-141">On non-Windows platforms, the newly started process is attached to the shell that launched.</span></span> <span data-ttu-id="a9cfd-142">Wenn die starsshell geschlossen ist, wird der untergeordnete Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-142">If the launching shell is closed, the child process is terminated.</span></span>

<span data-ttu-id="a9cfd-143">Um zu vermeiden, dass der untergeordnete Prozess auf Unix-ähnlichen Plattformen beendet wird, können Sie mit kombinieren `Start-Process` `nohup` .</span><span class="sxs-lookup"><span data-stu-id="a9cfd-143">To avoid terminating the child process on Unix-like platforms, you can combine `Start-Process` with `nohup`.</span></span> <span data-ttu-id="a9cfd-144">Im folgenden Beispiel wird eine Hintergrund Instanz von PowerShell unter Linux gestartet, die weiterhin aktiv bleibt, auch nachdem Sie die Start Sitzung geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-144">The following example launches a background instance of PowerShell on Linux that stays alive even after you close the launching session.</span></span> <span data-ttu-id="a9cfd-145">Der `nohup` Befehl erfasst die Ausgabe in `nohup.out` der Datei im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-145">The `nohup` command collects output in file `nohup.out` in the current directory.</span></span>

```powershell
# Runs for 2 minutes and appends output to ./nohup.out
Start-Process nohup 'pwsh -noprofile -c "1..120 | % { Write-Host . -NoNewline; sleep 1 }"'
```

<span data-ttu-id="a9cfd-146">In diesem Beispiel `Start-Process` führt den Linux- `nohup` Befehl aus, der `pwsh` als getrennter Prozess gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-146">In this example, `Start-Process` is running the Linux `nohup` command, which launches `pwsh` as a detached process.</span></span> <span data-ttu-id="a9cfd-147">Weitere Informationen finden Sie auf der Seite "man" für [nohup](https://linux.die.net/man/1/nohup).</span><span class="sxs-lookup"><span data-stu-id="a9cfd-147">For more information, see the man page for [nohup](https://linux.die.net/man/1/nohup).</span></span>

## <span data-ttu-id="a9cfd-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a9cfd-148">PARAMETERS</span></span>

### <span data-ttu-id="a9cfd-149">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="a9cfd-149">-ArgumentList</span></span>

<span data-ttu-id="a9cfd-150">Gibt Parameter oder Parameterwerte an, die verwendet werden sollen, wenn dieses Cmdlet den Prozess startet.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-150">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="a9cfd-151">Argumente können als einzelne Zeichenfolge akzeptiert werden, wobei die Argumente durch Leerzeichen getrennt sind, oder als ein Array von Zeichen folgen, die durch Kommas getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-151">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="a9cfd-152">Wenn Parameter oder Parameterwerte ein Leerzeichen enthalten, müssen Sie in doppelte Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-152">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="a9cfd-153">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="a9cfd-153">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="a9cfd-154">-Credential</span><span class="sxs-lookup"><span data-stu-id="a9cfd-154">-Credential</span></span>

<span data-ttu-id="a9cfd-155">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-155">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="a9cfd-156">Standardmäßig verwendet das Cmdlet die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-156">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="a9cfd-157">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-157">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="a9cfd-158">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-158">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="a9cfd-159">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-159">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="a9cfd-160">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="a9cfd-160">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="a9cfd-161">-FilePath</span><span class="sxs-lookup"><span data-stu-id="a9cfd-161">-FilePath</span></span>

<span data-ttu-id="a9cfd-162">Gibt den optionalen Pfad und den Dateinamen des Programms an, das im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-162">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="a9cfd-163">Geben Sie den Namen einer ausführbaren Datei oder eines Dokuments ein, z. b. eine-oder-Datei, die `.txt` `.doc` einem Programm auf dem Computer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-163">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="a9cfd-164">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-164">This parameter is required.</span></span>

<span data-ttu-id="a9cfd-165">Wenn Sie nur einen Dateinamen angeben, geben Sie den Pfad mithilfe des **WorkingDirectory** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-165">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

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

### <span data-ttu-id="a9cfd-166">-LoadUserProfile</span><span class="sxs-lookup"><span data-stu-id="a9cfd-166">-LoadUserProfile</span></span>

<span data-ttu-id="a9cfd-167">Gibt an, dass dieses Cmdlet das im `HKEY_USERS` Registrierungsschlüssel für den aktuellen Benutzer gespeicherte Windows-Benutzerprofil lädt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-167">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span> <span data-ttu-id="a9cfd-168">Der-Parameter gilt nicht für nicht-Windows-Systeme.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-168">The parameter does not apply for non-Windows systems.</span></span>

<span data-ttu-id="a9cfd-169">Dieser Parameter hat keine Auswirkung auf die PowerShell-Profile.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-169">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="a9cfd-170">Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a9cfd-170">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

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

### <span data-ttu-id="a9cfd-171">-Nonewwindow</span><span class="sxs-lookup"><span data-stu-id="a9cfd-171">-NoNewWindow</span></span>

<span data-ttu-id="a9cfd-172">Startet den neuen Prozess im aktuellen Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-172">Start the new process in the current console window.</span></span> <span data-ttu-id="a9cfd-173">In Windows wird PowerShell standardmäßig ein neues Fenster öffnen.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-173">By default on Windows, PowerShell opens a new window.</span></span> <span data-ttu-id="a9cfd-174">Auf nicht-Windows-Systemen erhalten Sie niemals ein neues Terminalfenster.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-174">On non-Windows systems, you never get a new terminal window.</span></span>

<span data-ttu-id="a9cfd-175">Der **NoNewWindow**-Parameter und der **WindowStyle**-Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-175">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

<span data-ttu-id="a9cfd-176">Der-Parameter gilt nicht für nicht-Windows-Systeme.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-176">The parameter does not apply for non-Windows systems.</span></span>

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

### <span data-ttu-id="a9cfd-177">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a9cfd-177">-PassThru</span></span>

<span data-ttu-id="a9cfd-178">Gibt ein Prozessobjekt für jeden Prozess zurück, der vom Cmdlet gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-178">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="a9cfd-179">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-179">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a9cfd-180">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="a9cfd-180">-RedirectStandardError</span></span>

<span data-ttu-id="a9cfd-181">Gibt eine Datei an.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-181">Specifies a file.</span></span> <span data-ttu-id="a9cfd-182">Dieses Cmdlet sendet alle Fehler, die vom Prozess generiert werden, in eine von Ihnen angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-182">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="a9cfd-183">Geben Sie den Pfad und den Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-183">Enter the path and filename.</span></span> <span data-ttu-id="a9cfd-184">Standardmäßig werden die Fehler in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-184">By default, the errors are displayed in the console.</span></span>

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

### <span data-ttu-id="a9cfd-185">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="a9cfd-185">-RedirectStandardInput</span></span>

<span data-ttu-id="a9cfd-186">Gibt eine Datei an.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-186">Specifies a file.</span></span> <span data-ttu-id="a9cfd-187">Dieses Cmdlet liest Eingaben aus der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-187">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="a9cfd-188">Geben Sie den Pfad und den Dateinamen der Eingabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-188">Enter the path and filename of the input file.</span></span> <span data-ttu-id="a9cfd-189">Standardmäßig ruft der Prozess die Eingabe von der Tastatur ab.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-189">By default, the process gets its input from the keyboard.</span></span>

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

### <span data-ttu-id="a9cfd-190">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="a9cfd-190">-RedirectStandardOutput</span></span>

<span data-ttu-id="a9cfd-191">Gibt eine Datei an.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-191">Specifies a file.</span></span> <span data-ttu-id="a9cfd-192">Dieses Cmdlet sendet die Ausgabe, die vom Prozess generiert wird, an eine von Ihnen angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-192">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="a9cfd-193">Geben Sie den Pfad und den Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-193">Enter the path and filename.</span></span> <span data-ttu-id="a9cfd-194">Standardmäßig wird die Ausgabe in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-194">By default, the output is displayed in the console.</span></span>

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

### <span data-ttu-id="a9cfd-195">-Usenewenvironment</span><span class="sxs-lookup"><span data-stu-id="a9cfd-195">-UseNewEnvironment</span></span>

<span data-ttu-id="a9cfd-196">Gibt an, dass dieses Cmdlet für den Prozess angegebene neue Umgebungsvariablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-196">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="a9cfd-197">Standardmäßig wird der gestartete Prozess mit den Umgebungsvariablen ausgeführt, die vom übergeordneten Prozess geerbt wurden.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-197">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

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

### <span data-ttu-id="a9cfd-198">-Verb</span><span class="sxs-lookup"><span data-stu-id="a9cfd-198">-Verb</span></span>

<span data-ttu-id="a9cfd-199">Gibt ein Verb an, das verwendet werden soll, wenn dieses Cmdlet den Prozess startet.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-199">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="a9cfd-200">Die verfügbaren Verben werden durch die Dateinamenerweiterung der Datei bestimmt, die im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-200">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="a9cfd-201">Die folgende Tabelle enthält die Verben für einige allgemeine Prozessdateitypen:</span><span class="sxs-lookup"><span data-stu-id="a9cfd-201">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="a9cfd-202">Dateityp</span><span class="sxs-lookup"><span data-stu-id="a9cfd-202">File type</span></span> |                <span data-ttu-id="a9cfd-203">Verben</span><span class="sxs-lookup"><span data-stu-id="a9cfd-203">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="a9cfd-204">.cmd</span><span class="sxs-lookup"><span data-stu-id="a9cfd-204">.cmd</span></span>      | <span data-ttu-id="a9cfd-205">Bearbeiten, öffnen, drucken, runas, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="a9cfd-205">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="a9cfd-206">.exe</span><span class="sxs-lookup"><span data-stu-id="a9cfd-206">.exe</span></span>      | <span data-ttu-id="a9cfd-207">Öffnen, runas, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="a9cfd-207">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="a9cfd-208">.txt</span><span class="sxs-lookup"><span data-stu-id="a9cfd-208">.txt</span></span>      | <span data-ttu-id="a9cfd-209">Öffnen, drucken, Printto</span><span class="sxs-lookup"><span data-stu-id="a9cfd-209">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="a9cfd-210">WAV</span><span class="sxs-lookup"><span data-stu-id="a9cfd-210">.wav</span></span>      | <span data-ttu-id="a9cfd-211">Öffnen, wiedergeben</span><span class="sxs-lookup"><span data-stu-id="a9cfd-211">Open, Play</span></span>                          |

<span data-ttu-id="a9cfd-212">Verwenden Sie zum Suchen der Verben, die mit der in einem Prozess ausgeführten Datei verwendet werden können, das- `New-Object` Cmdlet, um ein **System. Diagnostics. ProcessStartInfo** -Objekt für die Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-212">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="a9cfd-213">Die verfügbaren Verben sind in der **Verbs** -Eigenschaft des **ProcessStartInfo** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-213">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="a9cfd-214">Weitere Informationen finden Sie in den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-214">For details, see the examples.</span></span>

<span data-ttu-id="a9cfd-215">Der-Parameter gilt nicht für nicht-Windows-Systeme.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-215">The parameter does not apply for non-Windows systems.</span></span>

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

### <span data-ttu-id="a9cfd-216">-Wait</span><span class="sxs-lookup"><span data-stu-id="a9cfd-216">-Wait</span></span>

<span data-ttu-id="a9cfd-217">Gibt an, dass dieses Cmdlet auf den Abschluss des angegebenen Prozesses und seiner Nachfolger wartet, bevor mehr Eingaben akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-217">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="a9cfd-218">Dieser Parameter unterdrückt die Eingabeaufforderung oder behält das Fenster bei, bis die Prozesse abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-218">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

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

### <span data-ttu-id="a9cfd-219">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="a9cfd-219">-WindowStyle</span></span>

<span data-ttu-id="a9cfd-220">Gibt den Status des für den neuen Prozess verwendeten Fensters an.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-220">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="a9cfd-221">Die zulässigen Werte für diesen Parameter sind " **Normal**", " **ausgeblendet**", " **minimiert**" und " **maximiert**".</span><span class="sxs-lookup"><span data-stu-id="a9cfd-221">The acceptable values for this parameter are: **Normal**, **Hidden**, **Minimized**, and **Maximized**.</span></span> <span data-ttu-id="a9cfd-222">Der Standardwert ist " **Normal**".</span><span class="sxs-lookup"><span data-stu-id="a9cfd-222">The default value is **Normal**.</span></span>

<span data-ttu-id="a9cfd-223">Der **WindowStyle**-Parameter und der **NoNewWindow**-Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-223">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

<span data-ttu-id="a9cfd-224">Der-Parameter gilt nicht für nicht-Windows-Systeme.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-224">The parameter does not apply for non-Windows systems.</span></span>

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

### <span data-ttu-id="a9cfd-225">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="a9cfd-225">-WorkingDirectory</span></span>

<span data-ttu-id="a9cfd-226">Gibt den Speicherort an, in dem der neue Prozess beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-226">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="a9cfd-227">Der Standardwert ist der Speicherort der ausführbaren Datei oder des Dokuments, das gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-227">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="a9cfd-228">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-228">Wildcards are not supported.</span></span> <span data-ttu-id="a9cfd-229">Der Pfadname darf keine Zeichen enthalten, die als Platzhalter interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-229">The path name must not contain characters that would be interpreted as wildcards.</span></span>

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

### <span data-ttu-id="a9cfd-230">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a9cfd-230">-Confirm</span></span>

<span data-ttu-id="a9cfd-231">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-231">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a9cfd-232">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a9cfd-232">-WhatIf</span></span>

<span data-ttu-id="a9cfd-233">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-233">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a9cfd-234">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-234">The cmdlet is not run.</span></span>

<span data-ttu-id="a9cfd-235">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-235">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="a9cfd-236">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a9cfd-236">CommonParameters</span></span>

<span data-ttu-id="a9cfd-237">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-237">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a9cfd-238">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a9cfd-238">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a9cfd-239">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a9cfd-239">INPUTS</span></span>

### <span data-ttu-id="a9cfd-240">Keine</span><span class="sxs-lookup"><span data-stu-id="a9cfd-240">None</span></span>

<span data-ttu-id="a9cfd-241">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-241">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a9cfd-242">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a9cfd-242">OUTPUTS</span></span>

### <span data-ttu-id="a9cfd-243">None, System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="a9cfd-243">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="a9cfd-244">Dieses Cmdlet generiert ein **System. Diagnostics. Process** -Objekt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-244">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="a9cfd-245">Andernfalls wird von diesem Cmdlet keine Ausgabe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-245">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="a9cfd-246">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a9cfd-246">NOTES</span></span>

- <span data-ttu-id="a9cfd-247">Dieses Cmdlet wird mithilfe der **Start** -Methode der **System. Diagnostics. Process** -Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-247">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="a9cfd-248">Weitere Informationen zu dieser Methode finden Sie unter [Process. Start-Methode](/dotnet/api/system.diagnostics.process.start#overloads).</span><span class="sxs-lookup"><span data-stu-id="a9cfd-248">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="a9cfd-249">Wenn Sie unter Windows **usenewenvironment** verwenden, beginnt der neue Prozess nur mit den Standard Umgebungsvariablen, die für den **Computer** Bereich definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-249">On Windows, when you use **UseNewEnvironment**, the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="a9cfd-250">Dies hat den Nebeneffekt, dass `$env:USERNAME` auf **System** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-250">This has the side affect that the `$env:USERNAME` is set to **SYSTEM**.</span></span> <span data-ttu-id="a9cfd-251">Es sind keine Variablen aus dem **Benutzer** Bereich enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-251">None of the variables from the **User** scope are included.</span></span>

- <span data-ttu-id="a9cfd-252">Unter Windows ist der häufigste Anwendungsfall, wenn `Start-Process` der **Wait** -Parameter verwendet wird, um den Fortschritt zu blockieren, bis der neue Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-252">On Windows, the most common use case for `Start-Process` is to use the **Wait** parameter to block progress until the new process exits.</span></span> <span data-ttu-id="a9cfd-253">Bei nicht-Windows-Systemen ist dies nur selten erforderlich, da das Standardverhalten für Befehlszeilen Anwendungen entspricht `Start-Process -Wait` .</span><span class="sxs-lookup"><span data-stu-id="a9cfd-253">On non-Windows system, this is rarely needed since the default behavior for command-line applications is equivalent to `Start-Process -Wait`.</span></span>

- <span data-ttu-id="a9cfd-254">Wenn `Start-Process` Sie auf nicht-Windows-Systemen verwenden, erhalten Sie niemals ein neues Terminalfenster.</span><span class="sxs-lookup"><span data-stu-id="a9cfd-254">When using `Start-Process` on non-Windows systems, you never get a new terminal window.</span></span>

## <span data-ttu-id="a9cfd-255">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a9cfd-255">RELATED LINKS</span></span>

[<span data-ttu-id="a9cfd-256">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="a9cfd-256">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="a9cfd-257">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="a9cfd-257">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="a9cfd-258">Get-Process</span><span class="sxs-lookup"><span data-stu-id="a9cfd-258">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="a9cfd-259">Start-Service</span><span class="sxs-lookup"><span data-stu-id="a9cfd-259">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="a9cfd-260">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="a9cfd-260">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="a9cfd-261">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="a9cfd-261">Wait-Process</span></span>](Wait-Process.md)
