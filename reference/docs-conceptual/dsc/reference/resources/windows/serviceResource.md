---
ms.date: 09/20/2019
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressource „Service“
ms.openlocfilehash: f936f58ffd00f84d8c6d5d41d93378eaa8db5879
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463583"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="9781f-103">DSC-Ressource „Service“</span><span class="sxs-lookup"><span data-stu-id="9781f-103">DSC Service Resource</span></span>

> <span data-ttu-id="9781f-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="9781f-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="9781f-105">Die Ressource **Service** in Windows PowerShell DSC bietet einen Mechanismus zum Verwalten von Diensten auf dem Zielknoten.</span><span class="sxs-lookup"><span data-stu-id="9781f-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="9781f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9781f-106">Syntax</span></span>

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupTimeout = [uint32]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Ignore | Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DesktopInteract = [boolean]]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
    [ TerminateTimeout = [uint32] ]
}
```

## <a name="properties"></a><span data-ttu-id="9781f-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9781f-107">Properties</span></span>

|<span data-ttu-id="9781f-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9781f-108">Property</span></span> |<span data-ttu-id="9781f-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9781f-109">Description</span></span> |
|---|---|
|<span data-ttu-id="9781f-110">Name</span><span class="sxs-lookup"><span data-stu-id="9781f-110">Name</span></span> |<span data-ttu-id="9781f-111">Gibt den Namen des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="9781f-111">Indicates the service name.</span></span> <span data-ttu-id="9781f-112">Beachten Sie, dass sich dieser mitunter vom Anzeigenamen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="9781f-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="9781f-113">Mit dem Cmdlet `Get-Service` können Sie eine Liste der Dienste und ihren aktuellen Status abrufen.</span><span class="sxs-lookup"><span data-stu-id="9781f-113">You can get a list of the services and their current state with the `Get-Service` cmdlet.</span></span> |
|<span data-ttu-id="9781f-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="9781f-114">BuiltInAccount</span></span> |<span data-ttu-id="9781f-115">Gibt das zu verwendende Anmeldekonto für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="9781f-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="9781f-116">Die für diese Eigenschaft zulässigen Werte sind: **LocalService**, **LocalSystem** und **NetworkService**.</span><span class="sxs-lookup"><span data-stu-id="9781f-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span> |
|<span data-ttu-id="9781f-117">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="9781f-117">Credential</span></span> |<span data-ttu-id="9781f-118">Gibt die Anmeldeinformationen für das Konto an, unter dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9781f-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="9781f-119">Diese Eigenschaft und die **BuiltinAccount**-Eigenschaft können nicht zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9781f-119">This property and the **BuiltinAccount** property cannot be used together.</span></span> |
|<span data-ttu-id="9781f-120">StartupTimeout</span><span class="sxs-lookup"><span data-stu-id="9781f-120">StartupTimeout</span></span> | <span data-ttu-id="9781f-121">Die Zeit (in Millisekunden ), die gewartet werden soll, bis der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9781f-121">The time to wait for the service to be running in milliseconds.</span></span>|
|<span data-ttu-id="9781f-122">StartupType</span><span class="sxs-lookup"><span data-stu-id="9781f-122">StartupType</span></span> |<span data-ttu-id="9781f-123">Gibt den Starttyp für den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="9781f-123">Indicates the startup type for the service.</span></span> <span data-ttu-id="9781f-124">Die für diese Eigenschaft zulässigen Werte sind: **Automatic**, **Disabled** und **Manual**.</span><span class="sxs-lookup"><span data-stu-id="9781f-124">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**.</span></span> |
|<span data-ttu-id="9781f-125">State</span><span class="sxs-lookup"><span data-stu-id="9781f-125">State</span></span> |<span data-ttu-id="9781f-126">Gibt den Status an, den Sie für den Dienst sicherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9781f-126">Indicates the state you want to ensure for the service.</span></span> <span data-ttu-id="9781f-127">Die Werte sind: **Running** oder **Stopped**.</span><span class="sxs-lookup"><span data-stu-id="9781f-127">The values are: **Running** or **Stopped**.</span></span> |
|<span data-ttu-id="9781f-128">TerminateTimeout</span><span class="sxs-lookup"><span data-stu-id="9781f-128">TerminateTimeout</span></span> |<span data-ttu-id="9781f-129">Die Wartezeit (in Millisekunden), die gewartet werden soll, bis der Dienst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="9781f-129">The time to wait for the service to be stopped in milliseconds.</span></span>|
|<span data-ttu-id="9781f-130">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="9781f-130">Dependencies</span></span> | <span data-ttu-id="9781f-131">Ein Array mit den Namen der Abhängigkeiten, die der Dienst aufweisen sollte.</span><span class="sxs-lookup"><span data-stu-id="9781f-131">An array of the names of the dependencies the service should have.</span></span> |
|<span data-ttu-id="9781f-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9781f-132">Description</span></span> |<span data-ttu-id="9781f-133">Gibt die Beschreibung des Zieldiensts an.</span><span class="sxs-lookup"><span data-stu-id="9781f-133">Indicates the description of the target service.</span></span> |
|<span data-ttu-id="9781f-134">DesktopInteract</span><span class="sxs-lookup"><span data-stu-id="9781f-134">DesktopInteract</span></span> | <span data-ttu-id="9781f-135">Gibt an, ob der Dienst in der Lage sein soll, mit einem Fenster auf dem Desktop zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="9781f-135">Indicates whether or not the service should be able to communicate with a window on the desktop.</span></span> <span data-ttu-id="9781f-136">Muss für Dienste, die nicht als LocalSystem ausgeführt werden, FALSE sein.</span><span class="sxs-lookup"><span data-stu-id="9781f-136">Must be false for services not running as LocalSystem.</span></span>|
|<span data-ttu-id="9781f-137">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9781f-137">DisplayName</span></span> |<span data-ttu-id="9781f-138">Gibt den Anzeigenamen des Zieldiensts an.</span><span class="sxs-lookup"><span data-stu-id="9781f-138">Indicates the display name of the target service.</span></span> |
|<span data-ttu-id="9781f-139">Pfad</span><span class="sxs-lookup"><span data-stu-id="9781f-139">Path</span></span> |<span data-ttu-id="9781f-140">Gibt den Pfad zur Binärdatei eines neuen Diensts an.</span><span class="sxs-lookup"><span data-stu-id="9781f-140">Indicates the path to the binary file for a new service.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="9781f-141">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9781f-141">Common properties</span></span>

|<span data-ttu-id="9781f-142">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9781f-142">Property</span></span> |<span data-ttu-id="9781f-143">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9781f-143">Description</span></span> |
|---|---|
|<span data-ttu-id="9781f-144">DependsOn</span><span class="sxs-lookup"><span data-stu-id="9781f-144">DependsOn</span></span> |<span data-ttu-id="9781f-145">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="9781f-145">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="9781f-146">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="9781f-146">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="9781f-147">Ensure</span><span class="sxs-lookup"><span data-stu-id="9781f-147">Ensure</span></span> |<span data-ttu-id="9781f-148">Gibt an, ob der Zieldienst auf dem System vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9781f-148">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="9781f-149">Legen Sie diese Eigenschaft auf **Absent** fest, um sicherzustellen, dass der Zieldienst nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9781f-149">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="9781f-150">Das Festlegen auf **Present** stellt sicher, dass der Zieldienst vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9781f-150">Setting it to **Present** ensures that target service exists.</span></span> <span data-ttu-id="9781f-151">Der Standardwert ist **Present**.</span><span class="sxs-lookup"><span data-stu-id="9781f-151">The default value is **Present**.</span></span> |
|<span data-ttu-id="9781f-152">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="9781f-152">PsDscRunAsCredential</span></span> |<span data-ttu-id="9781f-153">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="9781f-153">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="9781f-154">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9781f-154">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="9781f-155">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="9781f-155">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="9781f-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9781f-156">Example</span></span>

```powershell
configuration ServiceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        Service ServiceExample
        {
            Name        = "TermService"
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```
