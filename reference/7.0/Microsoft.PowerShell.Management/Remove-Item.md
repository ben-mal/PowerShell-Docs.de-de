---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/07/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Item
ms.openlocfilehash: ddb3f8d1889887e01db8663e21cdb0323e6d4084
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209804"
---
# Remove-Item

## ZUSAMMENFASSUNG
Löscht die angegebenen Elemente.

## SYNTAX

### Pfad (Standard)

```
Remove-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

### LiteralPath

```
Remove-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Remove-Item` Cmdlet werden ein oder mehrere Elemente gelöscht. Da es von vielen Anbietern unterstützt wird, können viele verschiedene Elementtypen, einschließlich Dateien, Ordner, Registrierungsschlüssel, Variablen, Aliase und Funktionen, gelöscht werden.

## BEISPIELE

### Beispiel 1: Löschen von Dateien mit einer Dateinamenerweiterung

In diesem Beispiel werden alle Dateien gelöscht, deren Namen einen Punkt ( `.` ) aus dem Ordner enthalten `C:\Test` . Da der Befehl einen Punkt angibt, löscht der Befehl keine Ordner oder Dateien ohne Dateinamenerweiterung.

```powershell
Remove-Item C:\Test\*.*
```

### Beispiel 2: Löschen einiger Dokument Dateien in einem Ordner

In diesem Beispiel wird aus dem aktuellen Ordner alle Dateien mit einer `.doc` Dateinamenerweiterung und einem Namen gelöscht, der nicht enthält `*1*` .

```powershell
Remove-Item * -Include *.doc -Exclude *1*
```

Dabei wird das Platzhalter Zeichen ( `*` ) verwendet, um den Inhalt des aktuellen Ordners anzugeben. Er verwendet die Parameter " **include** " und " **Exclude** ", um die zu löschenden Dateien anzugeben.

### Beispiel 3: Löschen ausgeblendeter, Schreib geschützter Dateien

Mit diesem Befehl wird eine Datei gelöscht, die sowohl *ausgeblendet* als auch schreibgeschützt *ist.*

```powershell
Remove-Item -Path C:\Test\hidden-RO-file.txt -Force
```

Er verwendet den **path** -Parameter, um die Datei anzugeben. Er verwendet den **Force** -Parameter, um ihn zu löschen. Ohne " **Force** " können Sie keine Schreib _geschützten oder_ _ausgeblendeten_ Dateien löschen.

### Beispiel 4: rekursiver Löschen von Dateien in Unterordnern

Mit diesem Befehl werden alle CSV-Dateien im aktuellen Ordner und alle Unterordner rekursiv gelöscht.

Da der **recurse** -Parameter in `Remove-Item` ein bekanntes Problem aufweist, verwendet der Befehl in diesem Beispiel, `Get-ChildItem` um die gewünschten Dateien zu erhalten, und verwendet dann den Pipeline-Operator, um Sie an zu übergeben `Remove-Item` .

```powershell
Get-ChildItem * -Include *.csv -Recurse | Remove-Item
```

Im `Get-ChildItem` Befehl hat **path** den Wert ( `*` ), der den Inhalt des aktuellen Ordners darstellt. Er verwendet **include** , um den CSV-Dateityp anzugeben, und verwendet **recurse** , um den Abruf rekursiv zu machen. Wenn Sie versuchen, den Dateityp anzugeben, z. b. `-Path *.csv` , interpretiert das Cmdlet den Betreff der Suche als Datei ohne untergeordnete Elemente, und die **Rekurse** schlägt fehl.

### Beispiel 5: rekursiver Löschen von unter Schlüsseln

Mit diesem Befehl werden der Registrierungsschlüssel "oldapp" und alle zugehörigen Unterschlüssel und Werte gelöscht. Verwendet `Remove-Item` , um den Schlüssel zu entfernen. Der Pfad ist angegeben, der optionale Parameter Name ( **path** ) wird jedoch ausgelassen.

Der **recurse** -Parameter löscht den gesamten Inhalt des "oldapp"-Schlüssels rekursiv. Wenn der Schlüssel Unterschlüssel enthält und Sie den **recurse** -Parameter weglassen, werden Sie aufgefordert, zu bestätigen, dass Sie den Inhalt des Schlüssels löschen möchten.

```powershell
Remove-Item HKLM:\Software\MyCompany\OldApp -Recurse
```

### Beispiel 6: Löschen von Dateien mit Sonderzeichen

Im folgenden Beispiel wird gezeigt, wie Sie Dateien löschen, die Sonderzeichen wie eckige Klammern oder Klammern enthalten.

```powershell
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*'
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*' | ForEach-Object { Remove-Item -LiteralPath $_.Name }
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
```

### Beispiel 7: Entfernen eines alternativen Datenstroms

Dieses Beispiel zeigt, wie Sie den dynamischen **Stream** -Parameter des `Remove-Item` Cmdlets verwenden, um einen alternativen Datenstrom zu löschen. Der Stream-Parameter wird in Windows PowerShell 3,0 eingeführt.

```powershell
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
   FileName: \\C:\Test\Copy-Script.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

