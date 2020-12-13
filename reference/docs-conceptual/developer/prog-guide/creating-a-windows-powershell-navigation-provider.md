---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen eines Windows PowerShell-Navigationsanbieters
description: Erstellen eines Windows PowerShell-Navigationsanbieters
ms.openlocfilehash: 73d4971fb91acaef9e1f20226e7b9b883730e394
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658673"
---
# <a name="creating-a-windows-powershell-navigation-provider"></a>Erstellen eines Windows PowerShell-Navigationsanbieters

In diesem Thema wird beschrieben, wie Sie einen Windows PowerShell-Navigations Anbieter erstellen, der im Datenspeicher navigieren kann. Dieser Anbietertyp unterstützt rekursive Befehle, unterstützte Container und relative Pfade.

> [!NOTE]
> Sie können die c#-Quelldatei (AccessDBSampleProvider05.cs) für diesen Anbieter mit dem Microsoft Windows Software Development Kit für Windows Vista und .NET Framework 3,0-Laufzeitkomponenten herunterladen. Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).
> Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar. Weitere Informationen zu anderen Windows PowerShell-Anbieter Implementierungen finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./designing-your-windows-powershell-provider.md).

Der hier beschriebene Anbieter ermöglicht dem Benutzer das Verarbeiten einer Access-Datenbank als Laufwerk, sodass der Benutzer zu den Datentabellen in der Datenbank navigieren kann. Beim Erstellen eines eigenen navigationsanbieters können Sie Methoden implementieren, die für das Laufwerk qualifizierte Pfade für die Navigation, normalisieren relativer Pfade, Verschieben von Elementen des Datenspeicher sowie Methoden zur Verfügung stellen, die untergeordnete Namen erhalten, den übergeordneten Pfad eines Elements erhalten und testen, ob ein Element ein Container ist.

> [!CAUTION]
> Beachten Sie, dass bei diesem Entwurf eine Datenbank mit einem Feld mit der namens-ID und der Typ des Felds longinteger ist.

## <a name="define-the-windows-powershell-provider"></a>Definieren des Windows PowerShell-Anbieters

