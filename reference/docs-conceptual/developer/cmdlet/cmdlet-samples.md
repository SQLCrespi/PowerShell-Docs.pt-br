---
title: Exemplos de cmdlet | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7a4fb91cb316bf4231df0bb4446b9a7cd54cf647
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "89235975"
---
# <a name="cmdlet-samples"></a>Amostras de cmdlet

Esta seção descreve o código de exemplo que é fornecido no SDK do Windows PowerShell 2.0. Você pode copiar o código dos tópicos nesta seção ou abrir os arquivos de origem instalados com o SDK. O [SDK (Software Development Kit) do Windows PowerShell 2.0](https://www.microsoft.com/download/details.aspx?id=2560) fornece arquivos Leiame, arquivos de origem e arquivos de projeto do Visual Studio para cada exemplo. Com o SDK instalado, você pode encontrar os exemplos na pasta `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`.

## <a name="in-this-section"></a>Nesta seção

[Exemplo GetProcessSample01](./getprocesssample01-sample.md) Este exemplo mostra como escrever um cmdlet que recupera os processos no computador local.

[Exemplo GetProcessSample02](./getprocesssample02-sample.md) Este exemplo mostra como escrever um cmdlet que recupera os processos no computador local. Ele fornece um parâmetro Name que pode ser usado para especificar os processos a serem recuperados.

[Exemplo GetProcessSample03](./getprocesssample03-sample.md) Este exemplo mostra como escrever um cmdlet que recupera os processos no computador local. Ele fornece um parâmetro Name que pode aceitar um objeto do pipeline ou um valor de uma propriedade de um objeto cujo nome da propriedade é igual ao nome do parâmetro.

[Exemplo GetProcessSample04](./getprocesssample04-sample.md) Este exemplo mostra como escrever um cmdlet que recupera os processos no computador local. Ele gerará um erro sem encerramento se ocorrer um erro durante a recuperação de um processo.

[Exemplo GetProcessSample05](./getprocesssample05-sample.md) Este exemplo mostra uma versão completa do cmdlet Get-Proc.

[Exemplo StopProcessSample01](./stopprocesssample01-sample.md) Este exemplo mostra como escrever um cmdlet que solicita uma resposta do usuário antes de tentar interromper um processo. Mostra também como implementar um parâmetro `PassThru` que indica que o usuário deseja o retorno de um objeto pelo cmdlet.

[Exemplo StopProcessSample02](./stopprocesssample02-sample.md) Este exemplo mostra como escrever um cmdlet que escreve mensagens de depuração, detalhamento e aviso quando interrompe processos no computador local.

[Exemplo StopProcessSample03](./stopprocesssample03-sample.md) Este exemplo mostra como escrever um cmdlet cujos parâmetros têm aliases e dão suporte a caracteres curinga.

[Exemplo StopProcessSample04](./stopprocesssample04-sample.md) Este exemplo mostra como escrever um cmdlet que declara conjuntos de parâmetros, especifica o conjunto de parâmetros padrão e pode aceitar um objeto de entrada.

[Exemplo Events01](./events01-sample.md) Este exemplo mostra como criar um cmdlet que permite ao usuário registrar em eventos gerados por [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher). Com esse cmdlet, os usuários podem, por exemplo, registrar uma ação a ser executada quando um arquivo é criado em um diretório específico. Este exemplo deriva da classe base [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase).

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
