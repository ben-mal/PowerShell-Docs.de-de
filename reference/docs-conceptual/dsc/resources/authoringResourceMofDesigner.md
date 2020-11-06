---
ms.date: 07/08/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Verwenden des Ressourcen-Designers
description: Der Ressourcen-Designer ist ein Gruppe von Cmdlets, die vom Modul xDscResourceDesigner verfügbar gemacht werden und das Erstellen von Windows PowerShell DSC-Ressourcen erleichtern.
ms.openlocfilehash: efe36d045ac3fba3823cb1f812bb5761d238fdf1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656493"
---
# <a name="using-the-resource-designer-tool"></a><span data-ttu-id="262ba-104">Verwenden des Ressourcen-Designers</span><span class="sxs-lookup"><span data-stu-id="262ba-104">Using the Resource Designer tool</span></span>

> <span data-ttu-id="262ba-105">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="262ba-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="262ba-106">Der Ressourcen-Designer ist ein Satz von Cmdlets, die vom Modul **xDscResourceDesigner** verfügbar gemacht werden und das Erstellen von Windows PowerShell DSC-Ressourcen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="262ba-106">The Resource Designer tool is a set of cmdlets exposed by the **xDscResourceDesigner** module that make creating Windows PowerShell Desired State Configuration (DSC) resources easier.</span></span> <span data-ttu-id="262ba-107">Die Cmdlets in dieser Ressource helfen beim Erstellen des MOF-Schemas, des Skriptmoduls und der Verzeichnisstruktur für die neue Ressource.</span><span class="sxs-lookup"><span data-stu-id="262ba-107">The cmdlets in this resource help create the MOF schema, the script module, and the directory structure for your new resource.</span></span> <span data-ttu-id="262ba-108">Weitere Informationen zu DSC-Ressourcen finden Sie unter [Erstellen von benutzerdefinierten Windows PowerShell DSC-Ressourcen](authoringResource.md).</span><span class="sxs-lookup"><span data-stu-id="262ba-108">For more information about DSC resources, see [Build Custom Windows PowerShell Desired State Configuration Resources](authoringResource.md).</span></span> <span data-ttu-id="262ba-109">In diesem Artikel wird eine DSC-Ressource zur Verwaltung von Active Directory-Benutzern erstellt.</span><span class="sxs-lookup"><span data-stu-id="262ba-109">In this article, we will create a DSC resource that manages Active Directory users.</span></span> <span data-ttu-id="262ba-110">Verwenden Sie das Cmdlet [Install-Module](/powershell/module/PowershellGet/Install-Module) zum Installieren des Moduls **xDscResourceDesigner**.</span><span class="sxs-lookup"><span data-stu-id="262ba-110">Use the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to install the **xDscResourceDesigner** module.</span></span>

## <a name="creating-resource-properties"></a><span data-ttu-id="262ba-111">Erstellen von Ressourceneigenschaften</span><span class="sxs-lookup"><span data-stu-id="262ba-111">Creating resource properties</span></span>

<span data-ttu-id="262ba-112">Zunächst werden Eigenschaften festgelegt, die die Ressource verfügbar machen soll.</span><span class="sxs-lookup"><span data-stu-id="262ba-112">The first thing we need to do is decide on properties that the resource will expose.</span></span> <span data-ttu-id="262ba-113">In diesem Beispiel wird ein Active Directory-Benutzer mit den folgenden Eigenschaften definiert.</span><span class="sxs-lookup"><span data-stu-id="262ba-113">For this example, we will define an Active Directory user with the following properties.</span></span>

<span data-ttu-id="262ba-114">Parameternamen und Beschreibungen</span><span class="sxs-lookup"><span data-stu-id="262ba-114">Parameter name  Description</span></span>

- <span data-ttu-id="262ba-115">**UserName** : Schlüsseleigenschaft, die einen Benutzer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="262ba-115">**UserName** : Key property that uniquely identifies a user.</span></span>
- <span data-ttu-id="262ba-116">**Ensure** : Gibt an, ob das Benutzerkonto vorhanden („Present“) oder nicht vorhanden („Absent“) sein soll.</span><span class="sxs-lookup"><span data-stu-id="262ba-116">**Ensure** : Specifies whether the user account should be Present or Absent.</span></span> <span data-ttu-id="262ba-117">Für diesen Parameter gibt es nur zwei mögliche Werte.</span><span class="sxs-lookup"><span data-stu-id="262ba-117">This parameter will have only two possible values.</span></span>
- <span data-ttu-id="262ba-118">**DomainCredential** : Das Domänenkennwort für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="262ba-118">**DomainCredential** : The domain password for the user.</span></span>
- <span data-ttu-id="262ba-119">**Password** : Das gewünschte Kennwort für den Benutzer, um einer Konfiguration zu erlauben, das Benutzerkennwort bei Bedarf zu ändern.</span><span class="sxs-lookup"><span data-stu-id="262ba-119">**Password** : The desired password for the user to allow a configuration to change the user password if necessary.</span></span>

