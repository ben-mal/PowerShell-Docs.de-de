---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-webserviceproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebServiceProxy
ms.openlocfilehash: aea656bc8ad4416673a7abb7d32a58d45dd3cc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214599"
---
# <span data-ttu-id="2d555-103">New-WebServiceProxy</span><span class="sxs-lookup"><span data-stu-id="2d555-103">New-WebServiceProxy</span></span>

## <span data-ttu-id="2d555-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2d555-104">SYNOPSIS</span></span>
<span data-ttu-id="2d555-105">Erstellt ein Webdienst Proxy-Objekt, mit dem Sie den Webdienst in PowerShell verwenden und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="2d555-105">Creates a Web service proxy object that lets you use and manage the Web service in PowerShell.</span></span>

## <span data-ttu-id="2d555-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d555-106">SYNTAX</span></span>

### <span data-ttu-id="2d555-107">Noanmelde Informationen (Standard)</span><span class="sxs-lookup"><span data-stu-id="2d555-107">NoCredentials (Default)</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [<CommonParameters>]
```

### <span data-ttu-id="2d555-108">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="2d555-108">Credential</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="2d555-109">UseDefaultCredential</span><span class="sxs-lookup"><span data-stu-id="2d555-109">UseDefaultCredential</span></span>

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-UseDefaultCredential]
 [<CommonParameters>]
```

## <span data-ttu-id="2d555-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2d555-110">DESCRIPTION</span></span>

<span data-ttu-id="2d555-111">Mit dem- `New-WebServiceProxy` Cmdlet können Sie einen Webdienst in PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d555-111">The `New-WebServiceProxy` cmdlet lets you use a Web service in PowerShell.</span></span> <span data-ttu-id="2d555-112">Das-Cmdlet stellt eine Verbindung mit einem Webdienst her und erstellt ein Webdienst Proxy-Objekt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d555-112">The cmdlet connects to a Web service and creates a Web service proxy object in PowerShell.</span></span> <span data-ttu-id="2d555-113">Sie können den Webdienst mithilfe des Proxyobjekts verwalten.</span><span class="sxs-lookup"><span data-stu-id="2d555-113">You can use the proxy object to manage the Web service.</span></span>

<span data-ttu-id="2d555-114">Ein Webdienst ist ein XML-basiertes Programm, das Daten über ein Netzwerk austauscht, insbesondere über das Internet.</span><span class="sxs-lookup"><span data-stu-id="2d555-114">A Web service is an XML-based program that exchanges data over a network, especially over the Internet.</span></span> <span data-ttu-id="2d555-115">Microsoft .NET Framework stellt Webdienstproxyobjekte bereit, die den Webdienst als .NET Framework-Objekt darstellen.</span><span class="sxs-lookup"><span data-stu-id="2d555-115">The Microsoft .NET Framework provides Web service proxy objects that represent the Web service as a .NET Framework object.</span></span>

## <span data-ttu-id="2d555-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2d555-116">EXAMPLES</span></span>

### <span data-ttu-id="2d555-117">Beispiel 1: Erstellen eines Proxys für einen Webdienst</span><span class="sxs-lookup"><span data-stu-id="2d555-117">Example 1: Create a proxy for a Web service</span></span>

<span data-ttu-id="2d555-118">In diesem Beispiel wird ein .NET Framework Proxy des Rechner-Webdiensts in Windows PowerShell erstellt.</span><span class="sxs-lookup"><span data-stu-id="2d555-118">This example creates a .NET Framework proxy of the calculator Web service in Windows PowerShell.</span></span>

```powershell
$calc = New-WebServiceProxy -Uri "http://www.dneonline.com/calculator.asmx?wsdl"
```

### <span data-ttu-id="2d555-119">Beispiel 2: Erstellen eines Proxys für einen Webdienst und Angeben von Namespace und Klasse</span><span class="sxs-lookup"><span data-stu-id="2d555-119">Example 2: Create a proxy for a Web service and specify namespace and class</span></span>

