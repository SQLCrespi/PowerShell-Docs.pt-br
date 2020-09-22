---
title: Como resolver conflitos de dependência de assembly de módulo do PowerShell
description: Ao escrever um módulo do PowerShell binário em C#, é natural assumir dependências de outros pacotes ou bibliotecas para fornecer funcionalidade.
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 536bcfd1ced536faccde0d6c5bc483cdaf31ce68
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87775176"
---
# <a name="resolving-powershell-module-assembly-dependency-conflicts"></a>Como resolver conflitos de dependência de assembly de módulo do PowerShell

Ao escrever um módulo do PowerShell binário em C#, é natural assumir dependências de outros pacotes ou bibliotecas para fornecer funcionalidade. A obtenção de dependências em outras bibliotecas é desejável para reutilização de código. O PowerShell sempre carrega assemblies no mesmo contexto. Isso apresenta problemas quando as dependências de um módulo entram em conflito com DLLs já carregadas e podem impedir o uso de dois módulos não relacionados na mesma sessão do PowerShell.

Se você teve esse problema, você viu uma mensagem de erro como esta:

![Mensagem de erro de conflito de carregamento de assembly](./media/resolving-dependency-conflicts/moduleconflict.png)

Este artigo analisa algumas das maneiras como os conflitos de dependência ocorrem no PowerShell e como mitigar problemas de conflito de dependência. Mesmo que você não seja um autor do módulo, há alguns truques que podem ser úteis com conflitos de dependência que ocorrem em módulos que você usa.

## <a name="why-do-dependency-conflicts-occur"></a>Por que conflitos de dependência ocorrem?

