---
external help file: Microsoft.PowerShell.ODataUtils-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.ODataUtils
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.odatautils/export-odataendpointproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ODataEndpointProxy
ms.openlocfilehash: 7550e2df319e5f195e65609ae29ebb00830ec8d2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193889"
---
# Export-ODataEndpointProxy

## SINOPSE
Gera um módulo que contém cmdlets para gerenciar um ponto de extremidade OData.

## SYNTAX

```
Export-ODataEndpointProxy [-Uri] <String> [-OutputModule] <String> [[-MetadataUri] <String>]
 [[-Credential] <PSCredential>] [[-CreateRequestMethod] <String>] [[-UpdateRequestMethod] <String>]
 [[-CmdletAdapter] <String>] [[-ResourceNameMapping] <Hashtable>] [-Force] [[-CustomData] <Hashtable>]
 [-AllowClobber] [-AllowUnsecureConnection] [[-Headers] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Export-ODataEndpointProxy` cmdlet usa os metadados de um ponto de extremidade OData para gerar um módulo que contém cmdlets que você pode usar para gerenciar esse ponto de extremidade OData. O módulo baseia-se no CDXML. Depois que esse cmdlet gera o módulo, ele salva esse módulo no caminho e no nome do arquivo especificado pelo parâmetro **OutputModule** .

`Export-ODataEndpointProxy` gera cmdlets para operações CRUD (criar, ler, atualizar e excluir), ações não CRUD e manipulação de associação.

`Export-ODataEndpointProxy` gera um arquivo CDXML por recurso de ponto de extremidade. Você pode editar esses arquivos CDXML depois que o módulo é gerado. Por exemplo, se você quiser alterar os nomes de substantivo ou de verbo dos cmdlets para alinhar com as diretrizes de nomenclatura de cmdlet do Windows PowerShell, poderá modificar o arquivo.

Cada cmdlet em um módulo gerado deve incluir um parâmetro **conexãouri** para se conectar ao ponto de extremidade que o módulo gerencia.

## EXEMPLOS

### Exemplo 1: gerar um módulo para gerenciar um ponto de extremidade de serviço Web de varejo

```powershell
PS C:\> Export-ODataEndpointProxy -Uri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc' -MetadataUri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc/$metadata' -AllowUnsecureConnection -OutputModule 'C:\Users\user\GeneratedScript.psm1' -ResourceNameMapping @{Products = 'Merchandise'}
```

Esse comando gera um módulo para gerenciar um ponto de extremidade de serviço de varejo. O comando especifica o URI do ponto de extremidade e o URI dos metadados do ponto de extremidade. O comando também fornece um caminho de saída e um nome de módulo de script como o valor do parâmetro **OutputModule** . Para o valor do parâmetro **ResourceNameMapping** , o comando fornece uma tabela de hash que mapeia o nome da coleção de recursos para o substantivo desejado para o conjunto de cmdlets. Neste exemplo, Products é o nome da coleção de recursos e **mercadoria** é o substantivo. Para permitir conexões com sites não SSL, HTTP, em vez de HTTPS, adicione o parâmetro **AllowUnsecureConnection** .

## PARAMETERS

### -AllowClobber

Indica que esse cmdlet substitui um módulo existente.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AllowUnsecureConnection

Indica que este módulo pode se conectar a URIs que não são protegidas por SSL. O módulo pode gerenciar sites HTTP, além de sites HTTPS.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CmdletAdapter

Especifica o adaptador do cmdlet. Os valores aceitáveis para esse parâmetro são: ODataAdapter e NetworkControllerAdapter.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ODataAdapter, NetworkControllerAdapter, ODataV4Adapter

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CreateRequestMethod

Especifica o método de solicitação. Os valores aceitáveis para esse parâmetro são: PUT, POST e PATCH.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem acesso ao ponto de extremidade OData. O valor padrão é o usuário atual. Se um computador remoto executar o Windows Vista ou uma versão posterior do sistema operacional Windows, o cmdlet solicitará as credenciais.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomData

Especifica uma tabela de hash de dados personalizados.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Indica que esse cmdlet substitui um módulo gerado existente de mesmo nome em uma `Modules` pasta existente.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Cabeçalhos

Especifica os cabeçalhos da solicitação da Web. Insira uma tabela de hash ou dicionário.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MetadataUri

Especifica o URI dos metadados do ponto de extremidade.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputModule

Especifica o caminho e o nome do módulo para o qual esse cmdlet salva o módulo gerado de comandos de proxy.

Esse cmdlet copia um módulo binário, um manifesto de módulo e um arquivo de formatação, se aplicável, para a pasta especificada. Se você especificar apenas o nome do módulo, `Export-ODataEndpointProxy` o salvará o módulo na `$home\Documents\WindowsPowerShell\Modules` pasta. Se você especificar um caminho, o cmdlet criará a pasta do módulo nesse caminho.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceNameMapping

Especifica uma tabela de hash que contém mapeamentos que permitem personalizar os cmdlets gerados. Nessa tabela de hash, o nome da coleção de recursos é a chave. O substantivo do cmdlet desejado é o valor.

Por exemplo, na tabela de hash `@{Products = 'Merchandise'}` , **Products** é o nome da coleção de recursos que serve como a chave. **Mercadoria** é o substantivo do cmdlet resultante. Os nomes de cmdlets gerados podem não ser alinhados às diretrizes de nomenclatura de cmdlet do Windows PowerShell. Você pode modificar o arquivo de recurso CDXML para alterar os nomes de cmdlet depois que esse cmdlet criar o módulo. Para obter mais informações, consulte [diretrizes de desenvolvimento altamente incentivadas](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UpdateRequestMethod

Especifica o método de solicitação de atualização. Os valores aceitáveis para esse parâmetro são: PUT, POST e PATCH.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -URI

Especifica o URI do ponto de extremidade.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Biblioteca OData](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)

[O que é o protocolo OData?](https://www.odata.org/)

[Invoke-RestMethod](../Microsoft.PowerShell.Utility/Invoke-RestMethod.md)
