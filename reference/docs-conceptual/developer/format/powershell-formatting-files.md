---
title: Windows PowerShell-Formatierungs Dateien | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 54fae12163f8d439c2acc24df17ed140a556cba0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783499"
---
# <a name="windows-powershell-formatting-files"></a>Windows PowerShell-Formatierungsdateien

Windows PowerShell stellt mehrere Formatierungs Dateien (.format.ps1XML) bereit, die sich im Installationsverzeichnis ( `$pshome` ) befinden. Jede dieser Dateien definiert die Standard Anzeige für einen bestimmten Satz von .NET-Objekten. Diese Dateien sollten nie geändert werden. Sie können Sie jedoch als Referenz verwenden, um eigene benutzerdefinierte Formatierungs Dateien zu erstellen.

`Certificate.Format.ps1xml`Definiert die Anzeige von Objekten im Zertifikat Speicher, z. b. x. 509-Zertifikate und Zertifikat Speicher.

`DotNetTypes.Format.ps1xml`Definiert die Anzeige verschiedener .NET-Objekte, z. b. CultureInfo-, FileVersionInfo-und EventLogEntry-Objekte.

`FileSystem.Format.ps1xml`Definiert die Anzeige von Dateisystemobjekten, wie z. b. Datei-und Verzeichnisobjekte.

`Help.Format.ps1xml`Definiert die verschiedenen Sichten, die vom Cmdlet " [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) " verwendet werden, z. b. die detaillierten, vollständigen, Parameter und Beispiel Ansichten.

`PowerShellCore.Format.ps1xml`Definiert die Anzeige der Objekte, die von Windows PowerShell Core-Cmdlets generiert werden, z. b. die von den Cmdlets " [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) " und " [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) " zurückgegebenen Objekte.

`PowerShellTrace.Format.ps1xml`Definiert die Anzeige von Ablauf Verfolgungs Objekten, wie z. b. die, die vom [Trace-Command-](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) Cmdlet generiert werden.

`Registry.Format.ps1xml`Definiert die Anzeige von Registrierungs Objekten, wie z. b. Key-und Entry-Objekte.

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](../cmdlet/writing-a-windows-powershell-cmdlet.md)
