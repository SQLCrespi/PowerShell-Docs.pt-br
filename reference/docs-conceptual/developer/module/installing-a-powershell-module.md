---
ms.date: 09/13/2016
ms.topic: reference
title: Instalar um módulo do PowerShell
description: Instalar um módulo do PowerShell
ms.openlocfilehash: 3c7a4413168934ca4de1912c9615a6ae0fc45788
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645330"
---
# <a name="installing-a-powershell-module"></a>Instalar um módulo do PowerShell

Depois de criar o módulo do PowerShell, provavelmente você desejará instalar o módulo em um sistema para que você ou outras pessoas possam usá-lo. Em termos gerais, isso consiste em copiar os arquivos do módulo (ou seja, o arquivo .psm1 ou o assembly binário, o manifesto do módulo e os outros arquivos associados) em um diretório no computador. Em um projeto muito pequeno, isso pode ser tão simples quanto copiar e colar os arquivos com o Windows Explorer em um computador remoto; no entanto, em soluções maiores, convém usar um processo de instalação mais sofisticado. Independentemente de como você obtém seu módulo no sistema, o PowerShell pode usar várias técnicas que permitirão aos usuários localizar e usar os módulos. Portanto, o principal problema da instalação é garantir que o PowerShell consiga encontrar o módulo. Para obter mais informações, confira [Importar um módulo do PowerShell](./importing-a-powershell-module.md).

## <a name="rules-for-installing-modules"></a>Regras para a instalação de módulos

As informações a seguir se relacionam a todos os módulos, incluindo aqueles que você cria para uso próprio, que obtém de outras partes e que você distribui para outras pessoas.

### <a name="install-modules-in-psmodulepath"></a>Instalar módulos no PSModulePath

Sempre que possível, instale todos os módulos em um caminho listado na variável de ambiente **PSModulePath** ou adicione o caminho do módulo ao valor da variável de ambiente **PSModulePath**.

A variável de ambiente **PSModulePath** ($Env:PSModulePath) contém os locais dos módulos do Windows PowerShell. Os cmdlets dependem do valor dessa variável de ambiente para localizar módulos.

Por padrão, o valor da variável de ambiente **PSModulePath** contém os diretórios de módulo de usuário e sistema a seguir, mas você pode adicionar e editar o valor.

- `$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)

  > [!WARNING]
  > Esse local é reservado para módulos que acompanham o Windows. Não instale módulos nesse local.

- `$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)

