---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: cbd100b73aa40eb3d14366a3c0f845fc2837a783
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347481"
---
# <span data-ttu-id="f1dce-103">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f1dce-103">Test-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="f1dce-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f1dce-104">SYNOPSIS</span></span>
<span data-ttu-id="f1dce-105">Überprüft die Schlüssel und Werte in einer Sitzungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f1dce-105">Verifies the keys and values in a session configuration file.</span></span>

## <span data-ttu-id="f1dce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f1dce-106">SYNTAX</span></span>

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="f1dce-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f1dce-107">DESCRIPTION</span></span>

<span data-ttu-id="f1dce-108">Mit diesem Cmdlet wird überprüft, ob eine Sitzungs Konfigurationsdatei gültige Schlüssel enthält und die Werte den richtigen Typ haben.</span><span class="sxs-lookup"><span data-stu-id="f1dce-108">This cmdlet verifies that a session configuration file contains valid keys and the values are of the correct type.</span></span> <span data-ttu-id="f1dce-109">Bei Enumerationswerten überprüft das Cmdlet, ob die angegebenen Werte gültig sind.</span><span class="sxs-lookup"><span data-stu-id="f1dce-109">For enumerated values, the cmdlet verifies that the specified values are valid.</span></span>

<span data-ttu-id="f1dce-110">Das-Cmdlet gibt zurück, `$True` Wenn die Datei alle Tests übergibt und `$False` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="f1dce-110">The cmdlet returns `$True` if the file passes all tests and `$False` if it does not.</span></span> <span data-ttu-id="f1dce-111">Um Fehler zu finden, verwenden Sie den **verbose** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f1dce-111">To find any errors, use the **Verbose** parameter.</span></span>

<span data-ttu-id="f1dce-112">`Test-PSSessionConfigurationFile` überprüft die Sitzungs Konfigurationsdateien, z. b. die, die vom `New-PSSessionConfigurationFile` Cmdlet erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f1dce-112">`Test-PSSessionConfigurationFile` verifies the session configuration files, such as those created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="f1dce-113">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="f1dce-113">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span> <span data-ttu-id="f1dce-114">Weitere Informationen zu Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="f1dce-114">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="f1dce-115">Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f1dce-115">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="f1dce-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f1dce-116">EXAMPLES</span></span>

### <span data-ttu-id="f1dce-117">Beispiel 1: Testen einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f1dce-117">Example 1: Test a session configuration file</span></span>

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### <span data-ttu-id="f1dce-118">Beispiel 2: Testen der Sitzungs Konfigurationsdatei einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f1dce-118">Example 2: Test the session configuration file of a session configuration</span></span>

<span data-ttu-id="f1dce-119">In diesem Beispiel testen wir die Konfigurationsdatei, die in der **eingeschränkten** Sitzungs Konfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f1dce-119">In this example, we test the configuration file used in the **Restricted** session configuration.</span></span>
<span data-ttu-id="f1dce-120">Der Wert des **path** -Parameters ist das Ergebnis des `Get-PSSessionConfiguration` Befehls, mit dem die **Eingeschränkte** Sitzungs Konfiguration abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f1dce-120">The value of the **Path** parameter is the result of the `Get-PSSessionConfiguration` command that gets the **Restricted** session configuration.</span></span> <span data-ttu-id="f1dce-121">Der Pfad der Sitzungs Konfigurationsdatei wird im Wert der **configfilepath** -Eigenschaft der Sitzungs Konfiguration gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f1dce-121">The path of the session configuration file is stored in the value of the **ConfigFilePath** property of the session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### <span data-ttu-id="f1dce-122">Beispiel 3: Testen aller Sitzungs Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="f1dce-122">Example 3: Test all session configuration files</span></span>

<span data-ttu-id="f1dce-123">Mit der-Funktion in diesem Beispiel werden alle Sitzungs Konfigurationsdateien auf dem lokalen Computer getestet.</span><span class="sxs-lookup"><span data-stu-id="f1dce-123">The function in this example tests all session configuration files on the local computer.</span></span> <span data-ttu-id="f1dce-124">Die-Funktion verwendet das- `Get-PSSessionConfiguration` Cmdlet, um alle Sitzungs Konfigurationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f1dce-124">The function uses the `Get-PSSessionConfiguration` cmdlet to get all session configurations.</span></span> <span data-ttu-id="f1dce-125">Der Code in der `ForEach-Object` Schleife zeigt den Dateipfad an und testet jede Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f1dce-125">The code inside the `ForEach-Object` loop displays the file path and tests each of the session configurations.</span></span>

```powershell
function Test-AllConfigFiles
{
    Get-PSSessionConfiguration | ForEach-Object {
        if ($_.ConfigFilePath) {
            $_.ConfigFilePath
            Test-PSSessionConfigurationFile -Verbose -Path $_.ConfigFilePath
        }
    }
}
Test-AllConfigFiles
```

