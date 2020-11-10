---
description: Bietet eine kurze Einführung in die PowerShell DSC-Funktion (DSC).
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_desiredstateconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_DesiredStateConfiguration
ms.openlocfilehash: 5d088934ffc953ad19be401bce72f6287f0fde07
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387021"
---
# <a name="about_desiredstateconfiguration"></a><span data-ttu-id="601b3-104">about_DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="601b3-104">about_DesiredStateConfiguration</span></span>

## <a name="short-description"></a><span data-ttu-id="601b3-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="601b3-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="601b3-106">Bietet eine kurze Einführung in die PowerShell DSC-Funktion (DSC).</span><span class="sxs-lookup"><span data-stu-id="601b3-106">Provides a brief introduction to the PowerShell Desired State Configuration (DSC) feature.</span></span>

## <a name="long-description"></a><span data-ttu-id="601b3-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="601b3-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="601b3-108">DSC ist eine Verwaltungsplattform in PowerShell, die die Bereitstellung und Verwaltung von Konfigurationsdaten für Software Dienste und die Verwaltung der Umgebung ermöglicht, in der diese Dienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="601b3-108">DSC is a management platform in PowerShell that enables deploying and managing configuration data for software services, and managing the environment in which these services run.</span></span>

<span data-ttu-id="601b3-109">DSC stellt eine Reihe von PowerShell-Spracherweiterungen, neue Cmdlets und Ressourcen bereit, mit denen Sie deklarativ angeben können, wie der Zustand ihrer Softwareumgebung konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="601b3-109">DSC provides a set of PowerShell language extensions, new cmdlets, and resources that you can use to declaratively specify how you want the state of your software environment to be configured.</span></span> <span data-ttu-id="601b3-110">DSC bietet außerdem eine Möglichkeit zum Warten und Verwalten vorhandener Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="601b3-110">It also provides a means to maintain and manage existing configurations.</span></span>

<span data-ttu-id="601b3-111">DSC wird in PowerShell 4,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="601b3-111">DSC is introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="601b3-112">Ausführliche Informationen zu DSC finden Sie unter [PowerShell](/powershell/scripting/dsc/overview/overview)DSC (DSC).</span><span class="sxs-lookup"><span data-stu-id="601b3-112">For detailed information about DSC, see [PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/overview).</span></span>

## <a name="developing-dsc-resources-with-classes"></a><span data-ttu-id="601b3-113">Entwickeln von DSC-Ressourcen mit Klassen</span><span class="sxs-lookup"><span data-stu-id="601b3-113">DEVELOPING DSC RESOURCES WITH CLASSES</span></span>

<span data-ttu-id="601b3-114">Ab PowerShell 5,0 können Sie DSC-Ressourcen mithilfe von Klassen entwickeln.</span><span class="sxs-lookup"><span data-stu-id="601b3-114">Starting in PowerShell 5.0, you can develop DSC resources by using classes.</span></span>
<span data-ttu-id="601b3-115">Weitere Informationen finden Sie unter [about_Classes](about_Classes.md)und [Schreiben einer benutzerdefinierten DSC-Ressource mit PowerShell-Klassen](/powershell/scripting/dsc/resources/authoringresourceclass).</span><span class="sxs-lookup"><span data-stu-id="601b3-115">For more information, see [about_Classes](about_Classes.md), and [Writing a custom DSC resource with PowerShell classes](/powershell/scripting/dsc/resources/authoringresourceclass).</span></span>

## <a name="using-dsc"></a><span data-ttu-id="601b3-116">Verwenden von DSC</span><span class="sxs-lookup"><span data-stu-id="601b3-116">USING DSC</span></span>

