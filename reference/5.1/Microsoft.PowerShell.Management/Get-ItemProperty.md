---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: b2c5b8596da085fab3af7a1545569dd65931a5f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215420"
---
# Get-ItemProperty

## ZUSAMMENFASSUNG
Ruft die Eigenschaften eines angegebenen Elements ab.

## SYNTAX

### Pfad (Standard)

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-ItemProperty` Cmdlet ruft die Eigenschaften der angegebenen Elemente ab.
Beispielsweise können Sie mit diesem Cmdlet den Wert der LastAccessTime-Eigenschaft eines Datei Objekts erhalten.
Sie können dieses Cmdlet auch zum Anzeigen von Registrierungs Einträgen und deren Werten verwenden.

## BEISPIELE

### Beispiel 1: erhalten von Informationen zu einem bestimmten Verzeichnis

Mit diesem Befehl werden Informationen zum Verzeichnis "c:\Windows" abgerufen.

```powershell
Get-ItemProperty C:\Windows
```

### Beispiel 2: erhalten der Eigenschaften einer bestimmten Datei

Mit diesem Befehl werden die Eigenschaften der Datei "C:\Test\Weather.xls" abgerufen.
Das Ergebnis wird an das `Format-List` Cmdlet weitergeleitet, um die Ausgabe als Liste anzuzeigen.

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### Beispiel 3: Anzeigen des Werte namens und der Daten von Registrierungs Einträgen in einem Registrierungs Unterschlüssel

Dieser Befehl zeigt den Wertnamen und die Daten der einzelnen Registrierungseinträge im Registrierungs Unterschlüssel "CurrentVersion" an.
Beachten Sie, dass der Befehl erfordert, dass ein PowerShell-Laufwerk mit dem Namen vorhanden ist `HKLM:` , das der Hive-HKEY_LOCAL_MACHINE Struktur der Registrierung zugeordnet ist.
Ein Laufwerk mit diesem Namen und dieser Zuordnung ist standardmäßig in PowerShell verfügbar.
Der Pfad zu diesem Registrierungsunterschlüssel kann jedoch auch mit dem folgenden alternativen Pfad angegeben werden, der mit dem Anbieternamen beginnt, auf den zwei Doppelpunkte folgen:

"Registry:: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

### Beispiel 4: erhalten Sie den Wertnamen und die Daten eines Registrierungs Eintrags in einem Registrierungs Unterschlüssel.

Mit diesem Befehl werden der Wertname und die Daten des Registrierungs Eintrags "ProgramFilesDir" im Registrierungs Unterschlüssel "CurrentVersion" abgerufen.
Der Befehl verwendet den **path** -Parameter, um den Unterschlüssel anzugeben, und den Name-Parameter, um den Wertnamen des Eintrags anzugeben.

Der Befehl verwendet einen Backtick oder ein großes Akzent ( \` ), das PowerShell-Fortsetzungs Zeichen, um den Befehl in der zweiten Zeile fortzusetzen.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### Beispiel 5: erhalten der Werte Namen und Daten von Registrierungs Einträgen in einem Registrierungsschlüssel

Dieser Befehl ruft die Wertnamen und Daten der Registrierungseinträge im Registrierungsschlüssel "powershellengine" ab.
Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

### Beispiel 6: Get, Format und Anzeige der Ergebnisse von Registrierungs Werten und-Daten

Dieses Beispiel zeigt, wie die Ausgabe eines `Get-ItemProperty` Befehls in einer Liste formatiert werden kann, damit die Registrierungs Werte und-Daten leicht angezeigt werden und die Ergebnisse leicht interpretiert werden können.

Der erste Befehl verwendet das `Get-ItemProperty` Cmdlet, um die Registrierungseinträge im Unterschlüssel **Microsoft. PowerShell** zu erhalten.
Dieser Unterschlüssel speichert Optionen für die Standardshell für PowerShell.
Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.

Die Ausgabe zeigt, dass zwei Registrierungseinträge vorhanden sind: "Path" und "ExecutionPolicy".
Wenn ein Registrierungsschlüssel weniger als fünf Einträge enthält, wird er standardmäßig in einer Tabelle angezeigt. Die Darstellung in einer Liste ist jedoch häufig übersichtlicher.

Der zweite Befehl verwendet denselben `Get-ItemProperty` Befehl.
Diesmal verwendet der Befehl jedoch einen Pipeline Operator ( `|` ), um die Ergebnisse des Befehls an das `Format-List` Cmdlet zu senden.
Der `Format-List` Befehl verwendet den property-Parameter mit dem Wert "*" (alle), um alle Eigenschaften der Objekte in einer Liste anzuzeigen.
Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.

In der resultierenden Anzeige werden die Registrierungseinträge "Path" und "ExecutionPolicy" zusammen mit einigen weniger vertrauten Eigenschaften des Registrierungsschlüssel Objekts angezeigt.
Bei den anderen Eigenschaften mit dem Präfix PS handelt es sich um Eigenschaften von benutzerdefinierten PowerShell-Objekten, z. b. die Objekte, die die Registrierungsschlüssel darstellen.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell
```

```output
Path                                                        ExecutionPolicy
----                                                        ---------------
C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe   RemoteSigned
```

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell | Format-List -Property *
```

```output
PSPath          : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds\Micro
soft.PowerShell
PSParentPath    : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds
PSChildName     : Microsoft.PowerShell
PSDrive         : HKLM
PSProvider      : Microsoft.PowerShell.Core\Registry
Path            : C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe
ExecutionPolicy : RemoteSigned
```

## PARAMETERS

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.
Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.
Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

> [!WARNING]
> Dieser Parameter wird nicht von mit Windows PowerShell installierten Anbietern unterstützt.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ausschließen

Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.
Der Wert dieses Parameters qualifiziert den **Path** -Parameter.
Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;*.txt%%amp;quot; ein.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter

Gibt einen Filter im Format oder in der Sprache des Anbieters an.
Der Wert dieses Parameters qualifiziert den **Path** -Parameter.

Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.
Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.

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

Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.
Der Wert dieses Parameters qualifiziert den **Path** -Parameter.
Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;*.txt%%amp;quot; ein.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Literalpath

Gibt den Pfad zum aktuellen Speicherort der Eigenschaft an.
Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.
Es werden keine Zeichen als Platzhalter interpretiert.
Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.
Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt den Namen der abzurufenden Eigenschaft oder Eigenschaften an.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zu den Elementen an.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UseTransaction

Schließt den Befehl in die aktive Transaktion ein.
Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.
Weitere Informationen finden Sie unter schließt den Befehl in die aktive Transaktion ein.
Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.
Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Get-ItemProperty` .

## AUSGABEN

### System. Boolean, System. String, System. DateTime

`Get-ItemProperty` Gibt ein-Objekt für jede Element Eigenschaft zurück, die es abruft.
Der Objekttyp richtet sich nach dem abgerufenen Objekt.
Beispielsweise wird auf einem Dateisystemlaufwerk möglicherweise eine Datei oder ein Ordner zurückgegeben.

## HINWEISE

Das- `Get-ItemProperty` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie " `Get-PSProvider` " ein. Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.

## VERWANDTE LINKS

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)
