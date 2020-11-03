---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: d2b80640a5cdc985d34e39fe608950ea5f4dfe2d
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "93219140"
---
# Update-Help

## ZUSAMMENFASSUNG
Lädt die neuesten Hilfedateien auf den Computer herunter und installiert sie.

## SYNTAX

### Pfad (Standard)

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### LiteralPath

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Das `Update-Help` Cmdlet lädt die neuesten Hilfedateien für PowerShell-Module herunter und installiert Sie auf Ihrem Computer. PowerShell muss nicht neu gestartet werden, damit die Änderung wirksam wird. Mit dem- `Get-Help` Cmdlet können Sie die neuen Hilfedateien sofort anzeigen.

`Update-Help` Hiermit wird die Version der Hilfedateien auf Ihrem Computer überprüft. Wenn Sie keine Hilfedateien für ein Modul haben oder wenn Ihre Hilfedateien veraltet sind, werden `Update-Help` die neuesten Hilfedateien heruntergeladen. Die Hilfedateien können aus dem Internet oder aus einer Dateifreigabe heruntergeladen und installiert werden.

Ohne Parameter `Update-Help` aktualisiert die Hilfedateien für Module in der Sitzung und für alle installierten Module, die die aktualisierbare Hilfe unterstützen. Module, die installiert, aber nicht in der aktuellen Sitzung geladen werden, sind eingeschlossen. PowerShell-Module werden an einem Speicherort gespeichert, der in der `$env:PSModulePath` Umgebungsvariablen aufgeführt ist. Weitere Informationen hierzu finden Sie unter [about_Updatable_Help](./About/about_Updatable_Help.md).

Sie können den **Module** -Parameter verwenden, um Hilfedateien für ein bestimmtes Modul zu aktualisieren. Verwenden Sie den **UICulture** -Parameter, um Hilfedateien in mehreren Sprachen und Gebiets Schemas herunterzuladen.

Sie können auch `Update-Help` auf Computern verwenden, die nicht mit dem Internet verbunden sind. Verwenden Sie zunächst das `Save-Help` Cmdlet, um Hilfedateien aus dem Internet herunterzuladen, und speichern Sie Sie in einem freigegebenen Ordner, der für das System verfügbar ist, das nicht mit dem Internet verbunden ist. Verwenden Sie dann den **SourcePath** -Parameter von `Update-Help` , um die aktualisierten Hilfedateien aus dem freigegebenen herunterzuladen und auf dem Computer zu installieren.

Sie können Hilfe Updates automatisieren, indem Sie das `Update-Help` Cmdlet Ihrem PowerShell-Profil hinzufügen. Standardmäßig wird `Update-Help` auf jedem Computer nur einmal pro Tag ausgeführt. Um den Grenzwert von einmal täglich zu überschreiben, verwenden Sie den **Force** -Parameter.

Das `Update-Help` Cmdlet wurde in Windows PowerShell 3,0 eingeführt.

> [!IMPORTANT]
> `Update-Help` erfordert Administratorrechte in PowerShell 6,0 und niedriger.
> Mit PowerShell 6,1 und höher wird der Standard **Bereich** auf festgelegt `CurrentUser` .
> Vor PowerShell 6,1 war der **Bereichs** Parameter nicht verfügbar.
>
> Sie müssen Mitglied der Gruppe "Administratoren" auf dem Computer sein, um die Hilfedateien für die PowerShell-Kernmodule zu aktualisieren.
>
> Zum Herunterladen oder Aktualisieren der Hilfedateien für Module im PowerShell-Installationsverzeichnis ( `$PSHOME\Modules` ), einschließlich der PowerShell-Kernmodule, starten Sie PowerShell mit der Option **als Administrator ausführen** .
> Ein Beispiel für die Camel-Case-Schreibweise lautet: `Start-Process pwsh.exe -Verb RunAs`.

## BEISPIELE

### Beispiel 1: Aktualisieren der Hilfedateien für alle Module

