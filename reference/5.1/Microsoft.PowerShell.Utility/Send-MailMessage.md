---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: 915f0eb0e27bc753db0bd3a5dd4b77dbc24c3e1f
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2021
ms.locfileid: "106273998"
---
# Send-MailMessage

## Übersicht
Sendet eine E-Mail.

## Syntax

### All

```
Send-MailMessage [-To] <string[]> [-Subject] <string> [[-Body] <string>] [[-SmtpServer] <string>]
 -From <string> [-Attachments <string[]>] [-Bcc <string[]>] [-BodyAsHtml] [-Encoding <Encoding>]
 [-Cc <string[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 [-Priority <MailPriority>] [-Credential <pscredential>] [-UseSsl] [-Port <int>]
 [<CommonParameters>]
```

## BESCHREIBUNG

Das `Send-MailMessage` Cmdlet sendet eine e-Mail-Nachricht in PowerShell.

Sie müssen einen Simple Mail Transfer Protocol (SMTP)-Server angeben, oder der `Send-MailMessage` Befehl schlägt fehl. Verwenden Sie den **SmtpServer** -Parameter, oder legen `$PSEmailServer` Sie die Variable auf einen gültigen SMTP-Server fest.
Der Wert, der zugewiesen `$PSEmailServer` wird, ist die SMTP-Standardeinstellung für PowerShell. Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

