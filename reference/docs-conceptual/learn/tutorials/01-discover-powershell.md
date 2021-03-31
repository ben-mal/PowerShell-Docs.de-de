---
title: PowerShell entdecken
ms.date: 03/12/2021
ms.custom: chnoring
ms.reviewer: sewhee
description: Erfahren Sie, was PowerShell ist, und erlernen Sie einige grundlegende Befehle, mit denen Sie PowerShell besser kennenlernen.
ms.openlocfilehash: 34bbd465a918224c203e7243834e7fb3a3a6070c
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "104730000"
---
# <a name="discover-powershell"></a><span data-ttu-id="44a93-103">PowerShell entdecken</span><span class="sxs-lookup"><span data-stu-id="44a93-103">Discover PowerShell</span></span>

<span data-ttu-id="44a93-104">PowerShell ist sowohl eine Befehlszeilenshell als auch eine Skriptsprache.</span><span class="sxs-lookup"><span data-stu-id="44a93-104">PowerShell is a command-line shell and a scripting language in one.</span></span> <span data-ttu-id="44a93-105">PowerShell wurde zunächst nur in Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="44a93-105">PowerShell started out on Windows.</span></span> <span data-ttu-id="44a93-106">Es war ursprünglich für die Automatisierung von Verwaltungsaufgaben vorgesehen, ist inzwischen jedoch plattformübergreifend und kann für eine Vielzahl von Aufgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44a93-106">It was meant to help with task automation for administration tasks but has now grown to be cross platform and can be used for a variety of tasks.</span></span>

<span data-ttu-id="44a93-107">PowerShell zeichnet sich dadurch aus, dass es anstelle von Text .NET-Objekte akzeptiert und zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="44a93-107">The thing that makes PowerShell unique is that accepts and returns .NET objects, rather than text.</span></span>
<span data-ttu-id="44a93-108">Dies erleichtert das Verbinden unterschiedlicher Befehle in einer _Pipeline_.</span><span class="sxs-lookup"><span data-stu-id="44a93-108">This fact makes it easier to connect different commands in series, in a _pipeline_.</span></span>

> [!NOTE]
> <span data-ttu-id="44a93-109">Pipelines werden in dieser Tutorialreihe ausführlicher behandelt.</span><span class="sxs-lookup"><span data-stu-id="44a93-109">Pipelines will be covered more in detail in this tutorial series.</span></span>

<span data-ttu-id="44a93-110">Die Ergebnisse müssen jedoch möglicherweise noch ein wenig _behandelt_ werden.</span><span class="sxs-lookup"><span data-stu-id="44a93-110">Even then, you might need to _massage_ the results a little.</span></span>

## <a name="what-can-powershell--be-used-for"></a><span data-ttu-id="44a93-111">Wofür lässt sich PowerShell verwenden?</span><span class="sxs-lookup"><span data-stu-id="44a93-111">What can PowerShell  be used for?</span></span>

<span data-ttu-id="44a93-112">PowerShell wird inzwischen für einen größeren Bereich als nur für Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="44a93-112">Usage of PowerShell has grown since the days when it was Windows-only.</span></span> <span data-ttu-id="44a93-113">Es wird immer noch für die Aufgabenautomatisierung unter Windows genutzt, Sie können es jedoch jetzt für eine Vielzahl von Aufgaben verwenden, z. B. die folgenden:</span><span class="sxs-lookup"><span data-stu-id="44a93-113">It's still used for Windows task automation, but today, you can use for a variety of tasks like:</span></span>

- <span data-ttu-id="44a93-114">**Cloudverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="44a93-114">**Cloud management**.</span></span> <span data-ttu-id="44a93-115">PowerShell lässt sich zum Verwalten von Cloudressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="44a93-115">PowerShell can be used to manage cloud resources.</span></span> <span data-ttu-id="44a93-116">Beispielsweise können Sie Informationen zu Cloudressourcen abrufen und Cloudressourcen aktualisieren oder neue Ressourcen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="44a93-116">For example, you can retrieve information about cloud resources, as well as update or deploy new resources.</span></span>
- <span data-ttu-id="44a93-117">**CI/CD**.</span><span class="sxs-lookup"><span data-stu-id="44a93-117">**CI/CD**.</span></span> <span data-ttu-id="44a93-118">PowerShell kann auch als Teil einer Continuous Integration/Continuous Deployment-Pipeline verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44a93-118">It can also be used as part of a Continuous Integration/Continuous Deployment pipeline.</span></span>
- <span data-ttu-id="44a93-119">**Automatisieren von Aufgaben für Active Directory und Exchange**.</span><span class="sxs-lookup"><span data-stu-id="44a93-119">**Automate tasks for Active Directory and Exchange**.</span></span> <span data-ttu-id="44a93-120">Sie können mit PowerShell fast jede Aufgabe unter Windows automatisieren, z. B. das Erstellen von Benutzern in Active Directory und von Postfächern in Exchange.</span><span class="sxs-lookup"><span data-stu-id="44a93-120">You can use it to automate almost any task on Windows like creating users in Active Directory and mailboxes in Exchange.</span></span>

<span data-ttu-id="44a93-121">Es gibt noch viele weitere Verwendungsbereiche. Der obigen Liste können Sie entnehmen, dass diese Bereiche erheblich erweitert wurden.</span><span class="sxs-lookup"><span data-stu-id="44a93-121">There are many more areas of usage but the list above gives you a hint that PowerShell has come a long way.</span></span>

## <a name="who-uses-powershell"></a><span data-ttu-id="44a93-122">Von wem wird PowerShell verwendet?</span><span class="sxs-lookup"><span data-stu-id="44a93-122">Who uses PowerShell?</span></span>

