---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-hotfix?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HotFix
ms.openlocfilehash: 277dd2678b54c9e708d09f6ca27d82ab9afd4c1c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347617"
---
# <span data-ttu-id="4784d-103">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="4784d-103">Get-HotFix</span></span>

## <span data-ttu-id="4784d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4784d-104">SYNOPSIS</span></span>
<span data-ttu-id="4784d-105">Ruft die Hotfixes ab, die auf lokalen Computern oder Remote Computern installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4784d-105">Gets the hotfixes that are installed on local or remote computers.</span></span>

## <span data-ttu-id="4784d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4784d-106">SYNTAX</span></span>

### <span data-ttu-id="4784d-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="4784d-107">Default (Default)</span></span>

```
Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

### <span data-ttu-id="4784d-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4784d-108">Description</span></span>

```
Get-HotFix [-Description <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

## <span data-ttu-id="4784d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4784d-109">DESCRIPTION</span></span>

<span data-ttu-id="4784d-110">Das- `Get-Hotfix` Cmdlet ruft Hotfixes oder Updates ab, die auf dem lokalen Computer oder den angegebenen Remote Computern installiert sind.</span><span class="sxs-lookup"><span data-stu-id="4784d-110">The `Get-Hotfix` cmdlet gets hotfixes, or updates, that are installed on the local computer or specified remote computers.</span></span> <span data-ttu-id="4784d-111">Die Updates können Windows Update, Microsoft Update, Windows Server Update Services oder manuell installiert werden.</span><span class="sxs-lookup"><span data-stu-id="4784d-111">The updates can be installed by Windows Update, Microsoft Update, Windows Server Update Services, or manually installed.</span></span>

## <span data-ttu-id="4784d-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4784d-112">EXAMPLES</span></span>

### <span data-ttu-id="4784d-113">Beispiel 1: alle Hotfixes auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="4784d-113">Example 1: Get all hotfixes on the local computer</span></span>

<span data-ttu-id="4784d-114">Mit dem- `Get-Hotfix` Cmdlet werden alle auf dem lokalen Computer installierten Hotfixes abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4784d-114">The `Get-Hotfix` cmdlet gets all hotfixes installed on the local computer.</span></span>

```powershell
Get-HotFix
```

```output
Source         Description      HotFixID      InstalledBy          InstalledOn
------         -----------      --------      -----------          -----------
Server01       Update           KB4495590     NT AUTHORITY\SYSTEM  5/16/2019 00:00:00
Server01       Security Update  KB4470788     NT AUTHORITY\SYSTEM  1/22/2019 00:00:00
Server01       Update           KB4480056     NT AUTHORITY\SYSTEM  1/24/2019 00:00:00
```

### <span data-ttu-id="4784d-115">Beispiel 2: erhalten von Hotfixes von mehreren Computern, die nach einer Zeichenfolge gefiltert sind</span><span class="sxs-lookup"><span data-stu-id="4784d-115">Example 2: Get hotfixes from multiple computers filtered by a string</span></span>

<span data-ttu-id="4784d-116">Der `Get-Hotfix` Befehl verwendet Parameter, um Hotfixes auf Remote Computern zu installieren.</span><span class="sxs-lookup"><span data-stu-id="4784d-116">The `Get-Hotfix` command uses parameters to get hotfixes installed on remote computers.</span></span> <span data-ttu-id="4784d-117">Die Ergebnisse werden anhand einer angegebenen Beschreibungs Zeichenfolge gefiltert.</span><span class="sxs-lookup"><span data-stu-id="4784d-117">The results are filtered by a specified description string.</span></span>

```
PS> Get-HotFix -Description Security* -ComputerName Server01, Server02 -Credential Domain01\admin01
```

<span data-ttu-id="4784d-118">`Get-Hotfix` filtert die Ausgabe mit dem **Beschreibungs** Parameter und der Zeichen folgen **Sicherheit** , die das Sternchen-Platzhalter Zeichen ( `*` ) enthält.</span><span class="sxs-lookup"><span data-stu-id="4784d-118">`Get-Hotfix` filters the output with the **Description** parameter and the string **Security** that includes the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="4784d-119">Der **Computername** -Parameter enthält eine durch Trennzeichen getrennte Zeichenfolge von Remote Computernamen.</span><span class="sxs-lookup"><span data-stu-id="4784d-119">The **ComputerName** parameter includes a comma-separated string of remote computer names.</span></span> <span data-ttu-id="4784d-120">Der **Credential** -Parameter gibt ein Benutzerkonto an, das über die Berechtigung zum Zugreifen auf die Remote Computer und zum Ausführen von Befehlen verfügt.</span><span class="sxs-lookup"><span data-stu-id="4784d-120">The **Credential** parameter specifies a user account that has permission to access the remote computers and run commands.</span></span>

### <span data-ttu-id="4784d-121">Beispiel 3: überprüfen, ob ein Update installiert ist, und Schreiben von Computernamen in eine Datei</span><span class="sxs-lookup"><span data-stu-id="4784d-121">Example 3: Verify if an update is installed and write computer names to a file</span></span>

<span data-ttu-id="4784d-122">Mit den Befehlen in diesem Beispiel wird überprüft, ob ein bestimmtes Update installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4784d-122">The commands in this example verify whether a particular update installed.</span></span> <span data-ttu-id="4784d-123">Wenn das Update nicht installiert ist, wird der Computername in eine Textdatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="4784d-123">If the update isn't installed, the computer name is written to a text file.</span></span>

```
PS> $A = Get-Content -Path ./Servers.txt
PS> $A | ForEach-Object { if (!(Get-HotFix -Id KB957095 -ComputerName $_))
         { Add-Content $_ -Path ./Missing-KB957095.txt }}
```

<span data-ttu-id="4784d-124">Die- `$A` Variable enthält Computernamen, die von `Get-Content` aus einer Textdatei abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="4784d-124">The `$A` variable contains computer names that were obtained by `Get-Content` from a text file.</span></span> <span data-ttu-id="4784d-125">Die Objekte in `$A` werden über die Pipeline an gesendet `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="4784d-125">The objects in `$A` are sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="4784d-126">Eine `if` -Anweisung verwendet das `Get-Hotfix` -Cmdlet mit dem **ID** -Parameter und eine bestimmte ID-Nummer für jeden Computernamen.</span><span class="sxs-lookup"><span data-stu-id="4784d-126">An `if` statement uses the `Get-Hotfix` cmdlet with the **Id** parameter and a specific Id number for each computer name.</span></span> <span data-ttu-id="4784d-127">Wenn auf einem Computer die angegebene HotFixID nicht installiert ist, `Add-Content` schreibt das Cmdlet den Computernamen in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="4784d-127">If a computer doesn't have the specified hotfix Id installed, the `Add-Content` cmdlet writes the computer name to a file.</span></span>

### <span data-ttu-id="4784d-128">Beispiel 4: Holen Sie sich den neuesten Hotfix auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="4784d-128">Example 4: Get the most recent hotfix on the local computer</span></span>

<span data-ttu-id="4784d-129">In diesem Beispiel wird der aktuelle Hotfix abgerufen, der auf einem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4784d-129">This example gets the most recent hotfix installed on a computer.</span></span>

```powershell
(Get-HotFix | Sort-Object -Property InstalledOn)[-1]
```

<span data-ttu-id="4784d-130">`Get-Hotfix` sendet die Objekte in der Pipeline an das `Sort-Object` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4784d-130">`Get-Hotfix` sends the objects down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="4784d-131">`Sort-Object` sortiert Objekte in aufsteigender Reihenfolge und verwendet den **Property** -Parameter zum Auswerten der einzelnen **installedon** -Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="4784d-131">`Sort-Object` sorts objects by ascending order and uses the **Property** parameter to evaluate each **InstalledOn** date.</span></span> <span data-ttu-id="4784d-132">Die Array Notation `[-1]` wählt den neuesten installierten Hotfix aus.</span><span class="sxs-lookup"><span data-stu-id="4784d-132">The array notation `[-1]` selects the most recent installed hotfix.</span></span>

## <span data-ttu-id="4784d-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4784d-133">PARAMETERS</span></span>

### <span data-ttu-id="4784d-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="4784d-134">-ComputerName</span></span>

<span data-ttu-id="4784d-135">Gibt einen Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="4784d-135">Specifies a remote computer.</span></span> <span data-ttu-id="4784d-136">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines Remote Computers ein.</span><span class="sxs-lookup"><span data-stu-id="4784d-136">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>

<span data-ttu-id="4784d-137">Wenn der **Computername** -Parameter nicht angegeben wird, wird `Get-Hotfix` auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4784d-137">When the **ComputerName** parameter isn't specified, `Get-Hotfix` runs on the local computer.</span></span>

<span data-ttu-id="4784d-138">Der **Computername** -Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="4784d-138">The **ComputerName** parameter doesn't rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="4784d-139">Wenn Ihr Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist, verwenden Sie den **Computername** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="4784d-139">If your computer isn't configured to run remote commands, use the **ComputerName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __Server, IPAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4784d-140">-Credential</span><span class="sxs-lookup"><span data-stu-id="4784d-140">-Credential</span></span>

<span data-ttu-id="4784d-141">Gibt ein Benutzerkonto an, das über die Berechtigung zum Zugreifen auf den Computer und zum Ausführen von Befehlen verfügt.</span><span class="sxs-lookup"><span data-stu-id="4784d-141">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="4784d-142">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4784d-142">The default is the current user</span></span>

<span data-ttu-id="4784d-143">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4784d-143">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="4784d-144">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4784d-144">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="4784d-145">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4784d-145">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="4784d-146">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="4784d-146">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4784d-147">-Description</span><span class="sxs-lookup"><span data-stu-id="4784d-147">-Description</span></span>

<span data-ttu-id="4784d-148">`Get-HotFix` verwendet den **Description** -Parameter, um hotfixtypen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4784d-148">`Get-HotFix` uses the **Description** parameter to specify hotfix types.</span></span> <span data-ttu-id="4784d-149">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="4784d-149">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Description
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="4784d-150">-Id</span><span class="sxs-lookup"><span data-stu-id="4784d-150">-Id</span></span>

<span data-ttu-id="4784d-151">Filtert die `Get-HotFix` Ergebnisse für bestimmte HotfixIDs.</span><span class="sxs-lookup"><span data-stu-id="4784d-151">Filters the `Get-HotFix` results for specific hotfix Ids.</span></span> <span data-ttu-id="4784d-152">Platzhalter werden nicht akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4784d-152">Wildcards aren't accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: HFID

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4784d-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4784d-153">CommonParameters</span></span>

<span data-ttu-id="4784d-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4784d-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4784d-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4784d-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4784d-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4784d-156">INPUTS</span></span>

### <span data-ttu-id="4784d-157">String</span><span class="sxs-lookup"><span data-stu-id="4784d-157">String</span></span>

<span data-ttu-id="4784d-158">Sie können einen oder mehrere Computernamen über die Pipeline an Get-Hotfix übergeben.</span><span class="sxs-lookup"><span data-stu-id="4784d-158">You can pipe one or more computer names to Get-HotFix.</span></span>

## <span data-ttu-id="4784d-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4784d-159">OUTPUTS</span></span>

### <span data-ttu-id="4784d-160">System. Management. ManagementObject # root\cimv2\ Win32_QuickFixEngineering</span><span class="sxs-lookup"><span data-stu-id="4784d-160">System.Management.ManagementObject#root\CIMV2\Win32_QuickFixEngineering</span></span>

<span data-ttu-id="4784d-161">`Get-HotFix` gibt-Objekte zurück, die die Hotfixes auf dem Computer darstellen.</span><span class="sxs-lookup"><span data-stu-id="4784d-161">`Get-HotFix` returns objects that represent the hotfixes on the computer.</span></span>

## <span data-ttu-id="4784d-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4784d-162">NOTES</span></span>

<span data-ttu-id="4784d-163">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4784d-163">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="4784d-164">Die **Win32_QuickFixEngineering** [WMI-Klasse](/windows/desktop/WmiSdk/retrieving-a-class) stellt ein kleines systemweites Update dar, das auf das aktuelle Betriebssystem häufig als Update für die schnelle Korrektur Technik (Quick fixengineering, QFE) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="4784d-164">The **Win32_QuickFixEngineering** [WMI class](/windows/desktop/WmiSdk/retrieving-a-class) represents a small system-wide update, commonly referred to as a quick-fix engineering (QFE) update, applied to the current operating system.</span></span> <span data-ttu-id="4784d-165">Diese Klasse gibt nur die von der komponentenbasierten Wartung (Component based Wartung, CBS) bereitgestellten Updates zurück.</span><span class="sxs-lookup"><span data-stu-id="4784d-165">This class returns only the updates supplied by Component Based Servicing (CBS).</span></span> <span data-ttu-id="4784d-166">Diese Updates sind nicht in der Registrierung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="4784d-166">These updates are not listed in the registry.</span></span> <span data-ttu-id="4784d-167">Von der Microsoft Windows Installer (MSI) oder der [Windows Update](https://update.microsoft.com) Site bereitgestellte Updates werden von **Win32_QuickFixEngineering** nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4784d-167">Updates supplied by Microsoft Windows Installer (MSI) or the [Windows Update](https://update.microsoft.com) site are not returned by **Win32_QuickFixEngineering**.</span></span> <span data-ttu-id="4784d-168">Weitere Informationen finden Sie unter [Win32_QuickFixEngineering-Klasse](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).</span><span class="sxs-lookup"><span data-stu-id="4784d-168">For more information, see [Win32_QuickFixEngineering class](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).</span></span>

<span data-ttu-id="4784d-169">Die `Get-HotFix` Ausgabe kann sich je nach Betriebssystem unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4784d-169">The `Get-HotFix` output might vary on different operating systems.</span></span>

## <span data-ttu-id="4784d-170">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4784d-170">RELATED LINKS</span></span>

[<span data-ttu-id="4784d-171">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="4784d-171">about_Arrays</span></span>](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[<span data-ttu-id="4784d-172">Add-Content</span><span class="sxs-lookup"><span data-stu-id="4784d-172">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="4784d-173">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="4784d-173">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="4784d-174">Win32_QuickFixEngineering-Klasse</span><span class="sxs-lookup"><span data-stu-id="4784d-174">Win32_QuickFixEngineering class</span></span>](/windows/desktop/CIMWin32Prov/win32-quickfixengineering)