```

```powershell
Remove-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
Get-Item : Could not open alternate data stream 'Zone.Identifier' of file 'C:\Test\Copy-Script.ps1'.
At line:1 char:1
+ Get-Item 'C:\Test\Copy-Script.ps1' -Stream Zone.Identifier
+ [!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()]~~
    + CategoryInfo          : ObjectNotFound: (C:\Test\Copy-Script.ps1:String) [Get-Item], FileNotFoundE
   xception
    + FullyQualifiedErrorId : AlternateDataStreamNotFound,Microsoft.PowerShell.Commands.GetItemCommand

```

Der **Stream** -Parameter ruft `Get-Item` den " **Zone. Identifier** "-Stream der `Copy-Script.ps1` Datei ab. `Remove-Item` verwendet den **Stream** -Parameter, um den " **Zone. Identifier** "-Stream der Datei zu entfernen. Zum Schluss `Get-Item` zeigt das Cmdlet, dass der Datenstrom " **Zone. Identifier** " gelöscht wurde.

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

Zwingt das Cmdlet, Elemente zu entfernen, die anderweitig nicht geändert werden können, z. b. ausgeblendete oder schreibgeschützte Dateien oder schreibgeschützte Aliase oder Variablen. Mit dem Cmdlet können keine konstanten Aliase oder Variablen entfernt werden.
Die Implementierung unterscheidet sich bei den einzelnen Anbietern. Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md). Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.

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

### -Path

Gibt einen Pfad zu den Elementen an, die entfernt werden.
Platzhalterzeichen sind zulässig.

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

Gibt an, dass dieses Cmdlet die Elemente an den angegebenen Speicherorten und in allen untergeordneten Elementen der Speicherorte löscht.

Bei Verwendung mit dem **include** -Parameter löscht der **recurse** -Parameter möglicherweise nicht alle Unterordner oder alle untergeordneten Elemente. Dies ist ein bekanntes Problem. Um dieses Problem zu umgehen, können Sie die Ergebnisse des `Get-ChildItem -Recurse` Befehls an weiterleiten `Remove-Item` , wie in "Beispiel 4" in diesem Thema beschrieben.

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

### -Stream

Der **Stream** -Parameter ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Remove-Item` .
Dieser Parameter funktioniert nur in Dateisystemlaufwerken.

Sie können verwenden `Remove-Item` , um einen alternativen Datenstrom zu löschen. Es ist jedoch nicht die empfohlene Methode, Sicherheitsüberprüfungen zu deaktivieren, die Dateien blockieren, die aus dem Internet heruntergeladen werden. Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert. Weitere Informationen finden Sie in den folgenden Artikeln:

- [about_Preference_Variables](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)
- [about_Functions_CmdletBindingAttribute](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

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

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

Das- `Remove-Item` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

Wenn Sie versuchen, einen Ordner zu löschen, der Elemente ohne Verwendung des **recurse** -Parameters enthält, fordert das Cmdlet zur Bestätigung auf. Die Verwendung von `-Confirm:$false` unterdrückt die Eingabeaufforderung nicht. Dies ist beabsichtigt.

## VERWANDTE LINKS

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[Move-Item](Move-Item.md)

[New-Item](New-Item.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Preference_Variables](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)

[about_Functions_CmdletBindingAttribute](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)
