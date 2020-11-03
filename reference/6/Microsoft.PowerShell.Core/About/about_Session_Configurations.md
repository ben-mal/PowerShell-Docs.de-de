---
description: Beschreibt die Sitzungskonfigurationen, die bestimmen, welche Benutzer eine Remoteverbindung mit dem Computer herstellen können und welche Befehle ausgeführt werden können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configurations?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configurations
ms.openlocfilehash: 0956e2e96cb67d1c4b8c3ef245c6fa084b781351
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221167"
---
# <a name="about-session-configurations"></a>Informationen zu Sitzungs Konfigurationen

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt die Sitzungskonfigurationen, die bestimmen, welche Benutzer eine Remoteverbindung mit dem Computer herstellen können und welche Befehle ausgeführt werden können.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Eine Sitzungs Konfiguration, auch als "Endpunkt" bezeichnet, ist eine Gruppe von Einstellungen auf dem lokalen Computer, die die Umgebung für die PowerShell-Sitzungen definieren, die erstellt werden, wenn Remote-oder lokale Benutzer eine Verbindung mit PowerShell auf dem lokalen Computer herstellen.

Administratoren des Computers können Sitzungs Konfigurationen verwenden, um den Computer zu schützen und benutzerdefinierte Umgebungen für Benutzer zu definieren, die eine Verbindung mit dem Computer herstellen.

Administratoren können auch Sitzungs Konfigurationen verwenden, um die Berechtigungen zu bestimmen, die erforderlich sind, um eine Remote Verbindung mit dem Computer herzustellen. Standardmäßig haben nur Mitglieder der Gruppe "Administratoren" die Berechtigung, die Sitzungs Konfiguration für eine Remote Verbindung zu verwenden. Sie können jedoch die Standardeinstellungen ändern, damit alle Benutzer oder ausgewählte Benutzer eine Remote Verbindung mit dem Computer herstellen können.

Ab PowerShell 3,0 können Sie eine Sitzungs Konfigurationsdatei verwenden, um die Elemente einer Sitzungs Konfiguration zu definieren. Diese Funktion erleichtert das Anpassen von Sitzungen, ohne Code zu schreiben und die Eigenschaften einer Sitzungs Konfiguration zu ermitteln. Verwenden Sie das Cmdlet "New-PSSessionConfiguration", um eine Sitzungs Konfigurationsdatei zu erstellen. Weitere Informationen zu Sitzungskonfigurationsdateien finden Sie unter [about_Session_Configuration_Files](about_Session_Configuration_Files.md).

Sitzungs Konfigurationen sind eine Funktion von Web Services for Management (WS-Management)-basierten PowerShell-Remoting. Sie werden nur verwendet, wenn Sie die Cmdlets New-PSSession, Aufruf-Command oder Enter-PSSession zum Herstellen einer Verbindung mit einem Remote Computer verwenden.

Hinweis: Starten Sie PowerShell mit der Option "als Administrator ausführen", um die Sitzungs Konfigurationen zu verwalten.

Informationen zu Sitzungs Konfigurationen

Für jede PowerShell-Sitzung wird eine Sitzungs Konfiguration verwendet. Dies schließt persistente Sitzungen ein, die Sie mithilfe der Cmdlets New-PSSession oder Enter-PSSession erstellen, und die temporären Sitzungen, die PowerShell erstellt, wenn Sie den Computername-Parameter eines Cmdlets verwenden, das WS-Management-basierte Remotingtechnologie verwendet, wie z. b. "Start-Command".

Administratoren können Sitzungs Konfigurationen verwenden, um die Ressourcen des Computers zu schützen und benutzerdefinierte Umgebungen für Benutzer zu erstellen, die eine Verbindung mit dem Computer herstellen. Beispielsweise können Sie eine Sitzungs Konfiguration verwenden, um die Größe der Objekte, die der Computer in der Sitzung empfängt, einzuschränken, den Sprachmodus der Sitzung zu definieren und die in der Sitzung verfügbaren Cmdlets, Anbieter und Funktionen anzugeben.

