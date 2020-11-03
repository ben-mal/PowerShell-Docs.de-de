---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disconnect-wsman?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-WSMan
ms.openlocfilehash: 8e1a406b56d5e74ade438699847b80b0adab2a24
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224820"
---
# <span data-ttu-id="9e266-103">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="9e266-103">Disconnect-WSMan</span></span>

## <span data-ttu-id="9e266-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9e266-104">SYNOPSIS</span></span>
<span data-ttu-id="9e266-105">Trennt den Client vom WinRM-Dienst auf einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="9e266-105">Disconnects the client from the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="9e266-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9e266-106">SYNTAX</span></span>

```
Disconnect-WSMan [[-ComputerName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="9e266-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9e266-107">DESCRIPTION</span></span>
<span data-ttu-id="9e266-108">Das **Disconnect-WSMAN-** Cmdlet trennt den Client vom WinRM-Dienst auf einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="9e266-108">The **Disconnect-WSMan** cmdlet disconnects the client from the WinRM service on a remote computer.</span></span>
<span data-ttu-id="9e266-109">Wenn Sie die WS-Management Sitzung in einer Variablen gespeichert haben, bleibt das Sitzungs Objekt in der Variablen, der Status der WS-Management Sitzung wird jedoch geschlossen.</span><span class="sxs-lookup"><span data-stu-id="9e266-109">If you saved the WS-Management session in a variable, the session object remains in the variable, but the state of the WS-Management session is Closed.</span></span>
<span data-ttu-id="9e266-110">Sie können dieses Cmdlet im Kontext des WSMan-Anbieters verwenden, um den Client vom WinRM-Dienst auf einem Remotecomputer zu trennen.</span><span class="sxs-lookup"><span data-stu-id="9e266-110">You can use this cmdlet within the context of the WSMan provider to disconnect the client from the WinRM service on a remote computer.</span></span>
<span data-ttu-id="9e266-111">Sie können dieses Cmdlet jedoch auch verwenden, um die Verbindung mit dem WinRM-Dienst auf Remotecomputern zu trennen, bevor Sie zum WSMan-Anbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="9e266-111">However, you can also use this cmdlet to disconnect from the WinRM service on remote computers before you change to the WSMan provider.</span></span>

<span data-ttu-id="9e266-112">Weitere Informationen zum Herstellen einer Verbindung mit dem WinRM-Dienst auf einem Remotecomputer finden Sie unter „Connect-WSMan“.</span><span class="sxs-lookup"><span data-stu-id="9e266-112">For more information about how to connect to the WinRM service on a remote computer, see Connect-WSMan.</span></span>

## <span data-ttu-id="9e266-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9e266-113">EXAMPLES</span></span>

### <span data-ttu-id="9e266-114">Beispiel 1: Löschen einer Verbindung mit einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="9e266-114">Example 1: Delete a connection to a remote computer</span></span>

```
PS C:\> Disconnect-WSMan -computer server01
PS C:\> cd WSMan:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
```

<span data-ttu-id="9e266-115">Dieser Befehl löscht die Verbindung mit dem Remote Computer mit dem Namen Server01.</span><span class="sxs-lookup"><span data-stu-id="9e266-115">This command deletes the connection to the remote computer named server01.</span></span>

<span data-ttu-id="9e266-116">Dieses Cmdlet wird in der Regel im Kontext des WSMan-Anbieters verwendet, um eine Verbindung mit einem Remotecomputer zu trennen, in diesem Fall mit dem Computer server01.</span><span class="sxs-lookup"><span data-stu-id="9e266-116">This cmdlet is generally used within the context of the WSMan provider to disconnect from a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="9e266-117">Sie können jedoch auch **Disconnect-WSMAN** verwenden, um Verbindungen mit Remote Computern zu entfernen, bevor Sie zum WSMAN-Anbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="9e266-117">However, you can also use **Disconnect-WSMan** to remove connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="9e266-118">Diese Verbindungen werden nicht in der Computername-Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9e266-118">Those connections do not appear in the ComputerName list.</span></span>

## <span data-ttu-id="9e266-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9e266-119">PARAMETERS</span></span>

### <span data-ttu-id="9e266-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9e266-120">-ComputerName</span></span>
<span data-ttu-id="9e266-121">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9e266-121">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="9e266-122">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="9e266-122">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="9e266-123">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9e266-123">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="9e266-124">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="9e266-124">The local computer is the default.</span></span>
<span data-ttu-id="9e266-125">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e266-125">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="9e266-126">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="9e266-126">You can pipe a value for this parameter to the cmdlet.</span></span>

<span data-ttu-id="9e266-127">Die Verbindung mit dem lokalen Host kann nicht getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="9e266-127">You cannot disconnect from the local host.</span></span>
<span data-ttu-id="9e266-128">Das heißt, Sie können die Standardverbindung mit dem lokalen Computer nicht trennen.</span><span class="sxs-lookup"><span data-stu-id="9e266-128">That is, you cannot disconnect the default connection to the local computer.</span></span>
<span data-ttu-id="9e266-129">Wenn Sie jedoch eine separate Verbindung mit dem lokalen Computer erstellen, z. b. mithilfe des Computer namens.</span><span class="sxs-lookup"><span data-stu-id="9e266-129">However, if you create a separate connection to the local computer, for example, by using the computer name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e266-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9e266-130">CommonParameters</span></span>
<span data-ttu-id="9e266-131">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9e266-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9e266-132">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9e266-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9e266-133">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9e266-133">INPUTS</span></span>

### <span data-ttu-id="9e266-134">Keine</span><span class="sxs-lookup"><span data-stu-id="9e266-134">None</span></span>
<span data-ttu-id="9e266-135">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="9e266-135">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="9e266-136">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9e266-136">OUTPUTS</span></span>

### <span data-ttu-id="9e266-137">Keine</span><span class="sxs-lookup"><span data-stu-id="9e266-137">None</span></span>
<span data-ttu-id="9e266-138">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9e266-138">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9e266-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9e266-139">NOTES</span></span>

## <span data-ttu-id="9e266-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9e266-140">RELATED LINKS</span></span>

[<span data-ttu-id="9e266-141">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="9e266-141">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="9e266-142">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="9e266-142">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="9e266-143">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="9e266-143">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="9e266-144">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="9e266-144">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="9e266-145">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9e266-145">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="9e266-146">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="9e266-146">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="9e266-147">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9e266-147">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="9e266-148">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="9e266-148">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="9e266-149">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9e266-149">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="9e266-150">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="9e266-150">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="9e266-151">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="9e266-151">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="9e266-152">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="9e266-152">Test-WSMan</span></span>](Test-WSMan.md)
