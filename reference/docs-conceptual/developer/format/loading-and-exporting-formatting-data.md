---
title: Carregando e exportando dados de formatação | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b449b280ccee561679d58f2f2a8b467c83150766
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781113"
---
# <a name="loading-and-exporting-formatting-data"></a>Carregar e exportar dados de formatação

Depois de criar o arquivo de formatação, você precisa atualizar os dados de formato da sessão carregando os arquivos na sessão atual. (Os arquivos de formatação fornecidos pelo Windows PowerShell são carregados por snap-ins que são registrados quando a sessão atual é aberta.) Depois que os dados de formato da sessão atual são atualizados, o Windows PowerShell usa esses dados para exibir os objetos .NET associados às exibições definidas nos arquivos de formatação carregados. Não há nenhum limite para o número de arquivos de formatação que você pode carregar na sessão atual. Além de atualizar os dados de formatação, você pode exportar os dados de formato na sessão atual de volta para um arquivo de formatação.

## <a name="loading-format-data"></a>Carregando dados de formato

Os arquivos de formatação podem ser carregados na sessão atual usando os seguintes métodos:

- Você pode importar o arquivo de formatação para a sessão atual da linha de comando. Use o cmdlet [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) conforme descrito no procedimento a seguir.

- Você pode criar um manifesto de módulo que faça referência ao arquivo de formatação. Os módulos permitem empacotar os arquivos de formatação para distribuição. Use o cmdlet [New-ModuleManifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) para criar o manifesto e o cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) para carregar o módulo na sessão atual. Para obter mais informações sobre módulos, consulte [escrevendo um módulo do Windows PowerShell](../module/writing-a-windows-powershell-module.md).

- Você pode criar um snap-in que faça referência ao arquivo de formatação. Use o [System. Management. Automation. PSSnapin. formats](/dotnet/api/System.Management.Automation.PSSnapIn.Formats) para fazer referência aos arquivos de formatação. É altamente recomendável usar módulos para pacotes de cmdlets e todos os arquivos de formatação e tipos associados para distribuição. Para obter mais informações sobre módulos, consulte [escrevendo um módulo do Windows PowerShell](../module/writing-a-windows-powershell-module.md).

- Se você estiver invocando comandos programaticamente, poderá adicionar uma entrada de arquivo de formatação ao estado de sessão inicial do runspace em que os comandos são executados. Para obter mais informações sobre o tipo .NET usado para adicionar o arquivo de formatação, consulte [System. Management. Automation. Runspaces. Sessionstateformatentry? Classe displayproperty = FullName](/dotnet/api/System.Management.Automation.Runspaces.SessionStateFormatEntry) .

Quando um arquivo de formatação é carregado, ele é adicionado a uma lista interna que o Windows PowerShell usa para determinar qual exibição usar ao exibir objetos na linha de comando. Você pode colocar o arquivo de formatação no início da lista ou acrescentá-lo ao final da lista. Saber onde o arquivo de formatação é adicionado a essa lista é importante se você estiver carregando o arquivo de formatação que define uma exibição para um objeto que tem uma exibição existente definida, como quando você deseja alterar a forma como um objeto retornado por um cmdlet do Windows PowerShell Core é exibido. Se você estiver carregando um arquivo de formatação que define a única exibição de um objeto, poderá usar qualquer um dos métodos descritos anteriormente.  Se você estiver carregando um arquivo de formatação que define outra exibição para um objeto, deverá usar o cmdlet [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) e preceder o arquivo até o início da lista.

## <a name="storing-your-formatting-file"></a>Armazenando o arquivo de formatação

Não há nenhum requisito para o local em que os arquivos de formatação são armazenados no disco. No entanto, é altamente recomendável que você os armazene na seguinte pasta:`user\documents\windowspowershell\`

#### <a name="loading-a-format-file-using-import-formatdata"></a>Carregando um arquivo de formato usando Import-FormatData

1. Armazene o arquivo de formatação em disco.

2. Execute o cmdlet [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) usando um dos comandos a seguir.

   Para adicionar o arquivo de formatação à frente da lista, use este comando. Use este comando se você estiver alterando como um objeto é exibido.

   ```powershell
   Update-FormatData -PrependPath PathToFormattingFile
   ```

   Para adicionar o arquivo de formatação ao final da lista, use este comando.

   ```powershell
   Update-FormatData -AppendPath PathToFormattingFile
   ```

   Depois de adicionar um arquivo usando o cmdlet [Update-FormatData](/powershell/module/Microsoft.PowerShell.Utility/Update-FormatData) , você não poderá remover o arquivo da lista enquanto a sessão estiver aberta. Você deve fechar a sessão para remover o arquivo de formatação da lista.

## <a name="exporting-format-data"></a>Exportando dados de formato

Insira o corpo da seção aqui.
