---
description: Erläutert `Types.ps1xml` die Verwendung von Dateien zum Erweitern der Objekttypen, die in PowerShell verwendet werden.
Locale: en-US
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_types.ps1xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Types.ps1xml
ms.openlocfilehash: 9a87394631d3318f3fb3f4b2a0cb2ab8d25408d0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600489"
---
# <a name="about-typesps1xml"></a>Informationen zu Types.ps1XML

## <a name="short-description"></a>Kurze Beschreibung
Erläutert `Types.ps1xml` die Verwendung von Dateien zum Erweitern der Objekttypen, die in PowerShell verwendet werden.

## <a name="long-description"></a>Lange Beschreibung

Erweiterte Typdaten definieren zusätzliche Eigenschaften und Methoden ("Member") von Objekttypen in PowerShell. Es gibt zwei Verfahren zum Hinzufügen von erweiterten Typdaten zu einer PowerShell-Sitzung.

- `Types.ps1xml` file: eine XML-Datei, die erweiterte Typdaten definiert.
- `Update-TypeData`: Ein Cmdlet, das Dateien erneut lädt `Types.ps1xml` und erweiterte Daten für Typen in der aktuellen Sitzung definiert.

In diesem Thema werden- `Types.ps1xml` Dateien beschrieben. Weitere Informationen zur Verwendung des `Update-TypeData` Cmdlets, um der aktuellen Sitzung dynamische erweiterte Typdaten hinzuzufügen, finden Sie unter [Update-typedata](xref:Microsoft.PowerShell.Utility.Update-TypeData).

## <a name="about-extended-type-data"></a>Informationen zu erweiterten Typdaten

Erweiterte Typdaten definieren zusätzliche Eigenschaften und Methoden ("Member") von Objekttypen in PowerShell. Sie können jeden von PowerShell unterstützten Typ erweitern und die hinzugefügten Eigenschaften und Methoden auf die gleiche Weise verwenden, wie Sie die Eigenschaften verwenden, die für die Objekttypen definiert sind.

Beispielsweise fügt PowerShell allen  `System.DateTime` Objekten, wie z. b. den vom Cmdlet zurückgegebenen Objekten, eine DateTime-Eigenschaft hinzu `Get-Date` .

```powershell
(Get-Date).DateTime
```

```Output
Sunday, January 29, 2012 9:43:57 AM
```

Die **DateTime** -Eigenschaft wird in der Beschreibung der [System. DateTime](/dotnet/api/system.datetime) -Struktur nicht gefunden, da die Eigenschaft von PowerShell hinzugefügt wird und nur in PowerShell sichtbar ist.

PowerShell definiert intern einen Standardsatz erweiterter Typen. Diese Typinformationen werden beim Start in jede PowerShell-Sitzung geladen. Die **DateTime** -Eigenschaft ist Teil dieses Standardsatzes. Vor PowerShell 6 wurden die Typdefinitionen `Types.ps1xml` im PowerShell-Installationsverzeichnis ( `$PSHOME` ) gespeichert.

## <a name="adding-extended-type-data-to-powershell"></a>Hinzufügen von erweiterten Typdaten zu PowerShell

Es gibt drei Quellen für erweiterte Typdaten in PowerShell-Sitzungen.

- Der von PowerShell definierte und wird automatisch in jede PowerShell-Sitzung geladen. Ab PowerShell 6 werden diese Informationen in PowerShell kompiliert und sind nicht mehr in einer `Types.ps1xml` Datei enthalten.

- Die `Types.ps1xml` Dateien, die Module exportieren, werden geladen, wenn das Modul in die aktuelle Sitzung importiert wird.

- Erweiterte Typdaten, die mithilfe des-Cmdlets definiert werden, werden `Update-TypeData` nur zur aktuellen Sitzung hinzugefügt. Er wird nicht in einer Datei gespeichert.

In der Sitzung werden die erweiterten Typdaten aus den drei Quellen auf die gleiche Weise auf-Objekte angewendet und sind für alle Objekte der angegebenen Typen verfügbar.

## <a name="the-typedata-cmdlets"></a>Die typedata-Cmdlets

Die folgenden Cmdlets sind im **Microsoft. PowerShell. Utility** -Modul in PowerShell 3,0 und höher enthalten.

