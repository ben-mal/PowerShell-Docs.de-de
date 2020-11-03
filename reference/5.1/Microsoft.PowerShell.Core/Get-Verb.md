---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/07/2018
Module Name: Microsoft.PowerShell.Core
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/functions/get-verb?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 4474bb50c2bf3be10e72d2554190208e956f9040
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "93219495"
---
# <span data-ttu-id="6924d-103">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="6924d-103">Get-Verb</span></span>

## <span data-ttu-id="6924d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6924d-104">SYNOPSIS</span></span>
<span data-ttu-id="6924d-105">Ruft genehmigte PowerShell-Verben ab.</span><span class="sxs-lookup"><span data-stu-id="6924d-105">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="6924d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6924d-106">SYNTAX</span></span>

```
Get-Verb [[-verb] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="6924d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6924d-107">DESCRIPTION</span></span>

<span data-ttu-id="6924d-108">Die `Get-Verb` Funktion ruft Verben ab, die für die Verwendung in PowerShell-Befehlen genehmigt sind.</span><span class="sxs-lookup"><span data-stu-id="6924d-108">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="6924d-109">PowerShell empfiehlt, dass Cmdlet-und Funktionsnamen das Verb-Noun Format aufweisen und ein genehmigtes Verb enthalten.</span><span class="sxs-lookup"><span data-stu-id="6924d-109">PowerShell recommends cmdlet and function names have the Verb-Noun format and include an approved verb.</span></span> <span data-ttu-id="6924d-110">Durch diese Vorgehensweise werden Befehlsnamen Koner, vorhersag barer und einfacher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6924d-110">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="6924d-111">Befehle, die nicht genehmigte Verben verwenden, werden in PowerShell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6924d-111">Commands that use unapproved verbs run in PowerShell.</span></span> <span data-ttu-id="6924d-112">Wenn Sie jedoch ein Modul importieren, das einen Befehl mit einem nicht genehmigten Verb in seinem Namen enthält, `Import-Module` zeigt der Befehl eine Warnmeldung an.</span><span class="sxs-lookup"><span data-stu-id="6924d-112">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="6924d-113">Die von zurückgegebene Verb Liste ist `Get-Verb` möglicherweise nicht fertig.</span><span class="sxs-lookup"><span data-stu-id="6924d-113">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="6924d-114">Eine aktualisierte Liste genehmigter PowerShell-Verben mit Beschreibungen finden Sie unter [genehmigte Verben](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in der Microsoft-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6924d-114">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="6924d-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6924d-115">EXAMPLES</span></span>

### <span data-ttu-id="6924d-116">Beispiel 1: erhalten einer Liste aller Verben</span><span class="sxs-lookup"><span data-stu-id="6924d-116">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="6924d-117">Beispiel 2: erhalten einer Liste genehmigter Verben, die mit "UN" beginnen</span><span class="sxs-lookup"><span data-stu-id="6924d-117">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

```powershell
Get-Verb un*
```

```Output
Verb                 Group
----                 -----
Undo                 Common
Unlock               Common
Unpublish            Data
Uninstall            Lifecycle
Unregister           Lifecycle
Unblock              Security
Unprotect            Security
```

### <span data-ttu-id="6924d-118">Beispiel 3: alle genehmigten Verben in der Sicherheitsgruppe erhalten</span><span class="sxs-lookup"><span data-stu-id="6924d-118">Example 3 - Get all approved verbs in the Security group</span></span>

```powershell
Get-Verb | Where-Object Group -EQ Security
```

```Output
Verb      Group
----      -----
Block     Security
Grant     Security
Protect   Security
Revoke    Security
Unblock   Security
Unprotect Security
```

### <span data-ttu-id="6924d-119">Beispiel 4: sucht alle Befehle in einem Modul, die nicht genehmigte Verben aufweisen</span><span class="sxs-lookup"><span data-stu-id="6924d-119">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="6924d-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6924d-120">PARAMETERS</span></span>

### <span data-ttu-id="6924d-121">-Verb</span><span class="sxs-lookup"><span data-stu-id="6924d-121">-verb</span></span>

<span data-ttu-id="6924d-122">Ruft nur die angegebenen Verben ab.</span><span class="sxs-lookup"><span data-stu-id="6924d-122">Gets only the specified verbs.</span></span>
<span data-ttu-id="6924d-123">Geben Sie den Namen eines Verbs oder ein Namensmuster ein.</span><span class="sxs-lookup"><span data-stu-id="6924d-123">Enter the name of a verb or a name pattern.</span></span>
<span data-ttu-id="6924d-124">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="6924d-124">Wildcards are allowed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: All verbs
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## <span data-ttu-id="6924d-125">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6924d-125">INPUTS</span></span>

### <span data-ttu-id="6924d-126">Keine</span><span class="sxs-lookup"><span data-stu-id="6924d-126">None</span></span>

## <span data-ttu-id="6924d-127">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6924d-127">OUTPUTS</span></span>

### <span data-ttu-id="6924d-128">Selected.Microsoft.PowerShell.Commands.MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="6924d-128">Selected.Microsoft.PowerShell.Commands.MemberDefinition</span></span>

## <span data-ttu-id="6924d-129">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6924d-129">NOTES</span></span>

<span data-ttu-id="6924d-130">`Get-Verb` gibt eine geänderte Version eines Microsoft. PowerShell. Commands. Membership Definition-Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="6924d-130">`Get-Verb` returns a modified version of a Microsoft.PowerShell.Commands.MemberDefinition object.</span></span>
<span data-ttu-id="6924d-131">Das Objekt muss nicht die Standardeigenschaften eines MemberDefinition-Objekts besitzen.</span><span class="sxs-lookup"><span data-stu-id="6924d-131">The object does not have the standard properties of a MemberDefinition object.</span></span> <span data-ttu-id="6924d-132">Stattdessen hat es Verb- und Gruppeneigenschaften.</span><span class="sxs-lookup"><span data-stu-id="6924d-132">Instead it has Verb and Group properties.</span></span> <span data-ttu-id="6924d-133">Die Verb-Eigenschaft enthält eine Zeichenfolge mit dem Verbnamen.</span><span class="sxs-lookup"><span data-stu-id="6924d-133">The Verb property contains a string with the verb name.</span></span> <span data-ttu-id="6924d-134">Die Group-Eigenschaft enthält eine Zeichenfolge mit der Verbgruppe.</span><span class="sxs-lookup"><span data-stu-id="6924d-134">The Group property contains a string with the verb group.</span></span>

<span data-ttu-id="6924d-135">PowerShell-Verben werden einer Gruppe basierend auf Ihrer gängigsten Verwendung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6924d-135">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="6924d-136">Die Gruppen sind so gestaltet, dass die Verben leicht zu finden und zu vergleichen sind, nicht um ihre Verwendung zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="6924d-136">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="6924d-137">Sie können alle genehmigten Verben für jeden Typ von Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="6924d-137">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="6924d-138">Jedes PowerShell-Verb ist einer der folgenden Gruppen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6924d-138">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="6924d-139">Common: definieren Sie generische Aktionen, die auf fast alle Cmdlets, z. b. Add, angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6924d-139">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="6924d-140">Kommunikation: definieren Sie Aktionen, die für die Kommunikation gelten, z. b. Connect.</span><span class="sxs-lookup"><span data-stu-id="6924d-140">Communications:  Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="6924d-141">Daten: definieren Sie Aktionen, die für die Datenverarbeitung gelten, wie z. b. Backup.</span><span class="sxs-lookup"><span data-stu-id="6924d-141">Data:  Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="6924d-142">Diagnose: definieren Sie Aktionen, die für die Diagnose gelten, z. b. Debug.</span><span class="sxs-lookup"><span data-stu-id="6924d-142">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="6924d-143">Lebenszyklus: definieren Sie Aktionen, die für den Lebenszyklus eines Cmdlets gelten, z. b. "Complete".</span><span class="sxs-lookup"><span data-stu-id="6924d-143">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="6924d-144">Sicherheit: definieren Sie Aktionen, die auf Sicherheit angewendet werden, z. b. widerrufen.</span><span class="sxs-lookup"><span data-stu-id="6924d-144">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="6924d-145">Sonstige: definieren Sie andere Arten von Aktionen.</span><span class="sxs-lookup"><span data-stu-id="6924d-145">Other: Define other types of actions.</span></span>

<span data-ttu-id="6924d-146">Einige der Cmdlets, die mit PowerShell installiert werden, wie z `Tee-Object` `Where-Object` . b. und, verwenden nicht genehmigte Verben.</span><span class="sxs-lookup"><span data-stu-id="6924d-146">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="6924d-147">Diese Cmdlets sind historische Ausnahmen und ihre Verben werden als **reserviert** klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="6924d-147">These cmdlets are historic exceptions and their verbs are classified as **reserved**.</span></span>

## <span data-ttu-id="6924d-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6924d-148">RELATED LINKS</span></span>

[<span data-ttu-id="6924d-149">Import-Module</span><span class="sxs-lookup"><span data-stu-id="6924d-149">Import-Module</span></span>](import-module.md)
