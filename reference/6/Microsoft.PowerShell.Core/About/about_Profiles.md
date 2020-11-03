---
description: Hier wird beschrieben, wie ein PowerShell-Profil erstellt und verwendet wird.
keywords: powershell,cmdlet
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Profiles
ms.openlocfilehash: d0457cf485528f675840161383aa24d0f63781fb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221364"
---
# <a name="about-profiles"></a><span data-ttu-id="ac669-104">Informationen zu Profilen</span><span class="sxs-lookup"><span data-stu-id="ac669-104">About Profiles</span></span>

## <a name="short-description"></a><span data-ttu-id="ac669-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac669-105">Short Description</span></span>
<span data-ttu-id="ac669-106">Hier wird beschrieben, wie ein PowerShell-Profil erstellt und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac669-106">Describes how to create and use a PowerShell profile.</span></span>

## <a name="long-description"></a><span data-ttu-id="ac669-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac669-107">Long Description</span></span>

<span data-ttu-id="ac669-108">Sie können ein PowerShell-Profil erstellen, um Ihre Umgebung anzupassen und um sitzungsspezifische Elemente zu jeder gestarteten PowerShell-Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ac669-108">You can create a PowerShell profile to customize your environment and to add session-specific elements to every PowerShell session that you start.</span></span>

<span data-ttu-id="ac669-109">Ein PowerShell-Profil ist ein Skript, das ausgeführt wird, wenn PowerShell gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ac669-109">A PowerShell profile is a script that runs when PowerShell starts.</span></span> <span data-ttu-id="ac669-110">Sie können das Profil als Anmelde Skript verwenden, um die Umgebung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ac669-110">You can use the profile as a logon script to customize the environment.</span></span> <span data-ttu-id="ac669-111">Sie können Befehle, Aliase, Funktionen, Variablen, Snap-Ins, Module und PowerShell-Laufwerke hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ac669-111">You can add commands, aliases, functions, variables, snap-ins, modules, and PowerShell drives.</span></span> <span data-ttu-id="ac669-112">Sie können Ihrem Profil auch weitere Sitzungs spezifische Elemente hinzufügen, sodass diese in jeder Sitzung verfügbar sind, ohne Sie importieren oder neu erstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ac669-112">You can also add other session-specific elements to your profile so they are available in every session without having to import or re-create them.</span></span>

<span data-ttu-id="ac669-113">PowerShell unterstützt mehrere Profile für Benutzer und Host Programme.</span><span class="sxs-lookup"><span data-stu-id="ac669-113">PowerShell supports several profiles for users and host programs.</span></span> <span data-ttu-id="ac669-114">Es werden jedoch nicht die Profile für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="ac669-114">However, it does not create the profiles for you.</span></span> <span data-ttu-id="ac669-115">In diesem Thema werden die Profile beschrieben, und es wird beschrieben, wie Profile auf Ihrem Computer erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ac669-115">This topic describes the profiles, and it describes how to create and maintain profiles on your computer.</span></span>

<span data-ttu-id="ac669-116">Es wird erläutert, wie Sie den **NoProfile** -Parameter der PowerShell-Konsole (PowerShell.exe) verwenden, um PowerShell ohne Profile zu starten.</span><span class="sxs-lookup"><span data-stu-id="ac669-116">It explains how to use the **NoProfile** parameter of the PowerShell console (PowerShell.exe) to start PowerShell without any profiles.</span></span> <span data-ttu-id="ac669-117">Außerdem werden die Auswirkungen der PowerShell-Ausführungs Richtlinie auf Profile erläutert.</span><span class="sxs-lookup"><span data-stu-id="ac669-117">And, it explains the effect of the PowerShell execution policy on profiles.</span></span>

## <a name="the-profile-files"></a><span data-ttu-id="ac669-118">Profil Dateien</span><span class="sxs-lookup"><span data-stu-id="ac669-118">The Profile Files</span></span>

<span data-ttu-id="ac669-119">PowerShell unterstützt mehrere Profil Dateien.</span><span class="sxs-lookup"><span data-stu-id="ac669-119">PowerShell supports several profile files.</span></span> <span data-ttu-id="ac669-120">PowerShell-Host Programme können außerdem ihre eigenen Host spezifischen Profile unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ac669-120">Also, PowerShell host programs can support their own host-specific profiles.</span></span>

