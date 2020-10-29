---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Auswählen von Elementen aus einem Listenfeld
description: In diesem Artikel erfahren Sie, wie Sie ein Listenfeld-Steuerelement unter Verwendung der Funktionen zur Formularerstellung von .NET Framework in Windows PowerShell erstellen.
ms.openlocfilehash: cfd6110a9cfcc3cea891d68d8ce7be5b332a949a
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501047"
---
# <a name="selecting-items-from-a-list-box"></a><span data-ttu-id="f8b04-104">Auswählen von Elementen aus einem Listenfeld</span><span class="sxs-lookup"><span data-stu-id="f8b04-104">Selecting Items from a List Box</span></span>

<span data-ttu-id="f8b04-105">Verwenden Sie Windows PowerShell 3.0 und spätere Versionen zur Erstellung eines Dialogfelds, in dem Benutzer Elemente aus einem Listenfeld-Steuerelement auswählen können.</span><span class="sxs-lookup"><span data-stu-id="f8b04-105">Use Windows PowerShell 3.0 and later releases to create a dialog box that lets users select items from a list box control.</span></span>

## <a name="create-a-list-box-control-and-select-items-from-it"></a><span data-ttu-id="f8b04-106">Erstellen Sie ein Listenfeld-Steuerelement, und wählen Sie Elemente daraus aus</span><span class="sxs-lookup"><span data-stu-id="f8b04-106">Create a list box control, and select items from it</span></span>

<span data-ttu-id="f8b04-107">Kopieren und fügen Sie Folgendes in Windows PowerShell ISE ein, und speichern Sie es als Windows PowerShell-Skript (.ps1).</span><span class="sxs-lookup"><span data-stu-id="f8b04-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'

$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)

$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)

$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80

