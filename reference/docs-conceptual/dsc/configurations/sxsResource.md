---
ms.date: 06/12/2017
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Importieren einer spezifischen Version einer installierten Ressource
description: In diesem Artikel wird gezeigt, wie Sie bestimmte Versionen von Ressourcenmodulen in Ihre Konfigurationen installieren und importieren.
ms.openlocfilehash: bb7b3273a5a3fed94fecd90dd3ea1e623fbc332b
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645056"
---
# <a name="import-a-specific-version-of-an-installed-resource"></a><span data-ttu-id="57851-104">Importieren einer spezifischen Version einer installierten Ressource</span><span class="sxs-lookup"><span data-stu-id="57851-104">Import a specific version of an installed resource</span></span>

> <span data-ttu-id="57851-105">Gilt für: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="57851-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="57851-106">In PowerShell 5.0 können separate Versionen von DSC-Ressourcen auf einem Computer parallel installiert werden.</span><span class="sxs-lookup"><span data-stu-id="57851-106">In PowerShell 5.0, separate versions of DSC resources can be installed on a computer side by side.</span></span> <span data-ttu-id="57851-107">Ein Ressourcenmodul kann separate Versionen einer Ressource in nach der Version benannten Ordnern speichern.</span><span class="sxs-lookup"><span data-stu-id="57851-107">A resource module can store separate versions of a resource in version named folders.</span></span>

## <a name="installing-separate-resource-versions-side-by-side"></a><span data-ttu-id="57851-108">Paralleles Installieren separater Ressourcenversionen</span><span class="sxs-lookup"><span data-stu-id="57851-108">Installing separate resource versions side by side</span></span>

<span data-ttu-id="57851-109">Sie können die Parameter **MinimumVersion** , **MaximumVersion** und **RequiredVersion** des Cmdlets [Install-Module](/powershell/module/PowershellGet/Install-Module) verwenden, um anzugeben, welche Version eines Moduls installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="57851-109">You can use the **MinimumVersion** , **MaximumVersion** , and **RequiredVersion** parameters of the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to specify which version of a module to install.</span></span> <span data-ttu-id="57851-110">Wenn Sie **Install-Module** ohne Angabe eine Version aufrufen, wird die neueste Version installiert.</span><span class="sxs-lookup"><span data-stu-id="57851-110">Calling **Install-Module** without specifying a version installs the most recent version.</span></span>

<span data-ttu-id="57851-111">So gibt es beispielsweise mehrere Versionen des **xFailOverCluster** -Moduls, von denen jede eine **xCluster** -Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="57851-111">For example, there are multiple versions of the **xFailOverCluster** module, each of which contains an **xCluster** resource.</span></span> <span data-ttu-id="57851-112">Wenn Sie **Install-Module** ohne Angabe der Versionsnummer aufrufen, wird die neueste Version des Moduls installiert.</span><span class="sxs-lookup"><span data-stu-id="57851-112">Calling **Install-Module** without specifying the version number installs the most recent version of the module.</span></span>

```powershell
PS> Install-Module xFailOverCluster
PS> Get-DscResource xCluster
```

```Output
ImplementedAs   Name          ModuleName           Version    Properties
-------------   ----          ----------           -------    ----------
PowerShell      xCluster      xFailOverCluster     1.2.0.0    {DomainAdministratorCredential, ...
```

<span data-ttu-id="57851-113">Um eine bestimmte Version eines Moduls zu installieren, geben Sie eine **RequiredVersion** von 1.1.0.0 an.</span><span class="sxs-lookup"><span data-stu-id="57851-113">To install a specific version of a module, specify a **RequiredVersion** of 1.1.0.0.</span></span> <span data-ttu-id="57851-114">Dadurch wird die angegebene Version parallel mit der installierten Version installiert.</span><span class="sxs-lookup"><span data-stu-id="57851-114">This installs the specified version side by side with the installed version.</span></span>

```powershell
PS> Install-Module xFailOverCluster -RequiredVersion 1.1
```

<span data-ttu-id="57851-115">Nun sehen Sie, dass beide Versionen des Moduls aufgelistet werden, wenn Sie `Get-DSCResource` verwenden.</span><span class="sxs-lookup"><span data-stu-id="57851-115">Now, you see both version of the module listed when you use `Get-DSCResource`.</span></span>

