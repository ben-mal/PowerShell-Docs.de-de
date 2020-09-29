---
title: Erstellen einer XML-basierten Hilfe mithilfe von PlatyPS
description: PlatyPS ist eine schnelle und effiziente Möglichkeit, eine XML-basierte Hilfe zu erstellen.
ms.date: 07/21/2020
ms.openlocfilehash: 79cf8c077a07bf1e7aa8ea1ea799be5f8d4af12c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "86972586"
---
# <a name="create-xml-based-help-using-platyps"></a><span data-ttu-id="8961c-103">Erstellen einer XML-basierten Hilfe mithilfe von PlatyPS</span><span class="sxs-lookup"><span data-stu-id="8961c-103">Create XML-based help using PlatyPS</span></span>

<span data-ttu-id="8961c-104">Beim Erstellen eines PowerShell-Moduls wird stets empfohlen, eine ausführliche Hilfe für die von Ihnen erstellten Cmdlets hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8961c-104">When creating a PowerShell module, it is always recommended that you include detailed help for the cmdlets you create.</span></span> <span data-ttu-id="8961c-105">Wenn Ihre Cmdlets in kompiliertem Code implementiert sind, müssen Sie die XML-basierte Hilfe verwenden.</span><span class="sxs-lookup"><span data-stu-id="8961c-105">If your cmdlets are implemented in compiled code, you must use the XML-based help.</span></span> <span data-ttu-id="8961c-106">Dieses XML-Format wird als Microsoft Assistance Markup Language (MAML) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8961c-106">This XML format is known as the Microsoft Assistance Markup Language (MAML).</span></span>

<span data-ttu-id="8961c-107">In der Legacy-Dokumentation zum PowerShell SDK werden die Details zur Erstellung von Hilfe für in Modulen gepackte PowerShell-Cmdlets behandelt.</span><span class="sxs-lookup"><span data-stu-id="8961c-107">The legacy PowerShell SDK documentation covers the details of creating help for PowerShell cmdlets packaged into modules.</span></span> <span data-ttu-id="8961c-108">PowerShell bietet jedoch keine Tools zum Erstellen der XML-basierten Hilfe.</span><span class="sxs-lookup"><span data-stu-id="8961c-108">However, PowerShell does not provide any tools for creating the XML-based help.</span></span> <span data-ttu-id="8961c-109">In der SDK-Dokumentation wird die Struktur der MAML-Hilfe erklärt, aber es bleibt Ihnen überlassen, den komplexen und tief geschachtelten MAML-Inhalt manuell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8961c-109">The SDK documentation explains the structure of MAML help, but leaves you the task of creating the complex, and deeply nested, MAML content by hand.</span></span>

<span data-ttu-id="8961c-110">An dieser Stelle kann das [PlatyPS][]-Modul helfen.</span><span class="sxs-lookup"><span data-stu-id="8961c-110">This is where the [PlatyPS][] module can help.</span></span>

## <a name="what-is-platyps"></a><span data-ttu-id="8961c-111">Was ist PlatyPS?</span><span class="sxs-lookup"><span data-stu-id="8961c-111">What is PlatyPS?</span></span>

<span data-ttu-id="8961c-112">PlatyPS ist ein [Open-Source-][platyps-repo]-Tool, das als _Hackathon_-Projekt begann, um die Erstellung und Pflege von MAML zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="8961c-112">PlatyPS is an [open-source][platyps-repo] tool that started as a _hackathon_ project to make the creation and maintenance of MAML easier.</span></span> <span data-ttu-id="8961c-113">PlatyPS dokumentiert die Syntax von Parametersätzen und die einzelnen Parameter für jedes Cmdlet in Ihrem Modul.</span><span class="sxs-lookup"><span data-stu-id="8961c-113">PlatyPS documents the syntax of parameter sets and the individual parameters for each cmdlet in your module.</span></span> <span data-ttu-id="8961c-114">PlatyPS erstellt strukturierte [Markdown][]-Dateien mit Syntaxinformationen.</span><span class="sxs-lookup"><span data-stu-id="8961c-114">PlatyPS creates structured [Markdown][] files that contain the syntax information.</span></span> <span data-ttu-id="8961c-115">Das Tool kann keine Beschreibungen erstellen oder Beispiele bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8961c-115">It can't create descriptions or provide examples.</span></span>

<span data-ttu-id="8961c-116">PlatyPS erstellt Platzhalter, die Sie zum Ausfüllen von Beschreibungen und Beispielen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8961c-116">PlatyPS creates placeholders for you to fill in descriptions and examples.</span></span> <span data-ttu-id="8961c-117">Nach Hinzufügen der erforderlichen Informationen kompiliert PlatyPS die Markdown-Dateien in MAML-Dateien.</span><span class="sxs-lookup"><span data-stu-id="8961c-117">After adding the required information, PlatyPS compiles the Markdown files into MAML files.</span></span> <span data-ttu-id="8961c-118">Das Hilfesystem von PowerShell ermöglicht auch konzeptionelle Hilfedateien in Textform (zu Themen).</span><span class="sxs-lookup"><span data-stu-id="8961c-118">PowerShell's help system also allows for plain-text conceptual help files (about topics).</span></span> <span data-ttu-id="8961c-119">PlatyPS bietet ein Cmdlet zum Erstellen einer strukturierten Markdown-Vorlage für eine neue _Info_-Datei, wobei diese `about_*.help.txt`-Dateien jedoch manuell gepflegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8961c-119">PlatyPS has a cmdlet to create a structured Markdown template for a new _about_ file, but these `about_*.help.txt` files must be maintained manually.</span></span>

