---
description: Erläutert Datenabschnitte, die Text Zeichenfolgen und andere schreibgeschützte Daten aus Skript Logik isolieren.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_data_sections?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Data_Sections
ms.openlocfilehash: a5eed0056fe572760415f62537b5a69942d819ae
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222119"
---
# <a name="about-data-sections"></a><span data-ttu-id="8db00-104">Informationen zu Daten Abschnitten</span><span class="sxs-lookup"><span data-stu-id="8db00-104">About Data Sections</span></span>

## <a name="short-description"></a><span data-ttu-id="8db00-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8db00-105">Short Description</span></span>
<span data-ttu-id="8db00-106">Erläutert Datenabschnitte, die Text Zeichenfolgen und andere schreibgeschützte Daten aus Skript Logik isolieren.</span><span class="sxs-lookup"><span data-stu-id="8db00-106">Explains Data sections, which isolate text strings and other read-only data from script logic.</span></span>

## <a name="long-description"></a><span data-ttu-id="8db00-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8db00-107">Long Description</span></span>

<span data-ttu-id="8db00-108">Skripts, die für PowerShell entwickelt wurden, können über einen oder mehrere Datenabschnitte verfügen, die nur Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="8db00-108">Scripts that are designed for PowerShell can have one or more Data sections that contain only data.</span></span> <span data-ttu-id="8db00-109">Sie können einen oder mehrere Datenabschnitte in beliebige Skripts, Funktionen oder erweiterte Funktionen einschließen.</span><span class="sxs-lookup"><span data-stu-id="8db00-109">You can include one or more Data sections in any script, function, or advanced function.</span></span> <span data-ttu-id="8db00-110">Der Inhalt des Abschnitts Daten ist auf eine bestimmte Teilmenge der PowerShell-Skriptsprache beschränkt.</span><span class="sxs-lookup"><span data-stu-id="8db00-110">The content of the Data section is restricted to a specified subset of the PowerShell scripting language.</span></span>

<span data-ttu-id="8db00-111">Durch das Aufteilen von Daten aus Code Logik wird die Identifizierung und Verwaltung von Logik und Daten vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="8db00-111">Separating data from code logic makes it easier to identify and manage both logic and data.</span></span> <span data-ttu-id="8db00-112">Sie können separate Zeichen folgen-Ressourcen Dateien für Text wie z. b. Fehlermeldungen und Hilfe Zeichenfolgen haben.</span><span class="sxs-lookup"><span data-stu-id="8db00-112">It lets you have separate string resource files for text, such as error messages and Help strings.</span></span> <span data-ttu-id="8db00-113">Außerdem wird die Codelogik isoliert, die Sicherheits-und Validierungstests erleichtert.</span><span class="sxs-lookup"><span data-stu-id="8db00-113">It also isolates the code logic, which facilitates security and validation tests.</span></span>

<span data-ttu-id="8db00-114">In PowerShell wird der Abschnitt "Data" verwendet, um die Skript Internationalisierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8db00-114">In PowerShell, the Data section is used to support script internationalization.</span></span>
<span data-ttu-id="8db00-115">Mithilfe von Daten Abschnitten können Sie Zeichen folgen, die in viele Benutzeroberflächen Sprachen (UI) übersetzt werden, einfacher isolieren, Auffinden und verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8db00-115">You can use Data sections to make it easier to isolate, locate, and process strings that will be translated into many user interface (UI) languages.</span></span>

<span data-ttu-id="8db00-116">Der Abschnitt "Data" ist eine PowerShell-Funktion 2,0.</span><span class="sxs-lookup"><span data-stu-id="8db00-116">The Data section is a PowerShell 2.0 feature.</span></span> <span data-ttu-id="8db00-117">Skripts mit Daten Abschnitten können nicht in PowerShell 1,0 ohne Revision ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8db00-117">Scripts with Data sections will not run in PowerShell 1.0 without revision.</span></span>

