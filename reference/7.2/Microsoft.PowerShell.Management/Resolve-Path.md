---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: 0481526aead285e3d5fb494218d1573e03216f2e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604854"
---
# <span data-ttu-id="9bdb9-102">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="9bdb9-102">Resolve-Path</span></span>

## <span data-ttu-id="9bdb9-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9bdb9-103">SYNOPSIS</span></span>
<span data-ttu-id="9bdb9-104">Löst die Platzhalterzeichen in einem Pfad auf und zeigt den Inhalt des Pfads an.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-104">Resolves the wildcard characters in a path, and displays the path contents.</span></span>

## <span data-ttu-id="9bdb9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9bdb9-105">SYNTAX</span></span>

### <span data-ttu-id="9bdb9-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="9bdb9-106">Path (Default)</span></span>

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="9bdb9-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9bdb9-107">LiteralPath</span></span>

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="9bdb9-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9bdb9-108">DESCRIPTION</span></span>

<span data-ttu-id="9bdb9-109">Das `Resolve-Path` -Cmdlet zeigt die Elemente und Container an, die dem Platzhalter Muster am angegebenen Speicherort entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-109">The `Resolve-Path` cmdlet displays the items and containers that match the wildcard pattern at the location specified.</span></span> <span data-ttu-id="9bdb9-110">Die Entsprechung kann Dateien, Ordner, Registrierungsschlüssel oder ein beliebiges anderes Objekt enthalten, auf das von einem PSDrive-Anbieter zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-110">The match can include files, folders, registry keys, or any other object accessible from a PSDrive provider.</span></span>

## <span data-ttu-id="9bdb9-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9bdb9-111">EXAMPLES</span></span>

### <span data-ttu-id="9bdb9-112">Beispiel 1: Auflösen des Basisordner Pfads</span><span class="sxs-lookup"><span data-stu-id="9bdb9-112">Example 1: Resolve the home folder path</span></span>

<span data-ttu-id="9bdb9-113">Das Tildezeichen (~) ist eine Kurznotiz für den Basisordner des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-113">The tilde character (~) is shorthand notation for the current user's home folder.</span></span> <span data-ttu-id="9bdb9-114">Dieses Beispiel zeigt, wie Sie `Resolve-Path` den voll qualifizierten Pfadwert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-114">This example shows `Resolve-Path` returning the fully qualified path value.</span></span>

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### <span data-ttu-id="9bdb9-115">Beispiel 2: Auflösen des Pfads des Windows-Ordners</span><span class="sxs-lookup"><span data-stu-id="9bdb9-115">Example 2: Resolve the path of the Windows folder</span></span>

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="9bdb9-116">Bei der Durchführung vom Stamm des Laufwerks c: gibt dieser Befehl den Pfad des Windows-Ordners auf Laufwerk c: zurück.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-116">When run from the root of the C: drive, this command returns the path of the Windows folder in the C: drive.</span></span>

### <span data-ttu-id="9bdb9-117">Beispiel 3: alle Pfade im Windows-Ordner</span><span class="sxs-lookup"><span data-stu-id="9bdb9-117">Example 3: Get all paths in the Windows folder</span></span>

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

<span data-ttu-id="9bdb9-118">Mit diesem Befehl werden alle Ordner im Ordner "c:\Windows" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-118">This command returns all of the folders in the C:\Windows folder.</span></span> <span data-ttu-id="9bdb9-119">Der Befehl verwendet einen Pipeline Operator (|), um eine Pfad Zeichenfolge an zu senden `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="9bdb9-119">The command uses a pipeline operator (|) to send a path string to `Resolve-Path`.</span></span>

### <span data-ttu-id="9bdb9-120">Beispiel 4: Auflösen eines UNC-Pfads</span><span class="sxs-lookup"><span data-stu-id="9bdb9-120">Example 4: Resolve a UNC path</span></span>

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

<span data-ttu-id="9bdb9-121">Dieser Befehl löst einen UNC (Universal Naming Convention)-Pfad auf und gibt die Freigaben im Pfad zurück.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-121">This command resolves a Universal Naming Convention (UNC) path and returns the shares in the path.</span></span>

### <span data-ttu-id="9bdb9-122">Beispiel 5: erhalten relativer Pfade</span><span class="sxs-lookup"><span data-stu-id="9bdb9-122">Example 5: Get relative paths</span></span>

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

<span data-ttu-id="9bdb9-123">Dieser Befehl gibt relative Pfade für die Verzeichnisse im Stammverzeichnis von Laufwerk %%amp;quot;C:%%amp;quot; zurück.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-123">This command returns relative paths for the directories at the root of the C: drive.</span></span>

### <span data-ttu-id="9bdb9-124">Beispiel 6: Auflösen eines Pfads, der eckige Klammern enthält</span><span class="sxs-lookup"><span data-stu-id="9bdb9-124">Example 6: Resolve a path containing brackets</span></span>

<span data-ttu-id="9bdb9-125">Dieses Beispiel verwendet den **literalpath** -Parameter, um den Pfad des Test- \[ XML- \] unter Ordners aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-125">This example uses the **LiteralPath** parameter to resolve the path of the Test\[xml\] subfolder.</span></span>
<span data-ttu-id="9bdb9-126">Die Verwendung von **literalpath** bewirkt, dass die Klammern als normale Zeichen und nicht als regulärer Ausdruck behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-126">Using **LiteralPath** causes the brackets to be treated as normal characters rather than a regular expression.</span></span>

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## <span data-ttu-id="9bdb9-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9bdb9-127">PARAMETERS</span></span>

