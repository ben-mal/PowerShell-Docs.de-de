---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: 20116c12f09d6a9a36f33b656a36e30c2096db70
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605378"
---
# Get-ItemProperty

## ZUSAMMENFASSUNG
Ruft die Eigenschaften eines angegebenen Elements ab.

## SYNTAX

### Pfad (Standard)

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### LiteralPath

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-ItemProperty` Cmdlet ruft die Eigenschaften der angegebenen Elemente ab.
Beispielsweise können Sie mit diesem Cmdlet den Wert der LastAccessTime-Eigenschaft eines Datei Objekts erhalten. Sie können dieses Cmdlet auch zum Anzeigen von Registrierungs Einträgen und deren Werten verwenden.

## BEISPIELE

### Beispiel 1: erhalten von Informationen zu einem bestimmten Verzeichnis

Mit diesem Befehl werden Informationen zum `C:\Windows` Verzeichnis abgerufen.

```powershell
Get-ItemProperty C:\Windows
```

### Beispiel 2: erhalten der Eigenschaften einer bestimmten Datei

Mit diesem Befehl werden die Eigenschaften der `C:\Test\Weather.xls` Datei abgerufen.
Das Ergebnis wird an das `Format-List` Cmdlet weitergeleitet, um die Ausgabe als Liste anzuzeigen.

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### Beispiel 3: Anzeigen des Werte namens und der Daten von Registrierungs Einträgen in einem Registrierungs Unterschlüssel

Dieser Befehl zeigt den Wertnamen und die Daten der einzelnen Registrierungseinträge im Registrierungs Unterschlüssel "CurrentVersion" an.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

> [!NOTE]
> Dieser Befehl erfordert, dass ein PowerShell-Laufwerk mit dem Namen vorhanden ist `HKLM:` , das der Hive-HKEY_LOCAL_MACHINE Struktur der Registrierung zugeordnet ist.
>
> Ein Laufwerk mit diesem Namen und dieser Zuordnung ist standardmäßig in PowerShell verfügbar.
> Der Pfad zu diesem Registrierungsunterschlüssel kann jedoch auch mit dem folgenden alternativen Pfad angegeben werden, der mit dem Anbieternamen beginnt, auf den zwei Doppelpunkte folgen:
>
> `Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.

### Beispiel 4: erhalten Sie den Wertnamen und die Daten eines Registrierungs Eintrags in einem Registrierungs Unterschlüssel.

Mit diesem Befehl werden der Wertname und die Daten des Registrierungs Eintrags "ProgramFilesDir" im Registrierungs Unterschlüssel "CurrentVersion" abgerufen.
Der **Pfad** gibt den Unterschlüssel an, und der **Name** -Parameter gibt den Wertnamen des Eintrags an.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### Beispiel 5: erhalten der Werte Namen und Daten von Registrierungs Einträgen in einem Registrierungsschlüssel

Dieser Befehl ruft die Wertnamen und Daten der Registrierungseinträge im Registrierungsschlüssel "powershellengine" ab. Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

## PARAMETERS

### -Credential

> [!NOTE]
> Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.
> Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ausschließen

Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden. Der Wert dieses Parameters qualifiziert den **Path**-Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b.. Platzhalterzeichen sind zulässig. Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Filter

Gibt einen Filter zum Qualifizieren des **path** -Parameters an. Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt. Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Include

Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt. Der Wert dieses Parameters qualifiziert den **Path**-Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b.. Platzhalterzeichen sind zulässig. Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Literalpath

Gibt einen Pfad zu einem oder mehreren Speicherorten an. Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt den Namen der abzurufenden Eigenschaft oder Eigenschaften an.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Path

Gibt den Pfad zu den Elementen an.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Get-ItemProperty` .

## AUSGABEN

### System. Boolean, System. String, System. DateTime

`Get-ItemProperty` Gibt ein-Objekt für jede Element Eigenschaft zurück, die es abruft. Der Objekttyp richtet sich nach dem abgerufenen Objekt. Beispielsweise wird auf einem Dateisystemlaufwerk möglicherweise eine Datei oder ein Ordner zurückgegeben.

## HINWEISE

Das- `Get-ItemProperty` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Clear-ItemProperty](Clear-ItemProperty.md)

[Copy-ItemProperty](Copy-ItemProperty.md)

[Move-ItemProperty](Move-ItemProperty.md)

[New-ItemProperty](New-ItemProperty.md)

[Remove-ItemProperty](Remove-ItemProperty.md)

[Rename-ItemProperty](Rename-ItemProperty.md)

[Set-ItemProperty](Set-ItemProperty.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

