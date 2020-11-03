---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-modulemember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ModuleMember
ms.openlocfilehash: a8f059a5f7ae36415054dd94f87a1224d64c2cbf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212063"
---
# Export-ModuleMember

## ZUSAMMENFASSUNG
Gibt die Modulelemente an, die exportiert werden.

## SYNTAX

```
Export-ModuleMember [[-Function] <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION

Das **Export-modulemember** -Cmdlet gibt die Modul Elemente an, die aus einer Skript Modul Datei (. psm1) exportiert werden, oder aus einem dynamischen Modul, das mit dem Cmdlet "New-Module" erstellt wurde.
Zu den Modulmembern gehören Cmdlets, Funktionen, Variablen und Aliase.
Dieses Cmdlet kann nur in einer Skriptmoduldatei oder einem dynamischen Modul verwendet werden.

Wenn ein Skript Modul keinen **Export-modulemember** -Befehl enthält, werden die Funktionen und Aliase im Skript Modul exportiert, die Variablen jedoch nicht.
Wenn ein Skript Modul **Export-modulemember** -Befehle enthält, werden nur die Elemente exportiert, die in den **Export-modulemember** -Befehlen angegeben sind.
Sie können **Export-modulemember** auch verwenden, um Member, die das Skript Modul aus anderen Modulen importiert, zu unterdrücken oder zu exportieren.

Ein **Export-modulemember** -Befehl ist optional, aber es handelt sich um eine bewährte Vorgehensweise.
Auch wenn der Befehl die Standardwerte bestätigt, wird die Absicht des Modulautors veranschaulicht.

## BEISPIELE

### Beispiel 1: Exportieren von Funktionen und Aliasen in einem Skript Modul

```powershell
Export-ModuleMember -Function * -Alias *
```

Dieser Befehl exportiert alle Funktionen und Aliase, die im Skript Modul definiert sind.

### Beispiel 2: Exportieren spezifischer Aliase und Funktionen

```powershell
Export-ModuleMember -Function Get-Test, New-Test, Start-Test -Alias gtt, ntt, stt
```

Dieser Befehl exportiert die drei Aliase und drei Funktionen, die im Skriptmodul definiert sind.

Verwenden Sie dieses Befehlsformat, um Namen der Modulelemente anzugeben.

### Beispiel 3: Exportieren von keinen Membern

```powershell
Export-ModuleMember
```

Dieser Befehl gibt an, dass keine im Skriptmodul definierten Elemente exportiert werden.

Dieser Befehl verhindert, dass Modulelemente exportiert werden, blendet die Elemente aber nicht aus.
Die Benutzer können Modulelemente lesen und kopieren oder den Aufrufoperator (&) verwenden, um Modulelemente aufzurufen, die nicht exportiert werden.

### Beispiel 4: Exportieren einer bestimmten Variablen

```powershell
Export-ModuleMember -Variable increment
```

Dieser Befehl exportiert nur die $increment-Variable aus dem Skriptmodul.
Keine anderen Elemente werden exportiert.

Wenn Sie eine Variable exportieren möchten, zusätzlich zum Exportieren der Funktionen in einem Modul, muss der **Export-modulemember** -Befehl die Namen aller Funktionen und den Namen der Variablen enthalten.

### Beispiel 5: mehrere Export Befehle

```powershell
# From TestModule.psm1
Function New-Test
{
    Write-Output 'I am New-Test function'
}
Export-ModuleMember -Function New-Test

