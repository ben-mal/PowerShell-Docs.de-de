---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 02/16/2021
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: 86386cb8d97e16ebdd869e2ec554fc947d788f67
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563283"
---
# <span data-ttu-id="f95cc-102">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="f95cc-102">Set-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="f95cc-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f95cc-103">SYNOPSIS</span></span>
<span data-ttu-id="f95cc-104">Bindet Schlüssel an benutzerdefinierte oder psread Line-schlüsselhandlerfunktionen.</span><span class="sxs-lookup"><span data-stu-id="f95cc-104">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

## <span data-ttu-id="f95cc-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f95cc-105">SYNTAX</span></span>

### <span data-ttu-id="f95cc-106">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="f95cc-106">ScriptBlock</span></span>

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### <span data-ttu-id="f95cc-107">Funktion</span><span class="sxs-lookup"><span data-stu-id="f95cc-107">Function</span></span>

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## <span data-ttu-id="f95cc-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f95cc-108">DESCRIPTION</span></span>

<span data-ttu-id="f95cc-109">Das- `Set-PSReadLineKeyHandler` Cmdlet passt das Ergebnis an, wenn ein Schlüssel oder eine Sequenz von Schlüsseln gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="f95cc-109">The `Set-PSReadLineKeyHandler` cmdlet customizes the result when a key or sequence of keys is pressed.</span></span> <span data-ttu-id="f95cc-110">Mit benutzerdefinierten Tastenkombinationen können Sie nahezu alles ausführen, was in einem PowerShell-Skript möglich ist.</span><span class="sxs-lookup"><span data-stu-id="f95cc-110">With user-defined key bindings, you can do almost anything that is possible from within a PowerShell script.</span></span>

## <span data-ttu-id="f95cc-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f95cc-111">EXAMPLES</span></span>

### <span data-ttu-id="f95cc-112">Beispiel 1: Binden der Pfeiltaste an eine Funktion</span><span class="sxs-lookup"><span data-stu-id="f95cc-112">Example 1: Bind the arrow key to a function</span></span>

<span data-ttu-id="f95cc-113">Mit diesem Befehl wird die nach-oben-Taste an die **historysearchrückwärts** -Funktion gebunden.</span><span class="sxs-lookup"><span data-stu-id="f95cc-113">This command binds the up arrow key to the **HistorySearchBackward** function.</span></span> <span data-ttu-id="f95cc-114">Diese Funktion durchsucht den Befehlsverlauf nach Befehlszeilen, die mit dem aktuellen Inhalt der Befehlszeile beginnen.</span><span class="sxs-lookup"><span data-stu-id="f95cc-114">This function searches command history for command lines that start with the current contents of the command line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### <span data-ttu-id="f95cc-115">Beispiel 2: Binden eines Schlüssels an einen Skriptblock</span><span class="sxs-lookup"><span data-stu-id="f95cc-115">Example 2: Bind a key to a script block</span></span>

<span data-ttu-id="f95cc-116">Dieses Beispiel zeigt, wie ein einzelner Schlüssel zum Ausführen eines Befehls verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f95cc-116">This example shows how a single key can be used to run a command.</span></span> <span data-ttu-id="f95cc-117">Mit dem Befehl wird der Schlüssel `Ctrl+B` an einen Skriptblock gebunden, der die Zeile löscht, das Wort "Build" einfügt und dann die Zeile annimmt.</span><span class="sxs-lookup"><span data-stu-id="f95cc-117">The command binds the key `Ctrl+B` to a script block that clears the line, inserts the word "build", and then accepts the line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## <span data-ttu-id="f95cc-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f95cc-118">PARAMETERS</span></span>

### <span data-ttu-id="f95cc-119">-Briefdescription</span><span class="sxs-lookup"><span data-stu-id="f95cc-119">-BriefDescription</span></span>

<span data-ttu-id="f95cc-120">Eine kurze Beschreibung der schlüsselbindung.</span><span class="sxs-lookup"><span data-stu-id="f95cc-120">A brief description of the key binding.</span></span> <span data-ttu-id="f95cc-121">Diese Beschreibung wird vom `Get-PSReadLineKeyHandler` Cmdlet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f95cc-121">This description is displayed by the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f95cc-122">-Akkord</span><span class="sxs-lookup"><span data-stu-id="f95cc-122">-Chord</span></span>

<span data-ttu-id="f95cc-123">Der Schlüssel oder die Sequenz von Schlüsseln, die an eine Funktion oder einen Skriptblock gebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f95cc-123">The key or sequence of keys to be bound to a function or script block.</span></span> <span data-ttu-id="f95cc-124">Verwenden Sie eine einzelne Zeichenfolge, um eine einzelne Bindung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f95cc-124">Use a single string to specify a single binding.</span></span> <span data-ttu-id="f95cc-125">Wenn die Bindung eine Sequenz von Schlüsseln ist, trennen Sie die Schlüssel durch ein Komma, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f95cc-125">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+X,Ctrl+L`

