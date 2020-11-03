---
description: Umgebung
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Umgebungsanbieter
ms.openlocfilehash: ae98e0e8c7d1c4a7e6e975b34e4c6e18b104c01b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223879"
---
# <a name="environment-provider"></a><span data-ttu-id="b9c47-104">Umgebungs Anbieter</span><span class="sxs-lookup"><span data-stu-id="b9c47-104">Environment provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="b9c47-105">Anbietername</span><span class="sxs-lookup"><span data-stu-id="b9c47-105">Provider name</span></span>
<span data-ttu-id="b9c47-106">Environment</span><span class="sxs-lookup"><span data-stu-id="b9c47-106">Environment</span></span>

## <a name="drives"></a><span data-ttu-id="b9c47-107">Laufwerke</span><span class="sxs-lookup"><span data-stu-id="b9c47-107">Drives</span></span>

`Env:`

## <a name="capabilities"></a><span data-ttu-id="b9c47-108">Funktionen</span><span class="sxs-lookup"><span data-stu-id="b9c47-108">Capabilities</span></span>

<span data-ttu-id="b9c47-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="b9c47-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="b9c47-110">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9c47-110">Short description</span></span>

<span data-ttu-id="b9c47-111">Bietet Zugriff auf die Windows-Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="b9c47-111">Provides access to the Windows environment variables.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="b9c47-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9c47-112">Detailed description</span></span>

<span data-ttu-id="b9c47-113">Mit dem PowerShell- **Umgebungs** Anbieter können Sie Umgebungsvariablen und-Werte in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.</span><span class="sxs-lookup"><span data-stu-id="b9c47-113">The PowerShell **Environment** provider lets you get, add, change, clear, and delete environment variables and values in PowerShell.</span></span>

<span data-ttu-id="b9c47-114">**Umgebungs** Variablen sind dynamisch benannte Variablen, die die Umgebung beschreiben, in der die Programme ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9c47-114">**Environment** variables are dynamically named variables that describe the environment in which your programs run.</span></span> <span data-ttu-id="b9c47-115">Windows und PowerShell verwenden Umgebungsvariablen zum Speichern von persistenten Informationen, die sich auf die System-und Prozess Ausführung auswirken.</span><span class="sxs-lookup"><span data-stu-id="b9c47-115">Windows and PowerShell use environment variables to store persistent information that affect system and process execution.</span></span> <span data-ttu-id="b9c47-116">Im Gegensatz zu PowerShell-Variablen unterliegen Umgebungsvariablen keinen Bereichs Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="b9c47-116">Unlike PowerShell variables, environment variables are not subject to scope constraints.</span></span>

<span data-ttu-id="b9c47-117">Das **Umgebungs** Laufwerk ist ein flacher Namespace, der die Umgebungsvariablen enthält, die spezifisch für die Sitzung des aktuellen Benutzers sind.</span><span class="sxs-lookup"><span data-stu-id="b9c47-117">The **Environment** drive is a flat namespace containing the environment variables specific to the current user's session.</span></span> <span data-ttu-id="b9c47-118">Die Umgebungsvariablen haben keine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="b9c47-118">The environment variables have no child items.</span></span>

<span data-ttu-id="b9c47-119">Der **Umgebungs** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="b9c47-119">The **Environment** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="b9c47-120">Get-Location</span><span class="sxs-lookup"><span data-stu-id="b9c47-120">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="b9c47-121">Set-Location</span><span class="sxs-lookup"><span data-stu-id="b9c47-121">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="b9c47-122">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b9c47-122">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="b9c47-123">New-Item</span><span class="sxs-lookup"><span data-stu-id="b9c47-123">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="b9c47-124">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b9c47-124">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="b9c47-125">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="b9c47-125">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="b9c47-126">Von diesem Anbieter verfügbar gemachte Typen</span><span class="sxs-lookup"><span data-stu-id="b9c47-126">Types exposed by this provider</span></span>

