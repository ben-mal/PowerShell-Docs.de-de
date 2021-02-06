---
description: Alias
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_alias_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Aliasanbieter
ms.openlocfilehash: d6bfbaf878a6d971b1e01d963faec8c8ece5d1fc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599215"
---
# <a name="alias-provider"></a><span data-ttu-id="e8f8a-103">Alias Anbieter</span><span class="sxs-lookup"><span data-stu-id="e8f8a-103">Alias provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="e8f8a-104">Anbietername</span><span class="sxs-lookup"><span data-stu-id="e8f8a-104">Provider name</span></span>
<span data-ttu-id="e8f8a-105">Alias</span><span class="sxs-lookup"><span data-stu-id="e8f8a-105">Alias</span></span>

## <a name="drives"></a><span data-ttu-id="e8f8a-106">Laufwerke</span><span class="sxs-lookup"><span data-stu-id="e8f8a-106">Drives</span></span>

`Alias:`

## <a name="capabilities"></a><span data-ttu-id="e8f8a-107">Funktionen</span><span class="sxs-lookup"><span data-stu-id="e8f8a-107">Capabilities</span></span>

<span data-ttu-id="e8f8a-108">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="e8f8a-108">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="e8f8a-109">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8f8a-109">Short description</span></span>

<span data-ttu-id="e8f8a-110">Bietet Zugriff auf die PowerShell-Aliase und die Werte, die Sie darstellen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-110">Provides access to the PowerShell aliases and the values that they represent.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="e8f8a-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8f8a-111">Detailed description</span></span>

<span data-ttu-id="e8f8a-112">Mit dem PowerShell- **Alias** Anbieter können Sie Aliase in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-112">The PowerShell **Alias** provider lets you get, add, change, clear, and delete aliases in PowerShell.</span></span>

<span data-ttu-id="e8f8a-113">Ein Alias ist ein alternativer Name für ein Cmdlet, eine Funktion, eine ausführbare Datei, einschließlich Skripts.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-113">An alias is an alternate name for a cmdlet, function, executable file, including scripts.</span></span> <span data-ttu-id="e8f8a-114">PowerShell enthält eine Reihe integrierter Aliase.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-114">PowerShell includes a set of built-in aliases.</span></span> <span data-ttu-id="e8f8a-115">Sie können Ihrer aktuellen Sitzung und Ihrem PowerShell-Profil eigene Aliase hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-115">You can add your own aliases to the current session and to your PowerShell profile.</span></span>

<span data-ttu-id="e8f8a-116">Das **Alias** Laufwerk ist ein flacher Namespace, der nur die Alias Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-116">The **Alias** drive is a flat namespace that contains only the alias objects.</span></span>
<span data-ttu-id="e8f8a-117">Die Aliase haben keine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-117">The aliases have no child items.</span></span>

<span data-ttu-id="e8f8a-118">Der **Alias** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-118">The **Alias** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="e8f8a-119">Get-Location</span><span class="sxs-lookup"><span data-stu-id="e8f8a-119">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="e8f8a-120">Set-Location</span><span class="sxs-lookup"><span data-stu-id="e8f8a-120">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="e8f8a-121">Get-Item</span><span class="sxs-lookup"><span data-stu-id="e8f8a-121">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="e8f8a-122">New-Item</span><span class="sxs-lookup"><span data-stu-id="e8f8a-122">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="e8f8a-123">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="e8f8a-123">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="e8f8a-124">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="e8f8a-124">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

<span data-ttu-id="e8f8a-125">PowerShell umfasst einen Satz von Cmdlets, die zum Anzeigen und Ändern von Aliasen entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-125">PowerShell includes a set of cmdlets that are designed to view and to change aliases.</span></span> <span data-ttu-id="e8f8a-126">Wenn Sie **Alias** -Cmdlets verwenden, müssen Sie nicht das `Alias:` Laufwerk im Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-126">When you use **Alias** cmdlets, you do not need to specify the `Alias:` drive in the name.</span></span> <span data-ttu-id="e8f8a-127">In diesem Artikel wird das Arbeiten mit **Alias** -Cmdlets nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-127">This article does not cover working with **Alias** cmdlets.</span></span>

