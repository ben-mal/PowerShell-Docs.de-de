---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Item
ms.openlocfilehash: f05101f06e4911a797d3342b2b535780badeaefd
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211060"
---
# Rename-Item

## ZUSAMMENFASSUNG
Benennt ein Element in einem PowerShell-Anbieter Namespace um.

## SYNTAX

### Bypath (Standard)

```
Rename-Item [-Path] <String> [-NewName] <String> [-Force] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### Byliteralpath

```
Rename-Item -LiteralPath <String> [-NewName] <String> [-Force] [-PassThru]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## DESCRIPTION

Das- `Rename-Item` Cmdlet ändert den Namen eines angegebenen Elements. Dieses Cmdlet hat keine Auswirkungen auf den Inhalt des umbenannten Elements.

Sie können nicht verwenden `Rename-Item` , um ein Element zu verschieben, z. b. durch Angeben eines Pfads mit dem neuen Namen. Verwenden Sie das-Cmdlet, um ein Element zu verschieben und umzubenennen `Move-Item` .

## BEISPIELE

### Beispiel 1: Umbenennen einer Datei

Mit diesem Befehl wird die Datei `daily_file.txt` in umbenannt `monday_file.txt` .

```powershell
Rename-Item -Path "c:\logfiles\daily_file.txt" -NewName "monday_file.txt"
```

### Beispiel 2: Umbenennen und Verschieben eines Elements

Sie können nicht verwenden `Rename-Item` , um ein Element umzubenennen und zu verschieben. Insbesondere können Sie keinen Pfad für den Wert des **NewName** -Parameters angeben, es sei denn, der Pfad ist identisch mit dem im **path** -Parameter angegebenen Pfad. Andernfalls ist nur ein neuer Name zulässig.

In diesem Beispiel wird versucht, die `project.txt` Datei im aktuellen Verzeichnis `old-project.txt` im Verzeichnis in umzubenennen `D:\Archive` . Das Ergebnis ist der in der Ausgabe angezeigte Fehler.

```powershell
Rename-Item -Path "project.txt" -NewName "d:\archive\old-project.txt"
```

```Output
Rename-Item : can't rename because the target specified represents a path or device name.
At line:1 char:12
+ Rename-Item <<<<  -path project.txt -NewName d:\archive\old-project.txt
+ CategoryInfo          : InvalidArgument: (:) [Rename-Item], PS>  Move-Item -Path "project.txt" -De
stination "d:\archive\old-project.txt"
```

### Beispiel 3: Umbenennen eines Registrierungsschlüssels

In diesem Beispiel wird ein Registrierungsschlüssel von " **Werbung** " in " **Marketing** " umbenannt. Nach Abschluss des Befehls wurde der Schlüssel umbenannt, die Registrierungseinträge im Schlüssel sind jedoch unverändert.

```powershell
Rename-Item -Path "HKLM:\Software\MyCompany\Advertising" -NewName "Marketing"
```

### Beispiel 4: Umbenennen mehrerer Dateien

In diesem Beispiel werden alle `*.txt` Dateien im aktuellen Verzeichnis in umbenannt `*.log` .

```powershell
Get-ChildItem *.txt
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.TXT
-a----        10/3/2019   7:46 AM           2918 Monday.Txt
-a----        10/3/2019   7:47 AM           2918 Wednesday.txt
```

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.Name -replace '.txt','.log' }
Get-ChildItem *.log
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.log
-a----        10/3/2019   7:46 AM           2918 Monday.log
-a----        10/3/2019   7:47 AM           2918 Wednesday.log
```

Mit dem- `Get-ChildItem` Cmdlet werden alle Dateien im aktuellen Ordner `.txt` mit einer Dateierweiterung abgerufen und an weitergeleitet `Rename-Item` . Der Wert von **NewName** ist ein Skriptblock, der ausgeführt wird, bevor der Wert an den **NewName** -Parameter gesendet wird.

Im Skriptblock `$_` stellt die automatische Variable jedes Datei Objekt dar, wie es über die Pipeline an den Befehl gesendet wird. Der Skriptblock verwendet den- `-replace` Operator, um die Dateierweiterung der einzelnen Dateien durch zu ersetzen `.log` . Beachten Sie, dass bei der Übereinstimmung mit dem- `-replace` Operator nicht zwischen Groß-

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
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Zwingt das Cmdlet, Elemente umzubenennen, die anderweitig nicht geändert werden können, z. b. ausgeblendete oder schreibgeschützte Dateien oder schreibgeschützte Aliase oder Variablen. Mit dem-Cmdlet können keine Konstanten Aliase oder Variablen geändert werden.
Die Implementierung unterscheidet sich bei den einzelnen Anbietern. Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.

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

### -Literalpath

Gibt einen Pfad zu einem oder mehreren Speicherorten an. Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Newname

Gibt den neuen Namen des Elements an. Geben Sie nur einen Namen ein, nicht einen Pfad und einen Namen. Wenn Sie einen Pfad eingeben, der von dem im **path** -Parameter angegebenen Pfad abweicht, `Rename-Item` generiert einen Fehler.
Verwenden Sie, um ein Element umzubenennen und zu verschieben `Move-Item` .

Sie können keine Platzhalter Zeichen im Wert des **NewName** -Parameters verwenden. Wenn Sie einen Namen für mehrere Dateien angeben möchten, verwenden Sie den **Replace** -Operator in einem regulären Ausdruck. Weitere Informationen zum Replace-Operator finden Sie unter [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das das Element für die Pipeline darstellt. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

Gibt den Pfad des umzubenennenden Elements an.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.

## AUSGABEN

### None oder ein Objekt, das das umbenannte Element darstellt.

Dieses Cmdlet generiert ein Objekt, das das umbenannte Element darstellt, wenn Sie den **passthru** -Parameter angeben. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

`Rename-Item` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-ChildItem](Get-ChildItem.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
