---
description: Beschreibt die Sitzungs Konfigurationsdateien, die in einer Sitzungs Konfiguration (auch als Endpunkt bezeichnet) zum Definieren der Umgebung von Sitzungen verwendet werden, die die Sitzungs Konfiguration verwenden.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configuration_files?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configuration_Files
ms.openlocfilehash: 1ed87e95b2ce823b5a887546545e1158630eabfb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601931"
---
# <a name="about-session-configuration-files"></a><span data-ttu-id="13638-103">Informationen zu Sitzungs Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="13638-103">About Session Configuration Files</span></span>

## <a name="short-description"></a><span data-ttu-id="13638-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="13638-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="13638-105">Beschreibt die Sitzungs Konfigurationsdateien, die in einer Sitzungs Konfiguration (auch als "Endpunkt" bezeichnet) zum Definieren der Umgebung von Sitzungen verwendet werden, die die Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="13638-105">Describes session configuration files, which are used in a session configuration (also known as an "endpoint") to define the environment of sessions that use the session configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="13638-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="13638-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="13638-107">Eine "Sitzungs Konfigurationsdatei" ist eine Textdatei mit der Dateinamenerweiterung ". PSSC", die eine Hash Tabelle mit Sitzungs Konfigurations Eigenschaften und-Werten enthält.</span><span class="sxs-lookup"><span data-stu-id="13638-107">A "session configuration file" is a text file with a .pssc file name extension that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="13638-108">Sie können eine Sitzungs Konfigurationsdatei verwenden, um die Eigenschaften einer Sitzungs Konfiguration festzulegen.</span><span class="sxs-lookup"><span data-stu-id="13638-108">You can use a session configuration file to set the properties of a session configuration.</span></span> <span data-ttu-id="13638-109">Dadurch wird die Umgebung von PowerShell-Sitzungen definiert, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="13638-109">Doing so defines the environment of any PowerShell sessions that use that session configuration.</span></span>

<span data-ttu-id="13638-110">Sitzungs Konfigurationsdateien vereinfachen die Erstellung benutzerdefinierter Sitzungs Konfigurationen, ohne komplexe c#-Assemblys oder-Skripts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="13638-110">Session configuration files make it easy to create custom session configurations without using complex C# assemblies or scripts.</span></span>

<span data-ttu-id="13638-111">Eine "Sitzungs Konfiguration" oder "Endpunkt" ist eine Sammlung von Einstellungen für den lokalen Computer, die bestimmen, wie Benutzersitzungen auf dem Computer erstellen können. welche Befehle können Benutzer in diesen Sitzungen ausführen? und ob die Sitzung als privilegiertes virtuelles Konto ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="13638-111">A "session configuration" or "endpoint" is a collection of local computer settings that determine such things as which users can create sessions on the computer; which commands users can run in those sessions; and whether the session should run as a privileged virtual account.</span></span> <span data-ttu-id="13638-112">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="13638-112">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

<span data-ttu-id="13638-113">Sitzungs Konfigurationen wurden in Windows PowerShell 2,0 eingeführt, und Sitzungs Konfigurationsdateien wurden in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="13638-113">Session configurations were introduced in Windows PowerShell 2.0, and session configuration files were introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="13638-114">Sie müssen Windows PowerShell 3,0 verwenden, um eine Sitzungs Konfigurationsdatei in eine Sitzungs Konfiguration einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="13638-114">You must use Windows PowerShell 3.0 to include a session configuration file in a session configuration.</span></span> <span data-ttu-id="13638-115">Benutzer von Windows PowerShell 2,0 (und höher) sind jedoch von den Einstellungen in der Sitzungs Konfiguration betroffen.</span><span class="sxs-lookup"><span data-stu-id="13638-115">However, users of Windows PowerShell 2.0 (and later) are affected by the settings in the session configuration.</span></span>

