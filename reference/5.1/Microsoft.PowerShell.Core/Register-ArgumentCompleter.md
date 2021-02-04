---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-argumentcompleter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ArgumentCompleter
ms.openlocfilehash: 963f99f69ff4406f94445841ad020555617dac42
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97490863"
---
# <span data-ttu-id="57370-103">Register-ArgumentCompleter</span><span class="sxs-lookup"><span data-stu-id="57370-103">Register-ArgumentCompleter</span></span>

## <span data-ttu-id="57370-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="57370-104">SYNOPSIS</span></span>

<span data-ttu-id="57370-105">Registriert ein benutzerdefiniertes Argument, das vervollständigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="57370-105">Registers a custom argument completer.</span></span>

## <span data-ttu-id="57370-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="57370-106">SYNTAX</span></span>

### <span data-ttu-id="57370-107">Nativeset</span><span class="sxs-lookup"><span data-stu-id="57370-107">NativeSet</span></span>

```
Register-ArgumentCompleter -CommandName <String[]> -ScriptBlock <ScriptBlock> [-Native]
 [<CommonParameters>]
```

### <span data-ttu-id="57370-108">PowerShellSet</span><span class="sxs-lookup"><span data-stu-id="57370-108">PowerShellSet</span></span>

```
Register-ArgumentCompleter [-CommandName <String[]>] -ParameterName <String>
 -ScriptBlock <ScriptBlock> [<CommonParameters>]
```

## <span data-ttu-id="57370-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="57370-109">DESCRIPTION</span></span>

<span data-ttu-id="57370-110">Mit dem- `Register-ArgumentCompleter` Cmdlet wird ein benutzerdefiniertes Argument zum Vervollständigen registriert.</span><span class="sxs-lookup"><span data-stu-id="57370-110">The `Register-ArgumentCompleter` cmdlet registers a custom argument completer.</span></span> <span data-ttu-id="57370-111">Mit einem Argument Vervollständigung können Sie zur Laufzeit für jeden von Ihnen angegebenen Befehl eine dynamische Vervollständigung der Tab-Taste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="57370-111">An argument completer allows you to provide dynamic tab completion, at run time for any command that you specify.</span></span>

## <span data-ttu-id="57370-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="57370-112">EXAMPLES</span></span>

### <span data-ttu-id="57370-113">Beispiel 1: Registrieren eines Completers für ein benutzerdefiniertes Argument</span><span class="sxs-lookup"><span data-stu-id="57370-113">Example 1: Register a custom argument completer</span></span>

<span data-ttu-id="57370-114">Im folgenden Beispiel wird ein Argument Vervollständigung für den **ID** -Parameter des `Set-TimeZone` Cmdlets registriert.</span><span class="sxs-lookup"><span data-stu-id="57370-114">The following example registers an argument completer for the **Id** parameter of the `Set-TimeZone` cmdlet.</span></span>

```powershell
$scriptBlock = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)

    (Get-TimeZone -ListAvailable).Id | Where-Object {
        $_ -like "$wordToComplete*"
    } | ForEach-Object {
          "'$_'"
    }
}
Register-ArgumentCompleter -CommandName Set-TimeZone -ParameterName Id -ScriptBlock $scriptBlock
```

<span data-ttu-id="57370-115">Mit dem ersten Befehl wird ein Skriptblock erstellt, der die erforderlichen Parameter annimmt, die beim Drücken der <kbd>Tab</kbd>-Taste durch den Benutzer übermittelt werden. Weitere Informationen finden Sie in der Beschreibung des **ScriptBlock** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="57370-115">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="57370-116">Innerhalb des Skript Blocks werden die verfügbaren Werte für die **ID** mithilfe des- `Get-TimeZone` Cmdlets abgerufen.</span><span class="sxs-lookup"><span data-stu-id="57370-116">Within the script block, the available values for **Id** are retrieved using the `Get-TimeZone` cmdlet.</span></span> <span data-ttu-id="57370-117">Die **ID** -Eigenschaft für jede Zeitzone wird an das `Where-Object` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="57370-117">The **Id** property for each Time Zone is piped to the `Where-Object` cmdlet.</span></span> <span data-ttu-id="57370-118">Mit dem- `Where-Object` Cmdlet werden alle IDs herausgefiltert, die nicht mit dem von bereitgestellten Wert beginnen `$wordToComplete` . dieser stellt den Text dar, den der Benutzer vor dem Drücken der <kbd>Registerkarte</kbd>eingegeben hat. Die gefilterten IDs werden an das `ForEach-Object` Cmdlet weitergeleitet, das die einzelnen Werte in Anführungszeichen einschließt, wenn der Wert Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="57370-118">The `Where-Object` cmdlet filters out any ids that do not start with the value provided by `$wordToComplete`, which represents the text the user typed before they pressed <kbd>Tab</kbd>. The filtered ids are piped to the `ForEach-Object` cmdlet which encloses each value in quotes, should the value contain spaces.</span></span>

