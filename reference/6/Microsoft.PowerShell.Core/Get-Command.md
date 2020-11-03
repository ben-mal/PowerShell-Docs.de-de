---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/14/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command
ms.openlocfilehash: 5e76a15e8f2dcacc7f973cbc46d057bb92c3ad41
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217236"
---
# Get-Command

## ZUSAMMENFASSUNG
Ruft alle Befehle ab.

## SYNTAX

### CmdletSet (Standard)

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
 [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
 [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### Allcommandset

```
Get-Command [[-Name] <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-CommandType <CommandTypes>] [-TotalCount <Int32>]
 [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [-UseFuzzyMatching]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-Command` Cmdlet ruft alle Befehle ab, die auf dem Computer installiert sind, einschließlich Cmdlets, Aliase, Funktionen, Filter, Skripts und Anwendungen. `Get-Command` Ruft die Befehle aus PowerShell-Modulen und-Befehlen ab, die aus anderen Sitzungen importiert wurden. Um nur die Befehle zu erhalten, die in die aktuelle Sitzung importiert wurden, verwenden Sie den **ListImported** -Parameter.

Ohne Parameter `Get-Command` Ruft alle-Cmdlets,-Funktionen und-Aliase ab, die auf dem Computer installiert sind. `Get-Command *` Ruft alle Befehls Typen ab, einschließlich aller nicht-PowerShell-Dateien in der PATH-Umgebungsvariablen ( `$env:Path` ), die Sie im Anwendungs Befehlstyp auflistet.

`Get-Command` der den genauen Namen des Befehls ohne Platzhalter Zeichen verwendet, importiert automatisch das Modul, das den Befehl enthält, sodass Sie den Befehl sofort verwenden können. Verwenden Sie die Preference-Variable, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren `$PSModuleAutoLoadingPreference` . Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).

`Get-Command` Ruft die zugehörigen Daten direkt aus dem Befehls Code ab, wobei `Get-Help` die Informationen aus Hilfe Themen abgerufen werden.

Ab Windows PowerShell 5,0 zeigen die Ergebnisse des `Get-Command` Cmdlets standardmäßig eine **Versions** Spalte an. Der **CommandInfo** -Klasse wurde eine neue **Versions** Eigenschaft hinzugefügt.

## BEISPIELE

### Beispiel 1: Cmdlets, Funktionen und Aliase

Mit diesem Befehl werden die auf dem Computer installierten PowerShell-Cmdlets,-Funktionen und-Aliase abgerufen.

```powershell
Get-Command
```

### Beispiel 2: Get-Befehle in der aktuellen Sitzung

Dieser Befehl verwendet den **ListImported** -Parameter, um nur die Befehle in der aktuellen Sitzung abzurufen.

```powershell
Get-Command -ListImported
```

### Beispiel 3: Cmdlets erhalten und in der richtigen Reihenfolge angezeigt

Dieser Befehl ruft alle Cmdlets ab, sortiert sie alphabetisch nach dem Nomen im Cmdlet-Namen und zeigt sie dann in nomenbasierten Gruppen an. Diese Anzeige hilft Ihnen dabei, die Cmdlets für eine Aufgabe zu finden.

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### Beispiel 4: Get-Befehle in einem Modul

Dieser Befehl verwendet den **Module** -Parameter, um die Befehle in den Modulen "Microsoft. PowerShell. Security" und "Microsoft. PowerShell. Utility" zu erhalten.

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### Beispiel 5: erhalten von Informationen zu einem Cmdlet

Dieser Befehl ruft Informationen über das `Get-AppLockerPolicy` Cmdlet ab. Der Befehl importiert auch das **AppLocker** -Modul, das alle Befehle im **AppLocker** -Modul zur aktuellen Sitzung hinzufügt.

```powershell
Get-Command Get-AppLockerPolicy
```

Wenn ein Modul automatisch importiert wird, entspricht der Effekt dem Verwenden des Import-Module-Cmdlets.
Das Modul kann Befehle, Typen und Formatierungsdateien hinzufügen und Skripts in der Sitzung ausführen. Verwenden Sie die Preference-Variable, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren `$PSModuleAutoLoadingPreference` . Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

### Beispiel 6: erhalten der Syntax eines Cmdlets

Dieser Befehl verwendet den Argument **List** -Parameter und den **Syntax** Parameter, um die Syntax des Cmdlets zu erhalten, `Get-ChildItem` Wenn es im CERT:-Laufwerk verwendet wird. Das Laufwerk "CERT:" ist ein PowerShell-Laufwerk, das der Zertifikat Anbieter der Sitzung hinzufügt.

```powershell
Get-Command Get-Childitem -Args Cert: -Syntax
```

Wenn Sie die in der Ausgabe angezeigte Syntax mit der Syntax vergleichen, die angezeigt wird, wenn Sie den **args** -Parameter (Argument **List** ) weglassen, sehen Sie, dass der **Zertifikat Anbieter** dem Cmdlet einen dynamischen Parameter, **codeSigningCert** , hinzufügt `Get-ChildItem` .

Weitere Informationen zum Zertifikat Anbieter finden Sie unter [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).

### Beispiel 7: Get Dynamic Parameters

Der Befehl im Beispiel verwendet die- `Get-DynamicParameters` Funktion, um die dynamischen Parameter zu erhalten, die der Zertifikat Anbieter dem `Get-ChildItem` Cmdlet hinzufügt, wenn er im CERT:-Laufwerk verwendet wird.

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command $Cmdlet -ArgumentList $PSDrive).ParameterSets | ForEach-Object {$_.Parameters} | Where-Object { $_.IsDynamic } | Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

