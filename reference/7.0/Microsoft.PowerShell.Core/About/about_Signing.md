---
description: Erläutert, wie Skripts signiert werden, damit Sie den PowerShell-Ausführungsrichtlinien entsprechen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_signing?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Signing
ms.openlocfilehash: e6b9ac8b096ff2607dc6b68512a998ac00bd1796
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685701"
---
# <a name="about-signing"></a>Informationen zum Signieren

## <a name="short-description"></a>Kurze Beschreibung
Erläutert, wie Skripts signiert werden, damit Sie den PowerShell-Ausführungsrichtlinien entsprechen.

## <a name="long-description"></a>Lange Beschreibung

In der eingeschränkten Ausführungs Richtlinie ist es nicht zulässig, Skripts auszuführen. Mit den Ausführungsrichtlinien " **AllSigned** " und " **RemoteSigned** " wird verhindert, dass PowerShell Skripts ohne digitale Signatur ausführen kann.

In diesem Thema wird erläutert, wie ausgewählte Skripts ausgeführt werden, die nicht signiert sind, auch wenn die Ausführungs Richtlinie **RemoteSigned** ist, und wie Skripts für Ihre eigene Verwendung signiert werden.

Weitere Informationen zu PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).

## <a name="to-permit-signed-scripts-to-run"></a>So lassen Sie das Ausführen signierter Skripts zu

Wenn Sie PowerShell zum ersten Mal auf einem Computer starten, ist die **Eingeschränkte** Ausführungs Richtlinie (Standardeinstellung) wahrscheinlich wirksam.

Die **Eingeschränkte** Richtlinie lässt das Ausführen von Skripts nicht zu.

Geben Sie Folgendes ein, um die effektive Ausführungs Richtlinie auf dem Computer zu ermitteln:

```powershell
Get-ExecutionPolicy
```

Starten Sie PowerShell mit der Option als Administrator ausführen, um nicht signierte Skripts auszuführen, die Sie auf dem lokalen Computer schreiben, und von anderen Benutzern signierte Skripts. verwenden Sie dann den folgenden Befehl, um die Ausführungs Richtlinie auf dem Computer in **RemoteSigned** zu ändern:

```powershell
Set-ExecutionPolicy RemoteSigned
```

Weitere Informationen finden Sie im Hilfethema für das `Set-ExecutionPolicy` Cmdlet.

## <a name="running-unsigned-scripts-using-the-remotesigned-execution-policy"></a>Ausführen von nicht signierten Skripts mithilfe der RemoteSigned-Ausführungs Richtlinie

Wenn Ihre PowerShell-Ausführungs Richtlinie **RemoteSigned** ist, führt PowerShell keine nicht signierten Skripts aus, die aus dem Internet heruntergeladen werden, einschließlich nicht signierter Skripts, die über e-Mail-und Instant Messaging-Programme empfangen werden.

Wenn Sie versuchen, ein heruntergeladenes Skript auszuführen, zeigt PowerShell die folgende Fehlermeldung an:

```Output
The file <file-name> cannot be loaded. The file <file-name> is not digitally
signed. The script will not execute on the system. Please see "Get-Help
about_Signing" for more details.
```

Bevor Sie das Skript ausführen, überprüfen Sie den Code, um sicher zu sein, dass Sie ihm vertrauen.
Skripts haben dieselbe Wirkung wie jedes ausführbare Programm.

Verwenden Sie zum Ausführen eines nicht signierten Skripts das-Unblock-File-Cmdlet, oder verwenden Sie das folgende Verfahren.

1. Speichern Sie die Skriptdatei auf Ihrem Computer.
2. Klicken Sie auf Start, klicken Sie auf Arbeitsplatz, und suchen Sie nach der gespeicherten Skriptdatei.
3. Klicken Sie mit der rechten Maustaste auf die Skriptdatei, und klicken Sie dann auf Eigenschaften.
4. Klicken Sie auf Nicht mehr blocken.

Wenn ein Skript, das aus dem Internet heruntergeladen wurde, digital signiert ist, Sie aber noch nicht als vertrauenswürdig für den Verleger ausgewählt haben, zeigt PowerShell die folgende Meldung an:

