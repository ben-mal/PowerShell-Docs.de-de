---
ms.date: 12/12/2018
keywords: DSC,PowerShell,Ressource,Katalog,Setup
title: Hinzufügen von Parametern zu einer Konfiguration
description: DSC-Konfigurationen können parametrisiert werden, sodass dynamischere Konfigurationen auf Grundlage der Benutzereingabe möglich sind.
ms.openlocfilehash: 72f3cf9efb5d99170e71992bed86a20a57132250
ms.sourcegitcommit: 62282bb9c36fea3b4290b9263c1cd8e9ac216e29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96470331"
---
# <a name="add-parameters-to-a-configuration"></a><span data-ttu-id="2ce2c-104">Hinzufügen von Parametern zu einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="2ce2c-104">Add Parameters to a Configuration</span></span>

<span data-ttu-id="2ce2c-105">Ebenso wie Funktionen können [Konfigurationen](configurations.md) parametrisiert werden können, sodass dynamischere Konfigurationen auf Grundlage der Benutzereingabe möglich sind.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-105">Like Functions, [Configurations](configurations.md) can be parameterized to allow more dynamic configurations based on user input.</span></span> <span data-ttu-id="2ce2c-106">Die Schritte ähneln den in [Funktionen mit Parametern](/powershell/module/microsoft.powershell.core/about/about_functions) beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-106">The steps are similar to those described in [Functions with Parameters](/powershell/module/microsoft.powershell.core/about/about_functions).</span></span>

