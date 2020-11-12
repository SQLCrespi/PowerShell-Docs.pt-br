---
description: A variável de ambiente PSModulePath contém uma lista de locais de pasta que são pesquisados para localizar módulos e recursos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_PSModulePath?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSModulePath
ms.openlocfilehash: 5d87f550b3aa8774ae81f68848d5aa252b2e5851
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524647"
---
# <a name="about-psmodulepath"></a>Sobre o PSModulePath

A `$env:PSModulePath` variável de ambiente contém uma lista de locais de pasta que são pesquisados para localizar módulos e recursos. O PowerShell pesquisa recursivamente cada pasta em busca de arquivos de módulo ( `.psd1` ou `.psm1` ).

Por padrão, os locais efetivos atribuídos a `$env:PSModulePath` são:

- Locais de todo o sistema: essas pastas contêm módulos que acompanham o PowerShell. Esses módulos são armazenados na `$PSHOME\Modules` pasta. Esse também é o local em que os módulos de gerenciamento do Windows estão instalados.

- Módulos instalados pelo usuário: são módulos instalados pelo usuário.
  `Install-Module` tem um parâmetro de **escopo** que permite que você especifique se o módulo está instalado para o usuário atual ou para todos os usuários. Para obter mais informações, consulte [install-Module](xref:PowerShellGet.Install-Module).

  - No Windows, o local do escopo **CurrentUser** específico do usuário é a `$HOME\Documents\PowerShell\Modules` pasta. O local do escopo **AllUsers** é `$env:ProgramFiles\PowerShell\Modules` .
  - Em sistemas não Windows, o local do escopo **CurrentUser** específico do usuário é a `$HOME/.local/share/powershell/Modules` pasta. O local do escopo **AllUsers** é `/usr/local/share/powershell/Modules` .

Além disso, os programas de instalação que instalam módulos em outros diretórios, como o diretório arquivos de programas, podem acrescentar seus locais ao valor de `$env:PSModulePath` .

> [!NOTE]
> No Windows, o local específico do usuário é a `PowerShell\Modules` pasta localizada na pasta **documentos** em seu perfil de usuário. O caminho específico desse local varia de acordo com a versão do Windows e se você está usando o redirecionamento de pasta. O Microsoft OneDrive também pode alterar o local da sua pasta de **documentos** . Você pode verificar o local da pasta **documentos** usando o seguinte comando: `[Environment]::GetFolderPath('MyDocuments')` .

## <a name="modifying-psmodulepath"></a>Modificando PSModulePath

Para alterar os diretórios de módulo padrão para a sessão atual, use o seguinte formato de comando para alterar o valor da `PSModulePath` variável de ambiente.

Por exemplo, para adicionar o `C:\Program Files\Fabrikam\Modules` diretório ao valor da variável de ambiente PSModulePath, digite:

```powershell
$Env:PSModulePath = $Env:PSModulePath+";C:\Program Files\Fabrikam\Modules"
```

O ponto e vírgula ( `;` ) no comando separa o novo caminho do caminho que o precede na lista. Em plataformas não Windows, os dois-pontos () separam `:` os locais de caminho na variável de ambiente.

Para alterar o valor de `PSModulePath` em cada sessão, adicione o comando anterior ao seu perfil do PowerShell ou use o método **SetEnvironmentVariable não** da classe **Environment** .

O comando a seguir usa o método **GetEnvironmentVariable** para obter a configuração do computador `PSModulePath` e o método **SetEnvironmentVariable não** para adicionar o `C:\Program Files\Fabrikam\Modules` caminho ao valor.

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'Machine')
```

Para adicionar um caminho para a configuração de usuário, altere o valor de destino para **usuário**.

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'User')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'User')
```

Para obter mais informações sobre os métodos da classe **System. Environment** , consulte [métodos de ambiente](/dotnet/api/system.environment).

## <a name="powershell-psmodulepath-construction"></a>Construção do PowerShell PSModulePath

O valor de `$env:PSModulePath` é construído cada vez que o PowerShell é iniciado.
O valor varia de acordo com a versão do PowerShell e como ele é iniciado.

### <a name="windows-powershell-startup"></a>Inicialização do Windows PowerShell

O Windows PowerShell usa a seguinte lógica para construir o `PSModulePath` na inicialização:

- Se `PSModulePath` não existir, combine **CurrentUser** , **AllUsers** e os `$PSHOME` caminhos dos módulos
- Se `PSModulePath` existir:
  - Se `PSModulePath` contém o `$PSHOME` caminho dos módulos:
    - O caminho dos módulos **AllUsers** é inserido antes do `$PSHOME` caminho dos módulos
  - restante
    - Basta usar `PSModulePath` conforme definido, pois o usuário removeu o local deliberadamente `$PSHOME`

