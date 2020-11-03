---
description: Erläutert die sprach Modi und ihre Auswirkung auf PowerShell-Sitzungen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: 8254760e49d5d9b2d1b035038b14414b0074435c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221527"
---
# <a name="about-language-modes"></a><span data-ttu-id="dcbaf-104">Informationen zu sprach Modi</span><span class="sxs-lookup"><span data-stu-id="dcbaf-104">About Language Modes</span></span>

## <a name="short-description"></a><span data-ttu-id="dcbaf-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dcbaf-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="dcbaf-106">Erläutert die sprach Modi und ihre Auswirkung auf PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-106">Explains language modes and their effect on PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="dcbaf-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dcbaf-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="dcbaf-108">Der Sprachmodus einer PowerShell-Sitzung bestimmt teilweise, welche Elemente der PowerShell-Sprache in der Sitzung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-108">The language mode of a PowerShell session determines, in part, which elements of the PowerShell language can be used in the session.</span></span>

<span data-ttu-id="dcbaf-109">PowerShell unterstützt die folgenden sprach Modi:</span><span class="sxs-lookup"><span data-stu-id="dcbaf-109">PowerShell supports the following language modes:</span></span>

- <span data-ttu-id="dcbaf-110">FullLanguage</span><span class="sxs-lookup"><span data-stu-id="dcbaf-110">FullLanguage</span></span>
- <span data-ttu-id="dcbaf-111">Einschräninedlanguage (eingeführt in PowerShell 3,0)</span><span class="sxs-lookup"><span data-stu-id="dcbaf-111">ConstrainedLanguage (introduced in PowerShell 3.0)</span></span>
- <span data-ttu-id="dcbaf-112">Restrictedlanguage</span><span class="sxs-lookup"><span data-stu-id="dcbaf-112">RestrictedLanguage</span></span>
- <span data-ttu-id="dcbaf-113">NoLanguage</span><span class="sxs-lookup"><span data-stu-id="dcbaf-113">NoLanguage</span></span>

### <a name="what-is-a-language-mode"></a><span data-ttu-id="dcbaf-114">Was ist ein Sprachmodus?</span><span class="sxs-lookup"><span data-stu-id="dcbaf-114">WHAT IS A LANGUAGE MODE?</span></span>

<span data-ttu-id="dcbaf-115">Der Sprachmodus bestimmt die Sprachelemente, die in der Sitzung zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-115">The language mode determines the language elements that are permitted in the session.</span></span>

<span data-ttu-id="dcbaf-116">Der Sprachmodus ist tatsächlich eine Eigenschaft der Sitzungs Konfiguration (oder des "Endpunkts"), die verwendet wird, um die Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-116">The language mode is actually a property of the session configuration (or "endpoint") that is used to create the session.</span></span> <span data-ttu-id="dcbaf-117">Alle Sitzungen, die eine bestimmte Sitzungs Konfiguration verwenden, haben den Sprachmodus der Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-117">All sessions that use a particular session configuration have the language mode of the session configuration.</span></span>

<span data-ttu-id="dcbaf-118">Alle PowerShell-Sitzungen verfügen über einen Sprachmodus, einschließlich pssessions, die Sie mithilfe des `New-PSSession` Cmdlets erstellen, temporäre Sitzungen mit dem Computername-Parameter und die Standard Sitzungen, die beim Starten von PowerShell angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-118">All PowerShell sessions have a language mode, including PSSessions that you create by using the `New-PSSession` cmdlet, temporary sessions that use the ComputerName parameter, and the default sessions that appear when you start PowerShell.</span></span>

<span data-ttu-id="dcbaf-119">Remote Sitzungen werden mithilfe der Sitzungs Konfigurationen auf dem Remote Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-119">Remote sessions are created by using the session configurations on the remote computer.</span></span> <span data-ttu-id="dcbaf-120">Der Sprachmodus, der in der Sitzungs Konfiguration festgelegt ist, bestimmt den Sprachmodus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-120">The language mode set in the session configuration determines the language mode of the session.</span></span> <span data-ttu-id="dcbaf-121">Um die Sitzungs Konfiguration einer PSSession anzugeben, verwenden Sie den ConfigurationName-Parameter von Cmdlets, die eine Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-121">To specify the session configuration of a PSSession, use the ConfigurationName parameter of cmdlets that create a session.</span></span>

