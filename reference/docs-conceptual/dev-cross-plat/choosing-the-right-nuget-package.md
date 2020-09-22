---
title: Como escolher o pacote NuGet do PowerShell correto para seu projeto .NET
description: Com os pacotes executáveis publicados com cada versão do PowerShell, a equipe do PowerShell também mantém diversos pacotes disponíveis no NuGet. Com esses pacotes, é possível ter o PowerShell como destino como se fosse uma plataforma de API no .NET.
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 39369ed872faa76ad2c41d813da5e0a98cf1c078
ms.sourcegitcommit: d0461273abb6db099c5e784ef00f57fd551be4a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85795242"
---
# <a name="choosing-the-right-powershell-nuget-package-for-your-net-project"></a>Como escolher o pacote NuGet do PowerShell correto para seu projeto .NET

Com os pacotes executáveis `pwsh` publicados com cada versão do PowerShell, a equipe do PowerShell também mantém diversos pacotes disponíveis no [NuGet][]. Com esses pacotes, é possível ter o PowerShell como destino como se fosse uma plataforma de API no .NET.

Como um aplicativo .NET que fornece APIs e espera carregar bibliotecas .NET que implementam suas próprias (módulos binários), é essencial que o PowerShell esteja disponível na forma de um pacote NuGet.

Atualmente, diversos pacotes NuGet fornecem alguma representação da área de superfície da API do PowerShell. Nem sempre fica claro qual pacote usar com um projeto específico. Este artigo esclarece alguns cenários comuns de projetos .NET direcionados ao PowerShell e como escolher o pacote NuGet correto que será o destino de seu projeto .NET orientado ao PowerShell.

## <a name="hosting-vs-referencing"></a>Hospedagem versus referência

Alguns projetos .NET buscam escrever código para ser carregado em um runtime do PowerShell preexistente (como `pwsh`, `powershell.exe`, o Console integrado do PowerShell ou o ISE), enquanto outros querem executar o PowerShell nos próprios aplicativos.

- A **referência** é usada quando um projeto, geralmente um módulo, tem a finalidade de ser carregado no PowerShell.
  Ele deve ser compilado em relação às APIs que o PowerShell fornece para interagir com ele, mas a implementação do PowerShell é fornecida pelo carregamento no processo do PowerShell. Para fazer referência, um projeto pode usar [assemblies de referência][] ou os assemblies de runtime reais como destino de compilação, mas deve garantir que nenhum deles seja pulicado com seu build.
- A **hospedagem** ocorre quando um projeto precisa da própria implementação do PowerShell, geralmente por ser um aplicativo autônomo que precisa executar o PowerShell. Nesse caso, assemblies de referência pura não podem ser usados. Em vez disso, é necessário depender de uma implementação concreta do PowerShell. Como uma implementação concreta do PowerShell deve ser usada, uma versão específica dele deve ser escolhida para hospedagem; um aplicativo host não pode ter como destino várias versões do PowerShell.

### <a name="publishing-projects-that-target-powershell-as-a-reference"></a>Publicando projetos em que o PowerShell é um destino de referência

> [!NOTE]
> Quando usamos o termo **publicar** neste artigo, nos referimos a executar `dotnet publish`, o que coloca uma biblioteca do .NET em um diretório com todas as suas dependências, pronta para implantação em um runtime específico.

Para evitar a publicação de dependências do projeto que estão sendo usadas apenas como destinos de referência de compilação, é recomendável definir o [atributo PrivateAssets][]:

```xml
<PackageReference Include="PowerShellStandard.Library" Version="5.1.0.0" PrivateAssets="all" />
```

Caso se esqueça de fazer isso e use um assembly de referência como destino, você poderá ter problemas relacionados ao uso da implementação padrão do assembly de referência em vez da implementação real. Isso pode assumir a forma de uma `NullReferenceException`, uma vez que os assemblies de referência costumam simular a API de implementação, retornando apenas `null`.

## <a name="key-kinds-of-powershell-targeting-net-projects"></a>Principais tipos de projetos .NET que têm o PowerShell como destino

Embora qualquer aplicativo ou biblioteca do .NET possa inserir o PowerShell, há alguns cenários comuns que usam APIs do PowerShell:

- **Implementar um módulo binário do PowerShell**

  Módulos binários do PowerShell são bibliotecas do .NET carregadas pelo PowerShell que precisam implementar APIs do PowerShell, como os tipos [PSCmdlet][] ou [CmdletProvider][], para expor cmdlets ou provedores, respectivamente. Como são carregados, os módulos buscam compilar em relação a referências ao PowerShell sem publicá-lo em seu build. Também é comum que os módulos queiram dar suporte a várias versões e plataformas do PowerShell, idealmente com um mínimo de sobrecarga de espaço em disco, complexidade ou implementação repetida. Confira [about_Modules][] para obter mais informações sobre módulos.

- **Implementar um Host do PowerShell**

  Um Host do PowerShell fornece uma camada de interação para o runtime do PowerShell. Trata-se de uma forma específica de _hospedagem_, em que um [PSHost][] é implementado como uma nova interface do usuário no PowerShell. Por exemplo, o ConsoleHost do PowerShell fornece uma interface do usuário de terminal para executáveis do PowerShell, enquanto o Host dos Serviços do Editor do PowerShell e o Host do ISE fornecem uma interface parcialmente gráfica do usuário integrada ao editor em torno do PowerShell. Embora seja possível carregar um host em um processo existente do PowerShell, é muito mais comum que uma implementação de host atue como uma implementação autônoma do PowerShell que redistribui o mecanismo do PowerShell.

- **Chamar o PowerShell de outro aplicativo .NET**

  Assim como ocorre com qualquer aplicativo, o PowerShell pode ser chamado como um subprocesso para executar cargas de trabalho. No entanto, como um aplicativo .NET, também é possível invocar o PowerShell em processo para recuperar objetos .NET completos para uso no aplicativo autor da chamada. Essa é uma forma mais geral _hospedagem_, em que o aplicativo mantém a própria implementação do PowerShell para uso interno. Exemplos podem ser um serviço ou daemon que executa o PowerShell para gerenciar o estado do computador ou um aplicativo Web que executa o PowerShell quando solicitado para fazer algo como gerenciar implantações de nuvem.

- **Efetuar o teste de unidade de módulos do PowerShell usando o .NET**

  Embora módulos e outras bibliotecas criadas para expor funcionalidades ao PowerShell devam ser testados principalmente no PowerShell (recomendamos o [Pester][]), às vezes é necessário efetuar o teste de unidade de APIs escritas para um módulo do PowerShell no .NET. Essa situação ocorre quando o código do módulo tenta ter várias versões do PowerShell como destino, enquanto os testes devem executá-lo em implementações concretas específicas.

## <a name="powershell-nuget-packages-at-a-glance"></a>Pacotes NuGet do PowerShell em um relance

Neste artigo, abordaremos os seguintes pacotes NuGet que expõem APIs do PowerShell:

- [PowerShellStandard.Library][], um assembly de referência que habilita a criação de um só assembly que pode ser carregado por vários runtimes do PowerShell.
- [Microsoft.PowerShell.SDK][], a maneira de direcionar e hospedar novamente o SDK do PowerShell completo
- O pacote [System.Management.Automation][], a implementação de mecanismo e runtime principal do PowerShell, que pode ser útil em implementações hospedadas mínimas e em cenários em que o destino é uma versão específica.
- Os **assemblies de referência do Windows PowerShell**, a maneira de direcionar e hospedar novamente, de maneira efetiva, o Windows PowerShell (versões 5.1 e anteriores do PowerShell).

> [!NOTE]
> O pacote [NuGet do PowerShell][] não é um pacote de biblioteca do .NET, ele fornece a implementação da ferramenta dotnet global do PowerShell. Ela não deve ser usada por nenhum projeto, pois fornece apenas um executável.

## <a name="powershellstandardlibrary"></a>PowerShellStandard.Library

A Biblioteca PowerShell Standard é um assembly de referência que captura a interseção das APIs das versões 7, 6 e 5.1 do PowerShell. Isso proporciona uma superfície de API verificada em tempo de compilação com a qual compilar código .NET, permitindo que projetos .NET sejam direcionados às versões 7, 6 e 5.1 do PowerShell sem correr risco de chamar uma API que não estará lá.

