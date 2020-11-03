---
description: WSMan
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_wsman_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: WS-Management-Anbieter
ms.openlocfilehash: 011383112d453a4fa88745c69b52e432709aa9d3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221028"
---
# <a name="wsman-provider"></a>WS-Management-Anbieter

## <a name="provider-name"></a>Anbietername

WSMan

## <a name="drives"></a>Laufwerke

`WSMan:`

## <a name="short-description"></a>Kurze Beschreibung

Bietet Zugriff auf Web Services for Management (WS-Management)-Konfigurationsinformationen.

## <a name="detailed-description"></a>Detaillierte Beschreibung

Mit dem **WSMAN** -Anbieter für PowerShell können Sie WS-Management Konfigurationsdaten auf lokalen Computern oder Remote Computern hinzufügen, ändern, löschen und löschen.

Der **WSMAN** -Anbieter macht ein PowerShell-Laufwerk mit einer Verzeichnisstruktur verfügbar, die einer logischen Gruppierung von WS-Management Konfigurationseinstellungen entspricht. Diese Gruppierungen werden als Container bezeichnet.

Ab Windows PowerShell 3,0 wurde der **WSMAN** -Anbieter aktualisiert, um neue Eigenschaften für Sitzungs Konfigurationen zu unterstützen, z. b. **outputbufferingmode**. Die Sitzungs Konfigurationen werden als Elemente im Plug-in-Verzeichnis des `WSMan:` Laufwerks angezeigt, und die Eigenschaften werden als Elemente in jeder Sitzungs Konfiguration angezeigt.

Der **WSMAN** -Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)

> [!NOTE]
> Sie können Befehle im Laufwerk verwenden `WSMan:` , um die Werte der neuen Eigenschaften zu ändern. Allerdings können Sie das `WSMan:` Laufwerk in PowerShell 2,0 nicht verwenden, um die in Windows PowerShell 3,0 eingeführten Eigenschaften zu ändern.
> Obwohl kein Fehler generiert wird, sind die Befehle nicht wirksam, um diese Einstellungen zu ändern. verwenden Sie das **WSMAN** -Laufwerk in Windows PowerShell 3,0.

### <a name="organization-of-the-wsman-drive"></a>Organisation des WSMAN:-Laufwerks

- **Client** : Sie können verschiedene Aspekte des WS-Management Clients konfigurieren. Die Konfigurationsinformationen werden in der Registrierung gespeichert.

- **Dienst** : Sie können verschiedene Aspekte des WS-Management Dienstanbieter konfigurieren.
  Die Konfigurationsinformationen werden in der Registrierung gespeichert.
  > [!NOTE]
  > Die Dienstkonfiguration wird manchmal als Serverkonfiguration bezeichnet.

- **Shell** : Sie können verschiedene Aspekte der WS-Management Shell konfigurieren, z. b. die Einstellung zum Zulassen von remoteshellzugriff ( **allowremoteshellaccess** ) und die maximal zulässige Anzahl von gleichzeitigen Benutzern ( **maxconcurrentusers** ).

- **Listener** : Sie können einen Listener erstellen und konfigurieren. Ein Listener ist ein Verwaltungsdienst, der das WS-Verwaltungsprotokoll zum Senden und Empfangen von Nachrichten implementiert.

- **Plug-in: Plug** -ins werden geladen und vom WS-Management-Dienst verwendet, um verschiedene Funktionen bereitzustellen. PowerShell bietet standardmäßig drei Plug-ins:
  - Das Ereignis Weiterleitungs-Plug-in.
  - Das Microsoft. PowerShell-Plug-in.
  - Das Plug-in für den Windows-Verwaltungsinstrumentation (WMI)-Anbieter.
  Diese drei Plug-Ins unterstützen Ereignis Weiterleitung, Konfiguration und WMI-Zugriff.

- **ClientCertificate** : Sie können ein Client Zertifikat erstellen und konfigurieren.
  Ein Clientzertifikat wird verwendet, wenn der WS-Verwaltungsclient zur Verwendung der Zertifikatsauthentifizierung konfiguriert ist.

### <a name="directory-hierarchy-of-the-wsman-provider"></a>Verzeichnishierarchie des WSMan-Anbieters

Die Verzeichnishierarchie des WSMAN-Anbieters für den lokalen Computer lautet wie folgt.

```
WSMan:\localhost
--- Client
--- Service
--- Shell
--- Listener
------ <Specific_Listener>
--- Plugin
------ Event Forwarding Plugin
--------- InitializationParameters
--------- Resources
------------ Security
------ Microsoft.Powershell
--------- InitializationParameters
--------- Resources
------------ Security
------ WMI Provider
--------- InitializationParameters
--------- Resources
------------ Security
--- ClientCertificate
```

Die Verzeichnishierarchie des WSMan-Anbieters für einen Remotecomputer ist identisch mit der für einen lokalen Computer. Wenn Sie jedoch auf die Konfigurationseinstellungen eines Remote Computers zugreifen möchten, müssen Sie mithilfe von [Connect-WSMAN](xref:Microsoft.WSMan.Management.Connect-WSMan)eine Verbindung mit dem Remote Computer herstellen. Sobald eine Verbindung mit einem Remotecomputer hergestellt wurde, wird der Name des Remotecomputers beim Anbieter angezeigt.

```
WSMan:\<Remote_Computer_Name>
```

## <a name="navigating-the-wsman-drive"></a>Navigieren im WSMAN:-Laufwerk

Dieser Befehl verwendet das `Set-Location` Cmdlet, um den aktuellen Speicherort auf das Laufwerk zu ändern `WSMan:` .

```powershell
Set-Location WSMan:
```

Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein. Geben Sie z. b. ein.

```powershell
Set-Location C:
```

### <a name="navigating-to-a-remote-system-store-location"></a>Navigieren zu einem Remote System-Speicherort

Dieser Befehl verwendet den- `Set-Location` Befehl, um den aktuellen Speicherort in den Stammverzeichnis des Remote Systemspeicher-Speicher Orts zu ändern. Verwenden Sie einen umgekehrten Schrägstrich `\` oder einen Schrägstrich `/` , um eine Ebene des `WSMan:` Laufwerks anzugeben.

```powershell
Set-Location -Path  WSMan:\SERVER01
```

> [!NOTE]
> Der obige Befehl geht davon aus, dass bereits eine Verbindung mit dem Remotesystem vorhanden ist.

## <a name="displaying-the-contents-of-the-wsman-drive"></a>Anzeigen des Inhalts des WSMAN:-Laufwerks

Dieser Befehl verwendet das `Get-Childitem` Cmdlet, um die WS-Management Stores am localhost-Speicherort anzuzeigen.

```powershell
Get-ChildItem -path WSMan:\Localhost
```

Wenn Sie sich auf dem `WSMan:` Laufwerk befinden, können Sie den Namen des Laufwerks weglassen.

Dieser Befehl verwendet das `Get-Childitem` Cmdlet, um die WS-Management Stores im Speicherort des Remote Computers "Server01" anzuzeigen.

```powershell
Get-ChildItem -path WSMan:\SERVER01
```

> [!NOTE]
> Der obige Befehl geht davon aus, dass bereits eine Verbindung mit dem Remotesystem vorhanden ist.

## <a name="setting-the-value-of-items-in-the--wsman-drive"></a>Festlegen des Werts von Elementen im WSMAN:-Laufwerk

Sie können das `Set-Item` Cmdlet verwenden, um die Konfigurationseinstellungen im `WSMAN` Laufwerk zu ändern. Im folgenden Beispiel wird der Wert für " **Treuhänder Hosts** " so festgelegt, dass alle Hosts mit dem Suffix "contoso.com" akzeptiert werden.

```powershell
# You do not need to specify the -Path parameter name when using Set-Item.
PS WSMAN:\localhost\Client> Set-Item .\TrustedHosts -Value "*.contoso.com"
```

Das `Set-Item` Cmdlet unterstützt einen zusätzlichen Parameter `-Concatenate` , der einen Wert anfügt, anstatt ihn zu ändern. Im folgenden Beispiel wird der neue Wert "*. domain2.com" an den alten Wert angehängt, der in gespeichert ist. `TrustedHost:`

```powershell
Set-Item WSMAN:\localhost\Client\TrustedHosts *.domain2.com -Concatenate
```

## <a name="creating-items-in-the-wsman-drive"></a>Erstellen von Elementen im WSMAN:-Laufwerk

### <a name="creating-a-new-listener"></a>Erstellen eines neuen Listener

Das- `New-Item` Cmdlet erstellt Elemente innerhalb eines Anbieter Laufwerks. Jeder Anbieter verfügt über verschiedene Elementtypen, die Sie erstellen können. Auf dem `WSMAN:` Laufwerk können Sie Listener erstellen *,* die Sie konfigurieren, um Remote Anforderungen zu empfangen und darauf zu reagieren. Mit dem folgenden Befehl wird ein neuer http-Listener mit dem- `New-Item` Cmdlet erstellt.

```powershell
New-Item -Path WSMan:\localhost\Listener -Address * -Transport HTTP -force
```

### <a name="creating-a-new-plug-in"></a>Erstellen eines neuen Plug-ins

Dieser Befehl erstellt (registriert) ein Plug-In für den WS-Verwaltungsdienst.

```powershell
New-Item -Path WSMan:\localhost\Plugin `
         -Plugin TestPlugin `
         -FileName %systemroot%\system32\WsmWmiPl.dll `
         -Resource http://schemas.dmtf.org/wbem/wscim/2/cim-schema `
         -SDKVersion 1 `
         -Capability "Get","Put","Invoke","Enumerate" `
         -XMLRenderingType text
