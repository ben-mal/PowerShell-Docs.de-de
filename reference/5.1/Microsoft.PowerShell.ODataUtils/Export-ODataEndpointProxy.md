---
external help file: Microsoft.PowerShell.ODataUtils-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.ODataUtils
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.odatautils/export-odataendpointproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ODataEndpointProxy
ms.openlocfilehash: 7550e2df319e5f195e65609ae29ebb00830ec8d2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214292"
---
# Export-ODataEndpointProxy

## ZUSAMMENFASSUNG
Generiert ein Modul, das Cmdlets zum Verwalten eines odata-Endpunkts enthält.

## SYNTAX

```
Export-ODataEndpointProxy [-Uri] <String> [-OutputModule] <String> [[-MetadataUri] <String>]
 [[-Credential] <PSCredential>] [[-CreateRequestMethod] <String>] [[-UpdateRequestMethod] <String>]
 [[-CmdletAdapter] <String>] [[-ResourceNameMapping] <Hashtable>] [-Force] [[-CustomData] <Hashtable>]
 [-AllowClobber] [-AllowUnsecureConnection] [[-Headers] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das `Export-ODataEndpointProxy` Cmdlet verwendet die Metadaten eines odata-Endpunkts, um ein Modul zu generieren, das Cmdlets enthält, die Sie zum Verwalten dieses odata-Endpunkts verwenden können. Das Modul basiert auf cdxml. Nachdem dieses Cmdlet das Modul generiert hat, speichert es das Modul in dem Pfad und dem Dateinamen, die durch den Parameter **outputmodule** angegeben werden.

`Export-ODataEndpointProxy` generiert Cmdlets für Erstellungs-, Lese-, Aktualisierungs-und Löschvorgänge (CRUD), nicht-CRUD-Aktionen und Zuordnungs Manipulationen.

`Export-ODataEndpointProxy` generiert eine cdxml-Datei pro Endpunkt Ressource. Sie können diese cdxml-Dateien bearbeiten, nachdem das Modul generiert wurde. Wenn Sie z. b. die Substantiv-oder Verb Namen der Cmdlets so ändern möchten, dass Sie mit den Benennungs Richtlinien für Windows PowerShell-Cmdlets übereinstimmen, können Sie die Datei ändern.

Jedes Cmdlet in einem generierten Modul muss einen **ConnectionUri** -Parameter enthalten, um eine Verbindung mit dem Endpunkt herzustellen, den das Modul verwaltet.

## BEISPIELE

### Beispiel 1: Generieren eines Moduls zum Verwalten eines Einzelhandels-Webdienst-Endpunkts

```powershell
PS C:\> Export-ODataEndpointProxy -Uri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc' -MetadataUri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc/$metadata' -AllowUnsecureConnection -OutputModule 'C:\Users\user\GeneratedScript.psm1' -ResourceNameMapping @{Products = 'Merchandise'}
```

Dieser Befehl generiert ein Modul zum Verwalten eines Einzelhandels Dienst-Endpunkts. Der-Befehl gibt den URI des Endpunkts und den URI der Endpunkt Metadaten an. Der Befehl stellt außerdem einen Ausgabepfad und Skript Modulnamen als Wert für den Parameter **outputmodule** bereit. Für den Wert des **resourcenamemapping** -Parameters bietet der Befehl eine Hash Tabelle, die den Ressourcen Sammlungsnamen dem gewünschten Substantiv für das Cmdlet-Set zuordnet. In diesem Beispiel ist Products der Name der Ressourcensammlung, und die **Ware** ist das Substantiv. Um Verbindungen mit nicht-SSL-Sites zuzulassen, fügen Sie http anstelle von HTTPS den Parameter " **zufüge** Anforderung" hinzu.

## PARAMETERS

### -Allowclobber

Gibt an, dass dieses Cmdlet ein vorhandenes Modul ersetzt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -"-Zugewunsecureconnection"

Gibt an, dass dieses Modul eine Verbindung mit URIs herstellen kann, die nicht SSL-geschützt sind. Das Modul kann neben HTTPS-Websites auch HTTP-Websites verwalten.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Cmdletadapter

Gibt den Cmdlet-Adapter an. Die zulässigen Werte für diesen Parameter sind: odataadapter und networkcontrolleradapter.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ODataAdapter, NetworkControllerAdapter, ODataV4Adapter

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -"-Kreaterequestmethod"

Gibt die Anforderungs Methode an. Die zulässigen Werte für diesen Parameter lauten: Put, Post und Patch.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das Zugriff auf den odata-Endpunkt hat. Der Standardwert ist der aktuelle Benutzer. Wenn auf einem Remote Computer Windows Vista oder ein späteres Release des Windows-Betriebssystems ausgeführt wird, werden Sie vom Cmdlet zur Eingabe von Anmelde Informationen aufgefordert.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomData

Gibt eine Hash Tabelle mit benutzerdefinierten Daten an.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Gibt an, dass dieses Cmdlet ein vorhandenes generiertes Modul mit demselben Namen in einem vorhandenen Ordner überschreibt `Modules` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Header

Gibt die Header der Webanforderung an. Geben Sie eine Hashtabelle oder ein Wörterbuch ein.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MetadataUri

Gibt den URI der Metadaten des Endpunkts an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Outputmodule

Gibt den Pfad und den Modulnamen an, in denen dieses Cmdlet das generierte Modul von Proxy Befehlen speichert.

Dieses Cmdlet kopiert ggf. ein binäres Modul, ein Modul Manifest und eine Formatierungs Datei in den angegebenen Ordner. Wenn Sie nur den Namen des Moduls angeben, `Export-ODataEndpointProxy` speichert das Modul im `$home\Documents\WindowsPowerShell\Modules` Ordner. Wenn Sie einen Pfad angeben, erstellt das Cmdlet den Modul Ordner in diesem Pfad.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Resourcenamemapping

Gibt eine Hash Tabelle an, die Zuordnungen enthält, mit denen Sie die generierten Cmdlets anpassen können. In dieser Hash Tabelle ist der Name der Ressourcensammlung der Schlüssel. Das gewünschte Substantiv des Cmdlets ist der Wert.

In der Hash Tabelle ist z. b. `@{Products = 'Merchandise'}` **Products** der Name der Ressourcensammlung, die als Schlüssel dient. " **Waren** " ist das resultierende Cmdlet-Substantiv. Die generierten Cmdlet-Namen sind möglicherweise nicht an den Windows PowerShell-Cmdlet-Benennungs Richtlinien ausgerichtet. Sie können die Ressourcen-cdxml-Datei ändern, um die Cmdlet-Namen zu ändern, nachdem dieses Cmdlet das Modul erstellt hat. Weitere Informationen finden Sie unter [stark unterstützt Entwicklungs Richtlinien](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Updaterequestmethod

Gibt die Aktualisierungs Anforderungs Methode an. Die zulässigen Werte für diesen Parameter lauten: Put, Post und Patch.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -URI

Gibt den URI des Endpunkts an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[OData-Bibliothek](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)

[Was ist das odata-Protokoll?](https://www.odata.org/)

[Invoke-RestMethod](../Microsoft.PowerShell.Utility/Invoke-RestMethod.md)