Die- `Get-DynamicParameters` Funktion in diesem Beispiel ruft die dynamischen Parameter eines Cmdlets ab. Dies ist eine Alternative zu der Methode, die im vorherigen Beispiel verwendet wurde. Der dynamische Parameter kann durch andere Cmdlets oder einen Anbieter zu einem Cmdlet hinzugefügt werden.

### Beispiel 8: alle Befehle aller Typen erhalten

Mit diesem Befehl werden alle Befehle aller Typen auf dem lokalen Computer abgerufen, einschließlich der ausführbaren Dateien in den Pfaden der **path** -Umgebungsvariablen ( `$env:path` ).

```powershell
Get-Command *
```

Der Befehl gibt ein **ApplicationInfo** -Objekt (System.Management.Automation.ApplicationInfo) für jede Datei und kein **FileInfo** -Objekt (System.IO.FileInfo) zurück.

### Beispiel 9: Cmdlets mithilfe eines Parameter namens und-Typs

Dieser Befehl ruft Cmdlets ab, die über einen Parameter verfügen, dessen Name "auth" und dessen Typ " **authenticationmechanism** " ist.

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

Verwenden Sie Befehle wie diesen, um nach Cmdlets zu suchen, mit denen Sie die Methode angeben können, die zum Authentifizieren des Benutzers verwendet wird.

Der **ParameterType** -Parameter unterscheidet Parameter, die einen **AuthenticationMechanism** -Wert akzeptieren, von Parametern, die einen **AuthenticationLevel** -Wert akzeptieren, selbst wenn sie ähnliche Namen haben.

### Beispiel 10: Holen Sie sich einen Alias

In diesem Beispiel wird gezeigt, wie das `Get-Command` Cmdlet mit einem Alias verwendet wird.

