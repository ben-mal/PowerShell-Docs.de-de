---
ms.date: 09/12/2016
ms.topic: reference
title: Hinzufügen von Parameterinformationen
description: Hinzufügen von Parameterinformationen
ms.openlocfilehash: 8f4fc46ef256a77b058df4ba506124f80732cb39
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663043"
---
# <a name="how-to-add-parameter-information"></a><span data-ttu-id="5c0f1-103">Hinzufügen von Parameterinformationen</span><span class="sxs-lookup"><span data-stu-id="5c0f1-103">How to Add Parameter Information</span></span>

<span data-ttu-id="5c0f1-104">In diesem Abschnitt wird beschrieben, wie Sie Inhalte hinzufügen, die im Abschnitt **Parameters** des Cmdlet-Hilfe Themas angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-104">This section describes how to add content that is displayed in the **PARAMETERS** section of the cmdlet Help topic.</span></span> <span data-ttu-id="5c0f1-105">Der Abschnitt **para** meters des Hilfe Themas Listet jeden Parameter des Cmdlets auf und stellt eine ausführliche Beschreibung der einzelnen Parameter bereit.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-105">The **PARAMETERS** section of the Help topic lists each of the parameters of the cmdlet and provides a detailed description of each parameter.</span></span>

<span data-ttu-id="5c0f1-106">Der Inhalt des **Parameters** -Abschnitts sollte mit dem Inhalt des **Syntax** Abschnitts des Hilfe Themas konsistent sein.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-106">The content of the **PARAMETERS** section should be consistent with the content of the **SYNTAX** section of the Help topic.</span></span> <span data-ttu-id="5c0f1-107">Der Autor der Hilfe ist dafür verantwortlich, sicherzustellen, dass der Knoten **Syntax** und **Parameter** ähnliche XML-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-107">It is the responsibility of the Help author to make sure that both the **Syntax** and **Parameters** node contain similar XML elements.</span></span>

> [!NOTE]
> <span data-ttu-id="5c0f1-108">Eine umfassende Ansicht einer Hilfedatei erhalten Sie, indem Sie eine der `dll-Help.xml` Dateien im PowerShell-Installationsverzeichnis öffnen.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-108">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="5c0f1-109">Die `Microsoft.PowerShell.Commands.Management.dll-Help.xml` Datei enthält z. b. Inhalte für mehrere PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-109">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="to-add-parameters"></a><span data-ttu-id="5c0f1-110">So fügen Sie Parameter hinzu</span><span class="sxs-lookup"><span data-stu-id="5c0f1-110">To Add Parameters</span></span>

1. <span data-ttu-id="5c0f1-111">Öffnen Sie die Cmdlet-Hilfedatei, und suchen Sie den Befehls Knoten für das Cmdlet, das Sie dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-111">Open the cmdlet Help file and locate the Command node for the cmdlet you are documenting.</span></span> <span data-ttu-id="5c0f1-112">Wenn Sie ein neues Cmdlet hinzufügen, müssen Sie einen neuen Befehls Knoten erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-112">If you are adding a new cmdlet you will need to create a new Command node.</span></span> <span data-ttu-id="5c0f1-113">Die Hilfedatei enthält einen Befehls Knoten für jedes Cmdlet, für das Sie Hilfe Inhalte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-113">Your Help file will contain a Command node for each cmdlet that you are providing Help content for.</span></span> <span data-ttu-id="5c0f1-114">Im folgenden finden Sie ein Beispiel für einen leeren Befehls Knoten.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-114">Here is an example of a blank Command node.</span></span>

    ```xml
    <command:command>
    </command:command>
    ```

1. <span data-ttu-id="5c0f1-115">Suchen Sie im Befehls Knoten den Beschreibungs Knoten, und fügen Sie wie unten dargestellt einen Parameter Knoten hinzu.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-115">Within the Command node, locate the Description node and add a Parameters node as shown below.</span></span>
   <span data-ttu-id="5c0f1-116">Es ist nur ein Parameter Knoten zulässig, der unmittelbar auf den Syntax Knoten folgt.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-116">Only one Parameters node is allowed, and it should immediately follow the Syntax node.</span></span>

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

