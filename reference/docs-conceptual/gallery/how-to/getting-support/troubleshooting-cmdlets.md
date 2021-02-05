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
# <a name="troubleshooting-cmdlets"></a>Problembehandlung für Cmdlets

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>Gewusst wie: Beheben des Fehlers „WARNUNG: Fehler beim Herunterladen des Pakets "Name Ihres Pakets"“

Es wurde berichtet, dass bei Ausführung von `Install-Module` oder `Update-Module` auf einigen Computern ein Fehler auftritt. Unseren Untersuchungen zufolge hängt dieses Problem mit der Netzwerkverbindung zusammen. Der NuGet-Anbieter wurde vor Kurzem aktualisiert, sodass Pakete nun zuverlässig heruntergeladen werden können. Befolgen Sie die unten stehenden Anweisungen, um den aktuellen Build des NuGet-Anbieters zu installieren und anschließend Ihr Modul zu installieren oder zu aktualisieren. Im nachfolgenden Beispiel wird das Modul „Azure“ verwendet.

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a>Erforderliche Netzwerkendpunkte

Die Install- und Update-Cmdlets erfordern einen Internetzugang, um eine Verbindung mit den vom PowerShell-Katalog verwendeten Netzwerkendpunkten herzustellen. Stellen Sie sicher, dass Ihre Netzwerkzugriffsrichtlinien das Herstellen einer Verbindung mit den folgenden Endpunkten zulassen.

- `psg-prod-eastus.azureedge.net`: CDN-Hostname
- `az818661.vo.msecnd.net`: CDN-Hostname
- `devopsgallerystorage.blob.core.windows.net`: Hostname des Speicherkontos
- `*.powershellgallery.com`: Website
- `go.microsoft.com`: Umleitungsdienst
- `onegetcdn.azureedge.net`: führt einen Bootstrapvorgang für den NuGet-Anbieter in `PowerShellGet/PackageManagement` durch

> [!NOTE]
> Cmdlets, die mit dem PowerShell-Katalog interagieren, können unerwartet fehlschlagen, wenn es zu einem Ausfall der Dienste des PowerShell-Katalogs kommt. Informationen zum aktuellen Status des PowerShell-Katalogs finden Sie auf der GitHub-Seite [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md).
