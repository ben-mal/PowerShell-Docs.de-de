---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itempropertyvalue?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemPropertyValue
ms.openlocfilehash: 2dbbbfeac3810f79b976b6a68ab3089e91707fb3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215415"
---
# <span data-ttu-id="f4fe4-103">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="f4fe4-103">Get-ItemPropertyValue</span></span>

## <span data-ttu-id="f4fe4-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f4fe4-104">SYNOPSIS</span></span>
<span data-ttu-id="f4fe4-105">Ruft den Wert für eine oder mehrere Eigenschaften eines angegebenen Elements ab.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-105">Gets the value for one or more properties of a specified item.</span></span>

## <span data-ttu-id="f4fe4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f4fe4-106">SYNTAX</span></span>

### <span data-ttu-id="f4fe4-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="f4fe4-107">Path (Default)</span></span>

```
Get-ItemPropertyValue [[-Path] <String[]>] [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="f4fe4-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="f4fe4-108">LiteralPath</span></span>

```
Get-ItemPropertyValue -LiteralPath <String[]> [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="f4fe4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f4fe4-109">DESCRIPTION</span></span>

<span data-ttu-id="f4fe4-110">Der ruft `Get-ItemPropertyValue` den aktuellen Wert für eine Eigenschaft ab, die Sie angeben, wenn Sie den *Name* -Parameter verwenden, der sich in einem Pfad befindet, den Sie mit dem *path* -Parameter oder dem *literalpath* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-110">The `Get-ItemPropertyValue` gets the current value for a property that you specify when you use the *Name* parameter, located in a path that you specify with either the *Path* or *LiteralPath* parameters.</span></span>

## <span data-ttu-id="f4fe4-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f4fe4-111">EXAMPLES</span></span>

### <span data-ttu-id="f4fe4-112">Beispiel 1: erhalten des Werts der ProductID-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="f4fe4-112">Example 1: Get the value of the ProductID property</span></span>

<span data-ttu-id="f4fe4-113">Mit diesem Befehl wird der Wert der **ProductID-** Eigenschaft des Objekts "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" im Windows-Registrierungs Anbieter abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-113">This command gets the value of the **ProductID** property of the "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" object in the Windows Registry provider.</span></span>

```powershell
Get-ItemPropertyValue 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' -Name ProductID
```

```output
94253-50000-11141-AA785
```

### <span data-ttu-id="f4fe4-114">Beispiel 2: erhalten der letzten Schreibzeit einer Datei oder eines Ordners</span><span class="sxs-lookup"><span data-stu-id="f4fe4-114">Example 2: Get the last write time of a file or folder</span></span>

<span data-ttu-id="f4fe4-115">Mit diesem Befehl wird der Wert der **LastWrite Time** -Eigenschaft oder der Zeitpunkt der letzten Änderung einer Datei oder eines Ordners aus dem Ordner "c:\users\test\documents\modulecomassembly" abgerufen, der im File System-Anbieter funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-115">This command gets the value of the **LastWriteTime** property, or the last time a file or folder was changed, from the "C:\Users\Test\Documents\ModuleToAssembly" folder, working in the FileSystem provider.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime
```

```output
Wednesday, September 3, 2014 2:53:22 PM
```

### <span data-ttu-id="f4fe4-116">Beispiel 3: erhalten mehrerer Eigenschaftswerte einer Datei oder eines Ordners</span><span class="sxs-lookup"><span data-stu-id="f4fe4-116">Example 3: Get multiple property values of a file or folder</span></span>

<span data-ttu-id="f4fe4-117">Mit diesem Befehl werden die Werte der Eigenschaften " **lastschreitetime** ", " **kreationtime** " und " **root** " eines Ordners abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-117">This command gets the values of the **LastWriteTime** , **CreationTime** , and **Root** properties of a folder.</span></span>
<span data-ttu-id="f4fe4-118">Die Eigenschaftswerte werden in der Reihenfolge zurückgegeben, in der Sie die Eigenschaftsnamen angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-118">The property values are returned in the order in which you specified the property names.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime,CreationTime,Root
```

```output
Wednesday, September 3, 2014 2:53:22 PM
Wednesday, September 3, 2014 2:53:10 PM

Name              : C:\
Parent            :
Exists            : True
Root              : C:\
FullName          : C:\
Extension         :
CreationTime      : 9/1/2014 4:59:45 AM
CreationTimeUtc   : 9/1/2014 11:59:45 AM
LastAccessTime    : 9/27/2014 5:22:02 PM
LastAccessTimeUtc : 9/28/2014 12:22:02 AM
LastWriteTime     : 9/27/2014 5:22:02 PM
LastWriteTimeUtc  : 9/28/2014 12:22:02 AM
Attributes        : Hidden, System, Directory
BaseName          : C:\
Target            :
LinkType          :
Mode              : d--hs-
```

## <span data-ttu-id="f4fe4-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f4fe4-119">PARAMETERS</span></span>

### <span data-ttu-id="f4fe4-120">-Credential</span><span class="sxs-lookup"><span data-stu-id="f4fe4-120">-Credential</span></span>

<span data-ttu-id="f4fe4-121">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-121">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="f4fe4-122">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-122">The default is the current user.</span></span>

<span data-ttu-id="f4fe4-123">Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-123">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="f4fe4-124">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-124">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="f4fe4-125">Dieser Parameter wird nicht von mit Windows PowerShell installierten Anbietern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-125">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f4fe4-126">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="f4fe4-126">-Exclude</span></span>

<span data-ttu-id="f4fe4-127">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-127">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="f4fe4-128">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-128">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="f4fe4-129">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-129">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="f4fe4-130">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-130">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="f4fe4-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="f4fe4-131">-Filter</span></span>

<span data-ttu-id="f4fe4-132">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-132">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="f4fe4-133">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-133">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="f4fe4-134">Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-134">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="f4fe4-135">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="f4fe4-136">-Include</span><span class="sxs-lookup"><span data-stu-id="f4fe4-136">-Include</span></span>

<span data-ttu-id="f4fe4-137">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="f4fe4-138">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="f4fe4-139">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="f4fe4-140">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="f4fe4-141">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="f4fe4-141">-LiteralPath</span></span>

<span data-ttu-id="f4fe4-142">Gibt den Pfad zum aktuellen Speicherort der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-142">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="f4fe4-143">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-143">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="f4fe4-144">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-144">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="f4fe4-145">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-145">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="f4fe4-146">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="f4fe4-147">-Name</span><span class="sxs-lookup"><span data-stu-id="f4fe4-147">-Name</span></span>

<span data-ttu-id="f4fe4-148">Gibt den Namen der abzurufenden Eigenschaft oder Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-148">Specifies the name of the property or properties to retrieve.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f4fe4-149">-Path</span><span class="sxs-lookup"><span data-stu-id="f4fe4-149">-Path</span></span>

<span data-ttu-id="f4fe4-150">Gibt den Pfad zu den Elementen an.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-150">Specifies the path to the item or items.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f4fe4-151">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="f4fe4-151">-UseTransaction</span></span>

<span data-ttu-id="f4fe4-152">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-152">Includes the command in the active transaction.</span></span>
<span data-ttu-id="f4fe4-153">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-153">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="f4fe4-154">Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-154">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="f4fe4-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f4fe4-155">CommonParameters</span></span>

<span data-ttu-id="f4fe4-156">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="f4fe4-156">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="f4fe4-157">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="f4fe4-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f4fe4-158">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f4fe4-158">INPUTS</span></span>

### <span data-ttu-id="f4fe4-159">System.String</span><span class="sxs-lookup"><span data-stu-id="f4fe4-159">System.String</span></span>

<span data-ttu-id="f4fe4-160">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-160">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="f4fe4-161">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f4fe4-161">OUTPUTS</span></span>

### <span data-ttu-id="f4fe4-162">System. Boolean, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="f4fe4-162">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="f4fe4-163">Dieses Cmdlet gibt ein Objekt für jeden Elementwert zurück, den es erhält.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-163">This cmdlet returns an object for each item property value that it gets.</span></span>
<span data-ttu-id="f4fe4-164">Der Objekttyp hängt von dem abgerufenen Eigenschafts Wert ab.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-164">The object type depends on the property value that is retrieved.</span></span>
<span data-ttu-id="f4fe4-165">Beispielsweise kann das Cmdlet in einem Dateisystem Laufwerk eine Datei oder einen Ordner zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-165">For example, in a file system drive, the cmdlet might return a file or folder.</span></span>

## <span data-ttu-id="f4fe4-166">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f4fe4-166">NOTES</span></span>

<span data-ttu-id="f4fe4-167">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-167">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="f4fe4-168">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, führen Sie das- `Get-PSProvider` Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-168">To list the providers available in your session, run the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="f4fe4-169">Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="f4fe4-169">For more information, see about_Providers.</span></span>

## <span data-ttu-id="f4fe4-170">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f4fe4-170">RELATED LINKS</span></span>

[<span data-ttu-id="f4fe4-171">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f4fe4-171">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="f4fe4-172">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f4fe4-172">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="f4fe4-173">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f4fe4-173">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="f4fe4-174">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f4fe4-174">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="f4fe4-175">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f4fe4-175">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="f4fe4-176">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f4fe4-176">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="f4fe4-177">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f4fe4-177">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="f4fe4-178">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f4fe4-178">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="f4fe4-179">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="f4fe4-179">Get-PSProvider</span></span>](Get-PSProvider.md)
