---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionConfiguration
ms.openlocfilehash: d0c5f0a967ecd6eb07d7268cc9e25be93cc5f34c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218679"
---
# Get-PSSessionConfiguration

## ZUSAMMENFASSUNG
Ruft die registrierten Sitzungskonfigurationen auf dem Computer ab.

## SYNTAX

```
Get-PSSessionConfiguration [[-Name] <String[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-PSSessionConfiguration` Cmdlet werden die Sitzungs Konfigurationen abgerufen, die auf dem lokalen Computer registriert wurden. Dies ist ein erweitertes Cmdlet für Systemadministratoren, die benutzerdefinierte Sitzungskonfigurationen für ihre Benutzer verwalten.

Ab PowerShell 3,0 können Sie die Eigenschaften einer Sitzungs Konfiguration mit einer Sitzungs Konfigurationsdatei (. PSSC) definieren. Mit dieser Funktion können Sie angepasste und eingeschränkte Sitzungen erstellen, ohne ein Programm zu schreiben. Weitere Informationen zu Sitzungskonfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

Außerdem wurden ab PowerShell 3,0 neue Hinweis Eigenschaften zum Sitzungs Konfigurationsobjekt hinzugefügt, das `Get-PSSessionConfiguration` zurückgibt. Diese Eigenschaften erleichtern Benutzern und Erstellern von Sitzungskonfigurationen die Überprüfung und den Vergleich von Sitzungskonfigurationen.

Verwenden Sie das-Cmdlet, um eine Sitzungs Konfiguration zu erstellen und zu registrieren `Register-PSSessionConfiguration` .
Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

## BEISPIELE

### Beispiel 1: erhalten von Sitzungs Konfigurationen auf dem lokalen Computer

```powershell
Get-PSSessionConfiguration
```

### Beispiel 2: Holen Sie sich die beiden Standard Sitzungs Konfigurationen.

Der Befehl verwendet den **Name** -Parameter von `Get-PSSessionConfiguration` , um nur die Sitzungs Konfigurationen zu erhalten, deren Namen mit "Microsoft" beginnen.

```powershell
Get-PSSessionConfiguration -Name Microsoft*
```

```Output
Name                      PSVersion  StartupScript        Permission
----                      ---------  -------------        ----------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll...
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll...
```

### Beispiel 3: erhalten der Eigenschaften und Werte einer Sitzungs Konfiguration

Dieses Beispiel zeigt die Eigenschaften und Eigenschaftswerte einer Sitzungskonfiguration, die mithilfe einer Sitzungskonfigurationsdatei erstellt wurde.

```powershell
Get-PSSessionConfiguration -Name Full  | Format-List -Property *
```

```Output
Copyright                     : (c) 2011 User01. All rights reserved.
AliasDefinitions              : {System.Collections.Hashtable}
SessionType                   : Default
CompanyName                   : Unknown
GUID                          : 1e9cb265-dae0-4bd3-89a9-8338a47698a1
Author                        : User01
ExecutionPolicy               : Restricted
SchemaVersion                 : 1.0.0.0
LanguageMode                  : FullLanguage
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/Full
MaxConcurrentCommandsPerShell : 1500
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 10
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
configfilepath                : C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 300
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 1
Name                          : Full
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 25
Enabled                       : True
MaxShellsPerUser              : 30
Permission                    :
```

Im Beispiel wird das- `Get-PSSessionConfiguration` Cmdlet verwendet, um die vollständige Sitzungs Konfiguration zu erhalten. Ein Pipeline Operator sendet die vollständige Sitzungs Konfiguration an das `Format-List` Cmdlet. Der **Property** -Parameter mit dem Wert `*` (All) leitet `Format-List` , um alle Eigenschaften und Werte des Objekts in einer Liste anzuzeigen.

Die Ausgabe enthält nützliche Informationen, darunter den Autor der Sitzungs Konfiguration, den Sitzungstyp, den Sprachmodus und die Ausführungs Richtlinie von Sitzungen, die mit dieser Sitzungs Konfiguration, Sitzungs Kontingente und dem vollständigen Pfad zur Sitzungs Konfigurationsdatei erstellt werden.

