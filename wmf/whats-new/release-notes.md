---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,instalação
title: Notas de versão do WMF 5.x
ms.openlocfilehash: 8924240a4bbedcd34bc68b7cacdd23189a3716d6
ms.sourcegitcommit: 00083f07b13c73b86936e7d7307397df27c63c04
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848148"
---
# <a name="windows-management-framework-wmf-5x-release-notes"></a>Notas de versão do Windows Management Framework (WMF) 5.x

## <a name="wmf-50-changes"></a>Alterações do WMF 5.0

- O PowerShell 5.0 adiciona um novo fluxo **Information** estruturado
- Aprimoramentos do DSC, incluindo quatro novos recursos de DSC:
  - WindowsFeatureSet
  - WindowsOptionalFeatureSet
  - ServiceSet
  - ProcessSet
- Foi adicionada a Administração Suficiente para permitir a administração baseada em funções por meio da comunicação remota do PowerShell
- O PowerShell 5.0 estende a linguagem para incluir enumerações e classes definidas pelo usuário
- Os recursos de depuração no ISE do PowerShell foram aprimorados e a depuração remota foi adicionada
- Os módulos PowerShellGet e PackageManagement foram adicionados
- As transcrições e logs de script do PowerShell foram aprimorados
- Foram adicionados cmdlets da CMS (Sintaxe de Mensagem Criptografada)
- O WMF 5.0 inclui o módulo NetworkSwitchManager para o Windows
- Adicionado o módulo Microsoft.PowerShell.ODataUtils
- Adicionado suporte para SIL (Log de Inventário de Software)
- Cmdlets novos ou atualizados do servidor em resposta às questões e solicitações dos usuários

## <a name="wmf-51-changes"></a>Alterações do WMF 5.1

O WMF 5.1 inclui os componentes PowerShell, WMI, WinRM e SIL (Log de Inventário de Software) que foram lançados com o Windows Server 2016. O WMF 5.1 pode ser instalado no Windows 7, Windows 8.1, Windows Server 2008 R2, 2012 e 2012 R2 e fornece diversos aprimoramentos para o WMF 5.0, incluindo:

- Novos cmdlets
- Os aprimoramentos do PowerShellGet incluem a imposição de módulos assinados e a instalação de módulos JEA
- Suporte acrescentado para o PackageManagement para Contêineres, Configuração de CBS, configuração baseada em EXE, pacotes CAB
- Melhorias de depuração para classes DSC e PowerShell
- Aprimoramentos de segurança, incluindo a imposição de módulos de catálogo assinado provenientes do Servidor de Recepção e ao usar cmdlets do PowerShellGet
- Respostas para diversos problemas e solicitações de usuários

> [!IMPORTANT]
> Antes de instalar o WMF 5.1 no Windows Server 2008 ou no Windows 7, confirme se o WMF 3.0 não está instalado. Para obter mais informações, confira [Pré-requisitos do WMF 5.1 para Windows Server 2008 R2 SP1 e Windows 7 SP1](../setup/install-configure.md#wmf-51-prerequisites-for-windows-server-2008-r2-sp1-and-windows-7-sp1).

## <a name="powershell-editions"></a>Edições do PowerShell

Da versão 5.1 em diante, o PowerShell está disponível em edições diferentes que denotam diferentes conjuntos de recursos e compatibilidade de plataforma.

- **Desktop Edition:** criada no .NET Framework, fornece compatibilidade com scripts e módulos destinados a versões do PowerShell em execução em edições de volume completo do Windows, como Server Core e Windows Desktop.
- **Core Edition:** criada no .NET Core, oferece compatibilidade com scripts e módulos destinados a versões do PowerShell executadas em edições de volume reduzido do Windows, como o Nano Server e Windows IoT.

### <a name="learn-more-about-using-powershell-editions"></a>Saiba mais sobre como usar as edições do PowerShell

- [Determinar a edição em execução do PowerShell usando $PSVersionTable](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [Filtrar resultados de Get-Module por CompatiblePSEditions usando o parâmetro PSEdition](/powershell/module/microsoft.powershell.core/get-module)
- [Impedir a execução do script, a menos que seja ele executado em uma edição compatível do PowerShell](/powershell/gallery/concepts/script-psedition-support)
- [Declarar a compatibilidade de um módulo para versões específicas do PowerShell](/powershell/gallery/concepts/module-psedition-support)

## <a name="module-analysis-cache"></a>Cache de análise do módulo

Do WMF 5.1 em diante, o PowerShell fornece controle sobre o arquivo que é usado para cache de dados sobre um módulo, como os comandos que exporta.

Por padrão, esse cache é armazenado no arquivo `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`. O cache normalmente é lido na inicialização ao procurar um comando e é gravado em um thread em segundo plano em algum momento após a importação de um módulo.

Para alterar o local padrão do cache, defina a variável de ambiente `$env:PSModuleAnalysisCachePath` antes de iniciar o PowerShell. As alterações a esta variável de ambiente afetarão apenas processos filhos. O valor deve nomear um caminho completo (incluindo nome do arquivo) em que o PowerShell tenha permissão para criar e gravar arquivos. Para desabilitar o cache de arquivo, defina esse valor para um local inválido, por exemplo:

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

Isso define o caminho para um dispositivo inválido. Se o PowerShell não conseguir gravar no caminho, nenhum erro será retornado, mas você poderá ver relatórios de erro usando um rastreamento:

```powershell
Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
```

Ao gravar o cache, o PowerShell verificará se há módulos que não existem mais para evitar um cache desnecessariamente grande. Às vezes, essas verificações não são desejáveis, o que, nesse caso, você pode desativá-las configurando:

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

Definir essa variável de ambiente entrará em vigor imediatamente no processo atual.

## <a name="specifying-module-version"></a>Especificando a versão do módulo

No WMF 5.1, o `using module` comporta-se da mesma maneira que outras construções relacionadas ao módulo no PowerShell.
Anteriormente, não era possível especificar uma versão de módulo específica; se houvesse várias versões presentes, isso resultaria em um erro.

No WMF 5.1:

- Você pode usar o [Construtor ModuleSpecification (tabela de hash)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).

  Essa tabela de hash tem o mesmo formato que `Get-Module -FullyQualifiedName`.

  **Exemplo:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`

- Se houver várias versões do módulo, o PowerShell usará a **mesma lógica de resolução** que `Import-Module` e não retornará um erro – o mesmo comportamento que `Import-Module` e `Import-DscResource`.

## <a name="improvements-to-pester"></a>Melhorias no Pester

No WMF 5.1, a versão do Pester fornecida com o PowerShell foi atualizada de 3.3.5 para 3.4.0.
Essa atualização permite melhorar o comportamento do Pester no Nano Server.

As alterações no Pester podem ser analisadas inspecionando o [ChangeLog](https://github.com/pester/Pester/blob/master/CHANGELOG.md) no repositório do GitHub.
