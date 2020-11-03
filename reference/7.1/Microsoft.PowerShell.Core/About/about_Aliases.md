---
description: Beschreibt, wie alternative Namen für Cmdlets und Befehle in PowerShell verwendet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_aliases?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Aliases
ms.openlocfilehash: e0a1fa357e591dd17986a8dd685a1818751ab355
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224084"
---
# <a name="about-aliases"></a>Informationen zu Aliasen

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt, wie alternative Namen für Cmdlets und Befehle in PowerShell verwendet werden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Ein Alias ist ein alternativer Name oder Spitzname für ein Cmdlet oder ein Befehls Element, z. b. eine Funktion, ein Skript, eine Datei oder eine ausführbare Datei. Sie können den Alias anstelle des Befehlsnamens in beliebigen PowerShell-Befehlen verwenden.

Verwenden Sie das Cmdlet "New-Alias", um einen Alias zu erstellen. Der folgende Befehl erstellt z. b. den Alias "Gas" für das `Get-AuthenticodeSignature` Cmdlet:

```powershell
New-Alias -Name gas -Value Get-AuthenticodeSignature
```

Nachdem Sie den Alias für den Cmdlet-Namen erstellt haben, können Sie den Alias anstelle des Cmdlet-namens verwenden. Um z. b. die Authenticode-Signatur für die SqlScript.ps1-Datei zu erhalten, geben Sie Folgendes ein:

```powershell
Get-AuthenticodeSignature SqlScript.ps1
```

Oder geben Sie Folgendes ein:

```powershell
gas SqlScript.ps1
```

Wenn Sie "Word" als Alias für Microsoft Office Word erstellen, können Sie anstelle der folgenden "Word" eingeben:

```powershell
"C:\Program Files\Microsoft Office\Office11\Winword.exe"
```

## <a name="built-in-aliases"></a>integrierte Aliase

PowerShell umfasst eine Reihe integrierter Aliase, einschließlich "CD" und "chdir" für das Cmdlet "Set-Location" und "ls" und "dir" für das Get-ChildItem-Cmdlet.

Um alle Aliase auf dem Computer zu erhalten, einschließlich der integrierten Aliase, geben Sie Folgendes ein:

```powershell
Get-Alias
```

## <a name="alias-cmdlets"></a>Alias-Cmdlets

PowerShell umfasst die folgenden Cmdlets, die für die Arbeit mit Aliasen entwickelt wurden:

- `Get-Alias` : Ruft alle Aliase in der aktuellen Sitzung ab.
- `New-Alias` -Erstellt einen neuen Alias.
- `Set-Alias` -Erstellt oder ändert einen Alias.
- `Export-Alias` -Exportiert mindestens einen Alias in eine Datei.
- `Import-Alias` : Importiert eine Alias Datei in PowerShell.

Ausführliche Informationen zu den-Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:

```powershell
Get-Help <cmdlet-Name> -Detailed
```

Beispiel:

```powershell
Get-Help Export-Alias -Detailed
```

## <a name="creating-an-alias"></a>Erstellen eines Alias

Um einen neuen Alias zu erstellen, verwenden Sie das Cmdlet "New-Alias". Geben Sie beispielsweise Folgendes ein, um den "GH"-Alias für "Get-Help" zu erstellen:

```powershell
New-Alias -Name gh -Value Get-Help
```

Sie können den Alias in Befehlen wie den vollständigen Cmdlet-Namen verwenden, und Sie können den Alias mit Parametern verwenden.

Wenn Sie z. b. Ausführliche Hilfe für das Cmdlet "Get-WmiObject" benötigen, geben Sie Folgendes ein:

```powershell
Get-Help Get-WmiObject -Detailed
```

Oder geben Sie Folgendes ein:

```powershell
gh Get-WmiObject -Detailed
```

## <a name="saving-aliases"></a>Speichern von Aliasen

Die von Ihnen erstellten Aliase werden nur in der aktuellen Sitzung gespeichert. Um die Aliase in einer anderen Sitzung zu verwenden, fügen Sie den Alias Ihrem PowerShell-Profil hinzu. Oder verwenden Sie das Cmdlet "Export-Alias", um die Aliase in einer Datei zu speichern.

Geben Sie folgenden Befehl ein, um weitere Informationen zu erhalten:

```powershell
Get-Help about_Profiles
```

## <a name="getting-aliases"></a>erhalten von Aliasen

Um alle Aliase in der aktuellen Sitzung, einschließlich der integrierten Aliase, der Aliase in ihren PowerShell-Profilen und der Aliase, die Sie in der aktuellen Sitzung erstellt haben, zu erhalten, geben Sie Folgendes ein:

```powershell
Get-Alias
```

Um bestimmte Aliase zu erhalten, verwenden Sie den Name-Parameter des Cmdlets "Get-Alias". Um Aliase zu erhalten, die mit "p" beginnen, geben Sie z. b. Folgendes ein:

```powershell
Get-Alias -Name p*
```

Um die Aliase für ein bestimmtes Element zu erhalten, verwenden Sie den Definition-Parameter. Um beispielsweise die Aliase für den Get-ChildItem Cmdlet-Typ zu erhalten, geben Sie Folgendes ein:

```powershell
Get-Alias -Definition Get-ChildItem
```

### <a name="get-alias-output"></a>Get-Alias-Ausgabe

