---
ms.date: 09/13/2016
ms.topic: reference
title: Unterstützung einer Onlinehilfe
description: Unterstützung einer Onlinehilfe
ms.openlocfilehash: 0164b5e6c6c8d66a6ab2467a8adfb7efffe0fe17
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645419"
---
# <a name="supporting-online-help"></a><span data-ttu-id="6e102-103">Unterstützung einer Onlinehilfe</span><span class="sxs-lookup"><span data-stu-id="6e102-103">Supporting Online Help</span></span>

<span data-ttu-id="6e102-104">Ab PowerShell 3,0 gibt es zwei Möglichkeiten, das `Get-Help` Online Feature für PowerShell-Befehle zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6e102-104">Beginning in PowerShell 3.0, there are two ways to support the `Get-Help` Online feature for PowerShell commands.</span></span> <span data-ttu-id="6e102-105">In diesem Thema wird erläutert, wie diese Funktion für verschiedene Befehls Typen implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="6e102-105">This topic explains how to implement this feature for different command types.</span></span>

## <a name="about-online-help"></a><span data-ttu-id="6e102-106">Informationen zur Online Hilfe</span><span class="sxs-lookup"><span data-stu-id="6e102-106">About Online Help</span></span>

<span data-ttu-id="6e102-107">Die Online Hilfe war immer ein wesentlicher Bestandteil von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e102-107">Online help has always been a vital part of PowerShell.</span></span> <span data-ttu-id="6e102-108">Obwohl das `Get-Help` Cmdlet an der Eingabeaufforderung Hilfe Themen anzeigt, bevorzugen viele Benutzer das Lesen der Online Dokumentation, einschließlich Farbcodierung, Hyperlinks und Freigabe von Ideen in Communityinhalten und Wiki-basierten Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="6e102-108">Although the `Get-Help` cmdlet displays help topics at the command prompt, many users prefer the experience of reading online, including color-coding, hyperlinks, and sharing ideas in Community Content and wiki-based documents.</span></span> <span data-ttu-id="6e102-109">Vor der Einführung der aktualisierbaren Hilfe stellte die Online Hilfe die aktuelle Version der Hilfedateien bereit.</span><span class="sxs-lookup"><span data-stu-id="6e102-109">Most importantly, before the advent of Updatable Help, online help provided the most up-to-date version of the help files.</span></span>

<span data-ttu-id="6e102-110">Mit der Einführung der aktualisierbaren Hilfe in PowerShell 3,0 spielt die Online Hilfe immer noch eine wichtige Rolle.</span><span class="sxs-lookup"><span data-stu-id="6e102-110">With the advent of Updatable Help in PowerShell 3.0, online help still plays a vital role.</span></span> <span data-ttu-id="6e102-111">Zusätzlich zur flexiblen Benutzer Darstellung bietet die Online Hilfe Benutzern Hilfe, die keine aktualisierbare Hilfe zum Herunterladen von Hilfe Themen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6e102-111">In addition to the flexible user experience, online help provides help to users who do not or cannot use Updatable Help to download help topics.</span></span>

## <a name="how-get-help--online-works"></a><span data-ttu-id="6e102-112">Funktionsweise von Get-Help-Online</span><span class="sxs-lookup"><span data-stu-id="6e102-112">How Get-Help -Online Works</span></span>

<span data-ttu-id="6e102-113">Um Benutzern die Suche nach den Online Hilfe Themen für Befehle zu erleichtern, `Get-Help` verfügt der Befehl über einen Online-Parameter, der die Online Version des Hilfe Themas für einen Befehl im Standard Internetbrowser des Benutzers öffnet.</span><span class="sxs-lookup"><span data-stu-id="6e102-113">To help users find the online help topics for commands, the `Get-Help` command has an Online parameter that opens the online version of help topic for a command in the user's default internet browser.</span></span>

<span data-ttu-id="6e102-114">Mit dem folgenden Befehl wird beispielsweise das Online Hilfethema für das `Invoke-Command` Cmdlet geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e102-114">For example, the following command opens the online help topic for the `Invoke-Command` cmdlet.</span></span>

```powershell
Get-Help Invoke-Command -Online
```

<span data-ttu-id="6e102-115">Zum Implementieren von `Get-Help -Online` `Get-Help` sucht das Cmdlet in den folgenden Speicherorten nach einem Uniform Resource Identifier (URI) für das Hilfethema der Online Version.</span><span class="sxs-lookup"><span data-stu-id="6e102-115">To implement `Get-Help -Online`, the `Get-Help` cmdlet looks for a Uniform Resource Identifier (URI) for the online version help topic in the following locations.</span></span>

