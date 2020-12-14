---
description: Erläutert die sprach Modi und ihre Auswirkung auf PowerShell-Sitzungen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: 63b0edcb9465d10474a60c0d2a66c145baacc93f
ms.sourcegitcommit: fb1a4bc4b249afd3513663de2e1ba3025d63467e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "94625668"
---
# <a name="about-language-modes"></a><span data-ttu-id="e6cf7-104">Informationen zu sprach Modi</span><span class="sxs-lookup"><span data-stu-id="e6cf7-104">About Language Modes</span></span>

## <a name="short-description"></a><span data-ttu-id="e6cf7-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6cf7-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="e6cf7-106">Erläutert die sprach Modi und ihre Auswirkung auf PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-106">Explains language modes and their effect on PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="e6cf7-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6cf7-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e6cf7-108">Der Sprachmodus einer PowerShell-Sitzung bestimmt teilweise, welche Elemente der PowerShell-Sprache in der Sitzung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-108">The language mode of a PowerShell session determines, in part, which elements of the PowerShell language can be used in the session.</span></span>

<span data-ttu-id="e6cf7-109">PowerShell unterstützt die folgenden sprach Modi:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-109">PowerShell supports the following language modes:</span></span>

- <span data-ttu-id="e6cf7-110">FullLanguage</span><span class="sxs-lookup"><span data-stu-id="e6cf7-110">FullLanguage</span></span>
- <span data-ttu-id="e6cf7-111">Einschräninedlanguage (eingeführt in PowerShell 3,0)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-111">ConstrainedLanguage (introduced in PowerShell 3.0)</span></span>
- <span data-ttu-id="e6cf7-112">Restrictedlanguage</span><span class="sxs-lookup"><span data-stu-id="e6cf7-112">RestrictedLanguage</span></span>
- <span data-ttu-id="e6cf7-113">NoLanguage</span><span class="sxs-lookup"><span data-stu-id="e6cf7-113">NoLanguage</span></span>

### <a name="what-is-a-language-mode"></a><span data-ttu-id="e6cf7-114">Was ist ein Sprachmodus?</span><span class="sxs-lookup"><span data-stu-id="e6cf7-114">WHAT IS A LANGUAGE MODE?</span></span>

<span data-ttu-id="e6cf7-115">Der Sprachmodus bestimmt die Sprachelemente, die in der Sitzung zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-115">The language mode determines the language elements that are permitted in the session.</span></span>

<span data-ttu-id="e6cf7-116">Der Sprachmodus ist tatsächlich eine Eigenschaft der Sitzungs Konfiguration (oder des "Endpunkts"), die verwendet wird, um die Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-116">The language mode is actually a property of the session configuration (or "endpoint") that is used to create the session.</span></span> <span data-ttu-id="e6cf7-117">Alle Sitzungen, die eine bestimmte Sitzungs Konfiguration verwenden, haben den Sprachmodus der Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-117">All sessions that use a particular session configuration have the language mode of the session configuration.</span></span>

<span data-ttu-id="e6cf7-118">Alle PowerShell-Sitzungen verfügen über einen Sprachmodus, einschließlich pssessions, die Sie mithilfe des `New-PSSession` Cmdlets erstellen, temporäre Sitzungen mit dem Computername-Parameter und die Standard Sitzungen, die beim Starten von PowerShell angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-118">All PowerShell sessions have a language mode, including PSSessions that you create by using the `New-PSSession` cmdlet, temporary sessions that use the ComputerName parameter, and the default sessions that appear when you start PowerShell.</span></span>

<span data-ttu-id="e6cf7-119">Remote Sitzungen werden mithilfe der Sitzungs Konfigurationen auf dem Remote Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-119">Remote sessions are created by using the session configurations on the remote computer.</span></span> <span data-ttu-id="e6cf7-120">Der Sprachmodus, der in der Sitzungs Konfiguration festgelegt ist, bestimmt den Sprachmodus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-120">The language mode set in the session configuration determines the language mode of the session.</span></span> <span data-ttu-id="e6cf7-121">Um die Sitzungs Konfiguration einer PSSession anzugeben, verwenden Sie den ConfigurationName-Parameter von Cmdlets, die eine Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-121">To specify the session configuration of a PSSession, use the ConfigurationName parameter of cmdlets that create a session.</span></span>

