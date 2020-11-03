---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-help?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Help
ms.openlocfilehash: 1a4a3f7050c3da2a73ae0d5319938117284076b7
ms.sourcegitcommit: 05f578d3fca0d9663bb1e4f76e2f14604f5303ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "93219847"
---
# Get-Help

## ZUSAMMENFASSUNG
Zeigt Informationen zu PowerShell-Befehlen und-Konzepten an.

## SYNTAX

### Allusersview (Standard)

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Full] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### Detailedview

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Detailed
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### Beispiele

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Examples
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### Parameter

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Parameter <String[]>
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### Online

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Online [<CommonParameters>]
```

### ShowWindow

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -ShowWindow [<CommonParameters>]
```

## DESCRIPTION

Das `Get-Help` -Cmdlet zeigt Informationen zu PowerShell-Konzepten und-Befehlen an, einschließlich Cmdlets, Funktionen, Common Information Model (CIM)-Befehlen, Workflows, Anbietern, Aliase und Skripts.

Um Hilfe zu einem PowerShell-Cmdlet zu erhalten, geben Sie `Get-Help` gefolgt vom Namen des Cmdlets ein, z `Get-Help Get-Process` . b.:.

Konzeptionelle Hilfeartikel in PowerShell beginnen mit **About_** , z. b. **about_Comparison_Operators**. Wenn Sie alle **About_** Artikel anzeigen möchten, geben Sie ein `Get-Help about_*` . Um einen bestimmten Artikel anzuzeigen, geben Sie ein `Get-Help about_<article-name>` , z `Get-Help about_Comparison_Operators` . b..

Um Hilfe zu einem PowerShell-Anbieter zu erhalten, geben Sie `Get-Help` gefolgt vom Anbieter Namen ein. Wenn Sie z. b. Hilfe zum Zertifikat Anbieter benötigen, geben Sie ein `Get-Help Certificate` .

Sie können auch `help` oder eingeben `man` , das jeweils jeweils einen Bildschirm anzeigt. Oder, `<cmdlet-name> -?` das ist mit identisch `Get-Help` , funktioniert aber nur für Cmdlets.

`Get-Help` Ruft den Hilfe Inhalt ab, der von Hilfedateien auf Ihrem Computer angezeigt wird. Ohne die Hilfedateien `Get-Help` zeigt nur grundlegende Informationen zu Cmdlets an. Einige PowerShell-Module enthalten Hilfedateien. Ab PowerShell 3,0 enthalten die Module, die im Lieferumfang des Windows-Betriebssystems enthalten sind, keine Hilfedateien. Verwenden Sie das-Cmdlet, um die Hilfedateien für ein Modul in PowerShell 3,0 herunterzuladen oder zu aktualisieren `Update-Help` .

Sie können die PowerShell-Hilfedokumente auch online im Microsoft-Dokumentation anzeigen. Um die Online Version einer Hilfedatei zu erhalten, verwenden Sie den **Online-** Parameter, z `Get-Help Get-Process -Online` . b.:. Informationen zum Lesen der gesamten PowerShell-Dokumentation finden Sie in der Microsoft-Dokumentation [PowerShell-Dokumentation](/powershell).

Wenn Sie eingeben `Get-Help` , gefolgt vom exakten Namen eines Hilfe Artikels oder durch ein Wort, das für einen Hilfeartikel eindeutig ist, `Get-Help` zeigt den Inhalt des Artikels an. Wenn Sie den genauen Namen eines befehlsalias angeben, wird `Get-Help` die Hilfe für den ursprünglichen Befehl angezeigt. Wenn Sie ein Word-oder Word-Muster eingeben, das in mehreren Hilfeartikel Titeln angezeigt wird, `Get-Help` zeigt eine Liste der übereinstimmenden Titel an. Wenn Sie Text eingeben, der nicht in den Titeln von Hilfe Artikeln enthalten ist, wird `Get-Help` von eine Liste mit Artikeln angezeigt, die diesen Text im Inhalt enthalten.

