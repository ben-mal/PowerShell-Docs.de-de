---
ms.date: 09/13/2016
ms.topic: reference
title: Schreiben eines benutzerdefinierten Windows PowerShell-Snap-Ins
description: Schreiben eines benutzerdefinierten Windows PowerShell-Snap-Ins
ms.openlocfilehash: e79c0c3db583fa0add9287745e97958a71360592
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659528"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a><span data-ttu-id="0b4a5-103">Schreiben eines benutzerdefinierten Windows PowerShell-Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="0b4a5-103">Writing a Custom Windows PowerShell Snap-in</span></span>

<span data-ttu-id="0b4a5-104">Dieses Beispiel zeigt, wie Sie ein Windows PowerShell-Snap-in schreiben, mit dem bestimmte Cmdlets registriert werden.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-104">This example shows how to write a Windows PowerShell snap-in that registers specific cmdlets.</span></span>

<span data-ttu-id="0b4a5-105">Bei dieser Art von Snap-in geben Sie an, welche Cmdlets, Anbieter, Typen oder Formate registriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-105">With this type of snap-in, you specify which cmdlets, providers, types, or formats to register.</span></span> <span data-ttu-id="0b4a5-106">Weitere Informationen zum Schreiben eines Snap-Ins, das alle Cmdlets und Anbieter in einer Assembly registriert, finden Sie unter [Schreiben eines Windows PowerShell-Snap-Ins](./writing-a-windows-powershell-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-106">For more information about how to write a snap-in that registers all the cmdlets and providers in an assembly, see [Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md).</span></span>

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a><span data-ttu-id="0b4a5-107">Zum Schreiben eines Windows PowerShell-Snap-Ins, mit dem bestimmte Cmdlets registriert werden.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-107">To write a Windows PowerShell Snap-in that registers specific cmdlets.</span></span>

