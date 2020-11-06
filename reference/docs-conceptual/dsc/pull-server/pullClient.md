---
ms.date: 06/12/2017
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Einrichten eines DSC-Pullclients
description: Dieser Artikel bietet eine Übersicht über die Informationen, die zum Einrichten des DSC-Pullclients verfügbar sind.
ms.openlocfilehash: 584af3aee46d801e363422ae7a197348231a1442
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646812"
---
# <a name="setting-up-a-dsc-pull-client"></a><span data-ttu-id="c355f-104">Einrichten eines DSC-Pullclients</span><span class="sxs-lookup"><span data-stu-id="c355f-104">Setting up a DSC pull client</span></span>

> <span data-ttu-id="c355f-105">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="c355f-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c355f-106">Der Pull-Server (Windows-Feature *DSC-Dienst* ) ist eine von Windows Server unterstützte Komponente, jedoch sollen keine neuen Features oder Funktionen angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="c355f-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="c355f-107">Es wird empfohlen, verwaltete Clients auf [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) umzustellen (enthält Features zusätzlich zum Pull-Server unter Windows Server) oder auf eine der [hier](pullserver.md#community-solutions-for-pull-service) aufgeführten Communitylösungen.</span><span class="sxs-lookup"><span data-stu-id="c355f-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="c355f-108">Jeder Zielknoten muss angewiesen werden, den Pullmodus zu verwenden. Außerdem muss die URL oder der Dateispeicherort angegeben werden, unter der bzw. dem der Pullserver Konfigurationen und Ressourcen abrufen kann und an die bzw. den Berichtsdaten gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c355f-108">Each target node has to be told to use pull mode and given the URL or file location where it can contact the pull server to get configurations and resources, and where it should send report data.</span></span>

<span data-ttu-id="c355f-109">In den folgenden Themen wird erläutert, wie Pullclients eingerichtet werden:</span><span class="sxs-lookup"><span data-stu-id="c355f-109">The following topics explain how to set up pull clients:</span></span>

- <span data-ttu-id="c355f-110">[Einrichten eines Pullclients mithilfe von Konfigurationsnamen](pullClientConfigNames.md)
\*-[Einrichten eines DSC-Pullclients mithilfe einer Konfigurations-ID](pullClientConfigID.md)</span><span class="sxs-lookup"><span data-stu-id="c355f-110">[Setting up a pull client using configuration names](pullClientConfigNames.md)
\*-[Setting up a pull client using configuration ID](pullClientConfigID.md)</span></span>

> [!NOTE]
> <span data-ttu-id="c355f-111">Diese Artikel beziehen sich auf PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="c355f-111">These topics apply to PowerShell 5.0.</span></span> <span data-ttu-id="c355f-112">Informationen zum Einrichten eines Pullclients in PowerShell 4.0 finden Sie unter [Einrichten eines Pullclients mithilfe der Konfigurations-ID in PowerShell 4.0](pullClientConfigID4.md).</span><span class="sxs-lookup"><span data-stu-id="c355f-112">To set up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md).</span></span>