<span data-ttu-id="2d555-120">In diesem Beispiel wird das- `New-WebServiceProxy` Cmdlet zum Erstellen eines .NET Framework Proxys des Rechner-Webdiensts verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d555-120">This example uses the `New-WebServiceProxy` cmdlet to create a .NET Framework proxy of the calculator Web service.</span></span>

```powershell
$URI = "http://www.dneonline.com/calculator.asmx?wsdl"
$calc = New-WebServiceProxy -Uri $URI -Namespace "WSProxy" -Class "Calculator"
```

<span data-ttu-id="2d555-121">Der Befehl verwendet den **URI** -Parameter, um den URI und den **Namespace** und die **Klassen** Parameter anzugeben, um den Namespace und die Klasse des Objekts anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2d555-121">The command uses the **Uri** parameter to specify the URI and the **Namespace** and **Class** parameters to specify the namespace and class of the object.</span></span>

### <span data-ttu-id="2d555-122">Beispiel 3: Anzeigen von Methoden eines Webdienst Proxys</span><span class="sxs-lookup"><span data-stu-id="2d555-122">Example 3: Display methods of a Web service proxy</span></span>

```powershell
$calc | Get-Member -MemberType method
```

```Output
   TypeName: WSProxy.Calculator

Name                      MemberType Definition
----                      ---------- ----------
Abort                     Method     void Abort()
Add                       Method     int Add(int intA, int intB)
AddAsync                  Method     void AddAsync(int intA, int intB), void AddAsync(int intA,
BeginAdd                  Method     System.IAsyncResult BeginAdd(int intA, int intB, System.Asy
BeginDivide               Method     System.IAsyncResult BeginDivide(int intA, int intB, System.
BeginMultiply             Method     System.IAsyncResult BeginMultiply(int intA, int intB, Syste
BeginSubtract             Method     System.IAsyncResult BeginSubtract(int intA, int intB, Syste
CancelAsync               Method     void CancelAsync(System.Object userState)
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type requestedT
Discover                  Method     void Discover()
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Divide                    Method     int Divide(int intA, int intB)
DivideAsync               Method     void DivideAsync(int intA, int intB), void DivideAsync(int
EndAdd                    Method     int EndAdd(System.IAsyncResult asyncResult)
EndDivide                 Method     int EndDivide(System.IAsyncResult asyncResult)
EndMultiply               Method     int EndMultiply(System.IAsyncResult asyncResult)
EndSubtract               Method     int EndSubtract(System.IAsyncResult asyncResult)
Equals                    Method     bool Equals(System.Object obj)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Multiply                  Method     int Multiply(int intA, int intB)
MultiplyAsync             Method     void MultiplyAsync(int intA, int intB), void MultiplyAsync(
Subtract                  Method     int Subtract(int intA, int intB)
SubtractAsync             Method     void SubtractAsync(int intA, int intB), void SubtractAsync(
ToString                  Method     string ToString()
```

<span data-ttu-id="2d555-123">In diesem Beispiel wird das- `Get-Member` Cmdlet verwendet, um die Methoden des Webdienst Proxy Objekts in der `$calc` Variablen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d555-123">This example uses the `Get-Member` cmdlet to display the methods of the Web service proxy object in the `$calc` variable.</span></span> <span data-ttu-id="2d555-124">Diese Methoden werden im folgenden Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d555-124">We uses these methods in the following example.</span></span>

<span data-ttu-id="2d555-125">Beachten Sie, dass der **Typname** des Proxy Objekts (WebServiceProxy) die Namespace-und Klassennamen darstellt, die im vorherigen Beispiel angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="2d555-125">Notice that the **TypeName** of the proxy object, WebServiceProxy, reflects the namespace and class names that were specified in the previous example.</span></span>

### <span data-ttu-id="2d555-126">Beispiel 4: Verwenden eines Webdienst Proxys</span><span class="sxs-lookup"><span data-stu-id="2d555-126">Example 4: Use a Web service proxy</span></span>