1. <span data-ttu-id="0b4a5-108">Fügen Sie das RunInstallerAttribute-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-108">Add the RunInstallerAttribute attribute.</span></span>
2. <span data-ttu-id="0b4a5-109">Erstellen Sie eine öffentliche Klasse, die von der [System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-109">Create a public class that derives from the [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class.</span></span>

   <span data-ttu-id="0b4a5-110">In diesem Beispiel lautet der Klassenname "custompssnapintest".</span><span class="sxs-lookup"><span data-stu-id="0b4a5-110">In this example, the class name is "CustomPSSnapinTest".</span></span>

3. <span data-ttu-id="0b4a5-111">Fügen Sie eine öffentliche Eigenschaft für den Namen des Snap-Ins hinzu (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-111">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="0b4a5-112">Verwenden Sie beim Benennen von Snap-Ins keines der folgenden Zeichen: `#` , `.` , `,` , `(` , `)` , `{` , `}` , `[` , `]` , `&` , `-` , `/` , `\` , `$` , `;` , `:` , `"` , `'` , `<` , `>` , `|` , `?` , `@` , `` ` `` , `*`</span><span class="sxs-lookup"><span data-stu-id="0b4a5-112">When naming snap-ins, do not use any of the following characters: `#`, `.`, `,`, `(`, `)`, `{`, `}`, `[`, `]`, `&`, `-`, `/`, `\`, `$`, `;`, `:`, `"`, `'`, `<`, `>`, `|`, `?`, `@`, `` ` ``, `*`</span></span>

   <span data-ttu-id="0b4a5-113">In diesem Beispiel lautet der Name des Snap-Ins "custompssnapintest".</span><span class="sxs-lookup"><span data-stu-id="0b4a5-113">In this example, the name of the snap-in is "CustomPSSnapInTest".</span></span>

4. <span data-ttu-id="0b4a5-114">Hinzufügen einer öffentlichen Eigenschaft für den Anbieter des Snap-Ins (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-114">Add a public property for the vendor of the snap-in (required).</span></span>

   <span data-ttu-id="0b4a5-115">In diesem Beispiel ist der Lieferant "Microsoft".</span><span class="sxs-lookup"><span data-stu-id="0b4a5-115">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="0b4a5-116">Fügen Sie eine öffentliche Eigenschaft für die Vendor-Ressource des Snap-Ins hinzu (optional).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-116">Add a public property for the vendor resource of the snap-in (optional).</span></span>

   <span data-ttu-id="0b4a5-117">In diesem Beispiel lautet die Ressource "Vendor" "custompssnapintest, Microsoft".</span><span class="sxs-lookup"><span data-stu-id="0b4a5-117">In this example, the vendor resource is "CustomPSSnapInTest,Microsoft".</span></span>

6. <span data-ttu-id="0b4a5-118">Fügen Sie eine öffentliche Eigenschaft für die Beschreibung des Snap-Ins hinzu (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-118">Add a public property for the description of the snap-in (required).</span></span>

   <span data-ttu-id="0b4a5-119">In diesem Beispiel lautet die Beschreibung: "Dies ist ein benutzerdefiniertes Windows PowerShell-Snap-in, das die `Test-HelloWorld` `Test-CustomSnapinTest` Cmdlets und enthält."</span><span class="sxs-lookup"><span data-stu-id="0b4a5-119">In this example, the description is: "This is a custom Windows PowerShell snap-in that includes the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets".</span></span>

7. <span data-ttu-id="0b4a5-120">Fügen Sie eine öffentliche Eigenschaft für die Description-Ressource des Snap-Ins hinzu (optional).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-120">Add a public property for the description resource of the snap-in (optional).</span></span>

   <span data-ttu-id="0b4a5-121">In diesem Beispiel lautet die Ressource "Vendor" wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0b4a5-121">In this example, the vendor resource is:</span></span>

   > <span data-ttu-id="0b4a5-122">Custompssnapintest ist ein benutzerdefiniertes Windows PowerShell-Snap-in, das die Test-HelloWorld-und Test-CustomSnapinTest-Cmdlets enthält.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-122">CustomPSSnapInTest, This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

8. <span data-ttu-id="0b4a5-123">Geben Sie die Cmdlets, die zum benutzerdefinierten Snap-in (optional) gehören, mithilfe der [System. Management. Automation. Runspaces. cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) -Klasse an.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-123">Specify the cmdlets that belong to the custom snap-in (optional) using the [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) class.</span></span> <span data-ttu-id="0b4a5-124">Die hier hinzugefügten Informationen umfassen den Namen des Cmdlets, den .NET-Typ und den Namen der Cmdlet-Hilfedatei (das Format des Cmdlet-Hilfe Dateinamens sollte lauten `name.dll-help.xml` ).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-124">The information added here includes the name of the cmdlet, its .NET type, and the cmdlet Help file name (the format of the cmdlet Help file name should be `name.dll-help.xml`).</span></span>

   <span data-ttu-id="0b4a5-125">In diesem Beispiel werden die Cmdlets Test-HelloWorld und testcustomsnapintest hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-125">This example adds the Test-HelloWorld and TestCustomSnapinTest cmdlets.</span></span>

9. <span data-ttu-id="0b4a5-126">Geben Sie die Anbieter an, die zum benutzerdefinierten Snap-in gehören (optional).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-126">Specify the providers that belong to the custom snap-in (optional).</span></span>

   <span data-ttu-id="0b4a5-127">In diesem Beispiel werden keine Anbieter angegeben.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-127">This example does not specify any providers.</span></span>

10. <span data-ttu-id="0b4a5-128">Geben Sie die Typen an, die zum benutzerdefinierten Snap-in gehören (optional).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-128">Specify the types that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="0b4a5-129">In diesem Beispiel werden keine Typen angegeben.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-129">This example does not specify any types.</span></span>

11. <span data-ttu-id="0b4a5-130">Geben Sie die Formate an, die zum benutzerdefinierten Snap-in gehören (optional).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-130">Specify the formats that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="0b4a5-131">In diesem Beispiel werden keine Formate angegeben.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-131">This example does not specify any formats.</span></span>

## <a name="example"></a><span data-ttu-id="0b4a5-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b4a5-132">Example</span></span>

<span data-ttu-id="0b4a5-133">Dieses Beispiel zeigt, wie Sie ein benutzerdefiniertes Windows PowerShell-Snap-in schreiben, das zum Registrieren der `Test-HelloWorld` Cmdlets und verwendet werden kann `Test-CustomSnapinTest` .</span><span class="sxs-lookup"><span data-stu-id="0b4a5-133">This example shows how to write a Custom Windows PowerShell snap-in that can be used to register the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets.</span></span> <span data-ttu-id="0b4a5-134">Beachten Sie, dass in diesem Beispiel die vollständige Assembly andere Cmdlets und Anbieter enthalten kann, die nicht von diesem Snap-in registriert werden.</span><span class="sxs-lookup"><span data-stu-id="0b4a5-134">Be aware that in this example, the complete assembly could contain other cmdlets and providers that would not be registered by this snap-in.</span></span>

```csharp
[RunInstaller(true)]
public class CustomPSSnapinTest : CustomPSSnapIn
{
  /// <summary>
  /// Creates an instance of CustomPSSnapInTest class.
  /// </summary>
  public CustomPSSnapinTest()
          : base()
  {
  }

  /// <summary>
  /// Specify the name of the custom PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "CustomPSSnapInTest";
    }
  }

  /// <summary>
  /// Specify the vendor for the custom PowerShell snap-in.
  /// </summary>
  public override string Vendor
  {
    get
    {
      return "Microsoft";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the vendor.
  /// Use the format: resourceBaseName,resourceName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
        return "CustomPSSnapInTest,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the custom PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the description.
  /// Use the format: resourceBaseName,Description.
  /// </summary>
  public override string DescriptionResource
  {
    get
    {
        return "CustomPSSnapInTest,This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
    }
  }

  /// <summary>
  /// Specify the cmdlets that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<CmdletConfigurationEntry> _cmdlets;
  public override Collection<CmdletConfigurationEntry> Cmdlets
  {
    get
    {
      if (_cmdlets == null)
      {
        _cmdlets = new Collection<CmdletConfigurationEntry>();
        _cmdlets.Add(new CmdletConfigurationEntry("test-customsnapintest", typeof(TestCustomSnapinTest), "TestCmdletHelp.dll-help.xml"));
        _cmdlets.Add(new CmdletConfigurationEntry("test-helloworld", typeof(TestHelloWorld), "HelloWorldHelp.dll-help.xml"));
      }

      return _cmdlets;
    }
  }

  /// <summary>
  /// Specify the providers that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<ProviderConfigurationEntry> _providers;
  public override Collection<ProviderConfigurationEntry> Providers
  {
    get
    {
      if (_providers == null)
      {
        _providers = new Collection<ProviderConfigurationEntry>();
      }

      return _providers;
    }
  }

  /// <summary>
  /// Specify the types that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<TypeConfigurationEntry> _types;
  public override Collection<TypeConfigurationEntry> Types
  {
    get
    {
      if (_types == null)
      {
        _types = new Collection<TypeConfigurationEntry>();
      }

      return _types;
    }
  }

  /// <summary>
  /// Specify the formats that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<FormatConfigurationEntry> _formats;
  public override Collection<FormatConfigurationEntry> Formats
  {
    get
    {
      if (_formats == null)
      {
        _formats = new Collection<FormatConfigurationEntry>();
      }

      return _formats;
    }
  }
}
```

<span data-ttu-id="0b4a5-135">Weitere Informationen zum Registrieren von Snap-Ins finden [Sie unter Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions/ms714644(v=vs.85)) im [Windows PowerShell-Programmier Handbuch](../prog-guide/windows-powershell-programmer-s-guide.md).</span><span class="sxs-lookup"><span data-stu-id="0b4a5-135">For more information about registering snap-ins, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)) in the [Windows PowerShell Programmer's Guide](../prog-guide/windows-powershell-programmer-s-guide.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b4a5-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b4a5-136">See Also</span></span>

<span data-ttu-id="0b4a5-137">[Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="0b4a5-137">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="0b4a5-138">Referenz zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b4a5-138">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
