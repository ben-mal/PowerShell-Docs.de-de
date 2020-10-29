---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Listenfelder für Mehrfachauswahl
description: In diesem Artikel erfahren Sie, wie Sie ein Listenfeld-Steuerelement mit Mehrfachauswahl unter Verwendung der Funktionen zur Formularerstellung von .NET Framework in Windows PowerShell erstellen.
ms.openlocfilehash: e11d1f545f748e0503b92c02bc7a101d8014bd96
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500282"
---
# <a name="multiple-selection-list-boxes"></a><span data-ttu-id="f5b25-104">Listenfelder für Mehrfachauswahl</span><span class="sxs-lookup"><span data-stu-id="f5b25-104">Multiple-selection List Boxes</span></span>

<span data-ttu-id="f5b25-105">Verwenden Sie Windows PowerShell 3.0 und höhere Versionen, um ein Listenfeld-Steuerelement für die Mehrfachauswahl in einem benutzerdefinierten Windows-Formular zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5b25-105">Use Windows PowerShell 3.0 and later releases to create a multiple-selection list box control in a custom Windows Form.</span></span>

## <a name="create-list-box-controls-that-allow-multiple-selections"></a><span data-ttu-id="f5b25-106">Erstellen von Listenfeld-Steuerelementen, die Mehrfachauswahl unterstützen</span><span class="sxs-lookup"><span data-stu-id="f5b25-106">Create list box controls that allow multiple selections</span></span>

<span data-ttu-id="f5b25-107">Kopieren und fügen Sie Folgendes in Windows PowerShell ISE ein, und speichern Sie es als Windows PowerShell-Skript (.ps1).</span><span class="sxs-lookup"><span data-stu-id="f5b25-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Data Entry Form'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'

$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Point(75,120)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = 'OK'
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)

$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(150,120)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = 'Cancel'
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)

$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please make a selection from the list below:'
$form.Controls.Add($label)

$listBox = New-Object System.Windows.Forms.Listbox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)

$listBox.SelectionMode = 'MultiExtended'

[void] $listBox.Items.Add('Item 1')
[void] $listBox.Items.Add('Item 2')
[void] $listBox.Items.Add('Item 3')
[void] $listBox.Items.Add('Item 4')
[void] $listBox.Items.Add('Item 5')

$listBox.Height = 70
$form.Controls.Add($listBox)
$form.Topmost = $true

$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItems
    $x
}
```

<span data-ttu-id="f5b25-108">Das Skript beginnt mit dem Laden von zwei .NET Framework-Klassen: **System.Drawing** und **System.Windows.Forms** .</span><span class="sxs-lookup"><span data-stu-id="f5b25-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms** .</span></span> <span data-ttu-id="f5b25-109">Sie starten daraufhin eine neue Instanz der .NET Framework-Klasse **System.Windows.Forms.Form** , die ein leeres Formular oder Fenster bereitstellt, zu dem Sie Steuerelemente hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="f5b25-109">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form** ; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object System.Windows.Forms.Form
```

<span data-ttu-id="f5b25-110">Nachdem Sie eine Instanz der Formularklasse erstellt haben, ordnen Sie drei Eigenschaften dieser Klasse Werte zu.</span><span class="sxs-lookup"><span data-stu-id="f5b25-110">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="f5b25-111">**Text.**</span><span class="sxs-lookup"><span data-stu-id="f5b25-111">**Text.**</span></span> <span data-ttu-id="f5b25-112">Dies wird der Titel des Fensters.</span><span class="sxs-lookup"><span data-stu-id="f5b25-112">This becomes the title of the window.</span></span>

- <span data-ttu-id="f5b25-113">**Size.**</span><span class="sxs-lookup"><span data-stu-id="f5b25-113">**Size.**</span></span> <span data-ttu-id="f5b25-114">Dies ist die Größe des Formulars, in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="f5b25-114">This is the size of the form, in pixels.</span></span> <span data-ttu-id="f5b25-115">Das vorstehende Skript erstellt ein Formular mit 300 Pixeln Breite und 200 Pixeln Höhe.</span><span class="sxs-lookup"><span data-stu-id="f5b25-115">The preceding script creates a form that's 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="f5b25-116">**StartingPosition.**</span><span class="sxs-lookup"><span data-stu-id="f5b25-116">**StartingPosition.**</span></span> <span data-ttu-id="f5b25-117">Für diese optionale Eigenschaft ist im Skript oben **CenterScreen** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f5b25-117">This optional property is set to **CenterScreen** in the preceding script.</span></span> <span data-ttu-id="f5b25-118">Wenn Sie diese Eigenschaft nicht hinzufügen, wählt Windows eine Position aus, wenn das Formular geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="f5b25-118">If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="f5b25-119">Durch Festlegen der **StartingPosition** auf **CenterScreen** wird das Formular automatisch bei jedem Laden in der Mitte des Bildschirms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5b25-119">By setting the **StartingPosition** to **CenterScreen** , you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Data Entry Form'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="f5b25-120">Als Nächstes erstellen Sie eine Schaltfläche **OK** für Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="f5b25-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="f5b25-121">Legen Sie die Größe und das Verhalten der Schaltfläche **OK** fest.</span><span class="sxs-lookup"><span data-stu-id="f5b25-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="f5b25-122">In diesem Beispiel befindet sich die Schaltfläche 120 Pixel vom oberen Formularrand und 75 Pixel vom linken Rand entfernt.</span><span class="sxs-lookup"><span data-stu-id="f5b25-122">In this example, the button position is 120 pixels from the form's top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="f5b25-123">Die Schaltflächenhöhe beträgt 23 Pixel und die Schaltflächenlänge 75 Pixel.</span><span class="sxs-lookup"><span data-stu-id="f5b25-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="f5b25-124">Das Skript verwendet vordefinierte Windows-Formulartypen zur Bestimmung des Schaltflächenverhaltens.</span><span class="sxs-lookup"><span data-stu-id="f5b25-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Size(75,120)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = 'OK'
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="f5b25-125">In entsprechender Weise erstellen Sie eine Schaltfläche **Abbrechen** .</span><span class="sxs-lookup"><span data-stu-id="f5b25-125">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="f5b25-126">Die **Abbrechen** -Schaltfläche ist 120 Pixel vom oberen und 150 Pixel vom linken Rand des Fensters entfernt.</span><span class="sxs-lookup"><span data-stu-id="f5b25-126">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(150,120)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = 'Cancel'
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)
```

<span data-ttu-id="f5b25-127">Als nächstes stellen Sie einen Beschriftungstext in Ihrem Fenster bereit, der die Information beschreibt, die Benutzer verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="f5b25-127">Next, provide label text on your window that describes the information you want users to provide.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please make a selection from the list below:'
$form.Controls.Add($label)
```

