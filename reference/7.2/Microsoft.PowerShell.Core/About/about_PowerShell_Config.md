---
description: Arquivos de configuração do PowerShell Core, substituindo a configuração do registro.
Locale: en-US
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Config
ms.openlocfilehash: 7190484832958e778a21e6d2cc91771587bffdbf
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595374"
---
# <a name="about-powershell-config"></a>Sobre a configuração do PowerShell

## <a name="short-description"></a>DESCRIÇÃO BREVE
Arquivos de configuração do PowerShell Core, substituindo a configuração do registro.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O `powershell.config.json` arquivo contém definições de configuração para o PowerShell Core. O PowerShell carrega essa configuração na inicialização. As configurações também podem ser modificadas em tempo de execução. Anteriormente, essas configurações eram armazenadas no registro do Windows para o PowerShell, mas agora estão contidas em um arquivo para habilitar a configuração no macOS e no Linux.

> [!WARNING]
> Se o `powershell.config.json` arquivo contiver um PowerShell JSON inválido não poderá iniciar uma sessão interativa.
> Se isso ocorrer, você deverá corrigir o arquivo de configuração.

> [!NOTE]
> Chaves não reconhecidas ou valores inválidos no arquivo de configuração serão ignorados silenciosamente.

### <a name="allusers-shared-configuration"></a>Configuração de AllUsers (compartilhado)

Um `powershell.config.json` arquivo no `$PSHOME` diretório define a configuração para todas as sessões do PowerShell Core em execução a partir da instalação do PowerShell Core.

> [!NOTE]
> O `$PSHOME` local é definido como o mesmo diretório que o assembly de System.Management.Automation.dll em execução. Isso se aplica a instâncias do SDK do PowerShell hospedadas também.

### <a name="currentuser-per-user-configurations"></a>Configurações CurrentUser (por usuário)

Você também pode configurar o PowerShell em uma base por usuário colocando o arquivo no diretório de configuração de escopo do usuário. O diretório de configuração do usuário pode ser encontrado em várias plataformas com o comando `Split-Path $PROFILE.CurrentUserCurrentHost` .

## <a name="general-configuration-settings"></a>Definições de configuração geral

### <a name="executionpolicy"></a>ExecutionPolicy

> [!IMPORTANT]
> Essa configuração se aplica somente a plataformas Windows.

Configura a política de execução para sessões do PowerShell, determinando quais scripts podem ser executados. Por padrão, o PowerShell usa a política de execução existente.

Para configurações AllUsers, isso define a política de execução **LocalMachine** .
Para configurações CurrentUser, isso define a política de execução **CurrentUser** .

> [!NOTE]
> O [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) cmdlet modifica essa configuração no arquivo de configuração AllUsers quando invocado com `-Scope LocalMachine` o e modifica essa configuração no arquivo de configuração CurrentUser quando invocado com `-Scope CurrentUser` .

```Schema
"<shell-id>:ExecutionPolicy": "<execution-policy>"
```

Em que:

- `<shell-id>` refere-se à ID do host do PowerShell atual.
  Para o PowerShell Core normal, isso é `Microsoft.PowerShell` .
  Em qualquer sessão do PowerShell, você pode descobri-lo com o `$ShellId` .
- `<execution-policy>` refere-se a um nome de política de execução válido.

