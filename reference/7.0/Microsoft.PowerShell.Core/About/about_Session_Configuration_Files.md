---
description: Beschreibt die Sitzungs Konfigurationsdateien, die in einer Sitzungs Konfiguration (auch als "Endpunkt" bezeichnet) zum Definieren der Umgebung von Sitzungen verwendet werden, die die Sitzungs Konfiguration verwenden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configuration_files?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configuration_Files
ms.openlocfilehash: 113c068022f37b22cbcc5dae61a6a5edf26187d8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220591"
---
# <a name="about-session-configuration-files"></a><span data-ttu-id="2ba8b-104">Informationen zu Sitzungs Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="2ba8b-104">About Session Configuration Files</span></span>

## <a name="short-description"></a><span data-ttu-id="2ba8b-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2ba8b-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="2ba8b-106">Beschreibt die Sitzungs Konfigurationsdateien, die in einer Sitzungs Konfiguration (auch als "Endpunkt" bezeichnet) zum Definieren der Umgebung von Sitzungen verwendet werden, die die Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-106">Describes session configuration files, which are used in a session configuration (also known as an "endpoint") to define the environment of sessions that use the session configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="2ba8b-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2ba8b-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="2ba8b-108">Eine "Sitzungs Konfigurationsdatei" ist eine Textdatei mit der Dateinamenerweiterung ". PSSC", die eine Hash Tabelle mit Sitzungs Konfigurations Eigenschaften und-Werten enthält.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-108">A "session configuration file" is a text file with a .pssc file name extension that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="2ba8b-109">Sie können eine Sitzungs Konfigurationsdatei verwenden, um die Eigenschaften einer Sitzungs Konfiguration festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-109">You can use a session configuration file to set the properties of a session configuration.</span></span> <span data-ttu-id="2ba8b-110">Dadurch wird die Umgebung von PowerShell-Sitzungen definiert, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-110">Doing so defines the environment of any PowerShell sessions that use that session configuration.</span></span>

<span data-ttu-id="2ba8b-111">Sitzungs Konfigurationsdateien vereinfachen die Erstellung benutzerdefinierter Sitzungs Konfigurationen, ohne komplexe c#-Assemblys oder-Skripts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-111">Session configuration files make it easy to create custom session configurations without using complex C# assemblies or scripts.</span></span>

<span data-ttu-id="2ba8b-112">Eine "Sitzungs Konfiguration" oder "Endpunkt" ist eine Sammlung von Einstellungen für den lokalen Computer, die bestimmen, wie Benutzersitzungen auf dem Computer erstellen können. welche Befehle können Benutzer in diesen Sitzungen ausführen? und ob die Sitzung als privilegiertes virtuelles Konto ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-112">A "session configuration" or "endpoint" is a collection of local computer settings that determine such things as which users can create sessions on the computer; which commands users can run in those sessions; and whether the session should run as a privileged virtual account.</span></span> <span data-ttu-id="2ba8b-113">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="2ba8b-113">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

<span data-ttu-id="2ba8b-114">Sitzungs Konfigurationen wurden in Windows PowerShell 2,0 eingeführt, und Sitzungs Konfigurationsdateien wurden in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-114">Session configurations were introduced in Windows PowerShell 2.0, and session configuration files were introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="2ba8b-115">Sie müssen Windows PowerShell 3,0 verwenden, um eine Sitzungs Konfigurationsdatei in eine Sitzungs Konfiguration einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-115">You must use Windows PowerShell 3.0 to include a session configuration file in a session configuration.</span></span> <span data-ttu-id="2ba8b-116">Benutzer von Windows PowerShell 2,0 (und höher) sind jedoch von den Einstellungen in der Sitzungs Konfiguration betroffen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-116">However, users of Windows PowerShell 2.0 (and later) are affected by the settings in the session configuration.</span></span>

## <a name="creating-custom-sessions"></a><span data-ttu-id="2ba8b-117">Erstellen von benutzerdefinierten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="2ba8b-117">Creating Custom Sessions</span></span>

