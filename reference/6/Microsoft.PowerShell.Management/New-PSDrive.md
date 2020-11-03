---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-psdrive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSDrive
ms.openlocfilehash: 04346a3bd324b2d7033405546f131d2d56c5a2bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213151"
---
# <span data-ttu-id="375d6-103">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="375d6-103">New-PSDrive</span></span>

## <span data-ttu-id="375d6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="375d6-104">SYNOPSIS</span></span>
<span data-ttu-id="375d6-105">Erstellt temporäre und permanente zugeordnete Netzwerklaufwerke.</span><span class="sxs-lookup"><span data-stu-id="375d6-105">Creates temporary and persistent mapped network drives.</span></span>

## <span data-ttu-id="375d6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="375d6-106">SYNTAX</span></span>

### <span data-ttu-id="375d6-107">Alle</span><span class="sxs-lookup"><span data-stu-id="375d6-107">All</span></span>

```
New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Description <String>]
 [-Scope <String>] [-Persist] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="375d6-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="375d6-108">DESCRIPTION</span></span>

<span data-ttu-id="375d6-109">Mit dem `New-PSDrive` -Cmdlet werden temporäre und persistente Laufwerke erstellt, die einem Speicherort in einem Datenspeicher zugeordnet oder zugeordnet sind, z. b. ein Netzwerklaufwerk, ein Verzeichnis auf dem lokalen Computer oder ein Registrierungsschlüssel, und persistente Windows zugeordnete Netzwerklaufwerke, die einem Dateisystem Speicherort auf einem Remote Computer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="375d6-109">The `New-PSDrive` cmdlet creates temporary and persistent drives that are mapped to or associated with a location in a data store, such as a network drive, a directory on the local computer, or a registry key, and persistent Windows mapped network drives that are associated with a file system location on a remote computer.</span></span>

<span data-ttu-id="375d6-110">Temporäre Laufwerke sind nur in der aktuellen PowerShell-Sitzung und in Sitzungen vorhanden, die Sie in der aktuellen Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="375d6-110">Temporary drives exist only in the current PowerShell session and in sessions that you create in the current session.</span></span> <span data-ttu-id="375d6-111">Sie können einen beliebigen Namen haben, der in PowerShell gültig ist und einer beliebigen lokalen Ressource oder Remote Ressource zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="375d6-111">They can have any name that is valid in PowerShell and can be mapped to any local or remote resource.</span></span> <span data-ttu-id="375d6-112">Sie können temporäre PowerShell-Laufwerke verwenden, um auf Daten im zugeordneten Datenspeicher zuzugreifen, genauso wie bei jedem zugeordneten Netzwerklaufwerk.</span><span class="sxs-lookup"><span data-stu-id="375d6-112">You can use temporary PowerShell drives to access data in the associated data store, just as you would do with any mapped network drive.</span></span> <span data-ttu-id="375d6-113">Sie können Speicherorte in das Laufwerk ändern, indem Sie verwenden `Set-Location` und mithilfe von oder auf den Inhalt des Laufwerks zugreifen `Get-Item` `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="375d6-113">You can change locations into the drive, by using `Set-Location`, and access the contents of the drive by using `Get-Item` or `Get-ChildItem`.</span></span>

<span data-ttu-id="375d6-114">Da temporäre Laufwerke nur PowerShell bekannt sind, können Sie nicht über den Datei-Explorer, Windows-Verwaltungsinstrumentation (WMI), Component Object Model (com), Microsoft .NET Framework oder mit Tools wie z. b. **net use** darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="375d6-114">Because temporary drives are known only to PowerShell, you can't access them by using File Explorer, Windows Management Instrumentation (WMI), Component Object Model (COM), Microsoft .NET Framework, or with tools such as **net use** .</span></span>

<span data-ttu-id="375d6-115">In PowerShell 3,0 wurden die folgenden Features hinzugefügt `New-PSDrive` :</span><span class="sxs-lookup"><span data-stu-id="375d6-115">The following features were added to `New-PSDrive` in PowerShell 3.0:</span></span>

