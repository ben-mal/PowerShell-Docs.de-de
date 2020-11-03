---
description: Beschreibt die Namen Formate für vollständige und relative Pfadnamen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_path_syntax?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Path_Syntax
ms.openlocfilehash: b58fdd62803bfb654c9c69acda390d63341aacd9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223108"
---
# <a name="about-path-syntax"></a>Informationen zur Pfad Syntax

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt die Namen Formate für vollständige und relative Pfadnamen in PowerShell.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Alle Elemente in einem Datenspeicher, auf die über einen PowerShell-Anbieter zugegriffen werden kann, können durch ihre Pfadnamen eindeutig identifiziert werden. Ein Pfadname ist eine Kombination aus Elementname, Container und unter Containern, in der sich das Element befindet, und dem PowerShell-Laufwerk, auf das die Container zugreifen.

In PowerShell sind Pfadnamen in einen von zwei Typen unterteilt: voll qualifiziert und relativ. Ein voll qualifizierter Pfadname besteht aus allen Elementen, die einen Pfad bilden. Die folgende Syntax zeigt die Elemente in einem voll qualifizierten Pfadnamen:

```powershell
[<provider>::]<drive>:[\<container>[\<subcontainer>...]]\<item>
```

Der \<provider\> Platzhalter bezieht sich auf den PowerShell-Anbieter, über den Sie auf den Datenspeicher zugreifen. Beispielsweise können Sie mit dem File System-Anbieter auf die Dateien und Verzeichnisse auf dem Computer zugreifen. Dieses Element der Syntax ist optional und wird nie benötigt, da die Laufwerks Namen in allen Anbietern eindeutig sind.

Der \<drive\> Platzhalter bezieht sich auf das PowerShell-Laufwerk, das von einem bestimmten PowerShell-Anbieter unterstützt wird. Im Fall des File System-Anbieters werden die PowerShell-Laufwerke den Windows-Laufwerken zugeordnet, die auf Ihrem System konfiguriert sind. Wenn Ihr System beispielsweise ein Laufwerk A: und Laufwerk C: enthält, erstellt der File System-Anbieter die gleichen Laufwerke in PowerShell.

Nachdem Sie das Laufwerk angegeben haben, müssen Sie alle Container und unter Container angeben, in denen das Element enthalten ist. Die Container müssen in der hierarchischen Reihenfolge angegeben werden, in der Sie im Datenspeicher vorhanden sind. Anders ausgedrückt: Sie müssen mit dem übergeordneten Container, dem untergeordneten Container in diesem übergeordneten Container usw. beginnen. Außerdem muss jedem Container ein umgekehrter Schrägstrich vorangestellt werden. (Beachten Sie, dass Sie mithilfe von PowerShell Schrägstriche für die Kompatibilität mit anderen powershells verwenden können.)

Nachdem der Container und die Subcontainer angegeben wurden, müssen Sie den Elementnamen angeben, dem ein umgekehrter Schrägstrich vorangestellt ist. Der voll qualifizierte Pfadname für die Shell.dll-Datei im Verzeichnis "C: \\ Windows System32" lautet beispielsweise \\ wie folgt:

```powershell
C:\Windows\System32\Shell.dll
```

In diesem Fall ist das Laufwerk, über das auf die Container zugegriffen wird, Laufwerk C:, der Container der obersten Ebene ist Windows, der unter Container ist System32 (befindet sich im Windows-Container), und das Element wird Shell.dll.

In einigen Situationen müssen Sie keinen voll qualifizierten Pfadnamen angeben und können stattdessen einen relativen Pfadnamen verwenden. Ein relativer Pfadname basiert auf dem aktuellen Arbeits Speicherort. Mit PowerShell können Sie ein Element auf der Grundlage seiner Position relativ zum aktuellen Arbeits Speicherort identifizieren. Sie können mit Sonderzeichen relative Pfadnamen angeben. In der folgenden Tabelle werden die einzelnen Zeichen beschrieben und Beispiele für relative Pfadnamen und voll qualifizierte Pfadnamen bereitstellt. Die Beispiele in der Tabelle basieren auf dem aktuellen Arbeitsverzeichnis, das auf "c:\Windows" festgelegt ist.

|Symbol|BESCHREIBUNG               |Relativer Pfad    |Vollständiger Pfad          |
|------|--------------------------|-----------------|-------------------|
|.     |Aktueller Speicherort          |.\\ Anlage        |c: \\ Windows- \\ System|
|..    |Übergeordnetes Element des aktuellen Speicher Orts|..\\ Programmdateien|c: \\ Programmdateien  |
|\     |Laufwerks Stamm der aktuellen     |\\Programmdateien  |c: \\ Programmdateien  |
|      |location                  |                 |                   |
|gar|Keine Sonderzeichen     |System           |c: \\ Windows- \\ System|

Wenn Sie einen Pfadnamen in einem Befehl verwenden, geben Sie diesen Namen auf die gleiche Weise ein, unabhängig davon, ob Sie einen voll qualifizierten Pfadnamen oder einen relativen Pfadnamen verwenden. Nehmen Sie beispielsweise an, dass das aktuelle Arbeitsverzeichnis c:\Windows. Mit dem folgenden Get-ChildItem Befehl werden alle Elemente im Verzeichnis "c:\techdocs" abgerufen:

```powershell
Get-ChildItem \techdocs
```

Der umgekehrte Schrägstrich gibt an, dass der Laufwerks Stamm des aktuellen Arbeitsspeicher Orts verwendet werden soll. Da das Arbeitsverzeichnis "c: \\ Windows" ist, ist der Laufwerks Stamm das Laufwerk "c:". Da sich das techdocs-Verzeichnis außerhalb des Stamms befindet, müssen Sie nur den umgekehrten Schrägstrich angeben.

Sie können dieselben Ergebnisse erzielen, indem Sie den folgenden Befehl verwenden:

```powershell
Get-ChildItem c:\techdocs
```

Unabhängig davon, ob Sie einen voll qualifizierten Pfadnamen oder einen relativen Pfadnamen verwenden, ist ein Pfadname nicht nur wichtig, da er ein Element sucht, sondern auch, weil das Element eindeutig identifiziert wird, auch wenn dieses Element denselben Namen wie ein anderes Element in einem anderen Container hat.

Nehmen Sie beispielsweise an, dass Sie über zwei Dateien mit dem Namen Results.txt verfügen.
Die erste Datei befindet sich in einem Verzeichnis mit dem Namen "c: \\ techdocs \\ Jan", und die zweite Datei befindet sich in einem Verzeichnis mit dem Namen "c: \\ techdocs \\ Feb". Der Pfadname für die erste Datei (c: \\ techdocs \\ Jan \\Results.txt) und der Pfadname für die zweite Datei (c: \\ techdocs \\ Feb \\Results.txt) ermöglichen es Ihnen, die beiden Dateien eindeutig zu unterscheiden.

## <a name="see-also"></a>SIEHE AUCH

[about_Locations](about_Locations.md)
