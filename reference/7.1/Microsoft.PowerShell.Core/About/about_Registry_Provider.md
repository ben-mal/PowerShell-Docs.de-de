---
description: Registrierung
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_registry_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Registrierungsanbieter
ms.openlocfilehash: e97fc607c456909dc0abdb50cb7dd5b5847998a0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223596"
---
# <a name="registry-provider"></a><span data-ttu-id="375a8-104">Registrierungs Anbieter</span><span class="sxs-lookup"><span data-stu-id="375a8-104">Registry provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="375a8-105">Anbietername</span><span class="sxs-lookup"><span data-stu-id="375a8-105">Provider name</span></span>

<span data-ttu-id="375a8-106">Registrierung</span><span class="sxs-lookup"><span data-stu-id="375a8-106">Registry</span></span>

## <a name="drives"></a><span data-ttu-id="375a8-107">Laufwerke</span><span class="sxs-lookup"><span data-stu-id="375a8-107">Drives</span></span>

<span data-ttu-id="375a8-108">`HKLM:`, `HKCU:`</span><span class="sxs-lookup"><span data-stu-id="375a8-108">`HKLM:`, `HKCU:`</span></span>

## <a name="capabilities"></a><span data-ttu-id="375a8-109">Funktionen</span><span class="sxs-lookup"><span data-stu-id="375a8-109">Capabilities</span></span>

<span data-ttu-id="375a8-110">Nicht **verarbeiten** , **usetransactions**</span><span class="sxs-lookup"><span data-stu-id="375a8-110">**ShouldProcess** , **UseTransactions**</span></span>

## <a name="short-description"></a><span data-ttu-id="375a8-111">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="375a8-111">Short description</span></span>

<span data-ttu-id="375a8-112">Ermöglicht den Zugriff auf die Registrierungsschlüssel, Einträge und Werte in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="375a8-112">Provides access to the registry keys, entries, and values in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="375a8-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="375a8-113">Detailed description</span></span>

<span data-ttu-id="375a8-114">Mit dem PowerShell- **Registrierungs** Anbieter können Sie Registrierungsschlüssel, Einträge und Werte in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.</span><span class="sxs-lookup"><span data-stu-id="375a8-114">The PowerShell **Registry** provider lets you get, add, change, clear, and delete registry keys, entries, and values in PowerShell.</span></span>

<span data-ttu-id="375a8-115">Die **Registrierungs** Laufwerke sind ein hierarchischer Namespace, der die Registrierungsschlüssel und Unterschlüssel auf dem Computer enthält.</span><span class="sxs-lookup"><span data-stu-id="375a8-115">The **Registry** drives are a hierarchical namespace containing the registry keys and subkeys on your computer.</span></span> <span data-ttu-id="375a8-116">Registrierungseinträge und Werte sind keine Komponenten dieser Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="375a8-116">Registry entries and values are not components of that hierarchy.</span></span> <span data-ttu-id="375a8-117">Stattdessen sind sie Eigenschaften des jeweiligen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="375a8-117">Instead, they are properties of each of the keys.</span></span>

<span data-ttu-id="375a8-118">Der **Registrierungs** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="375a8-118">The **Registry** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="375a8-119">Get-Location</span><span class="sxs-lookup"><span data-stu-id="375a8-119">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="375a8-120">Set-Location</span><span class="sxs-lookup"><span data-stu-id="375a8-120">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="375a8-121">Get-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-121">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="375a8-122">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="375a8-122">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="375a8-123">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-123">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="375a8-124">Move-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-124">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="375a8-125">New-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-125">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="375a8-126">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-126">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="375a8-127">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-127">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="375a8-128">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-128">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="375a8-129">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-129">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="375a8-130">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-130">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="375a8-131">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="375a8-131">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="375a8-132">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="375a8-132">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="375a8-133">Von diesem Anbieter verfügbar gemachte Typen</span><span class="sxs-lookup"><span data-stu-id="375a8-133">Types exposed by this provider</span></span>

<span data-ttu-id="375a8-134">Registrierungsschlüssel werden als Instanzen der [Microsoft. Win32. RegistryKey](/dotnet/api/microsoft.win32.registrykey) -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="375a8-134">Registry keys are represented as instances of the [Microsoft.Win32.RegistryKey](/dotnet/api/microsoft.win32.registrykey) class.</span></span> <span data-ttu-id="375a8-135">Registrierungseinträge werden als Instanzen der Klasse [pscustomobject](/dotnet/api/system.management.automation.pscustomobject) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="375a8-135">Registry entries are represented as instances of the [PSCustomObject](/dotnet/api/system.management.automation.pscustomobject) class.</span></span>

## <a name="navigating-the-registry-drives"></a><span data-ttu-id="375a8-136">Navigieren in den Registrierungs Laufwerken</span><span class="sxs-lookup"><span data-stu-id="375a8-136">Navigating the Registry drives</span></span>

<span data-ttu-id="375a8-137">Der **Registrierungs** Anbieter stellt seinen Datenspeicher als zwei Standard Laufwerke zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="375a8-137">The **Registry** provider exposes its data store as two default drives.</span></span> <span data-ttu-id="375a8-138">Der Registrierungs Speicherort HKEY_LOCAL_MACHINE der dem Laufwerk zugeordnet ist `HKLM:` und dem Laufwerk HKEY_CURRENT_USER zugeordnet ist `HKCU:` .</span><span class="sxs-lookup"><span data-stu-id="375a8-138">The registry location HKEY_LOCAL_MACHINE is mapped to the `HKLM:` drive and HKEY_CURRENT_USER is mapped to the `HKCU:` drive.</span></span> <span data-ttu-id="375a8-139">Wenn Sie mit der Registrierung arbeiten möchten, können Sie den Speicherort `HKLM:` mit dem folgenden Befehl auf das Laufwerk umstellen.</span><span class="sxs-lookup"><span data-stu-id="375a8-139">To work with the registry, you can change your location to the `HKLM:` drive using the following command.</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="375a8-140">Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein.</span><span class="sxs-lookup"><span data-stu-id="375a8-140">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="375a8-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="375a8-141">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="375a8-142">Sie können auch mit dem **Registrierungs** Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="375a8-142">You can also work with the **Registry** provider from any other PowerShell drive.</span></span> <span data-ttu-id="375a8-143">Um auf einen Registrierungsschlüssel von einem anderen Speicherort zu verweisen, verwenden Sie den Laufwerk Namen ( `HKLM:` , `HKCU:` ) im Pfad.</span><span class="sxs-lookup"><span data-stu-id="375a8-143">To reference a registry key from another location, use the drive name (`HKLM:`, `HKCU:`) in the path.</span></span> <span data-ttu-id="375a8-144">Verwenden Sie einen umgekehrten Schrägstrich ( \\ ) oder einen Schrägstrich (/), um eine Ebene des **Registrierungs** Laufwerks anzugeben.</span><span class="sxs-lookup"><span data-stu-id="375a8-144">Use a backslash (\\) or a forward slash (/) to indicate a level of the **Registry** drive.</span></span>

```powershell
PS C:\> cd HKLM:\Software
```

> [!NOTE]
> <span data-ttu-id="375a8-145">PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten.</span><span class="sxs-lookup"><span data-stu-id="375a8-145">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="375a8-146">Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="375a8-146">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location), and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

<span data-ttu-id="375a8-147">Das letzte Beispiel zeigt eine weitere Pfad Syntax, die Sie verwenden können, um durch den **Registrierungs** Anbieter zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="375a8-147">This last example shows another path syntax you can use to navigate the **Registry** provider.</span></span> <span data-ttu-id="375a8-148">Diese Syntax verwendet den Anbieter Namen, gefolgt von zwei Doppelpunkten `::` .</span><span class="sxs-lookup"><span data-stu-id="375a8-148">This syntax uses the provider name, followed by two colons `::`.</span></span> <span data-ttu-id="375a8-149">Mit dieser Syntax können Sie anstelle des zugeordneten Laufwerks namens den vollständigen Hive-Namen verwenden `HKLM` .</span><span class="sxs-lookup"><span data-stu-id="375a8-149">This syntax allows you to use the full HIVE name, instead of the mapped drive name `HKLM`.</span></span>

```powershell
cd "Registry::HKEY_LOCAL_MACHINE\Software"
```

## <a name="displaying-the-contents-of-registry-keys"></a><span data-ttu-id="375a8-150">Anzeigen des Inhalts von Registrierungs Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="375a8-150">Displaying the contents of registry keys</span></span>

<span data-ttu-id="375a8-151">Die Registrierung ist in Schlüssel, Unterschlüssel und Einträge unterteilt.</span><span class="sxs-lookup"><span data-stu-id="375a8-151">The registry is divided into keys, subkeys, and entries.</span></span> <span data-ttu-id="375a8-152">Weitere Informationen zur Registrierungs Struktur finden Sie unter [Struktur der Registrierung](/windows/desktop/sysinfo/structure-of-the-registry).</span><span class="sxs-lookup"><span data-stu-id="375a8-152">For more information about registry structure, see [Structure of the Registry](/windows/desktop/sysinfo/structure-of-the-registry).</span></span>

<span data-ttu-id="375a8-153">In einem **Registrierungs** Laufwerk ist jeder Schlüssel ein Container.</span><span class="sxs-lookup"><span data-stu-id="375a8-153">In a **Registry** drive, each key is a container.</span></span> <span data-ttu-id="375a8-154">Ein Schlüssel kann eine beliebige Anzahl von Schlüsseln enthalten.</span><span class="sxs-lookup"><span data-stu-id="375a8-154">A key can contain any number of keys.</span></span> <span data-ttu-id="375a8-155">Ein Registrierungsschlüssel, der über einen übergeordneten Schlüssel verfügt, wird als Unterschlüssel bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="375a8-155">A registry key that has a parent key is called a subkey.</span></span> <span data-ttu-id="375a8-156">Sie können verwenden `Get-ChildItem` , um Registrierungsschlüssel anzuzeigen und `Set-Location` zu einem Schlüssel Pfad zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="375a8-156">You can use `Get-ChildItem` to view registry keys and `Set-Location` to navigate to a key path.</span></span>