- <span data-ttu-id="375d6-116">Zugeordnete Netzlaufwerke.</span><span class="sxs-lookup"><span data-stu-id="375d6-116">Mapped network drives.</span></span> <span data-ttu-id="375d6-117">Mit dem **Persistenzparameter** von können Sie von Windows zugeordnete `New-PSDrive` Netzwerklaufwerke erstellen.</span><span class="sxs-lookup"><span data-stu-id="375d6-117">You can use the **Persist** parameter of `New-PSDrive` to create Windows mapped network drives.</span></span> <span data-ttu-id="375d6-118">Anders als bei temporären PowerShell-Laufwerken sind zugeordnete Windows-Netzlaufwerke nicht Sitzungs spezifisch.</span><span class="sxs-lookup"><span data-stu-id="375d6-118">Unlike temporary PowerShell drives, Windows mapped network drives aren't session-specific.</span></span> <span data-ttu-id="375d6-119">Sie werden in Windows gespeichert und können mithilfe von Windows-Standard Tools, wie z. b. Datei-Explorer und **net use** , verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="375d6-119">They're saved in Windows and they can be managed by using standard Windows tools, such as File Explorer and **net use** .</span></span> <span data-ttu-id="375d6-120">Zugeordnete Netzwerklaufwerke müssen einen Laufwerkbuchstaben aufweisen und mit einem Remotedateisystem-Speicherort verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="375d6-120">Mapped network drives must have a drive-letter name and be connected to a remote file system location.</span></span> <span data-ttu-id="375d6-121">Wenn Ihr Befehl lokal festgelegt ist, ohne dass der **Persistenzparameter** die Erstellung eines " **PSDrive** " über den Gültigkeitsbereich hinaus speichert, in dem der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="375d6-121">When your command is scoped locally, no dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which the command is running.</span></span> <span data-ttu-id="375d6-122">Wenn Sie `New-PSDrive` innerhalb eines Skripts arbeiten und das Laufwerk unbegrenzt beibehalten werden soll, müssen Sie das Skript als Punkt verwenden.</span><span class="sxs-lookup"><span data-stu-id="375d6-122">If you're running `New-PSDrive` inside a script, and you want the drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="375d6-123">Um optimale Ergebnisse zu erzwingen, fügen Sie dem Befehl den **Scope** -Parameter hinzu, und legen Sie seinen Wert auf **Global** fest, um zu erzwingen, dass ein neues Laufwerk unbegrenzt persistent gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="375d6-123">For best results, to force a new drive to persist indefinitely, add the **Scope** parameter to your command, and set its value to **Global** .</span></span> <span data-ttu-id="375d6-124">Weitere Informationen zur Punkt basierten Beschaffung finden Sie unter [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="375d6-124">For more information about dot-sourcing, see [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span></span>
- <span data-ttu-id="375d6-125">Externe Laufwerke.</span><span class="sxs-lookup"><span data-stu-id="375d6-125">External drives.</span></span> <span data-ttu-id="375d6-126">Wenn ein externes Laufwerk mit dem Computer verbunden ist, wird dem Dateisystem, das das neue Laufwerk darstellt, von PowerShell automatisch ein **PSDrive** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="375d6-126">When an external drive is connected to the computer, PowerShell automatically adds a **PSDrive** to the file system that represents the new drive.</span></span> <span data-ttu-id="375d6-127">PowerShell muss nicht neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="375d6-127">You don't have to restart PowerShell.</span></span> <span data-ttu-id="375d6-128">Ebenso wird beim Trennen eines externen Laufwerks mit dem Computer das **PSDrive** , das das entfernte Laufwerk darstellt, von PowerShell automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="375d6-128">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the **PSDrive** that represents the removed drive.</span></span>
- <span data-ttu-id="375d6-129">Anmelde Informationen für Universal Naming Convention (UNC)-Pfade.</span><span class="sxs-lookup"><span data-stu-id="375d6-129">Credentials for Universal Naming Convention (UNC) paths.</span></span>

<span data-ttu-id="375d6-130">Wenn der Wert des **root** -Parameters ein UNC-Pfad ist (z. b.), `\\Server\Share` werden die im Wert des **Anmelde Informationen** -Parameters angegebenen Anmelde Informationen zum Erstellen des **PSDrive** verwendet.</span><span class="sxs-lookup"><span data-stu-id="375d6-130">When the value of the **Root** parameter is a UNC path, such as `\\Server\Share`, the credential specified in the value of the **Credential** parameter is used to create the **PSDrive** .</span></span> <span data-ttu-id="375d6-131">Andernfalls sind **Anmelde Informationen nicht wirksam** , wenn Sie neue Dateisystem Laufwerke erstellen.</span><span class="sxs-lookup"><span data-stu-id="375d6-131">Otherwise, **Credential** isn't effective when you're creating new file system drives.</span></span>

<span data-ttu-id="375d6-132">Einige Codebeispiele verwenden Verteilung, um die Zeilenlänge zu verringern und die Lesbarkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="375d6-132">Some code samples use splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="375d6-133">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="375d6-133">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="375d6-134">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="375d6-134">EXAMPLES</span></span>

### <span data-ttu-id="375d6-135">Beispiel 1: Erstellen eines temporären Laufwerks, das einer Netzwerkfreigabe zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="375d6-135">Example 1: Create a temporary drive mapped to a network share</span></span>

