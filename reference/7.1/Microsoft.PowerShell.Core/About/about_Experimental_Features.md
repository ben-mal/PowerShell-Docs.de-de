---
description: Die Unterstützung experimenteller Features in PowerShell stellt einen Mechanismus bereit, über den experimentelle Features und vorhandene stabile Features in PowerShell oder PowerShell-Modulen parallel genutzt werden können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen zu experimentellen Features
ms.openlocfilehash: fb13d605607b3f6daaba30cef9e7ee339221191c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222052"
---
# <a name="experimental-features"></a><span data-ttu-id="21228-104">Experimentelle Features</span><span class="sxs-lookup"><span data-stu-id="21228-104">Experimental Features</span></span>

<span data-ttu-id="21228-105">Die Unterstützung experimenteller Features in PowerShell stellt einen Mechanismus bereit, über den experimentelle Features und vorhandene stabile Features in PowerShell oder PowerShell-Modulen parallel genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="21228-105">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="21228-106">Ein experimentelles Feature ist ein Feature, dessen Design noch nicht finalisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="21228-106">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="21228-107">Das Feature wird bereitgestellt, damit die Benutzer es testen und Feedback dazu senden können.</span><span class="sxs-lookup"><span data-stu-id="21228-107">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="21228-108">Sobald ein experimentelles Feature finalisiert wurde, werden die Designänderungen zu Breaking Changes.</span><span class="sxs-lookup"><span data-stu-id="21228-108">Once an experimental feature is finalized, the design changes become breaking changes.</span></span> <span data-ttu-id="21228-109">Experimentelle Features sind nicht für den Einsatz in der Produktion vorgesehen, da Auswirkungen auf die Lauffähigkeit möglich sind.</span><span class="sxs-lookup"><span data-stu-id="21228-109">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span>

<span data-ttu-id="21228-110">Experimentelle Features sind standardmäßig deaktiviert und müssen vom Benutzer oder vom Administrator des Systems explizit aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="21228-110">Experimental features are disabled by default and need to be explicitly enabled by the user or administrator of the system.</span></span>

<span data-ttu-id="21228-111">Aktivierte experimentelle Features werden in der `powershell.config.json` Datei in `$PSHOME` für alle Benutzer oder die benutzerspezifische Konfigurationsdatei für einen bestimmten Benutzer aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="21228-111">Enabled experimental features are listed in the `powershell.config.json` file in `$PSHOME` for all users or the user-specific configuration file for a specific user.</span></span>

> [!NOTE]
> <span data-ttu-id="21228-112">Experimentelle Features, die in der Benutzer Konfigurationsdatei aktiviert sind, haben Vorrang vor experimentellen Funktionen in der System Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="21228-112">Experimental features enabled in the user configuration file take precedence over experimental features listed in the system configuration file.</span></span>

## <a name="the-experimental-attribute"></a><span data-ttu-id="21228-113">Das experimentelle Attribut</span><span class="sxs-lookup"><span data-stu-id="21228-113">The Experimental Attribute</span></span>

<span data-ttu-id="21228-114">Verwenden Sie das- `Experimental` Attribut, um Code als experimentell zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="21228-114">Use the `Experimental` attribute to declare some code as experimental.</span></span>

<span data-ttu-id="21228-115">Verwenden Sie die folgende Syntax, um das Attribut zu deklarieren, das `Experimental` den Namen des experimentellen Features und die auszuführende Aktion, wenn die experimentelle Funktion aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="21228-115">Use the following syntax to declare the `Experimental` attribute providing the name of the experimental feature and the action to take if the experimental feature is enabled:</span></span>

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

<span data-ttu-id="21228-116">Für Module muss das `NameOfExperimentalFeature` die Form von befolgen `<modulename>.<experimentname>` .</span><span class="sxs-lookup"><span data-stu-id="21228-116">For modules, the `NameOfExperimentalFeature` must follow the form of `<modulename>.<experimentname>`.</span></span> <span data-ttu-id="21228-117">Der `ExperimentAction` -Parameter muss angegeben werden, und die einzigen gültigen Werte sind:</span><span class="sxs-lookup"><span data-stu-id="21228-117">The `ExperimentAction` parameter must be specified and the only valid values are:</span></span>

