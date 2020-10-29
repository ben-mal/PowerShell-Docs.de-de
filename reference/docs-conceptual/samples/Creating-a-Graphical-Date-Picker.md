---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Erstellen einer grafischen Datumsauswahl
description: In diesem Artikel erfahren Sie, wie Sie ein benutzerdefiniertes Steuerelement in der Art eines Kalenders unter Verwendung der Funktionen zur Formularerstellung von .NET Framework in Windows PowerShell erstellen.
ms.openlocfilehash: b73c9ba78817af7c38c20642402752765a7a3674
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500503"
---
# <a name="creating-a-graphical-date-picker"></a><span data-ttu-id="60bc4-104">Erstellen einer grafischen Datumsauswahl</span><span class="sxs-lookup"><span data-stu-id="60bc4-104">Creating a Graphical Date Picker</span></span>

<span data-ttu-id="60bc4-105">Verwenden Sie Windows PowerShell 3.0 und neuere Versionen, um ein Formular mit einem grafischen Kalendersteuerelement zu erstellen, mit dem Benutzer einen Tag des Monats auswählen können.</span><span class="sxs-lookup"><span data-stu-id="60bc4-105">Use Windows PowerShell 3.0 and later releases to create a form with a graphical, calendar-style control that lets users select a day of the month.</span></span>

## <a name="create-a-graphical-date-picker-control"></a><span data-ttu-id="60bc4-106">Erstellen eines grafischen Steuerelements für die Datumsauswahl</span><span class="sxs-lookup"><span data-stu-id="60bc4-106">Create a graphical date-picker control</span></span>

<span data-ttu-id="60bc4-107">Kopieren und fügen Sie Folgendes in Windows PowerShell ISE ein, und speichern Sie es als Windows PowerShell-Skript (.ps1).</span><span class="sxs-lookup"><span data-stu-id="60bc4-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}

$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)

$okButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

$cancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)

$result = $form.ShowDialog()

if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

