---
ms.date: 01/25/2021
title: Problembehandlung für Cmdlets
description: Dieser Artikel bietet Informationen und Anweisungen zum Beheben von Fehlern mithilfe des PowerShell-Katalogs.
ms.openlocfilehash: 8139147683b655b5f8532c3068387db6df12a98f
ms.sourcegitcommit: 0f003644684422e425a59b7361121e05ac772e15
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98771815"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="5975a-103">Problembehandlung für Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5975a-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="5975a-104">Gewusst wie: Beheben des Fehlers „WARNUNG: Fehler beim Herunterladen des Pakets "Name Ihres Pakets"“</span><span class="sxs-lookup"><span data-stu-id="5975a-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="5975a-105">Es wurde berichtet, dass bei Ausführung von `Install-Module` oder `Update-Module` auf einigen Computern ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="5975a-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="5975a-106">Unseren Untersuchungen zufolge hängt dieses Problem mit der Netzwerkverbindung zusammen.</span><span class="sxs-lookup"><span data-stu-id="5975a-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="5975a-107">Der NuGet-Anbieter wurde vor Kurzem aktualisiert, sodass Pakete nun zuverlässig heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="5975a-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="5975a-108">Befolgen Sie die unten stehenden Anweisungen, um den aktuellen Build des NuGet-Anbieters zu installieren und anschließend Ihr Modul zu installieren oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5975a-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="5975a-109">Im nachfolgenden Beispiel wird das Modul „Azure“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="5975a-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a><span data-ttu-id="5975a-110">Erforderliche Netzwerkendpunkte</span><span class="sxs-lookup"><span data-stu-id="5975a-110">Required network endpoints</span></span>

<span data-ttu-id="5975a-111">Die Install- und Update-Cmdlets erfordern einen Internetzugang, um eine Verbindung mit den vom PowerShell-Katalog verwendeten Netzwerkendpunkten herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5975a-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="5975a-112">Stellen Sie sicher, dass Ihre Netzwerkzugriffsrichtlinien das Herstellen einer Verbindung mit den folgenden Endpunkten zulassen.</span><span class="sxs-lookup"><span data-stu-id="5975a-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="5975a-113">`psg-prod-eastus.azureedge.net`: CDN-Hostname</span><span class="sxs-lookup"><span data-stu-id="5975a-113">`psg-prod-eastus.azureedge.net` - CDN hostname</span></span>
- <span data-ttu-id="5975a-114">`az818661.vo.msecnd.net`: CDN-Hostname</span><span class="sxs-lookup"><span data-stu-id="5975a-114">`az818661.vo.msecnd.net` - CDN hostname</span></span>
- <span data-ttu-id="5975a-115">`devopsgallerystorage.blob.core.windows.net`: Hostname des Speicherkontos</span><span class="sxs-lookup"><span data-stu-id="5975a-115">`devopsgallerystorage.blob.core.windows.net` - storage account hostname</span></span>
- <span data-ttu-id="5975a-116">`*.powershellgallery.com`: Website</span><span class="sxs-lookup"><span data-stu-id="5975a-116">`*.powershellgallery.com` - website</span></span>
- <span data-ttu-id="5975a-117">`go.microsoft.com`: Umleitungsdienst</span><span class="sxs-lookup"><span data-stu-id="5975a-117">`go.microsoft.com` - redirection service</span></span>
- <span data-ttu-id="5975a-118">`onegetcdn.azureedge.net`: führt einen Bootstrapvorgang für den NuGet-Anbieter in `PowerShellGet/PackageManagement` durch</span><span class="sxs-lookup"><span data-stu-id="5975a-118">`onegetcdn.azureedge.net` - bootstrap the NuGet Provider in `PowerShellGet/PackageManagement`</span></span>

> [!NOTE]
> <span data-ttu-id="5975a-119">Cmdlets, die mit dem PowerShell-Katalog interagieren, können unerwartet fehlschlagen, wenn es zu einem Ausfall der Dienste des PowerShell-Katalogs kommt.</span><span class="sxs-lookup"><span data-stu-id="5975a-119">Cmdlets that interact with the PowerShell Gallery can fail with unexpected errors when there is an outage of the PowerShell Gallery services.</span></span> <span data-ttu-id="5975a-120">Informationen zum aktuellen Status des PowerShell-Katalogs finden Sie auf der GitHub-Seite [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md).</span><span class="sxs-lookup"><span data-stu-id="5975a-120">To see the current status of the PowerShell Gallery, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>
