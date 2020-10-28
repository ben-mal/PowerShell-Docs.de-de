---
ms.date: 09/13/2016
ms.topic: reference
title: Installieren eines PowerShell-Moduls
description: Installieren eines PowerShell-Moduls
ms.openlocfilehash: 3c7a4413168934ca4de1912c9615a6ae0fc45788
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645338"
---
# <a name="installing-a-powershell-module"></a>Installieren eines PowerShell-Moduls

Nachdem Sie das PowerShell-Modul erstellt haben, möchten Sie das Modul wahrscheinlich auf einem System installieren, damit Sie oder andere es benutzen können. Im Allgemeinen müssen Sie hierzu die Moduldateien (d. h. die PSM1- oder binäre Assemblydatei, das Modulmanifest und alle zugehörigen Dateien) in ein Verzeichnis auf diesem Computer kopieren. Bei einem sehr kleinen Projekt kann dies so einfach sein wie das Kopieren und Einfügen der Dateien mit Windows Explorer auf einem einzelnen Remotecomputer. Bei größeren Lösungen sollten Sie jedoch einen komplexeren Installationsprozess verwenden. Unabhängig davon, wie Sie Ihr Modul auf das System übertragen, kann PowerShell eine Reihe von Techniken verwenden, mit denen Benutzer Ihre Module suchen und verwenden können. Das Hauptproblem bei der Installation besteht daher darin, sicherzustellen, dass PowerShell das Modul finden kann. Weitere Informationen finden Sie unter [Importieren eines PowerShell-Moduls](./importing-a-powershell-module.md).

## <a name="rules-for-installing-modules"></a>Regeln für die Installation von Modulen

Die folgenden Informationen beziehen sich auf alle Module einschließlich derer, die Sie zur eigenen Verwendung erstellen, der Module, die Sie von anderen Anbietern erhalten, sowie Module, die Sie an andere Benutzer verteilen.

### <a name="install-modules-in-psmodulepath"></a>Installieren von Modulen in PSModulePath

Installieren Sie nach Möglichkeit alle Module in einem Pfad, der in der **PSModulePath** -Umgebungsvariablen aufgeführt ist, oder fügen Sie den Modulpfad dem Wert der **PSModulePath** -Umgebungsvariablen hinzu.

Die **PSModulePath** -Umgebungsvariable ($Env:PSModulePath) enthält die Speicherorte von Windows PowerShell-Modulen. Cmdlets suchen Module auf Basis des Werts dieser Umgebungsvariablen.

Standardmäßig enthält der Wert der Umgebungsvariablen **PSModulePath** die folgenden System- und Benutzermodulverzeichnisse. Sie können den Wert jedoch ergänzen und bearbeiten.

- `$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)

  > [!WARNING]
  > Dieser Speicherort ist für Module reserviert, die mit Windows ausgeliefert werden. Installieren Sie keine Module an diesem Speicherort.

- `$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Dokumente\WindowsPowerShell\Modules)

