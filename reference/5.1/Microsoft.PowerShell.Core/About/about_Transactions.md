---
description: Descreve como gerenciar operações transacionadas no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_transactions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Transactions
ms.openlocfilehash: 522e0f727754b0b0153571039f3bf3966d0abf20
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195954"
---
# <a name="about-transactions"></a>Sobre transações

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve como gerenciar operações transacionadas no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

As transações têm suporte no PowerShell a partir do PowerShell 2,0. Esse recurso permite que você inicie uma transação, para indicar quais comandos fazem parte da transação e para confirmar ou reverter uma transação.

## <a name="about-transactions"></a>SOBRE TRANSAÇÕES

No PowerShell, uma transação é um conjunto de um ou mais comandos que são gerenciados como uma unidade lógica. Uma transação pode ser concluída ("confirmada"), que altera os dados afetados pela transação. Ou, uma transação pode ser completamente desfeita ("revertida") para que os dados afetados não sejam alterados pela transação.

Como os comandos em uma transação são gerenciados como uma unidade, todos os comandos são confirmados ou todos os comandos são revertidos.

As transações são amplamente usadas no processamento de dados, mais notavelmente em operações de banco e transações financeiras. As transações são usadas com mais frequência quando o cenário de pior caso para um conjunto de comandos não é que todas elas falham, mas que alguns comandos tenham êxito enquanto outros falham, deixando o sistema em um estado danificado, falso ou não interpretável que seja difícil de reparar.

## <a name="transaction-cmdlets"></a>CMDLETS DE TRANSAÇÃO

O PowerShell inclui vários cmdlets projetados para gerenciar transações.

- Start-Transaction: inicia uma nova transação.
- Use-Transaction: Adiciona um comando ou uma expressão à transação. O comando deve usar objetos habilitados para transação.
- Undo-Transaction: reverte a transação para que nenhum dado seja alterado pela transação.
- Complete-Transaction: confirma a transação. Os dados afetados pela transação são alterados.
- Get-Transaction: Obtém informações sobre a transação ativa.

Para obter uma lista de cmdlets de transação, digite:

```powershell
get-command *transaction
```

Para obter informações detalhadas sobre os cmdlets, digite:

```powershell
get-help use-transaction -detailed
```

## <a name="transaction-enabled-elements"></a>ELEMENTOS HABILITADOS PARA TRANSAÇÃO

Para participar de uma transação, o cmdlet e o provedor devem dar suporte a transações. Esse recurso é integrado aos objetos afetados pela transação.

O provedor de registro do PowerShell dá suporte a transações no Windows Vista. O objeto transacionastring (Microsoft. PowerShell. Commands. Management. transacionastring) funciona com qualquer sistema operacional que executa o PowerShell.

Outros provedores do PowerShell podem dar suporte a transações. Para localizar os provedores do PowerShell em sua sessão que dão suporte a transações, use o seguinte comando para localizar o valor de "transações" na propriedade Capabilities dos provedores:

```powershell
get-psprovider | where {$_.Capabilities -like "*transactions*"}
```

Para obter mais informações sobre um provedor, consulte a ajuda do provedor. Para obter ajuda do provedor, digite:

```
get-help <provider-name>
```

Por exemplo, para obter Ajuda para o provedor de Registro, digite:

```powershell
get-help registry
```

## <a name="the-usetransaction-parameter"></a>O PARÂMETRO USETRANSACTION

Os cmdlets que podem dar suporte a transações têm um parâmetro UseTransaction. Esse parâmetro inclui o comando na transação ativa. Você pode usar o nome completo do parâmetro ou seu alias, "usetx".

O parâmetro pode ser usado somente quando a sessão contiver uma transação ativa. Se você inserir um comando com o parâmetro UseTransaction quando não houver nenhuma transação ativa, o comando falhará.

Para localizar cmdlets com o parâmetro UseTransaction, digite:

```powershell
get-help * -parameter UseTransaction
```

No PowerShell Core, todos os cmdlets projetados para trabalhar com provedores do PowerShell dão suporte a transações. Como resultado, você pode usar os cmdlets do provedor para gerenciar transações.

Para obter mais informações sobre provedores do PowerShell, consulte [about_Providers](about_Providers.md).

## <a name="the-transaction-object"></a>O OBJETO DE TRANSAÇÃO

As transações são representadas no PowerShell por um objeto de transação, System. Management. Automation. Transaction.

O objeto tem as seguintes propriedades:

