---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Publicar em um servidor de Pull usando IDs de configuração (v4/v5)
ms.openlocfilehash: 3b094308338e62c783b19f4d3bb41634feee63f6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74417245"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a>Publicar em um servidor de Pull usando IDs de configuração (v4/v5)

As seções a seguir pressupõem que você já tenha configurado um servidor de pull. Se ainda não configurou o servidor de pull, use os guias a seguir:

- [Configurar um servidor de pull SMB de DSC](pullServerSmb.md)
- [Configurar um servidor de pull HTTP de DSC](pullServer.md)

Cada nó de destino pode ser configurado para baixar configurações, recursos e até mesmo relatar seu status. Este artigo mostra como carregar recursos para que fiquem disponíveis para download e como configurar clientes para baixar automaticamente os recursos. Quando o nó recebe uma configuração atribuída, por meio de **Pull** ou **Push** (v5), ele baixa automaticamente todos os recursos necessários para a configuração do local especificado no LCM (Local Configuration Manager).

## <a name="compile-configurations"></a>Compilar configurações

A primeira etapa para armazenar [Configurações](../configurations/configurations.md) em um servidor de pull é compilá-las em arquivos `.mof`. Para tornar uma configuração genérica e aplicável a mais clientes, use `localhost` em seu bloco de nós. O exemplo a seguir mostra um shell de configuração que usa `localhost` em vez de um nome de cliente específico.

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

Depois de compilar sua configuração genérica, você deve ter um arquivo `localhost.mof`.

## <a name="renaming-the-mof-file"></a>Renomeando o arquivo MOF

Você pode armazenar arquivos de configuração `.mof` em um servidor de pull por **ConfigurationName** ou **ConfigurationID**. Dependendo de como você planeja configurar os clientes de pull, é possível escolher uma seção abaixo para renomear corretamente seus arquivos `.mof` compilados.

### <a name="configuration-ids-guid"></a>IDs de configuração (GUID)

Você precisará renomear o arquivo `localhost.mof` como o arquivo `<GUID>.mof`. Você pode criar um **Guid** aleatório usando o exemplo abaixo ou usando o cmdlet [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid).

```powershell
[System.Guid]::NewGuid()
```

Saída de exemplo

```Output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

Em seguida, você pode renomear o arquivo `.mof` usando qualquer método aceitável. O exemplo a seguir usa o cmdlet [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

Para obter mais informações sobre o uso de **Guids** em seu ambiente, confira [Plan for Guids](/powershell/scripting/dsc/secureserver#guids) (Planejar-se para usar Guids).

### <a name="configuration-names"></a>Nomes de configuração

Você precisará renomear o arquivo `localhost.mof` como o arquivo `<Configuration Name>.mof`. No exemplo a seguir, é usado o nome da configuração da seção anterior. Em seguida, você pode renomear o arquivo `.mof` usando qualquer método aceitável. O exemplo a seguir usa o cmdlet [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item).

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a>Criar a soma de verificação

Cada arquivo `.mof` armazenado em um servidor de pull ou compartilhamento SMB precisa ter um arquivo `.checksum` associado.
Esse arquivo permite que os clientes saibam quando o arquivo `.mof` associado foi alterado e deve ser baixado novamente.

Você pode criar um **CheckSum** com o cmdlet [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum). Também pode executar `New-DSCCheckSum` em um diretório de arquivos usando o parâmetro `-Path`.
Se já existir uma soma de verificação, é possível forçá-la a ser criada novamente com o parâmetro `-Force`. O exemplo a seguir especificou um diretório que contém o arquivo `.mof` da seção anterior e usa o parâmetro `-Force`.

```powershell
New-DscChecksum -Path '.\' -Force
```

Nenhuma saída será exibida, mas agora você deve ver um arquivo `<GUID or Configuration Name>.mof.checksum`.

## <a name="where-to-store-mof-files-and-checksums"></a>Onde armazenar os arquivos MOF e as somas de verificação

### <a name="on-a-dsc-http-pull-server"></a>Em um servidor de pull HTTP de DSC

Ao configurar seu servidor de Pull HTTP, conforme explicado em [Configurar um servidor de pull HTTP de DSC](pullServer.md), você especifica diretórios para as chaves **ModulePath** e **ConfigurationPath**. A chave **ModulePath** indica onde os arquivos `.zip` empacotados de um módulo devem ser armazenados. O **ConfigurationPath** indica onde os arquivos `.mof` e `.checksum` devem ser armazenados.

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a>Em um compartilhamento SMB

Quando você configurar um cliente de pull para usar um compartilhamento SMB, especifique um **ConfigurationRepositoryShare**.
Todos os arquivos `.mof` e `.checksum` devem ser armazenados no diretório **SourcePath** do bloco **ConfigurationRepositoryShare**.

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a>Próximas etapas

Em seguida, configure clientes de pull para extrair a configuração especificada. Para saber mais, confira um dos guias a seguir:

- [Configurar um cliente de pull usando IDs de configuração (v4)](pullClientConfigId4.md)
- [Configurar um cliente de pull usando IDs de configuração (v5)](pullClientConfigId.md)
- [Configurar um cliente de pull usando Nomes de configuração (v5)](pullClientConfigNames.md)

## <a name="see-also"></a>Consulte também

- [Configurar um servidor de pull SMB de DSC](pullServerSmb.md)
- [Configurar um servidor de pull HTTP de DSC](pullServer.md)
- [Empacotar e carregar recursos em um servidor de pull](package-upload-resources.md)
