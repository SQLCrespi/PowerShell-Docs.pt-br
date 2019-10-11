---
ms.date: 12/12/2018
keywords: dsc,powershell,recurso,galeria,instalação
title: Adicionar parâmetros a uma configuração
ms.openlocfilehash: 72e6c15593d11ed39d7fe8ea79f794089f410cf8
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954193"
---
# <a name="add-parameters-to-a-configuration"></a>Adicionar parâmetros a uma configuração

Como as Funções, as [Configurações](configurations.md) podem ter parâmetros que possibilitam configurações mais dinâmicas com base na inserção do usuário. As etapas são semelhantes às descritas em [Funções com parâmetros](/powershell/module/microsoft.powershell.core/about/about_functions).

Este exemplo começa com uma Configuração básica que define o serviço "Spooler" como "Running".

```powershell
Configuration TestConfig
{
    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}
```

## <a name="built-in-configuration-parameters"></a>Parâmetros de configuração internos

Porém, diferente de uma Função, o atributo [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) não adiciona funcionalidade. Além de [Parâmetros Comuns](/powershell/module/microsoft.powershell.core/about/about_commonparameters), as Configurações também podem usar os parâmetros internos a seguir, sem exigir que você os defina.

|Parâmetro  |Descrição  |
|---------|---------|
|`-InstanceName`|Usado na definição de [Configurações de Composição](compositeconfigs.md)|
|`-DependsOn`|Usado na definição de [Configurações de Composição](compositeconfigs.md)|
|`-PSDSCRunAsCredential`|Usado na definição de [Configurações de Composição](compositeconfigs.md)|
|`-ConfigurationData`|Usado para passar [Dados de Configuração](configData.md) estruturados para uso na Configuração.|
|`-OutputPath`|Usado para especificar onde o arquivo "\<nome_do_computador\>.mof" será compilado|

## <a name="adding-your-own-parameters-to-configurations"></a>Adicionando seus próprios parâmetros às Configurações

Além dos parâmetros internos, você também pode adicionar seus próprios parâmetros às Configurações. O bloco de parâmetro vai diretamente dentro da declaração da Configuração, assim como em uma Função. Um bloco de parâmetro de Configuração deve estar fora de qualquer declaração de **Nó** e acima de qualquer instrução de *importação*. Ao adicionar parâmetros, você pode tornar suas Configurações mais robustas e dinâmicas.

```powershell
Configuration TestConfig
{
    param
    (

    )
```

### <a name="add-a-computername-parameter"></a>Adicionar um parâmetro ComputerName

O primeiro parâmetro que pode ser adicionado é `-Computername`. Assim, é possível compilar dinamicamente um arquivo ".mof" para qualquer `-Computername` que você passa para sua configuração. Como em Funções, você também pode definir um valor padrão, caso o usuário não passe um valor para `-ComputerName`

```powershell
param
(
    [String]
    $ComputerName="localhost"
)
```

Em sua configuração, você pode especificar o parâmetro `-ComputerName` ao definir o bloco Nó.

```powershell
Node $ComputerName
{

}
```

### <a name="calling-your-configuration-with-parameters"></a>Chamando sua Configuração com parâmetros

Depois de adicionar parâmetros à sua Configuração, você pode usá-los como faria com um cmdlet.

```powershell
TestConfig -ComputerName "server01"
```

### <a name="compiling-multiple-mof-files"></a>Compilando vários arquivos .mof

O bloco Nó também pode aceitar uma lista de nomes de computador separados por vírgula, gerando arquivos ".mof" para cada um. Você também pode executar o exemplo a seguir para gerar arquivos ".mof" para todos os computadores passados ao parâmetro `-ComputerName`.

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}

TestConfig -ComputerName "server01", "server02", "server03"
```

## <a name="advanced-parameters-in-configurations"></a>Parâmetros avançados em Configurações

Além de um parâmetro `-ComputerName`, podemos adicionar parâmetros para o nome e o estado do serviço. O exemplo a seguir adiciona um bloco de parâmetro com um parâmetro `-ServiceName` e o usa para definir dinamicamente o bloco de recurso **Service**. Também adiciona um parâmetro `-State` para definir dinamicamente o **State** no bloco de recurso **Service**.

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ServiceName,

        [String]
        $State,

        [String]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

> [!NOTE]
> Em cenários mais avançados, pode fazer mais sentido mover seus dados dinâmicos para [Dados de Configuração](configData.md) estruturados.

O exemplo Configuração agora usa um `$ServiceName` dinâmico, mas se um não for especificado, a compilação resultará em um erro. Você pode adicionar um valor padrão como o deste exemplo.

```powershell
[String]
$ServiceName="Spooler"
```

Porém, nessa instância, faz mais sentido simplesmente forçar o usuário a especificar um valor para o parâmetro `$ServiceName`. O atributo `parameter` permite adicionar mais suporte de validação e de pipeline aos parâmetros da Configuração.

Acima de qualquer declaração de parâmetro, adicione o bloco de atributo `parameter`, como no exemplo abaixo.

```powershell
[parameter()]
[String]
$ServiceName
```

Você pode especificar argumentos para cada atributo `parameter`, de modo a controlar aspectos do parâmetro definido. O exemplo a seguir transforma `$ServiceName` em um parâmetro **Mandatory**.

```powershell
[parameter(Mandatory)]
[String]
$ServiceName
```

Para o parâmetro `$State`, gostaríamos de impedir o usuário de especificar valores fora de um conjunto predefinido (como Running ou Stopped). O atributo `ValidationSet*` impediria o usuário de especificar esses valores. O exemplo a seguir adiciona o atributo `ValidationSet` ao parâmetro `$State`. Uma vez que não queremos transformar o parâmetro `$State` como **Mandatory**, precisaremos adicionar um valor padrão para ele.

```powershell
[ValidateSet("Running", "Stopped")]
[String]
$State="Running"
```

> [!NOTE]
> Não é preciso especificar um atributo `parameter` ao usar um atributo `validation`.

Você pode saber mais sobre os atributos de validação e `parameter` em [about_Functions_Advanced_Parameters](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters).

## <a name="fully-parameterized-configuration"></a>Configuração totalmente parametrizada

Agora temos uma Configuração parametrizada que força o usuário a especificar um `-InstanceName`, `-ServiceName`, e valida o parâmetro `-State`.

```powershell
Configuration TestConfig
{
    param
    (
        [parameter(Mandatory)]
        [String]
        $ServiceName,

        [ValidateSet("Running","Stopped")]
        [String]
        $State="Running",

        [String]
        $ComputerName="localhost",
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

## <a name="see-also"></a>Consulte também

- [Gravar ajuda para configurações de DSC](configHelp.md)
- [Configurações dinâmicas](flow-control-in-configurations.md)
- [Usar Dados de Configuração em suas Configurações](configData.md)
- [Separar dados de configuração e de ambiente](separatingEnvData.md)
