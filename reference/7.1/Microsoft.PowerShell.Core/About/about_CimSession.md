---
description: Beschreibt ein **cimsession** -Objekt und den Unterschied zwischen CIM-Sitzungen und PowerShell-Sitzungen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_cimsession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CimSession
ms.openlocfilehash: d0d926efb3f534705f2cf3840e72408ac80b75c7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224132"
---
# <a name="about-cimsession"></a>Informationen zu cimsession

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt ein **cimsession** -Objekt und den Unterschied zwischen CIM-Sitzungen und PowerShell-Sitzungen.

## <a name="long-description"></a>Lange Beschreibung

Eine Common Information Model-Sitzung (CIM) ist ein Client seitiges Objekt, das eine Verbindung mit einem lokalen Computer oder einem Remote Computer darstellt. Sie können CIM-Sitzungen als Alternative zu PowerShell-Sitzungen (pssessions) verwenden. Beide Ansätze haben Vorteile.

Mit dem `New-CimSession` Cmdlet können Sie eine CIM-Sitzung erstellen, die Informationen zu einer Verbindung enthält, wie z. b. den Computernamen, das für die Verbindung verwendete Protokoll, die Sitzungs-ID und die Instanz-ID.

Nachdem Sie ein **cimsession** -Objekt erstellt haben, das Informationen angibt, die zum Herstellen einer Verbindung erforderlich sind, wird die Verbindung von PowerShell nicht sofort hergestellt. Wenn ein Cmdlet die CIM-Sitzung verwendet, stellt PowerShell eine Verbindung mit dem angegebenen Computer her, und wenn das Cmdlet abgeschlossen ist, beendet PowerShell die Verbindung.

Wenn Sie eine **PSSession** erstellen, anstatt eine CIM-Sitzung zu verwenden, überprüft PowerShell die Verbindungseinstellungen und stellt dann die Verbindung her und verwaltet Sie. Wenn Sie CIM-Sitzungen verwenden, öffnet PowerShell erst eine Netzwerkverbindung, wenn dies erforderlich ist. Weitere Informationen zu PowerShell-Sitzungen finden Sie unter [about_PSSessions](about_PSSessions.md).

## <a name="when-to-use-a-cim-session"></a>Verwendung einer CIM-Sitzung

Nur Cmdlets, die mit einem Windows-Verwaltungsinstrumentation (WMI)-Anbieter oder CIM over WS-Man arbeiten, akzeptieren CIM-Sitzungen. Verwenden Sie für andere Cmdlets **pssessions**.

Wenn Sie eine CIM-Sitzung verwenden, führt PowerShell das Cmdlet auf dem lokalen Client aus. Er stellt mithilfe der CIM-Sitzung eine Verbindung mit dem WMI-Anbieter her. Der Zielcomputer erfordert weder PowerShell noch eine Version des Windows-Betriebssystems.

Im Gegensatz dazu wird ein Cmdlet mit einer **PSSession** auf dem Zielcomputer ausgeführt.
Hierfür ist PowerShell auf dem Zielsystem erforderlich. Außerdem sendet das Cmdlet Daten zurück an den lokalen Computer. PowerShell verwaltet die über die Verbindung gesendeten Daten und behält die Größe in den von Windows-Remoteverwaltung (WinRM) festgelegten Grenzwerten. Die WinRM-Limits werden von CIM-Sitzungen nicht erzwungen.

## <a name="using-cdxml-cmdlets"></a>Verwenden von cdxml-Cmdlets

CIM-basierte Cmdlet-Definitions-XML-Cmdlets (Cmdlet Definition XML) können für die Verwendung eines beliebigen WMI-Anbieters geschrieben werden. Alle WMI-Anbieter verwenden **cimsession** -Objekte. Weitere Informationen zu cdxml finden Sie unter [cdxml-Definition und-Begriffe](/previous-versions/windows/desktop/wmi_v2/cdxml-overview).

Cdxml-Cmdlets verfügen über einen automatischen **cimsession** -Parameter, der ein Array von **cimsession** -Objekten annehmen kann. PowerShell schränkt die Anzahl gleichzeitiger CIM-Verbindungen standardmäßig auf 15 ein. Dieser Grenzwert kann durch cdxml-Cmdlets überschrieben werden, die " **throttlelimit** " implementieren. Weitere Informationen zu " **throttlelimit** " finden Sie in der Dokumentation zu den einzelnen Cmdlets.

## <a name="see-also"></a>SIEHE AUCH

[New-CimSession](xref:CimCmdlets.New-CimSession)

[about_PSSessions](about_PSSessions.md)

