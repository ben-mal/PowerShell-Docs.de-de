---
ms.date: 08/21/2019
ms.topic: reference
title: Erweitern Objekteigenschaften
description: Erweitern Objekteigenschaften
ms.openlocfilehash: 37803d9fd87319204565c2abde62f269744481b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652889"
---
# <a name="extending-properties-for-objects"></a><span data-ttu-id="28a70-103">Erweitern Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="28a70-103">Extending Properties for Objects</span></span>

<span data-ttu-id="28a70-104">Wenn Sie .NET Framework Objekte erweitern, können Sie den-Objekten Alias Eigenschaften, Code Eigenschaften, Notiz Eigenschaften, Skript Eigenschaften und Eigenschaften Sätze hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="28a70-104">When you extend .NET Framework objects, you can add alias properties, code properties, note properties, script properties, and property sets to the objects.</span></span> <span data-ttu-id="28a70-105">Die XML-Daten, die diese Eigenschaften definieren, werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="28a70-105">The XML that defines these properties is described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="28a70-106">Die Beispiele in den folgenden Abschnitten stammen aus der `Types.ps1xml` Datei mit den Standardtypen im PowerShell-Installationsverzeichnis ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="28a70-106">The examples in the following sections are from the default `Types.ps1xml` types file in the PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="28a70-107">Weitere Informationen finden Sie unter Informationen [zu Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="28a70-107">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml).</span></span>

## <a name="alias-properties"></a><span data-ttu-id="28a70-108">Aliaseigenschaften</span><span class="sxs-lookup"><span data-stu-id="28a70-108">Alias properties</span></span>

<span data-ttu-id="28a70-109">Eine Alias Eigenschaft definiert einen neuen Namen für eine vorhandene Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="28a70-109">An alias property defines a new name for an existing property.</span></span>

<span data-ttu-id="28a70-110">Im folgenden Beispiel wird die **count** -Eigenschaft dem [System. Array](/dotnet/api/System.Array) -Typ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="28a70-110">In the following example, the **Count** property is added to the [System.Array](/dotnet/api/System.Array) type.</span></span> <span data-ttu-id="28a70-111">Das [aliasproperty](/dotnet/api/system.management.automation.psaliasproperty) -Element definiert die erweiterte Eigenschaft als Alias Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="28a70-111">The [AliasProperty](/dotnet/api/system.management.automation.psaliasproperty) element defines the extended property as an alias property.</span></span> <span data-ttu-id="28a70-112">Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name) -Element gibt den neuen Namen an.</span><span class="sxs-lookup"><span data-stu-id="28a70-112">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the new name.</span></span> <span data-ttu-id="28a70-113">Und das [referencedmembership Name](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername) -Element gibt die vorhandene Eigenschaft an, auf die vom Alias verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="28a70-113">And, the [ReferencedMemberName](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername) element specifies the existing property that is referenced by the alias.</span></span> <span data-ttu-id="28a70-114">Sie können auch das- `AliasProperty` Element den Membern des Members [](/dotnet/api/system.management.automation.psmemberset) -Elements hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="28a70-114">You can also add the `AliasProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

## <a name="code-properties"></a><span data-ttu-id="28a70-115">Code Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="28a70-115">Code properties</span></span>

<span data-ttu-id="28a70-116">Eine Code Eigenschaft verweist auf eine statische Eigenschaft eines .NET Framework Objekts.</span><span class="sxs-lookup"><span data-stu-id="28a70-116">A code property references a static property of a .NET Framework object.</span></span>

<span data-ttu-id="28a70-117">Im folgenden Beispiel wird die **Mode** -Eigenschaft dem [System. IO. directoriyinfo](/dotnet/api/System.IO.DirectoryInfo) -Typ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="28a70-117">In the following example, the **Mode** property is added to the [System.IO.DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="28a70-118">Das [CodeProperty](/dotnet/api/system.management.automation.pscodeproperty) -Element definiert die erweiterte Eigenschaft als Code Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="28a70-118">The [CodeProperty](/dotnet/api/system.management.automation.pscodeproperty) element defines the extended property as a code property.</span></span> <span data-ttu-id="28a70-119">Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name) -Element gibt den Namen der erweiterten Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="28a70-119">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="28a70-120">Und das [getcodereferenzierungselement](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference) definiert die statische Methode, auf die von der erweiterten Eigenschaft verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="28a70-120">And, the [GetCodeReference](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference) element defines the static method that is referenced by the extended property.</span></span> <span data-ttu-id="28a70-121">Sie können auch das- `CodeProperty` Element den Membern des Members [](/dotnet/api/system.management.automation.psmemberset) -Elements hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="28a70-121">You can also add the `CodeProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>Microsoft.PowerShell.Commands.FileSystemProvider</TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

