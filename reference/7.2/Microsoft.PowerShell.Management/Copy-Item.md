---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-Item
ms.openlocfilehash: ee2d8b8a3b736a59b5af4a81710a0d29dd2238d5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602310"
---
# <span data-ttu-id="8391a-102">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="8391a-102">Copy-Item</span></span>

## <span data-ttu-id="8391a-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8391a-103">SYNOPSIS</span></span>
<span data-ttu-id="8391a-104">Kopiert ein Element von einem Speicherort an einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="8391a-104">Copies an item from one location to another.</span></span>

## <span data-ttu-id="8391a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8391a-105">SYNTAX</span></span>

### <span data-ttu-id="8391a-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="8391a-106">Path (Default)</span></span>

```
Copy-Item [-Path] <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="8391a-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8391a-107">LiteralPath</span></span>

```
Copy-Item -LiteralPath <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

## <span data-ttu-id="8391a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8391a-108">DESCRIPTION</span></span>

<span data-ttu-id="8391a-109">Das `Copy-Item` Cmdlet kopiert ein Element von einem Speicherort an einen anderen Speicherort im selben Namespace.</span><span class="sxs-lookup"><span data-stu-id="8391a-109">The `Copy-Item` cmdlet copies an item from one location to another location in the same namespace.</span></span>
<span data-ttu-id="8391a-110">Beispielsweise kann eine Datei in einen Ordner kopiert werden, aber Sie kann keine Datei auf ein Zertifikat Laufwerk kopieren.</span><span class="sxs-lookup"><span data-stu-id="8391a-110">For instance, it can copy a file to a folder, but it can't copy a file to a certificate drive.</span></span>

<span data-ttu-id="8391a-111">Mit diesem Cmdlet werden die kopierten Elemente nicht ausgeschnitten oder gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8391a-111">This cmdlet doesn't cut or delete the items being copied.</span></span> <span data-ttu-id="8391a-112">Die Elemente, die vom Cmdlet kopiert werden können, hängen vom PowerShell-Anbieter ab, der das Element verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="8391a-112">The particular items that the cmdlet can copy depend on the PowerShell provider that exposes the item.</span></span> <span data-ttu-id="8391a-113">Beispielsweise können Dateien und Verzeichnisse auf einem Dateisystem Laufwerk sowie Registrierungsschlüssel und-Einträge auf dem Registrierungs Laufwerk kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="8391a-113">For instance, it can copy files and directories in a file system drive and registry keys and entries in the registry drive.</span></span>

<span data-ttu-id="8391a-114">Mit diesem Cmdlet können Elemente im selben Befehl kopiert und umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="8391a-114">This cmdlet can copy and rename items in the same command.</span></span> <span data-ttu-id="8391a-115">Um ein Element umzubenennen, geben Sie den neuen Namen in den Wert des **Destination** -Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="8391a-115">To rename an item, enter the new name in the value of the **Destination** parameter.</span></span> <span data-ttu-id="8391a-116">Verwenden Sie das-Cmdlet, um ein Element umzubenennen und es nicht zu kopieren `Rename-Item` .</span><span class="sxs-lookup"><span data-stu-id="8391a-116">To rename an item and not copy it, use the `Rename-Item` cmdlet.</span></span>

## <span data-ttu-id="8391a-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8391a-117">EXAMPLES</span></span>

### <span data-ttu-id="8391a-118">Beispiel 1: Kopieren einer Datei in das angegebene Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="8391a-118">Example 1: Copy a file to the specified directory</span></span>

<span data-ttu-id="8391a-119">In diesem Beispiel wird die `mar1604.log.txt` Datei in das `C:\Presentation` Verzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="8391a-119">This example copies the `mar1604.log.txt` file to the `C:\Presentation` directory.</span></span> <span data-ttu-id="8391a-120">Die ursprüngliche Datei wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8391a-120">The original file isn't deleted.</span></span>

```powershell
Copy-Item "C:\Wabash\Logfiles\mar1604.log.txt" -Destination "C:\Presentation"
```

