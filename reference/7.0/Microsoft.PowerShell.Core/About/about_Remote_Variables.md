---
description: Erläutert die Verwendung von lokalen und Remotevariablen in Remotebefehlen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Variables
ms.openlocfilehash: 2260e1a6ba4553cbdba0057972f491d17c61382d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223735"
---
# <a name="about-remote-variables"></a><span data-ttu-id="4c25d-104">Informationen zu Remote Variablen</span><span class="sxs-lookup"><span data-stu-id="4c25d-104">About Remote Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="4c25d-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c25d-105">Short description</span></span>

<span data-ttu-id="4c25d-106">Erläutert die Verwendung von lokalen und Remotevariablen in Remotebefehlen.</span><span class="sxs-lookup"><span data-stu-id="4c25d-106">Explains how to use local and remote variables in remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="4c25d-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c25d-107">Long description</span></span>

<span data-ttu-id="4c25d-108">Sie können Variablen in Befehlen verwenden, die Sie auf Remote Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="4c25d-108">You can use variables in commands that you run on remote computers.</span></span> <span data-ttu-id="4c25d-109">Weisen Sie der Variablen einen Wert zu, und verwenden Sie dann die Variable anstelle des Werts.</span><span class="sxs-lookup"><span data-stu-id="4c25d-109">Assign a value to the variable and then use the variable in place of the value.</span></span>

<span data-ttu-id="4c25d-110">Standardmäßig wird davon ausgegangen, dass die Variablen in Remote Befehlen in der Sitzung definiert werden, die den Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="4c25d-110">By default, the variables in remote commands are assumed to be defined in the session that runs the command.</span></span> <span data-ttu-id="4c25d-111">Variablen, die in einer lokalen Sitzung definiert sind, müssen im Befehl als lokale Variablen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="4c25d-111">Variables that are defined in a local session, must be identified as local variables in the command.</span></span>

## <a name="using-remote-variables"></a><span data-ttu-id="4c25d-112">Verwenden von Remote Variablen</span><span class="sxs-lookup"><span data-stu-id="4c25d-112">Using remote variables</span></span>

<span data-ttu-id="4c25d-113">PowerShell geht davon aus, dass die in Remote Befehlen verwendeten Variablen in der Sitzung definiert sind, in der der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4c25d-113">PowerShell assumes that the variables used in remote commands are defined in the session in which the command runs.</span></span>

<span data-ttu-id="4c25d-114">In diesem Beispiel wird die `$ps` Variable in der temporären Sitzung definiert, in der der `Get-WinEvent` Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4c25d-114">In this example, the `$ps` variable is defined in the temporary session in which the `Get-WinEvent` command runs.</span></span>

```powershell
Invoke-Command -ComputerName S1 -ScriptBlock {
  $ps = "*PowerShell*"; Get-WinEvent -LogName $ps
}
```

<span data-ttu-id="4c25d-115">Wenn der Befehl in einer persistenten Sitzung ( **PSSession** ) ausgeführt wird, muss die Remote Variable in dieser Sitzung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4c25d-115">When the command runs in a persistent session, **PSSession** , the remote variable must be defined in that session.</span></span>

```powershell
$s = New-PSSession -ComputerName S1
Invoke-Command -Session $s -ScriptBlock {$ps = "*PowerShell*"}
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $ps}
```

## <a name="using-local-variables"></a><span data-ttu-id="4c25d-116">Verwenden lokaler Variablen</span><span class="sxs-lookup"><span data-stu-id="4c25d-116">Using local variables</span></span>

<span data-ttu-id="4c25d-117">Sie können lokale Variablen in Remote Befehlen verwenden, aber die Variable muss in der lokalen Sitzung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4c25d-117">You can use local variables in remote commands, but the variable must be defined in the local session.</span></span>

<span data-ttu-id="4c25d-118">Ab PowerShell 3,0 können Sie den bereichsmodifizierer verwenden, `Using` um eine lokale Variable in einem Remote Befehl zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4c25d-118">Beginning in PowerShell 3.0, you can use the `Using` scope modifier to identify a local variable in a remote command.</span></span>

