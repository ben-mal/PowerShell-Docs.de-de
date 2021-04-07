---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: 540be766d3fa66432207130f581262ec17e4c05c
ms.sourcegitcommit: d95a7255f6775b2973aa9473611185a5583881ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "106555779"
---
# Import-PSSession

## Übersicht
Importiert Befehle aus einer anderen Sitzung in die aktuelle Sitzung.

## Syntax

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## BESCHREIBUNG

Das- `Import-PSSession` Cmdlet importiert Befehle, z. b. Cmdlets, Funktionen und Aliase, von einer PSSession auf einem lokalen oder Remote Computer in die aktuelle Sitzung. Sie können jeden Befehl importieren, den das `Get-Command` Cmdlet in der PSSession finden kann.

Verwenden `Import-PSSession` Sie einen Befehl zum Importieren von Befehlen aus einer angepassten Shell (z. b. eine Microsoft Exchange Server-Shell) oder aus einer Sitzung, die Windows PowerShell-Module und-Snap-Ins oder andere Elemente enthält, die sich nicht in der aktuellen Sitzung befinden.

Zum Importieren von Befehlen verwenden Sie zunächst das `New-PSSession` Cmdlet, um eine PSSession zu erstellen. Verwenden Sie dann das `Import-PSSession` Cmdlet, um die Befehle zu importieren. Standardmäßig `Import-PSSession` importiert alle Befehle mit Ausnahme von Befehlen, die denselben Namen wie die Befehle in der aktuellen Sitzung haben. Zum Importieren aller Befehle verwenden Sie den **AllowClobber**-Parameter.

Sie können importierte Befehle genauso wie jeden anderen Befehl in der Sitzung ausführen. Wenn Sie einen importierten Befehl verwenden, wird der importierte Teil des Befehls implizit in der Sitzung ausgeführt, aus der er importiert wurde. Die Remotevorgänge werden jedoch vollständig von Windows PowerShell verarbeitet. Abgesehen davon, dass die Verbindung mit der anderen Sitzung (PSSession) geöffnet bleiben muss, können Remotevorgänge vollständig unbeaufsichtigt ablaufen. Wenn Sie die Verbindung trennen, sind die importierten Befehle nicht mehr verfügbar.

Da die Ausführung importierter Befehle länger dauern kann als lokale Befehle, `Import-PSSession` fügt jedem importierten Befehl einen **AsJob** -Parameter hinzu. Durch diesen Parameter können Sie den Befehl in Windows PowerShell als Hintergrundauftrag ausführen. Weitere Informationen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md).

Wenn Sie verwenden `Import-PSSession` , fügt Windows PowerShell die importierten Befehle einem temporären Modul hinzu, das nur in der Sitzung vorhanden ist, und gibt ein Objekt zurück, das das Modul darstellt. Verwenden Sie das-Cmdlet, um ein dauerhaftes Modul zu erstellen, das Sie in zukünftigen Sitzungen verwenden können `Export-PSSession` .

Das- `Import-PSSession` Cmdlet verwendet das implizite Remoting-Feature von Windows PowerShell. Wenn Sie Befehle in die aktuelle Sitzung importieren, werden Sie implizit in der ursprünglichen Sitzung oder in einer ähnlichen Sitzung auf dem ursprünglichen Computer ausgeführt.

Ab Windows PowerShell 3,0 können Sie das `Import-Module` Cmdlet verwenden, um Module aus einer Remote Sitzung in die aktuelle Sitzung zu importieren. Dieses Feature verwendet implizites Remoting. Dies entspricht `Import-PSSession` der Verwendung von, um ausgewählte Module aus einer Remote Sitzung in die aktuelle Sitzung zu importieren.

## Beispiele

### Beispiel 1: Importieren aller Befehle aus einer PSSession

```
$S = New-PSSession -ComputerName Server01
Import-PSSession -Session $S
```

