---
title: Hinzufügen von Unterstützung für Anmeldeinformationen zu PowerShell-Funktionen
description: Erfahren Sie, wie Sie Ihren PowerShell-Skripts, -Funktionen und -Cmdlets Parameter mit Anmeldeinformationen hinzufügen.
ms.date: 10/29/2020
ms.custom: contributor-JoshDuffney
ms.openlocfilehash: fb85d47121dc106ae04742254f418e2c727f6157
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143157"
---
# <a name="add-credential-support-to-powershell-functions"></a><span data-ttu-id="945ac-103">Hinzufügen von Unterstützung für Anmeldeinformationen zu PowerShell-Funktionen</span><span class="sxs-lookup"><span data-stu-id="945ac-103">Add Credential support to PowerShell functions</span></span>

> [!NOTE]
> <span data-ttu-id="945ac-104">Die [Originalversion][] dieses Artikels ist im Blog von [@joshduffney][] erschienen.</span><span class="sxs-lookup"><span data-stu-id="945ac-104">The [original version][] of this article appeared on the blog written by [@joshduffney][].</span></span> <span data-ttu-id="945ac-105">Dieser Artikel wurde für die Einbindung in diese Website bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="945ac-105">This article has been edited for inclusion on this site.</span></span> <span data-ttu-id="945ac-106">Das PowerShell-Team dankt Josh Duffney, dass er uns diesen Inhalt zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="945ac-106">The PowerShell team thanks Josh for sharing this content with us.</span></span> <span data-ttu-id="945ac-107">Weitere Informationen finden Sie in seinem Blog unter [duffney.io][].</span><span class="sxs-lookup"><span data-stu-id="945ac-107">Please check out his blog at [duffney.io][].</span></span>

<span data-ttu-id="945ac-108">In diesem Artikel erfahren Sie, wie Sie PowerShell-Funktionen Parameter mit Anmeldeinformationen hinzufügen und warum dies gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="945ac-108">This article shows you how to add credential parameters to PowerShell functions and why you'd want to.</span></span> <span data-ttu-id="945ac-109">Mit einem Parameter mit Anmeldeinformationen können Sie die Funktion oder das Cmdlet als ein anderer Benutzer ausführen.</span><span class="sxs-lookup"><span data-stu-id="945ac-109">A credential parameter is to allow you to run the function or cmdlet as a different user.</span></span> <span data-ttu-id="945ac-110">Der häufigste Zweck ist das Ausführen der Funktion oder des Cmdlets mit einem Benutzerkonto mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="945ac-110">The most common use is to run the function or cmdlet as an elevated user account.</span></span>

<span data-ttu-id="945ac-111">Beispielsweise verfügt das Cmdlet `New-ADUser` über den Parameter **Credential** , mit dem Sie Anmeldeinformationen eines Domänenadministrators bereitstellen können, um in einer Domäne ein Konto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="945ac-111">For example, the cmdlet `New-ADUser` has a **Credential** parameter, which you could provide domain admin credentials to create an account in a domain.</span></span> <span data-ttu-id="945ac-112">Es wird angenommen, dass Ihr normales Konto, mit dem die PowerShell-Sitzung ausgeführt wird, nicht bereits über diesen Zugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="945ac-112">Assuming your normal account running the PowerShell session doesn't have that access already.</span></span>

## <a name="creating-credential-object"></a><span data-ttu-id="945ac-113">Erstellen des Objekts mit Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="945ac-113">Creating credential object</span></span>

