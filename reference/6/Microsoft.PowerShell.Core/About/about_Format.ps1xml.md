---
description: Ab PowerShell 6 werden die Standardansichten für-Objekte im PowerShell-Quellcode definiert.  Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: bbe7c9d2d36673ff6240be89f9ceb439ab0d0dfa
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221631"
---
# <a name="about-formatps1xml"></a>Informationen zu Format.ps1XML

## <a name="short-description"></a>Kurze Beschreibung

Ab PowerShell 6 werden die Standardansichten für-Objekte im PowerShell-Quellcode definiert.

Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.

## <a name="long-description"></a>Lange Beschreibung

Ab PowerShell 6 werden die Standardansichten im PowerShell-Quellcode definiert. Die `Format.ps1xml` Dateien aus PowerShell 5,1 und früheren Versionen sind in PowerShell 6 und höheren Versionen nicht vorhanden.

Der PowerShell-Quellcode definiert die Standard Anzeige von Objekten in der PowerShell-Konsole. Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.

Wenn PowerShell ein Objekt anzeigt, verwendet es die Daten in strukturierten Formatierungs Dateien, um die Standard Anzeige des Objekts zu bestimmen. Die Daten in den Formatierungs Dateien bestimmen, ob das Objekt in einer Tabelle oder in einer Liste gerendert wird, und legt fest, welche Eigenschaften standardmäßig angezeigt werden.

Die Formatierung wirkt sich nur auf die Anzeige aus. Es wirkt sich nicht darauf aus, welche Objekteigenschaften in der Pipeline oder wie Sie übermittelt werden. `Format.ps1xml` Dateien können nicht zum Anpassen des Ausgabeformats für Hash Tabellen verwendet werden.

Eine `.ps1xml` Formatierungs Datei kann vier verschiedene Ansichten der einzelnen Objekte definieren:

- Tabelle
- List
- Breite
- Benutzerdefiniert

Wenn z. b. die Ausgabe eines `Get-ChildItem` Befehls an einen Befehl weitergeleitet wird `Format-List` , `Format-List` verwendet die Listenansicht, die im Quellcode definiert ist, um zu bestimmen, wie die Datei-und Ordner Objekte als Liste angezeigt werden.

Wenn eine Formatierungs Datei mehr als eine Ansicht eines Objekts enthält, wendet PowerShell die erste gefundene Ansicht an.

In einer benutzerdefinierten `Format.ps1xml` Datei wird eine Ansicht durch eine Reihe von XML-Tags definiert, die den Namen der Ansicht, den Typ des Objekts, auf das es angewendet werden kann, die Spaltenüberschriften und die im Text der Ansicht angezeigten Eigenschaften beschreiben. Das Format in `Format.ps1xml` Dateien wird angewendet, kurz bevor die Daten dem Benutzer angezeigt werden.

## <a name="creating-new-formatps1xml-files"></a>Erstellen neuer Format.ps1XML-Dateien

Wenn Sie das Anzeige Format einer vorhandenen Objekt Ansicht ändern oder Ansichten für neue Objekte hinzufügen möchten, erstellen Sie Ihre eigenen `Format.ps1xml` Dateien, und fügen Sie Sie dann der PowerShell-Sitzung hinzu.

`Format.ps1xml`Verwenden Sie die Cmdlets [Get-formatdata](xref:Microsoft.PowerShell.Utility.Get-FormatData) und [Export-formatdata](xref:Microsoft.PowerShell.Utility.Export-FormatData) , um eine Datei zum Definieren einer benutzerdefinierten Ansicht zu erstellen. Verwenden Sie einen Text-Editor, um die Datei zu bearbeiten. Die Datei kann in einem beliebigen Verzeichnis gespeichert werden, auf das PowerShell zugreifen kann, z. b. ein Unterverzeichnis von `$HOME` .

Um die Formatierung einer aktuellen Ansicht zu ändern, suchen Sie die Ansicht in der Formatierungs Datei, und verwenden Sie dann die Tags, um die Ansicht zu ändern. Um eine Ansicht für einen neuen Objekttyp zu erstellen, erstellen Sie eine neue Ansicht, oder verwenden Sie eine vorhandene Sicht als Modell. Die Tags werden im nächsten Abschnitt beschrieben. Sie können dann alle anderen Sichten in der Datei löschen, damit die Änderungen offensichtlich von allen Benutzern untersucht werden, die die Datei überprüfen.