```powershell
PS> Get-DscResource xCluster
```

```Output
ImplementedAs   Name          ModuleName            Version    Properties
-------------   ----          ----------            -------    ----------
PowerShell      xCluster      xFailOverCluster      1.1        {DomainAdministratorCredential, Name, ...
PowerShell      xCluster      xFailOverCluster      1.2.0.0    {DomainAdministratorCredential, Name, ...
```

## <a name="specifying-a-resource-version-in-a-configuration"></a><span data-ttu-id="57851-116">Angeben einer Ressourcenversion in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="57851-116">Specifying a resource version in a configuration</span></span>

<span data-ttu-id="57851-117">Wenn Sie separate Ressourcenversionen auf einem Computer installiert haben, müssen Sie die Version dieser Ressource angeben, wenn Sie sie in einer Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="57851-117">If you have separate resource versions installed on a computer, you must specify the version of that resource when you use it in a configuration.</span></span> <span data-ttu-id="57851-118">Hierzu geben Sie den Parameter **ModuleVersion** des Schlüsselworts **Import-DscResource** an.</span><span class="sxs-lookup"><span data-stu-id="57851-118">You do this by specifying the **ModuleVersion** parameter of the **Import-DscResource** keyword.</span></span> <span data-ttu-id="57851-119">Wenn Sie bei einer Ressource, von der Sie mehr als eine Version installiert haben, keine Version des Ressourcenmoduls angeben, generiert die Konfiguration einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="57851-119">If you fail to specify the version of a resource module of a resource of which you have more than one version installed, the configuration generates an error.</span></span>

<span data-ttu-id="57851-120">Die folgende Konfiguration zeigt, wie Sie die Version der aufzurufenden Ressource angeben:</span><span class="sxs-lookup"><span data-stu-id="57851-120">The following configuration shows how to specify the version of the resource to call:</span></span>

```powershell
configuration VersionTest
{
    Import-DscResource -ModuleName xFailOverCluster -ModuleVersion 1.1

    Node 'localhost'
    {
       xCluster ClusterTest
       {
            Name                          = 'TestCluster'
            StaticIPAddress               = '10.0.0.3'
            DomainAdministratorCredential = Get-Credential
        }
     }
}
```

<span data-ttu-id="57851-121">Der Parameter „ModuleVersion“ von „Import-DscResource“ ist in PowerShell 4.0 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="57851-121">The ModuleVersion parameter of Import-DscResource is not available in PowerShell 4.0.</span></span> <span data-ttu-id="57851-122">In PowerShell 4.0 können Sie eine Modulversion angeben, indem Sie ein Modulspezifikationsobjekt an den Parameter „ModuleName“ von „Import-DscResource“ übergeben.</span><span class="sxs-lookup"><span data-stu-id="57851-122">In PowerShell 4.0, you can specify a module version by passing a module specification object to the ModuleName parameter of Import-DscResource.</span></span> <span data-ttu-id="57851-123">Ein Modulspezifikationsobjekt ist eine Hashtabelle, die die Schlüssel ModuleName und RequiredVersion enthält.</span><span class="sxs-lookup"><span data-stu-id="57851-123">A module specification object is a hash table that contains ModuleName and RequiredVersion keys.</span></span> <span data-ttu-id="57851-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="57851-124">For example:</span></span>

```powershell
configuration VersionTest
{
    Import-DscResource -ModuleName (@{ModuleName='xFailOverCluster'; RequiredVersion='1.1'} )

    Node 'localhost'
    {
       xCluster ClusterTest
       {
            Name                          = 'TestCluster'
            StaticIPAddress               = '10.0.0.3'
            DomainAdministratorCredential = Get-Credential
        }
     }
}
```

<span data-ttu-id="57851-125">Dies funktioniert auch in PowerShell 5.0, aber es wird empfohlen, dass Sie den Parameter **ModuleVersion** verwenden.</span><span class="sxs-lookup"><span data-stu-id="57851-125">This will also work in PowerShell 5.0, but it is recommended that you use the **ModuleVersion** parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="57851-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57851-126">See also</span></span>

- [<span data-ttu-id="57851-127">DSC-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="57851-127">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="57851-128">DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="57851-128">DSC Resources</span></span>](../resources/resources.md)
