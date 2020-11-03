---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-location?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Location
ms.openlocfilehash: 235c775e2da4188213f4eb35612c469947b5e2fc
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "93219543"
---
# Get-Location

## ZUSAMMENFASSUNG
Ruft Informationen zum aktuellen Arbeitsspeicherot oder Speicherstapel ab.

## SYNTAX

### Speicherort (Standard)

```
Get-Location [-PSProvider <String[]>] [-PSDrive <String[]>] [<CommonParameters>]
```

### Stapel

```
Get-Location [-Stack] [-StackName <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-Location` Cmdlet ruft ein Objekt ab, das das aktuelle Verzeichnis darstellt, ähnlich wie der pwd-Befehl (Print Working Directory).

Wenn Sie zwischen PowerShell-Laufwerken wechseln, behält PowerShell ihren Speicherort auf jedem Laufwerk bei. Mit diesem Cmdlet können Sie ihren Speicherort auf jedem Laufwerk suchen.

Mit diesem Cmdlet können Sie das aktuelle Verzeichnis zur Laufzeit herunterladen und in Funktionen und Skripts verwenden, z. b. in einer Funktion, die das aktuelle Verzeichnis in der PowerShell-Eingabeaufforderung anzeigt.

Mit diesem Cmdlet können Sie auch die Speicherorte in einem Speicher Stapel anzeigen. Weitere Informationen finden Sie in den Hinweisen und Beschreibungen der **Stapel** -und **stackname** -Parameter.

## BEISPIELE

### Beispiel 1: Anzeigen des aktuellen Laufwerks

Dieser Befehl zeigt den Speicherort auf dem aktuellen PowerShell-Laufwerk an.

```powershell
PS C:\Windows> Get-Location
```

```Output
Path
----
C:\Windows
```

Wenn Sie sich beispielsweise im `Windows` Verzeichnis des `C:` Laufwerks befinden, wird der Pfad zu diesem Verzeichnis angezeigt.

### Beispiel 2: Anzeigen Ihres aktuellen Speicher Orts für verschiedene Laufwerke

In diesem Beispiel wird die Verwendung von `Get-Location` zum Anzeigen Ihres aktuellen Speicher Orts in verschiedenen PowerShell-Laufwerken veranschaulicht. `Set-Location` wird verwendet, um den Speicherort in mehrere verschiedene Pfade auf verschiedenen PSDrives zu ändern.

```powershell
PS C:\> Set-Location C:\Windows
PS C:\Windows> Set-Location HKLM:\Software\Microsoft
PS HKLM:\Software\Microsoft> Set-Location "HKCU:\Control Panel\Input Method"
PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive C

Path
----
C:\Windows

PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive HKLM

Path
----
HKLM:\Software\Microsoft

PS HKCU:\Control Panel\Input Method> Set-Location C:
PS C:\Windows> Get-Location -PSProvider Registry

Path
----
HKCU:\Control Panel\Input Method
```

### Beispiel 3: Speicherorte mithilfe von Stapeln

In diesem Beispiel wird gezeigt, wie die **Stapel** -und **stackname** -Parameter von verwendet werden `Get-Location` , um die Speicherorte im aktuellen Speicher Stapel und in alternativen Speicher Stapeln aufzulisten.

Das- `Push-Location` Cmdlet wird verwendet, um in drei verschiedene Speicherorte zu wechseln. Für den dritten Push wird ein anderer Stapelname verwendet. Der **Stapel** Parameter von `Get-Location` zeigt den Inhalt des Standard Stapels an. Der **stackname** -Parameter von `Get-Location` zeigt den Inhalt des Stapels mit dem Namen an `Stack2` .

```powershell
PS C:\> Push-Location C:\Windows
PS C:\Windows>Push-Location System32
PS C:\Windows\System32>Push-Location WindowsPowerShell -StackName Stack2
C:\Windows\System32\WindowsPowerShell>Get-Location -Stack

Path
----
C:\Windows
C:\

C:\Windows\System32\WindowsPowerShell>Get-Location -StackName Stack2

Path
----
C:\Windows\System32
```

### Beispiel 4: Anpassen der PowerShell-Eingabeaufforderung

In diesem Beispiel wird gezeigt, wie die PowerShell-Eingabeaufforderung angepasst wird.

```powershell
PS C:\>
function prompt { 'PowerShell: ' + (Get-Location) + '> '}
PowerShell: C:\>
```

Die Funktion, die die Eingabeaufforderung definiert, enthält einen- `Get-Location` Befehl, der ausgeführt wird, wenn die Eingabeaufforderung in der Konsole angezeigt wird.

Das Format der PowerShell-Standardeingabe Aufforderung wird von einer speziellen Funktion mit dem Namen definiert `prompt` . Sie können die Eingabeaufforderung in der Konsole ändern, indem Sie eine neue Funktion mit dem Namen erstellen `prompt` .

Zum Anzeigen der aktuellen prompt-Funktion geben Sie den folgenden Befehl ein: `Get-Content Function:\prompt`

## PARAMETERS

### -PSDrive

Ruft die aktuelle Position im angegebenen PowerShell-Laufwerk ab.

Wenn Sie sich beispielsweise auf dem `Cert:` Laufwerk befinden, können Sie diesen Parameter verwenden, um den aktuellen Speicherort auf dem Laufwerk zu finden `C:` .

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Psprovider

