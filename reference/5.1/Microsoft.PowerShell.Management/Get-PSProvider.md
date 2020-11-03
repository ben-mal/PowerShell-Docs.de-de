---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: 997d86460837946a2cf18fc78f058f21472dd909
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215399"
---
# <span data-ttu-id="6c5ce-103">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="6c5ce-103">Get-PSProvider</span></span>

## <span data-ttu-id="6c5ce-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6c5ce-104">SYNOPSIS</span></span>
<span data-ttu-id="6c5ce-105">Ruft Informationen zum angegebenen Windows PowerShell-Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-105">Gets information about the specified Windows PowerShell provider.</span></span>

## <span data-ttu-id="6c5ce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6c5ce-106">SYNTAX</span></span>

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="6c5ce-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6c5ce-107">DESCRIPTION</span></span>
<span data-ttu-id="6c5ce-108">Mit dem " **Get-psprovider"-** Cmdlet werden die Windows PowerShell-Anbieter in der aktuellen Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-108">The **Get-PSProvider** cmdlet gets the Windows PowerShell providers in the current session.</span></span>
<span data-ttu-id="6c5ce-109">Sie können ein bestimmtes Laufwerk oder alle Laufwerke in der Sitzung abrufen.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-109">You can get a particular drive or all drives in the session.</span></span>

<span data-ttu-id="6c5ce-110">Mit Windows PowerShell-Anbietern können Sie auf verschiedene Datenspeicher zugreifen, als wären es Dateisystemlaufwerke.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-110">Windows PowerShell providers let you access a variety of data stores as though they were file system drives.</span></span>
<span data-ttu-id="6c5ce-111">Informationen zu Windows PowerShell-Anbietern finden Sie unter %%amp;quot;about_Providers%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-111">For information about Windows PowerShell providers, see about_Providers.</span></span>

## <span data-ttu-id="6c5ce-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6c5ce-112">EXAMPLES</span></span>

### <span data-ttu-id="6c5ce-113">Beispiel 1: Anzeigen einer Liste aller verfügbaren Anbieter</span><span class="sxs-lookup"><span data-stu-id="6c5ce-113">Example 1: Display a list of all available providers</span></span>

```
PS C:\> Get-PSProvider
```

<span data-ttu-id="6c5ce-114">Mit diesem Befehl wird eine Liste aller verfügbaren Windows PowerShell-Anbieter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-114">This command displays a list of all available Windows PowerShell providers.</span></span>

### <span data-ttu-id="6c5ce-115">Beispiel 2: Anzeigen einer Liste aller Windows PowerShell-Anbieter, die mit angegebenen Buchstaben beginnen</span><span class="sxs-lookup"><span data-stu-id="6c5ce-115">Example 2: Display a list of all Windows PowerShell providers that begin with specified letters</span></span>

```
PS C:\> Get-PSProvider f*, r* | Format-List
```

<span data-ttu-id="6c5ce-116">Mit diesem Befehl wird eine Liste aller Windows PowerShell-Anbieter angezeigt, deren Namen mit dem Buchstaben f oder r beginnen.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-116">This command displays a list of all Windows PowerShell providers with names that begin with the letter f or r.</span></span>

### <span data-ttu-id="6c5ce-117">Beispiel 3: Suchen von Snap-Ins oder Modulen, die ihrer Sitzung Anbieter hinzugefügt haben</span><span class="sxs-lookup"><span data-stu-id="6c5ce-117">Example 3: Find snap-ins or module that added providers to your session</span></span>

