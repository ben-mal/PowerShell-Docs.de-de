---
title: Typen von Cmdlet-Parametern | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e704aae6e23568be9935e228752f652929863a98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786372"
---
# <a name="types-of-cmdlet-parameters"></a>Cmdlet-Parametertypen

In diesem Thema werden die verschiedenen Parametertypen beschrieben, die Sie in Cmdlets deklarieren können. Cmdlet-Parameter können Positions-, benannte, erforderliche, optionale oder Switch-Parameter sein.

## <a name="positional-and-named-parameters"></a>Positions Parameter und benannte Parameter

Alle Cmdlet-Parameter sind entweder benannte oder positionelle Parameter. Ein benannter Parameter erfordert, dass Sie den Parameternamen und das Argument eingeben, wenn Sie das Cmdlet aufrufen. Ein Positions Parameter erfordert nur, dass Sie die Argumente in relativer Reihenfolge eingeben. Das System ordnet dann das erste unbenannte Argument dem ersten Positions Parameter zu. Das System ordnet das zweite unbenannte Argument dem zweiten unbenannten Parameter zu usw. Standardmäßig sind alle Cmdlet-Parameter benannte Parameter.

Um einen benannten Parameter zu definieren, lassen Sie das- `Position` Schlüsselwort in der Deklaration des **Parameter** Attributs aus, wie in der folgenden Parameter Deklaration gezeigt.

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

Um einen Positions Parameter zu definieren, fügen Sie das `Position` -Schlüsselwort in der Attribut Deklaration des Parameters ein, und geben Sie dann eine Position an Im folgenden Beispiel wird der- `UserName` Parameter als Positions Parameter mit der Position 0 deklariert. Dies bedeutet, dass das erste Argument des Aufrufes automatisch an diesen Parameter gebunden wird.

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

> [!NOTE]
> Ein gutes Cmdlet-Design empfiehlt, dass die am häufigsten verwendeten Parameter als Positions Parameter deklariert werden, damit der Benutzer den Parameternamen nicht eingeben muss, wenn das Cmdlet ausgeführt wird.

Positions Parameter und benannte Parameter akzeptieren einzelne Argumente oder mehrere Argumente, die durch Kommas getrennt sind. Mehrere Argumente sind nur zulässig, wenn der Parameter eine Auflistung, z. b. ein Array von Zeichen folgen, akzeptiert. Sie können positionelle und benannte Parameter im gleichen Cmdlet kombinieren. In diesem Fall ruft das System zuerst die benannten Argumente ab und versucht dann, die verbleibenden unbenannten Argumente den Positions Parametern zuzuordnen.

Die folgenden Befehle zeigen die verschiedenen Methoden, mit denen Sie einzelne und mehrere Argumente für die Parameter des `Get-Command` Cmdlets angeben können. Beachten Sie, dass der **-Name** in den letzten beiden Beispielen nicht angegeben werden muss, da der- `Name` Parameter als Positions Parameter definiert ist.

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a>Obligatorische und optionale Parameter

Sie können auch Cmdlet-Parameter als obligatorische oder optionale Parameter definieren. (Ein obligatorischer Parameter muss angegeben werden, bevor das Cmdlet von der Windows PowerShell-Laufzeit aufgerufen wird.)  Standardmäßig werden Parameter als optional definiert.

Zum Definieren eines obligatorischen Parameters fügen Sie das `Mandatory` -Schlüsselwort in der Deklaration des Parameter Attributs hinzu, und legen Sie es auf fest `true` , wie in der folgenden Parameter Deklaration gezeigt.

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

Um einen optionalen Parameter zu definieren, lassen Sie das- `Mandatory` Schlüsselwort in der Deklaration des **Parameter** Attributs aus, wie in der folgenden Parameter Deklaration gezeigt.

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a>Parameter wechseln

Windows PowerShell stellt einen [System. Management. Automation. Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter) -Typ bereit, mit dem Sie einen Parameter definieren können, dessen Wert automatisch auf festgelegt wird, `false` Wenn der-Parameter nicht angegeben wird, wenn das Cmdlet aufgerufen wird. Verwenden Sie nach Möglichkeit anstelle von booleschen Parametern Switchparameter.

Sehen Sie sich das folgende Beispiel an. Standardmäßig übergeben mehrere Windows PowerShell-Cmdlets kein Ausgabe Objekt in der Pipeline. Diese Cmdlets verfügen jedoch über einen `PassThru` Switch-Parameter, der das Standardverhalten überschreibt. Wenn der- `PassThru` Parameter angegeben wird, wenn diese Cmdlets aufgerufen werden, gibt das Cmdlet ein Ausgabe Objekt an die Pipeline zurück.

Wenn Sie für den-Parameter den Standardwert benötigen `true` , wenn der-Parameter nicht im-Befehl angegeben ist, sollten Sie den Sinn des Parameters umkehren. Wenn Sie z. b. das Parameter Attribut nicht auf einen booleschen Wert festlegen, `true` deklarieren Sie die Eigenschaft als [System. Management. Automation. Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter) -Typ, und legen Sie dann den Standardwert des-Parameters auf fest `false` .

Um einen Switch-Parameter zu definieren, deklarieren Sie die Eigenschaft als [System. Management. Automation. Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter) -Typ, wie im folgenden Beispiel gezeigt.

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

Um das Cmdlet für den Parameter zu verwenden, wenn es angegeben ist, verwenden Sie die folgende Struktur in einer der Eingabe Verarbeitungsmethoden.

```csharp
protected override void ProcessRecord()
{
  WriteObject("Switch parameter test: " + userName + ".");
  if(goodbye)
  {
    WriteObject(" Goodbye!");
  }
} // End ProcessRecord
```

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
