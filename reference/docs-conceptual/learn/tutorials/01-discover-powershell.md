---
title: PowerShell entdecken
ms.date: 03/12/2021
ms.custom: chnoring
ms.reviewer: sewhee
description: Erfahren Sie, was PowerShell ist, und erlernen Sie einige grundlegende Befehle, mit denen Sie PowerShell besser kennenlernen.
ms.openlocfilehash: 34bbd465a918224c203e7243834e7fb3a3a6070c
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "104730000"
---
# <a name="discover-powershell"></a>PowerShell entdecken

PowerShell ist sowohl eine Befehlszeilenshell als auch eine Skriptsprache. PowerShell wurde zunächst nur in Windows verwendet. Es war ursprünglich für die Automatisierung von Verwaltungsaufgaben vorgesehen, ist inzwischen jedoch plattformübergreifend und kann für eine Vielzahl von Aufgaben verwendet werden.

PowerShell zeichnet sich dadurch aus, dass es anstelle von Text .NET-Objekte akzeptiert und zurückgibt.
Dies erleichtert das Verbinden unterschiedlicher Befehle in einer _Pipeline_.

> [!NOTE]
> Pipelines werden in dieser Tutorialreihe ausführlicher behandelt.

Die Ergebnisse müssen jedoch möglicherweise noch ein wenig _behandelt_ werden.

## <a name="what-can-powershell--be-used-for"></a>Wofür lässt sich PowerShell verwenden?

PowerShell wird inzwischen für einen größeren Bereich als nur für Windows verwendet. Es wird immer noch für die Aufgabenautomatisierung unter Windows genutzt, Sie können es jedoch jetzt für eine Vielzahl von Aufgaben verwenden, z. B. die folgenden:

- **Cloudverwaltung**. PowerShell lässt sich zum Verwalten von Cloudressourcen verwenden. Beispielsweise können Sie Informationen zu Cloudressourcen abrufen und Cloudressourcen aktualisieren oder neue Ressourcen bereitstellen.
- **CI/CD**. PowerShell kann auch als Teil einer Continuous Integration/Continuous Deployment-Pipeline verwendet werden.
- **Automatisieren von Aufgaben für Active Directory und Exchange**. Sie können mit PowerShell fast jede Aufgabe unter Windows automatisieren, z. B. das Erstellen von Benutzern in Active Directory und von Postfächern in Exchange.

Es gibt noch viele weitere Verwendungsbereiche. Der obigen Liste können Sie entnehmen, dass diese Bereiche erheblich erweitert wurden.

## <a name="who-uses-powershell"></a>Von wem wird PowerShell verwendet?

PowerShell ist sehr leistungsstark, und viele Personen in zahlreichen Rollen können von seiner Verwendung profitieren. Früher wurde PowerShell von der Systemadministratorrolle verwendet, inzwischen wird es jedoch von Personen in den Bereichen DevOps, CloudOps und von Entwicklern genutzt.

## <a name="powershell-cmdlets"></a>PowerShell-Cmdlets

PowerShell bietet Hunderte vorinstallierter Befehle. PowerShell-Befehle werden als Cmdlets (ausgesprochen wie „Commandlets“) bezeichnet.

Der Name jedes Cmdlets besteht aus einer Kombination von Verb und Nomen, wie beispielsweise in `Get-Process`. Diese Namenskonvention erleichtert das Verständnis der Funktion des Cmdlets. Außerdem erleichtert sie die Suche nach einem Befehl. Wenn Sie ein Cmdlet suchen, können Sie nach dem Verb oder dem Nomen filtern.

### <a name="using-cmdlets-to-explore-powershell"></a>Verwenden von Cmdlets zum Erkunden von PowerShell

Wenn Sie PowerShell zum ersten Mal verwenden, fühlen Sie sich vielleicht eingeschüchtert, weil Sie glauben, dass Ihnen noch viele Kenntnisse fehlen.
PowerShell ist jedoch so aufgebaut, dass Sie es in kleinen Schritten entsprechend Ihren Anforderungen erlernen können.