Nachdem Sie die Änderungen gespeichert haben, verwenden Sie [Update-formatdata](xref:Microsoft.PowerShell.Utility.Update-FormatData) , um die neue Datei zur PowerShell-Sitzung hinzuzufügen. Wenn Sie möchten, dass Ihre Ansicht Vorrang vor einer Ansicht hat, die in den integrierten Dateien definiert ist, verwenden Sie den **prepdpath** -Parameter. `Update-FormatData` wirkt sich nur auf die aktuelle Sitzung aus. Fügen Sie den `Update-FormatData` Befehl zu Ihrem PowerShell-Profil hinzu, um die Änderung an allen zukünftigen Sitzungen vorzunehmen.

### <a name="example-add-calendar-data-to-culture-objects"></a>Beispiel: Hinzufügen von Kalenderdaten zu Kultur Objekten

In diesem Beispiel wird gezeigt, wie die Formatierung der Culture-Objekte **System. Globalization. CultureInfo** geändert wird, die durch das `Get-Culture` Cmdlet in der aktuellen PowerShell-Sitzung generiert werden. Mit den Befehlen in diesem Beispiel wird die **Calendar** -Eigenschaft der standardmäßigen Tabellen Ansichts Anzeige von Culture-Objekten hinzugefügt.

Rufen Sie zunächst die Format Daten aus der Quell Code Datei ab, und erstellen Sie eine `Format.ps1xml` Datei, die die aktuelle Ansicht der Kultur Objekte enthält.

```powershell
Get-FormatData -TypeName System.Globalization.CultureInfo |
  Export-FormatData -Path $HOME\Format\CultureInfo.Format.ps1xml
```

Öffnen Sie die `CultureInfo.Format.ps1xml` Datei in einem beliebigen XML-oder Text-Editor, z. b. Visual Studio Code. Der folgende XML-Code definiert die Ansichten des **CultureInfo** -Objekts.

Die `CultureInfo.Format.ps1xml` Datei sollte wie im folgenden Beispiel aussehen:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.Globalization.CultureInfo</Name>
      <ViewSelectedBy>
        <TypeName>System.Globalization.CultureInfo</TypeName>
      </ViewSelectedBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Width>16</Width>
          </TableColumnHeader>
          <TableColumnHeader>
            <Width>16</Width>
          </TableColumnHeader>
          <TableColumnHeader />
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>LCID</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Name</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>DisplayName</PropertyName>
              </TableColumnItem>
            </TableColumnItems>
          </TableRowEntry>
        </TableRowEntries>
      </TableControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

Erstellen Sie eine neue Spalte für die **Calendar** -Eigenschaft, indem Sie einen neuen Satz von Tags hinzufügen `<TableColumnHeader>` . Der Wert der **Calendar** -Eigenschaft kann lang sein. Geben Sie daher einen Wert von 45 Zeichen als an `<Width>` .

```xml
<TableHeaders>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>45</Width>
  </TableColumnHeader>
  <TableColumnHeader/>
</TableHeaders>
```

Fügen Sie ein neues Spalten Element für **Calendar** in den Tabellenzeilen mithilfe `<TableColumnItem>` der `<PropertyName` Tags und hinzu:

```xml
<TableRowEntries>
  <TableRowEntry>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName>LCID</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Name</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Calendar</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>DisplayName</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>
```

Speichern und schließen Sie die Datei. Verwenden Sie `Update-FormatData` , um der aktuellen PowerShell-Sitzung die neue Format Datei hinzuzufügen.

In diesem Beispiel wird der **prepdpath** -Parameter verwendet, um die neue Datei in einer höheren Rangfolge als die ursprüngliche Datei zu platzieren. Weitere Informationen finden Sie unter [Update-formatdata](xref:Microsoft.PowerShell.Utility.Update-FormatData).

```powershell
Update-FormatData -PrependPath $HOME\Format\CultureInfo.Format.ps1xml
```

Zum Testen der Änderung geben Sie ein, `Get-Culture` und überprüfen Sie die Ausgabe, die die **Calendar** -Eigenschaft enthält.

```powershell
Get-Culture
```

