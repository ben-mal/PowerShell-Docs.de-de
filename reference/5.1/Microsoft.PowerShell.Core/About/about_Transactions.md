---
description: Hier wird beschrieben, wie transaktive Vorgänge in PowerShell verwaltet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_transactions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Transactions
ms.openlocfilehash: 522e0f727754b0b0153571039f3bf3966d0abf20
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222479"
---
# <a name="about-transactions"></a>Informationen zu Transaktionen

## <a name="short-description"></a>KURZE BESCHREIBUNG

Hier wird beschrieben, wie transaktive Vorgänge in PowerShell verwaltet werden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Transaktionen werden in PowerShell ab PowerShell 2,0 unterstützt. Diese Funktion ermöglicht es Ihnen, eine Transaktion zu starten, anzugeben, welche Befehle Teil der Transaktion sind, und einen Commit oder Rollback für eine Transaktion auszuführen.

## <a name="about-transactions"></a>Informationen zu Transaktionen

In PowerShell besteht eine Transaktion aus einer Reihe von Befehlen, die als logische Einheit verwaltet werden. Eine Transaktion kann abgeschlossen werden ("Commit"), wodurch die von der Transaktion betroffenen Daten geändert werden. Oder eine Transaktion kann vollständig rückgängig gemacht werden ("Rollback"), damit die betroffenen Daten von der Transaktion nicht geändert werden.

Da die Befehle in einer Transaktion als Einheit verwaltet werden, wird entweder für alle Befehle ein Commit ausgeführt, oder für alle Befehle wird ein Rollback ausgeführt.

Transaktionen werden häufig in der Datenverarbeitung verwendet, insbesondere bei Daten Bank Vorgängen und für Finanztransaktionen. Transaktionen werden meistens verwendet, wenn es sich bei dem ungünstigsten Szenario für einen Satz von Befehlen nicht um alle Fehler handelt, aber dass einige Befehle erfolgreich sind, während andere fehlschlagen, sodass das System in einem beschädigten, falschen oder nicht interpretierbaren Zustand ist, der schwer zu reparieren ist.

## <a name="transaction-cmdlets"></a>Transaktions-Cmdlets

PowerShell umfasst mehrere Cmdlets, die für die Verwaltung von Transaktionen konzipiert sind.

- Start-Transaction: startet eine neue Transaktion.
- Use-Transaction: Fügt der Transaktion einen Befehl oder einen Ausdruck hinzu. Für den Befehl müssen Transaktions aktivierte Objekte verwendet werden.
- Rückgängig-Transaktion: führt einen Rollback für die Transaktion aus, sodass keine Daten von der Transaktion geändert werden.
- Complete-Transaction: führt einen Commit für die Transaktion aus. Die Daten, die von der Transaktion betroffen sind, werden geändert.
- Get-Transaction: Ruft Informationen über die aktive Transaktion ab.

Eine Liste der Transaktions-Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:

```powershell
get-command *transaction
```

Ausführliche Informationen zu den-Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:

```powershell
get-help use-transaction -detailed
```

## <a name="transaction-enabled-elements"></a>transaktionsaktivierte Elemente

Um an einer Transaktion teilnehmen zu können, müssen sowohl das Cmdlet als auch der Anbieter Transaktionen unterstützen. Diese Funktion ist in die Objekte integriert, die von der Transaktion betroffen sind.

Der PowerShell-Registrierungs Anbieter unterstützt Transaktionen in Windows Vista. Das transactedstring-Objekt (Microsoft. PowerShell. Commands. Management. transactedstring) funktioniert mit jedem Betriebssystem, auf dem PowerShell ausgeführt wird.

Andere PowerShell-Anbieter können Transaktionen unterstützen. Um die PowerShell-Anbieter in Ihrer Sitzung zu finden, die Transaktionen unterstützen, verwenden Sie den folgenden Befehl, um den Wert "Transactions" in der Eigenschaft "Funktionen" der Anbieter zu finden:

```powershell
get-psprovider | where {$_.Capabilities -like "*transactions*"}
```

Weitere Informationen zu einem Anbieter finden Sie in der Hilfe für den Anbieter. Um die Anbieter Hilfe zu erhalten, geben Sie Folgendes ein:

```
get-help <provider-name>
```

Wenn Sie z. B. Hilfe zum Registrierungsanbieter abrufen möchten, geben Sie Folgendes ein:

