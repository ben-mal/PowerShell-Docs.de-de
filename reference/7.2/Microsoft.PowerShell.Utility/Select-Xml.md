---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Xml
ms.openlocfilehash: 7686ade747345b7c770772067007b8abf13aac3d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602924"
---
# <span data-ttu-id="52596-102">Select-Xml</span><span class="sxs-lookup"><span data-stu-id="52596-102">Select-Xml</span></span>

## <span data-ttu-id="52596-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="52596-103">SYNOPSIS</span></span>
<span data-ttu-id="52596-104">Sucht Text in einer XML-Zeichenfolge oder einem XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="52596-104">Finds text in an XML string or document.</span></span>

## <span data-ttu-id="52596-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="52596-105">SYNTAX</span></span>

### <span data-ttu-id="52596-106">XML (Standard)</span><span class="sxs-lookup"><span data-stu-id="52596-106">Xml (Default)</span></span>

```
Select-Xml [-Xml] <XmlNode[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="52596-107">Pfad</span><span class="sxs-lookup"><span data-stu-id="52596-107">Path</span></span>

```
Select-Xml [-Path] <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="52596-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="52596-108">LiteralPath</span></span>

```
Select-Xml -LiteralPath <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="52596-109">Inhalt</span><span class="sxs-lookup"><span data-stu-id="52596-109">Content</span></span>

```
Select-Xml -Content <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="52596-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="52596-110">DESCRIPTION</span></span>

<span data-ttu-id="52596-111">Mit dem **Select-XML-** Cmdlet können Sie XPath-Abfragen verwenden, um Text in XML-Zeichen folgen und-Dokumenten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="52596-111">The **Select-Xml** cmdlet lets you use XPath queries to search for text in XML strings and documents.</span></span>
<span data-ttu-id="52596-112">Geben Sie eine XPath-Abfrage ein, und verwenden Sie den Parameter *Content*, *path* oder *XML* , um das zu durchsuchende XML anzugeben.</span><span class="sxs-lookup"><span data-stu-id="52596-112">Enter an XPath query, and use the *Content*, *Path*, or *Xml* parameter to specify the XML to be searched.</span></span>

## <span data-ttu-id="52596-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="52596-113">EXAMPLES</span></span>

### <span data-ttu-id="52596-114">Beispiel 1: Auswählen von aliasproperty-Knoten</span><span class="sxs-lookup"><span data-stu-id="52596-114">Example 1: Select AliasProperty nodes</span></span>

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

<span data-ttu-id="52596-115">In diesem Beispiel werden die Aliaseigenschaften in „Types.ps1xml“ abgerufen.</span><span class="sxs-lookup"><span data-stu-id="52596-115">This example gets the alias properties in the Types.ps1xml.</span></span>
<span data-ttu-id="52596-116">(Weitere Informationen zu dieser Datei finden Sie unter about_Types.ps1xml.)</span><span class="sxs-lookup"><span data-stu-id="52596-116">(For information about this file, see about_Types.ps1xml.)</span></span>

<span data-ttu-id="52596-117">Der erste Befehl speichert den Pfad zur Datei „Types.ps1xml“ in der $Path-Variablen.</span><span class="sxs-lookup"><span data-stu-id="52596-117">The first command saves the path to the Types.ps1xml file in the $Path variable.</span></span>

<span data-ttu-id="52596-118">Der zweite Befehl speichert den XML-Pfad zum AliasProperty-Knoten in der $XPath-Variablen.</span><span class="sxs-lookup"><span data-stu-id="52596-118">The second command saves the XML path to the AliasProperty node in the $XPath variable.</span></span>

