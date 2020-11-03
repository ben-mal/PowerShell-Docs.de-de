---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/new-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-IseSnippet
ms.openlocfilehash: 0ed1c2913fc7531574bfbdd435a002d60931d24a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212380"
---
# <span data-ttu-id="e9607-103">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="e9607-103">New-IseSnippet</span></span>

## <span data-ttu-id="e9607-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e9607-104">SYNOPSIS</span></span>
<span data-ttu-id="e9607-105">Erstellt einen Windows PowerShell ISE-Codeausschnitt.</span><span class="sxs-lookup"><span data-stu-id="e9607-105">Creates a Windows PowerShell ISE code snippet.</span></span>

## <span data-ttu-id="e9607-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e9607-106">SYNTAX</span></span>

```
New-IseSnippet [-Title] <String> [-Description] <String> [-Text] <String> [-Author <String>]
 [-CaretOffset <Int32>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="e9607-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e9607-107">DESCRIPTION</span></span>

<span data-ttu-id="e9607-108">Das- `New-ISESnippet` Cmdlet erstellt einen wiederverwendbaren Text Ausschnitt für Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="e9607-108">The `New-ISESnippet` cmdlet creates a reusable text "snippet" for Windows PowerShell ISE.</span></span> <span data-ttu-id="e9607-109">Sie können Codeausschnitte verwenden, um dem Skriptbereich oder dem Befehlsbereich in Windows PowerShell ISE Text hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e9607-109">You can use snippets to add text to the Script pane or Command pane in Windows PowerShell ISE.</span></span> <span data-ttu-id="e9607-110">Dieses Cmdlet ist nur in Windows PowerShell ISE verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e9607-110">This cmdlet is available only in Windows PowerShell ISE.</span></span>

<span data-ttu-id="e9607-111">Ab Windows PowerShell 3.0 enthält Windows PowerShell ISE eine Auflistung von integrierten Codeausschnitten.</span><span class="sxs-lookup"><span data-stu-id="e9607-111">Beginning in Windows PowerShell 3.0, Windows PowerShell ISE includes a collection of built-in snippets.</span></span> <span data-ttu-id="e9607-112">Mit dem- `New-ISESnippet` Cmdlet können Sie eigene Ausschnitte erstellen, die der integrierten Auflistung hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e9607-112">The `New-ISESnippet` cmdlet lets you create your own snippets to add to the built-in collection.</span></span> <span data-ttu-id="e9607-113">Sie können Codeausschnittsdateien anzeigen, ändern, hinzufügen, löschen und freigeben sowie in Windows PowerShell-Module einschließen.</span><span class="sxs-lookup"><span data-stu-id="e9607-113">You can view, change, add, delete, and share snippet files and include them in Windows PowerShell modules.</span></span> <span data-ttu-id="e9607-114">Um Ausschnitte in Windows PowerShell ISE anzuzeigen, wählen Sie im Menü **Bearbeiten** die Option **Ausschnitte starten** aus, oder drücken Sie <kbd>STRG</kbd> + <kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="e9607-114">To see snippets in Windows PowerShell ISE, from the **Edit** menu, select **Start Snippets** or press <kbd>CTRL</kbd>+<kbd>J</kbd>.</span></span>

<span data-ttu-id="e9607-115">Das- `New-ISESnippet` Cmdlet erstellt eine `<Title>.Snippets.ps1xml` Datei im `$home\Documents\WindowsPowerShell\Snippets` Verzeichnis mit dem von Ihnen angegebenen Titel.</span><span class="sxs-lookup"><span data-stu-id="e9607-115">The `New-ISESnippet` cmdlet creates a `<Title>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory with the title that you specify.</span></span> <span data-ttu-id="e9607-116">Um eine Codeausschnittsdatei in ein Modul einzuschließen, das Sie erstellen, fügen Sie die Codeausschnittsdatei einem Unterverzeichnis „Snippets“ Ihres Modulverzeichnisses hinzu.</span><span class="sxs-lookup"><span data-stu-id="e9607-116">To include a snippet file in a module that you are authoring, add the snippet file to a Snippets subdirectory of your module directory.</span></span>

<span data-ttu-id="e9607-117">Benutzer erstellte Code Ausschnitte können nicht in einer Sitzung verwendet werden, in der die Ausführungs Richtlinie **eingeschränkt** oder **AllSigned** ist.</span><span class="sxs-lookup"><span data-stu-id="e9607-117">You cannot use user-created snippets in a session in which the execution policy is **Restricted** or **AllSigned** .</span></span>

<span data-ttu-id="e9607-118">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e9607-118">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="e9607-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e9607-119">EXAMPLES</span></span>

