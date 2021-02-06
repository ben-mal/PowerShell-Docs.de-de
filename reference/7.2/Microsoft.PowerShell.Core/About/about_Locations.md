---
description: Hier wird beschrieben, wie Sie über den Arbeits Speicherort in PowerShell auf Elemente zugreifen.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_locations?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Locations
ms.openlocfilehash: 4876abe3c651ad2279b85355f2e5e029203b6d4e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602928"
---
# <a name="about_locations"></a><span data-ttu-id="20831-103">about_Locations</span><span class="sxs-lookup"><span data-stu-id="20831-103">about_Locations</span></span>

## <a name="short-description"></a><span data-ttu-id="20831-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="20831-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="20831-105">Hier wird beschrieben, wie Sie über den Arbeits Speicherort in PowerShell auf Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="20831-105">Describes how to access items from the working location in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="20831-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="20831-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="20831-107">Der aktuelle Arbeits Speicherort ist der Standard Speicherort, auf den Befehle zeigen.</span><span class="sxs-lookup"><span data-stu-id="20831-107">The current working location is the default location to which commands point.</span></span>
<span data-ttu-id="20831-108">Das heißt, dass dies der Speicherort ist, den PowerShell verwendet, wenn Sie keinen expliziten Pfad zu dem Element oder Speicherort bereitstellen, das von dem Befehl betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="20831-108">In other words, this is the location that PowerShell uses if you do not supply an explicit path to the item or location that is affected by the command.</span></span> <span data-ttu-id="20831-109">In den meisten Fällen ist der aktuelle Arbeits Speicherort ein Laufwerk, auf das über den PowerShell-Dateisystem Anbieter zugegriffen wird, und in einigen Fällen ein Verzeichnis auf diesem Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="20831-109">In most cases, the current working location is a drive accessed through the PowerShell FileSystem provider and, in some cases, a directory on that drive.</span></span>
<span data-ttu-id="20831-110">Beispielsweise können Sie den aktuellen Arbeits Speicherort auf den folgenden Speicherort festlegen:</span><span class="sxs-lookup"><span data-stu-id="20831-110">For example, you might set your current working location to the following location:</span></span>

```powershell
C:\Program Files\Windows PowerShell
```

<span data-ttu-id="20831-111">Folglich werden alle Befehle von diesem Speicherort verarbeitet, es sei denn, es wird explizit ein anderer Pfad bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="20831-111">As a result, all commands are processed from this location unless another path is explicitly provided.</span></span>

<span data-ttu-id="20831-112">PowerShell verwaltet den aktuellen Arbeits Speicherort für jedes Laufwerk, auch wenn das Laufwerk nicht das aktuelle Laufwerk ist.</span><span class="sxs-lookup"><span data-stu-id="20831-112">PowerShell maintains the current working location for each drive even when the drive is not the current drive.</span></span> <span data-ttu-id="20831-113">Dies ermöglicht Ihnen den Zugriff auf Elemente aus dem aktuellen Arbeits Speicherort, indem nur auf das Laufwerk eines anderen Speicher Orts verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="20831-113">This allows you to access items from the current working location by referring only to the drive of another location.</span></span>
<span data-ttu-id="20831-114">Nehmen Sie beispielsweise an, dass der aktuelle Arbeits Speicherort "C: Windows" lautet \\ .</span><span class="sxs-lookup"><span data-stu-id="20831-114">For example, suppose that your current working location is C:\\Windows.</span></span> <span data-ttu-id="20831-115">Nehmen Sie nun an, dass Sie den folgenden Befehl verwenden, um den aktuellen Arbeits Speicherort in das Laufwerk "HKLM:" zu ändern:</span><span class="sxs-lookup"><span data-stu-id="20831-115">Now, suppose you use the following command to change your current working location to the HKLM: drive:</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="20831-116">Obwohl Ihr aktueller Speicherort nun das Registrierungs Laufwerk ist, können Sie weiterhin auf Elemente im Verzeichnis "c: Windows" zugreifen \\ , indem Sie einfach das Laufwerk "c:" verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="20831-116">Although your current location is now the registry drive, you can still access items in the C:\\Windows directory simply by using the C: drive, as shown in the following example:</span></span>

