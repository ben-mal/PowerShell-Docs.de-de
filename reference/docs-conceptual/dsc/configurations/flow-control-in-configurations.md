---
ms.date: 12/12/2018
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Bedingte Anweisungen und Schleifen in Konfigurationen
description: Dieser Artikel zeigt Ihnen, wie Sie bedingte Anweisungen und Schleifen verwenden können, um Ihre Konfiguration dynamischer zu gestalten. Die Kombination von Bedingungen und Schleifen mit Parametern und Konfigurationsdaten ermöglicht Ihnen mehr Flexibilität und Kontrolle bei der Kompilierung Ihrer Konfiguration.
ms.openlocfilehash: 7af8a360c17a0842fa2b95d1d1fb288323c327ef
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658468"
---
# <a name="conditional-statements-and-loops-in-a-configuration"></a><span data-ttu-id="1245c-105">Bedingte Anweisungen und Schleifen in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1245c-105">Conditional statements and loops in a Configuration</span></span>

<span data-ttu-id="1245c-106">Sie können Ihre [Konfiguration](configurations.md) dynamischer gestalten, indem Sie PowerShell-Schlüsselwörter für die Ablaufsteuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1245c-106">You can make your [Configuration](configurations.md) more dynamic by using PowerShell flow-control keywords.</span></span> <span data-ttu-id="1245c-107">Dieser Artikel zeigt Ihnen, wie Sie bedingte Anweisungen und Schleifen verwenden können, um Ihre `Configuration` dynamischer zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="1245c-107">This article shows you how you can use conditional statements and loops to make your `Configuration` more dynamic.</span></span> <span data-ttu-id="1245c-108">Die Kombination von Bedingungen und Schleifen mit [Parametern](add-parameters-to-a-configuration.md) und [Konfigurationsdaten](configData.md) ermöglicht Ihnen mehr Flexibilität und Kontrolle bei der Kompilierung Ihrer `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="1245c-108">Combining conditional statements and loops with [parameters](add-parameters-to-a-configuration.md) and [Configuration Data](configData.md) allows you more flexibility and control when compiling your `Configuration`.</span></span>

<span data-ttu-id="1245c-109">Genau wie eine Funktion oder ein Skriptblock können Sie jedes beliebige PowerShell-Sprachfeature innerhalb einer `Configuration` verwenden.</span><span class="sxs-lookup"><span data-stu-id="1245c-109">Just like a function or a script block, you can use any PowerShell language feature within a `Configuration`.</span></span> <span data-ttu-id="1245c-110">Die von Ihnen verwendeten Anweisungen werden nur ausgewertet, wenn Sie Ihre `Configuration` aufrufen, um eine `.mof`-Datei zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="1245c-110">The statements you use will only be evaluated when you call your `Configuration` to compile a `.mof` file.</span></span> <span data-ttu-id="1245c-111">Die folgenden Beispiele zeigen Szenarien zur Veranschaulichung der Konzepte.</span><span class="sxs-lookup"><span data-stu-id="1245c-111">The examples below show scenarios to demonstrate concepts.</span></span> <span data-ttu-id="1245c-112">Bedingte Anweisungen und Schleifen werden häufiger mit Parametern und Konfigurationsdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="1245c-112">Conditional statements and loops are more often used with parameters and configuration Data.</span></span>

<span data-ttu-id="1245c-113">In diesem Beispiel ruft der Ressourcenblock **Service** den aktuellen Zustand eines Diensts zur Kompilierungszeit ab, um eine `.mof`-Datei zu generieren, die ihren aktuellen Zustand beibehält.</span><span class="sxs-lookup"><span data-stu-id="1245c-113">In this  example, the **Service** resource block retrieves the current state of a service at compile time to generate a `.mof` file that maintains its current state.</span></span>

> [!NOTE]
> <span data-ttu-id="1245c-114">Die Verwendung dynamischer Ressourcenblöcke verhindert die Effektivität von IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="1245c-114">Using dynamic Resource blocks will preempt the effectiveness of Intellisense.</span></span> <span data-ttu-id="1245c-115">Der PowerShell-Parser kann nicht bestimmen, ob die angegebenen Werte akzeptabel sind, bis die `Configuration` kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="1245c-115">The PowerShell parser cannot determine if the values specified are acceptable until the `Configuration` is compiled.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Service Spooler
        {
            Name = "Spooler"
            State = $(Get-Service -Name 'spooler').Status
            StartType = $(Get-Service -Name 'spooler').StartType
        }
    }
}
```

<span data-ttu-id="1245c-116">Zusätzlich können Sie für jeden Dienst auf dem aktuellen Computer einen **Service** -Ressourcenblock erstellen, indem Sie eine `foreach`-Schleife verwenden.</span><span class="sxs-lookup"><span data-stu-id="1245c-116">Additionally, you could create a **Service** resource block for every service on the current machine using a `foreach` loop.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        foreach ($service in $(Get-Service))
        {
            Service $service.Name
            {
                Name = $service.Name
                State = $service.Status
                StartType = $service.StartType
            }
        }
    }
}
```

