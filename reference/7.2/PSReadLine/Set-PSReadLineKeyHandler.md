---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: 0ec3466aaaf6ed1ac78b62d88a5a6cce99153673
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596153"
---
# <span data-ttu-id="efb91-102">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="efb91-102">Set-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="efb91-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="efb91-103">SYNOPSIS</span></span>
<span data-ttu-id="efb91-104">Bindet Schlüssel an benutzerdefinierte oder psread Line-schlüsselhandlerfunktionen.</span><span class="sxs-lookup"><span data-stu-id="efb91-104">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

## <span data-ttu-id="efb91-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="efb91-105">SYNTAX</span></span>

### <span data-ttu-id="efb91-106">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="efb91-106">ScriptBlock</span></span>

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### <span data-ttu-id="efb91-107">Funktion</span><span class="sxs-lookup"><span data-stu-id="efb91-107">Function</span></span>

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## <span data-ttu-id="efb91-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="efb91-108">DESCRIPTION</span></span>

<span data-ttu-id="efb91-109">Das- `Set-PSReadLineKeyHandler` Cmdlet passt das Ergebnis an, wenn ein Schlüssel oder eine Sequenz von Schlüsseln gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="efb91-109">The `Set-PSReadLineKeyHandler` cmdlet customizes the result when a key or sequence of keys is pressed.</span></span> <span data-ttu-id="efb91-110">Mit benutzerdefinierten Tastenkombinationen können Sie nahezu alles ausführen, was in einem PowerShell-Skript möglich ist.</span><span class="sxs-lookup"><span data-stu-id="efb91-110">With user-defined key bindings, you can do almost anything that is possible from within a PowerShell script.</span></span>

## <span data-ttu-id="efb91-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="efb91-111">EXAMPLES</span></span>

### <span data-ttu-id="efb91-112">Beispiel 1: Binden der Pfeiltaste an eine Funktion</span><span class="sxs-lookup"><span data-stu-id="efb91-112">Example 1: Bind the arrow key to a function</span></span>

<span data-ttu-id="efb91-113">Mit diesem Befehl wird die nach-oben-Taste an die **historysearchrückwärts** -Funktion gebunden.</span><span class="sxs-lookup"><span data-stu-id="efb91-113">This command binds the up arrow key to the **HistorySearchBackward** function.</span></span> <span data-ttu-id="efb91-114">Diese Funktion durchsucht den Befehlsverlauf nach Befehlszeilen, die mit dem aktuellen Inhalt der Befehlszeile beginnen.</span><span class="sxs-lookup"><span data-stu-id="efb91-114">This function searches command history for command lines that start with the current contents of the command line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### <span data-ttu-id="efb91-115">Beispiel 2: Binden eines Schlüssels an einen Skriptblock</span><span class="sxs-lookup"><span data-stu-id="efb91-115">Example 2: Bind a key to a script block</span></span>

<span data-ttu-id="efb91-116">Dieses Beispiel zeigt, wie ein einzelner Schlüssel zum Ausführen eines Befehls verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="efb91-116">This example shows how a single key can be used to run a command.</span></span> <span data-ttu-id="efb91-117">Mit dem Befehl wird der Schlüssel `Ctrl+B` an einen Skriptblock gebunden, der die Zeile löscht, das Wort "Build" einfügt und dann die Zeile annimmt.</span><span class="sxs-lookup"><span data-stu-id="efb91-117">The command binds the key `Ctrl+B` to a script block that clears the line, inserts the word "build", and then accepts the line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## <span data-ttu-id="efb91-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="efb91-118">PARAMETERS</span></span>

### <span data-ttu-id="efb91-119">-Briefdescription</span><span class="sxs-lookup"><span data-stu-id="efb91-119">-BriefDescription</span></span>

<span data-ttu-id="efb91-120">Eine kurze Beschreibung der schlüsselbindung.</span><span class="sxs-lookup"><span data-stu-id="efb91-120">A brief description of the key binding.</span></span> <span data-ttu-id="efb91-121">Diese Beschreibung wird vom `Get-PSReadLineKeyHandler` Cmdlet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="efb91-121">This description is displayed by the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="efb91-122">-Akkord</span><span class="sxs-lookup"><span data-stu-id="efb91-122">-Chord</span></span>

