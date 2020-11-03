---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: 6f98c95e6c0144f76393e9d28454833097894512
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213719"
---
# <span data-ttu-id="97f87-103">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="97f87-103">Send-MailMessage</span></span>

## <span data-ttu-id="97f87-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="97f87-104">SYNOPSIS</span></span>
<span data-ttu-id="97f87-105">Sendet eine E-Mail.</span><span class="sxs-lookup"><span data-stu-id="97f87-105">Sends an email message.</span></span>

## <span data-ttu-id="97f87-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="97f87-106">SYNTAX</span></span>

### <span data-ttu-id="97f87-107">Alle</span><span class="sxs-lookup"><span data-stu-id="97f87-107">All</span></span>

```
Send-MailMessage [-To] <string[]> [-Subject] <string> [[-Body] <string>] [[-SmtpServer] <string>]
 -From <string> [-Attachments <string[]>] [-Bcc <string[]>] [-BodyAsHtml] [-Encoding <Encoding>]
 [-Cc <string[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 [-Priority <MailPriority>] [-Credential <pscredential>] [-UseSsl] [-Port <int>]
 [<CommonParameters>]
```

## <span data-ttu-id="97f87-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="97f87-108">DESCRIPTION</span></span>

<span data-ttu-id="97f87-109">Das `Send-MailMessage` Cmdlet sendet eine e-Mail-Nachricht in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97f87-109">The `Send-MailMessage` cmdlet sends an email message from within PowerShell.</span></span>

<span data-ttu-id="97f87-110">Sie müssen einen Simple Mail Transfer Protocol (SMTP)-Server angeben, oder der `Send-MailMessage` Befehl schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="97f87-110">You must specify a Simple Mail Transfer Protocol (SMTP) server or the `Send-MailMessage` command fails.</span></span> <span data-ttu-id="97f87-111">Verwenden Sie den **SmtpServer** -Parameter, oder legen `$PSEmailServer` Sie die Variable auf einen gültigen SMTP-Server fest.</span><span class="sxs-lookup"><span data-stu-id="97f87-111">Use the **SmtpServer** parameter or set the `$PSEmailServer` variable to a valid SMTP server.</span></span>
<span data-ttu-id="97f87-112">Der Wert, der zugewiesen `$PSEmailServer` wird, ist die SMTP-Standardeinstellung für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97f87-112">The value assigned to `$PSEmailServer` is the default SMTP setting for PowerShell.</span></span> <span data-ttu-id="97f87-113">Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="97f87-113">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

> [!WARNING]
> <span data-ttu-id="97f87-114">Das- `Send-MailMessage` Cmdlet ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="97f87-114">The `Send-MailMessage` cmdlet is obsolete.</span></span> <span data-ttu-id="97f87-115">Dieses Cmdlet garantiert keine sicheren Verbindungen mit SMTP-Servern.</span><span class="sxs-lookup"><span data-stu-id="97f87-115">This cmdlet does not guarantee secure connections to SMTP servers.</span></span> <span data-ttu-id="97f87-116">Obwohl es in PowerShell keinen unmittelbaren Austausch gibt, wird empfohlen, nicht zu verwenden `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="97f87-116">While there is no immediate replacement available in PowerShell, we recommend you do not use `Send-MailMessage`.</span></span> <span data-ttu-id="97f87-117">Weitere Informationen finden Sie unter [Platform Compatibility Note DE0005](https://aka.ms/SendMailMessage).</span><span class="sxs-lookup"><span data-stu-id="97f87-117">For more information, see [Platform Compatibility note DE0005](https://aka.ms/SendMailMessage).</span></span>

## <span data-ttu-id="97f87-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="97f87-118">EXAMPLES</span></span>

### <span data-ttu-id="97f87-119">Beispiel 1: Senden einer e-Mail von einer Person an eine andere Person</span><span class="sxs-lookup"><span data-stu-id="97f87-119">Example 1: Send an email from one person to another person</span></span>

<span data-ttu-id="97f87-120">In diesem Beispiel wird eine e-Mail-Nachricht von einer Person an eine andere Person gesendet.</span><span class="sxs-lookup"><span data-stu-id="97f87-120">This example sends an email message from one person to another person.</span></span>

<span data-ttu-id="97f87-121">Die Parameter **from** , **to** und **Subject** werden von benötigt `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="97f87-121">The **From** , **To** , and **Subject** parameters are required by `Send-MailMessage`.</span></span> <span data-ttu-id="97f87-122">In diesem Beispiel wird die Standard `$PSEmailServer` Variable für den SMTP-Server verwendet, sodass der **SmtpServer** -Parameter nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="97f87-122">This example uses the default `$PSEmailServer` variable for the SMTP server, so the **SmtpServer** parameter is not needed.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

