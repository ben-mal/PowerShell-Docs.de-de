---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-PSSession
ms.openlocfilehash: 11533a9b127dc6d088258392c0e142bfbe5c070c
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388024"
---
# <span data-ttu-id="e3bd5-103">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="e3bd5-103">Export-PSSession</span></span>

## <span data-ttu-id="e3bd5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e3bd5-104">SYNOPSIS</span></span>

<span data-ttu-id="e3bd5-105">Exportiert Befehle aus einer anderen Sitzung und speichert Sie in einem PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-105">Exports commands from another session and saves them in a PowerShell module.</span></span>

## <span data-ttu-id="e3bd5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3bd5-106">SYNTAX</span></span>

```
Export-PSSession [-Session] <PSSession> [-OutputModule] <string> [[-CommandName] <string[]>]
 [[-FormatTypeName] <string[]>] [-Force] [-Encoding <string>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <string[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-Certificate <X509Certificate2>]
 [<CommonParameters>]
```

## <span data-ttu-id="e3bd5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e3bd5-107">DESCRIPTION</span></span>

<span data-ttu-id="e3bd5-108">Das `Export-PSSession` Cmdlet ruft Cmdlets, Funktionen, Aliase und andere Befehls Typen aus einer anderen PowerShell-Sitzung (PSSession) auf einem lokalen Computer oder einem Remote Computer ab und speichert Sie in einem PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-108">The `Export-PSSession` cmdlet gets cmdlets, functions, aliases, and other command types from another PowerShell session (PSSession) on a local or remote computer and saves them in a PowerShell module.</span></span> <span data-ttu-id="e3bd5-109">Verwenden Sie das-Cmdlet, um der aktuellen Sitzung die Befehle aus dem Modul hinzuzufügen `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-109">To add the commands from the module to the current session, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="e3bd5-110">Im Gegensatz zu `Import-PSSession` , das Befehle aus einer anderen PSSession in die aktuelle Sitzung importiert, `Export-PSSession` speichert die Befehle in einem Modul.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-110">Unlike `Import-PSSession`, which imports commands from another PSSession into the current session, `Export-PSSession` saves the commands in a module.</span></span> <span data-ttu-id="e3bd5-111">Die Befehle werden nicht in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-111">The commands are not imported into the current session.</span></span>

<span data-ttu-id="e3bd5-112">Um Befehle zu exportieren, verwenden `New-PSSession` Sie das Cmdlet, um eine PSSession mit den Befehlen zu erstellen, die Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-112">To export commands, use the `New-PSSession` cmdlet to create a PSSession that has the commands that you want to export.</span></span> <span data-ttu-id="e3bd5-113">Verwenden Sie dann das- `Export-PSSession` Cmdlet, um die Befehle zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-113">Then use the `Export-PSSession` cmdlet to export the commands.</span></span>

<span data-ttu-id="e3bd5-114">Um Konflikte bei Befehlsnamen zu vermeiden, wird standardmäßig `Export-PSSession` alle Befehle exportiert, mit Ausnahme der Befehle, die in der aktuellen Sitzung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-114">To prevent command name conflicts, the default for `Export-PSSession` is to export all commands, except for commands that exist in the current session.</span></span> <span data-ttu-id="e3bd5-115">Sie können den **CommandName** -Parameter verwenden, um die Befehle anzugeben, die exportiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-115">You can use the **CommandName** parameter to specify the commands to export.</span></span>

<span data-ttu-id="e3bd5-116">Das- `Export-PSSession` Cmdlet verwendet das implizite Remoting-Feature von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-116">The `Export-PSSession` cmdlet uses the implicit remoting feature of PowerShell.</span></span> <span data-ttu-id="e3bd5-117">Wenn Sie Befehle in die aktuelle Sitzung importieren, werden Sie implizit in der ursprünglichen Sitzung oder in einer ähnlichen Sitzung auf dem ursprünglichen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-117">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

## <span data-ttu-id="e3bd5-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e3bd5-118">EXAMPLES</span></span>

### <span data-ttu-id="e3bd5-119">Beispiel 1: Exportieren von Befehlen aus einer PSSession</span><span class="sxs-lookup"><span data-stu-id="e3bd5-119">Example 1: Export commands from a PSSession</span></span>

