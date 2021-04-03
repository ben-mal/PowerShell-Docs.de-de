---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: 8a194f2858055612ce7e92dadac42bada4d48ac4
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2021
ms.locfileid: "106273980"
---
# <span data-ttu-id="1732e-103">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="1732e-103">Send-MailMessage</span></span>

## <span data-ttu-id="1732e-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1732e-104">Synopsis</span></span>
<span data-ttu-id="1732e-105">Sendet eine E-Mail.</span><span class="sxs-lookup"><span data-stu-id="1732e-105">Sends an email message.</span></span>

## <span data-ttu-id="1732e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1732e-106">Syntax</span></span>

### <span data-ttu-id="1732e-107">All</span><span class="sxs-lookup"><span data-stu-id="1732e-107">All</span></span>

```
Send-MailMessage [-Attachments <String[]>] [-Bcc <String[]>] [[-Body] <String>] [-BodyAsHtml]
 [-Encoding <Encoding>] [-Cc <String[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 -From <String> [[-SmtpServer] <String>] [-Priority <MailPriority>] [-ReplyTo <String[]>]
 [[-Subject] <String>] [-To] <String[]> [-Credential <PSCredential>] [-UseSsl] [-Port <Int32>]
 [<CommonParameters>]
```

## <span data-ttu-id="1732e-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1732e-108">Description</span></span>

<span data-ttu-id="1732e-109">Das `Send-MailMessage` Cmdlet sendet eine e-Mail-Nachricht in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1732e-109">The `Send-MailMessage` cmdlet sends an email message from within PowerShell.</span></span>

<span data-ttu-id="1732e-110">Sie müssen einen Simple Mail Transfer Protocol (SMTP)-Server angeben, oder der `Send-MailMessage` Befehl schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="1732e-110">You must specify a Simple Mail Transfer Protocol (SMTP) server or the `Send-MailMessage` command fails.</span></span> <span data-ttu-id="1732e-111">Verwenden Sie den **SmtpServer** -Parameter, oder legen `$PSEmailServer` Sie die Variable auf einen gültigen SMTP-Server fest.</span><span class="sxs-lookup"><span data-stu-id="1732e-111">Use the **SmtpServer** parameter or set the `$PSEmailServer` variable to a valid SMTP server.</span></span>
<span data-ttu-id="1732e-112">Der Wert, der zugewiesen `$PSEmailServer` wird, ist die SMTP-Standardeinstellung für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1732e-112">The value assigned to `$PSEmailServer` is the default SMTP setting for PowerShell.</span></span> <span data-ttu-id="1732e-113">Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="1732e-113">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

> [!WARNING]
> <span data-ttu-id="1732e-114">Das- `Send-MailMessage` Cmdlet ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="1732e-114">The `Send-MailMessage` cmdlet is obsolete.</span></span> <span data-ttu-id="1732e-115">Dieses Cmdlet garantiert keine sicheren Verbindungen mit SMTP-Servern.</span><span class="sxs-lookup"><span data-stu-id="1732e-115">This cmdlet does not guarantee secure connections to SMTP servers.</span></span> <span data-ttu-id="1732e-116">Obwohl es in PowerShell keinen unmittelbaren Austausch gibt, wird empfohlen, nicht zu verwenden `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="1732e-116">While there is no immediate replacement available in PowerShell, we recommend you do not use `Send-MailMessage`.</span></span> <span data-ttu-id="1732e-117">Weitere Informationen finden Sie unter [Platform Compatibility Note DE0005](https://aka.ms/SendMailMessage).</span><span class="sxs-lookup"><span data-stu-id="1732e-117">For more information, see [Platform Compatibility note DE0005](https://aka.ms/SendMailMessage).</span></span>

## <span data-ttu-id="1732e-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1732e-118">Examples</span></span>

### <span data-ttu-id="1732e-119">Beispiel 1: Senden einer e-Mail von einer Person an eine andere Person</span><span class="sxs-lookup"><span data-stu-id="1732e-119">Example 1: Send an email from one person to another person</span></span>

<span data-ttu-id="1732e-120">In diesem Beispiel wird eine e-Mail-Nachricht von einer Person an eine andere Person gesendet.</span><span class="sxs-lookup"><span data-stu-id="1732e-120">This example sends an email message from one person to another person.</span></span>

<span data-ttu-id="1732e-121">Die Parameter **from**, **to** und **Subject** werden von benötigt `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="1732e-121">The **From**, **To**, and **Subject** parameters are required by `Send-MailMessage`.</span></span> <span data-ttu-id="1732e-122">In diesem Beispiel wird die Standard `$PSEmailServer` Variable für den SMTP-Server verwendet, sodass der **SmtpServer** -Parameter nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="1732e-122">This example uses the default `$PSEmailServer` variable for the SMTP server, so the **SmtpServer** parameter is not needed.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