### <span data-ttu-id="e9607-120">Beispiel 1: Erstellen eines Comment-Based-Hilfe Ausschnitts</span><span class="sxs-lookup"><span data-stu-id="e9607-120">Example 1: Create a Comment-Based help snippet</span></span>

```
New-IseSnippet -Title Comment-BasedHelp -Description "A template for comment-based help." -Text "<#
    .SYNOPSIS

    .DESCRIPTION
    .PARAMETER  <Parameter-Name>
    .INPUTS
    .OUTPUTS
    .EXAMPLE
    .LINK
#>"
```

<span data-ttu-id="e9607-121">Dieser Befehl erstellt einen Comment-BasedHelp-Codeausschnitt für Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="e9607-121">This command creates a Comment-BasedHelp snippet for Windows PowerShell ISE.</span></span> <span data-ttu-id="e9607-122">Er erstellt eine Datei namens `Comment-BasedHelp.snippets.ps1xml` im Verzeichnis "Snippets" des Benutzers `$home\Documents\WindowsPowerShell\Snippets` .</span><span class="sxs-lookup"><span data-stu-id="e9607-122">It creates a file named `Comment-BasedHelp.snippets.ps1xml` in the user's Snippets directory `$home\Documents\WindowsPowerShell\Snippets`.</span></span>

### <span data-ttu-id="e9607-123">Beispiel 2: Erstellen eines obligatorischen Ausschnitts</span><span class="sxs-lookup"><span data-stu-id="e9607-123">Example 2: Create a mandatory snippet</span></span>

```
$M = @'
Param
(
  [parameter(Mandatory=$true)]
  [String[]]
  $<ParameterName>
)
'@

New-ISESnippet -Text $M -Title Mandatory -Description "Adds a mandatory function parameter." -Author "Patti Fuller, Fabrikam Corp." -Force
```

<span data-ttu-id="e9607-124">In diesem Beispiel wird ein Ausschnitt namens " **obligatorisch** " für Windows PowerShell ISE erstellt.</span><span class="sxs-lookup"><span data-stu-id="e9607-124">This example creates a snippet named **Mandatory** for Windows PowerShell ISE.</span></span> <span data-ttu-id="e9607-125">Der erste Befehl speichert den Ausschnitt Text in der `$M` Variablen.</span><span class="sxs-lookup"><span data-stu-id="e9607-125">The first command saves the snippet text in the `$M` variable.</span></span> <span data-ttu-id="e9607-126">Der zweite Befehl verwendet das `New-ISESnippet` Cmdlet zum Erstellen des Code Ausschnitts.</span><span class="sxs-lookup"><span data-stu-id="e9607-126">The second command uses the `New-ISESnippet` cmdlet to create the snippet.</span></span> <span data-ttu-id="e9607-127">Der Befehl verwendet den **Force** -Parameter zum Überschreiben eines vorherigen Codeausschnitts mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="e9607-127">The command uses the **Force** parameter to overwrite a previous snippet with the same name.</span></span>

### <span data-ttu-id="e9607-128">Beispiel 3: Kopieren eines obligatorischen Ausschnitts aus einem Ordner in einen Zielordner</span><span class="sxs-lookup"><span data-stu-id="e9607-128">Example 3: Copy a mandatory snippet from a folder to a destination folder</span></span>

```
Copy-Item "$Home\Documents\WindowsPowerShell\Snippets\Mandatory.Snippets.ps1xml" -Destination "\\Server\Share"
```

<span data-ttu-id="e9607-129">Dieser Befehl verwendet das `Copy-Item` Cmdlet, um den **obligatorischen** Ausschnitt aus dem Ordner zu kopieren, in dem `New-ISESnippet` Sie in die Dateifreigabe "Server\Freigabe" eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e9607-129">This command uses the `Copy-Item` cmdlet to copy the **Mandatory** snippet from the folder where `New-ISESnippet` places it to the Server\Share file share.</span></span>

## <span data-ttu-id="e9607-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e9607-130">PARAMETERS</span></span>

### <span data-ttu-id="e9607-131">-Autor</span><span class="sxs-lookup"><span data-stu-id="e9607-131">-Author</span></span>

<span data-ttu-id="e9607-132">Gibt den Autor des Code Ausschnitts an.</span><span class="sxs-lookup"><span data-stu-id="e9607-132">Specifies the author of the snippet.</span></span> <span data-ttu-id="e9607-133">Das Autorfeld wird in der Codeausschnittsdatei angezeigt, aber es wird nicht eingeblendet, wenn Sie in Windows PowerShell ISE auf den Codeausschnittsnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="e9607-133">The author field appears in the snippet file, but it does not appear when you click the snippet name in Windows PowerShell ISE.</span></span>

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

