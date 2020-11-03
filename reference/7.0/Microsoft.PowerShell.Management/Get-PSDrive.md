---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psdrive?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSDrive
ms.openlocfilehash: d404f0fdc82e3730f1f6a04d7f39d5988a3de7d6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210196"
---
# Get-PSDrive

## ZUSAMMENFASSUNG
Ruft Laufwerke in der aktuellen Sitzung ab.

## SYNTAX

### Name (Standard)

```
Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

### LiteralName

```
Get-PSDrive [-LiteralName] <String[]> [-Scope <String>] [-PSProvider <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-PSDrive` Cmdlet werden die Laufwerke in der aktuellen Sitzung abgerufen. Sie können ein bestimmtes Laufwerk oder alle Laufwerke in der Sitzung abrufen.

Dieses Cmdlet ruft die folgenden Laufwerkstypen ab:

- Logische Windows-Laufwerke auf dem Computer, einschließlich den Netzwerkfreigaben zugeordneten Laufwerken.
- Laufwerke, die von PowerShell-Anbietern verfügbar gemacht werden (z. b. das Zertifikat:, Funktion: und Alias: Laufwerke) und die Laufwerke HKLM: und HKCU:, die vom Windows PowerShell-Registrierungs Anbieter verfügbar gemacht werden.
- Sitzungs spezifische temporäre Laufwerke und permanente zugeordnete Netzwerklaufwerke, die Sie mit dem Cmdlet "New-PSDrive" erstellen.

Ab Windows PowerShell 3,0 können mit dem **Persistenzparameter** des `New-PSDrive` Cmdlets zugeordnete Netzwerklaufwerke erstellt werden, die auf dem lokalen Computer gespeichert sind und in anderen Sitzungen verfügbar sind. Weitere Informationen finden Sie unter New-PSDrive.

Ab Windows PowerShell 3.0 wird beim Herstellen einer Verbindung zwischen einem externen Laufwerk und dem Computer außerdem von Windows PowerShell automatisch ein PowerShell-Laufwerk (PSDrive) zum Dateisystem hinzugefügt, das das neue Laufwerk darstellt.
Windows PowerShell muss nicht neu gestartet werden. Ebenso wird beim Trennen der Verbindung zwischen einem externen Laufwerk und dem Computer das PSDrive, das das entfernte Laufwerk darstellt, von Windows PowerShell automatisch gelöscht.

## BEISPIELE

### Beispiel 1: erhalten von Laufwerken in der aktuellen Sitzung

```
PS C:\> Get-PSDrive

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
Alias                                  Alias
C                 202.06      23718.91 FileSystem    C:\
Cert                                   Certificate   \
D                1211.06     123642.32 FileSystem    D:\
Env                                    Environment
Function                               Function
HKCU                                   Registry      HKEY_CURRENT_USER
HKLM                                   Registry      HKEY_LOCAL_MACHINE
Variable                               Variable
```

Dieser Befehl ruft die Laufwerke in der aktuellen Sitzung ab.

Die Ausgabe zeigt die Festplatte (C:), CD-ROM-Laufwerk (D:) und die Laufwerke, die von den Windows PowerShell-Anbietern (alias:, CERT:, ENV:, Function:, HKCU:, HKLM: und Variable:) verfügbar gemacht werden.

### Beispiel 2: erhalten eines Laufwerks auf dem Computer

```
PS C:\foo> Get-PSDrive D

Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
D                1211.06     123642.32 FileSystem    D:\
```

Mit diesem Befehl wird das Laufwerk %%amp;quot;D:%%amp;quot; auf dem Computer abgerufen. Achten Sie darauf, dass im Befehl nach dem Laufwerkbuchstaben kein Doppelpunkt folgt.

### Beispiel 3: erhalten Sie alle Laufwerke, die vom Windows PowerShell-Dateisystem Anbieter unterstützt werden.

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
```

Dieser Befehl ruft alle Laufwerke ab, die vom Windows PowerShell-FileSystem-Anbieter unterstützt werden. Dies schließt Festplattenlaufwerke, logische Partitionen, zugeordnete Netzlaufwerke und temporäre Laufwerke ein, die Sie mit dem Cmdlet "New-PSDrive" erstellen.

### Beispiel 4: überprüfen, ob ein Laufwerk als Windows PowerShell-Laufwerk Name verwendet wird

```powershell
if (Get-PSDrive X -ErrorAction SilentlyContinue) {
    Write-Host 'The X: drive is already in use.'
} else {
    New-PSDrive -Name X -PSProvider Registry -Root HKLM:\SOFTWARE
}
```

Dieser Befehl überprüft, ob das Laufwerk %%amp;quot;X%%amp;quot; bereits als Windows PowerShell-Laufwerkname verwendet wird.
Wenn dies nicht der Fall ist, verwendet der Befehl das `New-PSDrive` Cmdlet, um ein temporäres Laufwerk zu erstellen, das dem Registrierungsschlüssel "HKLM: \ Software" zugeordnet ist.

### Beispiel 5: Vergleichen der System Laufwerkstypen

```
PS C:\> Get-PSDrive -PSProvider FileSystem
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
A                                                    A:\
C                 202.06      23718.91 FileSystem    C:\
D                1211.06     123642.32 FileSystem    D:\
G                 202.06        710.91 FileSystem    \\Music\GratefulDead
X                                      Registry      HKLM:\Network

PS C:\> net use
New connections will be remembered.
Status       Local     Remote                    Network
-------------------------------------------------------------------------------
OK           G:        \\Server01\Public         Microsoft Windows Network

PS C:\> [System.IO.DriveInfo]::GetDrives() | Format-Table
Name DriveType DriveFormat IsReady AvailableFreeSpace TotalFreeSpace TotalSize     RootDirectory VolumeLabel
---- --------- ----------- ------- ------------------ -------------- ---------     ------------- -----------
A:\    Network               False                                                 A:\
C:\      Fixed NTFS          True  771920580608       771920580608   988877418496  C:\           Windows
D:\      Fixed NTFS          True  689684144128       689684144128   1990045179904 D:\           Big Drive
E:\      CDRom               False                                                 E:\
G:\    Network NTFS          True      69120000           69120000       104853504 G:\           GratefulDead

PS N:\> Get-CimInstance -Class Win32_LogicalDisk

DeviceID DriveType ProviderName   VolumeName         Size          FreeSpace
-------- --------- ------------   ----------         ----          ---------
A:       4
C:       3                        Windows            988877418496  771926069248
D:       3                        Big!              1990045179904  689684144128
E:       5
G:       4         \\Music\GratefulDead              988877418496  771926069248


PS C:\> Get-CimInstance -Class Win32_NetworkConnection
LocalName RemoteName            ConnectionState Status
--------- ----------            --------------- ------
G:        \\Music\GratefulDead  Connected       OK
```

In diesem Beispiel werden die Typen von Dateisystem Laufwerken, die von angezeigt werden, mit denen verglichen, die `Get-PSDrive` mithilfe anderer Methoden angezeigt werden. Dieses Beispiel zeigt verschiedene Möglichkeiten zum Anzeigen von Laufwerken in Windows PowerShell und zeigt, dass Sitzungs spezifische Laufwerke, die mit dem Cmdlet "New-PSDrive" erstellt werden, nur in Windows PowerShell verfügbar sind.

Der erste Befehl verwendet `Get-PSDrive` , um alle Dateisystem Laufwerke in der Sitzung zu erhalten. Dies umfasst die Festplattenlaufwerke (C: und D:), ein zugeordnetes Netzwerklaufwerk (G:). das mit dem **Persistenzparameter** von `New-PSDrive` und einem PowerShell-Laufwerk (T:) erstellt wurde. der mit erstellt wurde, `New-PSDrive` ohne den **Persistenzparameter** zu verwenden.

Der Befehl **net use** zeigt zugeordnete Windows-Netzlaufwerke an, in diesem Fall wird nur das Laufwerk G angezeigt. Das X:-Laufwerk, das von erstellt wurde, wird nicht angezeigt `New-PSDrive` . Es zeigt, dass das Laufwerk G: ebenfalls \\ \\ Music \\ gratefuldead zugeordnet ist.

Der dritte Befehl verwendet die **GetDrives** -Methode der **System.IO.DriveInfo** -Klasse von Microsoft .NET Framework. Mit diesem Befehl werden die Windows-Dateisystem Laufwerke (einschließlich Laufwerk G:) abgerufen, die von erstellten Laufwerke werden jedoch nicht abgerufen `New-PSDrive` .

Im vierten Befehl werden mit dem Cmdlet `Get-CimInstance` die Instanzen der Klasse **Win32_LogicalDisk** abgerufen. Sie gibt die Laufwerke A:, C:, D:, E: und G: zurück, jedoch nicht die von erstellten Laufwerke `New-PSDrive` .

Im letzten Befehl werden mit dem Cmdlet `Get-CimInstance` die Instanzen der Klasse **Win32_NetworkConnection** angezeigt. Wie bei **net use** wird nur das permanente Laufwerk G: zurückgegeben, das von erstellt wurde `New-PSDrive` .

## PARAMETERS

### -LiteralName

Gibt den Namen des Laufwerks an.

Der Wert von **LiteralName** wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Name Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen Windows PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt den Namen oder den Namen der Laufwerke an, die dieses Cmdlet im Vorgang abruft, als Zeichen folgen Array.
Geben Sie den Laufwerknamen oder den Buchstaben ohne Doppelpunkt (:) ein.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Psprovider

Gibt als Zeichen folgen Array den Windows PowerShell-Anbieter an. Dieses Cmdlet ruft nur die Laufwerke ab, die von diesem Anbieter unterstützt werden. Geben Sie den Namen eines Anbieters ein, z. B. %%amp;quot;FileSystem%%amp;quot;, %%amp;quot;Registry%%amp;quot; oder %%amp;quot;Certificate%%amp;quot;.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Bereich

Gibt den Bereich an, in dem dieses Cmdlet die Laufwerke abruft.

Zulässige Werte für diesen Parameter:

- Global
- Lokal
- Skript
- eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist). Local ist der Standardwert.

Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System.Management.Automation.PSDrivin FO

Dieses Cmdlet gibt Objekte zurück, die die Laufwerke in der Sitzung darstellen.

## HINWEISE

* Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Führen Sie die verfügbaren Anbieter in Ihrer Sitzung mithilfe des Cmdlets `Get-PSProvider` auf. Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).
* Zugeordnete Netzwerklaufwerke, die mit dem **Persistenzparameter** des Cmdlets "New-PSDrive" erstellt werden, sind für ein Benutzerkonto spezifisch. Zugeordnete Netzwerklaufwerke, die in Sitzungen erstellt werden, die mit der Option "als Administrator ausführen" oder mit den Anmelde Informationen eines anderen Benutzers gestartet werden, sind nicht in Sitzungen sichtbar, die ohne explizite Anmelde Informationen oder mit den Anmelde Informationen des aktuellen Benutzers gestartet werden.

## VERWANDTE LINKS

[New-PSDrive](New-PSDrive.md)

[Remove-PSDrive](Remove-PSDrive.md)

[Get-PSProvider](Get-PSProvider.md)
