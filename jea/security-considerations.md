---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Considerações sobre segurança de JEA
ms.openlocfilehash: befc24fec368c4f6d60477daf63bf17e9431133e
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67726590"
---
# <a name="jea-security-considerations"></a>Considerações sobre segurança de JEA

O JEA ajuda a melhorar a sua situação de segurança, reduzindo o número de administradores permanentes em seus computadores. O JEA usa uma configuração de sessão do PowerShell para criar um ponto de entrada para os usuários gerenciarem o sistema. Os usuários que precisam de acesso com privilégios elevados, mas não acesso ilimitado, ao computador para realizar tarefas administrativas podem receber acesso ao ponto de extremidade JEA. Como o JEA permite que esses usuários executem comandos de administrador sem ter o acesso de administrador completo, você então poderá remover esses usuários de grupos de segurança altamente privilegiados.

## <a name="run-as-account"></a>Conta Executar como

Cada ponto de extremidade JEA tem uma conta **Executar como** designada. Essa é a conta na qual as ações do usuário que está se conectando são executadas. Essa conta é configurável no [arquivo de configuração de sessão](session-configurations.md) e a conta que você escolher tem uma influência significativa sobre a segurança de seu ponto de extremidade.

As **contas virtuais** são a maneira recomendada de configurar a conta **Executar como**. As contas virtuais são avulsas, temporárias e locais que são criadas para o usuário que está se conectando para ser usada durante a duração de sua sessão JEA. Assim que a sessão é terminada, a conta virtual é destruída e não pode mais ser usada. O usuário que está se conectando não sabe as credenciais da conta virtual. A conta virtual não pode ser usada para acessar o sistema por outros meios, como a Área de Trabalho Remota ou um ponto de extremidade irrestrito do PowerShell.

Por padrão, as contas virtuais pertencem ao grupo local de **administradores** no computador. Isso dá a eles direitos totais para gerenciar qualquer coisa no sistema, mas não dá direito para gerenciar recursos na rede.
Durante a autenticação com outros computadores, o contexto do usuário é aquele da conta do computador local, não da conta virtual.

Os controladores de domínio são um caso especial, uma vez que não há um grupo local de **administradores**. Em vez disso, as contas virtuais pertencem a **Administradores de Domínio** e podem gerenciar os serviços de diretório no controlador de domínio. A identidade do domínio ainda é restrita para uso no controlador de domínio em que foi criada uma instância da sessão JEA. Qualquer acesso à rede parece ser proveniente do objeto de computador do controlador de domínio.

Em ambos os casos, você pode definir explicitamente a quais grupos de segurança a conta virtual pertence. Essa é uma boa prática quando a tarefa que pode ser realizada sem privilégios de administrador local ou de domínio. Se você já tiver um grupo de segurança definido para seus administradores, conceda a associação de conta virtual a esse grupo. A associação de grupo da conta virtual é limitada aos grupos de segurança locais na estação de trabalho e em servidores membro. Em controladores de domínio, as contas virtuais precisam ser membros de grupos de segurança de domínio.
Depois que a conta virtual é adicionada a um ou mais grupos de segurança, ela deixa de pertencer aos grupos padrão (administradores locais ou de domínio).

A seguinte tabela resume as possíveis opções de configuração e as permissões resultantes para as contas virtuais:

|        Tipo de Computador         | Configuração do grupo de conta virtual |                   Contexto de usuário local                    | Contexto de usuário de rede |
| ---------------------------- | ----------------------------------- | ------------------------------------------------------- | -------------------- |
| Controlador de domínio            | Padrão                             | Usuário do domínio, membro de '*DOMÍNIO*\Administradores de Domínio'         | Conta de Computador     |
| Controlador de domínio            | Grupos de domínio A e B               | Usuário do domínio, membro de '*DOMÍNIO*\A', '*DOMÍNIO*\B'       | Conta de Computador     |
| Estação de trabalho ou servidor membro | Padrão                             | Usuário local, membro de '*BUILTIN*\Administradores'        | Conta de Computador     |
| Estação de trabalho ou servidor membro | Grupos locais C e D                | Usuário local, membro de '*COMPUTADOR*\C' e '*COMPUTADOR*\D' | Conta de Computador     |

