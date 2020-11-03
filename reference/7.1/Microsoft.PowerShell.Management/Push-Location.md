---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/push-location?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Push-Location
ms.openlocfilehash: 91ee85507d8ad0f128025af3d549d461310a415d
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "93219151"
---
# Push-Location

## ZUSAMMENFASSUNG
Fügt den aktuellen Speicherort an oberster Stelle eines Speicherstapels hinzu.

## SYNTAX

### Pfad (Standard)

```
Push-Location [[-Path] <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

### LiteralPath

```
Push-Location [-LiteralPath <String>] [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Push-Location` Cmdlet wird der aktuelle Speicherort zu einem Speicherort Stapel hinzugefügt ("pushen"). Wenn Sie einen Pfad angeben, wird `Push-Location` der aktuelle Speicherort von an einen Speicherort Stapel gepusht, und der aktuelle Speicherort wird in den durch den Pfad angegebenen Speicherort geändert. Sie können das `Pop-Location` Cmdlet verwenden, um Standorte aus dem Speicherort Stapel zu erhalten.

Standardmäßig schiebt das `Push-Location` Cmdlet den aktuellen Speicherort auf den aktuellen Speicher Stapel, aber Sie können den **stackname** -Parameter verwenden, um einen alternativen Speicherort Stapel anzugeben. Wenn der Stapel nicht vorhanden ist, wird `Push-Location` er von erstellt.

Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).

## BEISPIELE

### Beispiel 1

In diesem Beispiel wird der aktuelle Speicherort auf den Standard Speicherort Stapel gepusht und der Speicherort dann in geändert `C:\Windows` .

```
PS C:\> Push-Location C:\Windows
```

### Beispiel 2

In diesem Beispiel wird der aktuelle Speicherort auf den regfunction-Stapel gepusht und der aktuelle Speicherort in den `HKLM:\Software\Policies` Speicherort geändert.

```
PS C:\> Push-Location HKLM:\Software\Policies -StackName RegFunction
```

Sie können die Location-Cmdlets in einem beliebigen PowerShell-Laufwerk (PSDrive) verwenden.

### Beispiel 3

Mit diesem Befehl wird der aktuelle Speicherort auf den Standardstapel verschoben. Der Speicherort wird nicht geändert.

```
PS C:\> Push-Location
```

### Beispiel 4: Erstellen und Verwenden eines benannten Stapels

Diese Befehle veranschaulichen das Erstellen und Verwenden eines benannten Speicherstapels.

```
PS C:\> Push-Location ~ -StackName Stack2
PS C:\Users\User01> Pop-Location -StackName Stack2
PS C:\>
```

Mit dem ersten Befehl wird der aktuelle Speicherort auf einen neuen Stapel mit dem Namen "Stack2" übertragen. Anschließend wird der aktuelle Speicherort in das Basisverzeichnis geändert, das im Befehl durch das tildesymbol () dargestellt wird `~` , das bei Verwendung auf einem Dateisystem Anbieter `$HOME` -Laufwerke und entspricht `$env:USERPROFILE` .

Wenn Stack2 nicht bereits in der Sitzung vorhanden ist, wird `Push-Location` Sie von erstellt. Der zweite Befehl verwendet das `Pop-Location` Cmdlet, um den ursprünglichen Speicherort ( `C:\` ) aus dem Stack2-Stapel zu Popups. Ohne den **stackname** -Parameter `Pop-Location` würde den Speicherort aus dem unbenannten Standard Stapel aufklappen.

Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).

## PARAMETERS

### -Literalpath

Gibt den Pfad zum neuen Speicherort an. Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Übergibt ein Objekt, das den Speicherort darstellt, an die Pipeline. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

Ändert den Speicherort in den von diesem Pfad angegebenen Speicherort, nachdem der aktuelle Speicherort dem Stapel an oberster Position hinzugefügt wurde. Geben Sie einen Pfad zu einem Speicherort ein, dessen Anbieter dieses Cmdlet unterstützt. Platzhalter sind zulässig. Der Parametername ist optional.

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Stackname

Gibt den Speicherstapel an, dem der aktuelle Speicherort hinzugefügt wird. Geben Sie einen Speicherstapelnamen ein.
Wenn der Stapel nicht vorhanden ist, wird `Push-Location` er von erstellt.

Ohne diesen Parameter wird `Push-Location` der Speicherort dem aktuellen Speicher Stapel hinzugefügt. Standardmäßig ist der aktuelle Speicher Stapel der unbenannte Standard Speicherort Stapel, den PowerShell erstellt.
Verwenden Sie den **stackname** -Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` . Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).

