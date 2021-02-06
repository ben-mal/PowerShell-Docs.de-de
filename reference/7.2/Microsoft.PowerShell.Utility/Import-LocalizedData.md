---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-localizeddata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-LocalizedData
ms.openlocfilehash: fa5de857b70ec05d30c42fbf8e51a9411d823018
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600492"
---
# <span data-ttu-id="983fc-102">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="983fc-102">Import-LocalizedData</span></span>

## <span data-ttu-id="983fc-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="983fc-103">SYNOPSIS</span></span>
<span data-ttu-id="983fc-104">Importiert sprachspezifische Daten in Skripts und Funktionen, basierend auf der Benutzeroberflächenkultur, die für das Betriebssystem ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="983fc-104">Imports language-specific data into scripts and functions based on the UI culture that is selected for the operating system.</span></span>

## <span data-ttu-id="983fc-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="983fc-105">SYNTAX</span></span>

```
Import-LocalizedData [[-BindingVariable] <String>] [[-UICulture] <String>] [-BaseDirectory <String>]
 [-FileName <String>] [-SupportedCommand <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="983fc-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="983fc-106">DESCRIPTION</span></span>

<span data-ttu-id="983fc-107">Mit dem- `Import-LocalizedData` Cmdlet werden Zeichen folgen dynamisch aus einem Unterverzeichnis abgerufen, dessen Name mit der Benutzeroberflächen Sprache übereinstimmt, die für den aktuellen Benutzer des Betriebssystems festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="983fc-107">The `Import-LocalizedData` cmdlet dynamically retrieves strings from a subdirectory whose name matches the UI language set for the current user of the operating system.</span></span> <span data-ttu-id="983fc-108">Es dient der Aktivierung von Skripts, um Benutzermeldungen in der vom aktuellen Benutzer ausgewählten Benutzeroberflächensprache anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="983fc-108">It is designed to enable scripts to display user messages in the UI language selected by the current user.</span></span>

<span data-ttu-id="983fc-109">`Import-LocalizedData` importiert Daten aus `.psd1` Dateien in sprachspezifischen Unterverzeichnissen des Skript Verzeichnisses und speichert Sie in einer lokalen Variablen, die im Befehl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="983fc-109">`Import-LocalizedData` imports data from `.psd1` files in language-specific subdirectories of the script directory and saves them in a local variable that is specified in the command.</span></span> <span data-ttu-id="983fc-110">Das-Cmdlet wählt das Unterverzeichnis und die Datei basierend auf dem Wert der `$PSUICulture` automatischen Variablen aus.</span><span class="sxs-lookup"><span data-stu-id="983fc-110">The cmdlet selects the subdirectory and file based on the value of the `$PSUICulture` automatic variable.</span></span> <span data-ttu-id="983fc-111">Wenn Sie die lokale Variable im Skript verwenden, um eine Benutzermeldung anzuzeigen, wird die Meldung in der Benutzeroberflächensprache des Benutzers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="983fc-111">When you use the local variable in the script to display a user message, the message appears in the user's UI language.</span></span>

<span data-ttu-id="983fc-112">Sie können mit den Parametern von `Import-LocalizedData` eine Alternative Benutzeroberflächen Kultur, einen Pfad und einen Dateinamen angeben, unterstützte Befehle hinzufügen und die Fehlermeldung unterdrücken, die angezeigt wird, wenn die `.psd1` Dateien nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="983fc-112">You can use the parameters of `Import-LocalizedData` to specify an alternate UI culture, path, and filename, to add supported commands, and to suppress the error message that appears if the `.psd1` files are not found.</span></span>

<span data-ttu-id="983fc-113">Das `Import-LocalizedData` Cmdlet unterstützt die Skript Internationalisierungs Initiative, die in Windows PowerShell 2,0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="983fc-113">The `Import-LocalizedData` cmdlet supports the script internationalization initiative that was introduced in Windows PowerShell 2.0.</span></span> <span data-ttu-id="983fc-114">Ziel dieser Initiative ist es, Benutzern weltweit einen besseren Dienst zu bieten, indem es Skripts erleichtert wird, Benutzermeldungen in der Sprache der Benutzeroberfläche des aktuellen Benutzers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="983fc-114">This initiative aims to better serve users worldwide by making it easy for scripts to display user messages in the UI language of the current user.</span></span> <span data-ttu-id="983fc-115">Weitere Informationen zu diesem und zum Format der `.psd1` Dateien finden Sie unter [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="983fc-115">For more information about this and about the format of the `.psd1` files, see [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span></span>

## <span data-ttu-id="983fc-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="983fc-116">EXAMPLES</span></span>

### <span data-ttu-id="983fc-117">Beispiel 1: Importieren von Text Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="983fc-117">Example 1: Import text strings</span></span>

<span data-ttu-id="983fc-118">In diesem Beispiel werden Text Zeichenfolgen in die- `$Messages` Variable importiert.</span><span class="sxs-lookup"><span data-stu-id="983fc-118">This example imports text strings into the `$Messages` variable.</span></span> <span data-ttu-id="983fc-119">Es werden die Standardwerte aller anderen Cmdlet-Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="983fc-119">It uses the default values of all other cmdlet parameters.</span></span>

```powershell
Import-LocalizedData -BindingVariable "Messages"
```

<span data-ttu-id="983fc-120">Wenn der Befehl im Archives.ps1 Skript im Verzeichnis enthalten ist `C:\Test` und der Wert der `$PsUICulture` automatischen Variablen zh-cn ist, `Import-LocalizedData` importiert die `Archives.psd1` Datei im `C:\test\zh-CN` Verzeichnis in die `$Messages` Variable.</span><span class="sxs-lookup"><span data-stu-id="983fc-120">If the command is included in the Archives.ps1 script in the `C:\Test` directory, and the value of the `$PsUICulture` automatic variable is zh-CN, `Import-LocalizedData` imports the `Archives.psd1` file in the `C:\test\zh-CN` directory into the `$Messages` variable.</span></span>

### <span data-ttu-id="983fc-121">Beispiel 2: Importieren lokalisierter Daten Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="983fc-121">Example 2: Import localized data strings</span></span>

<span data-ttu-id="983fc-122">Dieses Beispiel wird in der Befehlszeile ausgeführt, die nicht in einem Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="983fc-122">This example is run at the command line not in a script.</span></span> <span data-ttu-id="983fc-123">Er ruft lokalisierte Datenzeichenfolgen aus der Datei „Test.psd1“ ab, und zeigt sie in der Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="983fc-123">It gets localized data strings from the Test.psd1 file and displays them at the command line.</span></span> <span data-ttu-id="983fc-124">Da der Befehl nicht in einem Skript verwendet wird, ist der **FileName**-Parameter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="983fc-124">Because the command is not used in a script, the **FileName** parameter is required.</span></span> <span data-ttu-id="983fc-125">Der Befehl verwendet den **UICulture** -Parameter, um die Kultur "en-US" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="983fc-125">The command uses the **UICulture** parameter to specify the en-US culture.</span></span>

```powershell
Import-LocalizedData -FileName "Test.psd1" -UICulture "en-US"
```

```Output
Name                           Value
----                           -----
Msg3                           "Use $_ to represent the object that is being processed."
Msg2                           "This command requires the credentials of a member of the Administrators group on the...
Msg1                           "The Name parameter is missing from the command."
```

<span data-ttu-id="983fc-126">`Import-LocalizedData` gibt eine Hash Tabelle mit den lokalisierten Daten Zeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="983fc-126">`Import-LocalizedData` returns a hash table that contains the localized data strings.</span></span>

### <span data-ttu-id="983fc-127">Beispiel 3: Importieren von UI-Kultur Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="983fc-127">Example 3: Import UI culture strings</span></span>

```powershell
Import-LocalizedData -BindingVariable "MsgTbl" -UICulture "ar-SA" -FileName "Simple" -BaseDirectory "C:\Data\Localized"
```

<span data-ttu-id="983fc-128">Dieser Befehl importiert Text Zeichenfolgen in die- `$MsgTbl` Variable eines Skripts.</span><span class="sxs-lookup"><span data-stu-id="983fc-128">This command imports text strings into the `$MsgTbl` variable of a script.</span></span>

<span data-ttu-id="983fc-129">Er verwendet den **UICulture** -Parameter, um das Cmdlet anzuweisen, Daten aus der `Simple.psd1` Datei in das `ar-SA` Unterverzeichnis von zu importieren `C:\Data\Localized` .</span><span class="sxs-lookup"><span data-stu-id="983fc-129">It uses the **UICulture** parameter to direct the cmdlet to import data from the `Simple.psd1` file in the `ar-SA` subdirectory of `C:\Data\Localized`.</span></span>

### <span data-ttu-id="983fc-130">Beispiel 4: Importieren lokalisierter Daten in ein Skript</span><span class="sxs-lookup"><span data-stu-id="983fc-130">Example 4: Import localized data into a script</span></span>

<span data-ttu-id="983fc-131">In diesem Beispiel wird veranschaulicht, wie lokalisierte Daten in einem einfachen Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="983fc-131">This example shows how to use localized data in a simple script.</span></span>

```powershell
PS C:\> # In C:\Test\en-US\Test.psd1:

ConvertFrom-StringData @'

# English strings

Msg1 = "The Name parameter is missing from the command."
Msg2 = "This command requires the credentials of a member of the Administrators group on the computer."
Msg3 = "Use $_ to represent the object that is being processed."
'@

# In C:\Test\Test.ps1

Import-LocalizedData -BindingVariable "Messages"
Write-Host $Messages.Msg2

# In Windows PowerShell

PS C:\> .\Test.ps1

This command requires the credentials of a member of the Administrators group on the computer.
```

<span data-ttu-id="983fc-132">Der erste Teil des Beispiels zeigt den Inhalt der `Test.psd1` Datei.</span><span class="sxs-lookup"><span data-stu-id="983fc-132">The first part of the example shows the contents of the `Test.psd1` file.</span></span> <span data-ttu-id="983fc-133">Sie enthält einen `ConvertFrom-StringData` Befehl, mit dem eine Reihe benannter Text Zeichenfolgen in eine Hash Tabelle konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="983fc-133">It contains a `ConvertFrom-StringData` command that converts a series of named text strings into a hash table.</span></span> <span data-ttu-id="983fc-134">Die `Test.psd1` Datei befindet sich im Unterverzeichnis "en-US" des `C:\Test` Verzeichnisses, das das Skript enthält.</span><span class="sxs-lookup"><span data-stu-id="983fc-134">The `Test.psd1` file is located in the en-US subdirectory of the `C:\Test` directory that contains the script.</span></span>

<span data-ttu-id="983fc-135">Der zweite Teil des Beispiels zeigt den Inhalt des `Test.ps1` Skripts.</span><span class="sxs-lookup"><span data-stu-id="983fc-135">The second part of the example shows the contents of the `Test.ps1` script.</span></span> <span data-ttu-id="983fc-136">Sie enthält einen `Import-LocalizedData` Befehl, mit dem die Daten aus der übereinstimmenden `.psd1` Datei in die-Variable importiert werden, `$Messages` sowie einen `Write-Host` Befehl, mit dem eine der Nachrichten in der `$Messages` Variablen in das Host Programm geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="983fc-136">It contains an `Import-LocalizedData` command that imports the data from the matching `.psd1` file into the `$Messages` variable and a `Write-Host` command that writes one of the messages in the `$Messages` variable to the host program.</span></span>

<span data-ttu-id="983fc-137">Der letzte Teil des Beispiels führt das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="983fc-137">The last part of the example runs the script.</span></span> <span data-ttu-id="983fc-138">Die Ausgabe zeigt, dass die richtige Benutzermeldung in der Benutzeroberflächensprache angezeigt wird, die für den aktuellen Benutzer des Betriebssystems festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="983fc-138">The output shows that it displays the correct user message in the UI language set for the current user of the operating system.</span></span>

### <span data-ttu-id="983fc-139">Beispiel 5: Ersetzen von Standardtext Zeichenfolgen in einem Skript</span><span class="sxs-lookup"><span data-stu-id="983fc-139">Example 5: Replace default text strings in a script</span></span>

<span data-ttu-id="983fc-140">In diesem Beispiel wird gezeigt, wie verwendet wird `Import-LocalizedData` , um die im Daten Abschnitt eines Skripts definierten Standardtext Zeichenfolgen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="983fc-140">This example shows how to use `Import-LocalizedData` to replace default text strings defined in the DATA section of a script.</span></span>

```powershell
PS C:\> # In TestScript.ps1
$UserMessages = DATA