### <a name="syntax"></a><span data-ttu-id="8db00-118">Syntax</span><span class="sxs-lookup"><span data-stu-id="8db00-118">Syntax</span></span>

<span data-ttu-id="8db00-119">Die Syntax für einen Daten Abschnitt lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8db00-119">The syntax for a Data section is as follows:</span></span>

```
DATA [<variable-name>] [-supportedCommand <cmdlet-name>] {
    <Permitted content>
}
```

<span data-ttu-id="8db00-120">Das Schlüsselwort "Data" ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8db00-120">The Data keyword is required.</span></span> <span data-ttu-id="8db00-121">Es wird nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="8db00-121">It is not case-sensitive.</span></span> <span data-ttu-id="8db00-122">Der zulässige Inhalt ist auf die folgenden Elemente beschränkt:</span><span class="sxs-lookup"><span data-stu-id="8db00-122">The permitted content is limited to the following elements:</span></span>

- <span data-ttu-id="8db00-123">Alle PowerShell-Operatoren, außer `-match`</span><span class="sxs-lookup"><span data-stu-id="8db00-123">All PowerShell operators, except `-match`</span></span>
- <span data-ttu-id="8db00-124">`If``Else`-,-und- `ElseIf` Anweisungen</span><span class="sxs-lookup"><span data-stu-id="8db00-124">`If`, `Else`, and `ElseIf` statements</span></span>
- <span data-ttu-id="8db00-125">Die folgenden automatischen Variablen: `$PsCulture` , `$PsUICulture` , `$True` , `$False` und. `$Null`</span><span class="sxs-lookup"><span data-stu-id="8db00-125">The following automatic variables: `$PsCulture`, `$PsUICulture`, `$True`, `$False`, and `$Null`</span></span>
- <span data-ttu-id="8db00-126">Kommentare</span><span class="sxs-lookup"><span data-stu-id="8db00-126">Comments</span></span>
- <span data-ttu-id="8db00-127">Pipelines</span><span class="sxs-lookup"><span data-stu-id="8db00-127">Pipelines</span></span>
- <span data-ttu-id="8db00-128">Durch Semikolons getrennte Anweisungen ( `;` )</span><span class="sxs-lookup"><span data-stu-id="8db00-128">Statements separated by semicolons (`;`)</span></span>
- <span data-ttu-id="8db00-129">Literale, wie z. b. die folgenden:</span><span class="sxs-lookup"><span data-stu-id="8db00-129">Literals, such as the following:</span></span>

  ```powershell
  a
  1
  1,2,3
  "PowerShell 2.0"
  @( "red", "green", "blue" )
  @{ a = 0x1; b = "great"; c ="script" }
  [XML] @'
  <p> Hello, World </p>
  '@
  ```

- <span data-ttu-id="8db00-130">Cmdlets, die in einem Daten Abschnitt zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="8db00-130">Cmdlets that are permitted in a Data section.</span></span> <span data-ttu-id="8db00-131">Standardmäßig ist nur das `ConvertFrom-StringData` Cmdlet zulässig.</span><span class="sxs-lookup"><span data-stu-id="8db00-131">By default, only the `ConvertFrom-StringData` cmdlet is permitted.</span></span>
- <span data-ttu-id="8db00-132">-Cmdlets, die Sie in einem Daten Abschnitt mithilfe des- `-SupportedCommand` Parameters zulassen.</span><span class="sxs-lookup"><span data-stu-id="8db00-132">Cmdlets that you permit in a Data section by using the `-SupportedCommand` parameter.</span></span>

