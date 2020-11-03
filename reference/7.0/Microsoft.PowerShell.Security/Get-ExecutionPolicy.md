---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: 2bd5854b689fad077f6a3df2e37693cff973a62a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210932"
---
# Get-ExecutionPolicy

## ZUSAMMENFASSUNG
Ruft die Ausführungsrichtlinien für die aktuelle Sitzung ab.

## SYNTAX

### Alle

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## DESCRIPTION

Verwenden Sie, um die Ausführungsrichtlinien für jeden Bereich in der Rangfolge anzuzeigen `Get-ExecutionPolicy -List` . Um die effektive Ausführungs Richtlinie für Ihre PowerShell-Sitzung anzuzeigen, verwenden Sie `Get-ExecutionPolicy` ohne Parameter.

Die effektive Ausführungs Richtlinie wird durch die von und festgelegten Ausführungsrichtlinien `Set-ExecutionPolicy` und Gruppenrichtlinie Einstellungen bestimmt.

Weitere Informationen finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

## BEISPIELE

### Beispiel 1: alle Ausführungsrichtlinien

Dieser Befehl zeigt die Ausführungsrichtlinien für jeden Bereich in der Rangfolge an.

```powershell
Get-ExecutionPolicy -List
```

```Output
Scope          ExecutionPolicy
-----          ---------------
MachinePolicy  Undefined
UserPolicy     Undefined
Process        Undefined
CurrentUser    AllSigned
LocalMachine   Undefined
```

Das `Get-ExecutionPolicy` Cmdlet verwendet den **List** -Parameter, um die Ausführungs Richtlinie jedes Bereichs anzuzeigen.

### Beispiel 2: Festlegen einer Ausführungs Richtlinie

Dieses Beispiel zeigt, wie eine Ausführungs Richtlinie für den lokalen Computer festgelegt wird.

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
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

Das `Set-ExecutionPolicy` Cmdlet verwendet den **ExecutionPolicy** -Parameter, um die **RemoteSigned** -Richtlinie anzugeben. Der **Scope** -Parameter gibt den Standard Bereichs Wert **LocalMachine** an. Verwenden Sie das `Get-ExecutionPolicy` Cmdlet mit dem **List** -Parameter, um die Einstellungen für die Ausführungs Richtlinie anzuzeigen.

### Beispiel 3: erhalten der effektiven Ausführungs Richtlinie

Dieses Beispiel zeigt, wie die effektive Ausführungs Richtlinie für eine PowerShell-Sitzung angezeigt wird.

```
PS> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned

PS> Get-ExecutionPolicy

AllSigned
```

Das `Get-ExecutionPolicy` Cmdlet verwendet den **List** -Parameter, um die Ausführungs Richtlinie jedes Bereichs anzuzeigen. Das `Get-ExecutionPolicy` Cmdlet wird ohne einen Parameter ausgeführt, um die effektive Ausführungs Richtlinie " **AllSigned** " anzuzeigen.

### Beispiel 4: Entsperren eines Skripts, um es auszuführen, ohne die Ausführungs Richtlinie zu ändern

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

### -List

Ruft alle Ausführungsrichtlinienwerte für die Sitzung nach ihrer Rangfolge ab. Standardmäßig ruft `Get-ExecutionPolicy` nur die effektive Ausführungs Richtlinie ab.

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

### -Bereich

Gibt den Bereich an, der von einer Ausführungs Richtlinie betroffen ist.

Die effektive Ausführungs Richtlinie wird wie folgt durch die Rangfolge bestimmt:

- **MachinePolicy** . Wird von einem Gruppenrichtlinie für alle Benutzer des Computers festgelegt.
- **UserPolicy** . Wird von einem Gruppenrichtlinie für den aktuellen Benutzer des Computers festgelegt.
- **Verarbeiten** . Wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.
- **CurrentUser** . Wirkt sich nur auf den aktuellen Benutzer aus.
- **LocalMachine** . Standardbereich, der sich auf alle Benutzer des Computers auswirkt.

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 0
Default value: Effective execution policy
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

`Get-ExecutionPolicy` akzeptiert keine Eingaben aus der Pipeline.

## AUSGABEN

### Microsoft.PowerShell.Executionpolicy

## HINWEISE

Eine Ausführungs Richtlinie ist Bestandteil der PowerShell-Sicherheitsstrategie. Ausführungsrichtlinien legen fest, ob Sie Konfigurationsdateien, z. b. Ihr PowerShell-Profil, laden oder Skripts ausführen können. Und, ob Skripts vor der Durchführung digital signiert werden müssen.

## VERWANDTE LINKS

[about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[about_Group_Policy_Settings](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)

[Set-ExecutionPolicy](Set-ExecutionPolicy.md)
