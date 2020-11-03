---
description: Erläutert Einschränkungen von Windows PowerShell 4,0 unter Windows RT 8,1.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_rt?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_RT
ms.openlocfilehash: 323f06a7a0d8253417510503c1011ac02c20179f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222436"
---
# <a name="about-windows-rt"></a><span data-ttu-id="19b37-104">Informationen zu Windows RT</span><span class="sxs-lookup"><span data-stu-id="19b37-104">About Windows RT</span></span>

## <a name="short-description"></a><span data-ttu-id="19b37-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="19b37-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="19b37-106">Erläutert Einschränkungen von Windows PowerShell 4,0 unter Windows RT 8,1.</span><span class="sxs-lookup"><span data-stu-id="19b37-106">Explains limitations of  Windows PowerShell 4.0 on Windows RT 8.1.</span></span>

## <a name="long-description"></a><span data-ttu-id="19b37-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="19b37-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="19b37-108">Das Betriebssystem Windows RT 8,1 ist auf Computern und Geräten installiert (z. b. Microsoft Surface 2, auf denen es sich um das Betriebssystem des Computers handelt), von dem Advanced RISC Machine (Arm)-Prozessoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19b37-108">The Windows RT 8.1 operating system is installed on computers and devices (such as Microsoft Surface 2, on which it is the operating system that ships with the computer) that use Advanced RISC Machine (ARM) processors.</span></span>

<span data-ttu-id="19b37-109">Windows PowerShell 4,0 ist in Windows RT 8,1 enthalten.</span><span class="sxs-lookup"><span data-stu-id="19b37-109">Windows PowerShell 4.0 is included in Windows RT 8.1.</span></span> <span data-ttu-id="19b37-110">Alle-Cmdlets,-Anbieter und-Module sowie die meisten Skripts, die für Windows PowerShell 2,0 und spätere Versionen entworfen wurden, können ohne Änderungen unter Windows RT 8,1 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="19b37-110">All cmdlets, providers, and modules, and most scripts designed for Windows PowerShell 2.0 and later releases run on Windows RT 8.1 without changes.</span></span>

<span data-ttu-id="19b37-111">Da Windows RT 8,1 nicht alle Windows-Features umfasst, funktionieren einige Windows PowerShell-Features anders oder funktionieren nicht auf Windows RT-basierten Geräten.</span><span class="sxs-lookup"><span data-stu-id="19b37-111">Because Windows RT 8.1 does not include all Windows features, some Windows PowerShell features work differently or do not work on Windows RT-based devices.</span></span> <span data-ttu-id="19b37-112">In der folgenden Liste werden die Unterschiede erläutert.</span><span class="sxs-lookup"><span data-stu-id="19b37-112">The following list explains the differences.</span></span>

- <span data-ttu-id="19b37-113">Windows PowerShell ISE ist nicht in enthalten und kann unter Windows RT 8,1 nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="19b37-113">Windows PowerShell ISE is not included in and cannot run on Windows RT 8.1.</span></span>
  <span data-ttu-id="19b37-114">Windows PowerShell ISE erfordert Windows Presentation Foundation, das nicht in Windows RT 8,1 enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="19b37-114">Windows PowerShell ISE requires Windows Presentation Foundation, which is not included in Windows RT 8.1.</span></span>

- <span data-ttu-id="19b37-115">Windows PowerShell-Remoting und der WinRM-Dienst sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="19b37-115">Windows PowerShell remoting and the WinRM service are disabled by default.</span></span>
  <span data-ttu-id="19b37-116">Um Remoting zu aktivieren, führen Sie das Enable-PSRemoting-Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="19b37-116">To enable remoting, run the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="19b37-117">Führen Sie außerdem das Set-Service-Cmdlet aus, um den Starttyp des WinRM-Dienstanbieter auf automatisch oder automatisch (verzögerter Start) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="19b37-117">Also, run the Set-Service cmdlet to set the startup type of the WinRM service to Automatic, or Automatic (Delayed Start).</span></span>

  <span data-ttu-id="19b37-118">Während Remoting deaktiviert ist, können Sie Windows PowerShell-Remoting verwenden, um Befehle auf anderen Computern auszuführen, andere Computer können jedoch keine Befehle auf dem Windows RT-Gerät ausführen.</span><span class="sxs-lookup"><span data-stu-id="19b37-118">While remoting is disabled, you can use Windows PowerShell remoting to run commands on other computers, but other computers cannot run commands on the Windows RT device.</span></span> <span data-ttu-id="19b37-119">Außerdem implizites Remoting, d. h. Remoting, das in ein Cmdlet oder Skript integriert ist, und nicht explizit mit hinzugefügten Parametern angefordert</span><span class="sxs-lookup"><span data-stu-id="19b37-119">Also, implicit remoting - that is, remoting that is built in to a cmdlet or script, and not explicitly requested with added parameters</span></span>
  - <span data-ttu-id="19b37-120">funktioniert nicht in Windows PowerShell, die unter Windows RT 8,1 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="19b37-120">does not work in Windows PowerShell running on Windows RT 8.1.</span></span>

