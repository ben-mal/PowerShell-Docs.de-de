---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disconnect-wsman?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-WSMan
ms.openlocfilehash: 948b870948f51bd51424beaeca45ed2b2d195891
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600506"
---
# <span data-ttu-id="839aa-102">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="839aa-102">Disconnect-WSMan</span></span>

## <span data-ttu-id="839aa-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="839aa-103">SYNOPSIS</span></span>
<span data-ttu-id="839aa-104">Trennt den Client vom WinRM-Dienst auf einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="839aa-104">Disconnects the client from the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="839aa-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="839aa-105">SYNTAX</span></span>

```
Disconnect-WSMan [[-ComputerName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="839aa-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="839aa-106">DESCRIPTION</span></span>
<span data-ttu-id="839aa-107">Das **Disconnect-WSMAN-** Cmdlet trennt den Client vom WinRM-Dienst auf einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="839aa-107">The **Disconnect-WSMan** cmdlet disconnects the client from the WinRM service on a remote computer.</span></span>
<span data-ttu-id="839aa-108">Wenn Sie die WS-Management Sitzung in einer Variablen gespeichert haben, bleibt das Sitzungs Objekt in der Variablen, der Status der WS-Management Sitzung wird jedoch geschlossen.</span><span class="sxs-lookup"><span data-stu-id="839aa-108">If you saved the WS-Management session in a variable, the session object remains in the variable, but the state of the WS-Management session is Closed.</span></span>
<span data-ttu-id="839aa-109">Sie können dieses Cmdlet im Kontext des WSMan-Anbieters verwenden, um den Client vom WinRM-Dienst auf einem Remotecomputer zu trennen.</span><span class="sxs-lookup"><span data-stu-id="839aa-109">You can use this cmdlet within the context of the WSMan provider to disconnect the client from the WinRM service on a remote computer.</span></span>
<span data-ttu-id="839aa-110">Sie können dieses Cmdlet jedoch auch verwenden, um die Verbindung mit dem WinRM-Dienst auf Remotecomputern zu trennen, bevor Sie zum WSMan-Anbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="839aa-110">However, you can also use this cmdlet to disconnect from the WinRM service on remote computers before you change to the WSMan provider.</span></span>

<span data-ttu-id="839aa-111">Weitere Informationen zum Herstellen einer Verbindung mit dem WinRM-Dienst auf einem Remotecomputer finden Sie unter „Connect-WSMan“.</span><span class="sxs-lookup"><span data-stu-id="839aa-111">For more information about how to connect to the WinRM service on a remote computer, see Connect-WSMan.</span></span>

## <span data-ttu-id="839aa-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="839aa-112">EXAMPLES</span></span>

### <span data-ttu-id="839aa-113">Beispiel 1: Löschen einer Verbindung mit einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="839aa-113">Example 1: Delete a connection to a remote computer</span></span>

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

<span data-ttu-id="839aa-114">Dieser Befehl löscht die Verbindung mit dem Remote Computer mit dem Namen Server01.</span><span class="sxs-lookup"><span data-stu-id="839aa-114">This command deletes the connection to the remote computer named server01.</span></span>

<span data-ttu-id="839aa-115">Dieses Cmdlet wird in der Regel im Kontext des WSMan-Anbieters verwendet, um eine Verbindung mit einem Remotecomputer zu trennen, in diesem Fall mit dem Computer server01.</span><span class="sxs-lookup"><span data-stu-id="839aa-115">This cmdlet is generally used within the context of the WSMan provider to disconnect from a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="839aa-116">Sie können jedoch auch **Disconnect-WSMAN** verwenden, um Verbindungen mit Remote Computern zu entfernen, bevor Sie zum WSMAN-Anbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="839aa-116">However, you can also use **Disconnect-WSMan** to remove connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="839aa-117">Diese Verbindungen werden nicht in der Computername-Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="839aa-117">Those connections do not appear in the ComputerName list.</span></span>

## <span data-ttu-id="839aa-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="839aa-118">PARAMETERS</span></span>

### <span data-ttu-id="839aa-119">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="839aa-119">-ComputerName</span></span>
<span data-ttu-id="839aa-120">Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="839aa-120">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="839aa-121">Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.</span><span class="sxs-lookup"><span data-stu-id="839aa-121">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="839aa-122">Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="839aa-122">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="839aa-123">Der lokale Computer ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="839aa-123">The local computer is the default.</span></span>
<span data-ttu-id="839aa-124">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="839aa-124">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="839aa-125">Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="839aa-125">You can pipe a value for this parameter to the cmdlet.</span></span>

<span data-ttu-id="839aa-126">Die Verbindung mit dem lokalen Host kann nicht getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="839aa-126">You cannot disconnect from the local host.</span></span>
<span data-ttu-id="839aa-127">Das heißt, Sie können die Standardverbindung mit dem lokalen Computer nicht trennen.</span><span class="sxs-lookup"><span data-stu-id="839aa-127">That is, you cannot disconnect the default connection to the local computer.</span></span>
<span data-ttu-id="839aa-128">Wenn Sie jedoch eine separate Verbindung mit dem lokalen Computer erstellen, z. b. mithilfe des Computer namens.</span><span class="sxs-lookup"><span data-stu-id="839aa-128">However, if you create a separate connection to the local computer, for example, by using the computer name.</span></span>

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

### <span data-ttu-id="839aa-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="839aa-129">CommonParameters</span></span>
<span data-ttu-id="839aa-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="839aa-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="839aa-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="839aa-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="839aa-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="839aa-132">INPUTS</span></span>

### <span data-ttu-id="839aa-133">Keine</span><span class="sxs-lookup"><span data-stu-id="839aa-133">None</span></span>
<span data-ttu-id="839aa-134">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="839aa-134">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="839aa-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="839aa-135">OUTPUTS</span></span>

### <span data-ttu-id="839aa-136">Keine</span><span class="sxs-lookup"><span data-stu-id="839aa-136">None</span></span>
<span data-ttu-id="839aa-137">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="839aa-137">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="839aa-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="839aa-138">NOTES</span></span>

## <span data-ttu-id="839aa-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="839aa-139">RELATED LINKS</span></span>

[<span data-ttu-id="839aa-140">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="839aa-140">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="839aa-141">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="839aa-141">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="839aa-142">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="839aa-142">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="839aa-143">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="839aa-143">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="839aa-144">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="839aa-144">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="839aa-145">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="839aa-145">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="839aa-146">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="839aa-146">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="839aa-147">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="839aa-147">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="839aa-148">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="839aa-148">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="839aa-149">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="839aa-149">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="839aa-150">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="839aa-150">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="839aa-151">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="839aa-151">Test-WSMan</span></span>](Test-WSMan.md)

