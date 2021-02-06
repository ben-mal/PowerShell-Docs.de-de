---
description: Die Unterstützung experimenteller Features in PowerShell stellt einen Mechanismus bereit, über den experimentelle Features und vorhandene stabile Features in PowerShell oder PowerShell-Modulen parallel genutzt werden können.
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen zu experimentellen Features
ms.openlocfilehash: 82f5ef9838fcbb98e71e362ad00b1ec68f9a9f67
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596562"
---
# <a name="experimental-features"></a><span data-ttu-id="09510-103">Experimentelle Features</span><span class="sxs-lookup"><span data-stu-id="09510-103">Experimental Features</span></span>

<span data-ttu-id="09510-104">Die Unterstützung experimenteller Features in PowerShell stellt einen Mechanismus bereit, über den experimentelle Features und vorhandene stabile Features in PowerShell oder PowerShell-Modulen parallel genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="09510-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="09510-105">Ein experimentelles Feature ist ein Feature, dessen Design noch nicht finalisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="09510-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="09510-106">Das Feature wird bereitgestellt, damit die Benutzer es testen und Feedback dazu senden können.</span><span class="sxs-lookup"><span data-stu-id="09510-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="09510-107">Sobald ein experimentelles Feature finalisiert wurde, werden die Designänderungen zu Breaking Changes.</span><span class="sxs-lookup"><span data-stu-id="09510-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span> <span data-ttu-id="09510-108">Experimentelle Features sind nicht für den Einsatz in der Produktion vorgesehen, da Auswirkungen auf die Lauffähigkeit möglich sind.</span><span class="sxs-lookup"><span data-stu-id="09510-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span>

<span data-ttu-id="09510-109">Experimentelle Features sind standardmäßig deaktiviert und müssen vom Benutzer oder vom Administrator des Systems explizit aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="09510-109">Experimental features are disabled by default and need to be explicitly enabled by the user or administrator of the system.</span></span>

<span data-ttu-id="09510-110">Aktivierte experimentelle Features werden in der `powershell.config.json` Datei in `$PSHOME` für alle Benutzer oder die benutzerspezifische Konfigurationsdatei für einen bestimmten Benutzer aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="09510-110">Enabled experimental features are listed in the `powershell.config.json` file in `$PSHOME` for all users or the user-specific configuration file for a specific user.</span></span>

> [!NOTE]
> <span data-ttu-id="09510-111">Experimentelle Features, die in der Benutzer Konfigurationsdatei aktiviert sind, haben Vorrang vor experimentellen Funktionen in der System Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="09510-111">Experimental features enabled in the user configuration file take precedence over experimental features listed in the system configuration file.</span></span>

## <a name="the-experimental-attribute"></a><span data-ttu-id="09510-112">Das experimentelle Attribut</span><span class="sxs-lookup"><span data-stu-id="09510-112">The Experimental Attribute</span></span>

<span data-ttu-id="09510-113">Verwenden Sie das- `Experimental` Attribut, um Code als experimentell zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="09510-113">Use the `Experimental` attribute to declare some code as experimental.</span></span>

<span data-ttu-id="09510-114">Verwenden Sie die folgende Syntax, um das Attribut zu deklarieren, das `Experimental` den Namen des experimentellen Features und die auszuführende Aktion, wenn die experimentelle Funktion aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="09510-114">Use the following syntax to declare the `Experimental` attribute providing the name of the experimental feature and the action to take if the experimental feature is enabled:</span></span>

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

<span data-ttu-id="09510-115">Für Module muss das `NameOfExperimentalFeature` die Form von befolgen `<modulename>.<experimentname>` .</span><span class="sxs-lookup"><span data-stu-id="09510-115">For modules, the `NameOfExperimentalFeature` must follow the form of `<modulename>.<experimentname>`.</span></span> <span data-ttu-id="09510-116">Der `ExperimentAction` -Parameter muss angegeben werden, und die einzigen gültigen Werte sind:</span><span class="sxs-lookup"><span data-stu-id="09510-116">The `ExperimentAction` parameter must be specified and the only valid values are:</span></span>