- <span data-ttu-id="21228-118">`Show` bedeutet, diese experimentelle Funktion anzuzeigen, wenn die Funktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="21228-118">`Show` means to show this experimental feature if the feature is enabled</span></span>
- <span data-ttu-id="21228-119">`Hide` bedeutet, diese experimentelle Funktion auszublenden, wenn die Funktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="21228-119">`Hide` means to hide this experimental feature if the feature is enabled</span></span>

### <a name="declaring-experimental-features-in-modules-written-in-c"></a><span data-ttu-id="21228-120">Deklarieren von experimentellen Features in in C geschriebenen Modulen\#</span><span class="sxs-lookup"><span data-stu-id="21228-120">Declaring Experimental Features in Modules Written in C\#</span></span>

<span data-ttu-id="21228-121">Modul Autoren, die die experimentellen Merkmals Flags verwenden möchten, können ein Cmdlet mit dem-Attribut als experimentell deklarieren `Experimental` .</span><span class="sxs-lookup"><span data-stu-id="21228-121">Module authors who want to use the Experimental Feature flags can declare a cmdlet as experimental by using the `Experimental` attribute.</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a><span data-ttu-id="21228-122">Deklarieren von experimentellen Features in in PowerShell geschriebenen Modulen</span><span class="sxs-lookup"><span data-stu-id="21228-122">Declaring Experimental Features in Modules written in PowerShell</span></span>

<span data-ttu-id="21228-123">Das in PowerShell geschriebene Modul kann auch das- `Experimental` Attribut verwenden, um experimentelle Cmdlets zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="21228-123">Module written in PowerShell can also use the `Experimental` attribute to declare experimental cmdlets:</span></span>

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a><span data-ttu-id="21228-124">Gegenseitig ausschließende experimentelle Features</span><span class="sxs-lookup"><span data-stu-id="21228-124">Mutually Exclusive Experimental Features</span></span>

<span data-ttu-id="21228-125">Es gibt Fälle, in denen eine experimentelle Funktion nicht parallel zu einer vorhandenen Funktion oder einem anderen experimentellen Feature nebeneinander vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="21228-125">There are cases where an experimental feature cannot co-exist side-by-side with an existing feature or another experimental feature.</span></span>

<span data-ttu-id="21228-126">Beispielsweise können Sie über ein experimentelles Cmdlet verfügen, das ein vorhandenes Cmdlet überschreibt.</span><span class="sxs-lookup"><span data-stu-id="21228-126">For example, you can have an experimental cmdlet that overrides an existing cmdlet.</span></span> <span data-ttu-id="21228-127">Die beiden Versionen können nicht nebeneinander nebeneinander vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="21228-127">The two versions can't coexist side by side.</span></span> <span data-ttu-id="21228-128">Mit der `ExperimentAction.Hide` Einstellung kann nur eines der beiden Cmdlets gleichzeitig aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="21228-128">The `ExperimentAction.Hide` setting allows only one of the two cmdlets to be enabled at one time.</span></span>

<span data-ttu-id="21228-129">In diesem Beispiel erstellen wir ein neues experimentelles `Invoke-WebRequest` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="21228-129">In this example, we create a new experimental `Invoke-WebRequest` cmdlet.</span></span>
<span data-ttu-id="21228-130">`InvokeWebRequestCommand` enthält die nicht experimentelle Implementierung.</span><span class="sxs-lookup"><span data-stu-id="21228-130">`InvokeWebRequestCommand` contains the non-experimental implementation.</span></span>
<span data-ttu-id="21228-131">`InvokeWebRequestCommandV2` enthält die experimentelle Version des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="21228-131">`InvokeWebRequestCommandV2` contains the experimental version of the cmdlet.</span></span>

