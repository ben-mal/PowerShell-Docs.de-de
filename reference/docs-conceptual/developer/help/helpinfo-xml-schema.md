---
ms.date: 09/12/2016
ms.topic: reference
title: XML-Schema von HelpInfo
description: XML-Schema von HelpInfo
ms.openlocfilehash: 157fd9c0f47c57efbaa9b7888fa174a34ad9567d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662019"
---
# <a name="helpinfo-xml-schema"></a><span data-ttu-id="ee6fd-103">XML-Schema von HelpInfo</span><span class="sxs-lookup"><span data-stu-id="ee6fd-103">HelpInfo XML Schema</span></span>

<span data-ttu-id="ee6fd-104">Dieses Thema enthält das XML-Schema für aktualisierbare Hilfe Informationsdateien, die häufig als "helpinfo-XML-Dateien" bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-104">This topic contains the XML schema for Updatable Help Information files, commonly known as "HelpInfo XML files."</span></span>

## <a name="helpinfo-xml-schema"></a><span data-ttu-id="ee6fd-105">XML-Schema von HelpInfo</span><span class="sxs-lookup"><span data-stu-id="ee6fd-105">HelpInfo XML Schema</span></span>

<span data-ttu-id="ee6fd-106">Helpinfo-XML-Dateien basieren auf dem folgenden XML-Schema.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-106">HelpInfo XML files are based on the following XML schema.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<schema targetNamespace="http://schemas.microsoft.com/powershell/help/2010/05" xmlns="http://www.w3.org/2001/XMLSchema">
  <element name="HelpInfo">
    <complexType>
      <sequence>
        <element name="HelpContentURI" type="anyURI" minOccurs="1" maxOccurs="1" />
        <element name="SupportedUICultures" minOccurs="1" maxOccurs="1">
          <complexType>
            <sequence>
              <element name="UICulture" minOccurs="1" maxOccurs="unbounded">
                <complexType>
                  <sequence>
                    <element name="UICultureName" type="language" minOccurs="1" maxOccurs="1" />
                    <element name="UICultureVersion" type="string" minOccurs="1" maxOccurs="1" />
                  </sequence>
                </complexType>
              </element>
            </sequence>
          </complexType>
        </element>
      </sequence>
    </complexType>
  </element>
</schema>
```

## <a name="helpinfo-xml-elements"></a><span data-ttu-id="ee6fd-107">Helpinfo-XML-Elemente</span><span class="sxs-lookup"><span data-stu-id="ee6fd-107">HelpInfo XML Elements</span></span>

<span data-ttu-id="ee6fd-108">Die helpinfo-XML-Datei enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="ee6fd-108">The HelpInfo XML file includes the following elements.</span></span>

- <span data-ttu-id="ee6fd-109">**Helpcontenturi** : enthält den URI des Speicher Orts der Hilfe-CAB-Dateien für das Modul.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-109">**HelpContentURI** - Contains the URI of the location of the help CAB files for the module.</span></span> <span data-ttu-id="ee6fd-110">Der URI muss mit "http" oder "https" beginnen.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-110">The URI must begin with "http" or "https".</span></span> <span data-ttu-id="ee6fd-111">Der URI sollte einen Internet Speicherort angeben, darf jedoch nicht den CAB-Dateinamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-111">The URI should specify an internet location, but must not include the CAB filename.</span></span> <span data-ttu-id="ee6fd-112">Der **helpcontenturi** -Wert kann identisch oder vom **helpinfouri** -Wert abweichen.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-112">The **HelpContentURI** value can be the same or different from the **HelpInfoURI** value.</span></span>

- <span data-ttu-id="ee6fd-113">**Supporteduicultures** : stellt die Modul Hilfedateien in allen Benutzeroberflächen Kulturen dar.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-113">**SupportedUICultures** - Represents the module help files in all UI cultures.</span></span> <span data-ttu-id="ee6fd-114">Enthält **UICulture** -Elemente, von denen jede einen Satz von Hilfedateien für das Modul in einer angegebenen Benutzeroberflächen Kultur darstellt.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-114">Contains **UICulture** elements, each of which represents a set of help files for the module in a specified UI culture.</span></span>

- <span data-ttu-id="ee6fd-115">**UICulture** : stellt einen Satz von Hilfedateien für das Modul in einer angegebenen Benutzeroberflächen Kultur dar.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-115">**UICulture** - Represents a set of help files for the module in a specified UI culture.</span></span> <span data-ttu-id="ee6fd-116">Fügen Sie für jede Benutzeroberflächen Kultur, in der die Hilfedateien geschrieben werden, ein **UICulture** -Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-116">Add a **UICulture** element for each UI culture in which the help files are written.</span></span>

- <span data-ttu-id="ee6fd-117">**Uiculturename** : enthält den Sprachcode für die Benutzeroberflächen Kultur, in der die Hilfedateien geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-117">**UICultureName** - Contains the language code for the UI culture in which the help files are written.</span></span>

- <span data-ttu-id="ee6fd-118">**Uicultureversion** : enthält eine 4-teilige Versionsnummer in "N1. N2. N3. N4-Format, das die Version der Hilfe-CAB-Datei in der Benutzeroberflächen Kultur darstellt.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-118">**UICultureVersion** - Contains a 4-part version number in "N1.N2.N3.N4" format that represents the version of the help CAB file in the UI culture.</span></span> <span data-ttu-id="ee6fd-119">Erhöhen Sie diese Versionsnummer immer dann, wenn Sie neue Hilfe-CAB-Dateien in der Benutzeroberflächen Kultur hochladen, die von **uiculturename** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ee6fd-119">Increment this version number whenever you upload new help CAB files in the UI culture that is specified by **UICultureName**.</span></span> <span data-ttu-id="ee6fd-120">Weitere Informationen zu diesem Wert finden Sie unter [Version Class](/dotnet/api/system.version).</span><span class="sxs-lookup"><span data-stu-id="ee6fd-120">For more information about this value, see [Version Class](/dotnet/api/system.version).</span></span>