<span data-ttu-id="57370-119">Mit dem zweiten Befehl wird das Argument Vervollständigung registriert, indem der ScriptBlock, die **Parameter Name** - **ID** und der **CommandName** übergeben werden `Set-TimeZone` .</span><span class="sxs-lookup"><span data-stu-id="57370-119">The second command registers the argument completer by passing the scriptblock, the **ParameterName** **Id** and the **CommandName** `Set-TimeZone`.</span></span>

### <span data-ttu-id="57370-120">Beispiel 2: Hinzufügen von Details zu den Vervollständigungs Werten der Registerkarte</span><span class="sxs-lookup"><span data-stu-id="57370-120">Example 2: Add details to your tab completion values</span></span>

<span data-ttu-id="57370-121">Im folgenden Beispiel wird die Vervollständigung mit der Tab-Taste für den **Name** -Parameter des `Stop-Service` Cmdlets überschrieben</span><span class="sxs-lookup"><span data-stu-id="57370-121">The following example overwrites tab completion for the **Name** parameter of the `Stop-Service` cmdlet and only returns running services.</span></span>

```powershell
$s = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)
    $services = Get-Service | Where-Object {$_.Status -eq "Running" -and $_.Name -like "$wordToComplete*"}
    $services | ForEach-Object {
        New-Object -Type System.Management.Automation.CompletionResult -ArgumentList $_.Name,
            $_.Name,
            "ParameterValue",
            $_.Name
    }
}
Register-ArgumentCompleter -CommandName Stop-Service -ParameterName Name -ScriptBlock $s
```

<span data-ttu-id="57370-122">Mit dem ersten Befehl wird ein Skriptblock erstellt, der die erforderlichen Parameter annimmt, die beim Drücken der <kbd>Tab</kbd>-Taste durch den Benutzer übermittelt werden. Weitere Informationen finden Sie in der Beschreibung des **ScriptBlock** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="57370-122">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="57370-123">Im Skriptblock ruft der erste Befehl alle laufenden Dienste mithilfe des- `Where-Object` Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="57370-123">Within the script block, the first command retrieves all running services using the `Where-Object` cmdlet.</span></span> <span data-ttu-id="57370-124">Die Dienste werden an das `ForEach-Object` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="57370-124">The services are piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="57370-125">Das `ForEach-Object` -Cmdlet erstellt ein neues [`[System.Management.Automation.CompletionResult]`](/dotnet/api/system.management.automation.completionresult) -Objekt und füllt es mit den Werten des aktuellen Dienstanbieter (dargestellt durch die Pipeline Variable `$_` ).</span><span class="sxs-lookup"><span data-stu-id="57370-125">The `ForEach-Object` cmdlet creates a new [`[System.Management.Automation.CompletionResult]`](/dotnet/api/system.management.automation.completionresult) object and populates it with the values of the current service (represented by the pipeline variable `$_`).</span></span>

<span data-ttu-id="57370-126">Mit dem **completionresult** -Objekt können Sie für jeden zurückgegebenen Wert weitere Details angeben:</span><span class="sxs-lookup"><span data-stu-id="57370-126">The **CompletionResult** object allows you to provide additional details to each returned value:</span></span>

