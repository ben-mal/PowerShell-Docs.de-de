---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-member?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Member
ms.openlocfilehash: 833be15e4018a0c25b0f604b5c84ab077c584cae
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213084"
---
# Get-Member

## ZUSAMMENFASSUNG
Ruft die Eigenschaften und Methoden der Objekte ab.

## SYNTAX

```
Get-Member [-InputObject <PSObject>] [[-Name] <String[]>] [-MemberType <PSMemberTypes>]
 [-View <PSMemberViewTypes>] [-Static] [-Force] [<CommonParameters>]
```

## DESCRIPTION

`Get-Member`Mit dem-Cmdlet werden die Elemente, die Eigenschaften und Methoden von Objekten abgerufen.

Um das Objekt anzugeben, verwenden Sie den **Inputobject** -Parameter, oder übergeben Sie ein Objekt an `Get-Member` . Um Informationen zu statischen Membern zu erhalten, verwenden die Member der-Klasse und nicht die-Instanz den **static** -Parameter. Um nur bestimmte Typen von Membern (z. b. **noteproperties** ) zu erhalten, verwenden Sie den Parameter " **Membership Type** ".

## BEISPIELE

### Beispiel 1: erhalten der Member von Process-Objekten

Dieser Befehl zeigt die Eigenschaften und Methoden der Dienst Objekte an, die vom `Get-Service` Cmdlet generiert werden.

Da der- `Get-Member` Teil des Befehls keine Parameter enthält, werden für die Parameter Standardwerte verwendet. Standardmäßig werden von keine statischen oder systeminternen Member `Get-Member` erhalten.

```powershell
Get-Service | Get-Member
```

```Output
   TypeName: System.Service.ServiceController#StartupType

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, System.EventArgs)
Close                     Method        void Close()
Continue                  Method        void Continue()
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
ExecuteCommand            Method        void ExecuteCommand(int command)
GetHashCode               Method        int GetHashCode()
GetLifetimeService        Method        System.Object GetLifetimeService()
GetType                   Method        type GetType()
InitializeLifetimeService Method        System.Object InitializeLifetimeService()
Pause                     Method        void Pause()
Refresh                   Method        void Refresh()
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.ServiceControllerSt...
BinaryPathName            Property      System.String {get;set;}
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DelayedAutoStart          Property      System.Boolean {get;set;}
DependentServices         Property      System.ServiceProcess.ServiceController[] DependentServices {get;}
Description               Property      System.String {get;set;}
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle ServiceHandle {get;}
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] ServicesDependedOn {get;}
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType {get;}
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartType {get;}
StartupType               Property      Microsoft.PowerShell.Commands.ServiceStartupType {get;set;}
Status                    Property      System.ServiceProcess.ServiceControllerStatus Status {get;}
UserName                  Property      System.String {get;set;}
ToString                  ScriptMethod  System.Object ToString();
```

### Beispiel 2: erhalten von Mitgliedern von Dienst Objekten

In diesem Beispiel werden alle Member (Eigenschaften und Methoden) der Dienst Objekte abgerufen, die vom `Get-Service` Cmdlet abgerufen werden, einschließlich der systeminternen Member (z. b. **PSBase** , **psobject** ) und der Methoden **get_** und **set_** .

```powershell
Get-Service | Get-Member -Force
(Get-Service Schedule).PSBase
```

Der `Get-Member` Befehl verwendet den **Force** -Parameter, um die systeminternen Member und vom Compiler generierten Member der Objekte der Anzeige hinzuzufügen. Sie können diese Eigenschaften und Methoden auf die gleiche Weise verwenden wie eine angepasste Methode des Objekts. Der zweite Befehl veranschaulicht, wie Sie den Wert der PSBase-Eigenschaft des Zeitplandiensts anzeigen können.

### Beispiel 3: erhalten erweiterter Member von Dienst Objekten

In diesem Beispiel werden die Methoden und Eigenschaften von Dienst Objekten abgerufen, die mit einer- `Types.ps1xml` Datei oder dem- `Add-Member` Cmdlet erweitert wurden.

```powershell
Get-Service | Get-Member -View Extended
```

```Output
   TypeName: System.Service.ServiceController#StartupType

Name             MemberType    Definition
----             ----------    ----------
Name             AliasProperty Name = ServiceName
RequiredServices AliasProperty RequiredServices = ServicesDependedOn
ToString         ScriptMethod  System.Object ToString();
```

