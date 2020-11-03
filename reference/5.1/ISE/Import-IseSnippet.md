---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/import-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IseSnippet
ms.openlocfilehash: 810be675fc593f665ccc6f3d5b86ac2f6b633863
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212383"
---
# Import-IseSnippet

## ZUSAMMENFASSUNG
Importiert ISE-Codeausschnitte in die aktuelle Sitzung.

## SYNTAX

### Fromfolder (Standard)

```
Import-IseSnippet [-Path] <String> [-Recurse] [<CommonParameters>]
```

### Frommodule

```
Import-IseSnippet [-Recurse] -Module <String> [-ListAvailable] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Import-IseSnippet` Cmdlet werden wiederverwendbare Textausschnitte aus einem Modul oder einem Verzeichnis in die aktuelle Sitzung importiert. Die Ausschnitte sind sofort für die Verwendung in Windows PowerShell ISE verfügbar. Dieses Cmdlet funktioniert nur in Windows PowerShell Integrated Scripting Environment (ISE).

Um die importierten Ausschnitte anzuzeigen und zu verwenden, klicken Sie im Menü Windows PowerShell ISE **Bearbeiten** auf Code **Ausschnitte starten** , oder drücken Sie <kbd>STRG</kbd> + <kbd>J</kbd>.

Importierte Codeausschnitte sind nur in der aktuellen Sitzung verfügbar. Um die Code Ausschnitte in alle Windows PowerShell ISE Sitzungen zu importieren, fügen Sie `Import-IseSnippet` Ihrem Windows PowerShell-Profil einen Befehl hinzu, oder kopieren Sie die codeausschnittsdateien in das lokale Verzeichnis "Snippets" `$home\Documents\WindowsPowershell\Snippets` .

Um Ausschnitte zu importieren, müssen Sie in der Ausschnitt-XML-Datei für Windows PowerShell ISE Ausschnitte ordnungsgemäß formatiert und in Snippet.ps1XML-Dateien gespeichert werden. Um berechtigte Ausschnitte zu erstellen, verwenden Sie das- `New-IseSnippet` Cmdlet. `New-IseSnippet` erstellt eine `<SnippetTitle>.Snippets.ps1xml` Datei im `$home\Documents\WindowsPowerShell\Snippets` Verzeichnis. Sie können die Codeausschnitte in das Verzeichnis „Snippets“ eines Windows PowerShell-Moduls oder in ein beliebiges anderen Verzeichnis verschieben oder kopieren.

`Get-IseSnippet`Mit dem-Cmdlet, das vom Benutzer erstellte Code Ausschnitte im Verzeichnis "local Snippets" abruft, werden keine importierten Ausschnitte abgerufen.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Importieren von Ausschnitten aus einem Verzeichnis

In diesem Beispiel werden die Code Ausschnitte aus dem `\\Server01\Public\Snippets` Verzeichnis in die aktuelle Sitzung importiert. Er verwendet den **recurse** -Parameter, um Code Ausschnitte aus allen Unterverzeichnissen des Verzeichnisses "Snippets" abzurufen.

```powershell
Import-IseSnippet -Path \\Server01\Public\Snippets -Recurse
```

### Beispiel 2: Importieren von Ausschnitten aus einem Modul

In diesem Beispiel werden die Code Ausschnitte aus dem **snippetmodule** -Modul importiert. Der Befehl verwendet den **listavailable** -Parameter, um die Code Ausschnitte zu importieren, auch wenn das **snippetmodule** -Modul nicht in die Sitzung des Benutzers importiert wird, wenn der Befehl ausgeführt wird.

```powershell
Import-IseSnippet -Module SnippetModule -ListAvailable
```

### Beispiel 3: Suchen von Code Ausschnitten in Modulen

In diesem Beispiel werden Ausschnitte in allen installierten Modulen in der psmodulepath-Umgebungsvariablen abgerufen.

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$_.fullname}
```

### Beispiel 4: Importieren aller Modul Ausschnitte

In diesem Beispiel werden alle Ausschnitte aus allen installierten Modulen in die aktuelle Sitzung importiert. In der Regel müssen Sie keinen Befehl wie diesen ausführen, da Module mit Code `Import-IseSnippet` Ausschnitten das Cmdlet verwenden, um Sie beim Importieren des Moduls für Sie zu importieren.

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$psise.CurrentPowerShellTab.Snippets.Load($_)}
```

