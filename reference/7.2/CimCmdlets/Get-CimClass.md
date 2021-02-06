---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimclass?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimClass
ms.openlocfilehash: 483b4b5b940a9effca99e942b86a967de5d26d68
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599193"
---
# <span data-ttu-id="3c830-102">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="3c830-102">Get-CimClass</span></span>

## <span data-ttu-id="3c830-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3c830-103">SYNOPSIS</span></span>
<span data-ttu-id="3c830-104">Ruft eine Liste von CIM-Klassen in einem bestimmten Namespace ab.</span><span class="sxs-lookup"><span data-stu-id="3c830-104">Gets a list of CIM classes in a specific namespace.</span></span>

## <span data-ttu-id="3c830-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3c830-105">SYNTAX</span></span>

### <span data-ttu-id="3c830-106">Computergruppe (Standard)</span><span class="sxs-lookup"><span data-stu-id="3c830-106">ComputerSet (Default)</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

### <span data-ttu-id="3c830-107">Sessionset</span><span class="sxs-lookup"><span data-stu-id="3c830-107">SessionSet</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

## <span data-ttu-id="3c830-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3c830-108">DESCRIPTION</span></span>

<span data-ttu-id="3c830-109">Mit dem- `Get-CimClass` Cmdlet wird eine Liste der CIM-Klassen in einem bestimmten Namespace abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3c830-109">The `Get-CimClass` cmdlet retrieves a list of CIM classes in a specific namespace.</span></span> <span data-ttu-id="3c830-110">Wenn kein Klassenname angegeben wird, gibt das Cmdlet alle Klassen im-Namespace zurück.</span><span class="sxs-lookup"><span data-stu-id="3c830-110">If there is no class name supplied, then the cmdlet returns all the classes in the namespace.</span></span> <span data-ttu-id="3c830-111">Im Gegensatz zu einer CIM-Instanz enthalten CIM-Klassen nicht die CIM-Sitzung oder den Computernamen, von dem Sie abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3c830-111">Unlike a CIM instance, CIM classes do not contain the CIM session or computer name from which they are retrieved.</span></span>

## <span data-ttu-id="3c830-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3c830-112">EXAMPLES</span></span>

### <span data-ttu-id="3c830-113">Beispiel 1: alle Klassendefinitionen</span><span class="sxs-lookup"><span data-stu-id="3c830-113">Example 1: Get all the class definitions</span></span>

<span data-ttu-id="3c830-114">In diesem Beispiel werden alle Klassendefinitionen unter dem Namespace **root/cimv2** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3c830-114">This example gets all the class definitions under the namespace **root/cimv2**.</span></span>

```powershell
Get-CimClass
```

### <span data-ttu-id="3c830-115">Beispiel 2: erhalten der Klassen mit einem bestimmten Namen</span><span class="sxs-lookup"><span data-stu-id="3c830-115">Example 2: Get the classes with a specific name</span></span>

<span data-ttu-id="3c830-116">**In diesem** Beispiel werden die Klassen abgerufen, die den Word-Datenträger in ihren Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c830-116">This example gets the classes that contain the word **disk** in their names.</span></span>

```powershell
Get-CimClass -ClassName *disk*
```

### <span data-ttu-id="3c830-117">Beispiel 3: erhalten der Klassen mit einem bestimmten Methodennamen</span><span class="sxs-lookup"><span data-stu-id="3c830-117">Example 3: Get the classes with a specific method name</span></span>

<span data-ttu-id="3c830-118">In diesem Beispiel werden die Klassen abgerufen, die mit dem Namen **Win32** beginnen und einen Methodennamen aufweisen, der mit dem **Begriff** beginnt.</span><span class="sxs-lookup"><span data-stu-id="3c830-118">This example gets the classes that start with the name **Win32** and have a method name that starts with **Term**.</span></span>

```powershell
Get-CimClass -ClassName Win32* -MethodName Term*
```

### <span data-ttu-id="3c830-119">Beispiel 4: erhalten der Klassen mit einem bestimmten Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="3c830-119">Example 4: Get the classes with a specific property name</span></span>

<span data-ttu-id="3c830-120">In diesem Beispiel werden die Klassen abgerufen, die mit dem Namen **Win32** beginnen und über eine Eigenschaft mit dem Namen **handle** verfügen.</span><span class="sxs-lookup"><span data-stu-id="3c830-120">This example gets the classes that start with the name **Win32** and have a property named **Handle**.</span></span>

```powershell
Get-CimClass -ClassName Win32* -PropertyName Handle
```

### <span data-ttu-id="3c830-121">Beispiel 5: erhalten der Klassen mit einem bestimmten Qualifizierernamen</span><span class="sxs-lookup"><span data-stu-id="3c830-121">Example 5: Get the classes with a specific qualifier name</span></span>

<span data-ttu-id="3c830-122">In diesem Beispiel werden die Klassen abgerufen, die mit dem Namen **Win32** beginnen, das Wort **Disk** in ihren Namen enthalten und über die angegebene qualifiziererzuordnung verfügen. </span><span class="sxs-lookup"><span data-stu-id="3c830-122">This example gets the classes that start with the name **Win32**, contain the word **Disk** in their names and have the specified qualifier **Association**.</span></span>

```powershell
Get-CimClass -ClassName Win32*Disk* -QualifierName Association
```

### <span data-ttu-id="3c830-123">Beispiel 6: erhalten der Klassendefinitionen aus einem bestimmten Namespace</span><span class="sxs-lookup"><span data-stu-id="3c830-123">Example 6: Get the class definitions from a specific namespace</span></span>

<span data-ttu-id="3c830-124">In diesem Beispiel werden die Klassendefinitionen mit dem Wort **net** in ihren Namen aus dem angegebenen Namespace **root/standardCimv2** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3c830-124">This example gets the class definitions that contain the word **Net** in their names from the specified namespace **root/standardCimv2**.</span></span>

```powershell
Get-CimClass -Namespace root/standardCimv2 -ClassName *Net*
```

### <span data-ttu-id="3c830-125">Beispiel 7: erhalten der Klassendefinitionen von einem Remote Server</span><span class="sxs-lookup"><span data-stu-id="3c830-125">Example 7: Get the class definitions from a remote server</span></span>

<span data-ttu-id="3c830-126">**In diesem** Beispiel werden die Klassendefinitionen abgerufen, die den Word-Datenträger in ihren Namen aus den angegebenen Remote Servern **Server01** und **Server02** enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c830-126">This example gets the class definitions that contain the word **disk** in their names from the specified remote servers **Server01** and **Server02**.</span></span>

```powershell
Get-CimClass -ClassName *disk* -ComputerName Server01, Server02
```

### <span data-ttu-id="3c830-127">Beispiel 8: erhalten der Klassen mithilfe einer CIM-Sitzung</span><span class="sxs-lookup"><span data-stu-id="3c830-127">Example 8: Get the classes by using a CIM session</span></span>

```powershell
$s = New-CimSession -ComputerName Server01, Server02
Get-CimClass -ClassName *disk* -CimSession $s
```

<span data-ttu-id="3c830-128">Dieser Satz von Befehlen erstellt eine Sitzung mit mehreren Computern und speichert Sie `$s` mithilfe des `New-CimSession` Cmdlets in einer Variablen und ruft dann die Klassen mithilfe des `Get-CimClass` Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="3c830-128">This set of commands creates a session with multiple computers and stores it into a variable `$s` using the `New-CimSession` cmdlet, and then gets the classes using the `Get-CimClass` cmdlet.</span></span>

## <span data-ttu-id="3c830-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3c830-129">PARAMETERS</span></span>

### <span data-ttu-id="3c830-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="3c830-130">-CimSession</span></span>

<span data-ttu-id="3c830-131">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="3c830-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="3c830-132">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines- `New-CimSession` oder- `Get-CimSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3c830-132">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span> <span data-ttu-id="3c830-133">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="3c830-133">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: SessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3c830-134">-ClassName</span><span class="sxs-lookup"><span data-stu-id="3c830-134">-ClassName</span></span>

