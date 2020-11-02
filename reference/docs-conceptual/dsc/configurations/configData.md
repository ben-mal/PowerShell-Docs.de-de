---
ms.date: 06/12/2017
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Verwenden von Konfigurationsdaten
description: In diesem Thema wird die Struktur der Hashtabelle ConfigurationData beschrieben. Dadurch können Sie eine einzige Konfiguration erstellen, die für mehrere Knoten oder für unterschiedliche Umgebungen verwendet werden kann.
ms.openlocfilehash: aa4a0545aec529dbc923908612d2e1f9e60b3c9c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92647111"
---
# <a name="using-configuration-data-in-dsc"></a><span data-ttu-id="3cb61-105">Verwenden von Konfigurationsdaten in DSC</span><span class="sxs-lookup"><span data-stu-id="3cb61-105">Using configuration data in DSC</span></span>

> <span data-ttu-id="3cb61-106">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="3cb61-106">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="3cb61-107">Mithilfe des integrierten DSC-Parameters **ConfigurationData** können Sie Daten definieren, die innerhalb einer Konfiguration verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3cb61-107">By using the built-in DSC **ConfigurationData** parameter, you can define data that can be used within a configuration.</span></span> <span data-ttu-id="3cb61-108">Dadurch können Sie eine einzige Konfiguration erstellen, die für mehrere Knoten oder für unterschiedliche Umgebungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3cb61-108">This allows you to create a single configuration that can be used for multiple nodes or for different environments.</span></span> <span data-ttu-id="3cb61-109">Wenn Sie z.B. eine Anwendung entwickeln, können Sie eine Konfiguration für die Entwicklungs-und die Produktionsumgebung verwenden und mithilfe von Konfigurationsdaten Daten für jede Umgebung angeben.</span><span class="sxs-lookup"><span data-stu-id="3cb61-109">For example, if you are developing an application, you can use one configuration for both development and production environments, and use configuration data to specify data for each environment.</span></span>

<span data-ttu-id="3cb61-110">In diesem Thema wird die Struktur der Hashtabelle **ConfigurationData** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3cb61-110">This topic describes the structure of the **ConfigurationData** hashtable.</span></span> <span data-ttu-id="3cb61-111">Beispiele zur Verwendung von Konfigurationsdaten finden Sie unter [Trennen von Konfigurations- und Umgebungsdaten](separatingEnvData.md).</span><span class="sxs-lookup"><span data-stu-id="3cb61-111">For examples of how to use configuration data, see [Separating configuration and environment data](separatingEnvData.md).</span></span>

## <a name="the-configurationdata-common-parameter"></a><span data-ttu-id="3cb61-112">Der allgemeine Parameter „ConfigurationData“</span><span class="sxs-lookup"><span data-stu-id="3cb61-112">The ConfigurationData common parameter</span></span>