<span data-ttu-id="262ba-120">Zum Erstellen der Eigenschaften verwenden wir das Cmdlet `New-xDscResourceProperty`.</span><span class="sxs-lookup"><span data-stu-id="262ba-120">To create the properties, we use the `New-xDscResourceProperty` cmdlet.</span></span> <span data-ttu-id="262ba-121">Mit den folgenden PowerShell-Befehlen werden die oben beschriebenen Eigenschaften erstellt.</span><span class="sxs-lookup"><span data-stu-id="262ba-121">The following PowerShell commands create the properties described above.</span></span>

```powershell
$UserName = New-xDscResourceProperty –Name UserName -Type String -Attribute Key
$Ensure = New-xDscResourceProperty –Name Ensure -Type String -Attribute Write –ValidateSet "Present", "Absent"
$DomainCredential = New-xDscResourceProperty –Name DomainCredential -Type PSCredential -Attribute Write
$Password = New-xDscResourceProperty –Name Password -Type PSCredential -Attribute Write
```

## <a name="create-the-resource"></a><span data-ttu-id="262ba-122">Erstellen der Ressource</span><span class="sxs-lookup"><span data-stu-id="262ba-122">Create the resource</span></span>

<span data-ttu-id="262ba-123">Nachdem die Ressourceneigenschaften nun erstellt wurden, kann das Cmdlet `New-xDscResource` aufgerufen werden, um die Ressource zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="262ba-123">Now that the resource properties have been created, we can call the `New-xDscResource` cmdlet to create the resource.</span></span> <span data-ttu-id="262ba-124">Vom Cmdlet `New-xDscResource` wird die Liste der Eigenschaften als Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="262ba-124">The `New-xDscResource` cmdlet takes the list of properties as parameters.</span></span> <span data-ttu-id="262ba-125">Es verwendet auch der Pfad, unter dem das Modul erstellt werden soll, den Namen der neuen Ressource und den Namen des Moduls, in dem sie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="262ba-125">It also takes the path where the module should be created, the name of the new resource, and the name of the module in which it is contained.</span></span> <span data-ttu-id="262ba-126">Der folgende PowerShell-Befehl erstellt die Ressource:</span><span class="sxs-lookup"><span data-stu-id="262ba-126">The following PowerShell command creates the resource.</span></span>

```powershell
New-xDscResource –Name Demo_ADUser –Property $UserName, $Ensure, $DomainCredential, $Password –Path 'C:\Program Files\WindowsPowerShell\Modules' –ModuleName Demo_DSCModule
```

<span data-ttu-id="262ba-127">Das Cmdlet `New-xDscResource` erstellt das MOF-Schema, ein Gerüstressourcenskript, die erforderliche Verzeichnisstruktur für die neue Ressource und ein Manifest für das Modul, das die neue Ressource verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="262ba-127">The `New-xDscResource` cmdlet creates the MOF schema, a skeleton resource script, the required directory structure for your new resource, and a manifest for the module that exposes the new resource.</span></span>

<span data-ttu-id="262ba-128">Die MOF-Schemadatei befindet sich in `C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.schema.mof`. Ihre Inhalte sind wie folgt.</span><span class="sxs-lookup"><span data-stu-id="262ba-128">The MOF schema file is at `C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.schema.mof`, and its contents are as follows.</span></span>

```
[ClassVersion("1.0.0.0"), FriendlyName("Demo_ADUser")]
class Demo_ADUser : OMI_BaseResource
{
  [Key] string UserName;
  [Write, ValueMap{"Present","Absent"}, Values{"Present","Absent"}] string Ensure;
  [Write, EmbeddedInstance("MSFT_Credential")] String DomainCredential;
  [Write, EmbeddedInstance("MSFT_Credential")] String Password;
};
```

<span data-ttu-id="262ba-129">Das Ressourcenskript befindet sich in `C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.psm1`.</span><span class="sxs-lookup"><span data-stu-id="262ba-129">The resource script is at `C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.psm1`.</span></span>
<span data-ttu-id="262ba-130">Es umfasst nicht die eigentliche Logik zum Implementieren der Ressource. Diese müssen Sie selbst hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="262ba-130">It does not include the actual logic to implement the resource, which you must add yourself.</span></span> <span data-ttu-id="262ba-131">Der Inhalt des Skelettskripts sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="262ba-131">The contents of the skeleton script are as follows.</span></span>

