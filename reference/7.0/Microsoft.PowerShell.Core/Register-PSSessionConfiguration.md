---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSSessionConfiguration
ms.openlocfilehash: c72641c73851521ceb3b696e8eda5ad02a4e46d2
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347515"
---
# Register-PSSessionConfiguration

## ZUSAMMENFASSUNG
Erstellt und registriert eine neue Sitzungskonfiguration.

## SYNTAX

### Nameparameterset (Standard)

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-ApplicationBase <String>]
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Assemblynameparameterset

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-AssemblyName] <String>
 [-ApplicationBase <String>] [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Sessionconfigurationfile

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String>
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das `Register-PSSessionConfiguration` -Cmdlet erstellt und registriert eine neue Sitzungs Konfiguration auf dem lokalen Computer. Hierbei handelt es sich um ein erweitertes Cmdlet, das Sie zum Erstellen benutzerdefinierter Sitzungen für Remote Benutzer verwenden können.

Jede PowerShell-Sitzung ( **PSSession** ) verwendet eine Sitzungs Konfiguration, auch als Endpunkt bezeichnet.
Wenn Benutzer eine Sitzung erstellen, die eine Verbindung mit dem Computer herstellt, können Sie eine Sitzungs Konfiguration auswählen oder die Standard Sitzungs Konfiguration verwenden, die beim Aktivieren von PowerShell-Remoting registriert wird.
Benutzer können auch die $PSSessionConfigurationName-Einstellungsvariable festlegen, die eine Standardkonfiguration für in der aktuellen Sitzung erstellte Remotesitzungen angibt.

Die Sitzungskonfiguration definiert die Umgebung für die Remotesitzung. Die Konfiguration kann festlegen, welche Befehle und Sprachelemente in der Sitzung verfügbar sind und Einstellungen zum Schutz des Computers enthalten, wie z. B. Beschränkungen der Datenmenge, die von der Sitzung remote in einem einzigen Objekt oder Befehl empfangen werden kann. Die Sicherheits Beschreibung der Sitzungs Konfiguration bestimmt, welche Benutzer über die Berechtigung zum Verwenden der Sitzungs Konfiguration verfügen.

Sie können die Elemente der Konfiguration mit einer Assembly definieren, die eine neue Konfigurationsklasse implementiert, sowie mithilfe eines Skripts, das in der Sitzung ausgeführt wird. Ab PowerShell 3,0 können Sie auch eine Sitzungs Konfigurationsdatei verwenden, um die Sitzungs Konfiguration zu definieren.

Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).
Weitere Informationen zu Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

## BEISPIELE

### Beispiel 1: Registrieren einer Newshell-Sitzungs Konfiguration

In diesem Beispiel registrieren wir die **Newshell** -Sitzungs Konfiguration. Die Parameter **AssemblyName** und **ApplicationBase** geben den Speicherort der **MyShell.dll** Datei an, die die Cmdlets und Anbieter in der Sitzungs Konfiguration angibt. Der **configurationtypame** -Parameter gibt die Konfigurations Klasse an, die aus der Assembly verwendet werden soll.

```powershell
$sessionConfiguration = @{
    Name='NewShell'
    ApplicationBase='c:\MyShells\'
    AssemblyName='MyShell.dll'
    ConfigurationTypeName='MyClass'
}
Register-PSSessionConfiguration @sessionConfiguration
```

Um diese Konfiguration zu verwenden, geben Sie ein `New-PSSession -ConfigurationName newshell` .

### Beispiel 2: Registrieren einer maintenanceshell-Sitzungs Konfiguration

In diesem Beispiel wird die **maintenanceshell** -Sitzungs Konfiguration auf dem lokalen Computer registriert. Der **startupscript** -Parameter gibt das `Maintenance.ps1` Skript an.

```powershell
Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
```

Wenn ein Benutzer einen `New-PSSession` Befehl verwendet und die **maintenanceshell** -Konfiguration auswählt, wird das `Maintenance.ps1` Skript in der neuen Sitzung ausgeführt. Das Skript kann die Sitzung konfigurieren. Dies schließt das Importieren von Modulen und das Festlegen der Ausführungs Richtlinie für die Sitzung ein. Wenn das Skript Fehler generiert, einschließlich Fehler ohne Abbruch, `New-PSSession` schlägt der Befehl fehl.

### Beispiel 3: Registrieren einer Sitzungs Konfiguration

In diesem Beispiel wird die **adminshell** -Sitzungs Konfiguration registriert.