O PowerShell Standard tem a finalidade de escrever módulos do PowerShell ou outros códigos que devem ser executados somente depois de serem carregados em um processo do PowerShell. Por ser um assembly de referência, o PowerShell Standard não contém nenhuma implementação e, portanto, não fornece nenhuma funcionalidade para aplicativos autônomos.

### <a name="using-powershell-standard-with-different-net-runtimes"></a>Usando o PowerShell Standard com diferentes runtimes .NET

O PowerShell Standard é direcionado ao runtime de destino [.NET Standard 2.0][], que é um runtime de fachada projetado para fornecer uma área de superfície comum compartilhada pelo .NET Framework e pelo .NET Core. Com isso, é possível ter com destino um só runtime para produzir um só assembly que funcionará com várias versões do PowerShell, mas as seguintes consequências se aplicam:

- O PowerShell que carregará o módulo ou a biblioteca precisa executar, no mínimo, o .NET 4.6.1, uma vez que o .NET 4.6 e o .NET 4.5.2 não dão suporte ao .NET Standard. Observe que uma versão mais nova do Windows PowerShell não implica uma versão mais nova do .NET Framework; o Windows PowerShell 5.1 pode ser executado no .NET 4.5.2.
- Para funcionar com um PowerShell executando o .NET Framework 4.7.1 ou abaixo, a implementação da [NETStandard.Library][] no .NET 4.6.1 precisa fornecer o netstandard.dll e outros assemblies de shim em versões mais antigas do .NET Framework.

O PowerShell 6+ fornece os próprios assemblies de shim para encaminhamento de tipo do .NET Framework 4.6.1 (e acima) para o .NET Core. Isso significa que, desde que um módulo use apenas APIs existentes no .NET Core, o PowerShell 6+ poderá carregá-lo e executá-lo quando tiver sido criado para o .NET Framework 4.6.1 (o destino do runtime `net461`).

Isso significa que módulos binários que usam o PowerShell Standard para ter como destino várias versões do PowerShell com uma só DLL publicada têm duas opções:

1. Publicar um assembly criado para o runtime do `net461` de destino. Isso envolve:
   - Publicar o projeto para o runtime do `net461`
   - Além disso, compilar para o runtime do `netstandard2.0` (sem usar sua saída de build) para garantir que todas as APIs usadas também estejam presentes no .NET Core.

1. Publicar um build de assembly para o runtime do `netstandard2.0` de destino. Isso requer:
   - Publicar o projeto para o runtime do `netstandard2.0`
   - Pegar as dependências de `net461` de NETStandard.Library e copiá-las para o local de publicação do assembly do projeto para que o assembly seja corrigido com o encaminhamento do tipo para o .NET Framework.

Para criar bibliotecas ou módulos do PowerShell direcionados a versões mais antigas do .NET Framework, pode ser preferível direcionar vários runtimes .NET. Isso publicará um assembly para cada runtime de destino, e o assembly correto precisará ser carregado no tempo de carregamento do módulo (por exemplo, com um pequeno psm1 como módulo raiz).

### <a name="testing-powershell-standard-projects-in-net"></a>Testando projetos do PowerShell Standard no .NET

Quando se trata de testar seu módulo em executores de teste do .NET, como o xUnit, lembre-se de que as verificações de tempo de compilação têm limitações. Você precisa testar o módulo com relação às plataformas relevantes do PowerShell.

Para testar APIs criadas com o PowerShell Standard no .NET, adicione `Microsoft.Powershell.SDK` como uma dependência de teste com o .NET Core (com a versão configurada de modo correspondente com a versão desejada do PowerShell) e os assemblies de referência apropriados do Windows PowerShell com o .NET Framework.

Para obter mais informações sobre o PowerShell Standard e como usá-lo para escrever um módulo binário que funciona em várias versões do PowerShell, confira [esta postagem no blog][]. Confira também o [repositório do PowerShell Standard][] no GitHub.

## <a name="microsoftpowershellsdk"></a>Microsoft.PowerShell.SDK