Durch Konfigurieren der Sicherheits Beschreibung einer Sitzungs Konfiguration legen Sie fest, wer die Sitzungs Konfiguration verwenden kann, um eine Verbindung mit dem Computer herzustellen.
Benutzer müssen über die Berechtigung Ausführen für eine Sitzungs Konfiguration verfügen, damit Sie in einer Sitzung verwendet werden kann. Wenn ein Benutzer nicht über die erforderlichen Berechtigungen verfügt, um eine der Sitzungs Konfigurationen auf einem Computer zu verwenden, kann der Benutzer keine Remote Verbindung mit dem Computer herstellen.

Standardmäßig verfügen nur Administratoren des Computers über die Berechtigung zum Verwenden der Standard Sitzungs Konfigurationen. Sie können jedoch die Sicherheits Deskriptoren ändern, um allen Benutzern, nicht oder nur ausgewählten Benutzern zu gestatten, die Sitzungs Konfigurationen auf dem Computer zu verwenden.

Integrierte Sitzungs Konfigurationen

PowerShell 3,0 umfasst integrierte Sitzungs Konfigurationen namens Microsoft. PowerShell und Microsoft. PowerShell. Workflow. Auf Computern, auf denen 64-Bit-Versionen von Windows ausgeführt werden, bietet PowerShell auch Microsoft. PowerShell32, eine 32-Bit-Sitzungs Konfiguration.

Die Microsoft. PowerShell-Sitzungs Konfiguration wird standardmäßig für Sitzungen verwendet, d. h., wenn ein Befehl zum Erstellen einer Sitzung nicht den ConfigurationName-Parameter des Cmdlets New-PSSession, Enter-PSSession oder Invoke-Command enthält.

Die Sicherheits Deskriptoren für die Standard Sitzungs Konfigurationen ermöglichen es nur Mitgliedern der Gruppe "Administratoren" auf dem lokalen Computer, Sie zu verwenden. Daher können nur Mitglieder der Gruppe "Administratoren" eine Remote Verbindung mit dem Computer herstellen, es sei denn, Sie ändern die Standardeinstellungen.

Sie können die Standard Sitzungs Konfigurationen mithilfe der $PSSessionConfigurationName Preference-Variablen ändern. Weitere Informationen finden Sie unter „about_Preference_Variables“.

Anzeigen von Sitzungs Konfigurationen auf dem lokalen Computer

Verwenden Sie das Cmdlet "Get-PSSessionConfiguration", um die Sitzungs Konfigurationen auf dem lokalen Computer zu erhalten.

Beispiel:

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property Name, Permission

Name       : microsoft.powershell
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell.workflow
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell32
Permission : BUILTIN\Administrators AccessAllowed
```

Das Sitzungs Konfigurationsobjekt wird in PowerShell 3,0 erweitert, um die Eigenschaften der Sitzungs Konfiguration anzuzeigen, die mithilfe einer Sitzungs Konfigurationsdatei konfiguriert werden.

Wenn Sie z. b. alle Eigenschaften eines Sitzungs Konfigurations Objekts anzeigen möchten, geben Sie Folgendes ein:

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property *
```

Sie können auch den WSMAN-Anbieter in PowerShell verwenden, um Sitzungs Konfigurationen anzuzeigen. Der WSMAN-Anbieter erstellt ein WSMAN:-Laufwerk in der Sitzung.

Im WSMAN:-Laufwerk befinden sich Sitzungs Konfigurationen im Plug-in-Knoten. (Alle Sitzungs Konfigurationen befinden sich im Plug-in-Knoten, es sind jedoch Elemente im Plug-in-Knoten vorhanden, die keine Sitzungs Konfigurationen sind.)

Wenn Sie z. b. die Sitzungs Konfigurationen auf dem lokalen Computer anzeigen möchten, geben Sie Folgendes ein:

```powershell
PS C:> dir wsman:\localhost\plugin\microsoft*

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

Anzeigen von Sitzungs Konfigurationen auf einem Remote Computer

Um die Sitzungs Konfigurationen auf einem Remote Computer anzuzeigen, verwenden Sie das Cmdlet "Connect-WSMan", um dem WSMAN:-Laufwerk auf dem lokalen Computer einen Hinweis für den Remote Computer hinzuzufügen, und verwenden Sie dann das WSMAN:-Laufwerk, um die Sitzungs Konfigurationen anzuzeigen.

Beispielsweise wird mit dem folgenden Befehl dem WSMAN:-Laufwerk auf dem lokalen Computer ein Knoten für den Remote Computer Server01 hinzugefügt.

```powershell
PS C:> Connect-WSMan server01.corp.fabrikam.com
```

Wenn der Befehl fertiggestellt ist, können Sie zum Knoten für den Server01-Computer navigieren, um die Sitzungs Konfigurationen anzuzeigen.

Beispiel:

```powershell
PS C:> cd wsman:

PS WSMan:> dir

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01.corp.fabrikam.com                    Container

PS WSMan:> dir server01\plugin\

WSManConfig: Microsoft.WSMan.Management\WSMan::server01.corp.fabrikam.com\Pl
ugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

Ändern der Sicherheits Beschreibung einer Sitzungs Konfiguration

In Windows Server 2012 und neueren Versionen von Windows Server sind die integrierten Sitzungs Konfigurationen standardmäßig für Remote Benutzer aktiviert. In anderen unterstützten Versionen von Windows müssen Sie die Sicherheits Deskriptoren der Sitzungs Konfigurationen ändern, um den Remote Zugriff zu ermöglichen.

Verwenden Sie das Cmdlet "Enable-PSRemoting", um den Remote Zugriff auf die Sitzungs Konfigurationen auf dem Computer zu aktivieren. Dieses Cmdlet erstellt zwei Sitzungs Konfigurationen:

- mit dem definierten Namen "PowerShell". + "aktuelle PowerShell-Version"
- mit dem Namen "PowerShell. 6", nicht an eine bestimmte PowerShell-Version gebunden.

Außerdem verfügen standardmäßig nur Mitglieder der Gruppe "Administratoren" auf dem Computer über die Berechtigung "ausführen" für die Standard Sitzungs Konfigurationen, aber Sie können die Sicherheits Beschreibungen in den Standard Sitzungs Konfigurationen und in den von Ihnen erstellten Sitzungs Konfigurationen ändern.

Um anderen Benutzern die Berechtigung zu erteilen, eine Remote Verbindung mit dem Computer herzustellen, verwenden Sie das Cmdlet "Set-PSSessionConfiguration", um den Sicherheits Beschreibungen der Sitzungs Konfigurationen Microsoft. PowerShell und Microsoft. PowerShell32 Berechtigungen für diese Benutzer hinzuzufügen.

Beispielsweise wird mit dem folgenden Befehl eine Eigenschaften Seite geöffnet, auf der Sie die Sicherheits Beschreibung für die Standard Sitzungs Konfiguration von Microsoft. PowerShell ändern können.

```powershell
Set-PSSessionConfiguration -name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

Verwenden Sie das Cmdlet "Disable-PSSessionConfiguration", um allen Sitzungs Konfigurationen auf dem Computer alle Berechtigungen zu verweigern. Der folgende Befehl deaktiviert z. b. die Standard Sitzungs Konfigurationen auf dem Computer.

```powershell
PS C:> Disable-PSSessionConfiguration -Name Microsoft.PowerShell
```

Verwenden Sie das Cmdlet "Disable-PSRemoting", um zu verhindern, dass Remote Benutzer eine Verbindung mit dem Computer herstellen, aber die Verbindung zwischen lokalen Benutzern herstellen können. Disable-PSRemoting fügt allen Sitzungs Konfigurationen auf dem Computer einen "Network_Deny_All"-Eintrag hinzu.

```powershell
PS C:> Disable-PSRemoting
```

Verwenden Sie das Cmdlet Enable-PSRemoting oder Enable-PSSessionConfiguration, damit Remote Benutzer alle Sitzungs Konfigurationen auf dem Computer verwenden können. Der folgende Befehl aktiviert z. b. den Remote Zugriff auf die integrierten Sitzungs Konfigurationen.

```powershell
PS C:> Enable-PSSessionConfiguration -name Microsoft.Power*
```

Wenn Sie andere Änderungen an der Sicherheits Beschreibung einer Sitzungs Konfiguration vornehmen möchten, verwenden Sie das Cmdlet "Set-PSSessionConfiguration". Verwenden Sie den securitydescriptorsddl-Parameter, um einen SDDL-Zeichen folgen Wert zu senden. Verwenden Sie den showsecuritydescriptorui-Parameter, um ein Eigenschaften Blatt für die Benutzeroberfläche anzuzeigen, das Ihnen beim Erstellen einer neuen SDDL hilft.

Beispiel:

```powershell
Set-PSSessionConfiguration -Name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

