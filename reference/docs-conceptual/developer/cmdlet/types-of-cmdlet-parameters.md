---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet-Parametertypen
description: Cmdlet-Parametertypen
ms.openlocfilehash: 8daaa3c778396e06a826de3b93e0610c51160fb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660486"
---
# <a name="types-of-cmdlet-parameters"></a><span data-ttu-id="82fc9-103">Cmdlet-Parametertypen</span><span class="sxs-lookup"><span data-stu-id="82fc9-103">Types of Cmdlet Parameters</span></span>

<span data-ttu-id="82fc9-104">In diesem Thema werden die verschiedenen Parametertypen beschrieben, die Sie in Cmdlets deklarieren können.</span><span class="sxs-lookup"><span data-stu-id="82fc9-104">This topic describes the different types of parameters that you can declare in cmdlets.</span></span> <span data-ttu-id="82fc9-105">Cmdlet-Parameter können Positions-, benannte, erforderliche, optionale oder Switch-Parameter sein.</span><span class="sxs-lookup"><span data-stu-id="82fc9-105">Cmdlet parameters can be positional, named, required, optional, or switch parameters.</span></span>

## <a name="positional-and-named-parameters"></a><span data-ttu-id="82fc9-106">Positions Parameter und benannte Parameter</span><span class="sxs-lookup"><span data-stu-id="82fc9-106">Positional and Named Parameters</span></span>

<span data-ttu-id="82fc9-107">Alle Cmdlet-Parameter sind entweder benannte oder positionelle Parameter.</span><span class="sxs-lookup"><span data-stu-id="82fc9-107">All cmdlet parameters are either named or positional parameters.</span></span> <span data-ttu-id="82fc9-108">Ein benannter Parameter erfordert, dass Sie den Parameternamen und das Argument eingeben, wenn Sie das Cmdlet aufrufen.</span><span class="sxs-lookup"><span data-stu-id="82fc9-108">A named parameter requires that you type the parameter name and argument when calling the cmdlet.</span></span> <span data-ttu-id="82fc9-109">Ein Positions Parameter erfordert nur, dass Sie die Argumente in relativer Reihenfolge eingeben.</span><span class="sxs-lookup"><span data-stu-id="82fc9-109">A positional parameter requires only that you type the arguments in relative order.</span></span> <span data-ttu-id="82fc9-110">Das System ordnet dann das erste unbenannte Argument dem ersten Positions Parameter zu.</span><span class="sxs-lookup"><span data-stu-id="82fc9-110">The system then maps the first unnamed argument to the first positional parameter.</span></span> <span data-ttu-id="82fc9-111">Das System ordnet das zweite unbenannte Argument dem zweiten unbenannten Parameter zu usw.</span><span class="sxs-lookup"><span data-stu-id="82fc9-111">The system maps the second unnamed argument to the second unnamed parameter, and so on.</span></span> <span data-ttu-id="82fc9-112">Standardmäßig sind alle Cmdlet-Parameter benannte Parameter.</span><span class="sxs-lookup"><span data-stu-id="82fc9-112">By default, all cmdlet parameters are named parameters.</span></span>

<span data-ttu-id="82fc9-113">Um einen benannten Parameter zu definieren, lassen Sie das- `Position` Schlüsselwort in der Deklaration des **Parameter** Attributs aus, wie in der folgenden Parameter Deklaration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="82fc9-113">To define a named parameter, omit the `Position` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="82fc9-114">Um einen Positions Parameter zu definieren, fügen Sie das `Position` -Schlüsselwort in der Attribut Deklaration des Parameters ein, und geben Sie dann eine Position an</span><span class="sxs-lookup"><span data-stu-id="82fc9-114">To define a positional parameter, add the `Position` keyword in the Parameter attribute declaration, and then specify a position.</span></span> <span data-ttu-id="82fc9-115">Im folgenden Beispiel wird der- `UserName` Parameter als Positions Parameter mit der Position 0 deklariert.</span><span class="sxs-lookup"><span data-stu-id="82fc9-115">In the following sample, the `UserName` parameter is declared as a positional parameter with position 0.</span></span> <span data-ttu-id="82fc9-116">Dies bedeutet, dass das erste Argument des Aufrufes automatisch an diesen Parameter gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="82fc9-116">This means that the first argument of the call will be automatically bound to this parameter.</span></span>

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