### <span data-ttu-id="8391a-121">Beispiel 2: Kopieren von Verzeichnis Inhalten in ein vorhandenes Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="8391a-121">Example 2: Copy directory contents to an existing directory</span></span>

<span data-ttu-id="8391a-122">In diesem Beispiel wird der Inhalt des `C:\Logfiles` Verzeichnisses in das vorhandene `C:\Drawings` Verzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="8391a-122">This example copies the contents of the `C:\Logfiles` directory into the existing `C:\Drawings` directory.</span></span> <span data-ttu-id="8391a-123">Das `Logfiles` Verzeichnis wird nicht kopiert.</span><span class="sxs-lookup"><span data-stu-id="8391a-123">The `Logfiles` directory isn't copied.</span></span>

<span data-ttu-id="8391a-124">Wenn das `Logfiles` Verzeichnis Dateien in Unterverzeichnissen enthält, werden diese Unterverzeichnisse mit ihren Dateistrukturen intakt kopiert.</span><span class="sxs-lookup"><span data-stu-id="8391a-124">If the `Logfiles` directory contains files in subdirectories, those subdirectories are copied with their file trees intact.</span></span> <span data-ttu-id="8391a-125">Standardmäßig ist der **Container** -Parameter auf **true** festgelegt, wodurch die Verzeichnisstruktur beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="8391a-125">By default, the **Container** parameter is set to **True**, which preserves the directory structure.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings" -Recurse
```

> [!NOTE]
> <span data-ttu-id="8391a-126">Wenn Sie das `Logfiles` Verzeichnis in die Kopie einschließen müssen, entfernen Sie das `\*` aus dem **Pfad**.</span><span class="sxs-lookup"><span data-stu-id="8391a-126">If you need to include the `Logfiles` directory in the copy, remove the `\*` from the **Path**.</span></span>
> <span data-ttu-id="8391a-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8391a-127">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings" -Recurse`

### <span data-ttu-id="8391a-128">Beispiel 3: Kopieren von Verzeichnis und Inhalt in ein neues Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="8391a-128">Example 3: Copy directory and contents to a new directory</span></span>

<span data-ttu-id="8391a-129">In diesem Beispiel werden die Inhalte des `C:\Logfiles` Quell Verzeichnisses kopiert und ein neues Zielverzeichnis erstellt.</span><span class="sxs-lookup"><span data-stu-id="8391a-129">This example copies the contents of the `C:\Logfiles` source directory and creates a new destination directory.</span></span> <span data-ttu-id="8391a-130">Das neue Zielverzeichnis `\Logs` wird in erstellt `C:\Drawings` .</span><span class="sxs-lookup"><span data-stu-id="8391a-130">The new destination directory, `\Logs` is created in `C:\Drawings`.</span></span>

<span data-ttu-id="8391a-131">Wenn Sie den Namen des Quell Verzeichnisses einschließen möchten, kopieren Sie ihn in ein vorhandenes Zielverzeichnis, wie in **Beispiel 2** gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8391a-131">To include the source directory's name, copy to an existing destination directory as shown in **Example 2**.</span></span> <span data-ttu-id="8391a-132">Oder benennen Sie das neue Zielverzeichnis mit dem Quellverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8391a-132">Or, name the new destination directory with the same as the source directory.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings\Logs" -Recurse
```

> [!NOTE]
> <span data-ttu-id="8391a-133">Wenn der **Pfad** enthält `\*` , werden alle Dateiinhalte des Verzeichnisses, einschließlich der Unterverzeichnis Strukturen, in das neue Zielverzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="8391a-133">If the **Path** includes `\*`, all the directory's file contents, including the subdirectory trees, are copied to the new destination directory.</span></span> <span data-ttu-id="8391a-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8391a-134">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings\Logs" -Recurse`

