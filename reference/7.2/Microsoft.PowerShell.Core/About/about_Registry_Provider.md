---
description: Registrierung
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_registry_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Registrierungsanbieter
ms.openlocfilehash: 2d57afc164885b4d207108a360215e63a5431632
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599423"
---
# <a name="registry-provider"></a><span data-ttu-id="e195d-103">Registrierungs Anbieter</span><span class="sxs-lookup"><span data-stu-id="e195d-103">Registry provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="e195d-104">Anbietername</span><span class="sxs-lookup"><span data-stu-id="e195d-104">Provider name</span></span>

<span data-ttu-id="e195d-105">Registrierung</span><span class="sxs-lookup"><span data-stu-id="e195d-105">Registry</span></span>

## <a name="drives"></a><span data-ttu-id="e195d-106">Laufwerke</span><span class="sxs-lookup"><span data-stu-id="e195d-106">Drives</span></span>

<span data-ttu-id="e195d-107">`HKLM:`, `HKCU:`</span><span class="sxs-lookup"><span data-stu-id="e195d-107">`HKLM:`, `HKCU:`</span></span>

## <a name="capabilities"></a><span data-ttu-id="e195d-108">Funktionen</span><span class="sxs-lookup"><span data-stu-id="e195d-108">Capabilities</span></span>

<span data-ttu-id="e195d-109">Nicht **verarbeiten**, **usetransactions**</span><span class="sxs-lookup"><span data-stu-id="e195d-109">**ShouldProcess**, **UseTransactions**</span></span>

## <a name="short-description"></a><span data-ttu-id="e195d-110">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e195d-110">Short description</span></span>

<span data-ttu-id="e195d-111">Ermöglicht den Zugriff auf die Registrierungsschlüssel, Einträge und Werte in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e195d-111">Provides access to the registry keys, entries, and values in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="e195d-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e195d-112">Detailed description</span></span>

<span data-ttu-id="e195d-113">Mit dem PowerShell- **Registrierungs** Anbieter können Sie Registrierungsschlüssel, Einträge und Werte in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.</span><span class="sxs-lookup"><span data-stu-id="e195d-113">The PowerShell **Registry** provider lets you get, add, change, clear, and delete registry keys, entries, and values in PowerShell.</span></span>

<span data-ttu-id="e195d-114">Die **Registrierungs** Laufwerke sind ein hierarchischer Namespace, der die Registrierungsschlüssel und Unterschlüssel auf dem Computer enthält.</span><span class="sxs-lookup"><span data-stu-id="e195d-114">The **Registry** drives are a hierarchical namespace containing the registry keys and subkeys on your computer.</span></span> <span data-ttu-id="e195d-115">Registrierungseinträge und Werte sind keine Komponenten dieser Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="e195d-115">Registry entries and values are not components of that hierarchy.</span></span> <span data-ttu-id="e195d-116">Stattdessen sind sie Eigenschaften des jeweiligen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="e195d-116">Instead, they are properties of each of the keys.</span></span>

<span data-ttu-id="e195d-117">Der **Registrierungs** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e195d-117">The **Registry** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="e195d-118">Get-Location</span><span class="sxs-lookup"><span data-stu-id="e195d-118">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="e195d-119">Set-Location</span><span class="sxs-lookup"><span data-stu-id="e195d-119">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="e195d-120">Get-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-120">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="e195d-121">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e195d-121">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="e195d-122">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-122">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="e195d-123">Move-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-123">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="e195d-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="e195d-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="e195d-126">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-126">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="e195d-127">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-127">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="e195d-128">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-128">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="e195d-129">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-129">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="e195d-130">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="e195d-130">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="e195d-131">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="e195d-131">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="e195d-132">Von diesem Anbieter verfügbar gemachte Typen</span><span class="sxs-lookup"><span data-stu-id="e195d-132">Types exposed by this provider</span></span>

<span data-ttu-id="e195d-133">Registrierungsschlüssel werden als Instanzen der [Microsoft. Win32. RegistryKey](/dotnet/api/microsoft.win32.registrykey) -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e195d-133">Registry keys are represented as instances of the [Microsoft.Win32.RegistryKey](/dotnet/api/microsoft.win32.registrykey) class.</span></span> <span data-ttu-id="e195d-134">Registrierungseinträge werden als Instanzen der Klasse [pscustomobject](/dotnet/api/system.management.automation.pscustomobject) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e195d-134">Registry entries are represented as instances of the [PSCustomObject](/dotnet/api/system.management.automation.pscustomobject) class.</span></span>

