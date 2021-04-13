---
description: Beschreibt die PowerShell-Ausführungsrichtlinien und erläutert, wie sie verwaltet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Execution_Policies
ms.openlocfilehash: 6c2d4b784c68649ea88e744a9cf5df6329ac897f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222060"
---
# <a name="about-execution-policies"></a>Informationen zu Ausführungsrichtlinien

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt die PowerShell-Ausführungsrichtlinien und erläutert, wie sie verwaltet werden.

## <a name="long-description"></a>Lange Beschreibung

Die PowerShell-Ausführungsrichtlinie ist ein Sicherheits-Feature, mit dem die Bedingungen gesteuert werden, unter denen PowerShell Konfigurationsdateien lädt und Skripts ausführt. Diese Funktion verhindert, dass böswillige Skripts ausgeführt werden.

Auf einem Windows-Computer können Sie eine Ausführungsrichtlinie für den lokalen Computer, für den aktuellen Benutzer oder für eine bestimmte Sitzung festlegen. Sie können auch eine Gruppenrichtlinien-Einstellung verwenden, um Ausführungsrichtlinien für Computer und Benutzer festzulegen.

Ausführungsrichtlinien für den lokalen Computer und den aktuellen Benutzer werden in der Registrierung gespeichert. Sie müssen keine Ausführungsrichtlinien in Ihrem PowerShell-Profil festlegen.
Die Ausführungsrichtlinie für eine bestimmte Sitzung wird nur im Arbeitsspeicher gespeichert und geht verloren, wenn die Sitzung geschlossen wird.

Die Ausführungsrichtlinie ist kein Sicherheitssystem, das Benutzeraktionen einschränkt. Beispielsweise können Benutzer eine Richtlinie problemlos umgehen, indem sie den Skript-Inhalt in der Befehlszeile eingeben, wenn sie ein Skript nicht ausführen können. Stattdessen unterstützt die Ausführungsrichtlinie Benutzer beim Festlegen grundlegender Regeln und verhindert, dass sie unbeabsichtigt gegen sie verstoßen.

Auf Nicht-Windows-Computern ist die Standard-Ausführungsrichtlinie **uneingeschränkt** und kann nicht geändert werden. Das `Set-ExecutionPolicy`-Cmdlet ist verfügbar, aber PowerShell zeigt eine Konsolenmeldung an, dass dies nicht unterstützt wird. Obwohl `Get-ExecutionPolicy` bei Nicht-Windows-Plattformen **uneingeschränkt** zurückgibt, stimmt das Verhalten tatsächlich mit der **Umgehung** überein, da diese Plattformen die Windows-Sicherheitszonen nicht implementieren.

## <a name="powershell-execution-policies"></a>PowerShell-Ausführungsrichtlinien

Die Durchsetzung dieser Richtlinien erfolgt nur auf Windows-Plattformen. Die PowerShell-Ausführungsrichtlinien lauten wie folgt:

### <a name="allsigned"></a>AllSigned

- Skripts können ausgeführt werden.
- Erfordert, dass alle Skripts und Konfigurationsdateien von einem vertrauenswürdigen Herausgeber signiert sind, einschließlich Skripts, die auf dem lokalen Computer geschrieben werden.
- Sie werden vor dem Ausführen von Skripts von Verlegern aufgefordert, die Sie noch nicht als vertrauenswürdig eingestuft haben.
- Risiken, die mit signierten, aber bösartigen Skripts ausgeführt werden.

### <a name="bypass"></a>Umgehung

- Es findet keine Blockierung statt und es werden keine Warnungen oder Eingabeaufforderungen ausgegeben.
- Diese Ausführungsrichtlinie ist für Konfigurationen konzipiert, in denen ein PowerShell-Skript in eine größere Anwendung integriert ist, oder für Konfigurationen, in denen PowerShell die Grundlage für ein Programm ist, das über ein eigenes Sicherheitsmodell verfügt.

### <a name="default"></a>Standard

- Legt die Standard-Ausführungsrichtlinie fest.
- Für Windows-Clients **beschränkt** .
- **RemoteSigned** für Windows-Server.