<span data-ttu-id="945ac-114">Das Objekt [PSCredential][] stellt sicherheitsrelevante Anmeldeinformationen wie einen Benutzernamen und ein Kennwort dar.</span><span class="sxs-lookup"><span data-stu-id="945ac-114">The [PSCredential][] object represents a set of security credentials such as a user name and password.</span></span> <span data-ttu-id="945ac-115">Das Objekt kann als Parameter an eine Funktion übergeben werden, die in diesem Objekt mit Anmeldeinformationen mit dem entsprechenden Benutzerkonto ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="945ac-115">The object can be passed as a parameter to a function that runs as the user account in that credential object.</span></span> <span data-ttu-id="945ac-116">Es gibt mehrere Möglichkeiten, ein Objekt mit Anmeldeinformationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="945ac-116">There are a few ways that you can create a credential object.</span></span> <span data-ttu-id="945ac-117">Die erste ist das PowerShell-Cmdlet `Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="945ac-117">The first way to create a credential object is to use the PowerShell cmdlet `Get-Credential`.</span></span> <span data-ttu-id="945ac-118">Wenn Sie es ohne Parameter ausführen, werden Sie aufgefordert, einen Benutzernamen und ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="945ac-118">When you run without parameters, it prompts you for a username and password.</span></span> <span data-ttu-id="945ac-119">Oder Sie können das Cmdlet mit optionalen Parametern aufrufen.</span><span class="sxs-lookup"><span data-stu-id="945ac-119">Or you can call the cmdlet with some optional parameters.</span></span>

<span data-ttu-id="945ac-120">Um den Domänennamen und den Benutzernamen im Voraus anzugeben, können Sie entweder den Parameter **Credential** oder den Parameter **UserName** verwenden.</span><span class="sxs-lookup"><span data-stu-id="945ac-120">To specify the domain name and username ahead of time you can use either the **Credential** or **UserName** parameters.</span></span> <span data-ttu-id="945ac-121">Beim Parameter **UserName** müssen Sie auch einen Wert für **Message** angeben.</span><span class="sxs-lookup"><span data-stu-id="945ac-121">When you use the **UserName** parameter, you're also required to provide a **Message** value.</span></span> <span data-ttu-id="945ac-122">Der folgende Code veranschaulicht die Verwendung des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="945ac-122">The code below demonstrates using the cmdlet.</span></span> <span data-ttu-id="945ac-123">Sie können das Objekt mit Anmeldeinformationen auch in einer Variablen speichern, damit Sie diese mehrmals verwenden können.</span><span class="sxs-lookup"><span data-stu-id="945ac-123">You can also store the credential object in a variable so that you can use the credential multiple times.</span></span> <span data-ttu-id="945ac-124">Im folgenden Beispiel wird das Objekt mit Anmeldeinformationen in der Variablen `$Cred`gespeichert.</span><span class="sxs-lookup"><span data-stu-id="945ac-124">In the example below, the credential object is stored in the variable `$Cred`.</span></span>

```powershell
$Cred = Get-Credential
$Cred = Get-Credential -Credential domain\user
$Cred = Get-Credential -UserName domain\user -Message 'Enter Password'
```

<span data-ttu-id="945ac-125">Mitunter ist es nicht möglich, die im vorherigen Beispiel gezeigte interaktive Methode zum Erstellen von Objekten mit Anmeldeinformationen einzusetzen.</span><span class="sxs-lookup"><span data-stu-id="945ac-125">Sometimes, you can't use the interactive method of creating credential objects shown in the previous example.</span></span> <span data-ttu-id="945ac-126">Die meisten Automatisierungstools erfordern eine nicht interaktive Methode.</span><span class="sxs-lookup"><span data-stu-id="945ac-126">Most automation tools require a non-interactive method.</span></span> <span data-ttu-id="945ac-127">Erstellen Sie eine sichere Zeichenfolge mit dem Kennwort, um Anmeldeinformationen ohne Interaktion mit dem Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="945ac-127">To create a credential without user interaction, create a secure string containing the password.</span></span> <span data-ttu-id="945ac-128">Übergeben Sie dann die sichere Zeichenfolge und den Benutzernamen an die `System.Management.Automation.PSCredential()`-Methode.</span><span class="sxs-lookup"><span data-stu-id="945ac-128">Then pass the secure string and user name to the `System.Management.Automation.PSCredential()` method.</span></span>

<span data-ttu-id="945ac-129">Erstellen Sie mit dem folgenden Befehl eine sichere Zeichenfolge mit dem Kennwort:</span><span class="sxs-lookup"><span data-stu-id="945ac-129">Use the following command to create a secure string containing the password:</span></span>

```powershell
ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
```

<span data-ttu-id="945ac-130">**AsPlainText** und **Force** sind Pflichtparameter.</span><span class="sxs-lookup"><span data-stu-id="945ac-130">Both the **AsPlainText** and **Force** parameters are required.</span></span> <span data-ttu-id="945ac-131">Ohne diese Parameter erhalten Sie eine Warnmeldung, dass Sie keinen Klartext in eine sichere Zeichenfolge eingeben dürfen.</span><span class="sxs-lookup"><span data-stu-id="945ac-131">Without those parameters, you receive a message warning that you shouldn't pass plain text into a secure string.</span></span> <span data-ttu-id="945ac-132">PowerShell gibt diese Warnung zurück, da das Kennwort im Klartext in verschiedenen Protokollen aufgezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="945ac-132">PowerShell returns this warning because the plain text password gets recorded in various logs.</span></span> <span data-ttu-id="945ac-133">Nachdem Sie eine sichere Zeichenfolge erstellt haben, müssen Sie sie an die `PSCredential()`-Methode übergeben, um das Objekt für Anmeldeinformationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="945ac-133">Once you have a secure string created, you need to pass it to the `PSCredential()` method to create the credential object.</span></span> <span data-ttu-id="945ac-134">Im folgenden Beispiel enthält die Variable `$password` die sichere Zeichenfolge `$Cred` mit dem Objekt mit Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="945ac-134">In the following example, the variable `$password` contains the secure string `$Cred` contains the credential object.</span></span>

```powershell
$password = ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("username", $password)
```

<span data-ttu-id="945ac-135">Nachdem Sie nun wissen, wie Objekte mit Anmeldeinformationen erstellt werden, können Sie Ihren PowerShell-Funktionen Parameter mit Anmeldeinformationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="945ac-135">Now that you know how to create credential objects, you can add credential parameters to your PowerShell functions.</span></span>

## <a name="adding-a-credential-parameter"></a><span data-ttu-id="945ac-136">Hinzufügen eines Parameters mit Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="945ac-136">Adding a Credential Parameter</span></span>

<span data-ttu-id="945ac-137">Wie bei jedem anderen Parameter beginnen Sie, indem Sie ihn dem Block `param` Ihrer Funktion hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="945ac-137">Just like any other parameter, you start off by adding it in the `param` block of your function.</span></span>
<span data-ttu-id="945ac-138">Es wird empfohlen, den Parameter `$Credential` zu nennen, weil dieser von vorhandenen PowerShell-Cmdlets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="945ac-138">It's recommended that you name the parameter `$Credential` because that's what existing PowerShell cmdlets use.</span></span> <span data-ttu-id="945ac-139">Der Typ des Parameters muss `[System.Management.Automation.PSCredential]` sein.</span><span class="sxs-lookup"><span data-stu-id="945ac-139">The type of the parameter should be `[System.Management.Automation.PSCredential]`.</span></span>

<span data-ttu-id="945ac-140">Das folgende Beispiel zeigt den Parameterblock für eine Funktion mit dem Namen `Get-Something`.</span><span class="sxs-lookup"><span data-stu-id="945ac-140">The following example shows the parameter block for a function called `Get-Something`.</span></span> <span data-ttu-id="945ac-141">Sie hat zwei Parameter: `$Name` und `$Credential`.</span><span class="sxs-lookup"><span data-stu-id="945ac-141">It has two parameters: `$Name` and `$Credential`.</span></span>

```powershell
function Get-Something {
    param(
        $Name,
        [System.Management.Automation.PSCredential]$Credential
    )
```

<span data-ttu-id="945ac-142">Der Code in diesem Beispiel reicht für einen funktionierenden Parameter mit Anmeldeinformationen aus. Es gibt jedoch ein paar Dinge, die Sie hinzufügen können, um ihn stabiler zu machen.</span><span class="sxs-lookup"><span data-stu-id="945ac-142">The code in this example is enough to have a working credential parameter, however there are a few things you can add to make it more robust.</span></span>

- <span data-ttu-id="945ac-143">Fügen Sie das Überprüfungsattribut `[ValidateNotNull()]` hinzu, um zu prüfen, ob der Wert an **Credential** übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="945ac-143">Add the `[ValidateNotNull()]` validation attribute to check that the value being passed to **Credential**.</span></span> <span data-ttu-id="945ac-144">Wenn der Parameterwert NULL ist, verhindert dieses Attribut die Ausführung der Funktion mit ungültigen Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="945ac-144">If the parameter value is null, this attribute prevents the function from executing with invalid credentials.</span></span>

- <span data-ttu-id="945ac-145">Fügen Sie `[System.Management.Automation.Credential()]` hinzu.</span><span class="sxs-lookup"><span data-stu-id="945ac-145">Add `[System.Management.Automation.Credential()]`.</span></span> <span data-ttu-id="945ac-146">Dies ermöglicht Ihnen die Eingabe eines Benutzernamens als Zeichenfolge und eine interaktive Abfrage des Kennworts.</span><span class="sxs-lookup"><span data-stu-id="945ac-146">This allows you to pass in a username as a string and have an interactive prompt for the password.</span></span>

- <span data-ttu-id="945ac-147">Legen Sie den Standardwert des Parameters `$Credential` auf `[System.Management.Automation.PSCredential]::Empty` fest.</span><span class="sxs-lookup"><span data-stu-id="945ac-147">Set a default value for the `$Credential` parameter to `[System.Management.Automation.PSCredential]::Empty`.</span></span> <span data-ttu-id="945ac-148">Ihre Funktion übergibt dieses `$Credential`-Objekt möglicherweise an vorhandene PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="945ac-148">Your function you might be passing this `$Credential` object to existing PowerShell cmdlets.</span></span> <span data-ttu-id="945ac-149">Das Angeben eines NULL-Werts für das Cmdlet, das in Ihrer Funktion aufgerufen wird, verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="945ac-149">Providing a null value to the cmdlet called inside your function causes an error.</span></span> <span data-ttu-id="945ac-150">Durch Angeben eines leeren Objekts mit Anmeldeinformationen wird dieser Fehler vermieden.</span><span class="sxs-lookup"><span data-stu-id="945ac-150">Providing an empty credential object avoids this error.</span></span>

> [!TIP]
> <span data-ttu-id="945ac-151">Einige Cmdlets, die einen Parameter mit Anmeldeinformationen akzeptieren, unterstützen `[System.Management.Automation.PSCredential]::Empty` nicht.</span><span class="sxs-lookup"><span data-stu-id="945ac-151">Some cmdlets that accept a credential parameter do not support `[System.Management.Automation.PSCredential]::Empty` as they should.</span></span> <span data-ttu-id="945ac-152">Eine Problemumgehung finden Sie im Abschnitt [Umgang mit Legacy-Cmdlets](#dealing-with-legacy-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="945ac-152">See the [Dealing with Legacy Cmdlets](#dealing-with-legacy-cmdlets) section for a workaround.</span></span>

## <a name="using-credential-parameters"></a><span data-ttu-id="945ac-153">Verwenden von Parametern mit Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="945ac-153">Using credential parameters</span></span>

<span data-ttu-id="945ac-154">Im folgenden Beispiel wird die Verwendung von Parametern mit Anmeldeinformationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="945ac-154">The following example demonstrates how to use credential parameters.</span></span> <span data-ttu-id="945ac-155">Dieses Beispiel zeigt eine Funktion mit dem Namen `Set-RemoteRegistryValue`, die aus [The Pester Book][] stammt.</span><span class="sxs-lookup"><span data-stu-id="945ac-155">This example shows a function called `Set-RemoteRegistryValue`, which is out of [The Pester Book][].</span></span> <span data-ttu-id="945ac-156">Diese Funktion definiert den Parameter mit Anmeldeinformationen mithilfe der im vorherigen Abschnitt beschriebenen Techniken.</span><span class="sxs-lookup"><span data-stu-id="945ac-156">This function defines the credential parameter using the techniques describe in the previous section.</span></span> <span data-ttu-id="945ac-157">Die Funktion ruft `Invoke-Command` mithilfe der Variablen `$Credential` auf, die von der Funktion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="945ac-157">The function calls `Invoke-Command` using the `$Credential` variable created by the function.</span></span> <span data-ttu-id="945ac-158">Dies ermöglicht Ihnen das Ändern des Benutzers, der `Invoke-Command` ausführt.</span><span class="sxs-lookup"><span data-stu-id="945ac-158">This allows you to change the user who's running `Invoke-Command`.</span></span> <span data-ttu-id="945ac-159">Da der Standardwert von `$Credential` leere Anmeldeinformationen sind, kann die Funktion ohne Angabe von Anmeldeinformationen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="945ac-159">Because the default value of `$Credential` is an empty credential, the function can run without providing credentials.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )
        $null = Invoke-Command -ComputerName $ComputerName -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } -Credential $Credential
}
```

<span data-ttu-id="945ac-160">In den folgenden Abschnitten werden verschiedene Methoden zum Bereitstellen von Anmeldeinformationen für `Set-RemoteRegistryValue` erläutert.</span><span class="sxs-lookup"><span data-stu-id="945ac-160">The following sections show different methods of providing credentials to `Set-RemoteRegistryValue`.</span></span>

### <a name="prompting-for-credentials"></a><span data-ttu-id="945ac-161">Anfordern von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="945ac-161">Prompting for credentials</span></span>

<span data-ttu-id="945ac-162">Die Verwendung von `Get-Credential` in Klammern `()` zur Laufzeit bewirkt, dass `Get-credential` zuerst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="945ac-162">Using `Get-Credential` in parentheses `()` at run time causes the `Get-credential` to run first.</span></span> <span data-ttu-id="945ac-163">Sie werden aufgefordert, einen Benutzernamen und ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="945ac-163">You are prompted for a username and password.</span></span> <span data-ttu-id="945ac-164">Sie könnten die Parameter **Credential** oder **UserName** von `Get-credential` verwenden, um den Benutzernamen und die Domäne vorab auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="945ac-164">You could use the **Credential** or **UserName** parameters of `Get-credential` to pre-populate the username and domain.</span></span> <span data-ttu-id="945ac-165">Im folgenden Beispiel wird eine Technik namens „Splatting“ verwendet, um Parameter an die `Set-RemoteRegistryValue`-Funktion zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="945ac-165">The following example uses a technique called splatting to pass parameters to the `Set-RemoteRegistryValue` function.</span></span> <span data-ttu-id="945ac-166">Weitere Informationen zu Splatting finden Sie im Artikel [about_Splatting][].</span><span class="sxs-lookup"><span data-stu-id="945ac-166">For more information about splatting, check out the [about_Splatting][] article.</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential (Get-Credential)
```

![Abrufen von Anmeldeinformationen zur Laufzeit](./media/add-credentials-to-powershell-functions/GetCredAtRunTime.gif)

<span data-ttu-id="945ac-168">Die Verwendung von `(Get-Credential)` scheint umständlich.</span><span class="sxs-lookup"><span data-stu-id="945ac-168">Using `(Get-Credential)` seems cumbersome.</span></span> <span data-ttu-id="945ac-169">Wenn Sie den Parameter **Credential** nur mit einem Benutzernamen verwenden, fordert das Cmdlet normalerweise automatisch zur Eingabe des Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="945ac-169">Normally, when you use the **Credential** parameter with only a username, the cmdlet automatically prompts for the password.</span></span> <span data-ttu-id="945ac-170">Das Attribut `[System.Management.Automation.Credential()]` ermöglicht dieses Verhalten.</span><span class="sxs-lookup"><span data-stu-id="945ac-170">The `[System.Management.Automation.Credential()]` attribute enables this behavior.</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential duffney
```

![Aufforderung zur Eingabe von Anmeldeinformationen](./media/add-credentials-to-powershell-functions/GetCredsPrompt.gif)

> [!NOTE]
> <span data-ttu-id="945ac-172">Um den angezeigten Registrierungswert festzulegen, wird in diesen Beispielen davon ausgegangen, dass die **Webserver** -Features von Windows installiert sind.</span><span class="sxs-lookup"><span data-stu-id="945ac-172">To set the registry value shown, these examples assume you have the **Web Server** features of Windows installed.</span></span> <span data-ttu-id="945ac-173">Führen Sie bei Bedarf `Install-WindowsFeature Web-Server` und `Install-WindowsFeature web-mgmt-tools` aus.</span><span class="sxs-lookup"><span data-stu-id="945ac-173">Run `Install-WindowsFeature Web-Server` and `Install-WindowsFeature web-mgmt-tools` if required.</span></span>

### <a name="provide-credentials-in-a-variable"></a><span data-ttu-id="945ac-174">Angeben von Anmeldeinformationen in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="945ac-174">Provide credentials in a variable</span></span>

<span data-ttu-id="945ac-175">Sie können eine Variable für Anmeldeinformationen auch vorab auffüllen und an den **Credential** -Parameter der `Set-RemoteRegistryValue`-Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="945ac-175">You can also populate a credential variable ahead of time and pass it to the **Credential** parameter of `Set-RemoteRegistryValue` function.</span></span> <span data-ttu-id="945ac-176">Verwenden Sie diese Methode mit Continuous Integration-/Continuous Deployment-Tools (CI/CD) wie Jenkins, TeamCity und Octopus Deploy.</span><span class="sxs-lookup"><span data-stu-id="945ac-176">Use this method with Continuous Integration / Continuous Deployment (CI/CD) tools such as Jenkins, TeamCity, and Octopus Deploy.</span></span> <span data-ttu-id="945ac-177">Ein Beispiel für Jenkins finden Sie im Blogbeitrag von Matthew Hodgkins [Automating with Jenkins and PowerShell on Windows - Part 2][].</span><span class="sxs-lookup"><span data-stu-id="945ac-177">For an example using Jenkins, check out Hodge's blog post [Automating with Jenkins and PowerShell on Windows - Part 2][].</span></span>

<span data-ttu-id="945ac-178">In diesem Beispiel wird die .NET-Methode verwendet, um das Objekt für Anmeldeinformationen und eine sichere Zeichenfolge für die Übergabe des Kennworts zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="945ac-178">This example uses the .NET method to create the credential object and a secure string to pass in the password.</span></span>

```powershell
$password = ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("duffney", $password)

$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential $Cred
```

<span data-ttu-id="945ac-179">In diesem Beispiel wird die sichere Zeichenfolge mit einem Kennwort in Klartext erstellt.</span><span class="sxs-lookup"><span data-stu-id="945ac-179">For this example, the secure string is created using a clear text password.</span></span> <span data-ttu-id="945ac-180">Alle zuvor erwähnten CI/CD-Tools verfügen über eine sichere Methode zur Bereitstellung dieses Kennworts zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="945ac-180">All of the previously mentioned CI/CD have a secure method of providing that password at run time.</span></span> <span data-ttu-id="945ac-181">Ersetzen Sie bei Nutzung dieser Tools das Kennwort im Klartext durch die Variable, die in dem von Ihnen verwendeten CI/CD-Tool definiert ist.</span><span class="sxs-lookup"><span data-stu-id="945ac-181">When using those tools, replace the plain text password with the variable defined within the CI/CD tool you use.</span></span>

### <a name="run-without-credentials"></a><span data-ttu-id="945ac-182">Ausführung ohne Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="945ac-182">Run without credentials</span></span>

<span data-ttu-id="945ac-183">Da `$Credential` standardmäßig ein leeres Anmeldeinformationsobjekt ist, können Sie den Befehl, wie in diesem Beispiel gezeigt, ohne Anmeldeinformationen ausführen:</span><span class="sxs-lookup"><span data-stu-id="945ac-183">Since `$Credential` defaults to an empty credential object, you can run the command without credentials, as shown in this example:</span></span>

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams
```

## <a name="dealing-with-legacy-cmdlets"></a><span data-ttu-id="945ac-184">Umgang mit Legacy-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="945ac-184">Dealing with legacy cmdlets</span></span>

<span data-ttu-id="945ac-185">Nicht alle Cmdlets unterstützen Objekte mit Anmeldeinformationen oder lassen leere Anmeldeinformationen zu.</span><span class="sxs-lookup"><span data-stu-id="945ac-185">Not all cmdlets support credential objects or allow empty credentials.</span></span> <span data-ttu-id="945ac-186">Stattdessen fordert das Cmdlet Parameter für Benutzername und Kennwort als Zeichenfolgen an.</span><span class="sxs-lookup"><span data-stu-id="945ac-186">Instead, the cmdlet wants username and password parameters as strings.</span></span> <span data-ttu-id="945ac-187">Es gibt mehrere Möglichkeiten, diese Einschränkung zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="945ac-187">There are a few ways to work around this limitation.</span></span>

### <a name="using-if-else-to-handle-empty-credentials"></a><span data-ttu-id="945ac-188">Verwenden von IF-ELSE bei leeren Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="945ac-188">Using if-else to handle empty credentials</span></span>

<span data-ttu-id="945ac-189">In diesem Szenario akzeptiert das Cmdlet, das Sie ausführen möchten, kein leeres Objekt für Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="945ac-189">In this scenario, the cmdlet you want to run doesn't accept an empty credential object.</span></span> <span data-ttu-id="945ac-190">Bei diesem Beispiel wird der Parameter **Credential** nur dann `Invoke-Command` hinzugefügt, wenn er nicht leer ist.</span><span class="sxs-lookup"><span data-stu-id="945ac-190">This example adds the **Credential** parameter to `Invoke-Command` only if it's not empty.</span></span> <span data-ttu-id="945ac-191">Andernfalls wird `Invoke-Command` ohne den Parameter **Credential** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="945ac-191">Otherwise, it runs the `Invoke-Command` without the **Credential** parameter.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

    if($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
        Invoke-Command -ComputerName:$ComputerName -Credential:$Credential  {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    } else {
        Invoke-Command -ComputerName:$ComputerName {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    }
}
```

### <a name="using-splatting-to-handle-empty-credentials"></a><span data-ttu-id="945ac-192">Verwenden von Splatting bei leeren Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="945ac-192">Using splatting to handle empty credentials</span></span>

<span data-ttu-id="945ac-193">Bei diesem Beispiel wird der Parameter „Splatting“ verwendet, um das Legacy-Cmdlet aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="945ac-193">This example uses parameter splatting to call the legacy cmdlet.</span></span> <span data-ttu-id="945ac-194">Das Objekt `$Credential` wird der Hashtabelle für Splatting bedingt hinzugefügt und vermeidet, dass der Skriptblock `Invoke-Command` wiederholt werden muss.</span><span class="sxs-lookup"><span data-stu-id="945ac-194">The `$Credential` object is conditionally added to the hash table for splatting and avoids the need to repeat the `Invoke-Command` script block.</span></span> <span data-ttu-id="945ac-195">Weitere Informationen zu Splatting innerhalb von Funktionen finden Sie im Blogbeitrag [Splatting Parameters Inside Advanced Functions][].</span><span class="sxs-lookup"><span data-stu-id="945ac-195">To learn more about splatting inside functions, see the [Splatting Parameters Inside Advanced Functions][] blog post.</span></span>

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $Splat = @{
            ComputerName = $ComputerName
        }

        if ($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
            $Splat['Credential'] = $Credential
        }

        $null = Invoke-Command -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } @splat
}
```

### <a name="working-with-string-passwords"></a><span data-ttu-id="945ac-196">Arbeiten mit Zeichenfolgen als Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="945ac-196">Working with string passwords</span></span>

<span data-ttu-id="945ac-197">Das Cmdlet `Invoke-Sqlcmd` ist ein Beispiel eines Cmdlets, das eine Zeichenfolge als Kennwort akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="945ac-197">The `Invoke-Sqlcmd` cmdlet is an example of a cmdlet that accepts a string as a password.</span></span>
<span data-ttu-id="945ac-198">`Invoke-Sqlcmd` ermöglicht das Ausführen der einfachen SQL-Anweisungen INSERT, UPDATE und DELETE.</span><span class="sxs-lookup"><span data-stu-id="945ac-198">`Invoke-Sqlcmd` allows you to run simple SQL insert, update, and delete statements.</span></span> <span data-ttu-id="945ac-199">`Invoke-Sqlcmd` erfordert einen Benutzernamen in Klartext und ein Kennwort anstelle eines sichereren Objekts mit Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="945ac-199">`Invoke-Sqlcmd` requires a clear-text username and password rather than a more secure credential object.</span></span> <span data-ttu-id="945ac-200">Dieses Beispiel zeigt, wie Benutzername und Kennwort aus einem Objekt mit Anmeldeinformationen extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="945ac-200">This example shows how to extract the username and password from a credential object.</span></span>

<span data-ttu-id="945ac-201">Die `Get-AllSQLDatabases`-Funktion in diesem Beispiel ruft das Cmdlet `Invoke-Sqlcmd` auf, um alle in einer SQL Server-Instanz enthaltenen Datenbanken abzufragen.</span><span class="sxs-lookup"><span data-stu-id="945ac-201">The `Get-AllSQLDatabases` function in this example calls the `Invoke-Sqlcmd` cmdlet to query a SQL server for all its databases.</span></span> <span data-ttu-id="945ac-202">Die Funktion definiert den Parameter **Credential** mit dem gleichen Attribut, das in den vorherigen Beispielen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="945ac-202">The function defines a **Credential** parameter with the same attribute used in the previous examples.</span></span> <span data-ttu-id="945ac-203">Da Benutzername und Kennwort innerhalb der Variablen `$Credential` vorhanden sind, können Sie diese Werte für die Verwendung mit `Invoke-Sqlcmd` extrahieren.</span><span class="sxs-lookup"><span data-stu-id="945ac-203">Since the username and password exist within the `$Credential` variable, you can extract those values for use with `Invoke-Sqlcmd`.</span></span>

<span data-ttu-id="945ac-204">Der Benutzername ist über die Eigenschaft **UserName** der Variablen `$Credential` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="945ac-204">The user name is available from the **UserName** property of the `$Credential` variable.</span></span> <span data-ttu-id="945ac-205">Zum Abrufen des Kennworts müssen Sie die `GetNetworkCredential()`-Methode des `$Credential`-Objekts verwenden.</span><span class="sxs-lookup"><span data-stu-id="945ac-205">To obtain the password, you have to use the `GetNetworkCredential()` method of the `$Credential` object.</span></span> <span data-ttu-id="945ac-206">Die Werte werden in Variablen extrahiert, die einer Hashtabelle hinzugefügt werden, die zum Splatting von Parametern in `Invoke-Sqlcmd` dient.</span><span class="sxs-lookup"><span data-stu-id="945ac-206">The values are extracted into variables that are added to a hash table used for splatting parameters to `Invoke-Sqlcmd`.</span></span>

```powershell
function Get-AllSQLDatabases {
    param(
        $SQLServer,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $UserName = $Credential.UserName
        $Password = $Credential.GetNetworkCredential().Password

        $splat = @{
            UserName = $UserName
            Password = $Password
            ServerInstance = 'SQLServer'
            Query = "Select * from Sys.Databases"
        }

        Invoke-Sqlcmd @splat
}

$credSplat = @{
    TypeName = 'System.Management.Automation.PSCredential'
    ArgumentList = 'duffney',('P@ssw0rd' | ConvertTo-SecureString -AsPlainText -Force)
}
$Credential= New-Object @credSplat
ConvertTo-SecureString -AsPlainText -Force)

