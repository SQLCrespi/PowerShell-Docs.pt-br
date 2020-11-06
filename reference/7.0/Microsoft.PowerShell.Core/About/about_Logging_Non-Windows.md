---
description: O PowerShell registra em log as operações internas do mecanismo, provedores e cmdlets.
keywords: powershell
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_non-windows?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging_Non-Windows
ms.openlocfilehash: e1d46acb7dbe85e6c83df3bdcfb355c91a3c2e25
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354517"
---
# <a name="about-logging-non-windows"></a>Sobre o log de não Windows

## <a name="short-description"></a>Descrição breve
O PowerShell registra em log as operações internas do mecanismo, provedores e cmdlets.

## <a name="long-description"></a>Descrição longa

O PowerShell registra detalhes de operações do PowerShell. Por exemplo, o PowerShell registrará operações como iniciar e parar o mecanismo e iniciar e parar provedores. Ele também registrará em log detalhes sobre os comandos do PowerShell.

O local dos logs do PowerShell depende da plataforma de destino. No **Linux** , os logs do PowerShell para **syslog** e **rsyslog. conf** podem ser usados. Para obter mais informações, consulte as páginas locais do computador Linux `man` . No **MacOS** , o sistema de log de **os_log** é usado. Para obter mais informações, consulte [os_log documentação do desenvolvedor](https://developer.apple.com/documentation/os/os_log).

## <a name="viewing-powershell-log-output-on-linux"></a>Exibindo a saída de log do PowerShell no Linux

Os logs do PowerShell para **syslog** no Linux e qualquer uma das ferramentas normalmente usadas para exibir o conteúdo do **syslog** podem ser usados.

O formato das entradas de log usa o seguinte modelo:

```
TIMESTAMP MACHINENAME powershell[PID]: (COMMITID:TID:CID)
  [EVENTID:TASK.OPCODE.LEVEL] MESSAGE
```

|Campo        |Descrição                                             |
|-------------|--------------------------------------------------------|
|`TIMESTAMP`  |Uma data/hora em que a entrada de log foi produzida.            |
|`MACHINENAME`|O nome do sistema em que o log foi produzido.      |
|`PID`        |A ID do processo que gravou a entrada de log. |
|`COMMITID`   |A `git commit` ID ou a marca usada para produzir a compilação.   |
|`TID`        |A ID de thread do thread que gravou a entrada de log.   |
|`CID`        |O identificador do canal hex da entrada de log.            |
|             |10 = operacional, 11 = análise                         |
|`EVENTID`    |O identificador de evento da entrada de log.                  |
|`TASK`       |O identificador da tarefa para a entrada do evento                 |
|`OPCODE`     |O opcode para a entrada do evento                          |
|`LEVEL`      |O nível de log para a entrada do evento                       |
|`MESSAGE`    |A mensagem associada à entrada do evento             |

> [!NOTE]
> `EVENTID`, `TASK` , `OPCODE` e `LEVEL` são os mesmos valores usados ao fazer logon no log de eventos do Windows.

### <a name="filtering-powershell-log-entries-using-rsyslog"></a>Filtrando entradas de log do PowerShell usando rsyslog

Normalmente, as entradas de log do PowerShell são gravadas no padrão `location/file` para **syslog**. No entanto, é possível redirecionar as entradas para um arquivo personalizado.

1. Crie uma conf para a configuração de log do PowerShell e forneça um número menor que 50 (para `50-default.conf` ), como `40-powershell.conf` . O arquivo deve ser colocado em `/etc/rsyslog.d` .

1. Adicione a seguinte entrada ao arquivo:

   ```
   :syslogtag, contains, "powershell[" /var/log/powershell.log
   & stop
   ```

1. Certifique-se `/etc/rsyslog.conf` de que o inclui o novo arquivo. Geralmente, ele terá uma instrução include genérica semelhante à seguinte configuração:

   `$IncludeConfig /etc/rsyslog.d/*.conf`

   Caso contrário, você precisará adicionar uma instrução include manualmente.

1. Verifique se os atributos e as permissões estão definidos adequadamente.

   ```
   -rw-r--r-- 1 root root   67 Nov 28 12:51 40-powershell.conf
   ```

1. Defina a propriedade como **raiz**.

   ```
   chown root:root /etc/rsyslog.d/40-powershell.conf
   ```

1. Definir permissões de acesso: a **raiz** tem leitura/gravação, **os usuários** têm lido.

   ```
   chmod 644 /etc/rsyslog.d/40-powershell.conf
   ```

## <a name="viewing-powershell-log-output-on-macos"></a>Exibindo a saída de log do PowerShell no macOS

O método mais fácil para exibir a saída de log do PowerShell no macOS é usando o aplicativo de **console** .

1. Pesquise o aplicativo de **console** e inicie-o.
1. Selecione o nome do computador em **dispositivos**.
1. No campo de **pesquisa** , insira `pwsh` para o binário principal do PowerShell.
1. Altere o filtro de pesquisa de `Any` para `Process` .
1. Execute as operações.
1. Opcionalmente, salve a pesquisa para uso futuro.

Para filtrar em uma instância de processo específica do PowerShell no **console** do, a variável `$pid` contém a ID do processo.

1. Insira o **pid** (ID do processo) no campo de **pesquisa** .
1. Altere o filtro de pesquisa para `PID` .
1. Execute as operações.

### <a name="viewing-powershell-log-output-from-a-command-line"></a>Exibindo a saída de log do PowerShell de uma linha de comando

O `log` comando pode ser usado para exibir entradas de log do PowerShell na linha de comando.

```
sudo log stream --predicate 'process == "pwsh"' --info
```

### <a name="persisting-powershell-log-output"></a>Persistindo a saída de log do PowerShell

Por padrão, o PowerShell usa o log somente de memória padrão no macOS. Esse comportamento pode ser alterado para habilitar a persistência usando o `log config` comando.

O script a seguir habilita o registro em nível de informação e a persistência:

```
log config --subsystem com.microsoft.powershell --mode=persist:info,level:info
```

O comando a seguir reverte o log do PowerShell para o estado padrão:

```
log config --subsystem com.microsoft.powershell --mode=persist:default,level:default
```

Depois que a persistência é habilitada, o `log show` comando pode ser usado para exportar itens de log. O comando fornece opções para exportar os últimos N itens, itens desde um determinado tempo ou itens dentro de um determinado período de tempo.

Por exemplo, o comando a seguir exporta itens desde o `9am on April 5 of 2018` :

```
log show --info --start "2018-04-05 09:00:00" --predicate "process = 'pwsh'"
```

Você pode obter ajuda para o `log` executando `log show --help` para obter detalhes adicionais.

> [!TIP]
> Ao executar qualquer um dos comandos de log de um prompt ou script do PowerShell, use aspas duplas em toda a cadeia de caracteres de predicado e aspas simples no. Isso evita a necessidade de escapar caracteres de aspas duplas dentro da cadeia de caracteres de predicado.

Talvez você também queira salvar os logs de eventos em um local mais seguro, como um coletor de log de eventos central ou um agregador [Siem][] . Você pode configurar o SIEM no Azure. Para obter mais informações, consulte [integração de Siem genérico](/cloud-app-security/siem).

## <a name="configuring-logging-on-a-non-windows-system"></a>Configurando o log em um sistema não Windows

No Windows, o registro em log é configurado Criando ouvintes de rastreamento ETW ou usando o Visualizador de Eventos para habilitar o log analítico. No Linux e no macOS, o registro em log é configurado usando o arquivo `powershell.config.json` . O restante desta seção discutirá a configuração do log do PowerShell em um sistema que não seja do Windows.

Por padrão, o PowerShell habilita o log informativo para o canal operacional. Isso significa que qualquer saída de log produzida pelo PowerShell que está marcada como operacional e tem um nível de log (rastreamento) maior que o informativo será registrado. Ocasionalmente, os diagnósticos podem exigir uma saída de log adicional, como a saída de log detalhada ou a habilitação da saída de log analítico.

O arquivo `powershell.config.json` é um arquivo **JSON** formatado que reside no diretório do PowerShell `$PSHOME` . Cada instalação do PowerShell usa sua própria cópia desse arquivo. Para a operação normal, esse arquivo permanece inalterado. Embora possa ser útil, alterar algumas das configurações no arquivo, para diagnóstico ou para distinguir entre várias versões do PowerShell no mesmo sistema ou até mesmo várias cópias da mesma versão (consulte `LogIdentity` a tabela abaixo).

O código a seguir é uma configuração de exemplo:

```json
{
  "Microsoft.PowerShell:ExecutionPolicy": "RemoteSigned",
  "PowerShellPolicies": {
    "ScriptExecution": {
      "ExecutionPolicy": "RemoteSigned",
      "EnableScripts": true
    },
    "ScriptBlockLogging": {
      "EnableScriptBlockInvocationLogging": true,
      "EnableScriptBlockLogging": true
    },
    "ModuleLogging": {
      "EnableModuleLogging": false,
      "ModuleNames": [
        "PSReadline",
        "PowerShellGet"
      ]
    },
    "ProtectedEventLogging": {
      "EnableProtectedEventLogging": false,
      "EncryptionCertificate": [
        "Joe"
      ]
    },
    "Transcription": {
      "EnableTranscripting": true,
      "EnableInvocationHeader": true,
      "OutputDirectory": "F:\\tmp\\new"
    },
    "UpdatableHelp": {
      "DefaultSourcePath": "f:\\temp"
    },
    "ConsoleSessionConfiguration": {
      "EnableConsoleSessionConfiguration": false,
      "ConsoleSessionConfigurationName": "name"
    }
  },
  "LogLevel": "verbose"
}
```

As propriedades para configurar o log do PowerShell são listadas na tabela a seguir. Valores marcados com um asterisco, como `Operational*` , indicam o valor padrão quando nenhum valor é fornecido no arquivo.

|Propriedade   |Valores        |Descrição                                  |
|-----------|--------------|---------------------------------------------|
|`LogIdentity`|(nome da cadeia de caracteres) |O nome a ser usado ao registrar em log. Por padrão, o  |
|           |PowerShell   |o PowerShell é a identidade. Esse valor pode ser |
|           |              |usado para informar a diferença entre dois      |
|           |              |instâncias de uma instalação do PowerShell, como |
|           |              |como versão beta e liberação. Esse valor é |
|           |              |também usado para redirecionar a saída de log para um        |
|           |              |arquivo separado no Linux. Consulte a discussão de|
|           |              |**rsyslog** acima.                           |
|`LogChannels`|Eficiência  |Os canais a serem habilitados. Separar os valores|
|           |Analítico      |com uma vírgula ao especificar mais de um.  |
|`LogLevel`   |Always        |Especifique um único valor. O valor habilita  |
|           |Crítico      |a si mesmo e todos os valores acima dele no        |
|           |Erro         |lista à esquerda.                            |
|           |Aviso       |                                             |
|           |Informativa|                                             |
|           |Detalhado       |                                             |
|           |Depurar         |                                             |
|`LogKeywords`|Runspace      |As palavras-chave fornecem a capacidade de limitar o registro em log|
|           |Pipeline      |para componentes específicos no PowerShell. Por |
|           |Protocolo      |padrão, todas as palavras-chave são habilitadas e alteradas |
|           |Transporte     |Esse valor só é útil para           |
|           |Host          |solução de problemas especializada.                |
|           |Cmdlets       |                                             |
|           |serializador    |                                             |
|           |Session       |                                             |
|           |ManagedPlugin |                                             |

## <a name="see-also"></a>Confira também

Para obter informações sobre o **syslog** do Linux e o **rsyslog. conf** , consulte as páginas locais do computador Linux `man` .

Para obter informações sobre o macOS **os_log** , consulte [os_log documentação do desenvolvedor](https://developer.apple.com/documentation/os/os_log).

[about_Logging_Windows](about_Logging_Windows.md)

[Integração genérica ao SIEM](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management
