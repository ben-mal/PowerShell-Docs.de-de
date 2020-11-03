---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: 6843a598b5d20ebd9819b2ed0b180cd21f0416f4
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "93219188"
---
# Pop-Location

## ZUSAMMENFASSUNG
Ändert den aktuellen Speicherort in den Speicherort, der zuletzt auf den Stapel verschoben wurde.

## SYNTAX

```
Pop-Location [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Pop-Location` Cmdlet wird der aktuelle Speicherort in den Speicherort geändert, der zuletzt mit dem-Cmdlet auf den Stapel verschoben wurde `Push-Location` . Sie können einen Speicherort vom Standard Stapel oder von einem Stapel erstellen, den Sie mit einem `Push-Location` Befehl erstellen.

## BEISPIELE

### Beispiel 1: Ändern des aktuellen Speicher Orts

```
PS C:\> Pop-Location
```

Mit diesem Befehl wird der Speicherort in den Speicherort geändert, der dem aktuellen Stapel zuletzt hinzugefügt wurde.

### Beispiel 2: Ändern des aktuellen Speicher Orts in einem benannten Stapel

```
PS C:\> Pop-Location -StackName "Stack2"
```

Mit diesem Befehl wird der Speicherort in den Speicherort geändert, der dem Speicherstapel %%amp;quot;Stack2%%amp;quot; zuletzt hinzugefügt wurde.

Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).

### Beispiel 3: wechseln Zwischenstand Orten für verschiedene Anbieter

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

Diese Befehle verwenden die `Push-Location` `Pop-Location` Cmdlets und, um Zwischenstand Orten zu wechseln, die von verschiedenen PowerShell-Anbietern unterstützt werden. Die Befehle verwenden den `pushd` Alias für `Push-Location` und den `popd` Alias für `Pop-Location` .

Mit dem ersten Befehl wird der aktuelle Dateisystem Speicherort auf den Stapel verschoben und zum HKLM-Laufwerk gewechselt, das vom PowerShell-Registrierungs Anbieter unterstützt wird.

Mit dem zweiten Befehl wird der Registrierungs Speicherort auf den Stapel verschoben und zu einem Speicherort gewechselt, der vom PowerShell-Zertifikat Anbieter unterstützt wird.

Mit den letzten beiden Befehlen werden diese Speicherorte vom Stapel abgerufen. Der erste `popd` Befehl kehrt zum Registrierungs Laufwerk zurück, und der zweite Befehl kehrt zum Dateisystem Laufwerk zurück.

## PARAMETERS

### -PassThru

Übergibt ein Objekt, das den Speicherort darstellt, an die Pipeline. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### -Stackname

Gibt den Speicherstapel an, von dem der Speicherort abgerufen wird. Geben Sie einen Speicherstapelnamen ein.

Ohne diesen Parameter wird `Pop-Location` ein Speicherort vom aktuellen Speicher Stapel angezeigt. Standardmäßig ist der aktuelle Speicher Stapel der unbenannte Standard Speicherort Stapel, den PowerShell erstellt. Verwenden Sie den **stackname** -Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` . Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).

`Pop-Location` ein Speicherort kann nicht aus dem unbenannten Standard Stapel entfernt werden, es sei denn, er ist der aktuelle Speicher Stapel

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseTransaction

Schließt den Befehl in die aktive Transaktion ein. Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird. Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

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

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine, System. Management. Automation. PathInfo

Dieses Cmdlet generiert ein **System. Management. Automation. PathInfo** -Objekt, das den Speicherort darstellt, wenn Sie den **passthru** -Parameter angeben. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

PowerShell unterstützt mehrere Runspaces pro Prozess. Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.
Dies ist nicht identisch mit `[System.Environment]::CurrentDirectory` . Dieses Verhalten kann ein Problem sein, wenn Sie .NET-APIs aufrufen oder native Anwendungen ausführen, ohne explizite Verzeichnispfade bereitzustellen.

Auch wenn die Location-Cmdlets das aktuelle Prozess weite Verzeichnis festgelegt haben, können Sie nicht davon abhängen, weil es von einem anderen Runspace möglicherweise jederzeit geändert wird. Verwenden Sie die Location-Cmdlets zum Ausführen von Pfad basierten Vorgängen mit dem aktuellen Arbeitsverzeichnis, das für den aktuellen Runspace spezifisch ist.

Bei einem Stapel handelt es sich um eine Last-in-First-out-Liste, in der nur auf das zuletzt hinzugefügte Element zugegriffen werden kann. Sie fügen einem Stapel Elemente in der Reihenfolge hinzu, in der Sie sie verwenden. Anschließend rufen Sie sie zur Verwendung in der umgekehrten Reihenfolge auf. Mit PowerShell können Sie Anbieter Speicherorte in Speicherort Stapeln speichern.

Von PowerShell wird ein unbenannter Standard Speicher Stapel erstellt, und Sie können mehrere benannte Speicher Stapel erstellen. Wenn Sie keinen Stapelnamen angeben, verwendet PowerShell den aktuellen Speicher Stapel. Standardmäßig ist der unbenannte Standard Speicherort der aktuelle Speicher Stapel. Sie können das `Set-Location` Cmdlet jedoch verwenden, um den aktuellen Speicher Stapel zu ändern.

Verwenden Sie zum Verwalten von Speicherort Stapeln die PowerShell- `*-Location` Cmdlets wie folgt:

- Verwenden Sie das-Cmdlet, um einen Speicherort zu einem Speicherort Stapel hinzuzufügen `Push-Location` .

- Verwenden Sie das-Cmdlet, um einen Speicherort aus einem Speicherort Stapel zu erhalten `Pop-Location` .

- Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter des `Get-Location` Cmdlets.

- Um die Speicherorte in einem benannten Positions Stapel anzuzeigen, verwenden Sie den **stackname** -Parameter des `Get-Location` Cmdlets.

- Um einen neuen Speicherort Stapel zu erstellen, verwenden Sie den **stackname** -Parameter des `Push-Location` Cmdlets. Wenn Sie einen Stapel angeben, der nicht vorhanden ist, wird `Push-Location` der Stapel von erstellt.

- Verwenden Sie den **stackname** -Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .

Auf den unbenannten Standardspeicherstapel kann nur vollständig zugegriffen werden, wenn es sich dabei um den aktuellen Speicherstapel handelt.
Wenn Sie einen benannten Speicherort Stapel zum aktuellen Speicher Stapel machen, können Sie die `Push-Location` Cmdlets oder nicht mehr verwenden, `Pop-Location` um Elemente zum Standard Stapel hinzuzufügen oder daraus zu machen. Sie können auch das `Get-Location` Cmdlet verwenden, um die Speicherorte im unbenannten Stapel anzuzeigen. Um den unbenannten Stapel zum aktuellen Stapel zu machen, verwenden Sie den **stackname** -Parameter des `Set-Location` Cmdlets mit dem Wert `$Null` oder einer leeren Zeichenfolge ( `""` ).

Sie können auch auf den `Pop-Location` integrierten Alias verweisen `popd` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

`Pop-Location` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Get-Location](Get-Location.md)

[Push-Location](Push-Location.md)

[Set-Location](Set-Location.md)

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