<span data-ttu-id="8db00-133">Wenn Sie das `ConvertFrom-StringData` Cmdlet in einem Daten Abschnitt verwenden, können Sie die Schlüssel-Wert-Paare in Zeichen folgen in einfachen Anführungszeichen oder in Zeichen folgen mit nur einem oder zwei Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="8db00-133">When you use the `ConvertFrom-StringData` cmdlet in a Data section, you can enclose the key-value pairs in single-quoted or double-quoted strings or in single-quoted or double-quoted here-strings.</span></span> <span data-ttu-id="8db00-134">Zeichen folgen, die Variablen und Teil Ausdrücke enthalten, müssen jedoch in Zeichen folgen in einfachen Anführungszeichen oder in einfachen Zeichen folgen eingeschlossen werden, damit die Variablen nicht erweitert werden und die Teil Ausdrücke nicht ausführbar sind.</span><span class="sxs-lookup"><span data-stu-id="8db00-134">However, strings that contain variables and subexpressions must be enclosed in single-quoted strings or in single-quoted here-strings so that the variables are not expanded and the subexpressions are not executable.</span></span>

### <a name="-supportedcommand"></a><span data-ttu-id="8db00-135">-Supportedcommand</span><span class="sxs-lookup"><span data-stu-id="8db00-135">-SupportedCommand</span></span>

<span data-ttu-id="8db00-136">Mit dem- `-SupportedCommand` Parameter können Sie angeben, dass ein Cmdlet oder eine Funktion nur Daten generiert.</span><span class="sxs-lookup"><span data-stu-id="8db00-136">The `-SupportedCommand` parameter allows you to indicate that a cmdlet or function generates only data.</span></span> <span data-ttu-id="8db00-137">Es ist so konzipiert, dass Benutzer Cmdlets und Funktionen in einen Daten Abschnitt einschließen können, den Sie geschrieben oder getestet haben.</span><span class="sxs-lookup"><span data-stu-id="8db00-137">It is designed to allow users to include cmdlets and functions in a data section that they have written or tested.</span></span>

<span data-ttu-id="8db00-138">Der Wert von `-SupportedCommand` ist eine durch Trennzeichen getrennte Liste mit einem oder mehreren Cmdlet-oder Funktionsnamen.</span><span class="sxs-lookup"><span data-stu-id="8db00-138">The value of `-SupportedCommand` is a comma-separated list of one or more cmdlet or function names.</span></span>

<span data-ttu-id="8db00-139">Der folgende Daten Abschnitt enthält z. b. ein vom Benutzer geschriebenes Cmdlet, `Format-XML` , das Daten in einer XML-Datei formatiert:</span><span class="sxs-lookup"><span data-stu-id="8db00-139">For example, the following data section includes a user-written cmdlet, `Format-XML`, that formats data in an XML file:</span></span>

```powershell
DATA -supportedCommand Format-Xml
{
    Format-Xml -Strings string1, string2, string3
}
```

### <a name="using-a-data-section"></a><span data-ttu-id="8db00-140">Verwenden eines Daten Abschnitts</span><span class="sxs-lookup"><span data-stu-id="8db00-140">Using a Data Section</span></span>

<span data-ttu-id="8db00-141">Um den Inhalt eines Daten Abschnitts zu verwenden, weisen Sie ihn einer Variablen zu, und verwenden Sie Variablen Notation, um auf den Inhalt zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="8db00-141">To use the content of a Data section, assign it to a variable and use variable notation to access the content.</span></span>

<span data-ttu-id="8db00-142">Beispielsweise enthält der folgende Daten Abschnitt einen `ConvertFrom-StringData` Befehl, der die here-Zeichenfolge in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="8db00-142">For example, the following data section contains a `ConvertFrom-StringData` command that converts the here-string into a hash table.</span></span> <span data-ttu-id="8db00-143">Die Hash Tabelle wird der Variablen zugewiesen `$TextMsgs` .</span><span class="sxs-lookup"><span data-stu-id="8db00-143">The hash table is assigned to the `$TextMsgs` variable.</span></span>

<span data-ttu-id="8db00-144">Die `$TextMsgs` Variable ist nicht Teil des Daten Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="8db00-144">The `$TextMsgs` variable is not part of the data section.</span></span>

