---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 69cebe735e413b226bd40539df075bf3a49bce95
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217164"
---
# Start-Job

## ZUSAMMENFASSUNG
Startet einen PowerShell-Hintergrund Auftrag.

## SYNTAX

### Computername (Standard)

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### DefinitionName

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [<CommonParameters>]
```

### Literalfilepathcomputername

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### Filepathcomputername

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Start-Job` Cmdlet wird ein PowerShell-Hintergrund Auftrag auf dem lokalen Computer gestartet.

Ein PowerShell-Hintergrund Auftrag führt einen Befehl aus, ohne mit der aktuellen Sitzung zu interagieren. Wenn Sie einen Hintergrund Auftrag starten, wird ein Auftrags Objekt sofort zurückgegeben, auch wenn der Auftrag längere Zeit in Anspruch nimmt. Sie können ohne Unterbrechung in der Sitzung weiterarbeiten, während der Auftrag abgeschlossen wird.

Das Auftrags Objekt enthält nützliche Informationen zum Auftrag, aber keine Auftrags Ergebnisse.
Wenn der Auftrag abgeschlossen ist, verwenden Sie das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten. Weitere Informationen zu Hintergrundaufträgen finden Sie unter [about_Jobs](./About/about_Jobs.md).

Um einen Hintergrund Auftrag auf einem Remote Computer auszuführen, verwenden Sie den **AsJob** -Parameter, der für viele Cmdlets verfügbar ist, oder verwenden `Invoke-Command` Sie das Cmdlet zum Ausführen eines `Start-Job` Befehls auf dem Remote Computer. Weitere Informationen finden Sie unter [about_Remote_Jobs](./About/about_Remote_Jobs.md).

Ab PowerShell 3,0 `Start-Job` können Instanzen von benutzerdefinierten Auftrags Typen, z. b. geplante Aufträge, gestartet werden. Informationen zum `Start-Job` Starten von Aufträgen mit benutzerdefinierten Typen finden Sie in den Hilfedokumenten für den Auftragstyp.

