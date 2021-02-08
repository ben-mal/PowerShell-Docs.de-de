---
title: Installieren von PowerShell unter Windows
description: Informationen zur Installation von PowerShell unter Windows
ms.date: 02/02/2021
ms.openlocfilehash: befc5ff156cb7c3843d89e394e903778682ba28e
ms.sourcegitcommit: 40b6d8e9b6d791ac69e2ff85224e900b21552bc1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "99536490"
---
# <a name="installing-powershell-on-windows"></a>Installieren von PowerShell unter Windows

Es gibt mehrere Möglichkeiten zum Installieren von PowerShell unter Windows.

## <a name="prerequisites"></a>Voraussetzungen

Die neueste Version von PowerShell wird unter Windows 7 SP1, Windows Server 2008 R2 und höheren Versionen unterstützt.

Zum Aktivieren des PowerShell-Remoting über WSMan müssen die folgenden Voraussetzungen erfüllt sein:

- [Universal C-Runtime](https://www.microsoft.com/download/details.aspx?id=50410) muss unter Windows-Versionen vor Windows 10 installiert sein. Die Runtime ist über einen direkten Download oder Windows-Update verfügbar. Auf vollständig gepatchten Systemen ist dieses Paket bereits installiert.
- Installieren Sie Windows Management Framework (WMF) 4.0 oder höher auf Windows 7 und Windows Server 2008 R2. Weitere Informationen zu WMF erhalten Sie in der [WMF-Übersicht](/powershell/scripting/wmf/overview).

## <a name="download-the-installer-package"></a>Herunterladen des Installationspakets

Laden Sie zum Installieren von PowerShell unter Windows das [neueste][] Installationspaket von GitHub herunter. Sie können auch die neueste [Vorschauversion][] herunterladen. Scrollen Sie auf der Seite „Release“ nach unten zum Abschnitt **Assets**. Der Abschnitt **Assets** ist möglicherweise zugeklappt, sodass Sie darauf klicken müssen, um ihn aufzuklappen.

## <a name="installing-the-msi-package"></a><a id="msi" />Installieren des MSI-Pakets

Die MSI-Datei sieht so aus: `PowerShell-<version>-win-<os-arch>.msi`. Beispiel:

- `PowerShell-7.1.1-win-x64.msi`
- `PowerShell-7.1.1-win-x86.msi`

Sobald sie heruntergeladen wurde, führen Sie den Installer mit einem Doppelklick aus und befolgen die Anweisungen.

Das Installationsprogramm erstellt eine Verknüpfung im Windows-Startmenü.

- Das Paket wird standardmäßig unter `$env:ProgramFiles\PowerShell\<version>` installiert
- Sie können PowerShell über das Startmenü oder über `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` starten

> [!NOTE]
> PowerShell 7.1 wird in ein neues Verzeichnis installiert und parallel mit Windows PowerShell 5.1 ausgeführt.
> PowerShell 7.1 ist ein direktes Upgrade, das PowerShell 6.x. oder PowerShell 7.0 ersetzt.
>
> - PowerShell 7.1 wird in `$env:ProgramFiles\PowerShell\7` installiert.
> - Der Ordner `$env:ProgramFiles\PowerShell\7` wird `$env:PATH` hinzugefügt.
> - Der Ordner `$env:ProgramFiles\PowerShell\6` wird gelöscht.
>
> Wenn PowerShell 7.1 parallel mit anderen Versionen ausgeführt werden muss, installieren Sie die andere Version mit der Methode unter [Installieren des ZIP-Pakets](#zip) in einem anderen Ordner.

### <a name="administrative-install-from-the-command-line"></a>Administrative Installation über die Befehlszeile

MSI-Pakete können über die Befehlszeile installiert werden, sodass Administratoren Pakete ohne Benutzerinteraktion bereitstellen können. Das MSI-Paket enthält die folgenden Eigenschaften zum Steuern der Installationsoptionen:

- **ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Diese Eigenschaft steuert die Option zum Hinzufügen des Elements **PowerShell öffnen** zum Kontextmenü im Windows-Explorer.
- **ADD_FILE_CONTEXT_MENU_RUNPOWERSHELL**: Diese Eigenschaft steuert das Hinzufügen der Option **Mit PowerShell ausführen** zum Kontextmenü im Windows-Explorer.
- **ENABLE_PSREMOTING** – Diese Eigenschaft steuert die Option zum Aktivieren von PowerShell-Remoting während der Installation.
- **REGISTER_MANIFEST** – Diese Eigenschaft steuert die Option zum Registrieren des Manifests für Windows-Ereignisprotokollierung.

Das folgenden Beispiel zeigt, wie PowerShell mit allen aktivierten Installationsoptionen im Hintergrund installiert wird.

```powershell
msiexec.exe /package PowerShell-7.1.1-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

Eine vollständige Liste der Befehlszeilenoptionen für `Msiexec.exe` finden Sie unter [Befehlszeilenoptionen](/windows/desktop/Msi/command-line-options).

### <a name="registry-keys-created-during-installation"></a>Während der Installation erstellte Registrierungsschlüssel

Ab PowerShell 7.1 erstellt das MSI-Paket Registrierungsschlüssel, die den Installationsort und die PowerShell-Version speichern. Diese Werte befinden sich in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`. Der Wert von `<GUID>` ist für jeden Buildtyp (Release oder Vorschau), Hauptversion und Architektur eindeutig.

|    Release    | Aufbau |                                          Registrierungsschlüssel                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| Release 7.1.x |     x86      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| Release 7.1.x |     x64      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| Vorschau 7.1.x |     x86      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| Vorschau 7.1.x |     x64      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

Dies kann von Administratoren und Entwicklern verwendet werden, um den Pfad zu PowerShell zu finden. Die `<GUID>`-Werte sind für alle Vorschau- und Nebenversionen identisch. Die `<GUID>`-Werte werden für jede Hauptversion geändert.

## <a name="installing-the-zip-package"></a><a id="zip" />Installieren des ZIP-Pakets

Binäre PowerShell ZIP-Archive werden zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu ermöglichen. Laden Sie eines der folgenden ZIP-Archive von der Seite [Releases][Releases] herunter.

- PowerShell-7.1.1-win-x64.zip
- PowerShell-7.1.1-win-x86.zip
- PowerShell-7.1.1-win-arm64.zip
- PowerShell-7.1.1-win-arm32.zip

Je nachdem, wie Sie die Datei herunterladen, müssen Sie die Blockierung der Datei mit dem Cmdlet `Unblock-File` aufheben. Entpacken Sie den Inhalt an den Speicherort Ihrer Wahl, und führen Sie `pwsh.exe` von dort aus. Anders als bei der Installation der MSI-Pakete erfolgt bei der Installation des ZIP-Archivs keine Prüfung auf Voraussetzungen. Damit Remoting über WSMan einwandfrei funktioniert, müssen die [Voraussetzungen](#prerequisites) unbedingt erfüllt sein.

Installieren Sie mit dieser Methode die ARM-basierte Version von PowerShell auf Computern wie Microsoft Surface Pro X. Die besten Ergebnisse erzielen Sie, wenn Sie PowerShell im Ordner `$env:ProgramFiles\PowerShell\7` installieren.

## <a name="deploying-on-windows-10-iot-enterprise"></a>Bereitstellung unter Windows 10 IoT Enterprise

Bei Windows 10 IoT Enterprise ist Windows PowerShell bereits im Funktionsumfang enthalten, sodass PowerShell 7 bereitgestellt werden kann.

1. Erstellen Sie `PSSession` auf dem Zielgerät.

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. Kopieren Sie das ZIP-Paket auf das Gerät.

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. Stellen Sie eine Verbindung mit dem Gerät her, und erweitern Sie das Archiv.

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. Richten Sie Remoting für PowerShell 7 ein.

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. Stellen Sie eine Verbindung mit dem PowerShell 7-Endpunkt auf dem Gerät her.

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a>Bereitstellung unter Windows 10 IoT Core

Bei Windows 10 IoT Core wird Windows PowerShell hinzugefügt, wenn Sie das Feature _IOT_POWERSHELL_ aufnehmen. Über dieses Feature kann PowerShell 7 bereitgestellt werden. Die oben beschriebenen Schritte für Windows 10 IoT Enterprise können auch für IoT Core ausgeführt werden.

Verwenden Sie zum Hinzufügen der aktuellen PowerShell-Version im Image den Befehl [Import-PSCoreRelease][]. Mit diesem Befehl wird das Paket im Arbeitsbereich eingefügt und das Feature _OPENSRC_POWERSHELL_ zu Ihrem Image hinzugefügt.

> [!NOTE]
> Bei der ARM64-Architektur wird Windows PowerShell nicht hinzugefügt, wenn Sie _IOT_POWERSHELL_ einfügen. Daher funktioniert die ZIP-basierte Installation nicht. Sie müssen den Befehl `Import-PSCoreRelease` verwenden, um ihn im Image hinzuzufügen.

## <a name="deploying-on-nano-server"></a>Bereitstellen auf Nano Server

Diese Anweisungen gehen davon aus, dass der Nano Server ein „monitorloses“ Betriebssystem ist, unter dem bereits eine Version von PowerShell ausgeführt wird. Weitere Informationen finden Sie in der [Dokumentation zu Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).

PowerShell-Binärdateien können auf zwei verschiedene Arten bereitgestellt werden.

1. Offline: Binden Sie die Nano Server-VHD ein, und entpacken Sie den Inhalt der ZIP-Datei an dem von Ihnen gewünschten Speicherort in dem eingebundenen Image.
1. Online: Übertragen Sie die ZIP-Datei über eine PowerShell-Sitzung, und entpacken Sie sie an dem von Ihnen gewünschten Speicherort.

In beiden Fällen benötigen Sie das ZIP-Releasepaket für Windows 10 x64. Führen Sie die Befehle in einer „Administrator“-Instanz von PowerShell aus.

### <a name="offline-deployment-of-powershell"></a>Offlinebereitstellung von PowerShell

1. Verwenden Sie Ihr bevorzugtes ZIP-Hilfsprogramm, um das Paket in ein Verzeichnis im eingebundenen Nano Server-Image zu entpacken.
1. Heben Sie die Bereitstellung des Images auf, und starten Sie es.
1. Stellen Sie eine Verbindung mit der integrierten Instanz von Windows PowerShell her.
1. Befolgen Sie die Anweisungen, um einen Remoting-Endpunkt mithilfe der [„Andere Instanz-Methode“][] zu erstellen.

### <a name="online-deployment-of-powershell"></a>Onlinebereitstellung von PowerShell

Stellen Sie PowerShell mithilfe der folgenden Schritte für Nano Server bereit.

- Herstellen einer Verbindung mit der integrierten Instanz von Windows PowerShell

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- Kopieren Sie die Datei in die Nano Server-Instanz.

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- Geben Sie die Sitzung ein.

  ```powershell
  Enter-PSSession $session
  ```

- Extrahieren Sie die ZIP-Datei.

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- Befolgen Sie die Anweisungen, wenn Sie auf WSMan basierendes Remoting verwenden möchten, um einen Remoting-Endpunkt mithilfe der [„Andere Instanz-Methode“][] zu erstellen.

## <a name="install-as-a-net-global-tool"></a>Installieren als globales .NET-Tool

Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.

```
dotnet tool install --global PowerShell
```

Der .NET-Toolinstaller fügt `$env:USERPROFILE\dotnet\tools` Ihrer `$env:PATH`-Umgebungsvariablen hinzu. Die aktuell ausgeführte Shell verfügt jedoch nicht über die aktualisierte Umgebungsvariable `$env:PATH`. Sie können PowerShell über eine neue Shell starten, indem Sie `pwsh` eingeben.

## <a name="install-powershell-via-winget"></a>Installieren von PowerShell über Winget

Mit dem Befehlszeilentool `winget` können Entwickler Anwendungen auf Windows 10-Computern ermitteln, installieren, aktualisieren, entfernen und konfigurieren. Dieses Tool ist die Clientschnittstelle für den Windows-Paket-Manager-Dienst.

> [!NOTE]
> Das `winget`-Tool befindet sich zurzeit in der Vorschau. Zurzeit sind nicht alle geplanten Funktionen verfügbar.
> Diese Methode sollten Sie nicht in einem Produktionsbereitstellungsszenario verwenden. Eine Liste der Systemanforderungen und Installationsanweisungen finden Sie in der Dokumentation zu [winget].

Die folgenden Befehle können verwendet werden, um PowerShell mithilfe der veröffentlichten `winget`-Pakete zu installieren:

1. Suchen nach der neuesten Version von PowerShell

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.1.1
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.1-preview.5
   ```

1. Installieren einer PowerShell-Version mithilfe des `--exact`-Parameters

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="installing-from-the-microsoft-store"></a><a id="msix" />Installieren über den Microsoft Store

PowerShell 7.1 wurde im Microsoft Store veröffentlicht. Die PowerShell-Version finden Sie auf der Website von [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) oder in der Store-Anwendung unter Windows.

Vorteile des Microsoft Store-Pakets:

- Direkt in Windows 10 integrierte automatische Updates
- Integration in andere Softwareverteilungsmechanismen wie Intune und SCCM

Einschränkungen:

MSIX-Pakete werden in einer Sandbox für Anwendungen ausgeführt, die den Zugriff auf einige Dateisystem- und Registrierungsspeicherorte virtualisiert.

- Alle Registrierungsänderungen unter HKEY_CURRENT_USER werden beim Schreiben in einen privaten Speicherort benutzer- und App-spezifisch kopiert. Diese Werte sind daher für andere Anwendungen nicht verfügbar.
- Alle in `$PSHOME` gespeicherten Konfigurationseinstellungen auf Systemebene lassen sich nicht ändern. Dies schließt die WSMAN-Konfiguration ein. Dadurch wird verhindert, dass Remotesitzungen eine Verbindung mit auf Store basierenden Installationen von PowerShell herstellen. Konfigurationen auf Benutzerebene und SSH-Remoting werden unterstützt.

Weitere Informationen finden Sie unter [Grundlegendes zur Funktionsweise von App-Paketen unter Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).

### <a name="using-the-msix-package"></a>Verwenden des MSIX-Pakets

> [!NOTE]
> Die Vorschaubuilds von PowerShell enthalten ein MSIX-Paket. Das MSIX-Paket wird nicht offiziell unterstützt. Das Paket wird zu Testzwecken in der Vorschauphase erstellt.

Für eine manuelle Installation des MSIX-Pakets auf einem Windows 10-Client laden Sie das MSIX-Paket von der GitHub-Seite mit den [Releases][Releases] herunter. Scrollen Sie nach unten zum Abschnitt **Assets** des Release, das Sie installieren möchten. Der Abschnitt „Assets“ ist möglicherweise reduziert, sodass Sie klicken müssen, um ihn zu erweitern.

Die MSIX-Datei sieht so aus: `PowerShell-<version>-win-<os-arch>.msix`

Zum Installieren des Pakets müssen Sie das Cmdlet `Add-AppxPackage` verwenden:

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="how-to-create-a-remoting-endpoint"></a>Vorgehensweise zum Erstellen eines Remoting-Endpunkts

PowerShell unterstützt das PowerShell-Remotingprotokoll (PSRP) über WSMan und SSH. Weitere Informationen finden Sie unter

- [SSH-Remoting in PowerShell Core][ssh-remoting]
- [WSMan-Remoting in PowerShell Core][wsman-remoting]

## <a name="upgrading-an-existing-installation"></a>Upgrade einer vorhandenen Installation

Für optimale Ergebnisse beim Upgrade sollten Sie dieselbe Installationsmethode verwenden, die Sie bei der ersten Installation von PowerShell verwendet haben. Bei jeder Installationsmethode wird PowerShell an einem anderen Speicherort installiert. Wenn Sie nicht sicher sind, wie PowerShell installiert wurde, können Sie den Speicherort der Installation mit den Paketinformationen in diesem Artikel vergleichen. Wenn die Installation über das MSI-Paket erfolgt ist, finden Sie diese Informationen in der Systemsteuerung unter **Programme und Features**.

## <a name="installation-support"></a>Installationsunterstützung

Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden. Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung. Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.

<!-- link references -->

[Vorschauversion]: https://aka.ms/powershell-release?tag=preview
[Neueste]: https://aka.ms/powershell-release?tag=stable
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
[„andere Instanztechnik“]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
[Import-PSCoreRelease]: https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease
