---
title: Exemplos de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b99d53fc-0af9-426b-82ce-09955e031d4b
caps.latest.revision: 13
ms.openlocfilehash: 0fa4a5f804586c51ae6a36121f9aab041b0989cc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365875"
---
# <a name="cmdlet-samples"></a>Amostras de cmdlet

Esta seção descreve o código de exemplo que é fornecido no SDK do Windows PowerShell 2,0. Você pode copiar o código dos tópicos nesta seção ou abrir os arquivos de origem instalados com o SDK. O [SDK (Software Development Kit) do Windows PowerShell 2,0](https://www.microsoft.com/en-us/download/details.aspx?id=2560) fornece arquivos leiame, arquivos de origem e arquivos de projeto do Visual Studio para cada exemplo. Com o SDK instalado, você pode encontrar os exemplos na pasta `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`.

## <a name="in-this-section"></a>Nesta seção

[Exemplo de GetProcessSample01](./getprocesssample01-sample.md) Este exemplo mostra como escrever um cmdlet que recupera os processos no computador local.

[Exemplo de GetProcessSample02](./getprocesssample02-sample.md) Este exemplo mostra como escrever um cmdlet que recupera os processos no computador local. Ele fornece um parâmetro de nome que pode ser usado para especificar os processos a serem recuperados.

[Exemplo de GetProcessSample03](./getprocesssample03-sample.md) Este exemplo mostra como escrever um cmdlet que recupera os processos no computador local. Ele fornece um parâmetro de nome que pode aceitar um objeto do pipeline ou um valor de uma propriedade de um objeto cujo nome de propriedade é igual ao nome do parâmetro.

[Exemplo de GetProcessSample04](./getprocesssample04-sample.md) Este exemplo mostra como escrever um cmdlet que recupera os processos no computador local. Ele gera um erro de não encerramento se ocorrer um erro durante a recuperação de um processo.

[Exemplo de GetProcessSample05](./getprocesssample05-sample.md) Este exemplo mostra uma versão completa do cmdlet Get-proc.

[Exemplo de StopProcessSample01](./stopprocesssample01-sample.md) Este exemplo mostra como escrever um cmdlet que solicita comentários do usuário antes de tentar parar um processo e como implementar um parâmetro de `PassThru` que indica que o usuário deseja que o cmdlet retorne um objeto.

[Exemplo de StopProcessSample02](./stopprocesssample02-sample.md) Este exemplo mostra como escrever um cmdlet que grava mensagens de depuração, detalhadas e de aviso ao parar os processos no computador local.

[Exemplo de StopProcessSample03](./stopprocesssample03-sample.md) Este exemplo mostra como escrever um cmdlet cujos parâmetros têm aliases e que dão suporte a caracteres curinga.

[Exemplo de StopProcessSample04](./stopprocesssample04-sample.md) Este exemplo mostra como escrever um cmdlet que declara conjuntos de parâmetros, especifica o conjunto de parâmetros padrão e pode aceitar um objeto de entrada.

[Exemplo de Events01](./events01-sample.md) Este exemplo mostra como criar um cmdlet que permite ao usuário se registrar para eventos gerados por [System. IO. FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher). Com esse cmdlet, os usuários podem, por exemplo, registrar uma ação a ser executada quando um arquivo é criado em um diretório específico. Este exemplo deriva da classe base [Microsoft. PowerShell. Commands. Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) .

## <a name="see-also"></a>Consulte Também

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
