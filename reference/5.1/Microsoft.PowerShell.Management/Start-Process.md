---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: b6147b35a8818cf448b1e23f5458550d1c6e5c50
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "93219055"
---
# <span data-ttu-id="5a7b5-103">Start-Process</span><span class="sxs-lookup"><span data-stu-id="5a7b5-103">Start-Process</span></span>

## <span data-ttu-id="5a7b5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5a7b5-104">SYNOPSIS</span></span>
<span data-ttu-id="5a7b5-105">Startet Prozesse auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-105">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="5a7b5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5a7b5-106">SYNTAX</span></span>

### <span data-ttu-id="5a7b5-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="5a7b5-107">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [<CommonParameters>]
```

### <span data-ttu-id="5a7b5-108">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="5a7b5-108">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [<CommonParameters>]
```

## <span data-ttu-id="5a7b5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5a7b5-109">DESCRIPTION</span></span>

<span data-ttu-id="5a7b5-110">Mit dem- `Start-Process` Cmdlet wird mindestens ein Prozess auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-110">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="5a7b5-111">Standardmäßig wird von `Start-Process` ein neuer Prozess erstellt, der alle Umgebungsvariablen erbt, die im aktuellen Prozess definiert sind.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-111">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="5a7b5-112">Geben Sie zum Angeben des Programms, das im Prozess ausgeführt wird, eine ausführbare Datei, eine Skriptdatei oder eine Datei an, die mit einem Programm auf dem Computer geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-112">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="5a7b5-113">Wenn Sie eine nicht ausführbare Datei angeben, `Start-Process` startet das Programm, das der Datei zugeordnet ist, vergleichbar mit dem- `Invoke-Item` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-113">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="5a7b5-114">Sie können die Parameter von verwenden, `Start-Process` um Optionen anzugeben, z. b. das Laden eines Benutzerprofils, das Starten des Prozesses in einem neuen Fenster oder das Verwenden alternativer Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-114">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="5a7b5-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5a7b5-115">EXAMPLES</span></span>

### <span data-ttu-id="5a7b5-116">Beispiel 1: Starten eines Prozesses, der Standardwerte verwendet</span><span class="sxs-lookup"><span data-stu-id="5a7b5-116">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="5a7b5-117">In diesem Beispiel wird ein Prozess gestartet, der die `Sort.exe` Datei im aktuellen Ordner verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-117">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="5a7b5-118">Der Befehl verwendet alle Standardwerte, einschließlich Standardfenster Stil, Arbeitsordner und Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-118">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="5a7b5-119">Beispiel 2: Drucken einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="5a7b5-119">Example 2: Print a text file</span></span>

<span data-ttu-id="5a7b5-120">In diesem Beispiel wird ein Prozess gestartet, der die `C:\PS-Test\MyFile.txt` Datei druckt.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-120">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="5a7b5-121">Beispiel 3: Starten eines Prozesses zum Sortieren von Elementen in einer neuen Datei</span><span class="sxs-lookup"><span data-stu-id="5a7b5-121">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="5a7b5-122">In diesem Beispiel wird ein Prozess gestartet, mit dem Elemente in der Datei sortiert werden `Testsort.txt` und die sortierten Elemente in den Dateien zurückgegeben werden `Sorted.txt` .</span><span class="sxs-lookup"><span data-stu-id="5a7b5-122">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="5a7b5-123">Alle Fehler werden in die `SortError.txt` Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-123">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="5a7b5-124">Der **usenewenvironment** -Parameter gibt an, dass der Prozess mit seinen eigenen Umgebungsvariablen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-124">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="5a7b5-125">Beispiel 4: Starten eines Prozesses in einem maximierten Fenster</span><span class="sxs-lookup"><span data-stu-id="5a7b5-125">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="5a7b5-126">In diesem Beispiel wird der `Notepad.exe` Prozess gestartet.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-126">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="5a7b5-127">Das Fenster wird maximiert und beibehalten, bis der Prozess abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-127">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="5a7b5-128">Beispiel 5: Starten von PowerShell als Administrator</span><span class="sxs-lookup"><span data-stu-id="5a7b5-128">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="5a7b5-129">In diesem Beispiel wird PowerShell mit der Option **als Administrator ausführen** gestartet.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-129">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="5a7b5-130">Beispiel 6: Verwenden verschiedener Verben zum Starten eines Prozesses</span><span class="sxs-lookup"><span data-stu-id="5a7b5-130">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="5a7b5-131">Dieses Beispiel zeigt, wie Sie die Verben suchen, die beim Starten eines Prozesses verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-131">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="5a7b5-132">Die verfügbaren Verben werden durch die Dateinamenerweiterung der Datei bestimmt, die im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-132">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="5a7b5-133">Im Beispiel wird verwendet, `New-Object` um ein **System. Diagnostics. ProcessStartInfo** -Objekt für **PowerShell.exe** zu erstellen, die Datei, die im PowerShell-Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-133">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe** , the file that runs in the PowerShell process.</span></span> <span data-ttu-id="5a7b5-134">Die **Verbs** -Eigenschaft des **ProcessStartInfo** -Objekts zeigt, dass Sie die " **Open** "-und " **runas** "-Verben mit `PowerShell.exe` oder mit einem beliebigen Prozess verwenden können, der eine `.exe` Datei ausführt.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-134">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="5a7b5-135">Beispiel 7: Angeben von Argumenten für den Prozess</span><span class="sxs-lookup"><span data-stu-id="5a7b5-135">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="5a7b5-136">Beide Befehle starten den Windows-Befehls Interpreter und geben einen `dir` Befehl für den `Program Files` Ordner aus.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-136">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="5a7b5-137">Da dieser FolderName ein Leerzeichen enthält, muss der Wert mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-137">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="5a7b5-138">Beachten Sie, dass der erste Befehl eine Zeichenfolge als **argumentlist** angibt.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-138">Note that the first command specifies a string as **ArgumentList**.</span></span> <span data-ttu-id="5a7b5-139">Der zweite Befehl ist ein Zeichen folgen Array.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-139">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

