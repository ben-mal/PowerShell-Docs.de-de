---
title: Dynamische Cmdlet-Parameter | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: f44f71326d4711242c754c332a151dd997721595
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782360"
---
# <a name="cmdlet-dynamic-parameters"></a><span data-ttu-id="958e7-102">Dynamische Cmdlet-Parameter</span><span class="sxs-lookup"><span data-stu-id="958e7-102">Cmdlet dynamic parameters</span></span>

<span data-ttu-id="958e7-103">Cmdlets können Parameter definieren, die für den Benutzer unter bestimmten Bedingungen verfügbar sind, z. b. wenn das Argument eines anderen Parameters ein bestimmter Wert ist.</span><span class="sxs-lookup"><span data-stu-id="958e7-103">Cmdlets can define parameters that are available to the user under special conditions, such as when the argument of another parameter is a specific value.</span></span> <span data-ttu-id="958e7-104">Diese Parameter werden zur Laufzeit hinzugefügt und als dynamische Parameter bezeichnet, da Sie nur bei Bedarf hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="958e7-104">These parameters are added at runtime and are referred to as dynamic parameters because they're only added when needed.</span></span> <span data-ttu-id="958e7-105">Beispielsweise können Sie ein Cmdlet entwerfen, das nur dann mehrere Parameter hinzufügt, wenn ein bestimmter Switch-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="958e7-105">For example, you can design a cmdlet that adds several parameters only when a specific switch parameter is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="958e7-106">Anbieter und PowerShell-Funktionen können auch dynamische Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="958e7-106">Providers and PowerShell functions can also define dynamic parameters.</span></span>

## <a name="dynamic-parameters-in-powershell-cmdlets"></a><span data-ttu-id="958e7-107">Dynamische Parameter in PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="958e7-107">Dynamic parameters in PowerShell cmdlets</span></span>

<span data-ttu-id="958e7-108">PowerShell verwendet dynamische Parameter in mehreren der Anbieter-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="958e7-108">PowerShell uses dynamic parameters in several of its provider cmdlets.</span></span> <span data-ttu-id="958e7-109">Beispielsweise fügen die `Get-Item` -und- `Get-ChildItem` Cmdlets zur Laufzeit einen **codeSigningCert** -Parameter hinzu, wenn der **path** -Parameter den Pfad des **Zertifikat** Anbieters angibt.</span><span class="sxs-lookup"><span data-stu-id="958e7-109">For example, the `Get-Item` and `Get-ChildItem` cmdlets add a **CodeSigningCert** parameter at runtime when the **Path** parameter specifies the **Certificate** provider path.</span></span> <span data-ttu-id="958e7-110">Wenn der **path** -Parameter einen Pfad für einen anderen Anbieter angibt, ist der **codeSigningCert** -Parameter nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="958e7-110">If the **Path** parameter specifies a path for a different provider, the **CodeSigningCert** parameter isn't available.</span></span>

<span data-ttu-id="958e7-111">In den folgenden Beispielen wird gezeigt, wie der **codeSigningCert** -Parameter zur Laufzeit hinzugefügt wird, wenn `Get-Item` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="958e7-111">The following examples show how the **CodeSigningCert** parameter is added at runtime when `Get-Item` is run.</span></span>

<span data-ttu-id="958e7-112">In diesem Beispiel hat die PowerShell-Laufzeit den-Parameter hinzugefügt, und das Cmdlet ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="958e7-112">In this example, the PowerShell runtime has added the parameter and the cmdlet is successful.</span></span>

```powershell
Get-Item -Path cert:\CurrentUser -CodeSigningCert
```

```Output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

<span data-ttu-id="958e7-113">In diesem Beispiel wird ein **Dateisystem** Laufwerk angegeben, und es wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="958e7-113">In this example, a **FileSystem** drive is specified and an error is returned.</span></span> <span data-ttu-id="958e7-114">Die Fehlermeldung gibt an, dass der **codeSigningCert** -Parameter nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="958e7-114">The error message indicates that the **CodeSigningCert** parameter can't be found.</span></span>

```powershell
Get-Item -Path C:\ -CodeSigningCert
```

```Output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a><span data-ttu-id="958e7-115">Unterstützung für dynamische Parameter</span><span class="sxs-lookup"><span data-stu-id="958e7-115">Support for dynamic parameters</span></span>