Dieser Befehl importiert alle Befehle einer PSSession auf Computer Server01 in die aktuelle Sitzung. Dies gilt nicht für Befehle, die über dieselben Namen wie Befehle in der aktuellen Sitzung verfügen.

Da der **CommandName**-Parameter von diesem Befehl nicht verwendet wird, werden außerdem alle für die importierten Befehle erforderlichen Formatierungsdaten importiert.

### Beispiel 2: Importieren von Befehlen, die mit einer bestimmten Zeichenfolge enden

```
$S = New-PSSession https://ps.testlabs.com/powershell
Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
New-Test -Name Test1
Get-Test test1 | Run-Test
```

Durch diese Befehle werden die auf „-test“ endenden Namen aus einer PSSession in die lokale Sitzung importiert. Anschließend wird die Verwendung eines importierten Cmdlets gezeigt.

Der erste Befehl verwendet das `New-PSSession` Cmdlet, um eine PSSession zu erstellen. Er speichert die PSSession in der `$S` Variablen.

Der zweite Befehl verwendet das `Import-PSSession` Cmdlet, um Befehle aus der PSSession in in `$S` die aktuelle Sitzung zu importieren. Er verwendet den **CommandName**-Parameter, um Befehle mit dem Substantiv „Test“ anzugeben, und den **FormatTypeName**-Parameter, um die Formatierungsdaten für die Test-Befehle zu importieren.

Vom dritten und vierten Befehl werden die importierten Befehle in der aktuellen Sitzung verwendet. Importierte Befehle werden der aktuellen Sitzung tatsächlich hinzugefügt, sodass Sie sie mithilfe lokaler Syntax ausführen. Sie müssen das `Invoke-Command` Cmdlet nicht verwenden, um einen importierten Befehl auszuführen.

### Beispiel 3: Importieren von Cmdlets aus einer PSSession

```
$S1 = New-PSSession -ComputerName s1
$S2 = New-PSSession -ComputerName s2
Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
New-Test Test1 | Set-Test -RunType Full
```

Dieses Beispiel zeigt, dass Sie importierte Cmdlets genauso verwenden, wie Sie lokale Cmdlets verwenden würden.

Mit diesen Befehlen werden die `New-Test` -und- `Get-Test` Cmdlets aus einer PSSession auf dem Server01-Computer und das `Set-Test` Cmdlet aus einer PSSession auf dem Server02-Computer importiert.

Obwohl die Cmdlets aus verschiedenen PSSessions importiert wurden, können Sie ein Objekt aus einem Cmdlet fehlerfrei an ein anderes Cmdlet weiterreichen.

### Beispiel 4: Ausführen eines importierten Befehls als Hintergrund Auftrag

```
$S = New-PSSession -ComputerName Server01
Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
$batch = New-Test -Name Batch -AsJob
Receive-Job $batch
```

In diesem Beispiel wird erläutert, wie ein importierter Befehl als Hintergrundauftrag ausgeführt wird.

Da die Ausführung importierter Befehle länger dauern kann als lokale Befehle, `Import-PSSession` fügt jedem importierten Befehl einen **AsJob** -Parameter hinzu. Der **AsJob**-Parameter ermöglicht Ihnen die Ausführung des Befehls als Hintergrundauftrag.

Der erste Befehl erstellt eine PSSession auf dem Server01-Computer und speichert das PSSession-Objekt in der `$S` Variablen.

Der zweite Befehl verwendet `Import-PSSession` , um die Test-Cmdlets aus der PSSession in `$S` in die aktuelle Sitzung zu importieren.

Der dritte Befehl verwendet den **AsJob** -Parameter des importierten `New-Test` Cmdlets, um einen `New-Test` Befehl als Hintergrund Auftrag auszuführen. Der Befehl speichert das Auftrags Objekt, das `New-Test` in der Variablen zurückgegeben wird `$batch` .

Der vierte Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags in der Variablen zu erhalten `$batch` .

