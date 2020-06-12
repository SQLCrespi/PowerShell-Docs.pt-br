---
title: Discovering objects, properties, and methods (Descobrir objetos, propriedades e métodos)
description: Você não precisa ser um desenvolvedor para entender e usar objetos, propriedades e métodos.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 5ab972755afeba0d94bf6c2debaf84ec84cd9244
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438067"
---
# <a name="chapter-3---discovering-objects-properties-and-methods"></a><span data-ttu-id="7a8a2-103">Capítulo 3 – Como descobrir objetos, propriedades e métodos</span><span class="sxs-lookup"><span data-stu-id="7a8a2-103">Chapter 3 - Discovering objects, properties, and methods</span></span>

<span data-ttu-id="7a8a2-104">Meu primeiro contato com os computadores foi um Commodore 64, mas meu primeiro computador moderno foi um clone do 286 12 MHz da IBM com 1 megabyte de memória, um disco rígido de 40 MB e uma unidade de disquete de 5-1/4 polegadas com um monitor CGA que executava o Microsoft DOS 3.3.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-104">My first introduction to computers was a Commodore 64, but my first modern computer was a 286 12-Mhz IBM clone with 1 megabyte of memory, a 40-megabyte hard drive, and one 5-1/4 inch floppy disk drive with a CGA monitor running Microsoft DOS 3.3.</span></span>

<span data-ttu-id="7a8a2-105">Muitos profissionais de TI, como eu mesmo, estão familiarizados com a linha de comando, mas quando se fala de objetos, propriedades e métodos, eles ficam paralisados e dizem "não sou um desenvolvedor".</span><span class="sxs-lookup"><span data-stu-id="7a8a2-105">Many IT Pros, like myself, are no stranger to the command line, but when the subject of objects, properties, and methods comes up, they get the deer in the headlights look and say, "I'm not a developer."</span></span> <span data-ttu-id="7a8a2-106">Adivinha?</span><span class="sxs-lookup"><span data-stu-id="7a8a2-106">Guess what?</span></span> <span data-ttu-id="7a8a2-107">Você não precisa ser um desenvolvedor para ser bem-sucedido com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-107">You don't have to be a developer to be successful with PowerShell.</span></span> <span data-ttu-id="7a8a2-108">Não fique atrapalhado com a terminologia.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-108">Don't get bogged down in the terminology.</span></span> <span data-ttu-id="7a8a2-109">Nem tudo pode fazer sentido no começo, mas depois de um pouco de experiência prática, você começará a ter aqueles momentos de inspiração.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-109">Not everything may make sense initially, but after a little hands-on experience you'll start to have those "light bulb" moments.</span></span> <span data-ttu-id="7a8a2-110">"Aha!</span><span class="sxs-lookup"><span data-stu-id="7a8a2-110">"Aha!</span></span> <span data-ttu-id="7a8a2-111">É disso que o livro tratava."</span><span class="sxs-lookup"><span data-stu-id="7a8a2-111">So that's what the book was talking about."</span></span>

<span data-ttu-id="7a8a2-112">Lembre-se de experimentar os exemplos no computador para obter uma experiência prática.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-112">Be sure to try the examples on your computer to gain some of that hands-on experience.</span></span>

## <a name="requirements"></a><span data-ttu-id="7a8a2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a8a2-113">Requirements</span></span>

<span data-ttu-id="7a8a2-114">O módulo do Active Directory PowerShell é necessário para alguns dos exemplos mostrados neste capítulo.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-114">The Active Directory PowerShell module is required by some of the examples shown in this chapter.</span></span>
<span data-ttu-id="7a8a2-115">Ele faz parte das Ferramentas de Administração de Servidor Remoto para Windows.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-115">The module is part of the Remote Server Administration Tools (RSAT) for Windows.</span></span> <span data-ttu-id="7a8a2-116">Para a versão 1809 (ou superior) do Windows, as Ferramentas de Administração de Servidor Remoto são instaladas como um recurso do Windows.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-116">For the 1809 (or higher) build of Windows, the RSAT tools are installed as a Windows feature.</span></span>

- <span data-ttu-id="7a8a2-117">Para obter informações sobre como instalar as Ferramentas de Administração de Servidor Remoto, confira [Módulos de gerenciamento do Windows][].</span><span class="sxs-lookup"><span data-stu-id="7a8a2-117">For information about installing the RSAT tools, see [Windows Management modules][].</span></span>
- <span data-ttu-id="7a8a2-118">Para as versões mais antigas do Windows, confira [Ferramentas de Administração de Servidor Remoto para Windows][].</span><span class="sxs-lookup"><span data-stu-id="7a8a2-118">For older versions of Windows, see [RSAT for Windows][].</span></span>

## <a name="get-member"></a><span data-ttu-id="7a8a2-119">Get-Member</span><span class="sxs-lookup"><span data-stu-id="7a8a2-119">Get-Member</span></span>

