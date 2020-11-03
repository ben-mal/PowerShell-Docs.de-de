---
description: Erläutert, wie Skripts signiert werden, damit Sie den PowerShell-Ausführungsrichtlinien entsprechen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_signing?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Signing
ms.openlocfilehash: 060a53d4d08700e541fb6bcd388ffb4167a271a3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222343"
---
# <a name="about-signing"></a><span data-ttu-id="b4832-104">Informationen zum Signieren</span><span class="sxs-lookup"><span data-stu-id="b4832-104">About Signing</span></span>

## <a name="short-description"></a><span data-ttu-id="b4832-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4832-105">Short description</span></span>
<span data-ttu-id="b4832-106">Erläutert, wie Skripts signiert werden, damit Sie den PowerShell-Ausführungsrichtlinien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b4832-106">Explains how to sign scripts so that they comply with the PowerShell execution policies.</span></span>

## <a name="long-description"></a><span data-ttu-id="b4832-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4832-107">Long description</span></span>

<span data-ttu-id="b4832-108">In der eingeschränkten Ausführungs Richtlinie ist es nicht zulässig, Skripts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b4832-108">The Restricted execution policy does not permit any scripts to run.</span></span> <span data-ttu-id="b4832-109">Mit den Ausführungsrichtlinien " **AllSigned** " und " **RemoteSigned** " wird verhindert, dass PowerShell Skripts ohne digitale Signatur ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="b4832-109">The **AllSigned** and **RemoteSigned** execution policies prevent PowerShell from running scripts that do not have a digital signature.</span></span>

<span data-ttu-id="b4832-110">In diesem Thema wird erläutert, wie ausgewählte Skripts ausgeführt werden, die nicht signiert sind, auch wenn die Ausführungs Richtlinie **RemoteSigned** ist, und wie Skripts für Ihre eigene Verwendung signiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4832-110">This topic explains how to run selected scripts that are not signed, even while the execution policy is **RemoteSigned** , and how to sign scripts for your own use.</span></span>

<span data-ttu-id="b4832-111">Weitere Informationen zu PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="b4832-111">For more information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="to-permit-signed-scripts-to-run"></a><span data-ttu-id="b4832-112">So lassen Sie das Ausführen signierter Skripts zu</span><span class="sxs-lookup"><span data-stu-id="b4832-112">To permit signed scripts to run</span></span>

<span data-ttu-id="b4832-113">Wenn Sie PowerShell zum ersten Mal auf einem Computer starten, ist die **Eingeschränkte** Ausführungs Richtlinie (Standardeinstellung) wahrscheinlich wirksam.</span><span class="sxs-lookup"><span data-stu-id="b4832-113">When you start PowerShell on a computer for the first time, the **Restricted** execution policy (the default) is likely to be in effect.</span></span>

<span data-ttu-id="b4832-114">Die **Eingeschränkte** Richtlinie lässt das Ausführen von Skripts nicht zu.</span><span class="sxs-lookup"><span data-stu-id="b4832-114">The **Restricted** policy does not permit any scripts to run.</span></span>

<span data-ttu-id="b4832-115">Geben Sie Folgendes ein, um die effektive Ausführungs Richtlinie auf dem Computer zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="b4832-115">To find the effective execution policy on your computer, type:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="b4832-116">Starten Sie PowerShell mit der Option als Administrator ausführen, um nicht signierte Skripts auszuführen, die Sie auf dem lokalen Computer schreiben, und von anderen Benutzern signierte Skripts. verwenden Sie dann den folgenden Befehl, um die Ausführungs Richtlinie auf dem Computer in **RemoteSigned** zu ändern:</span><span class="sxs-lookup"><span data-stu-id="b4832-116">To run unsigned scripts that you write on your local computer and signed scripts from other users, start PowerShell with the Run as Administrator option and then use the following command to change the execution policy on the computer to **RemoteSigned** :</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

<span data-ttu-id="b4832-117">Weitere Informationen finden Sie im Hilfethema für das `Set-ExecutionPolicy` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b4832-117">For more information, see the help topic for the `Set-ExecutionPolicy` cmdlet.</span></span>

