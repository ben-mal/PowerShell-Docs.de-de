---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WmiMethod
ms.openlocfilehash: e9743488e86429e5cc3252162e51268a7978b79d
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "93217991"
---
# <span data-ttu-id="39dd2-103">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="39dd2-103">Invoke-WmiMethod</span></span>

## <span data-ttu-id="39dd2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="39dd2-104">SYNOPSIS</span></span>
<span data-ttu-id="39dd2-105">Ruft WMI-Methoden auf.</span><span class="sxs-lookup"><span data-stu-id="39dd2-105">Calls WMI methods.</span></span>

## <span data-ttu-id="39dd2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39dd2-106">SYNTAX</span></span>

### <span data-ttu-id="39dd2-107">Class (Standard)</span><span class="sxs-lookup"><span data-stu-id="39dd2-107">class (Default)</span></span>

```
Invoke-WmiMethod [-Class] <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="39dd2-108">Objekt</span><span class="sxs-lookup"><span data-stu-id="39dd2-108">object</span></span>

```
Invoke-WmiMethod -InputObject <ManagementObject> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="39dd2-109">path</span><span class="sxs-lookup"><span data-stu-id="39dd2-109">path</span></span>

```
Invoke-WmiMethod -Path <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="39dd2-110">Wqlquery</span><span class="sxs-lookup"><span data-stu-id="39dd2-110">WQLQuery</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="39dd2-111">Abfrage</span><span class="sxs-lookup"><span data-stu-id="39dd2-111">query</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="39dd2-112">list</span><span class="sxs-lookup"><span data-stu-id="39dd2-112">list</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="39dd2-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="39dd2-113">DESCRIPTION</span></span>

<span data-ttu-id="39dd2-114">Das- `Invoke-WmiMethod` Cmdlet ruft die Methoden von Windows-Verwaltungsinstrumentation (WMI)-Objekten auf.</span><span class="sxs-lookup"><span data-stu-id="39dd2-114">The `Invoke-WmiMethod` cmdlet calls the methods of Windows Management Instrumentation (WMI) objects.</span></span>

<span data-ttu-id="39dd2-115">New Common Information Model (CIM)-Cmdlets, die in Windows PowerShell 3,0 eingeführt wurden, führen dieselben Aufgaben wie die WMI-Cmdlets aus.</span><span class="sxs-lookup"><span data-stu-id="39dd2-115">New Common Information Model (CIM) cmdlets, introduced in Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="39dd2-116">Die CIM-Cmdlets entsprechen den WS-Management (WSMAN)-Standards und dem CIM-Standard, mit dem die Cmdlets die gleichen Techniken zum Verwalten von Windows-Computern und von Computern mit anderen Betriebssystemen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="39dd2-116">The CIM cmdlets comply with WS-Management (WSMan) standards and with the CIM standard, which enables the cmdlets to use the same techniques to manage Windows computers and those running other operating systems.</span></span> <span data-ttu-id="39dd2-117">Verwenden Sie anstelle von die Verwendung von " `Invoke-WmiMethod` [aufrufen-cimmethod](../cimcmdlets/invoke-cimmethod.md)".</span><span class="sxs-lookup"><span data-stu-id="39dd2-117">Instead of using `Invoke-WmiMethod`, consider using [Invoke-CimMethod](../cimcmdlets/invoke-cimmethod.md).</span></span>

## <span data-ttu-id="39dd2-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="39dd2-118">EXAMPLES</span></span>

### <span data-ttu-id="39dd2-119">Beispiel 1: Auflisten der erforderlichen Reihenfolge von WMI-Objekten</span><span class="sxs-lookup"><span data-stu-id="39dd2-119">Example 1: List the required order of WMI objects</span></span>

```powershell
([wmiclass]'Win32_Volume').GetMethodParameters('Format')
```

```Output
__GENUS           : 2
__CLASS           : __PARAMETERS
__SUPERCLASS      :
__DYNASTY         : __PARAMETERS
__RELPATH         :
__PROPERTY_COUNT  : 6
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
ClusterSize       : 0
EnableCompression : False
FileSystem        : NTFS
Label             :
QuickFormat       : False
Version           : 0
PSComputerName    :
```

<span data-ttu-id="39dd2-120">In diesem Befehl ist die erforderliche Reihenfolge der Objekte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="39dd2-120">This command lists the required order of the objects.</span></span> <span data-ttu-id="39dd2-121">Das Aufrufen von WMI in PowerShell 3.0 unterscheidet sich von anderen Methoden. Darüber hinaus müssen Objektwerte in einer bestimmten Reihenfolge eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="39dd2-121">To invoke WMI in PowerShell 3.0 differs from alternate methods, and requires that object values are entered in a specific order.</span></span>

### <span data-ttu-id="39dd2-122">Beispiel 2: Starten einer Instanz einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="39dd2-122">Example 2: Start an instance of an application</span></span>

```powershell
([Wmiclass]'Win32_Process').GetMethodParameters('Create')
```

```Output
__GENUS                   : 2
__CLASS                   : __PARAMETERS
__SUPERCLASS              :
__DYNASTY                 : __PARAMETERS
__RELPATH                 :
__PROPERTY_COUNT          : 3
__DERIVATION              : {}
__SERVER                  :
__NAMESPACE               :
__PATH                    :
CommandLine               :
CurrentDirectory          :
ProcessStartupInformation :
PSComputerName            :
```

```powershell
Invoke-WmiMethod -Path win32_process -Name create -ArgumentList notepad.exe
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 2
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ProcessId        : 11312
ReturnValue      : 0
PSComputerName   :
```

<span data-ttu-id="39dd2-123">Mit diesem Befehl wird eine Instanz von Editor gestartet, indem die- `Create` Methode der **Win32_Process** -Klasse aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="39dd2-123">This command starts an instance of Notepad by calling the `Create` method of the **Win32_Process** class.</span></span>

<span data-ttu-id="39dd2-124">Die **ReturnValue** -Eigenschaft wird mit 0 aufgefüllt, und die **ProcessID-** Eigenschaft wird mit einer ganzen Zahl (der nächsten Prozess-ID-Nummer) aufgefüllt, wenn der Befehl abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="39dd2-124">The **ReturnValue** property is populated with a 0, and the **ProcessId** property is populated with an integer (the next process ID number) if the command is completed.</span></span>

### <span data-ttu-id="39dd2-125">Beispiel 3: Umbenennen einer Datei</span><span class="sxs-lookup"><span data-stu-id="39dd2-125">Example 3: Rename a file</span></span>

```powershell
Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\scripts\test.txt'" -Name Rename -ArgumentList "C:\scripts\test_bu.txt"
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ReturnValue      : 0
```

<span data-ttu-id="39dd2-126">Mit diesem Befehl wird eine Datei umbenannt.</span><span class="sxs-lookup"><span data-stu-id="39dd2-126">This command renames a file.</span></span> <span data-ttu-id="39dd2-127">Er verwendet den **path** -Parameter, um auf eine Instanz der **CIM_Datafile** -Klasse zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="39dd2-127">It uses the **Path** parameter to reference an instance of the **CIM_DataFile** class.</span></span> <span data-ttu-id="39dd2-128">Anschließend wird die Rename-Methode auf die betreffende Instanz angewendet.</span><span class="sxs-lookup"><span data-stu-id="39dd2-128">Then, it applies the Rename method to that particular instance.</span></span>

<span data-ttu-id="39dd2-129">Die **ReturnValue** -Eigenschaft wird mit 0 aufgefüllt, wenn der Befehl abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="39dd2-129">The **ReturnValue** property is populated with a 0 if the command is completed.</span></span>

### <span data-ttu-id="39dd2-130">Beispiel 4: Übergeben eines Arrays von Werten mithilfe von `-ArgumentList`</span><span class="sxs-lookup"><span data-stu-id="39dd2-130">Example 4: Passing an array of values using `-ArgumentList`</span></span>

<span data-ttu-id="39dd2-131">Ein Beispiel mit einem Array von-Objekten, `$binSD` auf das ein- `$null` Wert folgt.</span><span class="sxs-lookup"><span data-stu-id="39dd2-131">An example using an array of objects `$binSD` followed by a `$null` value.</span></span>

```powershell
$acl = get-acl test.txt
$binSD = $acl.GetSecurityDescriptorBinaryForm()
Invoke-WmiMethod -class Win32_SecurityDescriptorHelper -Name BinarySDToSDDL -ArgumentList $binSD, $null
```

## <span data-ttu-id="39dd2-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39dd2-132">PARAMETERS</span></span>

### <span data-ttu-id="39dd2-133">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="39dd2-133">-ArgumentList</span></span>

<span data-ttu-id="39dd2-134">Gibt die Parameter an, die an die aufgerufene Methode übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="39dd2-134">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="39dd2-135">Der Wert dieses Parameters muss ein Array von-Objekten sein, und Sie müssen in der Reihenfolge angezeigt werden, die von der aufgerufenen Methode benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="39dd2-135">The value of this parameter must be an array of objects, and they must appear in the order required by the called method.</span></span> <span data-ttu-id="39dd2-136">Für das `Invoke-CimCommand` Cmdlet gelten diese Einschränkungen nicht.</span><span class="sxs-lookup"><span data-stu-id="39dd2-136">The `Invoke-CimCommand` cmdlet does not have these limitations.</span></span>

<span data-ttu-id="39dd2-137">Um die Reihenfolge zu bestimmen, in der diese Objekte aufgeführt werden sollen, führen Sie die- `GetMethodParameters()` Methode für die WMI-Klasse aus, wie in Beispiel 1 am Ende dieses Themas veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="39dd2-137">To determine the order in which to list those objects, run the `GetMethodParameters()` method on the WMI class, as illustrated in Example 1, near the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39dd2-138">Handelt es sich beim ersten Wert um ein Array, das mehrere Elemente enthält, ist der zweite Wert $null erforderlich.</span><span class="sxs-lookup"><span data-stu-id="39dd2-138">If the first value is an array that contains more than one element, a second value of $null is required.</span></span> <span data-ttu-id="39dd2-139">Andernfalls wird vom Befehl ein Fehler generiert, z. B. %%amp;quot;Das Objekt des Typs "System.Byte" kann nicht in Typ "System.Array" umgewandelt werden.%%amp;quot;</span><span class="sxs-lookup"><span data-stu-id="39dd2-139">Otherwise, the command generates an error, such as "Unable to cast object of type 'System.Byte' to type 'System.Array'.".</span></span> <span data-ttu-id="39dd2-140">Siehe Beispiel 4 oben.</span><span class="sxs-lookup"><span data-stu-id="39dd2-140">See example 4 above.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: class, object, path
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39dd2-141">-AsJob</span><span class="sxs-lookup"><span data-stu-id="39dd2-141">-AsJob</span></span>

<span data-ttu-id="39dd2-142">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="39dd2-142">Indicates that this cmdlet runs the command as a background job.</span></span> <span data-ttu-id="39dd2-143">Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="39dd2-143">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="39dd2-144">Wenn Sie den **AsJob** -Parameter verwenden, gibt der Befehl ein Objekt zurück, das den Hintergrundauftrag darstellt, und zeigt dann die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="39dd2-144">When you use the **AsJob** parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span> <span data-ttu-id="39dd2-145">Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="39dd2-145">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="39dd2-146">Wenn für `Invoke-WmiMethod` einen Remote Computer verwendet wird, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse von Remote Computern werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="39dd2-146">If `Invoke-WmiMethod` is used against a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="39dd2-147">Verwenden Sie zum Verwalten des Auftrags die Cmdlets, die das Substantiv %%amp;quot;Job%%amp;quot; enthalten (die Job-Cmdlets).</span><span class="sxs-lookup"><span data-stu-id="39dd2-147">To manage the job, use the cmdlets that contain the Job noun (the Job cmdlets).</span></span> <span data-ttu-id="39dd2-148">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="39dd2-148">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="39dd2-149">Um diesen Parameter für Remotecomputer zu verwenden, müssen lokale Computer und Remotecomputer für Remoting konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="39dd2-149">To use this parameter with remote computers, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="39dd2-150">Außerdem müssen Sie Windows PowerShell starten, indem Sie die Option als Administrator ausführen in Windows Vista und höheren Versionen von Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="39dd2-150">Additionally, you must start Windows PowerShell by using the Run as administrator option in Windows Vista and later versions of Windows.</span></span> <span data-ttu-id="39dd2-151">Weitere Informationen finden Sie unter %%amp;quot;about_Remote_Requirements%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="39dd2-151">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="39dd2-152">Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter about_Jobs und about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="39dd2-152">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="39dd2-153">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="39dd2-153">-Authentication</span></span>

<span data-ttu-id="39dd2-154">Gibt die für die WMI-Verbindung zu verwendende Authentifizierungsebene an.</span><span class="sxs-lookup"><span data-stu-id="39dd2-154">Specifies the authentication level to be used with the WMI connection.</span></span> <span data-ttu-id="39dd2-155">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="39dd2-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="39dd2-156">-1: Unchanged</span><span class="sxs-lookup"><span data-stu-id="39dd2-156">-1: Unchanged</span></span>
- <span data-ttu-id="39dd2-157">0: Default</span><span class="sxs-lookup"><span data-stu-id="39dd2-157">0: Default</span></span>
- <span data-ttu-id="39dd2-158">1: None (Es wird keine Authentifizierung ausgeführt.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-158">1: None (No authentication in performed.)</span></span>
- <span data-ttu-id="39dd2-159">2: Connect (Die Authentifizierung wird nur ausgeführt, wenn der Client eine Beziehung mit der Anwendung herstellt.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-159">2: Connect (Authentication is performed only when the client establishes a relationship with the application.)</span></span>
- <span data-ttu-id="39dd2-160">3: Call (Die Authentifizierung wird nur zu Beginn eines Aufrufs ausgeführt, wenn die Anwendung die Anforderung empfängt.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-160">3: Call (Authentication is performed only at the beginning of each call when the application receives the request.)</span></span>
- <span data-ttu-id="39dd2-161">4: Packet (Die Authentifizierung wird für alle Daten ausgeführt, die vom Client empfangen werden.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-161">4: Packet (Authentication is performed on all the data that is received from the client.)</span></span>
- <span data-ttu-id="39dd2-162">5: packetintegrity (alle Daten, die zwischen dem Client und der Anwendung übertragen werden, werden authentifiziert und überprüft.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-162">5: PacketIntegrity (All the data that is transferred between the client and the application is authenticated and verified.)</span></span>
- <span data-ttu-id="39dd2-163">6: PacketPrivacy (Die Eigenschaften der anderen Authentifizierungsebenen werden verwendet, und alle Daten werden verschlüsselt.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-163">6: PacketPrivacy (The properties of the other authentication levels are used, and all the data is encrypted.)</span></span>

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

### <span data-ttu-id="39dd2-164">-Autorität</span><span class="sxs-lookup"><span data-stu-id="39dd2-164">-Authority</span></span>

<span data-ttu-id="39dd2-165">Gibt die Autorität an, die zum Authentifizieren der WMI-Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="39dd2-165">Specifies the authority to use to authenticate the WMI connection.</span></span> <span data-ttu-id="39dd2-166">Sie können die standardmäßige NTLM (Windows NT LAN Manager)-oder Kerberos-Authentifizierung angeben.</span><span class="sxs-lookup"><span data-stu-id="39dd2-166">You can specify standard Windows NT LAN Manager (NTLM) or Kerberos authentication.</span></span> <span data-ttu-id="39dd2-167">Legen Sie für die Verwendung von NTLM die Authority-Einstellung auf %%amp;quot;ntlmdomain:\<DomainName\>%%amp;quot; fest, wobei \<DomainName\> einen gültigen NTLM-Domänennamen darstellt.</span><span class="sxs-lookup"><span data-stu-id="39dd2-167">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span> <span data-ttu-id="39dd2-168">Geben Sie für die Verwendung von Kerberos %%amp;quot;kerberos:\<DomainName\ServerName\>%%amp;quot; an.</span><span class="sxs-lookup"><span data-stu-id="39dd2-168">To use Kerberos, specify kerberos:\<DomainName\ServerName\>.</span></span> <span data-ttu-id="39dd2-169">Sie können die Authority-Einstellung nicht einschließen, wenn Sie eine Verbindung mit dem lokalen Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="39dd2-169">You cannot include the authority setting when you connect to the local computer.</span></span>

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

### <span data-ttu-id="39dd2-170">-Klasse</span><span class="sxs-lookup"><span data-stu-id="39dd2-170">-Class</span></span>

<span data-ttu-id="39dd2-171">Gibt die WMI-Klasse an, die eine aufzurufende statische Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="39dd2-171">Specifies the WMI class that contains a static method to call.</span></span>

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

### <span data-ttu-id="39dd2-172">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="39dd2-172">-ComputerName</span></span>

<span data-ttu-id="39dd2-173">Gibt die Computer, auf denen dieses Cmdlet den Befehl ausführt, als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="39dd2-173">Specifies, as a string array, the computers that this cmdlet runs the command on.</span></span> <span data-ttu-id="39dd2-174">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="39dd2-174">The default is the local computer.</span></span>

<span data-ttu-id="39dd2-175">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer ein.</span><span class="sxs-lookup"><span data-stu-id="39dd2-175">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span> <span data-ttu-id="39dd2-176">Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="39dd2-176">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="39dd2-177">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="39dd2-177">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="39dd2-178">Sie können den **ComputerName** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="39dd2-178">You can use the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="39dd2-179">-Credential</span><span class="sxs-lookup"><span data-stu-id="39dd2-179">-Credential</span></span>

<span data-ttu-id="39dd2-180">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="39dd2-180">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="39dd2-181">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="39dd2-181">The default is the current user.</span></span> <span data-ttu-id="39dd2-182">Geben Sie einen Benutzernamen ein, `User01` z `Domain01\User01` . b `User@Contoso.com` ., oder.</span><span class="sxs-lookup"><span data-stu-id="39dd2-182">Type a user name, such as `User01`, `Domain01\User01`, or `User@Contoso.com`.</span></span> <span data-ttu-id="39dd2-183">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein Objekt, das vom Get-Credential-Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="39dd2-183">Or, enter a **PSCredential** object, such as an object that is returned by the Get-Credential cmdlet.</span></span> <span data-ttu-id="39dd2-184">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="39dd2-184">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="39dd2-185">-Enableallprivileges</span><span class="sxs-lookup"><span data-stu-id="39dd2-185">-EnableAllPrivileges</span></span>

<span data-ttu-id="39dd2-186">Gibt an, dass dieses Cmdlet alle Berechtigungen des aktuellen Benutzers aktiviert, bevor der Befehl den WMI-Aufrufe ausführt.</span><span class="sxs-lookup"><span data-stu-id="39dd2-186">Indicates that this cmdlet enables all the privileges of the current user before the command makes the WMI call.</span></span>

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

### <span data-ttu-id="39dd2-187">-Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="39dd2-187">-Impersonation</span></span>

<span data-ttu-id="39dd2-188">Gibt die zu verwendende Identitätswechselebene an.</span><span class="sxs-lookup"><span data-stu-id="39dd2-188">Specifies the impersonation level to use.</span></span> <span data-ttu-id="39dd2-189">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="39dd2-189">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="39dd2-190">0: Default (Liest die lokale Registrierung für die Standard-Identitätswechselebene, die normalerweise auf %%amp;quot;3: Impersonate%%amp;quot; festgelegt ist.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-190">0: Default (Reads the local registry for the default impersonation level, which is usually set to "3: Impersonate".)</span></span>
- <span data-ttu-id="39dd2-191">1: Anonymous (Verbirgt die Anmeldeinformationen des Aufrufers.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-191">1: Anonymous (Hides the credentials of the caller.)</span></span>
- <span data-ttu-id="39dd2-192">2: Identify (Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers abzufragen.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-192">2: Identify (Allows objects to query the credentials of the caller.)</span></span>
- <span data-ttu-id="39dd2-193">3: Impersonate (Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers zu verwenden.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-193">3: Impersonate (Allows objects to use the credentials of the caller.)</span></span>
- <span data-ttu-id="39dd2-194">4: Delegate (Ermöglicht es Objekten, anderen Objekten die Verwendung der Anmeldeinformationen des Aufrufers zu gestatten.)</span><span class="sxs-lookup"><span data-stu-id="39dd2-194">4: Delegate (Allows objects to permit other objects to use the credentials of the caller.)</span></span>

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

### <span data-ttu-id="39dd2-195">-InputObject</span><span class="sxs-lookup"><span data-stu-id="39dd2-195">-InputObject</span></span>

<span data-ttu-id="39dd2-196">Gibt ein **ManagementObject** -Objekt an, das als Eingabe verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="39dd2-196">Specifies a **ManagementObject** object to use as input.</span></span> <span data-ttu-id="39dd2-197">Wenn dieser Parameter verwendet wird, werden alle anderen Parameter Außer dem **Flag** und den **Argument** Parametern ignoriert.</span><span class="sxs-lookup"><span data-stu-id="39dd2-197">When this parameter is used, all other parameters except the **Flag** and **Argument** parameters are ignored.</span></span>

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

### <span data-ttu-id="39dd2-198">-Gebiets Schema</span><span class="sxs-lookup"><span data-stu-id="39dd2-198">-Locale</span></span>

<span data-ttu-id="39dd2-199">Gibt das bevorzugte Gebietsschema für WMI-Objekte an.</span><span class="sxs-lookup"><span data-stu-id="39dd2-199">Specifies the preferred locale for WMI objects.</span></span> <span data-ttu-id="39dd2-200">Geben Sie den Wert des **locale** -Parameters als Array im `MS_<LCID>` Format in der bevorzugten Reihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="39dd2-200">Specify the value of the **Locale** parameter as an array in the `MS_<LCID>` format in the preferred order.</span></span>

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

### <span data-ttu-id="39dd2-201">-Name</span><span class="sxs-lookup"><span data-stu-id="39dd2-201">-Name</span></span>

<span data-ttu-id="39dd2-202">Gibt den Namen der aufzurufenden Methode an.</span><span class="sxs-lookup"><span data-stu-id="39dd2-202">Specifies the name of the method to be invoked.</span></span> <span data-ttu-id="39dd2-203">Dieser Parameter ist erforderlich und kann nicht NULL oder leer sein.</span><span class="sxs-lookup"><span data-stu-id="39dd2-203">This parameter is mandatory and cannot be null or empty.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39dd2-204">-Namespace</span><span class="sxs-lookup"><span data-stu-id="39dd2-204">-Namespace</span></span>

<span data-ttu-id="39dd2-205">Bei Verwendung mit dem **Class** -Parameter gibt dieser Parameter den WMI-Repository-Namespace an, in dem sich die WMI-Klasse oder das referenzierte Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="39dd2-205">When used with the **Class** parameter, this parameter specifies the WMI repository namespace where the referenced WMI class or object is located.</span></span>

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

### <span data-ttu-id="39dd2-206">-Path</span><span class="sxs-lookup"><span data-stu-id="39dd2-206">-Path</span></span>

<span data-ttu-id="39dd2-207">Gibt den WMI-Objektpfad einer WMI-Klasse oder den WMI-Objektpfad einer Instanz einer WMI-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="39dd2-207">Specifies the WMI object path of a WMI class, or specifies the WMI object path of an instance of a WMI class.</span></span> <span data-ttu-id="39dd2-208">Die Klasse oder die Instanz, die Sie angeben, muss die im **Name** -Parameter angegebene Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="39dd2-208">The class or the instance that you specify must contain the method that is specified in the **Name** parameter.</span></span>

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

### <span data-ttu-id="39dd2-209">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="39dd2-209">-ThrottleLimit</span></span>

<span data-ttu-id="39dd2-210">Gibt einen Drosselungs Wert für die Anzahl der WMI-Vorgänge an, die gleichzeitig ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="39dd2-210">Specifies a throttle value for the number of WMI operations that can be executed simultaneously.</span></span>
<span data-ttu-id="39dd2-211">Dieser Parameter wird in Verbindung mit dem **AsJob** -Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="39dd2-211">This parameter is used together with the **AsJob** parameter.</span></span> <span data-ttu-id="39dd2-212">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="39dd2-212">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="39dd2-213">-Confirm</span><span class="sxs-lookup"><span data-stu-id="39dd2-213">-Confirm</span></span>

<span data-ttu-id="39dd2-214">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="39dd2-214">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="39dd2-215">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="39dd2-215">-WhatIf</span></span>

<span data-ttu-id="39dd2-216">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="39dd2-216">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="39dd2-217">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="39dd2-217">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="39dd2-218">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="39dd2-218">CommonParameters</span></span>

<span data-ttu-id="39dd2-219">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="39dd2-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39dd2-220">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="39dd2-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="39dd2-221">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="39dd2-221">INPUTS</span></span>

### <span data-ttu-id="39dd2-222">Keine</span><span class="sxs-lookup"><span data-stu-id="39dd2-222">None</span></span>

<span data-ttu-id="39dd2-223">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="39dd2-223">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="39dd2-224">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="39dd2-224">OUTPUTS</span></span>

### <span data-ttu-id="39dd2-225">Keine</span><span class="sxs-lookup"><span data-stu-id="39dd2-225">None</span></span>

<span data-ttu-id="39dd2-226">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="39dd2-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="39dd2-227">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="39dd2-227">NOTES</span></span>

## <span data-ttu-id="39dd2-228">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="39dd2-228">RELATED LINKS</span></span>

[<span data-ttu-id="39dd2-229">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="39dd2-229">Get-WSManInstance</span></span>](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[<span data-ttu-id="39dd2-230">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="39dd2-230">Invoke-WSManAction</span></span>](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[<span data-ttu-id="39dd2-231">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="39dd2-231">New-WSManInstance</span></span>](../Microsoft.WsMan.Management/New-WSManInstance.md)

[<span data-ttu-id="39dd2-232">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="39dd2-232">Remove-WSManInstance</span></span>](../Microsoft.WsMan.Management/Remove-WSManInstance.md)

[<span data-ttu-id="39dd2-233">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="39dd2-233">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="39dd2-234">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="39dd2-234">Remove-WmiObject</span></span>](Remove-WmiObject.md)

[<span data-ttu-id="39dd2-235">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="39dd2-235">Set-WmiInstance</span></span>](Set-WmiInstance.md)
