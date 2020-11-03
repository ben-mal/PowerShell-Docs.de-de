---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: b6147b35a8818cf448b1e23f5458550d1c6e5c50
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "93219055"
---
# Start-Process

## ZUSAMMENFASSUNG
Startet Prozesse auf dem lokalen Computer.

## SYNTAX

### Standard (Standard)

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [<CommonParameters>]
```

### UseShellExecute

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Start-Process` Cmdlet wird mindestens ein Prozess auf dem lokalen Computer gestartet. Standardmäßig wird von `Start-Process` ein neuer Prozess erstellt, der alle Umgebungsvariablen erbt, die im aktuellen Prozess definiert sind.

Geben Sie zum Angeben des Programms, das im Prozess ausgeführt wird, eine ausführbare Datei, eine Skriptdatei oder eine Datei an, die mit einem Programm auf dem Computer geöffnet werden kann. Wenn Sie eine nicht ausführbare Datei angeben, `Start-Process` startet das Programm, das der Datei zugeordnet ist, vergleichbar mit dem- `Invoke-Item` Cmdlet.

Sie können die Parameter von verwenden, `Start-Process` um Optionen anzugeben, z. b. das Laden eines Benutzerprofils, das Starten des Prozesses in einem neuen Fenster oder das Verwenden alternativer Anmelde Informationen.

## BEISPIELE

### Beispiel 1: Starten eines Prozesses, der Standardwerte verwendet

In diesem Beispiel wird ein Prozess gestartet, der die `Sort.exe` Datei im aktuellen Ordner verwendet. Der Befehl verwendet alle Standardwerte, einschließlich Standardfenster Stil, Arbeitsordner und Anmelde Informationen.

```powershell
Start-Process -FilePath "sort.exe"
```

### Beispiel 2: Drucken einer Textdatei

In diesem Beispiel wird ein Prozess gestartet, der die `C:\PS-Test\MyFile.txt` Datei druckt.

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### Beispiel 3: Starten eines Prozesses zum Sortieren von Elementen in einer neuen Datei

In diesem Beispiel wird ein Prozess gestartet, mit dem Elemente in der Datei sortiert werden `Testsort.txt` und die sortierten Elemente in den Dateien zurückgegeben werden `Sorted.txt` . Alle Fehler werden in die `SortError.txt` Datei geschrieben.

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

Der **usenewenvironment** -Parameter gibt an, dass der Prozess mit seinen eigenen Umgebungsvariablen ausgeführt wird.

### Beispiel 4: Starten eines Prozesses in einem maximierten Fenster

In diesem Beispiel wird der `Notepad.exe` Prozess gestartet. Das Fenster wird maximiert und beibehalten, bis der Prozess abgeschlossen wurde.

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### Beispiel 5: Starten von PowerShell als Administrator

In diesem Beispiel wird PowerShell mit der Option **als Administrator ausführen** gestartet.

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### Beispiel 6: Verwenden verschiedener Verben zum Starten eines Prozesses

Dieses Beispiel zeigt, wie Sie die Verben suchen, die beim Starten eines Prozesses verwendet werden können. Die verfügbaren Verben werden durch die Dateinamenerweiterung der Datei bestimmt, die im Prozess ausgeführt wird.

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

Im Beispiel wird verwendet, `New-Object` um ein **System. Diagnostics. ProcessStartInfo** -Objekt für **PowerShell.exe** zu erstellen, die Datei, die im PowerShell-Prozess ausgeführt wird. Die **Verbs** -Eigenschaft des **ProcessStartInfo** -Objekts zeigt, dass Sie die " **Open** "-und " **runas** "-Verben mit `PowerShell.exe` oder mit einem beliebigen Prozess verwenden können, der eine `.exe` Datei ausführt.

### Beispiel 7: Angeben von Argumenten für den Prozess

Beide Befehle starten den Windows-Befehls Interpreter und geben einen `dir` Befehl für den `Program Files` Ordner aus. Da dieser FolderName ein Leerzeichen enthält, muss der Wert mit Escapezeichen versehen werden.
Beachten Sie, dass der erste Befehl eine Zeichenfolge als **argumentlist** angibt. Der zweite Befehl ist ein Zeichen folgen Array.

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

## PARAMETERS

### -Argumentlist

Gibt Parameter oder Parameterwerte an, die verwendet werden sollen, wenn dieses Cmdlet den Prozess startet. Argumente können als einzelne Zeichenfolge akzeptiert werden, wobei die Argumente durch Leerzeichen getrennt sind, oder als ein Array von Zeichen folgen, die durch Kommas getrennt sind.

Wenn Parameter oder Parameterwerte ein Leerzeichen enthalten, müssen Sie in doppelte Anführungszeichen eingeschlossen werden. Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Standardmäßig verwendet das Cmdlet die Anmeldeinformationen des aktuellen Benutzers.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Default
Aliases: RunAs

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Gibt den optionalen Pfad und den Dateinamen des Programms an, das im Prozess ausgeführt wird. Geben Sie den Namen einer ausführbaren Datei oder eines Dokuments ein, z. b. eine-oder-Datei, die `.txt` `.doc` einem Programm auf dem Computer zugeordnet ist. Dieser Parameter ist erforderlich.

Wenn Sie nur einen Dateinamen angeben, geben Sie den Pfad mithilfe des **WorkingDirectory** -Parameters an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadUserProfile

Gibt an, dass dieses Cmdlet das im `HKEY_USERS` Registrierungsschlüssel für den aktuellen Benutzer gespeicherte Windows-Benutzerprofil lädt.

Dieser Parameter hat keine Auswirkung auf die PowerShell-Profile. Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: Lup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nonewwindow

Startet den neuen Prozess im aktuellen Konsolenfenster. PowerShell öffnet standardmäßig ein neues Fenster.

Der **NoNewWindow** -Parameter und der **WindowStyle** -Parameter können nicht im selben Befehl verwendet werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: nnw

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt ein Prozessobjekt für jeden Prozess zurück, der vom Cmdlet gestartet wurde. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### -RedirectStandardError

Gibt eine Datei an. Dieses Cmdlet sendet alle Fehler, die vom Prozess generiert werden, in eine von Ihnen angegebene Datei.
Geben Sie den Pfad und den Dateinamen ein. Standardmäßig werden die Fehler in der Konsole angezeigt.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardInput

Gibt eine Datei an. Dieses Cmdlet liest Eingaben aus der angegebenen Datei. Geben Sie den Pfad und den Dateinamen der Eingabedatei ein. Standardmäßig ruft der Prozess die Eingabe von der Tastatur ab.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardOutput

Gibt eine Datei an. Dieses Cmdlet sendet die Ausgabe, die vom Prozess generiert wird, an eine von Ihnen angegebene Datei.
Geben Sie den Pfad und den Dateinamen ein. Standardmäßig wird die Ausgabe in der Konsole angezeigt.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usenewenvironment

Gibt an, dass dieses Cmdlet für den Prozess angegebene neue Umgebungsvariablen verwendet. Standardmäßig wird der gestartete Prozess mit den Umgebungsvariablen ausgeführt, die vom übergeordneten Prozess geerbt wurden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Verb

Gibt ein Verb an, das verwendet werden soll, wenn dieses Cmdlet den Prozess startet. Die verfügbaren Verben werden durch die Dateinamenerweiterung der Datei bestimmt, die im Prozess ausgeführt wird.

Die folgende Tabelle enthält die Verben für einige allgemeine Prozessdateitypen:

| Dateityp |                Verben                |
| --------- | ----------------------------------- |
| .cmd      | Bearbeiten, öffnen, drucken, runas, RunAsUser |
| .exe      | Öffnen, runas, RunAsUser              |
| .txt      | Öffnen, drucken, Printto                |
| WAV      | Öffnen, wiedergeben                          |

Verwenden Sie zum Suchen der Verben, die mit der in einem Prozess ausgeführten Datei verwendet werden können, das- `New-Object` Cmdlet, um ein **System. Diagnostics. ProcessStartInfo** -Objekt für die Datei zu erstellen. Die verfügbaren Verben sind in der **Verbs** -Eigenschaft des **ProcessStartInfo** -Objekts. Weitere Informationen finden Sie in den Beispielen.

```yaml
Type: System.String
Parameter Sets: UseShellExecute
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Gibt an, dass dieses Cmdlet auf den Abschluss des angegebenen Prozesses und seiner Nachfolger wartet, bevor mehr Eingaben akzeptiert werden. Dieser Parameter unterdrückt die Eingabeaufforderung oder behält das Fenster bei, bis die Prozesse abgeschlossen sind.

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

### -WindowStyle

Gibt den Status des für den neuen Prozess verwendeten Fensters an. Die zulässigen Werte für diesen Parameter sind " **Normal** ", " **ausgeblendet** ", " **minimiert** " und " **maximiert** ". Der Standardwert ist " **Normal** ".

Der **WindowStyle** -Parameter und der **NoNewWindow** -Parameter können nicht im selben Befehl verwendet werden.

```yaml
Type: System.Diagnostics.ProcessWindowStyle
Parameter Sets: (All)
Aliases:
Accepted values: Normal, Hidden, Minimized, Maximized

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkingDirectory

Gibt den Speicherort an, in dem der neue Prozess beginnen soll. Der Standardwert ist der Speicherort der ausführbaren Datei oder des Dokuments, das gestartet wird. Platzhalter werden nicht unterstützt. Der Pfadname darf keine Zeichen enthalten, die als Platzhalter interpretiert werden.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### None, System. Diagnostics. Process

Dieses Cmdlet generiert ein **System. Diagnostics. Process** -Objekt, wenn Sie den **passthru** -Parameter angeben. Andernfalls wird von diesem Cmdlet keine Ausgabe zurückgegeben.

## HINWEISE

- Dieses Cmdlet wird mithilfe der **Start** -Methode der **System. Diagnostics. Process** -Klasse implementiert. Weitere Informationen zu dieser Methode finden Sie unter [Process. Start-Methode](/dotnet/api/system.diagnostics.process.start#overloads).

- Wenn Sie unter Windows **usenewenvironment** verwenden, beginnt der neue Prozess nur mit den Standard Umgebungsvariablen, die für den **Computer** Bereich definiert wurden. Dies hat den Nebeneffekt, dass `$env:USERNAME` auf **System** festgelegt ist. Es sind keine Variablen aus dem **Benutzer** Bereich enthalten.

## VERWANDTE LINKS

[about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Service](Start-Service.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