`Get-Help` kann Hilfeartikel für alle unterstützten Sprachen und Gebiets Schemas erhalten. `Get-Help` sucht zuerst nach Hilfedateien im Gebiets Schema, das für Windows festgelegt ist, und dann im übergeordneten Gebiets Schema, z. b. **PT** für **pt-br** , und dann in einem Fall Back Gebiets Schema. Wenn in PowerShell 3,0 `Get-Help` keine Hilfe im Fall Back Gebiets Schema gefunden wird, sucht es nach Hilfe Artikeln in englischer Sprache ( **en-US** ), bevor eine Fehlermeldung zurückgegeben oder automatisch generierte Hilfe angezeigt wird.

Informationen zu den Symbolen, die `Get-Help` im Befehlssyntax Diagramm angezeigt werden, finden Sie unter [about_Command_Syntax](./About/about_Command_Syntax.md).
Weitere Informationen zu Parameter Attributen, wie z. b. **Required** und **Position** , finden Sie unter [about_Parameters](./About/about_Parameters.md).

>[!NOTE]
> In PowerShell 3,0 und PowerShell 4,0 `Get-Help` können Artikel nicht **About** in Modulen gefunden werden, es sei denn, das Modul wird in die aktuelle Sitzung importiert. Dies ist ein bekanntes Problem. Um **Informationen über** Artikel in einem Modul zu erhalten, importieren Sie das Modul entweder mithilfe des- `Import-Module` Cmdlets oder durch Ausführen eines Cmdlets, das im Modul enthalten ist.

## BEISPIELE

### Beispiel 1: Anzeigen grundlegender Hilfe Informationen zu einem Cmdlet

In diesen Beispielen werden grundlegende Hilfe Informationen zum `Format-Table` Cmdlet angezeigt.

```powershell
Get-Help Format-Table
Get-Help -Name Format-Table
Format-Table -?
```

`Get-Help <cmdlet-name>` ist die einfachste und standardmäßige Syntax des `Get-Help` Cmdlets. Sie können den **Name** -Parameter weglassen.

Die Syntax `<cmdlet-name> -?` funktioniert nur für Cmdlets.

### Beispiel 2: Anzeigen von grundlegenden Informationen auf einer Seite

In diesen Beispielen werden grundlegende Hilfe Informationen zum- `Format-Table` Cmdlet nacheinander angezeigt.

```powershell
help Format-Table
man Format-Table
Get-Help Format-Table | Out-Host -Paging
```

`help` ist eine Funktion, die das `Get-Help` Cmdlet intern ausführt und das Ergebnis jeweils eine Seite anzeigt.

`man` ist ein Alias für die- `help` Funktion.

`Get-Help Format-Table` sendet das Objekt über die Pipeline. `Out-Host -Paging` empfängt die Ausgabe der Pipeline und zeigt Sie jeweils auf einer Seite an. Weitere Informationen finden Sie unter [Out-Host](Out-Host.md).

### Beispiel 3: Anzeigen von weiteren Informationen zu einem Cmdlet

In diesen Beispielen werden ausführlichere Hilfe Informationen zum `Format-Table` Cmdlet angezeigt.

```powershell
Get-Help Format-Table -Detailed
Get-Help Format-Table -Full
```

Der **ausführliche** Parameter zeigt die ausführliche Ansicht des Hilfe Artikels an, die Parameter Beschreibungen und Beispiele enthält.

Der **vollständige** Parameter zeigt die vollständige Ansicht des Hilfe Artikels an, die Parameter Beschreibungen, Beispiele, Eingabe-und Ausgabe Objekttypen sowie weitere Hinweise enthält.

Die **detaillierten** und **vollständigen** Parameter sind nur für die Befehle wirksam, bei denen Hilfedateien auf dem Computer installiert sind. Die Parameter sind für die konzeptionellen Hilfeartikel ( **About_** ) nicht wirksam.

### Beispiel 4: Anzeigen ausgewählter Teile eines Cmdlets mithilfe von Parametern

In diesen Beispielen werden ausgewählte Teile der `Format-Table` Cmdlet-Hilfe angezeigt.

```powershell
Get-Help Format-Table -Examples
Get-Help Format-Table -Parameter *
Get-Help Format-Table -Parameter GroupBy
```

Der Parameter " **examples** " zeigt den **Namen** und die **Synopsis** -Abschnitte der Hilfedatei sowie alle Beispiele an. Sie können keine Beispiel Zahl angeben, da der **examples** -Parameter ein Switch-Parameter ist.

