---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: df7f9000cf66cebce83e3146cd5c95a7d1a78bf8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603137"
---
# New-Guid

## ZUSAMMENFASSUNG
Erstellt eine GUID.

## SYNTAX

```
New-Guid [<CommonParameters>]
```

## DESCRIPTION

Das **New-GUID-** Cmdlet erstellt eine zufällige Globally Unique Identifier (GUID).
Wenn Sie in einem Skript eine eindeutige ID benötigen, können Sie nach Bedarf eine GUID erstellen.

## BEISPIELE

### Beispiel 1: Erstellen einer GUID

```
PS C:\> New-Guid
Guid
----
0352cf0f-2e7a-4aee-801d-7f27f8344c77
```

Mit diesem Befehl wird eine zufällige GUID erstellt.
Alternativ können Sie die Ausgabe dieses Cmdlets in einer Variablen speichern, die an anderer Stelle in einem Skript verwendet werden soll.

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

### System.Guid

Dieses Cmdlet gibt eine GUID zurück.

## HINWEISE

## VERWANDTE LINKS