`Microsoft.PowerShell.SDK` é um metapacote que reúne todos os componentes do SDK do PowerShell em um só pacote NuGet. Um aplicativo .NET autossuficiente pode usar o Microsoft.PowerShell.SDK para executar funcionalidades arbitrárias do PowerShell sem depender de nenhuma instalação ou biblioteca externas do PowerShell.

> [!NOTE]
> O SDK do PowerShell se refere apenas a todos os pacotes de componentes que compõem o PowerShell e que podem ser usados para desenvolvimento do .NET com o PowerShell.

Uma determinada versão de `Microsoft.Powershell.SDK` contém a implementação concreta da mesma versão do aplicativo PowerShell; a versão 7.0 contém a implementação do PowerShell 7.0, e a execução de comandos ou scripts com ela se comportará, em grande parte, como a execução no PowerShell 7.0.

Executar comandos do PowerShell no SDK é, na maioria dos casos, mas não em todos, o mesmo que executá-los em `pwsh`. Por exemplo, [Start-Job][] atualmente depende da disponibilidade do executável `pwsh` e, portanto, não funcionará com `Microsoft.Powershell.SDK` por padrão.

Ter `Microsoft.Powershell.SDK` como destino usando um aplicativo .NET permite que você integre com todos os assemblies de implementação do PowerShell, como `System.Management.Automation`, `Microsoft.PowerShell.Management` e outros assemblies de módulo.

Pulicar um aplicativo que tem `Microsoft.Powershell.SDK` como destino incluirá todos esses assemblies e as dependências que o PowerShell exige. Incluirá também outros ativos que o PowerShell exigiu em seu build, como os manifestos de módulo para módulos de `Microsoft.PowerShell.*` e o diretório `ref` exigido por [Add-Type][].

Por ser mais completo, `Microsoft.Powershell.SDK` é mais adequado para:

- Implementação de hosts do PowerShell.
- Teste com xUnit de bibliotecas com assemblies de referência do PowerShell como destino.
- Invocar o PowerShell em processo de um aplicativo .NET.

`Microsoft.PowerShell.SDK` também pode ser usado como um destino de referência quando um projeto .NET tem a finalidade de ser usado como um módulo ou, de alguma forma, ser carregado pelo PowerShell, mas depende de APIs presentes apenas em uma versão específica do PowerShell. Observe que só é seguro carregar e usar um assembly publicado para uma versão específica do `Microsoft.PowerShell.SDK` nessa versão do PowerShell. Para ter como destino várias versões do PowerShell com APIs específicas, vários builds são necessários, cada destinado à própria versão do `Microsoft.Powershell.SDK`.

> [!NOTE]
> O SDK do PowerShell está disponível apenas para o PowerShell versões 6 e superiores. Para fornecer funcionalidades equivalentes com o Windows PowerShell, use os assemblies de referência do Windows PowerShell descritos abaixo.

## <a name="systemmanagementautomation"></a>System.Management.Automation

O pacote `System.Management.Automation` é o coração do SDK do PowerShell. Ele existe no NuGet, principalmente, como um ativo para que `Microsoft.Powershell.SDK` efetue pull. No entanto, ele também pode ser usado diretamente como um pacote para cenários de hospedagem menores e módulos direcionados a versões.

Especificamente, o pacote `System.Management.Automation` pode ser um provedor preferível de funcionalidades do PowerShell quando:

- Você quer usar apenas a funcionalidade de linguagem do PowerShell (no namespace `System.Management.Automation.Language`), como o analisador do PowerShell, o AST e as APIs de visitante do AST (por exemplo, para análise estática do PowerShell).
- Você deseja apenas executar comandos específicos do módulo `Microsoft.PowerShell.Core` e pode executá-los em um estado de sessão criado com o método de fábrica [CreateDefault2][].

Além disso, `System.Management.Automation` é um assembly de referência útil quando:

- Você deseja ter como alvo APIs que estão presentes apenas dentro de uma versão específica do PowerShell
- Você não vai depender de tipos que ocorrem fora do assembly `System.Management.Automation` (por exemplo, tipos exportados por cmdlets em módulos `Microsoft.PowerShell.*`).

## <a name="windows-powershell-reference-assemblies"></a>Assemblies de referência do Windows PowerShell