Die `$sessionParams` Variable ist eine Hash Tabelle, die alle Parameterwerte enthält. Diese Hash Tabelle wird mithilfe von PowerShell-splatting an das Cmdlet übergeben. Der `Register-PSSessionConfiguration` Befehl verwendet den **securitydescritorsddl** -Parameter, um die SDDL im Wert der `$sddl` Variablen anzugeben, und den **maximumreceivedobjectsizemb** -Parameter, um das Objektgrößen Limit zu erhöhen. Darüber hinaus verwendet er den **StartupScript** -Parameter, um ein Skript für die Sitzungskonfiguration anzugeben.

```powershell
$sddl = "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;FA;SA;GWGX;;WD)"
$sessionParams = @{
    Name="AdminShell"
    SecurityDescriptorSDDL=$sddl
    MaximumReceivedObjectSizeMB=20
    StartupScript="C:\scripts\AdminShell.ps1"
}
Register-PSSessionConfiguration @sessionParams
```

### Beispiel 4: Zurückgeben eines Konfigurations Container Elements

Dieses Beispiel zeigt, wie die **maintenanceshell** -Konfiguration registriert wird.
`Register-PSSessionConfiguration` Gibt ein **wsmanconfigcontainerelement** -Objekt zurück, das in der Variablen gespeichert ist `$s` . `Format-List` zeigt alle Eigenschaften des zurückgegebenen Objekts an. Die **PSPath** -Eigenschaft zeigt, dass das Objekt in einem Verzeichnis auf dem WSMan:-Laufwerk gespeichert ist. `Get-ChildItem` (Alias `dir` ) zeigt die Elemente im `WSMan:\LocalHost\PlugIn` Pfad an. Hierzu gehören die neue **maintenanceshell** -Konfiguration und die beiden Standardkonfigurationen, die in PowerShell enthalten sind.

```powershell
$s = Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
$s | Format-List -Property *
dir WSMan:\LocalHost\Plugin
```

```Output
PSPath            : Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell
PSParentPath      : Microsoft.WSMan.Management\WSMan::localhost\Plugin
PSChildName       : MaintenanceShell
PSDrive           : WSMan
PSProvider        : Microsoft.WSMan.Management\WSMan
PSIsContainer     : True
Keys              : {Name=MaintenanceShell}
Name              : MaintenanceShell
TypeNameOfElement : Container

Name                      Type                 Keys
----                      ----                 ----
MaintenanceShell          Container            {Name=MaintenanceShell}
microsoft.powershell      Container            {Name=microsoft.powershell}
microsoft.powershell32    Container            {Name=microsoft.powershell32}
```

### Beispiel 5: Registrieren einer Sitzungs Konfiguration mit einem Startskript

In diesem Beispiel erstellen und registrieren wir die **withprofile** -Sitzungs Konfiguration. Der **startupscript** -Parameter weist PowerShell an, das angegebene Skript für jede Sitzung auszuführen, die die Sitzungs Konfiguration verwendet.

```powershell
Register-PSSessionConfiguration -Name WithProfile -StartupScript Add-Profile.ps1
```

Das Skript enthält einen einzelnen Befehl, der DOT-Quellentnahme verwendet, um das **CurrentUserAllHosts** -Profil des Benutzers im aktuellen Bereich der Sitzung auszuführen.

Weitere Informationen zu Profilen finden Sie unter [about_Profiles](./About/about_Profiles.md). Weitere Informationen zur DOT-Quellentnahme finden Sie unter [about_Scopes](./About/about_Scopes.md).

## PARAMETERS

### -AccessMode

Aktiviert und deaktiviert die Sitzungskonfiguration und bestimmt, ob sie für Remote- oder lokale Sitzungen auf dem Computer verwendet werden kann. Zulässige Werte für diesen Parameter:

- Deaktiviert. Deaktiviert die Sitzungskonfiguration. Sie kann nicht für Remote- oder lokalen Zugriff auf den Computer verwendet werden.
- Lokal. Ermöglicht Benutzern des lokalen Computers die Verwendung der Sitzungs Konfiguration zum Erstellen einer lokalen Loopback Sitzung auf demselben Computer, verweigert aber Remote Benutzern den Zugriff.
- Remote. Ermöglicht lokalen und Remotebenutzern die Verwendung der Sitzungskonfiguration zum Erstellen von Sitzungen und Ausführen von Befehlen auf diesem Computer.

Der Standardwert ist Remote.

