---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-error?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Error
ms.openlocfilehash: d5f7002eea35924117753d0f73b40e9d9243c64e
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224231"
---
# <span data-ttu-id="fba62-103">Write-Error</span><span class="sxs-lookup"><span data-stu-id="fba62-103">Write-Error</span></span>

## <span data-ttu-id="fba62-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fba62-104">SYNOPSIS</span></span>
<span data-ttu-id="fba62-105">Schreibt ein Objekt in den Fehlerdatenstrom.</span><span class="sxs-lookup"><span data-stu-id="fba62-105">Writes an object to the error stream.</span></span>

## <span data-ttu-id="fba62-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fba62-106">SYNTAX</span></span>

### <span data-ttu-id="fba62-107">Noexception (Standard)</span><span class="sxs-lookup"><span data-stu-id="fba62-107">NoException (Default)</span></span>

```
Write-Error [-Message] <String> [-Category <ErrorCategory>] [-ErrorId <String>] [-TargetObject <Object>]
 [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="fba62-108">Withexception</span><span class="sxs-lookup"><span data-stu-id="fba62-108">WithException</span></span>

```
Write-Error -Exception <Exception> [-Message <String>] [-Category <ErrorCategory>] [-ErrorId <String>]
 [-TargetObject <Object>] [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="fba62-109">ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="fba62-109">ErrorRecord</span></span>

```
Write-Error -ErrorRecord <ErrorRecord> [-RecommendedAction <String>] [-CategoryActivity <String>]
 [-CategoryReason <String>] [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

## <span data-ttu-id="fba62-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fba62-110">DESCRIPTION</span></span>

<span data-ttu-id="fba62-111">Mit dem `Write-Error` -Cmdlet wird ein Fehler ohne Abbruch deklariert.</span><span class="sxs-lookup"><span data-stu-id="fba62-111">The `Write-Error` cmdlet declares a non-terminating error.</span></span> <span data-ttu-id="fba62-112">Standardmäßig werden Fehler im Fehlerdatenstrom an das Hostprogramm gesendet und zusammen mit der Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fba62-112">By default, errors are sent in the error stream to the host program to be displayed, along with output.</span></span>

<span data-ttu-id="fba62-113">Um einen Fehler ohne Abbruch zu schreiben, geben Sie eine Fehlermeldungs-Zeichenfolge, ein **ErrorRecord** -Objekt oder ein **Exception** -Objekt ein.</span><span class="sxs-lookup"><span data-stu-id="fba62-113">To write a non-terminating error, enter an error message string, an **ErrorRecord** object, or an **Exception** object.</span></span> <span data-ttu-id="fba62-114">Verwenden Sie die anderen Parameter von `Write-Error` , um den Fehler Daten Satz aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="fba62-114">Use the other parameters of `Write-Error` to populate the error record.</span></span>

<span data-ttu-id="fba62-115">Fehler ohne Abbruch schreiben einen Fehler in den Fehlerdatenstrom, ohne die Befehlsverarbeitung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="fba62-115">Non-terminating errors write an error to the error stream, but they do not stop command processing.</span></span>
<span data-ttu-id="fba62-116">Wenn ein Fehler ohne Abbruch für ein einzelnes Element in einer Auflistung von Eingabeelementen deklariert wird, verarbeitet der Befehl weiterhin die anderen Elemente in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fba62-116">If a non-terminating error is declared on one item in a collection of input items, the command continues to process the other items in the collection.</span></span>

<span data-ttu-id="fba62-117">Verwenden Sie das-Schlüsselwort, um einen Abbruch Fehler zu deklarieren `Throw` .</span><span class="sxs-lookup"><span data-stu-id="fba62-117">To declare a terminating error, use the `Throw` keyword.</span></span>
<span data-ttu-id="fba62-118">Weitere Informationen finden Sie unter [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span><span class="sxs-lookup"><span data-stu-id="fba62-118">For more information, see [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span></span>

## <span data-ttu-id="fba62-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fba62-119">EXAMPLES</span></span>

### <span data-ttu-id="fba62-120">Beispiel 1: Schreiben eines Fehlers für das RegistryKey-Objekt</span><span class="sxs-lookup"><span data-stu-id="fba62-120">Example 1: Write an error for RegistryKey object</span></span>

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

<span data-ttu-id="fba62-121">Mit diesem Befehl wird ein Fehler ohne Abbruch deklariert, wenn das `Get-ChildItem` Cmdlet ein-Objekt zurückgibt `Microsoft.Win32.RegistryKey` , wie z. b. die Objekte in den- `HKLM:` oder- `HKCU:` Laufwerken des PowerShell-Registrierungs Anbieters.</span><span class="sxs-lookup"><span data-stu-id="fba62-121">This command declares a non-terminating error when the `Get-ChildItem` cmdlet returns a `Microsoft.Win32.RegistryKey` object, such as the objects in the `HKLM:` or `HKCU:` drives of the PowerShell Registry provider.</span></span>

### <span data-ttu-id="fba62-122">Beispiel 2: Schreiben einer Fehlermeldung in die Konsole</span><span class="sxs-lookup"><span data-stu-id="fba62-122">Example 2: Write an error message to the console</span></span>

```powershell
Write-Error "Access denied."
```

<span data-ttu-id="fba62-123">Mit diesem Befehl wird ein Fehler ohne Abbruch deklariert und ein Fehler des Typs „Zugriff verweigert“ geschrieben.</span><span class="sxs-lookup"><span data-stu-id="fba62-123">This command declares a non-terminating error and writes an "Access denied" error.</span></span> <span data-ttu-id="fba62-124">Der Befehl verwendet den **Message** -Parameter zur Angabe der Meldung, lässt jedoch den optionalen **Message** -Parameternamen aus.</span><span class="sxs-lookup"><span data-stu-id="fba62-124">The command uses the **Message** parameter to specify the message, but omits the optional **Message** parameter name.</span></span>

### <span data-ttu-id="fba62-125">Beispiel 3: Schreiben eines Fehlers in die Konsole und angeben der Kategorie</span><span class="sxs-lookup"><span data-stu-id="fba62-125">Example 3: Write an error to the console and specify the category</span></span>

```powershell
Write-Error -Message "Error: Too many input values." -Category InvalidArgument
```

<span data-ttu-id="fba62-126">Mit diesem Befehl wird ein Fehler ohne Abbruch deklariert und eine Fehlerkategorie angegeben.</span><span class="sxs-lookup"><span data-stu-id="fba62-126">This command declares a non-terminating error and specifies an error category.</span></span>

### <span data-ttu-id="fba62-127">Beispiel 4: Schreiben eines Fehlers mit einem Exception-Objekt</span><span class="sxs-lookup"><span data-stu-id="fba62-127">Example 4: Write an error using an Exception object</span></span>

```powershell
$E = [System.Exception]@{Source="Get-ParameterNames.ps1";HelpLink="https://go.microsoft.com/fwlink/?LinkID=113425"}
Write-Error -Exception $E -Message "Files not found. The $Files location does not contain any XML files."
```

<span data-ttu-id="fba62-128">Dieser Befehl verwendet ein **Exception** -Objekt, um einen Fehler ohne Abbruch zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="fba62-128">This command uses an **Exception** object to declare a non-terminating error.</span></span>

<span data-ttu-id="fba62-129">Der erste Befehl verwendet eine Hashtabelle zum Erstellen des **System.Exception** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="fba62-129">The first command uses a hash table to create the **System.Exception** object.</span></span> <span data-ttu-id="fba62-130">Das Ausnahme Objekt wird in der `$E` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fba62-130">It saves the exception object in the `$E` variable.</span></span> <span data-ttu-id="fba62-131">Mithilfe einer Hashtabelle können Sie ein beliebiges Objekt eines Typs erstellen, der über einen NULL-Konstruktor verfügt.</span><span class="sxs-lookup"><span data-stu-id="fba62-131">You can use a hash table to create any object of a type that has a null constructor.</span></span>

<span data-ttu-id="fba62-132">Der zweite Befehl verwendet das `Write-Error` Cmdlet, um einen Fehler ohne Abbruch zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="fba62-132">The second command uses the `Write-Error` cmdlet to declare a non-terminating error.</span></span> <span data-ttu-id="fba62-133">Der Wert des **Exception** -Parameters ist das **Exception** -Objekt in der `$E` Variablen.</span><span class="sxs-lookup"><span data-stu-id="fba62-133">The value of the **Exception** parameter is the **Exception** object in the `$E` variable.</span></span>

## <span data-ttu-id="fba62-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fba62-134">PARAMETERS</span></span>

### <span data-ttu-id="fba62-135">-Kategorie</span><span class="sxs-lookup"><span data-stu-id="fba62-135">-Category</span></span>

<span data-ttu-id="fba62-136">Gibt die Kategorie des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="fba62-136">Specifies the category of the error.</span></span> <span data-ttu-id="fba62-137">Der Standardwert ist " **notangegeben** ".</span><span class="sxs-lookup"><span data-stu-id="fba62-137">The default value is **NotSpecified**.</span></span> <span data-ttu-id="fba62-138">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="fba62-138">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fba62-139">NotSpecified</span><span class="sxs-lookup"><span data-stu-id="fba62-139">NotSpecified</span></span>
- <span data-ttu-id="fba62-140">OpenError</span><span class="sxs-lookup"><span data-stu-id="fba62-140">OpenError</span></span>
- <span data-ttu-id="fba62-141">Closeerror</span><span class="sxs-lookup"><span data-stu-id="fba62-141">CloseError</span></span>
- <span data-ttu-id="fba62-142">Deviceerror</span><span class="sxs-lookup"><span data-stu-id="fba62-142">DeviceError</span></span>
- <span data-ttu-id="fba62-143">Deadlockerkannt</span><span class="sxs-lookup"><span data-stu-id="fba62-143">DeadlockDetected</span></span>
- <span data-ttu-id="fba62-144">Invalidargument</span><span class="sxs-lookup"><span data-stu-id="fba62-144">InvalidArgument</span></span>
- <span data-ttu-id="fba62-145">InvalidData</span><span class="sxs-lookup"><span data-stu-id="fba62-145">InvalidData</span></span>
- <span data-ttu-id="fba62-146">InvalidOperation</span><span class="sxs-lookup"><span data-stu-id="fba62-146">InvalidOperation</span></span>
- <span data-ttu-id="fba62-147">Invalidresult</span><span class="sxs-lookup"><span data-stu-id="fba62-147">InvalidResult</span></span>
- <span data-ttu-id="fba62-148">Invalidtype</span><span class="sxs-lookup"><span data-stu-id="fba62-148">InvalidType</span></span>
- <span data-ttu-id="fba62-149">MetadataError</span><span class="sxs-lookup"><span data-stu-id="fba62-149">MetadataError</span></span>
- <span data-ttu-id="fba62-150">NotImplemented</span><span class="sxs-lookup"><span data-stu-id="fba62-150">NotImplemented</span></span>
- <span data-ttu-id="fba62-151">Notinstalliert</span><span class="sxs-lookup"><span data-stu-id="fba62-151">NotInstalled</span></span>
- <span data-ttu-id="fba62-152">ObjectNotFound</span><span class="sxs-lookup"><span data-stu-id="fba62-152">ObjectNotFound</span></span>
- <span data-ttu-id="fba62-153">Operationbeendet</span><span class="sxs-lookup"><span data-stu-id="fba62-153">OperationStopped</span></span>
- <span data-ttu-id="fba62-154">OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="fba62-154">OperationTimeout</span></span>
- <span data-ttu-id="fba62-155">Syntax Error</span><span class="sxs-lookup"><span data-stu-id="fba62-155">SyntaxError</span></span>
- <span data-ttu-id="fba62-156">Parser Error</span><span class="sxs-lookup"><span data-stu-id="fba62-156">ParserError</span></span>
- <span data-ttu-id="fba62-157">Permissionverweigert</span><span class="sxs-lookup"><span data-stu-id="fba62-157">PermissionDenied</span></span>
- <span data-ttu-id="fba62-158">Resourcebusy</span><span class="sxs-lookup"><span data-stu-id="fba62-158">ResourceBusy</span></span>
- <span data-ttu-id="fba62-159">Resourcevorhanden</span><span class="sxs-lookup"><span data-stu-id="fba62-159">ResourceExists</span></span>
- <span data-ttu-id="fba62-160">Resourcenicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="fba62-160">ResourceUnavailable</span></span>
- <span data-ttu-id="fba62-161">ReadError</span><span class="sxs-lookup"><span data-stu-id="fba62-161">ReadError</span></span>
- <span data-ttu-id="fba62-162">WriteError</span><span class="sxs-lookup"><span data-stu-id="fba62-162">WriteError</span></span>
- <span data-ttu-id="fba62-163">Fromstderr</span><span class="sxs-lookup"><span data-stu-id="fba62-163">FromStdErr</span></span>
- <span data-ttu-id="fba62-164">SecurityError</span><span class="sxs-lookup"><span data-stu-id="fba62-164">SecurityError</span></span>
- <span data-ttu-id="fba62-165">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="fba62-165">ProtocolError</span></span>
- <span data-ttu-id="fba62-166">Connectionerror</span><span class="sxs-lookup"><span data-stu-id="fba62-166">ConnectionError</span></span>
- <span data-ttu-id="fba62-167">AuthenticationError</span><span class="sxs-lookup"><span data-stu-id="fba62-167">AuthenticationError</span></span>
- <span data-ttu-id="fba62-168">Limits</span><span class="sxs-lookup"><span data-stu-id="fba62-168">LimitsExceeded</span></span>
- <span data-ttu-id="fba62-169">QuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="fba62-169">QuotaExceeded</span></span>
- <span data-ttu-id="fba62-170">NotEnabled</span><span class="sxs-lookup"><span data-stu-id="fba62-170">NotEnabled</span></span>

<span data-ttu-id="fba62-171">Weitere Informationen zu den Fehlerkategorien finden Sie unter [ErrorCategory-Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span><span class="sxs-lookup"><span data-stu-id="fba62-171">For information about the error categories, see [ErrorCategory Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span></span>

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

### <span data-ttu-id="fba62-172">-Categoryactivity</span><span class="sxs-lookup"><span data-stu-id="fba62-172">-CategoryActivity</span></span>

<span data-ttu-id="fba62-173">Gibt die Aktion an, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="fba62-173">Specifies the action that caused the error.</span></span>

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

### <span data-ttu-id="fba62-174">-Categoryreason</span><span class="sxs-lookup"><span data-stu-id="fba62-174">-CategoryReason</span></span>

<span data-ttu-id="fba62-175">Gibt an, wie oder warum die Aktivität den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="fba62-175">Specifies how or why the activity caused the error.</span></span>

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

### <span data-ttu-id="fba62-176">-Categorytargetname</span><span class="sxs-lookup"><span data-stu-id="fba62-176">-CategoryTargetName</span></span>

<span data-ttu-id="fba62-177">Gibt den Namen des Objekts an, das beim Auftreten des Fehlers verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="fba62-177">Specifies the name of the object that was being processed when the error occurred.</span></span>

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

### <span data-ttu-id="fba62-178">-Categorytargettype</span><span class="sxs-lookup"><span data-stu-id="fba62-178">-CategoryTargetType</span></span>

<span data-ttu-id="fba62-179">Gibt den Typ des Objekts an, das beim Auftreten des Fehlers verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="fba62-179">Specifies the type of the object that was being processed when the error occurred.</span></span>

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

### <span data-ttu-id="fba62-180">-ErrorID</span><span class="sxs-lookup"><span data-stu-id="fba62-180">-ErrorId</span></span>

<span data-ttu-id="fba62-181">Gibt eine ID-Zeichenfolge zum Identifizieren des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="fba62-181">Specifies an ID string to identify the error.</span></span> <span data-ttu-id="fba62-182">Die Zeichenfolge muss für den Fehler eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="fba62-182">The string should be unique to the error.</span></span>

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

### <span data-ttu-id="fba62-183">-ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="fba62-183">-ErrorRecord</span></span>

<span data-ttu-id="fba62-184">Gibt ein Fehlereintragsobjekt an, das den Fehler darstellt.</span><span class="sxs-lookup"><span data-stu-id="fba62-184">Specifies an error record object that represents the error.</span></span> <span data-ttu-id="fba62-185">Verwenden Sie die Eigenschaften des Objekts zur Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="fba62-185">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="fba62-186">Zum Erstellen eines Fehler Daten Satz Objekts verwenden Sie das `New-Object` Cmdlet, oder rufen Sie ein Fehler Daten Satz Objekt aus dem Array in der `$Error` automatischen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="fba62-186">To create an error record object, use the `New-Object` cmdlet or get an error record object from the array in the `$Error` automatic variable.</span></span>

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

### <span data-ttu-id="fba62-187">-Exception</span><span class="sxs-lookup"><span data-stu-id="fba62-187">-Exception</span></span>

<span data-ttu-id="fba62-188">Gibt ein Ausnahmeobjekt an, das den Fehler darstellt.</span><span class="sxs-lookup"><span data-stu-id="fba62-188">Specifies an exception object that represents the error.</span></span> <span data-ttu-id="fba62-189">Verwenden Sie die Eigenschaften des Objekts zur Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="fba62-189">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="fba62-190">Verwenden Sie zum Erstellen eines Ausnahme Objekts eine Hash Tabelle, oder verwenden Sie das `New-Object` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fba62-190">To create an exception object, use a hash table or use the `New-Object` cmdlet.</span></span>

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

### <span data-ttu-id="fba62-191">-Meldung</span><span class="sxs-lookup"><span data-stu-id="fba62-191">-Message</span></span>

<span data-ttu-id="fba62-192">Gibt den Meldungstext des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="fba62-192">Specifies the message text of the error.</span></span> <span data-ttu-id="fba62-193">Wenn der Text Leerzeichen oder Sonderzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="fba62-193">If the text includes spaces or special characters, enclose it in quotation marks.</span></span> <span data-ttu-id="fba62-194">Sie können eine Meldungs Zeichenfolge auch an übergeben `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="fba62-194">You can also pipe a message string to `Write-Error`.</span></span>

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

### <span data-ttu-id="fba62-195">-Empfehlungs dedaction</span><span class="sxs-lookup"><span data-stu-id="fba62-195">-RecommendedAction</span></span>

<span data-ttu-id="fba62-196">Gibt die Aktion an, die der Benutzer durchführen sollte, um den Fehler zu beheben oder zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="fba62-196">Specifies the action that the user should take to resolve or prevent the error.</span></span>

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

### <span data-ttu-id="fba62-197">-TargetObject</span><span class="sxs-lookup"><span data-stu-id="fba62-197">-TargetObject</span></span>

<span data-ttu-id="fba62-198">Gibt das Objekt an, das beim Auftreten des Fehlers verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="fba62-198">Specifies the object that was being processed when the error occurred.</span></span> <span data-ttu-id="fba62-199">Geben Sie das-Objekt, eine Variable, die das Objekt enthält, oder einen Befehl ein, mit dem das-Objekt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fba62-199">Enter the object, a variable that contains the object, or a command that gets the object.</span></span>

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

### <span data-ttu-id="fba62-200">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fba62-200">CommonParameters</span></span>

<span data-ttu-id="fba62-201">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fba62-201">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fba62-202">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fba62-202">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fba62-203">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fba62-203">INPUTS</span></span>

### <span data-ttu-id="fba62-204">System.String</span><span class="sxs-lookup"><span data-stu-id="fba62-204">System.String</span></span>

<span data-ttu-id="fba62-205">Sie können eine Zeichenfolge, die eine Fehlermeldung enthält, über die Pipeline an senden `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="fba62-205">You can pipe a string that contains an error message to `Write-Error`.</span></span>

## <span data-ttu-id="fba62-206">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fba62-206">OUTPUTS</span></span>

### <span data-ttu-id="fba62-207">Error-Objekt</span><span class="sxs-lookup"><span data-stu-id="fba62-207">Error object</span></span>

<span data-ttu-id="fba62-208">`Write-Error` schreibt nur in den Fehler Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="fba62-208">`Write-Error` writes only to the error stream.</span></span> <span data-ttu-id="fba62-209">und gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="fba62-209">It does not return any objects.</span></span>

## <span data-ttu-id="fba62-210">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fba62-210">NOTES</span></span>

<span data-ttu-id="fba62-211">`Write-Error` der Wert der `$?` automatischen Variablen wird nicht geändert, und es wird kein Abbruch Fehlerzustand signalisiert.</span><span class="sxs-lookup"><span data-stu-id="fba62-211">`Write-Error` does not change the value of the `$?` automatic variable, therefore it does not signal a terminating error condition.</span></span> <span data-ttu-id="fba62-212">Um einen Beendigungs Fehler zu signalisieren, verwenden Sie die [$PSCmdlet. Write-error ()](/dotnet/api/system.management.automation.cmdlet.writeerror) -Methode.</span><span class="sxs-lookup"><span data-stu-id="fba62-212">To signal a terminating error, use the [$PSCmdlet.WriteError()](/dotnet/api/system.management.automation.cmdlet.writeerror) method.</span></span>

## <span data-ttu-id="fba62-213">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fba62-213">RELATED LINKS</span></span>

[<span data-ttu-id="fba62-214">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="fba62-214">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="fba62-215">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="fba62-215">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="fba62-216">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="fba62-216">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="fba62-217">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="fba62-217">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="fba62-218">Write-Host</span><span class="sxs-lookup"><span data-stu-id="fba62-218">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="fba62-219">Write-Output</span><span class="sxs-lookup"><span data-stu-id="fba62-219">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="fba62-220">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="fba62-220">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="fba62-221">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="fba62-221">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="fba62-222">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="fba62-222">Write-Warning</span></span>](Write-Warning.md)
