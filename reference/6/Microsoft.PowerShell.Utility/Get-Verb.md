---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/07/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-verb?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 516ecf2b5d6e3bce2a0cda7c36c143d2ba75933a
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "93219508"
---
# <span data-ttu-id="b07d8-103">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="b07d8-103">Get-Verb</span></span>

## <span data-ttu-id="b07d8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b07d8-104">SYNOPSIS</span></span>
<span data-ttu-id="b07d8-105">Ruft genehmigte PowerShell-Verben ab.</span><span class="sxs-lookup"><span data-stu-id="b07d8-105">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="b07d8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b07d8-106">SYNTAX</span></span>

```
Get-Verb [[-Verb] <String[]>] [[-Group] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="b07d8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b07d8-107">DESCRIPTION</span></span>

<span data-ttu-id="b07d8-108">Die `Get-Verb` Funktion ruft Verben ab, die für die Verwendung in PowerShell-Befehlen genehmigt sind.</span><span class="sxs-lookup"><span data-stu-id="b07d8-108">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="b07d8-109">Es wird empfohlen, dass PowerShell-Cmdlet-und Funktionsnamen das `Verb-Noun` Format aufweisen und ein genehmigtes Verb enthalten.</span><span class="sxs-lookup"><span data-stu-id="b07d8-109">It is recommended that PowerShell cmdlet and function names have the `Verb-Noun` format and include an approved verb.</span></span> <span data-ttu-id="b07d8-110">Durch diese Vorgehensweise werden Befehlsnamen Koner, vorhersag barer und einfacher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b07d8-110">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="b07d8-111">Befehle, die nicht genehmigte Verben verwenden, werden weiterhin in PowerShell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b07d8-111">Commands that use unapproved verbs, still run in PowerShell.</span></span> <span data-ttu-id="b07d8-112">Wenn Sie jedoch ein Modul importieren, das einen Befehl mit einem nicht genehmigten Verb in seinem Namen enthält, `Import-Module` zeigt der Befehl eine Warnmeldung an.</span><span class="sxs-lookup"><span data-stu-id="b07d8-112">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="b07d8-113">Die von zurückgegebene Verb Liste ist `Get-Verb` möglicherweise nicht fertig.</span><span class="sxs-lookup"><span data-stu-id="b07d8-113">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="b07d8-114">Eine aktualisierte Liste genehmigter PowerShell-Verben mit Beschreibungen finden Sie unter [genehmigte Verben](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in der Microsoft-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b07d8-114">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="b07d8-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b07d8-115">Examples</span></span>

### <span data-ttu-id="b07d8-116">Beispiel 1: erhalten einer Liste aller Verben</span><span class="sxs-lookup"><span data-stu-id="b07d8-116">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="b07d8-117">Beispiel 2: erhalten einer Liste genehmigter Verben, die mit "UN" beginnen</span><span class="sxs-lookup"><span data-stu-id="b07d8-117">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

```powershell
Get-Verb un*
```

```Output
Verb       AliasPrefix Group     Description
----       ----------- -----     -----------
Undo       un          Common    Sets a resource to its previous state
Unlock     uk          Common    Releases a resource that was locked
Unpublish  ub          Data      Makes a resource unavailable to others
Uninstall  us          Lifecycle Removes a resource from an indicated location
Unregister ur          Lifecycle Removes the entry for a resource from a repository
Unblock    ul          Security  Removes restrictions to a resource
Unprotect  up          Security  Removes safeguards from a resource that were added to prevent it from attack or loss
```

### <span data-ttu-id="b07d8-118">Beispiel 3: alle genehmigten Verben in der Sicherheitsgruppe erhalten</span><span class="sxs-lookup"><span data-stu-id="b07d8-118">Example 3 - Get all approved verbs in the Security group</span></span>

```powershell
Get-Verb -Group Security
```

```Output
Verb      AliasPrefix Group    Description
----      ----------- -----    -----------
Block     bl          Security Restricts access to a resource
Grant     gr          Security Allows access to a resource
Protect   pt          Security Safeguards a resource from attack or loss
Revoke    rk          Security Specifies an action that does not allow access to a resource
Unblock   ul          Security Removes restrictions to a resource
Unprotect up          Security Removes safeguards from a resource that were added to prevent it from attack or loss
```

### <span data-ttu-id="b07d8-119">Beispiel 4: sucht alle Befehle in einem Modul, die nicht genehmigte Verben aufweisen</span><span class="sxs-lookup"><span data-stu-id="b07d8-119">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="b07d8-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b07d8-120">PARAMETERS</span></span>

### <span data-ttu-id="b07d8-121">-Verb</span><span class="sxs-lookup"><span data-stu-id="b07d8-121">-Verb</span></span>

<span data-ttu-id="b07d8-122">Ruft nur die angegebenen Verben ab.</span><span class="sxs-lookup"><span data-stu-id="b07d8-122">Gets only the specified verbs.</span></span> <span data-ttu-id="b07d8-123">Geben Sie den Namen eines Verbs oder ein Namensmuster ein.</span><span class="sxs-lookup"><span data-stu-id="b07d8-123">Enter the name of a verb or a name pattern.</span></span> <span data-ttu-id="b07d8-124">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b07d8-124">Wildcards are allowed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Common, Communications, Data, Diagnostic, Lifecycle, Other, Security

Required: False
Position: 1
Default value: All groups
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="b07d8-125">-Group</span><span class="sxs-lookup"><span data-stu-id="b07d8-125">-Group</span></span>

<span data-ttu-id="b07d8-126">Ruft nur die angegebenen Gruppen ab.</span><span class="sxs-lookup"><span data-stu-id="b07d8-126">Gets only the specified groups.</span></span> <span data-ttu-id="b07d8-127">Geben Sie den Namen einer Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="b07d8-127">Enter the name of a group.</span></span> <span data-ttu-id="b07d8-128">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="b07d8-128">Wildcards are not allowed.</span></span>

<span data-ttu-id="b07d8-129">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b07d8-129">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All verbs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b07d8-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b07d8-130">CommonParameters</span></span>

<span data-ttu-id="b07d8-131">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b07d8-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b07d8-132">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b07d8-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b07d8-133">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b07d8-133">INPUTS</span></span>

### <span data-ttu-id="b07d8-134">Keine</span><span class="sxs-lookup"><span data-stu-id="b07d8-134">None</span></span>

## <span data-ttu-id="b07d8-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b07d8-135">OUTPUTS</span></span>

### <span data-ttu-id="b07d8-136">System. Management. Automation. verbinfo</span><span class="sxs-lookup"><span data-stu-id="b07d8-136">System.Management.Automation.VerbInfo</span></span>

## <span data-ttu-id="b07d8-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b07d8-137">NOTES</span></span>

<span data-ttu-id="b07d8-138">PowerShell-Verben werden einer Gruppe basierend auf Ihrer gängigsten Verwendung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b07d8-138">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="b07d8-139">Die Gruppen sind so gestaltet, dass die Verben leicht zu finden und zu vergleichen sind, nicht um ihre Verwendung zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="b07d8-139">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="b07d8-140">Sie können alle genehmigten Verben für jeden Typ von Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="b07d8-140">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="b07d8-141">Jedes PowerShell-Verb ist einer der folgenden Gruppen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b07d8-141">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="b07d8-142">Common: definieren Sie generische Aktionen, die auf fast alle Cmdlets, z. b. Add, angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b07d8-142">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="b07d8-143">Kommunikation: definieren Sie Aktionen, die für die Kommunikation gelten, z. b. Connect.</span><span class="sxs-lookup"><span data-stu-id="b07d8-143">Communications: Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="b07d8-144">Daten: definieren Sie Aktionen, die für die Datenverarbeitung gelten, wie z. b. Backup.</span><span class="sxs-lookup"><span data-stu-id="b07d8-144">Data: Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="b07d8-145">Diagnose: definieren Sie Aktionen, die für die Diagnose gelten, z. b. Debug.</span><span class="sxs-lookup"><span data-stu-id="b07d8-145">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="b07d8-146">Lebenszyklus: definieren Sie Aktionen, die für den Lebenszyklus eines Cmdlets gelten, z. b. "Complete".</span><span class="sxs-lookup"><span data-stu-id="b07d8-146">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="b07d8-147">Sicherheit: definieren Sie Aktionen, die auf Sicherheit angewendet werden, z. b. widerrufen.</span><span class="sxs-lookup"><span data-stu-id="b07d8-147">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="b07d8-148">Sonstige: definieren Sie andere Arten von Aktionen.</span><span class="sxs-lookup"><span data-stu-id="b07d8-148">Other: Define other types of actions.</span></span>

<span data-ttu-id="b07d8-149">Einige der Cmdlets, die mit PowerShell installiert werden, wie z `Tee-Object` `Where-Object` . b. und, verwenden nicht genehmigte Verben.</span><span class="sxs-lookup"><span data-stu-id="b07d8-149">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="b07d8-150">Diese Cmdlets sind historische Ausnahmen und ihre Verben werden als **reserviert** klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="b07d8-150">These cmdlets are historic exceptions and their verbs are classified as **reserved**.</span></span>

## <span data-ttu-id="b07d8-151">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b07d8-151">RELATED LINKS</span></span>

[<span data-ttu-id="b07d8-152">Import-Module</span><span class="sxs-lookup"><span data-stu-id="b07d8-152">Import-Module</span></span>](../microsoft.powershell.core/import-module.md)