### <span data-ttu-id="8391a-135">Beispiel 4: Kopieren einer Datei in das angegebene Verzeichnis und Umbenennen der Datei</span><span class="sxs-lookup"><span data-stu-id="8391a-135">Example 4: Copy a file to the specified directory and rename the file</span></span>

<span data-ttu-id="8391a-136">In diesem Beispiel wird das- `Copy-Item` Cmdlet verwendet, um das `Get-Widget.ps1` Skript aus dem `\\Server01\Share` Verzeichnis in das Verzeichnis zu kopieren `\\Server12\ScriptArchive` .</span><span class="sxs-lookup"><span data-stu-id="8391a-136">This example uses the `Copy-Item` cmdlet to copy the `Get-Widget.ps1` script from the `\\Server01\Share` directory to the `\\Server12\ScriptArchive` directory.</span></span> <span data-ttu-id="8391a-137">Im Rahmen des Kopiervorgangs ändert der-Befehl den Elementnamen von `Get-Widget.ps1` in `Get-Widget.ps1.txt` , sodass er an e-Mail-Nachrichten angefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8391a-137">As part of the copy operation, the command changes the item name from `Get-Widget.ps1` to `Get-Widget.ps1.txt`, so it can be attached to email messages.</span></span>

```powershell
Copy-Item "\\Server01\Share\Get-Widget.ps1" -Destination "\\Server12\ScriptArchive\Get-Widget.ps1.txt"
```

### <span data-ttu-id="8391a-138">Beispiel 5: Kopieren einer Datei auf einen Remote Computer</span><span class="sxs-lookup"><span data-stu-id="8391a-138">Example 5: Copy a file to a remote computer</span></span>

<span data-ttu-id="8391a-139">Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-139">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="8391a-140">Das `Copy-Item` Cmdlet kopiert `test.log` `D:\Folder001` `C:\Folder001_Copy` mithilfe der in der Variablen gespeicherten Sitzungsinformationen aus dem Ordner in den Ordner auf dem Remote Computer `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-140">The `Copy-Item` cmdlet copies `test.log` from the `D:\Folder001` folder to the `C:\Folder001_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="8391a-141">Die ursprüngliche Datei wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8391a-141">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "D:\Folder001\test.log" -Destination "C:\Folder001_Copy\" -ToSession $Session
```

### <span data-ttu-id="8391a-142">Beispiel 6: Kopieren eines Ordners auf einen Remote Computer</span><span class="sxs-lookup"><span data-stu-id="8391a-142">Example 6: Copy a folder to a remote computer</span></span>

<span data-ttu-id="8391a-143">Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-143">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="8391a-144">Das- `Copy-Item` Cmdlet kopiert den `D:\Folder002` Ordner `C:\Folder002_Copy` mithilfe der in der-Variablen gespeicherten Sitzungsinformationen in das Verzeichnis auf dem Remote Computer `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-144">The `Copy-Item` cmdlet copies the `D:\Folder002` folder to the `C:\Folder002_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="8391a-145">Alle Unterordner oder Dateien werden ohne Verwendung des **recurse** -Schalters nicht kopiert.</span><span class="sxs-lookup"><span data-stu-id="8391a-145">Any subfolders or files are not copied without using the **Recurse** switch.</span></span>
<span data-ttu-id="8391a-146">Der-Vorgang erstellt den `Folder002_Copy` Ordner, wenn er nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8391a-146">The operation creates the `Folder002_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server02" -Credential "Contoso\User01"
Copy-Item "D:\Folder002\" -Destination "C:\Folder002_Copy\" -ToSession $Session
```

### <span data-ttu-id="8391a-147">Beispiel 7: rekursiver Kopieren des gesamten Inhalts eines Ordners auf einen Remote Computer</span><span class="sxs-lookup"><span data-stu-id="8391a-147">Example 7: Recursively copy the entire contents of a folder to a remote computer</span></span>

<span data-ttu-id="8391a-148">Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-148">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="8391a-149">Mit dem- `Copy-Item` Cmdlet wird der gesamte Inhalt aus dem `D:\Folder003` Ordner `C:\Folder003_Copy` mithilfe der in der-Variablen gespeicherten Sitzungsinformationen aus dem Ordner in das Verzeichnis auf dem Remote Computer kopiert `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-149">The `Copy-Item` cmdlet copies the entire contents from the `D:\Folder003` folder to the `C:\Folder003_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="8391a-150">Die Unterordner werden mit ihren Dateistrukturen intakt kopiert.</span><span class="sxs-lookup"><span data-stu-id="8391a-150">The subfolders are copied with their file trees intact.</span></span> <span data-ttu-id="8391a-151">Der-Vorgang erstellt den `Folder003_Copy` Ordner, wenn er nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8391a-151">The operation creates the `Folder003_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder003\" -Destination "C:\Folder003_Copy\" -ToSession $Session -Recurse
```

