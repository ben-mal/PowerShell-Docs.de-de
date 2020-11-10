---
description: Bietet eine kurze Einführung in die PowerShell DSC-Funktion (DSC).
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_desiredstateconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_DesiredStateConfiguration
ms.openlocfilehash: 5d088934ffc953ad19be401bce72f6287f0fde07
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387021"
---
# <a name="about_desiredstateconfiguration"></a>about_DesiredStateConfiguration

## <a name="short-description"></a>KURZE BESCHREIBUNG

Bietet eine kurze Einführung in die PowerShell DSC-Funktion (DSC).

## <a name="long-description"></a>LANGE BESCHREIBUNG

DSC ist eine Verwaltungsplattform in PowerShell, die die Bereitstellung und Verwaltung von Konfigurationsdaten für Software Dienste und die Verwaltung der Umgebung ermöglicht, in der diese Dienste ausgeführt werden.

DSC stellt eine Reihe von PowerShell-Spracherweiterungen, neue Cmdlets und Ressourcen bereit, mit denen Sie deklarativ angeben können, wie der Zustand ihrer Softwareumgebung konfiguriert werden soll. DSC bietet außerdem eine Möglichkeit zum Warten und Verwalten vorhandener Konfigurationen.

DSC wird in PowerShell 4,0 eingeführt.

Ausführliche Informationen zu DSC finden Sie unter [PowerShell](/powershell/scripting/dsc/overview/overview)DSC (DSC).

## <a name="developing-dsc-resources-with-classes"></a>Entwickeln von DSC-Ressourcen mit Klassen

Ab PowerShell 5,0 können Sie DSC-Ressourcen mithilfe von Klassen entwickeln.
Weitere Informationen finden Sie unter [about_Classes](about_Classes.md)und [Schreiben einer benutzerdefinierten DSC-Ressource mit PowerShell-Klassen](/powershell/scripting/dsc/resources/authoringresourceclass).

## <a name="using-dsc"></a>Verwenden von DSC

Um DSC zum Konfigurieren Ihrer Umgebung zu verwenden, definieren Sie zunächst einen PowerShell-Skriptblock mithilfe des Schlüssel Worts "Configuration", gefolgt von einem Bezeichner, auf den wiederum das Paar der geschweiften Klammern folgt, die den Block begrenzen. Innerhalb des Konfigurations Blocks können Sie Knoten Blöcke definieren, die den gewünschten Konfigurations Zustand für jeden Knoten (Computer) in der Umgebung angeben. Ein Node-Block beginnt mit dem Node-Schlüsselwort, gefolgt vom Namen des Ziel Computers, bei dem es sich um eine Variable handeln kann. Wechseln Sie nach dem Computernamen zu den geschweiften Klammern, die den Knoten Block begrenzen. Innerhalb des Knoten Blocks können Sie Ressourcenblöcke definieren, um bestimmte Ressourcen zu konfigurieren. Ein Ressourcenblock beginnt mit dem Typnamen der Ressource, gefolgt von dem Bezeichner, den Sie für diesen Block angeben möchten, gefolgt von den geschweiften Klammern, die den Block begrenzen, wie im folgenden Beispiel gezeigt.

```powershell
Configuration MyWebConfig {
    # Parameters are optional
    param ($MachineName, $WebsiteFilePath)
    # A Configuration block can have one or more Node blocks
    Node $MachineName
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            # To ensure that the role is not installed, set Ensure to "Absent"
            Ensure = "Present"
            Name = "Web-Server" # Use the Name property from Get-WindowsFeature
        }

        # You can use the File resource to create files and folders
        # "WebDirectory" is the name you want to use to refer to this instance
        File WebDirectory
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath
            DestinationPath = "C:\inetpub\wwwroot"

            # Ensure that the IIS block is successfully run first before
            # configuring this resource
            DependsOn = "[WindowsFeature]IIS"  # Use for dependencies
        }
    }
}
```

Um eine Konfiguration zu erstellen, rufen Sie den Konfigurations Block auf dieselbe Weise auf wie Sie eine PowerShell-Funktion aufrufen, und übergeben Sie dabei alle erwarteten Parameter, die Sie möglicherweise definiert haben (zwei im obigen Beispiel). In diesem Fall gilt beispielsweise Folgendes:

```powershell
MyWebConfig -MachineName "TestMachine" -WebsiteFilePath `
  "\\filesrv\WebFiles" -OutputPath "C:\Windows\system32\temp"