PowerShell enthält Cmdlets, die Ihnen helfen, PowerShell zu erkunden. Mit den folgenden vier Cmdlets können Sie ermitteln, welche Befehle verfügbar sind, was sie ausführen und für welche Typen sie verwendet werden.

- `Get-Verb`. Dieser Befehl gibt eine Liste mit Verben zurück, die von den meisten Befehlen verwendet werden.
  Außerdem wird in der Antwort die Funktion des jeweiligen Verbs beschrieben. Da die meisten Befehle dieser Namenskonvention folgen, lässt sich aus dieser die Funktion eines Befehls erschließen. Dies hilft Ihnen nicht nur, den entsprechenden Befehl auszuwählen, sondern auch beim Erstellen eines Befehls, diesen zu benennen.
- `Get-Command`. Dieser Befehl ruft eine Liste aller Befehle ab, die auf Ihrem Computer installiert sind.
- `Get-Member`. Mit diesem Befehl lässt sich für die objektbasierte Ausgabe ermitteln, welches Objekt, welche Eigenschaften und welche Methoden für einen Befehl verfügbar sind.
- `Get-Help`. Wenn Sie diesen Befehl mit dem Namen eines Befehls als Argument aufrufen, wird eine Hilfeseite angezeigt, auf der die verschiedenen Teile eines Befehls beschrieben werden.

Mit diesen Befehlen können Sie nahezu alles ermitteln, was Sie über PowerShell wissen müssen.

### <a name="verb"></a>Verb

Das Verb ist ein wichtiges Konzept in PowerShell. Es ist ein Benennungsstandard, dem die meisten Cmdlets entsprechen. Sie müssen diesen Benennungsstandard befolgen, wenn Sie eigene Befehle schreiben. Das _Verb_ bezeichnet, was ausgeführt werden soll, z. B. das Lesen von Daten oder das Ändern von Daten. PowerShell verfügt über eine standardisierte Liste von Verben. Um eine vollständige Liste aller möglichen Verben abzurufen, verwenden Sie das Cmdlet `Get-Verb`:

```powershell
Get-Verb
```

Die Ausgabe des Cmdlets ist eine umfangreiche Liste von Verben. Die Antwort liefert außerdem Informationen über den Verwendungszweck eines Verbs. Dies ist die erste Zeile der Ausgabe:

```output
Verb        AliasPrefix Group          Description
----        ----------- -----          -----------
Add         a           Common         Adds a resource to a container, or attaches an item to ano…
```

## <a name="find-commands-with-get-command"></a>Suchen von Befehlen mit „Get-Command“

Mit dem Cmdlet `Get-Command` wird eine Liste aller verfügbaren Befehle zurückgegeben, die auf Ihrem System installiert sind.
Die zurückgegebene Liste ist recht umfangreich. Um die Suche nach Befehlen zu vereinfachen, können Sie die Menge der zurückgegebenen Informationen einschränken. Sie können die Antwort entweder mithilfe von Parametern oder mithilfe von Hilfs-Cmdlets filtern.

### <a name="filter-on-name"></a>Filtern nach Namen

Sie können die Ausgabe von `Get-Command` mithilfe verschiedener Parameter filtern. Bei dieser Art von Filterung handelt es sich um die Abfrage nach einer bestimmten Eigenschaft im Befehl. Sie legen fest, nach welcher Eigenschaft gefiltert werden soll, und geben dann eine Zeichenfolge an, mit der verglichen werden soll. Dies ergibt einen Vergleich, der wie folgt aussieht:

```powershell
Get-Command -Name '*Process'
```

In diesem Befehl wird mit der Filterung eine genaue Übereinstimmung mit dem angegebenen Zeichenfolgenargument gesucht.
Wenn Sie mehr Flexibilität benötigen, können Sie im Vergleich das Platzhalterzeichen`*` verwenden, mit dem ein Musterabgleich erfolgt. Im folgenden Code wird nach allen Befehlen gesucht, deren Name mit „Process“ endet.

Im obigen Beispiel wird zum Filtern der Parameter `-Name` verwendet. Sie können nicht nur nach `-Name`, sondern auch z. B. nach `-ParameterName` oder `-Type` filtern.