<span data-ttu-id="21228-132">Durch die Verwendung von `ExperimentAction.Hide` kann nur eine der beiden Features gleichzeitig aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="21228-132">The use of `ExperimentAction.Hide` will allow only one of the two features to be enabled at one time:</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

<span data-ttu-id="21228-133">Wenn die `MyWebCmdlets.PSWebCmdletV2` experimentelle Funktion aktiviert ist, wird die vorhandene `InvokeWebRequestCommand` Implementierung ausgeblendet, und `InvokeWebRequestCommandV2` stellt die Implementierung von bereit `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="21228-133">When the `MyWebCmdlets.PSWebCmdletV2` experimental feature is enabled, the existing `InvokeWebRequestCommand` implementation is hidden and the `InvokeWebRequestCommandV2` provides the implementation of `Invoke-WebRequest`.</span></span>

<span data-ttu-id="21228-134">Dies ermöglicht es Benutzern, das neue Cmdlet auszuprobieren und Feedback bereitzustellen und dann bei Bedarf auf die nicht experimentelle Version zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="21228-134">This allows users to try out the new cmdlet and provide feedback then revert to the non-experimental version when needed.</span></span>

### <a name="experimental-parameters-in-cmdlets"></a><span data-ttu-id="21228-135">Experimentelle Parameter in Cmdlets</span><span class="sxs-lookup"><span data-stu-id="21228-135">Experimental Parameters in Cmdlets</span></span>

<span data-ttu-id="21228-136">Das- `Experimental` Attribut kann auch auf einzelne Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="21228-136">The `Experimental` attribute can also be applied to individual parameters.</span></span> <span data-ttu-id="21228-137">Dies ermöglicht es Ihnen, einen experimentellen Satz von Parametern für ein vorhandenes Cmdlet anstelle eines vollständig neuen Cmdlets zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="21228-137">This allows you to create an experimental set of parameters for an existing cmdlet rather than an entirely new cmdlet.</span></span>

<span data-ttu-id="21228-138">Im folgenden finden Sie ein Beispiel in c#:</span><span class="sxs-lookup"><span data-stu-id="21228-138">Here is an example in C#:</span></span>

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

<span data-ttu-id="21228-139">Im folgenden finden Sie ein anderes Beispiel im PowerShell-Skript:</span><span class="sxs-lookup"><span data-stu-id="21228-139">Here is a different example in PowerShell script:</span></span>

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a><span data-ttu-id="21228-140">Es wird überprüft, ob eine experimentelle Funktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="21228-140">Checking if an Experimental Feature is Enabled</span></span>

<span data-ttu-id="21228-141">In Ihrem Code müssen Sie überprüfen, ob Ihre experimentelle Funktion aktiviert ist, bevor Sie die entsprechende Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="21228-141">In your code, you will need to check if your experimental feature is enabled before taking appropriate action.</span></span> <span data-ttu-id="21228-142">Mithilfe der statischen-Methode der-Klasse können Sie feststellen, ob eine experimentelle Funktion aktiviert ist `IsEnabled()` `System.Management.Automation.ExperimentalFeature` .</span><span class="sxs-lookup"><span data-stu-id="21228-142">You can determine if an experimental feature is enabled using the static `IsEnabled()` method on the `System.Management.Automation.ExperimentalFeature` class.</span></span>

<span data-ttu-id="21228-143">Im folgenden finden Sie ein Beispiel in c#:</span><span class="sxs-lookup"><span data-stu-id="21228-143">Here is an example in C#:</span></span>

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

<span data-ttu-id="21228-144">Im folgenden finden Sie ein Beispiel für ein PowerShell-Skript:</span><span class="sxs-lookup"><span data-stu-id="21228-144">Here is an example in PowerShell script:</span></span>

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a><span data-ttu-id="21228-145">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="21228-145">See also</span></span>

[<span data-ttu-id="21228-146">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="21228-146">Enable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[<span data-ttu-id="21228-147">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="21228-147">Disable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[<span data-ttu-id="21228-148">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="21228-148">Get-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)