<span data-ttu-id="97f87-123">Das `Send-MailMessage` Cmdlet verwendet den **from** -Parameter, um den Absender der Nachricht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="97f87-123">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="97f87-124">Der **to** -Parameter gibt den Empfänger der Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="97f87-124">The **To** parameter specifies the message's recipient.</span></span> <span data-ttu-id="97f87-125">Der " **Subject** "-Parameter verwendet die Text Zeichenfolge " **Test Mail** " als Nachricht, weil der optionale **Body** -Parameter nicht eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="97f87-125">The **Subject** parameter uses the text string **Test mail** as the message because the optional **Body** parameter is not included.</span></span>

### <span data-ttu-id="97f87-126">Beispiel 2: Senden einer Anlage</span><span class="sxs-lookup"><span data-stu-id="97f87-126">Example 2: Send an attachment</span></span>

<span data-ttu-id="97f87-127">In diesem Beispiel wird eine e-Mail-Nachricht mit einer Anlage gesendet.</span><span class="sxs-lookup"><span data-stu-id="97f87-127">This example sends an email message with an attachment.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

<span data-ttu-id="97f87-128">Das `Send-MailMessage` Cmdlet verwendet den **from** -Parameter, um den Absender der Nachricht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="97f87-128">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="97f87-129">Der **to** -Parameter gibt die Empfänger der Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="97f87-129">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="97f87-130">Der **Betreff** -Parameter beschreibt den Inhalt der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="97f87-130">The **Subject** parameter describes the content of the message.</span></span> <span data-ttu-id="97f87-131">Der **Body** -Parameter ist der Inhalt der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="97f87-131">The **Body** parameter is the content of the message.</span></span>

<span data-ttu-id="97f87-132">Der **Attachments** -Parameter gibt die Datei im aktuellen Verzeichnis an, das an die e-Mail-Nachricht angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="97f87-132">The **Attachments** parameter specifies the file in the current directory that is attached to the email message.</span></span> <span data-ttu-id="97f87-133">Der **Priority** -Parameter legt die Nachricht auf **hohe** Priorität fest.</span><span class="sxs-lookup"><span data-stu-id="97f87-133">The **Priority** parameter sets the message to **High** priority.</span></span> <span data-ttu-id="97f87-134">Der Parameter " **-deliverynotificationoption** " gibt zwei Werte an: " **onSuccess** " und " **OnFailure** ".</span><span class="sxs-lookup"><span data-stu-id="97f87-134">The **-DeliveryNotificationOption** parameter specifies two values, **OnSuccess** and **OnFailure** .</span></span> <span data-ttu-id="97f87-135">Der Absender empfängt e-Mail-Benachrichtigungen, um den Erfolg oder das Fehlschlagen der Nachrichtenübermittlung zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="97f87-135">The sender will receive email notifications to confirm the success or failure of the message delivery.</span></span>
<span data-ttu-id="97f87-136">Der **SmtpServer** -Parameter legt den SMTP-Server auf **SMTP.fabrikam.com** fest.</span><span class="sxs-lookup"><span data-stu-id="97f87-136">The **SmtpServer** parameter sets the SMTP server to **smtp.fabrikam.com** .</span></span>