<span data-ttu-id="ac669-121">Die PowerShell-Konsole unterstützt z. b. die folgenden grundlegenden Profil Dateien.</span><span class="sxs-lookup"><span data-stu-id="ac669-121">For example, the PowerShell console supports the following basic profile files.</span></span> <span data-ttu-id="ac669-122">Die Profile werden in der Reihenfolge der Rangfolge aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ac669-122">The profiles are listed in precedence order.</span></span> <span data-ttu-id="ac669-123">Das erste Profil weist die höchste Rangfolge auf.</span><span class="sxs-lookup"><span data-stu-id="ac669-123">The first profile has the highest precedence.</span></span>

|<span data-ttu-id="ac669-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ac669-124">Description</span></span>               | <span data-ttu-id="ac669-125">`Path`</span><span class="sxs-lookup"><span data-stu-id="ac669-125">Path</span></span>                                          |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="ac669-126">Alle Benutzer, alle Hosts</span><span class="sxs-lookup"><span data-stu-id="ac669-126">All Users, All Hosts</span></span>      |<span data-ttu-id="ac669-127">$PSHOME \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="ac669-127">$PSHOME\\Profile.ps1</span></span>                           |
|<span data-ttu-id="ac669-128">Alle Benutzer, aktueller Host</span><span class="sxs-lookup"><span data-stu-id="ac669-128">All Users, Current Host</span></span>   |<span data-ttu-id="ac669-129">$PSHOME \\Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="ac669-129">$PSHOME\\Microsoft.PowerShell_profile.ps1</span></span>      |
|<span data-ttu-id="ac669-130">Aktueller Benutzer, alle Hosts</span><span class="sxs-lookup"><span data-stu-id="ac669-130">Current User, All Hosts</span></span>   |<span data-ttu-id="ac669-131">$Home \\ [My] dokumentiert \\ PowerShell- \\Profile.ps1</span><span class="sxs-lookup"><span data-stu-id="ac669-131">$Home\\[My ]Documents\\PowerShell\\Profile.ps1</span></span> |
|<span data-ttu-id="ac669-132">Aktueller Benutzer, aktueller Host</span><span class="sxs-lookup"><span data-stu-id="ac669-132">Current user, Current Host</span></span>|<span data-ttu-id="ac669-133">$Home \\ [meine] Dokumente \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac669-133">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="ac669-134">Microsoft.PowerShell_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="ac669-134">Microsoft.PowerShell_profile.ps1</span></span> |

<span data-ttu-id="ac669-135">Die Profil Pfade enthalten die folgenden Variablen:</span><span class="sxs-lookup"><span data-stu-id="ac669-135">The profile paths include the following variables:</span></span>

- <span data-ttu-id="ac669-136">Die `$PSHOME` Variable, in der das Installationsverzeichnis für PowerShell gespeichert ist</span><span class="sxs-lookup"><span data-stu-id="ac669-136">The `$PSHOME` variable, which stores the installation directory for PowerShell</span></span>
- <span data-ttu-id="ac669-137">Die `$Home` Variable, in der das Basisverzeichnis des aktuellen Benutzers gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ac669-137">The `$Home` variable, which stores the current user's home directory</span></span>

<span data-ttu-id="ac669-138">Außerdem können andere Programme, die PowerShell hosten, eigene Profile unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ac669-138">In addition, other programs that host PowerShell can support their own profiles.</span></span> <span data-ttu-id="ac669-139">Beispielsweise werden von Visual Studio Code die folgenden Host spezifischen Profile unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac669-139">For example, Visual Studio Code supports the following host-specific profiles.</span></span>

