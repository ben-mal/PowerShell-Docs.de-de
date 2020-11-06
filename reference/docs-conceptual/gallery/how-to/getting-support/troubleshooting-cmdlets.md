---
ms.date: 06/12/2017
title: Problembehandlung für Cmdlets
description: Dieser Artikel bietet Informationen und Anweisungen zum Beheben von Fehlern mithilfe des PowerShell-Katalogs.
ms.openlocfilehash: db9e58c185c6f3bca26ff3639af85fa2dba48909
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661063"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="d0334-103">Problembehandlung für Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d0334-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="d0334-104">Gewusst wie: Beheben des Fehlers „WARNUNG: Fehler beim Herunterladen des Pakets "Name Ihres Pakets"“</span><span class="sxs-lookup"><span data-stu-id="d0334-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="d0334-105">Es wurde berichtet, dass bei Ausführung von `Install-Module` oder `Update-Module` auf einigen Computern ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="d0334-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="d0334-106">Unseren Untersuchungen zufolge hängt dieses Problem mit der Netzwerkverbindung zusammen.</span><span class="sxs-lookup"><span data-stu-id="d0334-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="d0334-107">Der NuGet-Anbieter wurde vor Kurzem aktualisiert, sodass Pakete nun zuverlässig heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="d0334-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="d0334-108">Befolgen Sie die unten stehenden Anweisungen, um den aktuellen Build des NuGet-Anbieters zu installieren und anschließend Ihr Modul zu installieren oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d0334-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="d0334-109">Im nachfolgenden Beispiel wird das Modul „Azure“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0334-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

### <a name="required-network-endpoints"></a><span data-ttu-id="d0334-110">Erforderliche Netzwerkendpunkte</span><span class="sxs-lookup"><span data-stu-id="d0334-110">Required network endpoints</span></span>

<span data-ttu-id="d0334-111">Die Install- und Update-Cmdlets erfordern einen Internetzugang, um eine Verbindung mit den vom PowerShell-Katalog verwendeten Netzwerkendpunkten herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d0334-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="d0334-112">Stellen Sie sicher, dass Ihre Netzwerkzugriffsrichtlinien das Herstellen einer Verbindung mit den folgenden Endpunkten zulassen.</span><span class="sxs-lookup"><span data-stu-id="d0334-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="d0334-113">oneget.org</span><span class="sxs-lookup"><span data-stu-id="d0334-113">oneget.org</span></span>
- <span data-ttu-id="d0334-114">go.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d0334-114">go.microsoft.com</span></span>
- <span data-ttu-id="d0334-115">az818661.vo.msecnd.net</span><span class="sxs-lookup"><span data-stu-id="d0334-115">az818661.vo.msecnd.net</span></span>
- <span data-ttu-id="d0334-116">www.powershellgallery.com</span><span class="sxs-lookup"><span data-stu-id="d0334-116">www.powershellgallery.com</span></span>
- <span data-ttu-id="d0334-117">devopsgallerystorage.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="d0334-117">devopsgallerystorage.blob.core.windows.net</span></span>