{    ConvertFrom-StringData @'

    # English strings

        Msg1 = "Enter a name."
        Msg2 = "Enter your employee ID."
        Msg3 = "Enter your building number."
'@
}

Import-LocalizedData -BindingVariable "UserMessages"
$UserMessages.Msg1...
```

<span data-ttu-id="983fc-141">In diesem Beispiel enthält der Daten Abschnitt des TestScript.ps1 Skripts einen `ConvertFrom-StringData` Befehl, der den Inhalt des Daten Abschnitts in eine Hash Tabelle konvertiert und den Wert der `$UserMessages` Variablen speichert.</span><span class="sxs-lookup"><span data-stu-id="983fc-141">In this example, the DATA section of the TestScript.ps1 script contains a `ConvertFrom-StringData` command that converts the contents of the DATA section to a hash table and stores in the value of the `$UserMessages` variable.</span></span>

<span data-ttu-id="983fc-142">Das Skript enthält außerdem einen- `Import-LocalizedData` Befehl, der eine Hash Tabelle mit übersetzten Text Zeichenfolgen aus der TestScript.psd1-Datei in dem Unterverzeichnis importiert, das durch den Wert der-Variable angegeben wird `$PsUICulture` .</span><span class="sxs-lookup"><span data-stu-id="983fc-142">The script also includes an `Import-LocalizedData` command, which imports a hash table of translated text strings from the TestScript.psd1 file in the subdirectory specified by the value of the `$PsUICulture` variable.</span></span> <span data-ttu-id="983fc-143">Wenn der Befehl die `.psd1` Datei findet, speichert Sie die übersetzten Zeichen folgen aus der Datei im Wert derselben `$UserMessages` Variablen und überschreibt die Hash Tabelle, die von der Daten Abschnitts Logik gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="983fc-143">If the command finds the `.psd1` file, it saves the translated strings from the file in the value of the same `$UserMessages` variable, overwriting the hash table saved by the DATA section logic.</span></span>

<span data-ttu-id="983fc-144">Der dritte Befehl zeigt die erste Meldung in der `$UserMessages` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="983fc-144">The third command displays the first message in the `$UserMessages` variable.</span></span>

<span data-ttu-id="983fc-145">Wenn der `Import-LocalizedData` Befehl eine `.psd1` Datei für die `$PsUICulture` Sprache findet, enthält der Wert der `$UserMessages` Variablen die übersetzten Text Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="983fc-145">If the `Import-LocalizedData` command finds a `.psd1` file for the `$PsUICulture` language, the value of the `$UserMessages` variable contains the translated text strings.</span></span> <span data-ttu-id="983fc-146">Wenn der Befehl aus irgendeinem Grund fehlschlägt, zeigt der Befehl die im DATA-Abschnitt des Skripts definierten Standardtextzeichenfolgen an.</span><span class="sxs-lookup"><span data-stu-id="983fc-146">If the command fails for any reason, the command displays the default text strings defined in the DATA section of the script.</span></span>

### <span data-ttu-id="983fc-147">Beispiel 6: Unterdrücken von Fehlermeldungen, wenn die UI-Kultur nicht gefunden wird</span><span class="sxs-lookup"><span data-stu-id="983fc-147">Example 6: Suppress error messages if the UI culture is not found</span></span>

<span data-ttu-id="983fc-148">In diesem Beispiel wird gezeigt, wie Sie die Fehlermeldungen unterdrücken können, die angezeigt werden, wenn `Import-LocalizedData` die Verzeichnisse, die der Benutzeroberflächen Kultur des Benutzers entsprechen, nicht finden können oder keine `.psd1` Datei für das Skript in diesen Verzeichnissen finden.</span><span class="sxs-lookup"><span data-stu-id="983fc-148">This example shows how to suppress the error messages that appear when `Import-LocalizedData` cannot find the directories that match the user's UI culture or cannot find a `.psd1` file for the script in those directories.</span></span>

```powershell
PS C:\> # In Day1.ps1

