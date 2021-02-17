---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadline
ms.date: 02/16/2021
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: 220b38f51afab619a57473be27b1139b878eb7e9
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563226"
---
# <span data-ttu-id="ff481-103">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="ff481-103">Set-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="ff481-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ff481-104">SYNOPSIS</span></span>
<span data-ttu-id="ff481-105">Bindet Schlüssel an benutzerdefinierte oder psread Line-schlüsselhandlerfunktionen.</span><span class="sxs-lookup"><span data-stu-id="ff481-105">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

## <span data-ttu-id="ff481-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ff481-106">SYNTAX</span></span>

### <span data-ttu-id="ff481-107">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="ff481-107">ScriptBlock</span></span>

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### <span data-ttu-id="ff481-108">Funktion</span><span class="sxs-lookup"><span data-stu-id="ff481-108">Function</span></span>

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## <span data-ttu-id="ff481-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ff481-109">DESCRIPTION</span></span>

<span data-ttu-id="ff481-110">Das- `Set-PSReadLineKeyHandler` Cmdlet passt das Ergebnis an, wenn ein Schlüssel oder eine Sequenz von Schlüsseln gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="ff481-110">The `Set-PSReadLineKeyHandler` cmdlet customizes the result when a key or sequence of keys is pressed.</span></span> <span data-ttu-id="ff481-111">Mit benutzerdefinierten Tastenkombinationen können Sie nahezu alles ausführen, was in einem PowerShell-Skript möglich ist.</span><span class="sxs-lookup"><span data-stu-id="ff481-111">With user-defined key bindings, you can do almost anything that is possible from within a PowerShell script.</span></span>

## <span data-ttu-id="ff481-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ff481-112">EXAMPLES</span></span>

### <span data-ttu-id="ff481-113">Beispiel 1: Binden der Pfeiltaste an eine Funktion</span><span class="sxs-lookup"><span data-stu-id="ff481-113">Example 1: Bind the arrow key to a function</span></span>

<span data-ttu-id="ff481-114">Mit diesem Befehl wird die nach-oben-Taste an die **historysearchrückwärts** -Funktion gebunden.</span><span class="sxs-lookup"><span data-stu-id="ff481-114">This command binds the up arrow key to the **HistorySearchBackward** function.</span></span> <span data-ttu-id="ff481-115">Diese Funktion durchsucht den Befehlsverlauf nach Befehlszeilen, die mit dem aktuellen Inhalt der Befehlszeile beginnen.</span><span class="sxs-lookup"><span data-stu-id="ff481-115">This function searches command history for command lines that start with the current contents of the command line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### <span data-ttu-id="ff481-116">Beispiel 2: Binden eines Schlüssels an einen Skriptblock</span><span class="sxs-lookup"><span data-stu-id="ff481-116">Example 2: Bind a key to a script block</span></span>

<span data-ttu-id="ff481-117">Dieses Beispiel zeigt, wie ein einzelner Schlüssel zum Ausführen eines Befehls verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ff481-117">This example shows how a single key can be used to run a command.</span></span> <span data-ttu-id="ff481-118">Mit dem Befehl wird der Schlüssel `Ctrl+B` an einen Skriptblock gebunden, der die Zeile löscht, das Wort "Build" einfügt und dann die Zeile annimmt.</span><span class="sxs-lookup"><span data-stu-id="ff481-118">The command binds the key `Ctrl+B` to a script block that clears the line, inserts the word "build", and then accepts the line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## <span data-ttu-id="ff481-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ff481-119">PARAMETERS</span></span>

### <span data-ttu-id="ff481-120">-Briefdescription</span><span class="sxs-lookup"><span data-stu-id="ff481-120">-BriefDescription</span></span>

<span data-ttu-id="ff481-121">Eine kurze Beschreibung der schlüsselbindung.</span><span class="sxs-lookup"><span data-stu-id="ff481-121">A brief description of the key binding.</span></span> <span data-ttu-id="ff481-122">Diese Beschreibung wird vom `Get-PSReadLineKeyHandler` Cmdlet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff481-122">This description is displayed by the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="ff481-123">-Akkord</span><span class="sxs-lookup"><span data-stu-id="ff481-123">-Chord</span></span>

<span data-ttu-id="ff481-124">Der Schlüssel oder die Sequenz von Schlüsseln, die an eine Funktion oder einen Skriptblock gebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff481-124">The key or sequence of keys to be bound to a function or script block.</span></span> <span data-ttu-id="ff481-125">Verwenden Sie eine einzelne Zeichenfolge, um eine einzelne Bindung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ff481-125">Use a single string to specify a single binding.</span></span> <span data-ttu-id="ff481-126">Wenn die Bindung eine Sequenz von Schlüsseln ist, trennen Sie die Schlüssel durch ein Komma, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ff481-126">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+X,Ctrl+L`