Andere Cmdlets können den Wert dieses Parameters später überschreiben. Beispielsweise ermöglicht das `Enable-PSRemoting` Cmdlet den Remote Zugriff auf alle Sitzungs Konfigurationen, das `Enable-PSSessionConfiguration` Cmdlet aktiviert Sitzungs Konfigurationen, und das `Disable-PSRemoting` Cmdlet verhindert den Remote Zugriff auf alle Sitzungs Konfigurationen.

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

Gibt den Pfad der \* **Assemblydatei** (. dll) an, die im Wert des AssemblyName-Parameters angegeben ist. Verwenden Sie diesen Parameter, wenn der Wert des **AssemblyName** -Parameters keinen Pfad enthält. Der Standardwert ist das aktuelle Verzeichnis.

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

Gibt den Namen einer \* Assemblydatei (. dll) an, in der der Konfigurationstyp definiert ist. Sie können den Pfad der DLL-Datei in diesem Parameter oder im Wert des **ApplicationBase** -Parameters angeben.

Dieser Parameter ist erforderlich, wenn Sie den **configurationtypame** -Parameter angeben.

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

Gibt den vollqualifizierten Namen des Microsoft .NET Framework-Typs an, der für diese Konfiguration verwendet wird. Der Typ, den Sie angeben, muss die **System.Management.Automation.Remoting.PSSessionConfiguration** Klasse implementieren.

Um die \* **Assemblydatei** (. dll) anzugeben, die den Konfigurationstyp implementiert, geben Sie die Parameter AssemblyName und **ApplicationBase** an.

Durch das Erstellen eines Typs können Sie weitere Aspekte der Sitzungs Konfiguration steuern, z. b. das verfügbar machen oder Ausblenden bestimmter Parameter von Cmdlets oder das Festlegen von Datengrößen-und Objektgrößen Beschränkungen, die von Benutzern nicht überschrieben werden können.

Wenn Sie diesen Parameter weglassen, wird die **DefaultRemotePowerShellConfiguration** -Klasse für die Sitzungskonfiguration verwendet.

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

Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, geben Sie den **noservicerestart** -Parameter an.

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

Gibt einen Grenzwert für die Datenmenge an, die in jedem einzelnen Remote Befehl an diesen Computer gesendet werden kann. Geben Sie die Datengröße in Megabyte (MB) ein. Der Standardwert ist 50 MB.

Wenn eine Datengrößenbeschränkung im Konfigurationstyp definiert ist, der im **ConfigurationTypeName** -Parameter angegeben ist, wird die Beschränkung im Konfigurationstyp verwendet und der Wert dieses Parameters ignoriert.

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maximumreceivedobjectsizemb

Gibt einen Grenzwert für die Datenmenge an, die in jedem einzelnen Objekt an diesen Computer gesendet werden kann.
Geben Sie die Datengröße in Megabyte ein. Der Standardwert ist 10 MB.

Wenn eine Objektgrößenbeschränkung im Konfigurationstyp definiert ist, der im **ConfigurationTypeName** -Parameter angegeben ist, wird die Beschränkung im Konfigurationstyp verwendet und der Wert dieses Parameters ignoriert.

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

Gibt die Module an, die automatisch in Sitzungen importiert werden, die die Sitzungs Konfiguration verwenden.

Standardmäßig wird nur **Microsoft. PowerShell. Core** in Sitzungen importiert. Wenn die Cmdlets nicht ausgeschlossen sind, können Sie verwenden, `Import-Module` um der Sitzung Module hinzuzufügen.

Die in diesem Parameterwert angegebenen Module werden in Ergänzungen zu Modulen importiert, die durch den **SessionType** -Parameter angegeben werden, und die Module, die im Schlüssel **modulestoimport** in der Sitzungs Konfigurationsdatei () aufgelistet sind `New-PSSessionConfigurationFile` . Einstellungen in der Sitzungskonfigurationsdatei können jedoch die von Modulen exportierten Befehle ausblenden oder verhindern, dass Benutzer sie verwenden.

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

Gibt einen Namen für die Sitzungskonfiguration an. Dieser Parameter ist erforderlich.

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

Wenn Sie einen `Register-PSSessionConfiguration` Befehl ausführen, werden Sie standardmäßig aufgefordert, den **WinRM** -Dienst neu zu starten, damit die neue Sitzungs Konfiguration wirksam wird. Bis der **WinRM** -Dienst neu gestartet wird, ist die neue Sitzungs Konfiguration nicht wirksam.

Um den **WinRM** -Dienst ohne Aufforderung neu zu starten, geben Sie den **Force** -Parameter an. Verwenden Sie das-Cmdlet, um den **WinRM** -Dienst manuell neu zu starten `Restart-Service` .

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