O exemplo a seguir define a política de execução do PowerShell para `RemoteSigned` .

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "RemoteSigned"
}
```

No Windows, as chaves de registro equivalentes podem ser encontradas em `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` em `HKEY_LOCAL_MACHINE` e `HKEY_CURRENT_USER` .

### <a name="psmodulepath"></a>PSModulePath

Substitui um componente PSModulePath para esta sessão do PowerShell. Se a configuração for para o usuário atual, define o caminho do módulo CurrentUser. Se a configuração for para todos os usuários, define o caminho do módulo do usuário.

> [!WARNING]
> Configurar um caminho de módulo AllUsers ou CurrentUser aqui não alterará o local de instalação com escopo para módulos do PowerShellGet [, como install-Module](/powershell/module/powershellget/install-module).
> Esses cmdlets sempre usam os caminhos de módulo *padrão* .

Se nenhum valor for definido, o valor padrão do respectivo componente de caminho do módulo será usado. Consulte [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) para obter mais detalhes sobre esses padrões.

Essa configuração permite que as variáveis de ambiente sejam usadas inserindo-as entre `%` caracteres, como `"%HOME%\Documents\PowerShell\Modules"` , da mesma maneira que o cmd permite. Essa sintaxe também se aplica ao Linux e ao macOS. Consulte abaixo para obter exemplos.

```Schema
"PSModulePath": "<ps-module-path>"
```

Em que:

- `<ps-module-path>` é o caminho absoluto para um diretório de módulo. Para todas as configurações de usuário, esse é o diretório de módulo compartilhado AllUsers. Para as configurações de usuário atuais, este é o diretório de módulo CurrentUser.

Este exemplo mostra uma configuração de PSModulePath para um ambiente do Windows:

```json
{
  "PSModulePath": "C:\\Program Files\\PowerShell\\6\\Modules"
}
```

Este exemplo mostra uma configuração de PSModulePath para um ambiente macOS ou Linux:

```json
{
  "PSModulePath": "/opt/powershell/6/Modules"
}
```

Este exemplo mostra a inserção de uma variável de ambiente em uma configuração de PSModulePath. Observe que, usando a `HOME` variável de ambiente e o `/` separador de diretório, isso funcionará no Windows, no MacOS e no Linux.

```json
{
  "PSModulePath": "%HOME%/Documents/PowerShell/Modules"
}
```

Este exemplo mostra a inserção de uma variável de ambiente em uma configuração PSModulePath que só funcionará no macOS e no Linux:

```json
{
  "PSModulePath": "%XDG_CONFIG_HOME%/powershell/Modules"
}
```

> [!NOTE]
> As variáveis do PowerShell não podem ser inseridas em configurações do PSModulePath.
> As configurações do PSModulePath no Linux e no macOS diferenciam maiúsculas de minúsculas. Uma configuração PSModulePath deve usar separadores de diretório válidos para a plataforma. No macOS e no Linux, isso significa `/` . No Windows, `/` e `\` funcionarão.

### <a name="experimentalfeatures"></a>ExperimentalFeatures

Os nomes dos recursos experimentais a serem habilitados no PowerShell.
Por padrão, nenhum recurso experimental está habilitado.
O valor padrão é uma matriz vazia.

```Schema
"ExperimentalFeatures": ["<experimental-feature-name>", ...]
```

Em que:

- `<experimental-feature-name>` é o nome de um recurso experimental a ser habilitado.

O exemplo a seguir habilita os recursos experimentais **PSImplicitRemoting** e **PSUseAbbreviationExpansion** quando o PowerShell é iniciado.

```json
{
  "ExperimentalFeatures": [
    "PSImplicitRemotingBatching",
    "PSUseAbbreviationExpansion"
  ]
}
```

Para obter mais informações sobre recursos experimentais, consulte [PowerShell RFC 29][RFC0029].

## <a name="non-windows-logging-configuration"></a>Configuração de log não Windows

> [!IMPORTANT]
> As opções de configuração nesta seção se aplicam somente ao macOS e ao Linux.
> O registro em log do Windows é gerenciado pelo Visualizador de Eventos do Windows.

O registro em log do PowerShell no macOS e no Linux pode ser configurado no arquivo de configuração do PowerShell. Para obter uma descrição completa do log do PowerShell para sistemas que não são do Windows, consulte [sobre registro em log](./about_Logging_Non-Windows.md).

### <a name="logidentity"></a>LogIdentity

> [!IMPORTANT]
> Essa configuração só pode ser usada no macOS e no Linux.

Define o nome de identidade usado para gravar no log do sistema. O valor padrão é "PowerShell".

```Schema
"LogIdentity": "<log-identity>"
```

Em que:

- `<log-identity>` é a identidade de cadeia de caracteres que o PowerShell deve usar para gravar no syslog.

> [!NOTE]
> Talvez você queira ter diferentes valores de **LogIdentity** para cada instância diferente do PowerShell que você instalou.

Neste exemplo, estamos Configurando o **LogIdentity** para uma versão de visualização do PowerShell.

```json
{
  "LogIdentity": "powershell-preview"
}
```

### <a name="loglevel"></a>LogLevel

> [!IMPORTANT]
> Essa configuração só pode ser usada no macOS e no Linux.

Especifica o nível de severidade mínimo no qual o PowerShell deve registrar.

```Schema
"LogLevel": "<log-level>|default"
```

Em que:

- `<log-level>` pode ser:
  - Sempre
  - Crítico
  - Erro
  - Aviso
  - Informativo
  - Detalhado
  - Depurar

> [!NOTE]
> A configuração de um nível de log habilita todos os níveis de log acima dele.

Definir essa configuração como **padrão** será interpretado como o valor padrão.
O valor padrão é **informativo**.

O exemplo a seguir define o valor como **Verbose**.

```json
{
  "LogLevel": "Verbose"
}
```

### <a name="logchannels"></a>LogChannels

> [!IMPORTANT]
> Essa configuração só pode ser usada no macOS e no Linux.

Determina quais canais de log estão habilitados.

```Schema
"LogChannels": "<log-channel>,..."
```

Em que:

- `<log-channel>` pode ser:
  - Operacional-registra informações básicas sobre as atividades do PowerShell
  - Análise-registra informações de diagnóstico mais detalhadas

O valor padrão é **operacional**. Para habilitar ambos os canais, inclua os dois valores como uma única cadeia de caracteres separada por vírgulas. Por exemplo:

```json
{
  "LogChannels": "Operational,Analytic"
}
```

### <a name="logkeywords"></a>LogKeywords

> [!IMPORTANT]
> Essa configuração só pode ser usada no macOS e no Linux.

Determina quais partes do PowerShell são registradas. Por padrão, todas as palavras-chave de log são habilitadas. Para habilitar várias palavras-chave, liste os valores em uma única cadeia de caracteres separada por vírgulas.

```Schema
"LogKeywords": "<log-keyword>,..."
```

Em que:

- `<log-keyword>` pode ser:
  - Runspace-gerenciamento de runspace
  - Pipeline – operações de pipeline
  - Protocolo – tratamento de protocolo de comunicação, como PSRP
  - Suporte de camada de transporte de transporte, como SSH
  - Funcionalidade host-PowerShell host, por exemplo, interação do console
  - Cmdlets – cmdlets internos do PowerShell
  - Serializador-lógica de serialização
  - Sessão-estado de sessão do PowerShell
  - ManagedPlugin-plug-in do WSMan

> [!NOTE]
> Geralmente, é aconselhável deixar esse valor definido, a menos que você esteja tentando diagnosticar um comportamento específico em uma parte conhecida do PowerShell.
> A alteração desse valor diminui apenas a quantidade de informações registradas.

Este exemplo limita o registro em log para operações de runspace, lógica de pipeline e uso de cmdlet. Todos os outros logs serão omitidos.

```json
"LogKeywords": "Runspace,Pipeline,Cmdlets"
```

<!--

## Group policy configuration

### ScriptExecution

### ScriptBlockLogging

### ProtectedEventLogging

### Transcription

### UpdateableHelp

### ConsoleSessionConfiguration

-->

## <a name="more-example-configurations"></a>Mais configurações de exemplo

### <a name="example-windows-configuration"></a>Configuração do Windows de exemplo

Essa configuração tem mais configurações definidas explicitamente:

- A política de execução para esta instalação do PowerShell é `AllSigned`
- O caminho do módulo CurrentUser é definido como um diretório de módulo em uma unidade compartilhada
- O `PSImplicitRemotingBatching` recurso experimental está habilitado

> [!NOTE]
> As `ExecutionPolicy` `PSModulePath` configurações e aqui só funcionariam em uma plataforma Windows, já que o caminho do módulo usa `\` e `;` caracteres separadores e a política de execução não é `Unrestricted` (a única política permitida em plataformas semelhantes a UNIX).

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "AllSigned",
  "PSModulePath": "Z:\\Marisol's Shared Drive\\Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
}
```

### <a name="example-non-windows-configuration"></a>Exemplo de configuração não Windows

Essa configuração define várias opções que funcionam apenas no macOS ou Linux:

- O caminho do módulo CurrentUser é definido como um diretório de módulo personalizado no `$HOME`
- O recurso experimental do **PSImplicitRemotingBatching** está habilitado
- O nível de log do PowerShell é definido como **detalhado**, para obter mais registro em log
- Essa instalação do PowerShell grava nos logs usando a identidade do **PowerShell inicial** .

```json
{
  "PSModulePath": "%HOME%/.powershell/Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
  "LogLevel": "Verbose",
  "LogIdentity": "home-powershell"
}
```

## <a name="see-also"></a>Consulte também

[Sobre as políticas de execução](./about_Execution_Policies.md)

[Sobre variáveis automáticas](./about_Automatic_Variables.md)

[RFC0029]: https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md