<span data-ttu-id="375d6-136">In diesem Beispiel wird ein temporäres PowerShell-Laufwerk erstellt, das einer Netzwerkfreigabe zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="375d6-136">This example creates a temporary PowerShell drive that's mapped to a network share.</span></span>

```powershell
New-PSDrive -Name "Public" -PSProvider "FileSystem" -Root "\\Server01\Public"
```

```Output
Name       Provider      Root
----       --------      ----
Public     FileSystem    \\Server01\Public
```

<span data-ttu-id="375d6-137">`New-PSDrive` verwendet den **Name** -Parameter, um das PowerShell `Public` -Laufwerk mit dem Namen und den **psprovider** -Parameter anzugeben, um den PowerShell- `FileSystem` Anbieter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="375d6-137">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `Public` and the **PSProvider** parameter to specify the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="375d6-138">Der **root** -Parameter gibt den UNC-Pfad der Netzwerkfreigabe an.</span><span class="sxs-lookup"><span data-stu-id="375d6-138">The **Root** parameter specifies the network share's UNC path.</span></span>

<span data-ttu-id="375d6-139">So zeigen Sie den Inhalt einer PowerShell-Sitzung an: `Get-ChildItem -Path Public:`</span><span class="sxs-lookup"><span data-stu-id="375d6-139">To view the contents from a PowerShell session: `Get-ChildItem -Path Public:`</span></span>

### <span data-ttu-id="375d6-140">Beispiel 2: Erstellen eines temporären Laufwerks, das einem lokalen Verzeichnis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="375d6-140">Example 2: Create a temporary drive mapped to a local directory</span></span>

<span data-ttu-id="375d6-141">In diesem Beispiel wird ein temporäres PowerShell-Laufwerk erstellt, das Zugriff auf ein Verzeichnis auf dem lokalen Computer bietet.</span><span class="sxs-lookup"><span data-stu-id="375d6-141">This example creates a temporary PowerShell drive that provides access to a directory on the local computer.</span></span>

```powershell
$parameters = @{
    Name = "MyDocs"
    PSProvider = "FileSystem"
    Root = "C:\Users\User01\Documents"
    Description = "Maps to my My Documents folder."
}
New-PSDrive @parameters
```

```Output
Name        Provider      Root
----        --------      ----
MyDocs      FileSystem    C:\Users\User01\Documents
```

<span data-ttu-id="375d6-142">Splatting erstellt die Parameter Schlüssel und-Werte.</span><span class="sxs-lookup"><span data-stu-id="375d6-142">Splatting creates the parameter keys and values.</span></span> <span data-ttu-id="375d6-143">Der **Name** -Parameter gibt den Namen des Laufwerks an, **MyDocs** .</span><span class="sxs-lookup"><span data-stu-id="375d6-143">The **Name** parameter specifies the drive name, **MyDocs** .</span></span> <span data-ttu-id="375d6-144">Der **psprovider** -Parameter gibt den PowerShell- `FileSystem` Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="375d6-144">The **PSProvider** parameter specifies the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="375d6-145">**Root** gibt das Verzeichnis des lokalen Computers an.</span><span class="sxs-lookup"><span data-stu-id="375d6-145">**Root** specifies the local computer's directory.</span></span> <span data-ttu-id="375d6-146">Der **Beschreibungs** Parameter beschreibt den Zweck des Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="375d6-146">The **Description** parameter describes the drive's purpose.</span></span> <span data-ttu-id="375d6-147">`New-PSDrive` verwendet die splatted-Parameter, um das Laufwerk zu erstellen `MyDocs` .</span><span class="sxs-lookup"><span data-stu-id="375d6-147">`New-PSDrive` uses the splatted parameters to create the `MyDocs` drive.</span></span>

<span data-ttu-id="375d6-148">So zeigen Sie den Inhalt einer PowerShell-Sitzung an: `Get-ChildItem -Path MyDocs:`</span><span class="sxs-lookup"><span data-stu-id="375d6-148">To view the contents from a PowerShell session: `Get-ChildItem -Path MyDocs:`</span></span>

### <span data-ttu-id="375d6-149">Beispiel 3: Erstellen eines temporären Laufwerks für einen Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="375d6-149">Example 3: Create a temporary drive for a registry key</span></span>

<span data-ttu-id="375d6-150">In diesem Beispiel wird ein temporäres PowerShell-Laufwerk erstellt, das Zugriff auf einen Registrierungsschlüssel bietet.</span><span class="sxs-lookup"><span data-stu-id="375d6-150">This example creates a temporary PowerShell drive that provides access to a registry key.</span></span> <span data-ttu-id="375d6-151">Es wird ein Laufwerk mit dem Namen MyCompany erstellt, das dem `HKLM:\Software\MyCompany` Registrierungsschlüssel zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="375d6-151">It creates a drive named MyCompany that is mapped to the `HKLM:\Software\MyCompany` registry key.</span></span>