Ab PowerShell 6,0 können Sie Aufträge mithilfe des kaufmännischen und-( `&` )-Hintergrund Operators starten. Die Funktionalität des Background-Operators ist vergleichbar mit `Start-Job` . Beide Methoden zum Starten eines Auftrags erstellen ein **psremotingjob** -Auftrags Objekt. Weitere Informationen zur Verwendung von kaufmännisches und-( `&` ) finden Sie unter [about_Operators](./about/about_operators.md#background-operator-).

Das Standard Arbeitsverzeichnis für Aufträge ist hart codiert. Der Standardwert für Windows ist, `$HOME\Documents` und unter Linux oder macOS lautet der Standardwert `$HOME` . Der Skriptcode, der im Hintergrund Auftrag ausgeführt wird, muss das Arbeitsverzeichnis nach Bedarf verwalten.

> [!NOTE]
> Das Erstellen eines Out-of-Process-Hintergrund Auftrags mit `Start-Job` wird in dem Szenario, in dem PowerShell in anderen Anwendungen gehostet wird, z. b. in der PowerShell-Azure Functions, nicht unterstützt.
>
> Dies ist beabsichtigt, da von `Start-Job` der `pwsh` ausführbaren Datei abhängig ist, um `$PSHOME` einen Prozess für die Out-of-Process-Hintergrund Ausführung zu starten. Wenn eine Anwendung jedoch PowerShell verwendet, wird Sie direkt mit den PowerShell nuget SDK-Paketen verwendet, die nicht `pwsh` zusammen geliefert werden.
>
> Der Ersatz in diesem Szenario ist `Start-ThreadJob` das Modul **[threadjob](https://www.powershellgallery.com/packages/ThreadJob)**.

## BEISPIELE

### Beispiel 1: Starten eines Hintergrund Auftrags

In diesem Beispiel wird ein Hintergrund Auftrag gestartet, der auf dem lokalen Computer ausgeführt wird.

```powershell
Start-Job -ScriptBlock { Get-Process -Name pwsh }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name pwsh
```

`Start-Job` verwendet den **ScriptBlock** -Parameter, um `Get-Process` als Hintergrund Auftrag auszuführen. Der **Name** -Parameter gibt an, dass PowerShell-Prozesse gesucht werden `pwsh` . Die Auftrags Informationen werden angezeigt, und PowerShell kehrt zur Eingabeaufforderung zurück, während der Auftrag im Hintergrund ausgeführt wird.

Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` . Beispiel: `Receive-Job -Id 1`.

### Beispiel 2: Verwenden des Background-Operators zum Starten eines Hintergrund Auftrags

In diesem Beispiel wird der kaufmännische und- `&` Operator () verwendet, um einen Hintergrund Auftrag auf dem lokalen Computer zu starten. Der Auftrag erhält dasselbe Ergebnis wie `Start-Job` in Beispiel 1.

```powershell
Get-Process -Name pwsh &
```

```Output
Id    Name   PSJobTypeName   State       HasMoreData     Location      Command
--    ----   -------------   -----       -----------     --------      -------
5     Job5   BackgroundJob   Running     True            localhost     Microsoft.PowerShell.Man...
```

`Get-Process` verwendet den **Name** -Parameter zum Angeben von PowerShell-Prozessen `pwsh` . Das kaufmännische und-( `&` ) führt den Befehl als Hintergrund Auftrag aus. Die Auftrags Informationen werden angezeigt, und PowerShell kehrt zur Eingabeaufforderung zurück, während der Auftrag im Hintergrund ausgeführt wird.

Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` . Beispiel: `Receive-Job -Id 5`.

### Beispiel 3: Starten eines Auftrags mit Invoke-Command

In diesem Beispiel wird ein Auftrag auf mehreren Computern ausgeführt. Der Auftrag wird in einer Variablen gespeichert und mithilfe des Variablen namens in der PowerShell-Befehlszeile ausgeführt.

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

Ein Auftrag, der verwendet, `Invoke-Command` wird erstellt und in der- `$jobWRM` Variable gespeichert. `Invoke-Command` verwendet den **Computername** -Parameter, um die Computer anzugeben, auf denen der Auftrag ausgeführt wird. `Get-Content` Ruft die Servernamen aus der `C:\Servers.txt` Datei ab.

Der **ScriptBlock** -Parameter gibt einen Befehl an, mit `Get-Service` dem der **WinRM** -Dienst abgerufen wird. Der **Jobname** -Parameter gibt einen anzeigen Amen für den Auftrag an, **WinRM**. Der **throttlelimit** -Parameter schränkt die Anzahl der gleichzeitigen Befehle auf 16 ein. Der **AsJob** -Parameter startet einen Hintergrund Auftrag, der den Befehl auf den Servern ausführt.

### Beispiel 4: erhalten von Auftrags Informationen

In diesem Beispiel werden Informationen zu einem Auftrag abgerufen und die Ergebnisse eines abgeschlossenen Auftrags angezeigt, der auf dem lokalen Computer ausgeführt wurde.

```powershell
$j = Start-Job -ScriptBlock { Get-WinEvent -Log System } -Credential Domain01\User01
$j | Select-Object -Property *
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-WinEvent -Log System
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : 27ce3fd9-40ed-488a-99e5-679cd91b9dd3
Id            : 18
Name          : Job18
ChildJobs     : {Job19}
PSBeginTime   : 8/8/2019 14:41:57
PSEndTime     : 8/8/2019 14:42:07
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

`Start-Job` verwendet den **ScriptBlock** -Parameter, um einen Befehl auszuführen, der angibt, `Get-WinEvent` um das **System** Protokoll zu erhalten. Der **Credential** -Parameter gibt ein Domänen Benutzerkonto mit der Berechtigung zum Ausführen des Auftrags auf dem Computer an. Das Auftrags Objekt wird in der `$j` Variablen gespeichert.

Das-Objekt in der- `$j` Variable wird an die Pipeline gesendet `Select-Object` . Der **Property** -Parameter gibt ein Sternchen ( `*` ) an, um alle Eigenschaften des Auftrags Objekts anzuzeigen.

### Beispiel 5: Ausführen eines Skripts als Hintergrund Auftrag

In diesem Beispiel wird ein Skript auf dem lokalen Computer als Hintergrund Auftrag ausgeführt.

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

`Start-Job` verwendet den **FilePath** -Parameter, um eine Skriptdatei anzugeben, die auf dem lokalen Computer gespeichert ist.

### Beispiel 6: erhalten eines Prozesses mithilfe eines Hintergrund Auftrags

In diesem Beispiel wird ein Hintergrund Auftrag verwendet, um einen angegebenen Prozess nach dem Namen zu erhalten.

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

`Start-Job` verwendet den **Name** -Parameter, um einen anzeigen Amen, **pshelljob** , anzugeben. Der **ScriptBlock** -Parameter gibt `Get-Process` an, um Prozesse mit dem Namen **PowerShell** zu erhalten.

### Beispiel 7: erfassen und Speichern von Daten mithilfe eines Hintergrund Auftrags

In diesem Beispiel wird ein Auftrag gestartet, mit dem eine große Menge an Kartendaten erfasst und dann in einer Datei gespeichert wird `.tif` .

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif } -RunAs32
```

`Start-Job` verwendet den **Name** -Parameter, um den Namen des anzeigen Amens, **getmappingfiles** , anzugeben. Der **initializationscript** -Parameter führt einen Skriptblock aus, der das **mapfunctions** -Modul importiert. Der **ScriptBlock** -Parameter `Get-Map` wird ausgeführt und `Set-Content` speichert die Daten an dem Speicherort, der durch den **path** -Parameter angegeben wird. Der **RunAs32** -Parameter führt den Prozess als 32-Bit-Version aus, auch bei einem 64-Bit-Betriebssystem.

### Beispiel 8: übergeben von Eingaben an einen Hintergrund Auftrag

In diesem Beispiel wird die `$input` Automatische Variable verwendet, um ein Eingabe Objekt zu verarbeiten. Verwenden `Receive-Job` Sie, um die Ausgabe des Auftrags anzuzeigen.

```powershell
Start-Job -ScriptBlock { Get-Content $input } -InputObject "C:\Servers.txt"
Receive-Job -Name Job45 -Keep
```

```Output
Server01
Server02
Server03
Server04
```

`Start-Job` verwendet den **ScriptBlock** -Parameter, um `Get-Content` mit der `$input` automatischen Variablen auszuführen. Die `$input` Variable Ruft Objekte aus dem **Inputobject** -Parameter ab. `Receive-Job` verwendet den **Name** -Parameter, um den Auftrag anzugeben, und gibt die Ergebnisse aus. Der **Keep** -Parameter speichert die Auftrags Ausgabe, damit Sie während der PowerShell-Sitzung erneut angezeigt werden kann.

### Beispiel 9: Verwenden des Argument list-Parameters zum Angeben eines Arrays

In diesem Beispiel wird der Argument **List** -Parameter verwendet, um ein Array von Argumenten anzugeben. Das Array ist eine durch Trennzeichen getrennte Liste von Prozessnamen.

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

Das `Start-Job` Cmdlet verwendet den **ScriptBlock** -Parameter, um einen Befehl auszuführen. `Get-Process` verwendet den **Name** -Parameter, um die automatische Variable anzugeben `$args` . Der Argument **List** -Parameter übergibt das Array von Prozessnamen an `$args` . Die Prozessnamen PowerShell, pwsh und Editor sind Prozesse, die auf dem lokalen Computer ausgeführt werden.

Verwenden Sie das-Cmdlet, um die Ausgabe des Auftrags anzuzeigen `Receive-Job` . Beispiel: `Receive-Job -Id 1`.

## PARAMETERS

### -Argumentlist

Gibt ein Array von Argumenten oder Parameterwerten für das Skript an, das durch den **FilePath** -Parameter angegeben wird, oder einen Befehl, der mit dem **ScriptBlock** -Parameter angegeben wird.

Argumente müssen als Array Argument mit einem einzelnen Dimensions Argument an **argumentlist** übermittelt werden. Beispielsweise eine durch Trennzeichen getrennte Liste. Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentifizierung

Gibt den Mechanismus an, der verwendet wird, um Benutzer Anmelde Informationen zu authentifizieren.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- Standard
- Basic
- CredSSP
- Digest
- Kerberos
- Aushandeln
- NegotiateWithImplicitCredential

Der Standardwert ist Default.

Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Die CredSSP (Credential Security Support Provider)-Authentifizierung, bei der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle konzipiert, die die Authentifizierung auf mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remotenetzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Wenn der **Credential** -Parameter nicht angegeben ist, verwendet der Befehl die Anmelde Informationen des aktuellen Benutzers.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefinitionName

Gibt den Definitions Namen des Auftrags an, der von diesem Cmdlet gestartet wird. Verwenden Sie diesen Parameter, um benutzerdefinierte Auftragstypen zu starten, die über einen Definitionsnamen verfügen, z. B. geplante Aufträge.

Wenn Sie verwenden, `Start-Job` um eine Instanz eines geplanten Auftrags zu starten, wird der Auftrag unabhängig von Auftrags Triggern oder Auftrags Optionen sofort gestartet. Die resultierende Auftrags Instanz ist ein geplanter Auftrag, wird jedoch nicht wie ausgelöste geplante Aufträge auf einem Datenträger gespeichert. Sie können den Argument **List** -Parameter von nicht verwenden `Start-Job` , um Werte für Parameter von Skripts bereitzustellen, die in einem geplanten Auftrag ausgeführt werden.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefinitionPath

Gibt den Pfad der Definition für den Auftrag an, der von diesem Cmdlet gestartet wird. Geben Sie den Definitionspfad ein. Die Verkettung der Werte des **DefinitionPath** -Parameters und des **DefinitionName** -Parameters ist der voll qualifizierte Pfad der Auftrags Definition. Verwenden Sie diesen Parameter, um benutzerdefinierte Auftragstypen zu starten, die über einen Definitionspfad verfügen, z. B. geplante Aufträge.

Bei geplanten Aufträgen lautet der Wert des **DefinitionPath** -Parameters `$home\AppData\Local\Windows\PowerShell\ScheduledJob` .

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Gibt ein lokales Skript an, das `Start-Job` als Hintergrund Auftrag ausgeführt wird. Geben Sie den Pfad und den Dateinamen des Skripts ein, oder verwenden Sie die Pipeline, um einen Skript Pfad an zu senden `Start-Job` . Das Skript muss sich auf dem lokalen Computer oder in einem Ordner befinden, auf den der lokale Computer zugreifen kann.

Wenn Sie diesen Parameter verwenden, konvertiert PowerShell den Inhalt der angegebenen Skriptdatei in einen Skriptblock und führt den Skriptblock als Hintergrund Auftrag aus.

```yaml
Type: System.String
Parameter Sets: FilePathComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Initializationscript

Gibt Befehle an, die vor dem Starten des Auftrags ausgeführt werden. Um einen Skriptblock zu erstellen, schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein.

Verwenden Sie diesen Parameter zum Vorbereiten der Sitzung, in der der Auftrag ausgeführt wird. Sie können damit beispielsweise Funktionen, Snap-Ins und Module zur Sitzung hinzufügen.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die Eingabe für den Befehl an. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der die Objekte generiert.

Verwenden Sie im Wert des **ScriptBlock** -Parameters die `$input` Automatische Variable, um die Eingabe Objekte darzustellen.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Literalpath

Gibt ein lokales Skript an, das dieses Cmdlet als Hintergrund Auftrag ausführt. Geben Sie den Pfad eines Skripts auf dem lokalen Computer ein.

`Start-Job` verwendet den Wert des **literalpath** -Parameters genau so, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String
Parameter Sets: LiteralFilePathComputerName
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt einen Anzeigenamen für den neuen Auftrag an. Sie können den Namen verwenden, um den Auftrag für andere Auftrags-Cmdlets wie z `Stop-Job` . b. das Cmdlet zu identifizieren.

Der standardmäßige Anzeige Name ist `Job#` , wobei `#` eine Ordinalzahl ist, die für jeden Auftrag inkrementiert wird.

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Psversion

Gibt eine Version an. `Start-Job` führt den Auftrag mit der PowerShell-Version aus. Die zulässigen Werte für diesen Parameter sind: `2.0` und `3.0` .

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Version
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAs32

Gibt an, dass `Start-Job` den Auftrag in einem 32-Bit-Prozess ausführt. **RunAs32** erzwingt, dass der Auftrag in einem 32-Bit-Prozess ausgeführt wird, selbst bei einem 64-Bit-Betriebssystem.

Wenn in 64-Bit-Versionen von Windows 7 und Windows Server 2008 R2 der `Start-Job` Befehl den **RunAs32** -Parameter enthält, können Sie den **Credential** -Parameter nicht verwenden, um die Anmelde Informationen eines anderen Benutzers anzugeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Gibt die im Hintergrundauftrag auszuführenden Befehle an. Um einen Skriptblock zu erstellen, schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein. Verwenden `$input` Sie die automatische Variable, um auf den Wert des **Inputobject** -Parameters zuzugreifen. Dieser Parameter ist erforderlich.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

Gibt den benutzerdefinierten Typ für Aufträge an, die von gestartet werden `Start-Job` . Geben Sie einen benutzerdefinierten Auftragstypnamen ein, wie z. B. „PSScheduledJob“ für geplante Aufträge oder „SWorkflowJob“für Workflowaufträge. Dieser Parameter ist für Standard-Hintergrund Aufträge nicht gültig.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können die Pipeline verwenden, um ein Objekt mit der **Name** -Eigenschaft an den **Name** -Parameter zu senden. Sie können z. b. ein **FileInfo** -Objekt von an Pipeline Pipeline `Get-ChildItem` `Start-Job` .

## AUSGABEN

### System. Management. Automation. psremotingjob

`Start-Job` Gibt ein **psremotingjob** -Objekt zurück, das den gestarteten Auftrag darstellt.

## HINWEISE

Zur Ausführung im Hintergrund wird in `Start-Job` der aktuellen Sitzung in einer eigenen Sitzung ausgeführt. Wenn Sie mit dem `Invoke-Command` Cmdlet einen `Start-Job` Befehl in einer Sitzung auf einem Remote Computer ausführen, wird in `Start-Job` einer Sitzung in der Remote Sitzung ausgeführt.

## VERWANDTE LINKS

[about_Arrays](./about/about_arrays.md)

[about_Automatic_Variables](./about/about_automatic_variables.md)

[about_Jobs](./About/about_Jobs.md)

[about_Job_Details](./About/about_Job_Details.md)

[about_Remote_Jobs](./About/about_Remote_Jobs.md)

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Stop-Job](Stop-Job.md)

[Wait-Job](Wait-Job.md)
