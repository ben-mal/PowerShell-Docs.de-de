---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-Item
ms.openlocfilehash: 0aeebac75c5a84fd78056954d7178de1dbac1460
ms.sourcegitcommit: 33ac34789e86ffb4e7e69453ae38fc0bd24933dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "93219751"
---
# Copy-Item

## ZUSAMMENFASSUNG
Kopiert ein Element von einem Speicherort an einen anderen Speicherort.

## SYNTAX

### Pfad (Standard)

```
Copy-Item [-Path] <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

### LiteralPath

```
Copy-Item -LiteralPath <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

## DESCRIPTION

Das `Copy-Item` Cmdlet kopiert ein Element von einem Speicherort an einen anderen Speicherort im selben Namespace.
Beispielsweise kann eine Datei in einen Ordner kopiert werden, aber Sie kann keine Datei auf ein Zertifikat Laufwerk kopieren.

Mit diesem Cmdlet werden die kopierten Elemente nicht ausgeschnitten oder gelöscht. Die Elemente, die vom Cmdlet kopiert werden können, hängen vom PowerShell-Anbieter ab, der das Element verfügbar macht. Beispielsweise können Dateien und Verzeichnisse auf einem Dateisystem Laufwerk sowie Registrierungsschlüssel und-Einträge auf dem Registrierungs Laufwerk kopiert werden.

Mit diesem Cmdlet können Elemente im selben Befehl kopiert und umbenannt werden. Um ein Element umzubenennen, geben Sie den neuen Namen in den Wert des **Destination** -Parameters ein. Verwenden Sie das-Cmdlet, um ein Element umzubenennen und es nicht zu kopieren `Rename-Item` .

## BEISPIELE

### Beispiel 1: Kopieren einer Datei in das angegebene Verzeichnis

In diesem Beispiel wird die `mar1604.log.txt` Datei in das `C:\Presentation` Verzeichnis kopiert. Die ursprüngliche Datei wird nicht gelöscht.

```powershell
Copy-Item "C:\Wabash\Logfiles\mar1604.log.txt" -Destination "C:\Presentation"
```

### Beispiel 2: Kopieren von Verzeichnis Inhalten in ein vorhandenes Verzeichnis

In diesem Beispiel wird der Inhalt des `C:\Logfiles` Verzeichnisses in das vorhandene `C:\Drawings` Verzeichnis kopiert. Das `Logfiles` Verzeichnis wird nicht kopiert.

Wenn das `Logfiles` Verzeichnis Dateien in Unterverzeichnissen enthält, werden diese Unterverzeichnisse mit ihren Dateistrukturen intakt kopiert. Standardmäßig ist der **Container** -Parameter auf **true** festgelegt, wodurch die Verzeichnisstruktur beibehalten wird.

```powershell
Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings" -Recurse
```

> [!NOTE]
> Wenn Sie das `Logfiles` Verzeichnis in die Kopie einschließen müssen, entfernen Sie das `\*` aus dem **Pfad**.
> Beispiel:
>
> `Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings" -Recurse`

### Beispiel 3: Kopieren von Verzeichnis und Inhalt in ein neues Verzeichnis

In diesem Beispiel werden die Inhalte des `C:\Logfiles` Quell Verzeichnisses kopiert und ein neues Zielverzeichnis erstellt. Das neue Zielverzeichnis `\Logs` wird in erstellt `C:\Drawings` .

Wenn Sie den Namen des Quell Verzeichnisses einschließen möchten, kopieren Sie ihn in ein vorhandenes Zielverzeichnis, wie in **Beispiel 2** gezeigt. Oder benennen Sie das neue Zielverzeichnis mit dem Quellverzeichnis.

```powershell
Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings\Logs" -Recurse
```

> [!NOTE]
> Wenn der **Pfad** enthält `\*` , werden alle Dateiinhalte des Verzeichnisses, einschließlich der Unterverzeichnis Strukturen, in das neue Zielverzeichnis kopiert. Beispiel:
>
> `Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings\Logs" -Recurse`

### Beispiel 4: Kopieren einer Datei in das angegebene Verzeichnis und Umbenennen der Datei

In diesem Beispiel wird das- `Copy-Item` Cmdlet verwendet, um das `Get-Widget.ps1` Skript aus dem `\\Server01\Share` Verzeichnis in das Verzeichnis zu kopieren `\\Server12\ScriptArchive` . Im Rahmen des Kopiervorgangs ändert der-Befehl den Elementnamen von `Get-Widget.ps1` in `Get-Widget.ps1.txt` , sodass er an e-Mail-Nachrichten angefügt werden kann.

```powershell
Copy-Item "\\Server01\Share\Get-Widget.ps1" -Destination "\\Server12\ScriptArchive\Get-Widget.ps1.txt"
```