<span data-ttu-id="52596-119">Der dritte Befehl verwendet das **Select-Xml**-Cmdlet zum Abrufen der AliasProperty-Knoten, die durch die XPath-Anweisung der Datei „Types.ps1xml“ identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="52596-119">The third command uses the **Select-Xml** cmdlet to get the AliasProperty nodes that are identified by the XPath statement from the Types.ps1xml file.</span></span>
<span data-ttu-id="52596-120">Der Befehl verwendet einen Pipeline Operator, um die aliasproperty-Knoten an das Select-Object-Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="52596-120">The command uses a pipeline operator to send the AliasProperty nodes to the Select-Object cmdlet.</span></span>
<span data-ttu-id="52596-121">Der *ExpandProperty* -Parameter erweitert das **Knoten** Objekt und gibt dessen Eigenschaften Name und referencedmembership Name zurück.</span><span class="sxs-lookup"><span data-stu-id="52596-121">The *ExpandProperty* parameter expands the **Node** object and returns its Name and ReferencedMemberName properties.</span></span>

<span data-ttu-id="52596-122">Das Ergebnis zeigt die Name-Eigenschaft und ReferencedMemberName-Eigenschaft jeder Aliaseigenschaft in der Datei „Types.ps1xml“ an.</span><span class="sxs-lookup"><span data-stu-id="52596-122">The result shows the Name and ReferencedMemberName of each alias property in the Types.ps1xml file.</span></span>
<span data-ttu-id="52596-123">Beispielsweise gibt es eine **count** -Eigenschaft, die ein Alias der **length** -Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="52596-123">For example, there is a **Count** property that is an alias of the **Length** property.</span></span>

### <span data-ttu-id="52596-124">Beispiel 2: Eingabe eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="52596-124">Example 2: Input an XML document</span></span>

```
PS C:\> [xml]$Types = Get-Content $Pshome\Types.ps1xml
PS C:\> Select-Xml -Xml $Types -XPath "//MethodName"
```

<span data-ttu-id="52596-125">In diesem Beispiel wird gezeigt, wie der *XML* -Parameter verwendet wird, um ein XML-Dokument für das **Select-XML** -Cmdlet bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="52596-125">This example shows how to use the *XML* parameter to provide an XML document to the **Select-Xml** cmdlet.</span></span>

<span data-ttu-id="52596-126">Der erste Befehl verwendet das Cmdlet "Get-Content", um den Inhalt der Types.ps1XML-Datei zu erhalten und in der $Types-Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="52596-126">The first command uses the Get-Content cmdlet to get the content of the Types.ps1xml file and save it in the $Types variable.</span></span>
<span data-ttu-id="52596-127">Der XML-Code wandelt \[ \] die Variable in ein XML-Objekt um.</span><span class="sxs-lookup"><span data-stu-id="52596-127">The \[xml\] casts the variable as an XML object.</span></span>

<span data-ttu-id="52596-128">Der zweite Befehl verwendet das **Select-Xml**-Cmdlet zum Abrufen der MethodName-Knoten in der Datei „Types.ps1xml“.</span><span class="sxs-lookup"><span data-stu-id="52596-128">The second command uses the **Select-Xml** cmdlet to get the MethodName nodes in the Types.ps1xml file.</span></span>
<span data-ttu-id="52596-129">Der Befehl verwendet den *Xml*-Parameter, um den XML-Inhalt in der $Types-Variablen und den *XPath*-Parameter anzugeben, der den Pfad zum MethodName-Knoten festlegt.</span><span class="sxs-lookup"><span data-stu-id="52596-129">The command uses the *Xml* parameter to specify the XML content in the $Types variable and the *XPath* parameter to specify the path to the MethodName node.</span></span>

### <span data-ttu-id="52596-130">Beispiel 3: Durchsuchen von PowerShell-Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="52596-130">Example 3: Search PowerShell Help files</span></span>

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

<span data-ttu-id="52596-131">In diesem Beispiel wird gezeigt, wie das Cmdlet **Select-XML** verwendet wird, um die XML-basierten Cmdlet-Hilfedateien von PowerShell zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="52596-131">This example shows how to use the **Select-Xml** cmdlet to search the PowerShell XML-based cmdlet help files.</span></span>
<span data-ttu-id="52596-132">In diesem Beispiel suchen wir den Cmdletnamen, der als Titel der einzelnen Hilfedateien dient, und den Pfad zur Hilfedatei.</span><span class="sxs-lookup"><span data-stu-id="52596-132">In this example, we'll search for the cmdlet name that serves as a title for each help file and the path to the help file.</span></span>