<span data-ttu-id="44a93-123">PowerShell ist sehr leistungsstark, und viele Personen in zahlreichen Rollen können von seiner Verwendung profitieren.</span><span class="sxs-lookup"><span data-stu-id="44a93-123">PowerShell is very powerful and a lot of people, working in multitude of roles, can benefit from using it.</span></span> <span data-ttu-id="44a93-124">Früher wurde PowerShell von der Systemadministratorrolle verwendet, inzwischen wird es jedoch von Personen in den Bereichen DevOps, CloudOps und von Entwicklern genutzt.</span><span class="sxs-lookup"><span data-stu-id="44a93-124">Traditionally, PowerShell has been used by the System Administrator role but is now being used by people calling themselves DevOps, Cloud Ops, and even Developers.</span></span>

## <a name="powershell-cmdlets"></a><span data-ttu-id="44a93-125">PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="44a93-125">PowerShell cmdlets</span></span>

<span data-ttu-id="44a93-126">PowerShell bietet Hunderte vorinstallierter Befehle.</span><span class="sxs-lookup"><span data-stu-id="44a93-126">PowerShell comes with hundreds of preinstalled commands.</span></span> <span data-ttu-id="44a93-127">PowerShell-Befehle werden als Cmdlets (ausgesprochen wie „Commandlets“) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="44a93-127">PowerShell command are called cmdlets; pronounced as "command-lets".</span></span>

<span data-ttu-id="44a93-128">Der Name jedes Cmdlets besteht aus einer Kombination von Verb und Nomen, wie beispielsweise in `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="44a93-128">The name of each cmdlet consists of a "Verb-Noun" pair; for example `Get-Process`.</span></span> <span data-ttu-id="44a93-129">Diese Namenskonvention erleichtert das Verständnis der Funktion des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="44a93-129">This naming convention makes it easier to understand what the cmdlet does.</span></span> <span data-ttu-id="44a93-130">Außerdem erleichtert sie die Suche nach einem Befehl.</span><span class="sxs-lookup"><span data-stu-id="44a93-130">It also make it easier to find the command your looking for.</span></span> <span data-ttu-id="44a93-131">Wenn Sie ein Cmdlet suchen, können Sie nach dem Verb oder dem Nomen filtern.</span><span class="sxs-lookup"><span data-stu-id="44a93-131">When looking for a cmdlet to use, you can filter on the verb or noun.</span></span>

### <a name="using-cmdlets-to-explore-powershell"></a><span data-ttu-id="44a93-132">Verwenden von Cmdlets zum Erkunden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="44a93-132">Using cmdlets to explore PowerShell</span></span>

<span data-ttu-id="44a93-133">Wenn Sie PowerShell zum ersten Mal verwenden, fühlen Sie sich vielleicht eingeschüchtert, weil Sie glauben, dass Ihnen noch viele Kenntnisse fehlen.</span><span class="sxs-lookup"><span data-stu-id="44a93-133">When you first pick up PowerShell, it might feel intimidating as there seems to be so much to learn.</span></span>
<span data-ttu-id="44a93-134">PowerShell ist jedoch so aufgebaut, dass Sie es in kleinen Schritten entsprechend Ihren Anforderungen erlernen können.</span><span class="sxs-lookup"><span data-stu-id="44a93-134">However, PowerShell is designed to help you learn a little at a time, as you need it.</span></span>

<span data-ttu-id="44a93-135">PowerShell enthält Cmdlets, die Ihnen helfen, PowerShell zu erkunden.</span><span class="sxs-lookup"><span data-stu-id="44a93-135">PowerShell includes cmdlets that help you discover PowerShell.</span></span> <span data-ttu-id="44a93-136">Mit den folgenden vier Cmdlets können Sie ermitteln, welche Befehle verfügbar sind, was sie ausführen und für welche Typen sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44a93-136">Using these three cmdlets, you can discover what commands available, what they do, and what types they operate on.</span></span>

- <span data-ttu-id="44a93-137">`Get-Verb`.</span><span class="sxs-lookup"><span data-stu-id="44a93-137">`Get-Verb`.</span></span> <span data-ttu-id="44a93-138">Dieser Befehl gibt eine Liste mit Verben zurück, die von den meisten Befehlen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44a93-138">Running this command returns a list of verbs that most commands adhere to.</span></span>
  <span data-ttu-id="44a93-139">Außerdem wird in der Antwort die Funktion des jeweiligen Verbs beschrieben.</span><span class="sxs-lookup"><span data-stu-id="44a93-139">Additionally, the response describes what these verbs does.</span></span> <span data-ttu-id="44a93-140">Da die meisten Befehle dieser Namenskonvention folgen, lässt sich aus dieser die Funktion eines Befehls erschließen. Dies hilft Ihnen nicht nur, den entsprechenden Befehl auszuwählen, sondern auch beim Erstellen eines Befehls, diesen zu benennen.</span><span class="sxs-lookup"><span data-stu-id="44a93-140">As most commands follow this naming, it sets expectations on what a command does, which helps you select the appropriate command but also what to name a command, should you be creating one.</span></span>
- <span data-ttu-id="44a93-141">`Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="44a93-141">`Get-Command`.</span></span> <span data-ttu-id="44a93-142">Dieser Befehl ruft eine Liste aller Befehle ab, die auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="44a93-142">This command retrieves a list of all commands installed on your machine.</span></span>
- <span data-ttu-id="44a93-143">`Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="44a93-143">`Get-Member`.</span></span> <span data-ttu-id="44a93-144">Mit diesem Befehl lässt sich für die objektbasierte Ausgabe ermitteln, welches Objekt, welche Eigenschaften und welche Methoden für einen Befehl verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="44a93-144">It operates on object based output and is able to discover what object, properties and methods are available for a command.</span></span>
- <span data-ttu-id="44a93-145">`Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="44a93-145">`Get-Help`.</span></span> <span data-ttu-id="44a93-146">Wenn Sie diesen Befehl mit dem Namen eines Befehls als Argument aufrufen, wird eine Hilfeseite angezeigt, auf der die verschiedenen Teile eines Befehls beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="44a93-146">Invoking this command with the name of a command as an argument displays a help page describing various parts of a command.</span></span>

