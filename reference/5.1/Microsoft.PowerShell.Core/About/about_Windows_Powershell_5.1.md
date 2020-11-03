---
description: Descreve os novos recursos que estão incluídos no Windows PowerShell 5,1.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/17/2018
online version: https://docs.microsoft.com/powershell/module/?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_5.1
ms.openlocfilehash: 567af048dd137c0287c6eba4ccc42a77055c0c92
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196561"
---
# <a name="about_windows_powershell_51"></a>about_Windows_PowerShell_5.1

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve os novos recursos que estão incluídos no Windows PowerShell 5,1.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O Windows PowerShell 5,1 inclui recursos novos e significativos que estendem seu uso, melhoram sua usabilidade e permitem controlar e gerenciar ambientes baseados no Windows de forma mais fácil e abrangente.

O Windows PowerShell 5,1 é compatível com versões anteriores. Os cmdlets, provedores, módulos, snap-ins, scripts, funções e perfis que foram projetados para o Windows PowerShell 4,0, o Windows PowerShell 3,0 e o Windows PowerShell 2,0 geralmente funcionam no Windows PowerShell 5,1 sem alterações.

- Novos cmdlets: usuários e grupos locais; Get-ComputerInfo
- Os aprimoramentos do PowerShellGet incluem a imposição de módulos assinados e a instalação de módulos JEA
- Suporte acrescentado para o PackageManagement para Contêineres, Configuração de CBS, configuração baseada em EXE, pacotes CAB
- Melhorias de depuração para classes DSC e PowerShell
- Aprimoramentos de segurança, incluindo a imposição de módulos de catálogo assinado provenientes do Servidor de Recepção e ao usar cmdlets do PowerShellGet
- Respostas para diversos problemas e solicitações de usuários

O Windows PowerShell 5,1 é instalado por padrão no Windows Server 2016 e Windows 10. Para instalar o Windows PowerShell 5,1 no Windows Server 2012 R2, Windows 8.1 Enterprise ou Windows 8.1 Pro, consulte [instalar e configurar o WMF 5,1](/powershell/scripting/wmf/setup/install-configure).
Certifique-se de ler os detalhes do download e atender a todos os requisitos do sistema antes de instalar o Windows Management Framework 5,1.

Você também pode ler sobre as alterações no Windows PowerShell 5,1 em [novidades do Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).

## <a name="new-scenarios-and-features-in-wmf-51"></a>Novos cenários e recursos no WMF 5.1

> Observação: essas informações são preliminares e estão sujeitas a alteração.

### <a name="powershell-editions"></a>Edições do PowerShell
A partir da versão 5.1, o PowerShell está disponível em diferentes edições que denotam os vários conjuntos de recursos e compatibilidades de plataforma.

- **Desktop Edition:** Criado no .NET Framework; fornece compatibilidade com scripts e módulos destinados a versões do PowerShell em execução em edições de volume completo do Windows, como Server Core e Windows Desktop.
- **Core Edition:** criada no .NET Core, oferece compatibilidade com scripts e módulos destinados a versões do PowerShell executadas em edições de volume reduzido do Windows, como o Nano Server e Windows IoT.

**Saiba mais sobre como usar as edições do PowerShell**

- [Determinar a edição em execução do PowerShell usando $PSVersionTable](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [Filtrar resultados de Get-Module por CompatiblePSEditions usando o parâmetro PSEdition](/powershell/module/microsoft.powershell.core/get-module)
- [Impedir a execução do script, a menos que seja ele executado em uma edição compatível do PowerShell](/powershell/scripting/gallery/concepts/script-psedition-support)
- [Declarar a compatibilidade de um módulo para versões específicas do PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support)

### <a name="catalog-cmdlets"></a>Cmdlets de Catálogo

Dois novos cmdlets foram adicionados no módulo [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)); eles geram e validam os arquivos de catálogo do Windows.

#### <a name="new-filecatalog"></a>New-FileCatalog

New-FileCatalog cria um arquivo de catálogo do Windows para o conjunto de arquivos e pastas.
Este arquivo de catálogo contém hashes para todos os arquivos nos caminhos especificados. Os usuários podem distribuir o conjunto de pastas juntamente com o arquivo de catálogo correspondente que representa essas pastas. Essas informações são úteis para validar se as alterações foram feitas nas pastas desde a hora de criação do catálogo.