<span data-ttu-id="52596-133">Der erste Befehl erstellt eine Hashtabelle, die den für die Hilfedateien verwendeten XML-Namespace darstellt, und speichert sie in der $Namespace-Variablen.</span><span class="sxs-lookup"><span data-stu-id="52596-133">The first command creates a hash table that represents the XML namespace that is used for the help files and saves it in the $Namespace variable.</span></span>

### <span data-ttu-id="52596-134">Beispiel 4: unterschiedliche Möglichkeiten zum Eingeben von XML</span><span class="sxs-lookup"><span data-stu-id="52596-134">Example 4: Different ways to input XML</span></span>

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

<span data-ttu-id="52596-135">In diesem Beispiel werden zwei verschiedene Möglichkeiten zum Senden von XML an das **Select-XML-** Cmdlet veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="52596-135">This example shows two different ways to send XML to the **Select-Xml** cmdlet.</span></span>

<span data-ttu-id="52596-136">Der erste Befehl speichert eine here-Zeichenfolge, die XML in der $XML Variable enthält.</span><span class="sxs-lookup"><span data-stu-id="52596-136">The first command saves a here-string that contains XML in the $Xml variable.</span></span>
<span data-ttu-id="52596-137">Weitere Informationen zu here-strings finden Sie unter about_Quoting_Rules.</span><span class="sxs-lookup"><span data-stu-id="52596-137">(For more information about here-strings, see about_Quoting_Rules.)</span></span>

### <span data-ttu-id="52596-138">Beispiel 5: Verwenden des xmlns-Standard Namespace</span><span class="sxs-lookup"><span data-stu-id="52596-138">Example 5: Use the default xmlns namespace</span></span>

```
PS C:\> $SnippetNamespace = @{snip = "http://schemas.microsoft.com/PowerShell/Snippets"}

The second command uses the **Select-Xml** cmdlet to get the content of the Title element of each snippet. It uses the *Path* parameter to specify the Snippets directory and the *Namespace* parameter to specify the namespace in the $SnippetNamespace variable. The value of the *XPath* parameter is the "snip" namespace key, a colon (:), and the name of the Title element.The command uses a pipeline operator (|) to send each **Node** property that **Select-Xml** returns to the ForEach-Object cmdlet, which gets the title in the value of the **InnerXml** property of the node.
PS C:\> Select-Xml -Path $Home\Documents\WindowsPowerShell\Snippets -Namespace $SnippetNamespace -XPath "//snip:Title" | foreach {$_.Node.Innerxml}
```

<span data-ttu-id="52596-139">Dieses Beispiel zeigt, wie Sie das **Select-XML-** Cmdlet mit XML-Dokumenten verwenden, die den xmlns-Standard Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="52596-139">This example shows how to use the **Select-Xml** cmdlet with XML documents that use the default xmlns namespace.</span></span>
<span data-ttu-id="52596-140">Im Beispiel werden die Titel der vom Benutzer erstellten Windows PowerShell ISE-Codeausschnittsdateien abgerufen.</span><span class="sxs-lookup"><span data-stu-id="52596-140">The example gets the titles of Windows PowerShell ISE user-created snippet files.</span></span>
<span data-ttu-id="52596-141">Weitere Informationen zu Codeausschnitten finden Sie unter New-IseSnippet.</span><span class="sxs-lookup"><span data-stu-id="52596-141">For information about snippets, see New-IseSnippet.</span></span>

