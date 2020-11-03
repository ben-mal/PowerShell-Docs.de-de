---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimclass?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimClass
ms.openlocfilehash: e5700af4ff3f238d347e2c367416af08caf148ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212460"
---
# <span data-ttu-id="b5313-103">Get-CimClass</span><span class="sxs-lookup"><span data-stu-id="b5313-103">Get-CimClass</span></span>

## <span data-ttu-id="b5313-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b5313-104">SYNOPSIS</span></span>
<span data-ttu-id="b5313-105">Ruft eine Liste von CIM-Klassen in einem bestimmten Namespace ab.</span><span class="sxs-lookup"><span data-stu-id="b5313-105">Gets a list of CIM classes in a specific namespace.</span></span>

## <span data-ttu-id="b5313-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5313-106">SYNTAX</span></span>

### <span data-ttu-id="b5313-107">Computergruppe (Standard)</span><span class="sxs-lookup"><span data-stu-id="b5313-107">ComputerSet (Default)</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

### <span data-ttu-id="b5313-108">Sessionset</span><span class="sxs-lookup"><span data-stu-id="b5313-108">SessionSet</span></span>

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

## <span data-ttu-id="b5313-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b5313-109">DESCRIPTION</span></span>

<span data-ttu-id="b5313-110">Mit dem- `Get-CimClass` Cmdlet wird eine Liste der CIM-Klassen in einem bestimmten Namespace abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b5313-110">The `Get-CimClass` cmdlet retrieves a list of CIM classes in a specific namespace.</span></span> <span data-ttu-id="b5313-111">Wenn kein Klassenname angegeben wird, gibt das Cmdlet alle Klassen im-Namespace zurück.</span><span class="sxs-lookup"><span data-stu-id="b5313-111">If there is no class name supplied, then the cmdlet returns all the classes in the namespace.</span></span> <span data-ttu-id="b5313-112">Im Gegensatz zu einer CIM-Instanz enthalten CIM-Klassen nicht die CIM-Sitzung oder den Computernamen, von dem Sie abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b5313-112">Unlike a CIM instance, CIM classes do not contain the CIM session or computer name from which they are retrieved.</span></span>

## <span data-ttu-id="b5313-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b5313-113">EXAMPLES</span></span>

### <span data-ttu-id="b5313-114">Beispiel 1: alle Klassendefinitionen</span><span class="sxs-lookup"><span data-stu-id="b5313-114">Example 1: Get all the class definitions</span></span>

<span data-ttu-id="b5313-115">In diesem Beispiel werden alle Klassendefinitionen unter dem Namespace **root/cimv2** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b5313-115">This example gets all the class definitions under the namespace **root/cimv2** .</span></span>

```powershell
Get-CimClass
```

### <span data-ttu-id="b5313-116">Beispiel 2: erhalten der Klassen mit einem bestimmten Namen</span><span class="sxs-lookup"><span data-stu-id="b5313-116">Example 2: Get the classes with a specific name</span></span>

<span data-ttu-id="b5313-117">**In diesem** Beispiel werden die Klassen abgerufen, die den Word-Datenträger in ihren Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5313-117">This example gets the classes that contain the word **disk** in their names.</span></span>

```powershell
Get-CimClass -ClassName *disk*
```

### <span data-ttu-id="b5313-118">Beispiel 3: erhalten der Klassen mit einem bestimmten Methodennamen</span><span class="sxs-lookup"><span data-stu-id="b5313-118">Example 3: Get the classes with a specific method name</span></span>

<span data-ttu-id="b5313-119">In diesem Beispiel werden die Klassen abgerufen, die mit dem Namen **Win32** beginnen und einen Methodennamen aufweisen, der mit dem **Begriff** beginnt.</span><span class="sxs-lookup"><span data-stu-id="b5313-119">This example gets the classes that start with the name **Win32** and have a method name that starts with **Term** .</span></span>

```powershell
Get-CimClass -ClassName Win32* -MethodName Term*
```

### <span data-ttu-id="b5313-120">Beispiel 4: erhalten der Klassen mit einem bestimmten Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="b5313-120">Example 4: Get the classes with a specific property name</span></span>

<span data-ttu-id="b5313-121">In diesem Beispiel werden die Klassen abgerufen, die mit dem Namen **Win32** beginnen und über eine Eigenschaft mit dem Namen **handle** verfügen.</span><span class="sxs-lookup"><span data-stu-id="b5313-121">This example gets the classes that start with the name **Win32** and have a property named **Handle** .</span></span>

