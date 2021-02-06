---
description: Listet die reservierten Wörter auf, die nicht als Bezeichner verwendet werden können, da Sie in PowerShell eine besondere Bedeutung haben.
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_reserved_words?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Reserved_Words
ms.openlocfilehash: 95911e328a50c173235f47a7610393124781555d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603709"
---
# <a name="about-reserved-words"></a>Informationen zu reservierten Wörtern

## <a name="short-description"></a>KURZE BESCHREIBUNG
Listet die reservierten Wörter auf, die nicht als Bezeichner verwendet werden können, da Sie in PowerShell eine besondere Bedeutung haben.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Es gibt bestimmte Wörter, die in PowerShell eine besondere Bedeutung haben. Wenn diese Wörter ohne Anführungszeichen angezeigt werden, versucht PowerShell, ihre besondere Bedeutung anzuwenden, anstatt Sie als Zeichen folgen zu behandeln. Um diese Wörter in einem Befehl oder Skript als Parameter Argumente zu verwenden, ohne Ihre besondere Bedeutung aufzurufen, müssen Sie die reservierten Wörter in Anführungszeichen einschließen.

Im folgenden finden Sie die reservierten Wörter in PowerShell:

```
assembly         exit            process
base             filter          public
begin            finally         return
break            for             sequence
catch            foreach         static
class            from (*)        switch
command          function        throw
configuration    hidden          trap
continue         if              try
data             in              type
define (*)       inlinescript    until
do               interface       using
dynamicparam     module          var (*)
else             namespace       while
elseif           parallel        workflow
end              param
enum             private

(*) These keywords are reserved for future use.
```

Mehrere sprach Schlüsselwörter, einschließlich `Foreach` , `If` , `For` und `While` , verfügen über eigene Hilfeartikel. Um diese anzuzeigen, geben Sie ein, `Get-Help about_` und fügen Sie es hinzu. Um z. b. Informationen zur-Anweisung zu erhalten, geben Sie Folgendes ein `Foreach` :

```powershell
Get-Help about_ForEach
```

Informationen zur- `Filter` Anweisung oder der- `Return` Anweisungs Syntax erhalten Sie, wenn Sie Folgendes eingeben:

```powershell
Get-Help about_Functions
```

Weitere Informationen zu anderen reservierten Wörtern erhalten Sie, wenn Sie Folgendes eingeben:

```powershell
Get-Help <Reserved_Word>
```

> [!NOTE]
> Nicht jedes reservierte Wort hat einen eigenen Hilfeartikel. Wenn keinen `Get-Help` Artikel zurückgibt, können Sie mithilfe des folgenden Befehls nach Artikeln suchen, die über das reservierte Wort sprechen:
>
> ```powershell
> Get-Help <Reserved_Word> -Category:HelpFile
> ```

## <a name="see-also"></a>SIEHE AUCH

- [about_Command_Syntax](about_Command_Syntax.md)
- [about_Language_Keywords](about_Language_Keywords.md)
- [about_Parsing](about_Parsing.md)
- [about_Quoting_Rules](about_Quoting_Rules.md)
- [about_Script_Blocks](about_Script_Blocks.md)
- [about_Special_Characters](about_Special_Characters.md)