## <a name="running-unsigned-scripts-using-the-remotesigned-execution-policy"></a><span data-ttu-id="b4832-118">Ausführen von nicht signierten Skripts mithilfe der RemoteSigned-Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="b4832-118">Running unsigned scripts using the RemoteSigned execution policy</span></span>

<span data-ttu-id="b4832-119">Wenn Ihre PowerShell-Ausführungs Richtlinie **RemoteSigned** ist, führt PowerShell keine nicht signierten Skripts aus, die aus dem Internet heruntergeladen werden, einschließlich nicht signierter Skripts, die über e-Mail-und Instant Messaging-Programme empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="b4832-119">If your PowerShell execution policy is **RemoteSigned** , PowerShell will not run unsigned scripts that are downloaded from the internet, including unsigned scripts you receive through email and instant messaging programs.</span></span>

<span data-ttu-id="b4832-120">Wenn Sie versuchen, ein heruntergeladenes Skript auszuführen, zeigt PowerShell die folgende Fehlermeldung an:</span><span class="sxs-lookup"><span data-stu-id="b4832-120">If you try to run a downloaded script, PowerShell displays the following error message:</span></span>

```Output
The file <file-name> cannot be loaded. The file <file-name> is not digitally
signed. The script will not execute on the system. Please see "Get-Help
about_Signing" for more details.
```

<span data-ttu-id="b4832-121">Bevor Sie das Skript ausführen, überprüfen Sie den Code, um sicher zu sein, dass Sie ihm vertrauen.</span><span class="sxs-lookup"><span data-stu-id="b4832-121">Before you run the script, review the code to be sure that you trust it.</span></span>
<span data-ttu-id="b4832-122">Skripts haben dieselbe Wirkung wie jedes ausführbare Programm.</span><span class="sxs-lookup"><span data-stu-id="b4832-122">Scripts have the same effect as any executable program.</span></span>

<span data-ttu-id="b4832-123">Verwenden Sie zum Ausführen eines nicht signierten Skripts das-Unblock-File-Cmdlet, oder verwenden Sie das folgende Verfahren.</span><span class="sxs-lookup"><span data-stu-id="b4832-123">To run an unsigned script, use the Unblock-File cmdlet or use the following procedure.</span></span>

1. <span data-ttu-id="b4832-124">Speichern Sie die Skriptdatei auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="b4832-124">Save the script file on your computer.</span></span>
2. <span data-ttu-id="b4832-125">Klicken Sie auf Start, klicken Sie auf Arbeitsplatz, und suchen Sie nach der gespeicherten Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="b4832-125">Click Start, click My Computer, and locate the saved script file.</span></span>
3. <span data-ttu-id="b4832-126">Klicken Sie mit der rechten Maustaste auf die Skriptdatei, und klicken Sie dann auf Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="b4832-126">Right-click the script file, and then click Properties.</span></span>
4. <span data-ttu-id="b4832-127">Klicken Sie auf Nicht mehr blocken.</span><span class="sxs-lookup"><span data-stu-id="b4832-127">Click Unblock.</span></span>

<span data-ttu-id="b4832-128">Wenn ein Skript, das aus dem Internet heruntergeladen wurde, digital signiert ist, Sie aber noch nicht als vertrauenswürdig für den Verleger ausgewählt haben, zeigt PowerShell die folgende Meldung an:</span><span class="sxs-lookup"><span data-stu-id="b4832-128">If a script that was downloaded from the internet is digitally signed, but you have not yet chosen to trust its publisher, PowerShell displays the following message:</span></span>

```Output
Do you want to run software from this untrusted publisher?
The file <file-name> is published by CN=<publisher-name>. This
publisher is not trusted on your system. Only run scripts
from trusted publishers.

[V] Never run  [D] Do not run  [R] Run once  [A] Always run
[?] Help (default is "D"):
```

