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
# <a name="credential-attribute-declaration"></a><span data-ttu-id="c2527-102">Attributdeklaration: Credential</span><span class="sxs-lookup"><span data-stu-id="c2527-102">Credential Attribute Declaration</span></span>

<span data-ttu-id="c2527-103">Das Anmelde Informationen-Attribut ist ein optionales Attribut, das mit Anmelde Informations Parametern vom Typ " [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) " verwendet werden kann, sodass eine Zeichenfolge auch als Argument an den-Parameter übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="c2527-103">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="c2527-104">Wenn dieses Attribut einer Parameter Deklaration hinzugefügt wird, konvertiert Windows PowerShell die Zeichen folgen Eingabe in ein [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="c2527-104">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="c2527-105">Beispielsweise verwendet das [Get-Credential-](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) Cmdlet dieses Attribut, damit Windows PowerShell das [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) -Objekt generiert, das vom Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c2527-105">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="c2527-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2527-106">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="c2527-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c2527-107">Remarks</span></span>

- <span data-ttu-id="c2527-108">In der Regel wird dieses Attribut von Parametern des Typs [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) verwendet, sodass eine Zeichenfolge auch als Argument an den-Parameter übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="c2527-108">Typically this attribute is used by parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="c2527-109">Wenn ein [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) -Objekt an den-Parameter übergeben wird, führt Windows PowerShell keine Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="c2527-109">When a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="c2527-110">Beim Erstellen des [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) -Objekts verwendet Windows PowerShell den aktuellen Host, um dem Benutzer die entsprechenden Eingabe Aufforderungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c2527-110">When creating the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="c2527-111">Der Standard Host zeigt z. b. eine Eingabeaufforderung für einen Benutzernamen und ein Kennwort an, wenn dieses Attribut verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2527-111">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="c2527-112">Wenn jedoch ein benutzerdefinierter Host verwendet wird, der eine andere Eingabeaufforderung definiert, wird diese Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2527-112">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="c2527-113">Dieses Attribut wird mit dem Parameter-Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2527-113">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="c2527-114">Weitere Informationen zu diesem Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="c2527-114">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="c2527-115">Das Anmelde Informationen-Attribut wird von der [System. Management. Automation. kredentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="c2527-115">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2527-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2527-116">See Also</span></span>

[<span data-ttu-id="c2527-117">Parameteraliase</span><span class="sxs-lookup"><span data-stu-id="c2527-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="c2527-118">Attributdeklaration: Parameter</span><span class="sxs-lookup"><span data-stu-id="c2527-118">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="c2527-119">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c2527-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
