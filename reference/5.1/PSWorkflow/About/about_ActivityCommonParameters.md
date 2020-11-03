---
description: Beschreibt die Parameter, die durch den Windows PowerShell-Workflow zu Aktivitäten hinzugefügt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_activitycommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über_ActivityCommonParameters
ms.openlocfilehash: b745bf17e4ae26156042ecdc25211830177bc692
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221916"
---
# <a name="about-activitycommonparameters"></a>Informationen zu activitycommonparameters

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt die Parameter, die durch den Windows PowerShell-Workflow zu Aktivitäten hinzugefügt werden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Der Windows PowerShell-Workflow fügt die allgemeinen Aktivitäts Parameter zu Aktivitäten hinzu, die von der psactivity-Basisklasse abgeleitet werden. Diese Kategorie enthält die InlineScript-Aktivität und Windows PowerShell-Cmdlets, die als Aktivitäten implementiert sind, z. b. Get-Process und Get-WinEvent.

Die allgemeinen Aktivitäts Parameter sind für die Suspend-Workflow-und Checkpoint-Workflow Aktivitäten ungültig und werden nicht zu Cmdlets oder Ausdrücken hinzugefügt, die der Windows PowerShell-Workflow automatisch in einem InlineScript-Skriptblock oder einer ähnlichen Aktivität ausführt. Die allgemeinen Aktivitätsparameter sind für die Aktivität InlineScript verfügbar, nicht aber für die Befehle im Skriptblock InlineScript.

Einige der allgemeinen Aktivitäts Parameter sind auch allgemeine Workflow Parameter oder allgemeine Windows PowerShell-Parameter. Andere allgemeine Aktivitäts Parameter sind nur für Aktivitäten spezifisch.

Weitere Informationen zu allgemeinen Workflowparametern finden Sie unter about_WorkflowCommonParameters. Informationen zu den allgemeinen Windows PowerShell-Parametern finden Sie unter about_CommonParameters.

### <a name="list-of-activity-common-parameters"></a>Liste der allgemeinen Aktivitäts Parameter

```
AppendOutput                      PSDebug
Debug                             PSDisableSerialization
DisplayName                       PSDisableSerializationPreference
ErrorAction                       PSError
Input                             PSPersist
MergeErrorToOutput                PSPort
PSActionRetryCount                PSProgress
PSActionRetryIntervalSec          PSProgressMessage
PSActionRunningTimeoutSec         PSRemotingBehavior
PSApplicationName                 PSRequiredModules
PSAuthentication                  PSSessionOption
PSCertificateThumbprint           PSUseSSL
PSComputerName                    PSVerbose
PSConfigurationName               PSWarning
PSConnectionRetryCount            Result
PSConnectionRetryIntervalSec      UseDefaultInput
PSConnectionURI                   Verbose
PSCredential                      WarningAction
```

### <a name="parameter-descriptions"></a>Parameter Beschreibungen

In diesem Abschnitt werden die allgemeinen Aktivitäts Parameter beschrieben.

#### <a name="appendoutput-boolean"></a>Appendoutput \<Boolean\>

Mit dem Wert wird `$True` die Ausgabe der-Aktivität dem Wert der Variablen hinzugefügt.
Der Wert `$False` hat keine Auswirkung. In der Standardeinstellung ersetzt das Zuweisen eines Werts zu einer Variablen den Wert der Variablen.

Die folgenden Befehle fügen z. b. dem Dienst Objekt in der Variablen ein Prozess Objekt hinzu `$x` .

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x = Get-Process -AppendOutput $true
}
```

Dieser Parameter ist für XAML-basierte Workflows konzipiert. In Skript Workflows können Sie auch den + =-Zuweisungs Operator verwenden, um eine Ausgabe zum Wert einer Variablen hinzuzufügen, wie im folgenden Beispiel gezeigt.

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x += Get-Process
}
```

#### <a name="debug-switchparameter"></a>Gen \<SwitchParameter\>

Zeigt Details zur Programmierungs Ebene zu dem vom Befehl ausgeführten Vorgang an.
Der Debug-Parameter überschreibt den Wert der $debugPreference-Variablen für den aktuellen Befehl. Dieser Parameter funktioniert nur, wenn der Befehl Debugmeldungen generiert. Bei diesem Parameter handelt es sich auch um einen allgemeinen Windows PowerShell-Parameter.