```powershell
get-help registry
```

## <a name="the-usetransaction-parameter"></a>der UseTransaction-Parameter.

Cmdlets, die Transaktionen unterstützen können, verfügen über einen UseTransaction-Parameter. Dieser Parameter schließt den Befehl in die aktive Transaktion ein. Sie können den vollständigen Parameternamen oder seinen Alias, "usetx", verwenden.

Der-Parameter kann nur verwendet werden, wenn die Sitzung eine aktive Transaktion enthält. Wenn Sie einen Befehl mit dem UseTransaction-Parameter eingeben, wenn keine aktive Transaktion vorhanden ist, schlägt der Befehl fehl.

Um Cmdlets mit dem UseTransaction-Parameter zu suchen, geben Sie Folgendes ein:

```powershell
get-help * -parameter UseTransaction
```

In PowerShell Core unterstützen alle Cmdlets, die für die Arbeit mit PowerShell-Anbietern entwickelt wurden, Transaktionen. Daher können Sie die Anbieter-Cmdlets zum Verwalten von Transaktionen verwenden.

Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](about_Providers.md).

## <a name="the-transaction-object"></a>das Transaktions Objekt.

Transaktionen werden in PowerShell durch ein Transaktions Objekt (System. Management. Automation. Transaction) dargestellt.

Das Objekt hat die folgenden Eigenschaften:

- Rollbackpreference: enthält die Roll Back Einstellung, die für die aktuelle Transaktion festgelegt wurde. Sie können die Roll Back Einstellung festlegen, wenn Sie Start-Transaction verwenden, um die Transaktion zu starten.

  Die Rollback-Einstellung bestimmt die Bedingungen, unter denen automatisch ein Rollback für die Transaktion ausgeführt wird. Gültige Werte sind Error, terminatingerror und Never. Der Standardwert ist "Error".

- Status: enthält den aktuellen Status der Transaktion. Gültige Werte sind "aktiv", "Commit" und "rolledback".

- Abonnement Anzahl: enthält die Anzahl der Abonnenten der Transaktion. Ein Abonnent wird einer Transaktion hinzugefügt, wenn Sie eine Transaktion starten, während eine andere Transaktion ausgeführt wird. Die Abonnenten Anzahl wird dekrementiert, wenn ein Abonnent einen Commit für die Transaktion ausführt.

## <a name="active-transactions"></a>aktive Transaktionen

In PowerShell ist jeweils nur eine Transaktion aktiv, und Sie können nur die aktive Transaktion verwalten. Mehrere Transaktionen können gleichzeitig in derselben Sitzung ausgeführt werden, aber nur die zuletzt gestartete Transaktion ist aktiv.

Daher können Sie keine bestimmte Transaktion angeben, wenn Sie die Cmdlets für die Transaktion verwenden. Befehle gelten immer für die aktive Transaktion.

Dies ist am deutlichsten im Verhalten des Get-Transaction Cmdlets ersichtlich. Wenn Sie einen Get-Transaction Befehl eingeben, erhält Get-Transaction immer nur ein Transaktions Objekt. Dieses Objekt ist das Objekt, das die aktive Transaktion darstellt.

Zum Verwalten einer anderen Transaktion müssen Sie zuerst die aktive Transaktion beenden, indem Sie entweder einen Commit durchführen oder einen Rollback ausführen. Wenn Sie dies tun, wird die vorherige Transaktion automatisch aktiv. Transaktionen werden in umgekehrter Reihenfolge aktiv, in der Sie gestartet werden, sodass die zuletzt gestartete Transaktion immer aktiv ist.

## <a name="subscribers-and-independent-transactions"></a>Abonnenten und unabhängige Transaktionen

Wenn Sie eine Transaktion starten, während eine andere Transaktion ausgeführt wird, wird von PowerShell standardmäßig keine neue Transaktion gestartet. Stattdessen wird der aktuellen Transaktion ein "Abonnent" hinzugefügt.

Wenn eine Transaktion über mehrere Abonnenten verfügt, führt ein einzelner Undo-Transaction Befehl zu einem beliebigen Zeitpunkt ein Rollback für die gesamte Transaktion für alle Abonnenten aus. Um einen Commit für die Transaktion durchführen zu können, müssen Sie jedoch einen Complete-Transaction Befehl für jeden Abonnenten eingeben.