```

### <a name="creating-a-new-resource-entry"></a>Erstellen eines neuen Ressourcen Eintrags

Dieser Befehl erstellt einen Ressourcen Eintrag im Ressourcenverzeichnis von testplugin. Bei diesem Befehl wird davon ausgegangen, dass ein testplugin mithilfe eines separaten Befehls erstellt wurde.

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\Resources `
         -ResourceUri http://schemas.dmtf.org/wbem/wscim/3/cim-schema `
         -Capability "Enumerate"

```

### <a name="creating-a-new-security-entry-for-a-resource"></a>Erstellen eines neuen Sicherheits Eintrags für eine Ressource

Dieser Befehl erstellt einen Eintrag für die Sicherheit im Verzeichnis "Security" von Resource_5967683 (eine bestimmte Ressource). Bei diesem Befehl wird davon ausgegangen, dass der Ressourcen Eintrag mit einem separaten Befehl erstellt wurde.

```powershell
$path = "WSMan:\localhost\Plugin\TestPlugin\Resources\Resource_5967683"
New-Item -Path $path\Security `
         -Sddl "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GWGX;;;WD)"
```

### <a name="creating-a-new-client-certificate"></a>Erstellen eines neuen Client Zertifikats

Mit diesem Befehl wird der **ClientCertificate** -Eintrag erstellt, der vom WS-Management-Client verwendet werden kann. Das neue **ClientCertificate** wird unter dem Verzeichnis " **ClientCertificate** " als "ClientCertificate_1234567890" angezeigt. Alle Parameter müssen angegeben werden. Der **Aussteller** muss den Fingerabdruck des Aussteller Zertifikats aufweisen.

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* `
         -Credential $cred;
```

### <a name="creating-a-new-initialization-parameter"></a>Erstellen eines neuen Initialisierungs Parameters

Dieser Befehl erstellt im Verzeichnis "initializationparameters" einen Initialisierungs Parameter mit dem Namen "testparametername". Bei diesem Befehl wird davon ausgegangen, dass "testplugin" mit einem separaten Befehl erstellt wurde.

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\InitializationParameters `
         -ParamName testparametername `
         -ParamValue testparametervalue
