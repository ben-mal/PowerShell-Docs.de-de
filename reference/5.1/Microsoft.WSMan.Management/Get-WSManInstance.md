---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmaninstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManInstance
ms.openlocfilehash: c60d17631d0603e4285c34b91dd0971e4e358af0
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224807"
---
# <span data-ttu-id="22d49-103">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="22d49-103">Get-WSManInstance</span></span>

## <span data-ttu-id="22d49-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="22d49-104">SYNOPSIS</span></span>
<span data-ttu-id="22d49-105">Zeigt Verwaltungsinformationen für eine durch einen Ressourcen-URI angegebene Ressourceninstanz an.</span><span class="sxs-lookup"><span data-stu-id="22d49-105">Displays management information for a resource instance specified by a Resource URI.</span></span>

## <span data-ttu-id="22d49-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="22d49-106">SYNTAX</span></span>

### <span data-ttu-id="22d49-107">GetInstance (Standard)</span><span class="sxs-lookup"><span data-stu-id="22d49-107">GetInstance (Default)</span></span>

```
Get-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-ConnectionURI <Uri>] [-Dialect <Uri>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet <Hashtable>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="22d49-108">Aufzählen</span><span class="sxs-lookup"><span data-stu-id="22d49-108">Enumerate</span></span>

```
Get-WSManInstance [-ApplicationName <String>] [-BasePropertiesOnly] [-ComputerName <String>]
 [-ConnectionURI <Uri>] [-Dialect <Uri>] [-Enumerate] [-Filter <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-Associations] [-ResourceURI] <Uri> [-ReturnType <String>] [-SessionOption <SessionOption>]
 [-Shallow] [-UseSSL] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="22d49-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="22d49-109">DESCRIPTION</span></span>
<span data-ttu-id="22d49-110">Das **Get-wsmaninstance** -Cmdlet ruft eine Instanz einer Verwaltungs Ressource ab, die durch eine Ressourcen Uniform Resource Identifier (URI) angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="22d49-110">The **Get-WSManInstance** cmdlet retrieves an instance of a management resource that is specified by a resource Uniform Resource Identifier (URI).</span></span>
<span data-ttu-id="22d49-111">Bei den abgerufenen Informationen kann es sich um einen komplexen XML-Informations Satz handeln, bei dem es sich um ein Objekt oder einen einfachen Wert handelt.</span><span class="sxs-lookup"><span data-stu-id="22d49-111">The information that is retrieved can be a complex XML information set, which is an object, or a simple value.</span></span>
<span data-ttu-id="22d49-112">Dieses Cmdlet entspricht dem standardmäßigen Web Services for Management (WS-Management) **Get** -Befehl.</span><span class="sxs-lookup"><span data-stu-id="22d49-112">This cmdlet is the equivalent to the standard Web Services for Management (WS-Management) **Get** command.</span></span>

<span data-ttu-id="22d49-113">Das Cmdlet verwendet die Verbindungs-/Transportschicht von WS-Management zum Abrufen von Informationen.</span><span class="sxs-lookup"><span data-stu-id="22d49-113">This cmdlet uses the WS-Management connection/transport layer to retrieve information.</span></span>

## <span data-ttu-id="22d49-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="22d49-114">EXAMPLES</span></span>

### <span data-ttu-id="22d49-115">Beispiel 1: alle Informationen aus WMI</span><span class="sxs-lookup"><span data-stu-id="22d49-115">Example 1: Get all information from WMI</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI wmicimv2/win32_service -SelectorSet @{name="winrm"} -ComputerName "Server01"
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : true
Caption                 : Windows Remote Management (WS-Management)
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Windows Remote Management (WinRM) service implements the WS-Management protocol for remote
management. WS-Management is a standard web services protocol used for remote software and
hardware management. The WinRM service listens on the network for WS-Management requests
and processes them. The WinRM Service needs to be configured with a listener using the
winrm.cmd command line tool or through Group Policy in order for it to listen over the
network. The WinRM service provides access to WMI data and enables event collection. Event
collection and subscription to events require that the service is running. WinRM messages
use HTTP and HTTPS as transports. The WinRM service does not depend on IIS but is
preconfigured to share a port with IIS on the same computer.  The WinRM service reserves the
/wsman URL prefix. To prevent conflicts with IIS, administrators should ensure that any
websites hosted on IIS do not use the /wsman URL prefix.
DesktopInteract         : false
DisplayName             : Windows Remote Management (WS-Management)
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : winrm
PathName                : C:\Windows\System32\svchost.exe -k NetworkService
ProcessId               : 948
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : true
StartMode               : Auto
StartName               : NT AUTHORITY\NetworkService
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
WaitHint                : 0
```

<span data-ttu-id="22d49-116">Mit diesem Befehl werden alle Informationen zurückgegeben, die Windows-Verwaltungsinstrumentation (WMI) über den **WinRM** -Dienst auf dem Remote Computer mit Server01 verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="22d49-116">This command returns all of the information that Windows Management Instrumentation (WMI) exposes about the **WinRM** service on the remote server01 computer.</span></span>

### <span data-ttu-id="22d49-117">Beispiel 2: erhalten des Status des Spoolerdiensts</span><span class="sxs-lookup"><span data-stu-id="22d49-117">Example 2: Get the status of the Spooler service</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI wmicimv2/win32_service -SelectorSet @{name="spooler"} -Fragment Status -ComputerName "Server01"
XmlFragment=OK
```

