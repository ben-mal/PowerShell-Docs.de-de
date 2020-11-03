---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-PSSession
ms.openlocfilehash: ff1b709b363684e27a1f4eb8fdeada2d5ae1d588
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211036"
---
# Export-PSSession

## ZUSAMMENFASSUNG

Exportiert Befehle aus einer anderen Sitzung und speichert Sie in einem PowerShell-Modul.

## SYNTAX

### Alle

```
Export-PSSession [-OutputModule] <String> [-Force] [-Encoding <Encoding>]
 [[-CommandName] <String[]>] [-AllowClobber] [-ArgumentList <Object[]>]
 [-CommandType <CommandTypes>] [-Module <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-FormatTypeName] <String[]>] [-Certificate <X509Certificate2>] [-Session] <PSSession>
 [<CommonParameters>]
```

## DESCRIPTION

Das `Export-PSSession` Cmdlet ruft Cmdlets, Funktionen, Aliase und andere Befehls Typen aus einer anderen PowerShell-Sitzung (PSSession) auf einem lokalen Computer oder einem Remote Computer ab und speichert Sie in einem PowerShell-Modul. Verwenden Sie das-Cmdlet, um der aktuellen Sitzung die Befehle aus dem Modul hinzuzufügen `Import-Module` .

Im Gegensatz zu `Import-PSSession` , das Befehle aus einer anderen PSSession in die aktuelle Sitzung importiert, `Export-PSSession` speichert die Befehle in einem Modul. Die Befehle werden nicht in die aktuelle Sitzung importiert.

Um Befehle zu exportieren, verwenden `New-PSSession` Sie das Cmdlet, um eine PSSession mit den Befehlen zu erstellen, die Sie exportieren möchten. Verwenden Sie dann das- `Export-PSSession` Cmdlet, um die Befehle zu exportieren.

Um Konflikte bei Befehlsnamen zu vermeiden, wird standardmäßig `Export-PSSession` alle Befehle exportiert, mit Ausnahme der Befehle, die in der aktuellen Sitzung vorhanden sind. Sie können den **CommandName** -Parameter verwenden, um die Befehle anzugeben, die exportiert werden sollen.

Das- `Export-PSSession` Cmdlet verwendet das implizite Remoting-Feature von PowerShell. Wenn Sie Befehle in die aktuelle Sitzung importieren, werden Sie implizit in der ursprünglichen Sitzung oder in einer ähnlichen Sitzung auf dem ursprünglichen Computer ausgeführt.

## BEISPIELE

### Beispiel 1: Exportieren von Befehlen aus einer PSSession

In diesem Beispiel wird eine neue PSSession vom lokalen Computer zum Server01-Computer erstellt. Alle Befehle, mit Ausnahme derjenigen, die in der aktuellen Sitzung vorhanden sind, werden auf dem lokalen Computer in das Modul mit dem Namen Server01 exportiert. Der Export umfasst die Formatierungsdaten für die Befehle.

```powershell
$S = New-PSSession -ComputerName Server01
Export-PSSession -Session $S -OutputModule Server01
```

Der `New-PSSession` Befehl erstellt eine PSSession auf dem Server01-Computer. Die PSSession wird in der `$S` Variablen gespeichert. Der `Export-PSSession` Befehl exportiert die `$S` Befehle der Variablen und formatiert Daten in das Modul Server01.

### Beispiel 2: Exportieren der Befehle "Get" und "Set"

In diesem Beispiel werden alle `Get` -und- `Set` Befehle von einem Server exportiert.

```powershell
$S = New-PSSession -ConnectionUri https://exchange.microsoft.com/mailbox -Credential exchangeadmin01@hotmail.com -Authentication Negotiate
Export-PSSession -Session $S -Module exch* -CommandName Get-*, Set-* -FormatTypeName * -OutputModule $PSHOME\Modules\Exchange -Encoding ASCII
```

Mit diesen Befehlen werden `Get` die `Set` Befehle und aus einem Microsoft Exchange Server-Snap-in auf einem Remote Computer in ein Exchange-Modul im `$PSHOME\Modules` Verzeichnis auf dem lokalen Computer exportiert.
Wenn Sie das Modul in das `$PSHOME\Modules` Verzeichnis versetzen, ist es für alle Benutzer des Computers zugänglich.