### <a name="language-modes"></a><span data-ttu-id="e6cf7-122">sprach Modi</span><span class="sxs-lookup"><span data-stu-id="e6cf7-122">LANGUAGE MODES</span></span>

<span data-ttu-id="e6cf7-123">In diesem Abschnitt werden die sprach Modi in PowerShell-Sitzungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-123">This section describes the language modes in PowerShell sessions.</span></span>

#### <a name="full-language-fulllanguage"></a><span data-ttu-id="e6cf7-124">Vollständige Sprache (vollständig)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-124">FULL LANGUAGE (FullLanguage)</span></span>

<span data-ttu-id="e6cf7-125">Im voll Sprachmodus sind alle Sprachelemente in der Sitzung zulässig.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-125">The FullLanguage mode permits all language elements in the session.</span></span>
<span data-ttu-id="e6cf7-126">Fulllanguage ist der Standard Sprachmodus für Standard Sitzungen in allen Windows-Versionen mit Ausnahme von Windows RT.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-126">FullLanguage is the default language mode for default sessions on all versions of Windows except for Windows RT.</span></span>

#### <a name="restricted-language-restrictedlanguage"></a><span data-ttu-id="e6cf7-127">Eingeschränkte Sprache (restrictedlanguage)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-127">RESTRICTED LANGUAGE (RestrictedLanguage)</span></span>

<span data-ttu-id="e6cf7-128">Im restrictedlanguage-Modus können Benutzer Befehle (Cmdlets, Funktionen, CIM-Befehle und Workflows) ausführen, aber Sie dürfen keine Skriptblöcke verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-128">In RestrictedLanguage mode, users may run commands (cmdlets, functions, CIM commands, and workflows) but are not permitted to use script blocks.</span></span>

<span data-ttu-id="e6cf7-129">Standardmäßig sind nur die folgenden Variablen im restrictedlanguage-Modus zulässig:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-129">By default, only the following variables are permitted in RestrictedLanguage mode:</span></span>

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

<span data-ttu-id="e6cf7-130">Modul Manifeste, die den restrictedlanguage-Modus verwenden, lassen die folgenden zusätzlichen Variablen ebenfalls zu:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-130">Module manifests, which use RestrictedLanguage mode, permit the following additional variables as well:</span></span>

- `$PSScriptRoot`
- <span data-ttu-id="e6cf7-131">`$PSEdition` (in PowerShell Core)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-131">`$PSEdition` (in PowerShell Core)</span></span>
- <span data-ttu-id="e6cf7-132">`$EnabledExperimentalFeatures` (in PowerShell Core)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-132">`$EnabledExperimentalFeatures` (in PowerShell Core)</span></span>

<span data-ttu-id="e6cf7-133">Nur die folgenden Vergleichs Operatoren sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-133">Only the following comparison operators are permitted:</span></span>

- <span data-ttu-id="e6cf7-134">`-eq` hoch</span><span class="sxs-lookup"><span data-stu-id="e6cf7-134">`-eq` (equal)</span></span>
- <span data-ttu-id="e6cf7-135">`-gt` (größer als)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-135">`-gt` (greater-than)</span></span>
- <span data-ttu-id="e6cf7-136">`-lt` (kleiner als)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-136">`-lt` (less-than)</span></span>

<span data-ttu-id="e6cf7-137">Zuweisungsanweisungen, Eigenschaftsverweise und Methodenaufrufe sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-137">Assignment statements, property references, and method calls are not permitted.</span></span>

#### <a name="no-language-nolanguage"></a><span data-ttu-id="e6cf7-138">Keine Sprache (nolanguage)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-138">NO LANGUAGE (NoLanguage)</span></span>