|<span data-ttu-id="ac669-140">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ac669-140">Description</span></span>               | <span data-ttu-id="ac669-141">`Path`</span><span class="sxs-lookup"><span data-stu-id="ac669-141">Path</span></span>                                     |
|--------------------------|------------------------------------------|
|<span data-ttu-id="ac669-142">Alle Benutzer, aktueller Host</span><span class="sxs-lookup"><span data-stu-id="ac669-142">All users, Current Host</span></span>   |<span data-ttu-id="ac669-143">$PSHOME \\Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="ac669-143">$PSHOME\\Microsoft.VSCode_profile.ps1</span></span>|
|<span data-ttu-id="ac669-144">Aktueller Benutzer, aktueller Host</span><span class="sxs-lookup"><span data-stu-id="ac669-144">Current user, Current Host</span></span>|<span data-ttu-id="ac669-145">$Home \\ [meine] Dokumente \\ PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac669-145">$Home\\[My ]Documents\\PowerShell</span></span>\\<br><span data-ttu-id="ac669-146">Microsoft.VSCode_profile.ps1</span><span class="sxs-lookup"><span data-stu-id="ac669-146">Microsoft.VSCode_profile.ps1</span></span>|

<span data-ttu-id="ac669-147">In der PowerShell-Hilfe ist das Profil "CurrentUser, Current Host" das Profil, das am häufigsten als "Ihr PowerShell-Profil" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ac669-147">In PowerShell Help, the "CurrentUser, Current Host" profile is the profile most often referred to as "your PowerShell profile".</span></span>

## <a name="the-profile-variable"></a><span data-ttu-id="ac669-148">Die $Profile Variable</span><span class="sxs-lookup"><span data-stu-id="ac669-148">The $PROFILE variable</span></span>

<span data-ttu-id="ac669-149">Die `$PROFILE` Automatische Variable speichert die Pfade zu den PowerShell-Profilen, die in der aktuellen Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ac669-149">The `$PROFILE` automatic variable stores the paths to the PowerShell profiles that are available in the current session.</span></span>

<span data-ttu-id="ac669-150">Um einen Profilpfad anzuzeigen, zeigen Sie den Wert der `$PROFILE` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="ac669-150">To view a profile path, display the value of the `$PROFILE` variable.</span></span> <span data-ttu-id="ac669-151">Sie können auch die- `$PROFILE` Variable in einem Befehl verwenden, um einen Pfad darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ac669-151">You can also use the `$PROFILE` variable in a command to represent a path.</span></span>

<span data-ttu-id="ac669-152">Die `$PROFILE` Variable speichert den Pfad zum Profil "aktueller Benutzer, aktueller Host".</span><span class="sxs-lookup"><span data-stu-id="ac669-152">The `$PROFILE` variable stores the path to the "Current User, Current Host" profile.</span></span> <span data-ttu-id="ac669-153">Die anderen Profile werden in den Hinweis Eigenschaften der `$PROFILE` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ac669-153">The other profiles are saved in note properties of the `$PROFILE` variable.</span></span>

<span data-ttu-id="ac669-154">Beispielsweise enthält die `$PROFILE` Variable die folgenden Werte in der Windows PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="ac669-154">For example, the `$PROFILE` variable has the following values in the Windows PowerShell console.</span></span>

|<span data-ttu-id="ac669-155">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ac669-155">Description</span></span>                |<span data-ttu-id="ac669-156">Name</span><span class="sxs-lookup"><span data-stu-id="ac669-156">Name</span></span>                              |
|---------------------------|----------------------------------|
|<span data-ttu-id="ac669-157">Aktueller Benutzer, aktueller Host</span><span class="sxs-lookup"><span data-stu-id="ac669-157">Current User, Current Host</span></span> |`$PROFILE`                        |
|<span data-ttu-id="ac669-158">Aktueller Benutzer, aktueller Host</span><span class="sxs-lookup"><span data-stu-id="ac669-158">Current User, Current Host</span></span> |`$PROFILE.CurrentUserCurrentHost` |
|<span data-ttu-id="ac669-159">Aktueller Benutzer, alle Hosts</span><span class="sxs-lookup"><span data-stu-id="ac669-159">Current User, All Hosts</span></span>    |`$PROFILE.CurrentUserAllHosts`    |
|<span data-ttu-id="ac669-160">Alle Benutzer, aktueller Host</span><span class="sxs-lookup"><span data-stu-id="ac669-160">All Users, Current Host</span></span>    |`$PROFILE.AllUsersCurrentHost`    |
|<span data-ttu-id="ac669-161">Alle Benutzer, alle Hosts</span><span class="sxs-lookup"><span data-stu-id="ac669-161">All Users, All Hosts</span></span>       |`$PROFILE.AllUsersAllHosts`       |

