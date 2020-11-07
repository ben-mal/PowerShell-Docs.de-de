---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: 6aa820e2f80b7b2b3068a3b6e06bc99e3b5db179
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343588"
---
# <span data-ttu-id="1ac74-103">ConvertFrom-SddlString</span><span class="sxs-lookup"><span data-stu-id="1ac74-103">ConvertFrom-SddlString</span></span>

## <span data-ttu-id="1ac74-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1ac74-104">SYNOPSIS</span></span>
<span data-ttu-id="1ac74-105">Konvertiert eine SDDL-Zeichenfolge in ein benutzerdefiniertes-Objekt.</span><span class="sxs-lookup"><span data-stu-id="1ac74-105">Converts a SDDL string to a custom object.</span></span>

## <span data-ttu-id="1ac74-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1ac74-106">SYNTAX</span></span>

### <span data-ttu-id="1ac74-107">Alle</span><span class="sxs-lookup"><span data-stu-id="1ac74-107">All</span></span>

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <AccessRightTypeNames>] [<CommonParameters>]
```

## <span data-ttu-id="1ac74-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ac74-108">DESCRIPTION</span></span>

<span data-ttu-id="1ac74-109">Mit dem- `ConvertFrom-SddlString` Cmdlet wird eine Zeichenfolge für die Definitions Sprache der Sicherheits Beschreibung in ein benutzerdefiniertes **pscustomobject** -Objekt mit den folgenden Eigenschaften konvertiert: Owner, Group, diskretionaryacl, SystemAcl und rawdescriptor.</span><span class="sxs-lookup"><span data-stu-id="1ac74-109">The `ConvertFrom-SddlString` cmdlet converts a Security Descriptor Definition Language string to a custom **PSCustomObject** object with the following properties: Owner, Group, DiscretionaryAcl, SystemAcl and RawDescriptor.</span></span>

<span data-ttu-id="1ac74-110">Die Eigenschaften "Owner", "Group", "diskretionaryacl" und "SystemAcl" enthalten eine lesbare Textdarstellung der in einer SDDL-Zeichenfolge angegebenen Zugriffsrechte</span><span class="sxs-lookup"><span data-stu-id="1ac74-110">Owner, Group, DiscretionaryAcl and SystemAcl properties contain a readable text representation of the access rights specified in a SDDL string.</span></span>

<span data-ttu-id="1ac74-111">Dieses Cmdlet wurde in PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1ac74-111">This cmdlet was introduced in PowerShell 5.0.</span></span>

## <span data-ttu-id="1ac74-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1ac74-112">EXAMPLES</span></span>

### <span data-ttu-id="1ac74-113">Beispiel 1: Konvertieren der SDDL für Dateisystem-Zugriffsrechte in ein pscustomobject</span><span class="sxs-lookup"><span data-stu-id="1ac74-113">Example 1: Convert file system access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

<span data-ttu-id="1ac74-114">Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung für den Ordner "c:\Windows" zu erhalten, und speichert Sie in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="1ac74-114">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the C:\Windows folder and saves it in the variable.</span></span>

<span data-ttu-id="1ac74-115">Der zweite Befehl verwendet das `ConvertFrom-SddlString` Cmdlet, um die Textdarstellung der SDDL-Zeichenfolge zu erhalten, die in der SDDL-Eigenschaft des Objekts enthalten ist, das die Sicherheits Beschreibung darstellt.</span><span class="sxs-lookup"><span data-stu-id="1ac74-115">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

### <span data-ttu-id="1ac74-116">Beispiel 2: Konvertieren von Registrierungs Zugriffsrechten-SDDL in ein pscustomobject</span><span class="sxs-lookup"><span data-stu-id="1ac74-116">Example 2: Convert registry access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

<span data-ttu-id="1ac74-117">Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung für den Schlüssel "HKLM: \ software\microsoft\" zu erhalten, und speichert Sie in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="1ac74-117">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="1ac74-118">Der zweite Befehl verwendet das `ConvertFrom-SddlString` Cmdlet, um die Textdarstellung der SDDL-Zeichenfolge zu erhalten, die in der SDDL-Eigenschaft des Objekts enthalten ist, das die Sicherheits Beschreibung darstellt.</span><span class="sxs-lookup"><span data-stu-id="1ac74-118">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="1ac74-119">Er verwendet den- `-Type` Parameter, um anzugeben, dass die SDDL-Zeichenfolge eine Sicherheits Beschreibung für die Registrierung darstellt.</span><span class="sxs-lookup"><span data-stu-id="1ac74-119">It uses the `-Type` parameter to specify that SDDL string represents a registry security descriptor.</span></span>

### <span data-ttu-id="1ac74-120">Beispiel 3: Konvertieren von Registrierungs Zugriffsrechten SDDL in ein pscustomobject mithilfe von ConvertFrom-SddlString mit und ohne den- `-Type` Parameter</span><span class="sxs-lookup"><span data-stu-id="1ac74-120">Example 3: Convert registry access rights SDDL to a PSCustomObject by using ConvertFrom-SddlString with and without the `-Type` parameter</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

<span data-ttu-id="1ac74-121">Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung für den Schlüssel "HKLM: \ software\microsoft\" zu erhalten, und speichert Sie in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="1ac74-121">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="1ac74-122">Der zweite Befehl verwendet das `ConvertFrom-SddlString` Cmdlet, um die Textdarstellung der SDDL-Zeichenfolge zu erhalten, die in der SDDL-Eigenschaft des Objekts enthalten ist, das die Sicherheits Beschreibung darstellt.</span><span class="sxs-lookup"><span data-stu-id="1ac74-122">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="1ac74-123">Der- `-Type` Parameter wird nicht verwendet, sodass die angezeigten Zugriffsrechte für das Dateisystem gelten.</span><span class="sxs-lookup"><span data-stu-id="1ac74-123">It doesn't use the `-Type` parameter, so the access rights shown are for file system.</span></span>

<span data-ttu-id="1ac74-124">Der dritte Befehl verwendet das `ConvertFrom-SddlString` Cmdlet mit dem- `-Type` Parameter, sodass die zurückgegebenen Zugriffsrechte für die Registrierung lauten.</span><span class="sxs-lookup"><span data-stu-id="1ac74-124">The third command uses the `ConvertFrom-SddlString` cmdlet with the `-Type` parameter, so the access rights returned are for registry.</span></span>

## <span data-ttu-id="1ac74-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1ac74-125">PARAMETERS</span></span>

### <span data-ttu-id="1ac74-126">-SDDL</span><span class="sxs-lookup"><span data-stu-id="1ac74-126">-Sddl</span></span>

<span data-ttu-id="1ac74-127">Gibt die Zeichenfolge an, die die Sicherheits Beschreibung in der SDDL-Syntax darstellt.</span><span class="sxs-lookup"><span data-stu-id="1ac74-127">Specifies the string representing the security descriptor in SDDL syntax.</span></span>

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

### <span data-ttu-id="1ac74-128">-Type</span><span class="sxs-lookup"><span data-stu-id="1ac74-128">-Type</span></span>

<span data-ttu-id="1ac74-129">Gibt den Typ der Rechte an, die die SDDL-Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="1ac74-129">Specifies the type of rights that SDDL string represents.</span></span>

<span data-ttu-id="1ac74-130">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="1ac74-130">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1ac74-131">File System Rights</span><span class="sxs-lookup"><span data-stu-id="1ac74-131">FileSystemRights</span></span>
- <span data-ttu-id="1ac74-132">RegistryRights</span><span class="sxs-lookup"><span data-stu-id="1ac74-132">RegistryRights</span></span>
- <span data-ttu-id="1ac74-133">Activedirectoriyrights</span><span class="sxs-lookup"><span data-stu-id="1ac74-133">ActiveDirectoryRights</span></span>
- <span data-ttu-id="1ac74-134">MutexRights</span><span class="sxs-lookup"><span data-stu-id="1ac74-134">MutexRights</span></span>
- <span data-ttu-id="1ac74-135">SemaphoreRights</span><span class="sxs-lookup"><span data-stu-id="1ac74-135">SemaphoreRights</span></span>
- <span data-ttu-id="1ac74-136">CryptoKeyRights</span><span class="sxs-lookup"><span data-stu-id="1ac74-136">CryptoKeyRights</span></span>
- <span data-ttu-id="1ac74-137">EventWaitHandleRights</span><span class="sxs-lookup"><span data-stu-id="1ac74-137">EventWaitHandleRights</span></span>

<span data-ttu-id="1ac74-138">Standardmäßig verwendet das Cmdlet Dateisystem Rechte.</span><span class="sxs-lookup"><span data-stu-id="1ac74-138">By default cmdlet uses file system rights.</span></span>

<span data-ttu-id="1ac74-139">CryptoKeyRights und activedirector yrights werden in PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1ac74-139">CryptoKeyRights and ActiveDirectoryRights are not supported in PowerShell Core.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ConvertFromSddlStringCommand+AccessRightTypeNames
Parameter Sets: (All)
Aliases:
Accepted values: FileSystemRights, RegistryRights, ActiveDirectoryRights, MutexRights, SemaphoreRights, CryptoKeyRights, EventWaitHandleRights

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1ac74-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1ac74-140">CommonParameters</span></span>

<span data-ttu-id="1ac74-141">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1ac74-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1ac74-142">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1ac74-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1ac74-143">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1ac74-143">INPUTS</span></span>

### <span data-ttu-id="1ac74-144">System.String</span><span class="sxs-lookup"><span data-stu-id="1ac74-144">System.String</span></span>

<span data-ttu-id="1ac74-145">Sie können eine SDDL-Zeichenfolge an übergeben `ConvertFrom-SddlString` .</span><span class="sxs-lookup"><span data-stu-id="1ac74-145">You can pipe a SDDL string to `ConvertFrom-SddlString`.</span></span>

## <span data-ttu-id="1ac74-146">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1ac74-146">OUTPUTS</span></span>

## <span data-ttu-id="1ac74-147">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1ac74-147">NOTES</span></span>

<span data-ttu-id="1ac74-148">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1ac74-148">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="1ac74-149">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1ac74-149">RELATED LINKS</span></span>

[<span data-ttu-id="1ac74-150">Definitions Sprache für Sicherheits Deskriptoren</span><span class="sxs-lookup"><span data-stu-id="1ac74-150">Security Descriptor Definition Language</span></span>](/windows/win32/secauthz/security-descriptor-definition-language)