Um die Anzahl der Abonnenten einer Transaktion zu ermitteln, überprüfen Sie die Eigenschaft "abonniert" des Transaktions Objekts. Der folgende Befehl verwendet z. b. das Get-Transaction-Cmdlet, um den Wert der Eigenschaft "abonniert" der aktiven Transaktion zu erhalten:

```powershell
(Get-Transaction).SubscriberCount
```

Das Hinzufügen eines Abonnenten ist das Standardverhalten, da die meisten Transaktionen, die gestartet werden, während eine andere Transaktion ausgeführt wird, mit der ursprünglichen Transaktion verknüpft sind. Im typischen Modell wird ein Skript, das eine Transaktion enthält, ein Hilfsskript aufrufen, das seine eigene Transaktion enthält. Da die Transaktionen verknüpft sind, sollten Sie als Einheit zurückgesetzt oder als Commit ausgeführt werden.

Sie können jedoch eine Transaktion starten, die unabhängig von der aktuellen Transaktion ist, indem Sie den unabhängigen Parameter des Start-Transaction Cmdlets verwenden.

Wenn Sie eine unabhängige Transaktion starten, erstellt Start-Transaction ein neues Transaktions Objekt, und die neue Transaktion wird zur aktiven Transaktion.
Für die unabhängige Transaktion kann ein Commit oder ein Rollback ausgeführt werden, ohne dass die ursprüngliche Transaktion beeinträchtigt wird.

Wenn die unabhängige Transaktion abgeschlossen ist (Commit oder Rollback), wird die ursprüngliche Transaktion wieder zur aktiven Transaktion.

## <a name="changing-data"></a>Ändern von Daten

Wenn Sie Transaktionen zum Ändern von Daten verwenden, werden die Daten, die von der Transaktion betroffen sind, erst geändert, wenn Sie einen Commit für die Transaktion durchführen. Die gleichen Daten können jedoch durch Befehle geändert werden, die nicht Teil der Transaktion sind.

Beachten Sie dies, wenn Sie Transaktionen verwenden, um freigegebene Daten zu verwalten.
Datenbanken verfügen in der Regel über Mechanismen, die die Daten Sperren, während Sie daran arbeiten, sodass andere Benutzer und andere Befehle, Skripts und Funktionen nicht geändert werden können.

Die Sperre ist jedoch eine Funktion der-Datenbank. Sie steht nicht im Zusammenhang mit Transaktionen. Wenn Sie in einem Transaktions fähigen Dateisystem oder einem anderen Datenspeicher arbeiten, können die Daten geändert werden, während die Transaktion ausgeführt wird.

## <a name="examples"></a>BEISPIELE

In den Beispielen in diesem Abschnitt wird der PowerShell-Registrierungs Anbieter verwendet, und es wird davon ausgegangen, dass Sie damit vertraut sind. Weitere Informationen zum Registrierungs Anbieter erhalten Sie, wenn Sie "Get-Help Registry" eingeben.

### <a name="example-1-committing-a-transaction"></a>Beispiel 1: Commit für eine Transaktion

Verwenden Sie zum Erstellen einer Transaktion das Start-Transaction-Cmdlet. Der folgende Befehl startet eine Transaktion mit den Standardeinstellungen.

```powershell
start-transaction
```

Wenn Sie Befehle in die Transaktion einschließen möchten, verwenden Sie den UseTransaction-Parameter des Cmdlets. Standardmäßig sind Befehle nicht in der Transaktion enthalten,

Beispielsweise ist der folgende Befehl, der den aktuellen Speicherort im Software Schlüssel des HKCU:-Laufwerks festlegt, nicht in der Transaktion enthalten.

```powershell
cd hkcu:\Software
```

Der folgende Befehl, der den Schlüssel MyCompany erstellt, verwendet den UseTransaction-Parameter des New-Item Cmdlets, um den Befehl in die aktive Transaktion einzubeziehen.

```powershell
new-item MyCompany -UseTransaction
```

