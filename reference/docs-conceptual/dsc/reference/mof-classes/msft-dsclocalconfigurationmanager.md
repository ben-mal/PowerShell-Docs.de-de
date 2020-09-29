---
ms.date: 07/14/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: MSFT_DSCLocalConfigurationManager-Klasse
ms.openlocfilehash: 20c9ac5128fcfbbcb2113b89d9e5b53693744b45
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464280"
---
# <a name="msft_dsclocalconfigurationmanager-class"></a>MSFT_DSCLocalConfigurationManager-Klasse

Der lokale Konfigurations-Manager, der die Zustände von Konfigurationsdateien steuert und den Konfigurations-Agent verwendet, um die Konfigurationen anzuwenden.

Die folgende Syntax wurde aus MOF-Code (Managed Object Format, verwaltetes Objektformat) vereinfacht und enthält alle geerbten Eigenschaften.

## <a name="syntax"></a>Syntax

```
[ClassVersion("1.0.0"), dynamic, provider("dsccore"), AMENDMENT]
class MSFT_DSCLocalConfigurationManager
{
};
```

## <a name="members"></a>Members

Die **MSFT_DSCLocalConfigurationManager**-Klasse hat folgende Member:

- [Methoden][]

### <a name="methods"></a>Methoden

Die **MSFT_DSCLocalConfigurationManager**-Klasse enthält diese Methoden.

|Methoden |BESCHREIBUNG |
|:--- |:---|
| [ApplyConfiguration(boolean)](msft-dsclocalconfigurationmanager-applyconfiguration.md)| Verwendet den Konfigurations-Agent, um die ausstehende Konfiguration anzuwenden.|
| [DisableDebugConfiguration()](msft-dsclocalconfigurationmanager-disabledebugconfiguration.md)| Deaktiviert das Debuggen von DSC-Ressourcen.|
| [EnableDebugConfiguration(boolean)](msft-dsclocalconfigurationmanager-enabledebugconfiguration.md)| Aktiviert das Debuggen von DSC-Ressourcen.|
| [GetConfiguration()](msft-dsclocalconfigurationmanager-getconfiguration.md)| Sendet das Konfigurationsdokument an den verwalteten Knoten und verwendet die **Get**-Methode des Konfigurations-Agents, um die Konfiguration anzuwenden.|
| [GetConfigurationResultOutput](msft-dsclocalconfigurationmanager-getconfigurationresultoutput.md)| Ruft die Konfigurations-Agent-Ausgabe im Zusammenhang mit einem bestimmten Auftrag ab.|
| [GetConfigurationStatus](msft-dsclocalconfigurationmanager-getconfigurationstatus.md)| Abrufen des Konfigurationsstatusverlaufs.|
| [GetMetaConfiguration](msft-dsclocalconfigurationmanager-getmetaconfiguration.md)| Ruft die Einstellungen des lokalen Konfigurations-Managers ab, die zur Steuerung des Konfigurations-Agents verwendet werden.|
| [PerformRequiredConfigurationChecks](msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)| Startet die Konsistenzprüfung.|
| [RemoveConfiguration](msft-dsclocalconfigurationmanager-removeconfiguration.md)| Entfernt die Konfigurationsdateien.|
| [ResourceGet](msft-dsclocalconfigurationmanager-resourceget.md)| Ruft direkt die **Get**-Methode einer DSC-Ressource auf.|
| [ResourceSet](msft-dsclocalconfigurationmanager-resourceset.md)| Ruft direkt die **Set**-Methode einer DSC-Ressource auf.|
| [ResourceTest](msft-dsclocalconfigurationmanager-resourcetest.md)| Ruft direkt die **Test**-Methode einer DSC-Ressource auf.|
| [RollBack](msft-dsclocalconfigurationmanager-rollback.md)| Führt einen Rollback zu einer vorherigen Konfiguration aus.|
| [SendConfiguration](msft-dsclocalconfigurationmanager-sendconfiguration.md)| Sendet das Konfigurationsdokument an den verwalteten Knoten und speichert es als ausstehende Änderung.|
| [SendConfigurationApply](msft-dsclocalconfigurationmanager-sendconfigurationapply.md)| Sendet das Konfigurationsdokument an den verwalteten Knoten und verwendet den Konfigurations-Agent zum Anwenden der Konfiguration.|
| [SendConfigurationApplyAsync](msft-dsclocalconfigurationmanager-sendconfigurationapplyasync.md)| Senden des Konfigurationsdokuments an den verwalteten Knoten und Beginnen mit der Verwendung des Konfigurations-Agents zum Anwenden der Konfiguration. Verwenden Sie „GetConfigurationResultOutput“, um Ergebnisausgaben abzurufen.|
| [SendMetaConfigurationApply](msft-dsclocalconfigurationmanager-sendmetaconfigurationapply.md)| Legt die Einstellungen des lokalen Konfigurations-Managers fest, die zur Steuerung des Konfigurations-Agents verwendet werden.|
| [StopConfiguration](msft-dsclocalconfigurationmanager-stopconfiguration.md)| Beende die Konfiguration, die gerade ausgeführt wird.|
| [TestConfiguration](msft-dsclocalconfigurationmanager-testconfiguration.md)| Sendet das Konfigurationsdokument an den verwalteten Knoten und überprüft die aktuelle Konfiguration anhand dieses Dokuments.|

## <a name="requirements"></a>Requirements (Anforderungen)

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration
