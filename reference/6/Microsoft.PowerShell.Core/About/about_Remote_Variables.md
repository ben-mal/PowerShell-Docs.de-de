---
description: Erläutert die Verwendung von lokalen und Remotevariablen in Remotebefehlen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_variables?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Variables
ms.openlocfilehash: 813b961d6e59dd85e09a461f8b5743924fecc673
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221247"
---
# <a name="about-remote-variables"></a>Informationen zu Remote Variablen

## <a name="short-description"></a>Kurze Beschreibung

Erläutert die Verwendung von lokalen und Remotevariablen in Remotebefehlen.

## <a name="long-description"></a>Lange Beschreibung

Sie können Variablen in Befehlen verwenden, die Sie auf Remote Computern ausführen. Weisen Sie der Variablen einen Wert zu, und verwenden Sie dann die Variable anstelle des Werts.

Standardmäßig wird davon ausgegangen, dass die Variablen in Remote Befehlen in der Sitzung definiert werden, die den Befehl ausführt. Variablen, die in einer lokalen Sitzung definiert sind, müssen im Befehl als lokale Variablen identifiziert werden.

## <a name="using-remote-variables"></a>Verwenden von Remote Variablen

PowerShell geht davon aus, dass die in Remote Befehlen verwendeten Variablen in der Sitzung definiert sind, in der der Befehl ausgeführt wird.

In diesem Beispiel wird die `$ps` Variable in der temporären Sitzung definiert, in der der `Get-WinEvent` Befehl ausgeführt wird.

```powershell
Invoke-Command -ComputerName S1 -ScriptBlock {
  $ps = "*PowerShell*"; Get-WinEvent -LogName $ps
}
```

Wenn der Befehl in einer persistenten Sitzung ( **PSSession** ) ausgeführt wird, muss die Remote Variable in dieser Sitzung definiert werden.

```powershell
$s = New-PSSession -ComputerName S1
Invoke-Command -Session $s -ScriptBlock {$ps = "*PowerShell*"}
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $ps}
```

## <a name="using-local-variables"></a>Verwenden lokaler Variablen

Sie können lokale Variablen in Remote Befehlen verwenden, aber die Variable muss in der lokalen Sitzung definiert werden.

Ab PowerShell 3,0 können Sie den bereichsmodifizierer verwenden, `Using` um eine lokale Variable in einem Remote Befehl zu identifizieren.

Die Syntax von `Using` lautet wie folgt:

```
$Using:<VariableName>
```

Im folgenden Beispiel `$ps` wird die Variable in der lokalen Sitzung erstellt, aber in der Sitzung verwendet, in der der Befehl ausgeführt wird. Der bereichsmodifizierer `Using` identifiziert `$ps` als lokale Variable.

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  Get-WinEvent -LogName $Using:ps
}
```

Der bereichsmodifizierer `Using` kann in einer **PSSession** verwendet werden.

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $Using:ps}
```

