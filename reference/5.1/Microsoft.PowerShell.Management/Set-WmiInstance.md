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
# Set-WmiInstance

## ZUSAMMENFASSUNG
Erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI).

## SYNTAX

### Class (Standard)

```
Set-WmiInstance [-Class] <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Objekt

```
Set-WmiInstance -InputObject <ManagementObject> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### path

```
Set-WmiInstance -Path <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Wqlquery

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Abfrage

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### list

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das- `Set-WmiInstance` Cmdlet erstellt oder aktualisiert eine Instanz einer vorhandenen WMI-Klasse (Windows-Verwaltungsinstrumentation).
Die erstellte oder aktualisierte Instanz wird in das WMI-Repository geschrieben.

Mit den neuen in Windows PowerShell 3.0 eingeführten CIM-Cmdlets werden die gleichen Aufgaben wie mit WMI-Cmdlets ausgeführt.
Die CIM-Cmdlets entsprechen den WS-Management (WSMAN)-Standards und dem Common Information Model (CIM)-Standard.
Dadurch können Cmdlets dieselben Verfahren zum Verwalten von Windows-basierten Computern und denjenigen verwenden, auf denen andere Betriebssysteme ausgeführt werden.
Anstatt zu verwenden `Set-WmiInstance` , sollten Sie die Cmdlets [Set-ciminstance](/powershell/module/cimcmdlets/set-ciminstance) oder [New-ciminstance](/powershell/module/cimcmdlets/new-ciminstance) verwenden.

## BEISPIELE

### Beispiel 1: Festlegen der WMI-Protokollierungs Stufe

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

Mit diesem Befehl wird der WMI-Protokolliergrad auf %%amp;quot;2%%amp;quot; festgelegt.
Der Befehl übergibt die festzulegende Eigenschaft, und der Wert, der als Wertpaar betrachtet wird, im Argument-Parameter.
Der Parameter akzeptiert eine durch die Konstruktion %%amp;quot;@{property = value}%%amp;quot; definierte Hashtabelle.
Die zurückgegebenen Klasseninformationen spiegeln den neuen Wert wider.

### Beispiel 2: Erstellen einer Umgebungsvariablen und ihres Werts

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

Mit diesem Befehl wird die TestVar-Umgebungsvariable mit dem Wert "TestValue" erstellt.
Dies geschieht durch Erstellen einer neuen Instanz der WMI-Klasse **Win32_Environment** .
Dieser Vorgang erfordert geeignete Anmelde Informationen, und Sie müssen Windows PowerShell möglicherweise neu starten, damit die neue Umgebungsvariable angezeigt wird.

### Beispiel 3: Festlegen der WMI-Protokollierungs Stufe für mehrere Remote Computer

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

Mit diesem Befehl wird der WMI-Protokolliergrad auf %%amp;quot;2%%amp;quot; festgelegt.
Der Befehl übergibt die festzulegende Eigenschaft, und der Wert, der als Wertpaar betrachtet wird, im Argument-Parameter.
Der Parameter akzeptiert eine durch die Konstruktion %%amp;quot;@{property = value}%%amp;quot; definierte Hashtabelle.
Die zurückgegebenen Klasseninformationen spiegeln den neuen Wert wider.

## PARAMETERS

### -Arguments
Gibt den Namen der zu ändernden Eigenschaft und den neuen Wert für diese Eigenschaft an.
Der Name und der Wert müssen ein Name-Wert-Paar sein.
Das Name-Wert-Paar wird in der Befehlszeile als Hash Tabelle weitergegeben.
Beispiel:

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

### -AsJob
Gibt an, dass dieses cmdket als Hintergrund Auftrag ausgeführt wird.
Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.

Wenn Sie den *AsJob* -Parameter angeben, gibt der Befehl ein Objekt zurück, das den Hintergrund Auftrag darstellt, und zeigt dann die Eingabeaufforderung an.
Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.
Wenn **Set-wmiinstance** für einen Remote Computer verwendet wird, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse von Remote Computern werden automatisch an den lokalen Computer zurückgegeben.
Verwenden Sie zum Verwalten des Auftrags die Cmdlets, die das **Auftrags** Substantiv (die **Job** -Cmdlets) enthalten.
Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.

Um diesen Parameter zusammen mit Remote Computern verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein.
Außerdem müssen Sie Windows PowerShell mit der Option als Administrator ausführen in Windows Vista und höheren Versionen des Windows-Betriebssystems starten.
Weitere Informationen finden Sie unter %%amp;quot;about_Remote_Requirements%%amp;quot;.

Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter about_Jobs und about_Remote_Jobs.

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

### -Authentifizierung
Gibt die Authentifizierungs Ebene an, die für die WMI-Verbindung verwendet werden muss.
Zulässige Werte für diesen Parameter:

- -1: unverändert.
- 0: Default.
- 1: keine.
Es wird keine Authentifizierung durchgeführt.
- 2: verbinden.
Die Authentifizierung wird nur ausgeführt, wenn der Client eine Beziehung mit der Anwendung herstellt.
- 3: wird aufgerufen.
Die Authentifizierung wird nur zu Beginn jedes Aufrufes ausgeführt, wenn die Anwendung die Anforderung empfängt.
- 4: Paket.
Die Authentifizierung wird für alle Daten ausgeführt, die vom Client empfangen werden.
- 5: packetintegrity.
Alle Daten, die zwischen dem Client und der Anwendung übertragen werden, werden authentifiziert und überprüft.
- 6: PacketPrivacy.
Die Eigenschaften der anderen Authentifizierungs Ebenen werden verwendet, und alle Daten werden verschlüsselt.

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

### -Autorität
Gibt die Autorität an, die zum Authentifizieren der WMI-Verbindung verwendet werden soll.
Sie können die Standard-NTLM- oder Kerberos-Authentifizierung angeben.
Legen Sie für die Verwendung von NTLM die Authority-Einstellung auf %%amp;quot;ntlmdomain:\<DomainName\>%%amp;quot; fest, wobei \<DomainName\> einen gültigen NTLM-Domänennamen darstellt.
Wenn Sie Kerberos verwenden möchten, geben Sie Kerberos: an \<DomainName\> \\ \<ServerName\> .
Sie können die Authority-Einstellung nicht einschließen, wenn Sie eine Verbindung mit dem lokalen Computer herstellen.

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

### -Klasse
Gibt den Namen einer WMI-Klasse an.

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

### -ComputerName
Gibt den Namen des Computers an, auf dem dieses Cmdlet ausgeführt wird.
Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer ein.
Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.
Sie können den *ComputerName* -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.

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

### -Credential
Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.
Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. das vom Cmdlet Get-Credential generierte.
Wenn Sie einen Benutzernamen eingeben, fordert dieses Cmdlet zur Eingabe eines Kennworts auf.

Dieser Parameter wird nicht von Anbietern unterstützt, die mit dem-Parameter installiert werden, wird von keinen mit Windows PowerShell installierten Anbietern unterstützt.

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

### -Enableallprivileges
Gibt an, dass dieses Cmdlet alle Berechtigungen des aktuellen Benutzers vor dem Befehl aktiviert, den der WMI aufruft.

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

### -Identitätswechsel
Gibt die zu verwendende Identitätswechselebene an.
Zulässige Werte für diesen Parameter:

- 0: Default.
Liest die lokale Registrierung für die standardmäßige Identitätswechsel Ebene, die normalerweise auf 3 festgelegt ist: Identität annehmen.
- 1: Anonymous.
Verbirgt die Anmeldeinformationen des Aufrufers.
- 2: Identify.
Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers abzufragen.
- 3: Impersonate.
Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers zu verwenden.
- 4: Delegate.
Ermöglicht es Objekten, anderen Objekten die Verwendung der Anmeldeinformationen des Aufrufers zu gestatten.

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

### -InputObject
Gibt ein **ManagementObject** -Objekt an, das als Eingabe verwendet werden soll.
Wenn dieser Parameter verwendet wird, werden alle anderen Parameter Außer dem *Arguments* -Parameter ignoriert.

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

### -Gebiets Schema
Gibt das bevorzugte Gebietsschema für WMI-Objekte an.
Der *locale* -Parameter wird in einem Array im MS_ \<LCID\> Format in der bevorzugten Reihenfolge angegeben.

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

### -Namespace
Gibt den WMI-Repository-Namespace an, in dem sich die referenzierte WMI-Klasse befindet, wenn Sie mit dem *Class* -Parameter verwendet wird.

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

### -Path
Gibt einen WMI-Objekt Pfad der Instanz an, die Sie erstellen oder aktualisieren möchten.

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

### -PutType
Gibt an, ob die WMI-Instanz erstellt oder aktualisiert werden soll.
Zulässige Werte für diesen Parameter:

- UpdateOnly.
Aktualisiert eine vorhandene WMI-Instanz.
- CreateOnly.
Erstellt eine neue WMI-Instanz.
- UpdateOrCreate.
Aktualisiert die WMI-Instanz, sofern vorhanden, oder erstellt eine neue Instanz, wenn keine Instanz vorhanden ist.

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

### -ThrottleLimit
Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.
Dieser Parameter wird in Verbindung mit dem *AsJob* -Parameter verwendet.
Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

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

### -Confirm
Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

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

### -WhatIf
Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

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

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Dieses Cmdlet nimmt keine Eingabe an.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

## VERWANDTE LINKS

[Get-WmiObject](Get-WmiObject.md)

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Remove-WmiObject](Remove-WmiObject.md)