<span data-ttu-id="22d49-118">Mit diesem Befehl wird nur der Status des **Spoolerdiensts** auf dem Remote Computer "Server01" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="22d49-118">This command returns only the status of the **Spooler** service on the remote server01 computer.</span></span>

### <span data-ttu-id="22d49-119">Beispiel 3: Endpunkt Verweise für alle Dienste erhalten</span><span class="sxs-lookup"><span data-stu-id="22d49-119">Example 3: Get endpoint references for all services</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -ResourceURI wmicimv2/win32_service -ReturnType EPR
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Visual Studio 2008 Remote Debugger
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Allows members of the Administrators group to remotely debug server applications using Visual
Studio 2008. Use the Visual Studio 2008 Remote Debugging Configuration Wizard to enable this
service.
DesktopInteract         : false
DisplayName             : Visual Studio 2008 Remote Debugger
ErrorControl            : Ignore
ExitCode                : 1077
InstallDate             : InstallDate
Name                    : msvsmon90
PathName                : "C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\Remote Debugger\x86\msvsmon.exe" /service msvsmon90
ProcessId               : 0
ServiceSpecificExitCode : 0
ServiceType             : Own Process
Started                 : false
StartMode               : Disabled
StartName               : LocalSystem
State                   : Stopped
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : COMPUTER01
TagId                   : 0
WaitHint                : 0
...
```

<span data-ttu-id="22d49-120">Dieser Befehl gibt Endpunktverweise zurück, die allen Diensten auf dem lokalen Computer entsprechen.</span><span class="sxs-lookup"><span data-stu-id="22d49-120">This command returns endpoint references that correspond to all the services on the local computer.</span></span>

### <span data-ttu-id="22d49-121">Beispiel 4: erhalten von Diensten, die bestimmte Kriterien erfüllen</span><span class="sxs-lookup"><span data-stu-id="22d49-121">Example 4: Get services that meet specified criteria</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -ResourceURI wmicimv2/* -Filter "select * from win32_service where StartMode = 'Auto' and State = 'Stopped'" -ComputerName "Server01"
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Windows Media Center Service Launcher
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Starts Windows Media Center Scheduler and Windows Media Center Receiver services
at startup if TV is enabled within Windows Media Center.
DesktopInteract         : false
DisplayName             : Windows Media Center Service Launcher
ErrorControl            : Ignore
ExitCode                : 0
InstallDate             : InstallDate
Name                    : ehstart
PathName                : C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork
ProcessId               : 0
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : false
StartMode               : Auto
StartName               : NT AUTHORITY\LocalService
State                   : Stopped
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : Server01
TagId                   : 0
WaitHint                : 0
...
```

<span data-ttu-id="22d49-122">Mit diesem Befehl werden alle Dienste aufgelistet, die die folgenden Kriterien auf dem Remote Computer mit Server01 erfüllen:</span><span class="sxs-lookup"><span data-stu-id="22d49-122">This command lists all of the services that meet the following criteria on the remote Server01 computer:</span></span>

- <span data-ttu-id="22d49-123">Der Starttyp des Dienstanbieter ist "automatisch".</span><span class="sxs-lookup"><span data-stu-id="22d49-123">The startup type of the service is Automatic.</span></span>
- <span data-ttu-id="22d49-124">Der -Dienst wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="22d49-124">The service is stopped.</span></span>