<span data-ttu-id="1732e-123">Das `Send-MailMessage` Cmdlet verwendet den **from** -Parameter, um den Absender der Nachricht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1732e-123">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="1732e-124">Der **to** -Parameter gibt den Empfänger der Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="1732e-124">The **To** parameter specifies the message's recipient.</span></span> <span data-ttu-id="1732e-125">Der " **Subject** "-Parameter verwendet die Text Zeichenfolge " **Test Mail** " als Nachricht, weil der optionale **Body** -Parameter nicht eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1732e-125">The **Subject** parameter uses the text string **Test mail** as the message because the optional **Body** parameter is not included.</span></span>

### <span data-ttu-id="1732e-126">Beispiel 2: Senden einer Anlage</span><span class="sxs-lookup"><span data-stu-id="1732e-126">Example 2: Send an attachment</span></span>

<span data-ttu-id="1732e-127">In diesem Beispiel wird eine e-Mail-Nachricht mit einer Anlage gesendet.</span><span class="sxs-lookup"><span data-stu-id="1732e-127">This example sends an email message with an attachment.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

<span data-ttu-id="1732e-128">Das `Send-MailMessage` Cmdlet verwendet den **from** -Parameter, um den Absender der Nachricht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1732e-128">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="1732e-129">Der **to** -Parameter gibt die Empfänger der Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="1732e-129">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="1732e-130">Der **Betreff** -Parameter beschreibt den Inhalt der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1732e-130">The **Subject** parameter describes the content of the message.</span></span> <span data-ttu-id="1732e-131">Der **Body** -Parameter ist der Inhalt der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1732e-131">The **Body** parameter is the content of the message.</span></span>

<span data-ttu-id="1732e-132">Der **Attachments** -Parameter gibt die Datei im aktuellen Verzeichnis an, das an die e-Mail-Nachricht angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="1732e-132">The **Attachments** parameter specifies the file in the current directory that is attached to the email message.</span></span> <span data-ttu-id="1732e-133">Der **Priority** -Parameter legt die Nachricht auf **hohe** Priorität fest.</span><span class="sxs-lookup"><span data-stu-id="1732e-133">The **Priority** parameter sets the message to **High** priority.</span></span> <span data-ttu-id="1732e-134">Der Parameter " **-deliverynotificationoption** " gibt zwei Werte an: " **onSuccess** " und " **OnFailure**".</span><span class="sxs-lookup"><span data-stu-id="1732e-134">The **-DeliveryNotificationOption** parameter specifies two values, **OnSuccess** and **OnFailure**.</span></span> <span data-ttu-id="1732e-135">Der Absender empfängt e-Mail-Benachrichtigungen, um den Erfolg oder das Fehlschlagen der Nachrichtenübermittlung zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="1732e-135">The sender will receive email notifications to confirm the success or failure of the message delivery.</span></span>
<span data-ttu-id="1732e-136">Der **SmtpServer** -Parameter legt den SMTP-Server auf **SMTP.fabrikam.com** fest.</span><span class="sxs-lookup"><span data-stu-id="1732e-136">The **SmtpServer** parameter sets the SMTP server to **smtp.fabrikam.com**.</span></span>

### <span data-ttu-id="1732e-137">Beispiel 3: Senden einer e-Mail an eine Mailingliste</span><span class="sxs-lookup"><span data-stu-id="1732e-137">Example 3: Send email to a mailing list</span></span>