<span data-ttu-id="ac669-162">Da sich die Werte der `$PROFILE` Variablen für jeden Benutzer und jede Host Anwendung ändern, sollten Sie sicherstellen, dass Sie die Werte der Profil Variablen in jeder verwendeten PowerShell-Host Anwendung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ac669-162">Because the values of the `$PROFILE` variable change for each user and in each host application, ensure that you display the values of the profile variables in each PowerShell host application that you use.</span></span>

<span data-ttu-id="ac669-163">Geben Sie Folgendes ein, um die aktuellen Werte der `$PROFILE` Variablen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ac669-163">To see the current values of the `$PROFILE` variable, type:</span></span>

```powershell
$PROFILE | Get-Member -Type NoteProperty
```

<span data-ttu-id="ac669-164">Die-Variable kann `$PROFILE` in vielen Befehlen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac669-164">You can use the `$PROFILE` variable in many commands.</span></span> <span data-ttu-id="ac669-165">Mit dem folgenden Befehl wird beispielsweise das Profil "aktueller Benutzer, aktueller Host" in Editor geöffnet:</span><span class="sxs-lookup"><span data-stu-id="ac669-165">For example, the following command opens the "Current User, Current Host" profile in Notepad:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="ac669-166">Der folgende Befehl bestimmt, ob das Profil "alle Benutzer, alle Hosts" auf dem lokalen Computer erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="ac669-166">The following command determines whether an "All Users, All Hosts" profile has been created on the local computer:</span></span>

```powershell
Test-Path -Path $PROFILE.AllUsersAllHosts
```

## <a name="how-to-create-a-profile"></a><span data-ttu-id="ac669-167">Erstellen eines Profils</span><span class="sxs-lookup"><span data-stu-id="ac669-167">How to create a profile</span></span>

<span data-ttu-id="ac669-168">Verwenden Sie zum Erstellen eines PowerShell-Profils das folgende Befehls Format:</span><span class="sxs-lookup"><span data-stu-id="ac669-168">To create a PowerShell profile, use the following command format:</span></span>

```powershell
if (!(Test-Path -Path <profile-name>)) {
  New-Item -ItemType File -Path <profile-name> -Force
}
```

<span data-ttu-id="ac669-169">Verwenden Sie z. b. den folgenden Befehl, um ein Profil für den aktuellen Benutzer in der aktuellen PowerShell-Host Anwendung zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="ac669-169">For example, to create a profile for the current user in the current PowerShell host application, use the following command:</span></span>

```powershell
if (!(Test-Path -Path $PROFILE)) {
  New-Item -ItemType File -Path $PROFILE -Force
}
```

<span data-ttu-id="ac669-170">In diesem Befehl `If` hindert Sie die-Anweisung daran, ein vorhandenes Profil zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ac669-170">In this command, the `If` statement prevents you from overwriting an existing profile.</span></span> <span data-ttu-id="ac669-171">Ersetzen Sie den Wert des \<profile-path\> Platzhalters durch den Pfad zu der Profil Datei, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ac669-171">Replace the value of the \<profile-path\> placeholder with the path to the profile file that you want to create.</span></span>

> [!NOTE]
> <span data-ttu-id="ac669-172">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um "alle Benutzer"-Profile in Windows Vista und höheren Versionen von Windows zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac669-172">To create "All Users" profiles in Windows Vista and later versions of Windows, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="how-to-edit-a-profile"></a><span data-ttu-id="ac669-173">Bearbeiten eines Profils</span><span class="sxs-lookup"><span data-stu-id="ac669-173">How to edit a profile</span></span>

<span data-ttu-id="ac669-174">Sie können ein beliebiges PowerShell-Profil in einem Text-Editor öffnen, z. b. in Editor.</span><span class="sxs-lookup"><span data-stu-id="ac669-174">You can open any PowerShell profile in a text editor, such as Notepad.</span></span>

