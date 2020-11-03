---
description: Beschreibt, wie benutzerdefinierte Standardwerte für Cmdlet-Parameter und erweiterte Funktionen festgelegt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 5/31/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters_default_values?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters_Default_Values
ms.openlocfilehash: 0e19241549b53bac9a57de183f2896985f94d116
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221404"
---
# <a name="about-parameters-default-values"></a>Informationen zu Standardwerten von Parametern

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt, wie benutzerdefinierte Standardwerte für Cmdlet-Parameter und erweiterte Funktionen festgelegt werden.

## <a name="long-description"></a>Lange Beschreibung

Die Einstellungs `$PSDefaultParameterValues` Variable ermöglicht Ihnen die Angabe benutzerdefinierter Standardwerte für beliebige Cmdlets oder erweiterte Funktionen. Cmdlets und erweiterte Funktionen verwenden den benutzerdefinierten Standardwert, es sei denn, Sie geben im Befehl einen anderen Wert an.

Die Autoren von Cmdlets und erweiterten Funktionen legen standardmäßige Standardwerte für Ihre Parameter fest. Normalerweise sind die Standard Standardwerte nützlich, aber Sie sind möglicherweise nicht für alle Umgebungen geeignet.

Diese Funktion ist besonders nützlich, wenn Sie den gleichen alternativen Parameterwert fast jedes Mal angeben müssen, wenn Sie den Befehl verwenden, oder wenn ein bestimmter Parameterwert schwer zu merken ist, z. b. ein e-Mail-Servername oder eine Projekt-GUID.

Wenn der gewünschte Standardwert erwartungsgemäß variiert, können Sie einen Skriptblock angeben, der unterschiedlichen Bedingungen unterschiedliche Standardwerte für einen Parameter bereitstellt.

`$PSDefaultParameterValues` wurde in PowerShell 3,0 eingeführt.

## <a name="syntax"></a>Syntax

Die- `$PSDefaultParameterValues` Variable ist eine Hash Tabelle, die das Format der Schlüssel als Objekttyp von **System. Management. Automation. defaultparameterdictionary** überprüft. Die Hash Tabelle enthält **Schlüssel-Wert-** Paare. Ein **Schlüssel** weist das Format auf `CmdletName:ParameterName` . Ein **Wert** ist der **DefaultValue** oder **ScriptBlock** , der dem Schlüssel zugewiesen ist.

Die Syntax der `$PSDefaultParameterValues` Preference-Variablen lautet wie folgt:

```
$PSDefaultParameterValues=@{"CmdletName:ParameterName"="DefaultValue"}

$PSDefaultParameterValues=@{ "CmdletName:ParameterName"={{ScriptBlock}} }

$PSDefaultParameterValues["Disabled"]=$True | $False
```

Platzhalter Zeichen sind in den Werten " **cmdletname** " und " **Parameter Name** " zulässig.

Um ein bestimmtes **Schlüssel-Wert-** Paar aus festzulegen, zu ändern, hinzuzufügen oder zu entfernen, `$PSDefaultParameterValues` verwenden Sie die-Methoden, um eine Standard Hash Tabelle zu bearbeiten. Beispielsweise die Methoden zum **Hinzufügen** und **Entfernen** . Diese Methoden überschreiben keine anderen Werte in der Hash Tabelle.

Es gibt eine weitere Syntax, die eine vorhandene `$PSDefaultParameterValues` Hash Tabelle nicht überschreibt. Verwenden Sie die folgende Syntax, um ein bestimmtes **Schlüssel-Wert-** Paar hinzuzufügen oder zu ändern:

```
$PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

Der **cmdletname** muss der Name eines Cmdlets oder der Name einer erweiterten Funktion sein, die das **cmdletbinding** -Attribut verwendet. Sie können nicht verwenden `$PSDefaultParameterValues` , um Standardwerte für Skripts oder einfache Funktionen anzugeben.

Der **DefaultValue** kann ein Objekt oder ein Skriptblock sein. Wenn es sich bei dem Wert um einen Skriptblock handelt, wertet PowerShell den Skriptblock aus und verwendet das Ergebnis als Parameterwert. Wenn der angegebene Parameter einen Skriptblock Wert akzeptiert, schließen Sie den Wert für den Skriptblock in einen zweiten Satz geschweifter Klammern ein, z. b.:

```powershell
$PSDefaultParameterValues=@{ "Invoke-Command:ScriptBlock"={{Get-Process}} }
```

Weitere Informationen finden Sie in den folgenden Dokumenten:

- [about_Hash_Tables](about_Hash_Tables.md)
- [about_Script_Blocks](about_Script_Blocks.md)
- [about_Preference_Variables](about_Preference_Variables.md)

## <a name="examples"></a>Beispiele

### <a name="how-to-set-psdefaultparametervalues"></a>Festlegen von " \$ psdefaultparametervalues"

`$PSDefaultParameterValues` ist eine bevorzugte Variable, sodass Sie nur in der Sitzung vorhanden ist, in der Sie festgelegt ist. Er besitzt keinen Standardwert.

Um festzulegen `$PSDefaultParameterValues` , geben Sie den Variablennamen und mindestens ein **Schlüssel-Wert** -Paar ein. Wenn Sie einen anderen `$PSDefaultParameterValues` Befehl ausführen, wird die vorhandene Hash Tabelle überschrieben.

Beispiele dazu, wie Sie **Schlüssel-Wert-** Paare ändern können, ohne vorhandene Hash Tabellenwerte zu überschreiben, finden [Sie unter Hinzufügen von Werten zu \$ psdefaultparametervalues](#how-to-add-values-to-psdefaultparametervalues) oder [Ändern von Werten in " \$ psdefaultparametervalues](#how-to-change-values-in-psdefaultparametervalues)".

`$PSDefaultParameterValues`Fügen Sie Ihrem PowerShell-Profil einen Befehl hinzu, um Sie für zukünftige Sitzungen zu speichern `$PSDefaultParameterValues` . Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).

#### <a name="set-a-custom-default-value"></a>Festlegen eines benutzerdefinierten Standardwerts

Das **Schlüssel-Wert-** paar legt den `Send-MailMessage:SmtpServer` Schlüssel auf einen benutzerdefinierten Standardwert von **Server123** fest.

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
}
```

#### <a name="set-default-values-for-multiple-parameters"></a>Festlegen von Standardwerten für mehrere Parameter

