---
ms.date: 09/19/2019
contributor: manikb
keywords: gallery,powershell,cmdlet,psget
title: Installieren von PowerShellGet
ms.openlocfilehash: 4a10699be9ff2b64e5848c6749bdd3dedf55e3c7
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "88162510"
---
# <a name="installing-powershellget"></a>Installieren von PowerShellGet

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a>PowerShellGet ist ein Modul, das zum Lieferumfang der folgenden Releases gehört:

- [Windows 10](https://www.microsoft.com/windows) oder höher
- [Windows Server 2016](/windows-server/windows-server) oder höher
- [Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) oder höher
- [PowerShell 6](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a>Herunterladen der neuesten Version aus dem PowerShell-Katalog

Bevor Sie **PowerShellGet** aktualisieren, sollten Sie immer den neuesten **NuGet**-Anbieter installieren. Führen Sie hierzu den folgenden Befehl in einer PowerShell-Sitzung mit erhöhten Rechten aus.

```powershell
Install-PackageProvider -Name NuGet -Force
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a>Für Systeme mit PowerShell 5.0 (oder höher) können Sie das neueste PowerShellGet-Modul installieren

Zum Installieren von PowerShellGet führen Sie unter Windows 10, Windows Server 2016 auf einem beliebigen System mit WMF 5.0 oder 5.1 oder auf einem beliebigen System mit PowerShell 6 den folgenden Befehl aus einer PowerShell-Sitzung mit erhöhten Rechten aus.

```powershell
Install-Module -Name PowerShellGet -Force
```

Verwenden Sie `Update-Module`, um neuere Versionen zu beziehen.

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a>Computer mit PowerShell 3.0 oder PowerShell 4.0

Diese Anweisungen gelten für Computer, auf denen die **PackageManagement-Vorschauversion** oder keine Version von **PowerShellGet** installiert ist.

Das Cmdlet `Save-Module` wird in beiden Anweisungssätzen verwendet. `Save-Module` lädt ein Modul und alle Abhängigkeiten aus einem registrierten Repository herunter und speichert sie. Die neueste Version des Moduls wird in einem bestimmten Pfad auf dem lokalen Computer gespeichert, wird aber nicht installiert. Kopieren Sie die in Modulen gespeicherten Ordner in `$env:ProgramFiles\WindowsPowerShell\Modules`, um die Module in PowerShell 3.0 oder 4.0 zu installieren.

Weitere Informationen finden Sie unter [Save-Module](/powershell/module/PowershellGet/Save-Module).

> [!NOTE]
> PowerShell 3.0 und PowerShell 4.0 unterstützten nur eine Version eines Moduls Ab PowerShell 5.0 werden Module in `<modulename>\<version>` installiert. Dadurch können Sie mehrere Versionen nebeneinander installieren. Nachdem Sie das Modul mithilfe von `Save-Module` heruntergeladen haben, müssen Sie wie in den nachfolgenden Anweisungen beschrieben die Dateien aus `<modulename>\<version>` in den Ordner `<modulename>` auf dem Zielcomputer kopieren.

#### <a name="preparatory-step-on-computers-running-powershell-30"></a>Vorbereitungsschritt für Computer, auf denen PowerShell 3.0 ausgeführt wird

Wenn Sie die Anweisungen in den folgenden Abschnitten ausführen, werden die Module im Verzeichnis `$env:ProgramFiles\WindowsPowerShell\Modules` installiert.
In PowerShell 3.0 wird dieses Verzeichnis in `$env:PSModulePath` standardmäßig nicht aufgeführt. Damit die Module automatisch geladen werden, müssen Sie das Verzeichnis hinzufügen. 

Öffnen Sie eine PowerShell-Sitzung mit erhöhten Rechten, und führen Sie den folgenden Befehl aus (der in künftigen Sitzungen übernommen wird):

```powershell
[Environment]::SetEnvironmentVariable(
  'PSModulePath',
  ((([Environment]::GetEnvironmentVariable('PSModulePath', 'Machine') -split ';') + "$env:ProgramFiles\WindowsPowerShell\Modules") -join ';'),
  'Machine'
)
```

#### <a name="computers-with-the-packagemanagement-preview-installed"></a>Computer mit installierter PackageManagement-Vorschauversion

> [!NOTE] 
> Die PackageManagement-Vorschauversion war eine herunterladbare Komponente, mit der PowerShellGet für die PowerShell-Versionen 3 und 4 verfügbar gemacht wurde. Diese Version ist jedoch nicht mehr verfügbar.
> Führen Sie `Get-Module -ListAvailable PowerShellGet` aus, um zu testen, ob diese Komponente auf einem bestimmten Computer installiert wurde.

1. Verwenden Sie aus einer PowerShell-Sitzung `Save-Module`, um die aktuelle Version von **PowerShellGet** herunterzuladen. Es werden zwei Ordner heruntergeladen: **PowerShellGet** und **PackageManagement**. Jeder Ordner enthält einen Unterordner mit einer Versionsnummer.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. Stellen Sie sicher, dass die Module **PowerShellGet** und **PackageManagement** nicht in anderen Prozessen geladen sind.

1. Öffnen Sie die PowerShell-Konsole erneut mit erhöhten Rechten, und führen Sie den folgenden Befehl aus:

   ```powershell
   'PowerShellGet', 'PackageManagement' | % { 
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     Remove-Item $targetDir\* -Recurse -Force
     Copy-Item C:\LocalFolder\$_\*\* $targetDir\ -Recurse -Force
   }
   ```

#### <a name="computers-without-powershellget"></a>Computer ohne PowerShellGet

Für Computer ohne installierte Version von **PowerShellGet** (Testen über `Get-Module -ListAvailable PowerShellGet`) wird zum Herunterladen der Module ein Computer benötigt, auf dem **PowerShellGet** installiert ist.

1. Verwenden Sie `Save-Module` auf dem Computer, auf dem **PowerShellGet** installiert ist, um die aktuelle Version von **PowerShellGet** herunterzuladen. Es werden zwei Ordner heruntergeladen: **PowerShellGet** und **PackageManagement**. Jeder Ordner enthält einen Unterordner mit einer Versionsnummer.

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. Kopieren Sie den entsprechenden Unterordner `<version>` in den Ordnern **PowerShellGet** und **PackageManagement**, und fügen Sie ihn auf dem Computer ohne **PowerShellGet**, der eine Sitzung mit erhöhten Rechten benötigt, in die Ordner `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` bzw. `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` ein.
   
1. Wenn Sie beispielsweise vom Zielcomputer über einen UNC-Pfad (z. B. `\\ws1\C$\LocalFolder`) auf den Downloadordner auf dem anderen Computer (z. B. `ws1`) zugreifen können, öffnen Sie eine PowerShell-Konsole mit erhöhten Rechten, und führen Sie den folgenden Befehl aus:

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     $null = New-Item -Type Directory -Force $targetDir
     $fromComputer = 'ws1'  # Specify the name of the other computer here.
     Copy-Item \\$fromComputer\C$\LocalFolder\$_\*\* $targetDir -Recurse -Force
     if (-not (Get-ChildItem $targetDir)) { Throw "Copying failed." }
   }
   ```
