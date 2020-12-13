---
ms.date: 09/13/2016
ms.topic: reference
title: Listenansicht (Basic)
description: Listenansicht (Basic)
ms.openlocfilehash: d80ac9c6143b976d8bc13e2b184e4f5a2f8a37ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666636"
---
# <a name="list-view-basic"></a>Listenansicht (Basic)

Dieses Beispiel zeigt, wie Sie eine einfache Listenansicht implementieren, in der [System. ServiceProcess. ServiceController angezeigt wird? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekte, die vom Cmdlet " [Get-Service](/powershell/module/microsoft.powershell.management/get-service) " zurückgegeben werden. Weitere Informationen zu den Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).

### <a name="to-load-this-formatting-file"></a>So laden Sie diese Formatierungs Datei

1. Kopieren Sie den XML-Code aus dem Beispiel Abschnitt dieses Themas in eine Textdatei.

2. Speichern Sie die Textdatei. Stellen Sie sicher, dass `format.ps1xml` Sie die Erweiterung der Datei hinzufügen, um Sie als Formatierungs Datei zu identifizieren.

3. Öffnen Sie Windows PowerShell, und führen Sie den folgenden Befehl aus, um die Formatierungs Datei in die aktuelle Sitzung zu laden: `Update-formatdata -prependpath PathToFormattingFile` .

   > [!WARNING]
   > Mit dieser Formatierungs Datei wird die Anzeige eines Objekts definiert, das bereits durch eine Windows PowerShell-Formatierungs Datei definiert ist. Sie müssen den `prependPath` -Parameter verwenden, wenn Sie das-Cmdlet ausführen, und Sie können diese Formatierungs Datei nicht als Modul laden.

## <a name="demonstrates"></a>Zeigt

Diese Formatierungs Datei veranschaulicht die folgenden XML-Elemente:

- Das [Name](./name-element-for-view-format.md) -Element für die Sicht.

- Das [viewselectedby](./viewselectedby-element-format.md) -Element, das definiert, welche Objekte von der Sicht angezeigt werden.

- Das [ListControl](./listcontrol-element-format.md) -Element, das definiert, welche Eigenschaft von der Ansicht angezeigt wird.

- Das [ListItem](./listitem-element-for-listitems-for-listcontrol-format.md) -Element, das definiert, was in einer Zeile der Listenansicht angezeigt wird.

- Das [propertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) -Element, das definiert, welche Eigenschaft angezeigt wird.

## <a name="example"></a>Beispiel

Der folgende XML-Code definiert eine Listenansicht, in der vier Eigenschaften des [System. ServiceProcess. ServiceController angezeigt werden? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt. In jeder Zeile wird der Name der Eigenschaft angezeigt, gefolgt vom Wert der-Eigenschaft.

```xml
<Configuration>
  <View>
    <Name>System.ServiceProcess.ServiceController</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <ListControl>
      <ListEntries>
        <ListEntry>
          <ListItems>
            <ListItem>
              <PropertyName>Name</PropertyName>
            </ListItem>
            <ListItem>
              <PropertyName>DisplayName</PropertyName>
            </ListItem>
            <ListItem>
              <PropertyName>Status</PropertyName>
            </ListItem>
            <ListItem>
              <PropertyName>ServiceType</PropertyName>
            </ListItem>
          </ListItems>
        </ListEntry>
      </ListEntries>
    </ListControl>
  </View>
</Configuration>
```

Das folgende Beispiel zeigt, wie Windows PowerShell [System. ServiceProcess. ServiceController anzeigt? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekte, nachdem diese Format Datei geladen wurde.

```powershell
Get-Service f*
```

```output
Name        : Fax
DisplayName : Fax
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FCSAM
DisplayName : Microsoft Antimalware Service
Status      : Running
ServiceType : Win32OwnProcess

Name        : fdPHost
DisplayName : Function Discovery Provider Host
Status      : Stopped
ServiceType : Win32ShareProcess

Name        : FDResPub
DisplayName : Function Discovery Resource Publication
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache
DisplayName : Windows Font Cache Service
Status      : Running
ServiceType : Win32ShareProcess

Name        : FontCache3.0.0.0
DisplayName : Windows Presentation Foundation Font Cache 3.0.0.0
Status      : Stopped
ServiceType : Win32OwnProcess

Name        : FSysAgent
DisplayName : Microsoft Forefront System Agent
Status      : Running
ServiceType : Win32OwnProcess

Name        : FwcAgent
DisplayName : Firewall Client Agent
Status      : Running
ServiceType : Win32OwnProcess
```

## <a name="see-also"></a>Weitere Informationen

[Beispiele für Formatierungsdateien](./examples-of-formatting-files.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
