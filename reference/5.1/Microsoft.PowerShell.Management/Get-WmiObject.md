---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmiObject
ms.openlocfilehash: ed759ff3d0dd35cd55f9dac5a2d76e36eac4dc6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215391"
---
# <span data-ttu-id="da442-103">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="da442-103">Get-WmiObject</span></span>

## <span data-ttu-id="da442-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="da442-104">SYNOPSIS</span></span>
<span data-ttu-id="da442-105">Ruft Instanzen von Klassen der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) oder Informationen zu den verfügbaren Klassen ab.</span><span class="sxs-lookup"><span data-stu-id="da442-105">Gets instances of Windows Management Instrumentation (WMI) classes or information about the available classes.</span></span>

## <span data-ttu-id="da442-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="da442-106">SYNTAX</span></span>

### <span data-ttu-id="da442-107">Abfrage (Standard)</span><span class="sxs-lookup"><span data-stu-id="da442-107">query (Default)</span></span>

```
Get-WmiObject [-Class] <String> [[-Property] <String[]>] [-Filter <String>] [-Amended] [-DirectRead]
 [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="da442-108">list</span><span class="sxs-lookup"><span data-stu-id="da442-108">list</span></span>

```
Get-WmiObject [[-Class] <String>] [-Recurse] [-Amended] [-List] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="da442-109">Wqlquery</span><span class="sxs-lookup"><span data-stu-id="da442-109">WQLQuery</span></span>

```
Get-WmiObject [-Amended] [-DirectRead] -Query <String> [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="da442-110">class</span><span class="sxs-lookup"><span data-stu-id="da442-110">class</span></span>

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="da442-111">path</span><span class="sxs-lookup"><span data-stu-id="da442-111">path</span></span>

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

## <span data-ttu-id="da442-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="da442-112">DESCRIPTION</span></span>

<span data-ttu-id="da442-113">Ab PowerShell 3,0 wurde dieses Cmdlet durch ersetzt `Get-CimInstance` .</span><span class="sxs-lookup"><span data-stu-id="da442-113">Starting in PowerShell 3.0, this cmdlet has been superseded by `Get-CimInstance`.</span></span>

<span data-ttu-id="da442-114">Mit dem- `Get-WmiObject` Cmdlet werden Instanzen von WMI-Klassen oder Informationen zu den verfügbaren WMI-Klassen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="da442-114">The `Get-WmiObject` cmdlet gets instances of WMI classes or information about the available WMI classes.</span></span> <span data-ttu-id="da442-115">Geben Sie einen Remotecomputer mit dem **ComputerName** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="da442-115">To specify a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="da442-116">Wenn der **List** -Parameter angegeben wird, ruft das Cmdlet Informationen zu den WMI-Klassen ab, die in einem angegebenen Namespace verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="da442-116">If the **List** parameter is specified, the cmdlet gets information about the WMI classes that are available in a specified namespace.</span></span> <span data-ttu-id="da442-117">Wenn der **Query** -Parameter angegeben ist, wird vom Cmdlet eine WQL (WMI Query Language)-Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="da442-117">If the **Query** parameter is specified, the cmdlet runs a WMI query language (WQL) statement.</span></span>

<span data-ttu-id="da442-118">Das `Get-WmiObject` Cmdlet verwendet Windows PowerShell-Remoting nicht zum Ausführen von Remote Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="da442-118">The `Get-WmiObject` cmdlet does not use Windows PowerShell remoting to perform remote operations.</span></span>
<span data-ttu-id="da442-119">Sie können den **Computername** -Parameter des `Get-WmiObject` Cmdlets auch dann verwenden, wenn der Computer die Anforderungen für Windows PowerShell-Remoting nicht erfüllt oder nicht für das Remoting in Windows PowerShell konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="da442-119">You can use the **ComputerName** parameter of the `Get-WmiObject` cmdlet even if your computer does not meet the requirements for Windows PowerShell remoting or is not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="da442-120">Ab Windows PowerShell 3,0 hat die **__Server** -Eigenschaft des-Objekts, das `Get-WmiObject` zurückgibt, einen **pscomputername** -Alias.</span><span class="sxs-lookup"><span data-stu-id="da442-120">Beginning in Windows PowerShell 3.0, the **__Server** property of the object that `Get-WmiObject` returns has a **PSComputerName** alias.</span></span> <span data-ttu-id="da442-121">Dadurch kann der Quellcomputername leichter in die Ausgabe und in Berichte aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="da442-121">This makes it easier to include the source computer name in output and reports.</span></span>

## <span data-ttu-id="da442-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="da442-122">EXAMPLES</span></span>

### <span data-ttu-id="da442-123">Beispiel 1: erhalten Sie Prozesse auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="da442-123">Example 1: Get processes on the local computer</span></span>

<span data-ttu-id="da442-124">In diesem Beispiel werden die Prozesse auf dem lokalen Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da442-124">This example get the processes on the local computer.</span></span>

```powershell
Get-WmiObject -Class Win32_Process
```

### <span data-ttu-id="da442-125">Beispiel 2: Abrufen von Diensten auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="da442-125">Example 2: Gets services on a remote computer</span></span>

<span data-ttu-id="da442-126">In diesem Beispiel werden die Dienste auf einem Remote Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="da442-126">This example gets the services on a remote computer.</span></span> <span data-ttu-id="da442-127">Der **Computername** -Parameter gibt die IP-Adresse eines Remote Computers an.</span><span class="sxs-lookup"><span data-stu-id="da442-127">The **ComputerName** parameter specifies the IP address of a remote computer.</span></span> <span data-ttu-id="da442-128">Standardmäßig muss das aktuelle Benutzerkonto Mitglied der Gruppe " **Administratoren** " auf dem Remote Computer sein.</span><span class="sxs-lookup"><span data-stu-id="da442-128">By default, the current user account must be a member of the **Administrators** group on the remote computer.</span></span>

```powershell
Get-WmiObject -Class Win32_Service -ComputerName 10.1.4.62
```

### <span data-ttu-id="da442-129">Beispiel 3: WMI-Klassen im Stamm-oder Standard Namespace des lokalen Computers</span><span class="sxs-lookup"><span data-stu-id="da442-129">Example 3: Get WMI classes in the root or default namespace of the local computer</span></span>

<span data-ttu-id="da442-130">In diesem Beispiel werden die WMI-Klassen im Stamm-oder Standard Namespace des lokalen Computers abgerufen.</span><span class="sxs-lookup"><span data-stu-id="da442-130">This example gets the WMI classes in the root or default namespace of the local computer.</span></span>

```powershell
Get-WmiObject -Namespace "root/default" -List
```

### <span data-ttu-id="da442-131">Beispiel 4: erhalten eines benannten Dienstanbieter auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="da442-131">Example 4: Get a named service on multiple computers</span></span>

<span data-ttu-id="da442-132">In diesem Beispiel wird der WinRM-Dienst auf den Computern abgerufen, die durch den Wert des **Computername** -Parameters angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="da442-132">This example gets the WinRM service on the computers specified by the value of the **ComputerName** parameter.</span></span>

```powershell
Get-WmiObject -Query "select * from win32_service where name='WinRM'" -ComputerName Server01, Server02 |
  Format-List -Property PSComputerName, Name, ExitCode, Name, ProcessID, StartMode, State, Status