Diese Ansicht einer Sitzungskonfiguration wird für Sitzungen verwendet, die eine Sitzungskonfigurationsdatei enthalten.
Weitere Informationen zu Sitzungskonfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

### Beispiel 4: eine weitere Möglichkeit zum Überprüfen der Sitzungs Konfigurationen

In diesem Beispiel wird das- `Get-ChildItem` Cmdlet (Alias `dir` ) im WSMAN: Provider-Laufwerk verwendet, um den Inhalt des Plug-in-Knotens anzuzeigen. Dies ist eine weitere Möglichkeit, um die Sitzungskonfigurationen auf dem Computer anzuzeigen.

```powershell
dir wsman:\localhost\plugin
```

```Output
Type            Keys                                Name
----            ----                                ----
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=WMI Provider}                 WMI Provider
```

Der **Plug** -in-Knoten enthält **Containerelement** -Objekte (Microsoft. WSMAN. Management. wsmanconfigcontainerelement), die die registrierten PowerShell-Sitzungs Konfigurationen zusammen mit anderen Plug-Ins für die WS-Verwaltung darstellen.

### Beispiel 6: Anzeigen von Sitzungs Konfigurationen auf einem Remote Computer

Dieses Beispiel zeigt, wie Sie den WSMan-Anbieter verwenden können, um die Sitzungskonfigurationen auf einem Remotecomputer anzuzeigen. Diese Methode bietet nicht so viele Informationen wie ein `Get-PSSessionConfiguration` Befehl, aber der Benutzer muss nicht Mitglied der Gruppe "Administratoren" sein, um dieses Cmdlet ausführen zu können.

```powershell
Connect-WSMan -ComputerName Server01
dir WSMan:\Server01\Plugin
```

```Output
   WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=Empty}                        Empty
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=NoLanguage}                   NoLanguage
Container       {Name=RestrictedLang}               RestrictedLang
Container       {Name=RRS}                          RRS
Container       {Name=SEL Plugin}                   SEL Plugin
Container       {Name=WithProfile}                  WithProfile
Container       {Name=WMI Provider}                 WMI Provider
```

Das- `Connect-WSMan` Cmdlet stellt eine Verbindung mit dem WinRM-Dienst auf dem Remote Computer Server01 her. Mit dem- `Get-ChildItem` Cmdlet (Alias `dir` ) des WSMAN:-Laufwerks werden die Elemente im **Server01\Plugin** -Pfad abgerufen. Die Ausgabe zeigt die Elemente im Plugin-Verzeichnis auf dem Computer „Server01“. Die Elemente enthalten die Sitzungskonfigurationen, die eine Art von WSMan-Plug-In sind, sowie andere Arten von Plug-Ins auf dem Computer.

### Beispiel 7: erhalten von detaillierten Sitzungs Konfigurationen von einem Remote Computer

In diesem Beispiel wird gezeigt, wie ein `Get-PSSessionConfiguration` Befehl auf einem Remote Computer ausgeführt wird. Der Befehl erfordert, dass die CredSSP-Delegierung in den Clienteinstellungen auf dem lokalen Computer und in den Diensteinstellungen auf dem Remotecomputer aktiviert ist.

Um die Befehle in diesem Beispiel auszuführen, müssen Sie Mitglied der Gruppe "Administratoren" auf dem lokalen Computer und dem Remote Computer sein, und Sie müssen PowerShell mit der Option " **als Administrator ausführen** " starten.

```powershell
Enable-WSManCredSSP -Delegate Server02
Connect-WSMan Server02
Set-Item WSMan:\Server02*\Service\Auth\CredSSP -Value $true
Invoke-Command -ScriptBlock {Get-PSSessionConfiguration} -ComputerName Server02 -Authentication CredSSP -Credential Domain01\Admin01
```

```Output
Name                      PSVersion  StartupScript        Permission                          PSComputerName
----                      ---------  -------------        ----------                          --------------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
MyX86Shell                5.1        c:\test\x86Shell.ps1 BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
```

