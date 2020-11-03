---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: 6e8903d6ee1b9bb38c42abd866a1657e86d2f3ac
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200807"
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
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

## AUSGABEN

### System.Guid
Dieses Cmdlet gibt eine GUID zurück.

## HINWEISE

## VERWANDTE LINKS
