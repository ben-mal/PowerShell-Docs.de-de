---
ms.date: 06/09/2017
title: Erforderliche Zustimmung zur Lizenz für Skripts
description: In diesem Artikel wird erläutert, wie Sie mit Skripts arbeiten, die im PowerShell-Katalog veröffentlicht wurden und die Zustimmung zu einer Endbenutzerlizenz erfordern.
ms.openlocfilehash: d82974810fd1e73ef8d9e5771fc430d0f7964e87
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656086"
---
# <a name="requiring-license-acceptance-for-scripts"></a>Erforderliche Zustimmung zur Lizenz für Skripts

Das Zustimmen zu Lizenzen wird für Skripts nicht unterstützt. Das Szenario, in dem ein Skript von einem Modul abhängt, das die Zustimmung zur Lizenz erfordert, wird jedoch unterstützt.

Die PowerShellGet-Skriptbefehle unterstützen den Parameter **AcceptLicense** , der sich so verhält, als ob der Benutzer die Lizenz gesehen hat. Wenn **AcceptLicense** nicht angegeben ist, wird dem Benutzer die Datei `license.txt` für das abhängige Modul angezeigt, und er wird aufgefordert, die Lizenz zu akzeptieren.

## <a name="examples"></a>BEISPIELE

### <a name="example-1-install-script-with-dependencies-requiring-license-acceptance"></a>Beispiel 1: Installieren eines Skripts mit Abhängigkeiten, die die Zustimmung zur Lizenz erfordern

Das Skript „ScriptRequireLicenseAcceptance“ hängt vom Modul „ModuleRequireLicenseAcceptance“ ab. Der Benutzer wird zum Akzeptieren der Lizenz aufgefordert.

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance

License Acceptance
MIT License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

### <a name="example-2-install-script-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a>Beispiel 2: Installieren eines Skripts mit Abhängigkeiten, die die Zustimmung zur Lizenz erfordern, und -AcceptLicense

Das Skript „ScriptRequireLicenseAcceptance“ hängt vom Modul „ModuleRequireLicenseAcceptance“ ab. Der Benutzer wird nicht zum Akzeptieren der Lizenz aufgefordert, weil -AcceptLicense angegeben wurde.

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance -AcceptLicense
```

## <a name="more-details"></a>Weitere Informationen

- [Unterstützung für das Anfordern der Zustimmung zur Lizenz für Module](module-license-acceptance.md)
- [Unterstützung für das Anfordern der Zustimmung zur Lizenz in PowerShellGallery](../how-to/working-with-packages/packages-that-require-license-acceptance.md)
- [Erforderliche Zustimmung zur Lizenz für die Bereitstellung in Azure Automation](../how-to/working-with-packages/deploy-to-azure-automation.md)
