---
description: Hier wird beschrieben, wie Sie in PowerShell auf Windows-Umgebungsvariablen zugreifen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_variables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Environment_Variables
ms.openlocfilehash: c954ee6e783b7926dbcd05a3e08b6b9b5cf9bc25
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222071"
---
# <a name="about-environment-variables"></a>Informationen zu Umgebungsvariablen

## <a name="short-description"></a>KURZE BESCHREIBUNG
Hier wird beschrieben, wie Sie in PowerShell auf Windows-Umgebungsvariablen zugreifen.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Umgebungsvariablen speichern Informationen über die Betriebssystemumgebung. Diese Informationen umfassen Details wie den Betriebssystem Pfad, die Anzahl der Prozessoren, die vom Betriebssystem verwendet werden, und den Speicherort der temporären Ordner.

In den Umgebungsvariablen werden Daten gespeichert, die vom Betriebssystem und anderen Programmen verwendet werden. Die `WINDIR` Umgebungsvariable enthält z. b. den Speicherort des Windows-Installationsverzeichnisses. Programme können den Wert dieser Variablen Abfragen, um zu bestimmen, wo sich die Dateien des Windows-Betriebssystems befinden.

PowerShell kann auf Umgebungsvariablen auf allen unterstützten Betriebssystemplattformen zugreifen und diese verwalten. Der PowerShell-Umgebungs Anbieter vereinfacht diesen Prozess, indem er die Anzeige und Änderung von Umgebungsvariablen vereinfacht.

Umgebungsvariablen werden im Gegensatz zu anderen Variablen Typen in PowerShell von untergeordneten Prozessen geerbt, wie z. b. lokalen Hintergrund Aufträgen und den Sitzungen, in denen Modulmember ausgeführt werden. Dadurch eignen sich Umgebungsvariablen gut zum Speichern von Werten, die in über-und untergeordneten Prozessen benötigt werden.

## <a name="using-and-changing-environment-variables"></a>Verwenden und Ändern von Umgebungsvariablen

Unter Windows können Umgebungsvariablen in drei Bereichen definiert werden:

- Computerbereich (oder System)
- Benutzerbereich
- Prozessbereich

Der _Prozess_ Bereich enthält die Umgebungsvariablen, die im aktuellen Prozess oder in der PowerShell-Sitzung verfügbar sind. Diese Liste der Variablen wird vom übergeordneten Prozess geerbt und aus den Variablen in den Bereichen _Computer_ und _Benutzer_ erstellt. UNIX-basierte Plattformen verfügen nur über den _Prozess_ Bereich.

Sie können die Werte von Umgebungsvariablen anzeigen und ändern, ohne ein Cmdlet zu verwenden, indem Sie eine Variablen Syntax mit dem Umgebungs Anbieter verwenden. Verwenden Sie die folgende Syntax, um den Wert einer Umgebungsvariablen anzuzeigen:

```
$Env:<variable-name>
```

Wenn Sie z. b. den Wert der `WINDIR` Umgebungsvariablen anzeigen möchten, geben Sie an der PowerShell-Eingabeaufforderung den folgenden Befehl ein:

```powershell
$Env:windir
```

In dieser Syntax gibt das Dollarzeichen ( `$` ) eine Variable an, und der Laufwerks Name ( `Env:` ) gibt eine Umgebungsvariable an, gefolgt vom Variablennamen ( `windir` ).

Wenn Sie Umgebungsvariablen in PowerShell ändern, wirkt sich die Änderung nur auf die aktuelle Sitzung aus. Dieses Verhalten ähnelt dem Verhalten des `Set` Befehls in der Windows-Befehlsshell und des `Setenv` Befehls in UNIX-basierten Umgebungen. Wenn Sie Werte in den Bereichen Computer oder Benutzer ändern möchten, müssen Sie die Methoden der **System. Environment** -Klasse verwenden.

Um Änderungen an Variablen im Computerbereich vorzunehmen, muss ebenfalls über die-Berechtigung verfügen. Wenn Sie versuchen, einen Wert ohne ausreichende Berechtigungen zu ändern, schlägt der Befehl fehl, und PowerShell zeigt einen Fehler an.

Sie können die Werte von Variablen ändern, ohne ein Cmdlet mit der folgenden Syntax zu verwenden:

```powershell
$Env:<variable-name> = "<new-value>"
```