# OutputPath is optional
```

Dadurch wird eine MOF-Datei pro Knoten an dem von Ihnen angegebenen Pfad generiert. Diese MOF-Dateien geben die gewünschte Konfiguration für jeden Knoten an. Verwenden Sie als nächstes das folgende Cmdlet, um die MOF-Konfigurationsdateien zu analysieren, die einzelnen Knoten mit der entsprechenden Konfiguration zu übertragen und diese Konfigurationen zu implementieren. Beachten Sie, dass Sie keine separate MOF-Datei für klassenbasierte DSC-Ressourcen erstellen müssen.

```powershell
Start-DscConfiguration -Verbose -Wait -Path "C:\Windows\system32\temp"
```

## <a name="using-dsc-to-maintain-configuration-state"></a>Verwalten des Konfigurations Status mithilfe von DSC

Bei DSC ist die Konfiguration idempotent. Dies bedeutet Folgendes: Wenn Sie DSC verwenden, um dieselbe Konfiguration mehrmals durchzusetzen, ist der resultierende Konfigurations Status immer identisch. Wenn Sie davon ausgehen, dass ein Knoten in Ihrer Umgebung möglicherweise vom gewünschten Zustand der Konfiguration abweicht, können Sie dieselbe DSC-Konfiguration erneut ausführen, um Sie wieder in den gewünschten Zustand zu bringen. Sie müssen das Konfigurationsskript nicht so ändern, dass nur die Ressourcen adressiert werden, deren Zustand vom gewünschten Zustand abweicht.

Im folgenden Beispiel wird gezeigt, wie Sie überprüfen können, ob der tatsächliche Status der Konfiguration auf einem bestimmten Knoten von der letzten auf dem Knoten ersetzten DSC-Konfiguration abweicht. In diesem Beispiel überprüfen wir die Konfiguration des lokalen Computers.

```powershell
$session = New-CimSession -ComputerName "localhost"
Test-DscConfiguration -CimSession $session
```

## <a name="built-in-dsc-resources"></a>integrierte DSC-Ressourcen

Sie können die folgenden integrierten Ressourcen in ihren Konfigurations Skripts verwenden:

|Name                  |Eigenschaften                                         |
|----------------------|---------------------------------------------------|
|Datei                  |{DestinationPath, Attribute, Checksum, Content...}|
|Archivieren               |{Destination, Path, Prüfsumme, Credential...}       |
|Umgebung           |{Name, DependsOn, sicher, Pfad...}                 |
|Group                 |{GroupName, Credential, DependsOn, Description...} |
|Log                   |{Message, DependsOn, psdscrunascredential}         |
|Paket               |{Name, Path, ProductID, Arguments...}              |
|Registrierung              |{Key, valueName, DependsOn, sicher...}             |
|Skript                |{GetScript, SetScript, testScript, Credential...}  |
|Dienst               |{Name, builtinaccount, Credential, Abhängigkeiten...}|
|Benutzer                  |{UserName, DependsOn, Description, deaktiviert...}    |
|WaitForAll            |{Nodename, resourceName, DependsOn, psdscrunasc...}|
|WaitForAny            |{Nodename, resourceName, DependsOn, psdscrunasc...}|
|WaitForSome           |{Nobecount, nodename, resourceName, DependsOn...}  |
|WindowsFeature        |{Name, Credential, DependsOn, sicher...}           |
|WindowsOptionalFeature|{Name, DependsOn, sicher, LogLevel...}             |
|WindowsProcess        |{Arguments, Path, Credential, DependsOn...}        |

Führen Sie das-Cmdlet aus, um eine Liste der verfügbaren DSC-Ressourcen auf Ihrem System zu erhalten `Get-DscResource` .

> [!NOTE]
> In Versionen vor PowerShell 7.0 findet `Get-DscResource` keine klassenbasierten DSC-Ressourcen.

Das Beispiel in diesem Thema veranschaulicht die Verwendung der Datei-und Windows Feature-Ressourcen. Um alle Eigenschaften anzuzeigen, die Sie mit einer Ressource verwenden können, fügen Sie den Cursor in das Schlüsselwort "Resource" (z. b. "file") in Ihr Konfigurationsskript in PowerShell ISE ein, halten Sie <kbd>STRG</kbd> + <kbd>LEERTASTE</kbd> gedrückt.

## <a name="find-more-resources"></a>Weitere Ressourcen suchen

Sie können viele weitere verfügbare DSC-Ressourcen herunterladen, installieren und kennenlernen, die von der PowerShell und der DSC-Benutzer Community und von Microsoft erstellt wurden. Besuchen Sie die [PowerShell-Katalog](https://www.powershellgallery.com/) , um zu erfahren, welche DSC-Ressourcen verfügbar sind.

## <a name="see-also"></a>SIEHE AUCH

[PowerShell-Konfiguration des gewünschten Zustands (Übersicht)](/powershell/scripting/dsc/overview/overview)

[Integrierte PowerShell DSC-Ressourcen](/powershell/scripting/dsc/resources/resources)

[Erstellen von benutzerdefinierten PowerShell DSC-Ressourcen](/powershell/scripting/dsc/resources/authoringResource)