<span data-ttu-id="e3bd5-120">In diesem Beispiel wird eine neue PSSession vom lokalen Computer zum Server01-Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-120">This example creates a new PSSession from the local computer to the Server01 computer.</span></span> <span data-ttu-id="e3bd5-121">Alle Befehle, mit Ausnahme derjenigen, die in der aktuellen Sitzung vorhanden sind, werden auf dem lokalen Computer in das Modul mit dem Namen Server01 exportiert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-121">All of the commands, except those that exist in the current session, are exported to the module named Server01 on the local computer.</span></span> <span data-ttu-id="e3bd5-122">Der Export umfasst die Formatierungsdaten für die Befehle.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-122">The export includes the formatting data for the commands.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Export-PSSession -Session $S -OutputModule Server01
```

<span data-ttu-id="e3bd5-123">Der `New-PSSession` Befehl erstellt eine PSSession auf dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-123">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span> <span data-ttu-id="e3bd5-124">Die PSSession wird in der `$S` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-124">The PSSession is stored in the `$S` variable.</span></span> <span data-ttu-id="e3bd5-125">Der `Export-PSSession` Befehl exportiert die `$S` Befehle der Variablen und formatiert Daten in das Modul Server01.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-125">The `Export-PSSession` command exports the `$S` variable's commands and formatting data into the Server01 module.</span></span>

### <span data-ttu-id="e3bd5-126">Beispiel 2: Exportieren der Befehle "Get" und "Set"</span><span class="sxs-lookup"><span data-stu-id="e3bd5-126">Example 2: Export the Get and Set commands</span></span>

<span data-ttu-id="e3bd5-127">In diesem Beispiel werden alle `Get` -und- `Set` Befehle von einem Server exportiert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-127">This example exports all of the `Get` and `Set` commands from a server.</span></span>

```powershell
$S = New-PSSession -ConnectionUri https://exchange.microsoft.com/mailbox -Credential exchangeadmin01@hotmail.com -Authentication Negotiate
Export-PSSession -Session $S -Module exch* -CommandName Get-*, Set-* -FormatTypeName * -OutputModule $PSHOME\Modules\Exchange -Encoding ASCII
```

<span data-ttu-id="e3bd5-128">Mit diesen Befehlen werden `Get` die `Set` Befehle und aus einem Microsoft Exchange Server-Snap-in auf einem Remote Computer in ein Exchange-Modul im `$PSHOME\Modules` Verzeichnis auf dem lokalen Computer exportiert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-128">These commands export the `Get` and `Set` commands from a Microsoft Exchange Server snap-in on a remote computer to an Exchange module in the `$PSHOME\Modules` directory on the local computer.</span></span>
<span data-ttu-id="e3bd5-129">Wenn Sie das Modul in das `$PSHOME\Modules` Verzeichnis versetzen, ist es für alle Benutzer des Computers zugänglich.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-129">Placing the module in the `$PSHOME\Modules` directory makes it accessible to all users of the computer.</span></span>

### <span data-ttu-id="e3bd5-130">Beispiel 3: Exportieren von Befehlen von einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="e3bd5-130">Example 3: Export commands from a remote computer</span></span>

<span data-ttu-id="e3bd5-131">In diesem Beispiel werden Cmdlets aus einer PSSession auf einem Remote Computer exportiert und in einem Modul auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-131">This example exports cmdlets from a PSSession on a remote computer and saves them in a module on the local computer.</span></span> <span data-ttu-id="e3bd5-132">Die Cmdlets aus dem Modul werden der aktuellen Sitzung hinzugefügt, sodass Sie verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-132">The cmdlets from the module are added to the current session so that they can be used.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01 -Credential Server01\User01
Export-PSSession -Session $S -OutputModule TestCmdlets -Type Cmdlet -CommandName *test* -FormatTypeName *
Remove-PSSession $S
Import-Module TestCmdlets
Get-Help Test*
Test-Files
```

<span data-ttu-id="e3bd5-133">Der `New-PSSession` Befehl erstellt eine PSSession auf dem Server01-Computer und speichert Sie in der `$S` Variablen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-133">The `New-PSSession` command creates a PSSession on the Server01 computer and saves it in the `$S` variable.</span></span> <span data-ttu-id="e3bd5-134">Der `Export-PSSession` Befehl exportiert die Cmdlets, deren Namen mit "Test" beginnen, aus der PSSession in in `$S` das testcmdlets-Modul auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-134">The `Export-PSSession` command exports the cmdlets whose names begin with Test from the PSSession in `$S` to the TestCmdlets module on the local computer.</span></span>

<span data-ttu-id="e3bd5-135">Das- `Remove-PSSession` Cmdlet löscht die PSSession in `$S` aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-135">The `Remove-PSSession` cmdlet deletes the PSSession in `$S` from the current session.</span></span> <span data-ttu-id="e3bd5-136">Dieser Befehl zeigt, dass die PSSession nicht aktiv sein muss, um die Befehle zu verwenden, die aus der Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-136">This command shows that the PSSession need not be active to use the commands that were imported from the session.</span></span> <span data-ttu-id="e3bd5-137">Mit dem- `Import-Module` Cmdlet werden die Cmdlets im testcmdlets-Modul zur aktuellen Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-137">The `Import-Module` cmdlet adds the cmdlets in the TestCmdlets module to the current session.</span></span> <span data-ttu-id="e3bd5-138">Der Befehl kann jederzeit in einer beliebigen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-138">The command can be run in any session at any time.</span></span>

