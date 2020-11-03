---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: b2c5b8596da085fab3af7a1545569dd65931a5f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215420"
---
# <span data-ttu-id="1f5e2-103">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f5e2-103">Get-ItemProperty</span></span>

## <span data-ttu-id="1f5e2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1f5e2-104">SYNOPSIS</span></span>
<span data-ttu-id="1f5e2-105">Ruft die Eigenschaften eines angegebenen Elements ab.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-105">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="1f5e2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1f5e2-106">SYNTAX</span></span>

### <span data-ttu-id="1f5e2-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="1f5e2-107">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="1f5e2-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1f5e2-108">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="1f5e2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1f5e2-109">DESCRIPTION</span></span>

<span data-ttu-id="1f5e2-110">Das- `Get-ItemProperty` Cmdlet ruft die Eigenschaften der angegebenen Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-110">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="1f5e2-111">Beispielsweise können Sie mit diesem Cmdlet den Wert der LastAccessTime-Eigenschaft eines Datei Objekts erhalten.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-111">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span>
<span data-ttu-id="1f5e2-112">Sie können dieses Cmdlet auch zum Anzeigen von Registrierungs Einträgen und deren Werten verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-112">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="1f5e2-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1f5e2-113">EXAMPLES</span></span>

### <span data-ttu-id="1f5e2-114">Beispiel 1: erhalten von Informationen zu einem bestimmten Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="1f5e2-114">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="1f5e2-115">Mit diesem Befehl werden Informationen zum Verzeichnis "c:\Windows" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-115">This command gets information about the "C:\Windows" directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="1f5e2-116">Beispiel 2: erhalten der Eigenschaften einer bestimmten Datei</span><span class="sxs-lookup"><span data-stu-id="1f5e2-116">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="1f5e2-117">Mit diesem Befehl werden die Eigenschaften der Datei "C:\Test\Weather.xls" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-117">This command gets the properties of the "C:\Test\Weather.xls" file.</span></span>
<span data-ttu-id="1f5e2-118">Das Ergebnis wird an das `Format-List` Cmdlet weitergeleitet, um die Ausgabe als Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-118">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="1f5e2-119">Beispiel 3: Anzeigen des Werte namens und der Daten von Registrierungs Einträgen in einem Registrierungs Unterschlüssel</span><span class="sxs-lookup"><span data-stu-id="1f5e2-119">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="1f5e2-120">Dieser Befehl zeigt den Wertnamen und die Daten der einzelnen Registrierungseinträge im Registrierungs Unterschlüssel "CurrentVersion" an.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-120">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="1f5e2-121">Beachten Sie, dass der Befehl erfordert, dass ein PowerShell-Laufwerk mit dem Namen vorhanden ist `HKLM:` , das der Hive-HKEY_LOCAL_MACHINE Struktur der Registrierung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-121">Note that the command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
<span data-ttu-id="1f5e2-122">Ein Laufwerk mit diesem Namen und dieser Zuordnung ist standardmäßig in PowerShell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-122">A drive with that name and mapping is available in PowerShell by default.</span></span>
<span data-ttu-id="1f5e2-123">Der Pfad zu diesem Registrierungsunterschlüssel kann jedoch auch mit dem folgenden alternativen Pfad angegeben werden, der mit dem Anbieternamen beginnt, auf den zwei Doppelpunkte folgen:</span><span class="sxs-lookup"><span data-stu-id="1f5e2-123">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>

<span data-ttu-id="1f5e2-124">"Registry:: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="1f5e2-124">"Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

### <span data-ttu-id="1f5e2-125">Beispiel 4: erhalten Sie den Wertnamen und die Daten eines Registrierungs Eintrags in einem Registrierungs Unterschlüssel.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-125">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="1f5e2-126">Mit diesem Befehl werden der Wertname und die Daten des Registrierungs Eintrags "ProgramFilesDir" im Registrierungs Unterschlüssel "CurrentVersion" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-126">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="1f5e2-127">Der Befehl verwendet den **path** -Parameter, um den Unterschlüssel anzugeben, und den Name-Parameter, um den Wertnamen des Eintrags anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-127">The command uses the **Path** parameter to specify the subkey and the Name parameter to specify the value name of the entry.</span></span>