## <a name="navigating-the-registry-drives"></a><span data-ttu-id="e195d-135">Navigieren in den Registrierungs Laufwerken</span><span class="sxs-lookup"><span data-stu-id="e195d-135">Navigating the Registry drives</span></span>

<span data-ttu-id="e195d-136">Der **Registrierungs** Anbieter stellt seinen Datenspeicher als zwei Standard Laufwerke zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e195d-136">The **Registry** provider exposes its data store as two default drives.</span></span> <span data-ttu-id="e195d-137">Der Registrierungs Speicherort HKEY_LOCAL_MACHINE der dem Laufwerk zugeordnet ist `HKLM:` und dem Laufwerk HKEY_CURRENT_USER zugeordnet ist `HKCU:` .</span><span class="sxs-lookup"><span data-stu-id="e195d-137">The registry location HKEY_LOCAL_MACHINE is mapped to the `HKLM:` drive and HKEY_CURRENT_USER is mapped to the `HKCU:` drive.</span></span> <span data-ttu-id="e195d-138">Wenn Sie mit der Registrierung arbeiten möchten, können Sie den Speicherort `HKLM:` mit dem folgenden Befehl auf das Laufwerk umstellen.</span><span class="sxs-lookup"><span data-stu-id="e195d-138">To work with the registry, you can change your location to the `HKLM:` drive using the following command.</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="e195d-139">Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein.</span><span class="sxs-lookup"><span data-stu-id="e195d-139">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="e195d-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e195d-140">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="e195d-141">Sie können auch mit dem **Registrierungs** Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e195d-141">You can also work with the **Registry** provider from any other PowerShell drive.</span></span> <span data-ttu-id="e195d-142">Um auf einen Registrierungsschlüssel von einem anderen Speicherort zu verweisen, verwenden Sie den Laufwerk Namen ( `HKLM:` , `HKCU:` ) im Pfad.</span><span class="sxs-lookup"><span data-stu-id="e195d-142">To reference a registry key from another location, use the drive name (`HKLM:`, `HKCU:`) in the path.</span></span> <span data-ttu-id="e195d-143">Verwenden Sie einen umgekehrten Schrägstrich ( \\ ) oder einen Schrägstrich (/), um eine Ebene des **Registrierungs** Laufwerks anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e195d-143">Use a backslash (\\) or a forward slash (/) to indicate a level of the **Registry** drive.</span></span>

```powershell
PS C:\> cd HKLM:\Software
```

> [!NOTE]
> <span data-ttu-id="e195d-144">PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten.</span><span class="sxs-lookup"><span data-stu-id="e195d-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="e195d-145">Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="e195d-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location), and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

<span data-ttu-id="e195d-146">Das letzte Beispiel zeigt eine weitere Pfad Syntax, die Sie verwenden können, um durch den **Registrierungs** Anbieter zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="e195d-146">This last example shows another path syntax you can use to navigate the **Registry** provider.</span></span> <span data-ttu-id="e195d-147">Diese Syntax verwendet den Anbieter Namen, gefolgt von zwei Doppelpunkten `::` .</span><span class="sxs-lookup"><span data-stu-id="e195d-147">This syntax uses the provider name, followed by two colons `::`.</span></span> <span data-ttu-id="e195d-148">Mit dieser Syntax können Sie anstelle des zugeordneten Laufwerks namens den vollständigen Hive-Namen verwenden `HKLM` .</span><span class="sxs-lookup"><span data-stu-id="e195d-148">This syntax allows you to use the full HIVE name, instead of the mapped drive name `HKLM`.</span></span>

```powershell
cd "Registry::HKEY_LOCAL_MACHINE\Software"
```

## <a name="displaying-the-contents-of-registry-keys"></a><span data-ttu-id="e195d-149">Anzeigen des Inhalts von Registrierungs Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="e195d-149">Displaying the contents of registry keys</span></span>

<span data-ttu-id="e195d-150">Die Registrierung ist in Schlüssel, Unterschlüssel und Einträge unterteilt.</span><span class="sxs-lookup"><span data-stu-id="e195d-150">The registry is divided into keys, subkeys, and entries.</span></span> <span data-ttu-id="e195d-151">Weitere Informationen zur Registrierungs Struktur finden Sie unter [Struktur der Registrierung](/windows/desktop/sysinfo/structure-of-the-registry).</span><span class="sxs-lookup"><span data-stu-id="e195d-151">For more information about registry structure, see [Structure of the Registry](/windows/desktop/sysinfo/structure-of-the-registry).</span></span>