<span data-ttu-id="958e7-116">Um dynamische Parameter zu unterstützen, müssen die folgenden Elemente im Cmdlet-Code enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="958e7-116">To support dynamic parameters, the following elements must be included in the cmdlet code.</span></span>

### <a name="interface"></a><span data-ttu-id="958e7-117">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="958e7-117">Interface</span></span>

<span data-ttu-id="958e7-118">[System. Management. Automation. idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters).</span><span class="sxs-lookup"><span data-stu-id="958e7-118">[System.Management.Automation.IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters).</span></span>
<span data-ttu-id="958e7-119">Diese Schnittstelle stellt die Methode bereit, die die dynamischen Parameter abruft.</span><span class="sxs-lookup"><span data-stu-id="958e7-119">This interface provides the method that retrieves the dynamic parameters.</span></span>

<span data-ttu-id="958e7-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="958e7-120">For example:</span></span>

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

### <a name="method"></a><span data-ttu-id="958e7-121">Methode</span><span class="sxs-lookup"><span data-stu-id="958e7-121">Method</span></span>

<span data-ttu-id="958e7-122">[System. Management. Automation. idynamicparameters. getdynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span><span class="sxs-lookup"><span data-stu-id="958e7-122">[System.Management.Automation.IDynamicParameters.GetDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span></span>
<span data-ttu-id="958e7-123">Diese Methode ruft das-Objekt ab, das die dynamischen Parameter Definitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="958e7-123">This method retrieves the object that contains the dynamic parameter definitions.</span></span>

<span data-ttu-id="958e7-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="958e7-124">For example:</span></span>

```csharp
 public object GetDynamicParameters()
 {
   if (employee)
   {
     context= new SendGreetingCommandDynamicParameters();
     return context;
   }
   return null;
}
private SendGreetingCommandDynamicParameters context;
```

### <a name="class"></a><span data-ttu-id="958e7-125">Klasse</span><span class="sxs-lookup"><span data-stu-id="958e7-125">Class</span></span>

<span data-ttu-id="958e7-126">Eine Klasse, die die dynamischen Parameter definiert, die hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="958e7-126">A class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="958e7-127">Diese Klasse muss ein **Parameter** Attribut für jeden Parameter und alle optionalen **Alias** -und **Validierungs** Attribute enthalten, die vom Cmdlet benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="958e7-127">This class must include a **Parameter** attribute for each parameter and any optional **Alias** and **Validation** attributes that are needed by the cmdlet.</span></span>

<span data-ttu-id="958e7-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="958e7-128">For example:</span></span>

```csharp
public class SendGreetingCommandDynamicParameters
{
  [Parameter]
  [ValidateSet ("Marketing", "Sales", "Development")]
  public string Department
  {
    get { return department; }
    set { department = value; }
  }
  private string department;
}
```

<span data-ttu-id="958e7-129">Ein umfassendes Beispiel für ein Cmdlet, das dynamische Parameter unterstützt, finden [Sie unter deklarieren dynamischer Parameter](./how-to-declare-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="958e7-129">For a complete example of a cmdlet that supports dynamic parameters, see [How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="958e7-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="958e7-130">See also</span></span>

[<span data-ttu-id="958e7-131">System. Management. Automation. idynamicparameters</span><span class="sxs-lookup"><span data-stu-id="958e7-131">System.Management.Automation.IDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters)

[<span data-ttu-id="958e7-132">System. Management. Automation. idynamicparameters. getdynamicparameters</span><span class="sxs-lookup"><span data-stu-id="958e7-132">System.Management.Automation.IDynamicParameters.GetDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="958e7-133">Deklarieren von dynamischen Parametern</span><span class="sxs-lookup"><span data-stu-id="958e7-133">How to Declare Dynamic Parameters</span></span>](./how-to-declare-dynamic-parameters.md)

[<span data-ttu-id="958e7-134">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="958e7-134">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