<span data-ttu-id="ac669-175">Um das Profil des aktuellen Benutzers in der aktuellen PowerShell-Host Anwendung in Editor zu öffnen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ac669-175">To open the profile of the current user in the current PowerShell host application in Notepad, type:</span></span>

```powershell
notepad $PROFILE
```

<span data-ttu-id="ac669-176">Um andere Profile zu öffnen, geben Sie den Namen des Profils an.</span><span class="sxs-lookup"><span data-stu-id="ac669-176">To open other profiles, specify the profile name.</span></span> <span data-ttu-id="ac669-177">Wenn Sie z. b. das Profil für alle Benutzer aller Host Anwendungen öffnen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ac669-177">For example, to open the profile for all the users of all the host applications, type:</span></span>

```powershell
notepad $PROFILE.AllUsersAllHosts
```

<span data-ttu-id="ac669-178">Speichern Sie die Profil Datei, und starten Sie PowerShell neu, um die Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="ac669-178">To apply the changes, save the profile file, and then restart PowerShell.</span></span>

## <a name="how-to-choose-a-profile"></a><span data-ttu-id="ac669-179">Auswählen eines Profils</span><span class="sxs-lookup"><span data-stu-id="ac669-179">How to choose a profile</span></span>

<span data-ttu-id="ac669-180">Wenn Sie mehrere Host Anwendungen verwenden, platzieren Sie die Elemente, die Sie in allen Host Anwendungen verwenden, in Ihrem `$PROFILE.CurrentUserAllHosts` Profil.</span><span class="sxs-lookup"><span data-stu-id="ac669-180">If you use multiple host applications, put the items that you use in all the host applications into your `$PROFILE.CurrentUserAllHosts` profile.</span></span> <span data-ttu-id="ac669-181">Platzieren Sie Elemente, die für eine Host Anwendung spezifisch sind, z. b. einen Befehl, der die Hintergrundfarbe für eine Host Anwendung festlegt, in einem Profil, das für diese Host Anwendung spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="ac669-181">Put items that are specific to a host application, such as a command that sets the background color for a host application, in a profile that is specific to that host application.</span></span>

<span data-ttu-id="ac669-182">Wenn Sie ein Administrator sind, der PowerShell für viele Benutzer anpasst, befolgen Sie die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="ac669-182">If you are an administrator who is customizing PowerShell for many users, follow these guidelines:</span></span>

- <span data-ttu-id="ac669-183">Speichern der allgemeinen Elemente im `$PROFILE.AllUsersAllHosts` Profil</span><span class="sxs-lookup"><span data-stu-id="ac669-183">Store the common items in the `$PROFILE.AllUsersAllHosts` profile</span></span>
- <span data-ttu-id="ac669-184">Speichern Sie Elemente, die für eine Host Anwendung spezifisch sind, in Profilen, die `$PROFILE.AllUsersCurrentHost` für die Host Anwendung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="ac669-184">Store items that are specific to a host application in `$PROFILE.AllUsersCurrentHost` profiles that are specific to the host application</span></span>
- <span data-ttu-id="ac669-185">Speichern von Elementen für bestimmte Benutzer in den benutzerspezifischen Profilen</span><span class="sxs-lookup"><span data-stu-id="ac669-185">Store items for particular users in the user-specific profiles</span></span>

<span data-ttu-id="ac669-186">Stellen Sie sicher, dass Sie in der Dokumentation der Host Anwendung nach einer speziellen Implementierung von PowerShell-Profilen suchen.</span><span class="sxs-lookup"><span data-stu-id="ac669-186">Be sure to check the host application documentation for any special implementation of PowerShell profiles.</span></span>

## <a name="how-to-use-a-profile"></a><span data-ttu-id="ac669-187">Verwenden eines Profils</span><span class="sxs-lookup"><span data-stu-id="ac669-187">How to use a profile</span></span>

<span data-ttu-id="ac669-188">Viele der Elemente, die Sie in PowerShell erstellen, und die meisten Befehle, die Sie ausführen, wirken sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="ac669-188">Many of the items that you create in PowerShell and most commands that you run affect only the current session.</span></span> <span data-ttu-id="ac669-189">Wenn Sie die Sitzung beenden, werden die Elemente gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ac669-189">When you end the session, the items are deleted.</span></span>

