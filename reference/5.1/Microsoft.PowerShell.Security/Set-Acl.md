---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Acl
ms.openlocfilehash: e2e2166bbe65256c67937be8da1a3e82944840e8
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343232"
---
# <span data-ttu-id="7c473-103">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="7c473-103">Set-Acl</span></span>

## <span data-ttu-id="7c473-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7c473-104">SYNOPSIS</span></span>
<span data-ttu-id="7c473-105">Ändert die Sicherheitsbeschreibung für ein angegebenes Element, z. B. eine Datei oder einen Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="7c473-105">Changes the security descriptor of a specified item, such as a file or a registry key.</span></span>

## <span data-ttu-id="7c473-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7c473-106">SYNTAX</span></span>

### <span data-ttu-id="7c473-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="7c473-107">ByPath (Default)</span></span>

```
Set-Acl [-Path] <String[]> [-AclObject] <Object> [[-CentralAccessPolicy] <String>] [-ClearCentralAccessPolicy]
 [-Passthru] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="7c473-108">Byinputobject</span><span class="sxs-lookup"><span data-stu-id="7c473-108">ByInputObject</span></span>

```
Set-Acl [-InputObject] <PSObject> [-AclObject] <Object> [-Passthru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="7c473-109">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="7c473-109">ByLiteralPath</span></span>

```
Set-Acl -LiteralPath <String[]> [-AclObject] <Object> [[-CentralAccessPolicy] <String>]
 [-ClearCentralAccessPolicy] [-Passthru] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="7c473-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7c473-110">DESCRIPTION</span></span>

<span data-ttu-id="7c473-111">Mit dem- `Set-Acl` Cmdlet wird die Sicherheits Beschreibung für ein angegebenes Element, z. b. eine Datei oder einen Registrierungsschlüssel, so geändert, dass Sie den Werten in einer von Ihnen angegebenen Sicherheits Beschreibung entspricht.</span><span class="sxs-lookup"><span data-stu-id="7c473-111">The `Set-Acl` cmdlet changes the security descriptor of a specified item, such as a file or a registry key, to match the values in a security descriptor that you supply.</span></span>

<span data-ttu-id="7c473-112">Um zu verwenden `Set-Acl` , verwenden Sie den **path** -oder **Inputobject** -Parameter, um das Element zu identifizieren, dessen Sicherheits Beschreibung Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="7c473-112">To use `Set-Acl`, use the **Path** or **InputObject** parameter to identify the item whose security descriptor you want to change.</span></span> <span data-ttu-id="7c473-113">Verwenden Sie dann die Parameter **AclObject** oder **SecurityDescriptor** , um eine Sicherheitsbeschreibung mit den Werten anzugeben, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7c473-113">Then, use the **AclObject** or **SecurityDescriptor** parameters to supply a security descriptor that has the values you want to apply.</span></span> <span data-ttu-id="7c473-114">`Set-Acl` wendet die angegebene Sicherheits Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="7c473-114">`Set-Acl` applies the security descriptor that is supplied.</span></span> <span data-ttu-id="7c473-115">Es verwendet den Wert des **AclObject** -Parameters als Modell und ändert die Werte in der Sicherheitsbeschreibung des Elements, sodass sie den Werten im **AclObject** -Parameter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7c473-115">It uses the value of the **AclObject** parameter as a model and changes the values in the item's security descriptor to match the values in the **AclObject** parameter.</span></span>

## <span data-ttu-id="7c473-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7c473-116">EXAMPLES</span></span>

### <span data-ttu-id="7c473-117">Beispiel 1: Kopieren einer Sicherheits Beschreibung aus einer Datei in eine andere</span><span class="sxs-lookup"><span data-stu-id="7c473-117">Example 1: Copy a security descriptor from one file to another</span></span>

```powershell
$DogACL = Get-Acl -Path "C:\Dog.txt"
Set-Acl -Path "C:\Cat.txt" -AclObject $DogACL
```

<span data-ttu-id="7c473-118">Diese Befehle kopieren die Werte aus der Sicherheitsbeschreibung der Datei „Dog.txt“ in die Sicherheitsbeschreibung der Datei „Cat.txt“.</span><span class="sxs-lookup"><span data-stu-id="7c473-118">These commands copy the values from the security descriptor of the Dog.txt file to the security descriptor of the Cat.txt file.</span></span> <span data-ttu-id="7c473-119">Wenn die Befehle abgeschlossen sind, stimmen die Sicherheitsbeschreibungen von Dog.txt und Cat.txt überein.</span><span class="sxs-lookup"><span data-stu-id="7c473-119">When the commands complete, the security descriptors of the Dog.txt and Cat.txt files are identical.</span></span>

<span data-ttu-id="7c473-120">Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung der Dog.txt Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7c473-120">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>
<span data-ttu-id="7c473-121">Der Zuweisungs Operator ( `=` ) speichert die Sicherheits Beschreibung im Wert der $DogACL Variable.</span><span class="sxs-lookup"><span data-stu-id="7c473-121">The assignment operator (`=`) stores the security descriptor in the value of the $DogACL variable.</span></span>

<span data-ttu-id="7c473-122">Der zweite Befehl verwendet `Set-Acl` , um die Werte in der ACL von Cat.txt in die Werte in zu ändern `$DogACL` .</span><span class="sxs-lookup"><span data-stu-id="7c473-122">The second command uses `Set-Acl` to change the values in the ACL of Cat.txt to the values in `$DogACL`.</span></span>

<span data-ttu-id="7c473-123">Der Wert des **Path** -Parameters ist der Pfad zur Datei „Cat.txt“.</span><span class="sxs-lookup"><span data-stu-id="7c473-123">The value of the **Path** parameter is the path to the Cat.txt file.</span></span> <span data-ttu-id="7c473-124">Der Wert des **aclobject** -Parameters ist die Modell-ACL, in diesem Fall die ACL Dog.txt wie in der `$DogACL` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7c473-124">The value of the **AclObject** parameter is the model ACL, in this case, the ACL of Dog.txt as saved in the `$DogACL` variable.</span></span>

### <span data-ttu-id="7c473-125">Beispiel 2: Verwenden des Pipeline-Operators zum Übergeben eines Deskriptors</span><span class="sxs-lookup"><span data-stu-id="7c473-125">Example 2: Use the pipeline operator to pass a descriptor</span></span>

```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```

<span data-ttu-id="7c473-126">Dieser Befehl ist fast identisch mit dem Befehl im vorherigen Beispiel, mit dem Unterschied, dass er einen Pipeline Operator () verwendet, `|` um die Sicherheits Beschreibung von einem `Get-Acl` Befehl an einen Befehl zu senden `Set-Acl` .</span><span class="sxs-lookup"><span data-stu-id="7c473-126">This command is almost the same as the command in the previous example, except that it uses a pipeline operator (`|`) to send the security descriptor from a `Get-Acl` command to a `Set-Acl` command.</span></span>

<span data-ttu-id="7c473-127">Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung der Dog.txt Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7c473-127">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span> <span data-ttu-id="7c473-128">Der Pipeline Operator ( `|` ) übergibt ein Objekt, das den Dog.txt Sicherheits Deskriptor darstellt, an das `Set-Acl` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7c473-128">The pipeline operator (`|`) passes an object that represents the Dog.txt security descriptor to the `Set-Acl` cmdlet.</span></span>

<span data-ttu-id="7c473-129">Der zweite Befehl verwendet `Set-Acl` , um die Sicherheits Beschreibung von Dog.txt auf Cat.txt anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7c473-129">The second command uses `Set-Acl` to apply the security descriptor of Dog.txt to Cat.txt.</span></span>
<span data-ttu-id="7c473-130">Wenn der Befehl abgeschlossen ist, stimmen die ACLs von Dog.txt und Cat.txt überein.</span><span class="sxs-lookup"><span data-stu-id="7c473-130">When the command completes, the ACLs of the Dog.txt and Cat.txt files are identical.</span></span>

### <span data-ttu-id="7c473-131">Beispiel 3: Anwenden einer Sicherheits Beschreibung auf mehrere Dateien</span><span class="sxs-lookup"><span data-stu-id="7c473-131">Example 3: Apply a security descriptor to multiple files</span></span>

```powershell
$NewAcl = Get-Acl File0.txt
Get-ChildItem -Path "C:\temp" -Recurse -Include "*.txt" -Force | Set-Acl -AclObject $NewAcl
```

<span data-ttu-id="7c473-132">Diese Befehle wenden die Sicherheits Deskriptoren in der File0.txt-Datei auf alle Textdateien im `C:\Temp` Verzeichnis und alle zugehörigen Unterverzeichnisse an.</span><span class="sxs-lookup"><span data-stu-id="7c473-132">These commands apply the security descriptors in the File0.txt file to all text files in the `C:\Temp` directory and all of its subdirectories.</span></span>

<span data-ttu-id="7c473-133">Mit dem ersten Befehl wird die Sicherheits Beschreibung der File0.txt Datei im aktuellen Verzeichnis abgerufen und der Zuweisungs Operator ( `=` ) verwendet, um Sie in der `$NewACL` Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7c473-133">The first command gets the security descriptor of the File0.txt file in the current directory and uses the assignment operator (`=`) to store it in the `$NewACL` variable.</span></span>

<span data-ttu-id="7c473-134">Der erste Befehl in der Pipeline verwendet das Get-ChildItem-Cmdlet, um alle Textdateien im Verzeichnis zu erhalten `C:\Temp` .</span><span class="sxs-lookup"><span data-stu-id="7c473-134">The first command in the pipeline uses the Get-ChildItem cmdlet to get all of the text files in the `C:\Temp` directory.</span></span> <span data-ttu-id="7c473-135">Der **recurse** -Parameter erweitert den-Befehl auf alle Unterverzeichnisse von `C:\temp` .</span><span class="sxs-lookup"><span data-stu-id="7c473-135">The **Recurse** parameter extends the command to all subdirectories of `C:\temp`.</span></span> <span data-ttu-id="7c473-136">Der **include** -Parameter schränkt die Dateien ein, die auf die Dateien mit der `.txt` Dateinamenerweiterung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7c473-136">The **Include** parameter limits the files retrieved to those with the `.txt` file name extension.</span></span> <span data-ttu-id="7c473-137">Der **Force** -Parameter ruft versteckte Dateien ab, die andernfalls ausgeschlossen würden.</span><span class="sxs-lookup"><span data-stu-id="7c473-137">The **Force** parameter gets hidden files, which would otherwise be excluded.</span></span> <span data-ttu-id="7c473-138">(Sie können nicht verwenden `c:\temp\*.txt` , da der **recurse** -Parameter für Verzeichnisse, nicht für Dateien, funktioniert.)</span><span class="sxs-lookup"><span data-stu-id="7c473-138">(You cannot use `c:\temp\*.txt`, because the **Recurse** parameter works on directories, not on files.)</span></span>

<span data-ttu-id="7c473-139">Der Pipeline Operator ( `|` ) sendet die-Objekte, die die abgerufenen Dateien darstellen, an das `Set-Acl` Cmdlet, das die Sicherheits Beschreibung im **aclobject** -Parameter auf alle Dateien in der Pipeline anwendet.</span><span class="sxs-lookup"><span data-stu-id="7c473-139">The pipeline operator (`|`) sends the objects representing the retrieved files to the `Set-Acl` cmdlet, which applies the security descriptor in the **AclObject** parameter to all of the files in the pipeline.</span></span>

<span data-ttu-id="7c473-140">In der Praxis ist es am besten, den **WhatIf** -Parameter mit allen Befehlen zu verwenden `Set-Acl` , die mehr als ein Element beeinflussen können.</span><span class="sxs-lookup"><span data-stu-id="7c473-140">In practice, it is best to use the **WhatIf** parameter with all `Set-Acl` commands that can affect more than one item.</span></span> <span data-ttu-id="7c473-141">In diesem Fall wäre der zweite Befehl in der Pipeline `Set-Acl -AclObject $NewAcl -WhatIf` .</span><span class="sxs-lookup"><span data-stu-id="7c473-141">In this case, the second command in the pipeline would be `Set-Acl -AclObject $NewAcl -WhatIf`.</span></span> <span data-ttu-id="7c473-142">Dieser Befehl listet die Dateien auf, die von dem Befehl betroffen wären.</span><span class="sxs-lookup"><span data-stu-id="7c473-142">This command lists the files that would be affected by the command.</span></span> <span data-ttu-id="7c473-143">Nachdem Sie das Ergebnis überprüft haben, können Sie den Befehl erneut ohne den **WhatIf** -Parameter ausführen.</span><span class="sxs-lookup"><span data-stu-id="7c473-143">After reviewing the result, you can run the command again without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="7c473-144">Beispiel 4: Deaktivieren der Vererbung und beibehalten von vererbten Zugriffsregeln</span><span class="sxs-lookup"><span data-stu-id="7c473-144">Example 4: Disable inheritance and preserve inherited access rules</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="7c473-145">Mit diesen Befehlen wird die Zugriffs Vererbung aus übergeordneten Ordnern deaktiviert, während die vorhandenen vererbten Zugriffsregeln beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="7c473-145">These commands is will disable access inheritance from parent folders, while still preserving the existing inherited access rules.</span></span>

<span data-ttu-id="7c473-146">Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung der Dog.txt Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7c473-146">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="7c473-147">Als nächstes werden Variablen erstellt, um die geerbten Zugriffsregeln in explizite Zugriffsregeln zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7c473-147">Next, variables are created to convert the inherited access rules to explicit access rules.</span></span> <span data-ttu-id="7c473-148">Legen Sie die-Variable auf fest, um die von der Vererbung zugeordneten Zugriffsregeln zu schützen `$isProtected` . Legen Sie auf fest, `$true` um die Vererbung zuzulassen. `$isProtected` `$false`</span><span class="sxs-lookup"><span data-stu-id="7c473-148">To protect the access rules associated with this from inheritance, set the `$isProtected` variable to `$true`.to allow inheritance, set `$isProtected` to `$false`.</span></span> <span data-ttu-id="7c473-149">Weitere Informationen finden Sie unter [Festlegen des Zugriffs Regel Schutzes](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span><span class="sxs-lookup"><span data-stu-id="7c473-149">For more information, see [set access rule protection](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).</span></span>
<span data-ttu-id="7c473-150">Die `$preserveInheritance` Variable, die auf festgelegt ist, `$true` um geerbte Zugriffsregeln beizubehalten; false zum Entfernen geerbte Zugriffsregeln.</span><span class="sxs-lookup"><span data-stu-id="7c473-150">The `$preserveInheritance` variable set to `$true` to preserve inherited access rules; false to remove inherited access rules.</span></span> <span data-ttu-id="7c473-151">Anschließend wird der Schutz der Zugriffsregeln mithilfe der **SetAccessRuleProtection ()** -Methode aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7c473-151">Then the access rule protection is updated using the **SetAccessRuleProtection()** method.</span></span>

<span data-ttu-id="7c473-152">Mit dem letzten Befehl wird verwendet `Set-Acl` , um die Sicherheits Beschreibung von auf Dog.txt anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7c473-152">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="7c473-153">Wenn der Befehl abgeschlossen ist, werden die ACLs der Dog.txt, die aus dem Ordner "Pets" geerbt wurden, direkt auf Dog.txt angewendet, und neue Zugriffsrichtlinien, die Haustiere hinzugefügt werden, ändern nicht den Zugriff auf Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="7c473-153">When the command completes, the ACLs of the Dog.txt that were inherited from the Pets folder will be applied directly to Dog.txt, and new access policies added to Pets will not change the access to Dog.txt.</span></span>

### <span data-ttu-id="7c473-154">Beispiel 5: erteilen der vollständigen Kontrolle der Datei durch Administratoren</span><span class="sxs-lookup"><span data-stu-id="7c473-154">Example 5: Grant Administrators Full Control of the file</span></span>

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
# Set properties
$identity = "BUILTIN\Administrators"
$fileSystemRights = "FullControl"
$type = "Allow"
# Create new rule
$fileSystemAccessRuleArgumentList = $identity, $fileSystemRights, $type
$fileSystemAccessRule = New-Object -TypeName System.Security.AccessControl.FileSystemAccessRule -ArgumentList $fileSystemAccessRuleArgumentList
# Apply new rule
$NewAcl.SetAccessRule($fileSystemAccessRule)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

<span data-ttu-id="7c473-155">Mit diesem Befehl wird der Gruppe " **BUILTIN\Administrators** " die vollständige Kontrolle über die Dog.txt Datei erteilt.</span><span class="sxs-lookup"><span data-stu-id="7c473-155">This command will grant the **BUILTIN\Administrators** group Full control of the Dog.txt file.</span></span>

<span data-ttu-id="7c473-156">Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung der Dog.txt Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7c473-156">The first command uses the `Get-Acl` cmdlet to get the security descriptor of the Dog.txt file.</span></span>

<span data-ttu-id="7c473-157">Die nächsten Variablen werden erstellt, um der Gruppe **BUILTIN\Administrators** die vollständige Kontrolle über die Dog.txt Datei zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="7c473-157">Next variables are created to grant the **BUILTIN\Administrators** group full control of the Dog.txt file.</span></span> <span data-ttu-id="7c473-158">Die `$identity` Variable, die auf den Namen eines [Benutzerkontos](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7c473-158">The `$identity` variable set to the name of a [user account](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor).</span></span> <span data-ttu-id="7c473-159">Die `$fileSystemRights` Variable, die auf FullControl festgelegt ist, und kann einer der [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) -Werte sein, der den Typ des Vorgangs angibt, der der Zugriffs Regel zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7c473-159">The `$fileSystemRights` variable set to FullControl, and can be any one of the [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) values that specifies the type of operation associated with the access rule.</span></span> <span data-ttu-id="7c473-160">Die `$type` Variable, die auf "Allow" festgelegt ist, gibt an, ob der Vorgang zugelassen oder verweigert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c473-160">The `$type` variable set to "Allow" to specifies whether to allow or deny the operation.</span></span> <span data-ttu-id="7c473-161">Die `$fileSystemAccessRuleArgumentList` Variable ist eine Argumentliste, die beim Erstellen des neuen **FileSystemAccessRule** -Objekts übermittelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c473-161">The `$fileSystemAccessRuleArgumentList` variable is an argument list is to be passed when making the new **FileSystemAccessRule** object.</span></span> <span data-ttu-id="7c473-162">Anschließend wird ein neues **FileSystemAccessRule** -Objekt erstellt, und das **FileSystemAccessRule** -Objekt wird an die **SetAccessRule ()** -Methode weitergegeben, fügt die neue Zugriffs Regel hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c473-162">Then a new **FileSystemAccessRule** object is created, and the **FileSystemAccessRule** object is passed to the **SetAccessRule()** method, adds the new access rule.</span></span>

<span data-ttu-id="7c473-163">Mit dem letzten Befehl wird verwendet `Set-Acl` , um die Sicherheits Beschreibung von auf Dog.txt anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7c473-163">The last command uses `Set-Acl` to apply the security descriptor of to Dog.txt.</span></span> <span data-ttu-id="7c473-164">Wenn der Befehl abgeschlossen ist, verfügt die Gruppe " **BUILTIN\Administrators** " über Vollzugriff auf die Dog.txt.</span><span class="sxs-lookup"><span data-stu-id="7c473-164">When the command completes, the **BUILTIN\Administrators** group will have full control of the Dog.txt.</span></span>

## <span data-ttu-id="7c473-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7c473-165">PARAMETERS</span></span>

### <span data-ttu-id="7c473-166">-Aclobject</span><span class="sxs-lookup"><span data-stu-id="7c473-166">-AclObject</span></span>

<span data-ttu-id="7c473-167">Gibt eine ACL mit den gewünschten Eigenschaftswerten an.</span><span class="sxs-lookup"><span data-stu-id="7c473-167">Specifies an ACL with the desired property values.</span></span> <span data-ttu-id="7c473-168">`Set-Acl` ändert die ACL des durch den **path** -oder **Inputobject** -Parameter angegebenen Elements, um die Werte im angegebenen Sicherheits Objekt abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="7c473-168">`Set-Acl` changes the ACL of item specified by the **Path** or **InputObject** parameter to match the values in the specified security object.</span></span>

<span data-ttu-id="7c473-169">Sie können die Ausgabe eines `Get-Acl` Befehls in einer Variablen speichern und dann den **aclobject** -Parameter verwenden, um die Variable zu übergeben, oder einen `Get-Acl` Befehl eingeben.</span><span class="sxs-lookup"><span data-stu-id="7c473-169">You can save the output of a `Get-Acl` command in a variable and then use the **AclObject** parameter to pass the variable, or type a `Get-Acl` command.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7c473-170">-Centralaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="7c473-170">-CentralAccessPolicy</span></span>

<span data-ttu-id="7c473-171">Erstellt oder ändert die zentrale Zugriffsrichtlinie (CAP) des Elements.</span><span class="sxs-lookup"><span data-stu-id="7c473-171">Establishes or changes the central access policy of the item.</span></span>
<span data-ttu-id="7c473-172">Geben Sie die CAP-ID oder den Anzeigenamen einer zentralen Zugriffsrichtlinie auf dem Computer ein.</span><span class="sxs-lookup"><span data-stu-id="7c473-172">Enter the CAP ID or friendly name of a central access policy on the computer.</span></span>

<span data-ttu-id="7c473-173">Ab Windows Server 2012 können Administratoren mit Active Directory und Gruppenrichtlinie zentrale Zugriffsrichtlinien für Benutzer und Gruppen festlegen.</span><span class="sxs-lookup"><span data-stu-id="7c473-173">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span>
<span data-ttu-id="7c473-174">Weitere Informationen finden Sie unter [dynamische Access Control: Szenarioübersicht](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span><span class="sxs-lookup"><span data-stu-id="7c473-174">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="7c473-175">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c473-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7c473-176">-Clearcentralaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="7c473-176">-ClearCentralAccessPolicy</span></span>

<span data-ttu-id="7c473-177">Entfernt die zentrale Zugriffsrichtlinie aus dem angegebenen Element.</span><span class="sxs-lookup"><span data-stu-id="7c473-177">Removes the central access policy from the specified item.</span></span>

<span data-ttu-id="7c473-178">Ab Windows Server 2012 können Administratoren mit Active Directory und Gruppenrichtlinie zentrale Zugriffsrichtlinien für Benutzer und Gruppen festlegen.</span><span class="sxs-lookup"><span data-stu-id="7c473-178">Beginning in Windows Server 2012, administrators can use Active Directory and Group Policy to set central access policies for users and groups.</span></span> <span data-ttu-id="7c473-179">Weitere Informationen finden Sie unter [dynamische Access Control: Szenarioübersicht](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span><span class="sxs-lookup"><span data-stu-id="7c473-179">For more information, see [Dynamic Access Control: Scenario Overview](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).</span></span>

<span data-ttu-id="7c473-180">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c473-180">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7c473-181">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="7c473-181">-Exclude</span></span>

<span data-ttu-id="7c473-182">Lässt die angegebenen Elemente aus.</span><span class="sxs-lookup"><span data-stu-id="7c473-182">Omits the specified items.</span></span> <span data-ttu-id="7c473-183">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="7c473-183">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7c473-184">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="7c473-184">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="7c473-185">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7c473-185">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="7c473-186">-Filter</span><span class="sxs-lookup"><span data-stu-id="7c473-186">-Filter</span></span>

<span data-ttu-id="7c473-187">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="7c473-187">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="7c473-188">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="7c473-188">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7c473-189">Die Syntax des Filters einschließlich der Verwendung von Platzhaltern ist vom Anbieter abhängig.</span><span class="sxs-lookup"><span data-stu-id="7c473-189">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="7c473-190">Filter sind effizienter als andere Parameter, da Sie vom Anbieter beim Abrufen der Objekte angewendet werden, anstatt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="7c473-190">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="7c473-191">-Include</span><span class="sxs-lookup"><span data-stu-id="7c473-191">-Include</span></span>

<span data-ttu-id="7c473-192">Ändert nur die angegebenen Elemente.</span><span class="sxs-lookup"><span data-stu-id="7c473-192">Changes only the specified items.</span></span> <span data-ttu-id="7c473-193">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="7c473-193">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="7c473-194">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="7c473-194">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="7c473-195">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7c473-195">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="7c473-196">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7c473-196">-InputObject</span></span>

<span data-ttu-id="7c473-197">Ändert die Sicherheitsbeschreibung für das angegebene Objekt.</span><span class="sxs-lookup"><span data-stu-id="7c473-197">Changes the security descriptor of the specified object.</span></span> <span data-ttu-id="7c473-198">Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl ein, mit dem das Objekt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7c473-198">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="7c473-199">Sie können das Objekt nicht an die Pipeline übergeben, die geändert werden soll `Set-Acl` .</span><span class="sxs-lookup"><span data-stu-id="7c473-199">You cannot pipe the object to be changed to `Set-Acl`.</span></span> <span data-ttu-id="7c473-200">Verwenden Sie stattdessen den **InputObject** -Parameter explizit im Befehl.</span><span class="sxs-lookup"><span data-stu-id="7c473-200">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="7c473-201">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c473-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7c473-202">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="7c473-202">-LiteralPath</span></span>

<span data-ttu-id="7c473-203">Ändert die Sicherheitsbeschreibung für das angegebene Element.</span><span class="sxs-lookup"><span data-stu-id="7c473-203">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="7c473-204">Im Gegensatz zu **Path** wird der Wert des **LiteralPath** -Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="7c473-204">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="7c473-205">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="7c473-205">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="7c473-206">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen ( `'` ) einschließen.</span><span class="sxs-lookup"><span data-stu-id="7c473-206">If the path includes escape characters, enclose it in single quotation marks (`'`).</span></span>
<span data-ttu-id="7c473-207">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="7c473-207">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="7c473-208">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c473-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7c473-209">-Passthru</span><span class="sxs-lookup"><span data-stu-id="7c473-209">-Passthru</span></span>

<span data-ttu-id="7c473-210">Gibt ein Objekt zurück, das die geänderte Sicherheitsbeschreibung darstellt.</span><span class="sxs-lookup"><span data-stu-id="7c473-210">Returns an object that represents the security descriptor that was changed.</span></span> <span data-ttu-id="7c473-211">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="7c473-211">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7c473-212">-Path</span><span class="sxs-lookup"><span data-stu-id="7c473-212">-Path</span></span>

<span data-ttu-id="7c473-213">Ändert die Sicherheitsbeschreibung für das angegebene Element.</span><span class="sxs-lookup"><span data-stu-id="7c473-213">Changes the security descriptor of the specified item.</span></span> <span data-ttu-id="7c473-214">Geben Sie den Pfad zu einem Element ein, z. B. einen Pfad zu einer Datei oder einem Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="7c473-214">Enter the path to an item, such as a path to a file or registry key.</span></span> <span data-ttu-id="7c473-215">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7c473-215">Wildcards are permitted.</span></span>

<span data-ttu-id="7c473-216">Wenn Sie ein Sicherheits Objekt an übergeben `Set-Acl` (entweder mithilfe des **aclobject** -oder **securityDescriptor** -Parameters oder durch Übergeben eines Sicherheits Objekts von Get-Acl an `Set-Acl` ) und den **path** -Parameter (Name und Wert) weglassen, `Set-Acl` verwendet den Pfad, der im Sicherheits Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7c473-216">If you pass a security object to `Set-Acl` (either by using the **AclObject** or **SecurityDescriptor** parameters or by passing a security object from Get-Acl to `Set-Acl`), and you omit the **Path** parameter (name and value), `Set-Acl` uses the path that is included in the security object.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="7c473-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7c473-217">-Confirm</span></span>

<span data-ttu-id="7c473-218">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7c473-218">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7c473-219">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="7c473-219">-UseTransaction</span></span>

<span data-ttu-id="7c473-220">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="7c473-220">Includes the command in the active transaction.</span></span>
<span data-ttu-id="7c473-221">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7c473-221">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="7c473-222">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="7c473-222">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="7c473-223">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7c473-223">-WhatIf</span></span>

<span data-ttu-id="7c473-224">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7c473-224">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7c473-225">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7c473-225">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7c473-226">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7c473-226">CommonParameters</span></span>

<span data-ttu-id="7c473-227">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7c473-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7c473-228">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7c473-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7c473-229">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7c473-229">INPUTS</span></span>

### <span data-ttu-id="7c473-230">System. Security. AccessControl. ObjectSecurity, System. Security. AccessControl. CommonSecurityDescriptor</span><span class="sxs-lookup"><span data-stu-id="7c473-230">System.Security.AccessControl.ObjectSecurity, System.Security.AccessControl.CommonSecurityDescriptor</span></span>

<span data-ttu-id="7c473-231">Sie können ein ACL-Objekt oder eine Sicherheits Beschreibung an die Pipeline übergeben `Set-Acl` .</span><span class="sxs-lookup"><span data-stu-id="7c473-231">You can pipe an ACL object or a security descriptor to `Set-Acl`.</span></span>

## <span data-ttu-id="7c473-232">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7c473-232">OUTPUTS</span></span>

### <span data-ttu-id="7c473-233">System. Security. AccessControl. File Security</span><span class="sxs-lookup"><span data-stu-id="7c473-233">System.Security.AccessControl.FileSecurity</span></span>

<span data-ttu-id="7c473-234">Standardmäßig `Set-Acl` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7c473-234">By default, `Set-Acl` does not generate any output.</span></span> <span data-ttu-id="7c473-235">Allerdings wird bei Verwendung des **Passthru** -Parameters ein Sicherheitsobjekt generiert.</span><span class="sxs-lookup"><span data-stu-id="7c473-235">However, if you use the **Passthru** parameter, it generates a security object.</span></span> <span data-ttu-id="7c473-236">Der Typ des Sicherheitsobjekts hängt vom Typ des Elements ab.</span><span class="sxs-lookup"><span data-stu-id="7c473-236">The type of the security object depends on the type of the item.</span></span>

## <span data-ttu-id="7c473-237">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7c473-237">NOTES</span></span>

<span data-ttu-id="7c473-238">Das `Set-Acl` -Cmdlet wird vom PowerShell-Dateisystem und von Registrierungs Anbietern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7c473-238">The `Set-Acl` cmdlet is supported by the PowerShell file system and registry providers.</span></span> <span data-ttu-id="7c473-239">Sie können es verwenden, um die Sicherheitsbeschreibungen von Dateien, Verzeichnissen und Registrierungsschlüsseln zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7c473-239">As such, you can use it to change the security descriptors of files, directories, and registry keys.</span></span>

## <span data-ttu-id="7c473-240">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7c473-240">RELATED LINKS</span></span>

[<span data-ttu-id="7c473-241">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="7c473-241">Get-Acl</span></span>](Get-Acl.md)

[<span data-ttu-id="7c473-242">FileSystemAccessRule</span><span class="sxs-lookup"><span data-stu-id="7c473-242">FileSystemAccessRule</span></span>](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)

[<span data-ttu-id="7c473-243">ObjectSecurity. SetAccessRuleProtection</span><span class="sxs-lookup"><span data-stu-id="7c473-243">ObjectSecurity.SetAccessRuleProtection</span></span>](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)

[<span data-ttu-id="7c473-244">File System Rights</span><span class="sxs-lookup"><span data-stu-id="7c473-244">FileSystemRights</span></span>](/dotnet/api/system.security.accesscontrol.filesystemrights)