- <span data-ttu-id="6e102-116">Der erste Link im Abschnitt " **Verwandte Links** " des Hilfe Themas für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="6e102-116">The first link in the **Related Links** section of the help topic for the command.</span></span> <span data-ttu-id="6e102-117">Das Hilfethema muss auf dem Computer des Benutzers installiert sein.</span><span class="sxs-lookup"><span data-stu-id="6e102-117">The help topic must be installed on the user's computer.</span></span> <span data-ttu-id="6e102-118">Diese Funktion wurde in PowerShell 2,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6e102-118">This feature was introduced in PowerShell 2.0.</span></span>

- <span data-ttu-id="6e102-119">Die **HelpUri** -Eigenschaft eines beliebigen Befehls.</span><span class="sxs-lookup"><span data-stu-id="6e102-119">The **HelpUri** property of any command.</span></span> <span data-ttu-id="6e102-120">Der Zugriff auf die **HelpUri** -Eigenschaft ist auch dann möglich, wenn das Hilfethema für den Befehl nicht auf dem Computer des Benutzers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="6e102-120">The **HelpUri** property is accessible even when the help topic for the command is not installed on the user's computer.</span></span> <span data-ttu-id="6e102-121">Diese Funktion wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6e102-121">This feature was introduced in PowerShell 3.0.</span></span>

  <span data-ttu-id="6e102-122">`Get-Help` sucht im ersten Eintrag im Abschnitt " **Verwandte Links** " nach einem URI, bevor der Wert der **HelpUri** -Eigenschaft erhalten wird.</span><span class="sxs-lookup"><span data-stu-id="6e102-122">`Get-Help` looks for a URI in the first entry in the **Related Links** section before getting the **HelpUri** property value.</span></span> <span data-ttu-id="6e102-123">Wenn der Eigenschafts Wert falsch ist oder geändert wurde, können Sie ihn überschreiben, indem Sie im ersten verknüpften Link einen anderen Wert eingeben.</span><span class="sxs-lookup"><span data-stu-id="6e102-123">If the property value is incorrect or has changed, you can override it by entering a different value in the first related link.</span></span> <span data-ttu-id="6e102-124">Der erste Verwandte Link funktioniert jedoch nur, wenn die Hilfe Themen auf dem Computer des Benutzers installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6e102-124">However, the first related link works only when the help topics are installed on the user's computer.</span></span>

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a><span data-ttu-id="6e102-125">Hinzufügen eines URIs zum ersten verknüpften Link eines Befehls Hilfe Themas</span><span class="sxs-lookup"><span data-stu-id="6e102-125">Adding a URI to the first related link of a command help topic</span></span>

<span data-ttu-id="6e102-126">Sie können `Get-Help -Online` einen beliebigen Befehl unterstützen, indem Sie dem ersten Eintrag im Abschnitt **Verwandte Links** des XML-basierten Hilfe Themas für den Befehl einen gültigen URI hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6e102-126">You can support `Get-Help -Online` for any command by adding a valid URI to the first entry in the **Related Links** section of the XML-based help topic for the command.</span></span> <span data-ttu-id="6e102-127">Diese Option ist nur in XML-basierten Hilfe Themen gültig und funktioniert nur, wenn das Hilfethema auf dem Computer des Benutzers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="6e102-127">This option is valid only in XML-based help topics and works only when the help topic is installed on the user's computer.</span></span> <span data-ttu-id="6e102-128">Wenn das Hilfethema installiert ist und der URI aufgefüllt wird, hat dieser Wert Vorrang vor der **HelpUri** -Eigenschaft des Befehls.</span><span class="sxs-lookup"><span data-stu-id="6e102-128">When the help topic is installed and the URI is populated, this value takes precedence over the **HelpUri** property of the command.</span></span>

<span data-ttu-id="6e102-129">Um diese Funktion zu unterstützen, muss der URI im- `maml:uri` Element unter dem ersten `maml:relatedLinks/maml:navigationLink` Element im-Element enthalten sein `maml:relatedLinks` .</span><span class="sxs-lookup"><span data-stu-id="6e102-129">To support this feature, the URI must appear in the `maml:uri` element under the first `maml:relatedLinks/maml:navigationLink` element in the `maml:relatedLinks` element.</span></span>

<span data-ttu-id="6e102-130">Der folgende XML-Code zeigt die korrekte Platzierung des URI.</span><span class="sxs-lookup"><span data-stu-id="6e102-130">The following XML shows the correct placement of the URI.</span></span> <span data-ttu-id="6e102-131">Der `Online version:` Text im- `maml:linkText` Element ist eine bewährte Vorgehensweise, aber er ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e102-131">The `Online version:` text in the `maml:linkText` element is a best practice, but it is not required.</span></span>

```xml
<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>https://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a><span data-ttu-id="6e102-132">Hinzufügen der HelpUri-Eigenschaft zu einem Befehl</span><span class="sxs-lookup"><span data-stu-id="6e102-132">Adding the HelpUri property to a command</span></span>

<span data-ttu-id="6e102-133">In diesem Abschnitt wird gezeigt, wie die HelpUri-Eigenschaft Befehlen verschiedener Typen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6e102-133">This section shows how to add the HelpUri property to commands of different types.</span></span>

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a><span data-ttu-id="6e102-134">Hinzufügen einer HelpUri-Eigenschaft zu einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6e102-134">Adding a HelpUri Property to a Cmdlet</span></span>

<span data-ttu-id="6e102-135">Fügen Sie für in c# geschriebene Cmdlets der **Cmdlet** -Klasse ein **HelpUri** -Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e102-135">For cmdlets written in C#, add a **HelpUri** attribute to the **Cmdlet** class.</span></span> <span data-ttu-id="6e102-136">Der Wert des-Attributs muss ein URI sein, der mit `http` oder beginnt `https` .</span><span class="sxs-lookup"><span data-stu-id="6e102-136">The value of the attribute must be a URI that begins with `http` or `https`.</span></span>

<span data-ttu-id="6e102-137">Der folgende Code zeigt das **HelpUri** -Attribut der `Get-History` Cmdlet-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6e102-137">The following code shows the **HelpUri** attribute of the `Get-History` cmdlet class.</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "https://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a><span data-ttu-id="6e102-138">Hinzufügen einer HelpUri-Eigenschaft zu einer erweiterten Funktion</span><span class="sxs-lookup"><span data-stu-id="6e102-138">Adding a HelpUri Property to an Advanced Function</span></span>

<span data-ttu-id="6e102-139">Fügen Sie für erweiterte Funktionen eine **HelpUri** -Eigenschaft zum **cmdletbinding** -Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e102-139">For advanced functions, add a **HelpUri** property to the **CmdletBinding** attribute.</span></span> <span data-ttu-id="6e102-140">Der Wert der Eigenschaft muss ein URI sein, der mit "http" oder "https" beginnt.</span><span class="sxs-lookup"><span data-stu-id="6e102-140">The value of the property must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="6e102-141">Der folgende Code zeigt das **HelpUri** -Attribut der `New-Calendar` Funktion.</span><span class="sxs-lookup"><span data-stu-id="6e102-141">The following code shows the **HelpUri** attribute of the `New-Calendar` function</span></span>

```powershell
function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="https://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a><span data-ttu-id="6e102-142">Hinzufügen eines HelpUri-Attributs zu einem CIM-Befehl</span><span class="sxs-lookup"><span data-stu-id="6e102-142">Adding a HelpUri Attribute to a CIM Command</span></span>

<span data-ttu-id="6e102-143">Fügen Sie für CIM-Befehle dem **cmdletmetadata** -Element in der cdxml-Datei ein **HelpUri** -Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e102-143">For CIM commands, add a **HelpUri** attribute to the **CmdletMetadata** element in the CDXML file.</span></span>
<span data-ttu-id="6e102-144">Der Wert des-Attributs muss ein URI sein, der mit `http` oder beginnt `https` .</span><span class="sxs-lookup"><span data-stu-id="6e102-144">The value of the attribute must be a URI that begins with `http` or `https`.</span></span>

<span data-ttu-id="6e102-145">Der folgende Code zeigt das HelpUri-Attribut des `Start-Debug` CIM-Befehls.</span><span class="sxs-lookup"><span data-stu-id="6e102-145">The following code shows the HelpUri attribute of the `Start-Debug` CIM command</span></span>

```xml
<CmdletMetadata Verb="Debug" HelpUri="https://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a><span data-ttu-id="6e102-146">Hinzufügen eines HelpUri-Attributs zu einem Workflow</span><span class="sxs-lookup"><span data-stu-id="6e102-146">Adding a HelpUri Attribute to a Workflow</span></span>

<span data-ttu-id="6e102-147">Fügen Sie für Workflows, die in der PowerShell-Sprache geschrieben sind, ein hinzu **. Externalhelp** -Kommentar Anweisung an den Workflow Code.</span><span class="sxs-lookup"><span data-stu-id="6e102-147">For workflows that are written in the PowerShell language, add an **.ExternalHelp** comment directive to the workflow code.</span></span> <span data-ttu-id="6e102-148">Der Wert der-Direktive muss ein URI sein, der mit `http` oder beginnt `https` .</span><span class="sxs-lookup"><span data-stu-id="6e102-148">The value of the directive must be a URI that begins with `http` or `https`.</span></span>

> [!NOTE]
> <span data-ttu-id="6e102-149">Die HelpUri-Eigenschaft wird für XAML-basierte Workflows in PowerShell nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e102-149">The HelpUri property is not supported for XAML-based workflows in PowerShell.</span></span>

<span data-ttu-id="6e102-150">Der folgende Code zeigt den. Externalhelp-Direktive in einer Workflow Datei.</span><span class="sxs-lookup"><span data-stu-id="6e102-150">The following code shows the .ExternalHelp directive in a workflow file.</span></span>

```powershell
# .ExternalHelp "https://go.microsoft.com/fwlink/?LinkID=138338"
```
