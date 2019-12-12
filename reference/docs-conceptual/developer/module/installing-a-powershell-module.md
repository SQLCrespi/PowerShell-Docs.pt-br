---
title: Instalando um módulo do PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb82827e-fdb7-4cbf-b3d4-093e72b3ff0e
caps.latest.revision: 28
ms.openlocfilehash: 60ac4bf9089232a9fa879e835e32da53422489fd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367065"
---
# <a name="installing-a-powershell-module"></a>Instalar um módulo do PowerShell

Depois de criar o módulo do PowerShell, você provavelmente desejará instalar o módulo em um sistema, para que você ou outros usuários possam usá-lo. Em termos gerais, isso consiste em copiar os arquivos de módulo (ou seja, o. psm1 ou o assembly binário, o manifesto do módulo e todos os outros arquivos associados) para um diretório nesse computador. Para um projeto muito pequeno, isso pode ser tão simples quanto copiar e colar os arquivos com o Windows Explorer em um único computador remoto; no entanto, para soluções maiores, você pode desejar usar um processo de instalação mais sofisticado. Independentemente de como você obtém seu módulo no sistema, o PowerShell pode usar várias técnicas que permitirão que os usuários localizem e usem seus módulos. Portanto, o principal problema para a instalação é garantir que o PowerShell poderá encontrar seu módulo. Para obter mais informações, consulte [importando um módulo do PowerShell](./importing-a-powershell-module.md).

## <a name="rules-for-installing-modules"></a>Regras para instalação de módulos

As informações a seguir pertencem a todos os módulos, incluindo módulos que você cria para seu próprio uso, módulos que você obtém de outras partes e módulos que você distribui para outras pessoas.

### <a name="install-modules-in-psmodulepath"></a>Instalar módulos no PSModulePath

Sempre que possível, instale todos os módulos em um caminho que esteja listado na variável de ambiente **PSModulePath** ou adicione o caminho do módulo ao valor da variável de ambiente **PSModulePath** .

A variável de ambiente **PSModulePath** ($env:P smodulepath) contém os locais dos módulos do Windows PowerShell. Os cmdlets dependem do valor dessa variável de ambiente para localizar módulos.

Por padrão, o valor da variável de ambiente **PSModulePath** contém os seguintes diretórios de sistema e de módulo de usuário, mas você pode adicionar e editar o valor.

- `$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)

  > [!WARNING]
  > Esse local é reservado para módulos que acompanham o Windows. Não instale módulos nesse local.

- `$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)

