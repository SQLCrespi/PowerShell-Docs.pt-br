---
description: Descreve como trabalhar com parâmetros de comando no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 02/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters
ms.openlocfilehash: 7cc5c071116df8d3326a4ea13802227d350bfac3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196179"
---
# <a name="about-parameters"></a>Sobre parâmetros

## <a name="short-description"></a>Descrição breve
Descreve como trabalhar com parâmetros de comando no PowerShell.

## <a name="long-description"></a>Descrição longa

A maioria dos comandos do PowerShell, como cmdlets, funções e scripts, depende de parâmetros para permitir que os usuários selecionem opções ou forneçam entradas. Os parâmetros seguem o nome do comando e têm o seguinte formato:

```
-<parameter_name> <parameter_value>
-<parameter_name>:<parameter_value>
```

O nome do parâmetro é precedido por um hífen (-), que sinaliza ao PowerShell que a palavra que segue o hífen é um nome de parâmetro. O nome e o valor do parâmetro podem ser separados por um espaço ou um caractere de dois-pontos. Alguns parâmetros não exigem ou aceitam um valor de parâmetro. Outros parâmetros exigem um valor, mas não exigem o nome do parâmetro no comando.

O tipo de parâmetros e os requisitos para esses parâmetros variam. Para localizar informações sobre os parâmetros de um comando, use o `Get-Help` cmdlet. Por exemplo, para encontrar informações sobre os parâmetros do `Get-ChildItem` cmdlet, digite:

```powershell
Get-Help Get-ChildItem
```

Para encontrar informações sobre os parâmetros de um script, use o caminho completo para o arquivo de script. Por exemplo:

```powershell
Get-Help $home\Documents\Scripts\Get-Function.ps1
```

O `Get-Help` cmdlet retorna vários detalhes sobre o comando, incluindo uma descrição, a sintaxe do comando, informações sobre os parâmetros e exemplos que mostram como usar os parâmetros em um comando.

Você também pode usar o parâmetro Parameter do `Get-Help` cmdlet para encontrar informações sobre um determinado parâmetro. Ou, você pode usar o parâmetro **Parameter** com o valor Character curinga ( `*` ) para encontrar informações sobre todos os parâmetros do comando. Por exemplo, o comando a seguir obtém informações sobre todos os parâmetros do `Get-Member` cmdlet:

```powershell
Get-Help Get-Member -Parameter *
```

### <a name="default-parameter-values"></a>Valores do parâmetro padrão

Os parâmetros opcionais têm um valor padrão, que é o valor que é usado ou assumido quando o parâmetro não é especificado no comando.

Por exemplo, o valor padrão do parâmetro **ComputerName** de muitos cmdlets é o nome do computador local. Como resultado, o nome do computador local é usado no comando, a menos que o parâmetro **ComputerName** seja especificado.

Para localizar o valor do parâmetro padrão, consulte o tópico da ajuda para o cmdlet. A descrição do parâmetro deve incluir o valor padrão.

Você também pode definir um valor padrão personalizado para qualquer parâmetro de um cmdlet ou função avançada. Para obter informações sobre como definir valores padrão personalizados, consulte [about_Parameters_Default_Values](about_Parameters_Default_Values.md).

### <a name="parameter-attribute-table"></a>Tabela de atributos de parâmetro

Quando você usa os parâmetros **completo** , **parâmetro** ou **online** do `Get-Help` cmdlet, `Get-Help` o exibe uma tabela de atributos de parâmetro com informações detalhadas sobre o parâmetro.

Essas informações incluem os detalhes que você precisa saber para usar o parâmetro.
Por exemplo, o tópico da ajuda para o `Get-ChildItem` cmdlet inclui os seguintes detalhes sobre seu parâmetro de caminho:

```
-path <string[]>
    Specifies a path of one or more locations. Wildcard characters are
    permitted. The default location is the current directory (.).

Required?                    false
Position?                    0
Default value                Current directory
Accept pipeline input?       true (ByValue, ByPropertyName)
Accept wildcard characters?  true
```

As informações de parâmetro incluem a sintaxe do parâmetro, uma descrição do parâmetro e os atributos de parâmetro. As seções a seguir descrevem os atributos de parâmetro.

#### <a name="parameter-required"></a>Parâmetro necessário

Essa configuração indica se o parâmetro é obrigatório, ou seja, se todos os comandos que usam esse cmdlet devem incluir esse parâmetro. Quando o valor for **true** e o parâmetro estiver ausente no comando, o PowerShell solicitará um valor para o parâmetro.

#### <a name="parameter-position"></a>Posição do parâmetro

Se a `Position` configuração for definida como um inteiro positivo, o nome do parâmetro não será necessário. Esse tipo de parâmetro é conhecido como um parâmetro posicional e o número indica a posição em que o parâmetro deve aparecer em relação a outros parâmetros de posição. Um parâmetro nomeado pode ser listado em qualquer posição após o nome do cmdlet. Se você incluir o nome do parâmetro para um parâmetro posicional, o parâmetro poderá ser listado em qualquer posição após o nome do cmdlet.

