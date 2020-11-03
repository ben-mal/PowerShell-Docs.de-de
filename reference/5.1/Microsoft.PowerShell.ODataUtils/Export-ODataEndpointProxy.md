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
# <span data-ttu-id="a190e-103">Export-ODataEndpointProxy</span><span class="sxs-lookup"><span data-stu-id="a190e-103">Export-ODataEndpointProxy</span></span>

## <span data-ttu-id="a190e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a190e-104">SYNOPSIS</span></span>
<span data-ttu-id="a190e-105">Generiert ein Modul, das Cmdlets zum Verwalten eines odata-Endpunkts enthält.</span><span class="sxs-lookup"><span data-stu-id="a190e-105">Generates a module that contains cmdlets to manage an OData endpoint.</span></span>

## <span data-ttu-id="a190e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a190e-106">SYNTAX</span></span>

```
Export-ODataEndpointProxy [-Uri] <String> [-OutputModule] <String> [[-MetadataUri] <String>]
 [[-Credential] <PSCredential>] [[-CreateRequestMethod] <String>] [[-UpdateRequestMethod] <String>]
 [[-CmdletAdapter] <String>] [[-ResourceNameMapping] <Hashtable>] [-Force] [[-CustomData] <Hashtable>]
 [-AllowClobber] [-AllowUnsecureConnection] [[-Headers] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a190e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a190e-107">DESCRIPTION</span></span>

<span data-ttu-id="a190e-108">Das `Export-ODataEndpointProxy` Cmdlet verwendet die Metadaten eines odata-Endpunkts, um ein Modul zu generieren, das Cmdlets enthält, die Sie zum Verwalten dieses odata-Endpunkts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a190e-108">The `Export-ODataEndpointProxy` cmdlet uses the metadata of an OData endpoint to generate a module that contains cmdlets you can use to manage that OData endpoint.</span></span> <span data-ttu-id="a190e-109">Das Modul basiert auf cdxml.</span><span class="sxs-lookup"><span data-stu-id="a190e-109">The module is based on CDXML.</span></span> <span data-ttu-id="a190e-110">Nachdem dieses Cmdlet das Modul generiert hat, speichert es das Modul in dem Pfad und dem Dateinamen, die durch den Parameter **outputmodule** angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a190e-110">After this cmdlet generates the module, it saves that module to the path and file name specified by the **OutputModule** parameter.</span></span>

<span data-ttu-id="a190e-111">`Export-ODataEndpointProxy` generiert Cmdlets für Erstellungs-, Lese-, Aktualisierungs-und Löschvorgänge (CRUD), nicht-CRUD-Aktionen und Zuordnungs Manipulationen.</span><span class="sxs-lookup"><span data-stu-id="a190e-111">`Export-ODataEndpointProxy` generates cmdlets for create, read, update, and delete (CRUD) operations, non-CRUD actions, and association manipulation.</span></span>

<span data-ttu-id="a190e-112">`Export-ODataEndpointProxy` generiert eine cdxml-Datei pro Endpunkt Ressource.</span><span class="sxs-lookup"><span data-stu-id="a190e-112">`Export-ODataEndpointProxy` generates one CDXML file per endpoint resource.</span></span> <span data-ttu-id="a190e-113">Sie können diese cdxml-Dateien bearbeiten, nachdem das Modul generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a190e-113">You can edit these CDXML files after the module is generated.</span></span> <span data-ttu-id="a190e-114">Wenn Sie z. b. die Substantiv-oder Verb Namen der Cmdlets so ändern möchten, dass Sie mit den Benennungs Richtlinien für Windows PowerShell-Cmdlets übereinstimmen, können Sie die Datei ändern.</span><span class="sxs-lookup"><span data-stu-id="a190e-114">For example, if you want to change the noun or verb names of the cmdlets to align with Windows PowerShell cmdlet naming guidelines, you can modify the file.</span></span>

<span data-ttu-id="a190e-115">Jedes Cmdlet in einem generierten Modul muss einen **ConnectionUri** -Parameter enthalten, um eine Verbindung mit dem Endpunkt herzustellen, den das Modul verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a190e-115">Every cmdlet in a generated module must include a **ConnectionURI** parameter in order to connect to the endpoint that the module manages.</span></span>

## <span data-ttu-id="a190e-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a190e-116">EXAMPLES</span></span>

### <span data-ttu-id="a190e-117">Beispiel 1: Generieren eines Moduls zum Verwalten eines Einzelhandels-Webdienst-Endpunkts</span><span class="sxs-lookup"><span data-stu-id="a190e-117">Example 1: Generate a module to manage a retail web service endpoint</span></span>

```powershell
PS C:\> Export-ODataEndpointProxy -Uri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc' -MetadataUri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc/$metadata' -AllowUnsecureConnection -OutputModule 'C:\Users\user\GeneratedScript.psm1' -ResourceNameMapping @{Products = 'Merchandise'}
```

<span data-ttu-id="a190e-118">Dieser Befehl generiert ein Modul zum Verwalten eines Einzelhandels Dienst-Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="a190e-118">This command generates a module to manage a retail service endpoint.</span></span> <span data-ttu-id="a190e-119">Der-Befehl gibt den URI des Endpunkts und den URI der Endpunkt Metadaten an.</span><span class="sxs-lookup"><span data-stu-id="a190e-119">The command specifies the URI of the endpoint and the URI of the endpoint metadata.</span></span> <span data-ttu-id="a190e-120">Der Befehl stellt außerdem einen Ausgabepfad und Skript Modulnamen als Wert für den Parameter **outputmodule** bereit.</span><span class="sxs-lookup"><span data-stu-id="a190e-120">The command also provides an output path and script module name as the value of the **OutputModule** parameter.</span></span> <span data-ttu-id="a190e-121">Für den Wert des **resourcenamemapping** -Parameters bietet der Befehl eine Hash Tabelle, die den Ressourcen Sammlungsnamen dem gewünschten Substantiv für das Cmdlet-Set zuordnet.</span><span class="sxs-lookup"><span data-stu-id="a190e-121">For the value of the **ResourceNameMapping** parameter, the command provides a hashtable that maps the resource collection name to the desired noun for the cmdlet set.</span></span> <span data-ttu-id="a190e-122">In diesem Beispiel ist Products der Name der Ressourcensammlung, und die **Ware** ist das Substantiv.</span><span class="sxs-lookup"><span data-stu-id="a190e-122">In this example, Products is the resource collection name and **Merchandise** is the noun.</span></span> <span data-ttu-id="a190e-123">Um Verbindungen mit nicht-SSL-Sites zuzulassen, fügen Sie http anstelle von HTTPS den Parameter " **zufüge** Anforderung" hinzu.</span><span class="sxs-lookup"><span data-stu-id="a190e-123">To allow connections to non-SSL sites, HTTP, as opposed to HTTPS, add the **AllowUnsecureConnection** parameter.</span></span>

## <span data-ttu-id="a190e-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a190e-124">PARAMETERS</span></span>

### <span data-ttu-id="a190e-125">-Allowclobber</span><span class="sxs-lookup"><span data-stu-id="a190e-125">-AllowClobber</span></span>

<span data-ttu-id="a190e-126">Gibt an, dass dieses Cmdlet ein vorhandenes Modul ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a190e-126">Indicates that this cmdlet replaces an existing module.</span></span>

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

### <span data-ttu-id="a190e-127">-"-Zugewunsecureconnection"</span><span class="sxs-lookup"><span data-stu-id="a190e-127">-AllowUnsecureConnection</span></span>

<span data-ttu-id="a190e-128">Gibt an, dass dieses Modul eine Verbindung mit URIs herstellen kann, die nicht SSL-geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="a190e-128">Indicates that this module can connect to URIs that are not SSL-secured.</span></span> <span data-ttu-id="a190e-129">Das Modul kann neben HTTPS-Websites auch HTTP-Websites verwalten.</span><span class="sxs-lookup"><span data-stu-id="a190e-129">The module can manage HTTP sites in addition to HTTPS sites.</span></span>

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

### <span data-ttu-id="a190e-130">-Cmdletadapter</span><span class="sxs-lookup"><span data-stu-id="a190e-130">-CmdletAdapter</span></span>

<span data-ttu-id="a190e-131">Gibt den Cmdlet-Adapter an.</span><span class="sxs-lookup"><span data-stu-id="a190e-131">Specifies the cmdlet adapter.</span></span> <span data-ttu-id="a190e-132">Die zulässigen Werte für diesen Parameter sind: odataadapter und networkcontrolleradapter.</span><span class="sxs-lookup"><span data-stu-id="a190e-132">The acceptable values for this parameter are: ODataAdapter and NetworkControllerAdapter.</span></span>

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

### <span data-ttu-id="a190e-133">-"-Kreaterequestmethod"</span><span class="sxs-lookup"><span data-stu-id="a190e-133">-CreateRequestMethod</span></span>

<span data-ttu-id="a190e-134">Gibt die Anforderungs Methode an.</span><span class="sxs-lookup"><span data-stu-id="a190e-134">Specifies the request method.</span></span> <span data-ttu-id="a190e-135">Die zulässigen Werte für diesen Parameter lauten: Put, Post und Patch.</span><span class="sxs-lookup"><span data-stu-id="a190e-135">The acceptable values for this parameter are: PUT, POST, and PATCH.</span></span>

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

### <span data-ttu-id="a190e-136">-Credential</span><span class="sxs-lookup"><span data-stu-id="a190e-136">-Credential</span></span>

<span data-ttu-id="a190e-137">Gibt ein Benutzerkonto an, das Zugriff auf den odata-Endpunkt hat.</span><span class="sxs-lookup"><span data-stu-id="a190e-137">Specifies a user account that has access to the OData endpoint.</span></span> <span data-ttu-id="a190e-138">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a190e-138">The default value is the current user.</span></span> <span data-ttu-id="a190e-139">Wenn auf einem Remote Computer Windows Vista oder ein späteres Release des Windows-Betriebssystems ausgeführt wird, werden Sie vom Cmdlet zur Eingabe von Anmelde Informationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a190e-139">If a remote computer runs Windows Vista or a later release of the Windows operating system, the cmdlet prompts you for credentials.</span></span>

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

### <span data-ttu-id="a190e-140">-CustomData</span><span class="sxs-lookup"><span data-stu-id="a190e-140">-CustomData</span></span>

<span data-ttu-id="a190e-141">Gibt eine Hash Tabelle mit benutzerdefinierten Daten an.</span><span class="sxs-lookup"><span data-stu-id="a190e-141">Specifies a hash table of custom data.</span></span>

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

### <span data-ttu-id="a190e-142">-Force</span><span class="sxs-lookup"><span data-stu-id="a190e-142">-Force</span></span>

<span data-ttu-id="a190e-143">Gibt an, dass dieses Cmdlet ein vorhandenes generiertes Modul mit demselben Namen in einem vorhandenen Ordner überschreibt `Modules` .</span><span class="sxs-lookup"><span data-stu-id="a190e-143">Indicates that this cmdlet overwrites an existing generated module of the same name in an existing `Modules` folder.</span></span>

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

### <span data-ttu-id="a190e-144">-Header</span><span class="sxs-lookup"><span data-stu-id="a190e-144">-Headers</span></span>

<span data-ttu-id="a190e-145">Gibt die Header der Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="a190e-145">Specifies the headers of the web request.</span></span> <span data-ttu-id="a190e-146">Geben Sie eine Hashtabelle oder ein Wörterbuch ein.</span><span class="sxs-lookup"><span data-stu-id="a190e-146">Enter a hash table or dictionary.</span></span>

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

### <span data-ttu-id="a190e-147">-MetadataUri</span><span class="sxs-lookup"><span data-stu-id="a190e-147">-MetadataUri</span></span>

<span data-ttu-id="a190e-148">Gibt den URI der Metadaten des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="a190e-148">Specifies the URI of the metadata of the endpoint.</span></span>

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

### <span data-ttu-id="a190e-149">-Outputmodule</span><span class="sxs-lookup"><span data-stu-id="a190e-149">-OutputModule</span></span>

<span data-ttu-id="a190e-150">Gibt den Pfad und den Modulnamen an, in denen dieses Cmdlet das generierte Modul von Proxy Befehlen speichert.</span><span class="sxs-lookup"><span data-stu-id="a190e-150">Specifies the path and module name to which this cmdlet saves the generated module of proxy commands.</span></span>

<span data-ttu-id="a190e-151">Dieses Cmdlet kopiert ggf. ein binäres Modul, ein Modul Manifest und eine Formatierungs Datei in den angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="a190e-151">This cmdlet copies a binary module, module manifest, and formatting file, if applicable, to the specified folder.</span></span> <span data-ttu-id="a190e-152">Wenn Sie nur den Namen des Moduls angeben, `Export-ODataEndpointProxy` speichert das Modul im `$home\Documents\WindowsPowerShell\Modules` Ordner.</span><span class="sxs-lookup"><span data-stu-id="a190e-152">If you specify only the name of the module, `Export-ODataEndpointProxy` saves the module in the `$home\Documents\WindowsPowerShell\Modules` folder.</span></span> <span data-ttu-id="a190e-153">Wenn Sie einen Pfad angeben, erstellt das Cmdlet den Modul Ordner in diesem Pfad.</span><span class="sxs-lookup"><span data-stu-id="a190e-153">If you specify a path, the cmdlet creates the module folder in that path.</span></span>

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

### <span data-ttu-id="a190e-154">-Resourcenamemapping</span><span class="sxs-lookup"><span data-stu-id="a190e-154">-ResourceNameMapping</span></span>

<span data-ttu-id="a190e-155">Gibt eine Hash Tabelle an, die Zuordnungen enthält, mit denen Sie die generierten Cmdlets anpassen können.</span><span class="sxs-lookup"><span data-stu-id="a190e-155">Specifies a hashtable that contains mappings that let you customize the generated cmdlets.</span></span> <span data-ttu-id="a190e-156">In dieser Hash Tabelle ist der Name der Ressourcensammlung der Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="a190e-156">In this hashtable, the resource collection name is the key.</span></span> <span data-ttu-id="a190e-157">Das gewünschte Substantiv des Cmdlets ist der Wert.</span><span class="sxs-lookup"><span data-stu-id="a190e-157">The desired cmdlet noun is the value.</span></span>

<span data-ttu-id="a190e-158">In der Hash Tabelle ist z. b. `@{Products = 'Merchandise'}` **Products** der Name der Ressourcensammlung, die als Schlüssel dient.</span><span class="sxs-lookup"><span data-stu-id="a190e-158">For example, in the hash table `@{Products = 'Merchandise'}`, **Products** is the resource collection name that serves as the key.</span></span> <span data-ttu-id="a190e-159">" **Waren** " ist das resultierende Cmdlet-Substantiv.</span><span class="sxs-lookup"><span data-stu-id="a190e-159">**Merchandise** is the resulting cmdlet noun.</span></span> <span data-ttu-id="a190e-160">Die generierten Cmdlet-Namen sind möglicherweise nicht an den Windows PowerShell-Cmdlet-Benennungs Richtlinien ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="a190e-160">The generated cmdlet names might not align to Windows PowerShell cmdlet naming guidelines.</span></span> <span data-ttu-id="a190e-161">Sie können die Ressourcen-cdxml-Datei ändern, um die Cmdlet-Namen zu ändern, nachdem dieses Cmdlet das Modul erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="a190e-161">You can modify the resource CDXML file to change the cmdlet names after this cmdlet creates the module.</span></span> <span data-ttu-id="a190e-162">Weitere Informationen finden Sie unter [stark unterstützt Entwicklungs Richtlinien](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).</span><span class="sxs-lookup"><span data-stu-id="a190e-162">For more information, see [Strongly Encouraged Development Guidelines](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).</span></span>

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

### <span data-ttu-id="a190e-163">-Updaterequestmethod</span><span class="sxs-lookup"><span data-stu-id="a190e-163">-UpdateRequestMethod</span></span>

<span data-ttu-id="a190e-164">Gibt die Aktualisierungs Anforderungs Methode an.</span><span class="sxs-lookup"><span data-stu-id="a190e-164">Specifies the update request method.</span></span> <span data-ttu-id="a190e-165">Die zulässigen Werte für diesen Parameter lauten: Put, Post und Patch.</span><span class="sxs-lookup"><span data-stu-id="a190e-165">The acceptable values for this parameter are: PUT, POST, and PATCH.</span></span>

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

### <span data-ttu-id="a190e-166">-URI</span><span class="sxs-lookup"><span data-stu-id="a190e-166">-Uri</span></span>

<span data-ttu-id="a190e-167">Gibt den URI des Endpunkts an.</span><span class="sxs-lookup"><span data-stu-id="a190e-167">Specifies the URI of the endpoint.</span></span>

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

### <span data-ttu-id="a190e-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a190e-168">-Confirm</span></span>

<span data-ttu-id="a190e-169">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a190e-169">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a190e-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a190e-170">-WhatIf</span></span>

<span data-ttu-id="a190e-171">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a190e-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a190e-172">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a190e-172">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a190e-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a190e-173">CommonParameters</span></span>

<span data-ttu-id="a190e-174">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a190e-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a190e-175">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a190e-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a190e-176">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a190e-176">INPUTS</span></span>

## <span data-ttu-id="a190e-177">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a190e-177">OUTPUTS</span></span>

## <span data-ttu-id="a190e-178">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a190e-178">NOTES</span></span>

## <span data-ttu-id="a190e-179">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a190e-179">RELATED LINKS</span></span>

<span data-ttu-id="a190e-180">[OData-Bibliothek](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)</span><span class="sxs-lookup"><span data-stu-id="a190e-180">[OData Library](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)</span></span>

[<span data-ttu-id="a190e-181">Was ist das odata-Protokoll?</span><span class="sxs-lookup"><span data-stu-id="a190e-181">What is the OData Protocol?</span></span>](https://www.odata.org/)

[<span data-ttu-id="a190e-182">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="a190e-182">Invoke-RestMethod</span></span>](../Microsoft.PowerShell.Utility/Invoke-RestMethod.md)