<span data-ttu-id="e3bd5-139">Das- `Get-Help` Cmdlet ruft Hilfe für Cmdlets ab, deren Namen mit "Test" beginnen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-139">The `Get-Help` cmdlet gets help for cmdlets whose names begin with Test.</span></span> <span data-ttu-id="e3bd5-140">Nachdem die Befehle in einem Modul zur aktuellen Sitzung hinzugefügt wurden, können Sie die `Get-Help` -und- `Get-Command` Cmdlets verwenden, um mehr über die importierten Befehle zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-140">After the commands in a module are added to the current session, you can use the `Get-Help` and `Get-Command` cmdlets to learn about the imported commands.</span></span> <span data-ttu-id="e3bd5-141">Das `Test-Files` Cmdlet wurde vom Server01-Computer exportiert und der Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-141">The `Test-Files` cmdlet was exported from the Server01 computer and added to the session.</span></span> <span data-ttu-id="e3bd5-142">Das- `Test-Files` Cmdlet wird in einer Remote Sitzung auf dem Computer ausgeführt, von dem aus der Befehl importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-142">The `Test-Files` cmdlet runs in a remote session on the computer from which the command was imported.</span></span> <span data-ttu-id="e3bd5-143">PowerShell erstellt eine Sitzung aus Informationen, die im testcmdlets-Modul gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-143">PowerShell creates a session from information that is stored in the TestCmdlets module.</span></span>

### <span data-ttu-id="e3bd5-144">Beispiel 4: Exportieren und Clobber-Befehle in der aktuellen Sitzung</span><span class="sxs-lookup"><span data-stu-id="e3bd5-144">Example 4: Export and clobber commands in the current session</span></span>

<span data-ttu-id="e3bd5-145">In diesem Beispiel werden die in einer Variablen gespeicherten Befehle in die aktuelle Sitzung exportiert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-145">This example exports commands that are stored in a variable into the current session.</span></span>

```powershell
Export-PSSession -Session $S -AllowClobber -OutputModule AllCommands
```

<span data-ttu-id="e3bd5-146">Dieser `Export-PSSession` Befehl exportiert alle Befehle und alle Formatierungsdaten aus der PSSession in der `$S` Variablen in die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-146">This `Export-PSSession` command exports all commands and all formatting data from the PSSession in the `$S` variable into the current session.</span></span> <span data-ttu-id="e3bd5-147">Der **allowclobber** -Parameter enthält Befehle mit denselben Namen wie die Befehle in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-147">The **AllowClobber** parameter includes commands with the same names as commands in the current session.</span></span>

### <span data-ttu-id="e3bd5-148">Beispiel 5: Exportieren von Befehlen aus einer geschlossenen PSSession</span><span class="sxs-lookup"><span data-stu-id="e3bd5-148">Example 5: Export commands from a closed PSSession</span></span>

<span data-ttu-id="e3bd5-149">In diesem Beispiel wird gezeigt, wie die exportierten Befehle mit besonderen Optionen ausgeführt werden, wenn die PSSession, die die exportierten Befehle erstellt hat, geschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-149">This example shows how to run the exported commands with special options when the PSSession that created the exported commands is closed.</span></span>

<span data-ttu-id="e3bd5-150">Wenn die ursprüngliche Remote Sitzung geschlossen wird, wenn ein Modul importiert wird, verwendet das Modul eine beliebige offene Remote Sitzung, die eine Verbindung mit dem ursprünglichen Computer herstellt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-150">If the original remote session is closed when a module is imported, the module will use any open remote session that connects to the originating computer.</span></span> <span data-ttu-id="e3bd5-151">Wenn keine aktuelle Sitzung zum Ursprungs Computer vorhanden ist, wird eine Sitzung vom Modul wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-151">If there is no current session to the originating computer, the module will reestablish a session.</span></span>

<span data-ttu-id="e3bd5-152">Um exportierte Befehle mit speziellen Optionen in einer Remote Sitzung auszuführen, müssen Sie eine Remote Sitzung mit diesen Optionen erstellen, bevor Sie das Modul importieren.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-152">To run exported commands with special options in a remote session, you must create a remote session with those options before you import the module.</span></span> <span data-ttu-id="e3bd5-153">Verwenden des `New-PSSession` Cmdlets mit dem **sessionoption** -Parameter</span><span class="sxs-lookup"><span data-stu-id="e3bd5-153">Use the `New-PSSession` cmdlet with the **SessionOption** parameter</span></span>

```powershell
$Options = New-PSSessionOption -NoMachineProfile
$S = New-PSSession -ComputerName Server01 -SessionOption $Options
Export-PSSession -Session $S -OutputModule Server01
Remove-PSSession $S
New-PSSession -ComputerName Server01 -SessionOption $Options
Import-Module Server01
```

<span data-ttu-id="e3bd5-154">`New-PSSessionOption`Mit dem-Cmdlet wird ein **pssessionoption** -Objekt erstellt, und das-Objekt wird in der `$Options` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-154">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object, and it saves the object in the `$Options` variable.</span></span> <span data-ttu-id="e3bd5-155">Der `New-PSSession` Befehl erstellt eine PSSession auf dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-155">The `New-PSSession` command creates a PSSession on the Server01 computer.</span></span>
<span data-ttu-id="e3bd5-156">Der **sessionoption** -Parameter verwendet das in gespeicherte-Objekt `$Options` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-156">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="e3bd5-157">Die Sitzung wird in der `$S` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-157">The session is stored in the `$S` variable.</span></span>

<span data-ttu-id="e3bd5-158">Mit dem- `Export-PSSession` Cmdlet werden Befehle aus der PSSession in in `$S` das Server01-Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-158">The `Export-PSSession` cmdlet exports commands from the PSSession in `$S` to the Server01 module.</span></span>
<span data-ttu-id="e3bd5-159">Das- `Remove-PSSession` Cmdlet löscht die PSSession in der `$S` Variablen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-159">The `Remove-PSSession` cmdlet deletes the PSSession in the `$S` variable.</span></span>

<span data-ttu-id="e3bd5-160">Das- `New-PSSession` Cmdlet erstellt eine neue PSSession, die eine Verbindung mit dem Server01-Computer herstellt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-160">The `New-PSSession` cmdlet creates a new PSSession that connects to the Server01 computer.</span></span> <span data-ttu-id="e3bd5-161">Der **sessionoption** -Parameter verwendet das in gespeicherte-Objekt `$Options` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-161">The **SessionOption** parameter uses the object stored in `$Options`.</span></span> <span data-ttu-id="e3bd5-162">Mit dem- `Import-Module` Cmdlet werden die Befehle aus dem Server01-Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-162">The `Import-Module` cmdlet imports the commands from the Server01 module.</span></span> <span data-ttu-id="e3bd5-163">Die Befehle im Modul werden in der PSSession auf dem Computer Server01 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-163">The commands in the module are run in the PSSession on the Server01 computer.</span></span>

## <span data-ttu-id="e3bd5-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3bd5-164">PARAMETERS</span></span>

### <span data-ttu-id="e3bd5-165">-Allowclobber</span><span class="sxs-lookup"><span data-stu-id="e3bd5-165">-AllowClobber</span></span>

<span data-ttu-id="e3bd5-166">Exportiert die angegebenen Befehle, auch wenn sie denselben Namen wie die Befehle in der aktuellen Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-166">Exports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="e3bd5-167">Wenn Sie einen Befehl mit demselben Namen wie einen Befehl in der aktuellen Sitzung exportieren, werden die ursprünglichen Befehle durch den exportierten Befehl ausgeblendet oder ersetzt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-167">If you export a command with the same name as a command in the current session, the exported command hides or replaces the original commands.</span></span> <span data-ttu-id="e3bd5-168">Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="e3bd5-168">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-169">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="e3bd5-169">-ArgumentList</span></span>

