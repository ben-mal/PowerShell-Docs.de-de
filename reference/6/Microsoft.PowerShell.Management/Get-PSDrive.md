---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psdrive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSDrive
ms.openlocfilehash: f5000ec88defda441d5f31f6ead5d8c37412857b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216324"
---
# <span data-ttu-id="26cb1-103">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="26cb1-103">Get-PSDrive</span></span>

## <span data-ttu-id="26cb1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="26cb1-104">SYNOPSIS</span></span>
<span data-ttu-id="26cb1-105">Ruft Laufwerke in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="26cb1-105">Gets drives in the current session.</span></span>

## <span data-ttu-id="26cb1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="26cb1-106">SYNTAX</span></span>

### <span data-ttu-id="26cb1-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="26cb1-107">Name (Default)</span></span>

```
Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="26cb1-108">LiteralName</span><span class="sxs-lookup"><span data-stu-id="26cb1-108">LiteralName</span></span>

```
Get-PSDrive [-LiteralName] <String[]> [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="26cb1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="26cb1-109">DESCRIPTION</span></span>

<span data-ttu-id="26cb1-110">Mit dem- `Get-PSDrive` Cmdlet werden die Laufwerke in der aktuellen Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="26cb1-110">The `Get-PSDrive` cmdlet gets the drives in the current session.</span></span> <span data-ttu-id="26cb1-111">Sie können ein bestimmtes Laufwerk oder alle Laufwerke in der Sitzung abrufen.</span><span class="sxs-lookup"><span data-stu-id="26cb1-111">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="26cb1-112">Dieses Cmdlet ruft die folgenden Laufwerkstypen ab:</span><span class="sxs-lookup"><span data-stu-id="26cb1-112">This cmdlet gets the following types of drives:</span></span>

- <span data-ttu-id="26cb1-113">Logische Windows-Laufwerke auf dem Computer, einschließlich den Netzwerkfreigaben zugeordneten Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="26cb1-113">Windows logical drives on the computer, including drives mapped to network shares.</span></span>
- <span data-ttu-id="26cb1-114">Laufwerke, die von PowerShell-Anbietern verfügbar gemacht werden (z. b. das Zertifikat:, Funktion: und Alias: Laufwerke) und die Laufwerke HKLM: und HKCU:, die vom Windows PowerShell-Registrierungs Anbieter verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-114">Drives exposed by PowerShell providers (such as the Certificate:, Function:, and Alias: drives) and the HKLM: and HKCU: drives that are exposed by the Windows PowerShell Registry provider.</span></span>
- <span data-ttu-id="26cb1-115">Sitzungs spezifische temporäre Laufwerke und permanente zugeordnete Netzwerklaufwerke, die Sie mit dem Cmdlet "New-PSDrive" erstellen.</span><span class="sxs-lookup"><span data-stu-id="26cb1-115">Session-specified temporary drives and persistent mapped network drives that you create by using the New-PSDrive cmdlet.</span></span>

<span data-ttu-id="26cb1-116">Ab Windows PowerShell 3,0 können mit dem **Persistenzparameter** des `New-PSDrive` Cmdlets zugeordnete Netzwerklaufwerke erstellt werden, die auf dem lokalen Computer gespeichert sind und in anderen Sitzungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="26cb1-116">Beginning in Windows PowerShell 3.0, the **Persist** parameter of the `New-PSDrive` cmdlet can create mapped network drives that are saved on the local computer and are available in other sessions.</span></span> <span data-ttu-id="26cb1-117">Weitere Informationen finden Sie unter New-PSDrive.</span><span class="sxs-lookup"><span data-stu-id="26cb1-117">For more information, see New-PSDrive.</span></span>

<span data-ttu-id="26cb1-118">Ab Windows PowerShell 3.0 wird beim Herstellen einer Verbindung zwischen einem externen Laufwerk und dem Computer außerdem von Windows PowerShell automatisch ein PowerShell-Laufwerk (PSDrive) zum Dateisystem hinzugefügt, das das neue Laufwerk darstellt.</span><span class="sxs-lookup"><span data-stu-id="26cb1-118">Also, beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, Windows PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="26cb1-119">Windows PowerShell muss nicht neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-119">You do not need to restart Windows PowerShell.</span></span> <span data-ttu-id="26cb1-120">Ebenso wird beim Trennen der Verbindung zwischen einem externen Laufwerk und dem Computer das PSDrive, das das entfernte Laufwerk darstellt, von Windows PowerShell automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="26cb1-120">Similarly, when an external drive is disconnected from the computer, Windows PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="26cb1-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="26cb1-121">EXAMPLES</span></span>

### <span data-ttu-id="26cb1-122">Beispiel 1: erhalten von Laufwerken in der aktuellen Sitzung</span><span class="sxs-lookup"><span data-stu-id="26cb1-122">Example 1: Get drives in the current session</span></span>

```
PS C:\> Get-PSDrive

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
Alias                                  Alias
C                 202.06      23718.91 FileSystem    C:\
Cert                                   Certificate   \
D                1211.06     123642.32 FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
Variable                               Variable
```

<span data-ttu-id="26cb1-123">Dieser Befehl ruft die Laufwerke in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="26cb1-123">This command gets the drives in the current session.</span></span>

<span data-ttu-id="26cb1-124">Die Ausgabe zeigt die Festplatte (C:), CD-ROM-Laufwerk (D:) und die Laufwerke, die von den Windows PowerShell-Anbietern (alias:, CERT:, ENV:, Function:, HKCU:, HKLM: und Variable:) verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-124">The output shows the hard drive (C:), CD-ROM drive (D:), and the drives exposed by the Windows PowerShell providers (Alias:, Cert:, Env:, Function:, HKCU:, HKLM:, and Variable:).</span></span>

### <span data-ttu-id="26cb1-125">Beispiel 2: erhalten eines Laufwerks auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="26cb1-125">Example 2: Get a drive on the computer</span></span>

```
PS C:\foo> Get-PSDrive D

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
D                1211.06     123642.32 FileSystem    D:\
```

<span data-ttu-id="26cb1-126">Mit diesem Befehl wird das Laufwerk %%amp;quot;D:%%amp;quot; auf dem Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="26cb1-126">This command gets the D: drive on the computer.</span></span> <span data-ttu-id="26cb1-127">Achten Sie darauf, dass im Befehl nach dem Laufwerkbuchstaben kein Doppelpunkt folgt.</span><span class="sxs-lookup"><span data-stu-id="26cb1-127">Note that the drive letter in the command is not followed by a colon.</span></span>

### <span data-ttu-id="26cb1-128">Beispiel 3: erhalten Sie alle Laufwerke, die vom Windows PowerShell-Dateisystem Anbieter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-128">Example 3: Get all the drives that are supported by the Windows PowerShell file system provider</span></span>

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
```

<span data-ttu-id="26cb1-129">Dieser Befehl ruft alle Laufwerke ab, die vom Windows PowerShell-FileSystem-Anbieter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-129">This command gets all of the drives that are supported by the Windows PowerShell FileSystem provider.</span></span> <span data-ttu-id="26cb1-130">Dies schließt Festplattenlaufwerke, logische Partitionen, zugeordnete Netzlaufwerke und temporäre Laufwerke ein, die Sie mit dem Cmdlet "New-PSDrive" erstellen.</span><span class="sxs-lookup"><span data-stu-id="26cb1-130">This includes fixed drives, logical partitions, mapped network drives, and temporary drives that you create by using the New-PSDrive cmdlet.</span></span>

### <span data-ttu-id="26cb1-131">Beispiel 4: überprüfen, ob ein Laufwerk als Windows PowerShell-Laufwerk Name verwendet wird</span><span class="sxs-lookup"><span data-stu-id="26cb1-131">Example 4: Check to see if a drive is in use as a Windows PowerShell drive name</span></span>

```powershell
if (Get-PSDrive X -ErrorAction SilentlyContinue) {
    Write-Host 'The X: drive is already in use.'
} else {
    New-PSDrive -Name X -PSProvider Registry -Root HKLM:\SOFTWARE
}
```

<span data-ttu-id="26cb1-132">Dieser Befehl überprüft, ob das Laufwerk %%amp;quot;X%%amp;quot; bereits als Windows PowerShell-Laufwerkname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="26cb1-132">This command checks to see whether the X drive is already in use as a Windows PowerShell drive name.</span></span>
<span data-ttu-id="26cb1-133">Wenn dies nicht der Fall ist, verwendet der Befehl das `New-PSDrive` Cmdlet, um ein temporäres Laufwerk zu erstellen, das dem Registrierungsschlüssel "HKLM: \ Software" zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="26cb1-133">If it is not, the command uses the `New-PSDrive` cmdlet to create a temporary drive that is mapped to the HKLM:\SOFTWARE registry key.</span></span>

### <span data-ttu-id="26cb1-134">Beispiel 5: Vergleichen der System Laufwerkstypen</span><span class="sxs-lookup"><span data-stu-id="26cb1-134">Example 5: Compare the types of files system drives</span></span>

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
X                                      Registry      HKLM:\Network

PS C:\> net use
New connections will be remembered.
Status       Local     Remote                    Network
-------------------------------------------------------------------------------
OK           G:        \\Server01\Public         Microsoft Windows Network

PS C:\> [System.IO.DriveInfo]::GetDrives() | Format-Table
Name DriveType DriveFormat IsReady AvailableFreeSpace TotalFreeSpace TotalSize     RootDirectory VolumeLabel
---- --------- ----------- ------- ------------------ -------------- ---------     ------------- -----------
A:\    Network               False                                                 A:\
C:\      Fixed NTFS          True  771920580608       771920580608   988877418496  C:\           Windows
D:\      Fixed NTFS          True  689684144128       689684144128   1990045179904 D:\           Big Drive
E:\      CDRom               False                                                 E:\
G:\    Network NTFS          True      69120000           69120000       104853504 G:\           GratefulDead

PS N:\> Get-CimInstance -Class Win32_LogicalDisk

DeviceID DriveType ProviderName   VolumeName         Size          FreeSpace
-------- --------- ------------   ----------         ----          ---------
A:       4
C:       3                        Windows            988877418496  771926069248
D:       3                        Big!              1990045179904  689684144128
E:       5
G:       4         \\Music\GratefulDead              988877418496  771926069248


PS C:\> Get-CimInstance -Class Win32_NetworkConnection
LocalName RemoteName            ConnectionState Status
--------- ----------            --------------- ------
G:        \\Music\GratefulDead  Connected       OK
```

<span data-ttu-id="26cb1-135">In diesem Beispiel werden die Typen von Dateisystem Laufwerken, die von angezeigt werden, mit denen verglichen, die `Get-PSDrive` mithilfe anderer Methoden angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-135">This example compares the types of file system drives that are displayed by `Get-PSDrive` to those displayed by using other methods.</span></span> <span data-ttu-id="26cb1-136">Dieses Beispiel zeigt verschiedene Möglichkeiten zum Anzeigen von Laufwerken in Windows PowerShell und zeigt, dass Sitzungs spezifische Laufwerke, die mit dem Cmdlet "New-PSDrive" erstellt werden, nur in Windows PowerShell verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="26cb1-136">This example demonstrates different ways to display drives in Windows PowerShell, and it shows that session-specific drives created by using the New-PSDrive cmdlet are accessible only in Windows PowerShell.</span></span>

<span data-ttu-id="26cb1-137">Der erste Befehl verwendet `Get-PSDrive` , um alle Dateisystem Laufwerke in der Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="26cb1-137">The first command uses `Get-PSDrive` to get all of the file system drives in the session.</span></span> <span data-ttu-id="26cb1-138">Dies umfasst die Festplattenlaufwerke (C: und D:), ein zugeordnetes Netzwerklaufwerk (G:). das mit dem **Persistenzparameter** von `New-PSDrive` und einem PowerShell-Laufwerk (T:) erstellt wurde. der mit erstellt wurde, `New-PSDrive` ohne den **Persistenzparameter** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-138">This includes the fixed drives (C: and D:), a mapped network drive (G:) that was created by using the **Persist** parameter of `New-PSDrive`, and a PowerShell drive (T:) that was created by using `New-PSDrive` without the **Persist** parameter.</span></span>

<span data-ttu-id="26cb1-139">Der Befehl **net use** zeigt zugeordnete Windows-Netzlaufwerke an, in diesem Fall wird nur das Laufwerk G angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26cb1-139">The **net use** command displays Windows mapped network drives, in this case it displays only the G drive.</span></span> <span data-ttu-id="26cb1-140">Das X:-Laufwerk, das von erstellt wurde, wird nicht angezeigt `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="26cb1-140">It does not display the X: drive that was created by `New-PSDrive`.</span></span> <span data-ttu-id="26cb1-141">Es zeigt, dass das Laufwerk G: ebenfalls \\ \\ Music \\ gratefuldead zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="26cb1-141">It shows that the G: drive is also mapped to \\\\Music\\GratefulDead.</span></span>

<span data-ttu-id="26cb1-142">Der dritte Befehl verwendet die **GetDrives** -Methode der **System.IO.DriveInfo** -Klasse von Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="26cb1-142">The third command uses the **GetDrives** method of the Microsoft .NET Framework **System.IO.DriveInfo** class.</span></span> <span data-ttu-id="26cb1-143">Mit diesem Befehl werden die Windows-Dateisystem Laufwerke (einschließlich Laufwerk G:) abgerufen, die von erstellten Laufwerke werden jedoch nicht abgerufen `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="26cb1-143">This command gets the Windows file system drives, including drive G:, but it does not get the drives created by `New-PSDrive`.</span></span>

<span data-ttu-id="26cb1-144">Im vierten Befehl werden mit dem Cmdlet `Get-CimInstance` die Instanzen der Klasse **Win32_LogicalDisk** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="26cb1-144">The fourth command uses the `Get-CimInstance` cmdlet to get the instances of the **Win32_LogicalDisk** class.</span></span> <span data-ttu-id="26cb1-145">Sie gibt die Laufwerke A:, C:, D:, E: und G: zurück, jedoch nicht die von erstellten Laufwerke `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="26cb1-145">It returns the A:, C:, D:, E:, and G: drives, but not the drives created by `New-PSDrive`.</span></span>

<span data-ttu-id="26cb1-146">Im letzten Befehl werden mit dem Cmdlet `Get-CimInstance` die Instanzen der Klasse **Win32_NetworkConnection** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26cb1-146">The last command uses the `Get-CimInstance` cmdlet to display the instances of the **Win32_NetworkConnection** class.</span></span> <span data-ttu-id="26cb1-147">Wie bei **net use** wird nur das permanente Laufwerk G: zurückgegeben, das von erstellt wurde `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="26cb1-147">Like **net use** , it returns only the persistent G: drive created by `New-PSDrive`.</span></span>

## <span data-ttu-id="26cb1-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="26cb1-148">PARAMETERS</span></span>

### <span data-ttu-id="26cb1-149">-LiteralName</span><span class="sxs-lookup"><span data-stu-id="26cb1-149">-LiteralName</span></span>

<span data-ttu-id="26cb1-150">Gibt den Namen des Laufwerks an.</span><span class="sxs-lookup"><span data-stu-id="26cb1-150">Specifies the name of the drive.</span></span>

<span data-ttu-id="26cb1-151">Der Wert von **LiteralName** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="26cb1-151">The value of **LiteralName** is used exactly as it is typed.</span></span> <span data-ttu-id="26cb1-152">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="26cb1-152">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="26cb1-153">Wenn der Name Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="26cb1-153">If the name includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="26cb1-154">Einfache Anführungszeichen veranlassen Windows PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="26cb1-154">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="26cb1-155">-Name</span><span class="sxs-lookup"><span data-stu-id="26cb1-155">-Name</span></span>

<span data-ttu-id="26cb1-156">Gibt den Namen oder den Namen der Laufwerke an, die dieses Cmdlet im Vorgang abruft, als Zeichen folgen Array.</span><span class="sxs-lookup"><span data-stu-id="26cb1-156">Specifies, as a string array, the name or name of drives that this cmdlet gets in the operation.</span></span>
<span data-ttu-id="26cb1-157">Geben Sie den Laufwerknamen oder den Buchstaben ohne Doppelpunkt (:) ein.</span><span class="sxs-lookup"><span data-stu-id="26cb1-157">Type the drive name or letter without a colon (:).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="26cb1-158">-Psprovider</span><span class="sxs-lookup"><span data-stu-id="26cb1-158">-PSProvider</span></span>

<span data-ttu-id="26cb1-159">Gibt als Zeichen folgen Array den Windows PowerShell-Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="26cb1-159">Specifies, as a string array, the Windows PowerShell provider.</span></span> <span data-ttu-id="26cb1-160">Dieses Cmdlet ruft nur die Laufwerke ab, die von diesem Anbieter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-160">This cmdlet gets only the drives supported by this provider.</span></span> <span data-ttu-id="26cb1-161">Geben Sie den Namen eines Anbieters ein, z. B. %%amp;quot;FileSystem%%amp;quot;, %%amp;quot;Registry%%amp;quot; oder %%amp;quot;Certificate%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="26cb1-161">Type the name of a provider, such as FileSystem, Registry, or Certificate.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="26cb1-162">-Bereich</span><span class="sxs-lookup"><span data-stu-id="26cb1-162">-Scope</span></span>

<span data-ttu-id="26cb1-163">Gibt den Bereich an, in dem dieses Cmdlet die Laufwerke abruft.</span><span class="sxs-lookup"><span data-stu-id="26cb1-163">Specifies the scope in which this cmdlet gets the drives.</span></span>

<span data-ttu-id="26cb1-164">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="26cb1-164">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="26cb1-165">Global</span><span class="sxs-lookup"><span data-stu-id="26cb1-165">Global</span></span>
- <span data-ttu-id="26cb1-166">Lokal</span><span class="sxs-lookup"><span data-stu-id="26cb1-166">Local</span></span>
- <span data-ttu-id="26cb1-167">Skript</span><span class="sxs-lookup"><span data-stu-id="26cb1-167">Script</span></span>
- <span data-ttu-id="26cb1-168">eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist).</span><span class="sxs-lookup"><span data-stu-id="26cb1-168">a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span> <span data-ttu-id="26cb1-169">Local ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="26cb1-169">"Local" is the default.</span></span>

