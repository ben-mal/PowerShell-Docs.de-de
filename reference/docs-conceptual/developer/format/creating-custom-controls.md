---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen von benutzerdefinierten Steuerelementen
description: Erstellen von benutzerdefinierten Steuerelementen
ms.openlocfilehash: 78d8cc2970b2b3e493bef25d78404ba1be195bb1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668047"
---
# <a name="creating-custom-controls"></a>Erstellen von benutzerdefinierten Steuerelementen

Benutzerdefinierte Steuerelemente sind die flexibelsten Komponenten einer Formatierungs Datei. Im Gegensatz zu Tabellen-, Listen-und breiten Ansichten, die eine formale Struktur von Daten definieren, z. b. eine Tabelle mit Daten, können Sie mit benutzerdefinierten Steuerelementen definieren, wie ein einzelnes Datenelement angezeigt wird. Sie können einen allgemeinen Satz benutzerdefinierter Steuerelemente definieren, die für alle Sichten der Formatierungs Datei verfügbar sind. Sie können benutzerdefinierte Steuerelemente definieren, die für eine bestimmte Ansicht verfügbar sind, oder Sie können einen Satz von Steuerelementen definieren, die für eine Gruppe von Objekten verfügbar sind.

## <a name="custom-control-example"></a>Beispiel für einen benutzerdefinierten

Im folgenden Beispiel wird ein benutzerdefiniertes Steuerelement gezeigt, das in der Certificates.Format.ps1-XML-Datei definiert ist. Dieses benutzerdefinierte Steuerelement wird zum Trennen der [System. Management. Automation. Signature](/dotnet/api/System.Management.Automation.Signature) -Objekte verwendet, die in einer Tabellenansicht angezeigt werden.

```xml
<Controls>
  <Control>
    <Name>SignatureTypes-GroupingFormat</Name>
    <CustomControl>
      <CustomEntries>
        <CustomEntry>
          <CustomItem>
            <Frame>
              <LeftIndent>4</LeftIndent>
              <CustomItem>
                <Text AssemblyName="System.Management.Automation" BaseName="FileSystemProviderStrings"
                  ResourceId="DirectoryDisplayGrouping"/>
                <ExpressionBinding>
                  <ScriptBlock>split-path $_.Path</ScriptBlock>
                </ExpressionBinding>
                <NewLine/>
              </CustomItem>
            </Frame>
          </CustomItem>
        </CustomEntry>
      </CustomEntries>
    </CustomControl>
  </Control>
</Controls>

```

## <a name="see-also"></a>Weitere Informationen

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