> [!WARNING]
> Das- `Send-MailMessage` Cmdlet ist veraltet. Dieses Cmdlet garantiert keine sicheren Verbindungen mit SMTP-Servern. Obwohl es in PowerShell keinen unmittelbaren Austausch gibt, wird empfohlen, nicht zu verwenden `Send-MailMessage` . Weitere Informationen finden Sie unter [Platform Compatibility Note DE0005](https://aka.ms/SendMailMessage).

## Beispiele

### Beispiel 1: Senden einer e-Mail von einer Person an eine andere Person

In diesem Beispiel wird eine e-Mail-Nachricht von einer Person an eine andere Person gesendet.

Die Parameter **from**, **to** und **Subject** werden von benötigt `Send-MailMessage` . In diesem Beispiel wird die Standard `$PSEmailServer` Variable für den SMTP-Server verwendet, sodass der **SmtpServer** -Parameter nicht benötigt wird.

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

Das `Send-MailMessage` Cmdlet verwendet den **from** -Parameter, um den Absender der Nachricht anzugeben. Der **to** -Parameter gibt den Empfänger der Nachricht an. Der " **Subject** "-Parameter verwendet die Text Zeichenfolge " **Test Mail** " als Nachricht, weil der optionale **Body** -Parameter nicht eingeschlossen ist.

### Beispiel 2: Senden einer Anlage

In diesem Beispiel wird eine e-Mail-Nachricht mit einer Anlage gesendet.

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

Das `Send-MailMessage` Cmdlet verwendet den **from** -Parameter, um den Absender der Nachricht anzugeben. Der **to** -Parameter gibt die Empfänger der Nachricht an. Der **Betreff** -Parameter beschreibt den Inhalt der Nachricht. Der **Body** -Parameter ist der Inhalt der Nachricht.

Der **Attachments** -Parameter gibt die Datei im aktuellen Verzeichnis an, das an die e-Mail-Nachricht angefügt ist. Der **Priority** -Parameter legt die Nachricht auf **hohe** Priorität fest. Der Parameter " **-deliverynotificationoption** " gibt zwei Werte an: " **onSuccess** " und " **OnFailure**". Der Absender empfängt e-Mail-Benachrichtigungen, um den Erfolg oder das Fehlschlagen der Nachrichtenübermittlung zu bestätigen.
Der **SmtpServer** -Parameter legt den SMTP-Server auf **SMTP.fabrikam.com** fest.

### Beispiel 3: Senden einer e-Mail an eine Mailingliste

In diesem Beispiel wird eine e-Mail-Nachricht an eine Mailingliste gesendet.

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

Das `Send-MailMessage` Cmdlet verwendet den **from** -Parameter, um den Absender der Nachricht anzugeben. Der **to** -Parameter gibt die Empfänger der Nachricht an. Der **CC** -Parameter sendet eine Kopie der Nachricht an den angegebenen Empfänger. Der **Bcc** -Parameter sendet eine Blind Kopie der Nachricht. Eine Blind Kopie ist eine e-Mail-Adresse, die für die anderen Empfänger ausgeblendet ist. Der **Subject** -Parameter ist die Nachricht, weil der optionale **Body** -Parameter nicht eingeschlossen ist.

Der **Credential** -Parameter gibt an, dass die Anmelde Informationen eines Domänen Administrators zum Senden der Nachricht verwendet werden. Der **Parameter** "", gibt an, dass Secure Socket Layer (SSL) eine sichere Verbindung erstellt.

## Parameter

### -Anhänge

Gibt die Pfad-und Dateinamen der Dateien an, die an die e-Mail-Nachricht angefügt werden. Sie können diesen Parameter verwenden oder die Pfade und Dateinamen an die Pipeline übergeben `Send-MailMessage` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BCC

Gibt die e-Mail-Adressen an, die eine Kopie der e-Mail erhalten, aber nicht als Empfänger der Nachricht aufgeführt sind. Geben Sie Namen (optional) und e-Mail-Adresse ein, z `Name <someone@fabrikam.com>` . b..

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Text

Gibt den Inhalt der e-Mail-Nachricht an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bodyashtml

Gibt an, dass der Wert des **Body** -Parameters HTML enthält.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: BAH

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CC

Gibt die e-Mail-Adressen an, an die eine Kopie (CC) der e-Mail-Nachricht gesendet wird. Geben Sie Namen (optional) und e-Mail-Adresse ein, z `Name <someone@fabrikam.com>` . b..

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**. Oder geben Sie ein **PSCredential** -Objekt ein, z. b. einen aus dem `Get-Credential` Cmdlet.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deliverynotificationoption

Gibt die Übermittlungs Benachrichtigungs Optionen für die e-Mail an. Sie können mehrere Werte angeben.
"None" ist der Standardwert. Der Alias für diesen Parameter ist " **DNO**".

Die Übermittlungs Benachrichtigungen werden an die Adresse im **from** -Parameter gesendet.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- `None`: Keine Benachrichtigung.
- `OnSuccess`: Benachrichtigen, wenn die Übermittlung erfolgreich war.
- `OnFailure`: Benachrichtigen, wenn die Übermittlung nicht erfolgreich war.
- `Delay`: Benachrichtigen, wenn die Übermittlung verzögert ist.
- `Never`: Nie benachrichtigen.

Diese Werte werden als Flag-basierte Enumeration definiert. Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen. Die Werte können an den Parameter **deliverynotification** als Array von Werten oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden. Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert. Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.

```yaml
Type: System.Net.Mail.DeliveryNotificationOptions
Parameter Sets: (All)
Aliases: DNO
Accepted values: None, OnSuccess, OnFailure, Delay, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Codierung

Gibt den Typ der Codierung für die Zieldatei an. Der Standardwert ist `Default`.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- `ASCII` Verwendet den ASCII-Zeichensatz (7-Bit).
- `BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.
- `Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).
- `OEM` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.
- `Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.
- `UTF7` Verwendet UTF-7.
- `UTF8` Verwendet UTF-8.
- `UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Von

Der **from** -Parameter ist erforderlich. Dieser Parameter gibt die e-Mail-Adresse des Absenders an. Geben Sie einen Namen (optional) und eine e-Mail-Adresse ein, z.b. `Name <someone@fabrikam.com>` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Gibt einen alternativen Port auf dem SMTP-Server an. Der Standardwert ist 25, wobei es sich um den SMTP-Standardport handelt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 25
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority

Gibt die Priorität der e-Mail-Nachricht an. Der Standardwert ist „Normal“. Die zulässigen Werte für diesen Parameter sind "Normal", "hoch" und "niedrig".

```yaml
Type: System.Net.Mail.MailPriority
Parameter Sets: (All)
Aliases:
Accepted values: Normal, High, Low

Required: False
Position: Named
Default value: Normal
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmtpServer

Gibt den Namen des SMTP-Servers an, der die e-Mail-Nachricht sendet.

Der Standardwert ist der Wert der `$PSEmailServer` Preference-Variablen. Wenn die Einstellungs Variable nicht festgelegt ist und dieser Parameter nicht verwendet wird, `Send-MailMessage` schlägt der Befehl fehl.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: 3
Default value: $PSEmailServer
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subject

Der Parameter " **Subject** " ist erforderlich. Dieser Parameter gibt den Betreff der e-Mail-Nachricht an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Bis

Der **to** -Parameter ist erforderlich. Dieser Parameter gibt die e-Mail-Adresse des Empfängers an. Wenn mehrere Empfänger vorhanden sind, trennen Sie die Adressen durch ein Komma ( `,` ). Geben Sie Namen (optional) und e-Mail-Adresse ein, z `Name <someone@fabrikam.com>` . b..

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -US-

Das Secure Sockets Layer (SSL)-Protokoll wird verwendet, um eine sichere Verbindung mit dem Remote Computer herzustellen, um e-Mails zu senden. Standardmäßig wird SSL nicht verwendet.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Eingaben

### System.String

Sie können die Pfad-und Dateinamen von Anlagen an übergeben `Send-MailMessage` .

## Ausgaben

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## Notizen

## Ähnliche Themen

[about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)