<span data-ttu-id="e3bd5-170">Exportiert die Variante des Befehls, die sich aus der Verwendung der angegebenen Argumente (Parameterwerte) ergibt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-170">Exports the variant of the command that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="e3bd5-171">So exportieren Sie z. b. die Variante des `Get-Item` Befehls im Zertifikat (CERT:) Geben Sie in die PSSession in ein `$S` , und geben Sie ein `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-171">For example, to export the variant of the `Get-Item` command in the certificate (Cert:) drive in the PSSession in `$S`, type `Export-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-172">-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="e3bd5-172">-Certificate</span></span>

<span data-ttu-id="e3bd5-173">Gibt das Client Zertifikat an, das zum Signieren der Format Dateien (\* .Format.ps1XML) oder Skript Moduldateien (. psm1) im Modul verwendet wird, das von `Export-PSSession` erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-173">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the module that `Export-PSSession` creates.</span></span> <span data-ttu-id="e3bd5-174">Geben Sie eine Variable ein, die ein Zertifikat, einen Befehl oder einen Ausdruck enthält, durch die das Zertifikat abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-174">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="e3bd5-175">Um ein Zertifikat zu suchen, verwenden Sie das `Get-PfxCertificate` Cmdlet, oder verwenden Sie das `Get-ChildItem` Cmdlet im Zertifikat (CERT:). Antrie.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-175">To find a certificate, use the `Get-PfxCertificate` cmdlet or use the `Get-ChildItem` cmdlet in the Certificate (Cert:) drive.</span></span> <span data-ttu-id="e3bd5-176">Wenn das Zertifikat ungültig ist oder keine qualifizierte Zertifizierungsstelle aufweist, verursacht der Befehl einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-176">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-177">-CommandName</span><span class="sxs-lookup"><span data-stu-id="e3bd5-177">-CommandName</span></span>

<span data-ttu-id="e3bd5-178">Exportiert nur die Befehle mit den angegebenen Namen oder Namensmustern.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-178">Exports only the commands with the specified names or name patterns.</span></span> <span data-ttu-id="e3bd5-179">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-179">Wildcards are permitted.</span></span> <span data-ttu-id="e3bd5-180">Verwenden Sie **CommandName** oder den Alias **Name**.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-180">Use **CommandName** or its alias, **Name**.</span></span>

<span data-ttu-id="e3bd5-181">Standardmäßig `Export-PSSession` exportiert alle Befehle aus der PSSession mit Ausnahme von Befehlen, die denselben Namen wie die Befehle in der aktuellen Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-181">By default, `Export-PSSession` exports all commands from the PSSession except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="e3bd5-182">Dadurch wird verhindert, dass Befehle ausgeblendet oder durch Befehle in der aktuellen Sitzung ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-182">This prevents commands from being hidden or replaced by commands in the current session.</span></span> <span data-ttu-id="e3bd5-183">Verwenden Sie den **allowclobber** -Parameter, um alle Befehle zu exportieren, auch solche, die andere Befehle ausblenden oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-183">To export all commands, even those that hide or replace other commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="e3bd5-184">Wenn Sie den **CommandName** -Parameter verwenden, werden die Formatierungs Dateien für die Befehle nicht exportiert, es sei denn, Sie verwenden den **formattypame** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-184">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span> <span data-ttu-id="e3bd5-185">Wenn Sie den **formattypame** -Parameter verwenden, werden auch keine Befehle exportiert, es sei denn, Sie verwenden den **CommandName** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-185">Similarly, if you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="e3bd5-186">-CommandType</span><span class="sxs-lookup"><span data-stu-id="e3bd5-186">-CommandType</span></span>

<span data-ttu-id="e3bd5-187">Exportiert nur die angegebenen Typen von Befehlsobjekten.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-187">Exports only the specified types of command objects.</span></span> <span data-ttu-id="e3bd5-188">Verwenden Sie **CommandType** oder dessen Aliasname **Type**.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-188">Use **CommandType** or its alias, **Type**.</span></span>

<span data-ttu-id="e3bd5-189">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e3bd5-189">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e3bd5-190">Alias.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-190">Alias.</span></span> <span data-ttu-id="e3bd5-191">Alle PowerShell-Aliase in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-191">All PowerShell aliases in the current session.</span></span>
- <span data-ttu-id="e3bd5-192">Alle</span><span class="sxs-lookup"><span data-stu-id="e3bd5-192">All.</span></span> <span data-ttu-id="e3bd5-193">Alle Befehlstypen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-193">All command types.</span></span> <span data-ttu-id="e3bd5-194">Dies entspricht `Get-Command -Name *` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-194">It is the equivalent of `Get-Command -Name *`.</span></span>
- <span data-ttu-id="e3bd5-195">Anwendung:</span><span class="sxs-lookup"><span data-stu-id="e3bd5-195">Application.</span></span> <span data-ttu-id="e3bd5-196">Alle anderen Dateien als PowerShell-Dateien in Pfaden, die in der PATH-Umgebungsvariablen ( `$env:path` ) aufgelistet sind, einschließlich txt-, exe-und dll-Dateien.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-196">All files other than PowerShell files in paths listed in the Path environment variable (`$env:path`), including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="e3bd5-197">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-197">Cmdlet.</span></span> <span data-ttu-id="e3bd5-198">Die Cmdlets in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-198">The cmdlets in the current session.</span></span> <span data-ttu-id="e3bd5-199">Das-Cmdlet ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-199">Cmdlet is the default.</span></span>
- <span data-ttu-id="e3bd5-200">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e3bd5-200">Configuration.</span></span> <span data-ttu-id="e3bd5-201">Eine PowerShell-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-201">A PowerShell configuration.</span></span> <span data-ttu-id="e3bd5-202">Weitere Informationen finden Sie unter [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="e3bd5-202">For more information, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>
- <span data-ttu-id="e3bd5-203">Externalscript.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-203">ExternalScript.</span></span> <span data-ttu-id="e3bd5-204">Alle PS1-Dateien in den Pfaden, die in der PATH-Umgebungsvariablen () aufgelistet sind `$env:path` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-204">All .ps1 files in the paths listed in the Path environment variable (`$env:path`).</span></span>
- <span data-ttu-id="e3bd5-205">Filter und function.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-205">Filter and Function.</span></span> <span data-ttu-id="e3bd5-206">Alle PowerShell-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-206">All PowerShell functions.</span></span>
- <span data-ttu-id="e3bd5-207">Skript.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-207">Script.</span></span> <span data-ttu-id="e3bd5-208">Skriptblöcke in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-208">Script blocks in the current session.</span></span>
- <span data-ttu-id="e3bd5-209">Workflow.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-209">Workflow.</span></span> <span data-ttu-id="e3bd5-210">Einen PowerShell-Workflow.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-210">A PowerShell workflow.</span></span> <span data-ttu-id="e3bd5-211">Weitere Informationen finden Sie unter [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span><span class="sxs-lookup"><span data-stu-id="e3bd5-211">For more information, see [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, All, Application, Cmdlet, Configuration, ExternalScript, Filter, Function, Script, Workflow

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-212">-Codierung</span><span class="sxs-lookup"><span data-stu-id="e3bd5-212">-Encoding</span></span>

<span data-ttu-id="e3bd5-213">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-213">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="e3bd5-214">Standardwert: `UTF8`.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-214">The default value is `UTF8`.</span></span>

<span data-ttu-id="e3bd5-215">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e3bd5-215">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e3bd5-216">`ASCII` Verwendet den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="e3bd5-216">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="e3bd5-217">`BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-217">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="e3bd5-218">`Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-218">`Default` Uses the encoding that corresponds to the system's active code page.</span></span>
- <span data-ttu-id="e3bd5-219">`OEM` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-219">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="e3bd5-220">`Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-220">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="e3bd5-221">`UTF7` Verwendet UTF-7.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-221">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="e3bd5-222">`UTF8` Verwendet UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-222">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="e3bd5-223">`UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-223">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: UTF8
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-224">-Force</span><span class="sxs-lookup"><span data-stu-id="e3bd5-224">-Force</span></span>

<span data-ttu-id="e3bd5-225">Überschreibt eine oder mehrere vorhandene Ausgabedateien, auch wenn die Datei das Schreibschutzattribut aufweist.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-225">Overwrites one or more existing output files, even if the file has the read-only attribute.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-226">-Formattyname</span><span class="sxs-lookup"><span data-stu-id="e3bd5-226">-FormatTypeName</span></span>

<span data-ttu-id="e3bd5-227">Exportiert Formatierungsanweisungen nur für die angegebenen Microsoft .NET Framework-Typen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-227">Exports formatting instructions only for the specified Microsoft .NET Framework types.</span></span> <span data-ttu-id="e3bd5-228">Geben Sie die Typnamen ein.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-228">Enter the type names.</span></span> <span data-ttu-id="e3bd5-229">Standardmäßig `Export-PSSession` exportiert Formatierungs Anweisungen für alle .NET Framework Typen, die nicht im **System. Management. Automation** -Namespace sind.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-229">By default, `Export-PSSession` exports formatting instructions for all .NET Framework types that are not in the **System.Management.Automation** namespace.</span></span>

<span data-ttu-id="e3bd5-230">Der Wert dieses Parameters muss dem Namen eines Typs entsprechen, der von einem `Get-FormatData` Befehl in der Sitzung zurückgegeben wird, aus der die Befehle importiert werden.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-230">The value of this parameter must be the name of a type that is returned by a `Get-FormatData` command in the session from which the commands are being imported.</span></span> <span data-ttu-id="e3bd5-231">Um alle Formatierungsdaten in der Remote Sitzung zu erhalten, geben Sie ein `*` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-231">To get all of the formatting data in the remote session, type `*`.</span></span>

<span data-ttu-id="e3bd5-232">Wenn Sie den **formattypame** -Parameter verwenden, werden keine Befehle exportiert, es sei denn, Sie verwenden den **CommandName** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-232">If you use the **FormatTypeName** parameter, no commands are exported unless you use the **CommandName** parameter.</span></span>

<span data-ttu-id="e3bd5-233">Wenn Sie den **CommandName** -Parameter verwenden, werden die Formatierungs Dateien für die Befehle nicht exportiert, es sei denn, Sie verwenden den **formattypame** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-233">If you use the **CommandName** parameter, the formatting files for the commands are not exported unless you use the **FormatTypeName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-234">-Fullyqualifiedmodule</span><span class="sxs-lookup"><span data-stu-id="e3bd5-234">-FullyQualifiedModule</span></span>

<span data-ttu-id="e3bd5-235">Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-235">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="e3bd5-236">Weitere Informationen finden Sie im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="e3bd5-236">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="e3bd5-237">Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der in einem der folgenden Formate angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="e3bd5-237">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="e3bd5-238">**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-238">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="e3bd5-239">Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-239">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="e3bd5-240">die beiden Parameter schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-240">the two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-241">-Modul</span><span class="sxs-lookup"><span data-stu-id="e3bd5-241">-Module</span></span>

<span data-ttu-id="e3bd5-242">Exportiert nur die Befehle in den angegebenen PowerShell-Snap-Ins und-Modulen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-242">Exports only the commands in the specified PowerShell snap-ins and modules.</span></span> <span data-ttu-id="e3bd5-243">Geben Sie die Snap-In- und Modulnamen ein.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-243">Enter the snap-in and module names.</span></span> <span data-ttu-id="e3bd5-244">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-244">Wildcards are not permitted.</span></span>

<span data-ttu-id="e3bd5-245">Weitere Informationen finden Sie unter `Import-Module` und [about_PSSnapins](../Microsoft.PowerShell.Core/About/about_PSSnapins.md).</span><span class="sxs-lookup"><span data-stu-id="e3bd5-245">For more information, see `Import-Module` and [about_PSSnapins](../Microsoft.PowerShell.Core/About/about_PSSnapins.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: All commands in the session.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-246">-Outputmodule</span><span class="sxs-lookup"><span data-stu-id="e3bd5-246">-OutputModule</span></span>

<span data-ttu-id="e3bd5-247">Gibt einen optionalen Pfad und Namen für das Modul an, das von erstellt wird `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-247">Specifies an optional path and name for the module created by `Export-PSSession`.</span></span> <span data-ttu-id="e3bd5-248">Der Standardpfad lautet `$home\Documents\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-248">The default path is `$home\Documents\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="e3bd5-249">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-249">This parameter is required.</span></span>

<span data-ttu-id="e3bd5-250">Wenn das Modul Unterverzeichnis oder eine der erstellten Dateien `Export-PSSession` bereits vorhanden ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-250">If the module subdirectory or any of the files that `Export-PSSession` creates already exist, the command fails.</span></span> <span data-ttu-id="e3bd5-251">Um vorhandene Dateien zu überschreiben, verwenden Sie den **Force** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-251">To overwrite existing files, use the **Force** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, ModuleName

Required: True
Position: 1
Default value: $home\Documents\WindowsPowerShell\Modules
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-252">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="e3bd5-252">-Session</span></span>

<span data-ttu-id="e3bd5-253">Gibt die PSSession an, aus der die Befehle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-253">Specifies the PSSession from which the commands are exported.</span></span> <span data-ttu-id="e3bd5-254">Geben Sie eine Variable ein, die ein Sitzungs Objekt oder einen Befehl zum Abrufen eines Sitzungs Objekts enthält, z. b. einen- `Get-PSSession` Befehl.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-254">Enter a variable that contains a session object or a command that gets a session object, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="e3bd5-255">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-255">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3bd5-256">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e3bd5-256">CommonParameters</span></span>

<span data-ttu-id="e3bd5-257">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3bd5-258">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e3bd5-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3bd5-259">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e3bd5-259">INPUTS</span></span>

### <span data-ttu-id="e3bd5-260">Keine</span><span class="sxs-lookup"><span data-stu-id="e3bd5-260">None</span></span>

<span data-ttu-id="e3bd5-261">Objekte können nicht an übergeben werden `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-261">You cannot pipe objects to `Export-PSSession`.</span></span>