```powershell
function Get-TargetResource
{
  [CmdletBinding()]
  [OutputType([System.Collections.Hashtable])]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."

  <#
  $returnValue = @{
  UserName = [System.String]
  Ensure = [System.String]
  DomainAdminCredential = [System.Management.Automation.PSCredential]
  Password = [System.Management.Automation.PSCredential]
  }

  $returnValue
  #>
}

function Set-TargetResource
{
  [CmdletBinding()]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName,

    [ValidateSet("Present","Absent")]
    [System.String]
    $Ensure,

    [System.Management.Automation.PSCredential]
    $DomainAdminCredential,

    [System.Management.Automation.PSCredential]
    $Password
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."

  #Include this line if the resource requires a system reboot.
  #$global:DSCMachineStatus = 1
}

function Test-TargetResource
{
  [CmdletBinding()]
  [OutputType([System.Boolean])]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName,

    [ValidateSet("Present","Absent")]
    [System.String]
    $Ensure,

    [System.Management.Automation.PSCredential]
    $DomainAdminCredential,

    [System.Management.Automation.PSCredential]
    $Password
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."

  <#
  $result = [System.Boolean]

  $result
  #>
}

Export-ModuleMember -Function *-TargetResource
```

## <a name="updating-the-resource"></a><span data-ttu-id="262ba-132">Aktualisieren der Ressource</span><span class="sxs-lookup"><span data-stu-id="262ba-132">Updating the resource</span></span>

<span data-ttu-id="262ba-133">Wenn Sie die Parameterliste der Ressource erweitern oder ändern müssen, können Sie das Cmdlet `Update-xDscResource` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="262ba-133">If you need to add or modify the parameter list of the resource, you can call the `Update-xDscResource` cmdlet.</span></span> <span data-ttu-id="262ba-134">Das Cmdlet aktualisiert die Ressource mit einer neuen Parameterliste.</span><span class="sxs-lookup"><span data-stu-id="262ba-134">The cmdlet updates the resource with a new parameter list.</span></span> <span data-ttu-id="262ba-135">Wenn Sie bereits Logik zu Ihrem Ressourcenskript hinzugefügt haben, bleibt diese davon unberührt.</span><span class="sxs-lookup"><span data-stu-id="262ba-135">If you have already added logic in your resource script, it is left intact.</span></span>

<span data-ttu-id="262ba-136">Angenommen, Sie möchten den Zeitpunkt der letzten Anmeldung des Benutzers zur Ressource hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="262ba-136">For example, suppose you want to include the last log in time for the user in our resource.</span></span> <span data-ttu-id="262ba-137">Anstatt die Ressource vollständig neu zu schreiben, können Sie `New-xDscResourceProperty` aufrufen, um die Eigenschaft neu zu erstellen, und diese neue Eigenschaft dann mit `Update-xDscResource` zur Eigenschaftenliste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="262ba-137">Rather than writing the resource again completely, you can call the `New-xDscResourceProperty` to create the new property, and then call `Update-xDscResource` and add your new property to the properties list.</span></span>

```powershell
$lastLogon = New-xDscResourceProperty –Name LastLogon –Type Hashtable –Attribute Write –Description "For mapping users to their last log on time"
Update-xDscResource –Name 'Demo_ADUser' –Property $UserName, $Ensure, $DomainCredential, $Password, $lastLogon -Force
```

## <a name="testing-a-resource-schema"></a><span data-ttu-id="262ba-138">Testen eines Ressourcenschemas</span><span class="sxs-lookup"><span data-stu-id="262ba-138">Testing a resource schema</span></span>

<span data-ttu-id="262ba-139">Der Ressourcen-Designer stellt ein weiteres Cmdlet zur Verfügung, mit dem Sie die Gültigkeit eines MOF-Schemas testen können, das Sie manuell geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="262ba-139">The Resource Designer tool exposes one more cmdlet that can be used to test the validity of a MOF schema that you have written manually.</span></span> <span data-ttu-id="262ba-140">Rufen Sie das Cmdlet `Test-xDscSchema` auf, und übergeben Sie dabei den Pfad eines MOF-Ressourcenschemas als Parameter.</span><span class="sxs-lookup"><span data-stu-id="262ba-140">Call the `Test-xDscSchema` cmdlet, passing the path of a MOF resource schema as a parameter.</span></span> <span data-ttu-id="262ba-141">Das Cmdlet gibt alle Fehler im Schema aus.</span><span class="sxs-lookup"><span data-stu-id="262ba-141">The cmdlet will output any errors in the schema.</span></span>

### <a name="see-also"></a><span data-ttu-id="262ba-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="262ba-142">See Also</span></span>

#### <a name="concepts"></a><span data-ttu-id="262ba-143">Konzepte</span><span class="sxs-lookup"><span data-stu-id="262ba-143">Concepts</span></span>

[<span data-ttu-id="262ba-144">Erstellen von benutzerdefinierten Windows PowerShell DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="262ba-144">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>](authoringResource.md)

#### <a name="other-resources"></a><span data-ttu-id="262ba-145">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="262ba-145">Other Resources</span></span>

[<span data-ttu-id="262ba-146">xDscResourceDesigner-Modul</span><span class="sxs-lookup"><span data-stu-id="262ba-146">xDscResourceDesigner Module</span></span>](https://www.powershellgallery.com/packages/xDscResourceDesigner/1.12.0.0)
