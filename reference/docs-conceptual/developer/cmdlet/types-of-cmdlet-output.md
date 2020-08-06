---
title: Tipos de saída de cmdlet | Microsoft Docs
ms.date: 01/18/2019
helpviewer_keywords:
- cmdlets [PowerShell SDK], output
ms.openlocfilehash: 8f761fdddd264b7c580c4a860081fdc5d2776ee7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786349"
---
# <a name="types-of-cmdlet-output"></a>Tipos de saída de cmdlet

O PowerShell fornece vários métodos que podem ser chamados por cmdlets para gerar a saída. Esses métodos usam uma operação específica para gravar sua saída em um fluxo de dados específico, como o fluxo de dados de êxito ou o fluxo de dados de erro. Este artigo descreve os tipos de saída e os métodos usados para gerá-los.

## <a name="types-of-output"></a>Tipos de saída

### <a name="success-output"></a>Saída de êxito

Os cmdlets podem relatar êxito retornando um objeto que pode ser processado pelo próximo comando no pipeline. Depois que o cmdlet executou sua ação com êxito, o cmdlet chama o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) . É recomendável que você chame esse método em vez dos métodos [System. console. WriteLine](/dotnet/api/System.Console.WriteLine) ou [System. Management. Automation. host. PSHostUserInterface. WriteLine](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine) .

Você pode fornecer um parâmetro de opção **PassThru** para cmdlets que normalmente não retornam objetos.
Quando o parâmetro de opção **PassThru** é especificado na linha de comando, o cmdlet é solicitado a retornar um objeto. Para obter um exemplo de um cmdlet que tem um parâmetro **PassThru** , consulte [Add-History](/powershell/module/Microsoft.PowerShell.Core/Add-History).

### <a name="error-output"></a>Saída de erro

Os cmdlets podem relatar erros. Quando ocorre um erro de encerramento, o cmdlet gera uma exceção. Quando ocorre um erro de não finalização, o cmdlet chama o método [System. Management. Automation. Provider. cmdletprovider. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) para enviar um registro de erro para o fluxo de dados de erro. Para obter mais informações sobre relatórios de erros, consulte [conceitos de relatório de erros](./error-reporting-concepts.md).

### <a name="verbose-output"></a>Saída detalhada

Os cmdlets podem fornecer informações úteis para você enquanto o cmdlet está processando corretamente os registros chamando o método [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) . O método gera mensagens detalhadas que indicam como a ação está prosseguindo.

Por padrão, as mensagens detalhadas não são exibidas. Você pode especificar o parâmetro **Verbose** quando o cmdlet for executado para exibir essas mensagens. **Verbose** é um parâmetro comum que está disponível para todos os cmdlets.

### <a name="progress-output"></a>Saída de progresso

Os cmdlets podem fornecer informações sobre o progresso quando o cmdlet executa tarefas que levam muito tempo para serem concluídas, como copiar um diretório recursivamente. Para exibir informações de progresso, o cmdlet chama o método [System. Management. Automation. cmdlet. WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) .

### <a name="debug-output"></a>Saída de depuração

Os cmdlets podem fornecer mensagens de depuração que são úteis ao solucionar problemas do código do cmdlet. Para exibir informações de depuração, o cmdlet chama o método [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) .

Por padrão, as mensagens de depuração não são exibidas. Você pode especificar o parâmetro de **depuração** quando o cmdlet for executado para exibir essas mensagens. **Debug** é um parâmetro comum que está disponível para todos os cmdlets.

### <a name="warning-output"></a>Saída de aviso

Os cmdlets podem exibir mensagens de aviso chamando o método [System. Management. Automation. cmdlet. WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) .

Por padrão, as mensagens de aviso são exibidas. No entanto, você pode configurar mensagens de aviso usando a `$WarningPreference` variável ou usando os parâmetros **detalhados** e de **depuração** quando o cmdlet é chamado.

## <a name="displaying-output"></a>Exibindo saída

Para todas as chamadas de método de gravação, a exibição de conteúdo é determinada por variáveis de tempo de execução específicas. A exceção é o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) . Usando essas variáveis, você pode fazer a chamada de gravação apropriada no local correto em seu código e não se preocupar quando ou se a saída deve ser exibida.

## <a name="accessing-the-output-functionality-of-a-host-application"></a>Acessando a funcionalidade de saída de um aplicativo host

Você também pode criar um cmdlet para acessar diretamente a funcionalidade de saída de um aplicativo host por meio do tempo de execução do PowerShell. Usar as APIs de host fornecidas pelo PowerShell em vez de [System. console](/dotnet/api/System.Console) ou [System. Windows. Forms](/dotnet/api/System.Windows.Forms) garante que o cmdlet funcionará com uma variedade de hosts. Por exemplo: o host do console do **powershell.exe** , o host de **powershell_ise.exe** gráfico, o host de comunicação remota do PowerShell e hosts de terceiros.

## <a name="see-also"></a>Confira também

[Conceitos de relatórios de erro](./error-reporting-concepts.md)

[Visão geral do cmdlet](./cmdlet-overview.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
