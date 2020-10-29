---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Erstellen eines benutzerdefinierten Eingabefelds
description: In diesem Artikel erfahren Sie, wie Sie ein benutzerdefiniertes Eingabefeld unter Verwendung der Funktionen zur Formularerstellung von .NET Framework in Windows PowerShell erstellen.
ms.openlocfilehash: 18fba743b169010936d2ea83dca4e95203664fe9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500554"
---
# <a name="creating-a-custom-input-box"></a><span data-ttu-id="b9c12-104">Erstellen eines benutzerdefinierten Eingabefelds</span><span class="sxs-lookup"><span data-stu-id="b9c12-104">Creating a Custom Input Box</span></span>

<span data-ttu-id="b9c12-105">Schreiben Sie ein benutzerdefiniertes graphisches Eingabefeld mit Microsoft .NET Framework-Formularerstellungsfunktionen in Windows PowerShell 3.0 und späteren Versionen.</span><span class="sxs-lookup"><span data-stu-id="b9c12-105">Script a graphical custom input box by using Microsoft .NET Framework form-building features in Windows PowerShell 3.0 and later releases.</span></span>

## <a name="create-a-custom-graphical-input-box"></a><span data-ttu-id="b9c12-106">Erstellen Sie eine benutzerdefiniertes, graphisches Eingabefeld</span><span class="sxs-lookup"><span data-stu-id="b9c12-106">Create a custom, graphical input box</span></span>

<span data-ttu-id="b9c12-107">Kopieren und fügen Sie Folgendes in Windows PowerShell ISE ein, und speichern Sie es als Windows PowerShell-Skript (.ps1).</span><span class="sxs-lookup"><span data-stu-id="b9c12-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Data Entry Form'
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
$label.Text = 'Please enter the information in the space below:'
$form.Controls.Add($label)

$textBox = New-Object System.Windows.Forms.TextBox
$textBox.Location = New-Object System.Drawing.Point(10,40)
$textBox.Size = New-Object System.Drawing.Size(260,20)
$form.Controls.Add($textBox)

$form.Topmost = $true

$form.Add_Shown({$textBox.Select()})
$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $textBox.Text
    $x
}
```

<span data-ttu-id="b9c12-108">Das Skript beginnt mit dem Laden von zwei .NET Framework-Klassen: **System.Drawing** und **System.Windows.Forms** .</span><span class="sxs-lookup"><span data-stu-id="b9c12-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms** .</span></span> <span data-ttu-id="b9c12-109">Sie starten daraufhin eine neue Instanz der .NET Framework-Klasse **System.Windows.Forms.Form** , die ein leeres Formular oder Fenster bereitstellt, zu dem Sie Steuerelemente hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="b9c12-109">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form** ; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object System.Windows.Forms.Form
```

<span data-ttu-id="b9c12-110">Nachdem Sie eine Instanz der Formularklasse erstellt haben, ordnen Sie drei Eigenschaften dieser Klasse Werte zu.</span><span class="sxs-lookup"><span data-stu-id="b9c12-110">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="b9c12-111">**Text.**</span><span class="sxs-lookup"><span data-stu-id="b9c12-111">**Text.**</span></span> <span data-ttu-id="b9c12-112">Dies wird der Titel des Fensters.</span><span class="sxs-lookup"><span data-stu-id="b9c12-112">This becomes the title of the window.</span></span>

