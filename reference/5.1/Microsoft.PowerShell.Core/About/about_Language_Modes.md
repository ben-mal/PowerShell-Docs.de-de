---
description: Erläutert die sprach Modi und ihre Auswirkung auf PowerShell-Sitzungen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: a75afd5149f3d290a8ec377417d4920b0ad6b526
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222692"
---
# <a name="about-language-modes"></a><span data-ttu-id="9092d-104">Informationen zu sprach Modi</span><span class="sxs-lookup"><span data-stu-id="9092d-104">About Language Modes</span></span>

## <a name="short-description"></a><span data-ttu-id="9092d-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9092d-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="9092d-106">Erläutert die sprach Modi und ihre Auswirkung auf PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="9092d-106">Explains language modes and their effect on PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="9092d-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9092d-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="9092d-108">Der Sprachmodus einer PowerShell-Sitzung bestimmt teilweise, welche Elemente der PowerShell-Sprache in der Sitzung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9092d-108">The language mode of a PowerShell session determines, in part, which elements of the PowerShell language can be used in the session.</span></span>

<span data-ttu-id="9092d-109">PowerShell unterstützt die folgenden sprach Modi:</span><span class="sxs-lookup"><span data-stu-id="9092d-109">PowerShell supports the following language modes:</span></span>

- <span data-ttu-id="9092d-110">FullLanguage</span><span class="sxs-lookup"><span data-stu-id="9092d-110">FullLanguage</span></span>
- <span data-ttu-id="9092d-111">Einschräninedlanguage (eingeführt in PowerShell 3,0)</span><span class="sxs-lookup"><span data-stu-id="9092d-111">ConstrainedLanguage (introduced in PowerShell 3.0)</span></span>
- <span data-ttu-id="9092d-112">Restrictedlanguage</span><span class="sxs-lookup"><span data-stu-id="9092d-112">RestrictedLanguage</span></span>
- <span data-ttu-id="9092d-113">NoLanguage</span><span class="sxs-lookup"><span data-stu-id="9092d-113">NoLanguage</span></span>

### <a name="what-is-a-language-mode"></a><span data-ttu-id="9092d-114">Was ist ein Sprachmodus?</span><span class="sxs-lookup"><span data-stu-id="9092d-114">WHAT IS A LANGUAGE MODE?</span></span>

<span data-ttu-id="9092d-115">Der Sprachmodus bestimmt die Sprachelemente, die in der Sitzung zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9092d-115">The language mode determines the language elements that are permitted in the session.</span></span>

<span data-ttu-id="9092d-116">Der Sprachmodus ist tatsächlich eine Eigenschaft der Sitzungs Konfiguration (oder des "Endpunkts"), die verwendet wird, um die Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9092d-116">The language mode is actually a property of the session configuration (or "endpoint") that is used to create the session.</span></span> <span data-ttu-id="9092d-117">Alle Sitzungen, die eine bestimmte Sitzungs Konfiguration verwenden, haben den Sprachmodus der Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="9092d-117">All sessions that use a particular session configuration have the language mode of the session configuration.</span></span>

<span data-ttu-id="9092d-118">Alle PowerShell-Sitzungen verfügen über einen Sprachmodus, einschließlich pssessions, die Sie mithilfe des `New-PSSession` Cmdlets erstellen, temporäre Sitzungen mit dem Computername-Parameter und die Standard Sitzungen, die beim Starten von PowerShell angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9092d-118">All PowerShell sessions have a language mode, including PSSessions that you create by using the `New-PSSession` cmdlet, temporary sessions that use the ComputerName parameter, and the default sessions that appear when you start PowerShell.</span></span>

<span data-ttu-id="9092d-119">Remote Sitzungen werden mithilfe der Sitzungs Konfigurationen auf dem Remote Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="9092d-119">Remote sessions are created by using the session configurations on the remote computer.</span></span> <span data-ttu-id="9092d-120">Der Sprachmodus, der in der Sitzungs Konfiguration festgelegt ist, bestimmt den Sprachmodus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9092d-120">The language mode set in the session configuration determines the language mode of the session.</span></span> <span data-ttu-id="9092d-121">Um die Sitzungs Konfiguration einer PSSession anzugeben, verwenden Sie den ConfigurationName-Parameter von Cmdlets, die eine Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="9092d-121">To specify the session configuration of a PSSession, use the ConfigurationName parameter of cmdlets that create a session.</span></span>