```powershell
PS> $calc.Multiply(6,7)
42
```

<span data-ttu-id="2d555-127">In diesem Beispiel wird der in der-Variablen gespeicherte Webdienst Proxy verwendet `$calc` .</span><span class="sxs-lookup"><span data-stu-id="2d555-127">This example uses the Web service proxy stored in the `$calc` variable.</span></span> <span data-ttu-id="2d555-128">Der Befehl verwendet die **Multiplikations** Methode des Proxys.</span><span class="sxs-lookup"><span data-stu-id="2d555-128">The command uses the **Multiply** method of the proxy.</span></span>

## <span data-ttu-id="2d555-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d555-129">PARAMETERS</span></span>

### <span data-ttu-id="2d555-130">-Klasse</span><span class="sxs-lookup"><span data-stu-id="2d555-130">-Class</span></span>

<span data-ttu-id="2d555-131">Gibt einen Namen für die Proxyklasse an, die das Cmdlet für den Webdienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="2d555-131">Specifies a name for the proxy class that the cmdlet creates for the Web service.</span></span> <span data-ttu-id="2d555-132">Der Wert dieses Parameters wird in Verbindung mit dem **Namespace** -Parameter verwendet, um einen voll qualifizierten Namen für die Klasse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2d555-132">The value of this parameter is used together with the **Namespace** parameter to provide a fully qualified name for the class.</span></span> <span data-ttu-id="2d555-133">Der Standardwert wird aus dem Uniform Resource Identifier (URI) generiert.</span><span class="sxs-lookup"><span data-stu-id="2d555-133">The default value is generated from the Uniform Resource Identifier (URI).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FileName, FN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d555-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="2d555-134">-Credential</span></span>

<span data-ttu-id="2d555-135">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="2d555-135">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="2d555-136">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2d555-136">The default is the current user.</span></span> <span data-ttu-id="2d555-137">Dies stellt eine Alternative zum Verwenden des **UseDefaultCredential** -Parameters dar.</span><span class="sxs-lookup"><span data-stu-id="2d555-137">This is an alternative to using the **UseDefaultCredential** parameter.</span></span>

<span data-ttu-id="2d555-138">Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="2d555-138">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2d555-139">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="2d555-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Credential
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d555-140">-Namespace</span><span class="sxs-lookup"><span data-stu-id="2d555-140">-Namespace</span></span>

<span data-ttu-id="2d555-141">Gibt einen Namespace für die neue Klasse an.</span><span class="sxs-lookup"><span data-stu-id="2d555-141">Specifies a namespace for the new class.</span></span>

<span data-ttu-id="2d555-142">Der Wert dieses Parameters wird mit dem Wert des **Class** -Parameters verwendet, um einen voll qualifizierten Namen für die Klasse zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2d555-142">The value of this parameter is used together with the value of the **Class** parameter to generate a fully qualified name for the class.</span></span> <span data-ttu-id="2d555-143">Der Standardwert ist **Microsoft. PowerShell. Commands. newwebserviceproxy. autogeneratedtypes** und ein Typ, der aus dem URI generiert wird.</span><span class="sxs-lookup"><span data-stu-id="2d555-143">The default value is **Microsoft.PowerShell.Commands.NewWebserviceProxy.AutogeneratedTypes** plus a type that is generated from the URI.</span></span>

<span data-ttu-id="2d555-144">Sie können den Wert des **Namespace** -Parameters so festlegen, dass Sie auf mehrere Webdienste mit demselben Namen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="2d555-144">You can set the value of the **Namespace** parameter so that you can access multiple Web services that have the same name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d555-145">-URI</span><span class="sxs-lookup"><span data-stu-id="2d555-145">-Uri</span></span>

<span data-ttu-id="2d555-146">Gibt den URI des Webdiensts an.</span><span class="sxs-lookup"><span data-stu-id="2d555-146">Specifies the URI of the Web service.</span></span> <span data-ttu-id="2d555-147">Geben Sie einen URI oder den Pfad und Dateinamen einer Datei ein, die eine Dienst Beschreibung enthält.</span><span class="sxs-lookup"><span data-stu-id="2d555-147">Enter a URI or the path and filename of a file that contains a service description.</span></span>

