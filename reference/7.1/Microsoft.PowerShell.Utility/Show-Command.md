---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/29/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Command
ms.openlocfilehash: 86253a8a0bd02a60980cc3655af7bb961acf88ac
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211764"
---
# Show-Command

## ZUSAMMENFASSUNG
Zeigt PowerShell-Befehls Informationen in einem grafischen Fenster an.

## SYNTAX

```
Show-Command [[-Name] <String>] [-Height <Double>] [-Width <Double>] [-NoCommonParameter]
 [-ErrorPopup] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Show-Command` Cmdlet können Sie einen PowerShell-Befehl in einem Befehlsfenster erstellen. Mithilfe der Funktionen des Befehlsfensters können Sie den Befehl ausführen oder den Befehl an Sie zurückgeben lassen.

`Show-Command` ist ein sehr nützliches Schulungs-und Lerntool. `Show-Command` funktioniert an allen Befehls Typen, einschließlich Cmdlets, Funktionen, Workflows und CIM-Befehlen.

Ohne Parameter `Show-Command` zeigt ein Befehlsfenster an, in dem alle verfügbaren Befehle in allen installierten Modulen aufgelistet sind. Um die Befehle in einem Modul zu suchen, wählen Sie das Modul aus der Dropdownliste „Module“ aus. Klicken Sie zum Auswählen eines Befehls auf den Befehlsnamen.

Um das Befehlsfenster zu verwenden, wählen Sie einen Befehl aus, indem Sie entweder den Namen verwenden oder indem Sie in der Liste **Befehle** auf den Befehlsnamen klicken. Jeder Parametersatz wird auf einer separaten Registerkarte angezeigt. Sternchen geben die erforderlichen Parameter an. Um Werte für einen Parameter einzugeben, geben Sie den Wert in das Textfeld ein, oder wählen Sie den Wert aus der Dropdownliste aus. Um einen Switch-Parameter hinzuzufügen, aktivieren Sie das Parameter-Kontrollkästchen.

Sobald Sie bereit sind, können Sie auf **Copy** klicken, um den Befehl, den Sie erstellt haben, in die Zwischenablage zu kopieren, oder klicken Sie auf **Run** , um den Befehl auszuführen. Sie können auch den **passthru** -Parameter verwenden, um den Befehl an das Host Programm zurückzugeben, z. b. die PowerShell-Konsole. Um die Befehls Auswahl abzubrechen und zur Ansicht zurückzukehren, in der alle Befehle angezeigt werden, drücken Sie STRG, und klicken Sie auf den ausgewählten Befehl.

In der PowerShell Integrated Scripting Environment (ISE) `Show-Command` wird standardmäßig eine Variation des Fensters angezeigt. Weitere Informationen zur Verwendung dieses Befehls Fensters finden Sie in den Hilfe Themen zur PowerShell ISE.

Dieses Cmdlet wurde in PowerShell 7 erneut eingeführt. 

Da dieses Cmdlet eine Benutzeroberfläche erfordert, funktioniert es nicht unter Windows Server Core oder Windows Nano Server. Dieses Cmdlet ist nur auf Windows-Systemen verfügbar, die den Windows-Desktop unterstützen.

## BEISPIELE

### Beispiel 1: Öffnen des Befehls Fensters

In diesem Beispiel wird die Standardansicht des `Show-Command` Fensters angezeigt. Das Fenster " **Befehle** " zeigt eine Liste aller Befehle in allen Modulen an, die auf dem Computer installiert sind.

```powershell
Show-Command
```

### Beispiel 2: Öffnen eines Cmdlets im Fenster "Befehle"

In diesem Beispiel wird das- `Invoke-Command` Cmdlet im **Befehls** Fenster angezeigt. Mit dieser Anzeige können Sie Befehle ausführen `Invoke-Command` .

```powershell
Show-Command -Name "Invoke-Command"
```

### Beispiel 3: Öffnen eines Cmdlets mit angegebenen Parametern

Mit diesem Befehl wird ein `Show-Command` Fenster für das `Connect-PSSession` Cmdlet geöffnet.

```powershell
Show-Command -Name "Connect-PSSession" -Height 700 -Width 1000 -ErrorPopup
```

Mit den Parametern **height** und **Width** wird die Dimension des Befehls Fensters angegeben. Der **errorpopup** -Parameter zeigt das Fehler Befehlsfenster an.