<span data-ttu-id="e195d-152">In einem **Registrierungs** Laufwerk ist jeder Schlüssel ein Container.</span><span class="sxs-lookup"><span data-stu-id="e195d-152">In a **Registry** drive, each key is a container.</span></span> <span data-ttu-id="e195d-153">Ein Schlüssel kann eine beliebige Anzahl von Schlüsseln enthalten.</span><span class="sxs-lookup"><span data-stu-id="e195d-153">A key can contain any number of keys.</span></span> <span data-ttu-id="e195d-154">Ein Registrierungsschlüssel, der über einen übergeordneten Schlüssel verfügt, wird als Unterschlüssel bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e195d-154">A registry key that has a parent key is called a subkey.</span></span> <span data-ttu-id="e195d-155">Sie können verwenden `Get-ChildItem` , um Registrierungsschlüssel anzuzeigen und `Set-Location` zu einem Schlüssel Pfad zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="e195d-155">You can use `Get-ChildItem` to view registry keys and `Set-Location` to navigate to a key path.</span></span>

<span data-ttu-id="e195d-156">Registrierungs Werte sind Attribute eines Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="e195d-156">Registry values are attributes of a registry key.</span></span> <span data-ttu-id="e195d-157">Im **Registrierungs** Laufwerk werden Sie als **Element Eigenschaften** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e195d-157">In the **Registry** drive, they are called **Item Properties**.</span></span> <span data-ttu-id="e195d-158">Ein Registrierungsschlüssel kann sowohl untergeordnete Schlüssel als auch Element Eigenschaften haben.</span><span class="sxs-lookup"><span data-stu-id="e195d-158">A registry key can have both children keys and item properties.</span></span>

<span data-ttu-id="e195d-159">In diesem Beispiel wird der Unterschied zwischen `Get-Item` und `Get-ChildItem` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e195d-159">In this example, the difference between `Get-Item` and `Get-ChildItem` is shown.</span></span> <span data-ttu-id="e195d-160">Wenn Sie `Get-Item` den "Spooler"-Registrierungsschlüssel verwenden, können Sie dessen Eigenschaften anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e195d-160">When you use `Get-Item` on the "Spooler" registry key, you can view its properties.</span></span>

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

<span data-ttu-id="e195d-161">Jeder Registrierungsschlüssel kann auch Unterschlüssel enthalten.</span><span class="sxs-lookup"><span data-stu-id="e195d-161">Each registry key can also have subkeys.</span></span> <span data-ttu-id="e195d-162">Wenn Sie `Get-Item` für einen Registrierungsschlüssel verwenden, werden die Unterschlüssel nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e195d-162">When you use `Get-Item` on a registry key, the subkeys are not displayed.</span></span> <span data-ttu-id="e195d-163">`Get-ChildItem`Mit dem-Cmdlet werden die untergeordneten Elemente der "Spooler"-Taste angezeigt, einschließlich der Eigenschaften des unter Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="e195d-163">The `Get-ChildItem` cmdlet will show you children items of the "Spooler" key, including each subkey's properties.</span></span> <span data-ttu-id="e195d-164">Die Eigenschaften der übergeordneten Schlüssel werden bei Verwendung von nicht angezeigt `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="e195d-164">The parent keys properties are not shown when using `Get-ChildItem`.</span></span>

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

<span data-ttu-id="e195d-165">Das- `Get-Item` Cmdlet kann auch am aktuellen Speicherort verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e195d-165">The `Get-Item` cmdlet can also be used on the current location.</span></span> <span data-ttu-id="e195d-166">Im folgenden Beispiel wird zum "Spooler"-Registrierungsschlüssel navigiert, und die Element Eigenschaften werden abgerufen.</span><span class="sxs-lookup"><span data-stu-id="e195d-166">The following example navigates to the "Spooler" registry key and gets the item properties.</span></span>
<span data-ttu-id="e195d-167">Der Punkt `.` wird verwendet, um den aktuellen Speicherort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e195d-167">The dot `.` is used to indicate the current location.</span></span>

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

<span data-ttu-id="e195d-168">Weitere Informationen zu den in diesem Abschnitt behandelten Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="e195d-168">For more information on the cmdlets covered in this section, see the following articles.</span></span>