### <span data-ttu-id="22d49-125">Beispiel 5: Get Listener Configuration, die den Kriterien auf dem lokalen Computer entspricht</span><span class="sxs-lookup"><span data-stu-id="22d49-125">Example 5: Get listener configuration that matches criteria on the local computer</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{Address="*";Transport="http"}
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 80
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {100.0.0.1, 123.123.123.123, ::1, 2001:4898:0:fff:0:5efe:123.123.123.123...}
```

<span data-ttu-id="22d49-126">Dieser Befehl listet die WS-Management-Listenerkonfiguration auf dem lokalen Computer für den Listener auf, der den Kriterien im Selektorsatz entspricht.</span><span class="sxs-lookup"><span data-stu-id="22d49-126">This command lists the WS-Management listener configuration on the local computer for the listener that matches the criteria in the selector set.</span></span>

### <span data-ttu-id="22d49-127">Beispiel 6: Get Listener-Konfiguration, die den Kriterien eines Remote Computers entspricht</span><span class="sxs-lookup"><span data-stu-id="22d49-127">Example 6: Get listener configuration that matches criteria on a remote computer</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{Address="*";Transport="http"} -ComputerName "Server01"
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 80
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {100.0.0.1, 123.123.123.124, ::1, 2001:4898:0:fff:0:5efe:123.123.123.124...}
```

<span data-ttu-id="22d49-128">Dieser Befehl listet die WS-Management-Listenerkonfiguration auf dem Remotecomputer server01 für den Listener auf, der den Kriterien im Selektorsatz entspricht.</span><span class="sxs-lookup"><span data-stu-id="22d49-128">This command lists the WS-Management listener configuration on the remote server01 computer for the listener that matches the criteria in the selector set.</span></span>

### <span data-ttu-id="22d49-129">Beispiel 7: beziehen von zugeordneten Instanzen, die mit einer angegebenen Instanz verknüpft sind</span><span class="sxs-lookup"><span data-stu-id="22d49-129">Example 7: Get associated instances related to a specified instance</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -Dialect Association -Filter "{Object=win32_service?name=winrm}" -ResourceURI wmicimv2/*
xsi                       : http://www.w3.org/2001/XMLSchema-instance
p                         : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_ComputerSystem
cim                       : http://schemas.dmtf.org/wbem/wscim/1/common
type                      : p:Win32_ComputerSystem_Type
lang                      : en-US
AdminPasswordStatus       : 1
AutomaticManagedPagefile  : true
AutomaticResetBootOption  : true
AutomaticResetCapability  : true
BootOptionOnLimit         : BootOptionOnLimit
BootOptionOnWatchDog      : BootOptionOnWatchDog
BootROMSupported          : true
BootupState               : Normal boot
Caption                   : SERVER01
ChassisBootupState        : 3
CreationClassName         : Win32_ComputerSystem
CurrentTimeZone           : -480
DaylightInEffect          : false
Description               : AT/AT COMPATIBLE
DNSHostName               : server01
Domain                    : site01.corp.fabrikam.com
DomainRole                : 1
EnableDaylightSavingsTime : true
FrontPanelResetStatus     : 2
InfraredSupported         : false
InstallDate               : InstallDate
KeyboardPasswordStatus    : 2
LastLoadInfo              : LastLoadInfo
Manufacturer              : Dell Inc.
Model                     : OptiPlex 745
Name                      : SERVER01
NameFormat                : NameFormat
NetworkServerModeEnabled  : true
NumberOfLogicalProcessors : 2
NumberOfProcessors        : 1
OEMStringArray            : www.dell.com
PartOfDomain              : true
PauseAfterReset           : -1
PCSystemType              : 5
PowerManagementSupported  : PowerManagementSupported
PowerOnPasswordStatus     : 1
PowerState                : 0
PowerSupplyState          : 3
PrimaryOwnerContact       : PrimaryOwnerContact
PrimaryOwnerName          : testuser01
ResetCapability           : 1
ResetCount                : -1
ResetLimit                : -1
Roles                     : {LM_Workstation, LM_Server, SQLServer, NT}
Status                    : OK
SystemStartupDelay        : SystemStartupDelay
SystemStartupSetting      : SystemStartupSetting
SystemType                : X86-based PC
ThermalState              : 3
TotalPhysicalMemory       : 3217760256
UserName                  : FABRIKAM\testuser01
WakeUpType                : 6
Workgroup                 : Workgroup
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Remote Procedure Call (RPC)
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Serves as the endpoint mapper and COM Service Control Manager. If this service is stopped
or disabled, programs using COM or Remote Procedure Call (RPC) services will not function
properly.
DesktopInteract         : false
DisplayName             : Remote Procedure Call (RPC)
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : RpcSs
PathName                : C:\Windows\system32\svchost.exe -k rpcss
ProcessId               : 1100
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : true
StartMode               : Auto
StartName               : NT AUTHORITY\NetworkService
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
WaitHint                : 0

xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_SystemDriver
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_SystemDriver_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : true
Caption                 : HTTP
CreationClassName       : Win32_SystemDriver
Description             : HTTP
DesktopInteract         : false
DisplayName             : HTTP
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : HTTP
PathName                : C:\Windows\system32\drivers\HTTP.sys
ServiceSpecificExitCode : 0
ServiceType             : Kernel Driver
Started                 : true
StartMode               : Manual
StartName               :
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
```

<span data-ttu-id="22d49-130">Dieser Befehl ruft die assoziierten Instanzen ab, die mit der angegebenen Instanz (winrm) verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="22d49-130">This command gets the associated instances that are related to the specified instance (winrm).</span></span>

<span data-ttu-id="22d49-131">Sie müssen den Filter in Anführungszeichen einschließen, wie im Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="22d49-131">You must enclose the filter in quotation marks, as shown in the example.</span></span>

### <span data-ttu-id="22d49-132">Beispiel 8: erhalten von Zuordnungs Instanzen, die mit einer angegebenen Instanz verknüpft sind</span><span class="sxs-lookup"><span data-stu-id="22d49-132">Example 8: Get association instances related to a specified instance</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -Dialect Association -Associations -Filter "{Object=win32_service?name=winrm}" -ResourceURI wmicimv2/*
```

<span data-ttu-id="22d49-133">Dieser Befehl ruft die Assoziationsinstanzen ab, die mit der angegebenen Instanz (winrm) verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="22d49-133">This command gets association instances that are related to the specified instance (winrm).</span></span>
<span data-ttu-id="22d49-134">Da der *Dialekt* Wert Association lautet und der Association *-Parameter verwendet* wird, gibt dieser Befehl Zuordnungs Instanzen zurück, keine zugeordneten Instanzen.</span><span class="sxs-lookup"><span data-stu-id="22d49-134">Because the *Dialect* value is association and the *Associations* parameter is used, this command returns association instances, not associated instances.</span></span>

<span data-ttu-id="22d49-135">Sie müssen den Filter in Anführungszeichen einschließen, wie im Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="22d49-135">You must enclose the filter in quotation marks, as shown in the example.</span></span>

## <span data-ttu-id="22d49-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="22d49-136">PARAMETERS</span></span>

### <span data-ttu-id="22d49-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="22d49-137">-ApplicationName</span></span>
<span data-ttu-id="22d49-138">Gibt den Anwendungsnamen in der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="22d49-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="22d49-139">Der Standardwert des *ApplicationName* -Parameters lautet "wsman".</span><span class="sxs-lookup"><span data-stu-id="22d49-139">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="22d49-140">Der vollständige Bezeichner für den Remoteendpunkt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="22d49-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="22d49-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="22d49-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="22d49-142">Beispiel: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="22d49-142">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="22d49-143">Die Sitzung wird von IIS (Internetinformationsdienste) gehostet. IIS leitet Anforderungen mit diesem Endpunkt an die angegebene Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="22d49-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="22d49-144">Diese Standardeinstellung von WSMAN eignet sich für die meisten Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="22d49-144">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="22d49-145">Dieser Parameter ist für die Verwendung bestimmt, wenn viele Computer Remote Verbindungen mit einem Computer herstellen, auf dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="22d49-145">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="22d49-146">In diesem Fall hostet IIS WS-Management aus Effizienzgründen.</span><span class="sxs-lookup"><span data-stu-id="22d49-146">In this case, IIS hosts WS-Management for efficiency.</span></span>

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