<span data-ttu-id="2ce2c-107">Dieses Beispiel beginnt mit einer einfachen Konfiguration, die den „Spooler“-Dienst als „Wird ausgeführt“ konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-107">This example starts with a basic Configuration that configures the "Spooler" service to be "Running".</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}
```

## <a name="built-in-configuration-parameters"></a><span data-ttu-id="2ce2c-108">Integrierte Konfigurationsparameter</span><span class="sxs-lookup"><span data-stu-id="2ce2c-108">Built-in Configuration parameters</span></span>

<span data-ttu-id="2ce2c-109">Im Gegensatz zu einer Funktion fügt das [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute)-Attribut jedoch keine Funktionalität hinzu.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-109">Unlike a Function though, the [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) attribute adds no functionality.</span></span> <span data-ttu-id="2ce2c-110">Zusätzlich zu [allgemeinen Parametern](/powershell/module/microsoft.powershell.core/about/about_commonparameters) können Konfigurationen auch die folgenden integrierten Parameter verwenden, ohne dass Sie sie definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-110">In addition to [Common Parameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters), Configurations can also use the following built in parameters, without requiring you to define them.</span></span>

|        <span data-ttu-id="2ce2c-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ce2c-111">Parameter</span></span>        |                                         <span data-ttu-id="2ce2c-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2ce2c-112">Description</span></span>                                          |
| ----------------------- | -------------------------------------------------------------------------------------------- |
| `-InstanceName`         | <span data-ttu-id="2ce2c-113">Zur Definition [zusammengesetzter Konfigurationen](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="2ce2c-113">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>                             |
| `-DependsOn`            | <span data-ttu-id="2ce2c-114">Zur Definition [zusammengesetzter Konfigurationen](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="2ce2c-114">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>                             |
| `-PSDSCRunAsCredential` | <span data-ttu-id="2ce2c-115">Zur Definition [zusammengesetzter Konfigurationen](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="2ce2c-115">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>                             |
| `-ConfigurationData`    | <span data-ttu-id="2ce2c-116">Zur Übergabe strukturierter [Konfigurationsdaten](configData.md) für die Verwendung in der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-116">Used to pass in structured [Configuration Data](configData.md) for use in the Configuration.</span></span> |
| `-OutputPath`           | <span data-ttu-id="2ce2c-117">Zur Angabe, wo Ihre Datei „\<computername\>.mof“ kompiliert wird</span><span class="sxs-lookup"><span data-stu-id="2ce2c-117">Used to specify where your "\<computername\>.mof" file will be compiled</span></span>                      |

## <a name="adding-your-own-parameters-to-configurations"></a><span data-ttu-id="2ce2c-118">Hinzufügen Ihrer eigenen Parameter zu Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="2ce2c-118">Adding your own parameters to Configurations</span></span>

<span data-ttu-id="2ce2c-119">Neben den integrierten Parametern können Sie auch Ihre eigenen Parameter Ihren Konfigurationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-119">In addition to the built-in parameters, you can also add your own parameters to your Configurations.</span></span>
<span data-ttu-id="2ce2c-120">Der Parameterblock wird wie eine Funktion direkt in die Deklaration der Konfiguration eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-120">The parameter block goes directly inside the Configuration declaration, just like a Function.</span></span> <span data-ttu-id="2ce2c-121">Ein Konfigurationsparameterblock muss außerhalb von **Node**-Deklarationen und vor jeglichen *import*-Anweisungen platziert werden.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-121">A Configuration parameter block should be outside any **Node** declarations, and above any *import* statements.</span></span> <span data-ttu-id="2ce2c-122">Durch Hinzufügen von Parametern können Sie Ihre Konfigurationen robuster und dynamischer machen.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-122">By adding parameters, you can make your Configurations more robust and dynamic.</span></span>

```powershell
Configuration TestConfig
{
    param
    (

    )
```

### <a name="add-a-computername-parameter"></a><span data-ttu-id="2ce2c-123">Hinzufügen eines ComputerName-Parameters</span><span class="sxs-lookup"><span data-stu-id="2ce2c-123">Add a ComputerName parameter</span></span>

<span data-ttu-id="2ce2c-124">Als ersten Parameter könnten Sie einen `-Computername`-Parameter hinzufügen, sodass Sie dynamisch eine MOF-Datei für einen beliebigen `-Computername` kompilieren können, den Sie Ihrer Konfiguration übergeben.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-124">The first parameter you might add is a `-Computername` parameter so you can dynamically compile a ".mof" file for any `-Computername` you pass to your configuration.</span></span> <span data-ttu-id="2ce2c-125">Wie bei Funktionen können Sie auch einen Standardwert definieren für den Fall, dass der Benutzer keinen Wert für `-ComputerName` übergibt.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-125">Like Functions, you can also define a default value, in case the user does not pass in a value for `-ComputerName`</span></span>

```powershell
param
(
    [String]
    $ComputerName="localhost"
)
```

<span data-ttu-id="2ce2c-126">Anschließend können Sie in Ihrer Konfiguration Ihren `-ComputerName`-Parameter angeben, wenn Sie Ihren Node-Block definieren.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-126">Within your configuration, you can then specify your `-ComputerName` parameter when defining your Node block.</span></span>

```powershell
Node $ComputerName
{

}
```

### <a name="calling-your-configuration-with-parameters"></a><span data-ttu-id="2ce2c-127">Aufrufen Ihrer Konfiguration mit Parametern</span><span class="sxs-lookup"><span data-stu-id="2ce2c-127">Calling your Configuration with parameters</span></span>

<span data-ttu-id="2ce2c-128">Nachdem Sie Ihrer Konfiguration Parameter hinzugefügt haben, können Sie sie genau so wie ein Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-128">After you have added parameters to your Configuration, you can use them just like you would with a cmdlet.</span></span>

```powershell
TestConfig -ComputerName "server01"
```

### <a name="compiling-multiple-mof-files"></a><span data-ttu-id="2ce2c-129">Kompilieren mehrerer MOF-Dateien</span><span class="sxs-lookup"><span data-stu-id="2ce2c-129">Compiling multiple .mof files</span></span>

<span data-ttu-id="2ce2c-130">Der Node-Block kann auch eine durch Trennzeichen getrennte Liste von Computernamen annehmen und generiert für jeden eine MOF-Datei.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-130">The Node block can also accept a comma-separated list of computer names and will generate ".mof" files for each.</span></span> <span data-ttu-id="2ce2c-131">Sie können das folgende Beispiel ausführen, um MOF-Dateien für alle an den `-ComputerName`-Parameter übergebenen Computer zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-131">You can run the following example to generate ".mof" files for all of the computers passed to the `-ComputerName` parameter.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [String[]]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}

TestConfig -ComputerName "server01", "server02", "server03"
```

## <a name="advanced-parameters-in-configurations"></a><span data-ttu-id="2ce2c-132">Erweiterte Parameter in Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="2ce2c-132">Advanced parameters in Configurations</span></span>

<span data-ttu-id="2ce2c-133">Zusätzlich zu einem `-ComputerName`-Parameter können wir Parameter für den Dienstnamen und Zustand hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-133">In addition to a `-ComputerName` parameter, we can add parameters for the service name and state.</span></span>
<span data-ttu-id="2ce2c-134">Im folgenden Beispiel wird ein Parameterblock mit einem `-ServiceName`-Parameter hinzugefügt und verwendet, um den **Service**-Ressourcenblock dynamisch zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-134">The following example adds a parameter block with a `-ServiceName` parameter and uses it to dynamically define the **Service** resource block.</span></span> <span data-ttu-id="2ce2c-135">Es wird auch ein `-State`-Parameter hinzugefügt, um den **State** (Zustand) im **Service**-Ressourcenblock dynamisch zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-135">It also adds a `-State` parameter to dynamically define the **State** in the **Service** resource block.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ServiceName,

        [String]
        $State,

        [String]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="2ce2c-136">In fortgeschritteneren Szenarien könnte es sinnvoller sein, dynamische Daten in strukturierte [Konfigurationsdaten](configData.md) zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-136">In more advanced scenarios, it might make more sense to move your dynamic data into a structured [Configuration Data](configData.md).</span></span>

<span data-ttu-id="2ce2c-137">Die Beispielkonfiguration nimmt einen dynamischen `$ServiceName` an, aber wenn er nicht angegeben wird, tritt beim Kompilieren ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-137">The example Configuration now takes a dynamic `$ServiceName`, but if one is not specified, compiling results in an error.</span></span> <span data-ttu-id="2ce2c-138">Sie können einen Standardwert wie im folgenden Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-138">You could add a default value like this example.</span></span>

```powershell
[String]
$ServiceName="Spooler"
```

<span data-ttu-id="2ce2c-139">In diesem Fall ist es allerdings sinnvoller, vom Benutzer einfach die Eingabe eines Werts für den `$ServiceName`-Parameter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-139">In this instance though, it makes more sense to simply force the user to specify a value for the `$ServiceName` parameter.</span></span> <span data-ttu-id="2ce2c-140">Mit dem `parameter`-Attribut können Sie die Überprüfungs- und Pipelineunterstützung durch die Parameter Ihrer Konfiguration erweitern.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-140">The `parameter` attribute allows you to add further validation and pipeline support to your Configuration's parameters.</span></span>

<span data-ttu-id="2ce2c-141">Fügen Sie vor jeder Parameterdeklaration wie im folgenden Beispiel den `parameter`-Attributblock ein.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-141">Above any parameter declaration, add the `parameter` attribute block as in the example below.</span></span>

```powershell
[parameter()]
[String]
$ServiceName
```

<span data-ttu-id="2ce2c-142">Sie können für jedes `parameter`-Attribut Argumente angeben, um die Aspekte der definierten Parameter zu steuern.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-142">You can specify arguments to each `parameter` attribute, to control aspects of the defined parameter.</span></span> <span data-ttu-id="2ce2c-143">Im folgenden Beispiel wird `$ServiceName` zu einem **Mandatory**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-143">The following example makes the `$ServiceName` a **Mandatory** parameter.</span></span>

```powershell
[parameter(Mandatory)]
[String]
$ServiceName
```

<span data-ttu-id="2ce2c-144">Wir möchten verhindern, dass der Benutzer für den `$State`-Parameter außerhalb eines vordefinierten Satzes (z.B. „Running“, „Stopped“) liegende Werte angibt, und verwenden hierzu das `ValidationSet*`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-144">For the `$State` parameter, we would like to prevent the user from specifying values outside of a predefined set (like Running, Stopped) the `ValidationSet*`attribute would prevent the user from specifying values outside of a predefined set (like Running, Stopped).</span></span> <span data-ttu-id="2ce2c-145">Im folgenden Beispiel wird das `ValidationSet`-Attribut dem `$State`-Parameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-145">The following example adds the `ValidationSet` attribute to the `$State` parameter.</span></span> <span data-ttu-id="2ce2c-146">Da wir den `$State`-Parameter nicht zu einem **Mandatory**-Parameter machen möchten, müssen wir für ihn einen Standardwert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-146">Since we do not want to make the `$State` parameter **Mandatory**, we will need to add a default value for it.</span></span>

```powershell
[ValidateSet("Running", "Stopped")]
[String]
$State="Running"
```

> [!NOTE]
> <span data-ttu-id="2ce2c-147">Sie müssen kein `parameter`-Attribut angeben, wenn Sie ein `validation`-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-147">You do not need to specify a `parameter` attribute when using a `validation` attribute.</span></span>

<span data-ttu-id="2ce2c-148">Weitere Informationen über `parameter` und Validierungsattribute finden Sie unter [Informationen zu Parametern erweiterter Funktionen](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters).</span><span class="sxs-lookup"><span data-stu-id="2ce2c-148">You can read more about the `parameter` and validation attributes in [about_Functions_Advanced_Parameters](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters).</span></span>

## <a name="fully-parameterized-configuration"></a><span data-ttu-id="2ce2c-149">Vollständig parametrisierte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="2ce2c-149">Fully parameterized Configuration</span></span>

<span data-ttu-id="2ce2c-150">Wir verfügen jetzt über eine parametrisierte Konfiguration, die vom Benutzer die Eingabe von `-InstanceName` und `-ServiceName` erzwingt und den `-State`-Parameter überprüft.</span><span class="sxs-lookup"><span data-stu-id="2ce2c-150">We now have a parameterized Configuration that forces the user to specify an `-InstanceName`, `-ServiceName`, and validates the `-State` parameter.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [parameter(Mandatory)]
        [String]
        $ServiceName,

        [ValidateSet("Running","Stopped")]
        [String]
        $State="Running",

        [String]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="2ce2c-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ce2c-151">See also</span></span>

- [<span data-ttu-id="2ce2c-152">Schreiben von Hilfe für DSC-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="2ce2c-152">Write help for DSC configurations</span></span>](configHelp.md)
- [<span data-ttu-id="2ce2c-153">Bedingte Anweisungen und Schleifen in Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="2ce2c-153">Dynamic Configurations</span></span>](flow-control-in-configurations.md)
- [<span data-ttu-id="2ce2c-154">Verwenden von Konfigurationsdaten in DSC</span><span class="sxs-lookup"><span data-stu-id="2ce2c-154">Use Configuration Data in your Configurations</span></span>](configData.md)
- [<span data-ttu-id="2ce2c-155">Trennen von Konfiguration und Umgebungsdaten</span><span class="sxs-lookup"><span data-stu-id="2ce2c-155">Separate configuration and environment data</span></span>](separatingEnvData.md)
