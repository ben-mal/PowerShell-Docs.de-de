---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: 6ed809f357cf9424008b2207519abbde22fc9280
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209892"
---
# Save-Help

## ZUSAMMENFASSUNG
Lädt die neuesten Hilfedateien herunter und speichert sie in einem Dateisystemverzeichnis.

## SYNTAX

### Pfad (Standard)

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

### LiteralPath

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

## DESCRIPTION

Das **Save-Help-** Cmdlet lädt die neuesten Hilfedateien für PowerShell-Module herunter und speichert Sie in einem von Ihnen angegebenen Verzeichnis.
Mit dieser Funktion können Sie die Hilfedateien auf Computern aktualisieren, die keinen Internetzugriff haben, und sie vereinfacht die Aktualisierung der Hilfedateien auf mehreren Computern.

In Windows PowerShell 3,0 funktionierte **Save-Help** nur für Module, die auf dem lokalen Computer installiert sind.
Obwohl es möglich war, ein Modul von einem Remote Computer zu importieren oder einen Verweis auf ein **psmoduleinfo** -Objekt von einem Remote Computer mithilfe von PowerShell-Remoting abzurufen, wurde die **helpinfouri** -Eigenschaft nicht beibehalten, und **Save-Help** funktionierte nicht für die Remote Modul-Hilfe.

In Windows PowerShell 4,0 wird die **helpinfouri** -Eigenschaft über PowerShell-Remoting beibehalten, sodass **Save-Help** für Module funktioniert, die auf Remote Computern installiert sind.
Es ist auch möglich, ein **psmoduleinfo** -Objekt auf einem Datenträger oder Wechselmedium zu speichern, indem Export-Clixml auf einem Computer ausgeführt wird, der nicht über Internet Zugriff verfügt, das Objekt auf einem Computer mit Internet Zugriff zu importieren und dann **Save-Help** auf dem **psmoduleinfo** -Objekt auszuführen.
Die gespeicherte Hilfe kann mithilfe von Wechselmedien (z. b. einem USB-Laufwerk) auf den Remote Computer übertragen werden.
Die Hilfe kann durch Ausführen von **Update-Help** auf dem Remote Computer installiert werden.
Dieser Prozess kann zum Installieren der Hilfe auf Computern verwendet werden, die überhaupt keinen Zugriff auf das Netzwerk haben.

Führen Sie zum Installieren gespeicherter Hilfedateien das Update-Help-Cmdlet aus.
Fügen Sie seinen *SourcePath* -Parameter hinzu, um den Ordner anzugeben, in dem Sie die Hilfedateien gespeichert haben.

Ohne Parameter lädt ein **Save-Help** -Befehl die neueste Hilfe für alle Module in der Sitzung und für Module herunter, die auf dem Computer an einem in der **PSModulePath** -Umgebungsvariablen aufgeführten Speicherort installiert sind.
Diese Aktion überspringt Module, die eine aktualisierbare Hilfe ohne Warnung nicht unterstützen.

Das **Save-Help-** Cmdlet überprüft die Version der Hilfedateien im Zielordner.
Wenn neuere Hilfedateien verfügbar sind, lädt dieses Cmdlet die neuesten Hilfedateien aus dem Internet herunter und speichert Sie anschließend im Ordner.
Das **Save-Help-** Cmdlet funktioniert genauso wie das Update-Help-Cmdlet, mit dem Unterschied, dass es die heruntergeladenen CAB-Dateien speichert, anstatt die Hilfedateien aus den CAB-Dateien zu extrahieren und auf dem Computer zu installieren.

Die gespeicherte Hilfe für jedes Modul besteht aus einer Hilfe Informationsdatei (helpinfo XML) und einer CAB-Datei für die Hilfedateien jeder Benutzeroberflächen Kultur.
Sie müssen die Hilfedateien nicht aus der CAB-Datei extrahieren.
Das **Update-Help-** Cmdlet extrahiert die Hilfedateien, überprüft den XML-Code auf Sicherheit und installiert dann die Hilfedateien und die Hilfe Informationsdatei in einem sprachspezifischen Unterordner des Modul Ordners.

Um die Hilfedateien für Module im PowerShell-Installationsordner ($PSHome \modules) zu speichern, starten Sie PowerShell mit der Option als Administrator ausführen.
Sie müssen ein Mitglied der Gruppe „Administratoren“ auf dem Computer sein, um die Hilfedateien für diese Module herunterzuladen.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Speichern der Hilfe für das dhcpserver-Modul

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module, save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