## <span data-ttu-id="5a7b5-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5a7b5-140">PARAMETERS</span></span>

### <span data-ttu-id="5a7b5-141">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="5a7b5-141">-ArgumentList</span></span>

<span data-ttu-id="5a7b5-142">Gibt Parameter oder Parameterwerte an, die verwendet werden sollen, wenn dieses Cmdlet den Prozess startet.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-142">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="5a7b5-143">Argumente können als einzelne Zeichenfolge akzeptiert werden, wobei die Argumente durch Leerzeichen getrennt sind, oder als ein Array von Zeichen folgen, die durch Kommas getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-143">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="5a7b5-144">Wenn Parameter oder Parameterwerte ein Leerzeichen enthalten, müssen Sie in doppelte Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-144">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="5a7b5-145">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="5a7b5-145">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="5a7b5-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="5a7b5-146">-Credential</span></span>

<span data-ttu-id="5a7b5-147">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-147">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="5a7b5-148">Standardmäßig verwendet das Cmdlet die Anmeldeinformationen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-148">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="5a7b5-149">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-149">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="5a7b5-150">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-150">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="5a7b5-151">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-151">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="5a7b5-152">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="5a7b5-152">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="5a7b5-153">-FilePath</span><span class="sxs-lookup"><span data-stu-id="5a7b5-153">-FilePath</span></span>

<span data-ttu-id="5a7b5-154">Gibt den optionalen Pfad und den Dateinamen des Programms an, das im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-154">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="5a7b5-155">Geben Sie den Namen einer ausführbaren Datei oder eines Dokuments ein, z. b. eine-oder-Datei, die `.txt` `.doc` einem Programm auf dem Computer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-155">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="5a7b5-156">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-156">This parameter is required.</span></span>

<span data-ttu-id="5a7b5-157">Wenn Sie nur einen Dateinamen angeben, geben Sie den Pfad mithilfe des **WorkingDirectory** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-157">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5a7b5-158">-LoadUserProfile</span><span class="sxs-lookup"><span data-stu-id="5a7b5-158">-LoadUserProfile</span></span>

<span data-ttu-id="5a7b5-159">Gibt an, dass dieses Cmdlet das im `HKEY_USERS` Registrierungsschlüssel für den aktuellen Benutzer gespeicherte Windows-Benutzerprofil lädt.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-159">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span>

<span data-ttu-id="5a7b5-160">Dieser Parameter hat keine Auswirkung auf die PowerShell-Profile.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-160">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="5a7b5-161">Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5a7b5-161">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

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

### <span data-ttu-id="5a7b5-162">-Nonewwindow</span><span class="sxs-lookup"><span data-stu-id="5a7b5-162">-NoNewWindow</span></span>

<span data-ttu-id="5a7b5-163">Startet den neuen Prozess im aktuellen Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-163">Start the new process in the current console window.</span></span> <span data-ttu-id="5a7b5-164">PowerShell öffnet standardmäßig ein neues Fenster.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-164">By default PowerShell opens a new window.</span></span>

<span data-ttu-id="5a7b5-165">Der **NoNewWindow** -Parameter und der **WindowStyle** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-165">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

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

### <span data-ttu-id="5a7b5-166">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5a7b5-166">-PassThru</span></span>

<span data-ttu-id="5a7b5-167">Gibt ein Prozessobjekt für jeden Prozess zurück, der vom Cmdlet gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-167">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="5a7b5-168">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-168">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5a7b5-169">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="5a7b5-169">-RedirectStandardError</span></span>