No .NET, os conflitos de dependência ocorrem quando duas versões do mesmo assembly são carregadas no mesmo _Contexto de Carregamento do Assembly_. Esse termo tem significados ligeiramente diferentes em diferentes plataformas .NET, o que é explicado [mais tarde](#powershell-and-net). Esse conflito é um problema comum que ocorre em qualquer software no qual as dependências com controle de versão são usadas. Como não há soluções simples e como muitas estruturas de resolução de dependências tentam resolver o problema de diferentes maneiras, essa situação costuma ser chamada de "inferno de dependências".

Os problemas de conflito ocorrem porque um projeto quase nunca deliberadamente ou diretamente depende de duas versões da mesma dependência. Em vez disso, o projeto tem duas ou mais dependências que exigem uma versão diferente da mesma dependência.

Por exemplo, digamos que o seu aplicativo .NET, `DuckBuilder`, traga duas dependências para executar partes da funcionalidade dele e que isso seja semelhante ao seguinte:

![Duas dependências de DuckBuilder dependem de versões diferentes do Newtonsoft.Json](./media/resolving-dependency-conflicts/dep-conflict.jpg)

Como `Contoso.ZipTools` e `Fabrikam.FileHelpers` dependem de versões diferentes do `Newtonsoft.Json`, pode haver um conflito de dependência dependendo de como cada dependência é carregada.

### <a name="conflicting-with-powershells-dependencies"></a>Conflito com as dependências do PowerShell

No PowerShell, o problema de conflito de dependência é ampliado porque os módulos do PowerShell e as dependências do PowerShell são carregados no mesmo contexto compartilhado. Isso significa que o mecanismo do PowerShell e todos os módulos do PowerShell carregados não podem ter dependências conflitantes. Um exemplo clássico disso é `Newtonsoft.Json`:

![O módulo FictionalTools depende da versão mais recente do Newtonsoft.Json do que o PowerShell](./media/resolving-dependency-conflicts/engine-conflict.jpg)

Neste exemplo, o módulo `FictionalTools` depende do `Newtonsoft.Json` versão `12.0.3`, que é uma versão mais recente de `Newtonsoft.Json` do que a `11.0.2` fornecida no PowerShell de exemplo.

> [!NOTE]
> Este é um exemplo e, no momento, o PowerShell 7 é fornecido com `Newtonsoft.Json 12.0.3`.

Como o módulo depende de uma versão mais recente do assembly, ele não aceitará a versão que o PowerShell já carregou. Mas, como o PowerShell já carregou uma versão do assembly, o módulo não pode carregar a própria versão usando o mecanismo de carregamento convencional.

### <a name="conflicting-with-another-modules-dependencies"></a>Conflito com as dependências de outro módulo

Outro cenário comum no PowerShell é que um módulo que depende de uma versão de um assembly é carregado e outro módulo que depende de uma versão diferente desse assembly é carregado mais tarde.

Isso frequentemente se parece com o seguinte:

![Dois módulos do PowerShell exigem versões diferentes da dependência Microsoft.Extensions.Logging](./media/resolving-dependency-conflicts/mod-conflict.jpg)

Nesse caso, o módulo `FictionalTools` requer uma versão mais recente de `Microsoft.Extensions.Logging` do que o módulo `FilesystemManager`.

Imagine que esses módulos carregam as dependências deles colocando os assemblies de dependência no mesmo diretório que o assembly do módulo raiz. Isso permite que o .NET carregue-os implicitamente por nome. Se estivermos executando o PowerShell 7 (além do .NET Core 3.1), poderemos carregar e executar o `FictionalTools` e, em seguida, carregar e executar o `FilesystemManager` sem problemas. No entanto, em uma nova sessão, se carregarmos e executarmos o `FilesystemManager` e, em seguida, carregarmos o `FictionalTools`, obteremos um `FileLoadException` do comando `FictionalTools` porque ele requer uma versão mais recente de `Microsoft.Extensions.Logging` do que a carregada.
O `FictionalTools` não consegue carregar a versão necessária porque um assembly de mesmo nome já foi carregado.

## <a name="powershell-and-net"></a>PowerShell e .NET

O PowerShell é executado na plataforma .NET. O NET e é, em última instância, responsável por resolver e carregar dependências de assembly. Portanto, precisamos entender como o .NET opera aqui para entender os conflitos de dependência.

Também precisamos ter em mente que diferentes versões do PowerShell são executadas em diferentes implementações do .NET. Em geral, o PowerShell 5.1 e versões anteriores são executados no .NET Framework, enquanto o PowerShell 6 e versões posteriores são executados no .NET Core. Essas duas implementações do .NET carregam e administram assemblies de modo diferente.
Isso significa que a resolução de conflitos de dependência pode variar dependendo da plataforma .NET subjacente.

### <a name="assembly-load-contexts"></a>Contextos de carregamento de assembly

No .NET, um _ALC_ (Contexto de Carregamento de Assembly) que é um namespace do runtime no qual os assemblies são carregados. Os nomes dos assemblies precisam ser exclusivos. Esse conceito permite que os assemblies sejam resolvidos exclusivamente pelo nome em cada ALC.

### <a name="assembly-reference-loading-in-net"></a>Carregamento de referência de assembly no .NET

A semântica do carregamento do assembly depende da implementação do .NET (.NET Core vs .NET Framework) e da API do .NET usada para carregar um determinado assembly. Em vez de entrar em detalhes aqui, há links na seção [Leitura adicional](#further-reading) que se aprofundam sobre como o carregamento do assembly do .NET funciona em cada implementação do .NET.

Neste artigo, vamos nos referir aos seguintes mecanismos:

- Carregamento de assembly implícito (efetivamente `Assembly.Load(AssemblyName)`), que ocorre quando o .NET tenta, implicitamente, carregar um assembly por nome usando uma referência de assembly estática no código .NET.
- `Assembly.LoadFrom()`, uma API de carregamento orientada por plug-in que adiciona manipuladores para resolver as dependências da DLL carregada. Esse método pode não resolver dependências da maneira que desejamos.
- `Assembly.LoadFile()`, uma API de carregamento básica destinada a carregar apenas o assembly solicitado e que não trata de nenhuma dependência.

### <a name="differences-in-net-framework-vs-net-core"></a>Diferenças entre o .NET Framework e o .NET Core

A maneira como essas APIs funcionam passou por mudanças sutis entre o .NET Core e o .NET Framework, portanto, vale a pena ler os [links](#further-reading) incluídos. Importante: os Contextos de Carregamento de Assembly e outros mecanismos de resolução de assembly foram alterados entre o .NET Framework e o .NET Core.

Em particular, o .NET Framework tem os seguintes recursos:

- O Cache de Assembly Global, para resolução de assembly em todo o computador
- Domínios do Aplicativo, que funcionam como áreas restritas em processo para isolamento de assembly, mas também apresentam uma camada de serialização com a qual lidar
- Um modelo de contexto de carregamento de assembly limitado, explicado em detalhes [aqui](/dotnet/framework/deployment/best-practices-for-assembly-loading), que tem um conjunto fixo de contextos de carregamento de assembly, cada um com o próprio comportamento:
  - O contexto de carregamento padrão, em que os assemblies são carregados por padrão
  - O contexto de origem de carregamento, para carregar assemblies manualmente no runtime
  - O contexto somente para reflexão, usado para carregar assemblies com segurança a fim de ler os metadados sem executá-los
  - O valor nulo misterioso nos quais os assemblies carregados com `Assembly.LoadFile(string path)` e `Assembly.Load(byte[] asmBytes)` residem

O .NET Core (e o .NET 5+) substituiu essa complexidade por um modelo mais simples:

- Nenhum Cache de Assembly Global. Os aplicativos trazem todas as próprias dependências. Isso remove um fator externo para a resolução de dependência em aplicativos, tornando-a mais reproduzível.
  O PowerShell, como o host do plug-in, torna isso um pouco mais complicado nos módulos. As dependências dele no `$PSHOME` são compartilhadas com todos os módulos.
- Apenas um Domínio do Aplicativo e nenhuma capacidade de criar outros. O conceito de Domínio do Aplicativo é mantido no .NET Core apenas para ser o estado global do processo do .NET.
- Um novo modelo de Contexto de Carregamento de Assembly extensível. A resolução de assembly pode ser armazenada em namespace colocando-a em um novo ALC. Os processos do .NET Core começam com um único ALC padrão no qual todos os assemblies são carregados. (exceto aqueles carregados com `Assembly.LoadFile(string)` e `Assembly.Load(byte[])`). Entretanto, o processo pode criar e definir os próprios ALCs personalizados com a própria lógica de carregamento. Quando um assembly for carregado, o primeiro ALC no qual ele é carregado será responsável por resolver as dependências dele. Isso cria oportunidades para implementar mecanismos avançados de carregamento de plug-in do .NET.

Em ambas as implementações, os assemblies são carregados lentamente. Isso significa que eles serão carregados quando um método que exige o tipo for executado pela primeira vez.

Por exemplo, a seguir estão duas versões do mesmo código que carregam uma dependência em momentos diferentes.

A primeira sempre carrega a dependência dela quando `Program.GetRange()` é chamado, porque a referência de dependência está presente em forma lexical no método:

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetRange(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library will be loaded when GetRange is run
                // because the dependency call occurs directly within the method
                DependencyApi.Use();
            }

            list.Add(i);
        }
        return list;
    }
}
```

A segunda carregará a dependência somente se o parâmetro `limit` for 20 ou mais, devido à indireção interna por meio de um método:

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetNumbers(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library is only referenced within
                // the UseDependencyApi() method,
                // so will only be loaded when limit >= 20
                UseDependencyApi();
            }

            list.Add(i);
        }
        return list;
    }

    private static void UseDependencyApi()
    {
        // Once UseDependencyApi() is called, Dependency.Library is loaded
        DependencyApi.Use();
    }
}
```

Essa é uma prática recomendada, pois minimiza a memória e a E/S do sistema de arquivos, além de usar os recursos com mais eficiência. Um efeito colateral indesejado disso é que não sabemos se o assembly teve uma falha ao ser carregado até chegarmos ao caminho do código que tenta carregar o assembly.

Isso também pode criar uma condição de tempo para conflitos de carregamento de assembly. Se duas partes do mesmo programa tentarem carregar versões diferentes do mesmo assembly, a versão carregada dependerá de qual caminho do código foi executado primeiro.

Para o PowerShell, isso significa que os seguintes fatores podem afetar um conflito de carregamento de assembly:

- Qual módulo foi carregado primeiro?
- O caminho do código que usa a biblioteca de dependências foi executado?
- O PowerShell carrega uma dependência conflitante na inicialização ou somente em determinados caminhos do código?

## <a name="quick-fixes-and-their-limitations"></a>Correções rápidas e limitações