Um z. b. `;c:\temp` an den Wert der `Path` Umgebungsvariablen anzufügen, verwenden Sie die folgende Syntax:

```powershell
$Env:Path += ";c:\temp"
```

Unter Linux oder MacOS trennt der Doppelpunkt ( `:` ) im Befehl den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist.

```powershell
$Env:PATH += ":/usr/local/temp"
```

Sie können auch die Item-Cmdlets verwenden, z `Set-Item` `Remove-Item` . b., und, `Copy-Item` um die Werte von Umgebungsvariablen zu ändern. Verwenden Sie z. b. die folgende Syntax, um das `Set-Item` Cmdlet zum Anfügen `;c:\temp` an den Wert der `Path` Umgebungsvariablen zu verwenden:

```powershell
Set-Item -Path Env:Path -Value ($Env:Path + ";C:\Temp")
```

In diesem Befehl wird der Wert in Klammern eingeschlossen, sodass er als Einheit interpretiert wird.

## <a name="environment-variables-that-store-preferences"></a>Umgebungsvariablen, die Einstellungen speichern

PowerShell-Funktionen können Umgebungsvariablen verwenden, um Benutzereinstellungen zu speichern.
Diese Variablen funktionieren wie bevorzugte Variablen, werden jedoch von den untergeordneten Sitzungen der Sitzungen geerbt, in denen Sie erstellt werden. Weitere Informationen zu Einstellungs Variablen finden Sie unter [about_preference_variables](about_Preference_Variables.md).

Zu den Umgebungsvariablen, die Einstellungen speichern, gehören:

- PSExecutionPolicyPreference

  Speichert die Ausführungs Richtlinie, die für die aktuelle Sitzung festgelegt ist. Diese Umgebungsvariable ist nur vorhanden, wenn Sie eine Ausführungs Richtlinie für eine einzelne Sitzung festlegen.
  Dies kann auf zwei verschiedene Arten erfolgen.

  - Starten Sie mithilfe des **ExecutionPolicy** -Parameters eine Sitzung von der Befehlszeile aus, um die Ausführungs Richtlinie für die Sitzung festzulegen.

  - Verwenden Sie das `Set-ExecutionPolicy`-Cmdlet. Verwenden Sie den Scope-Parameter mit dem Wert "Process".

    Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).