```powershell
New-PSDrive -Name "MyCompany" -PSProvider "Registry" -Root "HKLM:\Software\MyCompany"
```

```Output
Name           Provider      Root
----           --------      ----
MyCompany      Registry      HKLM:\Software\MyCompany
```

<span data-ttu-id="375d6-152">`New-PSDrive` verwendet den **Name** -Parameter, um das PowerShell `MyCompany` -Laufwerk mit dem Namen und den **psprovider** -Parameter anzugeben, um den PowerShell- `Registry` Anbieter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="375d6-152">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `MyCompany` and the **PSProvider** parameter to specify the PowerShell `Registry` provider.</span></span> <span data-ttu-id="375d6-153">Der **root** -Parameter gibt den Registrierungs Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="375d6-153">The **Root** parameter specifies the registry location.</span></span>

<span data-ttu-id="375d6-154">So zeigen Sie den Inhalt einer PowerShell-Sitzung an: `Get-ChildItem -Path MyCompany:`</span><span class="sxs-lookup"><span data-stu-id="375d6-154">To view the contents from a PowerShell session: `Get-ChildItem -Path MyCompany:`</span></span>

### <span data-ttu-id="375d6-155">Beispiel 4: Erstellen eines permanenten zugeordneten Netzwerklaufwerks mithilfe von Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="375d6-155">Example 4: Create a persistent mapped network drive using credentials</span></span>

<span data-ttu-id="375d6-156">In diesem Beispiel wird ein Netzwerklaufwerk zugeordnet, das mit den Anmelde Informationen eines Domänen Dienst Kontos authentifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="375d6-156">This example maps a network drive that's authenticated with a domain service account's credentials.</span></span>
<span data-ttu-id="375d6-157">Weitere Informationen über das **PSCredential** -Objekt, in dem Anmelde Informationen gespeichert werden, und wie Kenn Wörter als **SecureString** gespeichert werden, finden Sie in der Beschreibung des Parameters " **Credential** ".</span><span class="sxs-lookup"><span data-stu-id="375d6-157">For more information about the **PSCredential** object that stores credentials and how passwords are stored as a **SecureString** , see the **Credential** parameter's description.</span></span>

```powershell
$cred = Get-Credential -Credential Contoso\ServiceAccount
New-PSDrive -Name "S" -Root "\\Server01\Scripts" -Persist -PSProvider "FileSystem" -Credential $cred
Net Use
```

```Output
Status       Local     Remote                    Network
---------------------------------------------------------
OK           S:        \\Server01\Scripts        Microsoft Windows Network
```

> [!NOTE]
> <span data-ttu-id="375d6-158">Wenn Sie den obigen Code Ausschnitt in einem Skript verwenden, legen Sie den Wert des **Bereichs** Parameters auf "Global" fest, um sicherzustellen, dass das Laufwerk außerhalb des aktuellen Bereichs beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="375d6-158">Remember, if you use the above snippet in a script, set the **Scope** parameter value to "Global" to ensure the drive persists outside the current scope.</span></span>

<span data-ttu-id="375d6-159">Die `$cred` Variable speichert ein **PSCredential** -Objekt, das die Anmelde Informationen des Dienst Kontos enthält.</span><span class="sxs-lookup"><span data-stu-id="375d6-159">The `$cred` variable stores a **PSCredential** object that contains the service account's credentials.</span></span> <span data-ttu-id="375d6-160">`Get-Credential` Sie werden aufgefordert, das Kennwort einzugeben, das in einer **SecureString** gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="375d6-160">`Get-Credential` prompts you to enter the password that's stored in a **SecureString** .</span></span>

<span data-ttu-id="375d6-161">`New-PSDrive` erstellt das zugeordnete Netzwerklaufwerk mithilfe mehrerer Parameter.</span><span class="sxs-lookup"><span data-stu-id="375d6-161">`New-PSDrive` creates the mapped network drive by using several parameters.</span></span> <span data-ttu-id="375d6-162">**Name** gibt den `S` Laufwerk Buchstaben an, den Windows akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="375d6-162">**Name** specifies the `S` drive letter that Windows accepts.</span></span> <span data-ttu-id="375d6-163">und **root** definiert `\\Server01\Scripts` als Speicherort auf einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="375d6-163">and **Root** defines `\\Server01\Scripts` as the location on a remote computer.</span></span> <span data-ttu-id="375d6-164">**Persistenz erstellt ein** zugeordnetes Windows-Netzwerklaufwerk, das auf dem lokalen Computer gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="375d6-164">**Persist** creates a Windows mapped network drive that's saved on the local computer.</span></span> <span data-ttu-id="375d6-165">**Psprovider** gibt den `FileSystem` Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="375d6-165">**PSProvider** specifies the `FileSystem` provider.</span></span> <span data-ttu-id="375d6-166">Anmelde **Informationen verwenden die** - `$cred` Variable, um die Anmelde Informationen des Dienst Kontos für die Authentifizierung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="375d6-166">**Credential** uses the `$cred` variable to get the service account credentials for authentication.</span></span>

