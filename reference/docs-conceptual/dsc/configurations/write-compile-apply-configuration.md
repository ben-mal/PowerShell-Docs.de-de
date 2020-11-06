---
ms.date: 06/22/2020
keywords: dsc,powershell,configuration,service,setup
title: Schreiben, Kompilieren und Anwenden einer Konfiguration
description: Diese Übung führt Sie von Anfang bis Ende durch das Erstellen und Anwenden einer DSC-Konfiguration. Anhand des folgenden Beispiels erfahren Sie, wie Sie eine einfache Konfiguration schreiben und anwenden.
ms.openlocfilehash: f173fe0dc6cd73e2b49bb8c44a9ee1a53eab475f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645032"
---
# <a name="write-compile-and-apply-a-configuration"></a><span data-ttu-id="aec04-105">Schreiben, Kompilieren und Anwenden einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="aec04-105">Write, Compile, and Apply a Configuration</span></span>

> <span data-ttu-id="aec04-106">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="aec04-106">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="aec04-107">Diese Übung führt Sie von Anfang bis Ende durch das Erstellen und Anwenden einer Desired State Configuration (DSC)-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="aec04-107">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span> <span data-ttu-id="aec04-108">Anhand des folgenden Beispiels erfahren Sie, wie Sie eine einfache Konfiguration schreiben und anwenden.</span><span class="sxs-lookup"><span data-stu-id="aec04-108">In the following example, you will learn how to write and apply a very simple Configuration.</span></span> <span data-ttu-id="aec04-109">Mit der Konfiguration wird sichergestellt, dass eine „HelloWorld.txt“-Datei auf Ihrem lokalen Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="aec04-109">The Configuration will ensure a "HelloWorld.txt" file exists on your local machine.</span></span>
<span data-ttu-id="aec04-110">Wenn Sie die Datei löschen, erstellt DSC sie beim nächsten Update neu.</span><span class="sxs-lookup"><span data-stu-id="aec04-110">If you delete the file, DSC will recreate it the next time it updates.</span></span>

