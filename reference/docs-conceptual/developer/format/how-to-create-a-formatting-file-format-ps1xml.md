---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen einer Formatierungsdatei (.format.ps1xml)
description: Erstellen einer Formatierungsdatei (.format.ps1xml)
ms.openlocfilehash: 5bbc1ba40bfccf13636abc0f0751938aa724b761
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652003"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a>Erstellen einer Formatierungsdatei (.format.ps1xml)

In diesem Thema wird beschrieben, wie eine Formatierungs Datei (.format.ps1XML) erstellt wird.

> [!NOTE]
> Sie können auch eine Formatierungs Datei erstellen, indem Sie eine Kopie einer der von Windows PowerShell bereitgestellten Dateien erstellen. Wenn Sie eine Kopie einer vorhandenen Datei erstellen, löschen Sie die vorhandene digitale Signatur, und fügen Sie der neuen Datei Ihre eigene Signatur hinzu.

### <a name="to-create-a-formatps1xml-file"></a>Zum Erstellen einer .format.ps1-XML-Datei.

1. Erstellen Sie eine Textdatei (. txt) mit einem Text-Editor, z. b. Notepad.

2. Kopieren Sie die folgenden Zeilen in die Formatierungs Datei.

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - Die `<Configuration></Configuration>` Tags definieren den Stamm `Configuration` Knoten. Alle zusätzlichen XML-Tags werden in diesen Knoten eingeschlossen.

   - Die `<ViewDefinitions></ViewDefinitions>` Tags definieren den `ViewDefinitions` Knoten. Alle Sichten werden innerhalb dieses Knotens definiert.

3. Speichern Sie die Datei im Installationsordner von Windows PowerShell, in Ihrem Modul Ordner oder in einem Unterordner des Modul Ordners. Verwenden Sie das folgende Namensformat, wenn Sie die Datei speichern:  `MyFile.format.ps1xml` . Beim Formatieren von Dateien muss die Erweiterung verwendet werden `.format.ps1xml` .

   Nun können Sie der Formatierungs Datei Ansichten hinzufügen. Es gibt keine Beschränkung für die Anzahl der Sichten, die in einer Formatierungs Datei definiert werden können. Sie können eine einzelne Ansicht für jedes Objekt, mehrere Ansichten für dasselbe Objekt oder eine einzelne Ansicht hinzufügen, die von mehreren Objekten verwendet wird.

## <a name="see-also"></a>Weitere Informationen

[Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei](./writing-a-powershell-formatting-file.md)
