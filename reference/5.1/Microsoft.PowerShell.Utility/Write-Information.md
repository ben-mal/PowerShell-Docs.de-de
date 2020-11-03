---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-information?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Information
ms.openlocfilehash: e0f28393c95e2c0703c489d4691edcf883b4cb05
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224300"
---
# Write-Information

## ZUSAMMENFASSUNG

Gibt an, wie PowerShell Daten in einem Informationsdaten Strom für einen Befehl verarbeitet.

## SYNTAX

```
Write-Information [-MessageData] <Object> [[-Tags] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Write-Information` Cmdlet gibt an, wie PowerShell Daten in einem Informationsdaten Strom für einen Befehl verarbeitet.

Windows PowerShell 5,0 führt einen neuen, strukturierten Informationsdaten Strom ein. Mit diesem Stream können Sie strukturierte Daten zwischen einem Skript und seinen Aufrufern oder der Host Anwendung übertragen.
`Write-Information` ermöglicht es Ihnen, dem Stream eine Informations Meldung hinzuzufügen und anzugeben, wie PowerShell Daten in einem Informationsdaten Strom für einen Befehl verarbeitet. Informationsdaten Ströme funktionieren auch für `PowerShell.Streams` , Aufträge und geplante Aufgaben.

> [!NOTE]
> Der Informationsdaten Strom folgt nicht der Standard Konvention, dass seine Nachrichten mit "[Stream Name]:" vorangestellt werden. Dies wurde aus Gründen der Kürze und visuellen Sauberkeit bestimmt.

Der `$InformationPreference` Wert der Einstellungs Variablen bestimmt, ob die Nachricht, die Sie für bereitstellen, zu `Write-Information` dem erwarteten Zeitpunkt im Vorgang eines Skripts angezeigt wird. Da der Standardwert dieser Variablen Standard `SilentlyContinue` mäßig nicht angezeigt wird, werden keine Informationsmeldungen angezeigt. Wenn Sie den Wert von nicht ändern möchten `$InformationPreference` , können Sie seinen Wert überschreiben, indem Sie dem `InformationAction` Befehl den allgemeinen Parameter hinzufügen. Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) und [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

> [!NOTE]
> Ab Windows PowerShell 5,0 `Write-Host` ist ein Wrapper dafür, mit `Write-Information` `Write-Host` dem Sie die Ausgabe an den Informationsdaten Strom ausgeben können. Dies ermöglicht die **Erfassung** oder **Unterdrückung** von Daten, die mithilfe von geschrieben wurden, während die abwärts `Write-Host` Kompatibilität beibehalten wird. Weitere Informationen finden Sie unter [Write-Host](Write-Host.md) .

`Write-Information` ist auch eine unterstützte Workflow Aktivität in PowerShell 5. x.

## BEISPIELE

### Beispiel 1: Schreiben von Informationen für get-results

In diesem Beispiel wird eine Informations Meldung mit dem Namen "hat ihre Features!" angezeigt, nachdem der Befehl ausgeführt wurde, `Get-WindowsFeature` um alle Features zu finden, deren namens Wert mit "p" beginnt.
Da die- `$InformationPreference` Variable weiterhin auf den Standardwert festgelegt ist, `SilentlyContinue` fügen Sie den `InformationAction` -Parameter hinzu, um den Wert zu überschreiben `$InformationPreference` , und zeigen Sie die Meldung an. Der `InformationAction` Wert lautet "Continue", was bedeutet, dass die Meldung angezeigt wird, das Skript oder der Befehl jedoch fortgesetzt wird, wenn er noch nicht abgeschlossen ist.

```powershell
Get-WindowsFeature -Name p*
Write-Information -MessageData "Got your features!" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
Got your features!
```

### Beispiel 2: Schreiben von Informationen und Markieren dieser Informationen

In diesem Beispiel verwenden Sie, `Write-Information` um Benutzer darüber zu informieren, dass Sie einen weiteren Befehl ausführen müssen, nachdem Sie den aktuellen Befehl ausgeführt haben. Im Beispiel werden der Informations Meldung die taganweisungen hinzugefügt. Wenn Sie nach dem Ausführen dieses Befehls den Informationsdaten Strom nach Nachrichten mit markierten Anweisungen durchsuchen, wird die hier angegebene Meldung in den Ergebnissen angezeigt.

```powershell
$message = "To filter your results for PowerShell, pipe your results to the Where-Object cmdlet."
Get-WindowsFeature -Name p*
Write-Information -MessageData $message -Tags "Instructions" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
To filter your results for PowerShell, pipe your results to the Where-Object cmdlet.
```

### Beispiel 3: Schreiben von Informationen in eine Datei

```powershell
function Test-Info
{
    Get-Process P*
    Write-Information "Here you go"
}
Test-Info 6> Info.txt
```

## PARAMETERS

### -MessageData

Gibt eine Informations Meldung an, die Benutzern angezeigt werden soll, wenn Sie ein Skript oder einen Befehl ausführen. Schließen Sie die Informations Meldung in Anführungszeichen ein, um optimale Ergebnisse zu erzielen.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags

Gibt eine einfache Zeichenfolge an, mit der Sie Nachrichten, die Sie dem Informationsdaten Strom hinzugefügt haben, Sortieren und Filtern können `Write-Information` . Dieser Parameter funktioniert ähnlich wie der **Tags** -Parameter in `New-ModuleManifest` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

`Write-Information` akzeptiert keine weitergeleiteten Eingaben.

## AUSGABEN

### System. Management. Automation. informationrecord

## HINWEISE

## VERWANDTE LINKS

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)

[about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)

[Write-Output](Write-Output.md)