Der Befehl gibt ein Objekt zurück, das den neuen Schlüssel darstellt, aber da der Befehl Teil der Transaktion ist, wird die Registrierung noch nicht geändert.

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyCompany                      {}
```

Verwenden Sie das Cmdlet Complete-Transaction, um ein Commit für die Transaktion durchführen. Da Sie sich immer auf die aktive Transaktion auswirkt, können Sie die Transaktion nicht angeben.

```powershell
complete-transaction
```

Daher wird der Schlüssel "MyCompany" der Registrierung hinzugefügt.

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-2-rolling-back-a-transaction"></a>Beispiel 2: Rollback einer Transaktion

Verwenden Sie zum Erstellen einer Transaktion das Start-Transaction-Cmdlet. Der folgende Befehl startet eine Transaktion mit den Standardeinstellungen.

```powershell
start-transaction
```

Der folgende Befehl, der den myothercompany-Schlüssel erstellt, verwendet den UseTransaction-Parameter des New-Item-Cmdlets, um den Befehl in die aktive Transaktion einzubeziehen.

```powershell
new-item MyOtherCompany -UseTransaction
```

Der Befehl gibt ein Objekt zurück, das den neuen Schlüssel darstellt, aber da der Befehl Teil der Transaktion ist, wird die Registrierung noch nicht geändert.

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyOtherCompany                 {}
```

Verwenden Sie das Cmdlet "Undo-Transaction", um ein Rollback für die Transaktion auszuführen. Da Sie sich immer auf die aktive Transaktion auswirkt, wird die Transaktion nicht angegeben.

```powershell
Undo-transaction
```

Das Ergebnis ist, dass der Schlüssel "myothercompany" nicht zur Registrierung hinzugefügt wird.

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-3-previewing-a-transaction"></a>Beispiel 3: Anzeigen einer Vorschau einer Transaktion

In der Regel werden die in einer Transaktion verwendeten Befehle geändert. Die Befehle, die Daten erhalten, sind aber auch in einer Transaktion nützlich, da Sie Daten innerhalb der Transaktion erhalten. Dadurch wird eine Vorschau der Änderungen bereitstellt, die durch das committen der Transaktion verursacht werden.

Im folgenden Beispiel wird gezeigt, wie der Get-ChildItem-Befehl (der Alias ist "dir") verwendet wird, um eine Vorschau der Änderungen in einer Transaktion anzuzeigen.

Der folgende Befehl startet eine Transaktion.

```powershell
start-transaction
```

Der folgende Befehl verwendet das Cmdlet "New-ItemProperty", um den Registrierungs Eintrag "MyKey" dem Schlüssel "MyCompany" hinzuzufügen. Der Befehl verwendet den UseTransaction-Parameter, um den Befehl in die Transaktion einzubeziehen.

```powershell
new-itemproperty -path MyCompany -Name MyKey -value 123 -UseTransaction
```

Der Befehl gibt ein Objekt zurück, das den neuen Registrierungs Eintrag darstellt, der Registrierungs Eintrag wird jedoch nicht geändert.

```
MyKey
-----
123
```

Um die Elemente zu erhalten, die sich derzeit in der Registrierung befinden, verwenden Sie einen Get-ChildItem Befehl ("dir") ohne den UseTransaction-Parameter. Mit dem folgenden Befehl werden Elemente abgerufen, die mit "M" beginnen.

```powershell
dir m*
```

Das Ergebnis zeigt, dass dem Schlüssel MyCompany noch keine Einträge hinzugefügt wurden.

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

Geben Sie einen Get-ChildItem ("dir")-Befehl mit dem UseTransaction-Parameter ein, um eine Vorschau der Auswirkungen des Commit der Transaktion anzuzeigen. Dieser Befehl verfügt über eine Ansicht der Daten aus der Transaktion.

```powershell
dir m* -useTransaction
```

Das Ergebnis zeigt, dass, wenn für die Transaktion ein Commit ausgeführt wird, der MyKey-Eintrag dem Schlüssel MyCompany hinzugefügt wird.

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   1 MyCompany                      {MyKey}
```

### <a name="example-4-combining-transacted-and-non-transacted-commands"></a>Beispiel 4: Kombinieren von transaktiven und nicht transaktionalen Befehlen

Während einer Transaktion können nicht transaktive Befehle eingegeben werden. Die nicht transaktiven Befehle wirken sich sofort auf die Daten aus, Sie wirken sich jedoch nicht auf die Transaktion aus.
Der folgende Befehl startet eine Transaktion im Registrierungsschlüssel "HKCU: \ Software".

```powershell
start-transaction
```

Die nächsten drei Befehle verwenden das Cmdlet "New-Item", um der Registrierung Schlüssel hinzuzufügen.
Der erste und der dritte Befehl verwenden den UseTransaction-Parameter, um die Befehle in die Transaktion einzubeziehen. Mit dem zweiten Befehl wird der-Parameter ausgelassen. Da der zweite Befehl nicht in der Transaktion enthalten ist, wird er sofort wirksam.

```powershell
new-item MyCompany1 -UseTransaction
new-item MyCompany2
new-item MyCompany3 -UseTransaction
```

Um den aktuellen Status der Registrierung anzuzeigen, verwenden Sie einen Get-ChildItem ("dir")-Befehl ohne den UseTransaction-Parameter. Mit diesem Befehl werden Elemente abgerufen, die mit "M" beginnen.

```powershell
dir m*
```

Das Ergebnis zeigt, dass die MyCompany2-Taste der Registrierung hinzugefügt wird, die Schlüssel MyCompany1 und MyCompany3, die Teil der Transaktion sind, jedoch nicht hinzugefügt werden.

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0    0 MyCompany2                     {}
```

