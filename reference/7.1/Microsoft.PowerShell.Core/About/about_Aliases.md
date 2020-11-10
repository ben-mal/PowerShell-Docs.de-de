---
description: Beschreibt, wie alternative Namen für Cmdlets und Befehle in PowerShell verwendet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_aliases?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Aliases
ms.openlocfilehash: 9213bd41af6d5383c7e67d33b8909736a6e380bb
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391288"
---
# <a name="about-aliases"></a><span data-ttu-id="5fc18-104">Informationen zu Aliasen</span><span class="sxs-lookup"><span data-stu-id="5fc18-104">About Aliases</span></span>

## <a name="short-description"></a><span data-ttu-id="5fc18-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5fc18-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="5fc18-106">Beschreibt, wie alternative Namen für Cmdlets und Befehle in PowerShell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5fc18-106">Describes how to use alternate names for cmdlets and commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="5fc18-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5fc18-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="5fc18-108">Ein Alias ist ein alternativer Name oder Spitzname für ein Cmdlet oder ein Befehls Element, z. b. eine Funktion, ein Skript, eine Datei oder eine ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="5fc18-108">An alias is an alternate name or nickname for a cmdlet or for a command element, such as a function, script, file, or executable file.</span></span> <span data-ttu-id="5fc18-109">Sie können den Alias anstelle des Befehlsnamens in beliebigen PowerShell-Befehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5fc18-109">You can use the alias instead of the command name in any PowerShell commands.</span></span>

<span data-ttu-id="5fc18-110">Verwenden Sie das Cmdlet "New-Alias", um einen Alias zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5fc18-110">To create an alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="5fc18-111">Der folgende Befehl erstellt z. b. den Alias "Gas" für das `Get-AuthenticodeSignature` Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5fc18-111">For example, the following command creates the "gas" alias for the `Get-AuthenticodeSignature` cmdlet:</span></span>

```powershell
New-Alias -Name gas -Value Get-AuthenticodeSignature
```

<span data-ttu-id="5fc18-112">Nachdem Sie den Alias für den Cmdlet-Namen erstellt haben, können Sie den Alias anstelle des Cmdlet-namens verwenden.</span><span class="sxs-lookup"><span data-stu-id="5fc18-112">After you create the alias for the cmdlet name, you can use the alias instead of the cmdlet name.</span></span> <span data-ttu-id="5fc18-113">Um z. b. die Authenticode-Signatur für die SqlScript.ps1-Datei zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5fc18-113">For example, to get the Authenticode signature for the SqlScript.ps1 file, type:</span></span>

```powershell
Get-AuthenticodeSignature SqlScript.ps1
```

<span data-ttu-id="5fc18-114">Oder geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5fc18-114">Or, type:</span></span>

```powershell
gas SqlScript.ps1
```

<span data-ttu-id="5fc18-115">Wenn Sie "Word" als Alias für Microsoft Office Word erstellen, können Sie anstelle der folgenden "Word" eingeben:</span><span class="sxs-lookup"><span data-stu-id="5fc18-115">If you create "word" as the alias for Microsoft Office Word, you can type "word" instead of the following:</span></span>

```powershell
"C:\Program Files\Microsoft Office\Office11\Winword.exe"
```

## <a name="built-in-aliases"></a><span data-ttu-id="5fc18-116">integrierte Aliase</span><span class="sxs-lookup"><span data-stu-id="5fc18-116">BUILT-IN ALIASES</span></span>

<span data-ttu-id="5fc18-117">PowerShell umfasst eine Reihe integrierter Aliase, einschließlich "CD" und "chdir" für das Cmdlet "Set-Location" und "ls" und "dir" für das Get-ChildItem-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5fc18-117">PowerShell includes a set of built-in aliases, including "cd" and "chdir" for the Set-Location cmdlet, and "ls" and "dir" for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="5fc18-118">Um alle Aliase auf dem Computer zu erhalten, einschließlich der integrierten Aliase, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5fc18-118">To get all the aliases on the computer, including the built-in aliases, type:</span></span>

```powershell
Get-Alias
```

## <a name="alias-cmdlets"></a><span data-ttu-id="5fc18-119">Alias-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5fc18-119">ALIAS CMDLETS</span></span>

<span data-ttu-id="5fc18-120">PowerShell umfasst die folgenden Cmdlets, die für die Arbeit mit Aliasen entwickelt wurden:</span><span class="sxs-lookup"><span data-stu-id="5fc18-120">PowerShell includes the following cmdlets, which are designed for working with aliases:</span></span>

