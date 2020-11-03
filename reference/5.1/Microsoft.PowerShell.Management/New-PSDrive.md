---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-psdrive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSDrive
ms.openlocfilehash: df5f335780ad04b2d833180c30cc46a06f85d850
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214607"
---
# New-PSDrive

## ZUSAMMENFASSUNG
Erstellt temporäre und permanente zugeordnete Netzwerklaufwerke.

## SYNTAX

### Alle

```
New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Description <String>]
 [-Scope <String>] [-Persist] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem `New-PSDrive` -Cmdlet werden temporäre und persistente Laufwerke erstellt, die einem Speicherort in einem Datenspeicher zugeordnet oder zugeordnet sind, z. b. ein Netzwerklaufwerk, ein Verzeichnis auf dem lokalen Computer oder ein Registrierungsschlüssel, und persistente Windows zugeordnete Netzwerklaufwerke, die einem Dateisystem Speicherort auf einem Remote Computer zugeordnet sind.

Temporäre Laufwerke sind nur in der aktuellen PowerShell-Sitzung und in Sitzungen vorhanden, die Sie in der aktuellen Sitzung erstellen. Sie können einen beliebigen Namen haben, der in PowerShell gültig ist und einer beliebigen lokalen Ressource oder Remote Ressource zugeordnet werden kann. Sie können temporäre PowerShell-Laufwerke verwenden, um auf Daten im zugeordneten Datenspeicher zuzugreifen, genauso wie bei jedem zugeordneten Netzwerklaufwerk. Sie können Speicherorte in das Laufwerk ändern, indem Sie verwenden `Set-Location` und mithilfe von oder auf den Inhalt des Laufwerks zugreifen `Get-Item` `Get-ChildItem` .

Da temporäre Laufwerke nur PowerShell bekannt sind, können Sie nicht über den Datei-Explorer, Windows-Verwaltungsinstrumentation (WMI), Component Object Model (com), Microsoft .NET Framework oder mit Tools wie z. b. **net use** darauf zugreifen.

In PowerShell 3,0 wurden die folgenden Features hinzugefügt `New-PSDrive` :

- Zugeordnete Netzlaufwerke. Mit dem **Persistenzparameter** von können Sie von Windows zugeordnete `New-PSDrive` Netzwerklaufwerke erstellen. Anders als bei temporären PowerShell-Laufwerken sind zugeordnete Windows-Netzlaufwerke nicht Sitzungs spezifisch. Sie werden in Windows gespeichert und können mithilfe von Windows-Standard Tools, wie z. b. Datei-Explorer und **net use** , verwaltet werden. Zugeordnete Netzwerklaufwerke müssen einen Laufwerkbuchstaben aufweisen und mit einem Remotedateisystem-Speicherort verbunden sein. Wenn Ihr Befehl lokal festgelegt ist, ohne dass der **Persistenzparameter** die Erstellung eines " **PSDrive** " über den Gültigkeitsbereich hinaus speichert, in dem der Befehl ausgeführt wird. Wenn Sie `New-PSDrive` innerhalb eines Skripts arbeiten und das Laufwerk unbegrenzt beibehalten werden soll, müssen Sie das Skript als Punkt verwenden. Um optimale Ergebnisse zu erzwingen, fügen Sie dem Befehl den **Scope** -Parameter hinzu, und legen Sie seinen Wert auf **Global** fest, um zu erzwingen, dass ein neues Laufwerk unbegrenzt persistent gespeichert wird. Weitere Informationen zur Punkt basierten Beschaffung finden Sie unter [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).
- Externe Laufwerke. Wenn ein externes Laufwerk mit dem Computer verbunden ist, wird dem Dateisystem, das das neue Laufwerk darstellt, von PowerShell automatisch ein **PSDrive** hinzugefügt. PowerShell muss nicht neu gestartet werden. Ebenso wird beim Trennen eines externen Laufwerks mit dem Computer das **PSDrive** , das das entfernte Laufwerk darstellt, von PowerShell automatisch gelöscht.
- Anmelde Informationen für Universal Naming Convention (UNC)-Pfade.

Wenn der Wert des **root** -Parameters ein UNC-Pfad ist (z. b.), `\\Server\Share` werden die im Wert des **Anmelde Informationen** -Parameters angegebenen Anmelde Informationen zum Erstellen des **PSDrive** verwendet. Andernfalls sind **Anmelde Informationen nicht wirksam** , wenn Sie neue Dateisystem Laufwerke erstellen.

Einige Codebeispiele verwenden Verteilung, um die Zeilenlänge zu verringern und die Lesbarkeit zu verbessern. Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

## BEISPIELE

### Beispiel 1: Erstellen eines temporären Laufwerks, das einer Netzwerkfreigabe zugeordnet ist

In diesem Beispiel wird ein temporäres PowerShell-Laufwerk erstellt, das einer Netzwerkfreigabe zugeordnet ist.

```powershell
New-PSDrive -Name "Public" -PSProvider "FileSystem" -Root "\\Server01\Public"
```

```Output
Name       Provider      Root
----       --------      ----
Public     FileSystem    \\Server01\Public
```

`New-PSDrive` verwendet den **Name** -Parameter, um das PowerShell `Public` -Laufwerk mit dem Namen und den **psprovider** -Parameter anzugeben, um den PowerShell- `FileSystem` Anbieter anzugeben. Der **root** -Parameter gibt den UNC-Pfad der Netzwerkfreigabe an.

So zeigen Sie den Inhalt einer PowerShell-Sitzung an: `Get-ChildItem -Path Public:`

### Beispiel 2: Erstellen eines temporären Laufwerks, das einem lokalen Verzeichnis zugeordnet ist

In diesem Beispiel wird ein temporäres PowerShell-Laufwerk erstellt, das Zugriff auf ein Verzeichnis auf dem lokalen Computer bietet.

```powershell
$parameters = @{
    Name = "MyDocs"
    PSProvider = "FileSystem"
    Root = "C:\Users\User01\Documents"
    Description = "Maps to my My Documents folder."
}
New-PSDrive @parameters
```

```Output
Name        Provider      Root
----        --------      ----
MyDocs      FileSystem    C:\Users\User01\Documents
```

Splatting erstellt die Parameter Schlüssel und-Werte. Der **Name** -Parameter gibt den Namen des Laufwerks an, **MyDocs** . Der **psprovider** -Parameter gibt den PowerShell- `FileSystem` Anbieter an. **Root** gibt das Verzeichnis des lokalen Computers an. Der **Beschreibungs** Parameter beschreibt den Zweck des Laufwerks. `New-PSDrive` verwendet die splatted-Parameter, um das Laufwerk zu erstellen `MyDocs` .

So zeigen Sie den Inhalt einer PowerShell-Sitzung an: `Get-ChildItem -Path MyDocs:`

### Beispiel 3: Erstellen eines temporären Laufwerks für einen Registrierungsschlüssel

In diesem Beispiel wird ein temporäres PowerShell-Laufwerk erstellt, das Zugriff auf einen Registrierungsschlüssel bietet. Es wird ein Laufwerk mit dem Namen MyCompany erstellt, das dem `HKLM:\Software\MyCompany` Registrierungsschlüssel zugeordnet ist.

```powershell
New-PSDrive -Name "MyCompany" -PSProvider "Registry" -Root "HKLM:\Software\MyCompany"
```

```Output
Name           Provider      Root
----           --------      ----
MyCompany      Registry      HKLM:\Software\MyCompany
```

`New-PSDrive` verwendet den **Name** -Parameter, um das PowerShell `MyCompany` -Laufwerk mit dem Namen und den **psprovider** -Parameter anzugeben, um den PowerShell- `Registry` Anbieter anzugeben. Der **root** -Parameter gibt den Registrierungs Speicherort an.

So zeigen Sie den Inhalt einer PowerShell-Sitzung an: `Get-ChildItem -Path MyCompany:`

### Beispiel 4: Erstellen eines permanenten zugeordneten Netzwerklaufwerks mithilfe von Anmelde Informationen

In diesem Beispiel wird ein Netzwerklaufwerk zugeordnet, das mit den Anmelde Informationen eines Domänen Dienst Kontos authentifiziert ist.
Weitere Informationen über das **PSCredential** -Objekt, in dem Anmelde Informationen gespeichert werden, und wie Kenn Wörter als **SecureString** gespeichert werden, finden Sie in der Beschreibung des Parameters " **Credential** ".

```powershell
$cred = Get-Credential -Credential Contoso\ServiceAccount
New-PSDrive -Name "S" -Root "\\Server01\Scripts" -Persist -PSProvider "FileSystem" -Credential $cred
Net Use
```

```Output
Status       Local     Remote                    Network
---------------------------------------------------------
OK           S:        \\Server01\Scripts        Microsoft Windows Network
```

> [!NOTE]
> Wenn Sie den obigen Code Ausschnitt in einem Skript verwenden, legen Sie den Wert des **Bereichs** Parameters auf "Global" fest, um sicherzustellen, dass das Laufwerk außerhalb des aktuellen Bereichs beibehalten wird.

Die `$cred` Variable speichert ein **PSCredential** -Objekt, das die Anmelde Informationen des Dienst Kontos enthält. `Get-Credential` Sie werden aufgefordert, das Kennwort einzugeben, das in einer **SecureString** gespeichert ist.

`New-PSDrive` erstellt das zugeordnete Netzwerklaufwerk mithilfe mehrerer Parameter. **Name** gibt den `S` Laufwerk Buchstaben an, den Windows akzeptiert. und **root** definiert `\\Server01\Scripts` als Speicherort auf einem Remote Computer. **Persistenz erstellt ein** zugeordnetes Windows-Netzwerklaufwerk, das auf dem lokalen Computer gespeichert ist. **Psprovider** gibt den `FileSystem` Anbieter an. Anmelde **Informationen verwenden die** - `$cred` Variable, um die Anmelde Informationen des Dienst Kontos für die Authentifizierung zu erhalten.

Das zugeordnete Laufwerk kann auf dem lokalen Computer in PowerShell-Sitzungen, im Datei-Explorer und mit Tools wie z. b. **net use** angezeigt werden. So zeigen Sie den Inhalt einer PowerShell-Sitzung an: `Get-ChildItem -Path S:`

### Beispiel 5: Erstellen von persistenten und temporären Laufwerken

Dieses Beispiel zeigt den Unterschied zwischen einem permanenten zugeordneten Netzwerklaufwerk und einem temporären PowerShell-Laufwerk, das derselben Netzwerkfreigabe zugeordnet ist.

Wenn Sie die PowerShell-Sitzung schließen und dann eine neue Sitzung öffnen, ist die temporäre `PSDrive:` nicht verfügbar, aber das persistente `X:` Laufwerk ist verfügbar. Berücksichtigen Sie bei der Entscheidung, welche Methode zum Zuordnen von Netzlaufwerken verwendet werden soll, die Verwendung des Laufwerks. Beispielsweise, ob es persistent sein muss und ob das Laufwerk für andere Windows-Features sichtbar sein muss.

```powershell
# Create a temporary PowerShell drive called PSDrive:
# that's mapped to the \\Server01\Public network share.
New-PSDrive -Name "PSDrive" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Use the Persist parameter of New-PSDrive to create the X: mapped network drive,
# which is also mapped to the \\Server01\Public network share.
New-PSDrive -Persist -Name "X" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Now, you can use the Get-PSDrive drive cmdlet to examine the two drives.
# The drives appear to be the same, although the network share name appears only
# in the root of the PSDrive: drive.
Get-PSDrive -Name "PSDrive", "X"
```

```Output
Name       Provider      Root
----       --------      ----