<span data-ttu-id="60bc4-108">Das Skript beginnt mit dem Laden von zwei .NET Framework-Klassen: **System.Drawing** und **System.Windows.Forms** .</span><span class="sxs-lookup"><span data-stu-id="60bc4-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms** .</span></span> <span data-ttu-id="60bc4-109">Sie starten dann eine neue Instanz der .NET Framework-Klasse **Windows.Forms.Form** . Diese stellt ein leeres Formular oder Fenster bereit, in das Sie Steuerelemente einfügen können.</span><span class="sxs-lookup"><span data-stu-id="60bc4-109">You then start a new instance of the .NET Framework class **Windows.Forms.Form** ; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}
```

<span data-ttu-id="60bc4-110">Dieses Beispiel weist vier Eigenschaften dieser Klasse Werte zu, indem es die Eigenschaft **Property** und die Hashtabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="60bc4-110">This example assigns values to four properties of this class by using the **Property** property and hashtable.</span></span>

1. <span data-ttu-id="60bc4-111">**StartPosition** : Wenn Sie diese Eigenschaft nicht hinzufügen, wählt Windows eine Position aus, wenn das Formular geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="60bc4-111">**StartPosition** : If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="60bc4-112">Durch Festlegen dieser Eigenschaft auf **CenterScreen** wird das Formular automatisch bei jedem Laden in der Mitte des Bildschirms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60bc4-112">By setting this property to **CenterScreen** , you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

2. <span data-ttu-id="60bc4-113">**Size** : Dies ist die Größe des Formulars, in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="60bc4-113">**Size** : This is the size of the form, in pixels.</span></span>
   <span data-ttu-id="60bc4-114">Dieses Skript erstellt ein Formular, das 243 Pixel breit und 230 Pixel hoch ist.</span><span class="sxs-lookup"><span data-stu-id="60bc4-114">The preceding script creates a form that's 243 pixels wide by 230 pixels tall.</span></span>

3. <span data-ttu-id="60bc4-115">**Text** : Dies wird der Titel des Fensters.</span><span class="sxs-lookup"><span data-stu-id="60bc4-115">**Text** : This becomes the title of the window.</span></span>

4. <span data-ttu-id="60bc4-116">**Topmost** : Durch das Festlegen dieser Eigenschaft auf `$true` können Sie erzwingen, dass das Fenster über anderen geöffneten Fenstern und Dialogfeldern geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="60bc4-116">**Topmost** : By setting this property to `$true`, you can force the window to open atop other open windows and dialog boxes.</span></span>

<span data-ttu-id="60bc4-117">Als Nächstes erstellen Sie in Ihrem Formular ein Kalendersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="60bc4-117">Next, create and then add a calendar control in your form.</span></span>
<span data-ttu-id="60bc4-118">In diesem Beispiel wird der aktuelle Tag nicht hervorgehoben oder markiert.</span><span class="sxs-lookup"><span data-stu-id="60bc4-118">In this example, the current day is not highlighted or circled.</span></span>
<span data-ttu-id="60bc4-119">Benutzer können immer nur einen Tag im Kalender auswählen.</span><span class="sxs-lookup"><span data-stu-id="60bc4-119">Users can select only one day on the calendar at one time.</span></span>

```powershell
$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)
```

<span data-ttu-id="60bc4-120">Als Nächstes erstellen Sie eine Schaltfläche **OK** für Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="60bc4-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="60bc4-121">Legen Sie die Größe und das Verhalten der Schaltfläche **OK** fest.</span><span class="sxs-lookup"><span data-stu-id="60bc4-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="60bc4-122">In diesem Beispiel befindet sich die Schaltfläche 165 Pixel vom oberen Formularrand und 38 Pixel vom linken Rand entfernt.</span><span class="sxs-lookup"><span data-stu-id="60bc4-122">In this example, the button position is 165 pixels from the form's top edge, and 38 pixels from the left edge.</span></span> <span data-ttu-id="60bc4-123">Die Schaltflächenhöhe beträgt 23 Pixel und die Schaltflächenlänge 75 Pixel.</span><span class="sxs-lookup"><span data-stu-id="60bc4-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="60bc4-124">Das Skript verwendet vordefinierte Windows-Formulartypen zur Bestimmung des Schaltflächenverhaltens.</span><span class="sxs-lookup"><span data-stu-id="60bc4-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$okButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

<span data-ttu-id="60bc4-125">In entsprechender Weise erstellen Sie eine Schaltfläche **Abbrechen** .</span><span class="sxs-lookup"><span data-stu-id="60bc4-125">Similarly, you create a **Cancel** button.</span></span>
<span data-ttu-id="60bc4-126">Die Position der Schaltfläche **Abbrechen** ist 165 Pixel vom oberen Rand und 113 Pixel vom linken Rand des Fensters entfernt.</span><span class="sxs-lookup"><span data-stu-id="60bc4-126">The **Cancel** button is 165 pixels from the top, but 113 pixels from the left edge of the window.</span></span>

```powershell
$cancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

<span data-ttu-id="60bc4-127">Fügen Sie die folgende Codezeile hinzu, um das Formular in Windows anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60bc4-127">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="60bc4-128">Abschließend weist der Code im Block `if` Windows an, was mit dem Formular geschehen soll, wenn Benutzer einen Tag im Kalender auswählen und anschließend auf die Schaltfläche **OK** klicken oder die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="60bc4-128">Finally, the code inside the `if` block instructs Windows what to do with the form after users select a day on the calendar, and then click the **OK** button or press the **Enter** key.</span></span> <span data-ttu-id="60bc4-129">Windows PowerShell zeigt den Benutzern das ausgewählte Datum an.</span><span class="sxs-lookup"><span data-stu-id="60bc4-129">Windows PowerShell displays the selected date to users.</span></span>

```powershell
if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

## <a name="see-also"></a><span data-ttu-id="60bc4-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60bc4-130">See Also</span></span>

- [<span data-ttu-id="60bc4-131">GitHub: Dave Wyatt's WinFormsExampleUpdates</span><span class="sxs-lookup"><span data-stu-id="60bc4-131">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="60bc4-132">[Windows PowerShell-Tipp der Woche: Erstellen einer grafischen Datumsauswahl](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730942(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="60bc4-132">[Windows PowerShell Tip of the Week:  Creating a Graphical Date Picker](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730942(v=technet.10))</span></span>