<span data-ttu-id="44a93-147">Mit diesen Befehlen können Sie nahezu alles ermitteln, was Sie über PowerShell wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="44a93-147">Using these commands, you can discover almost anything you need to know about PowerShell.</span></span>

### <a name="verb"></a><span data-ttu-id="44a93-148">Verb</span><span class="sxs-lookup"><span data-stu-id="44a93-148">Verb</span></span>

<span data-ttu-id="44a93-149">Das Verb ist ein wichtiges Konzept in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44a93-149">Verb is an important concepts in PowerShell.</span></span> <span data-ttu-id="44a93-150">Es ist ein Benennungsstandard, dem die meisten Cmdlets entsprechen.</span><span class="sxs-lookup"><span data-stu-id="44a93-150">It's a naming standard that most cmdlets follow.</span></span> <span data-ttu-id="44a93-151">Sie müssen diesen Benennungsstandard befolgen, wenn Sie eigene Befehle schreiben.</span><span class="sxs-lookup"><span data-stu-id="44a93-151">It's also a naming standard you're expected to follow, once you write your own commands.</span></span> <span data-ttu-id="44a93-152">Das _Verb_ bezeichnet, was ausgeführt werden soll, z. B. das Lesen von Daten oder das Ändern von Daten.</span><span class="sxs-lookup"><span data-stu-id="44a93-152">The idea is that the _verb_ says what you're trying to do, read data or maybe change it.</span></span> <span data-ttu-id="44a93-153">PowerShell verfügt über eine standardisierte Liste von Verben.</span><span class="sxs-lookup"><span data-stu-id="44a93-153">PowerShell has a standardized list of verbs.</span></span> <span data-ttu-id="44a93-154">Um eine vollständige Liste aller möglichen Verben abzurufen, verwenden Sie das Cmdlet `Get-Verb`:</span><span class="sxs-lookup"><span data-stu-id="44a93-154">To get a full list of all possible verbs, use the `Get-Verb` cmdlet:</span></span>

```powershell
Get-Verb
```

<span data-ttu-id="44a93-155">Die Ausgabe des Cmdlets ist eine umfangreiche Liste von Verben.</span><span class="sxs-lookup"><span data-stu-id="44a93-155">The output from running it, is a long list of verbs.</span></span> <span data-ttu-id="44a93-156">Die Antwort liefert außerdem Informationen über den Verwendungszweck eines Verbs.</span><span class="sxs-lookup"><span data-stu-id="44a93-156">What's informative about the response, is that it also shows more context, what such a verb is meant to do.</span></span> <span data-ttu-id="44a93-157">Dies ist die erste Zeile der Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="44a93-157">Here's the first row of the output:</span></span>

```output
Verb        AliasPrefix Group          Description
----        ----------- -----          -----------
Add         a           Common         Adds a resource to a container, or attaches an item to ano…
```

## <a name="find-commands-with-get-command"></a><span data-ttu-id="44a93-158">Suchen von Befehlen mit „Get-Command“</span><span class="sxs-lookup"><span data-stu-id="44a93-158">Find commands with Get-Command</span></span>

<span data-ttu-id="44a93-159">Mit dem Cmdlet `Get-Command` wird eine Liste aller verfügbaren Befehle zurückgegeben, die auf Ihrem System installiert sind.</span><span class="sxs-lookup"><span data-stu-id="44a93-159">The `Get-Command` cmdlet returns a list of all available commands that are installed on your system.</span></span>
<span data-ttu-id="44a93-160">Die zurückgegebene Liste ist recht umfangreich.</span><span class="sxs-lookup"><span data-stu-id="44a93-160">That list you get back, is quite large though.</span></span> <span data-ttu-id="44a93-161">Um die Suche nach Befehlen zu vereinfachen, können Sie die Menge der zurückgegebenen Informationen einschränken.</span><span class="sxs-lookup"><span data-stu-id="44a93-161">To make finding commands easier you can limit the amount of information that comes back.</span></span> <span data-ttu-id="44a93-162">Sie können die Antwort entweder mithilfe von Parametern oder mithilfe von Hilfs-Cmdlets filtern.</span><span class="sxs-lookup"><span data-stu-id="44a93-162">You can filter the response using either parameters or by using helper cmdlets.</span></span>

### <a name="filter-on-name"></a><span data-ttu-id="44a93-163">Filtern nach Namen</span><span class="sxs-lookup"><span data-stu-id="44a93-163">Filter on name</span></span>