### <span data-ttu-id="9bdb9-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="9bdb9-128">-Credential</span></span>

<span data-ttu-id="9bdb9-129">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-129">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="9bdb9-130">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-130">The default is the current user.</span></span>

<span data-ttu-id="9bdb9-131">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder übergeben Sie ein **PSCredential** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-131">Type a user name, such as User01 or Domain01\User01, or pass a **PSCredential** object.</span></span> <span data-ttu-id="9bdb9-132">Sie können ein **PSCredential** -Objekt mit dem `Get-Credential` Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-132">You can create a **PSCredential** object using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="9bdb9-133">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-133">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="9bdb9-134">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-134">This parameter is not supported by any providers installed with PowerShell.</span></span>

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

### <span data-ttu-id="9bdb9-135">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="9bdb9-135">-LiteralPath</span></span>

<span data-ttu-id="9bdb9-136">Gibt den aufzulösenden Pfad an.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-136">Specifies the path to be resolved.</span></span>
<span data-ttu-id="9bdb9-137">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-137">The value of the **LiteralPath** parameter is used exactly as typed.</span></span>
<span data-ttu-id="9bdb9-138">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-138">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="9bdb9-139">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-139">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="9bdb9-140">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-140">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="9bdb9-141">-Path</span><span class="sxs-lookup"><span data-stu-id="9bdb9-141">-Path</span></span>

<span data-ttu-id="9bdb9-142">Gibt den aufzulösenden PowerShell-Pfad an.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-142">Specifies the PowerShell path to resolve.</span></span>
<span data-ttu-id="9bdb9-143">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-143">This parameter is required.</span></span>
<span data-ttu-id="9bdb9-144">Sie können eine Pfad Zeichenfolge auch über die Pipeline an übergeben `Resolve-Path` .</span><span class="sxs-lookup"><span data-stu-id="9bdb9-144">You can also pipe a path string to `Resolve-Path`.</span></span>
<span data-ttu-id="9bdb9-145">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-145">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="9bdb9-146">-Relativ</span><span class="sxs-lookup"><span data-stu-id="9bdb9-146">-Relative</span></span>

<span data-ttu-id="9bdb9-147">Gibt an, dass dieses Cmdlet einen relativen Pfad zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-147">Indicates that this cmdlet returns a relative path.</span></span>

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

### <span data-ttu-id="9bdb9-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9bdb9-148">CommonParameters</span></span>

<span data-ttu-id="9bdb9-149">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9bdb9-150">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9bdb9-150">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9bdb9-151">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9bdb9-151">INPUTS</span></span>

### <span data-ttu-id="9bdb9-152">System.String</span><span class="sxs-lookup"><span data-stu-id="9bdb9-152">System.String</span></span>

<span data-ttu-id="9bdb9-153">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-153">You can pipe a string that contains a path to this cmdlet</span></span>

## <span data-ttu-id="9bdb9-154">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9bdb9-154">OUTPUTS</span></span>

### <span data-ttu-id="9bdb9-155">System. Management. Automation. PathInfo, System. String</span><span class="sxs-lookup"><span data-stu-id="9bdb9-155">System.Management.Automation.PathInfo, System.String</span></span>

<span data-ttu-id="9bdb9-156">Gibt ein **pathinfo** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-156">Returns a **PathInfo** object.</span></span> <span data-ttu-id="9bdb9-157">Gibt einen Zeichen folgen Wert für den aufgelösten Pfad zurück, wenn Sie den **relativen** Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-157">Returns a string value for the resolved path if you specify the **Relative** parameter.</span></span>

## <span data-ttu-id="9bdb9-158">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9bdb9-158">NOTES</span></span>

<span data-ttu-id="9bdb9-159">Die `*-Path` Cmdlets funktionieren mit dem Dateisystem, der Registrierung und den Zertifikat Anbietern.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-159">The `*-Path` cmdlets work with the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="9bdb9-160">`Resolve-Path` ist für den Einsatz mit jedem Anbieter konzipiert.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-160">`Resolve-Path` is designed to work with any provider.</span></span> <span data-ttu-id="9bdb9-161">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="9bdb9-161">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="9bdb9-162">Weitere Informationen finden Sie unter [about_Providers](../microsoft.powershell.core/about/about_providers.md).</span><span class="sxs-lookup"><span data-stu-id="9bdb9-162">For more information, see [about_providers](../microsoft.powershell.core/about/about_providers.md).</span></span>

<span data-ttu-id="9bdb9-163">`Resolve-Path` löst nur vorhandene Pfade auf.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-163">`Resolve-Path` only resolves existing paths.</span></span> <span data-ttu-id="9bdb9-164">Sie kann nicht verwendet werden, um einen Speicherort aufzulösen, der noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9bdb9-164">It cannot be used to resolve a location that does not exist yet.</span></span>

## <span data-ttu-id="9bdb9-165">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9bdb9-165">RELATED LINKS</span></span>

[<span data-ttu-id="9bdb9-166">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="9bdb9-166">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="9bdb9-167">Join-Path</span><span class="sxs-lookup"><span data-stu-id="9bdb9-167">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="9bdb9-168">Split-Path</span><span class="sxs-lookup"><span data-stu-id="9bdb9-168">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="9bdb9-169">Test-Path</span><span class="sxs-lookup"><span data-stu-id="9bdb9-169">Test-Path</span></span>](Test-Path.md)