<span data-ttu-id="52596-142">Der erste Befehl erstellt eine Hash Tabelle für den Standard Namespace, der von Code Ausschnitt-XML-Dateien verwendet wird, und weist ihn der $SnippetNamespace Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="52596-142">The first command creates a hash table for the default namespace that snippet XML files use and assigns it to the $SnippetNamespace variable.</span></span>
<span data-ttu-id="52596-143">Der Hashtabellenwert befindet sich im XMLNS-Schema-URI der XML-Codeausschnittsdatei.</span><span class="sxs-lookup"><span data-stu-id="52596-143">The hash table value is the XMLNS schema URI in the snippet XML.</span></span>
<span data-ttu-id="52596-144">Der Name des Hash Tabellen Schlüssels (Snip) ist willkürlich.</span><span class="sxs-lookup"><span data-stu-id="52596-144">The hash table key name, snip, is arbitrary.</span></span>
<span data-ttu-id="52596-145">Sie können einen beliebigen Namen verwenden, der nicht reserviert ist, aber Sie können keine xmlns verwenden.</span><span class="sxs-lookup"><span data-stu-id="52596-145">You can use any name that is not reserved, but you cannot use xmlns.</span></span>

## <span data-ttu-id="52596-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="52596-146">PARAMETERS</span></span>

### <span data-ttu-id="52596-147">-Inhalt</span><span class="sxs-lookup"><span data-stu-id="52596-147">-Content</span></span>

<span data-ttu-id="52596-148">Gibt eine Zeichenfolge an, die den zu suchenden XML-Inhalt enthält.</span><span class="sxs-lookup"><span data-stu-id="52596-148">Specifies a string that contains the XML to search.</span></span>
<span data-ttu-id="52596-149">Sie können Zeichen folgen auch an **Select-XML** übergeben.</span><span class="sxs-lookup"><span data-stu-id="52596-149">You can also pipe strings to **Select-Xml**.</span></span>

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

### <span data-ttu-id="52596-150">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="52596-150">-LiteralPath</span></span>

<span data-ttu-id="52596-151">Gibt die Pfad- und Dateinamen der zu durchsuchenden XML-Dateien an.</span><span class="sxs-lookup"><span data-stu-id="52596-151">Specifies the paths and file names of the XML files to search.</span></span>
<span data-ttu-id="52596-152">Im Gegensatz zu *Path* wird der Wert des *LiteralPath*-Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="52596-152">Unlike *Path*, the value of the *LiteralPath* parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="52596-153">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="52596-153">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="52596-154">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="52596-154">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="52596-155">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="52596-155">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="52596-156">-Namespace</span><span class="sxs-lookup"><span data-stu-id="52596-156">-Namespace</span></span>

<span data-ttu-id="52596-157">Gibt eine Hashtabelle der im XML-Inhalt verwendeten Namespaces an.</span><span class="sxs-lookup"><span data-stu-id="52596-157">Specifies a hash table of the namespaces used in the XML.</span></span>
<span data-ttu-id="52596-158">Verwenden Sie das Format @ { \<namespaceName\>  =  \<namespaceValue\> }.</span><span class="sxs-lookup"><span data-stu-id="52596-158">Use the format @{\<namespaceName\> = \<namespaceValue\>}.</span></span>

