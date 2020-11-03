---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-error?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Error
ms.openlocfilehash: ad9e3daa7d67fc2bec6fa19a873573ce33dc609d
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224372"
---
# Write-Error

## ZUSAMMENFASSUNG
Schreibt ein Objekt in den Fehlerdatenstrom.

## SYNTAX

### Noexception (Standard)

```
Write-Error [-Message] <String> [-Category <ErrorCategory>] [-ErrorId <String>] [-TargetObject <Object>]
 [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### Withexception

```
Write-Error -Exception <Exception> [[-Message] <String>] [-Category <ErrorCategory>] [-ErrorId <String>]
 [-TargetObject <Object>] [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### ErrorRecord

```
Write-Error -ErrorRecord <ErrorRecord> [-RecommendedAction <String>] [-CategoryActivity <String>]
 [-CategoryReason <String>] [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem `Write-Error` -Cmdlet wird ein Fehler ohne Abbruch deklariert. Standardmäßig werden Fehler im Fehlerdatenstrom an das Hostprogramm gesendet und zusammen mit der Ausgabe angezeigt.

Um einen Fehler ohne Abbruch zu schreiben, geben Sie eine Fehlermeldungs-Zeichenfolge, ein **ErrorRecord** -Objekt oder ein **Exception** -Objekt ein. Verwenden Sie die anderen Parameter von `Write-Error` , um den Fehler Daten Satz aufzufüllen.

Fehler ohne Abbruch schreiben einen Fehler in den Fehlerdatenstrom, ohne die Befehlsverarbeitung zu beenden.
Wenn ein Fehler ohne Abbruch für ein einzelnes Element in einer Auflistung von Eingabeelementen deklariert wird, verarbeitet der Befehl weiterhin die anderen Elemente in der Auflistung.

Verwenden Sie das-Schlüsselwort, um einen Abbruch Fehler zu deklarieren `Throw` .
Weitere Informationen finden Sie unter [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).

## BEISPIELE

### Beispiel 1: Schreiben eines Fehlers für das RegistryKey-Objekt

```powershell
Get-ChildItem | ForEach-Object {
    if ($_.GetType().ToString() -eq "Microsoft.Win32.RegistryKey")
    {
        Write-Error "Invalid object" -ErrorId B1 -TargetObject $_
    }
    else
    {
        $_
    }
}
```

Mit diesem Befehl wird ein Fehler ohne Abbruch deklariert, wenn das `Get-ChildItem` Cmdlet ein-Objekt zurückgibt `Microsoft.Win32.RegistryKey` , wie z. b. die Objekte in den- `HKLM:` oder- `HKCU:` Laufwerken des PowerShell-Registrierungs Anbieters.

### Beispiel 2: Schreiben einer Fehlermeldung in die Konsole

```powershell
Write-Error "Access denied."
```

Mit diesem Befehl wird ein Fehler ohne Abbruch deklariert und ein Fehler des Typs „Zugriff verweigert“ geschrieben. Der Befehl verwendet den **Message** -Parameter zur Angabe der Meldung, lässt jedoch den optionalen **Message** -Parameternamen aus.

### Beispiel 3: Schreiben eines Fehlers in die Konsole und angeben der Kategorie

```powershell
Write-Error -Message "Error: Too many input values." -Category InvalidArgument
```

Mit diesem Befehl wird ein Fehler ohne Abbruch deklariert und eine Fehlerkategorie angegeben.

### Beispiel 4: Schreiben eines Fehlers mit einem Exception-Objekt

```powershell
$E = [System.Exception]@{Source="Get-ParameterNames.ps1";HelpLink="https://go.microsoft.com/fwlink/?LinkID=113425"}
Write-Error -Exception $E -Message "Files not found. The $Files location does not contain any XML files."
```

Dieser Befehl verwendet ein **Exception** -Objekt, um einen Fehler ohne Abbruch zu deklarieren.

Der erste Befehl verwendet eine Hashtabelle zum Erstellen des **System.Exception** -Objekts. Das Ausnahme Objekt wird in der `$E` Variablen gespeichert. Mithilfe einer Hashtabelle können Sie ein beliebiges Objekt eines Typs erstellen, der über einen NULL-Konstruktor verfügt.

Der zweite Befehl verwendet das `Write-Error` Cmdlet, um einen Fehler ohne Abbruch zu deklarieren. Der Wert des **Exception** -Parameters ist das **Exception** -Objekt in der `$E` Variablen.

## PARAMETERS

### -Kategorie

Gibt die Kategorie des Fehlers an. Der Standardwert ist " **notangegeben** ". Zulässige Werte für diesen Parameter:

- NotSpecified
- OpenError
- Closeerror
- Deviceerror
- Deadlockerkannt
- Invalidargument
- InvalidData
- InvalidOperation
- Invalidresult
- Invalidtype
- MetadataError
- NotImplemented
- Notinstalliert
- ObjectNotFound
- Operationbeendet
- OperationTimeout
- Syntax Error
- Parser Error
- Permissionverweigert
- Resourcebusy
- Resourcevorhanden
- Resourcenicht verfügbar
- ReadError
- WriteError
- Fromstderr
- SecurityError
- ProtocolError
- Connectionerror
- AuthenticationError
- Limits
- QuotaExceeded
- NotEnabled

Weitere Informationen zu den Fehlerkategorien finden Sie unter [ErrorCategory-Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).

```yaml
Type: System.Management.Automation.ErrorCategory
Parameter Sets: NoException, WithException
Aliases:
Accepted values: NotSpecified, OpenError, CloseError, DeviceError, DeadlockDetected, InvalidArgument, InvalidData, InvalidOperation, InvalidResult, InvalidType, MetadataError, NotImplemented, NotInstalled, ObjectNotFound, OperationStopped, OperationTimeout, SyntaxError, ParserError, PermissionDenied, ResourceBusy, ResourceExists, ResourceUnavailable, ReadError, WriteError, FromStdErr, SecurityError, ProtocolError, ConnectionError, AuthenticationError, LimitsExceeded, QuotaExceeded, NotEnabled

Required: False
Position: Named
Default value: NotSpecified
Accept pipeline input: False
Accept wildcard characters: False
```

### -Categoryactivity

Gibt die Aktion an, die den Fehler verursacht hat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Activity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Categoryreason

Gibt an, wie oder warum die Aktivität den Fehler verursacht hat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Reason

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Categorytargetname

Gibt den Namen des Objekts an, das beim Auftreten des Fehlers verarbeitet wurde.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Categorytargettype

Gibt den Typ des Objekts an, das beim Auftreten des Fehlers verarbeitet wurde.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorID

Gibt eine ID-Zeichenfolge zum Identifizieren des Fehlers an. Die Zeichenfolge muss für den Fehler eindeutig sein.

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorRecord

Gibt ein Fehlereintragsobjekt an, das den Fehler darstellt. Verwenden Sie die Eigenschaften des Objekts zur Beschreibung des Fehlers.

Zum Erstellen eines Fehler Daten Satz Objekts verwenden Sie das `New-Object` Cmdlet, oder rufen Sie ein Fehler Daten Satz Objekt aus dem Array in der `$Error` automatischen Variablen ab.

```yaml
Type: System.Management.Automation.ErrorRecord
Parameter Sets: ErrorRecord
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exception

Gibt ein Ausnahmeobjekt an, das den Fehler darstellt. Verwenden Sie die Eigenschaften des Objekts zur Beschreibung des Fehlers.

Verwenden Sie zum Erstellen eines Ausnahme Objekts eine Hash Tabelle, oder verwenden Sie das `New-Object` Cmdlet.

```yaml
Type: System.Exception
Parameter Sets: WithException
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Meldung

Gibt den Meldungstext des Fehlers an. Wenn der Text Leerzeichen oder Sonderzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen. Sie können eine Meldungs Zeichenfolge auch an übergeben `Write-Error` .

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases: Msg

Required: True (NoException), False (WithException)
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Empfehlungs dedaction

Gibt die Aktion an, die der Benutzer durchführen sollte, um den Fehler zu beheben oder zu verhindern.

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

### -TargetObject

Gibt das Objekt an, das beim Auftreten des Fehlers verarbeitet wurde. Geben Sie das-Objekt, eine Variable, die das Objekt enthält, oder einen Befehl ein, mit dem das-Objekt abgerufen wird.

```yaml
Type: System.Object
Parameter Sets: NoException, WithException
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

### System.String

Sie können eine Zeichenfolge, die eine Fehlermeldung enthält, über die Pipeline an senden `Write-Error` .

## AUSGABEN

### Error-Objekt

`Write-Error` schreibt nur in den Fehler Datenstrom. und gibt keine Objekte zurück.

## HINWEISE

`Write-Error` der Wert der `$?` automatischen Variablen wird nicht geändert, und es wird kein Abbruch Fehlerzustand signalisiert. Um einen Beendigungs Fehler zu signalisieren, verwenden Sie die [$PSCmdlet. Write-error ()](/dotnet/api/system.management.automation.cmdlet.writeerror) -Methode.

## VERWANDTE LINKS

[about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md)

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Write-Host](Write-Host.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
