---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-acl?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Acl
ms.openlocfilehash: 118c3e563743cee03dc7a75ca68e0979c1522f07
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347073"
---
# Get-Acl

## ZUSAMMENFASSUNG
Ruft die Sicherheitsbeschreibung für eine Ressource ab, z. B. eine Datei oder einen Registrierungsschlüssel.

## SYNTAX

### Bypath (Standard)

```
Get-Acl [[-Path] <String[]>] [-Audit] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [<CommonParameters>]
```

### Byinputobject

```
Get-Acl -InputObject <PSObject> [-Audit] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### Byliteralpath

```
Get-Acl [-LiteralPath <String[]>] [-Audit] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Acl` Cmdlet werden Objekte abgerufen, die die Sicherheits Beschreibung einer Datei oder Ressource darstellen. Die Sicherheitsbeschreibung enthält die Zugriffssteuerungslisten (Access Control Lists, ACLs) der Ressource. Die ACL gibt die Berechtigungen an, über die Benutzer und Benutzergruppen für den Zugriff auf die Ressource verfügen.

Ab Windows PowerShell 3,0 können Sie den **Inputobject** -Parameter von verwenden, `Get-Acl` um die Sicherheits Beschreibung von Objekten mit einem Pfad zu erhalten.

## BEISPIELE

### Beispiel 1: erhalten einer ACL für einen Ordner

In diesem Beispiel wird die Sicherheits Beschreibung des `C:\Windows` Verzeichnisses abgerufen.

```powershell
Get-Acl C:\Windows
```

### Beispiel 2: erhalten einer ACL für einen Ordner mithilfe von Platzhaltern

In diesem Beispiel werden der PowerShell-Pfad und die SDDL für alle `.log` Dateien im `C:\Windows` Verzeichnis abgerufen, deren Namen mit beginnen `s` .

```powershell
Get-Acl C:\Windows\s*.log | Format-List -Property PSPath, Sddl
```

Der Befehl verwendet das `Get-Acl` Cmdlet, um Objekte zu erhalten, die die Sicherheits Deskriptoren der einzelnen Protokolldateien darstellen. Er verwendet einen Pipeline Operator ( `|` ), um die Ergebnisse an das `Format-List` Cmdlet zu senden. Der Befehl verwendet den **Property** -Parameter von `Format-List` , um nur die **pspath** -und **SDDL** -Eigenschaften der einzelnen Sicherheits deskriptorobjekte anzuzeigen.

Listen werden häufig in PowerShell verwendet, da lange Werte in Tabellen abgeschnitten angezeigt werden.

Die **SDDL** -Werte sind für Systemadministratoren hilfreich, da es sich dabei um einfache Textzeichenfolgen handelt, die alle Informationen in der Sicherheitsbeschreibung enthalten. Daher können sie einfach übergeben und gespeichert und bei Bedarf analysiert werden.

### Beispiel 3: Abruf der Anzahl der Überwachungs Einträge für eine ACL

In diesem Beispiel werden die Sicherheits Deskriptoren der `.log` Dateien im Verzeichnis abgerufen, `C:\Windows` deren Namen mit beginnen `s` .

```powershell
Get-Acl C:\Windows\s*.log -Audit | ForEach-Object { $_.Audit.Count }
```

Mit dem **Audit** -Parameter werden die Überwachungsdatensätze aus der SACL in der Sicherheitsbeschreibung abgerufen.
Anschließend wird mit dem `ForEach-Object` Cmdlet die Anzahl der Überwachungsdaten Sätze gezählt, die den einzelnen Dateien zugeordnet sind. Das Ergebnis ist eine Liste von Zahlen, die die Anzahl der Überwachungsdatensätze für jede Protokolldatei darstellen.

### Beispiel 4: erhalten einer Zugriffs Steuerungs Liste (ACL) für einen Registrierungsschlüssel

In diesem Beispiel wird das- `Get-Acl` Cmdlet verwendet, um die Sicherheits Beschreibung des Control-unter Schlüssels ( `HKLM:\SYSTEM\CurrentControlSet\Control` ) der Registrierung zu erhalten.

```powershell
Get-Acl -Path HKLM:\System\CurrentControlSet\Control | Format-List
```

Der **path** -Parameter gibt den Steuerelement Unterschlüssel an. Der Pipeline Operator ( `|` ) übergibt die Sicherheits Beschreibung, die `Get-Acl` an den `Format-List` Befehl gelangt, der die Eigenschaften der Sicherheits Beschreibung als Liste formatiert, sodass Sie leicht lesbar sind.

### Beispiel 5: erhalten einer ACL mithilfe von **Inputobject**

In diesem Beispiel wird der **Inputobject** -Parameter von verwendet `Get-Acl` , um die Sicherheits Beschreibung für ein Speichersubsystem-Objekt zu erhalten.

```powershell
Get-Acl -InputObject (Get-StorageSubSystem -Name S087)
```

## PARAMETERS

### -Überprüfung

Ruft die Überwachungsdaten für die Sicherheitsbeschreibung aus der System-Zugriffssteuerungsliste (SACL) ab.

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

Ruft nur die angegebenen Elemente ab. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b.. Platzhalter sind zulässig.

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

### -Path

Gibt den Pfad zu einer Ressource an. `Get-Acl` Ruft die Sicherheits Beschreibung der Ressource ab, die durch den Pfad angegeben wird. Platzhalter sind zulässig. Wenn Sie den **path** -Parameter weglassen, ruft `Get-Acl` die Sicherheits Beschreibung des aktuellen Verzeichnisses ab.

Der Parametername (Path) ist optional.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -InputObject

Ruft die Sicherheitsbeschreibung für das angegebene Objekt ab. Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl ein, mit dem das Objekt abgerufen wird.

Ein Objekt, das kein Pfad ist, kann nicht an übergeben werden `Get-Acl` . Verwenden Sie stattdessen den **InputObject** -Parameter explizit im Befehl.

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Literalpath

Gibt den Pfad zu einer Ressource an. Im Gegensatz zu **Path** wird der Wert des **LiteralPath** -Parameters genauso verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Get-Acl` .

