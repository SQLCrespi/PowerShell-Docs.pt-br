---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Instruções condicionais e loops em configurações
ms.openlocfilehash: 86f75be4a3d1c1760dd6269335431e8ab9fd8d09
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "75736889"
---
# <a name="conditional-statements-and-loops-in-a-configuration"></a>Instruções condicionais e loops em uma configuração

Você pode tornar sua [Configuração](configurations.md) mais dinâmica usando palavras-chave de controle de fluxo do PowerShell. Este artigo mostra como usar instruções condicionais e loops para tornar a `Configuration` mais dinâmica. Combinar instruções condicionais e loops com [parâmetros](add-parameters-to-a-configuration.md) e [Dados de Configuração](configData.md) proporciona a você mais flexibilidade e controle ao compilar a `Configuration`.

Assim como uma função ou um bloco de script, é possível usar qualquer recurso de linguagem do PowerShell em uma `Configuration`.
As instruções usadas serão avaliadas somente quando você chamar a `Configuration` para compilar um arquivo `.mof`. Os exemplos abaixo mostram cenários para demonstrar conceitos. As instruções condicionais e loops são usados com mais frequência com parâmetros e Dados de Configuração.

Neste exemplo, o bloco de recurso **Service** recupera o estado atual de um serviço no tempo de compilação para gerar um arquivo `.mof` que mantém seu estado atual.

> [!NOTE]
> Usar blocos de recurso dinâmicos inviabiliza a eficácia do Intellisense. O analisador do PowerShell não pode determinar se os valores especificados são aceitáveis até que a `Configuration` seja compilada.

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
        foreach ($service in $(Get-Service))
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

Também é possível criar uma `Configuration` somente para computadores que estão online usando uma instrução `if`.

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    foreach ($computer in @('Server01', 'Server02', 'Server03'))
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
> Os blocos de recurso dinâmicos nos exemplos acima fazem referência ao computador atual. Nesse caso, esse seria o computador no qual você cria a `Configuration`, e não o Nó de destino.

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a>Resumo

Resumindo, você pode usar qualquer recurso de linguagem do PowerShell em uma `Configuration`.

Isso inclui itens como:

- Objetos personalizados
- Tabelas de hash
- Manipulação da cadeia de caracteres
- Comunicação remota
- WMI e CIM
- Objetos do ActiveDirectory
- e mais...

Qualquer código do PowerShell definido em uma `Configuration` será avaliado no tempo de compilação, mas você também pode colocar o código no script que contém sua `Configuration`. Qualquer código fora do bloco de `Configuration` será executado quando você importar sua `Configuration`.

## <a name="see-also"></a>Confira também

- [Adicionar parâmetros a uma configuração](add-parameters-to-a-configuration.md)
- [Separar dados de configuração das Configurações](configData.md)
