---
ms.date: 07/16/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Resource „Environment“
ms.openlocfilehash: d8519a66d457767dcbc0e08b01a69a9264997479
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464416"
---
# <a name="dsc-environment-resource"></a>DSC-Resource „Environment“

> Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x

Die Ressource **Environment** in Windows PowerShell DSC bietet einen Mechanismus zum Verwalten von Systemumgebungsvariablen.

## <a name="syntax"></a>Syntax

```Syntax
Environment [string] #ResourceName
{
    Name = [string]
    [ Path = [bool] ]
    [ Target = [string] { Process | Machine } ]
    [ Value = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|Name |Gibt den Namen der Umgebungsvariablen an, für die Sie einen bestimmten Zustand sicherstellen möchten. |
|`Path` |Definiert die Umgebungsvariable, die konfiguriert wird. Legen Sie diese Eigenschaft auf `$true` fest, wenn die Variable die **Path**-Variable ist. Legen Sie sie andernfalls auf `$false` fest. Der Standardwert lautet `$false`. Wenn die konfigurierte Variable die **Path**-Variable ist, wird der von der **Value**-Eigenschaft bereitgestellte Wert an den vorhandenen Wert angefügt. |
|Ziel| Gibt an, wo die Variable abgerufen werden soll: Computer oder Prozess. Wenn beide angegeben werden, wird nur der Wert des Computers zurückgegeben. Standard sind beide Werte, da dies die Standardeinstellung für den Rest der Ressource ist. |
|Wert |Der Wert, der der Umgebungsvariablen zugewiesen werden soll. |

## <a name="common-properties"></a>Allgemeine Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|DependsOn |Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird. Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Gibt an, ob eine Variable vorhanden ist. Legen Sie diese Eigenschaft auf **Present** fest, um die Umgebungsvariable zu erstellen, falls sie noch nicht vorhanden ist, oder um sicherzustellen, dass ihr Wert der Angabe durch die **Value**-Eigenschaft entspricht, wenn die Variable bereits vorhanden ist. Legen Sie sie auf **Absent** fest, um die Variable zu löschen, falls sie vorhanden ist. |
|PsDscRunAsCredential |Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest. |

> [!NOTE]
> Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen. Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird sichergestellt, dass TestEnvironmentVariable vorhanden ist und den Wert _TestValue_ hat. Falls sie nicht vorhanden ist, wird sie erstellt.

```powershell
Environment EnvironmentExample
{
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Name = "TestEnvironmentVariable"
    Value = "TestValue"
}
```
