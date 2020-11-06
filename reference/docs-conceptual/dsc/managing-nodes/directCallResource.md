---
ms.date: 08/11/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Direktes Aufrufen von DSC-Ressourcenmethoden
description: Das Cmdlet Invoke-DscResource kann verwendet werden, um die Funktionen oder Methoden einer DSC-Ressource aufzurufen. Es kann von Drittanbietern verwendet werden, die DSC-Ressourcen verwenden möchten, oder als hilfreiches Tool bei der Entwicklung von Ressourcen.
ms.openlocfilehash: 5ccf0f589b60cef4ec197d1e0a583af9ed60d5e7
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92651000"
---
# <a name="calling-dsc-resource-methods-directly"></a><span data-ttu-id="a30ae-105">Direktes Aufrufen von DSC-Ressourcenmethoden</span><span class="sxs-lookup"><span data-stu-id="a30ae-105">Calling DSC resource methods directly</span></span>

> <span data-ttu-id="a30ae-106">Gilt für: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="a30ae-106">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="a30ae-107">Sie können das Cmdlet [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) verwenden, um die Funktionen oder Methoden einer DSC-Ressource direkt aufzurufen (die Funktionen `Get-TargetResource`, `Set-TargetResource` und `Test-TargetResource` einer MOF-basierten Ressource oder die Methoden **Get** , **Set** und **Test** einer klassenbasierten Ressource).</span><span class="sxs-lookup"><span data-stu-id="a30ae-107">You can use the [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) cmdlet to directly call the functions or methods of a DSC resource (The `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` functions of a MOF-based resource, or the **Get** , **Set** , and **Test** methods of a class-based resource).</span></span> <span data-ttu-id="a30ae-108">Dieses kann von Drittanbietern verwendet werden, die DSC-Ressourcen verwenden möchten, oder als hilfreiches Tool bei der Entwicklung von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a30ae-108">This can be used by third-parties that want to use DSC resources, or as a helpful tool while developing resources.</span></span>

> [!NOTE]
> <span data-ttu-id="a30ae-109">Ab PowerShell 7.0 unterstützt `Invoke-DscResource` nicht mehr das Aufrufen von WMI DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a30ae-109">In PowerShell 7.0+, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="a30ae-110">Dies gilt auch für die Ressourcen **File** und **Log** in **PSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a30ae-110">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

<span data-ttu-id="a30ae-111">Dieses Cmdlet wird in der Regel in Kombination mit einer Metakonfigurationseigenschaft `refreshMode = 'Disabled'` verwendet, kann aber unabhängig davon verwendet werden, auf was **refreshMode** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a30ae-111">This cmdlet is typically used in combination with a metaconfiguration property `refreshMode = 'Disabled'`, but it can be used no matter what **refreshMode** is set to.</span></span>

<span data-ttu-id="a30ae-112">Beim Aufrufen des Cmdlets `Invoke-DscResource` geben Sie mithilfe des **Method** -Parameters an, welche Methode oder Funktion aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a30ae-112">When calling the `Invoke-DscResource` cmdlet, you specify which method or function to call by using the **Method** parameter.</span></span> <span data-ttu-id="a30ae-113">Sie geben die Eigenschaften der Ressource an, indem Sie eine Hashtabelle als Wert des Parameters **Property** übergeben.</span><span class="sxs-lookup"><span data-stu-id="a30ae-113">You specify the properties of the resource by passing a hashtable as the value of the **Property** parameter.</span></span>

<span data-ttu-id="a30ae-114">Im Folgenden finden Sie Beispiele für das direkte Aufrufen von Ressourcenmethoden:</span><span class="sxs-lookup"><span data-stu-id="a30ae-114">The following are examples of directly calling resource methods:</span></span>

## <a name="ensure-a-file-is-present"></a><span data-ttu-id="a30ae-115">Sicherstellen, dass eine Datei vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="a30ae-115">Ensure a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
              DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
              Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a><span data-ttu-id="a30ae-116">Testen, ob eine Datei vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="a30ae-116">Test that a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a><span data-ttu-id="a30ae-117">Abrufen des Inhalts einer Datei</span><span class="sxs-lookup"><span data-stu-id="a30ae-117">Get the contents of file</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

> [!NOTE]
> <span data-ttu-id="a30ae-118">Das direkte Aufrufen von Methoden für zusammengesetzte Ressourcen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a30ae-118">Directly calling composite resource methods is not supported.</span></span> <span data-ttu-id="a30ae-119">Rufen Sie stattdessen die Methoden der zugrunde liegenden Ressourcen auf, aus denen die zusammengesetzte Ressource besteht.</span><span class="sxs-lookup"><span data-stu-id="a30ae-119">Instead, call the methods of the underlying resources that make up the composite resource.</span></span>

## <a name="see-also"></a><span data-ttu-id="a30ae-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a30ae-120">See Also</span></span>

- [<span data-ttu-id="a30ae-121">Schreiben einer benutzerdefinierten DSC-Ressource mit MOF</span><span class="sxs-lookup"><span data-stu-id="a30ae-121">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="a30ae-122">Schreiben einer benutzerdefinierten DSC-Ressource mit PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="a30ae-122">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)
- [<span data-ttu-id="a30ae-123">Debuggen von DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="a30ae-123">Debugging DSC resources</span></span>](../troubleshooting/debugResource.md)
