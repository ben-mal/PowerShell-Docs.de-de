---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessioncapability?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionCapability
ms.openlocfilehash: c5e3cb677a736595d1acd98c6f4be4d43b2151ba
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216468"
---
# <span data-ttu-id="d2dcc-103">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="d2dcc-103">Get-PSSessionCapability</span></span>

## <span data-ttu-id="d2dcc-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d2dcc-104">SYNOPSIS</span></span>
<span data-ttu-id="d2dcc-105">Ruft die Funktionen eines bestimmten Benutzers in einer eingeschränkten Sitzungs Konfiguration ab.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-105">Gets the capabilities of a specific user on a constrained session configuration.</span></span>

## <span data-ttu-id="d2dcc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d2dcc-106">SYNTAX</span></span>

```
Get-PSSessionCapability [-ConfigurationName] <String> [-Username] <String> [-Full] [<CommonParameters>]
```

## <span data-ttu-id="d2dcc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d2dcc-107">DESCRIPTION</span></span>

<span data-ttu-id="d2dcc-108">Mit dem " **Get-pssessioncapability"-** Cmdlet werden die Funktionen eines bestimmten Benutzers in einer eingeschränkten Sitzungs Konfiguration abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-108">The **Get-PSSessionCapability** cmdlet gets the capabilities of a specific user on a constrained session configuration.</span></span>
<span data-ttu-id="d2dcc-109">Verwenden Sie dieses Cmdlet, um benutzerdefinierte Sitzungs Konfigurationen für Benutzer zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-109">Use this cmdlet to audit customized session configurations for users.</span></span>

<span data-ttu-id="d2dcc-110">Ab Windows PowerShell 5,0 können Sie die **roledefinitions** -Eigenschaft in einer Sitzungs Konfigurationsdatei (. PSSC) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-110">Starting in Windows PowerShell 5.0, you can use the **RoleDefinitions** property in a session configuration (.pssc) file.</span></span>
<span data-ttu-id="d2dcc-111">Mithilfe dieser Eigenschaft können Sie Benutzern basierend auf der Gruppenmitgliedschaft unterschiedliche Funktionen für einen einzelnen eingeschränkten Endpunkt erteilen.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-111">Using this property lets you grant users different capabilities on a single constrained endpoint based on group membership.</span></span>
<span data-ttu-id="d2dcc-112">Mit dem " **Get-pssessioncapability"-** Cmdlet wird die Komplexität bei der Überwachung dieser Endpunkte reduziert, indem Sie die genauen Funktionen eines Benutzers bestimmen können.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-112">The **Get-PSSessionCapability** cmdlet reduces complexity when auditing these endpoints by letting you determine the exact capabilities granted to a user.</span></span>

<span data-ttu-id="d2dcc-113">Standardmäßig gibt das **Get-pssessioncapability** -Cmdlet eine Liste der Befehle zurück, die der angegebene Benutzer im angegebenen Endpunkt ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-113">By default, the **Get-PSSessionCapability** cmdlet returns a list of commands the specified user can run in the specified endpoint.</span></span>
<span data-ttu-id="d2dcc-114">Dies entspricht dem Benutzer, der " **Get-Command** " im angegebenen Endpunkt ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-114">This is equivalent to the user running **Get-Command** in the specified endpoint.</span></span>
<span data-ttu-id="d2dcc-115">Bei der Verwendung mit dem *Full* -Parameter gibt dieses Cmdlet ein **initialsessionstate** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-115">When run with the *Full* parameter, this cmdlet returns an **InitialSessionState** object.</span></span>
<span data-ttu-id="d2dcc-116">Dieses Objekt enthält Details zum PowerShell-Runspace, mit dem der angegebene Benutzer für den angegebenen Endpunkt interagieren würde.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-116">This object contains details about the PowerShell runspace the specified user would interact with for the specified endpoint.</span></span>
<span data-ttu-id="d2dcc-117">Sie enthält Informationen wie den Sprachmodus, die Ausführungs Richtlinie und Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-117">It includes information such as Language Mode, Execution Policy, and Environmental Variables.</span></span>