1. <span data-ttu-id="5c0f1-117">Fügen Sie im Knoten Parameter einen **Parameter** Knoten für jeden Parameter des Cmdlets hinzu, wie unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-117">Within the Parameters node, add a **Parameter** node for each parameter of the cmdlet as shown below.</span></span>

   <span data-ttu-id="5c0f1-118">In diesem Beispiel wird ein **Parameter** Knoten für drei Parameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-118">In this example, a **Parameter** node is added for three parameters.</span></span>

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   <span data-ttu-id="5c0f1-119">Da es sich hierbei um dieselben XML-Tags handelt, die im Syntax Knoten verwendet werden, und da die hier angegebenen Parameter mit den Parametern übereinstimmen müssen, die durch den Syntax Knoten angegeben werden, können Sie die Parameter Knoten aus dem Syntax Knoten kopieren und in den Parameter Knoten einfügen.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-119">Because these are the same XML tags that are used in the Syntax node, and because the parameters specified here must match the parameters specified by the Syntax node, you can copy the Parameter nodes from the Syntax node and paste them into the Parameters node.</span></span> <span data-ttu-id="5c0f1-120">Achten Sie jedoch darauf, nur eine Instanz eines Parameter Knotens zu kopieren, auch wenn der Parameter in mehreren Parameter Sätzen in der Syntax angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-120">However, be sure to copy only one instance of a Parameter node, even if the parameter is specified in multiple parameter sets in the syntax.</span></span>

1. <span data-ttu-id="5c0f1-121">Legen Sie für jeden Parameter Knoten die Attributwerte fest, die die Merkmale der einzelnen Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-121">For each Parameter node, set the attribute values that define the characteristics of each parameter.</span></span> <span data-ttu-id="5c0f1-122">Diese Attribute umfassen Folgendes: required, Globin, pipelineinput und Position.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-122">These attributes include the following: required, globbing, pipelineinput, and position.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named" ></command:parameter>
    </command:Parameters>
    ```

1. <span data-ttu-id="5c0f1-123">Fügen Sie für jeden Parameter Knoten den Namen des Parameters hinzu.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-123">For each Parameter node, add the name of the parameter.</span></span> <span data-ttu-id="5c0f1-124">Im folgenden finden Sie ein Beispiel für den Parameternamen, der dem Parameter Knoten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-124">Here is an example of the parameter name added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

1. <span data-ttu-id="5c0f1-125">Fügen Sie für jeden **Parameter** Knoten die Beschreibung des Parameters hinzu.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-125">For each **Parameter** node, add the description of the parameter.</span></span> <span data-ttu-id="5c0f1-126">Im folgenden finden Sie ein Beispiel für die Parameter Beschreibung, die dem **Parameter** -Knoten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-126">Here is an example of the parameter description added to the **Parameter** node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
      </command:parameter>
    </command:parameters>
    ```

1. <span data-ttu-id="5c0f1-127">Fügen Sie für jeden **Parameter** Knoten den .NET-Typ des Parameters hinzu.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-127">For each **Parameter** node, add the .NET type of the parameter.</span></span> <span data-ttu-id="5c0f1-128">Der Parametertyp wird zusammen mit dem Parameternamen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-128">The parameter type is displayed along with the parameter name.</span></span>

   <span data-ttu-id="5c0f1-129">Im folgenden finden Sie ein Beispiel für den .net-Parametertyp, der dem **Parameter** Knoten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-129">Here is an example of the parameter .NET type added to the **Parameter** node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
      </command:parameter>
    </command:parameters>
    ```

1. <span data-ttu-id="5c0f1-130">Fügen Sie für jeden **Parameter** Knoten den Standardwert des Parameters hinzu.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-130">For each **Parameter** node, add the default value of the parameter.</span></span> <span data-ttu-id="5c0f1-131">Der folgende Satz wird der Parameter Beschreibung hinzugefügt, wenn der Inhalt angezeigt wird: " **DefaultValue** " ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-131">The following sentence is added to the parameter description when the content is displayed: **DefaultValue** is the default.</span></span>

   <span data-ttu-id="5c0f1-132">Im folgenden finden Sie ein Beispiel für den Standardwert des Parameters, der dem **Parameter** Knoten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-132">Here is an example of the parameter default value is added to the **Parameter** node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
        <dev:defaultvalue> Add default value...</dev:defaultvalue>
      </command:parameter>
    </command:parameters>
    ```

1. <span data-ttu-id="5c0f1-133">Fügen Sie für jeden Parameter mit mehreren Werten den Knoten mögliche Werte hinzu.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-133">For each Parameter that has multiple values, add a possible values node.</span></span>

   <span data-ttu-id="5c0f1-134">Im folgenden finden Sie ein Beispiel für den eines möglichen Values-Knotens, der zwei mögliche Werte für den Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-134">Here is an example of the of a possible values node that defines two possible values for the parameter</span></span>

    ```xml
    <dev:possiblevalues>
      <dev:possiblevalue>
        <dev:value>Unknown</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possiblevalue>
      <dev:possiblevalue>
        <dev:value>String</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possibleValue>
    </dev:possiblevalues>
    ```

