---
description: Descreve os parâmetros que podem ser usados com qualquer cmdlet.
Locale: en-US
ms.date: 11/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_commonparameters?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CommonParameters
ms.openlocfilehash: 44503e9c251cd3cccf9b879ceb71262c65d8e5e9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599028"
---
# <a name="about-commonparameters"></a>Sobre CommonParameters

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve os parâmetros que podem ser usados com qualquer cmdlet.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Os parâmetros comuns são um conjunto de parâmetros de cmdlet que você pode usar com qualquer cmdlet. Eles são implementados pelo PowerShell, não pelo desenvolvedor de cmdlets e estão automaticamente disponíveis para qualquer cmdlet.

Você pode usar os parâmetros comuns com qualquer cmdlet, mas eles podem não ter um efeito sobre todos os cmdlets. Por exemplo, se um cmdlet não gerar nenhuma saída detalhada, o uso do parâmetro comum **Verbose** não terá nenhum efeito.

Os parâmetros comuns também estão disponíveis em funções avançadas que usam o atributo **CmdletBinding** ou o atributo de **parâmetro** .

Vários parâmetros comuns substituem os padrões ou as preferências do sistema que você define usando as variáveis de preferência do PowerShell. Ao contrário das variáveis de preferência, os parâmetros comuns afetam apenas os comandos nos quais eles são usados.

Para obter mais informações, consulte [about_Preference_Variables](./about_Preference_Variables.md).

A lista a seguir exibe os parâmetros comuns. Seus aliases são listados entre parênteses.

- **Debug** (db)
- **Erroaction** (ea)
- **ErrorVariable** (EV)
- **Informationaction** (infa)
- **InformationVariable** (IV)
- **Outvariance** (OV)
- **OutBuffer** (OB)
- **PipelineVariable** (PV)
- **Detalhado** (VB)
- **Avisoaction** (WA)
- **WarningVariable** (WV)

Os parâmetros de **ação** são valores de tipo **preferência** .
**Preferência** é uma enumeração com os seguintes valores:

| Nome             | Valor |
|------------------|-------|
| Suspend          | 5     |
| Ignorar           | 4     |
| Consultar          | 3     |
| Continuar         | 2     |
| Parar             | 1     |
| SilentlyContinue | 0     |

Você pode usar o nome ou o valor com o parâmetro.

Além dos parâmetros comuns, muitos cmdlets oferecem parâmetros de mitigação de risco. Os cmdlets que envolvem o risco para o sistema ou para os dados do usuário geralmente oferecem esses parâmetros.

Os parâmetros de mitigação de risco são:

- **WhatIf** (Wi)
- **Confirmar** (CF)

### <a name="common-parameter-descriptions"></a>DESCRIÇÕES DE PARÂMETROS COMUNS

#### <a name="debug"></a>Depurar

Exibe detalhes no nível do programador sobre a operação feita pelo comando. Esse parâmetro funciona somente quando o comando gera uma mensagem de depuração. Por exemplo, esse parâmetro funciona quando um comando contém o `Write-Debug` cmdlet.

```yaml
Type: SwitchParameter
Aliases: db

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

Por padrão, as mensagens de depuração não são exibidas porque o valor da `$DebugPreference` variável é **SilentlyContinue**.

No modo interativo, o parâmetro **debug** substitui o valor da `$DebugPreference` variável para o comando atual, definindo o valor de `$DebugPreference` para **inquire**.

No modo não interativo, o parâmetro de **depuração** substitui o valor da `$DebugPreference` variável para o comando atual, definindo o valor de `$DebugPreference` para **continuar**.

`-Debug:$true` tem o mesmo efeito que `-Debug` . Use `-Debug:$false` para suprimir a exibição de mensagens de depuração quando `$DebugPreference` não for **SilentlyContinue**, que é o padrão.

#### <a name="erroraction"></a>ErrorAction

Determina como o cmdlet responde a um erro de não finalização do comando.
Esse parâmetro funciona somente quando o comando gera um erro de não finalização, como os do `Write-Error` cmdlet.

```yaml
Type: ActionPreference
Aliases: ea
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