### Beispiel 3: Exportieren von Befehlen von einem Remote Computer

In diesem Beispiel werden Cmdlets aus einer PSSession auf einem Remote Computer exportiert und in einem Modul auf dem lokalen Computer gespeichert. Die Cmdlets aus dem Modul werden der aktuellen Sitzung hinzugefügt, sodass Sie verwendet werden können.

```powershell
$S = New-PSSession -ComputerName Server01 -Credential Server01\User01
Export-PSSession -Session $S -OutputModule TestCmdlets -Type Cmdlet -CommandName *test* -FormatTypeName *
Remove-PSSession $S
Import-Module TestCmdlets
Get-Help Test*
Test-Files
```

Der `New-PSSession` Befehl erstellt eine PSSession auf dem Server01-Computer und speichert Sie in der `$S` Variablen. Der `Export-PSSession` Befehl exportiert die Cmdlets, deren Namen mit "Test" beginnen, aus der PSSession in in `$S` das testcmdlets-Modul auf dem lokalen Computer.

Das- `Remove-PSSession` Cmdlet löscht die PSSession in `$S` aus der aktuellen Sitzung. Dieser Befehl zeigt, dass die PSSession nicht aktiv sein muss, um die Befehle zu verwenden, die aus der Sitzung importiert wurden. Mit dem- `Import-Module` Cmdlet werden die Cmdlets im testcmdlets-Modul zur aktuellen Sitzung hinzugefügt. Der Befehl kann jederzeit in einer beliebigen Sitzung ausgeführt werden.

Das- `Get-Help` Cmdlet ruft Hilfe für Cmdlets ab, deren Namen mit "Test" beginnen. Nachdem die Befehle in einem Modul zur aktuellen Sitzung hinzugefügt wurden, können Sie die `Get-Help` -und- `Get-Command` Cmdlets verwenden, um mehr über die importierten Befehle zu erfahren. Das `Test-Files` Cmdlet wurde vom Server01-Computer exportiert und der Sitzung hinzugefügt. Das- `Test-Files` Cmdlet wird in einer Remote Sitzung auf dem Computer ausgeführt, von dem aus der Befehl importiert wurde. PowerShell erstellt eine Sitzung aus Informationen, die im testcmdlets-Modul gespeichert sind.

### Beispiel 4: Exportieren und Clobber-Befehle in der aktuellen Sitzung

In diesem Beispiel werden die in einer Variablen gespeicherten Befehle in die aktuelle Sitzung exportiert.

```powershell
Export-PSSession -Session $S -AllowClobber -OutputModule AllCommands
```

Dieser `Export-PSSession` Befehl exportiert alle Befehle und alle Formatierungsdaten aus der PSSession in der `$S` Variablen in die aktuelle Sitzung. Der **allowclobber** -Parameter enthält Befehle mit denselben Namen wie die Befehle in der aktuellen Sitzung.

### Beispiel 5: Exportieren von Befehlen aus einer geschlossenen PSSession

In diesem Beispiel wird gezeigt, wie die exportierten Befehle mit besonderen Optionen ausgeführt werden, wenn die PSSession, die die exportierten Befehle erstellt hat, geschlossen ist.

Wenn die ursprüngliche Remote Sitzung geschlossen wird, wenn ein Modul importiert wird, verwendet das Modul eine beliebige offene Remote Sitzung, die eine Verbindung mit dem ursprünglichen Computer herstellt. Wenn keine aktuelle Sitzung zum Ursprungs Computer vorhanden ist, wird eine Sitzung vom Modul wieder hergestellt.

Um exportierte Befehle mit speziellen Optionen in einer Remote Sitzung auszuführen, müssen Sie eine Remote Sitzung mit diesen Optionen erstellen, bevor Sie das Modul importieren. Verwenden des `New-PSSession` Cmdlets mit dem **sessionoption** -Parameter

```powershell
$Options = New-PSSessionOption -NoMachineProfile
$S = New-PSSession -ComputerName Server01 -SessionOption $Options
Export-PSSession -Session $S -OutputModule Server01
Remove-PSSession $S
New-PSSession -ComputerName Server01 -SessionOption $Options
Import-Module Server01
```

