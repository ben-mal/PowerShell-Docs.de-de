---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: c6d6d305b283522215d43b7339683b1617a85804
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600908"
---
# Test-PSSessionConfigurationFile

## ZUSAMMENFASSUNG
Überprüft die Schlüssel und Werte in einer Sitzungskonfigurationsdatei.

## SYNTAX

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

Mit diesem Cmdlet wird überprüft, ob eine Sitzungs Konfigurationsdatei gültige Schlüssel enthält und die Werte den richtigen Typ haben. Bei Enumerationswerten überprüft das Cmdlet, ob die angegebenen Werte gültig sind.

Das-Cmdlet gibt zurück, `$True` Wenn die Datei alle Tests übergibt und `$False` andernfalls. Um Fehler zu finden, verwenden Sie den **verbose** -Parameter.

`Test-PSSessionConfigurationFile` überprüft die Sitzungs Konfigurationsdateien, z. b. die, die vom `New-PSSessionConfigurationFile` Cmdlet erstellt wurden. Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md). Weitere Informationen zu Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.

## BEISPIELE

### Beispiel 1: Testen einer Sitzungs Konfigurationsdatei

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### Beispiel 2: Testen der Sitzungs Konfigurationsdatei einer Sitzungs Konfiguration

In diesem Beispiel testen wir die Konfigurationsdatei, die in der **eingeschränkten** Sitzungs Konfiguration verwendet wird.
Der Wert des **path** -Parameters ist das Ergebnis des `Get-PSSessionConfiguration` Befehls, mit dem die **Eingeschränkte** Sitzungs Konfiguration abgerufen wird. Der Pfad der Sitzungs Konfigurationsdatei wird im Wert der **configfilepath** -Eigenschaft der Sitzungs Konfiguration gespeichert.

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### Beispiel 3: Testen aller Sitzungs Konfigurationsdateien

Mit der-Funktion in diesem Beispiel werden alle Sitzungs Konfigurationsdateien auf dem lokalen Computer getestet. Die-Funktion verwendet das- `Get-PSSessionConfiguration` Cmdlet, um alle Sitzungs Konfigurationen zu erhalten. Der Code in der `ForEach-Object` Schleife zeigt den Dateipfad an und testet jede Sitzungs Konfiguration.

```powershell
function Test-AllConfigFiles
{
    Get-PSSessionConfiguration | ForEach-Object {
        if ($_.ConfigFilePath) {
            $_.ConfigFilePath
            Test-PSSessionConfigurationFile -Verbose -Path $_.ConfigFilePath
        }
    }
}
Test-AllConfigFiles
```

```Output
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Empty_6fd77bf6-e084-4372-bd8a-af3e207354d3.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
VERBOSE: The member 'AliasDefinitions' must contain the required key 'Description'. Add the require key
to the fileC:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc.
False
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RestrictedLang_b6bd9474-0a6c-4e06-8722-c2c95bb10d3e.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RRS_3fb29420-2c87-46e5-a402-e21436331efc.pssc
True
```

Die **configfilepath** -Eigenschaft einer Sitzungs Konfiguration enthält den Pfad der Sitzungs Konfigurationsdatei, die in der Sitzungs Konfiguration verwendet wird (sofern vorhanden).

Wenn der Wert der **ConfigFilePath**-Eigenschaft angegeben ist (sprich er ist „true“), ruft der Befehl den **ConfigFilePath**-Eigenschaftswert ab (bzw. gibt ihn aus). Dann wird das `Test-PSSessionConfigurationFile` Cmdlet verwendet, um die Datei im **configfilepath** -Wert zu testen. Der **Verbose**-Parameter gibt den Dateifehler zurück, wenn die Datei den Test nicht besteht.

## PARAMETERS

### -Path

Gibt den Pfad und den Dateinamen einer Sitzungs Konfigurationsdatei (. PSSC) an. Wenn Sie den Pfad weglassen, wird standardmäßig der aktuelle Ordner angezeigt. Platzhalter Zeichen werden unterstützt, aber Sie müssen in eine einzelne Datei aufgelöst werden. Sie können auch einen Sitzungs Konfigurationsdateipfad an über die Pipeline übergeben `Test-PSSessionConfigurationFile` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können einen Sitzungs Konfigurationsdateipfad an über die Pipeline übergeben `Test-PSSessionConfigurationFile` .

## AUSGABEN

### System.Boolean

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

## VERWANDTE LINKS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan-Anbieter](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
