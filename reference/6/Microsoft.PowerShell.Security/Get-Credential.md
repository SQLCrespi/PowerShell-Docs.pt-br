---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 3716e5b8b88f4c07da06c28091d2c7f3202caa28
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "93196631"
---
# Get-Credential

## SINOPSE
Obtém um objeto de credencial com base em um nome de usuário e senha.

## SYNTAX

### Credentialset (padrão)

```
Get-Credential [[-Credential] <PSCredential>] [<CommonParameters>]
```

### Mensagem de

```
Get-Credential [-Message <String>] [[-UserName] <String>] [-Title <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Credential` cmdlet cria um objeto de credencial para um nome de usuário e senha especificados. É possível utilizar o objeto de credencial em operações de segurança.

O `Get-Credential` cmdlet solicita ao usuário uma senha ou um nome de usuário e senha. Você pode usar o parâmetro **Message** para especificar uma mensagem personalizada no prompt de linha de comando.

## EXEMPLOS

### Exemplo 1

```powershell
$c = Get-Credential
```

Esse comando obtém um objeto de credencial e o salva na `$c` variável.

Quando você inserir o comando, um nome de usuário e uma senha serão solicitados. Quando você insere as informações solicitadas, o cmdlet cria um objeto **PSCredential** que representa as credenciais do usuário e salva-o na `$c` variável.

É possível utilizar o objeto como entrada para os cmdlets que exigem autenticação de usuário, como aqueles com um parâmetro **Credential** . No entanto, alguns provedores instalados com o PowerShell não oferecem suporte ao parâmetro **Credential** .

### Exemplo 2

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

Esses comandos usam um objeto Credential que o `Get-Credential` cmdlet retorna para autenticar um usuário em um computador remoto para que eles possam usar o Instrumentação de gerenciamento do Windows (WMI) para gerenciar o computador.

O primeiro comando obtém um objeto de credencial e o salva na `$c` variável. O segundo comando usa o objeto Credential em um `Get-CimInstance` comando. Esse comando obtém informações sobre as unidades de disco no computador Server01.

### Exemplo 3:

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

Este comando mostra como incluir um `Get-Credential` comando em um  `Get-CimInstance` comando.

Esse comando usa o `Get-CimInstance` cmdlet para obter informações sobre o BIOS no computador Server01. Ele usa o parâmetro **Credential** para autenticar o usuário, Domínio01 \ Usuário01 e um `Get-Credential` comando como o valor do parâmetro **Credential** .

### Exemplo 4

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

Este exemplo cria uma credencial que inclui um nome de usuário sem um nome de domínio.

O primeiro comando obtém uma credencial com o nome de usuário User01 e a armazena na `$c` variável.
O segundo comando exibe o valor da propriedade **Username** do objeto de credencial resultante.

### Exemplo 5

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

Este comando utiliza o método **PromptForCredential** para solicitar ao usuário seu nome de usuário e senha. O comando salva as credenciais resultantes na `$Credential` variável.

O método **PromptForCredential** é uma alternativa ao uso do `Get-Credential` cmdlet. Ao usar o **PromptForCredential** , você pode especificar a legenda, as mensagens e o nome de usuário que aparecem no prompt.

Para obter mais informações, consulte a documentação do [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) no SDK.

### Exemplo 6

Este exemplo mostra como criar um objeto de credencial que seja idêntico ao objeto que `Get-Credential` retorna sem avisar o usuário. Este método requer uma senha de texto sem formatação, que pode violar os padrões de segurança em algumas empresas.

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

O primeiro comando salva o nome da conta de usuário no `$User` parâmetro. O valor deve ter o formato "Domain\User" ou "ComputerName\User".

O segundo comando usa o `ConvertTo-SecureString` cmdlet para criar uma cadeia de caracteres segura de uma senha de texto sem formatação. O comando utiliza o parâmetro **AsPlainText** para indicar que a cadeia de caracteres de texto está sem formatação e o parâmetro **Force** para confirmar que você compreende os riscos do uso de texto sem formatação.

O terceiro comando usa o `New-Object` cmdlet para criar um objeto **PSCredential** com base nos valores nas `$User` `$PWord` variáveis e.

### Exemplo 7

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

Esse comando usa os parâmetros de **mensagem** e **nome de usuário** do `Get-Credential` cmdlet. Esse formato de comando destina-se a funções e scripts compartilhados. Nesse caso, a mensagem informa ao usuário porque as credenciais são necessárias e dá a eles confiança de que a solicitação é legítima.

### Exemplo 8

```powershell
Invoke-Command -ComputerName Server01 {Get-Credential Domain01\User02}
```

```Output
PowerShell Credential Request : PowerShell Credential Request
Warning: This credential is being requested by a script or application on the SERVER01 remote computer. Enter your credentials only if you
 trust the remote computer and the application or script requesting it.

Enter your credentials.
Password for user Domain01\User02: ***************

PSComputerName     : Server01
RunspaceId         : 422bdf52-9886-4ada-ab2f-130497c6777f
PSShowComputerName : True
UserName           : Domain01\User01
Password           : System.Security.SecureString
```

Esse comando obtém uma credencial do computador remoto Server01. O comando usa o `Invoke-Command` cmdlet para executar um `Get-Credential` comando no computador remoto. A saída mostra a mensagem de segurança remota que `Get-Credential` inclui no prompt de autenticação.

## PARAMETERS

### -Credential

Especifica um nome de usuário para a credencial, como **User01** ou **Domínio01 \ Usuário01** . O nome do parâmetro, `-Credential` , é opcional.

Ao enviar o comando e especificar um nome de usuário, você será solicitado a fornecer uma senha. Se você omitir esse parâmetro, um nome de usuário e uma senha serão solicitados.

A partir do PowerShell 3,0, se você inserir um nome de usuário sem um domínio, `Get-Credential` o não inserirá mais uma barra invertida antes do nome.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mensagem

Especifica uma mensagem que aparece no prompt de autenticação. Esse parâmetro é projetado para o uso em uma função ou script. É possível utilizar a mensagem para explicar ao usuário por que você está solicitando credenciais e como elas serão utilizadas.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

Define o texto da linha de título para o prompt de autenticação no console do.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

Especifica um nome de usuário. O prompt de autenticação solicita uma senha para o nome de usuário. Por padrão, o nome de usuário está em branco e o prompt de autenticação solicita um nome de usuário e uma senha.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: 1
Default value: None (blank)
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Management. Automation. PSCredential

`Get-Credential` Retorna um objeto Credential.

## OBSERVAÇÕES

Você pode usar o objeto **PSCredential** que `Get-Credential` cria em cmdlets que solicitam autenticação de usuário, como aqueles com um parâmetro **Credential** .

O parâmetro **Credential** não tem suporte de todos os provedores instalados com o PowerShell.
A partir do PowerShell 3,0, ele tem suporte em cmdlets selecionados, como os `Get-Content` `New-PSDrive` cmdlets e.

## LINKS RELACIONADOS

[PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