- RollbackPreference: contém a preferência de reversão definida para a transação atual. Você pode definir a preferência de reversão ao usar Start-Transaction para iniciar a transação.

  A preferência de reversão determina as condições sob as quais a transação é revertida automaticamente. Os valores válidos são Error, TerminatingError e Never. O valor padrão é Error.

- Status: contém o status atual da transação. Os valores válidos são ativo, confirmado e revertida.

- SubscriberCount: contém o número de assinantes para a transação. Um assinante é adicionado a uma transação quando você inicia uma transação enquanto outra transação está em andamento. A contagem de assinantes é decrementada quando um assinante confirma a transação.

## <a name="active-transactions"></a>TRANSAÇÕES ATIVAS

No PowerShell, apenas uma transação está ativa por vez e você pode gerenciar apenas a transação ativa. Várias transações podem estar em andamento na mesma sessão ao mesmo tempo, mas apenas a transação iniciada mais recentemente está ativa.

Como resultado, você não pode especificar uma transação específica ao usar os cmdlets de transação. Os comandos sempre se aplicam à transação ativa.

Isso é mais evidente no comportamento do cmdlet Get-Transaction. Quando você insere um comando de Get-Transaction, Get-Transaction sempre obtém apenas um objeto de transação. Esse objeto é o objeto que representa a transação ativa.

Para gerenciar uma transação diferente, você deve primeiro concluir a transação ativa, confirmando-a ou Redistribuindo-a. Quando você faz isso, a transação anterior torna-se ativa automaticamente. As transações se tornam ativas na ordem inversa da qual elas são iniciadas, para que a transação iniciada mais recentemente esteja sempre ativa.

## <a name="subscribers-and-independent-transactions"></a>ASSINANTES E TRANSAÇÕES INDEPENDENTES

Se você iniciar uma transação enquanto outra transação estiver em andamento, por padrão, o PowerShell não iniciará uma nova transação. Em vez disso, ele adiciona um "assinante" à transação atual.

Quando uma transação tem vários assinantes, um único comando Undo-Transaction a qualquer momento reverte a transação inteira para todos os assinantes. No entanto, para confirmar a transação, você deve inserir um comando Complete-Transaction para cada Assinante.

Para localizar o número de assinantes de uma transação, verifique a propriedade SubscriberCount do objeto de transação. Por exemplo, o comando a seguir usa o cmdlet Get-Transaction para obter o valor da propriedade SubscriberCount da transação ativa:

```powershell
(Get-Transaction).SubscriberCount
```

Adicionar um assinante é o comportamento padrão porque a maioria das transações iniciadas enquanto outra transação está em andamento está relacionada à transação original. No modelo típico, um script que contém uma transação chama um script auxiliar que contém sua própria transação. Como as transações estão relacionadas, elas devem ser revertidas ou confirmadas como uma unidade.

No entanto, você pode iniciar uma transação que é independente da transação atual usando o parâmetro independente do cmdlet Start-Transaction.

Quando você inicia uma transação independente, o Start-Transaction cria um novo objeto de transação e a nova transação se torna a transação ativa.
A transação independente pode ser confirmada ou revertida sem afetar a transação original.

Quando a transação independente for concluída (confirmada ou revertida), a transação original se tornará a transação ativa novamente.

## <a name="changing-data"></a>ALTERANDO DADOS

Quando você usa transações para alterar dados, os dados que são afetados pela transação não são alterados até que você confirme a transação. No entanto, os mesmos dados podem ser alterados por comandos que não fazem parte da transação.

Tenha isso em mente ao usar transações para gerenciar dados compartilhados.
Normalmente, os bancos de dados têm mecanismos que bloqueiam os dados enquanto você trabalha nele, impedindo que outros usuários e outros comandos, scripts e funções alterem a alteração.

No entanto, o bloqueio é um recurso do banco de dados. Ele não está relacionado a transações. Se você estiver trabalhando em um sistema de arquivos habilitado para transação ou em outro armazenamento de dados, os dados poderão ser alterados enquanto a transação estiver em andamento.

## <a name="examples"></a>EXEMPLOS

Os exemplos nesta seção usam o provedor de registro do PowerShell e pressupõem que você esteja familiarizado com ele. Para obter informações sobre o provedor de registro, digite "Get-Help Registry".

### <a name="example-1-committing-a-transaction"></a>EXEMPLO 1: CONFIRMANDO UMA TRANSAÇÃO

Para criar uma transação, use o cmdlet Start-Transaction. O comando a seguir inicia uma transação com as configurações padrão.

```powershell
start-transaction
```

Para incluir comandos na transação, use o parâmetro UseTransaction do cmdlet. Por padrão, os comandos não são incluídos na transação,