```

## <a name="dynamic-parameters"></a>Dynamische Parameter

Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.

### <a name="address-string"></a>Adresse \<String\>

Gibt die Adresse an, für die der Listener erstellt wurde. Der Wert kann in folgenden Formen vorliegen:

- Die Literalzeichenfolge "*". (Mit dem Platzhalter Zeichen ( `*` ) werden alle IP-Adressen auf allen Netzwerkadaptern an den Befehl gebunden.)
- Die Literalzeichenfolge "IP:", gefolgt von einer gültigen IP-Adresse im IPv4-gepunkteten Dezimal Format oder im IPv6-Format mit geklontem hexadezimal.
- Die Literalzeichenfolge "Mac:" gefolgt von der Mac-Adresse eines Adapters.
  Beispiel: Mac: 32-a3-58 -90-be-cc.

> [!NOTE]
> Der Wert der Adresse wird beim Erstellen eines Listeners festgelegt.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="capability-enumeration"></a>Re \<Enumeration\>

Beim Arbeiten mit *Plug-ins* gibt dieser Parameter einen Vorgang an, der für diesen Uniform Resource Identifier (URI) unterstützt wird. Sie müssen einen Eintrag für jede Art von Vorgang erstellen, die der URI unterstützt. Sie können beliebige gültige Attribute für einen bestimmten Vorgang angeben, wenn der Vorgang dies unterstützt.

Zu diesen Attributen gehören **SupportsFiltering** und **supportsfragment**.

- **Create** : Erstellungs Vorgänge werden für den URI unterstützt.
  - Das **supportfragment**  -Attribut wird verwendet, wenn der Create-Vorgang das Konzept unterstützt.
  - Das **supportfiltering** -Attribut ist für Erstellungs Vorgänge ungültig und sollte auf "false" festgelegt werden.
  > [!NOTE]
  > Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.
- **Delete** : Löschvorgänge werden für den URI unterstützt.
  - Das **supportfragment** -Attribut wird verwendet, wenn der DELETE-Vorgang das Konzept unterstützt.
  - Das **supportfiltering** -Attribut ist für Löschvorgänge ungültig und sollte auf "false" festgelegt werden.
  > [!NOTE]
  > Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.
- **Enumerate** : aufzählenden Vorgänge werden für den URI unterstützt.
  - Das **supportfragment** -Attribut wird für Enumerate-Vorgänge nicht unterstützt und sollte auf false festgelegt werden.
  - Das **supportfiltering** -Attribut ist gültig, und wenn das Plug-in das Filtern unterstützt, sollte dieses Attribut auf "true" festgelegt werden.
  > [!NOTE]
  > Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.
- **Get** : Get-Vorgänge werden für den URI unterstützt.
  - Das **supportfragment** -Attribut wird verwendet, wenn der Get-Vorgang das Konzept unterstützt.
  - Das **supportfiltering** -Attribut ist für Get-Vorgänge ungültig und sollte auf "false" festgelegt werden.
  > [!NOTE]
  > Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.
- **Aufrufen** : Aufruf Vorgänge werden für den URI unterstützt.
  - Das **supportfragment** -Attribut wird für Aufruf Vorgänge nicht unterstützt und sollte auf false festgelegt werden.
  - Das **supportfiltering** -Attribut ist ungültig und sollte auf "false" festgelegt werden.
  > [!NOTE]
  > Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.
- **Put** : Put-Vorgänge werden für den URI unterstützt.
  - Das **supportfragment** -Attribut wird verwendet, wenn der Put-Vorgang das Konzept unterstützt.
  - Das **supportfiltering** -Attribut ist für Put-Vorgänge ungültig und sollte auf "false" festgelegt werden.
  > [!NOTE]
  > Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.
- **Abonnieren** : abonnieren-Vorgänge werden für den URI unterstützt.
  - Das **supportfragment** -Attribut wird für abonnieren-Vorgänge nicht unterstützt und sollte auf false festgelegt werden.
  - Das **supportfiltering** -Attribut ist für subscribe-Vorgänge ungültig und sollte auf "false" festgelegt werden.
  > [!NOTE]
  > Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.
- **Shell** : Shellvorgänge werden für den URI unterstützt.
  - Das **supportfragment** -Attribut wird für Shellvorgänge nicht unterstützt und muss auf "false" festgelegt werden.
  - Das **supportfiltering** -Attribut ist für Shellvorgänge nicht gültig und sollte auf "false" festgelegt werden.
  > [!NOTE]
  > Dieser Vorgang ist für einen URI ungültig, wenn ein anderer Vorgang ebenfalls unterstützt wird.
  > [!NOTE]
  > Wenn ein Shell-Vorgang für eine URI konfiguriert ist, werden Get-, Put-, Create-, Delete-, Invoke- und Enumerate-Vorgänge intern innerhalb des WS-Verwaltungsdiensts (WinRM) zum Verwalten von Shells verarbeitet. Daher kann das Plug-In die Vorgänge nicht verarbeiten.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="certificatethumbprint-string"></a>CertificateThumbprint \<String\>

Gibt den Fingerabdruck des Dienstzertifikats an.

Dieser Wert repräsentiert die Zeichenfolge von zweistelligen Hexadezimalwerten im Fingerabdruckfeld des Zertifikats. Es gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet und nicht mit Domänenkonten verwendet werden. Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie das- `Get-Item` `Get-ChildItem` Cmdlet oder das-Cmdlet auf dem PowerShell- `Cert:` Laufwerk.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="enabled-boolean"></a>Wodurch \<Boolean\>

Gibt an, ob der Listener aktiviert oder deaktiviert ist. Der Standardwert ist True.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="filename-plugin-string"></a>Dateiname (Plugin) \<String\>

Gibt den Dateinamen des Vorgangs-Plug-ins an. Alle Umgebungsvariablen, die in diesen Eintrag eingefügt werden, werden im Kontext des Benutzers erweitert, wenn eine Anforderung empfangen wird. Da jeder Benutzer eine andere Version der gleichen Umgebungsvariablen aufweisen könnte, kann jeder Benutzer über ein anderes Plug-in verfügen. Dieser Eintrag darf nicht leer sein und muss auf ein gültiges Plug-in zeigen.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="hostname-string"></a>Hostname \<String\>

Gibt den Hostnamen des Computers an, auf dem der WS-Management-Dienst (WinRM) ausgeführt wird.

Bei diesem Wert muss es sich um einen vollständig qualifizierten Domänennamen, eine IPv4- oder IPv6-Literalzeichenfolge oder ein Platzhalterzeichen handeln.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="issuer-string"></a>Stellers \<String\>

Gibt den Namen der Zertifizierungsstelle an, die das Zertifikat ausgestellt hat.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="plugin--ws-management-plug-ins-are-native-dynamic-link-libraries-dlls"></a>\<\>Plug-Ins für Plug-ins WS-Management sind native Dynamic Link Libraries (DLLs)

das Plug-in und erweitert die Funktionalität von WS-Management. Die WSW-Management-Plug-in-API stellt Funktionen bereit, mit denen ein Benutzer Plug-ins schreiben kann, indem er bestimmte APIs für unterstützte Ressourcen-URIs und-Vorgänge implementiert. Nachdem die Plug-Ins entweder für den WS-Verwaltungsdienst (WinRM) oder für Internet Information Services (IIS) konfiguriert wurden, werden die Plug-Ins in den WS-Management-Host oder in den IIS-Host geladen. Remoteanforderungen werden an diese Plug-In-Einstiegspunkte für Operationen weitergeleitet.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="port-unsigned-short-integer"></a>Port \<Unsigned Short Integer\>

Gibt den TCP-Port an, für den der Listener erstellt wird. Sie können einen beliebigen Wert zwischen 1 und 65535 angeben.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a>Ressource \<String\>

Gibt einen Endpunkt an, der einen unterschiedlichen Typ von Verwaltungsvorgang oder Wert darstellt. Ein Dienst macht eine oder mehrere Ressourcen verfügbar, und einige Ressourcen können mehr als eine Instanz aufweisen. Eine Management-Ressource ist vergleichbar mit einer WMI-Klasse oder einer Datenbanktabelle, und eine Instanz ist vergleichbar mit einer Instanz der Klasse oder einer Zeile in der Tabelle. Beispielsweise stellt die **Win32_LogicalDisk** -Klasse eine Ressource dar. `Win32_LogicalDisk="C:\\"` ist eine bestimmte Instanz der Ressource.

Ein Uniform Resource Identifier (URI) enthält ein Präfix und einen Pfad zu einer Ressource.
Beispiel:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a>Ressource \<String\>

Gibt den Uniform Resource Identifier (URI) an, der eine bestimmte Art von Ressource identifiziert, z. B. ein Datenträger oder ein Prozess auf einem Computer.

Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource. Beispiel:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sdkversion-string"></a>SDKVersion \<String\>

Gibt die Version des WS-Management-Plug-In-SDKs an. Der einzige gültige Wert ist .
1.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="subject-string"></a>Betreff \<String\>

Gibt die Entität an, die durch das Zertifikat identifiziert wird.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="transport-string"></a>Personen \<String\>

Legt den Transport zum Senden und Empfangen von WS-Management-Protokollanforderungen und -antworten fest. Der Wert muss entweder HTTP oder HTTPS sein.

Hinweis: der Transport Wert wird festgelegt, wenn ein Listener erstellt wird.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="uri-string"></a>RT \<String\>

Gibt den URI an, für den der Zugriff basierend auf dem Wert des Parameters Sddl gewährt wird.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="urlprefix-string"></a>URLPrefix \<String\>

Ein URL-Präfix für das Akzeptieren von HTTP- oder HTTPS-Anforderungen. Dabei handelt es sich um eine Zeichenfolge, die nur die Zeichen, `[a-z]` `[A-Z]` , `[9-0]` , Unterstriche ( `_` ) und umgekehrten Schrägstrich ( `/` ) enthält. Die Zeichenfolge darf nicht mit einem umgekehrten Schrägstrich () beginnen oder mit einem umgekehrten Schrägstrich enden `/` . Wenn der Computername beispielsweise "samplecomputer" ist, würde der WS-Management Client `http://SampleMachine/URLPrefix` in der Zieladresse angeben.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="value-string"></a>Wert \<String\>