<span data-ttu-id="375a8-157">Registrierungs Werte sind Attribute eines Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="375a8-157">Registry values are attributes of a registry key.</span></span> <span data-ttu-id="375a8-158">Im **Registrierungs** Laufwerk werden Sie als **Element Eigenschaften** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="375a8-158">In the **Registry** drive, they are called **Item Properties**.</span></span> <span data-ttu-id="375a8-159">Ein Registrierungsschlüssel kann sowohl untergeordnete Schlüssel als auch Element Eigenschaften haben.</span><span class="sxs-lookup"><span data-stu-id="375a8-159">A registry key can have both children keys and item properties.</span></span>

<span data-ttu-id="375a8-160">In diesem Beispiel wird der Unterschied zwischen `Get-Item` und `Get-ChildItem` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="375a8-160">In this example, the difference between `Get-Item` and `Get-ChildItem` is shown.</span></span> <span data-ttu-id="375a8-161">Wenn Sie `Get-Item` den "Spooler"-Registrierungsschlüssel verwenden, können Sie dessen Eigenschaften anzeigen.</span><span class="sxs-lookup"><span data-stu-id="375a8-161">When you use `Get-Item` on the "Spooler" registry key, you can view its properties.</span></span>

```
PS C:\ > Get-Item -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services


Name        Property
----        --------
Spooler     DependOnService    : {RPCSS, http}
            Description        : @%systemroot%\system32\spoolsv.exe,-2
            DisplayName        : @%systemroot%\system32\spoolsv.exe,-1
            ErrorControl       : 1
            FailureActions     : {16, 14, 0, 0...}
            Group              : SpoolerGroup
            ImagePath          : C:\WINDOWS\System32\spoolsv.exe
            ObjectName         : LocalSystem
            RequiredPrivileges : {SeTcbPrivilege, SeImpersonatePrivilege, ...
            ServiceSidType     : 1
            Start              : 2
            Type               : 27
```

<span data-ttu-id="375a8-162">Jeder Registrierungsschlüssel kann auch Unterschlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="375a8-162">Each registry key can also have subkeys.</span></span> <span data-ttu-id="375a8-163">Wenn Sie `Get-Item` für einen Registrierungsschlüssel verwenden, werden die Unterschlüssel nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="375a8-163">When you use `Get-Item` on a registry key, the subkeys are not displayed.</span></span> <span data-ttu-id="375a8-164">`Get-ChildItem`Mit dem-Cmdlet werden die untergeordneten Elemente der "Spooler"-Taste angezeigt, einschließlich der Eigenschaften des unter Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="375a8-164">The `Get-ChildItem` cmdlet will show you children items of the "Spooler" key, including each subkey's properties.</span></span> <span data-ttu-id="375a8-165">Die Eigenschaften der übergeordneten Schlüssel werden bei Verwendung von nicht angezeigt `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="375a8-165">The parent keys properties are not shown when using `Get-ChildItem`.</span></span>

```
PS C:\> Get-ChildItem -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Spooler


Name             Property
----             --------
Performance      Close           : PerfClose
                 Collect         : PerfCollect
                 Collect Timeout : 2000
                 Library         : C:\Windows\System32\winspool.drv
                 Object List     : 1450
                 Open            : PerfOpen
                 Open Timeout    : 4000
Security         Security : {1, 0, 20, 128...}
```

<span data-ttu-id="375a8-166">Das- `Get-Item` Cmdlet kann auch am aktuellen Speicherort verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="375a8-166">The `Get-Item` cmdlet can also be used on the current location.</span></span> <span data-ttu-id="375a8-167">Im folgenden Beispiel wird zum "Spooler"-Registrierungsschlüssel navigiert, und die Element Eigenschaften werden abgerufen.</span><span class="sxs-lookup"><span data-stu-id="375a8-167">The following example navigates to the "Spooler" registry key and gets the item properties.</span></span>
<span data-ttu-id="375a8-168">Der Punkt `.` wird verwendet, um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="375a8-168">The dot `.` is used to indicate the current location.</span></span>

```
PS C:\> cd HKLM:\System\CurrentControlSet\Services\Spooler
PS HKLM:\SYSTEM\CurrentControlSet\Services\Spooler> Get-Item .

    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services

Name             Property
----             --------
Spooler          DependOnService    : {RPCSS, http}
                 Description        : @%systemroot%\system32\spoolsv.exe,-2
...
```

<span data-ttu-id="375a8-169">Weitere Informationen zu den in diesem Abschnitt behandelten Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="375a8-169">For more information on the cmdlets covered in this section, see the following articles.</span></span>