- [<span data-ttu-id="e8f8a-128">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="e8f8a-128">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="e8f8a-129">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="e8f8a-129">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="e8f8a-130">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="e8f8a-130">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="e8f8a-131">New-Alias</span><span class="sxs-lookup"><span data-stu-id="e8f8a-131">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="e8f8a-132">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="e8f8a-132">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="e8f8a-133">Von diesem Anbieter verfügbar gemachte Typen</span><span class="sxs-lookup"><span data-stu-id="e8f8a-133">Types exposed by this provider</span></span>

<span data-ttu-id="e8f8a-134">Jeder Alias ist eine Instanz der [System. Management. Automation. AliasInfo](/dotnet/api/system.management.automation.aliasinfo) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-134">Each alias is an instance of the [System.Management.Automation.AliasInfo](/dotnet/api/system.management.automation.aliasinfo) class.</span></span>

## <a name="navigating-the-alias-drive"></a><span data-ttu-id="e8f8a-135">Navigieren im Alias Laufwerk</span><span class="sxs-lookup"><span data-stu-id="e8f8a-135">Navigating the Alias drive</span></span>

<span data-ttu-id="e8f8a-136">Der **Alias** Anbieter stellt seinen Datenspeicher im `Alias:` Laufwerk bereit.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-136">The **Alias** provider exposes its data store in the `Alias:` drive.</span></span> <span data-ttu-id="e8f8a-137">Um mit Aliasen zu arbeiten, können Sie den Speicherort auf das Laufwerk ändern, `Alias:` indem Sie den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="e8f8a-137">To work with aliases, you can change your location to the `Alias:` drive by using the following command:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="e8f8a-138">Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-138">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="e8f8a-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8f8a-139">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="e8f8a-140">Sie können auch mit dem Alias Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-140">You can also work with the Alias provider from any other PowerShell drive.</span></span> <span data-ttu-id="e8f8a-141">Um auf einen Alias von einem anderen Speicherort zu verweisen, verwenden Sie den `Alias:` Namen des Laufwerks im Pfad.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-141">To reference an alias from another location, use the `Alias:` drive name in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="e8f8a-142">PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-142">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="e8f8a-143">Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="e8f8a-143">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="e8f8a-144">und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="e8f8a-144">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

### <a name="displaying-the-contents-of-the-alias-drive"></a><span data-ttu-id="e8f8a-145">Anzeigen des Inhalts des Alias:-Laufwerks</span><span class="sxs-lookup"><span data-stu-id="e8f8a-145">Displaying the Contents of the Alias: drive</span></span>

<span data-ttu-id="e8f8a-146">Mit diesem Befehl wird die Liste aller Aliase abgerufen, wenn der aktuelle Speicherort das `Alias:` Laufwerk ist.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-146">This command gets the list of all the aliases when the current location is the `Alias:` drive.</span></span> <span data-ttu-id="e8f8a-147">Es verwendet ein Platzhalter Zeichen `*` , um den gesamten Inhalt des aktuellen Speicher Orts anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-147">It uses a wildcard character `*` to indicate all the contents of the current location.</span></span>

```powershell
PS Alias:\> Get-Item -Path *
```

<span data-ttu-id="e8f8a-148">Im `Alias:` Laufwerk haben Sie einen Punkt `.` , der den aktuellen Speicherort darstellt, und ein Platzhalter Zeichen `*` , das alle Elemente am aktuellen Speicherort darstellt.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-148">In the `Alias:` drive, a dot `.`, which represents the current location, and a wildcard character `*`, which represents all items in the current location, have the same effect.</span></span> <span data-ttu-id="e8f8a-149">Beispielsweise, `Get-Item -Path .` oder `Get-Item \*` führen Sie das gleiche Ergebnis aus.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-149">For example, `Get-Item -Path .` or `Get-Item \*` produce the same result.</span></span>

<span data-ttu-id="e8f8a-150">Der Alias Anbieter hat keine Container, sodass der obige Befehl bei der Verwendung mit dieselbe Auswirkung hat `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="e8f8a-150">The Alias provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Alias:
```

### <a name="get-a-selected-alias"></a><span data-ttu-id="e8f8a-151">Ausgewählten Alias erhalten</span><span class="sxs-lookup"><span data-stu-id="e8f8a-151">Get a selected alias</span></span>

<span data-ttu-id="e8f8a-152">Mit diesem Befehl wird der `ls` Alias abgerufen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-152">This command gets the `ls` alias.</span></span>
<span data-ttu-id="e8f8a-153">Da Sie den Pfad enthält, können Sie ihn in jedem beliebigen PowerShell-Laufwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-153">Because it includes the path, you can use it in any PowerShell drive.</span></span>

```powershell
Get-Item -Path Alias:ls
```

<span data-ttu-id="e8f8a-154">Wenn Sie sich auf dem `Alias:` Laufwerk befinden, können Sie den Namen des Laufwerks aus dem Pfad weglassen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-154">If you are in the `Alias:` drive, you can omit the drive name from the path.</span></span>

<span data-ttu-id="e8f8a-155">Sie können die Definition für einen Alias auch abrufen, indem Sie dem Anbieter Pfad das Dollarzeichen () voranstellen `$` .</span><span class="sxs-lookup"><span data-stu-id="e8f8a-155">You can also retrieve the definition for an alias by prefixing the provider path with the dollar sign (`$`).</span></span>

```powershell
$Alias:ls
```

### <a name="get-all-aliases-for-a-specific-cmdlet"></a><span data-ttu-id="e8f8a-156">Alle Aliase für ein bestimmtes Cmdlet erhalten</span><span class="sxs-lookup"><span data-stu-id="e8f8a-156">Get all aliases for a specific cmdlet</span></span>

<span data-ttu-id="e8f8a-157">Mit diesem Befehl wird eine Liste der Aliase abgerufen, die dem `Get-ChildItem` Cmdlet zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-157">This command gets a list of the aliases that are associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="e8f8a-158">Er verwendet die **Definition** -Eigenschaft, die den Cmdlet-Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-158">It uses the **Definition** property, which stores the cmdlet name.</span></span>

```powershell
Get-Item -Path Alias:* | Where-Object {$_.Definition -eq "Get-ChildItem"}
```

## <a name="creating-aliases"></a><span data-ttu-id="e8f8a-159">Erstellen von Aliasen</span><span class="sxs-lookup"><span data-stu-id="e8f8a-159">Creating aliases</span></span>

### <a name="create-an-alias-from-the-alias-drive"></a><span data-ttu-id="e8f8a-160">Erstellen eines Alias über das Alias:-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="e8f8a-160">Create an alias from the Alias: drive</span></span>

<span data-ttu-id="e8f8a-161">Mit diesem Befehl wird der `serv` Alias für das `Get-Service` Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-161">This command creates the `serv` alias for the `Get-Service` cmdlet.</span></span> <span data-ttu-id="e8f8a-162">Da sich der aktuelle Speicherort im `Alias:` Laufwerk befindet, `-Path` wird der-Parameter nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-162">Because the current location is in the `Alias:` drive, the `-Path` parameter is not needed.</span></span>

<span data-ttu-id="e8f8a-163">Dieser Befehl verwendet außerdem den `-Options` Dynamic-Parameter, um die **allscope** -Option für den Alias festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-163">This command also uses the `-Options` dynamic parameter to set the **AllScope** option on the alias.</span></span> <span data-ttu-id="e8f8a-164">Der- `-Options` Parameter ist nur im- `New-Item` Cmdlet verfügbar, wenn Sie sich auf dem- `Alias:` Laufwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-164">The `-Options` parameter is available in the `New-Item` cmdlet only when you are in the `Alias:` drive.</span></span> <span data-ttu-id="e8f8a-165">Der Punkt ( `.` ) gibt das aktuelle Verzeichnis an, das das Alias Laufwerk ist.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-165">The dot (`.`) indicates the current directory, which is the alias drive.</span></span>

```
PS Alias:\> New-Item -Path . -Name serv -Value Get-Service -Options "AllScope"
```

### <a name="create-an-alias-with-an-absolute-path"></a><span data-ttu-id="e8f8a-166">Einen Alias mit einem absoluten Pfad erstellen</span><span class="sxs-lookup"><span data-stu-id="e8f8a-166">Create an alias with an absolute path</span></span>

<span data-ttu-id="e8f8a-167">Sie können einen Alias für jedes Element erstellen, das einen Befehl aufruft.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-167">You can create an alias for any item that invokes a command.</span></span>
<span data-ttu-id="e8f8a-168">Mit diesem Befehl wird der `np` Alias für erstellt `Notepad.exe` .</span><span class="sxs-lookup"><span data-stu-id="e8f8a-168">This command creates the `np` alias for `Notepad.exe`.</span></span>

```powershell
New-Item -Path Alias:np -Value c:\windows\notepad.exe
```

### <a name="create-an-alias-to-a-new-function"></a><span data-ttu-id="e8f8a-169">Erstellen eines Alias für eine neue Funktion</span><span class="sxs-lookup"><span data-stu-id="e8f8a-169">Create an alias to a new function</span></span>

<span data-ttu-id="e8f8a-170">Sie können einen Alias für jede Funktion erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-170">You can create an alias for any function.</span></span> <span data-ttu-id="e8f8a-171">Mit diesem Feature können Sie einen Alias erstellen, der ein Cmdlet und die entsprechenden Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-171">You can use this feature to create an alias that includes both a cmdlet and its parameters.</span></span>

<span data-ttu-id="e8f8a-172">Der erste Befehl erstellt die- `CD32` Funktion, die das aktuelle Verzeichnis in das `System32` Verzeichnis ändert.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-172">The first command creates the `CD32` function, which changes the current directory to the `System32` directory.</span></span> <span data-ttu-id="e8f8a-173">Mit dem zweiten Befehl wird der `go` Alias für die `CD32` Funktion erstellt.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-173">The second command creates the `go` alias for the `CD32` function.</span></span>

<span data-ttu-id="e8f8a-174">Wenn der Befehl fertig ist, können Sie entweder oder verwenden, `CD32` `go` um die Funktion aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-174">When the command is complete, you can use either `CD32` or `go` to invoke the function.</span></span>

```powershell
function CD32 {Set-Location -Path c:\windows\system32}
Set-Item -Path Alias:go -Value CD32
```

## <a name="changing-aliases"></a><span data-ttu-id="e8f8a-175">Ändern von Aliasen</span><span class="sxs-lookup"><span data-stu-id="e8f8a-175">Changing aliases</span></span>

### <a name="change-the-options-of-an-alias"></a><span data-ttu-id="e8f8a-176">Ändern der Optionen eines Alias</span><span class="sxs-lookup"><span data-stu-id="e8f8a-176">Change the options of an alias</span></span>

<span data-ttu-id="e8f8a-177">Sie können das `Set-Item` Cmdlet mit dem `-Options` dynamischen Parameter verwenden, um den Wert der- `-Options` Eigenschaft eines Alias zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-177">You can use the `Set-Item` cmdlet with the `-Options` dynamic parameter to change the value of the `-Options` property of an alias.</span></span>

<span data-ttu-id="e8f8a-178">Dieser Befehl legt die Optionen " **allscope** " und "read **only** " für den `dir` Alias fest.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-178">This command sets the **AllScope** and **ReadOnly** options for the `dir` alias.</span></span> <span data-ttu-id="e8f8a-179">Der Befehl verwendet den `-Options` dynamischen Parameter des `Set-Item` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-179">The command uses the `-Options` dynamic parameter of the `Set-Item` cmdlet.</span></span> <span data-ttu-id="e8f8a-180">Der- `-Options` Parameter ist in verfügbar, `Set-Item` Wenn er mit dem **Alias** -oder **Funktions** Anbieter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-180">The `-Options` parameter is available in `Set-Item` when you use it with the **Alias** or **Function** provider.</span></span>

```powershell
Set-Item -Path Alias:dir -Options "AllScope,ReadOnly"
```

### <a name="change-an-aliases-referenced-command"></a><span data-ttu-id="e8f8a-181">Ändern eines referenzierten Aliase-Befehls</span><span class="sxs-lookup"><span data-stu-id="e8f8a-181">Change an aliases referenced command</span></span>

<span data-ttu-id="e8f8a-182">Dieser Befehl verwendet das `Set-Item` Cmdlet, um den `gp` Alias so zu ändern, dass er das `Get-Process` Cmdlet anstelle des `Get-ItemProperty` Cmdlets darstellt.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-182">This command uses the `Set-Item` cmdlet to change the `gp` alias so that it represents the `Get-Process` cmdlet instead of the `Get-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="e8f8a-183">Der- `-Force` Parameter ist erforderlich, da der Wert der **options** -Eigenschaft des `gp` Alias auf festgelegt ist `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="e8f8a-183">The `-Force` parameter is required because the value of the **Options** property of the `gp` alias is set to `ReadOnly`.</span></span> <span data-ttu-id="e8f8a-184">Da der Befehl innerhalb des Laufwerks übermittelt wird `Alias:` , ist das Laufwerk im Pfad nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-184">Because the command is submitted from within the `Alias:` drive, the drive is not specified in the path.</span></span>

```powershell
Set-Item -Path gp -Value Get-Process -Force
```

<span data-ttu-id="e8f8a-185">Die Änderung wirkt sich auf die vier Eigenschaften aus, die die Zuordnung zwischen dem Alias und dem Befehl definieren.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-185">The change affects the four properties that define the association between the alias and the command.</span></span> <span data-ttu-id="e8f8a-186">Um die Auswirkung der Änderung anzuzeigen, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e8f8a-186">To view the effect of the change, type the following command:</span></span>

```powershell
Get-Item -Path gp | Format-List -Property *
```

### <a name="rename-an-alias"></a><span data-ttu-id="e8f8a-187">Umbenennen eines Alias</span><span class="sxs-lookup"><span data-stu-id="e8f8a-187">Rename an alias</span></span>

<span data-ttu-id="e8f8a-188">Dieser Befehl verwendet das `Rename-Item` Cmdlet, um den `popd` Alias in zu ändern `pop` .</span><span class="sxs-lookup"><span data-stu-id="e8f8a-188">This command uses the `Rename-Item` cmdlet to change the `popd` alias to `pop`.</span></span>

```powershell
Rename-Item -Path Alias:popd -NewName pop
```

## <a name="copying-an-alias"></a><span data-ttu-id="e8f8a-189">Kopieren eines Alias</span><span class="sxs-lookup"><span data-stu-id="e8f8a-189">Copying an alias</span></span>

<span data-ttu-id="e8f8a-190">Mit diesem Befehl `pushd` wird der Alias kopiert, sodass ein neuer `push` Alias für das `Push-Location` Cmdlet erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-190">This command copies the `pushd` alias so that a new `push` alias is created for the `Push-Location` cmdlet.</span></span>

<span data-ttu-id="e8f8a-191">Beim Erstellen des neuen Alias hat die **Description** -Eigenschaft einen NULL-Wert.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-191">When the new alias is created, its **Description** property has a null value.</span></span>
<span data-ttu-id="e8f8a-192">Und die **Option** -Eigenschaft hat den Wert `None` .</span><span class="sxs-lookup"><span data-stu-id="e8f8a-192">And, its **Option** property has a value of `None`.</span></span> <span data-ttu-id="e8f8a-193">Wenn der Befehl innerhalb des `Alias:` Laufwerks ausgegeben wird, können Sie den Namen des Laufwerks aus dem Wert des- `-Path` Parameters weglassen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-193">If the command is issued from within the `Alias:` drive, you can omit the drive name from the value of the `-Path` parameter.</span></span>

```powershell
Copy-Item -Path Alias:pushd -Destination Alias:push
```

## <a name="deleting-an-alias"></a><span data-ttu-id="e8f8a-194">Löschen eines Alias</span><span class="sxs-lookup"><span data-stu-id="e8f8a-194">Deleting an alias</span></span>

<span data-ttu-id="e8f8a-195">Dieser Befehl löscht den `serv` Alias aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-195">This command deletes the `serv` alias from the current session.</span></span>
<span data-ttu-id="e8f8a-196">Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-196">You can use this command in any PowerShell drive.</span></span>

```powershell
Remove-Item -Path Alias:serv
```

<span data-ttu-id="e8f8a-197">Dieser Befehl löscht alle Aliase, die mit "s" beginnen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-197">This command deletes aliases that begin with "s".</span></span>
<span data-ttu-id="e8f8a-198">Schreibgeschützte Aliase werden nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-198">It does not delete read-only aliases.</span></span>

```powershell
Clear-Item -Path Alias:s*
```

### <a name="delete-read-only-aliases"></a><span data-ttu-id="e8f8a-199">Schreibgeschützte Aliase löschen</span><span class="sxs-lookup"><span data-stu-id="e8f8a-199">Delete read-only aliases</span></span>

<span data-ttu-id="e8f8a-200">Dieser Befehl löscht alle Aliase aus der aktuellen Sitzung, mit Ausnahme derjenigen mit dem Wert `Constant` für die **options** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-200">This command deletes all aliases from the current session, except those with a value of `Constant` for their **Options** property.</span></span> <span data-ttu-id="e8f8a-201">Der- `-Force` Parameter ermöglicht dem Befehl das Löschen von Aliasen, deren **options** -Eigenschaft den Wert hat `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="e8f8a-201">The `-Force` parameter allows the command to delete aliases whose **Options** property has a value of `ReadOnly`.</span></span>

```powershell
Remove-Item Alias:* -Force
```

## <a name="dynamic-parameters"></a><span data-ttu-id="e8f8a-202">Dynamische Parameter</span><span class="sxs-lookup"><span data-stu-id="e8f8a-202">Dynamic parameters</span></span>

<span data-ttu-id="e8f8a-203">Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-203">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="options-systemmanagementautomationscopeditemoptions"></a><span data-ttu-id="e8f8a-204">Optionen [System. Management. Automation. scopeditemoptions]</span><span class="sxs-lookup"><span data-stu-id="e8f8a-204">Options [System.Management.Automation.ScopedItemOptions]</span></span>

<span data-ttu-id="e8f8a-205">Bestimmt den Wert der **options** -Eigenschaft eines Alias.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-205">Determines the value of the **Options** property of an alias.</span></span>

- <span data-ttu-id="e8f8a-206">**Keine: keine** Optionen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-206">**None**: No options.</span></span> <span data-ttu-id="e8f8a-207">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-207">This value is the default.</span></span>
- <span data-ttu-id="e8f8a-208">**Constant**: der Alias kann nicht gelöscht werden, und seine Eigenschaften können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-208">**Constant**:The alias cannot be deleted and its properties cannot be changed.</span></span>
  <span data-ttu-id="e8f8a-209">**Constant** ist nur verfügbar, wenn Sie einen Alias erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-209">**Constant** is available only when you create an alias.</span></span> <span data-ttu-id="e8f8a-210">Die Option eines vorhandenen Alias kann nicht in " **Constant**" geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-210">You cannot change the option of an existing alias to **Constant**.</span></span>
- <span data-ttu-id="e8f8a-211">**Privat**: der Alias ist nur im aktuellen Gültigkeitsbereich, nicht in den untergeordneten Bereichen sichtbar.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-211">**Private**:The alias is visible only in the current scope, not in the child  scopes.</span></span>
- <span data-ttu-id="e8f8a-212">Schreib **geschützt: die** Eigenschaften des Alias können nicht geändert werden, es sei denn, Sie verwenden den- `-Force` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-212">**ReadOnly**:The properties of the alias cannot be changed except by using the `-Force` parameter.</span></span> <span data-ttu-id="e8f8a-213">Sie können verwenden `Remove-Item` , um den Alias zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-213">You can use `Remove-Item` to delete the alias.</span></span>
- <span data-ttu-id="e8f8a-214">**Allscope**: der Alias wird in neue Bereiche kopiert, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-214">**AllScope**:The alias is copied to any new scopes that are created.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="e8f8a-215">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e8f8a-215">Cmdlets supported</span></span>

- [<span data-ttu-id="e8f8a-216">New-Item</span><span class="sxs-lookup"><span data-stu-id="e8f8a-216">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="e8f8a-217">Set-Item</span><span class="sxs-lookup"><span data-stu-id="e8f8a-217">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="e8f8a-218">Verwenden der Pipeline</span><span class="sxs-lookup"><span data-stu-id="e8f8a-218">Using the pipeline</span></span>

<span data-ttu-id="e8f8a-219">Anbieter-Cmdlets akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-219">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="e8f8a-220">Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-220">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="e8f8a-221">Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-221">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="e8f8a-222">Hilfe</span><span class="sxs-lookup"><span data-stu-id="e8f8a-222">Getting help</span></span>

<span data-ttu-id="e8f8a-223">Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-223">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="e8f8a-224">Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den `-Path` -Parameter von [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) zum Angeben eines Dateisystem Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="e8f8a-224">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path alias:
```

## <a name="see-also"></a><span data-ttu-id="e8f8a-225">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8f8a-225">See also</span></span>

[<span data-ttu-id="e8f8a-226">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="e8f8a-226">about_Aliases</span></span>](../About/about_Aliases.md)

[<span data-ttu-id="e8f8a-227">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e8f8a-227">about_Providers</span></span>](../About/about_Providers.md)