## <span data-ttu-id="e3bd5-262">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e3bd5-262">OUTPUTS</span></span>

### <span data-ttu-id="e3bd5-263">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="e3bd5-263">System.IO.FileInfo</span></span>

<span data-ttu-id="e3bd5-264">`Export-PSSession` gibt eine Liste der Dateien zurück, die das Modul enthalten, das es erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-264">`Export-PSSession` returns a list of files that comprise the module that it created.</span></span>

## <span data-ttu-id="e3bd5-265">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e3bd5-265">NOTES</span></span>

<span data-ttu-id="e3bd5-266">`Export-PSSession` basiert auf der PowerShell-Remoting-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-266">`Export-PSSession` relies on the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="e3bd5-267">Um dieses Cmdlet zu verwenden, muss der Computer für Remoting konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-267">To use this cmdlet, the computer must be configured for remoting.</span></span> <span data-ttu-id="e3bd5-268">Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3bd5-268">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="e3bd5-269">Sie können nicht verwenden `Export-PSSession` , um einen PowerShell-Anbieter zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-269">You cannot use `Export-PSSession` to export a PowerShell provider.</span></span>

<span data-ttu-id="e3bd5-270">Exportierte Befehle werden implizit in der PSSession ausgeführt, aus der sie exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-270">Exported commands run implicitly in the PSSession from which they were exported.</span></span> <span data-ttu-id="e3bd5-271">Die Details der Remote Ausführung der Befehle werden vollständig von PowerShell verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-271">The details of running the commands remotely are handled entirely by PowerShell.</span></span> <span data-ttu-id="e3bd5-272">Sie können die exportierten Befehle genau so ausführen, wie Sie lokale Befehle ausführen würden.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-272">You can run the exported commands just as you would run local commands.</span></span>