- `Get-TypeData`: Ruft erweiterte Typdaten in der aktuellen Sitzung ab.
- `Update-TypeData`: Lädt `Types.ps1xml` Dateien erneut. Fügt der aktuellen Sitzung erweiterte Typdaten hinzu.
- `Remove-TypeData`: Entfernt erweiterte Typdaten aus der aktuellen Sitzung.

Weitere Informationen zu diesen Cmdlets finden Sie im Hilfethema für jedes Cmdlet.

## <a name="built-in-typesps1xml-files"></a>Integrierte Types.ps1XML-Dateien

Die `Types.ps1xml` Dateien im `$PSHOME` Verzeichnis werden jeder Sitzung automatisch hinzugefügt.

`Types.ps1xml`Bei der Datei im PowerShell-Installationsverzeichnis ( `$PSHOME` ) handelt es sich um eine XML-basierte Textdatei, mit der Sie den Objekten, die in PowerShell verwendet werden, Eigenschaften und Methoden hinzufügen können. PowerShell verfügt über integrierte Dateien, die `Types.ps1xml` den .NET-Typen mehrere Elemente hinzufügen. Sie können jedoch zusätzliche `Types.ps1xml` Dateien erstellen, um die Typen weiter zu erweitern.

Standardmäßig verfügen Array Objekte ( `System.Array` ) z. b. über eine **length** -Eigenschaft, die die Anzahl der Objekte im Array auflistet. Da die Name- **Länge** die Eigenschaft jedoch nicht eindeutig beschreibt, fügt PowerShell eine Alias Eigenschaft mit dem Namen **count** hinzu, die denselben Wert anzeigt. Im folgenden XML-Code wird die **count** -Eigenschaft zum-Typ hinzugefügt `System.Array` .

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>
        Length
      </ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

Um die neue **aliasproperty** zu erhalten, verwenden Sie einen `Get-Member` Befehl für ein beliebiges Array, wie im folgenden Beispiel gezeigt.

```powershell
Get-Member -InputObject (1,2,3,4)
```

Der Befehl gibt die folgenden Ergebnisse zurück.

```Output
Name       MemberType    Definition
----       ----------    ----------
Count      AliasProperty Count = Length
Address    Method        System.Object& Address(Int32)
Clone      Method        System.Object Clone()
CopyTo     Method        System.Void CopyTo(Array array, Int32 index):
Equals     Method        System.Boolean Equals(Object obj)
Get        Method        System.Object Get(Int32)
# ...
```

Daher können Sie entweder die **count** -Eigenschaft oder die **length** -Eigenschaft von Arrays in PowerShell verwenden. Beispiel:

```powershell
(1, 2, 3, 4).count
4
```

```powershell
(1, 2, 3, 4).length
4
```

## <a name="creating-new-typesps1xml-files"></a>Erstellen neuer Types.ps1XML-Dateien

Die `.ps1xml` mit PowerShell installierten Dateien sind digital signiert, um Manipulationen zu verhindern, da die Formatierung Skriptblöcke einschließen kann. Wenn Sie also eine Eigenschaft oder Methode zu einem .NET-Typ hinzufügen möchten, erstellen Sie Ihre eigenen `Types.ps1xml` Dateien, und fügen Sie Sie dann der PowerShell-Sitzung hinzu.

Um eine neue Datei zu erstellen, kopieren Sie zunächst eine vorhandene `Types.ps1xml` Datei. Die neue Datei kann einen beliebigen Namen haben, Sie muss jedoch eine `.ps1xml` Dateinamenerweiterung aufweisen. Sie können die neue Datei in einem beliebigen Verzeichnis platzieren, auf das PowerShell zugreifen kann, aber es ist hilfreich, die Dateien im PowerShell-Installationsverzeichnis ( `$PSHOME` ) oder in einem Unterverzeichnis des Installationsverzeichnisses zu platzieren.

Wenn Sie die neue Datei gespeichert haben, verwenden Sie das `Update-TypeData` Cmdlet, um die neue Datei zur PowerShell-Sitzung hinzuzufügen. Wenn Sie möchten, dass Ihre Typen Vorrang vor den integrierten Typen haben, die definiert sind, verwenden Sie den **prepddata** -Parameter des `Update-TypeData` Cmdlets. `Update-TypeData` wirkt sich nur auf die aktuelle Sitzung aus. Um die Änderung an allen zukünftigen Sitzungen vorzunehmen, exportieren Sie die-Konsole, oder fügen Sie den `Update-TypeData` Befehl zu Ihrem PowerShell-Profil hinzu.

