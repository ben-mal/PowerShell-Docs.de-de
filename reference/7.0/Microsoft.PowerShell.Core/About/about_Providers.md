---
description: Hier wird beschrieben, wie PowerShell-Anbieter den Zugriff auf Daten und Komponenten ermöglichen, auf die in der Befehlszeile sonst nicht einfach zugegriffen werden kann. Die Daten werden in einem konsistenten Format dargestellt, das einem Dateisystem Laufwerk ähnelt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: c0ae976c9f82a8a7481eda2bad136e7ba2689a44
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220652"
---
# <a name="about-providers"></a>Informationen zu Anbietern

## <a name="short-description"></a>Kurze Beschreibung
Hier wird beschrieben, wie PowerShell-Anbieter den Zugriff auf Daten und Komponenten ermöglichen, auf die in der Befehlszeile sonst nicht einfach zugegriffen werden kann.
Die Daten werden in einem konsistenten Format dargestellt, das einem Dateisystem Laufwerk ähnelt.

## <a name="long-description"></a>Lange Beschreibung

PowerShell-Anbieter sind .net-Programme, die den Zugriff auf spezialisierte Datenspeicher bereitstellen, um die Anzeige und Verwaltung zu vereinfachen. Die Daten werden in einem Laufwerk angezeigt, und Sie greifen auf die Daten in einem Pfad wie auf einem Festplattenlaufwerk zu. Sie können alle integrierten Cmdlets verwenden, die der Anbieter unterstützt, um die Daten im Anbieter Laufwerk zu verwalten. Und Sie können benutzerdefinierte Cmdlets verwenden, die speziell für die Daten entworfen wurden.

Die Anbieter können den integrierten Cmdlets auch dynamische Parameter hinzufügen. Diese Parameter sind nur verfügbar, wenn Sie das-Cmdlet mit den Anbieter Daten verwenden.

## <a name="built-in-providers"></a>Integrierte Anbieter

PowerShell umfasst eine Reihe integrierter Anbieter, mit denen Sie auf die verschiedenen Typen von Daten speichern zugreifen können.

| Anbieter   |   Laufwerk (e)  |OutputType                                                    |
|----------- |------------ |--------------------------------------------------------------|
|Alias       |Alias:       |System. Management. Automation. AliasInfo                        |
|Zertifikat |Cert:        |Microsoft. PowerShell. Commands. X509StoreLocation               |
|            |             |System.Security.Cryptography.X509Certificates.X509Certificate2|
|Environment |Env:         |System. Collections. ditionaryentry                            |
|FileSystem  |C: (*)       |System. IO. fileingefo                                            |
|            |             |System. IO. directoriyinfo                                       |
|Funktion    |Funktion:    |System. Management. Automation. functioninfo                     |
|Registrierung    |HKLM: HKCU:  |Microsoft. Win32. RegistryKey                                   |
|Variable    |Variable:    |System. Management. Automation. psvariable                       |
|WSMan       |WS-Management:       |Microsoft. WSMAN. Management. wsmanconfigcontainerelement        |

(*) Die Dateisystem Laufwerke variieren je nach System.

Sie können auch Ihre eigenen PowerShell-Anbieter erstellen, und Sie können Anbieter installieren, die andere entwickeln. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie Folgendes ein:

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a>Installieren und Entfernen von Anbietern

Anbieter werden in der Regel über PowerShell-Module installiert. Beim Importieren des Moduls wird der Anbieter in Ihre Sitzung geladen. Sie können die integrierten Anbieter nicht deinstallieren. Sie können von anderen Modulen geladene Anbieter deinstallieren.

Sie können einen Anbieter aus der aktuellen Sitzung mithilfe des `Remove-Module` Cmdlets entladen. Mit diesem Cmdlet wird der Anbieter nicht deinstalliert, aber der Anbieter ist in der Sitzung nicht verfügbar.

Sie können auch das- `Remove-PSDrive` Cmdlet verwenden, um ein beliebiges Laufwerk aus der aktuellen Sitzung zu entfernen. Diese Daten auf dem Laufwerk sind nicht betroffen, aber das Laufwerk ist in dieser Sitzung nicht mehr verfügbar.

## <a name="viewing-providers"></a>Anzeigen von Anbietern

Geben Sie Folgendes ein, um die PowerShell-Anbieter auf Ihrem Computer anzuzeigen:

```powershell
Get-PSProvider
```

Die Ausgabe listet die integrierten Anbieter und die Anbieter auf, die Sie der Sitzung hinzugefügt haben.

## <a name="the-provider-cmdlets"></a>Die Anbieter-Cmdlets

