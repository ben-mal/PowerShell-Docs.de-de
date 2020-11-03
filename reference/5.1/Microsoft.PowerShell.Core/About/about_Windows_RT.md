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
# <a name="about-windows-rt"></a>Informationen zu Windows RT

## <a name="short-description"></a>KURZE BESCHREIBUNG

Erläutert Einschränkungen von Windows PowerShell 4,0 unter Windows RT 8,1.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Das Betriebssystem Windows RT 8,1 ist auf Computern und Geräten installiert (z. b. Microsoft Surface 2, auf denen es sich um das Betriebssystem des Computers handelt), von dem Advanced RISC Machine (Arm)-Prozessoren verwendet werden.

Windows PowerShell 4,0 ist in Windows RT 8,1 enthalten. Alle-Cmdlets,-Anbieter und-Module sowie die meisten Skripts, die für Windows PowerShell 2,0 und spätere Versionen entworfen wurden, können ohne Änderungen unter Windows RT 8,1 ausgeführt werden.

Da Windows RT 8,1 nicht alle Windows-Features umfasst, funktionieren einige Windows PowerShell-Features anders oder funktionieren nicht auf Windows RT-basierten Geräten. In der folgenden Liste werden die Unterschiede erläutert.

- Windows PowerShell ISE ist nicht in enthalten und kann unter Windows RT 8,1 nicht ausgeführt werden.
  Windows PowerShell ISE erfordert Windows Presentation Foundation, das nicht in Windows RT 8,1 enthalten ist.

- Windows PowerShell-Remoting und der WinRM-Dienst sind standardmäßig deaktiviert.
  Um Remoting zu aktivieren, führen Sie das Enable-PSRemoting-Cmdlet aus. Führen Sie außerdem das Set-Service-Cmdlet aus, um den Starttyp des WinRM-Dienstanbieter auf automatisch oder automatisch (verzögerter Start) festzulegen.

  Während Remoting deaktiviert ist, können Sie Windows PowerShell-Remoting verwenden, um Befehle auf anderen Computern auszuführen, andere Computer können jedoch keine Befehle auf dem Windows RT-Gerät ausführen. Außerdem implizites Remoting, d. h. Remoting, das in ein Cmdlet oder Skript integriert ist, und nicht explizit mit hinzugefügten Parametern angefordert
  - funktioniert nicht in Windows PowerShell, die unter Windows RT 8,1 ausgeführt wird.

- In die Domäne eingebundenes Computing und die Kerberos-Authentifizierung werden unter Windows RT 8,1 nicht unterstützt. Sie können Windows PowerShell nicht verwenden, um diese Features hinzuzufügen oder zu verwalten.

- Microsoft .NET Framework-Klassen, die unter Windows RT 8,1 nicht unterstützt werden, werden von Windows PowerShell unter Windows RT 8,1 ebenfalls nicht unterstützt.

- Transaktionen sind unter Windows RT 8,1 nicht aktiviert. Transaktions-Cmdlets, wie z. b. Start-Transaction, und Transaktions Parameter, wie z. b. UseTransaction, funktionieren nicht ordnungsgemäß.

- Alle Windows PowerShell-Sitzungen auf Windows RT 8,1-Geräten verwenden den einschräninedlanguage-Sprachmodus. Der Modus "einschräninedlanguage" ist ein Begleit Konto für die Benutzermodus-Code Integrität (ENCI). Sie ermöglicht alle Windows-Cmdlets und Windows PowerShell-Sprachelemente, schränkt jedoch die Typen ein, um sicherzustellen, dass Benutzer Windows PowerShell nicht verwenden können, um den umci-Schutz zu umgehen oder zu verletzen

Weitere Informationen zum einschräninedlanguage-Sprachmodus finden Sie unter [about_Language_Modes](about_Language_Modes.md).

## <a name="see-also"></a>SIEHE AUCH

[about_Language_Modes](about_Language_Modes.md)

[about_Remote](about_Remote.md)

[about_Windows_PowerShell_ISE](about_Windows_PowerShell_ISE.md)