<span data-ttu-id="3cb61-113">Eine DSC-Konfiguration umfasst einen allgemeinen Parameter namens **ConfigurationData** , den Sie beim Kompilieren der Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="3cb61-113">A DSC configuration takes a common parameter, **ConfigurationData** , that you specify when you compile the configuration.</span></span> <span data-ttu-id="3cb61-114">Informationen zum Kompilieren von Konfigurationen finden Sie unter [DSC-Konfigurationen](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="3cb61-114">For information about compiling configurations, see [DSC configurations](configurations.md).</span></span>

<span data-ttu-id="3cb61-115">Der Parameter **ConfigurationData** ist eine Hashtabelle, die mindestens einen Schlüssel namens **AllNodes** benötigt.</span><span class="sxs-lookup"><span data-stu-id="3cb61-115">The **ConfigurationData** parameter is a hashtable that must have at least one key named **AllNodes** .</span></span> <span data-ttu-id="3cb61-116">Die Hashtabelle kann außerdem noch weitere Schlüssel umfassen.</span><span class="sxs-lookup"><span data-stu-id="3cb61-116">It can also have one or more other keys.</span></span>

> [!NOTE]
> <span data-ttu-id="3cb61-117">In den Beispielen in diesem Artikel wird (neben dem Schlüssel **AllNodes** ) nur ein einziger zusätzlicher Schlüssel verwendet. Dieser trägt den Namen `NonNodeData`. Sie können jedoch eine beliebige Anzahl zusätzlicher Schlüssel verwenden und diese nach Wunsch benennen.</span><span class="sxs-lookup"><span data-stu-id="3cb61-117">The examples in this topic use a single additional key (other than the named **AllNodes** key) named `NonNodeData`, but you can include any number of additional keys, and name them whatever you want.</span></span>

```powershell
$MyData =
@{
    AllNodes = @()
    NonNodeData = ""
}
```

<span data-ttu-id="3cb61-118">Der Wert des **AllNodes** -Schlüssels ist ein Array.</span><span class="sxs-lookup"><span data-stu-id="3cb61-118">The value of the **AllNodes** key is an array.</span></span> <span data-ttu-id="3cb61-119">Jedes Element dieses Arrays ist ebenfalls eine Hashtabelle, die mindestens einen Schlüssel namens **NodeName** benötigt:</span><span class="sxs-lookup"><span data-stu-id="3cb61-119">Each element of this array is also a hash table that must have at least one key named **NodeName** :</span></span>

```powershell
$MyData =
@{
    AllNodes =
    @(
        @{
            NodeName = "VM-1"
        },


        @{
            NodeName = "VM-2"
        },


        @{
            NodeName = "VM-3"
        }
    );

    NonNodeData = ""
}
```

<span data-ttu-id="3cb61-120">Sie können jeder Hashtabelle auch andere Schlüssel hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="3cb61-120">You can add other keys to each hash table as well:</span></span>

```powershell
$MyData =
@{
    AllNodes =
    @(
        @{
            NodeName = "VM-1"
            Role     = "WebServer"
        },


        @{
            NodeName = "VM-2"
            Role     = "SQLServer"
        },


        @{
            NodeName = "VM-3"
            Role     = "WebServer"
        }
    );

    NonNodeData = ""
}
```

<span data-ttu-id="3cb61-121">Um allen Knoten eine Eigenschaft zuzuweisen, können Sie ein Member des **AllNodes** -Arrays erstellen, dessen **NodeName** gleich `*` ist.</span><span class="sxs-lookup"><span data-stu-id="3cb61-121">To apply a property to all nodes, you can create a member of the **AllNodes** array that has a **NodeName** of `*`.</span></span> <span data-ttu-id="3cb61-122">Verwenden Sie z.B. folgenden Code, um allen Knoten die Eigenschaft `LogPath` zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="3cb61-122">For example, to give every node a `LogPath` property, you could do this:</span></span>

```powershell
$MyData =
@{
    AllNodes =
    @(
        @{
            NodeName     = "*"
            LogPath      = "C:\Logs"
        },


        @{
            NodeName     = "VM-1"
            Role         = "WebServer"
            SiteContents = "C:\Site1"
            SiteName     = "Website1"
        },


        @{
            NodeName     = "VM-2"
            Role         = "SQLServer"
        },


        @{
            NodeName     = "VM-3"
            Role         = "WebServer"
            SiteContents = "C:\Site2"
            SiteName     = "Website3"
        }
    );
}
```

<span data-ttu-id="3cb61-123">Dies entspricht dem Hinzufügen einer Eigenschaft namens `LogPath` mit einem Wert `"C:\Logs"` zu jedem der anderen Blöcke (`VM-1`, `VM-2` und `VM-3`).</span><span class="sxs-lookup"><span data-stu-id="3cb61-123">This is the equivalent of adding a property with a name of `LogPath` with a value of `"C:\Logs"` to each of the other blocks (`VM-1`, `VM-2`, and `VM-3`).</span></span>

## <a name="defining-the-configurationdata-hashtable"></a><span data-ttu-id="3cb61-124">Definieren der ConfigurationData-Hashtabelle</span><span class="sxs-lookup"><span data-stu-id="3cb61-124">Defining the ConfigurationData hashtable</span></span>

<span data-ttu-id="3cb61-125">Sie können **ConfigurationData** entweder als eine Variable innerhalb derselben Skriptdatei als Konfiguration (wie in unseren bisherigen Beispielen) oder in einer separaten `.psd1`-Datei definieren.</span><span class="sxs-lookup"><span data-stu-id="3cb61-125">You can define **ConfigurationData** either as a variable within the same script file as a configuration (as in our previous examples) or in a separate `.psd1` file.</span></span> <span data-ttu-id="3cb61-126">Erstellen Sie zum Definieren von **ConfigurationData** in einer `.psd1`-Datei eine Datei, die nur die Hashtabelle enthält, die die Konfigurationsdaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="3cb61-126">To define **ConfigurationData** in a `.psd1` file, create a file that contains only the hashtable that represents the configuration data.</span></span>

<span data-ttu-id="3cb61-127">Sie könnten z.B. eine Datei namens `MyData.psd1` mit folgendem Inhalt erstellen:</span><span class="sxs-lookup"><span data-stu-id="3cb61-127">For example, you could create a file named `MyData.psd1` with the following contents:</span></span>

```powershell
@{
    AllNodes =
    @(
        @{
            NodeName    = 'VM-1'
            FeatureName = 'Web-Server'
        },

        @{
            NodeName    = 'VM-2'
            FeatureName = 'Hyper-V'
        }
    )
}
```

## <a name="compiling-a-configuration-with-configuration-data"></a><span data-ttu-id="3cb61-128">Kompilieren einer Konfiguration mit Konfigurationsdaten</span><span class="sxs-lookup"><span data-stu-id="3cb61-128">Compiling a configuration with configuration data</span></span>

<span data-ttu-id="3cb61-129">Um eine Konfiguration zu kompilieren, für die Sie Konfigurationsdaten definiert haben, übergeben Sie die Konfigurationsdaten als Wert des Parameters **ConfigurationData** .</span><span class="sxs-lookup"><span data-stu-id="3cb61-129">To compile a configuration for which you have defined configuration data, you pass the configuration data as the value of the **ConfigurationData** parameter.</span></span>

<span data-ttu-id="3cb61-130">Auf diese Weise wird für jeden Eintrag im **AllNodes** -Array eine MOF-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="3cb61-130">This will create a MOF file for each entry in the **AllNodes** array.</span></span> <span data-ttu-id="3cb61-131">Jede MOF-Datei wird nach der `NodeName`-Eigenschaft des zugehörigen Arrayeintrags benannt.</span><span class="sxs-lookup"><span data-stu-id="3cb61-131">Each MOF file will be named with the `NodeName` property of the corresponding array entry.</span></span>

<span data-ttu-id="3cb61-132">Wenn Sie beispielsweise Konfigurationsdaten wie in der vorstehenden `MyData.psd1`-Datei definieren, werden beim Kompilieren einer Konfiguration sowohl `VM-1.mof`- als auch `VM-2.mof`-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="3cb61-132">For example, if you define configuration data as in the `MyData.psd1` file above, compiling a configuration would create both `VM-1.mof` and `VM-2.mof` files.</span></span>

### <a name="compiling-a-configuration-with-configuration-data-using-a-variable"></a><span data-ttu-id="3cb61-133">Kompilieren einer Konfiguration mit Konfigurationsdaten unter Verwendung einer Variablen</span><span class="sxs-lookup"><span data-stu-id="3cb61-133">Compiling a configuration with configuration data using a variable</span></span>

<span data-ttu-id="3cb61-134">Um Konfigurationsdaten zu verwenden, die in derselben `.ps1`-Datei wie die Konfiguration als Variable definiert sind, übergeben Sie den Variablennamen beim Kompilieren der Konfiguration als Wert des Parameters **ConfigurationData** :</span><span class="sxs-lookup"><span data-stu-id="3cb61-134">To use configuration data that is defined as a variable in the same `.ps1` file as the configuration, you pass the variable name as the value of the **ConfigurationData** parameter when compiling the configuration:</span></span>

```powershell
MyDscConfiguration -ConfigurationData $MyData
```

### <a name="compiling-a-configuration-with-configuration-data-using-a-data-file"></a><span data-ttu-id="3cb61-135">Kompilieren einer Konfiguration mit Konfigurationsdaten unter Verwendung einer Datendatei</span><span class="sxs-lookup"><span data-stu-id="3cb61-135">Compiling a configuration with configuration data using a data file</span></span>

<span data-ttu-id="3cb61-136">Um Konfigurationsdaten zu verwenden, die in einer PSD1-Datei definiert sind, übergeben Sie Pfad und Namen der Datei bei der Kompilierung der Konfiguration als Wert des Parameters **ConfigurationData** :</span><span class="sxs-lookup"><span data-stu-id="3cb61-136">To use configuration data that is defined in a .psd1 file, you pass the path and name of that file as the value of the **ConfigurationData** parameter when compiling the configuration:</span></span>

```powershell
MyDscConfiguration -ConfigurationData .\MyData.psd1
```

## <a name="using-configurationdata-variables-in-a-configuration"></a><span data-ttu-id="3cb61-137">Verwenden von ConfigurationData-Variablen in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3cb61-137">Using ConfigurationData variables in a configuration</span></span>

<span data-ttu-id="3cb61-138">DSC stellt die folgenden speziellen Variablen bereit, die in einem Skript verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="3cb61-138">DSC provides the following special variables that can be used in a configuration script:</span></span>

- <span data-ttu-id="3cb61-139">**$AllNodes** bezieht sich auf die gesamte, in **ConfigurationData** definierte Knotensammlung.</span><span class="sxs-lookup"><span data-stu-id="3cb61-139">**$AllNodes** refers to the entire collection of nodes defined in **ConfigurationData** .</span></span> <span data-ttu-id="3cb61-140">Sie können die **AllNodes** -Sammlung mit **.Where()** und **.ForEach()** filtern.</span><span class="sxs-lookup"><span data-stu-id="3cb61-140">You can filter the **AllNodes** collection by using **.Where()** and **.ForEach()** .</span></span>
- <span data-ttu-id="3cb61-141">**ConfigurationData** bezieht sich auf die gesamte Hashtabelle, die beim Kompilieren einer Konfiguration als Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="3cb61-141">**ConfigurationData** refers to the entire hash table that is passed as the parameter when compiling a configuration.</span></span>
- <span data-ttu-id="3cb61-142">**MyTypeName** enthält den [Namen der Konfiguration](configurations.md), in der die Variable verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3cb61-142">**MyTypeName** contains the [configuration](configurations.md) name the variable is used in.</span></span> <span data-ttu-id="3cb61-143">In der Konfiguration `MyDscConfiguration` weist `$MyTypeName` beispielsweise den Wert `MyDscConfiguration` auf.</span><span class="sxs-lookup"><span data-stu-id="3cb61-143">For example, in the configuration `MyDscConfiguration`, the `$MyTypeName` will have a value of `MyDscConfiguration`.</span></span>
- <span data-ttu-id="3cb61-144">**Nodes** bezieht sich auf einen bestimmten Eintrag in der **AllNodes** -Sammlung, nachdem sie mithilfe von **.Where()** oder **.ForEach()** gefiltert wurde.</span><span class="sxs-lookup"><span data-stu-id="3cb61-144">**Node** refers to a particular entry in the **AllNodes** collection after it is filtered by using **.Where()** or **.ForEach()** .</span></span>
  - <span data-ttu-id="3cb61-145">Weitere Informationen zu diesen Methoden finden Sie unter [about_arrays](/powershell/module/microsoft.powershell.core/about/about_arrays).</span><span class="sxs-lookup"><span data-stu-id="3cb61-145">You can read more about these methods in [about_arrays](/powershell/module/microsoft.powershell.core/about/about_arrays)</span></span>

## <a name="using-non-node-data"></a><span data-ttu-id="3cb61-146">Verwenden von Daten ohne Knoten</span><span class="sxs-lookup"><span data-stu-id="3cb61-146">Using non-node data</span></span>

<span data-ttu-id="3cb61-147">Wie wir in den vorherigen Beispielen gesehen haben, kann die Hashtabelle **ConfigurationData** neben dem erforderlichen Schlüssel **AllNodes** weitere Schlüssel aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3cb61-147">As we've seen in previous examples, the **ConfigurationData** hashtable can have one or more keys in addition to the required **AllNodes** key.</span></span> <span data-ttu-id="3cb61-148">In den Beispielen in diesem Thema wurde nur ein einziger zusätzlicher Knoten namens `NonNodeData` verwendet.</span><span class="sxs-lookup"><span data-stu-id="3cb61-148">In the examples in this topic, we have used only a single additional node, and named it `NonNodeData`.</span></span> <span data-ttu-id="3cb61-149">Sie können jedoch eine beliebige Anzahl von zusätzlichen Schlüsseln definieren und diese nach Wunsch benennen.</span><span class="sxs-lookup"><span data-stu-id="3cb61-149">However, you can define any number of additional keys, and name them anything you want.</span></span>

<span data-ttu-id="3cb61-150">Ein Beispiel für die Verwendung von Nicht-Knotendaten finden Sie unter [Trennen von Konfigurations- und Umgebungsdaten](separatingEnvData.md).</span><span class="sxs-lookup"><span data-stu-id="3cb61-150">For an example of using non-node data, see [Separating configuration and environment data](separatingEnvData.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3cb61-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3cb61-151">See Also</span></span>

- [<span data-ttu-id="3cb61-152">Optionen für Anmeldeinformationen in den Konfigurationsdaten</span><span class="sxs-lookup"><span data-stu-id="3cb61-152">Credentials Options in Configuration Data</span></span>](configDataCredentials.md)
- [<span data-ttu-id="3cb61-153">DSC-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="3cb61-153">DSC Configurations</span></span>](configurations.md)
