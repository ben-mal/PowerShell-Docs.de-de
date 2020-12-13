---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen der Cmdlet-Hilfedatei
description: Erstellen der Cmdlet-Hilfedatei
ms.openlocfilehash: 40259c8f9496b10380805a78f3711aed6f1bf2e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659088"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="67f2a-103">Erstellen der Cmdlet-Hilfedatei</span><span class="sxs-lookup"><span data-stu-id="67f2a-103">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="67f2a-104">In diesem Abschnitt wird beschrieben, wie Sie eine gültige XML-Datei erstellen, die Inhalt für Windows PowerShell-Cmdlet-Hilfe Themen enthält.</span><span class="sxs-lookup"><span data-stu-id="67f2a-104">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="67f2a-105">In diesem Abschnitt wird erläutert, wie Sie die Hilfedatei benennen, die entsprechenden XML-Header hinzufügen und Knoten hinzufügen, die die verschiedenen Abschnitte der Cmdlet-Hilfe Inhalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="67f2a-105">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="67f2a-106">Eine umfassende Ansicht einer Hilfedatei erhalten Sie, indem Sie eine der `dll-Help.xml` Dateien öffnen, die sich im Windows PowerShell-Installationsverzeichnis befinden.</span><span class="sxs-lookup"><span data-stu-id="67f2a-106">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="67f2a-107">Die `Microsoft.PowerShell.Commands.Management.dll-Help.xml` Datei enthält z. b. Inhalte für mehrere PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="67f2a-107">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="67f2a-108">Erstellen einer Cmdlet-Hilfedatei</span><span class="sxs-lookup"><span data-stu-id="67f2a-108">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="67f2a-109">Erstellen Sie eine Textdatei, und speichern Sie Sie mithilfe der UTF8-Codierung.</span><span class="sxs-lookup"><span data-stu-id="67f2a-109">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="67f2a-110">Der Dateiname muss das folgende Format aufweisen, damit Windows PowerShell ihn als Cmdlet-Hilfedatei erkennen kann.</span><span class="sxs-lookup"><span data-stu-id="67f2a-110">The filename must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

1. <span data-ttu-id="67f2a-111">Fügen Sie die folgenden XML-Header der Textdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-111">Add the following XML headers to the text file.</span></span> <span data-ttu-id="67f2a-112">Beachten Sie, dass die Datei mit dem Schema der Microsoft-Unterstützung Markup Sprache (MAML) überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="67f2a-112">Be aware that the file will be validated against the Microsoft Assistance Markup Language (MAML) schema.</span></span> <span data-ttu-id="67f2a-113">PowerShell stellt derzeit keine Tools zum Überprüfen der Datei bereit.</span><span class="sxs-lookup"><span data-stu-id="67f2a-113">Currently, PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

1. <span data-ttu-id="67f2a-114">Fügen Sie der Cmdlet-Hilfedatei einen **Befehls** Knoten für jedes Cmdlet in der Assembly hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-114">Add a **Command** node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="67f2a-115">Jeder Knoten im **Befehls** Knoten bezieht sich auf die verschiedenen Abschnitte des Cmdlet-Hilfe Themas.</span><span class="sxs-lookup"><span data-stu-id="67f2a-115">Each node within the **Command** node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="67f2a-116">In der folgenden Tabelle wird das XML-Element für jeden Knoten aufgeführt, gefolgt von einer Beschreibung der einzelnen Knoten.</span><span class="sxs-lookup"><span data-stu-id="67f2a-116">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |           <span data-ttu-id="67f2a-117">Knoten</span><span class="sxs-lookup"><span data-stu-id="67f2a-117">Node</span></span>           |                                                                                                     <span data-ttu-id="67f2a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67f2a-118">Description</span></span>                                                                                                     |
   | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | `<details>`              | <span data-ttu-id="67f2a-119">Fügt Inhalt für die Abschnitte "Name" und "Synopsis" des Cmdlet-Hilfe Themas hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-119">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="67f2a-120">Weitere Informationen finden Sie unter Vorgehens [Weise beim Hinzufügen des Cmdlet-namens und der Synchronisierungs](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)Datei.</span><span class="sxs-lookup"><span data-stu-id="67f2a-120">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span> |
   | `<maml:description>`     | <span data-ttu-id="67f2a-121">Fügt Inhalt für den Beschreibungs Abschnitt des Cmdlet-Hilfe Themas hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-121">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="67f2a-122">Weitere Informationen finden Sie unter Vorgehens [Weise beim Hinzufügen der ausführlichen Beschreibung zu einem Cmdlet-Hilfethema](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="67f2a-122">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>                    |
   | `<command:syntax>`       | <span data-ttu-id="67f2a-123">Fügt Inhalt für den Syntax Abschnitt des Cmdlet-Hilfe Themas hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-123">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="67f2a-124">Weitere Informationen finden Sie unter Vorgehens [Weise beim Hinzufügen von Syntax zu einem Cmdlet-Hilfethema](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="67f2a-124">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>                                  |
   | `<command:parameters>`   | <span data-ttu-id="67f2a-125">Fügt Inhalt für den Parameter Abschnitt des Cmdlet-Hilfe Themas hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-125">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="67f2a-126">Weitere Informationen finden Sie unter Vorgehens [Weise beim Hinzufügen von Parametern zu einem Cmdlet-Hilfethema](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="67f2a-126">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>                                  |
   | `<command:inputTypes>`   | <span data-ttu-id="67f2a-127">Fügt Inhalt für den Abschnitt Eingaben des Hilfe Themas für das Cmdlet hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-127">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="67f2a-128">Weitere Informationen finden Sie unter Vorgehens [Weise beim Hinzufügen von Eingabetypen zu einem Cmdlet-Hilfethema](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="67f2a-128">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>                        |
   | `<command:returnValues>` | <span data-ttu-id="67f2a-129">Fügt Inhalt für den Abschnitt "Outputs" des Cmdlet-Hilfe Themas hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-129">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="67f2a-130">Weitere Informationen finden Sie unter Vorgehens [Weise beim Hinzufügen von Rückgabe Werten zu einem Cmdlet-Hilfethema](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="67f2a-130">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>                   |
   | `<maml:alertset>`        | <span data-ttu-id="67f2a-131">Fügt Inhalt für den Abschnitt Notizen des Cmdlet-Hilfe Themas hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-131">Adds content for the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="67f2a-132">Weitere Informationen finden Sie unter Vorgehens [Weise beim Hinzufügen von Notizen zu einem Cmdlet-Hilfethema](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="67f2a-132">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>                                      |
   | `<command:examples>`     | <span data-ttu-id="67f2a-133">Fügt Inhalt für den Abschnitt "Beispiele" des Cmdlet-Hilfe Themas hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-133">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="67f2a-134">Weitere Informationen finden Sie unter [Hinzufügen von Beispielen zu einem Cmdlet-Hilfethema](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="67f2a-134">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>                            |
   | `<maml:relatedLinks>`    | <span data-ttu-id="67f2a-135">Fügt Inhalt für den Abschnitt "Verwandte Links" des Cmdlet-Hilfe Themas hinzu.</span><span class="sxs-lookup"><span data-stu-id="67f2a-135">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="67f2a-136">Weitere Informationen finden Sie [unter Hinzufügen verwandter Links zu einem Cmdlet-Hilfethema](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="67f2a-136">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>             |

## <a name="example"></a><span data-ttu-id="67f2a-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67f2a-137">Example</span></span>

 <span data-ttu-id="67f2a-138">Im folgenden finden Sie ein Beispiel für einen **Befehls** Knoten, der die Knoten für die verschiedenen Abschnitte des Cmdlet-Hilfe Themas enthält.</span><span class="sxs-lookup"><span data-stu-id="67f2a-138">Here is an example of a **Command** node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

```xml
<command:command
  xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
  xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
  <command:details>
    <!--Add name an synopsis here-->
  </command:details>
  <maml:description>
    <!--Add detailed description here-->
  </maml:description>
  <command:syntax>
    <!--Add syntax information here-->
  </command:syntax>
  <command:parameters>
    <!--Add parameter information here-->
  </command:parameters>
  <command:inputTypes>
    <!--Add input type information here-->
  </command:inputTypes>
  <command:returnValues>
    <!--Add return value information here-->
  </command:returnValues>
  <maml:alertSet>
    <!--Add Note information here-->
  </maml:alertSet>
  <command:examples>
    <!--Add cmdlet examples here-->
  </command:examples>
  <maml:relatedLinks>
    <!--Add links to related content here-->
  </maml:relatedLinks>
</command:command>
```

## <a name="see-also"></a><span data-ttu-id="67f2a-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67f2a-139">See Also</span></span>

 [<span data-ttu-id="67f2a-140">Vorgehensweise beim Hinzufügen des Cmdlet-namens und der Synopsis</span><span class="sxs-lookup"><span data-stu-id="67f2a-140">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="67f2a-141">Vorgehensweise beim Hinzufügen der ausführlichen Beschreibung zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="67f2a-141">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="67f2a-142">Hinzufügen einer Syntax zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="67f2a-142">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="67f2a-143">Vorgehensweise beim Hinzufügen von Parametern zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="67f2a-143">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="67f2a-144">Hinzufügen von Eingabetypen zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="67f2a-144">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="67f2a-145">Hinzufügen von Rückgabewerten zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="67f2a-145">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="67f2a-146">Vorgehensweise beim Hinzufügen von Notizen zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="67f2a-146">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="67f2a-147">Hinzufügen von Beispielen zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="67f2a-147">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="67f2a-148">Hinzufügen von zugehörigen Verknüpfungen zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="67f2a-148">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="67f2a-149">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="67f2a-149">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