```powershell
$TextMsgs = DATA {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

<span data-ttu-id="8db00-145">Verwenden Sie die folgenden Befehle, um auf die Schlüssel und Werte in der Hash Tabelle in zuzugreifen `$TextMsgs` .</span><span class="sxs-lookup"><span data-stu-id="8db00-145">To access the keys and values in hash table in `$TextMsgs`, use the following commands.</span></span>

```powershell
$TextMsgs.Text001
$TextMsgs.Text002
```

<span data-ttu-id="8db00-146">Alternativ können Sie den Variablennamen in der Definition des Daten Abschnitts ablegen.</span><span class="sxs-lookup"><span data-stu-id="8db00-146">Alternately, you can put the variable name in the definition of the Data section.</span></span> <span data-ttu-id="8db00-147">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8db00-147">For example:</span></span>

```powershell
DATA TextMsgs {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}

$TextMsgs
```

<span data-ttu-id="8db00-148">Das Ergebnis ist das gleiche wie das vorherige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="8db00-148">The result is the same as the previous example.</span></span>

```Output
Name                           Value
----                           -----
Text001                        Windows 7
Text002                        Windows Server 2008 R2
```

### <a name="examples"></a><span data-ttu-id="8db00-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8db00-149">Examples</span></span>

<span data-ttu-id="8db00-150">Einfache Daten Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="8db00-150">Simple data strings.</span></span>

```powershell
DATA {
    "Thank you for using my PowerShell Organize.pst script."
    "It is provided free of charge to the community."
    "I appreciate your comments and feedback."
}
```

<span data-ttu-id="8db00-151">Zeichen folgen, die zugelassene Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8db00-151">Strings that include permitted variables.</span></span>

```powershell
DATA {
    if ($null) {
        "To get help for this cmdlet, type get-help new-dictionary."
    }
}
```

<span data-ttu-id="8db00-152">Eine here-Zeichenfolge in einfachen Anführungszeichen, die das `ConvertFrom-StringData` Cmdlet verwendet:</span><span class="sxs-lookup"><span data-stu-id="8db00-152">A single-quoted here-string that uses the `ConvertFrom-StringData` cmdlet:</span></span>

```powershell
DATA {
    ConvertFrom-StringData -stringdata @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

<span data-ttu-id="8db00-153">Eine here-Zeichenfolge mit doppelten Anführungszeichen, die das `ConvertFrom-StringData` Cmdlet verwendet:</span><span class="sxs-lookup"><span data-stu-id="8db00-153">A double-quoted here-string that uses the `ConvertFrom-StringData` cmdlet:</span></span>

```powershell
DATA  {
    ConvertFrom-StringData -stringdata @"
Msg1 = To start, press any key.
Msg2 = To exit, type "quit".
"@
}
```

<span data-ttu-id="8db00-154">Ein Daten Abschnitt, der ein vom Benutzer geschriebenes Cmdlet enthält, das Daten generiert:</span><span class="sxs-lookup"><span data-stu-id="8db00-154">A data section that includes a user-written cmdlet that generates data:</span></span>

```powershell
DATA -supportedCommand Format-XML {
    Format-Xml -strings string1, string2, string3
}
```

## <a name="see-also"></a><span data-ttu-id="8db00-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8db00-155">See Also</span></span>

[<span data-ttu-id="8db00-156">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="8db00-156">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="8db00-157">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="8db00-157">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="8db00-158">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="8db00-158">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="8db00-159">about_If</span><span class="sxs-lookup"><span data-stu-id="8db00-159">about_If</span></span>](about_If.md)

[<span data-ttu-id="8db00-160">about_Operators</span><span class="sxs-lookup"><span data-stu-id="8db00-160">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="8db00-161">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="8db00-161">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="8db00-162">about_Script_Internationalization</span><span class="sxs-lookup"><span data-stu-id="8db00-162">about_Script_Internationalization</span></span>](about_Script_Internationalization.md)

[<span data-ttu-id="8db00-163">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="8db00-163">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[<span data-ttu-id="8db00-164">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="8db00-164">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