## <a name="typesps1xml-and-add-member"></a>Types.ps1XML und Add-Member

Die `Types.ps1xml` Dateien fügen Eigenschaften und Methoden zu allen Instanzen der Objekte des angegebenen .net-Typs in der betroffenen PowerShell-Sitzung hinzu. Wenn Sie jedoch nur einer Instanz eines Objekts Eigenschaften oder Methoden hinzufügen müssen, verwenden Sie das- `Add-Member` Cmdlet.

Weitere Informationen finden Sie unter [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).

## <a name="example-adding-an-age-member-to-fileinfo-objects"></a>Beispiel: Hinzufügen eines Age-Members zu filinput Info-Objekten

Dieses Beispiel zeigt, wie Sie **System. IO. filinput Info** -Objekten eine **Age** -Eigenschaft hinzufügen. Das Alter einer Datei ist der Unterschied zwischen der Erstellungszeit und der aktuellen Zeit (in Tagen).

Da die **Age** -Eigenschaft mit einem Skriptblock berechnet wird, suchen Sie `<ScriptProperty>` nach einem Tag, das als Modell für die neue **Age** -Eigenschaft verwendet werden soll.

Speichern Sie den folgenden XML-Code in der Datei `$PSHOME\MyTypes.ps1xml` .

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Types>
  <Type>
    <Name>System.IO.FileInfo</Name>
    <Members>
      <ScriptProperty>
        <Name>Age</Name>
        <GetScriptBlock>
          ((Get-Date) - ($this.CreationTime)).Days
        </GetScriptBlock>
      </ScriptProperty>
    </Members>
  </Type>
</Types>
```

Führen Sie aus `Update-TypeData` , um die neue `Types.ps1xml` Datei zur aktuellen Sitzung hinzuzufügen. Der Befehl verwendet den **prepddata** -Parameter, um die neue Datei in einer Rangfolge zu platzieren, die höher als die ursprünglichen Definitionen ist.

Weitere Informationen zu `Update-TypeData` finden Sie unter [Update-typedata](xref:Microsoft.PowerShell.Utility.Update-TypeData).

```powershell
Update-Typedata -PrependPath $PSHOME\MyTypes.ps1xml
```

Um die Änderung zu testen, führen Sie einen `Get-ChildItem` Befehl aus, um die PowerShell.exe-Datei im Verzeichnis zu erhalten `$PSHOME` , und übergeben Sie die Datei dann an das `Format-List` Cmdlet, um alle Eigenschaften der Datei aufzulisten. Aufgrund der Änderung wird die **Age** -Eigenschaft in der Liste angezeigt.

```powershell
Get-ChildItem $PSHOME\pwsh.exe | Select-Object Age
```

```Output
142
```

## <a name="the-xml-in-typesps1xml-files"></a>Der XML-Code in Types.ps1XML-Dateien

Die vollständige Schema Definition finden Sie in der Datei " [types. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) " im PowerShell-Quellcoderepository auf GitHub.

Das- `<Types>` Tag schließt alle Typen ein, die in der Datei definiert sind. Es darf nur ein Tag vorhanden sein `<Types>` .

Jeder in der Datei erwähnte .NET-Typ sollte durch ein- `<Type>` Tag dargestellt werden.

Die typtags müssen die folgenden Tags enthalten:

`<Name>`: Enschließt den Namen des betroffenen .net-Typs.

`<Members>`: Schließt die Tags für die neuen Eigenschaften und Methoden ein, die für den .NET-Typ definiert sind.

Jedes der folgenden Member-Tags kann sich im- `<Members>` Tag befinden.

`<AliasProperty>`: Definiert einen neuen Namen für eine vorhandene Eigenschaft.

Das `<AliasProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein `<ReferencedMemberName>` Tag angibt, das die vorhandene Eigenschaft angibt.

Beispielsweise ist die **count** -Alias Eigenschaft ein Alias für die **length** -Eigenschaft von Array-Objekten.

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