<span data-ttu-id="8961c-120">Sie können die MAML-und Texthilfedateien in Ihr Modul einschließen.</span><span class="sxs-lookup"><span data-stu-id="8961c-120">You can include the MAML and Text help files with your module.</span></span> <span data-ttu-id="8961c-121">Sie können mit PlatyPS auch die Hilfedateien zu einem CAB-Paket kompilieren, das für aktualisierbare Hilfe gehostet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8961c-121">You can also use PlatyPS to compile the help files into a CAB package that can be hosted for updateable help.</span></span>

## <a name="get-started-using-platyps"></a><span data-ttu-id="8961c-122">Erste Schritte mit PlatyPS</span><span class="sxs-lookup"><span data-stu-id="8961c-122">Get started using PlatyPS</span></span>

<span data-ttu-id="8961c-123">Zunächst müssen Sie PlatyPS aus dem PowerShell-Katalog herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="8961c-123">First you must install PlatyPS from the PowerShell Gallery.</span></span>

```powershell
Install-Module platyps -Force
Import-Module platyps
```

<span data-ttu-id="8961c-124">Im folgenden Flussdiagramm wird der Prozess zum Erstellen oder Aktualisieren von PowerShell-Referenzinhalten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8961c-124">The following flowchart outlines the process for creating or updating PowerShell reference content.</span></span>

:::image type="content" source="./media/create-help-using-platyps/cmdlet-ref-flow-v2.png" alt-text="Der Workflow zum Erstellen einer XML-basierten Hilfe mithilfe von PlatyPS":::

##  <a name="create-markdown-content-for-a-powershell-module"></a><span data-ttu-id="8961c-126">Erstellen von Markdown-Inhalten für ein PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="8961c-126">Create Markdown content for a PowerShell module</span></span>

1. <span data-ttu-id="8961c-127">Importieren Sie Ihr neues Modul in die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="8961c-127">Import your new module into the session.</span></span> <span data-ttu-id="8961c-128">Wiederholen Sie diesen Schritt für jedes Modul, das Sie dokumentieren müssen.</span><span class="sxs-lookup"><span data-stu-id="8961c-128">Repeat this step for each module you need to document.</span></span>

   <span data-ttu-id="8961c-129">Führen Sie den folgenden Befehl aus, um die Module zu importieren:</span><span class="sxs-lookup"><span data-stu-id="8961c-129">Run the following command to import your modules:</span></span>

   ```powershell
   Import-Module <your module name>
   ```

