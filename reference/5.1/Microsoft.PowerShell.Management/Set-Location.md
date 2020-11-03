---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Location
ms.openlocfilehash: 06b1596366c9c9e20857b55aa9a17342bab07028
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "93219551"
---
# Set-Location

## ZUSAMMENFASSUNG
Legt den aktuellen Arbeitsspeicherort auf einen angegebenen Speicherort fest.

## SYNTAX

### Pfad (Standard)

```
Set-Location [[-Path] <String>] [-PassThru] [-UseTransaction] [<CommonParameters>]
```

### LiteralPath

```
Set-Location -LiteralPath <String> [-PassThru] [-UseTransaction] [<CommonParameters>]
```

### Stapel

```
Set-Location [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-Location` Cmdlet wird der Arbeits Speicherort auf einen angegebenen Speicherort festgelegt. Bei diesem Speicherort kann es sich um ein Verzeichnis, ein Unterverzeichnis, einen Registrierungs Speicherort oder einen Anbieter Pfad handeln.

Sie können auch den **stackname** -Parameter verwenden, um einen benannten Speicherort Stapel zum aktuellen Speicher Stapel zu machen. Weitere Informationen zu Speicherstapeln finden Sie in den Hinweisen.

## BEISPIELE

### Beispiel 1: Festlegen des aktuellen Speicher Orts

```powershell
PS C:\> Set-Location -Path "HKLM:\"
```

```output
PS HKLM:\>
```

Mit diesem Befehl wird der aktuelle Speicherort auf den Stamm des `HKLM:` Laufwerks festgelegt.

### Beispiel 2: Festlegen des aktuellen Speicher Orts und Anzeigen dieses Speicher Orts

```powershell
PS C:\> Set-Location -Path "Env:\" -PassThru
```

```output
Path
----
Env:\

PS Env:\>
```

Mit diesem Befehl wird der aktuelle Speicherort auf den Stamm des `Env:` Laufwerks festgelegt. Er verwendet den **passthru** -Parameter, um PowerShell anzuweisen, ein **pathinfo** -Objekt zurückzugeben, das den `Env:\` Speicherort darstellt.

### Beispiel 3: Festlegen des Speicher Orts auf den aktuellen Speicherort auf Laufwerk C:

```powershell
PS C:\Windows\> Set-Location HKLM:\
PS HKLM:\> Set-Location C:
PS C:\Windows\>
```

Mit dem ersten Befehl wird der Speicherort auf den Stamm des `HKLM:` Laufwerks im Registrierungs Anbieter festgelegt.
Mit dem zweiten Befehl wird der Speicherort auf den aktuellen Speicherort des `C:` Laufwerks im File System-Anbieter festgelegt.
Wenn der Laufwerks Name in der Form `<DriveName>:` (ohne umgekehrten Schrägstrich) angegeben wird, legt das Cmdlet den Speicherort auf den aktuellen Speicherort auf dem PSDrive fest.
Um den aktuellen Speicherort im Befehl "PSDrive use" abzurufen `Get-Location -PSDrive <DriveName>` .

### Beispiel 4: Festlegen des aktuellen Speicher Orts auf einen benannten Stapel

```powershell
PS C:\> Push-Location -Path 'C:\Program Files\PowerShell\' -StackName "Paths"
PS C:\Program Files\PowerShell\> Set-Location -StackName "Paths"
PS C:\Program Files\PowerShell\> Get-Location -Stack
```

```Output
Path
----
C:\
```

Mit dem ersten Befehl wird der aktuelle Speicherort dem Pfad Stapel hinzugefügt.
Mit dem zweiten Befehl wird der Speicherort des Pfads zum aktuellen Speicher Stapel.
Der dritte Befehl zeigt die Speicherorte im aktuellen Speicher Stapel an.

Die `*-Location` Cmdlets verwenden den aktuellen Speicher Stapel, es sei denn, im Befehl wird ein anderer Speicher Stapel angegeben. Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).

## PARAMETERS

### -Literalpath

Gibt einen Pfad zum Speicherort an. Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

Einfache Anführungszeichen veranlassen Windows PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Gibt ein **pathinfo** -Objekt zurück, das den Speicherort darstellt. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Geben Sie den Pfad eines neuen Arbeitsspeicher Orts an. Wenn kein Pfad angegeben wird, wird `Set-Location` standardmäßig das Basisverzeichnis des aktuellen Benutzers verwendet. Wenn Platzhalter verwendet werden, wählt das Cmdlet den ersten Pfad aus, der mit dem Platzhalter Muster übereinstimmt.

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Stackname

Gibt den vorhandenen Namen des Speicher Orts an, der von diesem Cmdlet zum aktuellen Speicher Stapel erstellt wird. Geben Sie einen Speicherstapelnamen ein. Um den unbenannten Standard Speicher Stapel anzugeben, geben Sie `$null` oder eine leere Zeichenfolge ( `""` ) ein.

Die `*-Location` Cmdlets agieren für den aktuellen Stapel, es sei denn, Sie verwenden den **stackname** -Parameter, um einen anderen Stapel anzugeben.

```yaml
Type: System.String
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseTransaction

Schließt den Befehl in die aktive Transaktion ein.
Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.
Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

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

Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.

## AUSGABEN

### None, System. Management. Automation. PathInfo, System. Management. Automation. pathinfostack

Dieses Cmdlet generiert keine Ausgabe, es sei denn, Sie geben den **passthru** -Parameter an. Durch die Verwendung von **passthru** mit **path** oder **literalpath** wird ein **pathinfo** -Objekt generiert, das den neuen Speicherort darstellt. Bei Verwendung von **passthru** mit **stackname** wird ein " **pthinfostack** "-Objekt generiert, das den neuen Stapel Kontext darstellt.

## HINWEISE

PowerShell unterstützt mehrere Runspaces pro Prozess. Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.
Dies ist nicht identisch mit `[System.Environment]::CurrentDirectory` . Dieses Verhalten kann ein Problem sein, wenn Sie .NET-APIs aufrufen oder native Anwendungen ausführen, ohne explizite Verzeichnispfade bereitzustellen.

Auch wenn die Location-Cmdlets das aktuelle Prozess weite Verzeichnis festgelegt haben, können Sie nicht davon abhängen, weil es von einem anderen Runspace möglicherweise jederzeit geändert wird. Verwenden Sie die Location-Cmdlets zum Ausführen von Pfad basierten Vorgängen mit dem aktuellen Arbeitsverzeichnis, das für den aktuellen Runspace spezifisch ist.

Das- `Set-Location` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/about/about_Providers.md).

Bei einem Stapel handelt es sich um eine Last-in-First-out-Liste, in der nur auf das zuletzt hinzugefügte Element zugegriffen werden kann. Sie fügen einem Stapel Elemente in der Reihenfolge hinzu, in der Sie sie verwenden. Anschließend rufen Sie sie zur Verwendung in der umgekehrten Reihenfolge auf. Mit PowerShell können Sie Anbieter Speicherorte in Speicherort Stapeln speichern. PowerShell erstellt einen unbenannten Standard Speicher Stapel. Sie können mehrere benannte Speicher Stapel erstellen. Wenn Sie keinen Stapelnamen angeben, verwendet PowerShell den aktuellen Speicher Stapel. Standardmäßig ist der unbenannte Standard Speicherort der aktuelle Speicher Stapel. Sie können das `Set-Location` Cmdlet jedoch verwenden, um den aktuellen Speicher Stapel zu ändern.

Verwenden Sie zum Verwalten von Speicherort Stapeln die `*-Location` Cmdlets wie folgt:

- Verwenden Sie das-Cmdlet, um einen Speicherort zu einem Speicherort Stapel hinzuzufügen `Push-Location` .

- Verwenden Sie das-Cmdlet, um einen Speicherort aus einem Speicherort Stapel zu erhalten `Pop-Location` .

- Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter des `Get-Location` Cmdlets. Um die Speicherorte in einem benannten Positions Stapel anzuzeigen, verwenden Sie den **stackname** -Parameter von `Get-Location` .

- Um einen neuen Speicherort Stapel zu erstellen, verwenden Sie den **stackname** -Parameter von `Push-Location` . Wenn Sie einen Stapel angeben, der nicht vorhanden ist, wird `Push-Location` der Stapel von erstellt.

- Um einen Speicherort Stapel zum aktuellen Speicher Stapel zu machen, verwenden Sie den **stackname** -Parameter von `Set-Location` .

Auf den unbenannten Standardspeicherstapel kann nur vollständig zugegriffen werden, wenn es sich dabei um den aktuellen Speicherstapel handelt.
Wenn Sie einen benannten Speicherort Stapel zum aktuellen Speicher Stapel machen, können Sie die `Push-Location` Cmdlets oder nicht mehr verwenden, `Pop-Location` um Elemente zum Standard Stapel hinzuzufügen oder daraus zu machen. Sie können auch das `Get-Location` Cmdlet verwenden, um die Speicherorte im unbenannten Stapel anzuzeigen. Um den unbenannten Stapel zum aktuellen Stapel zu machen, verwenden Sie den **stackname** -Parameter des `Set-Location` Cmdlets mit dem Wert `$null` oder einer leeren Zeichenfolge ( `""` ).

## VERWANDTE LINKS

[Get-Location](Get-Location.md)

[Pop-Location](Pop-Location.md)

[Push-Location](Push-Location.md)
