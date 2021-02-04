---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: 9ffe7510745e92c6863cf08d143f89e214ae9133
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692974"
---
# Clear-Content

## ZUSAMMENFASSUNG
Löscht den Inhalt eines Elements, jedoch nicht das Element selbst.

## SYNTAX

### Pfad (Standard)

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

### LiteralPath

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Clear-Content` Cmdlet löscht den Inhalt eines Elements, z. b. das Löschen des Texts aus einer Datei, aber das Element wird nicht gelöscht.
Folglich ist das Element vorhanden, aber leer.
Der `Clear-Content` ähnelt `Clear-Item` , funktioniert jedoch für Elemente mit Inhalt anstelle von Elementen mit Werten.

## BEISPIELE

### Beispiel 1: Löschen aller Inhalte aus einem Verzeichnis

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

Mit diesem Befehl wird der gesamte Inhalt aus den Dateien mit dem Namen %%amp;quot;init.txt%%amp;quot; in allen Unterverzeichnissen des Verzeichnisses %%amp;quot;SmpUsers%%amp;quot; gelöscht.
Die Dateien werden nicht gelöscht, sie sind anschließend jedoch leer.

### Beispiel 2: Löschen des Inhalts aller Dateien mit einem Platzhalter

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

Mit diesem Befehl wird der Inhalt aller Dateien mit der Dateinamenerweiterung %%amp;quot;.log%%amp;quot; im aktuellen Verzeichnis gelöscht, einschließlich der Dateien mit Schreibschutzattribut. Das Sternchen ( \* ) im Pfad stellt alle Elemente im aktuellen Verzeichnis dar. Der **Force** -Parameter bewirkt, dass der Befehl für schreibgeschützte Dateien wirksam wird. Wenn Sie einen Filter verwenden, um den Befehl auf Dateien mit der Dateinamenerweiterung ". log" zu beschränken, anstatt " \* . log" im Pfad anzugeben, wird der Vorgang beschleunigt.

### Beispiel 3: Löschen aller Daten aus einem Stream

Dieses Beispiel zeigt, wie das `Clear-Content` Cmdlet den Inhalt aus einem alternativen Datenstrom löscht, während der Stream unverändert bleibt.

Der erste Befehl verwendet das `Get-Content` Cmdlet, um den Inhalt des `Zone.Identifier` Streams in der Copy-Script.ps1-Datei, die aus dem Internet heruntergeladen wurde, zu erhalten.

Der zweite Befehl verwendet das `Clear-Content` Cmdlet, um den Inhalt zu löschen.

Mit dem dritten Befehl wird der erste Befehl wiederholt. Es überprüft, ob der Inhalt gelöscht wurde, der Stream bleibt jedoch erhalten. Wenn der Stream gelöscht wurde, generiert der Befehl einen Fehler.

Sie können eine Methode wie diese verwenden, um den Inhalt eines alternativen Datenstroms zu löschen. Es ist jedoch nicht die empfohlene Methode, Sicherheitsüberprüfungen zu deaktivieren, die Dateien blockieren, die aus dem Internet heruntergeladen werden. Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.

```
PS C:\> Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

[ZoneTransfer]
ZoneId=3

PS C:\>Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

PS C:\>Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
PS C:\>
```

## PARAMETERS

### -Stream

> [!NOTE]
> Dieser Parameter ist nur unter Windows verfügbar.

Gibt einen alternativen Datenstrom für den Inhalt an. Wenn der Datenstrom nicht vorhanden ist, wird er von diesem Cmdlet erstellt. Platzhalterzeichen werden nicht unterstützt.

Stream ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Clear-Content` .
Dieser Parameter funktioniert nur in Dateisystemlaufwerken.

Sie können das `Clear-Content` Cmdlet verwenden, um den Inhalt des beliebigen Alternativen Datenstroms zu ändern, z `Zone.Identifier` . b.. Dies wird jedoch nicht empfohlen, um Sicherheitsüberprüfungen zu vermeiden, die Dateien blockieren, die aus dem Internet heruntergeladen werden. Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.

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

### -Credential

> [!NOTE]
> Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt. Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start-Command".

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

Gibt Zeichen folgen, die von diesem Cmdlet aus dem Pfad zum Inhalt ausgelassen werden, als Zeichen folgen Array an. Der Wert dieses Parameters qualifiziert den **Path**-Parameter. Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;*.txt%%amp;quot; ein. Platzhalter sind zulässig.

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

Gibt einen Filter im Format oder in der Sprache des Anbieters an. Der Wert dieses Parameters qualifiziert den **Path**-Parameter. Die Syntax des Filters einschließlich der Verwendung von Platzhaltern ist vom Anbieter abhängig. Filter sind effizienter als andere Parameter, da Sie vom Anbieter beim Abrufen der Objekte angewendet werden, anstatt dass PowerShell die Objekte nach dem Abrufen filtert.

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

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

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

Gibt den Inhalt, den dieses Cmdlet löscht, als Zeichen folgen Array an. Der Wert dieses Parameters qualifiziert den **Path**-Parameter. Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;*.txt%%amp;quot; ein. Platzhalter sind zulässig.

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

Gibt die Pfade zu den Elementen an, aus denen der Inhalt gelöscht wird. Im Gegensatz zum **Path**-Parameter wird der Wert des **LiteralPath**-Parameters genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert.
Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen geben an, dass PowerShell Zeichen nicht als Escapesequenzen interpretieren soll.

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

Gibt die Pfade zu den Elementen an, aus denen der Inhalt gelöscht wird. Platzhalter sind zulässig. Die Pfade müssen auf Elemente und nicht auf Container zeigen. Sie müssen beispielsweise einen Pfad zu Dateien angeben, ein Pfad zu einem Verzeichnis ist nicht zulässig. Platzhalter sind zulässig. Dieser Parameter ist erforderlich, der Parametername (Path) ist jedoch optional.

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

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).


## EINGABEN

### Keine

Objekte können nicht an übergeben werden `Clear-Content` .

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Objekte zurück.

## HINWEISE

Sie können `Clear-Content` mit dem PowerShell-File System-Anbieter und mit anderen Anbietern verwenden, die den Inhalt bearbeiten. Verwenden Sie, um Elemente zu löschen, die nicht als Inhalt angesehen werden, z. b. Elemente, die vom PowerShell-Zertifikat oder von Registrierungs Anbietern verwaltet werden `Clear-Item` .

Das- `Clear-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.
Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .
Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Add-Content](Add-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[Set-Content](Set-Content.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
