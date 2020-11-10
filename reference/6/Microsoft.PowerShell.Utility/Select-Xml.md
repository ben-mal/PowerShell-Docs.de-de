---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-xml?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Xml
ms.openlocfilehash: d3cadbc6ca08741f8e747ad59456e5b6924e1688
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94386915"
---
# Select-Xml

## ZUSAMMENFASSUNG
Sucht Text in einer XML-Zeichenfolge oder einem XML-Dokument.

## SYNTAX

### XML (Standard)

```
Select-Xml [-Xml] <XmlNode[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### Pfad

```
Select-Xml [-Path] <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### LiteralPath

```
Select-Xml -LiteralPath <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### Inhalt

```
Select-Xml -Content <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem **Select-XML-** Cmdlet können Sie XPath-Abfragen verwenden, um Text in XML-Zeichen folgen und-Dokumenten zu suchen.
Geben Sie eine XPath-Abfrage ein, und verwenden Sie den Parameter *Content* , *path* oder *XML* , um das zu durchsuchende XML anzugeben.

## BEISPIELE

### Beispiel 1: Auswählen von aliasproperty-Knoten

```
PS C:\> $Path = "$Pshome\Types.ps1xml"
PS C:\> $XPath = "/Types/Type/Members/AliasProperty"
PS C:\> Select-Xml -Path $Path -XPath $Xpath | Select-Object -ExpandProperty Node
Name                 ReferencedMemberName
----                 --------------------
Count                Length
Name                 Key
Name                 ServiceName
RequiredServices     ServicesDependedOn
ProcessName          Name
Handles              Handlecount
VM                   VirtualSize
WS                   WorkingSetSize
Name                 ProcessName
Handles              Handlecount
VM                   VirtualMemorySize
WS                   WorkingSet
PM                   PagedMemorySize
NPM                  NonpagedSystemMemorySize
Name                 __Class
Namespace            ModuleName
```

In diesem Beispiel werden die Aliaseigenschaften in „Types.ps1xml“ abgerufen.
(Weitere Informationen zu dieser Datei finden Sie unter about_Types.ps1xml.)

Der erste Befehl speichert den Pfad zur Datei „Types.ps1xml“ in der $Path-Variablen.

Der zweite Befehl speichert den XML-Pfad zum AliasProperty-Knoten in der $XPath-Variablen.

Der dritte Befehl verwendet das **Select-Xml** -Cmdlet zum Abrufen der AliasProperty-Knoten, die durch die XPath-Anweisung der Datei „Types.ps1xml“ identifiziert werden.
Der Befehl verwendet einen Pipeline Operator, um die aliasproperty-Knoten an das Select-Object-Cmdlet zu senden.
Der *ExpandProperty* -Parameter erweitert das **Knoten** Objekt und gibt dessen Eigenschaften Name und referencedmembership Name zurück.

Das Ergebnis zeigt die Name-Eigenschaft und ReferencedMemberName-Eigenschaft jeder Aliaseigenschaft in der Datei „Types.ps1xml“ an.
Beispielsweise gibt es eine **count** -Eigenschaft, die ein Alias der **length** -Eigenschaft ist.

### Beispiel 2: Eingabe eines XML-Dokuments

```
PS C:\> [xml]$Types = Get-Content $Pshome\Types.ps1xml
PS C:\> Select-Xml -Xml $Types -XPath "//MethodName"
```

In diesem Beispiel wird gezeigt, wie der *XML* -Parameter verwendet wird, um ein XML-Dokument für das **Select-XML** -Cmdlet bereitzustellen.

Der erste Befehl verwendet das Cmdlet "Get-Content", um den Inhalt der Types.ps1XML-Datei zu erhalten und in der $Types-Variablen zu speichern.
Der XML-Code wandelt \[ \] die Variable in ein XML-Objekt um.

Der zweite Befehl verwendet das **Select-Xml** -Cmdlet zum Abrufen der MethodName-Knoten in der Datei „Types.ps1xml“.
Der Befehl verwendet den *Xml* -Parameter, um den XML-Inhalt in der $Types-Variablen und den *XPath* -Parameter anzugeben, der den Pfad zum MethodName-Knoten festlegt.