<span data-ttu-id="e195d-169">-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) 
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span><span class="sxs-lookup"><span data-stu-id="e195d-169">-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
-[Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span></span>

## <a name="viewing-registry-key-values"></a><span data-ttu-id="e195d-170">Anzeigen von Registrierungsschlüssel Werten</span><span class="sxs-lookup"><span data-stu-id="e195d-170">Viewing registry key values</span></span>

<span data-ttu-id="e195d-171">Registrierungsschlüssel Werte werden als Eigenschaften der einzelnen Registrierungsschlüssel gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e195d-171">Registry key values are stored as properties of each registry key.</span></span> <span data-ttu-id="e195d-172">Das `Get-ItemProperty` Cmdlet zeigt die Registrierungsschlüssel Eigenschaften mit dem von Ihnen angegebenen Namen an.</span><span class="sxs-lookup"><span data-stu-id="e195d-172">The `Get-ItemProperty` cmdlet views registry key properties using the name you specify.</span></span> <span data-ttu-id="e195d-173">Das Ergebnis ist ein **pscustomobject** mit den von Ihnen angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e195d-173">The result is a **PSCustomObject** containing the properties you specify.</span></span>

<span data-ttu-id="e195d-174">Im folgenden Beispiel wird das- `Get-ItemProperty` Cmdlet verwendet, um alle Eigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e195d-174">The Following example uses the `Get-ItemProperty` cmdlet to view all properties.</span></span> <span data-ttu-id="e195d-175">Wenn Sie das resultierende Objekt in einer Variablen speichern, können Sie auf den gewünschten Eigenschafts Wert zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e195d-175">Storing the resulting object in a variable allows you to access the desired property value.</span></span>

```powershell
$p = Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler
$p.DependOnService
```

```output
RPCSS
http
```

<span data-ttu-id="e195d-176">Wenn Sie einen Wert für den Parameter angeben, werden `-Name` die von Ihnen angegebenen Eigenschaften ausgewählt und das **pscustomobject-Objekt** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e195d-176">Specifying a value for the `-Name` parameter selects the properties you specify and returns the **PSCustomObject**.</span></span>  <span data-ttu-id="e195d-177">Das folgende Beispiel zeigt den Unterschied in der Ausgabe, wenn Sie den- `-Name` Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="e195d-177">The following example shows the difference in output when you use the `-Name` parameter.</span></span>

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

<span data-ttu-id="e195d-178">Ab PowerShell 5,0 `Get-ItemPropertyValue` gibt das Cmdlet nur den Wert der angegebenen Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="e195d-178">Beginning in PowerShell 5.0, the `Get-ItemPropertyValue` cmdlet returns only the value of the property you specify.</span></span>

```powershell
Get-ItemPropertyValue -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD
```

```output
17134.1
```

<span data-ttu-id="e195d-179">Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="e195d-179">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="e195d-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-180">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="e195d-181">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="e195d-181">Get-ItemPropertyValue</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)

## <a name="changing-registry-key-values"></a><span data-ttu-id="e195d-182">Ändern von Registrierungsschlüssel Werten</span><span class="sxs-lookup"><span data-stu-id="e195d-182">Changing registry key values</span></span>

<span data-ttu-id="e195d-183">Mit dem- `Set-ItemProperty` Cmdlet werden die Attribute für Registrierungsschlüssel festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e195d-183">The `Set-ItemProperty` cmdlet will set attributes for registry keys.</span></span> <span data-ttu-id="e195d-184">Im folgenden Beispiel wird verwendet `Set-ItemProperty` , um den Starttyp des Spoolerdiensts in manuell zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e195d-184">The following example uses `Set-ItemProperty` to change the spooler service start type to manual.</span></span> <span data-ttu-id="e195d-185">Im Beispiel wird der **StartType** mithilfe des Cmdlets wieder in " *automatisch* " geändert `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="e195d-185">The example changes the **StartType** back to *Automatic* using the `Set-Service` cmdlet.</span></span>

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

<span data-ttu-id="e195d-186">Jeder Registrierungsschlüssel hat einen *Standard* Wert.</span><span class="sxs-lookup"><span data-stu-id="e195d-186">Each registry key has a *default* value.</span></span> <span data-ttu-id="e195d-187">Sie können den *Standard* Wert für einen Registrierungsschlüssel entweder mit `Set-Item` oder ändern `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="e195d-187">You can change the *default* value for a registry key with either `Set-Item` or `Set-ItemProperty`.</span></span>

```powershell
Set-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name "(default)" -Value "one"
Set-Item -Path HKLM:\SOFTWARE\Contoso -Value "two"
```

<span data-ttu-id="e195d-188">Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="e195d-188">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="e195d-189">Set-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-189">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="e195d-190">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-190">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="creating-registry-keys-and-values"></a><span data-ttu-id="e195d-191">Erstellen von Registrierungs Schlüsseln und-Werten</span><span class="sxs-lookup"><span data-stu-id="e195d-191">Creating registry keys and values</span></span>

<span data-ttu-id="e195d-192">Mit dem- `New-Item` Cmdlet werden Registrierungsschlüssel mit einem von Ihnen bereitgestellten Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="e195d-192">The `New-Item` cmdlet will create registry keys with a name that you provide.</span></span>
<span data-ttu-id="e195d-193">Sie können auch die- `mkdir` Funktion verwenden, die das `New-Item` Cmdlet intern aufruft.</span><span class="sxs-lookup"><span data-stu-id="e195d-193">You can also use the `mkdir` function, which calls the `New-Item` cmdlet internally.</span></span>