<span data-ttu-id="44a93-164">Sie können die Ausgabe von `Get-Command` mithilfe verschiedener Parameter filtern.</span><span class="sxs-lookup"><span data-stu-id="44a93-164">You can filter the output of `Get-Command`, using different parameters.</span></span> <span data-ttu-id="44a93-165">Bei dieser Art von Filterung handelt es sich um die Abfrage nach einer bestimmten Eigenschaft im Befehl.</span><span class="sxs-lookup"><span data-stu-id="44a93-165">Filtering this way, is about querying a specific property on the command.</span></span> <span data-ttu-id="44a93-166">Sie legen fest, nach welcher Eigenschaft gefiltert werden soll, und geben dann eine Zeichenfolge an, mit der verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="44a93-166">The idea is that you specify what property you want to filter against, and then you provide a string that you want to match against.</span></span> <span data-ttu-id="44a93-167">Dies ergibt einen Vergleich, der wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="44a93-167">You'll therefore get a comparison that looks like this:</span></span>

```powershell
Get-Command -Name '*Process'
```

<span data-ttu-id="44a93-168">In diesem Befehl wird mit der Filterung eine genaue Übereinstimmung mit dem angegebenen Zeichenfolgenargument gesucht.</span><span class="sxs-lookup"><span data-stu-id="44a93-168">At this point, the filtering is trying to do an exact matching against the provided string argument.</span></span>
<span data-ttu-id="44a93-169">Wenn Sie mehr Flexibilität benötigen, können Sie im Vergleich das Platzhalterzeichen`*` verwenden, mit dem ein Musterabgleich erfolgt.</span><span class="sxs-lookup"><span data-stu-id="44a93-169">If you want to have more flexibility, in the comparison, you can use a wildcard `*`, that does pattern matching.</span></span> <span data-ttu-id="44a93-170">Im folgenden Code wird nach allen Befehlen gesucht, deren Name mit „Process“ endet.</span><span class="sxs-lookup"><span data-stu-id="44a93-170">The following code would look for all commands, who's name ends with process:</span></span>

<span data-ttu-id="44a93-171">Im obigen Beispiel wird zum Filtern der Parameter `-Name` verwendet.</span><span class="sxs-lookup"><span data-stu-id="44a93-171">Above, the parameter the `-Name` is used to filter.</span></span> <span data-ttu-id="44a93-172">Sie können nicht nur nach `-Name`, sondern auch z. B. nach `-ParameterName` oder `-Type` filtern.</span><span class="sxs-lookup"><span data-stu-id="44a93-172">Apart from `-Name`, you can also filter on `-ParameterName` and `-Type`, for example.</span></span>

### <a name="filtering-on-noun-and-verb"></a><span data-ttu-id="44a93-173">Filtern nach Nomen und Verb</span><span class="sxs-lookup"><span data-stu-id="44a93-173">Filtering on Noun and Verb</span></span>

<span data-ttu-id="44a93-174">Oben wurde gezeigt, wie Sie nach `-Name` filtern können und dass auch nach anderen Parametern gefiltert werden kann.</span><span class="sxs-lookup"><span data-stu-id="44a93-174">You've seen how you can filter on `-Name`, and that there are other parameters you can filter on as well.</span></span> <span data-ttu-id="44a93-175">Sie können auch nach Verb und Nomen filtern.</span><span class="sxs-lookup"><span data-stu-id="44a93-175">Verb and noun is something you can filter on as well.</span></span> <span data-ttu-id="44a93-176">Dabei wird nach einer Komponente eines Befehlsnamens gefiltert.</span><span class="sxs-lookup"><span data-stu-id="44a93-176">Such filtering targets part of a command's name.</span></span>

- <span data-ttu-id="44a93-177">**Filtern nach Verb**.</span><span class="sxs-lookup"><span data-stu-id="44a93-177">**Filter on verb**.</span></span> <span data-ttu-id="44a93-178">Das Verb im Namen eines Befehls ist der linke Teil des Befehls.</span><span class="sxs-lookup"><span data-stu-id="44a93-178">The verb part of a command's name is the leftmost part.</span></span> <span data-ttu-id="44a93-179">Im Befehl `Get-Process` ist `Get` das Verb.</span><span class="sxs-lookup"><span data-stu-id="44a93-179">In the command `Get-Process`, the verb part is `Get`.</span></span> <span data-ttu-id="44a93-180">Um nach dem Verbteil im Befehl zu filtern, geben Sie `-Verb` als Parameter an, z. B. wie im folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="44a93-180">To filter on th verb part, specify `-Verb` as a parameter like so:</span></span>

   ```powershell
   Get-Command -Verb 'Get'
   ```

   <span data-ttu-id="44a93-181">Mit dem obigen Befehl werden alle Befehle aufgelistet, deren Verb `Get` lautet.</span><span class="sxs-lookup"><span data-stu-id="44a93-181">The above command would list all the commands where the verb part is `Get`.</span></span>

- <span data-ttu-id="44a93-182">**Filtern nach Nomen**.</span><span class="sxs-lookup"><span data-stu-id="44a93-182">**Filter on noun**.</span></span> <span data-ttu-id="44a93-183">Das Nomen ist der rechte Teil eines Befehls.</span><span class="sxs-lookup"><span data-stu-id="44a93-183">The rightmost part of a command is the noun part.</span></span> <span data-ttu-id="44a93-184">Während das Verb eines der durch den Aufruf von `Get-Verb` zurückgegebenen Verben sein muss, ist als Nomen ein beliebiges Substantiv möglich.</span><span class="sxs-lookup"><span data-stu-id="44a93-184">Where verb should be among the verbs returned from invoking `Get-Verb`, a noun can be anything.</span></span> <span data-ttu-id="44a93-185">Im Befehl `Get-Process` lautet das Nomen `Process`.</span><span class="sxs-lookup"><span data-stu-id="44a93-185">In the command `Get-Process`, the noun part is `Process`.</span></span> <span data-ttu-id="44a93-186">Um nach Nomen zu filtern, geben Sie `-Noun` als Parameter und ein Zeichenfolgenargument an, z. B. wie im folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="44a93-186">To filter on noun, specify `-Noun` as a parameter and a string argument, like so:</span></span>

   ```powershell
   Get-Command -Noun U*
   ```

