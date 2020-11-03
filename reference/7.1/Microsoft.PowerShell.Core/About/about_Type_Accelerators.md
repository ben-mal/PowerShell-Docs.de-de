---
description: Beschreibt die für .NET Framework-Klassen verfügbaren Type Accelerators.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 05/01/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_accelerators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Accelerators
ms.openlocfilehash: 3c7f7f0d993819da1efbc7ba9f4c26bd2827bc84
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222335"
---
# <a name="about-type-accelerators"></a>Informationen zu typaccelerators

## <a name="short-desription"></a>kurze Beschreibung
Beschreibt die für .NET Framework-Klassen verfügbaren Type Accelerators.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Type Accelerators sind Aliase für .NET Framework-Klassen. Sie ermöglichen den Zugriff auf bestimmte .NET Framework-Klassen, ohne explizit den gesamten Klassennamen eingeben zu müssen. Beispielsweise können Sie die **Aliasattribute** -Klasse von `[System.Management.Automation.AliasAttribute]` auf verkürzen `[Alias]` .

> [!NOTE]
> Alle typacceleratoren müssen immer noch in eckige Klammern () eingeschlossen werden `[]` .

## <a name="available-type-accelerators"></a>Verfügbare typacceleratoren

|        Accelerator          |                           FullClassName                           |
|---------------------------- | ------------------------------------------------------------------- |
|ADSI                         | System. Director yservices. Director yentry                             |
|adsisearcher                 | System. Director yservices. Director ysearcher                          |
|Alias                        | System. Management. Automation. Aliasattribute                         |
|"Zuordnung"         | System. Management. Automation. zuwemptycollectionattribute          |
|"Zuordnung"             | System. Management. Automation. zuwemptystringattribute              |
|AllowNull                    | System. Management. Automation. allownullattribute                     |
|Argumentcompleter            | System. Management. Automation. argumentcompleterattribute             |
|Argumentvervollständigungen          | System. Management. Automation. argumentcompletionsattribute           |
|array                        | System.Array                                                        |
|BIGINT                       | System. Numerics. BigInteger                                          |
|bool                         | System.Boolean                                                      |
|byte                         | System.Byte                                                         |
|char                         | System.Char                                                         |
|cimclass                     | Microsoft. Management. Infrastructure. cimclass                        |
|cimconverter                 | Microsoft. Management. Infrastructure. cimconverter                    |
|ciminstance                  | Microsoft.Management.Infrastructure.CimInstance                     |
|CimSession                   | Microsoft.Management.Infrastructure.CimSession                      |
|CimType                      | Microsoft. Management. Infrastructure. CimType                         |
|CmdletBinding                | System. Management. Automation. cmdletbindingattribute                 |
|CultureInfo                  | System. Globalization. CultureInfo                                    |
|datetime                     | System.DateTime                                                     |
|decimal                      | System.Decimal                                                      |
|double                       | System.Double                                                       |
|DscLocalConfigurationManager | System. Management. Automation. dsclocalconfigurationmanagerattribute  |
|DscProperty                  | System. Management. Automation. dscpropertyattribute                   |
|DscResource                  | System. Management. Automation. dscresourceattribute                   |
|Experiment Aktion             | System. Management. Automation. Experiment Action                       |
|Experimentell                 | System. Management. Automation. ExperimentalAttribute                  |
|Experimentalfeature          | System. Management. Automation. experimentalfeature                    |
|float                        | System.Single                                                       |
|guid                         | System.Guid                                                         |
|Hash Tabelle                    | System.Collections.Hashtable                                        |
|initialsessionstate          | System.Management.Automation.Runspaces.Initialsessionstate          |
|INT                          | System.Int32                                                        |
|int16                        | System.Int16                                                        |
|int32                        | System.Int32                                                        |
|int64                        | System.Int64                                                        |
|IPAddress                    | System .net. IPAddress                                                |
|IPEndPoint                   | System .net. ipdpoint                                               |
|long                         | System.Int64                                                        |
|MailAddress                  | System .net. Mail. MailAddress                                         |
|NULL-Zeichenfolge                   | System. Management. Automation. Language. NullString                    |
|ObjectSecurity               | System. Security. AccessControl. ObjectSecurity                        |
|OutputType                   | System. Management. Automation. outputtypeer Attribute                    |
|Parameter                    | System. Management. Automation. ParameterAttribute                     |
|PhysicalAddress              | System .net. Network Information. PhysicalAddress                       |
|powershell                   | System. Management. Automation. PowerShell                             |
|psaliasproperty              | System. Management. Automation. psaliasproperty                        |
|pscredential                 | System. Management. Automation. PSCredential                           |
|pscustomobject               | System. Management. Automation. psobject                               |
|Psdefaultvalue               | System.Management.Automation.PSDefaultvalueattribute                |
|pslistmodifier               | System. Management. Automation. pslistmodifier                         |
|psmoduleinfo                 | System. Management. Automation. psmoduleinfo                           |
|psnoteproperty               | System. Management. Automation. psnoteproperty                         |
|psobject                     | System. Management. Automation. psobject                               |
|psprientschärvedictionary        | System. Management. Automation. psprientschärvedictionary                  |
|pspropertyexpression         | Microsoft. PowerShell. Commands. pspropertyexpression                  |
|psscriptmethod               | System. Management. Automation. psscriptmethod                         |
|psscriptproperty             | System. Management. Automation. psscriptproperty                       |
|Pstypameattribute          | System. Management. Automation. pstypameattribute                    |
|psvariable                   | System. Management. Automation. psvariable                             |
|psvariableproperty           | System. Management. Automation. psvariableproperty                     |
|ref                          | System. Management. Automation. psreference                            |
|regex                        | System.Text.RegularExpressions.Regex                                |
|Runspace                     | System. Management. Automation. Runspaces. Runspace                     |
|runspacefactory              | System. Management. Automation. Runspaces. runspacefactory              |
|sbyte                        | System.SByte                                                        |
|scriptblock                  | System. Management. Automation. ScriptBlock                            |
|securestring                 | System.Security.SecureString                                        |
|semver                       | System. Management. Automation. semanticversion                        |
|short                        | System.Int16                                                        |
|single                       | System.Single                                                       |
|string                       | System.String                                                       |
|Supportswildcards            | System. Management. Automation. supportswildcardsattribute             |
|switch                       | System.Management.Automation.SwitchParameter                        |
|Zeitraum                     | System.TimeSpan                                                     |
|type                         | System.Type                                                         |
|uint                         | System.UInt32                                                       |
|uint16                       | System.UInt16                                                       |
|uint32                       | System.UInt32                                                       |
|uint64                       | System.UInt64                                                       |
|ulong                        | System.UInt64                                                       |
|uri                          | System.Uri                                                          |
|ushort                       | System.UInt16                                                       |
|Validatecount                | System. Management. Automation. validatezähltattribute                 |
|Validatedrive                | System. Management. Automation. validatedriveattribute                 |
|ValidateLength               | System. Management. Automation. validatelengthattribute                |
|Validatenotnull              | System. Management. Automation. validatenotnullattribute               |
|Validatenotnullorempty       | System. Management. Automation. validatenotnulloremptyattribute        |
|ValidatePattern              | System. Management. Automation. validatepatternattribute               |
|Validaterange                | System. Management. Automation. validaterangeattribute                 |
|Validatescript               | System. Management. Automation. validatescriptattribute                |
|ValidateSet                  | System. Management. Automation. validatesetattribute                   |
|Validatetrusteddata          | System. Management. Automation. validatetrusteddataattribute           |
|Validateuserdrive            | System. Management. Automation. validateuserdriveattribute             |
|version                      | System.Version                                                      |
|void                         | System.Void                                                         |
|Wildcardpattern              | System. Management. Automation. wildcardpattern                        |
|WMI                          | System. Management. ManagementObject                                  |
|WMIClass                     | System. Management. ManagementClass                                   |
|wmisearcher                  | System. Management. ManagementObjectSearcher                          |
|X500DistinguishedName        | System.Security.Cryptography.X509Certificates.X500DistinguishedName |
|X509Certificate              | System.Security.Cryptography.X509Certificates.X509Certificate       |
|Xml                          | System.Xml.XmlDocument                                              |

