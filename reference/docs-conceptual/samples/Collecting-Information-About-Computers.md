---
ms.date: 12/23/2019
keywords: powershell,cmdlet
title: Erfassen von Informationen über Computer
description: In diesem Artikel wird beschrieben, wie Sie mithilfe von WMI- und CIM-Cmdlets Informationen zur Computerkonfiguration sammeln.
ms.openlocfilehash: 5088960ab7c049085a9d7c05ec4571b6fd7e3545
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500588"
---
# <a name="collecting-information-about-computers"></a><span data-ttu-id="e5f04-104">Erfassen von Informationen über Computer</span><span class="sxs-lookup"><span data-stu-id="e5f04-104">Collecting Information About Computers</span></span>

<span data-ttu-id="e5f04-105">Cmdlets des Moduls **CimCmdlets** sind die wichtigsten Cmdlets für einfache Tasks zur Systemverwaltung.</span><span class="sxs-lookup"><span data-stu-id="e5f04-105">Cmdlets from **CimCmdlets** module are the most important cmdlets for general system management tasks.</span></span> <span data-ttu-id="e5f04-106">Alle kritischen Subsystemeinstellungen werden über WMI verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="e5f04-106">All critical subsystem settings are exposed through WMI.</span></span> <span data-ttu-id="e5f04-107">Darüber hinaus behandelt WMI Daten als Objekte, die zu Sammlungen eines oder mehrerer Elemente gehören.</span><span class="sxs-lookup"><span data-stu-id="e5f04-107">Furthermore, WMI treats data as objects that are in collections of one or more items.</span></span> <span data-ttu-id="e5f04-108">Da Windows PowerShell ebenfalls mit Objekten arbeitet und über eine Pipeline verfügt, mit der Sie einzelne oder mehrere Objekte auf die gleiche Weise behandeln können, ermöglicht der generische WMI-Zugriff Ihnen, einige erweiterte Aufgaben mit sehr geringem Aufwand auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e5f04-108">Because Windows PowerShell also works with objects and has a pipeline that allows you to treat single or multiple objects in the same way, generic WMI access allows you to perform some advanced tasks with very little work.</span></span>

## <a name="listing-desktop-settings"></a><span data-ttu-id="e5f04-109">Auflisten von Desktopeinstellungen</span><span class="sxs-lookup"><span data-stu-id="e5f04-109">Listing Desktop Settings</span></span>

<span data-ttu-id="e5f04-110">Wir beginnen mit einem Befehl, der Informationen über die Desktops auf dem lokalen Computer erfasst.</span><span class="sxs-lookup"><span data-stu-id="e5f04-110">We'll begin with a command that collects information about the desktops on the local computer.</span></span>

```powershell
Get-CimInstance -ClassName Win32_Desktop
```

<span data-ttu-id="e5f04-111">Dadurch werden Informationen über alle Desktops zurückgegeben, ganz gleich, ob sie verwendet werden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e5f04-111">This returns information for all desktops, whether they are in use or not.</span></span>

> [!NOTE]
> <span data-ttu-id="e5f04-112">Einige WMI-Klassen geben sehr detaillierte Informationen zurück, die häufig Metadaten über die WMI-Klasse enthalten.</span><span class="sxs-lookup"><span data-stu-id="e5f04-112">Information returned by some WMI classes can be very detailed, and often include metadata about the WMI class.</span></span>

