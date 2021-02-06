---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-History
ms.openlocfilehash: d2c0abb0e6742de3e316fe964d5945375591ef4d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598394"
---
# Add-History

## ZUSAMMENFASSUNG
Fügt Einträge an den Sitzungsverlauf an.

## SYNTAX

```
Add-History [[-InputObject] <PSObject[]>] [-Passthru] [<CommonParameters>]
```

## DESCRIPTION

Das- `Add-History` Cmdlet fügt Einträge am Ende des Sitzungs Verlaufs hinzu, d. h. die Liste der Befehle, die während der aktuellen Sitzung eingegeben wurden.

Der Sitzungsverlauf ist eine Liste der Befehle, die während der Sitzung eingegeben wurden. Der Sitzungsverlauf stellt die Reihenfolge der Ausführung, den Status und die Start- und Endzeiten des Befehls dar. Wenn Sie jeden Befehl eingeben, wird er von PowerShell dem Verlauf hinzugefügt, damit Sie ihn wieder verwenden können. Weitere Informationen zum Sitzungsverlauf finden Sie unter [about_History](About/about_History.md).

Der Sitzungsverlauf wird getrennt von dem vom **psread Line** -Modul verwalteten Verlauf verwaltet.
Beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird. Dieses Cmdlet funktioniert nur mit dem Sitzungsverlauf. Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

Sie können das `Get-History` Cmdlet verwenden, um die Befehle zu erhalten und Sie an zu übergeben `Add-History` , oder Sie können die Befehle in eine CSV-oder XML-Datei exportieren, die Befehle importieren und die importierte Datei an übergeben `Add-History` . Sie können dieses Cmdlet verwenden, um bestimmte Befehle zum Verlauf hinzuzufügen oder eine einzelne Verlaufsdatei zu erstellen, die Befehle aus mehreren Sitzungen enthält.

## BEISPIELE

### Beispiel 1: Hinzufügen von Befehlen zum Verlauf einer anderen Sitzung

In diesem Beispiel werden die in einer PowerShell-Sitzung eingegebenen Befehle dem Verlauf einer anderen PowerShell-Sitzung hinzugefügt.

```powershell
Get-History | Export-Csv c:\testing\history.csv -IncludeTypeInformation
Import-Csv c:\testing\history.csv | Add-History
```

Der erste Befehl ruft die Objekte ab, die die Befehle im Verlauf darstellen, und exportiert Sie in die `History.csv` Datei.

Der zweite Befehl wird in der Befehlszeile einer anderen Sitzung eingegeben. Er verwendet das `Import-Csv` Cmdlet, um die Objekte in die `History.csv` Datei zu importieren. Der Pipeline Operator ( `|` ) übergibt die Objekte an das `Add-History` Cmdlet, wodurch die Objekte, die die Befehle in der `History.csv` Datei darstellen, dem aktuellen Sitzungsverlauf hinzugefügt werden.

### Beispiel 2: Importieren und Ausführen von Befehlen

In diesem Beispiel werden Befehle aus der `History.xml` Datei importiert, dem aktuellen Sitzungsverlauf hinzugefügt und dann die Befehle im kombinierten Verlauf ausgeführt.

```powershell
Import-Clixml c:\temp\history.xml | Add-History -PassThru | ForEach-Object -Process {Invoke-History}
```

Der erste Befehl verwendet das `Import-Clixml` Cmdlet, um einen Befehlsverlauf zu importieren, der in die Datei exportiert wurde `History.xml` . Der Pipeline Operator übergibt die Befehle an das `Add-History` Cmdlet, wodurch die Befehle dem aktuellen Sitzungsverlauf hinzugefügt werden. Der **passthru** -Parameter übergibt die Objekte, die die hinzugefügten Befehle darstellen, in der Pipeline.

Der Befehl verwendet dann das `ForEach-Object` Cmdlet, um den `Invoke-History` Befehl auf jeden der Befehle im kombinierten Verlauf anzuwenden. Der `Invoke-History` Befehl wird als Skriptblock formatiert, der in geschweiften Klammern () eingeschlossen ist `{}` , wie dies für den **Process** -Parameter des `ForEach-Object` Cmdlets erforderlich ist.

### Beispiel 3: Hinzufügen von Befehlen im Verlauf am Ende des Verlaufs

In diesem Beispiel werden die ersten fünf Befehle im Verlauf am Ende der Verlaufs Liste hinzugefügt.

```powershell
Get-History -Id 5 -Count 5 | Add-History
```

Mit dem- `Get-History` Cmdlet werden die fünf Befehle abgerufen, die mit dem Befehl 5 enden. Der Pipeline Operator übergibt sie an das- `Add-History` Cmdlet, das Sie an den aktuellen Verlauf anfügt. Der `Add-History` Befehl enthält keine Parameter, aber PowerShell verknüpft die Objekte, die durch die Pipeline übergeben werden, mit dem **Inputobject** -Parameter von `Add-History` .

### Beispiel 4: Hinzufügen von Befehlen in einer CSV-Datei zum aktuellen Verlauf

