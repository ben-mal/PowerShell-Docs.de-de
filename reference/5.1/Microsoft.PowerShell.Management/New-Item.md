---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: b1657d369d44d575ee7bed8b76d36224ea2748f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214615"
---
# <span data-ttu-id="239cf-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="239cf-103">New-Item</span></span>

## <span data-ttu-id="239cf-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="239cf-104">SYNOPSIS</span></span>
<span data-ttu-id="239cf-105">Erstellt ein neues Element.</span><span class="sxs-lookup"><span data-stu-id="239cf-105">Creates a new item.</span></span>

## <span data-ttu-id="239cf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="239cf-106">SYNTAX</span></span>

### <span data-ttu-id="239cf-107">pfadsatz (Standard)</span><span class="sxs-lookup"><span data-stu-id="239cf-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="239cf-108">nameset</span><span class="sxs-lookup"><span data-stu-id="239cf-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="239cf-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="239cf-109">DESCRIPTION</span></span>

<span data-ttu-id="239cf-110">Das `New-Item` Cmdlet erstellt ein neues Element und legt seinen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="239cf-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="239cf-111">Die Typen der Elemente, die erstellt werden können, hängen vom Speicherort des Elements ab.</span><span class="sxs-lookup"><span data-stu-id="239cf-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="239cf-112">Beispielsweise werden im Dateisystem `New-Item` Dateien und Ordner erstellt.</span><span class="sxs-lookup"><span data-stu-id="239cf-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="239cf-113">In der Registrierung `New-Item` erstellt Registrierungsschlüssel und-Einträge.</span><span class="sxs-lookup"><span data-stu-id="239cf-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="239cf-114">`New-Item` kann auch den Wert der erstellten Elemente festlegen.</span><span class="sxs-lookup"><span data-stu-id="239cf-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="239cf-115">Wenn beispielsweise eine neue Datei erstellt wird, `New-Item` kann der Datei anfänglicher Inhalt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="239cf-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="239cf-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="239cf-116">EXAMPLES</span></span>

### <span data-ttu-id="239cf-117">Beispiel 1: Erstellen einer Datei im aktuellen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="239cf-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="239cf-118">Mit diesem Befehl wird eine Textdatei mit dem Namen "testfile1.txt" im aktuellen Verzeichnis erstellt.</span><span class="sxs-lookup"><span data-stu-id="239cf-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="239cf-119">Der Punkt (".") im Wert des **path** -Parameters gibt das aktuelle Verzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="239cf-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="239cf-120">Der Text in Anführungszeichen, der auf den **value** -Parameter folgt, wird der Datei als Inhalt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="239cf-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="239cf-121">Beispiel 2: Erstellen eines Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="239cf-121">Example 2: Create a directory</span></span>

<span data-ttu-id="239cf-122">Mit diesem Befehl wird ein Verzeichnis mit dem Namen "Logfiles" im `C:` Laufwerk erstellt.</span><span class="sxs-lookup"><span data-stu-id="239cf-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="239cf-123">Der **ItemType** -Parameter gibt an, dass das neue Element ein Verzeichnis und keine Datei oder ein anderes Dateisystem Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="239cf-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="239cf-124">Beispiel 3: Erstellen eines Profils</span><span class="sxs-lookup"><span data-stu-id="239cf-124">Example 3: Create a profile</span></span>