```
PS HKLM:\SOFTWARE\> mkdir ContosoCompany

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
ContosoCompany
```

<span data-ttu-id="e195d-194">Sie können das `New-ItemProperty` Cmdlet verwenden, um Werte in einem von Ihnen angegebenen Registrierungsschlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e195d-194">You can use the `New-ItemProperty` cmdlet to create values in a registry key that you specify.</span></span> <span data-ttu-id="e195d-195">Im folgenden Beispiel wird ein neuer DWORD-Wert im Registrierungsschlüssel "contosocompany" erstellt.</span><span class="sxs-lookup"><span data-stu-id="e195d-195">The following example creates a new DWORD value on the ContosoCompany registry key.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\ContosoCompany"
New-ItemProperty -Path  -Name Test -Type DWORD -Value 1
```

> [!NOTE]
> <span data-ttu-id="e195d-196">Weitere zulässige Typwerte finden Sie im Abschnitt "dynamische Parameter" in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="e195d-196">Review the dynamic parameters section in this article for other allowed type values.</span></span>

<span data-ttu-id="e195d-197">Ausführliche Informationen zur Verwendung von Cmdlets finden Sie unter [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).</span><span class="sxs-lookup"><span data-stu-id="e195d-197">For detailed cmdlet usage, see [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).</span></span>

## <a name="copying-registry-keys-and-values"></a><span data-ttu-id="e195d-198">Kopieren von Registrierungs Schlüsseln und-Werten</span><span class="sxs-lookup"><span data-stu-id="e195d-198">Copying registry keys and values</span></span>

<span data-ttu-id="e195d-199">Verwenden Sie  das `Copy-Item` Cmdlet zum Kopieren von Registrierungs Schlüsseln und-Werten im Registrierungs Anbieter.</span><span class="sxs-lookup"><span data-stu-id="e195d-199">In the **Registry** provider, use the `Copy-Item` cmdlet copies registry keys and values.</span></span> <span data-ttu-id="e195d-200">Verwenden Sie das- `Copy-ItemProperty` Cmdlet, um nur Registrierungs Werte zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="e195d-200">Use the `Copy-ItemProperty` cmdlet to copy registry values only.</span></span>
<span data-ttu-id="e195d-201">Mit dem folgenden Befehl werden der Registrierungsschlüssel "%% amp; quot;" und seine Eigenschaften an den angegebenen Speicherort "HKLM: \ software\fabrikam" kopiert.</span><span class="sxs-lookup"><span data-stu-id="e195d-201">The following command copies the "Contoso" registry key, and its properties to the specified location "HKLM:\Software\Fabrikam".</span></span>

<span data-ttu-id="e195d-202">`Copy-Item` erstellt den Ziel Schlüssel, wenn er nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e195d-202">`Copy-Item` creates the destination key if it does not exist.</span></span> <span data-ttu-id="e195d-203">Wenn der Ziel Schlüssel vorhanden ist, wird von `Copy-Item` ein Duplikat des Quell Schlüssels als untergeordnetes Element (Unterschlüssel) des Ziel Schlüssels erstellt.</span><span class="sxs-lookup"><span data-stu-id="e195d-203">If the destination key exists, `Copy-Item` creates a duplicate of the source key as a child item (subkey) of the destination key.</span></span>

```powershell
Copy-Item -Path  HKLM:\Software\Contoso -Destination HKLM:\Software\Fabrikam
```

<span data-ttu-id="e195d-204">Der folgende Befehl verwendet das `Copy-ItemProperty` Cmdlet, um den Wert "Server" aus dem Schlüssel "" in den Schlüssel "Fabrikam" zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="e195d-204">The following command uses the `Copy-ItemProperty` cmdlet to copy the "Server" value from the "Contoso" key to the "Fabrikam" key.</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Copy-ItemProperty -Path $source -Destination $dest -Name Server
```

<span data-ttu-id="e195d-205">Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="e195d-205">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="e195d-206">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-206">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="e195d-207">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-207">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

## <a name="moving-registry-keys-and-values"></a><span data-ttu-id="e195d-208">Verschieben von Registrierungs Schlüsseln und-Werten</span><span class="sxs-lookup"><span data-stu-id="e195d-208">Moving registry keys and values</span></span>