### <span data-ttu-id="22d49-147">-Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="22d49-147">-Associations</span></span>
<span data-ttu-id="22d49-148">Gibt an, dass dieses Cmdlet Zuordnungs Instanzen, keine zugeordneten Instanzen, abruft.</span><span class="sxs-lookup"><span data-stu-id="22d49-148">Indicates that this cmdlet gets association instances, not associated instances.</span></span>
<span data-ttu-id="22d49-149">Sie können diesen Parameter nur verwenden, wenn der *Dialekt* Parameter den Wert Association aufweist.</span><span class="sxs-lookup"><span data-stu-id="22d49-149">You can use this parameter only when the *Dialect* parameter has a value of Association.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-150">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="22d49-150">-Authentication</span></span>
<span data-ttu-id="22d49-151">Gibt den Authentifizierungsmechanismus an, der auf dem Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="22d49-151">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="22d49-152">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="22d49-152">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="22d49-153">Standard.</span><span class="sxs-lookup"><span data-stu-id="22d49-153">Basic.</span></span>
<span data-ttu-id="22d49-154">„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="22d49-154">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="22d49-155">Standard.</span><span class="sxs-lookup"><span data-stu-id="22d49-155">Default.</span></span>
<span data-ttu-id="22d49-156">Verwendet die vom WS-Verwaltungsprotokoll implementierte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="22d49-156">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="22d49-157">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="22d49-157">This is the default.</span></span>
- <span data-ttu-id="22d49-158">Digest.</span><span class="sxs-lookup"><span data-stu-id="22d49-158">Digest.</span></span>
<span data-ttu-id="22d49-159">„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="22d49-159">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="22d49-160">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="22d49-160">Kerberos.</span></span>
<span data-ttu-id="22d49-161">Der Clientcomputer und der Server authentifizieren sich gegenseitig mithilfe von Kerberos-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="22d49-161">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="22d49-162">Negotiate</span><span class="sxs-lookup"><span data-stu-id="22d49-162">Negotiate.</span></span>
<span data-ttu-id="22d49-163">„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="22d49-163">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="22d49-164">Dieser Parameterwert ermöglicht beispielsweise die Aushandlung, um zu bestimmen, ob das Kerberos-Protokoll oder NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="22d49-164">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="22d49-165">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="22d49-165">CredSSP.</span></span>
<span data-ttu-id="22d49-166">Verwenden Sie die Authentifizierung der Credential Security Support Provider (kredssp), mit der der Benutzer Anmelde Informationen delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="22d49-166">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="22d49-167">Diese Option ist für Befehle vorgesehen, die auf einem Remotecomputer ausgeführt werden, jedoch Daten von anderen Remotecomputern sammeln oder zusätzliche Befehle auf anderen Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="22d49-167">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="22d49-168">Vorsicht: die Anmelde Informationen des Benutzers werden vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="22d49-168">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="22d49-169">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="22d49-169">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="22d49-170">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="22d49-170">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-171">-Basepropertiesonly</span><span class="sxs-lookup"><span data-stu-id="22d49-171">-BasePropertiesOnly</span></span>
<span data-ttu-id="22d49-172">Gibt an, dass dieses Cmdlet nur die Eigenschaften auflistet, die Teil der Basisklasse sind, die durch den *resourceUri* -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="22d49-172">Indicates that this cmdlet enumerates only the properties that are part of the base class that is specified by the *ResourceURI* parameter.</span></span>
<span data-ttu-id="22d49-173">Dieser Parameter hat keine Auswirkung, wenn der *flache* Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="22d49-173">This parameter has no effect if the *Shallow* parameter is specified.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases: UBPO, Base

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-174">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="22d49-174">-CertificateThumbprint</span></span>
<span data-ttu-id="22d49-175">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="22d49-175">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="22d49-176">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="22d49-176">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="22d49-177">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="22d49-177">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="22d49-178">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="22d49-178">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="22d49-179">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den Befehl Get-Item oder Get-ChildItem im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="22d49-179">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="22d49-180">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="22d49-180">-ComputerName</span></span>
<span data-ttu-id="22d49-181">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="22d49-181">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="22d49-182">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="22d49-182">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="22d49-183">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="22d49-183">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="22d49-184">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="22d49-184">The local computer is the default.</span></span>
<span data-ttu-id="22d49-185">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="22d49-185">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="22d49-186">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="22d49-186">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-187">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="22d49-187">-ConnectionURI</span></span>
<span data-ttu-id="22d49-188">Gibt den Verbindungsendpunkt an.</span><span class="sxs-lookup"><span data-stu-id="22d49-188">Specifies the connection endpoint.</span></span>
<span data-ttu-id="22d49-189">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="22d49-189">The format of this string is as follows:</span></span>

