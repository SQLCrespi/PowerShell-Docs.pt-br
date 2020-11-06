---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Empacotar e carregar recursos em um servidor de pull
description: Este artigo mostra como carregar recursos em um Servidor de Pull para que eles possam ser baixados pelas configurações nos nós gerenciados pela DSC.
ms.openlocfilehash: a19d04346a0ae546cfcaf70701fde870d3839f65
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661696"
---
# <a name="package-and-upload-resources-to-a-pull-server"></a>Empacotar e carregar recursos em um servidor de pull

As seções a seguir pressupõem que você já tenha configurado um servidor de pull. Se ainda não configurou, use os guias a seguir:

- [Configurar um servidor de pull SMB de DSC](pullServerSmb.md)
- [Configurar um servidor de pull HTTP de DSC](pullServer.md)

Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status. Este artigo mostrará como carregar recursos para que fiquem disponíveis para download e como configurar clientes para baixar os recursos automaticamente. Quando o nó recebe uma configuração atribuída, por meio de **Pull** ou **Push** (v5), ele baixa automaticamente todos os recursos necessários para a configuração do local especificado no LCM.

## <a name="package-resource-modules"></a>Módulos do recurso Package

Cada recurso disponível para um cliente fazer download deve ser armazenado em um arquivo `.zip`. O exemplo a seguir mostra as etapas necessárias usando o recurso [xPSDesiredStateConfiguration](https://www.powershellgallery.com/packages/xPSDesiredStateConfiguration/8.4.0.0).

> [!NOTE]
> Se você tem clientes que usam o PowerShell 4.0, é preciso reduzir a estrutura da pasta de recursos e remover as pastas de versão. Para saber mais, confira [Várias versões do recurso](../configurations/import-dscresource.md#multiple-resource-versions).

Você pode compactar o diretório de recursos usando qualquer utilitário, script ou método que preferir. No Windows, _clique com o botão direito do mouse_ no diretório `xPSDesiredStateConfiguration` e selecione **Enviar para** e em **Pasta compactada**.

![Clique com o botão direito do mouse – Enviar para – Pasta compactada](media/package-upload-resources/right-click.gif)

### <a name="naming-the-resource-archive"></a>Nomear o arquivo de recurso

O arquivo de recurso precisa ser nomeado com o seguinte formato:

```
{ModuleName}_{Version}.zip
```

No exemplo acima, `xPSDesiredStateConfiguration.zip` deve ser renomeado como `xPSDesiredStateConfiguration_8.4.4.0.zip`.

### <a name="create-checksums"></a>Criar somas de verificação

Quando o módulo de recurso estiver compactado e renomeado, é preciso criar uma **soma de verificação**. A **soma de verificação** é usada pelo LCM no cliente, para determinar se o recurso foi alterado e precisa ser baixado novamente. Você pode criar uma **soma de verificação** com o cmdlet [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum), como mostrado no exemplo a seguir.

```powershell
New-DscChecksum -Path .\xPSDesiredStateConfiguration_8.4.4.0.zip
```

Nenhuma saída é exibida, mas agora você deve ver "xPSDesiredStateConfiguration_8.4.4.0.zip.checksum". Também pode executar `New-DSCCheckSum` em um diretório de arquivos usando o parâmetro `-Path`. Se já existir uma soma de verificação, é possível forçá-la a ser criada novamente com o parâmetro `-Force`.

### <a name="where-to-store-resource-archives"></a>Onde armazenar os arquivos de recurso

#### <a name="on-a-dsc-http-pull-server"></a>Em um servidor de pull HTTP de DSC

Ao configurar seu servidor de Pull HTTP, conforme explicado em [Configurar um servidor de pull HTTP de DSC](pullServer.md), você especifica diretórios para as chaves **ModulePath** e **ConfigurationPath**. A chave **ConfigurationPath** indica onde todos os arquivos ".mof" devem ser armazenados. O **ModulePath** indica onde os módulos de recursos DSC devem ser armazenados.

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

#### <a name="on-an-smb-share"></a>Em um compartilhamento SMB

Se você especificou um **ResourceRepositoryShare** ao configurar o seu cliente de pull, armazene os arquivos e as somas de verificação no diretório **SourcePath** do bloco **ResourceRepositoryShare**.

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Configurations'
}

ResourceRepositoryShare SMBResourceServer
{
    SourcePath = '\\SMBPullServer\Resources'
}
```

Se você especificou apenas um **ConfigurationRepositoryShare** ao configurar o seu cliente de pull, armazene os arquivos e as somas de verificação no diretório **SourcePath** do bloco **ConfigurationRepositoryShare**.

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

#### <a name="updating-resources"></a>Atualização de recursos

Você pode forçar um nó a atualizar seus recursos alterando o número de versão no nome de arquivo ou criando uma nova soma de verificação. O cliente de pull verifica se há versões mais recentes dos recursos necessários e somas de verificação atualizadas quando o LCM é atualizado.

## <a name="see-also"></a>Confira também

- [Configurar um servidor de pull SMB de DSC](pullServerSmb.md)
- [Configurar um servidor de pull HTTP de DSC](pullServer.md)