```
PS C:\> Get-PSProvider | Format-Table name, module, pssnapin -auto

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

PS C:\> Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}

Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

<span data-ttu-id="6c5ce-118">Mit diesen Befehlen werden die Windows PowerShell-Snap-Ins oder -Module gesucht, durch die der Sitzung Anbieter hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-118">These commands find the Windows PowerShell snap-ins or modules that added providers to your session.</span></span>
<span data-ttu-id="6c5ce-119">Alle Windows PowerShell-Elemente, einschließlich Anbieter, stammen aus einem Snap-In oder einem Modul.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-119">All Windows PowerShell elements, including providers, originate in a snap-in or in a module.</span></span>

<span data-ttu-id="6c5ce-120">Diese Befehle verwenden die PSSnapIn-Eigenschaft und die Module-Eigenschaft des **ProviderInfo** -Objekts, das von **Get-psprovider** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-120">These commands use the PSSnapin and Module properties of the **ProviderInfo** object that **Get-PSProvider** returns.</span></span>
<span data-ttu-id="6c5ce-121">Die Werte dieser Eigenschaften enthalten den Namen des Snap-Ins oder Moduls, das den Anbieter hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-121">The values of these properties contain the name of the snap-in or module that adds the provider.</span></span>

<span data-ttu-id="6c5ce-122">Der erste Befehl ruft alle Anbieter in der Sitzung ab und formatiert sie in einer Tabelle mit den Werten der Eigenschaften %%amp;quot;Name%%amp;quot;, %%amp;quot;Module%%amp;quot; und %%amp;quot;PSSnapin%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-122">The first command gets all of the providers in the session and formats them in a table with the values of their Name, Module, and PSSnapin properties.</span></span>

<span data-ttu-id="6c5ce-123">Der zweite Befehl verwendet das Cmdlet "Where-Object", um die Anbieter zu erhalten, die aus dem **Microsoft. PowerShell. Security** -Snap-in stammen.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-123">The second command uses the Where-Object cmdlet to get the providers that come from the **Microsoft.PowerShell.Security** snap-in.</span></span>

### <span data-ttu-id="6c5ce-124">Beispiel 4: Auflösen des Pfads der Eigenschaft "Home" des Dateisystem Anbieters</span><span class="sxs-lookup"><span data-stu-id="6c5ce-124">Example 4: Resolve the path of the Home property of the file system provider</span></span>

```
PS C:\> Resolve-Path ~

Path
----
C:\Users\User01

PS C:\> (get-psprovider FileSystem).home
C:\Users\User01
```

<span data-ttu-id="6c5ce-125">Dieses Beispiel veranschaulicht, dass die Tilde (~) den Wert der Home-Eigenschaft des FileSystem-Anbieters darstellt.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-125">This example shows that the tilde symbol (~) represents the value of the Home property of the FileSystem provider.</span></span>
<span data-ttu-id="6c5ce-126">Der Home-Eigenschafts Wert ist optional, aber für den File System-Anbieter ist er als $ENV: HOMEDRIVE \$ ENV: HOMEPATH oder $Home definiert.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-126">The Home property value is optional, but for the FileSystem provider, it is defined as $env:homedrive\$env:homepath or $home.</span></span>

## <span data-ttu-id="6c5ce-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6c5ce-127">PARAMETERS</span></span>

### <span data-ttu-id="6c5ce-128">-Psprovider</span><span class="sxs-lookup"><span data-stu-id="6c5ce-128">-PSProvider</span></span>
<span data-ttu-id="6c5ce-129">Gibt die Namen der Windows PowerShell-Anbieter an, über die dieses Cmdlet Informationen abruft.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-129">Specifies the name or names of the Windows PowerShell providers about which this cmdlet gets information.</span></span>

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

### <span data-ttu-id="6c5ce-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6c5ce-130">CommonParameters</span></span>
<span data-ttu-id="6c5ce-131">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6c5ce-132">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6c5ce-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6c5ce-133">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6c5ce-133">INPUTS</span></span>

### <span data-ttu-id="6c5ce-134">String[]</span><span class="sxs-lookup"><span data-stu-id="6c5ce-134">String[]</span></span>

<span data-ttu-id="6c5ce-135">Sie können eine oder mehrere Anbieter namens Zeichenfolgen über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-135">You can pipe one or more provider name strings to this cmdlet.</span></span>

## <span data-ttu-id="6c5ce-136">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6c5ce-136">OUTPUTS</span></span>

### <span data-ttu-id="6c5ce-137">System. Management. Automation. ProviderInfo</span><span class="sxs-lookup"><span data-stu-id="6c5ce-137">System.Management.Automation.ProviderInfo</span></span>
<span data-ttu-id="6c5ce-138">Dieses Cmdlet gibt Objekte zurück, die die Windows PowerShell-Anbieter in der Sitzung darstellen.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-138">This cmdlet returns objects that represent the Windows PowerShell providers in the session.</span></span>

## <span data-ttu-id="6c5ce-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6c5ce-139">NOTES</span></span>

## <span data-ttu-id="6c5ce-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6c5ce-140">RELATED LINKS</span></span>

## <span data-ttu-id="6c5ce-141">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6c5ce-141">RELATED LINKS</span></span>