<span data-ttu-id="1732e-138">In diesem Beispiel wird eine e-Mail-Nachricht an eine Mailingliste gesendet.</span><span class="sxs-lookup"><span data-stu-id="1732e-138">This example sends an email message to a mailing list.</span></span>

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

<span data-ttu-id="1732e-139">Das `Send-MailMessage` Cmdlet verwendet den **from** -Parameter, um den Absender der Nachricht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1732e-139">The `Send-MailMessage` cmdlet uses the **From** parameter to specify the message's sender.</span></span> <span data-ttu-id="1732e-140">Der **to** -Parameter gibt die Empfänger der Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="1732e-140">The **To** parameter specifies the message's recipients.</span></span> <span data-ttu-id="1732e-141">Der **CC** -Parameter sendet eine Kopie der Nachricht an den angegebenen Empfänger.</span><span class="sxs-lookup"><span data-stu-id="1732e-141">The **Cc** parameter sends a copy of the message to the specified recipient.</span></span> <span data-ttu-id="1732e-142">Der **Bcc** -Parameter sendet eine Blind Kopie der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1732e-142">The **Bcc** parameter sends a blind copy of the message.</span></span> <span data-ttu-id="1732e-143">Eine Blind Kopie ist eine e-Mail-Adresse, die für die anderen Empfänger ausgeblendet ist.</span><span class="sxs-lookup"><span data-stu-id="1732e-143">A blind copy is an email address that is hidden from the other recipients.</span></span> <span data-ttu-id="1732e-144">Der **Subject** -Parameter ist die Nachricht, weil der optionale **Body** -Parameter nicht eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1732e-144">The **Subject** parameter is the message because the optional **Body** parameter is not included.</span></span>

<span data-ttu-id="1732e-145">Der **Credential** -Parameter gibt an, dass die Anmelde Informationen eines Domänen Administrators zum Senden der Nachricht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1732e-145">The **Credential** parameter specifies a domain administrator's credentials are used to send the message.</span></span> <span data-ttu-id="1732e-146">Der **Parameter** "", gibt an, dass Secure Socket Layer (SSL) eine sichere Verbindung erstellt.</span><span class="sxs-lookup"><span data-stu-id="1732e-146">The **UseSsl** parameter specifies that Secure Socket Layer (SSL) creates a secure connection.</span></span>

## <span data-ttu-id="1732e-147">Parameter</span><span class="sxs-lookup"><span data-stu-id="1732e-147">Parameters</span></span>

### <span data-ttu-id="1732e-148">-Anhänge</span><span class="sxs-lookup"><span data-stu-id="1732e-148">-Attachments</span></span>

<span data-ttu-id="1732e-149">Gibt die Pfad-und Dateinamen der Dateien an, die an die e-Mail-Nachricht angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1732e-149">Specifies the path and file names of files to be attached to the email message.</span></span> <span data-ttu-id="1732e-150">Sie können diesen Parameter verwenden oder die Pfade und Dateinamen an die Pipeline übergeben `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="1732e-150">You can use this parameter or pipe the paths and file names to `Send-MailMessage`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-151">-BCC</span><span class="sxs-lookup"><span data-stu-id="1732e-151">-Bcc</span></span>

<span data-ttu-id="1732e-152">Gibt die e-Mail-Adressen an, die eine Kopie der e-Mail erhalten, aber nicht als Empfänger der Nachricht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="1732e-152">Specifies the email addresses that receive a copy of the mail but are not listed as recipients of the message.</span></span> <span data-ttu-id="1732e-153">Geben Sie Namen (optional) und e-Mail-Adresse ein, z `Name <someone@fabrikam.com>` . b..</span><span class="sxs-lookup"><span data-stu-id="1732e-153">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-154">-Text</span><span class="sxs-lookup"><span data-stu-id="1732e-154">-Body</span></span>

<span data-ttu-id="1732e-155">Gibt den Inhalt der e-Mail-Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="1732e-155">Specifies the content of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-156">-Bodyashtml</span><span class="sxs-lookup"><span data-stu-id="1732e-156">-BodyAsHtml</span></span>