### <span data-ttu-id="e9607-134">-Careworffset</span><span class="sxs-lookup"><span data-stu-id="e9607-134">-CaretOffset</span></span>

<span data-ttu-id="e9607-135">Gibt das Zeichen des Ausschnitt Texts an, auf dem dieses Cmdlet den Cursor platziert.</span><span class="sxs-lookup"><span data-stu-id="e9607-135">Specifies the character of the snippet text that this cmdlet places the cursor on.</span></span> <span data-ttu-id="e9607-136">Geben Sie eine ganze Zahl zur Darstellung der Cursorposition ein, wobei „1“ das erste Textzeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="e9607-136">Enter an integer that represents the cursor position, with "1" representing the first character of text.</span></span> <span data-ttu-id="e9607-137">Der Standardwert 0 (null) platziert den Cursor unmittelbar vor dem ersten Textzeichen.</span><span class="sxs-lookup"><span data-stu-id="e9607-137">The default value, 0 (zero), places the cursor immediately before the first character of text.</span></span> <span data-ttu-id="e9607-138">Dieser Parameter rückt den Codeausschnittstext nicht ein.</span><span class="sxs-lookup"><span data-stu-id="e9607-138">This parameter does not indent the snippet text.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9607-139">-Description</span><span class="sxs-lookup"><span data-stu-id="e9607-139">-Description</span></span>

<span data-ttu-id="e9607-140">Gibt eine Beschreibung des Code Ausschnitts an.</span><span class="sxs-lookup"><span data-stu-id="e9607-140">Specifies a description of the snippet.</span></span> <span data-ttu-id="e9607-141">Der Beschreibungswert wird angezeigt, wenn Sie in Windows PowerShell ISE auf den Codeausschnittsnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="e9607-141">The description value appears when you click the snippet name in Windows PowerShell ISE.</span></span> <span data-ttu-id="e9607-142">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e9607-142">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9607-143">-Force</span><span class="sxs-lookup"><span data-stu-id="e9607-143">-Force</span></span>

<span data-ttu-id="e9607-144">Gibt an, dass dieses Cmdlet Ausschnitt Dateien mit demselben Namen am gleichen Speicherort überschreibt.</span><span class="sxs-lookup"><span data-stu-id="e9607-144">Indicates that this cmdlet overwrites snippet files with the same name in the same location.</span></span> <span data-ttu-id="e9607-145">Standardmäßig werden von keine `New-ISESnippet` Dateien überschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9607-145">By default, `New-ISESnippet` does not overwrite files.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9607-146">-Text</span><span class="sxs-lookup"><span data-stu-id="e9607-146">-Text</span></span>

<span data-ttu-id="e9607-147">Gibt den Textwert an, der hinzugefügt wird, wenn Sie den Codeausschnitt auswählen.</span><span class="sxs-lookup"><span data-stu-id="e9607-147">Specifies the text value that is added when you select the snippet.</span></span> <span data-ttu-id="e9607-148">Der Codeausschnittstext wird angezeigt, wenn Sie in Windows PowerShell ISE auf den Codeausschnittsnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="e9607-148">The snippet text appears when you click the snippet name in Windows PowerShell ISE.</span></span> <span data-ttu-id="e9607-149">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e9607-149">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9607-150">-Title</span><span class="sxs-lookup"><span data-stu-id="e9607-150">-Title</span></span>

<span data-ttu-id="e9607-151">Gibt einen Titel oder einen Namen für den Codeausschnitt an.</span><span class="sxs-lookup"><span data-stu-id="e9607-151">Specifies a title or name for the snippet.</span></span> <span data-ttu-id="e9607-152">Der Titel dient auch als Name der Codeausschnittsdatei.</span><span class="sxs-lookup"><span data-stu-id="e9607-152">The title also names the snippet file.</span></span> <span data-ttu-id="e9607-153">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e9607-153">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9607-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e9607-154">CommonParameters</span></span>

<span data-ttu-id="e9607-155">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e9607-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e9607-156">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e9607-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e9607-157">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e9607-157">INPUTS</span></span>

### <span data-ttu-id="e9607-158">Keine</span><span class="sxs-lookup"><span data-stu-id="e9607-158">None</span></span>

<span data-ttu-id="e9607-159">Dieses Cmdlet nimmt keine Eingabe von der Pipeline an.</span><span class="sxs-lookup"><span data-stu-id="e9607-159">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="e9607-160">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e9607-160">OUTPUTS</span></span>

