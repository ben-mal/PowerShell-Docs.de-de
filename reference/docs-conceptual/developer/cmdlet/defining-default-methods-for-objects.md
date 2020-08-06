---
title: Definieren von Standardmethoden für Objekte | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 10917de9e897fc1eed362430d63ff5b9cb7e813d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774591"
---
# <a name="defining-default-methods-for-objects"></a>Definieren von Standardmethoden für Objekte

Wenn Sie .NET Framework Objekte erweitern, können Sie den-Objekten Code Methoden und Skript Methoden hinzufügen.
Der XML-Code, der verwendet wird, um diese Methoden zu definieren, wird in den folgenden Abschnitten beschrieben.

> [!NOTE]
> Die Beispiele in den folgenden Abschnitten stammen aus der `Types.ps1xml` Datei Types im Installationsverzeichnis von Windows PowerShell ( `$PSHOME` ). Weitere Informationen finden Sie unter Informationen [zu Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).

## <a name="code-methods"></a>Code Methoden

Eine Code Methode verweist auf eine statische Methode eines .NET Framework Objekts.

Im folgenden Beispiel wird die Methode " **destring** " dem [System.Xml.XmlKnotentyp](/dotnet/api/System.Xml.XmlNode) hinzugefügt. Das [pscodemethod](/dotnet/api/system.management.automation.pscodemethod) -Element definiert die erweiterte Methode als Code Methode. Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) -Element gibt den Namen der erweiterten Methode an. Das [codereferenzierungselement](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) gibt die statische Methode an. Sie können auch das [pscodemethod](/dotnet/api/system.management.automation.pscodemethod) -Element den Membern des [psmembership Sets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) -Elements hinzufügen.

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodeMethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a>Skript Methoden

Eine Skript Methode definiert eine Methode, deren Wert die Ausgabe eines Skripts ist. Im folgenden Beispiel wird die **convertdedatetime** -Methode dem [System. Management. ManagementObject](/dotnet/api/System.Management.ManagementObject) -Typ hinzugefügt. Das [psscriptmethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) -Element definiert die erweiterte Methode als Skript Methode. Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) -Element gibt den Namen der erweiterten Methode an. Das [Script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) -Element gibt das Skript an, das den Methoden Wert generiert. Sie können auch das [psscriptmethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) -Element den Membern des [psmembership Sets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) -Elements hinzufügen.

```xml
<Type>
  <Name>System.Management.ManagementObject</Name>
  <Members>
    <ScriptMethod>
      <Name>ConvertToDateTime</Name>
      <Script>
        [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
      </Script>
    </ScriptMethod>
  </Members>
</Type>
```

## <a name="see-also"></a>Siehe auch

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