In diesem Beispiel werden die Befehle in der `History.csv` Datei dem aktuellen Sitzungsverlauf hinzugefügt.

```powershell
$a = Import-Csv c:\testing\history.csv
Add-History -InputObject $a -PassThru
```

Mit dem `Import-Csv` -Cmdlet werden die Befehle in der `History.csv` Datei importiert und der Inhalt in der Variablen gespeichert `$a` .

Der zweite Befehl verwendet das `Add-History` Cmdlet, um die Befehle aus `History.csv` dem aktuellen Sitzungsverlauf hinzuzufügen. Er verwendet den **Inputobject** -Parameter, um die Variable anzugeben, `$a` und den **passthru** -Parameter, um ein Objekt zu generieren, das in der Befehlszeile angezeigt werden soll. Ohne den **passthru** -Parameter `Add-History` generiert das Cmdlet keine Ausgabe.

### Beispiel 5: Hinzufügen von Befehlen in einer XML-Datei zum aktuellen Verlauf

In diesem Beispiel werden die Befehle in der `history.xml` Datei dem aktuellen Sitzungsverlauf hinzugefügt.

```powershell
Add-History -InputObject (Import-Clixml c:\temp\history.xml)
```

Der **Inputobject** -Parameter übergibt die Ergebnisse des Befehls in Klammern an das `Add-History` Cmdlet. Der Befehl in Klammern, der zuerst ausgeführt wird, importiert die `history.xml` Datei in PowerShell. Das `Add-History` Cmdlet fügt dann die Befehle in der Datei dem Sitzungsverlauf hinzu.

## PARAMETERS

### -InputObject

Gibt ein Array von Einträgen an, die dem Verlauf als **historyinfo** -Objekt zum Sitzungsverlauf hinzugefügt werden sollen.
Sie können diesen Parameter verwenden, um ein **historyinfo** -Objekt, z. b. diejenigen, die von `Get-History` den `Import-Clixml` Cmdlets, oder zurückgegeben werden `Import-Csv` , an zu senden `Add-History` .

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Passthru

Gibt an, dass dieses Cmdlet ein **historyinfo** -Objekt für jeden Verlaufs Eintrag zurückgibt. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### Microsoft. PowerShell. Commands. historyinfo

Sie können ein **historyinfo** -Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### None oder Microsoft. PowerShell. Commands. historyinfo

Dieses Cmdlet gibt ein **historyinfo** -Objekt zurück, wenn Sie den **passthru** -Parameter angeben. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

Der Sitzungsverlauf ist eine Liste der Befehle, die während der Sitzung eingegeben wurden, mit der ID. Der Sitzungsverlauf stellt die Reihenfolge der Ausführung, den Status und die Start- und Endzeiten des Befehls dar. Wenn Sie jeden Befehl eingeben, wird er von PowerShell dem Verlauf hinzugefügt, damit Sie ihn wieder verwenden können. Weitere Informationen zum Sitzungsverlauf finden Sie unter [about_History](About/about_History.md).

Verwenden Sie zum Angeben der Befehle, die dem Verlauf hinzugefügt werden sollen, den **InputObject**-Parameter. Der `Add-History` Befehl akzeptiert nur **historyinfo** -Objekte, z. b. die, die für jeden Befehl vom `Get-History` Cmdlet zurückgegeben werden. Sie können ihm keinen Pfad und Dateinamen bzw. eine Befehlsliste übergeben.

Sie können den **Inputobject** -Parameter verwenden, um eine Datei mit **historyinfo** -Objekten an zu übergeben `Add-History` . Exportieren Sie dazu die Ergebnisse eines `Get-History` Befehls mithilfe des `Export-Csv` Cmdlets oder in eine Datei, `Export-Clixml` und importieren Sie die Datei dann mithilfe der `Import-Csv` `Import-Clixml` Cmdlets oder. Anschließend können Sie die Datei importierter **historyinfo** -Objekte `Add-History` über eine Pipeline oder eine Variable an übergeben. Weitere Informationen finden Sie in den Beispielen.

Die Datei der **historyinfo** -Objekte, die Sie an das `Add-History` Cmdlet übergeben, muss die Typinformationen, Spaltenüberschriften und alle Eigenschaften der **historyinfo** -Objekte enthalten. Wenn Sie beabsichtigen, die Objekte zurück an zu übergeben `Add-History` , verwenden Sie nicht den **notypeinformation** -Parameter des `Export-Csv` Cmdlets, und löschen Sie nicht die Typinformationen, Spaltenüberschriften oder Felder in der Datei.

Um den Sitzungsverlauf zu ändern, exportieren Sie die Sitzung in eine CSV-oder XML-Datei, ändern Sie die Datei, importieren Sie die Datei, und verwenden `Add-History` Sie Sie, um Sie an den aktuellen Sitzungsverlauf anzufügen.

## VERWANDTE LINKS

[Clear-History](Clear-History.md)

[Get-History](Get-History.md)

[Invoke-History](Invoke-History.md)

[about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)

[Get-psread lineoption](/powershell/module/psreadline/get-psreadlineoption)

[Set-psread lineoption](/powershell/module/psreadline/set-psreadlineoption)