- <span data-ttu-id="09510-117">`Show` bedeutet, diese experimentelle Funktion anzuzeigen, wenn die Funktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="09510-117">`Show` means to show this experimental feature if the feature is enabled</span></span>
- <span data-ttu-id="09510-118">`Hide` bedeutet, diese experimentelle Funktion auszublenden, wenn die Funktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="09510-118">`Hide` means to hide this experimental feature if the feature is enabled</span></span>

### <a name="declaring-experimental-features-in-modules-written-in-c"></a><span data-ttu-id="09510-119">Deklarieren von experimentellen Features in in C geschriebenen Modulen\#</span><span class="sxs-lookup"><span data-stu-id="09510-119">Declaring Experimental Features in Modules Written in C\#</span></span>

<span data-ttu-id="09510-120">Modul Autoren, die die experimentellen Merkmals Flags verwenden möchten, können ein Cmdlet mit dem-Attribut als experimentell deklarieren `Experimental` .</span><span class="sxs-lookup"><span data-stu-id="09510-120">Module authors who want to use the Experimental Feature flags can declare a cmdlet as experimental by using the `Experimental` attribute.</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a><span data-ttu-id="09510-121">Deklarieren von experimentellen Features in in PowerShell geschriebenen Modulen</span><span class="sxs-lookup"><span data-stu-id="09510-121">Declaring Experimental Features in Modules written in PowerShell</span></span>

<span data-ttu-id="09510-122">Das in PowerShell geschriebene Modul kann auch das- `Experimental` Attribut verwenden, um experimentelle Cmdlets zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="09510-122">Module written in PowerShell can also use the `Experimental` attribute to declare experimental cmdlets:</span></span>

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a><span data-ttu-id="09510-123">Gegenseitig ausschließende experimentelle Features</span><span class="sxs-lookup"><span data-stu-id="09510-123">Mutually Exclusive Experimental Features</span></span>

<span data-ttu-id="09510-124">Es gibt Fälle, in denen eine experimentelle Funktion nicht parallel zu einer vorhandenen Funktion oder einem anderen experimentellen Feature nebeneinander vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="09510-124">There are cases where an experimental feature cannot co-exist side-by-side with an existing feature or another experimental feature.</span></span>

<span data-ttu-id="09510-125">Beispielsweise können Sie über ein experimentelles Cmdlet verfügen, das ein vorhandenes Cmdlet überschreibt.</span><span class="sxs-lookup"><span data-stu-id="09510-125">For example, you can have an experimental cmdlet that overrides an existing cmdlet.</span></span> <span data-ttu-id="09510-126">Die beiden Versionen können nicht nebeneinander nebeneinander vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="09510-126">The two versions can't coexist side by side.</span></span> <span data-ttu-id="09510-127">Mit der `ExperimentAction.Hide` Einstellung kann nur eines der beiden Cmdlets gleichzeitig aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="09510-127">The `ExperimentAction.Hide` setting allows only one of the two cmdlets to be enabled at one time.</span></span>

<span data-ttu-id="09510-128">In diesem Beispiel erstellen wir ein neues experimentelles `Invoke-WebRequest` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09510-128">In this example, we create a new experimental `Invoke-WebRequest` cmdlet.</span></span>
<span data-ttu-id="09510-129">`InvokeWebRequestCommand` enthält die nicht experimentelle Implementierung.</span><span class="sxs-lookup"><span data-stu-id="09510-129">`InvokeWebRequestCommand` contains the non-experimental implementation.</span></span>
<span data-ttu-id="09510-130">`InvokeWebRequestCommandV2` enthält die experimentelle Version des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="09510-130">`InvokeWebRequestCommandV2` contains the experimental version of the cmdlet.</span></span>