### <span data-ttu-id="8391a-152">Beispiel 8: Kopieren einer Datei auf einen Remote Computer und anschließendes Umbenennen der Datei</span><span class="sxs-lookup"><span data-stu-id="8391a-152">Example 8: Copy a file to a remote computer and then rename the file</span></span>

<span data-ttu-id="8391a-153">Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-153">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="8391a-154">Das `Copy-Item` Cmdlet kopiert `scriptingexample.ps1` `D:\Folder004` `C:\Folder004_Copy` mithilfe der in der Variablen gespeicherten Sitzungsinformationen aus dem Ordner in den Ordner auf dem Remote Computer `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-154">The `Copy-Item` cmdlet copies `scriptingexample.ps1` from the `D:\Folder004` folder to the `C:\Folder004_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="8391a-155">Im Rahmen des Kopiervorgangs ändert der-Befehl den Elementnamen von `scriptingexample.ps1` in `scriptingexample_copy.ps1` , sodass er an e-Mail-Nachrichten angefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8391a-155">As part of the copy operation, the command changes the item name from `scriptingexample.ps1` to `scriptingexample_copy.ps1`, so it can be attached to email messages.</span></span> <span data-ttu-id="8391a-156">Die ursprüngliche Datei wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8391a-156">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder004\scriptingexample.ps1" -Destination "C:\Folder004_Copy\scriptingexample_copy.ps1" -ToSession $Session
```

### <span data-ttu-id="8391a-157">Beispiel 9: Kopieren einer Remote Datei auf den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="8391a-157">Example 9: Copy a remote file to the local computer</span></span>

<span data-ttu-id="8391a-158">Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-158">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="8391a-159">Das- `Copy-Item` Cmdlet kopiert `test.log` `C:\MyRemoteData\` `D:\MyLocalData` mithilfe der in der-Variablen gespeicherten Sitzungsinformationen aus dem Remote-in den lokalen Ordner `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-159">The `Copy-Item` cmdlet copies `test.log` from the remote `C:\MyRemoteData\` to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="8391a-160">Die ursprüngliche Datei wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8391a-160">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\test.log" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="8391a-161">Beispiel 10: Kopieren des gesamten Inhalts eines Remote Ordners auf den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="8391a-161">Example 10: Copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="8391a-162">Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-162">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="8391a-163">Mit dem- `Copy-Item` Cmdlet wird der gesamte Inhalt aus dem Remote `C:\MyRemoteData\scripts` Ordner `D:\MyLocalData` mithilfe der in der-Variablen gespeicherten Sitzungsinformationen aus dem Remote Ordner in den lokalen Ordner kopiert `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-163">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="8391a-164">Wenn der Ordner Scripts Dateien in Unterordnern enthält, werden diese Unterordner mit ihren Dateistrukturen intakt kopiert.</span><span class="sxs-lookup"><span data-stu-id="8391a-164">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="8391a-165">Beispiel 11: rekursiver Kopieren des gesamten Inhalts eines Remote Ordners auf den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="8391a-165">Example 11: Recursively copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="8391a-166">Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-166">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="8391a-167">Mit dem- `Copy-Item` Cmdlet wird der gesamte Inhalt aus dem Remote `C:\MyRemoteData\scripts` Ordner `D:\MyLocalData\scripts` mithilfe der in der-Variablen gespeicherten Sitzungsinformationen aus dem Remote Ordner in den lokalen Ordner kopiert `$Session` .</span><span class="sxs-lookup"><span data-stu-id="8391a-167">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData\scripts` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="8391a-168">Da der **recurse** -Parameter verwendet wird, erstellt der Vorgang den Ordner "Scripts", falls er nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8391a-168">Because the **Recurse** parameter is used, the operation creates the scripts folder if it doesn't already exist.</span></span> <span data-ttu-id="8391a-169">Wenn der Ordner Scripts Dateien in Unterordnern enthält, werden diese Unterordner mit ihren Dateistrukturen intakt kopiert.</span><span class="sxs-lookup"><span data-stu-id="8391a-169">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\scripts" -FromSession $Session -Recurse
```