Em alguns casos, é possível fazer pequenos ajustes no seu módulo e consertar problemas com o mínimo de esforço. Mas essas soluções tendem a surgir com ressalvas. Embora elas possam se aplicar ao seu módulo, elas não funcionam em todos os módulos.

### <a name="change-your-dependency-version"></a>Alterar a sua versão de dependência

A maneira mais simples de evitar conflitos de dependência é concordar com uma dependência. Isso pode ser possível quando:

- O seu conflito ocorre com uma dependência direta do módulo e você controla a versão.
- O seu conflito ocorre com uma dependência indireta, mas você pode configurar as dependências diretas para usar uma versão de dependência indireta viável.
- Você sabe a versão conflitante e pode confiar que ela não mudará.

O pacote `Newtonsoft.Json` é um bom exemplo desse último cenário. Ele é uma dependência do PowerShell 6 e versões posteriores e não é usado no Windows PowerShell. Isso significa que uma forma simples de resolver conflitos de controle de versão é direcionar a versão mais antiga do `Newtonsoft.Json` nas versões do PowerShell que você deseja direcionar.

Por exemplo, o PowerShell 6.2.6 e o PowerShell 7.0.2 atualmente usam o `Newtonsoft.Json` versão 12.0.3. Portanto, para criar um módulo que seja direcionado ao Windows PowerShell, ao PowerShell 6 e ao PowerShell 7, você deve direcionar `Newtonsoft.Json 12.0.3` como uma dependência e incluí-lo no seu módulo criado. Quando o módulo for carregado no PowerShell 6 ou 7, o assembly `Newtonsoft.Json` próprio do PowerShell já estará carregado. Além disso, ele terá no mínimo a versão necessária para o seu módulo, portanto a resolução será bem sucedida. No Windows PowerShell, o assembly ainda não está presente no PowerShell. Portanto, em vez disso, ele será carregado da sua pasta de módulo.

Geralmente, ao direcionar um pacote do PowerShell concreto, como `Microsoft.PowerShell.Sdk` ou `System.Management.Automation`, o NuGet deve ser capaz de resolver as versões de dependência corretas necessárias. Direcionar tanto o Windows PowerShell quanto o PowerShell 6+ se torna mais difícil, pois você precisa escolher entre direcionar várias estruturas ou o `PowerShellStandard.Library`.

As circunstâncias em que anexar uma versão de dependência comum não funciona incluem:

- O conflito ocorre com uma dependência indireta e nenhuma das suas dependências pode ser configurada para usar uma versão comum.
- A outra versão de dependência provavelmente será alterada com frequência, portanto, escolher uma versão comum é apenas um conserto (fix) de curto prazo.

### <a name="add-an-assemblyresolve-event-handler-to-create-a-dynamic-binding-redirect"></a>Adicionar um manipulador de eventos AssemblyResolve para criar um redirecionamento de associação dinâmica

Às vezes, alterar a própria versão de dependência não é possível ou é muito difícil. Outra opção é configurar um redirecionamento de associação dinâmica registrando um manipulador de eventos para o evento `AssemblyResolve`.

Assim como em um redirecionamento de associação estático, o objetivo é forçar todos os consumidores de uma dependência a usar o mesmo assembly real. Você intercepta as chamadas para carregar a dependência e sempre as redireciona para a versão desejada.

Você obterá algo semelhante isto:

```csharp
// Register the event handler as early as you can in your code.
// A good option is to use the IModuleAssemblyInitializer interface
// that PowerShell provides to run code early on when your module is loaded.

// This class will be instantiated on module import and the OnImport() method run.
// Make sure that:
//  - the class is public
//  - the class has a public, parameterless constructor
//  - the class implements IModuleAssemblyInitializer
public class MyModuleInitializer : IModuleAssemblyInitializer
{
    public void OnImport()
    {
        AppDomain.CurrentDomain.AssemblyResolve += DependencyResolution.ResolveNewtonsoftJson;
    }
}

// Clean up the event handler when the the module is removed
// to prevent memory leaks.
//
// Like IModuleAssemblyInitializer, IModuleAssemblyCleanup allows
// you to register code to run when a module is removed (with Remove-Module).
// Make sure it is also public with a public parameterless contructor
// and implements IModuleAssemblyCleanup.
public class MyModuleCleanup : IModuleAssemblyCleanup
{
    public void OnRemove()
    {
        AppDomain.CurrentDomain.AssemblyResolve -= DependencyResolution.ResolveNewtonsoftJson;
    }
}

internal static class DependencyResolution
{
    private static readonly string s_modulePath = Path.GetDirectoryName(
        Assembly.GetExecutingAssembly().Location);

    public static Assembly ResolveNewtonsoftJson(object sender, ResolveEventArgs args)
    {
        // Parse the assembly name
        var assemblyName = new AssemblyName(args.Name);

        // We only want to handle the dependency we care about.
        // In this example it's Newtonsoft.Json.
        if (!assemblyName.Name.Equals("Newtonsoft.Json"))
        {
            return null;
        }

        // Generally the version of the dependency you want to load is the higher one,
        // since it's the most likely to be compatible with all dependent assemblies.
        // The logic here assumes our module always has the version we want to load.
        // Also note the use of Assembly.LoadFrom() here rather than Assembly.LoadFile().
        return Assembly.LoadFrom(Path.Combine(s_modulePath, "Newtonsoft.Json.dll"));
    }
}
```

Tecnicamente, você pode registrar um scriptblock no PowerShell para administrar um evento `AssemblyResolve`, mas:

- Um evento `AssemblyResolve` pode ser disparado em qualquer thread. Isso é algo que o PowerShell não poderá administrar.
- Mesmo quando os eventos são administrados no thread correto, os conceitos de escopo do PowerShell significam que o scriptblock do manipulador de eventos precisa ser escrito com cuidado para não depender de variáveis definidas fora dele.

Há situações em que o redirecionamento para uma versão comum não funcionará:

- Quando a dependência fez alterações da falha entre as versões ou quando o código dependente precisa de uma funcionalidade que não está disponível na versão para a qual ela será redirecionada.
- Quando o seu módulo não é carregado antes da dependência conflitante. Se você registrar um manipulador de eventos `AssemblyResolve` depois que a dependência tiver sido carregada, ela nunca será acionada. Se você está tentando evitar conflitos de dependência com outro módulo, isso pode ser um problema, já que o outro módulo pode ser carregado primeiro.