```powershell
Get-ChildItem C:
```

<span data-ttu-id="20831-117">PowerShell speichert, dass der aktuelle Arbeits Speicherort für dieses Laufwerk das Windows-Verzeichnis ist, sodass Elemente aus diesem Verzeichnis abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="20831-117">PowerShell remembers that your current working location for that drive is the Windows directory, so it retrieves items from that directory.</span></span> <span data-ttu-id="20831-118">Die Ergebnisse sind identisch, wenn Sie den folgenden Befehl ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="20831-118">The results would be the same if you ran the following command:</span></span>

```powershell
Get-ChildItem C:\Windows
```

<span data-ttu-id="20831-119">In PowerShell können Sie den Get-Location-Befehl verwenden, um den aktuellen Arbeits Speicherort zu bestimmen, und Sie können den Set-Location-Befehl verwenden, um den aktuellen Arbeits Speicherort festzulegen.</span><span class="sxs-lookup"><span data-stu-id="20831-119">In PowerShell, you can use the Get-Location command to determine the current working location, and you can use the Set-Location command to set the current working location.</span></span> <span data-ttu-id="20831-120">Der folgende Befehl legt z. b. den aktuellen Arbeits Speicherort auf das Windows-Verzeichnis des Laufwerks C: fest:</span><span class="sxs-lookup"><span data-stu-id="20831-120">For example, the following command sets the current working location to the Windows directory of the C: drive:</span></span>

```powershell
Set-Location c:\windows
```

<span data-ttu-id="20831-121">Nachdem Sie den aktuellen Arbeits Speicherort festgelegt haben, können Sie weiterhin auf Elemente von anderen Laufwerken zugreifen, indem Sie einfach den Namen des Laufwerks (gefolgt von einem Doppelpunkt) in den Befehl einschließen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="20831-121">After you set the current working location, you can still access items from other drives simply by including the drive name (followed by a colon) in the command, as shown in the following example:</span></span>

```powershell
Get-ChildItem HKLM:\software
```

<span data-ttu-id="20831-122">Der Beispiel Befehl ruft eine Liste von Elementen im Software Container der HKEY-Hive-Struktur in der Registrierung ab.</span><span class="sxs-lookup"><span data-stu-id="20831-122">The example command retrieves a list of items in the Software container of the HKEY Local Machine hive in the registry.</span></span>

<span data-ttu-id="20831-123">Mit PowerShell können Sie auch Sonderzeichen verwenden, um den aktuellen Arbeits Speicherort und seinen übergeordneten Speicherort darzustellen.</span><span class="sxs-lookup"><span data-stu-id="20831-123">PowerShell also allows you to use special characters to represent the current working location and its parent location.</span></span> <span data-ttu-id="20831-124">Um den aktuellen Arbeits Speicherort darzustellen, verwenden Sie einen einzelnen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="20831-124">To represent the current working location, use a single period.</span></span> <span data-ttu-id="20831-125">Um das übergeordnete Element des aktuellen Arbeitsspeicher Orts darzustellen, verwenden Sie zwei Zeiträume.</span><span class="sxs-lookup"><span data-stu-id="20831-125">To represent the parent of the current working location, use two periods.</span></span> <span data-ttu-id="20831-126">Im folgenden Beispiel wird das System Unterverzeichnis im aktuellen Arbeits Speicherort angegeben:</span><span class="sxs-lookup"><span data-stu-id="20831-126">For example, the following specifies the System subdirectory in the current working location:</span></span>

```powershell
Get-ChildItem .\system
```