## AUSGABEN

### System. Security. AccessControl. File Security, System. Security. AccessControl. Director ysecurity, System. Security. AccessControl. RegistrySecurity

`Get-Acl` Gibt ein-Objekt zurück, das die Abbild-ACLs darstellt. Der Objekttyp richtet sich nach der ACL-Typ.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

Standardmäßig `Get-Acl` zeigt den PowerShell-Pfad der Ressource ( `<provider>::<resource-path>` ), den Besitzer der Ressource und "Access", eine Liste (Array) der Zugriffs Steuerungs Einträge in der freigegebenen Zugriffs Steuerungs Liste (DACL) für die Ressource an. Die DACL-Liste wird durch den Besitzer der Ressource gesteuert.

Wenn Sie das Ergebnis als Liste ( `Get-Acl | Format-List` ), zusätzlich zum Pfad, Besitzer und der Zugriffsliste formatieren, zeigt PowerShell die folgenden Eigenschaften und Eigenschaftswerte an:

- **Gruppe** : die Sicherheitsgruppe des Besitzers.
- **Audit** : eine Liste (Array) der Einträge in der System-Zugriffs Steuerungs Liste (SACL). Die SACL gibt die Arten von Zugriffsversuchen an, für die Windows Überwachungsdatensätze generiert.
- **SDDL** : die Sicherheits Beschreibung der Ressource, die in einer einzelnen Text Zeichenfolge im Format der Sicherheits Deskriptor-Definitions Sprache angezeigt wird. PowerShell verwendet die **gezddlform** -Methode von Sicherheits Deskriptoren, um diese Daten zu erhalten.

Da `Get-Acl` von den Dateisystem-und Registrierungs Anbietern unterstützt wird, können Sie verwenden, `Get-Acl` um die ACL von Dateisystemobjekten, wie z. b. Dateien und Verzeichnissen, und Registrierungs Objekten, wie z. b. Registrierungsschlüssel und Einträge, anzuzeigen.

## VERWANDTE LINKS

[Set-Acl](Set-Acl.md)