<span data-ttu-id="1732e-157">Gibt an, dass der Wert des **Body** -Parameters HTML enthält.</span><span class="sxs-lookup"><span data-stu-id="1732e-157">Specifies that the value of the **Body** parameter contains HTML.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: BAH

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-158">-CC</span><span class="sxs-lookup"><span data-stu-id="1732e-158">-Cc</span></span>

<span data-ttu-id="1732e-159">Gibt die e-Mail-Adressen an, an die eine Kopie (CC) der e-Mail-Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="1732e-159">Specifies the email addresses to which a carbon copy (CC) of the email message is sent.</span></span> <span data-ttu-id="1732e-160">Geben Sie Namen (optional) und e-Mail-Adresse ein, z `Name <someone@fabrikam.com>` . b..</span><span class="sxs-lookup"><span data-stu-id="1732e-160">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="1732e-161">-Credential</span></span>

<span data-ttu-id="1732e-162">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="1732e-162">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="1732e-163">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1732e-163">The default is the current user.</span></span>

<span data-ttu-id="1732e-164">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**.</span><span class="sxs-lookup"><span data-stu-id="1732e-164">Type a user name, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="1732e-165">Oder geben Sie ein **PSCredential** -Objekt ein, z. b. einen aus dem `Get-Credential` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1732e-165">Or, enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="1732e-166">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1732e-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="1732e-167">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="1732e-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-168">-Deliverynotificationoption</span><span class="sxs-lookup"><span data-stu-id="1732e-168">-DeliveryNotificationOption</span></span>

<span data-ttu-id="1732e-169">Gibt die Übermittlungs Benachrichtigungs Optionen für die e-Mail an.</span><span class="sxs-lookup"><span data-stu-id="1732e-169">Specifies the delivery notification options for the email message.</span></span> <span data-ttu-id="1732e-170">Sie können mehrere Werte angeben.</span><span class="sxs-lookup"><span data-stu-id="1732e-170">You can specify multiple values.</span></span>
<span data-ttu-id="1732e-171">"None" ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="1732e-171">None is the default value.</span></span> <span data-ttu-id="1732e-172">Der Alias für diesen Parameter ist " **DNO**".</span><span class="sxs-lookup"><span data-stu-id="1732e-172">The alias for this parameter is **DNO**.</span></span>

<span data-ttu-id="1732e-173">Die Übermittlungs Benachrichtigungen werden an die Adresse im **from** -Parameter gesendet.</span><span class="sxs-lookup"><span data-stu-id="1732e-173">The delivery notifications are sent to the address in the **From** parameter.</span></span>

<span data-ttu-id="1732e-174">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1732e-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="1732e-175">`None`: Keine Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="1732e-175">`None`: No notification.</span></span>
- <span data-ttu-id="1732e-176">`OnSuccess`: Benachrichtigen, wenn die Übermittlung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="1732e-176">`OnSuccess`: Notify if the delivery is successful.</span></span>
- <span data-ttu-id="1732e-177">`OnFailure`: Benachrichtigen, wenn die Übermittlung nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="1732e-177">`OnFailure`: Notify if the delivery is unsuccessful.</span></span>
- <span data-ttu-id="1732e-178">`Delay`: Benachrichtigen, wenn die Übermittlung verzögert ist.</span><span class="sxs-lookup"><span data-stu-id="1732e-178">`Delay`: Notify if the delivery is delayed.</span></span>
- <span data-ttu-id="1732e-179">`Never`: Nie benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="1732e-179">`Never`: Never notify.</span></span>

<span data-ttu-id="1732e-180">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="1732e-180">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="1732e-181">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1732e-181">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="1732e-182">Die Werte können an den Parameter **deliverynotification** als Array von Werten oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1732e-182">The values can be passed to the **DeliveryNotification** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="1732e-183">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="1732e-183">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="1732e-184">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1732e-184">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