<span data-ttu-id="2ba8b-118">Sie können viele Funktionen einer PowerShell-Sitzung anpassen, indem Sie in einer Sitzungs Konfiguration Sitzungs Eigenschaften angeben.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-118">You can customize many features of a PowerShell session by specifying session properties in a session configuration.</span></span> <span data-ttu-id="2ba8b-119">Sie können eine Sitzung anpassen, indem Sie ein c#-Programm schreiben, das einen benutzerdefinierten Runspace definiert, oder Sie können eine Sitzungs Konfigurationsdatei verwenden, um die Eigenschaften von Sitzungen zu definieren, die mit der Sitzungs Konfiguration erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-119">You can customize a session by writing a C# program that defines a custom runspace, or you can use a session configuration file to define the properties of sessions created by using the session configuration.</span></span> <span data-ttu-id="2ba8b-120">Als allgemeine Regel ist es einfacher, die Sitzungs Konfigurationsdatei zu verwenden, als ein c#-Programm zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-120">As a general rule, it is easier to use the session configuration file than to write a C# program.</span></span>

<span data-ttu-id="2ba8b-121">Sie können eine Sitzungs Konfigurationsdatei verwenden, um Elemente wie z. b. voll funktionsfähige Sitzungen für hochgradig vertrauenswürdige Benutzer zu erstellen. gesperrte Sitzungen, die minimalen Zugriff zulassen bestimmte Sitzungen, die nur die für diese Aufgaben erforderlichen Module enthalten. und Sitzungen, in denen nicht privilegierte Benutzer nur bestimmte Befehle als privilegiertes Konto ausführen können.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-121">You can use a session configuration file to create items such as fully-functioning sessions for highly trusted users; locked-down sessions that allow minimal access; sessions designed for particular and that contain only the modules required for those tasks; and sessions where unprivileged users can only run specific commands as a privileged account.</span></span>

<span data-ttu-id="2ba8b-122">Darüber hinaus können Sie steuern, ob Benutzer der Sitzung PowerShell-Sprachelemente wie Skriptblöcke verwenden können oder ob Sie nur Befehle ausführen dürfen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-122">In addition to that, you can manage whether users of the session can use PowerShell language elements such as script blocks, or whether they can only run commands.</span></span> <span data-ttu-id="2ba8b-123">Sie können die Version von PowerShell-Benutzern verwalten, die in der Sitzung ausgeführt werden können. Verwalten der Module, die in die Sitzung importiert werden. und verwalten, welche Cmdlets, Funktionen und Aliase Sitzungs Benutzer ausführen können.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-123">You can manage the version of PowerShell users can run in the session; manage which modules are imported into the session; and manage which cmdlets, functions, and aliases session users can run.</span></span> <span data-ttu-id="2ba8b-124">Wenn Sie das Feld roledefinitions verwenden, können Sie Benutzern basierend auf der Gruppenmitgliedschaft unterschiedliche Funktionen in der Sitzung zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-124">When using the RoleDefinitions field, you can give users different capabilities in the session based on group membership.</span></span>

<span data-ttu-id="2ba8b-125">Weitere Informationen zu roledefinitions und zum Definieren dieses Werts finden Sie im Hilfethema für das Cmdlet "New-PSRoleCapabilityFile".</span><span class="sxs-lookup"><span data-stu-id="2ba8b-125">For more information about RoleDefinitions and how to define this Value, see the help topic for the New-PSRoleCapabilityFile Cmdlet.</span></span>

## <a name="creating-a-session-configuration-file"></a><span data-ttu-id="2ba8b-126">Erstellen einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2ba8b-126">Creating a Session Configuration File</span></span>

<span data-ttu-id="2ba8b-127">Die einfachste Möglichkeit zum Erstellen einer Sitzungs Konfigurationsdatei ist die Verwendung des New-PSSessionConfigurationFile-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-127">The easiest way to create a session configuration file is by using the New-PSSessionConfigurationFile cmdlet.</span></span> <span data-ttu-id="2ba8b-128">Mit diesem Cmdlet wird eine Datei generiert, die die richtige Syntax und das richtige Format verwendet, sodass viele der Konfigurationsdatei-Eigenschaftswerte automatisch überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-128">This cmdlet generates a file that uses the correct syntax and format, and that automatically verifies many of the configuration file property values.</span></span>