<span data-ttu-id="22d49-190">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="22d49-190">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="22d49-191">Die folgende Zeichenfolge ist ein ordnungsgemäß formatierter Wert für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="22d49-191">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="22d49-192">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="22d49-192">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-193">-Credential</span><span class="sxs-lookup"><span data-stu-id="22d49-193">-Credential</span></span>
<span data-ttu-id="22d49-194">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="22d49-194">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="22d49-195">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="22d49-195">The default is the current user.</span></span>
<span data-ttu-id="22d49-196">Geben Sie einen Benutzernamen ein, z. b. USER01, Domain01\User01 oder User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="22d49-196">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="22d49-197">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom Get-Credential-Cmdlet zurück gegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="22d49-197">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="22d49-198">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="22d49-198">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-199">-Dialekt</span><span class="sxs-lookup"><span data-stu-id="22d49-199">-Dialect</span></span>
<span data-ttu-id="22d49-200">Gibt den im Filterprädikat zu verwendenden Dialekt an.</span><span class="sxs-lookup"><span data-stu-id="22d49-200">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="22d49-201">Dies kann ein beliebiger vom Remotedienst unterstützter Dialekt sein.</span><span class="sxs-lookup"><span data-stu-id="22d49-201">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="22d49-202">Die folgenden Aliase können für den Dialekt-URI verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="22d49-202">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="22d49-203">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="22d49-203">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="22d49-204">Ktor `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="22d49-204">Selector `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="22d49-205">Anwalt `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="22d49-205">Association `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-206">-Aufzählen</span><span class="sxs-lookup"><span data-stu-id="22d49-206">-Enumerate</span></span>
<span data-ttu-id="22d49-207">Gibt an, dass dieses Cmdlet alle Instanzen einer Verwaltungs Ressource zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="22d49-207">Indicates that this cmdlet returns all of the instances of a management resource.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-208">-Filter</span><span class="sxs-lookup"><span data-stu-id="22d49-208">-Filter</span></span>
<span data-ttu-id="22d49-209">Gibt den Filterausdruck für die Enumeration an.</span><span class="sxs-lookup"><span data-stu-id="22d49-209">Specifies the filter expression for the enumeration.</span></span>
<span data-ttu-id="22d49-210">Wenn Sie diesen Parameter angeben, müssen Sie auch " *Dialekt* " angeben.</span><span class="sxs-lookup"><span data-stu-id="22d49-210">If you specify this parameter, you must also specify *Dialect* .</span></span>

<span data-ttu-id="22d49-211">Die gültigen Werte dieses Parameters hängen vom Dialekt ab, der im *Dialekt* angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="22d49-211">The valid values of this parameter depend on the dialect that is specified in *Dialect* .</span></span>
<span data-ttu-id="22d49-212">Wenn der *Dialekt* z. b. WQL ist, muss der *Filter* -Parameter eine Zeichenfolge enthalten, und die Zeichenfolge muss eine gültige WQL-Abfrage enthalten, wie z. b. die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="22d49-212">For example, if *Dialect* is WQL, the *Filter* parameter must contain a string, and the string must contain a valid WQL query such as the following query:</span></span>

`"Select * from Win32_Service where State != Running"`

<span data-ttu-id="22d49-213">Wenn der *Dialekt* Association ist, muss der *Filter* eine Zeichenfolge enthalten, und die Zeichenfolge muss einen gültigen Filter enthalten, wie z. b. den folgenden Filter:</span><span class="sxs-lookup"><span data-stu-id="22d49-213">If *Dialect* is Association, *Filter* must contain a string, and the string must contain a valid filter, such as the following filter:</span></span>

`-filter:Object=EPR\[;AssociationClassName=AssocClassName\]\[;ResultClassName=ClassName\]\[;Role=RefPropertyName\]\[;ResultRole=RefPropertyName\]}`

```yaml
Type: System.String
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-214">-Fragment</span><span class="sxs-lookup"><span data-stu-id="22d49-214">-Fragment</span></span>
<span data-ttu-id="22d49-215">Gibt einen Abschnitt innerhalb der Instanz an, die aktualisiert oder für den angegebenen Vorgang abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="22d49-215">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="22d49-216">Um beispielsweise den Status eines Spoolerdiensts zu erhalten, geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="22d49-216">For example, to get the status of a spooler service, specify the following:</span></span>

`-Fragment Status`

```yaml
Type: System.String
Parameter Sets: GetInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-217">-OptionSET</span><span class="sxs-lookup"><span data-stu-id="22d49-217">-OptionSet</span></span>
<span data-ttu-id="22d49-218">Gibt eine Reihe von Schaltern für einen Dienst an, um die Art der Anforderung zu ändern oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="22d49-218">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="22d49-219">Diese ähneln Switches, die in Befehlszeilenshells verwendet werden, da Sie Dienst spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="22d49-219">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="22d49-220">Es können beliebig viele Optionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="22d49-220">Any number of options can be specified.</span></span>