Der folgende Befehl führt einen Commit für die Transaktion aus.

```powershell
complete-transaction
```

Nun werden die Schlüssel, die als Teil der Transaktion hinzugefügt wurden, in der Registrierung angezeigt.

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
83   1 Microsoft                      {(default)}
0    0 MyCompany1                     {}
0    0 MyCompany2                     {}
0    0 MyCompany3                     {}
```

### <a name="example-5-using-automatic-rollback"></a>Beispiel 5: Verwenden des automatischen Rollbacks

Wenn ein Befehl in einer Transaktion einen Fehler generiert, wird für die Transaktion automatisch ein Rollback ausgeführt.

Dieses Standardverhalten ist für Skripts konzipiert, die Transaktionen ausführen. Skripts werden in der Regel gut getestet und enthalten Fehler Behandlungs Logik, sodass keine Fehler zu erwarten sind und die Transaktion beendet werden sollte.

Der erste Befehl startet eine Transaktion im Registrierungsschlüssel "HKCU: \ Software".

```powershell
start-transaction
```

Der folgende Befehl verwendet das Cmdlet "New-Item", um den Schlüssel "MyCompany" der Registrierung hinzuzufügen. Der Befehl verwendet den UseTransaction-Parameter (der Alias ist "usetx"), um den Befehl in die Transaktion einzubeziehen.

```powershell
New-Item MyCompany -UseTX
```

Da der Schlüssel MyCompany bereits in der Registrierung vorhanden ist, schlägt der Befehl fehl, und für die Transaktion wird ein Rollback ausgeführt.

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

Ein Get-Transaction Befehl bestätigt, dass ein Rollback für die Transaktion ausgeführt wurde und dass der index count den Wert 0 aufweist.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 RolledBack
```

### <a name="example-6-changing-the-rollback-preference"></a>Beispiel 6: Ändern der Roll Back Einstellung

Wenn die Transaktion eher fehlertolerant sein soll, können Sie den Rollback Preference-Parameter von Start-Transaction verwenden, um die Einstellung zu ändern.

Der folgende Befehl startet eine Transaktion mit der Rollback-Einstellung "Never".

```powershell
start-transaction -rollbackpreference Never
```

Wenn in diesem Fall der Befehl fehlschlägt, wird für die Transaktion nicht automatisch ein Rollback ausgeführt.

```powershell
New-Item MyCompany -UseTX
```

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

Da die Transaktion noch aktiv ist, können Sie den Befehl als Teil der Transaktion erneut übermitteln.

```powershell
New-Item MyOtherCompany -UseTX
```

### <a name="example-7-using-the-use-transaction-cmdlet"></a>Beispiel 7: Verwenden des Cmdlets "Use-Transaction"

Mit dem-Cmdlet "Use-Transaction" können Sie direkte Skripts für Transaktions aktivierte Microsoft .NET Framework-Objekte ausführen. Use-Transaction nimmt einen Skriptblock an, der nur Befehle und Ausdrücke enthalten kann, die Transaktions fähige .NET Framework Objekte verwenden, wie z. b. Instanzen der Microsoft. PowerShell. Commands. Management. transactedstring-Klasse.

Der folgende Befehl startet eine Transaktion.

```powershell
start-transaction
```

Mit dem folgenden New-Object Befehl wird eine Instanz der transactedstring-Klasse erstellt und in der $t Variablen gespeichert.

```powershell
$t = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
```