### <a name="filtering-on-noun-and-verb"></a>Filtern nach Nomen und Verb

Oben wurde gezeigt, wie Sie nach `-Name` filtern können und dass auch nach anderen Parametern gefiltert werden kann. Sie können auch nach Verb und Nomen filtern. Dabei wird nach einer Komponente eines Befehlsnamens gefiltert.

- **Filtern nach Verb**. Das Verb im Namen eines Befehls ist der linke Teil des Befehls. Im Befehl `Get-Process` ist `Get` das Verb. Um nach dem Verbteil im Befehl zu filtern, geben Sie `-Verb` als Parameter an, z. B. wie im folgenden Befehl:

   ```powershell
   Get-Command -Verb 'Get'
   ```

   Mit dem obigen Befehl werden alle Befehle aufgelistet, deren Verb `Get` lautet.

- **Filtern nach Nomen**. Das Nomen ist der rechte Teil eines Befehls. Während das Verb eines der durch den Aufruf von `Get-Verb` zurückgegebenen Verben sein muss, ist als Nomen ein beliebiges Substantiv möglich. Im Befehl `Get-Process` lautet das Nomen `Process`. Um nach Nomen zu filtern, geben Sie `-Noun` als Parameter und ein Zeichenfolgenargument an, z. B. wie im folgenden Befehl:

   ```powershell
   Get-Command -Noun U*
   ```

Wenn nur nach Verb oder Nomen gefiltert wird, kann das Ergebnis immer noch sehr umfangreich sein. Um die Suche einzugrenzen, können die beiden Parameter kombiniert werden, wie im folgenden Beispiel:

```powershell
Get-Command -Verb Get -Noun U*
```

Das Ergebnis des obigen Beispiels lautet wie folgt:

```output
CommandType     Name                         Version    Source
-----------     ----                         -------    ------
Cmdlet          Get-UICulture                7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Unique                   7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Uptime                   7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-UsageAggregates          2.0.0      Az.Billing
```

In dem Sie den Namen des Verbs angegeben haben, konnten Sie die Suche erheblich eingrenzen.

### <a name="use-helper-cmdlets-to-filter-results"></a>Verwenden von Hilfs-Cmdlets zum Filtern von Ergebnissen

Sie können nicht nur nach Parametern filtern, sondern zum Filtern auch Befehle verwenden. Nachstehend werden einige Befehle beschrieben, die als Filter fungieren können:

- `Select-Object`. Dies ist ein sehr vielseitiger Befehl, mit dem Sie bestimmte Eigenschaften eines oder mehrerer Objekten auswählen können. Zudem können Sie mit diesem Befehl die zurückgegebene Antwort beschränken. Im folgenden Beispiel wird mit `Select-Object` eine begrenzte Anzahl von Datensätzen angefordert:

   ```powershell
   Get-Command | Select-Object -First 3
   ```

   Das Ergebnis des obigen Befehls sind die ersten drei Befehle. Das Ergebnis lautet wie folgt:

   ```output
   CommandType     Name                                               Version    Source
   -----------     ----                                               -------    ------
   Alias           Add-AdlAnalyticsDataSource                         1.0.2      Az.DataLakeAnalytics
   Alias           Add-AdlAnalyticsFirewallRule                       1.0.2      Az.DataLakeAnalytics
   Alias           Add-AdlStoreFirewallRule                           1.3.0      Az.DataLakeStore
   ```

   Es lohnt sich, diesen Befehl genauer zu betrachten, da er noch viel mehr kann (siehe [Select-Object](/powershell/module/microsoft.powershell.utility/select-object)).