`New-PSSessionOption`Mit dem-Cmdlet wird ein **pssessionoption** -Objekt erstellt, und das-Objekt wird in der `$Options` Variablen gespeichert. Der `New-PSSession` Befehl erstellt eine PSSession auf dem Server01-Computer.
Der **sessionoption** -Parameter verwendet das in gespeicherte-Objekt `$Options` . Die Sitzung wird in der `$S` Variablen gespeichert.

Mit dem- `Export-PSSession` Cmdlet werden Befehle aus der PSSession in in `$S` das Server01-Modul exportiert.
Das- `Remove-PSSession` Cmdlet löscht die PSSession in der `$S` Variablen.

Das- `New-PSSession` Cmdlet erstellt eine neue PSSession, die eine Verbindung mit dem Server01-Computer herstellt. Der **sessionoption** -Parameter verwendet das in gespeicherte-Objekt `$Options` . Mit dem- `Import-Module` Cmdlet werden die Befehle aus dem Server01-Modul importiert. Die Befehle im Modul werden in der PSSession auf dem Computer Server01 ausgeführt.

## PARAMETERS

### -Allowclobber

Exportiert die angegebenen Befehle, auch wenn sie denselben Namen wie die Befehle in der aktuellen Sitzung haben.

Wenn Sie einen Befehl mit demselben Namen wie einen Befehl in der aktuellen Sitzung exportieren, werden die ursprünglichen Befehle durch den exportierten Befehl ausgeblendet oder ersetzt. Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).

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

### -Argumentlist

Exportiert die Variante des Befehls, die sich aus der Verwendung der angegebenen Argumente (Parameterwerte) ergibt.

So exportieren Sie z. b. die Variante des `Get-Item` Befehls im Zertifikat (CERT:) Geben Sie in die PSSession in ein `$S` , und geben Sie ein `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zertifikat

Gibt das Client Zertifikat an, das zum Signieren der Format Dateien (* .Format.ps1XML) oder Skript Moduldateien (. psm1) im Modul verwendet wird, das von `Export-PSSession` erstellt wird. Geben Sie eine Variable ein, die ein Zertifikat, einen Befehl oder einen Ausdruck enthält, durch die das Zertifikat abgerufen wird.

Um ein Zertifikat zu suchen, verwenden Sie das `Get-PfxCertificate` Cmdlet, oder verwenden Sie das `Get-ChildItem` Cmdlet im Zertifikat (CERT:). Antrie. Wenn das Zertifikat ungültig ist oder keine qualifizierte Zertifizierungsstelle aufweist, verursacht der Befehl einen Fehler.

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandName

Exportiert nur die Befehle mit den angegebenen Namen oder Namensmustern. Platzhalter sind zulässig. Verwenden Sie **CommandName** oder den Alias **Name** .

Standardmäßig `Export-PSSession` exportiert alle Befehle aus der PSSession mit Ausnahme von Befehlen, die denselben Namen wie die Befehle in der aktuellen Sitzung haben. Dadurch wird verhindert, dass Befehle ausgeblendet oder durch Befehle in der aktuellen Sitzung ersetzt werden. Verwenden Sie den **allowclobber** -Parameter, um alle Befehle zu exportieren, auch solche, die andere Befehle ausblenden oder ersetzen.

Wenn Sie den **CommandName** -Parameter verwenden, werden die Formatierungs Dateien für die Befehle nicht exportiert, es sei denn, Sie verwenden den **formattypame** -Parameter. Wenn Sie den **formattypame** -Parameter verwenden, werden auch keine Befehle exportiert, es sei denn, Sie verwenden den **CommandName** -Parameter.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: True
```

### -CommandType