- <span data-ttu-id="19b37-121">In die Domäne eingebundenes Computing und die Kerberos-Authentifizierung werden unter Windows RT 8,1 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19b37-121">Domain-joined computing and Kerberos authentication are not supported on Windows RT 8.1.</span></span> <span data-ttu-id="19b37-122">Sie können Windows PowerShell nicht verwenden, um diese Features hinzuzufügen oder zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="19b37-122">You cannot use Windows PowerShell to add or manage these features.</span></span>

- <span data-ttu-id="19b37-123">Microsoft .NET Framework-Klassen, die unter Windows RT 8,1 nicht unterstützt werden, werden von Windows PowerShell unter Windows RT 8,1 ebenfalls nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19b37-123">Microsoft .NET Framework classes that are not supported on Windows RT 8.1 are also not supported by Windows PowerShell on Windows RT 8.1.</span></span>

- <span data-ttu-id="19b37-124">Transaktionen sind unter Windows RT 8,1 nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="19b37-124">Transactions are not enabled on Windows RT 8.1.</span></span> <span data-ttu-id="19b37-125">Transaktions-Cmdlets, wie z. b. Start-Transaction, und Transaktions Parameter, wie z. b. UseTransaction, funktionieren nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="19b37-125">Transaction cmdlets, such as Start-Transaction, and transaction parameters, such as UseTransaction, do not work properly.</span></span>

- <span data-ttu-id="19b37-126">Alle Windows PowerShell-Sitzungen auf Windows RT 8,1-Geräten verwenden den einschräninedlanguage-Sprachmodus.</span><span class="sxs-lookup"><span data-stu-id="19b37-126">All Windows PowerShell sessions on Windows RT 8.1 devices use the ConstrainedLanguage language mode.</span></span> <span data-ttu-id="19b37-127">Der Modus "einschräninedlanguage" ist ein Begleit Konto für die Benutzermodus-Code Integrität (ENCI).</span><span class="sxs-lookup"><span data-stu-id="19b37-127">ConstrainedLanguage language mode is a companion to User Mode Code Integrity (UMCI).</span></span> <span data-ttu-id="19b37-128">Sie ermöglicht alle Windows-Cmdlets und Windows PowerShell-Sprachelemente, schränkt jedoch die Typen ein, um sicherzustellen, dass Benutzer Windows PowerShell nicht verwenden können, um den umci-Schutz zu umgehen oder zu verletzen</span><span class="sxs-lookup"><span data-stu-id="19b37-128">It permits all Windows cmdlets and Windows PowerShell language elements, but restricts types to ensure that users cannot use Windows PowerShell to circumvent or violate the UMCI protections.</span></span>

<span data-ttu-id="19b37-129">Weitere Informationen zum einschräninedlanguage-Sprachmodus finden Sie unter [about_Language_Modes](about_Language_Modes.md).</span><span class="sxs-lookup"><span data-stu-id="19b37-129">For more information about ConstrainedLanguage language mode, see [about_Language_Modes](about_Language_Modes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="19b37-130">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="19b37-130">SEE ALSO</span></span>

[<span data-ttu-id="19b37-131">about_Language_Modes</span><span class="sxs-lookup"><span data-stu-id="19b37-131">about_Language_Modes</span></span>](about_Language_Modes.md)

[<span data-ttu-id="19b37-132">about_Remote</span><span class="sxs-lookup"><span data-stu-id="19b37-132">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="19b37-133">about_Windows_PowerShell_ISE</span><span class="sxs-lookup"><span data-stu-id="19b37-133">about_Windows_PowerShell_ISE</span></span>](about_Windows_PowerShell_ISE.md)
