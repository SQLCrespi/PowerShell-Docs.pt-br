---
description: Descreve as políticas de execução do PowerShell e explica como gerenciá-las.
Locale: en-US
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Execution_Policies
ms.openlocfilehash: 1a2b8458b39233f96d47a52e3fea21b31e9b3c42
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597015"
---
# <a name="about-execution-policies"></a>Sobre as políticas de execução

## <a name="short-description"></a>Descrição breve
Descreve as políticas de execução do PowerShell e explica como gerenciá-las.

## <a name="long-description"></a>Descrição longa

A política de execução do PowerShell é um recurso de segurança que controla as condições sob as quais o PowerShell carrega arquivos de configuração e executa scripts. Esse recurso ajuda a impedir a execução de scripts mal-intencionados.

Em um computador com Windows, você pode definir uma política de execução para o computador local, para o usuário atual ou para uma sessão específica. Você também pode usar uma configuração de Política de Grupo para definir políticas de execução para computadores e usuários.

As políticas de execução para o computador local e o usuário atual são armazenadas no registro. Você não precisa definir políticas de execução no seu perfil do PowerShell.
A política de execução para uma sessão específica é armazenada apenas na memória e é perdida quando a sessão é fechada.

A política de execução não é um sistema de segurança que restringe as ações do usuário. Por exemplo, os usuários podem ignorar facilmente uma política digitando o conteúdo do script na linha de comando quando não puderem executar um script. Em vez disso, a política de execução ajuda os usuários a definir regras básicas e impede que eles as violem involuntariamente.

Em computadores não Windows, a política de execução padrão é **irrestrita** e não pode ser alterada. O `Set-ExecutionPolicy` cmdlet está disponível, mas o PowerShell exibe uma mensagem de console que não tem suporte. Embora `Get-ExecutionPolicy` o retorne **irrestrito** em plataformas não Windows, o comportamento realmente corresponde ao **bypass** porque essas plataformas não implementam as zonas de segurança do Windows.

## <a name="powershell-execution-policies"></a>Políticas de execução do PowerShell

A imposição dessas políticas só ocorre em plataformas Windows. As políticas de execução do PowerShell são as seguintes:

### <a name="allsigned"></a>AllSigned

- Os scripts podem ser executados.
- Requer que todos os arquivos de configuração e scripts sejam assinados por um editor confiável, incluindo scripts escritos no computador local.
- O solicita antes de executar scripts de editores que você ainda não classificou como confiáveis ou não confiáveis.
- Riscos em execução assinada, mas mal-intencionados, scripts.

### <a name="bypass"></a>Bypass

- Nada está bloqueado e não há avisos ou prompts.
- Essa política de execução é projetada para configurações nas quais um script do PowerShell é integrado a um aplicativo maior ou para configurações em que o PowerShell é a base para um programa que tem seu próprio modelo de segurança.

### <a name="default"></a>Padrão

- Define a política de execução padrão.
- **Restrito** para clientes Windows.
- **RemoteSigned** para servidores Windows.

### <a name="remotesigned"></a>RemoteSigned

- A política de execução padrão para computadores Windows Server.
- Os scripts podem ser executados.
- Requer uma assinatura digital de um editor confiável em arquivos de configuração e scripts que são baixados da Internet, que inclui programas de email e mensagens instantâneas.
- Não requer assinaturas digitais em scripts que são gravados no computador local e não baixados da Internet.
- Executa scripts que são baixados da Internet e não assinados, se os scripts forem desbloqueados, como usando o `Unblock-File` cmdlet.
- Riscos que executam scripts não assinados de fontes diferentes da Internet e scripts assinados que podem ser mal-intencionados.

### <a name="restricted"></a>Restritos

- A política de execução padrão para computadores cliente Windows.
- Permite comandos individuais, mas não permite scripts.
- Impede a execução de todos os arquivos de script, incluindo arquivos de formatação e configuração ( `.ps1xml` ), arquivos de script de módulo ( `.psm1` ) e perfis do PowerShell ( `.ps1` ).

### <a name="undefined"></a>Indefinido

- Não há nenhuma política de execução definida no escopo atual.
- Se a política de execução em todos os escopos for **indefinida**, a política de execução efetiva será **restrita** para clientes Windows e **RemoteSigned** para Windows Server.

### <a name="unrestricted"></a>Irrestrito

- A política de execução padrão para computadores não Windows e não pode ser alterada.
- Os scripts não assinados podem ser executados. Há um risco de executar scripts mal-intencionados.
- Avisa o usuário antes de executar scripts e arquivos de configuração que não são da zona da intranet local.

> [!NOTE]
> Em sistemas que não diferenciam caminhos UNC (Convenção de nomenclatura universal) de caminhos da Internet, os scripts identificados por um caminho UNC podem não ter permissão para serem executados com a política de execução **RemoteSigned** .

## <a name="execution-policy-scope"></a>Escopo da política de execução

