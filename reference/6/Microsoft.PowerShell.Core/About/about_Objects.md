---
description: Stellt wichtige Informationen zu Objekten in PowerShell bereit.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: 152234de5e4f55f63b70ee9775bba0c5c9977f84
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221468"
---
# <a name="about-objects"></a>Informationen zu Objekten

## <a name="short-description"></a>Kurze Beschreibung
Stellt wichtige Informationen zu Objekten in PowerShell bereit.

## <a name="long-description"></a>Lange Beschreibung

Jede Aktion, die Sie in PowerShell ausführen, findet innerhalb des Kontexts von Objekten statt. Wenn Daten von einem Befehl zum nächsten verschoben werden, werden Sie als ein oder mehrere identifizierbare Objekte verschoben. Bei einem Objekt handelt es sich um eine Auflistung von Daten, die ein Element darstellt. Ein Objekt besteht aus drei Datentypen: dem Objekttyp, seinen Methoden und seinen Eigenschaften.

## <a name="types-methods-and-properties"></a>Typen, Methoden und Eigenschaften

Der Objekttyp gibt an, welche Art von Objekt es ist. Beispielsweise ist ein Objekt, das eine Datei darstellt, ein FileInfo-Objekt.

Die Objektmethoden sind Aktionen, die Sie für das-Objekt ausführen können.
Beispielsweise verfügen FileInfo-Objekte über eine CopyTo-Methode, die Sie zum Kopieren der Datei verwenden können.

Objekteigenschaften speichern Informationen über das Objekt. Beispielsweise verfügen FileInfo-Objekte über eine LastWrite Time-Eigenschaft, die das Datum und die Uhrzeit speichert, zu der die Datei zuletzt aufgerufen wurde.

Beim Arbeiten mit-Objekten können Sie Ihre Methoden und Eigenschaften in Befehlen verwenden, um Maßnahmen zu ergreifen und Daten zu verwalten.

## <a name="objects-in-pipelines"></a>Objekte in Pipelines

Wenn Befehle in einer Pipeline kombiniert werden, übergeben Sie Informationen als Objekte an einander. Wenn der erste Befehl ausgeführt wird, sendet er ein oder mehrere Objekte in der Pipeline an den zweiten Befehl. Der zweite Befehl empfängt die Objekte vom ersten Befehl, verarbeitet die Objekte und übergibt dann neue oder überarbeitete Objekte an den nächsten Befehl in der Pipeline.
Dies wird fortgesetzt, bis alle Befehle in der Pipeline ausgeführt werden.

Im folgenden Beispiel wird veranschaulicht, wie-Objekte von einem Befehl an den nächsten übermittelt werden:

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

Der erste Befehl `Get-ChildItem C:` gibt ein Datei-oder Verzeichnis Objekt für jedes Element im Stammverzeichnis des Dateisystems zurück. Die Datei-und Verzeichnisobjekte werden über die Pipeline an den zweiten Befehl übermittelt.

Der zweite Befehl `where { $_.PsIsContainer -eq $false }` verwendet die psiscontainer-Eigenschaft aller Dateisystem Objekte, um nur Dateien auszuwählen, deren psiscontainer-Eigenschaft den Wert false ( \$ false) hat. Ordner, bei denen es sich um Container handelt und \$ deren psiscontainer-Eigenschaft den Wert true (true) hat, werden nicht ausgewählt.

Mit dem zweiten Befehl werden nur die Datei Objekte an den dritten Befehl weitergeleitet `Format-List` , der die Datei Objekte in einer Liste anzeigt.

## <a name="see-also"></a>Weitere Informationen

[about_Methods](about_Methods.md)

[about_Object_Creation](about_Object_Creation.md)

[about_Properties](about_Properties.md)

[about_Pipelines](about_Pipelines.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)