<span data-ttu-id="7a8a2-120">`Get-Member` ajuda você a descobrir quais objetos, propriedades e métodos estão disponíveis para os comandos.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-120">`Get-Member` helps you discover what objects, properties, and methods are available for commands.</span></span>
<span data-ttu-id="7a8a2-121">Qualquer comando que produza a saída baseada em objeto pode ser direcionado para `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-121">Any command that produces object-based output can be piped to `Get-Member`.</span></span> <span data-ttu-id="7a8a2-122">Uma propriedade é uma característica de um item.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-122">A property is a characteristic about an item.</span></span> <span data-ttu-id="7a8a2-123">Sua carteira de motorista tem uma propriedade chamada cor dos olhos, e os valores mais comuns para essa propriedade são azul e castanho.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-123">Your drivers license has a property called eye color and the most common values for that property are blue and brown.</span></span> <span data-ttu-id="7a8a2-124">Um método é uma ação que pode ser executada em um item.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-124">A method is an action that can be taken on an item.</span></span> <span data-ttu-id="7a8a2-125">Continuando com o exemplo da carteira de motorista, um dos métodos é "Revoke", porque o departamento de trânsito pode revogar sua carteira de motorista.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-125">In staying with the drivers license example, one of the methods is "Revoke" because the department of motor vehicles can revoke your drivers license.</span></span>

### <a name="properties"></a><span data-ttu-id="7a8a2-126">Propriedades</span><span class="sxs-lookup"><span data-stu-id="7a8a2-126">Properties</span></span>

<span data-ttu-id="7a8a2-127">No exemplo a seguir, vou recuperar informações sobre o serviço de Tempo do Windows em execução no meu computador.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-127">In the following example, I'll retrieve information about the Windows Time service running on my computer.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="7a8a2-128">**Status**, **Name** e **DisplayName** são exemplos de propriedades, conforme mostrado no conjunto de resultados anterior.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-128">**Status**, **Name**, and **DisplayName** are examples of properties as shown in the previous set of results.</span></span> <span data-ttu-id="7a8a2-129">O valor da propriedade **Status** é `Running`, o valor da propriedade **Name** é `w32time` e o valor de **DisplayName** é `Windows Time`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-129">The value for the **Status** property is `Running`, the value for the **Name** property is `w32time`, and the value for **DisplayName** is `Windows Time`.</span></span>

<span data-ttu-id="7a8a2-130">Agora vou direcionar o mesmo comando para `Get-Member`:</span><span class="sxs-lookup"><span data-stu-id="7a8a2-130">Now I'll pipe that same command to `Get-Member`:</span></span>

```powershell
Get-Service -Name w32time | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, Sy...
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(ty...
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
ExecuteCommand            Method        void ExecuteCommand(int command)
GetHashCode               Method        int GetHashCode()
GetLifetimeService        Method        System.Object GetLifetimeService()
GetType                   Method        type GetType()
InitializeLifetimeService Method        System.Object InitializeLifetimeService()
Pause                     Method        void Pause()
Refresh                   Method        void Refresh()
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.Servi...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] Depe...
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle Serv...
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] Serv...
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType ...
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartTy...
Status                    Property      System.ServiceProcess.ServiceControllerStatus ...
ToString                  ScriptMethod  System.Object ToString();
```

<span data-ttu-id="7a8a2-131">A primeira linha dos resultados no exemplo anterior contém uma informação muito importante.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-131">The first line of the results in the previous example contains one piece of very important information.</span></span> <span data-ttu-id="7a8a2-132">**TypeName** informa que tipo de objeto foi retornado.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-132">**TypeName** tells you what type of object was returned.</span></span> <span data-ttu-id="7a8a2-133">Neste exemplo, um objeto **System.ServiceProcess.ServiceController** foi retornado.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-133">In this example, a **System.ServiceProcess.ServiceController** object was returned.</span></span> <span data-ttu-id="7a8a2-134">Em geral, isso é abreviado como a parte do **TypeName** logo após o último ponto; **ServiceController**, neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-134">This is often abbreviated as the portion of the **TypeName** just after the last period; **ServiceController** in this example.</span></span>

<span data-ttu-id="7a8a2-135">Depois de saber o tipo de objeto que um comando produz, você pode usar essas informações para localizar comandos que aceitem esse tipo de objeto como entrada.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-135">Once you know what type of object a command produces, you can use this information to find commands that accept that type of object as input.</span></span>

```powershell
Get-Command -ParameterType ServiceController
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Service                                        3.1.0.0    Microsof...
Cmdlet          Restart-Service                                    3.1.0.0    Microsof...
Cmdlet          Resume-Service                                     3.1.0.0    Microsof...
Cmdlet          Set-Service                                        3.1.0.0    Microsof...
Cmdlet          Start-Service                                      3.1.0.0    Microsof...
Cmdlet          Stop-Service                                       3.1.0.0    Microsof...
Cmdlet          Suspend-Service                                    3.1.0.0    Microsof...
```

<span data-ttu-id="7a8a2-136">Todos esses comandos têm um parâmetro que aceita um tipo de objeto **ServiceController** por pipeline, entrada de parâmetro ou ambos.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-136">All of those commands have a parameter that accepts a **ServiceController** object type by pipeline, parameter input, or both.</span></span>

<span data-ttu-id="7a8a2-137">Observe que há mais propriedades do que são exibidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-137">Notice that there are more properties than are displayed by default.</span></span> <span data-ttu-id="7a8a2-138">Embora essas propriedades adicionais não sejam exibidas por padrão, elas podem ser selecionadas no pipeline, direcionando o comando para o cmdlet `Select-Object` e usando o parâmetro **Property**.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-138">Although these additional properties aren't displayed by default, they can be selected from the pipeline by piping the command to the `Select-Object` cmdlet and using the **Property** parameter.</span></span> <span data-ttu-id="7a8a2-139">O exemplo a seguir seleciona todas as propriedades direcionando os resultados de `Get-Service` para `Select-Object` e especificando o caractere curinga `*` como o valor do parâmetro **Property**.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-139">The following example selects all of the properties by piping the results of `Get-Service` to `Select-Object` and specifying the `*` wildcard character as the value for the **Property** parameter.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property *
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

<span data-ttu-id="7a8a2-140">Propriedades específicas também podem ser selecionadas por meio de uma lista separada por vírgula para o valor do parâmetro **Property**.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-140">Specific properties can also be selected using a comma-separated list for the value of the **Property** parameter.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, Name, DisplayName, ServiceType
```

```Output
 Status Name    DisplayName        ServiceType
 ------ ----    -----------        -----------
Running w32time Windows Time Win32ShareProcess
```

<span data-ttu-id="7a8a2-141">Por padrão, quatro propriedades são retornadas em uma tabela, e cinco ou mais são retornadas em uma lista.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-141">By default, four properties are returned in a table and five or more are returned in a list.</span></span> <span data-ttu-id="7a8a2-142">Alguns comandos usam a formatação personalizada para substituir o número de propriedades exibidas por padrão em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-142">Some commands use custom formatting to override how many properties are displayed by default in a table.</span></span>
<span data-ttu-id="7a8a2-143">Há vários cmdlets `Format-*` que podem ser usados para substituir manualmente esses padrões.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-143">There are several `Format-*` cmdlets that can be used to manually override these defaults.</span></span> <span data-ttu-id="7a8a2-144">Os mais comuns são `Format-Table` e `Format-List`, que serão abordados em um capítulo futuro.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-144">The most common ones are `Format-Table` and `Format-List`, both of which will be covered in an upcoming chapter.</span></span>