## <a name="creating-custom-sessions"></a><span data-ttu-id="13638-116">Erstellen von benutzerdefinierten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="13638-116">Creating Custom Sessions</span></span>

<span data-ttu-id="13638-117">Sie können viele Funktionen einer PowerShell-Sitzung anpassen, indem Sie in einer Sitzungs Konfiguration Sitzungs Eigenschaften angeben.</span><span class="sxs-lookup"><span data-stu-id="13638-117">You can customize many features of a PowerShell session by specifying session properties in a session configuration.</span></span> <span data-ttu-id="13638-118">Sie können eine Sitzung anpassen, indem Sie ein c#-Programm schreiben, das einen benutzerdefinierten Runspace definiert, oder Sie können eine Sitzungs Konfigurationsdatei verwenden, um die Eigenschaften von Sitzungen zu definieren, die mit der Sitzungs Konfiguration erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="13638-118">You can customize a session by writing a C# program that defines a custom runspace, or you can use a session configuration file to define the properties of sessions created by using the session configuration.</span></span> <span data-ttu-id="13638-119">Als allgemeine Regel ist es einfacher, die Sitzungs Konfigurationsdatei zu verwenden, als ein c#-Programm zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="13638-119">As a general rule, it is easier to use the session configuration file than to write a C# program.</span></span>

<span data-ttu-id="13638-120">Sie können eine Sitzungs Konfigurationsdatei verwenden, um Elemente wie z. b. voll funktionsfähige Sitzungen für hochgradig vertrauenswürdige Benutzer zu erstellen. gesperrte Sitzungen, die minimalen Zugriff zulassen bestimmte Sitzungen, die nur die für diese Aufgaben erforderlichen Module enthalten. und Sitzungen, in denen nicht privilegierte Benutzer nur bestimmte Befehle als privilegiertes Konto ausführen können.</span><span class="sxs-lookup"><span data-stu-id="13638-120">You can use a session configuration file to create items such as fully-functioning sessions for highly trusted users; locked-down sessions that allow minimal access; sessions designed for particular and that contain only the modules required for those tasks; and sessions where unprivileged users can only run specific commands as a privileged account.</span></span>

<span data-ttu-id="13638-121">Darüber hinaus können Sie steuern, ob Benutzer der Sitzung PowerShell-Sprachelemente wie Skriptblöcke verwenden können oder ob Sie nur Befehle ausführen dürfen.</span><span class="sxs-lookup"><span data-stu-id="13638-121">In addition to that, you can manage whether users of the session can use PowerShell language elements such as script blocks, or whether they can only run commands.</span></span> <span data-ttu-id="13638-122">Sie können die Version von PowerShell-Benutzern verwalten, die in der Sitzung ausgeführt werden können. Verwalten der Module, die in die Sitzung importiert werden. und verwalten, welche Cmdlets, Funktionen und Aliase Sitzungs Benutzer ausführen können.</span><span class="sxs-lookup"><span data-stu-id="13638-122">You can manage the version of PowerShell users can run in the session; manage which modules are imported into the session; and manage which cmdlets, functions, and aliases session users can run.</span></span> <span data-ttu-id="13638-123">Wenn Sie das Feld roledefinitions verwenden, können Sie Benutzern basierend auf der Gruppenmitgliedschaft unterschiedliche Funktionen in der Sitzung zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="13638-123">When using the RoleDefinitions field, you can give users different capabilities in the session based on group membership.</span></span>

<span data-ttu-id="13638-124">Weitere Informationen zu roledefinitions und zum Definieren dieses Werts finden Sie im Hilfethema für das Cmdlet "New-PSRoleCapabilityFile".</span><span class="sxs-lookup"><span data-stu-id="13638-124">For more information about RoleDefinitions and how to define this Value, see the help topic for the New-PSRoleCapabilityFile Cmdlet.</span></span>

## <a name="creating-a-session-configuration-file"></a><span data-ttu-id="13638-125">Erstellen einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="13638-125">Creating a Session Configuration File</span></span>

