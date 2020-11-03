---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 2/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: 791b500660ed536eb1bd7ba4d6f37e8211078a0c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216279"
---
# Set-Alias

## ZUSAMMENFASSUNG
Erstellt oder ändert einen Alias für ein Cmdlet oder einen anderen Befehl in der aktuellen PowerShell-Sitzung.

## SYNTAX

### Standard (Standard)

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Set-Alias` Cmdlet erstellt oder ändert einen Alias für ein Cmdlet oder einen Befehl, z. b. eine Funktion, ein Skript, eine Datei oder eine andere ausführbare Datei. Ein Alias ist ein alternativer Name, der auf ein Cmdlet oder einen Befehl verweist.
Beispielsweise `sal` ist der Alias für das `Set-Alias` Cmdlet. Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Ein Cmdlet kann über mehrere Aliase verfügen, aber ein Alias kann nur einem Cmdlet zugeordnet werden. Sie können verwenden, `Set-Alias` um einen vorhandenen Alias einem anderen Cmdlet zuzuweisen oder um die Eigenschaften eines Alias, z. b. die Beschreibung, zu ändern.

Ein Alias, der von erstellt oder geändert wird, `Set-Alias` ist nicht permanent und ist nur während der aktuellen PowerShell-Sitzung verfügbar. Wenn die PowerShell-Sitzung geschlossen ist, wird der Alias entfernt.

## BEISPIELE

### Beispiel 1: Erstellen eines Alias für ein Cmdlet

Dieser Befehl erstellt einen Alias für ein Cmdlet in der aktuellen PowerShell-Sitzung.

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt. Der **Name** -Parameter gibt den Aliasnamen an `list` . Der **value** -Parameter gibt das Cmdlet an, das der Alias ausführt.

Um den Alias auszuführen, geben Sie `list` in der PowerShell-Befehlszeile ein.

### Beispiel 2: Neuzuweisen eines vorhandenen Alias zu einem anderen Cmdlet

Mit diesem Befehl wird ein vorhandener Alias neu zugewiesen, um ein anderes Cmdlet auszuführen.

```
PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem

PS> Set-Alias -Name list -Value Get-Location

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-Location
```

Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzuzeigen. Der `list` Alias ist dem- `Get-ChildItem` Cmdlet zugeordnet. Wenn der `list` Alias ausgeführt wird, werden die Elemente im aktuellen Verzeichnis angezeigt.

Das `Set-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzugeben. Mit dem **value** -Parameter wird der Alias dem `Get-Location` Cmdlet zugeordnet.

Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um den `list` Alias anzuzeigen. Der `list` Alias ist dem- `Get-Location` Cmdlet zugeordnet. Wenn der `list` Alias ausgeführt wird, wird der Speicherort des aktuellen Verzeichnisses angezeigt.

### Beispiel 3: Erstellen und Ändern eines schreibgeschützten Alias

Dieser Befehl erstellt einen schreibgeschützten Alias. Die Option "schreibgeschützt" verhindert unbeabsichtigte Änderungen an einem Alias. Verwenden Sie den **Force** -Parameter, um einen schreibgeschützten Alias zu ändern oder zu löschen.

```
PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         :
Name                : loc
CommandType         : Alias

PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -Description 'Displays the current directory' -Force -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         : Displays the current directory
Name                : loc
CommandType         : Alias
```

Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt. Der **Name** -Parameter gibt den Aliasnamen an `loc` . Der **value** -Parameter gibt das `Get-Location` Cmdlet an, das der Alias ausführt. Der **Option** -Parameter gibt den Schreib **geschützten Wert an** . Der **passthru** -Parameter stellt das Alias Objekt dar und sendet das Objekt über die Pipeline an das `Format-List` Cmdlet. `Format-List` verwendet den **Property** -Parameter mit einem Sternchen ( `*` ), sodass alle Eigenschaften angezeigt werden. Die Beispielausgabe zeigt eine partielle Liste dieser Eigenschaften.

Der `loc` Alias wird durch das Hinzufügen von zwei Parametern geändert. **Beschreibung** fügt Text hinzu, um den Zweck des Alias zu erläutern. Der **Force** -Parameter ist erforderlich, da der Alias schreibgeschützt `loc` ist. Wenn der **Force** -Parameter nicht verwendet wird, schlägt die Änderung fehl.

### Beispiel 4: Erstellen eines Alias für eine ausführbare Datei

In diesem Beispiel wird ein Alias für eine ausführbare Datei auf dem lokalen Computer erstellt.

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

Mit dem- `Set-Alias` Cmdlet wird ein Alias in der aktuellen PowerShell-Sitzung erstellt. Der **Name** -Parameter gibt den Aliasnamen an `np` . Der **value** -Parameter gibt den Pfad und den Anwendungsnamen **C:\Windows\notepad.exe** an. Das `Get-Alias` Cmdlet verwendet den **Name** -Parameter, um anzuzeigen, dass der `np` Alias **notepad.exe** zugeordnet ist.

Um den Alias auszuführen, geben Sie in `np` der PowerShell-Befehlszeile ein, um **notepad.exe** zu öffnen.

### Beispiel 5: Erstellen eines Alias für einen Befehl mit Parametern

In diesem Beispiel wird gezeigt, wie ein Alias einem Befehl mit Parametern zugewiesen wird.

