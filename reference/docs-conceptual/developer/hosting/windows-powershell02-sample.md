---
title: Windows PowerShell02 Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: a82366a88addb08e186eede79e621d90d915c50f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779385"
---
# <a name="windows-powershell02-sample"></a>Windows PowerShell02-Beispiel

Dieses Beispiel zeigt, wie Befehle asynchron mit den Runspaces eines Runspace-Pools ausgeführt werden. Das Beispiel generiert eine Liste mit Befehlen und führt diese Befehle aus, während die Windows PowerShell-Engine einen Runspace aus dem Pool öffnet, wenn Sie benötigt wird.

## <a name="requirements"></a>Requirements (Anforderungen)

- Dieses Beispiel erfordert Windows PowerShell 2,0.

## <a name="demonstrates"></a>Zeigt

Dieses Beispiel zeigt Folgendes:

- Das Erstellen eines runspacepool-Objekts mit einer minimalen und maximalen Anzahl von Runspaces, die gleichzeitig geöffnet sein dürfen.
- Erstellen einer Liste von Befehlen.
- Asynchrones Ausführen der Befehle.
- Aufrufen der [System. Management. Automation. Runspaces. runspacepool. getavailablerunspaces *](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) -Methode, um zu sehen, wie viele Runspaces kostenlos sind.
- Erfassen der Befehlsausgabe mit der [System. Management. Automation. PowerShell. EndInvoke *](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) -Methode.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie Sie die Runspaces eines Runspace-Pools öffnen und Befehle in diesen Runspaces asynchron ausführen.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a>Weitere Informationen

[Schreiben einer Windows PowerShell-Hostanwendung](./writing-a-windows-powershell-host-application.md)