```powershell
Get-Command dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

Obwohl es in der Regel für Cmdlets und Funktionen verwendet wird, ruft `Get-Command` auch Skripts, Funktionen, Aliase und ausführbare Dateien ab.

Die Befehlsausgabe zeigt die Ansicht des **Name** -Eigenschaftswerts für Aliase. Die Ansicht zeigt den Alias und den vollständigen Befehlsnamen.

### Beispiel 11: alle Instanzen des Notepad-Befehls erhalten

In diesem Beispiel wird der **all** -Parameter des `Get-Command` Cmdlets verwendet, um alle Instanzen des Befehls "Notepad" auf dem lokalen Computer anzuzeigen.

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

Der **All** -Parameter ist nützlich, wenn es mehr als einen Befehl mit demselben Namen in der Sitzung gibt.

Ab Windows PowerShell 3,0, wenn die Sitzung mehrere Befehle mit demselben Namen enthält, wird von nur der Befehl abgerufen, der ausgeführt wird, `Get-Command` Wenn Sie den Befehlsnamen eingeben. Mit dem **all** -Parameter ruft `Get-Command` alle Befehle mit dem angegebenen Namen ab und gibt Sie in der Ausführungs Rangfolge zurück. Um einen anderen Befehl als den ersten in der Liste auszuführen, geben Sie den vollqualifizierten Pfad zu dem Befehl ein.

Weitere Informationen zur Befehls Rangfolge finden Sie unter [about_Command_Precedence](About/about_Command_Precedence.md).

### Beispiel 12: Holen Sie sich den Namen eines Moduls, das ein Cmdlet enthält.

Mit diesem Befehl wird der Name des Moduls abgerufen, von dem das `Get-Date` Cmdlet stammt.
Der Befehl verwendet die **ModuleName** -Eigenschaft aller Befehle.

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

Dieses Befehls Format funktioniert mit Befehlen in PowerShell-Modulen, auch wenn Sie nicht in die Sitzung importiert werden.

### Beispiel 13: Cmdlets und Funktionen mit einem Ausgabetyp

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

Dieser Befehl ruft die Cmdlets und Funktionen ab, die über einen Ausgabetyp verfügen, und den Typ der Objekte, die sie zurückgeben.

Der erste Teil des Befehls ruft alle Cmdlets ab.
Ein Pipeline Operator (|) sendet die Cmdlets an das `Where-Object` Cmdlet, das nur die Cmdlets auswählt, in denen die **OutputType** -Eigenschaft aufgefüllt ist.
Ein weiterer Pipeline Operator sendet die ausgewählten Cmdlet-Objekte an das `Format-List` Cmdlet, das den Namen und den Ausgabetyp der einzelnen Cmdlets in einer Liste anzeigt.

Die **OutputType** -Eigenschaft eines **CommandInfo** -Objekts hat nur dann einen Nicht-Null-Wert, wenn der Cmdlet-Code das **OutputType** -Attribut für das Cmdlet definiert.

### Beispiel 14: Get-Cmdlets, die einen bestimmten Objekttyp als Eingabe annehmen

```powershell
Get-Command -ParameterType (((Get-NetAdapter)[0]).PSTypeNames)
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Disable-NetAdapter                                 NetAdapter
Function        Enable-NetAdapter                                  NetAdapter
Function        Rename-NetAdapter                                  NetAdapter
Function        Restart-NetAdapter                                 NetAdapter
Function        Set-NetAdapter                                     NetAdapter
```

Mit diesem Befehl wird nach Cmdlets gesucht, die Netzwerkadapterobjekte als Eingabe akzeptieren. Verwenden Sie dieses Befehlsformat, um nach den Cmdlets zu suchen, die den Typ von Objekten akzeptieren, die ein beliebiger Befehl zurückgibt.

Der Befehl verwendet die systeminterne Eigenschaft aller Objekte **PSTypeNames** , die die Typen abruft, die das Objekt beschreiben. Zum Abrufen der **PSTypeNames** -Eigenschaft eines Netzwerkadapters und nicht der **PSTypeNames** -Eigenschaft einer Auflistung von Netzwerkadaptern verwendet der Befehl die Arraynotation, um den ersten Netzwerkadapter abzurufen, den das Cmdlet zurückgibt.

### Beispiel 15: Get-Befehle mithilfe einer Fuzzyübereinstimmung

In diesem Beispiel weist der Name des Befehls absichtlich einen Tippfehler als ' Get-commnd ' auf.
Mithilfe des- `-UseFuzzyMatching` Schalters hat das Cmdlet ermittelt, dass die beste Entsprechung `Get-Command` von anderen systemeigenen Befehlen auf dem System gefolgt ist, die eine ähnliche Entsprechung hatten.

```powershell
Get-Command get-commnd -UseFuzzyMatching
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Command                                        6.2.0.0    Microsoft.PowerShell.Core
Application     getconf                                            0.0.0.0    /usr/bin/getconf
Application     command                                            0.0.0.0    /usr/bin/command
```

## PARAMETERS

### -All

Gibt an, dass dieses Cmdlet alle Befehle abruft, einschließlich Befehlen desselben Typs, die denselben Namen aufweisen. Standardmäßig ruft `Get-Command` nur die Befehle ab, die ausgeführt werden, wenn Sie den Befehlsnamen eingeben.

Weitere Informationen zu der Methode, die von PowerShell verwendet wird, um den Befehl auszuwählen, der ausgeführt werden soll, wenn mehrere Befehle denselben Namen aufweisen, finden Sie unter [about_Command_Precedence](About/about_Command_Precedence.md).
Informationen zu Modul qualifizierten Befehlsnamen und zum Ausführen von Befehlen, die aufgrund eines Namens Konflikts nicht standardmäßig ausgeführt werden, finden Sie unter [about_Modules](About/about_Modules.md).

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

In Windows PowerShell 2,0 ruft `Get-Command` standardmäßig alle Befehle ab.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Argumentlist

Gibt ein Array von Argumenten an. Dieses Cmdlet ruft Informationen zu einem Cmdlet oder einer Funktion ab, wenn es mit den angegebenen Parametern ("Argumenten") verwendet wird. Der Alias für **ArgumentList** ist **Args**.

Um dynamische Parameter zu ermitteln, die nur verfügbar sind, wenn bestimmte andere Parameter verwendet werden, legen Sie den Wert von Argument **List** auf die Parameter fest, die die dynamischen Parameter auslöst.

Um die dynamischen Parameter zu ermitteln, die ein Anbieter zu einem Cmdlet hinzufügt, legen Sie den Wert des **argumentlist** -Parameters auf einen Pfad im Anbieter Laufwerk fest, z. b. WSMAN:, HKLM: oder CERT:. Wenn es sich bei dem Befehl um ein PowerShell-Anbieter-Cmdlet handelt, geben Sie in jedem Befehl nur einen Pfad ein. Die Anbieter-Cmdlets geben nur die dynamischen Parameter für den ersten Pfad den Wert von **argumentlist** zurück. Weitere Informationen zu den Anbieter-Cmdlets finden Sie unter [about_Providers](About/about_Providers.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandType

Gibt die Typen von Befehlen an, die von diesem Cmdlet abgerufen werden. Geben Sie einen oder mehrere Befehlstypen ein. Verwenden Sie **CommandType** oder dessen Aliasname **Type**. Standardmäßig `Get-Command` Ruft alle-Cmdlets,-Funktionen und-Aliase ab.

Zulässige Werte für diesen Parameter:

- Alias. Ruft die Aliase aller PowerShell-Befehle ab. Weitere Informationen finden Sie unter [about_Aliases](About/about_Aliases.md).
- Alle Ruft alle Befehlstypen ab. Dieser Parameterwert entspricht `Get-Command *` .
- Anwendung: Ruft nicht-PowerShell-Dateien in Pfaden ab, die in der **path** -Umgebungsvariablen ($env:p ATH) aufgelistet sind, einschließlich. txt-,. exe-und. dll-Dateien. Weitere Informationen zur **path** -Umgebungsvariablen finden Sie unter about_Environment_Variables.
- Cmdlet. Ruft alle Cmdlets ab.
- Externalscript. Ruft alle PS1-Dateien in den Pfaden ab, die in der **Path** -Umgebungsvariablen ($env:path) aufgeführt sind.
- Filter und function. Ruft alle erweiterten und einfachen PowerShell-Funktionen und-Filter ab.
- Skript. Ruft alle Skriptblöcke ab. Um PowerShell-Skripts (PS1-Dateien) zu erhalten, verwenden Sie den externalscript-Wert.

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: AllCommandSet
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Fullyqualifiedmodule

Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind, die im Abschnitt " **Hinweise** " des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)beschrieben werden.
Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der in einem der folgenden Formate angegeben ist:

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.

Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben. Die beiden Parameter schließen sich gegenseitig aus.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Listimportiert

Gibt an, dass dieses Cmdlet nur Befehle in der aktuellen Sitzung abruft.

Ab PowerShell 3,0 ruft standardmäßig `Get-Command` alle installierten Befehle ab, einschließlich, aber nicht beschränkt auf die Befehle in der aktuellen Sitzung. In PowerShell 2,0 werden nur Befehle in der aktuellen Sitzung abgerufen.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Modul

Gibt ein Array von Modulen an. Dieses Cmdlet ruft die Befehle ab, die von den angegebenen Modulen stammen.
Geben Sie die Namen der Module oder Modul Objekte ein.

Dieser Parameter nimmt Zeichen folgen Werte an, aber der Wert dieses Parameters kann auch ein **psmoduleinfo** -Objekt sein, z. b. die Objekte, die von den `Get-Module` -und- `Import-PSSession` Cmdlets zurückgegeben werden.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Name

Gibt ein Array von Namen an. Dieses Cmdlet ruft nur Befehle mit dem angegebenen Namen ab. Geben Sie einen Namen oder ein Namensmuster ein. Platzhalterzeichen sind zulässig.

Um Befehle abzurufen, die den gleichen Namen haben, verwenden Sie den **All** -Parameter. Wenn zwei Befehle denselben Namen haben, ruft standardmäßig den Befehl ab, der ausgeführt wird, `Get-Command` Wenn Sie den Befehlsnamen eingeben.

```yaml
Type: System.String[]
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Substantiv

