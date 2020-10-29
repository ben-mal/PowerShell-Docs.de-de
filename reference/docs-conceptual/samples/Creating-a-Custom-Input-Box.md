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
# <a name="creating-a-custom-input-box"></a>Erstellen eines benutzerdefinierten Eingabefelds

Schreiben Sie ein benutzerdefiniertes graphisches Eingabefeld mit Microsoft .NET Framework-Formularerstellungsfunktionen in Windows PowerShell 3.0 und späteren Versionen.

## <a name="create-a-custom-graphical-input-box"></a>Erstellen Sie eine benutzerdefiniertes, graphisches Eingabefeld

Kopieren und fügen Sie Folgendes in Windows PowerShell ISE ein, und speichern Sie es als Windows PowerShell-Skript (.ps1).

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

Das Skript beginnt mit dem Laden von zwei .NET Framework-Klassen: **System.Drawing** und **System.Windows.Forms** . Sie starten daraufhin eine neue Instanz der .NET Framework-Klasse **System.Windows.Forms.Form** , die ein leeres Formular oder Fenster bereitstellt, zu dem Sie Steuerelemente hinzufügen können.

```powershell
$form = New-Object System.Windows.Forms.Form
```

Nachdem Sie eine Instanz der Formularklasse erstellt haben, ordnen Sie drei Eigenschaften dieser Klasse Werte zu.

- **Text.** Dies wird der Titel des Fensters.

- **Size.** Dies ist die Größe des Formulars, in Pixeln. Das vorstehende Skript erstellt ein Formular mit 300 Pixeln Breite und 200 Pixeln Höhe.

- **StartingPosition.** Für diese optionale Eigenschaft ist im Skript oben **CenterScreen** festgelegt.
  Wenn Sie diese Eigenschaft nicht hinzufügen, wählt Windows eine Position aus, wenn das Formular geöffnet wird. Durch Festlegen der **StartingPosition** auf **CenterScreen** wird das Formular automatisch bei jedem Laden in der Mitte des Bildschirms angezeigt.

```powershell
$form.Text = 'Data Entry Form'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

Als Nächstes erstellen Sie eine Schaltfläche **OK** für Ihr Formular. Legen Sie die Größe und das Verhalten der Schaltfläche **OK** fest. In diesem Beispiel befindet sich die Schaltfläche 120 Pixel vom oberen Formularrand und 75 Pixel vom linken Rand entfernt. Die Schaltflächenhöhe beträgt 23 Pixel und die Schaltflächenlänge 75 Pixel. Das Skript verwendet vordefinierte Windows-Formulartypen zur Bestimmung des Schaltflächenverhaltens.

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

In entsprechender Weise erstellen Sie eine Schaltfläche **Abbrechen** . Die **Abbrechen** -Schaltfläche ist 120 Pixel vom oberen und 150 Pixel vom linken Rand des Fensters entfernt.

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

Als nächstes stellen Sie einen Beschriftungstext in Ihrem Fenster bereit, der die Information beschreibt, die Benutzer verwenden sollen.

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please enter the information in the space below:'
$form.Controls.Add($label)
```

Fügen Sie das Steuerelement (in diesem Fall ein Textfeld) hinzu, mit dem Benutzer die Informationen bereitstellen, die Sie in Ihrem Beschriftungstext beschrieben haben. Es gibt viele weitere Steuerelemente, die Sie neben Textfeldern anwenden können. Weitere Steuerelemente finden Sie unter [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms) auf MSDN.

```powershell
$textBox = New-Object System.Windows.Forms.TextBox
$textBox.Location = New-Object System.Drawing.Point(10,40)
$textBox.Size = New-Object System.Drawing.Size(260,20)
$form.Controls.Add($textBox)
```

Legen Sie die Eigenschaft **Topmost** auf **$true** fest, um zu erzwingen, dass das Fenster über anderen geöffneten Fenstern und Dialogfeldern geöffnet wird.

```powershell
$form.Topmost = $true
```

Fügen Sie als nächstes diese Codezeile zum Aktivieren des Formulars hinzu, und stellen Sie den Fokus auf das von Ihnen erstellte Textfeld ein.

```powershell
$form.Add_Shown({$textBox.Select()})
```

Fügen Sie die folgende Codezeile hinzu, um das Formular in Windows anzuzeigen.

```powershell
$result = $form.ShowDialog()
```

Schließlich weist der Code im **If** -Block Windows an, was mit dem Formular geschehen soll, wenn Benutzer Text im Textfeld bereitstellen, und dann auf die Schaltfläche **OK** klicken oder die **Eingabe** -Taste klicken.

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $textBox.Text
    $x
}
```

## <a name="see-also"></a>Weitere Informationen

- [GitHub: Dave Wyatt's WinFormsExampleUpdates](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730941(v=technet.10))
- [Windows PowerShell-Tipp der Woche: Erstellen eines benutzerdefinierten Eingabefelds](https://technet.microsoft.com/library/ff730941.aspx)