### <span data-ttu-id="8391a-170">Beispiel 12: rekursiver Kopieren von Dateien aus einer Ordnerstruktur in den aktuellen Ordner</span><span class="sxs-lookup"><span data-stu-id="8391a-170">Example 12: Recursively copy files from a folder tree into the current folder</span></span>

<span data-ttu-id="8391a-171">In diesem Beispiel wird gezeigt, wie Sie Dateien aus einer mehrstufigen Ordnerstruktur in einen einzelnen flatfolder kopieren.</span><span class="sxs-lookup"><span data-stu-id="8391a-171">This example shows how to copy files from a multilevel folder structure into a single flat folder.</span></span>
<span data-ttu-id="8391a-172">Die ersten drei Befehle zeigen die vorhandene Ordnerstruktur und den Inhalt von zwei Dateien, beide Namen `file3.txt` .</span><span class="sxs-lookup"><span data-stu-id="8391a-172">The first three commands show the existing folder structure and the contents of two files, both names `file3.txt`.</span></span>

```powershell
PS C:\temp\test> (Get-ChildItem C:\temp\tree -Recurse).FullName
C:\temp\tree\subfolder
C:\temp\tree\file1.txt
C:\temp\tree\file2.txt
C:\temp\tree\file3.txt
C:\temp\tree\subfolder\file3.txt
C:\temp\tree\subfolder\file4.txt
C:\temp\tree\subfolder\file5.txt

PS C:\temp\test> Get-Content C:\temp\tree\file3.txt
This is file3.txt in the root folder

PS C:\temp\test> Get-Content C:\temp\tree\subfolder\file3.txt
This is file3.txt in the subfolder

PS C:\temp\test> Copy-Item -Path C:\temp\tree -Filter *.txt -Recurse -Container:$false
PS C:\temp\test> (Get-ChildItem . -Recurse).FullName
C:\temp\test\subfolder
C:\temp\test\file1.txt
C:\temp\test\file2.txt
C:\temp\test\file3.txt
C:\temp\test\file4.txt
C:\temp\test\file5.txt

PS C:\temp\test> Get-Content .\file3.txt
This is file3.txt in the subfolder
```

<span data-ttu-id="8391a-173">Für das- `Copy-Item` Cmdlet ist der **Container** -Parameter auf festgelegt `$false` .</span><span class="sxs-lookup"><span data-stu-id="8391a-173">The `Copy-Item` cmdlet has the **Container** parameter set to `$false`.</span></span> <span data-ttu-id="8391a-174">Dies bewirkt, dass der Inhalt des Quell Ordners kopiert wird, behält jedoch die Ordnerstruktur nicht bei.</span><span class="sxs-lookup"><span data-stu-id="8391a-174">This causes the contents of the source folder to be copied but does not preserve the folder structure.</span></span> <span data-ttu-id="8391a-175">Beachten Sie, dass Dateien mit demselben Namen im Zielordner überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8391a-175">Notice that files with the same name are overwritten in the destination folder.</span></span>

