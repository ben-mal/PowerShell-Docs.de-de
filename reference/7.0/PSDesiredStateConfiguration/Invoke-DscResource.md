---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 4703586008d9044ae68fd7375db65f0d0a9b9980
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "93219527"
---
# Invoke-DscResource

## ZUSAMMENFASSUNG
Führt eine Methode einer angegebenen PowerShell DSC-Ressource aus.

## SYNTAX

```
Invoke-DscResource [[-Method] <Object>] [[-Name] <Object>] [[-Property] <Object>]
 [[-ModuleName] <Object>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

Mit dem Cmdlet `Invoke-DscResource` wird eine Methode einer angegebenen PowerShell DSC-Ressource (Desired State Configuration) ausgeführt.

Dieses Cmdlet ruft eine DSC-Ressource direkt auf, ohne ein Konfigurationsdokument zu erstellen. Mithilfe dieses Cmdlets können Konfigurations Verwaltungs Produkte Windows oder Linux mithilfe von DSC-Ressourcen verwalten. Dieses Cmdlet ermöglicht auch das Debuggen von Ressourcen, wenn die DSC-Engine mit aktiviertem Debuggen ausgeführt wird.

> [!NOTE]
> `Invoke-DscResource` ist eine experimentelle Funktion in PowerShell 7. Um das Cmdlet zu verwenden, müssen Sie es mit dem folgenden Befehl aktivieren.
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## BEISPIELE

### Beispiel 1: Aufrufen der Set-Methode einer Ressource durch Angeben der obligatorischen Eigenschaften

In diesem Beispiel wird die **Set** -Methode einer Ressource namens " **windowsprocess** " aufgerufen und die obligatorischen **Pfad** -und **Argument** Eigenschaften zum Starten des angegebenen Windows-Prozesses bereitstellt.

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### Beispiel 2: Aufrufen der Test Methode einer Ressource für ein bestimmtes Modul

In diesem Beispiel wird die **Test** Methode einer Ressource mit dem Namen " **windowsprocess** " aufgerufen, die im Modul " **psdesiredstatus econfiguration** " enthalten ist.

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## PARAMETERS

### -Methode

Gibt die Methode der Ressource an, die von diesem Cmdlet aufgerufen wird. Die zulässigen Werte für diesen Parameter sind: **Get** , **set** und **Test**.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ModuleName

Gibt den Namen des Moduls an, von dem dieses Cmdlet die angegebene Ressource aufruft.

```yaml
Type: ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt den Namen der zu startenden DSC-Ressource an.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Eigenschaft

Gibt den Namen der Ressourceneigenschaft und deren Wert in einer Hashtabelle als Schlüssel und Wert an.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

### Microsoft. Management. Infrastructure. ciminstance, System. Boolean

## HINWEISE

- Zuvor wurden Windows PowerShell 5,1-Ressourcen im System Kontext ausgeführt, es sei denn, Sie wurden mit dem Schlüssel **psdscrunascredential** mit einem Benutzer Kontext angegeben. In PowerShell 7,0 werden Ressourcen im Kontext des Benutzers ausgeführt, und " **psdscrunascredential** " wird nicht mehr unterstützt. Vorherige Konfigurationen, die diesen Schlüssel verwenden, lösen eine Ausnahme aus.

- Ab PowerShell 7 `Invoke-DscResource` unterstützt nicht mehr das Aufrufen von WMI DSC-Ressourcen. Dies gilt auch für die Ressourcen **File** und **Log** in **PSDesiredStateConfiguration**.

## VERWANDTE LINKS

[Windows PowerShell DSC – Übersicht](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscResource](Get-DscResource.md)