1. <span data-ttu-id="8961c-130">Verwenden Sie PlatyPS, um Markdown-Dateien für Ihre Modulseite und alle zugehörigen Cmdlets innerhalb des Moduls zu generieren.</span><span class="sxs-lookup"><span data-stu-id="8961c-130">Use PlatyPS to generate Markdown files for your module page and all associated cmdlets within the module.</span></span> <span data-ttu-id="8961c-131">Wiederholen Sie diesen Schritt für jedes Modul, das Sie dokumentieren müssen.</span><span class="sxs-lookup"><span data-stu-id="8961c-131">Repeat this step for each module you need to document.</span></span>

   ```powershell
   $OutputFolder = <output path>
   $parameters = @{
       Module = <ModuleName>
       OutputFolder = $OutputFolder
       AlphabeticParamsOrder = $true
       WithModulePage = $true
       ExcludeDontShow = $true
       Encoding = 'UTF8BOM'
   }
   New-MarkdownHelp @parameters

   New-MarkdownAboutHelp -OutputFolder $OutputFolder -AboutName "topic_name"
   ```

   <span data-ttu-id="8961c-132">Wenn der Ausgabeordner nicht vorhanden ist, wird er von `New-MarkdownHelp` erstellt.</span><span class="sxs-lookup"><span data-stu-id="8961c-132">If the output folder does not exist, `New-MarkdownHelp` creates it.</span></span> <span data-ttu-id="8961c-133">In diesem Beispiel erstellt `New-MarkdownHelp` eine Markdown-Datei für jedes Cmdlet im Modul.</span><span class="sxs-lookup"><span data-stu-id="8961c-133">In this example, `New-MarkdownHelp` creates a Markdown file for each cmdlet in the module.</span></span> <span data-ttu-id="8961c-134">Außerdem wird die _Modulseite_ in einer Datei namens `<ModuleName>.md` erstellt.</span><span class="sxs-lookup"><span data-stu-id="8961c-134">It also creates the _module page_ in a file named `<ModuleName>.md`.</span></span> <span data-ttu-id="8961c-135">Diese Modulseite enthält eine Liste der Cmdlets im Modul und Platzhalter für die beschreibende **Übersicht**.</span><span class="sxs-lookup"><span data-stu-id="8961c-135">This module page contains a list of the cmdlets contained in the module and placeholders for the **Synopsis** description.</span></span> <span data-ttu-id="8961c-136">Die Metadaten auf der Modulseite stammen aus dem Modulmanifest und werden von PlatyPS zur Erstellung der HelpInfo-XML-Datei verwendet (wie [nachstehend](#creating-an-updateable-help-package) erklärt).</span><span class="sxs-lookup"><span data-stu-id="8961c-136">The metadata in the module page comes from the module manifest and is used by PlatyPS to create the HelpInfo XML file (as explained [below](#creating-an-updateable-help-package)).</span></span>

   <span data-ttu-id="8961c-137">`New-MarkdownAboutHelp` erstellt eine neue _Info_-Datei mit dem Namen `about_topic_name.md`.</span><span class="sxs-lookup"><span data-stu-id="8961c-137">`New-MarkdownAboutHelp` creates a new _about_ file named `about_topic_name.md`.</span></span>

   <span data-ttu-id="8961c-138">Weitere Informationen finden Sie unter [New-MarkdownHelp][] und [New-MarkdownAboutHelp][].</span><span class="sxs-lookup"><span data-stu-id="8961c-138">For more information, see [New-MarkdownHelp][] and [New-MarkdownAboutHelp][].</span></span>

### <a name="update-existing-markdown-content-when-the-module-changes"></a><span data-ttu-id="8961c-139">Aktualisieren vorhandener Markdown-Inhalte bei Moduländerungen</span><span class="sxs-lookup"><span data-stu-id="8961c-139">Update existing Markdown content when the module changes</span></span>

<span data-ttu-id="8961c-140">Mit PlatyPS können auch vorhandene Markdown-Dateien für ein Modul aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8961c-140">PlatyPS can also update existing Markdown files for a module.</span></span> <span data-ttu-id="8961c-141">Mit diesem Schritt können Sie vorhandene Module aktualisieren, die über neue Cmdlets, neue Parameter oder geänderte Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="8961c-141">Use this step to update existing modules that have new cmdlets, new parameters, or parameters that have changed.</span></span>

1. <span data-ttu-id="8961c-142">Importieren Sie Ihr neues Modul in die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="8961c-142">Import your new module into the session.</span></span> <span data-ttu-id="8961c-143">Wiederholen Sie diesen Schritt für jedes Modul, das Sie dokumentieren müssen.</span><span class="sxs-lookup"><span data-stu-id="8961c-143">Repeat this step for each module you need to document.</span></span>

   <span data-ttu-id="8961c-144">Führen Sie den folgenden Befehl aus, um die Module zu importieren:</span><span class="sxs-lookup"><span data-stu-id="8961c-144">Run the following command to import your modules:</span></span>

   ```powershell
   Import-Module <your module name>
   ```

1. <span data-ttu-id="8961c-145">Verwenden Sie PlatyPS, um Markdown-Dateien für Ihre Modulzielseite und alle zugehörigen Cmdlets innerhalb des Moduls zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8961c-145">Use PlatyPS to update Markdown files for your module landing page and all associated cmdlets within the module.</span></span> <span data-ttu-id="8961c-146">Wiederholen Sie diesen Schritt für jedes Modul, das Sie dokumentieren müssen.</span><span class="sxs-lookup"><span data-stu-id="8961c-146">Repeat this step for each module you need to document.</span></span>

   ```powershell
   $parameters = @{
       Path = <folder with Markdown>
       RefreshModulePage = $true
       AlphabeticParamsOrder = $true
       UpdateInputOutput = $true
       ExcludeDontShow = $true
       LogPath = <path to store log file>
       Encoding = 'UTF8BOM'
   }
   Update-MarkdownHelpModule @parameters
   ```

   <span data-ttu-id="8961c-147">`Update-MarkdownHelpModule` aktualisiert die Markdown-Dateien für Cmdlets und Module im angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="8961c-147">`Update-MarkdownHelpModule` updates the cmdlet and module Markdown files in the specified folder.</span></span>
   <span data-ttu-id="8961c-148">Die `about_*.md`-Dateien werden damit nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8961c-148">It does not update the `about_*.md` files.</span></span> <span data-ttu-id="8961c-149">Die Moduldatei (`ModuleName.md`) empfängt jeglichen neuen Text für die **Übersicht**, der den Cmdlet-Dateien hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="8961c-149">The module file (`ModuleName.md`) receives any new **Synopsis** text that has been added to the cmdlet files.</span></span> <span data-ttu-id="8961c-150">Zu Aktualisierungen von Cmdlet-Dateien zählen folgende Änderungen:</span><span class="sxs-lookup"><span data-stu-id="8961c-150">Updates to cmdlet files include the following change:</span></span>

   - <span data-ttu-id="8961c-151">Neue Parametersätze</span><span class="sxs-lookup"><span data-stu-id="8961c-151">New parameter sets</span></span>
   - <span data-ttu-id="8961c-152">Neue Parameter</span><span class="sxs-lookup"><span data-stu-id="8961c-152">New parameters</span></span>
   - <span data-ttu-id="8961c-153">Aktualisierte Metadaten von Parametern</span><span class="sxs-lookup"><span data-stu-id="8961c-153">Updated parameter metadata</span></span>
   - <span data-ttu-id="8961c-154">Aktualisierte Informationen zu Ein- und Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="8961c-154">Updated input and output type information</span></span>

   <span data-ttu-id="8961c-155">Weitere Informationen finden Sie unter [Update-MarkdownHelpModule][].</span><span class="sxs-lookup"><span data-stu-id="8961c-155">For more information, see [Update-MarkdownHelpModule][].</span></span>

## <a name="edit-the-new-or-updated-markdown-files"></a><span data-ttu-id="8961c-156">Bearbeiten der neuen oder aktualisierten Markdown-Dateien</span><span class="sxs-lookup"><span data-stu-id="8961c-156">Edit the new or updated Markdown files</span></span>

<span data-ttu-id="8961c-157">PlatyPS dokumentiert die Syntax der Parametersätze und einzelnen Parameter.</span><span class="sxs-lookup"><span data-stu-id="8961c-157">PlatyPS documents the syntax of the parameter sets and the individual parameters.</span></span> <span data-ttu-id="8961c-158">Das Tool kann keine Beschreibungen erstellen oder Beispiele bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8961c-158">It can't create descriptions or provide examples.</span></span> <span data-ttu-id="8961c-159">Die spezifischen Bereiche, in denen Inhalte benötigt werden, stehen in geschweiften Klammern.</span><span class="sxs-lookup"><span data-stu-id="8961c-159">The specific areas where content is needed are contained in curly braces.</span></span> <span data-ttu-id="8961c-160">Beispiel: `{{ Fill in the Description }}`</span><span class="sxs-lookup"><span data-stu-id="8961c-160">For example: `{{ Fill in the Description }}`</span></span>

:::image type="content" source="./media/create-help-using-platyps/placeholders-example.png" alt-text="Der Workflow zum Erstellen einer XML-basierten Hilfe mithilfe von PlatyPS":::

<span data-ttu-id="8961c-162">Sie müssen eine Übersicht, eine Beschreibung des Cmdlets und der einzelnen Parameter sowie mindestens ein Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8961c-162">You need to add a synopsis, a description of the cmdlet, descriptions for each parameter, and at least one example.</span></span>

<span data-ttu-id="8961c-163">Ausführliche Informationen zum Schreiben von PowerShell-Inhalten finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="8961c-163">For detailed information about writing PowerShell content, see the following articles:</span></span>

- [<span data-ttu-id="8961c-164">Styleguide für PowerShell</span><span class="sxs-lookup"><span data-stu-id="8961c-164">PowerShell style guide</span></span>](/powershell/scripting/community/contributing/powershell-style-guide)
- [<span data-ttu-id="8961c-165">Bearbeiten von Referenzartikeln</span><span class="sxs-lookup"><span data-stu-id="8961c-165">Editing reference articles</span></span>](/powershell/scripting/community/contributing/editing-cmdlet-ref)

> [!NOTE]
> <span data-ttu-id="8961c-166">PlatyPS weist ein bestimmtes Schema auf, das als Cmdlet-Referenz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8961c-166">PlatyPS has a specific schema that is uses for cmdlet reference.</span></span> <span data-ttu-id="8961c-167">Dieses Schema lässt nur bestimmte Markdown-Blöcke in bestimmten Abschnitten des Dokuments zu.</span><span class="sxs-lookup"><span data-stu-id="8961c-167">That schema only allows certain Markdown blocks in specific sections of the document.</span></span> <span data-ttu-id="8961c-168">Wenn Sie Inhalte an der falschen Stelle ablegen, schlägt der PlatyPS-Buildschritt fehl.</span><span class="sxs-lookup"><span data-stu-id="8961c-168">If you put content in the wrong location, the PlatyPS build step fails.</span></span> <span data-ttu-id="8961c-169">Weitere Informationen finden Sie in der Dokumentation zum [Schema][] im PlatyPS-Repository.</span><span class="sxs-lookup"><span data-stu-id="8961c-169">For more information, see the [schema][] documentation in the PlatyPS repository.</span></span> <span data-ttu-id="8961c-170">Ein umfassendes Beispiel einer wohlgeformten Cmdlet-Referenz finden Sie unter [Get-Item][].</span><span class="sxs-lookup"><span data-stu-id="8961c-170">For a complete example of well-formed cmdlet reference, see [Get-Item][].</span></span>

<span data-ttu-id="8961c-171">Nachdem Sie den erforderlichen Inhalt für jedes Ihrer Cmdlets bereitgestellt haben, müssen Sie die Zielseite des Moduls aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8961c-171">After providing the required content for each of your cmdlets, you need to make sure that you update the module landing page.</span></span> <span data-ttu-id="8961c-172">Vergewissern Sie sich, dass Ihr Modul die richtigen Werte für `Module Guid` und `Download Help Link` in den YAML-Metadaten der Datei `<module-name>.md` enthält.</span><span class="sxs-lookup"><span data-stu-id="8961c-172">Verify your module has the correct `Module Guid` and `Download Help Link` values in the YAML metadata of the `<module-name>.md` file.</span></span> <span data-ttu-id="8961c-173">Fügen Sie fehlende Metadaten hinzu.</span><span class="sxs-lookup"><span data-stu-id="8961c-173">Add any missing metadata.</span></span>

<span data-ttu-id="8961c-174">Sie werden auch feststellen, dass einigen Cmdlets möglicherweise eine **Übersicht** (_Kurzbeschreibung_) fehlt.</span><span class="sxs-lookup"><span data-stu-id="8961c-174">Also, you may notice that some cmdlets may be missing a **Synopsis** (_short description_).</span></span> <span data-ttu-id="8961c-175">Der folgende Befehl aktualisiert die Zielseite des Moduls mit dem Beschreibungstext Ihrer **Übersicht**.</span><span class="sxs-lookup"><span data-stu-id="8961c-175">The following command updates the module landing page with your **Synopsis** description text.</span></span> <span data-ttu-id="8961c-176">Öffnen Sie die Zielseite des Moduls, um die Beschreibungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8961c-176">Open the module landing page to verify the descriptions.</span></span>

```powershell
Update-MarkdownHelpModule –Path <full path output folder> -RefreshModulePage
```

<span data-ttu-id="8961c-177">Nachdem Sie den gesamten Inhalt eingegeben haben, können Sie nun die MAML-Hilfedateien erstellen, die von `Get-Help` in der PowerShell-Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8961c-177">Now that you have entered all the content, you can create the MAML help files that are displayed by `Get-Help` in the PowerShell console.</span></span>

## <a name="create-the-external-help-files"></a><span data-ttu-id="8961c-178">Erstellen der externen Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="8961c-178">Create the external help files</span></span>

<span data-ttu-id="8961c-179">In diesem Schritt werden die MAML-Hilfedateien erstellt, die von `Get-Help` in der PowerShell-Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8961c-179">This step creates the MAML help files that are displayed by `Get-Help` in the PowerShell console.</span></span>

<span data-ttu-id="8961c-180">Führen Sie den folgenden Befehl aus, um die MAML-Dateien zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="8961c-180">To build the MAML files, run the following command:</span></span>

```powershell
New-ExternalHelp –Path <folder with MDs> -OutputPath <output help folder>
```

<span data-ttu-id="8961c-181">`New-ExternalHelp` konvertiert alle Markdown-Dateien von Cmdlets in eine (oder mehrere) MAML-Dateien.</span><span class="sxs-lookup"><span data-stu-id="8961c-181">`New-ExternalHelp` converts all of the cmdlet Markdown files into one (or more) MAML files.</span></span> <span data-ttu-id="8961c-182">Info-Dateien werden in einfache Textdateien mit dem folgenden Namensformat konvertiert: `about_topic_name.help.txt`.</span><span class="sxs-lookup"><span data-stu-id="8961c-182">About files are converted to plain-text files with the following name format: `about_topic_name.help.txt`.</span></span>
<span data-ttu-id="8961c-183">Der Markdown-Inhalt muss die Anforderung des PlatyPS-Schemas erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8961c-183">The Markdown content must meet the requirement of the PlatyPS schema.</span></span> <span data-ttu-id="8961c-184">`New-ExternalHelp` wird mit Fehlern beendet, wenn der Inhalt nicht dem Schema folgt.</span><span class="sxs-lookup"><span data-stu-id="8961c-184">`New-ExternalHelp` will exits with errors when the content does not follow the schema.</span></span> <span data-ttu-id="8961c-185">Sie müssen die Dateien bearbeiten und die Schemaverstöße beheben.</span><span class="sxs-lookup"><span data-stu-id="8961c-185">You must edit the files to fix the schema violations.</span></span>

> [!CAUTION]
> <span data-ttu-id="8961c-186">PlatyPS wandelt die `about_*.md`-Dateien schlecht in einfachen Text um.</span><span class="sxs-lookup"><span data-stu-id="8961c-186">PlatyPS does a poor job converting the `about_*.md` files to plain text.</span></span> <span data-ttu-id="8961c-187">Sie müssen sehr einfaches Markdown verwenden, um akzeptable Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="8961c-187">You must use very simple Markdown to get acceptable results.</span></span> <span data-ttu-id="8961c-188">Möglicherweise möchten Sie die Dateien im einfachen Textformat `about_topic_name.help.txt` beibehalten, anstatt PlatyPS die Umwandlung zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="8961c-188">You may want to maintain the files in plain-text `about_topic_name.help.txt` format, rather than allowing PlatyPS to convert them.</span></span>

<span data-ttu-id="8961c-189">Nach diesem Schritt sehen Sie die Dateien `*-help.xml` und `about_*.help.txt` im Zielausgabeordner.</span><span class="sxs-lookup"><span data-stu-id="8961c-189">Once this step is complete, you will see `*-help.xml` and `about_*.help.txt` files in the target output folder.</span></span>

<span data-ttu-id="8961c-190">Weitere Informationen finden Sie unter [New-ExternalHelp][].</span><span class="sxs-lookup"><span data-stu-id="8961c-190">For more information, see [New-ExternalHelp][]</span></span>

### <a name="test-the-compiled-help-files"></a><span data-ttu-id="8961c-191">Testen der kompilierten Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="8961c-191">Test the compiled help files</span></span>

<span data-ttu-id="8961c-192">Sie können den Inhalt mit dem Cmdlet [Get-HelpPreview][] überprüfen:</span><span class="sxs-lookup"><span data-stu-id="8961c-192">You can verify the content with the [Get-HelpPreview][] cmdlet:</span></span>

```powershell
Get-HelpPreview -Path "<ModuleName>-Help.xml"
```

<span data-ttu-id="8961c-193">Das Cmdlet liest die kompilierte MAML-Datei und gibt den Inhalt in dem Format aus, das Sie von `Get-Help` empfangen würden.</span><span class="sxs-lookup"><span data-stu-id="8961c-193">The cmdlet reads the compiled MAML file and outputs the content in the same format you would receive from `Get-Help`.</span></span> <span data-ttu-id="8961c-194">Auf diese Weise können Sie die Ergebnisse überprüfen, um sicherzustellen, dass die Markdown-Dateien einwandfrei kompiliert wurden und die gewünschten Ergebnisse liefern.</span><span class="sxs-lookup"><span data-stu-id="8961c-194">This allows you to inspect the results to verify that the Markdown files compiled correctly and produce the desired results.</span></span> <span data-ttu-id="8961c-195">Wenn Sie einen Fehler finden, bearbeiten Sie die Markdown-Dateien erneut, und kompilieren Sie die MAML-Dateien neu.</span><span class="sxs-lookup"><span data-stu-id="8961c-195">If you find an error, re-edit the Markdown files and recompile the MAML.</span></span>

<span data-ttu-id="8961c-196">Nun können Sie Ihre Hilfedateien veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8961c-196">Now you are ready to publish your help files.</span></span>

## <a name="publishing-your-help"></a><span data-ttu-id="8961c-197">Veröffentlichen Ihrer Hilfe</span><span class="sxs-lookup"><span data-stu-id="8961c-197">Publishing your help</span></span>

<span data-ttu-id="8961c-198">Nun, da Sie die Markdown-Dateien zu PowerShell-Hilfedateien kompiliert haben, können Sie die Dateien den Benutzern zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="8961c-198">Now that you have compiled the Markdown files into PowerShell help files, you are ready to make the files available to users.</span></span> <span data-ttu-id="8961c-199">Es gibt in der PowerShell-Konsole zwei Optionen für die Bereitstellung von Hilfe.</span><span class="sxs-lookup"><span data-stu-id="8961c-199">There are two options for providing help in the PowerShell console.</span></span>

- <span data-ttu-id="8961c-200">Packen der Hilfedateien mit dem Modul</span><span class="sxs-lookup"><span data-stu-id="8961c-200">Package the help files with the module</span></span>
- <span data-ttu-id="8961c-201">Erstellen eines aktualisierbaren Hilfepakets, das Benutzer mit dem Cmdlet `Update-Help` installieren</span><span class="sxs-lookup"><span data-stu-id="8961c-201">Create an updateable help package that users install with the `Update-Help` cmdlet</span></span>

### <a name="packaging-help-with-the-module"></a><span data-ttu-id="8961c-202">Packen der Hilfe mit dem Modul</span><span class="sxs-lookup"><span data-stu-id="8961c-202">Packaging help with the module</span></span>

<span data-ttu-id="8961c-203">Die Hilfedateien können mit Ihrem Modul gepackt werden.</span><span class="sxs-lookup"><span data-stu-id="8961c-203">The help files can be packaged with your module.</span></span> <span data-ttu-id="8961c-204">Ausführliche Informationen zur Ordnerstruktur finden Sie unter [Schreiben von Hilfe für Module][].</span><span class="sxs-lookup"><span data-stu-id="8961c-204">See [Writing Help for Modules][] for details of the folder structure.</span></span> <span data-ttu-id="8961c-205">Sie sollten die Liste der Hilfedateien in den Wert des Schlüssels **FileList** im Modulmanifest aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="8961c-205">You should include the list of Help files in the value of the **FileList** key in the module manifest.</span></span>

### <a name="creating-an-updateable-help-package"></a><span data-ttu-id="8961c-206">Erstellen eines aktualisierbaren Hilfepakets</span><span class="sxs-lookup"><span data-stu-id="8961c-206">Creating an updateable help package</span></span>

<span data-ttu-id="8961c-207">Die allgemeinen Schritte zum Erstellen einer aktualisierbaren Hilfe sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8961c-207">At a high level, the steps to create updateable help include:</span></span>

1. <span data-ttu-id="8961c-208">Bestimmen einer Internetwebsite zum Hosten der Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="8961c-208">Find an internet site to host your help files</span></span>
1. <span data-ttu-id="8961c-209">Hinzufügen des Schlüssels **HelpInfoURI** zum Modulmanifest</span><span class="sxs-lookup"><span data-stu-id="8961c-209">Add a **HelpInfoURI** key to your module manifest</span></span>
1. <span data-ttu-id="8961c-210">Erstellen der XML-Datei HelpInfo</span><span class="sxs-lookup"><span data-stu-id="8961c-210">Create a HelpInfo XML file</span></span>
1. <span data-ttu-id="8961c-211">Erstellen von CAB-Dateien</span><span class="sxs-lookup"><span data-stu-id="8961c-211">Create CAB files</span></span>
1. <span data-ttu-id="8961c-212">Hochladen Ihrer Dateien</span><span class="sxs-lookup"><span data-stu-id="8961c-212">Upload your files</span></span>

<span data-ttu-id="8961c-213">Weitere Informationen finden Sie unter [Unterstützen einer aktualisierbaren Hilfe: ausführliche Anleitung][step-by-step].</span><span class="sxs-lookup"><span data-stu-id="8961c-213">For more information, see [Supporting Updateable Help: Step-by-step][step-by-step].</span></span>

<span data-ttu-id="8961c-214">PlatyPS unterstützt Sie bei einigen dieser Schritte.</span><span class="sxs-lookup"><span data-stu-id="8961c-214">PlatyPS assists you with  some of these steps.</span></span>

<span data-ttu-id="8961c-215">**HelpInfoURI** ist eine URL, die auf den Speicherort verweist, an dem Ihre Hilfedateien im Internet gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="8961c-215">The **HelpInfoURI** is a URL that points to location where your help files are hosted on the internet.</span></span> <span data-ttu-id="8961c-216">Dieser Wert wird im Modulmanifest konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8961c-216">This value is configured in the module manifest.</span></span> <span data-ttu-id="8961c-217">`Update-Help` liest das Modulmanifest, um diese URL zu erhalten und den aktualisierbaren Hilfeinhalt herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="8961c-217">`Update-Help` reads the module manifest to get this URL and download the updateable help content.</span></span> <span data-ttu-id="8961c-218">Diese URL darf nur auf den Speicherort des Ordners und nicht auf einzelne Dateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="8961c-218">This URL should only point to the folder location and not to individual files.</span></span> <span data-ttu-id="8961c-219">`Update-Help` erstellt die herunterzuladenden Dateinamen auf Grundlage anderer Informationen im Modulmanifest und in der HelpInfo-XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="8961c-219">`Update-Help` constructs the filenames to download based on other information from the module manifest and the HelpInfo XML file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8961c-220">**HelpInfoURI** muss mit einem Schrägstrich (`/`) enden.</span><span class="sxs-lookup"><span data-stu-id="8961c-220">The **HelpInfoURI** must end with a forward-slash character (`/`).</span></span> <span data-ttu-id="8961c-221">Ohne dieses Zeichen kann `Update-Help` die ordnungsgemäßen Dateipfade zum Herunterladen des Inhalts nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="8961c-221">Without that character, `Update-Help` cannot construct the correct file paths to download the content.</span></span> <span data-ttu-id="8961c-222">Außerdem wird bei den meisten HTTP-basierten Dateidiensten Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="8961c-222">Also, most HTTP-based file services are case-sensitive.</span></span> <span data-ttu-id="8961c-223">Es ist wichtig, dass die Modulmetadaten in der HelpInfo-XML-Datei die richtige Groß-/Kleinschreibung enthalten.</span><span class="sxs-lookup"><span data-stu-id="8961c-223">It is important that the module metadata in the HelpInfo XML file contains the proper letter case.</span></span>

<span data-ttu-id="8961c-224">Mit dem Cmdlet `New-ExternalHelp` wird die HelpInfo-XML-Datei im Ausgabeordner erstellt.</span><span class="sxs-lookup"><span data-stu-id="8961c-224">The `New-ExternalHelp` cmdlet creates the HelpInfo XML file in the output folder.</span></span> <span data-ttu-id="8961c-225">Die HelpInfo-XML-Datei wird mithilfe von YAML-Metadaten erstellt, die in den Markdown-Dateien (`ModuleName.md`) des Moduls enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8961c-225">The HelpInfo XML file is built using YAML metadata contained in the module Markdown files (`ModuleName.md`).</span></span>

<span data-ttu-id="8961c-226">Das Cmdlet `New-ExternalHelpCab` erstellt ZIP- und CAB-Dateien mit den von Ihnen kompilierten MAML- und `about_*.help.txt`-Dateien.</span><span class="sxs-lookup"><span data-stu-id="8961c-226">The `New-ExternalHelpCab` cmdlet creates ZIP and CAB files containing the MAML and `about_*.help.txt` files you compiled.</span></span> <span data-ttu-id="8961c-227">CAB-Dateien sind mit allen Versionen von PowerShell kompatibel.</span><span class="sxs-lookup"><span data-stu-id="8961c-227">CAB files are compatible with all versions of PowerShell.</span></span>
<span data-ttu-id="8961c-228">Ab PowerShell 6 können ZIP-Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8961c-228">PowerShell 6 and higher can use ZIP files.</span></span>

```powershell
$helpCabParameters = @{
    CabFilesFolder = $MamlOutputFolder
    LandingPagePath = $LandingPage
    OutputFolder = $CabOutputFolder
}
New-ExternalHelpCab @helpCabParameters
```

<span data-ttu-id="8961c-229">Nach dem Erstellen der ZIP- und CAB-Dateien laden Sie die ZIP-, CAB- und HelpInfo-XML-Dateien auf Ihren HTTP-Dateiserver hoch.</span><span class="sxs-lookup"><span data-stu-id="8961c-229">After creating the ZIP and CAB files, upload the ZIP, CAB, and HelpInfo XML files to your HTTP file server.</span></span> <span data-ttu-id="8961c-230">Legen Sie die Dateien an dem von **HelpInfoURI** angegebenen Speicherort ab.</span><span class="sxs-lookup"><span data-stu-id="8961c-230">Put the files in the location indicated by the **HelpInfoURI**.</span></span>

<span data-ttu-id="8961c-231">Weitere Informationen finden Sie unter [New-ExternalHelpCab][].</span><span class="sxs-lookup"><span data-stu-id="8961c-231">For more information, see [New-ExternalHelpCab][].</span></span>

### <a name="other-publishing-options"></a><span data-ttu-id="8961c-232">Weitere Veröffentlichungsoptionen</span><span class="sxs-lookup"><span data-stu-id="8961c-232">Other publishing options</span></span>

<span data-ttu-id="8961c-233">Markdown ist ein vielseitiges Format, das sich für die Veröffentlichung problemlos in andere Formate umwandeln lässt.</span><span class="sxs-lookup"><span data-stu-id="8961c-233">Markdown is a versatile format that is easy to transform to other formats for publishing.</span></span> <span data-ttu-id="8961c-234">Mit einem Tool wie [Pandoc][] können Sie Ihre Markdown-Hilfedateien in viele verschiedene Dokumentformate konvertieren, darunter Nur-Text, HTML, PDF und Office.</span><span class="sxs-lookup"><span data-stu-id="8961c-234">Using a tool like [Pandoc][], you can convert your Markdown help files to many different document formats, including plain text, HTML, PDF, and Office document formats.</span></span>

<span data-ttu-id="8961c-235">Darüber hinaus können die Cmdlets [ConvertFrom-Markdown][] und [Show-Markdown][] ab PowerShell 6 verwendet werden, um Markdown in HTML zu konvertieren oder eine farbige Anzeige in der PowerShell-Konsole zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8961c-235">Also, the cmdlets [ConvertFrom-Markdown][] and [Show-Markdown][] in PowerShell 6 and higher can be used to convert Markdown to HTML or create a colorful display in the PowerShell console.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8961c-236">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="8961c-236">Known issues</span></span>

<span data-ttu-id="8961c-237">PlatyPS reagiert sehr empfindlich auf das [-Schema][] für die Struktur der Markdown-Dateien, die es erstellt und kompiliert.</span><span class="sxs-lookup"><span data-stu-id="8961c-237">PlatyPS is very sensitive to the [schema][] for the structure of the Markdown files it creates and compiles.</span></span> <span data-ttu-id="8961c-238">Es ist sehr einfach, gültige Markdown-Inhalte zu schreiben, die gegen dieses Schema verstoßen.</span><span class="sxs-lookup"><span data-stu-id="8961c-238">It is very easy write valid Markdown that violates this schema.</span></span> <span data-ttu-id="8961c-239">Weitere Informationen finden Sie im [Styleguide für PowerShell][] und unter[Bearbeiten von Referenzartikeln][].</span><span class="sxs-lookup"><span data-stu-id="8961c-239">For more information, consult the [PowerShell style guide][] and [Editing reference articles][].</span></span>

<!-- link references -->
[platyps-repo]: https://github.com/PowerShell/platyps
[PlatyPS]: https://www.powershellgallery.com/packages/platyPS/
[Markdown]: https://commonmark.org
[markdig]: https://github.com/lunet-io/markdig
[schema]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[Get-Item]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/7.0/Microsoft.PowerShell.Management/Get-Item.md
[New-MarkdownHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownHelp.md
[Update-MarkdownHelpModule]: https://github.com/PowerShell/platyPS/blob/master/docs/Update-MarkdownHelpModule.md
[New-MarkdownAboutHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownAboutHelp.md
[New-ExternalHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelp.md
[Get-HelpPreview]: https://github.com/PowerShell/platyPS/blob/master/docs/Get-HelpPreview.md
[New-ExternalHelpCab]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelpCab.md
[Styleguide für PowerShell]: /powershell/scripting/community/contributing/powershell-style-guide
[PowerShell style guide]: /powershell/scripting/community/contributing/powershell-style-guide
[Bearbeiten von Referenzartikeln]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Editing reference articles]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Schreiben von Hilfe für Module]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[Writing Help for Modules]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[step-by-step]: /powershell/scripting/developer/help/updatable-help-authoring-step-by-step
[Pandoc]: https://pandoc.org
[ConvertFrom-Markdown]: /powershell/module/microsoft.powershell.utility/convertfrom-markdown
[Show-Markdown]: /powershell/module/microsoft.powershell.utility/show-markdown
