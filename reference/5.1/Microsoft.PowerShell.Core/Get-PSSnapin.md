---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSnapin
ms.openlocfilehash: 156cadecd87910e3c3312e84929b16709770641d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388670"
---
# Get-PSSnapin

## ZUSAMMENFASSUNG
Ruft die Windows PowerShell-Snap-Ins auf dem Computer ab.

## SYNTAX

```
Get-PSSnapin [[-Name] <String[]>] [-Registered] [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-PSSnapin` Cmdlet ruft die Windows PowerShell-Snap-Ins ab, die der aktuellen Sitzung hinzugefügt wurden oder auf dem System registriert wurden. Dieses Cmdlet listet die Snap-Ins in der Reihenfolge auf, in der Sie erkannt werden.

`Get-PSSnapin` Ruft nur registrierte Snap-Ins ab. Verwenden Sie zum Registrieren eines Windows PowerShell-Snap-Ins das InstallUtil-Tool, das im Microsoft .NET Framework 2,0 enthalten ist. Weitere Informationen finden Sie unter [Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).

Ab Windows PowerShell 3,0 werden die in Windows PowerShell enthaltenen Hauptbefehle in Module gepackt. Eine Ausnahme ist das Snap-In **Microsoft.PowerShell.Core** (PSSnapin).
Standardmäßig wird nur das **Microsoft.PowerShell.Core** -Snap-In der Sitzung hinzugefügt. Module werden bei der ersten Verwendung automatisch importiert, und Sie können das `Import-Module` Cmdlet verwenden, um Sie zu importieren.

## BEISPIELE

### Beispiel 1: Get-Snap-Ins, die zurzeit geladen sind

```
PS C:\> Get-PSSnapIn
```

Dieser Befehl ruft die Windows PowerShell-Snap-Ins ab, die derzeit in der Sitzung geladen sind. Dies umfasst die mit Windows PowerShell installierten Snap-Ins und die Snap-Ins, die der Sitzung hinzugefügt wurden.

### Beispiel 2: Get-Snap-Ins, die registriert wurden

```
PS C:\> get-PSSnapIn -Registered
```

Dieser Befehl ruft die für den Computer registrierten Windows PowerShell-Snap-Ins ab, einschließlich der Snap-Ins, die der Sitzung bereits hinzugefügt wurden. Die Ausgabe umfasst keine Snap-Ins, die mit noch nicht beim System registrierten Dynamic-Link Libraries (DLLs) von Windows PowerShell oder Windows PowerShell-Snap-Ins installiert wurden.

### Beispiel 3: erhalten der aktuellen Snap-Ins, die einer Zeichenfolge entsprechen

```
PS C:\> Get-PSSnapIn -Name smp*
```

Dieser Befehl ruft die Windows PowerShell-Snap-Ins in der aktuellen Sitzung ab, deren Namen mit "SMP" beginnen.

## PARAMETERS

### -Name

Gibt ein Array von Snap-in-Namen an. Dieses Cmdlet ruft nur die angegebenen Windows PowerShell-Snap-Ins ab. Platzhalter Zeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Registriert

Gibt an, dass mit diesem Cmdlet die Windows PowerShell-Snap-Ins abgerufen werden, die im System registriert wurden, auch wenn Sie der Sitzung noch nicht hinzugefügt wurden.

Die mit Windows PowerShell installierten Snap-Ins werden in dieser Liste nicht angezeigt.

Ohne diesen Parameter ruft `Get-PSSnapin` die Windows PowerShell-Snap-Ins ab, die der Sitzung hinzugefügt wurden.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. pssnapininfo

`Get-PSSnapin` Gibt ein-Objekt für jedes-Snap-in zurück, das es abruft.

## HINWEISE

Ab Windows PowerShell 3,0 werden die Kern Befehle, die mit Windows PowerShell installiert werden, in Module verpackt. In Windows PowerShell 2,0 und in Host Programmen, die in neueren Versionen von Windows PowerShell ältere Sitzungen erstellen, werden die Hauptbefehle in Snap-Ins ( **PSSnapIn** ) verpackt. Die Ausnahme ist **Microsoft. PowerShell. Core** , bei der es sich immer um ein Snap-in handelt. Remote Sitzungen, wie z. b. die vom `New-PSSession` Cmdlet gestarteten, sind auch ältere Sitzungen, die Core-Snap-Ins enthalten.

 Weitere Informationen über die **CreateDefault2** -Methode, die Sitzungen im neueren Stil mit Kernmodulen erstellt, finden Sie unter [CreateDefault2-Methode](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2).

## VERWANDTE LINKS

[Add-PSSnapin](Add-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