<span data-ttu-id="b4832-129">Wenn Sie dem Verleger vertrauen, wählen Sie "einmal ausführen" oder "immer ausführen" aus.</span><span class="sxs-lookup"><span data-stu-id="b4832-129">If you trust the publisher, select "Run once" or "Always run."</span></span> <span data-ttu-id="b4832-130">Wenn Sie den Verleger nicht als vertrauenswürdig einstufen, wählen Sie entweder "niemals ausführen" oder "nicht ausführen" aus.</span><span class="sxs-lookup"><span data-stu-id="b4832-130">If you do not trust the publisher, select either "Never run" or "Do not run."</span></span> <span data-ttu-id="b4832-131">Wenn Sie die Option "nie ausführen" oder "immer ausführen" auswählen, werden Sie von PowerShell nicht erneut zur Eingabe des Verlegers aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b4832-131">If you select "Never run" or "Always run," PowerShell will not prompt you again for this publisher.</span></span>

## <a name="methods-of-signing-scripts"></a><span data-ttu-id="b4832-132">Methoden zum Signieren von Skripts</span><span class="sxs-lookup"><span data-stu-id="b4832-132">Methods of signing scripts</span></span>

<span data-ttu-id="b4832-133">Sie können die Skripts, die Sie schreiben, und die Skripts, die Sie aus anderen Quellen abrufen, signieren.</span><span class="sxs-lookup"><span data-stu-id="b4832-133">You can sign the scripts that you write and the scripts that you obtain from other sources.</span></span> <span data-ttu-id="b4832-134">Überprüfen Sie vor dem Signieren eines Skripts jeden Befehl, um sicherzustellen, dass er sicher ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4832-134">Before you sign any script, examine each command to verify that it is safe to run.</span></span>