Exportiert nur die angegebenen Typen von Befehlsobjekten. Verwenden Sie **CommandType** oder dessen Aliasname **Type** .

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- Alias. Alle PowerShell-Aliase in der aktuellen Sitzung.
- Alle Alle Befehlstypen. Dies entspricht `Get-Command -Name *` .
- Anwendung: Alle anderen Dateien als PowerShell-Dateien in Pfaden, die in der PATH-Umgebungsvariablen ( `$env:path` ) aufgelistet sind, einschließlich txt-, exe-und dll-Dateien.
- Cmdlet. Die Cmdlets in der aktuellen Sitzung. Das-Cmdlet ist die Standardeinstellung.
- Konfiguration Eine PowerShell-Konfiguration. Weitere Informationen finden Sie unter [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).
- Externalscript. Alle PS1-Dateien in den Pfaden, die in der PATH-Umgebungsvariablen () aufgelistet sind `$env:path` .
- Filter und function. Alle PowerShell-Funktionen.
- Skript. Skriptblöcke in der aktuellen Sitzung.
- Workflow. Einen PowerShell-Workflow. Weitere Informationen finden Sie unter [about_Workflows](/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1).

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, All, Application, Cmdlet, Configuration, ExternalScript, Filter, Function, Script, Workflow

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### -Codierung

Gibt den Typ der Codierung für die Zieldatei an. Der Standardwert ist `utf8NoBOM`.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- `ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).
- `bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.
- `oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.
- `unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.
- `utf7`: Codiert im UTF-7-Format.
- `utf8`: Codiert im UTF-8-Format.
- `utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).
- `utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).
- `utf32`: Codiert im UTF-32-Format.


Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.). Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Überschreibt eine oder mehrere vorhandene Ausgabedateien, auch wenn die Datei das Schreibschutzattribut aufweist.

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

### -Formattyname

Exportiert Formatierungsanweisungen nur für die angegebenen Microsoft .NET Framework-Typen. Geben Sie die Typnamen ein. Standardmäßig `Export-PSSession` exportiert Formatierungs Anweisungen für alle .NET Framework Typen, die nicht im **System. Management. Automation** -Namespace sind.

Der Wert dieses Parameters muss dem Namen eines Typs entsprechen, der von einem `Get-FormatData` Befehl in der Sitzung zurückgegeben wird, aus der die Befehle importiert werden. Um alle Formatierungsdaten in der Remote Sitzung zu erhalten, geben Sie ein `*` .

Wenn Sie den **formattypame** -Parameter verwenden, werden keine Befehle exportiert, es sei denn, Sie verwenden den **CommandName** -Parameter.

