---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: e2498c02d42123e207b49e622654d3cb881fc0fc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601729"
---
# Split-Path

## ZUSAMMENFASSUNG
Gibt den angegebenen Teil eines Pfads zurück.

## SYNTAX

### Parametriset (Standard)

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Blätter Satz

```
Split-Path [-Path] <String[]> -Leaf [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

### Leafbaseset

```
Split-Path [-Path] <String[]> -LeafBase [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### ExtensionSet

```
Split-Path [-Path] <String[]> -Extension [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Qualifierset

```
Split-Path [-Path] <String[]> -Qualifier [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Noqualifierset

```
Split-Path [-Path] <String[]> -NoQualifier [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Isabsoluteset

```
Split-Path [-Path] <String[]> [-Resolve] -IsAbsolute [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Literalpathset

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Split-Path` Cmdlet gibt nur den angegebenen Teil eines Pfads zurück, z. b. den übergeordneten Ordner, einen Unterordner oder einen Dateinamen. Außerdem können Elemente abgerufen werden, auf die von dem geteilten Pfad verwiesen wird, und es kann angegeben werden, ob es sich um einen relativen oder absoluten Pfad handelt.

Sie können mit diesem Cmdlet nur einen ausgewählten Teil eines Pfads abrufen oder senden.

## BEISPIELE

### Beispiel 1: Holen Sie sich den Qualifizierer eines Pfads.

```powershell
Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
```

```Output
HKCU:
```

Mit diesem Befehl wird nur der Qualifizierer des Pfads zurückgegeben. Der Qualifizierer ist das Laufwerk.

### Beispiel 2: Anzeigen von Dateinamen

```powershell
Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
```

```Output
Pass1.log
Pass2.log
...
```

Mit diesem Befehl werden die Dateien angezeigt, auf die vom geteilten Pfad verwiesen wird. Da dieser Pfad auf das letzte Element aufgeteilt ist, das auch als Blatt bezeichnet wird, zeigt der Befehl nur die Dateinamen an.

Der **Resolve** -Parameter weist `Split-Path` an, die Elemente anzuzeigen, auf die der geteilte Pfad verweist, anstatt den geteilten Pfad anzuzeigen.

Wie alle `Split-Path` Befehle gibt dieser Befehl Zeichen folgen zurück. Es werden keine **FileInfo** -Objekte zurückgegeben, die die Dateien darstellen.

### Beispiel 3: Get the parent Container

```powershell
Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
```

```Output
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

Mit diesem Befehl werden nur die übergeordneten Container des Pfads zurückgegeben. Da keine Parameter zum Angeben der Teilung enthalten sind, `Split-Path` verwendet den Standard **Wert für** den geteilten Speicherort, der übergeordnet ist.

### Beispiel 4: bestimmt, ob ein Pfad absolut ist

```powershell
Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
```

```Output
False
```

Mit diesem Befehl wird bestimmt, ob der Pfad relativ oder absolut ist. In diesem Fall wird zurückgegeben, da der Pfad relativ zum aktuellen Ordner ist, der durch einen Punkt ( `.` ) dargestellt wird `$False` .

### Beispiel 5: Ändern des Speicher Orts in einen angegebenen Pfad

```powershell
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

Mit diesem Befehl wird der Speicherort in den Ordner geändert, der das PowerShell-Profil enthält.

Der-Befehl in Klammern verwendet `Split-Path` , um nur das übergeordnete Element des Pfads zurückzugeben, der in der integrierten Variablen gespeichert ist `$Profile` . Der **Parent** -Parameter ist der standardmäßige Split Location-Parameter.
Aus diesem Grund können Sie Sie im Befehl weglassen. Die Klammern leiten PowerShell an, den Befehl zuerst auszuführen. Dies ist eine hilfreiche Möglichkeit, um zu einem Ordner zu wechseln, der über einen langen Pfadnamen verfügt.

### Beispiel 6: Aufteilen eines Pfads mithilfe der Pipeline

```powershell
'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
```

```Output
C:\Documents and Settings\User01\My Documents
```

Dieser Befehl verwendet einen Pipeline Operator ( `|` ), um einen Pfad an zu senden `Split-Path` . Der Pfad ist in Anführungszeichen eingeschlossen, um anzugeben, dass es sich um ein einzelnes Token handelt.

## PARAMETERS

### -Credential

> [!NOTE]
> Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt. Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".

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

### -Erweiterung

Gibt an, dass dieses Cmdlet nur die Erweiterung des Blatts zurückgibt. Im Pfad wird beispielsweise `C:\Test\Logs\Pass1.log` nur zurückgegeben `.log` .

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ExtensionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsAbsolute

Gibt an, dass dieses Cmdlet $true zurückgibt, wenn der Pfad absolut ist, und $false, wenn er relativ ist. Ein absoluter Pfad weist eine Länge größer als 0 (null) auf und verwendet keinen Punkt ( `.` ), um den aktuellen Pfad anzugeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Blatt

Gibt an, dass dieses Cmdlet nur das letzte Element bzw. den letzten Container im Pfad zurückgibt. Beispielsweise wird im Pfad `C:\Test\Logs\Pass1.log` nur Pass1. log zurückgegeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Leafbase

Gibt an, dass dieses Cmdlet nur den Basis Namen des Blatts zurückgibt. Im Pfad wird beispielsweise `C:\Test\Logs\Pass1.log` nur zurückgegeben `Pass1` .

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafBaseSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Literalpath

Gibt die zu teilenden Pfade an. Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Noqualifizierer

Gibt an, dass dieses Cmdlet den Pfad ohne den Qualifizierer zurückgibt. Für den Dateisystem-oder Registrierungs Anbieter ist der Qualifizierer das Laufwerk des Anbieter Pfads, z `C:` `HKCU:` . b. oder. Im Pfad wird beispielsweise `C:\Test\Logs\Pass1.log` nur zurückgegeben `\Test\Logs\Pass1.log` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Übergeordnetes Element

Gibt an, dass dieses Cmdlet nur die übergeordneten Container des Elements oder des Containers zurückgibt, der durch den Pfad angegeben wird. Beispielsweise wird im Pfad `C:\Test\Logs\Pass1.log` zurückgegeben `C:\Test\Logs` .
Der **Parent** -Parameter ist der standardmäßige Split Location-Parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Gibt die zu teilenden Pfade an. Platzhalterzeichen sind zulässig. Wenn der Pfad Leerzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen. Sie können einen Pfad auch über die Pipeline an dieses Cmdlet übergeben.

```yaml
Type: System.String[]
Parameter Sets: ParentSet, LeafSet, LeafBaseSet, ExtensionSet, QualifierSet, NoQualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Qualifizierer

Gibt an, dass dieses Cmdlet nur den Qualifizierer des angegebenen Pfads zurückgibt. Für den Dateisystem-oder Registrierungs Anbieter ist der Qualifizierer das Laufwerk des Anbieter Pfads, z `C:` `HKCU:` . b. oder.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Auflösen

Gibt an, dass dieses Cmdlet die Elemente anzeigt, auf die vom resultierenden geteilten Pfad verwiesen wird, anstatt die Pfad Elemente anzuzeigen.

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

### System.String

Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.

## AUSGABEN

### System. String, System. Boolean

`Split-Path` Gibt Text Zeichenfolgen zurück. Wenn Sie den **Resolve** -Parameter angeben, `Split-Path` gibt eine Zeichenfolge zurück, die den Speicherort der Elemente beschreibt. es werden keine Objekte zurückgegeben, die die Elemente darstellen, wie z. b. ein **FileInfo** -oder ein **RegistryKey** -Objekt.

Wenn Sie den **IsAbsolute** -Parameter angeben, wird von `Split-Path` ein **boolescher** Wert zurückgegeben.

## HINWEISE

- Die Split Location-Parameter (**Qualifizierer**, über **geordnetes** Element, **Erweiterung**, **Blatt**, **leafbase** und **noqualifizierer**) sind exklusiv. In einem Befehl kann immer nur ein Parameter angegeben werden.

- Die Cmdlets, die das **Pfad** -Substantiv enthalten (die **path** -Cmdlets), funktionieren mit Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann. Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll. Verwenden Sie diese in der Weise, in der Sie **dirname**, **normpath**, **realpath**, **Join** oder andere Pfad Manipulatoren verwenden.

- Sie können die **Pfad** -Cmdlets mit verschiedenen Anbietern verwenden. Hierzu gehören das Dateisystem, die Registrierung und die Zertifikat Anbieter.

- `Split-Path` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.

## VERWANDTE LINKS

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Test-Path](Test-Path.md)