### <a name="language-modes"></a><span data-ttu-id="dcbaf-122">sprach Modi</span><span class="sxs-lookup"><span data-stu-id="dcbaf-122">LANGUAGE MODES</span></span>

<span data-ttu-id="dcbaf-123">In diesem Abschnitt werden die sprach Modi in PowerShell-Sitzungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-123">This section describes the language modes in PowerShell sessions.</span></span>

#### <a name="full-language-fulllanguage"></a><span data-ttu-id="dcbaf-124">Vollständige Sprache (vollständig)</span><span class="sxs-lookup"><span data-stu-id="dcbaf-124">FULL LANGUAGE (FullLanguage)</span></span>

<span data-ttu-id="dcbaf-125">Im voll Sprachmodus sind alle Sprachelemente in der Sitzung zulässig.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-125">The FullLanguage mode permits all language elements in the session.</span></span>
<span data-ttu-id="dcbaf-126">Fulllanguage ist der Standard Sprachmodus für Standard Sitzungen in allen Windows-Versionen mit Ausnahme von Windows RT.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-126">FullLanguage is the default language mode for default sessions on all versions of Windows except for Windows RT.</span></span>

#### <a name="restricted-language-restrictedlanguage"></a><span data-ttu-id="dcbaf-127">Eingeschränkte Sprache (restrictedlanguage)</span><span class="sxs-lookup"><span data-stu-id="dcbaf-127">RESTRICTED LANGUAGE (RestrictedLanguage)</span></span>

<span data-ttu-id="dcbaf-128">Im restrictedlanguage-Modus können Benutzer Befehle (Cmdlets, Funktionen, CIM-Befehle und Workflows) ausführen, aber Sie dürfen keine Skriptblöcke verwenden.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-128">In RestrictedLanguage mode, users may run commands (cmdlets, functions, CIM commands, and workflows) but are not permitted to use script blocks.</span></span>

<span data-ttu-id="dcbaf-129">Standardmäßig sind nur die folgenden Variablen im restrictedlanguage-Modus zulässig:</span><span class="sxs-lookup"><span data-stu-id="dcbaf-129">By default, only the following variables are permitted in RestrictedLanguage mode:</span></span>

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

<span data-ttu-id="dcbaf-130">Modul Manifeste, die den restrictedlanguage-Modus verwenden, lassen die folgenden zusätzlichen Variablen ebenfalls zu:</span><span class="sxs-lookup"><span data-stu-id="dcbaf-130">Module manifests, which use RestrictedLanguage mode, permit the following additional variables as well:</span></span>

- `$PSScriptRoot`
- <span data-ttu-id="dcbaf-131">`$PSEdition` (in PowerShell Core)</span><span class="sxs-lookup"><span data-stu-id="dcbaf-131">`$PSEdition` (in PowerShell Core)</span></span>
- <span data-ttu-id="dcbaf-132">`$EnabledExperimentalFeatures` (in PowerShell Core)</span><span class="sxs-lookup"><span data-stu-id="dcbaf-132">`$EnabledExperimentalFeatures` (in PowerShell Core)</span></span>

<span data-ttu-id="dcbaf-133">Nur die folgenden Vergleichs Operatoren sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="dcbaf-133">Only the following comparison operators are permitted:</span></span>

- <span data-ttu-id="dcbaf-134">`-eq` hoch</span><span class="sxs-lookup"><span data-stu-id="dcbaf-134">`-eq` (equal)</span></span>
- <span data-ttu-id="dcbaf-135">`-gt` (größer als)</span><span class="sxs-lookup"><span data-stu-id="dcbaf-135">`-gt` (greater-than)</span></span>
- <span data-ttu-id="dcbaf-136">`-lt` (kleiner als)</span><span class="sxs-lookup"><span data-stu-id="dcbaf-136">`-lt` (less-than)</span></span>

<span data-ttu-id="dcbaf-137">Zuweisungsanweisungen, Eigenschaftsverweise und Methodenaufrufe sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-137">Assignment statements, property references, and method calls are not permitted.</span></span>

#### <a name="no-language-nolanguage"></a><span data-ttu-id="dcbaf-138">Keine Sprache (nolanguage)</span><span class="sxs-lookup"><span data-stu-id="dcbaf-138">NO LANGUAGE (NoLanguage)</span></span>

