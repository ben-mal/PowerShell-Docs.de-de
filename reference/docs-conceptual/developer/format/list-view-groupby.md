---
ms.date: 09/13/2016
ms.topic: reference
title: Listenansicht (GroupBy)
description: Listenansicht (GroupBy)
ms.openlocfilehash: e039c38d1e4e93f65a508fe60aaaf35c64ebe2ed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666619"
---
# <a name="list-view-groupby"></a><span data-ttu-id="50f0c-103">Listenansicht (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="50f0c-103">List View (GroupBy)</span></span>

<span data-ttu-id="50f0c-104">In diesem Beispiel wird gezeigt, wie eine Listenansicht implementiert wird, die die Zeilen der Liste in Gruppen trennt.</span><span class="sxs-lookup"><span data-stu-id="50f0c-104">This example shows how to implement a list view that separates the rows of the list into groups.</span></span> <span data-ttu-id="50f0c-105">Diese Listenansicht zeigt die Eigenschaften des [System. ServiceProcess. ServiceController an? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekte, die vom Cmdlet " [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) " zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="50f0c-105">This list view displays the properties of the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the [Get-Service](/powershell/module/Microsoft.PowerShell.Management/Get-Service) cmdlet.</span></span> <span data-ttu-id="50f0c-106">Weitere Informationen zu den Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="50f0c-106">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="50f0c-107">So laden Sie diese Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="50f0c-107">To load this formatting file</span></span>

1. <span data-ttu-id="50f0c-108">Kopieren Sie den XML-Code aus dem Beispiel Abschnitt dieses Themas in eine Textdatei.</span><span class="sxs-lookup"><span data-stu-id="50f0c-108">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="50f0c-109">Speichern Sie die Textdatei.</span><span class="sxs-lookup"><span data-stu-id="50f0c-109">Save the text file.</span></span> <span data-ttu-id="50f0c-110">Stellen Sie sicher, dass `format.ps1xml` Sie die Erweiterung der Datei hinzufügen, um Sie als Formatierungs Datei zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="50f0c-110">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="50f0c-111">Öffnen Sie Windows PowerShell, und führen Sie den folgenden Befehl aus, um die Formatierungs Datei in die aktuelle Sitzung zu laden: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="50f0c-111">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="50f0c-112">Mit dieser Formatierungs Datei wird die Anzeige eines Objekts definiert, das bereits durch eine Windows PowerShell-Formatierungs Datei definiert ist.</span><span class="sxs-lookup"><span data-stu-id="50f0c-112">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="50f0c-113">Sie müssen den `prependPath` -Parameter verwenden, wenn Sie das-Cmdlet ausführen, und Sie können diese Formatierungs Datei nicht als Modul laden.</span><span class="sxs-lookup"><span data-stu-id="50f0c-113">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="50f0c-114">Zeigt</span><span class="sxs-lookup"><span data-stu-id="50f0c-114">Demonstrates</span></span>

<span data-ttu-id="50f0c-115">Diese Formatierungs Datei veranschaulicht die folgenden XML-Elemente:</span><span class="sxs-lookup"><span data-stu-id="50f0c-115">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="50f0c-116">Das [Name](./name-element-for-view-format.md) -Element für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="50f0c-116">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="50f0c-117">Das [viewselectedby](./viewselectedby-element-format.md) -Element, das definiert, welche Objekte von der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="50f0c-117">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="50f0c-118">Das [GroupBy](./viewselectedby-element-format.md) -Element, das definiert, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="50f0c-118">The [GroupBy](./viewselectedby-element-format.md) element that defines how a new group of objects is displayed.</span></span>

- <span data-ttu-id="50f0c-119">Das [ListControl](./listcontrol-element-format.md) -Element, das definiert, welche Eigenschaft von der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="50f0c-119">The [ListControl](./listcontrol-element-format.md) element that defines what property is displayed by the view.</span></span>

- <span data-ttu-id="50f0c-120">Das [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) -Element, das definiert, was in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="50f0c-120">The [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) element that defines what is displayed in a row of the list view.</span></span>

- <span data-ttu-id="50f0c-121">Das [propertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) -Element, das definiert, welche Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="50f0c-121">The [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element that defines which property is displayed.</span></span>

## <a name="example"></a><span data-ttu-id="50f0c-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50f0c-122">Example</span></span>

<span data-ttu-id="50f0c-123">Der folgende XML-Code definiert eine Listenansicht, die eine neue Gruppe startet, wenn der Wert der [System. ServiceProcess. ServiceController. Status](/dotnet/api/System.ServiceProcess.ServiceController.Status) -Eigenschaft geändert wird.</span><span class="sxs-lookup"><span data-stu-id="50f0c-123">The following XML defines a list view that starts a new group whenever the value of the [System.Serviceprocess.Servicecontroller.Status](/dotnet/api/System.ServiceProcess.ServiceController.Status) property changes.</span></span> <span data-ttu-id="50f0c-124">Wenn jede Gruppe gestartet wird, wird eine benutzerdefinierte Bezeichnung angezeigt, die den neuen Wert der Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="50f0c-124">When each group is started, a custom label is displayed that includes the new value of the property.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.ServiceProcess.ServiceController</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>Status</PropertyName>
        <Label>New Service Status</Label>
      </GroupBy>
      <ListControl>
        <ListEntries>
          <ListEntry>
            <ListItems>
              <ListItem>
                <PropertyName>Name</PropertyName>
              </ListItem>
              <ListItem>
                <PropertyName>DisplayName</PropertyName>
              </ListItem>
              <ListItem>
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

<span data-ttu-id="50f0c-125">Das folgende Beispiel zeigt, wie Windows PowerShell [System. ServiceProcess. ServiceController anzeigt? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekte, nachdem diese Format Datei geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="50f0c-125">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span> <span data-ttu-id="50f0c-126">Die leeren Zeilen, die vor und nach der Gruppen Bezeichnung hinzugefügt werden, werden automatisch von Windows PowerShell hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="50f0c-126">The blank lines added before and after the group label are automatically added by Windows PowerShell.</span></span>

```powershell
Get-Service f*
```

```output
   New Service Status: Stopped

Name        : Fax
DisplayName : Fax
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
ServiceType : Win32OwnProcess

   New Service Status: Stopped

Name        : fdPHost
DisplayName : Function Discovery Provider Host
ServiceType : Win32ShareProcess

   New Service Status: Running

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
ServiceType : Win32ShareProcess

   New Service Status: Stopped

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
ServiceType : Win32OwnProcess

   New Service Status: Running

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a><span data-ttu-id="50f0c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50f0c-127">See Also</span></span>

[<span data-ttu-id="50f0c-128">Beispiele für Formatierungsdateien</span><span class="sxs-lookup"><span data-stu-id="50f0c-128">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="50f0c-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="50f0c-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