> [!NOTE]
> `Push-Location` ein Speicherort kann nur dem unbenannten Standard Stapel hinzugefügt werden, wenn es sich um den aktuellen Speicher Stapel handelt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default stack
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge, die einen Pfad (jedoch keinen literalen Pfad) enthält, über die Pipeline an senden `Push-Location` .

## AUSGABEN

### None oder System. Management. Automation. PathInfo

Wenn Sie den **passthru** -Parameter verwenden, `Push-Location` generiert ein **System. Management. Automation. PathInfo** -Objekt, das den Speicherort darstellt. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

PowerShell unterstützt mehrere Runspaces pro Prozess. Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.
Dies ist nicht identisch mit `[System.Environment]::CurrentDirectory` . Dieses Verhalten kann ein Problem sein, wenn Sie .NET-APIs aufrufen oder native Anwendungen ausführen, ohne explizite Verzeichnispfade bereitzustellen.

Auch wenn die Location-Cmdlets das aktuelle Prozess weite Verzeichnis festgelegt haben, können Sie nicht davon abhängen, weil es von einem anderen Runspace möglicherweise jederzeit geändert wird. Verwenden Sie die Location-Cmdlets zum Ausführen von Pfad basierten Vorgängen mit dem aktuellen Arbeitsverzeichnis, das für den aktuellen Runspace spezifisch ist.

Bei einem Stapel handelt es sich um eine Last-in-First-out-Liste, in der nur auf das zuletzt hinzugefügte Element zugegriffen werden kann.
Sie fügen einem Stapel Elemente in der Reihenfolge hinzu, in der Sie sie verwenden. Anschließend rufen Sie sie zur Verwendung in der umgekehrten Reihenfolge auf. Mit PowerShell können Sie Anbieter Speicherorte in Speicherort Stapeln speichern.

Von PowerShell wird ein unbenannter Standard Speicher Stapel erstellt, und Sie können mehrere benannte Speicher Stapel erstellen. Wenn Sie keinen Stapelnamen angeben, verwendet PowerShell den aktuellen Speicher Stapel. Standardmäßig ist der unbenannte Standard Speicherort der aktuelle Speicher Stapel. Sie können das `Set-Location` Cmdlet jedoch verwenden, um den aktuellen Speicher Stapel zu ändern.

Verwenden Sie zum Verwalten von Speicherort Stapeln die PowerShell-Location-Cmdlets wie folgt.

- Verwenden Sie das-Cmdlet, um einen Speicherort zu einem Speicherort Stapel hinzuzufügen `Push-Location` .

- Verwenden Sie das-Cmdlet, um einen Speicherort aus einem Speicherort Stapel zu erhalten `Pop-Location` .

- Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter des `Get-Location` Cmdlets.

- Um die Speicherorte in einem benannten Positions Stapel anzuzeigen, verwenden Sie den **stackname** -Parameter des `Get-Location` Cmdlets.

- Um einen neuen Speicherort Stapel zu erstellen, verwenden Sie den stackname-Parameter des `Push-Location` Cmdlets. Wenn Sie einen Stapel angeben, der nicht vorhanden ist, wird `Push-Location` der Stapel von erstellt.

- Verwenden Sie den stackname-Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .

Auf den unbenannten Standardspeicherstapel kann nur vollständig zugegriffen werden, wenn es sich dabei um den aktuellen Speicherstapel handelt.
Wenn Sie einen benannten Speicherort Stapel zum aktuellen Speicher Stapel machen, können Sie die `Push-Location` Cmdlets oder nicht mehr verwenden, `Pop-Location` um Elemente zum Standard Stapel hinzuzufügen oder daraus zu machen. Sie können auch das `Get-Location` Cmdlet verwenden, um die Speicherorte im unbenannten Stapel anzuzeigen. Um den unbenannten Stapel zum aktuellen Stapel zu machen, verwenden Sie den **stackname** -Parameter des `Set-Location` Cmdlets mit dem Wert `$null` oder einer leeren Zeichenfolge ( `""` ).

Sie können auch auf den `Push-Location` integrierten Alias verweisen `pushd` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Das- `Push-Location` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Get-Location](Get-Location.md)

[Pop-Location](Pop-Location.md)

[Set-Location](Set-Location.md)

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
