---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Module
ms.openlocfilehash: 2954bbec68b837a73e5365ab6a1e8ecb501d4898
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602538"
---
# Remove-Module

## ZUSAMMENFASSUNG
Entfernt Module aus der aktuellen Sitzung.

## SYNTAX

### name

```
Remove-Module [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FullyQualifiedName

```
Remove-Module [-FullyQualifiedName] <ModuleSpecification[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ModuleInfo

```
Remove-Module [-ModuleInfo] <PSModuleInfo[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das **Remove-Module**-Cmdlet entfernt die Elemente eines Moduls, wie z. B. Cmdlets und Funktionen, aus der aktuellen Sitzung.

Wenn das Modul eine Assembly (.dll) enthält, werden alle Elemente entfernt, die von der Assembly implementiert werden, die Assembly wird jedoch nicht entladen.

Mit diesem Cmdlet wird das Modul nicht deinstalliert oder vom Computer gelöscht.
Er wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.

## BEISPIELE

### Beispiel 1: Entfernen eines Moduls

```powershell
Remove-Module -Name "BitsTransfer"
```

Mit diesem Befehl wird das BitsTransfer-Modul aus der aktuellen Sitzung entfernt.

### Beispiel 2: Entfernen aller Module

```powershell
Get-Module | Remove-Module
```

Dieser Befehl entfernt alle Module aus der aktuellen Sitzung.

### Beispiel 3: Entfernen von Modulen mithilfe der Pipeline

```powershell
"FileTransfer", "PSDiagnostics" | Remove-Module -Verbose
```

```Output
VERBOSE: Performing operation "Remove-Module" on Target "filetransfer (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\filetransfer\filetransfer.psd1')".
VERBOSE: Performing operation "Remove-Module" on Target "Microsoft.BackgroundIntelligentTransfer.Management (Path: 'C:\Windows\assembly\GAC_MSIL\Microsoft.BackgroundIntelligentTransfer.Management\1.0.0.0__31bf3856ad364e35\Microsoft.BackgroundIntelligentTransfe
r.Management.dll')".
VERBOSE: Performing operation "Remove-Module" on Target "psdiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\psdiagnostics.psd1')".
VERBOSE: Removing imported function 'Start-Trace'.
VERBOSE: Removing imported function 'Stop-Trace'.
VERBOSE: Removing imported function 'Enable-WSManTrace'.
VERBOSE: Removing imported function 'Disable-WSManTrace'.
VERBOSE: Removing imported function 'Enable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Disable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Set-LogProperties'.
VERBOSE: Removing imported function 'Get-LogProperties'.
VERBOSE: Removing imported function 'Enable-PSTrace'.
VERBOSE: Removing imported function 'Disable-PSTrace'.
VERBOSE: Performing operation "Remove-Module" on Target "PSDiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\PSDiagnostics.psm1')".
```

Dieser Befehl entfernt die BitsTransfer- und PSDiagnostics-Module aus der aktuellen Sitzung.

Der Befehl verwendet einen Pipelineoperator (|), um die Modulnamen an **Remove-Module** zu senden.
Er verwendet den allgemeinen *Verbose*-Parameter, um detaillierte Informationen über die zu entfernenden Elemente abzurufen.

In den ausführlichen Meldungen werden die Elemente angezeigt *, die entfernt* werden.
Die Meldungen unterscheiden sich voneinander, da das BitsTransfer-Modul eine Assembly enthält, die die Cmdlets implementiert, sowie ein geschachteltes Modul mit seiner eigenen Assembly.
Das PSDiagnostics-Modul umfasst eine Modulskriptdatei (.psm1), die Funktionen exportiert.

### Beispiel 4: Entfernen eines Moduls mithilfe von ModuleInfo

```powershell
$a = Get-Module BitsTransfer
Remove-Module -ModuleInfo $a
```

Dieser Befehl verwendet den *ModuleInfo* -Parameter, um das bitstransfer-Modul zu entfernen.

## PARAMETERS

### -Force

Gibt an, dass mit diesem Cmdlet schreibgeschützte Module entfernt werden.
In der Standardeinstellung entfernt **Remove-Module** nur Module mit Lese-/ Schreibzugriff.

Die Werte **ReadOnly** und **ReadWrite** sind in der **AccessMode**-Eigenschaft eines Moduls gespeichert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedName

Gibt die voll qualifizierten Namen von Modulen an, die entfernt werden sollen.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ModuleInfo

Gibt die zu entfernenden Modulobjekte an.
Geben Sie eine Variable ein, die ein Modul Objekt (**psmoduleinfo**) enthält, oder einen Befehl, mit dem ein Modul Objekt abgerufen wird, z. b. ein Get-Module Befehl.
Sie können auch Modulobjekte an **Remove-Module** übergeben.

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die Namen der zu entfernenden Module an.
Platzhalterzeichen sind zulässig.
Sie können auch Namenszeichenfolgen an **Remove-Module** übergeben.

```yaml
Type: System.String[]
Parameter Sets: name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. String, System. Management. Automation. psmoduleinfo

Sie können Modulnamen und Modul Objekte über die Pipeline an **Remove-Module** übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

Beim Entfernen eines Moduls ist ein Ereignis für das Modul vorhanden, das ausgeführt wird.
Dieses Ereignis ermöglicht einem Modul, auf das Entfernen zu reagieren und einige Bereinigungs Vorgänge auszuführen, z. b. das Freigeben von Ressourcen. Beispiel:

$OnRemoveScript = {

  \# Bereinigung ausführen

  $cachedSessions | Remove-PSSession

}

$ExecutionContext. SessionState. Module. OnRemove + = $OnRemoveScript

Um vollständige Konsistenz zu gewährleisten, kann es auch hilfreich sein, auf den Abschluss des PowerShell-Prozesses zu reagieren:

Register-EngineEvent-SourceIdentifier ([System. Management. Automation. psengineevent]:: Exit)-Action $OnRemoveScript

## VERWANDTE LINKS

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

