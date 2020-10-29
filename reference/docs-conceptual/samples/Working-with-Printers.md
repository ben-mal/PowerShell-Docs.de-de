---
ms.date: 12/23/2019
keywords: powershell,cmdlet
title: Arbeiten mit Druckern
description: In diesem Artikel wird die Verwaltung von Druckern unter Windows mithilfe von WMI-Objekten und COM-Schnittstellen gezeigt.
ms.openlocfilehash: 2606753783043eeae8e9d461e56f0901149cb8e3
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501081"
---
# <a name="working-with-printers-in-windows"></a><span data-ttu-id="0c91b-104">Arbeiten mit Druckern in Windows</span><span class="sxs-lookup"><span data-stu-id="0c91b-104">Working with Printers in Windows</span></span>

<span data-ttu-id="0c91b-105">Sie können Windows PowerShell zum Verwalten von Druckern mit WMI und dem COM-Objekt **WScript.Network** vom WSH verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c91b-105">You can use PowerShell to manage printers by using WMI and the **WScript.Network** COM object from WSH.</span></span> <span data-ttu-id="0c91b-106">Wir werden eine Kombination beider Tools verwenden, um bestimmte Aufgaben zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="0c91b-106">We will use a mix of both tools to demonstrate specific tasks.</span></span>

## <a name="listing-printer-connections"></a><span data-ttu-id="0c91b-107">Auflisten von Druckerverbindungen</span><span class="sxs-lookup"><span data-stu-id="0c91b-107">Listing Printer Connections</span></span>

<span data-ttu-id="0c91b-108">Die einfachste Möglichkeit, die auf einem Computer installierten Drucker aufzulisten, ist die Verwendung der WMI-Klasse **Win32_Printer** :</span><span class="sxs-lookup"><span data-stu-id="0c91b-108">The simplest way to list the printers installed on a computer is to use the WMI **Win32_Printer** class:</span></span>

```powershell
Get-CimInstance -Class Win32_Printer
```

<span data-ttu-id="0c91b-109">Sie können die Drucker auch mit dem COM-Objekt **WScript.Network** auflisten, das normalerweise in WSH-Skripts verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="0c91b-109">You can also list the printers by using the **WScript.Network** COM object that is typically used in WSH scripts:</span></span>

```powershell
(New-Object -ComObject WScript.Network).EnumPrinterConnections()
```

<span data-ttu-id="0c91b-110">Da dieser Befehl eine einfache Zeichenfolgenauflistung von Portnamen und Druckergerätenamen ohne unterscheidende Bezeichnungen zurückgibt, ist die Ausgabe nicht leicht zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="0c91b-110">Because this command returns a simple string collection of port names and printer device names without any distinguishing labels, it is not easy to interpret.</span></span>

## <a name="adding-a-network-printer"></a><span data-ttu-id="0c91b-111">Hinzufügen eines Netzwerkdruckers</span><span class="sxs-lookup"><span data-stu-id="0c91b-111">Adding a Network Printer</span></span>

<span data-ttu-id="0c91b-112">Verwenden Sie zum Hinzufügen eines neuen Netzwerkdruckers **WScript.Network** :</span><span class="sxs-lookup"><span data-stu-id="0c91b-112">To add a new network printer, use **WScript.Network** :</span></span>

```powershell
(New-Object -ComObject WScript.Network).AddWindowsPrinterConnection("\\Printserver01\Xerox5")
```

## <a name="setting-a-default-printer"></a><span data-ttu-id="0c91b-113">Festlegen eines Standarddruckers</span><span class="sxs-lookup"><span data-stu-id="0c91b-113">Setting a Default Printer</span></span>

<span data-ttu-id="0c91b-114">Um mithilfe von WMI den Standarddrucker festzulegen, suchen Sie den Drucker in der **Win32_Printer** -Sammlung, und rufen Sie dann die Methode **SetDefaultPrinter** auf:</span><span class="sxs-lookup"><span data-stu-id="0c91b-114">To use WMI to set the default printer, find the printer in the **Win32_Printer** collection and then invoke the **SetDefaultPrinter** method:</span></span>

```powershell
$printer = Get-CimInstance -Class Win32_Printer -Filter "Name='HP LaserJet 5Si'"
Invoke-CimMethod -InputObject $printer -MethodName SetDefaultPrinter
```

<span data-ttu-id="0c91b-115">**WScript.Network** ist etwas einfacher zu verwenden, da es eine **SetDefaultPrinter** -Methode besitzt, die nur den Druckernamen als Argument akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="0c91b-115">**WScript.Network** is a little simpler to use, because it has a **SetDefaultPrinter** method that takes only the printer name as an argument:</span></span>

```powershell
(New-Object -ComObject WScript.Network).SetDefaultPrinter('HP LaserJet 5Si')
```

## <a name="removing-a-printer-connection"></a><span data-ttu-id="0c91b-116">Entfernen einer Druckerverbindung</span><span class="sxs-lookup"><span data-stu-id="0c91b-116">Removing a Printer Connection</span></span>

<span data-ttu-id="0c91b-117">Um eine Druckerverbindung zu entfernen, verwenden Sie die Methode **WScript.Network RemovePrinterConnection** :</span><span class="sxs-lookup"><span data-stu-id="0c91b-117">To remove a printer connection, use the **WScript.Network RemovePrinterConnection** method:</span></span>

```powershell
(New-Object -ComObject WScript.Network).RemovePrinterConnection("\\Printserver01\Xerox5")
```
