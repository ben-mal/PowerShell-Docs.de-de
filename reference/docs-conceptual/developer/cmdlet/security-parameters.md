---
title: Sicherheitsparameter | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 290905b04547af932182005869b18dc1bc210ca4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786508"
---
# <a name="security-parameters"></a>Sicherheitsparameter

In der folgenden Tabelle werden die empfohlenen Namen und Funktionen für Parameter aufgelistet, die zum Bereitstellen von Sicherheitsinformationen für einen Vorgang verwendet werden, z. b. Parameter, die Zertifikat Schlüssel und Berechtigungsinformationen angeben

|Parameter|Funktionalität|
|---|---|
|**ACL**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, um die Zugriffs Steuerungsebene des Schutzes für einen Katalog oder für einen Uniform Resource Identifier (URI) anzugeben.|
|**CertFile**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Namen einer Datei angeben kann, die einen der folgenden Parameter enthält:<br>-Ein Base64-oder Distinguished Encoding Rules (der) codiertes x. 509-Zertifikat<br>-Eine PKCS-#12 Datei (Public Key Cryptography Standards), die mindestens ein Zertifikat und einen Schlüssel enthält|
|**CertIssuerName**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Namen des Ausstellers eines Zertifikats angeben kann oder dass der Benutzer eine Teil Zeichenfolge angeben kann.|
|**Certrequestfile**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, um den Namen einer Datei anzugeben, die eine Base64-oder der-codierte PKCS-#10 Zertifikat Anforderung enthält.|
|**CertSerialNumber**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, um die Seriennummer anzugeben, die von der Zertifizierungsstelle ausgestellt wurde.|
|**CertStoreLocation**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Speicherort des Zertifikat Speicher angeben kann. Der Speicherort ist in der Regel ein Dateipfad.|
|**CertSubjectName**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Aussteller eines Zertifikats angeben kann oder dass der Benutzer eine Teil Zeichenfolge angeben kann.|
|**Certusage**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, um die Schlüssel Verwendung oder die erweiterte Schlüssel Verwendung anzugeben. Der Schlüssel kann als Bitmaske, Bit, Objekt Bezeichner (OID) oder Zeichenfolge dargestellt werden.|
|**Credential**<br>Datentyp: [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential)|Implementieren Sie diesen Parameter, damit das Cmdlet den Benutzer automatisch zur Eingabe eines Benutzernamens oder Kennworts auffordert. Wenn keine vollständigen Anmelde Informationen direkt bereitgestellt werden, wird eine Eingabeaufforderung für beide angezeigt.|
|**CSPName**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Namen des Zertifikat Dienstanbieters (Certificate Service Provider, CSP) angeben kann.|
|**Csptype**<br>Datentyp: Ganzzahl|Implementieren Sie diesen Parameter, sodass der Benutzer den Typ des CSP angeben kann.|
|**Gruppe**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer eine Auflistung von Prinzipale für den Zugriff angeben kann. Weitere Informationen finden Sie in der Beschreibung des **Prinzipal** Parameters.|
|**KeyAlgorithm**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Algorithmus für die Schlüsselgenerierung angeben kann, der für die Sicherheit verwendet werden soll.|
|**KeyContainerName**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Namen des Schlüssel Containers angeben kann.|
|**KeyLength**<br>Datentyp: Ganzzahl|Implementieren Sie diesen Parameter, sodass der Benutzer die Länge des Schlüssels in Bits angeben kann.|
|**Vorgang**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer eine Aktion angeben kann, die für ein geschütztes Objekt ausgeführt werden kann.|
|**Prinzipal**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer eine eindeutige identifizierbare Entität für den Zugriff angeben kann.|
|**Berechtigung**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer die Rechte angeben kann, die ein Cmdlet zum Ausführen eines Vorgangs für eine bestimmte Entität benötigt.|
|**Berechtigungen**<br>Datentyp: Array von Berechtigungen|Implementieren Sie diesen Parameter, sodass der Benutzer die Rechte angeben kann, die ein Cmdlet zum Ausführen des Vorgangs für einen bestimmten Eintrag benötigt.|
|**Rolle**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer eine Reihe von Vorgängen angeben kann, die von einer Entität ausgeführt werden können.|
|**Savecred**<br>Datentyp: Switchparameter|Implementieren Sie diesen Parameter, damit Anmelde Informationen, die zuvor vom Benutzer gespeichert wurden, verwendet werden, wenn der-Parameter angegeben wird.|
|**Umfang**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer die Gruppe der geschützten Objekte für das Cmdlet angeben kann.|
|**SID**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer einen eindeutigen Bezeichner angeben kann, der einen Prinzipal darstellt.|
|**Würdiges**<br>Datentyp: Switchparameter|Implementieren Sie diesen Parameter, damit Vertrauens Ebenen unterstützt werden, wenn der-Parameter angegeben wird.|
|**Trust Level**<br>Datentyp: Schlüsselwort|Implementieren Sie diesen Parameter, sodass der Benutzer die Vertrauens Ebene angeben kann, die unterstützt wird. Mögliche Werte sind z. b. "Internet", "Intranet" und "FullTrust".|

## <a name="see-also"></a>Weitere Informationen

[Cmdlet-Parameter](./cmdlet-parameters.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