<span data-ttu-id="ac669-190">Die Sitzungs spezifischen Befehle und Elemente enthalten Variablen, Einstellungs Variablen, Aliase, Funktionen, Befehle (mit Ausnahme von " [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)") und PowerShell-Module, die Sie der Sitzung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ac669-190">The session-specific commands and items include variables, preference variables, aliases, functions, commands (except for [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)), and PowerShell modules that you add to the session.</span></span>

<span data-ttu-id="ac669-191">Um diese Elemente zu speichern und in allen zukünftigen Sitzungen verfügbar zu machen, fügen Sie Sie einem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac669-191">To save these items and make them available in all future sessions, add them to a PowerShell profile.</span></span>

<span data-ttu-id="ac669-192">Eine weitere häufige Verwendung von Profilen ist das Speichern häufig verwendeter Funktionen, Aliase und Variablen.</span><span class="sxs-lookup"><span data-stu-id="ac669-192">Another common use for profiles is to save frequently-used functions, aliases, and variables.</span></span> <span data-ttu-id="ac669-193">Wenn Sie die Elemente in einem Profil speichern, können Sie Sie in einer beliebigen anwendbaren Sitzung verwenden, ohne Sie neu erstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ac669-193">When you save the items in a profile, you can use them in any applicable session without recreating them.</span></span>

## <a name="how-to-start-a-profile"></a><span data-ttu-id="ac669-194">Starten eines Profils</span><span class="sxs-lookup"><span data-stu-id="ac669-194">How to start a profile</span></span>

<span data-ttu-id="ac669-195">Wenn Sie die Profil Datei öffnen, ist sie leer.</span><span class="sxs-lookup"><span data-stu-id="ac669-195">When you open the profile file, it is blank.</span></span> <span data-ttu-id="ac669-196">Allerdings können Sie Sie mit den Variablen, Aliasen und Befehlen ausfüllen, die Sie häufig verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac669-196">However, you can fill it with the variables, aliases, and commands that you use frequently.</span></span>

<span data-ttu-id="ac669-197">Hier finden Sie einige Vorschläge für den Einstieg.</span><span class="sxs-lookup"><span data-stu-id="ac669-197">Here are a few suggestions to get you started.</span></span>

### <a name="add-commands-that-make-it-easy-to-open-your-profile"></a><span data-ttu-id="ac669-198">Hinzufügen von Befehlen, die das Öffnen des Profils erleichtern</span><span class="sxs-lookup"><span data-stu-id="ac669-198">Add commands that make it easy to open your profile</span></span>

<span data-ttu-id="ac669-199">Dies ist besonders nützlich, wenn Sie ein anderes Profil als das Profil "aktueller Benutzer, aktueller Host" verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac669-199">This is especially useful if you use a profile other than the "Current User, Current Host" profile.</span></span> <span data-ttu-id="ac669-200">Fügen Sie z. b. den folgenden Befehl hinzu:</span><span class="sxs-lookup"><span data-stu-id="ac669-200">For example, add the following command:</span></span>

```powershell
function Pro {notepad $PROFILE.CurrentUserAllHosts}
```

### <a name="add-a-function-that-lists-the-aliases-for-any-cmdlet"></a><span data-ttu-id="ac669-201">Fügen Sie eine Funktion hinzu, die die Aliase für alle Cmdlets auflistet.</span><span class="sxs-lookup"><span data-stu-id="ac669-201">Add a function that lists the aliases for any cmdlet</span></span>

```powershell
function Get-CmdletAlias ($cmdletname) {
  Get-Alias |
    Where-Object -FilterScript {$_.Definition -like "$cmdletname"} |
      Format-Table -Property Definition, Name -AutoSize
}
```

### <a name="customize-your-console"></a><span data-ttu-id="ac669-202">Anpassen der Konsole</span><span class="sxs-lookup"><span data-stu-id="ac669-202">Customize your console</span></span>

