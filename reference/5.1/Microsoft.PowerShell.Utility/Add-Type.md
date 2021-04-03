---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: e6fa1d63f2c748c590920db0cbfdf241e0646a73
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2021
ms.locfileid: "106274254"
---
# Add-Type

## ZUSAMMENFASSUNG
Fügt einer PowerShell-Sitzung eine Microsoft .NET Klasse hinzu.

## SYNTAX

### Fromsource (Standard)

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [<CommonParameters>]
```

### Frommember

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>] [-UsingNamespace <String[]>]
 [-Language <Language>] [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### Frompath

```
Add-Type [-CompilerParameters <CompilerParameters>] [-Path] <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### Fromliteralpath

```
Add-Type [-CompilerParameters <CompilerParameters>] -LiteralPath <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### Fromassemblyname

```
Add-Type -AssemblyName <String[]> [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Add-Type` Cmdlet können Sie in ihrer PowerShell-Sitzung eine Microsoft .NET Framework-Klasse definieren.
Anschließend können Sie Objekte mit dem `New-Object` Cmdlet instanziieren und die Objekte wie jedes beliebige .NET Framework Objekt verwenden. Wenn Sie `Add-Type` Ihrem PowerShell-Profil einen Befehl hinzufügen, ist die Klasse in allen PowerShell-Sitzungen verfügbar.

Sie können den Typ angeben, indem Sie eine vorhandene Assembly oder Quellcodedateien angeben, oder Sie können den Quellcode inline oder in einer Variablen gespeichert angeben. Sie können sogar nur eine-Methode angeben und `Add-Type` die-Klasse definieren und generieren. Unter Windows können Sie diese Funktion verwenden, um Platt Form Aufrufe (P/aufrufen) von nicht verwalteten Funktionen in PowerShell durchführen. Wenn Sie Quellcode angeben, `Add-Type` kompiliert den angegebenen Quellcode und generiert eine in-Memory-Assembly, die die neuen .NET Framework Typen enthält.

Sie können die Parameter von verwenden, `Add-Type` um eine alternative Sprache und einen anderen Compiler anzugeben, c# ist die Standardeinstellung, Compileroptionen, Assemblyabhängigkeiten, den Klassen Namespace, die Namen des Typs und die resultierende Assembly.

## BEISPIELE

### Beispiel 1: Hinzufügen eines .net-Typs zu einer Sitzung

In diesem Beispiel wird die **basictest** -Klasse der Sitzung hinzugefügt, indem Quellcode angegeben wird, der in einer Variablen gespeichert ist. Die **basictest** -Klasse wird verwendet, um ganze Zahlen hinzuzufügen, ein Objekt zu erstellen und ganze Zahlen zu multiplizieren.

```powershell
$Source = @"
public class BasicTest
{
  public static int Add(int a, int b)
    {
        return (a + b);
    }
  public int Multiply(int a, int b)
    {
    return (a * b);
    }
}
"@

Add-Type -TypeDefinition $Source
[BasicTest]::Add(4, 3)
$BasicTestObject = New-Object BasicTest
$BasicTestObject.Multiply(5, 2)
```

Die- `$Source` Variable speichert den Quellcode für die-Klasse. Der-Typ verfügt über eine statische Methode mit dem Namen `Add` und eine nicht statische Methode mit dem Namen `Multiply` .

Mit dem- `Add-Type` Cmdlet wird die-Klasse der Sitzung hinzugefügt. Da es Inline Quellcode verwendet, verwendet der Befehl den **typeDefinition** -Parameter, um den Code in der `$Source` Variablen anzugeben.

Die `Add` statische-Methode der **basictest** -Klasse verwendet die doppelten Doppelpunkte ( `::` ), um einen statischen Member der-Klasse anzugeben. Die ganzen Zahlen werden hinzugefügt, und die Summe wird angezeigt.

Das- `New-Object` Cmdlet instanziiert eine Instanz der **basictest** -Klasse. Das neue Objekt wird in der `$BasicTestObject` Variablen gespeichert.

`$BasicTestObject` verwendet die- `Multiply` Methode. Die ganzen Zahlen werden multipliziert, und das Produkt wird angezeigt.

### Beispiel 2: Untersuchen eines hinzugefügten Typs

In diesem Beispiel wird das `Get-Member` -Cmdlet verwendet, um die Objekte zu überprüfen, die `Add-Type` `New-Object` in **Beispiel 1** erstellt wurden.

```powershell
[BasicTest] | Get-Member
```

```Output
   TypeName: System.RuntimeType

Name                 MemberType Definition
----                 ---------- ----------
AsType               Method     type AsType()
Clone                Method     System.Object Clone(), System.Object ICloneable.Clone()
Equals               Method     bool Equals(System.Object obj), bool Equals(type o)
FindInterfaces       Method     type[] FindInterfaces(System.Reflection.TypeFilter filter...
...
```

```powershell
[BasicTest] | Get-Member -Static
```

```Output
  TypeName: BasicTest

Name            MemberType Definition
----            ---------- ----------
Add             Method     static int Add(int a, int b)
Equals          Method     static bool Equals(System.Object objA, System.Object objB)
new             Method     BasicTest new()
ReferenceEquals Method     static bool ReferenceEquals(System.Object objA, System.Object objB)
```

```powershell
$BasicTestObject | Get-Member
```

```Output
   TypeName: BasicTest

Name        MemberType Definition
----        ---------- ----------
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
Multiply    Method     int Multiply(int a, int b)
ToString    Method     string ToString()
```

`Get-Member`Mit dem-Cmdlet werden der Typ und die Member der **basictest** -Klasse abgerufen, die `Add-Type` der Sitzung hinzugefügt wurden. Der `Get-Member` Befehl zeigt, dass es sich um ein **System. RuntimeType** -Objekt handelt, das von der **System. Object** -Klasse abgeleitet ist.

Der `Get-Member` **static** -Parameter ruft die statischen Eigenschaften und Methoden der **basictest** -Klasse ab. Die Ausgabe zeigt, dass die- `Add` Methode enthalten ist.

Das- `Get-Member` Cmdlet ruft die Member des-Objekts ab, das in der Variablen gespeichert ist `$BasicTestObject` .
`$BasicTestObject` wurde mithilfe des `New-Object` Cmdlets mit der **basictest** -Klasse erstellt. Die Ausgabe zeigt, dass der Wert der `$BasicTestObject` Variablen eine Instanz der **basictest** -Klasse ist und einen Member mit dem Namen enthält `Multiply` .

### Beispiel 3: Hinzufügen von Typen aus einer Assembly

In diesem Beispiel werden die Klassen der- `Accessibility.dll` Assembly der aktuellen Sitzung hinzugefügt.

```powershell
$AccType = Add-Type -AssemblyName "accessib*" -PassThru
```

Die- `$AccType` Variable speichert ein mit dem- `Add-Type` Cmdlet erstelltes Objekt. `Add-Type` verwendet den **AssemblyName** -Parameter, um den Namen der Assembly anzugeben. Mit dem Platzhalter Zeichen Sternchen ( `*` ) können Sie die richtige Assembly auch dann erhalten, wenn Sie den Namen oder die Schreibweise nicht sicher sind. Der **passthru** -Parameter generiert-Objekte, die die Klassen darstellen, die der Sitzung hinzugefügt werden.

### Beispiel 4: Abrufen von systemeigenen Windows-APIs

In diesem Beispiel wird veranschaulicht, wie Native Windows-APIs in PowerShell aufgerufen werden. `Add-Type` verwendet den Platt Form Aufruf-Mechanismus (P/aufrufen), um eine Funktion in über `User32.dll` PowerShell aufzurufen. Dieses Beispiel funktioniert nur auf Computern, auf denen das Windows-Betriebssystem ausgeführt wird.

```powershell
$Signature = @"
[DllImport("user32.dll")]public static extern bool ShowWindowAsync(IntPtr hWnd, int nCmdShow);
"@

$ShowWindowAsync = Add-Type -MemberDefinition $Signature -Name "Win32ShowWindowAsync" -Namespace Win32Functions -PassThru

# Minimize the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $pid).MainWindowHandle, 2)

# Restore the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $Pid).MainWindowHandle, 4)
```

Die `$Signature` Variable speichert die c#-Signatur der `ShowWindowAsync` Funktion. Um sicherzustellen, dass die resultierende Methode in einer PowerShell-Sitzung sichtbar ist, wurde das- `public` Schlüsselwort der Standard Signatur hinzugefügt. Weitere Informationen finden Sie unter [ShowWindowAsync-Funktion](/windows/win32/api/winuser/nf-winuser-showwindowasync).

Die- `$ShowWindowAsync` Variable speichert das-Objekt, das vom `Add-Type` **passthru** -Parameter erstellt wurde.
Das- `Add-Type` Cmdlet fügt die `ShowWindowAsync` Funktion als statische Methode zur PowerShell-Sitzung hinzu. Der Befehl verwendet den Parameter " **Membership Definition** ", um die in der Variablen gespeicherte Methoden Definition anzugeben `$Signature` . Der Befehl verwendet die Parameter **Name** und **Namespace**, um einen Namen und einen Namespace für die Klasse anzugeben. Der **passthru** -Parameter generiert ein Objekt, das die Typen darstellt.

Die neue `ShowWindowAsync` statische Methode wird in den Befehlen verwendet, um die PowerShell-Konsole zu minimieren und wiederherzustellen. Die-Methode nimmt zwei Parameter an: das Fenster Handle und eine ganze Zahl, die angibt, wie das Fenster angezeigt wird.

Um die PowerShell-Konsole zu minimieren, `ShowWindowAsync` verwendet das `Get-Process` Cmdlet mit der `$PID` automatischen Variablen, um den Prozess zu erhalten, der die aktuelle PowerShell-Sitzung gehostet. Anschließend wird die **MainWindowHandle** -Eigenschaft des aktuellen Prozesses und der Wert verwendet `2` , der den- `SW_MINIMIZE` Wert darstellt.

Um das Fenster wiederherzustellen, `ShowWindowAsync` verwendet den Wert `4` für die Fensterposition, die den `SW_RESTORE` Wert darstellt.

Um das Fenster zu maximieren, verwenden Sie den Wert von `3` , der darstellt `SW_MAXIMIZE` .

### Beispiel 5: Hinzufügen eines Typs aus einer Visual Basic Datei

In diesem Beispiel wird das `Add-Type` -Cmdlet verwendet, um die in der Datei definierte **vbfromfile** -Klasse `Hello.vb` der aktuellen Sitzung hinzuzufügen. Der Text der `Hello.vb` Datei wird in der Befehlsausgabe angezeigt.

```powershell
Add-Type -Path "C:\PS-Test\Hello.vb"
[VBFromFile]::SayHello(", World")

# From Hello.vb

Public Class VBFromFile
  Public Shared Function SayHello(sourceName As String) As String
    Dim myValue As String = "Hello"
    return myValue + sourceName
  End Function
End Class
```

```Output
Hello, World
```

`Add-Type` verwendet den **path** -Parameter, um die Quelldatei anzugeben, `Hello.vb` und fügt den in der Datei definierten Typ hinzu. Die- `SayHello` Funktion wird als statische Methode der **vbfromfile** -Klasse aufgerufen.

### Beispiel 6: Hinzufügen einer Klasse mit JScript.net

In diesem Beispiel wird JScript.NET verwendet, um eine neue Klasse ( **frechteck**) in der PowerShell-Sitzung zu erstellen.

```powershell
Add-Type @'
 class FRectangle {
   var Length : double;
   var Height : double;
   function Perimeter() : double {
       return (Length + Height) * 2; }
   function Area() : double {
       return Length * Height;  } }
'@ -Language JScript

$rect = [FRectangle]::new()
$rect
```

```Output
Length Height
------ ------
     0      0
```

### Beispiel 7: Hinzufügen eines F #-Compilers

In diesem Beispiel wird gezeigt, wie Sie mit dem `Add-Type` Cmdlet ihrer PowerShell-Sitzung einen F #-Code Compiler hinzufügen. Um dieses Beispiel in PowerShell auszuführen, müssen Sie über das verfügen, das `FSharp.Compiler.CodeDom.dll` mit der Sprache F # installiert ist.

```powershell
Add-Type -Path "FSharp.Compiler.CodeDom.dll"
$Provider = New-Object Microsoft.FSharp.Compiler.CodeDom.FSharpCodeProvider
$FSharpCode = @"
let rec loop n =if n <= 0 then () else beginprint_endline (string_of_int n);loop (n-1)end
"@
$FSharpType = Add-Type -TypeDefinition $FSharpCode -CodeDomProvider $Provider -PassThru |
   Where-Object { $_.IsPublic }
$FSharpType::loop(4)
```

```Output
4
3
2
1
```

`Add-Type` verwendet den **path** -Parameter, um eine Assembly anzugeben, und ruft die Typen in der Assembly ab.
`New-Object` erstellt eine Instanz des F #-Code Anbieters und speichert das Ergebnis in der `$Provider` Variablen. Die- `$FSharpCode` Variable speichert den F #-Code, der die **Schleifen** Methode definiert.

Die- `$FSharpType` Variable speichert die Ergebnisse des- `Add-Type` Cmdlets, das die in definierten öffentlichen Typen speichert `$FSharpCode` . Der **TypeDefinition**-Parameter gibt den Quellcode an, der die Typen definiert. Der **CodeDomProvider**-Parameter gibt den Quellcodecompiler an. Der **passthru** -Parameter weist `Add-Type` an, ein **Lauf** Zeit Objekt zurückzugeben, das die Typen darstellt.
Die Objekte werden über die Pipeline an das `Where-Object` Cmdlet gesendet, das nur die öffentlichen Typen zurückgibt. Das **Where-Object-** Cmdlet wird verwendet, da der F #-Anbieter nicht öffentliche Typen generiert, um den resultierenden öffentlichen Typ zu unterstützen.

Die Schleifen Methode wird als statische Methode des in der Variablen gespeicherten Typs aufgerufen `$FSharpType` .

## PARAMETERS

### -AssemblyName

Gibt den Namen einer Assembly an, die die Typen enthält. `Add-Type` nimmt die Typen aus der angegebenen Assembly. Dieser Parameter ist erforderlich, wenn Sie Typen auf der Grundlage eines Assemblynamens erstellen.

Geben Sie den vollständigen oder einfachen Namen einer Assembly ein, die auch als partieller Name bezeichnet wird. Der Assemblyname darf Platzhalterzeichen enthalten. Wenn Sie einen einfachen oder partiellen Namen eingeben, wird `Add-Type` dieser in den vollständigen Namen aufgelöst, und dann wird der vollständige Name verwendet, um die Assembly zu laden.

Dieser Parameter akzeptiert keinen Pfad oder Dateinamen. Um den Pfad zur DLL-Datei (Dynamic Link Library) der Assembly einzugeben, verwenden Sie den **path** -Parameter.

```yaml
Type: System.String[]
Parameter Sets: FromAssemblyName
Aliases: AN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -CodeDom Provider

Gibt einen Code-Generator oder Compiler an. `Add-Type` verwendet den angegebenen Compiler zum Kompilieren des Quellcodes. Der Standardwert ist der c#-Compiler. Verwenden Sie diesen Parameter, wenn Sie eine Sprache verwenden, die mit dem **Language** -Parameter nicht angegeben werden kann. Der von Ihnen angegebene **CodeDom Provider** muss in der Lage sein, Assemblys aus dem Quellcode zu generieren.

```yaml
Type: System.CodeDom.Compiler.CodeDomProvider
Parameter Sets: FromSource, FromMember
Aliases: Provider

Required: False
Position: Named
Default value: C# compiler
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompilerParameters

Gibt die Optionen für den Quellcodecompiler an. Diese Optionen werden ohne Revision an den Compiler gesendet.

Mit diesem Parameter können Sie den Compiler anweisen, eine ausführbare Datei zu generieren, Ressourcen einzubetten oder Befehlszeilenoptionen (z. b. die Option) festzulegen `/unsafe` . Dieser Parameter implementiert die **CompilerParameters** -Klasse, **System. CodeDom. Compiler. CompilerParameters**.

Der **CompilerParameters** -Parameter und der **referencedassemblyparameter** können nicht im selben Befehl verwendet werden.

```yaml
Type: System.CodeDom.Compiler.CompilerParameters
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: CP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ignorewarning

Ignoriert Compilerwarnungen. Verwenden Sie diesen Parameter, um zu verhindern, dass `Add-Type` Compilerwarnungen als Fehler behandelt werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sprache

Gibt die Sprache an, die im Quellcode verwendet wird. Das `Add-Type` Cmdlet verwendet den Wert dieses Parameters, um den entsprechenden **CodeDom Provider** auszuwählen. CSharp ist der Standardwert. Die zulässigen Werte für diesen Parameter lauten wie folgt:

- CSharp
- CSharpVersion2
- CSharpVersion3
- JScript
- Visual Basic

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp, CSharpVersion2, CSharpVersion3, JScript, VisualBasic

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### -Literalpath

Gibt den Pfad zu Quellcodedateien oder Assembly-DLL-Dateien an, die die Typen enthalten. Im Gegensatz zu **path** wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mitglieddefinition

Gibt neue Eigenschaften oder Methoden für die Klasse an. `Add-Type` generiert den Vorlagen Code, der zur Unterstützung der Eigenschaften oder Methoden erforderlich ist.

Unter Windows können Sie diese Funktion verwenden, um Platt Form Aufrufe (P/aufrufen) von nicht verwalteten Funktionen in PowerShell durchführen.

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt den Namen der zu erstellenden Klasse an. Dieser Parameter ist beim Generieren eines Typs aus einer Memberdefinition erforderlich.

Der Typname und der Namespace müssen innerhalb einer Sitzung eindeutig sein. Ein Typ kann nicht entladen oder geändert werden.
Wenn Sie den Code für einen Typ ändern möchten, müssen Sie den Namen ändern oder eine neue PowerShell-Sitzung starten.
Andernfalls führt der Befehl zu einem Fehler.

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Gibt einen Namespace für den Typ an.

Wenn dieser Parameter nicht im Befehl enthalten ist, wird der Typ im **Microsoft. PowerShell. Commands. AddType. autogeneratedtypes** -Namespace erstellt. Wenn der Parameter im Befehl mit einem leeren Zeichen folgen Wert oder einem Wert von enthalten ist `$Null` , wird der Typ im globalen Namespace generiert.

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputAssembly

Generiert eine DLL-Datei für die Assembly mit dem angegebenen Namen an dem Speicherort. Geben Sie einen optionalen Pfad und Dateinamen ein. Platzhalterzeichen sind zulässig. Standardmäßig `Add-Type` generiert die Assembly nur im Arbeitsspeicher.

```yaml
Type: System.String
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -OutputType

Gibt den Ausgabetyp der Ausgabeassembly an. Standardmäßig wird kein Ausgabetyp angegeben. Dieser Parameter gilt nur, wenn eine Ausgabeassembly im Befehl angegeben wird. Weitere Informationen zu den Werten finden Sie unter [outputassemblytype-Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- ConsoleApplication
- Bibliothek
- Datei WindowsApplication

```yaml
Type: Microsoft.PowerShell.Commands.OutputAssemblyType
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OT
Accepted values: ConsoleApplication, Library, WindowsApplication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt ein **System.Runtime**-Objekt zurück, das die Typen darstellt, die hinzugefügt wurden. Standardmäßig generiert dieses Cmdlet keine Ausgabe.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zu Quellcodedateien oder Assembly-DLL-Dateien an, die die Typen enthalten.

Wenn Sie Quell Code Dateien übermitteln, `Add-Type` kompiliert den Code in den Dateien und erstellt eine in-Memory-Assembly der Typen. Die im **Pfad** Wert angegebene Dateinamenerweiterung bestimmt den Compiler, der von `Add-Type` verwendet wird.

Wenn Sie eine Assemblydatei übermitteln, `Add-Type` übernimmt die Typen aus der Assembly. Um eine speicherinterne Assembly oder den globalen Assemblycache anzugeben, verwenden Sie den **AssemblyName**-Parameter.

```yaml
Type: System.String[]
Parameter Sets: FromPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Referencedassemblys

Gibt die Assemblys an, von denen der Typ abhängig ist. Standardmäßig `Add-Type` verweist auf `System.dll` und `System.Management.Automation.dll` . Auf die Assemblys, die Sie mithilfe dieses Parameters angeben, wird zusätzlich zu den Standardassemblys verwiesen.

Der **CompilerParameters** -Parameter und der **referencedassemblyparameter** können nicht im selben Befehl verwendet werden.

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: RA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeDefinition

Gibt den Quellcode an, der die Typdefinitionen enthält. Geben Sie den Quellcode in einer Zeichenfolge oder einer here-Zeichenfolge ein, oder geben Sie eine Variable ein, die den Quellcode enthält. Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).

Schließen Sie eine Namespacedeklaration in die Typdefinition ein. Wenn Sie die Namespacedeklaration weglassen, kann der Typ denselben Namen wie ein anderer Typ oder die Verknüpfung für einen anderen Typ aufweisen, was zu einer unbeabsichtigten Überschreibung führen kann. Wenn Sie z. b. einen Typ mit dem Namen " **Exception**" definieren, schlagen Skripts, die eine **Ausnahme** als Verknüpfung für **System. Exception** verwenden, fehl.

```yaml
Type: System.String
Parameter Sets: FromSource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usingnamespace

Gibt andere Namespaces an, die für die Klasse erforderlich sind. Dies ähnelt dem c#-Schlüsselwort `Using` .

Standardmäßig `Add-Type` verweist auf den **System** -Namespace. Wenn der Parameter " **Membership Definition** " verwendet wird, `Add-Type` verweist standardmäßig auch auf den **System. Runtime. InteropServices** -Namespace. Auf die Namespaces, die Sie mithilfe der **UsingNamespace**-Parameter hinzufügen, wird zusätzlich zu den standardmäßigen Namespaces verwiesen.

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases: Using

Required: False
Position: Named
Default value: System namespace
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Objekte können nicht über die Pipeline an gesendet werden `Add-Type` .

## AUSGABEN

### None oder System. Type

Wenn Sie den **passthru** -Parameter verwenden, `Add-Type` gibt ein **System. Type** -Objekt zurück, das den neuen Typ darstellt. Andernfalls generiert dieses Cmdlet keine Ausgabe.

## HINWEISE

Die Typen, die Sie hinzufügen, sind nur in der aktuellen Sitzung vorhanden. Um die Typen in allen Sitzungen zu verwenden, fügen Sie Sie Ihrem PowerShell-Profil hinzu. Weitere Informationen zum Profil finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

Typnamen und Namespaces müssen innerhalb einer Sitzung eindeutig sein. Ein Typ kann nicht entladen oder geändert werden. Wenn Sie den Code für einen Typ ändern müssen, müssen Sie den Namen ändern oder eine neue PowerShell-Sitzung starten.
Andernfalls führt der Befehl zu einem Fehler.

Die **CodeDom Provider** -Klasse für einige Sprachen, z. b. IronPython und j#, generiert keine Ausgabe. Daher können in diesen Sprachen geschriebene Typen nicht mit verwendet werden `Add-Type` .

Dieses Cmdlet basiert auf der Microsoft .NET Framework- [CodeDom Provider-Klasse](/dotnet/api/system.codedom.compiler.codedomprovider).

## VERWANDTE LINKS

[about_Profiles](../Microsoft.PowerShell.Core/About/about_profiles.md)

[about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[Add-Member](Add-Member.md)

[New-Object](New-Object.md)

[OutputAssemblyType](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[Plattformaufruf (P/Invoke)](/dotnet/standard/native-interop/pinvoke)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