- <span data-ttu-id="b9c12-113">**Size.**</span><span class="sxs-lookup"><span data-stu-id="b9c12-113">**Size.**</span></span> <span data-ttu-id="b9c12-114">Dies ist die Größe des Formulars, in Pixeln.</span><span class="sxs-lookup"><span data-stu-id="b9c12-114">This is the size of the form, in pixels.</span></span> <span data-ttu-id="b9c12-115">Das vorstehende Skript erstellt ein Formular mit 300 Pixeln Breite und 200 Pixeln Höhe.</span><span class="sxs-lookup"><span data-stu-id="b9c12-115">The preceding script creates a form that's 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="b9c12-116">**StartingPosition.**</span><span class="sxs-lookup"><span data-stu-id="b9c12-116">**StartingPosition.**</span></span> <span data-ttu-id="b9c12-117">Für diese optionale Eigenschaft ist im Skript oben **CenterScreen** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b9c12-117">This optional property is set to **CenterScreen** in the preceding script.</span></span>
  <span data-ttu-id="b9c12-118">Wenn Sie diese Eigenschaft nicht hinzufügen, wählt Windows eine Position aus, wenn das Formular geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="b9c12-118">If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="b9c12-119">Durch Festlegen der **StartingPosition** auf **CenterScreen** wird das Formular automatisch bei jedem Laden in der Mitte des Bildschirms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9c12-119">By setting the **StartingPosition** to **CenterScreen** , you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Data Entry Form'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="b9c12-120">Als Nächstes erstellen Sie eine Schaltfläche **OK** für Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="b9c12-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="b9c12-121">Legen Sie die Größe und das Verhalten der Schaltfläche **OK** fest.</span><span class="sxs-lookup"><span data-stu-id="b9c12-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="b9c12-122">In diesem Beispiel befindet sich die Schaltfläche 120 Pixel vom oberen Formularrand und 75 Pixel vom linken Rand entfernt.</span><span class="sxs-lookup"><span data-stu-id="b9c12-122">In this example, the button position is 120 pixels from the form's top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="b9c12-123">Die Schaltflächenhöhe beträgt 23 Pixel und die Schaltflächenlänge 75 Pixel.</span><span class="sxs-lookup"><span data-stu-id="b9c12-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="b9c12-124">Das Skript verwendet vordefinierte Windows-Formulartypen zur Bestimmung des Schaltflächenverhaltens.</span><span class="sxs-lookup"><span data-stu-id="b9c12-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="b9c12-125">In entsprechender Weise erstellen Sie eine Schaltfläche **Abbrechen** .</span><span class="sxs-lookup"><span data-stu-id="b9c12-125">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="b9c12-126">Die **Abbrechen** -Schaltfläche ist 120 Pixel vom oberen und 150 Pixel vom linken Rand des Fensters entfernt.</span><span class="sxs-lookup"><span data-stu-id="b9c12-126">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

<span data-ttu-id="b9c12-127">Als nächstes stellen Sie einen Beschriftungstext in Ihrem Fenster bereit, der die Information beschreibt, die Benutzer verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9c12-127">Next, provide label text on your window that describes the information you want users to provide.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please enter the information in the space below:'
$form.Controls.Add($label)
```

<span data-ttu-id="b9c12-128">Fügen Sie das Steuerelement (in diesem Fall ein Textfeld) hinzu, mit dem Benutzer die Informationen bereitstellen, die Sie in Ihrem Beschriftungstext beschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="b9c12-128">Add the control (in this case, a text box) that lets users provide the information you've described in your label text.</span></span> <span data-ttu-id="b9c12-129">Es gibt viele weitere Steuerelemente, die Sie neben Textfeldern anwenden können. Weitere Steuerelemente finden Sie unter [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms) auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="b9c12-129">There are many other controls you can apply besides text boxes; for more controls, see [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms) on MSDN.</span></span>

```powershell
$textBox = New-Object System.Windows.Forms.TextBox
$textBox.Location = New-Object System.Drawing.Point(10,40)
$textBox.Size = New-Object System.Drawing.Size(260,20)
$form.Controls.Add($textBox)
```

<span data-ttu-id="b9c12-130">Legen Sie die Eigenschaft **Topmost** auf **$true** fest, um zu erzwingen, dass das Fenster über anderen geöffneten Fenstern und Dialogfeldern geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="b9c12-130">Set the **Topmost** property to **$true** to force the window to open atop other open windows and dialog boxes.</span></span>

```powershell
$form.Topmost = $true
```

<span data-ttu-id="b9c12-131">Fügen Sie als nächstes diese Codezeile zum Aktivieren des Formulars hinzu, und stellen Sie den Fokus auf das von Ihnen erstellte Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="b9c12-131">Next, add this line of code to activate the form, and set the focus to the text box that you created.</span></span>

```powershell
$form.Add_Shown({$textBox.Select()})
```

<span data-ttu-id="b9c12-132">Fügen Sie die folgende Codezeile hinzu, um das Formular in Windows anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9c12-132">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="b9c12-133">Schließlich weist der Code im **If** -Block Windows an, was mit dem Formular geschehen soll, wenn Benutzer Text im Textfeld bereitstellen, und dann auf die Schaltfläche **OK** klicken oder die **Eingabe** -Taste klicken.</span><span class="sxs-lookup"><span data-stu-id="b9c12-133">Finally, the code inside the **If** block instructs Windows what to do with the form after users provide text in the text box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $textBox.Text
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="b9c12-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9c12-134">See Also</span></span>

- <span data-ttu-id="b9c12-135">[GitHub: Dave Wyatt's WinFormsExampleUpdates](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730941(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b9c12-135">[GitHub: Dave Wyatt's WinFormsExampleUpdates](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730941(v=technet.10))</span></span>
- [<span data-ttu-id="b9c12-136">Windows PowerShell-Tipp der Woche: Erstellen eines benutzerdefinierten Eingabefelds</span><span class="sxs-lookup"><span data-stu-id="b9c12-136">Windows PowerShell Tip of the Week:  Creating a Custom Input Box</span></span>](https://technet.microsoft.com/library/ff730941.aspx)