```Output
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Empty_6fd77bf6-e084-4372-bd8a-af3e207354d3.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
VERBOSE: The member 'AliasDefinitions' must contain the required key 'Description'. Add the require key
to the fileC:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc.
False
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RestrictedLang_b6bd9474-0a6c-4e06-8722-c2c95bb10d3e.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RRS_3fb29420-2c87-46e5-a402-e21436331efc.pssc
True
```

<span data-ttu-id="f1dce-126">Die **configfilepath** -Eigenschaft einer Sitzungs Konfiguration enthält den Pfad der Sitzungs Konfigurationsdatei, die in der Sitzungs Konfiguration verwendet wird (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="f1dce-126">The **ConfigFilePath** property of a session configuration contains the path of the session configuration file that is used in the session configuration, if any.</span></span>

<span data-ttu-id="f1dce-127">Wenn der Wert der **ConfigFilePath** -Eigenschaft angegeben ist (sprich er ist „true“), ruft der Befehl den **ConfigFilePath** -Eigenschaftswert ab (bzw. gibt ihn aus).</span><span class="sxs-lookup"><span data-stu-id="f1dce-127">If the value of the **ConfigFilePath** property is populated (is true), the command gets (prints) the **ConfigFilePath** property value.</span></span> <span data-ttu-id="f1dce-128">Dann wird das `Test-PSSessionConfigurationFile` Cmdlet verwendet, um die Datei im **configfilepath** -Wert zu testen.</span><span class="sxs-lookup"><span data-stu-id="f1dce-128">Then it uses the `Test-PSSessionConfigurationFile` cmdlet to test the file in the **ConfigFilePath** value.</span></span> <span data-ttu-id="f1dce-129">Der **Verbose** -Parameter gibt den Dateifehler zurück, wenn die Datei den Test nicht besteht.</span><span class="sxs-lookup"><span data-stu-id="f1dce-129">The **Verbose** parameter returns the file error when the file fails the test.</span></span>

## <span data-ttu-id="f1dce-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f1dce-130">PARAMETERS</span></span>

### <span data-ttu-id="f1dce-131">-Path</span><span class="sxs-lookup"><span data-stu-id="f1dce-131">-Path</span></span>

<span data-ttu-id="f1dce-132">Gibt den Pfad und den Dateinamen einer Sitzungs Konfigurationsdatei (. PSSC) an.</span><span class="sxs-lookup"><span data-stu-id="f1dce-132">Specifies the path and filename of a session configuration file (.pssc).</span></span> <span data-ttu-id="f1dce-133">Wenn Sie den Pfad weglassen, wird standardmäßig der aktuelle Ordner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1dce-133">If you omit the path, the default is the current folder.</span></span> <span data-ttu-id="f1dce-134">Platzhalter Zeichen werden unterstützt, aber Sie müssen in eine einzelne Datei aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="f1dce-134">Wildcard characters are supported, but they must resolve to a single file.</span></span> <span data-ttu-id="f1dce-135">Sie können auch einen Sitzungs Konfigurationsdateipfad an über die Pipeline übergeben `Test-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="f1dce-135">You can also pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="f1dce-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f1dce-136">CommonParameters</span></span>

<span data-ttu-id="f1dce-137">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f1dce-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f1dce-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f1dce-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f1dce-139">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f1dce-139">INPUTS</span></span>

### <span data-ttu-id="f1dce-140">System.String</span><span class="sxs-lookup"><span data-stu-id="f1dce-140">System.String</span></span>

<span data-ttu-id="f1dce-141">Sie können einen Sitzungs Konfigurationsdateipfad an über die Pipeline übergeben `Test-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="f1dce-141">You can pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

## <span data-ttu-id="f1dce-142">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f1dce-142">OUTPUTS</span></span>

### <span data-ttu-id="f1dce-143">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="f1dce-143">System.Boolean</span></span>

## <span data-ttu-id="f1dce-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f1dce-144">NOTES</span></span>

<span data-ttu-id="f1dce-145">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1dce-145">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="f1dce-146">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f1dce-146">RELATED LINKS</span></span>

[<span data-ttu-id="f1dce-147">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1dce-147">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="f1dce-148">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1dce-148">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="f1dce-149">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1dce-149">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="f1dce-150">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f1dce-150">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="f1dce-151">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="f1dce-151">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="f1dce-152">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1dce-152">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="f1dce-153">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1dce-153">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="f1dce-154">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f1dce-154">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="f1dce-155">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1dce-155">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="f1dce-156">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="f1dce-156">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="f1dce-157">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="f1dce-157">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="f1dce-158">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="f1dce-158">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