<span data-ttu-id="22d49-221">Das folgende Beispiel veranschaulicht die Syntax, durch die die Werte 1, 2 und 3 für die Parameter „a“, „b“ und „c“ übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="22d49-221">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: OS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-222">-Port</span><span class="sxs-lookup"><span data-stu-id="22d49-222">-Port</span></span>
<span data-ttu-id="22d49-223">Gibt den Port an, der verwendet wird, wenn der Client eine Verbindung mit dem WinRM-Dienst herstellt.</span><span class="sxs-lookup"><span data-stu-id="22d49-223">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="22d49-224">Wenn der Transport auf HTTP festgelegt ist, lautet der Standardport 80.</span><span class="sxs-lookup"><span data-stu-id="22d49-224">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="22d49-225">Wenn der Transport auf HTTPS festgelegt ist, lautet der Standardport 443.</span><span class="sxs-lookup"><span data-stu-id="22d49-225">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="22d49-226">Wenn Sie HTTPS als Transport verwenden, muss der Wert des *Computername* -Parameters mit dem allgemeinen Namen des Serverzertifikats (CN) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="22d49-226">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="22d49-227">Wenn der *skipcncheck* -Parameter jedoch als Teil des *sessionoption* -Parameters angegeben wird, muss der allgemeine Name des Zertifikats für den Server nicht mit dem Hostnamen des Servers identisch sein.</span><span class="sxs-lookup"><span data-stu-id="22d49-227">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="22d49-228">Der *skipcncheck* -Parameter sollte nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="22d49-228">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="22d49-229">-ResourceUri</span><span class="sxs-lookup"><span data-stu-id="22d49-229">-ResourceURI</span></span>
<span data-ttu-id="22d49-230">Gibt den URI der Ressourcen Klasse oder-Instanz an.</span><span class="sxs-lookup"><span data-stu-id="22d49-230">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="22d49-231">Der URI identifiziert einen bestimmten Ressourcentyp (z. b. Datenträger oder Prozesse) auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="22d49-231">The URI identifies a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="22d49-232">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="22d49-232">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="22d49-233">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="22d49-233">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: RURI

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-234">-ReturnType</span><span class="sxs-lookup"><span data-stu-id="22d49-234">-ReturnType</span></span>
<span data-ttu-id="22d49-235">Gibt den Typ der zurückzugebenden Daten an.</span><span class="sxs-lookup"><span data-stu-id="22d49-235">Specifies the type of data to be returned.</span></span>
<span data-ttu-id="22d49-236">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="22d49-236">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="22d49-237">Object</span><span class="sxs-lookup"><span data-stu-id="22d49-237">Object</span></span>
- <span data-ttu-id="22d49-238">EPR</span><span class="sxs-lookup"><span data-stu-id="22d49-238">EPR</span></span>
- <span data-ttu-id="22d49-239">ObjectAndEPR</span><span class="sxs-lookup"><span data-stu-id="22d49-239">ObjectAndEPR</span></span>

<span data-ttu-id="22d49-240">Der Standardwert ist Object.</span><span class="sxs-lookup"><span data-stu-id="22d49-240">The default value is Object.</span></span>

<span data-ttu-id="22d49-241">Wenn Sie das Objekt angeben oder diesen Parameter nicht angeben, gibt dieses Cmdlet nur-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="22d49-241">If you specify Object or do not specify this parameter, this cmdlet returns only objects.</span></span>
<span data-ttu-id="22d49-242">Wenn Sie Endpunkt Verweis (EPR) angeben, gibt dieses Cmdlet nur die Endpunkt Verweise der Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="22d49-242">If you specify endpoint reference (EPR) this cmdlet returns only the endpoint references of the objects.</span></span>
<span data-ttu-id="22d49-243">Endpunktverweise enthalten Informationen zum Ressourcen-URI und den Selektoren für die Instanz.</span><span class="sxs-lookup"><span data-stu-id="22d49-243">Endpoint references contain information about the resource URI and the selectors for the instance.</span></span>
<span data-ttu-id="22d49-244">Wenn Sie objectandepr angeben, gibt dieses Cmdlet sowohl das-Objekt als auch seine zugeordneten Endpunkt Verweise zurück.</span><span class="sxs-lookup"><span data-stu-id="22d49-244">If you specify ObjectAndEPR, this cmdlet returns both the object and its associated endpoint references.</span></span>