## <span data-ttu-id="8391a-176">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8391a-176">PARAMETERS</span></span>

### <span data-ttu-id="8391a-177">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8391a-177">-Confirm</span></span>

<span data-ttu-id="8391a-178">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="8391a-178">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8391a-179">-Container</span><span class="sxs-lookup"><span data-stu-id="8391a-179">-Container</span></span>

<span data-ttu-id="8391a-180">Gibt an, dass dieses Cmdlet während des Kopiervorgangs Containerobjekte beibehält.</span><span class="sxs-lookup"><span data-stu-id="8391a-180">Indicates that this cmdlet preserves container objects during the copy operation.</span></span> <span data-ttu-id="8391a-181">Standardmäßig ist der **Container** -Parameter auf **true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8391a-181">By default, the **Container** parameter is set to **True**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8391a-182">-Credential</span><span class="sxs-lookup"><span data-stu-id="8391a-182">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="8391a-183">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8391a-183">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="8391a-184">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="8391a-184">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="8391a-185">-Destination</span><span class="sxs-lookup"><span data-stu-id="8391a-185">-Destination</span></span>

<span data-ttu-id="8391a-186">Gibt den Pfad zum neuen Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="8391a-186">Specifies the path to the new location.</span></span> <span data-ttu-id="8391a-187">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8391a-187">The default is the current directory.</span></span>

<span data-ttu-id="8391a-188">Um das zu kopierende Element umzubenennen, geben Sie im Wert des **Destination** -Parameters einen neuen Namen an.</span><span class="sxs-lookup"><span data-stu-id="8391a-188">To rename the item being copied, specify a new name in the value of the **Destination** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8391a-189">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="8391a-189">-Exclude</span></span>

<span data-ttu-id="8391a-190">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8391a-190">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="8391a-191">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="8391a-191">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="8391a-192">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="8391a-192">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="8391a-193">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8391a-193">Wildcard characters are permitted.</span></span> <span data-ttu-id="8391a-194">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="8391a-194">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8391a-195">-Filter</span><span class="sxs-lookup"><span data-stu-id="8391a-195">-Filter</span></span>

<span data-ttu-id="8391a-196">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="8391a-196">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="8391a-197">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8391a-197">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="8391a-198">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="8391a-198">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="8391a-199">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="8391a-199">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8391a-200">-Force</span><span class="sxs-lookup"><span data-stu-id="8391a-200">-Force</span></span>

<span data-ttu-id="8391a-201">Gibt an, dass dieses Cmdlet Elemente kopiert, die anderweitig nicht geändert werden können, z. b. das Kopieren über eine schreibgeschützte Datei oder einen Alias.</span><span class="sxs-lookup"><span data-stu-id="8391a-201">Indicates that this cmdlet copies items that can't otherwise be changed, such as copying over a read-only file or alias.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8391a-202">-Fromsession</span><span class="sxs-lookup"><span data-stu-id="8391a-202">-FromSession</span></span>

<span data-ttu-id="8391a-203">Gibt das **PSSession** -Objekt an, aus dem eine Remote Datei kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="8391a-203">Specifies the **PSSession** object from which a remote file is being copied.</span></span> <span data-ttu-id="8391a-204">Wenn Sie diesen Parameter verwenden, verweisen die **path** -und **literalpath** -Parameter auf den lokalen Pfad auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="8391a-204">When you use this parameter, the **Path** and **LiteralPath** parameters refer to the local path on the remote machine.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8391a-205">-Include</span><span class="sxs-lookup"><span data-stu-id="8391a-205">-Include</span></span>

<span data-ttu-id="8391a-206">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="8391a-206">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="8391a-207">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="8391a-207">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="8391a-208">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="8391a-208">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="8391a-209">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8391a-209">Wildcard characters are permitted.</span></span> <span data-ttu-id="8391a-210">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="8391a-210">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8391a-211">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="8391a-211">-LiteralPath</span></span>

