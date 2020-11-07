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
# ConvertFrom-SddlString

## ZUSAMMENFASSUNG
Konvertiert eine SDDL-Zeichenfolge in ein benutzerdefiniertes-Objekt.

## SYNTAX

### Alle

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <AccessRightTypeNames>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `ConvertFrom-SddlString` Cmdlet wird eine Zeichenfolge für die Definitions Sprache der Sicherheits Beschreibung in ein benutzerdefiniertes **pscustomobject** -Objekt mit den folgenden Eigenschaften konvertiert: Owner, Group, diskretionaryacl, SystemAcl und rawdescriptor.

Die Eigenschaften "Owner", "Group", "diskretionaryacl" und "SystemAcl" enthalten eine lesbare Textdarstellung der in einer SDDL-Zeichenfolge angegebenen Zugriffsrechte

Dieses Cmdlet wurde in PowerShell 5,0 eingeführt.

## BEISPIELE

### Beispiel 1: Konvertieren der SDDL für Dateisystem-Zugriffsrechte in ein pscustomobject

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung für den Ordner "c:\Windows" zu erhalten, und speichert Sie in der Variablen.

Der zweite Befehl verwendet das `ConvertFrom-SddlString` Cmdlet, um die Textdarstellung der SDDL-Zeichenfolge zu erhalten, die in der SDDL-Eigenschaft des Objekts enthalten ist, das die Sicherheits Beschreibung darstellt.

### Beispiel 2: Konvertieren von Registrierungs Zugriffsrechten-SDDL in ein pscustomobject

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung für den Schlüssel "HKLM: \ software\microsoft\" zu erhalten, und speichert Sie in der Variablen.

Der zweite Befehl verwendet das `ConvertFrom-SddlString` Cmdlet, um die Textdarstellung der SDDL-Zeichenfolge zu erhalten, die in der SDDL-Eigenschaft des Objekts enthalten ist, das die Sicherheits Beschreibung darstellt.

Er verwendet den- `-Type` Parameter, um anzugeben, dass die SDDL-Zeichenfolge eine Sicherheits Beschreibung für die Registrierung darstellt.

### Beispiel 3: Konvertieren von Registrierungs Zugriffsrechten SDDL in ein pscustomobject mithilfe von ConvertFrom-SddlString mit und ohne den- `-Type` Parameter

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

Der erste Befehl verwendet das `Get-Acl` Cmdlet, um die Sicherheits Beschreibung für den Schlüssel "HKLM: \ software\microsoft\" zu erhalten, und speichert Sie in der Variablen.

Der zweite Befehl verwendet das `ConvertFrom-SddlString` Cmdlet, um die Textdarstellung der SDDL-Zeichenfolge zu erhalten, die in der SDDL-Eigenschaft des Objekts enthalten ist, das die Sicherheits Beschreibung darstellt.

Der- `-Type` Parameter wird nicht verwendet, sodass die angezeigten Zugriffsrechte für das Dateisystem gelten.

Der dritte Befehl verwendet das `ConvertFrom-SddlString` Cmdlet mit dem- `-Type` Parameter, sodass die zurückgegebenen Zugriffsrechte für die Registrierung lauten.

## PARAMETERS

### -SDDL

Gibt die Zeichenfolge an, die die Sicherheits Beschreibung in der SDDL-Syntax darstellt.

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

### -Type

Gibt den Typ der Rechte an, die die SDDL-Zeichenfolge darstellt.

Zulässige Werte für diesen Parameter:

- File System Rights
- RegistryRights
- Activedirectoriyrights
- MutexRights
- SemaphoreRights
- CryptoKeyRights
- EventWaitHandleRights

Standardmäßig verwendet das Cmdlet Dateisystem Rechte.

CryptoKeyRights und activedirector yrights werden in PowerShell Core nicht unterstützt.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine SDDL-Zeichenfolge an übergeben `ConvertFrom-SddlString` .

## AUSGABEN

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

## VERWANDTE LINKS

[Definitions Sprache für Sicherheits Deskriptoren](/windows/win32/secauthz/security-descriptor-definition-language)
