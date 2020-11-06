---
ms.date: 06/12/2017
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Verschachteln von Konfigurationen
description: DSC ermöglicht das Erstellen zusammengesetzter Konfigurationen, indem eine Konfiguration in einer anderen Konfiguration geschachtelt wird.
ms.openlocfilehash: d7a81cb9673126e92e9185aacf19c5c7c17da8ca
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667418"
---
# <a name="nesting-dsc-configurations"></a><span data-ttu-id="eefca-104">Schachteln von DSC-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="eefca-104">Nesting DSC configurations</span></span>

<span data-ttu-id="eefca-105">Eine geschachtelte Konfiguration (auch zusammengesetzte Konfiguration genannt) ist eine Konfiguration, die in einer anderen Konfiguration aufgerufen wird, als handele es sich um eine Ressource.</span><span class="sxs-lookup"><span data-stu-id="eefca-105">A nested configuration (also called composite configuration) is a configuration that's called within another configuration as if it were a resource.</span></span> <span data-ttu-id="eefca-106">Beide Konfigurationen müssen in derselben Datei definiert werden.</span><span class="sxs-lookup"><span data-stu-id="eefca-106">Both configurations must be defined in the same file.</span></span>

<span data-ttu-id="eefca-107">Sehen wir uns ein einfaches Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="eefca-107">Let's look at a simple example:</span></span>

```powershell
Configuration FileConfig
{
    param (
        [Parameter(Mandatory = $true)]
        [String] $CopyFrom,

        [Parameter(Mandatory = $true)]
        [String] $CopyTo
    )

    Import-DscResource -ModuleName PSDesiredStateConfiguration

    File FileTest
    {
        SourcePath = $CopyFrom
        DestinationPath = $CopyTo
        Ensure = 'Present'
    }
}

Configuration NestedFileConfig
{
    Node localhost
    {
        FileConfig NestedConfig
        {
            CopyFrom = 'C:\Test\TestFile.txt'
            CopyTo = 'C:\Test2'
        }
    }
}
```

<span data-ttu-id="eefca-108">In diesem Beispiel akzeptiert `FileConfig` zwei erforderliche Parameter – **CopyFrom** und **CopyTo** –, die als Werte für die Eigenschaften **SourcePath** und **DestinationPath** im Ressourcenblock `File` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eefca-108">In this example, `FileConfig` takes two mandatory parameters, **CopyFrom** and **CopyTo** , which are used as the values for the **SourcePath** and **DestinationPath** properties in the `File` resource block.</span></span> <span data-ttu-id="eefca-109">Die Konfiguration `NestedConfig` ruft `FileConfig` auf, als handele es sich um eine Ressource.</span><span class="sxs-lookup"><span data-stu-id="eefca-109">The `NestedConfig` configuration calls `FileConfig` as if it were a resource.</span></span> <span data-ttu-id="eefca-110">Die Eigenschaften im Ressourcenblock `NestedConfig` ( **CopyFrom** und **CopyTo** ) sind die Parameter der Konfiguration `FileConfig`.</span><span class="sxs-lookup"><span data-stu-id="eefca-110">The properties in the `NestedConfig` resource block ( **CopyFrom** and **CopyTo** ) are the parameters of the `FileConfig` configuration.</span></span>

<span data-ttu-id="eefca-111">DSC unterstützt aktuell keine geschachtelten Konfigurationen innerhalb von geschachtelten Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="eefca-111">DSC doesn't currently support nesting configurations within nested configurations.</span></span> <span data-ttu-id="eefca-112">Sie können eine Konfiguration nur eine Ebene tief schachteln.</span><span class="sxs-lookup"><span data-stu-id="eefca-112">You can only nest a configuration one layer deep.</span></span>

## <a name="see-also"></a><span data-ttu-id="eefca-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eefca-113">See Also</span></span>

- [<span data-ttu-id="eefca-114">Zusammengesetzte Ressourcen: Verwenden einer DSC-Konfiguration als Ressource</span><span class="sxs-lookup"><span data-stu-id="eefca-114">Composite resources--Using a DSC configuration as a resource</span></span>](../resources/authoringResourceComposite.md)
