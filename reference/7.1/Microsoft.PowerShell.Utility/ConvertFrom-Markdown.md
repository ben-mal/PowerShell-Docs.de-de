---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: PowerShell, Cmdlet, markdown
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-markdown?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Markdown
ms.openlocfilehash: 9f070819491b87b02868dffdfbe25bf5d72ecab8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216956"
---
# ConvertFrom-Markdown

## ZUSAMMENFASSUNG
Konvertiert den Inhalt einer Zeichenfolge oder einer Datei in ein **markdowninfo** -Objekt.

## SYNTAX

### Pathparamset (Standard)

```
ConvertFrom-Markdown [-Path] <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### Literalparamset

```
ConvertFrom-Markdown -LiteralPath <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### Inputobjparamset

```
ConvertFrom-Markdown -InputObject <PSObject> [-AsVT100EncodedString] [<CommonParameters>]
```

## DESCRIPTION

Dieses Cmdlet konvertiert den angegebenen Inhalt in eine **markdowninfo** . Wenn ein Dateipfad für den **path** -Parameter angegeben wird, wird der Inhalt der Datei konvertiert. Das Ausgabe Objekt verfügt über drei Eigenschaften:

- Die **Token** -Eigenschaft verfügt über die abstrakte Syntax Struktur (AST) des konvertierten Objekts.
- Die **HTML** -Eigenschaft hat die HTML-Konvertierung der angegebenen Eingabe.
- Die **VT100EncodedString** -Eigenschaft hat die konvertierte Zeichenfolge mit ANSI (VT100)-Escapesequenzen, wenn der **AsVT100EncodedString** -Parameter angegeben wurde

Dieses Cmdlet wurde in PowerShell 6,1 eingeführt.

## BEISPIELE

### Beispiel 1: Konvertieren einer Datei mit markdown-Inhalt in HTML

```powershell
ConvertFrom-Markdown -Path .\README.md
```

Das **markdowninfo** -Objekt wird zurückgegeben. Die **Tokens** -Eigenschaft verfügt über die Ast des konvertierten Inhalts der `README.md` Datei. Die **HTML** -Eigenschaft verfügt über den HTML-konvertierten Inhalt der `README.md` Datei.

### Beispiel 2: Konvertieren einer Datei, die markdown-Inhalte enthält, in eine VT100-codierte Zeichenfolge

```powershell
ConvertFrom-Markdown -Path .\README.md -AsVT100EncodedString
```

Das **markdowninfo** -Objekt wird zurückgegeben. Die **Tokens** -Eigenschaft verfügt über die Ast des konvertierten Inhalts der `README.md` Datei. Die **VT100EncodedString** -Eigenschaft weist den VT100-codierten Zeichen folgen konvertierten Inhalt der `README.md` Datei auf.

### Beispiel 3: Konvertieren eines Eingabe Objekts mit markdown-Inhalt in eine VT100-codierte Zeichenfolge

```powershell
Get-Item .\README.md | ConvertFrom-Markdown -AsVT100EncodedString
```

Das **markdowninfo** -Objekt wird zurückgegeben. Das **FileInfo** -Objekt von `Get-Item` wird in eine VT100-codierte Zeichenfolge konvertiert. Die **Tokens** -Eigenschaft verfügt über die Ast des konvertierten Inhalts der `README.md` Datei. Die **VT100EncodedString** -Eigenschaft weist den VT100-codierten Zeichen folgen konvertierten Inhalt der `README.md` Datei auf.

### Beispiel 4: Konvertieren einer Zeichenfolge mit markdown-Inhalt in eine VT100-codierte Zeichenfolge

```powershell
"**Bold text**" | ConvertFrom-Markdown -AsVT100EncodedString
```

Das **markdowninfo** -Objekt wird zurückgegeben. Die angegebene Zeichenfolge `**Bold text**` wird in eine VT100-codierte Zeichenfolge konvertiert und ist in der **VT100EncodedString** -Eigenschaft verfügbar.

## PARAMETERS

### -AsVT100EncodedString

Gibt an, ob die Ausgabe als Zeichenfolge mit VT100-Escapecodes codiert werden soll.

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

### -InputObject

Gibt das zu konvertierende Objekt an. Wenn ein Objekt vom Typ " **System. String** " angegeben wird, wird die Zeichenfolge konvertiert. Wenn ein Objekt vom Typ **System. IO. FileInfo** angegeben wird, wird der Inhalt der durch das-Objekt angegebenen Datei konvertiert. Objekte eines beliebigen anderen Typs führen zu einem Fehler.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObjParamSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Literalpath

Gibt einen Pfad zu der Datei an, die konvertiert werden soll.

```yaml
Type: System.String[]
Parameter Sets: LiteralParamSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt einen Pfad zu der Datei an, die konvertiert werden soll.

```yaml
Type: System.String[]
Parameter Sets: PathParamSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

## AUSGABEN

### Microsoft. PowerShell. markdownrendering. markdowninfo

## HINWEISE

## VERWANDTE LINKS

[Markdownparser](https://github.com/lunet-io/markdig)

[ANSI-Escapecode](https://wikipedia.org/wiki/ANSI_escape_code)

