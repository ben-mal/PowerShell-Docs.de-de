---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: 33773769cd19373764cf4adbe86bb990589948ff
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218175"
---
# Set-PSSessionConfiguration

## ZUSAMMENFASSUNG
Ändert die Eigenschaften einer registrierten Sitzungskonfiguration.

## SYNTAX

### Nameparameterset (Standard)

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Assemblynameparameterset

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Sessionconfigurationfile

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-PSSessionConfiguration` Cmdlet werden die Eigenschaften der Sitzungs Konfigurationen auf dem lokalen Computer geändert.

Verwenden Sie den **Name** -Parameter, um die Sitzungskonfiguration zu identifizieren, die Sie ändern möchten. Verwenden Sie die anderen Parameter, um neue Werte für die Eigenschaften der Sitzungskonfiguration anzugeben. Um einen Eigenschafts Wert aus der Konfiguration zu löschen und den Standardwert zu verwenden, geben Sie eine leere Zeichenfolge ("") oder den Wert `$Null` für den entsprechenden Parameter ein.

Ab PowerShell 3,0 können Sie eine Sitzungs Konfigurationsdatei verwenden, um eine Sitzungs Konfiguration zu definieren. Diese Funktion bietet eine einfache und sichtbare Methode für das Festlegen und Ändern der Eigenschaften von Sitzungen, die die Sitzungskonfiguration verwenden. Um eine Sitzungs Konfigurationsdatei anzugeben, verwenden Sie den **path** -Parameter von `Set-PSSessionConfiguration` . Weitere Informationen zu Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).
Weitere Informationen zum Erstellen und Ändern einer Sitzungs Konfigurationsdatei finden Sie unter dem- `New-PSSessionConfigurationFile` Cmdlet.

Sitzungs Konfigurationen definieren die Umgebung von Remote Sitzungen ( **pssessions** ), die eine Verbindung mit dem lokalen Computer herstellen. Jede **PSSession** verwendet eine Sitzungs Konfiguration. Die Sitzungs Konfiguration bestimmt die Funktionen der **PSSession** , wie z. b. die Module, die in der Sitzung verfügbar sind, die Cmdlets, die ausgeführt werden dürfen, den Sprachmodus, Kontingente und Timeouts. Die Sicherheits Beschreibung der Sitzungs Konfiguration bestimmt, wer die Sitzungs Konfiguration verwenden kann, um eine Verbindung mit dem lokalen Computer herzustellen. Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

Um die Eigenschaften einer Sitzungs Konfiguration anzuzeigen, verwenden Sie das `Get-PSSessionConfiguration` Cmdlet oder den WSMAN-Anbieter. Weitere Informationen zum WSMAN-Anbieter erhalten Sie, wenn Sie eingeben `Get-Help WSMan` .

## BEISPIELE

### Beispiel 1: Ändern des Thread Apartment Zustands

```
PS C:\> Set-PSSessionConfiguration -Name "MaintenanceShell" -ThreadApartmentState STA
```

Dieser Befehl ändert den Threadapartmentzustand in der MaintenanceShell-Konfiguration in „STA“.
Die Änderung ist wirksam, wenn Sie den **WinRM** -Dienst neu starten.

### Beispiel 2: Erstellen und Ändern einer Sitzungs Konfiguration

Dieses Beispiel zeigt, wie Sie ein Startskript aus einer Konfiguration hinzufügen und daraus entfernen.

Mit dem ersten Befehl wird die **adminshell** -Konfiguration erstellt. Mit dem zweiten Befehl wird das Skript der Konfiguration hinzugefügt `AdminConfig.ps1` . Die Änderung ist wirksam, wenn Sie **WinRM** neu starten.
Der dritte Befehl entfernt das `AdminConfig.ps1` Skript aus der Konfiguration.

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### Beispiel 3: Anzeigen der Ergebnisse

In diesem Beispiel wird der Wert der **maximumreceivedobjectsizemb** -Eigenschaft auf 20 erhöht. Mit diesem Befehl werden Sie außerdem aufgefordert, den **WinRM** -Dienst neu zu starten. Die Änderung wird erst wirksam, wenn der **WinRM** -Dienst neu gestartet wird.

```powershell
Set-PSSessionConfiguration -Name "IncObj" -MaximumReceivedObjectSizeMB 20
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\IncObj\InitializationParameters