### <span data-ttu-id="97f87-137">Beispiel 3: Senden einer e-Mail an eine Mailingliste</span><span class="sxs-lookup"><span data-stu-id="97f87-137">Example 3: Send email to a mailing list</span></span>

<span data-ttu-id="97f87-138">In diesem Beispiel wird eine e-Mail-Nachricht an eine Mailingliste gesendet.</span><span class="sxs-lookup"><span data-stu-id="97f87-138">This example sends an email message to a mailing list.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

<span data-ttu-id="97f87-139">Das `Send-MailMessage` Cmdlet verwendet den **from** -Parameter, um den Absender der Nachricht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="97f87-139">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="97f87-140">Der **to** -Parameter gibt die Empfänger der Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="97f87-140">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="97f87-141">Der **CC** -Parameter sendet eine Kopie der Nachricht an den angegebenen Empfänger.</span><span class="sxs-lookup"><span data-stu-id="97f87-141">The **Cc** parameter sends a copy of the message to the specified recipient.</span></span> <span data-ttu-id="97f87-142">Der **Bcc** -Parameter sendet eine Blind Kopie der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="97f87-142">The **Bcc** parameter sends a blind copy of the message.</span></span> <span data-ttu-id="97f87-143">Eine Blind Kopie ist eine e-Mail-Adresse, die für die anderen Empfänger ausgeblendet ist.</span><span class="sxs-lookup"><span data-stu-id="97f87-143">A blind copy is an email address that is hidden from the other recipients.</span></span> <span data-ttu-id="97f87-144">Der **Subject** -Parameter ist die Nachricht, weil der optionale **Body** -Parameter nicht eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="97f87-144">The **Subject** parameter is the message because the optional **Body** parameter is not included.</span></span>

<span data-ttu-id="97f87-145">Der **Credential** -Parameter gibt an, dass die Anmelde Informationen eines Domänen Administrators zum Senden der Nachricht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="97f87-145">The **Credential** parameter specifies a domain administrator's credentials are used to send the message.</span></span> <span data-ttu-id="97f87-146">Der **Parameter** "", gibt an, dass Secure Socket Layer (SSL) eine sichere Verbindung erstellt.</span><span class="sxs-lookup"><span data-stu-id="97f87-146">The **UseSsl** parameter specifies that Secure Socket Layer (SSL) creates a secure connection.</span></span>

## <span data-ttu-id="97f87-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="97f87-147">PARAMETERS</span></span>

### <span data-ttu-id="97f87-148">-Anhänge</span><span class="sxs-lookup"><span data-stu-id="97f87-148">-Attachments</span></span>