```

```Output
PSComputerName : SERVER01
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 844
StartMode      : Auto
State          : Running
Status         : OK

PSComputerName : SERVER02
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 932
StartMode      : Auto
State          : Running
Status         : OK
```

<span data-ttu-id="da442-133">Ein Pipelineoperator (|) sendet die Ausgabe an das Cmdlet `Format-List`, wodurch die **PSComputerName** -Eigenschaft der Standardausgabe hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="da442-133">A pipeline operator (|) sends the output to the `Format-List` cmdlet, which adds the **PSComputerName** property to the default output.</span></span> <span data-ttu-id="da442-134">**Pscomputername** ist ein Alias der **__Server** -Eigenschaft der Objekte, die `Get-WmiObject` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="da442-134">**PSComputerName** is an alias of the **__Server** property of the objects that `Get-WmiObject` returns.</span></span> <span data-ttu-id="da442-135">Dieser Alias wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="da442-135">This alias was introduced in PowerShell 3.0.</span></span>

### <span data-ttu-id="da442-136">Beispiel 5: Beendigung eines Dienstanbieter auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="da442-136">Example 5: Stop a service on a remote computer</span></span>

<span data-ttu-id="da442-137">In diesem Beispiel wird der WinRM-Dienst auf einem Remote Computer angehalten.</span><span class="sxs-lookup"><span data-stu-id="da442-137">This example stops the WinRM service on a remote computer.</span></span> <span data-ttu-id="da442-138">`Get-WmiObject` Ruft die Instanz des WinRM-Dienst Objekts auf SERVER01 ab.</span><span class="sxs-lookup"><span data-stu-id="da442-138">`Get-WmiObject` gets the instance of the WinRM service object on Server01.</span></span> <span data-ttu-id="da442-139">Anschließend wird die **Stop Service** -Methode der **Win32_Service** WMI-Klasse für dieses Objekt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="da442-139">Then, it invokes the **StopService** method of the **Win32_Service** WMI class on that object.</span></span>

```powershell
(Get-WmiObject -Class Win32_Service -Filter "name='WinRM'" -ComputerName Server01).StopService()
```

<span data-ttu-id="da442-140">Dies entspricht der Verwendung des- `Stop-Service` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="da442-140">This is equivalent to using the `Stop-Service` cmdlet.</span></span>

### <span data-ttu-id="da442-141">Beispiel 6: das BIOS auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="da442-141">Example 6: Get the BIOS on the local computer</span></span>

<span data-ttu-id="da442-142">In diesem Beispiel werden die BIOS-Informationen vom lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="da442-142">This example gets the BIOS information from the local computer.</span></span> <span data-ttu-id="da442-143">Der **Property** -Parameter des `Format-List` Cmdlets wird verwendet, um alle Eigenschaften des zurückgegebenen Objekts in einer Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="da442-143">The **Property** parameter of the `Format-List` cmdlet is used to display all properties of the returned object in a list.</span></span> <span data-ttu-id="da442-144">Standardmäßig wird nur die Teilmenge der in der `Types.ps1xml` Konfigurationsdatei definierten Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da442-144">By default, only the subset of properties defined in the `Types.ps1xml` configuration file are displayed.</span></span>

```powershell
Get-WmiObject -Class Win32_Bios | Format-List -Property *
```

```Output
Status                : OK
Name                  : Phoenix ROM BIOS PLUS Version 1.10 A05
Caption               : Phoenix ROM BIOS PLUS Version 1.10 A05
SMBIOSPresent         : True
__GENUS               : 2
__CLASS               : Win32_BIOS
__SUPERCLASS          : CIM_BIOSElement
__DYNASTY             : CIM_ManagedSystemElement
__RELPATH             : Win32_BIOS.Name="Phoenix ROM BIOS PLUS Version 1.10
__PROPERTY_COUNT      : 27
__DERIVATION          : {CIM_BIOSElement, CIM_SoftwareElement, CIM_LogicalElement,
__SERVER              : Server01
__NAMESPACE           : root\cimv2
__PATH                : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
BiosCharacteristics   : {7, 9, 10, 11...}
BIOSVersion           : {DELL   - 15, Phoenix ROM BIOS PLUS Version 1.10 A05}
BuildNumber           :
CodeSet               :
CurrentLanguage       : en|US|iso8859-1
Description           : Phoenix ROM BIOS PLUS Version 1.10 A05
IdentificationCode    :
InstallableLanguages  : 1
InstallDate           :
LanguageEdition       :
ListOfLanguages       : {en|US|iso8859-1}
Manufacturer          : Dell Inc.
OtherTargetOS         :
PrimaryBIOS           : True
ReleaseDate           : 20101103000000.000000+000
SerialNumber          : 8VDM9P1
SMBIOSBIOSVersion     : A05
SMBIOSMajorVersion    : 2
SMBIOSMinorVersion    : 6
SoftwareElementID     : Phoenix ROM BIOS PLUS Version 1.10 A05
SoftwareElementState  : 3
TargetOperatingSystem : 0
Version               : DELL   - 15
Scope                 : System.Management.ManagementScope
Path                  : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
Options               : System.Management.ObjectGetOptions
ClassPath             : \\JUNE-PC\root\cimv2:Win32_BIOS
Properties            : {BiosCharacteristics, BIOSVersion, BuildNumber, Caption...}
SystemProperties      : {__GENUS, __CLASS, __SUPERCLASS, __DYNASTY...}
Qualifiers            : {dynamic, Locale, provider, UUID}
Site                  :
Container             :
```

### <span data-ttu-id="da442-145">Beispiel 7: erhalten der Dienste auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="da442-145">Example 7: Get the services on a remote computer</span></span>

<span data-ttu-id="da442-146">In diesem Beispiel wird der **Credential** -Parameter des `Get-WmiObject` Cmdlets verwendet, um die Dienste auf einem Remote Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="da442-146">This example uses the **Credential** parameter of the `Get-WmiObject` cmdlet to get the services on a remote computer.</span></span> <span data-ttu-id="da442-147">Beim Wert des **Credential** -Parameters handelt es sich um einen Benutzerkontonamen.</span><span class="sxs-lookup"><span data-stu-id="da442-147">The value of the **Credential** parameter is a user account name.</span></span> <span data-ttu-id="da442-148">Der Benutzer wird zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="da442-148">The user is prompted for a password.</span></span>

```powershell
Get-WmiObject Win32_Service -Credential FABRIKAM\administrator -ComputerName Fabrikam
```

> [!NOTE]
> <span data-ttu-id="da442-149">Anmelde Informationen können nicht für den lokalen Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da442-149">Credentials cannot be used when targeting the local computer.</span></span>

## <span data-ttu-id="da442-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="da442-150">PARAMETERS</span></span>

### <span data-ttu-id="da442-151">-Geändert</span><span class="sxs-lookup"><span data-stu-id="da442-151">-Amended</span></span>

<span data-ttu-id="da442-152">Ruft einen Wert ab, der angibt, ob die von WMI zurückgegebenen Objekte ergänzte Informationen enthalten sollen, oder legt diesen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="da442-152">Gets or sets a value that indicates whether the objects that are returned from WMI should contain amended information.</span></span> <span data-ttu-id="da442-153">Normalerweise handelt es sich bei ergänzten Informationen um lokalisierbare Informationen, die an das WMI-Objekt angefügt sind, z. B. Objekt- und Eigenschaftenbeschreibungen.</span><span class="sxs-lookup"><span data-stu-id="da442-153">Typically, amended information is localizable information, such as object and property descriptions, that is attached to the WMI object.</span></span>

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

### <span data-ttu-id="da442-154">-AsJob</span><span class="sxs-lookup"><span data-stu-id="da442-154">-AsJob</span></span>

<span data-ttu-id="da442-155">Führt den Befehl als Hintergrundauftrag aus.</span><span class="sxs-lookup"><span data-stu-id="da442-155">Runs the command as a background job.</span></span> <span data-ttu-id="da442-156">Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="da442-156">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="da442-157">Wenn Sie den **AsJob** -Parameter verwenden, gibt der Befehl ein Objekt zurück, das den Hintergrundauftrag darstellt, und zeigt dann die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="da442-157">When you use the **AsJob** parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span> <span data-ttu-id="da442-158">Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="da442-158">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="da442-159">Wenn `Get-WmiObject` auf einem Remote Computer verwendet wird, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse von Remote Computern werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="da442-159">If `Get-WmiObject` is used on a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="da442-160">Verwenden Sie zum Verwalten des Auftrags die Cmdlets, die die Job-Cmdlets enthalten.</span><span class="sxs-lookup"><span data-stu-id="da442-160">To manage the job, use the cmdlets that contain the Job cmdlets.</span></span> <span data-ttu-id="da442-161">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="da442-161">To get the job results, use the `Receive-Job` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="da442-162">Um diesen Parameter für Remotecomputer zu verwenden, müssen lokale Computer und Remotecomputer für Remoting konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="da442-162">To use this parameter with remote computers, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="da442-163">Außerdem müssen Sie Windows PowerShell in Windows Vista und höheren Versionen von Windows mit der Option %%amp;quot;Als Administrator ausführen%%amp;quot; starten.</span><span class="sxs-lookup"><span data-stu-id="da442-163">Additionally, you must start Windows PowerShell by using the "Run as administrator" option in Windows Vista and later versions of Windows.</span></span> <span data-ttu-id="da442-164">Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da442-164">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="da442-165">Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="da442-165">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="da442-166">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="da442-166">-Authentication</span></span>

<span data-ttu-id="da442-167">Gibt die für die WMI-Verbindung zu verwendende Authentifizierungsebene an.</span><span class="sxs-lookup"><span data-stu-id="da442-167">Specifies the authentication level to be used with the WMI connection.</span></span>
<span data-ttu-id="da442-168">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="da442-168">Valid values are:</span></span>

- <span data-ttu-id="da442-169">-1: Unchanged</span><span class="sxs-lookup"><span data-stu-id="da442-169">-1: Unchanged</span></span>
- <span data-ttu-id="da442-170">0: Default</span><span class="sxs-lookup"><span data-stu-id="da442-170">0: Default</span></span>
- <span data-ttu-id="da442-171">1: None (Es wird keine Authentifizierung ausgeführt.)</span><span class="sxs-lookup"><span data-stu-id="da442-171">1: None (No authentication in performed.)</span></span>
- <span data-ttu-id="da442-172">2: Connect (Die Authentifizierung wird nur ausgeführt, wenn der Client eine Beziehung mit der Anwendung herstellt.)</span><span class="sxs-lookup"><span data-stu-id="da442-172">2: Connect (Authentication is performed only when the client establishes a relationship with the application.)</span></span>
- <span data-ttu-id="da442-173">3: Call (Die Authentifizierung wird nur zu Beginn eines Aufrufs ausgeführt, wenn die Anwendung die Anforderung empfängt.)</span><span class="sxs-lookup"><span data-stu-id="da442-173">3: Call (Authentication is performed only at the beginning of each call when the application receives the request.)</span></span>
- <span data-ttu-id="da442-174">4: Packet (Die Authentifizierung wird für alle Daten ausgeführt, die vom Client empfangen werden.)</span><span class="sxs-lookup"><span data-stu-id="da442-174">4: Packet (Authentication is performed on all the data that is received from the client.)</span></span>
- <span data-ttu-id="da442-175">5: packetintegrity (alle Daten, die zwischen dem Client und der Anwendung übertragen werden, werden authentifiziert und überprüft.)</span><span class="sxs-lookup"><span data-stu-id="da442-175">5: PacketIntegrity (All the data that is transferred between the client and the application is authenticated and verified.)</span></span>
- <span data-ttu-id="da442-176">6: PacketPrivacy (Die Eigenschaften der anderen Authentifizierungsebenen werden verwendet, und alle Daten werden verschlüsselt.)</span><span class="sxs-lookup"><span data-stu-id="da442-176">6: PacketPrivacy (The properties of the other authentication levels are used, and all the data is encrypted.)</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-177">-Autorität</span><span class="sxs-lookup"><span data-stu-id="da442-177">-Authority</span></span>

<span data-ttu-id="da442-178">Gibt die Autorität an, die zum Authentifizieren der WMI-Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="da442-178">Specifies the authority to use to authenticate the WMI connection.</span></span> <span data-ttu-id="da442-179">Sie können die Standard-NTLM- oder Kerberos-Authentifizierung angeben.</span><span class="sxs-lookup"><span data-stu-id="da442-179">You can specify standard NTLM or Kerberos authentication.</span></span> <span data-ttu-id="da442-180">Legen Sie für die Verwendung von NTLM die Authority-Einstellung auf fest `ntlmdomain:<DomainName>` , wobei `<DomainName>` einen gültigen NTLM-Domänen Namen angibt.</span><span class="sxs-lookup"><span data-stu-id="da442-180">To use NTLM, set the authority setting to `ntlmdomain:<DomainName>`, where `<DomainName>` identifies a valid NTLM domain name.</span></span> <span data-ttu-id="da442-181">Wenn Sie Kerberos verwenden möchten, geben Sie an `kerberos:<DomainName>\<ServerName>` .</span><span class="sxs-lookup"><span data-stu-id="da442-181">To use Kerberos, specify `kerberos:<DomainName>\<ServerName>`.</span></span> <span data-ttu-id="da442-182">Sie können die Authority-Einstellung nicht einschließen, wenn Sie eine Verbindung mit dem lokalen Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="da442-182">You cannot include the authority setting when you connect to the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-183">-Klasse</span><span class="sxs-lookup"><span data-stu-id="da442-183">-Class</span></span>

<span data-ttu-id="da442-184">Gibt den Namen einer WMI-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="da442-184">Specifies the name of a WMI class.</span></span> <span data-ttu-id="da442-185">Wenn dieser Parameter verwendet wird, ruft das Cmdlet Instanzen der WMI-Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="da442-185">When this parameter is used, the cmdlet retrieves instances of the WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: query, list
Aliases: ClassName

Required: True (query), False (list)
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-186">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="da442-186">-ComputerName</span></span>

<span data-ttu-id="da442-187">Gibt den Zielcomputer für den Verwaltungsvorgang an.</span><span class="sxs-lookup"><span data-stu-id="da442-187">Specifies the target computer for the management operation.</span></span> <span data-ttu-id="da442-188">Geben Sie einen voll qualifizierten Domänen Namen (FQDN), einen NetBIOS-Namen oder eine IP-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="da442-188">Enter a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="da442-189">Wenn sich der Remotecomputer in einer anderen Domäne als der lokale Computer befindet, ist der vollqualifizierte Domänenname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="da442-189">When the remote computer is in a different domain than the local computer, the fully qualified domain name is required.</span></span>

<span data-ttu-id="da442-190">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="da442-190">The default is the local computer.</span></span> <span data-ttu-id="da442-191">Verwenden Sie zum Angeben des lokalen Computers (z. B. in einer Liste mit Computernamen) %%amp;quot;localhost%%amp;quot;, den Namen des lokalen Computers oder einen Punkt (.).</span><span class="sxs-lookup"><span data-stu-id="da442-191">To specify the local computer, such as in a list of computer names, use "localhost", the local computer name, or a dot (.).</span></span>

<span data-ttu-id="da442-192">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting, bei dem die WS-Verwaltung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="da442-192">This parameter does not rely on Windows PowerShell remoting, which uses WS-Management.</span></span> <span data-ttu-id="da442-193">Sie können den **Computername** -Parameter `Get-WmiObject` auch dann verwenden, wenn der Computer nicht für das Ausführen WS-Management Remote Befehle konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="da442-193">You can use the **ComputerName** parameter of `Get-WmiObject` even if your computer is not configured to run WS-Management remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-194">-Credential</span><span class="sxs-lookup"><span data-stu-id="da442-194">-Credential</span></span>

<span data-ttu-id="da442-195">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="da442-195">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="da442-196">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="da442-196">The default is the current user.</span></span> <span data-ttu-id="da442-197">Geben Sie einen Benutzernamen ein, z. b. "USER01", "Domain01\User01" oder User@Contoso.com .</span><span class="sxs-lookup"><span data-stu-id="da442-197">Type a user name, such as "User01", "Domain01\User01", or User@Contoso.com.</span></span> <span data-ttu-id="da442-198">Oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein Objekt, das vom Cmdlet `Get-Credential` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="da442-198">Or, enter a **PSCredential** object, such as an object that is returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="da442-199">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="da442-199">When you type a user name, you are prompted for a password.</span></span> <span data-ttu-id="da442-200">Anmelde Informationen können nicht für den lokalen Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da442-200">Credentials cannot be used when targeting the local computer.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-201">-Directread</span><span class="sxs-lookup"><span data-stu-id="da442-201">-DirectRead</span></span>

<span data-ttu-id="da442-202">Gibt an, ob der Direktzugriff auf den WMI-Anbieter für die angegebene Klasse angefordert wird, unabhängig von deren Basisklasse oder abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="da442-202">Specifies whether direct access to the WMI provider is requested for the specified class without any regard to its base class or to its derived classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: query, WQLQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-203">-Enableallprivileges</span><span class="sxs-lookup"><span data-stu-id="da442-203">-EnableAllPrivileges</span></span>

<span data-ttu-id="da442-204">Aktiviert alle Berechtigungen des aktuellen Benutzers, bevor der Befehl den WMI-Aufruf ausführt.</span><span class="sxs-lookup"><span data-stu-id="da442-204">Enables all the privileges of the current user before the command makes the WMI call.</span></span>

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

### <span data-ttu-id="da442-205">-Filter</span><span class="sxs-lookup"><span data-stu-id="da442-205">-Filter</span></span>

<span data-ttu-id="da442-206">Gibt eine als Filter zu verwendende **Where** -Klausel an.</span><span class="sxs-lookup"><span data-stu-id="da442-206">Specifies a **Where** clause to use as a filter.</span></span> <span data-ttu-id="da442-207">Verwendet die WQL (WMI Query Language)-Syntax.</span><span class="sxs-lookup"><span data-stu-id="da442-207">Uses the syntax of the WMI Query Language (WQL).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da442-208">Schließen Sie das **Where** -Schlüsselwort nicht in den Wert des Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="da442-208">Do not include the **Where** keyword in the value of the parameter.</span></span> <span data-ttu-id="da442-209">Die folgenden Befehle geben z. B. nur die logischen Datenträger zurück, deren **DeviceID** %%amp;quot;c:%%amp;quot; entspricht, und die Dienste, deren Name %%amp;quot;WinRM%%amp;quot; entspricht, ohne das **Where** -Schlüsselwort zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="da442-209">For example, the following commands return only the logical disks that have a **DeviceID** of 'c:' and services that have the name 'WinRM' without using the **Where** keyword.</span></span>

`Get-WmiObject Win32_LogicalDisk -filter "DeviceID = 'c:' "`

`Get-WmiObject win32_service -filter "name='WinRM'"`

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-210">-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="da442-210">-Impersonation</span></span>

<span data-ttu-id="da442-211">Gibt die zu verwendende Identitätswechselebene an.</span><span class="sxs-lookup"><span data-stu-id="da442-211">Specifies the impersonation level to use.</span></span>

<span data-ttu-id="da442-212">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="da442-212">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="da442-213">0: Default.</span><span class="sxs-lookup"><span data-stu-id="da442-213">0: Default.</span></span> <span data-ttu-id="da442-214">Liest die lokale Registrierung für die Standard Ebene des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="da442-214">Reads the local registry for the default impersonation level.</span></span> <span data-ttu-id="da442-215">Der Standardwert **ist in der Regel auf Identitäts** Wechsel festgelegt.</span><span class="sxs-lookup"><span data-stu-id="da442-215">The default is usually set to **Impersonate** .</span></span>
- <span data-ttu-id="da442-216">1: Anonymous.</span><span class="sxs-lookup"><span data-stu-id="da442-216">1: Anonymous.</span></span> <span data-ttu-id="da442-217">Verbirgt die Anmeldeinformationen des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="da442-217">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="da442-218">2: Identify.</span><span class="sxs-lookup"><span data-stu-id="da442-218">2: Identify.</span></span> <span data-ttu-id="da442-219">Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers abzufragen.</span><span class="sxs-lookup"><span data-stu-id="da442-219">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="da442-220">3: Impersonate.</span><span class="sxs-lookup"><span data-stu-id="da442-220">3: Impersonate.</span></span> <span data-ttu-id="da442-221">Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="da442-221">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="da442-222">4: Delegate.</span><span class="sxs-lookup"><span data-stu-id="da442-222">4: Delegate.</span></span> <span data-ttu-id="da442-223">Ermöglicht es Objekten, anderen Objekten die Verwendung der Anmeldeinformationen des Aufrufers zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="da442-223">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-224">-List</span><span class="sxs-lookup"><span data-stu-id="da442-224">-List</span></span>

<span data-ttu-id="da442-225">Ruft die Namen der WMI-Klassen im WMI-Repositorynamespace, der im **Namespace** -Parameter angegeben ist, ab.</span><span class="sxs-lookup"><span data-stu-id="da442-225">Gets the names of the WMI classes in the WMI repository namespace that is specified by the **Namespace** parameter.</span></span>

<span data-ttu-id="da442-226">Wenn Sie den **List** -Parameter, aber nicht den **Namespace** -Parameter angeben, `Get-WmiObject` verwendet standardmäßig den **root\cimv2** -Namespace.</span><span class="sxs-lookup"><span data-stu-id="da442-226">If you specify the **List** parameter, but not the **Namespace** parameter, `Get-WmiObject` uses the **Root\Cimv2** namespace by default.</span></span> <span data-ttu-id="da442-227">Dieses Cmdlet verwendet nicht den **standardmäßigen Namespace** -Registrierungs Eintrag im `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` Registrierungsschlüssel, um den Standard Namespace zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="da442-227">This cmdlet does not use the **Default Namespace** registry entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` registry key to determine the default namespace.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-228">-Gebiets Schema</span><span class="sxs-lookup"><span data-stu-id="da442-228">-Locale</span></span>

<span data-ttu-id="da442-229">Gibt das bevorzugte Gebietsschema für WMI-Objekte an.</span><span class="sxs-lookup"><span data-stu-id="da442-229">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="da442-230">Geben Sie einen Wert im Format %%amp;quot;MS_\<LCID\>%%amp;quot; an.</span><span class="sxs-lookup"><span data-stu-id="da442-230">Enter a value in MS_\<LCID\> format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-231">-Namespace</span><span class="sxs-lookup"><span data-stu-id="da442-231">-Namespace</span></span>

<span data-ttu-id="da442-232">Bei Verwendung mit dem **Class** -Parameter gibt der **Namespace** -Parameter den WMI-Repository-Namespace an, in dem sich die angegebene WMI-Klasse befindet.</span><span class="sxs-lookup"><span data-stu-id="da442-232">When used with the **Class** parameter, the **Namespace** parameter specifies the WMI repository namespace where the specified WMI class is located.</span></span> <span data-ttu-id="da442-233">Bei Verwendung mit dem **List** -Parameter gibt er den Namespace an, aus dem die WMI-Klasseninformationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="da442-233">When used with the **List** parameter, it specifies the namespace from which to gather WMI class information.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-234">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="da442-234">-Property</span></span>

<span data-ttu-id="da442-235">Gibt die WMI-Klasseneigenschaften an, von denen dieses Cmdlet Informationen abruft.</span><span class="sxs-lookup"><span data-stu-id="da442-235">Specifies the WMI class properties that this cmdlet gets information from.</span></span> <span data-ttu-id="da442-236">Geben Sie die Eigenschaftennamen an.</span><span class="sxs-lookup"><span data-stu-id="da442-236">Enter the property names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: query
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-237">-Query</span><span class="sxs-lookup"><span data-stu-id="da442-237">-Query</span></span>

<span data-ttu-id="da442-238">Führt die angegebene WMI Query Language (WQL)-Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="da442-238">Runs the specified WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="da442-239">Von diesem Parameter werden keine Ereignisabfragen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="da442-239">This parameter does not support event queries.</span></span>

```yaml
Type: System.String
Parameter Sets: WQLQuery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-240">-Recurse</span><span class="sxs-lookup"><span data-stu-id="da442-240">-Recurse</span></span>

<span data-ttu-id="da442-241">Durchsucht den aktuellen Namespace und alle anderen Namespaces nach dem im **Class** -Parameter angegebenen Klassennamen.</span><span class="sxs-lookup"><span data-stu-id="da442-241">Searches the current namespace and all other namespaces for the class name that is specified by the **Class** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-242">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="da442-242">-ThrottleLimit</span></span>

<span data-ttu-id="da442-243">Gibt die maximale Anzahl der WMI-Vorgänge an, die gleichzeitig ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="da442-243">Specifies the maximum number of WMI operations that can be executed simultaneously.</span></span> <span data-ttu-id="da442-244">Dieser Parameter ist nur gültig, wenn der **AsJob** -Parameter im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="da442-244">This parameter is valid only when the **AsJob** parameter is used in the command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da442-245">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="da442-245">CommonParameters</span></span>

<span data-ttu-id="da442-246">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="da442-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="da442-247">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="da442-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="da442-248">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="da442-248">INPUTS</span></span>

### <span data-ttu-id="da442-249">Keine</span><span class="sxs-lookup"><span data-stu-id="da442-249">None</span></span>

<span data-ttu-id="da442-250">Eingaben können nicht an übergeben werden `Get-WmiObject` .</span><span class="sxs-lookup"><span data-stu-id="da442-250">You cannot pipe input to `Get-WmiObject`.</span></span>

## <span data-ttu-id="da442-251">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="da442-251">OUTPUTS</span></span>

### <span data-ttu-id="da442-252">Psobject oder System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="da442-252">PSObject or System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="da442-253">Wenn Sie den **AsJob** -Parameter verwenden, wird vom Cmdlet ein Auftragsobjekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="da442-253">When you use the **AsJob** parameter, the cmdlet returns a job object.</span></span> <span data-ttu-id="da442-254">Andernfalls hängt das Objekt, das `Get-WmiObject` zurückgibt, von dem Wert des **Class** -Parameters ab.</span><span class="sxs-lookup"><span data-stu-id="da442-254">Otherwise, the object that `Get-WmiObject` returns depends on the value of the **Class** parameter.</span></span>

## <span data-ttu-id="da442-255">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="da442-255">NOTES</span></span>

<span data-ttu-id="da442-256">Für den Zugriff auf WMI-Informationen auf einem Remotecomputer muss das Cmdlet unter einem Konto ausgeführt werden, das auf dem Remotecomputer Mitglied der lokalen Administratorengruppe ist.</span><span class="sxs-lookup"><span data-stu-id="da442-256">To access WMI information on a remote computer, the cmdlet must run under an account that is a member of the local administrators group on the remote computer.</span></span> <span data-ttu-id="da442-257">Die Standardzugriffssteuerung für den WMI-Namespace des Remote-Repositorys kann auch so geändert werden, dass anderen Konten Zugriffsrechte gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="da442-257">Or, the default access control on the WMI namespace of the remote repository can be changed to give access rights to other accounts.</span></span>

<span data-ttu-id="da442-258">Standardmäßig werden nur einige Eigenschaften einer WMI-Klasse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da442-258">Only some of the properties of each WMI class are displayed by default.</span></span> <span data-ttu-id="da442-259">Welche Eigenschaften für die einzelnen WMI-Klassen angezeigt werden, ist in der Konfigurationsdatei %%amp;quot;Types.ps1xml%%amp;quot; festgelegt.</span><span class="sxs-lookup"><span data-stu-id="da442-259">The set of properties that is displayed for each WMI class is specified in the Types.ps1xml configuration file.</span></span> <span data-ttu-id="da442-260">Um alle Eigenschaften eines WMI-Objekts zu erhalten, verwenden Sie die `Get-Member` `Format-List` Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="da442-260">To get all properties of a WMI object, use the `Get-Member` or `Format-List` cmdlets.</span></span>

## <span data-ttu-id="da442-261">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="da442-261">RELATED LINKS</span></span>

[<span data-ttu-id="da442-262">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="da442-262">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="da442-263">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="da442-263">Remove-WmiObject</span></span>](Remove-WmiObject.md)

[<span data-ttu-id="da442-264">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="da442-264">Set-WmiInstance</span></span>](Set-WmiInstance.md)

[<span data-ttu-id="da442-265">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="da442-265">Get-WSManInstance</span></span>](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[<span data-ttu-id="da442-266">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="da442-266">Invoke-WSManAction</span></span>](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[<span data-ttu-id="da442-267">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="da442-267">New-WSManInstance</span></span>](../Microsoft.WsMan.Management/New-WSManInstance.md)

[<span data-ttu-id="da442-268">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="da442-268">Remove-WSManInstance</span></span>](../Microsoft.WsMan.Management/Remove-WSManInstance.md)