Dieses Beispiel zeigt drei verschiedene Möglichkeiten, **Save-Help** zu verwenden, um die Hilfe für das **DHCPServer** -Modul von einem Client Computer mit Internet Verbindung zu speichern, ohne das **DHCPServer** -Modul oder die DHCP-Server Rolle auf dem lokalen Computer zu installieren.

### Beispiel 2: Installieren der Hilfe für das dhcpserver-Modul

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

In diesem Beispiel wird gezeigt, wie die Hilfe, die Sie in Beispiel 1 für das **DHCPServer** -Modul gespeichert haben, auf einem Computer installiert wird, der nicht über Internet Zugriff verfügt.

### Beispiel 3: Speichern der Hilfe für alle Module

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

Mit diesem Befehl werden die neuesten Hilfedateien für alle Module in der Benutzeroberflächenkultur für Windows auf den lokalen Computer heruntergeladen.
Die Hilfedateien werden im \\ \\ Ordner Server01\Fileshare01 gespeichert.

### Beispiel 4: Speichern der Hilfe für ein Modul auf dem Computer

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

Mit diesem Befehl werden die neuesten Hilfedateien für das **Server Manager** -Modul heruntergeladen und dann im \\ \\ Ordner Server01\Fileshare01 gespeichert.

Wenn ein Modul auf dem Computer installiert ist, können Sie den Namen des Moduls als Wert des *Module* -Parameters eingeben, auch wenn das Modul nicht in die aktuelle Sitzung importiert wird.

Der Befehl verwendet den *Credential* -Parameter, um die Anmeldeinformationen eines Benutzers anzugeben, der über die Berechtigung zum Schreiben in der Dateifreigabe verfügt.

### Beispiel 5: Speichern der Hilfe für ein Modul auf einem anderen Computer

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

Mit diesen Befehlen werden die neuesten Hilfedateien für das **customsql** -Modul heruntergeladen und im \\ \\ Ordner Server01\Fileshare01 gespeichert.

Da das **customsql** -Modul nicht auf dem Computer installiert ist, enthält die Sequenz einen Invoke-Command Befehl, mit dem das Modul Objekt für das customsql-Modul vom Server02-Computer abgerufen und dann das Modul Objekt an das **Save-Help-** Cmdlet weitergeleitet wird.

Wenn ein Modul nicht auf dem Computer installiert ist, benötigt **Save-Help** das Modulobjekt, das Informationen über den Speicherort der neuesten Hilfedateien enthält.

### Beispiel 6: Speichern der Hilfe für ein Modul in mehreren Sprachen

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

Dieser Befehl speichert die Hilfe für die PowerShell-Kernmodule in vier verschiedenen Benutzeroberflächen Kulturen.
Die Sprachpakete für diese Gebiets Schemas müssen nicht auf dem Computer installiert werden.

Mit **Save-Help** können Hilfedateien für Module in verschiedenen Benutzeroberflächen Kulturen nur heruntergeladen werden, wenn der Modul Besitzer die übersetzten Dateien im Internet verfügbar macht.

### Beispiel 7: Speichern Sie die Hilfe mehr als einmal täglich.

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

Dieser Befehl speichert die Hilfe für alle Module, die auf dem Computer installiert sind.
Der Befehl gibt den *Force* -Parameter an, um die Regel zu überschreiben, die verhindert, dass das **Save-Help-** Cmdlet die Hilfe mehr als einmal in jedem 24-Stunden-Zeitraum herunterlädt.

Der *Force* -Parameter überschreibt auch die 1 GB-Einschränkung und umgeht die Versions Überprüfung.
Daher können Sie Dateien auch dann herunterladen, wenn die Version nicht höher als die Version im Zielordner ist.

Der Befehl verwendet das **Save-Help-** Cmdlet zum herunterladen und Speichern der Hilfedateien im angegebenen Ordner.
Der *Force* -Parameter ist erforderlich, wenn Sie einen **Save-Help-** Befehl mehrmals täglich ausführen müssen.

## PARAMETERS

### -Credential

Gibt Benutzer Anmelde Informationen an. Dieses Cmdlet führt den Befehl mithilfe der Anmelde Informationen eines Benutzers aus, der über die Berechtigung zum Zugreifen auf den Dateisystem Speicherort verfügt, der durch den **DestinationPath** -Parameter angegeben wird. Dieser Parameter ist nur gültig, wenn der **DestinationPath** -Parameter oder der **literalpath** -Parameter im Befehl verwendet wird.