Der folgende Befehl verwendet die Append-Methode des transactedstring-Objekts, um der Zeichenfolge Text hinzuzufügen. Da der Befehl nicht Teil der Transaktion ist, wird die Änderung sofort wirksam.

```powershell
$t.append("Windows")
```

Der folgende Befehl verwendet die gleiche Append-Methode, um Text hinzuzufügen, fügt den Text jedoch als Teil der Transaktion hinzu. Der Befehl ist in geschweifte Klammern eingeschlossen und wird als Wert des ScriptBlock-Parameters von use-Transaction festgelegt. Der UseTransaction-Parameter (usetx) ist erforderlich.

```powershell
use-transaction {$t.append(" PowerShell")} -usetx
```

Um den aktuellen Inhalt der transaktiven Zeichenfolge in $t anzuzeigen, verwenden Sie die Methode "-Methode" des transactedstring-Objekts.

```powershell
$t.tostring()
```

Die Ausgabe zeigt, dass nur die nicht transaktiven Änderungen wirksam sind.

```output
Windows
```

Um den aktuellen Inhalt der transaktiven Zeichenfolge in $t innerhalb der Transaktion anzuzeigen, Betten Sie den Ausdruck in einen Use-Transaction-Befehl ein.

```powershell
use-transaction {$s.tostring()} -usetx
```

Die Ausgabe zeigt die Transaktions Ansicht an.

```output
PowerShell
```

Der folgende Befehl führt einen Commit für die Transaktion aus.

```powershell
complete-transaction
```

So zeigen Sie die endgültige Zeichenfolge an:

```
$t.tostring()
PowerShell
```

### <a name="example-8-managing-multi-subscriber-transactions"></a>Beispiel 8: Verwalten von Transaktionen mit mehreren Abonnenten

Wenn Sie eine Transaktion starten, während eine andere Transaktion ausgeführt wird, erstellt PowerShell standardmäßig keine zweite Transaktion. Stattdessen wird der aktuellen Transaktion ein Abonnent hinzugefügt.

Dieses Beispiel zeigt, wie Sie eine Transaktion mit mehreren Abonnenten anzeigen und verwalten.

Beginnen Sie, indem Sie eine Transaktion im Schlüssel "HKCU: \ Software" starten.

```powershell
start-transaction
```

Der folgende Befehl verwendet den Get-Transaction-Befehl, um die aktive Transaktion zu erhalten.

```powershell
get-transaction
```

Das Ergebnis zeigt das-Objekt, das die aktive Transaktion darstellt.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

Der folgende Befehl fügt der Registrierung den Schlüssel MyCompany hinzu. Der Befehl verwendet den UseTransaction-Parameter, um den Befehl in die Transaktion einzubeziehen.

```powershell
new-item MyCompany -UseTransaction
```

Der folgende Befehl verwendet den Start-Transaction-Befehl, um eine Transaktion zu starten. Obwohl dieser Befehl an der Eingabeaufforderung eingegeben wird, ist dieses Szenario wahrscheinlicher, wenn Sie ein Skript ausführen, das eine Transaktion enthält.

```powershell
start-transaction
```

Mit einem Get-Transaction-Befehl wird angezeigt, dass die Anzahl der Abonnenten für das Transaktions Objekt inkrementiert wird. Der Wert ist jetzt 2.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

Der nächste Befehl verwendet das Cmdlet "New-ItemProperty", um den Registrierungs Eintrag "MyKey" dem Schlüssel "MyCompany" hinzuzufügen. Der Befehl verwendet den UseTransaction-Parameter, um den Befehl in die Transaktion einzubeziehen.

```powershell
new-itemproperty -path MyCompany -name MyKey -UseTransaction
```

Der Schlüssel MyCompany ist nicht in der Registrierung vorhanden, aber dieser Befehl ist erfolgreich, da die beiden Befehle Teil derselben Transaktion sind.

Der folgende Befehl führt einen Commit für die Transaktion aus. Wenn für die Transaktion ein Rollback ausgeführt wird, wird für alle Abonnenten ein Rollback für die Transaktion ausgeführt.

```powershell
complete-transaction
```

Ein Get-Transaction Befehl zeigt, dass die Anzahl der Abonnenten für das Transaktions Objekt 1 beträgt, der Wert des Status jedoch noch aktiv (kein Commit) ist.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