<span data-ttu-id="375a8-170">-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) 
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span><span class="sxs-lookup"><span data-stu-id="375a8-170">-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
-[Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span></span>

## <a name="viewing-registry-key-values"></a><span data-ttu-id="375a8-171">Anzeigen von Registrierungsschlüssel Werten</span><span class="sxs-lookup"><span data-stu-id="375a8-171">Viewing registry key values</span></span>

<span data-ttu-id="375a8-172">Registrierungsschlüssel Werte werden als Eigenschaften der einzelnen Registrierungsschlüssel gespeichert.</span><span class="sxs-lookup"><span data-stu-id="375a8-172">Registry key values are stored as properties of each registry key.</span></span> <span data-ttu-id="375a8-173">Das `Get-ItemProperty` Cmdlet zeigt die Registrierungsschlüssel Eigenschaften mit dem von Ihnen angegebenen Namen an.</span><span class="sxs-lookup"><span data-stu-id="375a8-173">The `Get-ItemProperty` cmdlet views registry key properties using the name you specify.</span></span> <span data-ttu-id="375a8-174">Das Ergebnis ist ein **pscustomobject** mit den von Ihnen angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="375a8-174">The result is a **PSCustomObject** containing the properties you specify.</span></span>

<span data-ttu-id="375a8-175">Im folgenden Beispiel wird das- `Get-ItemProperty` Cmdlet verwendet, um alle Eigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="375a8-175">The Following example uses the `Get-ItemProperty` cmdlet to view all properties.</span></span> <span data-ttu-id="375a8-176">Wenn Sie das resultierende Objekt in einer Variablen speichern, können Sie auf den gewünschten Eigenschafts Wert zugreifen.</span><span class="sxs-lookup"><span data-stu-id="375a8-176">Storing the resulting object in a variable allows you to access the desired property value.</span></span>

```powershell
$p = Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler
$p.DependOnService
```

```output
RPCSS
http
```

<span data-ttu-id="375a8-177">Wenn Sie einen Wert für den Parameter angeben, werden `-Name` die von Ihnen angegebenen Eigenschaften ausgewählt und das **pscustomobject-Objekt** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="375a8-177">Specifying a value for the `-Name` parameter selects the properties you specify and returns the **PSCustomObject**.</span></span>  <span data-ttu-id="375a8-178">Das folgende Beispiel zeigt den Unterschied in der Ausgabe, wenn Sie den- `-Name` Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="375a8-178">The following example shows the difference in output when you use the `-Name` parameter.</span></span>

```
PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem

BUILD                      : 17134.1
Installation Directory     : C:\WINDOWS\system32\WBEM
MOF Self-Install Directory : C:\WINDOWS\system32\WBEM\MOF
PSPath                     : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath               : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName                : Wbem
PSDrive                    : HKLM
PSProvider                 : Microsoft.PowerShell.Core\Registry

PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD

BUILD        : 17134.1
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName  : Wbem
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
```

<span data-ttu-id="375a8-179">Ab PowerShell 5,0 `Get-ItemPropertyValue` gibt das Cmdlet nur den Wert der angegebenen Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="375a8-179">Beginning in PowerShell 5.0, the `Get-ItemPropertyValue` cmdlet returns only the value of the property you specify.</span></span>

```powershell
Get-ItemPropertyValue -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD
```

```output
17134.1
```

<span data-ttu-id="375a8-180">Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="375a8-180">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="375a8-181">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-181">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="375a8-182">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="375a8-182">Get-ItemPropertyValue</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)

## <a name="changing-registry-key-values"></a><span data-ttu-id="375a8-183">Ändern von Registrierungsschlüssel Werten</span><span class="sxs-lookup"><span data-stu-id="375a8-183">Changing registry key values</span></span>

<span data-ttu-id="375a8-184">Mit dem- `Set-ItemProperty` Cmdlet werden die Attribute für Registrierungsschlüssel festgelegt.</span><span class="sxs-lookup"><span data-stu-id="375a8-184">The `Set-ItemProperty` cmdlet will set attributes for registry keys.</span></span> <span data-ttu-id="375a8-185">Im folgenden Beispiel wird verwendet `Set-ItemProperty` , um den Starttyp des Spoolerdiensts in manuell zu ändern.</span><span class="sxs-lookup"><span data-stu-id="375a8-185">The following example uses `Set-ItemProperty` to change the spooler service start type to manual.</span></span> <span data-ttu-id="375a8-186">Im Beispiel wird der **StartType** mithilfe des Cmdlets wieder in " *automatisch* " geändert `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="375a8-186">The example changes the **StartType** back to *Automatic* using the `Set-Service` cmdlet.</span></span>

```
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler Automatic

PS C:\> $path = "HKLM:\SYSTEM\CurrentControlSet\Services\Spooler\"
PS C:\> Set-ItemProperty -Path $path -Name Start -Value 3
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler    Manual

PS C:\> Set-Service -Name Spooler -StartupType Automatic
```

<span data-ttu-id="375a8-187">Jeder Registrierungsschlüssel hat einen *Standard* Wert.</span><span class="sxs-lookup"><span data-stu-id="375a8-187">Each registry key has a *default* value.</span></span> <span data-ttu-id="375a8-188">Sie können den *Standard* Wert für einen Registrierungsschlüssel entweder mit `Set-Item` oder ändern `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="375a8-188">You can change the *default* value for a registry key with either `Set-Item` or `Set-ItemProperty`.</span></span>

```powershell
Set-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name "(default)" -Value "one"
Set-Item -Path HKLM:\SOFTWARE\Contoso -Value "two"
```

<span data-ttu-id="375a8-189">Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="375a8-189">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="375a8-190">Set-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-190">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="375a8-191">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-191">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="creating-registry-keys-and-values"></a><span data-ttu-id="375a8-192">Erstellen von Registrierungs Schlüsseln und-Werten</span><span class="sxs-lookup"><span data-stu-id="375a8-192">Creating registry keys and values</span></span>

<span data-ttu-id="375a8-193">Mit dem- `New-Item` Cmdlet werden Registrierungsschlüssel mit einem von Ihnen bereitgestellten Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="375a8-193">The `New-Item` cmdlet will create registry keys with a name that you provide.</span></span>
<span data-ttu-id="375a8-194">Sie können auch die- `mkdir` Funktion verwenden, die das `New-Item` Cmdlet intern aufruft.</span><span class="sxs-lookup"><span data-stu-id="375a8-194">You can also use the `mkdir` function, which calls the `New-Item` cmdlet internally.</span></span>

```
PS HKLM:\SOFTWARE\> mkdir ContosoCompany

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
ContosoCompany
```

<span data-ttu-id="375a8-195">Sie können das `New-ItemProperty` Cmdlet verwenden, um Werte in einem von Ihnen angegebenen Registrierungsschlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="375a8-195">You can use the `New-ItemProperty` cmdlet to create values in a registry key that you specify.</span></span> <span data-ttu-id="375a8-196">Im folgenden Beispiel wird ein neuer DWORD-Wert im Registrierungsschlüssel "contosocompany" erstellt.</span><span class="sxs-lookup"><span data-stu-id="375a8-196">The following example creates a new DWORD value on the ContosoCompany registry key.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\ContosoCompany"
New-ItemProperty -Path  -Name Test -Type DWORD -Value 1
```

> [!NOTE]
> <span data-ttu-id="375a8-197">Weitere zulässige Typwerte finden Sie im Abschnitt "dynamische Parameter" in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="375a8-197">Review the dynamic parameters section in this article for other allowed type values.</span></span>

<span data-ttu-id="375a8-198">Ausführliche Informationen zur Verwendung von Cmdlets finden Sie unter [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).</span><span class="sxs-lookup"><span data-stu-id="375a8-198">For detailed cmdlet usage, see [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).</span></span>

## <a name="copying-registry-keys-and-values"></a><span data-ttu-id="375a8-199">Kopieren von Registrierungs Schlüsseln und-Werten</span><span class="sxs-lookup"><span data-stu-id="375a8-199">Copying registry keys and values</span></span>

<span data-ttu-id="375a8-200">Verwenden Sie **Registry** das `Copy-Item` Cmdlet zum Kopieren von Registrierungs Schlüsseln und-Werten im Registrierungs Anbieter.</span><span class="sxs-lookup"><span data-stu-id="375a8-200">In the **Registry** provider, use the `Copy-Item` cmdlet copies registry keys and values.</span></span> <span data-ttu-id="375a8-201">Verwenden Sie das- `Copy-ItemProperty` Cmdlet, um nur Registrierungs Werte zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="375a8-201">Use the `Copy-ItemProperty` cmdlet to copy registry values only.</span></span>
<span data-ttu-id="375a8-202">Mit dem folgenden Befehl werden der Registrierungsschlüssel "%% amp; quot;" und seine Eigenschaften an den angegebenen Speicherort "HKLM: \ software\fabrikam" kopiert.</span><span class="sxs-lookup"><span data-stu-id="375a8-202">The following command copies the "Contoso" registry key, and its properties to the specified location "HKLM:\Software\Fabrikam".</span></span>

<span data-ttu-id="375a8-203">`Copy-Item` erstellt den Ziel Schlüssel, wenn er nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="375a8-203">`Copy-Item` creates the destination key if it does not exist.</span></span> <span data-ttu-id="375a8-204">Wenn der Ziel Schlüssel vorhanden ist, wird von `Copy-Item` ein Duplikat des Quell Schlüssels als untergeordnetes Element (Unterschlüssel) des Ziel Schlüssels erstellt.</span><span class="sxs-lookup"><span data-stu-id="375a8-204">If the destination key exists, `Copy-Item` creates a duplicate of the source key as a child item (subkey) of the destination key.</span></span>

```powershell
Copy-Item -Path  HKLM:\Software\Contoso -Destination HKLM:\Software\Fabrikam
```

<span data-ttu-id="375a8-205">Der folgende Befehl verwendet das `Copy-ItemProperty` Cmdlet, um den Wert "Server" aus dem Schlüssel "" in den Schlüssel "Fabrikam" zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="375a8-205">The following command uses the `Copy-ItemProperty` cmdlet to copy the "Server" value from the "Contoso" key to the "Fabrikam" key.</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Copy-ItemProperty -Path $source -Destination $dest -Name Server
```

<span data-ttu-id="375a8-206">Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="375a8-206">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="375a8-207">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-207">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="375a8-208">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-208">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

## <a name="moving-registry-keys-and-values"></a><span data-ttu-id="375a8-209">Verschieben von Registrierungs Schlüsseln und-Werten</span><span class="sxs-lookup"><span data-stu-id="375a8-209">Moving registry keys and values</span></span>

<span data-ttu-id="375a8-210">Die `Move-Item` `Move-ItemProperty` Cmdlets und Verhalten sich wie Ihre "Copy"-Entsprechungen.</span><span class="sxs-lookup"><span data-stu-id="375a8-210">The `Move-Item` and `Move-ItemProperty` cmdlets behave like their "Copy" counterparts.</span></span> <span data-ttu-id="375a8-211">Wenn das Ziel vorhanden ist, `Move-Item` Verschiebt den Quell Schlüssel unterhalb des Ziel Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="375a8-211">If the destination exists, `Move-Item` moves the source key underneath the destination key.</span></span> <span data-ttu-id="375a8-212">Wenn der Ziel Schlüssel nicht vorhanden ist, wird der Quell Schlüssel in den Zielpfad verschoben.</span><span class="sxs-lookup"><span data-stu-id="375a8-212">If the destination key does not exist, the source key is moved to the destination path.</span></span>

<span data-ttu-id="375a8-213">Mit dem folgenden Befehl wird der Schlüssel "fitoso" in den Pfad "HKLM: \ software\fabrikam" verschoben.</span><span class="sxs-lookup"><span data-stu-id="375a8-213">The following command moves the "Contoso" key to the path "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
Move-Item -Path HKLM:\SOFTWARE\Contoso -Destination HKLM:\SOFTWARE\Fabrikam
```

<span data-ttu-id="375a8-214">Mit diesem Befehl werden alle Eigenschaften von "HKLM: \ software\contosocompany" nach "HKLM: \ software\fabrikam" verschoben.</span><span class="sxs-lookup"><span data-stu-id="375a8-214">This command moves all of the properties from "HKLM:\SOFTWARE\ContosoCompany" to "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Move-ItemProperty -Path $source -Destination $dest -Name *
```

<span data-ttu-id="375a8-215">Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="375a8-215">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="375a8-216">Move-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-216">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="375a8-217">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-217">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)

