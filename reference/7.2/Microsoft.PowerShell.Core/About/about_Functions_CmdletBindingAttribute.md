---
description: Descreve o atributo que faz uma função funcionar como um cmdlet compilado.
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_CmdletBindingAttribute
ms.openlocfilehash: f1463bafc462ae2a266f5b1f6f4d71e3422f5831
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595993"
---
# <a name="about-functions-cmdletbindingattribute"></a>Sobre o Functions CmdletBindingAttribute

## <a name="short-description"></a>Descrição breve
Descreve o atributo que faz uma função funcionar como um cmdlet compilado.

## <a name="long-description"></a>Descrição longa

O `CmdletBinding` atributo é um atributo de funções que os torna operar como cmdlets compilados escritos em C#. Ele fornece acesso aos recursos de cmdlets.

O PowerShell associa os parâmetros das funções que têm o `CmdletBinding` atributo da mesma forma que vincula os parâmetros dos cmdlets compilados. A `$PSCmdlet` variável automática está disponível para funções com o `CmdletBinding` atributo, mas a `$Args` variável não está disponível.

Em funções que têm o `CmdletBinding` atributo, parâmetros desconhecidos e argumentos posicionais que não têm parâmetros posicionais correspondentes causam a falha da Associação de parâmetro.

> [!NOTE]
> Os cmdlets compilados usam o `Cmdlet` Atributo Required, que é semelhante ao `CmdletBinding` atributo descrito neste tópico.

## <a name="syntax"></a>Syntax

O exemplo a seguir mostra o formato de uma função que especifica todos os argumentos opcionais do `CmdletBinding` atributo. Uma breve descrição de cada argumento segue este exemplo.