<span data-ttu-id="8391a-212">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="8391a-212">Specifies a path to one or more locations.</span></span> <span data-ttu-id="8391a-213">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8391a-213">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="8391a-214">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="8391a-214">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8391a-215">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="8391a-215">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="8391a-216">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="8391a-216">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="8391a-217">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="8391a-217">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8391a-218">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8391a-218">-PassThru</span></span>

<span data-ttu-id="8391a-219">Gibt ein-Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8391a-219">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="8391a-220">Standardmäßig generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="8391a-220">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8391a-221">-Path</span><span class="sxs-lookup"><span data-stu-id="8391a-221">-Path</span></span>

<span data-ttu-id="8391a-222">Gibt den Pfad zu den zu kopierenden Elementen als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="8391a-222">Specifies, as a string array, the path to the items to copy.</span></span> <span data-ttu-id="8391a-223">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8391a-223">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="8391a-224">-Recurse</span><span class="sxs-lookup"><span data-stu-id="8391a-224">-Recurse</span></span>

<span data-ttu-id="8391a-225">Gibt an, dass dieses Cmdlet eine rekursive Kopie durchführt.</span><span class="sxs-lookup"><span data-stu-id="8391a-225">Indicates that this cmdlet does a recursive copy.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8391a-226">-Sitzungs</span><span class="sxs-lookup"><span data-stu-id="8391a-226">-ToSession</span></span>

<span data-ttu-id="8391a-227">Gibt das **PSSession** -Objekt an, in das eine Remote Datei kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="8391a-227">Specifies the **PSSession** object to which a remote file is being copied.</span></span> <span data-ttu-id="8391a-228">Wenn Sie diesen Parameter verwenden, verweist der **Ziel** Parameter auf den lokalen Pfad auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="8391a-228">When you use this parameter, the **Destination** parameter refers to the local path on the remote machine.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8391a-229">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8391a-229">-WhatIf</span></span>

<span data-ttu-id="8391a-230">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8391a-230">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="8391a-231">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8391a-231">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="8391a-232">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8391a-232">CommonParameters</span></span>

<span data-ttu-id="8391a-233">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="8391a-233">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="8391a-234">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8391a-234">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8391a-235">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8391a-235">INPUTS</span></span>

### <span data-ttu-id="8391a-236">System.String</span><span class="sxs-lookup"><span data-stu-id="8391a-236">System.String</span></span>

<span data-ttu-id="8391a-237">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="8391a-237">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="8391a-238">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8391a-238">OUTPUTS</span></span>

### <span data-ttu-id="8391a-239">None oder ein Objekt, das das kopierte Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="8391a-239">None or an object representing the copied item</span></span>

<span data-ttu-id="8391a-240">Wenn Sie den **passthru** -Parameter verwenden, gibt dieses Cmdlet ein Objekt zurück, das das kopierte Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="8391a-240">When you use the **PassThru** parameter, this cmdlet returns an object that represents the copied item.</span></span> <span data-ttu-id="8391a-241">Andernfalls generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="8391a-241">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="8391a-242">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8391a-242">NOTES</span></span>

<span data-ttu-id="8391a-243">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="8391a-243">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="8391a-244">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="8391a-244">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="8391a-245">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8391a-245">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="8391a-246">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8391a-246">RELATED LINKS</span></span>

[<span data-ttu-id="8391a-247">about_Providers</span><span class="sxs-lookup"><span data-stu-id="8391a-247">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="8391a-248">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="8391a-248">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="8391a-249">Get-Item</span><span class="sxs-lookup"><span data-stu-id="8391a-249">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="8391a-250">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="8391a-250">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="8391a-251">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="8391a-251">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="8391a-252">Move-Item</span><span class="sxs-lookup"><span data-stu-id="8391a-252">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="8391a-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="8391a-253">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="8391a-254">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="8391a-254">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="8391a-255">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="8391a-255">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="8391a-256">Set-Item</span><span class="sxs-lookup"><span data-stu-id="8391a-256">Set-Item</span></span>](Set-Item.md)