<span data-ttu-id="20831-127">Wenn der aktuelle Arbeits Speicherort "C: Windows" ist \\ , gibt dieser Befehl eine Liste aller Elemente im C: \\ Windows-System zurück \\ .</span><span class="sxs-lookup"><span data-stu-id="20831-127">If the current working location is C:\\Windows, this command returns a list of all the items in C:\\Windows\\System.</span></span> <span data-ttu-id="20831-128">Wenn Sie jedoch zwei Zeiträume verwenden, wird das übergeordnete Verzeichnis des aktuellen Arbeitsverzeichnisses verwendet, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="20831-128">However, if you use two periods, the parent directory of the current working directory is used, as shown in the following example:</span></span>

```powershell
Get-ChildItem ..\"program files"
```

<span data-ttu-id="20831-129">In diesem Fall werden die beiden Zeiträume von PowerShell als Laufwerk "c:" behandelt, sodass der Befehl alle Elemente im Verzeichnis "c: \\ Program Files" abruft.</span><span class="sxs-lookup"><span data-stu-id="20831-129">In this case, PowerShell treats the two periods as the C: drive, so the command retrieves all the items in the C:\\Program Files directory.</span></span>

<span data-ttu-id="20831-130">Ein Pfad, der mit einem Schrägstrich beginnt, identifiziert einen Pfad vom Stamm des aktuellen Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="20831-130">A path beginning with a slash identifies a path from the root of the current drive.</span></span> <span data-ttu-id="20831-131">Wenn der aktuelle Arbeits Speicherort z. b. c: \\ Program Files \\ PowerShell lautet, ist der Stamm des Laufwerks c. Aus diesem Grund listet der folgende Befehl alle Elemente im Verzeichnis "C: Windows" auf \\ :</span><span class="sxs-lookup"><span data-stu-id="20831-131">For example, if your current working location is C:\\Program Files\\PowerShell, the root of your drive is C. Therefore, the following command lists all items in the C:\\Windows directory:</span></span>

```powershell
Get-ChildItem \windows
```

<span data-ttu-id="20831-132">Wenn Sie keinen Pfad angeben, der mit einem Laufwerks Namen, einem Schrägstrich oder einem Punkt beginnt, wenn Sie den Namen eines Containers oder Elements angeben, wird davon ausgegangen, dass sich der Container bzw. das Element am aktuellen Arbeits Speicherort befindet.</span><span class="sxs-lookup"><span data-stu-id="20831-132">If you do not specify a path beginning with a drive name, slash, or period when supplying the name of a container or item, the container or item is assumed to be located in the current working location.</span></span> <span data-ttu-id="20831-133">Wenn der aktuelle Arbeits Speicherort z. b. "c: Windows" lautet \\ , gibt der folgende Befehl alle Elemente im \\ System Verzeichnis "c: Windows" zurück \\ :</span><span class="sxs-lookup"><span data-stu-id="20831-133">For example, if your current working location is C:\\Windows, the following command returns all the items in the C:\\Windows\\System directory:</span></span>

```powershell
Get-ChildItem system
```

<span data-ttu-id="20831-134">Wenn Sie anstelle eines Verzeichnis namens einen Dateinamen angeben, gibt PowerShell Details zu dieser Datei zurück (unter der Voraussetzung, dass sich die Datei im aktuellen Arbeits Speicherort befindet).</span><span class="sxs-lookup"><span data-stu-id="20831-134">If you specify a file name rather than a directory name, PowerShell returns details about that file (assuming that file is located in the current working location).</span></span>

## <a name="see-also"></a><span data-ttu-id="20831-135">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="20831-135">SEE ALSO</span></span>

[<span data-ttu-id="20831-136">Set-Location</span><span class="sxs-lookup"><span data-stu-id="20831-136">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

[<span data-ttu-id="20831-137">about_Providers</span><span class="sxs-lookup"><span data-stu-id="20831-137">about_Providers</span></span>](about_Providers.md)

[<span data-ttu-id="20831-138">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="20831-138">about_Path_Syntax</span></span>](about_Path_Syntax.md)

