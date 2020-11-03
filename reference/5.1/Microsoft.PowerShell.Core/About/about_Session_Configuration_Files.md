---
description: Beschreibt die Sitzungs Konfigurationsdateien, die in einer Sitzungs Konfiguration (auch als "Endpunkt" bezeichnet) zum Definieren der Umgebung von Sitzungen verwendet werden, die die Sitzungs Konfiguration verwenden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configuration_files?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configuration_Files
ms.openlocfilehash: 198a0aeb667c3c947bc7e202bc3c0d9832195b91
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222527"
---
# <a name="about-session-configuration-files"></a>Informationen zu Sitzungs Konfigurationsdateien

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt die Sitzungs Konfigurationsdateien, die in einer Sitzungs Konfiguration (auch als "Endpunkt" bezeichnet) zum Definieren der Umgebung von Sitzungen verwendet werden, die die Sitzungs Konfiguration verwenden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Eine "Sitzungs Konfigurationsdatei" ist eine Textdatei mit der Dateinamenerweiterung ". PSSC", die eine Hash Tabelle mit Sitzungs Konfigurations Eigenschaften und-Werten enthält. Sie können eine Sitzungs Konfigurationsdatei verwenden, um die Eigenschaften einer Sitzungs Konfiguration festzulegen. Dadurch wird die Umgebung von Windows PowerShell-Sitzungen definiert, die diese Sitzungs Konfiguration verwenden.

Sitzungs Konfigurationsdateien vereinfachen die Erstellung benutzerdefinierter Sitzungs Konfigurationen, ohne komplexe c#-Assemblys oder-Skripts zu verwenden.

Eine "Sitzungs Konfiguration" oder "Endpunkt" ist eine Sammlung von Einstellungen für den lokalen Computer, die bestimmen, wie Benutzersitzungen auf dem Computer erstellen können. welche Befehle können Benutzer in diesen Sitzungen ausführen? und ob die Sitzung als privilegiertes virtuelles Konto ausgeführt werden soll. Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).

Sitzungs Konfigurationen wurden in Windows PowerShell 2,0 eingeführt, und Sitzungs Konfigurationsdateien wurden in Windows PowerShell 3,0 eingeführt. Sie müssen Windows PowerShell 3,0 verwenden, um eine Sitzungs Konfigurationsdatei in eine Sitzungs Konfiguration einzubeziehen. Benutzer von Windows PowerShell 2,0 (und höher) sind jedoch von den Einstellungen in der Sitzungs Konfiguration betroffen.

## <a name="creating-custom-sessions"></a>Erstellen von benutzerdefinierten Sitzungen

Sie können viele Features einer Windows PowerShell-Sitzung anpassen, indem Sie in einer Sitzungs Konfiguration Sitzungs Eigenschaften angeben. Sie können eine Sitzung anpassen, indem Sie ein c#-Programm schreiben, das einen benutzerdefinierten Runspace definiert, oder Sie können eine Sitzungs Konfigurationsdatei verwenden, um die Eigenschaften von Sitzungen zu definieren, die mit der Sitzungs Konfiguration erstellt wurden. Als allgemeine Regel ist es einfacher, die Sitzungs Konfigurationsdatei zu verwenden, als ein c#-Programm zu schreiben.

Sie können eine Sitzungs Konfigurationsdatei verwenden, um Elemente wie z. b. voll funktionsfähige Sitzungen für hochgradig vertrauenswürdige Benutzer zu erstellen. gesperrte Sitzungen, die minimalen Zugriff zulassen bestimmte Sitzungen, die nur die für diese Aufgaben erforderlichen Module enthalten. und Sitzungen, in denen nicht privilegierte Benutzer nur bestimmte Befehle als privilegiertes Konto ausführen können.

Darüber hinaus können Sie steuern, ob Benutzer der Sitzung Windows PowerShell-Sprachelemente wie Skriptblöcke verwenden können oder ob Sie nur Befehle ausführen dürfen. Sie können die Version von Windows PowerShell verwalten, die Benutzer in der Sitzung ausführen können. Verwalten der Module, die in die Sitzung importiert werden. und verwalten, welche Cmdlets, Funktionen und Aliase Sitzungs Benutzer ausführen können. Wenn Sie das Feld roledefinitions verwenden, können Sie Benutzern basierend auf der Gruppenmitgliedschaft unterschiedliche Funktionen in der Sitzung zur Verfügung stehen.