Quando você examinar os eventos de auditoria de segurança e os logs de eventos do aplicativo, verá que cada sessão de usuário JEA tem uma conta virtual exclusiva. Essa conta exclusiva ajuda você a acompanhar as ações de usuário em um ponto de extremidade JEA até o usuário original que executou o comando. Os nomes das contas virtuais seguem o formato `WinRM Virtual Users\WinRM_VA_<ACCOUNTNUMBER>_<DOMAIN>_<sAMAccountName>`. Por exemplo, se o usuário **Alice** no domínio **Contoso** reiniciar um serviço em um ponto de extremidade JEA, o nome de usuário associado aos eventos do Gerenciador de Controle de Serviço será `WinRM Virtual Users\WinRM_VA_1_contoso_alice`.

**As GMSAs (contas de serviço gerenciado de grupo)** são úteis quando um servidor membro precisa ter acesso aos recursos de rede na sessão JEA. Por exemplo, quando um ponto de extremidade JEA é usado para controlar o acesso a um serviço de API REST hospedado em outro computador. É fácil escrever funções para invocar as APIs REST, mas você precisa de uma identidade de rede para autenticação na API. O uso de uma conta de serviço gerenciado de grupo possibilita o segundo salto, sem perder o controle sobre quais computadores podem usar a conta. As permissões efetivas da gMSA são definidas pelos grupos de segurança (local ou de domínio) ao qual a conta gMSA pertence.

Quando um ponto de extremidade JEA é configurado para usar uma GMSA, as ações de todos os usuários JEA parecem vir da mesma GMSA. A única maneira de rastrear as ações até um usuário específico é identificar o conjunto de comandos executados em uma transcrição de sessão do PowerShell.