- `$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)

  Para obter o valor da variável de ambiente **PSModulePath**, use um dos comandos a seguir.

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  Para adicionar um caminho de módulo ao valor da variável de ambiente **PSModulePath**, use o formato de comando a seguir. Esse formato usa o método **SetEnvironmentVariable** da classe **System.Environment** para fazer uma alteração independente da sessão à variável de ambiente **PSModulePath**.

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > Depois de adicionar o caminho a **PSModulePath**, você deve transmitir uma mensagem de ambiente sobre a alteração. A transmissão da alteração permite que outros aplicativos, como o Shell, adotem a alteração. Para transmitir a alteração, faça com que o código de instalação do produto envie a mensagem **WM_SETTINGCHANGE** com `lParam` definido como a cadeia de caracteres "Ambiente". Lembre-se de enviar a mensagem depois que o código de instalação do módulo atualizar **PSModulePath**.

### <a name="use-the-correct-module-directory-name"></a>Usar o nome do diretório de módulo correto

Um módulo bem formado será aquele armazenado em um diretório que tem o mesmo nome que o nome base de pelo menos um arquivo no diretório de módulo. Se um módulo não estiver bem formado, o Windows PowerShell não o reconhecerá como um módulo.

O "nome base" de um arquivo é o nome do arquivo sem a extensão. Em um módulo bem formado, o nome do diretório que contém os arquivos do módulo deve corresponder ao nome base de pelo menos um arquivo no módulo.

Por exemplo, no módulo Fabrikam da amostra, o diretório que contém os arquivos do módulo é denominado "Fabrikam" e pelo menos um arquivo tem o nome base "Fabrikam". Neste caso, Fabrikam.psd1 e Fabrikam.dll têm o nome base "Fabrikam".

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a>Efeito da instalação incorreta

Se o módulo não estiver bem formado e o local dele não estiver incluído no valor da variável de ambiente **PSModulePath**, os recursos da descoberta básica do Windows PowerShell, como os indicados a seguir, não funcionarão.

- O recurso Carregamento Automático de Módulo não consegue importar o módulo automaticamente.

- O parâmetro `ListAvailable` do cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) não consegue localizar o módulo.

- O cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) não consegue localizar o módulo. Para importar o módulo, você deve fornecer o caminho completo até o arquivo de módulo raiz ou o arquivo de manifesto do módulo.

  Recursos adicionais, como os indicados a seguir, só funcionarão se o módulo for importado para a sessão. Em módulos bem formados na variável de ambiente **PSModulePath**, esses recursos funcionam mesmo quando o módulo não é importado para a sessão.

- O cmdlet [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) não consegue localizar comandos no módulo.

- Os cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) não conseguem atualizar nem salvar a ajuda para o módulo.

- O cmdlet [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) não consegue localizar nem exibir os comandos no módulo.

  Os comandos do módulo estão ausentes na janela `Show-Command` no ISE (Ambiente de Script Integrado) do Windows PowerShell.

## <a name="where-to-install-modules"></a>Onde instalar os módulos

Esta seção explica onde instalar os módulos do Windows PowerShell no sistema de arquivos. O local depende de como o módulo é usado.

### <a name="installing-modules-for-a-specific-user"></a>Instalar módulos para um usuário específico

Se você criar seu próprio módulo ou obtiver um módulo de terceiros, como no site da comunidade do Windows PowerShell, e quiser que o módulo fique disponível somente para sua conta de usuário, instale-o no diretório Modules específico do usuário.

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

O diretório Modules específico do usuário é adicionado ao valor da variável de ambiente **PSModulePath** por padrão.

### <a name="installing-modules-for-all-users-in-program-files"></a>Instalar módulos para todos os usuários nos Arquivos de Programas

Se você quiser que um módulo fique disponível para todas as contas de usuário do computador, instale-o no local dos Arquivos de Programas.

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> O local dos Arquivos de Programas é adicionado por padrão ao valor da variável de ambiente PSModulePath no Windows PowerShell 4.0 e posterior. Para versões anteriores do Windows PowerShell, você pode criar manualmente o local dos Arquivos de Programas (%ProgramFiles%\WindowsPowerShell\Modules) e adicionar esse caminho à variável de ambiente PSModulePath, como descrito acima.

### <a name="installing-modules-in-a-product-directory"></a>Instalar módulos em um diretório de produto

Se você estiver distribuindo o módulo para terceiros, use o local padrão dos Arquivos de Programas descrito acima ou crie um subdiretório próprio específico do produto ou da empresa no diretório %ProgramFiles%.

Por exemplo, a Fabrikam Technologies, uma empresa fictícia, está enviando um módulo do Windows PowerShell para seu produto Fabrikam Manager. O instalador do módulo cria o subdiretório Modules no subdiretório do produto Fabrikam Manager.

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

Para habilitar os recursos de descoberta de módulo do Windows PowerShell a localizarem o módulo Fabrikam, o instalador do módulo Fabrikam adiciona o local do módulo ao valor da variável de ambiente **PSModulePath**.

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a>Instalar módulos no diretório de arquivos comuns

Se um módulo for usado por vários componentes ou versões de um produto, instale-o em um subdiretório específico de módulo no subdiretório %ProgramFiles%\Common Files\Modules.

No exemplo a seguir, o módulo Fabrikam é instalado no subdiretório Fabrikam do subdiretório `%ProgramFiles%\Common Files\Modules`. Observe que cada módulo reside em seu próprio subdiretório dentro do subdiretório Modules.

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

O instalador garante que o valor da variável de ambiente **PSModulePath** inclua o caminho do subdiretório de módulos de arquivos comuns.

```powershell
$m = $env:ProgramFiles + '\Common Files\Modules'
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$q = $p -split ';'
if ($q -notContains $m) {
    $q += ";$m"
}
$p = $q -join ';'
[Environment]::SetEnvironmentVariable("PSModulePath", $p)
```

## <a name="installing-multiple-versions-of-a-module"></a>Instalar várias versões de um módulo

Para instalar várias versões do mesmo módulo, use o procedimento a seguir.

1. Crie um diretório para cada versão do módulo. Inclua o número de versão no nome do diretório.
2. Crie um manifesto do módulo para cada versão. No valor da chave **ModuleVersion** no manifesto, insira o número da versão do módulo. Salve o arquivo de manifesto (.psd1) no diretório específico da versão do módulo.
3. Adicione o caminho da pasta raiz do módulo ao valor da variável de ambiente **PSModulePath**, conforme mostrado nos exemplos a seguir.

Para importar uma versão específica do módulo, o usuário final pode usar os parâmetros `MinimumVersion` ou `RequiredVersion` do cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).

Por exemplo, se o módulo Fabrikam estiver disponível nas versões 8.0 e 9.0, a estrutura do diretório do módulo Fabrikam poderá ser semelhante à que está a seguir.

 ```
C:\Program Files
Fabrikam Manager
  Fabrikam8
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "8.0")
      Fabrikam.dll (module assembly)
  Fabrikam9
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "9.0")
      Fabrikam.dll (module assembly)
```

O instalador adiciona os caminhos do módulo ao valor da variável de ambiente **PSModulePath**.

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

Quando essas etapas forem concluídas, o parâmetro **ListAvailable** do cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) obterá os dois módulos do Fabrikam. Para importar um módulo específico, use os parâmetros `MinimumVersion` ou `RequiredVersion` do cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).

Se os dois módulos forem importados na mesma sessão e contiverem cmdlets com os mesmos nomes, os cmdlets importados por último estarão em vigor na sessão.

## <a name="handling-command-name-conflicts"></a>Manipular conflitos de nome de comando

Conflitos de nome de comando podem ocorrer quando os comandos que um módulo exporta têm o mesmo nome dos comandos da sessão do usuário.

Quando uma sessão contém dois comandos com o mesmo nome, o Windows PowerShell executa o tipo de comando que tem precedência. Quando uma sessão contém dois comandos com o mesmo nome e o mesmo tipo, o Windows PowerShell executa o comando adicionado por último à sessão. Para executar um comando que não é executado por padrão, os usuários podem qualificar o nome do comando com o nome do módulo.

Por exemplo, se a sessão contiver a função `Get-Date` e o cmdlet `Get-Date`, o Windows PowerShell executará a função por padrão. Para executar o cmdlet, inicie o comando com o nome do módulo, como:

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

Para evitar conflitos de nome, os autores de módulos podem usar a chave **DefaultCommandPrefix** no manifesto do módulo a fim de especificar um prefixo de substantivo para todos os comandos exportados do módulo.

Os usuários podem usar o parâmetro **Prefix** do cmdlet `Import-Module` para usar um prefixo alternativo. O valor do parâmetro **Prefix** tem precedência sobre o valor da chave **DefaultCommandPrefix**.

## <a name="see-also"></a>Consulte Também

[about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[Escrever um módulo do Windows PowerShell](./writing-a-windows-powershell-module.md)