<span data-ttu-id="97f87-149">Gibt die Pfad-und Dateinamen der Dateien an, die an die e-Mail-Nachricht angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="97f87-149">Specifies the path and file names of files to be attached to the email message.</span></span> <span data-ttu-id="97f87-150">Sie können diesen Parameter verwenden oder die Pfade und Dateinamen an die Pipeline übergeben `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="97f87-150">You can use this parameter or pipe the paths and file names to `Send-MailMessage`.</span></span>

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

### <span data-ttu-id="97f87-151">-BCC</span><span class="sxs-lookup"><span data-stu-id="97f87-151">-Bcc</span></span>

<span data-ttu-id="97f87-152">Gibt die e-Mail-Adressen an, die eine Kopie der e-Mail erhalten, aber nicht als Empfänger der Nachricht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="97f87-152">Specifies the email addresses that receive a copy of the mail but are not listed as recipients of the message.</span></span> <span data-ttu-id="97f87-153">Geben Sie Namen (optional) und e-Mail-Adresse ein, z `Name <someone@fabrikam.com>` . b..</span><span class="sxs-lookup"><span data-stu-id="97f87-153">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="97f87-154">-Text</span><span class="sxs-lookup"><span data-stu-id="97f87-154">-Body</span></span>

<span data-ttu-id="97f87-155">Gibt den Inhalt der e-Mail-Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="97f87-155">Specifies the content of the email message.</span></span>

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

### <span data-ttu-id="97f87-156">-Bodyashtml</span><span class="sxs-lookup"><span data-stu-id="97f87-156">-BodyAsHtml</span></span>

<span data-ttu-id="97f87-157">Gibt an, dass der Wert des **Body** -Parameters HTML enthält.</span><span class="sxs-lookup"><span data-stu-id="97f87-157">Specifies that the value of the **Body** parameter contains HTML.</span></span>

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

### <span data-ttu-id="97f87-158">-CC</span><span class="sxs-lookup"><span data-stu-id="97f87-158">-Cc</span></span>

<span data-ttu-id="97f87-159">Gibt die e-Mail-Adressen an, an die eine Kopie (CC) der e-Mail-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="97f87-159">Specifies the email addresses to which a carbon copy (CC) of the email message is sent.</span></span> <span data-ttu-id="97f87-160">Geben Sie Namen (optional) und e-Mail-Adresse ein, z `Name <someone@fabrikam.com>` . b..</span><span class="sxs-lookup"><span data-stu-id="97f87-160">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="97f87-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="97f87-161">-Credential</span></span>

<span data-ttu-id="97f87-162">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="97f87-162">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="97f87-163">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="97f87-163">The default is the current user.</span></span>

<span data-ttu-id="97f87-164">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** .</span><span class="sxs-lookup"><span data-stu-id="97f87-164">Type a user name, such as **User01** or **Domain01\User01** .</span></span> <span data-ttu-id="97f87-165">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. einen aus dem `Get-Credential` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97f87-165">Or, enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="97f87-166">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="97f87-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="97f87-167">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="97f87-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="97f87-168">-Deliverynotificationoption</span><span class="sxs-lookup"><span data-stu-id="97f87-168">-DeliveryNotificationOption</span></span>

<span data-ttu-id="97f87-169">Gibt die Übermittlungs Benachrichtigungs Optionen für die e-Mail an.</span><span class="sxs-lookup"><span data-stu-id="97f87-169">Specifies the delivery notification options for the email message.</span></span> <span data-ttu-id="97f87-170">Sie können mehrere Werte angeben.</span><span class="sxs-lookup"><span data-stu-id="97f87-170">You can specify multiple values.</span></span>
<span data-ttu-id="97f87-171">"None" ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="97f87-171">None is the default value.</span></span> <span data-ttu-id="97f87-172">Der Alias für diesen Parameter ist " **DNO** ".</span><span class="sxs-lookup"><span data-stu-id="97f87-172">The alias for this parameter is **DNO** .</span></span>

<span data-ttu-id="97f87-173">Die Übermittlungs Benachrichtigungen werden an die Adresse im **from** -Parameter gesendet.</span><span class="sxs-lookup"><span data-stu-id="97f87-173">The delivery notifications are sent to the address in the **From** parameter.</span></span>

<span data-ttu-id="97f87-174">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97f87-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="97f87-175">`None`: Keine Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="97f87-175">`None`: No notification.</span></span>
- <span data-ttu-id="97f87-176">`OnSuccess`: Benachrichtigen, wenn die Übermittlung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="97f87-176">`OnSuccess`: Notify if the delivery is successful.</span></span>
- <span data-ttu-id="97f87-177">`OnFailure`: Benachrichtigen, wenn die Übermittlung nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="97f87-177">`OnFailure`: Notify if the delivery is unsuccessful.</span></span>
- <span data-ttu-id="97f87-178">`Delay`: Benachrichtigen, wenn die Übermittlung verzögert ist.</span><span class="sxs-lookup"><span data-stu-id="97f87-178">`Delay`: Notify if the delivery is delayed.</span></span>
- <span data-ttu-id="97f87-179">`Never`: Nie benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="97f87-179">`Never`: Never notify.</span></span>

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

### <span data-ttu-id="97f87-180">-Codierung</span><span class="sxs-lookup"><span data-stu-id="97f87-180">-Encoding</span></span>

<span data-ttu-id="97f87-181">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="97f87-181">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="97f87-182">Der Standardwert ist `Default`.</span><span class="sxs-lookup"><span data-stu-id="97f87-182">The default value is `Default`.</span></span>

<span data-ttu-id="97f87-183">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="97f87-183">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="97f87-184">`ASCII` Verwendet den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="97f87-184">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="97f87-185">`BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="97f87-185">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="97f87-186">`Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).</span><span class="sxs-lookup"><span data-stu-id="97f87-186">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="97f87-187">`OEM` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.</span><span class="sxs-lookup"><span data-stu-id="97f87-187">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="97f87-188">`Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="97f87-188">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="97f87-189">`UTF7` Verwendet UTF-7.</span><span class="sxs-lookup"><span data-stu-id="97f87-189">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="97f87-190">`UTF8` Verwendet UTF-8.</span><span class="sxs-lookup"><span data-stu-id="97f87-190">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="97f87-191">`UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="97f87-191">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

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

### <span data-ttu-id="97f87-192">-Von</span><span class="sxs-lookup"><span data-stu-id="97f87-192">-From</span></span>

<span data-ttu-id="97f87-193">Der **from** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="97f87-193">The **From** parameter is required.</span></span> <span data-ttu-id="97f87-194">Dieser Parameter gibt die e-Mail-Adresse des Absenders an.</span><span class="sxs-lookup"><span data-stu-id="97f87-194">This parameter specifies the sender's email address.</span></span> <span data-ttu-id="97f87-195">Geben Sie einen Namen (optional) und eine e-Mail-Adresse ein, z.b. `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="97f87-195">Enter a name (optional) and email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="97f87-196">-Port</span><span class="sxs-lookup"><span data-stu-id="97f87-196">-Port</span></span>