<span data-ttu-id="375d6-167">Das zugeordnete Laufwerk kann auf dem lokalen Computer in PowerShell-Sitzungen, im Datei-Explorer und mit Tools wie z. b. **net use** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="375d6-167">The mapped drive can be viewed on the local computer in PowerShell sessions, File Explorer, and with tools such as **net use** .</span></span> <span data-ttu-id="375d6-168">So zeigen Sie den Inhalt einer PowerShell-Sitzung an: `Get-ChildItem -Path S:`</span><span class="sxs-lookup"><span data-stu-id="375d6-168">To view the contents from a PowerShell session: `Get-ChildItem -Path S:`</span></span>

### <span data-ttu-id="375d6-169">Beispiel 5: Erstellen von persistenten und temporären Laufwerken</span><span class="sxs-lookup"><span data-stu-id="375d6-169">Example 5: Create persistent and temporary drives</span></span>

<span data-ttu-id="375d6-170">Dieses Beispiel zeigt den Unterschied zwischen einem permanenten zugeordneten Netzwerklaufwerk und einem temporären PowerShell-Laufwerk, das derselben Netzwerkfreigabe zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="375d6-170">This example shows the difference between a persistent mapped network drive and a temporary PowerShell drive that is mapped to the same network share.</span></span>

<span data-ttu-id="375d6-171">Wenn Sie die PowerShell-Sitzung schließen und dann eine neue Sitzung öffnen, ist die temporäre `PSDrive:` nicht verfügbar, aber das persistente `X:` Laufwerk ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="375d6-171">If you close the PowerShell session and then open a new session, the temporary `PSDrive:` isn't available, but the persistent `X:` drive is available.</span></span> <span data-ttu-id="375d6-172">Berücksichtigen Sie bei der Entscheidung, welche Methode zum Zuordnen von Netzlaufwerken verwendet werden soll, die Verwendung des Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="375d6-172">When deciding which method to use to map network drives, consider how you'll use the drive.</span></span> <span data-ttu-id="375d6-173">Beispielsweise, ob es persistent sein muss und ob das Laufwerk für andere Windows-Features sichtbar sein muss.</span><span class="sxs-lookup"><span data-stu-id="375d6-173">For example, whether it has to be persistent, and whether the drive has to be visible to other Windows features.</span></span>

```powershell
# Create a temporary PowerShell drive called PSDrive:
# that's mapped to the \\Server01\Public network share.
New-PSDrive -Name "PSDrive" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Use the Persist parameter of New-PSDrive to create the X: mapped network drive,
# which is also mapped to the \\Server01\Public network share.
New-PSDrive -Persist -Name "X" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Now, you can use the Get-PSDrive drive cmdlet to examine the two drives.
# The drives appear to be the same, although the network share name appears only
# in the root of the PSDrive: drive.
Get-PSDrive -Name "PSDrive", "X"
```

```Output
Name       Provider      Root
----       --------      ----

PsDrive    FileSystem    \\Server01\public
X          FileSystem    X:\
```

```powershell
# Get-Member cmdlet shows that the drives have the same object type,
# System.Management.Automation.PSDriveInfo.
Get-PSDrive "PSDrive", "x" | Get-Member
```

```Output
TypeName: System.Management.Automation.PSDriveInfo

Name                MemberType   Definition
----                ----------   ----------
CompareTo           Method       System.Int32 CompareTo(PSDriveInfo drive),
Equals              Method       System.Boolean Equals(Object obj),
GetHashCode         Method       System.Int32 GetHashCode()
...
```

```powershell
# Net Use and Get-CimInstance for the Win32_LogicalDisk class,
# and Win32_NetworkConnection class find only the persistent X: drive.
# PowerShell temporary drives are known only to PowerShell.
Net Use
Get-CimInstance Win32_LogicalDisk | Format-Table -Property DeviceID
Get-CimInstance Win32_NetworkConnection
```