Para as versões 5.1 e anteriores do PowerShell (Windows PowerShell), não há nenhum SDK para fornecer uma implementação do PowerShell, uma vez que a implementação do Windows PowerShell faz parte do Windows.

Em vez disso, os assemblies de referência do Windows PowerShell fornecem destinos de referência e uma forma de hospedar novamente o Windows PowerShell, atuando da mesma forma que o SDK do PowerShell para as versões 6 e superiores.

Em vez de serem diferenciados pela versão, os assemblies de referência do Windows PowerShell têm um pacote diferente para cada versão do Windows PowerShell:

- [PowerShell 5.1](https://www.nuget.org/packages/Microsoft.PowerShell.5.ReferenceAssemblies/)
- [PowerShell 4](https://www.nuget.org/packages/Microsoft.PowerShell.4.ReferenceAssemblies/)
- [PowerShell 3](https://www.nuget.org/packages/Microsoft.PowerShell.3.ReferenceAssemblies/)

Informações sobre como usar os assemblies de referência do Windows PowerShell podem ser encontradas em [SDK do Windows PowerShell][].

## <a name="real-world-examples-using-these-nuget-packages"></a>Exemplos reais de uso desses pacotes NuGet

Diferentes projetos de ferramentas do PowerShell têm como destino diferentes pacotes NuGet do PowerShell, dependendo de suas necessidades. Veja alguns exemplos notáveis.

### <a name="psreadline"></a>PSReadLine

[PSReadLine][], o módulo do PowerShell que fornece grande parte da experiência de console avançada do PowerShell, usa o PowerShell Standard como uma dependência, e não como uma versão específica do PowerShell, e tem como alvo o runtime do .NET `net461` em seu [csproj][].

O PowerShell 6+ fornece seus próprios assemblies de shim que permitem que uma DLL que tem como alvo o runtime de `net461` "simplesmente funcione" quando carregada (redirecionando a associação a `mscorlib.dll` do .NET Framework para o assembly do .NET Core relevante).

Isso simplifica significativamente o layout e a entrega do módulo de PSReadLine, uma vez que o PowerShell Standard garante que as únicas APIs usadas estejam presentes no PowerShell 5.1 e no PowerShell 6+, enquanto permite também que o módulo seja fornecido com somente um assembly.

No entanto, o destino .NET 4.6.1 significa que o Windows PowerShell em execução no .NET 4.5.2 e no .NET 4.6 não tem suporte.

### <a name="powershell-editor-services"></a>Serviços do Editor do PowerShell

O [PSES (Serviços do Editor do PowerShell)][] é o back-end da [extensão do PowerShell][] para o [Visual Studio Code][] e, na verdade, é uma forma de módulo do PowerShell que é carregada por um executável do PowerShell e, em seguida, assume esse processo para hospedar novamente o PowerShell dentro de si mesmo, enquanto fornece também recursos de Protocolo de Serviço de Linguagem e Adaptador de Depuração.

O PSES fornece destinos de implementação concretos para `netcoreapp2.1` ter como destino o PowerShell 6+ (já que o runtime `netcoreapp3.1` do PowerShell 7 é compatível com versões anteriores) e `net461` ter como destino o Windows PowerShell 5.1, mas mantém a maior parte de sua lógica em um segundo assembly que tem como destino `netstandard2.0` e o PowerShell Standard. Isso permite que ele efetue pull das dependências necessárias para as plataformas .NET Core e .NET Framework, ao mesmo tempo em que simplifica a maior parte da base de código por trás de uma abstração uniforme.

Por ser baseado no PowerShell Standard, o PSES requer uma implementação de runtime do PowerShell para ser testado corretamente. Para fazer isso, os testes de [xUnit do PSES][] efetuam pull de `Microsoft.PowerShell.SDK` e `Microsoft.PowerShell.5.ReferenceAssemblies` para fornecer uma implementação do PowerShell no ambiente de teste.

Assim como ocorre com PSReadLine, o PSES não dá suporte ao .NET 4.6 e versões anteriores, mas [executa uma verificação][] no runtime antes de chamar qualquer uma das APIs que poderiam causar falha nos runtimes anteriores do .NET Framework.

### <a name="psscriptanalyzer"></a>PSScriptAnalyzer

[PSScriptAnalyzer][], o linter do PowerShell, deve ter como destino elementos sintáticos introduzidos apenas em determinadas versões do PowerShell. Como o reconhecimento desses elementos sintáticos é realizado implementando um [AstVisitor2][], não é possível usar o PowerShellStandard e também implementar os métodos de visitante do AST para sintaxes mais recentes do PowerShell.

Em vez disso, PSScriptAnalyzer [tem como destino cada versão do PowerShell][] como uma configuração de build e produz uma DLL separada para cada uma delas. Isso aumenta o tamanho e a complexidade do build, mas permite:

- Testes de APIs específicas da versão
- A implementação de funcionalidades específicas da versão basicamente sem custo de runtime
- Suporte total para o Windows PowerShell até o .NET Framework 4.5.2

## <a name="summary"></a>Resumo

Neste artigo, listamos e falamos sobre os pacotes do NuGet disponíveis como destino ao implementar um projeto do .NET que usa o PowerShell, bem como sobre os motivos que você pode ter para usar um em vez do outro.

Se você veio direto para o resumo, algumas recomendações gerais são:

- Os **módulos** do PowerShell deverão ser compilados com o PowerShell Standard se exigirem apenas APIs comuns a versões diferentes do PowerShell.
- **Hosts e aplicativos** do PowerShell que precisam executar o PowerShell internamente devem ter como destino o SDK do PowerShell para o PowerShell 6+ ou os assemblies de referência relevantes do Windows PowerShell para o Windows PowerShell.
- Os módulos do PowerShell que precisam de **APIs específicas da versão** devem ter como destino os assemblies de referência do SDK do PowerShell ou do Windows PowerShell para as versões necessárias do PowerShell, usando-os como assemblies de referência (ou seja, sem publicar as dependências do PowerShell).

<!--link references -->

[.NET Standard 2.0]: /dotnet/standard/net-standard
[about_Modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[Add-Type]: /powershell/module/microsoft.powershell.utility/add-type
[AstVisitor2]: /dotnet/api/system.management.automation.language.astvisitor2
[CmdletProvider]: /dotnet/api/system.management.automation.provider.cmdletprovider
[CreateDefault2]: /dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2
[csproj]: https://github.com/PowerShell/PSReadLine/blob/master/PSReadLine/PSReadLine.csproj
[Microsoft.PowerShell.SDK]: https://www.nuget.org/packages/Microsoft.PowerShell.SDK/
[NETStandard.Library]: https://www.nuget.org/packages/NETStandard.Library/
[NuGet]: https://www.nuget.org/
[executa uma verificação]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/src/PowerShellEditorServices.Hosting/EditorServicesLoader.cs#L231-L251
[Pester]: https://github.com/Pester/Pester
[Serviços do Editor do PowerShell]: https://github.com/PowerShell/PowerShellEditorServices/
[Extensão do PowerShell]: https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[NuGet do PowerShell]: https://www.nuget.org/packages/PowerShell/
[Repositório do PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[PowerShellStandard.Library]: https://www.nuget.org/packages/PowerShellStandard.Library/
[PSCmdlet]: /dotnet/api/system.management.automation.pscmdlet
[XUnit do PSES]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/test/PowerShellEditorServices.Test/PowerShellEditorServices.Test.csproj#L15-L20
[PSHost]: /dotnet/api/system.management.automation.host.pshost
[Atributo PrivateAssets]: /dotnet/core/tools/csproj#packagereference
[PSReadLine]: https://github.com/PowerShell/PSReadLine
[PSScriptAnalyzer]: https://github.com/powershell/psscriptanalyzer
[assemblies de referência]: https://github.com/dotnet/standard/blob/master/docs/history/evolution-of-design-time-assemblies.md#definitions
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[System.Management.Automation]: https://www.nuget.org/packages/System.Management.Automation/
[tem como destino cada versão do PowerShell]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/Engine/Engine.csproj
[esta postagem no blog]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
[Visual Studio Code]: https://code.visualstudio.com/
[SDK do Windows PowerShell]: /powershell/scripting/developer/windows-powershell