```powershell
function Color-Console {
  $Host.ui.rawui.backgroundcolor = "white"
  $Host.ui.rawui.foregroundcolor = "black"
  $hosttime = (Get-ChildItem -Path $PSHOME\PowerShell.exe).CreationTime
  $hostversion="$($Host.Version.Major)`.$($Host.Version.Minor)"
  $Host.UI.RawUI.WindowTitle = "PowerShell $hostversion ($hosttime)"
  Clear-Host
}
Color-Console
```

### <a name="add-a-customized-powershell-prompt"></a><span data-ttu-id="ac669-203">Hinzufügen einer angepassten PowerShell-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="ac669-203">Add a customized PowerShell prompt</span></span>

```powershell
function Prompt
{
$env:COMPUTERNAME + "\" + (Get-Location) + "> "
}
```

<span data-ttu-id="ac669-204">Weitere Informationen zur PowerShell-Eingabeaufforderung finden Sie unter [about_Prompts](about_Prompts.md).</span><span class="sxs-lookup"><span data-stu-id="ac669-204">For more information about the PowerShell prompt, see [about_Prompts](about_Prompts.md).</span></span>

## <a name="the-noprofile-parameter"></a><span data-ttu-id="ac669-205">Der NoProfile-Parameter</span><span class="sxs-lookup"><span data-stu-id="ac669-205">The NoProfile parameter</span></span>

<span data-ttu-id="ac669-206">Wenn Sie PowerShell ohne profile starten möchten, verwenden Sie den **NoProfile** -Parameter von **PowerShell.exe** , das Programm, das PowerShell startet.</span><span class="sxs-lookup"><span data-stu-id="ac669-206">To start PowerShell without profiles, use the **NoProfile** parameter of **PowerShell.exe** , the program that starts PowerShell.</span></span>

<span data-ttu-id="ac669-207">Öffnen Sie zunächst ein Programm, mit dem PowerShell gestartet werden kann, z. b. Cmd.exe oder PowerShell selbst.</span><span class="sxs-lookup"><span data-stu-id="ac669-207">To begin, open a program that can start PowerShell, such as Cmd.exe or PowerShell itself.</span></span> <span data-ttu-id="ac669-208">Sie können auch das Dialogfeld Ausführen in Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac669-208">You can also use the Run dialog box in Windows.</span></span>

<span data-ttu-id="ac669-209">Typ:</span><span class="sxs-lookup"><span data-stu-id="ac669-209">Type:</span></span>

```
PowerShell -NoProfile
```

<span data-ttu-id="ac669-210">Eine umfassende Liste der Parameter PowerShell.exe erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="ac669-210">For a complete list of the parameters of PowerShell.exe, type:</span></span>

```
PowerShell -?
```

## <a name="profiles-and-execution-policy"></a><span data-ttu-id="ac669-211">Profile und Ausführungs Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ac669-211">Profiles and Execution Policy</span></span>

<span data-ttu-id="ac669-212">Die PowerShell-Ausführungs Richtlinie bestimmt teilweise, ob Sie Skripts ausführen und Konfigurationsdateien, einschließlich der Profile, laden können.</span><span class="sxs-lookup"><span data-stu-id="ac669-212">The PowerShell execution policy determines, in part, whether you can run scripts and load configuration files, including the profiles.</span></span> <span data-ttu-id="ac669-213">Die **Eingeschränkte** Ausführungs Richtlinie ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ac669-213">The **Restricted** execution policy is the default.</span></span> <span data-ttu-id="ac669-214">Dadurch wird verhindert, dass alle Skripts ausgeführt werden, einschließlich der Profile.</span><span class="sxs-lookup"><span data-stu-id="ac669-214">It prevents all scripts from running, including the profiles.</span></span> <span data-ttu-id="ac669-215">Wenn Sie die Richtlinie "Restricted" verwenden, wird das Profil nicht ausgeführt, und sein Inhalt wird nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="ac669-215">If you use the "Restricted" policy, the profile does not run, and its contents are not applied.</span></span>

<span data-ttu-id="ac669-216">`Set-ExecutionPolicy`Die Ausführungs Richtlinie wird von einem Befehl festgelegt und geändert.</span><span class="sxs-lookup"><span data-stu-id="ac669-216">A `Set-ExecutionPolicy` command sets and changes your execution policy.</span></span> <span data-ttu-id="ac669-217">Dabei handelt es sich um einen der wenigen Befehle, der in allen PowerShell-Sitzungen gilt, da der Wert in der Registrierung gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ac669-217">It is one of the few commands that applies in all PowerShell sessions because the value is saved in the registry.</span></span> <span data-ttu-id="ac669-218">Sie müssen Sie nicht festlegen, wenn Sie die Konsole öffnen, und Sie müssen keinen `Set-ExecutionPolicy` Befehl in Ihrem Profil speichern.</span><span class="sxs-lookup"><span data-stu-id="ac669-218">You do not have to set it when you open the console, and you do not have to store a `Set-ExecutionPolicy` command in your profile.</span></span>

## <a name="profiles-and-remote-sessions"></a><span data-ttu-id="ac669-219">Profile und Remote Sitzungen</span><span class="sxs-lookup"><span data-stu-id="ac669-219">Profiles and remote sessions</span></span>

<span data-ttu-id="ac669-220">PowerShell-Profile werden nicht automatisch in Remote Sitzungen ausgeführt, sodass die Befehle, die die Profile hinzufügen, nicht in der Remote Sitzung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ac669-220">PowerShell profiles are not run automatically in remote sessions, so the commands that the profiles add are not present in the remote session.</span></span> <span data-ttu-id="ac669-221">Außerdem `$PROFILE` wird die automatische Variable nicht in Remote Sitzungen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="ac669-221">In addition, the `$PROFILE` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="ac669-222">Verwenden Sie das Cmdlet "Start [-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) ", um ein Profil in einer Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ac669-222">To run a profile in a session, use the [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlet.</span></span>

<span data-ttu-id="ac669-223">Der folgende Befehl führt z. b. das Profil "aktueller Benutzer, Aktuelles Host" vom lokalen Computer in der Sitzung in aus `$s` .</span><span class="sxs-lookup"><span data-stu-id="ac669-223">For example, the following command runs the "Current user, Current Host" profile from the local computer in the session in `$s`.</span></span>

```powershell
Invoke-Command -Session $s -FilePath $PROFILE
```

<span data-ttu-id="ac669-224">Der folgende Befehl führt das Profil "aktueller Benutzer, Aktuelles Host" vom Remote Computer in der Sitzung in aus `$s` .</span><span class="sxs-lookup"><span data-stu-id="ac669-224">The following command runs the "Current user, Current Host" profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="ac669-225">Da die `$PROFILE` Variable nicht aufgefüllt wird, verwendet der Befehl den expliziten Pfad zum Profil.</span><span class="sxs-lookup"><span data-stu-id="ac669-225">Because the `$PROFILE` variable is not populated, the command uses the explicit path to the profile.</span></span> <span data-ttu-id="ac669-226">Wir verwenden den Dot-Sourcing-Operator, damit das Profil im aktuellen Bereich auf dem Remote Computer und nicht in seinem eigenen Bereich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ac669-226">We use dot sourcing operator so that the profile executes in the current scope on the remote computer and not in its own scope.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {
  . "$HOME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="ac669-227">Nachdem Sie diesen Befehl ausgeführt haben, sind die Befehle, die das Profil der Sitzung hinzufügt, in verfügbar `$s` .</span><span class="sxs-lookup"><span data-stu-id="ac669-227">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac669-228">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac669-228">See Also</span></span>

[<span data-ttu-id="ac669-229">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="ac669-229">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="ac669-230">about_Functions</span><span class="sxs-lookup"><span data-stu-id="ac669-230">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="ac669-231">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="ac669-231">about_Prompts</span></span>](about_Prompts.md)

[<span data-ttu-id="ac669-232">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="ac669-232">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="ac669-233">about_Signing</span><span class="sxs-lookup"><span data-stu-id="ac669-233">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="ac669-234">about_Remote</span><span class="sxs-lookup"><span data-stu-id="ac669-234">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="ac669-235">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="ac669-235">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="ac669-236">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ac669-236">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)