- <span data-ttu-id="5fc18-121">`Get-Alias` : Ruft alle Aliase in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="5fc18-121">`Get-Alias` - Gets all the aliases in the current session.</span></span>
- <span data-ttu-id="5fc18-122">`New-Alias` -Erstellt einen neuen Alias.</span><span class="sxs-lookup"><span data-stu-id="5fc18-122">`New-Alias` - Creates a new alias.</span></span>
- <span data-ttu-id="5fc18-123">`Set-Alias` -Erstellt oder ändert einen Alias.</span><span class="sxs-lookup"><span data-stu-id="5fc18-123">`Set-Alias` - Creates or changes an alias.</span></span>
- <span data-ttu-id="5fc18-124">`Export-Alias` -Exportiert mindestens einen Alias in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="5fc18-124">`Export-Alias` - Exports one or more aliases to a file.</span></span>
- <span data-ttu-id="5fc18-125">`Import-Alias` : Importiert eine Alias Datei in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fc18-125">`Import-Alias` - Imports an alias file into PowerShell.</span></span>

<span data-ttu-id="5fc18-126">Ausführliche Informationen zu den-Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="5fc18-126">For detailed information about the cmdlets, type:</span></span>

```powershell
Get-Help <cmdlet-Name> -Detailed
```

<span data-ttu-id="5fc18-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5fc18-127">For example, type:</span></span>

```powershell
Get-Help Export-Alias -Detailed
```

## <a name="creating-an-alias"></a><span data-ttu-id="5fc18-128">Erstellen eines Alias</span><span class="sxs-lookup"><span data-stu-id="5fc18-128">CREATING AN ALIAS</span></span>

<span data-ttu-id="5fc18-129">Um einen neuen Alias zu erstellen, verwenden Sie das Cmdlet "New-Alias".</span><span class="sxs-lookup"><span data-stu-id="5fc18-129">To create a new alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="5fc18-130">Geben Sie beispielsweise Folgendes ein, um den "GH"-Alias für "Get-Help" zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="5fc18-130">For example, to create the "gh" alias for Get-Help, type:</span></span>

```powershell
New-Alias -Name gh -Value Get-Help
```

<span data-ttu-id="5fc18-131">Sie können den Alias in Befehlen wie den vollständigen Cmdlet-Namen verwenden, und Sie können den Alias mit Parametern verwenden.</span><span class="sxs-lookup"><span data-stu-id="5fc18-131">You can use the alias in commands, just as you would use the full cmdlet name, and you can use the alias with parameters.</span></span>

<span data-ttu-id="5fc18-132">Wenn Sie z. b. Ausführliche Hilfe für das Cmdlet "Get-WmiObject" benötigen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5fc18-132">For example, to get detailed Help for the Get-WmiObject cmdlet, type:</span></span>

```powershell
Get-Help Get-WmiObject -Detailed
```

<span data-ttu-id="5fc18-133">Oder geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5fc18-133">Or, type:</span></span>

```powershell
gh Get-WmiObject -Detailed
```

## <a name="saving-aliases"></a><span data-ttu-id="5fc18-134">Speichern von Aliasen</span><span class="sxs-lookup"><span data-stu-id="5fc18-134">SAVING ALIASES</span></span>

<span data-ttu-id="5fc18-135">Die von Ihnen erstellten Aliase werden nur in der aktuellen Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5fc18-135">The aliases that you create are saved only in the current session.</span></span> <span data-ttu-id="5fc18-136">Um die Aliase in einer anderen Sitzung zu verwenden, fügen Sie den Alias Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="5fc18-136">To use the aliases in a different session, add the alias to your PowerShell profile.</span></span> <span data-ttu-id="5fc18-137">Oder verwenden Sie das Cmdlet "Export-Alias", um die Aliase in einer Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5fc18-137">Or, use the Export-Alias cmdlet to save the aliases to a file.</span></span>

<span data-ttu-id="5fc18-138">Geben Sie folgenden Befehl ein, um weitere Informationen zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="5fc18-138">For more information, type:</span></span>

```powershell
Get-Help about_Profiles
```

## <a name="getting-aliases"></a><span data-ttu-id="5fc18-139">erhalten von Aliasen</span><span class="sxs-lookup"><span data-stu-id="5fc18-139">GETTING ALIASES</span></span>

<span data-ttu-id="5fc18-140">Um alle Aliase in der aktuellen Sitzung, einschließlich der integrierten Aliase, der Aliase in ihren PowerShell-Profilen und der Aliase, die Sie in der aktuellen Sitzung erstellt haben, zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5fc18-140">To get all the aliases in the current session, including the built-in aliases, the aliases in your PowerShell profiles, and the aliases that you have created in the current session, type:</span></span>