Zum Festlegen von Standardwerten für mehrere Parameter trennen Sie die einzelnen **Schlüssel-Wert-** Paare durch ein Semikolon ( `;` ). Die `Send-MailMessage:SmtpServer` `Get-WinEvent:LogName` Schlüssel und werden auf benutzerdefinierte Standardwerte festgelegt.

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123";
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
}
```

#### <a name="use-wildcards-and-switch-parameters"></a>Verwenden von Platzhaltern und Switch-Parametern

Die Cmdlet-und Parameternamen können Platzhalter Zeichen enthalten. Verwenden `$True` `$False` Sie und, um Werte für Switch-Parameter wie " **verbose** " festzulegen. Der **verbose** -Parameter des Common-Parameters ist `$True` für alle Befehle auf festgelegt.

```powershell
$PSDefaultParameterValues = @{"*:Verbose"=$True}
```

#### <a name="use-an-array-for-the-default-value"></a>Array als Standardwert verwenden

Wenn ein Parameter mehrere Werte (ein Array) akzeptieren kann, können Sie mehrere Werte als Standardwerte festlegen. Der Standardwert des `Invoke-Command:ComputerName` Schlüssels wird auf einen Arraywert von **Server01** und **Server02** festgelegt.

```powershell
$PSDefaultParameterValues = @{
  "Invoke-Command:ComputerName"="Server01","Server02"
}
```

#### <a name="use-a-script-block"></a>Verwenden eines Skript Blocks

Sie können einen Skriptblock verwenden, um unterschiedlichen Bedingungen unterschiedliche Standardwerte für einen Parameter anzugeben. PowerShell wertet den Skriptblock aus und verwendet das Ergebnis als Standardparameter Wert.

Mit dem Schlüssel wird der `Format-Table:AutoSize` Switch-Parameter auf den Standard **Wert true** festgelegt. Die- `If` Anweisung enthält eine Bedingung, dass die `$host.Name` PowerShell-Konsole, **ConsoleHost** , sein muss.

```powershell
$PSDefaultParameterValues=@{
  "Format-Table:AutoSize"={if ($host.Name -eq "ConsoleHost"){$True}}
}
```

Wenn ein Parameter einen Skriptblock Wert akzeptiert, schließen Sie den Skriptblock in einen zusätzlichen Satz von geschweiften Klammern ein. Wenn PowerShell den äußeren Skriptblock auswertet, ist das Ergebnis der innere Skriptblock, der als Standardparameter Wert festgelegt wird.

Der `Invoke-Command:ScriptBlock` Schlüssel, der auf einen Standardwert des **System Ereignis Protokolls** festgelegt ist, da der Skriptblock in einem zweiten Satz von geschweiften Klammern eingeschlossen ist. Das Ergebnis des Skript Blocks wird an das `Invoke-Command` Cmdlet übergeben.

```powershell
$PSDefaultParameterValues=@{
  "Invoke-Command:ScriptBlock"={{Get-EventLog -Log System}}
}
```

### <a name="how-to-get-psdefaultparametervalues"></a>So erhalten Sie \$ psdefaultparametervalues

Die Hash Tabellenwerte werden angezeigt, wenn Sie `$PSDefaultParameterValues` an der PowerShell-Eingabeaufforderung eingeben.

Eine `$PSDefaultParameterValues` Hash Tabelle wird mit drei **Schlüssel-Wert-** Paaren festgelegt.
Diese Hash Tabelle wird in den folgenden Beispielen verwendet, in denen beschrieben wird, wie Werte hinzugefügt, geändert und entfernt werden `$PSDefaultParameterValues` .

```
PS> $PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
  "Get-*:Verbose"=$True
}

PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

Um den Wert eines bestimmten Schlüssels zu erhalten `CmdletName:ParameterName` , verwenden Sie die folgende Syntax:

```
$PSDefaultParameterValues["CmdletName:ParameterName"]
```

Zum Beispiel, um den Wert für den Schlüssel zu erhalten `Send-MailMessage:SmtpServer` .

```
PS> $PSDefaultParameterValues["Send-MailMessage:SmtpServer"]
Server123
```

### <a name="how-to-add-values-to-psdefaultparametervalues"></a>Hinzufügen von Werten zu \$ psdefaultparametervalues

Wenn Sie einen Wert hinzufügen möchten `$PSDefaultParameterValues` , verwenden **Sie die Add** -Methode. Das Hinzufügen eines Werts wirkt sich nicht auf die vorhandenen Werte der Hash Tabelle aus.

Verwenden Sie ein Komma ( `,` ), um den **Schlüssel** von dem **Wert** zu trennen. Die folgende Syntax zeigt die Verwendung der **Add** -Methode für `$PSDefaultParameterValues` .

```
PS> $PSDefaultParameterValues.Add("CmdletName:ParameterName", "DefaultValue")
```

Die Hash Tabelle, die im vorherigen Beispiel erstellt wurde, wird mit einem neuen **Schlüssel-Wert-** paar aktualisiert. Die **Add** -Methode legt den `Get-Process:Name` Schlüssel auf den Wert **PowerShell** fest.

```powershell
$PSDefaultParameterValues.Add("Get-Process:Name", "PowerShell")
```

Mit der folgenden Syntax wird das gleiche Ergebnis erreicht.

```powershell
$PSDefaultParameterValues["Get-Process:Name"]="PowerShell"
```

Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an. Der `Get-Process:Name` Schlüssel wurde hinzugefügt.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-Process:Name               PowerShell
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-remove-values-from-psdefaultparametervalues"></a>Entfernen von Werten aus \$ psdefaultparametervalues