- `Where-Object`. „Where-Object“ unterstützt Sie bei der Auswahl von Objekten aus einer Sammlung, die auf den Werten von Eigenschaften basiert. Der Befehl akzeptiert einen Ausdruck, in dem Sie angeben können, welche Spalte(n) mit welchen Werten verglichen werden soll(en). Um alle Process-Objekte zu suchen, deren `ProcessName` mit `p` beginnt, können Sie `Where-Object` wie folgt verwenden:

  ```powershell
  Get-Process | Where-Object {$_.ProcessName -Like "p*"}
  ```

  Im obigen Befehl erzeugt das Cmdlet `Get-Process` eine Sammlung von Process-Objekten. Zum Filtern der Antwort wird der Befehl `Where-Object` _weitergereicht_. „Weiterreichen“ bedeutet, dass mehrere Befehle mithilfe eines senkrechten Strichs (`|`) verbunden werden. Dabei fungiert die Ausgabe eines Befehls als Eingabe für den nächsten Befehl (von links nach rechts). `Where-Object` filtert mithilfe eines Ausdrucks. Im Ausdruck selbst werden der Operator `-Like` und ein Zeichenfolgenargument verwendet, das ein Platzhalterausdruck ist.

## <a name="explore-objects-with-get-member"></a>Untersuchen von Objekten mit „Get-Member“

Nachdem Sie das gewünschte Cmdlet gefunden haben, möchten Sie mehr über die von ihm erzeuge Ausgabe erfahren. Bei Ausgaben sind verschiedene Aspekte zu berücksichtigen:

- **Eigenständig**. Möglicherweise führen Sie nur ein Cmdlet aus, und die Ausgabe soll in einem Bericht angezeigt werden. In diesem Fall müssen Sie wissen, ob die vom Befehl erzeugte Ausgabe den gewünschten Zweck erfüllt oder geändert werden muss.
- **Verwendung in einer Pipeline**. In PowerShell werden häufig mehrere Befehle in einer Pipeline miteinander verbunden, um Daten abzurufen, zu filtern und zu transformieren. Damit ein Befehl in eine Pipeline aufgenommen werden kann, müssen Sie überprüfen, welche Eingabe er akzeptiert und welche Ausgabe er erzeugt. In einer Pipeline wird die Ausgabe eines Befehls als Eingabe eines weiteren Befehls verwendet.

Mit dem Cmdlet `Get-Member` werden die Eigenschaften und Methoden des Ergebnisses angezeigt. Es zeigt außerdem den Typ des Objekts an. Reichen Sie die Ausgabe, die Sie überprüfen möchten, an `Get-Member` weiter.

```powershell
Get-Process | Get-Member
```

Im Ergebnis werden durch `TypeName` der zurückgegebene Typ und dann alle Eigenschaften und Methoden des Objekts angezeigt. Dies ist ein Auszug aus einem solchen Ergebnis:

```output
TypeName: System.Diagnostics.Process

Name        MemberType     Definition
----        ----------     ----------
Handles     AliasProperty  Handles = Handlecount
Name        AliasProperty  Name = ProcessName
```

Ein Objekt verfügt in der Regel über viele Eigenschaften und Methoden. Um das Gesuchte leichter zu finden, können Sie die Ergebnisse filtern. Mit dem-Parameter `-MemberType` können Sie z. B. angeben, dass alle Methoden angezeigt werden sollen, wie im folgenden Beispiel:

```powershell
Get-Process | Get-Member -MemberType Method
```

In der zurückgegebenen Antwort werden in der Regel nur einige Eigenschaften angezeigt. In der obigen Antwort werden `Name`, `MemberType` und `Definition` angezeigt. Um die Anzeige zu ändern, können Sie das Cmdlet `Select-Object` verwenden. Mit `Select-Object` können Sie festlegen, welche Spalten angezeigt werden sollen. Sie können den Namen der Spalte, eine durch Kommas getrennte Liste oder einen Platzhalter (`*`) angeben. Im folgenden Beispiel wird `Select-Object` zum Abrufen von `Name` und `Definition` verwendet:

```powershell
Get-Process | Get-Member | Select-Object Name, Definition
```

### <a name="search-by-type"></a>Typbasiertes Suchen

Eine weitere Möglichkeit zum Suchen des gewünschten Befehls ist das Suchen aller Befehle, die für denselben Typ verwendet werden. Wenn Sie `Get-Member` verwendet haben, enthält die erste Zeile der Antwort den zurückgegebenen Typ, wie in diesem Beispiel:

