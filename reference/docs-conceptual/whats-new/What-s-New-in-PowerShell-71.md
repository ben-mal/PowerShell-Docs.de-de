---
title: Neuerungen in PowerShell 7.1
description: In PowerShell 7.1 veröffentlichte neue Features und Änderungen
ms.date: 12/15/2020
ms.openlocfilehash: 6bbeccd07dd696ee019828bdcd68ce3f6ee627e3
ms.sourcegitcommit: 1628fd2a1f50aec2f31ffb1c451a3ce77c08983c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97577206"
---
# <a name="whats-new-in-powershell-71"></a>Neuerungen in PowerShell 7.1

Am 11. November 2020 wurde die allgemeine Verfügbarkeit von PowerShell 7.1 [angekündigt](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/). Aufbauend auf den in PowerShell 7.0 geschaffenen Grundlagen konzentrierten sich unsere Bemühungen auf in der Community gemeldete Issues und umfassen eine Reihe von Verbesserungen und Korrekturen. Wir engagieren uns dafür, dass PowerShell auch weiterhin eine stabile und leistungsstarke Plattform bleibt.

PowerShell 7.1 umfasst die folgenden Features, Updates und Breaking Changes.

- PSReadLine 2.1.0, einschließlich Predictive IntelliSense
- Veröffentlichung von PowerShell 7.1 im Microsoft Store
- Installerpakete für neue Betriebssystemversionen mit Unterstützung für ARM64 aktualisiert
- Höherstufung von vier neuen experimentellen und zwei experimentellen Features auf Mainstreamfeatures
- Mehrere Breaking Changes zur Verbesserung der Benutzerfreundlichkeit

Eine umfassende Liste der Änderungen finden Sie im [Änderungsprotokoll](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md) im GitHub-Repository.

## <a name="psreadline-210"></a>PSReadLine 2.1.0

Zu PowerShell 7.1 gehört auch PSReadLine 2.1.0. Diese Version enthält Predictive IntelliSense. Weitere Informationen zum Feature Predictive IntelliSense finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/).

## <a name="microsoft-store-installer-package"></a>Microsoft Store-Installerpaket

PowerShell 7.1 wurde im Microsoft Store veröffentlicht. Die PowerShell-Version finden Sie auf der Website von [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) oder in der Store-Anwendung unter Windows.

Vorteile des Microsoft Store-Pakets:

- Direkt in Windows 10 integrierte automatische Updates
- Integration in andere Softwareverteilungsmechanismen wie Intune und SCCM

> [!NOTE]
> Alle in `$PSHOME` gespeicherten Konfigurationseinstellungen auf Systemebene lassen sich nicht ändern. Dies schließt die WSMAN-Konfiguration ein. Dadurch wird verhindert, dass Remotesitzungen eine Verbindung mit auf Store basierenden Installationen von PowerShell herstellen. Konfigurationen auf Benutzerebene und SSH-Remoting werden unterstützt.

## <a name="other-installers"></a>Andere Installer

Weitere aktuelle Informationen zu unterstützten Betriebssystemen und zum Supportlebenszyklus finden Sie unter [PowerShell-Supportlebenszyklus](/powershell/scripting/powershell-support-lifecycle).

Prüfen Sie die Installationsanweisungen für Ihr bevorzugtes Betriebssystem:

- [Windows](/powershell/scripting/install/installing-powershell-core-on-windows)
- [macOS](/powershell/scripting/install/installing-powershell-core-on-macos)
- [Linux](/powershell/scripting/install/installing-powershell-core-on-linux)

Darüber hinaus unterstützt PowerShell 7.1 die ARM32- und ARM64-Varianten von Debian, Ubuntu und ARM64 Alpine Linux.