<span data-ttu-id="13638-126">Die einfachste Möglichkeit zum Erstellen einer Sitzungs Konfigurationsdatei ist die Verwendung des New-PSSessionConfigurationFile-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="13638-126">The easiest way to create a session configuration file is by using the New-PSSessionConfigurationFile cmdlet.</span></span> <span data-ttu-id="13638-127">Mit diesem Cmdlet wird eine Datei generiert, die die richtige Syntax und das richtige Format verwendet, sodass viele der Konfigurationsdatei-Eigenschaftswerte automatisch überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="13638-127">This cmdlet generates a file that uses the correct syntax and format, and that automatically verifies many of the configuration file property values.</span></span>

<span data-ttu-id="13638-128">Ausführliche Beschreibungen der Eigenschaften, die Sie in einer Sitzungs Konfigurationsdatei festlegen können, finden Sie im Hilfethema für das Cmdlet "New-PSSessionConfigurationFile".</span><span class="sxs-lookup"><span data-stu-id="13638-128">For detailed descriptions of the properties that you can set in a session configuration file, see the help topic for the New-PSSessionConfigurationFile cmdlet.</span></span>

<span data-ttu-id="13638-129">Der folgende Befehl erstellt eine Sitzungs Konfigurationsdatei, in der die Standardwerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13638-129">The following command creates a session configuration file that uses the default values.</span></span> <span data-ttu-id="13638-130">In der resultierenden Konfigurationsdatei werden nur die Standardwerte verwendet, da keine anderen Parameter als der path-Parameter (der den Dateipfad angibt) enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="13638-130">The resulting configuration file uses only the default values because no parameters other than the Path parameter (which specifies the file path) are included:</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Defaults.pssc
```

<span data-ttu-id="13638-131">Verwenden Sie den folgenden Befehl, um die neue Konfigurationsdatei im Standardtext-Editor anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="13638-131">To view the new configuration file in your default text editor, use the following command:</span></span>

```powershell
Invoke-Item -Path .\Defaults.pssc
```

<span data-ttu-id="13638-132">Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, in denen Benutzer Befehle ausführen, aber keine anderen Elemente der PowerShell-Sprache verwenden können, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="13638-132">To create a session configuration for sessions in which user can run commands, but not use other elements of the PowerShell language, type:</span></span>

```powershell
New-PSSessionConfigurationFile -LanguageMode NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="13638-133">Im vorangehenden Befehl wird durch das Festlegen des languagemode-Parameters auf nolanguage verhindert, dass Benutzeraktionen wie das Schreiben oder Ausführen von Skripts oder Variablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="13638-133">In the preceding command, setting the LanguageMode parameter to NoLanguage prevents users from doing such things as writing or running scripts, or using variables.</span></span>

<span data-ttu-id="13638-134">Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, in denen Benutzer nur Get-Cmdlets verwenden können, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="13638-134">To create a session configuration for sessions in which users can use only Get cmdlets, type:</span></span>

```powershell
New-PSSessionConfigurationFile -VisibleCmdlets Get-*
-Path .\GetSessions.pssc
```

<span data-ttu-id="13638-135">Im vorhergehenden Beispiel schränkt das Festlegen des visiblecmdlets-Parameters auf "Get-\*" Benutzer auf Cmdlets ein, deren Namen mit dem Zeichen folgen Wert "Get-" beginnen.</span><span class="sxs-lookup"><span data-stu-id="13638-135">In the preceding example, setting the VisibleCmdlets parameter to Get-\* limits users to cmdlets that have names that start with the string value "Get-".</span></span>