<span data-ttu-id="e6cf7-139">Der nolanguage-Modus kann nur über die API verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-139">NoLanguage mode can only be used through the API.</span></span> <span data-ttu-id="e6cf7-140">Der nolanguage-Modus bedeutet, dass kein Skript Text eines beliebigen Formulars zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-140">NoLanguage mode means no script text of any form is permitted.</span></span> <span data-ttu-id="e6cf7-141">Dies verhindert die Verwendung der **addScript ()** -Methode, die Fragmente von PowerShell-Skripts sendet, die analysiert und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-141">This precludes the use of the **AddScript()** method which sends fragments of PowerShell script to be parsed and executed.</span></span> <span data-ttu-id="e6cf7-142">Sie können nur **AddCommand ()** und **AddParameter ()** verwenden, die den Parser nicht durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-142">You can only use **AddCommand()** and **AddParameter()** which don't go through the parser.</span></span>

#### <a name="constrained-language-constrained-language"></a><span data-ttu-id="e6cf7-143">Eingeschränkte Sprache (eingeschränkte Sprache)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-143">CONSTRAINED LANGUAGE (Constrained Language)</span></span>

<span data-ttu-id="e6cf7-144">Der Modus "einschräninedlanguage" erlaubt alle Cmdlets und alle PowerShell-Sprachelemente, schränkt jedoch zulässige Typen ein.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-144">The ConstrainedLanguage mode permits all cmdlets and all PowerShell language elements, but it limits permitted types.</span></span>

<span data-ttu-id="e6cf7-145">Der Modus "einschränder Modus" ist für die Unterstützung der Code Integrität (User Mode Code Integrity, Umschlag Code) in Windows RT konzipiert.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-145">ConstrainedLanguage mode is designed to support User Mode Code Integrity (UMCI) on Windows RT.</span></span> <span data-ttu-id="e6cf7-146">Dabei handelt es sich um den einzigen unterstützten Sprachmodus unter Windows RT, der jedoch auf allen unterstützten Systemen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-146">It is the only supported language mode on Windows RT, but it is available on all supported systems.</span></span>

<span data-ttu-id="e6cf7-147">Durch die über CI werden Arm-Geräte geschützt, da nur Microsoft-signierte und Microsoft-zertifizierte apps auf Windows RT-basierten Geräten installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-147">UMCI protects ARM devices by allowing only Microsoft-signed and Microsoft-certified apps to be installed on Windows RT-based devices.</span></span>
<span data-ttu-id="e6cf7-148">Der Modus "einschränken" verhindert, dass Benutzer PowerShell verwenden, um umci zu umgehen oder zu verletzen.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-148">ConstrainedLanguage mode prevents users from using PowerShell to circumvent or violate UMCI.</span></span>

<span data-ttu-id="e6cf7-149">Die Features des einschräninedlanguage-Modus lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-149">The features of ConstrainedLanguage mode are as follows:</span></span>

- <span data-ttu-id="e6cf7-150">Alle Cmdlets in Windows-Modulen und andere umci-genehmigte Cmdlets sind voll funktionsfähig und verfügen über vollständigen Zugriff auf Systemressourcen, außer wie bereits erwähnt.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-150">All cmdlets in Windows modules, and other UMCI-approved cmdlets, are fully functional and have complete access to system resources, except as noted.</span></span>

- <span data-ttu-id="e6cf7-151">Alle Elemente der PowerShell-Skriptsprache sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-151">All elements of the PowerShell scripting language are permitted.</span></span>

- <span data-ttu-id="e6cf7-152">Alle in Windows enthaltenen Module können importiert werden, und alle Befehle, die vom Modul exportiert werden, werden in der Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-152">All modules included in Windows can be imported and all commands that the modules export run in the session.</span></span>

- <span data-ttu-id="e6cf7-153">Im PowerShell-Workflow können Sie Skript Workflows (in der PowerShell-Sprache geschriebene Workflows) schreiben und ausführen.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-153">In PowerShell Workflow, you can write and run script workflows (workflows written in the PowerShell language).</span></span> <span data-ttu-id="e6cf7-154">XAML-basierte Workflows werden nicht unterstützt, und Sie können XAML nicht in einem Skript Workflow ausführen, z `Invoke-Expression -Language XAML` . b. mithilfe von.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-154">XAML-based workflows are not supported and you cannot run XAML in a script workflow, such as by using `Invoke-Expression -Language XAML`.</span></span> <span data-ttu-id="e6cf7-155">Workflows können auch keine anderen Workflows aufzurufen, obwohl es zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-155">Also, workflows cannot call other workflows, although nested workflows are permitted.</span></span>

