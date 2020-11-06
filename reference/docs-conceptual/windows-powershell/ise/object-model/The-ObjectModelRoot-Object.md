---
ms.date: 08/25/2017
title: Das ObjectModelRoot-Objekt
description: Das $psISE-Objekt, das Prinzipalstammobjekt in PowerShell ISE, ist eine Instanz der Microsoft.PowerShell.Host.ISE.ObjectModelRoot-Klasse. Dieses Thema beschreibt die Eigenschaften des ObjectModelRoot-Objekts.
ms.openlocfilehash: c8ae703c2663256ca037090fd3b1eb239cfc431a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660951"
---
# <a name="the-objectmodelroot-object"></a>Das ObjectModelRoot-Objekt

Das `$psISE`-Objekt ist das Prinzipalstammobjekt in Windows PowerShell&reg; Integrated Scripting Environment (ISE) und eine Instanz der Microsoft.PowerShell.Host.ISE.ObjectModelRoot-Klasse. Dieses Thema beschreibt die Eigenschaften des **ObjectModelRoot** -Objekts.

## <a name="properties"></a>Eigenschaften

### <a name="currentfile"></a>CurrentFile

> In Windows PowerShell ISE 2.0 und höher unterstützt.

Die schreibgeschützte Eigenschaft, die die diesem Hostobjekt, das gegenwärtig den Fokus besitzt, zugeordnete Datei abruft.

### <a name="currentpowershelltab"></a>CurrentPowerShellTab

> In Windows PowerShell ISE 2.0 und höher unterstützt.

Die schreibgeschützte Eigenschaft, die die PowerShell-Registerkarte abruft, die zurzeit den Fokus besitzt.

### <a name="currentvisiblehorizontaltool"></a>CurrentVisibleHorizontalTool

> In Windows PowerShell ISE 2.0 und höher unterstützt.

Die schreibgeschützte Eigenschaft, die das derzeit sichtbare Windows PowerShell ISE-Add-On-Tool abruft, das sich im horizontalen Toolbereich unten im Editor befindet.

### <a name="currentvisibleverticaltool"></a>CurrentVisibleVerticalTool

> In Windows PowerShell ISE 2.0 und höher unterstützt.

Die schreibgeschützte Eigenschaft, die das derzeit sichtbare Windows PowerShell ISE-Add-On-Tool abruft, das sich im vertikalen Toolbereich rechts im Editor befindet.

### <a name="options"></a>Optionen

> In Windows PowerShell ISE 2.0 und höher unterstützt.

Die schreibgeschützte Eigenschaft, mit der die verschiedenen Optionen zum Ändern von Eigenschaften in Windows PowerShell ISE abgerufen werden.

### <a name="powershelltabs"></a>PowerShellTabs

> In Windows PowerShell ISE 2.0 und höher unterstützt.

Die schreibgeschützte Eigenschaft, die die Sammlung von in Windows PowerShell ISE geöffneten PowerShell-Registerkarten abruft. Standardmäßig enthält dieses Objekt eine PowerShell-Registerkarte. Allerdings können Sie mit Skripts oder Menüs in Windows PowerShell ISE weitere PowerShell-Registerkarten zu diesem Objekt hinzufügen.

## <a name="see-also"></a>Weitere Informationen

- [Zweck des Windows PowerShell ISE-Skriptobjektmodells](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Die ISE-Objektmodellhierarchie](The-ISE-Object-Model-Hierarchy.md)
