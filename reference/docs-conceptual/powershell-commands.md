---
title: Was ist ein PowerShell-Befehl?
description: Mit PowerShell können Sie jeden Befehl ausführen, der auf Ihrem System verfügbar ist, und darüber hinaus PowerShell-spezifische Befehle, die als Cmdlets bezeichnet werden.
ms.date: 03/31/2021
ms.openlocfilehash: b6e54349ec15df3327c1f0525dce1a30ad35a6ac
ms.sourcegitcommit: eeedd4472b6cc6158494296c355579791e688baa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "106104013"
---
# <a name="powershell-commands"></a>PowerShell-Befehle

Mit PowerShell können Sie jeden Befehl ausführen, der auf Ihrem System verfügbar ist, einschließlich PowerShell-spezifischer Befehle, die als Cmdlets (gesprochen „Command-Lets“) bezeichnet werden.

## <a name="what-is-a-cmdlet"></a>Was ist ein Cmdlet?

Ein Cmdlet ist ein einzelner Befehl, der der Pipelinesemantik von PowerShell unterliegt und in der Regel ein .NET-Objekt zurückgibt. Cmdlets sind native PowerShell-Befehle, keine eigenständig ausführbaren Dateien. Cmdlets werden in PowerShell-Modulen gesammelt, die bei Bedarf geladen werden können. Cmdlets können in jeder kompilierten .NET-Sprache oder in der eigentlichen PowerShell-Skriptsprache geschrieben werden.

## <a name="cmdlet-names"></a>Cmdlet-Namen

PowerShell verwendet ein _Verb-Substantiv_-Namenspaar zur Benennung von Cmdlets. Beispielsweise wird das in PowerShell enthaltene Cmdlet `Get-Command` dazu verwendet, alle Cmdlets abzurufen, die in der Befehlsshell registriert sind. Das Verb gibt die Aktion an, die das Cmdlet ausführt, und das Substantiv identifiziert die Ressource, für die das Cmdlet seine Aktion ausführt.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu PowerShell und zum Auffinden anderer Cmdlets finden Sie im PowerShell-Bits-Tutorial zum [PowerShell entdecken](learn/tutorials/01-discover-powershell.md).

Informationen zum Erstellen eigener Cmdlets finden Sie in den folgenden Ressourcen:

Skriptbasierte Cmdlets

- [about_Functions_Advanced](/powershell/module/microsoft.powershell.core/about/about_functions_advanced)
- [about_Functions_CmdletBindingAttribute](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute)
- [about_Functions_Advanced_Methods](/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods)

Kompilierte Cmdlets (PowerShell SDK-Dokumentation)

- [Cmdlet-Übersicht](developer/cmdlet/cmdlet-overview.md)