```Output
Do you want to run software from this untrusted publisher?
The file <file-name> is published by CN=<publisher-name>. This
publisher is not trusted on your system. Only run scripts
from trusted publishers.

[V] Never run  [D] Do not run  [R] Run once  [A] Always run
[?] Help (default is "D"):
```

Wenn Sie dem Verleger vertrauen, wählen Sie "einmal ausführen" oder "immer ausführen" aus. Wenn Sie den Verleger nicht als vertrauenswürdig einstufen, wählen Sie entweder "niemals ausführen" oder "nicht ausführen" aus. Wenn Sie die Option "nie ausführen" oder "immer ausführen" auswählen, werden Sie von PowerShell nicht erneut zur Eingabe des Verlegers aufgefordert.

## <a name="methods-of-signing-scripts"></a>Methoden zum Signieren von Skripts

Sie können die Skripts, die Sie schreiben, und die Skripts, die Sie aus anderen Quellen abrufen, signieren. Überprüfen Sie vor dem Signieren eines Skripts jeden Befehl, um sicherzustellen, dass er sicher ausgeführt werden kann.

Bewährte Methoden zum Signieren von Code finden Sie unter [bewährte Methoden für die Code Signatur](/previous-versions/windows/hardware/design/dn653556(v=vs.85)).

Weitere Informationen zum Signieren einer Skriptdatei finden Sie unter [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature).

Das- `New-SelfSignedCertificate` Cmdlet, das im PKI-Modul in PowerShell 3,0 eingeführt wurde, erstellt ein selbst signiertes Zertifikat, das zum Testen geeignet ist. Weitere Informationen finden Sie im Hilfethema für das Cmdlet "New-SelfSignedCertificate".

Wenn Sie einem Skript eine digitale Signatur hinzufügen möchten, müssen Sie es mit einem Code Signaturzertifikat signieren. Zum Signieren einer Skriptdatei sind zwei Arten von Zertifikaten geeignet:

- Zertifikate, die von einer Zertifizierungsstelle erstellt werden: für eine Gebühr überprüft eine öffentliche Zertifizierungsstelle Ihre Identität und erteilt ein Code Signaturzertifikat. Wenn Sie Ihr Zertifikat von einer seriösen Zertifizierungsstelle erwerben, können Sie Ihr Skript für Benutzer auf anderen Computern freigeben, auf denen Windows ausgeführt wird, da diese anderen Computer der Zertifizierungsstelle vertrauen.

- Zertifikate, die Sie erstellen: Sie können ein selbst signiertes Zertifikat erstellen, für das das Zertifikat von Ihrem Computer erstellt wird. Dieses Zertifikat ist kostenlos und ermöglicht das Schreiben, Signieren und Ausführen von Skripts auf Ihrem Computer. Ein Skript, das von einem selbst signierten Zertifikat signiert wurde, kann jedoch nicht auf anderen Computern ausgeführt werden.

In der Regel verwenden Sie ein selbst signiertes Zertifikat nur zum Signieren von Skripts, die Sie für Ihre eigene Verwendung schreiben, und zum Signieren von Skripts, die Sie aus anderen Quellen erhalten, die Sie als sicher überprüft haben. Sie eignet sich nicht für Skripts, die selbst in einem Unternehmen freigegeben werden.

Wenn Sie ein selbst signiertes Zertifikat erstellen, achten Sie darauf, dass Sie einen starken Schutz für private Schlüssel für Ihr Zertifikat aktivieren. Dadurch wird verhindert, dass böswillige Programme Skripts in Ihrem Namen signieren. Die Anweisungen sind am Ende dieses Themas enthalten.

## <a name="create-a-self-signed-certificate"></a>Erstellen eines selbstsignierten Zertifikats

Um ein selbst signiertes Zertifikat zu erstellen, verwenden Sie das- `New-SelfSignedCertificate` Cmdlet im PKI-Modul. Dieses Modul wird in PowerShell 3,0 eingeführt und ist in Windows 8 und Windows Server 2012 enthalten. Weitere Informationen finden Sie im Hilfethema für das `New-SelfSignedCertificate` Cmdlet.

