---
ms.date: 09/13/2016
ms.topic: reference
title: Allgemeine Parameternamen
description: Allgemeine Parameternamen
ms.openlocfilehash: 506aab290abdb97a6e26c340ac4bd0051244f54b
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98860878"
---
# <a name="common-parameter-names"></a>Allgemeine Parameternamen

Die in diesem Thema beschriebenen Parameter werden als **Allgemeine Parameter** bezeichnet. Sie werden Cmdlets von der Windows PowerShell-Runtime hinzugefügt und können nicht vom Cmdlet deklariert werden.

> [!NOTE]
> Diese Parameter werden auch den Anbieter-Cmdlets und Funktionen hinzugefügt, die mit dem-Attribut ergänzt werden `CmdletBinding` .

## <a name="general-common-parameters"></a>Allgemeine allgemeine Parameter

Die folgenden Parameter werden allen Cmdlets hinzugefügt und können jederzeit aufgerufen werden, wenn das Cmdlet ausgeführt wird.
Diese Parameter werden von der [System. Management. Automation. Internal. CommonParameters](/dotnet/api/System.Management.Automation.Internal.CommonParameters) -Klasse definiert.

### <a name="confirm-alias-cf"></a>Bestätigen (alias: CF)

Datentyp: Switchparameter

Dieser Parameter gibt an, ob das Cmdlet eine Eingabeaufforderung anzeigt, in der gefragt wird, ob der Benutzer sicher ist, dass er fortgesetzt werden soll.

### <a name="debug-alias-db"></a>Debug (alias: DB)

Datentyp: Switchparameter

Dieser Parameter gibt an, ob Debugmeldungen auf Programmier Ebene, die in der Befehlszeile angezeigt werden können, angezeigt werden. Diese Nachrichten sind zur Problembehandlung bei der Ausführung des Cmdlets gedacht und werden durch Aufrufe der [System. Management. Automation. Cmdlet. Write Team Debug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) -Methode generiert. Debugmeldungen müssen nicht lokalisiert werden.

### <a name="erroraction-alias-ea"></a>ErrorAction (alias: EA)

Datentyp: Enumeration

Dieser Parameter gibt an, welche Aktion durchgeführt werden soll, wenn ein Fehler auftritt. Die möglichen Werte für diesen Parameter werden von der [System. Management. Automation. Action Preference](/dotnet/api/System.Management.Automation.ActionPreference) -Enumeration definiert.

### <a name="errorvariable-alias-ev"></a>ErrorVariable (alias: EV)

Datentyp: Zeichenfolge

Dieser Parameter gibt die Variable an, in der Objekte beim Auftreten eines Fehlers platziert werden sollen. Um an diese Variable anzufügen, verwenden Sie +_varname_ , anstatt die Variable zu löschen und festzulegen.

### <a name="outbuffer-alias-ob"></a>OutBuffer (alias: ob)

Datentyp: Int32

Dieser Parameter definiert die Anzahl der Objekte, die im Ausgabepuffer gespeichert werden sollen, bevor Objekte über die Pipeline übergeben werden. Standardmäßig werden Objekte direkt an die Pipeline übermittelt.

### <a name="outvariable-alias-ov"></a>OutVariable (alias: OV)

Datentyp: Zeichenfolge

Dieser Parameter gibt die Variable an, in der alle vom Cmdlet generierten Ausgabe Objekte platziert werden sollen.
Um an diese Variable anzufügen, verwenden Sie +_varname_ , anstatt die Variable zu löschen und festzulegen.

### <a name="pipelinevariable-alias-pv"></a>Pipelinevariable (alias: PV)

Datentyp: Zeichenfolge

Dieser Parameter speichert den Wert des aktuellen Pipeline Elements als Variable für jeden benannten Befehl, während er durch die Pipeline fließt.

## <a name="verbose-alias-vb"></a>Ausführlich (alias: VB)

Datentyp: Switchparameter

Dieser Parameter gibt an, ob das Cmdlet erklärende Meldungen schreibt, die in der Befehlszeile angezeigt werden können. Diese Nachrichten sind zum Bereitstellen zusätzlicher Hilfe für den Benutzer gedacht und werden durch Aufrufe der [System. Management. Automation. Cmdlet. Write-Verbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) -Methode generiert.

### <a name="warningaction-alias-wa"></a>WarningAction (alias: WA)

Datentyp: Enumeration

Dieser Parameter gibt an, welche Aktion durchgeführt werden soll, wenn das Cmdlet eine Warnmeldung schreibt. Die möglichen Werte für diesen Parameter werden von der [System. Management. Automation. Action Preference](/dotnet/api/System.Management.Automation.ActionPreference) -Enumeration definiert.

### <a name="warningvariable-alias-wv"></a>WarningVariable (alias: WV)

Datentyp: Zeichenfolge

Dieser Parameter gibt die Variable an, in der Warnmeldungen gespeichert werden können. Um an diese Variable anzufügen, verwenden Sie +_varname_ , anstatt die Variable zu löschen und festzulegen.

## <a name="risk-mitigation-parameters"></a>Risk-Mitigation Parameter

Die folgenden Parameter werden den Cmdlets hinzugefügt, die eine Bestätigung anfordern, bevor Sie Ihre Aktion ausführen. Weitere Informationen zu Bestätigungs Anforderungen finden Sie unter [Anfordern einer Bestätigung](./requesting-confirmation-from-cmdlets.md).
Diese Parameter werden von der [System. Management. Automation. Internal. schuldprocessparameters](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters) -Klasse definiert.

### <a name="whatif-alias-wi"></a>WhatIf (alias: Wi)

Datentyp: Switchparameter

Dieser Parameter gibt an, ob das Cmdlet eine Meldung schreibt, in der die Auswirkungen der Ausführung des Cmdlets beschrieben werden, ohne tatsächlich eine Aktion auszuführen.

## <a name="transaction-parameters"></a>Transaktions Parameter

Der folgende Parameter wird Cmdlets hinzugefügt, die Transaktionen unterstützen. Diese Parameter werden von der [System. Management. Automation. Internal. transaktionparameters](/dotnet/api/System.Management.Automation.Internal.TransactionParameters) -Klasse definiert. Die Transaktionsunterstützung wurde in PowerShell 3,0 eingeführt und in PowerShell 6,0 nicht mehr unterstützt.

### <a name="usetransaction-alias-usetx"></a>UseTransaction (alias: usetx)

Datentyp: Switchparameter

Dieser Parameter gibt an, ob das Cmdlet die aktuelle Transaktion verwendet, um die Aktion auszuführen.

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. Internal. CommonParameters](/dotnet/api/System.Management.Automation.Internal.CommonParameters)

[System. Management. Automation. Internal. schuldprocessparameters](/dotnet/api/System.Management.Automation.Internal.ShouldProcessParameters)

[System. Management. Automation. Internal. transaktionparameters](/dotnet/api/System.Management.Automation.Internal.TransactionParameters)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