<span data-ttu-id="7a8a2-145">Os caracteres curinga podem ser usados ao especificar os nomes de propriedades com `Select-Object`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-145">Wildcard characters can be used when specifying the property names with `Select-Object`.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can*
```

```powershell
Status              : Running
DisplayName         : Windows Time
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
```

<span data-ttu-id="7a8a2-146">No exemplo anterior, `Can*` foi usado como um dos valores do parâmetro **Property** para retornar todas as propriedades que começam com `Can`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-146">In the previous example, `Can*` was used as one of the values for the **Property** parameter to return all the properties that start with `Can`.</span></span> <span data-ttu-id="7a8a2-147">Isso inclui **CanPauseAndContinue**, **CanShutdown** e **CanStop**.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-147">These include **CanPauseAndContinue**, **CanShutdown**, and **CanStop**.</span></span>

### <a name="methods"></a><span data-ttu-id="7a8a2-148">Métodos</span><span class="sxs-lookup"><span data-stu-id="7a8a2-148">Methods</span></span>

<span data-ttu-id="7a8a2-149">Os métodos são uma ação que pode ser executada.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-149">Methods are an action that can be taken.</span></span> <span data-ttu-id="7a8a2-150">Use o parâmetro **MemberType** para restringir os resultados de `Get-Member`, a fim de mostrar apenas os métodos de `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-150">Use the **MemberType** parameter to narrow down the results of `Get-Member` to only show the methods for `Get-Service`.</span></span>

```powershell
Get-Service -Name w32time | Get-Member -MemberType Method
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType Definition
----                      ---------- ----------
Close                     Method     void Close()
Continue                  Method     void Continue()
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type ...
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Equals                    Method     bool Equals(System.Object obj)
ExecuteCommand            Method     void ExecuteCommand(int command)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Pause                     Method     void Pause()
Refresh                   Method     void Refresh()
Start                     Method     void Start(), void Start(string[] args)
Stop                      Method     void Stop()
WaitForStatus             Method     void WaitForStatus(System.ServiceProcess.ServiceC...
```

<span data-ttu-id="7a8a2-151">Como você pode ver, há muitos métodos.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-151">As you can see, there are many methods.</span></span> <span data-ttu-id="7a8a2-152">O método **Stop** pode ser usado para interromper um serviço Windows.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-152">The **Stop** method can be used to stop a Windows service.</span></span>

```powershell
(Get-Service -Name w32time).Stop()
```

<span data-ttu-id="7a8a2-153">Agora, para confirmar se o serviço de Tempo do Windows foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-153">Now to verify the Windows time service has indeed been stopped.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  w32time            Windows Time
```

<span data-ttu-id="7a8a2-154">Raramente uso métodos, mas é importante saber um pouco a respeito deles.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-154">I rarely find myself using methods, but they're something you need to be aware of.</span></span> <span data-ttu-id="7a8a2-155">Há ocasiões em que você encontrará um comando `Get-*` sem um comando correspondente para modificar esse item.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-155">There are times that you'll come across a `Get-*` command without a corresponding command to modify that item.</span></span>
<span data-ttu-id="7a8a2-156">Muitas vezes, um método pode ser usado para executar uma ação que o modifica.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-156">Often, a method can be used to perform an action that modifies it.</span></span> <span data-ttu-id="7a8a2-157">O cmdlet `Get-SqlAgentJob` no módulo do SQL Server PowerShell é um bom exemplo disso.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-157">The `Get-SqlAgentJob` cmdlet in the SqlServer PowerShell module is a good example of this.</span></span> <span data-ttu-id="7a8a2-158">O módulo é instalado como parte do [SSMS (SQL Server Management Studio)][SMSS].</span><span class="sxs-lookup"><span data-stu-id="7a8a2-158">The module installs as part of [SQL Server Management Studio (SMSS)][SMSS].</span></span> <span data-ttu-id="7a8a2-159">Não existe nenhum cmdlet `Set-*` correspondente, mas um método pode ser usado para concluir a mesma tarefa.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-159">No corresponding `Set-*` cmdlet exists, but a method can be used to complete the same task.</span></span>

<span data-ttu-id="7a8a2-160">Outro motivo para ter uma noção dos métodos é que muitos iniciantes pressupõem que alterações destrutivas não possam ser feitas com os comandos `Get-*`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-160">Another reason to be aware of methods is that many beginners assume destructive changes can't be made with `Get-*` commands.</span></span> <span data-ttu-id="7a8a2-161">Mas, de fato, eles poderão causar sérios problemas se forem usados de maneira inadequada.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-161">But they indeed can cause serious problems if used inappropriately.</span></span>

<span data-ttu-id="7a8a2-162">Uma opção melhor será usar um cmdlet para executar a ação, se houver.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-162">A better option is to use a cmdlet to perform the action if one exists.</span></span> <span data-ttu-id="7a8a2-163">Vá em frente e inicie o serviço de Tempo do Windows, mas, desta vez, use o cmdlet para iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-163">Go ahead and start the Windows Time service, except this time use the cmdlet for starting services.</span></span>

```powershell
Get-Service -Name w32time | Start-Service -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="7a8a2-164">Por padrão, `Start-Service` não retorna nenhum resultado, assim como o método start de `Get-Service`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-164">By default, `Start-Service` doesn't return any results just like the start method of `Get-Service`.</span></span>
<span data-ttu-id="7a8a2-165">No entanto, um dos benefícios do uso de um cmdlet é que, muitas vezes, o cmdlet oferece uma funcionalidade adicional que não está disponível em um método.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-165">But one of the benefits of using a cmdlet is that many times the cmdlet offers additional functionality that isn't available with a method.</span></span> <span data-ttu-id="7a8a2-166">No exemplo anterior, o parâmetro **PassThru** foi usado.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-166">In the previous example, the **PassThru** parameter was used.</span></span> <span data-ttu-id="7a8a2-167">Isso faz com que um cmdlet que normalmente não produz uma saída, produza uma saída.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-167">This causes a cmdlet that doesn't normally produce output, to produce output.</span></span>

<span data-ttu-id="7a8a2-168">Tenha cuidado ao fazer suposições sobre a saída de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-168">Be careful with assumptions about the output of a cmdlet.</span></span> <span data-ttu-id="7a8a2-169">Todos nós sabemos o que acontece quando fazemos suposições.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-169">We all know what happens when you assume things.</span></span> <span data-ttu-id="7a8a2-170">Vou recuperar informações sobre o processo do PowerShell em execução no meu computador do ambiente de laboratório do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-170">I'll retrieve information about the PowerShell process running on my Windows 10 lab environment computer.</span></span>

```powershell
Get-Process -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
    922      48   107984     140552       2.84   9020   1 powershell

```

<span data-ttu-id="7a8a2-171">Agora vou direcionar o mesmo comando para Get-Member:</span><span class="sxs-lookup"><span data-stu-id="7a8a2-171">Now I'll pipe that same command to Get-Member:</span></span>

```powershell
Get-Process -Name PowerShell | Get-Member
```

```Output
   TypeName: System.Diagnostics.Process

Name                       MemberType     Definition
----                       ----------     ----------
Handles                    AliasProperty  Handles = Handlecount
Name                       AliasProperty  Name = ProcessName
NPM                        AliasProperty  NPM = NonpagedSystemMemorySize64
PM                         AliasProperty  PM = PagedMemorySize64
SI                         AliasProperty  SI = SessionId
VM                         AliasProperty  VM = VirtualMemorySize64
WS                         AliasProperty  WS = WorkingSet64
Disposed                   Event          System.EventHandler Disposed(System.Object, ...
ErrorDataReceived          Event          System.Diagnostics.DataReceivedEventHandler ...
Exited                     Event          System.EventHandler Exited(System.Object, Sy...
OutputDataReceived         Event          System.Diagnostics.DataReceivedEventHandler ...
BeginErrorReadLine         Method         void BeginErrorReadLine()
BeginOutputReadLine        Method         void BeginOutputReadLine()
CancelErrorRead            Method         void CancelErrorRead()
CancelOutputRead           Method         void CancelOutputRead()
Close                      Method         void Close()
CloseMainWindow            Method         bool CloseMainWindow()
CreateObjRef               Method         System.Runtime.Remoting.ObjRef CreateObjRef(...
Dispose                    Method         void Dispose(), void IDisposable.Dispose()
Equals                     Method         bool Equals(System.Object obj)
GetHashCode                Method         int GetHashCode()
GetLifetimeService         Method         System.Object GetLifetimeService()
GetType                    Method         type GetType()
InitializeLifetimeService  Method         System.Object InitializeLifetimeService()
Kill                       Method         void Kill()
Refresh                    Method         void Refresh()
Start                      Method         bool Start()
ToString                   Method         string ToString()
WaitForExit                Method         bool WaitForExit(int milliseconds), void Wai...
WaitForInputIdle           Method         bool WaitForInputIdle(int milliseconds), boo...
__NounName                 NoteProperty   string __NounName=Process
BasePriority               Property       int BasePriority {get;}
Container                  Property       System.ComponentModel.IContainer Container {...
EnableRaisingEvents        Property       bool EnableRaisingEvents {get;set;}
ExitCode                   Property       int ExitCode {get;}
ExitTime                   Property       datetime ExitTime {get;}
Handle                     Property       System.IntPtr Handle {get;}
HandleCount                Property       int HandleCount {get;}
HasExited                  Property       bool HasExited {get;}
Id                         Property       int Id {get;}
MachineName                Property       string MachineName {get;}
MainModule                 Property       System.Diagnostics.ProcessModule MainModule ...
MainWindowHandle           Property       System.IntPtr MainWindowHandle {get;}
MainWindowTitle            Property       string MainWindowTitle {get;}
MaxWorkingSet              Property       System.IntPtr MaxWorkingSet {get;set;}
MinWorkingSet              Property       System.IntPtr MinWorkingSet {get;set;}
Modules                    Property       System.Diagnostics.ProcessModuleCollection M...
NonpagedSystemMemorySize   Property       int NonpagedSystemMemorySize {get;}
NonpagedSystemMemorySize64 Property       long NonpagedSystemMemorySize64 {get;}
PagedMemorySize            Property       int PagedMemorySize {get;}
PagedMemorySize64          Property       long PagedMemorySize64 {get;}
PagedSystemMemorySize      Property       int PagedSystemMemorySize {get;}
PagedSystemMemorySize64    Property       long PagedSystemMemorySize64 {get;}
PeakPagedMemorySize        Property       int PeakPagedMemorySize {get;}
PeakPagedMemorySize64      Property       long PeakPagedMemorySize64 {get;}
PeakVirtualMemorySize      Property       int PeakVirtualMemorySize {get;}
PeakVirtualMemorySize64    Property       long PeakVirtualMemorySize64 {get;}
PeakWorkingSet             Property       int PeakWorkingSet {get;}
PeakWorkingSet64           Property       long PeakWorkingSet64 {get;}
PriorityBoostEnabled       Property       bool PriorityBoostEnabled {get;set;}
PriorityClass              Property       System.Diagnostics.ProcessPriorityClass Prio...
PrivateMemorySize          Property       int PrivateMemorySize {get;}
PrivateMemorySize64        Property       long PrivateMemorySize64 {get;}
PrivilegedProcessorTime    Property       timespan PrivilegedProcessorTime {get;}
ProcessName                Property       string ProcessName {get;}
ProcessorAffinity          Property       System.IntPtr ProcessorAffinity {get;set;}
Responding                 Property       bool Responding {get;}
SafeHandle                 Property       Microsoft.Win32.SafeHandles.SafeProcessHandl...
SessionId                  Property       int SessionId {get;}
Site                       Property       System.ComponentModel.ISite Site {get;set;}
StandardError              Property       System.IO.StreamReader StandardError {get;}
StandardInput              Property       System.IO.StreamWriter StandardInput {get;}
StandardOutput             Property       System.IO.StreamReader StandardOutput {get;}
StartInfo                  Property       System.Diagnostics.ProcessStartInfo StartInf...
StartTime                  Property       datetime StartTime {get;}
SynchronizingObject        Property       System.ComponentModel.ISynchronizeInvoke Syn...
Threads                    Property       System.Diagnostics.ProcessThreadCollection T...
TotalProcessorTime         Property       timespan TotalProcessorTime {get;}
UserProcessorTime          Property       timespan UserProcessorTime {get;}
VirtualMemorySize          Property       int VirtualMemorySize {get;}
VirtualMemorySize64        Property       long VirtualMemorySize64 {get;}
WorkingSet                 Property       int WorkingSet {get;}
WorkingSet64               Property       long WorkingSet64 {get;}
PSConfiguration            PropertySet    PSConfiguration {Name, Id, PriorityClass, Fi...
PSResources                PropertySet    PSResources {Name, Id, Handlecount, WorkingS...
Company                    ScriptProperty System.Object Company {get=$this.Mainmodule....
CPU                        ScriptProperty System.Object CPU {get=$this.TotalProcessorT...
Description                ScriptProperty System.Object Description {get=$this.Mainmod...
FileVersion                ScriptProperty System.Object FileVersion {get=$this.Mainmod...
Path                       ScriptProperty System.Object Path {get=$this.Mainmodule.Fil...
Product                    ScriptProperty System.Object Product {get=$this.Mainmodule....
ProductVersion             ScriptProperty System.Object ProductVersion {get=$this.Main...
```

