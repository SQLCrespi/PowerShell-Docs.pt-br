---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Registrando Configurações de JEA
ms.openlocfilehash: dbed5c7dd71f2f7a09d97416be56dff675799548
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74417606"
---
# <a name="registering-jea-configurations"></a>Registrando Configurações de JEA

Depois que você criar as [capacidades de função](role-capabilities.md) e o [arquivo de configuração de sessão](session-configurations.md), a última etapa será registrar o ponto de extremidade JEA. Registrar o ponto de extremidade JEA no sistema torna o ponto de extremidade disponível para uso pelos usuários e pelos mecanismos de automação.

## <a name="single-machine-configuration"></a>Configuração de computador único

Em ambientes pequenos, você pode implantar o JEA ao registrar o arquivo de configuração de sessão usando o cmdlet [Register-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/register-pssessionconfiguration).

Antes de começar, verifique se os pré-requisitos a seguir foram atendidos:

- Uma ou mais funções foram criadas e colocadas na pasta **RoleCapabilities** de um módulo do PowerShell.
- Um arquivo de configuração de sessão foi criado e testado.
- O usuário que está registrando a configuração JEA tem direitos de administrador no sistema.
- Você selecionou um nome para o ponto de extremidade JEA.

O nome do ponto de extremidade JEA será necessário quando os usuários se conectarem ao sistema usando o JEA. O cmdlet [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) lista os nomes dos pontos de extremidade em um sistema. Os pontos de extremidade que começam com `microsoft` geralmente são fornecidos com o Windows. O ponto de extremidade `microsoft.powershell` é o ponto de extremidade padrão usado ao se conectar a um ponto de extremidade remoto do PowerShell.

```powershell
Get-PSSessionConfiguration | Select-Object Name
```

```Output
Name
----
microsoft.powershell
microsoft.powershell.workflow
microsoft.powershell32
```

Execute o comando a seguir para registrar o ponto de extremidade.

```powershell
Register-PSSessionConfiguration -Path .\MyJEAConfig.pssc -Name 'JEAMaintenance' -Force
```

> [!WARNING]
> O comando anterior reinicia o serviço WinRM no sistema. Isso termina todas as sessões de comunicação remota do PowerShell, bem como as configurações DSC em andamento. Recomendamos que você coloque todos os computadores de produção offline antes de executar o comando para evitar interromper as operações de negócios.

Após o registro, você estará pronto para [usar o JEA](using-jea.md). Você poderá excluir o arquivo de configuração de sessão a qualquer momento. O arquivo de configuração não é usado após o registro do ponto de extremidade.

## <a name="multi-machine-configuration-with-dsc"></a>Configuração de vários computadores com o DSC

Se você estiver implantando o JEA em vários computadores, o modelo de implantação mais simples usará o recurso [DSC (Desired State Configuration)](/powershell/scripting/dsc/overview) do JEA para implantar o JEA de forma rápida e consistente em cada computador.

Para implantar o JEA com o DSC, garanta que os seguintes pré-requisitos sejam atendidos:

- Uma ou mais capacidades de função foram criadas e adicionadas a um módulo do PowerShell.
- O módulo do PowerShell que contém as funções é armazenado em um compartilhamento de arquivo (somente leitura) acessível por cada computador.
- As configurações para a configuração de sessão foram determinadas. Não é necessário criar um arquivo de configuração de sessão ao usar o recurso DSC do JEA.
- Você tem credenciais que permitem ações administrativas em cada computador ou tem acesso ao servidor de pull DSC usado para gerenciar os computadores.
- Você baixou o [recurso DSC do JEA](https://github.com/powershell/JEA/tree/master/DSC%20Resource).

Crie uma configuração DSC para o ponto de extremidade JEA em um computador de destino ou um servidor de pull. Nessa configuração, o recurso DSC **JustEnoughAdministration** define o arquivo de configuração de sessão e o recurso **File** copia as capacidades de função do compartilhamento de arquivo.

As seguintes propriedades são configuráveis usando o recurso de DSC:

- Definições de Função
- Grupos de contas virtuais
- Nome da conta de serviço gerenciado de grupo
- Diretório de transcrição
- Unidade de usuário
- Regras de acesso condicional
- Scripts de inicialização para a sessão JEA

A sintaxe para cada uma dessas propriedades em uma configuração DSC é consistente com o arquivo de configuração de sessão do PowerShell.

Abaixo está um exemplo de configuração de DSC para um módulo de manutenção geral do servidor. Ele pressupõe que um módulo do PowerShell válido contendo as capacidades de função esteja localizado no compartilhamento de arquivo `\\myfileshare\JEA`.

```powershell
Configuration JEAMaintenance
{
    Import-DscResource -Module JustEnoughAdministration, PSDesiredStateConfiguration

    File MaintenanceModule
    {
        SourcePath = "\\myfileshare\JEA\ContosoMaintenance"
        DestinationPath = "C:\Program Files\WindowsPowerShell\Modules\ContosoMaintenance"
        Checksum = "SHA-256"
        Ensure = "Present"
        Type = "Directory"
        Recurse = $true
    }

    JeaEndpoint JEAMaintenanceEndpoint
    {
        EndpointName = "JEAMaintenance"
        RoleDefinitions = "@{ 'CONTOSO\JEAMaintenanceAuditors' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit' }; 'CONTOSO\JEAMaintenanceAdmins' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit', 'GeneralServerMaintenance-Admin' } }"
        TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
        DependsOn = '[File]MaintenanceModule'
    }
}
```

Em seguida, a configuração é aplicada em um sistema pela invocação direta do [Gerenciador de Configurações Local](/powershell/scripting/dsc/managing-nodes/metaConfig) ou pela atualização da [configuração do servidor de pull](/powershell/scripting/dsc/pull-server/pullServer).

O recurso DSC também permite que você substitua o ponto de extremidade **Microsoft.PowerShell** padrão. Quando substituído, o recurso registra automaticamente um ponto de extremidade de backup chamado **Microsoft.PowerShell.Restricted**. O ponto de extremidade de backup tem a ACL padrão do WinRM que permite acesso aos Usuários do Gerenciamento Remoto e aos membros do grupo local de administradores.

## <a name="unregistering-jea-configurations"></a>Cancelando o registro de configurações de JEA

O cmdlet [Unregister-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/Unregister-PSSessionConfiguration) remove um ponto de extremidade JEA. O cancelamento do registro de um ponto de extremidade JEA impede que novos usuários criem novas sessões de JEA no sistema. Ele também permite que você atualize uma configuração de JEA, registrando novamente um arquivo de configuração de sessão atualizado usando o mesmo nome de ponto de extremidade.

```powershell
# Unregister the JEA endpoint called "ContosoMaintenance"
Unregister-PSSessionConfiguration -Name 'ContosoMaintenance' -Force
```

> [!WARNING]
> O cancelamento do registro de um ponto de extremidade JEA faz com que o serviço WinRM seja reiniciado. Isso interrompe a maioria das operações de gerenciamento remotas em andamento, incluindo outras sessões do PowerShell, invocações de WMI e algumas ferramentas de gerenciamento. Cancele o registro de pontos de extremidade do PowerShell somente durante janelas de manutenção planejadas.

## <a name="next-steps"></a>Próximas etapas

[Testar o ponto de extremidade JEA](using-jea.md)