<span data-ttu-id="2ba8b-129">Ausführliche Beschreibungen der Eigenschaften, die Sie in einer Sitzungs Konfigurationsdatei festlegen können, finden Sie im Hilfethema für das Cmdlet "New-PSSessionConfigurationFile".</span><span class="sxs-lookup"><span data-stu-id="2ba8b-129">For detailed descriptions of the properties that you can set in a session configuration file, see the help topic for the New-PSSessionConfigurationFile cmdlet.</span></span>

<span data-ttu-id="2ba8b-130">Der folgende Befehl erstellt eine Sitzungs Konfigurationsdatei, in der die Standardwerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-130">The following command creates a session configuration file that uses the default values.</span></span> <span data-ttu-id="2ba8b-131">In der resultierenden Konfigurationsdatei werden nur die Standardwerte verwendet, da keine anderen Parameter als der path-Parameter (der den Dateipfad angibt) enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="2ba8b-131">The resulting configuration file uses only the default values because no parameters other than the Path parameter (which specifies the file path) are included:</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Defaults.pssc
```

<span data-ttu-id="2ba8b-132">Verwenden Sie den folgenden Befehl, um die neue Konfigurationsdatei im Standardtext-Editor anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="2ba8b-132">To view the new configuration file in your default text editor, use the following command:</span></span>

```powershell
Invoke-Item -Path .\Defaults.pssc
```

<span data-ttu-id="2ba8b-133">Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, in denen Benutzer Befehle ausführen, aber keine anderen Elemente der PowerShell-Sprache verwenden können, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2ba8b-133">To create a session configuration for sessions in which user can run commands, but not use other elements of the PowerShell language, type:</span></span>

```powershell
New-PSSessionConfigurationFile -LanguageMode NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="2ba8b-134">Im vorangehenden Befehl wird durch das Festlegen des languagemode-Parameters auf nolanguage verhindert, dass Benutzeraktionen wie das Schreiben oder Ausführen von Skripts oder Variablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-134">In the preceding command, setting the LanguageMode parameter to NoLanguage prevents users from doing such things as writing or running scripts, or using variables.</span></span>

<span data-ttu-id="2ba8b-135">Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, in denen Benutzer nur Get-Cmdlets verwenden können, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2ba8b-135">To create a session configuration for sessions in which users can use only Get cmdlets, type:</span></span>

```powershell
New-PSSessionConfigurationFile -VisibleCmdlets Get-*
-Path .\GetSessions.pssc
```

<span data-ttu-id="2ba8b-136">Im vorhergehenden Beispiel schränkt das Festlegen des visiblecmdlets-Parameters auf "Get-\*" Benutzer auf Cmdlets ein, deren Namen mit dem Zeichen folgen Wert "Get-" beginnen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-136">In the preceding example, setting the VisibleCmdlets parameter to Get-\* limits users to cmdlets that have names that start with the string value "Get-".</span></span>

<span data-ttu-id="2ba8b-137">Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, die unter einem privilegierten virtuellen Konto ausgeführt werden, anstelle der Anmelde Informationen des Benutzers, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2ba8b-137">To create a session configuration for sessions that run under a privileged virtual account instead of the user's credentials, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RunAsVirtualAccount
-Path .\VirtualAccount.pssc
```

<span data-ttu-id="2ba8b-138">Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, in denen die für den Benutzer sichtbaren Befehle in der Datei mit den Rollen Funktionen angegeben sind, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2ba8b-138">To create a session configuration for sessions in which the commands visible to the user are specified in a role capabilities file, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RoleDefinitions
@{ 'CONTOSO\User' = @{ RoleCapabilities = 'Maintenance' }}
-Path .\Maintenance.pssc
```

### <a name="using-a-session-configuration-file"></a><span data-ttu-id="2ba8b-139">Verwenden einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2ba8b-139">Using a Session Configuration File</span></span>

<span data-ttu-id="2ba8b-140">Sie können eine Sitzungs Konfigurationsdatei einschließen, wenn Sie eine Sitzungs Konfiguration erstellen oder hinzufügen. Sie können der Sitzungs Konfiguration zu einem späteren Zeitpunkt eine Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-140">You can include a session configuration file when you create a session configuration or add you can add a file to the session configuration at a later time.</span></span>