<span data-ttu-id="5a7b5-170">Gibt eine Datei an.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-170">Specifies a file.</span></span> <span data-ttu-id="5a7b5-171">Dieses Cmdlet sendet alle Fehler, die vom Prozess generiert werden, in eine von Ihnen angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-171">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="5a7b5-172">Geben Sie den Pfad und den Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-172">Enter the path and filename.</span></span> <span data-ttu-id="5a7b5-173">Standardmäßig werden die Fehler in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-173">By default, the errors are displayed in the console.</span></span>

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

### <span data-ttu-id="5a7b5-174">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="5a7b5-174">-RedirectStandardInput</span></span>

<span data-ttu-id="5a7b5-175">Gibt eine Datei an.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-175">Specifies a file.</span></span> <span data-ttu-id="5a7b5-176">Dieses Cmdlet liest Eingaben aus der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-176">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="5a7b5-177">Geben Sie den Pfad und den Dateinamen der Eingabedatei ein.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-177">Enter the path and filename of the input file.</span></span> <span data-ttu-id="5a7b5-178">Standardmäßig ruft der Prozess die Eingabe von der Tastatur ab.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-178">By default, the process gets its input from the keyboard.</span></span>

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

### <span data-ttu-id="5a7b5-179">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="5a7b5-179">-RedirectStandardOutput</span></span>

<span data-ttu-id="5a7b5-180">Gibt eine Datei an.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-180">Specifies a file.</span></span> <span data-ttu-id="5a7b5-181">Dieses Cmdlet sendet die Ausgabe, die vom Prozess generiert wird, an eine von Ihnen angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-181">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="5a7b5-182">Geben Sie den Pfad und den Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-182">Enter the path and filename.</span></span> <span data-ttu-id="5a7b5-183">Standardmäßig wird die Ausgabe in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-183">By default, the output is displayed in the console.</span></span>

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

### <span data-ttu-id="5a7b5-184">-Usenewenvironment</span><span class="sxs-lookup"><span data-stu-id="5a7b5-184">-UseNewEnvironment</span></span>

<span data-ttu-id="5a7b5-185">Gibt an, dass dieses Cmdlet für den Prozess angegebene neue Umgebungsvariablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-185">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="5a7b5-186">Standardmäßig wird der gestartete Prozess mit den Umgebungsvariablen ausgeführt, die vom übergeordneten Prozess geerbt wurden.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-186">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

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

### <span data-ttu-id="5a7b5-187">-Verb</span><span class="sxs-lookup"><span data-stu-id="5a7b5-187">-Verb</span></span>

<span data-ttu-id="5a7b5-188">Gibt ein Verb an, das verwendet werden soll, wenn dieses Cmdlet den Prozess startet.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-188">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="5a7b5-189">Die verfügbaren Verben werden durch die Dateinamenerweiterung der Datei bestimmt, die im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-189">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="5a7b5-190">Die folgende Tabelle enthält die Verben für einige allgemeine Prozessdateitypen:</span><span class="sxs-lookup"><span data-stu-id="5a7b5-190">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="5a7b5-191">Dateityp</span><span class="sxs-lookup"><span data-stu-id="5a7b5-191">File type</span></span> |                <span data-ttu-id="5a7b5-192">Verben</span><span class="sxs-lookup"><span data-stu-id="5a7b5-192">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="5a7b5-193">.cmd</span><span class="sxs-lookup"><span data-stu-id="5a7b5-193">.cmd</span></span>      | <span data-ttu-id="5a7b5-194">Bearbeiten, öffnen, drucken, runas, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="5a7b5-194">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="5a7b5-195">.exe</span><span class="sxs-lookup"><span data-stu-id="5a7b5-195">.exe</span></span>      | <span data-ttu-id="5a7b5-196">Öffnen, runas, RunAsUser</span><span class="sxs-lookup"><span data-stu-id="5a7b5-196">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="5a7b5-197">.txt</span><span class="sxs-lookup"><span data-stu-id="5a7b5-197">.txt</span></span>      | <span data-ttu-id="5a7b5-198">Öffnen, drucken, Printto</span><span class="sxs-lookup"><span data-stu-id="5a7b5-198">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="5a7b5-199">WAV</span><span class="sxs-lookup"><span data-stu-id="5a7b5-199">.wav</span></span>      | <span data-ttu-id="5a7b5-200">Öffnen, wiedergeben</span><span class="sxs-lookup"><span data-stu-id="5a7b5-200">Open, Play</span></span>                          |

<span data-ttu-id="5a7b5-201">Verwenden Sie zum Suchen der Verben, die mit der in einem Prozess ausgeführten Datei verwendet werden können, das- `New-Object` Cmdlet, um ein **System. Diagnostics. ProcessStartInfo** -Objekt für die Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-201">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="5a7b5-202">Die verfügbaren Verben sind in der **Verbs** -Eigenschaft des **ProcessStartInfo** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-202">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="5a7b5-203">Weitere Informationen finden Sie in den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-203">For details, see the examples.</span></span>

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

