---
title: Como adicionar parâmetros dinâmicos a um tópico de ajuda do provedor
ms.date: 09/13/2016
ms.openlocfilehash: ddf964292ee7bf477767a2ca17c717aef84bad51
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893451"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a>Como adicionar parâmetros dinâmicos a um tópico de ajuda do provedor

Esta seção explica como preencher a seção de **parâmetros dinâmicos** de um tópico de ajuda do provedor.

*Parâmetros dinâmicos* são parâmetros de um cmdlet ou função que estão disponíveis somente em condições especificadas.

Os parâmetros dinâmicos documentados em um tópico de ajuda do provedor são os parâmetros dinâmicos que o provedor adiciona ao cmdlet ou função quando o cmdlet ou a função é usada na unidade do provedor.

Os parâmetros dinâmicos também podem ser documentados na ajuda do cmdlet personalizado para um provedor. Ao escrever a ajuda do provedor e a ajuda do cmdlet personalizado para um provedor, inclua a documentação do parâmetro dinâmico em ambos os documentos.

Se um provedor não implementar nenhum parâmetro dinâmico, o tópico da ajuda do provedor conterá um `DynamicParameters` elemento vazio.

### <a name="to-add-dynamic-parameters"></a>Para adicionar parâmetros dinâmicos

1. No `<AssemblyName>.dll-help.xml` arquivo, dentro do `providerHelp` elemento, adicione um `DynamicParameters` elemento. O `DynamicParameters` elemento deve aparecer após o `Tasks` elemento e antes do `RelatedLinks` elemento.

   Por exemplo:

    ```xml
    <providerHelp>
        <Tasks>
        </Tasks>
        <DynamicParameters>
        </DynamicParameters>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

   Se o provedor não implementar nenhum parâmetro dinâmico, o `DynamicParameters` elemento poderá ficar vazio.

1. Dentro do `DynamicParameters` elemento, para cada parâmetro dinâmico, adicione um `DynamicParameter` elemento.

   Por exemplo:

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

1. Em cada `DynamicParameter` elemento, adicione um `Name` `CmdletSupported` elemento e.

   - Nome-especifica o nome do parâmetro
   - CmdletSupported-especifica os cmdlets nos quais o parâmetro é válido. Digite uma lista separada por vírgulas de nomes de cmdlet.

   Por exemplo, o XML a seguir documenta o `Encoding` parâmetro dinâmico que o provedor do sistema de arquivos do Windows PowerShell adiciona aos `Add-Content` `Get-Content` `Set-Content` cmdlets,,.

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

1. Em cada `DynamicParameter` elemento, adicione um `Type` elemento. O `Type` elemento é um contêiner para o `Name` elemento que contém o tipo .net do valor do parâmetro dinâmico.

   Por exemplo, o XML a seguir mostra que o tipo .NET do `Encoding` parâmetro dinâmico é a enumeração [FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) .

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
    ...
    </DynamicParameters>
    ```

1. Adicione o `Description` elemento, que contém uma breve descrição do parâmetro dinâmico. Ao compor a descrição, use as diretrizes indicadas para todos os parâmetros de cmdlet em [como adicionar informações de parâmetro](./how-to-add-parameter-information.md).

   Por exemplo, o XML a seguir inclui a descrição do `Encoding` parâmetro dinâmico.

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
            <Description> Specifies the encoding of the output file that contains the content. </Description>
    ...
    </DynamicParameters>
    ```

1. Adicione o `PossibleValues` elemento e seus elementos filho. Juntos, esses elementos descrevem os valores do parâmetro dinâmico. Esse elemento é projetado para valores enumerados. Se o parâmetro dinâmico não receber um valor, como é o caso com um parâmetro de opção, ou os valores não podem ser enumerados, adicione um `PossibleValues` elemento vazio.

   A tabela a seguir lista e descreve o `PossibleValues` elemento e seus elementos filho.

   - PossibleValues-este elemento é um contêiner. Seus elementos filho são descritos abaixo. Adicione um `PossibleValues` elemento a cada tópico da ajuda do provedor. O elemento pode estar vazio.
   - Possívelvalue-esse elemento é um contêiner. Seus elementos filho são descritos abaixo. Adicione um `PossibleValue` elemento para cada valor do parâmetro dinâmico.
   - Valor-especifica o nome do valor.
   - Descrição-Este elemento contém um `Para` elemento. O texto no `Para` elemento descreve o valor que é nomeado no `Value` elemento.

   Por exemplo, o XML a seguir mostra um `PossibleValue` elemento do `Encoding` parâmetro dinâmico.

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
    ...
            <Description> Specifies the encoding of the output file that contains the content. </Description>
            <PossibleValues>
                <PossibleValue>
                    <Value> ASCII </Value>
                    <Description>
                        <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                    </Description>
                </PossibleValue>
    ...
            </PossibleValues>
    </DynamicParameters>
    ```

## <a name="example"></a>Exemplo

O exemplo a seguir mostra o `DynamicParameters` elemento do `Encoding` parâmetro dinâmico.

```xml
<DynamicParameters/>
    <DynamicParameter>
        <Name> Encoding </Name>
        <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
        <Type>
            <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
        <Type>
        <Description> Specifies the encoding of the output file that contains the content. </Description>
        <PossibleValues>
            <PossibleValue>
                <Value> ASCII </Value>
                <Description>
                    <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                </Description>
            </PossibleValue>
            <PossibleValue>
                <Value> Unicode </Value>
                <Description>
                    <para> Encodes in UTF-16 format using the little-endian byte order. </para>
                </Description>
            </PossibleValue>
        </PossibleValues>
</DynamicParameters>
```