### <a name="remotesigned"></a>RemoteSigned

- Die Standard-Ausführungsrichtlinie für Windows-Server-Computer.
- Skripts können ausgeführt werden.
- Erfordert eine digitale Signatur von einem vertrauenswürdigen Herausgeber für Skripts und Konfigurationsdateien, die aus dem Internet heruntergeladen werden, einschließlich E-Mail- und Instant-Messaging-Programme.
- Erfordert keine digitalen Signaturen für Skripts, die auf dem lokalen Computer geschrieben und nicht aus dem Internet heruntergeladen wurden.
- Führt Skripts aus, die aus dem Internet heruntergeladen und nicht signiert sind, wenn die Blockierung der Skripts aufgehoben wird, z. b. mithilfe des `Unblock-File`-Cmdlets.
- Risiken bei der Ausführung nicht signierter Skripts aus anderen Quellen als dem Internet und signierten Skripts, die bösartig sein könnten.

### <a name="restricted"></a>Eingeschränkt

- Die Standard-Ausführungsrichtlinie für Windows-Client-Computer.
- Lässt einzelne Befehle zu, erlaubt aber keine Skripts.
- Verhindert die Ausführung aller Skriptdateien, einschließlich Formatierungs-und Konfigurationsdateien ( `.ps1xml` ), Modul-Skriptdateien ( `.psm1` ) und PowerShell-Profilen ( `.ps1` ).

### <a name="undefined"></a>Nicht definiert

- Im aktuellen Bereich ist keine Ausführungsrichtlinie festgelegt.
- Wenn die Ausführungsrichtlinie in allen Bereichen nicht **definiert** ist, ist die effektive Ausführungsrichtlinie für Windows-Clients und **RemoteSigned** für Windows-Server **beschränkt** .

### <a name="unrestricted"></a>Nicht eingeschränkt

- Die Standard-Ausführungsrichtlinie für Nicht-Windows-Computer und kann nicht geändert werden.
- Nicht signierte Skripts können ausgeführt werden. Es besteht das Risiko, bösartige Skripts auszuführen.
- Warnt den Benutzer vor dem Ausführen von Skripts und Konfigurationsdateien, die nicht in der lokalen Intranetzone sind.

> [!NOTE]
> Auf Systemen, die Universal-Naming-Convention (UNC)-Pfade nicht von Internet Pfaden unterscheiden, dürfen Skripts, die von einem UNC-Pfad identifiziert werden, möglicherweise nicht mit der **RemoteSigned**-Ausführungsrichtlinie ausgeführt werden.

## <a name="execution-policy-scope"></a>Ausführungsrichtlinienbereich

Sie können eine Ausführungsrichtlinie festlegen, die nur in einem bestimmten Bereich wirksam ist.

Gültige Werte für den **Bereich** sind " **MachinePolicy** ", " **UserPolicy** ", " **Process** ", " **CurrentUser** " und " **LocalMachine** ". **LocalMachine** ist die Standardeinstellung, wenn eine Ausführungsrichtlinie festgelegt wird.

Die **Bereichs**werte werden in der Reihenfolge der Rangfolge aufgelistet. Die Richtlinie, die Vorrang hat, ist in der aktuellen Sitzung wirksam, auch wenn eine restriktivere Richtlinie mit einer niedrigeren Rangfolge festgelegt wurde.

Weitere Informationen finden Sie unter [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).

### <a name="machinepolicy"></a>MachinePolicy

Wird von einem Gruppenrichtlinie für alle Benutzer des Computers festgelegt.

### <a name="userpolicy"></a>UserPolicy

Wird von einem Gruppenrichtlinie für den aktuellen Benutzer des Computers festgelegt.

### <a name="process"></a>Prozess

Der **Prozess**bereich wirkt sich nur auf die aktuelle PowerShell-Sitzung aus. Die Ausführungsrichtlinie wird in der Umgebungsvariablen und `$env:PSExecutionPolicyPreference` nicht in der Registrierung gespeichert. Wenn die PowerShell-Sitzung geschlossen ist, werden die Variable und der Wert gelöscht.