```
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>]
 [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

Há suporte para as versões 1 e 2 do catálogo. A versão 1 usa o algoritmo de hash SHA1 para criar hashes de arquivo; a versão 2 usa SHA256. Não há suporte para a versão 2 do catálogo no *Windows Server 2008 R2* ou no *Windows 7* . Você deve usar a versão 2 do catálogo no *Windows 8* , no *Windows Server 2012* e nos sistemas operacionais posteriores.

Para verificar a integridade do arquivo de catálogo (Pester.cat, no exemplo acima), assine-o usando o cmdlet [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature).

#### <a name="test-filecatalog"></a>Test-FileCatalog

Test-FileCatalog valida o catálogo que representa um conjunto de pastas.

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>]
 [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

Este cmdlet compara todos os hashes de arquivos e seus caminhos relativos encontrados no *catálogo* com aqueles no *disco* . Se detectar qualquer incompatibilidade entre os hashes e os caminhos de arquivo, o status será retornado como *ValidationFailed* . Os usuários podem recuperar todas essas informações usando o parâmetro *-Detailed* . Ele também exibe o status da assinatura do catálogo na propriedade *Signature* , que é equivalente a chamar o cmdlet [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) no arquivo de catálogo. Os usuários também podem ignorar qualquer arquivo durante a validação usando o parâmetro *-FilesToSkip* .

### <a name="module-analysis-cache"></a>Cache de análise do módulo

Do WMF 5.1 em diante, o PowerShell fornece controle sobre o arquivo que é usado para cache de dados sobre um módulo, como os comandos que exporta.

Por padrão, esse cache é armazenado no arquivo `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`. O cache normalmente é lido na inicialização ao procurar um comando e é gravado em um thread em segundo plano em algum momento após a importação de um módulo.

Para alterar o local padrão do cache, defina a variável de ambiente `$env:PSModuleAnalysisCachePath` antes de iniciar o PowerShell. As alterações a esta variável de ambiente afetarão apenas processos filhos. O valor deve nomear um caminho completo (incluindo nome do arquivo) em que o PowerShell tenha permissão para criar e gravar arquivos. Para desabilitar o cache de arquivo, defina esse valor para um local inválido, por exemplo:

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

Isso define o caminho para um dispositivo inválido. Se o PowerShell não conseguir gravar no caminho, nenhum erro será retornado, mas você poderá ver relatórios de erro usando um rastreamento:

```powershell
Trace-Command -PSHost -Name Modules -Expression {
  Import-Module Microsoft.PowerShell.Management -Force
}
```

Ao gravar o cache, o PowerShell verificará se há módulos que não existem mais para evitar um cache desnecessariamente grande. Às vezes, essas verificações não são desejáveis, o que, nesse caso, você pode desativá-las configurando:

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

Definir essa variável de ambiente entrará em vigor imediatamente no processo atual.

### <a name="specifying-module-version"></a>Especificando a versão do módulo

No WMF 5.1, o `using module` comporta-se da mesma maneira que outras construções relacionadas ao módulo no PowerShell. Anteriormente, não era possível especificar uma versão de módulo específica; se houvesse várias versões presentes, isso resultaria em um erro.

No WMF 5.1:

* Você pode usar o [Construtor ModuleSpecification (tabela de hash)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor).
  Essa tabela de hash tem o mesmo formato que `Get-Module -FullyQualifiedName`.

  **Exemplo:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`

* Se houver várias versões do módulo, o PowerShell usará a **mesma lógica de resolução** que `Import-Module` e não retornará um erro – o mesmo comportamento que `Import-Module` e `Import-DscResource`.

### <a name="improvements-to-pester"></a>Melhorias no Pester

No WMF 5,1, a versão do Pester que acompanha o PowerShell foi atualizada de 3.3.5 para 3.4.0, com a adição do GitHub [PR # 484](https://github.com/pester/Pester/pull/484), que permite um melhor comportamento para Pester no nano Server.

Você pode revisar as alterações nas versões 3.3.5 a 3.4.0 inspecionando o arquivo ChangeLog.md em: https://github.com/pester/Pester/blob/master/CHANGELOG.md

## <a name="keywords"></a>Palavras-chave

O que há de novo no Windows PowerShell 5,1