Mit dem- `Enable-WSManCredSSP` Cmdlet wird die Server01-Delegierung auf dem lokalen Computer aktiviert. **CredSSP** Das- `Connect-WSMan` Cmdlet stellt eine Verbindung mit Server02 Computer her. Durch diese Aktion wird dem WSMAN:-Laufwerk auf dem lokalen Computer ein Knoten für Server02 hinzugefügt, sodass Sie die WS-Management Einstellungen auf dem Server02-Computer anzeigen und ändern können. Das- `Set-Item` Cmdlet ändert den Wert des Elements " **kredssp** " im Knoten "Dienst" des Server02-Computers in " **true** ". Dadurch werden die Diensteinstellungen auf dem Remotecomputer konfiguriert. Das- `Invoke-Command` Cmdlet führt den `Get-PSSessionConfiguration` Befehl auf dem Server02-Computer aus. Der Befehl verwendet den **Credential** -Parameter und den **Authentication** -Parameter mit dem Wert **CredSSP**. Die Ausgabe zeigt die Sitzungskonfigurationen auf dem Remotecomputer „Server02“.

### Beispiel 8: Ressourcen-URI einer Sitzungs Konfiguration

Dieses Beispiel ist hilfreich beim Festlegen des Werts der `$PSSessionConfigurationName` Preference-Variablen, die einen Ressourcen-URI annimmt.

```powershell
(Get-PSSessionConfiguration -Name CustomShell).resourceURI
```

```Output
http://schemas.microsoft.com/powershell/microsoft.CustomShell
```

Die- `$PSSessionConfigurationName` Variable gibt die Standardkonfiguration an, die beim Erstellen einer Sitzung verwendet wird. Diese Variable wird auf dem lokalen Computer festgelegt, aber sie gibt eine Konfiguration auf dem Remotecomputer an. Weitere Informationen zur- `$PSSessionConfiguration` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).

## PARAMETERS

### -Force

Unterdrückt die Eingabeaufforderung zum Neustart des WinRM-Diensts, wenn der Dienst noch nicht ausgeführt wird.

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

### -Name

Ruft nur die Sitzungskonfigurationen mit dem angegebenen Namen oder Namensmuster ab. Geben Sie mindestens einen Konfigurationsnamen ein. Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All session configurations on the local computer
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](./About/about_CommonParameters.md).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Microsoft. PowerShell. Commands. pssessionconfigurationcommands # pssessionconfiguration

## HINWEISE

- Starten Sie PowerShell mit der Option **als Administrator ausführen** , um dieses Cmdlet auszuführen.

- Zur Anzeige der Sitzungskonfigurationen auf dem Computer müssen Sie Mitglied der Gruppe „Administratoren“ auf dem Computer sein.

- Wenn Sie einen `Get-PSSessionConfiguration` Befehl auf einem Remote Computer ausführen möchten, müssen Sie in den Client Einstellungen auf dem lokalen Computer (mithilfe des `Enable-WSManCredSSP` Cmdlets) und in den Dienst Einstellungen auf dem Remote Computer aktiviert sein. Sie müssen auch den Wert " **kredssp** " des Parameters " **Authentication** " verwenden, wenn Sie die Remote Sitzung einrichten. Andernfalls wird der Zugriff verweigert.

- Die Hinweis Eigenschaften des-Objekts, das `Get-PSSessionConfiguration` zurückgibt, werden nur für das-Objekt angezeigt, wenn Sie über einen Wert verfügen. Nur Sitzungs Konfigurationen, die mithilfe einer Sitzungs Konfigurationsdatei erstellt wurden, verfügen über alle definierten Eigenschaften.

- Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab. Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.

- Sie können Befehle im WSMan:-Laufwerk verwenden, um die Eigenschaften von Sitzungskonfigurationen zu ändern.
  Allerdings können Sie das WSMAN:-Laufwerk in PowerShell 2,0 nicht verwenden, um Sitzungs Konfigurations Eigenschaften zu ändern, die in PowerShell 3,0 (z. b. **outputbufferingmode** ) eingeführt wurden. PowerShell 2,0-Befehle generieren keine Fehler, aber Sie sind wirkungslos. Verwenden Sie das WSMAN:-Laufwerk in PowerShell 3,0, um die in PowerShell 3,0 eingeführten Eigenschaften zu ändern.

## VERWANDTE LINKS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan-Anbieter](../microsoft.wsman.management/about/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
