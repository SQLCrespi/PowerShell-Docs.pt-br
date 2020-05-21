---
title: Adicionando recursos a um serviço Web do Management OData | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e620bf6d-76be-47b0-a7a8-f43418f30c60
caps.latest.revision: 6
ms.openlocfilehash: 2f6ad8ee9f303d3dea92a633996e9248d2e87a21
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561893"
---
# <a name="adding-resources-to-a-management-odata-web-service"></a>Adicionar recursos a um serviço Web OData de gerenciamento

Este exemplo demonstra como adicionar um recurso a um serviço Web do Management OData existente usando o designer de esquema do Management OData. O exemplo [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) cria um serviço Web que expõe os recursos do processo e do servidor. Neste exemplo, você adicionará um recurso de VM (máquina virtual) ao serviço Web.

## <a name="prerequisites"></a>Pré-requisitos

Este tópico pressupõe que você tenha baixado e instalado o exemplo [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) , conforme descrito em [criando um serviço Web do Windows PowerShell](./creating-a-management-odata-web-service.md), e que você baixou e instalou o [Designer de esquema do Management OData](https://marketplace.visualstudio.com/items?itemName=jlisc0.ManagementODataSchemaDesigner). Este tópico também pressupõe que você tenha o módulo do Windows PowerShell do Hyper-V instalado no computador em que você configurou o ponto de extremidade do Management OData.

## <a name="adding-vm-as-a-resource-to-the-web-service"></a>Adicionando a VM como um recurso ao serviço Web

A primeira etapa é importar o esquema do ponto de extremidade do OData de gerenciamento existente para o designer de esquema. O procedimento a seguir descreve como fazer isso.

#### <a name="importing-an-existing-schema-into-the-schema-designer"></a>Importando um esquema existente para o designer de esquema

1. Abra o designer de esquema do Management OData.

2. No menu **arquivo** , selecione **arquivo** ; **Novo** ; **Arquivo**. A caixa de diálogo **novo arquivo** é exibida.

3. Clique em **Management OData Model**e, em seguida, clique em **abrir**.

4. Clique com o botão direito do mouse na janela principal e clique em **arquivo de esquema** ; **Importar**. A caixa de diálogo **abrir** é exibida.

5. Navegue até a pasta onde você configurou o serviço Web do Management OData para o exemplo [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) . Se você usou o script do Windows PowerShell fornecido com esse exemplo para configurar o ponto de extremidade sem modificar o script, essa pasta será **C:\inetpub\wwwroot\Modata**. Selecione Schema. mof e clique em **abrir**.

   Neste ponto, abra os arquivos Schema. mof e Schema. xml em um editor de texto e observe que eles contêm mapeamentos para os recursos de processo e serviço. O arquivo Schema. mof usa o padrão MOF ( [Distributed Management Task Force](https://www.dmtf.org/) ). O arquivo Schema. XML usa um esquema XML descrito no esquema de [mapeamento de recursos](./resource-mapping-schema.md).

   O procedimento a seguir descreve como importar cmdlets do Hyper-V no para o modelo de esquema.

#### <a name="importing-cmdlets-into-the-schema"></a>Importando cmdlets para o esquema

1. Clique com o botão direito do mouse em uma área em branco da janela do designer de esquema e clique em **importar cmdlets**. A caixa de diálogo **Assistente de importação de cmdlet** é exibida.

2. Verifique se **computador local** está selecionado e clique em **Avançar**.

3. Verifique se os módulos instalados do Windows PowerShell estão selecionados e selecione Hyper-V na lista suspensa. Clique em **Avançar**. Clique em **Avançar**.

4. Na lista de **Substandos do cmdlet** , selecione **VM**. Clique em **Avançar**.

5. Para este exemplo, Vincularemos apenas os comandos Get e DELETE com cmdlets. Desmarque as caixas de seleção **criar** e **Atualizar** e verifique se as caixas de seleção **obter** e **excluir** estão marcadas. Verifique se o `Get-VM` cmdlet está selecionado para **Get**e se o `Remove-VM` cmdlet está selecionado para **exclusão**.

6. Como os metadados dos cmdlets da VM não especificam um tipo de saída, será necessário executar o cmdlet para especificar o tipo de saída. Selecione **fornecer tipo de saída** e clique em **executar cmdlet**. A caixa de diálogo **executar cmdlet** é exibida. Clique em **Executar**. A caixa **tipo CLR** é populada com o `VirtualMachine` tipo. Clique em **OK**e em **Avançar**.

7. Por padrão, todas as propriedades do objeto VirtualMachine são selecionadas. Você pode limpar todas as propriedades que não deseja como parte dos dados retornados ao solicitar esse recurso do serviço Web. Clique em **Avançar**.

8. Você deve selecionar pelo menos uma propriedade para ser usada como uma chave. Selecione **nome** na lista e clique em **Avançar**.

9. A próxima janela permite mapear as propriedades do recurso do Management OData para as propriedades dos cmdlets subjacentes. O assistente mapeia Propriedades com nomes idênticos por padrão. Por exemplo, a `ComputerName` Propriedade do recurso é mapeada para a `ComputerName` propriedade dos cmdlets.  Isso permite que você especifique a `ComputerName` propriedade em uma solicitação para o serviço Web e que o valor especificado seja passado para o `Get-VM` cmdlet. `Id`e `Name` também são mapeados por padrão.

   10. Clique em **Avançar**e em **concluir**.

       O recurso de VM agora aparece na janela do designer de esquema. Você pode examinar as propriedades e as operações associadas ao recurso. Em seguida, você vai exportar os arquivos de esquema atualizados para o diretório virtual para o serviço Web.

#### <a name="exporting-schema-files-from-the-schema-designer"></a>Exportando arquivos de esquema do designer de esquema

1. Clique com o botão direito do mouse em uma área em branco da janela do designer de esquema e clique em **arquivo de esquema** ; **Exportar**. A caixa de diálogo **salvar como** é exibida.

2. Navegue até o mesmo diretório de onde você importou o arquivo MOF. Nomeie o arquivo da mesma forma que o arquivo MOF original (Schema. mof por padrão) e clique em **salvar**. Confirme que você deseja substituir o arquivo existente.

   Embora não seja explicitamente indicado na caixa de diálogo **salvar como** , isso substitui os arquivos Schema. mof e Schema. xml.

## <a name="next-steps"></a>Próximas etapas

Antes de acessar o novo recurso de VM do serviço Web do Management OData, você deve atualizar o arquivo RbacConfiguration. xml para permitir o acesso ao módulo do Windows PowerShell do Hyper-V, conforme descrito em [Configurando a autorização baseada em função](./configuring-role-based-authorization.md), e também será necessário reiniciar o serviço Web.
