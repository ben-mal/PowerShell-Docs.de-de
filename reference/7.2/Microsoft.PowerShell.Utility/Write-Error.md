---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-error?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Error
ms.openlocfilehash: d0ee66e1002e4f1d58f63e198bcb7f03b1c8d3a8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603518"
---
# <span data-ttu-id="21c94-102">Write-Error</span><span class="sxs-lookup"><span data-stu-id="21c94-102">Write-Error</span></span>

## <span data-ttu-id="21c94-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="21c94-103">SYNOPSIS</span></span>
<span data-ttu-id="21c94-104">Schreibt ein Objekt in den Fehlerdatenstrom.</span><span class="sxs-lookup"><span data-stu-id="21c94-104">Writes an object to the error stream.</span></span>

## <span data-ttu-id="21c94-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21c94-105">SYNTAX</span></span>

### <span data-ttu-id="21c94-106">Noexception (Standard)</span><span class="sxs-lookup"><span data-stu-id="21c94-106">NoException (Default)</span></span>

```
Write-Error [-Message] <String> [-Category <ErrorCategory>] [-ErrorId <String>] [-TargetObject <Object>]
 [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="21c94-107">Withexception</span><span class="sxs-lookup"><span data-stu-id="21c94-107">WithException</span></span>

```
Write-Error -Exception <Exception> [[-Message] <String>] [-Category <ErrorCategory>] [-ErrorId <String>]
 [-TargetObject <Object>] [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="21c94-108">ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="21c94-108">ErrorRecord</span></span>

```
Write-Error -ErrorRecord <ErrorRecord> [-RecommendedAction <String>] [-CategoryActivity <String>]
 [-CategoryReason <String>] [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

## <span data-ttu-id="21c94-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21c94-109">DESCRIPTION</span></span>

<span data-ttu-id="21c94-110">Mit dem `Write-Error` -Cmdlet wird ein Fehler ohne Abbruch deklariert.</span><span class="sxs-lookup"><span data-stu-id="21c94-110">The `Write-Error` cmdlet declares a non-terminating error.</span></span> <span data-ttu-id="21c94-111">Standardmäßig werden Fehler im Fehlerdatenstrom an das Hostprogramm gesendet und zusammen mit der Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="21c94-111">By default, errors are sent in the error stream to the host program to be displayed, along with output.</span></span>

<span data-ttu-id="21c94-112">Um einen Fehler ohne Abbruch zu schreiben, geben Sie eine Fehlermeldungs-Zeichenfolge, ein **ErrorRecord**-Objekt oder ein **Exception**-Objekt ein.</span><span class="sxs-lookup"><span data-stu-id="21c94-112">To write a non-terminating error, enter an error message string, an **ErrorRecord** object, or an **Exception** object.</span></span> <span data-ttu-id="21c94-113">Verwenden Sie die anderen Parameter von `Write-Error` , um den Fehler Daten Satz aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="21c94-113">Use the other parameters of `Write-Error` to populate the error record.</span></span>

<span data-ttu-id="21c94-114">Fehler ohne Abbruch schreiben einen Fehler in den Fehlerdatenstrom, ohne die Befehlsverarbeitung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="21c94-114">Non-terminating errors write an error to the error stream, but they do not stop command processing.</span></span>
<span data-ttu-id="21c94-115">Wenn ein Fehler ohne Abbruch für ein einzelnes Element in einer Auflistung von Eingabeelementen deklariert wird, verarbeitet der Befehl weiterhin die anderen Elemente in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="21c94-115">If a non-terminating error is declared on one item in a collection of input items, the command continues to process the other items in the collection.</span></span>

<span data-ttu-id="21c94-116">Verwenden Sie das-Schlüsselwort, um einen Abbruch Fehler zu deklarieren `Throw` .</span><span class="sxs-lookup"><span data-stu-id="21c94-116">To declare a terminating error, use the `Throw` keyword.</span></span>
<span data-ttu-id="21c94-117">Weitere Informationen finden Sie unter [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span><span class="sxs-lookup"><span data-stu-id="21c94-117">For more information, see [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span></span>

## <span data-ttu-id="21c94-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="21c94-118">EXAMPLES</span></span>

### <span data-ttu-id="21c94-119">Beispiel 1: Schreiben eines Fehlers für das RegistryKey-Objekt</span><span class="sxs-lookup"><span data-stu-id="21c94-119">Example 1: Write an error for RegistryKey object</span></span>

```powershell
Get-ChildItem | ForEach-Object {
    if ($_.GetType().ToString() -eq "Microsoft.Win32.RegistryKey")
    {
        Write-Error "Invalid object" -ErrorId B1 -TargetObject $_
    }
    else
    {
        $_
    }
}
```

<span data-ttu-id="21c94-120">Mit diesem Befehl wird ein Fehler ohne Abbruch deklariert, wenn das `Get-ChildItem` Cmdlet ein-Objekt zurückgibt `Microsoft.Win32.RegistryKey` , wie z. b. die Objekte in den- `HKLM:` oder- `HKCU:` Laufwerken des PowerShell-Registrierungs Anbieters.</span><span class="sxs-lookup"><span data-stu-id="21c94-120">This command declares a non-terminating error when the `Get-ChildItem` cmdlet returns a `Microsoft.Win32.RegistryKey` object, such as the objects in the `HKLM:` or `HKCU:` drives of the PowerShell Registry provider.</span></span>

### <span data-ttu-id="21c94-121">Beispiel 2: Schreiben einer Fehlermeldung in die Konsole</span><span class="sxs-lookup"><span data-stu-id="21c94-121">Example 2: Write an error message to the console</span></span>

```powershell
Write-Error "Access denied."
```

<span data-ttu-id="21c94-122">Mit diesem Befehl wird ein Fehler ohne Abbruch deklariert und ein Fehler des Typs „Zugriff verweigert“ geschrieben.</span><span class="sxs-lookup"><span data-stu-id="21c94-122">This command declares a non-terminating error and writes an "Access denied" error.</span></span> <span data-ttu-id="21c94-123">Der Befehl verwendet den **Message**-Parameter zur Angabe der Meldung, lässt jedoch den optionalen **Message**-Parameternamen aus.</span><span class="sxs-lookup"><span data-stu-id="21c94-123">The command uses the **Message** parameter to specify the message, but omits the optional **Message** parameter name.</span></span>

### <span data-ttu-id="21c94-124">Beispiel 3: Schreiben eines Fehlers in die Konsole und angeben der Kategorie</span><span class="sxs-lookup"><span data-stu-id="21c94-124">Example 3: Write an error to the console and specify the category</span></span>

```powershell
Write-Error -Message "Error: Too many input values." -Category InvalidArgument
```

<span data-ttu-id="21c94-125">Mit diesem Befehl wird ein Fehler ohne Abbruch deklariert und eine Fehlerkategorie angegeben.</span><span class="sxs-lookup"><span data-stu-id="21c94-125">This command declares a non-terminating error and specifies an error category.</span></span>

### <span data-ttu-id="21c94-126">Beispiel 4: Schreiben eines Fehlers mit einem Exception-Objekt</span><span class="sxs-lookup"><span data-stu-id="21c94-126">Example 4: Write an error using an Exception object</span></span>

```powershell
$E = [System.Exception]@{Source="Get-ParameterNames.ps1";HelpLink="https://go.microsoft.com/fwlink/?LinkID=113425"}
Write-Error -Exception $E -Message "Files not found. The $Files location does not contain any XML files."
```

<span data-ttu-id="21c94-127">Dieser Befehl verwendet ein **Exception**-Objekt, um einen Fehler ohne Abbruch zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="21c94-127">This command uses an **Exception** object to declare a non-terminating error.</span></span>

<span data-ttu-id="21c94-128">Der erste Befehl verwendet eine Hashtabelle zum Erstellen des **System.Exception**-Objekts.</span><span class="sxs-lookup"><span data-stu-id="21c94-128">The first command uses a hash table to create the **System.Exception** object.</span></span> <span data-ttu-id="21c94-129">Das Ausnahme Objekt wird in der `$E` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="21c94-129">It saves the exception object in the `$E` variable.</span></span> <span data-ttu-id="21c94-130">Mithilfe einer Hashtabelle können Sie ein beliebiges Objekt eines Typs erstellen, der über einen NULL-Konstruktor verfügt.</span><span class="sxs-lookup"><span data-stu-id="21c94-130">You can use a hash table to create any object of a type that has a null constructor.</span></span>

<span data-ttu-id="21c94-131">Der zweite Befehl verwendet das `Write-Error` Cmdlet, um einen Fehler ohne Abbruch zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="21c94-131">The second command uses the `Write-Error` cmdlet to declare a non-terminating error.</span></span> <span data-ttu-id="21c94-132">Der Wert des **Exception** -Parameters ist das **Exception** -Objekt in der `$E` Variablen.</span><span class="sxs-lookup"><span data-stu-id="21c94-132">The value of the **Exception** parameter is the **Exception** object in the `$E` variable.</span></span>

## <span data-ttu-id="21c94-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21c94-133">PARAMETERS</span></span>

### <span data-ttu-id="21c94-134">-Kategorie</span><span class="sxs-lookup"><span data-stu-id="21c94-134">-Category</span></span>

<span data-ttu-id="21c94-135">Gibt die Kategorie des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="21c94-135">Specifies the category of the error.</span></span> <span data-ttu-id="21c94-136">Der Standardwert ist " **notangegeben**".</span><span class="sxs-lookup"><span data-stu-id="21c94-136">The default value is **NotSpecified**.</span></span> <span data-ttu-id="21c94-137">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="21c94-137">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="21c94-138">NotSpecified</span><span class="sxs-lookup"><span data-stu-id="21c94-138">NotSpecified</span></span>
- <span data-ttu-id="21c94-139">OpenError</span><span class="sxs-lookup"><span data-stu-id="21c94-139">OpenError</span></span>
- <span data-ttu-id="21c94-140">Closeerror</span><span class="sxs-lookup"><span data-stu-id="21c94-140">CloseError</span></span>
- <span data-ttu-id="21c94-141">Deviceerror</span><span class="sxs-lookup"><span data-stu-id="21c94-141">DeviceError</span></span>
- <span data-ttu-id="21c94-142">Deadlockerkannt</span><span class="sxs-lookup"><span data-stu-id="21c94-142">DeadlockDetected</span></span>
- <span data-ttu-id="21c94-143">Invalidargument</span><span class="sxs-lookup"><span data-stu-id="21c94-143">InvalidArgument</span></span>
- <span data-ttu-id="21c94-144">InvalidData</span><span class="sxs-lookup"><span data-stu-id="21c94-144">InvalidData</span></span>
- <span data-ttu-id="21c94-145">InvalidOperation</span><span class="sxs-lookup"><span data-stu-id="21c94-145">InvalidOperation</span></span>
- <span data-ttu-id="21c94-146">Invalidresult</span><span class="sxs-lookup"><span data-stu-id="21c94-146">InvalidResult</span></span>
- <span data-ttu-id="21c94-147">Invalidtype</span><span class="sxs-lookup"><span data-stu-id="21c94-147">InvalidType</span></span>
- <span data-ttu-id="21c94-148">MetadataError</span><span class="sxs-lookup"><span data-stu-id="21c94-148">MetadataError</span></span>
- <span data-ttu-id="21c94-149">NotImplemented</span><span class="sxs-lookup"><span data-stu-id="21c94-149">NotImplemented</span></span>
- <span data-ttu-id="21c94-150">Notinstalliert</span><span class="sxs-lookup"><span data-stu-id="21c94-150">NotInstalled</span></span>
- <span data-ttu-id="21c94-151">ObjectNotFound</span><span class="sxs-lookup"><span data-stu-id="21c94-151">ObjectNotFound</span></span>
- <span data-ttu-id="21c94-152">Operationbeendet</span><span class="sxs-lookup"><span data-stu-id="21c94-152">OperationStopped</span></span>
- <span data-ttu-id="21c94-153">OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="21c94-153">OperationTimeout</span></span>
- <span data-ttu-id="21c94-154">Syntax Error</span><span class="sxs-lookup"><span data-stu-id="21c94-154">SyntaxError</span></span>
- <span data-ttu-id="21c94-155">Parser Error</span><span class="sxs-lookup"><span data-stu-id="21c94-155">ParserError</span></span>
- <span data-ttu-id="21c94-156">Permissionverweigert</span><span class="sxs-lookup"><span data-stu-id="21c94-156">PermissionDenied</span></span>
- <span data-ttu-id="21c94-157">Resourcebusy</span><span class="sxs-lookup"><span data-stu-id="21c94-157">ResourceBusy</span></span>
- <span data-ttu-id="21c94-158">Resourcevorhanden</span><span class="sxs-lookup"><span data-stu-id="21c94-158">ResourceExists</span></span>
- <span data-ttu-id="21c94-159">Resourcenicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="21c94-159">ResourceUnavailable</span></span>
- <span data-ttu-id="21c94-160">ReadError</span><span class="sxs-lookup"><span data-stu-id="21c94-160">ReadError</span></span>
- <span data-ttu-id="21c94-161">WriteError</span><span class="sxs-lookup"><span data-stu-id="21c94-161">WriteError</span></span>
- <span data-ttu-id="21c94-162">Fromstderr</span><span class="sxs-lookup"><span data-stu-id="21c94-162">FromStdErr</span></span>
- <span data-ttu-id="21c94-163">SecurityError</span><span class="sxs-lookup"><span data-stu-id="21c94-163">SecurityError</span></span>
- <span data-ttu-id="21c94-164">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="21c94-164">ProtocolError</span></span>
- <span data-ttu-id="21c94-165">Connectionerror</span><span class="sxs-lookup"><span data-stu-id="21c94-165">ConnectionError</span></span>
- <span data-ttu-id="21c94-166">AuthenticationError</span><span class="sxs-lookup"><span data-stu-id="21c94-166">AuthenticationError</span></span>
- <span data-ttu-id="21c94-167">Limits</span><span class="sxs-lookup"><span data-stu-id="21c94-167">LimitsExceeded</span></span>
- <span data-ttu-id="21c94-168">QuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="21c94-168">QuotaExceeded</span></span>
- <span data-ttu-id="21c94-169">NotEnabled</span><span class="sxs-lookup"><span data-stu-id="21c94-169">NotEnabled</span></span>

<span data-ttu-id="21c94-170">Weitere Informationen zu den Fehlerkategorien finden Sie unter [ErrorCategory-Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span><span class="sxs-lookup"><span data-stu-id="21c94-170">For information about the error categories, see [ErrorCategory Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span></span>

```yaml
Type: System.Management.Automation.ErrorCategory
Parameter Sets: NoException, WithException
Aliases:
Accepted values: NotSpecified, OpenError, CloseError, DeviceError, DeadlockDetected, InvalidArgument, InvalidData, InvalidOperation, InvalidResult, InvalidType, MetadataError, NotImplemented, NotInstalled, ObjectNotFound, OperationStopped, OperationTimeout, SyntaxError, ParserError, PermissionDenied, ResourceBusy, ResourceExists, ResourceUnavailable, ReadError, WriteError, FromStdErr, SecurityError, ProtocolError, ConnectionError, AuthenticationError, LimitsExceeded, QuotaExceeded, NotEnabled

Required: False
Position: Named
Default value: NotSpecified
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-171">-Categoryactivity</span><span class="sxs-lookup"><span data-stu-id="21c94-171">-CategoryActivity</span></span>

<span data-ttu-id="21c94-172">Gibt die Aktion an, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="21c94-172">Specifies the action that caused the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Activity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-173">-Categoryreason</span><span class="sxs-lookup"><span data-stu-id="21c94-173">-CategoryReason</span></span>

<span data-ttu-id="21c94-174">Gibt an, wie oder warum die Aktivität den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="21c94-174">Specifies how or why the activity caused the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Reason

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-175">-Categorytargetname</span><span class="sxs-lookup"><span data-stu-id="21c94-175">-CategoryTargetName</span></span>

<span data-ttu-id="21c94-176">Gibt den Namen des Objekts an, das beim Auftreten des Fehlers verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="21c94-176">Specifies the name of the object that was being processed when the error occurred.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-177">-Categorytargettype</span><span class="sxs-lookup"><span data-stu-id="21c94-177">-CategoryTargetType</span></span>

<span data-ttu-id="21c94-178">Gibt den Typ des Objekts an, das beim Auftreten des Fehlers verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="21c94-178">Specifies the type of the object that was being processed when the error occurred.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-179">-ErrorID</span><span class="sxs-lookup"><span data-stu-id="21c94-179">-ErrorId</span></span>

<span data-ttu-id="21c94-180">Gibt eine ID-Zeichenfolge zum Identifizieren des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="21c94-180">Specifies an ID string to identify the error.</span></span> <span data-ttu-id="21c94-181">Die Zeichenfolge muss für den Fehler eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="21c94-181">The string should be unique to the error.</span></span>

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-182">-ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="21c94-182">-ErrorRecord</span></span>

<span data-ttu-id="21c94-183">Gibt ein Fehlereintragsobjekt an, das den Fehler darstellt.</span><span class="sxs-lookup"><span data-stu-id="21c94-183">Specifies an error record object that represents the error.</span></span> <span data-ttu-id="21c94-184">Verwenden Sie die Eigenschaften des Objekts zur Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="21c94-184">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="21c94-185">Zum Erstellen eines Fehler Daten Satz Objekts verwenden Sie das `New-Object` Cmdlet, oder rufen Sie ein Fehler Daten Satz Objekt aus dem Array in der `$Error` automatischen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="21c94-185">To create an error record object, use the `New-Object` cmdlet or get an error record object from the array in the `$Error` automatic variable.</span></span>

```yaml
Type: System.Management.Automation.ErrorRecord
Parameter Sets: ErrorRecord
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-186">-Exception</span><span class="sxs-lookup"><span data-stu-id="21c94-186">-Exception</span></span>

<span data-ttu-id="21c94-187">Gibt ein Ausnahmeobjekt an, das den Fehler darstellt.</span><span class="sxs-lookup"><span data-stu-id="21c94-187">Specifies an exception object that represents the error.</span></span> <span data-ttu-id="21c94-188">Verwenden Sie die Eigenschaften des Objekts zur Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="21c94-188">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="21c94-189">Verwenden Sie zum Erstellen eines Ausnahme Objekts eine Hash Tabelle, oder verwenden Sie das `New-Object` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="21c94-189">To create an exception object, use a hash table or use the `New-Object` cmdlet.</span></span>

```yaml
Type: System.Exception
Parameter Sets: WithException
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-190">-Meldung</span><span class="sxs-lookup"><span data-stu-id="21c94-190">-Message</span></span>

<span data-ttu-id="21c94-191">Gibt den Meldungstext des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="21c94-191">Specifies the message text of the error.</span></span> <span data-ttu-id="21c94-192">Wenn der Text Leerzeichen oder Sonderzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="21c94-192">If the text includes spaces or special characters, enclose it in quotation marks.</span></span> <span data-ttu-id="21c94-193">Sie können eine Meldungs Zeichenfolge auch an übergeben `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="21c94-193">You can also pipe a message string to `Write-Error`.</span></span>

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases: Msg

Required: True (NoException), False (WithException)
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-194">-Empfehlungs dedaction</span><span class="sxs-lookup"><span data-stu-id="21c94-194">-RecommendedAction</span></span>

<span data-ttu-id="21c94-195">Gibt die Aktion an, die der Benutzer durchführen sollte, um den Fehler zu beheben oder zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="21c94-195">Specifies the action that the user should take to resolve or prevent the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-196">-TargetObject</span><span class="sxs-lookup"><span data-stu-id="21c94-196">-TargetObject</span></span>

<span data-ttu-id="21c94-197">Gibt das Objekt an, das beim Auftreten des Fehlers verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="21c94-197">Specifies the object that was being processed when the error occurred.</span></span> <span data-ttu-id="21c94-198">Geben Sie das-Objekt, eine Variable, die das Objekt enthält, oder einen Befehl ein, mit dem das-Objekt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="21c94-198">Enter the object, a variable that contains the object, or a command that gets the object.</span></span>

```yaml
Type: System.Object
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21c94-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="21c94-199">CommonParameters</span></span>

<span data-ttu-id="21c94-200">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="21c94-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21c94-201">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="21c94-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="21c94-202">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="21c94-202">INPUTS</span></span>

### <span data-ttu-id="21c94-203">System.String</span><span class="sxs-lookup"><span data-stu-id="21c94-203">System.String</span></span>

<span data-ttu-id="21c94-204">Sie können eine Zeichenfolge, die eine Fehlermeldung enthält, über die Pipeline an senden `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="21c94-204">You can pipe a string that contains an error message to `Write-Error`.</span></span>

## <span data-ttu-id="21c94-205">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="21c94-205">OUTPUTS</span></span>

### <span data-ttu-id="21c94-206">Error-Objekt</span><span class="sxs-lookup"><span data-stu-id="21c94-206">Error object</span></span>

<span data-ttu-id="21c94-207">`Write-Error` schreibt nur in den Fehler Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="21c94-207">`Write-Error` writes only to the error stream.</span></span> <span data-ttu-id="21c94-208">und gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="21c94-208">It does not return any objects.</span></span>

## <span data-ttu-id="21c94-209">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="21c94-209">NOTES</span></span>

<span data-ttu-id="21c94-210">`Write-Error` der Wert der `$?` automatischen Variablen wird nicht geändert, und es wird kein Abbruch Fehlerzustand signalisiert.</span><span class="sxs-lookup"><span data-stu-id="21c94-210">`Write-Error` does not change the value of the `$?` automatic variable, therefore it does not signal a terminating error condition.</span></span> <span data-ttu-id="21c94-211">Um einen Beendigungs Fehler zu signalisieren, verwenden Sie die [$PSCmdlet. Write-error ()](/dotnet/api/system.management.automation.cmdlet.writeerror) -Methode.</span><span class="sxs-lookup"><span data-stu-id="21c94-211">To signal a terminating error, use the [$PSCmdlet.WriteError()](/dotnet/api/system.management.automation.cmdlet.writeerror) method.</span></span>

## <span data-ttu-id="21c94-212">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="21c94-212">RELATED LINKS</span></span>

[<span data-ttu-id="21c94-213">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="21c94-213">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="21c94-214">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="21c94-214">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="21c94-215">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="21c94-215">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="21c94-216">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="21c94-216">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="21c94-217">Write-Host</span><span class="sxs-lookup"><span data-stu-id="21c94-217">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="21c94-218">Write-Output</span><span class="sxs-lookup"><span data-stu-id="21c94-218">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="21c94-219">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="21c94-219">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="21c94-220">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="21c94-220">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="21c94-221">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="21c94-221">Write-Warning</span></span>](Write-Warning.md)