<span data-ttu-id="e3bd5-273">`Export-ModuleMember` erfasst und speichert Informationen über die PSSession im Modul, das exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-273">`Export-ModuleMember` captures and saves information about the PSSession in the module that it exports.</span></span> <span data-ttu-id="e3bd5-274">Wenn die PSSession, von der die Befehle exportiert wurden, beim Importieren des Moduls geschlossen wird, und keine aktiven pssessions auf dem gleichen Computer vorhanden sind, versuchen die Befehle im Modul, die PSSession neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-274">If the PSSession from which the commands were exported is closed when you import the module, and there are no active PSSessions to the same computer, the commands in the module attempt to recreate the PSSession.</span></span> <span data-ttu-id="e3bd5-275">Wenn Versuche, die PSSession neu zu erstellen, fehlschlagen, werden die exportierten Befehle nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-275">If attempts to recreate the PSSession fail, the exported commands will not run.</span></span>

<span data-ttu-id="e3bd5-276">Die Sitzungsinformationen, die `Export-ModuleMember` im Modul erfasst und gespeichert werden, beinhalten keine Sitzungs Optionen, wie z. b. diejenigen, die Sie in der Einstellungs `$PSSessionOption` Variablen oder mithilfe des **sessionoption** -Parameters der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder angeben.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-276">The session information that `Export-ModuleMember` captures and saves in the module does not include session options, such as those that you specify in the `$PSSessionOption` preference variable or by using the **SessionOption** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span> <span data-ttu-id="e3bd5-277">Wenn die ursprüngliche PSSession geschlossen ist, wenn Sie das Modul importieren, verwendet das Modul eine andere PSSession auf dem gleichen Computer, falls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-277">If the original PSSession is closed when you import the module, the module will use another PSSession to the same computer, if one is available.</span></span> <span data-ttu-id="e3bd5-278">Damit die importierten Befehle in einer korrekt konfigurierten Sitzung ausgeführt werden können, erstellen Sie eine PSSession mit den gewünschten Optionen, bevor Sie das Modul importieren.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-278">To enable the imported commands to run in a correctly configured session, create a PSSession with the options that you want before you import the module.</span></span>