O parâmetro **ErrorAction** substitui o valor da `$ErrorActionPreference` variável para o comando atual. Como o valor padrão da `$ErrorActionPreference` variável é **continue**, as mensagens de erro são exibidas e a execução continua, a menos que você use o parâmetro **ErrorAction** .

O parâmetro **ErrorAction** não tem nenhum efeito sobre erros de encerramento (como dados ausentes, parâmetros que não são válidos ou permissões insuficientes) que impedem que um comando seja concluído com êxito.

`-ErrorAction:Continue` Exiba a mensagem de erro e continue executando o comando. `Continue` é o padrão.

`-ErrorAction:Ignore` suprime a mensagem de erro e continua executando o comando. Ao contrário de **SilentlyContinue**, **ignorar** não adiciona a mensagem de erro à `$Error` variável automática. O valor de **ignorar** é introduzido no PowerShell 3,0.

`-ErrorAction:Inquire` exibe a mensagem de erro e solicita a confirmação antes de continuar a execução. Esse valor raramente é usado.

`-ErrorAction:SilentlyContinue` suprime a mensagem de erro e continua executando o comando.

`-ErrorAction:Stop` exibe a mensagem de erro e para a execução do comando.

`-ErrorAction:Suspend` Só está disponível para fluxos de trabalho que não têm suporte no PowerShell 6 e posteriores.

> [!NOTE]
> O parâmetro **ErrorAction** substitui, mas não substitui o valor da variável de `$ErrorAction` preferência quando o parâmetro é usado em um comando para executar um script ou uma função.

#### <a name="errorvariable"></a>ErrorVariable

O **ErrorVariable** armazena mensagens de erro sobre o comando na variável especificada e na `$Error` variável automática. Para obter mais informações, confira [about_Automatic_Variables](about_Automatic_Variables.md)

```yaml
Type: String
Aliases: ev

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Por padrão, novas mensagens de erro substituem mensagens de erro que já estão armazenadas na variável. Para acrescentar a mensagem de erro ao conteúdo da variável, digite um sinal de adição ( `+` ) antes do nome da variável.

Por exemplo, o comando a seguir cria a `$a` variável e, em seguida, armazena todos os erros nela:

```powershell
Get-Process -Id 6 -ErrorVariable a
```

O comando a seguir adiciona todas as mensagens de erro à `$a` variável:

```powershell
Get-Process -Id 2 -ErrorVariable +a
```

O comando a seguir exibe o conteúdo de `$a` :

```powershell
$a
```

Você pode usar esse parâmetro para criar uma variável que contém apenas mensagens de erro de comandos específicos e não afeta o comportamento da `$Error` variável automática. A `$Error` variável automática contém mensagens de erro de todos os comandos na sessão. Você pode usar a notação de matriz, como `$a[0]` ou `$error[1,2]` para se referir a erros específicos armazenados nas variáveis.

> [!NOTE]
> A variável de erro personalizada contém todos os erros gerados pelo comando, incluindo erros de chamadas para funções aninhadas ou scripts.

#### <a name="informationaction"></a>InformationAction

Introduzido no PowerShell 5,0. No comando ou script em que é usado, o parâmetro Common **informationaction** substitui o valor da `$InformationPreference` variável de preferência, que por padrão é definido como **SilentlyContinue**. Quando você usa o `Write-Information` em um script com **informationaction**, `Write-Information` os valores são mostrados dependendo do valor do parâmetro **informationaction** . Para obter mais informações sobre o `$InformationPreference` , consulte [about_Preference_Variables](./about_Preference_Variables.md).

```yaml
Type: ActionPreference
Aliases: ia
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

`-InformationAction:Stop` interrompe um comando ou script em uma ocorrência do `Write-Information` comando.

`-InformationAction:Ignore` suprime a mensagem informativa e continua executando o comando. Ao contrário de **SilentlyContinue**, **ignorar** se esquece completamente da mensagem informativa; Ele não adiciona a mensagem informativa ao fluxo de informações.

`-InformationAction:Inquire` exibe a mensagem informativa que você especifica em um `Write-Information` comando e pergunta se deseja continuar.

`-InformationAction:Continue` exibe a mensagem informativa e continua em execução.

`-InformationAction:Suspend` Não tem suporte no PowerShell Core porque ele só está disponível para fluxos de trabalho.

