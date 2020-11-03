---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: f8575c97c4279f285598e2b1bdf94786d92c841a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216879"
---
# Set-ExecutionPolicy

## ZUSAMMENFASSUNG
Legt die PowerShell-Ausführungsrichtlinien für Windows-Computer fest.

## SYNTAX

### Alle

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-ExecutionPolicy` Cmdlet werden die PowerShell-Ausführungsrichtlinien für Windows-Computer geändert. Weitere Informationen finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

Ab PowerShell 6,0 für nicht-Windows-Computer ist die Standard Ausführungs Richtlinie **uneingeschränkt** und kann nicht geändert werden. Das `Set-ExecutionPolicy` -Cmdlet ist verfügbar, aber PowerShell zeigt eine Konsolen Meldung an, dass dies nicht unterstützt wird.

Eine Ausführungs Richtlinie ist Bestandteil der PowerShell-Sicherheitsstrategie. Ausführungsrichtlinien legen fest, ob Sie Konfigurationsdateien, z. b. Ihr PowerShell-Profil, laden oder Skripts ausführen können. Und, ob Skripts vor der Durchführung digital signiert werden müssen.

Der `Set-ExecutionPolicy` Standardbereich des Cmdlets ist " **LocalMachine** ", was sich auf alle Benutzer auswirkt, die den Computer verwenden. Um die Ausführungs Richtlinie für **LocalMachine** zu ändern, starten Sie PowerShell mit **als Administrator ausführen** .

Verwenden Sie, um die Ausführungsrichtlinien für jeden Bereich in der Rangfolge anzuzeigen `Get-ExecutionPolicy -List` . Um die effektive Ausführungs Richtlinie für Ihre PowerShell-Sitzung anzuzeigen, verwenden Sie `Get-ExecutionPolicy` ohne Parameter.

## BEISPIELE

### Beispiel 1: Festlegen einer Ausführungs Richtlinie

In diesem Beispiel wird gezeigt, wie die Ausführungs Richtlinie für den lokalen Computer festgelegt wird.

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

Das `Set-ExecutionPolicy` Cmdlet verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben. Der **Scope** -Parameter gibt den Standard Bereichs Wert **LocalMachine** an. Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.

### Beispiel 2: Festlegen einer Ausführungs Richtlinie, die in Konflikt mit einer Gruppenrichtlinie

Dieser Befehl versucht, die Ausführungs Richtlinie für den **LocalMachine** -Bereich auf " **restricted** " festzulegen.
" **LocalMachine** " ist restriktiver, aber nicht die wirksame Richtlinie, da Sie mit einer Gruppenrichtlinie in Konflikt steht. Die **Eingeschränkte** Richtlinie wird in die Registrierungs Struktur **HKEY_LOCAL_MACHINE** geschrieben.

```
PS> Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine

Set-ExecutionPolicy : PowerShell updated your local preference successfully, but the setting is
overridden by the Group Policy applied to your system. Due to the override, your shell will retain
its current effective execution policy of "AllSigned". Contact your Group Policy administrator for
more information. At line:1 char:20 + Set-ExecutionPolicy <<<< restricted

PS> Get-ChildItem -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\1\ShellIds

Name                    Property
----                    --------
Microsoft.PowerShell    Path            : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
                        ExecutionPolicy : Restricted
ScriptedDiagnostics     ExecutionPolicy : Unrestricted
```

Das `Set-ExecutionPolicy` Cmdlet verwendet den **ExecutionPolicy** -Parameter zum Angeben der **eingeschränkten** Richtlinie. Der **Scope** -Parameter gibt den Standard Bereichs Wert **LocalMachine** an.
Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter mit dem **HKLM** -Anbieter, um den Registrierungs Speicherort anzugeben.

### Beispiel 3: Anwenden der Ausführungs Richtlinie von einem Remote Computer auf einen lokalen Computer

Mit diesem Befehl wird das Objekt der Ausführungs Richtlinie von einem Remote Computer abgerufen, und die Richtlinie wird auf dem lokalen Computer festgelegt. `Get-ExecutionPolicy` sendet ein **Microsoft.PowerShell.Executionpolicy** -Objekt über die Pipeline. `Set-ExecutionPolicy` akzeptiert Pipeline Eingaben und erfordert keinen **ExecutionPolicy** -Parameter.

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

Das `Invoke-Command` -Cmdlet wird auf dem lokalen Computer ausgeführt und sendet den **ScriptBlock** an den Remote Computer. Der **Computername** -Parameter gibt den Remote Computer an, **Server01** . Der **ScriptBlock** -Parameter wird `Get-ExecutionPolicy` auf dem Remote Computer ausgeführt. Das `Get-ExecutionPolicy` Objekt wird über die Pipeline an das-Objekt gesendet `Set-ExecutionPolicy` .
`Set-ExecutionPolicy` wendet die Ausführungs Richtlinie auf den Standardbereich " **LocalMachine** " des lokalen Computers an.

### Beispiel 4: Festlegen des Gültigkeits Bereichs für eine Ausführungs Richtlinie

Dieses Beispiel zeigt, wie eine Ausführungs Richtlinie für einen angegebenen Bereich, **CurrentUser** , festgelegt wird. Der Bereich " **CurrentUser** " wirkt sich nur auf den Benutzer aus, der diesen Bereich festlegt.

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

`Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **AllSigned** -Richtlinie anzugeben.
Der **Scope** -Parameter gibt den **CurrentUser** an. Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.