Ruft den aktuellen Speicherort auf dem Laufwerk ab, der vom angegebenen PowerShell-Anbieter unterstützt wird.
Wenn der angegebene Anbieter mehr als ein Laufwerk unterstützt, gibt dieses Cmdlet den Speicherort auf dem Laufwerk zurück, auf das zuletzt zugegriffen wurde.

Wenn Sie sich z. b. auf dem `C:` Laufwerk befinden, können Sie diesen Parameter verwenden, um den aktuellen Speicherort auf den Laufwerken des PowerShell- **Registrierungs** Anbieters zu finden.

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Stack

Gibt an, dass dieses Cmdlet die Speicherorte anzeigt, die dem aktuellen Speicher Stapel hinzugefügt werden. Mithilfe des-Cmdlets können Sie Stapel Speicherorte hinzufügen `Push-Location` .

Verwenden Sie den **stackname** -Parameter, um die Speicherorte in einem anderen Speicher Stapel anzuzeigen. Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stackname

Gibt die benannten Positions Stapel als Zeichen folgen Array an. Geben Sie Speicherstapelnamen ein.

Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter. Verwenden Sie das-Cmdlet, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .

Dieses Cmdlet kann die Speicherorte im unbenannten Standard Stapel nicht anzeigen, es sei denn, es handelt sich um den aktuellen Stapel.

```yaml
Type: System.String[]
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. PathInfo oder System. Management. Automation. pathinfostack

Wenn Sie den **Stack** -Parameter oder den **stackname** -Parameter verwenden, gibt dieses Cmdlet ein " **pthinfostack** "-Objekt zurück. Andernfalls wird ein **pathinfo** -Objekt zurückgegeben.

## HINWEISE

PowerShell unterstützt mehrere Runspaces pro Prozess. Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.
Dies ist nicht identisch mit `[System.Environment]::CurrentDirectory` . Dieses Verhalten kann ein Problem sein, wenn Sie .NET-APIs aufrufen oder native Anwendungen ausführen, ohne explizite Verzeichnispfade bereitzustellen.
Mit dem- `Get-Location` Cmdlet wird das aktuelle Verzeichnis des aktuellen PowerShell-Runspace zurückgegeben.

Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die Anbieter in Ihrer Sitzung aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

Die Art und Weise, in der die Parameter **psprovider** , **PSDrive** , **Stack** und **stackname** interagieren, hängt vom Anbieter ab. Bestimmte Kombinationen führen zu Fehlern, beispielsweise wenn ein Laufwerk zusammen mit einem Anbieter angegeben wird, der das betreffende Laufwerk nicht verfügbar macht. Wenn keine Parameter angegeben werden, gibt dieses Cmdlet das **pathinfo** -Objekt für den Anbieter zurück, der den aktuellen Arbeits Speicherort enthält.

Bei einem Stapel handelt es sich um eine Last-in-First-out-Liste, in der nur auf das zuletzt hinzugefügte Element zugegriffen werden kann. Sie fügen einem Stapel Elemente in der Reihenfolge hinzu, in der Sie sie verwenden. Anschließend rufen Sie sie zur Verwendung in der umgekehrten Reihenfolge auf. Mit PowerShell können Sie Anbieter Speicherorte in Speicherort Stapeln speichern. Von PowerShell wird ein unbenannter Standard Speicher Stapel erstellt, und Sie können mehrere benannte Speicher Stapel erstellen. Wenn Sie keinen Stapelnamen angeben, verwendet PowerShell den aktuellen Speicher Stapel. Standardmäßig ist der unbenannte Standard Speicherort der aktuelle Speicher Stapel. Sie können das `Set-Location` Cmdlet jedoch verwenden, um den aktuellen Speicher Stapel zu ändern.

Verwenden Sie zum Verwalten von Speicherort Stapeln die PowerShell- `*-Location` Cmdlets wie folgt.

- Verwenden Sie das-Cmdlet, um einen Speicherort zu einem Speicherort Stapel hinzuzufügen `Push-Location` .

- Verwenden Sie das-Cmdlet, um einen Speicherort aus einem Speicherort Stapel zu erhalten `Pop-Location` .

- Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter des `Get-Location` Cmdlets. Um die Speicherorte in einem benannten Positions Stapel anzuzeigen, verwenden Sie den **stackname** -Parameter des `Get-Location` Cmdlets.

- Um einen neuen Speicherort Stapel zu erstellen, verwenden Sie den **stackname** -Parameter des `Push-Location` Cmdlets.
  Wenn Sie einen Stapel angeben, der nicht vorhanden ist, wird `Push-Location` der Stapel von erstellt.

- Verwenden Sie den **stackname** -Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .

Auf den unbenannten Standardspeicherstapel kann nur vollständig zugegriffen werden, wenn es sich dabei um den aktuellen Speicherstapel handelt.
Wenn Sie einen benannten Speicherort Stapel zum aktuellen Speicher Stapel machen, können Sie die `Push-Location` Cmdlets oder nicht mehr verwenden, `Pop-Location` um Elemente zum Standard Stapel hinzuzufügen oder daraus zu machen. Sie können auch das Cmdlet verwenden, um die Speicherorte im unbenannten Stapel anzuzeigen. Um den unbenannten Stapel zum aktuellen Stapel zu machen, verwenden Sie den **stackname** -Parameter des `Set-Location` Cmdlets mit dem Wert `$null` oder einer leeren Zeichenfolge ( `""` ).

## VERWANDTE LINKS

[Pop-Location](Pop-Location.md)

[Push-Location](Push-Location.md)

[Set-Location](Set-Location.md)