### <a name="language-modes"></a><span data-ttu-id="9092d-122">sprach Modi</span><span class="sxs-lookup"><span data-stu-id="9092d-122">LANGUAGE MODES</span></span>

<span data-ttu-id="9092d-123">In diesem Abschnitt werden die sprach Modi in PowerShell-Sitzungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9092d-123">This section describes the language modes in PowerShell sessions.</span></span>

#### <a name="full-language-fulllanguage"></a><span data-ttu-id="9092d-124">Vollständige Sprache (vollständig)</span><span class="sxs-lookup"><span data-stu-id="9092d-124">FULL LANGUAGE (FullLanguage)</span></span>

<span data-ttu-id="9092d-125">Im voll Sprachmodus sind alle Sprachelemente in der Sitzung zulässig.</span><span class="sxs-lookup"><span data-stu-id="9092d-125">The FullLanguage mode permits all language elements in the session.</span></span>
<span data-ttu-id="9092d-126">Fulllanguage ist der Standard Sprachmodus für Standard Sitzungen in allen Windows-Versionen mit Ausnahme von Windows RT.</span><span class="sxs-lookup"><span data-stu-id="9092d-126">FullLanguage is the default language mode for default sessions on all versions of Windows except for Windows RT.</span></span>

#### <a name="restricted-language-restrictedlanguage"></a><span data-ttu-id="9092d-127">Eingeschränkte Sprache (restrictedlanguage)</span><span class="sxs-lookup"><span data-stu-id="9092d-127">RESTRICTED LANGUAGE (RestrictedLanguage)</span></span>

<span data-ttu-id="9092d-128">Im restrictedlanguage-Modus können Benutzer Befehle (Cmdlets, Funktionen, CIM-Befehle und Workflows) ausführen, aber Sie dürfen keine Skriptblöcke verwenden.</span><span class="sxs-lookup"><span data-stu-id="9092d-128">In RestrictedLanguage mode, users may run commands (cmdlets, functions, CIM commands, and workflows) but are not permitted to use script blocks.</span></span>

<span data-ttu-id="9092d-129">Standardmäßig sind nur die folgenden Variablen im restrictedlanguage-Modus zulässig:</span><span class="sxs-lookup"><span data-stu-id="9092d-129">By default, only the following variables are permitted in RestrictedLanguage mode:</span></span>

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

<span data-ttu-id="9092d-130">Nur die folgenden Vergleichs Operatoren sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="9092d-130">Only the following comparison operators are permitted:</span></span>

- <span data-ttu-id="9092d-131">`-eq` hoch</span><span class="sxs-lookup"><span data-stu-id="9092d-131">`-eq` (equal)</span></span>
- <span data-ttu-id="9092d-132">`-gt` (größer als)</span><span class="sxs-lookup"><span data-stu-id="9092d-132">`-gt` (greater-than)</span></span>
- <span data-ttu-id="9092d-133">`-lt` (kleiner als)</span><span class="sxs-lookup"><span data-stu-id="9092d-133">`-lt` (less-than)</span></span>

<span data-ttu-id="9092d-134">Zuweisungsanweisungen, Eigenschaftsverweise und Methodenaufrufe sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="9092d-134">Assignment statements, property references, and method calls are not permitted.</span></span>

#### <a name="no-language-nolanguage"></a><span data-ttu-id="9092d-135">Keine Sprache (nolanguage)</span><span class="sxs-lookup"><span data-stu-id="9092d-135">NO LANGUAGE (NoLanguage)</span></span>

<span data-ttu-id="9092d-136">Der nolanguage-Modus kann nur über die API verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9092d-136">NoLanguage mode can only be used through the API.</span></span> <span data-ttu-id="9092d-137">Der nolanguage-Modus bedeutet, dass kein Skript Text eines beliebigen Formulars zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="9092d-137">NoLanguage mode means no script text of any form is permitted.</span></span> <span data-ttu-id="9092d-138">Dies verhindert die Verwendung der **addScript ()** -Methode, die Fragmente von PowerShell-Skripts sendet, die analysiert und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9092d-138">This precludes the use of the **AddScript()** method which sends fragments of PowerShell script to be parsed and executed.</span></span> <span data-ttu-id="9092d-139">Sie können nur **AddCommand ()** und **AddParameter ()** verwenden, die den Parser nicht durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="9092d-139">You can only use **AddCommand()** and **AddParameter()** which don't go through the parser.</span></span>

