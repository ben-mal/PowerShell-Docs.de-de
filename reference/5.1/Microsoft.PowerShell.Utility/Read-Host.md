---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/18/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 7f8c8a71657d1d00beb4c6e22159fb2b4ad5dce4
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "104726365"
---
# Read-Host

## ZUSAMMENFASSUNG
Liest eine Zeile von Eingabedaten aus der Konsole.

## SYNTAX

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## DESCRIPTION

Das- `Read-Host` Cmdlet liest eine Zeile der Eingabe aus der Konsole (stdin). Damit kann ein Benutzer zur Eingabe aufgefordert werden. Da Sie die Eingabe als sichere Zeichenfolge speichern können, können Sie dieses Cmdlet verwenden, um Benutzer zur Eingabe von sicheren Daten, z. b. Kenn Wörtern, aufzufordern.

> [!NOTE]
> `Read-Host` hat ein Limit von 8190 Zeichen, das als Eingabe eines Benutzers akzeptiert werden kann.

## BEISPIELE

### Beispiel 1: Speichern der Konsolen Eingabe in einer Variablen

In diesem Beispiel wird die Zeichenfolge "Bitte geben Sie Ihr Alter:" als Eingabeaufforderung angezeigt. Wenn ein Wert eingegeben und die EINGABETASTE gedrückt wird, wird der Wert in der Variablen gespeichert `$Age` .

```powershell
$Age = Read-Host "Please enter your age"
```

### Beispiel 2: Speichern der Konsolen Eingabe als sichere Zeichenfolge

In diesem Beispiel wird die Zeichenfolge "Enter a password:" als Eingabeaufforderung angezeigt. Wenn ein Wert eingegeben wird, werden `*` in der Konsole Sternchen () anstelle der Eingabe angezeigt. Wenn die EINGABETASTE gedrückt wird, wird der Wert als **SecureString** -Objekt in der `$pwd_secure_string` Variablen gespeichert.

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## PARAMETERS

### -Assecurestring

Gibt an, dass das Cmdlet Sternchen ( `*` ) anstelle der Zeichen anzeigt, die vom Benutzer als Eingabe eingegeben werden. Wenn Sie diesen Parameter verwenden, ist die Ausgabe des `Read-Host` Cmdlets ein **SecureString** -Objekt (**System. Security. SecureString**).

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

### -Eingabeaufforderung

Gibt den Text der Eingabeaufforderung an. Geben Sie eine Zeichenfolge ein. Wenn die Zeichenfolge Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen. PowerShell fügt einen Doppelpunkt ( `:` ) an den eingegebenen Text an.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Dieses Cmdlet akzeptiert keine Eingaben aus der PowerShell-Pipeline.

## AUSGABEN

### System. String oder System. Security. SecureString

Wenn der **assecurestring** -Parameter verwendet wird, `Read-Host` gibt eine **SecureString** zurück. Andernfalls wird eine Zeichenfolge zurückgegeben.

## HINWEISE

Dieses Cmdlet liest nur aus dem stdin-Stream des Host Prozesses. Normalerweise ist der stdin-Stream mit der Tastatur der Host Konsole verbunden.

## VERWANDTE LINKS

[Clear-Host](../microsoft.powershell.core/clear-host.md)

[Get-Host](Get-Host.md)

[Write-Host](Write-Host.md)

[ConvertFrom-SecureString](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