Das- `Update-Help` Cmdlet aktualisiert Hilfedateien für installierte Module, die die aktualisierbare Hilfe unterstützen. Die Kultur Sprache der Benutzeroberfläche (UI) wird im Betriebssystem festgelegt.

```powershell
Update-Help
```

### Beispiel 2: Aktualisieren der Hilfedateien für angegebene Module

Das `Update-Help` Cmdlet aktualisiert Hilfedateien nur für Modulnamen, die mit **Microsoft. PowerShell** beginnen.

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### Beispiel 3: Aktualisieren von Hilfedateien für verschiedene Sprachen

Mit dem `Update-Help` -Cmdlet werden die Hilfedateien für Japanisch (ja-JP) und Englisch (en-US) für alle Module aktualisiert.

Wenn ein Modul keine Hilfedateien für eine angegebene UI-Kultur bereitstellt, wird eine Fehlermeldung für das Modul und die Benutzeroberflächen Kultur angezeigt. In diesem Beispiel gibt die Fehlermeldung an, dass die **ja-JP-** Hilfedateien für das Modul " **Microsoft. PowerShell. Utility** " nicht gefunden wurden.

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### Beispiel 4: Aktualisieren von Hilfedateien auf mehreren Computern aus einer Dateifreigabe

In diesem Beispiel werden aktualisierte Hilfedateien aus dem Internet heruntergeladen und in einer Dateifreigabe gespeichert. Es sind Benutzer Anmelde Informationen erforderlich, die über Berechtigungen zum Zugreifen auf die Dateifreigabe und zum Installieren von Updates verfügen. Wenn eine Dateifreigabe verwendet wird, ist es möglich, Computer zu aktualisieren, die sich hinter Firewalls befinden oder nicht mit dem Internet verbunden sind.

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

Der `Save-Help` Befehl lädt die neuesten Hilfedateien für alle Module herunter, die die aktualisierbare Hilfe unterstützen.
Der **DestinationPath** -Parameter speichert die Dateien in der `\\Server01\Share\PSHelp` Dateifreigabe. Der **Credential** -Parameter gibt einen Benutzer an, der über die Berechtigung für den Zugriff auf die Dateifreigabe verfügt.

Mit dem- `Invoke-Command` Cmdlet werden Remote `Update-Help` Befehle auf mehreren Computern ausgeführt. Mit dem Parameter " **Computername** " wird eine Liste von Remote Computern aus der **Servers.txt** Datei abgerufen. Der **ScriptBlock** -Parameter führt den `Update-Help` Befehl aus und verwendet den **SourcePath** -Parameter, um die Dateifreigabe anzugeben, die die aktualisierten Hilfedateien enthält. Der **Credential** -Parameter gibt einen Benutzer an, der auf die Dateifreigabe zugreifen und den Remote Befehl ausführen kann `Update-Help` .

### Beispiel 5: erhalten einer Liste mit aktualisierten Hilfedateien

Das- `Update-Help` Cmdlet aktualisiert die Hilfe für ein angegebenes Modul. Das Cmdlet verwendet den allgemeinen **verbose** -Parameter, um die Liste der aktualisierten Hilfedateien anzuzeigen. Sie können " **verbose** " verwenden, um die Ausgabe für alle Hilfedateien oder Hilfedateien für ein bestimmtes Modul anzuzeigen.

Ohne den **verbose** -Parameter werden `Update-Help` die Ergebnisse des Befehls nicht angezeigt. Mithilfe der ausführlichen Parameter Ausgabe können Sie überprüfen, ob die Hilfedateien aktualisiert wurden oder **ob die neueste** Version installiert ist.

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### Beispiel 6: Suchen von Modulen, die aktualisierbare Hilfe unterstützen

In diesem Beispiel werden Module aufgelistet, die aktualisierbare Hilfe unterstützen Der Befehl verwendet die **helpinfouri** -Eigenschaft des Moduls zur Identifizierung von Modulen, die die aktualisierbare Hilfe unterstützen. Die **helpinfouri** -Eigenschaft enthält eine Adresse, die umgeleitet wird, wenn das `Update-Help` Cmdlet ausgeführt wird.

