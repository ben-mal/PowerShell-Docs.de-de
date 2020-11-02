---
ms.date: 07/16/2020
ms.topic: reference
title: DSC-Ressourcen „Archive“
description: DSC-Ressourcen „Archive“
ms.openlocfilehash: 28e2436683d7cb3b69f894ac75bb1a58b8eb1e8a
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142401"
---
# <a name="dsc-archive-resource"></a><span data-ttu-id="aa43c-103">DSC-Ressourcen „Archive“</span><span class="sxs-lookup"><span data-stu-id="aa43c-103">DSC Archive Resource</span></span>

> <span data-ttu-id="aa43c-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="aa43c-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="aa43c-105">Die Ressource „Archive“ in Windows PowerShell DSC bietet einen Mechanismus zum Entpacken von Archivdateien (.zip).</span><span class="sxs-lookup"><span data-stu-id="aa43c-105">The Archive resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to unpack archive (.zip) files at a specific path.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="aa43c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa43c-106">Syntax</span></span>

```Syntax
Archive [string] #ResourceName
{
    Destination = [string]
    Path = [string]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Validate = [bool] ]
    [ Ensure = [string] { Absent | Present } ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="aa43c-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="aa43c-107">Properties</span></span>

|<span data-ttu-id="aa43c-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="aa43c-108">Property</span></span> |<span data-ttu-id="aa43c-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="aa43c-109">Description</span></span> |
|---|---|
| <span data-ttu-id="aa43c-110">Destination</span><span class="sxs-lookup"><span data-stu-id="aa43c-110">Destination</span></span> | <span data-ttu-id="aa43c-111">Gibt den Speicherort an, an dem der Archivinhalt einer Datei extrahiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="aa43c-111">Specifies the location where you want to ensure the archive contents are extracted.</span></span> |
| <span data-ttu-id="aa43c-112">`Path`</span><span class="sxs-lookup"><span data-stu-id="aa43c-112">Path</span></span> | <span data-ttu-id="aa43c-113">Gibt den Quellpfad der Archivdatei an.</span><span class="sxs-lookup"><span data-stu-id="aa43c-113">Specifies the source path of the archive file.</span></span> |
| <span data-ttu-id="aa43c-114">Checksum</span><span class="sxs-lookup"><span data-stu-id="aa43c-114">Checksum</span></span> | <span data-ttu-id="aa43c-115">Definiert den zu verwendenden Typ, wenn bestimmt wird, ob zwei Dateien identisch sind.</span><span class="sxs-lookup"><span data-stu-id="aa43c-115">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="aa43c-116">Wenn **Checksum** nicht angegeben ist, wird nur der Datei- oder Verzeichnisnamen für den Vergleich verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa43c-116">If **Checksum** is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="aa43c-117">Gültige Werte: **SHA-1** , **SHA-256** , **SHA-512** , **createdDate** , **modifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="aa43c-117">Valid values include: **SHA-1** , **SHA-256** , **SHA-512** , **createdDate** , **modifiedDate** .</span></span> <span data-ttu-id="aa43c-118">Wenn Sie **Checksum** ohne **Validate** angeben, schlägt die Konfiguration fehl.</span><span class="sxs-lookup"><span data-stu-id="aa43c-118">If you specify **Checksum** without **Validate** , the configuration will fail.</span></span> |
| <span data-ttu-id="aa43c-119">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="aa43c-119">Credential</span></span> | <span data-ttu-id="aa43c-120">Die Anmeldeinformationen eines Benutzerkontos mit Zugriffsberechtigung (falls erforderlich) auf den angegebenen Archivpfad und das angegebene Ziel.</span><span class="sxs-lookup"><span data-stu-id="aa43c-120">The credential of a user account with permissions to access the specified archive path and destination if needed.</span></span> |
| <span data-ttu-id="aa43c-121">Force</span><span class="sxs-lookup"><span data-stu-id="aa43c-121">Force</span></span> | <span data-ttu-id="aa43c-122">Bestimmte Dateioperationen (z. B. das Überschreiben einer Datei oder Löschen eines Verzeichnisses, das nicht leer ist), führen zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="aa43c-122">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="aa43c-123">Bei Verwenden der **Force** -Eigenschaft werden solche Fehler überschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa43c-123">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="aa43c-124">Der Standardwert ist **False** .</span><span class="sxs-lookup"><span data-stu-id="aa43c-124">The default value is **False** .</span></span> |
| <span data-ttu-id="aa43c-125">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="aa43c-125">Validate</span></span>| <span data-ttu-id="aa43c-126">Verwendet die Eigenschaft **Checksum** , um zu bestimmen, ob das Archiv der Signatur entspricht.</span><span class="sxs-lookup"><span data-stu-id="aa43c-126">Uses the **Checksum** property to determine if the archive matches the signature.</span></span> <span data-ttu-id="aa43c-127">Wenn Sie **Checksum** ohne **Validate** angeben, schlägt die Konfiguration fehl.</span><span class="sxs-lookup"><span data-stu-id="aa43c-127">If you specify **Checksum** without **Validate** , the configuration will fail.</span></span> <span data-ttu-id="aa43c-128">Wenn Sie **Validate** ohne **Checksum** angeben, wird standardmäßig eine _SHA-256-_ **Prüfsumme** verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa43c-128">If you specify **Validate** without **Checksum** , a _SHA-256_ **Checksum** is used by default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="aa43c-129">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="aa43c-129">Common properties</span></span>

|<span data-ttu-id="aa43c-130">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="aa43c-130">Property</span></span> |<span data-ttu-id="aa43c-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="aa43c-131">Description</span></span> |
|---|---|
|<span data-ttu-id="aa43c-132">DependsOn</span><span class="sxs-lookup"><span data-stu-id="aa43c-132">DependsOn</span></span> |<span data-ttu-id="aa43c-133">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="aa43c-133">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="aa43c-134">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="aa43c-134">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="aa43c-135">Ensure</span><span class="sxs-lookup"><span data-stu-id="aa43c-135">Ensure</span></span> |<span data-ttu-id="aa43c-136">Bestimmt, ob geprüft wird, ob der Inhalt der Archivdatei am **Ziel** vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="aa43c-136">Determines whether to check if the content of the archive exists at the **Destination** .</span></span> <span data-ttu-id="aa43c-137">Legen Sie diese Eigenschaft auf **Present** fest, um sicherzustellen, dass der Inhalt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="aa43c-137">Set this property to **Present** to ensure the contents exist.</span></span> <span data-ttu-id="aa43c-138">Legen Sie sie auf **Absent** fest, um sicherzustellen, dass der Inhalt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="aa43c-138">Set it to **Absent** to ensure they do not exist.</span></span> <span data-ttu-id="aa43c-139">Der Standardwert ist **Present** .</span><span class="sxs-lookup"><span data-stu-id="aa43c-139">The default value is **Present** .</span></span> |
|<span data-ttu-id="aa43c-140">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="aa43c-140">PsDscRunAsCredential</span></span> |<span data-ttu-id="aa43c-141">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="aa43c-141">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="aa43c-142">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="aa43c-142">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="aa43c-143">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="aa43c-143">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="aa43c-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa43c-144">Example</span></span>

<span data-ttu-id="aa43c-145">Im folgenden Beispiel wird veranschaulicht, wie Sie die Ressource „Archive“ verwenden, um sicherzustellen, dass der Inhalt einer Archivdatei mit dem Namen `Test.zip` vorhanden ist und an einem bestimmten Zielspeicherort extrahiert, verwendet und autorisiert wird.</span><span class="sxs-lookup"><span data-stu-id="aa43c-145">The following example shows how to use the Archive resource to ensure that the contents of an archive file called `Test.zip` exist and are extracted at a given destination using and authorized.</span></span>

```powershell
Archive ArchiveExample {
    Ensure = "Present"
    Path = "C:\Users\Public\Documents\Test.zip"
    Destination = "C:\Users\Public\Documents\ExtractionPath"
}
```