```powershell
Get-Alias
```

<span data-ttu-id="5fc18-141">Um bestimmte Aliase zu erhalten, verwenden Sie den Name-Parameter des Cmdlets "Get-Alias".</span><span class="sxs-lookup"><span data-stu-id="5fc18-141">To get particular aliases, use the Name parameter of the Get-Alias cmdlet.</span></span> <span data-ttu-id="5fc18-142">Um Aliase zu erhalten, die mit "p" beginnen, geben Sie z. b. Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5fc18-142">For example, to get aliases that begin with "p", type:</span></span>

```powershell
Get-Alias -Name p*
```

<span data-ttu-id="5fc18-143">Um die Aliase für ein bestimmtes Element zu erhalten, verwenden Sie den Definition-Parameter.</span><span class="sxs-lookup"><span data-stu-id="5fc18-143">To get the aliases for a particular item, use the Definition parameter.</span></span> <span data-ttu-id="5fc18-144">Um beispielsweise die Aliase für den Get-ChildItem Cmdlet-Typ zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5fc18-144">For example, to get the aliases for the Get-ChildItem cmdlet type:</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

### <a name="get-alias-output"></a><span data-ttu-id="5fc18-145">Get-Alias-Ausgabe</span><span class="sxs-lookup"><span data-stu-id="5fc18-145">GET-ALIAS OUTPUT</span></span>

<span data-ttu-id="5fc18-146">Get-Alias gibt nur einen Objekttyp zurück, ein AliasInfo-Objekt (System. Management. Automation. AliasInfo).</span><span class="sxs-lookup"><span data-stu-id="5fc18-146">Get-Alias returns only one type of object, an AliasInfo object (System.Management.Automation.AliasInfo).</span></span> <span data-ttu-id="5fc18-147">Der Name von Aliasen, die keinen Bindestrich enthalten, wie z. b. "CD", wird im folgenden Format angezeigt:</span><span class="sxs-lookup"><span data-stu-id="5fc18-147">The name of aliases that don't include a hyphen, such as "cd" are displayed in the following format:</span></span>

```powershell
Get-Alias ac
```

```Output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Alias           ac -> Add-Content
```

<span data-ttu-id="5fc18-148">Dadurch ist es sehr schnell und einfach, die benötigten Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5fc18-148">This makes it very quick and easy to get the information that you need.</span></span>

<span data-ttu-id="5fc18-149">Das pfeilbasierte Aliasnamensformat wird nicht für Aliase verwendet, die einen Bindestrich enthalten.</span><span class="sxs-lookup"><span data-stu-id="5fc18-149">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="5fc18-150">Dabei handelt es sich wahrscheinlich um bevorzugte Ersatznamen für Cmdlets und Funktionen anstelle von typischen Abkürzungen oder Spitznamen, und der Autor möchte, dass Sie möglicherweise nicht so offensichtlich sind.</span><span class="sxs-lookup"><span data-stu-id="5fc18-150">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames, and the author might not want them to be as evident.</span></span>

## <a name="alternate-names-for-commands-with-parameters"></a><span data-ttu-id="5fc18-151">Alternative Namen für Befehle mit Parametern</span><span class="sxs-lookup"><span data-stu-id="5fc18-151">ALTERNATE NAMES FOR COMMANDS WITH PARAMETERS</span></span>

<span data-ttu-id="5fc18-152">Sie können einem Cmdlet, einem Skript, einer Funktion oder einer ausführbaren Datei einen Alias zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5fc18-152">You can assign an alias to a cmdlet, script, function, or executable file.</span></span> <span data-ttu-id="5fc18-153">Einem Befehl und seinen Parametern kann kein Alias zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="5fc18-153">You cannot assign an alias to a command and its parameters.</span></span> <span data-ttu-id="5fc18-154">Beispielsweise können Sie dem `Get-Eventlog` Cmdlet einen Alias zuweisen, Sie können dem Befehl aber keinen Alias zuweisen `Get-Eventlog -LogName System` .</span><span class="sxs-lookup"><span data-stu-id="5fc18-154">For example, you can assign an alias to the `Get-Eventlog` cmdlet, but you cannot assign an alias to the `Get-Eventlog -LogName System` command.</span></span>