<span data-ttu-id="e5f04-113">Da die meisten dieser Metadateneigenschaften über Namen verfügen, die mit **Cim** beginnen, können Sie die Eigenschaften mit `Select-Object` filtern.</span><span class="sxs-lookup"><span data-stu-id="e5f04-113">Because most of these metadata properties have names that begin with **Cim** , you can filter the properties using `Select-Object`.</span></span> <span data-ttu-id="e5f04-114">Geben Sie dem Parameter **-ExcludeProperty** mit „Cim\*“ als Wert an.</span><span class="sxs-lookup"><span data-stu-id="e5f04-114">Specify the **-ExcludeProperty** parameter with "Cim\*" as the value.</span></span> <span data-ttu-id="e5f04-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e5f04-115">For example:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Desktop | Select-Object -ExcludeProperty "CIM*"
```

<span data-ttu-id="e5f04-116">Um die Metadaten zu filtern, verwenden Sie einen Pipelineoperator (|), um die Ergebnisse des Befehls `Get-CimInstance` an `Select-Object -ExcludeProperty "CIM*"` zu senden.</span><span class="sxs-lookup"><span data-stu-id="e5f04-116">To filter out the metadata, use a pipeline operator (|) to send the results of the `Get-CimInstance` command to `Select-Object -ExcludeProperty "CIM*"`.</span></span>

## <a name="listing-bios-information"></a><span data-ttu-id="e5f04-117">Auflisten von BIOS-Informationen</span><span class="sxs-lookup"><span data-stu-id="e5f04-117">Listing BIOS Information</span></span>

<span data-ttu-id="e5f04-118">Die WMI-Klasse **Win32_BIOS** gibt kompakte und vollständige Informationen zum System-BIOS auf dem lokalen Computer zurück:</span><span class="sxs-lookup"><span data-stu-id="e5f04-118">The WMI **Win32_BIOS** class returns fairly compact and complete information about the system BIOS on the local computer:</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS
```

## <a name="listing-processor-information"></a><span data-ttu-id="e5f04-119">Auflisten von Prozessorinformationen</span><span class="sxs-lookup"><span data-stu-id="e5f04-119">Listing Processor Information</span></span>

<span data-ttu-id="e5f04-120">Sie können allgemeine Prozessorinformationen mithilfe der WMI-Klasse **Win32_Processor** abrufen. Allerdings möchten Sie die Daten wahrscheinlich filtern:</span><span class="sxs-lookup"><span data-stu-id="e5f04-120">You can retrieve general processor information by using WMI's **Win32_Processor** class, although you will likely want to filter the information:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Processor | Select-Object -ExcludeProperty "CIM*"
```

<span data-ttu-id="e5f04-121">Wenn Sie eine Zeichenfolge mit einer allgemeinen Beschreibung der Prozessorfamilie erhalten möchten, lassen Sie die **SystemType** -Eigenschaft zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="e5f04-121">For a generic description string of the processor family, you can just return the **SystemType** property:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem | Select-Object -Property SystemType

SystemType
----------
X86-based PC
```

## <a name="listing-computer-manufacturer-and-model"></a><span data-ttu-id="e5f04-122">Auflisten von Informationen zum Computerhersteller und -modell</span><span class="sxs-lookup"><span data-stu-id="e5f04-122">Listing Computer Manufacturer and Model</span></span>

<span data-ttu-id="e5f04-123">Informationen zum Computermodell sind auch über **Win32_ComputerSystem** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5f04-123">Computer model information is also available from **Win32_ComputerSystem** .</span></span> <span data-ttu-id="e5f04-124">Zum Bereitstellen von OEM-Daten ist keine Filterung der angezeigten Standardausgabe erforderlich:</span><span class="sxs-lookup"><span data-stu-id="e5f04-124">The standard displayed output will not need any filtering to provide OEM data:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem
```

```Output
Name PrimaryOwnerName Domain    TotalPhysicalMemory Model                   Manufacturer
---- ---------------- ------    ------------------- -----                   ------------
MyPC Jane Doe         WORKGROUP 804765696           DA243A-ABA 6415cl NA910 Compaq Presario 06
```

<span data-ttu-id="e5f04-125">Die Ausgabe von Befehlen, die Informationen direkt von bestimmter Hardware zurückgeben, kann nur so gut sein, wie die vorhandenen Daten.</span><span class="sxs-lookup"><span data-stu-id="e5f04-125">Your output from commands such as this, which return information directly from some hardware, is only as good as the data you have.</span></span> <span data-ttu-id="e5f04-126">Einige Informationen wurden von den Hardwareherstellern nicht ordnungsgemäß konfiguriert und sind daher möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5f04-126">Some information is not correctly configured by hardware manufacturers and may therefore be unavailable.</span></span>

## <a name="listing-installed-hotfixes"></a><span data-ttu-id="e5f04-127">Auflisten installierter Hotfixes</span><span class="sxs-lookup"><span data-stu-id="e5f04-127">Listing Installed Hotfixes</span></span>

<span data-ttu-id="e5f04-128">Mit **Win32_QuickFixEngineering** können Sie alle installierten Hotfixes auflisten:</span><span class="sxs-lookup"><span data-stu-id="e5f04-128">You can list all installed hotfixes by using **Win32_QuickFixEngineering** :</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering
```