```yaml
Type: System.String
Parameter Sets: Enumerate
Aliases: RT
Accepted values: object, epr, objectandepr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-245">-Selector Set</span><span class="sxs-lookup"><span data-stu-id="22d49-245">-SelectorSet</span></span>
<span data-ttu-id="22d49-246">Gibt eine Reihe von Wertpaaren an, mit denen bestimmte Instanzen von Verwaltungsressourcen ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="22d49-246">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="22d49-247">Der *selectorset* -Parameter wird verwendet, wenn mehr als eine Instanz der Ressource vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="22d49-247">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="22d49-248">Der Wert des *selectorset* -Parameters muss eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="22d49-248">The value of the *SelectorSet* parameter must be a hash table.</span></span>

<span data-ttu-id="22d49-249">Das folgende Beispiel zeigt, wie Sie einen Wert für diesen Parameter eingeben:</span><span class="sxs-lookup"><span data-stu-id="22d49-249">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: GetInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-250">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="22d49-250">-SessionOption</span></span>
<span data-ttu-id="22d49-251">Gibt erweiterte Optionen für die WS-Management Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="22d49-251">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="22d49-252">Geben Sie ein **sessionoption** -Objekt ein, das Sie mit dem New-WSManSessionOption-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="22d49-252">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="22d49-253">Geben Sie ein, um weitere Informationen zu den verfügbaren Optionen zu erhalten `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="22d49-253">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: SO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-254">-Flach</span><span class="sxs-lookup"><span data-stu-id="22d49-254">-Shallow</span></span>
<span data-ttu-id="22d49-255">Gibt an, dass dieses Cmdlet nur Instanzen der Basisklasse zurückgibt, die im Ressourcen-URI angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="22d49-255">Indicates that this cmdlet returns only instances of the base class that is specified in the resource URI.</span></span>
<span data-ttu-id="22d49-256">Wenn Sie diesen Parameter nicht angeben, gibt dieses Cmdlet Instanzen der Basisklasse zurück, die im URI und in allen abgeleiteten Klassen angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="22d49-256">If you do not specify this parameter,, this cmdlet returns instances of the base class that is specified in the URI and in all its derived classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-257">-US-</span><span class="sxs-lookup"><span data-stu-id="22d49-257">-UseSSL</span></span>
<span data-ttu-id="22d49-258">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="22d49-258">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="22d49-259">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="22d49-259">By default, SSL is not used.</span></span>

<span data-ttu-id="22d49-260">WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="22d49-260">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="22d49-261">Mit *dem Parameter "* Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="22d49-261">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="22d49-262">Wenn SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist und Sie diesen Parameter angeben, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="22d49-262">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SSL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22d49-263">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="22d49-263">CommonParameters</span></span>
<span data-ttu-id="22d49-264">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="22d49-264">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="22d49-265">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="22d49-265">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="22d49-266">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="22d49-266">INPUTS</span></span>

### <span data-ttu-id="22d49-267">Keine</span><span class="sxs-lookup"><span data-stu-id="22d49-267">None</span></span>
<span data-ttu-id="22d49-268">Dieser Befehl nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="22d49-268">This command does not accept any input.</span></span>

## <span data-ttu-id="22d49-269">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="22d49-269">OUTPUTS</span></span>

### <span data-ttu-id="22d49-270">System.Xml.Xml-Element</span><span class="sxs-lookup"><span data-stu-id="22d49-270">System.Xml.XmlElement</span></span>
<span data-ttu-id="22d49-271">Dieses Cmdlet generiert ein **XmlElement** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="22d49-271">This cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="22d49-272">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="22d49-272">NOTES</span></span>

## <span data-ttu-id="22d49-273">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="22d49-273">RELATED LINKS</span></span>

[<span data-ttu-id="22d49-274">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="22d49-274">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="22d49-275">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="22d49-275">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="22d49-276">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="22d49-276">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="22d49-277">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="22d49-277">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="22d49-278">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="22d49-278">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="22d49-279">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="22d49-279">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="22d49-280">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="22d49-280">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="22d49-281">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="22d49-281">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="22d49-282">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="22d49-282">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="22d49-283">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="22d49-283">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="22d49-284">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="22d49-284">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="22d49-285">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="22d49-285">Test-WSMan</span></span>](Test-WSMan.md)