<span data-ttu-id="f5b25-128">Fügen Sie das Steuerelement (in diesem Fall ein Listenfeld) hinzu, mit dem Benutzer die Informationen bereitstellen, die Sie in Ihrem Beschriftungstext beschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="f5b25-128">Add the control (in this case, a list box) that lets users provide the information you've described in your label text.</span></span> <span data-ttu-id="f5b25-129">Es gibt viele weitere Steuerelemente, die Sie neben Textfeldern anwenden können. Weitere Steuerelemente finden Sie unter [System.Windows.Forms Namespace](https://msdn.microsoft.com/library/k50ex0x9(v=vs.110).aspx) auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="f5b25-129">There are many other controls you can apply besides text boxes; for more controls, see [System.Windows.Forms Namespace](https://msdn.microsoft.com/library/k50ex0x9(v=vs.110).aspx) on MSDN.</span></span>

```powershell
$listBox = New-Object System.Windows.Forms.Listbox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
```

<span data-ttu-id="f5b25-130">Auf folgende Weise können Sie angeben, dass Sie Benutzern die Auswahl mehrerer Werte in der Liste erlauben möchten.</span><span class="sxs-lookup"><span data-stu-id="f5b25-130">Here's how you specify that you want to allow users to select multiple values from the list.</span></span>

```powershell
$listBox.SelectionMode = 'MultiExtended'
```

<span data-ttu-id="f5b25-131">Im nächsten Abschnitt legen Sie die Werte fest, die im Listenfeld für Benutzer angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f5b25-131">In the next section, you specify the values you want the list box to display to users.</span></span>

```powershell
[void] $listBox.Items.Add('Item 1')
[void] $listBox.Items.Add('Item 2')
[void] $listBox.Items.Add('Item 3')
[void] $listBox.Items.Add('Item 4')
[void] $listBox.Items.Add('Item 5')
```

<span data-ttu-id="f5b25-132">Geben Sie die maximale Höhe des Listenfeld-Steuerelements an.</span><span class="sxs-lookup"><span data-stu-id="f5b25-132">Specify the maximum height of the list box control.</span></span>

```powershell
$listBox.Height = 70
```

<span data-ttu-id="f5b25-133">Fügen Sie das Listenfeld-Steuerelement zu Ihrem Formular hinzu, um Windows anzuweisen, das Formular beim Öffnen über anderen Fenstern und Dialogfeldern zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f5b25-133">Add the list box control to your form, and instruct Windows to open the form atop other windows and dialog boxes when it's opened.</span></span>

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

<span data-ttu-id="f5b25-134">Fügen Sie die folgende Codezeile hinzu, um das Formular in Windows anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f5b25-134">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="f5b25-135">Schließlich weist der Code im **If** -Block Windows an, was mit dem Formular geschehen soll, wenn Benutzer eine oder mehrere Optionen im Listenfeld auswählen und dann auf die Schaltfläche **OK** klicken oder die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="f5b25-135">Finally, the code inside the **If** block instructs Windows what to do with the form after users select one or more options from the list box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItems
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="f5b25-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5b25-136">See Also</span></span>

- [<span data-ttu-id="f5b25-137">Weekend Scripter:  Fixing PowerShell GUI Examples</span><span class="sxs-lookup"><span data-stu-id="f5b25-137">Weekend Scripter:  Fixing PowerShell GUI Examples</span></span>](https://go.microsoft.com/fwlink/?LinkId=506644)
- [<span data-ttu-id="f5b25-138">GitHub: Dave Wyatt's WinFormsExampleUpdates</span><span class="sxs-lookup"><span data-stu-id="f5b25-138">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="f5b25-139">[Windows PowerShell Tip of the Week: Multi-Select List Boxes – And More!](https://technet.microsoft.com/library/ff730950.aspx) (Windows PowerShell-Tipp der Woche zum Thema Listenfelder mit Mehrfachauswahl)</span><span class="sxs-lookup"><span data-stu-id="f5b25-139">[Windows PowerShell Tip of the Week:  Multi-Select List Boxes - And More!](https://technet.microsoft.com/library/ff730950.aspx)</span></span>
