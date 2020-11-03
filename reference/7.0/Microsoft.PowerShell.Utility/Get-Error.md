---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: 1a8e278e03d8aea4129c172d786d285d6b55b083
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211844"
---
# <span data-ttu-id="29b0e-103">Get-Error</span><span class="sxs-lookup"><span data-stu-id="29b0e-103">Get-Error</span></span>

## <span data-ttu-id="29b0e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="29b0e-104">SYNOPSIS</span></span>

<span data-ttu-id="29b0e-105">Ruft die letzten Fehlermeldungen aus der aktuellen Sitzung ab und zeigt diese an.</span><span class="sxs-lookup"><span data-stu-id="29b0e-105">Gets and displays the most recent error messages from the current session.</span></span>

## <span data-ttu-id="29b0e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29b0e-106">SYNTAX</span></span>

### <span data-ttu-id="29b0e-107">Latest (Standard)</span><span class="sxs-lookup"><span data-stu-id="29b0e-107">Newest (Default)</span></span>

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="29b0e-108">Fehler</span><span class="sxs-lookup"><span data-stu-id="29b0e-108">Error</span></span>

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="29b0e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="29b0e-109">DESCRIPTION</span></span>

<span data-ttu-id="29b0e-110">Mit dem- `Get-Error` Cmdlet wird ein **psextendederror** -Objekt abgerufen, das die aktuellen Fehlerdetails aus dem letzten in der Sitzung aufgetretenen Fehler darstellt.</span><span class="sxs-lookup"><span data-stu-id="29b0e-110">The `Get-Error` cmdlet gets a **PSExtendedError** object that represents the current error details from the last error that occurred in the session.</span></span>

<span data-ttu-id="29b0e-111">`Get-Error`Mithilfe des **neuesten** Parameters können Sie mithilfe von eine angegebene Anzahl von Fehlern anzeigen, die in der aktuellen Sitzung aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="29b0e-111">You can use `Get-Error` to display a specified number of errors that have occurred in the current session using the **Newest** parameter.</span></span>

<span data-ttu-id="29b0e-112">Das- `Get-Error` Cmdlet empfängt auch Fehler Objekte aus einer Auflistung, z `$Error` . b., um mehrere Fehler aus der aktuellen Sitzung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="29b0e-112">The `Get-Error` cmdlet also receives error objects from a collection, such as `$Error`, to display multiple errors from the current session.</span></span>

## <span data-ttu-id="29b0e-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="29b0e-113">EXAMPLES</span></span>

### <span data-ttu-id="29b0e-114">Beispiel 1: erhalten der neuesten Fehlerdetails</span><span class="sxs-lookup"><span data-stu-id="29b0e-114">Example 1: Get the most recent error details</span></span>

<span data-ttu-id="29b0e-115">In diesem Beispiel werden `Get-Error` die Details des letzten Fehlers angezeigt, der in der aktuellen Sitzung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="29b0e-115">In this example, `Get-Error` displays the details of the most recent error that occurred in the current session.</span></span>

```powershell
Get-Childitem -path /NoRealDirectory
Get-Error
```

```
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.

Exception             :
    ErrorRecord          :
        Exception             :
            Message : Cannot find path 'C:\NoRealDirectory' because it does not exist.
            HResult : -2146233087
        TargetObject          : C:\NoRealDirectory
        CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [], ParentContainsErrorRecordException
        FullyQualifiedErrorId : PathNotFound
    ItemName             : C:\NoRealDirectory
    SessionStateCategory : Drive
    TargetSite           :
        Name          : GetChildItems
        DeclaringType : System.Management.Automation.SessionStateInternal
        MemberType    : Method
        Module        : System.Management.Automation.dll
    StackTrace           :
   at System.Management.Automation.SessionStateInternal.GetChildItems(String path, Boolean recurse, UInt32 depth,
CmdletProviderContext context)
   at System.Management.Automation.ChildItemCmdletProviderIntrinsics.Get(String path, Boolean recurse, UInt32
depth, CmdletProviderContext context)
   at Microsoft.PowerShell.Commands.GetChildItemCommand.ProcessRecord()
    Message              : Cannot find path 'C:\NoRealDirectory' because it does not exist.
    Source               : System.Management.Automation
    HResult              : -2146233087
TargetObject          : C:\NoRealDirectory
CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [Get-ChildItem], ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
InvocationInfo        :
    MyCommand        : Get-ChildItem
    ScriptLineNumber : 1
    OffsetInLine     : 1
    HistoryId        : 57
    Line             : Get-Childitem -path c:\NoRealDirectory
    PositionMessage  : At line:1 char:1
                       + Get-Childitem -path c:\NoRealDirectory
                       + ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    InvocationName   : Get-Childitem
    CommandOrigin    : Internal
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo :
```