Wenn Sie den **CommandName** -Parameter verwenden, werden die Formatierungs Dateien für die Befehle nicht exportiert, es sei denn, Sie verwenden den **formattypame** -Parameter.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fullyqualifiedmodule

Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind.
Weitere Informationen finden Sie im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](https://msdn.microsoft.com/library/jj136290).

Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der in einem der folgenden Formate angegeben ist:

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional. Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben. die beiden Parameter schließen sich gegenseitig aus.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Modul

Exportiert nur die Befehle in den angegebenen PowerShell-Snap-Ins und-Modulen. Geben Sie die Snap-In- und Modulnamen ein. Platzhalter sind nicht zulässig.

Weitere Informationen finden Sie unter `Import-Module` und [about_PSSnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### -Outputmodule

Gibt einen optionalen Pfad und Namen für das Modul an, das von erstellt wird `Export-PSSession` . Der Standardpfad lautet `$home\Documents\WindowsPowerShell\Modules`. Dieser Parameter ist erforderlich.

Wenn das Modul Unterverzeichnis oder eine der erstellten Dateien `Export-PSSession` bereits vorhanden ist, schlägt der Befehl fehl. Um vorhandene Dateien zu überschreiben, verwenden Sie den **Force** -Parameter.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, ModuleName

Required: True
Position: 1
Default value: $home\Documents\WindowsPowerShell\Modules
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sitzung

Gibt die PSSession an, aus der die Befehle ausgeführt werden. Geben Sie eine Variable ein, die ein Sitzungs Objekt oder einen Befehl zum Abrufen eines Sitzungs Objekts enthält, z. b. einen- `Get-PSSession` Befehl. Dieser Parameter ist erforderlich.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Objekte können nicht an übergeben werden `Export-PSSession` .

## AUSGABEN

### System. IO. fileingefo

`Export-PSSession` gibt eine Liste der Dateien zurück, die das Modul enthalten, das es erstellt hat.

## HINWEISE

`Export-PSSession` basiert auf der PowerShell-Remoting-Infrastruktur. Um dieses Cmdlet zu verwenden, muss der Computer für Remoting konfiguriert werden. Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

Sie können nicht verwenden `Export-PSSession` , um einen PowerShell-Anbieter zu exportieren.

Exportierte Befehle werden implizit in der PSSession ausgeführt, aus der sie exportiert wurden. Die Details der Remote Ausführung der Befehle werden vollständig von PowerShell verarbeitet. Sie können die exportierten Befehle genau so ausführen, wie Sie lokale Befehle ausführen würden.

`Export-ModuleMember` erfasst und speichert Informationen über die PSSession im Modul, das exportiert wird. Wenn die PSSession, von der die Befehle exportiert wurden, beim Importieren des Moduls geschlossen wird, und keine aktiven pssessions auf dem gleichen Computer vorhanden sind, versuchen die Befehle im Modul, die PSSession neu zu erstellen. Wenn Versuche, die PSSession neu zu erstellen, fehlschlagen, werden die exportierten Befehle nicht ausgeführt.

Die Sitzungsinformationen, die `Export-ModuleMember` im Modul erfasst und gespeichert werden, beinhalten keine Sitzungs Optionen, wie z. b. diejenigen, die Sie in der Einstellungs `$PSSessionOption` Variablen oder mithilfe des **sessionoption** -Parameters der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder angeben. Wenn die ursprüngliche PSSession geschlossen ist, wenn Sie das Modul importieren, verwendet das Modul eine andere PSSession auf dem gleichen Computer, falls verfügbar. Damit die importierten Befehle in einer korrekt konfigurierten Sitzung ausgeführt werden können, erstellen Sie eine PSSession mit den gewünschten Optionen, bevor Sie das Modul importieren.

Zum Suchen der zu exportierenden Befehle `Export-PSSession` verwendet das `Invoke-Command` Cmdlet, um einen `Get-Command` Befehl in der PSSession auszuführen. Um Formatierungsdaten für die Befehle zu erhalten und zu speichern, werden die `Get-FormatData` -und- `Export-FormatData` Cmdlets verwendet. Möglicherweise werden Fehlermeldungen von `Invoke-Command` , `Get-Command` , `Get-FormatData` und angezeigt, `Export-FormatData` Wenn Sie einen- `Export-PSSession` Befehl ausführen. Kann auch keine `Export-PSSession` Befehle aus einer Sitzung exportieren, die nicht die `Get-Command` `Get-FormatData` `Select-Object` Cmdlets,, und enthält `Get-Help` .

`Export-PSSession` verwendet das `Write-Progress` Cmdlet, um den Fortschritt des Befehls anzuzeigen. Während der Befehlsausführung wird u. U. die Statusanzeige angezeigt.

Exportierte Befehle unterliegen denselben Einschränkungen wie andere Remotebefehle, z. B. die Unfähigkeit, ein Programm mit einer Benutzeroberfläche, wie z. B. Editor, zu starten.

Da PowerShell-Profile nicht in pssessions ausgeführt werden, stehen die Befehle, die ein Profil einer Sitzung hinzufügt, nicht für zur Verfügung `Export-PSSession` . Um Befehle aus einem Profil zu exportieren, verwenden `Invoke-Command` Sie einen Befehl, um das Profil manuell in der PSSession auszuführen, bevor Sie Befehle exportieren.

Das Modul, das `Export-PSSession` erstellt, kann eine Formatierungs Datei enthalten, auch wenn der Befehl keine Formatierungsdaten importiert. Wenn durch den Befehl keine Formatierungsdaten importiert werden, enthält keine der erstellten Formatierungsdateien Formatierungsdaten.

## VERWANDTE LINKS

[about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)

[about_PSSessions](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[about_PSSnapins](/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1)

[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)

[Import-Module](../Microsoft.PowerShell.Core/Import-Module.md)

[Import-PSSession](Import-PSSession.md)

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[New-PSSession](../Microsoft.PowerShell.Core/New-PSSession.md)

[New-PSSessionOption](../Microsoft.PowerShell.Core/New-PSSessionOption.md)

[Remove-PSSession](../Microsoft.PowerShell.Core/Remove-PSSession.md)