#### <a name="constrained-language-constrained-language"></a><span data-ttu-id="9092d-140">Eingeschränkte Sprache (eingeschränkte Sprache)</span><span class="sxs-lookup"><span data-stu-id="9092d-140">CONSTRAINED LANGUAGE (Constrained Language)</span></span>

<span data-ttu-id="9092d-141">Der Modus "einschräninedlanguage" erlaubt alle Cmdlets und alle PowerShell-Sprachelemente, schränkt jedoch zulässige Typen ein.</span><span class="sxs-lookup"><span data-stu-id="9092d-141">The ConstrainedLanguage mode permits all cmdlets and all PowerShell language elements, but it limits permitted types.</span></span>

<span data-ttu-id="9092d-142">Der Modus "einschränder Modus" ist für die Unterstützung der Code Integrität (User Mode Code Integrity, Umschlag Code) in Windows RT konzipiert.</span><span class="sxs-lookup"><span data-stu-id="9092d-142">ConstrainedLanguage mode is designed to support User Mode Code Integrity (UMCI) on Windows RT.</span></span> <span data-ttu-id="9092d-143">Dabei handelt es sich um den einzigen unterstützten Sprachmodus unter Windows RT, der jedoch auf allen unterstützten Systemen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9092d-143">It is the only supported language mode on Windows RT, but it is available on all supported systems.</span></span>

<span data-ttu-id="9092d-144">Durch die über CI werden Arm-Geräte geschützt, da nur Microsoft-signierte und Microsoft-zertifizierte apps auf Windows RT-basierten Geräten installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="9092d-144">UMCI protects ARM devices by allowing only Microsoft-signed and Microsoft-certified apps to be installed on Windows RT-based devices.</span></span>
<span data-ttu-id="9092d-145">Der Modus "einschränken" verhindert, dass Benutzer PowerShell verwenden, um umci zu umgehen oder zu verletzen.</span><span class="sxs-lookup"><span data-stu-id="9092d-145">ConstrainedLanguage mode prevents users from using PowerShell to circumvent or violate UMCI.</span></span>

<span data-ttu-id="9092d-146">Die Features des einschräninedlanguage-Modus lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9092d-146">The features of ConstrainedLanguage mode are as follows:</span></span>

- <span data-ttu-id="9092d-147">Alle Cmdlets in Windows-Modulen und andere umci-genehmigte Cmdlets sind voll funktionsfähig und verfügen über vollständigen Zugriff auf Systemressourcen, außer wie bereits erwähnt.</span><span class="sxs-lookup"><span data-stu-id="9092d-147">All cmdlets in Windows modules, and other UMCI-approved cmdlets, are fully functional and have complete access to system resources, except as noted.</span></span>

- <span data-ttu-id="9092d-148">Alle Elemente der PowerShell-Skriptsprache sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9092d-148">All elements of the PowerShell scripting language are permitted.</span></span>

- <span data-ttu-id="9092d-149">Alle in Windows enthaltenen Module können importiert werden, und alle Befehle, die vom Modul exportiert werden, werden in der Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9092d-149">All modules included in Windows can be imported and all commands that the modules export run in the session.</span></span>

- <span data-ttu-id="9092d-150">Im PowerShell-Workflow können Sie Skript Workflows (in der PowerShell-Sprache geschriebene Workflows) schreiben und ausführen.</span><span class="sxs-lookup"><span data-stu-id="9092d-150">In PowerShell Workflow, you can write and run script workflows (workflows written in the PowerShell language).</span></span> <span data-ttu-id="9092d-151">XAML-basierte Workflows werden nicht unterstützt, und Sie können XAML nicht in einem Skript Workflow ausführen, z `Invoke-Expression -Language XAML` . b. mithilfe von.</span><span class="sxs-lookup"><span data-stu-id="9092d-151">XAML-based workflows are not supported and you cannot run XAML in a script workflow, such as by using `Invoke-Expression -Language XAML`.</span></span> <span data-ttu-id="9092d-152">Workflows können auch keine anderen Workflows aufzurufen, obwohl es zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="9092d-152">Also, workflows cannot call other workflows, although nested workflows are permitted.</span></span>

