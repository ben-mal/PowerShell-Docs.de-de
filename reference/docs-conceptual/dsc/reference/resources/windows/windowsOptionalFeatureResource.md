---
ms.date: 08/28/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressource „WindowsOptionalFeature“
ms.openlocfilehash: f24173c1a9ed605bac43767a9da2d4dbded78883
ms.sourcegitcommit: 06b6f4012e4eca71d414733cdba23ef75535223c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "89093249"
---
# <a name="dsc-windowsoptionalfeature-resource"></a>DSC-Ressource „WindowsOptionalFeature“

> Gilt für: Windows PowerShell 5.x

Die Ressource **WindowsOptionalFeature** in Windows PowerShell DSC (Desired State Configuration) bietet einen Mechanismus, um sicherzustellen, dass optionale Features auf einem Zielknoten aktiviert werden.

> [!NOTE]
> **WindowsOptionalFeature** funktioniert nur auf Windows-Clientcomputern wie Windows 10.

## <a name="syntax"></a>Syntax

```Syntax
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Eigenschaften

|Eigenschaft |Beschreibung |
|---|---|
|Name |Gibt den Namen des Features an, das aktiviert oder deaktiviert werden soll. |
|NoWindowsUpdateCheck |Gibt an, ob Windows Update (WU) von DISM kontaktiert wird, wenn die Quelldateien zum Aktivieren eines Features gesucht werden. Falls `$true`, wird WU nicht von DISM kontaktiert. |
|RemoveFilesOnDisable |Legen Sie diese Einstellung auf `$true` fest, um alle zu dem Feature gehörigen Dateien zu entfernen, wenn **Ensure** auf **Absent** festgelegt wird. |
|LogLevel |Die maximale Ausgabeebene, die in den Protokollen angezeigt wird. Zulässige Werte: **ErrorsOnly**, **ErrorsAndWarning** und **ErrorsAndWarningAndInformation**. |
|LogPath |Der Pfad zu einer Protokolldatei, in der der Ressourcenanbieter den Vorgang protokollieren soll. |

## <a name="common-properties"></a>Allgemeine Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|DependsOn |Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird. Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Gibt an, ob die Funktion aktiviert ist. Um sicherzustellen, dass das Feature aktiviert ist, legen Sie diese Eigenschaft auf _Enable_ fest. Um sicherzustellen, dass das Feature deaktiviert ist, legen Sie diese Eigenschaft auf _Disable_ fest. Der Standardwert ist _Enable_. |
|PsDscRunAsCredential |Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest. |

> [!NOTE]
> Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen. Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).