<span data-ttu-id="13638-136">Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, die unter einem privilegierten virtuellen Konto ausgeführt werden, anstelle der Anmelde Informationen des Benutzers, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="13638-136">To create a session configuration for sessions that run under a privileged virtual account instead of the user's credentials, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RunAsVirtualAccount
-Path .\VirtualAccount.pssc
```

<span data-ttu-id="13638-137">Zum Erstellen einer Sitzungs Konfiguration für Sitzungen, in denen die für den Benutzer sichtbaren Befehle in der Datei mit den Rollen Funktionen angegeben sind, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="13638-137">To create a session configuration for sessions in which the commands visible to the user are specified in a role capabilities file, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RoleDefinitions
@{ 'CONTOSO\User' = @{ RoleCapabilities = 'Maintenance' }}
-Path .\Maintenance.pssc
```

### <a name="using-a-session-configuration-file"></a><span data-ttu-id="13638-138">Verwenden einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="13638-138">Using a Session Configuration File</span></span>

<span data-ttu-id="13638-139">Sie können eine Sitzungs Konfigurationsdatei einschließen, wenn Sie eine Sitzungs Konfiguration erstellen oder hinzufügen. Sie können der Sitzungs Konfiguration zu einem späteren Zeitpunkt eine Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="13638-139">You can include a session configuration file when you create a session configuration or add you can add a file to the session configuration at a later time.</span></span>

<span data-ttu-id="13638-140">Verwenden Sie den path-Parameter des Register-PSSessionConfiguration-Cmdlets, um beim Erstellen einer Sitzungs Konfiguration eine Sitzungs Konfigurationsdatei einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="13638-140">To include a session configuration file when creating a session configuration, use the Path parameter of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="13638-141">Der folgende Befehl verwendet z. b. die Datei nolanguage. PSSC, wenn eine nolanguage-Sitzungs Konfiguration erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="13638-141">For example, the following command uses the NoLanguage.pssc file when it creates a NoLanguage session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="13638-142">Wenn eine neue nolanguage-Sitzung gestartet wird, haben Benutzer nur Zugriff auf PowerShell-Befehle.</span><span class="sxs-lookup"><span data-stu-id="13638-142">When a new NoLanguage session starts, users will only have access to PowerShell commands.</span></span>

<span data-ttu-id="13638-143">Zum Hinzufügen einer Sitzungs Konfigurationsdatei zu einer vorhandenen Sitzungs Konfiguration verwenden Sie das Cmdlet Set-PSSessionConfiguration und den path-Parameter.</span><span class="sxs-lookup"><span data-stu-id="13638-143">To add a session configuration file to an existing session configuration, use the Set-PSSessionConfiguration cmdlet and the Path parameter.</span></span> <span data-ttu-id="13638-144">Dies wirkt sich auf alle neuen Sitzungen aus, die mit der angegebenen Sitzungs Konfiguration erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="13638-144">This affects any new sessions created with the specified session configuration.</span></span> <span data-ttu-id="13638-145">Beachten Sie, dass das Cmdlet "Set-PSSessionConfiguration" die Sitzung selbst ändert und die Sitzungs Konfigurationsdatei nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="13638-145">Note that the Set-PSSessionConfiguration cmdlet changes the session itself and does not modify the session configuration file.</span></span>