### Beispiel 5: Importieren von Cmdlets und Funktionen aus einem Windows PowerShell-Modul

```
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S {Import-Module TestManagement}
Import-PSSession -Session $S -Module TestManagement
```

In diesem Beispiel wird veranschaulicht, wie Cmdlets und Funktionen aus einem Windows PowerShell-Modul auf einem Remotecomputer in die aktuelle Sitzung importiert werden.

Der erste Befehl erstellt eine PSSession auf dem Server01-Computer und speichert Sie in der `$S` Variablen.

Der zweite Befehl verwendet das `Invoke-Command` Cmdlet, um einen `Import-Module` Befehl in der PSSession in auszuführen `$S` .

Normalerweise würde das Modul allen Sitzungen durch einen `Import-Module` Befehl in einem Windows PowerShell-Profil hinzugefügt werden, aber Profile werden nicht in pssessions ausgeführt.

Der dritte Befehl verwendet den **Module** -Parameter von `Import-PSSession` , um die Cmdlets und Funktionen im Modul in die aktuelle Sitzung zu importieren.

### Beispiel 6: Erstellen eines Moduls in einer temporären Datei

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1
zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1
zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

Dieses Beispiel zeigt, dass `Import-PSSession` ein Modul in einer temporären Datei auf dem Datenträger erstellt. Außerdem wird veranschaulicht, dass alle Befehle vor dem Import in die aktuelle Sitzung in Funktionen konvertiert werden.

Der Befehl verwendet das `Import-PSSession` Cmdlet, um ein `Get-Date` Cmdlet und eine SearchHelp-Funktion in die aktuelle Sitzung zu importieren.

Das- `Import-PSSession` Cmdlet gibt ein **psmoduleinfo** -Objekt zurück, das das temporäre Modul darstellt. Der Wert der **path** -Eigenschaft zeigt, dass `Import-PSSession` eine Skript Modul Datei (. psm1) an einem temporären Speicherort erstellt hat. Die **exportedfunctions** -Eigenschaft zeigt, dass das `Get-Date` Cmdlet und die SearchHelp-Funktion beide als Funktionen importiert wurden.

### Beispiel 7: Ausführen eines Befehls, der von einem importierten Befehl ausgeblendet wird

```
PS C:\> Import-PSSession $S -CommandName Get-Date -FormatTypeName * -AllowClobber

PS C:\> Get-Command Get-Date -All

CommandType   Name       Definition
-----------   ----       ----------
Function      Get-Date   ...
Cmdlet        Get-Date   Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>]

PS C:\> Get-Date
09074

PS C:\> (Get-Command -Type Cmdlet -Name Get-Date).PSSnapin.Name
Microsoft.PowerShell.Utility

PS C:\> Microsoft.PowerShell.Utility\Get-Date
Sunday, March 15, 2009 2:08:26 PM
```

In diesem Beispiel wird die Ausführung eines Befehls veranschaulicht, der von einem importierten Befehl ausgeblendet wird.

Der erste Befehl importiert ein `Get-Date` Cmdlet aus der PSSession in der `$S` Variablen. Da die aktuelle Sitzung ein `Get-Date` Cmdlet enthält, ist der **allowclobber** -Parameter im Befehl erforderlich.

Der zweite Befehl verwendet den **all** -Parameter des `Get-Command` Cmdlets, um alle `Get-Date` Befehle in der aktuellen Sitzung zu erhalten. Die Ausgabe zeigt, dass die Sitzung das ursprüngliche `Get-Date` Cmdlet und eine `Get-Date` Funktion enthält. Die- `Get-Date` Funktion führt das importierte `Get-Date` Cmdlet in der PSSession in aus `$S` .

Der dritte Befehl führt einen `Get-Date` Befehl aus. Da Funktionen Vorrang vor Cmdlets haben, führt Windows PowerShell die importierte `Get-Date` Funktion aus, die ein Julianischer Datum zurückgibt.