<span data-ttu-id="e195d-209">Die `Move-Item` `Move-ItemProperty` Cmdlets und Verhalten sich wie Ihre "Copy"-Entsprechungen.</span><span class="sxs-lookup"><span data-stu-id="e195d-209">The `Move-Item` and `Move-ItemProperty` cmdlets behave like their "Copy" counterparts.</span></span> <span data-ttu-id="e195d-210">Wenn das Ziel vorhanden ist, `Move-Item` Verschiebt den Quell Schlüssel unterhalb des Ziel Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="e195d-210">If the destination exists, `Move-Item` moves the source key underneath the destination key.</span></span> <span data-ttu-id="e195d-211">Wenn der Ziel Schlüssel nicht vorhanden ist, wird der Quell Schlüssel in den Zielpfad verschoben.</span><span class="sxs-lookup"><span data-stu-id="e195d-211">If the destination key does not exist, the source key is moved to the destination path.</span></span>

<span data-ttu-id="e195d-212">Mit dem folgenden Befehl wird der Schlüssel "fitoso" in den Pfad "HKLM: \ software\fabrikam" verschoben.</span><span class="sxs-lookup"><span data-stu-id="e195d-212">The following command moves the "Contoso" key to the path "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
Move-Item -Path HKLM:\SOFTWARE\Contoso -Destination HKLM:\SOFTWARE\Fabrikam
```

<span data-ttu-id="e195d-213">Mit diesem Befehl werden alle Eigenschaften von "HKLM: \ software\contosocompany" nach "HKLM: \ software\fabrikam" verschoben.</span><span class="sxs-lookup"><span data-stu-id="e195d-213">This command moves all of the properties from "HKLM:\SOFTWARE\ContosoCompany" to "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Move-ItemProperty -Path $source -Destination $dest -Name *
```

<span data-ttu-id="e195d-214">Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="e195d-214">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="e195d-215">Move-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-215">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="e195d-216">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-216">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)

## <a name="renaming-registry-keys-and-values"></a><span data-ttu-id="e195d-217">Umbenennen von Registrierungs Schlüsseln und-Werten</span><span class="sxs-lookup"><span data-stu-id="e195d-217">Renaming registry keys and values</span></span>

<span data-ttu-id="e195d-218">Sie können Registrierungsschlüssel und-Werte genau wie Dateien und Ordner umbenennen.</span><span class="sxs-lookup"><span data-stu-id="e195d-218">You can rename registry keys and values just like you would files and folders.</span></span>
<span data-ttu-id="e195d-219">`Rename-Item` benennt Registrierungsschlüssel um und benennt `Rename-ItemProperty` Registrierungs Werte um.</span><span class="sxs-lookup"><span data-stu-id="e195d-219">`Rename-Item` renames registry keys, while `Rename-ItemProperty` renames registry values.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\Contoso"
Rename-ItemProperty -Path $path -Name ContosoTest -NewName FabrikamTest
Rename-Item -Path $path -NewName Fabrikam
```

## <a name="changing-security-descriptors"></a><span data-ttu-id="e195d-220">Ändern von Sicherheits Deskriptoren</span><span class="sxs-lookup"><span data-stu-id="e195d-220">Changing security descriptors</span></span>

<span data-ttu-id="e195d-221">Sie können den Zugriff auf Registrierungsschlüssel mithilfe der `Get-Acl` `Set-Acl` Cmdlets und einschränken.</span><span class="sxs-lookup"><span data-stu-id="e195d-221">You can restrict access to registry keys using the `Get-Acl` and `Set-Acl` cmdlets.</span></span> <span data-ttu-id="e195d-222">Im folgenden Beispiel wird ein neuer Benutzer mit Vollzugriff dem Registrierungsschlüssel "HKLM: \ software\configuration Manager" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e195d-222">The following example adds a new user with full control to the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Contoso
$rule = New-Object System.Security.AccessControl.RegistryAccessRule `
("CONTOSO\jsmith", "FullControl", "Allow")
$acl.SetAccessRule($rule)
$acl | Set-Acl -Path HKLM:\SOFTWARE\Contoso
```

<span data-ttu-id="e195d-223">Weitere Beispiele und Informationen zur Verwendung von Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="e195d-223">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="e195d-224">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="e195d-224">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="e195d-225">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="e195d-225">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="removing-and-clearing-registry-keys-and-values"></a><span data-ttu-id="e195d-226">Entfernen und Löschen von Registrierungs Schlüsseln und-Werten</span><span class="sxs-lookup"><span data-stu-id="e195d-226">Removing and clearing registry keys and values</span></span>

<span data-ttu-id="e195d-227">Mit **Remove-Item** können Sie enthaltene Elemente entfernen. Sie werden jedoch aufgefordert, das Entfernen zu bestätigen, wenn das Element etwas anderes enthält.</span><span class="sxs-lookup"><span data-stu-id="e195d-227">You can remove contained items by using **Remove-Item**, but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="e195d-228">Im folgenden Beispiel wird versucht, den Schlüssel "HKLM: \ software\configuration Manager" zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e195d-228">The following example attempts to delete a key "HKLM:\SOFTWARE\Contoso".</span></span>

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

<span data-ttu-id="e195d-229">Wenn Sie enthaltene Elemente ohne Aufforderung löschen möchten, geben Sie den- `-Recurse` Parameter an.</span><span class="sxs-lookup"><span data-stu-id="e195d-229">To delete contained items without prompting, specify the `-Recurse` parameter.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso -Recurse
```