- <span data-ttu-id="e6cf7-156">Das `Add-Type` Cmdlet kann signierte Assemblys laden, aber keinen beliebigen c#-Code oder Win32-APIs laden.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-156">The `Add-Type` cmdlet can load signed assemblies, but it cannot load arbitrary C# code or Win32 APIs.</span></span>

- <span data-ttu-id="e6cf7-157">Das- `New-Object` Cmdlet kann nur für zulässige Typen verwendet werden (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="e6cf7-157">The `New-Object` cmdlet can be used only on allowed types (listed below).</span></span>

- <span data-ttu-id="e6cf7-158">Nur zulässige Typen (unten aufgeführt) können in PowerShell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-158">Only allowed types (listed below) can be used in PowerShell.</span></span> <span data-ttu-id="e6cf7-159">Andere Typen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-159">Other types are not permitted.</span></span>

- <span data-ttu-id="e6cf7-160">Typkonvertierung ist zulässig, jedoch nur, wenn das Ergebnis ein zulässiger Typ ist.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-160">Type conversion is permitted, but only when the result is an allowed type.</span></span>

- <span data-ttu-id="e6cf7-161">Cmdlet-Parameter, die Zeichen folgen Eingaben in Typen konvertieren, funktionieren nur, wenn der resultierende Typ ein zulässiger Typ ist.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-161">Cmdlet parameters that convert string input to types work only when the resulting type is an allowed type.</span></span>

- <span data-ttu-id="e6cf7-162">Die **ToString ()** -Methode und die .NET-Methoden zulässiger Typen (siehe unten) können aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-162">The **ToString()** method and the .NET methods of allowed types (listed below) can be invoked.</span></span> <span data-ttu-id="e6cf7-163">Andere Methoden können nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-163">Other methods cannot be invoked.</span></span>

- <span data-ttu-id="e6cf7-164">Benutzer können alle Eigenschaften zulässiger Typen erhalten.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-164">Users can get all properties of allowed types.</span></span> <span data-ttu-id="e6cf7-165">Benutzer können die Werte von Eigenschaften nur für die Kerntypen festlegen.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-165">Users can set the values of properties only on Core types.</span></span> <span data-ttu-id="e6cf7-166">Nur die folgenden COM-Objekte sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-166">Only the following COM objects are permitted:</span></span>

  - <span data-ttu-id="e6cf7-167">**Scripting. Dictionary**</span><span class="sxs-lookup"><span data-stu-id="e6cf7-167">**Scripting.Dictionary**</span></span>
  - <span data-ttu-id="e6cf7-168">**Scripting.FileSystemObject**</span><span class="sxs-lookup"><span data-stu-id="e6cf7-168">**Scripting.FileSystemObject**</span></span>
  - <span data-ttu-id="e6cf7-169">**VBScript. RegExp**</span><span class="sxs-lookup"><span data-stu-id="e6cf7-169">**VBScript.RegExp**</span></span>

<span data-ttu-id="e6cf7-170">Die folgenden Typen sind im Modus "eingeschränkt" zulässig.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-170">The following types are permitted in ConstrainedLanguage mode.</span></span> <span data-ttu-id="e6cf7-171">Benutzer können Eigenschaften erhalten, Methoden aufrufen und Objekte in diese Typen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-171">Users can get properties, invoke methods, and convert objects to these types.</span></span>

<span data-ttu-id="e6cf7-172">Zulässige Typen:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-172">Allowed Types:</span></span>

- <span data-ttu-id="e6cf7-173">Aliasattribute</span><span class="sxs-lookup"><span data-stu-id="e6cf7-173">AliasAttribute</span></span>
- <span data-ttu-id="e6cf7-174">' Zubei ' zuder Zuordnung</span><span class="sxs-lookup"><span data-stu-id="e6cf7-174">AllowEmptyCollectionAttribute</span></span>
- <span data-ttu-id="e6cf7-175">' Zubei ' zuder Zuweisung</span><span class="sxs-lookup"><span data-stu-id="e6cf7-175">AllowEmptyStringAttribute</span></span>
- <span data-ttu-id="e6cf7-176">Allownullattribute</span><span class="sxs-lookup"><span data-stu-id="e6cf7-176">AllowNullAttribute</span></span>
- <span data-ttu-id="e6cf7-177">Array</span><span class="sxs-lookup"><span data-stu-id="e6cf7-177">Array</span></span>
- <span data-ttu-id="e6cf7-178">Bool</span><span class="sxs-lookup"><span data-stu-id="e6cf7-178">Bool</span></span>
- <span data-ttu-id="e6cf7-179">byte</span><span class="sxs-lookup"><span data-stu-id="e6cf7-179">byte</span></span>
- <span data-ttu-id="e6cf7-180">char</span><span class="sxs-lookup"><span data-stu-id="e6cf7-180">char</span></span>
- <span data-ttu-id="e6cf7-181">Cmdletbindingattribute</span><span class="sxs-lookup"><span data-stu-id="e6cf7-181">CmdletBindingAttribute</span></span>
- <span data-ttu-id="e6cf7-182">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6cf7-182">DateTime</span></span>
- <span data-ttu-id="e6cf7-183">Decimal</span><span class="sxs-lookup"><span data-stu-id="e6cf7-183">decimal</span></span>
- <span data-ttu-id="e6cf7-184">DirectoryEntry</span><span class="sxs-lookup"><span data-stu-id="e6cf7-184">DirectoryEntry</span></span>
- <span data-ttu-id="e6cf7-185">DirectorySearcher</span><span class="sxs-lookup"><span data-stu-id="e6cf7-185">DirectorySearcher</span></span>
- <span data-ttu-id="e6cf7-186">double</span><span class="sxs-lookup"><span data-stu-id="e6cf7-186">double</span></span>
- <span data-ttu-id="e6cf7-187">float</span><span class="sxs-lookup"><span data-stu-id="e6cf7-187">float</span></span>
- <span data-ttu-id="e6cf7-188">Guid</span><span class="sxs-lookup"><span data-stu-id="e6cf7-188">Guid</span></span>
- <span data-ttu-id="e6cf7-189">Hashtable</span><span class="sxs-lookup"><span data-stu-id="e6cf7-189">Hashtable</span></span>
- <span data-ttu-id="e6cf7-190">INT</span><span class="sxs-lookup"><span data-stu-id="e6cf7-190">int</span></span>
- <span data-ttu-id="e6cf7-191">Int16</span><span class="sxs-lookup"><span data-stu-id="e6cf7-191">Int16</span></span>
- <span data-ttu-id="e6cf7-192">long</span><span class="sxs-lookup"><span data-stu-id="e6cf7-192">long</span></span>
- <span data-ttu-id="e6cf7-193">ManagementClass</span><span class="sxs-lookup"><span data-stu-id="e6cf7-193">ManagementClass</span></span>
- <span data-ttu-id="e6cf7-194">ManagementObject</span><span class="sxs-lookup"><span data-stu-id="e6cf7-194">ManagementObject</span></span>
- <span data-ttu-id="e6cf7-195">ManagementObjectSearcher</span><span class="sxs-lookup"><span data-stu-id="e6cf7-195">ManagementObjectSearcher</span></span>
- <span data-ttu-id="e6cf7-196">NULL-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e6cf7-196">NullString</span></span>
- <span data-ttu-id="e6cf7-197">Outputtypeer Attribute</span><span class="sxs-lookup"><span data-stu-id="e6cf7-197">OutputTypeAttribute</span></span>
- <span data-ttu-id="e6cf7-198">Parameter Attribute</span><span class="sxs-lookup"><span data-stu-id="e6cf7-198">ParameterAttribute</span></span>
- <span data-ttu-id="e6cf7-199">PSCredential</span><span class="sxs-lookup"><span data-stu-id="e6cf7-199">PSCredential</span></span>
- <span data-ttu-id="e6cf7-200">Psdefaultvalueattribute</span><span class="sxs-lookup"><span data-stu-id="e6cf7-200">PSDefaultValueAttribute</span></span>
- <span data-ttu-id="e6cf7-201">Pslistmodifier</span><span class="sxs-lookup"><span data-stu-id="e6cf7-201">PSListModifier</span></span>
- <span data-ttu-id="e6cf7-202">PSObject</span><span class="sxs-lookup"><span data-stu-id="e6cf7-202">PSObject</span></span>
- <span data-ttu-id="e6cf7-203">Psprientschärvedictionary</span><span class="sxs-lookup"><span data-stu-id="e6cf7-203">PSPrimitiveDictionary</span></span>
- <span data-ttu-id="e6cf7-204">Psreference</span><span class="sxs-lookup"><span data-stu-id="e6cf7-204">PSReference</span></span>
- <span data-ttu-id="e6cf7-205">Pstypameattribute</span><span class="sxs-lookup"><span data-stu-id="e6cf7-205">PSTypeNameAttribute</span></span>
- <span data-ttu-id="e6cf7-206">RegEx</span><span class="sxs-lookup"><span data-stu-id="e6cf7-206">Regex</span></span>
- <span data-ttu-id="e6cf7-207">SByte</span><span class="sxs-lookup"><span data-stu-id="e6cf7-207">SByte</span></span>
- <span data-ttu-id="e6cf7-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e6cf7-208">string</span></span>
- <span data-ttu-id="e6cf7-209">Supportswildcardsattribute</span><span class="sxs-lookup"><span data-stu-id="e6cf7-209">SupportsWildcardsAttribute</span></span>
- <span data-ttu-id="e6cf7-210">SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e6cf7-210">SwitchParameter</span></span>
- <span data-ttu-id="e6cf7-211">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="e6cf7-211">System.Globalization.CultureInfo</span></span>
- <span data-ttu-id="e6cf7-212">System .net. IPAddress</span><span class="sxs-lookup"><span data-stu-id="e6cf7-212">System.Net.IPAddress</span></span>
- <span data-ttu-id="e6cf7-213">System .net. Mail. MailAddress</span><span class="sxs-lookup"><span data-stu-id="e6cf7-213">System.Net.Mail.MailAddress</span></span>
- <span data-ttu-id="e6cf7-214">System. Numerics. BigInteger</span><span class="sxs-lookup"><span data-stu-id="e6cf7-214">System.Numerics.BigInteger</span></span>
- <span data-ttu-id="e6cf7-215">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="e6cf7-215">System.Security.SecureString</span></span>
- <span data-ttu-id="e6cf7-216">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="e6cf7-216">TimeSpan</span></span>
- <span data-ttu-id="e6cf7-217">UInt16</span><span class="sxs-lookup"><span data-stu-id="e6cf7-217">UInt16</span></span>
- <span data-ttu-id="e6cf7-218">UInt32</span><span class="sxs-lookup"><span data-stu-id="e6cf7-218">UInt32</span></span>
- <span data-ttu-id="e6cf7-219">UInt64</span><span class="sxs-lookup"><span data-stu-id="e6cf7-219">UInt64</span></span>

### <a name="finding-the-language-mode-of-a-session-configuration"></a><span data-ttu-id="e6cf7-220">Suchen des Sprachmodus einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e6cf7-220">FINDING THE LANGUAGE MODE OF A SESSION CONFIGURATION</span></span>

<span data-ttu-id="e6cf7-221">Wenn eine Sitzungs Konfiguration mithilfe einer Sitzungs Konfigurationsdatei erstellt wird, verfügt die Sitzungs Konfiguration über eine languagemode-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-221">When a session configuration is created by using a session configuration file, the session configuration has a LanguageMode property.</span></span> <span data-ttu-id="e6cf7-222">Sie können den Sprachmodus suchen, indem Sie den Wert der languagemode-Eigenschaft abrufen.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-222">You can find the language mode by getting the value of the LanguageMode property.</span></span>

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

<span data-ttu-id="e6cf7-223">Bei anderen Sitzungs Konfigurationen können Sie den Sprachmodus indirekt ermitteln, indem Sie den Sprachmodus einer Sitzung ermitteln, die mit der Sitzungs Konfiguration erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-223">On other session configurations, you can find the language mode indirectly by finding the language mode of a session that is created by using the session configuration.</span></span>

### <a name="finding-the-language-mode-of-a-session"></a><span data-ttu-id="e6cf7-224">Suchen des Sprachmodus einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="e6cf7-224">FINDING THE LANGUAGE MODE OF A SESSION</span></span>

<span data-ttu-id="e6cf7-225">Sie können den Sprachmodus einer vollständigen Sprache oder einschräninedlanguage-Sitzung ermitteln, indem Sie den Wert der languagemode-Eigenschaft des Sitzungs Zustands abrufen.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-225">You can find the language mode of a FullLanguage or ConstrainedLanguage session by getting the value of the LanguageMode property of the session state.</span></span>

<span data-ttu-id="e6cf7-226">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-226">For example:</span></span>

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

<span data-ttu-id="e6cf7-227">In Sitzungen mit den Modi restrictedlanguage und nolanguage können Sie die Punkt-Methode jedoch nicht verwenden, um Eigenschaftswerte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-227">However, in sessions with RestrictedLanguage and NoLanguage modes, you cannot use the dot method to get property values.</span></span> <span data-ttu-id="e6cf7-228">Stattdessen wird in der Fehlermeldung der Sprachmodus angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-228">Instead, the error message reveals the language mode.</span></span>

<span data-ttu-id="e6cf7-229">Wenn Sie den `$ExecutionContext.SessionState.LanguageMode` Befehl in einer restrictedlanguage-Sitzung ausführen, gibt PowerShell die Fehlermeldungen propertyreferencenotsupportedindatasection und variablereferencenotsupportedindatasection zurück.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-229">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a RestrictedLanguage session, PowerShell returns the PropertyReferenceNotSupportedInDataSection and VariableReferenceNotSupportedInDataSection error messages.</span></span>

- <span data-ttu-id="e6cf7-230">Propertyreferencenotsupportedindatasection: Eigenschafts Verweise sind im eingeschränkten Sprachmodus oder in einem Daten Abschnitt nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-230">PropertyReferenceNotSupportedInDataSection: Property references are not allowed in restricted language mode or a Data section.</span></span>
- <span data-ttu-id="e6cf7-231">Variablereferencenotsupportedindatasection eine Variable, auf die im eingeschränkten Sprachmodus nicht verwiesen werden kann, oder auf einen Daten Abschnitt wird verwiesen.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-231">VariableReferenceNotSupportedInDataSection A variable that cannot be referenced in restricted language mode or a Data section is being referenced.</span></span>

<span data-ttu-id="e6cf7-232">Wenn Sie den `$ExecutionContext.SessionState.LanguageMode` Befehl in einer nolanguage-Sitzung ausführen, gibt PowerShell die scripznotallowed-Fehlermeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-232">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a NoLanguage session, PowerShell returns the ScriptsNotAllowed error message.</span></span>

- <span data-ttu-id="e6cf7-233">Scripznotallowed: die Syntax wird von diesem Runspace nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-233">ScriptsNotAllowed: The syntax is not supported by this runspace.</span></span> <span data-ttu-id="e6cf7-234">Dies liegt möglicherweise daran, dass es sich um einen nicht Sprachmodus handelt.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-234">This might be because it is in no-language mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6cf7-235">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="e6cf7-235">SEE ALSO</span></span>

- [<span data-ttu-id="e6cf7-236">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="e6cf7-236">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)
- [<span data-ttu-id="e6cf7-237">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="e6cf7-237">about_Session_Configurations</span></span>](about_Session_Configurations.md)