```powershell
Get-CimClass -ClassName Win32* -PropertyName Handle
```

### <span data-ttu-id="b5313-122">Beispiel 5: erhalten der Klassen mit einem bestimmten Qualifizierernamen</span><span class="sxs-lookup"><span data-stu-id="b5313-122">Example 5: Get the classes with a specific qualifier name</span></span>

<span data-ttu-id="b5313-123">In diesem Beispiel werden die Klassen abgerufen, die mit dem Namen **Win32** beginnen, das Wort **Disk** in ihren Namen enthalten und über die angegebene qualifiziererzuordnung verfügen. **Association**</span><span class="sxs-lookup"><span data-stu-id="b5313-123">This example gets the classes that start with the name **Win32** , contain the word **Disk** in their names and have the specified qualifier **Association** .</span></span>

```powershell
Get-CimClass -ClassName Win32*Disk* -QualifierName Association
```

### <span data-ttu-id="b5313-124">Beispiel 6: erhalten der Klassendefinitionen aus einem bestimmten Namespace</span><span class="sxs-lookup"><span data-stu-id="b5313-124">Example 6: Get the class definitions from a specific namespace</span></span>

<span data-ttu-id="b5313-125">In diesem Beispiel werden die Klassendefinitionen mit dem Wort **net** in ihren Namen aus dem angegebenen Namespace **root/standardCimv2** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b5313-125">This example gets the class definitions that contain the word **Net** in their names from the specified namespace **root/standardCimv2** .</span></span>

```powershell
Get-CimClass -Namespace root/standardCimv2 -ClassName *Net*
```

### <span data-ttu-id="b5313-126">Beispiel 7: erhalten der Klassendefinitionen von einem Remote Server</span><span class="sxs-lookup"><span data-stu-id="b5313-126">Example 7: Get the class definitions from a remote server</span></span>

<span data-ttu-id="b5313-127">**In diesem** Beispiel werden die Klassendefinitionen abgerufen, die den Word-Datenträger in ihren Namen aus den angegebenen Remote Servern **Server01** und **Server02** enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5313-127">This example gets the class definitions that contain the word **disk** in their names from the specified remote servers **Server01** and **Server02** .</span></span>

```powershell
Get-CimClass -ClassName *disk* -ComputerName Server01, Server02
```

### <span data-ttu-id="b5313-128">Beispiel 8: erhalten der Klassen mithilfe einer CIM-Sitzung</span><span class="sxs-lookup"><span data-stu-id="b5313-128">Example 8: Get the classes by using a CIM session</span></span>

```powershell
$s = New-CimSession -ComputerName Server01, Server02
Get-CimClass -ClassName *disk* -CimSession $s
```

<span data-ttu-id="b5313-129">Dieser Satz von Befehlen erstellt eine Sitzung mit mehreren Computern und speichert Sie `$s` mithilfe des `New-CimSession` Cmdlets in einer Variablen und ruft dann die Klassen mithilfe des `Get-CimClass` Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="b5313-129">This set of commands creates a session with multiple computers and stores it into a variable `$s` using the `New-CimSession` cmdlet, and then gets the classes using the `Get-CimClass` cmdlet.</span></span>

## <span data-ttu-id="b5313-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5313-130">PARAMETERS</span></span>

### <span data-ttu-id="b5313-131">-CimSession</span><span class="sxs-lookup"><span data-stu-id="b5313-131">-CimSession</span></span>