```Output
LCID  Name   Calendar                                DisplayName
----  ----   --------                                -----------
1033  en-US  System.Globalization.GregorianCalendar  English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a>Der XML-Code in Format.ps1XML-Dateien

Die vollständige Schema Definition finden Sie in der [Datei "Format. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) " im PowerShell-Quellcoderepository auf GitHub.

Der **viewdefinitions** -Abschnitt jeder `Format.ps1xml` Datei enthält die `<View>` Tags, die jede Ansicht definieren. Ein typisches `<View>` Tag umfasst die folgenden Tags:

- `<Name>` identifiziert den Namen der Ansicht.
- `<ViewSelectedBy>` Gibt den Objekttyp oder die Typen an, für die die Ansicht gilt.
- `<GroupBy>` Gibt an, wie Elemente in der Ansicht in Gruppen kombiniert werden.
- `<TableControl>`, `<ListControl>` , `<WideControl>` und `<CustomControl>` enthalten die Tags, die angeben, wie die einzelnen Elemente angezeigt werden.

### <a name="viewselectedby-tag"></a>Viewselectedby-Tag

Das- `<ViewSelectedBy>` Tag kann ein- `<TypeName>` Tag für jeden Objekttyp enthalten, auf den die Ansicht angewendet wird. Oder es kann ein Tag enthalten sein `<SelectionSetName>` , das auf einen Auswahl Satz verweist, der an anderer Stelle mithilfe eines Tags definiert wird `<SelectionSet>` .

### <a name="groupby-tag"></a>GroupBy-Tag

Das- `<GroupBy>` Tag enthält ein- `<PropertyName>` Tag, das die Objekt Eigenschaft angibt, nach der Elemente gruppiert werden sollen. Sie enthält auch ein `<Label>` Tag, das eine Zeichenfolge angibt, die als Bezeichnung für jede Gruppe oder ein Tag verwendet wird, `<CustomControlName>` das auf ein benutzerdefiniertes Steuerelement verweist, das an anderer Stelle mithilfe eines Tags definiert ist `<Control>` . Das `<Control>` Tag enthält ein `<Name>` Tag und ein `<CustomControl>` Tag.

### <a name="tablecontroltag"></a>Tablecontroltag

Das- `<TableControl>` Tag enthält normalerweise `<TableHeaders>` -und- `<TableRowEntries>` Tags, die die Formatierung für den Kopf und die Zeilen der Tabelle definieren. Das `<TableHeaders>` -Tag enthält in der Regel `<TableColumnHeader>` Tags, die `<Label>` `<Width>` -,-und- `<Alignment>` Tags enthalten. Das `<TableRowEntries>` Tag enthält `<TableRowEntry>` Tags für jede Zeile in der Tabelle. Das- `<TableRowEntry>` Tag enthält ein-Tag `<TableColumnItems>` , das ein- `<TableColumnItem>` Tag für jede Spalte in der Zeile enthält. In der Regel `<TableColumnItem>` enthält das Tag entweder ein `<PropertyName>` Tag, das die Objekt Eigenschaft angibt, die am definierten Speicherort angezeigt werden soll, oder ein `<ScriptBlock>` Tag, das Skriptcode enthält, der ein Ergebnis berechnet, das am Speicherort angezeigt werden soll.

> [!NOTE]
> Skriptblöcke können auch an anderen Speicherorten verwendet werden, an denen berechnete Ergebnisse nützlich sein können.

Das- `<TableColumnItem>` Tag kann auch ein- `<FormatString>` Tag enthalten, das angibt, wie die-Eigenschaft oder die berechneten Ergebnisse angezeigt werden.

### <a name="listcontrol-tag"></a>ListControl-Tag

Das- `<ListControl>` Tag enthält normalerweise ein- `<ListEntries>` Tag. Das `<ListEntries>` Tag enthält ein `<ListEntry>` Tag. Das `<ListEntry>` Tag enthält ein `<ListItems>` Tag. Das- `<ListItems>` Tag enthält `<ListItem>` Tags, die `<PropertyName>` Tags enthalten. `<PropertyName>`Mit den Tags wird die Objekt Eigenschaft angegeben, die an der angegebenen Position in der Liste angezeigt werden soll. Wenn die Ansichts Auswahl mithilfe eines Auswahl Satzes definiert ist, `<ListControl>` `<ListEntry>` können die Tags und auch ein `<EntrySelectedBy>` Tag enthalten, das ein oder mehrere `<TypeName>` Tags enthält. Diese `<TypeName>` Tags geben den Objekttyp an, der vom `<ListControl>` Tag angezeigt werden soll.

### <a name="widecontrol-tag"></a>Widecontrol-Tag

Das- `<WideControl>` Tag enthält normalerweise ein- `<WideEntries>` Tag. Das- `<WideEntries>` Tag enthält ein oder mehrere `<WideEntry>` Tags. Ein- `<WideEntry>` Tag enthält normalerweise ein- `<PropertyName>` Tag, das die Eigenschaft angibt, die an der angegebenen Position in der Ansicht angezeigt werden soll. Das- `<PropertyName>` Tag kann ein- `<FormatString>` Tag enthalten, das angibt, wie die-Eigenschaft angezeigt werden soll.

### <a name="customcontrol-tag"></a>CustomControl-Tag

Mit dem- `<CustomControl>` Tag können Sie einen Skriptblock verwenden, um ein Format zu definieren. Ein `<CustomControl>` Tag enthält normalerweise ein `<CustomEntries>` Tag, das mehrere `<CustomEntry>` Tags enthält. Jedes `<CustomEntry>` Tag enthält ein `<CustomItem>` Tag, das eine Vielzahl von Tags enthalten kann, die den Inhalt und die Formatierung der angegebenen Position in der Sicht angeben, einschließlich der `<Text>` `<Indentation>` Tags,, `<ExpressionBinding>` und `<NewLine>` .

## <a name="tracing-formatps1xml-file-use"></a>Ablauf Verfolgung Format.ps1XML-Datei Verwendung

Verwenden Sie zum Erkennen von Fehlern beim Laden oder bei der Anwendung von `Format.ps1xml` Dateien das- `Trace-Command` Cmdlet mit den folgenden Format Komponenten als Wert für den **Name** -Parameter:

- Formatfileloading
- Formatviewbinding

Weitere Informationen finden Sie unter [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) und [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).

## <a name="signing-a-formatps1xml-file"></a>Signieren einer Format.ps1-XML-Datei

`Format.ps1xml`Signieren Sie die Datei mithilfe einer digitalen Signatur, um die Benutzer Ihrer-Datei zu schützen. Weitere Informationen finden Sie unter [about_Signing](about_Signing.md).

## <a name="sample-xml-for-a-format-table-custom-view"></a>Beispiel-XML für eine Format-Table benutzerdefinierte Ansicht

Im folgenden XML `Format-Table` -Beispiel wird eine benutzerdefinierte Ansicht für die **System. IO. directeryinfo** -und **System. IO. FileInfo** -Objekte erstellt, die von erstellt werden `Get-ChildItem` . Die benutzerdefinierte Ansicht hat den Namen **mygciview** und fügt der Tabelle die Spalte " **kreationtime** " hinzu.

Um die benutzerdefinierte Ansicht zu erstellen, `Get-FormatData` verwenden `Export-FormatData` Sie die Cmdlets und, um eine Datei zu generieren `.ps1xml` . Bearbeiten Sie dann `.ps1xml` die Datei, um den Code für die benutzerdefinierte Ansicht zu erstellen. Die `.ps1xml` Datei kann in einem beliebigen Verzeichnis gespeichert werden, auf das PowerShell zugreifen kann. Beispielsweise ein Unterverzeichnis von `$HOME` .

Nachdem die `.ps1xml` Datei erstellt wurde, verwenden `Update-FormatData` Sie das Cmdlet, um die Ansicht in die aktuelle PowerShell-Sitzung einzubeziehen. Sie können auch den Update-Befehl zu Ihrem PowerShell-Profil hinzufügen, wenn Sie die Ansicht in allen PowerShell-Sitzungen verfügbar benötigen.

In diesem Beispiel muss die benutzerdefinierte Sicht das Tabellenformat verwenden, andernfalls `Format-Table` schlägt fehl.

Verwenden `Format-Table` Sie mit dem **View** -Parameter, um den Namen der benutzerdefinierten Ansicht ( **mygciview** ) anzugeben, und formatieren Sie die Ausgabe der Tabelle mit der Spalte " **kreationtime** ". Ein Beispiel für die Art und Weise, wie der Befehl ausgeführt wird, finden Sie unter [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).

> [!NOTE]
> Obwohl Sie den Formatierungs-XML-Code aus dem Quellcode zum Erstellen einer benutzerdefinierten Ansicht erhalten können, ist möglicherweise eine größere Entwicklung erforderlich, um das gewünschte Ergebnis zu erhalten.

Im folgenden `Get-FormatData` Befehl gibt es eine Alternative zum **PowerShellVersion** -Parameter, um sicherzustellen, dass alle lokalen Formatierungsinformationen zurückgegeben werden. Verwenden Sie `-PowerShellVersion $PSVersionTable.PSVersion` anstelle einer bestimmten PowerShell-Version.

```powershell
Get-FormatData -PowerShellVersion 5.1 -TypeName System.IO.DirectoryInfo |
   Export-FormatData -Path ./Mygciview.Format.ps1xml
Update-FormatData -AppendPath ./Mygciview.Format.ps1xml
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>mygciview</Name>
      <ViewSelectedBy>
        <TypeName>System.IO.DirectoryInfo</TypeName>
        <TypeName>System.IO.FileInfo</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>PSParentPath</PropertyName>
      </GroupBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Label>Mode</Label>
            <Width>7</Width>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>LastWriteTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>CreationTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Length</Label>
            <Width>14</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Name</Label>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <Wrap />
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>ModeWithoutHardLink</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>LastWriteTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>CreationTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Length</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Name</PropertyName>
              </TableColumnItem>
            </TableColumnItems>
          </TableRowEntry>
        </TableRowEntries>
      </TableControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a>Weitere Informationen:

[Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[Formatschema – XML-Referenz](/powershell/scripting/developer/format/format-schema-xml-reference)

[Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command)

[Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[Schreiben einer PowerShell-Formatierungsdatei](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
