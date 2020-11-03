---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-location?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Location
ms.openlocfilehash: 2ed19d8def95d9c83ae950af263bae5110e3b2f1
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "93219556"
---
# <span data-ttu-id="d69a8-103">Get-Location</span><span class="sxs-lookup"><span data-stu-id="d69a8-103">Get-Location</span></span>

## <span data-ttu-id="d69a8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d69a8-104">SYNOPSIS</span></span>
<span data-ttu-id="d69a8-105">Ruft Informationen zum aktuellen Arbeitsspeicherot oder Speicherstapel ab.</span><span class="sxs-lookup"><span data-stu-id="d69a8-105">Gets information about the current working location or a location stack.</span></span>

## <span data-ttu-id="d69a8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d69a8-106">SYNTAX</span></span>

### <span data-ttu-id="d69a8-107">Speicherort (Standard)</span><span class="sxs-lookup"><span data-stu-id="d69a8-107">Location (Default)</span></span>

```
Get-Location [-PSProvider <String[]>] [-PSDrive <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="d69a8-108">Stapel</span><span class="sxs-lookup"><span data-stu-id="d69a8-108">Stack</span></span>

```
Get-Location [-Stack] [-StackName <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="d69a8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d69a8-109">DESCRIPTION</span></span>

<span data-ttu-id="d69a8-110">Das- `Get-Location` Cmdlet ruft ein Objekt ab, das das aktuelle Verzeichnis darstellt, ähnlich wie der pwd-Befehl (Print Working Directory).</span><span class="sxs-lookup"><span data-stu-id="d69a8-110">The `Get-Location` cmdlet gets an object that represents the current directory, much like the print working directory (pwd) command.</span></span>

<span data-ttu-id="d69a8-111">Wenn Sie zwischen PowerShell-Laufwerken wechseln, behält PowerShell ihren Speicherort auf jedem Laufwerk bei.</span><span class="sxs-lookup"><span data-stu-id="d69a8-111">When you move between PowerShell drives, PowerShell retains your location in each drive.</span></span> <span data-ttu-id="d69a8-112">Mit diesem Cmdlet können Sie ihren Speicherort auf jedem Laufwerk suchen.</span><span class="sxs-lookup"><span data-stu-id="d69a8-112">You can use this cmdlet to find your location in each drive.</span></span>

<span data-ttu-id="d69a8-113">Mit diesem Cmdlet können Sie das aktuelle Verzeichnis zur Laufzeit herunterladen und in Funktionen und Skripts verwenden, z. b. in einer Funktion, die das aktuelle Verzeichnis in der PowerShell-Eingabeaufforderung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d69a8-113">You can use this cmdlet to get the current directory at run time and use it in functions and scripts, such as in a function that displays the current directory in the PowerShell prompt.</span></span>

<span data-ttu-id="d69a8-114">Mit diesem Cmdlet können Sie auch die Speicherorte in einem Speicher Stapel anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d69a8-114">You can also use this cmdlet to display the locations in a location stack.</span></span> <span data-ttu-id="d69a8-115">Weitere Informationen finden Sie in den Hinweisen und Beschreibungen der **Stapel** -und **stackname** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d69a8-115">For more information, see the Notes and the descriptions of the **Stack** and **StackName** parameters.</span></span>

## <span data-ttu-id="d69a8-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d69a8-116">EXAMPLES</span></span>

### <span data-ttu-id="d69a8-117">Beispiel 1: Anzeigen des aktuellen Laufwerks</span><span class="sxs-lookup"><span data-stu-id="d69a8-117">Example 1: Display your current drive location</span></span>

<span data-ttu-id="d69a8-118">Dieser Befehl zeigt den Speicherort auf dem aktuellen PowerShell-Laufwerk an.</span><span class="sxs-lookup"><span data-stu-id="d69a8-118">This command displays your location in the current PowerShell drive.</span></span>

```powershell
PS C:\Windows> Get-Location
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="d69a8-119">Wenn Sie sich beispielsweise im `Windows` Verzeichnis des `C:` Laufwerks befinden, wird der Pfad zu diesem Verzeichnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d69a8-119">For instance, if you are in the `Windows` directory of the `C:` drive, it displays the path to that directory.</span></span>

### <span data-ttu-id="d69a8-120">Beispiel 2: Anzeigen Ihres aktuellen Speicher Orts für verschiedene Laufwerke</span><span class="sxs-lookup"><span data-stu-id="d69a8-120">Example 2: Display your current location for different drives</span></span>

<span data-ttu-id="d69a8-121">In diesem Beispiel wird die Verwendung von `Get-Location` zum Anzeigen Ihres aktuellen Speicher Orts in verschiedenen PowerShell-Laufwerken veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d69a8-121">This example demonstrates the use of `Get-Location` to display your current location in different PowerShell drives.</span></span> <span data-ttu-id="d69a8-122">`Set-Location` wird verwendet, um den Speicherort in mehrere verschiedene Pfade auf verschiedenen PSDrives zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d69a8-122">`Set-Location` is used to change the location to several different paths on different PSDrives.</span></span>

```powershell
PS C:\> Set-Location C:\Windows
PS C:\Windows> Set-Location HKLM:\Software\Microsoft
PS HKLM:\Software\Microsoft> Set-Location "HKCU:\Control Panel\Input Method"
PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive C

Path
----
C:\Windows

PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive HKLM

Path
----
HKLM:\Software\Microsoft

PS HKCU:\Control Panel\Input Method> Set-Location C:
PS C:\Windows> Get-Location -PSProvider Registry

Path
----
HKCU:\Control Panel\Input Method
```

### <span data-ttu-id="d69a8-123">Beispiel 3: Speicherorte mithilfe von Stapeln</span><span class="sxs-lookup"><span data-stu-id="d69a8-123">Example 3: Get locations using stacks</span></span>

<span data-ttu-id="d69a8-124">In diesem Beispiel wird gezeigt, wie die **Stapel** -und **stackname** -Parameter von verwendet werden `Get-Location` , um die Speicherorte im aktuellen Speicher Stapel und in alternativen Speicher Stapeln aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="d69a8-124">This example shows how to use the **Stack** and **StackName** parameters of `Get-Location` to list the locations in the current location stack and alternate location stacks.</span></span>

<span data-ttu-id="d69a8-125">Das- `Push-Location` Cmdlet wird verwendet, um in drei verschiedene Speicherorte zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="d69a8-125">The `Push-Location` cmdlet is used to change into three different locations.</span></span> <span data-ttu-id="d69a8-126">Für den dritten Push wird ein anderer Stapelname verwendet.</span><span class="sxs-lookup"><span data-stu-id="d69a8-126">The third push uses a different stack name.</span></span> <span data-ttu-id="d69a8-127">Der **Stapel** Parameter von `Get-Location` zeigt den Inhalt des Standard Stapels an.</span><span class="sxs-lookup"><span data-stu-id="d69a8-127">The **Stack** parameter of `Get-Location` displays the contents of the default stack.</span></span> <span data-ttu-id="d69a8-128">Der **stackname** -Parameter von `Get-Location` zeigt den Inhalt des Stapels mit dem Namen an `Stack2` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-128">The **StackName** parameter of `Get-Location` displays the contents of the stack named `Stack2`.</span></span>

```powershell
PS C:\> Push-Location C:\Windows
PS C:\Windows>Push-Location System32
PS C:\Windows\System32>Push-Location WindowsPowerShell -StackName Stack2
C:\Windows\System32\WindowsPowerShell>Get-Location -Stack

Path
----
C:\Windows
C:\

C:\Windows\System32\WindowsPowerShell>Get-Location -StackName Stack2

Path
----
C:\Windows\System32
```

### <span data-ttu-id="d69a8-129">Beispiel 4: Anpassen der PowerShell-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="d69a8-129">Example 4: Customize the PowerShell prompt</span></span>

<span data-ttu-id="d69a8-130">In diesem Beispiel wird gezeigt, wie die PowerShell-Eingabeaufforderung angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="d69a8-130">This example shows how to customize the PowerShell prompt.</span></span>

```powershell
PS C:\>
function prompt { 'PowerShell: ' + (Get-Location) + '> '}
PowerShell: C:\>
```

<span data-ttu-id="d69a8-131">Die Funktion, die die Eingabeaufforderung definiert, enthält einen- `Get-Location` Befehl, der ausgeführt wird, wenn die Eingabeaufforderung in der Konsole angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d69a8-131">The function that defines the prompt includes a `Get-Location` command, which is run whenever the prompt appears in the console.</span></span>

<span data-ttu-id="d69a8-132">Das Format der PowerShell-Standardeingabe Aufforderung wird von einer speziellen Funktion mit dem Namen definiert `prompt` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-132">The format of the default PowerShell prompt is defined by a special function named `prompt`.</span></span> <span data-ttu-id="d69a8-133">Sie können die Eingabeaufforderung in der Konsole ändern, indem Sie eine neue Funktion mit dem Namen erstellen `prompt` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-133">You can change the prompt in your console by creating a new function named `prompt`.</span></span>

<span data-ttu-id="d69a8-134">Zum Anzeigen der aktuellen prompt-Funktion geben Sie den folgenden Befehl ein: `Get-Content Function:\prompt`</span><span class="sxs-lookup"><span data-stu-id="d69a8-134">To see the current prompt function, type the following command: `Get-Content Function:\prompt`</span></span>

## <span data-ttu-id="d69a8-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d69a8-135">PARAMETERS</span></span>

### <span data-ttu-id="d69a8-136">-PSDrive</span><span class="sxs-lookup"><span data-stu-id="d69a8-136">-PSDrive</span></span>

<span data-ttu-id="d69a8-137">Ruft die aktuelle Position im angegebenen PowerShell-Laufwerk ab.</span><span class="sxs-lookup"><span data-stu-id="d69a8-137">Gets the current location in the specified PowerShell drive.</span></span>

<span data-ttu-id="d69a8-138">Wenn Sie sich beispielsweise auf dem `Cert:` Laufwerk befinden, können Sie diesen Parameter verwenden, um den aktuellen Speicherort auf dem Laufwerk zu finden `C:` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-138">For instance, if you are in the `Cert:` drive, you can use this parameter to find your current location in the `C:` drive.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d69a8-139">-Psprovider</span><span class="sxs-lookup"><span data-stu-id="d69a8-139">-PSProvider</span></span>

<span data-ttu-id="d69a8-140">Ruft den aktuellen Speicherort auf dem Laufwerk ab, der vom angegebenen PowerShell-Anbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d69a8-140">Gets the current location in the drive supported by the specified PowerShell provider.</span></span>
<span data-ttu-id="d69a8-141">Wenn der angegebene Anbieter mehr als ein Laufwerk unterstützt, gibt dieses Cmdlet den Speicherort auf dem Laufwerk zurück, auf das zuletzt zugegriffen wurde.</span><span class="sxs-lookup"><span data-stu-id="d69a8-141">If the specified provider supports more than one drive, this cmdlet returns the location on the most recently accessed drive.</span></span>

<span data-ttu-id="d69a8-142">Wenn Sie sich z. b. auf dem `C:` Laufwerk befinden, können Sie diesen Parameter verwenden, um den aktuellen Speicherort auf den Laufwerken des PowerShell- **Registrierungs** Anbieters zu finden.</span><span class="sxs-lookup"><span data-stu-id="d69a8-142">For example, if you are in the `C:` drive, you can use this parameter to find your current location in the drives of the PowerShell **Registry** provider.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d69a8-143">-Stack</span><span class="sxs-lookup"><span data-stu-id="d69a8-143">-Stack</span></span>

<span data-ttu-id="d69a8-144">Gibt an, dass dieses Cmdlet die Speicherorte anzeigt, die dem aktuellen Speicher Stapel hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d69a8-144">Indicates that this cmdlet displays the locations added to the current location stack.</span></span> <span data-ttu-id="d69a8-145">Mithilfe des-Cmdlets können Sie Stapel Speicherorte hinzufügen `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-145">You can add locations to stacks by using the `Push-Location` cmdlet.</span></span>

<span data-ttu-id="d69a8-146">Verwenden Sie den **stackname** -Parameter, um die Speicherorte in einem anderen Speicher Stapel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d69a8-146">To display the locations in a different location stack, use the **StackName** parameter.</span></span> <span data-ttu-id="d69a8-147">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="d69a8-147">For information about location stacks, see the [Notes](#notes).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d69a8-148">-Stackname</span><span class="sxs-lookup"><span data-stu-id="d69a8-148">-StackName</span></span>

<span data-ttu-id="d69a8-149">Gibt die benannten Positions Stapel als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="d69a8-149">Specifies, as a string array, the named location stacks.</span></span> <span data-ttu-id="d69a8-150">Geben Sie Speicherstapelnamen ein.</span><span class="sxs-lookup"><span data-stu-id="d69a8-150">Enter one or more location stack names.</span></span>

<span data-ttu-id="d69a8-151">Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d69a8-151">To display the locations in the current location stack, use the **Stack** parameter.</span></span> <span data-ttu-id="d69a8-152">Verwenden Sie das-Cmdlet, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-152">To make a location stack the current location stack, use the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="d69a8-153">Dieses Cmdlet kann die Speicherorte im unbenannten Standard Stapel nicht anzeigen, es sei denn, es handelt sich um den aktuellen Stapel.</span><span class="sxs-lookup"><span data-stu-id="d69a8-153">This cmdlet cannot display the locations in the unnamed default stack unless it is the current stack.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d69a8-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d69a8-154">CommonParameters</span></span>

<span data-ttu-id="d69a8-155">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d69a8-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d69a8-156">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d69a8-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d69a8-157">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d69a8-157">INPUTS</span></span>

### <span data-ttu-id="d69a8-158">Keine</span><span class="sxs-lookup"><span data-stu-id="d69a8-158">None</span></span>

<span data-ttu-id="d69a8-159">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="d69a8-159">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d69a8-160">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d69a8-160">OUTPUTS</span></span>

### <span data-ttu-id="d69a8-161">System. Management. Automation. PathInfo oder System. Management. Automation. pathinfostack</span><span class="sxs-lookup"><span data-stu-id="d69a8-161">System.Management.Automation.PathInfo or System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="d69a8-162">Wenn Sie den **Stack** -Parameter oder den **stackname** -Parameter verwenden, gibt dieses Cmdlet ein " **pthinfostack** "-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="d69a8-162">If you use the **Stack** or **StackName** parameters, this cmdlet returns a **PathInfoStack** object.</span></span> <span data-ttu-id="d69a8-163">Andernfalls wird ein **pathinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d69a8-163">Otherwise, it returns a **PathInfo** object.</span></span>

## <span data-ttu-id="d69a8-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d69a8-164">NOTES</span></span>

<span data-ttu-id="d69a8-165">PowerShell unterstützt mehrere Runspaces pro Prozess.</span><span class="sxs-lookup"><span data-stu-id="d69a8-165">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="d69a8-166">Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.</span><span class="sxs-lookup"><span data-stu-id="d69a8-166">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="d69a8-167">Dies ist nicht identisch mit `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-167">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="d69a8-168">Dieses Verhalten kann ein Problem sein, wenn Sie .NET-APIs aufrufen oder native Anwendungen ausführen, ohne explizite Verzeichnispfade bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d69a8-168">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>
<span data-ttu-id="d69a8-169">Mit dem- `Get-Location` Cmdlet wird das aktuelle Verzeichnis des aktuellen PowerShell-Runspace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d69a8-169">The `Get-Location` cmdlet returns the current directory of the current PowerShell runspace.</span></span>

<span data-ttu-id="d69a8-170">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d69a8-170">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d69a8-171">Um die Anbieter in Ihrer Sitzung aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-171">To list the providers in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d69a8-172">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d69a8-172">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="d69a8-173">Die Art und Weise, in der die Parameter **psprovider** , **PSDrive** , **Stack** und **stackname** interagieren, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="d69a8-173">The ways that the **PSProvider** , **PSDrive** , **Stack** , and **StackName** parameters interact depends on the provider.</span></span> <span data-ttu-id="d69a8-174">Bestimmte Kombinationen führen zu Fehlern, beispielsweise wenn ein Laufwerk zusammen mit einem Anbieter angegeben wird, der das betreffende Laufwerk nicht verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="d69a8-174">Some combinations will result in errors, such as specifying both a drive and a provider that does not expose that drive.</span></span> <span data-ttu-id="d69a8-175">Wenn keine Parameter angegeben werden, gibt dieses Cmdlet das **pathinfo** -Objekt für den Anbieter zurück, der den aktuellen Arbeits Speicherort enthält.</span><span class="sxs-lookup"><span data-stu-id="d69a8-175">If no parameters are specified, this cmdlet returns the **PathInfo** object for the provider that contains the current working location.</span></span>

<span data-ttu-id="d69a8-176">Bei einem Stapel handelt es sich um eine Last-in-First-out-Liste, in der nur auf das zuletzt hinzugefügte Element zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d69a8-176">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span> <span data-ttu-id="d69a8-177">Sie fügen einem Stapel Elemente in der Reihenfolge hinzu, in der Sie sie verwenden. Anschließend rufen Sie sie zur Verwendung in der umgekehrten Reihenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="d69a8-177">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="d69a8-178">Mit PowerShell können Sie Anbieter Speicherorte in Speicherort Stapeln speichern.</span><span class="sxs-lookup"><span data-stu-id="d69a8-178">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="d69a8-179">Von PowerShell wird ein unbenannter Standard Speicher Stapel erstellt, und Sie können mehrere benannte Speicher Stapel erstellen.</span><span class="sxs-lookup"><span data-stu-id="d69a8-179">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="d69a8-180">Wenn Sie keinen Stapelnamen angeben, verwendet PowerShell den aktuellen Speicher Stapel.</span><span class="sxs-lookup"><span data-stu-id="d69a8-180">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="d69a8-181">Standardmäßig ist der unbenannte Standard Speicherort der aktuelle Speicher Stapel. Sie können das `Set-Location` Cmdlet jedoch verwenden, um den aktuellen Speicher Stapel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d69a8-181">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="d69a8-182">Verwenden Sie zum Verwalten von Speicherort Stapeln die PowerShell- `*-Location` Cmdlets wie folgt.</span><span class="sxs-lookup"><span data-stu-id="d69a8-182">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows.</span></span>

- <span data-ttu-id="d69a8-183">Verwenden Sie das-Cmdlet, um einen Speicherort zu einem Speicherort Stapel hinzuzufügen `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-183">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="d69a8-184">Verwenden Sie das-Cmdlet, um einen Speicherort aus einem Speicherort Stapel zu erhalten `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-184">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="d69a8-185">Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter des `Get-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d69a8-185">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="d69a8-186">Um die Speicherorte in einem benannten Positions Stapel anzuzeigen, verwenden Sie den **stackname** -Parameter des `Get-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d69a8-186">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="d69a8-187">Um einen neuen Speicherort Stapel zu erstellen, verwenden Sie den **stackname** -Parameter des `Push-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d69a8-187">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span>
  <span data-ttu-id="d69a8-188">Wenn Sie einen Stapel angeben, der nicht vorhanden ist, wird `Push-Location` der Stapel von erstellt.</span><span class="sxs-lookup"><span data-stu-id="d69a8-188">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="d69a8-189">Verwenden Sie den **stackname** -Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="d69a8-189">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="d69a8-190">Auf den unbenannten Standardspeicherstapel kann nur vollständig zugegriffen werden, wenn es sich dabei um den aktuellen Speicherstapel handelt.</span><span class="sxs-lookup"><span data-stu-id="d69a8-190">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="d69a8-191">Wenn Sie einen benannten Speicherort Stapel zum aktuellen Speicher Stapel machen, können Sie die `Push-Location` Cmdlets oder nicht mehr verwenden, `Pop-Location` um Elemente zum Standard Stapel hinzuzufügen oder daraus zu machen. Sie können auch das Cmdlet verwenden, um die Speicherorte im unbenannten Stapel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d69a8-191">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use this cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="d69a8-192">Um den unbenannten Stapel zum aktuellen Stapel zu machen, verwenden Sie den **stackname** -Parameter des `Set-Location` Cmdlets mit dem Wert `$null` oder einer leeren Zeichenfolge ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="d69a8-192">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="d69a8-193">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d69a8-193">RELATED LINKS</span></span>

[<span data-ttu-id="d69a8-194">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="d69a8-194">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="d69a8-195">Push-Location</span><span class="sxs-lookup"><span data-stu-id="d69a8-195">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="d69a8-196">Set-Location</span><span class="sxs-lookup"><span data-stu-id="d69a8-196">Set-Location</span></span>](Set-Location.md)