### <a name="currentuser"></a>CurrentUser

Die Ausführungsrichtlinie wirkt sich nur auf den aktuellen Benutzer aus. Sie wird im Registrierungsunterschlüssel **HKEY_CURRENT_USER** gespeichert.

### <a name="localmachine"></a>LocalMachine

Die Ausführungsrichtlinie wirkt sich auf alle Benutzer des aktuellen Computers aus. Sie wird im Registrierungsunterschlüssel **HKEY_LOCAL_MACHINE** gespeichert.

## <a name="managing-the-execution-policy-with-powershell"></a>Verwalten der Ausführungsrichtlinie mit PowerShell

Verwenden Sie das-Cmdlet, um die effektive Ausführungsrichtlinie für die aktuelle PowerShell-Sitzung zu erhalten `Get-ExecutionPolicy` .

Mit dem folgenden Befehl wird die effektive Ausführungsrichtlinie abgerufen:

```powershell
Get-ExecutionPolicy
```

So erhalten Sie alle Ausführungsrichtlinien, die sich auf die aktuelle Sitzung auswirken, und zeigen Sie in der Rangfolge an:

```powershell
Get-ExecutionPolicy -List
```

Das Ergebnis sieht in etwa wie in der folgenden Beispielausgabe aus:

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       AllSigned
```

In diesem Fall ist die effektive Ausführungsrichtlinie **RemoteSigned** , da die Ausführungsrichtlinie für den aktuellen Benutzer Vorrang vor der für den lokalen Computer festgelegten Ausführungs Richtlinie hat.

Um die Ausführungs Richtlinie für einen bestimmten Bereich zu erhalten, verwenden Sie den **Scope** -Parameter von `Get-ExecutionPolicy` .

Mit dem folgenden Befehl wird z. b. die Ausführungsrichtlinie für den Bereich **CurrentUser** abgerufen:

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

### <a name="change-the-execution-policy"></a>Ändern der Ausführungsrichtlinie

Verwenden Sie das-Cmdlet, um die PowerShell-Ausführungsrichtlinie auf dem Windows-Computer zu ändern `Set-ExecutionPolicy` . Die Änderung wird sofort wirksam. PowerShell muss nicht neu gestartet werden.

Wenn Sie die Ausführungsrichtlinie für die Bereiche **LocalMachine** oder **CurrentUser** festlegen, wird die Änderung in der Registrierung gespeichert und bleibt wirksam, bis Sie sie wieder ändern.

Wenn Sie die Ausführungsrichtlinie für den **Prozess**bereich festlegen, wird diese nicht in der Registrierung gespeichert. Die Ausführungsrichtlinie wird so lange beibehalten, bis der aktuelle Prozess und alle untergeordneten Prozesse geschlossen werden.

> [!NOTE]
> Starten Sie in Windows Vista und höheren Versionen von Windows PowerShell mit der Option **als Administrator ausführen** , um Befehle auszuführen, mit denen die Ausführungsrichtlinie für den lokalen Computer, den Bereich **LocalMachine** , geändert wird.

So ändern Sie die Ausführungsrichtlinie:

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName>
```

Beispiel:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

So legen Sie die Ausführungsrichtlinie in einem bestimmten Bereich fest:

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName> -Scope <scope>
```

Beispiel:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Ein Befehl zum Ändern einer Ausführungsrichtlinie kann erfolgreich sein, aber die effektive Ausführungsrichtlinie trotzdem nicht ändern.

Beispielsweise kann ein Befehl, mit dem die Ausführungsrichtlinie für den lokalen Computer festgelegt wird, erfolgreich ausgeführt, aber von der Ausführungsrichtlinie für den aktuellen Benutzer überschrieben werden.

### <a name="remove-the-execution-policy"></a>Entfernen der Ausführungs Richtlinie

Um die Ausführungsrichtlinie für einen bestimmten Bereich zu entfernen, legen Sie die Ausführungsrichtlinie auf "nicht **definiert** " fest.

So entfernen Sie beispielsweise die Ausführungsrichtlinie für alle Benutzer des lokalen Computers:

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope LocalMachine
```

