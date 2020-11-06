---
ms.date: 06/12/2017
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Verwenden von Anmeldeinformationen mit DSC-Ressourcen
description: DSC ermöglicht Ihnen, einer Konfiguration Anmeldeinformationen zur Verfügung zu stellen, sodass Konfigurationseinstellungen im Kontext eines bestimmten Benutzerkontos und nicht des lokalen Systemkontos angewendet werden können.
ms.openlocfilehash: e4ca39e099afacd7cb06c4d9ef889f94deb73cee
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645075"
---
# <a name="use-credentials-with-dsc-resources"></a><span data-ttu-id="a8ec2-104">Verwenden von Anmeldeinformationen mit DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="a8ec2-104">Use Credentials with DSC Resources</span></span>

> <span data-ttu-id="a8ec2-105">Gilt für: Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="a8ec2-105">Applies To: Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="a8ec2-106">Sie können eine DSC-Ressource unter einem angegebenen Satz von Anmeldeinformationen ausführen, indem Sie die automatische Eigenschaft **PsDscRunAsCredential** in der Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8ec2-106">You can run a DSC resource under a specified set of credentials by using the automatic **PsDscRunAsCredential** property in the configuration.</span></span> <span data-ttu-id="a8ec2-107">Standardmäßig führt DSC jede Ressource unter dem Systemkonto aus.</span><span class="sxs-lookup"><span data-stu-id="a8ec2-107">By default, DSC runs each resource as the system account.</span></span> <span data-ttu-id="a8ec2-108">Es gibt Situationen, in denen DSC unter einem Benutzerkonto ausgeführt werden muss, z. B. beim Installieren von MSI-Paketen in einem bestimmten Benutzerkontext, beim Festlegen von Registrierungsschlüsseln eines Benutzers, beim Zugriff auf ein bestimmtes lokales Verzeichnis eines Benutzers oder beim Zugriff auf eine Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="a8ec2-108">There are times when running as a user is necessary, such as installing MSI packages in a specific user context, setting a user's registry keys, accessing a user's specific local directory, or accessing a network share.</span></span> <span data-ttu-id="a8ec2-109">Das **SeInteractiveLogonRight** wird vom Zielcomputer für jedes Konto benötigt, das Sie für **PSDSCRunAsCredential** angeben.</span><span class="sxs-lookup"><span data-stu-id="a8ec2-109">The **SeInteractiveLogonRight** is required, by the target machine, for any account you specify to **PSDSCRunAsCredential**.</span></span> <span data-ttu-id="a8ec2-110">Weitere Informationen finden Sie unter [Konstanten für Kontorechte](/windows/desktop/secauthz/account-rights-constants).</span><span class="sxs-lookup"><span data-stu-id="a8ec2-110">For more information, see [Account Rights Constants](/windows/desktop/secauthz/account-rights-constants).</span></span>

<span data-ttu-id="a8ec2-111">Jede DSC-Ressource verfügt über eine **PsDscRunAsCredential** -Eigenschaft, die auf beliebige Anmeldeinformationen festgelegt werden kann (ein [PSCredential](/dotnet/api/system.management.automation.pscredential)-Objekt).</span><span class="sxs-lookup"><span data-stu-id="a8ec2-111">Every DSC resource has a **PsDscRunAsCredential** property that can be set to any user credentials (a [PSCredential](/dotnet/api/system.management.automation.pscredential) object).</span></span> <span data-ttu-id="a8ec2-112">Die Anmeldeinformationen können als Wert der Eigenschaft in der Konfiguration hartcodiert werden, oder Sie können den Wert auf [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) festlegen, wodurch der Benutzer beim Kompilieren der Konfiguration zur Eingabe der Anmeldeinformationen aufgefordert wird (Informationen zum Kompilieren von Konfigurationen finden Sie unter [Konfigurationen](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="a8ec2-112">The credential can be hard-coded as the value of the property in the configuration, or you can set the value to [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential), which will prompt the user for a credential when the configuration is compiled (for information about compiling configurations, see [Configurations](configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a8ec2-113">In PowerShell 5.0 wurde die Verwendung der Eigenschaft **PsDscRunAsCredential** in Konfigurationen, die zusammengesetzte Ressourcen aufrufen, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a8ec2-113">In PowerShell 5.0, using the **PsDscRunAsCredential** property in configurations calling composite resources was not supported.</span></span> <span data-ttu-id="a8ec2-114">In PowerShell 5.1 wird die Eigenschaft **PsDscRunAsCredential** in Konfigurationen, die zusammengesetzte Ressourcen aufrufen, unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a8ec2-114">In PowerShell 5.1, the **PsDscRunAsCredential** property is supported in configurations calling composite resources.</span></span> <span data-ttu-id="a8ec2-115">Die Eigenschaft **PsDscRunAsCredential** ist in PowerShell 4.0 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a8ec2-115">The **PsDscRunAsCredential** property is not available in PowerShell 4.0.</span></span>

<span data-ttu-id="a8ec2-116">Im folgenden Beispiel wird `Get-Credential` verwendet, um den Benutzer zur Eingabe von Anmeldeinformationen aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="a8ec2-116">In the following example, `Get-Credential` is used to prompt the user for credentials.</span></span> <span data-ttu-id="a8ec2-117">Die Ressource **Registry** wird verwendet, um den Registrierungsschlüssel zu ändern, der die Hintergrundfarbe für das Windows-Eingabeaufforderungsfenster angibt.</span><span class="sxs-lookup"><span data-stu-id="a8ec2-117">The **Registry** resource is used to change the registry key that specifies the background color for the Windows command prompt window.</span></span>

```powershell
Configuration ChangeCmdBackGroundColor
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node $AllNodes.NodeName
    {
        Registry CmdPath
        {
            Key                  = 'HKEY_CURRENT_USER\SOFTWARE\Microsoft\Command Processor'
            ValueName            = 'DefaultColor'
            ValueData            = '1F'
            ValueType            = 'DWORD'
            Ensure               = 'Present'
            Force                = $true
            Hex                  = $true
            PsDscRunAsCredential = Get-Credential
        }
    }
}

$configData = @{
    AllNodes = @(
        @{
            NodeName             = 'localhost';
            PSDscAllowDomainUser = $true
            CertificateFile      = 'C:\publicKeys\targetNode.cer'
            Thumbprint           = '7ee7f09d-4be0-41aa-a47f-96b9e3bdec25'
        }
    )
}

ChangeCmdBackGroundColor -ConfigurationData $configData
```

> [!NOTE]
> <span data-ttu-id="a8ec2-118">In diesem Beispiel wird vorausgesetzt, dass Sie über ein gültiges Zertifikat unter `C:\publicKeys\targetNode.cer` verfügen und dass der Fingerabdruck dieses Zertifikats der angezeigte Wert ist.</span><span class="sxs-lookup"><span data-stu-id="a8ec2-118">This example assumes that you have a valid certificate at `C:\publicKeys\targetNode.cer`, and that the thumbprint of that certificate is the value shown.</span></span> <span data-ttu-id="a8ec2-119">Informationen zum Verschlüsseln von Anmeldeinformationen in DSC MOF-Konfigurationsdateien finden Sie unter [Absichern der MOF-Datei](../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="a8ec2-119">For information about encrypting credentials in DSC configuration MOF files, see [Securing the MOF file](../pull-server/secureMOF.md).</span></span>
