---
ms.date: 06/22/2020
keywords: dsc,powershell,configuration,service,setup
title: Schreiben, Kompilieren und Anwenden einer Konfiguration
ms.openlocfilehash: 9acb2db882795d7150326fadb2964deb1105b2cc
ms.sourcegitcommit: 7eea0885dd7ac90ab36e5664501438a292217f7f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85295674"
---
# <a name="write-compile-and-apply-a-configuration"></a>Schreiben, Kompilieren und Anwenden einer Konfiguration

> Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0

Diese Übung führt Sie von Anfang bis Ende durch das Erstellen und Anwenden einer Desired State Configuration (DSC)-Konfiguration. Anhand des folgenden Beispiels erfahren Sie, wie Sie eine einfache Konfiguration schreiben und anwenden. Mit der Konfiguration wird sichergestellt, dass eine „HelloWorld.txt“-Datei auf Ihrem lokalen Computer vorhanden ist.
Wenn Sie die Datei löschen, erstellt DSC sie beim nächsten Update neu.

Eine Übersicht über DSC und die Funktionsweise finden Sie unter [Desired State Configuration Overview for Developers (Desired State Configuration (DSC): Übersicht für Entwickler)](../overview/overview.md).

## <a name="requirements"></a>Requirements (Anforderungen)

Sie benötigen einen Computer mit PowerShell 4.0 oder höher, um dieses Beispiel auszuführen.

## <a name="write-the-configuration"></a>Schreiben der Konfiguration

Eine DSC-[Konfiguration](configurations.md) ist eine spezielle PowerShell-Funktion, die definiert, wie Sie einen oder mehrere Zielcomputer (Knoten) konfigurieren möchten.

Geben Sie Folgendes in die PowerShell ISE oder einen anderen PowerShell-Editor ein:

```powershell
Configuration HelloWorld {

    # Import the module that contains the File resource.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets to compile MOF files for, when
    # this configuration is executed.
    Node 'localhost' {

        # The File resource can ensure the state of files, or copy them from a
        # source to a destination with persistent updates.
        File HelloWorld {
            DestinationPath = "C:\Temp\HelloWorld.txt"
            Ensure = "Present"
            Contents   = "Hello World from DSC!"
        }
    }
}
```

> [!IMPORTANT]
> In komplexeren Szenarien, in denen mehrere Module importiert werden müssen, damit Sie mit vielen DSC-Ressourcen in der gleichen Konfiguration arbeiten können, geben Sie jedes Modul mit `Import-DscResource` in einer separaten Zeile an. Dies lässt sich in der Quellcodeverwaltung leichter nachverfolgen und ist erforderlich, wenn Sie in Azure State Configuration mit DSC arbeiten.
>
> ```powershell
>  Configuration HelloWorld {
>
>   # Import the module that contains the File resource.
>   Import-DscResource -ModuleName PsDesiredStateConfiguration
>   Import-DscResource -ModuleName xWebAdministration
>
> ```

Speichern Sie die Datei als „HelloWorld.ps1“.

Das Definieren einer Konfiguration entspricht dem Definieren einer Funktion. Der **Node**-Block gibt den zu konfigurierenden Zielknoten an, in diesem Fall `localhost`.

Die Konfiguration ruft eine [Ressource](../resources/resources.md) auf, die `File`-Ressource. Ressourcen stellen sicher, dass sich der Zielknoten im durch die Konfiguration definierten Zustand befindet.

## <a name="compile-the-configuration"></a>Kompilieren der Konfiguration

Damit eine DSC-Konfiguration auf einem Knoten angewendet werden kann, muss sie zunächst in eine MOF-Datei kompiliert werden. Durch Ausführen der Konfiguration wie eine Funktion wird vom `Node`-Block eine `.mof`-Datei für jeden Knoten definiert. Sie müssen das Skript `HelloWorld.ps1` per _dot source_ im aktuellen Bereich aufrufen, um die Konfiguration auszuführen. Weitere Informationen hierzu finden Sie unter [about_Scripts (Informationen zu Skripts)](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).