<span data-ttu-id="2ba8b-141">Verwenden Sie den path-Parameter des Register-PSSessionConfiguration-Cmdlets, um beim Erstellen einer Sitzungs Konfiguration eine Sitzungs Konfigurationsdatei einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-141">To include a session configuration file when creating a session configuration, use the Path parameter of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="2ba8b-142">Der folgende Befehl verwendet z. b. die Datei nolanguage. PSSC, wenn eine nolanguage-Sitzungs Konfiguration erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-142">For example, the following command uses the NoLanguage.pssc file when it creates a NoLanguage session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="2ba8b-143">Wenn eine neue nolanguage-Sitzung gestartet wird, haben Benutzer nur Zugriff auf PowerShell-Befehle.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-143">When a new NoLanguage session starts, users will only have access to PowerShell commands.</span></span>

<span data-ttu-id="2ba8b-144">Zum Hinzufügen einer Sitzungs Konfigurationsdatei zu einer vorhandenen Sitzungs Konfiguration verwenden Sie das Cmdlet Set-PSSessionConfiguration und den path-Parameter.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-144">To add a session configuration file to an existing session configuration, use the Set-PSSessionConfiguration cmdlet and the Path parameter.</span></span> <span data-ttu-id="2ba8b-145">Dies wirkt sich auf alle neuen Sitzungen aus, die mit der angegebenen Sitzungs Konfiguration erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-145">This affects any new sessions created with the specified session configuration.</span></span> <span data-ttu-id="2ba8b-146">Beachten Sie, dass das Cmdlet "Set-PSSessionConfiguration" die Sitzung selbst ändert und die Sitzungs Konfigurationsdatei nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-146">Note that the Set-PSSessionConfiguration cmdlet changes the session itself and does not modify the session configuration file.</span></span>

<span data-ttu-id="2ba8b-147">Beispielsweise wird mit dem folgenden Befehl die Datei nolanguage. PSSC der lockeddown-Sitzungs Konfiguration hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-147">For example, the following command adds the NoLanguage.pssc file to the LockedDown session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -Name LockedDown
-Path .\NoLanguage.pssc
```

<span data-ttu-id="2ba8b-148">Wenn Benutzer die lockeddown-Sitzungs Konfiguration verwenden, um eine Sitzung zu erstellen, können Sie Cmdlets ausführen, aber Sie können keine Variablen erstellen oder verwenden, Werte zuweisen oder andere PowerShell-Sprachelemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-148">When users use the LockedDown session configuration to create a session, they will be able to run cmdlets but they will not be able to create or use variables, assign values, or use other PowerShell language elements.</span></span>

<span data-ttu-id="2ba8b-149">Der folgende Befehl verwendet das Cmdlet "New-PSSession", um eine Sitzung auf dem Computer zu erstellen SRV01, die die lockeddown-Sitzungs Konfiguration verwendet und einen Objekt Verweis auf die Sitzung in der $s Variablen speichert.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-149">The following command uses the New-PSSession cmdlet to create a session on the computer Srv01 that uses the LockedDown session configuration, saving an object reference to the session in the $s variable.</span></span> <span data-ttu-id="2ba8b-150">Die Zugriffs Steuerungs Liste (Access Control List, ACL) der Sitzungs Konfiguration bestimmt, wer zum Erstellen einer Sitzung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-150">The ACL (access control list) of the session configuration determines who can use it to create a session.</span></span>

```powershell
$s = New-PSSession -ComputerName Srv01
-ConfigurationName LockedDown
```

<span data-ttu-id="2ba8b-151">Da die nolanguage-Einschränkungen der lockeddown-Sitzungs Konfiguration hinzugefügt wurden, können Benutzer in lockeddown-Sitzungen nur PowerShell-Befehle und-Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-151">Because the NoLanguage constraints were added to the LockedDown session configuration, users in LockedDown sessions will only be able to run PowerShell commands and cmdlets.</span></span> <span data-ttu-id="2ba8b-152">Beispielsweise verwenden die folgenden beiden Befehle das Invoke-Command-Cmdlet, um Befehle in der Sitzung auszuführen, auf die in der $s-Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-152">For example, the following two commands use the Invoke-Command cmdlet to run commands in the session referenced in the $s variable.</span></span> <span data-ttu-id="2ba8b-153">Der erste Befehl, der das Get-UICulture-Cmdlet ausführt und keine Variablen verwendet, ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-153">The first command, which runs the Get-UICulture cmdlet and does not use any variables, succeeds.</span></span> <span data-ttu-id="2ba8b-154">Der zweite Befehl, der den Wert der $PSUICulture Variable abruft, schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-154">The second command, which gets the value of the $PSUICulture variable, fails.</span></span>

```
Invoke-Command -Session $s {Get-UICulture}
en-US