Mit diesem Parameter können Sie `Save-Help` Befehle ausführen, die den **DestinationPath** -Parameter auf Remote Computern verwenden. Durch die Angabe expliziter Anmelde Informationen können Sie den Befehl auf einem Remote Computer ausführen und auf eine Dateifreigabe auf einem dritten Computer zugreifen, ohne dass ein Zugriffs Verweigerungs Fehler aufgetreten ist oder die Verwendung der-Authentifizierung zum Delegieren von Anmelde Informationen verwendet wird.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

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

### -DestinationPath

Gibt den Pfad des Ordners an, in dem die Hilfedateien gespeichert werden.
Geben Sie keinen Dateinamen und keine Dateierweiterung an.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Gibt an, dass dieses Cmdlet nicht die einmal pro Tag-Einschränkung befolgt, die Versions Überprüfung überspringt und Dateien herunterlädt, die den Grenzwert von 1 GB überschreiten.

Ohne diesen Parameter ist der **Save-Help** -Befehl nur einmal alle 24 Stunden für jedes Modul zulässig, Downloads sind auf 1 GB an nicht komprimiertem Inhalt pro Modul beschränkt, und Hilfedateien für ein Modul werden nur installiert, wenn sie neuer sind als die Dateien auf dem Computer.

Der Grenzwert von einmal täglich schützt die Server, die die Hilfedateien hosten, und ermöglicht es Ihnen, Ihrem PowerShell-Profil einen **Save-Help-** Befehl hinzuzufügen.

Um die Hilfe für ein Modul in mehreren Benutzeroberflächen Kulturen ohne den *Force* -Parameter zu speichern, schließen Sie alle Benutzeroberflächen Kulturen in denselben Befehl ein, z. b.: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fullyqualifiedmodule