Der `Get-Member` Befehl verwendet den **View** -Parameter, um nur die erweiterten Member der Dienst Objekte zu erhalten. In diesem Fall ist der Erweiterte Member die **Name** -Eigenschaft, bei der es sich um eine Alias Eigenschaft der **Service Name** -Eigenschaft handelt.

### Beispiel 4: erhalten von Skript Eigenschaften von Ereignisprotokoll Objekten

In diesem Beispiel werden die Skript Eigenschaften von Ereignisprotokoll Objekten im System Protokoll in Ereignisanzeige abgerufen.

```powershell
Get-WinEvent -LogName System -MaxEvents 1 | Get-Member -MemberType NoteProperty
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.EventLogRecord

Name    MemberType   Definition
----    ----------   ----------
Message NoteProperty string Message=The machine-default permission settings do not grant Local ...
```

Der **Membership Type** -Parameter ruft nur Objekte mit dem Wert `NoteProperty` für die Eigenschaft des **Mitgliedschafts Typs** ab.

Der Befehl gibt die **Message** -Eigenschaft des **EventLogRecord** -Objekts zurück.

### Beispiel 5: erhalten von Objekten mit einer angegebenen Eigenschaft

In diesem Beispiel werden Objekte mit einer **MachineName** -Eigenschaft in der Ausgabe aus einer Liste von Cmdlets abgerufen.

Die- `$list` Variable enthält eine Liste von Cmdlets, die ausgewertet werden sollen. Die **foreach** -Anweisung ruft jeden Befehl auf und sendet die Ergebnisse an `Get-Member` . Mit dem **Name** -Parameter werden die Ergebnisse von `Get-Member` auf Member mit dem Namen " **MachineName** " eingeschränkt.

```powershell
$list = "Get-Process", "Get-Service", "Get-Culture", "Get-PSDrive", "Get-ExecutionPolicy"
foreach ($cmdlet in $list) {& $cmdlet | Get-Member -Name MachineName}
```

```Output
   TypeName: System.Diagnostics.Process

Name        MemberType Definition
----        ---------- ----------
MachineName Property   string MachineName {get;}

   TypeName: System.Service.ServiceController#StartupType

Name        MemberType Definition
----        ---------- ----------
MachineName Property   string MachineName {get;set;}
```

Die Ergebnisse zeigen, dass nur Prozess Objekte und Dienst Objekte über eine **MachineName** -Eigenschaft verfügen.

### Beispiel 6: erhalten von Membern für ein Array

In diesem Beispiel wird veranschaulicht, wie die Member eines Arrays von-Objekten gefunden werden. Wenn Sie die Pipeline und das Array von Objekten an übergeben `Get-Member` , gibt das Cmdlet eine Elementliste für jeden eindeutigen Objekttyp im Array zurück.
Wenn Sie das Array mithilfe des **Inputobject** -Parameters übergeben, wird das Array als einzelnes Objekt behandelt.

```powershell
$array = @(1,'hello')
$array | Get-Member
```

```Output
   TypeName: System.Int32

Name        MemberType Definition
----        ---------- ----------
CompareTo   Method     int CompareTo(System.Object value), int CompareTo(int value), int ICompar...
Equals      Method     bool Equals(System.Object obj), bool Equals(int obj), bool IEquatable[int...
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
GetTypeCode Method     System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean   Method     bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte      Method     byte IConvertible.ToByte(System.IFormatProvider provider)
...

   TypeName: System.String

Name                 MemberType            Definition
----                 ----------            ----------
Clone                Method                System.Object Clone(), System.Object ICloneable.Clone()
CompareTo            Method                int CompareTo(System.Object value), int CompareTo(str...
Contains             Method                bool Contains(string value), bool Contains(string val...
CopyTo               Method                void CopyTo(int sourceIndex, char[] destination, int ...
EndsWith             Method                bool EndsWith(string value), bool EndsWith(string val...
EnumerateRunes       Method                System.Text.StringRuneEnumerator EnumerateRunes()
Equals               Method                bool Equals(System.Object obj), bool Equals(string va...
GetEnumerator        Method                System.CharEnumerator GetEnumerator(), System.Collect...
GetHashCode          Method                int GetHashCode(), int GetHashCode(System.StringCompa...
...
```

```powershell
Get-Member -InputObject $array
```