Ein Variablen Verweis, z `$using:var` . b., wird auf den Wert der Variablen `$var` aus dem Kontext des Aufrufers erweitert. Sie erhalten keinen Zugriff auf das Variablen Objekt des Aufrufers.
Der `Using` bereichsmodifizierer kann nicht verwendet werden, um eine lokale Variable innerhalb der **PSSession** zu ändern. Der folgende Code kann beispielsweise nicht verwendet werden:

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {$Using:ps = 'Cannot assign new value'}
```

Weitere Informationen zu `Using` finden Sie unter [about_Scopes](./about_Scopes.md)

### <a name="using-splatting"></a>Verwenden von Verteilung

PowerShell-Verteilung übergibt eine Auflistung von Parameternamen und-Werten an einen Befehl. Weitere Informationen finden Sie unter [about_Splatting](about_Splatting.md).

In diesem Beispiel ist die Verteilung-Variable `$Splat` eine Hash Tabelle, die auf dem lokalen Computer eingerichtet ist. Der stellt `Invoke-Command` eine Verbindung mit einer Remote Computersitzung her. Der **ScriptBlock** verwendet den `Using` bereichsmodifizierer mit dem at- `@` Symbol (), um die splatted-Variable darzustellen.

```powershell
$Splat = @{ Name = "Win*"; Include = "WinRM" }
Invoke-Command -Session $s -ScriptBlock { Get-Service @Using:Splat }
```

### <a name="other-situations-where-the-using-scope-modifier-is-needed"></a>Andere Situationen, in denen der Bereichs Modifizierer "using" benötigt wird

Für Skripts oder Befehle, die außerhalb der Sitzung ausgeführt werden, müssen Sie den bereichsmodifizierer `Using` zum Einbetten von Variablen Werten aus dem aufrufenden Sitzungs Bereich benötigen, damit der Sitzungscode darauf zugreifen kann. Der bereichsmodifizierer `Using` wird in den folgenden Kontexten unterstützt:

- Remote ausgeführte Befehle, gestartet mit mit `Invoke-Command` den Parametern **Computername** , **Hostname** , **SshConnection** oder **Session** (Remote Sitzung)
- Hintergrund Aufträge, gestartet mit `Start-Job` (Out-of-Process-Sitzung)
- Thread Aufträge, die über `Start-ThreadJob` (separate Thread Sitzung) gestartet wurden

Abhängig vom Kontext sind eingebettete Variablen Werte entweder unabhängige Kopien der Daten im Gültigkeitsbereich des Aufrufers oder Verweise darauf. In Remote-und Out-of-Process-Sitzungen sind Sie immer unabhängige Kopien. In Thread Sitzungen werden Sie als Verweis übermittelt.

## <a name="serialization-of-variable-values"></a>Serialisierung von Variablen Werten

Remote ausgeführte Befehle und Hintergrund Aufträge werden außerhalb des Prozesses ausgeführt.
Out-of-Process-Sitzungen verwenden die XML-basierte Serialisierung und Deserialisierung, um die Werte der Variablen über die Prozess Grenzen hinweg verfügbar zu machen. Der Serialisierungsprozess konvertiert Objekte in ein **psobject** -Objekt, das die ursprünglichen Objekteigenschaften, aber nicht die zugehörigen Methoden enthält.

Bei einer begrenzten Menge von Typen werden Objekte von der Deserialisierung zurück auf den ursprünglichen Typ zurückgesetzt. Das rehydrierte Objekt ist eine Kopie der ursprünglichen Objektinstanz.
Es verfügt über die Typeigenschaften und-Methoden. Bei einfachen Typen, wie z. b **. System. Version** , ist die Kopie exakt. Bei komplexen Typen ist die Kopie nicht perfekt. Beispielsweise enthalten die von einem Zertifikat bereit erten Zertifikat Objekte nicht den privaten Schlüssel.

Instanzen aller anderen Typen sind **psobject** -Instanzen. Die **pstypames** -Eigenschaft enthält den ursprünglichen Typnamen, dem die **Deserialisierung** vorangestellt ist, z **. b.Deserialized.System. Data. datdatababel**

## <a name="using-local-variables-with-argumentlist-parameter"></a>Verwenden von lokalen Variablen mit Argument **List** -Parametern

Sie können lokale Variablen in einem Remote Befehl verwenden, indem Sie Parameter für den Remote Befehl definieren und den Argument **List** -Parameter des `Invoke-Command` Cmdlets verwenden, um die lokale Variable als Parameterwert anzugeben.

- Verwenden Sie das- `param` Schlüsselwort, um Parameter für den Remote Befehl zu definieren. Die Parameternamen sind Platzhalter, die nicht mit dem Namen der lokalen Variablen abgeglichen werden müssen.

- Verwenden Sie die Parameter, die vom- `param` Schlüsselwort im-Befehl definiert werden.

- Verwenden Sie den Argument **List** -Parameter des `Invoke-Command` Cmdlets, um die lokale Variable als Parameterwert anzugeben.

Die folgenden Befehle definieren z `$ps` . b. die Variable in der lokalen Sitzung und verwenden Sie dann in einem Remote Befehl. Der Befehl verwendet `$log` als Parameternamen und die lokale Variable, `$ps` , als Wert.

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  param($log)
  Get-WinEvent -LogName $log
} -ArgumentList $ps
```

## <a name="see-also"></a>Weitere Informationen:

[about_PSSessions](about_PSSessions.md)

[about_Remote](about_Remote.md)

[about_Scopes](about_Scopes.md)

[about_Splatting](about_Splatting.md)

[about_Variables](about_Variables.md)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Start-ThreadJob](xref:ThreadJob.Start-ThreadJob)
