---
ms.date: 09/20/2019
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressource „Service“
ms.openlocfilehash: f936f58ffd00f84d8c6d5d41d93378eaa8db5879
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463583"
---
# <a name="dsc-service-resource"></a>DSC-Ressource „Service“

> Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x

Die Ressource **Service** in Windows PowerShell DSC bietet einen Mechanismus zum Verwalten von Diensten auf dem Zielknoten.

## <a name="syntax"></a>Syntax

```Syntax
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ StartupTimeout = [uint32]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Ignore | Running | Stopped }  ]
    [ Dependencies = [string[]] ]
    [ Description = [string] ]
    [ DesktopInteract = [boolean]]
    [ DisplayName = [string] ]
    [ Path = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
    [ TerminateTimeout = [uint32] ]
}
```

## <a name="properties"></a>Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|Name |Gibt den Namen des Diensts an. Beachten Sie, dass sich dieser mitunter vom Anzeigenamen unterscheidet. Mit dem Cmdlet `Get-Service` können Sie eine Liste der Dienste und ihren aktuellen Status abrufen. |
|BuiltInAccount |Gibt das zu verwendende Anmeldekonto für den Dienst an. Die für diese Eigenschaft zulässigen Werte sind: **LocalService**, **LocalSystem** und **NetworkService**. |
|Anmeldeinformationen |Gibt die Anmeldeinformationen für das Konto an, unter dem der Dienst ausgeführt wird. Diese Eigenschaft und die **BuiltinAccount**-Eigenschaft können nicht zusammen verwendet werden. |
|StartupTimeout | Die Zeit (in Millisekunden ), die gewartet werden soll, bis der Dienst ausgeführt wird.|
|StartupType |Gibt den Starttyp für den Dienst an. Die für diese Eigenschaft zulässigen Werte sind: **Automatic**, **Disabled** und **Manual**. |
|State |Gibt den Status an, den Sie für den Dienst sicherstellen möchten. Die Werte sind: **Running** oder **Stopped**. |
|TerminateTimeout |Die Wartezeit (in Millisekunden), die gewartet werden soll, bis der Dienst beendet wird.|
|Abhängigkeiten | Ein Array mit den Namen der Abhängigkeiten, die der Dienst aufweisen sollte. |
|Beschreibung |Gibt die Beschreibung des Zieldiensts an. |
|DesktopInteract | Gibt an, ob der Dienst in der Lage sein soll, mit einem Fenster auf dem Desktop zu kommunizieren. Muss für Dienste, die nicht als LocalSystem ausgeführt werden, FALSE sein.|
|DisplayName |Gibt den Anzeigenamen des Zieldiensts an. |
|Pfad |Gibt den Pfad zur Binärdatei eines neuen Diensts an. |

## <a name="common-properties"></a>Allgemeine Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|DependsOn |Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird. Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Gibt an, ob der Zieldienst auf dem System vorhanden ist. Legen Sie diese Eigenschaft auf **Absent** fest, um sicherzustellen, dass der Zieldienst nicht vorhanden ist. Das Festlegen auf **Present** stellt sicher, dass der Zieldienst vorhanden ist. Der Standardwert ist **Present**. |
|PsDscRunAsCredential |Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest. |

> [!NOTE]
> Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen. Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).

## <a name="example"></a>Beispiel

```powershell
configuration ServiceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        Service ServiceExample
        {
            Name        = "TermService"
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```
