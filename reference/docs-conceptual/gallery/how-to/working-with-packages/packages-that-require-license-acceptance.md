---
ms.date: 06/12/2017
title: Erforderliche Zustimmung zur Lizenz
description: Anzeigen der Paketlizenz auf der Seite mit den Elementdetails
ms.openlocfilehash: 0d8a9ed671f7993726bc3fa41d11159b366e5a28
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662303"
---
# <a name="require-license-acceptance"></a>Erforderliche Zustimmung zur Lizenz

Der Text zum Anfordern der Zustimmung zur Lizenz wird auf der Seite mit den Elementdetails für Module angezeigt, für die die Zustimmung zur Lizenz erforderlich ist. Die Lizenz für das Modul kann durch Klicken auf den Link **„License.txt“ anzeigen** angezeigt werden.

![Erforderliche Zustimmung zur Lizenz](media/packages-that-require-license-acceptance/RequireLicenseAcceptance.png)

Benutzer werden beim Installieren, Speichern oder Aktualisieren des Moduls über PowerShellGet oder bei der Bereitstellung für Azure Automation aufgefordert, die Lizenz zu akzeptieren.

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a>Erforderliche Zustimmung zur Lizenz für die Bereitstellung in Azure Automation

Wenn für das Modul, das in Azure Automation bereitgestellt wird, die Zustimmung zur Lizenz erforderlich ist, wird auf der Portaloberfläche ein Haftungsausschluss mit folgender Meldung angezeigt: „Für dieses Modul muss der Lizenz zugestimmt werden. Indem Sie auf ‚OK‘ klicken, akzeptieren Sie die Lizenzbedingungen.“

![Für die Bereitstellung in Azure Automation ist die Zustimmung zur Lizenz erforderlich.](media/packages-that-require-license-acceptance/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a>Weitere Informationen

[Erforderliche Zustimmung zur Lizenz in PowerShellGet](../../concepts/module-license-acceptance.md)
[Azure Automation-Website](/azure/automation)