Wenngleich nicht offiziell unterstützt, hat die Community auch Pakete für [Arch](https://aur.archlinux.org/packages/powershell/) und Kali Linux bereitgestellt.

> [!NOTE]
> Debian ab Version 10, CentOS ab Version 8, Ubuntu 20.04, Alpine und ARM unterstützen WinRM-Remoting zurzeit nicht. Einzelheiten zum Einrichten von SSH-basiertem Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## <a name="experimental-features"></a>Experimentelle Features

Weitere Informationen zu den experimentellen Features finden Sie unter [Verwenden experimenteller Features](../learn/experimental-features.md).

Die folgenden experimentellen Features stellen in diesem Release nun Mainstreamfeatures dar:

- [PSNullConditionalOperators](../learn/experimental-features.md#psnullconditionaloperators)
- [PSUnixFileStat](../learn/experimental-features.md#psunixfilestat)

Die folgenden experimentellen Features wurden in diesem Release hinzugefügt:

- [Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace](../learn/experimental-features.md#microsoftpowershellutilitypsmanagebreakpointsinrunspace)
  - PowerShell 7.1 erweitert dieses experimentelle Feature, um allen `*-PSBreakpoint`-Cmdlets den **Runspace**-Parameter hinzuzufügen. Der **Runspace**-Parameter gibt ein **Runspace**-Objekt an, mit dem im angegebenen Runspace mit Haltepunkt	en interagiert wird.

- [PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution): Dieses Feature ermöglicht es Ihnen, PowerShell-Anbieterpfade an native Befehle zu übergeben, die die PowerShell-Pfadsyntax nicht unterstützen.

- [PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator): Wenn der linke Operand in einer `-replace`-Operatoranweisung keine Zeichenfolge ist, wird dieser Operand in eine Zeichenfolge konvertiert. Wenn das Feature aktiviert ist, werden für die Zeichenfolgenkonvertierung keine Kultureinstellungen verwendet.

- [PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) bildet die Grundlage für die Unterstützung zukünftiger Predictive IntelliSense-Plug-Ins.

## <a name="breaking-changes-and-improvements"></a>Breaking Changes und Verbesserungen

- Fix `$?` darf nicht `$false` sein, wenn der native Befehl in `stderr` schreibt ([#13395](https://github.com/PowerShell/PowerShell/pull/13395))

  Es kommt häufig vor, dass native Befehle ohne die Absicht in `stderr` schreiben, einen Fehler zu melden.
  Mit dieser Änderung wird `$?` nur auf `$false` festgelegt, wenn der native Befehl auch einen Exitcode ungleich null aufweist. Diese Änderung steht in keinem Zusammenhang mit dem experimentellen Feature `PSNotApplyErrorActionToStderr`.

- Veranlassen, dass `$ErrorActionPreference` sich nicht auf die `stderr`-Ausgabe nativer Befehle auswirkt ([#13361](https://github.com/PowerShell/PowerShell/pull/13361))

  Es kommt häufig vor, dass native Befehle ohne die Absicht in `stderr` schreiben, einen Fehler zu melden.
  Mit dieser Änderung wird die `stderr`-Ausgabe weiterhin in **ErrorRecord**-Objekten aufgezeichnet, die Runtime wendet `$ErrorActionPreference` jedoch nicht mehr an, wenn **ErrorRecord** aus einem nativen Befehl stammt.

- `-FromUnixTime` für `Get-Date` in `-UnixTimeSeconds` umbenannt, um die UNIX-Zeiteingabe zuzulassen ([#13084](https://github.com/PowerShell/PowerShell/pull/13084), mit bestem Dank an @aetos382)

  Der `-FromUnixTime`-Parameter wurde während 7.1-preview.2 hinzugefügt. Der Parameter wurde zwecks einer größeren Übereinstimmung mit dem Datentyp umbenannt. Dieser Parameter nimmt einen ganzzahligen Wert, der Datum und Uhrzeit seit dem 1 Januar 1970, 0:00:00, sekundengenau darstellt.

  In diesem Beispiel wird eine Unix-Zeitangabe (dargestellt durch die Anzahl von Sekunden seit dem 1970-01-01 0:00:00) in DateTime konvertiert.

  ```powershell
  Get-Date -UnixTimeSeconds 1577836800

  Wednesday, January 01, 2020 12:00:00 AM
  ```

- Explizit angegebenem benannten Parameter erlauben, denselben über das Splatting von Hashtabellen zu ersetzen (#13162)

  Mit dieser Änderung werden die benannten Parameter aus dem Splatting an das Ende der Parameterliste verschoben, sodass sie erst nach dem Binden aller explizit angegebenen benannten Parameter gebunden werden. Die Parameterbindung für einfache Funktionen löst keinen Fehler aus, wenn ein angegebener benannter Parameter nicht gefunden werden kann. Unbekannte benannte Parameter sind an den `$args`-Parameter der einfachen Funktion gebunden. Durch Verschieben des Splattings an das Ende der Argumentliste wird die Reihenfolge geändert, in der die Parameter in `$args` angezeigt werden.

  Beispiele:

  ```powershell
  function SimpleTest {
      param(
          $Name,
          $Path
      )
      "Name: $Name; Path: $Path; Args: $args"
  }
  ```

  Im vorherigen Verhalten ist **MyPath** das dritte Argument in der Argumentliste und daher nicht an `-Path` gebunden. Aus diesem Grund wird MyPath zusammen mit `Blah = "World"` in $args platziert.

  ```powershell
  PS> $hash = @{ Name = "Hello"; Blah = "World" }
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: ; Args: -Blah: World MyPath
  ```

  Mit dieser Änderung werden die Argumente aus `@hash` an das Ende der Argumentliste verschoben. **MyPath** wird zum ersten Argument in der Liste, sodass es an `-Path` gebunden ist.

  ```powershell
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: MyPath; Args: -Blah: World
  ```

- Umgestaltung des Parameters `-Qualifier` als nicht positionell für `Split-Path` ([#12960](https://github.com/PowerShell/PowerShell/pull/12960), mit bestem Dank an @yecril71pl)

- Auflösung des Arbeitsverzeichnisses als Literalpfad für `Start-Process`, wenn es nicht angegeben wird ([#11946](https://github.com/PowerShell/PowerShell/pull/11946), mit bestem Dank an @NoMoreFood)

- Umgestaltung des Parameters `-OutFile` in Web-Cmdlets, sodass er wie `-LiteralPath` funktioniert ([#11701](https://github.com/PowerShell/PowerShell/pull/11701), mit bestem Dank an @iSazonov)

- Korrektur der Bindung von Zeichenfolgenparametern für numerische Literale des Typs `BigInteger` ([#11634](https://github.com/PowerShell/PowerShell/pull/11634), mit bestem Dank an @vexx32)

- Unter Windows wird mit `Start-Process` eine Prozessumgebung mit allen Umgebungsvariablen der aktuellen Sitzung erstellt, wobei mit `-UseNewEnvironment` eine neue Standardprozessumgebung geschaffen wird ([#10830](https://github.com/PowerShell/PowerShell/pull/10830), mit bestem Dank an @iSazonov)

- Zurückgegebenes Ergebnis nicht in `PSObject` umschließen, wenn `ScriptBlock` in einen Delegaten konvertiert wird ([#10619](https://github.com/PowerShell/PowerShell/pull/10619))

  Wenn `ScriptBlock` in einen Delegattyp konvertiert wird, der im C#-Kontext verwendet werden soll, führt das Umschließen des Ergebnisses in `PSObject` zu unnötigen Problemen:

  - Wenn der Wert in den Rückgabetyp des Delegaten konvertiert wird, wird `PSObject` im Wesentlichen entpackt. `PSObject` ist daher nicht erforderlich.
  - Wenn der Rückgabetyp des Delegaten `object` ist, wird er in `PSObject` umschlossen, was die Verwendung in C#-Code erschwert.

  Nach dieser Änderung entspricht das zurückgegebene Objekt dem zugrunde liegenden Objekt.
