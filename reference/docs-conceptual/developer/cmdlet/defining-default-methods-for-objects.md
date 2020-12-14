---
ms.date: 09/13/2016
ms.topic: reference
title: Definieren von Standardmethoden für Objekte
description: Definieren von Standardmethoden für Objekte
ms.openlocfilehash: c65ca91a7038f32d8c3ef62cfe7881e5ad4dba5a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355526"
---
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="913fe-103">Definieren von Standardmethoden für Objekte</span><span class="sxs-lookup"><span data-stu-id="913fe-103">Defining Default Methods for Objects</span></span>

<span data-ttu-id="913fe-104">Wenn Sie .NET Framework Objekte erweitern, können Sie den-Objekten Code Methoden und Skript Methoden hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="913fe-104">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span>
<span data-ttu-id="913fe-105">Der XML-Code, der verwendet wird, um diese Methoden zu definieren, wird in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="913fe-105">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="913fe-106">Die Beispiele in den folgenden Abschnitten stammen aus der `Types.ps1xml` Datei Types im Installationsverzeichnis von Windows PowerShell ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="913fe-106">The examples in the following sections are from the `Types.ps1xml` types file in the Windows PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="913fe-107">Weitere Informationen finden Sie unter Informationen [zu Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="913fe-107">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="code-methods"></a><span data-ttu-id="913fe-108">Code Methoden</span><span class="sxs-lookup"><span data-stu-id="913fe-108">Code methods</span></span>

<span data-ttu-id="913fe-109">Eine Code Methode verweist auf eine statische Methode eines .NET Framework Objekts.</span><span class="sxs-lookup"><span data-stu-id="913fe-109">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="913fe-110">Im folgenden Beispiel wird die Methode " **destring** " dem [System.Xml.XmlKnotentyp](/dotnet/api/System.Xml.XmlNode) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="913fe-110">In the following example, the **ToString** method is added to the [System.Xml.XmlNode](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="913fe-111">Das [pscodemethod](/dotnet/api/system.management.automation.pscodemethod) -Element definiert die erweiterte Methode als Code Methode.</span><span class="sxs-lookup"><span data-stu-id="913fe-111">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="913fe-112">Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) -Element gibt den Namen der erweiterten Methode an.</span><span class="sxs-lookup"><span data-stu-id="913fe-112">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="913fe-113">Das [codereferenzierungselement](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) gibt die statische Methode an.</span><span class="sxs-lookup"><span data-stu-id="913fe-113">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="913fe-114">Sie können auch das [pscodemethod](/dotnet/api/system.management.automation.pscodemethod) -Element den Membern des [psmembership Sets](/dotnet/api/system.management.automation.psmemberset) -Elements hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="913fe-114">You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

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

## <a name="script-methods"></a><span data-ttu-id="913fe-115">Skript Methoden</span><span class="sxs-lookup"><span data-stu-id="913fe-115">Script methods</span></span>

<span data-ttu-id="913fe-116">Eine Skript Methode definiert eine Methode, deren Wert die Ausgabe eines Skripts ist.</span><span class="sxs-lookup"><span data-stu-id="913fe-116">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="913fe-117">Im folgenden Beispiel wird die **convertdedatetime** -Methode dem [System. Management. ManagementObject](/dotnet/api/System.Management.ManagementObject) -Typ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="913fe-117">In the following example, the **ConvertToDateTime** method is added to the [System.Management.ManagementObject](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="913fe-118">Das [psscriptmethod](/dotnet/api/system.management.automation.psscriptmethod) -Element definiert die erweiterte Methode als Skript Methode.</span><span class="sxs-lookup"><span data-stu-id="913fe-118">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) element defines the extended method as a script method.</span></span> <span data-ttu-id="913fe-119">Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) -Element gibt den Namen der erweiterten Methode an.</span><span class="sxs-lookup"><span data-stu-id="913fe-119">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="913fe-120">Das [Script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) -Element gibt das Skript an, das den Methoden Wert generiert.</span><span class="sxs-lookup"><span data-stu-id="913fe-120">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="913fe-121">Sie können auch das [psscriptmethod](/dotnet/api/system.management.automation.psscriptmethod) -Element den Membern des [psmembership Sets](/dotnet/api/system.management.automation.psmemberset) -Elements hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="913fe-121">You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="913fe-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="913fe-122">See also</span></span>

[<span data-ttu-id="913fe-123">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="913fe-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