<span data-ttu-id="26cb1-170">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="26cb1-170">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="26cb1-171">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="26cb1-171">CommonParameters</span></span>

<span data-ttu-id="26cb1-172">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="26cb1-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="26cb1-173">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="26cb1-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="26cb1-174">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="26cb1-174">INPUTS</span></span>

### <span data-ttu-id="26cb1-175">Keine</span><span class="sxs-lookup"><span data-stu-id="26cb1-175">None</span></span>

<span data-ttu-id="26cb1-176">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-176">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="26cb1-177">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="26cb1-177">OUTPUTS</span></span>

### <span data-ttu-id="26cb1-178">System.Management.Automation.PSDrivin FO</span><span class="sxs-lookup"><span data-stu-id="26cb1-178">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="26cb1-179">Dieses Cmdlet gibt Objekte zurück, die die Laufwerke in der Sitzung darstellen.</span><span class="sxs-lookup"><span data-stu-id="26cb1-179">This cmdlet returns objects that represent the drives in the session.</span></span>

## <span data-ttu-id="26cb1-180">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="26cb1-180">NOTES</span></span>

* <span data-ttu-id="26cb1-181">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-181">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="26cb1-182">Führen Sie die verfügbaren Anbieter in Ihrer Sitzung mithilfe des Cmdlets `Get-PSProvider` auf.</span><span class="sxs-lookup"><span data-stu-id="26cb1-182">To list the providers available in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="26cb1-183">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="26cb1-183">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
* <span data-ttu-id="26cb1-184">Zugeordnete Netzwerklaufwerke, die mit dem **Persistenzparameter** des Cmdlets "New-PSDrive" erstellt werden, sind für ein Benutzerkonto spezifisch.</span><span class="sxs-lookup"><span data-stu-id="26cb1-184">Mapped network drives that are created by using the **Persist** parameter of the New-PSDrive cmdlet are specific to a user account.</span></span> <span data-ttu-id="26cb1-185">Zugeordnete Netzwerklaufwerke, die in Sitzungen erstellt werden, die mit der Option "als Administrator ausführen" oder mit den Anmelde Informationen eines anderen Benutzers gestartet werden, sind nicht in Sitzungen sichtbar, die ohne explizite Anmelde Informationen oder mit den Anmelde Informationen des aktuellen Benutzers gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="26cb1-185">Mapped network drives that you create in sessions that are started with the Run as administrator option or with the credentials of another user are not visible in sessions that are started without explicit credentials or with the credentials of the current user.</span></span>

## <span data-ttu-id="26cb1-186">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="26cb1-186">RELATED LINKS</span></span>

[<span data-ttu-id="26cb1-187">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="26cb1-187">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="26cb1-188">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="26cb1-188">Remove-PSDrive</span></span>](Remove-PSDrive.md)

[<span data-ttu-id="26cb1-189">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="26cb1-189">Get-PSProvider</span></span>](Get-PSProvider.md)