```powershell
Get-Module -ListAvailable | Where-Object -Property HelpInfoUri
```

```output
   Directory: C:\program files\powershell\6\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   6.1.0.0    CimCmdlets                          Core      {Get-CimAssociatedInstance... }
Manifest   1.2.2.0    Microsoft.PowerShell.Archive        Desk      {Compress-Archive... }
Manifest   6.1.0.0    Microsoft.PowerShell.Diagnostics    Core      {Get-WinEvent, New-WinEvent}

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, ... }
Script     1.0.0.0    AssignedAccess                      Core,Desk {Clear-AssignedAccess, ... }
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, ... }
```

### Beispiel 7: Inventur aktualisierte Hilfedateien

In diesem Beispiel erstellt das Skript `Get-UpdateHelpVersion.ps1` eine Inventur der aktualisierbaren Hilfedateien für jedes Modul und ihre Versionsnummern.

Das Skript identifiziert Module, die die aktualisierbare Hilfe unterstützen, mithilfe der **helpinfouri** -Eigenschaft von Modulen. Bei Modulen, die die aktualisierbare Hilfe unterstützen, sucht das Skript nach der Hilfe Informationsdatei (* helpinfo.xml) und analysiert sie, um die aktuelle Versionsnummer zu ermitteln.

Das Skript verwendet die **pscustomobject** -Klasse und eine Hash Tabelle zum Erstellen eines benutzerdefinierten Ausgabe Objekts.

```powershell
# Get-UpdateHelpVersion.ps1
Param(
    [parameter(Mandatory=$False)]
    [String[]]
    $Module
)
$HelpInfoNamespace = @{helpInfo='http://schemas.microsoft.com/powershell/help/2010/05'}

if ($Module) { $Modules = Get-Module $Module -ListAvailable | where {$_.HelpInfoUri} }
else { $Modules = Get-Module -ListAvailable | where {$_.HelpInfoUri} }

foreach ($mModule in $Modules)
{
    $mDir = $mModule.ModuleBase

    if (Test-Path $mdir\*helpinfo.xml)
    {
        $mName=$mModule.Name
        $mNodes = dir $mdir\*helpinfo.xml -ErrorAction SilentlyContinue |
            Select-Xml -Namespace $HelpInfoNamespace -XPath "//helpInfo:UICulture"
        foreach ($mNode in $mNodes)
        {
            $mCulture=$mNode.Node.UICultureName
            $mVer=$mNode.Node.UICultureVersion

            [PSCustomObject]@{"ModuleName"=$mName; "Culture"=$mCulture; "Version"=$mVer}
        }
    }
}
```

```Output
ModuleName                              Culture                                 Version
----------                              -------                                 -------
ActiveDirectory                         en-US                                   3.0.0.0
ADCSAdministration                      en-US                                   3.0.0.0
ADCSDeployment                          en-US                                   3.0.0.0
ADDSDeployment                          en-US                                   3.0.0.0
ADFS                                    en-US                                   3.0.0.0
```

## PARAMETERS

### -Credential

Gibt die Anmelde Informationen eines Benutzers an, der über die Berechtigung zum Zugriff auf den durch **SourcePath** angegebenen Dateisystem Speicherort verfügt. Dieser Parameter ist nur gültig, wenn der **SourcePath** - oder **LiteralPath** -Parameter im Befehl verwendet wird.

Mit dem **Credential** -Parameter können Sie `Update-Help` Befehle mit dem **SourcePath** -Parameter auf Remote Computern ausführen. Durch die Angabe expliziter Anmelde Informationen können Sie den Befehl auf einem Remote Computer ausführen und auf eine Dateifreigabe auf einem dritten Computer zugreifen, ohne dass ein Zugriffs Verweigerungs Fehler aufgetreten ist oder die Verwendung der-Authentifizierung zum Delegieren von Anmelde Informationen verwendet wird.

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
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Gibt an, dass dieses Cmdlet nicht die einmal pro Tag-Einschränkung befolgt, die Versions Überprüfung überspringt und Dateien herunterlädt, die den Grenzwert von 1 GB überschreiten.

