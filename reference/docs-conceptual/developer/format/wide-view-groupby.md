---
ms.date: 09/13/2016
ms.topic: reference
title: Breite Ansicht (GroupBy)
description: Breite Ansicht (GroupBy)
ms.openlocfilehash: 807bea2a5d44c38e2c9977f792bea2fb9bca0fc3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667673"
---
# <a name="wide-view-groupby"></a>Breite Ansicht (GroupBy)

In diesem Beispiel wird gezeigt, wie eine breite Ansicht implementiert wird, in der Gruppen von [System. ServiceProcess. ServiceController angezeigt werden. Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekte, die vom `Get-Service` Cmdlet zurückgegeben werden. Weitere Informationen zu den Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).

### <a name="to-load-this-formatting-file"></a>So laden Sie diese Formatierungs Datei

1. Kopieren Sie den XML-Code aus dem Beispiel Abschnitt dieses Themas in eine Textdatei.

2. Speichern Sie die Textdatei. Stellen Sie sicher, dass `format.ps1xml` Sie die Erweiterung der Datei hinzufügen, um Sie als Formatierungs Datei zu identifizieren.

3. Öffnen Sie Windows PowerShell, und führen Sie den folgenden Befehl aus, um die Formatierungs Datei in die aktuelle Sitzung zu laden: `Update-formatdata -prependpath PathToFormattingFile` .

   > [!WARNING]
   > Mit dieser Formatierungs Datei wird die Anzeige eines Objekts definiert, das bereits von Windows PowerShell-Formatierungs Dateien definiert wird. Sie müssen den `prependPath` -Parameter verwenden, wenn Sie das-Cmdlet ausführen, und Sie können diese Formatierungs Datei nicht als Modul laden.

## <a name="demonstrates"></a>Zeigt

Diese Formatierungs Datei veranschaulicht die folgenden XML-Elemente:

- Das [Name](./name-element-for-view-format.md) -Element für die Sicht.

- Das [viewselectedby](./viewselectedby-element-format.md) -Element, das definiert, welche Objekte von der Sicht angezeigt werden.

- Das [GroupBy](./groupby-element-for-view-format.md) -Element, das definiert, wann eine neue Gruppe angezeigt wird.

- Das [wideitem](./wideitem-element-for-widecontrol-format.md) -Element, das definiert, welche Eigenschaft von der Ansicht angezeigt wird.

## <a name="example"></a>Beispiel

Der folgende XML-Code definiert eine breite Ansicht, in der Gruppen von Objekten angezeigt werden. Jede neue Gruppe wird gestartet, wenn sich der Wert der [System. ServiceProcess. ServiceController. ServiceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) -Eigenschaft ändert.

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <Label>Service Type</Label>
        <PropertyName>ServiceType</PropertyName>
      </GroupBy>
      <WideControl>
        <WideEntries>
          <WideEntry>
            <WideItem>
              <PropertyName>ServiceName</PropertyName>
            </WideItem>
          </WideEntry>
        </WideEntries>
      </WideControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

Das folgende Beispiel zeigt, wie Windows PowerShell [System. ServiceProcess. ServiceController anzeigt? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekte, nachdem diese Format Datei geladen wurde.

```powershell
Get-Service f*
```

```output
   Service Type: Win32OwnProcess

Fax                             FCSAM

   Service Type: Win32ShareProcess

fdPHost                         FDResPub
FontCache

   Service Type: Win32OwnProcess

FontCache3.0.0.0                FSysAgent
FwcAgent
```

## <a name="see-also"></a>Weitere Informationen

[Beispiele für Formatierungsdateien](./examples-of-formatting-files.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
