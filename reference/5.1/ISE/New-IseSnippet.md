---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/new-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-IseSnippet
ms.openlocfilehash: 0ed1c2913fc7531574bfbdd435a002d60931d24a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212380"
---
# New-IseSnippet

## ZUSAMMENFASSUNG
Erstellt einen Windows PowerShell ISE-Codeausschnitt.

## SYNTAX

```
New-IseSnippet [-Title] <String> [-Description] <String> [-Text] <String> [-Author <String>]
 [-CaretOffset <Int32>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

Das- `New-ISESnippet` Cmdlet erstellt einen wiederverwendbaren Text Ausschnitt für Windows PowerShell ISE. Sie können Codeausschnitte verwenden, um dem Skriptbereich oder dem Befehlsbereich in Windows PowerShell ISE Text hinzufügen. Dieses Cmdlet ist nur in Windows PowerShell ISE verfügbar.

Ab Windows PowerShell 3.0 enthält Windows PowerShell ISE eine Auflistung von integrierten Codeausschnitten. Mit dem- `New-ISESnippet` Cmdlet können Sie eigene Ausschnitte erstellen, die der integrierten Auflistung hinzugefügt werden sollen. Sie können Codeausschnittsdateien anzeigen, ändern, hinzufügen, löschen und freigeben sowie in Windows PowerShell-Module einschließen. Um Ausschnitte in Windows PowerShell ISE anzuzeigen, wählen Sie im Menü **Bearbeiten** die Option **Ausschnitte starten** aus, oder drücken Sie <kbd>STRG</kbd> + <kbd>J</kbd>.

Das- `New-ISESnippet` Cmdlet erstellt eine `<Title>.Snippets.ps1xml` Datei im `$home\Documents\WindowsPowerShell\Snippets` Verzeichnis mit dem von Ihnen angegebenen Titel. Um eine Codeausschnittsdatei in ein Modul einzuschließen, das Sie erstellen, fügen Sie die Codeausschnittsdatei einem Unterverzeichnis „Snippets“ Ihres Modulverzeichnisses hinzu.

Benutzer erstellte Code Ausschnitte können nicht in einer Sitzung verwendet werden, in der die Ausführungs Richtlinie **eingeschränkt** oder **AllSigned** ist.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Erstellen eines Comment-Based-Hilfe Ausschnitts

```
New-IseSnippet -Title Comment-BasedHelp -Description "A template for comment-based help." -Text "<#
    .SYNOPSIS

    .DESCRIPTION
    .PARAMETER  <Parameter-Name>
    .INPUTS
    .OUTPUTS
    .EXAMPLE
    .LINK
#>"
```

Dieser Befehl erstellt einen Comment-BasedHelp-Codeausschnitt für Windows PowerShell ISE. Er erstellt eine Datei namens `Comment-BasedHelp.snippets.ps1xml` im Verzeichnis "Snippets" des Benutzers `$home\Documents\WindowsPowerShell\Snippets` .

### Beispiel 2: Erstellen eines obligatorischen Ausschnitts

```
$M = @'
Param
(
  [parameter(Mandatory=$true)]
  [String[]]
  $<ParameterName>
)
'@