Você pode definir uma política de execução que só é eficaz em um escopo específico.

Os valores válidos para o **escopo** são **MachinePolicy**, **UserPolicy**, **process**, **CurrentUser** e **LocalMachine**. **LocalMachine** é o padrão ao definir uma política de execução.

Os valores de **escopo** são listados em ordem de precedência. A política que tem precedência é eficaz na sessão atual, mesmo que uma política mais restritiva tenha sido definida em um nível mais baixo de precedência.

Para obter mais informações, consulte [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).

### <a name="machinepolicy"></a>MachinePolicy

Definido por um Política de Grupo para todos os usuários do computador.

### <a name="userpolicy"></a>UserPolicy

Definido por um Política de Grupo para o usuário atual do computador.

### <a name="process"></a>Processar

O escopo do **processo** afeta apenas a sessão atual do PowerShell. A política de execução é salva na variável de ambiente `$env:PSExecutionPolicyPreference` , em vez de no registro. Quando a sessão do PowerShell é fechada, a variável e o valor são excluídos.

### <a name="currentuser"></a>CurrentUser

A política de execução afeta apenas o usuário atual. Ele é armazenado na subchave do registro **HKEY_CURRENT_USER** .

### <a name="localmachine"></a>LocalMachine

A política de execução afeta todos os usuários no computador atual. Ele é armazenado na subchave do registro **HKEY_LOCAL_MACHINE** .

## <a name="managing-the-execution-policy-with-powershell"></a>Gerenciando a política de execução com o PowerShell

Para obter a política de execução efetiva para a sessão atual do PowerShell, use o `Get-ExecutionPolicy` cmdlet.

O comando a seguir obtém a política de execução efetiva:

```powershell
Get-ExecutionPolicy
```

Para obter todas as políticas de execução que afetam a sessão atual e exibi-las em ordem de precedência:

```powershell
Get-ExecutionPolicy -List
```

O resultado é semelhante ao seguinte exemplo de saída:

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       AllSigned
```

Nesse caso, a política de execução efetiva é **RemoteSigned** porque a política de execução para o usuário atual tem precedência sobre a política de execução definida para o computador local.

Para obter a política de execução definida para um escopo específico, use o parâmetro **Scope** de `Get-ExecutionPolicy` .

Por exemplo, o comando a seguir obtém a política de execução para o escopo **CurrentUser** :

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

### <a name="change-the-execution-policy"></a>Alterar a política de execução

Para alterar a política de execução do PowerShell no computador com Windows, use o `Set-ExecutionPolicy` cmdlet. A alteração entra em vigor imediatamente. Você não precisa reiniciar o PowerShell.

Se você definir a política de execução para os escopos **LocalMachine** ou **CurrentUser**, a alteração será salva no registro e permanecerá em vigor até que você o altere novamente.

Se você definir a política de execução para o escopo do **processo** , ela não será salva no registro. A política de execução é mantida até que o processo atual e todos os processos filho sejam fechados.

> [!NOTE]
> No Windows Vista e versões posteriores do Windows, para executar comandos que alteram a política de execução para o computador local, escopo de **LocalMachine** , inicie o PowerShell com a opção **Executar como administrador** .

Para alterar sua política de execução:

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName>
```

Por exemplo:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

Para definir a política de execução em um escopo específico:

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName> -Scope <scope>
```

Por exemplo:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Um comando para alterar uma política de execução pode ter sucesso, mas ainda não alterar a política de execução efetiva.

Por exemplo, um comando que define a política de execução para o computador local pode ter sucesso, mas ser substituído pela política de execução para o usuário atual.

### <a name="remove-the-execution-policy"></a>Remover a política de execução

Para remover a política de execução para um escopo específico, defina a política de execução como **indefinido**.

Por exemplo, para remover a política de execução para todos os usuários do computador local:

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope LocalMachine
```

