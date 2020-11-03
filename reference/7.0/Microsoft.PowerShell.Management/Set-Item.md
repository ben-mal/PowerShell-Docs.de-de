---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Item
ms.openlocfilehash: 4485b1a140b1496ee80d81d1526b3d76e446fd34
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210911"
---
# Set-Item

## ZUSAMMENFASSUNG
Ändert den Wert eines Elements in den Wert, der im Befehl angegeben wird.

## SYNTAX

### Pfad (Standard)

```
Set-Item [-Path] <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Set-Item -LiteralPath <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-Item` Cmdlet wird der Wert eines Elements, z. b. einer Variablen oder eines Registrierungsschlüssels, in den im Befehl angegebenen Wert geändert.

## BEISPIELE

### Beispiel 1: Erstellen eines Alias

Dieser Befehl erstellt einen Alias von NP für Notepad.

```powershell
Set-Item -Path alias:np -Value "c:\windows\notepad.exe"
```

### Beispiel 2: Ändern des Werts einer Umgebungsvariablen

Dieser Befehl ändert den Wert der Umgebungsvariablen "UserRole" in "Administrator".

```powershell
Set-Item -Path env:UserRole -Value "Administrator"
```

### Beispiel 3: Ändern der prompt-Funktion

Mit diesem Befehl wird die prompt-Funktion so geändert, dass Sie die Zeit vor dem Pfad anzeigt.

```powershell
Set-Item -Path function:prompt -Value {'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '}
```

### Beispiel 4: Festlegen von Optionen für die prompt-Funktion

Dieser Befehl legt die Optionen " **allscope** " und "read **only** " für die prompt-Funktion fest.
Dieser Befehl verwendet den dynamischen **options** -Parameter von `Set-Item` .
Der **options** -Parameter ist nur in verfügbar, `Set-Item` Wenn er mit dem **Alias** -oder **Funktions** Anbieter verwendet wird.

```powershell
Set-Item -Path function:prompt -Options "AllScope,ReadOnly"
```

## PARAMETERS

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

Zwingt das Cmdlet, Elemente festzulegen, die anderweitig nicht geändert werden können, z. b. schreibgeschützte Alias oder Variablen. Mit diesem Cmdlet können keine konstanten Aliase oder Variablen geändert werden.
Die Implementierung unterscheidet sich bei den einzelnen Anbietern.
Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).
Selbst bei Verwendung des *Force* -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.

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

Übergibt ein Objekt, das das Element darstellt, an die Pipeline.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

Gibt einen Pfad zum Speicherort der Elemente an.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Value

Gibt einen neuen Wert für das Element an.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

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

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.Object

Sie können ein Objekt, das den neuen Wert des Elements darstellt, über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### None oder ein Objekt, das das neue oder geänderte Element darstellt.

Dieses Cmdlet generiert ein Objekt, das das Element darstellt, wenn Sie den *passthru* -Parameter angeben.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

- `Set-Item` wird vom PowerShell-File System-Anbieter nicht unterstützt. Verwenden Sie das-Cmdlet, um die Werte von Elementen im Dateisystem zu ändern `Set-Content` .
- In den Registrierungs Laufwerken `HKLM:` und `HKCU:` `Set-Item` ändert die Daten im (Standardwert) eines Registrierungsschlüssels.
  - Verwenden Sie das `New-Item` Cmdlet und, um die Namen von Registrierungs Schlüsseln zu erstellen und zu ändern `Rename-Item` .
  - Um die Namen und Daten in Registrierungs Werten zu ändern, verwenden Sie die `New-ItemProperty` `Set-ItemProperty` `Rename-ItemProperty` Cmdlets, und.
- `Set-Item` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.
  Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .
  Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
