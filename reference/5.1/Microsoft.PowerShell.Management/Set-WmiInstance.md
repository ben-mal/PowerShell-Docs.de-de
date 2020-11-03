---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-wmiinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmiInstance
ms.openlocfilehash: 03288a2ffbef416937b2c92a7d08a5aed49ffb43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214412"
---
# <span data-ttu-id="d6838-103">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="d6838-103">Set-WmiInstance</span></span>

## <span data-ttu-id="d6838-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d6838-104">SYNOPSIS</span></span>
<span data-ttu-id="d6838-105">Erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI).</span><span class="sxs-lookup"><span data-stu-id="d6838-105">Creates or updates an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>

## <span data-ttu-id="d6838-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d6838-106">SYNTAX</span></span>

### <span data-ttu-id="d6838-107">Class (Standard)</span><span class="sxs-lookup"><span data-stu-id="d6838-107">class (Default)</span></span>

```
Set-WmiInstance [-Class] <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d6838-108">Objekt</span><span class="sxs-lookup"><span data-stu-id="d6838-108">object</span></span>

```
Set-WmiInstance -InputObject <ManagementObject> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d6838-109">path</span><span class="sxs-lookup"><span data-stu-id="d6838-109">path</span></span>

```
Set-WmiInstance -Path <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d6838-110">Wqlquery</span><span class="sxs-lookup"><span data-stu-id="d6838-110">WQLQuery</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d6838-111">Abfrage</span><span class="sxs-lookup"><span data-stu-id="d6838-111">query</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d6838-112">list</span><span class="sxs-lookup"><span data-stu-id="d6838-112">list</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d6838-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d6838-113">DESCRIPTION</span></span>
<span data-ttu-id="d6838-114">Das- `Set-WmiInstance` Cmdlet erstellt oder aktualisiert eine Instanz einer vorhandenen WMI-Klasse (Windows-Verwaltungsinstrumentation).</span><span class="sxs-lookup"><span data-stu-id="d6838-114">The `Set-WmiInstance` cmdlet creates or updates an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>
<span data-ttu-id="d6838-115">Die erstellte oder aktualisierte Instanz wird in das WMI-Repository geschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6838-115">The created or updated instance is written to the WMI repository.</span></span>

<span data-ttu-id="d6838-116">Mit den neuen in Windows PowerShell 3.0 eingeführten CIM-Cmdlets werden die gleichen Aufgaben wie mit WMI-Cmdlets ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d6838-116">New CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span>
<span data-ttu-id="d6838-117">Die CIM-Cmdlets entsprechen den WS-Management (WSMAN)-Standards und dem Common Information Model (CIM)-Standard.</span><span class="sxs-lookup"><span data-stu-id="d6838-117">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard.</span></span>
<span data-ttu-id="d6838-118">Dadurch können Cmdlets dieselben Verfahren zum Verwalten von Windows-basierten Computern und denjenigen verwenden, auf denen andere Betriebssysteme ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d6838-118">this enables cmdlets to use the same techniques to manage Windows-based computers and those running other operating systems.</span></span>
<span data-ttu-id="d6838-119">Anstatt zu verwenden `Set-WmiInstance` , sollten Sie die Cmdlets [Set-ciminstance](/powershell/module/cimcmdlets/set-ciminstance) oder [New-ciminstance](/powershell/module/cimcmdlets/new-ciminstance) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6838-119">Instead of using `Set-WmiInstance`, consider using the [Set-CimInstance](/powershell/module/cimcmdlets/set-ciminstance) or [New-CimInstance](/powershell/module/cimcmdlets/new-ciminstance) cmdlets.</span></span>

## <span data-ttu-id="d6838-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d6838-120">EXAMPLES</span></span>

### <span data-ttu-id="d6838-121">Beispiel 1: Festlegen der WMI-Protokollierungs Stufe</span><span class="sxs-lookup"><span data-stu-id="d6838-121">Example 1: Set WMI logging level</span></span>

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2}
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
```

