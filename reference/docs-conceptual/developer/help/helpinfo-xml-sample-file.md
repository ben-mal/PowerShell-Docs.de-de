---
ms.date: 09/12/2016
ms.topic: reference
title: XML-Beispieldatei HelpInfo
description: XML-Beispieldatei HelpInfo
ms.openlocfilehash: 321793d61ab5df3cccc7c353b6c93f5a7275b533
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647770"
---
# <a name="helpinfo-xml-sample-file"></a><span data-ttu-id="b78f6-103">XML-Beispieldatei HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b78f6-103">HelpInfo XML Sample File</span></span>

<span data-ttu-id="b78f6-104">In diesem Thema wird ein Beispiel für eine wohlgeformte aktualisierbare Hilfe Informationsdatei angezeigt, die häufig als "helpinfo-XML-Datei" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="b78f6-104">This topic displays a sample of a well-formed Updatable Help Information file, commonly known as "HelpInfo XML file."</span></span> <span data-ttu-id="b78f6-105">In dieser Beispieldatei werden die UI-Kulturelemente in alphabetischer Reihenfolge nach dem Namen der Benutzeroberflächen Kultur angeordnet.</span><span class="sxs-lookup"><span data-stu-id="b78f6-105">In this sample file, the UI culture elements are arranged in alphabetical order by UI culture name.</span></span> <span data-ttu-id="b78f6-106">Die alphabetische Reihenfolge ist eine bewährte Vorgehensweise, aber Sie ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b78f6-106">Alphabetical ordering is a best practice, but it is not required.</span></span>

## <a name="helpinfo-xml-sample-file"></a><span data-ttu-id="b78f6-107">XML-Beispieldatei HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b78f6-107">HelpInfo XML Sample File</span></span>

```xml

<?xml version="1.0" encoding="utf-8"?>
<HelpInfo xmlns="http://schemas.microsoft.com/powershell/help/2010/05">
   <HelpContentURI>https://go.microsoft.com/fwlink/?LinkID=141553</HelpContentURI>
   <SupportedUICultures>
    <UICulture>
      <UICultureName>de-DE</UICultureName>
      <UICultureVersion>2.15.0.10</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>en-US</UICultureName>
      <UICultureVersion>3.2.0.7</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>it-IT</UICultureName>
      <UICultureVersion>1.1.0.5</UICultureVersion>
    </UICulture>
    <UICulture>
      <UICultureName>ja-JP</UICultureName>
      <UICultureVersion>3.2.0.4</UICultureVersion>
    </UICulture>
   </SupportedUICultures>
</HelpInfo>

```
