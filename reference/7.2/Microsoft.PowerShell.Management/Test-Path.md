---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: a79f12739643a873703b39d9d07e8b7db01dfbb4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601313"
---
# Test-Path

## ZUSAMMENFASSUNG
Bestimmt, ob alle Elemente eines Pfads vorhanden sind.

## SYNTAX

### Pfad (Standard)

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### LiteralPath

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Test-Path` Cmdlet bestimmt, ob alle Elemente des Pfads vorhanden sind. Er gibt zurück, `$True` Wenn alle Elemente vorhanden sind und ggf `$False` . fehlende vorhanden sind. Es kann auch festzustellen, ob die Pfad Syntax gültig ist und ob der Pfad zu einem Container oder einem Terminal oder einem Blatt Element führt. Wenn ein Leerraum `Path` eine leere Zeichenfolge ist, `$False` wird zurückgegeben. Wenn `Path` `$null` , `$null` ein Array oder ein leeres Array ist, wird ein Fehler ohne Abbruch zurückgegeben.

## BEISPIELE

### Beispiel 1: Testen eines Pfads

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

Mit diesem Befehl wird überprüft, ob alle Elemente im Pfad vorhanden sind, d. h. das Verzeichnis "C:", das Verzeichnis "Dokumente und Einstellungen" und das Verzeichnis "DavidC". Wenn eine solche fehlt, gibt das Cmdlet zurück `$False` .
Andernfalls wird `$True`zurückgegeben.

### Beispiel 2: Testen des Pfads eines Profils

```powershell
Test-Path -Path $profile
```

```Output
False
```

```powershell
Test-Path -Path $profile -IsValid
```

```Output
True
```

Mit diesen Befehlen wird der Pfad des PowerShell-Profils getestet.

Mit dem ersten Befehl wird bestimmt, ob alle Elemente im Pfad vorhanden sind. Mit dem zweiten Befehl wird bestimmt, ob die Syntax des Pfads gültig ist. In diesem Fall ist der Pfad `$False` , aber die Syntax ist richtig `$True` . Diese Befehle verwenden `$profile` , die automatische Variable, die auf den Speicherort für das Profil zeigt, selbst wenn das Profil nicht vorhanden ist.

Weitere Informationen zu automatischen Variablen finden Sie unter %%amp;quot;about_Automatic_Variables%%amp;quot;.

### Beispiel 3: überprüfen, ob neben einem angegebenen Typ Dateien vorhanden sind

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

Mit diesem Befehl wird überprüft, ob im Verzeichnis der kommerziellen Gebäude andere Dateien als DWG-Dateien vorhanden sind.

Der Befehl verwendet den **path** -Parameter, um den Pfad anzugeben. Da der Pfad ein Leerzeichen enthält, wird der Pfad in Anführungszeichen eingeschlossen. Das Sternchen am Ende des Pfads gibt den Inhalt des Verzeichnisses %%amp;quot;Commercial Building%%amp;quot; an. Bei langen Pfaden, wie z. b. diesem, geben Sie die ersten Buchstaben des Pfads ein, und verwenden Sie dann die Tab-Taste, um den Pfad abzuschließen.

Der Befehl gibt den **Exclude** -Parameter zum Angeben von Dateien an, die in der Auswertung ausgelassen werden.

Da das Verzeichnis in diesem Fall nur DWG-Dateien enthält, lautet das Ergebnis `$False` .

### Beispiel 4: Überprüfen auf eine Datei

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

Mit diesem Befehl wird überprüft, ob der in der Variablen gespeicherte Pfad `$profile` zu einer Datei führt. In diesem Fall `.ps1` gibt das Cmdlet zurück, da es sich bei dem PowerShell-Profil um eine Datei handelt `$True` .

### Beispiel 5: Überprüfen der Pfade in der Registrierung

Diese Befehle werden `Test-Path` mit dem PowerShell-Registrierungs Anbieter verwendet.

Der erste Befehl testet, ob der Registrierungs Pfad des **Microsoft. PowerShell** -Registrierungsschlüssels auf dem System richtig ist. Wenn PowerShell ordnungsgemäß installiert ist, wird vom Cmdlet zurückgegeben `$True` .

> [!IMPORTANT]
> `Test-Path` funktioniert nicht mit allen PowerShell-Anbietern ordnungsgemäß. Beispielsweise können Sie verwenden, `Test-Path` um den Pfad eines Registrierungsschlüssels zu testen, aber wenn Sie ihn zum Testen des Pfads eines Registrierungs Eintrags verwenden, wird immer zurückgegeben, `$False` auch wenn der Registrierungs Eintrag vorhanden ist.

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell"
```