- `$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)

  Verwenden Sie einen der folgenden Befehle, um den Wert der **PSModulePath** -Umgebungsvariablen abzurufen.

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  Verwenden Sie das folgende Befehlsformat, um dem Wert der **PSModulePath** -Umgebungsvariablen einen Modulpfad hinzuzufügen. Dieses Format verwendet die **SetEnvironmentVariable** -Methode der **System.Environment** -Klasse, um der Umgebungsvariablen **PSModulePath** einen sitzungsunabhängigen Pfad hinzuzufügen.

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > Nachdem Sie **PSModulePath** den Pfad hinzugefügt haben, sollten Sie eine Nachricht über die Änderung an die Umgebung übertragen. Das Übertragen der Änderung ermöglicht anderen Anwendungen wie der Shell, die Änderung zu übernehmen. Um die Änderung zu übertragen, lassen Sie Ihren Produktinstallationscode eine **WM_SETTINGCHANGE** -Nachricht senden, wobei `lParam` auf die Zeichenfolge „Environment“ festgelegt ist. Stellen Sie sicher, dass Sie die Nachricht übertragen, nachdem der Modulinstallationscode **PSModulePath** aktualisiert hat.

### <a name="use-the-correct-module-directory-name"></a>Verwenden des richtigen Modulverzeichnisnamens

Ein wohlgeformtes Modul ist ein Modul, das in einem Verzeichnis gespeichert ist, dessen Name mit dem Basisnamen mindestens einer Datei im Modulverzeichnis identisch ist. Wenn ein Modul nicht wohlgeformt ist, wird es von Windows PowerShell nicht als Modul erkannt.

Der „Basisname“ einer Datei entspricht dem Dateinamen ohne Erweiterung. In einem wohlgeformten Modul muss der Name des Verzeichnisses, das die Moduldateien enthält, mit dem Basisnamen mindestens einer Datei im Modul identisch sein.

Beispielsweise hat das Verzeichnis im Fabrikam-Beispielmodul, das die Moduldateien enthält, den Namen „Fabrikam“, und mindestens eine Datei hat den Basisnamen „Fabrikam“. In diesem Fall haben „Fabrikam.psd1“ und „Fabrikam.dll“ beide den Basisnamen „Fabrikam“.

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a>Auswirkungen einer falschen Installation

Wenn das Modul nicht wohlgeformt und sein Speicherort nicht im Wert der **PSModulePath** -Umgebungsvariablen enthalten ist, funktionieren grundlegende Ermittlungsfeatures von Windows PowerShell nicht, z. B. die folgenden.

- Das Feature „Module Auto-Loading“ kann das Modul nicht automatisch importieren.

- Der `ListAvailable`-Parameter des [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)-Cmdlets kann das Modul nicht finden.

- Das [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)-Cmdlet kann das Modul nicht finden. Zum Importieren des Moduls müssen Sie den vollständigen Pfad zur Stammmoduldatei oder zur Modulmanifestdatei angeben.

  Weitere Features, wie z. B. die folgenden, funktionieren erst, wenn das Modul in die Sitzung importiert wird. In wohlgeformten Modulen in der **PSModulePath** -Umgebungsvariablen funktionieren diese Features auch dann, wenn das Modul nicht in die Sitzung importiert wird.

- Das [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command)-Cmdlet kann keine Befehle im Modul finden.

- [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)- und [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)-Cmdlet können Hilfe für das Modul nicht aktualisieren oder speichern.

- Das [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command)-Cmdlet kann die Befehle im Modul nicht finden und anzeigen.

  Die Befehle im Modul fehlen in Windows PowerShell Integrated Scripting Environment (ISE) im `Show-Command`-Fenster.

## <a name="where-to-install-modules"></a>Installationsort der Module

In diesem Abschnitt wird erläutert, wo Windows PowerShell-Module im Dateisystem installiert werden. Der Installationsort hängt davon ab, wie das Modul verwendet wird.

### <a name="installing-modules-for-a-specific-user"></a>Installieren von Modulen für einen bestimmten Benutzer

Wenn Sie ein eigenes Modul erstellen oder ein Modul von einer anderen Partei (z. B. einer Windows PowerShell-Communitywebsite) erhalten, und das Modul soll nur für Ihr Benutzerkonto verfügbar sein, installieren Sie das Modul in Ihrem benutzerspezifischen Modules-Verzeichnis.

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

Das benutzerspezifische Modules-Verzeichnis wird standardmäßig dem Wert der **PSModulePath** -Umgebungsvariablen hinzugefügt.

### <a name="installing-modules-for-all-users-in-program-files"></a>Installieren von Modulen für alle Benutzer in „Programme“

Wenn Sie möchten, dass ein Modul für alle Benutzerkonten auf dem Computer verfügbar ist, installieren Sie das Modul im Speicherort „Programme“.

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> Der Speicherort „Programme“ wird dem Wert der Umgebungsvariablen PSModulePath in Windows PowerShell 4.0 und höher standardmäßig hinzugefügt. Für frühere Versionen von Windows PowerShell können Sie den Speicherort „Programme“ (%ProgramFiles%\WindowsPowerShell\Modules) manuell erstellen und diesen Pfad der PSModulePath-Umgebungsvariablen wie oben beschrieben hinzufügen.

### <a name="installing-modules-in-a-product-directory"></a>Installieren von Modulen in einem Produktverzeichnis

Wenn Sie das Modul an andere Parteien verteilen, verwenden Sie den oben beschriebenen Standardspeicherort „Programme“, oder erstellen Sie ein eigenes unternehmens- oder produktspezifisches Unterverzeichnis des Verzeichnisses „%ProgramFiles%“.

Beispielsweise liefert das fiktive Unternehmen Fabrikam Technologies ein Windows PowerShell-Modul für sein Produkt Fabrikam Manager. Das Modulinstallationsprogramm erstellt im Produktunterverzeichnis „Fabrikam Manager“ ein Unterverzeichnis „Modules“.

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

Damit die Modulermittlungsfeatures des Windows PowerShell-Moduls das Fabrikam-Modul finden können, fügt das Fabrikam-Modulinstallationsprogramm den Speicherort des Moduls dem Wert der Umgebungsvariablen **PSModulePath** hinzu.

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a>Installieren von Modulen im Verzeichnis „Gemeinsame Dateien“

Wenn ein Modul von mehreren Komponenten oder Versionen eines Produkts verwendet wird, installieren Sie das Modul in einem modulspezifischen Unterverzeichnis des Unterverzeichnisses „%ProgramFiles%\Gemeinsame Dateien\Modules“.

Im folgenden Beispiel wird das Modul „Fabrikam“ in einem Unterverzeichnis „Fabrikam“ des Unterverzeichnisses `%ProgramFiles%\Common Files\Modules` installiert. Beachten Sie, dass sich jedes Modul in einem eigenen Unterverzeichnis des Unterverzeichnisses „Modules“ befindet.

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

Das Installationsprogramm stellt dann sicher, dass der Wert der **PSModulePath** -Umgebungsvariablen den Pfad des Unterverzeichnisses von „\Gemeinsame Dateien\Modules“ enthält.

```powershell
$m = $env:ProgramFiles + '\Common Files\Modules'
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$q = $p -split ';'
if ($q -notContains $m) {
    $q += ";$m"
}
$p = $q -join ';'
[Environment]::SetEnvironmentVariable("PSModulePath", $p)
```

## <a name="installing-multiple-versions-of-a-module"></a>Installieren mehrerer Versionen eines Moduls

Wenn Sie mehrere Versionen desselben Moduls installieren möchten, verwenden Sie das folgende Verfahren.

1. Erstellen Sie ein Verzeichnis für jede Version des Moduls. Fügen Sie die Versionsnummer in den Verzeichnisnamen ein.
2. Erstellen Sie für jede Version des Moduls ein Modulmanifest. Geben Sie in den Wert des Schlüssels **ModuleVersion** im Manifest die Modulversionsnummer ein. Speichern Sie die Manifestdatei (PSD1) im versionsspezifischen Verzeichnis für das Modul.
3. Fügen Sie den Stammordnerpfad des Moduls dem Wert der **PSModulePath** -Umgebungsvariablen hinzu, wie in den folgenden Beispielen gezeigt.

Um eine bestimmte Version des Moduls zu importieren, kann der Endbenutzer die Parameter `MinimumVersion` oder `RequiredVersion` des [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)-Cmdlets verwenden.

Wenn das Modul „Fabrikam“ beispielsweise in den Versionen 8.0 und 9.0 verfügbar ist, könnte die Fabrikam-Modulverzeichnisstruktur wie folgt aussehen.

 ```