<span data-ttu-id="44a93-187">Wenn nur nach Verb oder Nomen gefiltert wird, kann das Ergebnis immer noch sehr umfangreich sein.</span><span class="sxs-lookup"><span data-stu-id="44a93-187">Only using the verb, or the noun, to filter on, might lead to a big result still.</span></span> <span data-ttu-id="44a93-188">Um die Suche einzugrenzen, können die beiden Parameter kombiniert werden, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="44a93-188">To narrow down your search, it's good to combine the two parameters like the below example:</span></span>

```powershell
Get-Command -Verb Get -Noun U*
```

<span data-ttu-id="44a93-189">Das Ergebnis des obigen Beispiels lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="44a93-189">The result of the above looks like so:</span></span>

```output
CommandType     Name                         Version    Source
-----------     ----                         -------    ------
Cmdlet          Get-UICulture                7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Unique                   7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Uptime                   7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-UsageAggregates          2.0.0      Az.Billing
```

<span data-ttu-id="44a93-190">In dem Sie den Namen des Verbs angegeben haben, konnten Sie die Suche erheblich eingrenzen.</span><span class="sxs-lookup"><span data-stu-id="44a93-190">Thereby, you narrowed down the output quite bit by knowing the verb and what it's called.</span></span>

### <a name="use-helper-cmdlets-to-filter-results"></a><span data-ttu-id="44a93-191">Verwenden von Hilfs-Cmdlets zum Filtern von Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="44a93-191">Use helper cmdlets to filter results</span></span>

<span data-ttu-id="44a93-192">Sie können nicht nur nach Parametern filtern, sondern zum Filtern auch Befehle verwenden.</span><span class="sxs-lookup"><span data-stu-id="44a93-192">Apart from using parameters to filter, you can also use commands to help you with this task.</span></span> <span data-ttu-id="44a93-193">Nachstehend werden einige Befehle beschrieben, die als Filter fungieren können:</span><span class="sxs-lookup"><span data-stu-id="44a93-193">Here's some commands that can act as filters:</span></span>

- <span data-ttu-id="44a93-194">`Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="44a93-194">`Select-Object`.</span></span> <span data-ttu-id="44a93-195">Dies ist ein sehr vielseitiger Befehl, mit dem Sie bestimmte Eigenschaften eines oder mehrerer Objekten auswählen können.</span><span class="sxs-lookup"><span data-stu-id="44a93-195">It's a very versatile command that helps you pick out specific properties from one or more objects.</span></span> <span data-ttu-id="44a93-196">Zudem können Sie mit diesem Befehl die zurückgegebene Antwort beschränken.</span><span class="sxs-lookup"><span data-stu-id="44a93-196">Additionally by using it's parameters you can limit the response you get back.</span></span> <span data-ttu-id="44a93-197">Im folgenden Beispiel wird mit `Select-Object` eine begrenzte Anzahl von Datensätzen angefordert:</span><span class="sxs-lookup"><span data-stu-id="44a93-197">Here's an example of `Select-Object` being used to ask for a limited number of records:</span></span>

   ```powershell
   Get-Command | Select-Object -First 3
   ```

   <span data-ttu-id="44a93-198">Das Ergebnis des obigen Befehls sind die ersten drei Befehle.</span><span class="sxs-lookup"><span data-stu-id="44a93-198">The result from the above is the three first commands, counted from the top.</span></span> <span data-ttu-id="44a93-199">Das Ergebnis lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="44a93-199">The result looks like so:</span></span>

   ```output
   CommandType     Name                                               Version    Source
   -----------     ----                                               -------    ------
   Alias           Add-AdlAnalyticsDataSource                         1.0.2      Az.DataLakeAnalytics
   Alias           Add-AdlAnalyticsFirewallRule                       1.0.2      Az.DataLakeAnalytics
   Alias           Add-AdlStoreFirewallRule                           1.3.0      Az.DataLakeStore
   ```

   <span data-ttu-id="44a93-200">Es lohnt sich, diesen Befehl genauer zu betrachten, da er noch viel mehr kann (siehe [Select-Object](/powershell/module/microsoft.powershell.utility/select-object)).</span><span class="sxs-lookup"><span data-stu-id="44a93-200">It's worth looking into to this command further as it can do a lot more  [docs Select-Object](/powershell/module/microsoft.powershell.utility/select-object)</span></span>

- <span data-ttu-id="44a93-201">`Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="44a93-201">`Where-Object`.</span></span> <span data-ttu-id="44a93-202">„Where-Object“ unterstützt Sie bei der Auswahl von Objekten aus einer Sammlung, die auf den Werten von Eigenschaften basiert.</span><span class="sxs-lookup"><span data-stu-id="44a93-202">The where object helps you select objects from a collection based on the values of properties.</span></span> <span data-ttu-id="44a93-203">Der Befehl akzeptiert einen Ausdruck, in dem Sie angeben können, welche Spalte(n) mit welchen Werten verglichen werden soll(en).</span><span class="sxs-lookup"><span data-stu-id="44a93-203">The command takes an expression in which you are able to express what column/s you want to match against what values.</span></span> <span data-ttu-id="44a93-204">Um alle Process-Objekte zu suchen, deren `ProcessName` mit `p` beginnt, können Sie `Where-Object` wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="44a93-204">To find all process object where the `ProcessName` starts with `p`, you could use `Where-Object` like so:</span></span>

  ```powershell
  Get-Process | Where-Object {$_.ProcessName -Like "p*"}
  ```

  <span data-ttu-id="44a93-205">Im obigen Befehl erzeugt das Cmdlet `Get-Process` eine Sammlung von Process-Objekten.</span><span class="sxs-lookup"><span data-stu-id="44a93-205">Above, the `Get-Process` cmdlet produces a collection of process objects.</span></span> <span data-ttu-id="44a93-206">Zum Filtern der Antwort wird der Befehl `Where-Object` _weitergereicht_.</span><span class="sxs-lookup"><span data-stu-id="44a93-206">To filter down the response, you _pipe_ the command `Where-Object`.</span></span> <span data-ttu-id="44a93-207">„Weiterreichen“ bedeutet, dass mehrere Befehle mithilfe eines senkrechten Strichs (`|`) verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="44a93-207">Piping means that two or more commands are connected via a pipe `|` character.</span></span> <span data-ttu-id="44a93-208">Dabei fungiert die Ausgabe eines Befehls als Eingabe für den nächsten Befehl (von links nach rechts).</span><span class="sxs-lookup"><span data-stu-id="44a93-208">The idea is that the output from one command serves as the input for the next command, as read from left to right.</span></span> <span data-ttu-id="44a93-209">`Where-Object` filtert mithilfe eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="44a93-209">The `Where-Object` uses an expression to filter.</span></span> <span data-ttu-id="44a93-210">Im Ausdruck selbst werden der Operator `-Like` und ein Zeichenfolgenargument verwendet, das ein Platzhalterausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="44a93-210">The expression itself uses the `-Like` operator and string argument that is a wildcard expression.</span></span>