<span data-ttu-id="239cf-125">Mit diesem Befehl wird ein PowerShell-Profil in dem Pfad erstellt, der durch die Variable angegeben wird `$profile` .</span><span class="sxs-lookup"><span data-stu-id="239cf-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="239cf-126">Mit Profilen können Sie PowerShell anpassen.</span><span class="sxs-lookup"><span data-stu-id="239cf-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="239cf-127">`$profile` ist eine automatische (integrierte) Variable, die den Pfad und den Dateinamen des Profils "CurrentUser/Currency Thost" speichert.</span><span class="sxs-lookup"><span data-stu-id="239cf-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="239cf-128">Standardmäßig ist das Profil nicht vorhanden, auch wenn von PowerShell ein Pfad und ein Dateiname für das Profil gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="239cf-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="239cf-129">In diesem Befehl stellt die `$profile` Variable den Pfad der Datei dar.</span><span class="sxs-lookup"><span data-stu-id="239cf-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="239cf-130">Der **ItemType** -Parameter gibt an, dass der Befehl eine Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="239cf-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="239cf-131">Mit dem **Force** -Parameter können Sie eine Datei im Profilpfad erstellen, selbst wenn die Verzeichnisse im Pfad nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="239cf-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="239cf-132">Nachdem Sie ein Profil erstellt haben, können Sie Aliase, Funktionen und Skripts im Profil eingeben, um die Shell anzupassen.</span><span class="sxs-lookup"><span data-stu-id="239cf-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="239cf-133">Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) und [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="239cf-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

> [!NOTE]
> <span data-ttu-id="239cf-134">Wenn Sie mit dieser Methode eine Datei erstellen, wird die resultierende Datei als UTF-8 ohne Byte Reihenfolge-Markierung (BOM) codiert.</span><span class="sxs-lookup"><span data-stu-id="239cf-134">When you create a file using this method, the resulting file is encoded as UTF-8 without a byte-order-mark (BOM).</span></span>

### <span data-ttu-id="239cf-135">Beispiel 4: Erstellen eines Verzeichnisses in einem anderen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="239cf-135">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="239cf-136">In diesem Beispiel wird ein neues Scripts-Verzeichnis im Verzeichnis "c:\ps-Test" erstellt.</span><span class="sxs-lookup"><span data-stu-id="239cf-136">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="239cf-137">Der Name des neuen Verzeichnis Elements "Scripts" ist im Wert des **path** -Parameters enthalten, anstatt im Wert von " **Name** " angegeben zu werden.</span><span class="sxs-lookup"><span data-stu-id="239cf-137">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="239cf-138">Gemäß Syntax kann der Befehl auf beide Weisen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="239cf-138">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="239cf-139">Beispiel 5: Erstellen mehrerer Dateien</span><span class="sxs-lookup"><span data-stu-id="239cf-139">Example 5: Create multiple files</span></span>

<span data-ttu-id="239cf-140">In diesem Beispiel werden Dateien in zwei verschiedenen Verzeichnissen erstellt.</span><span class="sxs-lookup"><span data-stu-id="239cf-140">This example creates files in two different directories.</span></span> <span data-ttu-id="239cf-141">Da der **Pfad** mehrere Zeichen folgen annimmt, können Sie ihn verwenden, um mehrere Elemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="239cf-141">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="239cf-142">Beispiel 6: Verwenden des Parameters "-Force" zum erneuten Erstellen von Ordnern</span><span class="sxs-lookup"><span data-stu-id="239cf-142">Example 6: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="239cf-143">In diesem Beispiel wird ein Ordner mit einer Datei in erstellt.</span><span class="sxs-lookup"><span data-stu-id="239cf-143">This example creates a folder with a file inside.</span></span> <span data-ttu-id="239cf-144">Anschließend versucht, mithilfe von denselben Ordner zu erstellen `-Force` .</span><span class="sxs-lookup"><span data-stu-id="239cf-144">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="239cf-145">Der Ordner wird nicht überschrieben, sondern es wird einfach das vorhandene Ordner Objekt mit der Datei zurückgegeben, die intakt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="239cf-145">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

```powershell
PS> New-Item -Path .\TestFolder -ItemType Directory
PS> New-Item -Path .\TestFolder\TestFile.txt -ItemType File

PS> New-Item -Path .\TestFolder -ItemType Directory -Force

    Directory: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         5/1/2020   8:03 AM                TestFolder

PS> Get-ChildItem .\TestFolder\

    Directory: C:\TestFolder
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:03 AM              0 TestFile.txt
```

### <span data-ttu-id="239cf-146">Beispiel 7: Verwenden des Parameters "-Force" zum Überschreiben vorhandener Dateien</span><span class="sxs-lookup"><span data-stu-id="239cf-146">Example 7: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="239cf-147">In diesem Beispiel wird eine Datei mit einem Wert erstellt und die Datei dann mithilfe von neu erstellt `-Force` .</span><span class="sxs-lookup"><span data-stu-id="239cf-147">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="239cf-148">Dadurch wird die vorhandene Datei überschrieben, und der Inhalt wird wie durch die length-Eigenschaft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="239cf-148">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

```powershell
PS> New-Item ./TestFile.txt -ItemType File -Value 'This is just a test file'

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM             24 TestFile.txt

New-Item ./TestFile.txt -ItemType File -Force

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM              0 TestFile.txt
```

> [!NOTE]
> <span data-ttu-id="239cf-149">Wenn Sie `New-Item` mit dem- `-Force` Schalter verwenden, um Registrierungsschlüssel zu erstellen, verhält sich der Befehl identisch mit dem, wenn eine Datei überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="239cf-149">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="239cf-150">Wenn der Registrierungsschlüssel bereits vorhanden ist, werden der Schlüssel und alle Eigenschaften und Werte mit einem leeren Registrierungsschlüssel überschrieben.</span><span class="sxs-lookup"><span data-stu-id="239cf-150">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="239cf-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="239cf-151">PARAMETERS</span></span>

### <span data-ttu-id="239cf-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="239cf-152">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="239cf-153">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="239cf-153">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="239cf-154">Verwenden Sie, um die Identität eines anderen Benutzers anzunehmen oder die Anmelde Informationen beim Ausführen dieses Cmdlets zu erhöhen `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="239cf-154">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="239cf-155">-Force</span><span class="sxs-lookup"><span data-stu-id="239cf-155">-Force</span></span>

<span data-ttu-id="239cf-156">Erzwingt, dass dieses Cmdlet ein Element erstellt, das ein vorhandenes Schreib geschütztes Element überschreibt.</span><span class="sxs-lookup"><span data-stu-id="239cf-156">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="239cf-157">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="239cf-157">Implementation varies from provider to provider.</span></span> <span data-ttu-id="239cf-158">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="239cf-158">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="239cf-159">-ItemType</span><span class="sxs-lookup"><span data-stu-id="239cf-159">-ItemType</span></span>

<span data-ttu-id="239cf-160">Gibt den vom Anbieter angegebenen Typ des neuen Elements an.</span><span class="sxs-lookup"><span data-stu-id="239cf-160">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="239cf-161">Die verfügbaren Werte dieses Parameters hängen vom aktuellen Anbieter ab, den Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="239cf-161">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="239cf-162">Wenn sich ihr Speicherort in einem `FileSystem` Laufwerk befindet, sind folgende Werte zulässig:</span><span class="sxs-lookup"><span data-stu-id="239cf-162">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="239cf-163">Datei</span><span class="sxs-lookup"><span data-stu-id="239cf-163">File</span></span>
- <span data-ttu-id="239cf-164">Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="239cf-164">Directory</span></span>
- <span data-ttu-id="239cf-165">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="239cf-165">SymbolicLink</span></span>
- <span data-ttu-id="239cf-166">Verbindung</span><span class="sxs-lookup"><span data-stu-id="239cf-166">Junction</span></span>
- <span data-ttu-id="239cf-167">HardLink</span><span class="sxs-lookup"><span data-stu-id="239cf-167">HardLink</span></span>

<span data-ttu-id="239cf-168">Wenn Sie mit dieser Methode eine Datei erstellen, wird die resultierende Datei als UTF-8 ohne Byte Reihenfolge-Markierung (BOM) codiert.</span><span class="sxs-lookup"><span data-stu-id="239cf-168">When you create a file using this method, the resulting file is encoded as UTF-8 without a byte-order-mark (BOM).</span></span>

<span data-ttu-id="239cf-169">In einem `Certificate` Laufwerk sind dies die Werte, die Sie angeben können:</span><span class="sxs-lookup"><span data-stu-id="239cf-169">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="239cf-170">Zertifikat-Anbieter</span><span class="sxs-lookup"><span data-stu-id="239cf-170">Certificate Provider</span></span>
- <span data-ttu-id="239cf-171">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="239cf-171">Certificate</span></span>
- <span data-ttu-id="239cf-172">Speicher</span><span class="sxs-lookup"><span data-stu-id="239cf-172">Store</span></span>
- <span data-ttu-id="239cf-173">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="239cf-173">StoreLocation</span></span>

<span data-ttu-id="239cf-174">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="239cf-174">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="239cf-175">-Name</span><span class="sxs-lookup"><span data-stu-id="239cf-175">-Name</span></span>

<span data-ttu-id="239cf-176">Gibt den Namen des neuen Elements an.</span><span class="sxs-lookup"><span data-stu-id="239cf-176">Specifies the name of the new item.</span></span> <span data-ttu-id="239cf-177">Sie können den Namen des neuen Elements im **Name** -oder **path** -Parameterwert angeben, und Sie können den Pfad des neuen Elements im **Name** -oder **path** -Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="239cf-177">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="239cf-178">Elementnamen, die mit dem **Name** -Parameter übergeben werden, werden relativ zum Wert des **path** -Parameters erstellt.</span><span class="sxs-lookup"><span data-stu-id="239cf-178">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="239cf-179">-Path</span><span class="sxs-lookup"><span data-stu-id="239cf-179">-Path</span></span>

<span data-ttu-id="239cf-180">Gibt den Pfad zum Speicherort des neuen Elements an.</span><span class="sxs-lookup"><span data-stu-id="239cf-180">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="239cf-181">Der Standardwert ist der aktuelle Speicherort, wenn der **Pfad** weggelassen wird.</span><span class="sxs-lookup"><span data-stu-id="239cf-181">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="239cf-182">Sie können den Namen des neuen Elements im **Namen** angeben oder ihn in **path** einschließen.</span><span class="sxs-lookup"><span data-stu-id="239cf-182">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="239cf-183">Elementnamen, die mit dem **Name** -Parameter übergeben werden, werden relativ zum Wert des **path** -Parameters erstellt.</span><span class="sxs-lookup"><span data-stu-id="239cf-183">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="239cf-184">Für dieses Cmdlet funktioniert der **path** -Parameter wie der **literalpath** -Parameter anderer Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="239cf-184">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="239cf-185">Platzhalter Zeichen werden nicht interpretiert.</span><span class="sxs-lookup"><span data-stu-id="239cf-185">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="239cf-186">Alle Zeichen werden an den Anbieter des Speicher Orts übermittelt.</span><span class="sxs-lookup"><span data-stu-id="239cf-186">All characters are passed to the location's provider.</span></span> <span data-ttu-id="239cf-187">Der Anbieter unterstützt möglicherweise nicht alle Zeichen.</span><span class="sxs-lookup"><span data-stu-id="239cf-187">The provider may not support all characters.</span></span> <span data-ttu-id="239cf-188">Beispielsweise können Sie keinen Dateinamen erstellen, der ein Sternchen ( `*` ) enthält.</span><span class="sxs-lookup"><span data-stu-id="239cf-188">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="239cf-189">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="239cf-189">-UseTransaction</span></span>

<span data-ttu-id="239cf-190">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="239cf-190">Includes the command in the active transaction.</span></span> <span data-ttu-id="239cf-191">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="239cf-191">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="239cf-192">Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="239cf-192">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="239cf-193">-Value</span><span class="sxs-lookup"><span data-stu-id="239cf-193">-Value</span></span>

<span data-ttu-id="239cf-194">Gibt den Wert des neuen Elements an.</span><span class="sxs-lookup"><span data-stu-id="239cf-194">Specifies the value of the new item.</span></span> <span data-ttu-id="239cf-195">Sie können einen Wert auch über die Pipeline an übergeben `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="239cf-195">You can also pipe a value to `New-Item`.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Target

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="239cf-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="239cf-196">-Confirm</span></span>

<span data-ttu-id="239cf-197">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="239cf-197">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="239cf-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="239cf-198">-WhatIf</span></span>

<span data-ttu-id="239cf-199">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="239cf-199">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="239cf-200">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="239cf-200">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="239cf-201">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="239cf-201">CommonParameters</span></span>

<span data-ttu-id="239cf-202">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="239cf-202">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="239cf-203">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="239cf-203">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="239cf-204">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="239cf-204">INPUTS</span></span>

### <span data-ttu-id="239cf-205">System.Object</span><span class="sxs-lookup"><span data-stu-id="239cf-205">System.Object</span></span>

<span data-ttu-id="239cf-206">Sie können einen Wert für das neue Element über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="239cf-206">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="239cf-207">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="239cf-207">OUTPUTS</span></span>

### <span data-ttu-id="239cf-208">System.Object</span><span class="sxs-lookup"><span data-stu-id="239cf-208">System.Object</span></span>

<span data-ttu-id="239cf-209">Dieses Cmdlet gibt das Element zurück, das es erstellt.</span><span class="sxs-lookup"><span data-stu-id="239cf-209">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="239cf-210">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="239cf-210">NOTES</span></span>

<span data-ttu-id="239cf-211">`New-Item` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="239cf-211">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="239cf-212">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="239cf-212">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="239cf-213">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="239cf-213">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="239cf-214">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="239cf-214">RELATED LINKS</span></span>

[<span data-ttu-id="239cf-215">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="239cf-215">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="239cf-216">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="239cf-216">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="239cf-217">Get-Item</span><span class="sxs-lookup"><span data-stu-id="239cf-217">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="239cf-218">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="239cf-218">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="239cf-219">Move-Item</span><span class="sxs-lookup"><span data-stu-id="239cf-219">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="239cf-220">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="239cf-220">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="239cf-221">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="239cf-221">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="239cf-222">Set-Item</span><span class="sxs-lookup"><span data-stu-id="239cf-222">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="239cf-223">about_Providers</span><span class="sxs-lookup"><span data-stu-id="239cf-223">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