> [!NOTE]
> <span data-ttu-id="82fc9-117">Ein gutes Cmdlet-Design empfiehlt, dass die am häufigsten verwendeten Parameter als Positions Parameter deklariert werden, damit der Benutzer den Parameternamen nicht eingeben muss, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="82fc9-117">Good cmdlet design recommends that the most-used parameters be declared as positional parameters so that the user does not have to enter the parameter name when the cmdlet is run.</span></span>

<span data-ttu-id="82fc9-118">Positions Parameter und benannte Parameter akzeptieren einzelne Argumente oder mehrere Argumente, die durch Kommas getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="82fc9-118">Positional and named parameters accept single arguments or multiple arguments separated by commas.</span></span> <span data-ttu-id="82fc9-119">Mehrere Argumente sind nur zulässig, wenn der Parameter eine Auflistung, z. b. ein Array von Zeichen folgen, akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="82fc9-119">Multiple arguments are allowed only if the parameter accepts a collection such as an array of strings.</span></span> <span data-ttu-id="82fc9-120">Sie können positionelle und benannte Parameter im gleichen Cmdlet kombinieren.</span><span class="sxs-lookup"><span data-stu-id="82fc9-120">You may mix positional and named parameters in the same cmdlet.</span></span> <span data-ttu-id="82fc9-121">In diesem Fall ruft das System zuerst die benannten Argumente ab und versucht dann, die verbleibenden unbenannten Argumente den Positions Parametern zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="82fc9-121">In this case, the system retrieves the named arguments first, and then attempts to map the remaining unnamed arguments to the positional parameters.</span></span>

<span data-ttu-id="82fc9-122">Die folgenden Befehle zeigen die verschiedenen Methoden, mit denen Sie einzelne und mehrere Argumente für die Parameter des `Get-Command` Cmdlets angeben können.</span><span class="sxs-lookup"><span data-stu-id="82fc9-122">The following commands show the different ways in which you can specify single and multiple arguments for the parameters of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="82fc9-123">Beachten Sie, dass der **-Name** in den letzten beiden Beispielen nicht angegeben werden muss, da der- `Name` Parameter als Positions Parameter definiert ist.</span><span class="sxs-lookup"><span data-stu-id="82fc9-123">Notice that in the last two samples, **-name** does not need to be specified because the `Name` parameter is defined as a positional parameter.</span></span>

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a><span data-ttu-id="82fc9-124">Obligatorische und optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="82fc9-124">Mandatory and Optional Parameters</span></span>

<span data-ttu-id="82fc9-125">Sie können auch Cmdlet-Parameter als obligatorische oder optionale Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="82fc9-125">You can also define cmdlet parameters as mandatory or optional parameters.</span></span> <span data-ttu-id="82fc9-126">(Ein obligatorischer Parameter muss angegeben werden, bevor das Cmdlet von der Windows PowerShell-Laufzeit aufgerufen wird.)  Standardmäßig werden Parameter als optional definiert.</span><span class="sxs-lookup"><span data-stu-id="82fc9-126">(A mandatory parameter must be specified before the Windows PowerShell runtime invokes the cmdlet.)  By default, parameters are defined as optional.</span></span>

<span data-ttu-id="82fc9-127">Zum Definieren eines obligatorischen Parameters fügen Sie das `Mandatory` -Schlüsselwort in der Deklaration des Parameter Attributs hinzu, und legen Sie es auf fest `true` , wie in der folgenden Parameter Deklaration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="82fc9-127">To define a mandatory parameter, add the `Mandatory` keyword in the Parameter attribute declaration, and set it to `true`, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="82fc9-128">Um einen optionalen Parameter zu definieren, lassen Sie das- `Mandatory` Schlüsselwort in der Deklaration des **Parameter** Attributs aus, wie in der folgenden Parameter Deklaration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="82fc9-128">To define an optional parameter, omit the `Mandatory` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a><span data-ttu-id="82fc9-129">Parameter wechseln</span><span class="sxs-lookup"><span data-stu-id="82fc9-129">Switch Parameters</span></span>

