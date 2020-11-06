---
ms.date: 07/08/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: 'Zusammengesetzte Ressourcen: Verwenden einer DSC-Konfiguration als Ressource'
description: In diesem Artikel wird beschrieben, wie eine zusammengesetzte Ressource erstellt und verwendet wird.
ms.openlocfilehash: c1f0e3b45c3a393c04700b5a4bc88be365794820
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667299"
---
# <a name="composite-resources-using-a-dsc-configuration-as-a-resource"></a><span data-ttu-id="41049-104">Zusammengesetzte Ressourcen: Verwenden einer DSC-Konfiguration als Ressource</span><span class="sxs-lookup"><span data-stu-id="41049-104">Composite resources: Using a DSC configuration as a resource</span></span>

> <span data-ttu-id="41049-105">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="41049-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="41049-106">In realen Situationen können Konfigurationen lang und komplex sein, viele verschiedene Ressourcen aufrufen und eine große Anzahl von Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="41049-106">In real-world situations, configurations can become long and complex, calling many different resources and setting a vast number of properties.</span></span> <span data-ttu-id="41049-107">Um mit dieser Komplexität zurecht zu kommen, können Sie eine Windows PowerShell DSC-Konfiguration als Ressource für andere Konfigurationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="41049-107">To help address this complexity, you can use a Windows PowerShell Desired State Configuration (DSC) configuration as a resource for other configurations.</span></span> <span data-ttu-id="41049-108">Dies wird als zusammengesetzte Ressource bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="41049-108">This is called a composite resource.</span></span> <span data-ttu-id="41049-109">Eine zusammengesetzte Ressource ist eine DSC-Konfiguration, die Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="41049-109">A composite resource is a DSC configuration that takes parameters.</span></span> <span data-ttu-id="41049-110">Die Parameter der Konfiguration fungieren als Eigenschaften der Ressource.</span><span class="sxs-lookup"><span data-stu-id="41049-110">The parameters of the configuration act as the properties of the resource.</span></span>
<span data-ttu-id="41049-111">Die Konfiguration wird als Datei mit der Erweiterung `.schema.psm1` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="41049-111">The configuration is saved as a file with a `.schema.psm1` extension.</span></span> <span data-ttu-id="41049-112">Sie ersetzt sowohl das MOF-Schema als auch das Ressourcenskript in einer typischen DSC-Ressource.</span><span class="sxs-lookup"><span data-stu-id="41049-112">It takes the place of both the MOF schema, and the resource script in a typical DSC resource.</span></span> <span data-ttu-id="41049-113">Weitere Informationen zu DSC-Ressourcen finden Sie unter [Windows PowerShell DSC-Ressourcen](resources.md).</span><span class="sxs-lookup"><span data-stu-id="41049-113">For more information about DSC resources, see [Windows PowerShell Desired State Configuration Resources](resources.md).</span></span>

## <a name="creating-the-composite-resource"></a><span data-ttu-id="41049-114">Erstellen der zusammengesetzten Ressource</span><span class="sxs-lookup"><span data-stu-id="41049-114">Creating the composite resource</span></span>

<span data-ttu-id="41049-115">Im folgenden Beispiel wird eine Konfiguration erstellt, die eine Reihe von vorhandenen Ressourcen zum Konfigurieren virtueller Computer aufruft.</span><span class="sxs-lookup"><span data-stu-id="41049-115">In our example, we create a configuration that invokes a number of existing resources to configure virtual machines.</span></span> <span data-ttu-id="41049-116">Anstatt die festzulegenden Werte in Konfigurationsblöcken anzugeben, verwendet die Konfiguration Parameter, die anschließend in den Konfigurationsblöcken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="41049-116">Instead of specifying the values to be set in configuration blocks, the configuration takes in parameters that are then used in the configuration blocks.</span></span>