> [!NOTE]
> <span data-ttu-id="f95cc-126">Ab psread Line 2.0.0 **wird die** **Groß-/Kleinschreibung** berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="f95cc-126">As of PSReadLine 2.0.0, the **Chord** parameter is **case-sensitive**.</span></span> <span data-ttu-id="f95cc-127">Dies bedeutet, dass `Ctrl+X` `Ctrl+x` unterschiedliche Bindungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f95cc-127">Meaning, `Ctrl+X` and `Ctrl+x` will create different bindings.</span></span>

<span data-ttu-id="f95cc-128">Dieser Parameter akzeptiert ein Array von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="f95cc-128">This parameter accepts an array of strings.</span></span> <span data-ttu-id="f95cc-129">Jede Zeichenfolge ist eine separate Bindung und keine Sequenz von Schlüsseln für eine einzelne Bindung.</span><span class="sxs-lookup"><span data-stu-id="f95cc-129">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f95cc-130">-Description</span><span class="sxs-lookup"><span data-stu-id="f95cc-130">-Description</span></span>

<span data-ttu-id="f95cc-131">Gibt eine ausführlichere Beschreibung der schlüsselbindung an, die in der Ausgabe des `Get-PSReadLineKeyHandler` Cmdlets sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="f95cc-131">Specifies a more detailed description of the key binding that is visible in the output of the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases: LongDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f95cc-132">-Funktion</span><span class="sxs-lookup"><span data-stu-id="f95cc-132">-Function</span></span>

<span data-ttu-id="f95cc-133">Gibt den Namen eines vorhandenen Schlüssel Handlers an, der von psread Line bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f95cc-133">Specifies the name of an existing key handler provided by PSReadLine.</span></span> <span data-ttu-id="f95cc-134">Dieser Parameter ermöglicht das erneute Binden vorhandener Schlüsselbindungen oder das Binden eines Handlers, der zurzeit nicht gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="f95cc-134">This parameter lets you rebind existing key bindings, or bind a handler that is currently unbound.</span></span>

```yaml
Type: System.String
Parameter Sets: Function
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f95cc-135">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="f95cc-135">-ScriptBlock</span></span>

<span data-ttu-id="f95cc-136">Gibt einen Skriptblock Wert an, der beim Eintreten des Akkords ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f95cc-136">Specifies a script block value to run when the chord is entered.</span></span> <span data-ttu-id="f95cc-137">Psread Line übergibt einen oder zwei Parameter an diesen Skriptblock.</span><span class="sxs-lookup"><span data-stu-id="f95cc-137">PSReadLine passes one or two parameters to this script block.</span></span> <span data-ttu-id="f95cc-138">Der erste Parameter ist ein **ConsoleKeyInfo** -Objekt, das den gedrückten Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="f95cc-138">The first parameter is a **ConsoleKeyInfo** object representing the key pressed.</span></span> <span data-ttu-id="f95cc-139">Das zweite Argument kann je nach Kontext ein beliebiges Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="f95cc-139">The second argument can be any object depending on the context.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f95cc-140">-Vimode</span><span class="sxs-lookup"><span data-stu-id="f95cc-140">-ViMode</span></span>

<span data-ttu-id="f95cc-141">Geben Sie den VI-Modus an, für den die Bindung gilt.</span><span class="sxs-lookup"><span data-stu-id="f95cc-141">Specify which vi mode the binding applies to.</span></span>

<span data-ttu-id="f95cc-142">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="f95cc-142">Valid values are:</span></span>

- <span data-ttu-id="f95cc-143">Insert</span><span class="sxs-lookup"><span data-stu-id="f95cc-143">Insert</span></span>
- <span data-ttu-id="f95cc-144">Get-Help</span><span class="sxs-lookup"><span data-stu-id="f95cc-144">Command</span></span>

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f95cc-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f95cc-145">CommonParameters</span></span>

<span data-ttu-id="f95cc-146">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f95cc-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f95cc-147">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f95cc-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f95cc-148">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f95cc-148">INPUTS</span></span>

### <span data-ttu-id="f95cc-149">Keine</span><span class="sxs-lookup"><span data-stu-id="f95cc-149">None</span></span>

<span data-ttu-id="f95cc-150">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="f95cc-150">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="f95cc-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f95cc-151">OUTPUTS</span></span>

### <span data-ttu-id="f95cc-152">Keine</span><span class="sxs-lookup"><span data-stu-id="f95cc-152">None</span></span>

<span data-ttu-id="f95cc-153">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="f95cc-153">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f95cc-154">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f95cc-154">NOTES</span></span>

## <span data-ttu-id="f95cc-155">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f95cc-155">RELATED LINKS</span></span>

[<span data-ttu-id="f95cc-156">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="f95cc-156">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="f95cc-157">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="f95cc-157">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="f95cc-158">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="f95cc-158">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="f95cc-159">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="f95cc-159">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