PsDrive    FileSystem    \\Server01\public
X          FileSystem    X:\
```

```powershell
# Get-Member cmdlet shows that the drives have the same object type,
# System.Management.Automation.PSDriveInfo.
Get-PSDrive "PSDrive", "x" | Get-Member
```

```Output
TypeName: System.Management.Automation.PSDriveInfo

Name                MemberType   Definition
----                ----------   ----------
CompareTo           Method       System.Int32 CompareTo(PSDriveInfo drive),
Equals              Method       System.Boolean Equals(Object obj),
GetHashCode         Method       System.Int32 GetHashCode()
...
```

```powershell
# Net Use and Get-CimInstance for the Win32_LogicalDisk class,
# and Win32_NetworkConnection class find only the persistent X: drive.
# PowerShell temporary drives are known only to PowerShell.
Net Use
Get-CimInstance Win32_LogicalDisk | Format-Table -Property DeviceID
Get-CimInstance Win32_NetworkConnection
```

```Output
Status       Local     Remote                    Network
--------------------------------------------------------
OK           X:        \\contoso-pc\data         Microsoft Windows Network

deviceid
--------
C:
D:
X:

LocalName    RemoteName              ConnectionState          Status
---------    ----------              ---------------          ------
X:           \\products\public       Disconnected             Unavailable
```

## PARAMETERS

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

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer.

Da PowerShell 3,0, wenn der Wert des **root** -Parameters ein UNC-Pfad ist, können Sie Anmelde Informationen zum Erstellen von Dateisystem Laufwerken verwenden.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

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

### -Description

Gibt eine kurze Textbeschreibung des Laufwerks an. Geben Sie eine beliebige Zeichenfolge ein.

, Um die Beschreibungen aller Laufwerke der Sitzung anzuzeigen `Get-PSDrive | Format-Table Name, Description` .

Wenn Sie die Beschreibung eines bestimmten Laufwerks anzeigen möchten, geben Sie ein `(Get-PSDrive <DriveName>).Description` .

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

### -Name

Gibt einen Namen für das neue Laufwerk an. Verwenden Sie für persistente zugeordnete Netzwerklaufwerke einen Laufwerk Buchstaben. Bei temporären PowerShell-Laufwerken sind Sie nicht auf Laufwerk Buchstaben beschränkt. verwenden Sie eine beliebige gültige Zeichenfolge.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Persistent speichern

Gibt an, dass dieses Cmdlet ein zugeordnetes Windows-Netzwerklaufwerk erstellt. Der **Persistenzparameter** ist nur unter Windows verfügbar.

Zugeordnete Netzwerklaufwerke werden unter Windows auf dem lokalen Computer gespeichert. Sie sind permanent, nicht Sitzungs spezifisch und können im Datei-Explorer und anderen Tools angezeigt und verwaltet werden.

Wenn Sie den Befehl ohne Punkt-Beschaffung lokal festlegen, behält der **Persistenzparameter** die Erstellung eines **PSDrive** nicht bei, der über den Bereich hinausgeht, in dem Sie den Befehl ausführen. Wenn Sie `New-PSDrive` in einem Skript ausführen und das neue Laufwerk unbegrenzt beibehalten werden soll, müssen Sie das Skript mit einer Punktquelle erstellen. Um die besten Ergebnisse zu erzwingen, geben Sie **Global** als Wert für den **Scope** -Parameter **und include in** Ihren Befehl ein, um die Beibehaltung eines neuen Laufwerks zu erzwingen.

Der Name des Laufwerks muss ein Buchstabe sein, z `D` . b `E` . oder. Der Wert des **root** -Parameters muss ein UNC-Pfad eines anderen Computers sein. Der Wert des **psprovider** -Parameters muss lauten `FileSystem` .

Verwenden Sie zum Trennen einer Verbindung mit einem zugeordneten Windows-Netzwerklaufwerk das Cmdlet `Remove-PSDrive`. Wenn Sie die Verbindung mit einem zugeordneten Windows-Netzwerklaufwerk trennen, wird die Zuordnung dauerhaft vom Computer gelöscht, nicht nur aus der aktuellen Sitzung.

Zugeordnete Netzwerklaufwerke sind bestimmten Benutzerkonten zugeordnet. Zugeordnete Laufwerke, die mit den Anmelde Informationen eines anderen Benutzers in erweiterten Sitzungen oder Sitzungen erstellt wurden, sind in Sitzungen, die mit unterschiedlichen Anmelde Informationen gestartet wurden,

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Psprovider

Gibt den PowerShell-Anbieter an, der Laufwerke dieser Art unterstützt.

Wenn das Laufwerk z. b. einer Netzwerkfreigabe oder einem Dateisystem Verzeichnis zugeordnet ist, ist der PowerShell-Anbieter `FileSystem` . Wenn das Laufwerk einem Registrierungsschlüssel zugeordnet ist, ist der Anbieter `Registry` .

Temporäre PowerShell-Laufwerke können einem beliebigen PowerShell-Anbieter zugeordnet werden. Zugeordnete Netzwerklaufwerke können nur dem Anbieter zugeordnet werden `FileSystem` .

Verwenden Sie das-Cmdlet, um eine Liste der Anbieter in ihrer PowerShell-Sitzung anzuzeigen `Get-PSProvider` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Root

Gibt den Speicherort des Datenspeicher Orts an, dem ein PowerShell-Laufwerk zugeordnet ist.

Geben Sie z. b. eine Netzwerkfreigabe an, z `\\Server01\Public` . b. ein lokales Verzeichnis, z `C:\Program Files` . b. oder einen Registrierungsschlüssel, z `HKLM:\Software\Microsoft` . b..

Temporäre PowerShell-Laufwerke können einem lokalen Speicherort oder einem Remote Speicherort auf einem beliebigen unterstützten Anbieter Laufwerk zugeordnet werden. Zugeordnete Netzwerklaufwerke können nur einem Dateisystemspeicherort auf einem Remotecomputer zugeordnet sein.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Bereich

Gibt einen Bereich für das Laufwerk an. Die zulässigen Werte für diesen Parameter lauten: **Global** , **local** und **Script** oder eine Zahl relativ zum aktuellen Bereich. Bereiche mit der Zahl 0 bis zur Anzahl der Bereiche. Die aktuelle Bereichs Nummer ist 0 und das übergeordnete Element ist 1. Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseTransaction

Schließt den Befehl in die aktive Transaktion ein. Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird. Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Sie können keine Eingabe für dieses Cmdlet ausführen.

## AUSGABEN

### System.Management.Automation.PSDrivin FO

## HINWEISE

`New-PSDrive` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, verwenden Sie `Get-PSProvider` . Weitere Informationen zu Anbietern finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

Zugeordnete Netzwerklaufwerke sind bestimmten Benutzerkonten zugeordnet. Zugeordnete Laufwerke, die mit den Anmelde Informationen eines anderen Benutzers in erweiterten Sitzungen oder Sitzungen erstellt wurden, sind in Sitzungen, die mit unterschiedlichen Anmelde Informationen gestartet wurden,

## VERWANDTE LINKS

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Get-PSDrive](Get-PSDrive.md)

[Remove-PSDrive](Remove-PSDrive.md)
