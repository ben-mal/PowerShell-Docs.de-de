---
description: Erläutert, wie Sie die Funktion "mit PowerShell ausführen" verwenden, um ein Skript von einem Dateisystem Laufwerk auszuführen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_run_with_powershell?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Run_With_PowerShell
ms.openlocfilehash: 83931fcfcc89340b1d4958e41cb182642a554737
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223716"
---
# <a name="about-run-with-powershell"></a>Informationen zum Ausführen mit PowerShell

## <a name="short-description"></a>KURZE BESCHREIBUNG
Erläutert, wie Sie die Funktion "mit PowerShell ausführen" verwenden, um ein Skript von einem Dateisystem Laufwerk auszuführen.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Ab Windows PowerShell 3,0 können Sie die Funktion "mit PowerShell ausführen" verwenden, um Skripts aus dem Datei-Explorer in Windows 8 und Windows Server 2012 und aus Windows-Explorer in früheren Versionen von Windows auszuführen.

Die Funktion "mit PowerShell ausführen" dient zum Ausführen von Skripts, die nicht über erforderliche Parameter verfügen und keine Ausgabe an die Eingabeaufforderung zurückgeben.

Wenn Sie die Funktion "mit PowerShell ausführen" verwenden, wird das PowerShell-Konsolenfenster nur kurz angezeigt, wenn überhaupt. Es ist nicht möglich, mit ihm zu interagieren.

So verwenden Sie die Funktion "mit PowerShell ausführen":

Klicken Sie im Datei-Explorer (oder Windows-Explorer) mit der rechten Maustaste auf den Namen der Skriptdatei, und wählen Sie dann die Option mit PowerShell ausführen aus.

Die Funktion "mit PowerShell ausführen" startet eine PowerShell-Sitzung mit der Ausführungs Richtlinie "Bypass", führt das Skript aus und schließt die Sitzung.

Er führt einen Befehl aus, der das folgende Format aufweist:

```
PowerShell.exe -File <FileName> -ExecutionPolicy Bypass
```

"Mit PowerShell ausführen" legt die Umgehungs Ausführungs Richtlinie nur für die Sitzung (die aktuelle Instanz des PowerShell-Prozesses) fest, in der das Skript ausgeführt wird.
Diese Funktion ändert nicht die Ausführungs Richtlinie für den Computer oder den Benutzer.

Die Funktion "mit PowerShell ausführen" ist nur durch die AllSigned-Ausführungs Richtlinie betroffen. Wenn die AllSigned-Ausführungs Richtlinie für den Computer oder den Benutzer wirksam ist, führt "Run with PowerShell" nur signierte Skripts aus. "Run with PowerShell" ist von keiner anderen Ausführungs Richtlinie betroffen. Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).

Hinweis zur Problembehandlung: Wenn Sie mit PowerShell ausführen, werden Sie möglicherweise zur Bestätigung der Änderung der Ausführungs Richtlinie aufgefordert.

## <a name="see-also"></a>SIEHE AUCH

[about_Execution_Policies](about_Execution_Policies.md)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Scripts](about_Scripts.md)