<span data-ttu-id="3c830-135">Gibt den Namen der CIM-Klasse an, für die der Vorgang durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3c830-135">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="3c830-136">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3c830-136">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="3c830-137">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="3c830-137">-ComputerName</span></span>

<span data-ttu-id="3c830-138">Gibt den Computer an, auf dem Sie den CIM-Vorgang ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="3c830-138">Specifies the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="3c830-139">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) als NetBIOS-Namen oder eine IP-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="3c830-139">You can specify a fully qualified domain name (FQDN) a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="3c830-140">Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="3c830-140">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="3c830-141">Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.</span><span class="sxs-lookup"><span data-stu-id="3c830-141">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="3c830-142">Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet die Verwendung einer CIM-Sitzung eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="3c830-142">If multiple operations are being performed on the same computer, using a CIM session gives better performance.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3c830-143">-MethodName</span><span class="sxs-lookup"><span data-stu-id="3c830-143">-MethodName</span></span>

<span data-ttu-id="3c830-144">Sucht die Klassen, die über eine Methode verfügen, die diesem Namen entspricht.</span><span class="sxs-lookup"><span data-stu-id="3c830-144">Finds the classes that have a method matching this name.</span></span> <span data-ttu-id="3c830-145">Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c830-145">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="3c830-146">-Namespace</span><span class="sxs-lookup"><span data-stu-id="3c830-146">-Namespace</span></span>

<span data-ttu-id="3c830-147">Gibt den Namespace für den CIM-Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="3c830-147">Specifies the namespace for CIM operation.</span></span> <span data-ttu-id="3c830-148">Der Standard Namespace ist **root/cimv2**.</span><span class="sxs-lookup"><span data-stu-id="3c830-148">The default namespace is **root/cimv2**.</span></span> <span data-ttu-id="3c830-149">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3c830-149">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3c830-150">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="3c830-150">-OperationTimeoutSec</span></span>

<span data-ttu-id="3c830-151">Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet.</span><span class="sxs-lookup"><span data-stu-id="3c830-151">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="3c830-152">Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="3c830-152">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="3c830-153">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="3c830-153">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3c830-154">-PropertyName</span><span class="sxs-lookup"><span data-stu-id="3c830-154">-PropertyName</span></span>

<span data-ttu-id="3c830-155">Sucht die Klassen, die über eine Eigenschaft verfügen, die diesem Namen entspricht.</span><span class="sxs-lookup"><span data-stu-id="3c830-155">Finds the classes which have a property matching this name.</span></span> <span data-ttu-id="3c830-156">Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c830-156">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3c830-157">-Qualifiername</span><span class="sxs-lookup"><span data-stu-id="3c830-157">-QualifierName</span></span>

<span data-ttu-id="3c830-158">Filtert die Klassen nach dem Qualifizierernamen auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="3c830-158">Filters the classes by class level qualifier name.</span></span> <span data-ttu-id="3c830-159">Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c830-159">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="3c830-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3c830-160">CommonParameters</span></span>

<span data-ttu-id="3c830-161">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3c830-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3c830-162">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3c830-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3c830-163">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3c830-163">INPUTS</span></span>

### <span data-ttu-id="3c830-164">Keine</span><span class="sxs-lookup"><span data-stu-id="3c830-164">None</span></span>

<span data-ttu-id="3c830-165">Dieses Cmdlet akzeptiert keine Eingabe Objekte.</span><span class="sxs-lookup"><span data-stu-id="3c830-165">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="3c830-166">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3c830-166">OUTPUTS</span></span>

### <span data-ttu-id="3c830-167">Microsoft. Management. Infrastructure. cimclass</span><span class="sxs-lookup"><span data-stu-id="3c830-167">Microsoft.Management.Infrastructure.CimClass</span></span>

<span data-ttu-id="3c830-168">Dieses Cmdlet gibt ein CIM-Klassenobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="3c830-168">This cmdlet returns a CIM class object.</span></span>

## <span data-ttu-id="3c830-169">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3c830-169">NOTES</span></span>

## <span data-ttu-id="3c830-170">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3c830-170">RELATED LINKS</span></span>

[<span data-ttu-id="3c830-171">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="3c830-171">New-CimSession</span></span>](New-CimSession.md)