```powershell
Configuration xVirtualMachine
{
    param
    (
        # Name of VMs
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String[]] $VMName,

        # Name of Switch to create
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $SwitchName,

        # Type of Switch to create
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $SwitchType,

        # Source Path for VHD
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VHDParentPath,

        # Destination path for diff VHD
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VHDPath,

        # Startup Memory for VM
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VMStartupMemory,

        # State of the VM
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VMState
    )

    # Import the module that defines custom resources
    Import-DscResource -Module xComputerManagement,xHyper-V

    # Install the Hyper-V role
    WindowsFeature HyperV
    {
        Ensure = "Present"
        Name = "Hyper-V"
    }

    # Create the virtual switch
    xVMSwitch $SwitchName
    {
        Ensure = "Present"
        Name = $SwitchName
        Type = $SwitchType
        DependsOn = "[WindowsFeature]HyperV"
    }

    # Check for Parent VHD file
    File ParentVHDFile
    {
        Ensure = "Present"
        DestinationPath = $VHDParentPath
        Type = "File"
        DependsOn = "[WindowsFeature]HyperV"
    }

    # Check the destination VHD folder
    File VHDFolder
    {
        Ensure = "Present"
        DestinationPath = $VHDPath
        Type = "Directory"
        DependsOn = "[File]ParentVHDFile"
    }

    # Create VM specific diff VHD
    foreach ($Name in $VMName)
    {
        xVHD "VHD$Name"
        {
            Ensure = "Present"
            Name = $Name
            Path = $VHDPath
            ParentPath = $VHDParentPath
            DependsOn = @("[WindowsFeature]HyperV",
                          "[File]VHDFolder")
        }
    }

    # Create VM using the above VHD
    foreach($Name in $VMName)
    {
        xVMHyperV "VMachine$Name"
        {
            Ensure = "Present"
            Name = $Name
            VhDPath = (Join-Path -Path $VHDPath -ChildPath $Name)
            SwitchName = $SwitchName
            StartupMemory = $VMStartupMemory
            State = $VMState
            MACAddress = $MACAddress
            WaitForIP = $true
            DependsOn = @("[WindowsFeature]HyperV",
                          "[xVHD]VHD$Name")
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="41049-117">DSC bietet aktuell keine Unterstützung für das Platzieren von zusammengesetzten Ressourcen oder geschachtelten Konfigurationen innerhalb einer zusammengesetzten Ressource.</span><span class="sxs-lookup"><span data-stu-id="41049-117">DSC doesn't currently support placing composite resources or nested configurations within a composite resource.</span></span>

### <a name="saving-the-configuration-as-a-composite-resource"></a><span data-ttu-id="41049-118">Speichern die Konfiguration als eine zusammengesetzte Ressource</span><span class="sxs-lookup"><span data-stu-id="41049-118">Saving the configuration as a composite resource</span></span>

<span data-ttu-id="41049-119">Damit die parametrisierte Konfiguration als DSC-Ressource verwendet werden kann, speichern Sie sie in einer Verzeichnisstruktur, die den Verzeichnisstrukturen MOF-basierter Ressourcen entspricht, und geben Sie ihr einen Namen mit der Erweiterung `.schema.psm1`.</span><span class="sxs-lookup"><span data-stu-id="41049-119">To use the parameterized configuration as a DSC resource, save it in a directory structure like that of any other MOF-based resource, and name it with a `.schema.psm1` extension.</span></span> <span data-ttu-id="41049-120">In diesem Beispiel erhält die Datei die Bezeichnung `xVirtualMachine.schema.psm1`.</span><span class="sxs-lookup"><span data-stu-id="41049-120">For this example, we'll name the file `xVirtualMachine.schema.psm1`.</span></span> <span data-ttu-id="41049-121">Sie müssen außerdem ein Manifest mit dem Namen `xVirtualMachine.psd1` erstellen, das die folgende Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="41049-121">You also need to create a manifest named `xVirtualMachine.psd1` that contains the following line.</span></span>

```powershell
RootModule = 'xVirtualMachine.schema.psm1'
```

> [!NOTE]
> <span data-ttu-id="41049-122">Dies ist neben `MyDscResources.psd1` das Modulmanifest für alle Ressourcen im Ordner `MyDscResources`.</span><span class="sxs-lookup"><span data-stu-id="41049-122">This is in addition to `MyDscResources.psd1`, the module manifest for all resources under the `MyDscResources` folder.</span></span>

<span data-ttu-id="41049-123">Wenn Sie fertig sind, sollte die Ordnerstruktur wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="41049-123">When you are done, the folder structure should be as follows.</span></span>

```
$env: psmodulepath
    |- MyDscResources
        |- MyDscResources.psd1
        |- DSCResources
            |- xVirtualMachine
                |- xVirtualMachine.psd1
                |- xVirtualMachine.schema.psm1