### <a name="use-the-dependency-out-of-process"></a>Usar a dependência fora do processo

Essa solução é direcionada especialmente para os usuários de módulo, em vez dos autores de módulo. Essa é uma solução a ser usada quando confrontada com um módulo que não funcionará devido a um conflito de dependência existente.

Os conflitos de dependência ocorrem porque duas versões do mesmo assembly são carregadas no mesmo processo do .NET. Uma solução simples é carregá-las em processos diferentes, desde que você ainda possa usar a funcionalidade de ambos juntos.

No PowerShell, há várias maneiras de conseguir isso:

- Invocar o PowerShell como um subprocesso

  Uma forma simples de executar um comando do PowerShell fora do processo atual é simplesmente iniciar um novo processo do PowerShell diretamente na chamada de comando:

  ```powershell
  pwsh -c 'Invoke-ConflictingCommand'
  ```

  A principal limitação aqui é que a reestruturação do resultado pode ser mais complicada ou mais propensa a erros do que outras opções.

- O sistema de trabalho do PowerShell

  O sistema de trabalho do PowerShell também executa comandos fora do processo, enviando comandos para um novo processo do PowerShell e retornando os resultados:

  ```powershell
  $result = Start-Job { Invoke-ConflictingCommand } | Receive-Job -Wait
  ```

  Nesse caso, você só precisa ter certeza de que todas as variáveis e estados sejam passados corretamente.

  O sistema de trabalho também pode ser um pouco complicado ao executar comandos pequenos.

- Comunicação remota do PowerShell

  Quando estiver disponível, a comunicação remota do PowerShell poderá ser uma forma útil de executar comandos fora do processo. Com a comunicação remota, você pode criar uma **PSSession** em um novo processo, chamar os comandos dela por meio da comunicação remota do PowerShell e, em seguida, usar os resultados localmente com os outros módulos que contêm as dependências conflitantes.

  Veja o exemplo de como seria essa aparência:

  ```powershell
  # Create a local PowerShell session
  # where the module with conflicting assemblies will be loaded
  $s = New-PSSession

  # Import the module with the conflicting dependency via remoting,
  # exposing the commands locally
  Import-Module -PSSession $s -Name ConflictingModule

  # Run a command from the module with the conflicting dependencies
  Invoke-ConflictingCommand
  ```

- Comunicação remota implícita com o Windows PowerShell

  Outra opção no PowerShell 7 é usar o sinalizador `-UseWindowsPowerShell` no `Import-Module`. Isso importará o módulo por meio de uma sessão de comunicação remota local no Windows PowerShell:

  ```powershell
  Import-Module -Name ConflictingModule -UseWindowsPowerShell
  ```

  Lembre-se de que os módulos podem não funcionar com o Windows PowerShell ou funcionar de maneira diferente.

#### <a name="when-out-of-process-invocation-should-not-be-used"></a>Quando a invocação fora do processo não deve ser usada

Como um autor de módulo, é difícil fazer o bake de uma invocação de comando fora do processo em um módulo e alguns casos de borda podem causar problemas. Em especial, a comunicação remota e os trabalhos podem não estar disponíveis em todos os ambientes nos quais o módulo precisa funcionar. No entanto, o princípio geral de mover a implementação para fora do processo e permitir que o módulo do PowerShell seja um cliente mais fino ainda pode ser aplicável.

Como um usuário de módulo, há casos em que a invocação fora do processo não funcionará:

- Quando a comunicação remota do PowerShell estiver indisponível porque você não tem privilégios para usá-la ou ela não estiver habilitada.
- Quando um tipo de .NET específico for necessário na saída como uma entrada para um método ou outro comando.
  Os comandos em execução na comunicação remota do PowerShell emitem objetos desserializados em vez de objetos .NET fortemente tipados. Isso significa que as chamadas de método e APIs fortemente tipadas não funcionam com a saída de comandos importados pela comunicação remota.

## <a name="more-robust-solutions"></a>Soluções mais robustas

Todas as soluções anteriores tinham cenários e módulos que não funcionam. No entanto, elas também tinham a vantagem de serem relativamente simples de implementar corretamente. As soluções a seguir são mais robustas, mas exigem mais esforço para serem implementadas corretamente e poderão causar bugs sutis se não forem escritas com cuidado.

### <a name="loading-through-net-core-assembly-load-contexts"></a>Carregamento por meio de Contextos de Carregamento de Assembly do .NET Core

Os [ALCs](/dotnet/api/system.runtime.loader.assemblyloadcontext) (Contextos de Carregamento de Assembly) como uma API implementável foram introduzidos no .NET Core 1.0 para resolver especificamente a necessidade de carregar várias versões do mesmo assembly no mesmo runtime.

No .NET Core e no .NET 5, eles oferecem a solução mais robusta para o problema de carregar versões conflitantes de um assembly. No entanto, os ALCs personalizados não estão disponíveis no .NET Framework. Isso significa que essa solução só funciona no PowerShell 6 e versões posteriores.

Atualmente, o melhor exemplo de uso de um ALC para isolamento de dependência no PowerShell está nos Serviços do Editor do PowerShell, no servidor de idioma da extensão do PowerShell para Visual Studio Code. Um [ALC é usado](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs) para impedir que as próprias dependências dos Serviços do Editor do PowerShell entrem em conflito com aquelas nos módulos do PowerShell.

A implementação do isolamento de dependência de módulo com um ALC é conceitualmente difícil, mas vamos trabalhar com um exemplo simples. Imagine que temos um módulo simples que se destina apenas a funcionar no PowerShell 7.
O código-fonte é organizado da seguinte maneira:

```
+ AlcModule.psd1
+ src/
    + TestAlcModuleCommand.cs
    + AlcModule.csproj
```

A implementação do cmdlet se parece com esta:

```csharp
using Shared.Dependency;

namespace AlcModule
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            // Here's where our dependency gets used
            Dependency.Use();
            // Something trivial to make our cmdlet do *something*
            WriteObject("done!");
        }
    }
}
```

O manifesto (muito simplificado), tem a seguinte aparência:

```powershell
@{
    Author = 'Me'
    ModuleVersion = '0.0.1'
    RootModule = 'AlcModule.dll'
    CmdletsToExport = @('Test-AlcModule')
    PowerShellVersion = '7.0'
}
```