Verwenden Sie zum Erstellen eines selbst signierten Zertifikats in früheren Versionen von Windows das Tool zur Erstellung von Zertifikaten `MakeCert.exe` . Dieses Tool ist im Microsoft .NET SDK (Version 1,1 und höher) und im Microsoft Windows SDK enthalten.

Weitere Informationen zur Syntax und den Parameter Beschreibungen des MakeCert.exe Tools finden Sie unter [Certificate Creation Tool (MakeCert.exe)](/previous-versions/dotnet/netframework-2.0/bfsktky3(v=vs.80)).

Führen Sie die folgenden Befehle in einem SDK-Eingabe Aufforderungs Fenster aus, um das MakeCert.exe Tool zum Erstellen eines Zertifikats zu verwenden.

Hinweis: mit dem ersten Befehl wird eine lokale Zertifizierungsstelle für Ihren Computer erstellt. Mit dem zweiten Befehl wird ein persönliches Zertifikat von der Zertifizierungsstelle generiert.

Hinweis: Sie können die Befehle genau so kopieren oder eingeben, wie Sie angezeigt werden. Es sind keine Substitutionen erforderlich, obwohl Sie den Zertifikat Namen ändern können.

```powershell
makecert -n "CN=PowerShell Local Certificate Root" -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -r -sv root.pvk root.cer `
-ss Root -sr localMachine

makecert -pe -n "CN=PowerShell User" -ss MY -a sha1 `
-eku 1.3.6.1.5.5.7.3.3 -iv root.pvk -ic root.cer
```

Mit dem MakeCert.exe Tool werden Sie zur Eingabe eines Kennworts für den privaten Schlüssel aufgefordert. Das Kennwort stellt sicher, dass niemand das Zertifikat ohne Ihre Zustimmung verwenden oder darauf zugreifen kann.
Erstellen Sie ein Kennwort, das Sie merken können. Sie verwenden dieses Kennwort später zum Abrufen des Zertifikats.

Um sicherzustellen, dass das Zertifikat ordnungsgemäß generiert wurde, verwenden Sie den folgenden Befehl, um das Zertifikat im Zertifikat Speicher des Computers zu erhalten. Sie finden keine Zertifikatsdatei im Dateisystem Verzeichnis.

Geben Sie an der PowerShell-Eingabeaufforderung Folgendes ein:

```powershell
Get-ChildItem cert:\CurrentUser\my -codesigning
```

Dieser Befehl verwendet den PowerShell-Zertifikat Anbieter, um Informationen zum Zertifikat anzuzeigen.

Wenn das Zertifikat erstellt wurde, zeigt die Ausgabe den Finger **Abdruck** an, der das Zertifikat in einer Anzeige identifiziert, die der folgenden ähnelt:

```Output
Directory: Microsoft.PowerShell.Security\Certificate::CurrentUser\My

Thumbprint                                Subject
----------                                -------
4D4917CB140714BA5B81B96E0B18AAF2C4564FDF  CN=PowerShell User ]
```

## <a name="sign-a-script"></a>Signieren eines Skripts

Nachdem Sie ein selbst signiertes Zertifikat erstellt haben, können Sie Skripts signieren. Wenn Sie die **AllSigned** -Ausführungs Richtlinie verwenden, können Sie durch Signieren eines Skripts das Skript auf Ihrem Computer ausführen.

Mit dem folgenden Beispielskript wird `Add-Signature.ps1` ein Skript signiert. Wenn Sie jedoch die **AllSigned** -Ausführungs Richtlinie verwenden, müssen Sie das Skript signieren, `Add-Signature.ps1` bevor Sie es ausführen.

> [!IMPORTANT]
> Das Skript muss mithilfe der ASCII-oder UTF8NoBOM-Codierung gespeichert werden. Sie können eine Skriptdatei signieren, die eine andere Codierung verwendet. Das Skript kann jedoch nicht ausgeführt werden, oder das Modul, das das Skript enthält, kann nicht importiert werden.

Um dieses Skript zu verwenden, kopieren Sie den folgenden Text in eine Textdatei, und benennen Sie ihn `Add-Signature.ps1` .

```powershell
## Signs a file
param([string] $file=$(throw "Please specify a filename."))
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature $file $cert
```