## <a name="renaming-registry-keys-and-values"></a><span data-ttu-id="375a8-218">Umbenennen von Registrierungs Schlüsseln und-Werten</span><span class="sxs-lookup"><span data-stu-id="375a8-218">Renaming registry keys and values</span></span>

<span data-ttu-id="375a8-219">Sie können Registrierungsschlüssel und-Werte genau wie Dateien und Ordner umbenennen.</span><span class="sxs-lookup"><span data-stu-id="375a8-219">You can rename registry keys and values just like you would files and folders.</span></span>
<span data-ttu-id="375a8-220">`Rename-Item` benennt Registrierungsschlüssel um und benennt `Rename-ItemProperty` Registrierungs Werte um.</span><span class="sxs-lookup"><span data-stu-id="375a8-220">`Rename-Item` renames registry keys, while `Rename-ItemProperty` renames registry values.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\Contoso"
Rename-ItemProperty -Path $path -Name ContosoTest -NewName FabrikamTest
Rename-Item -Path $path -NewName Fabrikam
```

## <a name="changing-security-descriptors"></a><span data-ttu-id="375a8-221">Ändern von Sicherheits Deskriptoren</span><span class="sxs-lookup"><span data-stu-id="375a8-221">Changing security descriptors</span></span>

<span data-ttu-id="375a8-222">Sie können den Zugriff auf Registrierungsschlüssel mithilfe der `Get-Acl` `Set-Acl` Cmdlets und einschränken.</span><span class="sxs-lookup"><span data-stu-id="375a8-222">You can restrict access to registry keys using the `Get-Acl` and `Set-Acl` cmdlets.</span></span> <span data-ttu-id="375a8-223">Im folgenden Beispiel wird ein neuer Benutzer mit Vollzugriff dem Registrierungsschlüssel "HKLM: \ software\configuration Manager" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="375a8-223">The following example adds a new user with full control to the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Contoso
$rule = New-Object System.Security.AccessControl.RegistryAccessRule `
("CONTOSO\jsmith", "FullControl", "Allow")
$acl.SetAccessRule($rule)
$acl | Set-Acl -Path HKLM:\SOFTWARE\Contoso
```

<span data-ttu-id="375a8-224">Weitere Beispiele und Informationen zur Verwendung von Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="375a8-224">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="375a8-225">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="375a8-225">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="375a8-226">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="375a8-226">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="removing-and-clearing-registry-keys-and-values"></a><span data-ttu-id="375a8-227">Entfernen und Löschen von Registrierungs Schlüsseln und-Werten</span><span class="sxs-lookup"><span data-stu-id="375a8-227">Removing and clearing registry keys and values</span></span>

<span data-ttu-id="375a8-228">Mit **Remove-Item** können Sie enthaltene Elemente entfernen. Sie werden jedoch aufgefordert, das Entfernen zu bestätigen, wenn das Element etwas anderes enthält.</span><span class="sxs-lookup"><span data-stu-id="375a8-228">You can remove contained items by using **Remove-Item** , but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="375a8-229">Im folgenden Beispiel wird versucht, den Schlüssel "HKLM: \ software\configuration Manager" zu löschen.</span><span class="sxs-lookup"><span data-stu-id="375a8-229">The following example attempts to delete a key "HKLM:\SOFTWARE\Contoso".</span></span>

```
PS C:\> dir HKLM:\SOFTWARE\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Contoso