<span data-ttu-id="dcbaf-139">Der nolanguage-Modus kann nur über die API verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-139">NoLanguage mode can only be used through the API.</span></span> <span data-ttu-id="dcbaf-140">Der nolanguage-Modus bedeutet, dass kein Skript Text eines beliebigen Formulars zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-140">NoLanguage mode means no script text of any form is permitted.</span></span> <span data-ttu-id="dcbaf-141">Dies verhindert die Verwendung der **addScript ()** -Methode, die Fragmente von PowerShell-Skripts sendet, die analysiert und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-141">This precludes the use of the **AddScript()** method which sends fragments of PowerShell script to be parsed and executed.</span></span> <span data-ttu-id="dcbaf-142">Sie können nur **AddCommand ()** und **AddParameter ()** verwenden, die den Parser nicht durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-142">You can only use **AddCommand()** and **AddParameter()** which don't go through the parser.</span></span>

#### <a name="constrained-language-constrained-language"></a><span data-ttu-id="dcbaf-143">Eingeschränkte Sprache (eingeschränkte Sprache)</span><span class="sxs-lookup"><span data-stu-id="dcbaf-143">CONSTRAINED LANGUAGE (Constrained Language)</span></span>

<span data-ttu-id="dcbaf-144">Der Modus "einschräninedlanguage" erlaubt alle Cmdlets und alle PowerShell-Sprachelemente, schränkt jedoch zulässige Typen ein.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-144">The ConstrainedLanguage mode permits all cmdlets and all PowerShell language elements, but it limits permitted types.</span></span>

<span data-ttu-id="dcbaf-145">Der Modus "einschränder Modus" ist für die Unterstützung der Code Integrität (User Mode Code Integrity, Umschlag Code) in Windows RT konzipiert.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-145">ConstrainedLanguage mode is designed to support User Mode Code Integrity (UMCI) on Windows RT.</span></span> <span data-ttu-id="dcbaf-146">Dabei handelt es sich um den einzigen unterstützten Sprachmodus unter Windows RT, der jedoch auf allen unterstützten Systemen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-146">It is the only supported language mode on Windows RT, but it is available on all supported systems.</span></span>

<span data-ttu-id="dcbaf-147">Durch die über CI werden Arm-Geräte geschützt, da nur Microsoft-signierte und Microsoft-zertifizierte apps auf Windows RT-basierten Geräten installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-147">UMCI protects ARM devices by allowing only Microsoft-signed and Microsoft-certified apps to be installed on Windows RT-based devices.</span></span>
<span data-ttu-id="dcbaf-148">Der Modus "einschränken" verhindert, dass Benutzer PowerShell verwenden, um umci zu umgehen oder zu verletzen.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-148">ConstrainedLanguage mode prevents users from using PowerShell to circumvent or violate UMCI.</span></span>

<span data-ttu-id="dcbaf-149">Die Features des einschräninedlanguage-Modus lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="dcbaf-149">The features of ConstrainedLanguage mode are as follows:</span></span>

- <span data-ttu-id="dcbaf-150">Alle Cmdlets in Windows-Modulen und andere umci-genehmigte Cmdlets sind voll funktionsfähig und verfügen über vollständigen Zugriff auf Systemressourcen, außer wie bereits erwähnt.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-150">All cmdlets in Windows modules, and other UMCI-approved cmdlets, are fully functional and have complete access to system resources, except as noted.</span></span>

- <span data-ttu-id="dcbaf-151">Alle Elemente der PowerShell-Skriptsprache sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-151">All elements of the PowerShell scripting language are permitted.</span></span>

- <span data-ttu-id="dcbaf-152">Alle in Windows enthaltenen Module können importiert werden, und alle Befehle, die vom Modul exportiert werden, werden in der Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-152">All modules included in Windows can be imported and all commands that the modules export run in the session.</span></span>

- <span data-ttu-id="dcbaf-153">Im PowerShell-Workflow können Sie Skript Workflows (in der PowerShell-Sprache geschriebene Workflows) schreiben und ausführen.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-153">In PowerShell Workflow, you can write and run script workflows (workflows written in the PowerShell language).</span></span> <span data-ttu-id="dcbaf-154">XAML-basierte Workflows werden nicht unterstützt, und Sie können XAML nicht in einem Skript Workflow ausführen, z `Invoke-Expression -Language XAML` . b. mithilfe von.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-154">XAML-based workflows are not supported and you cannot run XAML in a script workflow, such as by using `Invoke-Expression -Language XAML`.</span></span> <span data-ttu-id="dcbaf-155">Workflows können auch keine anderen Workflows aufzurufen, obwohl es zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-155">Also, workflows cannot call other workflows, although nested workflows are permitted.</span></span>