Der vierte und fünfte Befehl zeigen, wie ein Befehl, der von einem importierten Befehl ausgeblendet wird, anhand eines qualifizierten Namens ausgeführt wird.

Mit dem vierten Befehl wird der Name des Windows PowerShell-Snap-Ins abgerufen, das das ursprüngliche `Get-Date` Cmdlet zur aktuellen Sitzung hinzugefügt hat.

Der fünfte Befehl verwendet den mit dem Snap-in qualifizierten Namen des `Get-Date` Cmdlets, um einen `Get-Date` Befehl auszuführen.

Weitere Informationen zur Befehlsrangfolge und zu ausgeblendeten Befehlen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).

### Beispiel 8: Importieren von Befehlen, die eine bestimmte Zeichenfolge in ihren Namen haben

```
PS C:\> Import-PSSession -Session $S -CommandName **Item** -AllowClobber
```

Mit diesem Befehl werden Befehle importiert, deren Namen ein Element aus der PSSession in enthalten `$S` . Da der Befehl den **CommandName** -Parameter, aber nicht den **formattypedata** -Parameter enthält, wird nur der-Befehl importiert.

Verwenden Sie diesen Befehl, wenn Sie verwenden `Import-PSSession` , um einen Befehl auf einem Remote Computer auszuführen, und Sie bereits über die Formatierungsdaten für den Befehl in der aktuellen Sitzung verfügen.

### Beispiel 9: Verwenden Sie den Module-Parameter, um zu ermitteln, welche Befehle in die Sitzung importiert wurden.

```
PS C:\> $M = Import-PSSession -Session $S -CommandName *bits* -FormatTypeName *bits*
PS C:\> Get-Command -Module $M
CommandType     Name
-----------     ----
Function        Add-BitsFile
Function        Complete-BitsTransfer
Function        Get-BitsTransfer
Function        Remove-BitsTransfer
Function        Resume-BitsTransfer
Function        Set-BitsTransfer
Function        Start-BitsTransfer
Function        Suspend-BitsTransfer
```

Dieser Befehl zeigt, wie der **Modul** Parameter von verwendet `Get-Command` wird, um herauszufinden, welche Befehle von einem Befehl in die Sitzung importiert wurden `Import-PSSession` .

Der erste Befehl verwendet das `Import-PSSession` Cmdlet, um Befehle zu importieren, deren Namen "Bits" aus der PSSession in der `$S` Variablen enthalten. Der `Import-PSSession` Befehl gibt ein temporäres Modul zurück, und der Befehl speichert das Modul in der `$m` Variablen.

Der zweite Befehl verwendet das `Get-Command` Cmdlet, um die Befehle, die vom Modul in der Variablen exportiert werden, zu erhalten `$M` .

Der **Module**-Parameter akzeptiert einen Zeichenfolgenwert, der eigens für den Modulnamen erstellt wurde. Wenn Sie ein Modulobjekt senden, verwendet Windows PowerShell jedoch die **ToString**-Methode für das Modulobjekt, das den Modulnamen zurückgibt.

Der `Get-Command` Befehl ist das Äquivalent zu `Get-Command $M.Name` ".

## Parameter

### -Allowclobber

Gibt an, dass dieses Cmdlet die angegebenen Befehle importiert, auch wenn Sie dieselben Namen wie die Befehle in der aktuellen Sitzung haben.

Wenn Sie einen Befehl importieren, der denselben Namen wie der Befehl in der aktuellen Sitzung hat, werden die ursprünglichen Befehle durch den importierten Befehl ausgeblendet oder ersetzt. Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).

Standardmäßig `Import-PSSession` importiert keine Befehle, die denselben Namen wie die Befehle in der aktuellen Sitzung haben.

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

Gibt ein Array von Befehlen an, die sich aus der Verwendung der angegebenen Argumente (Parameterwerte) ergeben.