E o `csproj` tem esta aparência:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

Quando criamos esse módulo, a saída gerada tem o seguinte layout:

```
AlcModule/
  + AlcModule.psd1
  + AlcModule.dll
  + Shared.Dependency.dll
```

Neste exemplo, nosso problema está no assembly `Shared.Dependency.dll`, que é a nossa dependência conflitante imaginária. Essa é a dependência que precisamos ignorar em um ALC para que possamos usar a versão específica do módulo.

Precisamos refazer a engenharia do módulo para que:

- As dependências do módulo sejam carregadas apenas no nosso ALC personalizado e não no ALC do PowerShell. Portanto, não pode haver nenhum conflito. Além disso, à medida que adicionamos mais dependências ao nosso projeto, não é desejável adicionar mais código continuamente para continuar carregando o trabalho. Em vez disso, queremos uma lógica de resolução de dependência genérica e reutilizável.
- Carregar o módulo ainda funciona normalmente no PowerShell. Os cmdlets e outros tipos que o sistema de módulo do PowerShell precisa são definidos no ALC do PowerShell.

Para mediar esses dois requisitos, precisamos dividir nosso módulo em dois assemblies:

- Um assembly de cmdlets, `AlcModule.Cmdlets.dll`, que contém definições de todos os tipos que o sistema de módulo do PowerShell precisa para carregar o nosso módulo corretamente. Ou seja, todas as implementações da classe base `Cmdlet` e da classe que implementa `IModuleAssemblyInitializer`, que configuram o manipulador de eventos do `AssemblyLoadContext.Default.Resolving` para carregar corretamente o `AlcModule.Engine.dll` por meio de nosso ALC personalizado. Como o PowerShell 7 oculta deliberadamente os tipos definidos em assemblies carregados em outros ALCs, todos os tipos que devem ser expostos publicamente no PowerShell também precisam ser definidos aqui. Por fim, a nossa definição de ALC personalizada precisa ser definida nesse assembly. Além disso, o mínimo de código possível deve residir nesse assembly.
- Um assembly de mecanismo, `AlcModule.Engine.dll`, que administra a implementação real do módulo.
  Os tipos dele estão disponíveis no ALC do PowerShell, mas inicialmente serão carregados por meio do nosso ALC personalizado. As dependências são carregadas somente no ALC personalizado. Na prática, isso se torna uma _ponte_ entre os dois ALCs.

Usando esse conceito de ponte, a nossa nova situação de assembly tem a seguinte aparência:

![Diagrama que representa o AlcModule.Engine.dll realizando a ponte entre os dois ALCs](./media/resolving-dependency-conflicts/alc-diagram.jpg)

Para garantir que a lógica de investigação de dependência do ALC padrão não resolva as dependências a serem carregadas no ALC personalizado, precisamos separar essas duas partes do módulo em diretórios diferentes. O novo layout de módulo tem a seguinte estrutura:

```
AlcModule/
  AlcModule.Cmdlets.dll
  AlcModule.psd1
  Dependencies/
  | + AlcModule.Engine.dll
  | + Shared.Dependency.dll
```

Para ver como a implementação muda, começaremos com a implementação do `AlcModule.Engine.dll`:

```csharp
using Shared.Dependency;

namespace AlcModule.Engine
{
    public class AlcEngine
    {
        public static void Use()
        {
            Dependency.Use();
        }
    }
}
```

Esse é um contêiner simples da dependência, `Shared.Dependency.dll`, mas você deve considerá-lo como a API do .NET da sua funcionalidade que os cmdlets no outro assembly encapsulam para o PowerShell.

O cmdlet em `AlcModule.Cmdlets.dll` tem a seguinte aparência:

```csharp
// Reference our module's Engine implementation here
using AlcModule.Engine;

namespace AlcModule.Cmdlets
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            AlcEngine.Use();
            WriteObject("done!");
        }
    }
}
```

Neste ponto, se carregássemos o **AlcModule** e executássemos o `Test-AlcModule`, obteríamos um `FileNotFoundException` quando o ALC padrão tentasse carregar o `Alc.Engine.dll` para executar o `EndProcessing()`. Isso é bom, pois significa que o ALC padrão não conseguiu localizar as dependências que queríamos ocultar.

Agora, precisamos adicionar o código ao `AlcModule.Cmdlets.dll` para que ele saiba como resolver o `AlcModule.Engine.dll`. Primeiro, precisamos definir nosso ALC personalizado que resolverá assemblies do diretório `Dependencies` do módulo:

```csharp
namespace AlcModule.Cmdlets
{
    internal class AlcModuleAssemblyLoadContext : AssemblyLoadContext
    {
        private readonly string _dependencyDirPath;

        public AlcModuleAssemblyLoadContext(string dependencyDirPath)
        {
            _depdendencyDirPath = dependencyDirPath;
        }

        protected override Assembly Load(AssemblyName assemblyName)
        {
            // We do the simple logic here of
            // looking for an assembly of the given name
            // in the configured dependency directory
            string assemblyPath = Path.Combine(
                s_dependencyDirPath,
                $"{assemblyName.Name}.dll");

            // The ALC must use inherited methods to load assemblies
            // Assembly.Load*() won't work here
            return LoadFromAssemblyPath(assemblyPath);
        }
    }
}
```

Em seguida, precisamos conectar o ALC personalizado ao evento `Resolving` do ALC padrão, que é a versão do ALC do evento `AssemblyResolve` nos Domínios do Aplicativo. Esse evento será acionado para localizar o `AlcModule.Engine.dll` quando o `EndProcessing()` for chamado.

