---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Instruções condicionais e loops em configurações
ms.openlocfilehash: 0073d94d28afbb45bb635442129a6cddde4c805a
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954073"
---
# <a name="conditional-statements-and-loops-in-configurations"></a>Instruções condicionais e loops em configurações

Você pode tornar suas [Configurações](configurations.md) mais dinâmicas usando palavras-chave de controle de fluxo do PowerShell. Este artigo mostra como você pode usar instruções condicionais e loops para tornar as Configurações mais dinâmicas. Combinar condicionais e loops com [parâmetros](add-parameters-to-a-configuration.md) e [Dados de Configuração](configData.md) proporciona a você mais flexibilidade e controle ao compilar as Configurações.

Assim com uma Função ou um Bloco de Script, é possível usar qualquer linguagem do PowerShell em uma Configuração. As instruções usadas serão avaliadas somente quando você chamar a Configuração para compilar um arquivo ".mof". Os exemplos abaixo mostram cenários simples para demonstrar conceitos. As condicionais são loops usados frequentemente com parâmetros e Dados de Configuração.

Neste exemplo simples, o bloco de recurso **Service** recupera o estado atual de um serviço no tempo de compilação para gerar um arquivo ".mof" que mantém seu estado atual.

> [!NOTE]
> Usar blocos de recurso dinâmicos inviabiliza a eficácia do Intellisense. O analisador do PowerShell não pode determinar se os valores especificados são aceitáveis enquanto a Configuração não for compilada.

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Service Spooler
        {
            Name = "Spooler"
            State = $(Get-Service -Name 'spooler').Status
            StartType = $(Get-Service -Name 'spooler').StartType
        }
    }
}
```

Além disso, você pode criar um bloco de recurso **Service** para cada serviço no computador atual usando um loop `foreach`.

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Foreach ($service in $(Get-Service))
        {
            Service $service.Name
            {
                Name = $service.Name
                State = $service.Status
                StartType = $service.StartType
            }
        }
    }
}
```

Também é possível criar configurações somente para computadores que estão online, usando uma instrução `if` simples.

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    Foreach ($computer in @('Server01', 'Server02', 'Server03'))
    {
        if (Test-Connection -ComputerName $computer)
        {
            Node $computer
            {
                Service "Spooler"
                {
                    Name = "Spooler"
                    State = "Started"
                }
            }
        }
    }
}
```

> [!NOTE]
> Os blocos de recurso dinâmicos nos exemplos acima fazem referência ao computador atual. Nesse caso, esse seria o computador no qual você cria a Configuração, não o Nó de destino.

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a>Resumo

Resumindo, você pode usar qualquer linguagem do PowerShell em uma Configuração.

Isso inclui itens como:

- Objetos personalizados
- Tabelas de hash
- Manipulação da cadeia de caracteres
- Comunicação remota
- WMI e CIM
- Objetos do ActiveDirectory
- e mais...

Qualquer código do PowerShell definido em uma Configuração será avaliado no tempo de compilação, mas você também pode colocar o código no script que contém sua Configuração. Qualquer código fora do bloco de Configuração será executado ao importar sua Configuração.

## <a name="see-also"></a>Consulte também

- [Adicionar parâmetros a uma configuração](add-parameters-to-a-configuration.md)
- [Separar dados de configuração das Configurações](configData.md)