<span data-ttu-id="2d555-148">Der URI muss eine `.asmx` Seite oder eine Seite zurückgeben, die eine Dienst Beschreibung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2d555-148">The URI must return an `.asmx` page or to a page that returns a service description.</span></span> <span data-ttu-id="2d555-149">Fügen Sie zum Zurückgeben einer Dienst Beschreibung eines Webdiensts, der mit ASP.NET erstellt wurde, "? WSDL "an die URL des Webdiensts (z. b `http://www.contoso.com/MyWebService.asmx?WSDL` .).</span><span class="sxs-lookup"><span data-stu-id="2d555-149">To return a service description of a Web service that was created using ASP.NET, append "?WSDL" to the URL of the Web service (for example, `http://www.contoso.com/MyWebService.asmx?WSDL`).</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: WL, WSDL, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d555-150">-Usedefaultcredential</span><span class="sxs-lookup"><span data-stu-id="2d555-150">-UseDefaultCredential</span></span>

<span data-ttu-id="2d555-151">Gibt an, dass dieses Cmdlet die Standard Anmelde Informationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d555-151">Indicates that this cmdlet uses the default credential.</span></span> <span data-ttu-id="2d555-152">Mit diesem Cmdlet wird die **usedefaultcredential** -Eigenschaft des resultierenden Proxy Objekts auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2d555-152">This cmdlet sets the **UseDefaultCredential** property in the resulting proxy object to True.</span></span> <span data-ttu-id="2d555-153">Dies stellt eine Alternative zum Verwenden des **Credential** -Parameters dar.</span><span class="sxs-lookup"><span data-stu-id="2d555-153">This is an alternative to using the **Credential** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseDefaultCredential
Aliases: UDC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d555-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2d555-154">CommonParameters</span></span>

<span data-ttu-id="2d555-155">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2d555-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d555-156">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2d555-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2d555-157">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2d555-157">INPUTS</span></span>

### <span data-ttu-id="2d555-158">Keine</span><span class="sxs-lookup"><span data-stu-id="2d555-158">None</span></span>

<span data-ttu-id="2d555-159">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="2d555-159">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2d555-160">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2d555-160">OUTPUTS</span></span>

### <span data-ttu-id="2d555-161">Ein Webdienst-Proxy Objekt</span><span class="sxs-lookup"><span data-stu-id="2d555-161">A Web service proxy object</span></span>

<span data-ttu-id="2d555-162">Dieses Cmdlet gibt ein Webdienst Proxy-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="2d555-162">This cmdlet returns a Web service proxy object.</span></span> <span data-ttu-id="2d555-163">Der Namespace und die Klasse des Objekts werden von den Parametern des Befehls bestimmt.</span><span class="sxs-lookup"><span data-stu-id="2d555-163">The namespace and class of the object are determined by the parameters of the command.</span></span> <span data-ttu-id="2d555-164">Der Standardwert wird aus dem Eingabe-URI generiert.</span><span class="sxs-lookup"><span data-stu-id="2d555-164">The default is generated from the input URI.</span></span>

## <span data-ttu-id="2d555-165">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2d555-165">NOTES</span></span>

<span data-ttu-id="2d555-166">`New-WebServiceProxy` verwendet die **System .net. WebClient** -Klasse, um den angegebenen Webdienst zu laden.</span><span class="sxs-lookup"><span data-stu-id="2d555-166">`New-WebServiceProxy` uses the **System.Net.WebClient** class to load the specified Web service.</span></span>

## <span data-ttu-id="2d555-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2d555-167">RELATED LINKS</span></span>

[<span data-ttu-id="2d555-168">New-Service</span><span class="sxs-lookup"><span data-stu-id="2d555-168">New-Service</span></span>](New-Service.md)
