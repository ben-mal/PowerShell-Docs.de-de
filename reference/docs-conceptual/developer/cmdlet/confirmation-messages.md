---
ms.date: 09/13/2016
ms.topic: reference
title: Bestätigungsmeldungen
description: Bestätigungsmeldungen
ms.openlocfilehash: 76302b2f8d8ca6dcdfe1b3c36f71aad23a53f7cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355186"
---
# <a name="confirmation-messages"></a>Bestätigungsmeldungen

Im folgenden finden Sie unterschiedliche Bestätigungsmeldungen, die je nach den Varianten der Methoden " [System. Management. Automation. Cmdlet. Schulter dprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) " und " [System. Management. Automation. Cmdlet. schuldcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) " angezeigt werden können.

> [!IMPORTANT]
> Beispielcode, der zeigt, wie Bestätigungen angefordert werden, finden Sie unter [anfordern von Bestätigungen](./how-to-request-confirmations.md).

## <a name="specifying-the-resource"></a>Angeben der Ressource

Sie können die zu ändernde Ressource angeben, indem Sie das [System. Management. Automation. Cmdlet aufrufen. Displayproperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Methode. In diesem Fall stellen Sie die Ressource mithilfe des `target` -Parameters der-Methode bereit, und der Vorgang wird von Windows PowerShell hinzugefügt. In der folgenden Meldung ist der Text "MyResource" die Ressource, auf die reagiert wird, und der Vorgang ist der Name des Befehls, der den-Vorgang ausführt.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Wenn der Benutzer für die Bestätigungs Anforderung **Ja** oder **Ja** (wie im folgenden Beispiel gezeigt) auswählt, wird ein [System. Management. Automation. Cmdlet. ermdcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) -Methode aufgerufen, wodurch eine zweite Bestätigungsmeldung angezeigt wird.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a>Angeben des Vorgangs und der Ressource

Sie können die zu ändernde Ressource und den von dem Befehl auszuführenden Vorgang angeben, indem Sie das [System. Management. Automation. Cmdlet. tiondprocess% 2a aufrufen? Displayproperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Methode. In diesem Fall stellen Sie die Ressource mithilfe des `target` -Parameters und des-Vorgangs bereit, indem Sie den- `target` Parameter verwenden. In der folgenden Meldung ist der Text "MyResource" die Ressource, die ausgeführt wird, und "myaction" ist der Vorgang, der ausgeführt werden soll.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Wenn der Benutzer für die vorherige Nachricht **Ja** oder **Ja** ausgewählt hat, wird ein Rückruf der [System. Management. Automation. Cmdlet. ermdcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) -Methode durchgeführt, wodurch eine zweite Bestätigungsmeldung angezeigt wird.

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