<span data-ttu-id="82fc9-130">Windows PowerShell stellt einen [System. Management. Automation. Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter) -Typ bereit, mit dem Sie einen Parameter definieren können, dessen Wert automatisch auf festgelegt wird, `false` Wenn der-Parameter nicht angegeben wird, wenn das Cmdlet aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="82fc9-130">Windows PowerShell provides a [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type that allows you to define a parameter whose value is automatically set to `false` if the parameter is not specified when the cmdlet is called.</span></span> <span data-ttu-id="82fc9-131">Verwenden Sie nach Möglichkeit anstelle von booleschen Parametern Switchparameter.</span><span class="sxs-lookup"><span data-stu-id="82fc9-131">Whenever possible, use switch parameters in place of Boolean parameters.</span></span>

<span data-ttu-id="82fc9-132">Sehen Sie sich das folgende Beispiel an.</span><span class="sxs-lookup"><span data-stu-id="82fc9-132">Consider the following sample.</span></span> <span data-ttu-id="82fc9-133">Standardmäßig übergeben mehrere Windows PowerShell-Cmdlets kein Ausgabe Objekt in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="82fc9-133">By default, several Windows PowerShell cmdlets do not pass an output object down the pipeline.</span></span> <span data-ttu-id="82fc9-134">Diese Cmdlets verfügen jedoch über einen `PassThru` Switch-Parameter, der das Standardverhalten überschreibt.</span><span class="sxs-lookup"><span data-stu-id="82fc9-134">However, these cmdlets have a `PassThru` switch parameter that overrides the default behavior.</span></span> <span data-ttu-id="82fc9-135">Wenn der- `PassThru` Parameter angegeben wird, wenn diese Cmdlets aufgerufen werden, gibt das Cmdlet ein Ausgabe Objekt an die Pipeline zurück.</span><span class="sxs-lookup"><span data-stu-id="82fc9-135">If the `PassThru` parameter is specified when these cmdlets are called, the cmdlet returns an output object to the pipeline.</span></span>

<span data-ttu-id="82fc9-136">Wenn Sie für den-Parameter den Standardwert benötigen `true` , wenn der-Parameter nicht im-Befehl angegeben ist, sollten Sie den Sinn des Parameters umkehren.</span><span class="sxs-lookup"><span data-stu-id="82fc9-136">If you need the parameter to have a default value of `true` when the parameter is not specified in the call, consider reversing the sense of the parameter.</span></span> <span data-ttu-id="82fc9-137">Wenn Sie z. b. das Parameter Attribut nicht auf einen booleschen Wert festlegen, `true` deklarieren Sie die Eigenschaft als [System. Management. Automation. Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter) -Typ, und legen Sie dann den Standardwert des-Parameters auf fest `false` .</span><span class="sxs-lookup"><span data-stu-id="82fc9-137">For sample, instead of setting the parameter attribute to a Boolean value of `true`, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, and then set the default value of the parameter to `false`.</span></span>

<span data-ttu-id="82fc9-138">Um einen Switch-Parameter zu definieren, deklarieren Sie die Eigenschaft als [System. Management. Automation. Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter) -Typ, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="82fc9-138">To define a switch parameter, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, as shown in the following sample.</span></span>

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

<span data-ttu-id="82fc9-139">Um das Cmdlet für den Parameter zu verwenden, wenn es angegeben ist, verwenden Sie die folgende Struktur in einer der Eingabe Verarbeitungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="82fc9-139">To make the cmdlet act on the parameter when it is specified, use the following structure within one of the input processing methods.</span></span>

```csharp
protected override void ProcessRecord()
{
  WriteObject("Switch parameter test: " + userName + ".");
  if(goodbye)
  {
    WriteObject(" Goodbye!");
  }
} // End ProcessRecord
```

## <a name="see-also"></a><span data-ttu-id="82fc9-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82fc9-140">See Also</span></span>

[<span data-ttu-id="82fc9-141">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="82fc9-141">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
