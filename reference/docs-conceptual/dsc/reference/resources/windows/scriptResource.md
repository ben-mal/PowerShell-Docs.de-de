---
ms.date: 07/16/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressource „Script“
ms.openlocfilehash: 9b89981c17e87b3681c6416c7dee44a75c432ea1
ms.sourcegitcommit: eb6a7c01e6385809656ac828b9211683e0b1a6fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "89041128"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="5e2c2-103">DSC-Ressource „Script“</span><span class="sxs-lookup"><span data-stu-id="5e2c2-103">DSC Script Resource</span></span>

> <span data-ttu-id="5e2c2-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="5e2c2-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="5e2c2-105">Die Ressource `Script` in Windows PowerShell DSC bietet einen Mechanismus zum Anwenden von Windows PowerShell-Skriptblöcken auf Zielknoten.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-105">The `Script` resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="5e2c2-106">Die Ressource `Script` verwendet die Eigenschaften `GetScript`
`SetScript` und `TestScript`, die von Ihnen definierte Skriptblöcke enthalten, um die entsprechenden DSC-Zustandsvorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-106">The `Script` resource uses `GetScript`
`SetScript`, and `TestScript` properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e2c2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e2c2-107">Syntax</span></span>

```Syntax
Script [string] #ResourceName
{
    GetScript = [string]
    SetScript = [string]
    TestScript = [string]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

> [!NOTE]
> <span data-ttu-id="5e2c2-108">Die Blöcke `GetScript` `TestScript` und `SetScript` werden als Zeichenfolgen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-108">`GetScript` `TestScript`, and `SetScript` blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="5e2c2-109">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e2c2-109">Properties</span></span>

|  <span data-ttu-id="5e2c2-110">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5e2c2-110">Property</span></span>  |                                          <span data-ttu-id="5e2c2-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5e2c2-111">Description</span></span>                                          |
| ---------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="5e2c2-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="5e2c2-112">GetScript</span></span>  | <span data-ttu-id="5e2c2-113">Ein Skriptblock, der den aktuellen Zustand des Knotens zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-113">A script block that returns the current state of the Node.</span></span>                                    |
| <span data-ttu-id="5e2c2-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="5e2c2-114">SetScript</span></span>  | <span data-ttu-id="5e2c2-115">Ein Skriptblock, mit dem DSC die Konformität erzwingt, wenn der Knoten nicht im gewünschten Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span> |
| <span data-ttu-id="5e2c2-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="5e2c2-116">TestScript</span></span> | <span data-ttu-id="5e2c2-117">Ein Skriptblock, der bestimmt, ob der Knoten im gewünschten Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-117">A script block that determines if the Node is in the desired state.</span></span>                           |
| <span data-ttu-id="5e2c2-118">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="5e2c2-118">Credential</span></span> | <span data-ttu-id="5e2c2-119">Gibt die Anmeldeinformationen zum Ausführen dieses Skripts an, falls Anmeldeinformationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-119">Indicates the credentials to use for running this script, if credentials are required.</span></span>        |

## <a name="common-properties"></a><span data-ttu-id="5e2c2-120">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e2c2-120">Common properties</span></span>

|       <span data-ttu-id="5e2c2-121">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5e2c2-121">Property</span></span>       |                                            <span data-ttu-id="5e2c2-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5e2c2-122">Description</span></span>                                            |
| -------------------- | ------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="5e2c2-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="5e2c2-123">DependsOn</span></span>            | <span data-ttu-id="5e2c2-124">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> |
| <span data-ttu-id="5e2c2-125">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="5e2c2-125">PsDscRunAsCredential</span></span> | <span data-ttu-id="5e2c2-126">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-126">Sets the credential for running the entire resource as.</span></span>                                           |

> [!NOTE]
> <span data-ttu-id="5e2c2-127">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-127">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="5e2c2-128">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="5e2c2-128">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="5e2c2-129">Zusätzliche Informationen</span><span class="sxs-lookup"><span data-stu-id="5e2c2-129">Additional information</span></span>

#### <a name="getscript"></a><span data-ttu-id="5e2c2-130">GetScript</span><span class="sxs-lookup"><span data-stu-id="5e2c2-130">GetScript</span></span>

<span data-ttu-id="5e2c2-131">DSC verwendet die Ausgabe von `GetScript` nicht. Das Cmdlet [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) führt `GetScript` aus, um den aktuellen Zustand eines Knotens abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-131">DSC does not use the output from `GetScript` The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes `GetScript` to retrieve a node's current state.</span></span> <span data-ttu-id="5e2c2-132">Ein Rückgabewert von `GetScript` ist nicht erforderlich. Wenn Sie einen Rückgabewert angeben, muss es eine Hashtabelle mit einem **Result**-Schlüssel sein, dessen Wert eine Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-132">A return value is not required from `GetScript` If you specify a return value, it must be a hashtable containing a **Result** key whose value is a String.</span></span>

#### <a name="testscript"></a><span data-ttu-id="5e2c2-133">TestScript</span><span class="sxs-lookup"><span data-stu-id="5e2c2-133">TestScript</span></span>

<span data-ttu-id="5e2c2-134">`TestScript` wird von DSC ausgeführt, um zu bestimmen, ob `SetScript` ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-134">`TestScript` is executed by DSC to determine if `SetScript` should be run.</span></span> <span data-ttu-id="5e2c2-135">Wenn `TestScript` den Wert `$false` zurückgibt, führt DSC `SetScript` aus, um den Knoten wieder in den gewünschten Zustand zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-135">If `TestScript` returns `$false`, DSC executes `SetScript` to bring the node back to the desired state.</span></span> <span data-ttu-id="5e2c2-136">Es muss ein boolescher Wert zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-136">It must return a boolean value.</span></span> <span data-ttu-id="5e2c2-137">Das Ergebnis `$true` gibt an, dass der Knoten konform ist und `SetScript` nicht ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-137">A result of `$true` indicates that the node is compliant and `SetScript` should not executed.</span></span>

<span data-ttu-id="5e2c2-138">Das Cmdlet [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) führt `TestScript` aus, um die Konformität der Knoten mit den `Script`-Ressourcen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-138">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes `TestScript` to retrieve the nodes compliance with the `Script` resources.</span></span> <span data-ttu-id="5e2c2-139">In diesem Fall wird `SetScript` jedoch nicht ausgeführt, unabhängig davon, was vom `TestScript`-Block zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-139">However, in this case, `SetScript` does not run, no matter what `TestScript` block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="5e2c2-140">Die gesamte Ausgabe von `TestScript` ist Teil des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-140">All output from your `TestScript` is part of its return value.</span></span> <span data-ttu-id="5e2c2-141">PowerShell interpretiert nicht unterdrückte Ausgaben als ungleich null. Dies bedeutet, dass `TestScript` den Wert `$true` unabhängig vom Zustand des Knotens zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-141">PowerShell interprets unsuppressed output as non-zero, which means that your `TestScript` will return `$true` regardless of your node's state.</span></span> <span data-ttu-id="5e2c2-142">Dies führt zu unvorhersehbaren Ergebnissen und zu falsch positiven Ergebnissen und erschwert so die Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-142">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

#### <a name="setscript"></a><span data-ttu-id="5e2c2-143">SetScript</span><span class="sxs-lookup"><span data-stu-id="5e2c2-143">SetScript</span></span>

<span data-ttu-id="5e2c2-144">`SetScript` ändert den Knoten, um den gewünschten Zustand zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-144">`SetScript` modifies the node to enforce the desired state.</span></span> <span data-ttu-id="5e2c2-145">Der Skriptblock wird von DSC aufgerufen, wenn der Skriptblock `TestScript` den Wert `$false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-145">It is called by DSC if the `TestScript` script block returns `$false`.</span></span> <span data-ttu-id="5e2c2-146">`SetScript` sollte keinen Rückgabewert haben.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-146">The `SetScript` should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="5e2c2-147">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5e2c2-147">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="5e2c2-148">Beispiel 1: Schreiben von Beispieltext mit einer Skriptressource</span><span class="sxs-lookup"><span data-stu-id="5e2c2-148">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="5e2c2-149">Dieses Beispiel testet das Vorhandensein von `C:\TempFolder\TestFile.txt` auf jedem Knoten.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-149">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="5e2c2-150">Wenn die Datei nicht vorhanden ist, wird sie mit `SetScript` erstellt.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-150">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="5e2c2-151">`GetScript` gibt den Inhalt der Datei zurück, und der Rückgabewert wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-151">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

```powershell
Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script ScriptExample
        {
            SetScript = {
                $sw = New-Object System.IO.StreamWriter("C:\TempFolder\TestFile.txt")
                $sw.WriteLine("Some sample string")
                $sw.Close()
            }
            TestScript = { Test-Path "C:\TempFolder\TestFile.txt" }
            GetScript = { @{ Result = (Get-Content C:\TempFolder\TestFile.txt) } }
        }
    }
}
```

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="5e2c2-152">Beispiel 2: Vergleichen von Versionsinformationen mit einer Skriptressource</span><span class="sxs-lookup"><span data-stu-id="5e2c2-152">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="5e2c2-153">Dieses Beispiel ruft die Informationen zur _konformen_ Version aus einer Textdatei auf dem zur Erstellung verwendeten Computer ab und speichert sie in der `$version`-Variablen.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-153">This example retrieves the _compliant_ version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="5e2c2-154">Beim Generieren der MOF-Datei des Knotens ersetzt DSC die `$using:version`-Variablen in jedem Skriptblock durch den Wert der `$version`-Variablen.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-154">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>
<span data-ttu-id="5e2c2-155">Während der Ausführung wird die _konforme_ Version in einer Textdatei auf jedem Knoten gespeichert und bei nachfolgenden Ausführungen verglichen und aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-155">During execution, the _compliant_ version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state.Result -eq $using:version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state.Result,$using:version)
                    return $true
                }
                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                $using:version | Set-Content -Path (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
            }
        }
    }
}
```

### <a name="example-3-utilizing-parameters-in-a-script-resource"></a><span data-ttu-id="5e2c2-156">Beispiel 3: Verwenden von Parametern in einer Skriptressource</span><span class="sxs-lookup"><span data-stu-id="5e2c2-156">Example 3: Utilizing parameters in a Script resource</span></span>

<span data-ttu-id="5e2c2-157">In diesem Beispiel wird in der Skriptressource auf Parameter zugegriffen, indem der `using`-Bereich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-157">This example accesses parameters from within the Script resource by making use of the `using` scope.</span></span>
<span data-ttu-id="5e2c2-158">Beachten Sie dass auf **ConfigurationData** auf ähnliche Weise zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-158">Please note that **ConfigurationData** can be accessed in a similar way.</span></span> <span data-ttu-id="5e2c2-159">Wie in Beispiel 2 wird erwartet, dass eine Version in einer lokalen Datei auf dem Zielknoten gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-159">Like example 2, a version is expected to be stored inside a local file on the target node.</span></span> <span data-ttu-id="5e2c2-160">Jedoch sind sowohl der lokale Dateipfad als auch die Version konfigurierbar, wobei Code von Konfigurationsdaten abgekoppelt wird.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-160">Both the local file path as well as the version are configurable however, decoupling code from configuration data.</span></span>

```powershell
Configuration ScriptTest
{
    param
    (
        [Version]
        $Version,

        [string]
        $FilePath
    )

    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content -Path $using:FilePath
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

                if( $state['Result'] -eq $using:Version )
                {
                    Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
                    return $true
                }

                Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
                return $false
            }
            SetScript = {
                Set-Content -Path $using:FilePath -Value $using:Version
            }
        }
    }
}
```

<span data-ttu-id="5e2c2-161">Die resultierende MOF-Datei enthält die Variablen und deren Werte, auf die über den `using`-Bereich zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-161">The resulting MOF file includes the variables and their values accessed through the `using` scope.</span></span>
<span data-ttu-id="5e2c2-162">Sie werden in jeden ScriptBlock eingefügt, die die Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-162">They are injected into each scriptblock which uses the variables.</span></span> <span data-ttu-id="5e2c2-163">Test- und Set-Skripts wurden der Kürze halber entfernt:</span><span class="sxs-lookup"><span data-stu-id="5e2c2-163">Test and Set scripts have been removed for brevity:</span></span>

```Output
instance of MSFT_ScriptResource as $MSFT_ScriptResource1ref
{
 GetScript = "$FilePath ='C:\\Config.ini'\n\n $currentVersion = Get-Content -Path $FilePath\n return @{ 'Result' = \"$currentVersion\" }\n";
 TestScript = ...;
 SetScript = ...;
};
```

### <a name="known-limitations"></a><span data-ttu-id="5e2c2-164">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5e2c2-164">Known Limitations</span></span>

- <span data-ttu-id="5e2c2-165">Anmeldeinformationen, die innerhalb einer Skriptressource übermittelt werden, sind bei Verwendung eines Pull- oder Pushservermodells nicht immer zuverlässig.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-165">Credentials being passed within a script resource are not always reliable when using a pull or push server model.</span></span> <span data-ttu-id="5e2c2-166">Es wird empfohlen, in diesem Fall anstelle einer Skriptressource eine vollständige Ressource zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e2c2-166">It is recommended to use a full resource rather than use a script resource in this case.</span></span>