Weitere Informationen zu roledefinitions und zum Definieren dieses Werts finden Sie im Hilfethema für das Cmdlet "New-PSRoleCapabilityFile".

## <a name="creating-a-session-configuration-file"></a>Erstellen einer Sitzungs Konfigurationsdatei

Die einfachste Möglichkeit zum Erstellen einer Sitzungs Konfigurationsdatei ist die Verwendung des New-PSSessionConfigurationFile-Cmdlets. Mit diesem Cmdlet wird eine Datei generiert, die die richtige Syntax und das richtige Format verwendet, sodass viele der Konfigurationsdatei-Eigenschaftswerte automatisch überprüft werden.

Ausführliche Beschreibungen der Eigenschaften, die Sie in einer Sitzungs Konfigurationsdatei festlegen können, finden Sie im Hilfethema für das Cmdlet "New-PSSessionConfigurationFile".

Der folgende Befehl erstellt eine Sitzungs Konfigurationsdatei, in der die Standardwerte verwendet werden. In der resultierenden Konfigurationsdatei werden nur die Standardwerte verwendet, da keine anderen Parameter als der path-Parameter (der den Dateipfad angibt) enthalten sind:

```powershell
New-PSSessionConfigurationFile -Path .\Defaults.pssc
```

Verwenden Sie den folgenden Befehl, um die neue Konfigurationsdatei im Standardtext-Editor anzuzeigen:

```powershell
Invoke-Item -Path .\Defaults.pssc
```

Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, in denen Benutzer Befehle ausführen, aber keine anderen Elemente der Windows PowerShell-Sprache verwenden können, geben Sie Folgendes ein:

```powershell
New-PSSessionConfigurationFile -LanguageMode NoLanguage
-Path .\NoLanguage.pssc
```

Im vorangehenden Befehl wird durch das Festlegen des languagemode-Parameters auf nolanguage verhindert, dass Benutzeraktionen wie das Schreiben oder Ausführen von Skripts oder Variablen verwenden.

Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, in denen Benutzer nur Get-Cmdlets verwenden können, geben Sie Folgendes ein:

```powershell
New-PSSessionConfigurationFile -VisibleCmdlets Get-*
-Path .\GetSessions.pssc
```

Im vorhergehenden Beispiel schränkt das Festlegen des visiblecmdlets-Parameters auf "Get-*" Benutzer auf Cmdlets ein, deren Namen mit dem Zeichen folgen Wert "Get-" beginnen.

Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, die unter einem privilegierten virtuellen Konto ausgeführt werden, anstelle der Anmelde Informationen des Benutzers, geben Sie Folgendes ein:

```powershell
New-PSSessionConfigurationFile -RunAsVirtualAccount
-Path .\VirtualAccount.pssc
```

Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, in denen die für den Benutzer sichtbaren Befehle in der Datei mit den Rollen Funktionen angegeben sind, geben Sie Folgendes ein:

```powershell
New-PSSessionConfigurationFile -RoleDefinitions
@{ 'CONTOSO\User' = @{ RoleCapabilities = 'Maintenance' }}
-Path .\Maintenance.pssc
```

### <a name="using-a-session-configuration-file"></a>Verwenden einer Sitzungs Konfigurationsdatei

Sie können eine Sitzungs Konfigurationsdatei einschließen, wenn Sie eine Sitzungs Konfiguration erstellen oder hinzufügen. Sie können der Sitzungs Konfiguration zu einem späteren Zeitpunkt eine Datei hinzufügen.

Verwenden Sie den path-Parameter des Register-PSSessionConfiguration-Cmdlets, um beim Erstellen einer Sitzungs Konfiguration eine Sitzungs Konfigurationsdatei einzuschließen.

Der folgende Befehl verwendet z. b. die Datei nolanguage. PSSC, wenn eine nolanguage-Sitzungs Konfiguration erstellt wird.

```powershell
Register-PSSessionConfiguration -Name NoLanguage
-Path .\NoLanguage.pssc
```

Wenn eine neue nolanguage-Sitzung gestartet wird, haben Benutzer nur Zugriff auf Windows PowerShell-Befehle.