<span data-ttu-id="5c0f1-135">Beachten Sie beim Hinzufügen von Parametern die folgenden Punkte.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-135">Here are some things to remember when adding parameters.</span></span>

- <span data-ttu-id="5c0f1-136">Die Attribute des-Parameters werden nicht in allen Ansichten des Hilfe Themas für das Cmdlet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-136">The attributes of the parameter are not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="5c0f1-137">Sie werden jedoch in einer Tabelle angezeigt, die der Parameter Beschreibung folgt, wenn der Benutzer die **vollständige** ( `Get-Help <cmdletname> -full` ) oder die **Parameter** `Get-Help <cmdletname> -parameter` Ansicht () des Themas anfordert.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-137">However, they are displayed in a table following the parameter description when the user asks for the **Full** (`Get-Help <cmdletname> -full`) or **Parameter** (`Get-Help <cmdletname> -parameter`) view of the topic.</span></span>

- <span data-ttu-id="5c0f1-138">Die Parameter Beschreibung ist einer der wichtigsten Teile eines Cmdlet-Hilfe Themas.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-138">The parameter description is one of the most important parts of a cmdlet Help topic.</span></span> <span data-ttu-id="5c0f1-139">Die Beschreibung sollte kurz und gründlich sein.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-139">The description should be brief, as well as thorough.</span></span> <span data-ttu-id="5c0f1-140">Beachten Sie außerdem, dass Sie, wenn die Parameter Beschreibung zu lang wird, z. b. Wenn zwei Parameter miteinander interagieren, weitere Inhalte im Abschnitt "Hinweise" des Cmdlet-Hilfe Themas hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-140">Also, remember that if the parameter description becomes too long, such as when two parameters interact with each other, you can add more content in the NOTES section of the cmdlet Help topic.</span></span>

  <span data-ttu-id="5c0f1-141">Die Parameter Beschreibung bietet zwei Arten von Informationen.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-141">The parameter description provides two types of information.</span></span>

- <span data-ttu-id="5c0f1-142">Was das Cmdlet tut, wenn der-Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-142">What the cmdlet does when the parameter is used.</span></span>

- <span data-ttu-id="5c0f1-143">Der zulässige Wert für den-Parameter.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-143">What a legal value is for the parameter.</span></span>

- <span data-ttu-id="5c0f1-144">Da die Parameterwerte als .NET-Objekte ausgedrückt werden, benötigen die Benutzer mehr Informationen zu diesen Werten als in einer herkömmlichen Befehlszeilen Hilfe.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-144">Because the parameter values are expressed as .NET objects, users need more information about these values than they would in a traditional command-line Help.</span></span> <span data-ttu-id="5c0f1-145">Weisen Sie den Benutzer an, welche Art von Daten der Parameter akzeptieren soll, und fügen Sie Beispiele ein.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-145">Tell the user what type of data the parameter is designed to accept, and include examples.</span></span>

<span data-ttu-id="5c0f1-146">Der Standardwert des-Parameters ist der Wert, der verwendet wird, wenn der-Parameter nicht in der Befehlszeile angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-146">The default value of the parameter is the value that is used if the parameter is not specified on the command line.</span></span> <span data-ttu-id="5c0f1-147">Beachten Sie, dass der Standardwert optional ist und für einige Parameter, wie z. b. erforderliche Parameter, nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-147">Note that the default value is optional, and is not needed for some parameters, such as required parameters.</span></span> <span data-ttu-id="5c0f1-148">Sie sollten jedoch einen Standardwert für die meisten optionalen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-148">However, you should specify a default value for most optional parameters.</span></span>

<span data-ttu-id="5c0f1-149">Der Standardwert unterstützt den Benutzer dabei, die Auswirkungen der Verwendung des-Parameters zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-149">The default value helps the user to understand the effect of not using the parameter.</span></span> <span data-ttu-id="5c0f1-150">Beschreiben Sie den Standardwert sehr spezifisch, z. b. das "aktuelle Verzeichnis" oder "PowerShell-Installationsverzeichnis ( `$PSHOME` )", um einen optionalen Pfad zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-150">Describe the default value very specifically, such as the "Current directory" or the "PowerShell installation directory (`$PSHOME`)" for an optional path.</span></span> <span data-ttu-id="5c0f1-151">Sie können auch einen Satz schreiben, der den Standard beschreibt, z. b. den folgenden Satz, der für den **passthru** -Parameter verwendet wird: "Wenn passthru nicht angegeben ist, übergibt das Cmdlet Objekte nicht in der Pipeline."</span><span class="sxs-lookup"><span data-stu-id="5c0f1-151">You can also write a sentence that describes the default, such as the following sentence used for the **PassThru** parameter: "If PassThru is not specified, the cmdlet does not pass objects down the pipeline."</span></span> <span data-ttu-id="5c0f1-152">Da der Wert im Gegensatz zum **Standardwert** für den Feldnamen angezeigt wird, müssen Sie den Begriff "Standardwert" nicht in den Eintrag einschließen.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-152">Also, because the value is displayed opposite the field name **Default value**, you do not need to include the term "default value" in the entry.</span></span>

