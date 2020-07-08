---
title: Como criar um módulo binário da Biblioteca Padrão
description: A Biblioteca Padrão do PowerShell nos permite criar módulos multiplataforma que funcionam no PowerShell Core e com o Windows PowerShell 5.1.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 51734fd9232e7c33b11c6c5a6abddbcc1f28413c
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149409"
---
# <a name="how-to-create-a-standard-library-binary-module"></a>Como criar um módulo binário da Biblioteca do PowerShell Standard

Recentemente, eu tive uma ideia de um módulo que queria implementar como módulo binário. Eu ainda preciso criar um usando a [Biblioteca Padrão do PowerShell][], então achei que esta seria uma boa oportunidade. Usei o guia [Como criar um módulo binário multiplataforma][] para criar esse módulo sem qualquer obstáculo.
Vamos examinar esse processo e eu farei alguns comentários extras ao longo do percurso.

> [!NOTE]
> A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][]. A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco. Confira o blog dele em [PowerShellExplained.com][].

## <a name="what-is-the-powershell-standard-library"></a>O que é a Biblioteca Padrão do PowerShell?

A Biblioteca Padrão do PowerShell nos permite criar módulos multiplataforma que funcionam no PowerShell Core e com o Windows PowerShell 5.1 (ou 3.0).

## <a name="planning-our-module"></a>Como planejar nosso módulo

O plano para esse módulo é criar uma pasta `src` para o código C# e estruturar o restante da maneira que eu faria para um módulo de script. Isso inclui usar um script de build para compilar tudo em uma pasta `output`. A estrutura de pastas tem esta aparência:

```
MyModule
├───src
├───Output
│   └───MyModule
├───MyModule
│   ├───Data
│   ├───Private
│   └───Public
└───Tests
```

## <a name="getting-started"></a>Introdução

Normalmente, uso um modelo Plaster, mas meu modelo atual ainda não tem suporte para módulo binário. Isso não é um problema. Vou criá-lo manualmente dessa vez.

Primeiro, preciso criar a pasta e o repositório git. Estou usando `$module` como um espaço reservado para o nome do módulo. Isso deve facilitar a reutilização desses exemplos, se necessário.

```powershell
$module = 'MyModule'
New-Item -Path $module -Type Directory
Set-Location $module
git init
```

Em seguida, crio as pastas do nível raiz.

```powershell
New-Item -Path 'src' -Type Directory
New-Item -Path 'Output' -Type Directory
New-Item -Path 'Tests' -Type Directory
New-Item -Path $module -Type Directory
```

### <a name="binary-module-setup"></a>Configuração do módulo binário

O foco deste artigo é o módulo binário, portanto, vamos começar por aí. Esta seção usa exemplos retirados do guia [Como criar um módulo binário multiplataforma][]. Examine esse guia se precisar de mais detalhes ou tiver problemas.

A primeira coisa que precisamos fazer é verificar a versão do [SDK do .NET Core][] que instalamos. Estou usando a versão 2.1.4, mas você precisa da versão 2.0.0 ou posterior para continuar.

```powershell
PS> dotnet --version
2.1.4
```

Estou trabalhando fora da pasta `src` nesta seção.

```powershell
Set-Location 'src'
```

Usando o comando dotnet, crie uma nova biblioteca de classes.

```powershell
dotnet new classlib --name $module
```

Isso criou o projeto de biblioteca em uma subpasta, mas não quero esse nível extra de aninhamento. Vou mover esses arquivos para um nível acima.

```powershell
Move-Item -Path .\$module\* -Destination .\
Remove-Item $module -Recurse
```

Defina a versão do SDK do .NET Core para o projeto. Tenho o SDK 2.1, portanto, vou especificar 2.1.0.
Especifique 2.0.0 se você estiver usando o SDK 2.0.

```powershell
dotnet new globaljson --sdk-version 2.1.0
```

Adicione o [pacote NuGet][] da Biblioteca Padrão do PowerShell ao projeto. Lembre-se de usar a versão mais recente disponível para o nível de compatibilidade de que você precisa. Eu usaria como padrão a versão mais recente, mas não acho que este módulo use recursos mais recentes do que o PowerShell 3.0.

```powershell
dotnet add package PowerShellStandard.Library --version 7.0.0-preview.1
```

Devemos ter uma pasta src parecida com esta:

```powershell
PS> Get-ChildItem
    Directory: \MyModule\src

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        7/14/2018   9:51 PM                obj
-a----        7/14/2018   9:51 PM             86 Class1.cs
-a----        7/14/2018  10:03 PM            259 MyModule.csproj
-a----        7/14/2018  10:05 PM             45 global.json
```

Agora estamos prontos para adicionar nosso próprio código ao projeto.

### <a name="building-a-binary-cmdlet"></a>Como criar um cmdlet binário

Precisamos atualizar a `src\Class1.cs` para conter este cmdlet inicial:

```csharp
using System;
using System.Management.Automation;

namespace MyModule
{
    [Cmdlet( VerbsDiagnostic.Resolve , "MyCmdlet")]
    public class ResolveMyCmdletCommand : PSCmdlet
    {
        [Parameter(Position=0)]
        public Object InputObject { get; set; }

        protected override void EndProcessing()
        {
            this.WriteObject(this.InputObject);
            base.EndProcessing();
        }
    }
}
```

Renomeie o arquivo para corresponder ao nome de classe.

```powershell
Rename-Item .\Class1.cs .\ResolveMyCmdletCommand.cs
```

Em seguida, podemos criar nosso módulo.

```powershell
PS> dotnet build

Microsoft (R) Build Engine version 15.5.180.51428 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

Restore completed in 18.19 ms for C:\workspace\MyModule\src\MyModule.csproj.
MyModule -> C:\workspace\MyModule\src\bin\Debug\netstandard2.0\MyModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:02.19
```

Podemos chamar `Import-Module` na nova dll para carregar nosso novo cmdlet.

```powershell
PS> Import-Module .\bin\Debug\netstandard2.0\$module.dll
PS> Get-Command -Module $module

CommandType Name                    Version Source
----------- ----                    ------- ------
Cmdlet      Resolve-MyCmdlet        1.0.0.0 MyModule
```

Se a importação falhar no sistema, tente atualizar o .NET para a versão 4.7.1 ou mais recente. O guia [Como criar um módulo binário multiplataforma][] fornece mais detalhes sobre o suporte e a compatibilidade para versões mais antigas do .NET.

### <a name="module-manifest"></a>Manifesto de módulo

Acho ótimo que possamos importar a dll e ter um módulo de trabalho. Gosto de mantê-lo e criar um manifesto de módulo. Precisaremos do manifesto se quisermos publicar no PSGallery mais tarde.

Da raiz do nosso projeto, podemos executar esse comando para criar o manifesto do módulo que precisamos.

```powershell
$manifestSplat = @{
    Path              = ".\$module\$module.psd1"
    Author            = 'Kevin Marquette'
    NestedModules     = @('bin\MyModule.dll')
    RootModule        = "$module.psm1"
    FunctionsToExport = @('Resolve-MyCmdlet')
}
New-ModuleManifest @manifestSplat
```

Também vou criar um módulo raiz vazio para funções futuras do PowerShell.

```powershell
Set-Content -Value '' -Path ".\$module\$module.psm1"
```

Isso me permite combinar tanto funções normais PowerShell, quanto cmdlets binários no mesmo projeto.

### <a name="building-the-full-module"></a>Como criar o módulo completo

Eu compilo tudo junto em uma pasta de saída. Precisamos criar um script de build para fazer isso. Normalmente, eu o adicionaria a um script `Invoke-Build`, mas vamos manter este exemplo simples. Adicione isso a um `build.ps1` na raiz do projeto.

```powershell
$module = 'MyModule'
Push-Location $PSScriptRoot

dotnet build $PSScriptRoot\src -o $PSScriptRoot\output\$module\bin
Copy-Item "$PSScriptRoot\$module\*" "$PSScriptRoot\output\$module" -Recurse -Force

Import-Module "$PSScriptRoot\Output\$module\$module.psd1"
Invoke-Pester "$PSScriptRoot\Tests"
```

Esses comandos compilam nossa DLL e a colocam em nossa pasta `output\$module\bin`. Em seguida, ele copia os outros arquivos do módulo para o local.

```
Output
└───MyModule
    │   MyModule.psd1
    │   MyModule.psm1
    │
    └───bin
            MyModule.deps.json
            MyModule.dll
            MyModule.pdb
```

A essa altura, podemos importar nosso módulo com o arquivo psd1.

```powershell
Import-Module ".\Output\$module\$module.psd1"
```

Partindo daqui, podemos soltar a pasta `.\Output\$module` em nosso diretório `$env:PSModulePath` e ela carregará nosso comando automaticamente sempre que precisarmos.

### <a name="update-dotnet-new-psmodule"></a>Atualização: novo PSModule do .NET

Aprendi que a ferramenta de `dotnet` tem um modelo de `PSModule`.

Todas as etapas descritas acima ainda são válidas, mas esse modelo elimina muitas delas. É um modelo bastante novo e que ainda está sendo aprimorado. Pode acreditar que ele vai continuar melhorando.

