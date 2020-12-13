---
ms.date: 03/22/2012
ms.topic: reference
title: Zulässige Dateitypen in aktualisierbaren CAB-Hilfedateien
description: Zulässige Dateitypen in aktualisierbaren CAB-Hilfedateien
ms.openlocfilehash: bb69b8b89a9a3a5c8c00059ec404a4d41a5db9a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654734"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="fcf50-103">Zulässige Dateitypen in aktualisierbaren CAB-Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="fcf50-103">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="fcf50-104">Der Inhalt nicht komprimierter CAB-Dateien ist standardmäßig auf 1 GB beschränkt.</span><span class="sxs-lookup"><span data-stu-id="fcf50-104">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="fcf50-105">Um diese Beschränkung zu umgehen, müssen die Benutzer den **Force** -Parameter der Cmdlets " [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) " und " [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) " verwenden.</span><span class="sxs-lookup"><span data-stu-id="fcf50-105">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="fcf50-106">Um die Sicherheit von Hilfedateien sicherzustellen, die aus dem Internet heruntergeladen werden, kann eine aktualisierbare CAB-Hilfedatei nur die unten aufgeführten Dateitypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="fcf50-106">To assure the security of help files that are downloaded from the internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="fcf50-107">Das [Update-Help-](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlet überprüft alle Dateien anhand der Hilfe Themen Schemas.</span><span class="sxs-lookup"><span data-stu-id="fcf50-107">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="fcf50-108">Wenn das `Update-Help` Cmdlet auf eine Datei trifft, die ungültig ist oder kein zulässiger Typ ist, wird die ungültige Datei nicht installiert, und die Installation von Dateien aus dem CAB auf dem Computer des Benutzers wird beendet.</span><span class="sxs-lookup"><span data-stu-id="fcf50-108">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="fcf50-109">XML-basierte Hilfe Themen für Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fcf50-109">XML-based help topics for cmdlets.</span></span>
- <span data-ttu-id="fcf50-110">XML-basierte Hilfe Themen für Skripts und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="fcf50-110">XML-based help topics for scripts and functions.</span></span>
- <span data-ttu-id="fcf50-111">XML-basierte Hilfe Themen für PowerShell-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="fcf50-111">XML-based help topics for PowerShell providers.</span></span>
- <span data-ttu-id="fcf50-112">Text basierte Hilfe Themen, z. b. Informationen zu Themen.</span><span class="sxs-lookup"><span data-stu-id="fcf50-112">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="fcf50-113">Mit [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) werden die CAB-Inhalte überprüft, wenn die CAB-Datei entpackt wird.</span><span class="sxs-lookup"><span data-stu-id="fcf50-113">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="fcf50-114">Wenn `Update-Help` nicht kompatible Dateitypen in einer aktualisierbaren Hilfe-CAB-Datei findet, wird ein Beendigungs Fehler generiert und der Vorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="fcf50-114">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="fcf50-115">Er installiert keine Hilfedateien aus dem CAB, auch die von kompatiblen Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="fcf50-115">It does not install any help files from the CAB, even those of compliant file types.</span></span>