<span data-ttu-id="d6838-122">Mit diesem Befehl wird der WMI-Protokolliergrad auf %%amp;quot;2%%amp;quot; festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d6838-122">This command sets the WMI logging level to 2.</span></span>
<span data-ttu-id="d6838-123">Der Befehl übergibt die festzulegende Eigenschaft, und der Wert, der als Wertpaar betrachtet wird, im Argument-Parameter.</span><span class="sxs-lookup"><span data-stu-id="d6838-123">The command passes the property to be set and the value, together considered a value pair, in the argument parameter.</span></span>
<span data-ttu-id="d6838-124">Der Parameter akzeptiert eine durch die Konstruktion %%amp;quot;@{property = value}%%amp;quot; definierte Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="d6838-124">The parameter takes a hash table that is defined by the @{property = value} construction.</span></span>
<span data-ttu-id="d6838-125">Die zurückgegebenen Klasseninformationen spiegeln den neuen Wert wider.</span><span class="sxs-lookup"><span data-stu-id="d6838-125">The class information that is returned reflects the new value.</span></span>

### <span data-ttu-id="d6838-126">Beispiel 2: Erstellen einer Umgebungsvariablen und ihres Werts</span><span class="sxs-lookup"><span data-stu-id="d6838-126">Example 2: Create an environment variable and its value</span></span>

```
PS C:\> Set-WmiInstance -Class win32_environment -Argument @{Name="testvar";VariableValue="testvalue";UserName="<SYSTEM>"}
__GENUS          : 2
__CLASS          : Win32_Environment
__SUPERCLASS     : CIM_SystemResource
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Environment.Name="testvar",UserName="<SYSTEM>"
__PROPERTY_COUNT : 8
__DERIVATION     : {CIM_SystemResource, CIM_LogicalElement, CIM_ManagedSystemElement}
__SERVER         : SYSTEM01
__NAMESPACE      : root\cimv2
__PATH           : \\SYSTEM01\root\cimv2:Win32_Environment.Name="testvar",UserName="<SYSTEM>"
Caption          : <SYSTEM>\testvar
Description      : <SYSTEM>\testvar
InstallDate      :
Name             : testvar
Status           : OK
SystemVariable   : True
UserName         : <SYSTEM>
VariableValue    : testvalue
```

<span data-ttu-id="d6838-127">Mit diesem Befehl wird die TestVar-Umgebungsvariable mit dem Wert "TestValue" erstellt.</span><span class="sxs-lookup"><span data-stu-id="d6838-127">This command creates the testvar environment variable that has the value testvalue.</span></span>
<span data-ttu-id="d6838-128">Dies geschieht durch Erstellen einer neuen Instanz der WMI-Klasse **Win32_Environment** .</span><span class="sxs-lookup"><span data-stu-id="d6838-128">It does this by creating a new instance of the **Win32_Environment** WMI class.</span></span>
<span data-ttu-id="d6838-129">Dieser Vorgang erfordert geeignete Anmelde Informationen, und Sie müssen Windows PowerShell möglicherweise neu starten, damit die neue Umgebungsvariable angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d6838-129">This operation requires appropriate credentials and that you may have to restart Windows PowerShell to see the new environment variable.</span></span>