Invoke-Command -Session $s {$PSUICulture}
The syntax is not supported by this runspace. This might be
because it is in no-language mode.
+ CategoryInfo          : ParserError: ($PSUICulture:String) [],
ParseException
+ FullyQualifiedErrorId : ScriptsNotAllowed
```

## <a name="editing-a-session-configuration-file"></a><span data-ttu-id="2ba8b-155">Bearbeiten einer Sitzungskonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2ba8b-155">Editing a Session Configuration File</span></span>

<span data-ttu-id="2ba8b-156">Alle Einstellungen in einer Sitzungs Konfiguration mit Ausnahme von runasvirtualaccount und runasvirtualaccountgroups können durch Bearbeiten der Sitzungs Konfigurationsdatei geändert werden, die von der Sitzungs Konfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-156">All settings in a session configuration except for RunAsVirtualAccount and RunAsVirtualAccountGroups can be modified by editing the session configuration file used by the session configuration.</span></span> <span data-ttu-id="2ba8b-157">Zu diesem Zweck suchen Sie zunächst die aktive Kopie der Sitzungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-157">To do this, begin by locating the active copy of the session configuration file.</span></span>

<span data-ttu-id="2ba8b-158">Wenn Sie eine Sitzungs Konfigurationsdatei in einer Sitzungs Konfiguration verwenden, wird von PowerShell eine aktive Kopie der Sitzungs Konfigurationsdatei erstellt und im \$ Verzeichnis "PSHome \\ sessionconfig" auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-158">When you use a session configuration file in a session configuration, PowerShell creates an active copy of the session configuration file and stores it in the \$pshome\\SessionConfig directory on the local computer.</span></span>

<span data-ttu-id="2ba8b-159">Der Speicherort der aktiven Kopie einer Sitzungs Konfigurationsdatei wird in der configfilepath-Eigenschaft des Sitzungs Konfigurations Objekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-159">The location of the active copy of a session configuration file is stored in the ConfigFilePath property of the session configuration object.</span></span>

<span data-ttu-id="2ba8b-160">Mit dem folgenden Befehl wird der Speicherort der Sitzungs Konfigurationsdatei für die nolanguage-Sitzungs Konfiguration abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-160">The following command gets the location of the session configuration file for the NoLanguage session configuration.</span></span>

```powershell
(Get-PSSessionConfiguration -Name NoLanguage).ConfigFilePath
```

<span data-ttu-id="2ba8b-161">Dieser Befehl gibt einen Dateipfad zurück, der dem folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="2ba8b-161">That command returns a file path similar to the following:</span></span>

```
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="2ba8b-162">Sie können die PSSC-Datei in einem beliebigen Text-Editor bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-162">You can edit the .pssc file in any text editor.</span></span> <span data-ttu-id="2ba8b-163">Nachdem die Datei gespeichert wurde, wird Sie von allen neuen Sitzungen verwendet, die die Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-163">After the file is saved it will be employed by any new sessions that use the session configuration.</span></span>

<span data-ttu-id="2ba8b-164">Wenn Sie die runasvirtualaccount-oder runasvirtualaccountgroups-Einstellungen ändern müssen, müssen Sie die Registrierung der Sitzungs Konfiguration aufheben und eine Sitzungs Konfigurationsdatei erneut registrieren, die die bearbeiteten Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-164">If you need to modify the RunAsVirtualAccount or the RunAsVirtualAccountGroups settings, you must un-register the session configuration and re-register a session configuration file that includes the edited values.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="2ba8b-165">Testen einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2ba8b-165">Testing a Session Configuration File</span></span>

