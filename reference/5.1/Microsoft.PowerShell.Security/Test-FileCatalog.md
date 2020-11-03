---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/test-filecatalog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-FileCatalog
ms.openlocfilehash: 128405fdbcf0c1d059287191850ffdca53278ec1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214199"
---
# Test-FileCatalog

## ZUSAMMENFASSUNG

`Test-FileCatalog` überprüft, ob die Hashes, die in einer Katalog Datei (. cat) enthalten sind, mit den Hashwerten der eigentlichen Dateien übereinstimmen, um ihre Echtheit zu validieren.

Dieses Cmdlet wird nur unter Windows unterstützt.

## SYNTAX

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>] [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Test-FileCatalog` überprüft die Authentizität von Dateien, indem die Dateihashes einer Katalog Datei (. cat) mit den Hashes der tatsächlichen Dateien auf dem Datenträger verglichen werden.
Wenn keine Übereinstimmungen gefunden werden, wird der Status "validationfailed" zurückgegeben. Benutzer können alle diese Informationen mithilfe des Parameters -Detailed abrufen.
Außerdem wird der Signierungs Status des Katalogs in der Signatur Eigenschaft angezeigt, der dem aufrufenden `Get-AuthenticodeSignature` Cmdlet in der Katalog Datei entspricht.
Benutzer können außerdem jede Datei während der Überprüfung mithilfe des Parameters -FilesToSkip überspringen.

Dieses Cmdlet wird nur unter Windows unterstützt.

## BEISPIELE

### Beispiel 1: Erstellen und Validieren eines Datei Katalogs

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0

Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Valid
```

### Beispiel 2: Überprüfen eines Datei Katalogs mit detaillierter Ausgabe

```powershell
Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Status        : Valid
HashAlgorithm : SHA256
CatalogItems  : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
PathItems     : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
Signature     : System.Management.Automation.Signature
```

## PARAMETERS

### -Catalogfilepath

Ein Pfad zu einer Katalog Datei (. cat), die die Hashes enthält, die für die Validierung verwendet werden sollen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Detailed

Gibt weitere Informationen zu einem detaillierteren Objekt zurück, `CatalogInformation` das die getesteten Dateien, die erwarteten/tatsächlichen Hashwerte und eine Authenticode-Signatur der Katalog Datei enthält, wenn diese signiert ist.

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

### -Filestoskip

Ein Array von Pfaden, die nicht als Teil der Validierung getestet werden sollen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Ein Ordner oder ein Array von Dateien, die für die Katalog Datei überprüft werden sollen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. IO. Director yinfo [], System. String []

Die Pipeline akzeptiert ein Array von Zeichen folgen oder `DirectoryInfo` Objekten, die Pfade zu den Dateien darstellen, die überprüft werden müssen.

## AUSGABEN

### System. Management. Automation. catalogvalidationstatus

Der Standard Rückgabetyp, der entweder den Wert `Valid` oder enthält `ValidationFailed` .

### System. Management. Automation. cataloginformation

Ein ausführlicheres Objekt, das zurückgegeben wird, wenn verwendet `-Detailed` wird. es kann verwendet werden, um bestimmte Dateien zu analysieren, die die Überprüfung möglicherweise bestanden haben oder nicht, welche Hashwerte erwartet werden, und der im Katalog verwendete Algorithmus.

## HINWEISE

## VERWANDTE LINKS

[New-FileCatalog](New-FileCatalog.md)

[PowerShellGet](/powershell/module/PowerShellGet)