<span data-ttu-id="97f87-197">Gibt einen alternativen Port auf dem SMTP-Server an.</span><span class="sxs-lookup"><span data-stu-id="97f87-197">Specifies an alternate port on the SMTP server.</span></span> <span data-ttu-id="97f87-198">Der Standardwert ist 25, wobei es sich um den SMTP-Standardport handelt.</span><span class="sxs-lookup"><span data-stu-id="97f87-198">The default value is 25, which is the default SMTP port.</span></span>

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

### <span data-ttu-id="97f87-199">-Priority</span><span class="sxs-lookup"><span data-stu-id="97f87-199">-Priority</span></span>

<span data-ttu-id="97f87-200">Gibt die Priorität der e-Mail-Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="97f87-200">Specifies the priority of the email message.</span></span> <span data-ttu-id="97f87-201">Der Standardwert ist „Normal“.</span><span class="sxs-lookup"><span data-stu-id="97f87-201">Normal is the default.</span></span> <span data-ttu-id="97f87-202">Die zulässigen Werte für diesen Parameter sind "Normal", "hoch" und "niedrig".</span><span class="sxs-lookup"><span data-stu-id="97f87-202">The acceptable values for this parameter are Normal, High, and Low.</span></span>

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

### <span data-ttu-id="97f87-203">-SmtpServer</span><span class="sxs-lookup"><span data-stu-id="97f87-203">-SmtpServer</span></span>

<span data-ttu-id="97f87-204">Gibt den Namen des SMTP-Servers an, der die e-Mail-Nachricht sendet.</span><span class="sxs-lookup"><span data-stu-id="97f87-204">Specifies the name of the SMTP server that sends the email message.</span></span>