<!-- markdownlint-disable MD038 -->
Das Skript `HelloWorld.ps1` rufen Sie per _dot source_ auf, indem Sie den Pfad zum Speicherort nach dem `. ` (Punkt gefolgt von einem Leerzeichen) eingeben. Anschließend können Sie Ihre Konfiguration ausführen, indem Sie sie wie eine Funktion aufrufen. Sie könnten auch die Konfigurationsfunktion unten im Skript aufrufen, sodass „dot-source“ nicht erforderlich ist.
<!-- markdownlint-enable MD038 -->

```powershell
. C:\Scripts\HelloWorld.ps1
HelloWorld
```

Die folgende Ausgabe wird generiert:

```Output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a>Anwenden der Konfiguration

Nun, da Sie die kompilierte MOF-Dateien haben, können Sie die Konfiguration auf den Zielknoten (in diesem Fall der lokale Computer) anwenden, indem Sie das Cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) aufrufen.

Das Cmdlet `Start-DscConfiguration` fordert den [lokalen Konfigurations-Manager](../managing-nodes/metaConfig.md) (die DSC-Engine) dazu auf, die Konfiguration anzuwenden. Der LCM übernimmt das Aufrufen der DSC-Ressourcen, um die Konfiguration anzuwenden.

Verwenden Sie den folgenden Code, um das Cmdlet `Start-DSCConfiguration` auszuführen. Geben Sie für den Parameter **Path** den Verzeichnispfad an, unter dem `localhost.mof` gespeichert ist. Das Cmdlet `Start-DSCConfiguration` durchsucht das angegebene Verzeichnis auf Dateien des Typs `<computername>.mof`. Das Cmdlet `Start-DSCConfiguration` versucht, alle gefundenen `.mof`-Dateien auf den vom Dateinamen angegeben `computername` („localhost“, „server01“, „dc-02“ usw.) anzuwenden.

> [!NOTE]
> Wenn der Parameter `-Wait` nicht festgelegt wird, erstellt `Start-DSCConfiguration` einen Hintergrundauftrag zum Ausführen des Vorgangs. Durch Festlegen des `-Verbose`-Parameters können Sie die **ausführliche** Ausgabe des Vorgangs anzeigen. `-Wait` und `-Verbose` sind optionale Parameter.

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a>Testen der Konfiguration

Sobald das Cmdlet `Start-DSCConfiguration` abgeschlossen ist, sollte Ihnen eine Datei `HelloWorld.txt` am von Ihnen festgelegten Speicherort angezeigt werden. Sie können die Inhalte mit dem Cmdlet [Get-Content](/powershell/module/microsoft.powershell.management/get-content) überprüfen.

Sie können den aktuellen Status auch mit [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)_testen_.

Die Ausgabe muss `True` sein, wenn der Knoten derzeit der angewendeten Konfiguration entspricht.

```powershell
Test-DSCConfiguration
```

```Output
True
```

```powershell
Get-Content -Path C:\Temp\HelloWorld.txt
```

```Output
Hello World from DSC!
```

## <a name="re-applying-the-configuration"></a>Erneutes Anwenden der Konfiguration

Sie können die Textdatei entfernen, die von Ihrer Konfiguration erstellt wurde, um die erneute Anwendung Ihrer Konfiguration anzuzeigen. Verwenden Sie dann das Cmdlet `Start-DSCConfiguration` mit dem Parameter `-UseExisting`. Der Parameter `-UseExisting` weist `Start-DSCConfiguration` an, die Datei „current.mof“ erneut anzuwenden, die die letzte erfolgreich angewendete Konfiguration darstellt.

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a>Nächste Schritte

- Weiteren Informationen zu DSC-Konfigurationen erhalten Sie unter [DSC-Konfigurationen](configurations.md).
- Welche DSC-Ressourcen verfügbar sind und wie Sie benutzerdefinierte DSC-Ressourcen erstellen erfahren Sie unter [DSC-Ressourcen](../resources/resources.md).
- DSC-Konfigurationen und -Ressourcen finden Sie unter [PowerShell-Katalog](https://www.powershellgallery.com/).
