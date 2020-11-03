---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 07/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertfrom-securestring?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SecureString
ms.openlocfilehash: 4bbdab62168a7306bb02d0ac47b5513d23920814
ms.sourcegitcommit: b7ff031a12afd04910aeb98345ebee92f5845b0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "93219015"
---
# ConvertFrom-SecureString

## ZUSAMMENFASSUNG
Konvertiert eine sichere Zeichenfolge in eine verschlüsselte Standard Zeichenfolge.

## SYNTAX

### Sicher (Standard)

```
ConvertFrom-SecureString [-SecureString] <SecureString> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### AsPlainText

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-AsPlainText] [<CommonParameters>]
```

### Öffnen

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-Key <Byte[]>] [<CommonParameters>]
```

## DESCRIPTION

Das **ConvertFrom-SecureString-** Cmdlet konvertiert eine sichere Zeichenfolge ( **System. Security. SecureString** ) in eine verschlüsselte Standard Zeichenfolge ( **System. String** ). Im Gegensatz zu einer sicheren Zeichenfolge kann eine verschlüsselte Standardzeichenfolge zur späteren Verwendung in einer Datei gespeichert werden. Die verschlüsselte Standard Zeichenfolge kann mit dem-Cmdlet zurück in das sichere Zeichen folgen Format konvertiert werden `ConvertTo-SecureString` .

Wenn ein Verschlüsselungsschlüssel mithilfe des **Key** - oder **SecureKey** -Parameters angegeben wird, wird der AES (Advanced Encryption Standard)-Verschlüsselungsalgorithmus verwendet. Der angegebene Schlüssel muss eine Länge von 128, 192 oder 256 Bits haben, da dies die vom AES-Verschlüsselungsalgorithmus unterstützten Schlüssellängen sind. Wenn kein Schlüssel angegeben ist, wird Windows Data Protection API (DPAPI) zum Verschlüsseln der Standardzeichenfolgendarstellung verwendet.

> [!NOTE]
> Beachten Sie, dass die Inhalte von SecureString pro [dotnet](/dotnet/api/system.security.securestring?view=netcore-2.1#remarks)nicht auf nicht-Windows-Systemen verschlüsselt werden.

## BEISPIELE

### Beispiel 1: Erstellen einer sicheren Zeichenfolge

```powershell
$SecureString = Read-Host -AsSecureString
```

Dieser Befehl erstellt eine sichere Zeichenfolge aus Zeichen, die Sie an der Eingabeaufforderung eingeben. Geben Sie nach Eingabe des Befehls die Zeichenfolge ein, die Sie als sichere Zeichenfolge speichern möchten. Ein Sternchen ( `*` ) wird angezeigt, das die einzelnen Zeichen darstellt, die Sie eingeben.

### Beispiel 2: Konvertieren einer sicheren Zeichenfolge in eine verschlüsselte Standard Zeichenfolge

```powershell
$StandardString = ConvertFrom-SecureString $SecureString
```

Dieser Befehl konvertiert die sichere Zeichenfolge in der `$SecureString` Variablen in eine verschlüsselte Standard Zeichenfolge. Die resultierende verschlüsselte Standard Zeichenfolge wird in der `$StandardString` Variablen gespeichert.

### Beispiel 3: Konvertieren einer sicheren Zeichenfolge in eine verschlüsselte Standard Zeichenfolge mit einem 192-Bit-Schlüssel

```powershell
$Key = (3,4,2,3,56,34,254,222,1,1,2,23,42,54,33,233,1,34,2,7,6,5,35,43)
$StandardString = ConvertFrom-SecureString $SecureString -Key $Key
```

Diese Befehle verwenden den Advanced Encryption Standard (AES)-Algorithmus, um die in der Variablen gespeicherte sichere Zeichenfolge in eine `$SecureString` verschlüsselte Standard Zeichenfolge mit einem 192-Bit-Schlüssel zu konvertieren. Die resultierende verschlüsselte Standard Zeichenfolge wird in der `$StandardString` Variablen gespeichert.

Der erste Befehl speichert einen Schlüssel in der `$Key` Variablen. Der Schlüssel ist ein Array aus 24 Dezimalzahlen, von denen jede kleiner als 256 sein muss, damit Sie in ein einzelnes nicht signiertes Byte passt.

Da jede Dezimalzahl ein einzelnes Byte (8 Bits) darstellt, verfügt der Schlüssel über 24 Ziffern für insgesamt 192 Bits (8 x 24). Dies ist eine gültige Schlüssellänge für den AES-Algorithmus.

Der zweite Befehl verwendet den Schlüssel in der `$Key` Variablen, um die sichere Zeichenfolge in eine verschlüsselte Standard Zeichenfolge zu konvertieren.

### Beispiel 4: Konvertieren einer sicheren Zeichenfolge direkt in eine nur-Text-Zeichenfolge

```powershell
$secureString = ConvertTo-SecureString -String 'Example' -AsPlainText
$secureString # 'System.Security.SecureString'
ConvertFrom-SecureString -SecureString $secureString -AsPlainText # 'Example'
```

## PARAMETERS

### -Asplaintext

Wenn festgelegt, `ConvertFrom-SecureString` konvertiert sichere Zeichen folgen als Ausgabe in die entschlüsselte klar Text Zeichenfolge.

Dieser Parameter wurde in PowerShell 7,0 hinzugefügt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsPlainText
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Key

Gibt den Verschlüsselungsschlüssel als Bytearray an.

```yaml
Type: System.Byte[]
Parameter Sets: Open
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecureKey

Gibt den Verschlüsselungsschlüssel als sichere Zeichenfolge an. Der Wert der sicheren Zeichenfolge wird in ein Bytearray konvertiert, bevor er als Schlüssel verwendet wird.

```yaml
Type: System.Security.SecureString
Parameter Sets: Secure
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecureString

Gibt die sichere Zeichenfolge an, die in eine verschlüsselte Standardzeichenfolge konvertiert werden soll.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .
Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.Security.SecureString

Sie können ein **SecureString** -Objekt über die Pipeline an ConvertFrom-SecureString übergeben.

## AUSGABEN

### System.String

ConvertFrom-SecureString gibt ein Standardzeichenfolgenobjekt zurück.

## HINWEISE

- Verwenden Sie den **assecurestring** -Parameter des Cmdlets, um eine sichere Zeichenfolge aus Zeichen zu erstellen, die an der Eingabeaufforderung eingegeben werden `Read-Host` .
- Wenn Sie die **Schlüssel** -oder **SecureKey** -Parameter verwenden, um einen Schlüssel anzugeben, muss die Schlüssellänge korrekt sein. Beispielsweise kann ein Schlüssel von 128 Bits als Bytearray mit 16 Dezimalzahlen angegeben werden.
  Entsprechend entsprechen 192-Bit-und 256-Bit-Schlüssel Byte Arrays mit 24 und 32 Dezimalzahlen.
- Einige Zeichen, z. b. Emoticons, entsprechen mehreren Code Punkten in der Zeichenfolge, in der Sie enthalten sind. Vermeiden Sie die Verwendung dieser Zeichen, da Sie bei der Verwendung in einem Kennwort Probleme und Missverständnisse verursachen können.

## VERWANDTE LINKS

[ConvertTo-SecureString](ConvertTo-SecureString.md)

[Read-Host](../Microsoft.PowerShell.Utility/Read-Host.md)