<span data-ttu-id="97f87-205">Der Standardwert ist der Wert der `$PSEmailServer` Preference-Variablen.</span><span class="sxs-lookup"><span data-stu-id="97f87-205">The default value is the value of the `$PSEmailServer` preference variable.</span></span> <span data-ttu-id="97f87-206">Wenn die Einstellungs Variable nicht festgelegt ist und dieser Parameter nicht verwendet wird, `Send-MailMessage` schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="97f87-206">If the preference variable is not set and this parameter is not used, the `Send-MailMessage` command fails.</span></span>

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

### <span data-ttu-id="97f87-207">-Subject</span><span class="sxs-lookup"><span data-stu-id="97f87-207">-Subject</span></span>

<span data-ttu-id="97f87-208">Der Parameter " **Subject** " ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="97f87-208">The **Subject** parameter is required.</span></span> <span data-ttu-id="97f87-209">Dieser Parameter gibt den Betreff der e-Mail-Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="97f87-209">This parameter specifies the subject of the email message.</span></span>

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

### <span data-ttu-id="97f87-210">Bis</span><span class="sxs-lookup"><span data-stu-id="97f87-210">-To</span></span>

<span data-ttu-id="97f87-211">Der **to** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="97f87-211">The **To** parameter is required.</span></span> <span data-ttu-id="97f87-212">Dieser Parameter gibt die e-Mail-Adresse des Empfängers an.</span><span class="sxs-lookup"><span data-stu-id="97f87-212">This parameter specifies the recipient's email address.</span></span> <span data-ttu-id="97f87-213">Wenn mehrere Empfänger vorhanden sind, trennen Sie die Adressen durch ein Komma ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="97f87-213">If there are multiple recipients, separate their addresses with a comma (`,`).</span></span> <span data-ttu-id="97f87-214">Geben Sie Namen (optional) und e-Mail-Adresse ein, z `Name <someone@fabrikam.com>` . b..</span><span class="sxs-lookup"><span data-stu-id="97f87-214">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

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

### <span data-ttu-id="97f87-215">-US-</span><span class="sxs-lookup"><span data-stu-id="97f87-215">-UseSsl</span></span>

<span data-ttu-id="97f87-216">Das Secure Sockets Layer (SSL)-Protokoll wird verwendet, um eine sichere Verbindung mit dem Remote Computer herzustellen, um e-Mails zu senden.</span><span class="sxs-lookup"><span data-stu-id="97f87-216">The Secure Sockets Layer (SSL) protocol is used to establish a secure connection to the remote computer to send mail.</span></span> <span data-ttu-id="97f87-217">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="97f87-217">By default, SSL is not used.</span></span>

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

### <span data-ttu-id="97f87-218">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="97f87-218">CommonParameters</span></span>

<span data-ttu-id="97f87-219">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="97f87-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="97f87-220">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="97f87-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="97f87-221">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="97f87-221">INPUTS</span></span>

### <span data-ttu-id="97f87-222">System.String</span><span class="sxs-lookup"><span data-stu-id="97f87-222">System.String</span></span>

<span data-ttu-id="97f87-223">Sie können die Pfad-und Dateinamen von Anlagen an übergeben `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="97f87-223">You can pipe the path and file names of attachments to `Send-MailMessage`.</span></span>

## <span data-ttu-id="97f87-224">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="97f87-224">OUTPUTS</span></span>

### <span data-ttu-id="97f87-225">Keine</span><span class="sxs-lookup"><span data-stu-id="97f87-225">None</span></span>

<span data-ttu-id="97f87-226">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="97f87-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="97f87-227">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="97f87-227">NOTES</span></span>

## <span data-ttu-id="97f87-228">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="97f87-228">RELATED LINKS</span></span>

[<span data-ttu-id="97f87-229">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="97f87-229">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="97f87-230">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="97f87-230">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)