<span data-ttu-id="e195d-230">Wenn Sie alle Elemente in "HKLM: \ software\configuration Manager", aber nicht "HKLM: \ software\c" selbst entfernen möchten, verwenden Sie einen nachfolgenden umgekehrten Schrägstrich, `\` gefolgt von einem Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="e195d-230">If you wanted to remove all items within "HKLM:\SOFTWARE\Contoso" but not "HKLM:\SOFTWARE\Contoso" itself, use a trailing backslash `\` followed by a wildcard.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso\* -Recurse
```

<span data-ttu-id="e195d-231">Mit diesem Befehl wird der Registrierungs Wert "ContosoTest" aus dem Registrierungsschlüssel "HKLM: \ software\contoso" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e195d-231">This command deletes the "ContosoTest" registry value from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name ContosoTest
```

<span data-ttu-id="e195d-232">`Clear-Item` Löscht alle Registrierungs Werte für einen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="e195d-232">`Clear-Item` clears all registry values for a key.</span></span> <span data-ttu-id="e195d-233">Im folgenden Beispiel werden alle Werte aus dem Registrierungsschlüssel "HKLM: \ software\c" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e195d-233">The following example clears all values from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span> <span data-ttu-id="e195d-234">Verwenden Sie, um nur eine bestimmte Eigenschaft zu löschen `Clear-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="e195d-234">To clear only a specific property, use `Clear-ItemProperty`.</span></span>

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

<span data-ttu-id="e195d-235">Weitere Beispiele und Informationen zur Verwendung von Cmdlets finden Sie in den folgenden Artikeln.</span><span class="sxs-lookup"><span data-stu-id="e195d-235">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="e195d-236">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-236">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="e195d-237">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-237">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="e195d-238">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-238">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="e195d-239">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-239">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)

## <a name="dynamic-parameters"></a><span data-ttu-id="e195d-240">Dynamische Parameter</span><span class="sxs-lookup"><span data-stu-id="e195d-240">Dynamic parameters</span></span>

<span data-ttu-id="e195d-241">Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e195d-241">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="type-microsoftwin32registryvaluekind"></a><span data-ttu-id="e195d-242">Geben Sie <Microsoft. Win32. RegistryValueKind ein></span><span class="sxs-lookup"><span data-stu-id="e195d-242">Type <Microsoft.Win32.RegistryValueKind></span></span>

<span data-ttu-id="e195d-243">Erstellt oder ändert den Datentyp eines Registrierungswerts.</span><span class="sxs-lookup"><span data-stu-id="e195d-243">Establishes or changes the data type of a registry value.</span></span> <span data-ttu-id="e195d-244">Der Standardwert ist `String` (REG_SZ).</span><span class="sxs-lookup"><span data-stu-id="e195d-244">The default is `String` (REG_SZ).</span></span>

<span data-ttu-id="e195d-245">Dieser Parameter funktioniert wie vorgesehen im Cmdlet [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty).</span><span class="sxs-lookup"><span data-stu-id="e195d-245">This parameter works as designed on the [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty) cmdlet.</span></span> <span data-ttu-id="e195d-246">Es steht auch im Cmdlet [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) in den Registrierungslaufwerken zur Verfügung, aber er hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="e195d-246">It is also available on the [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) cmdlet in the registry drives, but it has no effect.</span></span>