## <a name="explore-objects-with-get-member"></a><span data-ttu-id="44a93-211">Untersuchen von Objekten mit „Get-Member“</span><span class="sxs-lookup"><span data-stu-id="44a93-211">Explore objects with Get-Member</span></span>

<span data-ttu-id="44a93-212">Nachdem Sie das gewünschte Cmdlet gefunden haben, möchten Sie mehr über die von ihm erzeuge Ausgabe erfahren.</span><span class="sxs-lookup"><span data-stu-id="44a93-212">Once you've been able to locate the cmdlet you want, you want to know more about what it produces, the output.</span></span> <span data-ttu-id="44a93-213">Bei Ausgaben sind verschiedene Aspekte zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="44a93-213">The output is interesting for several reasons like:</span></span>

- <span data-ttu-id="44a93-214">**Eigenständig**.</span><span class="sxs-lookup"><span data-stu-id="44a93-214">**Standalone**.</span></span> <span data-ttu-id="44a93-215">Möglicherweise führen Sie nur ein Cmdlet aus, und die Ausgabe soll in einem Bericht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="44a93-215">You might run just one cmdlet and you want to display the output in some sort of report.</span></span> <span data-ttu-id="44a93-216">In diesem Fall müssen Sie wissen, ob die vom Befehl erzeugte Ausgabe den gewünschten Zweck erfüllt oder geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="44a93-216">The question to ask yourself is whether the command produces an output that works for you, or if you need to change it.</span></span>
- <span data-ttu-id="44a93-217">**Verwendung in einer Pipeline**.</span><span class="sxs-lookup"><span data-stu-id="44a93-217">**When used in a pipeline**.</span></span> <span data-ttu-id="44a93-218">In PowerShell werden häufig mehrere Befehle in einer Pipeline miteinander verbunden, um Daten abzurufen, zu filtern und zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="44a93-218">It's common in PowerShell to connect several commands in a pipeline, to fetch data, filter and finally to transform it.</span></span> <span data-ttu-id="44a93-219">Damit ein Befehl in eine Pipeline aufgenommen werden kann, müssen Sie überprüfen, welche Eingabe er akzeptiert und welche Ausgabe er erzeugt.</span><span class="sxs-lookup"><span data-stu-id="44a93-219">For a command to fit into a pipeline, you have to look at what input and output it produces.</span></span> <span data-ttu-id="44a93-220">In einer Pipeline wird die Ausgabe eines Befehls als Eingabe eines weiteren Befehls verwendet.</span><span class="sxs-lookup"><span data-stu-id="44a93-220">The idea is that the output of a command is used as the input of another command.</span></span>

<span data-ttu-id="44a93-221">Mit dem Cmdlet `Get-Member` werden die Eigenschaften und Methoden des Ergebnisses angezeigt.</span><span class="sxs-lookup"><span data-stu-id="44a93-221">The `Get-Member` cmdlet displays the properties and methods of the result.</span></span> <span data-ttu-id="44a93-222">Es zeigt außerdem den Typ des Objekts an.</span><span class="sxs-lookup"><span data-stu-id="44a93-222">Additionally it also show the type of the object.</span></span> <span data-ttu-id="44a93-223">Reichen Sie die Ausgabe, die Sie überprüfen möchten, an `Get-Member` weiter.</span><span class="sxs-lookup"><span data-stu-id="44a93-223">Pipe the output you want to inspect to `Get-Member`.</span></span>

```powershell
Get-Process | Get-Member
```

<span data-ttu-id="44a93-224">Im Ergebnis werden durch `TypeName` der zurückgegebene Typ und dann alle Eigenschaften und Methoden des Objekts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="44a93-224">The result displays the returned type as `TypeName` and then all the properties and methods of the object.</span></span> <span data-ttu-id="44a93-225">Dies ist ein Auszug aus einem solchen Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="44a93-225">Here's an excerpt of such a result:</span></span>