```powershell
{
    [CmdletBinding(ConfirmImpact=<String>,
    DefaultParameterSetName=<String>,
    HelpURI=<URI>,
    SupportsPaging=<Boolean>,
    SupportsShouldProcess=<Boolean>,
    PositionalBinding=<Boolean>)]

    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

## <a name="confirmimpact"></a>ConfirmImpact

O argumento **ConfirmImpact** especifica quando a ação da função deve ser confirmada por uma chamada para o método **ShouldProcess** . A chamada para o método **ShouldProcess** exibe um prompt de confirmação somente quando o argumento **ConfirmImpact** é igual ou maior que o valor da `$ConfirmPreference` variável de preferência. (O valor padrão do argumento é **médio**.) Especifique esse argumento somente quando o argumento **SupportsShouldProcess** também for especificado.

Para obter mais informações sobre solicitações de confirmação, consulte [solicitando confirmação](/powershell/scripting/developer/cmdlet/requesting-confirmation).

## <a name="defaultparametersetname"></a>DefaultParameterSetName

O argumento **DefaultParameterSetName** especifica o nome do conjunto de parâmetros que o PowerShell tentará usar quando não puder determinar qual conjunto de parâmetros usar. Você pode evitar esse problema fazendo com que o parâmetro exclusivo de cada parâmetro defina um parâmetro obrigatório.

## <a name="helpuri"></a>HelpURI

O argumento **HelpURI** especifica o endereço de Internet da versão online do tópico da ajuda que descreve a função. O valor do argumento **HelpURI** deve começar com "http" ou "https".

O valor do argumento **HelpURI** é usado para o valor da propriedade **HelpURI** do objeto **CommandInfo** que `Get-Command` retorna para a função.

No entanto, quando os arquivos de ajuda são instalados no computador e o valor do primeiro link na seção **RelatedLinks** do arquivo de ajuda é um URI ou o valor da primeira `.Link` diretiva na Ajuda baseada em comentários é um URI, o URI no arquivo de ajuda é usado como o valor da propriedade **HelpUri** da função.

O `Get-Help` cmdlet usa o valor da propriedade **HelpURI** para localizar a versão online do tópico da ajuda da função quando o parâmetro **online** do `Get-Help` é especificado em um comando.

## <a name="supportspaging"></a>Suporteparapaginação

O argumento **suporteparapaginação** adiciona os parâmetros **First**, **Skip** e **IncludeTotalCount** à função. Esses parâmetros permitem que os usuários selecionem a saída de um conjunto de resultados muito grande. Esse argumento é projetado para cmdlets e funções que retornam dados de repositórios de dados grandes que dão suporte à seleção de dados, como um banco de dado SQL.

Esse argumento foi introduzido no Windows PowerShell 3,0.

- **Primeiro**: obtém somente os primeiros ' n' objetos.
- **Ignorar**: ignora os primeiros ' n' objetos e, em seguida, obtém os objetos restantes.
- **IncludeTotalCount**: relata o número de objetos no conjunto de dados (um inteiro) seguido pelos objetos. Se o cmdlet não puder determinar a contagem total, ele retornará "contagem total desconhecida".

O PowerShell inclui **NewTotalCount**, um método auxiliar que obtém o valor total da contagem para retornar e inclui uma estimativa da precisão do valor total da contagem.

A função de exemplo a seguir mostra como adicionar suporte para os parâmetros de paginação a uma função avançada.

```powershell
function Get-Numbers {
    [CmdletBinding(SupportsPaging = $true)]
    param()

    $FirstNumber = [Math]::Min($PSCmdlet.PagingParameters.Skip, 100)
    $LastNumber = [Math]::Min($PSCmdlet.PagingParameters.First +
      $FirstNumber - 1, 100)

    if ($PSCmdlet.PagingParameters.IncludeTotalCount) {
        $TotalCountAccuracy = 1.0
        $TotalCount = $PSCmdlet.PagingParameters.NewTotalCount(100,
          $TotalCountAccuracy)
        Write-Output $TotalCount
    }
    $FirstNumber .. $LastNumber | Write-Output
}
```

## <a name="supportsshouldprocess"></a>SupportsShouldProcess

O argumento **SupportsShouldProcess** adiciona os parâmetros **Confirm** e **WhatIf** à função. O parâmetro **Confirm** solicita o usuário antes de executar o comando em cada objeto no pipeline. O parâmetro **WhatIf** lista as alterações que o comando faria, em vez de executar o comando.

## <a name="positionalbinding"></a>PositionalBinding

O argumento **PositionalBinding** determina se os parâmetros na função são posicionais por padrão. O valor padrão é `$True`. Você pode usar o argumento **PositionalBinding** com um valor de `$False` para desabilitar a associação posicional.

O argumento **PositionalBinding** é introduzido no Windows PowerShell 3,0.

Quando os parâmetros são posicionais, o nome do parâmetro é opcional.
O PowerShell associa valores de parâmetro não nomeados aos parâmetros de função de acordo com a ordem ou a posição dos valores de parâmetro não nomeados no comando Function.

Quando os parâmetros não são posicionais (eles são "nomeados"), o nome do parâmetro (ou uma abreviação ou alias do nome) é necessário no comando.

Quando **PositionalBinding** é `$True` , os parâmetros de função são posicionais por padrão. O PowerShell atribui o número da posição aos parâmetros na ordem em que eles são declarados na função.

Quando **PositionalBinding** é `$False` , os parâmetros de função não são posicionais por padrão. A menos que o argumento de **posição** do atributo de **parâmetro** seja declarado no parâmetro, o nome do parâmetro (ou um alias ou uma abreviação) deve ser incluído quando o parâmetro é usado em uma função.

O argumento **Position** do atributo de **parâmetro** tem precedência sobre o valor padrão **PositionalBinding** . Você pode usar o argumento **Position** para especificar um valor de posição para um parâmetro. Para obter mais informações sobre o argumento **Position** , consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

## <a name="notes"></a>Observações

Não há suporte para o argumento **SupportsTransactions** em funções avançadas.

## <a name="keywords"></a>Palavras-chave

about_Functions_CmdletBinding_Attribute

## <a name="see-also"></a>Consulte também

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)