Der **Parameter** Parameter zeigt nur die Beschreibungen der angegebenen Parameter an. Wenn Sie nur das Sternchen ()-Platzhalter `*` Zeichen angeben, werden die Beschreibungen aller Parameter angezeigt.
Wenn **Parameter** einen Parameternamen (z. b. **GroupBy** ) angibt, werden Informationen zu diesem Parameter angezeigt.

Diese Parameter sind für die konzeptionellen Hilfeartikel ( **About_** ) nicht wirksam.

### Beispiel 5: Anzeigen der Online Version der Hilfe

In diesem Beispiel wird die Online Version des Hilfe Artikels für das `Format-Table` Cmdlet in Ihrem Standard Webbrowser angezeigt.

```powershell
Get-Help Format-Table -Online
```

### Beispiel 6: Anzeigen der Hilfe zum Hilfesystem

Das- `Get-Help` Cmdlet ohne Parameter zeigt Informationen zum PowerShell-Hilfesystem an.

```powershell
Get-Help
```

### Beispiel 7: Anzeigen der verfügbaren Hilfeartikel

In diesem Beispiel wird eine Liste aller Hilfeartikel angezeigt, die auf Ihrem Computer verfügbar sind.

```powershell
Get-Help *
```

### Beispiel 8: Anzeigen einer Liste von konzeptionellen Artikeln

In diesem Beispiel wird eine Liste mit den konzeptionellen Artikeln angezeigt, die in der PowerShell-Hilfe enthalten sind. Alle diese Artikel beginnen mit den Zeichen **About_**. Zum Anzeigen einer bestimmten Hilfedatei geben Sie `Get-Help \<about_article-name\>` z `Get-Help about_Signing` . b. ein.

Nur die konzeptionellen Artikel, in denen Hilfedateien auf Ihrem Computer installiert sind, werden angezeigt. Informationen zum herunterladen und Installieren von Hilfedateien in PowerShell 3,0 finden Sie unter [Update-Help](Update-Help.md).

```powershell
Get-Help about_*
```

### Beispiel 9: Suchen nach einem Wort in der Cmdlet-Hilfe

Dieses Beispiel zeigt, wie Sie in einem Cmdlet-Hilfeartikel nach einem Wort suchen.

```powershell
Get-Help Add-Member -Full | Out-String -Stream | Select-String -Pattern Clixml
```

```Output
the Export-Clixml cmdlet to save the instance of the object, including the additional members...
can use the Import-Clixml cmdlet to re-create the instance of the object from the information...
Export-Clixml
Import-Clixml
```

`Get-Help` verwendet den **Full** -Parameter, um Hilfe Informationen für zu erhalten `Add-Member` . Das **mamlcommandhelpinfo** -Objekt wird über die Pipeline gesendet. `Out-String` verwendet den **Stream** -Parameter, um das Objekt in eine Zeichenfolge zu konvertieren. `Select-String` verwendet den **Pattern** -Parameter, um die Zeichenfolge nach **CliXML** zu durchsuchen.

### Beispiel 10: Anzeigen einer Liste von Artikeln, die ein Wort enthalten

In diesem Beispiel wird eine Liste von Artikeln angezeigt, die das Wort **Remoting** enthalten.

Wenn Sie ein Wort eingeben, das in keinem Artikel Titel enthalten ist, wird `Get-Help` eine Liste mit Artikeln angezeigt, die dieses Wort enthalten.

```powershell
Get-Help -Name remoting
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Install-PowerShellRemoting.ps1    External                            Install-PowerShellRemoting.ps1
Disable-PSRemoting                Cmdlet    Microsoft.PowerShell.Core Prevents remote users...
Enable-PSRemoting                 Cmdlet    Microsoft.PowerShell.Core Configures the computer...
```

### Beispiel 11: Anzeige Anbieter spezifischer Hilfe

Dieses Beispiel zeigt zwei Möglichkeiten, die anbieterspezifische Hilfe für zu erhalten `Get-Item` . Diese Befehle erhalten Hilfe, in der erläutert wird, wie das `Get-Item` Cmdlet im **DataCollection** -Knoten des PowerShell-SQL Server Anbieters verwendet wird.