```output
TypeName: System.Diagnostics.Process

Name        MemberType     Definition
----        ----------     ----------
Handles     AliasProperty  Handles = Handlecount
Name        AliasProperty  Name = ProcessName
```

<span data-ttu-id="44a93-226">Ein Objekt verfügt in der Regel über viele Eigenschaften und Methoden. Um das Gesuchte leichter zu finden, können Sie die Ergebnisse filtern.</span><span class="sxs-lookup"><span data-stu-id="44a93-226">An object usually has plenty of properties and methods, to more easily find what you're looking for, you can filter the results.</span></span> <span data-ttu-id="44a93-227">Mit dem-Parameter `-MemberType` können Sie z. B. angeben, dass alle Methoden angezeigt werden sollen, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="44a93-227">By using the parameter `-MemberType`, you can specify to, for example see all the methods, like in the below example:</span></span>

```powershell
Get-Process | Get-Member -MemberType Method
```

<span data-ttu-id="44a93-228">In der zurückgegebenen Antwort werden in der Regel nur einige Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="44a93-228">When you get a response back, PowerShell usually only displays a few properties.</span></span> <span data-ttu-id="44a93-229">In der obigen Antwort werden `Name`, `MemberType` und `Definition` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="44a93-229">In the above response, `Name`, `MemberType` and `Definition` was displayed.</span></span> <span data-ttu-id="44a93-230">Um die Anzeige zu ändern, können Sie das Cmdlet `Select-Object` verwenden.</span><span class="sxs-lookup"><span data-stu-id="44a93-230">To change that display, you can use the cmdlet `Select-Object`.</span></span> <span data-ttu-id="44a93-231">Mit `Select-Object` können Sie festlegen, welche Spalten angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="44a93-231">`Select-Object` allows you to specify what columns you want to see.</span></span> <span data-ttu-id="44a93-232">Sie können den Namen der Spalte, eine durch Kommas getrennte Liste oder einen Platzhalter (`*`) angeben.</span><span class="sxs-lookup"><span data-stu-id="44a93-232">You can either provide it with the name of the column, a comma separated list or a wildcard `*`.</span></span> <span data-ttu-id="44a93-233">Im folgenden Beispiel wird `Select-Object` zum Abrufen von `Name` und `Definition` verwendet:</span><span class="sxs-lookup"><span data-stu-id="44a93-233">Here's an example where `Select-Object` is used to retrieve `Name` and `Definition`:</span></span>

```powershell
Get-Process | Get-Member | Select-Object Name, Definition
```

### <a name="search-by-type"></a><span data-ttu-id="44a93-234">Typbasiertes Suchen</span><span class="sxs-lookup"><span data-stu-id="44a93-234">Search by type</span></span>

<span data-ttu-id="44a93-235">Eine weitere Möglichkeit zum Suchen des gewünschten Befehls ist das Suchen aller Befehle, die für denselben Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44a93-235">Another way to approach searching for the command you want, is by searching for commands all operating on the same type.</span></span> <span data-ttu-id="44a93-236">Wenn Sie `Get-Member` verwendet haben, enthält die erste Zeile der Antwort den zurückgegebenen Typ, wie in diesem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="44a93-236">When you used `Get-Member`, you got the returned type as the first line of the response like so:</span></span>

```output
TypeName: System.Diagnostics.Process
```

<span data-ttu-id="44a93-237">Sie können jetzt anhand dieses Typs nach Befehlen suchen:</span><span class="sxs-lookup"><span data-stu-id="44a93-237">You can now use this type and search for commands like so:</span></span>

```powershell
Get-Command -ParameterType Process
```

<span data-ttu-id="44a93-238">Das Ergebnis des obigen Befehls ist eine Liste mit Befehlen, die ausschließlich für den Typ `Process` ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="44a93-238">The result from invoking the above is a list with commands that solely operates on the `Process` type:</span></span>

```output
CommandType     Name                         Version    Source
-----------     ----                         -------    ------
Cmdlet          Debug-Process                7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Enter-PSHostProcess          7.1.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-Process                  7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Get-PSHostProcessInfo        7.1.0.0    Microsoft.PowerShell.Core
Cmdlet          Stop-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Wait-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
```

<span data-ttu-id="44a93-239">Wie Sie sehen, lässt sich durch die Angabe des Typs eines Befehls die Suche nach Befehlen stark eingrenzen.</span><span class="sxs-lookup"><span data-stu-id="44a93-239">As you can see, knowing the type of a command, can greatly narrow down your search after commands that might be interesting for you.</span></span>

## <a name="exercise---calling-your-first-command"></a><span data-ttu-id="44a93-240">Übung: Aufrufen des ersten Befehls</span><span class="sxs-lookup"><span data-stu-id="44a93-240">Exercise - calling your first command</span></span>

<span data-ttu-id="44a93-241">In dieser Übung lernen Sie, wie Sie Ihren ersten Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="44a93-241">In this exercise, you'll learn how to run your first command.</span></span>

1. <span data-ttu-id="44a93-242">Starten Sie eine PowerShell-Konsole, indem Sie `pwsh` eingeben:</span><span class="sxs-lookup"><span data-stu-id="44a93-242">Start a PowerShell console by typing `pwsh`:</span></span>

   ```powershell
   pwsh
   ```

