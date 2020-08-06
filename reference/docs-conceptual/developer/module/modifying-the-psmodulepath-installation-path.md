---
title: Ändern des psmodulepath-Installations Pfads | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 795f2bd52aeceddd3c0ca092d0c0cf2ef44bcf23
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784842"
---
# <a name="modifying-the-psmodulepath-installation-path"></a>Ändern des Installationspfads PSModulePath

Die `PSModulePath` Umgebungsvariable speichert die Pfade zu den Speicherorten der Module, die auf dem Datenträger installiert sind. PowerShell verwendet diese Variable, um Module zu suchen, wenn der Benutzer nicht den vollständigen Pfad zu einem Modul angibt. Die Pfade in dieser Variablen werden in der Reihenfolge durchsucht, in der Sie angezeigt werden.

Wenn PowerShell gestartet `PSModulePath` wird, wird als System Umgebungsvariable mit dem folgenden Standardwert erstellt: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` unter Windows und `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` unter Linux oder Mac sowie `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` für Windows PowerShell.

> [!NOTE]
> Der benutzerspezifische **CurrentUser** -Speicherort ist der `WindowsPowerShell\Modules` Ordner im Speicherort der **Dokumente** in Ihrem Benutzerprofil. Der spezifische Pfad dieses Standorts variiert je nach Version von Windows und ob Sie die Ordner Umleitung verwenden. Standardmäßig ist dieser Speicherort unter Windows 10 `$HOME\Documents\WindowsPowerShell\Modules` .

## <a name="to-view-the-psmodulepath-variable"></a>So zeigen Sie die psmodulepath-Variable an

Geben Sie den folgenden Befehl ein, um die in der Variablen angegebenen Pfade anzuzeigen `PSModulePath` :

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a>So fügen Sie der psmodulepath-Variablen Speicherorte hinzu

Um dieser Variablen Pfade hinzuzufügen, verwenden Sie eine der folgenden Methoden:

- Wenn Sie einen temporären Wert hinzufügen möchten, der nur für die aktuelle Sitzung verfügbar ist, führen Sie den folgenden Befehl in der Befehlszeile aus:

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- Wenn Sie einen persistenten Wert hinzufügen möchten, der immer verfügbar ist, wenn eine Sitzung geöffnet wird, fügen Sie den obigen Befehl einer PowerShell-Profil Datei ( `$PROFILE` ) hinzu >

  Weitere Informationen zu Profilen finden Sie unter [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).

- Um der Registrierung eine persistente Variable hinzuzufügen, erstellen Sie eine neue Benutzer Umgebungsvariable `PSModulePath` mit dem Namen, indem Sie im Dialogfeld **System Eigenschaften** den Umgebungsvariablen-Editor verwenden.

- Verwenden Sie die .NET-Methode " [stenvironmentvariable](/dotnet/api/system.environment.setenvironmentvariable) " in der [System. Environment](/dotnet/api/system.environment) -Klasse, um eine persistente Variable mithilfe eines Skripts hinzuzufügen. Mit dem folgenden Skript wird z. b `C:\Program Files\Fabrikam\Module` . der Pfad zum Wert der `PSModulePath` Umgebungsvariablen für den Computer hinzugefügt. Um den Pfad zur Benutzer `PSModulePath` Umgebungsvariablen hinzuzufügen, legen Sie für das Ziel den Wert "User" fest.

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a>So entfernen Sie Speicherorte aus dem psmodulepath

Sie können Pfade aus der Variablen entfernen, indem Sie ähnliche Methoden verwenden: beispielsweise `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` wird der Pfad " **c:\modulepath** " aus der aktuellen Sitzung entfernt.

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Moduls](./writing-a-windows-powershell-module.md)

[about_Modules](/powershell/module/microsoft.powershell.core/about/about_modules)
