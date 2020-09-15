---
title: One-liners and the pipeline (Uma linha e o pipeline)
description: Um comando de uma linha do PowerShell é um pipeline contínuo, contendo vários comandos, para realizar uma só tarefa.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: b8fd45e5e5dc408754ebac015757ef4241428978
ms.sourcegitcommit: 109f132360e8adbbdaf5dbc42a270be73d9dfa9b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84633338"
---
# <a name="chapter-4---one-liners-and-the-pipeline"></a>Capítulo 4 – Comandos de uma linha e o pipeline

Quando comecei a aprender a usar o PowerShell pela primeira vez, se eu não conseguia realizar uma tarefa com um comando de uma linha do PowerShell, voltava para a GUI. Com o tempo, aprimorei minhas habilidades até conseguir escrever scripts, funções e módulos. Não se assuste com alguns dos exemplos mais avançados que você poderá ver na Internet. Ninguém é um especialista nato no PowerShell. Em algum momento, todos éramos iniciantes.

Tenho um conselho para dar a vocês que ainda estão usando a GUI para administração: instale as ferramentas de gerenciamento na estação de trabalho de administração e gerencie seus servidores remotamente. Dessa forma, não importa se o servidor está executando uma instalação da GUI ou do Server Core do sistema operacional.
Isso vai ajudar a preparar você para gerenciar servidores remotamente com o PowerShell.

Assim como recomendamos nos capítulos anteriores, lembre-se de acompanhar os exemplos no computador do ambiente de laboratório do Windows 10.

## <a name="one-liners"></a>Comandos de uma linha

Um comando de uma linha do PowerShell é um pipeline contínuo e, não necessariamente, um comando que esteja em uma linha física. Nem todos os comandos que estão em uma linha física são comandos de uma linha.

Embora o comando a seguir esteja em várias linhas físicas, ele é um comando de uma linha do PowerShell, pois é um pipeline contínuo. Ele pode ser escrito em uma linha física, mas optei pela quebra de linha no símbolo de barra vertical. O símbolo de barra vertical é um dos caracteres em que uma quebra de linha natural é permitida no PowerShell.

```powershell
Get-Service |
  Where-Object CanPauseAndContinue -eq $true |
    Select-Object -Property *
```

```Output
Name                : LanmanWorkstation
RequiredServices    : {NSI, MRxSmb20, Bowser}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Workstation
DependentServices   : {SessionEnv, Netlogon, Browser}
MachineName         : .
ServiceName         : LanmanWorkstation
ServicesDependedOn  : {NSI, MRxSmb20, Bowser}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :

Name                : Netlogon
RequiredServices    : {LanmanWorkstation}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Netlogon
DependentServices   : {}
MachineName         : .
ServiceName         : Netlogon
ServicesDependedOn  : {LanmanWorkstation}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :

Name                : vmicheartbeat
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Heartbeat Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicheartbeat
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmickvpexchange
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Data Exchange Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmickvpexchange
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicrdv
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Remote Desktop Virtualization Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicrdv
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicshutdown
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Guest Shutdown Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicshutdown
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmictimesync
RequiredServices    : {VmGid}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Time Synchronization Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmictimesync
ServicesDependedOn  : {VmGid}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicvss
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Volume Shadow Copy Requestor
DependentServices   : {}
MachineName         : .
ServiceName         : vmicvss
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : Winmgmt
RequiredServices    : {RPCSS}
CanPauseAndContinue : True
CanShutdown         : True
CanStop             : True
DisplayName         : Windows Management Instrumentation
DependentServices   : {wscsvc, NcaSvc, iphlpsvc}
MachineName         : .
ServiceName         : Winmgmt
ServicesDependedOn  : {RPCSS}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :
```

As quebras de linha naturais podem ocorrer em caracteres comumente usados, incluindo vírgula (`,`) e colchetes de abertura (`[`), chaves (`{`) e parênteses (`(`). Outras que não são tão comuns incluem ponto e vírgula (`;`), sinal de igual (`=`) e aspas simples e duplas de abertura (`'`, `"`).

O uso do caractere de acento grave (`` ` ``) como um caractere de continuação de linha é um tópico controverso. Minha recomendação é tentar evitá-lo, se possível. Em geral, vejo comandos do PowerShell escritos com um acento grave imediatamente após um caractere de quebra de linha natural.
Não há motivo para ele estar lá.

```powershell
Get-Service -Name w32time |
>> Select-Object -Property *
```

```Output
Name                : w32time
RequiredServices    : {}
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
DisplayName         : Windows Time
DependentServices   : {}
MachineName         : .
ServiceName         : w32time
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :
```

Os comandos mostrados nos dois exemplos anteriores funcionam bem no console do PowerShell. Mas se você tentar executá-los no painel de console do ISE do PowerShell, eles vão gerar um erro. O painel de console do ISE do PowerShell não aguarda o restante do comando ser inserido na próxima linha, como o console do PowerShell. Para evitar esse problema no painel de console do ISE do PowerShell, use <kbd>Shift</kbd>+<kbd>Enter</kbd> em vez de apenas selecionar <kbd>Enter</kbd> ao continuar um comando em outra linha.

Este próximo exemplo não é um comando de uma linha do PowerShell porque não é um pipeline contínuo. São dois comandos separados em uma linha, separados por ponto e vírgula.

```powershell
$Service = 'w32time'; Get-Service -Name $Service
```

```powershell
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

Muitas linguagens de programação e script exigem um ponto e vírgula no final de cada linha. Embora eles possam ser usados dessa forma no PowerShell, isso não é recomendado porque não são necessários.

## <a name="filtering-left"></a>Filtragem à esquerda

Os resultados dos comandos mostrados neste capítulo foram filtrados para um subconjunto. Por exemplo, `Get-Service` foi usado com o parâmetro **Name** para filtrar a lista de serviços que foram retornados apenas ao serviço de Tempo do Windows.

No pipeline, o ideal é sempre filtrar os resultados para o que você está procurando o mais rápido possível. Isso é feito usando parâmetros no primeiro comando ou aquele mais à esquerda.
Isso, às vezes, é chamado de _filtragem à esquerda_.

O exemplo a seguir usa o parâmetro **Name** de `Get-Service` para filtrar imediatamente os resultados somente para o serviço de Tempo do Windows.

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

Não é incomum ver exemplos em que o comando é direcionado para `Where-Object`, a fim de realizar a filtragem.

```powershell
Get-Service | Where-Object Name -eq w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  W32Time            Windows Time
```

O primeiro exemplo realiza a filtragem na origem e retorna apenas os resultados para o serviço de Tempo do Windows.
O segundo exemplo retorna todos os serviços e os direciona para outro comando a fim de realizar a filtragem. Embora isso possa não parecer ser um grande problema neste exemplo, imagine se você estiver consultando uma lista de usuários do Active Directory. Você realmente deseja retornar as informações para muitos milhares de contas de usuário do Active Directory apenas para direcioná-las para outro comando que as filtre em um pequeno subconjunto? Minha recomendação é sempre realizar a filtragem à esquerda mesmo quando isso não parece importante. Você ficará tão acostumado com isso que realizará uma filtragem automática à esquerda quando for realmente importante.

Uma vez, alguém me disse que a ordem na qual os comandos são especificados não importa. Isso está longe de ser verdade. A ordem na qual os comandos são especificados é realmente importante ao realizar a filtragem. Por exemplo, considere o cenário em que você está usando `Select-Object` para selecionar apenas algumas propriedades e `Where-Object` para filtrar as propriedades que não estarão na seleção. Nesse cenário, a filtragem precisará ocorrer primeiro, caso contrário, a propriedade não existirá no pipeline ao tentar realizar a filtragem.

```powershell
Get-Service |
Select-Object -Property DisplayName, Running, Status |
Where-Object CanPauseAndContinue
```

O comando no exemplo anterior não retorna nenhum resultado, porque a propriedade **CanStopAndContinue** não existe quando os resultados de `Select-Object` são direcionados para `Where-Object`. Essa propriedade específica não foi "selecionada". Em essência, ela foi filtrada. A reversão da ordem de `Select-Object` e `Where-Object` produz os resultados desejados.

```powershell
Get-Service |
Where-Object CanPauseAndContinue |
Select-Object -Property DisplayName, Status
```

```Output
DisplayName                                    Status
-----------                                    ------
Workstation                                    Running
Netlogon                                       Running
Hyper-V Heartbeat Service                      Running
Hyper-V Data Exchange Service                  Running
Hyper-V Remote Desktop Virtualization Service  Running
Hyper-V Guest Shutdown Service                 Running
Hyper-V Time Synchronization Service           Running
Hyper-V Volume Shadow Copy Requestor           Running
Windows Management Instrumentation             Running
```

## <a name="the-pipeline"></a>O pipeline

Como você viu em muitos dos exemplos mostrados até agora neste livro, muitas vezes, a saída de um comando pode ser usada como a entrada de outro comando. No Capítulo 3, `Get-Member` foi usado para determinar o tipo de objeto que um comando produz. O Capítulo 3 também mostrou o uso do parâmetro **ParameterType** de `Get-Command` para determinar quais comandos aceitaram esse tipo de entrada, embora não necessariamente pela entrada de pipeline.

Dependendo da extensão da Ajuda de comandos, ela pode incluir uma seção **ENTRADAS** e **SAÍDAS**.

```powershell
help Stop-Service -Full
```

```Output
...
INPUTS
    System.ServiceProcess.ServiceController, System.String
        You can pipe a service object or a string that contains the name of a service
        to this cmdlet.

OUTPUTS
    None, System.ServiceProcess.ServiceController
        This cmdlet generates a System.ServiceProcess.ServiceController object that
        represents the service, if you use the PassThru parameter. Otherwise, this
        cmdlet does not generate any output.
...
```

Somente a seção relevante da Ajuda é mostrada nos resultados anteriores. Como você pode ver, a seção **ENTRADAS** indica que um objeto **ServiceController** ou **String** pode ser direcionado para o cmdlet `Stop-Service`. Ele não informa quais parâmetros aceitam esse tipo de entrada. Uma das maneiras mais fáceis de determinar essas informações é examinar os diferentes parâmetros na versão completa da Ajuda para o cmdlet `Stop-Service`.

```powershell
help Stop-Service -Full
```

```powershell
...
-DisplayName <String[]>
    Specifies the display names of the services to stop. Wildcard characters are
    permitted.

    Required?                    true
    Position?                    named
    Default value                None
    Accept pipeline input?       False
    Accept wildcard characters?  false

-InputObject <ServiceController[]>
    Specifies ServiceController objects that represent the services to stop. Enter a
    variable that contains the objects, or type a command or expression that gets the
    objects.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByValue)
    Accept wildcard characters?  false

-Name <String[]>
    Specifies the service names of the services to stop. Wildcard characters are
    permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  false
...
```

Mais uma vez, mostrei apenas a parte relevante da Ajuda no conjunto de resultados anterior. Observe que o parâmetro **DisplayName** não aceita a entrada de pipeline, o parâmetro **InputObject** aceita a entrada do pipeline **por valor** para os objetos **ServiceController**, e o parâmetro **Name** aceita a entrada do pipeline **por valor** para objetos de **cadeia de caracteres**. Ele também aceita a entrada de pipeline **pelo nome da propriedade**.

Quando um parâmetro aceita a entrada de pipeline pelo nome da propriedade e por valor, ele sempre tenta **por valor** primeiro. Se **por valor** falhar, ele tentará **pelo nome da propriedade**. **Por valor** é um pouco enganoso. Prefiro chamá-lo de **por tipo**. Isso significa que se você direcionar os resultados de um comando que produz um tipo de objeto **ServiceController** para `Stop-Service`, ele associará essa entrada ao parâmetro **InputObject**. Porém, se você direcionar os resultados de um comando que produz a saída **String** para `Stop-Service`, ele o associará ao parâmetro **Name**. Se você direcionar os resultados de um comando que não produz um objeto **ServiceController** ou **String** para `Stop-Service`, mas que produz uma saída contendo uma propriedade chamada **Name**, ele associará a propriedade **Name** da saída ao parâmetro **Name** de `Stop-Service`.

Determine o tipo de saída produzido pelo comando `Get-Service`.

```powershell
Get-Service -Name w32time | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController
```

`Get-Service` produz um tipo de objeto ServiceController.

Como vimos anteriormente na Ajuda, o parâmetro **InputObject** de `Stop-Service` aceita objetos **ServiceController** por meio do pipeline **por valor** (por tipo). Isso significa que, quando os resultados do cmdlet `Get-Service` são direcionados para `Stop-Service`, eles se associam ao parâmetro **InputObject** de `Stop-Service`.

```powershell
Get-Service -Name w32time | Stop-Service
```

Agora, para experimentar a entrada da cadeia de caracteres. Direcione `w32time` para `Get-Member` apenas para confirmar que ela é uma cadeia de caracteres.

```powershell
'w32time' | Get-Member
```

```Output
   TypeName: System.String
```

Conforme mostrado anteriormente na Ajuda, o direcionamento de uma cadeia de caracteres para `Stop-Service` a associa **por valor** ao parâmetro **Name** de `Stop-Service`. Teste isso direcionando `w32time` para `Stop-Service`.

```powershell
'w32time' | Stop-Service
```

Observe que, no exemplo anterior, usei aspas simples em torno da cadeia de caracteres `w32time`. No PowerShell, você sempre deve usar aspas simples em vez de aspas duplas, a menos que o conteúdo da cadeia de caracteres entre aspas contenha uma variável que precise ser expandida para o valor real. Usando aspas simples, o PowerShell não precisa analisar o conteúdo contido entre aspas e, portanto, o código é executado um pouco mais rápido.

Crie um objeto personalizado para testar a entrada do pipeline pelo nome da propriedade para o parâmetro **Name** de `Stop-Service`.

```powershell
$CustomObject = [pscustomobject]@{
 Name = 'w32time'
 }
```

O conteúdo da variável **CustomObject** é um tipo de objeto **PSCustomObject** e contém uma propriedade chamada **Name**.

```powershell
$CustomObject | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty string Name=w32time
```

Se você for colocar a variável `$CustomObject` entre aspas, o ideal será usar aspas duplas.
Caso contrário, usando aspas simples, a cadeia de caracteres literal `$CustomObject` será direcionada para `Get-Member`, em vez de para o valor contido pela variável.

Embora o direcionamento do conteúdo de `$CustomObject` para o cmdlet `Stop-Service` associe-o ao parâmetro **Name**, desta vez, ele o associa **pelo nome da propriedade** em vez de **por valor**, porque o conteúdo de `$CustomObject` é um objeto que tem uma propriedade chamada **Name**.

Neste exemplo, crio outro objeto personalizado usando outro nome de propriedade, como **Service**.

```powershell
$CustomObject = [pscustomobject]@{
  Service = 'w32time'
}
```

Um erro é gerado ao tentar direcionar `$CustomObject` para `Stop-Service`, porque ele não produz um objeto **ServiceController** ou **String** e não tem uma propriedade chamada **Name**.

```powershell
$CustomObject | Stop-Service
```

```Output
Stop-Service : Cannot find any service with service name '@{Service=w32time}'.
At line:1 char:17
+ $CustomObject | Stop-Service
+
    + CategoryInfo          : ObjectNotFound: (@{Service=w32time}:String) [Stop-Service]
   , ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.S
   topServiceCommand
```

Se a saída de um comando não for alinhada com as opções de entrada do pipeline para outro comando, `Select-Object` poderá ser usado para renomear a propriedade, de modo que as propriedades sejam alinhadas corretamente.

```powershell
$CustomObject |
  Select-Object -Property @{name='Name';expression={$_.Service}} |
    Stop-Service
```

Neste exemplo, `Select-Object` foi usado para renomear a propriedade **Service** para uma propriedade chamada **Name**.

A sintaxe desse exemplo pode parecer um pouco complicada a princípio. O que aprendi é que você nunca aprenderá a sintaxe copiando e colando o código. Reserve um tempo para digitar o código. Após algum tempo, isso passará a ser algo natural. Ter vários monitores é um grande benefício, pois você pode ver o código de exemplo em uma tela e digitá-lo em outro.

Ocasionalmente, o ideal é usar um parâmetro que não aceite a entrada do pipeline. O exemplo a seguir demonstra o uso da saída de um comando como a entrada de outro. Primeiro, salve o nome de exibição de alguns serviços Windows em um arquivo de texto.

```powershell
'Background Intelligent Transfer Service', 'Windows Time' |
Out-File -FilePath $env:TEMP\services.txt
```

Execute o comando que fornece a saída necessária entre parênteses como o valor do parâmetro do comando que exige a entrada.

```powershell
Stop-Service -DisplayName (Get-Content -Path $env:TEMP\services.txt)
```

Isso é exatamente como a ordem das operações em álgebra para aqueles que se lembram de como ela funciona. O comando entre parênteses sempre é executado antes da parte externa do comando.

## <a name="powershellget"></a>PowerShellGet

O PowerShellGet é um módulo do PowerShell que contém comandos para descoberta, instalação, publicação e atualização de módulos (e outros artefatos) do PowerShell em um repositório do NuGet. O PowerShellGet é fornecido no PowerShell versão 5.0 e superior. Ele está disponível como um download separado para o PowerShell versão 3.0 e superior.

A Microsoft hospeda um repositório online do NuGet chamado [Galeria do PowerShell][]. Embora esse repositório seja hospedado pela Microsoft, a maioria dos módulos contidos no repositório não é escrita pela Microsoft. Qualquer código obtido na Galeria do PowerShell deve ser examinado detalhadamente em um ambiente de teste isolado antes de ser considerado adequado para uso em um ambiente de produção.

A maioria das empresas desejará hospedar o próprio repositório do NuGet particular interno, no qual poderá publicar módulos somente para uso interno, bem como módulos que ela baixou de outras fontes depois de validá-los como não sendo mal-intencionados.

Use o cmdlet `Find-Module` que faz parte do módulo PowerShellGet para localizar um módulo na Galeria do PowerShell que escrevi chamado MrToolkit.

```powershell
Find-Module -Name MrToolkit
```

```Output
NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with
NuGet-based repositories. The NuGet provider must be available in 'C:\Program
Files\PackageManagement\ProviderAssemblies' or
'C:\Users\MrAdmin\AppData\Local\PackageManagement\ProviderAssemblies'. You can also
install the NuGet provider by running 'Install-PackageProvider -Name NuGet
-MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to install and import the
NuGet provider now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.1        MrToolkit                           PSGallery            Misc PowerShell Tools
```

Na primeira vez que você usar um dos comandos do módulo PowerShellGet, precisará instalar o provedor do NuGet.

Para instalar o módulo MrToolkit, redirecione o comando anterior para `Install-Module`.

```powershell
Find-Module -Name MrToolkit | Install-Module
```

```Output
Untrusted repository
You are installing the modules from an untrusted repository. If you trust this
repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet.
Are you sure you want to install the modules from
'https://www.powershellgallery.com/api/v2/'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): y
```

Como a Galeria do PowerShell é um repositório não confiável, ele solicita que você aprove a instalação do módulo.

## <a name="finding-pipeline-input-the-easy-way"></a>Como localizar a entrada do pipeline da maneira fácil

O módulo MrToolkit contém uma função chamada `Get-MrPipelineInput`. Esse cmdlet pode ser usado para determinar com facilidade quais parâmetros de um comando aceitam a entrada do pipeline, que tipo de objeto eles aceitam e se aceitam a entrada do pipeline **por valor** ou **pelo nome da propriedade**.

```powershell
Get-MrPipelineInput -Name Stop-Service
```

```Output
ParameterName ParameterType                             ValueFromPipeline ValueFromPipelineByPropertyName
------------- -------------                             ----------------- ---------------
InputObject   System.ServiceProcess.ServiceController[]              True           False
Name          System.String[]                                        True            True
```

Como você pode ver, as mesmas informações que determinamos anteriormente por meio da Ajuda podem ser determinadas com facilidade por meio dessa função.

## <a name="summary"></a>Resumo

Neste capítulo, você aprendeu mais sobre os comandos de uma linha do PowerShell. Você descobriu que o número de linhas físicas nas quais um comando está não tem nada a ver com o fato de ele ser ou não um comando de uma linha do PowerShell. Você também conheceu a filtragem à esquerda, o pipeline e o PowerShellGet.

## <a name="review"></a>Revisão

1. O que é um comando de uma linha do PowerShell?
1. Quais são alguns dos caracteres em que as quebras de linha naturais podem ocorrer no PowerShell?
1. Por que você deve realizar a filtragem à esquerda?
1. Quais são as duas maneiras pelas quais um comando do PowerShell pode aceitar a entrada do pipeline?
1. Por que você não deve confiar nos comandos encontrados na Galeria do PowerShell?

## <a name="recommended-reading"></a>Leitura recomendada

- [about_Pipelines][]
- [about_Command_Syntax][]
- [about_Parameters][]
- [PowerShellGet: A maneira MAIS FÁCIL de descobrir, instalar e atualizar módulos do PowerShell][psget]

<!-- link references-->
[about_Pipelines]: /powershell/module/microsoft.powershell.core/about/about_pipelines
[about_Command_Syntax]: /powershell/module/microsoft.powershell.core/about/about_command_syntax
[about_Parameters]: /powershell/module/microsoft.powershell.core/about/about_parameters
[psget]: https://mikefrobbins.com/2015/04/23/powershellget-the-big-easy-way-to-discover-install-and-update-powershell-modules/
[Galeria do PowerShell]: https://www.powershellgallery.com/
