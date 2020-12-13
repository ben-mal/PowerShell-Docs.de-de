---
ms.date: 09/13/2016
ms.topic: reference
title: Listenansicht (Label)
description: Listenansicht (Label)
ms.openlocfilehash: 2d341ae95d025e0f95b5d88b96afb846b62b092f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666687"
---
# <a name="list-view-labels"></a><span data-ttu-id="e147a-103">Listenansicht (Label)</span><span class="sxs-lookup"><span data-stu-id="e147a-103">List View (Labels)</span></span>

<span data-ttu-id="e147a-104">Dieses Beispiel zeigt, wie Sie eine Listenansicht implementieren, in der eine benutzerdefinierte Bezeichnung für jede Zeile der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e147a-104">This example shows how to implement a list view that displays a custom label for each row of the list.</span></span> <span data-ttu-id="e147a-105">Diese Listenansicht zeigt die Eigenschaften des [System. ServiceProcess. ServiceController an? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt, das vom Cmdlet " [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) " zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e147a-105">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="e147a-106">Weitere Informationen zu den Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="e147a-106">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="e147a-107">So laden Sie diese Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="e147a-107">To load this formatting file</span></span>

1. <span data-ttu-id="e147a-108">Kopieren Sie den XML-Code aus dem Beispiel Abschnitt dieses Themas in eine Textdatei.</span><span class="sxs-lookup"><span data-stu-id="e147a-108">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="e147a-109">Speichern Sie die Textdatei.</span><span class="sxs-lookup"><span data-stu-id="e147a-109">Save the text file.</span></span> <span data-ttu-id="e147a-110">Stellen Sie sicher, dass `format.ps1xml` Sie die Erweiterung der Datei hinzufügen, um Sie als Formatierungs Datei zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e147a-110">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="e147a-111">Öffnen Sie Windows PowerShell, und führen Sie den folgenden Befehl aus, um die Formatierungs Datei in die aktuelle Sitzung zu laden: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="e147a-111">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="e147a-112">Mit dieser Formatierungs Datei wird die Anzeige eines Objekts definiert, das bereits durch eine Windows PowerShell-Formatierungs Datei definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e147a-112">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="e147a-113">Sie müssen den `prependPath` -Parameter verwenden, wenn Sie das-Cmdlet ausführen, und Sie können diese Formatierungs Datei nicht als Modul laden.</span><span class="sxs-lookup"><span data-stu-id="e147a-113">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="e147a-114">Zeigt</span><span class="sxs-lookup"><span data-stu-id="e147a-114">Demonstrates</span></span>

<span data-ttu-id="e147a-115">Diese Formatierungs Datei veranschaulicht die folgenden XML-Elemente:</span><span class="sxs-lookup"><span data-stu-id="e147a-115">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="e147a-116">Das [Name](./name-element-for-view-format.md) -Element für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="e147a-116">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="e147a-117">Das [viewselectedby](./viewselectedby-element-format.md) -Element, das definiert, welche Objekte von der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e147a-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="e147a-118">Das [ListControl](./listcontrol-element-format.md) -Element, das definiert, welche Eigenschaft von der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e147a-118">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="e147a-119">Das [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) -Element, das definiert, was in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e147a-119">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="e147a-120">Das [Label](./label-element-for-listitem-for-listcontrol-format.md) -Element, das definiert, was in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e147a-120">The [Label](./label-element-for-listitem-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="e147a-121">Das [propertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) -Element, das definiert, welche Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e147a-121">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="e147a-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e147a-122">Example</span></span>

<span data-ttu-id="e147a-123">Der folgende XML-Code definiert eine Listenansicht, in der in jeder Zeile eine benutzerdefinierte Bezeichnung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e147a-123">The following XML defines a list view that displays a custom label in each row.</span></span> <span data-ttu-id="e147a-124">In diesem Fall enthält die Bezeichnung den Eigenschaftsnamen, bei dem jeder Buchstabe groß geschrieben ist, und das Wort "Property".</span><span class="sxs-lookup"><span data-stu-id="e147a-124">In this case, the label includes the property name with each letter capitalized and the word "property".</span></span> <span data-ttu-id="e147a-125">In jeder Zeile wird der Name der Eigenschaft angezeigt, gefolgt vom Wert der-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e147a-125">In each row, the name of the property is displayed followed by the value of the property.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>
          <ListItem>
            <Label>NAME property</Label>
            <PropertyName>Name</PropertyName>
          </ListItem>
          <ListItem>
            <Label>DISPLAYNAME property</Label>
            <PropertyName>DisplayName</PropertyName>
          </ListItem>
          <ListItem>
            <Label>STATUS property</Label>
            <PropertyName>Status</PropertyName>
          </ListItem>
          <ListItem>
            <Label>SERVICETYPE property</Label>
            <PropertyName>ServiceType</PropertyName>
          </ListItem>
        </ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>

  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="e147a-126">Das folgende Beispiel zeigt, wie Windows PowerShell [System. ServiceProcess. ServiceController anzeigt? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekte, nachdem diese Format Datei geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="e147a-126">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
NAME property        : Fax
DISPLAYNAME property : Fax
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FCSAM
DISPLAYNAME property : Microsoft Antimalware Service
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : fdPHost
DISPLAYNAME property : Function Discovery Provider Host
STATUS property      : Stopped
SERVICETYPE property : Win32ShareProcess

NAME property        : FDResPub
DISPLAYNAME property : Function Discovery Resource Publication
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache
DISPLAYNAME property : Windows Font Cache Service
STATUS property      : Running
SERVICETYPE property : Win32ShareProcess

NAME property        : FontCache3.0.0.0
DISPLAYNAME property : Windows Presentation Foundation Font Cache 3.0.0.0
STATUS property      : Stopped
SERVICETYPE property : Win32OwnProcess

NAME property        : FSysAgent
DISPLAYNAME property : Microsoft Forefront System Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess

NAME property        : FwcAgent
DISPLAYNAME property : Firewall Client Agent
STATUS property      : Running
SERVICETYPE property : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="e147a-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e147a-127">See Also</span></span>

[<span data-ttu-id="e147a-128">Beispiele für Formatierungsdateien</span><span class="sxs-lookup"><span data-stu-id="e147a-128">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="e147a-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e147a-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
