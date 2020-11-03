---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Alias
ms.openlocfilehash: 98f68cff8501fec375e3a2b8ac446e41d5721fc7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210711"
---
# Get-Alias

## ZUSAMMENFASSUNG
Ruft die Aliase für die aktuelle Sitzung ab.

## SYNTAX

### Standard (Standard)

```
Get-Alias [[-Name] <String[]>] [-Exclude <String[]>] [-Scope <String>] [<CommonParameters>]
```

### Definition

```
Get-Alias [-Exclude <String[]>] [-Scope <String>] [-Definition <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das **Get-Alias-** Cmdlet ruft die Aliase in der aktuellen Sitzung ab.
Dies umfasst integrierte Aliase, Aliase, die Sie festgelegt oder importiert haben, und Aliase, die Sie Ihrem PowerShell-Profil hinzugefügt haben.

Standardmäßig nimmt **Get-Alias** einen Alias an und gibt den Befehlsnamen zurück.
Wenn Sie den *Definition* -Parameter verwenden, nimmt **Get-Alias** einen Befehlsnamen an und gibt dessen Aliase zurück.

Ab Windows PowerShell 3,0 zeigt **Get-Alias** nicht-hyphenated-Alias Namen in einem `<alias> -> <definition>` Format an, um die Suche nach benötigten Informationen noch einfacher zu gestalten.

## BEISPIELE

### Beispiel 1: alle Aliase in der aktuellen Sitzung erhalten

```
PS C:\> Get-Alias

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           asnp -> Add-PSSnapin
Alias           cat -> Get-Content
Alias           cd -> Set-Location
Alias           chdir -> Set-Location
Alias           clc -> Clear-Content
Alias           clear -> Clear-Host
Alias           clhy -> Clear-History
...
```

Dieser Befehl ruft alle Aliase in der aktuellen Sitzung ab.

Die Ausgabe zeigt das `<alias> -> <definition>` Format an, das in Windows PowerShell 3,0 eingeführt wurde.
Dieses Format wird nur für Aliase verwendet, die keine Bindestriche enthalten, weil Aliase mit Bindestrichen in der Regel bevorzugte Namen für Cmdlets und Funktionen und keine Spitznamen sind.

### Beispiel 2: erhalten von Aliasen nach Namen

```powershell
Get-Alias -Name gp*, sp* -Exclude *ps
```

Dieser Befehl ruft alle Aliase ab, die mit GP oder SP beginnen, mit Ausnahme der Aliase, die mit PS enden.

### Beispiel 3: erhalten von Aliasen für ein Cmdlet

```powershell
Get-Alias -Definition Get-ChildItem
```

Dieser Befehl ruft die Aliase für das Get-ChildItem-Cmdlet ab.

Standardmäßig ruft das **Get-Alias-** Cmdlet den Elementnamen ab, wenn Sie den Alias kennen.
Der *Definition* -Parameter ruft den Alias ab, wenn Sie den Elementnamen kennen.

### Beispiel 4: erhalten von Aliasen nach Eigenschaft

```powershell
Get-Alias | Where-Object {$_.Options -Match "ReadOnly"}
```

Dieser Befehl ruft alle Aliase ab, in denen der Wert der Options-Eigenschaft schreibgeschützt ist.
Dieser Befehl bietet eine schnelle Möglichkeit, die in PowerShell integrierten Aliase zu finden, da Sie über die Option "schreibgeschützt" verfügen.

"Options" ist nur eine Eigenschaft der AliasInfo-Objekte, die von **Get-Alias abgerufen werden** .
Um alle Eigenschaften und Methoden von AliasInfo-Objekten zu suchen, geben Sie ein `Get-Alias | get-member` .

### Beispiel 5: erhalten von Aliasen nach Name und Filtern nach dem Anfangsbuchstaben

```powershell
Get-Alias -Definition "*-PSSession" -Exclude e* -Scope Global
```

In diesem Beispiel werden Aliase für Befehle abgerufen, deren Namen mit „-PSSession“ enden, mit Ausnahme der Aliase, die mit „e“ beginnen.

Der Befehl verwendet den *Scope* -Parameter, um den Befehl im globalen Gültigkeitsbereich anzuwenden.
Dies empfiehlt sich in Skripts, wenn Sie die Aliase in der Sitzung abrufen möchten.

## PARAMETERS

### -Definition

Ruft die Aliase für das angegebene Element ab.
Geben Sie den Namen eines Cmdlets, einer Funktion, eines Skripts, einer Datei oder einer ausführbaren Datei ein.

Dieser Parameter wird als " *Definition* " bezeichnet, da er in der Definition-Eigenschaft des Alias Objekts nach dem Elementnamen sucht.

```yaml
Type: System.String[]
Parameter Sets: Definition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Ausschließen

Lässt die angegebenen Elemente aus.
Der Wert dieses Parameters qualifiziert die Name- und Definition-Parameter.
Geben Sie einen Namen, eine Definition oder ein Muster wie z. B. „s*“ ein.
Platzhalter sind zulässig.

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

### -Name

Gibt die Aliase an, die dieses Cmdlet abruft.
Platzhalter sind zulässig.
Standardmäßig `Get-Alias` Ruft alle Aliase ab, die für die aktuelle Sitzung definiert sind.
Der Parameter Name **Name** ist optional.
Sie können Aliasnamen auch über die Pipeline an senden `Get-Alias` .

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: All aliases
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Bereich

Gibt den Bereich an, für den dieses Cmdlet Aliase abrufen soll.
Zulässige Werte für diesen Parameter:

- Global
- Lokal
- Skript
- Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)

Local ist die Standardeinstellung.
Weitere Informationen finden Sie unter „about_Scopes“.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können Aliasnamen an **Get-Alias** übergeben.

## AUSGABEN

### System. Management. Automation. AliasInfo

**Get-Alias** gibt ein Objekt zurück, das jeden Alias darstellt.
**Get-Alias** gibt das gleiche Objekt für jeden Alias zurück, aber PowerShell verwendet ein Pfeil basiertes Format, um die Namen der nicht-Bindestriche anzuzeigen.

## HINWEISE

- Um einen neuen Alias zu erstellen, verwenden Sie Set-Alias oder New-Alias. Verwenden Sie zum Löschen eines Alias Remove-Item.
- Das pfeilbasierte Aliasnamensformat wird nicht für Aliase verwendet, die einen Bindestrich enthalten. Dabei handelt es sich wahrscheinlich um bevorzugte Ersatznamen für Cmdlets und Funktionen anstelle der üblichen Abkürzungen und Spitznamen.

## VERWANDTE LINKS

[Export-Alias](Export-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Set-Alias](Set-Alias.md)

[Aliasanbieter](../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)