Import-LocalizedData -BindingVariable "Day"

# In Day2.ps1

Import-LocalizedData -BindingVariable "Day" -ErrorAction:SilentlyContinue

PS C:\> .\Day1.ps1
Import-LocalizedData : Cannot find PowerShell data file 'Day1.psd1' in directory 'C:\ps-test\fr-BE\' or any parent culture directories.
At C:\ps-test\Day1.ps1:17 char:21+ Import-LocalizedData <<<<  Day
Today is Tuesday

PS C:\> .\Day2.ps1
Today is Tuesday
```

<span data-ttu-id="983fc-149">Sie können den allgemeinen **ErrorAction**-Parameter mit dem Wert SilentlyContinue verwenden, um die Fehlermeldung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="983fc-149">You can use the **ErrorAction** common parameter with a value of SilentlyContinue to suppress the error message.</span></span> <span data-ttu-id="983fc-150">Dies ist besonders nützlich, wenn Sie Benutzer Meldungen in einer Standard-oder Fall Back Sprache bereitgestellt haben und keine Fehlermeldung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="983fc-150">This is especially useful when you have provided user messages in a default or fallback language, and no error message is needed.</span></span>

<span data-ttu-id="983fc-151">In diesem Beispiel werden zwei Skripts `Day1.ps1` und Day2.ps1 verglichen, die einen- `Import-LocalizedData` Befehl enthalten.</span><span class="sxs-lookup"><span data-stu-id="983fc-151">This example compares two scripts, `Day1.ps1` and Day2.ps1, that include an `Import-LocalizedData` command.</span></span> <span data-ttu-id="983fc-152">Die Skripts sind identisch, mit dem Unterschied, dass "day2 den allgemeinen **ErrorAction** -Parameter mit einem Wert von verwendet `SilentlyContinue` .</span><span class="sxs-lookup"><span data-stu-id="983fc-152">The scripts are identical, except that Day2 uses the **ErrorAction** common parameter with a value of `SilentlyContinue`.</span></span>

<span data-ttu-id="983fc-153">Die Beispielausgabe zeigt die Ergebnisse der Ausführung beider Skripts, wenn die Benutzeroberflächen Kultur auf festgelegt ist `fr-BE` und es keine übereinstimmenden Dateien oder Verzeichnisse für diese Benutzeroberflächen Kultur gibt.</span><span class="sxs-lookup"><span data-stu-id="983fc-153">The sample output shows the results of running both scripts when the UI culture is set to `fr-BE` and there are no matching files or directories for that UI culture.</span></span> <span data-ttu-id="983fc-154">`Day1.ps1` zeigt eine Fehlermeldung und eine englische Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="983fc-154">`Day1.ps1` displays an error message and English output.</span></span> <span data-ttu-id="983fc-155">`Day2.ps1` zeigt nur die englische Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="983fc-155">`Day2.ps1` just displays the English output.</span></span>

## <span data-ttu-id="983fc-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="983fc-156">PARAMETERS</span></span>

### <span data-ttu-id="983fc-157">-BaseDirectory</span><span class="sxs-lookup"><span data-stu-id="983fc-157">-BaseDirectory</span></span>

<span data-ttu-id="983fc-158">Gibt das Basisverzeichnis an, in dem `.psd1` sich die Dateien befinden.</span><span class="sxs-lookup"><span data-stu-id="983fc-158">Specifies the base directory where the `.psd1` files are located.</span></span> <span data-ttu-id="983fc-159">Der Standardwert ist das Verzeichnis, in dem das Skript gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="983fc-159">The default is the directory where the script is located.</span></span> <span data-ttu-id="983fc-160">`Import-LocalizedData` sucht die `.psd1` Datei für das Skript in einem sprachspezifischen Unterverzeichnis des Basisverzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="983fc-160">`Import-LocalizedData` searches for the `.psd1` file for the script in a language-specific subdirectory of the base directory.</span></span>

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

### <span data-ttu-id="983fc-161">-Bindingvariable</span><span class="sxs-lookup"><span data-stu-id="983fc-161">-BindingVariable</span></span>

<span data-ttu-id="983fc-162">Gibt die Variable an, in die die Textzeichenfolgen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="983fc-162">Specifies the variable into which the text strings are imported.</span></span> <span data-ttu-id="983fc-163">Geben Sie einen Variablennamen ohne Dollarzeichen ( `$` ) ein.</span><span class="sxs-lookup"><span data-stu-id="983fc-163">Enter a variable name without a dollar sign (`$`).</span></span>

<span data-ttu-id="983fc-164">Dieser Parameter ist in Windows PowerShell 2.0 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="983fc-164">In Windows PowerShell 2.0, this parameter is required.</span></span> <span data-ttu-id="983fc-165">Dieser Parameter ist in Windows PowerShell 3.0 optional.</span><span class="sxs-lookup"><span data-stu-id="983fc-165">In Windows PowerShell 3.0, this parameter is optional.</span></span> <span data-ttu-id="983fc-166">Wenn Sie diesen Parameter weglassen, `Import-LocalizedData` gibt eine Hash Tabelle der Text Zeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="983fc-166">If you omit this parameter, `Import-LocalizedData` returns a hash table of the text strings.</span></span> <span data-ttu-id="983fc-167">Die Hashtabelle wird über die Pipeline übergeben oder in der Befehlszeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="983fc-167">The hash table is passed down the pipeline or displayed at the command line.</span></span>

<span data-ttu-id="983fc-168">Wenn Sie verwenden `Import-LocalizedData` , um im Data-Abschnitt eines Skripts angegebene Standardtext Zeichenfolgen zu ersetzen, weisen Sie den Daten Abschnitt einer Variablen zu, und geben Sie den Namen der Daten Abschnitts Variablen in den Wert des **bindingvariable** -Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="983fc-168">When using `Import-LocalizedData` to replace default text strings specified in the DATA section of a script, assign the DATA section to a variable and enter the name of the DATA section variable in the value of the **BindingVariable** parameter.</span></span> <span data-ttu-id="983fc-169">Wenn dann `Import-LocalizedData` den importierten Inhalt in der **bindingvariable** speichert, werden die Standardtext Zeichenfolgen durch die importierten Daten ersetzt.</span><span class="sxs-lookup"><span data-stu-id="983fc-169">Then, when `Import-LocalizedData` saves the imported content in the **BindingVariable**, the imported data will replace the default text strings.</span></span> <span data-ttu-id="983fc-170">Wenn Sie keine Standardtextzeichenfolgen angeben, können Sie einen beliebigen Variablennamen auswählen.</span><span class="sxs-lookup"><span data-stu-id="983fc-170">If you are not specifying default text strings, you can select any variable name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Variable

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="983fc-171">-Dateiname</span><span class="sxs-lookup"><span data-stu-id="983fc-171">-FileName</span></span>

<span data-ttu-id="983fc-172">Gibt den Namen der `.psd1)` zu importierenden Datendatei an.</span><span class="sxs-lookup"><span data-stu-id="983fc-172">Specifies the name of the data file (`.psd1)` to be imported.</span></span> <span data-ttu-id="983fc-173">Geben Sie einen Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="983fc-173">Enter a file name.</span></span> <span data-ttu-id="983fc-174">Sie können einen Dateinamen angeben, der die `.psd1` Dateinamenerweiterung nicht enthält, oder Sie können den Dateinamen angeben, einschließlich der `.psd1` Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="983fc-174">You can specify a file name that does not include its `.psd1` file name extension, or you can specify the file name including the `.psd1` file name extension.</span></span> <span data-ttu-id="983fc-175">Datendateien sollten als Unicode oder UTF-8 gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="983fc-175">Data files should be saved as Unicode or UTF-8.</span></span>

<span data-ttu-id="983fc-176">Der **filename** -Parameter ist erforderlich, wenn `Import-LocalizedData` nicht in einem Skript verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="983fc-176">The **FileName** parameter is required when `Import-LocalizedData` is not used in a script.</span></span>
<span data-ttu-id="983fc-177">Anderenfalls ist der Parameter optional, und der Standardwert ist der Basisname des Skripts.</span><span class="sxs-lookup"><span data-stu-id="983fc-177">Otherwise, the parameter is optional and the default value is the base name of the script.</span></span> <span data-ttu-id="983fc-178">Sie können diesen Parameter verwenden, um `Import-LocalizedData` eine andere Datei zu suchen `.psd1` .</span><span class="sxs-lookup"><span data-stu-id="983fc-178">You can use this parameter to direct `Import-LocalizedData` to search for a different `.psd1` file.</span></span>

<span data-ttu-id="983fc-179">Wenn z. b. der **Dateiname** weggelassen wird und der Skript Name FindFiles.ps1 ist, `Import-LocalizedData` sucht nach der FindFiles.psd1-Datendatei.</span><span class="sxs-lookup"><span data-stu-id="983fc-179">For example, if the **FileName** is omitted and the script name is FindFiles.ps1, `Import-LocalizedData` searches for the FindFiles.psd1 data file.</span></span>

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

### <span data-ttu-id="983fc-180">-Supportedcommand</span><span class="sxs-lookup"><span data-stu-id="983fc-180">-SupportedCommand</span></span>

<span data-ttu-id="983fc-181">Gibt Cmdlets und Funktionen an, die nur Daten generieren.</span><span class="sxs-lookup"><span data-stu-id="983fc-181">Specifies cmdlets and functions that generate only data.</span></span>

<span data-ttu-id="983fc-182">Verwenden Sie diesen Parameter, um Cmdlets und Funktionen einzuschließen, die Sie geschrieben oder getestet haben.</span><span class="sxs-lookup"><span data-stu-id="983fc-182">Use this parameter to include cmdlets and functions that you have written or tested.</span></span> <span data-ttu-id="983fc-183">Weitere Informationen finden Sie unter [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="983fc-183">For more information, see [about_Script_Internationalization](../Microsoft.PowerShell.Core/About/about_Script_Internationalization.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="983fc-184">-UICulture</span><span class="sxs-lookup"><span data-stu-id="983fc-184">-UICulture</span></span>

<span data-ttu-id="983fc-185">Gibt eine alternative Benutzeroberflächenkultur an.</span><span class="sxs-lookup"><span data-stu-id="983fc-185">Specifies an alternate UI culture.</span></span>
<span data-ttu-id="983fc-186">Der Standardwert ist der Wert der `$PsUICulture` automatischen Variablen.</span><span class="sxs-lookup"><span data-stu-id="983fc-186">The default is the value of the `$PsUICulture` automatic variable.</span></span>
<span data-ttu-id="983fc-187">Geben Sie eine Benutzeroberflächen Kultur im `<language>-<region>` Format ein, z `en-US` . b `de-DE` ., oder `ar-SA` .</span><span class="sxs-lookup"><span data-stu-id="983fc-187">Enter a UI culture in `<language>-<region>` format, such as `en-US`, `de-DE`, or `ar-SA`.</span></span>

<span data-ttu-id="983fc-188">Der Wert des **UICulture** -Parameters bestimmt das sprachspezifische Unterverzeichnis (innerhalb des Basisverzeichnisses), von dem `Import-LocalizedData` die `.psd1` Datei für das Skript abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="983fc-188">The value of the **UICulture** parameter determines the language-specific subdirectory (within the base directory) from which `Import-LocalizedData` gets the `.psd1` file for the script.</span></span>

<span data-ttu-id="983fc-189">Das-Cmdlet sucht nach einem Unterverzeichnis mit dem gleichen Namen wie der Wert des **UICulture** -Parameters oder der `$PsUICulture` automatischen Variablen, `de-DE` z `ar-SA` . b. oder.</span><span class="sxs-lookup"><span data-stu-id="983fc-189">The cmdlet searches for a subdirectory with the same name as the value of the **UICulture** parameter or the `$PsUICulture` automatic variable, such as `de-DE` or `ar-SA`.</span></span> <span data-ttu-id="983fc-190">Wenn das Verzeichnis nicht gefunden werden kann oder wenn das Verzeichnis keine `.psd1` Datei für das Skript enthält, sucht es nach einem Unterverzeichnis mit dem Namen des Sprachcodes, z. b. "de" oder "ar".</span><span class="sxs-lookup"><span data-stu-id="983fc-190">If it cannot find the directory, or the directory does not contain a `.psd1` file for the script, it searches for a subdirectory with the name of the language code, such as de or ar.</span></span> <span data-ttu-id="983fc-191">Wenn das Unterverzeichnis oder die Datei nicht gefunden `.psd1` werden kann, schlägt der Befehl fehl, und die Daten werden in der Standardsprache angezeigt, die im Skript angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="983fc-191">If it cannot find the subdirectory or `.psd1` file, the command fails and the data is displayed in the default language specified in the script.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="983fc-192">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="983fc-192">CommonParameters</span></span>

<span data-ttu-id="983fc-193">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="983fc-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="983fc-194">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="983fc-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="983fc-195">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="983fc-195">INPUTS</span></span>

### <span data-ttu-id="983fc-196">Keine</span><span class="sxs-lookup"><span data-stu-id="983fc-196">None</span></span>

<span data-ttu-id="983fc-197">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="983fc-197">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="983fc-198">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="983fc-198">OUTPUTS</span></span>

### <span data-ttu-id="983fc-199">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="983fc-199">System.Collections.Hashtable</span></span>

<span data-ttu-id="983fc-200">`Import-LocalizedData` speichert die Hash Tabelle in der Variablen, die durch den Wert des **bindingvariable** -Parameters angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="983fc-200">`Import-LocalizedData` saves the hash table in the variable that is specified by the value of the **BindingVariable** parameter.</span></span>

## <span data-ttu-id="983fc-201">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="983fc-201">NOTES</span></span>

- <span data-ttu-id="983fc-202">Vor der Verwendung von `Import-LocalizedData` können Sie Ihre Benutzer Nachrichten lokalisieren.</span><span class="sxs-lookup"><span data-stu-id="983fc-202">Before using `Import-LocalizedData`, localize your user messages.</span></span> <span data-ttu-id="983fc-203">Formatieren Sie die Nachrichten für jedes Gebiets Schema (UI-Kultur) in einer Hash Tabelle mit Schlüssel-Wert-Paaren, und speichern Sie die Hash Tabelle in einer Datei mit dem gleichen Namen wie das Skript und einer `.psd1` Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="983fc-203">Format the messages for each locale (UI culture) in a hash table of key-value pairs, and save the hash table in a file with the same name as the script and a `.psd1` file name extension.</span></span> <span data-ttu-id="983fc-204">Erstellen Sie für jede unterstützte Benutzeroberflächen Kultur im Skriptverzeichnis ein Verzeichnis, und speichern Sie dann die `.psd1` Datei für jede Benutzeroberflächen Kultur im Verzeichnis mit dem Namen der Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="983fc-204">Create a directory under the script directory for each supported UI culture, and then save the `.psd1` file for each UI culture in the directory with the UI culture name.</span></span>

  <span data-ttu-id="983fc-205">Lokalisieren Sie beispielsweise Benutzermeldungen für das Gebietsschema „de-DE“, und formatieren Sie sie in einer Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="983fc-205">For example, localize your user messages for the de-DE locale and format them in a hash table.</span></span>
  <span data-ttu-id="983fc-206">Speichert die Hash Tabelle in einer `<ScriptName>.psd1` Datei.</span><span class="sxs-lookup"><span data-stu-id="983fc-206">Save the hash table in a `<ScriptName>.psd1` file.</span></span> <span data-ttu-id="983fc-207">Erstellen Sie dann ein unter `de-DE` Verzeichnis unter dem Skriptverzeichnis, und speichern Sie die deutsche `<ScriptName\>.psd1` Datei im `de-DE` Unterverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="983fc-207">Then create a `de-DE` subdirectory under the script directory, and save the German `<ScriptName\>.psd1` file in the `de-DE` subdirectory.</span></span>
  <span data-ttu-id="983fc-208">Wiederholen Sie diese Methode für jedes Gebietsschema, das Sie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="983fc-208">Repeat this method for each locale that you support.</span></span>

- <span data-ttu-id="983fc-209">`Import-LocalizedData` führt eine strukturierte Suche nach den lokalisierten Benutzer Nachrichten für ein Skript aus.</span><span class="sxs-lookup"><span data-stu-id="983fc-209">`Import-LocalizedData` performs a structured search for the localized user messages for a script.</span></span>

  <span data-ttu-id="983fc-210">`Import-LocalizedData` startet die Suche in dem Verzeichnis, in dem sich die Skriptdatei befindet (oder dem Wert des **BaseDirectory** -Parameters).</span><span class="sxs-lookup"><span data-stu-id="983fc-210">`Import-LocalizedData` begins the search in the directory where the script file is located (or the value of the **BaseDirectory** parameter).</span></span> <span data-ttu-id="983fc-211">Anschließend wird im Basisverzeichnis nach einem Unterverzeichnis mit dem gleichen Namen wie der Wert der `$PsUICulture` Variablen (oder dem Wert des **UICulture** -Parameters) durchsucht, z `de-DE` . b `ar-SA` . oder.</span><span class="sxs-lookup"><span data-stu-id="983fc-211">It then searches within the base directory for a subdirectory with the same name as the value of the `$PsUICulture` variable (or the value of the **UICulture** parameter), such as `de-DE` or `ar-SA`.</span></span> <span data-ttu-id="983fc-212">Anschließend sucht er in diesem Unterverzeichnis nach einer `.psd1` Datei mit dem gleichen Namen wie das Skript (oder dem Wert des **filename** -Parameters).</span><span class="sxs-lookup"><span data-stu-id="983fc-212">Then, it searches in that subdirectory for a `.psd1` file with the same name as the script (or the value of the **FileName** parameter).</span></span>

  <span data-ttu-id="983fc-213">Wenn `Import-LocalizedData` ein Unterverzeichnis mit dem Namen der UI-Kultur nicht finden kann oder das Unterverzeichnis keine `.psd1` Datei für das Skript enthält, sucht es nach einer `.psd1` Datei für das Skript in einem Unterverzeichnis mit dem Namen des Sprachcodes, z. b. "de" oder "ar".</span><span class="sxs-lookup"><span data-stu-id="983fc-213">If `Import-LocalizedData` cannot find a subdirectory with the name of the UI culture, or the subdirectory does not contain a `.psd1` file for the script, it searches for a `.psd1` file for the script in a subdirectory with the name of the language code, such as de or ar.</span></span> <span data-ttu-id="983fc-214">Wenn das Unterverzeichnis oder die Datei nicht gefunden `.psd1` werden kann, schlägt der Befehl fehl, die Daten werden in der Standardsprache im Skript angezeigt, und es wird eine Fehlermeldung mit dem Hinweis angezeigt, dass die Daten nicht importiert werden konnten.</span><span class="sxs-lookup"><span data-stu-id="983fc-214">If it cannot find the subdirectory or `.psd1` file, the command fails, the data is displayed in the default language in the script, and an error message is displayed explaining that the data could not be imported.</span></span> <span data-ttu-id="983fc-215">Verwenden Sie den allgemeinen **ErrorAction** -Parameter mit dem Wert SilentlyContinue, um die Meldung zu unterdrücken und ordnungsgemäß fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="983fc-215">To suppress the message and fail gracefully, use the **ErrorAction** common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="983fc-216">Wenn `Import-LocalizedData` das Unterverzeichnis und die `.psd1` Datei findet, wird die Hash Tabelle mit Benutzer Nachrichten in den Wert des **bindingvariable** -Parameters im Befehl importiert.</span><span class="sxs-lookup"><span data-stu-id="983fc-216">If `Import-LocalizedData` finds the subdirectory and the `.psd1` file, it imports the hash table of user messages into the value of the **BindingVariable** parameter in the command.</span></span> <span data-ttu-id="983fc-217">Wenn Sie dann eine Meldung aus der Hashtabelle in der Variablen anzeigen, wird die lokalisierte Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="983fc-217">Then, when you display a message from the hash table in the variable, the localized message is displayed.</span></span>

  <span data-ttu-id="983fc-218">Weitere Informationen finden Sie unter [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="983fc-218">For more information, see [about_Script_Internationalization](../Microsoft.Powershell.Core/About/about_Script_Internationalization.md).</span></span>

## <span data-ttu-id="983fc-219">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="983fc-219">RELATED LINKS</span></span>

[<span data-ttu-id="983fc-220">Write-Host</span><span class="sxs-lookup"><span data-stu-id="983fc-220">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="983fc-221">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="983fc-221">Import-PowerShellDataFile</span></span>](Import-PowerShellDataFile.md)