Name                           Property
----                           --------
ChildKey

PS C:\> Remove-Item -Path HKLM:\SOFTWARE\Contoso

Confirm
The item at HKLM:\SOFTWARE\Contoso has children and the -Recurse
parameter was not specified. If you continue, all children will be removed
with the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

<span data-ttu-id="375a8-230">Wenn Sie enthaltene Elemente ohne Aufforderung löschen möchten, geben Sie den- `-Recurse` Parameter an.</span><span class="sxs-lookup"><span data-stu-id="375a8-230">To delete contained items without prompting, specify the `-Recurse` parameter.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso -Recurse
```

<span data-ttu-id="375a8-231">Wenn Sie alle Elemente in "HKLM: \ software\configuration Manager", aber nicht "HKLM: \ software\c" selbst entfernen möchten, verwenden Sie einen nachfolgenden umgekehrten Schrägstrich, `\` gefolgt von einem Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="375a8-231">If you wanted to remove all items within "HKLM:\SOFTWARE\Contoso" but not "HKLM:\SOFTWARE\Contoso" itself, use a trailing backslash `\` followed by a wildcard.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso\* -Recurse
```

<span data-ttu-id="375a8-232">Mit diesem Befehl wird der Registrierungs Wert "ContosoTest" aus dem Registrierungsschlüssel "HKLM: \ software\contoso" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="375a8-232">This command deletes the "ContosoTest" registry value from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name ContosoTest
```

<span data-ttu-id="375a8-233">`Clear-Item` Löscht alle Registrierungs Werte für einen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="375a8-233">`Clear-Item` clears all registry values for a key.</span></span> <span data-ttu-id="375a8-234">Im folgenden Beispiel werden alle Werte aus dem Registrierungsschlüssel "HKLM: \ software\c" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="375a8-234">The following example clears all values from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span> <span data-ttu-id="375a8-235">Verwenden Sie, um nur eine bestimmte Eigenschaft zu löschen `Clear-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="375a8-235">To clear only a specific property, use `Clear-ItemProperty`.</span></span>

