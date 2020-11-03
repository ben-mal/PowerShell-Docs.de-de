---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-webserviceproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WebServiceProxy
ms.openlocfilehash: aea656bc8ad4416673a7abb7d32a58d45dd3cc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214599"
---
# New-WebServiceProxy

## ZUSAMMENFASSUNG
Erstellt ein Webdienst Proxy-Objekt, mit dem Sie den Webdienst in PowerShell verwenden und verwalten können.

## SYNTAX

### Noanmelde Informationen (Standard)

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [<CommonParameters>]
```

### Anmeldeinformationen

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### UseDefaultCredential

```
New-WebServiceProxy [-Uri] <Uri> [[-Class] <String>] [[-Namespace] <String>] [-UseDefaultCredential]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `New-WebServiceProxy` Cmdlet können Sie einen Webdienst in PowerShell verwenden. Das-Cmdlet stellt eine Verbindung mit einem Webdienst her und erstellt ein Webdienst Proxy-Objekt in PowerShell. Sie können den Webdienst mithilfe des Proxyobjekts verwalten.

Ein Webdienst ist ein XML-basiertes Programm, das Daten über ein Netzwerk austauscht, insbesondere über das Internet. Microsoft .NET Framework stellt Webdienstproxyobjekte bereit, die den Webdienst als .NET Framework-Objekt darstellen.

## BEISPIELE

### Beispiel 1: Erstellen eines Proxys für einen Webdienst

In diesem Beispiel wird ein .NET Framework Proxy des Rechner-Webdiensts in Windows PowerShell erstellt.

```powershell
$calc = New-WebServiceProxy -Uri "http://www.dneonline.com/calculator.asmx?wsdl"
```

### Beispiel 2: Erstellen eines Proxys für einen Webdienst und Angeben von Namespace und Klasse

In diesem Beispiel wird das- `New-WebServiceProxy` Cmdlet zum Erstellen eines .NET Framework Proxys des Rechner-Webdiensts verwendet.

```powershell
$URI = "http://www.dneonline.com/calculator.asmx?wsdl"
$calc = New-WebServiceProxy -Uri $URI -Namespace "WSProxy" -Class "Calculator"
```

Der Befehl verwendet den **URI** -Parameter, um den URI und den **Namespace** und die **Klassen** Parameter anzugeben, um den Namespace und die Klasse des Objekts anzugeben.

### Beispiel 3: Anzeigen von Methoden eines Webdienst Proxys

```powershell
$calc | Get-Member -MemberType method
```

```Output
   TypeName: WSProxy.Calculator

Name                      MemberType Definition
----                      ---------- ----------
Abort                     Method     void Abort()
Add                       Method     int Add(int intA, int intB)
AddAsync                  Method     void AddAsync(int intA, int intB), void AddAsync(int intA,
BeginAdd                  Method     System.IAsyncResult BeginAdd(int intA, int intB, System.Asy
BeginDivide               Method     System.IAsyncResult BeginDivide(int intA, int intB, System.
BeginMultiply             Method     System.IAsyncResult BeginMultiply(int intA, int intB, Syste
BeginSubtract             Method     System.IAsyncResult BeginSubtract(int intA, int intB, Syste
CancelAsync               Method     void CancelAsync(System.Object userState)
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type requestedT
Discover                  Method     void Discover()
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Divide                    Method     int Divide(int intA, int intB)
DivideAsync               Method     void DivideAsync(int intA, int intB), void DivideAsync(int
EndAdd                    Method     int EndAdd(System.IAsyncResult asyncResult)
EndDivide                 Method     int EndDivide(System.IAsyncResult asyncResult)
EndMultiply               Method     int EndMultiply(System.IAsyncResult asyncResult)
EndSubtract               Method     int EndSubtract(System.IAsyncResult asyncResult)
Equals                    Method     bool Equals(System.Object obj)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Multiply                  Method     int Multiply(int intA, int intB)
MultiplyAsync             Method     void MultiplyAsync(int intA, int intB), void MultiplyAsync(
Subtract                  Method     int Subtract(int intA, int intB)
SubtractAsync             Method     void SubtractAsync(int intA, int intB), void SubtractAsync(
ToString                  Method     string ToString()
```

In diesem Beispiel wird das- `Get-Member` Cmdlet verwendet, um die Methoden des Webdienst Proxy Objekts in der `$calc` Variablen anzuzeigen. Diese Methoden werden im folgenden Beispiel verwendet.

Beachten Sie, dass der **Typname** des Proxy Objekts (WebServiceProxy) die Namespace-und Klassennamen darstellt, die im vorherigen Beispiel angegeben wurden.

### Beispiel 4: Verwenden eines Webdienst Proxys

```powershell
PS> $calc.Multiply(6,7)
42
```

In diesem Beispiel wird der in der-Variablen gespeicherte Webdienst Proxy verwendet `$calc` . Der Befehl verwendet die **Multiplikations** Methode des Proxys.

## PARAMETERS

### -Klasse

Gibt einen Namen für die Proxyklasse an, die das Cmdlet für den Webdienst erstellt. Der Wert dieses Parameters wird in Verbindung mit dem **Namespace** -Parameter verwendet, um einen voll qualifizierten Namen für die Klasse bereitzustellen. Der Standardwert wird aus dem Uniform Resource Identifier (URI) generiert.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FileName, FN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer. Dies stellt eine Alternative zum Verwenden des **UseDefaultCredential** -Parameters dar.

Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt. Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Credential
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Gibt einen Namespace für die neue Klasse an.

Der Wert dieses Parameters wird mit dem Wert des **Class** -Parameters verwendet, um einen voll qualifizierten Namen für die Klasse zu generieren. Der Standardwert ist **Microsoft. PowerShell. Commands. newwebserviceproxy. autogeneratedtypes** und ein Typ, der aus dem URI generiert wird.

Sie können den Wert des **Namespace** -Parameters so festlegen, dass Sie auf mehrere Webdienste mit demselben Namen zugreifen können.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -URI

Gibt den URI des Webdiensts an. Geben Sie einen URI oder den Pfad und Dateinamen einer Datei ein, die eine Dienst Beschreibung enthält.

Der URI muss eine `.asmx` Seite oder eine Seite zurückgeben, die eine Dienst Beschreibung zurückgibt. Fügen Sie zum Zurückgeben einer Dienst Beschreibung eines Webdiensts, der mit ASP.NET erstellt wurde, "? WSDL "an die URL des Webdiensts (z. b `http://www.contoso.com/MyWebService.asmx?WSDL` .).

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: WL, WSDL, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usedefaultcredential

Gibt an, dass dieses Cmdlet die Standard Anmelde Informationen verwendet. Mit diesem Cmdlet wird die **usedefaultcredential** -Eigenschaft des resultierenden Proxy Objekts auf "true" festgelegt. Dies stellt eine Alternative zum Verwenden des **Credential** -Parameters dar.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseDefaultCredential
Aliases: UDC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Ein Webdienst-Proxy Objekt

Dieses Cmdlet gibt ein Webdienst Proxy-Objekt zurück. Der Namespace und die Klasse des Objekts werden von den Parametern des Befehls bestimmt. Der Standardwert wird aus dem Eingabe-URI generiert.

## HINWEISE

`New-WebServiceProxy` verwendet die **System .net. WebClient** -Klasse, um den angegebenen Webdienst zu laden.

## VERWANDTE LINKS

[New-Service](New-Service.md)