Geben Sie an `Add-Signature.ps1` der PowerShell-Eingabeaufforderung die folgenden Befehle ein, um die Skriptdatei zu signieren:

```powershell
$cert = @(Get-ChildItem cert:\CurrentUser\My -codesigning)[0]
Set-AuthenticodeSignature add-signature.ps1 $cert
```

Nachdem das Skript signiert wurde, können Sie es auf dem lokalen Computer ausführen. Das Skript kann jedoch nicht auf Computern ausgeführt werden, auf denen die PowerShell-Ausführungs Richtlinie eine digitale Signatur von einer vertrauenswürdigen Zertifizierungsstelle erfordert. Wenn Sie versuchen, zeigt PowerShell die folgende Fehlermeldung an:

```Output
The file C:\remote_file.ps1 cannot be loaded. The signature of the
certificate cannot be verified.
At line:1 char:15
+ .\ remote_file.ps1 <<<<
```

Wenn PowerShell diese Meldung anzeigt, wenn Sie ein Skript ausführen, das Sie nicht geschrieben haben, behandeln Sie die Datei, wie Sie alle nicht signierten Skripts behandeln würden. Überprüfen Sie den Code, um zu bestimmen, ob Sie dem Skript vertrauen können.

## <a name="enable-strong-private-key-protection-for-your-certificate"></a>Aktivieren des starken Schutzes für private Schlüssel für Ihr Zertifikat

Wenn Sie über ein privates Zertifikat auf Ihrem Computer verfügen, können schädliche Programme möglicherweise Skripts in Ihrem Namen signieren, wodurch PowerShell zum Ausführen autorisiert wird.

Um die automatisierte Signierung in Ihrem Namen zu verhindern, verwenden Sie den Zertifikat-Manager, `Certmgr.exe` um das Signaturzertifikat in eine Datei zu exportieren `.pfx` . Der Zertifikat-Manager ist im Microsoft .NET SDK, in der Microsoft Windows SDK und in Internet Explorer enthalten.

So exportieren Sie das Zertifikat:

1. Starten Sie den Zertifikat-Manager.
2. Wählen Sie das Zertifikat aus, das von PowerShell local certificate root ausgestellt wurde.
3. Klicken Sie auf exportieren, um den Zertifikat Export-Assistenten zu starten.
4. Wählen Sie ja, privaten Schlüssel exportieren aus, und klicken Sie dann auf Weiter.
5. Wählen Sie "starken Schutz aktivieren" aus.
6. Geben Sie ein Kennwort ein, und geben Sie es erneut ein, um zu bestätigen.
7. Geben Sie einen Dateinamen mit der Dateinamenerweiterung ". pfx" ein.
8. Klicken Sie auf Fertig stellen.

So importieren Sie das Zertifikat erneut:

1. Starten Sie den Zertifikat-Manager.
2. Klicken Sie auf Importieren, um den Zertifikat Import-Assistenten zu starten.
3. Öffnen Sie den Speicherort der PFX-Datei, die Sie während des Export Vorgangs erstellt haben.
4. Wählen Sie auf der Seite Kennwort die Option "starken Schutz für den privaten Schlüssel aktivieren", und geben Sie dann das Kennwort ein, das Sie während des Export Vorgangs zugewiesen haben
5. Wählen Sie den persönlichen Zertifikat Speicher aus.
6. Klicken Sie auf Fertig stellen.

## <a name="prevent-the-signature-from-expiring"></a>Verhindern, dass die Signatur abläuft

Die digitale Signatur in einem Skript ist gültig, bis das Signaturzertifikat abläuft oder solange ein Zeitstempel-Server überprüfen kann, ob das Skript signiert wurde, während das Signaturzertifikat gültig war.

Da die meisten Signatur Zertifikate nur ein Jahr lang gültig sind, stellt die Verwendung eines Zeitstempel Servers sicher, dass Benutzer Ihr Skript für viele Jahre verwenden können.

## <a name="see-also"></a>Weitere Informationen

[about_Execution_Policies](about_Execution_Policies.md)

[about_Profiles](about_Profiles.md)

[Get-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[Einführung in die Codesignatur](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537361(v=vs.85))