So importieren Sie beispielsweise die Variante des `Get-Item` Befehls im Zertifikat (CERT:) Geben Sie in die PSSession in ein `$S` , und geben Sie ein `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .

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

Gibt das Client Zertifikat an, das zum Signieren der Format Dateien (* .Format.ps1XML) oder Skript Moduldateien (. psm1) im temporären Modul verwendet wird, das von `Import-PSSession` erstellt wird.

Geben Sie eine Variable ein, die ein Zertifikat, einen Befehl oder einen Ausdruck enthält, durch die das Zertifikat abgerufen wird.

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

Gibt Befehle mit den angegebenen Namen oder namens Mustern an. Platzhalter sind zulässig. Verwenden Sie **CommandName** oder den Alias **Name**.

Standardmäßig `Import-PSSession` importiert alle Befehle aus der Sitzung, mit Ausnahme von Befehlen, die denselben Namen wie die Befehle in der aktuellen Sitzung haben. Dadurch wird verhindert, dass Befehle in der Sitzung durch importierte Befehle ausgeblendet oder ersetzt werden. Um alle Befehle zu importieren, also auch die Befehle, durch die andere Befehle ausgeblendet oder ersetzt werden, verwenden Sie den **AllowClobber**-Parameter.

Bei Verwendung des **CommandName**-Parameters werden die Formatierungsdateien für die Befehle nicht importiert, sofern nicht der **FormatTypeName**-Parameter verwendet wird. Entsprechend werden bei Verwendung des **FormatTypeName**-Parameters keine Befehle importiert, sofern Sie nicht den **CommandName**-Parameter verwenden.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandType

Gibt den Typ von Befehls Objekten an. Der Standardwert ist Cmdlet. Verwenden Sie **CommandType** oder dessen Aliasname **Type**. Zulässige Werte für diesen Parameter:

- `Alias`: Windows PowerShell-Aliase in der Remote Sitzung.
- `All`: Die Cmdlets und Funktionen in der Remote Sitzung.
- `Application`: Alle Dateien außer Windows-PowerShell Dateien in den Pfaden, die in der PATH-Umgebungsvariablen ( `$env:path` ) in der Remote Sitzung aufgelistet sind, einschließlich txt-, exe-und dll-Dateien.
- `Cmdlet`: Die Cmdlets in der Remote Sitzung. Der Standardwert ist Cmdlet.
- `ExternalScript`: Die PS1-Dateien in den Pfaden, die in der PATH-Umgebungsvariablen ( `$env:path` ) in der Remote Sitzung aufgelistet sind.
- `Filter` und `Function` : die Windows PowerShell-Funktionen in der Remote Sitzung.
- `Script`: Die Skriptblöcke in der Remote Sitzung.

Diese Werte werden als Flag-basierte Enumeration definiert. Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen. Die Werte können als Array von Werten an den **CommandType** -Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden. Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert. Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Disablenamecheck

Gibt an, dass dieses Cmdlet die Meldung unterdrückt, die Sie warnt, wenn Sie ein Cmdlet oder eine Funktion importieren, deren Name ein nicht genehmigtes Verb oder ein unzulässiges Zeichen enthält.

Wenn ein Modul, das Sie importieren, Cmdlets oder Funktionen exportiert, die nicht genehmigte Verben in ihren Namen haben, zeigt Windows PowerShell standardmäßig die folgende Warnmeldung an:

"Warnung: einige importierte Befehlsnamen enthalten nicht genehmigte Verben, die Sie möglicherweise weniger auffallen machen. Verwenden Sie den Verbose-Parameter, um weitere Details `Get-Verb` anzuzeigen, oder geben Sie ein, um die Liste der genehmigten Verben anzuzeigen.

Diese Meldung ist nur eine Warnung. Es wird trotzdem das gesamte Modul einschließlich nicht konformer Befehle importiert. Obwohl die Meldung für Modulbenutzer angezeigt wird, sollte das Namensproblem vom Modulautor behoben werden.

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

Gibt Formatierungs Anweisungen für die angegebenen Microsoft .NET Framework-Typen an.
Geben Sie die Typnamen ein.
Platzhalter sind zulässig.

Der Wert dieses Parameters muss dem Namen eines Typs entsprechen, der von einem `Get-FormatData` Befehl in der Sitzung zurückgegeben wird, aus der die Befehle importiert werden. Um alle Formatierungsdaten in der Remote Sitzung zu erhalten, geben Sie ein `*` .

Wenn der Befehl weder den **CommandName** -Parameter noch den **formattypame** -Parameter enthält, `Import-PSSession` importiert Formatierungs Anweisungen für alle .NET Framework Typen, die von einem `Get-FormatData` Befehl in der Remote Sitzung zurückgegeben werden.

Wenn Sie den **FormatTypeName**-Parameter verwenden, werden keine Befehle importiert, sofern nicht der **CommandName**-Parameter verwendet wird.

Entsprechend werden bei Verwendung des **CommandName**-Parameters die Formatierungsdateien für die Befehle nicht importiert, sofern Sie nicht den **FormatTypeName**-Parameter verwenden.

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

Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind (im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) im PowerShell-SDK beschrieben. Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der im folgenden Format angegeben ist:

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}` oder
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`.

**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.

Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben. Die beiden Parameter schließen sich gegenseitig aus.

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

Gibt und ein Array von Befehlen in den Windows PowerShell-Snap-Ins und-Modulen an. Geben Sie die Snap-In- und Modulnamen ein. Platzhalter sind nicht zulässig.

`Import-PSSession` Anbieter können nicht aus einem Snap-in importiert werden.

Weitere Informationen finden Sie unter [about_PSSnapins](/powershell/module/Microsoft.PowerShell.Core/About/about_PSSnapins) und [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Präfix

Gibt ein Präfix der Nomen in den Namen importierter Befehle an.

Verwenden Sie diesen Parameter, um Namenskonflikte zu vermeiden, die auftreten können, wenn verschiedene Befehle in der Sitzung denselben Namen haben.

Wenn Sie beispielsweise das Präfix Remote angeben und dann ein `Get-Date` Cmdlet importieren, ist das Cmdlet in der Sitzung als bekannt `Get-RemoteDate` und nicht mit dem ursprünglichen `Get-Date` Cmdlet verwechselt.

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

### -Sitzung

Gibt die **PSSession** an, aus der die Cmdlets importiert werden. Geben Sie eine Variable ein, die ein Sitzungs Objekt oder einen Befehl zum Abrufen eines Sitzungs Objekts enthält, z. b. einen- `New-PSSession` oder- `Get-PSSession` Befehl. Sie können jeweils nur eine Sitzung angeben. Dieser Parameter ist erforderlich.

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

## Eingaben

### Keine

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## Ausgaben

### System. Management. Automation. psmoduleinfo

`Import-PSSession` Gibt das gleiche Modul Objekt zurück, das `New-Module` und die `Get-Module` Cmdlets zurückgeben.
Das importierte Modul ist jedoch temporär und nur in der aktuellen Sitzung vorhanden. Verwenden Sie das-Cmdlet, um ein dauerhaftes Modul auf dem Datenträger zu erstellen `Export-PSSession` .

## Hinweise

- `Import-PSSession` basiert auf der PowerShell-Remoting-Infrastruktur. Zur Verwendung dieses Cmdlets muss der Computer für das WS-Management-Remoting konfiguriert sein. Weitere Informationen finden Sie unter [about_Remote](../Microsoft.PowerShell.Core/about/about_Remote.md) und [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).
- `Import-PSSession` keine Variablen oder PowerShell-Anbieter werden importiert.
- Beim Importieren von Befehlen, die denselben Namen wie die Befehle in der aktuellen Sitzung haben, können die importierten Befehle Aliase, Funktionen und Cmdlets in der Sitzung ausblenden sowie Funktionen und Variablen in der Sitzung ersetzen. Um Namenskonflikte zu vermeiden, verwenden Sie den **Prefix**-Parameter. Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).
- `Import-PSSession` konvertiert alle Befehle in Funktionen, bevor Sie importiert werden. Folglich zeigen importierte Befehle ein etwas anderes Verhalten, als wenn sie den ursprünglichen Befehlstyp behalten würden. Wenn Sie z. B. ein Cmdlet aus einer PSSession importieren und dann ein Cmdlet desselben Namens aus einem Modul oder Snap-In importieren, wird standardmäßig das aus der PSSession importierte Cmdlet ausgeführt, weil Funktionen Vorrang vor Cmdlets haben. Wenn Sie dagegen einen Alias in eine Sitzung importieren, die über einen Alias desselben Namens verfügt, wird immer der ursprüngliche Alias verwendet, weil Aliase Vorrang vor Funktionen haben. Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).
- `Import-PSSession` verwendet das `Write-Progress` Cmdlet, um den Fortschritt des Befehls anzuzeigen. Während der Befehlsausführung wird u. U. die Statusanzeige angezeigt.
- Zum Ermitteln der zu importierenden Befehle `Import-PSSession` verwendet das `Invoke-Command` Cmdlet, um einen `Get-Command` Befehl in der PSSession auszuführen. Um Formatierungsdaten für die Befehle zu erhalten, wird das- `Get-FormatData` Cmdlet verwendet. Wenn Sie einen Befehl ausführen, werden möglicherweise Fehlermeldungen von diesen Cmdlets angezeigt `Import-PSSession` . Kann auch keine `Import-PSSession` Befehle aus einer PSSession importieren, die nicht die `Get-Command` `Get-FormatData` `Select-Object` Cmdlets,, und enthält `Get-Help` .
- Importierte Befehle unterliegen den gleichen Beschränkungen wie andere Remotebefehle. Beispielweise können sie kein Programm mit einer Benutzeroberfläche, z. B. den Editor, starten.
- Da Windows PowerShell-Profile nicht in pssessions ausgeführt werden, stehen die Befehle, die ein Profil einer Sitzung hinzufügt, nicht für zur Verfügung `Import-PSSession` . Zum Importieren von Befehlen aus einem Profil verwenden Sie einen- `Invoke-Command` Befehl, um das Profil manuell in der PSSession auszuführen, bevor Sie Befehle importieren.
- Das temporäre Modul, das `Import-PSSession` erstellt, kann eine Formatierungs Datei enthalten, auch wenn der Befehl keine Formatierungsdaten importiert. Wenn durch den Befehl keine Formatierungsdaten importiert werden, enthält keine der erstellten Formatierungsdateien Formatierungsdaten.
- Um zu verwenden `Import-PSSession` , kann die Ausführungs Richtlinie in der aktuellen Sitzung nicht eingeschränkt oder AllSigned sein, da das temporäre Modul, das `Import-PSSession` erstellt, nicht signierte Skriptdateien enthält, die von diesen Richtlinien nicht unterbunden werden. Wenn Sie `Import-PSSession` ohne Änderung der Ausführungs Richtlinie für den lokalen Computer verwenden möchten, verwenden Sie den **Scope** -Parameter von, `Set-ExecutionPolicy` um eine weniger restriktive Ausführungs Richtlinie für einen einzelnen Prozess festzulegen.
- In Windows PowerShell 2.0 enthalten Hilfethemen zu Befehlen, die aus einer anderen Sitzung importiert werden, nicht das über den **Prefix**-Parameter zugewiesene Präfix. Um Hilfe zu einem importierten Befehl in Windows PowerShell 2.0 zu erhalten, verwenden Sie den ursprünglichen Befehlsnamen (ohne Präfix).

## Ähnliche Themen

[Export-PSSession](Export-PSSession.md)