Geben Sie einen zweiten Complete-Transaction-Befehl ein, um den Commit der Transaktion abzuschließen. Um einen Commit für eine Transaktion mit mehreren Abonnenten durchführen zu können, müssen Sie für jeden Start-Transaction Befehl einen Complete-Transaction Befehl eingeben.

```powershell
complete-transaction
```

Ein weiterer Get-Transaction Befehl zeigt, dass für die Transaktion ein Commit ausgeführt wurde.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 Committed
```

### <a name="example-9-managing-independent-transactions"></a>Beispiel 9: Verwalten unabhängiger Transaktionen

Wenn Sie eine Transaktion starten, während eine andere Transaktion ausgeführt wird, können Sie den unabhängigen Parameter von Start-Transaction verwenden, um die neue Transaktion unabhängig von der ursprünglichen Transaktion zu machen.

Wenn Sie dies tun, erstellt Start-Transaction ein neues Transaktions Objekt und macht die neue Transaktion zur aktiven Transaktion.

Beginnen Sie, indem Sie eine Transaktion im Schlüssel "HKCU: Software" Starten \\ .

```powershell
start-transaction
```

Der folgende Befehl verwendet den Get-Transaction-Befehl, um die aktive Transaktion zu erhalten.

```powershell
get-transaction
```

Das Ergebnis zeigt das-Objekt, das die aktive Transaktion darstellt.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

Mit dem folgenden Befehl wird der Registrierungsschlüssel MyCompany als Teil der Transaktion hinzugefügt. Der Befehl verwendet den UseTransaction-Parameter (usetx), um den Befehl in die aktive Transaktion einzubeziehen.

```powershell
new-item MyCompany -use
```

Mit dem folgenden Befehl wird eine neue Transaktion gestartet. Der Befehl verwendet den unabhängigen Parameter, um anzugeben, dass es sich bei dieser Transaktion nicht um einen Abonnenten der aktiven Transaktion handelt.

```powershell
start-transaction -independent
```

Wenn Sie eine unabhängige Transaktion erstellen, wird die neue Transaktion (zuletzt erstellt) zur aktiven Transaktion. Sie können einen Get-Transaction Befehl verwenden, um die aktive Transaktion zu erhalten.

```powershell
get-transaction
```

Beachten Sie, dass der Abonnement Zähler der Transaktion 1 ist, was bedeutet, dass keine anderen Abonnenten vorhanden sind und dass die Transaktion neu ist.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

Die neue Transaktion muss abgeschlossen (entweder ein Commit oder ein Rollback) sein, bevor Sie die ursprüngliche Transaktion verwalten können.

Der folgende Befehl fügt den Schlüssel "myothercompany" der Registrierung hinzu. Der Befehl verwendet den UseTransaction-Parameter (usetx), um den Befehl in die aktive Transaktion einzubeziehen.

```powershell
new-item MyOtherCompany -usetx
```

Führen Sie nun ein Rollback für die Transaktion aus. Wenn eine einzelne Transaktion mit zwei Abonnenten vorhanden ist, führt ein Rollback der Transaktion für alle Abonnenten ein Rollback für die gesamte Transaktion aus.

Da diese Transaktionen jedoch unabhängig sind, werden durch das Rollback der neuesten Transaktion die Registrierungs Änderungen abgebrochen und die ursprüngliche Transaktion zur aktiven Transaktion.

```powershell
undo-transaction
```

Ein Get-Transaction Befehl bestätigt, dass die ursprüngliche Transaktion in der Sitzung noch aktiv ist.

```powershell
get-transaction
```

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

Der folgende Befehl führt einen Commit für die aktive Transaktion aus.

```powershell
complete-transaction
```

Mit einem Get-ChildItem Befehl wird angezeigt, dass die Registrierung geändert wurde.

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

## <a name="see-also"></a>SIEHE AUCH

[Start-Transaction](xref:Microsoft.PowerShell.Management.Start-Transaction)

[Get-Transaction](xref:Microsoft.PowerShell.Management.Get-Transaction)

[Complete-Transaction](xref:Microsoft.PowerShell.Management.Complete-Transaction)

[Undo-Transaction](xref:Microsoft.PowerShell.Management.Undo-Transaction)

[Use-Transaction](xref:Microsoft.PowerShell.Management.Use-Transaction)

[Get-PSProvider](xref:Microsoft.PowerShell.Management.Get-PSProvider)

[Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

[about_Providers](about_Providers.md)
