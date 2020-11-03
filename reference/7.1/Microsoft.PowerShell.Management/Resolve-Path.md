---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: d5a4e16f06ae98532f9716deb87dcadac50f8081
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211527"
---
# <span data-ttu-id="23748-103">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="23748-103">Resolve-Path</span></span>

## <span data-ttu-id="23748-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="23748-104">SYNOPSIS</span></span>
<span data-ttu-id="23748-105">Löst die Platzhalterzeichen in einem Pfad auf und zeigt den Inhalt des Pfads an.</span><span class="sxs-lookup"><span data-stu-id="23748-105">Resolves the wildcard characters in a path, and displays the path contents.</span></span>

## <span data-ttu-id="23748-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23748-106">SYNTAX</span></span>

### <span data-ttu-id="23748-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="23748-107">Path (Default)</span></span>

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="23748-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="23748-108">LiteralPath</span></span>

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="23748-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23748-109">DESCRIPTION</span></span>

<span data-ttu-id="23748-110">Das `Resolve-Path` -Cmdlet zeigt die Elemente und Container an, die dem Platzhalter Muster am angegebenen Speicherort entsprechen.</span><span class="sxs-lookup"><span data-stu-id="23748-110">The `Resolve-Path` cmdlet displays the items and containers that match the wildcard pattern at the location specified.</span></span> <span data-ttu-id="23748-111">Die Entsprechung kann Dateien, Ordner, Registrierungsschlüssel oder ein beliebiges anderes Objekt enthalten, auf das von einem PSDrive-Anbieter zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="23748-111">The match can include files, folders, registry keys, or any other object accessible from a PSDrive provider.</span></span>

## <span data-ttu-id="23748-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="23748-112">EXAMPLES</span></span>

### <span data-ttu-id="23748-113">Beispiel 1: Auflösen des Basisordner Pfads</span><span class="sxs-lookup"><span data-stu-id="23748-113">Example 1: Resolve the home folder path</span></span>

<span data-ttu-id="23748-114">Das Tildezeichen (~) ist eine Kurznotiz für den Basisordner des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="23748-114">The tilde character (~) is shorthand notation for the current user's home folder.</span></span> <span data-ttu-id="23748-115">Dieses Beispiel zeigt, wie Sie `Resolve-Path` den voll qualifizierten Pfadwert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="23748-115">This example shows `Resolve-Path` returning the fully qualified path value.</span></span>

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### <span data-ttu-id="23748-116">Beispiel 2: Auflösen des Pfads des Windows-Ordners</span><span class="sxs-lookup"><span data-stu-id="23748-116">Example 2: Resolve the path of the Windows folder</span></span>

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="23748-117">Bei der Durchführung vom Stamm des Laufwerks c: gibt dieser Befehl den Pfad des Windows-Ordners auf Laufwerk c: zurück.</span><span class="sxs-lookup"><span data-stu-id="23748-117">When run from the root of the C: drive, this command returns the path of the Windows folder in the C: drive.</span></span>

### <span data-ttu-id="23748-118">Beispiel 3: alle Pfade im Windows-Ordner</span><span class="sxs-lookup"><span data-stu-id="23748-118">Example 3: Get all paths in the Windows folder</span></span>

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

<span data-ttu-id="23748-119">Mit diesem Befehl werden alle Ordner im Ordner "c:\Windows" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23748-119">This command returns all of the folders in the C:\Windows folder.</span></span> <span data-ttu-id="23748-120">Der Befehl verwendet einen Pipeline Operator (|), um eine Pfad Zeichenfolge an zu senden `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="23748-120">The command uses a pipeline operator (|) to send a path string to `Resolve-Path`.</span></span>

### <span data-ttu-id="23748-121">Beispiel 4: Auflösen eines UNC-Pfads</span><span class="sxs-lookup"><span data-stu-id="23748-121">Example 4: Resolve a UNC path</span></span>

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

<span data-ttu-id="23748-122">Dieser Befehl löst einen UNC (Universal Naming Convention)-Pfad auf und gibt die Freigaben im Pfad zurück.</span><span class="sxs-lookup"><span data-stu-id="23748-122">This command resolves a Universal Naming Convention (UNC) path and returns the shares in the path.</span></span>

### <span data-ttu-id="23748-123">Beispiel 5: erhalten relativer Pfade</span><span class="sxs-lookup"><span data-stu-id="23748-123">Example 5: Get relative paths</span></span>

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

<span data-ttu-id="23748-124">Dieser Befehl gibt relative Pfade für die Verzeichnisse im Stammverzeichnis von Laufwerk %%amp;quot;C:%%amp;quot; zurück.</span><span class="sxs-lookup"><span data-stu-id="23748-124">This command returns relative paths for the directories at the root of the C: drive.</span></span>

### <span data-ttu-id="23748-125">Beispiel 6: Auflösen eines Pfads, der eckige Klammern enthält</span><span class="sxs-lookup"><span data-stu-id="23748-125">Example 6: Resolve a path containing brackets</span></span>

<span data-ttu-id="23748-126">Dieses Beispiel verwendet den **literalpath** -Parameter, um den Pfad des Test- \[ XML- \] unter Ordners aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="23748-126">This example uses the **LiteralPath** parameter to resolve the path of the Test\[xml\] subfolder.</span></span>
<span data-ttu-id="23748-127">Die Verwendung von **literalpath** bewirkt, dass die Klammern als normale Zeichen und nicht als regulärer Ausdruck behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="23748-127">Using **LiteralPath** causes the brackets to be treated as normal characters rather than a regular expression.</span></span>

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## <span data-ttu-id="23748-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23748-128">PARAMETERS</span></span>