```yaml
Type: System.Net.Mail.DeliveryNotificationOptions
Parameter Sets: (All)
Aliases: DNO
Accepted values: None, OnSuccess, OnFailure, Delay, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-185">-Codierung</span><span class="sxs-lookup"><span data-stu-id="1732e-185">-Encoding</span></span>

<span data-ttu-id="1732e-186">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="1732e-186">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="1732e-187">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="1732e-187">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="1732e-188">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1732e-188">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="1732e-189">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="1732e-189">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="1732e-190">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="1732e-190">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="1732e-191">`bigendianutf32`: Codiert im UTF-32-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="1732e-191">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="1732e-192">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="1732e-192">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="1732e-193">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="1732e-193">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="1732e-194">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="1732e-194">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="1732e-195">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="1732e-195">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="1732e-196">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="1732e-196">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="1732e-197">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="1732e-197">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="1732e-198">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="1732e-198">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="1732e-199">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="1732e-199">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="1732e-200">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="1732e-200">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-201">-Von</span><span class="sxs-lookup"><span data-stu-id="1732e-201">-From</span></span>

<span data-ttu-id="1732e-202">Der **from** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1732e-202">The **From** parameter is required.</span></span> <span data-ttu-id="1732e-203">Dieser Parameter gibt die e-Mail-Adresse des Absenders an.</span><span class="sxs-lookup"><span data-stu-id="1732e-203">This parameter specifies the sender's email address.</span></span> <span data-ttu-id="1732e-204">Geben Sie einen Namen (optional) und eine e-Mail-Adresse ein, z.b. `Name <someone@fabrikam.com>` .</span><span class="sxs-lookup"><span data-stu-id="1732e-204">Enter a name (optional) and email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-205">-Port</span><span class="sxs-lookup"><span data-stu-id="1732e-205">-Port</span></span>

<span data-ttu-id="1732e-206">Gibt einen alternativen Port auf dem SMTP-Server an.</span><span class="sxs-lookup"><span data-stu-id="1732e-206">Specifies an alternate port on the SMTP server.</span></span> <span data-ttu-id="1732e-207">Der Standardwert ist 25, wobei es sich um den SMTP-Standardport handelt.</span><span class="sxs-lookup"><span data-stu-id="1732e-207">The default value is 25, which is the default SMTP port.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 25
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-208">-Priority</span><span class="sxs-lookup"><span data-stu-id="1732e-208">-Priority</span></span>

<span data-ttu-id="1732e-209">Gibt die Priorität der e-Mail-Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="1732e-209">Specifies the priority of the email message.</span></span> <span data-ttu-id="1732e-210">Der Standardwert ist „Normal“.</span><span class="sxs-lookup"><span data-stu-id="1732e-210">Normal is the default.</span></span> <span data-ttu-id="1732e-211">Die zulässigen Werte für diesen Parameter sind "Normal", "hoch" und "niedrig".</span><span class="sxs-lookup"><span data-stu-id="1732e-211">The acceptable values for this parameter are Normal, High, and Low.</span></span>

```yaml
Type: System.Net.Mail.MailPriority
Parameter Sets: (All)
Aliases:
Accepted values: Normal, High, Low

Required: False
Position: Named
Default value: Normal
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-212">-ReplyTo</span><span class="sxs-lookup"><span data-stu-id="1732e-212">-ReplyTo</span></span>

<span data-ttu-id="1732e-213">Gibt zusätzliche e-Mail-Adressen (außer der from-Adresse) an, die zum Beantworten dieser Nachricht verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1732e-213">Specifies additional email addresses (other than the From address) to use to reply to this message.</span></span>
<span data-ttu-id="1732e-214">Geben Sie Namen (optional) und e-Mail-Adresse ein, z `Name <someone@fabrikam.com>` . b..</span><span class="sxs-lookup"><span data-stu-id="1732e-214">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

<span data-ttu-id="1732e-215">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1732e-215">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-216">-SmtpServer</span><span class="sxs-lookup"><span data-stu-id="1732e-216">-SmtpServer</span></span>