<span data-ttu-id="13638-146">Beispielsweise wird mit dem folgenden Befehl die Datei nolanguage. PSSC der lockeddown-Sitzungs Konfiguration hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="13638-146">For example, the following command adds the NoLanguage.pssc file to the LockedDown session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -Name LockedDown
-Path .\NoLanguage.pssc
```

<span data-ttu-id="13638-147">Wenn Benutzer die lockeddown-Sitzungs Konfiguration verwenden, um eine Sitzung zu erstellen, können Sie Cmdlets ausführen, aber Sie können keine Variablen erstellen oder verwenden, Werte zuweisen oder andere PowerShell-Sprachelemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="13638-147">When users use the LockedDown session configuration to create a session, they will be able to run cmdlets but they will not be able to create or use variables, assign values, or use other PowerShell language elements.</span></span>

<span data-ttu-id="13638-148">Der folgende Befehl verwendet das Cmdlet "New-PSSession", um eine Sitzung auf dem Computer zu erstellen SRV01, die die lockeddown-Sitzungs Konfiguration verwendet und einen Objekt Verweis auf die Sitzung in der $s Variablen speichert.</span><span class="sxs-lookup"><span data-stu-id="13638-148">The following command uses the New-PSSession cmdlet to create a session on the computer Srv01 that uses the LockedDown session configuration, saving an object reference to the session in the $s variable.</span></span> <span data-ttu-id="13638-149">Die Zugriffs Steuerungs Liste (Access Control List, ACL) der Sitzungs Konfiguration bestimmt, wer zum Erstellen einer Sitzung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="13638-149">The ACL (access control list) of the session configuration determines who can use it to create a session.</span></span>

```powershell
$s = New-PSSession -ComputerName Srv01
-ConfigurationName LockedDown
```

<span data-ttu-id="13638-150">Da die nolanguage-Einschränkungen der lockeddown-Sitzungs Konfiguration hinzugefügt wurden, können Benutzer in lockeddown-Sitzungen nur PowerShell-Befehle und-Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="13638-150">Because the NoLanguage constraints were added to the LockedDown session configuration, users in LockedDown sessions will only be able to run PowerShell commands and cmdlets.</span></span> <span data-ttu-id="13638-151">Beispielsweise verwenden die folgenden beiden Befehle das Invoke-Command-Cmdlet, um Befehle in der Sitzung auszuführen, auf die in der $s-Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="13638-151">For example, the following two commands use the Invoke-Command cmdlet to run commands in the session referenced in the $s variable.</span></span> <span data-ttu-id="13638-152">Der erste Befehl, der das Get-UICulture-Cmdlet ausführt und keine Variablen verwendet, ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="13638-152">The first command, which runs the Get-UICulture cmdlet and does not use any variables, succeeds.</span></span> <span data-ttu-id="13638-153">Der zweite Befehl, der den Wert der $PSUICulture Variable abruft, schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="13638-153">The second command, which gets the value of the $PSUICulture variable, fails.</span></span>

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

## <a name="editing-a-session-configuration-file"></a><span data-ttu-id="13638-154">Bearbeiten einer Sitzungskonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="13638-154">Editing a Session Configuration File</span></span>

<span data-ttu-id="13638-155">Alle Einstellungen in einer Sitzungs Konfiguration mit Ausnahme von runasvirtualaccount und runasvirtualaccountgroups können durch Bearbeiten der Sitzungs Konfigurationsdatei geändert werden, die von der Sitzungs Konfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13638-155">All settings in a session configuration except for RunAsVirtualAccount and RunAsVirtualAccountGroups can be modified by editing the session configuration file used by the session configuration.</span></span> <span data-ttu-id="13638-156">Zu diesem Zweck suchen Sie zunächst die aktive Kopie der Sitzungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="13638-156">To do this, begin by locating the active copy of the session configuration file.</span></span>

<span data-ttu-id="13638-157">Wenn Sie eine Sitzungs Konfigurationsdatei in einer Sitzungs Konfiguration verwenden, wird von PowerShell eine aktive Kopie der Sitzungs Konfigurationsdatei erstellt und im \$ Verzeichnis "PSHome \\ sessionconfig" auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="13638-157">When you use a session configuration file in a session configuration, PowerShell creates an active copy of the session configuration file and stores it in the \$pshome\\SessionConfig directory on the local computer.</span></span>

<span data-ttu-id="13638-158">Der Speicherort der aktiven Kopie einer Sitzungs Konfigurationsdatei wird in der configfilepath-Eigenschaft des Sitzungs Konfigurations Objekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="13638-158">The location of the active copy of a session configuration file is stored in the ConfigFilePath property of the session configuration object.</span></span>

<span data-ttu-id="13638-159">Mit dem folgenden Befehl wird der Speicherort der Sitzungs Konfigurationsdatei für die nolanguage-Sitzungs Konfiguration abgerufen.</span><span class="sxs-lookup"><span data-stu-id="13638-159">The following command gets the location of the session configuration file for the NoLanguage session configuration.</span></span>

```powershell
(Get-PSSessionConfiguration -Name NoLanguage).ConfigFilePath
```

<span data-ttu-id="13638-160">Dieser Befehl gibt einen Dateipfad zurück, der dem folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="13638-160">That command returns a file path similar to the following:</span></span>

```
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="13638-161">Sie können die PSSC-Datei in einem beliebigen Text-Editor bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="13638-161">You can edit the .pssc file in any text editor.</span></span> <span data-ttu-id="13638-162">Nachdem die Datei gespeichert wurde, wird Sie von allen neuen Sitzungen verwendet, die die Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="13638-162">After the file is saved it will be employed by any new sessions that use the session configuration.</span></span>