Im ersten Beispiel wird der `Get-Help` **path** -Parameter verwendet, um den Pfad des SQL Server Anbieters anzugeben.
Da der Pfad des Anbieters angegeben ist, können Sie den Befehl von einem beliebigen Pfad Speicherort aus ausführen.

Im zweiten Beispiel wird verwendet `Set-Location` , um zum Pfad des SQL Server Anbieters zu navigieren. An diesem Speicherort wird der **path** -Parameter nicht benötigt, um `Get-Help` die anbieterspezifische Hilfe zu erhalten.

```powershell
Get-Help Get-Item -Path SQLSERVER:\DataCollection
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

```powershell
Set-Location SQLSERVER:\DataCollection
SQLSERVER:\DataCollection> Get-Help Get-Item
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

### Beispiel 12: Anzeigen der Hilfe für ein Skript

In diesem Beispiel wird die Hilfe für das abgerufen `MyScript.ps1 script` . Informationen zum Schreiben von Hilfe für ihre Funktionen und Skripts finden Sie unter [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).

```powershell
Get-Help -Name C:\PS-Test\MyScript.ps1
```

## PARAMETERS

### -Kategorie

Zeigt nur für Elemente in der angegebenen Kategorie und ihre Aliase Hilfe an. Konzeptionelle Artikel befinden sich in der Kategorie **HelpFile** .

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- Alias
- Cmdlet
- Anbieter
- Allgemein
- Häufig gestellte Fragen
- Glossar
- HelpFile
- ScriptCommand
- Funktion
- Filter
- Externalscript
- Alle
- Defaulthelp
- Workflow
- DscResource
- Klasse
- Konfiguration

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Alias, Cmdlet, Provider, General, FAQ, Glossary, HelpFile, ScriptCommand, Function, Filter, ExternalScript, All, DefaultHelp, Workflow, DscResource, Class, Configuration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Komponente

Zeigt Befehle mit dem angegebenen Komponenten Wert an, z. b. **Exchange**. Geben Sie einen Komponentennamen ein.
Platzhalterzeichen sind zulässig. Dieser Parameter hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Detailed

Fügt der Anzeige der grundlegende Hilfe Parameterbeschreibungen und Beispiele hinzu. Dieser Parameter ist nur wirksam, wenn die Hilfedateien auf dem Computer installiert sind. Dies hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetailedView
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Examples

Zeigt nur den Namen, die Zusammenfassung und Beispiele an. Geben Sie ein, um nur die Beispiele anzuzeigen `(Get-Help \<cmdlet-name\>).Examples` .

Dieser Parameter ist nur wirksam, wenn die Hilfedateien auf dem Computer installiert sind. Dies hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Examples
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full

Zeigt den gesamten Hilfeartikel für ein Cmdlet an. **Vollständig** umfasst Parameter Beschreibungen und-Attribute, Beispiele, Eingabe-und Ausgabe Objekttypen sowie weitere Hinweise.

Dieser Parameter ist nur wirksam, wenn die Hilfedateien auf dem Computer installiert sind. Dies hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllUsersView
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Funktionalität

Zeigt Hilfe für Elemente mit der angegebenen Funktionalität an. Geben Sie die Funktionalität ein. Platzhalterzeichen sind zulässig. Dieser Parameter hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

Ruft Hilfe zum angegebenen Befehl oder Konzept ab. Geben Sie den Namen eines Cmdlets, einer Funktion, eines Anbieters, eines Skripts oder eines Workflows ein, z `Get-Member` . b. einen konzeptionellen Artikelnamen, z `about_Objects` . b. oder einen Alias, z `ls` . b.. Platzhalter Zeichen sind in Cmdlet-und Anbieter Namen zulässig, Sie können jedoch keine Platzhalter Zeichen verwenden, um die Namen der Hilfe-und Skript Hilfeartikel zu finden.

Um Hilfe für ein Skript zu erhalten, das sich nicht in einem Pfad befindet, der in der `$env:Path` Umgebungsvariablen aufgelistet ist, geben Sie den Pfad und den Dateinamen des Skripts ein.

Wenn Sie den genauen Namen eines Hilfe Artikels eingeben, wird `Get-Help` der Artikel Inhalt von angezeigt.

Wenn Sie ein Word-oder Word-Muster eingeben, das in mehreren Hilfeartikel Titeln angezeigt wird, `Get-Help` zeigt eine Liste der übereinstimmenden Titel an.