ParamName                       ParamValue
---------                       ----------
psmaximumreceivedobjectsizemb   20

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

### Beispiel 4: Anzeigen der Ergebnisse auf verschiedene Weise

In diesem Beispiel `Set-PSSessionConfiguration` ändert das Startskript in der **maintenanceshell** -Sitzungs Konfiguration in `Maintenance.ps1` . In der Ausgabe wird die Änderung angezeigt, und Sie werden aufgefordert, den **WinRM** -Dienst neu zu starten. Die Antwort ist „y“ (Ja).

`Get-PSSessionConfiguration` Ruft die **maintenanceshell** -Sitzungs Konfiguration ab. Der Pipeline Operator (|) sendet die Ergebnisse des Befehls an `Format-List` , wodurch alle Eigenschaften des Konfigurations Objekts in einer Liste angezeigt werden. Als Nächstes zeigen wir mithilfe des WSMAN-Anbieters die Initialisierungs Parameter für die **maintenanceshell** -Konfiguration an. `Get-ChildItem` (Alias `dir` ) Ruft die untergeordneten Elemente im **initializationparameters** -Knoten für das **maintenanceshell** -Plug-in ab. Weitere Informationen zum WSMAN-Anbieter erhalten Sie, wenn Sie eingeben `Get-Help wsman` .

```
PS> Set-PSSessionConfiguration -Name "MaintenanceShell" -StartupScript "C:\ps-test\Maintenance.ps1"

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName            ParamValue
---------            ----------
startupscript        c:\ps-test\Mainte...

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run
the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

PS> Get-PSSessionConfiguration MaintenanceShell | Format-List -Property *

xmlns            : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
Name             : MaintenanceShell
Filename         : %windir%\system32\pwrshplugin.dll
SDKVersion       : 1
XmlRenderingType : text
lang             : en-US
PSVersion        : 2.0
startupscript    : c:\ps-test\Maintenance.ps1
ResourceUri      : http://schemas.microsoft.com/powershell/MaintenanceShell
SupportsOptions  : true
ExactMatch       : true
Capability       : {Shell}
Permission       :

PS> dir WSMan:\localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName     ParamValue
---------     ----------
PSVersion     2.0
startupscript c:\ps-test\Maintenance.ps1
```

## PARAMETERS

### -AccessMode

Aktiviert und deaktiviert die Sitzungskonfiguration und bestimmt, ob sie für Remote- oder lokale Sitzungen auf dem Computer verwendet werden kann. Zulässige Werte für diesen Parameter:

- Deaktiviert. Deaktiviert die Sitzungskonfiguration. Sie kann nicht für Remote- oder lokalen Zugriff auf den Computer verwendet werden. Dieser Wert legt die **aktivierte** Eigenschaft der Sitzungs Konfiguration ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) auf " **false** " fest.
- Lokal. Fügt der Sicherheitsbeschreibung der Sitzungskonfiguration einen **Network_Deny_All** -Eintrag hinzu.
  Benutzer des lokalen Computers können die Sitzungs Konfiguration verwenden, um eine lokale Loopback Sitzung auf demselben Computer zu erstellen, aber Remote Benutzern wird der Zugriff verweigert.
- Remote. Entfernt die Einträge **Deny_All** und **Network_Deny_All** aus den Sicherheitsbeschreibungen der Sitzungskonfiguration. Benutzer von lokalen Computern und Remotecomputern können die Sitzungskonfiguration verwenden, um Sitzungen zu erstellen und um Befehle auf diesem Computer auszuführen.

Der Standardwert ist **Remote**.

Andere Cmdlets können den Wert dieses Parameters später überschreiben. Beispielsweise aktiviert das `Enable-PSRemoting` Cmdlet alle Sitzungs Konfigurationen auf dem Computer und ermöglicht den Remote Zugriff auf diese, und das `Disable-PSRemoting` Cmdlet gestattet nur den lokalen Zugriff auf alle Sitzungs Konfigurationen auf dem Computer.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Management.Automation.Runspaces.PSSessionConfigurationAccessMode
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Local, Remote

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationBase

Gibt den Pfad der \* **Assemblydatei** (. dll) an, die im Wert des AssemblyName-Parameters angegeben ist.