Wenn Sie auf **Ausführen** klicken, wird der `Connect-PSSession` Befehl genauso ausgeführt, als würden Sie den `Connect-PSSession` Befehl an der Befehlszeile eingeben.

### Beispiel 4: Angeben neuer Standardparameter Werte für ein Cmdlet

In diesem Beispiel wird die `$PSDefaultParameterValues` Automatische Variable verwendet, um neue Standardwerte für die Parameter " **height** ", " **Width** " und " **errorpopup** " des `Show-Command` Cmdlets festzulegen.

```powershell
$PSDefaultParameterValues = @{
    "Show-Command:Height" = 700
    "Show-Command:Width" = 1000
    "Show-Command:ErrorPopup" = $True
}
```

Wenn Sie nun einen `Show-Command` Befehl ausführen, werden die neuen Standardwerte automatisch angewendet. Um diese Standardwerte in jeder PowerShell-Sitzung zu verwenden, fügen Sie die `$PSDefaultParameterValues` Variable Ihrem PowerShell-Profil hinzu. Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) und [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md).

### Beispiel 5: Senden der Ausgabe an eine Rasteransicht

Dieser Befehl zeigt, wie die `Show-Command` `Out-GridView` Cmdlets und verwendet werden.

```powershell
Show-Command Get-ChildItem | Out-GridView
```

Der Befehl verwendet das `Show-Command` Cmdlet zum Öffnen eines Befehls Fensters für das `Get-ChildItem` Cmdlet.
Wenn Sie auf die Schaltfläche Ausführen klicken, wird der Befehl **ausgeführt** , `Get-ChildItem` und die Ausgabe wird generiert. Der Pipeline Operator (|) sendet die Ausgabe des `Get-ChildItem` Befehls an das `Out-GridView` Cmdlet, das die `Get-ChildItem` Ausgabe in einem interaktiven Fenster anzeigt.

### Beispiel 6: Anzeigen eines Befehls, den Sie im Fenster "Befehle" erstellen

Dieses Beispiel zeigt den Befehl, den Sie im- `Show-Command` Fenster erstellt haben. Der Befehl verwendet den **passthru** -Parameter, der die `Show-Command` Ergebnisse in einer Zeichenfolge zurückgibt.

```powershell
Show-Command -PassThru
```

```Output
Get-EventLog -LogName "Windows PowerShell" -Newest 5
```

Wenn Sie z. b. das `Show-Command` Fenster verwenden, um einen Befehl zu erstellen, mit `Get-EventLog` dem die fünf neuesten Ereignisse im Windows PowerShell-Ereignisprotokoll abgerufen werden, und dann auf **OK** klicken, gibt der Befehl die oben gezeigte Ausgabe zurück. Das Anzeigen der Befehls Zeichenfolge hilft Ihnen beim Erlernen von PowerShell.

### Beispiel 7: Speichern eines Befehls in einer Variablen

In diesem Beispiel wird gezeigt, wie Sie die Befehls Zeichenfolge ausführen können, die Sie erhalten, wenn Sie den **passthru** -Parameter des `Show-Command` Cmdlets verwenden. Mit dieser Strategie können Sie den Befehl anzeigen und ihn verwenden.

```powershell
$C = Show-Command -PassThru
$C
Invoke-Expression $C
```

```Output
Get-EventLog -LogName "PowerShell" -Newest 5

Index Time          EntryType   Source                 InstanceID Message
----- ----          ---------   ------                 ---------- -------
11520 Dec 16 16:37  Information Windows PowerShell            400 Engine state is changed from None to Available...
11519 Dec 16 16:37  Information Windows PowerShell            600 Provider "Variable" is Started. ...
11518 Dec 16 16:37  Information Windows PowerShell            600 Provider "Registry" is Started. ...
11517 Dec 16 16:37  Information Windows PowerShell            600 Provider "Function" is Started. ...
11516 Dec 16 16:37  Information Windows PowerShell            600 Provider "FileSystem" is Started. ...
```

Der erste Befehl verwendet den **passthru** -Parameter des `Show-Command` Cmdlets und speichert die Ergebnisse des Befehls in der `$C` Variablen. In diesem Fall verwenden wir das `Show-Command` Fenster, um einen Befehl zu erstellen `Get-EventLog` , mit dem die fünf neuesten Ereignisse im Windows PowerShell-Ereignisprotokoll abgerufen werden. Wenn Sie auf **OK** klicken, wird `Show-Command` die Befehls Zeichenfolge zurückgegeben, die in der Variablen gespeichert wird `$C` .