É assim que você usa install e modelo do PSModule.

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
dotnet new psmodule
dotnet build
Import-Module "bin\Debug\netstandard2.0\$module.dll"
Get-Module $module
```

Esse modelo minimamente viável se encarrega da adição do SDK do .NET, da Biblioteca Padrão do PowerShell, e cria uma classe de exemplo no projeto. Você pode compilá-lo e executá-lo imediatamente.

## <a name="important-details"></a>Detalhes importantes

Antes de encerrar este artigo, aqui estão alguns detalhes que vale a pena comentar.

### <a name="unloading-dlls"></a>Como descarregar DLLs

Uma vez que um módulo binário é carregado, você não pode descarregá-lo realmente. O arquivo DLL é bloqueado até que você o descarregue. Isso pode ser irritante durante o desenvolvimento, porque quase toda vez que você quiser compilar uma alteração que tenha feito, o arquivo será bloqueado. A única maneira confiável de resolver isso é fechar a sessão do PowerShell que carregou a DLL.

### <a name="vs-code-reload-window-action"></a>Ação recarregar janela no VS Code

Eu faço a maior parte do meu trabalho de desenvolvimento do PowerShell no [Código do VS][]. Quando estou trabalhando em um módulo binário (ou um módulo com classes), tenho o hábito de recarregar o VS Code toda vez que compilo.
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> abre a janela Comando e `Reload Window` está sempre na parte superior da minha lista.

### <a name="nested-powershell-sessions"></a>Sessões aninhadas do PowerShell

Outra opção é ter uma boa cobertura de teste do Pester. Em seguida, você pode ajustar o script build.ps1 para iniciar uma nova sessão do PowerShell, executar a compilação, executar os testes e fechar a sessão.

### <a name="updating-installed-modules"></a>Como atualizar os módulos instalados

Esse bloqueio pode incomodar ao tentar atualizar o módulo instalado localmente. Caso alguma sessão o tenha carregado, você precisará encontrá-lo e fechá-lo. Isso não é tão problemático ao fazer a instalação de uma PSGallery, porque o controle de versão do módulo coloca o novo módulo em uma pasta diferente.

Você pode configurar uma PSGallery local e publicá-la como parte da compilação. Em seguida, faça a instalação local por meio dessa PSGallery. Isso parece trabalhoso, mas pode ser tão simples quanto iniciar um contêiner do Docker. Eu abordei um jeito de fazer isso em minha postagem [Como usar um servidor NuGet para um PSRepository][].

## <a name="why-binary-modules"></a>Por que módulos binários?

Eu já comecei falando sobre como criar um módulo binário e nem comentei a razão pela qual seria interessante fazê-lo. Na realidade, você está escrevendo em C# e renunciando ao acesso fácil a cmdlets e funções do PowerShell. Esse é o principal motivo pelo qual não mudei para os módulos binários mais cedo.

Mas se você estiver criando um módulo que não dependa de muitos outros comandos do PowerShell, o benefício de desempenho poderá ser significativo. Ao colocar em C#, você consegue suprimir a sobrecarga adicionada pelo PowerShell. O PowerShell foi otimizado para o administrador, não para o computador, e isso adiciona uma pequena sobrecarga.

No trabalho, temos um processo crítico que trabalha muito com JSON e tabelas de hash. Nós otimizamos o PowerShell tanto quanto foi possível, mas esse processo continuou executando por 12 minutos. O módulo já continha muito PowerShell com o estilo do C#. Isso tornou a conversão para um módulo binário limpa e fácil de fazer. Nossa conversão reduziu o processo de mais de 12 minutos para menos de 4 minutos.

### <a name="hybrid-modules"></a>Módulos híbridos

Você pode combinar cmdlet binários com funções avançadas do PowerShell. É exatamente isso que estou fazendo nesse guia. Tudo o que você sabe sobre scripts de módulo será aplicável da mesma maneira.
O arquivo `psm1` vazio que eu criei hoje existe apenas para que você possa soltar outras funções do PowerShell mais tarde.

Quase todos os cmdlets compilados que criamos começaram como uma função do PowerShell antes. Todos os nossos módulos binários são na verdade módulos híbridos.

### <a name="build-scripts"></a>Scripts de build

Eu mantive o script de build simples aqui. Eu geralmente uso um script de `Invoke-Build` grande como parte do meu pipeline de CI/CD. Ele faz maravilhas como executar de testes de Pester, o PSScriptAnalyzer, gerenciar versões e a publicar no PSGallery. Depois que comecei a usar um script de build para os meus módulos, encontrei muitas coisas para adicionar a eles.

## <a name="final-thoughts"></a>Considerações finais

Os módulos binários são fáceis de criar. Eu não mexi na sintaxe do C# para criar um cmdlet, mas há muitas documentações sobre isso no [SDK do Windows PowerShell][]. Definitivamente, é algo que vale a pena tentar como ponto de partida para um nível mais sério do C#.

<!-- link references -->
[versão original]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Biblioteca Padrão do PowerShell]: https://github.com/PowerShell/PowerShellStandard
[Como criar um módulo binário multiplataforma]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[SDK do .NET Core]: https://www.microsoft.com/net/download/core
[Como usar um servidor NuGet para um PSRepository]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[SDK do Windows PowerShell]: /powershell/scripting/developer/windows-powershell-reference
[Código do VS]: https://code.visualstudio.com
[Pacote NuGet]: https://www.nuget.org/packages/PowerShellStandard.Library/