### Beispiel 5: Kopieren einer Datei auf einen Remote Computer

Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .

Das `Copy-Item` Cmdlet kopiert `test.log` `D:\Folder001` `C:\Folder001_Copy` mithilfe der in der Variablen gespeicherten Sitzungsinformationen aus dem Ordner in den Ordner auf dem Remote Computer `$Session` . Die ursprüngliche Datei wird nicht gelöscht.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "D:\Folder001\test.log" -Destination "C:\Folder001_Copy\" -ToSession $Session
```

### Beispiel 6: Kopieren eines Ordners auf einen Remote Computer

Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .

Das- `Copy-Item` Cmdlet kopiert den `D:\Folder002` Ordner `C:\Folder002_Copy` mithilfe der in der-Variablen gespeicherten Sitzungsinformationen in das Verzeichnis auf dem Remote Computer `$Session` . Alle Unterordner oder Dateien werden ohne Verwendung des **recurse** -Schalters nicht kopiert.
Der-Vorgang erstellt den `Folder002_Copy` Ordner, wenn er nicht bereits vorhanden ist.

```powershell
$Session = New-PSSession -ComputerName "Server02" -Credential "Contoso\User01"
Copy-Item "D:\Folder002\" -Destination "C:\Folder002_Copy\" -ToSession $Session
```

### Beispiel 7: rekursiver Kopieren des gesamten Inhalts eines Ordners auf einen Remote Computer

Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .

Mit dem- `Copy-Item` Cmdlet wird der gesamte Inhalt aus dem `D:\Folder003` Ordner `C:\Folder003_Copy` mithilfe der in der-Variablen gespeicherten Sitzungsinformationen aus dem Ordner in das Verzeichnis auf dem Remote Computer kopiert `$Session` . Die Unterordner werden mit ihren Dateistrukturen intakt kopiert. Der-Vorgang erstellt den `Folder003_Copy` Ordner, wenn er nicht bereits vorhanden ist.

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder003\" -Destination "C:\Folder003_Copy\" -ToSession $Session -Recurse
```

### Beispiel 8: Kopieren einer Datei auf einen Remote Computer und anschließendes Umbenennen der Datei

Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .

Das `Copy-Item` Cmdlet kopiert `scriptingexample.ps1` `D:\Folder004` `C:\Folder004_Copy` mithilfe der in der Variablen gespeicherten Sitzungsinformationen aus dem Ordner in den Ordner auf dem Remote Computer `$Session` . Im Rahmen des Kopiervorgangs ändert der-Befehl den Elementnamen von `scriptingexample.ps1` in `scriptingexample_copy.ps1` , sodass er an e-Mail-Nachrichten angefügt werden kann. Die ursprüngliche Datei wird nicht gelöscht.

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder004\scriptingexample.ps1" -Destination "C:\Folder004_Copy\scriptingexample_copy.ps1" -ToSession $Session
```

### Beispiel 9: Kopieren einer Remote Datei auf den lokalen Computer

Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .

Das- `Copy-Item` Cmdlet kopiert `test.log` `C:\MyRemoteData\` `D:\MyLocalData` mithilfe der in der-Variablen gespeicherten Sitzungsinformationen aus dem Remote-in den lokalen Ordner `$Session` . Die ursprüngliche Datei wird nicht gelöscht.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\test.log" -Destination "D:\MyLocalData\" -FromSession $Session
```

### Beispiel 10: Kopieren des gesamten Inhalts eines Remote Ordners auf den lokalen Computer

Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .

Mit dem- `Copy-Item` Cmdlet wird der gesamte Inhalt aus dem Remote `C:\MyRemoteData\scripts` Ordner `D:\MyLocalData` mithilfe der in der-Variablen gespeicherten Sitzungsinformationen aus dem Remote Ordner in den lokalen Ordner kopiert `$Session` . Wenn der Ordner Scripts Dateien in Unterordnern enthält, werden diese Unterordner mit ihren Dateistrukturen intakt kopiert.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\" -FromSession $Session
```

### Beispiel 11: rekursiver Kopieren des gesamten Inhalts eines Remote Ordners auf den lokalen Computer

Eine Sitzung wird auf dem Remote Computer mit dem Namen **Server01** mit den Anmelde Informationen von erstellt, `Contoso\User01` und die Ergebnisse werden in der Variablen mit dem Namen gespeichert `$Session` .

Mit dem- `Copy-Item` Cmdlet wird der gesamte Inhalt aus dem Remote `C:\MyRemoteData\scripts` Ordner `D:\MyLocalData\scripts` mithilfe der in der-Variablen gespeicherten Sitzungsinformationen aus dem Remote Ordner in den lokalen Ordner kopiert `$Session` . Da der **recurse** -Parameter verwendet wird, erstellt der Vorgang den Ordner "Scripts", falls er nicht bereits vorhanden ist. Wenn der Ordner Scripts Dateien in Unterordnern enthält, werden diese Unterordner mit ihren Dateistrukturen intakt kopiert.

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\scripts" -FromSession $Session -Recurse
```