Gibt Module an, deren Namen in Form von modulespecification-Objekten angegeben sind.
Dies wird im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](https://msdn.microsoft.com/library/jj136290) in der MSDN Library beschrieben.
Der *fullyqualifiedmodule* -Parameter nimmt z. b. einen Modulnamen an, der im Format @ {ModuleName = "ModuleName" angegeben ist; Moduleversion = "version_number"} oder @ {ModuleName = "ModuleName"; Moduleversion = "version_number"; GUID = "GUID"}.
**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.

Sie können den *fullyqualifiedmodule* -Parameter nicht im selben Befehl wie einen *Modul* Parameter angeben.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Literalpath

Gibt den Pfad des Ziel Ordners an.
Im Gegensatz zum Wert des *DestinationPath* -Parameters wird der Wert des *literalpath* -Parameters genau so verwendet, wie er eingegeben wurde.
Es werden keine Zeichen als Platzhalter interpretiert.
Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.
Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Modul

Gibt Module an, für die dieses Cmdlet die Hilfe herunterlädt.
Geben Sie mindestens einen Modulnamen oder ein Namensmuster in eine durch Trennzeichen getrennte Liste oder in eine Datei ein, die in jeder Zeile über einen Modulnamen verfügt.
Platzhalterzeichen sind zulässig.
Sie können Modul Objekte auch über das Cmdlet "Get-Module" an **Save-Help** übergeben.

Standardmäßig lädt **Save-Help** die Hilfe für alle Module herunter, die die aktualisierbare Hilfe unterstützen und die auf dem lokalen Computer in einem in der **PSModulePath** -Umgebungsvariablen aufgeführten Verzeichnis installiert sind.

Um die Hilfe für Module zu speichern, die nicht auf dem Computer installiert sind, führen **Sie einen Get-Module-** Befehl auf einem Remote Computer aus.
Übergeben Sie die resultierenden Modulobjekte über die Pipeline an das **Save-Help** -Cmdlet, oder senden Sie die Modulobjekte als Wert der *Module* - oder *InputObject* -Parameter.

Wenn das angegebene Modul auf dem Computer installiert ist, können Sie den Modulnamen oder ein Modulobjekt eingeben.
Wenn das Modul nicht auf dem Computer installiert ist, müssen Sie ein Modulobjekt eingeben, z. B. ein vom **Get-Module** -Cmdlet zurückgegebenes Objekt.

Der *Modul* Parameter des **Save-Help-** Cmdlets akzeptiert nicht den vollständigen Pfad einer Modul Datei oder Modul Manifest-Datei.
Um die Hilfe für ein Modul zu speichern, das sich nicht an einem **psmodulepath** -Speicherort befindet, importieren Sie das Modul in die aktuelle Sitzung, bevor Sie den **Save-Help-** Befehl ausführen.

Der Wert "*" (alle) versucht, die Hilfe für alle Module zu aktualisieren, die auf dem Computer installiert sind.
Dies schließt Module ein, die die aktualisierbare Hilfe nicht unterstützen.
Dieser Wert generiert möglicherweise Fehler, wenn der Befehl Module erkennt, die die aktualisierbare Hilfe nicht unterstützen.

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -UICulture

Gibt Werte für die Benutzeroberflächen Kultur an, für die dieses Cmdlet aktualisierte Hilfedateien abruft.
Geben Sie einen oder mehrere Sprachcodes ein, z. b. es-es, eine Variable, die Kultur Objekte enthält, oder einen Befehl, der Kultur Objekte abruft, z. b. einen Get-Culture oder Get-UICulture Befehl.

Platzhalterzeichen sind nicht zulässig.
Geben Sie keinen partiellen Sprachcode, z. b. "de", an.

Standardmäßig ruft **Save-Help** Hilfedateien in der Benutzeroberflächen Kultur ab, die für Windows oder die zugehörige Fall backkultur festgelegt ist.
Wenn Sie den *UICulture* -Parameter angeben, sucht **Save-Help** nur nach Hilfe für die angegebene Benutzeroberflächen Kultur, nicht in einer Fall backkultur.

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: Current UI culture
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usedefault-Anmelde Informationen

Gibt an, dass dieses Cmdlet den Befehl, einschließlich des Webdownloads, mit den Anmelde Informationen des aktuellen Benutzers ausführt.
Standardmäßig wird der Befehl ohne explizite Anmeldeinformationen ausgeführt.

Dieser Parameter gilt nur, wenn der Webdownload eine NTLM-, Negotiate- oder Kerberos-basierte Authentifizierung verwendet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bereich

Dieser Parameter führt in diesem Cmdlet keine Aktion aus.

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psmoduleinfo

Sie können ein Modul Objekt aus dem **Get-Module-** Cmdlet an den *Module* -Parameter von **Save-Help** übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Um die Hilfe für Module im Ordner "$PSHome \modules" zu speichern, starten Sie PowerShell mithilfe der Option als Administrator ausführen. Nur Mitglieder der Gruppe "Administratoren" auf dem Computer können die Hilfe für Module im Ordner "$PSHome \modules" herunterladen.
* Die gespeicherte Hilfe für jedes Modul besteht aus einer Hilfe Informationsdatei (helpinfo XML) und einer CAB-Datei für die Hilfedateien jeder Benutzeroberflächen Kultur. Sie müssen die Hilfedateien nicht aus der CAB-Datei extrahieren. Das Update-Help-Cmdlet extrahiert die Hilfedateien, überprüft den XML-Code und installiert dann die Hilfedateien und die Hilfe Informationsdatei in einem sprachspezifischen Unterordner des Modul Ordners.
* Das **Save-Help** -Cmdlet kann die Hilfe für Module speichern, die nicht auf dem Computer installiert sind. Da jedoch Hilfedateien im Modul Ordner installiert werden, kann das **Update-Help-** Cmdlet die aktualisierte Hilfedatei nur für Module installieren, die auf dem Computer installiert sind.
* Wenn **Save-Help** keine aktualisierten Hilfedateien für ein Modul oder aktualisierte Hilfedateien in der angegebenen Sprache finden kann, wird es weiterhin im Hintergrund ausgeführt, ohne eine Fehlermeldung anzuzeigen. Um anzuzeigen, welche Dateien durch den Befehl gespeichert wurden, geben Sie den *verbose* -Parameter an.
* Module sind die kleinste Einheit der aktualisierbaren Hilfe. Sie können die Hilfe nicht für ein bestimmtes Cmdlet speichern, sondern nur für alle Cmdlets im Modul. Um das Modul zu suchen, das ein bestimmtes Cmdlet enthält, verwenden Sie die **ModuleName** -Eigenschaft in Verbindung mit dem Get-Command-Cmdlet, z. b. `(Get-Command \<cmdlet-name\>).ModuleName`
* **Save-Help** unterstützt alle Module und die PowerShell-Kern-Snap-Ins. Es werden keine anderen Snap-Ins unterstützt.
* Die Cmdlets " **Update-Help** " und " **Save-Help** " verwenden die folgenden Ports, um Hilfedateien herunterzuladen: Port 80 für http und Port 443 für HTTPS.
* Die Cmdlets **Update-Help** und **Save-Help** werden unter Windows Preinstallation Environment (Windows PE) nicht unterstützt.

## VERWANDTE LINKS

[Get-Help](Get-Help.md)

[Get-Module](Get-Module.md)

[Update-Help](Update-Help.md)
