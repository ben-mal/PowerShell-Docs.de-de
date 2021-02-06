---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 20820d2d194f41d43048c9617b63b9acb3fbb4f8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601713"
---
# <span data-ttu-id="094ab-102">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="094ab-102">Get-PSProvider</span></span>

## <span data-ttu-id="094ab-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="094ab-103">SYNOPSIS</span></span>
<span data-ttu-id="094ab-104">Ruft Informationen zum angegebenen PowerShell-Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="094ab-104">Gets information about the specified PowerShell provider.</span></span>

## <span data-ttu-id="094ab-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="094ab-105">SYNTAX</span></span>

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="094ab-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="094ab-106">DESCRIPTION</span></span>

<span data-ttu-id="094ab-107">Mit dem- `Get-PSProvider` Cmdlet werden die PowerShell-Anbieter in der aktuellen Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="094ab-107">The `Get-PSProvider` cmdlet gets the PowerShell providers in the current session.</span></span>
<span data-ttu-id="094ab-108">Sie können ein bestimmtes Laufwerk oder alle Laufwerke in der Sitzung abrufen.</span><span class="sxs-lookup"><span data-stu-id="094ab-108">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="094ab-109">Mit PowerShell-Anbietern können Sie auf eine Vielzahl von Daten speichern zugreifen, als wären es Dateisystem Laufwerke.</span><span class="sxs-lookup"><span data-stu-id="094ab-109">PowerShell providers let you access a variety of data stores as though they were file system drives.</span></span>
<span data-ttu-id="094ab-110">Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="094ab-110">For information about PowerShell providers, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="094ab-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="094ab-111">EXAMPLES</span></span>

### <span data-ttu-id="094ab-112">Beispiel 1: Anzeigen einer Liste aller verfügbaren Anbieter</span><span class="sxs-lookup"><span data-stu-id="094ab-112">Example 1: Display a list of all available providers</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="094ab-113">Mit diesem Befehl wird eine Liste aller verfügbaren PowerShell-Anbieter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="094ab-113">This command displays a list of all available PowerShell providers.</span></span>

### <span data-ttu-id="094ab-114">Beispiel 2: Anzeigen einer Liste aller PowerShell-Anbieter, die mit angegebenen Buchstaben beginnen</span><span class="sxs-lookup"><span data-stu-id="094ab-114">Example 2: Display a list of all PowerShell providers that begin with specified letters</span></span>

```powershell
Get-PSProvider f*, r* | Format-List
```

<span data-ttu-id="094ab-115">Mit diesem Befehl wird eine Liste aller PowerShell-Anbieter angezeigt, deren Namen mit dem Buchstaben f oder r beginnen.</span><span class="sxs-lookup"><span data-stu-id="094ab-115">This command displays a list of all PowerShell providers with names that begin with the letter f or r.</span></span>

### <span data-ttu-id="094ab-116">Beispiel 3: Suchen von Snap-Ins oder Modulen, die ihrer Sitzung Anbieter hinzugefügt haben</span><span class="sxs-lookup"><span data-stu-id="094ab-116">Example 3: Find snap-ins or module that added providers to your session</span></span>

```powershell
Get-PSProvider | Format-Table name, module, pssnapin -auto
```

```Output
Name        Module       PSSnapIn
----        ------       --------
Test        TestModule
WSMan                    Microsoft.WSMan.Management
Alias                    Microsoft.PowerShell.Core
Environment              Microsoft.PowerShell.Core
FileSystem               Microsoft.PowerShell.Core
Function                 Microsoft.PowerShell.Core
Registry                 Microsoft.PowerShell.Core
Variable                 Microsoft.PowerShell.Core
Certificate              Microsoft.PowerShell.Security
```

```powershell
Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}
```

