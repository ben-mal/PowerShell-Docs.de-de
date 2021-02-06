---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-SecureString
ms.openlocfilehash: 0f95f66bdd13fd57f71823f2d44a28a1323d0d15
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599429"
---
# ConvertTo-SecureString

## ZUSAMMENFASSUNG
Konvertiert nur-Text-oder verschlüsselte Zeichen folgen in sichere Zeichen folgen.

## SYNTAX

### Sicher (Standard)

```
ConvertTo-SecureString [-String] <String> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### PlainText

```
ConvertTo-SecureString [-String] <String> [-AsPlainText] [-Force] [<CommonParameters>]
```

### Öffnen

```
ConvertTo-SecureString [-String] <String> [-Key <Byte[]>] [<CommonParameters>]
```

## DESCRIPTION

Das- `ConvertTo-SecureString` Cmdlet konvertiert verschlüsselte Standard Zeichenfolgen in sichere Zeichen folgen. Es kann auch einfachen Text in sichere Zeichenfolgen konvertieren. Sie wird mit `ConvertFrom-SecureString` und verwendet `Read-Host` . Die vom Cmdlet erstellte sichere Zeichenfolge kann mit Cmdlets oder Funktionen verwendet werden, die einen Parameter vom Typ " **SecureString**" erfordern. Die sichere Zeichenfolge kann mithilfe des Cmdlets zurück in eine verschlüsselte Standard Zeichenfolge konvertiert werden `ConvertFrom-SecureString` . So kann sie für die spätere Verwendung in einer Datei gespeichert werden.

Wenn die zu konvertierende Standard Zeichenfolge `ConvertFrom-SecureString` mithilfe eines angegebenen Schlüssels verschlüsselt wurde, muss der gleiche Schlüssel als Wert des **Key** -oder **SecureKey** -Parameters des `ConvertTo-SecureString` Cmdlets angegeben werden.

> [!NOTE]
> Beachten Sie, dass die Inhalte von SecureString pro [dotnet](/dotnet/api/system.security.securestring#remarks)nicht auf nicht-Windows-Systemen verschlüsselt werden.

## BEISPIELE

### Beispiel 1: Konvertieren einer sicheren Zeichenfolge in eine verschlüsselte Zeichenfolge

In diesem Beispiel wird veranschaulicht, wie eine sichere Zeichenfolge aus der Benutzereingabe erstellt, die sichere Zeichenfolge in eine verschlüsselte Standardzeichenfolge konvertiert und dann die verschlüsselte Standardzeichenfolge wieder in eine sichere Zeichenfolge konvertiert wird.

```powershell
PS C:\> $Secure = Read-Host -AsSecureString
PS C:\> $Secure
System.Security.SecureString
PS C:\> $Encrypted = ConvertFrom-SecureString -SecureString $Secure
PS C:\> $Encrypted
01000000d08c9ddf0115d1118c7a00c04fc297eb010000001a114d45b8dd3f4aa11ad7c0abdae98000000000
02000000000003660000a8000000100000005df63cea84bfb7d70bd6842e7efa79820000000004800000a000
000010000000f10cd0f4a99a8d5814d94e0687d7430b100000008bf11f1960158405b2779613e9352c6d1400
0000e6b7bf46a9d485ff211b9b2a2df3bd6eb67aae41
PS C:\> $Secure2 = ConvertTo-SecureString -String $Encrypted
PS C:\> $Secure2
System.Security.SecureString
```

Der erste Befehl verwendet den **assecurestring** -Parameter des `Read-Host` Cmdlets, um eine sichere Zeichenfolge zu erstellen. Nachdem Sie den Befehl eingegeben haben, werden alle von Ihnen eingegebenen Zeichen in eine sichere Zeichenfolge konvertiert und anschließend in der `$Secure` Variablen gespeichert.

Der zweite Befehl zeigt den Inhalt der `$Secure` Variablen an. Da die `$Secure` Variable eine sichere Zeichenfolge enthält, zeigt PowerShell nur den **System. Security. SecureString** -Typ an.

Der dritte Befehl verwendet das `ConvertFrom-SecureString` Cmdlet, um die sichere Zeichenfolge in der `$Secure` Variablen in eine verschlüsselte Standard Zeichenfolge zu konvertieren. Das Ergebnis wird in der `$Encrypted` Variablen gespeichert.

Der vierte Befehl zeigt die verschlüsselte Zeichenfolge im Wert der `$Encrypted` Variablen an.

Der fünfte Befehl verwendet das `ConvertTo-SecureString` Cmdlet, um die verschlüsselte Standard Zeichenfolge in der `$Encrypted` Variablen zurück in eine sichere Zeichenfolge zu konvertieren. Das Ergebnis wird in der `$Secure2` Variablen gespeichert.
Der sechste Befehl zeigt den Wert der `$Secure2` Variablen an. Der SecureString-Typ gibt an, dass der Befehl erfolgreich ausgeführt wurde.

### Beispiel 2: Erstellen einer sicheren Zeichenfolge aus einer verschlüsselten Zeichenfolge in einer Datei

Dieses Beispiel zeigt, wie eine sichere Zeichenfolge aus einer verschlüsselten, in einer Datei gespeicherten Standardzeichenfolge erstellt wird.

```powershell
$Secure = Read-Host -AsSecureString
$Encrypted = ConvertFrom-SecureString -SecureString $Secure -Key (1..16)
$Encrypted | Set-Content Encrypted.txt
$Secure2 = Get-Content Encrypted.txt | ConvertTo-SecureString -Key (1..16)
```

Der erste Befehl verwendet den **assecurestring** -Parameter des `Read-Host` Cmdlets, um eine sichere Zeichenfolge zu erstellen. Nachdem Sie den Befehl eingegeben haben, werden alle von Ihnen eingegebenen Zeichen in eine sichere Zeichenfolge konvertiert und anschließend in der `$Secure` Variablen gespeichert.

Der zweite Befehl verwendet das `ConvertFrom-SecureString` Cmdlet, um die sichere Zeichenfolge in der `$Secure` Variablen mithilfe des angegebenen Schlüssels in eine verschlüsselte Standard Zeichenfolge zu konvertieren. Der Inhalt wird in der `$Encrypted` Variablen gespeichert.

Der dritte Befehl verwendet einen Pipeline Operator ( `|` ), um den Wert der `$Encrypted` Variablen an das `Set-Content` Cmdlet zu senden, das den Wert in der Encrypted.txt-Datei speichert.

Der vierte Befehl verwendet das `Get-Content` Cmdlet, um die verschlüsselte Standard Zeichenfolge in der Encrypted.txt-Datei zu erhalten. Der Befehl verwendet einen Pipeline Operator, um die verschlüsselte Zeichenfolge an das `ConvertTo-SecureString` Cmdlet zu senden, das Sie mit dem angegebenen Schlüssel in eine sichere Zeichenfolge konvertiert.
Die Ergebnisse werden in der `$Secure2` Variablen gespeichert.

### Beispiel 3: Konvertieren einer nur-Text-Zeichenfolge in eine sichere Zeichenfolge

Dieser Befehl konvertiert die nur-Text-Zeichenfolge in `P@ssW0rD!` eine sichere Zeichenfolge und speichert das Ergebnis in der `$Secure_String_Pwd` Variablen. Um den **asplaintext** -Parameter zu verwenden, muss der **Force** -Parameter auch im Befehl enthalten sein.

```powershell
$Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
```

> [!CAUTION]
> Vermeiden Sie die Verwendung von nur-Text-Zeichen folgen im Skript oder über die Befehlszeile. Der nur-Text kann in Ereignisprotokollen und Befehlsverlauf Protokollen angezeigt werden.

## PARAMETERS

### -Asplaintext

Gibt eine Nur-Text-Zeichenfolge an, die in eine sichere Zeichenfolge konvertiert werden soll. Cmdlets für sichere Zeichenfolgen tragen zum Schutz von vertraulichem Text bei. Der Text wird zu Datenschutzzwecken verschlüsselt und nach der Verwendung aus dem Computerspeicher gelöscht. Wenn Sie diesen Parameter für einfachen Text als Eingabe verwenden, kann nicht das System die Eingabe nicht auf diese Weise schützen. Um diesen Parameter zu verwenden, müssen Sie auch den **Force** -Parameter angeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Bestätigt, dass Sie die Auswirkungen der Verwendung des **asplaintext** -Parameters verstehen und dennoch verwenden möchten.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Key

Gibt den Verschlüsselungsschlüssel an, der zum Konvertieren der ursprünglichen sicheren Zeichenfolge in die verschlüsselte Standard Zeichenfolge verwendet wird. Gültige Schlüssellängen sind 16, 24 und 32 Bytes.

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

Gibt den Verschlüsselungsschlüssel an, der zum Konvertieren der ursprünglichen sicheren Zeichenfolge in die verschlüsselte Standard Zeichenfolge verwendet wird. Der Schlüssel muss im Format einer sicheren Zeichenfolge bereitgestellt werden. Die sichere Zeichenfolge wird in ein Bytearray konvertiert, das als Schlüssel verwendet werden soll. Gültige sichere Schlüssellängen sind 8, 12 und 16 Code Punkte.

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

### -Zeichenfolge

Gibt die Zeichenfolge an, die in eine sichere Zeichenfolge konvertiert werden soll.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine verschlüsselte Standard Zeichenfolge an übergeben `ConvertTo-SecureString` .

## AUSGABEN

### System.Security.SecureString

`ConvertTo-SecureString` Gibt ein **SecureString** -Objekt zurück.

## HINWEISE

Einige Zeichen, z. b. Emoticons, entsprechen mehreren Code Punkten in der Zeichenfolge, in der Sie enthalten sind. Vermeiden Sie die Verwendung dieser Zeichen, da Sie bei der Verwendung in einem Kennwort Probleme und Missverständnisse verursachen können.

## VERWANDTE LINKS

[ConvertFrom-SecureString](ConvertFrom-SecureString.md)

[Read-Host](../Microsoft.PowerShell.Utility/Read-Host.md)