function Validate-Test
{
    Write-Output 'I am Validate-Test function'
}
function Start-Test
{
    Write-Output 'I am Start-Test function'
}
Set-Alias stt Start-Test
Export-ModuleMember -Function Start-Test -Alias stt
```

Diese Befehle zeigen, wie mehrere **Export-modulemember** -Befehle in einer Skript Modul Datei (. psm1) interpretiert werden.

Diese Befehle erstellen drei Funktionen und einen Alias und exportieren sie dann.

Ohne die **Export-modulemember** -Befehle würden alle drei Funktionen und der Alias exportiert werden.
Mit den **Export-modulemember** -Befehlen werden nur die Funktionen **New-Test** und **Start-Test** und der STT-Alias exportiert.

### Beispiel 6: Exportieren von Membern in einem dynamischen Modul

```powershell
New-Module -Script {function SayHello {"Hello!"}; Set-Alias Hi SayHello; Export-ModuleMember -Alias Hi -Function SayHello}
```

Dieser Befehl zeigt, wie Export-ModuleMember in einem dynamischen Modul verwendet wird, das mit dem **New-Module-** Cmdlet erstellt wird.

In diesem Beispiel wird **Export-modulemember** zum Exportieren des HI-Alias und der Funktion " **sayHello** " im dynamischen Modul verwendet.

### Beispiel 7: Deklarieren und Exportieren einer Funktion in einem einzelnen Befehl

```powershell
# From TestModule.psm1
function Export
{
  param (
    [Parameter(Mandatory=$true)]
    [ValidateSet("function","variable")]
    $Type,
    [Parameter(Mandatory=$true)]
    $Name,
    [Parameter(Mandatory=$true)]
    $Value
    )

    if ($Type -eq "function")
    {
        Set-item "function:script:$Name" $Value
        Export-ModuleMember $Name
    }
    else
    {
    Set-Variable -scope Script $Name $Value
    Export-ModuleMember -variable $Name
    }
}

Export function New-Test {Write-Output 'I am New-Test function'}
function helper {Write-Output 'I am helper function'}

Export variable Interval 0
$Interval = 2
```

Dieses Beispiel enthält eine Funktion namens " **Export** ", die eine Funktion deklariert oder eine Variable erstellt und dann einen `Export-ModuleMember` Befehl für die Funktion oder Variable schreibt.
Auf diese Weise können Sie eine Funktion oder Variable in einem einzigen Befehl deklarieren und exportieren.

Wenn Sie die **Export** -Funktion verwenden möchten, fügen Sie Sie in das Skript Modul ein.
Um eine Funktion zu exportieren, geben Sie `Export` vor dem **Function** -Schlüsselwort ein.

Um eine Variable zu exportieren, verwenden Sie folgendes Format, um die Variable zu deklarieren und ihren Wert festzulegen:

`Export variable <variable-name> <value>`

Die Befehle im Beispiel zeigen das richtige Format.
In diesem Beispiel werden nur die **New-Test-** Funktion und die $Interval-Variable exportiert.

## PARAMETERS

### -Alias

Gibt die Aliase an, die aus der Skriptmoduldatei exportiert werden.
Geben Sie die Aliasnamen ein.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Cmdlet

Gibt die Cmdlets an, die aus der Skriptmoduldatei exportiert werden.
Geben Sie die Cmdlet-Namen ein.
Platzhalterzeichen sind zulässig.

Sie können keine Cmdlets in einer Skriptmoduldatei erstellen, aber Sie können Cmdlets aus einem binären Modul in ein Skriptmodul importieren und dann erneut aus dem Skriptmodul exportieren.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Funktion

Gibt die Funktionen an, die aus der Skriptmoduldatei exportiert werden.
Geben Sie die Funktionsnamen ein.
Platzhalterzeichen sind zulässig.
Sie können auch Funktionsnamen-Zeichen folgen an **Export-modulemember** übergeben.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Variable

Gibt die Variablen an, die aus der Skriptmoduldatei exportiert werden.
Geben Sie die Variablennamen ohne Dollarzeichen ein.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können Funktionsnamen-Zeichen folgen an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Um ein Element aus der Liste der exportierten Elemente auszuschließen, fügen Sie einen **Export-modulemember** -Befehl hinzu, der alle anderen Member auflistet, aber das Element auslässt, das Sie ausschließen möchten.

## VERWANDTE LINKS

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

[Remove-Module](Remove-Module.md)

[about_Modules](About/about_Modules.md)