Erstellen einer neuen Sitzungs Konfiguration

Verwenden Sie das Cmdlet "Register-PSSessionConfiguration", um eine neue Sitzungs Konfiguration auf dem lokalen Computer zu erstellen. Zum Definieren der neuen Sitzungs Konfiguration können Sie eine c#-Assembly, ein PowerShell-Skript und die Parameter des Register-PSSessionConfiguration-Cmdlets verwenden.

Der folgende Befehl erstellt z. b. eine Sitzungs Konfiguration, die mit der Microsoft. PowerShell-Sitzungs Konfiguration identisch ist, mit dem Unterschied, dass die von einem Remote Befehl empfangenen Daten auf 20 Megabyte (MB) begrenzt werden. (Der Standardwert ist 50 MB).

```powershell
Register-PSSessionConfiguration -Name NewConfig `
  -MaximumReceivedDataSizePerCommandMB 20
```

Wenn Sie eine Sitzungs Konfiguration erstellen, können Sie Sie mit den anderen Cmdlets für die Sitzungs Konfiguration verwalten, die auf dem WSMAN:-Laufwerk angezeigt wird.

Weitere Informationen finden Sie unter Register-pssessionconfiguration.

Entfernen einer Sitzungs Konfiguration

Verwenden Sie das Cmdlet "Unregister-PSSessionConfiguration", um eine Sitzungs Konfiguration vom lokalen Computer zu entfernen. Mit dem folgenden Befehl wird beispielsweise die Konfiguration der Neukonfigurations Sitzung vom Computer entfernt.

```powershell
PS C:> Unregister-PSSessionConfiguration -Name NewConfig
```

Weitere Informationen finden Sie unter Unregister-pssessionconfiguration.

Wiederherstellen einer Sitzungs Konfiguration

Verwenden Sie das Cmdlet "Enable-PSRemoting", um eine standardmäßige Sitzungs Konfiguration, die versehentlich gelöscht wurde (ohne Registrierung), wiederherzustellen.

Mit dem Cmdlet "Enable-PSRemoting" werden alle Standard Sitzungs Konfigurationen neu erstellt, die auf dem Computer nicht vorhanden sind. Die Eigenschaftswerte vorhandener Sitzungs Konfigurationen werden nicht überschrieben oder geändert.

Um die ursprünglichen Eigenschaftswerte einer Standard Sitzungs Konfiguration wiederherzustellen, verwenden Sie die Unregister-PSSessionConfiguration, um die Sitzungs Konfiguration zu löschen, und verwenden Sie dann das Enable-PSRemoting-Cmdlet, um Sie neu zu erstellen.

Auswählen einer Sitzungs Konfiguration

Um eine bestimmte Sitzungs Konfiguration für eine Sitzung auszuwählen, verwenden Sie den ConfigurationName-Parameter von New-PSSession, Enter-PSSession oder aufrufen-Command.

Dieser Befehl verwendet z. b. das New-PSSession-Cmdlet, um eine PSSession auf dem Server01-Computer zu starten. Der Befehl verwendet den ConfigurationName-Parameter, um die withprofile-Konfiguration auf dem Server01-Computer auszuwählen.

```powershell
PS C:> New-PSSession -ComputerName Server01 -ConfigurationName WithProfile
```

Dieser Befehl ist nur erfolgreich, wenn der aktuelle Benutzer über die Berechtigung zum Verwenden der withprofile-Sitzungs Konfiguration verfügt oder die Anmelde Informationen eines Benutzers bereitstellen kann, der über die erforderlichen Berechtigungen verfügt.

Sie können auch die $PSSessionConfigurationName Preference-Variable verwenden, um die Standard Sitzungs Konfiguration auf dem Computer zu ändern. Weitere Informationen zur $PSSessionConfigurationName Preference-Variablen finden Sie unter about_Preference_Variables.

## <a name="keywords"></a>Keywords

about_Endpoints about_SessionConfigurations

## <a name="see-also"></a>SIEHE AUCH

[about_Preference_Variables](about_Preference_Variables.md)

[about_PSSessions](about_PSSessions.md)

[about_Remote](about_Remote.md)

[about_Session_Configuration_Files](about_Session_Configuration_Files.md)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Disable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[Enable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[Get-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[New-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[Register-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[Set-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[Test-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[Unregister-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)