<span data-ttu-id="4c25d-119">Die Syntax von `Using` lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4c25d-119">The syntax of `Using` is as follows:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="4c25d-120">Im folgenden Beispiel `$ps` wird die Variable in der lokalen Sitzung erstellt, aber in der Sitzung verwendet, in der der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4c25d-120">In the following example, the `$ps` variable is created in the local session, but is used in the session in which the command runs.</span></span> <span data-ttu-id="4c25d-121">Der bereichsmodifizierer `Using` identifiziert `$ps` als lokale Variable.</span><span class="sxs-lookup"><span data-stu-id="4c25d-121">The `Using` scope modifier identifies `$ps` as a local variable.</span></span>

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  Get-WinEvent -LogName $Using:ps
}
```

<span data-ttu-id="4c25d-122">Der bereichsmodifizierer `Using` kann in einer **PSSession** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c25d-122">The `Using` scope modifier can be used in a **PSSession**.</span></span>

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $Using:ps}
```

<span data-ttu-id="4c25d-123">Ein Variablen Verweis, z `$using:var` . b., wird auf den Wert der Variablen `$var` aus dem Kontext des Aufrufers erweitert.</span><span class="sxs-lookup"><span data-stu-id="4c25d-123">A variable reference such as `$using:var` expands to the value of variable `$var` from the caller's context.</span></span> <span data-ttu-id="4c25d-124">Sie erhalten keinen Zugriff auf das Variablen Objekt des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="4c25d-124">You do not get access to the caller's variable object.</span></span>
<span data-ttu-id="4c25d-125">Der `Using` bereichsmodifizierer kann nicht verwendet werden, um eine lokale Variable innerhalb der **PSSession** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4c25d-125">The `Using` scope modifier cannot be used to modify a local variable within the **PSSession**.</span></span> <span data-ttu-id="4c25d-126">Der folgende Code kann beispielsweise nicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4c25d-126">For example, the following code does not work:</span></span>

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {$Using:ps = 'Cannot assign new value'}
```

<span data-ttu-id="4c25d-127">Weitere Informationen zu `Using` finden Sie unter [about_Scopes](./about_Scopes.md)</span><span class="sxs-lookup"><span data-stu-id="4c25d-127">For more information about `Using`, see [about_Scopes](./about_Scopes.md)</span></span>

### <a name="using-splatting"></a><span data-ttu-id="4c25d-128">Verwenden von Verteilung</span><span class="sxs-lookup"><span data-stu-id="4c25d-128">Using splatting</span></span>

<span data-ttu-id="4c25d-129">PowerShell-Verteilung übergibt eine Auflistung von Parameternamen und-Werten an einen Befehl.</span><span class="sxs-lookup"><span data-stu-id="4c25d-129">PowerShell splatting passes a collection of parameter names and values to a command.</span></span> <span data-ttu-id="4c25d-130">Weitere Informationen finden Sie unter [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="4c25d-130">For more information, see [about_Splatting](about_Splatting.md).</span></span>

<span data-ttu-id="4c25d-131">In diesem Beispiel ist die Verteilung-Variable `$Splat` eine Hash Tabelle, die auf dem lokalen Computer eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="4c25d-131">In this example, the splatting variable, `$Splat` is a hash table that is set up on the local computer.</span></span> <span data-ttu-id="4c25d-132">Der stellt `Invoke-Command` eine Verbindung mit einer Remote Computersitzung her.</span><span class="sxs-lookup"><span data-stu-id="4c25d-132">The `Invoke-Command` connects to a remote computer session.</span></span> <span data-ttu-id="4c25d-133">Der **ScriptBlock** verwendet den `Using` bereichsmodifizierer mit dem at- `@` Symbol (), um die splatted-Variable darzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c25d-133">The **ScriptBlock** uses the `Using` scope modifier with the At (`@`) symbol to represent the splatted variable.</span></span>

```powershell
$Splat = @{ Name = "Win*"; Include = "WinRM" }
Invoke-Command -Session $s -ScriptBlock { Get-Service @Using:Splat }
```

### <a name="other-situations-where-the-using-scope-modifier-is-needed"></a><span data-ttu-id="4c25d-134">Andere Situationen, in denen der Bereichs Modifizierer "using" benötigt wird</span><span class="sxs-lookup"><span data-stu-id="4c25d-134">Other situations where the 'Using' scope modifier is needed</span></span>

<span data-ttu-id="4c25d-135">Für Skripts oder Befehle, die außerhalb der Sitzung ausgeführt werden, müssen Sie den bereichsmodifizierer `Using` zum Einbetten von Variablen Werten aus dem aufrufenden Sitzungs Bereich benötigen, damit der Sitzungscode darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="4c25d-135">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="4c25d-136">Der bereichsmodifizierer `Using` wird in den folgenden Kontexten unterstützt:</span><span class="sxs-lookup"><span data-stu-id="4c25d-136">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="4c25d-137">Remote ausgeführte Befehle, gestartet mit mit `Invoke-Command` den Parametern **Computername** , **Hostname** , **SshConnection** oder **Session** (Remote Sitzung)</span><span class="sxs-lookup"><span data-stu-id="4c25d-137">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** , **HostName** , **SSHConnection** or **Session** parameters (remote session)</span></span>
- <span data-ttu-id="4c25d-138">Hintergrund Aufträge, gestartet mit `Start-Job` (Out-of-Process-Sitzung)</span><span class="sxs-lookup"><span data-stu-id="4c25d-138">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="4c25d-139">Thread Aufträge, gestartet über `Start-ThreadJob` oder `ForEach-Object -Parallel` (separate Thread Sitzung)</span><span class="sxs-lookup"><span data-stu-id="4c25d-139">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="4c25d-140">Abhängig vom Kontext sind eingebettete Variablen Werte entweder unabhängige Kopien der Daten im Gültigkeitsbereich des Aufrufers oder Verweise darauf.</span><span class="sxs-lookup"><span data-stu-id="4c25d-140">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="4c25d-141">In Remote-und Out-of-Process-Sitzungen sind Sie immer unabhängige Kopien.</span><span class="sxs-lookup"><span data-stu-id="4c25d-141">In remote and out-of-process sessions, they are always independent copies.</span></span> <span data-ttu-id="4c25d-142">In Thread Sitzungen werden Sie als Verweis übermittelt.</span><span class="sxs-lookup"><span data-stu-id="4c25d-142">In thread sessions, they are passed by reference.</span></span>

## <a name="serialization-of-variable-values"></a><span data-ttu-id="4c25d-143">Serialisierung von Variablen Werten</span><span class="sxs-lookup"><span data-stu-id="4c25d-143">Serialization of variable values</span></span>

<span data-ttu-id="4c25d-144">Remote ausgeführte Befehle und Hintergrund Aufträge werden außerhalb des Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4c25d-144">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="4c25d-145">Out-of-Process-Sitzungen verwenden die XML-basierte Serialisierung und Deserialisierung, um die Werte der Variablen über die Prozess Grenzen hinweg verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="4c25d-145">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="4c25d-146">Der Serialisierungsprozess konvertiert Objekte in ein **psobject** -Objekt, das die ursprünglichen Objekteigenschaften, aber nicht die zugehörigen Methoden enthält.</span><span class="sxs-lookup"><span data-stu-id="4c25d-146">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="4c25d-147">Bei einer begrenzten Menge von Typen werden Objekte von der Deserialisierung zurück auf den ursprünglichen Typ zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4c25d-147">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="4c25d-148">Das rehydrierte Objekt ist eine Kopie der ursprünglichen Objektinstanz.</span><span class="sxs-lookup"><span data-stu-id="4c25d-148">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="4c25d-149">Es verfügt über die Typeigenschaften und-Methoden.</span><span class="sxs-lookup"><span data-stu-id="4c25d-149">It has the type properties and methods.</span></span> <span data-ttu-id="4c25d-150">Bei einfachen Typen, wie z. b **. System. Version** , ist die Kopie exakt.</span><span class="sxs-lookup"><span data-stu-id="4c25d-150">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="4c25d-151">Bei komplexen Typen ist die Kopie nicht perfekt.</span><span class="sxs-lookup"><span data-stu-id="4c25d-151">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="4c25d-152">Beispielsweise enthalten die von einem Zertifikat bereit erten Zertifikat Objekte nicht den privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="4c25d-152">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="4c25d-153">Instanzen aller anderen Typen sind **psobject** -Instanzen.</span><span class="sxs-lookup"><span data-stu-id="4c25d-153">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="4c25d-154">Die **pstypames** -Eigenschaft enthält den ursprünglichen Typnamen, dem die **Deserialisierung** vorangestellt ist, z **. b.Deserialized.System. Data. datdatababel**</span><span class="sxs-lookup"><span data-stu-id="4c25d-154">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

## <a name="using-local-variables-with-argumentlist-parameter"></a><span data-ttu-id="4c25d-155">Verwenden von lokalen Variablen mit Argument **List** -Parametern</span><span class="sxs-lookup"><span data-stu-id="4c25d-155">Using local variables with **ArgumentList** parameter</span></span>

<span data-ttu-id="4c25d-156">Sie können lokale Variablen in einem Remote Befehl verwenden, indem Sie Parameter für den Remote Befehl definieren und den Argument **List** -Parameter des `Invoke-Command` Cmdlets verwenden, um die lokale Variable als Parameterwert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4c25d-156">You can use local variables in a remote command by defining parameters for the remote command and using the **ArgumentList** parameter of the `Invoke-Command` cmdlet to specify the local variable as the parameter value.</span></span>

- <span data-ttu-id="4c25d-157">Verwenden Sie das- `param` Schlüsselwort, um Parameter für den Remote Befehl zu definieren.</span><span class="sxs-lookup"><span data-stu-id="4c25d-157">Use the `param` keyword to define parameters for the remote command.</span></span> <span data-ttu-id="4c25d-158">Die Parameternamen sind Platzhalter, die nicht mit dem Namen der lokalen Variablen abgeglichen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4c25d-158">The parameter names are placeholders that don't need to match the local variable's name.</span></span>

- <span data-ttu-id="4c25d-159">Verwenden Sie die Parameter, die vom- `param` Schlüsselwort im-Befehl definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4c25d-159">Use the parameters defined by the `param` keyword in the command.</span></span>

- <span data-ttu-id="4c25d-160">Verwenden Sie den Argument **List** -Parameter des `Invoke-Command` Cmdlets, um die lokale Variable als Parameterwert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4c25d-160">Use the **ArgumentList** parameter of the `Invoke-Command` cmdlet to specify the local variable as the parameter value.</span></span>

<span data-ttu-id="4c25d-161">Die folgenden Befehle definieren z `$ps` . b. die Variable in der lokalen Sitzung und verwenden Sie dann in einem Remote Befehl.</span><span class="sxs-lookup"><span data-stu-id="4c25d-161">For example, the following commands define the `$ps` variable in the local session and then use it in a remote command.</span></span> <span data-ttu-id="4c25d-162">Der Befehl verwendet `$log` als Parameternamen und die lokale Variable, `$ps` , als Wert.</span><span class="sxs-lookup"><span data-stu-id="4c25d-162">The command uses `$log` as the parameter name and the local variable, `$ps`, as its value.</span></span>

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  param($log)
  Get-WinEvent -LogName $log
} -ArgumentList $ps
```

## <a name="see-also"></a><span data-ttu-id="4c25d-163">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="4c25d-163">See also</span></span>

[<span data-ttu-id="4c25d-164">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="4c25d-164">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="4c25d-165">about_Remote</span><span class="sxs-lookup"><span data-stu-id="4c25d-165">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="4c25d-166">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="4c25d-166">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="4c25d-167">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="4c25d-167">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="4c25d-168">about_Variables</span><span class="sxs-lookup"><span data-stu-id="4c25d-168">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="4c25d-169">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="4c25d-169">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="4c25d-170">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="4c25d-170">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="4c25d-171">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="4c25d-171">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="4c25d-172">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="4c25d-172">Start-ThreadJob</span></span>](xref:ThreadJob.Start-ThreadJob)

[<span data-ttu-id="4c25d-173">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="4c25d-173">ForEach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