<span data-ttu-id="aec04-111">Eine Übersicht über DSC und die Funktionsweise finden Sie unter [Desired State Configuration Overview for Developers (Desired State Configuration (DSC): Übersicht für Entwickler)](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="aec04-111">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Developers](../overview/overview.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="aec04-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aec04-112">Requirements</span></span>

<span data-ttu-id="aec04-113">Sie benötigen einen Computer mit PowerShell 4.0 oder höher, um dieses Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="aec04-113">To run this example, you will need a computer running PowerShell 4.0 or later.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="aec04-114">Schreiben der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="aec04-114">Write the configuration</span></span>

<span data-ttu-id="aec04-115">Eine DSC-[Konfiguration](configurations.md) ist eine spezielle PowerShell-Funktion, die definiert, wie Sie einen oder mehrere Zielcomputer (Knoten) konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="aec04-115">A DSC [Configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (Nodes).</span></span>

<span data-ttu-id="aec04-116">Geben Sie Folgendes in die PowerShell ISE oder einen anderen PowerShell-Editor ein:</span><span class="sxs-lookup"><span data-stu-id="aec04-116">In the PowerShell ISE, or other PowerShell editor, type the following:</span></span>

```powershell
Configuration HelloWorld {

    # Import the module that contains the File resource.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets to compile MOF files for, when
    # this configuration is executed.
    Node 'localhost' {

        # The File resource can ensure the state of files, or copy them from a
        # source to a destination with persistent updates.
        File HelloWorld {
            DestinationPath = "C:\Temp\HelloWorld.txt"
            Ensure = "Present"
            Contents   = "Hello World from DSC!"
        }
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="aec04-117">In komplexeren Szenarien, in denen mehrere Module importiert werden müssen, damit Sie mit vielen DSC-Ressourcen in der gleichen Konfiguration arbeiten können, geben Sie jedes Modul mit `Import-DscResource` in einer separaten Zeile an.</span><span class="sxs-lookup"><span data-stu-id="aec04-117">In more advanced scenarios where multiple modules need to be imported so you can work with many DSC Resources in the same configuration, make sure to put each module in a separate line using `Import-DscResource`.</span></span> <span data-ttu-id="aec04-118">Dies lässt sich in der Quellcodeverwaltung leichter nachverfolgen und ist erforderlich, wenn Sie in Azure State Configuration mit DSC arbeiten.</span><span class="sxs-lookup"><span data-stu-id="aec04-118">This is easier to maintain in source control and required when working with DSC in Azure State Configuration.</span></span>
>
> ```powershell
>  Configuration HelloWorld {
>
>   # Import the module that contains the File resource.
>   Import-DscResource -ModuleName PsDesiredStateConfiguration
>   Import-DscResource -ModuleName xWebAdministration
>
> ```

<span data-ttu-id="aec04-119">Speichern Sie die Datei als „HelloWorld.ps1“.</span><span class="sxs-lookup"><span data-stu-id="aec04-119">Save the file as "HelloWorld.ps1".</span></span>

<span data-ttu-id="aec04-120">Das Definieren einer Konfiguration entspricht dem Definieren einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="aec04-120">Defining a Configuration is like defining a Function.</span></span> <span data-ttu-id="aec04-121">Der **Node** -Block gibt den zu konfigurierenden Zielknoten an, in diesem Fall `localhost`.</span><span class="sxs-lookup"><span data-stu-id="aec04-121">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="aec04-122">Die Konfiguration ruft eine [Ressource](../resources/resources.md) auf, die `File`-Ressource.</span><span class="sxs-lookup"><span data-stu-id="aec04-122">The configuration calls one [resources](../resources/resources.md), the `File` resource.</span></span> <span data-ttu-id="aec04-123">Ressourcen stellen sicher, dass sich der Zielknoten im durch die Konfiguration definierten Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="aec04-123">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="aec04-124">Kompilieren der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="aec04-124">Compile the configuration</span></span>

<span data-ttu-id="aec04-125">Damit eine DSC-Konfiguration auf einem Knoten angewendet werden kann, muss sie zunächst in eine MOF-Datei kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="aec04-125">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span> <span data-ttu-id="aec04-126">Durch Ausführen der Konfiguration wie eine Funktion wird vom `Node`-Block eine `.mof`-Datei für jeden Knoten definiert.</span><span class="sxs-lookup"><span data-stu-id="aec04-126">Running the configuration, like a function, will compile one `.mof` file for every Node defined by the `Node` block.</span></span> <span data-ttu-id="aec04-127">Sie müssen das Skript `HelloWorld.ps1` per _dot source_ im aktuellen Bereich aufrufen, um die Konfiguration auszuführen.</span><span class="sxs-lookup"><span data-stu-id="aec04-127">In order to run the configuration, you need to _dot source_ your `HelloWorld.ps1` script into the current scope.</span></span> <span data-ttu-id="aec04-128">Weitere Informationen hierzu finden Sie unter [about_Scripts (Informationen zu Skripts)](/powershell/module/microsoft.powershell.core/about/about_scripts#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="aec04-128">For more information, see [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts#script-scope-and-dot-sourcing).</span></span>

<!-- markdownlint-disable MD038 -->
<span data-ttu-id="aec04-129">Das Skript `HelloWorld.ps1` rufen Sie per _dot source_ auf, indem Sie den Pfad zum Speicherort nach dem `. ` (Punkt gefolgt von einem Leerzeichen) eingeben.</span><span class="sxs-lookup"><span data-stu-id="aec04-129">_Dot source_ your `HelloWorld.ps1` script by typing in the path where you stored it, after the `. ` (dot, space).</span></span> <span data-ttu-id="aec04-130">Anschließend können Sie Ihre Konfiguration ausführen, indem Sie sie wie eine Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aec04-130">You may then, run your configuration by calling it like a function.</span></span> <span data-ttu-id="aec04-131">Sie könnten auch die Konfigurationsfunktion unten im Skript aufrufen, sodass „dot-source“ nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="aec04-131">You could also invoke the configuration function at the bottom of the script so that you don't need to dot-source.</span></span>
<!-- markdownlint-enable MD038 -->

```powershell
. C:\Scripts\HelloWorld.ps1
HelloWorld
```

<span data-ttu-id="aec04-132">Die folgende Ausgabe wird generiert:</span><span class="sxs-lookup"><span data-stu-id="aec04-132">This generates the following output:</span></span>

```Output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a><span data-ttu-id="aec04-133">Anwenden der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="aec04-133">Apply the configuration</span></span>

<span data-ttu-id="aec04-134">Nun, da Sie die kompilierte MOF-Dateien haben, können Sie die Konfiguration auf den Zielknoten (in diesem Fall der lokale Computer) anwenden, indem Sie das Cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aec04-134">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="aec04-135">Das Cmdlet `Start-DscConfiguration` fordert den [lokalen Konfigurations-Manager](../managing-nodes/metaConfig.md) (die DSC-Engine) dazu auf, die Konfiguration anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="aec04-135">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), the engine of DSC, to apply the configuration.</span></span> <span data-ttu-id="aec04-136">Der LCM übernimmt das Aufrufen der DSC-Ressourcen, um die Konfiguration anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="aec04-136">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="aec04-137">Verwenden Sie den folgenden Code, um das Cmdlet `Start-DSCConfiguration` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="aec04-137">Use the code below to execute the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="aec04-138">Geben Sie für den Parameter **Path** den Verzeichnispfad an, unter dem `localhost.mof` gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="aec04-138">Specify the directory path where your `localhost.mof` is stored to the **Path** parameter.</span></span> <span data-ttu-id="aec04-139">Das Cmdlet `Start-DSCConfiguration` durchsucht das angegebene Verzeichnis auf Dateien des Typs `<computername>.mof`.</span><span class="sxs-lookup"><span data-stu-id="aec04-139">The `Start-DSCConfiguration` cmdlet looks through the directory specified for any `<computername>.mof` files.</span></span> <span data-ttu-id="aec04-140">Das Cmdlet `Start-DSCConfiguration` versucht, alle gefundenen `.mof`-Dateien auf den vom Dateinamen angegeben `computername` („localhost“, „server01“, „dc-02“ usw.) anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="aec04-140">The `Start-DSCConfiguration` cmdlet attempts to apply each `.mof` file it finds to the `computername` specified by the filename ("localhost", "server01", "dc-02", etc.).</span></span>

> [!NOTE]
> <span data-ttu-id="aec04-141">Wenn der Parameter `-Wait` nicht festgelegt wird, erstellt `Start-DSCConfiguration` einen Hintergrundauftrag zum Ausführen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="aec04-141">If the `-Wait` parameter is not specified, `Start-DSCConfiguration` creates a background job to perform the operation.</span></span> <span data-ttu-id="aec04-142">Durch Festlegen des `-Verbose`-Parameters können Sie die **ausführliche** Ausgabe des Vorgangs anzeigen.</span><span class="sxs-lookup"><span data-stu-id="aec04-142">Specifying the `-Verbose` parameter allows you to watch the **Verbose** output of the operation.</span></span> <span data-ttu-id="aec04-143">`-Wait` und `-Verbose` sind optionale Parameter.</span><span class="sxs-lookup"><span data-stu-id="aec04-143">`-Wait`, and `-Verbose` are both optional parameters.</span></span>

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a><span data-ttu-id="aec04-144">Testen der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="aec04-144">Test the configuration</span></span>

<span data-ttu-id="aec04-145">Sobald das Cmdlet `Start-DSCConfiguration` abgeschlossen ist, sollte Ihnen eine Datei `HelloWorld.txt` am von Ihnen festgelegten Speicherort angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="aec04-145">Once the `Start-DSCConfiguration` cmdlet is complete, you should see a `HelloWorld.txt` file in the location you specified.</span></span> <span data-ttu-id="aec04-146">Sie können die Inhalte mit dem Cmdlet [Get-Content](/powershell/module/microsoft.powershell.management/get-content) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="aec04-146">You can verify the contents with the [Get-Content](/powershell/module/microsoft.powershell.management/get-content) cmdlet.</span></span>

<span data-ttu-id="aec04-147">Sie können den aktuellen Status auch mit [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)_testen_.</span><span class="sxs-lookup"><span data-stu-id="aec04-147">You can also _test_ the current status using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>

<span data-ttu-id="aec04-148">Die Ausgabe muss `True` sein, wenn der Knoten derzeit der angewendeten Konfiguration entspricht.</span><span class="sxs-lookup"><span data-stu-id="aec04-148">The output should be `True` if the Node is currently compliant with the applied Configuration.</span></span>

```powershell
Test-DSCConfiguration
```

```Output
True
```

```powershell
Get-Content -Path C:\Temp\HelloWorld.txt
```

```Output
Hello World from DSC!
```

## <a name="re-applying-the-configuration"></a><span data-ttu-id="aec04-149">Erneutes Anwenden der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="aec04-149">Re-applying the configuration</span></span>

<span data-ttu-id="aec04-150">Sie können die Textdatei entfernen, die von Ihrer Konfiguration erstellt wurde, um die erneute Anwendung Ihrer Konfiguration anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="aec04-150">To see your configuration get applied again, you can remove the text file created by your Configuration.</span></span> <span data-ttu-id="aec04-151">Verwenden Sie dann das Cmdlet `Start-DSCConfiguration` mit dem Parameter `-UseExisting`.</span><span class="sxs-lookup"><span data-stu-id="aec04-151">The use the `Start-DSCConfiguration` cmdlet with the `-UseExisting` parameter.</span></span> <span data-ttu-id="aec04-152">Der Parameter `-UseExisting` weist `Start-DSCConfiguration` an, die Datei „current.mof“ erneut anzuwenden, die die letzte erfolgreich angewendete Konfiguration darstellt.</span><span class="sxs-lookup"><span data-stu-id="aec04-152">The `-UseExisting` parameter instructs `Start-DSCConfiguration` to re-apply the "current.mof" file, which represents the most recently successfully applied configuration.</span></span>

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a><span data-ttu-id="aec04-153">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="aec04-153">Next steps</span></span>

- <span data-ttu-id="aec04-154">Weiteren Informationen zu DSC-Konfigurationen erhalten Sie unter [DSC-Konfigurationen](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="aec04-154">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="aec04-155">Welche DSC-Ressourcen verfügbar sind und wie Sie benutzerdefinierte DSC-Ressourcen erstellen erfahren Sie unter [DSC-Ressourcen](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="aec04-155">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="aec04-156">DSC-Konfigurationen und -Ressourcen finden Sie unter [PowerShell-Katalog](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="aec04-156">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