<span data-ttu-id="601b3-117">Um DSC zum Konfigurieren Ihrer Umgebung zu verwenden, definieren Sie zunächst einen PowerShell-Skriptblock mithilfe des Schlüssel Worts "Configuration", gefolgt von einem Bezeichner, auf den wiederum das Paar der geschweiften Klammern folgt, die den Block begrenzen.</span><span class="sxs-lookup"><span data-stu-id="601b3-117">To use DSC to configure your environment, first define a PowerShell script block using the Configuration keyword, followed by an identifier, which is in turn followed by the pair of curly braces delimiting the block.</span></span> <span data-ttu-id="601b3-118">Innerhalb des Konfigurations Blocks können Sie Knoten Blöcke definieren, die den gewünschten Konfigurations Zustand für jeden Knoten (Computer) in der Umgebung angeben.</span><span class="sxs-lookup"><span data-stu-id="601b3-118">Inside the configuration block you can define node blocks that specify the desired configuration state for each node (computer) in the environment.</span></span> <span data-ttu-id="601b3-119">Ein Node-Block beginnt mit dem Node-Schlüsselwort, gefolgt vom Namen des Ziel Computers, bei dem es sich um eine Variable handeln kann.</span><span class="sxs-lookup"><span data-stu-id="601b3-119">A node block starts with the Node keyword, followed by the name of the target computer, which can be a variable.</span></span> <span data-ttu-id="601b3-120">Wechseln Sie nach dem Computernamen zu den geschweiften Klammern, die den Knoten Block begrenzen.</span><span class="sxs-lookup"><span data-stu-id="601b3-120">After the computer name, come the curly braces that delimit the node block.</span></span> <span data-ttu-id="601b3-121">Innerhalb des Knoten Blocks können Sie Ressourcenblöcke definieren, um bestimmte Ressourcen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="601b3-121">Inside the node block, you can define resource blocks to configure specific resources.</span></span> <span data-ttu-id="601b3-122">Ein Ressourcenblock beginnt mit dem Typnamen der Ressource, gefolgt von dem Bezeichner, den Sie für diesen Block angeben möchten, gefolgt von den geschweiften Klammern, die den Block begrenzen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="601b3-122">A resource block starts with the type name of the resource, followed by the identifier you want to specify for that block, followed by the curly braces that delimit the block, as shown in the following example.</span></span>

```powershell
Configuration MyWebConfig {
    # Parameters are optional
    param ($MachineName, $WebsiteFilePath)
    # A Configuration block can have one or more Node blocks
    Node $MachineName
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            # To ensure that the role is not installed, set Ensure to "Absent"
            Ensure = "Present"
            Name = "Web-Server" # Use the Name property from Get-WindowsFeature
        }

        # You can use the File resource to create files and folders
        # "WebDirectory" is the name you want to use to refer to this instance
        File WebDirectory
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath
            DestinationPath = "C:\inetpub\wwwroot"

            # Ensure that the IIS block is successfully run first before
            # configuring this resource
            DependsOn = "[WindowsFeature]IIS"  # Use for dependencies
        }
    }
}
```

<span data-ttu-id="601b3-123">Um eine Konfiguration zu erstellen, rufen Sie den Konfigurations Block auf dieselbe Weise auf wie Sie eine PowerShell-Funktion aufrufen, und übergeben Sie dabei alle erwarteten Parameter, die Sie möglicherweise definiert haben (zwei im obigen Beispiel).</span><span class="sxs-lookup"><span data-stu-id="601b3-123">To create a configuration, invoke the Configuration block the same way you would invoke a PowerShell function, passing in any expected parameters you may have defined (two in the example above).</span></span> <span data-ttu-id="601b3-124">In diesem Fall gilt beispielsweise Folgendes:</span><span class="sxs-lookup"><span data-stu-id="601b3-124">For example, in this case:</span></span>

```powershell
MyWebConfig -MachineName "TestMachine" -WebsiteFilePath `
  "\\filesrv\WebFiles" -OutputPath "C:\Windows\system32\temp"