**Credenciais de passagem** são usadas quando você não especifica uma conta **Executar como**. O PowerShell usa a credencial do usuário que está se conectando para executar comandos no servidor remoto. Isso exige que você permita acesso direto ao usuário que está se conectando aos grupos de gerenciamento privilegiado. Essa configuração **não** é recomendada para o JEA. Se o usuário que estiver se conectando já tiver privilégios de administrador, ele poderá evitar o JEA e gerenciar o sistema por outros meios irrestritos. Para obter mais informações, confira a seção abaixo sobre como [o JEA não fornece proteção contra administradores](#jea-doesnt-protect-against-admins).

As **contas padrão Executar como** permitem especificar qualquer conta de usuário na qual toda a sessão do PowerShell é executada. As configurações de sessão que usam contas fixas **Executar como** (com o parâmetro `-RunAsCredential`) não reconhecem o JEA. As definições de função deixarão de funcionar conforme o esperado. A mesma função é atribuída a todos os usuários autorizados a acessar o ponto de extremidade.

Você não deve usar uma **RunAsCredential** em um ponto de extremidade JEA, devido ao fato de ser difícil rastrear as ações até usuários específicos e não haver suporte para ela no mapeamento de usuários às funções.

## <a name="winrm-endpoint-acl"></a>ACL do Ponto de Extremidade do WinRM

Assim como acontece com pontos de extremidade regulares de comunicação remota do PowerShell, cada ponto de extremidade JEA tem uma ACL (lista de controle de acesso) separada que controla quem pode se autenticar no ponto de extremidade JEA. Se ele for configurado incorretamente, os usuários confiáveis poderão não conseguir acessar o ponto de extremidade JEA e os usuários não confiáveis poderão ter acesso. A ACL do WinRM não afeta o mapeamento de usuários às funções JEA. O mapeamento é controlado pelo campo **RoleDefinitions** no arquivo de configuração de sessão usado para registrar o ponto de extremidade.

Por padrão, quando um ponto de extremidade JEA tem várias capacidades de função, a ACL do WinRM é configurada para permitir o acesso a todos os usuários mapeados. Por exemplo, uma sessão JEA configurada que usa os comandos a seguir permite acesso completo a `CONTOSO\JEA_Lev1` e `CONTOSO\JEA_Lev2`.

```powershell
$roles = @{ 'CONTOSO\JEA_Lev1' = 'Lev1Role'; 'CONTOSO\JEA_Lev2' = 'Lev2Role' }
New-PSSessionConfigurationFile -Path '.\jea.pssc' -SessionType RestrictedRemoteServer -RoleDefinitions $roles -RunAsVirtualAccount
Register-PSSessionConfiguration -Path '.\jea.pssc' -Name 'MyJEAEndpoint'
```

Você pode auditar as permissões de usuário com o cmdlet [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration).

```powershell
Get-PSSessionConfiguration -Name 'MyJEAEndpoint' | Select-Object Permission
```

```Output
Permission
----------
CONTOSO\JEA_Lev1 AccessAllowed
CONTOSO\JEA_Lev2 AccessAllowed
```

Para alterar quais usuários têm acesso, execute `Set-PSSessionConfiguration -Name 'MyJEAEndpoint' -ShowSecurityDescriptorUI` para um prompt interativo ou `Set-PSSessionConfiguration -Name 'MyJEAEndpoint' -SecurityDescriptorSddl <SDDL string>` para atualizar as permissões. Os usuários precisam, pelo menos, de direitos de *Invocar* para acessar o ponto de extremidade JEA.

É possível criar um ponto de extremidade JEA que não mapeia uma função definida para cada usuário que tem acesso. Esses usuários podem iniciar uma sessão JEA, mas só têm acesso aos cmdlets padrão. Você pode auditar as permissões de usuário em um ponto de extremidade JEA executando o `Get-PSSessionCapability`. Para obter mais informações, confira [Auditoria e relatórios no JEA](audit-and-report.md).

## <a name="least-privilege-roles"></a>Funções de privilégio mínimo

Durante a criação de funções JEA, é importante lembrar que as contas virtuais e as contas de serviço gerenciado de grupo executadas em segundo plano têm acesso irrestrito ao computador local. As capacidades de função JEA ajudam a limitar os comandos e os aplicativos que podem ser executados nesse contexto privilegiado.
As funções projetadas de modo inadequado podem permitir comandos perigosos que, por sua vez, podem permitir que um usuário ultrapasse os limites do JEA ou obtenha acesso a informações confidenciais.

Por exemplo, considere a seguinte entrada de capacidade de função:

```powershell
@{
    VisibleCmdlets = 'Microsoft.PowerShell.Management\*-Process'
}
```

Essa capacidade de função permite que os usuários executem cmdlets do PowerShell com o substantivo **Process** do módulo **Microsoft.PowerShell.Management**. Os usuários podem precisar acessar cmdlets como `Get-Process` para ver quais aplicativos estão sendo executados no sistema e `Stop-Process` para encerrar os aplicativos que não esteja respondendo. No entanto, essa entrada também permite o `Start-Process`, que pode ser usado para iniciar um programa arbitrário com permissões de administrador completas. O programa não precisa ser instalado localmente no sistema. Um usuário conectado pode iniciar um programa em um compartilhamento de arquivo que concede privilégios de administrador local ao usuário, executa malware, entre outros.

Uma versão muito mais segura desse mesma capacidade de função seria:

```powershell
@{
    VisibleCmdlets = 'Microsoft.PowerShell.Management\Get-Process', 'Microsoft.PowerShell.Management\Stop-Process'
}
```

Evite usar curingas em capacidades de função. Lembre-se de [auditar regularmente as permissões efetivas de usuário](audit-and-report.md#check-effective-rights-for-a-specific-user) para entender quais comandos estão disponíveis para o usuário.

## <a name="jea-doesnt-protect-against-admins"></a>O JEA não oferece proteção contra administradores

Um dos princípios básicos do JEA é que ele permite que não administradores executem algumas tarefas de administrador. O JEA não oferece proteção contra os usuários que já têm privilégios de administrador. Os usuários que pertencem ao grupo **Administradores do Domínio**, ao grupo local de **administradores** ou a outros grupos altamente privilegiados podem burlar as proteções do JEA por outros meios. Por exemplo, eles podem entrar com o RDP, usar consoles remotos do MMC ou se conectar aos pontos de extremidade irrestritos do PowerShell. Além disso, os administradores locais em um sistema podem modificar as configurações do JEA para permitir usuários adicionais ou alterar uma capacidade de função para estender o escopo do que um usuário pode fazer em sua sessão JEA. É importante avaliar as permissões estendidas dos usuários JEA para ver se existem outras maneiras de obter acesso privilegiado ao sistema.

Uma prática comum é usar o JEA para a manutenção de rotina e ter uma solução de gerenciamento de acesso privilegiado just-in-time que permita que os usuários se tornem administradores locais temporariamente em situações de emergência. Isso ajuda a garantir que os usuários não sejam administradores permanentes no sistema, mas possam obter esses direitos se concluírem um fluxo de trabalho que documente o uso dessas permissões e somente quando fizerem isso.