<span data-ttu-id="2ba8b-166">Verwenden Sie das Cmdlet "Test-PSSessionConfigurationFile", um manuell bearbeiteten Sitzungs Konfigurationsdateien zu testen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-166">Use the Test-PSSessionConfigurationFile cmdlet to test manually edited session configuration files.</span></span> <span data-ttu-id="2ba8b-167">Das ist wichtig: Wenn die Datei Syntax und die Werte nicht gültig sind, können Benutzer die Sitzungs Konfiguration nicht verwenden, um eine Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-167">That's important: if the file syntax and values are not valid users will not be able to use the session configuration to create a session.</span></span>

<span data-ttu-id="2ba8b-168">Der folgende Befehl testet z. b. die aktive Sitzungs Konfigurationsdatei der nolanguage-Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-168">For example, the following command tests the active session configuration file of the NoLanguage session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path C:\WINDOWS\System32\
WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="2ba8b-169">Wenn die Syntax und die Werte in der Konfigurationsdatei gültig sind Test-PSSessionConfigurationFile gibt true zurück.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-169">If the syntax and values in the configuration file are valid Test-PSSessionConfigurationFile returns True.</span></span> <span data-ttu-id="2ba8b-170">Wenn die Syntax und die Werte nicht gültig sind, gibt das Cmdlet false zurück.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-170">If the syntax and values are not valid then the cmdlet returns False.</span></span>

<span data-ttu-id="2ba8b-171">Mit Test-PSSessionConfigurationFile können Sie alle Sitzungs Konfigurationsdateien testen, einschließlich Dateien, die vom New-PSSessionConfiguration-Cmdlet erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-171">You can use Test-PSSessionConfigurationFile to test any session configuration file, including files that the New-PSSessionConfiguration cmdlet creates.</span></span> <span data-ttu-id="2ba8b-172">Weitere Informationen finden Sie im Hilfethema für das Cmdlet "Test-PSSessionConfigurationFile".</span><span class="sxs-lookup"><span data-stu-id="2ba8b-172">For more information, see the help topic for the Test-PSSessionConfigurationFile cmdlet.</span></span>

## <a name="removing-a-session-configuration-file"></a><span data-ttu-id="2ba8b-173">Entfernen einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="2ba8b-173">Removing a Session Configuration File</span></span>

<span data-ttu-id="2ba8b-174">Eine Sitzungs Konfigurationsdatei kann nicht aus einer Sitzungs Konfiguration entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-174">You cannot remove a session configuration file from a session configuration.</span></span>
<span data-ttu-id="2ba8b-175">Allerdings können Sie die Datei durch eine neue Datei ersetzen, in der die Standardeinstellungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-175">However, you can replace the file with a new file that uses the default settings.</span></span> <span data-ttu-id="2ba8b-176">Dadurch werden die von der ursprünglichen Konfigurationsdatei verwendeten Einstellungen effektiv abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-176">This effectively cancels the settings used by the original configuration file.</span></span>

<span data-ttu-id="2ba8b-177">Zum Ersetzen einer Sitzungs Konfigurationsdatei erstellen Sie eine neue Sitzungs Konfigurationsdatei, in der die Standardeinstellungen verwendet werden. verwenden Sie dann das Cmdlet "Set-PSSessionConfiguration", um die benutzerdefinierte Sitzungs Konfigurationsdatei durch die neue Datei zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-177">To replace a session configuration file, create a new session configuration file that uses the default settings, then use the Set-PSSessionConfiguration cmdlet to replace the custom session configuration file with the new file.</span></span>