Gibt den Pfad und den Dateinamen einer Sitzungs Konfigurationsdatei (. PSSC) an, z. b. eine, die von erstellt wurde `New-PSSessionConfigurationFile` . Wenn Sie den Pfad weglassen, ist die Standardeinstellung das aktuelle Verzeichnis.

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

### -ProcessorArchitecture

Bestimmt, ob eine 32-Bit-oder 64-Bit-Version des PowerShell-Prozesses in Sitzungen gestartet wird, die diese Sitzungs Konfiguration verwenden. Die zulässigen Werte für diesen Parameter sind: x86 (32-Bit) und amd64 (64-Bit). Der Standardwert wird von der Prozessorarchitektur des Computers bestimmt, der die Sitzungskonfiguration hostet.

Sie können diesen Parameter verwenden, um eine 32-Bit-Sitzung auf einem 64-Bit-Computer zu erstellen. Versuche zum Erstellen eines 64-Bit-Prozesses auf einem 32-Bit-Computer schlagen fehl.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PA
Accepted values: x86, amd64

Required: False
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

Gibt eine Zeichenfolge für die Security Descriptor Definition Language (SDDL) der Konfiguration an.

Diese Zeichenfolge bestimmt die Berechtigungen, die erforderlich sind, um die Konfiguration für die neue Sitzung zu verwenden. Um eine Sitzungs Konfiguration in einer Sitzung zu verwenden, müssen die Benutzer mindestens über die Berechtigung Execute (aufrufen) für die Konfiguration verfügen.

Wenn die Sicherheitsbeschreibung komplex ist, sollten Sie den **ShowSecurityDescriptorUI** -Parameter anstelle dieses Parameters verwenden. Sie können nicht beide Parameter im selben Befehl verwenden.

Wenn Sie diesen Parameter weglassen, wird die Stamm-SDDL für den **WinRM** -Dienst für diese Konfiguration verwendet.
Verwenden Sie zum Anzeigen oder Ändern der Stamm-SDDL den WSMan-Anbieter. Beispiel: `Get-Item wsman:\localhost\service\rootSDDL`. Weitere Informationen zum WSMAN-Anbieter erhalten Sie, wenn Sie eingeben `Get-Help wsman` .

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

Gibt an, dass dieses Cmdlet ein Eigenschaften Blatt anzeigt, das Ihnen hilft, die SDDL für die Sitzungs Konfiguration zu erstellen. Das Eigenschaften Blatt wird angezeigt, nachdem Sie den `Register-PSSessionConfiguration` Befehl eingegeben und dann den **WinRM** -Dienst neu gestartet haben.

Denken Sie beim Festlegen der Berechtigungen für die Konfiguration daran, dass Benutzer mindestens über die Berechtigung Execute (aufrufen) verfügen müssen, um die Sitzungs Konfiguration in einer Sitzung zu verwenden.

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

Gibt den voll qualifizierten Pfad eines PowerShell-Skripts an. Das angegebene Skript wird in der neuen Sitzung ausgeführt, die die Sitzungskonfiguration verwendet.

Sie können das Skript verwenden, um die Sitzung zusätzlich zu konfigurieren. Wenn das Skript einen Fehler (auch einen Fehler ohne Abbruch) generiert, wird die Sitzung nicht erstellt, und der `New-PSSession` Befehl schlägt fehl.

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

### -Threadoptions

Gibt an, wie Threads erstellt und verwendet werden, wenn ein Befehl in der Sitzung ausgeführt wird. Zulässige Werte für diesen Parameter:

- Standard
- Reusethread
- UseCurrentThread
- Usenewthread

Der Standardwert ist **usecurrentthread**.

Weitere Informationen finden Sie unter [psthlesoptions-Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).

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

Gibt die Transport Option an.

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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

### -Threadapartmentstate

Gibt den Apartment Zustand des Threading Moduls an, das verwendet werden soll. Zulässige Werte sind:

- Unknown
- MTA
- STA

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Microsoft. WSMAN. Management. wsmanconfigcontainerelement

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

Zum Ausführen dieses Cmdlets müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.

Dieses Cmdlet generiert XML, das eine Plug-in-Konfiguration für Web Services for Management (WS-Management) darstellt, und sendet die XML-Datei an WS-Management, die das Plug-in auf dem lokalen Computer registriert ( `New-Item wsman:\localhost\plugin` ).

Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab. Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.

## VERWANDTE LINKS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan-Anbieter](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