<span data-ttu-id="b9c47-127">Jede Umgebungsvariable ist eine Instanz der Klasse [System. Collections. ditionaryentry](/dotnet/api/system.collections.dictionaryentry) .</span><span class="sxs-lookup"><span data-stu-id="b9c47-127">Each environment variable is an instance of the [System.Collections.DictionaryEntry](/dotnet/api/system.collections.dictionaryentry) class.</span></span> <span data-ttu-id="b9c47-128">Der Name der Variablen ist der Wörterbuchschlüssel.</span><span class="sxs-lookup"><span data-stu-id="b9c47-128">The name of the variable is the dictionary key.</span></span> <span data-ttu-id="b9c47-129">Der Wert der Umgebungsvariablen ist der Wörterbuchwert.</span><span class="sxs-lookup"><span data-stu-id="b9c47-129">The value of the environment variable is the dictionary value.</span></span>

## <a name="navigating-the-environment-drive"></a><span data-ttu-id="b9c47-130">Navigieren im Umgebungs Laufwerk</span><span class="sxs-lookup"><span data-stu-id="b9c47-130">Navigating the Environment drive</span></span>

<span data-ttu-id="b9c47-131">Der **Umgebungs** Anbieter stellt seinen Datenspeicher im `Env:` Laufwerk bereit.</span><span class="sxs-lookup"><span data-stu-id="b9c47-131">The **Environment** provider exposes its data store in the `Env:` drive.</span></span> <span data-ttu-id="b9c47-132">Um mit Umgebungsvariablen zu arbeiten, ändern Sie den Speicherort in das `Env:` Laufwerk ( `Set-Location Env:` ), oder arbeiten Sie von einem anderen PowerShell-Laufwerk aus.</span><span class="sxs-lookup"><span data-stu-id="b9c47-132">To work with environment variables, change your location to the `Env:` drive (`Set-Location Env:`), or work from another PowerShell drive.</span></span> <span data-ttu-id="b9c47-133">Um auf eine Umgebungsvariable von einem anderen Speicherort zu verweisen, verwenden Sie den `Env:` Laufwerks Namen im Pfad.</span><span class="sxs-lookup"><span data-stu-id="b9c47-133">To reference an environment variable from another location, use the `Env:` drive name in the path.</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="b9c47-134">Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein.</span><span class="sxs-lookup"><span data-stu-id="b9c47-134">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="b9c47-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b9c47-135">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="b9c47-136">Sie können auch mit dem **Umgebungs** Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b9c47-136">You can also work with the **Environment** provider from any other PowerShell drive.</span></span> <span data-ttu-id="b9c47-137">Um auf eine Umgebungsvariable von einem anderen Speicherort zu verweisen, verwenden Sie den Laufwerks Namen `Env:` im Pfad.</span><span class="sxs-lookup"><span data-stu-id="b9c47-137">To reference an environment variable from another location, use the drive name `Env:` in the path.</span></span>

<span data-ttu-id="b9c47-138">Der **Umgebungs** Anbieter macht auch Umgebungsvariablen mithilfe eines Variablen Präfixes von verfügbar `$env:` .</span><span class="sxs-lookup"><span data-stu-id="b9c47-138">The **Environment** provider also exposes environment variables using a variable prefix of `$env:`.</span></span>  <span data-ttu-id="b9c47-139">Mit dem folgenden Befehl wird der Inhalt der Programmier Umgebungsvariablen " **Program Files** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9c47-139">The following command views the contents of the **ProgramFiles** environment variable.</span></span> <span data-ttu-id="b9c47-140">Das `$env:` Variablen Präfix kann von jedem beliebigen PowerShell-Laufwerk verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9c47-140">The `$env:` variable prefix can be used from any PowerShell drive.</span></span>

```
PS C:\> $env:ProgramFiles
C:\Program Files
```