<span data-ttu-id="2ba8b-178">Die folgenden Befehle erstellen z. b. eine standardmäßige Sitzungs Konfigurationsdatei und ersetzen dann die aktive Sitzungs Konfigurationsdatei in der nolanguage-Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-178">For example, the following commands create a Default session configuration file and then replace the active session configuration file in the NoLanguage session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Default.pssc
Set-PSSessionConfiguration -Name NoLanguage
-Path .\Default.pssc
```

<span data-ttu-id="2ba8b-179">Wenn diese Befehle fertiggestellt werden, bietet die nolanguage-Sitzungs Konfiguration tatsächlich vollständige Sprachunterstützung (Standardeinstellung) für alle Sitzungen, die mit dieser Sitzungs Konfiguration erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-179">When these commands finish, the NoLanguage session configuration will actually provide full language support (the default setting) for all sessions created with that session configuration.</span></span>

<span data-ttu-id="2ba8b-180">Anzeigen der Eigenschaften einer Sitzungs Konfiguration die Sitzungs Konfigurationsobjekte, die Sitzungs Konfigurationen mithilfe von Sitzungs Konfigurationsdateien darstellen, verfügen über zusätzliche Eigenschaften, die das Auffinden und Analysieren der Sitzungs Konfiguration erleichtern.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-180">Viewing the Properties of a Session Configuration The session configuration objects that represent session configurations using session configuration files have additional properties that make it easy to discover and analyze the session configuration.</span></span> <span data-ttu-id="2ba8b-181">(Beachten Sie, dass der unten gezeigte Typname eine formatierte Sicht Definition enthält.) Sie können die Eigenschaften anzeigen, indem Sie das Cmdlet "Get-PSSessionConfiguration" ausführen und die zurückgegebenen Daten an das Get-Member-Cmdlet weiterleiten:</span><span class="sxs-lookup"><span data-stu-id="2ba8b-181">(Note that the type name shown below includes a formatted view definition.) You can view the properties by running the Get-PSSessionConfiguration cmdlet and piping the returned data to the Get-Member cmdlet:</span></span>

```powershell
Get-PSSessionConfiguration NoLanguage | Get-Member
```

```output
TypeName: Microsoft.PowerShell.Commands.PSSessionConfigurationCommands
#PSSessionConfiguration