<span data-ttu-id="5fc18-155">Sie können eine Funktion erstellen, die den Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="5fc18-155">You can create a function that includes the command.</span></span> <span data-ttu-id="5fc18-156">Um eine Funktion zu erstellen, geben Sie das Wort "Function" gefolgt von einem Namen für die Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="5fc18-156">To create a function, type the word "function" followed by a name for the function.</span></span> <span data-ttu-id="5fc18-157">Geben Sie den Befehl ein, und schließen Sie ihn in geschweifte Klammern ( {} ) ein.</span><span class="sxs-lookup"><span data-stu-id="5fc18-157">Type the command, and enclose it in braces ({}).</span></span>

<span data-ttu-id="5fc18-158">Der folgende Befehl erstellt z. b. die syslog-Funktion.</span><span class="sxs-lookup"><span data-stu-id="5fc18-158">For example, the following command creates the syslog function.</span></span> <span data-ttu-id="5fc18-159">Diese Funktion stellt den- `Get-Eventlog -LogName System` Befehl dar:</span><span class="sxs-lookup"><span data-stu-id="5fc18-159">This function represents the `Get-Eventlog -LogName System` command:</span></span>

```powershell
function Get-SystemEventlog {Get-Eventlog -LogName System}
Set-Alias -Name syslog -Value Get-SystemEventlog
```

<span data-ttu-id="5fc18-160">Sie können jetzt "syslog" anstelle des Befehls eingeben.</span><span class="sxs-lookup"><span data-stu-id="5fc18-160">You can now type "syslog" instead of the command.</span></span> <span data-ttu-id="5fc18-161">Und Sie können Aliase für die neue Funktion erstellen.</span><span class="sxs-lookup"><span data-stu-id="5fc18-161">And, you can create aliases for the new function.</span></span>

<span data-ttu-id="5fc18-162">Weitere Informationen zu Funktionen erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="5fc18-162">For more information about functions, type:</span></span>

```powershell
Get-Help about_Functions
```

## <a name="alias-objects"></a><span data-ttu-id="5fc18-163">Alias Objekte</span><span class="sxs-lookup"><span data-stu-id="5fc18-163">ALIAS OBJECTS</span></span>

<span data-ttu-id="5fc18-164">PowerShell-Aliase werden durch Objekte dargestellt, die Instanzen der System. Management. Automation. AliasInfo-Klasse sind.</span><span class="sxs-lookup"><span data-stu-id="5fc18-164">PowerShell aliases are represented by objects that are instances of the System.Management.Automation.AliasInfo class.</span></span> <span data-ttu-id="5fc18-165">Weitere Informationen zu diesem Objekttyp finden Sie unter [AliasInfo-Klasse][aliasinfo] im PowerShell SDK.</span><span class="sxs-lookup"><span data-stu-id="5fc18-165">For more information about this type of object, see [AliasInfo Class][aliasinfo] in the PowerShell SDK.</span></span>

<span data-ttu-id="5fc18-166">Um die Eigenschaften und Methoden der Alias Objekte anzuzeigen, erhalten Sie die Aliase.</span><span class="sxs-lookup"><span data-stu-id="5fc18-166">To view the properties and methods of the alias objects, get the aliases.</span></span>
<span data-ttu-id="5fc18-167">Übergeben Sie Sie dann an das Cmdlet "Get-Member".</span><span class="sxs-lookup"><span data-stu-id="5fc18-167">Then, pipe them to the Get-Member cmdlet.</span></span> <span data-ttu-id="5fc18-168">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5fc18-168">For example:</span></span>

```powershell
Get-Alias | Get-Member
```

<span data-ttu-id="5fc18-169">Zum Anzeigen der Werte der Eigenschaften eines bestimmten Alias, z. b. des `dir` Alias, erhalten Sie den Alias.</span><span class="sxs-lookup"><span data-stu-id="5fc18-169">To view the values of the properties of a specific alias, such as the `dir` alias, get the alias.</span></span> <span data-ttu-id="5fc18-170">Übergeben Sie ihn dann an das Cmdlet "Format-List".</span><span class="sxs-lookup"><span data-stu-id="5fc18-170">Then, pipe it to the Format-List cmdlet.</span></span> <span data-ttu-id="5fc18-171">Der folgende Befehl ruft z. b. den Alias "dir" ab.</span><span class="sxs-lookup"><span data-stu-id="5fc18-171">For example, the following command gets the "dir" alias.</span></span> <span data-ttu-id="5fc18-172">Als nächstes leitet der Befehl den Alias an das Format-List-Cmdlet weiter.</span><span class="sxs-lookup"><span data-stu-id="5fc18-172">Next, the command pipes the alias to the Format-List cmdlet.</span></span> <span data-ttu-id="5fc18-173">Anschließend verwendet der Befehl den property-Parameter von Format-List mit einem Platzhalter Zeichen ( \* ), um alle Eigenschaften des `dir` Alias anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5fc18-173">Then, the command uses the Property parameter of Format-List with a wildcard character (\*) to display all the properties of the `dir` alias.</span></span> <span data-ttu-id="5fc18-174">Der folgende Befehl führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="5fc18-174">The following command performs these tasks:</span></span>