Gibt den Wert eines Initialisierungsparameters an, einem Plug-In-spezifischen Wert, der verwendet wird, um Konfigurationsoptionen anzugeben.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="xmlrenderingtype-string"></a>Xmlrenderingtype \<String\>

Gibt das Format an, in dem XML über das **WSMAN_DATA** Objekt an Plug-ins übermittelt wird. Die folgenden sind Werte gültig:

- Text: eingehende XML-Daten sind in einer **WSMAN_DATA_TYPE_TEXT** -Struktur enthalten, die den XML-Code als **pcwstr** -Arbeitsspeicher Puffer darstellt.
- XmlReader: eingehende XML-Daten sind in einer **WSMAN_DATA_TYPE_WS_XML_READER** -Struktur enthalten, die den XML-Code als **XmlReader** -Objekt darstellt, das in der Header Datei "Webservices. h" definiert ist.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a>Verwenden der Pipeline

Anbieter-Cmdlets akzeptieren Pipeline Eingaben. Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.
Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.

## <a name="getting-help"></a>Hilfe

Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.

Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den `-Path` -Parameter von [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) zum Angeben eines Dateisystem Laufwerks.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path wsman:
```

## <a name="see-also"></a>Weitere Informationen:

[about_Providers](../../Microsoft.PowerShell.Core/About/about_Providers.md)