```
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name           Property
----           --------
Contoso        Server     : {a, b, c}
               HereString : {This is text which contains
               newlines. It also contains "quoted" strings}
               (default)  : 1

PS HKLM:\SOFTWARE\> Clear-Item .\Contoso\
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
Contoso
```

<span data-ttu-id="375a8-236">Weitere Beispiele und Informationen zur Verwendung von Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="375a8-236">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="375a8-237">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-237">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="375a8-238">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-238">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="375a8-239">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-239">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="375a8-240">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-240">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)

## <a name="dynamic-parameters"></a><span data-ttu-id="375a8-241">Dynamische Parameter</span><span class="sxs-lookup"><span data-stu-id="375a8-241">Dynamic parameters</span></span>

<span data-ttu-id="375a8-242">Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="375a8-242">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="type-microsoftwin32registryvaluekind"></a><span data-ttu-id="375a8-243">Geben Sie <Microsoft. Win32. RegistryValueKind ein></span><span class="sxs-lookup"><span data-stu-id="375a8-243">Type <Microsoft.Win32.RegistryValueKind></span></span>

<span data-ttu-id="375a8-244">Erstellt oder ändert den Datentyp eines Registrierungswerts.</span><span class="sxs-lookup"><span data-stu-id="375a8-244">Establishes or changes the data type of a registry value.</span></span> <span data-ttu-id="375a8-245">Der Standardwert ist `String` (REG_SZ).</span><span class="sxs-lookup"><span data-stu-id="375a8-245">The default is `String` (REG_SZ).</span></span>

<span data-ttu-id="375a8-246">Dieser Parameter funktioniert wie vorgesehen im Cmdlet [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty).</span><span class="sxs-lookup"><span data-stu-id="375a8-246">This parameter works as designed on the [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty) cmdlet.</span></span> <span data-ttu-id="375a8-247">Es steht auch im Cmdlet [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) in den Registrierungslaufwerken zur Verfügung, aber er hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="375a8-247">It is also available on the [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) cmdlet in the registry drives, but it has no effect.</span></span>