```output
TypeName: System.Diagnostics.Process
```

Sie können jetzt anhand dieses Typs nach Befehlen suchen:

```powershell
Get-Command -ParameterType Process
```

Das Ergebnis des obigen Befehls ist eine Liste mit Befehlen, die ausschließlich für den Typ `Process` ausgeführt werden:

```output
CommandType     Name                         Version    Source
-----------     ----                         -------    ------
Cmdlet          Debug-Process                7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Enter-PSHostProcess          7.1.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-Process                  7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Get-PSHostProcessInfo        7.1.0.0    Microsoft.PowerShell.Core
Cmdlet          Stop-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Wait-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
```

Wie Sie sehen, lässt sich durch die Angabe des Typs eines Befehls die Suche nach Befehlen stark eingrenzen.

## <a name="exercise---calling-your-first-command"></a>Übung: Aufrufen des ersten Befehls

In dieser Übung lernen Sie, wie Sie Ihren ersten Befehl ausführen.

1. Starten Sie eine PowerShell-Konsole, indem Sie `pwsh` eingeben:

   ```powershell
   pwsh
   ```

1. Führen Sie `$PSVersionTable.PSVersion` aus:

   ```powershell
   $PSVersionTable.PSVersion
   ```

   Die Ausgabe sieht in etwa wie folgt aus:

   ```output
   Major  Minor  Patch  PreReleaseLabel BuildLabel
   -----  -----  -----  --------------- ----------
   7      1      0
   ```

   Herzlichen Glückwunsch! Sie haben ihren ersten Befehl erfolgreich ausgeführt und konnten die auf Ihrem System installierte Version von PowerShell abrufen.

## <a name="exercise---find-related-commands"></a>Übung: Suchen verwandter Befehle

In dieser Übung sollen Sie mehr über einen Befehl erfahren. Dabei erfahren Sie, für welchen Typ der Befehl verwendet wird und welche ähnlichen Befehle für denselben Typ verwendet werden.

1. Stellen Sie sicher, dass eine PowerShell-Shell gestartet wurde.
1. Führen Sie den Befehl `Get-Process` aus:

   ```powershell
   Get-Process | Get-Member | Select-Object TypeName -Unique
   ```

   Die Ausgabe sieht ungefähr wie folgt aus:

   ```output
   TypeName
   --------
   System.Diagnostics.Process
   --------
   ```

   Sie erhalten als Ergebnis die vom Befehl `Get-Command` zurückgegebenen Typen. Jetzt können Sie ermitteln, welche sonstigen Befehle ebenfalls für diese Typen ausgeführt werden können.

1. Führen Sie den Befehl `Get-Command` aus:

   ```powershell
   Get-Command -ParameterType Process
   ```

   Die Ausgabe sieht ungefähr wie folgt aus:

   ```output
   CommandType     Name                         Version    Source
    -----------     ----                        -------    ------
    Cmdlet          Debug-Process               7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Enter-PSHostProcess         7.1.0.0    Microsoft.PowerShell.Core
    Cmdlet          Get-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Get-PSHostProcessInfo       7.1.0.0    Microsoft.PowerShell.Core
    Cmdlet          Stop-Process                7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Wait-Process                7.0.0.0    Microsoft.PowerShell.Managem…
   ```

   Herzlichen Glückwunsch! Sie haben weitere Befehle ermittelt, die ebenfalls für den Typ `Process` ausgeführt werden können.
   `Get-Member` eignet sich gut, um weitere Befehle zu ermitteln, die Sie sich als Nächstes ansehen sollten.

## <a name="summary"></a>Zusammenfassung

In diesem ersten Teil haben Sie erfahren, was PowerShell ist und in welchen Bereichen es verwendet werden kann. Dann haben Sie einiges über Cmdlets erfahren, insbesondere über `Get-Command`, `Get-Verb` und `Get-Member`. Die Kenntnis dieser Cmdlets ist eine wichtige Voraussetzung für das Erlernen von PowerShell. Im nächsten Abschnitt erfahren Sie, wie Sie das leistungsfähige Hilfesystem verwenden.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)
- [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)
