---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: dbb6263c628c08876f64335b420f76d5ecc8f59b
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344370"
---
# <span data-ttu-id="51f16-103">ConvertFrom-SddlString</span><span class="sxs-lookup"><span data-stu-id="51f16-103">ConvertFrom-SddlString</span></span>

## <span data-ttu-id="51f16-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="51f16-104">SYNOPSIS</span></span>
<span data-ttu-id="51f16-105">Konvertiert eine SDDL-Zeichenfolge in ein benutzerdefiniertes-Objekt.</span><span class="sxs-lookup"><span data-stu-id="51f16-105">Converts a SDDL string to a custom object.</span></span>

## <span data-ttu-id="51f16-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="51f16-106">SYNTAX</span></span>

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <Object>] [<CommonParameters>]
```

## <span data-ttu-id="51f16-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="51f16-107">DESCRIPTION</span></span>

<span data-ttu-id="51f16-108">Mit dem- `ConvertFrom-SddlString` Cmdlet wird eine Zeichenfolge für die Definitions Sprache der Sicherheits Beschreibung in ein benutzerdefiniertes **pscustomobject** -Objekt mit den folgenden Eigenschaften konvertiert: Owner, Group, diskretionaryacl, SystemAcl und rawdescriptor.</span><span class="sxs-lookup"><span data-stu-id="51f16-108">The `ConvertFrom-SddlString` cmdlet converts a Security Descriptor Definition Language string to a custom **PSCustomObject** object with the following properties: Owner, Group, DiscretionaryAcl, SystemAcl and RawDescriptor.</span></span>

<span data-ttu-id="51f16-109">Die Eigenschaften "Owner", "Group", "diskretionaryacl" und "SystemAcl" enthalten eine lesbare Textdarstellung der in einer SDDL-Zeichenfolge angegebenen Zugriffsrechte</span><span class="sxs-lookup"><span data-stu-id="51f16-109">Owner, Group, DiscretionaryAcl and SystemAcl properties contain a readable text representation of the access rights specified in a SDDL string.</span></span>

<span data-ttu-id="51f16-110">Dieses Cmdlet wurde in PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="51f16-110">This cmdlet was introduced in PowerShell 5.0.</span></span>

## <span data-ttu-id="51f16-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="51f16-111">EXAMPLES</span></span>

### <span data-ttu-id="51f16-112">Beispiel 1: Konvertieren der SDDL für Dateisystem-Zugriffsrechte in ein pscustomobject</span><span class="sxs-lookup"><span data-stu-id="51f16-112">Example 1: Convert file system access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

<span data-ttu-id="51f16-113">Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung für den Ordner "c:\Windows" zu erhalten, und speichert Sie in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="51f16-113">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the C:\Windows folder and saves it in the variable.</span></span>

<span data-ttu-id="51f16-114">Der zweite Befehl verwendet das `ConvertFrom-SddlString` Cmdlet, um die Textdarstellung der SDDL-Zeichenfolge zu erhalten, die in der SDDL-Eigenschaft des Objekts enthalten ist, das die Sicherheits Beschreibung darstellt.</span><span class="sxs-lookup"><span data-stu-id="51f16-114">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

### <span data-ttu-id="51f16-115">Beispiel 2: Konvertieren von Registrierungs Zugriffsrechten-SDDL in ein pscustomobject</span><span class="sxs-lookup"><span data-stu-id="51f16-115">Example 2: Convert registry access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

<span data-ttu-id="51f16-116">Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung für den Schlüssel "HKLM: \ software\microsoft\" zu erhalten, und speichert Sie in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="51f16-116">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="51f16-117">Der zweite Befehl verwendet das `ConvertFrom-SddlString` Cmdlet, um die Textdarstellung der SDDL-Zeichenfolge zu erhalten, die in der SDDL-Eigenschaft des Objekts enthalten ist, das die Sicherheits Beschreibung darstellt.</span><span class="sxs-lookup"><span data-stu-id="51f16-117">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="51f16-118">Er verwendet den- `-Type` Parameter, um anzugeben, dass die SDDL-Zeichenfolge eine Sicherheits Beschreibung für die Registrierung darstellt.</span><span class="sxs-lookup"><span data-stu-id="51f16-118">It uses the `-Type` parameter to specify that SDDL string represents a registry security descriptor.</span></span>

### <span data-ttu-id="51f16-119">Beispiel 3: Konvertieren von Registrierungs Zugriffsrechten SDDL in ein pscustomobject mithilfe von ConvertFrom-SddlString mit und ohne den- `-Type` Parameter</span><span class="sxs-lookup"><span data-stu-id="51f16-119">Example 3: Convert registry access rights SDDL to a PSCustomObject by using ConvertFrom-SddlString with and without the `-Type` parameter</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

<span data-ttu-id="51f16-120">Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung für den Schlüssel "HKLM: \ software\microsoft\" zu erhalten, und speichert Sie in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="51f16-120">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="51f16-121">Der zweite Befehl verwendet das `ConvertFrom-SddlString` Cmdlet, um die Textdarstellung der SDDL-Zeichenfolge zu erhalten, die in der SDDL-Eigenschaft des Objekts enthalten ist, das die Sicherheits Beschreibung darstellt.</span><span class="sxs-lookup"><span data-stu-id="51f16-121">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="51f16-122">Der- `-Type` Parameter wird nicht verwendet, sodass die angezeigten Zugriffsrechte für das Dateisystem gelten.</span><span class="sxs-lookup"><span data-stu-id="51f16-122">It doesn't use the `-Type` parameter, so the access rights shown are for file system.</span></span>

<span data-ttu-id="51f16-123">Der dritte Befehl verwendet das `ConvertFrom-SddlString` Cmdlet mit dem- `-Type` Parameter, sodass die zurückgegebenen Zugriffsrechte für die Registrierung lauten.</span><span class="sxs-lookup"><span data-stu-id="51f16-123">The third command uses the `ConvertFrom-SddlString` cmdlet with the `-Type` parameter, so the access rights returned are for registry.</span></span>

### <span data-ttu-id="51f16-124">Beispiel 4: Konvertieren der SDDL für Active Directory Zugriffsrechte in ein pscustomobject</span><span class="sxs-lookup"><span data-stu-id="51f16-124">Example 4: Convert Active Directory access rights SDDL to a PSCustomObject</span></span>

```powershell
$user = [ADSI]"LDAP://CN=username,CN=Users,DC=domain,DC=com"
ConvertFrom-SddlString $user.psbase.ObjectSecurity.Sddl -Type ActiveDirectoryRights
```

<span data-ttu-id="51f16-125">Der erste Befehl verwendet Active Directory Service Interfaces (ADSI), um das Benutzerobjekt zu erhalten, und speichert es in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="51f16-125">The first command uses Active Directory Service Interfaces (ADSI) to get the user object and saves it in the variable.</span></span>

<span data-ttu-id="51f16-126">Der zweite Befehl verwendet das `ConvertFrom-SddlString` Cmdlet, um die Textdarstellung der SDDL-Zeichenfolge zu erhalten, die in der SDDL-Eigenschaft des Objekts enthalten ist, das die Sicherheits Beschreibung darstellt.</span><span class="sxs-lookup"><span data-stu-id="51f16-126">The second command uses the `ConvertFrom-SddlString` cmdlet to get text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="51f16-127">Er verwendet den- `-Type` Parameter, um anzugeben, dass die SDDL-Zeichenfolge einen Active Directory Sicherheits Deskriptor darstellt.</span><span class="sxs-lookup"><span data-stu-id="51f16-127">It uses the `-Type` parameter to specify that SDDL string represents an Active Directory security descriptor.</span></span>

## <span data-ttu-id="51f16-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="51f16-128">PARAMETERS</span></span>

### <span data-ttu-id="51f16-129">-SDDL</span><span class="sxs-lookup"><span data-stu-id="51f16-129">-Sddl</span></span>

<span data-ttu-id="51f16-130">Gibt die Zeichenfolge an, die die Sicherheits Beschreibung in der SDDL-Syntax darstellt.</span><span class="sxs-lookup"><span data-stu-id="51f16-130">Specifies the string representing the security descriptor in SDDL syntax.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="51f16-131">-Type</span><span class="sxs-lookup"><span data-stu-id="51f16-131">-Type</span></span>

<span data-ttu-id="51f16-132">Gibt den Typ der Rechte an, die die SDDL-Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="51f16-132">Specifies the type of rights that SDDL string represents.</span></span>

<span data-ttu-id="51f16-133">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="51f16-133">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="51f16-134">File System Rights</span><span class="sxs-lookup"><span data-stu-id="51f16-134">FileSystemRights</span></span>
- <span data-ttu-id="51f16-135">RegistryRights</span><span class="sxs-lookup"><span data-stu-id="51f16-135">RegistryRights</span></span>
- <span data-ttu-id="51f16-136">Activedirectoriyrights</span><span class="sxs-lookup"><span data-stu-id="51f16-136">ActiveDirectoryRights</span></span>
- <span data-ttu-id="51f16-137">MutexRights</span><span class="sxs-lookup"><span data-stu-id="51f16-137">MutexRights</span></span>
- <span data-ttu-id="51f16-138">SemaphoreRights</span><span class="sxs-lookup"><span data-stu-id="51f16-138">SemaphoreRights</span></span>
- <span data-ttu-id="51f16-139">CryptoKeyRights</span><span class="sxs-lookup"><span data-stu-id="51f16-139">CryptoKeyRights</span></span>
- <span data-ttu-id="51f16-140">EventWaitHandleRights</span><span class="sxs-lookup"><span data-stu-id="51f16-140">EventWaitHandleRights</span></span>

<span data-ttu-id="51f16-141">Standardmäßig verwendet das Cmdlet Dateisystem Rechte.</span><span class="sxs-lookup"><span data-stu-id="51f16-141">By default cmdlet uses file system rights.</span></span>

<span data-ttu-id="51f16-142">CryptoKeyRights und activedirector yrights werden in PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51f16-142">CryptoKeyRights and ActiveDirectoryRights are not supported in PowerShell Core.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:
Accepted values: FileSystemRights, RegistryRights, ActiveDirectoryRights, MutexRights, SemaphoreRights, CryptoKeyRights, EventWaitHandleRights

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="51f16-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="51f16-143">CommonParameters</span></span>

<span data-ttu-id="51f16-144">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="51f16-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="51f16-145">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="51f16-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="51f16-146">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="51f16-146">INPUTS</span></span>

### <span data-ttu-id="51f16-147">System.String</span><span class="sxs-lookup"><span data-stu-id="51f16-147">System.String</span></span>

<span data-ttu-id="51f16-148">Sie können eine SDDL-Zeichenfolge an übergeben `ConvertFrom-SddlString` .</span><span class="sxs-lookup"><span data-stu-id="51f16-148">You can pipe a SDDL string to `ConvertFrom-SddlString`.</span></span>

## <span data-ttu-id="51f16-149">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="51f16-149">OUTPUTS</span></span>

## <span data-ttu-id="51f16-150">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="51f16-150">NOTES</span></span>

## <span data-ttu-id="51f16-151">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="51f16-151">RELATED LINKS</span></span>

[<span data-ttu-id="51f16-152">Definitions Sprache für Sicherheits Deskriptoren</span><span class="sxs-lookup"><span data-stu-id="51f16-152">Security Descriptor Definition Language</span></span>](/windows/win32/secauthz/security-descriptor-definition-language)