Get-AllSQLDatabases -SQLServer SQL01 -Credential $Credential
```

## <a name="continued-learning-credential-management"></a><span data-ttu-id="945ac-207">Weitere Informationen zur Verwaltung von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="945ac-207">Continued learning credential management</span></span>

<span data-ttu-id="945ac-208">Die sichere Erstellung und Speicherung von Objekten mit Anmeldeinformationen kann schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="945ac-208">Creating and storing credential objects securely can be difficult.</span></span> <span data-ttu-id="945ac-209">Die folgenden Ressourcen können Ihnen bei der Verwaltung von PowerShell-Anmeldeinformationen helfen.</span><span class="sxs-lookup"><span data-stu-id="945ac-209">The following resources can help you maintain PowerShell credentials.</span></span>

- <span data-ttu-id="945ac-210">[BetterCredentials][]</span><span class="sxs-lookup"><span data-stu-id="945ac-210">[BetterCredentials][]</span></span>
- <span data-ttu-id="945ac-211">[Azure Key Vault][]</span><span class="sxs-lookup"><span data-stu-id="945ac-211">[Azure Key Vault][]</span></span>
- <span data-ttu-id="945ac-212">[Das Projekt Vault][]</span><span class="sxs-lookup"><span data-stu-id="945ac-212">[Vault Project][]</span></span>
- <span data-ttu-id="945ac-213">[Das Modul SecretManagement][]</span><span class="sxs-lookup"><span data-stu-id="945ac-213">[SecretManagement module][]</span></span>

<!-- link references -->
[Originalversion]: https://duffney.io/addcredentialstopowershellfunctions/
[original version]: https://duffney.io/addcredentialstopowershellfunctions/
[@joshduffney]: https://twitter.com/joshduffney
[duffney.io]: https://duffney.io/posts/
[BetterCredentials]: https://www.powershellgallery.com/packages/BetterCredentials/
[Azure Key Vault]: https://azure.microsoft.com/services/key-vault/
[Das Projekt Vault]: https://www.vaultproject.io/
[Vault Project]: https://www.vaultproject.io/
[Splatting Parameters Inside Advanced Functions]: http://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Automating with Jenkins and PowerShell on Windows - Part 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[PSCredential]: /dotnet/api/system.management.automation.pscredential
[The Pester Book]: https://leanpub.com/the-pester-book
[about_Splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[Das Modul SecretManagement]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
[SecretManagement module]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
