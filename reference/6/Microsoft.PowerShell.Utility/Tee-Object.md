---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/tee-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Tee-Object
ms.openlocfilehash: 1f892ece313ddc0074afbeaf3f3243c0bb9f31d0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216212"
---
# Tee-Object

## ZUSAMMENFASSUNG
Speichert die Ausgabe des Befehls in einer Datei oder einer Variablen, und sendet sie über die Pipeline.

## SYNTAX

### File (Standard)

```
Tee-Object [-InputObject <PSObject>] [-FilePath] <String> [-Append] [<CommonParameters>]
```

### Literalfile

```
Tee-Object [-InputObject <PSObject>] -LiteralPath <String> [<CommonParameters>]
```

### Variable

```
Tee-Object [-InputObject <PSObject>] -Variable <String> [<CommonParameters>]
```

## DESCRIPTION

Das `Tee-Object` Cmdlet leitet die Ausgabe um, d. h., es sendet die Ausgabe eines Befehls in zwei Richtungen (wie z. b. den Buchstaben T). Das Cmdlet speichert die Ausgabe in einer Datei oder einer Variablen und sendet sie über die Pipeline. Wenn `Tee-Object` der letzte Befehl in der Pipeline ist, wird die Befehlsausgabe an der Eingabeaufforderung angezeigt.

## BEISPIELE

### Beispiel 1: Ausgabeprozesse in einer Datei und an der Konsole

Dieses Beispiel ruft eine Liste der Prozesse ab, die auf dem Computer ausgeführt werden, und sendet das Ergebnis an eine Datei.
Da kein zweiter Pfad angegeben ist, werden die Prozesse auch in der Konsole angezeigt.

```powershell
Get-Process | Tee-Object -FilePath "C:\Test1\testfile2.txt"
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
83       4     2300       4520    39     0.30    4032 00THotkey
272      6     1400       3944    34     0.06    3088 alg
81       3      804       3284    21     2.45     148 ApntEx
81       4     2008       5808    38     0.75    3684 Apoint
...
```

### Beispiel 2: Ausgabeprozesse für eine Variable und `Select-Object`

Dieses Beispiel ruft eine Liste der Prozesse ab, die auf dem Computer ausgeführt werden, speichert Sie in der `$proc` Variablen und leitet Sie an weiter `Select-Object` .

```powershell
Get-Process notepad | Tee-Object -Variable proc | Select-Object processname,handles
```

```Output
ProcessName                              Handles
-----------                              -------
notepad                                  43
notepad                                  37
notepad                                  38
notepad                                  38
```

Mit dem `Select-Object` -Cmdlet werden die Eigenschaften **ProcessName** und **Handles** ausgewählt. Beachten Sie, dass die- `$proc` Variable die von zurückgegebenen Standardinformationen enthält `Get-Process` .

### Beispiel 3: Ausgabe von Systemdateien in zwei Protokolldateien

In diesem Beispiel wird eine Liste von Systemdateien in zwei Protokolldateien gespeichert, einer kumulativen Datei und einer aktuellen Datei.

```powershell
Get-ChildItem -Path D: -File -System -Recurse |
  Tee-Object -FilePath "c:\test\AllSystemFiles.txt" -Append |
    Out-File c:\test\NewSystemFiles.txt
```

Der Befehl verwendet das `Get-ChildItem` Cmdlet, um eine rekursive Suche nach Systemdateien auf dem Laufwerk "D:" durchzuführen. Ein Pipeline Operator (|) sendet die Liste an `Tee-Object` , die die Liste an die AllSystemFiles.txt Datei anfügt und die Liste über die Pipeline an das `Out-File` Cmdlet übergibt, das die Liste in der NewSystemFiles.txt Datei speichert.

## PARAMETERS

### -Anfügen

Gibt an, dass das Cmdlet die Ausgabe an die angegebene Datei anfügt. Ohne diesen Parameter ersetzt der neue Inhalt vorhandene Inhalte in der Datei ohne Warnung.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Gibt eine Datei an, die von diesem Cmdlet zum Speichern des Objekts in Platzhalter Zeichen zulässig ist, aber in eine einzelne Datei aufgelöst werden muss.

```yaml
Type: System.String
Parameter Sets: File
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

Gibt das zu speichernde und anzuzeigende Objekt an. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden. Sie können ein Objekt auch über die Pipeline an übergeben `Tee-Object` .

Wenn Sie den **Inputobject** -Parameter mit verwenden `Tee-Object` , anstatt Befehls Ergebnisse an zu übergeben `Tee-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt, auch wenn der Wert eine Auflistung ist.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Literalpath

Gibt eine Datei an, in der dieses Cmdlet das Objekt speichert. Im Gegensatz zu **FilePath** wird der Wert des **LiteralPath** -Parameters genau wie eingegeben verwendet. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String
Parameter Sets: LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Variable

Gibt eine Variable an, in der das Cmdlet das Objekt speichert. Geben Sie einen Variablennamen ohne das vorherige Dollarzeichen ( `$` ) ein.

```yaml
Type: System.String
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können Objekte über die Pipeline an übergeben `Tee-Object` .

## AUSGABEN

### System. Management. Automation. psobject

`Tee-Object` Gibt das-Objekt zurück, das es umleitet.

## HINWEISE

Sie können auch das `Out-File` Cmdlet oder den Umleitungs Operator verwenden, die beide die Ausgabe in einer Datei speichern, aber nicht über die Pipeline senden.

Ab PowerShell 6 `Tee-Object` verwendet die BOM-lose UTF-8-Codierung beim Schreiben in Dateien. Wenn Sie eine andere Codierung benötigen, verwenden Sie das- `Out-File` Cmdlet mit dem **Encoding** -Parameter.

## VERWANDTE LINKS

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)