<span data-ttu-id="e5f04-129">Diese Klasse gibt eine Liste von Hotfixes zurück, die wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="e5f04-129">This class returns a list of hotfixes that looks like this:</span></span>

```Output
Source Description     HotFixID  InstalledBy   InstalledOn PSComputerName
------ -----------     --------  -----------   ----------- --------------
       Security Update KB4048951 Administrator 12/16/2017  .
```

<span data-ttu-id="e5f04-130">Wenn Sie eine kompaktere Ausgabe erhalten möchten, können Sie bestimmte Eigenschaften ausschließen.</span><span class="sxs-lookup"><span data-stu-id="e5f04-130">For more succinct output, you may want to exclude some properties.</span></span> <span data-ttu-id="e5f04-131">Sie können zwar den `Get-CimInstance`Property **-Parameter von** verwenden, um nur die **HotFixID** auszuwählen. Dennoch werden weitere Informationen zurückgegeben, da standardmäßig alle Metadaten angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="e5f04-131">Although you can use the `Get-CimInstance`'s **Property** parameter to choose only the **HotFixID** , doing so will actually return more information, because all the metadata is displayed by default:</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -Property HotFixID
```

```Output
InstalledOn           :
Caption               :
Description           :
InstallDate           :
Name                  :
Status                :
CSName                :
FixComments           :
HotFixID              : KB4533002
InstalledBy           :
ServicePackInEffect   :
PSComputerName        :
CimClass              : root/cimv2:Win32_QuickFixEngineering
CimInstanceProperties : {Caption, Description, InstallDate, Name…}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
...
```

<span data-ttu-id="e5f04-132">Die zusätzlichen Daten werden zurückgegeben, weil der **Property** -Parameter in `Get-CimInstance` die von WMI-Klasseninstanzen zurückgegebenen Eigenschaften, nicht aber das an die PowerShell zurückgegebene Objekt einschränkt.</span><span class="sxs-lookup"><span data-stu-id="e5f04-132">The additional data is returned, because the **Property** parameter in `Get-CimInstance` restricts the properties returned from WMI class instances, not the object returned to PowerShell.</span></span> <span data-ttu-id="e5f04-133">Um die Ausgabe zu verringern, verwenden Sie `Select-Object`:</span><span class="sxs-lookup"><span data-stu-id="e5f04-133">To reduce the output, use `Select-Object`:</span></span>

```powershell
Get-CimInstance -ClassName Win32_QuickFixEngineering -Property HotFixId | Select-Object -Property HotFixId
```

```Output
HotFixId
--------
KB4048951
```

## <a name="listing-operating-system-version-information"></a><span data-ttu-id="e5f04-134">Auflisten von Informationen zur Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="e5f04-134">Listing Operating System Version Information</span></span>

<span data-ttu-id="e5f04-135">Die Klasseneigenschaften **Win32_OperatingSystem** umfassen Informationen zur Version und zum Service Pack.</span><span class="sxs-lookup"><span data-stu-id="e5f04-135">The **Win32_OperatingSystem** class properties include version and service pack information.</span></span> <span data-ttu-id="e5f04-136">Sie können mit **Win32_OperatingSystem** explizit nur diese Eigenschaften auswählen, um eine Zusammenfassung von Versionsinformationen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="e5f04-136">You can explicitly select only these properties to get a version information summary from **Win32_OperatingSystem** :</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem |
  Select-Object -Property BuildNumber,BuildType,OSType,ServicePackMajorVersion,ServicePackMinorVersion
```