<span data-ttu-id="b5313-132">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="b5313-132">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="b5313-133">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines- `New-CimSession` oder- `Get-CimSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b5313-133">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span> <span data-ttu-id="b5313-134">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="b5313-134">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="b5313-135">-ClassName</span><span class="sxs-lookup"><span data-stu-id="b5313-135">-ClassName</span></span>

<span data-ttu-id="b5313-136">Gibt den Namen der CIM-Klasse an, für die der Vorgang durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5313-136">Specifies the name of the CIM class for which to perform the operation.</span></span> <span data-ttu-id="b5313-137">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b5313-137">You can use tab completion to browse the list of classes, because PowerShell gets a list of classes from the local WMI server to provide a list of class names.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b5313-138">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b5313-138">-ComputerName</span></span>

<span data-ttu-id="b5313-139">Gibt den Computer an, auf dem Sie den CIM-Vorgang ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="b5313-139">Specifies the computer on which you want to run the CIM operation.</span></span> <span data-ttu-id="b5313-140">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) als NetBIOS-Namen oder eine IP-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="b5313-140">You can specify a fully qualified domain name (FQDN) a NetBIOS name, or an IP address.</span></span>

<span data-ttu-id="b5313-141">Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="b5313-141">If you specify this parameter, the cmdlet creates a temporary session to the specified computer using the WsMan protocol.</span></span>

<span data-ttu-id="b5313-142">Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.</span><span class="sxs-lookup"><span data-stu-id="b5313-142">If you do not specify this parameter, the cmdlet performs the operation on the local computer using Component Object Model (COM).</span></span>

<span data-ttu-id="b5313-143">Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet die Verwendung einer CIM-Sitzung eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="b5313-143">If multiple operations are being performed on the same computer, using a CIM session gives better performance.</span></span>

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

### <span data-ttu-id="b5313-144">-MethodName</span><span class="sxs-lookup"><span data-stu-id="b5313-144">-MethodName</span></span>

<span data-ttu-id="b5313-145">Sucht die Klassen, die über eine Methode verfügen, die diesem Namen entspricht.</span><span class="sxs-lookup"><span data-stu-id="b5313-145">Finds the classes that have a method matching this name.</span></span> <span data-ttu-id="b5313-146">Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5313-146">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="b5313-147">-Namespace</span><span class="sxs-lookup"><span data-stu-id="b5313-147">-Namespace</span></span>

<span data-ttu-id="b5313-148">Gibt den Namespace für den CIM-Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="b5313-148">Specifies the namespace for CIM operation.</span></span> <span data-ttu-id="b5313-149">Der Standard Namespace ist **root/cimv2** .</span><span class="sxs-lookup"><span data-stu-id="b5313-149">The default namespace is **root/cimv2** .</span></span> <span data-ttu-id="b5313-150">Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b5313-150">You can use tab completion to browse the list of namespaces, because PowerShell gets a list of namespaces from the local WMI server to provide the list of namespaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b5313-151">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="b5313-151">-OperationTimeoutSec</span></span>

<span data-ttu-id="b5313-152">Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet.</span><span class="sxs-lookup"><span data-stu-id="b5313-152">Specifies the amount of time that the cmdlet waits for a response from the computer.</span></span> <span data-ttu-id="b5313-153">Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5313-153">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="b5313-154">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="b5313-154">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

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

### <span data-ttu-id="b5313-155">-PropertyName</span><span class="sxs-lookup"><span data-stu-id="b5313-155">-PropertyName</span></span>

<span data-ttu-id="b5313-156">Sucht die Klassen, die über eine Eigenschaft verfügen, die diesem Namen entspricht.</span><span class="sxs-lookup"><span data-stu-id="b5313-156">Finds the classes which have a property matching this name.</span></span> <span data-ttu-id="b5313-157">Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5313-157">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="b5313-158">-Qualifiername</span><span class="sxs-lookup"><span data-stu-id="b5313-158">-QualifierName</span></span>

<span data-ttu-id="b5313-159">Filtert die Klassen nach dem Qualifizierernamen auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="b5313-159">Filters the classes by class level qualifier name.</span></span> <span data-ttu-id="b5313-160">Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5313-160">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="b5313-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b5313-161">CommonParameters</span></span>

<span data-ttu-id="b5313-162">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b5313-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5313-163">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b5313-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5313-164">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b5313-164">INPUTS</span></span>

### <span data-ttu-id="b5313-165">Keine</span><span class="sxs-lookup"><span data-stu-id="b5313-165">None</span></span>

<span data-ttu-id="b5313-166">Dieses Cmdlet akzeptiert keine Eingabe Objekte.</span><span class="sxs-lookup"><span data-stu-id="b5313-166">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="b5313-167">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b5313-167">OUTPUTS</span></span>

### <span data-ttu-id="b5313-168">Microsoft. Management. Infrastructure. cimclass</span><span class="sxs-lookup"><span data-stu-id="b5313-168">Microsoft.Management.Infrastructure.CimClass</span></span>

<span data-ttu-id="b5313-169">Dieses Cmdlet gibt ein CIM-Klassenobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="b5313-169">This cmdlet returns a CIM class object.</span></span>

## <span data-ttu-id="b5313-170">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b5313-170">NOTES</span></span>

## <span data-ttu-id="b5313-171">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b5313-171">RELATED LINKS</span></span>

[<span data-ttu-id="b5313-172">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="b5313-172">New-CimSession</span></span>](New-CimSession.md)
