---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: 7e4f4adf60a4f6386c646d92ada0003f239f05f4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600296"
---
# <span data-ttu-id="cd783-102">Get-Error</span><span class="sxs-lookup"><span data-stu-id="cd783-102">Get-Error</span></span>

## <span data-ttu-id="cd783-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="cd783-103">SYNOPSIS</span></span>

<span data-ttu-id="cd783-104">Ruft die letzten Fehlermeldungen aus der aktuellen Sitzung ab und zeigt diese an.</span><span class="sxs-lookup"><span data-stu-id="cd783-104">Gets and displays the most recent error messages from the current session.</span></span>

## <span data-ttu-id="cd783-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cd783-105">SYNTAX</span></span>

### <span data-ttu-id="cd783-106">Latest (Standard)</span><span class="sxs-lookup"><span data-stu-id="cd783-106">Newest (Default)</span></span>

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="cd783-107">Fehler</span><span class="sxs-lookup"><span data-stu-id="cd783-107">Error</span></span>

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="cd783-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cd783-108">DESCRIPTION</span></span>

<span data-ttu-id="cd783-109">Mit dem- `Get-Error` Cmdlet wird ein **psextendederror** -Objekt abgerufen, das die aktuellen Fehlerdetails aus dem letzten in der Sitzung aufgetretenen Fehler darstellt.</span><span class="sxs-lookup"><span data-stu-id="cd783-109">The `Get-Error` cmdlet gets a **PSExtendedError** object that represents the current error details from the last error that occurred in the session.</span></span>

<span data-ttu-id="cd783-110">`Get-Error`Mithilfe des **neuesten** Parameters können Sie mithilfe von eine angegebene Anzahl von Fehlern anzeigen, die in der aktuellen Sitzung aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="cd783-110">You can use `Get-Error` to display a specified number of errors that have occurred in the current session using the **Newest** parameter.</span></span>

<span data-ttu-id="cd783-111">Das- `Get-Error` Cmdlet empfängt auch Fehler Objekte aus einer Auflistung, z `$Error` . b., um mehrere Fehler aus der aktuellen Sitzung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd783-111">The `Get-Error` cmdlet also receives error objects from a collection, such as `$Error`, to display multiple errors from the current session.</span></span>

## <span data-ttu-id="cd783-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="cd783-112">EXAMPLES</span></span>

### <span data-ttu-id="cd783-113">Beispiel 1: erhalten der neuesten Fehlerdetails</span><span class="sxs-lookup"><span data-stu-id="cd783-113">Example 1: Get the most recent error details</span></span>

<span data-ttu-id="cd783-114">In diesem Beispiel werden `Get-Error` die Details des letzten Fehlers angezeigt, der in der aktuellen Sitzung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cd783-114">In this example, `Get-Error` displays the details of the most recent error that occurred in the current session.</span></span>

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

### <span data-ttu-id="cd783-115">Beispiel 2: erhalten der angegebenen Anzahl von Fehlermeldungen, die in der aktuellen Sitzung aufgetreten sind</span><span class="sxs-lookup"><span data-stu-id="cd783-115">Example 2: Get the specified number of error messages that occurred in the current session</span></span>

<span data-ttu-id="cd783-116">Dieses Beispiel zeigt, wie `Get-Error` mit dem **neuesten** Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd783-116">This example shows how to use `Get-Error` with the **Newest** parameter.</span></span> <span data-ttu-id="cd783-117">In diesem Beispiel gibt **Latest** die Details zu den drei neuesten Fehlern zurück, die in dieser Sitzung aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="cd783-117">In this example, **Newest** returns the details of the 3 newest errors that occurred in this session.</span></span>

```powershell
Get-Error -Newest 3
```

### <span data-ttu-id="cd783-118">Beispiel 3: Senden einer Auflistung von Fehlern, um ausführliche Meldungen zu empfangen</span><span class="sxs-lookup"><span data-stu-id="cd783-118">Example 3: Send a collection of errors to receive detailed messages</span></span>

<span data-ttu-id="cd783-119">Die `$Error` Automatische Variable enthält ein Array von Fehler Objekten in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cd783-119">The `$Error` automatic variable contains an array of error objects in the current session.</span></span> <span data-ttu-id="cd783-120">Das Array von-Objekten kann an weitergeleitet werden `Get-Error` , um ausführliche Fehlermeldungen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="cd783-120">The array of objects can be piped to `Get-Error` to receive detailed error messages.</span></span>

<span data-ttu-id="cd783-121">In diesem Beispiel `$Error` wird an das `Get-Error` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="cd783-121">In this example, `$Error` is piped to the `Get-Error` cmdlet.</span></span> <span data-ttu-id="cd783-122">Das Ergebnis ist eine Liste detaillierter Fehlermeldungen, ähnlich wie im Ergebnis 1.</span><span class="sxs-lookup"><span data-stu-id="cd783-122">the result is list of detailed error messages, similar to the result of Example 1.</span></span>

```powershell
$Error | Get-Error
```

## <span data-ttu-id="cd783-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cd783-123">PARAMETERS</span></span>

### <span data-ttu-id="cd783-124">-Latest</span><span class="sxs-lookup"><span data-stu-id="cd783-124">-Newest</span></span>

<span data-ttu-id="cd783-125">Gibt die Anzahl der anzuzeigenden Fehler an, die in der aktuellen Sitzung aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="cd783-125">Specifies the number of errors to display that have occurred in the current session.</span></span>

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

### <span data-ttu-id="cd783-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cd783-126">-InputObject</span></span>

<span data-ttu-id="cd783-127">Dieser Parameter wird für Pipeline Eingaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd783-127">This parameter is used for pipeline input.</span></span>

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

### <span data-ttu-id="cd783-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cd783-128">CommonParameters</span></span>

<span data-ttu-id="cd783-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cd783-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cd783-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cd783-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cd783-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="cd783-131">INPUTS</span></span>

### <span data-ttu-id="cd783-132">PSObject</span><span class="sxs-lookup"><span data-stu-id="cd783-132">PSObject</span></span>

<span data-ttu-id="cd783-133">Unterstützt Eingaben aus beliebigen **psobject**, aber die Ergebnisse variieren, es sei denn, es wird ein **ErrorRecord** -oder **Exception** -Objekt bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cd783-133">Supports input from any **PSObject**, but results vary unless either an **ErrorRecord** or **Exception** object are supplied.</span></span>

## <span data-ttu-id="cd783-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="cd783-134">OUTPUTS</span></span>

### <span data-ttu-id="cd783-135">System. Management. Automation. ErrorRecord # psextendecoderror</span><span class="sxs-lookup"><span data-stu-id="cd783-135">System.Management.Automation.ErrorRecord#PSExtendedError</span></span>

<span data-ttu-id="cd783-136">Ausgabe in einem **psextendederror** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="cd783-136">Output in a **PSExtendedError** object.</span></span>

## <span data-ttu-id="cd783-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="cd783-137">NOTES</span></span>

<span data-ttu-id="cd783-138">`Get-Error` akzeptiert Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="cd783-138">`Get-Error` accepts pipeline input.</span></span> <span data-ttu-id="cd783-139">Beispiel: `$Error | Get-Error`.</span><span class="sxs-lookup"><span data-stu-id="cd783-139">For example, `$Error | Get-Error`.</span></span>

## <span data-ttu-id="cd783-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="cd783-140">RELATED LINKS</span></span>

[<span data-ttu-id="cd783-141">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="cd783-141">about_Try_Catch_Finally</span></span>](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)