```

<span data-ttu-id="41049-124">Die Ressource kann nun mit dem Cmdlet `Get-DscResource` gefunden werden, und ihre Eigenschaften können entweder mit diesem Cmdlet oder über die Tastenkombination <kbd>STRG</kbd>+<kbd>LEERTASTE</kbd> (AutoVervollständigen) in Windows PowerShell ISE sichtbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="41049-124">The resource is now discoverable by using the `Get-DscResource` cmdlet, and its properties are discoverable by either that cmdlet or by using <kbd>Ctrl</kbd>+<kbd>Space</kbd> autocomplete in the Windows PowerShell ISE.</span></span>

## <a name="using-the-composite-resource"></a><span data-ttu-id="41049-125">Verwenden der zusammengesetzten Ressource</span><span class="sxs-lookup"><span data-stu-id="41049-125">Using the composite resource</span></span>

<span data-ttu-id="41049-126">Als Nächstes wird eine Konfiguration erstellt, die die zusammengesetzte Ressource aufruft.</span><span class="sxs-lookup"><span data-stu-id="41049-126">Next we create a configuration that calls the composite resource.</span></span> <span data-ttu-id="41049-127">Diese Konfiguration ruft die zusammengesetzte Ressource „xVirtualMachine“ auf, um einen virtuellen Computer zu erstellen, und ruft anschließend die Ressource **xComputer** auf, um sie umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="41049-127">This configuration calls the xVirtualMachine composite resource to create a virtual machine, and then calls the **xComputer** resource to rename it.</span></span>

```powershell
configuration RenameVM
{
    Import-DscResource -Module xVirtualMachine
    Node localhost
    {
        xVirtualMachine VM
        {
            VMName = "Test"
            SwitchName = "Internal"
            SwitchType = "Internal"
            VhdParentPath = "C:\Demo\VHD\RTM.vhd"
            VHDPath = "C:\Demo\VHD"
            VMStartupMemory = 1024MB
            VMState = "Running"
        }
    }

    Node "192.168.10.1"
    {
        xComputer Name
        {
            Name = "SQL01"
            DomainName = "fourthcoffee.com"
        }
    }
}
```

<span data-ttu-id="41049-128">Sie können diese Ressource auch zum Erstellen mehrerer VMs verwenden, indem Sie ein Array von VM-Namen an die Ressource „xVirtualMachine“ übergeben.</span><span class="sxs-lookup"><span data-stu-id="41049-128">You can also use this resource to create multiple VMs by passing in an array of VM names to the xVirtualMachine resource.</span></span>

```PowerShell
Configuration MultipleVms
{
    Import-DscResource -Module xVirtualMachine
    Node localhost
    {
        xVirtualMachine VMs
        {
            VMName = "IIS01", "SQL01", "SQL02"
            SwitchName = "Internal"
            SwitchType = "Internal"
            VhdParentPath = "C:\Demo\VHD\RTM.vhd"
            VHDPath = "C:\Demo\VHD"
            VMStartupMemory = 1024MB
            VMState = "Running"
        }
    }
}
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="41049-129">Unterstützung von PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="41049-129">Supporting PsDscRunAsCredential</span></span>

> [!NOTE]
> <span data-ttu-id="41049-130">**PsDscRunAsCredential** wird in PowerShell 5.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41049-130">**PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="41049-131">Mithilfe der Eigenschaft **PsDscRunAsCredential** kann im Ressourcenblock [DSC configurations](../configurations/configurations.md) angegeben werden, dass die Ressource mit einem festgelegten Satz an Anmeldeinformationen ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="41049-131">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span> <span data-ttu-id="41049-132">Weitere Informationen finden Sie unter [Ausführen von DSC mit Benutzeranmeldeinformationen](../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="41049-132">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

<span data-ttu-id="41049-133">Um aus einer benutzerdefinierten Ressource auf den Benutzerkontext zuzugreifen, können Sie die automatische Variable `$PsDscContext` verwenden.</span><span class="sxs-lookup"><span data-stu-id="41049-133">To access the user context from within a custom resource, you can use the automatic variable `$PsDscContext`.</span></span>

<span data-ttu-id="41049-134">Beispielsweise wird mit dem folgenden Code der Benutzerkontext für die Ressourcenausführung in den ausführlichen Ausgabestream geschrieben:</span><span class="sxs-lookup"><span data-stu-id="41049-134">For example, the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if ($PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="see-also"></a><span data-ttu-id="41049-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41049-135">See Also</span></span>

### <a name="concepts"></a><span data-ttu-id="41049-136">Konzepte</span><span class="sxs-lookup"><span data-stu-id="41049-136">Concepts</span></span>

- [<span data-ttu-id="41049-137">Schreiben einer benutzerdefinierten DSC-Ressource mit MOF</span><span class="sxs-lookup"><span data-stu-id="41049-137">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
- [<span data-ttu-id="41049-138">Erste Schritte mit Windows PowerShell Desired State Configuration (DSC)</span><span class="sxs-lookup"><span data-stu-id="41049-138">Get Started with Windows PowerShell Desired State Configuration</span></span>](../overview/overview.md)