## <a name="note-properties"></a><span data-ttu-id="28a70-122">Eigenschaften notieren</span><span class="sxs-lookup"><span data-stu-id="28a70-122">Note properties</span></span>

<span data-ttu-id="28a70-123">Eine Hinweis Eigenschaft definiert eine Eigenschaft, die über einen statischen Wert verfügt.</span><span class="sxs-lookup"><span data-stu-id="28a70-123">A note property defines a property that has a static value.</span></span>

<span data-ttu-id="28a70-124">Im folgenden Beispiel wird die **Status** -Eigenschaft, deren Wert immer **Erfolg** ist, dem [System. IO. directoriyinfo](/dotnet/api/System.IO.DirectoryInfo) -Typ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="28a70-124">In the following example, the **Status** property, whose value is always **Success**, is added to the [System.IO.DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo) type.</span></span> <span data-ttu-id="28a70-125">Das [NoteProperty](/dotnet/api/system.management.automation.psnoteproperty) -Element definiert die erweiterte Eigenschaft als Note-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="28a70-125">The [NoteProperty](/dotnet/api/system.management.automation.psnoteproperty) element defines the extended property as a note property.</span></span> <span data-ttu-id="28a70-126">Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name) -Element gibt den Namen der erweiterten Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="28a70-126">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="28a70-127">Das [value](/dotnet/api/system.management.automation.psnoteproperty.value) -Element gibt den statischen Wert der erweiterten Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="28a70-127">The [Value](/dotnet/api/system.management.automation.psnoteproperty.value) element specifies the static value of the extended property.</span></span> <span data-ttu-id="28a70-128">Das- `NoteProperty` Element kann auch den Membern des Elements Members [](/dotnet/api/system.management.automation.psmemberset) hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="28a70-128">The `NoteProperty` element can also be added to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

## <a name="script-properties"></a><span data-ttu-id="28a70-129">Skript Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="28a70-129">Script properties</span></span>

