---
description: Die `Format.ps1xml` Dateien in PowerShell definieren die Standard Anzeige von Objekten in der PowerShell-Konsole. Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: be88007d23ab98b9c2f707b77f9c43578ba9887b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222759"
---
# <a name="about-formatps1xml"></a>Informationen zu Format.ps1XML

## <a name="short-description"></a>Kurze Beschreibung

Die `Format.ps1xml` Dateien in PowerShell definieren die Standard Anzeige von Objekten in der PowerShell-Konsole. Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.

## <a name="long-description"></a>Lange Beschreibung

Die `Format.ps1xml` Dateien in PowerShell definieren die Standard Anzeige von Objekten in PowerShell. Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.

Wenn PowerShell ein Objekt anzeigt, verwendet es die Daten in strukturierten Formatierungs Dateien, um die Standard Anzeige des Objekts zu bestimmen. Die Daten in den Formatierungs Dateien bestimmen, ob das Objekt in einer Tabelle oder in einer Liste gerendert wird, und legt fest, welche Eigenschaften standardmäßig angezeigt werden.

Die Formatierung wirkt sich nur auf die Anzeige aus. Es wirkt sich nicht darauf aus, welche Objekteigenschaften in der Pipeline oder wie Sie übermittelt werden. `Format.ps1xml` Dateien können nicht zum Anpassen des Ausgabeformats für Hash Tabellen verwendet werden.

PowerShell enthält sieben Formatierungs Dateien. Diese Dateien befinden sich im-Installationsverzeichnis ( `$PSHOME` ). Jede Datei definiert die Anzeige einer Gruppe von Microsoft .NET Framework-Objekten:

1. `Certificate.Format.ps1xml`

   Objekte im Zertifikat Speicher, z. b. X. 509-Zertifikate und Zertifikat Speicher.

1. `DotNetTypes.Format.ps1xml`

   Andere .NET Framework Typen, z. b. CultureInfo-, FileVersionInfo-und EventLogEntry-Objekte.

1. `FileSystem.Format.ps1xml`

   Dateisystem Objekte, z. b. Dateien und Verzeichnisse.

1. `Help.Format.ps1xml`

   Hilfe Ansichten, z. b. ausführliche und vollständige Sichten, Parameter und Beispiele.

1. `PowerShellCore.Format.ps1xml`

   Objekte, die von PowerShell Core-Cmdlets generiert werden, z `Get-Member` `Get-History` . b. und.

1. `PowerShellTrace.Format.ps1xml`

   Ablauf Verfolgungs Objekte, z. b. die vom `Trace-Command` Cmdlet generierten.

1. `Registry.Format.ps1xml`

   Registrierungs Objekte, z. b. Schlüssel und Einträge.

Eine Formatierungs Datei kann vier verschiedene Ansichten der einzelnen Objekte definieren:

- Tabelle
- List
- Breite
- Benutzerdefiniert

Wenn z. b. die Ausgabe eines `Get-ChildItem` Befehls an einen Befehl weitergeleitet wird `Format-List` , `Format-List` verwendet die Ansicht in der `FileSystem.Format.ps1xml` Datei, um zu bestimmen, wie die Datei-und Ordner Objekte als Liste angezeigt werden.

Wenn eine Formatierungs Datei mehr als eine Ansicht eines Objekts enthält, wendet PowerShell die erste gefundene Ansicht an.

In einer `Format.ps1xml` Datei wird eine Ansicht durch einen Satz von XML-Tags definiert, die den Namen der Sicht, den Typ des Objekts, auf das Sie angewendet werden kann, die Spaltenüberschriften und die im Text der Ansicht angezeigten Eigenschaften beschreiben. Das Format in `Format.ps1xml` Dateien wird angewendet, kurz bevor die Daten dem Benutzer angezeigt werden.

## <a name="creating-new-formatps1xml-files"></a>Erstellen neuer Format.ps1XML-Dateien

Die `.ps1xml` mit PowerShell installierten Dateien sind digital signiert, um Manipulationen zu verhindern, da die Formatierung Skriptblöcke einschließen kann. Wenn Sie das Anzeige Format einer vorhandenen Objekt Ansicht ändern oder Ansichten für neue Objekte hinzufügen möchten, erstellen Sie Ihre eigenen `Format.ps1xml` Dateien, und fügen Sie Sie dann der PowerShell-Sitzung hinzu.

Kopieren Sie eine vorhandene Datei, um eine neue Datei zu erstellen `Format.ps1xml` . Die neue Datei kann einen beliebigen Namen haben, Sie muss jedoch eine `.ps1xml` Dateinamenerweiterung aufweisen. Sie können die neue Datei in einem beliebigen Verzeichnis platzieren, auf das PowerShell zugreifen kann, aber es ist hilfreich, die Dateien im PowerShell-Installationsverzeichnis ( `$PSHOME` ) oder in einem Unterverzeichnis des Installationsverzeichnisses zu platzieren.