```yaml
Type: System.String
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssemblyName

Gibt den Assemblynamen an. Dieses Cmdlet erstellt eine Sitzungs Konfiguration basierend auf einer Klasse, die in einer Assembly definiert ist.

Geben Sie den Dateinamen oder den vollständigen Pfad einer Assembly. dll-Datei ein, die eine Sitzungs Konfiguration definiert. Wenn Sie nur den Dateinamen eingeben, können Sie den Pfad im Wert des **ApplicationBase** -Parameters eingeben.

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Configurationtyname

Gibt den Typ der Sitzungskonfiguration an, der in der Assembly im **AssemblyName** -Parameter definiert ist. Der Typ, den Sie angeben, muss die **System.Management.Automation.Remoting.PSSessionConfiguration** Klasse implementieren.

Dieser Parameter ist erforderlich, wenn Sie den Namen einer Assembly angeben.

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Unterdrückt alle Benutzer Aufforderungen und startet den **WinRM** -Dienst ohne Aufforderung neu. Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.

Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, verwenden Sie den **NoServiceRestart** -Parameter.

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

### -Maximumreceiveddatasizepercommandmb

Gibt den Grenzwert für die Datenmenge an, die in jedem einzelnen Remote Befehl an diesen Computer gesendet werden kann. Geben Sie die Datengröße in Megabyte (MB) ein. Der Standardwert ist 50 MB.

Wenn eine Datengrößen Beschränkung im Konfigurationstyp definiert ist, der im **configurationtypame** -Parameter angegeben ist, wird der Grenzwert im Konfigurationstyp verwendet. Der Wert dieses Parameters wird ignoriert.

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 50
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maximumreceivedobjectsizemb

Gibt die Grenzwerte für die Datenmenge an, die in jedem einzelnen Objekt an diesen Computer gesendet werden kann.
Geben Sie die Datengröße in Megabyte ein. Der Standardwert ist 10 MB.

Wenn eine Objektgrößen Beschränkung im Konfigurationstyp definiert ist, der im **configurationtypame** -Parameter angegeben ist, wird der Grenzwert im Konfigurationstyp verwendet. Der Wert dieses Parameters wird ignoriert.

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -Modulestoimport

Gibt die Module und Snap-ins an, die automatisch in Sitzungen importiert werden, die die Sitzungskonfiguration verwenden. Geben Sie die Namen der Module und Snap-Ins ein.

Standardmäßig wird nur das **Microsoft. PowerShell. Core** -Snap-in in Sitzungen importiert, aber wenn die Cmdlets nicht ausgeschlossen sind, können Sie die `Import-Module` -und-Add-PSSnapin-Cmdlets verwenden, um der Sitzung Module und Snap-Ins hinzuzufügen.

Die in diesem Parameterwert angegebenen Module werden in Ergänzungen zu Modulen importiert, die in der Sitzungs Konfigurationsdatei () angegeben sind `New-PSSessionConfigurationFile` . Einstellungen in der Sitzungskonfigurationsdatei können jedoch die von Modulen exportierten Befehle ausblenden oder verhindern, dass Benutzer sie verwenden.

Die in diesem Parameterwert angegebenen Module ersetzen die Liste der Module, die mit dem **modulestoimport** -Parameter des `Register-PSSessionConfiguration` Cmdlets angegeben werden.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Object[]
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt den Namen der Sitzungskonfiguration an, die Sie ändern möchten.

Sie können diesen Parameter verwenden, um den Namen der Sitzungskonfiguration zu ändern.

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

### -Noservicerestart

Der **WinRM** -Dienst wird nicht neu gestartet, und die Aufforderung zum Neustarten des Dienstanbieter wird unterdrückt.

Wenn Sie Ausführen `Set-PSSessionConfiguration` , werden Sie standardmäßig aufgefordert, den **WinRM** -Dienst neu zu starten, damit die neue Sitzungs Konfiguration wirksam wird. Bis der **WinRM** -Dienst neu gestartet wird, ist die neue Sitzungs Konfiguration nicht wirksam.

Um den **WinRM** -Dienst ohne Aufforderung neu zu starten, verwenden Sie den **Force** -Parameter. Verwenden Sie das-Cmdlet, um den **WinRM** -Dienst manuell neu zu starten `Restart-Service` .

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

### -Path

Gibt den Pfad einer Sitzungs Konfigurationsdatei (. PSSC) an, z. b. eine, die vom `New-PSSessionConfigurationFile` Cmdlet erstellt wurde. Wenn Sie den Pfad weglassen, ist die Standardeinstellung das aktuelle Verzeichnis.

Informationen dazu, wie Sie eine Sitzungs Konfigurationsdatei ändern, finden Sie im Hilfethema für das `New-PSSessionConfigurationFile` Cmdlet.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: SessionConfigurationFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Psversion

Gibt die Version von PowerShell in Sitzungen an, die diese Sitzungs Konfiguration verwenden.

Der Wert dieses Parameters hat Vorrang vor den Wert des **PowerShellVersion** -Schlüssels in der Sitzungskonfigurationsdatei.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Version
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases: PowerShellVersion

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runascredential

Gibt Anmelde Informationen für Befehle in der Sitzung an. Standardmäßig werden Befehle mit den Berechtigungen des aktuellen Benutzers ausgeführt.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

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

### -SecurityDescriptor SDDL

Gibt eine andere Security Descriptor Definition Language (SDDL)-Zeichenfolge für die Konfiguration an.

Diese Zeichenfolge bestimmt die Berechtigungen, die erforderlich sind, um die Konfiguration für die neue Sitzung zu verwenden. Um eine Sitzungs Konfiguration in einer Sitzung zu verwenden, müssen die Benutzer mindestens über die Berechtigung Execute (aufrufen) für die Konfiguration verfügen.

Um die Standard Sicherheits Beschreibung für die Konfiguration zu verwenden, geben Sie eine leere Zeichenfolge ("") oder einen Wert von ein `$Null` . Der Standardwert ist die Stamm-SDDL im WSMan:-Laufwerk.

Wenn die Sicherheits Beschreibung Komplex ist, sollten Sie die Verwendung des **showsecuritydescriptorui** -Parameters anstelle dieses Parameters in Erwägung gezogen. Sie können nicht beide Parameter im selben Befehl verwenden.

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

### -Sessiontypeoption

Gibt typspezifische Optionen für die Sitzungs Konfiguration an. Geben Sie ein "Session TYPE Options"-Objekt ein, z. b. das vom Cmdlet zurückgegebene **psworkflowexecutionoption** -Objekt `New-PSWorkflowExecutionOption` .

Die Optionen der Sitzungen, die die Sitzungskonfiguration verwenden, werden durch die Werte der Sitzungsoptionen und die Sitzungskonfigurationsoptionen bestimmt. Sofern nicht angegeben, haben in der Sitzung festgelegte Optionen, z. b. mit dem `New-PSSessionOption` Cmdlet, Vorrang vor den in der Sitzungs Konfiguration festgelegten Optionen. Die Sitzungsoptionswerte dürfen aber nicht die in der Sitzungskonfiguration festgelegten Höchstwerte überschreiten.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Management.Automation.PSSessionTypeOption
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Showsecuritydescriptor UI

Gibt an, dass dieses Cmdlet ein Eigenschaften Blatt ist, das Ihnen hilft, eine neue SDDL für die Sitzungs Konfiguration zu erstellen. Das Eigenschaften Blatt wird angezeigt, nachdem Sie den `Set-PSSessionConfiguration` Befehl ausgeführt und den **WinRM** -Dienst neu gestartet haben.

Beachten Sie beim Festlegen der Berechtigungen für die Konfiguration, dass die Benutzer mindestens über die Berechtigung Ausführen (aufrufen) verfügen müssen, um die Sitzungs Konfiguration in einer Sitzung zu verwenden.

Sie können den **SecurityDescriptorSDDL** -Parameter und diesen Parameter nicht im selben Befehl verwenden.

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

### -Startupscript

Gibt das Startskript für die Konfiguration an. Geben Sie den voll qualifizierten Pfad eines PowerShell-Skripts ein. Das angegebene Skript wird in der neuen Sitzung ausgeführt, die die Sitzungskonfiguration verwendet.

Zum Löschen eines Start Skripts aus einer Sitzungs Konfiguration geben Sie eine leere Zeichenfolge ("") oder einen Wert von ein `$Null` .

Zur weiteren Konfiguration der Benutzersitzung können Sie ein Startskript verwenden. Wenn das Skript einen Fehler (auch einen Fehler ohne Abbruch) generiert, wird die Sitzung nicht erstellt, und der `New-PSSession` Befehl schlägt fehl.

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

### -Threadapartmentstate

Gibt die Apartment Zustands Einstellung für die Threads in der Sitzung an.
Die zulässigen Werte für diesen Parameter sind "STA", "MTA" und "unknown".
Der Standardwert ist Unknown (Unbekannt).

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:
Accepted values: STA, MTA, Unknown

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Threadoptions

Gibt die Thread Options Einstellung in der Konfiguration an. Diese Einstellung definiert, wie Threads erstellt und verwendet werden, wenn ein Befehl in der Sitzung ausgeführt wird. Zulässige Werte für diesen Parameter:

- Standard
- Reusethread
- UseCurrentThread
- Usenewthread

Der Standardwert ist **usecurrentthread**.

Weitere Informationen finden Sie unter [psthlesoptions-Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).

```yaml
Type: System.Management.Automation.Runspaces.PSThreadOptions
Parameter Sets: (All)
Aliases:
Accepted values: Default, UseNewThread, ReuseThread, UseCurrentThread

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transportoption