- <span data-ttu-id="57370-127">**completiontext** (Zeichenfolge): der Text, der als Ergebnis der automatischen Vervollständigung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="57370-127">**completionText** (String) - The text to be used as the auto completion result.</span></span> <span data-ttu-id="57370-128">Dies ist der Wert, der an den Befehl gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="57370-128">This is the value sent to the command.</span></span>
- <span data-ttu-id="57370-129">**listitemtext** (Zeichenfolge): der Text, der in einer Liste angezeigt werden soll, z. b. wenn der Benutzer <kbd>STRG</kbd>- + <kbd>Taste</kbd>drückt.</span><span class="sxs-lookup"><span data-stu-id="57370-129">**listItemText** (String) - The text to be displayed in a list, such as when the user presses <kbd>Ctrl</kbd>+<kbd>Space</kbd>.</span></span> <span data-ttu-id="57370-130">Diese Option wird nur zur Anzeige verwendet und nicht an den Befehl übermittelt, wenn Sie ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="57370-130">This is used for display only and is not passed to the command when selected.</span></span>
- <span data-ttu-id="57370-131">**ResultType** ([completionresulttype](/dotnet/api/system.management.automation.completionresulttype)): der Typ des Vervollständigungs Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="57370-131">**resultType** ([CompletionResultType](/dotnet/api/system.management.automation.completionresulttype)) - The type of completion result.</span></span>
- <span data-ttu-id="57370-132">**ToolTip** (Zeichenfolge): der Text für die QuickInfo mit Details, die für das Objekt angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="57370-132">**toolTip** (String) - The text for the tooltip with details to be displayed about the object.</span></span>
  <span data-ttu-id="57370-133">Dies ist sichtbar, wenn der Benutzer nach Drücken von <kbd>STRG</kbd> + <kbd>LEERTASTE</kbd>ein Element auswählt.</span><span class="sxs-lookup"><span data-stu-id="57370-133">This is visible when the user selects an item after pressing <kbd>Ctrl</kbd>+<kbd>Space</kbd>.</span></span>

<span data-ttu-id="57370-134">Mit dem letzten Befehl wird veranschaulicht, dass beendete Dienste weiterhin manuell an das `Stop-Service` Cmdlet übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="57370-134">The last command demonstrates that stopped services can still be passed in manually to the `Stop-Service` cmdlet.</span></span> <span data-ttu-id="57370-135">Die Vervollständigung mit der Tab-Taste ist der einzige betroffene Aspekt.</span><span class="sxs-lookup"><span data-stu-id="57370-135">The tab completion is the only aspect affected.</span></span>

### <span data-ttu-id="57370-136">Beispiel 3: Registrieren eines benutzerdefinierten Completers für das Native Argument</span><span class="sxs-lookup"><span data-stu-id="57370-136">Example 3: Register a custom Native argument completer</span></span>

<span data-ttu-id="57370-137">Mit dem systemeigenen **Parameter können** Sie die Vervollständigung mit der Tab-Taste für einen nativen Befehl bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="57370-137">You can use the **Native** parameter to provide tab-completion for a native command.</span></span> <span data-ttu-id="57370-138">Im folgenden Beispiel wird die `dotnet` Befehlszeilenschnittstelle (Command Line Interface, CLI) mit der Befehlszeilenschnittstelle fertiggestellt.</span><span class="sxs-lookup"><span data-stu-id="57370-138">The following example adds tab-completion for the `dotnet` Command Line Interface (CLI).</span></span>

> [!NOTE]
> <span data-ttu-id="57370-139">Der `dotnet complete` Befehl ist nur in Version 2,0 und höher der dotnet-CLI verfügbar.</span><span class="sxs-lookup"><span data-stu-id="57370-139">The `dotnet complete` command is only available in version 2.0 and greater of the dotnet cli.</span></span>

```powershell
$scriptblock = {
    param($wordToComplete, $commandAst, $cursorPosition)
        dotnet complete --position $cursorPosition $commandAst.ToString() | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
        }
}
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock $scriptblock
```

<span data-ttu-id="57370-140">Mit dem ersten Befehl wird ein Skriptblock erstellt, der die erforderlichen Parameter annimmt, die beim Drücken der <kbd>Tab</kbd>-Taste durch den Benutzer übermittelt werden. Weitere Informationen finden Sie in der Beschreibung des **ScriptBlock** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="57370-140">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="57370-141">Innerhalb des Skript Blocks wird der `dotnet complete` Befehl verwendet, um die Vervollständigung mit der Tab-Taste auszuführen.</span><span class="sxs-lookup"><span data-stu-id="57370-141">Within the script block, the `dotnet complete` command is used to perform the tab completion.</span></span>
<span data-ttu-id="57370-142">Die Ergebnisse werden an das `ForEach-Object` Cmdlet weitergeleitet, das die **neue** statische Methode der [System. Management. Automation. completionresult](/dotnet/api/system.management.automation.completionresult) -Klasse verwendet, um ein neues **completionresult** -Objekt für jeden Wert zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57370-142">The results are piped to the `ForEach-Object` cmdlet which use the **new** static method of the [System.Management.Automation.CompletionResult](/dotnet/api/system.management.automation.completionresult) class to create a new **CompletionResult** object for each value.</span></span>