<span data-ttu-id="b9c47-141">Sie können auch den Wert einer Umgebungsvariablen ändern, indem Sie das `$env:` Variablen Präfix verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9c47-141">You can also change the value of an environment variable using the `$env:` variable prefix.</span></span>  <span data-ttu-id="b9c47-142">Alle vorgenommenen Änderungen beziehen sich nur auf die aktuelle PowerShell-Sitzung, solange Sie aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="b9c47-142">Any changes made only pertain to the current PowerShell session for as long as it is active.</span></span>

> [!NOTE]
> <span data-ttu-id="b9c47-143">PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten.</span><span class="sxs-lookup"><span data-stu-id="b9c47-143">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="b9c47-144">Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="b9c47-144">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="b9c47-145">und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="b9c47-145">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-environment-variables"></a><span data-ttu-id="b9c47-146">Umgebungsvariablen werden erhalten.</span><span class="sxs-lookup"><span data-stu-id="b9c47-146">Getting environment variables</span></span>

<span data-ttu-id="b9c47-147">Mit diesem Befehl werden alle Umgebungsvariablen in der aktuellen Sitzung aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="b9c47-147">This command lists all the environment variables in the current session.</span></span>

```powershell
Get-Item -Path Env:
```

<span data-ttu-id="b9c47-148">Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9c47-148">You can use this command from any PowerShell drive.</span></span>

<span data-ttu-id="b9c47-149">Der Umgebungs Anbieter hat keine Container, sodass der obige Befehl bei der Verwendung mit denselben Effekt hat `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="b9c47-149">The Environment provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Env:
```

### <a name="get-a-selected-environment-variable"></a><span data-ttu-id="b9c47-150">Ausgewählte Umgebungsvariable erhalten</span><span class="sxs-lookup"><span data-stu-id="b9c47-150">Get a selected environment variable</span></span>

<span data-ttu-id="b9c47-151">Mit diesem Befehl wird die `WINDIR` Umgebungs Variable abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b9c47-151">This command gets the `WINDIR` environment Variable.</span></span>

```powershell
Get-ChildItem -Path Env:windir
```

<span data-ttu-id="b9c47-152">Sie können auch das Variablen Präfix Format verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9c47-152">You can also use the variable prefix format as well.</span></span>

```powershell
$env:windir
```

## <a name="create-an-environment-variable"></a><span data-ttu-id="b9c47-153">Erstellen einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="b9c47-153">Create an environment variable</span></span>

<span data-ttu-id="b9c47-154">Mit diesem Befehl wird die `USERMODE` Umgebungsvariable mit dem Wert "Non-Admin" erstellt.</span><span class="sxs-lookup"><span data-stu-id="b9c47-154">This command creates the `USERMODE` environment variable with a value of "Non-Admin".</span></span> <span data-ttu-id="b9c47-155">Der `-Path` Parameterwert erstellt das neue Element im `Env:` Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="b9c47-155">The `-Path` parameter value creates the new item in the `Env:` drive.</span></span> <span data-ttu-id="b9c47-156">Die neue Umgebungsvariable kann nur in der aktuellen PowerShell-Sitzung verwendet werden, solange Sie aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="b9c47-156">The new environment variable is only usable in the current PowerShell session for as long as it is active.</span></span>

```powershell
PS C:\> New-Item -Path Env: -Name USERMODE -Value Non-Admin
```

## <a name="changing-an-environment-variable"></a><span data-ttu-id="b9c47-157">Ändern einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="b9c47-157">Changing an environment variable</span></span>

### <a name="rename-an-environment-variable"></a><span data-ttu-id="b9c47-158">Umbenennen einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="b9c47-158">Rename an environment variable</span></span>