Zum Hinzufügen einer Sitzungs Konfigurationsdatei zu einer vorhandenen Sitzungs Konfiguration verwenden Sie das Cmdlet Set-PSSessionConfiguration und den path-Parameter. Dies wirkt sich auf alle neuen Sitzungen aus, die mit der angegebenen Sitzungs Konfiguration erstellt wurden. Beachten Sie, dass das Cmdlet "Set-PSSessionConfiguration" die Sitzung selbst ändert und die Sitzungs Konfigurationsdatei nicht ändert.

Beispielsweise wird mit dem folgenden Befehl die Datei nolanguage. PSSC der lockeddown-Sitzungs Konfiguration hinzugefügt.

```powershell
Set-PSSessionConfiguration -Name LockedDown
-Path .\NoLanguage.pssc
```

Wenn Benutzer die lockeddown-Sitzungs Konfiguration verwenden, um eine Sitzung zu erstellen, können Sie Cmdlets ausführen, aber Sie können keine Variablen erstellen oder verwenden, Werte zuweisen oder andere Elemente der Windows PowerShell-Sprache verwenden.

Der folgende Befehl verwendet das Cmdlet "New-PSSession", um eine Sitzung auf dem Computer zu erstellen SRV01, die die lockeddown-Sitzungs Konfiguration verwendet und einen Objekt Verweis auf die Sitzung in der $s Variablen speichert. Die Zugriffs Steuerungs Liste (Access Control List, ACL) der Sitzungs Konfiguration bestimmt, wer zum Erstellen einer Sitzung verwendet werden kann.

```powershell
$s = New-PSSession -ComputerName Srv01
-ConfigurationName LockedDown
```

Da die nolanguage-Einschränkungen der lockeddown-Sitzungs Konfiguration hinzugefügt wurden, können Benutzer in lockeddown-Sitzungen nur Windows PowerShell-Befehle und-Cmdlets ausführen. Beispielsweise verwenden die folgenden beiden Befehle das Invoke-Command-Cmdlet, um Befehle in der Sitzung auszuführen, auf die in der $s-Variablen verwiesen wird. Der erste Befehl, der das Get-UICulture-Cmdlet ausführt und keine Variablen verwendet, ist erfolgreich. Der zweite Befehl, der den Wert der $PSUICulture Variable abruft, schlägt fehl.

```
Invoke-Command -Session $s {Get-UICulture}
en-US

Invoke-Command -Session $s {$PSUICulture}
The syntax is not supported by this runspace. This might be
because it is in no-language mode.
+ CategoryInfo          : ParserError: ($PSUICulture:String) [],
ParseException
+ FullyQualifiedErrorId : ScriptsNotAllowed
```

## <a name="editing-a-session-configuration-file"></a>Bearbeiten einer Sitzungskonfigurationsdatei

Alle Einstellungen in einer Sitzungs Konfiguration mit Ausnahme von runasvirtualaccount und runasvirtualaccountgroups können durch Bearbeiten der Sitzungs Konfigurationsdatei geändert werden, die von der Sitzungs Konfiguration verwendet wird. Zu diesem Zweck suchen Sie zunächst die aktive Kopie der Sitzungs Konfigurationsdatei.

Wenn Sie eine Sitzungs Konfigurationsdatei in einer Sitzungs Konfiguration verwenden, erstellt Windows PowerShell eine aktive Kopie der Sitzungs Konfigurationsdatei und speichert Sie im \$ Verzeichnis "PSHome \\ sessionconfig" auf dem lokalen Computer.

Der Speicherort der aktiven Kopie einer Sitzungs Konfigurationsdatei wird in der configfilepath-Eigenschaft des Sitzungs Konfigurations Objekts gespeichert.

Mit dem folgenden Befehl wird der Speicherort der Sitzungs Konfigurationsdatei für die nolanguage-Sitzungs Konfiguration abgerufen.

```powershell
(Get-PSSessionConfiguration -Name NoLanguage).ConfigFilePath
```

Dieser Befehl gibt einen Dateipfad zurück, der dem folgenden ähnelt:

```
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

Sie können die PSSC-Datei in einem beliebigen Text-Editor bearbeiten. Nachdem die Datei gespeichert wurde, wird Sie von allen neuen Sitzungen verwendet, die die Sitzungs Konfiguration verwenden.

Wenn Sie die runasvirtualaccount-oder runasvirtualaccountgroups-Einstellungen ändern müssen, müssen Sie die Registrierung der Sitzungs Konfiguration aufheben und eine Sitzungs Konfigurationsdatei erneut registrieren, die die bearbeiteten Werte enthält.

## <a name="testing-a-session-configuration-file"></a>Testen einer Sitzungs Konfigurationsdatei

Verwenden Sie das Cmdlet "Test-PSSessionConfigurationFile", um manuell bearbeiteten Sitzungs Konfigurationsdateien zu testen. Das ist wichtig: Wenn die Datei Syntax und die Werte nicht gültig sind, können Benutzer die Sitzungs Konfiguration nicht verwenden, um eine Sitzung zu erstellen.

Der folgende Befehl testet z. b. die aktive Sitzungs Konfigurationsdatei der nolanguage-Sitzungs Konfiguration.

```powershell
Test-PSSessionConfigurationFile -Path C:\WINDOWS\System32\
WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

Wenn die Syntax und die Werte in der Konfigurationsdatei gültig sind Test-PSSessionConfigurationFile gibt true zurück. Wenn die Syntax und die Werte nicht gültig sind, gibt das Cmdlet false zurück.

Mit Test-PSSessionConfigurationFile können Sie alle Sitzungs Konfigurationsdateien testen, einschließlich Dateien, die vom New-PSSessionConfiguration-Cmdlet erstellt werden. Weitere Informationen finden Sie im Hilfethema für das Cmdlet "Test-PSSessionConfigurationFile".

## <a name="removing-a-session-configuration-file"></a>Entfernen einer Sitzungs Konfigurationsdatei

Eine Sitzungs Konfigurationsdatei kann nicht aus einer Sitzungs Konfiguration entfernt werden.
Allerdings können Sie die Datei durch eine neue Datei ersetzen, in der die Standardeinstellungen verwendet werden. Dadurch werden die von der ursprünglichen Konfigurationsdatei verwendeten Einstellungen effektiv abgebrochen.

Zum Ersetzen einer Sitzungs Konfigurationsdatei erstellen Sie eine neue Sitzungs Konfigurationsdatei, in der die Standardeinstellungen verwendet werden. verwenden Sie dann das Cmdlet "Set-PSSessionConfiguration", um die benutzerdefinierte Sitzungs Konfigurationsdatei durch die neue Datei zu ersetzen.

Die folgenden Befehle erstellen z. b. eine standardmäßige Sitzungs Konfigurationsdatei und ersetzen dann die aktive Sitzungs Konfigurationsdatei in der nolanguage-Sitzungs Konfiguration.

```powershell
New-PSSessionConfigurationFile -Path .\Default.pssc
Set-PSSessionConfiguration -Name NoLanguage
-Path .\Default.pssc
```

Wenn diese Befehle fertiggestellt werden, bietet die nolanguage-Sitzungs Konfiguration tatsächlich vollständige Sprachunterstützung (Standardeinstellung) für alle Sitzungen, die mit dieser Sitzungs Konfiguration erstellt werden.

Anzeigen der Eigenschaften einer Sitzungs Konfiguration die Sitzungs Konfigurationsobjekte, die Sitzungs Konfigurationen mithilfe von Sitzungs Konfigurationsdateien darstellen, verfügen über zusätzliche Eigenschaften, die das Auffinden und Analysieren der Sitzungs Konfiguration erleichtern. (Beachten Sie, dass der unten gezeigte Typname eine formatierte Sicht Definition enthält.) Sie können die Eigenschaften anzeigen, indem Sie das Cmdlet "Get-PSSessionConfiguration" ausführen und die zurückgegebenen Daten an das Get-Member-Cmdlet weiterleiten:

```powershell
Get-PSSessionConfiguration NoLanguage | Get-Member
```