<span data-ttu-id="13638-163">Wenn Sie die runasvirtualaccount-oder runasvirtualaccountgroups-Einstellungen ändern müssen, müssen Sie die Registrierung der Sitzungs Konfiguration aufheben und eine Sitzungs Konfigurationsdatei erneut registrieren, die die bearbeiteten Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="13638-163">If you need to modify the RunAsVirtualAccount or the RunAsVirtualAccountGroups settings, you must un-register the session configuration and re-register a session configuration file that includes the edited values.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="13638-164">Testen einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="13638-164">Testing a Session Configuration File</span></span>

<span data-ttu-id="13638-165">Verwenden Sie das Cmdlet "Test-PSSessionConfigurationFile", um manuell bearbeiteten Sitzungs Konfigurationsdateien zu testen.</span><span class="sxs-lookup"><span data-stu-id="13638-165">Use the Test-PSSessionConfigurationFile cmdlet to test manually edited session configuration files.</span></span> <span data-ttu-id="13638-166">Das ist wichtig: Wenn die Datei Syntax und die Werte nicht gültig sind, können Benutzer die Sitzungs Konfiguration nicht verwenden, um eine Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="13638-166">That's important: if the file syntax and values are not valid users will not be able to use the session configuration to create a session.</span></span>

<span data-ttu-id="13638-167">Der folgende Befehl testet z. b. die aktive Sitzungs Konfigurationsdatei der nolanguage-Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="13638-167">For example, the following command tests the active session configuration file of the NoLanguage session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path C:\WINDOWS\System32\
WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="13638-168">Wenn die Syntax und die Werte in der Konfigurationsdatei gültig sind Test-PSSessionConfigurationFile gibt true zurück.</span><span class="sxs-lookup"><span data-stu-id="13638-168">If the syntax and values in the configuration file are valid Test-PSSessionConfigurationFile returns True.</span></span> <span data-ttu-id="13638-169">Wenn die Syntax und die Werte nicht gültig sind, gibt das Cmdlet false zurück.</span><span class="sxs-lookup"><span data-stu-id="13638-169">If the syntax and values are not valid then the cmdlet returns False.</span></span>

<span data-ttu-id="13638-170">Mit Test-PSSessionConfigurationFile können Sie alle Sitzungs Konfigurationsdateien testen, einschließlich Dateien, die vom New-PSSessionConfiguration-Cmdlet erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="13638-170">You can use Test-PSSessionConfigurationFile to test any session configuration file, including files that the New-PSSessionConfiguration cmdlet creates.</span></span> <span data-ttu-id="13638-171">Weitere Informationen finden Sie im Hilfethema für das Cmdlet "Test-PSSessionConfigurationFile".</span><span class="sxs-lookup"><span data-stu-id="13638-171">For more information, see the help topic for the Test-PSSessionConfigurationFile cmdlet.</span></span>

## <a name="removing-a-session-configuration-file"></a><span data-ttu-id="13638-172">Entfernen einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="13638-172">Removing a Session Configuration File</span></span>