<span data-ttu-id="7a8a2-172">Observe que há mais propriedades listadas do que são exibidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-172">Notice that there are more properties listed than are displayed by default.</span></span> <span data-ttu-id="7a8a2-173">Várias propriedades padrão exibidas não aparecem como propriedades ao exibir os resultados de `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-173">A number of the default properties displayed don't show up as properties when viewing the results of `Get-Member`.</span></span> <span data-ttu-id="7a8a2-174">Isso ocorre porque muitos dos valores exibidos, como `NPM(K)`, `PM(K)`, `WS(K)` e `CPU(s)`, são propriedades calculadas.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-174">This is because many of the displayed values, such as `NPM(K)`, `PM(K)`, `WS(K)`, and `CPU(s)`, are calculated properties.</span></span> <span data-ttu-id="7a8a2-175">Para determinar os nomes das propriedades reais, o comando precisará ser direcionado para `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-175">To determine the actual property names, the command must be piped to `Get-Member`.</span></span>

<span data-ttu-id="7a8a2-176">Se um comando não produzir uma saída, ele não poderá ser redirecionado para `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-176">If a command does not produce output, it can't be piped to `Get-Member`.</span></span> <span data-ttu-id="7a8a2-177">Como `Start-Service` não produz nenhuma saída por padrão, ele gera um erro quando você tenta direcioná-lo para `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-177">Since `Start-Service` doesn't produce any output by default, it generates an error when you try to pipe it to `Get-Member`.</span></span>

```powershell
Start-Service -Name w32time | Get-Member
```

```Output
Get-Member : You must specify an object for the Get-Member cmdlet.
At line:1 char:31
+ Start-Service -Name w32time | Get-Member
+
    + CategoryInfo          : CloseError: (:) [Get-Member], InvalidOperationException
    + FullyQualifiedErrorId : NoObjectInGetMember,Microsoft.PowerShell.Commands.GetMembe
   rCommand
```

<span data-ttu-id="7a8a2-178">O parâmetro **PassThru** pode ser especificado com o cmdlet `Start-Service` para fazer com que ele produza uma saída, que é então direcionado para `Get-Member` sem erros.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-178">The **PassThru** parameter can be specified with the `Start-Service` cmdlet make it produce output, which is then piped to `Get-Member` without error.</span></span>

```powershell
Start-Service -Name w32time -PassThru | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, Sy...
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(ty...
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
ExecuteCommand            Method        void ExecuteCommand(int command)
GetHashCode               Method        int GetHashCode()
GetLifetimeService        Method        System.Object GetLifetimeService()
GetType                   Method        type GetType()
InitializeLifetimeService Method        System.Object InitializeLifetimeService()
Pause                     Method        void Pause()
Refresh                   Method        void Refresh()
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.Servi...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] Depe...
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle Serv...
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] Serv...
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType ...
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartTy...
Status                    Property      System.ServiceProcess.ServiceControllerStatus ...
ToString                  ScriptMethod  System.Object ToString();
```

<span data-ttu-id="7a8a2-179">A fim de ser direcionado para `Get-Member`, um comando precisa produzir uma saída baseada em objeto.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-179">To be piped to `Get-Member`, a command must produce object-based output.</span></span>

```powershell
Get-Service -Name w32time | Out-Host | Get-Member
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time

Get-Member : You must specify an object for the Get-Member cmdlet.
At line:1 char:40
+ Get-Service -Name w32time | Out-Host | Get-Member
+
    + CategoryInfo          : CloseError: (:) [Get-Member], InvalidOperationException
    + FullyQualifiedErrorId : NoObjectInGetMember,Microsoft.PowerShell.Commands.GetMemberCommand
```

<span data-ttu-id="7a8a2-180">`Out-Host` faz a gravação diretamente no host do PowerShell, mas não produz uma saída baseada em objeto para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-180">`Out-Host` writes directly to the PowerShell host, but it doesn't produce object-based output for the pipeline.</span></span> <span data-ttu-id="7a8a2-181">Portanto, ele não pode ser direcionado para `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-181">So it can't be piped to `Get-Member`.</span></span>

## <a name="active-directory"></a><span data-ttu-id="7a8a2-182">Active Directory</span><span class="sxs-lookup"><span data-stu-id="7a8a2-182">Active Directory</span></span>

> [!NOTE]
> <span data-ttu-id="7a8a2-183">As Ferramentas de Administração de Servidor Remoto listadas na seção de requisitos deste capítulo são necessárias para concluir esta seção.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-183">The Remote Server Administration Tools listed in the requirements section of this chapter are required to complete this section.</span></span> <span data-ttu-id="7a8a2-184">Além disso, conforme mencionado na introdução deste livro, o computador do ambiente de laboratório do Windows 10 precisa ser membro do domínio do ambiente de laboratório.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-184">Also, as mentioned in the introduction to this book, your Windows 10 lab environment computer must be a member of the lab environment domain.</span></span>

<span data-ttu-id="7a8a2-185">Use `Get-Command` com o parâmetro **Module** para determinar quais comandos foram adicionados como parte do módulo do Active Directory PowerShell quando as Ferramentas de Administração de Servidor Remoto foram instaladas.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-185">Use `Get-Command` with the **Module** parameter to determine what commands were added as part of the ActiveDirectory PowerShell module when the remote server administration tools were installed.</span></span>

```powershell
Get-Command -Module ActiveDirectory
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Add-ADCentralAccessPolicyMember                    1.0.0.0    ActiveDi...
Cmdlet          Add-ADComputerServiceAccount                       1.0.0.0    ActiveDi...
Cmdlet          Add-ADDomainControllerPasswordReplicationPolicy    1.0.0.0    ActiveDi...
Cmdlet          Add-ADFineGrainedPasswordPolicySubject             1.0.0.0    ActiveDi...
Cmdlet          Add-ADGroupMember                                  1.0.0.0    ActiveDi...
Cmdlet          Add-ADPrincipalGroupMembership                     1.0.0.0    ActiveDi...
Cmdlet          Add-ADResourcePropertyListMember                   1.0.0.0    ActiveDi...
Cmdlet          Clear-ADAccountExpiration                          1.0.0.0    ActiveDi...
Cmdlet          Clear-ADClaimTransformLink                         1.0.0.0    ActiveDi...
Cmdlet          Disable-ADAccount                                  1.0.0.0    ActiveDi...
...
```

<span data-ttu-id="7a8a2-186">Um total de 147 comandos foram adicionados como parte do módulo do Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-186">A total of 147 commands were added as part of the ActiveDirectory PowerShell module.</span></span> <span data-ttu-id="7a8a2-187">Alguns comandos desses comandos retornam apenas uma parte das propriedades disponíveis por padrão.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-187">Some commands of these commands only return a portion of the available properties by default.</span></span>