`<CodeMethod>`: Verweist auf eine statische Methode einer .NET-Klasse.

Das `<CodeMethod>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Methode und ein `<GetCodeReference>` Tag angibt, das den Code angibt, in dem die Methode definiert ist.

Beispielsweise ist die **Mode** -Eigenschaft von- `System.IO.DirectoryInfo` Objekten eine im PowerShell-Dateisystem Anbieter definierte Code Eigenschaft.

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

`<CodeProperty>`: Verweist auf eine statische Methode einer .NET-Klasse.

Das `<CodeProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein `<GetCodeReference>` Tag angibt, das den Code angibt, in dem die Eigenschaft definiert ist.

Beispielsweise ist die **Mode** -Eigenschaft von- `System.IO.DirectoryInfo` Objekten eine im PowerShell-Dateisystem Anbieter definierte Code Eigenschaft.

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

`<MemberSet>`: Definiert eine Auflistung von Membern (Eigenschaften und Methoden).

Die `<MemberSet>` Tags werden innerhalb der primären `<Members>` Tags angezeigt. Die Tags müssen ein Tag umschließen `<Name>` , das den Namen des Element Satzes umschließt, und ein sekundäres `<Members>` Tag, das die Elemente (Eigenschaften und Methoden) in der Menge umschließt. Alle Tags, die eine Eigenschaft (z. b. `<NoteProperty>` oder `<ScriptProperty>` ) oder eine Methode (z. b. `<Method>` oder) erstellen, `<ScriptMethod>` können Member der Menge sein.

In- `Types.ps1xml` Dateien wird das- `<MemberSet>` Tag verwendet, um die Standard Sichten der .NET-Objekte in PowerShell zu definieren. In diesem Fall ist der Name des Element Satzes (der Wert innerhalb der `<Name>` Tags) immer **psstandardmembers**, und die Namen der Eigenschaften (der Wert des `<Name>` Tags) sind eines der folgenden:

- `DefaultDisplayProperty`: Eine einzelne Eigenschaft eines Objekts.

- `DefaultDisplayPropertySet`: Eine oder mehrere Eigenschaften eines Objekts.

- `DefaultKeyPropertySet`: Eine oder mehrere Schlüsseleigenschaften eines Objekts. Eine Schlüsseleigenschaft identifiziert Instanzen von Eigenschafts Werten, z. b. die ID-Anzahl von Elementen in einem Sitzungsverlauf.

Der folgende XML-Code definiert z. b. die Standard Anzeige der Dienste (- `System.ServiceProcess.ServiceController` Objekte), die vom `Get-Service` Cmdlet zurückgegeben werden. Er definiert einen Member-Satz mit dem Namen " **psstandardmembers** ", der aus einem Standardeigenschaften Satz mit den Eigenschaften " **Status**", " **Name**" und " **Display Name** " besteht.

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

`<Method>`: Verweist auf eine native Methode des zugrunde liegenden-Objekts.

`<Methods>`: Eine Auflistung der Methoden des-Objekts.

`<NoteProperty>`: Definiert eine Eigenschaft mit einem statischen Wert.

Das `<NoteProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein `<Value>` Tag angibt, das den Wert der-Eigenschaft angibt.

Der folgende XML-Code erstellt z. b. eine **Status** Eigenschaft für **System. IO. directoriyinfo** -Objekte. Der Wert der **Status** -Eigenschaft lautet immer **erfolgreich**.

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

`<ParameterizedProperty>`: Eigenschaften, die Argumente annehmen und einen Wert zurückgeben.

`<Properties>`: Eine Auflistung der Eigenschaften des-Objekts.

`<Property>`: Eine Eigenschaft des Basis Objekts.

`<PropertySet>`: Definiert eine Auflistung von Eigenschaften des-Objekts.

Das `<PropertySet>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen des Eigenschaften Satzes und ein `<ReferencedProperty>` Tag angibt, das die Eigenschaften angibt. Die Namen der Eigenschaften werden in Tag eingeschlossen `<Name>` .

In `Types.ps1xml` `<PropertySet>` werden Tags verwendet, um Gruppen von Eigenschaften für die Standard Anzeige eines Objekts zu definieren. Sie können die Standard anzeigen durch den Wert **psstandardmembers** im `<Name>` Tag eines `<MemberSet>` Tags ermitteln.

