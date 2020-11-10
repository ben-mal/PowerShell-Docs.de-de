---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PSSnapin
ms.openlocfilehash: a21c2974fd66a9b02929752ae487c8995579b8a7
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388823"
---
# Add-PSSnapin

## ZUSAMMENFASSUNG
Fügt ein oder mehrere Windows PowerShell-Snap-Ins zur aktuellen Sitzung hinzu.

## SYNTAX

```
Add-PSSnapin [-Name] <String[]> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Add-PSSnapin` Cmdlet werden registrierte Windows PowerShell-Snap-Ins zur aktuellen Sitzung hinzugefügt. Nach dem Hinzufügen der Snap-Ins können Sie die von den Snap-Ins unterstützten Cmdlets und Anbieter in der aktuellen Sitzung verwenden.

Fügen Sie `Add-PSSnapin` Ihrem Windows PowerShell-Profil einen Befehl hinzu, um das Snap-in zu allen zukünftigen Windows PowerShell-Sitzungen hinzuzufügen. Weitere Informationen finden Sie unter [about_Profiles](about/about_Profiles.md).

Ab Windows PowerShell 3.0 sind die in Windows PowerShell enthaltenen Hauptbefehle in Module gepackt. Eine Ausnahme ist das Snap-In **Microsoft.PowerShell.Core** (PSSnapin).
Standardmäßig wird nur das **Microsoft.PowerShell.Core** -Snap-In der Sitzung hinzugefügt. Module werden bei der ersten Verwendung automatisch importiert, und Sie können das Cmdlet "Import-Module" verwenden, um Sie zu importieren.

## BEISPIELE

### Beispiel 1: Hinzufügen von Snap-Ins

```powershell
PS C:\> Add-PSSnapIn -Name Microsoft.Exchange, Microsoft.Windows.AD
```

Dieser Befehl fügt die Microsoft Exchange- und Active Directory-Snap-Ins zur aktuellen Sitzung hinzu.

### Beispiel 2: Hinzufügen aller registrierten Snap-Ins

```powershell
PS C:\> Get-PSSnapin -Registered | Add-PSSnapin -Passthru
```

Dieser Befehl fügt alle registrierten Windows PowerShell-Snap-Ins zur Sitzung hinzu. Er verwendet das Cmdlet "Get-PSSnapin" mit dem **registrierten** Parameter, um Objekte zu erhalten, die die einzelnen registrierten Snap-Ins darstellen. Der Pipeline Operator (|) übergibt das Ergebnis an `Add-PSSnapin` , wodurch Sie der Sitzung hinzugefügt werden. Der **passthru** -Parameter gibt Objekte zurück, die die einzelnen hinzugefügten Snap-Ins darstellen.

### Beispiel 3: Registrieren eines Snap-Ins und Hinzufügen des Snap-Ins

Der erste Befehl ruft Snap-Ins ab, die der aktuellen Sitzung hinzugefügt wurden, die die mit Windows PowerShell installierten Snap-Ins enthalten. In diesem Beispiel wird ManagementFeatures nicht zurückgegeben. Dies gibt an, dass es nicht zur Sitzung hinzugefügt wurde.

Der zweite Befehl ruft Snap-Ins ab, die auf Ihrem System registriert wurden, einschließlich derjenigen, die der Sitzung bereits hinzugefügt wurden. Es sind keine Snap-Ins enthalten, die mit Windows PowerShell installiert werden. In diesem Fall gibt der Befehl keine Snap-Ins zurück. Dies gibt an, dass der Managementfeatures-Snap-in nicht auf dem System registriert wurde.

Mit dem dritten Befehl wird der Alias "installutil" für den Pfad des Tools "installutil" in .NET Framework erstellt.

Der vierte Befehl verwendet das Tool installutil, um das Snap-in zu registrieren. Mit dem Befehl wird der Pfad ManagementCmdlets.dll, der Dateiname oder der Modulname des Snap-Ins angegeben.

Der fünfte Befehl ist identisch mit dem zweiten Befehl. Dieses Mal wird er verwendet, um zu überprüfen, ob das ManagementCmdlets-Snap-In registriert ist.

Der sechste Befehl verwendet das `Add-PSSnapin` Cmdlet, um der Sitzung das Management Features-Snap-in hinzuzufügen. Der Befehl gibt den Namen des Snap-Ins (ManagementFeatures) und nicht den Dateinamen an.

