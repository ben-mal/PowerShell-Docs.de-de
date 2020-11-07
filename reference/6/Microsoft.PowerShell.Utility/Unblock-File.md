---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 4774c87c4f6ebe7f374f30139ead833bde7074e3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343401"
---
# Unblock-File

## ZUSAMMENFASSUNG
Hebt die Blockierung von Dateien auf, die aus dem Internet heruntergeladen wurden.

## SYNTAX

### Bypath (Standard)

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Byliteralpath

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Unblock-File` Cmdlet können Sie Dateien öffnen, die aus dem Internet heruntergeladen wurden. Die Blockierung von PowerShell-Skriptdateien, die aus dem Internet heruntergeladen wurden, wird aufgehoben, sodass Sie Sie ausführen können, auch wenn die PowerShell-Ausführungs Richtlinie **RemoteSigned** ist. Standardmäßig werden diese Dateien blockiert, um den Computer vor nicht vertrauenswürdigen Dateien zu schützen.

Bevor Sie das `Unblock-File` Cmdlet verwenden, überprüfen Sie die Datei und ihre Quelle, und vergewissern Sie sich, dass Sie sicher geöffnet werden kann.

Intern entfernt das `Unblock-File` Cmdlet den alternativen Datenstrom "Zone. Identifier" mit dem Wert "3", um anzugeben, dass er aus dem Internet heruntergeladen wurde.

Weitere Informationen zu PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Entsperren einer Datei

Dieser Befehl hebt die Blockierung der Datei „PowerShellTips.chm“ auf.

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

### Beispiel 2: entsperren mehrerer Dateien

Dieser Befehl hebt die Blockierung aller Dateien im Verzeichnis auf, `C:\Downloads` deren Namen "PowerShell" enthalten. Führen Sie keinen Befehl wie diesen aus, bis Sie sichergestellt haben, dass alle Dateien sicher sind.

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

### Beispiel 3: Suchen und Entsperren von Skripts

Dieser Befehl zeigt, wie Sie PowerShell-Skripts suchen und deren Blockierung entsperren.

Der erste Befehl verwendet den **Stream** -Parameter des *Get-Item-* Cmdlets zum Aufrufen von Dateien mit dem "Zone. Identifier"-Stream.

Der zweite Befehl zeigt, was geschieht, wenn Sie ein blockiertes Skript in einer PowerShell-Sitzung ausführen, in der die Ausführungs Richtlinie **RemoteSigned** ist. Die RemoteSigned-Richtlinie verhindert die Ausführung von Skripts, die aus dem Internet heruntergeladen werden, es sei denn, sie sind digital signiert.

Der dritte Befehl verwendet das `Unblock-File` Cmdlet, um die Blockierung des Skripts zu entsperren, sodass es in der Sitzung ausgeführt werden kann.

```
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

## PARAMETERS

### -Literalpath

Gibt die Dateien an, deren Blockierung aufgehoben werden soll. Im Gegensatz zu **Path** wird der Wert des **LiteralPath** -Parameters genauso verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Gibt die Dateien an, deren Blockierung aufgehoben werden soll. Platzhalterzeichen werden unterstützt.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

### System.String

Sie können einen Dateipfad an die Pipeline übergeben `Unblock-File` .

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

- Das- `Unblock-File` Cmdlet funktioniert nur in Dateisystem Laufwerken.
- `Unblock-File` führt den gleichen Vorgang wie die **Schaltfläche "entsperren"** im Dialogfeld " **Eigenschaften** " im Datei-Explorer aus.
- Wenn Sie das `Unblock-File` Cmdlet für eine Datei verwenden, die nicht blockiert ist, hat der Befehl keine Auswirkungen auf die nicht blockierte Datei, und das Cmdlet generiert keine Fehler.

## VERWANDTE LINKS

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[Get-Item](../Microsoft.PowerShell.Management/Get-Item.md)

[Out-File](Out-File.md)

[FileSystem-Anbieter](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)
