---
ms.date: 12/05/2019
keywords: powershell,cmdlet
title: Starten von Windows PowerShell
description: In diesem Artikel werden die Methoden zum Starten verschiedener Versionen von PowerShell erläutert.
ms.openlocfilehash: 47da7d85c9f7e6966a7f7e809c77979cd24cf129
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664020"
---
# <a name="starting-windows-powershell"></a><span data-ttu-id="6b3df-104">Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b3df-104">Starting Windows PowerShell</span></span>

<span data-ttu-id="6b3df-105">Windows PowerShell ist eine Skript-Engine im `.DLL`-Format, die in mehreren Hosts eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="6b3df-105">Windows PowerShell is a scripting engine `.DLL` that's embedded into multiple hosts.</span></span> <span data-ttu-id="6b3df-106">Als Hosts werden am häufigsten die interaktive Befehlszeile `powershell.exe` und die interaktive Skriptumgebung `powershell_ise.exe` verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b3df-106">The most common hosts you'll start are the interactive command-line `powershell.exe` and the Interactive Scripting Environment `powershell_ise.exe`.</span></span>

<span data-ttu-id="6b3df-107">Informationen zum Starten von Windows PowerShell&reg; unter Windows Server&reg; 2012 R2, Windows&reg; 8.1, Windows Server 2012 und Windows 8 finden Sie unter [Allgemeine Verwaltungsaufgaben und Navigation in Windows](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="6b3df-107">To start Windows PowerShell&reg; on Windows Server&reg; 2012 R2, Windows&reg; 8.1, Windows Server 2012, and Windows 8, see [Common Management Tasks and Navigation in Windows](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11)).</span></span>

## <a name="powershell-core-has-renamed-binary"></a><span data-ttu-id="6b3df-108">Umbenannte Binärdatei in PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="6b3df-108">PowerShell Core has renamed binary</span></span>

<span data-ttu-id="6b3df-109">PowerShell Core, auch als PowerShell bezeichnet, ist die Open-Source-Version 6 und höher, die .NET Core verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b3df-109">PowerShell Core, referred to as PowerShell, is version 6 and higher that's open source and uses .NET Core.</span></span> <span data-ttu-id="6b3df-110">Die unterstützten Versionen sind unter Windows, macOS und Linux verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6b3df-110">Supported versions are available on Windows, macOS, and Linux.</span></span>