### <span data-ttu-id="e9607-161">Keine</span><span class="sxs-lookup"><span data-stu-id="e9607-161">None</span></span>

<span data-ttu-id="e9607-162">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e9607-162">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e9607-163">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e9607-163">NOTES</span></span>

<span data-ttu-id="e9607-164">`New-IseSnippet` speichert neue Benutzer erstellte Code Ausschnitte in unsignierten ps1xml-Dateien.</span><span class="sxs-lookup"><span data-stu-id="e9607-164">`New-IseSnippet` stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="e9607-165">Daher kann Windows PowerShell sie nicht zu Sitzungen hinzufügen, in denen die Ausführungsrichtlinie **AllSigned** oder **Restricted** gilt.</span><span class="sxs-lookup"><span data-stu-id="e9607-165">As such, Windows PowerShell cannot add them to a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="e9607-166">In einer Sitzung mit der Ausführungsrichtlinie **Restricted** oder **AllSigned** können Sie zwar unsignierte benutzererstellte Codeausschnitte erstellen, abrufen und importieren, aber nicht in der Sitzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e9607-166">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

<span data-ttu-id="e9607-167">Wenn Sie das `New-IseSnippet` Cmdlet in einer **eingeschränkten** oder **AllSigned** -Sitzung verwenden, wird der Ausschnitt erstellt, aber es wird eine Fehlermeldung angezeigt, wenn Windows PowerShell versucht, den neu erstellten Ausschnitt der Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e9607-167">If you use the `New-IseSnippet` cmdlet in a **Restricted** or **AllSigned** session, the snippet is created, but an error message appears when Windows PowerShell tries to add the newly created snippet to the session.</span></span> <span data-ttu-id="e9607-168">Um den neuen Codeausschnitt (und andere unsignierte benutzererstellte Codeausschnitte) zu verwenden, ändern Sie die Ausführungsrichtlinie, und starten Sie Windows PowerShell ISE neu.</span><span class="sxs-lookup"><span data-stu-id="e9607-168">To use the new snippet (and other unsigned user-created snippets), change the execution policy, and then restart Windows PowerShell ISE.</span></span>

<span data-ttu-id="e9607-169">Weitere Informationen zu Windows PowerShell-Ausführungsrichtlinien finden Sie unter about_Execution_Policies.</span><span class="sxs-lookup"><span data-stu-id="e9607-169">For more information about Windows PowerShell execution policies, see about_Execution_Policies.</span></span>

- <span data-ttu-id="e9607-170">Um einen Ausschnitt zu ändern, bearbeiten Sie die codeausschnittsdatei.</span><span class="sxs-lookup"><span data-stu-id="e9607-170">To change a snippet, edit the snippet file.</span></span> <span data-ttu-id="e9607-171">Sie können Ausschnitt Dateien im Skript Bereich von Windows PowerShell ISE bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e9607-171">You can edit snippet files in the Script pane of Windows PowerShell ISE.</span></span>
- <span data-ttu-id="e9607-172">Um einen hinzugefügten Code Ausschnitt zu löschen, löschen Sie die codeausschnittsdatei.</span><span class="sxs-lookup"><span data-stu-id="e9607-172">To delete a snippet that you added, delete the snippet file.</span></span>
- <span data-ttu-id="e9607-173">Ein integrierter Ausschnitt kann nicht gelöscht werden, Sie können jedoch alle integrierten Code Ausschnitte ausblenden, indem Sie die $psise verwenden. Options. showdefaulsnippets = $false "Befehl.</span><span class="sxs-lookup"><span data-stu-id="e9607-173">You cannot delete a built-in snippet, but you can hide all built-in snippets by using the "$psise.Options.ShowDefaultSnippets=$false" command.</span></span>
- <span data-ttu-id="e9607-174">Sie können einen Ausschnitt erstellen, der denselben Namen wie ein integrierter Ausschnitt hat.</span><span class="sxs-lookup"><span data-stu-id="e9607-174">You can create a snippet that has the same name as a built-in snippet.</span></span> <span data-ttu-id="e9607-175">Beide Codeausschnitte werden im Codeausschnittsmenü in Windows PowerShell ISE angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9607-175">Both snippets appear in the snippet menu in Windows PowerShell ISE.</span></span>

## <span data-ttu-id="e9607-176">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e9607-176">RELATED LINKS</span></span>

[<span data-ttu-id="e9607-177">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="e9607-177">Get-IseSnippet</span></span>](Get-IseSnippet.md)

[<span data-ttu-id="e9607-178">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="e9607-178">Import-IseSnippet</span></span>](Import-IseSnippet.md)