> [!NOTE]
> <span data-ttu-id="ff481-127">Ab psread Line 2.0.0 **wird die** **Groß-/Kleinschreibung** berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="ff481-127">As of PSReadLine 2.0.0, the **Chord** parameter is **case-sensitive**.</span></span> <span data-ttu-id="ff481-128">Dies bedeutet, dass `Ctrl+X` `Ctrl+x` unterschiedliche Bindungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff481-128">Meaning, `Ctrl+X` and `Ctrl+x` will create different bindings.</span></span>

<span data-ttu-id="ff481-129">Dieser Parameter akzeptiert ein Array von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="ff481-129">This parameter accepts an array of strings.</span></span> <span data-ttu-id="ff481-130">Jede Zeichenfolge ist eine separate Bindung und keine Sequenz von Schlüsseln für eine einzelne Bindung.</span><span class="sxs-lookup"><span data-stu-id="ff481-130">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="ff481-131">-Description</span><span class="sxs-lookup"><span data-stu-id="ff481-131">-Description</span></span>

<span data-ttu-id="ff481-132">Gibt eine ausführlichere Beschreibung der schlüsselbindung an, die in der Ausgabe des `Get-PSReadLineKeyHandler` Cmdlets sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="ff481-132">Specifies a more detailed description of the key binding that is visible in the output of the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="ff481-133">-Funktion</span><span class="sxs-lookup"><span data-stu-id="ff481-133">-Function</span></span>

<span data-ttu-id="ff481-134">Gibt den Namen eines vorhandenen Schlüssel Handlers an, der von psread Line bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ff481-134">Specifies the name of an existing key handler provided by PSReadLine.</span></span> <span data-ttu-id="ff481-135">Dieser Parameter ermöglicht das erneute Binden vorhandener Schlüsselbindungen oder das Binden eines Handlers, der zurzeit nicht gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="ff481-135">This parameter lets you rebind existing key bindings, or bind a handler that is currently unbound.</span></span>

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

### <span data-ttu-id="ff481-136">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="ff481-136">-ScriptBlock</span></span>

<span data-ttu-id="ff481-137">Gibt einen Skriptblock Wert an, der beim Eintreten des Akkords ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff481-137">Specifies a script block value to run when the chord is entered.</span></span> <span data-ttu-id="ff481-138">Psread Line übergibt einen oder zwei Parameter an diesen Skriptblock.</span><span class="sxs-lookup"><span data-stu-id="ff481-138">PSReadLine passes one or two parameters to this script block.</span></span> <span data-ttu-id="ff481-139">Der erste Parameter ist ein **ConsoleKeyInfo** -Objekt, das den gedrückten Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="ff481-139">The first parameter is a **ConsoleKeyInfo** object representing the key pressed.</span></span> <span data-ttu-id="ff481-140">Das zweite Argument kann je nach Kontext ein beliebiges Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="ff481-140">The second argument can be any object depending on the context.</span></span>

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

### <span data-ttu-id="ff481-141">-Vimode</span><span class="sxs-lookup"><span data-stu-id="ff481-141">-ViMode</span></span>

<span data-ttu-id="ff481-142">Geben Sie den VI-Modus an, für den die Bindung gilt.</span><span class="sxs-lookup"><span data-stu-id="ff481-142">Specify which vi mode the binding applies to.</span></span>

<span data-ttu-id="ff481-143">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ff481-143">Valid values are:</span></span>

- <span data-ttu-id="ff481-144">Insert</span><span class="sxs-lookup"><span data-stu-id="ff481-144">Insert</span></span>
- <span data-ttu-id="ff481-145">Get-Help</span><span class="sxs-lookup"><span data-stu-id="ff481-145">Command</span></span>

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

### <span data-ttu-id="ff481-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ff481-146">CommonParameters</span></span>

<span data-ttu-id="ff481-147">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ff481-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ff481-148">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ff481-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ff481-149">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ff481-149">INPUTS</span></span>

### <span data-ttu-id="ff481-150">Keine</span><span class="sxs-lookup"><span data-stu-id="ff481-150">None</span></span>

<span data-ttu-id="ff481-151">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="ff481-151">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="ff481-152">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ff481-152">OUTPUTS</span></span>

### <span data-ttu-id="ff481-153">Keine</span><span class="sxs-lookup"><span data-stu-id="ff481-153">None</span></span>

<span data-ttu-id="ff481-154">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ff481-154">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ff481-155">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ff481-155">NOTES</span></span>

## <span data-ttu-id="ff481-156">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ff481-156">RELATED LINKS</span></span>

[<span data-ttu-id="ff481-157">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="ff481-157">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="ff481-158">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="ff481-158">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="ff481-159">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="ff481-159">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="ff481-160">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="ff481-160">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