#### <a name="displayname-string"></a>Display Name \<String\>

Gibt einen Anzeigenamen für die Aktivität an. Der DisplayName-Wert wird in der Statusanzeige angezeigt, während der Workflow ausgeführt wird, und im Wert der Progress-Eigenschaft des Workflow Auftrags. Wenn der psprogressmessage-Parameter auch im Befehl enthalten ist, wird der Inhalt der Statusanzeige \<DisplayName\> im \<PSProgressMessage\> Format angezeigt.

#### <a name="erroraction-actionpreference"></a>ErrorAction \<ActionPreference\>

Bestimmt, wie die Aktivität auf einen Fehler ohne Abbruch vom Befehl antwortet. Dies hat keine Auswirkung auf Abbruch Fehler. Dieser Parameter funktioniert nur, wenn der Befehl einen Fehler ohne Abbruch generiert, z. b. die des Write-Error-Cmdlets. Der ErrorAction-Parameter überschreibt den Wert der $ErrorActionPreference-Variablen für den aktuellen Befehl. Bei diesem Parameter handelt es sich auch um einen allgemeinen Windows PowerShell-Parameter.

Gültige Werte:

- Auch. Zeigt die Fehlermeldung an und setzt die Ausführung des Befehls fort. "Continue" ist der Standardwert.

- Ignorieren. Unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.
  Anders als SilentlyContinue wird die Fehlermeldung von IGNORE nicht der automatischen $Error-Variablen hinzugefügt. Der Wert Ignore wird in Windows PowerShell 3,0 eingeführt.

- Digte. Zeigt die Fehlermeldung an und fordert Sie zur Bestätigung auf, bevor die Ausführung fortgesetzt wird. Dieser Wert wird nur selten verwendet.

- Anhalten. Hält einen Workflow Auftrag automatisch an, um weitere Untersuchungen zu ermöglichen. Nach der Untersuchung kann der Workflow fortgesetzt werden.

- SilentlyContinue. Unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.

- Beenden Zeigt die Fehlermeldung an und beendet die Ausführung des Befehls.

#### <a name="input-object"></a>Der \<Object[]\>

Übermittelt eine Auflistung von Objekten an eine Aktivität. Dies stellt eine Alternative zum einzelnen Weiterleiten von Objekten an die Aktivität dar.

#### <a name="mergeerrortooutput-boolean"></a>Mergeerrordeoutput \<Boolean\>

`$True`Der Wert fügt dem Ausgabestream Fehler hinzu. Der Wert `$False` hat keine Auswirkung. Verwenden Sie diesen Parameter mit den parallelen `ForEach -Parallel` Schlüsselwörtern und, um Fehler und Ausgaben mehrerer paralleler Befehle in einer einzelnen Auflistung zu erfassen.

#### <a name="psactionretrycount-int32"></a>Psactionretrycount \<Int32\>

Versucht wiederholt, die Aktivität auszuführen, wenn der erste Versuch fehlschlägt. Beim Standardwert 0 wird keine Wiederholung durchgeführt.

#### <a name="psactionretryintervalsec-int32"></a>Psactionretryintervalsec \<Int32\>

Legt das Intervall zwischen Wiederholungsversuchen der Aktion in Sekunden fest. Beim Standardwert 0 wird die Aktion sofort wiederholt. Dieser Parameter ist nur gültig, wenn der psactionretrycount-Parameter auch im Befehl verwendet wird.

#### <a name="psactionrunningtimeoutsec-int32"></a>Psactionrunningtimeoutsec \<Int32\>

Legt fest, wie lange die Aktivität auf jedem Zielcomputer ausgeführt werden kann. Wenn die Aktivität vor Ablauf des Timeouts nicht beendet wird, generiert der Windows PowerShell-Workflow einen Fehler mit Abbruch und beendet die Verarbeitung des Workflows auf dem betroffenen Zielcomputer.

#### <a name="psallowredirection-boolean"></a>Psallowredirection \<Boolean\>

Der Wert $true ermöglicht die Umleitung der Verbindung zu den Ziel Computern.
Der Wert $false hat keine Auswirkung. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