```csharp
namespace AlcModule.Cmdlets
{
    public class AlcModuleResolveEventHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // Get the path of the dependency directory.
        // In this case we find it relative to the AlcModule.Cmdlets.dll location
        private static readonly string s_dependencyDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        private static readonly AlcModuleAssemblyLoadContext s_dependencyAlc = new AlcModuleAssemblyLoadContext(s_dependencyDirPath);

        public void OnImport()
        {
            // Add the Resolving event handler here
            AssemblyLoadContext.Default.Resolving += ResolveAlcEngine;
        }

        public void OnRemove()
        {
          // Remove the Resolving event handler here
          AssemblyLoadContext.Default.Resolving -= ResolveAlcEngine;
        }

        private static Assembly ResolveAlcEngine(
            AssemblyLoadContext defaultAlc,
            AssemblyName assemblyToResolve)
        {
            // We only want to resolve the Alc.Engine.dll assembly here.
            // Because this will be loaded into the custom ALC,
            // all of *its* dependencies will be resolved
            // by the logic we defined for that ALC's implementation.
            //
            // Note that we are safe in our assumption that the name is enough
            // to distinguish our assembly here,
            // since it's unique to our module.
            // There should be no other AlcModule.Engine.dll on the system.
            if (!assemblyToResolve.Name.Equals("AlcModule.Engine"))
            {
                return null;
            }

            // Allow our ALC to handle the directory discovery concept
            //
            // This is where Alc.Engine.dll is loaded into our custom ALC
            // and then passed through into PowerShell's ALC,
            // becoming the bridge between both
            return s_dependencyAlc.LoadFromAssemblyName(assemblyToResolve);
        }
    }
}
```

Com a nova implementação, dê uma olhada na sequência de chamadas que ocorre quando o módulo é carregado e o `Test-AlcModule` é executado:

![Diagrama da sequência de chamadas usando o ALC personalizado para carregar dependências](./media/resolving-dependency-conflicts/alc-sequence.png)

Alguns pontos de interesse são:

- O `IModuleAssemblyInitializer` é executado primeiro quando o módulo é carregado e configura o evento `Resolving`.
- Nós não carregamos as dependências até que `Test-AlcModule` seja executado e o método `EndProcessing()` seja chamado.
- Quando `EndProcessing()` é chamado, o ALC padrão falha ao localizar `AlcModule.Engine.dll` e aciona o evento `Resolving`.
- Nosso manipulador de eventos conecta o ALC personalizado ao ALC padrão e carrega somente o `AlcModule.Engine.dll`.
- Quando o `AlcEngine.Use()` é chamado no `AlcModule.Engine.dll`, o ALC personalizado é ativado novamente para resolver o `Shared.Dependency.dll`. Especificamente, ele sempre carrega o _nosso_ `Shared.Dependency.dll`, já que nunca entra em conflito com nada no ALC padrão e só procura no diretório `Dependencies`.

Ao montar a implementação, nosso novo layout de código-fonte tem esta aparência:

```
+ AlcModule.psd1
+ src/
  + AlcModule.Cmdlets/
  | + AlcModule.Cmdlets.csproj
  | + TestAlcModuleCommand.cs
  | + AlcModuleAssemblyLoadContext.cs
  | + AlcModuleInitializer.cs
  |
  + AlcModule.Engine/
  | + AlcModule.Engine.csproj
  | + AlcEngine.cs
```

O AlcModule.Cmdlets.csproj tem esta aparência:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <ProjectReference Include="..\AlcModule.Engine\AlcModule.Engine.csproj" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

O AlcModule.Engine.csproj tem a seguinte aparência:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
  </ItemGroup>
</Project>
```

Então, quando criamos o módulo, nossa estratégia é:

- Criar `AlcModule.Engine`
- Criar `AlcModule.Cmdlets`
- Copiar tudo de `AlcModule.Engine` para o diretório `Dependencies` e lembrar-se do que foi copiado
- Copiar tudo de `AlcModule.Cmdlets` que não estava em `AlcModule.Engine` no diretório do módulo base

Como aqui o layout do módulo é crucial para a separação de dependência, veja o seguinte script de build a ser usado na raiz de origem:

```powershell
param(
    # The .NET build configuration
    [ValidateSet('Debug', 'Release')]
    [string]
    $Configuration = 'Debug'
)

# Convenient reusable constants
$mod = "AlcModule"
$netcore = "netcoreapp3.1"
$copyExtensions = @('.dll', '.pdb')

# Source code locations
$src = "$PSScriptRoot/src"
$engineSrc = "$src/$mod.Engine"
$cmdletsSrc = "$src/$mod.Cmdlets"

# Generated output locations
$outDir = "$PSScriptRoot/out/$mod"
$outDeps = "$outDir/Dependencies"

# Build AlcModule.Engine
Push-Location $engineSrc
dotnet publish -c $Configuration
Pop-Location

# Build AlcModule.Cmdlets
Push-Location $cmdletsSrc
dotnet publish -c $Configuration
Pop-Location

# Ensure out directory exists and is clean
Remove-Item -Path $outDir -Recurse -ErrorAction Ignore
New-Item -Path $outDir -ItemType Directory
New-Item -Path $outDeps -ItemType Directory

# Copy manifest
Copy-Item -Path "$PSScriptRoot/$mod.psd1"

# Copy each Engine asset and remember it
$deps = [System.Collections.Generic.Hashtable[string]]::new()
Get-ChildItem -Path "$engineSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { $_.Extension -in $copyExtensions } |
    ForEach-Object { [void]$deps.Add($_.Name); Copy-Item -Path $_.FullName -Destination $outDeps }

# Now copy each Cmdlets asset, not taking any found in Engine
Get-ChildItem -Path "$cmdletsSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { -not $deps.Contains($_.Name) -and $_.Extension -in $copyExtensions } |
    ForEach-Object { Copy-Item -Path $_.FullName -Destination $outDir }
```

Por fim, temos uma forma geral de usar um Contexto de Carregamento de Assembly para isolar as dependências do módulo que permanecem robustas ao longo do tempo à medida que mais dependências são adicionadas.

Para obter um exemplo mais detalhado, acesse este [repositório GitHub](https://github.com/rjmholt/ModuleDependencyIsolationExample). Esse exemplo demonstra como migrar um módulo para usar um ALC e ao mesmo tempo manter o módulo funcionando no .NET Framework. Ele também mostra como usar o .NET Standard e o PowerShell Standard para simplificar a implementação principal.

### <a name="assembly-resolve-handler-for-side-by-side-loading-with-assemblyloadfile"></a>Manipulador de resolução de assembly para carregamento lado a lado com `Assembly.LoadFile()`

Outra maneira, possivelmente mais simples, de obter o carregamento lado a lado do assembly é vincular um evento `AssemblyResolve` a `Assembly.LoadFile()`. O uso de `Assembly.LoadFile()` tem a vantagem de ser a solução mais simples de implementar, além de funcionar com o .NET Core e o .NET Framework.

Para mostrar isso, vamos dar uma olhada em um exemplo rápido de uma implementação que combina ideias do exemplo de redirecionamento de associação dinâmica e do exemplo de Contexto de Carregamento de Assembly acima.

Chamaremos esse módulo de **LoadFileModule**, que tem um comando trivial `Test-LoadFile [-Path] <path>`. Esse módulo usa uma dependência no assembly `CsvHelper` (versão 15.0.5).

Assim como no módulo do ALC, precisamos primeiro dividir o módulo em duas partes.

A primeira parte faz a implementação real, `LoadFileModule.Engine`:

```csharp
using CsvHelper;