Gibt die Transport Optionen für die Sitzungs Konfiguration an. Geben Sie ein Transport Options Objekt ein, z. b. das **wsmanconfigurationoption** -Objekt, das vom `New-PSTransportOption` Cmdlet zurückgegeben wird.

Die Optionen der Sitzungen, die die Sitzungskonfiguration verwenden, werden durch die Werte der Sitzungsoptionen und die Sitzungskonfigurationsoptionen bestimmt. Sofern nicht angegeben, haben in der Sitzung festgelegte Optionen, z. b. mit dem `New-PSSessionOption` Cmdlet, Vorrang vor den in der Sitzungs Konfiguration festgelegten Optionen. Die Sitzungsoptionswerte dürfen aber nicht die in der Sitzungskonfiguration festgelegten Höchstwerte überschreiten.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Management.Automation.PSTransportOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### --Vorgang

Verwenden Sie nur einen Prozess, um alle Sitzungen zu hosten, die vom gleichen Benutzer gestartet wurden und die gleiche Sitzungs Konfiguration verwenden. Standardmäßig wird jede Sitzung in einem eigenen Prozess gehostet.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

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

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Microsoft. WSMAN. Management. wsmanconfigleafelement

## HINWEISE

Starten Sie PowerShell mit der Option als Administrator ausführen, um dieses Cmdlet auszuführen.

