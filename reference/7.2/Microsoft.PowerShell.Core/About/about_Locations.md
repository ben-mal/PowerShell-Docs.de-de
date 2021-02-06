---
description: Hier wird beschrieben, wie Sie über den Arbeits Speicherort in PowerShell auf Elemente zugreifen.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_locations?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Locations
ms.openlocfilehash: 4876abe3c651ad2279b85355f2e5e029203b6d4e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602928"
---
# <a name="about_locations"></a>about_Locations

## <a name="short-description"></a>KURZE BESCHREIBUNG
Hier wird beschrieben, wie Sie über den Arbeits Speicherort in PowerShell auf Elemente zugreifen.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Der aktuelle Arbeits Speicherort ist der Standard Speicherort, auf den Befehle zeigen.
Das heißt, dass dies der Speicherort ist, den PowerShell verwendet, wenn Sie keinen expliziten Pfad zu dem Element oder Speicherort bereitstellen, das von dem Befehl betroffen ist. In den meisten Fällen ist der aktuelle Arbeits Speicherort ein Laufwerk, auf das über den PowerShell-Dateisystem Anbieter zugegriffen wird, und in einigen Fällen ein Verzeichnis auf diesem Laufwerk.
Beispielsweise können Sie den aktuellen Arbeits Speicherort auf den folgenden Speicherort festlegen:

```powershell
C:\Program Files\Windows PowerShell
```

Folglich werden alle Befehle von diesem Speicherort verarbeitet, es sei denn, es wird explizit ein anderer Pfad bereitgestellt.

PowerShell verwaltet den aktuellen Arbeits Speicherort für jedes Laufwerk, auch wenn das Laufwerk nicht das aktuelle Laufwerk ist. Dies ermöglicht Ihnen den Zugriff auf Elemente aus dem aktuellen Arbeits Speicherort, indem nur auf das Laufwerk eines anderen Speicher Orts verwiesen wird.
Nehmen Sie beispielsweise an, dass der aktuelle Arbeits Speicherort "C: Windows" lautet \\ . Nehmen Sie nun an, dass Sie den folgenden Befehl verwenden, um den aktuellen Arbeits Speicherort in das Laufwerk "HKLM:" zu ändern:

```powershell
Set-Location HKLM:
```

Obwohl Ihr aktueller Speicherort nun das Registrierungs Laufwerk ist, können Sie weiterhin auf Elemente im Verzeichnis "c: Windows" zugreifen \\ , indem Sie einfach das Laufwerk "c:" verwenden, wie im folgenden Beispiel gezeigt:

```powershell
Get-ChildItem C:
```

PowerShell speichert, dass der aktuelle Arbeits Speicherort für dieses Laufwerk das Windows-Verzeichnis ist, sodass Elemente aus diesem Verzeichnis abgerufen werden. Die Ergebnisse sind identisch, wenn Sie den folgenden Befehl ausgeführt haben:

```powershell
Get-ChildItem C:\Windows
```

In PowerShell können Sie den Get-Location-Befehl verwenden, um den aktuellen Arbeits Speicherort zu bestimmen, und Sie können den Set-Location-Befehl verwenden, um den aktuellen Arbeits Speicherort festzulegen. Der folgende Befehl legt z. b. den aktuellen Arbeits Speicherort auf das Windows-Verzeichnis des Laufwerks C: fest:

```powershell
Set-Location c:\windows
```

Nachdem Sie den aktuellen Arbeits Speicherort festgelegt haben, können Sie weiterhin auf Elemente von anderen Laufwerken zugreifen, indem Sie einfach den Namen des Laufwerks (gefolgt von einem Doppelpunkt) in den Befehl einschließen, wie im folgenden Beispiel gezeigt:

```powershell
Get-ChildItem HKLM:\software
```

Der Beispiel Befehl ruft eine Liste von Elementen im Software Container der HKEY-Hive-Struktur in der Registrierung ab.

Mit PowerShell können Sie auch Sonderzeichen verwenden, um den aktuellen Arbeits Speicherort und seinen übergeordneten Speicherort darzustellen. Um den aktuellen Arbeits Speicherort darzustellen, verwenden Sie einen einzelnen Zeitraum. Um das übergeordnete Element des aktuellen Arbeitsspeicher Orts darzustellen, verwenden Sie zwei Zeiträume. Im folgenden Beispiel wird das System Unterverzeichnis im aktuellen Arbeits Speicherort angegeben:

```powershell
Get-ChildItem .\system
```

Wenn der aktuelle Arbeits Speicherort "C: Windows" ist \\ , gibt dieser Befehl eine Liste aller Elemente im C: \\ Windows-System zurück \\ . Wenn Sie jedoch zwei Zeiträume verwenden, wird das übergeordnete Verzeichnis des aktuellen Arbeitsverzeichnisses verwendet, wie im folgenden Beispiel gezeigt:

```powershell
Get-ChildItem ..\"program files"
```

In diesem Fall werden die beiden Zeiträume von PowerShell als Laufwerk "c:" behandelt, sodass der Befehl alle Elemente im Verzeichnis "c: \\ Program Files" abruft.

Ein Pfad, der mit einem Schrägstrich beginnt, identifiziert einen Pfad vom Stamm des aktuellen Laufwerks. Wenn der aktuelle Arbeits Speicherort z. b. c: \\ Program Files \\ PowerShell lautet, ist der Stamm des Laufwerks c. Aus diesem Grund listet der folgende Befehl alle Elemente im Verzeichnis "C: Windows" auf \\ :

```powershell
Get-ChildItem \windows
```

Wenn Sie keinen Pfad angeben, der mit einem Laufwerks Namen, einem Schrägstrich oder einem Punkt beginnt, wenn Sie den Namen eines Containers oder Elements angeben, wird davon ausgegangen, dass sich der Container bzw. das Element am aktuellen Arbeits Speicherort befindet. Wenn der aktuelle Arbeits Speicherort z. b. "c: Windows" lautet \\ , gibt der folgende Befehl alle Elemente im \\ System Verzeichnis "c: Windows" zurück \\ :

```powershell
Get-ChildItem system
```

Wenn Sie anstelle eines Verzeichnis namens einen Dateinamen angeben, gibt PowerShell Details zu dieser Datei zurück (unter der Voraussetzung, dass sich die Datei im aktuellen Arbeits Speicherort befindet).

## <a name="see-also"></a>SIEHE AUCH

[Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)

[about_Providers](about_Providers.md)

[about_Path_Syntax](about_Path_Syntax.md)