### <span data-ttu-id="29b0e-116">Beispiel 2: erhalten der angegebenen Anzahl von Fehlermeldungen, die in der aktuellen Sitzung aufgetreten sind</span><span class="sxs-lookup"><span data-stu-id="29b0e-116">Example 2: Get the specified number of error messages that occurred in the current session</span></span>

<span data-ttu-id="29b0e-117">Dieses Beispiel zeigt, wie `Get-Error` mit dem **neuesten** Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="29b0e-117">This example shows how to use `Get-Error` with the **Newest** parameter.</span></span> <span data-ttu-id="29b0e-118">In diesem Beispiel gibt **Latest** die Details zu den drei neuesten Fehlern zurück, die in dieser Sitzung aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="29b0e-118">In this example, **Newest** returns the details of the 3 newest errors that occurred in this session.</span></span>

```powershell
Get-Error -Newest 3
```

### <span data-ttu-id="29b0e-119">Beispiel 3: Senden einer Auflistung von Fehlern, um ausführliche Meldungen zu empfangen</span><span class="sxs-lookup"><span data-stu-id="29b0e-119">Example 3: Send a collection of errors to receive detailed messages</span></span>

<span data-ttu-id="29b0e-120">Die `$Error` Automatische Variable enthält ein Array von Fehler Objekten in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="29b0e-120">The `$Error` automatic variable contains an array of error objects in the current session.</span></span> <span data-ttu-id="29b0e-121">Das Array von-Objekten kann an weitergeleitet werden `Get-Error` , um ausführliche Fehlermeldungen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="29b0e-121">The array of objects can be piped to `Get-Error` to receive detailed error messages.</span></span>

<span data-ttu-id="29b0e-122">In diesem Beispiel `$Error` wird an das `Get-Error` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="29b0e-122">In this example, `$Error` is piped to the `Get-Error` cmdlet.</span></span> <span data-ttu-id="29b0e-123">Das Ergebnis ist eine Liste detaillierter Fehlermeldungen, ähnlich wie im Ergebnis 1.</span><span class="sxs-lookup"><span data-stu-id="29b0e-123">the result is list of detailed error messages, similar to the result of Example 1.</span></span>

```powershell
$Error | Get-Error
```

## <span data-ttu-id="29b0e-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29b0e-124">PARAMETERS</span></span>

### <span data-ttu-id="29b0e-125">-Latest</span><span class="sxs-lookup"><span data-stu-id="29b0e-125">-Newest</span></span>

<span data-ttu-id="29b0e-126">Gibt die Anzahl der anzuzeigenden Fehler an, die in der aktuellen Sitzung aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="29b0e-126">Specifies the number of errors to display that have occurred in the current session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Newest
Aliases: Last

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29b0e-127">-InputObject</span><span class="sxs-lookup"><span data-stu-id="29b0e-127">-InputObject</span></span>

<span data-ttu-id="29b0e-128">Dieser Parameter wird für Pipeline Eingaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="29b0e-128">This parameter is used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Error
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="29b0e-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="29b0e-129">CommonParameters</span></span>

<span data-ttu-id="29b0e-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="29b0e-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="29b0e-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="29b0e-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="29b0e-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="29b0e-132">INPUTS</span></span>

### <span data-ttu-id="29b0e-133">PSObject</span><span class="sxs-lookup"><span data-stu-id="29b0e-133">PSObject</span></span>

<span data-ttu-id="29b0e-134">Unterstützt Eingaben aus beliebigen **psobject** , aber die Ergebnisse variieren, es sei denn, es wird ein **ErrorRecord** -oder **Exception** -Objekt bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="29b0e-134">Supports input from any **PSObject** , but results vary unless either an **ErrorRecord** or **Exception** object are supplied.</span></span>

## <span data-ttu-id="29b0e-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="29b0e-135">OUTPUTS</span></span>

### <span data-ttu-id="29b0e-136">System. Management. Automation. ErrorRecord # psextendecoderror</span><span class="sxs-lookup"><span data-stu-id="29b0e-136">System.Management.Automation.ErrorRecord#PSExtendedError</span></span>

<span data-ttu-id="29b0e-137">Ausgabe in einem **psextendederror** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="29b0e-137">Output in a **PSExtendedError** object.</span></span>

## <span data-ttu-id="29b0e-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="29b0e-138">NOTES</span></span>

<span data-ttu-id="29b0e-139">`Get-Error` akzeptiert Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="29b0e-139">`Get-Error` accepts pipeline input.</span></span> <span data-ttu-id="29b0e-140">Beispiel: `$Error | Get-Error`.</span><span class="sxs-lookup"><span data-stu-id="29b0e-140">For example, `$Error | Get-Error`.</span></span>

## <span data-ttu-id="29b0e-141">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="29b0e-141">RELATED LINKS</span></span>

[<span data-ttu-id="29b0e-142">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="29b0e-142">about_Try_Catch_Finally</span></span>](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)