<span data-ttu-id="52596-159">Wenn der XML-Code den Standard Namespace verwendet, der mit xmlns beginnt, verwenden Sie einen beliebigen Schlüssel für den Namespace Namen.</span><span class="sxs-lookup"><span data-stu-id="52596-159">When the XML uses the default namespace, which begins with xmlns, use an arbitrary key for the namespace name.</span></span>
<span data-ttu-id="52596-160">Xmlns können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52596-160">You cannot use xmlns.</span></span>
<span data-ttu-id="52596-161">Stellen Sie in der XPath-Anweisung jedem Knoten Namen den Namespace Namen und einen Doppelpunkt (z. b.//Namespacename: Node) voran.</span><span class="sxs-lookup"><span data-stu-id="52596-161">In the XPath statement, prefix each node name with the namespace name and a colon, such as //namespaceName:Node.</span></span>

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

### <span data-ttu-id="52596-162">-Path</span><span class="sxs-lookup"><span data-stu-id="52596-162">-Path</span></span>

<span data-ttu-id="52596-163">Gibt die Pfad- und Dateinamen der zu durchsuchenden XML-Dateien an.</span><span class="sxs-lookup"><span data-stu-id="52596-163">Specifies the path and file names of the XML files to search.</span></span>
<span data-ttu-id="52596-164">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="52596-164">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="52596-165">-XML</span><span class="sxs-lookup"><span data-stu-id="52596-165">-Xml</span></span>

<span data-ttu-id="52596-166">Gibt mindestens einen XML-Knoten an.</span><span class="sxs-lookup"><span data-stu-id="52596-166">Specifies one or more XML nodes.</span></span>

<span data-ttu-id="52596-167">Ein XML-Dokument wird als eine Auflistung von XML-Knoten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="52596-167">An XML document will be processed as a collection of XML nodes.</span></span>
<span data-ttu-id="52596-168">Wenn Sie ein XML-Dokument an **Select-XML** übergeben, wird jeder Dokument Knoten separat durchsucht, während er die Pipeline durchläuft.</span><span class="sxs-lookup"><span data-stu-id="52596-168">If you pipe an XML document to **Select-Xml**, each document node will be searched separately as it comes through the pipeline.</span></span>

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

### <span data-ttu-id="52596-169">-XPath</span><span class="sxs-lookup"><span data-stu-id="52596-169">-XPath</span></span>

<span data-ttu-id="52596-170">Gibt eine XPath-Suchabfrage an.</span><span class="sxs-lookup"><span data-stu-id="52596-170">Specifies an XPath search query.</span></span>
<span data-ttu-id="52596-171">Bei der Abfragesprache wird Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="52596-171">The query language is case-sensitive.</span></span>
<span data-ttu-id="52596-172">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="52596-172">This parameter is required.</span></span>

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

### <span data-ttu-id="52596-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="52596-173">CommonParameters</span></span>

<span data-ttu-id="52596-174">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="52596-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="52596-175">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="52596-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="52596-176">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="52596-176">INPUTS</span></span>

### <span data-ttu-id="52596-177">System. String-oder System.Xml.Xml-Knoten</span><span class="sxs-lookup"><span data-stu-id="52596-177">System.String or System.Xml.XmlNode</span></span>

<span data-ttu-id="52596-178">Sie können einen Pfad oder XML-Knoten über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="52596-178">You can pipe a path or XML node to this cmdlet.</span></span>

## <span data-ttu-id="52596-179">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="52596-179">OUTPUTS</span></span>

### <span data-ttu-id="52596-180">Microsoft. PowerShell. Commands. selectxmlinfo</span><span class="sxs-lookup"><span data-stu-id="52596-180">Microsoft.PowerShell.Commands.SelectXmlInfo</span></span>

## <span data-ttu-id="52596-181">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="52596-181">NOTES</span></span>

<span data-ttu-id="52596-182">XPath ist eine Standardsprache, die Teile eines XML-Dokuments identifiziert.</span><span class="sxs-lookup"><span data-stu-id="52596-182">XPath is a standard language that is designed to identify parts of an XML document.</span></span> <span data-ttu-id="52596-183">Weitere Informationen zur XPath-Sprache finden Sie unter [XPath-Referenz](/dotnet/standard/data/xml/select-nodes-using-xpath-navigation) und im Abschnitt Auswahl Filter der [Ereignis Auswahl](/previous-versions//aa385231(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="52596-183">For more information about the XPath language, see [XPath Reference](/dotnet/standard/data/xml/select-nodes-using-xpath-navigation) and the Selection Filters section of [Event Selection](/previous-versions//aa385231(v=vs.85)).</span></span>

## <span data-ttu-id="52596-184">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="52596-184">RELATED LINKS</span></span>

[<span data-ttu-id="52596-185">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="52596-185">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)