Die folgenden Cmdlets sind für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Sie können dieselben Cmdlets auf dieselbe Weise verwenden, um die verschiedenen Typen von Daten zu verwalten, die von Anbietern verfügbar gemacht werden. Nachdem Sie erfahren haben, wie Sie die Daten eines Anbieters verwalten, können Sie die gleichen Prozeduren mit den Daten von beliebigen Anbietern verwenden.

Beispielsweise wird mit dem- `New-Item` Cmdlet ein neues Element erstellt. Auf dem `C:` Laufwerk, das vom **File System** -Anbieter unterstützt wird, können Sie verwenden, `New-Item` um eine neue Datei oder einen neuen Ordner zu erstellen. Auf den Laufwerken, die vom **Registrierungs** Anbieter unterstützt werden, können Sie verwenden, `New-Item` um einen neuen Registrierungsschlüssel zu erstellen. Im- `Alias:` Laufwerk können Sie verwenden, `New-Item` um einen neuen Alias zu erstellen.

Ausführliche Informationen zu den folgenden Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a>ChildItem-Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a>Content-Cmdlets

- [Add-Content](xref:Microsoft.PowerShell.Management.Add-Content)
- [Clear-Content](xref:Microsoft.PowerShell.Management.Clear-Content)
- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)
- [Set-Content](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a>Item-Cmdlets

- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)
- [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Rename-Item](xref:Microsoft.PowerShell.Management.Rename-Item)
- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a>ItemProperty-Cmdlets

- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Copy-ItemProperty](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Move-ItemProperty](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [Rename-ItemProperty](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a>Location-Cmdlets

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Pop-Location](xref:Microsoft.PowerShell.Management.Pop-Location)
- [Push-Location](xref:Microsoft.PowerShell.Management.Push-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a>Pfad-Cmdlets

- [Join-Path](xref:Microsoft.PowerShell.Management.Join-Path)
- [Convert-Path](xref:Microsoft.PowerShell.Management.Convert-Path)
- [Split-Path](xref:Microsoft.PowerShell.Management.Split-Path)
- [Resolve-Path](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [Test-Path](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a>PSDrive-Cmdlets

- [Get-PSDrive](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [New-PSDrive](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [Remove-PSDrive](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a>Psprovider-Cmdlets

- [Get-PSProvider](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a>Anzeigen von Anbieter Daten

Der Hauptvorteil eines Anbieters besteht darin, dass er seine Daten auf vertraute und konsistente Weise verfügbar macht. Das Modell für die Datenpräsentation ist ein Dateisystem Laufwerk.

Der Anbieter ermöglicht Ihnen das anzeigen, navigieren und Ändern von Elementen im Datenspeicher, als ob es sich um Daten in einem Dateisystem handelt. Der Zugriff auf den Datenspeicher erfolgt über den Namen des Laufwerks, das von ihm unterstützt wird.

Das Laufwerk wird in der Standard Anzeige des `Get-PSProvider` Cmdlets aufgelistet, Sie können jedoch mithilfe des Cmdlets Informationen über das Anbieter Laufwerk erhalten `Get-PSDrive` . Geben Sie z. b. Folgendes ein, um alle Eigenschaften des Laufwerks "function:" zu erhalten:

```powershell
Get-PSDrive Function | Format-List *
```

Sie können die Daten in einem Anbieter Laufwerk genau so wie auf einem Dateisystem Laufwerk anzeigen und durchlaufen.

Zum Anzeigen des Inhalts eines Anbieter Laufwerks verwenden Sie die Cmdlets Get-Item oder Get-ChildItem. Geben Sie den Namen des Laufwerks gefolgt von einem Doppelpunkt (:) ein. Wenn Sie z. b. den Inhalt des Alias:-Laufwerks anzeigen möchten, geben Sie Folgendes ein:

```powershell
Get-Item alias:
```

Sie können die Daten in einem beliebigen Laufwerk von einem anderen Laufwerk anzeigen und verwalten, indem Sie den Namen des Laufwerks in den Pfad einschließen. Geben Sie beispielsweise Folgendes ein, um den Registrierungsschlüssel "HKLM\Software" auf dem Laufwerk "HKLM:" auf einem anderen Laufwerk anzuzeigen:

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

Um das Laufwerk zu öffnen, verwenden Sie das Cmdlet "Set-Location". Merken Sie sich den Doppelpunkt, wenn Sie den Laufwerks Pfad angeben. Wenn Sie z. b. ihren Speicherort in das Stammverzeichnis des Zertifikats "CERT:" ändern möchten, geben Sie Folgendes ein:

```powershell
Set-Location cert:
```

Wenn Sie den Inhalt des Zertifikats "CERT:" anzeigen möchten, geben Sie Folgendes ein:

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a>Verschieben von hierarchischen Daten

Sie können ein Anbieter Laufwerk wie ein Festplattenlaufwerk durchlaufen.
Wenn die Daten in einer Hierarchie von Elementen innerhalb von Elementen angeordnet sind, verwenden Sie einen umgekehrten Schrägstrich ( `\` ), um ein untergeordnetes Element anzugeben. Verwenden Sie das folgende Format:

```
drive:\location\child-location\...
```

Wenn Sie beispielsweise ihren Speicherort in den Registrierungsschlüssel "HKLM\Software" ändern möchten, geben Sie einen Set-Location Befehl ein, z. b.:

```powershell
Set-Location HKLM:\SOFTWARE\
```

Wenn ein beliebiges Element im voll qualifizierten Namen Leerzeichen enthält, müssen Sie den Namen in doppelte Anführungszeichen ( `"` ) einschließen. Das folgende Beispiel zeigt einen voll qualifizierten Pfad, der Leerzeichen enthält.

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

Sie können auch relative Verweise auf Speicherorte verwenden. Ein Punkt ( `.` ) stellt den aktuellen Speicherort dar. Wenn Sie z. b. im `HKLM:\Software\Microsoft` Registrierungsschlüssel sind und die Registrierungs Unterschlüssel im Schlüssel auflisten möchten `HKLM:\Software\Microsoft\PowerShell` , geben Sie den folgenden Befehl ein:

```powershell
Get-ChildItem .\PowerShell
```

Außerdem verweist Double-Dots ( `..` ) direkt oberhalb ihres aktuellen Speicher Orts auf das Verzeichnis oder den Container. Sie können doppelte Punkte () verwenden `..` , um durch eine Anbieter Hierarchie zu navigieren.

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a>Startseite des Anbieters

Anbieter verfügen auch über einen **eigenen** Standort.  Dieser Speicherort wird von allen unter `PSDrives` stützt, die vom Anbieter unterstützt werden. Sie kann abgerufen werden, indem Sie die **Home** -Eigenschaft des Anbieters anzeigen.

```powershell
Get-PSProvider | Format-Table Name, Home
```

```Output
Name        Home
----        ----
Registry
Alias
Environment
FileSystem  C:\Users\username
Function
Variable
Certificate
```

Der **File System** -Anbieter ist der einzige Anbieter, der über einen Standardwert für **Home** verfügt. Dies ist der gleiche Wert wie `$Home` . Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).

Mithilfe der-Eigenschaft können Sie das **Basisverzeichnis für** einen Anbieter für die aktuelle Sitzung festlegen.

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

Das `~` -Zeichen kann verwendet werden, um das Basisverzeichnis des Anbieters darzustellen.
Wenn für den Anbieter kein **Start** Speicherort festgelegt ist, wird ein Fehler angezeigt.

```powershell
Cert:\> Set-Location ~
```

```Output
Set-Location : Home location for this provider isn't set. To set the home
location, call "(get-psprovider 'Certificate').Home = 'path'".
At line:1 char:1
+ Set-Location ~
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Set-Location],
                              PSInvalidOperationException
...
```

## <a name="finding-dynamic-parameters"></a>Suchen von dynamischen Parametern

Dynamische Parameter sind Cmdlet-Parameter, die einem Cmdlet von einem Anbieter hinzugefügt werden. Diese Parameter sind nur verfügbar, wenn das Cmdlet mit dem Anbieter verwendet wird, der Sie hinzugefügt hat.

Beispielsweise fügt das `Cert:` Laufwerk dem-Cmdlet und dem-Cmdlet den **codeSigningCert** -Parameter hinzu `Get-Item` `Get-ChildItem` . Sie können diesen Parameter nur verwenden, wenn Sie `Get-Item` oder `Get-ChildItem` auf dem `Cert:` Laufwerk verwenden.

Eine Liste der dynamischen Parameter, die von einem Anbieter unterstützt werden, finden Sie in der Hilfedatei für den Anbieter. Typ:

```
Get-Help <provider-name>
```

Beispiel:

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a>Kennenlernen von Anbietern

Obwohl alle Anbieter Daten auf den Laufwerken angezeigt werden und Sie die gleichen Methoden verwenden, um Sie zu durchlaufen, wird die Ähnlichkeit dort angehalten. Die Datenspeicher, die der Anbieter verfügbar macht, können so unterschiedlich sein wie Active Directory Standorte und Microsoft Exchange Server-Postfächer.

Informationen zu einzelnen PowerShell-Anbietern erhalten Sie, wenn Sie Folgendes eingeben:

```
Get-Help <ProviderName>
```

Beispiel:

```powershell
Get-Help registry
```

Eine Liste der Hilfe Themen zu den Anbietern erhalten Sie, wenn Sie Folgendes eingeben:

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a>Weitere Informationen:

[about_Locations](about_Locations.md)

[about_Path_Syntax](about_Path_Syntax.md)