<span data-ttu-id="09510-131">Durch die Verwendung von `ExperimentAction.Hide` kann nur eine der beiden Features gleichzeitig aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="09510-131">The use of `ExperimentAction.Hide` will allow only one of the two features to be enabled at one time:</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

<span data-ttu-id="09510-132">Wenn die `MyWebCmdlets.PSWebCmdletV2` experimentelle Funktion aktiviert ist, wird die vorhandene `InvokeWebRequestCommand` Implementierung ausgeblendet, und `InvokeWebRequestCommandV2` stellt die Implementierung von bereit `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="09510-132">When the `MyWebCmdlets.PSWebCmdletV2` experimental feature is enabled, the existing `InvokeWebRequestCommand` implementation is hidden and the `InvokeWebRequestCommandV2` provides the implementation of `Invoke-WebRequest`.</span></span>

<span data-ttu-id="09510-133">Dies ermöglicht es Benutzern, das neue Cmdlet auszuprobieren und Feedback bereitzustellen und dann bei Bedarf auf die nicht experimentelle Version zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="09510-133">This allows users to try out the new cmdlet and provide feedback then revert to the non-experimental version when needed.</span></span>

### <a name="experimental-parameters-in-cmdlets"></a><span data-ttu-id="09510-134">Experimentelle Parameter in Cmdlets</span><span class="sxs-lookup"><span data-stu-id="09510-134">Experimental Parameters in Cmdlets</span></span>

<span data-ttu-id="09510-135">Das- `Experimental` Attribut kann auch auf einzelne Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="09510-135">The `Experimental` attribute can also be applied to individual parameters.</span></span> <span data-ttu-id="09510-136">Dies ermöglicht es Ihnen, einen experimentellen Satz von Parametern für ein vorhandenes Cmdlet anstelle eines vollständig neuen Cmdlets zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="09510-136">This allows you to create an experimental set of parameters for an existing cmdlet rather than an entirely new cmdlet.</span></span>

<span data-ttu-id="09510-137">Im folgenden finden Sie ein Beispiel in c#:</span><span class="sxs-lookup"><span data-stu-id="09510-137">Here is an example in C#:</span></span>

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

<span data-ttu-id="09510-138">Im folgenden finden Sie ein anderes Beispiel im PowerShell-Skript:</span><span class="sxs-lookup"><span data-stu-id="09510-138">Here is a different example in PowerShell script:</span></span>

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a><span data-ttu-id="09510-139">Es wird überprüft, ob eine experimentelle Funktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="09510-139">Checking if an Experimental Feature is Enabled</span></span>

<span data-ttu-id="09510-140">In Ihrem Code müssen Sie überprüfen, ob Ihre experimentelle Funktion aktiviert ist, bevor Sie die entsprechende Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="09510-140">In your code, you will need to check if your experimental feature is enabled before taking appropriate action.</span></span> <span data-ttu-id="09510-141">Mithilfe der statischen-Methode der-Klasse können Sie feststellen, ob eine experimentelle Funktion aktiviert ist `IsEnabled()` `System.Management.Automation.ExperimentalFeature` .</span><span class="sxs-lookup"><span data-stu-id="09510-141">You can determine if an experimental feature is enabled using the static `IsEnabled()` method on the `System.Management.Automation.ExperimentalFeature` class.</span></span>

<span data-ttu-id="09510-142">Im folgenden finden Sie ein Beispiel in c#:</span><span class="sxs-lookup"><span data-stu-id="09510-142">Here is an example in C#:</span></span>

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

<span data-ttu-id="09510-143">Im folgenden finden Sie ein Beispiel für ein PowerShell-Skript:</span><span class="sxs-lookup"><span data-stu-id="09510-143">Here is an example in PowerShell script:</span></span>

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a><span data-ttu-id="09510-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09510-144">See also</span></span>

[<span data-ttu-id="09510-145">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="09510-145">Enable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[<span data-ttu-id="09510-146">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="09510-146">Disable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[<span data-ttu-id="09510-147">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="09510-147">Get-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)