Sie können einen Alias für ein Cmdlet erstellen, z `Set-Location` . b.. Sie können keinen Alias für einen Befehl mit Parametern und Werten erstellen, z `Set-Location -Path C:\Windows\System32` . b.. Um einen Alias für einen Befehl zu erstellen, erstellen Sie eine Funktion, die den Befehl enthält, und erstellen dann einen Alias für die Funktion. Weitere Informationen finden Sie unter [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).

```
PS> Function CD32 {Set-Location -Path C:\Windows\System32}

PS> Set-Alias -Name Go -Value CD32
```

Es wird eine Funktion mit dem Namen `CD32` erstellt. Die-Funktion verwendet das- `Set-Location` Cmdlet mit dem **path** -Parameter, um das Verzeichnis anzugeben, **c:\Windows\System32** .

Mit dem- `Set-Alias` Cmdlet wird ein Alias für die-Funktion in der aktuellen PowerShell-Sitzung erstellt. Der **Name** -Parameter gibt den Aliasnamen an `Go` . Der **value** -Parameter gibt den Namen der Funktion an `CD32` .

Um den Alias auszuführen, geben Sie `Go` in der PowerShell-Befehlszeile ein. Die `CD32` Funktion wird ausgeführt und wechselt zum Verzeichnis **c:\Windows\System32** .

## PARAMETERS

### -Description

Gibt eine Beschreibung des Alias an. Sie können eine beliebige Zeichenfolge eingeben. Wenn die Beschreibung Leerzeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.

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

### -Force

Verwenden Sie den **Force** -Parameter, um einen Alias zu ändern oder zu löschen, für den der **Option** - **Parameter auf "** schreibgeschützt" fest

Der **Force** -Parameter kann einen Alias nicht ändern oder löschen, wenn der **Option** -Parameter auf **Constant** festgelegt ist.

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

### -Name

Gibt den Namen eines neuen Alias an. Ein Alias Name kann alphanumerische Zeichen und Bindestriche enthalten. Alias Namen dürfen nicht numerisch sein, z. b. 123.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Option

Legt den Wert der **Option** -Eigenschaft des Alias fest. Werte wie "schreibgeschützt **" und "** **Constant** " schützen einen Alias vor unbeabsichtigten Änderungen. Um die **options** -Eigenschaft aller Aliase in der Sitzung anzuzeigen, geben Sie ein `Get-Alias | Format-Table -Property Name, Options -Autosize` .

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- **Allscope** Der Alias wird in neue Bereiche kopiert, die erstellt werden.
- **Konstante** Kann nicht geändert oder gelöscht werden.
- **Keine** Legt keine Optionen fest und ist die Standardeinstellung.
- **Privat** Der Alias ist nur im aktuellen Bereich verfügbar.
- **ReadOnly** Schreibgeschützt Kann nicht geändert oder gelöscht werden, es sei denn, der **Force** -Parameter wird verwendet.
- **Nicht angegeben**

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: AllScope, Constant, None, Private, ReadOnly, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das den Alias darstellt. Verwenden Sie ein Format-Cmdlet `Format-List` , z. b., um das Objekt anzuzeigen. Standardmäßig `Set-Alias` generiert keine Ausgabe.

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

### -Bereich

Gibt den Bereich an, in dem dieser Alias gültig ist. Der Standardwert ist **local** . Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

Die zulässigen Werte lauten wie folgt:

- Global
- Lokal
- Private
- Nummerierte Bereiche
- Skript

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Global, Local, Private, Numbered scopes, Script

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Gibt den Namen des Cmdlets oder des Befehls an, den der Alias ausführt. Der **value** -Parameter ist die **Definition** -Eigenschaft des Alias.

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

### Keine

`Set-Alias` akzeptiert keine Eingaben aus der Pipeline.

## AUSGABEN

### None oder System. Management. Automation. AliasInfo

Wenn Sie den **passthru** -Parameter verwenden, `Set-Alias` generiert ein **System. Management. Automation. AliasInfo** -Objekt, das den Alias darstellt. Andernfalls `Set-Alias` generiert keine Ausgabe.

## HINWEISE

PowerShell umfasst integrierte Aliase, die in jeder PowerShell-Sitzung verfügbar sind. Das- `Get-Alias` Cmdlet zeigt die Aliase an, die in einer PowerShell-Sitzung verfügbar sind.

Um einen Alias zu erstellen, verwenden Sie die-Cmdlets `Set-Alias` oder `New-Alias` . Verwenden Sie das Cmdlet in PowerShell 6, um einen Alias zu löschen `Remove-Alias` . `Remove-Item` wird aus Gründen der Abwärtskompatibilität akzeptiert, z.b. für Skripts, die mit früheren Versionen von PowerShell erstellt wurden. Verwenden Sie einen Befehl wie z `Remove-Item -Path Alias:aliasname` . b..

Um einen Alias zu erstellen, der in jeder PowerShell-Sitzung verfügbar ist, fügen Sie ihn zu Ihrem PowerShell-Profil hinzu.
Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

Ein Alias kann mithilfe eines Exports und Imports in einer anderen PowerShell-Sitzung gespeichert und wieder verwendet werden. Um einen Alias in einer Datei zu speichern, verwenden Sie `Export-Alias` . Zum Hinzufügen eines gespeicherten Alias zu einer neuen PowerShell-Sitzung verwenden Sie `Import-Alias` .

## VERWANDTE LINKS

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md)

[about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Remove-Alias](Remove-Alias.md)

[Remove-Item](../Microsoft.PowerShell.Management/Remove-Item.md)