|<span data-ttu-id="e195d-247">Wert</span><span class="sxs-lookup"><span data-stu-id="e195d-247">Value</span></span> | <span data-ttu-id="e195d-248">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e195d-248">Description</span></span> |
| ---- | ----------- |
| `String` | <span data-ttu-id="e195d-249">Gibt eine Null-terminierte Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="e195d-249">Specifies a null-terminated string.</span></span> <span data-ttu-id="e195d-250">Entspricht REG_SZ.</span><span class="sxs-lookup"><span data-stu-id="e195d-250">Equivalent to REG_SZ.</span></span> |
| `ExpandString` | <span data-ttu-id="e195d-251">Gibt eine auf NULL endenden Zeichenfolge an, die nicht erweitert ist.</span><span class="sxs-lookup"><span data-stu-id="e195d-251">Specifies a null-terminated string that contains unexpanded</span></span> |
|                | <span data-ttu-id="e195d-252">Verweise auf Umgebungsvariablen, die erweitert werden, wenn</span><span class="sxs-lookup"><span data-stu-id="e195d-252">references to environment variables that are expanded when</span></span> |
|                | <span data-ttu-id="e195d-253">der Wert wird abgerufen.</span><span class="sxs-lookup"><span data-stu-id="e195d-253">the value is retrieved.</span></span> <span data-ttu-id="e195d-254">Entspricht REG_EXPAND_SZ.</span><span class="sxs-lookup"><span data-stu-id="e195d-254">Equivalent to REG_EXPAND_SZ.</span></span> |
| `Binary` | <span data-ttu-id="e195d-255">Gibt Binärdaten in irgendeiner Form an.</span><span class="sxs-lookup"><span data-stu-id="e195d-255">Specifies binary data in any form.</span></span> <span data-ttu-id="e195d-256">Entspricht REG_BINARY.</span><span class="sxs-lookup"><span data-stu-id="e195d-256">Equivalent to REG_BINARY.</span></span> |
| `DWord` | <span data-ttu-id="e195d-257">Gibt eine 32-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="e195d-257">Specifies a 32-bit binary number.</span></span> <span data-ttu-id="e195d-258">Entspricht REG_DWORD.</span><span class="sxs-lookup"><span data-stu-id="e195d-258">Equivalent to REG_DWORD.</span></span> |
| `MultiString` | <span data-ttu-id="e195d-259">Gibt ein Array von null-terminierten Zeichen folgen an, die von</span><span class="sxs-lookup"><span data-stu-id="e195d-259">Specifies an array of null-terminated strings terminated by</span></span> |
|               | <span data-ttu-id="e195d-260">zwei NULL-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e195d-260">two null characters.</span></span> <span data-ttu-id="e195d-261">Entspricht REG_MULTI_SZ.</span><span class="sxs-lookup"><span data-stu-id="e195d-261">Equivalent to REG_MULTI_SZ.</span></span> |
| `QWord` | <span data-ttu-id="e195d-262">Gibt eine 64-Bit-Binärzahl an.</span><span class="sxs-lookup"><span data-stu-id="e195d-262">Specifies a 64-bit binary number.</span></span> <span data-ttu-id="e195d-263">Entspricht REG_QWORD.</span><span class="sxs-lookup"><span data-stu-id="e195d-263">Equivalent to REG_QWORD.</span></span> |
| `Unknown` | <span data-ttu-id="e195d-264">Gibt einen nicht unterstützten Registrierungs Datentyp an, z. b.</span><span class="sxs-lookup"><span data-stu-id="e195d-264">Indicates an unsupported registry data type, such as</span></span> |
|           | <span data-ttu-id="e195d-265">REG_RESOURCE_LIST.</span><span class="sxs-lookup"><span data-stu-id="e195d-265">REG_RESOURCE_LIST.</span></span> |

#### <a name="cmdlets-supported"></a><span data-ttu-id="e195d-266">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e195d-266">Cmdlets supported</span></span>

- [<span data-ttu-id="e195d-267">Set-Item</span><span class="sxs-lookup"><span data-stu-id="e195d-267">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="e195d-268">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e195d-268">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="using-the-pipeline"></a><span data-ttu-id="e195d-269">Verwenden der Pipeline</span><span class="sxs-lookup"><span data-stu-id="e195d-269">Using the pipeline</span></span>

<span data-ttu-id="e195d-270">Anbieter-Cmdlets akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="e195d-270">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="e195d-271">Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="e195d-271">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span> <span data-ttu-id="e195d-272">Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="e195d-272">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="e195d-273">Hilfe</span><span class="sxs-lookup"><span data-stu-id="e195d-273">Getting help</span></span>

<span data-ttu-id="e195d-274">Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.</span><span class="sxs-lookup"><span data-stu-id="e195d-274">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="e195d-275">Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen `Get-Help` Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den **path** -Parameter, um ein Dateisystem Laufwerk anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e195d-275">To get the help topics that are customized for the file system drive, run a `Get-Help` command in a file system drive or use the **Path** parameter to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path HKLM:
```

## <a name="see-also"></a><span data-ttu-id="e195d-276">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e195d-276">See also</span></span>

 [<span data-ttu-id="e195d-277">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e195d-277">about_Providers</span></span>](../About/about_Providers.md)