`-InformationAction:SilentlyContinue` nenhum efeito, pois a mensagem informativa não é exibida (padrão) e o script continua sem interrupção.

> [!NOTE]
> O parâmetro **informationaction** substitui, mas não substitui o valor da variável de `$InformationAction` preferência quando o parâmetro é usado em um comando para executar um script ou uma função.

#### <a name="informationvariable"></a>InformationVariable

Introduzido no PowerShell 5,0. No comando ou script em que é usado, o parâmetro comum **InformationVariable** armazena em uma variável uma cadeia de caracteres que você especifica adicionando o `Write-Information` comando. `Write-Information` os valores são mostrados dependendo do valor do parâmetro de **informationaction** comum; Se você não adicionar o parâmetro Common **Reinformationaction** , as `Write-Information` cadeias de caracteres serão mostradas dependendo do valor da `$InformationPreference` variável de preferência. Para obter mais informações sobre o `$InformationPreference` , consulte [about_Preference_Variables](./about_Preference_Variables.md).

> [!NOTE]
> A variável Information contém todas as mensagens de informações geradas pelo comando, incluindo mensagens de informações de chamadas para funções aninhadas ou scripts.

```yaml
Type: String
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

#### <a name="outbuffer"></a>OutBuffer

Determina o número de objetos a serem acumulados em um buffer antes que qualquer objeto seja enviado por meio do pipeline. Se você omitir esse parâmetro, os objetos serão enviados conforme eles forem gerados.

```yaml
Type: Int32
Aliases: ob

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Esse parâmetro de gerenciamento de recursos foi projetado para usuários avançados. Quando você usa esse parâmetro, o PowerShell envia dados para o próximo cmdlet em lotes de `OutBuffer + 1` .

As alternativas de exemplo a seguir são exibidas entre `ForEach-Object` os blocos de processo que usam o `Write-Host` cmdlet. As alternativas de exibição em lotes de 2 ou `OutBuffer + 1` .

```powershell
1..4 | ForEach-Object {
        Write-Host "$($_): First"; $_
      } -OutBuffer 1 | ForEach-Object {
                        Write-Host "$($_): Second" }
```

```Output
1: First
2: First
1: Second
2: Second
3: First
4: First
3: Second
4: Second
```

#### <a name="outvariable"></a>OutVariable

Armazena objetos de saída do comando na variável especificada, além de enviar a saída ao longo do pipeline.

```yaml
Type: String
Aliases: ov

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Para adicionar a saída à variável, em vez de substituir qualquer saída que já possa estar armazenada lá, digite um sinal de adição ( `+` ) antes do nome da variável.

Por exemplo, o comando a seguir cria a `$out` variável e armazena o objeto de processo nele:

```powershell
Get-Process PowerShell -OutVariable out
```

O comando a seguir adiciona o objeto de processo à `$out` variável:

```powershell
Get-Process iexplore -OutVariable +out
```

O comando a seguir exibe o conteúdo da `$out` variável:

```powershell
$out
```

> [!NOTE]
> A variável criada pelo parâmetro **Outvariance** é um `[System.Collections.ArrayList]` .

#### <a name="pipelinevariable"></a>PipelineVariable

**PipelineVariable** armazena o valor do elemento de pipeline atual como uma variável, para qualquer comando nomeado conforme ele flui pelo pipeline.

```yaml
Type: String
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Os valores válidos são cadeias de caracteres, o mesmo que para qualquer nome de variável.

Veja a seguir um exemplo de como o **PipelineVariable** funciona. Neste exemplo, o parâmetro **PipelineVariable** é adicionado a um `Foreach-Object` comando para armazenar os resultados do comando em variáveis. Um intervalo de números, de 1 a 10, são canalizados para o primeiro `Foreach-Object` comando, os resultados dos quais são armazenados em uma variável chamada **Left**.

Os resultados do primeiro `Foreach-Object` comando são canalizados para um segundo `Foreach-Object` comando, que filtra os objetos retornados pelo primeiro `Foreach-Object` comando. Os resultados do segundo comando são armazenados em uma variável chamada **Right**.

