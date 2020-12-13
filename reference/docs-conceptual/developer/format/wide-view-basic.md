---
ms.date: 09/13/2016
ms.topic: reference
title: Breite Ansicht (Basic)
description: Breite Ansicht (Basic)
ms.openlocfilehash: bfc647da9b78fcd22aac83cf330e466b6759471c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667690"
---
# <a name="wide-view-basic"></a><span data-ttu-id="ee648-103">Breite Ansicht (Basic)</span><span class="sxs-lookup"><span data-stu-id="ee648-103">Wide View (Basic)</span></span>

<span data-ttu-id="ee648-104">In diesem Beispiel wird gezeigt, wie eine grundlegende weite Ansicht implementiert wird, in der [System. ServiceProcess. ServiceController angezeigt wird? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekte, die vom `Get-Service` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ee648-104">This example shows how to implement a basic wide view that displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="ee648-105">Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="ee648-105">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

### <a name="to-load-this-formatting-file"></a><span data-ttu-id="ee648-106">So laden Sie diese Formatierungs Datei</span><span class="sxs-lookup"><span data-stu-id="ee648-106">To load this formatting file</span></span>

1. <span data-ttu-id="ee648-107">Kopieren Sie den XML-Code aus dem Beispiel Abschnitt dieses Themas in eine Textdatei.</span><span class="sxs-lookup"><span data-stu-id="ee648-107">Copy the XML from the Example section of this topic into a text file.</span></span>

2. <span data-ttu-id="ee648-108">Speichern Sie die Textdatei.</span><span class="sxs-lookup"><span data-stu-id="ee648-108">Save the text file.</span></span> <span data-ttu-id="ee648-109">Stellen Sie sicher, dass `format.ps1xml` Sie die Erweiterung der Datei hinzufügen, um Sie als Formatierungs Datei zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ee648-109">Be sure to add the `format.ps1xml` extension to the file to identify it as a formatting file.</span></span>

3. <span data-ttu-id="ee648-110">Öffnen Sie Windows PowerShell, und führen Sie den folgenden Befehl aus, um die Formatierungs Datei in die aktuelle Sitzung zu laden: `Update-formatdata -prependpath PathToFormattingFile` .</span><span class="sxs-lookup"><span data-stu-id="ee648-110">Open Windows PowerShell, and run the following command to load the formatting file into the current session: `Update-formatdata -prependpath PathToFormattingFile`.</span></span>

   > [!WARNING]
   > <span data-ttu-id="ee648-111">Mit dieser Formatierungs Datei wird die Anzeige eines Objekts definiert, das bereits durch eine Windows PowerShell-Formatierungs Datei definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ee648-111">This formatting file defines the display of an object that is already defined by a Windows PowerShell formatting file.</span></span> <span data-ttu-id="ee648-112">Sie müssen den `prependPath` -Parameter verwenden, wenn Sie das-Cmdlet ausführen, und Sie können diese Formatierungs Datei nicht als Modul laden.</span><span class="sxs-lookup"><span data-stu-id="ee648-112">You must use the `prependPath` parameter when you run the cmdlet, and you cannot load this formatting file as a module.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ee648-113">Zeigt</span><span class="sxs-lookup"><span data-stu-id="ee648-113">Demonstrates</span></span>

<span data-ttu-id="ee648-114">Diese Formatierungs Datei veranschaulicht die folgenden XML-Elemente:</span><span class="sxs-lookup"><span data-stu-id="ee648-114">This formatting file demonstrates the following XML elements:</span></span>

- <span data-ttu-id="ee648-115">Das [Name](./name-element-for-view-format.md) -Element für die Sicht.</span><span class="sxs-lookup"><span data-stu-id="ee648-115">The [Name](./name-element-for-view-format.md) element for the view.</span></span>

- <span data-ttu-id="ee648-116">Das [viewselectedby](./viewselectedby-element-format.md) -Element, das definiert, welche Objekte von der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ee648-116">The [ViewSelectedBy](./viewselectedby-element-format.md) element that defines what objects are displayed by the view.</span></span>

- <span data-ttu-id="ee648-117">Das [wideitem](./wideitem-element-for-widecontrol-format.md) -Element, das definiert, welche Eigenschaft von der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ee648-117">The [WideItem](./wideitem-element-for-widecontrol-format.md) element that defines what property is displayed by the view.</span></span>

## <a name="example"></a><span data-ttu-id="ee648-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ee648-118">Example</span></span>

<span data-ttu-id="ee648-119">Der folgende XML-Code definiert eine breite Ansicht, in der der Wert der [System. ServiceProcess. ServiceController. ServiceName](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) -Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ee648-119">The following XML defines a wide view that displays the value of the [System.Serviceprocess.Servicecontroller.Servicename](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName) property.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <WideControl>
        <WideEntries>
          <WideEntry>
            <WideItem>
              <PropertyName>ServiceName</PropertyName>
            </WideItem>
          </WideEntry>
        </WideEntries>
      </WideControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="ee648-120">Das folgende Beispiel zeigt, wie Windows PowerShell [System. ServiceProcess. ServiceController anzeigt? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekte, nachdem diese Format Datei geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ee648-120">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) objects after this format file is loaded.</span></span>

```powershell
Get-Service f*
```

```output
Fax                      FCSAM
fdPHost                  FDResPub
FontCache                FontCache3.0.0.0
FSysAgent                FwcAgent
```

## <a name="see-also"></a><span data-ttu-id="ee648-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee648-121">See Also</span></span>

[<span data-ttu-id="ee648-122">Beispiele für Formatierungsdateien</span><span class="sxs-lookup"><span data-stu-id="ee648-122">Examples of Formatting Files</span></span>](./examples-of-formatting-files.md)

[<span data-ttu-id="ee648-123">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="ee648-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
