---
ms.date: 02/03/2020
ms.topic: reference
title: Importar um módulo do PowerShell
description: Importar um módulo do PowerShell
ms.openlocfilehash: 688509c0943a9a0289e75b80543f278e16cfedfe
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658776"
---
# <a name="importing-a-powershell-module"></a>Importar um módulo do PowerShell

Depois de instalar um módulo em um sistema, você provavelmente vai querer importar o módulo. A importação é o processo que carrega o módulo na memória ativa, para que um usuário possa acessar esse módulo na sessão do PowerShell. No PowerShell 2,0, você pode importar um módulo do PowerShell instalado recentemente com uma chamada para o cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) . No PowerShell 3,0, o PowerShell é capaz de importar implicitamente um módulo quando uma das funções ou cmdlets no módulo é chamado por um usuário. Observe que ambas as versões pressupõem que você instale o módulo em um local onde o PowerShell possa encontrá-lo; para obter mais informações, consulte [instalando um módulo do PowerShell](./installing-a-powershell-module.md).
Você pode usar um manifesto de módulo para restringir quais partes do módulo são exportadas e pode usar parâmetros da `Import-Module` chamada para restringir quais partes são importadas.

## <a name="importing-a-snap-in-powershell-10"></a>Importando um Snap-In (PowerShell 1,0)

Os módulos não existiam no PowerShell 1,0: em vez disso, era necessário registrar e usar snap-ins. No entanto, não é recomendável que você use essa tecnologia neste ponto, pois os módulos são geralmente mais fáceis de instalar e importar. Para obter mais informações, consulte [como criar um snap-in do Windows PowerShell](../cmdlet/how-to-create-a-windows-powershell-snap-in.md).

## <a name="importing-a-module-with-import-module-powershell-20"></a>Importando um módulo com Import-Module (PowerShell 2,0)

O PowerShell 2,0 usa o cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) nomeado apropriadamente para importar módulos. Quando esse cmdlet é executado, o Windows PowerShell procura o módulo especificado dentro dos diretórios especificados na `PSModulePath` variável. Quando o diretório especificado é encontrado, o Windows PowerShell procura arquivos na seguinte ordem: Arquivos de manifesto de módulo (. psd1), arquivos de módulo de script (. psm1), arquivos de módulo binário (. dll). Para obter mais informações sobre como adicionar diretórios à pesquisa, consulte [modificando o caminho de instalação do PSModulePath](./modifying-the-psmodulepath-installation-path.md).
O código a seguir descreve como importar um módulo:

```powershell
Import-Module myModule
```

Supondo que MyModule estava localizado no `PSModulePath` , o PowerShell carregaria MyModule na memória ativa. Se MyModule não estiver localizado em um `PSModulePath` caminho, você ainda poderá dizer explicitamente ao PowerShell onde encontrá-lo:

```powershell
Import-Module -Name C:\myRandomDirectory\myModule -Verbose
```

Você também pode usar o `-Verbose` parâmetro para identificar o que está sendo exportado fora do módulo e o que está sendo importado para a memória ativa. As exportações e as importações restringem o que é exposto ao usuário: a diferença é quem está controlando a visibilidade. Essencialmente, as exportações são controladas pelo código dentro do módulo. Por outro lado, as importações são controladas pela `Import-Module` chamada. Para obter mais informações, consulte **restringindo Membros que são importados**, abaixo.

## <a name="implicitly-importing-a-module-powershell-30"></a>Importando implicitamente um módulo (PowerShell 3,0)

A partir do Windows PowerShell 3.0, os módulos são importados automaticamente quando qualquer cmdlet ou função do módulo é usada em um comando. Esse recurso funciona em qualquer módulo em um diretório que está incluído no valor da variável de ambiente **PSModulePath** . No entanto, se você não salvar seu módulo em um caminho válido, ainda poderá carregá-los usando a opção [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) explícita, descrita acima.

As ações a seguir disparam a importação automática de um módulo, também conhecido como "carregamento automático de módulo".

- Usando um cmdlet em um comando. Por exemplo, a digitação `Get-ExecutionPolicy` importa o módulo Microsoft. PowerShell. Security que contém o `Get-ExecutionPolicy` cmdlet.

- Usando o cmdlet [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) para obter o comando. Por exemplo, a digitação `Get-Command Get-JobTrigger` importa o módulo **PSScheduledJob** que contém o `Get-JobTrigger` cmdlet. Um `Get-Command` comando que inclui caracteres curinga é considerado como descoberta e não dispara a importação de um módulo.

- Usando o cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) para obter ajuda para um cmdlet. Por exemplo, a digitação `Get-Help Get-WinEvent` importa o módulo Microsoft. PowerShell. Diagnostics que contém o `Get-WinEvent` cmdlet.

Para dar suporte à importação automática de módulos, o `Get-Command` cmdlet obtém todos os cmdlets e funções em todos os módulos instalados, mesmo que o módulo não seja importado para a sessão. Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) .

## <a name="the-importing-process"></a>O processo de importação

Quando um módulo é importado, um novo estado de sessão é criado para o módulo e um objeto [System. Management. Automation. PSModuleInfo](/dotnet/api/System.Management.Automation.PSModuleInfo) é criado na memória. Um estado de sessão é criado para cada módulo que é importado (isso inclui o módulo raiz e quaisquer módulos aninhados). Os membros que são exportados do módulo raiz, incluindo todos os membros que foram exportados para o módulo raiz por qualquer módulo aninhado, são então importados para o estado de sessão do chamador.

Os metadados de membros que são exportados de um módulo têm uma propriedade ModuleName. Essa propriedade é populada com o nome do módulo que as exportou.

> [!WARNING]
> Se o nome de um membro exportado usar um verbo não aprovado ou se o nome do membro usar caracteres restritos, um aviso será exibido quando o cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) for executado.

Por padrão, o cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) não retorna nenhum objeto para o pipeline. No entanto, o cmdlet dá suporte a um parâmetro **PassThru** que pode ser usado para retornar um objeto [System. Management. Automation. PSModuleInfo](/dotnet/api/System.Management.Automation.PSModuleInfo) para cada módulo que é importado. Para enviar a saída para o host, os usuários devem executar o cmdlet [write-host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) .

## <a name="restricting--the-members-that-are-imported"></a>Restringindo os membros que são importados

Quando um módulo é importado usando o cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) , por padrão, todos os membros do módulo exportados são importados para a sessão, incluindo todos os comandos exportados para o módulo por um módulo aninhado. Por padrão, variáveis e aliases não são exportados. Para restringir os membros que são exportados, use um [manifesto de módulo](./how-to-write-a-powershell-module-manifest.md).
Para restringir os membros que são importados, use os parâmetros a seguir do `Import-Module` cmdlet.

- **Função**: esse parâmetro restringe as funções que são exportadas. (Se você estiver usando um manifesto de módulo, consulte a chave FunctionsToExport.)

- `**Cmdlet**: esse parâmetro restringe os cmdlets que são exportados (se você estiver usando um manifesto de módulo, consulte a chave CmdletsToExport).

- **Variável**: esse parâmetro restringe as variáveis que são exportadas (se você estiver usando um manifesto de módulo, consulte a chave VariablesToExport).

- **Alias**: esse parâmetro restringe os aliases que são exportados (se você estiver usando um manifesto de módulo, consulte a chave AliasesToExport).

## <a name="see-also"></a>Consulte Também

[Escrever um módulo do Windows PowerShell](./writing-a-windows-powershell-module.md)
