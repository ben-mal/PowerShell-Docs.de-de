---
title: Vorgehensweise beim Erstellen einer Formatierungs Datei (.format.ps1XML) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: abdbd4e15b0c4cb1dafcde087d24ed5792c86c3d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781255"
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

3. Speichern Sie die Datei im Installationsordner von Windows PowerShell, in Ihrem Modul Ordner oder in einem Unterordner des Modul Ordners. Verwenden Sie das folgende Namensformat, wenn Sie die Datei speichern: `MyFile.format.ps1xml` . Beim Formatieren von Dateien muss die Erweiterung verwendet werden `.format.ps1xml` .

   Nun können Sie der Formatierungs Datei Ansichten hinzufügen. Es gibt keine Beschränkung für die Anzahl der Sichten, die in einer Formatierungs Datei definiert werden können. Sie können eine einzelne Ansicht für jedes Objekt, mehrere Ansichten für dasselbe Objekt oder eine einzelne Ansicht hinzufügen, die von mehreren Objekten verwendet wird.

## <a name="see-also"></a>Weitere Informationen

[Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei](./writing-a-powershell-formatting-file.md)