- `$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)

  Para obter o valor da variável de ambiente **PSModulePath** , use um dos comandos a seguir.

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  Para adicionar um caminho de módulo ao valor do valor da variável de ambiente **PSModulePath** , use o seguinte formato de comando. Esse formato usa o método **SetEnvironmentVariable não** da classe **System. Environment** para fazer uma alteração independente de sessão na variável de ambiente **PSModulePath** .

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > Depois de adicionar o caminho para **PSModulePath**, você deve transmitir uma mensagem de ambiente sobre a alteração. A transmissão da alteração permite que outros aplicativos, como o Shell, escolham a alteração. Para difundir a alteração, peça ao código de instalação do produto para enviar uma mensagem de **WM_SETTINGCHANGE** com `lParam` definido como a cadeia de caracteres "ambiente". Lembre-se de enviar a mensagem depois que o código de instalação do módulo tiver atualizado o **PSModulePath**.

### <a name="use-the-correct-module-directory-name"></a>Usar o nome do diretório de módulo correto

Um módulo bem formado é um módulo que é armazenado em um diretório que tem o mesmo nome que o nome base de pelo menos um arquivo no diretório do módulo. Se um módulo não estiver bem formado, o Windows PowerShell não o reconhecerá como um módulo.

O "nome base" de um arquivo é o nome sem a extensão de nome de arquivo. Em um módulo bem formado, o nome do diretório que contém os arquivos de módulo deve corresponder ao nome de base de pelo menos um arquivo no módulo.

Por exemplo, no módulo Fabrikam de exemplo, o diretório que contém os arquivos de módulo é denominado "fabrikam" e pelo menos um arquivo tem o nome de base "fabrikam". Nesse caso, a Fabrikam. psd1 e a Fabrikam. dll têm o nome de base "fabrikam".

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

Se o módulo não estiver bem formado e seu local não estiver incluído no valor da variável de ambiente **PSModulePath** , os recursos básicos de descoberta do Windows PowerShell, como o seguinte, não funcionarão.

- O recurso de carregamento automático do módulo não pode importar o módulo automaticamente.

- O parâmetro `ListAvailable` do cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) não pode localizar o módulo.

- O cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) não pode localizar o módulo. Para importar o módulo, você deve fornecer o caminho completo para o arquivo de módulo raiz ou arquivo de manifesto de módulo.

  Recursos adicionais, como os seguintes, não funcionam, a menos que o módulo seja importado para a sessão. Em módulos bem formados na variável de ambiente **PSModulePath** , esses recursos funcionam mesmo quando o módulo não é importado para a sessão.

- O cmdlet [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) não pode localizar comandos no módulo.

- Os cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) não podem atualizar ou salvar a ajuda do módulo.

- O cmdlet [show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) não pode localizar e exibir os comandos no módulo.

  Os comandos no módulo estão ausentes na janela de `Show-Command` no Ambiente de Script Integrado do Windows PowerShell (ISE).

## <a name="where-to-install-modules"></a>Onde instalar os módulos

Esta seção explica onde no sistema de arquivos instalar os módulos do Windows PowerShell. O local depende de como o módulo é usado.

### <a name="installing-modules-for-a-specific-user"></a>Instalando módulos para um usuário específico

Se você criar seu próprio módulo ou obter um módulo de outra parte, como um site da Comunidade do Windows PowerShell, e desejar que o módulo esteja disponível somente para sua conta de usuário, instale o módulo em seu diretório de módulos específicos do usuário.

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

O diretório de módulos específicos do usuário é adicionado ao valor da variável de ambiente **PSModulePath** por padrão.

### <a name="installing-modules-for-all-users-in-program-files"></a>Instalando módulos para todos os usuários em arquivos de programas

Se você quiser que um módulo esteja disponível para todas as contas de usuário no computador, instale o módulo no local arquivos de programas.

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> O local dos arquivos de programas é adicionado ao valor da variável de ambiente PSModulePath por padrão no Windows PowerShell 4,0 e posterior. Para versões anteriores do Windows PowerShell, você pode criar manualmente o local dos arquivos de programas ((%ProgramFiles%\WindowsPowerShell\Modules) e adicionar esse caminho à sua variável de ambiente PSModulePath, conforme descrito acima.

### <a name="installing-modules-in-a-product-directory"></a>Instalando módulos em um diretório de produto

Se você estiver distribuindo o módulo para outras partes, use o local dos arquivos de programas padrão descritos acima ou crie seu próprio subdiretório específico da empresa ou do produto do diretório% ProgramFiles%.

Por exemplo, a Fabrikam Technologies, uma empresa fictícia, está enviando um módulo do Windows PowerShell para seu produto Fabrikam Manager. O instalador do módulo cria um subdiretório de módulos no subdiretório do produto Fabrikam Manager.

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

Para habilitar os recursos de descoberta de módulo do Windows PowerShell para localizar o módulo Fabrikam, o instalador do módulo Fabrikam adiciona o local do módulo ao valor da variável de ambiente **PSModulePath** .

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a>Instalando módulos no diretório de arquivos comuns

Se um módulo for usado por vários componentes de um produto ou por várias versões de um produto, instale o módulo em um subdiretório específico de módulo do subdiretório%ProgramFiles%\Common Files\Modules.

No exemplo a seguir, o módulo Fabrikam é instalado em um subdiretório Fabrikam do subdiretório `%ProgramFiles%\Common Files\Modules`. Observe que cada módulo reside em seu próprio subdiretório no subdiretório módulos.

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

Em seguida, o instalador garante que o valor da variável de ambiente **PSModulePath** inclui o caminho do subdiretório de módulos de arquivos comuns.

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

## <a name="installing-multiple-versions-of-a-module"></a>Instalando várias versões de um módulo

Para instalar várias versões do mesmo módulo, use o procedimento a seguir.

1. Crie um diretório para cada versão do módulo. Inclua o número de versão no nome do diretório.
2. Crie um manifesto de módulo para cada versão do módulo. No valor da chave **ModuleVersion** no manifesto, insira o número de versão do módulo. Salve o arquivo de manifesto (. psd1) no diretório específico da versão do módulo.
3. Adicione o caminho da pasta raiz do módulo ao valor da variável de ambiente **PSModulePath** , conforme mostrado nos exemplos a seguir.

Para importar uma versão específica do módulo, o usuário final pode usar os parâmetros `MinimumVersion` ou `RequiredVersion` do cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) .

Por exemplo, se o módulo Fabrikam estiver disponível nas versões 8,0 e 9,0, a estrutura de diretório do módulo Fabrikam poderá ser semelhante à seguinte.

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

O instalador adiciona ambos os caminhos de módulo ao valor de variável de ambiente **PSModulePath** .

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

Quando essas etapas forem concluídas, o parâmetro **listAvailable** do cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) obterá ambos os módulos da Fabrikam. Para importar um módulo específico, use os parâmetros `MinimumVersion` ou `RequiredVersion` do cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) .

Se ambos os módulos forem importados para a mesma sessão e os módulos contiverem cmdlets com os mesmos nomes, os cmdlets que são importados por último entram em vigor na sessão.

## <a name="handling-command-name-conflicts"></a>Manipulando conflitos de nome de comando

Conflitos de nome de comando podem ocorrer quando os comandos que um módulo exporta têm o mesmo nome que os comandos na sessão do usuário.

Quando uma sessão contém dois comandos que têm o mesmo nome, o Windows PowerShell executa o tipo de comando que tem precedência. Quando uma sessão contém dois comandos que têm o mesmo nome e o mesmo tipo, o Windows PowerShell executa o comando que foi adicionado à sessão mais recentemente. Para executar um comando que não é executado por padrão, os usuários podem qualificar o nome do comando com o nome do módulo.

Por exemplo, se a sessão contiver uma função `Get-Date` e o cmdlet `Get-Date`, o Windows PowerShell executará a função por padrão. Para executar o cmdlet, preceda o comando com o nome do módulo, como:

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

Para evitar conflitos de nome, os autores de módulo podem usar a chave **DefaultCommandPrefix** no manifesto do módulo para especificar um prefixo de substantivo para todos os comandos exportados do módulo.

Os usuários podem usar o parâmetro **prefix** do cmdlet `Import-Module` para usar um prefixo alternativo. O valor do parâmetro **prefix** tem precedência sobre o valor da chave **DefaultCommandPrefix** .

## <a name="see-also"></a>Consulte Também

[about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[Escrevendo um módulo do Windows PowerShell](./writing-a-windows-powershell-module.md)
