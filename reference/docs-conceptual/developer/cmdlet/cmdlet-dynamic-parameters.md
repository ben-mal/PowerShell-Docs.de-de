---
ms.date: 09/13/2016
ms.topic: reference
title: Dynamische Cmdlet-Parameter
description: Dynamische Cmdlet-Parameter
ms.openlocfilehash: b44dda2354e8b689e419c7bf4deefadfc4edcb07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653421"
---
# <a name="cmdlet-dynamic-parameters"></a>Dynamische Cmdlet-Parameter

Cmdlets können Parameter definieren, die für den Benutzer unter bestimmten Bedingungen verfügbar sind, z. b. wenn das Argument eines anderen Parameters ein bestimmter Wert ist. Diese Parameter werden zur Laufzeit hinzugefügt und als dynamische Parameter bezeichnet, da Sie nur bei Bedarf hinzugefügt werden. Beispielsweise können Sie ein Cmdlet entwerfen, das nur dann mehrere Parameter hinzufügt, wenn ein bestimmter Switch-Parameter angegeben wird.

> [!NOTE]
> Anbieter und PowerShell-Funktionen können auch dynamische Parameter definieren.

## <a name="dynamic-parameters-in-powershell-cmdlets"></a>Dynamische Parameter in PowerShell-Cmdlets

PowerShell verwendet dynamische Parameter in mehreren der Anbieter-Cmdlets. Beispielsweise fügen die `Get-Item` -und- `Get-ChildItem` Cmdlets zur Laufzeit einen **codeSigningCert** -Parameter hinzu, wenn der **path** -Parameter den Pfad des **Zertifikat** Anbieters angibt. Wenn der **path** -Parameter einen Pfad für einen anderen Anbieter angibt, ist der **codeSigningCert** -Parameter nicht verfügbar.

In den folgenden Beispielen wird gezeigt, wie der **codeSigningCert** -Parameter zur Laufzeit hinzugefügt wird, wenn `Get-Item` ausgeführt wird.

In diesem Beispiel hat die PowerShell-Laufzeit den-Parameter hinzugefügt, und das Cmdlet ist erfolgreich.

```powershell
Get-Item -Path cert:\CurrentUser -CodeSigningCert
```

```Output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

In diesem Beispiel wird ein **Dateisystem** Laufwerk angegeben, und es wird ein Fehler zurückgegeben. Die Fehlermeldung gibt an, dass der **codeSigningCert** -Parameter nicht gefunden werden kann.

```powershell
Get-Item -Path C:\ -CodeSigningCert
```

```Output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a>Unterstützung für dynamische Parameter

Um dynamische Parameter zu unterstützen, müssen die folgenden Elemente im Cmdlet-Code enthalten sein.

### <a name="interface"></a>Schnittstelle

[System. Management. Automation. idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters).
Diese Schnittstelle stellt die Methode bereit, die die dynamischen Parameter abruft.

Zum Beispiel:

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

### <a name="method"></a>Methode

[System. Management. Automation. idynamicparameters. getdynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).
Diese Methode ruft das-Objekt ab, das die dynamischen Parameter Definitionen enthält.

Beispiele:

```csharp
 public object GetDynamicParameters()
 {
   if (employee)
   {
     context= new SendGreetingCommandDynamicParameters();
     return context;
   }
   return null;
}
private SendGreetingCommandDynamicParameters context;
```

### <a name="class"></a>Klasse

Eine Klasse, die die dynamischen Parameter definiert, die hinzugefügt werden sollen. Diese Klasse muss ein **Parameter** Attribut für jeden Parameter und alle optionalen **Alias** -und **Validierungs** Attribute enthalten, die vom Cmdlet benötigt werden.

Zum Beispiel:

```csharp
public class SendGreetingCommandDynamicParameters
{
  [Parameter]
  [ValidateSet ("Marketing", "Sales", "Development")]
  public string Department
  {
    get { return department; }
    set { department = value; }
  }
  private string department;
}
```

Ein umfassendes Beispiel für ein Cmdlet, das dynamische Parameter unterstützt, finden [Sie unter deklarieren dynamischer Parameter](./how-to-declare-dynamic-parameters.md).

## <a name="see-also"></a>Siehe auch

[System. Management. Automation. idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters)

[System. Management. Automation. idynamicparameters. getdynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[Deklarieren von dynamischen Parametern](./how-to-declare-dynamic-parameters.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
