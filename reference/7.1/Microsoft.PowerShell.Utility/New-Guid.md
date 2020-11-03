---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: 2a289500020f069231023fbabaa5401ee0759697
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209291"
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

