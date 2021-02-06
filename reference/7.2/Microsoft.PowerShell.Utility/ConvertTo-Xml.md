---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Xml
ms.openlocfilehash: e461c07360b3d9eaf7d9a3c8875d34cd1fc841e8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598642"
---
# ConvertTo-Xml

## SINOPSE
Cria uma representação de um objeto baseada em XML.

## SYNTAX

```
ConvertTo-Xml [-Depth <Int32>] [-InputObject] <PSObject> [-NoTypeInformation] [-As <String>]
 [<CommonParameters>]
```

## DESCRIPTION

O `ConvertTo-Xml` cmdlet cria uma representação [baseada em XML](/dotnet/api/system.xml.xmldocument) de um ou mais objetos .net. Para usar esse cmdlet, redirecione um ou mais objetos para o cmdlet ou use o parâmetro **InputObject** para especificar o objeto.

Quando você canaliza vários objetos para `ConvertTo-Xml` ou usa o parâmetro **InputObject** para enviar vários objetos, `ConvertTo-Xml` o retorna um único documento XML na memória que inclui representações de todos os objetos.

Esse cmdlet é semelhante a [Export-Clixml](./Export-Clixml.md) , exceto pelo fato de `Export-Clixml` armazenar o XML resultante em um arquivo [XML de Common Language Infrastructure (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm) que pode ser reimportado como objetos com [Import-Clixml](./Import-Clixml.md). `ConvertTo-Xml` Retorna uma representação na memória de um documento XML, para que você possa continuar a processá-lo no PowerShell. `ConvertTo-Xml` Não tem uma opção para converter objetos em CLI XML.

## EXEMPLOS

### Exemplo 1: converter uma data em XML

```
PS C:\> Get-Date | ConvertTo-Xml
```

Esse comando converte a data atual (um objeto **DateTime** ) em XML.

### Exemplo 2: converter processos em XML

```
PS C:\> ConvertTo-Xml -As "Document" -InputObject (Get-Process) -Depth 3
```

Este comando converte os objetos de processo, que representam todos os processos no computador, em um documento XML. Os objetos são expandidos para uma profundidade de três níveis.

## PARAMETERS

### -Como

Determina o formato de saída.
Os valores aceitáveis para esse parâmetro são:

- Cadeia de caracteres.
Retorna uma única cadeia de caracteres.
- Fluxo.
Retorna uma matriz de cadeias de caracteres.
- Documento.
Retorna um objeto **XmlDocument** .

O valor padrão é documento.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Stream, String, Document

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profundidade

Especifica quantos níveis de objetos contidos estão incluídos na representação XML. O valor padrão é 1.

Por exemplo, se as propriedades do objeto também contêm objetos e você deseja salvar uma representação XML das propriedades dos objetos nelas contidos, é necessário especificar uma profundidade igual a 2.

O valor padrão pode ser substituído para o tipo de objeto em questão nos arquivos Types.ps1xml. Para obter mais informações, consulte about_Types.ps1xml.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica o objeto a ser convertido. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos. Você também pode canalizar objetos para **ConvertTo-XML**.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NoTypeInformation

Omite o atributo Type dos nós do objeto.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

É possível canalizar qualquer objeto para **ConvertTo-XML**.

## SAÍDAS

### Documento System. String ou System.Xml.Xml

*O valor do parâmetro as* determina o tipo de objeto que o **ConvertTo-XML** retorna.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[ConvertTo-Csv](ConvertTo-Csv.md)

[ConvertTo-Html](ConvertTo-Html.md)

[Export-Clixml](Export-Clixml.md)

[Obter Data](Get-Date.md)

[Import-Clixml](Import-Clixml.md)