```Output
   TypeName: System.Object[]

Name           MemberType            Definition
----           ----------            ----------
Add            Method                int IList.Add(System.Object value)
Address        Method                System.Object&, System.Private.CoreLib, Version=4.0.0.0, Cu...
Clear          Method                void IList.Clear()
Clone          Method                System.Object Clone(), System.Object ICloneable.Clone()
CompareTo      Method                int IStructuralComparable.CompareTo(System.Object other, Sy...
...
```

Die `$array` -Variable enthält ein **Int32** -Objekt und ein **String** -Objekt, das angezeigt wird, wenn das Array an die Pipeline übergeben wird `Get-Member` . Wenn `$array` mithilfe des **Inputobject** -Parameters übergeben wird, `Get-Member` gibt die Member des **Object []** -Typs zurück.

### Beispiel 7: Bestimmen der festzulegenden Objekteigenschaften

Dieses Beispiel zeigt, wie Sie bestimmen können, welche Eigenschaften eines Objekts geändert werden können.

```powershell
$File = Get-Item c:\test\textFile.txt
$File.PSObject.Properties | Where-Object isSettable | Select-Object -Property Name
```

```Output
Name
----
PSPath
PSParentPath
PSChildName
PSDrive
PSProvider
PSIsContainer
IsReadOnly
CreationTime
CreationTimeUtc
LastAccessTime
LastAccessTimeUtc
LastWriteTime
LastWriteTimeUtc
Attributes
```

## PARAMETERS

### -Force

Fügt die systeminternen Member und die vom Compiler generierten **get_** und **set_** Methoden der Anzeige hinzu.
In der folgenden Liste werden die Eigenschaften beschrieben, die hinzugefügt werden, wenn Sie den **Force** -Parameter verwenden:

- **PSBase** : die ursprünglichen Eigenschaften des .NET-Objekts ohne Erweiterung oder Anpassung. Dabei handelt es sich um die für die Objektklasse definierten Eigenschaften.
- **Psangepasste** . Die Eigenschaften und Methoden, die im erweiterten PowerShell-Typsystem definiert sind.
- **Psexgepflegt** . Die Eigenschaften und Methoden, die in den `Types.ps1xml` Dateien oder mithilfe des- `Add-Member` Cmdlets hinzugefügt wurden.
- **Psobject** . Der Adapter, der das Basisobjekt in ein PowerShell- **psobject** -Objekt konvertiert.
- **Pstypames** . Eine Liste der Objekttypen, die das Objekt nach Genauigkeit beschreiben. Bei der Formatierung des Objekts sucht PowerShell nach den Typen in den `Format.ps1xml` Dateien im PowerShell-Installationsverzeichnis ( `$PSHOME` ). Dabei wird die Formatierungsdefinition für den ersten gefundenen Typ verwendet.

Standardmäßig `Get-Member` ruft diese Eigenschaften in allen Ansichten ab, mit Ausnahme von " **Base** " und " **angepasst** ", zeigt Sie jedoch nicht an.

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

### -InputObject

Gibt das Objekt an, dessen Member abgerufen werden.

Die Verwendung des **Inputobject** -Parameters ist nicht identisch mit dem Übergeben eines Objekts an `Get-Member` . Es gibt die folgenden Unterschiede:

- Wenn Sie eine Auflistung von-Objekten an übergeben `Get-Member` , ruft `Get-Member` die Member der einzelnen Objekte in der Auflistung ab, z. b. die Eigenschaften der einzelnen Zeichen folgen in einem Array von Zeichen folgen.
- Wenn Sie **Inputobject** verwenden, um eine Auflistung von Objekten zu senden, ruft `Get-Member` die Member der Auflistung ab, z. b. die Eigenschaften des Arrays in einem Zeichen folgen Array.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Mitgliedstyp

Gibt den Elementtyp an, der von diesem Cmdlet abgerufen wird. Die Standardeinstellung ist **Alle** .

Zulässige Werte für diesen Parameter:

- AliasProperty
- CodeProperty
- Eigenschaft
- NoteProperty
- ScriptProperty
- Eigenschaften
- PropertySet
- Methode
- CodeMethod
- ScriptMethod
- Methoden
- ParameterizedProperty
- MemberSet
- Ereignis
- Dynamisch
- Alle

Weitere Informationen zu diesen Werten finden Sie unter [psmembership types-Enumeration](/dotnet/api/system.management.automation.psmembertypes).

Nicht alle Objekte verfügen über jeden Membertyp. Wenn Sie einen Elementtyp angeben, der für das Objekt nicht vorhanden ist, gibt PowerShell einen NULL-Wert zurück.