Por exemplo, o comando a seguir, que define o local atual na chave de software da unidade HKCU:, não está incluído na transação.

```powershell
cd hkcu:\Software
```

O comando a seguir, que cria a chave MyCompany, usa o parâmetro UseTransaction do cmdlet New-Item para incluir o comando na transação ativa.

```powershell
new-item MyCompany -UseTransaction
```

O comando retorna um objeto que representa a nova chave, mas como o comando faz parte da transação, o registro ainda não foi alterado.

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyCompany                      {}
```

Para confirmar a transação, use o cmdlet Complete-Transaction. Como ele sempre afeta a transação ativa, você não pode especificar a transação.

```powershell
complete-transaction
```

Como resultado, a chave MyCompany é adicionada ao registro.

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-2-rolling-back-a-transaction"></a>EXEMPLO 2: REVERTER UMA TRANSAÇÃO

Para criar uma transação, use o cmdlet Start-Transaction. O comando a seguir inicia uma transação com as configurações padrão.

```powershell
start-transaction
```

O comando a seguir, que cria a chave MyOtherCompany, usa o parâmetro UseTransaction do cmdlet New-Item para incluir o comando na transação ativa.

```powershell
new-item MyOtherCompany -UseTransaction
```

O comando retorna um objeto que representa a nova chave, mas como o comando faz parte da transação, o registro ainda não foi alterado.

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyOtherCompany                 {}
```

Para reverter a transação, use o cmdlet Undo-Transaction. Como ele sempre afeta a transação ativa, você não especifica a transação.

```powershell
Undo-transaction
```

O resultado é que a chave MyOtherCompany não é adicionada ao registro.

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-3-previewing-a-transaction"></a>EXEMPLO 3: VISUALIZANDO UMA TRANSAÇÃO

Normalmente, os comandos usados em uma transação alteram dados. No entanto, os comandos que obtêm dados também são úteis em uma transação, pois eles obtêm dados dentro da transação. Isso fornece uma visualização das alterações que a confirmação da transação causaria.

O exemplo a seguir mostra como usar o comando Get-ChildItem (o alias é "dir") para visualizar as alterações em uma transação.

O comando a seguir inicia uma transação.

```powershell
start-transaction
```

O comando a seguir usa o cmdlet New-ItemProperty para adicionar a entrada de Registro MyKey à chave MyCompany. O comando usa o parâmetro UseTransaction para incluir o comando na transação.

```powershell
new-itemproperty -path MyCompany -Name MyKey -value 123 -UseTransaction
```

O comando retorna um objeto que representa a nova entrada do registro, mas a entrada do registro não é alterada.

```
MyKey
-----
123
```

Para obter os itens que estão atualmente no registro, use um comando Get-ChildItem ("dir") sem o parâmetro UseTransaction. O comando a seguir obtém os itens que começam com "M".

```powershell
dir m*
```

O resultado mostra que nenhuma entrada ainda foi adicionada à chave MyCompany.

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

Para visualizar o efeito de confirmar a transação, insira um comando Get-ChildItem ("dir") com o parâmetro UseTransaction. Esse comando tem uma exibição dos dados de dentro da transação.

```powershell
dir m* -useTransaction
```

O resultado mostra que, se a transação for confirmada, a entrada MyKey será adicionada à chave MyCompany.

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   1 MyCompany                      {MyKey}
```

### <a name="example-4-combining-transacted-and-non-transacted-commands"></a>EXEMPLO 4: COMBINANDO COMANDOS TRANSACIONADOS E NÃO TRANSACIONADOS

Você pode inserir comandos não transacionados durante uma transação. Os comandos não transacionados afetam os dados imediatamente, mas eles não afetam a transação.
O comando a seguir inicia uma transação na chave de Registro HKCU: \ Software.

```powershell
start-transaction
```

Os próximos três comandos usam o cmdlet New-Item para adicionar chaves ao registro.
O primeiro e o terceiro comandos usam o parâmetro UseTransaction para incluir os comandos na transação. O segundo comando omite o parâmetro. Como o segundo comando não está incluído na transação, ele entra em vigor imediatamente.

```powershell
new-item MyCompany1 -UseTransaction
new-item MyCompany2
new-item MyCompany3 -UseTransaction
```

Para exibir o estado atual do registro, use um comando Get-ChildItem ("dir") sem o parâmetro UseTransaction. Este comando obtém os itens que começam com "M".

```powershell
dir m*
```

O resultado mostra que a chave MyCompany2 é adicionada ao registro, mas as chaves MyCompany1 e MyCompany3, que fazem parte da transação, não são adicionadas.

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0    0 MyCompany2                     {}
```