Get-Alias gibt nur einen Objekttyp zurück, ein AliasInfo-Objekt (System. Management. Automation. AliasInfo). Der Name von Aliasen, die keinen Bindestrich enthalten, wie z. b. "CD", wird im folgenden Format angezeigt:

```powershell
Get-Alias ac
```

```Output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Alias           ac -> Add-Content
```

Dadurch ist es sehr schnell und einfach, die benötigten Informationen zu erhalten.

Das pfeilbasierte Aliasnamensformat wird nicht für Aliase verwendet, die einen Bindestrich enthalten. Dabei handelt es sich wahrscheinlich um bevorzugte Ersatznamen für Cmdlets und Funktionen anstelle von typischen Abkürzungen oder Spitznamen, und der Autor möchte, dass Sie möglicherweise nicht so offensichtlich sind.

## <a name="alternate-names-for-commands-with-parameters"></a>Alternative Namen für Befehle mit Parametern

Sie können einem Cmdlet, einem Skript, einer Funktion oder einer ausführbaren Datei einen Alias zuweisen. Einem Befehl und seinen Parametern kann kein Alias zugewiesen werden. Beispielsweise können Sie dem `Get-Eventlog` Cmdlet einen Alias zuweisen, Sie können dem Befehl aber keinen Alias zuweisen `Get-Eventlog -LogName System` .

Sie können eine Funktion erstellen, die den Befehl enthält. Um eine Funktion zu erstellen, geben Sie das Wort "Function" gefolgt von einem Namen für die Funktion ein. Geben Sie den Befehl ein, und schließen Sie ihn in geschweifte Klammern ( {} ) ein.

Der folgende Befehl erstellt z. b. die syslog-Funktion. Diese Funktion stellt den- `Get-Eventlog -LogName System` Befehl dar:

```powershell
function Get-SystemEventlog {Get-Eventlog -LogName System}
Set-Alias -Name syslog -Value Get-SystemEventlog
```

Sie können jetzt "syslog" anstelle des Befehls eingeben. Und Sie können Aliase für die neue Funktion erstellen.

Weitere Informationen zu Funktionen erhalten Sie, wenn Sie Folgendes eingeben:

```powershell
Get-Help about_Functions
```

## <a name="alias-objects"></a>Alias Objekte

PowerShell-Aliase werden durch Objekte dargestellt, die Instanzen der System. Management. Automation. AliasInfo-Klasse sind. Weitere Informationen zu diesem Objekttyp finden Sie unter [AliasInfo-Klasse][aliasinfo] in der MSDN-Bibliothek (Microsoft Developer Network).

Um die Eigenschaften und Methoden der Alias Objekte anzuzeigen, erhalten Sie die Aliase.
Übergeben Sie Sie dann an das Cmdlet "Get-Member". Beispiel:

```powershell
Get-Alias | Get-Member
```

Zum Anzeigen der Werte der Eigenschaften eines bestimmten Alias, z. b. des `dir` Alias, erhalten Sie den Alias. Übergeben Sie ihn dann an das Cmdlet "Format-List". Der folgende Befehl ruft z. b. den Alias "dir" ab. Als nächstes leitet der Befehl den Alias an das Format-List-Cmdlet weiter. Anschließend verwendet der Befehl den property-Parameter von Format-List mit einem Platzhalter Zeichen ( \* ), um alle Eigenschaften des `dir` Alias anzuzeigen. Der folgende Befehl führt die folgenden Aufgaben aus:

```powershell
Get-Alias -Name dir | Format-List -Property *
```

## <a name="powershell-alias-provider"></a>PowerShell-Alias Anbieter

PowerShell enthält den Alias Anbieter. Mit dem Alias Anbieter können Sie die Aliase in PowerShell anzeigen, als ob Sie sich auf einem Dateisystem Laufwerk befinden.

Der Alias Anbieter stellt das Alias:-Laufwerk zur Verfügung. Um in das Alias:-Laufwerk zu wechseln, geben Sie Folgendes ein:

```powershell
Set-Location Alias:
```

Geben Sie Folgendes ein, um den Inhalt des Laufwerks anzuzeigen:

```powershell
Get-ChildItem
```

Um den Inhalt des Laufwerks von einem anderen PowerShell-Laufwerk aus anzuzeigen, starten Sie den Pfad mit dem Namen des Laufwerks. Fügen Sie den Doppelpunkt (:) ein. Beispiel:

```powershell
Get-ChildItem -Path Alias:
```

Um Informationen zu einem bestimmten Alias zu erhalten, geben Sie den Namen des Laufwerks und den Aliasnamen ein. Oder geben Sie ein Namensmuster ein. Um z. b. alle Aliase zu erhalten, die mit "p" beginnen, geben Sie Folgendes ein:

```powershell
Get-ChildItem -Path Alias:p*
```

Weitere Informationen zum PowerShell-Alias Anbieter erhalten Sie, wenn Sie Folgendes eingeben:

```powershell
Get-Help Alias
```

## <a name="see-also"></a>SIEHE AUCH

- [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias)
- [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [Set-Alias](xref:Microsoft.PowerShell.Utility.Set-Alias)
- [Export-Alias](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [Import-Alias](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [Get-PSProvider](xref:Microsoft.PowerShell.Management.Get-PSProvider)
- [Get-PSDrive](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [about_functions](about_functions.md)
- [about_profiles](about_profiles.md)
- [about_providers](about_providers.md)

<!-- External links -->
[aliasinfo]: /dotnet/api/system.management.automation.aliasinfo