<span data-ttu-id="5c0f1-153">Der Standardwert des-Parameters wird nicht in allen Ansichten des Hilfe Themas für das Cmdlet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-153">The default value of the parameter is not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="5c0f1-154">Sie wird jedoch in einer Tabelle (zusammen mit den Parameter Attributen) nach der Parameter Beschreibung angezeigt, wenn der Benutzer die **vollständige** ( `Get-Help <cmdletname> -full` ) oder die **Parameter** `Get-Help
<cmdletname> -parameter` Ansicht () des Themas anfordert.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-154">However, it is displayed in a table (along with the parameter attributes) following the parameter description when the user asks for the **Full** (`Get-Help <cmdletname> -full`) or **Parameter** (`Get-Help
<cmdletname> -parameter`) view of the topic.</span></span>

<span data-ttu-id="5c0f1-155">Der folgende XML-Code zeigt ein dem `<dev:defaultValue>` Knoten hinzugefügtes paar von Tags `<command:parameter>` .</span><span class="sxs-lookup"><span data-stu-id="5c0f1-155">The following XML shows a pair of `<dev:defaultValue>` tags added to the `<command:parameter>` node.</span></span>
<span data-ttu-id="5c0f1-156">Beachten Sie, dass der Standardwert direkt hinter das `</command:parameterValue>` Endtag (wenn der Parameterwert angegeben ist) oder das `</maml:description>` Endtag der Parameter Beschreibung folgt.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-156">Notice that the default value follows immediately after the closing `</command:parameterValue>` tag (when the parameter value is specified) or the closing `</maml:description>` tag of the parameter description.</span></span> <span data-ttu-id="5c0f1-157">name.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-157">name.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
  </command:parameter>
</command:parameters>
```

<span data-ttu-id="5c0f1-158">Werte für Enumerationstypen hinzufügen</span><span class="sxs-lookup"><span data-stu-id="5c0f1-158">Add Values for Enumerated Types</span></span>

<span data-ttu-id="5c0f1-159">Wenn der Parameter mehrere Werte oder Werte eines enumerierten Typs aufweist, können Sie einen optionalen \<dev:possibleValues> Knoten verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-159">If the parameter has multiple values or values of an enumerated type, you can use an optional \<dev:possibleValues> node.</span></span> <span data-ttu-id="5c0f1-160">Mit diesem Knoten können Sie einen Namen und eine Beschreibung für mehrere Werte angeben.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-160">This node allows you to specify a name and description for multiple values.</span></span>

<span data-ttu-id="5c0f1-161">Beachten Sie, dass die Beschreibungen der aufgelisteten Werte nicht in einer der vom Cmdlet angezeigten Standard Hilfe Ansichten angezeigt werden `Get-Help` , aber andere Help Viewer diesen Inhalt möglicherweise in ihren Ansichten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-161">Be aware that the descriptions of the enumerated values do not appear in any of the default Help views displayed by the `Get-Help` cmdlet, but other Help viewers may display this content in their views.</span></span>

<span data-ttu-id="5c0f1-162">Der folgende XML-Code zeigt einen `<dev:possibleValues>` Knoten mit zwei angegebenen Werten.</span><span class="sxs-lookup"><span data-stu-id="5c0f1-162">The following XML shows a `<dev:possibleValues>` node with two values specified.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
    <dev:possibleValues>
      <dev:possibleValue>
        <dev:value> Value 1 </dev:value>
        <maml:description>
          <maml:para> Description 1 </maml:para>
        </maml:description>
      <dev:possibleValue>
      <dev:possibleValue>
        <dev:value> Value 2 </dev:value>
        <maml:description>
          <maml:para> Description 2 </maml:para>
        </maml:description>
      <dev:possibleValue>
    </dev:possibleValues>
  </command:parameter>
</command:parameters>
```