Um sicherzustellen, dass das Snap-in der Sitzung hinzugefügt wird, verwendet der siebte Befehl den **Module** -Parameter des Get-Command Cmdlets. Der Parameter zeigt die Elemente an, die durch ein Snap-In oder ein Modul zur Sitzung hinzugefügt wurden.

Sie können auch die **PSSnapIn** -Eigenschaft des-Objekts verwenden, das vom `Get-Command` Cmdlet zurückgegeben wird, um das Snap-in oder Modul zu suchen, von dem ein Cmdlet stammt. Der achte Befehl verwendet die Punkt Notation, um den Wert der PSSnapIn-Eigenschaft des Set-Alias-Cmdlets zu suchen.

```powershell
PS C:\> Get-PSSnapin
PS C:\> Get-PSSnapin -Registered
PS C:\> Set-Alias installutil $env:windir\Microsoft.NET\Framework\v2.0.50727\installutil.exe
PS C:\> installutil C:\Dev\Management\ManagementCmdlets.dll
PS C:\> Get-PSSnapin -Registered
PS C:\> add-pssnapin ManagementFeatures
PS C:\> Get-Command -Module ManagementFeatures
PS C:\> (Get-Command Set-Alias).pssnapin
```

In diesem Beispiel wird veranschaulicht, wie ein Snap-In im System registriert und dann der Sitzung hinzugefügt wird. Er verwendet Managementfeatures, ein fiktives Snap-in, das in einer Datei mit dem Namen ManagementCmdlets.dll implementiert ist.

## PARAMETERS

### -Name

Gibt den Namen des Snap-Ins an. Dies ist der Name, nicht Assemblyname oder ModuleName. Platzhalter sind zulässig.

Geben Sie ein, um die Namen der registrierten Snap-Ins auf Ihrem System zu ermitteln `Get-PSSnapin -Registered` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

Gibt an, dass dieses Cmdlet ein Objekt zurückgibt, das die einzelnen hinzugefügten Snap-Ins darstellt. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### Keine
Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### None oder System. Management. Automation. pssnapininfo

Dieses Cmdlet gibt ein pssnapininfo-Objekt zurück, das das Snap-in darstellt, wenn Sie den **passthru** -Parameter angeben. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

- Ab Windows PowerShell 3.0 sind die mit Windows PowerShell installierten Hauptbefehle in Module gepackt. In Windows PowerShell 2,0 und in Host Programmen, die in neueren Versionen von Windows PowerShell ältere Sitzungen erstellen, werden die Hauptbefehle in Snap-Ins (pssnapins) gepackt. Die Ausnahme ist **Microsoft. PowerShell. Core** , bei der es sich immer um ein Snap-in handelt. Remote Sitzungen, wie z. b. diejenigen, die mit dem Cmdlet "New-PSSession" gestartet werden, sind auch ältere Sitzungen, die Core-Snap-Ins enthalten.

  Weitere Informationen über die **CreateDefault2** -Methode, die Sitzungen im neueren Stil mit Kernmodulen erstellt, finden Sie unter [CreateDefault2-Methode](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2).

- Weitere Informationen zu Snap-Ins finden Sie unter [about_PSSnapins](About/about_PSSnapins.md) und [Erstellen eines Windows PowerShell-Snap-](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in)ins.
- `Add-PSSnapin` Fügt das Snap-in nur zur aktuellen Sitzung hinzu. Um das Snap-In zu allen Windows PowerShell-Sitzungen hinzuzufügen, fügen Sie es zu Ihrem Windows PowerShell-Profil hinzu. Weitere Informationen finden Sie unter „about_Profiles“.
- Sie können ein beliebiges Snap-in hinzufügen, das mit dem Installationsprogramm für Microsoft .NET Framework registriert wurde. Weitere Informationen finden Sie unter [Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).
- Zum erhalten einer Liste von Snap-Ins, die auf Ihrem Computer registriert sind, geben Sie ein `Get-PSSnapin -Registered` .
- Vor dem Hinzufügen eines Snap-Ins `Add-PSSnapin` überprüft die Version des Snap-Ins, um zu überprüfen, ob es mit der aktuellen Version von Windows PowerShell kompatibel ist. Wenn das Snap-In die Versionsprüfung nicht besteht, meldet Windows PowerShell einen Fehler.

## VERWANDTE LINKS

[Get-PSSnapin](Get-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