### Beispiel 3: Durchsuchen von PowerShell-Hilfedateien

```
PS C:\> $Namespace = @{command = "http://schemas.microsoft.com/maml/dev/command/2004/10"; maml = "http://schemas.microsoft.com/maml/2004/10"; dev = "http://schemas.microsoft.com/maml/dev/2004/10"}

The second command saves the path to the help files in the $Path variable.If there are no help files in this path on your computer, use the Update-Help cmdlet to download the help files. For more information about Updatable Help, see about_Updatable_Help (https://go.microsoft.com/fwlink/?LinkId=235801).
PS C:\> $Path = "$Pshome\en-us\*dll-Help.xml"

The third command uses the **Select-Xml** cmdlet to search the XML for cmdlet names by finding Command:Name element anywhere in the files. It saves the results in the $Xml variable.**Select-Xml** returns a **SelectXmlInfo** object that has a Node property, which is a **System.Xml.XmlElement** object. The Node property has an InnerXML property, which contains the actual XML that is retrieved.
PS C:\> $Xml = Select-Xml -Path $Path -Namespace $Namespace -XPath "//command:name"

The fourth command sends the XML in the $Xml variable to the Format-Table cmdlet. The **Format-Table** command uses a calculated property to get the Node.InnerXML property of each object in the $Xml variable, trim the white space before and after the text, and display it in the table, along with the path to the source file.
PS C:\> $Xml | Format-Table @{Label="Name"; Expression= {($_.node.innerxml).trim()}}, Path -AutoSize

Name                    Path
----                    ----
Export-Counter          C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Get-Counter             C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Get-WinEvent            C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Import-Counter          C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Add-Computer            C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
Add-Content             C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
Checkpoint-Computer     C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
...
```

In diesem Beispiel wird gezeigt, wie das Cmdlet **Select-XML** verwendet wird, um die XML-basierten Cmdlet-Hilfedateien von PowerShell zu durchsuchen.
In diesem Beispiel suchen wir den Cmdletnamen, der als Titel der einzelnen Hilfedateien dient, und den Pfad zur Hilfedatei.

Der erste Befehl erstellt eine Hashtabelle, die den für die Hilfedateien verwendeten XML-Namespace darstellt, und speichert sie in der $Namespace-Variablen.

### Beispiel 4: unterschiedliche Möglichkeiten zum Eingeben von XML

```
PS C:\> $Xml = @"
<?xml version="1.0" encoding="utf-8"?>
<Book>
  <projects>
    <project name="Book1" date="2009-01-20">
      <editions>
        <edition language="English">En.Book1.com</edition>
        <edition language="German">Ge.Book1.Com</edition>
        <edition language="French">Fr.Book1.com</edition>
        <edition language="Polish">Pl.Book1.com</edition>
      </editions>
    </project>
  </projects>
</Book>
"@

The second command uses the *Content* parameter of **Select-Xml** to specify the XML in the $Xml variable.
PS C:\> Select-Xml -Content $Xml -XPath "//edition" | foreach {$_.node.InnerXML}

En.Book1.com
Ge.Book1.Com
Fr.Book1.com
Pl.Book1.com

The third command is equivalent to the second. It uses a pipeline operator (|) to send the XML in the $Xml variable to the **Select-Xml** cmdlet.
PS C:\> $Xml | Select-Xml -XPath "//edition" | foreach {$_.node.InnerXML}

En.Book1.com
Ge.Book1.Com
Fr.Book1.com
Pl.Book1.com
```

In diesem Beispiel werden zwei verschiedene Möglichkeiten zum Senden von XML an das **Select-XML-** Cmdlet veranschaulicht.

Der erste Befehl speichert eine here-Zeichenfolge, die XML in der $XML Variable enthält.
Weitere Informationen zu here-strings finden Sie unter about_Quoting_Rules.

### Beispiel 5: Verwenden des xmlns-Standard Namespace