- <span data-ttu-id="9092d-153">Das `Add-Type` Cmdlet kann signierte Assemblys laden, aber keinen beliebigen c#-Code oder Win32-APIs laden.</span><span class="sxs-lookup"><span data-stu-id="9092d-153">The `Add-Type` cmdlet can load signed assemblies, but it cannot load arbitrary C# code or Win32 APIs.</span></span>

- <span data-ttu-id="9092d-154">Das- `New-Object` Cmdlet kann nur für zulässige Typen verwendet werden (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="9092d-154">The `New-Object` cmdlet can be used only on allowed types (listed below).</span></span>

- <span data-ttu-id="9092d-155">Nur zulässige Typen (unten aufgeführt) können in PowerShell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9092d-155">Only allowed types (listed below) can be used in PowerShell.</span></span> <span data-ttu-id="9092d-156">Andere Typen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="9092d-156">Other types are not permitted.</span></span>

- <span data-ttu-id="9092d-157">Typkonvertierung ist zulässig, jedoch nur, wenn das Ergebnis ein zulässiger Typ ist.</span><span class="sxs-lookup"><span data-stu-id="9092d-157">Type conversion is permitted, but only when the result is an allowed type.</span></span>

- <span data-ttu-id="9092d-158">Cmdlet-Parameter, die Zeichen folgen Eingaben in Typen konvertieren, funktionieren nur, wenn der resultierende Typ ein zulässiger Typ ist.</span><span class="sxs-lookup"><span data-stu-id="9092d-158">Cmdlet parameters that convert string input to types work only when the resulting type is an allowed type.</span></span>

- <span data-ttu-id="9092d-159">Die **ToString ()** -Methode und die .NET-Methoden zulässiger Typen (siehe unten) können aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9092d-159">The **ToString()** method and the .NET methods of allowed types (listed below) can be invoked.</span></span> <span data-ttu-id="9092d-160">Andere Methoden können nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9092d-160">Other methods cannot be invoked.</span></span>

- <span data-ttu-id="9092d-161">Benutzer können alle Eigenschaften zulässiger Typen erhalten.</span><span class="sxs-lookup"><span data-stu-id="9092d-161">Users can get all properties of allowed types.</span></span> <span data-ttu-id="9092d-162">Benutzer können die Werte von Eigenschaften nur für die Kerntypen festlegen.</span><span class="sxs-lookup"><span data-stu-id="9092d-162">Users can set the values of properties only on Core types.</span></span> <span data-ttu-id="9092d-163">Nur die folgenden COM-Objekte sind zulässig:</span><span class="sxs-lookup"><span data-stu-id="9092d-163">Only the following COM objects are permitted:</span></span>

  - <span data-ttu-id="9092d-164">**Scripting. Dictionary**</span><span class="sxs-lookup"><span data-stu-id="9092d-164">**Scripting.Dictionary**</span></span>
  - <span data-ttu-id="9092d-165">**Scripting.FileSystemObject**</span><span class="sxs-lookup"><span data-stu-id="9092d-165">**Scripting.FileSystemObject**</span></span>
  - <span data-ttu-id="9092d-166">**VBScript. RegExp**</span><span class="sxs-lookup"><span data-stu-id="9092d-166">**VBScript.RegExp**</span></span>

<span data-ttu-id="9092d-167">Die folgenden Typen sind im Modus "eingeschränkt" zulässig.</span><span class="sxs-lookup"><span data-stu-id="9092d-167">The following types are permitted in ConstrainedLanguage mode.</span></span> <span data-ttu-id="9092d-168">Benutzer können Eigenschaften erhalten, Methoden aufrufen und Objekte in diese Typen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9092d-168">Users can get properties, invoke methods, and convert objects to these types.</span></span>

<span data-ttu-id="9092d-169">Zulässige Typen:</span><span class="sxs-lookup"><span data-stu-id="9092d-169">Allowed Types:</span></span>

- <span data-ttu-id="9092d-170">Aliasattribute</span><span class="sxs-lookup"><span data-stu-id="9092d-170">AliasAttribute</span></span>
- <span data-ttu-id="9092d-171">' Zubei ' zuder Zuordnung</span><span class="sxs-lookup"><span data-stu-id="9092d-171">AllowEmptyCollectionAttribute</span></span>
- <span data-ttu-id="9092d-172">' Zubei ' zuder Zuweisung</span><span class="sxs-lookup"><span data-stu-id="9092d-172">AllowEmptyStringAttribute</span></span>
- <span data-ttu-id="9092d-173">Allownullattribute</span><span class="sxs-lookup"><span data-stu-id="9092d-173">AllowNullAttribute</span></span>
- <span data-ttu-id="9092d-174">Array</span><span class="sxs-lookup"><span data-stu-id="9092d-174">Array</span></span>
- <span data-ttu-id="9092d-175">Bool</span><span class="sxs-lookup"><span data-stu-id="9092d-175">Bool</span></span>
- <span data-ttu-id="9092d-176">byte</span><span class="sxs-lookup"><span data-stu-id="9092d-176">byte</span></span>
- <span data-ttu-id="9092d-177">char</span><span class="sxs-lookup"><span data-stu-id="9092d-177">char</span></span>
- <span data-ttu-id="9092d-178">Cmdletbindingattribute</span><span class="sxs-lookup"><span data-stu-id="9092d-178">CmdletBindingAttribute</span></span>
- <span data-ttu-id="9092d-179">DateTime</span><span class="sxs-lookup"><span data-stu-id="9092d-179">DateTime</span></span>
- <span data-ttu-id="9092d-180">decimal</span><span class="sxs-lookup"><span data-stu-id="9092d-180">decimal</span></span>
- <span data-ttu-id="9092d-181">DirectoryEntry</span><span class="sxs-lookup"><span data-stu-id="9092d-181">DirectoryEntry</span></span>
- <span data-ttu-id="9092d-182">DirectorySearcher</span><span class="sxs-lookup"><span data-stu-id="9092d-182">DirectorySearcher</span></span>
- <span data-ttu-id="9092d-183">double</span><span class="sxs-lookup"><span data-stu-id="9092d-183">double</span></span>
- <span data-ttu-id="9092d-184">float</span><span class="sxs-lookup"><span data-stu-id="9092d-184">float</span></span>
- <span data-ttu-id="9092d-185">Guid</span><span class="sxs-lookup"><span data-stu-id="9092d-185">Guid</span></span>
- <span data-ttu-id="9092d-186">Hashtable</span><span class="sxs-lookup"><span data-stu-id="9092d-186">Hashtable</span></span>
- <span data-ttu-id="9092d-187">INT</span><span class="sxs-lookup"><span data-stu-id="9092d-187">int</span></span>
- <span data-ttu-id="9092d-188">Int16</span><span class="sxs-lookup"><span data-stu-id="9092d-188">Int16</span></span>
- <span data-ttu-id="9092d-189">long</span><span class="sxs-lookup"><span data-stu-id="9092d-189">long</span></span>
- <span data-ttu-id="9092d-190">ManagementClass</span><span class="sxs-lookup"><span data-stu-id="9092d-190">ManagementClass</span></span>
- <span data-ttu-id="9092d-191">ManagementObject</span><span class="sxs-lookup"><span data-stu-id="9092d-191">ManagementObject</span></span>
- <span data-ttu-id="9092d-192">ManagementObjectSearcher</span><span class="sxs-lookup"><span data-stu-id="9092d-192">ManagementObjectSearcher</span></span>
- <span data-ttu-id="9092d-193">NULL-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9092d-193">NullString</span></span>
- <span data-ttu-id="9092d-194">Outputtypeer Attribute</span><span class="sxs-lookup"><span data-stu-id="9092d-194">OutputTypeAttribute</span></span>
- <span data-ttu-id="9092d-195">Parameter Attribute</span><span class="sxs-lookup"><span data-stu-id="9092d-195">ParameterAttribute</span></span>
- <span data-ttu-id="9092d-196">PSCredential</span><span class="sxs-lookup"><span data-stu-id="9092d-196">PSCredential</span></span>
- <span data-ttu-id="9092d-197">Psdefaultvalueattribute</span><span class="sxs-lookup"><span data-stu-id="9092d-197">PSDefaultValueAttribute</span></span>
- <span data-ttu-id="9092d-198">Pslistmodifier</span><span class="sxs-lookup"><span data-stu-id="9092d-198">PSListModifier</span></span>
- <span data-ttu-id="9092d-199">PSObject</span><span class="sxs-lookup"><span data-stu-id="9092d-199">PSObject</span></span>
- <span data-ttu-id="9092d-200">Psprientschärvedictionary</span><span class="sxs-lookup"><span data-stu-id="9092d-200">PSPrimitiveDictionary</span></span>
- <span data-ttu-id="9092d-201">Psreference</span><span class="sxs-lookup"><span data-stu-id="9092d-201">PSReference</span></span>
- <span data-ttu-id="9092d-202">Pstypameattribute</span><span class="sxs-lookup"><span data-stu-id="9092d-202">PSTypeNameAttribute</span></span>
- <span data-ttu-id="9092d-203">RegEx</span><span class="sxs-lookup"><span data-stu-id="9092d-203">Regex</span></span>
- <span data-ttu-id="9092d-204">SByte</span><span class="sxs-lookup"><span data-stu-id="9092d-204">SByte</span></span>
- <span data-ttu-id="9092d-205">string</span><span class="sxs-lookup"><span data-stu-id="9092d-205">string</span></span>
- <span data-ttu-id="9092d-206">Supportswildcardsattribute</span><span class="sxs-lookup"><span data-stu-id="9092d-206">SupportsWildcardsAttribute</span></span>
- <span data-ttu-id="9092d-207">SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9092d-207">SwitchParameter</span></span>
- <span data-ttu-id="9092d-208">System. Globalization. CultureInfo</span><span class="sxs-lookup"><span data-stu-id="9092d-208">System.Globalization.CultureInfo</span></span>
- <span data-ttu-id="9092d-209">System .net. IPAddress</span><span class="sxs-lookup"><span data-stu-id="9092d-209">System.Net.IPAddress</span></span>
- <span data-ttu-id="9092d-210">System .net. Mail. MailAddress</span><span class="sxs-lookup"><span data-stu-id="9092d-210">System.Net.Mail.MailAddress</span></span>
- <span data-ttu-id="9092d-211">System. Numerics. BigInteger</span><span class="sxs-lookup"><span data-stu-id="9092d-211">System.Numerics.BigInteger</span></span>
- <span data-ttu-id="9092d-212">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="9092d-212">System.Security.SecureString</span></span>
- <span data-ttu-id="9092d-213">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="9092d-213">TimeSpan</span></span>
- <span data-ttu-id="9092d-214">UInt16</span><span class="sxs-lookup"><span data-stu-id="9092d-214">UInt16</span></span>
- <span data-ttu-id="9092d-215">UInt32</span><span class="sxs-lookup"><span data-stu-id="9092d-215">UInt32</span></span>
- <span data-ttu-id="9092d-216">UInt64</span><span class="sxs-lookup"><span data-stu-id="9092d-216">UInt64</span></span>

### <a name="finding-the-language-mode-of-a-session-configuration"></a><span data-ttu-id="9092d-217">Suchen des Sprachmodus einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9092d-217">FINDING THE LANGUAGE MODE OF A SESSION CONFIGURATION</span></span>

<span data-ttu-id="9092d-218">Wenn eine Sitzungs Konfiguration mithilfe einer Sitzungs Konfigurationsdatei erstellt wird, verfügt die Sitzungs Konfiguration über eine languagemode-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9092d-218">When a session configuration is created by using a session configuration file, the session configuration has a LanguageMode property.</span></span> <span data-ttu-id="9092d-219">Sie können den Sprachmodus suchen, indem Sie den Wert der languagemode-Eigenschaft abrufen.</span><span class="sxs-lookup"><span data-stu-id="9092d-219">You can find the language mode by getting the value of the LanguageMode property.</span></span>

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

<span data-ttu-id="9092d-220">Bei anderen Sitzungs Konfigurationen können Sie den Sprachmodus indirekt ermitteln, indem Sie den Sprachmodus einer Sitzung ermitteln, die mit der Sitzungs Konfiguration erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9092d-220">On other session configurations, you can find the language mode indirectly by finding the language mode of a session that is created by using the session configuration.</span></span>

### <a name="finding-the-language-mode-of-a-session"></a><span data-ttu-id="9092d-221">Suchen des Sprachmodus einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="9092d-221">FINDING THE LANGUAGE MODE OF A SESSION</span></span>

<span data-ttu-id="9092d-222">Sie können den Sprachmodus einer vollständigen Sprache oder einschräninedlanguage-Sitzung ermitteln, indem Sie den Wert der languagemode-Eigenschaft des Sitzungs Zustands abrufen.</span><span class="sxs-lookup"><span data-stu-id="9092d-222">You can find the language mode of a FullLanguage or ConstrainedLanguage session by getting the value of the LanguageMode property of the session state.</span></span>

<span data-ttu-id="9092d-223">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9092d-223">For example:</span></span>

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

<span data-ttu-id="9092d-224">In Sitzungen mit den Modi restrictedlanguage und nolanguage können Sie die Punkt-Methode jedoch nicht verwenden, um Eigenschaftswerte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9092d-224">However, in sessions with RestrictedLanguage and NoLanguage modes, you cannot use the dot method to get property values.</span></span> <span data-ttu-id="9092d-225">Stattdessen wird in der Fehlermeldung der Sprachmodus angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9092d-225">Instead, the error message reveals the language mode.</span></span>

<span data-ttu-id="9092d-226">Wenn Sie den `$ExecutionContext.SessionState.LanguageMode` Befehl in einer restrictedlanguage-Sitzung ausführen, gibt PowerShell die Fehlermeldungen propertyreferencenotsupportedindatasection und variablereferencenotsupportedindatasection zurück.</span><span class="sxs-lookup"><span data-stu-id="9092d-226">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a RestrictedLanguage session, PowerShell returns the PropertyReferenceNotSupportedInDataSection and VariableReferenceNotSupportedInDataSection error messages.</span></span>

- <span data-ttu-id="9092d-227">Propertyreferencenotsupportedindatasection: Eigenschafts Verweise sind im eingeschränkten Sprachmodus oder in einem Daten Abschnitt nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="9092d-227">PropertyReferenceNotSupportedInDataSection: Property references are not allowed in restricted language mode or a Data section.</span></span>
- <span data-ttu-id="9092d-228">Variablereferencenotsupportedindatasection eine Variable, auf die im eingeschränkten Sprachmodus nicht verwiesen werden kann, oder auf einen Daten Abschnitt wird verwiesen.</span><span class="sxs-lookup"><span data-stu-id="9092d-228">VariableReferenceNotSupportedInDataSection A variable that cannot be referenced in restricted language mode or a Data section is being referenced.</span></span>

<span data-ttu-id="9092d-229">Wenn Sie den `$ExecutionContext.SessionState.LanguageMode` Befehl in einer nolanguage-Sitzung ausführen, gibt PowerShell die scripznotallowed-Fehlermeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="9092d-229">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a NoLanguage session, PowerShell returns the ScriptsNotAllowed error message.</span></span>

- <span data-ttu-id="9092d-230">Scripznotallowed: die Syntax wird von diesem Runspace nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9092d-230">ScriptsNotAllowed: The syntax is not supported by this runspace.</span></span> <span data-ttu-id="9092d-231">Dies liegt möglicherweise daran, dass es sich um einen nicht Sprachmodus handelt.</span><span class="sxs-lookup"><span data-stu-id="9092d-231">This might be because it is in no-language mode.</span></span>

## <a name="keywords"></a><span data-ttu-id="9092d-232">Keywords</span><span class="sxs-lookup"><span data-stu-id="9092d-232">KEYWORDS</span></span>

- <span data-ttu-id="9092d-233">about_ConstrainedLanguage</span><span class="sxs-lookup"><span data-stu-id="9092d-233">about_ConstrainedLanguage</span></span>
- <span data-ttu-id="9092d-234">about_FullLanguage</span><span class="sxs-lookup"><span data-stu-id="9092d-234">about_FullLanguage</span></span>
- <span data-ttu-id="9092d-235">about_NoLanguage</span><span class="sxs-lookup"><span data-stu-id="9092d-235">about_NoLanguage</span></span>
- <span data-ttu-id="9092d-236">about_RestrictedLanguage</span><span class="sxs-lookup"><span data-stu-id="9092d-236">about_RestrictedLanguage</span></span>

## <a name="see-also"></a><span data-ttu-id="9092d-237">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="9092d-237">SEE ALSO</span></span>

- [<span data-ttu-id="9092d-238">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="9092d-238">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)
- [<span data-ttu-id="9092d-239">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="9092d-239">about_Session_Configurations</span></span>](about_Session_Configurations.md)
