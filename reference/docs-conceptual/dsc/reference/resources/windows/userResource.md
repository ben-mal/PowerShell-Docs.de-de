---
ms.date: 07/16/2020
ms.topic: reference
title: DSC-Ressource „User“
description: DSC-Ressource „User“
ms.openlocfilehash: b14f8d434ef3e1eb220fe7b0b18a011014c9ae6c
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142599"
---
# <a name="dsc-user-resource"></a><span data-ttu-id="41b30-103">DSC-Ressource „User“</span><span class="sxs-lookup"><span data-stu-id="41b30-103">DSC User Resource</span></span>

> <span data-ttu-id="41b30-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="41b30-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="41b30-105">Die Ressource **User** in Windows PowerShell DSC bietet einen Mechanismus zum Verwalten lokaler Benutzerkonten auf dem Zielknoten.</span><span class="sxs-lookup"><span data-stu-id="41b30-105">The **User** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local user accounts on the target node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="41b30-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="41b30-106">Syntax</span></span>

```Syntax
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="41b30-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="41b30-107">Properties</span></span>

|<span data-ttu-id="41b30-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="41b30-108">Property</span></span> |<span data-ttu-id="41b30-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="41b30-109">Description</span></span> |
|---|---|
|<span data-ttu-id="41b30-110">UserName</span><span class="sxs-lookup"><span data-stu-id="41b30-110">UserName</span></span> |<span data-ttu-id="41b30-111">Gibt den Kontonamen an, für den Sie einen bestimmten Zustand sicherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="41b30-111">Indicates the account name for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="41b30-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="41b30-112">Description</span></span> |<span data-ttu-id="41b30-113">Gibt die Beschreibung an, die Sie für das Benutzerkonto verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="41b30-113">Indicates the description you want to use for the user account.</span></span> |
|<span data-ttu-id="41b30-114">Disabled</span><span class="sxs-lookup"><span data-stu-id="41b30-114">Disabled</span></span> |<span data-ttu-id="41b30-115">Gibt an, ob das Konto aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="41b30-115">Indicates if the account is enabled.</span></span> <span data-ttu-id="41b30-116">Legen Sie diese Eigenschaft auf `$true` fest, um sicherzustellen, dass dieses Konto deaktiviert ist. Legen Sie sie auf `$false` fest, um sicherzustellen, dass es aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="41b30-116">Set this property to `$true` to ensure that this account is disabled, and set it to `$false` to ensure that it is enabled.</span></span> |
|<span data-ttu-id="41b30-117">FullName</span><span class="sxs-lookup"><span data-stu-id="41b30-117">FullName</span></span> |<span data-ttu-id="41b30-118">Stellt eine Zeichenfolge mit dem vollständigen Namen dar, den Sie für das Benutzerkonto verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="41b30-118">Represents a string with the full name you want to use for the user account.</span></span> |
|<span data-ttu-id="41b30-119">Kennwort</span><span class="sxs-lookup"><span data-stu-id="41b30-119">Password</span></span> |<span data-ttu-id="41b30-120">Gibt das Kennwort an, das Sie für dieses Konto verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="41b30-120">Indicates the password you want to use for this account.</span></span> |
|<span data-ttu-id="41b30-121">PasswordChangeNotAllowed</span><span class="sxs-lookup"><span data-stu-id="41b30-121">PasswordChangeNotAllowed</span></span> |<span data-ttu-id="41b30-122">Gibt an, ob der Benutzer das Kennwort ändern kann.</span><span class="sxs-lookup"><span data-stu-id="41b30-122">Indicates if the user can change the password.</span></span> <span data-ttu-id="41b30-123">Legen Sie diese Eigenschaft auf `$true` fest, um sicherzustellen, dass der Benutzer das Kennwort nicht ändern kann. Legen Sie es auf `$false` fest, damit der Benutzer das Kennwort ändern kann.</span><span class="sxs-lookup"><span data-stu-id="41b30-123">Set this property to `$true` to ensure that the user cannot change the password, and set it to `$false` to allow the user to change the password.</span></span> <span data-ttu-id="41b30-124">Standardwert: `$false`.</span><span class="sxs-lookup"><span data-stu-id="41b30-124">The default value is `$false`.</span></span> |
|<span data-ttu-id="41b30-125">PasswordChangeRequired</span><span class="sxs-lookup"><span data-stu-id="41b30-125">PasswordChangeRequired</span></span> |<span data-ttu-id="41b30-126">Gibt an, ob der Benutzer sein Kennwort bei der nächsten Anmeldung ändern muss.</span><span class="sxs-lookup"><span data-stu-id="41b30-126">Indicates if the user must change the password at the next sign in.</span></span> <span data-ttu-id="41b30-127">Legen Sie diese Eigenschaft auf `$true` fest, wenn der Benutzer das Kennwort ändern muss.</span><span class="sxs-lookup"><span data-stu-id="41b30-127">Set this property to `$true` if the user must change the password.</span></span> <span data-ttu-id="41b30-128">Standardwert: `$true`.</span><span class="sxs-lookup"><span data-stu-id="41b30-128">The default value is `$true`.</span></span> |
|<span data-ttu-id="41b30-129">PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="41b30-129">PasswordNeverExpires</span></span> |<span data-ttu-id="41b30-130">Gibt an, ob das Kennwort abläuft.</span><span class="sxs-lookup"><span data-stu-id="41b30-130">Indicates if the password will expire.</span></span> <span data-ttu-id="41b30-131">Um sicherzustellen, dass das Kennwort für dieses Konto nie abläuft, legen Sie diese Eigenschaft auf `$true` fest.</span><span class="sxs-lookup"><span data-stu-id="41b30-131">To ensure that the password for this account will never expire, set this property to `$true`.</span></span> <span data-ttu-id="41b30-132">Legen Sie sie auf `$false` fest, wenn das Kennwort ablaufen soll.</span><span class="sxs-lookup"><span data-stu-id="41b30-132">Set it to `$false` if the password will expire.</span></span> <span data-ttu-id="41b30-133">Standardwert: `$false`.</span><span class="sxs-lookup"><span data-stu-id="41b30-133">The default value is `$false`.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="41b30-134">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="41b30-134">Common properties</span></span>

|<span data-ttu-id="41b30-135">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="41b30-135">Property</span></span> |<span data-ttu-id="41b30-136">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="41b30-136">Description</span></span> |
|---|---|
|<span data-ttu-id="41b30-137">DependsOn</span><span class="sxs-lookup"><span data-stu-id="41b30-137">DependsOn</span></span> |<span data-ttu-id="41b30-138">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="41b30-138">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="41b30-139">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="41b30-139">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="41b30-140">Ensure</span><span class="sxs-lookup"><span data-stu-id="41b30-140">Ensure</span></span> |<span data-ttu-id="41b30-141">Gibt an, ob das Konto vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="41b30-141">Indicates if the account exists.</span></span> <span data-ttu-id="41b30-142">Legen Sie diese Eigenschaft auf **Present** fest, um sicherzustellen, dass das Konto vorhanden ist. Legen Sie sie auf **Absent** fest, um sicherzustellen, dass das Konto nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="41b30-142">Set this property to **Present** to ensure that the account exists, and set it to **Absent** to ensure that the account does not exist.</span></span> <span data-ttu-id="41b30-143">Der Standardwert ist **Present** .</span><span class="sxs-lookup"><span data-stu-id="41b30-143">The default value is **Present** .</span></span> |
|<span data-ttu-id="41b30-144">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="41b30-144">PsDscRunAsCredential</span></span> |<span data-ttu-id="41b30-145">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="41b30-145">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="41b30-146">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="41b30-146">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="41b30-147">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="41b30-147">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="41b30-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41b30-148">Example</span></span>

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = "[Group]GroupExample" # Configures GroupExample first
}
```
