---
description: Beschreibt, wie Befehle im Befehlsverlauf ausgeführt und ausgeführt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_history?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_History
ms.openlocfilehash: 8a79690cc409919286d0f14130df72a7fe278010
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220887"
---
# <a name="about-history"></a>Informationen zum Verlauf

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt, wie Befehle im Befehlsverlauf ausgeführt und ausgeführt werden.

## <a name="long-description"></a>Lange Beschreibung

Wenn Sie einen Befehl an der Eingabeaufforderung eingeben, speichert PowerShell den Befehl im Befehlsverlauf. Sie können die Befehle im Verlauf als Datensatz Ihrer Arbeit verwenden. Sie können die Befehle auch abrufen und aus dem Befehlsverlauf ausführen.

PowerShell verfügt über zwei verschiedene Verlaufs Anbieter: den integrierten Verlauf und den vom **psread Line** -Modul verwalteten Verlauf. Die Verläufe werden separat verwaltet, aber beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird.

## <a name="using-the-psreadline-history"></a>Verwenden des psread Line-Verlaufs

Der pslelinienverlauf verfolgt die Befehle, die in allen PowerShell-Sitzungen verwendet werden.
Der Verlauf wird pro Host in eine zentrale Datei geschrieben. Diese Verlaufs Datei ist für alle Sitzungen verfügbar und enthält den bisherigen Verlauf. Der Verlauf wird nicht gelöscht, wenn die Sitzung beendet wird. Außerdem kann dieser Verlauf nicht durch die `*-History` Cmdlets verwaltet werden. Weitere Informationen finden Sie unter [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).

## <a name="using-the-built-in-session-history"></a>Verwenden des integrierten Sitzungs Verlaufs

Der integrierte Verlauf verfolgt nur die Befehle nach, die in der aktuellen Sitzung verwendet werden. Der Verlauf ist für andere Sitzungen nicht verfügbar und wird gelöscht, wenn die Sitzung beendet wird.

### <a name="history-cmdlets"></a>History-Cmdlets

PowerShell verfügt über eine Reihe von Cmdlets, die den Befehlsverlauf verwalten.

| Cmdlet           | Alias  | BESCHREIBUNG                                |
| ---------------- | ------ | ------------------------------------------ |
| `Get-History`    | `h`    | Ruft den Befehlsverlauf ab.                  |
| `Invoke-History` | `r`    | Führt einen Befehl im Befehlsverlauf aus.     |
| `Add-History`    |        | Fügt dem Befehlsverlauf einen Befehl hinzu.     |
| `Clear-History`  | `clhy` | Löscht Befehle aus dem Befehlsverlauf. |

### <a name="keyboard-shortcuts-for-managing-history"></a>Tastenkombinationen zum Verwalten des Verlaufs

In der PowerShell-Konsole können Sie die folgenden Tastenkombinationen verwenden, um den Befehlsverlauf zu verwalten.

- <kbd>Ubirow</kbd> -zeigt den vorherigen Befehl an.
- <kbd>Downpfeil</kbd> : zeigt den nächsten Befehl an.
- <kbd>F7</kbd> -zeigt den Befehlsverlauf an.
- <kbd>ESC</kbd> , um den Verlauf auszublenden.
- <kbd>F8</kbd> -findet einen Befehl. Geben Sie ein oder mehrere Zeichen ein, und drücken Sie <kbd>F8</kbd>. Drücken Sie die nächste Instanz erneut mit <kbd>F8</kbd> .
- <kbd>F9</kbd> -Suchen eines Befehls anhand der Verlaufs-ID. Geben Sie die Verlauf-ID ein, und drücken Sie <kbd>F9</kbd> Drücken Sie <kbd>F7</kbd> , um die ID zu suchen.
- <kbd>#</kbd>`<string>`</kbd><kbd>Tab</kbd> : Durchsuchen Sie den Verlauf nach, `*<string>*` und gibt die letzte Übereinstimmung zurück. Wenn Sie die <kbd>Tab</kbd> -Taste wiederholt drücken, durchläuft Sie die übereinstimmenden Elemente im Verlauf.

> [!NOTE]
> Diese Tastenbindungen werden von der Konsolen Host Anwendung implementiert. Andere Anwendungen, wie z. b. Visual Studio Code oder Windows-Terminal, können unterschiedliche Tastenbindungen aufweisen. Die Bindungen können vom psread Line-Modul überschrieben werden. Psread Line wird automatisch geladen, wenn Sie eine PowerShell-Sitzung starten.
> Wenn psread Line geladen ist, sind <kbd>F7</kbd> und <kbd>F9</kbd> nicht an eine Funktion gebunden. Psread Line bietet keine äquivalente Funktionalität. Weitere Informationen finden Sie unter [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).

### <a name="maximumhistorycount"></a>MaximumHistoryCount

Die Einstellungs `$MaximumHistoryCount` Variable bestimmt die maximale Anzahl von Befehlen, die von PowerShell im Befehlsverlauf gespeichert werden. Der Standardwert lautet
4096.

Mit dem folgenden Befehl werden z. b. die `$MaximumHistoryCount` auf 100-Befehle gesenkt:

```powershell
$MaximumHistoryCount = 100
```

Starten Sie PowerShell neu, um die Einstellung zu übernehmen.

Um den neuen Variablen Wert für alle PowerShell-Sitzungen zu speichern, fügen Sie die Zuweisungsanweisung einem PowerShell-Profil hinzu. Weitere Informationen zu Profilen finden Sie unter [about_Profiles](about_Profiles.md).

Weitere Informationen zur Einstellungs `$MaximumHistoryCount` Variablen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).

### <a name="order-of-commands-in-the-history"></a>Reihenfolge der Befehle im Verlauf

Befehle werden dem Verlauf hinzugefügt, wenn die Ausführung des Befehls abgeschlossen ist, und nicht, wenn der Befehl eingegeben wird. Wenn die Ausführung von Befehlen einige Zeit in Anspruch nimmt oder die Befehle in einer eingefügten Eingabeaufforderung ausgeführt werden, scheinen die Befehle im Verlauf nicht in der richtigen Reihenfolge zu sein. Befehle, die in einer eingefügten Eingabeaufforderung ausgeführt werden, werden nur abgeschlossen, wenn Sie die Eingabe Aufforderungs Ebene beenden.

## <a name="see-also"></a>Weitere Informationen

- [about_Line_Editing](about_Line_Editing.md)
- [about_Preference_Variables](about_Preference_Variables.md)
- [about_Profiles](about_Profiles.md)
- [about_Variables](about_Variables.md)
- [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md)