namespace LoadFileModule.Engine
{
    public class Runner
    {
        public void Use(string path)
        {
            // Here's where we use the CsvHelper dependency
            using (var reader = new StreamReader(path))
            using (var csvReader = new CsvReader(reader, CultureInfo.InvariantCulture))
            {
                // Imagine we do something useful here...
            }
        }
    }
}
```

A segunda parte é a que o PowerShell carrega diretamente, `LoadFileModule.Cmdlets`. Usamos uma estratégia semelhante ao módulo do ALC, na qual isolamos as dependências em um diretório separado. Mas, desta vez, carregamos todos os assemblies com um evento de resolução, em vez de apenas com o `LoadFileModule.Engine.dll`.

```csharp
using LoadFileModule.Engine;

namespace LoadFileModule.Cmdlets
{
    // Actual cmdlet definition
    [Cmdlet(VerbsDiagnostic.Test, "LoadFile")]
    public class TestLoadFileCommand : Cmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        protected override void EndProcessing()
        {
            // Here's where we use LoadFileModule.Engine
            new Runner().Use(Path);
        }
    }

    // This class controls our dependency resolution
    public class ModuleContextHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // We catalog our dependencies here to ensure we don't load anything else
        private static IReadOnlyDictionary<string, int> s_dependencies = new Dictionary<string, int>
        {
            { "CsvHelper", 15 },
        };

        // Set up the path to our dependency directory within the module
        private static string s_dependenciesDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        // This makes sure we only try to resolve dependencies when the module is loaded
        private static bool s_engineLoaded = false;

        public void OnImport()
          {
            // Set up our event when the module is loaded
            AppDomain.CurrentDomain.AssemblyResolve += HandleResolveEvent;
        }

        public void OnRemove(PSModuleInfo psModuleInfo)
        {
            // Unset the event when the module is unloaded
            AppDomain.CurrentDomain.AssemblyResolve -= HandleResolveEvent;
        }

        private static Assembly HandleResolveEvent(object sender, ResolveEventArgs args)
        {
            var asmName = new AssemblyName(args.Name);

            // First we want to know if this is the top-level assembly
            if (asmName.Name.Equals("LoadFileModule.Engine"))
            {
                s_engineLoaded = true;
                return Assembly.LoadFile(Path.Combine(s_dependenciesDirPath, "Unrelated.Engine.dll"));
            }

            // Otherwise, if that assembly has been loaded, we must try to resolve its dependencies too
            if (s_engineLoaded
                && s_dependencies.TryGetValue(asmName.Name, out int requiredMajorVersion)
                && asmName.Version.Major == requiredMajorVersion)
            {
                string asmPath = Path.Combine(s_dependenciesDirPath, $"{asmName.Name}.dll");
                return Assembly.LoadFile(asmPath);
            }

            return null;
        }
    }
}
```

Por fim, o layout do módulo também é semelhante ao módulo do ALC:

```
LoadFileModule/
  + LoadFileModule.Cmdlets.dll
  + LoadFileModule.psd1
  + Dependencies/
  |  + LoadFileModule.Engine.dll
  |  + CsvHelper.dll