Ohne diesen Parameter wird `Update-Help` in jedem 24-Stunden-Zeitraum nur ein Mal ausgeführt. Downloads sind auf 1 GB an nicht komprimiertem Inhalt pro Modul beschränkt, und Hilfedateien werden nur installiert, wenn Sie neuer sind als die vorhandenen Dateien auf dem Computer.

Der Grenzwert von einmal täglich schützt die Server, die die Hilfedateien hosten, und ermöglicht es Ihnen, `Update-Help` Ihrem PowerShell-Profil einen Befehl hinzuzufügen, ohne dass die Ressourcenkosten für wiederholte Verbindungen oder Downloads anfallen.

Um die Hilfe für ein Modul in mehreren Benutzeroberflächenkulturen ohne den **Force** -Parameter zu aktualisieren, schließen Sie alle Benutzeroberflächenkulturen in denselben Befehl ein, z. B.:

`Update-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

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

### -Fullyqualifiedmodule

Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind.
Diese Module werden im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)beschrieben.

Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der im folgenden Format angegeben ist:

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

oder

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.

Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben.

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

Gibt den Ordner für aktualisierte Hilfedateien an, anstatt Sie aus dem Internet herunterzuladen. Verwenden Sie diesen Parameter oder **SourcePath** , wenn Sie das `Save-Help` Cmdlet zum Herunterladen von Hilfedateien in ein Verzeichnis verwendet haben.

Sie können ein Verzeichnis Objekt, z. b. aus den- `Get-Item` oder- `Get-ChildItem` Cmdlets, an Pipeline in Pipeline `Update-Help`

Im Gegensatz zum Wert von **SourcePath** wird der Wert von **literalpath** genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Modul

Aktualisiert die Hilfe für die angegebenen Module. Geben Sie mindestens einen Modulnamen oder ein Namensmuster in eine durch Trennzeichen getrennte Liste ein, oder geben Sie eine Datei an, in der in jeder Zeile ein Modulname aufgeführt ist. Platzhalterzeichen sind zulässig. Sie können Module aus dem `Get-Module` Cmdlet an das `Update-Help` Cmdlet weitergeben.

Die Module, die Sie angeben, müssen auf dem Computer installiert sein, aber Sie müssen nicht in die aktuelle Sitzung importiert werden. Sie können ein beliebiges Modul in der Sitzung oder ein beliebiges Modul angeben, das an einem in der Umgebungsvariablen aufgeführten Speicherort installiert ist `$env:PSModulePath` .

Der Wert `*` (alle) versucht, die Hilfe für alle Module zu aktualisieren, die auf dem Computer installiert sind.
Module, die keine aktualisierbare Hilfe unterstützen, sind enthalten. Dieser Wert generiert möglicherweise Fehler, wenn der Befehl Module erkennt, die die aktualisierbare Hilfe nicht unterstützen. Führen Sie stattdessen `Update-Help` ohne Parameter aus.

Der **Modul** Parameter des `Update-Help` Cmdlets akzeptiert nicht den vollständigen Pfad einer Modul Datei oder Modul Manifest-Datei. Um die Hilfe für ein Modul zu aktualisieren, das sich nicht an einem `$env:PSModulePath` Speicherort befindet, importieren Sie das Modul in die aktuelle Sitzung, bevor Sie den `Update-Help` Befehl ausführen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Recurse

Führt eine rekursive Suche nach Hilfedateien im angegebenen Verzeichnis aus. Dieser Parameter ist nur gültig, wenn der Befehl den **SourcePath** -Parameter verwendet.

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

### -Bereich

Gibt den Systembereich an, in dem die Hilfe aktualisiert wird. Updates im Bereich " **ALLUSERS** " erfordern Administratorrechte auf Windows-Systemen. Der- `-Scope` Parameter wurde in PowerShell Core Version 6,1 eingeführt.

**CurrentUser** ist der Standardbereich für Hilfedateien in PowerShell 6,1 und höher. **ALLUSERS** können angegeben werden, um die Hilfe für alle Benutzer zu installieren oder zu aktualisieren. Auf UNIX-Systemen `sudo` sind Berechtigungen erforderlich, um die Hilfe für alle Benutzer zu aktualisieren. Beispiel: `sudo pwsh -c Update-Help`

Gültige Werte sind:

- CurrentUser
- ALLUSERS

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourcePath

Gibt einen Dateisystem Ordner `Update-Help` an, in dem aktualisierte Hilfedateien abruft, anstatt Sie aus dem Internet herunterzuladen. Geben Sie den Pfad eines Ordners ein. Geben Sie keinen Dateinamen oder keine Dateinamenerweiterung an. Sie können einen Ordner, z. b. einen aus dem- `Get-Item` `Get-ChildItem` Cmdlet oder den-Cmdlet, in Pipeline `Update-Help`

Standardmäßig werden `Update-Help` aktualisierte Hilfedateien aus dem Internet heruntergeladen. Verwenden Sie **SourcePath** , wenn Sie das `Save-Help` Cmdlet zum Herunterladen aktualisierter Hilfedateien in ein Verzeichnis verwendet haben.

Um einen Standardwert für **SourcePath** anzugeben, navigieren Sie zu **Gruppenrichtlinie** , **Computer Konfiguration** , und **legen Sie den standardmäßigen Quellpfad für Update-Help fest**. Diese Gruppenrichtlinie Einstellung verhindert, dass Benutzer `Update-Help` zum Herunterladen von Hilfedateien aus dem Internet verwenden.
Weitere Informationen finden Sie unter [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UICulture

Gibt UI-Kultur Werte `Update-Help` an, die von zum erhalten aktualisierter Hilfedateien verwendet werden. Geben Sie einen oder mehrere Sprachcodes ein, z. b. **es-es** , eine Variable, die Kultur Objekte enthält, oder einen Befehl, der Kultur Objekte abruft, z. b. einen- `Get-Culture` oder- `Get-UICulture` Befehl. Platzhalter Zeichen sind nicht zulässig, und Sie können keinen partiellen Sprachcode, z. b. **de** , senden.

Standardmäßig ruft `Update-Help` Hilfedateien in der Benutzeroberflächen Kultur ab, die für das Betriebssystem festgelegt ist. Wenn Sie den **UICulture** -Parameter angeben, `Update-Help` sucht nur nach Hilfe für die angegebene Benutzeroberflächen Kultur.

> [!NOTE]
> Ubuntu 18,04 hat die Standardeinstellung für das Gebiets Schema in geändert `C.UTF.8` . Dies ist keine erkannte Benutzeroberflächen Kultur. `Update-Help` Wenn Sie diesen Parameter nicht mit einem unterstützten Gebiets Schema wie verwenden, wird die Hilfe im Hintergrund nicht heruntergeladen `en-US` . Dies kann auf jeder Plattform vorkommen, die einen nicht unterstützten Wert verwendet.

Befehle, die den **UICulture** -Parameter verwenden, werden nur dann erfolgreich ausgeführt, wenn das Modul Hilfedateien für die angegebene Benutzeroberflächenkultur bereitstellt. Wenn der Befehl fehlschlägt, da die angegebene Benutzeroberflächen Kultur nicht unterstützt wird, wird eine Fehlermeldung angezeigt.

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usedefault-Anmelde Informationen

Gibt an, dass `Update-Help` den Befehl, einschließlich des Internet Downloads, mithilfe der Anmelde Informationen des aktuellen Benutzers ausführt. Standardmäßig wird der Befehl ohne explizite Anmeldeinformationen ausgeführt.

Dieser Parameter ist nur wirksam, wenn der Webdownload NT LAN Manager (NTLM), Aushandlung oder Kerberos-basierte Authentifizierung verwendet.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. IO. directoriyinfo

Sie können einen Verzeichnispfad an über die Pipeline übergeben `Update-Help` .

### System. Management. Automation. psmoduleinfo

Sie können ein Modul Objekt über die Pipeline aus dem `Get-Module` Cmdlet an übergeben `Update-Help` .

## AUSGABEN

### Keine

`Update-Help` generiert keine Ausgabe.

## HINWEISE

Um die Hilfe für die PowerShell-Kernmodule zu aktualisieren, die die Befehle enthalten, die mit PowerShell installiert werden, oder ein beliebiges Modul im `$PSHOME\Modules` Verzeichnis, starten Sie PowerShell mit der Option **als Administrator ausführen**.

Nur Mitglieder der Gruppe "Administratoren" auf dem Computer können die Hilfe für die PowerShell-Kernmodule, die Befehle, die mit PowerShell installiert werden, und für Module im `$PSHOME\Modules` Ordner aktualisieren. Wenn Sie keine Berechtigung zum Aktualisieren von Hilfedateien haben, können Sie die Hilfedateien Online lesen. Beispiel: `Get-Help Update-Help -Online`.

Module sind die kleinste Einheit der aktualisierbaren Hilfe. Sie können die Hilfe für ein bestimmtes Cmdlet nicht aktualisieren. Um das Modul zu suchen, das ein bestimmtes Cmdlet enthält, verwenden Sie die **ModuleName** -Eigenschaft des `Get-Command` Cmdlets, z `(Get-Command Update-Help).ModuleName` . b..

Da Hilfedateien im Modul Verzeichnis installiert werden, kann das `Update-Help` Cmdlet die aktualisierte Hilfedatei nur für Module installieren, die auf dem Computer installiert sind. Allerdings `Save-Help` kann das Cmdlet die Hilfe für Module speichern, die nicht auf dem Computer installiert sind.

Wenn `Update-Help` keine aktualisierten Hilfedateien für ein Modul finden oder die aktualisierte Hilfe nicht in der angegebenen Sprache finden kann, wird Sie ohne Anzeige einer Fehlermeldung automatisch fortgesetzt. Verwenden Sie zum Anzeigen des Status und der Fortschrittsdetails den **Verbose** -Parameter.

Das `Update-Help` Cmdlet wurde in Windows PowerShell 3,0 eingeführt. Dies funktioniert nicht in früheren Versionen von PowerShell. Verwenden Sie auf Computern mit Windows PowerShell 2,0 und Windows PowerShell 3,0 das `Update-Help` -Cmdlet in einer Windows PowerShell 3,0-Sitzung, um Hilfedateien herunterzuladen und zu aktualisieren. Die Hilfedateien sind sowohl für Windows PowerShell 2,0 als auch für Windows PowerShell 3,0 verfügbar.

Die `Update-Help` -und- `Save-Help` Cmdlets verwenden die folgenden Ports, um Hilfedateien herunterzuladen: Port 80 für http und Port 443 für HTTPS.

`Update-Help` unterstützt alle Module und die PowerShell-Kern-Snap-Ins. Es werden keine anderen Snap-Ins unterstützt.

Um die Hilfe für ein Modul an einem Speicherort zu aktualisieren, der nicht in der `$env:PSModulePath` Umgebungsvariablen aufgeführt ist, importieren Sie das Modul in die aktuelle Sitzung, und führen Sie dann einen `Update-Help` Befehl aus. Führen `Update-Help` Sie ohne Parameter aus, oder verwenden Sie den **Module** -Parameter, um den Modulnamen anzugeben. Der **Modul** Parameter der `Update-Help` -und- `Save-Help` Cmdlets akzeptiert nicht den vollständigen Pfad einer Modul Datei oder Modul Manifest-Datei.

Jedes Modul kann die aktualisierbare Hilfe unterstützen. Anweisungen zur Unterstützung der aktualisierbaren Hilfe in den Modulen, die Sie erstellen, finden Sie [unter unterstützen der aktualisierbaren](/powershell/scripting/developer/module/supporting-updatable-help)

Die `Update-Help` `Save-Help` Cmdlets und werden auf Windows Preinstallation Environment (Windows PE) nicht unterstützt.

## VERWANDTE LINKS

[Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)

[Get-Help](Get-Help.md)

[Get-Module](Get-Module.md)

[Get-UICulture](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[Start-Job](Start-Job.md)

[Save-Help](Save-Help.md)