### Beispiel 8: Speichern der Ausgabe eines Befehls in einer Variablen

In diesem Beispiel wird der **errorpopup** -Parameter verwendet, um die Ausgabe eines Befehls in einer Variablen zu speichern.

```powershell
$P = Show-Command Get-Process -ErrorPopup
$P
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    473      33    94096     112532   709     2.06   4492 powershell
```

Zusätzlich zum Anzeigen von Fehlern in einem Fenster gibt **ErrorPopup** die Ausgabe des Befehls an den aktuellen Befehl zurück, anstatt einen neuen Befehl zu erstellen. Wenn Sie diesen Befehl ausführen, wird das `Show-Command` Fenster geöffnet. Mithilfe der Funktionen des Fensters können Sie Parameterwerte festlegen. Um den Befehl auszuführen, klicken Sie im-Fenster auf die Schaltfläche **Ausführen** `Show-Command` .

## PARAMETERS

### -Errorpopup

Gibt an, dass das Cmdlet neben der Anzeige in der Befehlszeile auch Fehler in einem Popup Fenster anzeigt. Wenn ein in einem `Show-Command` Fenster ausgelaufter Befehl einen Fehler generiert, wird der Fehler standardmäßig nur in der Befehlszeile angezeigt.

Wenn Sie den Befehl ausführen (mit der Schaltfläche " **Ausführen** " im `Show-Command` Fenster), gibt der **errorpopup** -Parameter die Befehls Ergebnisse an den aktuellen Befehl zurück, anstatt den Befehl auszuführen und seine Ausgabe an einen neuen Befehl zurückzugeben. Mit dieser Funktion können Sie die Ergebnisse des Befehls in einer Variablen speichern.

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

### -Höhe

Gibt die Höhe des `Show-Command` Fensters in Pixel an. Geben Sie einen Wert zwischen 300 und der Anzahl der Pixel in der Bildschirmauflösung ein. Wenn der Wert zu groß ist, um das Befehlsfenster auf dem Bildschirm anzuzeigen, `Show-Command` generiert einen Fehler. Die Standardhöhe ist 600 Pixel. Für einen `Show-Command` Befehl, der den **Name** -Parameter enthält, beträgt die Standardhöhe 300 Pixel.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Zeigt ein Befehlsfenster für den angegebenen Befehl an. Geben Sie den Namen eines Befehls ein, z. b. den Namen eines Cmdlets, einer Funktion oder eines CIM-Befehls. Wenn Sie diesen Parameter weglassen, wird `Show-Command` ein Befehlsfenster angezeigt, in dem alle PowerShell-Befehle in allen auf dem Computer installierten Modulen aufgelistet sind.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CommandName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nocommonparameter

Gibt an, dass dieses Cmdlet den Abschnitt Allgemeine Parameter der Befehls Anzeige auslässt. Standardmäßig werden die allgemeinen Parameter in einem erweiterbaren Abschnitt unten im Befehlsfenster angezeigt.

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

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert. Um die Befehls Zeichenfolge auszuführen, kopieren Sie Sie in die Eingabeaufforderung, oder speichern Sie Sie in einer Variablen, und verwenden Sie das `Invoke-Expression` Cmdlet, um die Zeichenfolge in der Variablen auszuführen.

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

### -Breite

Gibt die Breite des `Show-Command` Fensters in Pixel an. Geben Sie einen Wert zwischen 300 und der Anzahl der Pixel in der Bildschirmauflösung ein. Wenn der Wert zu groß ist, um das Befehlsfenster auf dem Bildschirm anzuzeigen, `Show-Command` generiert einen Fehler. Die Standardbreite ist 300 Pixel.

```yaml
Type: System.Double
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

Eingaben können nicht an übergeben werden `Show-Command` .

## AUSGABEN

### None, System. String, System. Object

Wenn Sie den **passthru** -Parameter verwenden, `Show-Command` gibt eine Befehls Zeichenfolge zurück. Wenn Sie den **errorpopup** -Parameter verwenden, wird `Show-Command` die Befehlsausgabe (beliebiges Objekt) zurückgegeben. Andernfalls `Show-Command` generiert keine Ausgabe.

## HINWEISE

`Show-Command` funktioniert nicht in Remote Sitzungen.

## VERWANDTE LINKS