C:\Program Files
Fabrikam Manager
  Fabrikam8
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "8.0")
      Fabrikam.dll (module assembly)
  Fabrikam9
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "9.0")
      Fabrikam.dll (module assembly)
```

Das Installationsprogramm fügt dem Wert der **PSModulePath** -Umgebungsvariablen beide Modulpfade hinzu.

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

Wenn diese Schritte abgeschlossen sind, ruft der **ListAvailable** -Parameter des [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)-Cmdlets beide Fabrikam-Module ab. Wenn Sie ein bestimmtes Modul importieren möchten, verwenden Sie die Parameter `MinimumVersion` oder `RequiredVersion` des [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)-Cmdlets.

Wenn beide Module in dieselbe Sitzung importiert werden und die Module Cmdlets mit identischen Namen enthalten, sind die zuletzt importierten Cmdlets in der Sitzung gültig.

## <a name="handling-command-name-conflicts"></a>Behandeln von Konflikten zwischen Befehlsnamen

Konflikte zwischen Befehlsnamen können auftreten, wenn die Befehle, die ein Modul exportiert, dieselben Namen wie die Befehle in der Benutzersitzung haben.

Wenn eine Sitzung zwei Befehle mit identischen Namen enthält, führt Windows PowerShell den Befehlstyp aus, der Vorrang hat. Wenn eine Sitzung zwei Befehle mit identischen Namen und identischem Typ enthält, führt Windows PowerShell den Befehl aus, der der Sitzung zuletzt hinzugefügt wurde. Um einen Befehl auszuführen, der nicht standardmäßig ausgeführt wird, können Benutzer den Befehlsnamen mit dem Modulnamen qualifizieren.

Wenn die Sitzung z. B. eine `Get-Date`-Funktion und das `Get-Date`-Cmdlet enthält, führt Windows PowerShell standardmäßig die Funktion aus. Um das Cmdlet auszuführen, stellen Sie dem Befehl den Namen des Moduls voran, z. B.:

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

Um Namenskonflikte zu verhindern, können Modulentwickler den **DefaultCommandPrefix** -Schlüssel im Modulmanifest verwenden, um ein Nounpräfix für alle Befehle anzugeben, die aus dem Modul exportiert werden.

Benutzer können den **Prefix** -Parameter des `Import-Module`-Cmdlets verwenden, um ein alternatives Präfix zu verwenden. Der Wert des **Prefix** -Parameters hat Vorrang vor dem Wert des **DefaultCommandPrefix** -Schlüssels.

## <a name="see-also"></a>Weitere Informationen

[about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[Schreiben eines Windows PowerShell-Moduls](./writing-a-windows-powershell-module.md)