Um die Formatierung einer aktuellen Ansicht zu ändern, suchen Sie die Ansicht in der Formatierungs Datei, und verwenden Sie dann die Tags, um die Ansicht zu ändern. Um eine Ansicht für einen neuen Objekttyp zu erstellen, erstellen Sie eine neue Ansicht, oder verwenden Sie eine vorhandene Sicht als Modell. Die Tags werden im nächsten Abschnitt beschrieben. Sie können dann alle anderen Sichten in der Datei löschen, damit die Änderungen offensichtlich von allen Benutzern untersucht werden, die die Datei überprüfen.

Nachdem Sie die Änderungen gespeichert haben, verwenden Sie das `Update-FormatData` Cmdlet, um die neue Datei zur PowerShell-Sitzung hinzuzufügen. Wenn Sie möchten, dass Ihre Ansicht Vorrang vor einer Ansicht hat, die in den integrierten Dateien definiert ist, verwenden Sie den **prepdpath** -Parameter.
`Update-FormatData` wirkt sich nur auf die aktuelle Sitzung aus. Fügen Sie den `Update-FormatData` Befehl zu Ihrem PowerShell-Profil hinzu, um die Änderung an allen zukünftigen Sitzungen vorzunehmen.

### <a name="example-adding-calendar-data-to-culture-objects"></a>Beispiel: Hinzufügen von Kalenderdaten zu Kultur Objekten

In diesem Beispiel wird gezeigt, wie die Formatierung der Culture-Objekte **System. Globalization. CultureInfo** geändert wird, die durch das `Get-Culture` Cmdlet in der aktuellen PowerShell-Sitzung generiert werden. Mit den Befehlen in diesem Beispiel wird die **Calendar** -Eigenschaft der standardmäßigen Tabellen Ansichts Anzeige von Culture-Objekten hinzugefügt.

Der erste Schritt besteht darin, die `Format.ps1xml` Datei zu suchen, die die aktuelle Ansicht der Kultur Objekte enthält. Der folgende `Select-String` Befehl sucht nach der Datei:

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.Globalization.CultureInfo"
}

Select-String @Parms
```

```Output
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:113:
     <Name>System.Globalization.CultureInfo</Name>
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:115:
<TypeName>System.Globalization.CultureInfo</TypeName>
```

Dieser Befehl zeigt, dass die Definition in der `DotNetTypes.Format.ps1xml` Datei gespeichert ist.

Der nächste Befehl kopiert den Dateiinhalt in eine neue Datei, `MyDotNetTypes.Format.ps1xml` .

```powershell
Copy-Item $PSHome\DotNetTypes.format.ps1xml MyDotNetTypes.Format.ps1xml
```

Öffnen Sie die `MyDotNetTypes.Format.ps1xml` Datei in einem beliebigen XML-oder Text-Editor, z. b. Visual Studio Code. Suchen Sie den Abschnitt **System. Globalization. CultureInfo** -Objekt. Der folgende XML-Code definiert die Ansichten des **CultureInfo** -Objekts. Das-Objekt verfügt nur über eine **tablecontrol** -Sicht.

```xml
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
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
```

Löschen Sie den Rest der Datei mit Ausnahme der öffnenden `<?xml>` `<Configuration>` Tags,, und `<ViewDefinitions>` und der schließenden `<ViewDefinitions>` -und- `<Configuration>` Tags. Wenn eine digitale Signatur vorhanden ist, löschen Sie Sie aus der benutzerdefinierten `Format.ps1xml` Datei.

Die `MyDotNetTypes.Format.ps1xml` Datei sollte nun wie im folgenden Beispiel aussehen:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
<ViewDefinitions>
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
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
      <TableColumnHeader/>
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
Update-FormatData -PrependPath $PSHOME\MyDotNetTypes.Format.ps1xml
```

Zum Testen der Änderung geben Sie ein, `Get-Culture` und überprüfen Sie die Ausgabe, die die **Calendar** -Eigenschaft enthält.

```powershell
Get-Culture
```