<span data-ttu-id="7a8a2-188">Você percebeu algo diferente sobre os nomes dos comandos deste módulo?</span><span class="sxs-lookup"><span data-stu-id="7a8a2-188">Did you notice anything different about the names of the commands in this module?</span></span> <span data-ttu-id="7a8a2-189">A parte do substantivo dos comandos tem um prefixo AD.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-189">The noun portion of the commands has an AD prefix.</span></span> <span data-ttu-id="7a8a2-190">É comum ver isto nos comandos da maioria dos módulos.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-190">This is common to see on the commands of most modules.</span></span> <span data-ttu-id="7a8a2-191">O prefixo foi criado para ajudar a prevenir conflitos de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-191">The prefix is designed to help prevent naming conflicts.</span></span>

```powershell
Get-ADUser -Identity mike | Get-Member
```

```Output
   TypeName: Microsoft.ActiveDirectory.Management.ADUser

Name              MemberType            Definition
----              ----------            ----------
Contains          Method                bool Contains(string propertyName)
Equals            Method                bool Equals(System.Object obj)
GetEnumerator     Method                System.Collections.IDictionaryEnumerator GetEn...
GetHashCode       Method                int GetHashCode()
GetType           Method                type GetType()
ToString          Method                string ToString()
Item              ParameterizedProperty Microsoft.ActiveDirectory.Management.ADPropert...
DistinguishedName Property              System.String DistinguishedName {get;set;}
Enabled           Property              System.Boolean Enabled {get;set;}
GivenName         Property              System.String GivenName {get;set;}
Name              Property              System.String Name {get;}
ObjectClass       Property              System.String ObjectClass {get;set;}
ObjectGUID        Property              System.Nullable`1[[System.Guid, mscorlib, Vers...
SamAccountName    Property              System.String SamAccountName {get;set;}
SID               Property              System.Security.Principal.SecurityIdentifier S...
Surname           Property              System.String Surname {get;set;}
UserPrincipalName Property              System.String UserPrincipalName {get;set;}
```

<span data-ttu-id="7a8a2-192">Mesmo que você esteja vagamente familiarizado com o Active Directory, é provável que saiba que uma conta de usuário tem mais propriedades do que as mostradas neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-192">Even if you're only vaguely familiar with Active Directory, you're probably aware that a user account has more properties than are shown in this example.</span></span>

<span data-ttu-id="7a8a2-193">O cmdlet `Get-ADUser` tem um parâmetro **Properties** que é usado para especificar as propriedades adicionais (não padrão) que você deseja retornar.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-193">The `Get-ADUser` cmdlet has a **Properties** parameter that is used to specify the additional (non-default) properties you want to return.</span></span> <span data-ttu-id="7a8a2-194">A especificação do caractere curinga `*` retorna todas elas.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-194">Specifying the `*` wildcard character returns all of them.</span></span>

```powershell
Get-ADUser -Identity mike -Properties * | Get-Member
```

```Output
   TypeName: Microsoft.ActiveDirectory.Management.ADUser

Name                                 MemberType            Definition
----                                 ----------            ----------
Contains                             Method                bool Contains(string proper...
Equals                               Method                bool Equals(System.Object obj)
GetEnumerator                        Method                System.Collections.IDiction...
GetHashCode                          Method                int GetHashCode()
GetType                              Method                type GetType()
ToString                             Method                string ToString()
Item                                 ParameterizedProperty Microsoft.ActiveDirectory.M...
AccountExpirationDate                Property              System.DateTime AccountExpi...
accountExpires                       Property              System.Int64 accountExpires...
AccountLockoutTime                   Property              System.DateTime AccountLock...
AccountNotDelegated                  Property              System.Boolean AccountNotDe...
AllowReversiblePasswordEncryption    Property              System.Boolean AllowReversi...
AuthenticationPolicy                 Property              Microsoft.ActiveDirectory.M...
AuthenticationPolicySilo             Property              Microsoft.ActiveDirectory.M...
BadLogonCount                        Property              System.Int32 BadLogonCount ...
badPasswordTime                      Property              System.Int64 badPasswordTim...
badPwdCount                          Property              System.Int32 badPwdCount {g...
CannotChangePassword                 Property              System.Boolean CannotChange...
CanonicalName                        Property              System.String CanonicalName...
Certificates                         Property              Microsoft.ActiveDirectory.M...
City                                 Property              System.String City {get;set;}
CN                                   Property              System.String CN {get;}
codePage                             Property              System.Int32 codePage {get;...
Company                              Property              System.String Company {get;...
CompoundIdentitySupported            Property              Microsoft.ActiveDirectory.M...
Country                              Property              System.String Country {get;...
countryCode                          Property              System.Int32 countryCode {g...
Created                              Property              System.DateTime Created {get;}
createTimeStamp                      Property              System.DateTime createTimeS...
Deleted                              Property              System.Boolean Deleted {get;}
Department                           Property              System.String Department {g...
Description                          Property              System.String Description {...
DisplayName                          Property              System.String DisplayName {...
DistinguishedName                    Property              System.String Distinguished...
Division                             Property              System.String Division {get...
DoesNotRequirePreAuth                Property              System.Boolean DoesNotRequi...
dSCorePropagationData                Property              Microsoft.ActiveDirectory.M...
EmailAddress                         Property              System.String EmailAddress ...
EmployeeID                           Property              System.String EmployeeID {g...
EmployeeNumber                       Property              System.String EmployeeNumbe...
Enabled                              Property              System.Boolean Enabled {get...
Fax                                  Property              System.String Fax {get;set;}
GivenName                            Property              System.String GivenName {ge...
HomeDirectory                        Property              System.String HomeDirectory...
HomedirRequired                      Property              System.Boolean HomedirRequi...
HomeDrive                            Property              System.String HomeDrive {ge...
HomePage                             Property              System.String HomePage {get...
HomePhone                            Property              System.String HomePhone {ge...
Initials                             Property              System.String Initials {get...
instanceType                         Property              System.Int32 instanceType {...
isDeleted                            Property              System.Boolean isDeleted {g...
KerberosEncryptionType               Property              Microsoft.ActiveDirectory.M...
LastBadPasswordAttempt               Property              System.DateTime LastBadPass...
LastKnownParent                      Property              System.String LastKnownPare...
lastLogoff                           Property              System.Int64 lastLogoff {ge...
lastLogon                            Property              System.Int64 lastLogon {get...
LastLogonDate                        Property              System.DateTime LastLogonDa...
lastLogonTimestamp                   Property              System.Int64 lastLogonTimes...
LockedOut                            Property              System.Boolean LockedOut {g...
logonCount                           Property              System.Int32 logonCount {ge...
LogonWorkstations                    Property              System.String LogonWorkstat...
Manager                              Property              System.String Manager {get;...
MemberOf                             Property              Microsoft.ActiveDirectory.M...
MNSLogonAccount                      Property              System.Boolean MNSLogonAcco...
MobilePhone                          Property              System.String MobilePhone {...
Modified                             Property              System.DateTime Modified {g...
modifyTimeStamp                      Property              System.DateTime modifyTimeS...
msDS-User-Account-Control-Computed   Property              System.Int32 msDS-User-Acco...
Name                                 Property              System.String Name {get;}
nTSecurityDescriptor                 Property              System.DirectoryServices.Ac...
ObjectCategory                       Property              System.String ObjectCategor...
ObjectClass                          Property              System.String ObjectClass {...
ObjectGUID                           Property              System.Nullable`1[[System.G...
objectSid                            Property              System.Security.Principal.S...
Office                               Property              System.String Office {get;s...
OfficePhone                          Property              System.String OfficePhone {...
Organization                         Property              System.String Organization ...
OtherName                            Property              System.String OtherName {ge...
PasswordExpired                      Property              System.Boolean PasswordExpi...
PasswordLastSet                      Property              System.DateTime PasswordLas...
PasswordNeverExpires                 Property              System.Boolean PasswordNeve...
PasswordNotRequired                  Property              System.Boolean PasswordNotR...
POBox                                Property              System.String POBox {get;set;}
PostalCode                           Property              System.String PostalCode {g...
PrimaryGroup                         Property              System.String PrimaryGroup ...
primaryGroupID                       Property              System.Int32 primaryGroupID...
PrincipalsAllowedToDelegateToAccount Property              Microsoft.ActiveDirectory.M...
ProfilePath                          Property              System.String ProfilePath {...
ProtectedFromAccidentalDeletion      Property              System.Boolean ProtectedFro...
pwdAnswer                            Property              System.String pwdAnswer {ge...
pwdLastSet                           Property              System.Int64 pwdLastSet {ge...
pwdQuestion                          Property              System.String pwdQuestion {...
SamAccountName                       Property              System.String SamAccountNam...
sAMAccountType                       Property              System.Int32 sAMAccountType...
ScriptPath                           Property              System.String ScriptPath {g...
sDRightsEffective                    Property              System.Int32 sDRightsEffect...
ServicePrincipalNames                Property              Microsoft.ActiveDirectory.M...
SID                                  Property              System.Security.Principal.S...
SIDHistory                           Property              Microsoft.ActiveDirectory.M...
SmartcardLogonRequired               Property              System.Boolean SmartcardLog...
sn                                   Property              System.String sn {get;set;}
State                                Property              System.String State {get;set;}
StreetAddress                        Property              System.String StreetAddress...
Surname                              Property              System.String Surname {get;...
Title                                Property              System.String Title {get;set;}
TrustedForDelegation                 Property              System.Boolean TrustedForDe...
TrustedToAuthForDelegation           Property              System.Boolean TrustedToAut...
UseDESKeyOnly                        Property              System.Boolean UseDESKeyOnl...
userAccountControl                   Property              System.Int32 userAccountCon...
userCertificate                      Property              Microsoft.ActiveDirectory.M...
UserPrincipalName                    Property              System.String UserPrincipal...
uSNChanged                           Property              System.Int64 uSNChanged {get;}
uSNCreated                           Property              System.Int64 uSNCreated {get;}
whenChanged                          Property              System.DateTime whenChanged...
whenCreated                          Property              System.DateTime whenCreated...
```

<span data-ttu-id="7a8a2-195">Agora ficou melhor.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-195">Now that looks more like it.</span></span>

<span data-ttu-id="7a8a2-196">Você pode imaginar um motivo pelo qual as propriedades de uma conta de usuário do Active Directory serão tão limitadas por padrão?</span><span class="sxs-lookup"><span data-stu-id="7a8a2-196">Can you think of a reason why the properties of an Active Directory user account would be so limited by default?</span></span> <span data-ttu-id="7a8a2-197">Imagine se você retornar todas as propriedades para cada conta de usuário no seu ambiente de produção do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-197">Imagine if you returned every property for every user account in your production Active Directory environment.</span></span> <span data-ttu-id="7a8a2-198">Considere a degradação do desempenho que você poderá causar, não apenas aos próprios controladores de domínio, mas também à sua rede.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-198">Think of the performance degradation that you could cause, not only to the domain controllers themselves, but also to your network.</span></span> <span data-ttu-id="7a8a2-199">É duvidoso que você realmente precisará de todas as propriedades de qualquer modo.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-199">It's doubtful that you'll actually need every property anyway.</span></span> <span data-ttu-id="7a8a2-200">O retorno de todas as propriedades para uma só conta de usuário é perfeitamente aceitável quando você está tentando determinar quais propriedades existem.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-200">Returning all of the properties for a single user account is perfectly acceptable when you're trying to determine what properties exist.</span></span>

<span data-ttu-id="7a8a2-201">Não é incomum executar um comando muitas vezes ao criar o protótipo dele.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-201">It's not uncommon to run a command many times when prototyping it.</span></span> <span data-ttu-id="7a8a2-202">Se você pretende executar uma consulta enorme, consulte-a uma vez e armazene os resultados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-202">If you're going to perform some huge query, query it once and store the results in a variable.</span></span> <span data-ttu-id="7a8a2-203">Em seguida, trabalhe com o conteúdo da variável em vez de usar repetidamente uma consulta cara.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-203">Then work with the contents of the variable instead of repeatedly using some expensive query.</span></span>

```powershell
$Users = Get-ADUser -Identity mike -Properties *
```

<span data-ttu-id="7a8a2-204">Use o conteúdo da variável `$Users` em vez de executar o comando anterior várias vezes.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-204">Use the contents of the `$Users` variable instead of running the previous command numerous times.</span></span>
<span data-ttu-id="7a8a2-205">Tenha em mente que o conteúdo da variável não é atualizado quando são feitas alterações nesse usuário no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-205">Keep in mind that the contents of the variable aren't updated when changes are made to that user in Active Directory.</span></span>

<span data-ttu-id="7a8a2-206">Você pode direcionar a variável `$Users` para `Get-Member`, a fim de descobrir as propriedades disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-206">You could pipe the `$Users` variable to `Get-Member` to discover the available properties.</span></span>

```powershell
$Users | Get-Member
```

<span data-ttu-id="7a8a2-207">Em seguida, selecione as propriedades individuais direcionando `$Users` para `Select-Object`, tudo isso sem precisar consultar o Active Directory mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-207">Then select the individual properties by piping `$Users` to `Select-Object`, all without ever having to query Active Directory more than one time.</span></span>

```powershell
$Users | Select-Object -Property Name, LastLogonDate, LastBadPasswordAttempt
```

<span data-ttu-id="7a8a2-208">Se você pretende consultar o Active Directory mais de uma vez, use o parâmetro **Properties** para especificar as propriedades não padrão desejadas.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-208">If you are going to query Active Directory more than once, use the **Properties** parameter to specify any non-default properties you want.</span></span>

```powershell
Get-ADUser -Identity mike -Properties LastLogonDate, LastBadPasswordAttempt
```

```Output
DistinguishedName      : CN=Mike F. Robbins,OU=Sales,DC=mikefrobbins,DC=com
Enabled                : True
GivenName              : Mike
LastBadPasswordAttempt : 2/4/2017 10:46:15 AM
LastLogonDate          : 2/18/2017 12:45:14 AM
Name                   : Mike F. Robbins
ObjectClass            : user
ObjectGUID             : a82a8c58-1332-4a57-a6e2-68e0c750ea56
SamAccountName         : mike
SID                    : S-1-5-21-2989741381-570885089-3319121794-1108
Surname                : Robbins
UserPrincipalName      : miker@mikefrobbins.com
```

## <a name="summary"></a><span data-ttu-id="7a8a2-209">Resumo</span><span class="sxs-lookup"><span data-stu-id="7a8a2-209">Summary</span></span>

<span data-ttu-id="7a8a2-210">Neste capítulo, você aprendeu a determinar o tipo de objeto que um comando produz, determinar quais propriedades e métodos estão disponíveis para um comando e trabalhar com os comandos que limitam as propriedades retornadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="7a8a2-210">In this chapter, you've learned how to determine what type of object a command produces, how to determine what properties and methods are available for a command, and how to work with commands that limit the properties that are returned by default.</span></span>

## <a name="review"></a><span data-ttu-id="7a8a2-211">Revisão</span><span class="sxs-lookup"><span data-stu-id="7a8a2-211">Review</span></span>

1. <span data-ttu-id="7a8a2-212">Que tipo de objeto o cmdlet `Get-Process` produz?</span><span class="sxs-lookup"><span data-stu-id="7a8a2-212">What type of object does the `Get-Process` cmdlet produce?</span></span>
1. <span data-ttu-id="7a8a2-213">Como determinar quais são as propriedades disponíveis para um comando?</span><span class="sxs-lookup"><span data-stu-id="7a8a2-213">How do you determine what the available properties are for a command?</span></span>
1. <span data-ttu-id="7a8a2-214">Se um comando existir para obter algo, mas não para definir a mesma coisa, o que você deverá verificar?</span><span class="sxs-lookup"><span data-stu-id="7a8a2-214">If a command exists for getting something but not for setting the same thing, what should you check for?</span></span>
1. <span data-ttu-id="7a8a2-215">Como alguns comandos que não produzem uma saída por padrão podem ser induzidos a produzir uma saída?</span><span class="sxs-lookup"><span data-stu-id="7a8a2-215">How can certain commands that don't produce output by default be made to produce output?</span></span>
1. <span data-ttu-id="7a8a2-216">Se você pretende trabalhar com os resultados de um comando que produz uma enorme quantidade de saída, o que você deve considerar fazer?</span><span class="sxs-lookup"><span data-stu-id="7a8a2-216">If you're going to be working with the results of a command that produces an enormous amount of output, what should you consider doing?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="7a8a2-217">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="7a8a2-217">Recommended Reading</span></span>

- <span data-ttu-id="7a8a2-218">[Get-Member][]</span><span class="sxs-lookup"><span data-stu-id="7a8a2-218">[Get-Member][]</span></span>
- <span data-ttu-id="7a8a2-219">[Exibindo a estrutura do objeto (Get-Member)][]</span><span class="sxs-lookup"><span data-stu-id="7a8a2-219">[Viewing Object Structure (Get-Member)][]</span></span>
- <span data-ttu-id="7a8a2-220">[about_Objects][]</span><span class="sxs-lookup"><span data-stu-id="7a8a2-220">[about_Objects][]</span></span>
- <span data-ttu-id="7a8a2-221">[about_Properties][]</span><span class="sxs-lookup"><span data-stu-id="7a8a2-221">[about_Properties][]</span></span>
- <span data-ttu-id="7a8a2-222">[about_Methods][]</span><span class="sxs-lookup"><span data-stu-id="7a8a2-222">[about_Methods][]</span></span>
- <span data-ttu-id="7a8a2-223">[Não conhece um cmdlet do PowerShell para iniciar ou interromper algo? Não se esqueça de verificar os métodos nos cmdlets Get][use-methods]</span><span class="sxs-lookup"><span data-stu-id="7a8a2-223">[No PowerShell Cmdlet to Start or Stop Something? Don’t Forget to Check for Methods on the Get Cmdlets][use-methods]</span></span>

<!-- link references -->
[Ferramentas de Administração de Servidor Remoto para Windows]: https://support.microsoft.com/help/2693643
[RSAT for Windows]: https://support.microsoft.com/help/2693643
[Módulos de gerenciamento do Windows]: /powershell/scripting/whats-new/module-compatibility#windows-management-modules
[Windows Management modules]: /powershell/scripting/whats-new/module-compatibility#windows-management-modules
[Get-Member]: /powershell/module/microsoft.powershell.utility/get-member
[Exibindo a estrutura do objeto (Get-Member)]: /powershell/scripting/samples/viewing-object-structure--get-member-
[Viewing Object Structure (Get-Member)]: /powershell/scripting/samples/viewing-object-structure--get-member-
[about_Objects]: /powershell/module/microsoft.powershell.core/about/about_objects
[about_Properties]: /powershell/module/microsoft.powershell.core/about/about_properties
[about_Methods]: /powershell/module/microsoft.powershell.core/about/about_methods
[use-methods]: https://mikefrobbins.com/2016/12/15/no-powershell-cmdlet-to-start-or-stop-something-dont-forget-to-check-for-methods-on-the-get-cmdlets/
[SMSS]: /sql/ssms/download-sql-server-management-studio-ssms