<span data-ttu-id="b9c47-159">Dieser Befehl verwendet das `Rename-Item` Cmdlet, um den Namen der `USERMODE` Umgebungsvariablen zu ändern, die Sie in erstellt haben `USERROLE` .</span><span class="sxs-lookup"><span data-stu-id="b9c47-159">This command uses the `Rename-Item` cmdlet to change the name of the `USERMODE` environment variable that you created to `USERROLE`.</span></span> <span data-ttu-id="b9c47-160">Ändern Sie nicht den Namen einer Umgebungsvariablen, die das System verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9c47-160">Do not change the name of an environment variable that the system uses.</span></span> <span data-ttu-id="b9c47-161">Obwohl diese Änderungen nur die aktuelle Sitzung betreffen, bewirken sie möglicherweise, dass das System oder ein Programm nicht korrekt arbeitet.</span><span class="sxs-lookup"><span data-stu-id="b9c47-161">Although these changes affect only the current session, they might cause the system or a program to operate incorrectly.</span></span>

```powershell
Rename-Item -Path Env:USERMODE -NewName USERROLE
```

### <a name="change-an-environment-variable"></a><span data-ttu-id="b9c47-162">Ändern einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="b9c47-162">Change an environment variable</span></span>

<span data-ttu-id="b9c47-163">Dieser Befehl verwendet das `Set-Item` Cmdlet, um den Wert der `USERROLE` Umgebungsvariablen in "Administrator" zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b9c47-163">This command uses the `Set-Item` cmdlet to change the value of the `USERROLE` environment variable to "Administrator".</span></span>

```powershell
Set-Item -Path Env:USERROLE -Value Administrator
```

## <a name="copy-an-environment-variable"></a><span data-ttu-id="b9c47-164">Kopieren einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="b9c47-164">Copy an environment variable</span></span>

<span data-ttu-id="b9c47-165">Mit diesem Befehl wird der Wert der `USERROLE` Umgebungsvariablen in die `USERROLE2` Umgebungsvariable kopiert.</span><span class="sxs-lookup"><span data-stu-id="b9c47-165">This command copies the value of the `USERROLE` environment variable to the `USERROLE2` environment Variable.</span></span>

```powershell
Copy-Item -Path Env:USERROLE -Destination Env:USERROLE2
```

## <a name="remove-an-environment-variable"></a><span data-ttu-id="b9c47-166">Entfernen einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="b9c47-166">Remove an environment variable</span></span>

<span data-ttu-id="b9c47-167">Dieser Befehl löscht die `USERROLE2` Umgebungsvariable aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b9c47-167">This command deletes the `USERROLE2` environment variable from the current session.</span></span>

```powershell
Remove-Item -Path Env:USERROLE2
```

## <a name="remove-an-environment-variable-with-clear-item"></a><span data-ttu-id="b9c47-168">Entfernen Sie eine Umgebungsvariable mit Clear-Item</span><span class="sxs-lookup"><span data-stu-id="b9c47-168">Remove an environment variable with Clear-Item</span></span>

<span data-ttu-id="b9c47-169">Mit diesem Befehl `USERROLE` wird die Umgebungsvariable gelöscht, indem ihr Wert gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="b9c47-169">This command deletes the `USERROLE` environment variable by clearing its value.</span></span>

```powershell
Clear-Item -Path Env:USERROLE
```

## <a name="using-the-pipeline"></a><span data-ttu-id="b9c47-170">Verwenden der Pipeline</span><span class="sxs-lookup"><span data-stu-id="b9c47-170">Using the pipeline</span></span>

<span data-ttu-id="b9c47-171">Anbieter-Cmdlets akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="b9c47-171">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="b9c47-172">Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="b9c47-172">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="b9c47-173">Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="b9c47-173">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="b9c47-174">Hilfe</span><span class="sxs-lookup"><span data-stu-id="b9c47-174">Getting help</span></span>

<span data-ttu-id="b9c47-175">Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.</span><span class="sxs-lookup"><span data-stu-id="b9c47-175">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="b9c47-176">Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den `-Path` -Parameter von [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) zum Angeben eines Dateisystem Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="b9c47-176">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path env:
```

## <a name="see-also"></a><span data-ttu-id="b9c47-177">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b9c47-177">See also</span></span>

[<span data-ttu-id="b9c47-178">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b9c47-178">about_Providers</span></span>](../About/about_Providers.md)