<span data-ttu-id="e3bd5-279">Zum Suchen der zu exportierenden Befehle `Export-PSSession` verwendet das `Invoke-Command` Cmdlet, um einen `Get-Command` Befehl in der PSSession auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-279">To find the commands to export, `Export-PSSession` uses the `Invoke-Command` cmdlet to run a `Get-Command` command in the PSSession.</span></span> <span data-ttu-id="e3bd5-280">Um Formatierungsdaten für die Befehle zu erhalten und zu speichern, werden die `Get-FormatData` -und- `Export-FormatData` Cmdlets verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-280">To get and save formatting data for the commands, it uses the `Get-FormatData` and `Export-FormatData` cmdlets.</span></span> <span data-ttu-id="e3bd5-281">Möglicherweise werden Fehlermeldungen von `Invoke-Command` , `Get-Command` , `Get-FormatData` und angezeigt, `Export-FormatData` Wenn Sie einen- `Export-PSSession` Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-281">You might see error messages from `Invoke-Command`, `Get-Command`, `Get-FormatData`, and `Export-FormatData` when you run an `Export-PSSession` command.</span></span> <span data-ttu-id="e3bd5-282">Kann auch keine `Export-PSSession` Befehle aus einer Sitzung exportieren, die nicht die `Get-Command` `Get-FormatData` `Select-Object` Cmdlets,, und enthält `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-282">Also, `Export-PSSession` cannot export commands from a session that does not include the `Get-Command`, `Get-FormatData`, `Select-Object`, and `Get-Help` cmdlets.</span></span>

<span data-ttu-id="e3bd5-283">`Export-PSSession` verwendet das `Write-Progress` Cmdlet, um den Fortschritt des Befehls anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-283">`Export-PSSession` uses the `Write-Progress` cmdlet to display the progress of the command.</span></span> <span data-ttu-id="e3bd5-284">Während der Befehlsausführung wird u. U. die Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-284">You might see the progress bar while the command is running.</span></span>

<span data-ttu-id="e3bd5-285">Exportierte Befehle unterliegen denselben Einschränkungen wie andere Remotebefehle, z. B. die Unfähigkeit, ein Programm mit einer Benutzeroberfläche, wie z. B. Editor, zu starten.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-285">Exported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>

<span data-ttu-id="e3bd5-286">Da PowerShell-Profile nicht in pssessions ausgeführt werden, stehen die Befehle, die ein Profil einer Sitzung hinzufügt, nicht für zur Verfügung `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="e3bd5-286">Because PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to `Export-PSSession`.</span></span> <span data-ttu-id="e3bd5-287">Um Befehle aus einem Profil zu exportieren, verwenden `Invoke-Command` Sie einen Befehl, um das Profil manuell in der PSSession auszuführen, bevor Sie Befehle exportieren.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-287">To export commands from a profile, use an `Invoke-Command` command to run the profile in the PSSession manually before exporting commands.</span></span>

<span data-ttu-id="e3bd5-288">Das Modul, das `Export-PSSession` erstellt, kann eine Formatierungs Datei enthalten, auch wenn der Befehl keine Formatierungsdaten importiert.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-288">The module that `Export-PSSession` creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="e3bd5-289">Wenn durch den Befehl keine Formatierungsdaten importiert werden, enthält keine der erstellten Formatierungsdateien Formatierungsdaten.</span><span class="sxs-lookup"><span data-stu-id="e3bd5-289">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>

## <span data-ttu-id="e3bd5-290">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e3bd5-290">RELATED LINKS</span></span>

[<span data-ttu-id="e3bd5-291">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="e3bd5-291">about_Command_Precedence</span></span>](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)

[<span data-ttu-id="e3bd5-292">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="e3bd5-292">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="e3bd5-293">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="e3bd5-293">about_PSSnapins</span></span>](../Microsoft.PowerShell.Core/About/about_PSSnapins.md)

[<span data-ttu-id="e3bd5-294">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="e3bd5-294">about_Remote_Requirements</span></span>](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)

[<span data-ttu-id="e3bd5-295">Import-Module</span><span class="sxs-lookup"><span data-stu-id="e3bd5-295">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="e3bd5-296">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="e3bd5-296">Import-PSSession</span></span>](Import-PSSession.md)

[<span data-ttu-id="e3bd5-297">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="e3bd5-297">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="e3bd5-298">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="e3bd5-298">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="e3bd5-299">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="e3bd5-299">New-PSSessionOption</span></span>](../Microsoft.PowerShell.Core/New-PSSessionOption.md)

[<span data-ttu-id="e3bd5-300">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="e3bd5-300">Remove-PSSession</span></span>](../Microsoft.PowerShell.Core/Remove-PSSession.md)