Der `Set-PSSessionConfiguration` Konfigurations Name wird vom Cmdlet nicht geändert, und der **WSMAN** -Anbieter unterstützt das `Rename-Item` Cmdlet nicht. Um den Namen einer Sitzungs Konfiguration zu ändern, verwenden `Unregister-PSSessionConfiguration` Sie das Cmdlet, um die Konfiguration zu löschen, und verwenden Sie dann das `Register-PSSessionConfiguration` Cmdlet, um eine neue Sitzungs Konfiguration zu erstellen und zu registrieren.

Sie können das `Set-PSSessionConfiguration` Cmdlet verwenden, um die Standard Sitzungs Konfigurationen Microsoft. PowerShell und Microsoft. PowerShell32 zu ändern. Sie sind nicht geschützt. Um die ursprüngliche Version einer Standard Sitzungs Konfiguration wiederherzustellen, verwenden Sie das `Unregister-PSSessionConfiguration` Cmdlet, um die Standard Sitzungs Konfiguration zu löschen, und verwenden Sie dann das `Enable-PSRemoting` Cmdlet, um es wiederherzustellen.

Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab. Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.

Sie können Befehle im WSMan:-Laufwerk verwenden, um die Eigenschaften von Sitzungskonfigurationen zu ändern.
Allerdings können Sie das WSMAN:-Laufwerk in PowerShell 2,0 nicht verwenden, um Sitzungs Konfigurations Eigenschaften zu ändern, die in PowerShell 3,0 (z. b. **outputbufferingmode** ) eingeführt wurden. Windows PowerShell 2.0-Befehle generieren keine Fehler, aber sie sind wirkungslos. Verwenden Sie das WSMAN:-Laufwerk in PowerShell 3,0, um die in PowerShell 3,0 eingeführten Eigenschaften zu ändern.

## VERWANDTE LINKS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[New-PSWorkflowExecutionOption](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan-Anbieter](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