### <span data-ttu-id="23748-129">-Credential</span><span class="sxs-lookup"><span data-stu-id="23748-129">-Credential</span></span>

<span data-ttu-id="23748-130">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="23748-130">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="23748-131">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="23748-131">The default is the current user.</span></span>

<span data-ttu-id="23748-132">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder übergeben Sie ein **PSCredential** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="23748-132">Type a user name, such as User01 or Domain01\User01, or pass a **PSCredential** object.</span></span> <span data-ttu-id="23748-133">Sie können ein **PSCredential** -Objekt mit dem `Get-Credential` Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="23748-133">You can create a **PSCredential** object using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="23748-134">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="23748-134">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="23748-135">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="23748-135">This parameter is not supported by any providers installed with PowerShell.</span></span>

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

### <span data-ttu-id="23748-136">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="23748-136">-LiteralPath</span></span>

<span data-ttu-id="23748-137">Gibt den aufzulösenden Pfad an.</span><span class="sxs-lookup"><span data-stu-id="23748-137">Specifies the path to be resolved.</span></span>
<span data-ttu-id="23748-138">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="23748-138">The value of the **LiteralPath** parameter is used exactly as typed.</span></span>
<span data-ttu-id="23748-139">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="23748-139">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="23748-140">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="23748-140">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="23748-141">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="23748-141">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="23748-142">-Path</span><span class="sxs-lookup"><span data-stu-id="23748-142">-Path</span></span>

<span data-ttu-id="23748-143">Gibt den aufzulösenden PowerShell-Pfad an.</span><span class="sxs-lookup"><span data-stu-id="23748-143">Specifies the PowerShell path to resolve.</span></span>
<span data-ttu-id="23748-144">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="23748-144">This parameter is required.</span></span>
<span data-ttu-id="23748-145">Sie können eine Pfad Zeichenfolge auch über die Pipeline an übergeben `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="23748-145">You can also pipe a path string to `Resolve-Path`.</span></span>
<span data-ttu-id="23748-146">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="23748-146">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="23748-147">-Relativ</span><span class="sxs-lookup"><span data-stu-id="23748-147">-Relative</span></span>

<span data-ttu-id="23748-148">Gibt an, dass dieses Cmdlet einen relativen Pfad zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="23748-148">Indicates that this cmdlet returns a relative path.</span></span>

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

### <span data-ttu-id="23748-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23748-149">CommonParameters</span></span>

<span data-ttu-id="23748-150">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="23748-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23748-151">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="23748-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="23748-152">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="23748-152">INPUTS</span></span>

### <span data-ttu-id="23748-153">System.String</span><span class="sxs-lookup"><span data-stu-id="23748-153">System.String</span></span>

<span data-ttu-id="23748-154">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="23748-154">You can pipe a string that contains a path to this cmdlet</span></span>

## <span data-ttu-id="23748-155">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="23748-155">OUTPUTS</span></span>

### <span data-ttu-id="23748-156">System. Management. Automation. PathInfo, System. String</span><span class="sxs-lookup"><span data-stu-id="23748-156">System.Management.Automation.PathInfo, System.String</span></span>

<span data-ttu-id="23748-157">Gibt ein **pathinfo** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="23748-157">Returns a **PathInfo** object.</span></span> <span data-ttu-id="23748-158">Gibt einen Zeichen folgen Wert für den aufgelösten Pfad zurück, wenn Sie den **relativen** Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="23748-158">Returns a string value for the resolved path if you specify the **Relative** parameter.</span></span>

## <span data-ttu-id="23748-159">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="23748-159">NOTES</span></span>

<span data-ttu-id="23748-160">Die `*-Path` Cmdlets funktionieren mit dem Dateisystem, der Registrierung und den Zertifikat Anbietern.</span><span class="sxs-lookup"><span data-stu-id="23748-160">The `*-Path` cmdlets work with the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="23748-161">`Resolve-Path` ist für den Einsatz mit jedem Anbieter konzipiert.</span><span class="sxs-lookup"><span data-stu-id="23748-161">`Resolve-Path` is designed to work with any provider.</span></span> <span data-ttu-id="23748-162">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="23748-162">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="23748-163">Weitere Informationen finden Sie unter [about_Providers](../microsoft.powershell.core/about/about_providers.md).</span><span class="sxs-lookup"><span data-stu-id="23748-163">For more information, see [about_providers](../microsoft.powershell.core/about/about_providers.md).</span></span>

<span data-ttu-id="23748-164">`Resolve-Path` löst nur vorhandene Pfade auf.</span><span class="sxs-lookup"><span data-stu-id="23748-164">`Resolve-Path` only resolves existing paths.</span></span> <span data-ttu-id="23748-165">Sie kann nicht verwendet werden, um einen Speicherort aufzulösen, der noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="23748-165">It cannot be used to resolve a location that does not exist yet.</span></span>

## <span data-ttu-id="23748-166">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="23748-166">RELATED LINKS</span></span>

[<span data-ttu-id="23748-167">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="23748-167">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="23748-168">Join-Path</span><span class="sxs-lookup"><span data-stu-id="23748-168">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="23748-169">Split-Path</span><span class="sxs-lookup"><span data-stu-id="23748-169">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="23748-170">Test-Path</span><span class="sxs-lookup"><span data-stu-id="23748-170">Test-Path</span></span>](Test-Path.md)

