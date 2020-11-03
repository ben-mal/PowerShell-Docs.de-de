---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalUser
ms.openlocfilehash: d83f3ad12481df0849ff2fe3f61d553a9ffdcdde
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214671"
---
# New-LocalUser

## ZUSAMMENFASSUNG

Erstellt ein lokales Benutzerkonto.

## SYNTAX

### Kennwort (Standard)

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> -Password <SecureString> [-PasswordNeverExpires]
 [-UserMayNotChangePassword] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nopassword

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> [-NoPassword] [-UserMayNotChangePassword] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `New-LocalUser` Cmdlet wird ein lokales Benutzerkonto erstellt. Dieses Cmdlet erstellt ein lokales Benutzerkonto oder ein lokales Benutzerkonto, das mit einem Microsoft-Konto verbunden ist.

> [!NOTE]
> Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.

## BEISPIELE

### Beispiel 1: Erstellen eines Benutzerkontos

```
PS C:\> New-LocalUser -Name "User02" -Description "Description of this account." -NoPassword
Name    Enabled  Description
----    -------  -----------
User02  True     Description of this account.
```

Mit diesem Befehl wird ein lokales Benutzerkonto erstellt, und die Parameter " **AccountExpires** " oder " **Password** " werden nicht angegeben. Daher läuft das Konto nicht ab oder hat standardmäßig ein Kennwort.

### Beispiel 2: Erstellen eines Benutzerkontos mit einem Kennwort

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."
Name    Enabled  Description
----    -------  -----------
User03  True     Description of this account.
```

Der erste Befehl fordert Sie mithilfe des-Cmdlets zur Eingabe eines Kennworts auf `Read-Host` . Der Befehl speichert das Kennwort als sichere Zeichenfolge in der `$Password` Variablen.

Mit dem zweiten Befehl wird ein lokales Benutzerkonto mit dem in gespeicherten Kennwort erstellt `$Password` . Der Befehl gibt einen Benutzernamen, einen vollständigen Namen und eine Beschreibung für das Benutzerkonto an.

## PARAMETERS

### -AccountExpires

Gibt an, wann das Benutzerkonto abläuft. Verwenden Sie zum Abrufen eines **DateTime** -Objekts das- `Get-Date` Cmdlet.
Wenn Sie diesen Parameter nicht angeben, läuft das Konto nicht ab.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Accountneverabläuft

Gibt an, dass das Konto nicht abläuft.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description

Gibt einen Kommentar für das Benutzerkonto an.
Die maximale Länge beträgt 48 Zeichen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Deaktiviert

Gibt an, dass dieses Cmdlet das Benutzerkonto als deaktiviert erstellt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FullName

Gibt den vollständigen Namen des Benutzerkontos an. Der vollständige Name unterscheidet sich vom Benutzernamen des Benutzerkontos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt den Benutzernamen für das Benutzerkonto an.

Wenn Sie ein lokales Benutzerkonto für das lokale System erstellen, kann der Benutzername bis zu 20 Groß-oder Kleinbuchstaben enthalten. Ein Benutzername darf nicht die folgenden Zeichen enthalten:

`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`

Ein Benutzername darf nicht ausschließlich aus Punkten `.` oder Leerzeichen bestehen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Nopassword

Gibt an, dass das Benutzerkonto nicht über ein Kennwort verfügt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoPassword
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password

Gibt ein Kennwort für das Benutzerkonto an. Sie können `Read-Host -GetCredential` , oder verwenden, `Get-Credential` `ConvertTo-SecureString` um ein **SecureString** -Objekt für das Kennwort zu erstellen.

Wenn Sie die Parameter " **Password** " und " **nopassword** " weglassen, werden `New-LocalUser` Sie von aufgefordert, das Kennwort des neuen Benutzers einzugeben.

```yaml
Type: System.Security.SecureString
Parameter Sets: Password
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passwordneverabläuft

Gibt an, ob das Kennwort abläuft.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Password
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usermaynotchangepassword

Gibt an, dass der Benutzer das Kennwort für das Benutzerkonto nicht ändern kann.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

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

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System. String, System. DateTime, System. Boolean, System. Security. SecureString

Sie können eine Zeichenfolge, ein **DateTime** -Objekt, einen booleschen Wert oder eine sichere Zeichenfolge an dieses Cmdlet übergeben.

## AUSGABEN

### System. Management. Automation. securityaccounungmanager. LocalUser

Dieses Cmdlet gibt ein **LocalUser** -Objekt zurück.
Dieses Objekt stellt Informationen zum Benutzerkonto bereit.

## HINWEISE

- Ein Benutzername darf nicht mit einem anderen Benutzernamen oder Gruppennamen auf dem Computer identisch sein. Ein Benutzername darf nicht ausschließlich aus Punkten `.` oder Leerzeichen bestehen. Ein Benutzername kann bis zu 20 Groß-oder Kleinbuchstaben enthalten. Ein Benutzername darf nicht die folgenden Zeichen enthalten:

`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`

- Ein Kennwort kann bis zu 127 Zeichen enthalten.
- Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben. Folgende Quellen sind möglich:

  - Lokal
  - Active Directory
  - Azure Active Directory-Gruppe
  - Microsoft-Konto

> [!NOTE]
> **Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt. Bei früheren Versionen ist die-Eigenschaft leer.

## VERWANDTE LINKS

[Disable-LocalUser](Disable-LocalUser.md)

[Enable-LocalUser](Enable-LocalUser.md)

[Get-LocalUser](Get-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