Die effektive Ausführungs Richtlinie für den Benutzer wird zu **AllSigned** .

### Beispiel 5: Entfernen der Ausführungs Richtlinie für den aktuellen Benutzer

In diesem Beispiel wird gezeigt, wie die nicht **definierte** Ausführungs Richtlinie verwendet wird, um eine Ausführungs Richtlinie für einen bestimmten Bereich zu entfernen.

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

`Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die nicht **definierte** Richtlinie anzugeben.
Der **Scope** -Parameter gibt den **CurrentUser** an. Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.

### Beispiel 6: Festlegen der Ausführungs Richtlinie für die aktuelle PowerShell-Sitzung

Der **Prozess** Bereich wirkt sich nur auf die aktuelle PowerShell-Sitzung aus. Die Ausführungs Richtlinie wird in der Umgebungsvariablen gespeichert `$env:PSExecutionPolicyPreference` und beim Schließen der Sitzung gelöscht.

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope Process
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       AllSigned
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

Der `Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **AllSigned** -Richtlinie anzugeben. Der **Scope** -Parameter gibt den Wert **Prozess** an. Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.

### Beispiel 7: Entsperren eines Skripts, um es auszuführen, ohne die Ausführungs Richtlinie zu ändern

Dieses Beispiel zeigt, wie die **RemoteSigned** -Ausführungs Richtlinie verhindert, dass nicht signierte Skripts ausgeführt werden.

Eine bewährte Vorgehensweise besteht darin, den Skriptcode zu lesen und zu überprüfen, ob er sicher ist, **bevor** Sie das `Unblock-File` Cmdlet verwenden. Das- `Unblock-File` Cmdlet entsperrt Skripts, sodass Sie ausgeführt werden können, ändert jedoch nicht die Ausführungs Richtlinie.

```
PS> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

.\Start-ActivityTracker.ps1 : File .\Start-ActivityTracker.ps1 cannot be loaded.
The file .\Start-ActivityTracker.ps1 is not digitally signed.
The script will not execute on the system.
For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], PSSecurityException
+ FullyQualifiedErrorId : UnauthorizedAccess

PS> Unblock-File -Path .\Start-ActivityTracker.ps1

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

Task 1:
```

Der `Set-ExecutionPolicy` verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben. Die Richtlinie wird für den Standardbereich **LocalMachine** festgelegt.

Das- `Get-ExecutionPolicy` Cmdlet zeigt, dass **RemoteSigned** die effektive Ausführungs Richtlinie für die aktuelle PowerShell-Sitzung ist.

Das **Start-ActivityTracker.ps1** Skript wird aus dem aktuellen Verzeichnis ausgeführt. Das Skript wird von **RemoteSigned** blockiert, da das Skript nicht digital signiert ist.

In diesem Beispiel wurde der Code des Skripts überprüft und als sicher für die Durchführung überprüft. Das `Unblock-File` Cmdlet verwendet den **path** -Parameter, um die Blockierung des Skripts aufzulösen.

Um zu überprüfen, ob `Unblock-File` die Ausführungs Richtlinie nicht geändert wurde, `Get-ExecutionPolicy` zeigt die effektive Ausführungs Richtlinie " **RemoteSigned** " an.

Das Skript, **Start-ActivityTracker.ps1** aus dem aktuellen Verzeichnis ausgeführt wird. Das Skript beginnt mit der Durchführung der Blockierung durch das `Unblock-File` Cmdlet.

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

### -ExecutionPolicy

Gibt die Ausführungs Richtlinie an. Wenn keine Gruppenrichtlinien vorhanden sind und die Ausführungs Richtlinie jedes Bereichs auf "nicht **definiert** " festgelegt ist, wird die eingeschränkte Richtlinie für alle Benutzer **eingeschränkt** .

Die zulässigen Werte für die Ausführungs Richtlinie lauten wie folgt:

- Alle **signiert** . Erfordert, dass alle Skripts und Konfigurationsdateien von einem vertrauenswürdigen Herausgeber signiert werden, einschließlich der auf dem lokalen Computer geschriebenen Skripts.
- **Umgehung** . Es findet keine Blockierung statt und es werden keine Warnungen oder Eingabeaufforderungen ausgegeben.
- **Default** . Legt die Standard Ausführungs Richtlinie fest. **Eingeschränkt** für Windows-Clients oder **RemoteSigned** für Windows-Server.
- **RemoteSigned** . Erfordert, dass alle aus dem Internet heruntergeladenen Skripts und Konfigurationsdateien von einem vertrauenswürdigen Herausgeber signiert werden. Die Standard Ausführungs Richtlinie für Windows Server-Computer.
- **Eingeschränkt** . Lädt keine Konfigurationsdateien und führt keine Skripts aus. Die Standard-Ausführungs Richtlinie für Windows-Client Computer.
- Nicht **definiert** . Für den Bereich wurde keine Ausführungs Richtlinie festgelegt. Entfernt eine zugewiesene Ausführungs Richtlinie aus einem Bereich, der nicht von einem Gruppenrichtlinie festgelegt ist. Wenn die Ausführungs Richtlinie in allen Bereichen nicht **definiert** ist, ist die effektive Ausführungs Richtlinie **eingeschränkt** .
- **Uneingeschränkt** . Ab PowerShell 6,0 ist dies die Standard Ausführungs Richtlinie für nicht-Windows-Computer und kann nicht mehr geändert werden. Lädt alle Konfigurationsdateien und führt alle Skripts aus. Wenn Sie ein nicht signiertes Skript ausführen, das aus dem Internet heruntergeladen wurde, werden Sie zur Eingabe der Berechtigung aufgefordert, bevor es ausgeführt wird.

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: AllSigned, Bypass, Default, RemoteSigned, Restricted, Undefined, Unrestricted

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force

Unterdrückt alle Bestätigungsaufforderungen. Verwenden Sie diesen Parameter als Vorsicht, um unerwartete Ergebnisse zu vermeiden.

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

### -Bereich

Gibt den Bereich an, der von einer Ausführungs Richtlinie betroffen ist. Der Standardbereich ist **LocalMachine** .

Die effektive Ausführungs Richtlinie wird wie folgt durch die Rangfolge bestimmt:

- **MachinePolicy** . Wird von einem Gruppenrichtlinie für alle Benutzer des Computers festgelegt.
- **UserPolicy** . Wird von einem Gruppenrichtlinie für den aktuellen Benutzer des Computers festgelegt.
- **Verarbeiten** . Wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.
- **CurrentUser** . Wirkt sich nur auf den aktuellen Benutzer aus.
- **LocalMachine** . Standardbereich, der sich auf alle Benutzer des Computers auswirkt.

Der **Prozess** Bereich wirkt sich nur auf die aktuelle PowerShell-Sitzung aus. Die Ausführungs Richtlinie wird in der-Umgebungsvariablen und `$env:PSExecutionPolicyPreference` nicht in der Registrierung gespeichert. Wenn die PowerShell-Sitzung geschlossen ist, werden die Variable und der Wert gelöscht.

Ausführungsrichtlinien für den Bereich **CurrentUser** werden in die Registrierungs Struktur **HKEY_LOCAL_USER** geschrieben.

Ausführungsrichtlinien für den Bereich " **LocalMachine** " werden in die Registrierungs Struktur **HKEY_LOCAL_MACHINE** geschrieben.

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 1
Default value: LocalMachine
Accept pipeline input: True (ByPropertyName)
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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Microsoft.PowerShell.Executionpolicy, System. String

Sie können ein Ausführungsrichtlinien Objekt oder eine Zeichenfolge, die den Namen einer Ausführungs Richtlinie enthält, über die Pipeline an übergeben `Set-ExecutionPolicy` .

## AUSGABEN

### Keine

`Set-ExecutionPolicy` gibt keine Ausgabe zurück.

## HINWEISE

`Set-ExecutionPolicy` ändert nicht die Bereiche **MachinePolicy** und **UserPolicy** , da diese durch Gruppenrichtlinien festgelegt werden.

`Set-ExecutionPolicy` überschreibt eine Gruppenrichtlinie nicht, auch wenn die Benutzereinstellung restriktiver als die Richtlinie ist.

Wenn die Gruppenrichtlinie **Skriptausführung** aktivieren für den Computer oder Benutzer aktiviert ist, wird die Benutzereinstellung gespeichert, aber Sie ist nicht wirksam. PowerShell zeigt eine Meldung an, in der der Konflikt erläutert wird.

## VERWANDTE LINKS

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[about_Group_Policy_Settings](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[Get-ExecutionPolicy](Get-ExecutionPolicy.md)

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)

[Unblock-File](../Microsoft.PowerShell.Utility/Unblock-File.md)
