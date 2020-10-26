---
ms.date: 08/03/2020
keywords: powershell,cmdlet
title: Anhang 1 – Kompatibilitätsaliase
description: PowerShell verfügt über mehrere Aliase, die UNIX- und cmd.exe-Benutzern ermöglichen, vertraute Befehle zu verwenden.
ms.openlocfilehash: 8cbbd5a358de9018fcb5c840e711cd76f7a9a353
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500741"
---
# <a name="appendix-1---compatibility-aliases"></a>Anhang 1: Kompatibilitätsaliase

PowerShell verfügt über mehrere Aliase, die **UNIX** - und **cmd.exe** -Benutzern ermöglichen, vertraute Befehle zu verwenden.
Die Befehle, das zugehörige PowerShell-Cmdlet und der PowerShell-Alias sind in der folgenden Tabelle aufgeführt:

|            Befehl „cmd. exe“            | UNIX-Befehl | PowerShell-Cmdlet | PowerShell-Alias |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| **cd** , **chdir**                     | **cd**       | `Set-Location`    | `sl`             |
| **cls**                               | **Löschen**    | `Clear-Host`      | `cls`            |
| **copy**                              | **cp**       | `Copy-Item`       | `cpi`            |
| **del** , **erase** , **rd** , **rmdir** | **rm**       | `Remove-Item`     | `ri`             |
| **dir**                               | **ls**       | `Get-ChildItem`   | `gci`            |
| **echo**                              | **echo**     | `Write-Output`    | `write`          |
| **md**                                | **mkdir**    | `New-Item`        | `ni`             |
| **move**                              | **mv**       | `Move-Item`       | `mi`             |
| **popd**                              | **popd**     | `Pop-Location`    | `popd`           |
| **pushd**                             | **pushd**    | `Push-Location`   | `pushd`          |
| **ren**                               | **mv**       | `Rename-Item`     | `rni`            |
| **type**                              | **cat**      | `Get-Content`     | `gc`             |

Verwenden Sie das [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias)-Cmdlet, um die PowerShell-Aliase zu ermitteln. Um die Aliase eines Cmdlets anzuzeigen, verwenden Sie den **Definition** -Parameter, und geben Sie den Namen des Cmdlets an.
Verwenden Sie alternativ den **Name** -Parameter, um den Cmdlet-Namen eines Alias zu suchen.

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