### <span data-ttu-id="d6838-130">Beispiel 3: Festlegen der WMI-Protokollierungs Stufe für mehrere Remote Computer</span><span class="sxs-lookup"><span data-stu-id="d6838-130">Example 3: Set WMI logging level for several remote computers</span></span>

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2} -Computername "system01", "system02", "system03"
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
...
```

<span data-ttu-id="d6838-131">Mit diesem Befehl wird der WMI-Protokolliergrad auf %%amp;quot;2%%amp;quot; festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d6838-131">This command sets the WMI logging level to 2.</span></span>
<span data-ttu-id="d6838-132">Der Befehl übergibt die festzulegende Eigenschaft, und der Wert, der als Wertpaar betrachtet wird, im Argument-Parameter.</span><span class="sxs-lookup"><span data-stu-id="d6838-132">The command passes the property to be set and the value, together considered a value pair, in the argument parameter.</span></span>
<span data-ttu-id="d6838-133">Der Parameter akzeptiert eine durch die Konstruktion %%amp;quot;@{property = value}%%amp;quot; definierte Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="d6838-133">The parameter takes a hash table that is defined by the @{property = value} construction.</span></span>
<span data-ttu-id="d6838-134">Die zurückgegebenen Klasseninformationen spiegeln den neuen Wert wider.</span><span class="sxs-lookup"><span data-stu-id="d6838-134">The returned class information reflects the new value.</span></span>

## <span data-ttu-id="d6838-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d6838-135">PARAMETERS</span></span>

### <span data-ttu-id="d6838-136">-Arguments</span><span class="sxs-lookup"><span data-stu-id="d6838-136">-Arguments</span></span>
<span data-ttu-id="d6838-137">Gibt den Namen der zu ändernden Eigenschaft und den neuen Wert für diese Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="d6838-137">Specifies the name of the property to be changed and the new value for that property.</span></span>
<span data-ttu-id="d6838-138">Der Name und der Wert müssen ein Name-Wert-Paar sein.</span><span class="sxs-lookup"><span data-stu-id="d6838-138">The name and value must be a name-value pair.</span></span>
<span data-ttu-id="d6838-139">Das Name-Wert-Paar wird in der Befehlszeile als Hash Tabelle weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="d6838-139">The name-value pair is passed on the command line as a hash table.</span></span>
<span data-ttu-id="d6838-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d6838-140">For example:</span></span>

`@{Setting1=1; Setting2=5; Setting3="test"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: class, object, path
Aliases: Args, Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-141">-AsJob</span><span class="sxs-lookup"><span data-stu-id="d6838-141">-AsJob</span></span>
<span data-ttu-id="d6838-142">Gibt an, dass dieses cmdket als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6838-142">Indicates that this cmdket runs as a background job.</span></span>
<span data-ttu-id="d6838-143">Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="d6838-143">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="d6838-144">Wenn Sie den *AsJob* -Parameter angeben, gibt der Befehl ein Objekt zurück, das den Hintergrund Auftrag darstellt, und zeigt dann die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="d6838-144">When you specify the *AsJob* parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span>
<span data-ttu-id="d6838-145">Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d6838-145">You can continue to work in the session while the job finishes.</span></span>
<span data-ttu-id="d6838-146">Wenn **Set-wmiinstance** für einen Remote Computer verwendet wird, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse von Remote Computern werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6838-146">If **Set-WmiInstance** is used for a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="d6838-147">Verwenden Sie zum Verwalten des Auftrags die Cmdlets, die das **Auftrags** Substantiv (die **Job** -Cmdlets) enthalten.</span><span class="sxs-lookup"><span data-stu-id="d6838-147">To manage the job, use the cmdlets that contain the **Job** noun (the **Job** cmdlets).</span></span>
<span data-ttu-id="d6838-148">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="d6838-148">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="d6838-149">Um diesen Parameter zusammen mit Remote Computern verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="d6838-149">To use this parameter together with remote computers, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="d6838-150">Außerdem müssen Sie Windows PowerShell mit der Option als Administrator ausführen in Windows Vista und höheren Versionen des Windows-Betriebssystems starten.</span><span class="sxs-lookup"><span data-stu-id="d6838-150">Additionally, you must start Windows PowerShell by using the Run as administrator option in Windows Vista and later versions of the Windows operating system.</span></span>
<span data-ttu-id="d6838-151">Weitere Informationen finden Sie unter %%amp;quot;about_Remote_Requirements%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="d6838-151">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="d6838-152">Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter about_Jobs und about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="d6838-152">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="d6838-153">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d6838-153">-Authentication</span></span>
<span data-ttu-id="d6838-154">Gibt die Authentifizierungs Ebene an, die für die WMI-Verbindung verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="d6838-154">Specifies the authentication level that must be used with the WMI connection.</span></span>
<span data-ttu-id="d6838-155">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="d6838-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d6838-156">-1: unverändert.</span><span class="sxs-lookup"><span data-stu-id="d6838-156">-1: Unchanged.</span></span>
- <span data-ttu-id="d6838-157">0: Default.</span><span class="sxs-lookup"><span data-stu-id="d6838-157">0: Default.</span></span>
- <span data-ttu-id="d6838-158">1: keine.</span><span class="sxs-lookup"><span data-stu-id="d6838-158">1: None.</span></span>
<span data-ttu-id="d6838-159">Es wird keine Authentifizierung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="d6838-159">No authentication in performed.</span></span>
- <span data-ttu-id="d6838-160">2: verbinden.</span><span class="sxs-lookup"><span data-stu-id="d6838-160">2: Connect.</span></span>
<span data-ttu-id="d6838-161">Die Authentifizierung wird nur ausgeführt, wenn der Client eine Beziehung mit der Anwendung herstellt.</span><span class="sxs-lookup"><span data-stu-id="d6838-161">Authentication is performed only when the client establishes a relationship with the application.</span></span>
- <span data-ttu-id="d6838-162">3: wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d6838-162">3: Call.</span></span>
<span data-ttu-id="d6838-163">Die Authentifizierung wird nur zu Beginn jedes Aufrufes ausgeführt, wenn die Anwendung die Anforderung empfängt.</span><span class="sxs-lookup"><span data-stu-id="d6838-163">Authentication is performed only at the start of each call when the application receives the request.</span></span>
- <span data-ttu-id="d6838-164">4: Paket.</span><span class="sxs-lookup"><span data-stu-id="d6838-164">4: Packet.</span></span>
<span data-ttu-id="d6838-165">Die Authentifizierung wird für alle Daten ausgeführt, die vom Client empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="d6838-165">Authentication is performed on all the data that is received from the client.</span></span>
- <span data-ttu-id="d6838-166">5: packetintegrity.</span><span class="sxs-lookup"><span data-stu-id="d6838-166">5: PacketIntegrity.</span></span>
<span data-ttu-id="d6838-167">Alle Daten, die zwischen dem Client und der Anwendung übertragen werden, werden authentifiziert und überprüft.</span><span class="sxs-lookup"><span data-stu-id="d6838-167">All the data that is transferred between the client and the application is authenticated and verified.</span></span>
- <span data-ttu-id="d6838-168">6: PacketPrivacy.</span><span class="sxs-lookup"><span data-stu-id="d6838-168">6: PacketPrivacy.</span></span>
<span data-ttu-id="d6838-169">Die Eigenschaften der anderen Authentifizierungs Ebenen werden verwendet, und alle Daten werden verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="d6838-169">The properties of the other authentication levels are used, and all the data is encrypted.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-170">-Autorität</span><span class="sxs-lookup"><span data-stu-id="d6838-170">-Authority</span></span>
<span data-ttu-id="d6838-171">Gibt die Autorität an, die zum Authentifizieren der WMI-Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6838-171">Specifies the authority to use to authenticate the WMI connection.</span></span>
<span data-ttu-id="d6838-172">Sie können die Standard-NTLM- oder Kerberos-Authentifizierung angeben.</span><span class="sxs-lookup"><span data-stu-id="d6838-172">You can specify standard NTLM or Kerberos authentication.</span></span>
<span data-ttu-id="d6838-173">Legen Sie für die Verwendung von NTLM die Authority-Einstellung auf %%amp;quot;ntlmdomain:\<DomainName\>%%amp;quot; fest, wobei \<DomainName\> einen gültigen NTLM-Domänennamen darstellt.</span><span class="sxs-lookup"><span data-stu-id="d6838-173">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span>
<span data-ttu-id="d6838-174">Wenn Sie Kerberos verwenden möchten, geben Sie Kerberos: an \<DomainName\> \\ \<ServerName\> .</span><span class="sxs-lookup"><span data-stu-id="d6838-174">To use Kerberos, specify kerberos:\<DomainName\>\\\<ServerName\>.</span></span>
<span data-ttu-id="d6838-175">Sie können die Authority-Einstellung nicht einschließen, wenn Sie eine Verbindung mit dem lokalen Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="d6838-175">You cannot include the authority setting when you connect to the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-176">-Klasse</span><span class="sxs-lookup"><span data-stu-id="d6838-176">-Class</span></span>
<span data-ttu-id="d6838-177">Gibt den Namen einer WMI-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="d6838-177">Specifies the name of a WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-178">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d6838-178">-ComputerName</span></span>
<span data-ttu-id="d6838-179">Gibt den Namen des Computers an, auf dem dieses Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6838-179">Specifies the name of the computer on which this cmdlet runs.</span></span>
<span data-ttu-id="d6838-180">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="d6838-180">The default is the local computer.</span></span>

<span data-ttu-id="d6838-181">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer ein.</span><span class="sxs-lookup"><span data-stu-id="d6838-181">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span>
<span data-ttu-id="d6838-182">Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6838-182">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="d6838-183">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="d6838-183">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="d6838-184">Sie können den *ComputerName* -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d6838-184">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-185">-Credential</span><span class="sxs-lookup"><span data-stu-id="d6838-185">-Credential</span></span>
<span data-ttu-id="d6838-186">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="d6838-186">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="d6838-187">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d6838-187">The default is the current user.</span></span>

<span data-ttu-id="d6838-188">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. das vom Cmdlet Get-Credential generierte.</span><span class="sxs-lookup"><span data-stu-id="d6838-188">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="d6838-189">Wenn Sie einen Benutzernamen eingeben, fordert dieses Cmdlet zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="d6838-189">If you type a user name, this cmdlet prompts for a password.</span></span>

<span data-ttu-id="d6838-190">Dieser Parameter wird nicht von Anbietern unterstützt, die mit dem-Parameter installiert werden, wird von keinen mit Windows PowerShell installierten Anbietern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d6838-190">This parameter is not supported by any providers installed with parameter is not supported by any providers installed with Windows PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-191">-Enableallprivileges</span><span class="sxs-lookup"><span data-stu-id="d6838-191">-EnableAllPrivileges</span></span>
<span data-ttu-id="d6838-192">Gibt an, dass dieses Cmdlet alle Berechtigungen des aktuellen Benutzers vor dem Befehl aktiviert, den der WMI aufruft.</span><span class="sxs-lookup"><span data-stu-id="d6838-192">Indicates that this cmdlet enables all the permissions of the current user before the command it makes the WMI call.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-193">-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="d6838-193">-Impersonation</span></span>
<span data-ttu-id="d6838-194">Gibt die zu verwendende Identitätswechselebene an.</span><span class="sxs-lookup"><span data-stu-id="d6838-194">Specifies the impersonation level to use.</span></span>
<span data-ttu-id="d6838-195">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="d6838-195">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d6838-196">0: Default.</span><span class="sxs-lookup"><span data-stu-id="d6838-196">0: Default.</span></span>
<span data-ttu-id="d6838-197">Liest die lokale Registrierung für die standardmäßige Identitätswechsel Ebene, die normalerweise auf 3 festgelegt ist: Identität annehmen.</span><span class="sxs-lookup"><span data-stu-id="d6838-197">Reads the local registry for the default impersonation level, which is usually set to 3: Impersonate.</span></span>
- <span data-ttu-id="d6838-198">1: Anonymous.</span><span class="sxs-lookup"><span data-stu-id="d6838-198">1: Anonymous.</span></span>
<span data-ttu-id="d6838-199">Verbirgt die Anmeldeinformationen des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="d6838-199">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="d6838-200">2: Identify.</span><span class="sxs-lookup"><span data-stu-id="d6838-200">2: Identify.</span></span>
<span data-ttu-id="d6838-201">Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers abzufragen.</span><span class="sxs-lookup"><span data-stu-id="d6838-201">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="d6838-202">3: Impersonate.</span><span class="sxs-lookup"><span data-stu-id="d6838-202">3: Impersonate.</span></span>
<span data-ttu-id="d6838-203">Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6838-203">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="d6838-204">4: Delegate.</span><span class="sxs-lookup"><span data-stu-id="d6838-204">4: Delegate.</span></span>
<span data-ttu-id="d6838-205">Ermöglicht es Objekten, anderen Objekten die Verwendung der Anmeldeinformationen des Aufrufers zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="d6838-205">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-206">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d6838-206">-InputObject</span></span>
<span data-ttu-id="d6838-207">Gibt ein **ManagementObject** -Objekt an, das als Eingabe verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6838-207">Specifies a **ManagementObject** object to use as input.</span></span>
<span data-ttu-id="d6838-208">Wenn dieser Parameter verwendet wird, werden alle anderen Parameter Außer dem *Arguments* -Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d6838-208">When this parameter is used, all other parameters ,except the *Arguments* parameter, are ignored.</span></span>

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-209">-Gebiets Schema</span><span class="sxs-lookup"><span data-stu-id="d6838-209">-Locale</span></span>
<span data-ttu-id="d6838-210">Gibt das bevorzugte Gebietsschema für WMI-Objekte an.</span><span class="sxs-lookup"><span data-stu-id="d6838-210">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="d6838-211">Der *locale* -Parameter wird in einem Array im MS_ \<LCID\> Format in der bevorzugten Reihenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="d6838-211">The *Locale* parameter is specified in an array in the MS_\<LCID\> format in the preferred order.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-212">-Namespace</span><span class="sxs-lookup"><span data-stu-id="d6838-212">-Namespace</span></span>
<span data-ttu-id="d6838-213">Gibt den WMI-Repository-Namespace an, in dem sich die referenzierte WMI-Klasse befindet, wenn Sie mit dem *Class* -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d6838-213">Specifies the WMI repository namespace where the referenced WMI class is located when it is used with the *Class* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-214">-Path</span><span class="sxs-lookup"><span data-stu-id="d6838-214">-Path</span></span>
<span data-ttu-id="d6838-215">Gibt einen WMI-Objekt Pfad der Instanz an, die Sie erstellen oder aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d6838-215">Specifies a WMI object path of the instance that you want to create or update.</span></span>

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-216">-PutType</span><span class="sxs-lookup"><span data-stu-id="d6838-216">-PutType</span></span>
<span data-ttu-id="d6838-217">Gibt an, ob die WMI-Instanz erstellt oder aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6838-217">Indicates whether to create or update the WMI instance.</span></span>
<span data-ttu-id="d6838-218">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="d6838-218">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d6838-219">UpdateOnly.</span><span class="sxs-lookup"><span data-stu-id="d6838-219">UpdateOnly.</span></span>
<span data-ttu-id="d6838-220">Aktualisiert eine vorhandene WMI-Instanz.</span><span class="sxs-lookup"><span data-stu-id="d6838-220">Updates an existing WMI instance.</span></span>
- <span data-ttu-id="d6838-221">CreateOnly.</span><span class="sxs-lookup"><span data-stu-id="d6838-221">CreateOnly.</span></span>
<span data-ttu-id="d6838-222">Erstellt eine neue WMI-Instanz.</span><span class="sxs-lookup"><span data-stu-id="d6838-222">Creates a new WMI instance.</span></span>
- <span data-ttu-id="d6838-223">UpdateOrCreate.</span><span class="sxs-lookup"><span data-stu-id="d6838-223">UpdateOrCreate.</span></span>
<span data-ttu-id="d6838-224">Aktualisiert die WMI-Instanz, sofern vorhanden, oder erstellt eine neue Instanz, wenn keine Instanz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d6838-224">Updates the WMI instance if it exists or creates a new instance if an instance does not exist.</span></span>

```yaml
Type: System.Management.PutType
Parameter Sets: (All)
Aliases:
Accepted values: None, UpdateOnly, CreateOnly, UpdateOrCreate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6838-225">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d6838-225">-ThrottleLimit</span></span>
<span data-ttu-id="d6838-226">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="d6838-226">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="d6838-227">Dieser Parameter wird in Verbindung mit dem *AsJob* -Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6838-227">This parameter is used together with the *AsJob* parameter.</span></span>
<span data-ttu-id="d6838-228">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="d6838-228">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="d6838-229">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d6838-229">-Confirm</span></span>
<span data-ttu-id="d6838-230">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d6838-230">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d6838-231">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d6838-231">-WhatIf</span></span>
<span data-ttu-id="d6838-232">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6838-232">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d6838-233">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d6838-233">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d6838-234">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d6838-234">CommonParameters</span></span>
<span data-ttu-id="d6838-235">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d6838-235">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d6838-236">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d6838-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d6838-237">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d6838-237">INPUTS</span></span>

### <span data-ttu-id="d6838-238">Keine</span><span class="sxs-lookup"><span data-stu-id="d6838-238">None</span></span>
<span data-ttu-id="d6838-239">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="d6838-239">This cmdlet does not accept input.</span></span>

## <span data-ttu-id="d6838-240">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d6838-240">OUTPUTS</span></span>

### <span data-ttu-id="d6838-241">Keine</span><span class="sxs-lookup"><span data-stu-id="d6838-241">None</span></span>
<span data-ttu-id="d6838-242">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d6838-242">This cmdlet does not generate output.</span></span>

## <span data-ttu-id="d6838-243">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d6838-243">NOTES</span></span>

## <span data-ttu-id="d6838-244">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d6838-244">RELATED LINKS</span></span>

[<span data-ttu-id="d6838-245">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="d6838-245">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="d6838-246">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="d6838-246">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="d6838-247">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="d6838-247">Remove-WmiObject</span></span>](Remove-WmiObject.md)
