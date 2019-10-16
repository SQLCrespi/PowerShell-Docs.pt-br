---
title: Diretrizes de desenvolvimento altamente incentivadas | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d68a8f3-fba0-44c5-97b9-9fc191d269a5
caps.latest.revision: 13
ms.openlocfilehash: 0906d0d37c66b8c1538a0b2e9e0f1ff2fba12ac0
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369335"
---
# <a name="strongly-encouraged-development-guidelines"></a>Diretrizes de desenvolvimento altamente recomendadas

Esta seção descreve as diretrizes que você deve seguir ao escrever seus cmdlets. Elas são separadas em diretrizes para criar cmdlets e diretrizes para escrever seu código de cmdlet. Você pode achar que essas diretrizes não são aplicáveis a todos os cenários. No entanto, se eles se aplicarem e você não seguir essas diretrizes, os usuários poderão ter uma experiência ruim ao usar seus cmdlets.

## <a name="design-guidelines"></a>Diretrizes de design

- [Usar um substantivo específico para um nome de cmdlet (SD01)](./strongly-encouraged-development-guidelines.md#use-a-specific-noun-for-a-cmdlet-name-sd01)

- [Usar caso de Pascal para nomes de cmdlet (SD02)](./strongly-encouraged-development-guidelines.md#use-pascal-case-for-cmdlet-names-sd02)

- [Diretrizes de design de parâmetro (SD03)](./strongly-encouraged-development-guidelines.md#parameter-design-guidelines-sd03)

- [Fornecer comentários para o usuário (SD04)](./strongly-encouraged-development-guidelines.md#provide-feedback-to-the-user-sd04)

- [Criar um arquivo de ajuda de cmdlet (SD05)](./strongly-encouraged-development-guidelines.md#create-a-cmdlet-help-file-sd05)

## <a name="code-guidelines"></a>Diretrizes de código

- [Parâmetros de codificação (SC01)](./strongly-encouraged-development-guidelines.md#coding-parameters-sc01)

- [Suporte à entrada de pipeline bem definida (SC02)](./strongly-encouraged-development-guidelines.md#support-well-defined-pipeline-input-sc02)

- [Gravar registros únicos no pipeline (SC03)](./strongly-encouraged-development-guidelines.md#write-single-records-to-the-pipeline-sc03)

- [Tornar cmdlets não diferencia maiúsculas de minúsculas e SC04 (preservação de maiúsculas e minúsculas)](./strongly-encouraged-development-guidelines.md#make-cmdlets-case-insensitive-and-case-preserving-sc04)

## <a name="design-guidelines"></a>Diretrizes de design

As diretrizes a seguir devem ser seguidas durante a criação de cmdlets para garantir uma experiência de usuário consistente entre usar seus cmdlets e outros cmdlets. Quando encontrar uma diretriz de design que se aplique à sua situação, certifique-se de examinar as diretrizes de código para obter diretrizes semelhantes.

### <a name="use-a-specific-noun-for-a-cmdlet-name-sd01"></a>Usar um substantivo específico para um nome de cmdlet (SD01)

Os substantivos usados na nomenclatura de cmdlets precisam ser muito específicos para que o usuário possa descobrir seus cmdlets. Prefixe os substantivos genéricos, como "servidor", por uma versão reduzida do nome do produto. Por exemplo, se um substantivo se referir a um servidor que está executando uma instância do Microsoft SQL Server, use um substantivo como "SQLServer". A combinação de substantivos específicos e a lista curta de verbos aprovados permite que o usuário descubra e antecipe rapidamente a funcionalidade e, ao mesmo tempo, evita a duplicação entre nomes de cmdlets.

Para aprimorar a experiência do usuário, o substantivo que você escolher para um nome de cmdlet deve ser singular. Por exemplo, use o nome `Get-Process` em vez de **Get-Processes**. É melhor seguir essa regra para todos os nomes de cmdlet, mesmo quando é provável que um cmdlet atue em mais de um item.

### <a name="use-pascal-case-for-cmdlet-names-sd02"></a>Usar caso de Pascal para nomes de cmdlet (SD02)

Use o caso do Pascal para nomes de parâmetro. Em outras palavras, coloque a primeira letra do verbo em maiúscula e todos os termos usados no substantivo. Por exemplo, "`Clear-ItemProperty`".

### <a name="parameter-design-guidelines-sd03"></a>Diretrizes de design de parâmetro (SD03)

Um cmdlet precisa de parâmetros que recebem os dados nos quais ele deve operar e parâmetros que indicam informações que são usadas para determinar as características da operação. Por exemplo, um cmdlet pode ter um parâmetro `Name` que recebe dados do pipeline, e o cmdlet pode ter um parâmetro `Force` para indicar que o cmdlet pode ser forçado a executar sua operação. Não há nenhum limite para o número de parâmetros que um cmdlet pode definir.

#### <a name="use-standard-parameter-names"></a>Usar nomes de parâmetro padrão

O cmdlet deve usar nomes de parâmetro padrão para que o usuário possa determinar rapidamente o que significa um determinado parâmetro. Se um nome mais específico for necessário, use um nome de parâmetro padrão e, em seguida, especifique um nome mais específico como um alias. Por exemplo, o cmdlet `Get-Service` tem um parâmetro que tem um nome genérico (`Name`) e um alias mais específico (`ServiceName`). Ambos os termos podem ser usados para especificar o parâmetro.

Para obter mais informações sobre nomes de parâmetro e seus tipos de dados, consulte [diretrizes de funcionalidade e nome de parâmetro de cmdlet](./standard-cmdlet-parameter-names-and-types.md).

#### <a name="use-singular-parameter-names"></a>Usar nomes de parâmetro singulares

Evite usar nomes no plural para parâmetros cujo valor é um único elemento. Isso inclui parâmetros que usam matrizes ou listas porque o usuário pode fornecer uma matriz ou lista com apenas um elemento.

Os nomes de parâmetro plural devem ser usados somente nesses casos em que o valor do parâmetro seja sempre um valor de vários elementos. Nesses casos, o cmdlet deve verificar se vários elementos são fornecidos e o cmdlet deve exibir um aviso para o usuário se vários elementos não forem fornecidos.

#### <a name="use-pascal-case-for-parameter-names"></a>Usar caso de Pascal para nomes de parâmetro

Use o caso do Pascal para nomes de parâmetro. Em outras palavras, coloque em maiúscula a primeira letra de cada palavra no nome do parâmetro, incluindo a primeira letra do nome. Por exemplo, o nome do parâmetro `ErrorAction` usa a capitalização correta. Os seguintes nomes de parâmetro usam capitalização incorreta:

- `errorAction`

- `erroraction`

#### <a name="parameters-that-take-a-list-of-options"></a>Parâmetros que usam uma lista de opções

Há duas maneiras de criar um parâmetro cujo valor pode ser selecionado em um conjunto de opções.

- Defina um tipo de enumeração (ou use um tipo de enumeração existente) que especifique os valores válidos. Em seguida, use o tipo de enumeração para criar um parâmetro desse tipo.

- Adicione o atributo **ValidateSet** à declaração de parâmetro. Para obter mais informações sobre esse atributo, consulte [declaração de atributo ValidateSet](./validateset-attribute-declaration.md).

#### <a name="use-standard-types-for-parameters"></a>Usar tipos padrão para parâmetros

Para garantir a consistência com outros cmdlets, use tipos padrão para parâmetros onde for possível. Para obter mais informações sobre os tipos que devem ser usados para parâmetros diferentes, consulte [tipos e nomes de parâmetro de cmdlet padrão](./standard-cmdlet-parameter-names-and-types.md). Este tópico fornece links para vários tópicos que descrevem os nomes e os tipos de .NET Framework para grupos de parâmetros padrão, como "parâmetros de atividade".

#### <a name="use-strongly-typed-net-framework-types"></a>Usar tipos de .NET Framework fortemente tipados

Os parâmetros devem ser definidos como tipos de .NET Framework para fornecer melhor validação de parâmetro. Por exemplo, parâmetros que são restritos a um valor de um conjunto de valores devem ser definidos como um tipo de enumeração. Para dar suporte a um valor de Uniform Resource Identifier (URI), defina o parâmetro como um tipo [System. URI](/dotnet/api/System.Uri) . Evite parâmetros de cadeia de caracteres básicos para todas as propriedades de texto de forma livre.

#### <a name="use-consistent-parameter-types"></a>Usar tipos de parâmetro consistentes

Quando o mesmo parâmetro é usado por vários cmdlets, sempre use o mesmo tipo de parâmetro.  Por exemplo, se o parâmetro `Process` for um tipo [System. Int16](/dotnet/api/System.Int16) para um cmdlet, não torne o parâmetro `Process` para outro cmdlet um tipo [System. UInt16](/dotnet/api/System.UInt16) .

#### <a name="parameters-that-take-true-and-false"></a>Parâmetros que assumem true e false

Se o parâmetro usar apenas `true` e `false`, defina o parâmetro como Type [System. Management. Automation. SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter). Um parâmetro de opção é tratado como `true` quando é especificado em um comando. Se o parâmetro não estiver incluído em um comando, o Windows PowerShell considerará o valor do parâmetro como `false`. Não defina parâmetros boolianos.

Se o parâmetro precisar diferenciar entre 3 valores: $true, $false e "não especificado", defina um parâmetro do tipo Nullable @ no__t-0bool >.  A necessidade de um terceiro, o valor "não especificado", normalmente ocorre quando o cmdlet pode modificar uma propriedade booliana de um objeto. Nesse caso, "não especificado" significa não alterar o valor atual da propriedade.

#### <a name="support-arrays-for-parameters"></a>Suporte a matrizes para parâmetros

Frequentemente, os usuários devem executar a mesma operação em vários argumentos. Para esses usuários, um cmdlet deve aceitar uma matriz como entrada de parâmetro para que um usuário possa passar os argumentos para o parâmetro como uma variável do Windows PowerShell. Por exemplo, o cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) usa uma matriz para as cadeias de caracteres que identificam os nomes dos processos a serem recuperados.

#### <a name="support-the-passthru-parameter"></a>Suporte ao parâmetro PassThru

Por padrão, muitos cmdlets que modificam o sistema, como o cmdlet [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) , atuam como "coletores" para objetos e não retornam um resultado. Esse cmdlet deve implementar o parâmetro `PassThru` para forçar o cmdlet a retornar um objeto. Quando o parâmetro `PassThru` é especificado, o cmdlet retorna um objeto usando uma chamada para o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) . Por exemplo, o comando a seguir interrompe o processo de cálculo e passa o processo resultante para o pipeline.

```powershell
Stop-Process calc -passthru
```

Na maioria dos casos, adicionar, definir e novos cmdlets devem dar suporte a um parâmetro `PassThru`.

#### <a name="support-parameter-sets"></a>Conjuntos de parâmetros de suporte

Um cmdlet destina-se a realizar uma única finalidade. No entanto, há muitas vezes mais de uma maneira de descrever a operação ou o destino da operação. Por exemplo, um processo pode ser identificado por seu nome, por seu identificador ou por um objeto de processo. O cmdlet deve dar suporte a todas as representações razoáveis de seus destinos. Normalmente, o cmdlet atende a esse requisito especificando conjuntos de parâmetros (chamados de conjuntos de parâmetros) que operam juntos. Um único parâmetro pode pertencer a qualquer número de conjuntos de parâmetros. Para obter mais informações sobre conjuntos de parâmetros, consulte [conjuntos de parâmetros de cmdlet](./cmdlet-parameter-sets.md).

Ao especificar conjuntos de parâmetros, defina apenas um parâmetro no conjunto como ValueFromPipeline. Para obter mais informações sobre como declarar o atributo de **parâmetro** , consulte [declaração de ParameterAttribute](./parameter-attribute-declaration.md).

Quando os conjuntos de parâmetros são usados, o conjunto de parâmetros padrão é definido pelo atributo de **cmdlet** . O conjunto de parâmetros padrão deve incluir os parâmetros mais prováveis de serem usados em uma sessão interativa do Windows PowerShell. Para obter mais informações sobre como declarar o atributo de **cmdlet** , consulte [declaração de CmdletAttribute](./cmdlet-attribute-declaration.md).

### <a name="provide-feedback-to-the-user-sd04"></a>Fornecer comentários para o usuário (SD04)

Use as diretrizes desta seção para fornecer comentários ao usuário. Esses comentários permitem que o usuário esteja ciente do que está ocorrendo no sistema e tome decisões administrativas melhores.

O tempo de execução do Windows PowerShell permite que um usuário especifique como tratar a saída de cada chamada para o método `Write` definindo uma variável de preferência. O usuário pode definir várias variáveis de preferência, incluindo uma variável que determina se o sistema deve exibir informações e uma variável que determina se o sistema deve consultar o usuário antes de realizar uma ação adicional.

#### <a name="support-the-writewarning-writeverbose-and-writedebug-methods"></a>Suporte aos métodos WriteWarning, WriteVerbose e WriteDebug

Um cmdlet deve chamar o método [System. Management. Automation. cmdlet. WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) quando o cmdlet está prestes a executar uma operação que pode ter um resultado indesejado. Por exemplo, um cmdlet deve chamar esse método se o cmdlet estiver prestes a substituir um arquivo somente leitura.

Um cmdlet deve chamar o método [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) quando o usuário precisar de detalhes sobre o que o cmdlet está fazendo. Por exemplo, um cmdlet deve chamar essas informações se o autor do cmdlet sentir que há cenários que podem exigir mais informações sobre o que o cmdlet está fazendo.

O cmdlet deve chamar o método [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) quando um engenheiro de suporte a produtos ou desenvolvedores precisar entender o que corrompeu a operação de cmdlet. Não é necessário que o cmdlet chame o método [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) no mesmo código que chama o método [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) , pois o parâmetro `Debug` apresenta ambos conjuntos de informações.

#### <a name="support-writeprogress-for-operations-that-take-a-long-time"></a>Suporte a WriteProgress para operações que levam muito tempo

Operações de cmdlet que levam muito tempo para serem concluídas e que não podem ser executadas em segundo plano devem dar suporte a relatórios de progresso por meio de chamadas periódicas para o método [System. Management. Automation. cmdlet. WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) .

#### <a name="use-the-host-interfaces"></a>Usar as interfaces de host

Ocasionalmente, um cmdlet deve se comunicar diretamente com o usuário em vez de usar as várias gravações ou os métodos com suporte na classe [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) . Nesse caso, o cmdlet deve derivar da classe [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) e usar a propriedade [System. Management. Automation. PSCmdlet. host *](/dotnet/api/System.Management.Automation.PSCmdlet.Host) . Essa propriedade dá suporte a diferentes níveis de tipo de comunicação, incluindo os tipos PromptForChoice, prompt e WriteLine/ReadLine. No nível mais específico, ele também fornece maneiras de ler e gravar chaves individuais e lidar com buffers.

A menos que um cmdlet seja projetado especificamente para gerar uma GUI (interface gráfica do usuário), ele não deve ignorar o host usando a propriedade [System. Management. Automation. PSCmdlet. host *](/dotnet/api/System.Management.Automation.PSCmdlet.Host) . Um exemplo de um cmdlet criado para gerar uma GUI é o cmdlet [Out-GridView](/powershell/module/Microsoft.PowerShell.Utility/Out-GridView) .

> [!NOTE]
> Os cmdlets não devem usar a API [System. console](/dotnet/api/System.Console) .

### <a name="create-a-cmdlet-help-file-sd05"></a>Criar um arquivo de ajuda de cmdlet (SD05)

Para cada assembly de cmdlet, crie um arquivo help. XML que contenha informações sobre o cmdlet. Essas informações incluem uma descrição do cmdlet, descrições dos parâmetros do cmdlet, exemplos de uso do cmdlet e muito mais.

## <a name="code-guidelines"></a>Diretrizes de código

As diretrizes a seguir devem ser seguidas durante a codificação de cmdlets para garantir uma experiência de usuário consistente entre usar seus cmdlets e outros cmdlets. Quando você encontrar uma diretriz de código que se aplica à sua situação, certifique-se de examinar as diretrizes de design para obter diretrizes semelhantes.

### <a name="coding-parameters-sc01"></a>Parâmetros de codificação (SC01)

Defina um parâmetro declarando uma propriedade pública da classe cmdlet que é decorada com o atributo **Parameter** . Os parâmetros não precisam ser membros estáticos da classe de .NET Framework derivada para o cmdlet. Para obter mais informações sobre como declarar o atributo de **parâmetro** , consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).

#### <a name="support-windows-powershell-paths"></a>Suporte a caminhos do Windows PowerShell

O caminho do Windows PowerShell é o mecanismo para normalizar o acesso a namespaces. Quando você atribui um caminho do Windows PowerShell a um parâmetro no cmdlet, o usuário pode definir uma "unidade" personalizada que atue como um atalho para um caminho específico. Quando um usuário designa tal unidade, os dados armazenados, como os dados no registro, podem ser usados de forma consistente.

Se o cmdlet permitir que o usuário especifique um arquivo ou uma fonte de dados, ele deverá definir um parâmetro do tipo [System. String](/dotnet/api/System.String). Se houver suporte para mais de uma unidade, o tipo deverá ser uma matriz. O nome do parâmetro deve ser `Path`, com um alias de `PSPath`. Além disso, o parâmetro `Path` deve dar suporte a caracteres curinga. Se o suporte para caracteres curinga não for necessário, defina um parâmetro `LiteralPath`.

Se os dados que o cmdlet ler ou gravar tiverem que ser um arquivo, o cmdlet deverá aceitar a entrada de caminho do Windows PowerShell e o cmdlet deverá usar a propriedade [System. Management. Automation. SessionState. path](/dotnet/api/System.Management.Automation.SessionState.Path) para converter os caminhos do Windows PowerShell em caminhos que o sistema de arquivos reconhece. Os mecanismos específicos incluem os seguintes métodos:

- [System. Management. Automation. PSCmdlet. GetResolvedProviderPathFromPSPath](/dotnet/api/System.Management.Automation.PSCmdlet.GetResolvedProviderPathFromPSPath)

- [System. Management. Automation. PSCmdlet. GetUnresolvedProviderPathFromPSPath](/dotnet/api/System.Management.Automation.PSCmdlet.GetUnresolvedProviderPathFromPSPath)

- [System. Management. Automation. PathIntrinsics. GetResolvedProviderPathFromPSPath](/dotnet/api/System.Management.Automation.PathIntrinsics.GetResolvedProviderPathFromPSPath)

- [System. Management. Automation. PathIntrinsics. GetUnresolvedProviderPathFromPSPath](/dotnet/api/System.Management.Automation.PathIntrinsics.GetUnresolvedProviderPathFromPSPath)

Se os dados que o cmdlet lê ou grava são apenas um conjunto de cadeias de caracteres em vez de um arquivo, o cmdlet deve usar as informações de conteúdo do provedor (`Content`) para leitura e gravação. Essas informações são obtidas da propriedade [System. Management. Automation. Provider. cmdletprovider. invokeprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.InvokeProvider) . Esses mecanismos permitem que outros armazenamentos de dados participem da leitura e gravação de dados.

#### <a name="support-wildcard-characters"></a>Suporte a caracteres curinga

Um cmdlet deve dar suporte A caracteres curinga, se possível. O suporte para caracteres curinga ocorre em muitos lugares em um cmdlet (especialmente quando um parâmetro usa uma cadeia de caracteres para identificar um objeto de um conjunto de objetos). Por exemplo, o cmdlet **Stop-proc** de exemplo do [tutorial StopProc](./stopproc-tutorial.md) define um parâmetro `Name` para manipular cadeias de caracteres que representam nomes de processo. Esse parâmetro dá suporte a caracteres curinga para que o usuário possa especificar facilmente os processos a serem interrompidos.

Quando o suporte para caracteres curinga está disponível, uma operação de cmdlet geralmente produz uma matriz. Ocasionalmente, não faz sentido dar suporte a uma matriz porque o usuário pode usar apenas um único item por vez. Por exemplo, o cmdlet [Set-Location](/powershell/module/Microsoft.PowerShell.Management/Set-Location) não precisa dar suporte a uma matriz porque o usuário está definindo apenas um único local. Nessa instância, o cmdlet ainda dá suporte a caracteres curinga, mas força a resolução para um único local.

Para obter mais informações sobre padrões de caracteres curinga, consulte [suporte a caracteres curinga em parâmetros de cmdlet](./supporting-wildcard-characters-in-cmdlet-parameters.md).

#### <a name="defining-objects"></a>Definindo objetos

Esta seção contém diretrizes para definir objetos para cmdlets e para estender objetos existentes.

##### <a name="define-standard-members"></a>Definir membros padrão

Defina membros padrão para estender um tipo de objeto em um arquivo Types. ps1xml personalizado (use o arquivo Types. ps1xml do Windows PowerShell como um modelo). Os membros padrão são definidos por um nó com o nome PSStandardMembers. Essas definições permitem que outros cmdlets e o tempo de execução do Windows PowerShell funcionem com seu objeto de forma consistente.

##### <a name="define-objectmembers-to-be-used-as-parameters"></a>Definir objectmembers a serem usados como parâmetros

Se você estiver criando um objeto para um cmdlet, certifique-se de que seus membros sejam mapeados diretamente para os parâmetros dos cmdlets que o usarão. Esse mapeamento permite que o objeto seja enviado facilmente para o pipeline e seja passado de um cmdlet para outro.

Objetos de .NET Framework preexistentes que são retornados por cmdlets geralmente não têm alguns membros importantes ou convenientes que são necessários para o desenvolvedor ou o usuário de script. Esses membros ausentes podem ser particularmente importantes para exibição e para criar os nomes de membro corretos para que o objeto possa ser passado corretamente para o pipeline. Crie um arquivo Types. ps1xml personalizado para documentar esses membros necessários. Ao criar esse arquivo, recomendamos a seguinte convenção de nomenclatura: *< Your_Product_Name >* . Types. ps1xml.

Por exemplo, você pode adicionar uma propriedade de script `Mode` ao tipo [System. IO. FileInfo](/dotnet/api/System.IO.FileInfo) para exibir os atributos de um arquivo mais claramente. Além disso, você pode adicionar uma propriedade de alias `Count` ao tipo [System. array](/dotnet/api/System.Array) para permitir o uso consistente desse nome de propriedade (em vez de `Length`).

##### <a name="implement-the-icomparable-interface"></a>Implementar a interface IComparable

Implemente uma interface [System. IComparable](/dotnet/api/System.IComparable) em todos os objetos de saída. Isso permite que os objetos de saída sejam facilmente canalizados para vários cmdlets de classificação e de análise.

##### <a name="update-display-information"></a>Atualizar informações de exibição

Se a exibição de um objeto não fornecer os resultados esperados, crie um *> personalizado de \<YourProductName*. Arquivo Format. ps1xml para esse objeto.

### <a name="support-well-defined-pipeline-input-sc02"></a>Suporte à entrada de pipeline bem definida (SC02)

#### <a name="implement-for-the-middle-of-a-pipeline"></a>Implementar para o meio de um pipeline

Implemente um cmdlet supondo que ele será chamado do meio de um pipeline (ou seja, outros cmdlets produzirão sua entrada ou consumirão sua saída). Por exemplo, você pode supor que o cmdlet `Get-Process`, pois ele gera dados, é usado somente como o primeiro cmdlet em um pipeline. No entanto, como esse cmdlet é projetado para o meio de um pipeline, esse cmdlet permite que os cmdlets ou dados anteriores no pipeline especifiquem os processos a serem recuperados.

#### <a name="support-input-from-the-pipeline"></a>Suporte à entrada do pipeline

Em cada conjunto de parâmetros para um cmdlet, inclua pelo menos um parâmetro que ofereça suporte à entrada do pipeline. O suporte para entrada de pipeline permite que o usuário recupere dados ou objetos, para enviá-los ao conjunto de parâmetros correto e para passar os resultados diretamente para um cmdlet.

Um parâmetro aceita a entrada do pipeline se o atributo de **parâmetro** incluir a palavra-chave `ValueFromPipeline`, o atributo de palavra-chave `ValueFromPipelineByPropertyName` ou ambas as palavras-chave em sua declaração. Se nenhum dos parâmetros em um conjunto de parâmetros oferecer suporte às palavras-chave `ValueFromPipeline` ou `ValueFromPipelineByPropertyName`, o cmdlet não poderá ser posicionado de forma significativa após outro cmdlet, pois ignorará qualquer entrada de pipeline.

#### <a name="support-the-processrecord-method"></a>Suporte ao método ProcessRecord

Para aceitar todos os registros do cmdlet anterior no pipeline, o cmdlet deve implementar o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) . O Windows PowerShell chama esse método várias vezes, uma vez para cada registro enviado ao seu cmdlet.

### <a name="write-single-records-to-the-pipeline-sc03"></a>Gravar registros únicos no pipeline (SC03)

Quando um cmdlet retorna objetos, o cmdlet deve gravar os objetos imediatamente conforme eles são gerados. O cmdlet não deve contê-los para armazená-los em uma matriz combinada. Os cmdlets que recebem os objetos como entrada serão capazes de processar, exibir ou processar e exibir os objetos de saída sem atraso. Um cmdlet que gera objetos de saída um de cada vez deve chamar o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) . Um cmdlet que gera objetos de saída em lotes (por exemplo, porque uma API subjacente retorna uma matriz de objetos de saída) deve chamar o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) com seu segundo parâmetro definido como `true`.

### <a name="make-cmdlets-case-insensitive-and-case-preserving-sc04"></a>Tornar cmdlets não diferencia maiúsculas de minúsculas e SC04 (preservação de maiúsculas e minúsculas)

Por padrão, o próprio Windows PowerShell não diferencia maiúsculas de minúsculas. No entanto, como ele lida com muitos sistemas preexistentes, o Windows PowerShell preserva o caso para facilitar a operação e a compatibilidade. Em outras palavras, se um caractere for fornecido em letras maiúsculas, o Windows PowerShell o manterá em letras maiúsculas. Para que os sistemas funcionem bem, um cmdlet precisa seguir essa convenção. Se possível, ele deve operar de forma não diferencia maiúsculas de minúsculas. No entanto, ele deve preservar o caso original para cmdlets que ocorrem posteriormente em um comando ou no pipeline.

## <a name="see-also"></a>Consulte Também

[Diretrizes de desenvolvimento necessárias](./required-development-guidelines.md)

[Diretrizes de desenvolvimento de consultoria](./advisory-development-guidelines.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