So entfernen Sie die Ausführungsrichtlinie für einen **Bereich** :

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
```

Wenn in keinem Bereich eine Ausführungsrichtlinie festgelegt ist, wird die effektive Ausführungsrichtlinie **eingeschränkt**. Dies ist die Standardeinstellung für Windows-Clients.

### <a name="set-a-different-policy-for-one-session"></a>Festlegen einer anderen Richtlinie für eine Sitzung

Sie können den **ExecutionPolicy** -Parameter von **pwsh.exe** verwenden, um eine Ausführungsrichtlinie für eine neue PowerShell-Sitzung festzulegen. Die Richtlinie wirkt sich nur auf die aktuelle Sitzung und untergeordnete Sitzungen aus.

Um die Ausführungsrichtlinie für eine neue Sitzung festzulegen, starten Sie PowerShell in der Befehlszeile, z. b. **cmd.exe** oder PowerShell, und verwenden Sie dann den **ExecutionPolicy** -Parameter von **pwsh.exe** , um die Ausführungsrichtlinie festzulegen.

Beispiel:

```powershell
pwsh.exe -ExecutionPolicy AllSigned
```

Die von Ihnen festgelegte Ausführungsrichtlinie ist nicht in der Registrierung gespeichert. Stattdessen wird Sie in der `$env:PSExecutionPolicyPreference` Umgebungsvariablen gespeichert. Die Variable wird gelöscht, wenn Sie die Sitzung schließen, in der die Richtlinie festgelegt ist. Sie können die Richtlinie nicht ändern, indem Sie den Variablenwert bearbeiten.

Während der Sitzung hat die Ausführungsrichtlinie, die für die Sitzung festgelegt ist, Vorrang vor einer Ausführungsrichtlinie, die in der Registrierung für den lokalen Computer oder den aktuellen Benutzer festgelegt ist. Sie hat jedoch keinen Vorrang vor der Ausführungsrichtlinie, die mithilfe einer Gruppenrichtlinie festgelegt wurde.

## <a name="use-group-policy-to-manage-execution-policy"></a>Verwalten der Ausführungsrichtlinie mit Gruppenrichtlinie

Sie können die Einstellung **Skriptausführung Gruppenrichtlinie aktivieren** verwenden, um die Ausführungsrichtlinie von Computern in Ihrem Unternehmen zu verwalten. Die Gruppenrichtlinieneinstellung überschreibt die Ausführungsrichtlinien, die in PowerShell in allen Bereichen festgelegt sind.

Die Richtlinieneinstellungen **für die Skriptausführung aktivieren** lauten wie folgt:

- Wenn Sie die **Ausführung der Skriptausführung** deaktivieren, werden Skripts nicht ausgeführt. Dies entspricht der **eingeschränkten** Ausführungsrichtlinie.
- Wenn Sie die Option **Skriptausführung** aktivieren aktivieren, können Sie eine Ausführungsrichtlinie auswählen. Die Gruppenrichtlinieneinstellungen entsprechen den folgenden Einstellungen für die Ausführungsrichtlinie:

  | Gruppenrichtlinie                                  | Ausführungsrichtlinie |
  | --------------------------------------------- | ---------------- |
  | Alle Skripts zulassen                             | Nicht eingeschränkt     |
  | Lokale Skripts und Remote signierte Skripts zulassen | RemoteSigned     |
  | Nur signierte Skripts zulassen                     | AllSigned        |

- Wenn die Option **Skriptausführung aktivieren** nicht konfiguriert ist, hat dies keine Auswirkungen. Die in PowerShell festgelegte Ausführungsrichtlinie ist gültig.

Die Dateien "powershellexecutionpolicy. adm" und "powershellexecutionpolicy. ADMX" fügen die Richtlinie zum **Aktivieren der Skriptausführung** zu den Knoten "Computer-Konfiguration" und "Benutzerkonfiguration" in Gruppenrichtlinie-Editor in den folgenden Pfaden hinzu.

Für Windows XP und Windows Server 2003:

Administrative Vorlagen\Windows-komponents\windows PowerShell

Für Windows Vista und spätere Versionen von Windows:

Administrative vorlagen\classic administrative Vorlagen \
Windows-Komponenten \ Windows PowerShell

Im Knoten Computer-Konfiguration festgelegte Richtlinien haben Vorrang vor den Richtlinien, die im Knoten Benutzerkonfiguration festgelegt sind.

Weitere Informationen finden Sie unter [about_Group_Policy_Settings](about_Group_Policy_Settings.md).

### <a name="execution-policy-precedence"></a>Rangfolge der Ausführungsrichtlinie

Wenn Sie die effektive Ausführungsrichtlinie für eine Sitzung ermitteln, wertet PowerShell die Ausführungsrichtlinien in der folgenden Reihenfolge aus:

- Gruppenrichtlinie: MachinePolicy
- Gruppenrichtlinie: UserPolicy
- Ausführungs Richtlinie: Prozess (oder `pwsh.exe -ExecutionPolicy` )
- Ausführungs Richtlinie: CurrentUser
- Ausführungs Richtlinie: LocalMachine

## <a name="manage-signed-and-unsigned-scripts"></a>Verwalten von signierten und nicht signierten Skripts

In Windows fügen Programme wie Internet Explorer und Microsoft Edge Dateien, die heruntergeladen werden, einen alternativen Datenstrom hinzu. Dadurch wird die Datei als "aus dem Internet über das Internet" markiert. Wenn Ihre PowerShell-Ausführungsrichtlinie **RemoteSigned** ist, führt PowerShell keine nicht signierten Skripts aus, die aus dem Internet heruntergeladen werden, einschließlich e-Mail-und Instant Messaging-Programme.

Sie können das Skript signieren oder ein nicht signiertes Skript ausführen, ohne die Ausführungs Richtlinie zu ändern.

Ab PowerShell 3,0 können Sie den **Stream** -Parameter des `Get-Item` Cmdlets verwenden, um Dateien zu erkennen, die blockiert werden, weil Sie aus dem Internet heruntergeladen wurden. Verwenden Sie das `Unblock-File` Cmdlet, um die Blockierung der Skripts aufzulösen, damit Sie Sie in PowerShell ausführen können.

Weitere Informationen finden Sie unter [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)und [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).

> [!NOTE]
> Andere Methoden zum Herunterladen von Dateien dürfen die Dateien nicht als aus der Internet Zone stammende Dateien markieren. Beispiele hierfür sind:
>
> - `curl.exe`
> - `Invoke-RestMethod`
> - `Invoke-WebRequest`

## <a name="execution-policy-on-windows-server-core-and-window-nano-server"></a>Ausführungs Richtlinie für Windows Server Core und Windows Nano Server

Wenn PowerShell 6 unter bestimmten Bedingungen unter Windows Server Core oder Windows Nano Server ausgeführt wird, können Ausführungsrichtlinien mit dem folgenden Fehler fehlschlagen:

```Output
AuthorizationManager check failed.
At line:1 char:1
+ C:\scriptpath\scriptname.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

PowerShell verwendet APIs in der Windows-Desktopshell ( `explorer.exe` ), um die Zone einer Skriptdatei zu validieren. Die Windows-Shell ist unter Windows Server Core und Windows Nano Server nicht verfügbar.

Dieser Fehler kann auch bei jedem Windows-System angezeigt werden, wenn die Windows Desktopshell nicht verfügbar ist oder nicht reagiert. Beispielsweise kann während der Anmeldung die Ausführung eines PowerShell-Anmelde-Skripts gestartet werden, bevor der Windows-Desktop bereit ist, was zu einem Fehler führt.

Die Verwendung einer Ausführungsrichtlinie von **Bypass** oder **AllSigned** erfordert keine Zonenüberprüfung, um das Problem zu vermeiden.

## <a name="see-also"></a>Weitere Informationen

[about_Environment_Variables](about_Environment_Variables.md)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Signing](about_Signing.md)

[Get-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)

[Hilfe zur pwsh-Konsole](about_pwsh.md)

[Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File)