### Beispiel 12: rekursiver Kopieren von Dateien aus einer Ordnerstruktur in den aktuellen Ordner

In diesem Beispiel wird gezeigt, wie Sie Dateien aus einer mehrstufigen Ordnerstruktur in einen einzelnen flatfolder kopieren.
Die ersten drei Befehle zeigen die vorhandene Ordnerstruktur und den Inhalt von zwei Dateien, beide Namen `file3.txt` .

```powershell
PS C:\temp\test> (Get-ChildItem C:\temp\tree -Recurse).FullName
C:\temp\tree\subfolder
C:\temp\tree\file1.txt
C:\temp\tree\file2.txt
C:\temp\tree\file3.txt
C:\temp\tree\subfolder\file3.txt
C:\temp\tree\subfolder\file4.txt
C:\temp\tree\subfolder\file5.txt

PS C:\temp\test> Get-Content C:\temp\tree\file3.txt
This is file3.txt in the root folder

PS C:\temp\test> Get-Content C:\temp\tree\subfolder\file3.txt
This is file3.txt in the subfolder

PS C:\temp\test> Copy-Item -Path C:\temp\tree -Filter *.txt -Recurse -Container:$false
PS C:\temp\test> (Get-ChildItem . -Recurse).FullName
C:\temp\test\subfolder
C:\temp\test\file1.txt
C:\temp\test\file2.txt
C:\temp\test\file3.txt
C:\temp\test\file4.txt
C:\temp\test\file5.txt

PS C:\temp\test> Get-Content .\file3.txt
This is file3.txt in the subfolder
```

Für das- `Copy-Item` Cmdlet ist der **Container** -Parameter auf festgelegt `$false` . Dies bewirkt, dass der Inhalt des Quell Ordners kopiert wird, behält jedoch die Ordnerstruktur nicht bei. Beachten Sie, dass Dateien mit demselben Namen im Zielordner überschrieben werden.

## PARAMETERS

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

### -Container

Gibt an, dass dieses Cmdlet während des Kopiervorgangs Containerobjekte beibehält. Standardmäßig ist der **Container** -Parameter auf **true** festgelegt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

> [!NOTE]
> Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.
> Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".

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

### -Destination

Gibt den Pfad zum neuen Speicherort an. Der Standardwert ist das aktuelle Verzeichnis.

Um das zu kopierende Element umzubenennen, geben Sie im Wert des **Destination** -Parameters einen neuen Namen an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ausschließen

Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b.. Platzhalterzeichen sind zulässig. Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

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

Gibt einen Filter zum Qualifizieren des **path** -Parameters an. Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt. Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
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

### -Force

Gibt an, dass dieses Cmdlet Elemente kopiert, die anderweitig nicht geändert werden können, z. b. das Kopieren über eine schreibgeschützte Datei oder einen Alias.

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

### -Fromsession

Gibt das **PSSession** -Objekt an, aus dem eine Remote Datei kopiert wird. Wenn Sie diesen Parameter verwenden, verweisen die **path** -und **literalpath** -Parameter auf den lokalen Pfad auf dem Remote Computer.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include

Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b.. Platzhalterzeichen sind zulässig. Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

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

### -Literalpath

Gibt einen Pfad zu einem oder mehreren Speicherorten an. Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

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

### -PassThru

Gibt ein-Objekt zurück, das das Element darstellt, mit dem Sie arbeiten. Standardmäßig generiert dieses Cmdlet keine Ausgabe.

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

### -Path

Gibt den Pfad zu den zu kopierenden Elementen als Zeichen folgen Array an. Platzhalterzeichen sind zulässig.

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

### -Recurse

Gibt an, dass dieses Cmdlet eine rekursive Kopie durchführt.

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

### -Sitzungs

Gibt das **PSSession** -Objekt an, in das eine Remote Datei kopiert wird. Wenn Sie diesen Parameter verwenden, verweist der **Ziel** Parameter auf den lokalen Pfad auf dem Remote Computer.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.

## AUSGABEN

### None oder ein Objekt, das das kopierte Element darstellt.

Wenn Sie den **passthru** -Parameter verwenden, gibt dieses Cmdlet ein Objekt zurück, das das kopierte Element darstellt. Andernfalls generiert dieses Cmdlet keine Ausgabe.

## HINWEISE

Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Clear-Item](Clear-Item.md)

[Get-Item](Get-Item.md)

[Get-PSProvider](Get-PSProvider.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)