Um verwandte Membertypen, wie z. B. alle erweiterten Member abzurufen, verwenden Sie den **View** -Parameter. Wenn Sie den Parameter " **Membership Type** " mit den Parametern " **static** " oder " **View** " verwenden, ruft die Member ab, die `Get-Member` zu beiden Sätzen gehören.

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt die Namen von mindestens einer Eigenschaft oder Methode des Objekts an. `Get-Member` Ruft nur die angegebenen Eigenschaften und Methoden ab.

Wenn Sie den Parameter " **Name** " mit dem Parameter " **Membership Type** ", " **View** " oder " **static** " verwenden, ruft nur die Member ab, die `Get-Member` die Kriterien aller Parameter erfüllen.

Um einen statischen Member nach Namen zu erhalten, verwenden Sie den **static** -Parameter mit dem **Name** -Parameter.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Static

Gibt an, dass dieses Cmdlet nur die statischen Eigenschaften und Methoden des-Objekts abruft. Statische Eigenschaften und Methoden werden für die Klasse von Objekten, nicht für eine bestimmte Instanz der Klasse definiert.

Wenn Sie den **static** -Parameter mit dem **View** -Parameter verwenden, wird der **View** -Parameter ignoriert.
Wenn Sie den **static** -Parameter mit dem **Membership Type** -Parameter verwenden, ruft nur die Member ab, die `Get-Member` zu beiden Sätzen gehören.

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

### -Ansicht

Gibt an, dass dieses Cmdlet nur bestimmte Typen Eigenschaften und Methoden abruft. Geben Sie mindestens einen der Werte an. Der Standardwert ist **angepasst** , **erweitert** .

Zulässige Werte für diesen Parameter:

- Basis. Ruft nur die ursprünglichen Eigenschaften und Methoden des .NET-Objekts (ohne Erweiterung oder Anpassung) ab.
- Speziell. Ruft nur die Eigenschaften und Methoden ab, die im erweiterten PowerShell-Typsystem definiert sind.
- Verlängert. Ruft nur die Eigenschaften und Methoden ab, die in einer `Types.ps1xml` Datei oder mithilfe des `Add-Member` Cmdlets hinzugefügt wurden.
- Alle Ruft die Member in den Ansichten „Base“, „Adapted“ und „Extended“ ab.

Der **View** -Parameter bestimmt die abgerufenen Member, nicht nur die Anzeige dieser Member.

Um bestimmte Elementtypen, z. b. Skript Eigenschaften, zu erhalten, verwenden Sie den Parameter " **Membership Type** ". Wenn Sie die Parameter " **Membership Type** " und " **View** " im selben Befehl verwenden, ruft die Member ab, die `Get-Member` zu beiden Sätzen gehören. Wenn Sie den **statischen** Parameter und den **View** -Parameter im gleichen Befehl verwenden, wird der **View** -Parameter ignoriert.

```yaml
Type: System.Management.Automation.PSMemberViewTypes
Parameter Sets: (All)
Aliases:
Accepted values: Extended, Adapted, Base, All

Required: False
Position: Named
Default value: Adapted, Extended
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt an die Pipeline übergeben `Get-Member` .

## AUSGABEN

### Microsoft. PowerShell. Commands. Membership Definition

`Get-Member` Gibt ein-Objekt für jede Eigenschaft oder Methode zurück, die von ihr abgerufen wird.

## HINWEISE

Sie können Informationen zu einem Auflistungs Objekt entweder mithilfe des **Inputobject** -Parameters oder durch Weiterleiten des Objekts, dem ein Komma vorangestellt ist, zu erhalten `Get-Member` .

Sie können die `$This` Automatische Variable in Skript Blöcken verwenden, die die Werte der neuen Eigenschaften und Methoden definieren. Die- `$This` Variable verweist auf die Instanz des Objekts, dem die Eigenschaften und Methoden hinzugefügt werden. Weitere Informationen zur- `$This` Variablen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

Wenn Sie ein Objekt übergeben, das einen _Typ_ darstellt, wie z. b. einen typliterals `[int]` , geben Sie `Get-Member` Informationen über den `[System.RuntimeType]` Typ zurück. Wenn Sie jedoch den **static** -Parameter verwenden, `Get-Member` gibt die statischen Member des angegebenen Typs zurück, der durch die-Instanz dargestellt wird `System.RuntimeType` .

## VERWANDTE LINKS

[Add-Member](Add-Member.md)