[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')

$form.Controls.Add($listBox)

$form.Topmost = $true

$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

<span data-ttu-id="f8b04-108">Das Skript beginnt mit dem Laden von zwei .NET Framework-Klassen: **System.Drawing** und **System.Windows.Forms** .</span><span class="sxs-lookup"><span data-stu-id="f8b04-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms** .</span></span> <span data-ttu-id="f8b04-109">Sie starten daraufhin eine neue Instanz der .NET Framework-Klasse **System.Windows.Forms.Form** , die ein leeres Formular oder Fenster bereitstellt, zu dem Sie Steuerelemente hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="f8b04-109">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form** ; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
```

<span data-ttu-id="f8b04-110">Nachdem Sie eine Instanz der Formularklasse erstellt haben, ordnen Sie drei Eigenschaften dieser Klasse Werte zu.</span><span class="sxs-lookup"><span data-stu-id="f8b04-110">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="f8b04-111">**Text.**</span><span class="sxs-lookup"><span data-stu-id="f8b04-111">**Text.**</span></span> <span data-ttu-id="f8b04-112">Dies wird der Titel des Fensters.</span><span class="sxs-lookup"><span data-stu-id="f8b04-112">This becomes the title of the window.</span></span>

- <span data-ttu-id="f8b04-113">**Size.**</span><span class="sxs-lookup"><span data-stu-id="f8b04-113">**Size.**</span></span> <span data-ttu-id="f8b04-114">Dies ist die Größe des Formulars, in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="f8b04-114">This is the size of the form, in pixels.</span></span> <span data-ttu-id="f8b04-115">Das vorstehende Skript erstellt ein Formular mit 300 Pixeln Breite und 200 Pixeln Höhe.</span><span class="sxs-lookup"><span data-stu-id="f8b04-115">The preceding script creates a form that's 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="f8b04-116">**StartingPosition.**</span><span class="sxs-lookup"><span data-stu-id="f8b04-116">**StartingPosition.**</span></span> <span data-ttu-id="f8b04-117">Für diese optionale Eigenschaft ist im Skript oben **CenterScreen** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f8b04-117">This optional property is set to **CenterScreen** in the preceding script.</span></span>
  <span data-ttu-id="f8b04-118">Wenn Sie diese Eigenschaft nicht hinzufügen, wählt Windows eine Position aus, wenn das Formular geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="f8b04-118">If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="f8b04-119">Durch Festlegen der **StartingPosition** auf **CenterScreen** wird das Formular automatisch bei jedem Laden in der Mitte des Bildschirms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8b04-119">By setting the **StartingPosition** to **CenterScreen** , you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="f8b04-120">Als Nächstes erstellen Sie eine Schaltfläche **OK** für Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="f8b04-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="f8b04-121">Legen Sie die Größe und das Verhalten der Schaltfläche **OK** fest.</span><span class="sxs-lookup"><span data-stu-id="f8b04-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="f8b04-122">In diesem Beispiel befindet sich die Schaltfläche 120 Pixel vom oberen Formularrand und 75 Pixel vom linken Rand entfernt.</span><span class="sxs-lookup"><span data-stu-id="f8b04-122">In this example, the button position is 120 pixels from the form's top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="f8b04-123">Die Schaltflächenhöhe beträgt 23 Pixel und die Schaltflächenlänge 75 Pixel.</span><span class="sxs-lookup"><span data-stu-id="f8b04-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="f8b04-124">Das Skript verwendet vordefinierte Windows-Formulartypen zur Bestimmung des Schaltflächenverhaltens.</span><span class="sxs-lookup"><span data-stu-id="f8b04-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

<span data-ttu-id="f8b04-125">In entsprechender Weise erstellen Sie eine Schaltfläche **Abbrechen** .</span><span class="sxs-lookup"><span data-stu-id="f8b04-125">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="f8b04-126">Die **Abbrechen** -Schaltfläche ist 120 Pixel vom oberen und 150 Pixel vom linken Rand des Fensters entfernt.</span><span class="sxs-lookup"><span data-stu-id="f8b04-126">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

<span data-ttu-id="f8b04-127">Als nächstes stellen Sie einen Beschriftungstext in Ihrem Fenster bereit, der die Information beschreibt, die Benutzer verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="f8b04-127">Next, provide label text on your window that describes the information you want users to provide.</span></span> <span data-ttu-id="f8b04-128">In diesem Fall sollen die Benutzer einen Computer auswählen.</span><span class="sxs-lookup"><span data-stu-id="f8b04-128">In this case, you want users to select a computer.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)
```

<span data-ttu-id="f8b04-129">Fügen Sie das Steuerelement (in diesem Fall ein Listenfeld) hinzu, mit dem Benutzer die Informationen bereitstellen, die Sie in Ihrem Beschriftungstext beschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="f8b04-129">Add the control (in this case, a list box) that lets users provide the information you've described in your label text.</span></span> <span data-ttu-id="f8b04-130">Es gibt viele weitere Steuerelemente, die Sie neben Listenfeldern anwenden können. Weitere Steuerelemente finden Sie unter [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms) auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="f8b04-130">There are many other controls you can apply besides list boxes; for more controls, see [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms) on MSDN.</span></span>

```powershell
$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80
```

<span data-ttu-id="f8b04-131">Im nächsten Abschnitt legen Sie die Werte fest, die im Listenfeld für Benutzer angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f8b04-131">In the next section, you specify the values you want the list box to display to users.</span></span>

> [!NOTE]
> <span data-ttu-id="f8b04-132">Das von diesem Skript erstellte Listenfeld erlaubt nur eine Auswahl.</span><span class="sxs-lookup"><span data-stu-id="f8b04-132">The list box created by this script allows only one selection.</span></span> <span data-ttu-id="f8b04-133">Zur Erstellung eines Listenfeld-Steuerelements für eine Mehrfachauswahl legen Sie einen Wert für die **SelectionMode** -Eigenschaft fest, wie hier beschrieben: `$listBox.SelectionMode = 'MultiExtended'`.</span><span class="sxs-lookup"><span data-stu-id="f8b04-133">To create a list box control that allows multiple selections, specify a value for the **SelectionMode** property, similarly to the following: `$listBox.SelectionMode = 'MultiExtended'`.</span></span> <span data-ttu-id="f8b04-134">Weitere Informationen finden Sie unter [Mehrfachauswahl-Listenfelder](Multiple-selection-List-Boxes.md).</span><span class="sxs-lookup"><span data-stu-id="f8b04-134">For more information, see [Multiple-selection List Boxes](Multiple-selection-List-Boxes.md).</span></span>

```powershell
[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')
```

<span data-ttu-id="f8b04-135">Fügen Sie das Listenfeld-Steuerelement zu Ihrem Formular hinzu, um Windows anzuweisen, das Formular beim Öffnen über anderen Fenstern und Dialogfeldern zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f8b04-135">Add the list box control to your form, and instruct Windows to open the form atop other windows and dialog boxes when it's opened.</span></span>

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

<span data-ttu-id="f8b04-136">Fügen Sie die folgende Codezeile hinzu, um das Formular in Windows anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f8b04-136">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="f8b04-137">Schließlich weist der Code im **If** -Block Windows an, was mit dem Formular geschehen soll, wenn Benutzer eine Option aus dem Listenfeld auswählen, und dann auf die Schaltfläche **OK** klicken oder die **Eingabe** -Taste klicken.</span><span class="sxs-lookup"><span data-stu-id="f8b04-137">Finally, the code inside the **If** block instructs Windows what to do with the form after users select an option from the list box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="f8b04-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8b04-138">See Also</span></span>

- [<span data-ttu-id="f8b04-139">GitHub: Dave Wyatt's WinFormsExampleUpdates</span><span class="sxs-lookup"><span data-stu-id="f8b04-139">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="f8b04-140">[Windows PowerShell-Tipp der Woche: Auswählen von Elementen aus einem Listenfeld](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f8b04-140">[Windows PowerShell Tip of the Week:  Selecting Items from a List Box](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10))</span></span>
