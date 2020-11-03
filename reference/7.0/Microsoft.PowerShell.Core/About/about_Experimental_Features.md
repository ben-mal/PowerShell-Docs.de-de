---
description: Die Unterstützung experimenteller Features in PowerShell stellt einen Mechanismus bereit, über den experimentelle Features und vorhandene stabile Features in PowerShell oder PowerShell-Modulen parallel genutzt werden können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen zu experimentellen Features
ms.openlocfilehash: e53af155c2a8691e2e4d4cc6f47bfd5932801db9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223863"
---
# <a name="experimental-features"></a>Experimentelle Features

Die Unterstützung experimenteller Features in PowerShell stellt einen Mechanismus bereit, über den experimentelle Features und vorhandene stabile Features in PowerShell oder PowerShell-Modulen parallel genutzt werden können.

Ein experimentelles Feature ist ein Feature, dessen Design noch nicht finalisiert wurde. Das Feature wird bereitgestellt, damit die Benutzer es testen und Feedback dazu senden können. Sobald ein experimentelles Feature finalisiert wurde, werden die Designänderungen zu Breaking Changes. Experimentelle Features sind nicht für den Einsatz in der Produktion vorgesehen, da Auswirkungen auf die Lauffähigkeit möglich sind.

Experimentelle Features sind standardmäßig deaktiviert und müssen vom Benutzer oder vom Administrator des Systems explizit aktiviert werden.

Aktivierte experimentelle Features werden in der `powershell.config.json` Datei in `$PSHOME` für alle Benutzer oder die benutzerspezifische Konfigurationsdatei für einen bestimmten Benutzer aufgelistet.

> [!NOTE]
> Experimentelle Features, die in der Benutzer Konfigurationsdatei aktiviert sind, haben Vorrang vor experimentellen Funktionen in der System Konfigurationsdatei.

## <a name="the-experimental-attribute"></a>Das experimentelle Attribut

Verwenden Sie das- `Experimental` Attribut, um Code als experimentell zu deklarieren.

Verwenden Sie die folgende Syntax, um das Attribut zu deklarieren, das `Experimental` den Namen des experimentellen Features und die auszuführende Aktion, wenn die experimentelle Funktion aktiviert ist:

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

Für Module muss das `NameOfExperimentalFeature` die Form von befolgen `<modulename>.<experimentname>` . Der `ExperimentAction` -Parameter muss angegeben werden, und die einzigen gültigen Werte sind:

- `Show` bedeutet, diese experimentelle Funktion anzuzeigen, wenn die Funktion aktiviert ist.
- `Hide` bedeutet, diese experimentelle Funktion auszublenden, wenn die Funktion aktiviert ist.

### <a name="declaring-experimental-features-in-modules-written-in-c"></a>Deklarieren von experimentellen Features in in C geschriebenen Modulen\#

Modul Autoren, die die experimentellen Merkmals Flags verwenden möchten, können ein Cmdlet mit dem-Attribut als experimentell deklarieren `Experimental` .

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a>Deklarieren von experimentellen Features in in PowerShell geschriebenen Modulen

Das in PowerShell geschriebene Modul kann auch das- `Experimental` Attribut verwenden, um experimentelle Cmdlets zu deklarieren:

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a>Gegenseitig ausschließende experimentelle Features

Es gibt Fälle, in denen eine experimentelle Funktion nicht parallel zu einer vorhandenen Funktion oder einem anderen experimentellen Feature nebeneinander vorhanden sein kann.

Beispielsweise können Sie über ein experimentelles Cmdlet verfügen, das ein vorhandenes Cmdlet überschreibt. Die beiden Versionen können nicht nebeneinander nebeneinander vorhanden sein. Mit der `ExperimentAction.Hide` Einstellung kann nur eines der beiden Cmdlets gleichzeitig aktiviert werden.

In diesem Beispiel erstellen wir ein neues experimentelles `Invoke-WebRequest` Cmdlet.
`InvokeWebRequestCommand` enthält die nicht experimentelle Implementierung.
`InvokeWebRequestCommandV2` enthält die experimentelle Version des Cmdlets.

Durch die Verwendung von `ExperimentAction.Hide` kann nur eine der beiden Features gleichzeitig aktiviert werden:

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

Wenn die `MyWebCmdlets.PSWebCmdletV2` experimentelle Funktion aktiviert ist, wird die vorhandene `InvokeWebRequestCommand` Implementierung ausgeblendet, und `InvokeWebRequestCommandV2` stellt die Implementierung von bereit `Invoke-WebRequest` .

Dies ermöglicht es Benutzern, das neue Cmdlet auszuprobieren und Feedback bereitzustellen und dann bei Bedarf auf die nicht experimentelle Version zurückzukehren.

### <a name="experimental-parameters-in-cmdlets"></a>Experimentelle Parameter in Cmdlets

Das- `Experimental` Attribut kann auch auf einzelne Parameter angewendet werden. Dies ermöglicht es Ihnen, einen experimentellen Satz von Parametern für ein vorhandenes Cmdlet anstelle eines vollständig neuen Cmdlets zu erstellen.

Im folgenden finden Sie ein Beispiel in c#:

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

Im folgenden finden Sie ein anderes Beispiel im PowerShell-Skript:

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a>Es wird überprüft, ob eine experimentelle Funktion aktiviert ist.

In Ihrem Code müssen Sie überprüfen, ob Ihre experimentelle Funktion aktiviert ist, bevor Sie die entsprechende Aktion ausführen. Mithilfe der statischen-Methode der-Klasse können Sie feststellen, ob eine experimentelle Funktion aktiviert ist `IsEnabled()` `System.Management.Automation.ExperimentalFeature` .

Im folgenden finden Sie ein Beispiel in c#:

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

Im folgenden finden Sie ein Beispiel für ein PowerShell-Skript:

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a>Weitere Informationen:

[Enable-ExperimentalFeature](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[Disable-ExperimentalFeature](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[Get-ExperimentalFeature](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)