```Output
Status       Local     Remote                    Network
--------------------------------------------------------
OK           X:        \\contoso-pc\data         Microsoft Windows Network

deviceid
--------
C:
D:
X:

LocalName    RemoteName              ConnectionState          Status
---------    ----------              ---------------          ------
X:           \\products\public       Disconnected             Unavailable
```

## <span data-ttu-id="375d6-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="375d6-174">PARAMETERS</span></span>

### <span data-ttu-id="375d6-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="375d6-175">-Confirm</span></span>

<span data-ttu-id="375d6-176">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="375d6-176">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="375d6-177">-Credential</span><span class="sxs-lookup"><span data-stu-id="375d6-177">-Credential</span></span>

<span data-ttu-id="375d6-178">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="375d6-178">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="375d6-179">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="375d6-179">The default is the current user.</span></span>

<span data-ttu-id="375d6-180">Da PowerShell 3,0, wenn der Wert des **root** -Parameters ein UNC-Pfad ist, können Sie Anmelde Informationen zum Erstellen von Dateisystem Laufwerken verwenden.</span><span class="sxs-lookup"><span data-stu-id="375d6-180">Since PowerShell 3.0, when the value of the **Root** parameter is a UNC path, you can use credentials to create file system drives.</span></span>

<span data-ttu-id="375d6-181">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="375d6-181">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="375d6-182">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="375d6-182">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="375d6-183">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="375d6-183">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="375d6-184">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="375d6-184">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="375d6-185">-Description</span><span class="sxs-lookup"><span data-stu-id="375d6-185">-Description</span></span>

<span data-ttu-id="375d6-186">Gibt eine kurze Textbeschreibung des Laufwerks an.</span><span class="sxs-lookup"><span data-stu-id="375d6-186">Specifies a brief text description of the drive.</span></span> <span data-ttu-id="375d6-187">Geben Sie eine beliebige Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="375d6-187">Type any string.</span></span>

<span data-ttu-id="375d6-188">, Um die Beschreibungen aller Laufwerke der Sitzung anzuzeigen `Get-PSDrive | Format-Table Name, Description` .</span><span class="sxs-lookup"><span data-stu-id="375d6-188">To see the descriptions of all the session's drives, `Get-PSDrive | Format-Table Name, Description`.</span></span>

<span data-ttu-id="375d6-189">Wenn Sie die Beschreibung eines bestimmten Laufwerks anzeigen möchten, geben Sie ein `(Get-PSDrive <DriveName>).Description` .</span><span class="sxs-lookup"><span data-stu-id="375d6-189">To see the description of a particular drive, type `(Get-PSDrive <DriveName>).Description`.</span></span>

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

### <span data-ttu-id="375d6-190">-Name</span><span class="sxs-lookup"><span data-stu-id="375d6-190">-Name</span></span>

<span data-ttu-id="375d6-191">Gibt einen Namen für das neue Laufwerk an.</span><span class="sxs-lookup"><span data-stu-id="375d6-191">Specifies a name for the new drive.</span></span> <span data-ttu-id="375d6-192">Verwenden Sie für persistente zugeordnete Netzwerklaufwerke einen Laufwerk Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="375d6-192">For persistent mapped network drives, use a drive letter.</span></span> <span data-ttu-id="375d6-193">Bei temporären PowerShell-Laufwerken sind Sie nicht auf Laufwerk Buchstaben beschränkt. verwenden Sie eine beliebige gültige Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="375d6-193">For temporary PowerShell drives, you aren't limited to drive letters, use any valid string.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="375d6-194">-Persistent speichern</span><span class="sxs-lookup"><span data-stu-id="375d6-194">-Persist</span></span>

<span data-ttu-id="375d6-195">Gibt an, dass dieses Cmdlet ein zugeordnetes Windows-Netzwerklaufwerk erstellt.</span><span class="sxs-lookup"><span data-stu-id="375d6-195">Indicates that this cmdlet creates a Windows mapped network drive.</span></span> <span data-ttu-id="375d6-196">Der **Persistenzparameter** ist nur unter Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="375d6-196">The **Persist** parameter is only available on Windows.</span></span>

<span data-ttu-id="375d6-197">Zugeordnete Netzwerklaufwerke werden unter Windows auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="375d6-197">Mapped network drives are saved in Windows on the local computer.</span></span> <span data-ttu-id="375d6-198">Sie sind permanent, nicht Sitzungs spezifisch und können im Datei-Explorer und anderen Tools angezeigt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="375d6-198">They're persistent, not session-specific, and can be viewed and managed in File Explorer and other tools.</span></span>