```
PS C:\> $SnippetNamespace = @{snip = "http://schemas.microsoft.com/PowerShell/Snippets"}

The second command uses the **Select-Xml** cmdlet to get the content of the Title element of each snippet. It uses the *Path* parameter to specify the Snippets directory and the *Namespace* parameter to specify the namespace in the $SnippetNamespace variable. The value of the *XPath* parameter is the "snip" namespace key, a colon (:), and the name of the Title element.The command uses a pipeline operator (|) to send each **Node** property that **Select-Xml** returns to the ForEach-Object cmdlet, which gets the title in the value of the **InnerXml** property of the node.
PS C:\> Select-Xml -Path $Home\Documents\WindowsPowerShell\Snippets -Namespace $SnippetNamespace -XPath "//snip:Title" | foreach {$_.Node.Innerxml}
```

Dieses Beispiel zeigt, wie Sie das **Select-XML-** Cmdlet mit XML-Dokumenten verwenden, die den xmlns-Standard Namespace verwenden.
Im Beispiel werden die Titel der vom Benutzer erstellten Windows PowerShell ISE-Codeausschnittsdateien abgerufen.
Weitere Informationen zu Codeausschnitten finden Sie unter New-IseSnippet.

Der erste Befehl erstellt eine Hash Tabelle für den Standard Namespace, der von Code Ausschnitt-XML-Dateien verwendet wird, und weist ihn der $SnippetNamespace Variablen zu.
Der Hashtabellenwert befindet sich im XMLNS-Schema-URI der XML-Codeausschnittsdatei.
Der Name des Hash Tabellen Schlüssels (Snip) ist willkürlich.
Sie können einen beliebigen Namen verwenden, der nicht reserviert ist, aber Sie können keine xmlns verwenden.

## PARAMETERS

### -Inhalt

Gibt eine Zeichenfolge an, die den zu suchenden XML-Inhalt enthält.
Sie können Zeichen folgen auch an **Select-XML** übergeben.

```yaml
Type: System.String[]
Parameter Sets: Content
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Literalpath

Gibt die Pfad- und Dateinamen der zu durchsuchenden XML-Dateien an.
Im Gegensatz zu *Path* wird der Wert des *LiteralPath* -Parameters genauso verwendet, wie er eingegeben wurde.
Es werden keine Zeichen als Platzhalter interpretiert.
Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.
Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace

Gibt eine Hashtabelle der im XML-Inhalt verwendeten Namespaces an.
Verwenden Sie das Format @ { \<namespaceName\>  =  \<namespaceValue\> }.

Wenn der XML-Code den Standard Namespace verwendet, der mit xmlns beginnt, verwenden Sie einen beliebigen Schlüssel für den Namespace Namen.
Xmlns können nicht verwendet werden.
Stellen Sie in der XPath-Anweisung jedem Knoten Namen den Namespace Namen und einen Doppelpunkt (z. b.//Namespacename: Node) voran.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt die Pfad- und Dateinamen der zu durchsuchenden XML-Dateien an.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -XML

Gibt mindestens einen XML-Knoten an.

Ein XML-Dokument wird als eine Auflistung von XML-Knoten verarbeitet.
Wenn Sie ein XML-Dokument an **Select-XML** übergeben, wird jeder Dokument Knoten separat durchsucht, während er die Pipeline durchläuft.

```yaml
Type: System.Xml.XmlNode[]
Parameter Sets: Xml
Aliases: Node

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -XPath

Gibt eine XPath-Suchabfrage an.
Bei der Abfragesprache wird Groß-/Kleinschreibung beachtet.
Dieser Parameter ist erforderlich.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. String-oder System.Xml.Xml-Knoten

Sie können einen Pfad oder XML-Knoten über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Microsoft. PowerShell. Commands. selectxmlinfo

## HINWEISE

XPath ist eine Standardsprache, die Teile eines XML-Dokuments identifiziert. Weitere Informationen zur XPath-Sprache finden Sie unter [XPath-Referenz](/dotnet/standard/data/xml/select-nodes-using-xpath-navigation) und im Abschnitt Auswahl Filter der [Ereignis Auswahl](/previous-versions//aa385231(v=vs.85)).

## VERWANDTE LINKS

[ConvertTo-Xml](ConvertTo-Xml.md)