<span data-ttu-id="13638-173">Eine Sitzungs Konfigurationsdatei kann nicht aus einer Sitzungs Konfiguration entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="13638-173">You cannot remove a session configuration file from a session configuration.</span></span>
<span data-ttu-id="13638-174">Allerdings können Sie die Datei durch eine neue Datei ersetzen, in der die Standardeinstellungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13638-174">However, you can replace the file with a new file that uses the default settings.</span></span> <span data-ttu-id="13638-175">Dadurch werden die von der ursprünglichen Konfigurationsdatei verwendeten Einstellungen effektiv abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="13638-175">This effectively cancels the settings used by the original configuration file.</span></span>

<span data-ttu-id="13638-176">Zum Ersetzen einer Sitzungs Konfigurationsdatei erstellen Sie eine neue Sitzungs Konfigurationsdatei, in der die Standardeinstellungen verwendet werden. verwenden Sie dann das Cmdlet "Set-PSSessionConfiguration", um die benutzerdefinierte Sitzungs Konfigurationsdatei durch die neue Datei zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="13638-176">To replace a session configuration file, create a new session configuration file that uses the default settings, then use the Set-PSSessionConfiguration cmdlet to replace the custom session configuration file with the new file.</span></span>

<span data-ttu-id="13638-177">Die folgenden Befehle erstellen z. b. eine standardmäßige Sitzungs Konfigurationsdatei und ersetzen dann die aktive Sitzungs Konfigurationsdatei in der nolanguage-Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="13638-177">For example, the following commands create a Default session configuration file and then replace the active session configuration file in the NoLanguage session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Default.pssc
Set-PSSessionConfiguration -Name NoLanguage
-Path .\Default.pssc
```

<span data-ttu-id="13638-178">Wenn diese Befehle fertiggestellt werden, bietet die nolanguage-Sitzungs Konfiguration tatsächlich vollständige Sprachunterstützung (Standardeinstellung) für alle Sitzungen, die mit dieser Sitzungs Konfiguration erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="13638-178">When these commands finish, the NoLanguage session configuration will actually provide full language support (the default setting) for all sessions created with that session configuration.</span></span>

<span data-ttu-id="13638-179">Anzeigen der Eigenschaften einer Sitzungs Konfiguration die Sitzungs Konfigurationsobjekte, die Sitzungs Konfigurationen mithilfe von Sitzungs Konfigurationsdateien darstellen, verfügen über zusätzliche Eigenschaften, die das Auffinden und Analysieren der Sitzungs Konfiguration erleichtern.</span><span class="sxs-lookup"><span data-stu-id="13638-179">Viewing the Properties of a Session Configuration The session configuration objects that represent session configurations using session configuration files have additional properties that make it easy to discover and analyze the session configuration.</span></span> <span data-ttu-id="13638-180">(Beachten Sie, dass der unten gezeigte Typname eine formatierte Sicht Definition enthält.) Sie können die Eigenschaften anzeigen, indem Sie das Cmdlet "Get-PSSessionConfiguration" ausführen und die zurückgegebenen Daten an das Get-Member-Cmdlet weiterleiten:</span><span class="sxs-lookup"><span data-stu-id="13638-180">(Note that the type name shown below includes a formatted view definition.) You can view the properties by running the Get-PSSessionConfiguration cmdlet and piping the returned data to the Get-Member cmdlet:</span></span>

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

<span data-ttu-id="13638-181">Diese Eigenschaften erleichtern das Suchen nach bestimmten Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="13638-181">These properties make it easy to search for specific session configurations.</span></span>
<span data-ttu-id="13638-182">Sie können z. b. die ExecutionPolicy-Eigenschaft verwenden, um eine Sitzungs Konfiguration zu suchen, die Sitzungen mit der RemoteSigned-Ausführungs Richtlinie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="13638-182">For example, you can use the ExecutionPolicy property to find a session configuration that supports sessions with the RemoteSigned execution policy.</span></span>
<span data-ttu-id="13638-183">Beachten Sie Folgendes: da die ExecutionPolicy-Eigenschaft nur für Sitzungen vorhanden ist, die Sitzungs Konfigurationsdateien verwenden, gibt der Befehl möglicherweise nicht alle qualifizierenden Sitzungs Konfigurationen zurück.</span><span class="sxs-lookup"><span data-stu-id="13638-183">Note that, because the ExecutionPolicy property exists only on sessions that use session configuration files, the command might not return all qualifying session configurations.</span></span>

```powershell
Get-PSSessionConfiguration |
where {$_.ExecutionPolicy -eq "RemoteSigned"}
```

<span data-ttu-id="13638-184">Mit dem folgenden Befehl werden Sitzungs Konfigurationen abgerufen, in denen der RunAsUser der Exchange-Administrator ist.</span><span class="sxs-lookup"><span data-stu-id="13638-184">The following command gets session configurations in which the RunAsUser is the Exchange administrator.</span></span>

```powershell
 Get-PSSessionConfiguration |
