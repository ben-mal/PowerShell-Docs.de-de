---
ms.date: 09/13/2016
ms.topic: reference
title: Attributtypen
description: Attributtypen
ms.openlocfilehash: 65640f2f8449887dedb9fae137eb16b6252f1d57
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667112"
---
# <a name="attribute-types"></a>Attributtypen

Cmdlet-Attribute können nach Funktionalität gruppiert werden.
In den folgenden Abschnitten werden die verfügbaren Attribute beschrieben, und es wird beschrieben, was die Laufzeit bewirkt, wenn das Attribut aufgerufen wird.

## <a name="cmdlet-attributes"></a>Cmdlet-Attribute

### <a name="cmdlet"></a>Cmdlet

Identifiziert eine .NET Framework Klasse als Cmdlet.
Dies ist das erforderliche Basis Attribut.
Weitere Informationen finden Sie unter [Cmdlet-Attribut Deklaration](./cmdlet-attribute-declaration.md).

## <a name="parameter-attributes"></a>Parameterattribute

### <a name="parameter"></a>Parameter

Identifiziert eine öffentliche Eigenschaft in der Cmdlet-Klasse als Cmdlet-Parameter.
Weitere Informationen finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).

### <a name="alias"></a>Alias

Gibt mindestens einen Alias für einen Parameter an.
Weitere Informationen finden Sie unter [Alias Attribut Deklaration](./alias-attribute-declaration.md).

## <a name="argument-validation-attributes"></a>Argument Validierungs Attribute

### <a name="validatecount"></a>Validatecount

Gibt die minimale und maximale Anzahl von Argumenten an, die für einen Cmdlet-Parameter zulässig sind.
Weitere Informationen finden Sie unter [validatecount-Attribut Deklaration](./validatecount-attribute-declaration.md).

### <a name="validatelength"></a>ValidateLength

Gibt eine minimale und maximale Anzahl von Zeichen für ein Cmdlet-Parameter Argument an.
Weitere Informationen finden Sie unter [validateLength-Attribut Deklaration](./validatelength-attribute-declaration.md).

### <a name="validatepattern"></a>ValidatePattern

Gibt ein Muster für einen regulären Ausdruck an, dem das Cmdlet-Parameter Argument entsprechen muss.
Weitere Informationen finden Sie unter [validatepattern-Attribut Deklaration](./validatepattern-attribute-declaration.md).

### <a name="validaterange"></a>Validaterange

Gibt die minimalen und maximalen Werte für ein Cmdlet-Parameter Argument an.
Weitere Informationen finden Sie unter [validaterange-Attribut Deklaration](./validaterange-attribute-declaration.md).

### <a name="validateset"></a>ValidateSet

Gibt einen Satz gültiger Werte für das Cmdlet-Parameter Argument an.
Weitere Informationen finden Sie unter [validateset-Attribut Deklaration](./validateset-attribute-declaration.md).

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell SDK](../windows-powershell-reference.md)