Ein Windows PowerShell-Navigations Anbieter muss eine .NET-Klasse erstellen, die von der [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Basisklasse abgeleitet wird. Hier ist die Klassendefinition für den in diesem Abschnitt beschriebenen Navigations Anbieter.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="31-32":::

Beachten Sie, dass das [System. Management. Automation. Provider. cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) -Attribut in diesem Anbieter zwei Parameter enthält. Der erste Parameter gibt einen benutzerfreundlichen Namen für den Anbieter an, der von Windows PowerShell verwendet wird. Der zweite Parameter gibt die Windows PowerShell-spezifischen Funktionen an, die der Anbieter während der Befehls Verarbeitung für die Windows PowerShell-Laufzeit verfügbar macht. Für diesen Anbieter gibt es keine Windows PowerShell-spezifischen Funktionen, die hinzugefügt werden.

## <a name="defining-base-functionality"></a>Definieren der Basisfunktionalität

Wie in [Entwerfen Ihres PS-Anbieters](./designing-your-windows-powershell-provider.md)beschrieben, wird die [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Basisklasse von mehreren anderen Klassen abgeleitet, die unterschiedliche Anbieter Funktionen bereitgestellt haben. Ein Windows PowerShell-Navigations Anbieter muss daher alle Funktionen definieren, die von diesen Klassen bereitgestellt werden.

Informationen zum Implementieren von Funktionen zum Hinzufügen von Sitzungs spezifischen Initialisierungs Informationen und zum Freigeben von Ressourcen, die vom Anbieter verwendet werden, finden Sie unter [Erstellen eines einfachen PS-Anbieters](./creating-a-basic-windows-powershell-provider.md). Die meisten Anbieter (einschließlich des hier beschriebenen Anbieters) können jedoch die Standard Implementierung dieser Funktionalität verwenden, die von Windows PowerShell bereitgestellt wird.

Um Zugriff auf den Datenspeicher über ein Windows PowerShell-Laufwerk zu erhalten, müssen Sie die Methoden der Basisklasse [System. Management. Automation. Provider. drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider) implementieren. Weitere Informationen zum Implementieren dieser Methoden finden Sie unter [Erstellen eines Windows PowerShell-Laufwerks Anbieters](./creating-a-windows-powershell-drive-provider.md).

Zum Bearbeiten der Elemente eines Datenspeicher, z. b. zum erhalten, festlegen und Löschen von Elementen, muss der Anbieter die von der [System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Basisklasse bereitgestellten Methoden implementieren. Weitere Informationen zum Implementieren dieser Methoden finden Sie unter [Erstellen eines Windows PowerShell-Element Anbieters](./creating-a-windows-powershell-item-provider.md).

Um die untergeordneten Elemente (oder deren Namen) des Datenspeicher sowie Methoden zum Erstellen, kopieren, umbenennen und Entfernen von Elementen zu erhalten, müssen Sie die Methoden implementieren, die von der [System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Basisklasse bereitgestellt werden. Weitere Informationen zum Implementieren dieser Methoden finden Sie unter [Erstellen eines Windows PowerShell-Container Anbieters](./creating-a-windows-powershell-container-provider.md).

## <a name="creating-a-windows-powershell-path"></a>Erstellen eines Windows PowerShell-Pfads

Windows PowerShell-Navigations Anbieter verwenden Sie einen Anbieter internen Windows PowerShell-Pfad, um durch die Elemente des Datenspeicher zu navigieren. Um einen Anbieter internen Pfad zu erstellen, muss der Anbieter die [System. Management. Automation. Provider. navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) -Methode implementieren, um Aufrufe vom Combine-Path-Cmdlet zu unterstützen. Diese Methode kombiniert einen übergeordneten und untergeordneten Pfad zu einem Anbieter internen Pfad, wobei ein Anbieter spezifisches Pfad Trennzeichen zwischen den übergeordneten und untergeordneten Pfaden verwendet wird.

Die Standard Implementierung verwendet Pfade mit "/" oder " \\ " als Pfad Trennzeichen, normalisiert das Pfad \\ Trennzeichen in "", kombiniert die übergeordneten und untergeordneten Pfad Teile mit dem Trennzeichen zwischen diesen und gibt dann eine Zeichenfolge zurück, die die kombinierten Pfade enthält.

Diese Methode wird von diesem Navigations Anbieter nicht implementiert. Der folgende Code ist jedoch die Standard Implementierung der [System. Management. Automation. Provider. navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) -Methode.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermakepath](Msh_samplestestcmdlets#testprovidermakepath)]  -->

#### <a name="things-to-remember-about-implementing-makepath"></a>Dinge, die Sie bei der Implementierung von makepath beachten sollten

Die folgenden Bedingungen können für Ihre Implementierung von [System. Management. Automation. Provider. navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)gelten:

- Ihre Implementierung der [System. Management. Automation. Provider. navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) -Methode sollte den Pfad nicht als einen gültigen voll qualifizierten Pfad im Anbieter Namespace validieren. Beachten Sie, dass jeder Parameter nur einen Teil eines Pfads darstellen kann, und die kombinierten Teile generieren möglicherweise keinen voll qualifizierten Pfad. Beispielsweise kann die [System. Management. Automation. Provider. navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) -Methode für den File System-Anbieter "Windows\System32" im `parent` Parameter und "abc.dll" im `child` Parameter empfangen. Die-Methode verbindet diese Werte mit dem \\ Trennzeichen "" und gibt "windows\system32\abc.dll" zurück, bei dem es sich nicht um einen voll qualifizierten Dateisystempfad handelt.

  > [!IMPORTANT]
  > Die im Aufruf von [System. Management. Automation. Provider. navigationcmdletprovider. makepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) bereitgestellten Pfad Teile können Zeichen enthalten, die im Anbieter Namespace nicht zulässig sind. Diese Zeichen werden wahrscheinlich für die Platzhalter Erweiterung verwendet, und die Implementierung dieser Methode sollte Sie nicht entfernen.

## <a name="retrieving-the-parent-path"></a>Abrufen des übergeordneten Pfads

Windows PowerShell-Navigations Anbieter implementieren die [System. Management. Automation. Provider. navigationcmdletprovider. getbientpath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) -Methode, um den übergeordneten Teil des angegebenen vollständigen oder partiellen anbieterspezifischen Pfads abzurufen. Die-Methode entfernt den untergeordneten Teil des Pfads und gibt den übergeordneten Pfadteil zurück. Der `root` -Parameter gibt den voll qualifizierten Pfad zum Stamm eines Laufwerks an. Dieser Parameter kann NULL oder leer sein, wenn ein bereitgestelltes Laufwerk nicht für den Abruf Vorgang verwendet wird. Wenn ein root-Wert angegeben wird, muss die Methode einen Pfad zu einem Container in derselben Struktur wie der Stamm zurückgeben.

Der Beispiel-Navigations Anbieter setzt diese Methode nicht außer Kraft, sondern verwendet die Standard Implementierung.
Sie akzeptiert Pfade, die sowohl "/" als auch " \\ " als Pfad Trennzeichen verwenden. Zuerst wird der Pfad so normalisiert, dass nur die Trennzeichen " \\ " vorhanden sind. Anschließend wird der übergeordnete Pfad auf dem letzten "" entfernt, \\ und der übergeordnete Pfad wird zurückgegeben.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetparentpath](Msh_samplestestcmdlets#testprovidergetparentpath)]  -->

#### <a name="to-remember-about-implementing-getparentpath"></a>So denken Sie an die Implementierung von getcentpath

Ihre Implementierung der [System. Management. Automation. Provider. navigationcmdletprovider. getparameentpath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) -Methode sollte den Pfad lexikalisch auf dem Pfad Trennzeichen für den Anbieter Namespace aufteilen. Beispielsweise verwendet der File System-Anbieter diese Methode, um nach dem letzten "" zu suchen, \\ und gibt alles links vom Trennzeichen zurück.

## <a name="retrieve-the-child-path-name"></a>Abrufen des Namens des untergeordneten Pfads

Der Navigations Anbieter implementiert die [System. Management. Automation. Provider. navigationcmdletprovider. getchildname *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) -Methode, um den Namen (Blatt Element) der untergeordneten Elemente des Elements abzurufen, das sich unter dem angegebenen vollständigen oder partiellen anbieterspezifischen Pfad befindet.

Der Beispiel-Navigations Anbieter setzt diese Methode nicht außer Kraft. Die Standard Implementierung ist unten dargestellt. Sie akzeptiert Pfade, die sowohl "/" als auch " \\ " als Pfad Trennzeichen verwenden. Zuerst wird der Pfad so normalisiert, dass nur die Trennzeichen " \\ " vorhanden sind. Anschließend wird der übergeordnete Pfad auf dem letzten " \\ " entfernt und der Name des untergeordneten Pfads zurückgegeben.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildname](Msh_samplestestcmdlets#testprovidergetchildname)]  -->

#### <a name="things-to-remember-about-implementing-getchildname"></a>Dinge, die Sie beim Implementieren von getchildname beachten sollten

Ihre Implementierung der [System. Management. Automation. Provider. navigationcmdletprovider. getchildname *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) -Methode sollte den Pfad lexikalisch auf dem Pfad Trennzeichen aufteilen. Wenn der angegebene Pfad keine Pfad Trennzeichen enthält, sollte die Methode den Pfad unverändert zurückgeben.

> [!IMPORTANT]
> Der im-Aufrufwert dieser Methode angegebene Pfad enthält möglicherweise Zeichen, die im Anbieter Namespace unzulässig sind. Diese Zeichen werden wahrscheinlich für die Platzhalter Erweiterung oder für Vergleiche mit regulärem Ausdruck verwendet, und die Implementierung dieser Methode sollte Sie nicht entfernen.

## <a name="determining-if-an-item-is-a-container"></a>Ermitteln, ob ein Element ein Container ist

Der Navigations Anbieter kann die [System. Management. Automation. Provider. navigationcmdletprovider. isitemcontainer *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) -Methode implementieren, um zu bestimmen, ob der angegebene Pfad einen Container angibt. Sie gibt true zurück, wenn der Pfad einen Container darstellt, andernfalls false. Der Benutzer benötigt diese Methode, damit das `Test-Path` Cmdlet für den angegebenen Pfad verwendet werden kann.

Der folgende Code zeigt die [System. Management. Automation. Provider. navigationcmdletprovider. isitemcontainer *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) -Implementierung in unserem Beispiel-Navigations Anbieter. Die-Methode überprüft, ob der angegebene Pfad richtig ist und ob die Tabelle vorhanden ist, und gibt true zurück, wenn der Pfad einen Container angibt.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="847-872":::

#### <a name="things-to-remember-about-implementing-isitemcontainer"></a>Dinge, die Sie beim Implementieren von isitemcontainer beachten sollten

Die .NET-Klasse des navigationsanbieters kann die Anbieter Funktionen von expandwildcards, Filtern, einschließen oder Ausschließen von der [System. Management. Automation. Provider. providerfunktionalitäten](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) -Enumeration deklarieren. In diesem Fall muss die Implementierung von [System. Management. Automation. Provider. navigationcmdletprovider. isitemcontainer *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) sicherstellen, dass der weiter gegebene Pfad den Anforderungen entspricht. Zu diesem Zweck sollte die-Methode auf die entsprechende Eigenschaft zugreifen, z. b. die [System. Management. Automation. Provider. cmdletprovider. Exclude *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude) -Eigenschaft.

## <a name="moving-an-item"></a>Verschieben eines Elements

Zur Unterstützung des `Move-Item` Cmdlets implementiert der Navigations Anbieter die [System. Management. Automation. Provider. navigationcmdletprovider. muveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) -Methode. Diese Methode verschiebt das durch den-Parameter angegebene Element in den `path` Container an dem Pfad, der im-Parameter angegeben ist `destination` .

Der Beispiel-Navigations Anbieter überschreibt nicht die [System. Management. Automation. Provider. navigationcmdletprovider. muveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) -Methode. Im folgenden finden Sie die Standard Implementierung.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitem](Msh_samplestestcmdlets#testprovidermoveitem)]  -->

#### <a name="things-to-remember-about-implementing-moveitem"></a>Wichtige Punkte beim Implementieren von "muveitem"

Die .NET-Klasse des navigationsanbieters kann die Anbieter Funktionen von expandwildcards, Filtern, einschließen oder Ausschließen von der [System. Management. Automation. Provider. providerfunktionalitäten](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities) -Enumeration deklarieren. In diesem Fall muss die Implementierung von [System. Management. Automation. Provider. navigationcmdletprovider. muveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) sicherstellen, dass der weiter gegebene Pfad den Anforderungen entspricht. Zu diesem Zweck sollte die-Methode auf die entsprechende Eigenschaft zugreifen, z. b. die **cmdletprovider. Exclude** -Eigenschaft.

Standardmäßig sollten über schreibungen dieser Methode Objekte nicht über vorhandene Objekte verschieben, es sei denn, die [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) -Eigenschaft ist auf festgelegt `true` . Beispielsweise kopiert der File System-Anbieter c:\temp\abc.txt nicht über eine vorhandene c:\bar.txt Datei, es sei denn, die [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) -Eigenschaft ist auf festgelegt `true` . Wenn der im `destination` -Parameter angegebene Pfad vorhanden ist und ein Container ist, ist die [System. Management. Automation. Provider. cmdletprovider. Force *](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force) -Eigenschaft nicht erforderlich. In diesem Fall sollte [System. Management. Automation. Provider. navigationcmdletprovider. MoveItem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) das Element, das durch den-Parameter angegeben ist, in den Container verschieben, der `path` durch den-Parameter als untergeordnetes Element angegeben wird `destination` .

Ihre Implementierung der [System. Management. Automation. Provider. navigationcmdletprovider. muveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) -Methode sollte [System. Management. Automation. Provider. cmdletprovider. rechtdprocess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) aufzurufen und ihren Rückgabewert überprüfen, bevor Änderungen am Datenspeicher vorgenommen werden. Diese Methode wird verwendet, um die Ausführung eines Vorgangs zu bestätigen, wenn eine Änderung am Systemstatus vorgenommen wird, z. b. das Löschen von Dateien.
[System. Management. Automation. Provider. cmdletprovider. schuldprocess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) sendet den Namen der Ressource, die an den Benutzer geändert werden soll, wobei die Windows PowerShell-Laufzeit alle Befehlszeilen Einstellungen oder Einstellungs Variablen unternimmt, um zu bestimmen, was dem Benutzer angezeigt werden soll.

Nachdem der Aufruf von [System. Management. Automation. Provider. cmdletprovider. dendprocess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess) zurückgegeben `true` wurde, sollte die [System. Management. Automation. Provider. navigationcmdletprovider. muveitem *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) -Methode die [System. Management. Automation. Provider. cmdletprovider. dendcontinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) -Methode aufruft. Diese Methode sendet eine Meldung an den Benutzer, um Feedback zu geben, ob der Vorgang fortgesetzt werden soll. Der Anbieter sollte [System. Management. Automation. Provider. cmdletprovider. undcontinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue) als zusätzliche Überprüfung auf potenziell gefährliche System Änderungen abrufen.

## <a name="attaching-dynamic-parameters-to-the-move-item-cmdlet"></a>Anfügen dynamischer Parameter an das Cmdlet "Move-Item"

Manchmal `Move-Item` benötigt das Cmdlet zusätzliche Parameter, die zur Laufzeit dynamisch bereitgestellt werden. Um diese dynamischen Parameter bereitzustellen, muss der Navigations Anbieter das [System implementieren. Management. Automation. Provider. navigationcmdletprovider. muveitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) -Methode, um die erforderlichen Parameterwerte aus dem Element im angezeigten Pfad abzurufen, und gibt ein Objekt zurück, das über Eigenschaften und Felder mit Eigenschaften und Feldern mit ähnlichen Attributen wie einer Cmdlet-Klasse oder einem [System. Management. Automation. runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary) -Objekt verfügt

Diese Methode wird von diesem Navigations Anbieter nicht implementiert. Der folgende Code ist jedoch die Standard Implementierung von [System. Management. Automation. Provider. navigationcmdletprovider. muveitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters).

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters](Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters)]  -->

## <a name="normalizing-a-relative-path"></a>Normalisieren eines relativen Pfads

Der Navigations Anbieter implementiert die [System. Management. Automation. Provider. navigationcmdletprovider. normalizerelativepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) -Methode, um den voll qualifizierten Pfad zu normalisieren, der im- `path` Parameter als relativ zu dem durch den-Parameter angegebenen Pfad angegeben ist `basePath` . Die-Methode gibt eine Zeichen folgen Darstellung des normalisierten Pfads zurück. Es wird ein Fehler geschrieben, wenn der- `path` Parameter einen nicht vorhandenen Pfad angibt.

Der Beispiel-Navigations Anbieter setzt diese Methode nicht außer Kraft. Im folgenden finden Sie die Standard Implementierung.

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernormalizepath](Msh_samplestestcmdlets#testprovidernormalizepath)]  -->

#### <a name="things-to-remember-about-implementing-normalizerelativepath"></a>Dinge, die Sie beim Implementieren von normalizerelativepath beachten sollten

Die Implementierung von [System. Management. Automation. Provider. navigationcmdletprovider. normalizerelativepath *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) sollte den- `path` Parameter analysieren, er muss jedoch nicht die reine syntaktische Analyse verwenden. Es wird empfohlen, diese Methode so zu entwerfen, dass Sie den Pfad verwendet, um die Pfadinformationen im Datenspeicher zu suchen und einen Pfad zu erstellen, der mit der Syntax für Groß-und Kleinschreibung übereinstimmt.

## <a name="code-sample"></a>Codebeispiel

Einen umfassenden Beispielcode finden Sie unter [AccessDbProviderSample05-Codebeispiel](./accessdbprovidersample05-code-sample.md).

## <a name="defining-object-types-and-formatting"></a>Definieren von Objekttypen und Formatierung

Es ist möglich, dass ein Anbieter vorhandenen Objekten Elemente hinzufügt oder neue Objekte definiert. Weitere Informationen finden Sie unter[Erweitern von Objekttypen und Formatierung](/previous-versions/ms714665(v=vs.85)).

## <a name="building-the-windows-powershell-provider"></a>Entwickeln des Windows PowerShell-Anbieters

Weitere Informationen finden Sie unter [Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions/ms714644(v=vs.85)).

## <a name="testing-the-windows-powershell-provider"></a>Testen des Windows PowerShell-Anbieters

Wenn Ihr Windows PowerShell-Anbieter bei Windows PowerShell registriert wurde, können Sie ihn testen, indem Sie die unterstützten Cmdlets in der Befehlszeile ausführen, einschließlich der von der Ableitung bereitgestellten Cmdlets. In diesem Beispiel wird der Beispiel-Navigations Anbieter getestet.

1. Führen Sie die neue Shell aus, und verwenden Sie das `Set-Location` Cmdlet, um den Pfad zum Angeben der Access-Datenbank festzulegen.

   ```powershell
   Set-Location mydb:
   ```

2. Führen Sie nun das `Get-Childitem` Cmdlet aus, um eine Liste der Datenbankelemente abzurufen, die die verfügbaren Datenbanktabellen sind. Für jede Tabelle ruft dieses Cmdlet auch die Anzahl der Tabellenzeilen ab.

   ```powershell
   Get-ChildItem | Format-Table rowcount,name -AutoSize
   ```

   ```Output
   RowCount   Name
   --------   ----
        180   MSysAccessObjects
          0   MSysACEs
          1   MSysCmdbars
          0   MSysIMEXColumns
          0   MSysIMEXSpecs
          0   MSysObjects
          0   MSysQueries
          7   MSysRelationships
          8   Categories
         91   Customers
          9   Employees
       2155   Order Details
        830   Orders
         77   Products
          3   Shippers
         29   Suppliers
   ```

3. Verwenden `Set-Location` Sie das Cmdlet erneut, um den Speicherort der Datentabelle Employees festzulegen.

   ```powershell
   Set-Location Employees
   ```

4. Nun verwenden wir das `Get-Location` Cmdlet, um den Pfad zur Tabelle Employees abzurufen.

   ```powershell
   Get-Location
   ```

   ```Output
   Path
   ----
   mydb:\Employees
   ```

5. Verwenden Sie nun das `Get-Childitem` Cmdlet an das `Format-Table` Cmdlet weitergeleitet. Mit diesem Cmdlet werden die Elemente für die Datentabelle "Employees" abgerufen, bei der es sich um die Tabellenzeilen handelt. Sie sind entsprechend der Angabe durch das- `Format-Table` Cmdlet formatiert.

   ```powershell
   Get-ChildItem | Format-Table rownumber,psiscontainer,data -AutoSize
   ```

   ```Output
   RowNumber   PSIsContainer   Data
   ---------   --------------   ----
   0           False            System.Data.DataRow
   1           False            System.Data.DataRow
   2           False            System.Data.DataRow
   3           False            System.Data.DataRow
   4           False            System.Data.DataRow
   5           False            System.Data.DataRow
   6           False            System.Data.DataRow
   7           False            System.Data.DataRow
   8           False            System.Data.DataRow
   ```

6. Sie können nun das `Get-Item` Cmdlet ausführen, um die Elemente für Zeile 0 der Tabelle Employees-Daten abzurufen.

   ```powershell
   Get-Item 0
   ```

   ```Output
   PSPath        : AccessDB::C:\PS\Northwind.mdb\Employees\0
   PSParentPath  : AccessDB::C:\PS\Northwind.mdb\Employees
   PSChildName   : 0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data           : System.Data.DataRow
   RowNumber      : 0
   ```

7. Verwenden `Get-Item` Sie das Cmdlet erneut, um die Mitarbeiterdaten für die Elemente in Zeile 0 abzurufen.

   ```powershell
   (Get-Item 0).data
   ```

   ```Output
   EmployeeID      : 1
   LastName        : Davis
   FirstName       : Sara
   Title           : Sales Representative
   TitleOfCourtesy : Ms.
   BirthDate       : 12/8/1968 12:00:00 AM
   HireDate        : 5/1/1992 12:00:00 AM
   Address         : 4567 Main Street
                     Apt. 2A
   City            : Buffalo
   Region          : NY
   PostalCode      : 98052
   Country         : USA
   HomePhone       : (206) 555-9857
   Extension       : 5467
   Photo           : EmpID1.bmp
   Notes           : Education includes a BA in psychology from
                     Colorado State University. She also completed "The
                     Art of the Cold Call."  Nancy is a member of
                     Toastmasters International.
   ReportsTo       : 2
   ```

## <a name="see-also"></a>Weitere Informationen

[Erstellen von Windows PowerShell-Anbietern](./how-to-create-a-windows-powershell-provider.md)

[Entwerfen Ihres Windows PowerShell-Anbieters](./designing-your-windows-powershell-provider.md)

[Erweitern von Objekttypen und Formatierung](/previous-versions/ms714665(v=vs.85))

[Implementieren eines Windows PowerShell-Anbieters für Container](./creating-a-windows-powershell-container-provider.md)

[Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions/ms714644(v=vs.85))

[Windows PowerShell-Programmiererhandbuch](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
