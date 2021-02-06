---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-modulemember?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ModuleMember
ms.openlocfilehash: fcb9af654f9e95f44e49ea984294b80752aa3453
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600487"
---
# <span data-ttu-id="82b6f-102">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="82b6f-102">Export-ModuleMember</span></span>

## <span data-ttu-id="82b6f-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="82b6f-103">SYNOPSIS</span></span>
<span data-ttu-id="82b6f-104">Gibt die Modulelemente an, die exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="82b6f-104">Specifies the module members that are exported.</span></span>

## <span data-ttu-id="82b6f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="82b6f-105">SYNTAX</span></span>

```
Export-ModuleMember [[-Function] <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="82b6f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="82b6f-106">DESCRIPTION</span></span>

<span data-ttu-id="82b6f-107">Das **Export-modulemember** -Cmdlet gibt die Modul Elemente an, die aus einer Skript Modul Datei (. psm1) exportiert werden, oder aus einem dynamischen Modul, das mit dem Cmdlet "New-Module" erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="82b6f-107">The **Export-ModuleMember** cmdlet specifies the module members that are exported from a script module (.psm1) file, or from a dynamic module created by using the New-Module cmdlet.</span></span>
<span data-ttu-id="82b6f-108">Zu den Modulmembern gehören Cmdlets, Funktionen, Variablen und Aliase.</span><span class="sxs-lookup"><span data-stu-id="82b6f-108">Module members include cmdlets, functions, variables, and aliases.</span></span>
<span data-ttu-id="82b6f-109">Dieses Cmdlet kann nur in einer Skriptmoduldatei oder einem dynamischen Modul verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82b6f-109">This cmdlet can be used only in a script module file or a dynamic module.</span></span>

<span data-ttu-id="82b6f-110">Wenn ein Skript Modul keinen **Export-modulemember** -Befehl enthält, werden die Funktionen und Aliase im Skript Modul exportiert, die Variablen jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="82b6f-110">If a script module does not include an **Export-ModuleMember** command, the functions and aliases in the script module are exported, but the variables are not.</span></span>
<span data-ttu-id="82b6f-111">Wenn ein Skript Modul **Export-modulemember** -Befehle enthält, werden nur die Elemente exportiert, die in den **Export-modulemember** -Befehlen angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="82b6f-111">When a script module includes **Export-ModuleMember** commands, only the members specified in the **Export-ModuleMember** commands are exported.</span></span>
<span data-ttu-id="82b6f-112">Sie können **Export-modulemember** auch verwenden, um Member, die das Skript Modul aus anderen Modulen importiert, zu unterdrücken oder zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="82b6f-112">You can also use **Export-ModuleMember** to suppress or export members that the script module imports from other modules.</span></span>

<span data-ttu-id="82b6f-113">Ein **Export-modulemember** -Befehl ist optional, aber es handelt sich um eine bewährte Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="82b6f-113">An **Export-ModuleMember** command is optional, but it is a best practice.</span></span>
<span data-ttu-id="82b6f-114">Auch wenn der Befehl die Standardwerte bestätigt, wird die Absicht des Modulautors veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="82b6f-114">Even if the command confirms the default values, it demonstrates the intention of the module author.</span></span>

## <span data-ttu-id="82b6f-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="82b6f-115">EXAMPLES</span></span>

### <span data-ttu-id="82b6f-116">Beispiel 1: Exportieren von Funktionen und Aliasen in einem Skript Modul</span><span class="sxs-lookup"><span data-stu-id="82b6f-116">Example 1: Export functions and aliases in a script module</span></span>

```powershell
Export-ModuleMember -Function * -Alias *
```

<span data-ttu-id="82b6f-117">Dieser Befehl exportiert alle Funktionen und Aliase, die im Skript Modul definiert sind.</span><span class="sxs-lookup"><span data-stu-id="82b6f-117">This command exports all the functions and aliases defined in the script module.</span></span>

### <span data-ttu-id="82b6f-118">Beispiel 2: Exportieren spezifischer Aliase und Funktionen</span><span class="sxs-lookup"><span data-stu-id="82b6f-118">Example 2: Export specific aliases and functions</span></span>

```powershell
Export-ModuleMember -Function Get-Test, New-Test, Start-Test -Alias gtt, ntt, stt
```

<span data-ttu-id="82b6f-119">Dieser Befehl exportiert die drei Aliase und drei Funktionen, die im Skriptmodul definiert sind.</span><span class="sxs-lookup"><span data-stu-id="82b6f-119">This command exports three aliases and three functions defined in the script module.</span></span>

<span data-ttu-id="82b6f-120">Verwenden Sie dieses Befehlsformat, um Namen der Modulelemente anzugeben.</span><span class="sxs-lookup"><span data-stu-id="82b6f-120">You can use this command format to specify the names of module members.</span></span>

### <span data-ttu-id="82b6f-121">Beispiel 3: Exportieren von keinen Membern</span><span class="sxs-lookup"><span data-stu-id="82b6f-121">Example 3: Export no members</span></span>

```powershell
Export-ModuleMember
```

<span data-ttu-id="82b6f-122">Dieser Befehl gibt an, dass keine im Skriptmodul definierten Elemente exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="82b6f-122">This command specifies that no members defined in the script module are exported.</span></span>

<span data-ttu-id="82b6f-123">Dieser Befehl verhindert, dass Modulelemente exportiert werden, blendet die Elemente aber nicht aus.</span><span class="sxs-lookup"><span data-stu-id="82b6f-123">This command prevents the module members from being exported, but it does not hide the members.</span></span>
<span data-ttu-id="82b6f-124">Die Benutzer können Modulelemente lesen und kopieren oder den Aufrufoperator (&) verwenden, um Modulelemente aufzurufen, die nicht exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="82b6f-124">Users can read and copy module members or use the call operator (&) to invoke module members that are not exported.</span></span>

### <span data-ttu-id="82b6f-125">Beispiel 4: Exportieren einer bestimmten Variablen</span><span class="sxs-lookup"><span data-stu-id="82b6f-125">Example 4: Export a specific variable</span></span>

```powershell
Export-ModuleMember -Variable increment
```

<span data-ttu-id="82b6f-126">Dieser Befehl exportiert nur die $increment-Variable aus dem Skriptmodul.</span><span class="sxs-lookup"><span data-stu-id="82b6f-126">This command exports only the $increment variable from the script module.</span></span>
<span data-ttu-id="82b6f-127">Keine anderen Elemente werden exportiert.</span><span class="sxs-lookup"><span data-stu-id="82b6f-127">No other members are exported.</span></span>

<span data-ttu-id="82b6f-128">Wenn Sie eine Variable exportieren möchten, zusätzlich zum Exportieren der Funktionen in einem Modul, muss der **Export-modulemember** -Befehl die Namen aller Funktionen und den Namen der Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="82b6f-128">If you want to export a variable, in addition to exporting the functions in a module, the **Export-ModuleMember** command must include the names of all of the functions and the name of the variable.</span></span>

### <span data-ttu-id="82b6f-129">Beispiel 5: mehrere Export Befehle</span><span class="sxs-lookup"><span data-stu-id="82b6f-129">Example 5: Multiple export commands</span></span>

```powershell
# From TestModule.psm1
Function New-Test
{
    Write-Output 'I am New-Test function'
}
Export-ModuleMember -Function New-Test

function Validate-Test
{
    Write-Output 'I am Validate-Test function'
}
function Start-Test
{
    Write-Output 'I am Start-Test function'
}
Set-Alias stt Start-Test
Export-ModuleMember -Function Start-Test -Alias stt
```

<span data-ttu-id="82b6f-130">Diese Befehle zeigen, wie mehrere **Export-modulemember** -Befehle in einer Skript Modul Datei (. psm1) interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="82b6f-130">These commands show how multiple **Export-ModuleMember** commands are interpreted in a script module (.psm1) file.</span></span>

<span data-ttu-id="82b6f-131">Diese Befehle erstellen drei Funktionen und einen Alias und exportieren sie dann.</span><span class="sxs-lookup"><span data-stu-id="82b6f-131">These commands create three functions and one alias, and then they export two of the functions and the alias.</span></span>

<span data-ttu-id="82b6f-132">Ohne die **Export-modulemember** -Befehle würden alle drei Funktionen und der Alias exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="82b6f-132">Without the **Export-ModuleMember** commands, all three of the functions and the alias would be exported.</span></span>
<span data-ttu-id="82b6f-133">Mit den **Export-modulemember** -Befehlen werden nur die Funktionen **New-Test** und **Start-Test** und der STT-Alias exportiert.</span><span class="sxs-lookup"><span data-stu-id="82b6f-133">With the **Export-ModuleMember** commands, only the **New-Test** and **Start-Test** functions and the STT alias are exported.</span></span>

### <span data-ttu-id="82b6f-134">Beispiel 6: Exportieren von Membern in einem dynamischen Modul</span><span class="sxs-lookup"><span data-stu-id="82b6f-134">Example 6: Export members in a dynamic module</span></span>

```powershell
New-Module -Script {function SayHello {"Hello!"}; Set-Alias Hi SayHello; Export-ModuleMember -Alias Hi -Function SayHello}
```

<span data-ttu-id="82b6f-135">Dieser Befehl zeigt, wie Export-ModuleMember in einem dynamischen Modul verwendet wird, das mit dem **New-Module-** Cmdlet erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="82b6f-135">This command shows how to use Export-ModuleMember in a dynamic module that is created by using the **New-Module** cmdlet.</span></span>

<span data-ttu-id="82b6f-136">In diesem Beispiel wird **Export-modulemember** zum Exportieren des HI-Alias und der Funktion " **sayHello** " im dynamischen Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="82b6f-136">In this example, **Export-ModuleMember** is used to export both the Hi alias and the **SayHello** function in the dynamic module.</span></span>

### <span data-ttu-id="82b6f-137">Beispiel 7: Deklarieren und Exportieren einer Funktion in einem einzelnen Befehl</span><span class="sxs-lookup"><span data-stu-id="82b6f-137">Example 7: Declare and export a function in a single command</span></span>

```powershell
# From TestModule.psm1
function Export
{
  param (
    [Parameter(Mandatory=$true)]
    [ValidateSet("function","variable")]
    $Type,
    [Parameter(Mandatory=$true)]
    $Name,
    [Parameter(Mandatory=$true)]
    $Value
    )

    if ($Type -eq "function")
    {
        Set-item "function:script:$Name" $Value
        Export-ModuleMember $Name
    }
    else
    {
    Set-Variable -scope Script $Name $Value
    Export-ModuleMember -variable $Name
    }
}

Export function New-Test {Write-Output 'I am New-Test function'}
function helper {Write-Output 'I am helper function'}

Export variable Interval 0
$Interval = 2
```

<span data-ttu-id="82b6f-138">Dieses Beispiel enthält eine Funktion namens " **Export** ", die eine Funktion deklariert oder eine Variable erstellt und dann einen `Export-ModuleMember` Befehl für die Funktion oder Variable schreibt.</span><span class="sxs-lookup"><span data-stu-id="82b6f-138">This example includes a function named **Export** that declares a function or creates a variable, and then writes an `Export-ModuleMember` command for the function or variable.</span></span>
<span data-ttu-id="82b6f-139">Auf diese Weise können Sie eine Funktion oder Variable in einem einzigen Befehl deklarieren und exportieren.</span><span class="sxs-lookup"><span data-stu-id="82b6f-139">This lets you declare and export a function or variable in a single command.</span></span>

<span data-ttu-id="82b6f-140">Wenn Sie die **Export** -Funktion verwenden möchten, fügen Sie Sie in das Skript Modul ein.</span><span class="sxs-lookup"><span data-stu-id="82b6f-140">To use the **Export** function, include it in your script module.</span></span>
<span data-ttu-id="82b6f-141">Um eine Funktion zu exportieren, geben Sie `Export` vor dem **Function** -Schlüsselwort ein.</span><span class="sxs-lookup"><span data-stu-id="82b6f-141">To export a function, type `Export` before the **Function** keyword.</span></span>

<span data-ttu-id="82b6f-142">Um eine Variable zu exportieren, verwenden Sie folgendes Format, um die Variable zu deklarieren und ihren Wert festzulegen:</span><span class="sxs-lookup"><span data-stu-id="82b6f-142">To export a variable, use the following format to declare the variable and set its value:</span></span>

`Export variable <variable-name> <value>`

<span data-ttu-id="82b6f-143">Die Befehle im Beispiel zeigen das richtige Format.</span><span class="sxs-lookup"><span data-stu-id="82b6f-143">The commands in the example show the correct format.</span></span>
<span data-ttu-id="82b6f-144">In diesem Beispiel werden nur die **New-Test-** Funktion und die $Interval-Variable exportiert.</span><span class="sxs-lookup"><span data-stu-id="82b6f-144">In this example, only the **New-Test** function and the $Interval variable are exported.</span></span>

## <span data-ttu-id="82b6f-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="82b6f-145">PARAMETERS</span></span>

### <span data-ttu-id="82b6f-146">-Alias</span><span class="sxs-lookup"><span data-stu-id="82b6f-146">-Alias</span></span>

<span data-ttu-id="82b6f-147">Gibt die Aliase an, die aus der Skriptmoduldatei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="82b6f-147">Specifies the aliases that are exported from the script module file.</span></span>
<span data-ttu-id="82b6f-148">Geben Sie die Aliasnamen ein.</span><span class="sxs-lookup"><span data-stu-id="82b6f-148">Enter the alias names.</span></span>
<span data-ttu-id="82b6f-149">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="82b6f-149">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="82b6f-150">-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="82b6f-150">-Cmdlet</span></span>

<span data-ttu-id="82b6f-151">Gibt die Cmdlets an, die aus der Skriptmoduldatei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="82b6f-151">Specifies the cmdlets that are exported from the script module file.</span></span>
<span data-ttu-id="82b6f-152">Geben Sie die Cmdlet-Namen ein.</span><span class="sxs-lookup"><span data-stu-id="82b6f-152">Enter the cmdlet names.</span></span>
<span data-ttu-id="82b6f-153">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="82b6f-153">Wildcard characters are permitted.</span></span>

<span data-ttu-id="82b6f-154">Sie können keine Cmdlets in einer Skriptmoduldatei erstellen, aber Sie können Cmdlets aus einem binären Modul in ein Skriptmodul importieren und dann erneut aus dem Skriptmodul exportieren.</span><span class="sxs-lookup"><span data-stu-id="82b6f-154">You cannot create cmdlets in a script module file, but you can import cmdlets from a binary module into a script module and re-export them from the script module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="82b6f-155">-Funktion</span><span class="sxs-lookup"><span data-stu-id="82b6f-155">-Function</span></span>

<span data-ttu-id="82b6f-156">Gibt die Funktionen an, die aus der Skriptmoduldatei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="82b6f-156">Specifies the functions that are exported from the script module file.</span></span>
<span data-ttu-id="82b6f-157">Geben Sie die Funktionsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="82b6f-157">Enter the function names.</span></span>
<span data-ttu-id="82b6f-158">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="82b6f-158">Wildcard characters are permitted.</span></span>
<span data-ttu-id="82b6f-159">Sie können auch Funktionsnamen-Zeichen folgen an **Export-modulemember** übergeben.</span><span class="sxs-lookup"><span data-stu-id="82b6f-159">You can also pipe function name strings to **Export-ModuleMember**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="82b6f-160">-Variable</span><span class="sxs-lookup"><span data-stu-id="82b6f-160">-Variable</span></span>

<span data-ttu-id="82b6f-161">Gibt die Variablen an, die aus der Skriptmoduldatei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="82b6f-161">Specifies the variables that are exported from the script module file.</span></span>
<span data-ttu-id="82b6f-162">Geben Sie die Variablennamen ohne Dollarzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="82b6f-162">Enter the variable names, without a dollar sign.</span></span>
<span data-ttu-id="82b6f-163">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="82b6f-163">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="82b6f-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="82b6f-164">CommonParameters</span></span>

<span data-ttu-id="82b6f-165">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="82b6f-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="82b6f-166">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="82b6f-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="82b6f-167">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="82b6f-167">INPUTS</span></span>

### <span data-ttu-id="82b6f-168">System.String</span><span class="sxs-lookup"><span data-stu-id="82b6f-168">System.String</span></span>

<span data-ttu-id="82b6f-169">Sie können Funktionsnamen-Zeichen folgen an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="82b6f-169">You can pipe function name strings to this cmdlet.</span></span>

## <span data-ttu-id="82b6f-170">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="82b6f-170">OUTPUTS</span></span>

### <span data-ttu-id="82b6f-171">Keine</span><span class="sxs-lookup"><span data-stu-id="82b6f-171">None</span></span>

<span data-ttu-id="82b6f-172">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="82b6f-172">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="82b6f-173">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="82b6f-173">NOTES</span></span>

* <span data-ttu-id="82b6f-174">Um ein Element aus der Liste der exportierten Elemente auszuschließen, fügen Sie einen **Export-modulemember** -Befehl hinzu, der alle anderen Member auflistet, aber das Element auslässt, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="82b6f-174">To exclude a member from the list of exported members, add an **Export-ModuleMember** command that lists all other members but omits the member that you want to exclude.</span></span>

## <span data-ttu-id="82b6f-175">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="82b6f-175">RELATED LINKS</span></span>

[<span data-ttu-id="82b6f-176">Get-Module</span><span class="sxs-lookup"><span data-stu-id="82b6f-176">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="82b6f-177">Import-Module</span><span class="sxs-lookup"><span data-stu-id="82b6f-177">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="82b6f-178">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="82b6f-178">Remove-Module</span></span>](Remove-Module.md)

