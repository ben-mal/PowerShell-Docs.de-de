---
description: Erläutert die Verwendung des Befehlszeilen Tools PowerShell_Ise.exe.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_ise_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Ise_exe
ms.openlocfilehash: c7500eb6d8586b9dca568edc4e805c577e94bec4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223340"
---
# <a name="about-powershell-iseexe"></a>Informationen zu PowerShell-Ise.exe

## <a name="short-description"></a>KURZE BESCHREIBUNG

Erläutert die Verwendung des Befehlszeilen Tools PowerShell_Ise.exe.

## <a name="long-description"></a>LANGE BESCHREIBUNG

PowerShell_Ise.exe startet eine Windows PowerShell Integrated Scripting Environment Sitzung (ISE). Sie können Sie in Cmd.exe und in Windows PowerShell ausführen.

Geben Sie PowerShell_ISE.exe, PowerShell_ISE oder ISE ein, um PowerShell_ISE.exe auszuführen.

## <a name="syntax"></a>SYNTAX

```
PowerShell_Ise[.exe]
PowerShell_ISE[.exe]
ISE[.exe]
[-File]<FilePath[]> [-NoProfile] [-MTA]
-Help | ? | -? | /? Displays the syntax and describes the command-line switches.
```

## <a name="parameters"></a>PARAMETERS

### <a name="-file"></a>-File

Öffnet die angegebenen Dateien in Windows PowerShell ISE. Der Parameter Name ("-file") ist optional. Um mehr als eine Datei aufzulisten, geben Sie eine Text Zeichenfolge ein, die in Anführungszeichen eingeschlossen ist. Verwenden Sie Kommas, um die Dateinamen innerhalb der Zeichenfolge voneinander zu trennen.

Beispiel:

PowerShell_ISE Datei "File1.ps1, File2.ps1 File3.xml".

Leerzeichen zwischen den Dateinamen sind in Windows PowerShell zulässig, werden jedoch möglicherweise nicht ordnungsgemäß von anderen Programmen, z. b. Cmd.exe, interpretiert.

Sie können diesen Parameter verwenden, um eine beliebige Textdatei zu öffnen, einschließlich Windows PowerShell-Skriptdateien und XML-Dateien.

### <a name="-mta"></a>-Mta

Startet Windows PowerShell ISE mit einem Multithread-Apartment. Dieser Parameter wird in Windows PowerShell 3.0 eingeführt. Single Thread-Apartment (STA) ist die Standardeinstellung.

### <a name="-noprofile"></a>-NoProfile

Führt keine Windows PowerShell-Profile aus. Standardmäßig werden Windows PowerShell-Profile in jeder Sitzung ausgeführt.

Dieser Parameter wird empfohlen, wenn Sie freigegebene Inhalte schreiben, z. b. Funktionen und Skripts, die auf Systemen mit unterschiedlichen Profilen ausgeführt werden.
Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).

### <a name="-help---"></a>-Hilfe-?,/?

Zeigt die Hilfe für PowerShell_ISE.exe an.

## <a name="examples"></a>BEISPIELE

Mit diesen Befehlen wird Windows PowerShell ISE gestartet. Diese Befehle sind gleichwertig und austauschbar.

```
PS C:> PowerShell_ISE.exe
PS C:> PowerShell_ISE
PS C:> ISE
```

Mit diesen Befehlen wird das Get-Profile.ps1 Skript in Windows PowerShell ISE geöffnet.
Diese Befehle sind gleichwertig und austauschbar.

```
PS C:> PowerShell_ISE.exe -File .\Get-Profile.ps1
PS C:> ISE -File .\Get-Profile.ps1
PS C:> ISE .\Get-Profile.ps1
```

Mit diesem Befehl werden die Get-Backups.ps1-und Get-BackupInstance.ps1 Skripts in Windows PowerShell ISE geöffnet. Um mehr als eine Datei zu öffnen, verwenden Sie ein Komma, um die Dateinamen voneinander zu trennen, und schließen Sie den gesamten Dateinamen in Anführungszeichen ein.

```
PS C:> ISE -File ".\Get-Backups.ps1,Get-BackupInstance.ps1"
```

Mit diesem Befehl wird Windows PowerShell ISE ohne profile gestartet.

```
PS C:> ISE -NoProfile
```

Mit diesem Befehl wird die Hilfe für PowerShell_ISE.exe abgerufen.

```
PS C:> ISE -help
```

## <a name="see-also"></a>SIEHE AUCH

[about_PowerShell.exe](about_PowerShell_exe.md)

[about_Windows_PowerShell_ISE](about_Windows_PowerShell_ISE.md)

[Windows PowerShell Integrated Scripting Environment (ISE)](/powershell/scripting/windows-powershell/ise/introducing-the-windows-powershell-ise)