```

Com essa estrutura em vigor, o **LoadFileModule** agora dá suporte ao carregamento com outros módulos com uma dependência no **CsvHelper**.

Como o nosso manipulador se aplica a **todos** os eventos `AssemblyResolve` no Domínio do Aplicativo, precisamos fazer algumas escolhas de design específicas aqui:

- Para restringir a janela na qual o nosso evento pode interferir com outro carregamento, começamos a tratar o carregamento de dependência geral apenas depois que `LoadFileModule.Engine.dll` foi carregado.
- Enviamos por push o `LoadFileModule.Engine.dll` para o diretório Dependencies, para que ele seja carregado por uma chamada `LoadFile()` em vez de pelo PowerShell. Isso significa que as próprias cargas de dependência sempre acionarão um evento `AssemblyResolve`, mesmo se outro `CsvHelper.dll` (por exemplo) for carregado no PowerShell.
  Isso nos dá a oportunidade de encontrar a dependência correta.
- Como só precisamos resolver as dependências específicas do nosso módulo, somos forçados a codificar um dicionário de nomes e versões de dependência no nosso manipulador. No nosso caso específico, seria possível usar a propriedade `ResolveEventArgs.RequestingAssembly` para descobrir se `CsvHelper` está sendo solicitado pelo nosso módulo. Mas isso não funcionará para dependências de dependências; por exemplo, se o próprio `CsvHelper` tiver gerado um evento `AssemblyResolve`. Há outras maneiras mais difíceis de fazer isso, como comparar assemblies solicitados aos metadados de assemblies no diretório `Dependencies`. Mas, neste exemplo, fizemos essa verificação mais explícita para realçar o problema e simplificar o exemplo.

Essa é a principal diferença entre a estratégia de `LoadFile()` e a estratégia de ALC: o evento `AssemblyResolve` precisa atender a todas as cargas no Domínio do Aplicativo, fazendo com que seja muito mais difícil evitar que a nossa resolução de dependência seja agrupada com outros módulos. No entanto, a falta de ALCs no .NET Framework faz com que valha a pena entender essa opção.

### <a name="custom-application-domains"></a>Domínios do Aplicativo personalizados

A opção final e mais extrema para o isolamento de assembly é usar Domínios do Aplicativo personalizados.
Os Domínios do Aplicativo (usados no plural) só estão disponíveis no .NET Framework. Eles são usados para fornecer isolamento em processo entre as partes de um aplicativo .NET. Um dos usos é isolar as cargas de assembly umas das outras no mesmo processo.

No entanto, os Domínios do Aplicativo são limites de serialização. Os objetos em um Domínio do Aplicativo não podem ser referenciados e usados diretamente por objetos em outro Domínio do Aplicativo. Você pode contornar esse problema implementando `MarshalByRefObject`. Mas quando você não controla os tipos, como costuma ser o caso com dependências, não é possível forçar uma implementação aqui. A única solução é fazer grandes alterações na arquitetura. O limite de serialização também tem sérias implicações para o desempenho.

Como os Domínios do Aplicativo têm essa limitação séria (são difíceis de implementar e só funcionam no .NET Framework) não daremos um exemplo de como usá-los aqui. Embora é válido mencioná-los como uma possibilidade, eles não são recomendados.

Se você está interessado em tentar usar um Domínio do Aplicativo personalizado, os seguintes links podem ser úteis:

- [Documentação conceitual sobre os Domínios do Aplicativo](/dotnet/framework/app-domains/application-domains)
- [Exemplos de uso dos Domínios do Aplicativo](/dotnet/framework/app-domains/use)

## <a name="solutions-for-dependency-conflicts-that-dont-work-for-powershell"></a>Soluções para conflitos de dependência que não funcionam para o PowerShell

Por fim, abordaremos algumas possibilidades que surgem ao pesquisar no .NET conflitos de dependência que podem parecer promissores, mas normalmente não funcionarão no PowerShell.

Todas essas soluções são alteradas para as configurações de implantação de um ambiente no qual você controla o aplicativo e, possivelmente, o computador inteiro. Essas soluções são orientadas para cenários como servidores Web e outros aplicativos implantados em ambientes de servidor, nos quais o ambiente destina-se a hospedar o aplicativo e pode ser configurado pelo usuário de implantação. Elas também tendem a ser muito orientadas para .NET Framework, o que significa que eles não funcionam com o PowerShell 6 ou versões posteriores.

Se você sabe que o seu módulo só é usado em ambientes do Windows PowerShell 5.1 dos quais você tem controle total, algumas dessas opções podem ser usadas. No entanto, em geral, **os módulos não devem modificar o estado do computador global dessa forma**. Isso pode interromper as configurações que causam problemas em `powershell.exe`, em outros módulos ou em outros aplicativos dependentes o que faz com que o módulo falhe de maneiras inesperadas.

### <a name="static-binding-redirect-with-appconfig-to-force-using-the-same-dependency-version"></a>Redirecionamento de associação estática com app.config para forçar o uso da mesma versão de dependência

Os aplicativos .NET Framework podem aproveitar um arquivo `app.config` para configurar alguns dos comportamentos do aplicativo de modo declarativo. É possível gravar uma entrada de `app.config` que configura a associação de assembly para redirecionar o carregamento de assembly para uma versão específica.

Essa solução no PowerShell tem dois problemas:

- O .NET Core não dá suporte a `app.config`, portanto, essa solução só se aplica a `powershell.exe`.
- `powershell.exe` é um aplicativo compartilhado que reside no diretório `System32`. É provável que o seu módulo não seja capaz de modificar o conteúdo dele em muitos sistemas. Mesmo que ele seja, modificar o `app.config` pode interromper uma configuração existente ou afetar o carregamento de outros módulos.

### <a name="setting-codebase-with-appconfig"></a>Configurar o `codebase` com app.config

Pelos mesmos motivos, tentar definir a configuração de `codebase` em `app.config` não funcionará nos módulos do PowerShell.

### <a name="installing-dependencies-to-the-global-assembly-cache-gac"></a>Instalar dependências no GAC (Cache de Assembly Global)

Outra maneira de resolver conflitos de versão de dependência no .NET Framework é instalar dependências no GAC, de modo que versões diferentes possam ser carregadas lado a lado no GAC.

Novamente, nos módulos do PowerShell os principais problemas são:

- O GAC aplica-se somente ao .NET Framework, portanto, isso não funciona no PowerShell 6 e versões posteriores.
- A instalação de assemblies no GAC é uma modificação do estado do computador global e pode causar efeitos colaterais em outros aplicativos ou em outros módulos. Ela também pode ser difícil realizar corretamente, mesmo quando o módulo tem os privilégios de acesso necessários. Fazer algo errado pode causar problemas sérios e em todo o computador em outros aplicativos .NET.

## <a name="further-reading"></a>Leitura adicional

Há muitos outros artigos sobre conflitos de dependência de versão do assembly do .NET que você pode ler. Veja alguns pontos de partida interessantes:

- [.NET: Assemblies no .NET](/dotnet/standard/assembly/)
- [.NET Core: O algoritmo de carregamento de assembly gerenciado](/dotnet/core/dependency-loading/loading-managed)
- [.NET Core: Compreendendo o System.Runtime.Loader.AssemblyLoadContext](/dotnet/core/dependency-loading/understanding-assemblyloadcontext)
- [.NET Core: Discussão sobre soluções de carregamento lado a lado do assembly](https://github.com/dotnet/runtime/issues/13471)
- [.NET Framework: Como redirecionar versões de assembly](/dotnet/framework/configure-apps/redirect-assembly-versions)
- [.NET Framework: Práticas recomendadas para carregamento de assembly](/dotnet/framework/deployment/best-practices-for-assembly-loading)
- [.NET Framework: Como o runtime localiza os assemblies](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [.NET Framework: Resolver carregamentos de assembly](/dotnet/standard/assembly/resolve-loads)
- [Stack Overflow: Como e por que realizar o redirecionamento da associação de assembly?](https://stackoverflow.com/questions/43365736/assembly-binding-redirect-how-and-why)
- [PowerShell: Discussão sobre a implementação do AssemblyLoadContexts](https://github.com/PowerShell/PowerShell/issues/11571)
- [PowerShell: `Assembly.LoadFile()` não carrega no AssemblyLoadContext padrão](https://github.com/PowerShell/PowerShell/issues/12052)
- [Rick Strahl: Quando uma dependência de assembly do .NET é carregada?](https://weblog.west-wind.com/posts/2012/Nov/03/Back-to-Basics-When-does-a-NET-Assembly-Dependency-get-loaded)
- [Jon Skeet: Resumo do controle de versão no .NET](https://codeblog.jonskeet.uk/2019/06/30/versioning-limitations-in-net/)
- [Nate McMaster: Saiba mais sobre os primitivos do .NET Core](https://natemcmaster.com/blog/2017/12/21/netcore-primitives/)
