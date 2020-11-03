---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/test-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DscConfiguration
ms.openlocfilehash: 25c8bc61976ce3940e0b9bd949fa3ee60728450d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213575"
---
# Test-DscConfiguration

## ZUSAMMENFASSUNG
Testet, ob die tatsächliche Konfiguration auf den Knoten mit der gewünschten Konfiguration übereinstimmt.

## SYNTAX

### Computernameset (Standard)

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Detailed] [<CommonParameters>]
```

### Computernameandpathset

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Path] <String> [<CommonParameters>]
```

### Computernameandreferenceconfigurationset

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] -ReferenceConfiguration <String> [<CommonParameters>]
```

### Cimsessionandpathset

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Path] <String>
 [<CommonParameters>]
```

### Cimsessionandreferenceconfigurationset

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob]
 -ReferenceConfiguration <String> [<CommonParameters>]
```

### Cimsessionset

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Detailed]
 [<CommonParameters>]
```

## DESCRIPTION
Das Cmdlet **Test-DscConfiguration** testet, ob die tatsächliche Konfiguration auf den Knoten mit der gewünschten Konfiguration übereinstimmt.
Geben Sie an, für welche Computerkonfigurationen mithilfe von Computernamen oder Common Information Model (CIM)-Sitzungen getestet werden sollen.
Wenn Sie keinen Zielcomputer angeben, testet das Cmdlet die Konfiguration des lokalen Computers.

Wenn die gewünschte und die tatsächliche Konfiguration entsprechen, gibt das Cmdlet den Zeichen folgen Wert "true" zurück.
Andernfalls wird der Zeichen folgen Wert "false" zurückgegeben.

## BEISPIELE

### Beispiel 1: Test Konfiguration für den lokalen Computer

```
PS C:\> Test-DscConfiguration
```

Dieser Befehl testet die Konfiguration für den lokalen Computer.

### Beispiel 2: Test Konfiguration für einen angegebenen Computer

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Test-DscConfiguration -CimSession $Session
```

In diesem Beispiel wird die Konfiguration von einem Computer von einer CIM-Sitzung angegebenen Computer getestet.
Das Beispiel erstellt eine CIM-Sitzung für einen Computer namens Server01 zur Verwendung mit dem Cmdlet.
Erstellen Sie alternativ ein Array von CIM-Sitzungen, um das Cmdlet für mehrere angegebene Computer anzuwenden.

Der erste Befehl erstellt eine CIM-Sitzung mithilfe des Cmdlets **New-CimSession** und speichert dann das **CimSession** -Objekt in der Variable $Session.
Der Befehl fordert Sie zur Eingabe eines Kennworts auf.
Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.

Der zweite Befehl teste die Konfiguration für die Computer, die durch die **CimSession** -Objekte identifiziert werden, die in der Variable $Session gespeichert sind, in diesem Fall der Computer namens Server01.

### Beispiel 3: Testen von Konfigurationen mit detaillierten Ergebnissen

```
PS C:\> Test-DscConfiguration -ComputerName "Server01", "Server02", "Server03" -Detailed
```

Dieser Befehl testet Konfigurationen für eine Reihe von Computern, die mit dem Parameter " *Computername* " angegeben wurden, und gibt ausführliche Informationen zurück, die den Gesamtstatus, Ressourcen im gewünschten Zustand, Ressourcen, die sich nicht im gewünschten Zustand befinden, und den Computernamen enthalten.

### Beispiel 4: in einem Ordner angegebene Test Konfigurationen

```
PS C:\> Test-DscConfiguration -Path "C:\Dsc\Configurations"
```

Mit diesem Befehl werden Konfigurationen getestet, die in einem durch den *path* -Parameter angegebenen Ordner definiert sind.
Die Konfigurationen werden für eine Gruppe von Computern getestet, die jeweils durch den Dateinamen der Konfigurationsdatei identifiziert werden.

### Beispiel 5: in einer Datei angegebene Test Konfigurationen

```
PS C:\> Test-DscConfiguration -ReferenceConfiguration "C:\Dsc\Configurations\WebServer.mof" -ComputerName "Server01", "Server02", "Server03"
```

Mit diesem Befehl wird eine in einer Datei definierte Konfiguration für eine Gruppe von Computern getestet, die durch den *Computername* -Parameter angegeben werden.

## PARAMETERS

### -AsJob
Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.

Wenn Sie den *AsJob* -Parameter angeben, gibt der Befehl ein Objekt zurück, das den Auftrag darstellt, und zeigt dann die Eingabeaufforderung an.
Sie können die Arbeit in der Sitzung fortsetzen, bis der Auftrag abgeschlossen ist.
Der Auftrag wird auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben.
Um den Auftrag zu verwalten, verwenden Sie die Job-Cmdlets.
Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.

Um diesen Parameter verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein. unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie Windows PowerShell mit der Option als Administrator ausführen öffnen.
Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).

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

### -CimSession
Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.
Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".
Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndReferenceConfigurationSet, CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Gibt ein Array von Computernamen an, auf denen dieses Cmdlet die Konfiguration testet.
Mit dem-Cmdlet wird das Konfigurations Dokument an dem durch den *path* -Parameter angegebenen Speicherort auf diese Computer getestet.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Gibt einen Benutzernamen und ein Kennwort als ein **PSCredential** -Objekt für den Zielcomputer an.
Zum Abrufen eines **PSCredential** -Objekts verwenden Sie das Get-Credential-Cmdlet.
Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Get-Credential`.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Detailed
Gibt an, dass dieses Cmdlet ein detailliertes Ergebnis des Vergleichs des Konfigurations Dokuments mit dem gewünschten Zustand der Knoten zurückgibt.
Das Ergebnis umfasst Informationen wie den Gesamtstatus, Ressourcen, die sich im gewünschten Zustand befinden, Ressourcen, die sich nicht im gewünschten Zustand befinden, und den Computernamen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameSet, CimSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Gibt den Pfad eines Ordners an, der Konfigurations Dokument Dateien enthält.
Das Cmdlet testet die Konfiguration mit dem gewünschten Zustand der Computer, die durch den Parameter " *Computername* " oder " *cimsession* " angegeben werden.

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Referenceconfiguration
Gibt den Pfad der Konfigurations Dokument Datei an.
Dieses Cmdlet testet die Konfiguration mit dem tatsächlichen Status der Computer, die durch den Parameter " *Computername* " oder " *cimsession* " angegeben werden.

```yaml
Type: System.String
Parameter Sets: ComputerNameAndReferenceConfigurationSet, CimSessionAndReferenceConfigurationSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.
Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.
Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.

```yaml
Type: System.Int32
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

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[Windows PowerShell DSC – Übersicht](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)
