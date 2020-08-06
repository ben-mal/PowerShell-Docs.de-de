---
title: Deklaration der Credential-Attribute | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: a6deca52fa6c9e46138ae92401f58ac5dbd15852
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784366"
---
# <a name="credential-attribute-declaration"></a>Attributdeklaration: Credential

Das Anmelde Informationen-Attribut ist ein optionales Attribut, das mit Anmelde Informations Parametern vom Typ " [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) " verwendet werden kann, sodass eine Zeichenfolge auch als Argument an den-Parameter übergeben werden kann. Wenn dieses Attribut einer Parameter Deklaration hinzugefügt wird, konvertiert Windows PowerShell die Zeichen folgen Eingabe in ein [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) -Objekt. Beispielsweise verwendet das [Get-Credential-](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) Cmdlet dieses Attribut, damit Windows PowerShell das [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) -Objekt generiert, das vom Cmdlet zurückgegeben wird.

## <a name="syntax"></a>Syntax

```csharp
[Credential]
```

## <a name="remarks"></a>Bemerkungen

- In der Regel wird dieses Attribut von Parametern des Typs [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) verwendet, sodass eine Zeichenfolge auch als Argument an den-Parameter übergeben werden kann. Wenn ein [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) -Objekt an den-Parameter übergeben wird, führt Windows PowerShell keine Aktion aus.

- Beim Erstellen des [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) -Objekts verwendet Windows PowerShell den aktuellen Host, um dem Benutzer die entsprechenden Eingabe Aufforderungen anzuzeigen. Der Standard Host zeigt z. b. eine Eingabeaufforderung für einen Benutzernamen und ein Kennwort an, wenn dieses Attribut verwendet wird. Wenn jedoch ein benutzerdefinierter Host verwendet wird, der eine andere Eingabeaufforderung definiert, wird diese Eingabeaufforderung angezeigt.

- Dieses Attribut wird mit dem Parameter-Attribut verwendet. Weitere Informationen zu diesem Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).

- Das Anmelde Informationen-Attribut wird von der [System. Management. Automation. kredentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) -Klasse definiert.

## <a name="see-also"></a>Weitere Informationen

[Parameteraliase](./parameter-aliases.md)

[Attributdeklaration: Parameter](./parameter-attribute-declaration.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
