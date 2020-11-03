---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 03/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: 18a7163a2f67c22013fb607c3b90f3c350a0d797
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216172"
---
# <span data-ttu-id="4fc91-102">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="4fc91-102">Get-ExperimentalFeature</span></span>

## <span data-ttu-id="4fc91-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4fc91-103">SYNOPSIS</span></span>
<span data-ttu-id="4fc91-104">Ruft experimentelle Funktionen ab.</span><span class="sxs-lookup"><span data-stu-id="4fc91-104">Gets experimental features.</span></span>

## <span data-ttu-id="4fc91-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4fc91-105">SYNTAX</span></span>

```
Get-ExperimentalFeature [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="4fc91-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4fc91-106">DESCRIPTION</span></span>

<span data-ttu-id="4fc91-107">Mit dem- `Get-ExperimentalFeature` Cmdlet werden alle von PowerShell ermittelten experimentellen Funktionen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4fc91-107">The `Get-ExperimentalFeature` cmdlet returns all experimental features discovered by PowerShell.</span></span>
<span data-ttu-id="4fc91-108">Experimentelle Features können von Modulen oder der PowerShell-Engine stammen.</span><span class="sxs-lookup"><span data-stu-id="4fc91-108">Experimental features can come from modules or the PowerShell engine.</span></span> <span data-ttu-id="4fc91-109">Mithilfe von experimentellen Features können Benutzer neue Features sicher testen und Feedback bereitstellen (in der Regel über GitHub), bevor der Entwurf als "Fertig" angesehen wird und alle Änderungen zu einer Breaking Change werden können.</span><span class="sxs-lookup"><span data-stu-id="4fc91-109">Experimental features allow users to safely test new features and provide feedback (typically via GitHub) before the design is considered complete and any changes can become a breaking change.</span></span>

## <span data-ttu-id="4fc91-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4fc91-110">EXAMPLES</span></span>

### <span data-ttu-id="4fc91-111">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="4fc91-111">Example 1</span></span>

<span data-ttu-id="4fc91-112">Ruft die Liste der derzeit registrierten experimentellen Features und deren aktuellen Status ab.</span><span class="sxs-lookup"><span data-stu-id="4fc91-112">Gets the list of currently registered experimental features and their current state.</span></span>

```powershell
Get-ExperimentalFeature
```

```Output
Name                         Enabled Source      Description
----                         ------- ------      -----------
PSImplicitRemotingBatching   False PSEngine      Batch implicit remoting proxy commands to improve performance
```

## <span data-ttu-id="4fc91-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4fc91-113">PARAMETERS</span></span>

### <span data-ttu-id="4fc91-114">-Name</span><span class="sxs-lookup"><span data-stu-id="4fc91-114">-Name</span></span>

<span data-ttu-id="4fc91-115">Name oder Name der spezifischen experimentellen Funktionen, die zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4fc91-115">Name or names of specific experimental features to return.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4fc91-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4fc91-116">CommonParameters</span></span>

<span data-ttu-id="4fc91-117">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4fc91-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4fc91-118">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4fc91-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4fc91-119">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4fc91-119">INPUTS</span></span>

### <span data-ttu-id="4fc91-120">System.String[]</span><span class="sxs-lookup"><span data-stu-id="4fc91-120">System.String[]</span></span>

<span data-ttu-id="4fc91-121">Name oder Name von experimentellen Funktionen, die zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4fc91-121">Name or names of experimental features to return.</span></span>

## <span data-ttu-id="4fc91-122">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4fc91-122">OUTPUTS</span></span>

### <span data-ttu-id="4fc91-123">Experimentalfeature</span><span class="sxs-lookup"><span data-stu-id="4fc91-123">ExperimentalFeature</span></span>

<span data-ttu-id="4fc91-124">Gibt-Instanzen zurück, die den angeforderten Namen oder allen experimentellen Funktionen entsprechen, wenn kein Name angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4fc91-124">Returns instances that match the requested names or all experimental features if no name is specified.</span></span>

## <span data-ttu-id="4fc91-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4fc91-125">NOTES</span></span>

## <span data-ttu-id="4fc91-126">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4fc91-126">RELATED LINKS</span></span>

[<span data-ttu-id="4fc91-127">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="4fc91-127">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="4fc91-128">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="4fc91-128">Enable-ExperimentalFeature</span></span>](Enable-ExperimentalFeature.md)