<span data-ttu-id="1f5e2-128">Der Befehl verwendet einen Backtick oder ein großes Akzent ( \` ), das PowerShell-Fortsetzungs Zeichen, um den Befehl in der zweiten Zeile fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-128">The command uses a back tick or grave accent (\`), the PowerShell continuation character, to continue the command on the second line.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="1f5e2-129">Beispiel 5: erhalten der Werte Namen und Daten von Registrierungs Einträgen in einem Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="1f5e2-129">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="1f5e2-130">Dieser Befehl ruft die Wertnamen und Daten der Registrierungseinträge im Registrierungsschlüssel "powershellengine" ab.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-130">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span>
<span data-ttu-id="1f5e2-131">Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-131">The results are shown in the following sample output.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

### <span data-ttu-id="1f5e2-132">Beispiel 6: Get, Format und Anzeige der Ergebnisse von Registrierungs Werten und-Daten</span><span class="sxs-lookup"><span data-stu-id="1f5e2-132">Example 6: Get, format, and display the results of registry values and data</span></span>

<span data-ttu-id="1f5e2-133">Dieses Beispiel zeigt, wie die Ausgabe eines `Get-ItemProperty` Befehls in einer Liste formatiert werden kann, damit die Registrierungs Werte und-Daten leicht angezeigt werden und die Ergebnisse leicht interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-133">This example shows how to format the output of a `Get-ItemProperty` command in a list to make it easy to see the registry values and data and to make it easy to interpret the results.</span></span>

<span data-ttu-id="1f5e2-134">Der erste Befehl verwendet das `Get-ItemProperty` Cmdlet, um die Registrierungseinträge im Unterschlüssel **Microsoft. PowerShell** zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-134">The first command uses the `Get-ItemProperty` cmdlet to get the registry entries in the **Microsoft.PowerShell** subkey.</span></span>
<span data-ttu-id="1f5e2-135">Dieser Unterschlüssel speichert Optionen für die Standardshell für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-135">This subkey stores options for the default shell for PowerShell.</span></span>
<span data-ttu-id="1f5e2-136">Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-136">The results are shown in the following sample output.</span></span>

<span data-ttu-id="1f5e2-137">Die Ausgabe zeigt, dass zwei Registrierungseinträge vorhanden sind: "Path" und "ExecutionPolicy".</span><span class="sxs-lookup"><span data-stu-id="1f5e2-137">The output shows that there are two registry entries, "Path" and "ExecutionPolicy".</span></span>
<span data-ttu-id="1f5e2-138">Wenn ein Registrierungsschlüssel weniger als fünf Einträge enthält, wird er standardmäßig in einer Tabelle angezeigt. Die Darstellung in einer Liste ist jedoch häufig übersichtlicher.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-138">When a registry key contains fewer than five entries, by default it is displayed in a table, but it is often easier to view in a list.</span></span>

<span data-ttu-id="1f5e2-139">Der zweite Befehl verwendet denselben `Get-ItemProperty` Befehl.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-139">The second command uses the same `Get-ItemProperty` command.</span></span>
<span data-ttu-id="1f5e2-140">Diesmal verwendet der Befehl jedoch einen Pipeline Operator ( `|` ), um die Ergebnisse des Befehls an das `Format-List` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-140">However, this time, the command uses a pipeline operator (`|`) to send the results of the command to the `Format-List` cmdlet.</span></span>
<span data-ttu-id="1f5e2-141">Der `Format-List` Befehl verwendet den property-Parameter mit dem Wert "\*" (alle), um alle Eigenschaften der Objekte in einer Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-141">The `Format-List` command uses the Property parameter with a value of '\*' (all) to display all of the properties of the objects in a list.</span></span>
<span data-ttu-id="1f5e2-142">Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-142">The results are shown in the following sample output.</span></span>

<span data-ttu-id="1f5e2-143">In der resultierenden Anzeige werden die Registrierungseinträge "Path" und "ExecutionPolicy" zusammen mit einigen weniger vertrauten Eigenschaften des Registrierungsschlüssel Objekts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-143">The resulting display shows the "Path" and "ExecutionPolicy" registry entries, along with several less familiar properties of the registry key object.</span></span>
<span data-ttu-id="1f5e2-144">Bei den anderen Eigenschaften mit dem Präfix PS handelt es sich um Eigenschaften von benutzerdefinierten PowerShell-Objekten, z. b. die Objekte, die die Registrierungsschlüssel darstellen.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-144">The other properties, prefixed with PS, are properties of PowerShell custom objects, such as the objects that represent the registry keys.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell
```

```output
Path                                                        ExecutionPolicy
----                                                        ---------------
C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe   RemoteSigned
```

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell | Format-List -Property *
```

```output
PSPath          : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds\Micro
soft.PowerShell
PSParentPath    : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds
PSChildName     : Microsoft.PowerShell
PSDrive         : HKLM
PSProvider      : Microsoft.PowerShell.Core\Registry
Path            : C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe
ExecutionPolicy : RemoteSigned
```

## <span data-ttu-id="1f5e2-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1f5e2-145">PARAMETERS</span></span>

### <span data-ttu-id="1f5e2-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="1f5e2-146">-Credential</span></span>

<span data-ttu-id="1f5e2-147">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-147">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="1f5e2-148">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-148">The default is the current user.</span></span>

<span data-ttu-id="1f5e2-149">Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-149">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="1f5e2-150">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-150">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="1f5e2-151">Dieser Parameter wird nicht von mit Windows PowerShell installierten Anbietern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-151">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="1f5e2-152">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="1f5e2-152">-Exclude</span></span>

<span data-ttu-id="1f5e2-153">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-153">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="1f5e2-154">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-154">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="1f5e2-155">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-155">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="1f5e2-156">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-156">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f5e2-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="1f5e2-157">-Filter</span></span>

<span data-ttu-id="1f5e2-158">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-158">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="1f5e2-159">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-159">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="1f5e2-160">Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-160">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="1f5e2-161">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-161">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="1f5e2-162">-Include</span><span class="sxs-lookup"><span data-stu-id="1f5e2-162">-Include</span></span>

<span data-ttu-id="1f5e2-163">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-163">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="1f5e2-164">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-164">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="1f5e2-165">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-165">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="1f5e2-166">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-166">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f5e2-167">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="1f5e2-167">-LiteralPath</span></span>

<span data-ttu-id="1f5e2-168">Gibt den Pfad zum aktuellen Speicherort der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-168">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="1f5e2-169">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-169">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="1f5e2-170">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-170">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="1f5e2-171">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-171">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="1f5e2-172">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-172">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1f5e2-173">-Name</span><span class="sxs-lookup"><span data-stu-id="1f5e2-173">-Name</span></span>

<span data-ttu-id="1f5e2-174">Gibt den Namen der abzurufenden Eigenschaft oder Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-174">Specifies the name of the property or properties to retrieve.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f5e2-175">-Path</span><span class="sxs-lookup"><span data-stu-id="1f5e2-175">-Path</span></span>

<span data-ttu-id="1f5e2-176">Gibt den Pfad zu den Elementen an.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-176">Specifies the path to the item or items.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1f5e2-177">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="1f5e2-177">-UseTransaction</span></span>

<span data-ttu-id="1f5e2-178">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-178">Includes the command in the active transaction.</span></span>
<span data-ttu-id="1f5e2-179">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-179">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="1f5e2-180">Weitere Informationen finden Sie unter schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-180">For more information, see Includes the command in the active transaction.</span></span>
<span data-ttu-id="1f5e2-181">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-181">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="1f5e2-182">Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="1f5e2-182">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="1f5e2-183">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1f5e2-183">CommonParameters</span></span>

<span data-ttu-id="1f5e2-184">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="1f5e2-184">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="1f5e2-185">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="1f5e2-185">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="1f5e2-186">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1f5e2-186">INPUTS</span></span>

### <span data-ttu-id="1f5e2-187">System.String</span><span class="sxs-lookup"><span data-stu-id="1f5e2-187">System.String</span></span>

<span data-ttu-id="1f5e2-188">Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Get-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="1f5e2-188">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="1f5e2-189">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1f5e2-189">OUTPUTS</span></span>

### <span data-ttu-id="1f5e2-190">System. Boolean, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="1f5e2-190">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="1f5e2-191">`Get-ItemProperty` Gibt ein-Objekt für jede Element Eigenschaft zurück, die es abruft.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-191">`Get-ItemProperty` returns an object for each item property that it gets.</span></span>
<span data-ttu-id="1f5e2-192">Der Objekttyp richtet sich nach dem abgerufenen Objekt.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-192">The object type depends on the object that is retrieved.</span></span>
<span data-ttu-id="1f5e2-193">Beispielsweise wird auf einem Dateisystemlaufwerk möglicherweise eine Datei oder ein Ordner zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-193">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="1f5e2-194">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1f5e2-194">NOTES</span></span>

<span data-ttu-id="1f5e2-195">Das- `Get-ItemProperty` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-195">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="1f5e2-196">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie " `Get-PSProvider` " ein.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-196">To list the providers available in your session, type "`Get-PSProvider`".</span></span> <span data-ttu-id="1f5e2-197">Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="1f5e2-197">For more information, see about_Providers.</span></span>

## <span data-ttu-id="1f5e2-198">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1f5e2-198">RELATED LINKS</span></span>

[<span data-ttu-id="1f5e2-199">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f5e2-199">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="1f5e2-200">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f5e2-200">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="1f5e2-201">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f5e2-201">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="1f5e2-202">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f5e2-202">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="1f5e2-203">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f5e2-203">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="1f5e2-204">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f5e2-204">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="1f5e2-205">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1f5e2-205">Set-ItemProperty</span></span>](Set-ItemProperty.md)
