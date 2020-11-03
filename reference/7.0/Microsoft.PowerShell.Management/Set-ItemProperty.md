---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: b9a2386b41ec4d64200283a5cd3b802d254b5475
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217284"
---
# Set-ItemProperty

## ZUSAMMENFASSUNG
Erstellt oder ändert den Wert für eine Eigenschaft eines Elements.

## SYNTAX

### propertyvaluepathset (Standard)

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### propertypsobjectpathset

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### propertyvalueliteralpathset

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### propertypsobjectliteralpathset

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Set-ItemProperty` Cmdlet ändert den Wert der-Eigenschaft des angegebenen Elements.
Sie können mit dem Cmdlet die Eigenschaften von Elementen festlegen oder ändern.
Beispielsweise können Sie verwenden, `Set-ItemProperty` um den Wert der **isread only** -Eigenschaft eines Datei Objekts auf festzulegen `$True` .

Außerdem verwenden Sie `Set-ItemProperty` , um Registrierungs Werte und-Daten zu erstellen und zu ändern.
Sie haben z. B. die Möglichkeit, einen neuen Registrierungseintrag in einem Schlüssel hinzuzufügen und seinen Wert festzulegen oder zu ändern.

## BEISPIELE

### Beispiel 1: Festlegen einer Eigenschaft einer Datei

Mit diesem Befehl wird der Wert der **isread only** -Eigenschaft der Datei "final.doc" auf "true" festgelegt.
Dabei wird **path** verwendet, um die Datei anzugeben, den **Namen** , um den Namen der Eigenschaft anzugeben, und den **value** -Parameter, um den neuen Wert anzugeben.

Bei der Datei handelt es sich um ein **System. IO. FileInfo** -Objekt, und **isread only** ist nur eine seiner Eigenschaften.
Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property` .

Die `$true` Automatische Variable stellt den Wert "true" dar.
Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### Beispiel 2: Erstellen eines Registrierungs Eintrags und-Werts

In diesem Beispiel wird gezeigt, wie verwendet wird, `Set-ItemProperty` um einen neuen Registrierungs Eintrag zu erstellen und dem Eintrag einen Wert zuzuweisen. Er erstellt den Eintrag "noofemployees" im Schlüssel "contosocompany" im `HKLM\Software` Schlüssel und legt seinen Wert auf 823 fest.

Da Registrierungseinträge als Eigenschaften der Registrierungsschlüssel betrachtet werden, bei denen es sich um Elemente handelt, verwenden Sie, `Set-ItemProperty` um Registrierungseinträge zu erstellen und ihre Werte festzulegen und zu ändern.

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 823
```

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 824
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

Der erste Befehl erstellt den Registrierungs Eintrag.
Dabei wird **path** verwendet, um den Pfad des `HKLM:` Laufwerks und den Schlüssel "software\mycompany" anzugeben.
Der Befehl verwendet den **Namen** , um den Namen und den **Wert** des Eintrags anzugeben, um einen Wert anzugeben.

Der zweite Befehl verwendet das `Get-ItemProperty` Cmdlet, um den neuen Registrierungs Eintrag anzuzeigen.
Wenn Sie das- `Get-Item` `Get-ChildItem` Cmdlet oder das-Cmdlet verwenden, werden die Einträge nicht angezeigt, da es sich um Eigenschaften eines Schlüssels handelt, nicht um Elemente oder untergeordnete Elemente.

Der dritte Befehl ändert den Wert des **noofemployees** -Eintrags in 824.

Sie können auch mit dem `New-ItemProperty` Cmdlet den Registrierungs Eintrag und seinen Wert erstellen und dann verwenden `Set-ItemProperty` , um den Wert zu ändern.

Weitere Informationen zum Laufwerk erhalten Sie, wenn Sie `HKLM:` eingeben `Get-Help Get-PSDrive` .
Weitere Informationen zur Verwendung von PowerShell zum Verwalten der Registrierung erhalten Sie, wenn Sie eingeben `Get-Help Registry` .

### Beispiel 3: Ändern eines Elements mithilfe der Pipeline

Diese Befehle zeigen, wie ein Pipeline Operator () verwendet wird, um `|` ein Element an zu senden `Set-ItemProperty` .

Der erste Teil des Befehls verwendet `Get-ChildItem` , um ein Objekt zu erhalten, das die Datei "Weekly.txt" darstellt. Der Befehl verwendet einen Pipeline Operator, um das Datei Objekt an zu senden `Set-ItemProperty` .
Der `Set-ItemProperty` Befehl verwendet die Parameter " **Name** " und " **value** ", um die Eigenschaft und ihren neuen Wert anzugeben.

Dieser Befehl entspricht der Verwendung des **Inputobject** -Parameters zum Angeben des abzurufenden Objekts `Get-ChildItem` .

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
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

Zwingt das Cmdlet, eine Eigenschaft für Elemente festzulegen, auf die der Benutzer anderweitig nicht zugreifen kann.
Die Implementierung unterscheidet sich bei den einzelnen Anbietern.
Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

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

### -InputObject

Gibt das-Objekt mit den Eigenschaften an, die von diesem Cmdlet geändert werden.
Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl ein, mit dem das Objekt abgerufen wird.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: propertyPSObjectPathSet, propertyPSObjectLiteralPathSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Literalpath

Gibt einen Pfad zu einem oder mehreren Speicherorten an. Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: propertyPSObjectLiteralPathSet, propertyValueLiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt den Namen der Eigenschaft an.

```yaml
Type: System.String
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das die Element Eigenschaft darstellt.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### -Path

Gibt den Pfad der Elemente mit der Eigenschaft an, die geändert werden soll.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Type

**Type** ist ein dynamischer Parameter, den der Registrierungs Anbieter dem `Set-ItemProperty` Cmdlet hinzufügt.
Dieser Parameter funktioniert nur in den Registrierungs Laufwerken.

Gibt den Typ der Eigenschaft an, die von diesem Cmdlet hinzugefügt wird.
Zulässige Werte für diesen Parameter:

- **String** : gibt eine NULL-terminierte Zeichenfolge an. Entspricht **REG_SZ**.
- **ExpandString** : gibt eine NULL-terminierte Zeichenfolge an, die nicht erweiterte Verweise auf Umgebungsvariablen enthält, die erweitert werden, wenn der Wert abgerufen wird. Entspricht **REG_EXPAND_SZ**.
- **Binary** : gibt Binärdaten in beliebiger Form an. Entspricht **REG_BINARY**.
- **DWORD** : gibt eine 32-Bit-Binärzahl an. Entspricht **REG_DWORD**.
- **MultiString** : gibt ein Array von auf NULL endenden Zeichen folgen an, die mit zwei NULL-Zeichen beendet werden.
  Entspricht **REG_MULTI_SZ**.
- **QWORD** : gibt eine 64-Bit-Binärzahl an. Entspricht **REG_QWORD**.
- **Unknown** : gibt einen nicht unterstützten Registrierungs Datentyp an, z. b. **REG_RESOURCE_LIST**.

```yaml
Type: Microsoft.Win32.RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value

Gibt den Wert der Eigenschaft an.

```yaml
Type: System.Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System. Management. Automation. psobject

Sie können Objekte über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### None, System. Management. Automation. pscustomobject

Dieses Cmdlet generiert ein **pscustomobject** -Objekt, das das geänderte Element darstellt, und den neuen Eigenschafts Wert, wenn Sie den **passthru** -Parameter angeben.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

`Set-ItemProperty` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Get-ItemProperty](Get-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
