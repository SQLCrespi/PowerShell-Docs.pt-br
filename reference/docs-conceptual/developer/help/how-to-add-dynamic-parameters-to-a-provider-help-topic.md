---
title: Como adicionar parâmetros dinâmicos a um tópico de ajuda do provedor | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e20e5ad6-a6e6-4a63-9d42-1ac54214f748
caps.latest.revision: 5
ms.openlocfilehash: 59839e9b8b6f2a56f2f1a9c755f2f1a85deb34aa
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361255"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a>Como adicionar parâmetros dinâmicos a um tópico de ajuda do provedor

Esta seção explica como preencher a seção de **parâmetros dinâmicos** de um tópico de ajuda do provedor.

*Parâmetros dinâmicos* são parâmetros de um cmdlet ou função que estão disponíveis somente em condições especificadas.

Os parâmetros dinâmicos documentados em um tópico de ajuda do provedor são os parâmetros dinâmicos que o provedor adiciona ao cmdlet ou função quando o cmdlet ou a função é usada na unidade do provedor.

Os parâmetros dinâmicos também podem ser documentados na ajuda do cmdlet personalizado para um provedor. Ao escrever a ajuda do provedor e a ajuda do cmdlet personalizado para um provedor, inclua a documentação do parâmetro dinâmico em ambos os documentos.

Se um provedor não implementar nenhum parâmetro dinâmico, o tópico da ajuda do provedor conterá um elemento `DynamicParameters` vazio.

### <a name="to-add-dynamic-parameters"></a>Para adicionar parâmetros dinâmicos

1. No arquivo *AssemblyName*. dll-help. xml, dentro do elemento `providerHelp`, adicione um elemento `DynamicParameters`. O elemento `DynamicParameters` deve aparecer após o elemento `Tasks` e antes do elemento `RelatedLinks`.

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

   Se o provedor não implementar nenhum parâmetro dinâmico, o elemento `DynamicParameters` poderá ficar vazio.

2. Dentro do elemento `DynamicParameters`, para cada parâmetro dinâmico, adicione um elemento `DynamicParameter`.

   Por exemplo:

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. Em cada elemento `DynamicParameter`, adicione um `Name` e um elemento `CmdletSupported`.

   |Nome do Elemento|Descrição|
   |------------------|-----------------|
   |Nome|Especifica o nome do parâmetro.|
   |CmdletSupported|Especifica os cmdlets nos quais o parâmetro é válido. Digite uma lista separada por vírgulas de nomes de cmdlet.|

   Por exemplo, o XML a seguir documenta o `Encoding` parâmetro dinâmico que o provedor do sistema de arquivos do Windows PowerShell adiciona aos cmdlets `Add-Content`, `Get-Content``Set-Content`.

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. Em cada elemento `DynamicParameter`, adicione um elemento `Type`. O elemento `Type` é um contêiner para o elemento `Name` que contém o tipo .NET do valor do parâmetro dinâmico.

   Por exemplo, o XML a seguir mostra que o tipo .NET do parâmetro dinâmico `Encoding` é a enumeração [Microsoft. PowerShell. Commands. FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) .

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

5. Adicione o elemento `Description`, que contém uma breve descrição do parâmetro dinâmico. Ao compor a descrição, use as diretrizes indicadas para todos os parâmetros de cmdlet em [como adicionar informações de parâmetro](./how-to-add-parameter-information.md).

   Por exemplo, o XML a seguir inclui a descrição do parâmetro dinâmico `Encoding`.

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

6. Adicione o elemento `PossibleValues` e seus elementos filho. Juntos, esses elementos descrevem os valores do parâmetro dinâmico. Esse elemento é projetado para valores enumerados. Se o parâmetro dinâmico não receber um valor, como é o caso com um parâmetro de opção, ou os valores não podem ser enumerados, adicione um elemento de `PossibleValues` vazio.

   A tabela a seguir lista e descreve o elemento `PossibleValues` e seus elementos filho.

   |Nome do Elemento|Descrição|
   |------------------|-----------------|
   |PossibleValues|Este elemento é um contêiner. Seus elementos filho são descritos abaixo. Adicione um elemento `PossibleValues` a cada tópico da ajuda do provedor. O elemento pode estar vazio.|
   |Possível|Este elemento é um contêiner. Seus elementos filho são descritos abaixo. Adicione um elemento `PossibleValue` para cada valor do parâmetro dinâmico.|
   |Valor|Especifica o nome do valor.|
   |Descrição|Este elemento contém um elemento `Para`. O texto no elemento `Para` descreve o valor que é nomeado no elemento `Value`.|

   Por exemplo, o XML a seguir mostra um elemento `PossibleValue` do parâmetro `Encoding` dinâmico.

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

O exemplo a seguir mostra o elemento `DynamicParameters` do parâmetro `Encoding` dinâmico.

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