## <span data-ttu-id="57370-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="57370-143">PARAMETERS</span></span>

### <span data-ttu-id="57370-144">-CommandName</span><span class="sxs-lookup"><span data-stu-id="57370-144">-CommandName</span></span>

<span data-ttu-id="57370-145">Gibt den Namen der Befehle als Array an.</span><span class="sxs-lookup"><span data-stu-id="57370-145">Specifies the name of the commands as an array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NativeSet, PowerShellSet
Aliases:

Required: True (NativeSet), False (PowerShellSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="57370-146">-Native</span><span class="sxs-lookup"><span data-stu-id="57370-146">-Native</span></span>

<span data-ttu-id="57370-147">Gibt an, dass das Argument Vervollständigung für einen nativen Befehl gilt, bei dem PowerShell Parameternamen nicht vervollständigen kann.</span><span class="sxs-lookup"><span data-stu-id="57370-147">Indicates that the argument completer is for a native command where PowerShell cannot complete parameter names.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NativeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="57370-148">-Parameter Name</span><span class="sxs-lookup"><span data-stu-id="57370-148">-ParameterName</span></span>

<span data-ttu-id="57370-149">Gibt den Namen des Parameters an, dessen Argument abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="57370-149">Specifies the name of the parameter whose argument is being completed.</span></span> <span data-ttu-id="57370-150">Der angegebene Parameter Name kann kein Enumerationswert sein, z. b. der **ForegroundColor** -Parameter des `Write-Host` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="57370-150">The parameter name specified cannot be an enumerated value, such as the **ForegroundColor** parameter of the `Write-Host` cmdlet.</span></span>

<span data-ttu-id="57370-151">Weitere Informationen zu-Aufständen finden Sie unter [about_Enum](./About/about_Enum.md).</span><span class="sxs-lookup"><span data-stu-id="57370-151">For more information on enums, see [about_Enum](./About/about_Enum.md).</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="57370-152">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="57370-152">-ScriptBlock</span></span>

<span data-ttu-id="57370-153">Gibt die Befehle an, die ausgeführt werden sollen, um die Vervollständigung der</span><span class="sxs-lookup"><span data-stu-id="57370-153">Specifies the commands to run to perform tab completion.</span></span> <span data-ttu-id="57370-154">Der von Ihnen bereitgestellte Skriptblock sollte die Werte zurückgeben, die die Eingabe vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="57370-154">The script block you provide should return the values that complete the input.</span></span> <span data-ttu-id="57370-155">Der Skriptblock muss die Registrierung der Werte mithilfe der Pipeline ( `ForEach-Object` , `Where-Object` , usw.) oder einer anderen geeigneten Methode aufheben.</span><span class="sxs-lookup"><span data-stu-id="57370-155">The script block must unroll the values using the pipeline (`ForEach-Object`, `Where-Object`, etc.), or another suitable method.</span></span> <span data-ttu-id="57370-156">Das Zurückgeben eines Arrays von Werten bewirkt, dass PowerShell das gesamte Array als **einen** Vervollständigungs Wert mit der Tab-Taste behandelt.</span><span class="sxs-lookup"><span data-stu-id="57370-156">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="57370-157">Der Skriptblock muss die folgenden Parameter in der unten angegebenen Reihenfolge akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="57370-157">The script block must accept the following parameters in the order specified below.</span></span> <span data-ttu-id="57370-158">Die Namen der Parameter sind nicht wichtig, da PowerShell die Werte nach Position übergibt.</span><span class="sxs-lookup"><span data-stu-id="57370-158">The names of the parameters aren't important because PowerShell passes in the values by position.</span></span>

- <span data-ttu-id="57370-159">`$commandName` (Position 0): dieser Parameter wird auf den Namen des Befehls festgelegt, für den der Skriptblock die Vervollständigung mit der Tab-Taste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="57370-159">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="57370-160">`$parameterName` (Position 1): dieser Parameter ist auf den Parameter festgelegt, dessen Wert die Vervollständigung der Tab-Taste erfordert.</span><span class="sxs-lookup"><span data-stu-id="57370-160">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="57370-161">`$wordToComplete` (Position 2): dieser Parameter ist auf den Wert festgelegt, den der Benutzer vor dem Drücken der <kbd>Tab</kbd>-Taste angegeben hat. Der Skriptblock sollte diesen Wert verwenden, um die Vervollständigungs Werte der Registerkarte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="57370-161">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="57370-162">`$commandAst` (Position 3): dieser Parameter ist für die aktuelle Eingabezeile auf die abstrakte Syntax Struktur (AST, Abstract Syntax Tree) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="57370-162">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="57370-163">Weitere Informationen finden Sie unter [AST-Klasse](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="57370-163">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="57370-164">`$fakeBoundParameters` (Position 4): dieser Parameter wird auf eine Hash Tabelle festgelegt, die den `$PSBoundParameters` für das Cmdlet enthält, bevor der Benutzer die <kbd>Tab</kbd>-Taste gedrückt hat. Weitere Informationen finden Sie unter [about_Automatic_Variables](./About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="57370-164">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](./About/about_Automatic_Variables.md).</span></span>

<span data-ttu-id="57370-165">Wenn Sie den **nativen** Parameter angeben, muss der Skriptblock die folgenden Parameter in der angegebenen Reihenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="57370-165">When you specify the **Native** parameter, the script block must take the following parameters in the specified order.</span></span> <span data-ttu-id="57370-166">Die Namen der Parameter sind nicht wichtig, da PowerShell die Werte nach Position übergibt.</span><span class="sxs-lookup"><span data-stu-id="57370-166">The names of the parameters aren't important because PowerShell passes in the values by position.</span></span>

- <span data-ttu-id="57370-167">`$wordToComplete` (Position 0): dieser Parameter ist auf den Wert festgelegt, den der Benutzer vor dem Drücken der <kbd>Tab</kbd>-Taste angegeben hat. Der Skriptblock sollte diesen Wert verwenden, um die Vervollständigungs Werte der Registerkarte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="57370-167">`$wordToComplete` (Position 0) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="57370-168">`$commandAst` (Position 1): dieser Parameter wird auf die abstrakte Syntax Struktur (AST) für die aktuelle Eingabezeile festgelegt.</span><span class="sxs-lookup"><span data-stu-id="57370-168">`$commandAst` (Position 1) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="57370-169">Weitere Informationen finden Sie unter [AST-Klasse](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="57370-169">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="57370-170">`$cursorPosition` (Position 2): dieser Parameter wird auf die Position des Cursors festgelegt, wenn der Benutzer die <kbd>Tab</kbd>-Taste gedrückt hat.</span><span class="sxs-lookup"><span data-stu-id="57370-170">`$cursorPosition` (Position 2) - This parameter is set to the position of the cursor when the user pressed <kbd>Tab</kbd>.</span></span>

<span data-ttu-id="57370-171">Sie können auch **argumentcompleter** als Parameter Attribut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="57370-171">You can also provide an **ArgumentCompleter** as a parameter attribute.</span></span> <span data-ttu-id="57370-172">Weitere Informationen finden Sie unter [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="57370-172">For more information, see [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="57370-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="57370-173">CommonParameters</span></span>

<span data-ttu-id="57370-174">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="57370-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="57370-175">Weitere Informationen findest du unter [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="57370-175">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="57370-176">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="57370-176">INPUTS</span></span>

### <span data-ttu-id="57370-177">Keine</span><span class="sxs-lookup"><span data-stu-id="57370-177">None</span></span>

<span data-ttu-id="57370-178">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="57370-178">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="57370-179">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="57370-179">OUTPUTS</span></span>

### <span data-ttu-id="57370-180">Keine</span><span class="sxs-lookup"><span data-stu-id="57370-180">None</span></span>

<span data-ttu-id="57370-181">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="57370-181">This cmdlet returns no output.</span></span>

## <span data-ttu-id="57370-182">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="57370-182">NOTES</span></span>

## <span data-ttu-id="57370-183">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="57370-183">RELATED LINKS</span></span>