Name                          MemberType     Definition
----                          ----------     ----------
Equals                        Method         bool Equals(System.O...
GetHashCode                   Method         int GetHashCode()
GetType                       Method         type GetType()
ToString                      Method         string ToString()
Architecture                  NoteProperty   System.String Archit...
Author                        NoteProperty   System.String Author...
AutoRestart                   NoteProperty   System.String AutoRe...
Capability                    NoteProperty   System.Object[] Capa...
CompanyName                   NoteProperty   System.String Compan...
configfilepath                NoteProperty   System.String config...
Copyright                     NoteProperty   System.String Copyri...
Enabled                       NoteProperty   System.String Enable...
ExactMatch                    NoteProperty   System.String ExactM...
ExecutionPolicy               NoteProperty   System.String Execut...
Filename                      NoteProperty   System.String Filena...
GUID                          NoteProperty   System.String GUID=0...
ProcessIdleTimeoutSec         NoteProperty   System.String Proces...
IdleTimeoutms                 NoteProperty   System.String IdleTi...
lang                          NoteProperty   System.String lang=e...
LanguageMode                  NoteProperty   System.String Langua...
MaxConcurrentCommandsPerShell NoteProperty   System.String MaxCon...
MaxConcurrentUsers            NoteProperty   System.String MaxCon...
MaxIdleTimeoutms              NoteProperty   System.String MaxIdl...
MaxMemoryPerShellMB           NoteProperty   System.String MaxMem...
MaxProcessesPerShell          NoteProperty   System.String MaxPro...
MaxShells                     NoteProperty   System.String MaxShells
MaxShellsPerUser              NoteProperty   System.String MaxShe...
Name                          NoteProperty   System.String Name=N...
PSVersion                     NoteProperty   System.String PSVersion
ResourceUri                   NoteProperty   System.String Resour...
RunAsPassword                 NoteProperty   System.String RunAsP...
RunAsUser                     NoteProperty   System.String RunAsUser
SchemaVersion                 NoteProperty   System.String Schema...
SDKVersion                    NoteProperty   System.String SDKVer...
OutputBufferingMode           NoteProperty   System.String Output...
SessionType                   NoteProperty   System.String Sessio...
UseSharedProcess              NoteProperty   System.String UseSha...
SupportsOptions               NoteProperty   System.String Suppor...
xmlns                         NoteProperty   System.String xmlns=...
XmlRenderingType              NoteProperty   System.String XmlRen...
Permission                    ScriptProperty System.Object Permis...
```

<span data-ttu-id="2ba8b-182">Diese Eigenschaften erleichtern das Suchen nach bestimmten Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-182">These properties make it easy to search for specific session configurations.</span></span>
<span data-ttu-id="2ba8b-183">Sie können z. b. die ExecutionPolicy-Eigenschaft verwenden, um eine Sitzungs Konfiguration zu suchen, die Sitzungen mit der RemoteSigned-Ausführungs Richtlinie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-183">For example, you can use the ExecutionPolicy property to find a session configuration that supports sessions with the RemoteSigned execution policy.</span></span>
<span data-ttu-id="2ba8b-184">Beachten Sie Folgendes: da die ExecutionPolicy-Eigenschaft nur für Sitzungen vorhanden ist, die Sitzungs Konfigurationsdateien verwenden, gibt der Befehl möglicherweise nicht alle qualifizierenden Sitzungs Konfigurationen zurück.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-184">Note that, because the ExecutionPolicy property exists only on sessions that use session configuration files, the command might not return all qualifying session configurations.</span></span>

```powershell
Get-PSSessionConfiguration |
where {$_.ExecutionPolicy -eq "RemoteSigned"}
```

<span data-ttu-id="2ba8b-185">Mit dem folgenden Befehl werden Sitzungs Konfigurationen abgerufen, in denen der RunAsUser der Exchange-Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-185">The following command gets session configurations in which the RunAsUser is the Exchange administrator.</span></span>

```powershell
 Get-PSSessionConfiguration |
where {$_.RunAsUser -eq "Exchange01\Admin01"}
```

<span data-ttu-id="2ba8b-186">Verwenden Sie das Cmdlet "Get-PSSessionCapability", um Informationen zu den einer Konfiguration zugeordneten Rollen Definitionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-186">To view information about the role definitions associated with a configuration use the Get-PSSessionCapability cmdlet.</span></span> <span data-ttu-id="2ba8b-187">Mit diesem Cmdlet können Sie die Befehle und die Umgebung ermitteln, die bestimmten Benutzern in bestimmten Endpunkten zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-187">This cmdlet enables you to determine the commands and environment available to specific users in specific endpoints.</span></span>

## <a name="notes"></a><span data-ttu-id="2ba8b-188">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2ba8b-188">NOTES</span></span>

<span data-ttu-id="2ba8b-189">Sitzungs Konfigurationen unterstützen auch einen Sitzungstyp, der als "leere" Sitzung bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-189">Session configurations also support a type of session known as an "empty" session.</span></span> <span data-ttu-id="2ba8b-190">Mit einem leeren Sitzungstyp können Sie benutzerdefinierte Sitzungen mit ausgewählten Befehlen erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-190">An Empty session type enables you to create custom sessions with selected commands.</span></span> <span data-ttu-id="2ba8b-191">Wenn Sie einer leeren Sitzung keine Module, Funktionen oder Skripts hinzufügen, ist die Sitzung auf Ausdrücke beschränkt und kann nicht praktisch verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-191">If you do not add modules, functions, or scripts to an empty session, the session is limited to expressions and might not be of any practical use.</span></span> <span data-ttu-id="2ba8b-192">Die SessionType-Eigenschaft gibt Aufschluss darüber, ob Sie mit einer leeren Sitzung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2ba8b-192">The SessionType property tells you whether or not you are working with an empty session.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ba8b-193">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="2ba8b-193">SEE ALSO</span></span>

[<span data-ttu-id="2ba8b-194">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="2ba8b-194">about_Session_Configurations</span></span>](about_Session_Configurations.md)

[<span data-ttu-id="2ba8b-195">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="2ba8b-195">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="2ba8b-196">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ba8b-196">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="2ba8b-197">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ba8b-197">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="2ba8b-198">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ba8b-198">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="2ba8b-199">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2ba8b-199">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="2ba8b-200">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ba8b-200">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="2ba8b-201">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ba8b-201">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="2ba8b-202">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2ba8b-202">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="2ba8b-203">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ba8b-203">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

[<span data-ttu-id="2ba8b-204">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="2ba8b-204">Get-PSSessionCapability</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionCapability)

[<span data-ttu-id="2ba8b-205">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="2ba8b-205">New-PSRoleCapabilityFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSRoleCapabilityFile)