No terceiro `Foreach-Object` comando, os resultados dos dois primeiros `Foreach-Object` comandos canalizados, representados pelas variáveis **Left** e **Right**, são processados usando um operador de multiplicação. O comando instrui os objetos armazenados nas variáveis **esquerda** e **direita** a serem multiplicados e especifica que os resultados devem ser exibidos como "membro do intervalo esquerdo * membro do intervalo direito = produto".

```powershell
1..10 | Foreach-Object -PipelineVariable Left -Process { $_ } |
  Foreach-Object -PV Right -Process { 1..10 } |
  Foreach-Object -Process { "$Left * $Right = " + ($Left*$Right) }
```

```output
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
...
```

#### <a name="verbose"></a>Detalhado

Exibe informações detalhadas sobre a operação feita pelo comando. Essas informações se assemelham às informações em um rastreamento ou em um log de transações. Esse parâmetro funciona somente quando o comando gera uma mensagem detalhada. Por exemplo, esse parâmetro funciona quando um comando contém o `Write-Verbose` cmdlet.

```yaml
Type: SwitchParameter
Aliases: vb

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

O parâmetro **Verbose** substitui o valor da `$VerbosePreference` variável para o comando atual. Como o valor padrão da `$VerbosePreference` variável é **SilentlyContinue**, as mensagens detalhadas não são exibidas por padrão.

`-Verbose:$true` tem o mesmo efeito que `-Verbose`

`-Verbose:$false` suprime a exibição de mensagens detalhadas. Use esse parâmetro quando o valor de `$VerbosePreference` não for **SilentlyContinue** (o padrão).

#### <a name="warningaction"></a>WarningAction

Determina como o cmdlet responde a um aviso do comando. **Continue** é o valor padrão. Esse parâmetro funciona somente quando o comando gera uma mensagem de aviso. Por exemplo, esse parâmetro funciona quando um comando contém o `Write-Warning` cmdlet.

```yaml
Type: ActionPreference
Aliases: wa
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

O parâmetro **WarningAction** substitui o valor da `$WarningPreference` variável para o comando atual. Como o valor padrão da `$WarningPreference` variável é **continue**, os avisos são exibidos e a execução continua, a menos que você use o parâmetro **WarningAction** .

`-WarningAction:Continue` exibe as mensagens de aviso e continua executando o comando. `Continue` é o padrão.

`-WarningAction:Inquire` exibe a mensagem de aviso e solicita sua confirmação antes de continuar a execução. Esse valor raramente é usado.

`-WarningAction:SilentlyContinue` suprime a mensagem de aviso e continua executando o comando.

`-WarningAction:Stop` exibe a mensagem de aviso e para a execução do comando.

> [!NOTE]
> O parâmetro **WarningAction** substitui, mas não substitui o valor da variável de `$WarningAction` preferência quando o parâmetro é usado em um comando para executar um script ou uma função.

#### <a name="warningvariable"></a>WarningVariable

Armazena avisos sobre o comando na variável especificada.

```yaml
Type: String
Aliases: wv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Todos os avisos gerados são salvos na variável, mesmo se os avisos não forem exibidos para o usuário.

Para acrescentar os avisos ao conteúdo da variável, em vez de substituir os avisos que já podem estar armazenados lá, digite um sinal de adição ( `+` ) antes do nome da variável.

Por exemplo, o comando a seguir cria a `$a` variável e, em seguida, armazena todos os avisos nela:

```powershell
Get-Process -Id 6 -WarningVariable a
```

O comando a seguir adiciona quaisquer avisos à `$a` variável:

```powershell
Get-Process -Id 2 -WarningVariable +a
```

O comando a seguir exibe o conteúdo de `$a` :

```powershell
$a
```

Você pode usar esse parâmetro para criar uma variável que contém apenas avisos de comandos específicos. Você pode usar a notação de matriz, como `$a[0]` ou `$warning[1,2]` para se referir a avisos específicos armazenados na variável.

> [!NOTE]
> A variável de aviso contém todos os avisos gerados pelo comando, incluindo avisos de chamadas para funções aninhadas ou scripts.

### <a name="risk-management-parameter-descriptions"></a>Descrições de parâmetros de gerenciamento de riscos

#### <a name="whatif"></a>WhatIf

Exibe uma mensagem que descreve o efeito do comando, em vez de executar o comando.

```yaml
Type: SwitchParameter
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

