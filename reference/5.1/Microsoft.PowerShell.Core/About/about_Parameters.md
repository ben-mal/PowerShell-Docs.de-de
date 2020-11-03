---
description: Beschreibt das Arbeiten mit Befehlsparametern in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 02/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters
ms.openlocfilehash: 7cc5c071116df8d3326a4ea13802227d350bfac3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223380"
---
# <a name="about-parameters"></a>Informationen zu Parametern

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt das Arbeiten mit Befehlsparametern in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

Die meisten PowerShell-Befehle, z. b. Cmdlets, Funktionen und Skripts, basieren auf Parametern, damit Benutzeroptionen auswählen oder Eingaben bereitstellen können. Die Parameter folgen dem Befehlsnamen und weisen die folgende Form auf:

```
-<parameter_name> <parameter_value>
-<parameter_name>:<parameter_value>
```

Dem Namen des Parameters wird ein Bindestrich (-) vorangestellt, der PowerShell signalisiert, dass das Wort nach dem Bindestrich ein Parameter Name ist. Der Parameter Name und der Wert können durch ein Leerzeichen oder einen Doppelpunkt getrennt werden. Einige Parameter erfordern keinen Parameterwert oder akzeptieren ihn nicht. Für andere Parameter ist ein Wert erforderlich, aber der Parameter Name ist im Befehl nicht erforderlich.

Der Parametertyp und die Anforderungen für diese Parameter variieren. Um Informationen zu den Parametern eines Befehls zu finden, verwenden Sie das- `Get-Help` Cmdlet. Wenn Sie z. b. Informationen zu den Parametern des `Get-ChildItem` Cmdlets suchen möchten, geben Sie Folgendes ein:

```powershell
Get-Help Get-ChildItem
```

Wenn Sie Informationen zu den Parametern eines Skripts suchen möchten, verwenden Sie den vollständigen Pfad zur Skriptdatei. Beispiel:

```powershell
Get-Help $home\Documents\Scripts\Get-Function.ps1
```

`Get-Help`Mit dem-Cmdlet werden verschiedene Details zum Befehl zurückgegeben, einschließlich einer Beschreibung, der Befehlssyntax, Informationen zu den Parametern und Beispielen, die zeigen, wie die Parameter in einem Befehl verwendet werden.

Sie können auch den Parameter Parameter des `Get-Help` Cmdlets verwenden, um Informationen zu einem bestimmten Parameter zu suchen. Oder Sie können den **Parameter** Parameter mit dem Platzhalter Zeichen ( `*` ) verwenden, um Informationen zu allen Parametern des Befehls zu suchen. Beispielsweise werden mit dem folgenden Befehl Informationen zu allen Parametern des `Get-Member` Cmdlets abgerufen:

```powershell
Get-Help Get-Member -Parameter *
```

### <a name="default-parameter-values"></a>Standardwerte für Parameter

Optionale Parameter verfügen über einen Standardwert. Dies ist der Wert, der verwendet wird, oder angenommen, wenn der-Parameter nicht im Befehl angegeben wird.

Der Standardwert des **Computername** -Parameters von vielen Cmdlets ist beispielsweise der Name des lokalen Computers. Daher wird der Name des lokalen Computers im Befehl verwendet, es sei denn, der **Computername** -Parameter ist angegeben.

Die Standardparameter Werte finden Sie im Hilfethema für das Cmdlet. Die Beschreibung des Parameters sollte den Standardwert enthalten.

Sie können auch einen benutzerdefinierten Standardwert für jeden Parameter eines Cmdlets oder einer erweiterten Funktion festlegen. Weitere Informationen zum Festlegen von benutzerdefinierten Standardwerten finden Sie unter [about_Parameters_Default_Values](about_Parameters_Default_Values.md).

### <a name="parameter-attribute-table"></a>Parameter Attribut Tabelle