<span data-ttu-id="efb91-123">Der Schlüssel oder die Sequenz von Schlüsseln, die an eine Funktion oder einen Skriptblock gebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="efb91-123">The key or sequence of keys to be bound to a function or script block.</span></span> <span data-ttu-id="efb91-124">Verwenden Sie eine einzelne Zeichenfolge, um eine einzelne Bindung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="efb91-124">Use a single string to specify a single binding.</span></span> <span data-ttu-id="efb91-125">Wenn die Bindung eine Sequenz von Schlüsseln ist, trennen Sie die Schlüssel durch ein Komma, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="efb91-125">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+X,Ctrl+L`

<span data-ttu-id="efb91-126">Dieser Parameter akzeptiert ein Array von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="efb91-126">This parameter accepts an array of strings.</span></span> <span data-ttu-id="efb91-127">Jede Zeichenfolge ist eine separate Bindung und keine Sequenz von Schlüsseln für eine einzelne Bindung.</span><span class="sxs-lookup"><span data-stu-id="efb91-127">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="efb91-128">-Description</span><span class="sxs-lookup"><span data-stu-id="efb91-128">-Description</span></span>

<span data-ttu-id="efb91-129">Gibt eine ausführlichere Beschreibung der schlüsselbindung an, die in der Ausgabe des `Get-PSReadLineKeyHandler` Cmdlets sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="efb91-129">Specifies a more detailed description of the key binding that is visible in the output of the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="efb91-130">-Funktion</span><span class="sxs-lookup"><span data-stu-id="efb91-130">-Function</span></span>

<span data-ttu-id="efb91-131">Gibt den Namen eines vorhandenen Schlüssel Handlers an, der von psread Line bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="efb91-131">Specifies the name of an existing key handler provided by PSReadLine.</span></span> <span data-ttu-id="efb91-132">Dieser Parameter ermöglicht das erneute Binden vorhandener Schlüsselbindungen oder das Binden eines Handlers, der zurzeit nicht gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="efb91-132">This parameter lets you rebind existing key bindings, or bind a handler that is currently unbound.</span></span>

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

### <span data-ttu-id="efb91-133">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="efb91-133">-ScriptBlock</span></span>

<span data-ttu-id="efb91-134">Gibt einen Skriptblock Wert an, der beim Eintreten des Akkords ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="efb91-134">Specifies a script block value to run when the chord is entered.</span></span> <span data-ttu-id="efb91-135">Psread Line übergibt einen oder zwei Parameter an diesen Skriptblock.</span><span class="sxs-lookup"><span data-stu-id="efb91-135">PSReadLine passes one or two parameters to this script block.</span></span> <span data-ttu-id="efb91-136">Der erste Parameter ist ein **ConsoleKeyInfo** -Objekt, das den gedrückten Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="efb91-136">The first parameter is a **ConsoleKeyInfo** object representing the key pressed.</span></span> <span data-ttu-id="efb91-137">Das zweite Argument kann je nach Kontext ein beliebiges Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="efb91-137">The second argument can be any object depending on the context.</span></span>

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

### <span data-ttu-id="efb91-138">-Vimode</span><span class="sxs-lookup"><span data-stu-id="efb91-138">-ViMode</span></span>

<span data-ttu-id="efb91-139">Geben Sie den VI-Modus an, für den die Bindung gilt.</span><span class="sxs-lookup"><span data-stu-id="efb91-139">Specify which vi mode the binding applies to.</span></span>

<span data-ttu-id="efb91-140">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="efb91-140">Valid values are:</span></span>

- <span data-ttu-id="efb91-141">Einfügen</span><span class="sxs-lookup"><span data-stu-id="efb91-141">Insert</span></span>
- <span data-ttu-id="efb91-142">Get-Help</span><span class="sxs-lookup"><span data-stu-id="efb91-142">Command</span></span>

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

### <span data-ttu-id="efb91-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="efb91-143">CommonParameters</span></span>

<span data-ttu-id="efb91-144">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="efb91-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="efb91-145">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="efb91-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="efb91-146">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="efb91-146">INPUTS</span></span>

### <span data-ttu-id="efb91-147">Keine</span><span class="sxs-lookup"><span data-stu-id="efb91-147">None</span></span>

<span data-ttu-id="efb91-148">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="efb91-148">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="efb91-149">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="efb91-149">OUTPUTS</span></span>

### <span data-ttu-id="efb91-150">Keine</span><span class="sxs-lookup"><span data-stu-id="efb91-150">None</span></span>

<span data-ttu-id="efb91-151">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="efb91-151">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="efb91-152">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="efb91-152">NOTES</span></span>

## <span data-ttu-id="efb91-153">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="efb91-153">RELATED LINKS</span></span>

[<span data-ttu-id="efb91-154">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="efb91-154">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="efb91-155">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="efb91-155">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="efb91-156">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="efb91-156">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="efb91-157">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="efb91-157">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