Para remover a política de execução para um **escopo**:

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
```

Se nenhuma política de execução for definida em nenhum escopo, a política de execução efetiva será **restrita**, que é o padrão para clientes Windows.

### <a name="set-a-different-policy-for-one-session"></a>Definir uma política diferente para uma sessão

Você pode usar o parâmetro **ExecutionPolicy** de **pwsh.exe** para definir uma política de execução para uma nova sessão do PowerShell. A política afeta apenas a sessão atual e as sessões filho.

Para definir a política de execução para uma nova sessão, inicie o PowerShell na linha de comando, como **cmd.exe** ou do PowerShell e, em seguida, use o parâmetro **ExecutionPolicy** de **pwsh.exe** para definir a política de execução.

Por exemplo:

```powershell
pwsh.exe -ExecutionPolicy AllSigned
```

A política de execução definida não é armazenada no registro. Em vez disso, ele é armazenado na `$env:PSExecutionPolicyPreference` variável de ambiente. A variável é excluída quando você fecha a sessão na qual a política está definida. Você não pode alterar a política editando o valor da variável.

Durante a sessão, a política de execução definida para a sessão tem precedência sobre uma política de execução definida no registro para o computador local ou o usuário atual. No entanto, ele não tem precedência sobre a política de execução definida usando um Política de Grupo.

## <a name="use-group-policy-to-manage-execution-policy"></a>Usar Política de Grupo para gerenciar a política de execução

Você pode usar a configuração **ativar a execução de Script** política de grupo para gerenciar a política de execução de computadores em sua empresa. A configuração de Política de Grupo substitui as políticas de execução definidas no PowerShell em todos os escopos.

As configurações ativar política de **execução de script** são as seguintes:

- Se você desabilitar **ativar a execução de script**, os scripts não são executados. Isso é equivalente à política de execução **restrita** .
- Se habilitar **ativar a execução do script**, você poderá selecionar uma política de execução. As configurações de Política de Grupo são equivalentes às seguintes configurações de política de execução:

  | Política de Grupo                                  | Política de execução |
  | --------------------------------------------- | ---------------- |
  | Permitir todos os scripts                             | Irrestrito     |
  | Permitir scripts locais e scripts remotos assinados | RemoteSigned     |
  | Permitir somente scripts assinados                     | AllSigned        |

- Se **ativar a execução do script** não estiver configurado, ele não terá nenhum efeito. A política de execução definida no PowerShell é eficaz.

Os arquivos PowerShellExecutionPolicy. adm e PowerShellExecutionPolicy. admx adicionam a política de **execução ativar script** aos nós configuração do computador e configuração do usuário no Editor de política de grupo nos caminhos a seguir.

Para o Windows XP e o Windows Server 2003:

Modelos administrativos do Windows\windows PowerShell

Para o Windows Vista e versões posteriores do Windows:

Templates\Classic administrativo Modelos Administrativos \
Windows Windows\windows PowerShell

As políticas definidas no nó Configuração do computador têm precedência sobre as políticas definidas no nó Configuração do usuário.

Confira mais informações em [about_Group_Policy_Settings](about_Group_Policy_Settings.md).

### <a name="execution-policy-precedence"></a>Precedência de política de execução

Ao determinar a política de execução efetiva para uma sessão, o PowerShell avalia as políticas de execução na seguinte ordem de precedência:

- Política de Grupo: MachinePolicy
- Política de Grupo: UserPolicy
- Política de execução: processo (ou `pwsh.exe -ExecutionPolicy` )
- Política de execução: CurrentUser
- Política de execução: LocalMachine

## <a name="manage-signed-and-unsigned-scripts"></a>Gerenciar scripts assinados e não assinados

No Windows, programas como o Internet Explorer e o Microsoft Edge adicionam um fluxo de dados alternativo a arquivos que são baixados. Isso marca o arquivo como "proveniente da Internet". Se a política de execução do PowerShell for **RemoteSigned**, o PowerShell não executará scripts não assinados que são baixados da Internet que inclui programas de email e mensagens instantâneas.

Você pode assinar o script ou optar por executar um script não assinado sem alterar a política de execução.

A partir do PowerShell 3,0, você pode usar o parâmetro **Stream** do `Get-Item` cmdlet para detectar arquivos bloqueados porque eles foram baixados da Internet. Use o `Unblock-File` cmdlet para desbloquear os scripts para que você possa executá-los no PowerShell.

Para obter mais informações, consulte [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)e [desbloquear-File](xref:Microsoft.PowerShell.Utility.Unblock-File).

> [!NOTE]
> Outros métodos de download de arquivos podem não marcar os arquivos como provenientes da zona da Internet. Alguns exemplos incluem:
>
> - `curl.exe`
> - `Invoke-RestMethod`
> - `Invoke-WebRequest`

## <a name="execution-policy-on-windows-server-core-and-window-nano-server"></a>Política de execução no Windows Server Core e no Window nano Server

Quando o PowerShell 6 é executado no Windows Server Core ou no Windows nano Server em determinadas condições, as políticas de execução podem falhar com o seguinte erro:

```Output
AuthorizationManager check failed.
At line:1 char:1
+ C:\scriptpath\scriptname.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

O PowerShell usa APIs no Shell da área de trabalho do Windows ( `explorer.exe` ) para validar a zona de um arquivo de script. O Shell do Windows não está disponível no Windows Server Core e no Windows nano Server.

Você também poderá obter esse erro em qualquer sistema Windows se o Shell da área de trabalho do Windows estiver indisponível ou sem resposta. Por exemplo, durante o logon, um script de logon do PowerShell pode iniciar a execução antes que a área de trabalho do Windows esteja pronta, resultando em falha.

Usar uma política de execução de **bypass** ou **AllSigned** não requer uma verificação de zona, o que evita o problema.

## <a name="see-also"></a>Consulte Também

[about_Environment_Variables](about_Environment_Variables.md)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Signing](about_Signing.md)

[Get-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)

[Ajuda do console do Pwsh](about_pwsh.md)

[Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File)