<span data-ttu-id="1245c-117">Sie können mithilfe einer `if`-Anweisung auch eine `Configuration` nur für Computer erstellen, die online sind.</span><span class="sxs-lookup"><span data-stu-id="1245c-117">You could also create a `Configuration` only for machines that are online by using an `if` statement.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    foreach ($computer in @('Server01', 'Server02', 'Server03'))
    {
        if (Test-Connection -ComputerName $computer)
        {
            Node $computer
            {
                Service "Spooler"
                {
                    Name = "Spooler"
                    State = "Started"
                }
            }
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="1245c-118">Die dynamischen Ressourcenblöcke in den oben aufgeführten Beispielen verweisen auf den aktuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="1245c-118">The dynamic resource blocks in the above examples reference the current machine.</span></span> <span data-ttu-id="1245c-119">In diesem Fall wäre das der Computer, auf dem Sie die `Configuration` erstellen, nicht der Zielknoten.</span><span class="sxs-lookup"><span data-stu-id="1245c-119">In this instance, that would be the machine you are authoring the `Configuration` on, not the target Node.</span></span>

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a><span data-ttu-id="1245c-120">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1245c-120">Summary</span></span>

<span data-ttu-id="1245c-121">Zusammenfassend lässt sich sagen, dass Sie jedes beliebige PowerShell-Sprachfeature innerhalb einer `Configuration` verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1245c-121">In summary, you can use any PowerShell language feature within a `Configuration`.</span></span>

<span data-ttu-id="1245c-122">Dazu zählen etwa:</span><span class="sxs-lookup"><span data-stu-id="1245c-122">This includes things like:</span></span>

- <span data-ttu-id="1245c-123">Benutzerdefinierte Objekte</span><span class="sxs-lookup"><span data-stu-id="1245c-123">Custom Objects</span></span>
- <span data-ttu-id="1245c-124">Hashtabellen</span><span class="sxs-lookup"><span data-stu-id="1245c-124">Hashtables</span></span>
- <span data-ttu-id="1245c-125">Zeichenfolgenbearbeitung</span><span class="sxs-lookup"><span data-stu-id="1245c-125">String manipulation</span></span>
- <span data-ttu-id="1245c-126">Remoting</span><span class="sxs-lookup"><span data-stu-id="1245c-126">Remoting</span></span>
- <span data-ttu-id="1245c-127">WMI und CIM</span><span class="sxs-lookup"><span data-stu-id="1245c-127">WMI and CIM</span></span>
- <span data-ttu-id="1245c-128">Active Directory-Objekte</span><span class="sxs-lookup"><span data-stu-id="1245c-128">ActiveDirectory objects</span></span>
- <span data-ttu-id="1245c-129">und vieles mehr...</span><span class="sxs-lookup"><span data-stu-id="1245c-129">and more...</span></span>

<span data-ttu-id="1245c-130">Der gesamte PowerShell-Code, der in einer `Configuration` definiert ist, wird während der Kompilierung ausgewertet, aber Sie können auch Code in das Skript einfügen, das Ihre `Configuration` enthält.</span><span class="sxs-lookup"><span data-stu-id="1245c-130">Any PowerShell code defined in a `Configuration` is evaluated at compile time, but you can also place code in the script containing your `Configuration`.</span></span> <span data-ttu-id="1245c-131">Sämtlicher Code, der sich außerhalb des `Configuration`-Blocks befindet, wird beim Import Ihrer `Configuration` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1245c-131">Any code outside of the `Configuration` block is executed when you import your `Configuration`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1245c-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1245c-132">See also</span></span>

- [<span data-ttu-id="1245c-133">Hinzufügen von Parametern zu einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1245c-133">Add parameters to a Configuration</span></span>](add-parameters-to-a-configuration.md)
- [<span data-ttu-id="1245c-134">Trennen von Konfigurationsdaten von Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="1245c-134">Separate Configuration data from Configurations</span></span>](configData.md)
