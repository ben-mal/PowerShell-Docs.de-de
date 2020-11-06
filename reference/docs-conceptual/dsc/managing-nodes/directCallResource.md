---
ms.date: 08/11/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Direktes Aufrufen von DSC-Ressourcenmethoden
description: Das Cmdlet Invoke-DscResource kann verwendet werden, um die Funktionen oder Methoden einer DSC-Ressource aufzurufen. Es kann von Drittanbietern verwendet werden, die DSC-Ressourcen verwenden möchten, oder als hilfreiches Tool bei der Entwicklung von Ressourcen.
ms.openlocfilehash: 5ccf0f589b60cef4ec197d1e0a583af9ed60d5e7
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92651000"
---
# <a name="calling-dsc-resource-methods-directly"></a>Direktes Aufrufen von DSC-Ressourcenmethoden

> Gilt für: Windows PowerShell 5.0

Sie können das Cmdlet [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) verwenden, um die Funktionen oder Methoden einer DSC-Ressource direkt aufzurufen (die Funktionen `Get-TargetResource`, `Set-TargetResource` und `Test-TargetResource` einer MOF-basierten Ressource oder die Methoden **Get** , **Set** und **Test** einer klassenbasierten Ressource). Dieses kann von Drittanbietern verwendet werden, die DSC-Ressourcen verwenden möchten, oder als hilfreiches Tool bei der Entwicklung von Ressourcen.

> [!NOTE]
> Ab PowerShell 7.0 unterstützt `Invoke-DscResource` nicht mehr das Aufrufen von WMI DSC-Ressourcen. Dies gilt auch für die Ressourcen **File** und **Log** in **PSDesiredStateConfiguration**.

Dieses Cmdlet wird in der Regel in Kombination mit einer Metakonfigurationseigenschaft `refreshMode = 'Disabled'` verwendet, kann aber unabhängig davon verwendet werden, auf was **refreshMode** festgelegt ist.

Beim Aufrufen des Cmdlets `Invoke-DscResource` geben Sie mithilfe des **Method** -Parameters an, welche Methode oder Funktion aufgerufen werden soll. Sie geben die Eigenschaften der Ressource an, indem Sie eine Hashtabelle als Wert des Parameters **Property** übergeben.

Im Folgenden finden Sie Beispiele für das direkte Aufrufen von Ressourcenmethoden:

## <a name="ensure-a-file-is-present"></a>Sicherstellen, dass eine Datei vorhanden ist

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
              DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
              Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a>Testen, ob eine Datei vorhanden ist

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a>Abrufen des Inhalts einer Datei

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

> [!NOTE]
> Das direkte Aufrufen von Methoden für zusammengesetzte Ressourcen wird nicht unterstützt. Rufen Sie stattdessen die Methoden der zugrunde liegenden Ressourcen auf, aus denen die zusammengesetzte Ressource besteht.

## <a name="see-also"></a>Weitere Informationen

- [Schreiben einer benutzerdefinierten DSC-Ressource mit MOF](../resources/authoringResourceMOF.md)
- [Schreiben einer benutzerdefinierten DSC-Ressource mit PowerShell-Klassen](../resources/authoringResourceClass.md)
- [Debuggen von DSC-Ressourcen](../troubleshooting/debugResource.md)
