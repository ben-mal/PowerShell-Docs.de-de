---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: 7794fc8814364d3ee62b0dece787aa0213dc4ff3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214908"
---
# <span data-ttu-id="88c6a-103">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="88c6a-103">Set-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="88c6a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="88c6a-104">SYNOPSIS</span></span>
<span data-ttu-id="88c6a-105">Bindet Schlüssel an benutzerdefinierte oder psread Line-schlüsselhandlerfunktionen.</span><span class="sxs-lookup"><span data-stu-id="88c6a-105">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

## <span data-ttu-id="88c6a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="88c6a-106">SYNTAX</span></span>

### <span data-ttu-id="88c6a-107">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="88c6a-107">ScriptBlock</span></span>

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### <span data-ttu-id="88c6a-108">Funktion</span><span class="sxs-lookup"><span data-stu-id="88c6a-108">Function</span></span>

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## <span data-ttu-id="88c6a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="88c6a-109">DESCRIPTION</span></span>

<span data-ttu-id="88c6a-110">Das- `Set-PSReadLineKeyHandler` Cmdlet passt das Ergebnis an, wenn ein Schlüssel oder eine Sequenz von Schlüsseln gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="88c6a-110">The `Set-PSReadLineKeyHandler` cmdlet customizes the result when a key or sequence of keys is pressed.</span></span> <span data-ttu-id="88c6a-111">Mit benutzerdefinierten Tastenkombinationen können Sie nahezu alles ausführen, was in einem PowerShell-Skript möglich ist.</span><span class="sxs-lookup"><span data-stu-id="88c6a-111">With user-defined key bindings, you can do almost anything that is possible from within a PowerShell script.</span></span>

## <span data-ttu-id="88c6a-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="88c6a-112">EXAMPLES</span></span>

### <span data-ttu-id="88c6a-113">Beispiel 1: Binden der Pfeiltaste an eine Funktion</span><span class="sxs-lookup"><span data-stu-id="88c6a-113">Example 1: Bind the arrow key to a function</span></span>

<span data-ttu-id="88c6a-114">Mit diesem Befehl wird die nach-oben-Taste an die **historysearchrückwärts** -Funktion gebunden.</span><span class="sxs-lookup"><span data-stu-id="88c6a-114">This command binds the up arrow key to the **HistorySearchBackward** function.</span></span> <span data-ttu-id="88c6a-115">Diese Funktion durchsucht den Befehlsverlauf nach Befehlszeilen, die mit dem aktuellen Inhalt der Befehlszeile beginnen.</span><span class="sxs-lookup"><span data-stu-id="88c6a-115">This function searches command history for command lines that start with the current contents of the command line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### <span data-ttu-id="88c6a-116">Beispiel 2: Binden eines Schlüssels an einen Skriptblock</span><span class="sxs-lookup"><span data-stu-id="88c6a-116">Example 2: Bind a key to a script block</span></span>

<span data-ttu-id="88c6a-117">Dieses Beispiel zeigt, wie ein einzelner Schlüssel zum Ausführen eines Befehls verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="88c6a-117">This example shows how a single key can be used to run a command.</span></span> <span data-ttu-id="88c6a-118">Mit dem Befehl wird der Schlüssel `Ctrl+B` an einen Skriptblock gebunden, der die Zeile löscht, das Wort "Build" einfügt und dann die Zeile annimmt.</span><span class="sxs-lookup"><span data-stu-id="88c6a-118">The command binds the key `Ctrl+B` to a script block that clears the line, inserts the word "build", and then accepts the line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## <span data-ttu-id="88c6a-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="88c6a-119">PARAMETERS</span></span>

### <span data-ttu-id="88c6a-120">-Briefdescription</span><span class="sxs-lookup"><span data-stu-id="88c6a-120">-BriefDescription</span></span>

<span data-ttu-id="88c6a-121">Eine kurze Beschreibung der schlüsselbindung.</span><span class="sxs-lookup"><span data-stu-id="88c6a-121">A brief description of the key binding.</span></span> <span data-ttu-id="88c6a-122">Diese Beschreibung wird vom `Get-PSReadLineKeyHandler` Cmdlet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88c6a-122">This description is displayed by the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="88c6a-123">-Akkord</span><span class="sxs-lookup"><span data-stu-id="88c6a-123">-Chord</span></span>

<span data-ttu-id="88c6a-124">Der Schlüssel oder die Sequenz von Schlüsseln, die an eine Funktion oder einen Skriptblock gebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="88c6a-124">The key or sequence of keys to be bound to a function or script block.</span></span> <span data-ttu-id="88c6a-125">Verwenden Sie eine einzelne Zeichenfolge, um eine einzelne Bindung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="88c6a-125">Use a single string to specify a single binding.</span></span> <span data-ttu-id="88c6a-126">Wenn die Bindung eine Sequenz von Schlüsseln ist, trennen Sie die Schlüssel durch ein Komma, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="88c6a-126">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+X,Ctrl+L`

<span data-ttu-id="88c6a-127">Dieser Parameter akzeptiert ein Array von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="88c6a-127">This parameter accepts an array of strings.</span></span> <span data-ttu-id="88c6a-128">Jede Zeichenfolge ist eine separate Bindung und keine Sequenz von Schlüsseln für eine einzelne Bindung.</span><span class="sxs-lookup"><span data-stu-id="88c6a-128">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="88c6a-129">-Description</span><span class="sxs-lookup"><span data-stu-id="88c6a-129">-Description</span></span>

<span data-ttu-id="88c6a-130">Gibt eine ausführlichere Beschreibung der schlüsselbindung an, die in der Ausgabe des `Get-PSReadLineKeyHandler` Cmdlets sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="88c6a-130">Specifies a more detailed description of the key binding that is visible in the output of the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="88c6a-131">-Funktion</span><span class="sxs-lookup"><span data-stu-id="88c6a-131">-Function</span></span>

<span data-ttu-id="88c6a-132">Gibt den Namen eines vorhandenen Schlüssel Handlers an, der von psread Line bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="88c6a-132">Specifies the name of an existing key handler provided by PSReadLine.</span></span> <span data-ttu-id="88c6a-133">Dieser Parameter ermöglicht das erneute Binden vorhandener Schlüsselbindungen oder das Binden eines Handlers, der zurzeit nicht gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="88c6a-133">This parameter lets you rebind existing key bindings, or bind a handler that is currently unbound.</span></span>

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

### <span data-ttu-id="88c6a-134">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="88c6a-134">-ScriptBlock</span></span>

<span data-ttu-id="88c6a-135">Gibt einen Skriptblock Wert an, der beim Eintreten des Akkords ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="88c6a-135">Specifies a script block value to run when the chord is entered.</span></span> <span data-ttu-id="88c6a-136">Psread Line übergibt einen oder zwei Parameter an diesen Skriptblock.</span><span class="sxs-lookup"><span data-stu-id="88c6a-136">PSReadLine passes one or two parameters to this script block.</span></span> <span data-ttu-id="88c6a-137">Der erste Parameter ist ein **ConsoleKeyInfo** -Objekt, das den gedrückten Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="88c6a-137">The first parameter is a **ConsoleKeyInfo** object representing the key pressed.</span></span> <span data-ttu-id="88c6a-138">Das zweite Argument kann je nach Kontext ein beliebiges Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="88c6a-138">The second argument can be any object depending on the context.</span></span>

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

### <span data-ttu-id="88c6a-139">-Vimode</span><span class="sxs-lookup"><span data-stu-id="88c6a-139">-ViMode</span></span>

<span data-ttu-id="88c6a-140">Geben Sie den VI-Modus an, für den die Bindung gilt.</span><span class="sxs-lookup"><span data-stu-id="88c6a-140">Specify which vi mode the binding applies to.</span></span>

<span data-ttu-id="88c6a-141">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="88c6a-141">Valid values are:</span></span>

- <span data-ttu-id="88c6a-142">Insert</span><span class="sxs-lookup"><span data-stu-id="88c6a-142">Insert</span></span>
- <span data-ttu-id="88c6a-143">Get-Help</span><span class="sxs-lookup"><span data-stu-id="88c6a-143">Command</span></span>

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

### <span data-ttu-id="88c6a-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="88c6a-144">CommonParameters</span></span>

<span data-ttu-id="88c6a-145">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="88c6a-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="88c6a-146">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="88c6a-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="88c6a-147">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="88c6a-147">INPUTS</span></span>

### <span data-ttu-id="88c6a-148">Keine</span><span class="sxs-lookup"><span data-stu-id="88c6a-148">None</span></span>

<span data-ttu-id="88c6a-149">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="88c6a-149">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="88c6a-150">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="88c6a-150">OUTPUTS</span></span>

### <span data-ttu-id="88c6a-151">Keine</span><span class="sxs-lookup"><span data-stu-id="88c6a-151">None</span></span>

<span data-ttu-id="88c6a-152">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="88c6a-152">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="88c6a-153">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="88c6a-153">NOTES</span></span>

## <span data-ttu-id="88c6a-154">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="88c6a-154">RELATED LINKS</span></span>

[<span data-ttu-id="88c6a-155">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="88c6a-155">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="88c6a-156">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="88c6a-156">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="88c6a-157">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="88c6a-157">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="88c6a-158">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="88c6a-158">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