## <span data-ttu-id="d2dcc-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d2dcc-118">EXAMPLES</span></span>

### <span data-ttu-id="d2dcc-119">Beispiel 1: Get-Befehle, die für einen Benutzer verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="d2dcc-119">Example 1: Get commands available for a user</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User'
```

<span data-ttu-id="d2dcc-120">In diesem Beispiel werden die Befehle, die für den Benutzer contoso\user verfügbar sind, beim Herstellen einer Verbindung mit dem eingeschränkten Endpunkt endpoint1 auf dem lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-120">This example returns the commands available to the user CONTOSO\User when connecting to the Endpoint1 constrained endpoint on the local computer.</span></span>

### <span data-ttu-id="d2dcc-121">Beispiel 2: erhalten von Details zu einem Runspace für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d2dcc-121">Example 2: Get details about a runspace for a user</span></span>

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User' -Full
```

<span data-ttu-id="d2dcc-122">In diesem Beispiel werden Details zum Runspace zurückgegeben, mit dem der Benutzer contoso\user interagieren würde, wenn eine Verbindung mit dem eingeschränkten endpoint1-Endpunkt hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-122">This example returns details about the runspace the user CONTOSO\User would interact with when connecting to the Endpoint1 constrained endpoint.</span></span>

## <span data-ttu-id="d2dcc-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d2dcc-123">PARAMETERS</span></span>

### <span data-ttu-id="d2dcc-124">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="d2dcc-124">-ConfigurationName</span></span>

<span data-ttu-id="d2dcc-125">Gibt die Konfiguration der eingeschränkten Sitzung (Endpunkt) an, die Sie überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-125">Specifies the constrained session configuration (endpoint) that you are inspecting.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2dcc-126">-Full</span><span class="sxs-lookup"><span data-stu-id="d2dcc-126">-Full</span></span>

<span data-ttu-id="d2dcc-127">Gibt an, dass dieses Cmdlet den gesamten anfänglichen Sitzungs Status für den angegebenen Benutzer am angegebenen eingeschränkten Endpunkt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-127">Indicates that this cmdlet returns the entire initial session state for the specified user at the specified constrained endpoint.</span></span>

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

### <span data-ttu-id="d2dcc-128">-Username</span><span class="sxs-lookup"><span data-stu-id="d2dcc-128">-Username</span></span>

<span data-ttu-id="d2dcc-129">Gibt den Benutzer an, dessen Funktionen Sie überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-129">Specifies the user whose capabilities you are inspecting.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2dcc-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d2dcc-130">CommonParameters</span></span>

<span data-ttu-id="d2dcc-131">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d2dcc-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d2dcc-132">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d2dcc-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d2dcc-133">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d2dcc-133">INPUTS</span></span>

## <span data-ttu-id="d2dcc-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d2dcc-134">OUTPUTS</span></span>

### <span data-ttu-id="d2dcc-135">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="d2dcc-135">System.Management.Automation.AliasInfo</span></span>

### <span data-ttu-id="d2dcc-136">System. Management. Automation. functioninfo</span><span class="sxs-lookup"><span data-stu-id="d2dcc-136">System.Management.Automation.FunctionInfo</span></span>

### <span data-ttu-id="d2dcc-137">System.Management.Automation.Runspaces.Initialsessionstate</span><span class="sxs-lookup"><span data-stu-id="d2dcc-137">System.Management.Automation.Runspaces.InitialSessionState</span></span>

## <span data-ttu-id="d2dcc-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d2dcc-138">NOTES</span></span>

## <span data-ttu-id="d2dcc-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d2dcc-139">RELATED LINKS</span></span>

[<span data-ttu-id="d2dcc-140">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="d2dcc-140">New-PSRoleCapabilityFile</span></span>](New-PSRoleCapabilityFile.md)
