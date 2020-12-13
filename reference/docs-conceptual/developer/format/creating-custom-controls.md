---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen von benutzerdefinierten Steuerelementen
description: Erstellen von benutzerdefinierten Steuerelementen
ms.openlocfilehash: 78d8cc2970b2b3e493bef25d78404ba1be195bb1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668047"
---
# <a name="creating-custom-controls"></a><span data-ttu-id="294df-103">Erstellen von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="294df-103">Creating Custom Controls</span></span>

<span data-ttu-id="294df-104">Benutzerdefinierte Steuerelemente sind die flexibelsten Komponenten einer Formatierungs Datei.</span><span class="sxs-lookup"><span data-stu-id="294df-104">Custom controls are the most flexible components of a formatting file.</span></span> <span data-ttu-id="294df-105">Im Gegensatz zu Tabellen-, Listen-und breiten Ansichten, die eine formale Struktur von Daten definieren, z. b. eine Tabelle mit Daten, können Sie mit benutzerdefinierten Steuerelementen definieren, wie ein einzelnes Datenelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="294df-105">Unlike table, list, and wide views that define a formal structure of data, such as a table of data, custom controls allow you to define how an individual piece of data is displayed.</span></span> <span data-ttu-id="294df-106">Sie können einen allgemeinen Satz benutzerdefinierter Steuerelemente definieren, die für alle Sichten der Formatierungs Datei verfügbar sind. Sie können benutzerdefinierte Steuerelemente definieren, die für eine bestimmte Ansicht verfügbar sind, oder Sie können einen Satz von Steuerelementen definieren, die für eine Gruppe von Objekten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="294df-106">You can define a common set of custom controls that are available to all the views of the formatting file, you can define custom controls that are available to a specific view, or you can define a set of controls that are available to a group of objects.</span></span>

## <a name="custom-control-example"></a><span data-ttu-id="294df-107">Beispiel für einen benutzerdefinierten</span><span class="sxs-lookup"><span data-stu-id="294df-107">Custom Control Example</span></span>

<span data-ttu-id="294df-108">Im folgenden Beispiel wird ein benutzerdefiniertes Steuerelement gezeigt, das in der Certificates.Format.ps1-XML-Datei definiert ist.</span><span class="sxs-lookup"><span data-stu-id="294df-108">The following example shows a custom control that is defined in the Certificates.Format.ps1xml file.</span></span> <span data-ttu-id="294df-109">Dieses benutzerdefinierte Steuerelement wird zum Trennen der [System. Management. Automation. Signature](/dotnet/api/System.Management.Automation.Signature) -Objekte verwendet, die in einer Tabellenansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="294df-109">This custom control is used to separate the [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature) objects displayed in a table view.</span></span>

```xml
<Controls>
  <Control>
    <Name>SignatureTypes-GroupingFormat</Name>
    <CustomControl>
      <CustomEntries>
        <CustomEntry>
          <CustomItem>
            <Frame>
              <LeftIndent>4</LeftIndent>
              <CustomItem>
                <Text AssemblyName="System.Management.Automation" BaseName="FileSystemProviderStrings"
                  ResourceId="DirectoryDisplayGrouping"/>
                <ExpressionBinding>
                  <ScriptBlock>split-path $_.Path</ScriptBlock>
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

```

## <a name="see-also"></a><span data-ttu-id="294df-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="294df-110">See Also</span></span>

[<span data-ttu-id="294df-111">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="294df-111">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
