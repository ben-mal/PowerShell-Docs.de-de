---
ms.date: 07/16/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressource „WindowsProcess“
ms.openlocfilehash: a1f8840a5894049efd27c5d213a66363cd8dbebc
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464127"
---
# <a name="dsc-windowsprocess-resource"></a>DSC-Ressource „WindowsProcess“

> Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x

Die Ressource **WindowsProcess** in Windows PowerShell DSC bietet einen Mechanismus zum Konfigurieren von Prozessen auf einem Zielknoten.

## <a name="syntax"></a>Syntax

```Syntax
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|Argumente |Gibt eine Zeichenfolge von Argumenten an, die wie vorhanden an den Prozess übergeben wird. Wenn Sie mehrere Argumente übergeben müssen, fügen Sie sie alle dieser Zeichenfolge hinzu. |
|`Path` |Der Pfad zur ausführbaren Prozessdatei. Wenn es sich um den Namen der ausführbaren Datei (keinen vollqualifizierten Pfad) handelt, durchsucht die Ressource „DSC“ die Umgebungsvariable `$env:Path`, um die ausführbare Datei zu ermitteln. Wenn der Werte dieser Eigenschaft ein vollqualifizierter Pfad ist, verwendet DSC nicht die Umgebungsvariable `$env:Path`, um die Dateien zu finden, und löst einen Fehler aus, wenn der Pfad nicht vorhanden ist. Relative Pfade sind nicht zulässig. |
|Anmeldeinformationen |Gibt die Anmeldeinformationen zum Starten des Prozesses an. |
|StandardErrorPath |Gibt den Verzeichnispfad an, in den der Standardfehler geschrieben wird. Eine vorhandene Datei wird überschrieben. |
|StandardInputPath |Gibt den Standardpfad für die Eingabe an. |
|StandardOutputPath |Gibt den Speicherort an, in den die Standardausgabe geschrieben wird. Eine vorhandene Datei wird überschrieben. |
|WorkingDirectory |Gibt den Speicherort an, der als das aktuelle Arbeitsverzeichnis für den Prozess verwendet wird. |

## <a name="common-properties"></a>Allgemeine Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|DependsOn |Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird. Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Gibt an, ob der Prozess vorhanden ist. Legen Sie diese Eigenschaft auf **Present** fest, um sicherzustellen, dass der Prozess vorhanden ist. Legen Sie sie andernfalls auf **Absent** fest. Der Standardwert ist **Present**. |
|PsDscRunAsCredential |Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest. |