O parâmetro **WhatIf** substitui o valor da `$WhatIfPreference` variável para o comando atual. Como o valor padrão da `$WhatIfPreference` variável é 0 (desabilitado), o comportamento de **WhatIf** não é feito sem o parâmetro **WhatIf** . Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md)

`-WhatIf:$true` tem o mesmo efeito que `-WhatIf` .

`-WhatIf:$false` suprime o comportamento de WhatIf automático que resulta quando o valor da `$WhatIfPreference` variável é 1.

Por exemplo, o comando a seguir usa o `-WhatIf` parâmetro em um `Remove-Item` comando:

```powershell
Remove-Item Date.csv -WhatIf
```

Em vez de remover o item, o PowerShell lista as operações que ele faria e os itens que seriam afetados. Esse comando gera a seguinte saída:

```output
What if: Performing operation "Remove File" on
Target "C:\ps-test\date.csv".
```

#### <a name="confirm"></a>Confirmar

Solicita sua confirmação antes de executar o comando.

```yaml
Type: SwitchParameter
Aliases: cf

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

O parâmetro **Confirm** substitui o valor da `$ConfirmPreference` variável para o comando atual. O valor padrão é true. Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md)

`-Confirm:$true` tem o mesmo efeito que `-Confirm` .

`-Confirm:$false` suprime a confirmação automática, que ocorre quando o valor de `$ConfirmPreference` é menor ou igual ao risco estimado do cmdlet.

Por exemplo, o comando a seguir usa o parâmetro **Confirm** com um `Remove-Item` comando. Antes de remover o item, o PowerShell lista as operações que ele faria e os itens que seriam afetados e solicita aprovação.

```
PS C:\ps-test> Remove-Item tmp*.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target " C:\ps-test\tmp1.txt
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

As opções de confirmação de resposta são as seguintes:

|Resposta       |Result                                                     |
|---------------|-----------------------------------------------------------|
|Sim (Y)        |Execute a ação.                                        |
|Sim para todos (A) |Executar todas as ações e suprimir consultas de confirmação subsequentes|
|               |para este comando.                                          |
|Não (N):        |Não execute a ação.                                 |
|Não para todos (L): |Não executar nenhuma ação e suprimir a confirmação subsequente |
|               |consultas para este comando.                                  |
|Suspender (S):   |Pause o comando e crie uma sessão temporária.          |
|Ajuda (?)       |Exibir a ajuda para essas opções.                            |

A opção **suspender** coloca o comando em espera e cria uma sessão aninhada temporária na qual você pode trabalhar até que você esteja pronto para escolher uma opção de **confirmação** . O prompt de comando para a sessão aninhada tem dois acentos extras (>>) para indicar que é uma operação filho do comando pai original. Você pode executar comandos e scripts na sessão aninhada. Para encerrar a sessão aninhada e retornar às opções de confirmação do comando original, digite "Exit".

No exemplo a seguir, as opções de **suspensão** são usadas para interromper um comando temporariamente enquanto o usuário verifica a ajuda de um parâmetro de comando. Depois de obter as informações necessárias, o usuário digita "Exit" para finalizar o prompt aninhado e, em seguida, seleciona a resposta Sim (y) à consulta confirmar.

```
PS C:\ps-test> New-Item -ItemType File -Name Test.txt -Confirm

Confirm
Are you sure you want to perform this action?

Performing operation "Create File" on Target "Destination:
C:\ps-test\test.txt".
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default
is "Y"): s

PS C:\ps-test> Get-Help New-Item -Parameter ItemType

-ItemType <string>
Specifies the provider-specified type of the new item.

Required?                    false
Position?                    named
Default value
Accept pipeline input?       true (ByPropertyName)
Accept wildcard characters?  false

PS C:\ps-test> exit

Confirm
Are you sure you want to perform this action?
Performing operation "Create File" on Target "Destination: C:\ps-test\test
.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (defau
lt is "Y"): y

Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         8/27/2010   2:41 PM          0 test.txt
```

## <a name="keywords"></a>Palavras-chave

about_Common_Parameters

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Preference_Variables](about_Preference_Variables.md)

[Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)

[Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning)

[Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error)

[Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)