New-ISESnippet -Text $M -Title Mandatory -Description "Adds a mandatory function parameter." -Author "Patti Fuller, Fabrikam Corp." -Force
```

In diesem Beispiel wird ein Ausschnitt namens " **obligatorisch** " für Windows PowerShell ISE erstellt. Der erste Befehl speichert den Ausschnitt Text in der `$M` Variablen. Der zweite Befehl verwendet das `New-ISESnippet` Cmdlet zum Erstellen des Code Ausschnitts. Der Befehl verwendet den **Force** -Parameter zum Überschreiben eines vorherigen Codeausschnitts mit dem gleichen Namen.

### Beispiel 3: Kopieren eines obligatorischen Ausschnitts aus einem Ordner in einen Zielordner

```
Copy-Item "$Home\Documents\WindowsPowerShell\Snippets\Mandatory.Snippets.ps1xml" -Destination "\\Server\Share"
```

Dieser Befehl verwendet das `Copy-Item` Cmdlet, um den **obligatorischen** Ausschnitt aus dem Ordner zu kopieren, in dem `New-ISESnippet` Sie in die Dateifreigabe "Server\Freigabe" eingefügt wird.

## PARAMETERS

### -Autor

Gibt den Autor des Code Ausschnitts an. Das Autorfeld wird in der Codeausschnittsdatei angezeigt, aber es wird nicht eingeblendet, wenn Sie in Windows PowerShell ISE auf den Codeausschnittsnamen klicken.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Careworffset

Gibt das Zeichen des Ausschnitt Texts an, auf dem dieses Cmdlet den Cursor platziert. Geben Sie eine ganze Zahl zur Darstellung der Cursorposition ein, wobei „1“ das erste Textzeichen darstellt. Der Standardwert 0 (null) platziert den Cursor unmittelbar vor dem ersten Textzeichen. Dieser Parameter rückt den Codeausschnittstext nicht ein.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Gibt eine Beschreibung des Code Ausschnitts an. Der Beschreibungswert wird angezeigt, wenn Sie in Windows PowerShell ISE auf den Codeausschnittsnamen klicken. Dieser Parameter ist erforderlich.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Gibt an, dass dieses Cmdlet Ausschnitt Dateien mit demselben Namen am gleichen Speicherort überschreibt. Standardmäßig werden von keine `New-ISESnippet` Dateien überschrieben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Text

Gibt den Textwert an, der hinzugefügt wird, wenn Sie den Codeausschnitt auswählen. Der Codeausschnittstext wird angezeigt, wenn Sie in Windows PowerShell ISE auf den Codeausschnittsnamen klicken. Dieser Parameter ist erforderlich.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

Gibt einen Titel oder einen Namen für den Codeausschnitt an. Der Titel dient auch als Name der Codeausschnittsdatei. Dieser Parameter ist erforderlich.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

`New-IseSnippet` speichert neue Benutzer erstellte Code Ausschnitte in unsignierten ps1xml-Dateien. Daher kann Windows PowerShell sie nicht zu Sitzungen hinzufügen, in denen die Ausführungsrichtlinie **AllSigned** oder **Restricted** gilt. In einer Sitzung mit der Ausführungsrichtlinie **Restricted** oder **AllSigned** können Sie zwar unsignierte benutzererstellte Codeausschnitte erstellen, abrufen und importieren, aber nicht in der Sitzung verwenden.

Wenn Sie das `New-IseSnippet` Cmdlet in einer **eingeschränkten** oder **AllSigned** -Sitzung verwenden, wird der Ausschnitt erstellt, aber es wird eine Fehlermeldung angezeigt, wenn Windows PowerShell versucht, den neu erstellten Ausschnitt der Sitzung hinzuzufügen. Um den neuen Codeausschnitt (und andere unsignierte benutzererstellte Codeausschnitte) zu verwenden, ändern Sie die Ausführungsrichtlinie, und starten Sie Windows PowerShell ISE neu.

Weitere Informationen zu Windows PowerShell-Ausführungsrichtlinien finden Sie unter about_Execution_Policies.

- Um einen Ausschnitt zu ändern, bearbeiten Sie die codeausschnittsdatei. Sie können Ausschnitt Dateien im Skript Bereich von Windows PowerShell ISE bearbeiten.
- Um einen hinzugefügten Code Ausschnitt zu löschen, löschen Sie die codeausschnittsdatei.
- Ein integrierter Ausschnitt kann nicht gelöscht werden, Sie können jedoch alle integrierten Code Ausschnitte ausblenden, indem Sie die $psise verwenden. Options. showdefaulsnippets = $false "Befehl.
- Sie können einen Ausschnitt erstellen, der denselben Namen wie ein integrierter Ausschnitt hat. Beide Codeausschnitte werden im Codeausschnittsmenü in Windows PowerShell ISE angezeigt.

## VERWANDTE LINKS

[Get-IseSnippet](Get-IseSnippet.md)

[Import-IseSnippet](Import-IseSnippet.md)