```Output
LCID Name  Calendar                               DisplayName
---- ----  --------                               -----------
1033 en-US System.Globalization.GregorianCalendar English (United States)
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

## <a name="default-displays-in-typesps1xml"></a>Standard Anzeige in Types.ps1XML

Die Standard Anzeige einiger grundlegender Objekttypen wird in der `Types.ps1xml` Datei im Verzeichnis definiert `$PSHOME` . Die Knoten haben den Namen **psstandardmembers** , und die untergeordneten Knoten verwenden eines der folgenden Tags:

- `<DefaultDisplayProperty>`
- `<DefaultDisplayPropertySet>`
- `<DefaultKeyPropertySet>`

Weitere Informationen finden Sie unter [about_Types.ps1XML](about_Types.ps1xml.md).

## <a name="tracing-formatps1xml-file-use"></a>Ablauf Verfolgung Format.ps1XML-Datei Verwendung

Verwenden Sie zum Erkennen von Fehlern beim Laden oder bei der Anwendung von `Format.ps1xml` Dateien das- `Trace-Command` Cmdlet mit den folgenden Format Komponenten als Wert für den **Name** -Parameter:

- Formatfileloading
- Formatviewbinding

Weitere Informationen finden Sie unter [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) und [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).

## <a name="signing-a-formatps1xml-file"></a>Signieren einer Format.ps1-XML-Datei

`Format.ps1xml`Signieren Sie die Datei mithilfe einer digitalen Signatur, um die Benutzer Ihrer-Datei zu schützen. Weitere Informationen finden Sie unter [about_Signing](about_Signing.md).

## <a name="sample-xml-for-a-format-table-custom-view"></a>Beispiel-XML für eine Format-Table benutzerdefinierte Ansicht

Im folgenden Beispiel wird eine `Format-Table` benutzerdefinierte Ansicht für die **System. IO. directeryinfo** -und **System. IO. FileInfo** -Objekte erstellt, die von erstellt werden `Get-ChildItem` . Die benutzerdefinierte Ansicht hat den Namen **mygciview** und fügt der Tabelle die Spalte " **kreationtime** " hinzu.

Die benutzerdefinierte Ansicht wird aus einer bearbeiteten Version der `FileSystem.Format.ps1xml` Datei erstellt, die in in `$PSHOME` PowerShell 5,1 gespeichert ist.

Nachdem die benutzerdefinierte `.ps1xml` Datei gespeichert wurde, verwenden `Update-FormatData` Sie, um die Ansicht in eine PowerShell-Sitzung einzubeziehen. In diesem Beispiel muss die benutzerdefinierte Sicht das Tabellenformat verwenden, andernfalls `Format-Table` schlägt fehl.

Verwenden `Format-Table` Sie mit dem **View** -Parameter, um den Namen der benutzerdefinierten Ansicht anzugeben und die Ausgabe der Tabelle zu formatieren. Ein Beispiel für die Art und Weise, wie der Befehl ausgeführt wird, finden Sie unter [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.IO.DirectoryInfo"
}
Select-String @Parms
Copy-Item $PSHome\FileSystem.format.ps1xml .\MyFileSystem.Format.ps1xml
Update-FormatData -PrependPath $PSHOME\Format\MyFileSystem.Format.ps1xml
```

> [!NOTE]
> Um das XML-Beispiel in Einschränkungen der Zeilenbreite zu integrieren, war es erforderlich, einen Einzug zu komprimieren und Zeilenumbrüche innerhalb des Codes zu verwenden.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
    <SelectionSets>
        <SelectionSet>
            <Name>FileSystemTypes</Name>
            <Types>
                <TypeName>System.IO.DirectoryInfo</TypeName>
                <TypeName>System.IO.FileInfo</TypeName>
            </Types>
        </SelectionSet>
    </SelectionSets>
<Controls>
<Control>
<Name>FileSystemTypes-GroupingFormat</Name>
<CustomControl>
 <CustomEntries>
  <CustomEntry>
    <CustomItem>
    <Frame>
    <LeftIndent>4</LeftIndent>
    <CustomItem>
    <Text AssemblyName="System.Management.Automation"
    BaseName="FileSystemProviderStrings"
    ResourceId="DirectoryDisplayGrouping"/>
    <ExpressionBinding>
     <ScriptBlock>
      $_.PSParentPath.Replace("Microsoft.PowerShell.Core\FileSystem::", "")
     </ScriptBlock>
    </ExpressionBinding>
    <NewLine/>
    </CustomItem>
    </Frame>
    </CustomItem>
    </CustomEntry>
 </CustomEntries>
</CustomControl>
</Control>
</Controls>
<ViewDefinitions>
    <View>
    <Name>mygciview</Name>
    <ViewSelectedBy>
        <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <GroupBy>
      <PropertyName>PSParentPath</PropertyName>
      <CustomControlName>FileSystemTypes-GroupingFormat</CustomControlName>
    </GroupBy>
        <TableControl>
            <TableHeaders>
                <TableColumnHeader>
                    <Label>Mode</Label>
                    <Width>7</Width>
                    <Alignment>left</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>LastWriteTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>CreationTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>Length</Label>
                    <Width>14</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader/>
            </TableHeaders>
            <TableRowEntries>
                <TableRowEntry>
                    <Wrap/>
                    <TableColumnItems>
                        <TableColumnItem>
                            <PropertyName>Mode</PropertyName>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.LastWriteTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.CreationTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
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