<span data-ttu-id="6b3df-111">Ab PowerShell 6 wurde die PowerShell-Binärdatei für Windows in `pwsh.exe` und für macOS und Linux in `pwsh` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="6b3df-111">Beginning in PowerShell 6, the PowerShell binary was renamed `pwsh.exe` for Windows and `pwsh` for macOS and Linux.</span></span> <span data-ttu-id="6b3df-112">Sie können PowerShell-Vorschauversionen mit `pwsh-preview` starten.</span><span class="sxs-lookup"><span data-stu-id="6b3df-112">You can start PowerShell preview versions using `pwsh-preview`.</span></span> <span data-ttu-id="6b3df-113">Weitere Informationen finden Sie unter [Neuigkeiten in PowerShell Core 6.0](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe) und [Über pwsh](/powershell/module/microsoft.powershell.core/about/about_pwsh).</span><span class="sxs-lookup"><span data-stu-id="6b3df-113">For more information, see [What's New in PowerShell Core 6.0](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe) and [About pwsh](/powershell/module/microsoft.powershell.core/about/about_pwsh).</span></span>

<span data-ttu-id="6b3df-114">Verwenden Sie die folgenden Links, um die Cmdlet-Referenz und die Installationsdokumentation für PowerShell 7 zu finden:</span><span class="sxs-lookup"><span data-stu-id="6b3df-114">To find cmdlet reference and installation documentation for PowerShell 7, use the following links:</span></span>

| <span data-ttu-id="6b3df-115">Dokument</span><span class="sxs-lookup"><span data-stu-id="6b3df-115">Document</span></span> | <span data-ttu-id="6b3df-116">Link</span><span class="sxs-lookup"><span data-stu-id="6b3df-116">Link</span></span> |
| ----- | ----- |
| <span data-ttu-id="6b3df-117">Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="6b3df-117">Cmdlet reference</span></span> | [<span data-ttu-id="6b3df-118">PowerShell-Modulbrowser</span><span class="sxs-lookup"><span data-stu-id="6b3df-118">PowerShell Module Browser</span></span>](/powershell/module/) |
| <span data-ttu-id="6b3df-119">Windows-Installation</span><span class="sxs-lookup"><span data-stu-id="6b3df-119">Windows installation</span></span> | [<span data-ttu-id="6b3df-120">Installieren von PowerShell Core unter Windows</span><span class="sxs-lookup"><span data-stu-id="6b3df-120">Installing PowerShell Core on Windows</span></span>](/powershell/scripting/install/installing-powershell-core-on-windows) |
| <span data-ttu-id="6b3df-121">macOS-Installation</span><span class="sxs-lookup"><span data-stu-id="6b3df-121">macOS installation</span></span> | [<span data-ttu-id="6b3df-122">Installieren von PowerShell Core unter macOS</span><span class="sxs-lookup"><span data-stu-id="6b3df-122">Installing PowerShell Core on macOS</span></span>](/powershell/scripting/install/installing-powershell-core-on-macos) |
| <span data-ttu-id="6b3df-123">Linux-Installation</span><span class="sxs-lookup"><span data-stu-id="6b3df-123">Linux installation</span></span> | [<span data-ttu-id="6b3df-124">Installieren von PowerShell Core unter Linux</span><span class="sxs-lookup"><span data-stu-id="6b3df-124">Installing PowerShell Core on Linux</span></span>](/powershell/scripting/install/installing-powershell-core-on-linux) |

<span data-ttu-id="6b3df-125">Zur Ansicht des Inhalts anderer PowerShell-Versionen finden Sie weitere Informationen unter [Verwenden der PowerShell-Dokumentation](../how-to-use-docs.md).</span><span class="sxs-lookup"><span data-stu-id="6b3df-125">To view content for other PowerShell versions, see [How to use the PowerShell documentation](../how-to-use-docs.md).</span></span>

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a><span data-ttu-id="6b3df-126">Starten von Windows PowerShell unter früheren Versionen von Windows</span><span class="sxs-lookup"><span data-stu-id="6b3df-126">How to Start Windows PowerShell on Earlier Versions of Windows</span></span>

<span data-ttu-id="6b3df-127">In diesem Abschnitt wird das Starten von Windows PowerShell und Windows PowerShell Integrated Scripting Environment (ISE) unter Windows&reg; 7, Windows Server&reg; 2008 R2 und Windows Server&reg; 2008 erläutert.</span><span class="sxs-lookup"><span data-stu-id="6b3df-127">This section explains how to start Windows PowerShell and Windows PowerShell Integrated Scripting Environment (ISE) on Windows&reg; 7, Windows Server&reg; 2008 R2, and Windows Server&reg; 2008.</span></span> <span data-ttu-id="6b3df-128">Außerdem wird beschrieben, wie das optionale Feature für Windows PowerShell ISE in Windows PowerShell 2.0 in Windows Server&reg; 2008 R2 und Windows Server&reg; 2008 aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="6b3df-128">It also explains how to enable the optional feature for Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server&reg; 2008 R2 and Windows Server&reg; 2008.</span></span>

<span data-ttu-id="6b3df-129">Mit den folgenden Methoden können Sie die installierte Version von Windows PowerShell 3.0 oder Windows PowerShell 4.0 installieren, sofern zutreffend.</span><span class="sxs-lookup"><span data-stu-id="6b3df-129">Use any of the following methods to start the installed version of Windows PowerShell 3.0, or Windows PowerShell 4.0, where applicable.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="6b3df-130">Über das Startmenü</span><span class="sxs-lookup"><span data-stu-id="6b3df-130">From the Start Menu</span></span>

- <span data-ttu-id="6b3df-131">Klicken Sie auf **Start** , geben Sie **PowerShell** ein, und klicken Sie dann auf **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-131">Click **Start** , type **PowerShell** , and then click **Windows PowerShell**.</span></span>
- <span data-ttu-id="6b3df-132">Klicken Sie im **Start** Menü **Start** auf **Alle Programme** , danach auf **Zubehör** , anschließend auf den Ordner **Windows PowerShell** und schließlich auf **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-132">From the **Start** menu, click **Start** , click **All Programs** , click **Accessories** , click the **Windows PowerShell** folder, and then click **Windows PowerShell**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="6b3df-133">An der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="6b3df-133">At the Command Prompt</span></span>

<span data-ttu-id="6b3df-134">Geben Sie zum Starten von Windows PowerShell in **Cmd.exe** Windows PowerShell oder Windows PowerShell ISE Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6b3df-134">In **cmd.exe** , Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell
```

<span data-ttu-id="6b3df-135">Sie können auch die Parameter des Programms `powershell.exe` verwenden, um die Sitzung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="6b3df-135">You can also use the parameters of the `powershell.exe` program to customize the session.</span></span> <span data-ttu-id="6b3df-136">Weitere Informationen finden Sie unter [PowerShell.exe – Befehlszeilenhilfe](/powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_exe).</span><span class="sxs-lookup"><span data-stu-id="6b3df-136">For more information, see [PowerShell.exe Command-Line Help](/powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_exe).</span></span>

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="6b3df-137">Mit administrativen Berechtigungen (Als Administrator ausführen)</span><span class="sxs-lookup"><span data-stu-id="6b3df-137">With Administrative privileges (Run as administrator)</span></span>

<span data-ttu-id="6b3df-138">Klicken Sie auf **Start** , geben Sie **PowerShell** ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell** , und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-138">Click **Start** , type **PowerShell** , right-click **Windows PowerShell** , and then click **Run as administrator**.</span></span>

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="6b3df-139">Starten von Windows PowerShell ISE unter früheren Versionen von Windows</span><span class="sxs-lookup"><span data-stu-id="6b3df-139">How to Start Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="6b3df-140">Verwenden Sie eine der folgenden Methoden, um Windows PowerShell ISE zu starten:</span><span class="sxs-lookup"><span data-stu-id="6b3df-140">Use any of the following methods to start Windows PowerShell ISE.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="6b3df-141">Über das Startmenü</span><span class="sxs-lookup"><span data-stu-id="6b3df-141">From the Start Menu</span></span>

- <span data-ttu-id="6b3df-142">Klicken Sie auf **Start** , geben Sie **ISE** ein, und klicken Sie dann auf **Windows PowerShell ISE**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-142">Click **Start** , type **ISE** , and then click **Windows PowerShell ISE**.</span></span>
- <span data-ttu-id="6b3df-143">Klicken Sie im **Menü** **Start** auf **Alle Programme** , danach auf **Zubehör** , anschließend auf den Ordner **Windows PowerShell** und schließlich auf **Windows PowerShell ISE**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-143">From the **Start** menu, click **Start** , click **All Programs** , click **Accessories** , click the **Windows PowerShell** folder, and then click **Windows PowerShell ISE**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="6b3df-144">An der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="6b3df-144">At the Command Prompt</span></span>

<span data-ttu-id="6b3df-145">Geben Sie zum Starten von Windows PowerShell in `cmd.exe`, Windows PowerShell oder Windows PowerShell ISE Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6b3df-145">In `cmd.exe`, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell_ISE
```

<span data-ttu-id="6b3df-146">oder</span><span class="sxs-lookup"><span data-stu-id="6b3df-146">or</span></span>

```
ISE
```

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="6b3df-147">Mit administrativen Berechtigungen (Als Administrator ausführen)</span><span class="sxs-lookup"><span data-stu-id="6b3df-147">With Administrative privileges (Run as administrator)</span></span>

<span data-ttu-id="6b3df-148">Klicken Sie auf **Start** , geben Sie **ISE** ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell ISE** , und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-148">Click **Start** , type **ISE** , right-click **Windows PowerShell ISE** , and then click **Run as administrator**.</span></span>

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="6b3df-149">Aktivieren von Windows PowerShell ISE unter früheren Versionen von Windows</span><span class="sxs-lookup"><span data-stu-id="6b3df-149">How to Enable Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="6b3df-150">In Windows PowerShell 4.0 und Windows PowerShell 3.0 ist Windows PowerShell ISE standardmäßig für alle Versionen von Windows aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6b3df-150">In Windows PowerShell 4.0 and Windows PowerShell 3.0, Windows PowerShell ISE is enabled by default on all versions of Windows.</span></span> <span data-ttu-id="6b3df-151">Falls es nicht bereits aktiviert ist, erfolgt die Aktivierung mithilfe von Windows Management Framework 4.0 oder Windows Management Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="6b3df-151">If it isn't already enabled, Windows Management Framework 4.0 or Windows Management Framework 3.0 enables it.</span></span>

<span data-ttu-id="6b3df-152">In Windows PowerShell 2.0 ist Windows PowerShell ISE standardmäßig für Windows 7 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6b3df-152">In Windows PowerShell 2.0, Windows PowerShell ISE is enabled by default on Windows 7.</span></span> <span data-ttu-id="6b3df-153">Allerdings ist es in Windows Server 2008 R2 und Windows Server 2008 ein optionales Feature.</span><span class="sxs-lookup"><span data-stu-id="6b3df-153">However, on Windows Server 2008 R2 and Windows Server 2008, it's an optional feature.</span></span>

<span data-ttu-id="6b3df-154">Gehen Sie wie folgt vor, um Windows PowerShell ISE in Windows PowerShell 2.0 unter Windows Server 2008 R2 oder Windows Server 2008 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6b3df-154">To enable Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server 2008 R2 or Windows Server 2008, use the following procedure.</span></span>

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="6b3df-155">So aktivieren Sie Windows PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="6b3df-155">To enable Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

1. <span data-ttu-id="6b3df-156">Starten Sie den Server-Manager.</span><span class="sxs-lookup"><span data-stu-id="6b3df-156">Start Server Manager.</span></span>
2. <span data-ttu-id="6b3df-157">Klicken Sie auf **Features** und dann auf **Features hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-157">Click **Features** and then click **Add Features**.</span></span>
3. <span data-ttu-id="6b3df-158">Klicken Sie unter „Features auswählen“ auf „Windows PowerShell Integrated Scripting Environment (ISE)“.</span><span class="sxs-lookup"><span data-stu-id="6b3df-158">In Select Features, click Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="starting-the-32-bit-version-of-windows-powershell"></a><span data-ttu-id="6b3df-159">Starten der 32-Bit-Version von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b3df-159">Starting the 32-Bit Version of Windows PowerShell</span></span>

<span data-ttu-id="6b3df-160">Bei der Installation von Windows PowerShell auf einem 64-Bit-Computer wird **Windows PowerShell (x86)** , eine 32-Bit-Version von Windows PowerShell, zusätzlich zur 64-Bit-Version installiert.</span><span class="sxs-lookup"><span data-stu-id="6b3df-160">When you install Windows PowerShell on a 64-bit computer, **Windows PowerShell (x86)** , a 32-bit version of Windows PowerShell is installed in addition to the 64-bit version.</span></span> <span data-ttu-id="6b3df-161">Wenn Sie Windows PowerShell ausführen, wird standardmäßig die 64-Bit-Version ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6b3df-161">When you run Windows PowerShell, the 64-bit version runs by default.</span></span>

<span data-ttu-id="6b3df-162">Es kann jedoch möglicherweise erforderlich sein, **Windows PowerShell (x86)** auszuführen, z. B. wenn Sie ein Modul verwenden, das die 32-Bit-Version verlangt, oder Sie eine Remoteverbindung mit einem 32-Bit-Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="6b3df-162">However, you might occasionally need to run **Windows PowerShell (x86)** , such as when you're using a module that requires the 32-bit version or when you're connecting remotely to a 32-bit computer.</span></span>

<span data-ttu-id="6b3df-163">Wählen Sie eines der folgenden Verfahren, um eine 32-Bit-Version von Windows PowerShell zu starten.</span><span class="sxs-lookup"><span data-stu-id="6b3df-163">To start a 32-bit version of Windows PowerShell, use any of the following procedures.</span></span>

#### <a name="in-windows-serverreg-2012-r2"></a><span data-ttu-id="6b3df-164">Unter Windows Server&reg; 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6b3df-164">In Windows Server&reg; 2012 R2</span></span>

- <span data-ttu-id="6b3df-165">Geben Sie im **Startbildschirm\*\*\*\*Windows PowerShell (x86)** ein.</span><span class="sxs-lookup"><span data-stu-id="6b3df-165">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="6b3df-166">Klicken Sie auf die Kachel **Windows PowerShell x86**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-166">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="6b3df-167">Wählen Sie im **Server-Manager** im Menü **Extras** den Eintrag **Windows PowerShell (x86)** aus.</span><span class="sxs-lookup"><span data-stu-id="6b3df-167">In **Server Manager** , from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="6b3df-168">Bewegen Sie auf dem Desktop den Cursor in die rechte obere Ecke, klicken Sie auf **Suchen** , geben Sie **PowerShell x86** ein, und klicken Sie dann auf **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="6b3df-168">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="6b3df-169">Geben Sie über die Befehlszeile Folgendes ein: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="6b3df-169">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-serverreg-2012"></a><span data-ttu-id="6b3df-170">Unter Windows Server&reg; 2012</span><span class="sxs-lookup"><span data-stu-id="6b3df-170">In Windows Server&reg; 2012</span></span>

- <span data-ttu-id="6b3df-171">Klicken Sie auf **Start** , geben Sie **PowerShell** ein, und klicken Sie dann auf **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-171">On the **Start** screen, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="6b3df-172">Wählen Sie im **Server-Manager** im Menü **Extras** den Eintrag **Windows PowerShell (x86)** aus.</span><span class="sxs-lookup"><span data-stu-id="6b3df-172">In **Server Manager** , from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="6b3df-173">Bewegen Sie auf dem Desktop den Cursor in die rechte obere Ecke, klicken Sie auf **Suchen** , geben Sie **PowerShell** ein, und klicken Sie dann auf **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="6b3df-173">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="6b3df-174">Geben Sie über die Befehlszeile Folgendes ein: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="6b3df-174">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windowsreg-81"></a><span data-ttu-id="6b3df-175">Unter Windows&reg; 8.1</span><span class="sxs-lookup"><span data-stu-id="6b3df-175">In Windows&reg; 8.1</span></span>

- <span data-ttu-id="6b3df-176">Geben Sie im **Startbildschirm\*\*\*\*Windows PowerShell (x86)** ein.</span><span class="sxs-lookup"><span data-stu-id="6b3df-176">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="6b3df-177">Klicken Sie auf die Kachel **Windows PowerShell x86**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-177">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="6b3df-178">Falls Sie die [Remoteserver-Verwaltungstools](https://go.microsoft.com/fwlink/?LinkID=304145) für Windows 8.1 ausführen, können Sie Windows PowerShell x86 auch im Menü **Server Manager Tools** (Server-Managertools) öffnen.</span><span class="sxs-lookup"><span data-stu-id="6b3df-178">If you're running [Remote Server Administration Tools](https://go.microsoft.com/fwlink/?LinkID=304145) for Windows 8.1, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="6b3df-179">Wählen Sie **Windows PowerShell (x86)** aus.</span><span class="sxs-lookup"><span data-stu-id="6b3df-179">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="6b3df-180">Bewegen Sie auf dem Desktop den Cursor in die rechte obere Ecke, klicken Sie auf **Suchen** , geben Sie **PowerShell x86** ein, und klicken Sie dann auf **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="6b3df-180">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="6b3df-181">Geben Sie über die Befehlszeile Folgendes ein: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="6b3df-181">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windowsreg-8"></a><span data-ttu-id="6b3df-182">Unter Windows&reg; 8</span><span class="sxs-lookup"><span data-stu-id="6b3df-182">In Windows&reg; 8</span></span>

- <span data-ttu-id="6b3df-183">Bewegen Sie auf dem Bildschirm **Start** den Cursor in die rechte obere Ecke, klicken Sie auf **Einstellungen** , dann auf **Kacheln** , und bewegen Sie den Schieberegler **Verwaltungstools anzeigen** auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-183">On the **Start** screen, move the cursor to the upper right corner, click **Settings** , click **Tiles** , and then move the **Show Administrative Tools** slider to **Yes**.</span></span> <span data-ttu-id="6b3df-184">Geben Sie dann **PowerShell** ein, und klicken Sie auf **Windows PowerShell (x86)** .</span><span class="sxs-lookup"><span data-stu-id="6b3df-184">Then, type **PowerShell** and click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="6b3df-185">Falls Sie die [Remoteserver-Verwaltungstools](https://www.microsoft.com/download/details.aspx?id=28972) für Windows 8 ausführen, können Sie Windows PowerShell x86 auch im Menü **Server Manager Tools** (Server-Managertools) öffnen.</span><span class="sxs-lookup"><span data-stu-id="6b3df-185">If you're running [Remote Server Administration Tools](https://www.microsoft.com/download/details.aspx?id=28972) for Windows 8, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="6b3df-186">Wählen Sie **Windows PowerShell (x86)** aus.</span><span class="sxs-lookup"><span data-stu-id="6b3df-186">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="6b3df-187">Geben Sie auf dem Bildschirm **Start** oder dem Desktop **PowerShell (x86)** ein, und klicken Sie dann auf **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="6b3df-187">On the **Start** screen or the desktop, type **PowerShell (x86)** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="6b3df-188">Geben Sie über die Befehlszeile Folgendes ein: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="6b3df-188">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>