<span data-ttu-id="e5f04-137">Sie können mit dem **Property** -Parameter von `Select-Object` auch Platzhalterzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5f04-137">You can also use wildcards with the `Select-Object`'s **Property** parameter.</span></span> <span data-ttu-id="e5f04-138">Da alle Eigenschaften, die entweder mit **Build** oder **Service Pack** beginnen, hier wichtig sind, können wir das Beispiel auf das folgende Format kürzen:</span><span class="sxs-lookup"><span data-stu-id="e5f04-138">Because all the properties beginning with either **Build** or **ServicePack** are important to use here, we can shorten this to the following form:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property Build*,OSType,ServicePack*
```

```Output
BuildNumber             : 18362
BuildType               : Multiprocessor Free
OSType                  : 18
ServicePackMajorVersion : 0
ServicePackMinorVersion : 0
```

## <a name="listing-local-users-and-owner"></a><span data-ttu-id="e5f04-139">Auflisten der lokalen Benutzer und des Besitzers</span><span class="sxs-lookup"><span data-stu-id="e5f04-139">Listing Local Users and Owner</span></span>

<span data-ttu-id="e5f04-140">Allgemeine lokale Benutzerinformationen (z. B. Anzahl lizenzierter Benutzer, aktuelle Anzahl von Benutzern und Besitzername) können Sie mit einer Auswahl von **Win32_OperatingSystem** -Klasseneigenschaften suchen.</span><span class="sxs-lookup"><span data-stu-id="e5f04-140">Local general user information — number of licensed users, current number of users, and owner name — can be found with a selection of **Win32_OperatingSystem** class properties.</span></span> <span data-ttu-id="e5f04-141">Sie können die anzuzeigenden Eigenschaften wie folgt explizit auswählen:</span><span class="sxs-lookup"><span data-stu-id="e5f04-141">You can explicitly select the properties to display like this:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem |
  Select-Object -Property NumberOfLicensedUsers,NumberOfUsers,RegisteredUser
```

<span data-ttu-id="e5f04-142">Eine kompaktere Version mit Platzhaltern ist:</span><span class="sxs-lookup"><span data-stu-id="e5f04-142">A more succinct version using wildcards is:</span></span>

```powershell
Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property *user*
```

## <a name="getting-available-disk-space"></a><span data-ttu-id="e5f04-143">Abrufen des verfügbaren Speicherplatzes</span><span class="sxs-lookup"><span data-stu-id="e5f04-143">Getting Available Disk Space</span></span>

<span data-ttu-id="e5f04-144">Um den Speicherplatz und den freien Speicherplatz auf lokalen Laufwerken anzuzeigen, können Sie die WMI-Klasse „Win32_LogicalDisk“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5f04-144">To see the disk space and free space for local drives, you can use the Win32_LogicalDisk WMI class.</span></span>
<span data-ttu-id="e5f04-145">Sie brauchen nur Instanzen mit einem „DriveType“-Wert von „3“ anzuzeigen. Dieser Wert wird von WMI für Festplatten mit fester Größe verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5f04-145">You need to see only instances with a DriveType of 3 — the value WMI uses for fixed hard disks.</span></span>

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3"
```

```Output
DeviceID DriveType ProviderName VolumeName Size         FreeSpace   PSComputerName
-------- --------- ------------ ---------- ----         ---------   --------------
C:       3                      Local Disk 203912880128 65541357568 .
Q:       3                      New Volume 122934034432 44298250240 .
```

```powershell
Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3" |
  Measure-Object -Property FreeSpace,Size -Sum |
    Select-Object -Property Property,Sum