<span data-ttu-id="375d6-199">Wenn Sie den Befehl ohne Punkt-Beschaffung lokal festlegen, behält der **Persistenzparameter** die Erstellung eines **PSDrive** nicht bei, der über den Bereich hinausgeht, in dem Sie den Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="375d6-199">When you scope the command locally, without dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which you run the command.</span></span> <span data-ttu-id="375d6-200">Wenn Sie `New-PSDrive` in einem Skript ausführen und das neue Laufwerk unbegrenzt beibehalten werden soll, müssen Sie das Skript mit einer Punktquelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="375d6-200">If you run `New-PSDrive` inside a script, and you want the new drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="375d6-201">Um die besten Ergebnisse zu erzwingen, geben Sie **Global** als Wert für den **Scope** -Parameter **und include in** Ihren Befehl ein, um die Beibehaltung eines neuen Laufwerks zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="375d6-201">For best results, to force a new drive to persist, specify **Global** as the value of the **Scope** parameter and include **Persist** in your command.</span></span>

<span data-ttu-id="375d6-202">Der Name des Laufwerks muss ein Buchstabe sein, z `D` . b `E` . oder.</span><span class="sxs-lookup"><span data-stu-id="375d6-202">The name of the drive must be a letter, such as `D` or `E`.</span></span> <span data-ttu-id="375d6-203">Der Wert des **root** -Parameters muss ein UNC-Pfad eines anderen Computers sein.</span><span class="sxs-lookup"><span data-stu-id="375d6-203">The value of **Root** parameter must be a UNC path of a different computer.</span></span> <span data-ttu-id="375d6-204">Der Wert des **psprovider** -Parameters muss lauten `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="375d6-204">The **PSProvider** parameter's value must be `FileSystem`.</span></span>

<span data-ttu-id="375d6-205">Verwenden Sie zum Trennen einer Verbindung mit einem zugeordneten Windows-Netzwerklaufwerk das Cmdlet `Remove-PSDrive`.</span><span class="sxs-lookup"><span data-stu-id="375d6-205">To disconnect a Windows mapped network drive, use the `Remove-PSDrive` cmdlet.</span></span> <span data-ttu-id="375d6-206">Wenn Sie die Verbindung mit einem zugeordneten Windows-Netzwerklaufwerk trennen, wird die Zuordnung dauerhaft vom Computer gelöscht, nicht nur aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="375d6-206">When you disconnect a Windows mapped network drive, the mapping is permanently deleted from the computer, not just deleted from the current session.</span></span>

<span data-ttu-id="375d6-207">Zugeordnete Netzwerklaufwerke sind bestimmten Benutzerkonten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="375d6-207">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="375d6-208">Zugeordnete Laufwerke, die mit den Anmelde Informationen eines anderen Benutzers in erweiterten Sitzungen oder Sitzungen erstellt wurden, sind in Sitzungen, die mit unterschiedlichen Anmelde Informationen gestartet wurden,</span><span class="sxs-lookup"><span data-stu-id="375d6-208">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="375d6-209">-Psprovider</span><span class="sxs-lookup"><span data-stu-id="375d6-209">-PSProvider</span></span>

<span data-ttu-id="375d6-210">Gibt den PowerShell-Anbieter an, der Laufwerke dieser Art unterstützt.</span><span class="sxs-lookup"><span data-stu-id="375d6-210">Specifies the PowerShell provider that supports drives of this kind.</span></span>

<span data-ttu-id="375d6-211">Wenn das Laufwerk z. b. einer Netzwerkfreigabe oder einem Dateisystem Verzeichnis zugeordnet ist, ist der PowerShell-Anbieter `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="375d6-211">For example, if the drive is associated with a network share or file system directory, the PowerShell provider is `FileSystem`.</span></span> <span data-ttu-id="375d6-212">Wenn das Laufwerk einem Registrierungsschlüssel zugeordnet ist, ist der Anbieter `Registry` .</span><span class="sxs-lookup"><span data-stu-id="375d6-212">If the drive is associated with a registry key, the provider is `Registry`.</span></span>

<span data-ttu-id="375d6-213">Temporäre PowerShell-Laufwerke können einem beliebigen PowerShell-Anbieter zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="375d6-213">Temporary PowerShell drives can be associated with any PowerShell provider.</span></span> <span data-ttu-id="375d6-214">Zugeordnete Netzwerklaufwerke können nur dem Anbieter zugeordnet werden `FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="375d6-214">Mapped network drives can be associated only with the `FileSystem` provider.</span></span>

<span data-ttu-id="375d6-215">Verwenden Sie das-Cmdlet, um eine Liste der Anbieter in ihrer PowerShell-Sitzung anzuzeigen `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="375d6-215">To see a list of the providers in your PowerShell session, use the `Get-PSProvider` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="375d6-216">-Root</span><span class="sxs-lookup"><span data-stu-id="375d6-216">-Root</span></span>