<span data-ttu-id="28a70-130">Eine Skript Eigenschaft definiert eine Eigenschaft, deren Wert die Ausgabe eines Skripts ist.</span><span class="sxs-lookup"><span data-stu-id="28a70-130">A script property defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="28a70-131">Im folgenden Beispiel wird die **VERSIONINFO** -Eigenschaft dem [System. IO. FileInfo](/dotnet/api/System.IO.FileInfo) -Typ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="28a70-131">In the following example, the **VersionInfo** property is added to the [System.IO.FileInfo](/dotnet/api/System.IO.FileInfo) type.</span></span> <span data-ttu-id="28a70-132">Das [scriptproperty](/dotnet/api/system.management.automation.psscriptproperty) -Element definiert die erweiterte Eigenschaft als Skript Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="28a70-132">The [ScriptProperty](/dotnet/api/system.management.automation.psscriptproperty) element defines the extended property as a script property.</span></span> <span data-ttu-id="28a70-133">Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name) -Element gibt den Namen der erweiterten Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="28a70-133">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the extended property.</span></span> <span data-ttu-id="28a70-134">Das [getscriptblock](/dotnet/api/system.management.automation.psscriptproperty.getterscript) -Element gibt das Skript an, das den Eigenschafts Wert generiert.</span><span class="sxs-lookup"><span data-stu-id="28a70-134">And, the [GetScriptBlock](/dotnet/api/system.management.automation.psscriptproperty.getterscript) element specifies the script that generates the property value.</span></span> <span data-ttu-id="28a70-135">Sie können auch das- `ScriptProperty` Element den Membern des Members [](/dotnet/api/system.management.automation.psmemberset) -Elements hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="28a70-135">You can also add the `ScriptProperty` element to the members of the [MemberSets](/dotnet/api/system.management.automation.psmemberset) element.</span></span>

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
        [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

## <a name="property-sets"></a><span data-ttu-id="28a70-136">Eigenschaften Sätze</span><span class="sxs-lookup"><span data-stu-id="28a70-136">Property sets</span></span>

<span data-ttu-id="28a70-137">Ein Eigenschaften Satz definiert eine Gruppe erweiterter Eigenschaften, auf die durch den Namen des Satzes verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="28a70-137">A property set defines a group of extended properties that can be referenced by the name of the set.</span></span>
<span data-ttu-id="28a70-138">Beispielsweise kann der [Format-Table-](/powershell/module/Microsoft.PowerShell.Utility/Format-Table) 
 **Eigenschafts** Parameter eine bestimmte Eigenschaften Gruppe angeben, die angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="28a70-138">For example, the [Format-Table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table)
**Property** parameter can specify a specific property set to be displayed.</span></span> <span data-ttu-id="28a70-139">Wenn ein Eigenschaften Satz angegeben wird, werden nur die Eigenschaften angezeigt, die zum Satz gehören.</span><span class="sxs-lookup"><span data-stu-id="28a70-139">When a property set is specified, only those properties that belong to the set are displayed.</span></span>

<span data-ttu-id="28a70-140">Es gibt keine Einschränkung hinsichtlich der Anzahl der Eigenschafts Sätze, die für ein Objekt definiert werden können.</span><span class="sxs-lookup"><span data-stu-id="28a70-140">There's no restriction on the number of property sets that can be defined for an object.</span></span> <span data-ttu-id="28a70-141">Die Eigenschaften Sätze, die zum Definieren der Standard Anzeigeeigenschaften eines Objekts verwendet werden, müssen jedoch innerhalb des **psstandardmembers** -Element Satzes angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="28a70-141">However, the property sets used to define the default display properties of an object must be specified within the **PSStandardMembers** member set.</span></span> <span data-ttu-id="28a70-142">In der `Types.ps1xml` types-Datei enthalten die standardmäßigen Eigenschaften Satz Namen " **defaultdisplayproperty**", " **defaultdisplaypropertyset**" und " **defaultkeypropertyset**".</span><span class="sxs-lookup"><span data-stu-id="28a70-142">In the `Types.ps1xml` types file, the default property set names include **DefaultDisplayProperty**, **DefaultDisplayPropertySet**, and **DefaultKeyPropertySet**.</span></span> <span data-ttu-id="28a70-143">Alle zusätzlichen Eigenschaften Sätze, die Sie dem **psstandardmembers** -Element Satz hinzufügen, werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="28a70-143">Any additional property sets that you add to the **PSStandardMembers** member set are ignored.</span></span>

<span data-ttu-id="28a70-144">Im folgenden Beispiel wird der Wert der **defaultdisplaypropertyset** -Eigenschaft dem **psstandardmembers** -Element Satz des Typs [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="28a70-144">In the following example, the **DefaultDisplayPropertySet** property set is added to the **PSStandardMembers** member set of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) type.</span></span> <span data-ttu-id="28a70-145">Das [PropertySet](/dotnet/api/system.management.automation.pspropertyset) -Element definiert die Gruppe von Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="28a70-145">The [PropertySet](/dotnet/api/system.management.automation.pspropertyset) element defines the group of properties.</span></span> <span data-ttu-id="28a70-146">Das [Name](/dotnet/api/system.management.automation.psmemberinfo.name) -Element gibt den Namen des Eigenschaften Satzes an.</span><span class="sxs-lookup"><span data-stu-id="28a70-146">The [Name](/dotnet/api/system.management.automation.psmemberinfo.name) element specifies the name of the property set.</span></span> <span data-ttu-id="28a70-147">Und das [referencedproperties](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames) -Element gibt die Eigenschaften des Satzes an.</span><span class="sxs-lookup"><span data-stu-id="28a70-147">And, the [ReferencedProperties](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames) element specifies the properties of the set.</span></span> <span data-ttu-id="28a70-148">Sie können auch das- `PropertySet` Element den Membern des [Type](/dotnet/api/system.management.automation.pstypename) -Elements hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="28a70-148">You can also add the `PropertySet` element to the members of the [Type](/dotnet/api/system.management.automation.pstypename) element.</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
           <Name>DefaultDisplayPropertySet</Name>
           <ReferencedProperties>
            <Name>Status</Name
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

## <a name="see-also"></a><span data-ttu-id="28a70-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28a70-149">See also</span></span>

[<span data-ttu-id="28a70-150">Informationen zu Types.ps1XML</span><span class="sxs-lookup"><span data-stu-id="28a70-150">About Types.ps1xml</span></span>](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)

[<span data-ttu-id="28a70-151">System.Management.Automation</span><span class="sxs-lookup"><span data-stu-id="28a70-151">System.Management.Automation</span></span>](/dotnet/api/System.Management.Automation)

[<span data-ttu-id="28a70-152">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="28a70-152">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
