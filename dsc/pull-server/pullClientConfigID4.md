---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Configurar um cliente de pull usando IDs de configuração no PowerShell 4.0
ms.openlocfilehash: 9adc767e91ff19d373c122a0d493e7b8703d5476
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62079465"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-40"></a>Configurar um cliente de pull usando IDs de configuração no PowerShell 4.0

>Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0

> [!IMPORTANT]
> O Servidor de Recepção (Recurso do Windows *Serviço DSC*) é um componente compatível com o Windows Server, no entanto, não há planos de oferecer novos recursos ou funcionalidades. É recomendável começar a fazer a transição dos clientes gerenciados para o [DSC de Automação do Azure](/azure/automation/automation-dsc-getting-started) (inclui recursos além do Servidor de Recepção no Windows Server) ou para uma das soluções da comunidade listadas [aqui](pullserver.md#community-solutions-for-pull-service).

Antes de configurar um cliente de pull, você deve configurar um servidor de pull. Embora essa ordem não seja obrigatória, ela ajuda na solução de problemas e ajuda a garantir que o registro seja bem-sucedido. Para configurar um servidor de pull, você pode usar os guias a seguir:

- [Configurar um servidor de pull SMB de DSC](pullServerSmb.md)
- [Configurar um servidor de pull HTTP de DSC](pullServer.md)

Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status. As seções a seguir mostram como configurar um cliente de pull com um compartilhamento SMB ou servidor de pull de DSC HTTP. Quando o nó do LCM for atualizado, ele entrará em contato com a localização configurada para baixar as configurações atribuídas. Se algum dos recursos necessários não existir no nó, ele será baixado automaticamente da localização configurada. Se o nó for configurado com um [Servidor de relatório](reportServer.md), ele relatará o status da operação.

## <a name="configure-the-pull-client-lcm"></a>Configurar o LCM do cliente de pull

A execução de qualquer um dos exemplos abaixo cria uma nova pasta de saída denominada **PullClientConfigID** e coloca nela um arquivo MOF de metaconfiguração. Nesse caso, o arquivo MOF de metaconfiguração será nomeado `localhost.meta.mof`.

Para aplicar a configuração, chame o cmdlet **Set-DscLocalConfigurationManager**, com **Path** definido como a localização do arquivo MOF de metaconfiguração. Por exemplo:

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a>ID de configuração

Os exemplos abaixo definem a propriedade **ConfigurationID** do LCM para um **Guid** criado anteriormente para essa finalidade. O **ConfigurationID** é usado pelo LCM para localizar a configuração apropriada no servidor de pull. O arquivo MOF de configuração no servidor de pull deve ser nomeado como `ConfigurationID.mof`, em que *ConfigurationID* é o valor da propriedade **ConfigurationID** do nó de destino do LCM. Para obter mais informações, confira [Publicar configurações em um servidor de pull (v4/v5)](publishConfigs.md).

Você pode criar um **Guid** aleatório usando o exemplo abaixo.

```powershell
[System.Guid]::NewGuid()
```

## <a name="set-up-a-pull-client-to-download-configurations"></a>Configurar um cliente de pull para baixar configurações

Cada cliente deve ser configurado no modo **Pull** e receber a URL do servidor de pull em que sua configuração está armazenada. Para fazer isso, você precisa configurar o Gerenciador de Configurações Local (LCM) com as informações necessárias. Para configurar o LCM, crie um tipo especial de configuração, com um bloco **LocalConfigurationManager**. Para obter mais informações sobre como configurar o LCM, consulte [Configurando o Gerenciador de Configurações Local](../managing-nodes/metaConfig4.md).

## <a name="http-dsc-pull-server"></a>Servidor de pull de DSC HTTP

Se o servidor de pull estiver configurado como um serviço Web, defina **DownloadManagerName** como **WebDownloadManager**. O **WebDownloadManager** exige que você especifique uma **ServerUrl** para a chave **DownloadManagerCustomData**. Você também pode especificar um valor para **AllowUnsecureConnection**, conforme mostrado no exemplo abaixo. O script a seguir configura o LCM para efetuar o pull de configurações de um servidor chamado "PullServer".

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "WebDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = “TRUE”}
    }
}
PullClientConfigId -Output "."
```

## <a name="smb-share"></a>Compartilhamento SMB

Se o servidor de pull for configurado como um compartilhamento de arquivos SMB, e não como um serviço Web, defina **DownloadManagerName** como **DscFileDownloadManager** em vez de **WebDownLoadManager**. O **DscFileDownloadManager** exige que você especifique uma propriedade **SourcePath** em **DownloadManagerCustomData**. O seguinte script configura o LCM para efetuar pull de configurações de um compartilhamento SMB denominado “SmbDscShare” em um servidor denominado “CONTOSO-SERVER”.

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "DscFileDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "\\CONTOSO-SERVER\SmbDscShare"}
    }
}
PullClientConfigId -Output "."
```

## <a name="next-steps"></a>Próximas etapas

Após o cliente de pull ser configurado, você pode usar os guias a seguir para executar as próximas etapas:

- [Publicar configurações em um servidor de pull (v4/v5)](publishConfigs.md)
- [Empacotar e carregar recursos em um servidor de pull (v4)](package-upload-resources.md)

## <a name="see-also"></a>Consulte Também

- [Configurar um servidor de pull Web de DSC](pullServer.md)
- [Configurar um servidor de pull SMB de DSC](pullServerSMB.md)