where {$_.RunAsUser -eq "Exchange01\Admin01"}
```

<span data-ttu-id="13638-185">Verwenden Sie das Cmdlet "Get-PSSessionCapability", um Informationen zu den einer Konfiguration zugeordneten Rollen Definitionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="13638-185">To view information about the role definitions associated with a configuration use the Get-PSSessionCapability cmdlet.</span></span> <span data-ttu-id="13638-186">Mit diesem Cmdlet können Sie die Befehle und die Umgebung ermitteln, die bestimmten Benutzern in bestimmten Endpunkten zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="13638-186">This cmdlet enables you to determine the commands and environment available to specific users in specific endpoints.</span></span>

## <a name="notes"></a><span data-ttu-id="13638-187">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="13638-187">NOTES</span></span>

<span data-ttu-id="13638-188">Sitzungs Konfigurationen unterstützen auch einen Sitzungstyp, der als "leere" Sitzung bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="13638-188">Session configurations also support a type of session known as an "empty" session.</span></span> <span data-ttu-id="13638-189">Mit einem leeren Sitzungstyp können Sie benutzerdefinierte Sitzungen mit ausgewählten Befehlen erstellen.</span><span class="sxs-lookup"><span data-stu-id="13638-189">An Empty session type enables you to create custom sessions with selected commands.</span></span> <span data-ttu-id="13638-190">Wenn Sie einer leeren Sitzung keine Module, Funktionen oder Skripts hinzufügen, ist die Sitzung auf Ausdrücke beschränkt und kann nicht praktisch verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13638-190">If you do not add modules, functions, or scripts to an empty session, the session is limited to expressions and might not be of any practical use.</span></span> <span data-ttu-id="13638-191">Die SessionType-Eigenschaft gibt Aufschluss darüber, ob Sie mit einer leeren Sitzung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="13638-191">The SessionType property tells you whether or not you are working with an empty session.</span></span>

## <a name="see-also"></a><span data-ttu-id="13638-192">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="13638-192">SEE ALSO</span></span>

[<span data-ttu-id="13638-193">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="13638-193">about_Session_Configurations</span></span>](about_Session_Configurations.md)

[<span data-ttu-id="13638-194">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="13638-194">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="13638-195">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="13638-195">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="13638-196">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="13638-196">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="13638-197">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="13638-197">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="13638-198">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="13638-198">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="13638-199">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="13638-199">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="13638-200">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="13638-200">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="13638-201">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="13638-201">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="13638-202">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="13638-202">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

[<span data-ttu-id="13638-203">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="13638-203">Get-PSSessionCapability</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionCapability)

[<span data-ttu-id="13638-204">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="13638-204">New-PSRoleCapabilityFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSRoleCapabilityFile)