1. <span data-ttu-id="44a93-243">Führen Sie `$PSVersionTable.PSVersion` aus:</span><span class="sxs-lookup"><span data-stu-id="44a93-243">Run the following `$PSVersionTable.PSVersion`:</span></span>

   ```powershell
   $PSVersionTable.PSVersion
   ```

   <span data-ttu-id="44a93-244">Die Ausgabe sieht in etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="44a93-244">Your output looks similar to this:</span></span>

   ```output
   Major  Minor  Patch  PreReleaseLabel BuildLabel
   -----  -----  -----  --------------- ----------
   7      1      0
   ```

   <span data-ttu-id="44a93-245">Herzlichen Glückwunsch! Sie haben ihren ersten Befehl erfolgreich ausgeführt und konnten die auf Ihrem System installierte Version von PowerShell abrufen.</span><span class="sxs-lookup"><span data-stu-id="44a93-245">Congrats, you've successfully run your first command and was able to get information of what version of PowerShell is installed on your system.</span></span>

## <a name="exercise---find-related-commands"></a><span data-ttu-id="44a93-246">Übung: Suchen verwandter Befehle</span><span class="sxs-lookup"><span data-stu-id="44a93-246">Exercise - find related commands</span></span>

<span data-ttu-id="44a93-247">In dieser Übung sollen Sie mehr über einen Befehl erfahren.</span><span class="sxs-lookup"><span data-stu-id="44a93-247">In this exercise your goal is to learn more about a command.</span></span> <span data-ttu-id="44a93-248">Dabei erfahren Sie, für welchen Typ der Befehl verwendet wird und welche ähnlichen Befehle für denselben Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44a93-248">In doing so you'll also find things like what type it operates on and what other similar commands operate on that same type.</span></span>

1. <span data-ttu-id="44a93-249">Stellen Sie sicher, dass eine PowerShell-Shell gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="44a93-249">Ensure you have a started PowerShell shell</span></span>
1. <span data-ttu-id="44a93-250">Führen Sie den Befehl `Get-Process` aus:</span><span class="sxs-lookup"><span data-stu-id="44a93-250">Run the the command `Get-Process`:</span></span>

   ```powershell
   Get-Process | Get-Member | Select-Object TypeName -Unique
   ```

   <span data-ttu-id="44a93-251">Die Ausgabe sieht ungefähr wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="44a93-251">Your output resembles this:</span></span>

   ```output
   TypeName
   --------
   System.Diagnostics.Process
   --------
   ```

   <span data-ttu-id="44a93-252">Sie erhalten als Ergebnis die vom Befehl `Get-Command` zurückgegebenen Typen.</span><span class="sxs-lookup"><span data-stu-id="44a93-252">What you're getting back, is a the types returned by the command `Get-Command`.</span></span> <span data-ttu-id="44a93-253">Jetzt können Sie ermitteln, welche sonstigen Befehle ebenfalls für diese Typen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="44a93-253">At this point you can now find out what other command also operates on these types.</span></span>

1. <span data-ttu-id="44a93-254">Führen Sie den Befehl `Get-Command` aus:</span><span class="sxs-lookup"><span data-stu-id="44a93-254">Run the command `Get-Command`:</span></span>

   ```powershell
   Get-Command -ParameterType Process
   ```

   <span data-ttu-id="44a93-255">Die Ausgabe sieht ungefähr wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="44a93-255">Your output resembles this:</span></span>

   ```output
   CommandType     Name                         Version    Source
    -----------     ----                        -------    ------
    Cmdlet          Debug-Process               7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Enter-PSHostProcess         7.1.0.0    Microsoft.PowerShell.Core
    Cmdlet          Get-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Get-PSHostProcessInfo       7.1.0.0    Microsoft.PowerShell.Core
    Cmdlet          Stop-Process                7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Wait-Process                7.0.0.0    Microsoft.PowerShell.Managem…
   ```

   <span data-ttu-id="44a93-256">Herzlichen Glückwunsch! Sie haben weitere Befehle ermittelt, die ebenfalls für den Typ `Process` ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="44a93-256">Congratulations, you've managed to find other commands that operates on the same type `Process`.</span></span>
   <span data-ttu-id="44a93-257">`Get-Member` eignet sich gut, um weitere Befehle zu ermitteln, die Sie sich als Nächstes ansehen sollten.</span><span class="sxs-lookup"><span data-stu-id="44a93-257">Using `Get-Member` is a good starting point to understand what other commands you should check out next.</span></span>

## <a name="summary"></a><span data-ttu-id="44a93-258">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="44a93-258">Summary</span></span>

<span data-ttu-id="44a93-259">In diesem ersten Teil haben Sie erfahren, was PowerShell ist und in welchen Bereichen es verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="44a93-259">In this first part, you learned what PowerShell is and what areas in can be used.</span></span> <span data-ttu-id="44a93-260">Dann haben Sie einiges über Cmdlets erfahren, insbesondere über `Get-Command`, `Get-Verb` und `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="44a93-260">You where then taught about cmdlets and in particular `Get-Command`, `Get-Verb` and `Get-Member`.</span></span> <span data-ttu-id="44a93-261">Die Kenntnis dieser Cmdlets ist eine wichtige Voraussetzung für das Erlernen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44a93-261">Knowing theses cmdlets is important as it teaches you how to learn.</span></span> <span data-ttu-id="44a93-262">Im nächsten Abschnitt erfahren Sie, wie Sie das leistungsfähige Hilfesystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="44a93-262">In the next part, you'll learn how to use the powerful help system.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="44a93-263">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="44a93-263">Additional resources</span></span>

- [<span data-ttu-id="44a93-264">Get-Command</span><span class="sxs-lookup"><span data-stu-id="44a93-264">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="44a93-265">Get-Member</span><span class="sxs-lookup"><span data-stu-id="44a93-265">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
