---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-default?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Default
ms.openlocfilehash: d650a9280982703e09ec22698c3848a616abb067
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597376"
---
# <span data-ttu-id="9b6a1-102">Out-Default</span><span class="sxs-lookup"><span data-stu-id="9b6a1-102">Out-Default</span></span>

## <span data-ttu-id="9b6a1-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9b6a1-103">SYNOPSIS</span></span>
<span data-ttu-id="9b6a1-104">Sendet die Ausgabe an das Standardformatierungsprogramm und das Standard-Ausgabe-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-104">Sends the output to the default formatter and to the default output cmdlet.</span></span>

## <span data-ttu-id="9b6a1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9b6a1-105">SYNTAX</span></span>

```
Out-Default [-Transcript] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="9b6a1-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b6a1-106">DESCRIPTION</span></span>

<span data-ttu-id="9b6a1-107">PowerShell wird automatisch `Out-Default` am Ende jeder Pipeline hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-107">PowerShell automatically adds `Out-Default` to the end of every pipeline.</span></span> <span data-ttu-id="9b6a1-108">`Out-Default` bestimmt, wie der Objektstream formatiert und ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-108">`Out-Default` decides how to format and output the object stream.</span></span> <span data-ttu-id="9b6a1-109">Wenn es sich bei dem Objektdaten Strom um einen Stream von Zeichen folgen handelt, werden `Out-Default` diese direkt an die Pipeline geleitet, die `Out-Host` die vom Host bereitgestellten entsprechenden APIs aufruft</span><span class="sxs-lookup"><span data-stu-id="9b6a1-109">If the object stream is a stream of strings, `Out-Default` pipes these directly to `Out-Host` which calls the appropriate APIs provided by the host.</span></span> <span data-ttu-id="9b6a1-110">Wenn der Objektstream keine Zeichen folgen enthält, wird `Out-Default` das Objekt von überprüft, um zu bestimmen, was zu tun ist.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-110">If the object stream does not contain strings, `Out-Default` inspects the object to determine what to do.</span></span>
<span data-ttu-id="9b6a1-111">Zuerst wird der Objekttyp untersucht, und es wird ermittelt, ob für diesen Objekttyp eine registrierte _Sicht_ vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-111">First it looks at the object type and determines whether there is a registered _view_ for this object type.</span></span>

<span data-ttu-id="9b6a1-112">PowerShell definiert das XML-Schema und einen Mechanismus (das `Update-FormatData` Cmdlet), in dem jeder Benutzer Sichten für einen Objekttyp registrieren kann.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-112">PowerShell defines XML schema and a mechanism (the `Update-FormatData` cmdlet) where anyone can register views for an object type.</span></span> <span data-ttu-id="9b6a1-113">Sie können für jeden Objekttyp eine **Breite**, eine **Liste**, eine **Tabelle** oder eine **benutzerdefinierte** Ansicht angeben.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-113">You can specify **wide**, **list**, **table**, or **custom** views for any object type.</span></span> <span data-ttu-id="9b6a1-114">Die Ansichten geben an, welche Eigenschaften angezeigt werden sollen und wie Sie angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-114">The views specify which properties to display and how they should be displayed.</span></span> <span data-ttu-id="9b6a1-115">Wenn eine Sicht registriert ist, definiert Sie den zu verwendenden Formatierer.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-115">If a view is registered, it defines which formatter to use.</span></span> <span data-ttu-id="9b6a1-116">Wenn die registrierte Sicht also eine **Tabellen** Ansicht ist, werden `Out-Default` die Objekte von in gestreamt `Format-Table | Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="9b6a1-116">So if the registered view is a **table** view, `Out-Default` streams the objects to `Format-Table | Out-Host`.</span></span> <span data-ttu-id="9b6a1-117">`Format-Table` Transformiert die Objekte in einen Stream von Formatierungsdaten Sätzen (gesteuert durch die Daten in der Sicht Definition) und `Out-Host` transformiert die Formatierungsdaten Sätze in Aufrufe der Host Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-117">`Format-Table` transforms the objects into a stream of Formatting records (driven by the data in the view definition) and `Out-Host` transforms the formatting records into calls on the Host interface.</span></span>

## <span data-ttu-id="9b6a1-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9b6a1-118">EXAMPLES</span></span>

### <span data-ttu-id="9b6a1-119">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="9b6a1-119">Example 1</span></span>

<span data-ttu-id="9b6a1-120">Obwohl dieses Cmdlet nicht direkt vom Endbenutzer ausgeführt werden soll, kann es sein.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-120">While this cmdlet is not intended to be run directly by the end user, it can be.</span></span>

```powershell
Get-Process | Select-Object -First 5 | Out-Default
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     12     2.56       5.20       0.00    7376   0 aesm_service
     48    34.32      18.10      26.64    9320  13 AlertusDesktopAlert
     24    13.97      12.74       0.77   12656  13 ApplicationFrameHost
      8     1.79       4.41       0.00    8180   0 AppVShNotify
      9     1.99       5.07       0.19   19320  13 AppVShNotify
```

## <span data-ttu-id="9b6a1-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9b6a1-121">PARAMETERS</span></span>

### <span data-ttu-id="9b6a1-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9b6a1-122">-InputObject</span></span>

<span data-ttu-id="9b6a1-123">Akzeptiert Eingaben für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-123">Accepts input to the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9b6a1-124">-Transkripts</span><span class="sxs-lookup"><span data-stu-id="9b6a1-124">-Transcript</span></span>

<span data-ttu-id="9b6a1-125">Bestimmt, ob die Ausgabe an die Transkriptions Dienste von PowerShell gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-125">Determines whether the output should be sent to PowerShell's transcription services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9b6a1-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9b6a1-126">CommonParameters</span></span>

<span data-ttu-id="9b6a1-127">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9b6a1-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9b6a1-128">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9b6a1-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9b6a1-129">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9b6a1-129">INPUTS</span></span>

## <span data-ttu-id="9b6a1-130">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9b6a1-130">OUTPUTS</span></span>

## <span data-ttu-id="9b6a1-131">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9b6a1-131">NOTES</span></span>

## <span data-ttu-id="9b6a1-132">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9b6a1-132">RELATED LINKS</span></span>

[<span data-ttu-id="9b6a1-133">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="9b6a1-133">Format-Custom</span></span>](../Microsoft.PowerShell.Utility/Format-Custom.md)

[<span data-ttu-id="9b6a1-134">Format-List</span><span class="sxs-lookup"><span data-stu-id="9b6a1-134">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="9b6a1-135">Format-Table</span><span class="sxs-lookup"><span data-stu-id="9b6a1-135">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="9b6a1-136">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="9b6a1-136">Format-Wide</span></span>](../Microsoft.PowerShell.Utility/Format-Wide.md)

[<span data-ttu-id="9b6a1-137">about_Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="9b6a1-137">about_Format.ps1xml</span></span>](About/about_Format.ps1xml.md)

[<span data-ttu-id="9b6a1-138">Funktionsweise von PowerShell-Formatierung und-Ausgabe</span><span class="sxs-lookup"><span data-stu-id="9b6a1-138">How PowerShell Formatting and Outputting REALLY works</span></span>](https://devblogs.microsoft.com/powershell/how-powershell-formatting-and-outputting-really-works/)