O comando a seguir confirma a transação.

```powershell
complete-transaction
```

Agora, as chaves que foram adicionadas como parte da transação aparecem no registro.

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
83   1 Microsoft                      {(default)}
0    0 MyCompany1                     {}
0    0 MyCompany2                     {}
0    0 MyCompany3                     {}
```

### <a name="example-5-using-automatic-rollback"></a>EXEMPLO 5: USANDO A REVERSÃO AUTOMÁTICA

Quando um comando em uma transação gera um erro de qualquer tipo, a transação é automaticamente revertida.

Esse comportamento padrão é projetado para scripts que executam transações. Normalmente, os scripts são bem testados e incluem lógica de tratamento de erros, de modo que os erros não são esperados e devem terminar a transação.

O primeiro comando inicia uma transação na chave de Registro HKCU: \ Software.

```powershell
start-transaction
```

O comando a seguir usa o cmdlet New-Item para adicionar a chave MyCompany ao registro. O comando usa o parâmetro UseTransaction (o alias é "usetx") para incluir o comando na transação.

```powershell
New-Item MyCompany -UseTX
```

Como a chave MyCompany já existe no registro, o comando falha e a transação é revertida.

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

Um comando Get-Transaction confirma que a transação foi revertida e que o SubscriberCount é 0.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 RolledBack
```

### <a name="example-6-changing-the-rollback-preference"></a>EXEMPLO 6: ALTERANDO A PREFERÊNCIA DE REVERSÃO

Se você quiser que a transação seja mais tolerante a erros, poderá usar o parâmetro RollbackPreference de Start-Transaction para alterar a preferência.

O comando a seguir inicia uma transação com uma preferência de reversão de "Never".

```powershell
start-transaction -rollbackpreference Never
```

Nesse caso, quando o comando falhar, a transação não será revertida automaticamente.

```powershell
New-Item MyCompany -UseTX
```

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

Como a transação ainda está ativa, você pode reenviar o comando como parte da transação.

```powershell
New-Item MyOtherCompany -UseTX
```

### <a name="example-7-using-the-use-transaction-cmdlet"></a>EXEMPLO 7: USANDO O CMDLET USE-TRANSACTION

O cmdlet Use-Transaction permite que você faça script direto em objetos da estrutura Microsoft .NET habilitados para transação. Use-Transaction usa um bloco de script que só pode conter comandos e expressões que usam objetos .NET Framework habilitados para transação, como instâncias da classe Microsoft. PowerShell. Commands. Management. transagiustring.

O comando a seguir inicia uma transação.

```powershell
start-transaction
```

O comando a seguir New-Object cria uma instância da classe transacionated e salva-a na variável $t.

```powershell
$t = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
```

O comando a seguir usa o método Append do objeto transacionastring para adicionar texto à cadeia de caracteres. Como o comando não faz parte da transação, a alteração entra em vigor imediatamente.

```powershell
$t.append("Windows")
```

O comando a seguir usa o mesmo método Append para adicionar texto, mas adiciona o texto como parte da transação. O comando é colocado entre chaves e é definido como o valor do parâmetro ScriptBlock de Use-Transaction. O parâmetro UseTransaction (UseTx) é necessário.

```powershell
use-transaction {$t.append(" PowerShell")} -usetx
```

Para ver o conteúdo atual da cadeia de caracteres transacionada em $t, use o método ToString do objeto transacionastring.

```powershell
$t.tostring()
```

A saída mostra que apenas as alterações não transacionadas são efetivas.

```output
Windows
```

Para ver o conteúdo atual da cadeia de caracteres transacionada em $t de dentro da transação, incorpore a expressão em um comando Use-Transaction.

```powershell
use-transaction {$s.tostring()} -usetx
```

A saída mostra o modo de exibição de transação.

```output
PowerShell
```

O comando a seguir confirma a transação.

```powershell
complete-transaction
```

Para ver a cadeia de caracteres final:

```
$t.tostring()
PowerShell
```

### <a name="example-8-managing-multi-subscriber-transactions"></a>EXEMPLO 8: GERENCIANDO TRANSAÇÕES DE VÁRIOS ASSINANTES

Quando você inicia uma transação enquanto outra transação está em andamento, o PowerShell não cria uma segunda transação por padrão. Em vez disso, ele adiciona um assinante à transação atual.

Este exemplo mostra como exibir e gerenciar uma transação de vários assinantes.

Comece iniciando uma transação na chave HKCU: \ Software.

```powershell
start-transaction
```

O comando a seguir usa o comando Get-Transaction para obter a transação ativa.

```powershell
get-transaction
```

O resultado mostra o objeto que representa a transação ativa.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

O comando a seguir adiciona a chave MyCompany ao registro. O comando usa o parâmetro UseTransaction para incluir o comando na transação.

```powershell
new-item MyCompany -UseTransaction
```

O comando a seguir usa o comando Start-Transaction para iniciar uma transação. Embora esse comando seja digitado no prompt de comando, esse cenário é mais provável de acontecer quando você executa um script que contém uma transação.

```powershell
start-transaction
```

Um comando Get-Transaction mostra que a contagem de assinantes no objeto de transação é incrementada. O valor agora é 2.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

O comando a seguir usa o cmdlet New-ItemProperty para adicionar a entrada do Registro MyKey à chave MyCompany. Ele usa o parâmetro UseTransaction para incluir o comando na transação.

```powershell
new-itemproperty -path MyCompany -name MyKey -UseTransaction
```

A chave MyCompany não existe no registro, mas esse comando é executado com sucesso porque os dois comandos fazem parte da mesma transação.

O comando a seguir confirma a transação. Se reverter a transação, a transação seria revertida para todos os assinantes.

```powershell
complete-transaction
```

Um comando Get-Transaction mostra que a contagem de assinantes no objeto de transação é 1, mas o valor de status ainda está ativo (não confirmado).

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

Para concluir a confirmação da transação, insira um segundo comando Complete-Transaction. Para confirmar uma transação de vários assinantes, você deve inserir um comando Complete-Transaction para cada comando Start-Transaction.

```powershell
complete-transaction
```

Outro comando Get-Transaction mostra que a transação foi confirmada.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 Committed
```

### <a name="example-9-managing-independent-transactions"></a>EXEMPLO 9: GERENCIANDO TRANSAÇÕES INDEPENDENTES

Ao iniciar uma transação enquanto outra transação está em andamento, você pode usar o parâmetro independente de Start-Transaction para tornar a nova transação independente da transação original.

Quando você faz isso, Start-Transaction cria um novo objeto de transação e torna a nova transação a transação ativa.

Comece iniciando uma transação na chave HKCU: \\ software.

```powershell
start-transaction
```

O comando a seguir usa o comando Get-Transaction para obter a transação ativa.

```powershell
get-transaction
```

O resultado mostra o objeto que representa a transação ativa.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

O comando a seguir adiciona a chave do Registro MyCompany como parte da transação. Ele usa o parâmetro UseTransaction (UseTx) para incluir o comando na transação ativa.

```powershell
new-item MyCompany -use
```

O comando a seguir inicia uma nova transação. O comando usa o parâmetro independente para indicar que essa transação não é um assinante para a transação ativa.

```powershell
start-transaction -independent
```

Quando você cria uma transação independente, a nova transação (criada mais recentemente) torna-se a transação ativa. Você pode usar um comando Get-Transaction para obter a transação ativa.

```powershell
get-transaction
```

Observe que o SubscriberCount da transação é 1, indicando que não há outros assinantes e que a transação é nova.

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

A nova transação deve ser concluída (confirmada ou revertida) antes que você possa gerenciar a transação original.

O comando a seguir adiciona a chave MyOtherCompany ao registro. Ele usa o parâmetro UseTransaction (UseTx) para incluir o comando na transação ativa.

```powershell
new-item MyOtherCompany -usetx
```

Agora, reverta a transação. Se houver uma única transação com dois assinantes, reverter a transação reverteria toda a transação para todos os assinantes.

No entanto, como essas transações são independentes, a reversão da transação mais recente cancela as alterações do registro e torna a transação original a Transaction ativa.

```powershell
undo-transaction
```

Um comando Get-Transaction confirma que a transação original ainda está ativa na sessão.

```powershell
get-transaction
```

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

O comando a seguir confirma a transação ativa.

```powershell
complete-transaction
```

Um comando Get-ChildItem mostra que o registro foi alterado.

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[Start-Transaction](xref:Microsoft.PowerShell.Management.Start-Transaction)

[Get-Transaction](xref:Microsoft.PowerShell.Management.Get-Transaction)

[Complete-Transaction](xref:Microsoft.PowerShell.Management.Complete-Transaction)

[Undo-Transaction](xref:Microsoft.PowerShell.Management.Undo-Transaction)

[Use-Transaction](xref:Microsoft.PowerShell.Management.Use-Transaction)

[Get-PSProvider](xref:Microsoft.PowerShell.Management.Get-PSProvider)

[Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

[about_Providers](about_Providers.md)