# OutputPath is optional
```

<span data-ttu-id="601b3-125">Dadurch wird eine MOF-Datei pro Knoten an dem von Ihnen angegebenen Pfad generiert.</span><span class="sxs-lookup"><span data-stu-id="601b3-125">This generates a MOF file per node at the path you specify.</span></span> <span data-ttu-id="601b3-126">Diese MOF-Dateien geben die gewünschte Konfiguration für jeden Knoten an.</span><span class="sxs-lookup"><span data-stu-id="601b3-126">These MOF files specify the desired configuration for each node.</span></span> <span data-ttu-id="601b3-127">Verwenden Sie als nächstes das folgende Cmdlet, um die MOF-Konfigurationsdateien zu analysieren, die einzelnen Knoten mit der entsprechenden Konfiguration zu übertragen und diese Konfigurationen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="601b3-127">Next, use the following cmdlet to parse the configuration MOF files, send each node its corresponding configuration, and enact those configurations.</span></span> <span data-ttu-id="601b3-128">Beachten Sie, dass Sie keine separate MOF-Datei für klassenbasierte DSC-Ressourcen erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="601b3-128">Note that you do not need to create a separate MOF file for class-based DSC resources.</span></span>

```powershell
Start-DscConfiguration -Verbose -Wait -Path "C:\Windows\system32\temp"
```

## <a name="using-dsc-to-maintain-configuration-state"></a><span data-ttu-id="601b3-129">Verwalten des Konfigurations Status mithilfe von DSC</span><span class="sxs-lookup"><span data-stu-id="601b3-129">USING DSC TO MAINTAIN CONFIGURATION STATE</span></span>

<span data-ttu-id="601b3-130">Bei DSC ist die Konfiguration idempotent.</span><span class="sxs-lookup"><span data-stu-id="601b3-130">With DSC, configuration is idempotent.</span></span> <span data-ttu-id="601b3-131">Dies bedeutet Folgendes: Wenn Sie DSC verwenden, um dieselbe Konfiguration mehrmals durchzusetzen, ist der resultierende Konfigurations Status immer identisch.</span><span class="sxs-lookup"><span data-stu-id="601b3-131">This means that if you use DSC to enact the same configuration more than once, the resulting configuration state will always be the same.</span></span> <span data-ttu-id="601b3-132">Wenn Sie davon ausgehen, dass ein Knoten in Ihrer Umgebung möglicherweise vom gewünschten Zustand der Konfiguration abweicht, können Sie dieselbe DSC-Konfiguration erneut ausführen, um Sie wieder in den gewünschten Zustand zu bringen.</span><span class="sxs-lookup"><span data-stu-id="601b3-132">Because of this, if you suspect that any nodes in your environment may have drifted from the desired state of configuration, you can enact the same DSC configuration again to bring them back to the desired state.</span></span> <span data-ttu-id="601b3-133">Sie müssen das Konfigurationsskript nicht so ändern, dass nur die Ressourcen adressiert werden, deren Zustand vom gewünschten Zustand abweicht.</span><span class="sxs-lookup"><span data-stu-id="601b3-133">You do not need to modify the configuration script to address only those resources whose state has drifted from the desired state.</span></span>

<span data-ttu-id="601b3-134">Im folgenden Beispiel wird gezeigt, wie Sie überprüfen können, ob der tatsächliche Status der Konfiguration auf einem bestimmten Knoten von der letzten auf dem Knoten ersetzten DSC-Konfiguration abweicht.</span><span class="sxs-lookup"><span data-stu-id="601b3-134">The following example shows how you can verify whether the actual state of configuration on a given node has drifted from the last DSC configuration enacted on the node.</span></span> <span data-ttu-id="601b3-135">In diesem Beispiel überprüfen wir die Konfiguration des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="601b3-135">In this example we are checking the configuration of the local computer.</span></span>

```powershell
$session = New-CimSession -ComputerName "localhost"
Test-DscConfiguration -CimSession $session
```

## <a name="built-in-dsc-resources"></a><span data-ttu-id="601b3-136">integrierte DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="601b3-136">BUILT-IN DSC RESOURCES</span></span>

<span data-ttu-id="601b3-137">Sie können die folgenden integrierten Ressourcen in ihren Konfigurations Skripts verwenden:</span><span class="sxs-lookup"><span data-stu-id="601b3-137">You can use the following built-in resources in your configuration scripts:</span></span>

|<span data-ttu-id="601b3-138">Name</span><span class="sxs-lookup"><span data-stu-id="601b3-138">Name</span></span>                  |<span data-ttu-id="601b3-139">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="601b3-139">Properties</span></span>                                         |
|----------------------|---------------------------------------------------|
|<span data-ttu-id="601b3-140">Datei</span><span class="sxs-lookup"><span data-stu-id="601b3-140">File</span></span>                  |<span data-ttu-id="601b3-141">{DestinationPath, Attribute, Checksum, Content...}</span><span class="sxs-lookup"><span data-stu-id="601b3-141">{DestinationPath, Attributes, Checksum, Content...}</span></span>|
|<span data-ttu-id="601b3-142">Archivieren</span><span class="sxs-lookup"><span data-stu-id="601b3-142">Archive</span></span>               |<span data-ttu-id="601b3-143">{Destination, Path, Prüfsumme, Credential...}</span><span class="sxs-lookup"><span data-stu-id="601b3-143">{Destination, Path, Checksum, Credential...}</span></span>       |
|<span data-ttu-id="601b3-144">Umgebung</span><span class="sxs-lookup"><span data-stu-id="601b3-144">Environment</span></span>           |<span data-ttu-id="601b3-145">{Name, DependsOn, sicher, Pfad...}</span><span class="sxs-lookup"><span data-stu-id="601b3-145">{Name, DependsOn, Ensure, Path...}</span></span>                 |
|<span data-ttu-id="601b3-146">Group</span><span class="sxs-lookup"><span data-stu-id="601b3-146">Group</span></span>                 |<span data-ttu-id="601b3-147">{GroupName, Credential, DependsOn, Description...}</span><span class="sxs-lookup"><span data-stu-id="601b3-147">{GroupName, Credential, DependsOn, Description...}</span></span> |
|<span data-ttu-id="601b3-148">Log</span><span class="sxs-lookup"><span data-stu-id="601b3-148">Log</span></span>                   |<span data-ttu-id="601b3-149">{Message, DependsOn, psdscrunascredential}</span><span class="sxs-lookup"><span data-stu-id="601b3-149">{Message, DependsOn, PsDscRunAsCredential}</span></span>         |
|<span data-ttu-id="601b3-150">Paket</span><span class="sxs-lookup"><span data-stu-id="601b3-150">Package</span></span>               |<span data-ttu-id="601b3-151">{Name, Path, ProductID, Arguments...}</span><span class="sxs-lookup"><span data-stu-id="601b3-151">{Name, Path, ProductId, Arguments...}</span></span>              |
|<span data-ttu-id="601b3-152">Registrierung</span><span class="sxs-lookup"><span data-stu-id="601b3-152">Registry</span></span>              |<span data-ttu-id="601b3-153">{Key, valueName, DependsOn, sicher...}</span><span class="sxs-lookup"><span data-stu-id="601b3-153">{Key, ValueName, DependsOn, Ensure...}</span></span>             |
|<span data-ttu-id="601b3-154">Skript</span><span class="sxs-lookup"><span data-stu-id="601b3-154">Script</span></span>                |<span data-ttu-id="601b3-155">{GetScript, SetScript, testScript, Credential...}</span><span class="sxs-lookup"><span data-stu-id="601b3-155">{GetScript, SetScript, TestScript, Credential...}</span></span>  |
|<span data-ttu-id="601b3-156">Dienst</span><span class="sxs-lookup"><span data-stu-id="601b3-156">Service</span></span>               |<span data-ttu-id="601b3-157">{Name, builtinaccount, Credential, Abhängigkeiten...}</span><span class="sxs-lookup"><span data-stu-id="601b3-157">{Name, BuiltInAccount, Credential, Dependencies...}</span></span>|
|<span data-ttu-id="601b3-158">Benutzer</span><span class="sxs-lookup"><span data-stu-id="601b3-158">User</span></span>                  |<span data-ttu-id="601b3-159">{UserName, DependsOn, Description, deaktiviert...}</span><span class="sxs-lookup"><span data-stu-id="601b3-159">{UserName, DependsOn, Description, Disabled...}</span></span>    |
|<span data-ttu-id="601b3-160">WaitForAll</span><span class="sxs-lookup"><span data-stu-id="601b3-160">WaitForAll</span></span>            |<span data-ttu-id="601b3-161">{Nodename, resourceName, DependsOn, psdscrunasc...}</span><span class="sxs-lookup"><span data-stu-id="601b3-161">{NodeName, ResourceName, DependsOn, PsDscRunAsC...}</span></span>|
|<span data-ttu-id="601b3-162">WaitForAny</span><span class="sxs-lookup"><span data-stu-id="601b3-162">WaitForAny</span></span>            |<span data-ttu-id="601b3-163">{Nodename, resourceName, DependsOn, psdscrunasc...}</span><span class="sxs-lookup"><span data-stu-id="601b3-163">{NodeName, ResourceName, DependsOn, PsDscRunAsC...}</span></span>|
|<span data-ttu-id="601b3-164">WaitForSome</span><span class="sxs-lookup"><span data-stu-id="601b3-164">WaitForSome</span></span>           |<span data-ttu-id="601b3-165">{Nobecount, nodename, resourceName, DependsOn...}</span><span class="sxs-lookup"><span data-stu-id="601b3-165">{NodeCount, NodeName, ResourceName, DependsOn...}</span></span>  |
|<span data-ttu-id="601b3-166">WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="601b3-166">WindowsFeature</span></span>        |<span data-ttu-id="601b3-167">{Name, Credential, DependsOn, sicher...}</span><span class="sxs-lookup"><span data-stu-id="601b3-167">{Name, Credential, DependsOn, Ensure...}</span></span>           |
|<span data-ttu-id="601b3-168">WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="601b3-168">WindowsOptionalFeature</span></span>|<span data-ttu-id="601b3-169">{Name, DependsOn, sicher, LogLevel...}</span><span class="sxs-lookup"><span data-stu-id="601b3-169">{Name, DependsOn, Ensure, LogLevel...}</span></span>             |
|<span data-ttu-id="601b3-170">WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="601b3-170">WindowsProcess</span></span>        |<span data-ttu-id="601b3-171">{Arguments, Path, Credential, DependsOn...}</span><span class="sxs-lookup"><span data-stu-id="601b3-171">{Arguments, Path, Credential, DependsOn...}</span></span>        |

<span data-ttu-id="601b3-172">Führen Sie das-Cmdlet aus, um eine Liste der verfügbaren DSC-Ressourcen auf Ihrem System zu erhalten `Get-DscResource` .</span><span class="sxs-lookup"><span data-stu-id="601b3-172">To get a list of available DSC resources on your system, run the `Get-DscResource` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="601b3-173">In Versionen vor PowerShell 7.0 findet `Get-DscResource` keine klassenbasierten DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="601b3-173">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="601b3-174">Das Beispiel in diesem Thema veranschaulicht die Verwendung der Datei-und Windows Feature-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="601b3-174">The example in this topic demonstrates how to use the File and WindowsFeature resources.</span></span> <span data-ttu-id="601b3-175">Um alle Eigenschaften anzuzeigen, die Sie mit einer Ressource verwenden können, fügen Sie den Cursor in das Schlüsselwort "Resource" (z. b. "file") in Ihr Konfigurationsskript in PowerShell ISE ein, halten Sie <kbd>STRG</kbd> + <kbd>LEERTASTE</kbd> gedrückt.</span><span class="sxs-lookup"><span data-stu-id="601b3-175">To see all properties that you can use with a resource, insert the cursor in the resource keyword (for example, File) within your configuration script in PowerShell ISE, hold down <kbd>CTRL</kbd>+<kbd>SPACEBAR</kbd></span></span>

## <a name="find-more-resources"></a><span data-ttu-id="601b3-176">Weitere Ressourcen suchen</span><span class="sxs-lookup"><span data-stu-id="601b3-176">FIND MORE RESOURCES</span></span>

<span data-ttu-id="601b3-177">Sie können viele weitere verfügbare DSC-Ressourcen herunterladen, installieren und kennenlernen, die von der PowerShell und der DSC-Benutzer Community und von Microsoft erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="601b3-177">You can download, install, and learn about many other available DSC resources that have been created by the PowerShell and DSC user community, and by Microsoft.</span></span> <span data-ttu-id="601b3-178">Besuchen Sie die [PowerShell-Katalog](https://www.powershellgallery.com/) , um zu erfahren, welche DSC-Ressourcen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="601b3-178">Visit the [PowerShell Gallery](https://www.powershellgallery.com/) to browse and learn about available DSC resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="601b3-179">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="601b3-179">SEE ALSO</span></span>

[<span data-ttu-id="601b3-180">PowerShell-Konfiguration des gewünschten Zustands (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="601b3-180">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="601b3-181">Integrierte PowerShell DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="601b3-181">Built-In PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/resources)

[<span data-ttu-id="601b3-182">Erstellen von benutzerdefinierten PowerShell DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="601b3-182">Build Custom PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/authoringResource)