<span data-ttu-id="b4832-135">Bewährte Methoden zum Signieren von Code finden Sie unter [bewährte Methoden für die Code Signatur](/previous-versions/windows/hardware/design/dn653556(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="b4832-135">For best practices about code signing, see [Code-Signing Best Practices](/previous-versions/windows/hardware/design/dn653556(v=vs.85)).</span></span>

<span data-ttu-id="b4832-136">Weitere Informationen zum Signieren einer Skriptdatei finden Sie unter [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature).</span><span class="sxs-lookup"><span data-stu-id="b4832-136">For more information about how to sign a script file, see [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature).</span></span>

<span data-ttu-id="b4832-137">Das- `New-SelfSignedCertificate` Cmdlet, das im PKI-Modul in PowerShell 3,0 eingeführt wurde, erstellt ein selbst signiertes Zertifikat, das zum Testen geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="b4832-137">The `New-SelfSignedCertificate` cmdlet, introduced in the PKI module in PowerShell 3.0, creates a self-signed certificate that is Appropriate for testing.</span></span> <span data-ttu-id="b4832-138">Weitere Informationen finden Sie im Hilfethema für das Cmdlet "New-SelfSignedCertificate".</span><span class="sxs-lookup"><span data-stu-id="b4832-138">For more information, see the help topic for the New-SelfSignedCertificate cmdlet.</span></span>

<span data-ttu-id="b4832-139">Wenn Sie einem Skript eine digitale Signatur hinzufügen möchten, müssen Sie es mit einem Code Signaturzertifikat signieren.</span><span class="sxs-lookup"><span data-stu-id="b4832-139">To add a digital signature to a script, you must sign it with a code signing certificate.</span></span> <span data-ttu-id="b4832-140">Zum Signieren einer Skriptdatei sind zwei Arten von Zertifikaten geeignet:</span><span class="sxs-lookup"><span data-stu-id="b4832-140">Two types of certificates are suitable for signing a script file:</span></span>

- <span data-ttu-id="b4832-141">Zertifikate, die von einer Zertifizierungsstelle erstellt werden: für eine Gebühr überprüft eine öffentliche Zertifizierungsstelle Ihre Identität und erteilt ein Code Signaturzertifikat.</span><span class="sxs-lookup"><span data-stu-id="b4832-141">Certificates that are created by a certification authority: For a fee, a public certification authority verifies your identity and gives you a code signing certificate.</span></span> <span data-ttu-id="b4832-142">Wenn Sie Ihr Zertifikat von einer seriösen Zertifizierungsstelle erwerben, können Sie Ihr Skript für Benutzer auf anderen Computern freigeben, auf denen Windows ausgeführt wird, da diese anderen Computer der Zertifizierungsstelle vertrauen.</span><span class="sxs-lookup"><span data-stu-id="b4832-142">When you purchase your certificate from a reputable certification authority, you are able to share your script with users on other computers that are running Windows because those other computers trust the certification authority.</span></span>

- <span data-ttu-id="b4832-143">Zertifikate, die Sie erstellen: Sie können ein selbst signiertes Zertifikat erstellen, für das das Zertifikat von Ihrem Computer erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b4832-143">Certificates that you create: You can create a self-signed certificate for which your computer is the authority that creates the certificate.</span></span> <span data-ttu-id="b4832-144">Dieses Zertifikat ist kostenlos und ermöglicht das Schreiben, Signieren und Ausführen von Skripts auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="b4832-144">This certificate is free of charge and enables you to write, sign, and run scripts on your computer.</span></span> <span data-ttu-id="b4832-145">Ein Skript, das von einem selbst signierten Zertifikat signiert wurde, kann jedoch nicht auf anderen Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b4832-145">However, a script signed by a self-signed certificate will not run on other computers.</span></span>

<span data-ttu-id="b4832-146">In der Regel verwenden Sie ein selbst signiertes Zertifikat nur zum Signieren von Skripts, die Sie für Ihre eigene Verwendung schreiben, und zum Signieren von Skripts, die Sie aus anderen Quellen erhalten, die Sie als sicher überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="b4832-146">Typically, you would use a self-signed certificate only to sign scripts that you write for your own use and to sign scripts that you get from other sources that you have verified to be safe.</span></span> <span data-ttu-id="b4832-147">Sie eignet sich nicht für Skripts, die selbst in einem Unternehmen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b4832-147">It is not appropriate for scripts that will be shared, even within an enterprise.</span></span>

<span data-ttu-id="b4832-148">Wenn Sie ein selbst signiertes Zertifikat erstellen, achten Sie darauf, dass Sie einen starken Schutz für private Schlüssel für Ihr Zertifikat aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b4832-148">If you create a self-signed certificate, be sure to enable strong private key protection on your certificate.</span></span> <span data-ttu-id="b4832-149">Dadurch wird verhindert, dass böswillige Programme Skripts in Ihrem Namen signieren.</span><span class="sxs-lookup"><span data-stu-id="b4832-149">This prevents malicious programs from signing scripts on your behalf.</span></span> <span data-ttu-id="b4832-150">Die Anweisungen sind am Ende dieses Themas enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4832-150">The instructions are included at the end of this topic.</span></span>

## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="b4832-151">Erstellen eines selbstsignierten Zertifikats</span><span class="sxs-lookup"><span data-stu-id="b4832-151">Create a self-signed certificate</span></span>

<span data-ttu-id="b4832-152">Verwenden Sie zum Erstellen eines selbst signierten Zertifikats in das- `New-SelfSignedCertificate` Cmdlet im PKI-Modul.</span><span class="sxs-lookup"><span data-stu-id="b4832-152">To create a self-signed certificate in use the `New-SelfSignedCertificate` cmdlet in the PKI module.</span></span> <span data-ttu-id="b4832-153">Dieses Modul wird in PowerShell 3,0 eingeführt und ist in Windows 8 und Windows Server 2012 enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4832-153">This module is introduced in PowerShell 3.0 and is included in Windows 8 and Windows Server 2012.</span></span> <span data-ttu-id="b4832-154">Weitere Informationen finden Sie im Hilfethema für das `New-SelfSignedCertificate` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b4832-154">For more information, see the help topic for the `New-SelfSignedCertificate` cmdlet.</span></span>

<span data-ttu-id="b4832-155">Verwenden Sie zum Erstellen eines selbst signierten Zertifikats in früheren Versionen von Windows das Tool zur Erstellung von Zertifikaten `MakeCert.exe` .</span><span class="sxs-lookup"><span data-stu-id="b4832-155">To create a self-signed certificate in earlier versions of Windows, use the Certificate Creation tool `MakeCert.exe`.</span></span> <span data-ttu-id="b4832-156">Dieses Tool ist im Microsoft .NET SDK (Version 1,1 und höher) und im Microsoft Windows SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4832-156">This tool is included in the Microsoft .NET SDK (versions 1.1 and later) and in the Microsoft Windows SDK.</span></span>

<span data-ttu-id="b4832-157">Weitere Informationen zur Syntax und den Parameter Beschreibungen des MakeCert.exe Tools finden Sie unter [Certificate Creation Tool (MakeCert.exe)](/previous-versions/dotnet/netframework-2.0/bfsktky3(v=vs.80)).</span><span class="sxs-lookup"><span data-stu-id="b4832-157">For more information about the syntax and the parameter descriptions of the MakeCert.exe tool, see [Certificate Creation Tool (MakeCert.exe)](/previous-versions/dotnet/netframework-2.0/bfsktky3(v=vs.80)).</span></span>

<span data-ttu-id="b4832-158">Führen Sie die folgenden Befehle in einem SDK-Eingabe Aufforderungs Fenster aus, um das MakeCert.exe Tool zum Erstellen eines Zertifikats zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4832-158">To use the MakeCert.exe tool to create a certificate, run the following commands in an SDK Command Prompt window.</span></span>

<span data-ttu-id="b4832-159">Hinweis: mit dem ersten Befehl wird eine lokale Zertifizierungsstelle für Ihren Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="b4832-159">Note: The first command creates a local certification authority for your computer.</span></span> <span data-ttu-id="b4832-160">Mit dem zweiten Befehl wird ein persönliches Zertifikat von der Zertifizierungsstelle generiert.</span><span class="sxs-lookup"><span data-stu-id="b4832-160">The second command generates a personal certificate from the certification authority.</span></span>

<span data-ttu-id="b4832-161">Hinweis: Sie können die Befehle genau so kopieren oder eingeben, wie Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b4832-161">Note: You can copy or type the commands exactly as they appear.</span></span> <span data-ttu-id="b4832-162">Es sind keine Substitutionen erforderlich, obwohl Sie den Zertifikat Namen ändern können.</span><span class="sxs-lookup"><span data-stu-id="b4832-162">No substitutions are necessary, although you can change the certificate name.</span></span>

```powershell
makecert -n "CN=PowerShell Local Certificate Root" -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -r -sv root.pvk root.cer `
-ss Root -sr localMachine

makecert -pe -n "CN=PowerShell User" -ss MY -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -iv root.pvk -ic root.cer
```

<span data-ttu-id="b4832-163">Mit dem MakeCert.exe Tool werden Sie zur Eingabe eines Kennworts für den privaten Schlüssel aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b4832-163">The MakeCert.exe tool will prompt you for a private key password.</span></span> <span data-ttu-id="b4832-164">Das Kennwort stellt sicher, dass niemand das Zertifikat ohne Ihre Zustimmung verwenden oder darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="b4832-164">The password ensures that no one can use or access the certificate without your consent.</span></span>
<span data-ttu-id="b4832-165">Erstellen Sie ein Kennwort, das Sie merken können.</span><span class="sxs-lookup"><span data-stu-id="b4832-165">Create and enter a password that you can remember.</span></span> <span data-ttu-id="b4832-166">Sie verwenden dieses Kennwort später zum Abrufen des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="b4832-166">You will use this password later to retrieve the certificate.</span></span>

<span data-ttu-id="b4832-167">Um sicherzustellen, dass das Zertifikat ordnungsgemäß generiert wurde, verwenden Sie den folgenden Befehl, um das Zertifikat im Zertifikat Speicher des Computers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b4832-167">To verify that the certificate was generated correctly, use the following command to get the certificate in the certificate store on the computer.</span></span> <span data-ttu-id="b4832-168">Sie finden keine Zertifikatsdatei im Dateisystem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b4832-168">You will not find a certificate file in the file system directory.</span></span>

<span data-ttu-id="b4832-169">Geben Sie an der PowerShell-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b4832-169">At the PowerShell prompt, type:</span></span>

```powershell
Get-ChildItem cert:\CurrentUser\my -codesigning
```

<span data-ttu-id="b4832-170">Dieser Befehl verwendet den PowerShell-Zertifikat Anbieter, um Informationen zum Zertifikat anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4832-170">This command uses the PowerShell Certificate provider to view information about the certificate.</span></span>

<span data-ttu-id="b4832-171">Wenn das Zertifikat erstellt wurde, zeigt die Ausgabe den Finger **Abdruck** an, der das Zertifikat in einer Anzeige identifiziert, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="b4832-171">If the certificate was created, the output shows the **thumbprint** that identifies the certificate in a display that resembles the following:</span></span>

```Output
Directory: Microsoft.PowerShell.Security\Certificate::CurrentUser\My

Thumbprint                                Subject
----------                                -------
4D4917CB140714BA5B81B96E0B18AAF2C4564FDF  CN=PowerShell User ]
```

## <a name="sign-a-script"></a><span data-ttu-id="b4832-172">Signieren eines Skripts</span><span class="sxs-lookup"><span data-stu-id="b4832-172">Sign a script</span></span>

<span data-ttu-id="b4832-173">Nachdem Sie ein selbst signiertes Zertifikat erstellt haben, können Sie Skripts signieren.</span><span class="sxs-lookup"><span data-stu-id="b4832-173">After you create a self-signed certificate, you can sign scripts.</span></span> <span data-ttu-id="b4832-174">Wenn Sie die **AllSigned** -Ausführungs Richtlinie verwenden, können Sie durch Signieren eines Skripts das Skript auf Ihrem Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="b4832-174">If you use the **AllSigned** execution policy, signing a script permits you to run the script on your computer.</span></span>

<span data-ttu-id="b4832-175">Mit dem folgenden Beispielskript wird `Add-Signature.ps1` ein Skript signiert.</span><span class="sxs-lookup"><span data-stu-id="b4832-175">The following sample script, `Add-Signature.ps1`, signs a script.</span></span> <span data-ttu-id="b4832-176">Wenn Sie jedoch die **AllSigned** -Ausführungs Richtlinie verwenden, müssen Sie das Skript signieren, `Add-Signature.ps1` bevor Sie es ausführen.</span><span class="sxs-lookup"><span data-stu-id="b4832-176">However, if you are using the **AllSigned** execution policy, you must sign the `Add-Signature.ps1` script before you run it.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4832-177">Das Skript muss mithilfe der ASCII-oder UTF8NoBOM-Codierung gespeichert werden. Sie können eine Skriptdatei signieren, die eine andere Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4832-177">The script must be saved using ASCII or UTF8NoBOM encoding.You can sign a script file that uses a different encoding.</span></span> <span data-ttu-id="b4832-178">Das Skript kann jedoch nicht ausgeführt werden, oder das Modul, das das Skript enthält, kann nicht importiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4832-178">But the script fails to run or the module containing the script fails to import.</span></span>

<span data-ttu-id="b4832-179">Um dieses Skript zu verwenden, kopieren Sie den folgenden Text in eine Textdatei, und benennen Sie ihn `Add-Signature.ps1` .</span><span class="sxs-lookup"><span data-stu-id="b4832-179">To use this script, copy the following text into a text file, and name it `Add-Signature.ps1`.</span></span>

```powershell
## Signs a file
param([string] $file=$(throw "Please specify a filename."))
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature $file $cert
```

<span data-ttu-id="b4832-180">Geben Sie an `Add-Signature.ps1` der PowerShell-Eingabeaufforderung die folgenden Befehle ein, um die Skriptdatei zu signieren:</span><span class="sxs-lookup"><span data-stu-id="b4832-180">To sign the `Add-Signature.ps1` script file, type the following commands at the PowerShell command prompt:</span></span>

```powershell
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature add-signature.ps1 $cert
```

<span data-ttu-id="b4832-181">Nachdem das Skript signiert wurde, können Sie es auf dem lokalen Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="b4832-181">After the script is signed, you can run it on the local computer.</span></span> <span data-ttu-id="b4832-182">Das Skript kann jedoch nicht auf Computern ausgeführt werden, auf denen die PowerShell-Ausführungs Richtlinie eine digitale Signatur von einer vertrauenswürdigen Zertifizierungsstelle erfordert.</span><span class="sxs-lookup"><span data-stu-id="b4832-182">However, the script will not run on computers on which the PowerShell execution policy requires a digital signature from a trusted authority.</span></span> <span data-ttu-id="b4832-183">Wenn Sie versuchen, zeigt PowerShell die folgende Fehlermeldung an:</span><span class="sxs-lookup"><span data-stu-id="b4832-183">If you try, PowerShell displays the following error message:</span></span>

```Output
The file C:\remote_file.ps1 cannot be loaded. The signature of the
certificate cannot be verified.
At line:1 char:15
+ .\ remote_file.ps1 <<<<
```

<span data-ttu-id="b4832-184">Wenn PowerShell diese Meldung anzeigt, wenn Sie ein Skript ausführen, das Sie nicht geschrieben haben, behandeln Sie die Datei, wie Sie alle nicht signierten Skripts behandeln würden.</span><span class="sxs-lookup"><span data-stu-id="b4832-184">If PowerShell displays this message when you run a script that you did not write, treat the file as you would treat any unsigned script.</span></span> <span data-ttu-id="b4832-185">Überprüfen Sie den Code, um zu bestimmen, ob Sie dem Skript vertrauen können.</span><span class="sxs-lookup"><span data-stu-id="b4832-185">Review the code to determine whether you can trust the script.</span></span>

## <a name="enable-strong-private-key-protection-for-your-certificate"></a><span data-ttu-id="b4832-186">Aktivieren des starken Schutzes für private Schlüssel für Ihr Zertifikat</span><span class="sxs-lookup"><span data-stu-id="b4832-186">Enable strong private key protection for your certificate</span></span>

<span data-ttu-id="b4832-187">Wenn Sie über ein privates Zertifikat auf Ihrem Computer verfügen, können schädliche Programme möglicherweise Skripts in Ihrem Namen signieren, wodurch PowerShell zum Ausführen autorisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b4832-187">If you have a private certificate on your computer, malicious programs might be able to sign scripts on your behalf, which authorizes PowerShell to run them.</span></span>

<span data-ttu-id="b4832-188">Um die automatisierte Signierung in Ihrem Namen zu verhindern, verwenden Sie den Zertifikat-Manager, `Certmgr.exe` um das Signaturzertifikat in eine Datei zu exportieren `.pfx` .</span><span class="sxs-lookup"><span data-stu-id="b4832-188">To prevent automated signing on your behalf, use Certificate Manager `Certmgr.exe` to export your signing certificate to a `.pfx` file.</span></span> <span data-ttu-id="b4832-189">Der Zertifikat-Manager ist im Microsoft .NET SDK, in der Microsoft Windows SDK und in Internet Explorer enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4832-189">Certificate Manager is included in the Microsoft .NET SDK, the Microsoft Windows SDK, and in internet Explorer.</span></span>

<span data-ttu-id="b4832-190">So exportieren Sie das Zertifikat:</span><span class="sxs-lookup"><span data-stu-id="b4832-190">To export the certificate:</span></span>

1. <span data-ttu-id="b4832-191">Starten Sie den Zertifikat-Manager.</span><span class="sxs-lookup"><span data-stu-id="b4832-191">Start Certificate Manager.</span></span>
2. <span data-ttu-id="b4832-192">Wählen Sie das Zertifikat aus, das von PowerShell local certificate root ausgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b4832-192">Select the certificate issued by PowerShell Local Certificate Root.</span></span>
3. <span data-ttu-id="b4832-193">Klicken Sie auf exportieren, um den Zertifikat Export-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="b4832-193">Click Export to start the Certificate Export Wizard.</span></span>
4. <span data-ttu-id="b4832-194">Wählen Sie ja, privaten Schlüssel exportieren aus, und klicken Sie dann auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="b4832-194">Select "Yes, export the private key", and then click Next.</span></span>
5. <span data-ttu-id="b4832-195">Wählen Sie "starken Schutz aktivieren" aus.</span><span class="sxs-lookup"><span data-stu-id="b4832-195">Select "Enable strong protection."</span></span>
6. <span data-ttu-id="b4832-196">Geben Sie ein Kennwort ein, und geben Sie es erneut ein, um zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="b4832-196">Type a password, and then type it again to confirm.</span></span>
7. <span data-ttu-id="b4832-197">Geben Sie einen Dateinamen mit der Dateinamenerweiterung ". pfx" ein.</span><span class="sxs-lookup"><span data-stu-id="b4832-197">Type a file name that has the .pfx file name extension.</span></span>
8. <span data-ttu-id="b4832-198">Klicken Sie auf Fertig stellen.</span><span class="sxs-lookup"><span data-stu-id="b4832-198">Click Finish.</span></span>

<span data-ttu-id="b4832-199">So importieren Sie das Zertifikat erneut:</span><span class="sxs-lookup"><span data-stu-id="b4832-199">To re-import the certificate:</span></span>

1. <span data-ttu-id="b4832-200">Starten Sie den Zertifikat-Manager.</span><span class="sxs-lookup"><span data-stu-id="b4832-200">Start Certificate Manager.</span></span>
2. <span data-ttu-id="b4832-201">Klicken Sie auf Importieren, um den Zertifikat Import-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="b4832-201">Click Import to start the Certificate Import Wizard.</span></span>
3. <span data-ttu-id="b4832-202">Öffnen Sie den Speicherort der PFX-Datei, die Sie während des Export Vorgangs erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b4832-202">Open to the location of the .pfx file that you created during the export process.</span></span>
4. <span data-ttu-id="b4832-203">Wählen Sie auf der Seite Kennwort die Option "starken Schutz für den privaten Schlüssel aktivieren", und geben Sie dann das Kennwort ein, das Sie während des Export Vorgangs zugewiesen haben</span><span class="sxs-lookup"><span data-stu-id="b4832-203">On the Password page, select "Enable strong private key protection", and then enter the password that you assigned during the export process.</span></span>
5. <span data-ttu-id="b4832-204">Wählen Sie den persönlichen Zertifikat Speicher aus.</span><span class="sxs-lookup"><span data-stu-id="b4832-204">Select the Personal certificate store.</span></span>
6. <span data-ttu-id="b4832-205">Klicken Sie auf Fertig stellen.</span><span class="sxs-lookup"><span data-stu-id="b4832-205">Click Finish.</span></span>

## <a name="prevent-the-signature-from-expiring"></a><span data-ttu-id="b4832-206">Verhindern, dass die Signatur abläuft</span><span class="sxs-lookup"><span data-stu-id="b4832-206">Prevent the signature from expiring</span></span>

<span data-ttu-id="b4832-207">Die digitale Signatur in einem Skript ist gültig, bis das Signaturzertifikat abläuft oder solange ein Zeitstempel-Server überprüfen kann, ob das Skript signiert wurde, während das Signaturzertifikat gültig war.</span><span class="sxs-lookup"><span data-stu-id="b4832-207">The digital signature in a script is valid until the signing certificate expires or as long as a timestamp server can verify that the script was signed while the signing certificate was valid.</span></span>

<span data-ttu-id="b4832-208">Da die meisten Signatur Zertifikate nur ein Jahr lang gültig sind, stellt die Verwendung eines Zeitstempel Servers sicher, dass Benutzer Ihr Skript für viele Jahre verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b4832-208">Because most signing certificates are valid for one year only, using a time stamp server ensures that users can use your script for many years to come.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4832-209">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b4832-209">See also</span></span>

[<span data-ttu-id="b4832-210">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="b4832-210">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="b4832-211">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="b4832-211">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="b4832-212">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="b4832-212">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="b4832-213">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="b4832-213">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="b4832-214">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="b4832-214">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

<span data-ttu-id="b4832-215">[Einführung in die Codesignatur](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="b4832-215">[Introduction to Code Signing](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))</span></span>