- <span data-ttu-id="dcbaf-156">Das `Add-Type` Cmdlet kann signierte Assemblys laden, aber keinen beliebigen c#-Code oder Win32-APIs laden.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-156">The `Add-Type` cmdlet can load signed assemblies, but it cannot load arbitrary C# code or Win32 APIs.</span></span>

- <span data-ttu-id="dcbaf-157">Das- `New-Object` Cmdlet kann nur für zulässige Typen verwendet werden (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="dcbaf-157">The `New-Object` cmdlet can be used only on allowed types (listed below).</span></span>

- <span data-ttu-id="dcbaf-158">Nur zulässige Typen (unten aufgeführt) können in PowerShell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-158">Only allowed types (listed below) can be used in PowerShell.</span></span> <span data-ttu-id="dcbaf-159">Andere Typen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-159">Other types are not permitted.</span></span>

- <span data-ttu-id="dcbaf-160">Typkonvertierung ist zulässig, jedoch nur, wenn das Ergebnis ein zulässiger Typ ist.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-160">Type conversion is permitted, but only when the result is an allowed type.</span></span>

- <span data-ttu-id="dcbaf-161">Cmdlet-Parameter, die Zeichen folgen Eingaben in Typen konvertieren, funktionieren nur, wenn der resultierende Typ ein zulässiger Typ ist.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-161">Cmdlet parameters that convert string input to types work only when the resulting type is an allowed type.</span></span>

- <span data-ttu-id="dcbaf-162">Die **ToString ()** -Methode und die .NET-Methoden zulässiger Typen (siehe unten) können aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-162">The **ToString()** method and the .NET methods of allowed types (listed below) can be invoked.</span></span> <span data-ttu-id="dcbaf-163">Andere Methoden können nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-163">Other methods cannot be invoked.</span></span>

- <span data-ttu-id="dcbaf-164">Benutzer können alle Eigenschaften zulässiger Typen erhalten.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-164">Users can get all properties of allowed types.</span></span> <span data-ttu-id="dcbaf-165">Benutzer können die Werte von Eigenschaften nur für die Kerntypen festlegen.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-165">Users can set the values of properties only on Core types.</span></span> <span data-ttu-id="dcbaf-166">Nur die folgenden COM-Objekte sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="dcbaf-166">Only the following COM objects are permitted:</span></span>

  - <span data-ttu-id="dcbaf-167">**Scripting. Dictionary**</span><span class="sxs-lookup"><span data-stu-id="dcbaf-167">**Scripting.Dictionary**</span></span>
  - <span data-ttu-id="dcbaf-168">**Scripting.FileSystemObject**</span><span class="sxs-lookup"><span data-stu-id="dcbaf-168">**Scripting.FileSystemObject**</span></span>
  - <span data-ttu-id="dcbaf-169">**VBScript. RegExp**</span><span class="sxs-lookup"><span data-stu-id="dcbaf-169">**VBScript.RegExp**</span></span>

<span data-ttu-id="dcbaf-170">Die folgenden Typen sind im Modus "eingeschränkt" zulässig.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-170">The following types are permitted in ConstrainedLanguage mode.</span></span> <span data-ttu-id="dcbaf-171">Benutzer können Eigenschaften erhalten, Methoden aufrufen und Objekte in diese Typen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-171">Users can get properties, invoke methods, and convert objects to these types.</span></span>

<span data-ttu-id="dcbaf-172">Zulässige Typen:</span><span class="sxs-lookup"><span data-stu-id="dcbaf-172">Allowed Types:</span></span>

- <span data-ttu-id="dcbaf-173">Aliasattribute</span><span class="sxs-lookup"><span data-stu-id="dcbaf-173">AliasAttribute</span></span>
- <span data-ttu-id="dcbaf-174">' Zubei ' zuder Zuordnung</span><span class="sxs-lookup"><span data-stu-id="dcbaf-174">AllowEmptyCollectionAttribute</span></span>
- <span data-ttu-id="dcbaf-175">' Zubei ' zuder Zuweisung</span><span class="sxs-lookup"><span data-stu-id="dcbaf-175">AllowEmptyStringAttribute</span></span>
- <span data-ttu-id="dcbaf-176">Allownullattribute</span><span class="sxs-lookup"><span data-stu-id="dcbaf-176">AllowNullAttribute</span></span>
- <span data-ttu-id="dcbaf-177">Array</span><span class="sxs-lookup"><span data-stu-id="dcbaf-177">Array</span></span>
- <span data-ttu-id="dcbaf-178">Bool</span><span class="sxs-lookup"><span data-stu-id="dcbaf-178">Bool</span></span>
- <span data-ttu-id="dcbaf-179">byte</span><span class="sxs-lookup"><span data-stu-id="dcbaf-179">byte</span></span>
- <span data-ttu-id="dcbaf-180">char</span><span class="sxs-lookup"><span data-stu-id="dcbaf-180">char</span></span>
- <span data-ttu-id="dcbaf-181">Cmdletbindingattribute</span><span class="sxs-lookup"><span data-stu-id="dcbaf-181">CmdletBindingAttribute</span></span>
- <span data-ttu-id="dcbaf-182">DateTime</span><span class="sxs-lookup"><span data-stu-id="dcbaf-182">DateTime</span></span>
- <span data-ttu-id="dcbaf-183">decimal</span><span class="sxs-lookup"><span data-stu-id="dcbaf-183">decimal</span></span>
- <span data-ttu-id="dcbaf-184">DirectoryEntry</span><span class="sxs-lookup"><span data-stu-id="dcbaf-184">DirectoryEntry</span></span>
- <span data-ttu-id="dcbaf-185">DirectorySearcher</span><span class="sxs-lookup"><span data-stu-id="dcbaf-185">DirectorySearcher</span></span>
- <span data-ttu-id="dcbaf-186">double</span><span class="sxs-lookup"><span data-stu-id="dcbaf-186">double</span></span>
- <span data-ttu-id="dcbaf-187">float</span><span class="sxs-lookup"><span data-stu-id="dcbaf-187">float</span></span>
- <span data-ttu-id="dcbaf-188">Guid</span><span class="sxs-lookup"><span data-stu-id="dcbaf-188">Guid</span></span>
- <span data-ttu-id="dcbaf-189">Hashtable</span><span class="sxs-lookup"><span data-stu-id="dcbaf-189">Hashtable</span></span>
- <span data-ttu-id="dcbaf-190">INT</span><span class="sxs-lookup"><span data-stu-id="dcbaf-190">int</span></span>
- <span data-ttu-id="dcbaf-191">Int16</span><span class="sxs-lookup"><span data-stu-id="dcbaf-191">Int16</span></span>
- <span data-ttu-id="dcbaf-192">long</span><span class="sxs-lookup"><span data-stu-id="dcbaf-192">long</span></span>
- <span data-ttu-id="dcbaf-193">ManagementClass</span><span class="sxs-lookup"><span data-stu-id="dcbaf-193">ManagementClass</span></span>
- <span data-ttu-id="dcbaf-194">ManagementObject</span><span class="sxs-lookup"><span data-stu-id="dcbaf-194">ManagementObject</span></span>
- <span data-ttu-id="dcbaf-195">ManagementObjectSearcher</span><span class="sxs-lookup"><span data-stu-id="dcbaf-195">ManagementObjectSearcher</span></span>
- <span data-ttu-id="dcbaf-196">NULL-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="dcbaf-196">NullString</span></span>
- <span data-ttu-id="dcbaf-197">Outputtypeer Attribute</span><span class="sxs-lookup"><span data-stu-id="dcbaf-197">OutputTypeAttribute</span></span>
- <span data-ttu-id="dcbaf-198">Parameter Attribute</span><span class="sxs-lookup"><span data-stu-id="dcbaf-198">ParameterAttribute</span></span>
- <span data-ttu-id="dcbaf-199">PSCredential</span><span class="sxs-lookup"><span data-stu-id="dcbaf-199">PSCredential</span></span>
- <span data-ttu-id="dcbaf-200">Psdefaultvalueattribute</span><span class="sxs-lookup"><span data-stu-id="dcbaf-200">PSDefaultValueAttribute</span></span>
- <span data-ttu-id="dcbaf-201">Pslistmodifier</span><span class="sxs-lookup"><span data-stu-id="dcbaf-201">PSListModifier</span></span>
- <span data-ttu-id="dcbaf-202">PSObject</span><span class="sxs-lookup"><span data-stu-id="dcbaf-202">PSObject</span></span>
- <span data-ttu-id="dcbaf-203">Psprientschärvedictionary</span><span class="sxs-lookup"><span data-stu-id="dcbaf-203">PSPrimitiveDictionary</span></span>
- <span data-ttu-id="dcbaf-204">Psreference</span><span class="sxs-lookup"><span data-stu-id="dcbaf-204">PSReference</span></span>
- <span data-ttu-id="dcbaf-205">Pstypameattribute</span><span class="sxs-lookup"><span data-stu-id="dcbaf-205">PSTypeNameAttribute</span></span>
- <span data-ttu-id="dcbaf-206">RegEx</span><span class="sxs-lookup"><span data-stu-id="dcbaf-206">Regex</span></span>
- <span data-ttu-id="dcbaf-207">SByte</span><span class="sxs-lookup"><span data-stu-id="dcbaf-207">SByte</span></span>
- <span data-ttu-id="dcbaf-208">string</span><span class="sxs-lookup"><span data-stu-id="dcbaf-208">string</span></span>
- <span data-ttu-id="dcbaf-209">Supportswildcardsattribute</span><span class="sxs-lookup"><span data-stu-id="dcbaf-209">SupportsWildcardsAttribute</span></span>
- <span data-ttu-id="dcbaf-210">SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="dcbaf-210">SwitchParameter</span></span>
- <span data-ttu-id="dcbaf-211">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="dcbaf-211">System.Globalization.CultureInfo</span></span>
- <span data-ttu-id="dcbaf-212">System .net. IPAddress</span><span class="sxs-lookup"><span data-stu-id="dcbaf-212">System.Net.IPAddress</span></span>
- <span data-ttu-id="dcbaf-213">System .net. Mail. MailAddress</span><span class="sxs-lookup"><span data-stu-id="dcbaf-213">System.Net.Mail.MailAddress</span></span>
- <span data-ttu-id="dcbaf-214">System. Numerics. BigInteger</span><span class="sxs-lookup"><span data-stu-id="dcbaf-214">System.Numerics.BigInteger</span></span>
- <span data-ttu-id="dcbaf-215">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="dcbaf-215">System.Security.SecureString</span></span>
- <span data-ttu-id="dcbaf-216">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="dcbaf-216">TimeSpan</span></span>
- <span data-ttu-id="dcbaf-217">UInt16</span><span class="sxs-lookup"><span data-stu-id="dcbaf-217">UInt16</span></span>
- <span data-ttu-id="dcbaf-218">UInt32</span><span class="sxs-lookup"><span data-stu-id="dcbaf-218">UInt32</span></span>
- <span data-ttu-id="dcbaf-219">UInt64</span><span class="sxs-lookup"><span data-stu-id="dcbaf-219">UInt64</span></span>

### <a name="finding-the-language-mode-of-a-session-configuration"></a><span data-ttu-id="dcbaf-220">Suchen des Sprachmodus einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="dcbaf-220">FINDING THE LANGUAGE MODE OF A SESSION CONFIGURATION</span></span>

<span data-ttu-id="dcbaf-221">Wenn eine Sitzungs Konfiguration mithilfe einer Sitzungs Konfigurationsdatei erstellt wird, verfügt die Sitzungs Konfiguration über eine languagemode-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-221">When a session configuration is created by using a session configuration file, the session configuration has a LanguageMode property.</span></span> <span data-ttu-id="dcbaf-222">Sie können den Sprachmodus suchen, indem Sie den Wert der languagemode-Eigenschaft abrufen.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-222">You can find the language mode by getting the value of the LanguageMode property.</span></span>

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

<span data-ttu-id="dcbaf-223">Bei anderen Sitzungs Konfigurationen können Sie den Sprachmodus indirekt ermitteln, indem Sie den Sprachmodus einer Sitzung ermitteln, die mit der Sitzungs Konfiguration erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-223">On other session configurations, you can find the language mode indirectly by finding the language mode of a session that is created by using the session configuration.</span></span>

### <a name="finding-the-language-mode-of-a-session"></a><span data-ttu-id="dcbaf-224">Suchen des Sprachmodus einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="dcbaf-224">FINDING THE LANGUAGE MODE OF A SESSION</span></span>

<span data-ttu-id="dcbaf-225">Sie können den Sprachmodus einer vollständigen Sprache oder einschräninedlanguage-Sitzung ermitteln, indem Sie den Wert der languagemode-Eigenschaft des Sitzungs Zustands abrufen.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-225">You can find the language mode of a FullLanguage or ConstrainedLanguage session by getting the value of the LanguageMode property of the session state.</span></span>

<span data-ttu-id="dcbaf-226">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dcbaf-226">For example:</span></span>

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

<span data-ttu-id="dcbaf-227">In Sitzungen mit den Modi restrictedlanguage und nolanguage können Sie die Punkt-Methode jedoch nicht verwenden, um Eigenschaftswerte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-227">However, in sessions with RestrictedLanguage and NoLanguage modes, you cannot use the dot method to get property values.</span></span> <span data-ttu-id="dcbaf-228">Stattdessen wird in der Fehlermeldung der Sprachmodus angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-228">Instead, the error message reveals the language mode.</span></span>

<span data-ttu-id="dcbaf-229">Wenn Sie den `$ExecutionContext.SessionState.LanguageMode` Befehl in einer restrictedlanguage-Sitzung ausführen, gibt PowerShell die Fehlermeldungen propertyreferencenotsupportedindatasection und variablereferencenotsupportedindatasection zurück.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-229">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a RestrictedLanguage session, PowerShell returns the PropertyReferenceNotSupportedInDataSection and VariableReferenceNotSupportedInDataSection error messages.</span></span>

- <span data-ttu-id="dcbaf-230">Propertyreferencenotsupportedindatasection: Eigenschafts Verweise sind im eingeschränkten Sprachmodus oder in einem Daten Abschnitt nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-230">PropertyReferenceNotSupportedInDataSection: Property references are not allowed in restricted language mode or a Data section.</span></span>
- <span data-ttu-id="dcbaf-231">Variablereferencenotsupportedindatasection eine Variable, auf die im eingeschränkten Sprachmodus nicht verwiesen werden kann, oder auf einen Daten Abschnitt wird verwiesen.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-231">VariableReferenceNotSupportedInDataSection A variable that cannot be referenced in restricted language mode or a Data section is being referenced.</span></span>

<span data-ttu-id="dcbaf-232">Wenn Sie den `$ExecutionContext.SessionState.LanguageMode` Befehl in einer nolanguage-Sitzung ausführen, gibt PowerShell die scripznotallowed-Fehlermeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-232">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a NoLanguage session, PowerShell returns the ScriptsNotAllowed error message.</span></span>

- <span data-ttu-id="dcbaf-233">Scripznotallowed: die Syntax wird von diesem Runspace nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-233">ScriptsNotAllowed: The syntax is not supported by this runspace.</span></span> <span data-ttu-id="dcbaf-234">Dies liegt möglicherweise daran, dass es sich um einen nicht Sprachmodus handelt.</span><span class="sxs-lookup"><span data-stu-id="dcbaf-234">This might be because it is in no-language mode.</span></span>

## <a name="keywords"></a><span data-ttu-id="dcbaf-235">Keywords</span><span class="sxs-lookup"><span data-stu-id="dcbaf-235">KEYWORDS</span></span>

- <span data-ttu-id="dcbaf-236">about_ConstrainedLanguage</span><span class="sxs-lookup"><span data-stu-id="dcbaf-236">about_ConstrainedLanguage</span></span>
- <span data-ttu-id="dcbaf-237">about_FullLanguage</span><span class="sxs-lookup"><span data-stu-id="dcbaf-237">about_FullLanguage</span></span>
- <span data-ttu-id="dcbaf-238">about_NoLanguage</span><span class="sxs-lookup"><span data-stu-id="dcbaf-238">about_NoLanguage</span></span>
- <span data-ttu-id="dcbaf-239">about_RestrictedLanguage</span><span class="sxs-lookup"><span data-stu-id="dcbaf-239">about_RestrictedLanguage</span></span>

## <a name="see-also"></a><span data-ttu-id="dcbaf-240">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="dcbaf-240">SEE ALSO</span></span>

- [<span data-ttu-id="dcbaf-241">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="dcbaf-241">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)
- [<span data-ttu-id="dcbaf-242">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="dcbaf-242">about_Session_Configurations</span></span>](about_Session_Configurations.md)