Wenn Sie Text eingeben, der mit keinem der Hilfeartikel Titel identisch ist, wird `Get-Help` eine Liste von Artikeln angezeigt, die diesen Text im Inhalt enthalten.

Die Namen von konzeptionellen Artikeln (z `about_Objects` . b.) müssen in englischer Sprache eingegeben werden, auch in nicht englischsprachigen Versionen von PowerShell.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Online

Zeigt die Online Version eines Hilfe Artikels im Standardbrowser an. Dieser Parameter ist nur für Cmdlet-, Function-, Workflow-und Skript-Hilfeartikel gültig. Der **Online-** Parameter kann nicht mit `Get-Help` in einer Remote Sitzung verwendet werden.

Weitere Informationen zur Unterstützung dieser Funktion in Hilfe Artikeln, die Sie schreiben, finden Sie unter [about_Comment_Based_Help](./About/about_Comment_Based_Help.md)und [unterstützen der Online Hilfe](/powershell/scripting/developer/module/supporting-online-help)und [Schreiben der Hilfe für PowerShell-Cmdlets](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Online
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter

Zeigt nur die ausführlichen Beschreibungen der angegebenen Parameter an. Platzhalter sind zulässig. Dieser Parameter hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).

```yaml
Type: System.String[]
Parameter Sets: Parameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Path

Ruft Hilfe ab, die die Funktionsweise des Cmdlets im angegebenen Anbieterpfad erläutert. Geben Sie einen PowerShell-Anbieter Pfad ein.

Dieser Parameter ruft eine angepasste Version eines Cmdlet-Hilfe Artikels ab, in der erläutert wird, wie das Cmdlet im angegebenen PowerShell-Anbieter Pfad funktioniert. Dieser Parameter ist nur für Hilfe zu einem Anbieter-Cmdlet und nur dann gültig, wenn der Anbieter eine benutzerdefinierte Version des Hilfe Artikels des Provider-Cmdlets in der Hilfedatei enthält. Um diesen Parameter zu verwenden, installieren Sie die Hilfedatei für das Modul, das den Anbieter enthält.

Um die Hilfe zum benutzerdefinierten Cmdlet für einen Anbieter Pfad anzuzeigen, wechseln Sie zum Speicherort des Anbieter Pfads, und geben Sie einen Befehl ein, `Get-Help` oder verwenden Sie aus einem beliebigen Pfad den **Pfad** Parameter von, `Get-Help` um den Anbieter Pfad anzugeben. Die benutzerdefinierte Cmdlet-Hilfe finden Sie auch online im Abschnitt Anbieter Hilfe der Hilfeartikel.

Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](./About/about_Providers.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Rolle

Zeigt Hilfe an, die für die angegebene Benutzerrolle angepasst wurde. Geben Sie eine Rolle ein. Platzhalterzeichen sind zulässig.

Geben Sie die Rolle ein, die der Benutzer in einer Organisation inne hat. Einige Cmdlets zeigen basierend auf dem Wert dieses Parameters unterschiedlichen Text in ihren Hilfedateien an. Dieser Parameter hat keine Auswirkungen auf die Hilfe für die Haupt-Cmdlets.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ShowWindow

Zeigt das Hilfethema zur besseren Lesbarkeit in einem Fenster an. Das Fenster enthält eine **Suchfunktion suchen und** ein **Einstellungs** Feld, mit dem Sie Optionen für die Anzeige festlegen können, einschließlich Optionen, um nur ausgewählte Abschnitte eines Hilfe Themas anzuzeigen.

Der **ShowWindow** -Parameter unterstützt Hilfe Themen für Befehle (Cmdlets, Funktionen, CIM-Befehle, Skripts) und konzeptionelle **Informationen zu** Artikeln. Die Anbieterhilfe wird nicht unterstützt.

Dieser Parameter wurde in PowerShell 7,0 erneut eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShowWindow
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Objekte können nicht über die Pipeline an gesendet werden `Get-Help` .

## AUSGABEN

### Extendedcmdlethelpinfo

Wenn Sie `Get-Help` mit einem Befehl ausführen, der keine Hilfedatei enthält, `Get-Help` gibt ein **extendedcmdlethelpinfo** -Objekt zurück, das die automatisch generierte Hilfe darstellt.

### System.String

Wenn Sie einen konzeptionellen Hilfeartikel erhalten, `Get-Help` gibt ihn als Zeichenfolge zurück.

### MamlCommandHelpInfo

Wenn Sie einen Befehl mit einer Hilfedatei erhalten, `Get-Help` gibt ein **mamlcommandhelpinfo** -Objekt zurück.

## HINWEISE

PowerShell 3,0 enthält keine Hilfedateien. `Get-Help`Verwenden Sie das-Cmdlet, um die von gelesenen Hilfedateien herunterzuladen und zu installieren `Update-Help` . Sie können das `Update-Help` Cmdlet zum herunterladen und Installieren von Hilfedateien für die Kern Befehle verwenden, die in PowerShell enthalten sind, sowie für alle Module, die Sie installieren. Sie können damit auch die Hilfedateien aktualisieren, sodass die Hilfedateien auf Ihrem Computer immer auf dem neuesten Stand sind.

Unter Erste Schritte [mit Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)können Sie auch die Hilfeartikel zu den Befehlen von PowerShell Online lesen.

`Get-Help` zeigt die Hilfe im Gebiets Schema an, das für das Windows-Betriebssystem oder in der Fall Back Sprache für dieses Gebiets Schema festgelegt wurde. Wenn Sie keine Hilfedateien für das primäre oder das Ausweich Gebiets Schema haben, `Get-Help` verhält sich so, als ob keine Hilfedateien auf dem Computer vorhanden sind. Um Hilfe für ein anderes Gebiets Schema zu erhalten, verwenden Sie **Region** und **Sprache** in der Systemsteuerung, um die Einstellungen zu ändern. Unter Windows 10, **Einstellungen** , **Zeit & Sprache**.

Die vollständige Ansicht der Hilfe enthält eine Tabelle mit Informationen zu den Parametern. Die Tabelle enthält die folgenden Felder:

- **Erforderlich**. Gibt an, ob der Parameter erforderlich (true) oder optional ist (false).

- **Position**. Gibt an, ob der Parameter benannt oder Positions basiert (numerisch) ist. Positionsparameter müssen an einer angegebenen Position im Befehl verwendet werden.

- Mit dem **Namen** wird angegeben, dass der Parameter Name erforderlich ist, aber der Parameter kann an beliebiger Stelle im Befehl angezeigt werden.

- **Numeric** gibt an, dass der Parameter Name optional ist, aber wenn der Name ausgelassen wird, muss der Parameter an der Stelle liegen, die durch die Zahl angegeben wird. `2`Gibt z. b. an, dass der Parameter, wenn der Parameter Name weggelassen wird, der zweite oder einzige unbenannte Parameter im Befehl sein muss. Wenn der Parametername verwendet wird, kann der Parameter an einer beliebigen Stelle im Befehl stehen.

- **Standardwert**. Der Parameterwert oder das Standardverhalten, das von PowerShell verwendet wird, wenn Sie den Parameter nicht in den Befehl einschließen.

- Akzeptiert Pipeline Eingaben. Gibt an, ob Sie Objekte über eine Pipeline an den Parameter senden können (true) oder nicht (false). **Nach Eigenschaftsname** bedeutet, dass das Pipeline Objekt über eine Eigenschaft verfügen muss, die den gleichen Namen wie der Parameter Name hat.

- **Akzeptiert** Platzhalter Zeichen. Gibt an, ob der Wert eines Parameters Platzhalter Zeichen enthalten kann, z. b. ein Sternchen ( `*` ) oder ein Fragezeichen ( `?` ).

## VERWANDTE LINKS

[about_Command_Syntax](About/about_Command_Syntax.md)

[about_Comment_Based_Help](./About/about_Comment_Based_Help.md)

[Get-Command](Get-Command.md)

[Unterstützung einer aktualisierbaren Hilfe](/powershell/scripting/developer/module/supporting-updatable-help)

[Update-Help](Update-Help.md)

[Schreiben von kommentarbasierten Hilfethemen](/powershell/scripting/developer/help/writing-comment-based-help-topics)

[Schreiben einer Hilfe für PowerShell-Cmdlets](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)