```

```Output
Property           Sum
--------           ---
FreeSpace 109839607808
Size      326846914560
```

## <a name="getting-logon-session-information"></a><span data-ttu-id="e5f04-146">Abrufen von Informationen zur Anmeldesitzung</span><span class="sxs-lookup"><span data-stu-id="e5f04-146">Getting Logon Session Information</span></span>

<span data-ttu-id="e5f04-147">Allgemeine Informationen zu Benutzern zugeordneten Anmeldesitzungen können Sie über die WMI-Klasse **Win32_LogonSession** abrufen:</span><span class="sxs-lookup"><span data-stu-id="e5f04-147">You can get general information about logon sessions associated with users through the **Win32_LogonSession** WMI class:</span></span>

```powershell
Get-CimInstance -ClassName Win32_LogonSession
```

## <a name="getting-the-user-logged-on-to-a-computer"></a><span data-ttu-id="e5f04-148">Abrufen des auf einem Computer angemeldeten Benutzers</span><span class="sxs-lookup"><span data-stu-id="e5f04-148">Getting the User Logged on to a Computer</span></span>

<span data-ttu-id="e5f04-149">Mit „Win32_ComputerSystem“ können Sie den auf einem bestimmten Computer angemeldeten Benutzers anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e5f04-149">You can display the user logged on to a particular computer system using Win32_ComputerSystem.</span></span> <span data-ttu-id="e5f04-150">Dieser Befehl gibt nur den auf dem Systemdesktop angemeldeten Benutzer zurück:</span><span class="sxs-lookup"><span data-stu-id="e5f04-150">This command returns only the user logged on to the system desktop:</span></span>

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -Property UserName
```

## <a name="getting-local-time-from-a-computer"></a><span data-ttu-id="e5f04-151">Abrufen der lokalen Uhrzeit eines Computers</span><span class="sxs-lookup"><span data-stu-id="e5f04-151">Getting Local Time from a Computer</span></span>

<span data-ttu-id="e5f04-152">Sie können die aktuelle lokale Zeit auf einem bestimmten Computer mit der Klasse **WMI-Win32_LocalTime** abrufen.</span><span class="sxs-lookup"><span data-stu-id="e5f04-152">You can retrieve the current local time on a specific computer by using the **Win32_LocalTime** WMI class.</span></span>

```powershell
Get-CimInstance -ClassName Win32_LocalTime
```

```Output
Day            : 23
DayOfWeek      : 1
Hour           : 8
Milliseconds   :
Minute         : 52
Month          : 12
Quarter        : 4
Second         : 55
WeekInMonth    : 4
Year           : 2019
PSComputerName :
```

## <a name="displaying-service-status"></a><span data-ttu-id="e5f04-153">Anzeigen des Dienststatus</span><span class="sxs-lookup"><span data-stu-id="e5f04-153">Displaying Service Status</span></span>

<span data-ttu-id="e5f04-154">Zum Anzeigen des Status aller Dienste auf einem bestimmten Computer können Sie das Cmdlet `Get-Service` verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5f04-154">To view the status of all services on a specific computer, you can locally use the `Get-Service` cmdlet.</span></span> <span data-ttu-id="e5f04-155">Für Remotesysteme können Sie die Klasse **WMI-Win32_Service** verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5f04-155">For remote systems, you can use the **Win32_Service** WMI class.</span></span> <span data-ttu-id="e5f04-156">Wenn Sie die Ergebnisse außerdem mit `Select-Object` nach **Status** , **Name** und **DisplayName** filtern, ist das Ausgabeformat fast identisch mit dem von `Get-Service`:</span><span class="sxs-lookup"><span data-stu-id="e5f04-156">If you also use `Select-Object` to filter the results to **Status** , **Name** , and **DisplayName** , the output format will be almost identical to that from `Get-Service`:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service | Select-Object -Property Status,Name,DisplayName
```

<span data-ttu-id="e5f04-157">Um für die wenigen Dienste mit extrem langen Namen die Anzeige der vollständigen Namen zu ermöglichen, können Sie `Format-Table` mit den Parametern **AutoSize** und **Wrap** verwenden. Dadurch wird die Spaltenbreite optimiert und ermöglicht, dass lange Namen umgebrochen und nicht abgeschnitten werden:</span><span class="sxs-lookup"><span data-stu-id="e5f04-157">To allow the complete display of names for the occasional services with extremely long names, you may want to use `Format-Table` with the **AutoSize** and **Wrap** parameters, to optimize column width and allow long names to wrap instead of being truncated:</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service | Format-Table -Property Status,Name,DisplayName -AutoSize -Wrap
```