Gibt ein Array von Befehls-nouns an. Dieses Cmdlet ruft die Befehle ab, die Cmdlets, Funktionen und Aliase enthalten, deren Namen das angegebene Substantiv enthalten. Geben Sie ein oder mehrere Nomen oder Nomenmuster ein. Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Parameter Name

Gibt ein Array von Parameternamen an. Dieses Cmdlet ruft die Befehle in der Sitzung ab, die über die angegebenen Parameter verfügen. Geben Sie Parameternamen oder Parameter Aliase ein. Platzhalterzeichen werden unterstützt.

Die Parameter **ParameterName** und **ParameterType** suchen nur Befehle in der aktuellen Sitzung.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ParameterType

Gibt ein Array von Parameternamen an. Dieses Cmdlet ruft die Befehle in der Sitzung ab, die Parameter des angegebenen Typs aufweisen. Geben Sie den vollständigen Namen oder Teilnamen eines Parametertyps ein. Platzhalterzeichen werden unterstützt.

Die Parameter **ParameterName** und **ParameterType** suchen nur Befehle in der aktuellen Sitzung.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.PSTypeName[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Showcommandinfo

Gibt an, dass dieses Cmdlet Befehls Informationen anzeigt.

Dieser Parameter wurde in Windows PowerShell 5,0 eingeführt.

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

### -Syntax

Gibt an, dass dieses Cmdlet nur die folgenden angegebenen Daten über den Befehl abruft:

- Aliase. Ruft den Standardnamen ab.
- Cmdlets. Ruft die Syntax ab.
- Funktionen und Filter. Ruft die Funktionsdefinition ab.
- Skripts und Anwendungen oder Dateien. Ruft den Pfad und Dateinamen ab.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TotalCount

Gibt die Anzahl der auszuführenden Befehle an. Mit diesem Parameter können Sie die Ausgabe eines Befehls beschränken.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Usefuzzymatching

Gibt die Verwendung eines Fuzzyübereinstimmungs Algorithmus beim Suchen von Befehlen Die Reihenfolge der Ausgabe ist von der nächsten Übereinstimmung bis zum wahrscheinlichsten Abgleich. Platzhalter sollten nicht mit Fuzzyübereinstimmung verwendet werden, da versucht wird, Befehle abzugleichen, die möglicherweise diese Platzhalter Zeichen enthalten.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Verb

Gibt ein Array von Befehls Verben an. Dieses Cmdlet ruft die Befehle ab, die Cmdlets, Funktionen und Aliase enthalten, deren Namen das angegebene Verb enthalten. Geben Sie ein oder mehrere Verben oder Verbmuster ein. Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können Befehlsnamen an dieses Cmdlet weiterreichen.

## AUSGABEN

### System. Management. Automation. CommandInfo

Dieses Cmdlet gibt Objekte zurück, die von der **CommandInfo** -Klasse abgeleitet wurden. Der Typ des Objekts, das zurückgegeben wird, hängt vom Typ des Befehls ab, der abgerufen wird `Get-Command` .

### System. Management. Automation. AliasInfo

Stellt Aliase dar.

### System. Management. Automation. ApplicationInfo

Stellt Anwendungen und Dateien dar.

### System. Management. Automation. cmdletinfo

Stellt Cmdlets dar.

### System. Management. Automation. functioninfo

Stellt Funktionen und Filter dar.

## HINWEISE

* Wenn mehr als ein Befehl mit demselben Namen für die Sitzung verfügbar ist, `Get-Command` gibt den Befehl zurück, der ausgeführt wird, wenn Sie den Befehlsnamen eingeben. Verwenden Sie den **all** -Parameter, um Befehle mit dem gleichen Namen, die in der Reihenfolge der Bestellung aufgeführt sind, zu erhalten. Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).
* Wenn ein Modul automatisch importiert wird, entspricht der Effekt dem Verwenden des `Import-Module` Cmdlets. Das Modul kann Befehle, Typen und Formatierungsdateien hinzufügen und Skripts in der Sitzung ausführen.
  Verwenden Sie die Preference-Variable, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren `$PSModuleAutoLoadingPreference` . Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

## VERWANDTE LINKS

[Export-PSSession](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[Get-Help](Get-Help.md)

[Get-Member](../Microsoft.PowerShell.Utility/Get-Member.md)

[Get-PSDrive](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[Import-PSSession](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[about_Command_Precedence](About/about_Command_Precedence.md)