Um einen Wert aus zu entfernen `$PSDefaultParameterValues` , verwenden Sie die **Remove** -Methode von Hash Tabellen. Das Entfernen eines Werts wirkt sich nicht auf die vorhandenen Werte der Hash Tabelle aus.

Die folgende Syntax zeigt, wie Sie die **Remove** -Methode für verwenden `$PSDefaultParameterValues` .

```
PS> $PSDefaultParameterValues.Remove("CmdletName:ParameterName")
```

In diesem Beispiel wird die im vorherigen Beispiel erstellte Hash Tabelle aktualisiert, um ein **Schlüssel-Wert-** paar zu entfernen. Mit der **Remove** -Methode wird der `Get-Process:Name` Schlüssel entfernt.

```powershell
$PSDefaultParameterValues.Remove("Get-Process:Name")
```

Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an. Der `Get-Process:Name` Schlüssel wurde entfernt.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-change-values-in-psdefaultparametervalues"></a>Ändern von Werten in " \$ psdefaultparametervalues"

Änderungen an einem bestimmten Wert wirken sich nicht auf vorhandene Hash Tabellenwerte aus. Verwenden Sie die folgende Syntax, um ein bestimmtes **Schlüssel-Wert-** Paar in zu ändern `$PSDefaultParameterValues` :

```
PS> $PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

In diesem Beispiel wird die im vorherigen Beispiel erstellte Hash Tabelle aktualisiert, um ein **Schlüssel-Wert-** paar zu ändern. Mit dem folgenden Befehl wird der `Send-MailMessage:SmtpServer` Schlüssel in den neuen Wert **serverxyz** geändert.

```powershell
$PSDefaultParameterValues["Send-MailMessage:SmtpServer"]="ServerXYZ"
```

Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an. Der `Send-MailMessage:SmtpServer` Schlüssel wurde in einen neuen Wert geändert.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

### <a name="how-to-disable-and-re-enable-psdefaultparametervalues"></a>Deaktivieren und erneutes Aktivieren von \$ psdefaultparametervalues

Sie können den temporär deaktivieren und dann erneut aktivieren `$PSDefaultParameterValues` .
Die Deaktivierung `$PSDefaultParameterValues` ist nützlich, wenn Sie Skripts ausführen, die unterschiedliche Standardparameter Werte benötigen.

Um dies zu deaktivieren `$PSDefaultParameterValues` , fügen Sie einen Schlüssel `Disabled` mit dem Wert **true** hinzu. Die Werte in `$PSDefaultParameterValues` bleiben erhalten, sind aber nicht wirksam.

```
PS> $PSDefaultParameterValues.Add("Disabled", $True)
```

Mit der folgenden Syntax wird das gleiche Ergebnis erreicht.

```
PS> $PSDefaultParameterValues["Disabled"]=$True
```

Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle mit dem Wert für den `Disabled` Schlüssel an.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       True
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

Entfernen Sie zum erneuten Aktivieren `$PSDefaultParameterValues` den **deaktivierten** Schlüssel, oder ändern Sie den Wert des **deaktivierten** Schlüssels in `$False` . Der vorherige Wert von `$PSDefaultParameterValues` ist erneut wirksam.

```
PS> $PSDefaultParameterValues.Remove("Disabled")
```

Mit der folgenden Syntax wird das gleiche Ergebnis erreicht.

```
PS> $PSDefaultParameterValues["Disabled"]=$False
```

Die `$PSDefaultParameterValues` Variable zeigt die aktualisierte Hash Tabelle an. Wenn die **Remove** -Methode verwendet wird, `Disabled` wird der Schlüssel aus der Ausgabe entfernt.
Wenn die alternative Syntax zum erneuten Aktivieren verwendet wurde `$PSDefaultParameterValues` , wird der `Disabled` Schlüssel als **false** angezeigt.

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       False
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

## <a name="see-also"></a>Weitere Informationen:

[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_Preference_Variables](about_Preference_Variables.md)

[about_Profiles](about_Profiles.md)

[about_Script_Blocks](about_Script_Blocks.md)
