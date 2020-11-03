---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-acl?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Acl
ms.openlocfilehash: a4c25d199b97be24277092bcb815a640a09360dd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212359"
---
# Set-Acl

## ZUSAMMENFASSUNG
Ändert die Sicherheitsbeschreibung für ein angegebenes Element, z. B. eine Datei oder einen Registrierungsschlüssel.

## SYNTAX

### Bypath (Standard)

```
Set-Acl [-Path] <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Byinputobject

```
Set-Acl [-InputObject] <PSObject> [-AclObject] <Object> [-Passthru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Byliteralpath

```
Set-Acl -LiteralPath <String[]> [-AclObject] <Object> [-ClearCentralAccessPolicy] [-Passthru]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-Acl` Cmdlet wird die Sicherheits Beschreibung für ein angegebenes Element, z. b. eine Datei oder einen Registrierungsschlüssel, so geändert, dass Sie den Werten in einer von Ihnen angegebenen Sicherheits Beschreibung entspricht.

Um zu verwenden `Set-Acl` , verwenden Sie den **path** -oder **Inputobject** -Parameter, um das Element zu identifizieren, dessen Sicherheits Beschreibung Sie ändern möchten. Verwenden Sie dann die Parameter **AclObject** oder **SecurityDescriptor** , um eine Sicherheitsbeschreibung mit den Werten anzugeben, die Sie anwenden möchten. `Set-Acl` wendet die angegebene Sicherheits Beschreibung an. Es verwendet den Wert des **AclObject** -Parameters als Modell und ändert die Werte in der Sicherheitsbeschreibung des Elements, sodass sie den Werten im **AclObject** -Parameter entsprechen.

## BEISPIELE

### Beispiel 1: Kopieren einer Sicherheits Beschreibung aus einer Datei in eine andere

```powershell
$DogACL = Get-Acl -Path "C:\Dog.txt"
Set-Acl -Path "C:\Cat.txt" -AclObject $DogACL
```

Diese Befehle kopieren die Werte aus der Sicherheitsbeschreibung der Datei „Dog.txt“ in die Sicherheitsbeschreibung der Datei „Cat.txt“. Wenn die Befehle abgeschlossen sind, stimmen die Sicherheitsbeschreibungen von Dog.txt und Cat.txt überein.

Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung der Dog.txt Datei zu erhalten.
Der Zuweisungs Operator ( `=` ) speichert die Sicherheits Beschreibung im Wert der $DogACL Variable.

Der zweite Befehl verwendet `Set-Acl` , um die Werte in der ACL von Cat.txt in die Werte in zu ändern `$DogACL` .

Der Wert des **Path** -Parameters ist der Pfad zur Datei „Cat.txt“. Der Wert des **aclobject** -Parameters ist die Modell-ACL, in diesem Fall die ACL Dog.txt wie in der `$DogACL` Variablen gespeichert.

### Beispiel 2: Verwenden des Pipeline-Operators zum Übergeben eines Deskriptors

```powershell
Get-Acl -Path "C:\Dog.txt" | Set-Acl -Path "C:\Cat.txt"
```

Dieser Befehl ist fast identisch mit dem Befehl im vorherigen Beispiel, mit dem Unterschied, dass er einen Pipeline Operator () verwendet, `|` um die Sicherheits Beschreibung von einem `Get-Acl` Befehl an einen Befehl zu senden `Set-Acl` .

Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung der Dog.txt Datei zu erhalten. Der Pipeline Operator ( `|` ) übergibt ein Objekt, das den Dog.txt Sicherheits Deskriptor darstellt, an das `Set-Acl` Cmdlet.

Der zweite Befehl verwendet `Set-Acl` , um die Sicherheits Beschreibung von Dog.txt auf Cat.txt anzuwenden.
Wenn der Befehl abgeschlossen ist, stimmen die ACLs von Dog.txt und Cat.txt überein.

### Beispiel 3: Anwenden einer Sicherheits Beschreibung auf mehrere Dateien

```powershell
$NewAcl = Get-Acl File0.txt
Get-ChildItem -Path "C:\temp" -Recurse -Include "*.txt" -Force | Set-Acl -AclObject $NewAcl
```

Diese Befehle wenden die Sicherheits Deskriptoren in der File0.txt-Datei auf alle Textdateien im `C:\Temp` Verzeichnis und alle zugehörigen Unterverzeichnisse an.

Mit dem ersten Befehl wird die Sicherheits Beschreibung der File0.txt Datei im aktuellen Verzeichnis abgerufen und der Zuweisungs Operator ( `=` ) verwendet, um Sie in der `$NewACL` Variablen zu speichern.

Der erste Befehl in der Pipeline verwendet das Get-ChildItem-Cmdlet, um alle Textdateien im Verzeichnis zu erhalten `C:\Temp` . Der **recurse** -Parameter erweitert den-Befehl auf alle Unterverzeichnisse von `C:\temp` . Der **include** -Parameter schränkt die Dateien ein, die auf die Dateien mit der `.txt` Dateinamenerweiterung abgerufen werden. Der **Force** -Parameter ruft versteckte Dateien ab, die andernfalls ausgeschlossen würden. (Sie können nicht verwenden `c:\temp\*.txt` , da der **recurse** -Parameter für Verzeichnisse, nicht für Dateien, funktioniert.)

Der Pipeline Operator ( `|` ) sendet die-Objekte, die die abgerufenen Dateien darstellen, an das `Set-Acl` Cmdlet, das die Sicherheits Beschreibung im **aclobject** -Parameter auf alle Dateien in der Pipeline anwendet.

In der Praxis ist es am besten, den **WhatIf** -Parameter mit allen Befehlen zu verwenden `Set-Acl` , die mehr als ein Element beeinflussen können. In diesem Fall wäre der zweite Befehl in der Pipeline `Set-Acl -AclObject $NewAcl -WhatIf` . Dieser Befehl listet die Dateien auf, die von dem Befehl betroffen wären. Nachdem Sie das Ergebnis überprüft haben, können Sie den Befehl erneut ohne den **WhatIf** -Parameter ausführen.

### Beispiel 4: Deaktivieren der Vererbung und beibehalten von vererbten Zugriffsregeln

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
$isProtected = $true
$preserveInheritance = $true
$NewAcl.SetAccessRuleProtection($isProtected, $preserveInheritance)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

Mit diesen Befehlen wird die Zugriffs Vererbung aus übergeordneten Ordnern deaktiviert, während die vorhandenen vererbten Zugriffsregeln beibehalten werden.

Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung der Dog.txt Datei zu erhalten.

Als nächstes werden Variablen erstellt, um die geerbten Zugriffsregeln in explizite Zugriffsregeln zu konvertieren. Legen Sie die-Variable auf fest, um die von der Vererbung zugeordneten Zugriffsregeln zu schützen `$isProtected` . Legen Sie auf fest, `$true` um die Vererbung zuzulassen. `$isProtected` `$false` Weitere Informationen finden Sie unter [Festlegen des Zugriffs Regel Schutzes](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection).
Die `$preserveInheritance` Variable, die auf festgelegt ist, `$true` um geerbte Zugriffsregeln beizubehalten; false zum Entfernen geerbte Zugriffsregeln. Anschließend wird der Schutz der Zugriffsregeln mithilfe der **SetAccessRuleProtection ()** -Methode aktualisiert.

Mit dem letzten Befehl wird verwendet `Set-Acl` , um die Sicherheits Beschreibung von auf Dog.txt anzuwenden. Wenn der Befehl abgeschlossen ist, werden die ACLs der Dog.txt, die aus dem Ordner "Pets" geerbt wurden, direkt auf Dog.txt angewendet, und neue Zugriffsrichtlinien, die Haustiere hinzugefügt werden, ändern nicht den Zugriff auf Dog.txt.

### Beispiel 5: erteilen der vollständigen Kontrolle der Datei durch Administratoren

```powershell
$NewAcl = Get-Acl -Path "C:\Pets\Dog.txt"
# Set properties
$identity = "BUILTIN\Administrators"
$fileSystemRights = "FullControl"
$type = "Allow"
# Create new rule
$fileSystemAccessRuleArgumentList = $identity, $fileSystemRights, $type
$fileSystemAccessRule = New-Object -TypeName System.Security.AccessControl.FileSystemAccessRule -ArgumentList $fileSystemAccessRuleArgumentList
# Apply new rule
$NewAcl.SetAccessRule($fileSystemAccessRule)
Set-Acl -Path "C:\Pets\Dog.txt" -AclObject $NewAcl
```

Mit diesem Befehl wird der Gruppe " **BUILTIN\Administrators** " die vollständige Kontrolle über die Dog.txt Datei erteilt.

Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung der Dog.txt Datei zu erhalten.

Die nächsten Variablen werden erstellt, um der Gruppe **BUILTIN\Administrators** die vollständige Kontrolle über die Dog.txt Datei zu erteilen. Die `$identity` Variable, die auf den Namen eines [Benutzerkontos](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)festgelegt ist.
Die `$fileSystemRights` Variable, die auf FullControl festgelegt ist, und kann einer der [FileSystemRights](/dotnet/api/system.security.accesscontrol.filesystemrights) -Werte sein, der den Typ des Vorgangs angibt, der der Zugriffs Regel zugeordnet ist. Die `$type` Variable, die auf "Allow" festgelegt ist, gibt an, ob der Vorgang zugelassen oder verweigert werden soll. Die `$fileSystemAccessRuleArgumentList` Variable ist eine Argumentliste, die beim Erstellen des neuen **FileSystemAccessRule** -Objekts übermittelt werden soll. Anschließend wird ein neues **FileSystemAccessRule** -Objekt erstellt, und das **FileSystemAccessRule** -Objekt wird an die **SetAccessRule ()** -Methode weitergegeben, fügt die neue Zugriffs Regel hinzu.

Mit dem letzten Befehl wird verwendet `Set-Acl` , um die Sicherheits Beschreibung von auf Dog.txt anzuwenden.
Wenn der Befehl abgeschlossen ist, verfügt die Gruppe " **BUILTIN\Administrators** " über Vollzugriff auf die Dog.txt.

## PARAMETERS

### -Aclobject

Gibt eine ACL mit den gewünschten Eigenschaftswerten an. `Set-Acl` ändert die ACL des durch den **path** -oder **Inputobject** -Parameter angegebenen Elements, um die Werte im angegebenen Sicherheits Objekt abzugleichen.

Sie können die Ausgabe eines `Get-Acl` Befehls in einer Variablen speichern und dann den **aclobject** -Parameter verwenden, um die Variable zu übergeben, oder einen `Get-Acl` Befehl eingeben.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Clearcentralaccesspolicy

Entfernt die zentrale Zugriffsrichtlinie aus dem angegebenen Element.

Ab Windows Server 2012 können Administratoren mit Active Directory und Gruppenrichtlinie zentrale Zugriffsrichtlinien für Benutzer und Gruppen festlegen. Weitere Informationen finden Sie unter [dynamische Access Control: Szenarioübersicht](/windows-server/identity/solution-guides/dynamic-access-control--scenario-overview).

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByPath, ByLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ausschließen

Lässt die angegebenen Elemente aus. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b.. Platzhalter sind zulässig.

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

Gibt einen Filter im Format oder in der Sprache des Anbieters an. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Die Syntax des Filters einschließlich der Verwendung von Platzhaltern ist vom Anbieter abhängig. Filter sind effizienter als andere Parameter, da Sie vom Anbieter beim Abrufen der Objekte angewendet werden, anstatt dass PowerShell die Objekte nach dem Abrufen filtert.

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

Ändert nur die angegebenen Elemente. Der Wert dieses Parameters qualifiziert den **Path** -Parameter.
Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b.. Platzhalter sind zulässig.

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

Ändert die Sicherheitsbeschreibung für das angegebene Objekt. Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl ein, mit dem das Objekt abgerufen wird.

Sie können das Objekt nicht an die Pipeline übergeben, die geändert werden soll `Set-Acl` . Verwenden Sie stattdessen den **InputObject** -Parameter explizit im Befehl.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Literalpath

Ändert die Sicherheitsbeschreibung für das angegebene Element. Im Gegensatz zu **Path** wird der Wert des **LiteralPath** -Parameters genauso verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen ( `'` ) einschließen.
Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru

Gibt ein Objekt zurück, das die geänderte Sicherheitsbeschreibung darstellt. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

Ändert die Sicherheitsbeschreibung für das angegebene Element. Geben Sie den Pfad zu einem Element ein, z. B. einen Pfad zu einer Datei oder einem Registrierungsschlüssel. Platzhalter sind zulässig.

Wenn Sie ein Sicherheits Objekt an übergeben `Set-Acl` (entweder mithilfe des **aclobject** -oder **securityDescriptor** -Parameters oder durch Übergeben eines Sicherheits Objekts von Get-Acl an `Set-Acl` ) und den **path** -Parameter (Name und Wert) weglassen, `Set-Acl` verwendet den Pfad, der im Sicherheits Objekt enthalten ist.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Security. AccessControl. ObjectSecurity, System. Security. AccessControl. CommonSecurityDescriptor

Sie können ein ACL-Objekt oder eine Sicherheits Beschreibung an die Pipeline übergeben `Set-Acl` .

## AUSGABEN

### System. Security. AccessControl. File Security

Standardmäßig `Set-Acl` generiert keine Ausgabe.
Allerdings wird bei Verwendung des **Passthru** -Parameters ein Sicherheitsobjekt generiert.
Der Typ des Sicherheitsobjekts hängt vom Typ des Elements ab.

## HINWEISE

 Das `Set-Acl` -Cmdlet wird vom PowerShell-Dateisystem und von Registrierungs Anbietern unterstützt. Sie können es verwenden, um die Sicherheitsbeschreibungen von Dateien, Verzeichnissen und Registrierungsschlüsseln zu ändern.

## VERWANDTE LINKS

[Get-Acl](Get-Acl.md)

[FileSystemAccessRule](/dotnet/api/system.security.accesscontrol.filesystemaccessrule.-ctor)

[ObjectSecurity. SetAccessRuleProtection](/dotnet/api/system.security.accesscontrol.objectsecurity.setaccessruleprotection)

[File System Rights](/dotnet/api/system.security.accesscontrol.filesystemrights)