- Psmoduleanalysiscachepath

  PowerShell bietet Kontrolle über die Datei, die zum Zwischenspeichern von Daten zu Modulen und ihren Cmdlets verwendet wird. Der Cache wird beim Start während der Suche nach einem Befehl gelesen und in einem Hintergrund Thread geschrieben, wenn ein Modul importiert wird.

  Der Standard Speicherort für den Cache lautet:

  - Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`
  - PowerShell 6,0 und höher: `$env:LOCALAPPDATA\Microsoft\PowerShell`
  - Standardeinstellung für nicht-Windows: `~/.cache/powershell`

  Der Standard Dateiname für den Cache ist `ModuleAnalysisCache` . Wenn Sie mehrere Instanzen von PowerShell installiert haben, enthält der Dateiname ein hexadezimales Suffix, sodass pro Installation ein eindeutiger Dateiname vorhanden ist.

  > [!NOTE]
  > Wenn die Befehls Ermittlung nicht ordnungsgemäß funktioniert, z. b. wenn IntelliSense Befehle anzeigt, die nicht vorhanden sind, können Sie die Cachedatei löschen. Der Cache wird beim nächsten Start von PowerShell neu erstellt.

  Um den Standard Speicherort des Caches zu ändern, legen Sie die Umgebungsvariable vor dem Starten von PowerShell fest. Änderungen an dieser Umgebungsvariablen wirken sich nur auf untergeordnete Prozesse aus. Der Wert muss einen vollständigen Pfad (samt Dateiname) definieren, in dem PowerShell die Berechtigung zum Erstellen und Schreiben von Dateien hat.

  Zum Deaktivieren des Dateicaches kann dieser Wert auf einen ungültigen Speicherort festgelegt werden. Beispiel:

  ```powershell
  # `NUL` here is a special device on Windows that cannot be written to,
  # on non-Windows you would use `/dev/null`
  $env:PSModuleAnalysisCachePath = 'NUL'
  ```

  Dadurch wird der Pfad zum **NUL** -Gerät festgelegt. PowerShell kann nicht in den Pfad schreiben, aber es wird kein Fehler zurückgegeben. Sie können die Fehler anzeigen, die mithilfe eines Tracers gemeldet werden:

  ```powershell
  Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
  ```

- Psdisablemoduleanalysiscachecleanup

  Wenn Sie den Modul Analyse Cache schreiben, prüft PowerShell, ob Module vorhanden sind, die nicht mehr vorhanden sind, um einen unnötig großen Cache zu vermeiden. Manchmal sind diese Überprüfungen nicht wünschenswert. in diesem Fall können Sie Sie deaktivieren, indem Sie diesen Umgebungsvariablen Wert auf festlegen `1` .

  Das Festlegen dieser Umgebungsvariablen tritt sofort im aktuellen Prozess in Kraft.

- PSModulePath

  Die `$env:PSModulePath` Umgebungsvariable enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden.

  Standardmäßig sind die folgenden effektiven Speicherorte zugewiesen `$env:PSModulePath` :

  - System weite Speicherorte: diese Ordner enthalten Module, die mit PowerShell ausgeliefert werden. Die Module werden am `$PSHOME\Modules` Speicherort gespeichert. Außerdem ist dies der Speicherort, an dem die Windows-Verwaltungs Module installiert werden.

  - Vom Benutzer installierte Module: Dies sind Module, die vom Benutzer installiert werden.
    `Install-Module` verfügt über einen **Scope** -Parameter, mit dem Sie angeben können, ob das Modul für den aktuellen Benutzer oder für alle Benutzer installiert ist. Weitere Informationen finden Sie unter [Install-Module](xref:PowerShellGet.Install-Module).

    - Unter Windows ist der Speicherort des benutzerspezifischen **CurrentUser** -Bereichs der `$HOME\Documents\PowerShell\Modules` Ordner. Der Speicherort des **ALLUSERS** -Bereichs ist `$env:ProgramFiles\PowerShell\Modules` .
    - Bei nicht-Windows-Systemen ist der Speicherort des benutzerspezifischen **CurrentUser** -Bereichs der `$HOME/.local/share/powershell/Modules` Ordner. Der Speicherort des **ALLUSERS** -Bereichs ist `/usr/local/share/powershell/Modules` .

  Außerdem können Setup Programme, die Module in anderen Verzeichnissen installieren, z. b. das Verzeichnis "Programme", ihre Speicherorte an den Wert von anfügen `$env:PSModulePath` .

  Weitere Informationen finden Sie unter [about_PSModulePath](about_PSModulePath.md).

## <a name="managing-environment-variables"></a>Verwalten von Umgebungsvariablen

PowerShell bietet verschiedene Methoden zum Verwalten von Umgebungsvariablen.

- Das Umgebungs Anbieter Laufwerk
- Die Item-Cmdlets
- Die .NET-Klasse " **System. Environment** "
- Unter Windows die System Steuerung

### <a name="using-the-environment-provider"></a>Verwenden des Umgebungs Anbieters

Jede Umgebungsvariable wird durch eine Instanz der Klasse **System. Collections. ditionaryentry** dargestellt. In jedem " **diktaryentry** "-Objekt ist der Name der Umgebungsvariablen der Wörterbuch Schlüssel. Der Wert der Variablen ist der Wörterbuch Wert.

Verwenden Sie das-Cmdlet, um die Eigenschaften und Methoden des Objekts anzuzeigen, das eine Umgebungsvariable in PowerShell darstellt `Get-Member` . Wenn Sie z. b. die Methoden und Eigenschaften aller Objekte im Laufwerk anzeigen möchten, geben Sie Folgendes ein `Env:` :

```powershell
Get-Item -Path Env:* | Get-Member
```

Mit dem PowerShell-Umgebungs Anbieter können Sie auf Umgebungsvariablen in einem PowerShell-Laufwerk ( `Env:` Laufwerk) zugreifen. Dieses Laufwerk sieht in etwa wie ein Dateisystem Laufwerk aus. Um zum Laufwerk zu wechseln, geben Sie Folgendes ein `Env:` :

```powershell
Set-Location Env:
```

Verwenden Sie die Content-Cmdlets, um die Werte einer Umgebungsvariablen zu erhalten oder festzulegen.

```powershell
PS Env:\> Set-Content -Path Test -Value 'Test value'
PS Env:\> Get-Content -Path Test
Test value
```

Sie können die Umgebungsvariablen auf dem `Env:` Laufwerk von einem beliebigen anderen PowerShell-Laufwerk anzeigen, und Sie können das `Env:` Laufwerk aufrufen, um die Umgebungsvariablen anzuzeigen und zu ändern.

### <a name="using-item-cmdlets"></a>Verwenden von Item-Cmdlets

Wenn Sie auf eine Umgebungsvariable verweisen, geben Sie den `Env:` Namen des Laufwerks gefolgt vom Namen der Variablen ein. Wenn Sie z. b. den Wert der `COMPUTERNAME` Umgebungsvariablen anzeigen möchten, geben Sie Folgendes ein:

```powershell
Get-ChildItem Env:Computername
```

Geben Sie Folgendes ein, um die Werte aller Umgebungsvariablen anzuzeigen:

```powershell
Get-ChildItem Env:
```

Da Umgebungsvariablen keine untergeordneten Elemente aufweisen, ist die Ausgabe von `Get-Item` und `Get-ChildItem` identisch.

Standardmäßig zeigt PowerShell die Umgebungsvariablen in der Reihenfolge an, in der Sie abgerufen werden. Übergeben Sie die Ausgabe eines `Get-ChildItem` Befehls an das Cmdlet, um die Liste der Umgebungsvariablen nach dem Variablennamen zu sortieren `Sort-Object` . Geben Sie beispielsweise von einem beliebigen PowerShell-Laufwerk Folgendes ein:

```powershell
Get-ChildItem Env: | Sort Name
```

Sie können auch mit dem- `Env:` Cmdlet auf das Laufwerk wechseln `Set-Location` :

```powershell
Set-Location Env:
```

Wenn Sie sich auf dem `Env:` Laufwerk befinden, können Sie den `Env:` Namen des Laufwerks aus dem Pfad weglassen. Wenn Sie z. b. alle Umgebungsvariablen anzeigen möchten, geben Sie Folgendes ein:

```powershell
PS Env:\> Get-ChildItem
```

Wenn Sie den Wert der `COMPUTERNAME` Variablen innerhalb des Laufwerks anzeigen möchten, geben Sie Folgendes ein `Env:` :

```powershell
PS Env:\> Get-ChildItem ComputerName
```

### <a name="saving-changes-to-environment-variables"></a>Speichern von Änderungen an Umgebungsvariablen

Verwenden Sie die System Steuerung, um eine dauerhafte Änderung an einer Umgebungsvariablen unter Windows vorzunehmen. Wählen Sie **Erweiterte System Einstellungen** aus. Klicken Sie auf der Registerkarte **erweitert** auf **Umgebungs Variable...**. Sie können vorhandene Umgebungsvariablen im Bereich " **Benutzer** " und " **System** " (Computer) hinzufügen oder bearbeiten. Diese Werte werden von Windows in die Registrierung geschrieben, sodass Sie Sitzungs übergreifend und Systemneustarts beibehalten werden.

Alternativ können Sie Umgebungsvariablen in Ihrem PowerShell-Profil hinzufügen oder ändern. Diese Methode funktioniert für jede Version von PowerShell auf allen unterstützten Plattformen.

### <a name="using-systemenvironment-methods"></a>Verwenden von System. Environment-Methoden

Die **System. Environment** -Klasse stellt die Methoden **GetEnvironmentVariable** und **ltenvironmentvariable** bereit, die es Ihnen ermöglichen, den Gültigkeitsbereich der Variablen anzugeben.

Im folgenden Beispiel wird die **GetEnvironmentVariable** -Methode verwendet, um die Computer Einstellung von `PSModulePath` und die Methode "-Methode" zu erhalten, um den **SetEnvironmentVariable** `C:\Program Files\Fabrikam\Modules` Pfad zum Wert hinzuzufügen.

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable("PSModulePath", $newpath, 'Machine')
```

Weitere Informationen zu den Methoden der **System. Environment** -Klasse finden Sie unter [Umgebungs Methoden](/dotnet/api/system.environment).

## <a name="see-also"></a>SIEHE AUCH

- [Umgebung (Anbieter)](../About/about_Environment_Provider.md)
- [about_Modules](about_Modules.md)

