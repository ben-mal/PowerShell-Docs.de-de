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
# <a name="defining-default-methods-for-objects"></a><span data-ttu-id="a99c4-102">Definieren von Standardmethoden für Objekte</span><span class="sxs-lookup"><span data-stu-id="a99c4-102">Defining Default Methods for Objects</span></span>

<span data-ttu-id="a99c4-103">Wenn Sie .NET Framework Objekte erweitern, können Sie den-Objekten Code Methoden und Skript Methoden hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a99c4-103">When you extend .NET Framework objects, you can add code methods and script methods to the objects.</span></span>
<span data-ttu-id="a99c4-104">Der XML-Code, der verwendet wird, um diese Methoden zu definieren, wird in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a99c4-104">The XML that is used to define these methods is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="a99c4-105">Die Beispiele in den folgenden Abschnitten stammen aus der `Types.ps1xml` Datei Types im Installationsverzeichnis von Windows PowerShell ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="a99c4-105">The examples in the following sections are from the `Types.ps1xml` types file in the Windows PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="a99c4-106">Weitere Informationen finden Sie unter Informationen [zu Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="a99c4-106">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="code-methods"></a><span data-ttu-id="a99c4-107">Code Methoden</span><span class="sxs-lookup"><span data-stu-id="a99c4-107">Code methods</span></span>

<span data-ttu-id="a99c4-108">Eine Code Methode verweist auf eine statische Methode eines .NET Framework Objekts.</span><span class="sxs-lookup"><span data-stu-id="a99c4-108">A code method references a static method of a .NET Framework object.</span></span>

<span data-ttu-id="a99c4-109">Im folgenden Beispiel wird die Methode " **destring** " dem [System.Xml.XmlKnotentyp](/dotnet/api/System.Xml.XmlNode) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a99c4-109">In the following example, the **ToString** method is added to the [System.Xml.XmlNode](/dotnet/api/System.Xml.XmlNode) type.</span></span> <span data-ttu-id="a99c4-110">Das [pscodemethod](/dotnet/api/system.management.automation.pscodemethod) -Element definiert die erweiterte Methode als Code Methode.</span><span class="sxs-lookup"><span data-stu-id="a99c4-110">The [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element defines the extended method as a code method.</span></span> <span data-ttu-id="a99c4-111">Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) -Element gibt den Namen der erweiterten Methode an.</span><span class="sxs-lookup"><span data-stu-id="a99c4-111">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="a99c4-112">Das [codereferenzierungselement](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) gibt die statische Methode an.</span><span class="sxs-lookup"><span data-stu-id="a99c4-112">And, the [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference) element specifies the static method.</span></span> <span data-ttu-id="a99c4-113">Sie können auch das [pscodemethod](/dotnet/api/system.management.automation.pscodemethod) -Element den Membern des [psmembership Sets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) -Elements hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a99c4-113">You can also add the [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.</span></span>

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

## <a name="script-methods"></a><span data-ttu-id="a99c4-114">Skript Methoden</span><span class="sxs-lookup"><span data-stu-id="a99c4-114">Script methods</span></span>

<span data-ttu-id="a99c4-115">Eine Skript Methode definiert eine Methode, deren Wert die Ausgabe eines Skripts ist.</span><span class="sxs-lookup"><span data-stu-id="a99c4-115">A script method defines a method whose value is the output of a script.</span></span> <span data-ttu-id="a99c4-116">Im folgenden Beispiel wird die **convertdedatetime** -Methode dem [System. Management. ManagementObject](/dotnet/api/System.Management.ManagementObject) -Typ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a99c4-116">In the following example, the **ConvertToDateTime** method is added to the [System.Management.ManagementObject](/dotnet/api/System.Management.ManagementObject) type.</span></span> <span data-ttu-id="a99c4-117">Das [psscriptmethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) -Element definiert die erweiterte Methode als Skript Methode.</span><span class="sxs-lookup"><span data-stu-id="a99c4-117">The [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element defines the extended method as a script method.</span></span> <span data-ttu-id="a99c4-118">Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) -Element gibt den Namen der erweiterten Methode an.</span><span class="sxs-lookup"><span data-stu-id="a99c4-118">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name) element specifies the name of the extended method.</span></span> <span data-ttu-id="a99c4-119">Das [Script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) -Element gibt das Skript an, das den Methoden Wert generiert.</span><span class="sxs-lookup"><span data-stu-id="a99c4-119">And, the [Script](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script) element specifies the script that generates the method value.</span></span> <span data-ttu-id="a99c4-120">Sie können auch das [psscriptmethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) -Element den Membern des [psmembership Sets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) -Elements hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a99c4-120">You can also add the [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0) element to the members of the [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0) element.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a99c4-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a99c4-121">See also</span></span>

[<span data-ttu-id="a99c4-122">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a99c4-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