```Output
Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

<span data-ttu-id="094ab-117">Diese Befehle suchen die PowerShell-Snap-Ins oder-Module, die ihrer Sitzung Anbieter hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="094ab-117">These commands find the PowerShell snap-ins or modules that added providers to your session.</span></span>
<span data-ttu-id="094ab-118">Alle PowerShell-Elemente, einschließlich Anbieter, stammen aus einem Snap-in oder einem Modul.</span><span class="sxs-lookup"><span data-stu-id="094ab-118">All PowerShell elements, including providers, originate in a snap-in or in a module.</span></span>

<span data-ttu-id="094ab-119">Diese Befehle verwenden die PSSnapIn-Eigenschaft und die Module-Eigenschaft des **ProviderInfo** -Objekts, das `Get-PSProvider` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="094ab-119">These commands use the PSSnapin and Module properties of the **ProviderInfo** object that `Get-PSProvider` returns.</span></span>
<span data-ttu-id="094ab-120">Die Werte dieser Eigenschaften enthalten den Namen des Snap-Ins oder Moduls, das den Anbieter hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="094ab-120">The values of these properties contain the name of the snap-in or module that adds the provider.</span></span>

<span data-ttu-id="094ab-121">Der erste Befehl ruft alle Anbieter in der Sitzung ab und formatiert sie in einer Tabelle mit den Werten der Eigenschaften %%amp;quot;Name%%amp;quot;, %%amp;quot;Module%%amp;quot; und %%amp;quot;PSSnapin%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="094ab-121">The first command gets all of the providers in the session and formats them in a table with the values of their Name, Module, and PSSnapin properties.</span></span>

<span data-ttu-id="094ab-122">Der zweite Befehl verwendet das `Where-Object` Cmdlet, um die Anbieter zu erhalten, die vom **Microsoft. PowerShell. Security** -Snap-in stammen.</span><span class="sxs-lookup"><span data-stu-id="094ab-122">The second command uses the `Where-Object` cmdlet to get the providers that come from the **Microsoft.PowerShell.Security** snap-in.</span></span>

### <span data-ttu-id="094ab-123">Beispiel 4: Auflösen des Pfads der Eigenschaft "Home" des Dateisystem Anbieters</span><span class="sxs-lookup"><span data-stu-id="094ab-123">Example 4: Resolve the path of the Home property of the file system provider</span></span>

```powershell
C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

```powershell
PS C:\> (get-psprovider FileSystem).home
```

```Output
C:\Users\User01
```

<span data-ttu-id="094ab-124">Dieses Beispiel zeigt, dass das tildesymbol (~) den Wert der **Home** -Eigenschaft des File System-Anbieters darstellt.</span><span class="sxs-lookup"><span data-stu-id="094ab-124">This example shows that the tilde symbol (~) represents the value of the **Home** property of the FileSystem provider.</span></span>
<span data-ttu-id="094ab-125">Der **Home** -Eigenschafts Wert ist optional, aber für den **File System** -Anbieter ist er als `$env:homedrive\$env:homepath` oder definiert `$home` .</span><span class="sxs-lookup"><span data-stu-id="094ab-125">The **Home** property value is optional, but for the **FileSystem** provider, it is defined as `$env:homedrive\$env:homepath` or `$home`.</span></span>

## <span data-ttu-id="094ab-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="094ab-126">PARAMETERS</span></span>

### <span data-ttu-id="094ab-127">-Psprovider</span><span class="sxs-lookup"><span data-stu-id="094ab-127">-PSProvider</span></span>

<span data-ttu-id="094ab-128">Gibt die Namen der PowerShell-Anbieter an, über die dieses Cmdlet Informationen abruft.</span><span class="sxs-lookup"><span data-stu-id="094ab-128">Specifies the name or names of the PowerShell providers about which this cmdlet gets information.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="094ab-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="094ab-129">CommonParameters</span></span>

<span data-ttu-id="094ab-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="094ab-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="094ab-131">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="094ab-131">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="094ab-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="094ab-132">INPUTS</span></span>

### <span data-ttu-id="094ab-133">String[]</span><span class="sxs-lookup"><span data-stu-id="094ab-133">String[]</span></span>

<span data-ttu-id="094ab-134">Sie können eine oder mehrere Anbieter namens Zeichenfolgen über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="094ab-134">You can pipe one or more provider name strings to this cmdlet.</span></span>

## <span data-ttu-id="094ab-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="094ab-135">OUTPUTS</span></span>

### <span data-ttu-id="094ab-136">System. Management. Automation. ProviderInfo</span><span class="sxs-lookup"><span data-stu-id="094ab-136">System.Management.Automation.ProviderInfo</span></span>

<span data-ttu-id="094ab-137">Dieses Cmdlet gibt Objekte zurück, die die PowerShell-Anbieter in der Sitzung darstellen.</span><span class="sxs-lookup"><span data-stu-id="094ab-137">This cmdlet returns objects that represent the PowerShell providers in the session.</span></span>

## <span data-ttu-id="094ab-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="094ab-138">NOTES</span></span>

## <span data-ttu-id="094ab-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="094ab-139">RELATED LINKS</span></span>