Der folgende XML-Code erstellt beispielsweise eine **Status** -Eigenschaft für das- `System.IO.DirectoryInfo` Objekt. Der Wert der **Status** -Eigenschaft lautet immer **erfolgreich**.

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

`<ScriptMethod>`: Definiert eine Methode, deren Wert die Ausgabe eines Skripts ist.

Das `<ScriptMethod>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Methode und ein `<Script>` Tag, das den Skriptblock einschließt, der das Methoden Ergebnis zurückgibt, angibt.

Die `ConvertToDateTime` -Methode und die- `ConvertFromDateTime` Methode von Management Objects () sind z. b `System.System.Management.ManagementObject` . Skript Methoden, die die `ToDateTime` statischen Methoden und der- `ToDmtfDateTime` Klasse verwenden `System.Management.ManagementDateTimeConverter` .

```xml
<Type>
 <Name>System.Management.ManagementObject</Name>
 <Members>
 <ScriptMethod>
   <Name>ConvertToDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
   </Script>
 </ScriptMethod>
 <ScriptMethod>
   <Name>ConvertFromDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDmtfDateTime($args[0])
   </Script>
 </ScriptMethod>
 </Members>
</Type>
```

`<ScriptProperty>`: Definiert eine Eigenschaft, deren Wert die Ausgabe eines Skripts ist.

Das `<ScriptProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein Tag angibt, das `<GetScriptBlock>` den Skriptblock einschließt, der den Eigenschafts Wert zurückgibt.

Beispielsweise ist die **VERSIONINFO** -Eigenschaft des **System. IO. FileInfo** -Objekts eine Skript Eigenschaft, die sich aus der Verwendung der **FullName** -Eigenschaft der statischen **GetVersionInfo** -Methode der **System. Diagnostics. FileVersionInfo** -Objekte ergibt.

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
      [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

Weitere Informationen finden Sie im [Windows PowerShell Software Development Kit (SDK)](/powershell/scripting/developer/windows-powershell).

## <a name="update-typedata"></a>Update-TypeData

`Types.ps1xml`Führen Sie das-Cmdlet aus, um die Dateien in eine PowerShell-Sitzung zu laden `Update-TypeData` . Wenn Sie möchten, dass die Typen in der Datei Vorrang vor Typen in der integrierten `Types.ps1xml` Datei haben, fügen Sie den **prepddata** -Parameter von hinzu `Update-TypeData` . `Update-TypeData` wirkt sich nur auf die aktuelle Sitzung aus. Um die Änderung an allen zukünftigen Sitzungen vorzunehmen, exportieren Sie die Sitzung, oder fügen Sie den `Update-TypeData` Befehl zu Ihrem PowerShell-Profil hinzu.

Ausnahmen, die in Eigenschaften auftreten, oder das Hinzufügen von Eigenschaften zu einem `Update-TypeData` Befehl, melden keine Fehler an `StdErr` . Dadurch werden Ausnahmen unterdrückt, die während der Formatierung und Ausgabe in vielen gängigen Typen auftreten würden. Wenn Sie .net-Eigenschaften erhalten, können Sie die Unterdrückung von Ausnahmen umgehen, indem Sie stattdessen die Methoden Syntax verwenden, wie im folgenden Beispiel gezeigt:

```powershell
"hello".get_Length()
```

Beachten Sie, dass die Methoden Syntax nur mit .net-Eigenschaften verwendet werden kann. Eigenschaften, die durch das Ausführen des `Update-TypeData` Cmdlets hinzugefügt werden, können keine Methoden Syntax verwenden.

## <a name="signing-a-typesps1xml-file"></a>Signieren einer Types.ps1-XML-Datei

Um Benutzer Ihrer Datei zu schützen `Types.ps1xml` , können Sie die Datei mit einer digitalen Signatur signieren. Weitere Informationen finden Sie unter [about_Signing](about_Signing.md).

## <a name="see-also"></a>Weitere Informationen

[about_Signing](about_Signing.md)

[Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item)

[Copy-ItemProperty](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)

[Get-TypeData](xref:Microsoft.PowerShell.Utility.Get-TypeData)

[Remove-TypeData](xref:Microsoft.PowerShell.Utility.Remove-TypeData)

[Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData)

