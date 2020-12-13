---
ms.date: 09/12/2016
ms.topic: reference
title: Festlegen von XML-Versionsnummern für HelpInfo
description: Festlegen von XML-Versionsnummern für HelpInfo
ms.openlocfilehash: 9ef1940ca05d8aa9b04770013287490b71c8065a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658835"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a>Festlegen von XML-Versionsnummern für HelpInfo

In diesem Thema wird erläutert, wie die Versionsnummern in einer aktualisierbaren Hilfe Informationsdatei festgelegt und erhöht werden, die häufig als "helpinfo-XML-Datei" bezeichnet wird.

## <a name="how-to-set-helpinfo-xml-version-numbers"></a>Festlegen von XML-Versionsnummern für HelpInfo

Die Versionsnummern in einer helpinfo-XML-Datei sind wichtig für den Vorgang der aktualisierbaren Hilfe. Mit den Cmdlets " [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) " und " [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) " werden neue Hilfedateien nur heruntergeladen, wenn die Versionsnummer für eine Benutzeroberflächen Kultur in der XML-Datei "Remote helpinfo" größer ist als die Versionsnummer für diese Benutzeroberflächen Kultur in der lokalen helpinfo-XML-Datei, oder es gibt keine lokale helpinfo

Die helpinfo-XML-Datei verwendet die 4-teilige Versionsnummer, die in der **System. Version** -Klasse des Microsoft .NET Frameworks definiert ist. Das Format ist `N1.N2.N3.N4`. Modul Autoren können ein beliebiges Versionsnummern Schema verwenden, das von der **System. Version** -Klasse zugelassen wird. Die aktualisierbare Hilfe erfordert nur, dass die Versionsnummer für eine Benutzeroberflächen Kultur zunimmt, wenn eine neue Version der CAB-Datei für die Benutzeroberflächen Kultur an den Speicherort hochgeladen wird, der durch das **helpcontenturi** -Element in der helpinfo-XML-Datei angegeben wird.

Das folgende Beispiel zeigt die Elemente der helpinfo-XML-Datei für die deutsche Benutzeroberflächen Kultur (de-de), wenn die Version 2.15.0.10 ist.

```xml
<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

Die Versionsnummer für eine Benutzeroberflächen Kultur spiegelt die Version der CAB-Datei für die Benutzeroberflächen Kultur wider. Die Versionsnummer gilt für die gesamte CAB-Datei. In der CAB-Datei können keine anderen Versionsnummern für verschiedene Dateien festgelegt werden. Die Versionsnummer für jede Benutzeroberflächen Kultur wird unabhängig ausgewertet und muss nicht mit den Versionsnummern für andere Benutzeroberflächen Kulturen verknüpft sein, die das Modul unterstützt.