O caminho do módulo **CurrentUser** será prefixado somente se o escopo do usuário `$env:PSModulePath` não existir. Caso contrário, o escopo do usuário `$env:PSModulePath` será usado conforme definido.

### <a name="powershell-core-6-startup"></a>Inicialização do PowerShell Core 6

O PowerShell Core 6 não usa o conteúdo de `$env:PSModulePath` se detectar que foi iniciado no PowerShell. Ele o substitui por:

- Módulos **CurrentUser** caminho + módulos **AllUsers** caminho + `$PSHOME` módulos caminho + módulo módulos do Windows PowerShell `$PSHOME` caminho.

### <a name="powershell-7-startup"></a>Inicialização do PowerShell 7

No Windows, para a maioria das variáveis de ambiente, se a variável no escopo do usuário existir, um novo processo usará esse valor somente se houver uma variável com escopo de computador com o mesmo nome.

No PowerShell 7, `PSModulePath` é tratado de maneira semelhante à forma como a `Path` variável de ambiente é tratada no Windows. No Windows, `Path` é tratado de forma diferente de outras variáveis de ambiente. Quando um processo é iniciado, o Windows combina o escopo do usuário `Path` com o escopo da máquina `Path` .

- Recuperar o escopo do usuário `PSModulePath`
- Comparar para processar variável de ambiente herdada `PSModulePath`
  - Se o mesmo:
    - Acrescente o **AllUsers** `PSModulePath` ao final seguindo a semântica da `Path` variável de ambiente
    - O caminho do Windows `System32` vem do computador definido `PSModulePath` , portanto, não precisa ser adicionado explicitamente
  - Se for diferente, trate como se o usuário o modificou explicitamente e não acrescente **AllUsers**`PSModulePath`
- Prefixo com o usuário PS7, o sistema e os `$PSHOME` caminhos nessa ordem
  - Se `powershell.config.json` contiver um escopo de usuário `PSModulePath` , use-o em vez do padrão para o usuário
  - Se `powershell.config.json` contiver um escopo do sistema `PSModulePath` , use-o em vez do padrão para o sistema

Os sistemas Unix não têm uma separação de variáveis de ambiente do usuário e do sistema.
`PSModulePath` é herdado e os caminhos específicos de PS7 são prefixados se ainda não estiverem definidos.

### <a name="starting-windows-powershell-from-powershell-7"></a>Iniciando o Windows PowerShell do PowerShell 7

Para essa discussão, o _Windows PowerShell_ significa `powershell.exe` e `powershell_ise.exe` .

O valor de `$env:PSModulePath` é copiado para `WinPSModulePath` com as seguintes modificações:

- Remover PS7 o caminho do módulo de usuário
- Remover PS7 o caminho do módulo do sistema
- Remover PS7 o `$PSHOME` caminho do módulo

Os caminhos PS7 são removidos para que os módulos PS7 não sejam carregados no Windows PowerShell. O `WinPSModulePath` valor é usado ao iniciar o Windows PowerShell.

### <a name="starting-powershell-7-from-windows-powershell"></a>Iniciando o PowerShell 7 do Windows PowerShell

A inicialização do PowerShell 7 continua no estado em que se encontra com a adição de caminhos herdados que o Windows PowerShell adicionou. Como os caminhos específicos do PS7 são prefixados, não há nenhum problema funcional.

### <a name="starting-powershell-6-from-powershell-7"></a>Iniciando o PowerShell 6 do PowerShell 7

O PowerShell Core 6 substitui `$env:PSModulePath` . Nenhuma alteração é feita.

### <a name="starting-powershell-7-from-powershell-6"></a>Iniciando o PowerShell 7 do PowerShell 6

A inicialização do PowerShell 7 continua no estado em que se encontra com a adição de caminhos herdados que o PowerShell Core 6 adicionou. Como os caminhos específicos do PS7 são prefixados, não há nenhum problema funcional.

## <a name="module-search-behavior"></a>Comportamento de pesquisa de módulo

O PowerShell pesquisa recursivamente cada pasta no **PSModulePath** para arquivos de módulo ( `.psd1` ou `.psm1` ). Esse padrão de pesquisa permite que várias versões do mesmo módulo sejam instaladas em pastas diferentes. Por exemplo:

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules\PowerShellGet

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----           8/14/2020  5:56 PM                1.0.0.1
d----           9/13/2019  3:53 PM                2.1.2
```

Por padrão, o PowerShell carrega o número de versão mais alto de um módulo quando várias versões são encontradas. Para carregar uma versão específica, use `Import-Module` com o parâmetro **FullyQualifiedName** . Para obter mais informações, consulte [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).

## <a name="see-also"></a>Confira também

- [about_Modules](about_Modules.md)
- [Métodos de ambiente](/dotnet/api/system.environment)