```output
TypeName: Microsoft.PowerShell.Commands.PSSessionConfigurationCommands
#PSSessionConfiguration

Name                          MemberType     Definition
----                          ----------     ----------
Equals                        Method         bool Equals(System.O...
GetHashCode                   Method         int GetHashCode()
GetType                       Method         type GetType()
ToString                      Method         string ToString()
Architecture                  NoteProperty   System.String Archit...
Author                        NoteProperty   System.String Author...
AutoRestart                   NoteProperty   System.String AutoRe...
Capability                    NoteProperty   System.Object[] Capa...
CompanyName                   NoteProperty   System.String Compan...
configfilepath                NoteProperty   System.String config...
Copyright                     NoteProperty   System.String Copyri...
Enabled                       NoteProperty   System.String Enable...
ExactMatch                    NoteProperty   System.String ExactM...
ExecutionPolicy               NoteProperty   System.String Execut...
Filename                      NoteProperty   System.String Filena...
GUID                          NoteProperty   System.String GUID=0...
ProcessIdleTimeoutSec         NoteProperty   System.String Proces...
IdleTimeoutms                 NoteProperty   System.String IdleTi...
lang                          NoteProperty   System.String lang=e...
LanguageMode                  NoteProperty   System.String Langua...
MaxConcurrentCommandsPerShell NoteProperty   System.String MaxCon...
MaxConcurrentUsers            NoteProperty   System.String MaxCon...
MaxIdleTimeoutms              NoteProperty   System.String MaxIdl...
MaxMemoryPerShellMB           NoteProperty   System.String MaxMem...
MaxProcessesPerShell          NoteProperty   System.String MaxPro...
MaxShells                     NoteProperty   System.String MaxShells
MaxShellsPerUser              NoteProperty   System.String MaxShe...
Name                          NoteProperty   System.String Name=N...
PSVersion                     NoteProperty   System.String PSVersion
ResourceUri                   NoteProperty   System.String Resour...
RunAsPassword                 NoteProperty   System.String RunAsP...
RunAsUser                     NoteProperty   System.String RunAsUser
SchemaVersion                 NoteProperty   System.String Schema...
SDKVersion                    NoteProperty   System.String SDKVer...
OutputBufferingMode           NoteProperty   System.String Output...
SessionType                   NoteProperty   System.String Sessio...
UseSharedProcess              NoteProperty   System.String UseSha...
SupportsOptions               NoteProperty   System.String Suppor...
xmlns                         NoteProperty   System.String xmlns=...
XmlRenderingType              NoteProperty   System.String XmlRen...
Permission                    ScriptProperty System.Object Permis...
```

Diese Eigenschaften erleichtern das Suchen nach bestimmten Sitzungs Konfigurationen.
Sie können z. b. die ExecutionPolicy-Eigenschaft verwenden, um eine Sitzungs Konfiguration zu suchen, die Sitzungen mit der RemoteSigned-Ausführungs Richtlinie unterstützt.
Beachten Sie Folgendes: da die ExecutionPolicy-Eigenschaft nur für Sitzungen vorhanden ist, die Sitzungs Konfigurationsdateien verwenden, gibt der Befehl möglicherweise nicht alle qualifizierenden Sitzungs Konfigurationen zurück.

```powershell
Get-PSSessionConfiguration |
where {$_.ExecutionPolicy -eq "RemoteSigned"}
```

Mit dem folgenden Befehl werden Sitzungs Konfigurationen abgerufen, in denen der RunAsUser der Exchange-Administrator ist.

```powershell
 Get-PSSessionConfiguration |
where {$_.RunAsUser -eq "Exchange01\Admin01"}
```

Verwenden Sie das Cmdlet "Get-PSSessionCapability", um Informationen zu den einer Konfiguration zugeordneten Rollen Definitionen anzuzeigen. Mit diesem Cmdlet können Sie die Befehle und die Umgebung ermitteln, die bestimmten Benutzern in bestimmten Endpunkten zur Verfügung stehen.

## <a name="notes"></a>HINWEISE

Sitzungs Konfigurationen unterstützen auch einen Sitzungstyp, der als "leere" Sitzung bezeichnet wird. Mit einem leeren Sitzungstyp können Sie benutzerdefinierte Sitzungen mit ausgewählten Befehlen erstellen. Wenn Sie einer leeren Sitzung keine Module, Funktionen oder Skripts hinzufügen, ist die Sitzung auf Ausdrücke beschränkt und kann nicht praktisch verwendet werden. Die SessionType-Eigenschaft gibt Aufschluss darüber, ob Sie mit einer leeren Sitzung arbeiten.

## <a name="see-also"></a>SIEHE AUCH

[about_Session_Configurations](about_Session_Configurations.md)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Disable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[Enable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[Get-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[New-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[Register-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[Set-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[Test-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[Unregister-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

[Get-PSSessionCapability](xref:Microsoft.PowerShell.Core.Get-PSSessionCapability)

[New-PSRoleCapabilityFile](xref:Microsoft.PowerShell.Core.New-PSRoleCapabilityFile)