Wenn Sie den psconnectionuri-Parameter verwenden, kann das Remote Ziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben. Standardmäßig umleitet Windows PowerShell Verbindungen nicht, Sie können jedoch den Parameter "psallowredirection" mit dem Wert "$true" verwenden, um die Umleitung der Verbindung zum Zielcomputer zuzulassen.

Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie die maximumconnectionredirectioncount-Eigenschaft der `$PSSessionOption` Preference-Variablen festlegen oder die maximumconnectionredirectioncount-Eigenschaft des Werts des ssessionoption-Parameters von Cmdlets, die eine Sitzung erstellen. Der Standardwert ist 5.

#### <a name="psapplicationname-string"></a>Psapplicationname \<String\>

Gibt das Anwendungs namens Segment des Verbindungs-URI an, der zum Herstellen der Verbindung mit den Ziel Computern verwendet wird. Verwenden Sie diesen Parameter, um den Anwendungsnamen anzugeben, wenn Sie nicht den ConnectionURI-Parameter im Befehl verwenden. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem Zielcomputer. Wenn diese Einstellungsvariable nicht definiert ist, ist der Standardwert „WSMan“. Dieser Wert ist für die meisten Verwendungsarten geeignet. Weitere Informationen finden Sie unter [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

Der WinRM-Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus. Der Wert dieses Parameters sollte mit dem Wert der URLPrefix-Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.

#### <a name="psauthentication-authenticationmechanism"></a>Psauthentication \<AuthenticationMechanism\>

Gibt den Mechanismus an, der zum Authentifizieren der Anmelde Informationen des Benutzers beim Herstellen einer Verbindung mit den Ziel Computern verwendet wird. Zu den gültigen Werten gehören Default, Basic, Credssp, Digest, Kerberos, Negotiate und NegotiateWithImplicitCredential. Der Standardwert ist Default. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

Informationen zu den Werten dieses Parameters finden Sie unter der Beschreibung der **System.Management.Automation.Runspaces.AuthenticationMechanism** -Enumeration in MSDN.

> [!WARNING]
> Die Credential Security Support Provider (CredSSP)-Authentifizierung, in der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle gedacht, die Authentifizierung bei mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remote-Netzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

#### <a name="pscertificatethumbprint-string"></a>Pscertifipethumbprint \<String\>

Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Geben Sie den Zertifikatfingerabdruck des Zertifikats ein. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.

Um ein Zertifikat abzurufen, verwenden Sie die Cmdlets " [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) " oder " [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) " im Windows PowerShell-Laufwerk "CERT:".

#### <a name="pscomputername-string"></a>PSComputerName \<String[]\>

Gibt die Zielcomputer an, auf denen die Aktivität ausgeführt wird. Die Standardeinstellung ist der lokale Computer. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen von mindestens einem Computer in eine durch Kommas getrennte Liste ein. Um den lokalen Computer anzugeben, geben Sie den Computernamen, „localhost“ oder einen Punkt (.) ein.

Um den lokalen Computer in den Wert des pscomputername-Parameters einzuschließen, öffnen Sie Windows PowerShell mit der Option "als Administrator ausführen".

Wenn dieser Parameter im Befehl weggelassen wird, oder wenn der Wert $NULL oder eine leere Zeichenfolge ist, ist das Workflow Ziel der lokale Computer, und Windows PowerShell-Remoting wird nicht verwendet, um den Befehl auszuführen.

Um eine IP-Adresse im Wert des Computername-Parameters zu verwenden, muss der Befehl den PSCredential-Parameter enthalten. Außerdem muss der Computer für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remotecomputers muss in der WinRM TrustedHosts-Liste auf dem lokalen Computer enthalten sein. Anweisungen zum Hinzufügen eines Computer namens zur Liste "Treuhänder Hosts" finden Sie unter "Vorgehensweise beim Hinzufügen eines Computers zur Liste vertrauenswürdiger Hosts" in [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).

#### <a name="psconfigurationname-string"></a>PSConfigurationName \<String\>

Gibt die Sitzungs Konfigurationen an, die zum Erstellen von Sitzungen auf den Ziel Computern verwendet werden. Geben Sie den Namen einer Sitzungs Konfiguration auf den Ziel Computern ein (nicht auf dem Computer, auf dem der Workflow ausgeführt wird). Der Standardwert ist Microsoft. PowerShell. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

#### <a name="psconnectionretrycount-uint"></a>PSConnectionRetryCount \<UInt\>

Gibt die maximale Anzahl von versuchen an, eine Verbindung mit den einzelnen Ziel Computern herzustellen, wenn beim ersten Verbindungsversuch ein Fehler auftritt. Geben Sie eine Zahl zwischen 1 und 4.294.967.295 (uint. MaxValue) ein. Der Standardwert 0 (null) stellt keine Wiederholungs Versuche dar.
Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

#### <a name="psconnectionretryintervalsec-uint"></a>Psconnectionretryintervalsec \<UInt\>

Gibt die Verzögerung zwischen Verbindungs Wiederholungs versuchen in Sekunden an. Der Standardwert ist 0 (null). Dieser Parameter ist nur gültig, wenn der Wert von psconnectionretrycount mindestens 1 ist. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

#### <a name="psconnectionuri-systemuri"></a>Psconnectionuri \<System.Uri\>

Gibt einen Uniform Resource Identifier (URI) an, der den Verbindungs Endpunkt für die Aktivität auf dem Bereitstellungs Zielcomputer definiert. Der URI muss vollqualifiziert sein. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

Das Format dieser Zeichenfolge lautet wie folgt:

```
<Transport>://<ComputerName>:<Port>/<ApplicationName>
```

Der Standardwert ist `http://localhost:5985/WSMAN`.

Wenn Sie keinen psconnectionuri angeben, können Sie die Parameter psusessl, pscomputername, psport und psapplicationname verwenden, um die psconnectionuri-Werte anzugeben.

Gültige Werte für das Transport-Segment des URI sind „HTTP“ und „HTTPS“. Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS. Um die Standardports für Windows PowerShell-Remoting zu verwenden, geben Sie Port 5985 für HTTP bzw. 5986 für HTTPS an.

#### <a name="pscredential-pscredential"></a>PSCredential \<PSCredential\>

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen der Aktivität auf dem Zielcomputer verfügt. Der Standardwert ist der aktuelle Benutzer. Dieser Parameter ist nur gültig, wenn der pscomputername-Parameter im Befehl enthalten ist. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

Geben Sie einen Benutzernamen ein, z. b. "USER01" oder "Domain01\User01", oder geben Sie eine Variable ein, die ein PSCredential-Objekt enthält, wie z. b. das Get-Credential Cmdlet zurückgibt. Wenn Sie nur einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

#### <a name="psdebug-psdatacollectiondebugrecord"></a>PSDebug \<PSDataCollection[DebugRecord]\>

Fügt Debugmeldungen aus der Aktivität der angegebenen Auflistung von debugdatensätzen hinzu, anstatt die Debugmeldungen in die Konsole oder den Wert der Debug-Eigenschaft des Workflow Auftrags zu schreiben. Sie können Debugmeldungen aus mehreren Aktivitäten demselben Auflistungsobjekt mit Debugdatensätzen hinzufügen.

Um diesen allgemeinen Aktivitäts Parameter zu verwenden, verwenden Sie das Cmdlet "New-Object", um ein psdatacollection-Objekt mit dem Typ "debugrecord" zu erstellen und das Objekt in einer Variablen zu speichern. Verwenden Sie dann die Variable als Wert des Parameters PSDebug einer oder mehrerer Aktivitäten, wie im folgenden Beispiel gezeigt.

```powershell
Workflow Test-Workflow
{
    $debugCollection = New-Object -Type `
    System.Management.Automation.PSDataCollection[System.Management.Automation.DebugRecord]
    InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    if ($debugCollection -like "Missing") { ...}
}
```

#### <a name="psdisableserialization-boolean"></a>Psdisableserialization \<Boolean\>

Weist die Aktivität an, „Live“-Objekte (nicht serialisierte Objekte) an den Workflow zurückzugeben.
Die resultierenden Objekte besitzen Methoden und Eigenschaften, aber sie können nicht gespeichert werden, wenn ein Prüfpunkt angenommen wird.

#### <a name="psdisableserializationpreference-boolean"></a>PSDisableSerializationPreference \<Boolean\>

Wendet die Entsprechung des psdisableserialization-Parameters auf den gesamten Workflow an, nicht nur auf die-Aktivität. Das Hinzufügen dieses Parameters wird in der Regel nicht empfohlen, da ein Workflow, der seine Objekte nicht serialisiert, nicht fortgesetzt oder beibehalten werden kann.

Gültige Werte:

- Vorgegebene Wenn der Parameter nicht angegeben wird und Sie den psdisableserialization-Parameter nicht zu einer Aktivität hinzugefügt haben, werden Objekte serialisiert.

- `$True`. Leitet alle Aktivitäten in einem Workflow an, (nicht serialisierte) „Live“-Objekte zurückzugeben. Die resultierenden Objekte besitzen Methoden und Eigenschaften, aber sie können nicht gespeichert werden, wenn ein Prüfpunkt angenommen wird.
- `$False`. Workflow-Objekte werden serialisiert.

#### <a name="pserror-psdatacollectionerrorrecord"></a>Pserror \<PSDataCollection[ErrorRecord]\>

Fügt der angegebenen Auflistung von Fehler Datensätzen Fehlermeldungen aus der-Aktivität hinzu, statt die Fehlermeldungen in die Konsole oder den Wert der Error-Eigenschaft des Workflow Auftrags zu schreiben. Sie können Fehlermeldungen aus mehreren Aktivitäten demselben Auflistungsobjekt mit Fehlerdatensätzen hinzufügen.

Um diesen allgemeinen Aktivitäts Parameter zu verwenden, verwenden `New-Object` Sie das Cmdlet, um ein psdatacollection-Objekt mit dem Typ ErrorRecord zu erstellen und das Objekt in einer Variablen zu speichern. Verwenden Sie dann die Variable als Wert des Parameters pserror einer oder mehrerer Aktivitäten, wie im folgenden Beispiel gezeigt.

```powershell
Workflow Test-Workflow
{
   $typeName = "System.Management.Automation.PSDataCollection"
   $typeName += '[System.Management.Automation.ErrorRecord]'
   $ec = New-Object $typeName
   InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSError $ec
   InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSError $ec
   if ($ec.Count -gt 2)
   {
      # Do Some Work.
   }
}
```

#### <a name="pspersist-boolean"></a>PSPersist \<Boolean\>

Nimmt einen Prüfpunkt nach der-Aktivität an. Dieser Prüfpunkt gilt zusätzlich zu allen Prüfpunkten, die im Workflow angegeben werden. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

Ein "Prüfpunkt" oder "Persistenzpunkt" ist eine Momentaufnahme des Workflow Status und der Daten, die erfasst werden, während der Workflow ausgeführt wird und in einem persistenten Speicher auf dem Datenträger gespeichert wird. Der Windows PowerShell-Workflow verwendet die gespeicherten Daten, um einen angehaltenen oder unterbrochenen Workflow vom letzten Persistenzpunkt wieder aufzunehmen, anstatt den Workflow neu zu starten.

Gültige Werte:

- Vorgegebene Wenn Sie diesen Parameter weglassen, werden keine Prüfpunkte hinzugefügt. Prüfpunkte werden basierend auf den Einstellungen für den Workflow übernommen.

- `$True`. Zeichnet einen Prüfpunkt auf, nachdem die Aktivität abgeschlossen ist.
  Dieser Prüfpunkt gilt zusätzlich zu allen Prüfpunkten, die im Workflow angegeben werden.

- `$False`. Es werden keine Prüfpunkte hinzugefügt. Prüfpunkte werden nur dann übernommen, wenn Sie im Workflow angegeben werden.

#### <a name="psport-int32"></a>Psport \<Int32\>

Gibt den Netzwerkport auf den Ziel Computern an. Die Standardports sind 5985 (der WinRM-Port für HTTP) und 5986 (der WinRM-Port für HTTPS). Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

Verwenden Sie den psport-Parameter nur, wenn dies erforderlich ist. Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird. Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird. Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren.

#### <a name="psprogress-psdatacollectionprogressrecord"></a>Psprogress \<PSDataCollection[ProgressRecord]\>

Fügt der angegebenen Auflistung von Statusdaten Sätzen Statusmeldungen aus der Aktivität hinzu, anstatt die Statusmeldungen in die Konsole oder den Wert der Status-Eigenschaft des Workflow Auftrags zu schreiben. Sie können Statusmeldungen aus mehreren Aktivitäten demselben Auflistungsobjekt mit Statusdatensätzen hinzufügen.

#### <a name="psprogressmessage-string"></a>Psprogressmessage \<String\>

Gibt eine Beschreibung der Aktivität an. Der Wert psprogressmessage wird in der Statusanzeige angezeigt, während der Workflow ausgeführt wird. Wenn Display Name auch im Befehl enthalten ist, wird der Inhalt der Statusanzeige im Format angezeigt \<DisplayName\> \<PSProgressMessage\> .

Dieser Parameter ist besonders nützlich zum Identifizieren von Aktivitäten in einem Foreach-parallel-Skriptblock. Ohne diese Nachricht werden Aktivitäten in allen parallelen Teilstrukturen mit demselben Namen identifiziert.

#### <a name="psremotingbehavior-remotingbehavior"></a>Psremotingbehavior \<RemotingBehavior\>

Gibt an, wie das Remoting verwaltet wird, wenn die Aktivität auf Zielcomputern ausgeführt wird.
PowerShell ist die Standardeinstellung.

Gültige Werte sind:

- Keine: die Aktivität wird nicht auf Remote Computern ausgeführt.

- PowerShell: Windows PowerShell-Remoting wird zum Ausführen der Aktivität auf Ziel Computern verwendet.

- Custom: die-Aktivität unterstützt den eigenen Remoting-Typ. Dieser Wert ist gültig, wenn das Cmdlet, das als Aktivität implementiert wird, den Wert des remotingcapability-Attributs auf supportedbycommand festlegt und der Befehl den Computername-Parameter enthält.

#### <a name="psrequiredmodules-string"></a>PSRequiredModules \<String[]\>

Importiert die angegebenen Module vor dem Ausführen des Befehls. Geben Sie die Modulnamen ein. Die Module müssen auf dem Bereitstellungs Zielcomputer installiert sein.

Module, die in einem in der psmodulepath-Umgebungsvariablen angegebenen Pfad installiert werden, werden automatisch bei der ersten Verwendung eines beliebigen Befehls im Modul importiert.
Verwenden Sie diesen Parameter, um Module zu importieren, die sich nicht an einem psmodulepath-Speicherort befinden.

Da jede Aktivität in einem Workflow in einer eigenen Sitzung ausgeführt wird, importiert ein Import-Module-Befehl nur ein Modul in der Sitzung, in der er ausgeführt wird. Er importiert das Modul nicht in Sitzungen, in denen andere Aktivitäten ausgeführt werden.

#### <a name="pssessionoption-pssessionoption"></a>PSSessionOption \<PSSessionOption\>

Legt Erweiterte Optionen für die Sitzungen auf den Ziel Computern fest. Geben Sie ein pssessionoption-Objekt ein, z. b. ein Objekt, das Sie mit dem Cmdlet "New-PSSessionOption" erstellen. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

Die Standardwerte für die Sitzungs Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt. Andernfalls verwendet die Sitzung die Werte, die in der Sitzungs Konfiguration angegeben sind.

Eine Beschreibung der Sitzungs Optionen, einschließlich der Standardwerte, finden Sie im Hilfethema für das New-PSSessionOption Cmdlet " [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)".

Weitere Informationen zur $PSSessionOption Preference-Variablen finden Sie unter [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

#### <a name="psusessl-boolean"></a>Psusessl \<Boolean\>

Der Wert $true verwendet das Secure Sockets Layer (SSL)-Protokoll, um eine Verbindung mit dem Zielcomputer herzustellen. Standardmäßig wird SSL nicht verwendet. Der Wert $false hat keine Auswirkung. Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.

WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden. UseSSL bietet zusätzlichen Schutz, indem die Daten über HTTPS, anstelle von HTTP gesendet werden. Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port für den Befehl nicht verfügbar ist, tritt ein Fehler beim Befehl auf.

#### <a name="psverbose-psdatacollectionverboserecord"></a>Psverbose \<PSDataCollection[VerboseRecord]\>

Fügt der angegebenen ausführlichen Daten Satz Auflistung ausführliche Meldungen aus der-Aktivität hinzu, anstatt die ausführlichen Meldungen in die Konsole oder den Wert der ausführliche-Eigenschaft des Workflow Auftrags zu schreiben. Sie können ausführliche Meldungen aus mehreren Aktivitäten demselben Auflistungsobjekt mit ausführlichen Datensätzen hinzufügen.

#### <a name="pswarning-psdatacollectionwarningrecord"></a>Pswarning \<PSDataCollection[WarningRecord]\>

Fügt der angegebenen Auflistung von Warnungs Datensätzen Warnmeldungen aus der-Aktivität hinzu, anstatt die Warnmeldungen in die Konsole oder den Wert der Warning-Eigenschaft des Workflow Auftrags zu schreiben. Sie können Warnungen aus mehreren Aktivitäten demselben Auflistungsobjekt mit Warnungsdatensätzen hinzufügen.

#### <a name="result"></a>Ergebnis

Dieser Parameter ist nur in XAML-Workflows gültig.

#### <a name="usedefaultinput-boolean"></a>Allgemeine usedefaultinput \<Boolean\>

Akzeptiert alle Workfloweingaben als Eingabe für die Aktivität nach Wert.

Beispielsweise verwendet die Get-Process-Aktivität im folgenden Beispielworkflow den allgemeine UseDefaultInput-Aktivitätsparameter als Eingabe, die an den Workflow übergeben wird. Beim Ausführen des Workflows mit der Eingabe wird die Eingabe von der Aktivität verwendet.

```powershell
workflow Test-Workflow
{
    Get-Service -UseDefaultInput $True
}