### Beispiel 5: Kopieren aller Modul Ausschnitte

In diesem Beispiel werden die Ausschnitt Dateien aus allen installierten Modulen in das Verzeichnis "Snippets" des aktuellen Benutzers kopiert. Im Gegensatz zu importierten Codeausschnitten, die nur die aktuelle Sitzung betreffen, sind die kopierten Codeausschnitte in jeder Windows PowerShell ISE-Sitzung verfügbar.

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    Copy-Item -Destination $home\Documents\WindowsPowerShell\Snippets
```

## PARAMETERS

### -Listavailable

Gibt an, dass dieses Cmdlet Code Ausschnitte aus Modulen abruft, die auf dem Computer installiert sind, selbst wenn die Module nicht in die aktuelle Sitzung importiert werden. Wenn dieser Parameter ausgelassen wird und das vom **Modul** Parameter angegebene Modul nicht in die aktuelle Sitzung importiert wird, schlägt der Versuch fehl, die Ausschnitte aus dem Modul zu erhalten.

Dieser Parameter ist nur gültig, wenn der **Module** -Parameter im Befehl verwendet wird.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromModule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Modul

Importiert Codeausschnitte aus dem angegebenen Modul in die aktuelle Sitzung. Platzhalterzeichen werden nicht unterstützt.

Dieser Parameter importiert Ausschnitte aus Snippet.ps1XML-Dateien im Unterverzeichnis "Snippets" im Modulpfad, z `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets` . b..

Dieser Parameter ist für die Verwendung durch Modulautoren in einem Startskript gedacht, wie z. B. ein im **ScriptsToProcess** -Schlüssel eines Modulmanifests angegebenes Modul. Ausschnitte in einem Modul werden nicht automatisch mit dem Modul importiert, Sie können jedoch einen Befehl verwenden, `Import-IseSnippet` um Sie zu importieren.

```yaml
Type: System.String
Parameter Sets: FromModule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zum Verzeichnis "Snippets" an, in dem das Cmdlet Ausschnitte importiert.

```yaml
Type: System.String
Parameter Sets: FromFolder
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Recurse

Gibt an, dass dieses Cmdlet Ausschnitte aus allen Unterverzeichnissen des Werts des **path** -Parameters importiert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Dieses Cmdlet nimmt keine Eingabe von der Pipeline an.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

- Sie können das `Get-IseSnippet` Cmdlet nicht verwenden, um importierte Ausschnitte zu erhalten. `Get-IseSnippet` Ruft nur Ausschnitte im `$home\Documents\WindowsPowerShell\Snippets` Verzeichnis ab.
- `Import-IseSnippet` verwendet die statische **Lade** Methode von **Microsoft. PowerShell. Host. ISE. isesnippetcollection** -Objekten. Sie können auch die **Load** -Methode von Code Ausschnitten im Windows PowerShell ISE-Objektmodell verwenden: `$psISE.CurrentPowerShellTab.Snippets.Load()`
- Das- `New-IseSnippet` Cmdlet speichert neue Benutzer erstellte Code Ausschnitte in unsignierten ps1xml-Dateien. Daher kann Windows PowerShell sie nicht in Sitzungen laden, in denen die Ausführungsrichtlinie **AllSigned** oder **Restricted** gilt. In einer Sitzung mit der Ausführungsrichtlinie **Restricted** oder **AllSigned** können Sie zwar unsignierte benutzererstellte Codeausschnitte erstellen, abrufen und importieren, aber nicht in der Sitzung verwenden.

  Um nicht signierte Benutzer erstellte Code Ausschnitte zu verwenden, die vom `Import-IseSnippet` Cmdlet zurückgegeben werden, ändern Sie die Ausführungs Richtlinie, und starten Sie Windows PowerShell ISE neu.

  Weitere Informationen zu Windows PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

## VERWANDTE LINKS

[Get-IseSnippet](Get-IseSnippet.md)

[New-IseSnippet](New-IseSnippet.md)