```powershell
Get-Alias -Name dir | Format-List -Property *
```

## <a name="powershell-alias-provider"></a><span data-ttu-id="5fc18-175">PowerShell-Alias Anbieter</span><span class="sxs-lookup"><span data-stu-id="5fc18-175">PowerShell ALIAS PROVIDER</span></span>

<span data-ttu-id="5fc18-176">PowerShell enthält den Alias Anbieter.</span><span class="sxs-lookup"><span data-stu-id="5fc18-176">PowerShell includes the Alias provider.</span></span> <span data-ttu-id="5fc18-177">Mit dem Alias Anbieter können Sie die Aliase in PowerShell anzeigen, als ob Sie sich auf einem Dateisystem Laufwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="5fc18-177">The Alias provider lets you view the aliases in PowerShell as though they were on a file system drive.</span></span>

<span data-ttu-id="5fc18-178">Der Alias Anbieter stellt das Alias:-Laufwerk zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5fc18-178">The Alias provider exposes the Alias: drive.</span></span> <span data-ttu-id="5fc18-179">Um in das Alias:-Laufwerk zu wechseln, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5fc18-179">To go into the Alias: drive, type:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="5fc18-180">Geben Sie Folgendes ein, um den Inhalt des Laufwerks anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="5fc18-180">To view the contents of the drive, type:</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="5fc18-181">Um den Inhalt des Laufwerks von einem anderen PowerShell-Laufwerk aus anzuzeigen, starten Sie den Pfad mit dem Namen des Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="5fc18-181">To view the contents of the drive from another PowerShell drive, begin the path with the drive name.</span></span> <span data-ttu-id="5fc18-182">Fügen Sie den Doppelpunkt (:) ein.</span><span class="sxs-lookup"><span data-stu-id="5fc18-182">Include the colon (:).</span></span> <span data-ttu-id="5fc18-183">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5fc18-183">For example:</span></span>

```powershell
Get-ChildItem -Path Alias:
```

<span data-ttu-id="5fc18-184">Um Informationen zu einem bestimmten Alias zu erhalten, geben Sie den Namen des Laufwerks und den Aliasnamen ein.</span><span class="sxs-lookup"><span data-stu-id="5fc18-184">To get information about a particular alias, type the drive name and the alias name.</span></span> <span data-ttu-id="5fc18-185">Oder geben Sie ein Namensmuster ein.</span><span class="sxs-lookup"><span data-stu-id="5fc18-185">Or, type a name pattern.</span></span> <span data-ttu-id="5fc18-186">Um z. b. alle Aliase zu erhalten, die mit "p" beginnen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5fc18-186">For example, to get all the aliases that begin with "p", type:</span></span>

```powershell
Get-ChildItem -Path Alias:p*
```

<span data-ttu-id="5fc18-187">Weitere Informationen zum PowerShell-Alias Anbieter erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="5fc18-187">For more information about the PowerShell Alias provider, type:</span></span>

```powershell
Get-Help Alias
```

## <a name="see-also"></a><span data-ttu-id="5fc18-188">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="5fc18-188">SEE ALSO</span></span>

- [<span data-ttu-id="5fc18-189">New-Alias</span><span class="sxs-lookup"><span data-stu-id="5fc18-189">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="5fc18-190">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="5fc18-190">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="5fc18-191">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="5fc18-191">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)
- [<span data-ttu-id="5fc18-192">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="5fc18-192">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="5fc18-193">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="5fc18-193">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="5fc18-194">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="5fc18-194">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)
- [<span data-ttu-id="5fc18-195">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="5fc18-195">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="5fc18-196">about_functions</span><span class="sxs-lookup"><span data-stu-id="5fc18-196">about_functions</span></span>](about_functions.md)
- [<span data-ttu-id="5fc18-197">about_profiles</span><span class="sxs-lookup"><span data-stu-id="5fc18-197">about_profiles</span></span>](about_profiles.md)
- [<span data-ttu-id="5fc18-198">about_providers</span><span class="sxs-lookup"><span data-stu-id="5fc18-198">about_providers</span></span>](about_providers.md)

<!-- External links -->
[aliasinfo]: /dotnet/api/system.management.automation.aliasinfo
