---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: 0481526aead285e3d5fb494218d1573e03216f2e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604854"
---
# Resolve-Path

## ZUSAMMENFASSUNG
Löst die Platzhalterzeichen in einem Pfad auf und zeigt den Inhalt des Pfads an.

## SYNTAX

### Pfad (Standard)

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

### LiteralPath

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

Das `Resolve-Path` -Cmdlet zeigt die Elemente und Container an, die dem Platzhalter Muster am angegebenen Speicherort entsprechen. Die Entsprechung kann Dateien, Ordner, Registrierungsschlüssel oder ein beliebiges anderes Objekt enthalten, auf das von einem PSDrive-Anbieter zugegriffen werden kann.

## BEISPIELE

### Beispiel 1: Auflösen des Basisordner Pfads

Das Tildezeichen (~) ist eine Kurznotiz für den Basisordner des aktuellen Benutzers. Dieses Beispiel zeigt, wie Sie `Resolve-Path` den voll qualifizierten Pfadwert zurückgeben.

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### Beispiel 2: Auflösen des Pfads des Windows-Ordners

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

Bei der Durchführung vom Stamm des Laufwerks c: gibt dieser Befehl den Pfad des Windows-Ordners auf Laufwerk c: zurück.

### Beispiel 3: alle Pfade im Windows-Ordner

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

Mit diesem Befehl werden alle Ordner im Ordner "c:\Windows" zurückgegeben. Der Befehl verwendet einen Pipeline Operator (|), um eine Pfad Zeichenfolge an zu senden `Resolve-Path` .

### Beispiel 4: Auflösen eines UNC-Pfads

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

Dieser Befehl löst einen UNC (Universal Naming Convention)-Pfad auf und gibt die Freigaben im Pfad zurück.

### Beispiel 5: erhalten relativer Pfade

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

Dieser Befehl gibt relative Pfade für die Verzeichnisse im Stammverzeichnis von Laufwerk %%amp;quot;C:%%amp;quot; zurück.

### Beispiel 6: Auflösen eines Pfads, der eckige Klammern enthält

Dieses Beispiel verwendet den **literalpath** -Parameter, um den Pfad des Test- \[ XML- \] unter Ordners aufzulösen.
Die Verwendung von **literalpath** bewirkt, dass die Klammern als normale Zeichen und nicht als regulärer Ausdruck behandelt werden.

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## PARAMETERS

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.
Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder übergeben Sie ein **PSCredential** -Objekt. Sie können ein **PSCredential** -Objekt mit dem `Get-Credential` Cmdlet erstellen. Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.

Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Literalpath

Gibt den aufzulösenden Pfad an.
Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.
Es werden keine Zeichen als Platzhalter interpretiert.
Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.
Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

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

### -Path

Gibt den aufzulösenden PowerShell-Pfad an.
Dieser Parameter ist erforderlich.
Sie können eine Pfad Zeichenfolge auch über die Pipeline an übergeben `Resolve-Path` .
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

### -Relativ

Gibt an, dass dieses Cmdlet einen relativen Pfad zurückgibt.

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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.

## AUSGABEN

### System. Management. Automation. PathInfo, System. String

Gibt ein **pathinfo** -Objekt zurück. Gibt einen Zeichen folgen Wert für den aufgelösten Pfad zurück, wenn Sie den **relativen** Parameter angeben.

## HINWEISE

Die `*-Path` Cmdlets funktionieren mit dem Dateisystem, der Registrierung und den Zertifikat Anbietern.

`Resolve-Path` ist für den Einsatz mit jedem Anbieter konzipiert. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../microsoft.powershell.core/about/about_providers.md).

`Resolve-Path` löst nur vorhandene Pfade auf. Sie kann nicht verwendet werden, um einen Speicherort aufzulösen, der noch nicht vorhanden ist.

## VERWANDTE LINKS

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Split-Path](Split-Path.md)

[Test-Path](Test-Path.md)