<span data-ttu-id="1732e-217">Gibt den Namen des SMTP-Servers an, der die e-Mail-Nachricht sendet.</span><span class="sxs-lookup"><span data-stu-id="1732e-217">Specifies the name of the SMTP server that sends the email message.</span></span>

<span data-ttu-id="1732e-218">Der Standardwert ist der Wert der `$PSEmailServer` Preference-Variablen.</span><span class="sxs-lookup"><span data-stu-id="1732e-218">The default value is the value of the `$PSEmailServer` preference variable.</span></span> <span data-ttu-id="1732e-219">Wenn die Einstellungs Variable nicht festgelegt ist und dieser Parameter nicht verwendet wird, `Send-MailMessage` schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="1732e-219">If the preference variable is not set and this parameter is not used, the `Send-MailMessage` command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: 3
Default value: $PSEmailServer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-220">-Subject</span><span class="sxs-lookup"><span data-stu-id="1732e-220">-Subject</span></span>

<span data-ttu-id="1732e-221">Der Parameter " **Subject** " ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1732e-221">The **Subject** parameter isn't required.</span></span> <span data-ttu-id="1732e-222">Dieser Parameter gibt den Betreff der e-Mail-Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="1732e-222">This parameter specifies the subject of the email message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-223">Bis</span><span class="sxs-lookup"><span data-stu-id="1732e-223">-To</span></span>

<span data-ttu-id="1732e-224">Der **to** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1732e-224">The **To** parameter is required.</span></span> <span data-ttu-id="1732e-225">Dieser Parameter gibt die e-Mail-Adresse des Empfängers an.</span><span class="sxs-lookup"><span data-stu-id="1732e-225">This parameter specifies the recipient's email address.</span></span> <span data-ttu-id="1732e-226">Wenn mehrere Empfänger vorhanden sind, trennen Sie die Adressen durch ein Komma ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="1732e-226">If there are multiple recipients, separate their addresses with a comma (`,`).</span></span> <span data-ttu-id="1732e-227">Geben Sie Namen (optional) und e-Mail-Adresse ein, z `Name <someone@fabrikam.com>` . b..</span><span class="sxs-lookup"><span data-stu-id="1732e-227">Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1732e-228">-US-</span><span class="sxs-lookup"><span data-stu-id="1732e-228">-UseSsl</span></span>

<span data-ttu-id="1732e-229">Das Secure Sockets Layer (SSL)-Protokoll wird verwendet, um eine sichere Verbindung mit dem Remote Computer herzustellen, um e-Mails zu senden.</span><span class="sxs-lookup"><span data-stu-id="1732e-229">The Secure Sockets Layer (SSL) protocol is used to establish a secure connection to the remote computer to send mail.</span></span> <span data-ttu-id="1732e-230">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="1732e-230">By default, SSL is not used.</span></span>

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

### <span data-ttu-id="1732e-231">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1732e-231">CommonParameters</span></span>

<span data-ttu-id="1732e-232">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1732e-232">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1732e-233">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1732e-233">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1732e-234">Eingaben</span><span class="sxs-lookup"><span data-stu-id="1732e-234">Inputs</span></span>

### <span data-ttu-id="1732e-235">System.String</span><span class="sxs-lookup"><span data-stu-id="1732e-235">System.String</span></span>

<span data-ttu-id="1732e-236">Sie können die Pfad-und Dateinamen von Anlagen an übergeben `Send-MailMessage` .</span><span class="sxs-lookup"><span data-stu-id="1732e-236">You can pipe the path and file names of attachments to `Send-MailMessage`.</span></span>

## <span data-ttu-id="1732e-237">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="1732e-237">Outputs</span></span>

### <span data-ttu-id="1732e-238">Keine</span><span class="sxs-lookup"><span data-stu-id="1732e-238">None</span></span>

<span data-ttu-id="1732e-239">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="1732e-239">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1732e-240">Notizen</span><span class="sxs-lookup"><span data-stu-id="1732e-240">Notes</span></span>

## <span data-ttu-id="1732e-241">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="1732e-241">Related Links</span></span>

[<span data-ttu-id="1732e-242">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="1732e-242">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="1732e-243">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="1732e-243">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