```Output
True
```

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell\ExecutionPolicy"
```

```Output
False
```

### Beispiel 6: testen, ob eine Datei neuer als ein bestimmtes Datum ist

Dieser Befehl verwendet den dynamischen Parameter " **newerthan** ", um zu bestimmen, ob die Datei "PowerShell.exe" auf dem Computer neuer als "Juli 13, 2009" ist.

Der Parameter NewerThan funktioniert nur in Dateisystemlaufwerken.

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### Beispiel 7: Testen eines Pfads mit NULL als Wert

Der für `null` `null` ein Array oder ein leeres Array zurückgegebene Fehler ist ein Fehler ohne Abbruch. Dies kann mithilfe von unterdrückt werden `-ErrorAction SilentlyContinue` . Im folgenden Beispiel werden alle Fälle gezeigt, die den Fehler zurückgeben `NullPathNotPermitted` .

```powershell
Test-Path $null
Test-Path $null, $null
Test-Path @()
```

```Output
Test-Path : Cannot bind argument to parameter 'Path' because it is null.
At line:1 char:11
+ Test-Path $null
+           ~~~~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorNullNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

### Beispiel 8: Testen eines Pfads mit Leerraum als Wert

Wenn ein Leerzeichen oder eine leere Zeichenfolge für den Parameter bereitgestellt wird `-Path` , wird **false** zurückgegeben.
Das folgende Beispiel zeigt Leerräume und eine leere Zeichenfolge.

```powershell
Test-Path ' '
Test-Path ''
```

```Output
False
False
```

## PARAMETERS

### -Credential

> [!NOTE]
> Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt. Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ausschließen

Gibt die Elemente an, die von diesem Cmdlet ausgelassen werden. Der Wert dieses Parameters qualifiziert den **Path**-Parameter. Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;*.txt%%amp;quot; ein. Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Filter

Gibt einen Filter im Format oder in der Sprache des Anbieters an. Der Wert dieses Parameters qualifiziert den **Path**-Parameter. Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab. Filter sind effizienter als andere Parameter, da Sie vom Anbieter beim Abrufen der Objekte angewendet werden, anstatt dass PowerShell die Objekte nach dem Abrufen filtert.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Include

Gibt die Pfade an, die von diesem Cmdlet getestet werden. Der Wert dieses Parameters qualifiziert den **Path**-Parameter. Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;*.txt%%amp;quot; ein. Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -IsValid

Gibt an, dass dieses Cmdlet die Syntax des Pfads testet, unabhängig davon, ob die Elemente des Pfads vorhanden sind. Dieses Cmdlet gibt zurück, `$True` Wenn die Pfad Syntax gültig ist, `$False` andernfalls.

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

### -Literalpath

Gibt den zu testenden Pfad an. Im Gegensatz zu **Path** wird der Wert des **LiteralPath**-Parameters genauso verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Zeichen enthält, die von PowerShell als Escapesequenzen interpretiert werden können, müssen Sie den Pfad in einfache Anführungszeichen einschließen, damit diese nicht interpretiert werden.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -"-Nals"

Geben Sie eine Uhrzeit als **DateTime** -Objekt an.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Olderthan

Geben Sie eine Uhrzeit als **DateTime** -Objekt an.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt den zu testenden Pfad an. Platzhalterzeichen sind zulässig. Wenn der Pfad Leerzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -PathType

Gibt den Typ des letzten Elements im Pfad an. Dieses Cmdlet gibt zurück, `$True` Wenn das Element den angegebenen Typ hat und `$False` andernfalls. Zulässige Werte für diesen Parameter:

- Container.
  Ein Element, das andere Elemente enthält, beispielsweise ein Verzeichnis oder einen Registrierungsschlüssel.
- Dach.
  Ein Element, das keine anderen Elemente enthält, beispielsweise eine Datei.
- Irgendeiner.
  Ein Container- oder Leaf-Element.

Gibt an, ob das letzte Element im Pfad einen bestimmten Typ aufweist.

> [!CAUTION]
>
> Bis zur PowerShell-Version 6.1.2, wenn die Schalter **IsValid** und **PathType** zusammen angegeben werden, `Test-Path` ignoriert das Cmdlet den **PathType** -Switch und überprüft nur den syntaktischen Pfad, ohne den Pfadtyp zu überprüfen.
>
> Gemäß der [Problem #8607](https://github.com/PowerShell/PowerShell/issues/8607)kann das Beheben dieses Verhaltens eine Breaking Change in einer zukünftigen Version sein, bei der die " **IsValid** "-und " **PathType** "-Schalter zu separaten Parametersätzen gehören und somit nicht gleichzeitig verwendet werden können, um diese Verwirrung zu vermeiden.

```yaml
Type: Microsoft.PowerShell.Commands.TestPathType
Parameter Sets: (All)
Aliases: Type
Accepted values: Any, Container, Leaf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.

## AUSGABEN

### System.Boolean

Mit dem-Cmdlet wird ein **boolescher** Wert zurückgegeben.

## HINWEISE

Die Cmdlets, die das **Pfad** -Substantiv enthalten (die **path** -Cmdlets), funktionieren mit Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann. Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll.
Verwenden Sie Sie wie **dirname**, **normpath**, **realpath**, **Join** oder andere Pfad Manipulatoren.

Der `Test-Path` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Split-Path](Split-Path.md)