Wenn Sie den **Full** -, **Parameter** -oder **Online-** Parameter des `Get-Help` Cmdlets verwenden, wird `Get-Help` eine Parameter Attribut Tabelle mit detaillierten Informationen zum Parameter angezeigt.

Diese Informationen umfassen die Details, die Sie kennen müssen, um den-Parameter zu verwenden.
Das Hilfethema für das `Get-ChildItem` Cmdlet enthält z. b. die folgenden Details zum Pfad Parameter:

```
-path <string[]>
    Specifies a path of one or more locations. Wildcard characters are
    permitted. The default location is the current directory (.).

Required?                    false
Position?                    0
Default value                Current directory
Accept pipeline input?       true (ByValue, ByPropertyName)
Accept wildcard characters?  true
```

Zu den Parameterinformationen gehören die Parameter Syntax, eine Beschreibung des Parameters und die Parameter Attribute. In den folgenden Abschnitten werden die Parameter Attribute beschrieben.

#### <a name="parameter-required"></a>Parameter erforderlich

Diese Einstellung gibt an, ob der Parameter obligatorisch ist, d. h. ob alle Befehle, die dieses Cmdlet verwenden, diesen Parameter enthalten müssen. Wenn der Wert **true** lautet und der-Parameter im Befehl fehlt, werden Sie von PowerShell aufgefordert, einen Wert für den-Parameter einzugeben.

#### <a name="parameter-position"></a>Parameter Position

Wenn die `Position` Einstellung auf eine positive ganze Zahl festgelegt ist, ist der Parameter Name nicht erforderlich. Dieser Parametertyp wird als Positions Parameter bezeichnet, und die Zahl gibt die Position an, an der der Parameter in Relation zu anderen Positions Parametern angezeigt werden muss. Ein benannter Parameter kann an einer beliebigen Position nach dem Namen des Cmdlets aufgelistet werden. Wenn Sie den Parameternamen für einen positionellen Parameter einschließen, kann der Parameter an einer beliebigen Position nach dem Cmdlet-Namen aufgelistet werden.

Das `Get-ChildItem` Cmdlet hat z. b. Pfad-und Ausschluss Parameter. Die `Position` Einstellung für **path** ist **0** , was bedeutet, dass es sich um einen Positions Parameter handelt. Die `Position` Einstellung für **Exclude** hat den **Namen**.

Dies bedeutet, dass für **path** nicht der Parameter Name erforderlich ist, aber der Parameterwert muss der erste oder einzige unbenannte Parameterwert im Befehl sein.
Da der Exclude-Parameter jedoch ein benannter Parameter ist, können Sie ihn an einer beliebigen Position im Befehl platzieren.

Aufgrund der `Position` Einstellungen für diese beiden Parameter können Sie einen der folgenden Befehle verwenden:

```powershell
Get-ChildItem -Path c:\techdocs -Exclude *.ppt
Get-ChildItem c:\techdocs -Exclude *.ppt
Get-ChildItem -Exclude *.ppt -Path c:\techdocs
Get-ChildItem -Exclude *.ppt c:\techdocs
```

Wenn Sie einen anderen Positions Parameter einschließen möchten, ohne den Parameternamen einzuschließen, muss dieser Parameter in der von der-Einstellung angegebenen Reihenfolge platziert werden `Position` .

#### <a name="parameter-type"></a>Parametertyp

Diese Einstellung gibt den Microsoft .net Frameworktyp des Parameter Werts an. Wenn der Typ z. b. **Int32** ist, muss der Parameterwert eine ganze Zahl sein. Wenn der Typ "String" ist, muss der Parameterwert eine Zeichenfolge sein. Wenn die Zeichenfolge Leerzeichen enthält, muss der Wert in Anführungszeichen eingeschlossen werden, oder dem Escapezeichen muss das Escapezeichen (') vorangestellt werden.

#### <a name="default-value"></a>Standardwert

Diese Einstellung gibt den Wert an, den der Parameter annimmt, wenn kein anderer Wert angegeben wird. Beispielsweise ist der Standardwert des path-Parameters oft das aktuelle Verzeichnis. Erforderliche Parameter haben niemals einen Standardwert.
Bei vielen optionalen Parametern gibt es keinen Standardwert, da der-Parameter keine Auswirkung hat, wenn er nicht verwendet wird.

#### <a name="accepts-multiple-values"></a>Akzeptiert mehrere Werte

Diese Einstellung gibt an, ob ein Parameter mehrere Parameterwerte akzeptiert.
Wenn ein Parameter mehrere Werte akzeptiert, können Sie eine durch Trennzeichen getrennte Liste als Wert des Parameters im Befehl eingeben oder eine durch Trennzeichen getrennte Liste (ein Array) in einer Variablen speichern und die Variable dann als Parameterwert angeben.

Der Service Name-Parameter des `Get-Service` Cmdlets nimmt z. b. mehrere Werte an. Die folgenden Befehle sind beide gültig:

```powershell
Get-Service -servicename winrm, netlogon
```

```powershell
$s = "winrm", "netlogon"
Get-Service -servicename $s
```

#### <a name="accepts-pipeline-input"></a>Akzeptiert Pipeline Eingaben

Diese Einstellung gibt an, ob Sie den Pipeline Operator ( `|` ) verwenden können, um einen Wert an den Parameter zu senden.

```
Value                    Description
-----                    -----------
False                    Indicates that you cannot pipe a value to the
                         parameter.

True (by Value)          Indicates that you can pipe any value to the
                         parameter, just so the value has the .NET
                         Framework type specified for the parameter or the
                         value can be converted to the specified .NET
                         Framework type.
```

Wenn ein Parameter "true (nach Wert)" ist, versucht PowerShell, alle weitergeleiteten Werte mit diesem Parameter zu verknüpfen, bevor versucht wird, den Befehl mit anderen Methoden zu interpretieren.

```
True (by Property Name)  Indicates that you can pipe a value to the
                         parameter, but the .NET Framework type of the
                         parameter must include a property with the same
                         name as the parameter.
```

Beispielsweise können Sie einen Wert nur an einen **Name** -Parameter übergeben, wenn der Wert eine Eigenschaft namens **Name** aufweist.

> [!NOTE]
> Ein typisierter Parameter, der Pipeline Eingaben ( `by Value` ) oder () akzeptiert, `by PropertyName` ermöglicht die Verwendung von **verzögerten Bindungs** Skript Blöcken für den Parameter.
>
> Der **Verzögerungs Bindungs** Skriptblock wird automatisch während der **ParameterBinding** ausgeführt. Das Ergebnis wird an den-Parameter gebunden. Die verzögerte Bindung funktioniert **nicht** für Parameter `ScriptBlock` , die als Typ oder definiert `System.Object` sind, und der Skriptblock wird durchlaufen, **ohne** aufgerufen zu werden.
>
> Informationen zu **verzögerten Bindungs** Skript Blöcken finden Sie hier [about_Script_Blocks. MD](about_Script_Blocks.md)

#### <a name="accepts-wildcard-characters"></a>Akzeptiert Platzhalter Zeichen

Diese Einstellung gibt an, ob der Wert des Parameters Platzhalter Zeichen enthalten kann, sodass der Parameterwert mit mehr als einem vorhandenen Element im Zielcontainer abgeglichen werden kann.

#### <a name="common-parameters"></a>Allgemeine Parameter

Allgemeine Parameter sind Parameter, die Sie mit jedem Cmdlet verwenden können. Weitere Informationen zu allgemeinen Parametern finden Sie unter [about_CommonParameters](about_CommonParameters.md).

## <a name="see-also"></a>Weitere Informationen:

[about_Command_syntax](about_Command_syntax.md)

[about_Comment_Based_Help](about_Comment_Based_Help.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Parameters_Default_Values](about_Parameters_Default_Values.md)

[about_Pipelines](about_Pipelines.md)

[about_Wildcards](about_Wildcards.md)