### <span data-ttu-id="5a7b5-204">-Wait</span><span class="sxs-lookup"><span data-stu-id="5a7b5-204">-Wait</span></span>

<span data-ttu-id="5a7b5-205">Gibt an, dass dieses Cmdlet auf den Abschluss des angegebenen Prozesses und seiner Nachfolger wartet, bevor mehr Eingaben akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-205">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="5a7b5-206">Dieser Parameter unterdrückt die Eingabeaufforderung oder behält das Fenster bei, bis die Prozesse abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-206">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

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

### <span data-ttu-id="5a7b5-207">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="5a7b5-207">-WindowStyle</span></span>

<span data-ttu-id="5a7b5-208">Gibt den Status des für den neuen Prozess verwendeten Fensters an.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-208">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="5a7b5-209">Die zulässigen Werte für diesen Parameter sind " **Normal** ", " **ausgeblendet** ", " **minimiert** " und " **maximiert** ".</span><span class="sxs-lookup"><span data-stu-id="5a7b5-209">The acceptable values for this parameter are: **Normal** , **Hidden** , **Minimized** , and **Maximized**.</span></span> <span data-ttu-id="5a7b5-210">Der Standardwert ist " **Normal** ".</span><span class="sxs-lookup"><span data-stu-id="5a7b5-210">The default value is **Normal**.</span></span>

<span data-ttu-id="5a7b5-211">Der **WindowStyle** -Parameter und der **NoNewWindow** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-211">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

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

### <span data-ttu-id="5a7b5-212">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="5a7b5-212">-WorkingDirectory</span></span>

<span data-ttu-id="5a7b5-213">Gibt den Speicherort an, in dem der neue Prozess beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-213">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="5a7b5-214">Der Standardwert ist der Speicherort der ausführbaren Datei oder des Dokuments, das gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-214">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="5a7b5-215">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-215">Wildcards are not supported.</span></span> <span data-ttu-id="5a7b5-216">Der Pfadname darf keine Zeichen enthalten, die als Platzhalter interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-216">The path name must not contain characters that would be interpreted as wildcards.</span></span>

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

### <span data-ttu-id="5a7b5-217">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5a7b5-217">CommonParameters</span></span>

<span data-ttu-id="5a7b5-218">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5a7b5-219">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5a7b5-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5a7b5-220">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5a7b5-220">INPUTS</span></span>

### <span data-ttu-id="5a7b5-221">Keine</span><span class="sxs-lookup"><span data-stu-id="5a7b5-221">None</span></span>

<span data-ttu-id="5a7b5-222">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-222">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="5a7b5-223">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5a7b5-223">OUTPUTS</span></span>

### <span data-ttu-id="5a7b5-224">None, System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="5a7b5-224">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="5a7b5-225">Dieses Cmdlet generiert ein **System. Diagnostics. Process** -Objekt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-225">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="5a7b5-226">Andernfalls wird von diesem Cmdlet keine Ausgabe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-226">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="5a7b5-227">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5a7b5-227">NOTES</span></span>

- <span data-ttu-id="5a7b5-228">Dieses Cmdlet wird mithilfe der **Start** -Methode der **System. Diagnostics. Process** -Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-228">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="5a7b5-229">Weitere Informationen zu dieser Methode finden Sie unter [Process. Start-Methode](/dotnet/api/system.diagnostics.process.start#overloads).</span><span class="sxs-lookup"><span data-stu-id="5a7b5-229">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="5a7b5-230">Wenn Sie unter Windows **usenewenvironment** verwenden, beginnt der neue Prozess nur mit den Standard Umgebungsvariablen, die für den **Computer** Bereich definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-230">On Windows, when you use **UseNewEnvironment** , the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="5a7b5-231">Dies hat den Nebeneffekt, dass `$env:USERNAME` auf **System** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-231">This has the side affect that the `$env:USERNAME` is set to **SYSTEM**.</span></span> <span data-ttu-id="5a7b5-232">Es sind keine Variablen aus dem **Benutzer** Bereich enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a7b5-232">None of the variables from the **User** scope are included.</span></span>

## <span data-ttu-id="5a7b5-233">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5a7b5-233">RELATED LINKS</span></span>

[<span data-ttu-id="5a7b5-234">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="5a7b5-234">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="5a7b5-235">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="5a7b5-235">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="5a7b5-236">Get-Process</span><span class="sxs-lookup"><span data-stu-id="5a7b5-236">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="5a7b5-237">Start-Service</span><span class="sxs-lookup"><span data-stu-id="5a7b5-237">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="5a7b5-238">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="5a7b5-238">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="5a7b5-239">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="5a7b5-239">Wait-Process</span></span>](Wait-Process.md)
