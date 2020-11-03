---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/get-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IseSnippet
ms.openlocfilehash: c43dae3f178ae778d78fe3718fa85fd2635eba86
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218103"
---
# Get-IseSnippet

## ZUSAMMENFASSUNG
Ruft vom Benutzer erstellte Codeausschnitte ab.

## SYNTAX

```
Get-IseSnippet [<CommonParameters>]
```

## DESCRIPTION

Das `Get-IseSnippet` Cmdlet ruft die PS1XML-Dateien ab, die wiederverwendbare Textausschnitte enthalten, die vom Benutzer erstellt wurden. Dies funktioniert nur in Windows PowerShell Integrated Scripting Environment (ISE).

Wenn Sie mit dem `New-IseSnippet` Cmdlet einen Ausschnitt erstellen, wird von `New-IseSnippet` eine `<SnippetTitle>.Snippets.ps1xml` Datei im Verzeichnis erstellt `$home\Documents\WindowsPowerShell\Snippets` .
`Get-IseSnippet` Ruft die Ausschnitt Dateien im Verzeichnis "Snippets" ab.

Dieses Cmdlet erhält keine integrierten Code Ausschnitte oder Ausschnitte, die aus Modulen über das `Import-IseSnippet` Cmdlet importiert werden.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: alle benutzerdefinierten Ausschnitte erhalten

In diesem Beispiel werden alle benutzerdefinierten Code Ausschnitte im Verzeichnis "Snippets" abgerufen.

```powershell
Get-IseSnippet
```

### Beispiel 2: Kopieren aller benutzerdefinierten Code Ausschnitte von Remote Computern in ein frei gegebenes Verzeichnis

In diesem Beispiel werden alle vom Benutzer erstellten Code Ausschnitte aus einer Gruppe von Remote Computern in ein frei gegebenes Verzeichnis "Snippets" kopiert.

```powershell
Invoke-Command -Computer (Get-Content Servers.txt) {Get-IseSnippet | Copy-Item -Destination \\Server01\Share01\Snippets}
```

`Invoke-Command` wird `Get-IseSnippet` auf den Computern in der `Servers.txt` Datei ausgeführt. Ein Pipeline Operator ( `|` ) sendet die Ausschnitt Dateien an das `Copy-Item` Cmdlet, das Sie in das durch den **Ziel** Parameter angegebene Verzeichnis kopiert.

### Beispiel 3: Anzeigen des Titels und Texts jedes Ausschnitts auf einem lokalen Computer

In diesem Beispiel werden die `Get-IseSnippet` -und- `Select-Xml` Cmdlets verwendet, um den Titel und den Text jedes Ausschnitts auf dem lokalen Computer anzuzeigen.

```powershell
#Parse-Snippet Function
function Parse-Snippet {
  $SnippetFiles = Get-IseSnippet
  $SnippetNamespace = @{x="http://schemas.microsoft.com/PowerShell/Snippets"}
  foreach ($SnippetFile in $SnippetFiles) {
     Write-Host ""
     $Title = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Title" |
       ForEach-Object {$_.Node.InnerXML}
     $Text = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Script" |
       ForEach-Object {$_.Node.InnerText}
     Write-Host "Title: $Title"
     Write-Host "Text: $Text"
   }
}
```

```Output
Title: Mandatory
Text:
Param
(
  [parameter(Mandatory=True)]
  [String[]]
  $<ParameterName>
)

Title: Copyright
Text:  (c) Fabrikam, Inc. 2012
```

### Beispiel 4: Anzeigen des Titels und der Beschreibung aller Ausschnitte in der Sitzung

In diesem Beispiel werden der Titel und die Beschreibung aller Code Ausschnitte in der Sitzung angezeigt, einschließlich integrierter Code Ausschnitte, benutzerdefinierter Code Ausschnitte und importierter Code Ausschnitte.

```powershell
$PSISE.CurrentPowerShellTab.Snippets | Format-Table DisplayTitle, Description
```

Die- `$PSISE` Variable stellt das Windows PowerShell ISE Host Programm dar. Die **currentpowershelltab** -Eigenschaft der `$PSISE` Variablen stellt die aktuelle Sitzung dar. Die **Snippets** -Eigenschaft stellt Codeausschnitte in der aktuellen Sitzung dar.

Der `$PSISE.CurrentPowerShellTab.Snippets` Befehl gibt ein **Microsoft. PowerShell. Host. ISE. isesnippet** -Objekt zurück, das einen Ausschnitt darstellt, im Gegensatz zum `Get-IseSnippet` Cmdlet. `Get-IseSnippet` Gibt ein Datei Objekt (System. IO. FileInfo) zurück, das eine codeausschnittsdatei darstellt.

`Format-Table`Mit dem-Cmdlet werden die Eigenschaften **Display Title** und **Description** der Code Ausschnitte in einer Tabelle angezeigt.

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

### System. IO. fileingefo

Dieses Cmdlet gibt ein Datei Objekt zurück, das die codeausschnittsdatei darstellt.

## HINWEISE

* Das- `New-IseSnippet` Cmdlet speichert neue Benutzer erstellte Code Ausschnitte in unsignierten ps1xml-Dateien. Daher kann Windows PowerShell sie nicht zu Sitzungen hinzufügen, in denen die Ausführungsrichtlinie **AllSigned** oder **Restricted** gilt. In einer Sitzung mit der Ausführungsrichtlinie **Restricted** oder **AllSigned** können Sie zwar unsignierte benutzererstellte Codeausschnitte erstellen, abrufen und importieren, aber nicht in der Sitzung verwenden.

  Um nicht signierte Benutzer erstellte Code Ausschnitte zu verwenden, die vom `Get-IseSnippet` Cmdlet zurückgegeben werden, ändern Sie die Ausführungs Richtlinie, und starten Sie Windows PowerShell ISE neu.

  Weitere Informationen zu Windows PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

## VERWANDTE LINKS

[New-IseSnippet](New-IseSnippet.md)

[Import-IseSnippet](Import-IseSnippet.md)