PS C:> Test-Workflow -InputObject WinRm
```

```output
Status   Name        DisplayName                            PSComputerName
------   ----        -----------                            --------------
Running  winrm       Windows Remote Management (WS-Manag... localhost
```

#### <a name="verbose-switchparameter"></a>Ausführliche \<SwitchParameter\>

Zeigt ausführliche Informationen zu dem vom Befehl ausgeführten Vorgang an.
Diese Informationen ähneln den Informationen in einer Ablauf Verfolgung oder einem Transaktionsprotokoll.
Der Verbose-Parameter überschreibt den Wert der $VerbosePreference-Variablen für den aktuellen Befehl. Dieser Parameter funktioniert nur, wenn der Befehl eine ausführliche Nachricht generiert. Bei diesem Parameter handelt es sich auch um einen allgemeinen Windows PowerShell-Parameter.

#### <a name="warningaction-actionpreference"></a>Allgemeinen WarningAction \<ActionPreference\>

Bestimmt, wie die Aktivität auf eine Warnung antwortet. "Continue" ist der Standardwert. Der WarningAction-Parameter überschreibt den Wert der $WarningPreference-Variablen für den aktuellen Befehl. Dieser Parameter funktioniert nur, wenn der Befehl eine Warnmeldung generiert. Bei diesem Parameter handelt es sich auch um einen allgemeinen Windows PowerShell-Parameter.

Gültige Werte:

- SilentlyContinue. Unterdrückt die Warnmeldung und setzt die Ausführung des Befehls fort.

- Auch. Zeigt die Warnmeldung an und setzt die Ausführung des Befehls fort.
  "Continue" ist der Standardwert.

- Digte. Zeigt die Warnmeldung an und fordert Sie zur Bestätigung auf, bevor die Ausführung fortgesetzt wird. Dieser Wert wird nur selten verwendet.

- Beenden Zeigt die Warnmeldung an und beendet die Ausführung des Befehls.

> [!NOTE]
> Der WarningAction-Parameter überschreibt den Wert der $WarningAction Preference-Variablen nicht, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.

### <a name="examples"></a>BEISPIELE

Die allgemeinen Aktivitätsparameter sind äußerst nützlich. Beispielsweise können Sie den pscomputername-Parameter verwenden, um bestimmte Aktivitäten nur für eine Teilmenge der Zielcomputer auszuführen.

Sie können auch die Parameter psconnectionretrycount und psconnectionretryintervalsec verwenden, um die Wiederholungswerte für bestimmte Aktivitäten anzupassen.

Im folgenden Beispiel wird gezeigt, wie die allgemeinen Parameter der pscomputername-Aktivität verwendet werden, um eine Get-EventLog Aktivität nur auf Computern auszuführen, die eine bestimmte Domäne haben.

```powershell
Workflow Test-Workflow
{
    $UserDomain = Get-Content -Path '.\UserComputers.txt'
    $Log = (Get-EventLog -LogName "Windows PowerShell" `
      -PSComputerName $UserDomain)

    if ($Log)
    {
        # Do Work Here.
    }
}
```

<!--
# KEYWORDS
[about_Activity_Common_Parameters](about_Activity_Common_Parameters.md)
[about_Activity_Parameters](about_Activity_Parameters.md)
[about_ActivityParameters]()about_ActivityParameters.md) -->

## <a name="see-also"></a>SIEHE AUCH

[about_Workflows](about_workflows.md) 
 [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)