<span data-ttu-id="375d6-217">Gibt den Speicherort des Datenspeicher Orts an, dem ein PowerShell-Laufwerk zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="375d6-217">Specifies the data store location to which a PowerShell drive is mapped.</span></span>

<span data-ttu-id="375d6-218">Geben Sie z. b. eine Netzwerkfreigabe an, z `\\Server01\Public` . b. ein lokales Verzeichnis, z `C:\Program Files` . b. oder einen Registrierungsschlüssel, z `HKLM:\Software\Microsoft` . b..</span><span class="sxs-lookup"><span data-stu-id="375d6-218">For example, specify a network share, such as `\\Server01\Public`, a local directory, such as `C:\Program Files`, or a registry key, such as `HKLM:\Software\Microsoft`.</span></span>

<span data-ttu-id="375d6-219">Temporäre PowerShell-Laufwerke können einem lokalen Speicherort oder einem Remote Speicherort auf einem beliebigen unterstützten Anbieter Laufwerk zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="375d6-219">Temporary PowerShell drives can be associated with a local or remote location on any supported provider drive.</span></span> <span data-ttu-id="375d6-220">Zugeordnete Netzwerklaufwerke können nur einem Dateisystemspeicherort auf einem Remotecomputer zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="375d6-220">Mapped network drives can be associated only with a file system location on a remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="375d6-221">-Bereich</span><span class="sxs-lookup"><span data-stu-id="375d6-221">-Scope</span></span>

<span data-ttu-id="375d6-222">Gibt einen Bereich für das Laufwerk an.</span><span class="sxs-lookup"><span data-stu-id="375d6-222">Specifies a scope for the drive.</span></span> <span data-ttu-id="375d6-223">Die zulässigen Werte für diesen Parameter lauten: **Global** , **local** und **Script** oder eine Zahl relativ zum aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="375d6-223">The acceptable values for this parameter are: **Global** , **Local** , and **Script** , or a number relative to the current scope.</span></span> <span data-ttu-id="375d6-224">Bereiche mit der Zahl 0 bis zur Anzahl der Bereiche.</span><span class="sxs-lookup"><span data-stu-id="375d6-224">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="375d6-225">Die aktuelle Bereichs Nummer ist 0 und das übergeordnete Element ist 1.</span><span class="sxs-lookup"><span data-stu-id="375d6-225">The current scope number is 0 and its parent is 1.</span></span> <span data-ttu-id="375d6-226">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="375d6-226">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="375d6-227">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="375d6-227">-WhatIf</span></span>

<span data-ttu-id="375d6-228">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="375d6-228">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="375d6-229">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="375d6-229">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="375d6-230">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="375d6-230">CommonParameters</span></span>

<span data-ttu-id="375d6-231">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="375d6-231">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="375d6-232">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="375d6-232">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="375d6-233">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="375d6-233">INPUTS</span></span>

### <span data-ttu-id="375d6-234">Keine</span><span class="sxs-lookup"><span data-stu-id="375d6-234">None</span></span>

<span data-ttu-id="375d6-235">Sie können keine Eingabe für dieses Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="375d6-235">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="375d6-236">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="375d6-236">OUTPUTS</span></span>

### <span data-ttu-id="375d6-237">System.Management.Automation.PSDrivin FO</span><span class="sxs-lookup"><span data-stu-id="375d6-237">System.Management.Automation.PSDriveInfo</span></span>

## <span data-ttu-id="375d6-238">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="375d6-238">NOTES</span></span>

<span data-ttu-id="375d6-239">`New-PSDrive` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="375d6-239">`New-PSDrive` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="375d6-240">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, verwenden Sie `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="375d6-240">To list the providers available in your session, use `Get-PSProvider`.</span></span> <span data-ttu-id="375d6-241">Weitere Informationen zu Anbietern finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="375d6-241">For more information about providers, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="375d6-242">Zugeordnete Netzwerklaufwerke sind bestimmten Benutzerkonten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="375d6-242">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="375d6-243">Zugeordnete Laufwerke, die mit den Anmelde Informationen eines anderen Benutzers in erweiterten Sitzungen oder Sitzungen erstellt wurden, sind in Sitzungen, die mit unterschiedlichen Anmelde Informationen gestartet wurden,</span><span class="sxs-lookup"><span data-stu-id="375d6-243">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

## <span data-ttu-id="375d6-244">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="375d6-244">RELATED LINKS</span></span>

[<span data-ttu-id="375d6-245">about_Providers</span><span class="sxs-lookup"><span data-stu-id="375d6-245">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="375d6-246">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="375d6-246">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="375d6-247">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="375d6-247">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="375d6-248">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="375d6-248">Remove-PSDrive</span></span>](Remove-PSDrive.md)