|<span data-ttu-id="375a8-248">Wert</span><span class="sxs-lookup"><span data-stu-id="375a8-248">Value</span></span> | <span data-ttu-id="375a8-249">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="375a8-249">Description</span></span> |
| ---- | ----------- |
| `String` | <span data-ttu-id="375a8-250">Gibt eine Null-terminierte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="375a8-250">Specifies a null-terminated string.</span></span> <span data-ttu-id="375a8-251">Entspricht REG_SZ.</span><span class="sxs-lookup"><span data-stu-id="375a8-251">Equivalent to REG_SZ.</span></span> |
| `ExpandString` | <span data-ttu-id="375a8-252">Gibt eine auf NULL endenden Zeichenfolge an, die nicht erweitert ist.</span><span class="sxs-lookup"><span data-stu-id="375a8-252">Specifies a null-terminated string that contains unexpanded</span></span> |
|                | <span data-ttu-id="375a8-253">Verweise auf Umgebungsvariablen, die erweitert werden, wenn</span><span class="sxs-lookup"><span data-stu-id="375a8-253">references to environment variables that are expanded when</span></span> |
|                | <span data-ttu-id="375a8-254">der Wert wird abgerufen.</span><span class="sxs-lookup"><span data-stu-id="375a8-254">the value is retrieved.</span></span> <span data-ttu-id="375a8-255">Entspricht REG_EXPAND_SZ.</span><span class="sxs-lookup"><span data-stu-id="375a8-255">Equivalent to REG_EXPAND_SZ.</span></span> |
| `Binary` | <span data-ttu-id="375a8-256">Gibt Binärdaten in irgendeiner Form an.</span><span class="sxs-lookup"><span data-stu-id="375a8-256">Specifies binary data in any form.</span></span> <span data-ttu-id="375a8-257">Entspricht REG_BINARY.</span><span class="sxs-lookup"><span data-stu-id="375a8-257">Equivalent to REG_BINARY.</span></span> |
| `DWord` | <span data-ttu-id="375a8-258">Gibt eine 32-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="375a8-258">Specifies a 32-bit binary number.</span></span> <span data-ttu-id="375a8-259">Entspricht REG_DWORD.</span><span class="sxs-lookup"><span data-stu-id="375a8-259">Equivalent to REG_DWORD.</span></span> |
| `MultiString` | <span data-ttu-id="375a8-260">Gibt ein Array von null-terminierten Zeichen folgen an, die von</span><span class="sxs-lookup"><span data-stu-id="375a8-260">Specifies an array of null-terminated strings terminated by</span></span> |
|               | <span data-ttu-id="375a8-261">zwei NULL-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="375a8-261">two null characters.</span></span> <span data-ttu-id="375a8-262">Entspricht REG_MULTI_SZ.</span><span class="sxs-lookup"><span data-stu-id="375a8-262">Equivalent to REG_MULTI_SZ.</span></span> |
| `QWord` | <span data-ttu-id="375a8-263">Gibt eine 64-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="375a8-263">Specifies a 64-bit binary number.</span></span> <span data-ttu-id="375a8-264">Entspricht REG_QWORD.</span><span class="sxs-lookup"><span data-stu-id="375a8-264">Equivalent to REG_QWORD.</span></span> |
| `Unknown` | <span data-ttu-id="375a8-265">Gibt einen nicht unterstützten Registrierungs Datentyp an, z. b.</span><span class="sxs-lookup"><span data-stu-id="375a8-265">Indicates an unsupported registry data type, such as</span></span> |
|           | <span data-ttu-id="375a8-266">REG_RESOURCE_LIST.</span><span class="sxs-lookup"><span data-stu-id="375a8-266">REG_RESOURCE_LIST.</span></span> |

#### <a name="cmdlets-supported"></a><span data-ttu-id="375a8-267">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="375a8-267">Cmdlets supported</span></span>

- [<span data-ttu-id="375a8-268">Set-Item</span><span class="sxs-lookup"><span data-stu-id="375a8-268">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="375a8-269">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="375a8-269">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="using-the-pipeline"></a><span data-ttu-id="375a8-270">Verwenden der Pipeline</span><span class="sxs-lookup"><span data-stu-id="375a8-270">Using the pipeline</span></span>

<span data-ttu-id="375a8-271">Anbieter-Cmdlets akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="375a8-271">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="375a8-272">Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="375a8-272">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span> <span data-ttu-id="375a8-273">Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="375a8-273">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="375a8-274">Hilfe</span><span class="sxs-lookup"><span data-stu-id="375a8-274">Getting help</span></span>

<span data-ttu-id="375a8-275">Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.</span><span class="sxs-lookup"><span data-stu-id="375a8-275">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="375a8-276">Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen `Get-Help` Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den **path** -Parameter, um ein Dateisystem Laufwerk anzugeben.</span><span class="sxs-lookup"><span data-stu-id="375a8-276">To get the help topics that are customized for the file system drive, run a `Get-Help` command in a file system drive or use the **Path** parameter to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path HKLM:
```

## <a name="see-also"></a><span data-ttu-id="375a8-277">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="375a8-277">See also</span></span>

 [<span data-ttu-id="375a8-278">about_Providers</span><span class="sxs-lookup"><span data-stu-id="375a8-278">about_Providers</span></span>](../About/about_Providers.md)