Por exemplo, o `Get-ChildItem` cmdlet tem parâmetros Path e exclude. A `Position` configuração para **Path** é **0** , o que significa que ele é um parâmetro posicional. A `Position` configuração para **excluir** é **denominada** .

Isso significa que o **caminho** não requer o nome do parâmetro, mas seu valor de parâmetro deve ser o primeiro ou apenas o valor do parâmetro não nomeado no comando.
No entanto, como o parâmetro Exclude é um parâmetro nomeado, você pode colocá-lo em qualquer posição no comando.

Como resultado das `Position` configurações para esses dois parâmetros, você pode usar qualquer um dos seguintes comandos:

```powershell
Get-ChildItem -Path c:\techdocs -Exclude *.ppt
Get-ChildItem c:\techdocs -Exclude *.ppt
Get-ChildItem -Exclude *.ppt -Path c:\techdocs
Get-ChildItem -Exclude *.ppt c:\techdocs
```

Se você tiver que incluir outro parâmetro posicional sem incluir o nome do parâmetro, esse parâmetro deverá ser colocado na ordem especificada pela `Position` configuração.

#### <a name="parameter-type"></a>Tipo de parâmetro

Essa configuração especifica o tipo de Microsoft .NET Framework do valor do parâmetro. Por exemplo, se o tipo for **Int32** , o valor do parâmetro deverá ser um inteiro. Se o tipo for String, o valor do parâmetro deverá ser uma cadeia de caracteres. Se a cadeia de caracteres contiver espaços, o valor deverá ser colocado entre aspas ou os espaços devem ser precedidos pelo caractere de escape (').

#### <a name="default-value"></a>Valor padrão

Essa configuração especifica o valor que o parâmetro assumirá se nenhum outro valor for fornecido. Por exemplo, o valor padrão do parâmetro Path é geralmente o diretório atual. Os parâmetros necessários nunca têm um valor padrão.
Para muitos parâmetros opcionais, não há nenhum padrão porque o parâmetro não tem efeito se não for usado.

#### <a name="accepts-multiple-values"></a>Aceita vários valores

Essa configuração indica se um parâmetro aceita vários valores de parâmetro.
Quando um parâmetro aceita vários valores, você pode digitar uma lista separada por vírgulas como o valor do parâmetro no comando ou salvar uma lista separada por vírgulas (uma matriz) em uma variável e, em seguida, especificar a variável como o valor do parâmetro.

Por exemplo, o parâmetro ServiceName do `Get-Service` cmdlet aceita vários valores. Os seguintes comandos são válidos:

```powershell
Get-Service -servicename winrm, netlogon
```

```powershell
$s = "winrm", "netlogon"
Get-Service -servicename $s
```

#### <a name="accepts-pipeline-input"></a>Aceita entrada de pipeline

Essa configuração indica se você pode usar o operador de pipeline ( `|` ) para enviar um valor para o parâmetro.

```
Value                    Description
-----                    -----------
False                    Indicates that you cannot pipe a value to the
                         parameter.

True (by Value)          Indicates that you can pipe any value to the
                         parameter, just so the value has the .NET
                         Framework type specified for the parameter or the
                         value can be converted to the specified .NET
                         Framework type.
```

Quando um parâmetro é "true (por valor)", o PowerShell tenta associar quaisquer valores de pipe com esse parâmetro antes de tentar outros métodos para interpretar o comando.

```
True (by Property Name)  Indicates that you can pipe a value to the
                         parameter, but the .NET Framework type of the
                         parameter must include a property with the same
                         name as the parameter.
```

Por exemplo, você pode canalizar um valor para um parâmetro de **nome** somente quando o valor tiver uma propriedade chamada **Name** .

> [!NOTE]
> Um parâmetro tipado que aceita entrada de pipeline ( `by Value` ) ou ( `by PropertyName` ) permite o uso de blocos de script de **ligação de atraso** no parâmetro.
>
> O bloco de script de **ligação de atraso** é executado automaticamente durante o **parâmetrobinding** . O resultado é associado ao parâmetro. A associação de atraso **não funciona para** parâmetros definidos como tipo `ScriptBlock` ou `System.Object` , o bloco de script é passado **sem** ser invocado.
>
> Você pode ler sobre blocos **de script de ligação de atraso** aqui [about_Script_Blocks. MD](about_Script_Blocks.md)

#### <a name="accepts-wildcard-characters"></a>Aceita caracteres curinga

Essa configuração indica se o valor do parâmetro pode conter caracteres curinga para que o valor do parâmetro possa ser correspondido a mais de um item existente no contêiner de destino.

#### <a name="common-parameters"></a>Parâmetros comuns

Parâmetros comuns são parâmetros que você pode usar com qualquer cmdlet. Para obter mais informações sobre parâmetros comuns, consulte [about_CommonParameters](about_CommonParameters.md).

## <a name="see-also"></a>Confira também

[about_Command_syntax](about_Command_syntax.md)

[about_Comment_Based_Help](about_Comment_Based_Help.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Parameters_Default_Values](about_Parameters_Default_Values.md)

[about_Pipelines](about_Pipelines.md)

[about_Wildcards](about_Wildcards.md)
