---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Usando o Import-DSCResource
ms.openlocfilehash: e1c2c06d756a70c2de516f330e3123235ce740ba
ms.sourcegitcommit: 02eed65c526ef19cf952c2129f280bb5615bf0c8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70215410"
---
# <a name="using-import-dscresource"></a>Usando o Import-DSCResource

`Import-DScResource` é uma palavra-chave dinâmica, que só pode ser usada dentro do bloco de script de Configuração. A palavra-chave `Import-DSCResource` para importar todos os recursos necessários em sua Configuração. Os recursos em `$pshome` são importados automaticamente, mas ainda consideramos que a melhor prática é importar explicitamente todos os recursos usados na sua [Configuração](Configurations.md).

A sintaxe para `Import-DSCResource` é mostrada abaixo.  Ao especificar os módulos por nome, é necessário listar cada um deles em uma nova linha.

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName>]
```

|Parâmetro  |Descrição  |
|---------|---------|
|`-Name`|Os nomes do recurso DSC que você deve importar. Se o nome do módulo for especificado, o comando procurará pelos recursos DSC neste módulo; caso contrário, o comando procurará os recursos DSC em todos os caminhos de recursos DSC. Caracteres curinga são suportados.|
|`-ModuleName`|O nome ou a especificação do módulo.  Se você especificar os recursos a importar de um módulo, o comando tentará importar apenas os recursos. Se você especificar apenas o módulo, o comando importará todos os recursos DSC no módulo.|

```powershell
Import-DscResource -ModuleName xActiveDirectory;
```

## <a name="example-use-import-dscresource-within-a-configuration"></a>Exemplo: Usar Import-DSCResource dentro de uma configuração

```powershell
Configuration MSDSCConfiguration
{
    # Search for and imports Service, File, and Registry from the module PSDesiredStateConfiguration.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration -Name Service, File, Registry
    
    # Search for and import Resource1 from the module that defines it.
    # If only –Name parameter is used then resources can belong to different PowerShell modules as well.
    # TimeZone resource is from the ComputerManagementDSC module which is not installed by default.
    # As a best practice, list each requirement on a different line if possible.  This makes reviewing
    # multiple changes in source control a bit easier.
    Import-DSCResource -Name File
    Import-DSCResource -Name TimeZone

    # Search for and import all DSC resources inside the module PSDesiredStateConfiguration.
    # When specifying the modulename parameter, it is a requirement to list each on a new line.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration
    Import-DSCResource -ModuleName ComputerManagementDsc
...
```

> [!NOTE]
> Não há suporte para especificar vários valores para os nomes de recursos e módulos no mesmo comando. Pode haver um comportamento não determinístico sobre qual recurso deve ser carregado de qual módulo, caso o mesmo recurso exista em vários módulos. O comando abaixo resultará em erro durante a compilação.
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

Ao usar somente o parâmetro Nome, considere o seguinte:

- É uma operação de uso intensivo de recursos, dependendo do número de módulos instalados no computador.
- Ele carregará o primeiro recurso encontrado com o nome fornecido. Caso haja mais de um recurso com o mesmo nome instalado, ele poderá carregar o recurso incorreto.

O uso recomendado é especificar `–ModuleName` com o parâmetro `-Name`, como descrito abaixo.

Esse uso oferece os seguintes benefícios:

- Reduz o impacto no desempenho ao limitar o escopo da pesquisa ao recurso especificado.
- Define explicitamente o módulo de definição do recurso, garantindo que o recurso correto seja carregado.

> [!NOTE]
> No PowerShell 5.0, recursos de DSC podem ter várias versões e as versões podem ser instaladas em um computador lado a lado. Isso é implementado por ter várias versões de um módulo de recursos que estão contidas na mesma pasta de módulo.
> Para obter mais informações, veja [Usando recursos com várias versões](sxsresource.md).

## <a name="intellisense-with-import-dscresource"></a>IntelliSense com Import-DSCResource

Ao criar a configuração DSC no ISE, o PowerShell fornece o IntelliSence para recursos e propriedades do recurso. Definições de recurso sob o caminho do módulo `$pshome` são carregados automaticamente. Quando você importa os recursos usando a palavra-chave `Import-DSCResource`, as definições de recursos especificadas são adicionadas e o Intellisense é expandido para incluir o esquema de recurso importado.

![Recurso Intellisense](../media/resource-intellisense.png)

> [!NOTE]
> A partir do PowerShell 5.0, o preenchimento com Tab foi adicionado ao ISE para recursos DSC e suas propriedades. Para saber mais, confira [Recursos](../resources/resources.md).

Ao compilar a configuração, o PowerShell usa as definições de recurso importadas para validar todos os blocos de recursos na configuração.
Cada bloco de recurso é validado, usando a definição de esquema do recurso, para as regras a seguir.

- Apenas as propriedades definidas no esquema são usadas.
- Os tipos de dados de cada propriedade estão corretos.
- As propriedades-chave estão especificadas.
- Nenhuma propriedade somente leitura é usada.
- Validação em tipos de mapas de valor.

Considere a configuração a seguir:

```powershell
Configuration SchemaValidationInCorrectEnumValue
{
    # It is best practice to explicitly import all resources used in your Configuration.
    # This includes resources that are imported automatically, like WindowsFeature.
    Import-DSCResource -Name WindowsFeature
    Node localhost
    {
        WindowsFeature ROLE1
        {
            Name = “Telnet-Client”
            Ensure = “Invalid”
        }
    }
}
```

Compilar essa configuração resulta em um erro.

```output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values ‘Invalid’ is not supported or valid for property ‘Ensure’ on class ‘WindowsFeature’. Please specify only supported values: Present, Absent.
```

O IntelliSense e a validação de esquema permitem capturar mais erros durante o tempo de análise e compilação, evitando complicações no tempo de execução.

> [!NOTE]
> Cada recurso DSC pode ter um nome e um **FriendlyName** definidos pelo esquema do recurso. Abaixo estão as duas primeiras linhas de "MSFT_ServiceResource.shema.mof".
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
> Ao usar esse recurso em uma configuração, você pode especificar **MSFT_ServiceResource** ou **Serviço**.

## <a name="powershell-v4-and-v5-differences"></a>Diferenças entre o PowerShell v4 e v5

Há várias diferenças que você vê ao criar configurações no PowerShell v. 4.0. PowerShell 5.0 e posterior. Esta seção realça as diferenças que são relevantes para este artigo.

### <a name="multiple-resource-versions"></a>Várias versões de recursos

Não havia suporte para instalar e usar várias versões de recursos lado a lado no PowerShell 4.0. Se você perceber problemas de importação de recursos em sua configuração, certifique-se de que só há uma versão instalada do recurso.

Na imagem abaixo, estão instaladas duas versões do módulo **xPSDesiredStateConfiguration**.

![Várias versões fixas de recurso](../media/multiple-resource-versions-broken.png)

Copie o conteúdo da sua versão de módulo desejada para o nível superior do diretório do módulo.

![Várias versões fixas de recurso](../media/multiple-resource-versions-fixed.png)

### <a name="resource-location"></a>Localização do recurso

Ao criar e compilar configurações, seus recursos podem ser armazenados em qualquer diretório especificado por seu [PSModulePath](/powershell/developer/module/modifying-the-psmodulepath-installation-path). No PowerShell 4.0, o LCM requer que todos os módulos de recursos DSC sejam armazenados em "Arquivos de Programa\WindowsPowerShell\Modules" ou `$pshome\Modules`. A partir do PowerShell 5.0, esse requisito foi removido e os módulos de recursos podem ser armazenados em qualquer diretório especificado por `PSModulePath`.

## <a name="see-also"></a>Consulte também

- [Recursos](../resources/resources.md)
