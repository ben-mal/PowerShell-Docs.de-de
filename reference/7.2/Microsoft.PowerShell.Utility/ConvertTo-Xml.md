---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Xml
ms.openlocfilehash: e461c07360b3d9eaf7d9a3c8875d34cd1fc841e8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601125"
---
# <span data-ttu-id="d014e-102">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="d014e-102">ConvertTo-Xml</span></span>

## <span data-ttu-id="d014e-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d014e-103">SYNOPSIS</span></span>
<span data-ttu-id="d014e-104">Erstellt eine XML-basierte Darstellung eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="d014e-104">Creates an XML-based representation of an object.</span></span>

## <span data-ttu-id="d014e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d014e-105">SYNTAX</span></span>

```
ConvertTo-Xml [-Depth <Int32>] [-InputObject] <PSObject> [-NoTypeInformation] [-As <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="d014e-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d014e-106">DESCRIPTION</span></span>

<span data-ttu-id="d014e-107">Das `ConvertTo-Xml` -Cmdlet erstellt eine [XML-basierte](/dotnet/api/system.xml.xmldocument) Darstellung eines oder mehrerer .NET-Objekte.</span><span class="sxs-lookup"><span data-stu-id="d014e-107">The `ConvertTo-Xml` cmdlet creates an [XML-based](/dotnet/api/system.xml.xmldocument) representation of one or more more .NET objects.</span></span> <span data-ttu-id="d014e-108">Um dieses Cmdlet zu verwenden, übergeben Sie ein oder mehrere Objekte an das Cmdlet, oder verwenden Sie den **Inputobject** -Parameter, um das Objekt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d014e-108">To use this cmdlet, pipe one or more objects to the cmdlet, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="d014e-109">Wenn Sie mehrere Objekte an übergeben `ConvertTo-Xml` oder den **Inputobject** -Parameter verwenden, um mehrere Objekte zu senden, `ConvertTo-Xml` gibt ein einzelnes XML-Dokument im Arbeitsspeicher zurück, das Darstellungen aller Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="d014e-109">When you pipe multiple objects to `ConvertTo-Xml` or use the **InputObject** parameter to submit multiple objects, `ConvertTo-Xml` returns a single, in-memory XML document that includes representations of all of the objects.</span></span>

<span data-ttu-id="d014e-110">Dieses Cmdlet ähnelt [Export-CliXML](./Export-Clixml.md) , mit der Ausnahme, dass `Export-Clixml` das resultierende XML in einer XML-Datei mit [Common Language Infrastructure (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm) speichert, die als Objekte mit [Import-CliXML](./Import-Clixml.md)erneut importiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d014e-110">This cmdlet is similar to [Export-Clixml](./Export-Clixml.md) except that `Export-Clixml` stores the resulting XML in a [Common Language Infrastructure(CLI) XML](https://www.ecma-international.org/publications/standards/Ecma-335.htm) file that can be reimported as objects with [Import-Clixml](./Import-Clixml.md).</span></span> <span data-ttu-id="d014e-111">`ConvertTo-Xml` gibt eine Speicher interne Darstellung eines XML-Dokuments zurück, sodass Sie die Verarbeitung in PowerShell fortsetzen können.</span><span class="sxs-lookup"><span data-stu-id="d014e-111">`ConvertTo-Xml` returns an in-memory representation of an XML document, so you can continue to process it in PowerShell.</span></span> <span data-ttu-id="d014e-112">`ConvertTo-Xml` bietet keine Option zum Konvertieren von Objekten in die CLI-XML.</span><span class="sxs-lookup"><span data-stu-id="d014e-112">`ConvertTo-Xml` does not have an option to convert objects to CLI XML.</span></span>

## <span data-ttu-id="d014e-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d014e-113">EXAMPLES</span></span>

### <span data-ttu-id="d014e-114">Beispiel 1: Konvertieren eines Datums in XML</span><span class="sxs-lookup"><span data-stu-id="d014e-114">Example 1: Convert a date to XML</span></span>

```
PS C:\> Get-Date | ConvertTo-Xml
```

<span data-ttu-id="d014e-115">Dieser Befehl konvertiert das aktuelle Datum (ein **DateTime** -Objekt) in XML.</span><span class="sxs-lookup"><span data-stu-id="d014e-115">This command converts the current date (a **DateTime** object) to XML.</span></span>

### <span data-ttu-id="d014e-116">Beispiel 2: Konvertieren von Prozessen in XML</span><span class="sxs-lookup"><span data-stu-id="d014e-116">Example 2: Convert processes to XML</span></span>

```
PS C:\> ConvertTo-Xml -As "Document" -InputObject (Get-Process) -Depth 3
```

<span data-ttu-id="d014e-117">Mit diesem Befehl werden die Prozessobjekte, die alle Prozesse auf dem Computer darstellen, in ein XML-Dokument konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d014e-117">This command converts the process objects that represent all of the processes on the computer into an XML document.</span></span> <span data-ttu-id="d014e-118">Die Objekte werden auf eine Tiefe von drei Ebenen erweitert.</span><span class="sxs-lookup"><span data-stu-id="d014e-118">The objects are expanded to a depth of three levels.</span></span>

## <span data-ttu-id="d014e-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d014e-119">PARAMETERS</span></span>

### <span data-ttu-id="d014e-120">-AS</span><span class="sxs-lookup"><span data-stu-id="d014e-120">-As</span></span>

<span data-ttu-id="d014e-121">Bestimmt das Ausgabeformat.</span><span class="sxs-lookup"><span data-stu-id="d014e-121">Determines the output format.</span></span>
<span data-ttu-id="d014e-122">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="d014e-122">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d014e-123">Eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d014e-123">String.</span></span>
<span data-ttu-id="d014e-124">Gibt eine einzelne Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="d014e-124">Returns a single string.</span></span>
- <span data-ttu-id="d014e-125">Stream.</span><span class="sxs-lookup"><span data-stu-id="d014e-125">Stream.</span></span>
<span data-ttu-id="d014e-126">Gibt ein Array von Zeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="d014e-126">Returns an array of strings.</span></span>
- <span data-ttu-id="d014e-127">Dokument.</span><span class="sxs-lookup"><span data-stu-id="d014e-127">Document.</span></span>
<span data-ttu-id="d014e-128">Gibt ein **XmlDocument** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="d014e-128">Returns an **XmlDocument** object.</span></span>

<span data-ttu-id="d014e-129">Der Standardwert ist "Document".</span><span class="sxs-lookup"><span data-stu-id="d014e-129">The default value is Document.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Stream, String, Document

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d014e-130">-Tiefe</span><span class="sxs-lookup"><span data-stu-id="d014e-130">-Depth</span></span>

<span data-ttu-id="d014e-131">Gibt an, wie viele Ebenen der enthaltenen Objekte in der XML-Darstellung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d014e-131">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="d014e-132">Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="d014e-132">The default value is 1.</span></span>

<span data-ttu-id="d014e-133">Wenn beispielsweise die Eigenschaften des Objekts ebenfalls Objekte enthalten, müssen Sie eine Tiefe von 2 angeben, um eine XML-Darstellung der Eigenschaften der enthaltenen Objekte zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d014e-133">For example, if the object's properties also contain objects, to save an XML representation of the properties of the contained objects, you must specify a depth of 2.</span></span>

<span data-ttu-id="d014e-134">Der Standardwert kann für den Objekttyp in den Dateien „Types.ps1xml“ überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d014e-134">The default value can be overridden for the object type in the Types.ps1xml files.</span></span> <span data-ttu-id="d014e-135">Weitere Informationen finden Sie unter „about_Types.ps1xml“.</span><span class="sxs-lookup"><span data-stu-id="d014e-135">For more information, see about_Types.ps1xml.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d014e-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d014e-136">-InputObject</span></span>

<span data-ttu-id="d014e-137">Gibt das zu konvertierende Objekt an.</span><span class="sxs-lookup"><span data-stu-id="d014e-137">Specifies the object to be converted.</span></span> <span data-ttu-id="d014e-138">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d014e-138">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="d014e-139">Sie können Objekte auch über die Pipeline an **ConvertTo-XML** übergeben.</span><span class="sxs-lookup"><span data-stu-id="d014e-139">You can also pipe objects to **ConvertTo-XML**.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d014e-140">-Notypeinformation</span><span class="sxs-lookup"><span data-stu-id="d014e-140">-NoTypeInformation</span></span>

<span data-ttu-id="d014e-141">Lässt das Type-Attribute in den Objektknoten aus.</span><span class="sxs-lookup"><span data-stu-id="d014e-141">Omits the Type attribute from the object nodes.</span></span>

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

### <span data-ttu-id="d014e-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d014e-142">CommonParameters</span></span>

<span data-ttu-id="d014e-143">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d014e-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d014e-144">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d014e-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d014e-145">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d014e-145">INPUTS</span></span>

### <span data-ttu-id="d014e-146">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="d014e-146">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="d014e-147">Sie können jedes beliebige Objekt über die Pipeline an **ConvertTo-XML** übergeben.</span><span class="sxs-lookup"><span data-stu-id="d014e-147">You can pipe any object to **ConvertTo-XML**.</span></span>

## <span data-ttu-id="d014e-148">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d014e-148">OUTPUTS</span></span>

### <span data-ttu-id="d014e-149">System. String-oder System.Xml.Xml-Dokument</span><span class="sxs-lookup"><span data-stu-id="d014e-149">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="d014e-150">Der Wert des *As* -Parameters bestimmt den von **ConvertTo-XML** zurückgegebenen Objekttyp.</span><span class="sxs-lookup"><span data-stu-id="d014e-150">The value of the *As* parameter determines the type of object that **ConvertTo-XML** returns.</span></span>

## <span data-ttu-id="d014e-151">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d014e-151">NOTES</span></span>

## <span data-ttu-id="d014e-152">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d014e-152">RELATED LINKS</span></span>

[<span data-ttu-id="d014e-153">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="d014e-153">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="d014e-154">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="d014e-154">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="d014e-155">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="d014e-155">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="d014e-156">Get-Date</span><span class="sxs-lookup"><span data-stu-id="d014e-156">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="d014e-157">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="d014e-157">Import-Clixml</span></span>](Import-Clixml.md)

