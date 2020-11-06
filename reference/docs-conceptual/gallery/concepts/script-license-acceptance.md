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
# <a name="requiring-license-acceptance-for-scripts"></a><span data-ttu-id="c4fa4-103">Erforderliche Zustimmung zur Lizenz für Skripts</span><span class="sxs-lookup"><span data-stu-id="c4fa4-103">Requiring license acceptance for scripts</span></span>

<span data-ttu-id="c4fa4-104">Das Zustimmen zu Lizenzen wird für Skripts nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c4fa4-104">License Acceptance is not supported for scripts.</span></span> <span data-ttu-id="c4fa4-105">Das Szenario, in dem ein Skript von einem Modul abhängt, das die Zustimmung zur Lizenz erfordert, wird jedoch unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c4fa4-105">However, the scenario where a script depends on a module that requires license acceptance is supported.</span></span>

<span data-ttu-id="c4fa4-106">Die PowerShellGet-Skriptbefehle unterstützen den Parameter **AcceptLicense** , der sich so verhält, als ob der Benutzer die Lizenz gesehen hat.</span><span class="sxs-lookup"><span data-stu-id="c4fa4-106">The PowerShellGet script commands support the parameter **AcceptLicense** that behaves as though user saw the license.</span></span> <span data-ttu-id="c4fa4-107">Wenn **AcceptLicense** nicht angegeben ist, wird dem Benutzer die Datei `license.txt` für das abhängige Modul angezeigt, und er wird aufgefordert, die Lizenz zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="c4fa4-107">If **AcceptLicense** is not specified the user is shown the `license.txt` file for dependent module and prompted to accept the license.</span></span>

## <a name="examples"></a><span data-ttu-id="c4fa4-108">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c4fa4-108">EXAMPLES</span></span>

### <a name="example-1-install-script-with-dependencies-requiring-license-acceptance"></a><span data-ttu-id="c4fa4-109">Beispiel 1: Installieren eines Skripts mit Abhängigkeiten, die die Zustimmung zur Lizenz erfordern</span><span class="sxs-lookup"><span data-stu-id="c4fa4-109">Example 1: Install Script with dependencies requiring license acceptance</span></span>

<span data-ttu-id="c4fa4-110">Das Skript „ScriptRequireLicenseAcceptance“ hängt vom Modul „ModuleRequireLicenseAcceptance“ ab.</span><span class="sxs-lookup"><span data-stu-id="c4fa4-110">Script 'ScriptRequireLicenseAcceptance' depends on module 'ModuleRequireLicenseAcceptance'.</span></span> <span data-ttu-id="c4fa4-111">Der Benutzer wird zum Akzeptieren der Lizenz aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c4fa4-111">User is prompted to Accept License.</span></span>

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

### <a name="example-2-install-script-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a><span data-ttu-id="c4fa4-112">Beispiel 2: Installieren eines Skripts mit Abhängigkeiten, die die Zustimmung zur Lizenz erfordern, und -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="c4fa4-112">Example 2: Install Script with dependencies requiring license acceptance and -AcceptLicense</span></span>

<span data-ttu-id="c4fa4-113">Das Skript „ScriptRequireLicenseAcceptance“ hängt vom Modul „ModuleRequireLicenseAcceptance“ ab.</span><span class="sxs-lookup"><span data-stu-id="c4fa4-113">Script 'ScriptRequireLicenseAcceptance' depends on module 'ModuleRequireLicenseAcceptance'.</span></span> <span data-ttu-id="c4fa4-114">Der Benutzer wird nicht zum Akzeptieren der Lizenz aufgefordert, weil -AcceptLicense angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c4fa4-114">User is not prompted to accept license as -AcceptLicense is specified.</span></span>

```PowerShell
PS> Install-Script -Name ScriptRequireLicenseAcceptance -AcceptLicense
```

## <a name="more-details"></a><span data-ttu-id="c4fa4-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4fa4-115">More details</span></span>

- [<span data-ttu-id="c4fa4-116">Unterstützung für das Anfordern der Zustimmung zur Lizenz für Module</span><span class="sxs-lookup"><span data-stu-id="c4fa4-116">Require License Acceptance support for Modules</span></span>](module-license-acceptance.md)
- [<span data-ttu-id="c4fa4-117">Unterstützung für das Anfordern der Zustimmung zur Lizenz in PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="c4fa4-117">Require License Acceptance support on PowerShellGallery</span></span>](../how-to/working-with-packages/packages-that-require-license-acceptance.md)
- [<span data-ttu-id="c4fa4-118">Erforderliche Zustimmung zur Lizenz für die Bereitstellung in Azure Automation</span><span class="sxs-lookup"><span data-stu-id="c4fa4-118">Require License Acceptance on Deploy to Azure Automation</span></span>](../how-to/working-with-packages/deploy-to-azure-automation.md)
