---
title: Working with WMI (Trabalhar com o WMI)
description: O PowerShell teve cmdlets para trabalhar com o WMI desde o início.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 243685efa1f976ddb46a0d0efc4ed0635844606d
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438287"
---
# <a name="chapter-7---working-with-wmi"></a>Capítulo 7 – Como trabalhar com o WMI

## <a name="wmi-and-cim"></a>WMI e CIM

O PowerShell é fornecido por padrão com cmdlets para trabalhar com outras tecnologias, como WMI (Instrumentação de Gerenciamento do Windows). Há vários cmdlets WMI nativos que existem no PowerShell sem a necessidade de instalar nenhum software ou módulo adicional.

O PowerShell teve cmdlets para trabalhar com o WMI desde o início. `Get-Command` pode ser usado para determinar quais cmdlets do WMI existem no PowerShell. Os resultados a seguir são do meu computador do ambiente de laboratório do Windows 10 que está executando o PowerShell versão 5.1. Seus resultados podem diferir dependendo da versão do PowerShell que você está executando.

```powershell
Get-Command -Noun WMI*
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-WmiObject                                      3.1.0.0    Microsof...
Cmdlet          Invoke-WmiMethod                                   3.1.0.0    Microsof...
Cmdlet          Register-WmiEvent                                  3.1.0.0    Microsof...
Cmdlet          Remove-WmiObject                                   3.1.0.0    Microsof...
Cmdlet          Set-WmiInstance                                    3.1.0.0    Microsof...
```

Os cmdlets do modelo CIM (CIM) foram introduzidos na versão 3.0 do PowerShell. Os cmdlets do CIM são projetados para que possam ser usados em computadores Windows e não Windows. Os cmdlets do WMI foram preteridos, portanto, minha recomendação é usar os cmdlets do CIM, em vez dos WMI mais antigos.

Os cmdlets CIM estão todos contidos em um módulo. Para obter uma lista dos cmdlets do CIM, use `Get-Command` com o parâmetro **Module**, conforme mostrado no exemplo a seguir.

```powershell
Get-Command -Module CimCmdlets
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Export-BinaryMiLog                                 1.0.0.0    CimCmdlets
Cmdlet          Get-CimAssociatedInstance                          1.0.0.0    CimCmdlets
Cmdlet          Get-CimClass                                       1.0.0.0    CimCmdlets
Cmdlet          Get-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          Get-CimSession                                     1.0.0.0    CimCmdlets
Cmdlet          Import-BinaryMiLog                                 1.0.0.0    CimCmdlets
Cmdlet          Invoke-CimMethod                                   1.0.0.0    CimCmdlets
Cmdlet          New-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          New-CimSession                                     1.0.0.0    CimCmdlets
Cmdlet          New-CimSessionOption                               1.0.0.0    CimCmdlets
Cmdlet          Register-CimIndicationEvent                        1.0.0.0    CimCmdlets
Cmdlet          Remove-CimInstance                                 1.0.0.0    CimCmdlets
Cmdlet          Remove-CimSession                                  1.0.0.0    CimCmdlets
Cmdlet          Set-CimInstance                                    1.0.0.0    CimCmdlets
```

Os cmdlets do CIM ainda permitem que você trabalhe com o WMI, portanto, não fique confuso quando alguém fizer a instrução "Quando eu consultar o WMI com os cmdlets CIM do PowerShell…"

Como mencionei anteriormente, o WMI é uma tecnologia separada do PowerShell e você está usando apenas os cmdlets do CIM para acessar o WMI. Você pode encontrar um VBScript antigo que usa linguagem WQL para consultar o WMI, como no exemplo a seguir.

```vb
strComputer = "."
Set objWMIService = GetObject("winmgmts:" _
    & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\cimv2")

Set colBIOS = objWMIService.ExecQuery _
    ("Select * from Win32_BIOS")

For each objBIOS in colBIOS
    Wscript.Echo "Manufacturer: " & objBIOS.Manufacturer
    Wscript.Echo "Name: " & objBIOS.Name
    Wscript.Echo "Serial Number: " & objBIOS.SerialNumber
    Wscript.Echo "SMBIOS Version: " & objBIOS.SMBIOSBIOSVersion
    Wscript.Echo "Version: " & objBIOS.Version
Next
```

Você pode usar a consulta WQL desse VBScript e usá-la com o cmdlet `Get-CimInstance` sem nenhuma modificação.

```powershell
Get-CimInstance -Query 'Select * from Win32_BIOS'
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 3810-1995-1654-4615-2295-2755-89
Version           : VRTUAL - 4001628
```

Isso não é como eu normalmente consulto o WMI com o PowerShell. Mas funciona e permite que você migre facilmente os VBScripts existentes para o PowerShell. Quando começo a escrever uma única linha para consultar o WMI, uso a sintaxe a seguir.

```powershell
Get-CimInstance -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 3810-1995-1654-4615-2295-2755-89
Version           : VRTUAL - 4001628
```

Se eu quiser apenas o número de série, poderei canalizar a saída para `Select-Object` e especificar apenas a propriedade **SerialNumber**.

```powershell
Get-CimInstance -ClassName Win32_BIOS | Select-Object -Property SerialNumber
```

```Output
SerialNumber
------------
3810-1995-1654-4615-2295-2755-89
```

Por padrão, há várias propriedades que são recuperadas em segundo plano que nunca são usadas.
Talvez não importe muito ao consultar o WMI no computador local. Mas, quando você começa a consultar computadores remotos, isso representa não apenas tempo de processamento adicional para retornar essas informações, mas também informações adicionais desnecessárias das quais efetuar pull pela rede. `Get-CimInstance` tem um parâmetro **Property** que limita as informações recuperadas. Isso torna a consulta ao WMI mais eficiente.

```powershell
Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber |
Select-Object -Property SerialNumber
```

```Output
SerialNumber
------------
3810-1995-1654-4615-2295-2755-89
```

Os resultados anteriores retornaram um objeto. Para retornar uma cadeia de caracteres simples, use o parâmetro **ExpandProperty**.

```powershell
Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber |
Select-Object -ExpandProperty SerialNumber
```

```Output
3810-1995-1654-4615-2295-2755-89
```

Você também pode usar o estilo pontilhado de sintaxe para retornar uma cadeia de caracteres simples. Isso elimina a necessidade de canalizar para `Select-Object`.

```powershell
(Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber).SerialNumber
```

```Output
3810-1995-1654-4615-2295-2755-89
```

## <a name="query-remote-computers-with-the-cim-cmdlets"></a>Consultar computadores remotos com os cmdlets do CIM

Ainda estou executando o PowerShell como um administrador local que é um usuário de domínio. Quando tento consultar informações de um computador remoto usando o cmdlet `Get-CimInstance`, recebo uma mensagem de erro de acesso negado.

```powershell
Get-CimInstance -ComputerName dc01 -ClassName Win32_BIOS
```

```Output
Get-CimInstance : Access is denied.
At line:1 char:1
+ Get-CimInstance -ComputerName dc01 -ClassName Win32_BIOS
+ ``````````````````````````````````````````````````````~~
    + CategoryInfo          : PermissionDenied: (root\cimv2:Win32_BIOS:String) [Get-CimI
   nstance], CimException
    + FullyQualifiedErrorId : HRESULT 0x80070005,Microsoft.Management.Infrastructure.Cim
   Cmdlets.GetCimInstanceCommand
    + PSComputerName        : dc01
```

Muitas pessoas têm preocupações com a segurança quando se trata do PowerShell, mas a verdade é que você tem exatamente as mesmas permissões no PowerShell e na GUI. Nem mais nem menos. O problema no exemplo anterior é que o usuário que está executando o PowerShell não tem direitos para consultar informações de WMI do servidor DC01. Eu poderia reiniciar o PowerShell como um administrador de domínio, pois `Get-CimInstance` não tem um parâmetro **Credential**. Mas, confie em mim: essa não é uma boa ideia, pois tudo que eu executar do PowerShell será executado como administrador de domínio. Isso pode ser perigoso do ponto de vista da segurança, dependendo da situação.

Usando o princípio de privilégios mínimos, vou elevar a minha conta do administrador de domínio por comando usando o parâmetro **Credential**, se um comando tiver um. `Get-CimInstance` não tem um parâmetro **Credential** para que a solução neste cenário seja criar uma **CimSession** primeiro. Em seguida, uso a **CimSession**, em vez de um nome do computador, para consultar o WMI no computador remoto.

```powershell
$CimSession = New-CimSession -ComputerName dc01 -Credential (Get-Credential)
```

```Output
cmdlet Get-Credential at command pipeline position 1
Supply values for the following parameters:
Credential
```

A sessão CIM foi armazenada em uma variável chamada `$CimSession`. Observe que também especifiquei o cmdlet `Get-Credential` entre parênteses para que ele seja executado primeiro, solicitando credenciais alternativas antes de criar a nova sessão. Mostrarei outra maneira mais eficiente de especificar credenciais alternativas posteriormente neste capítulo, mas é importante entender esse conceito básico antes de torná-lo mais complicado.

A sessão CIM criada no exemplo anterior agora pode ser usada com o cmdlet `Get-CimInstance` para consultar as informações do BIOS do WMI no computador remoto.

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 0986-6980-3916-0512-6608-8243-13
Version           : VRTUAL - 4001628
PSComputerName    : dc01
```

Há vários benefícios adicionais de usar sessões CIM, em vez de apenas especificar um nome do computador. Ao executar várias consultas no mesmo computador, usar uma sessão CIM é mais eficiente do que usar o nome do computador para cada consulta. A criação de uma sessão CIM só configura a conexão uma vez.
Em seguida, várias consultas usam essa mesma sessão para recuperar informações. Usar o nome do computador requer que os cmdlets configurem e derrubem a conexão com cada consulta individual.

O cmdlet `Get-CimInstance` usa o protocolo WSMan por padrão, o que significa que o computador remoto precisa do PowerShell versão 3.0 ou superior para se conectar. Na verdade, não é a versão do PowerShell que importa, é a versão da pilha. A versão da pilha pode ser determinada usando o cmdlet `Test-WSMan`.
Ele precisa ser a versão 3.0. Essa é a versão que você encontrará com o PowerShell versão 3.0 e superior.

```powershell
Test-WSMan -ComputerName dc01
```

```Output
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd
ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd
ProductVendor   : Microsoft Corporation
ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 3.0
```

Os cmdlets mais antigos do WMI usam o protocolo DCOM, que é compatível com versões mais antigas do Windows. Mas o DCOM é normalmente bloqueado pelo firewall em versões mais recentes do Windows. O cmdlet `New-CimSessionOption` permite que você crie uma conexão de protocolo DCOM para uso com `New-CimSession`. Isso permite que o cmdlet `Get-CimInstance` seja usado para se comunicar com versões do Windows tão antigas quanto o Windows Server 2000. Isso também significa que o PowerShell não é necessário no computador remoto ao usar o cmdlet `Get-CimInstance` com uma CimSession configurada para usar o protocolo DCOM.

Crie a opção de protocolo DCOM usando o cmdlet `New-CimSessionOption` e armazene-a em uma variável.

```powershell
$DCOM = New-CimSessionOption -Protocol Dcom
```

Para eficiência, você pode armazenar seu administrador de domínio ou credenciais elevadas em uma variável para que você não precise inseri-las constantemente para cada comando.

```powershell
$Cred = Get-Credential
```

```Output
cmdlet Get-Credential at command pipeline position 1
Supply values for the following parameters:
Credential
```

Tenho um servidor chamado SQL03 que executa o Windows Server 2008 (não R2). É o sistema operacional Windows Server mais recente que não tem o PowerShell instalado por padrão.

Crie uma **CimSession** para SQL03 usando o protocolo DCOM.

```powershell
$CimSession = New-CimSession -ComputerName sql03 -SessionOption $DCOM -Credential $Cred
```

Observe que, no comando anterior, desta vez eu especifiquei a variável chamada `$Cred` como o valor do parâmetro **Credential**, em vez de precisar inseri-las manualmente outra vez.

A saída da consulta é a mesma, não importa o protocolo subjacente que está sendo usado.

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 7237-7483-8873-8926-7271-5004-86
Version           : VRTUAL - 4001628
PSComputerName    : sql03
```

O cmdlet `Get-CimSession` é usado para ver quais **CimSessions** estão atualmente conectadas e quais protocolos elas estão usando.

```powershell
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : 80742787-e38e-41b1-a7d7-fa1369cf1402
ComputerName : dc01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : 8fcabd81-43cf-4682-bd53-ccce1e24aecb
ComputerName : sql03
Protocol     : DCOM
```

Recupere e armazene as duas **CimSessions** criadas anteriormente em uma variável chamada `$CimSession`.

```powershell
$CimSession = Get-CimSession
```

Confira ambos os computadores com um comando, um usando o protocolo WSMan e o outro com DCOM.

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 0986-6980-3916-0512-6608-8243-13
Version           : VRTUAL - 4001628
PSComputerName    : dc01

SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 7237-7483-8873-8926-7271-5004-86
Version           : VRTUAL - 4001628
PSComputerName    : sql03
```

Escrevi vários artigos de blog sobre os cmdlets do WMI e do CIM. Um dos mais úteis é sobre uma função que criei para determinar automaticamente se WSMan ou DCOM deve ser usado e configurar a sessão CIM automaticamente sem precisar descobrir manualmente qual delas. Esse artigo de blog é intitulado [Função do PowerShell para criar CimSessions a computadores remotos com fallback para DCOM][].

Quando você terminar com as sessões CIM, deverá removê-las com o cmdlet `Remove-CimSession`. Para remover todas as sessões CIM, basta canalizar `Get-CimSession` para `Remove-CimSession`.

```powershell
Get-CimSession | Remove-CimSession
```

## <a name="summary"></a>Resumo

Neste capítulo, você aprendeu a usar o PowerShell para trabalhar com o WMI em computadores locais e remotos. Você também aprendeu a usar os cmdlets do CIM para trabalhar com computadores remotos com o protocolo WSMan ou DCOM.

## <a name="review"></a>Revisão

1. Qual é a diferença entre os cmdlets do WMI e do CIM?
1. Por padrão, que protocolo o cmdlet `Get-CimInstance` usa?
1. Quais são alguns dos benefícios de usar uma sessão CIM, em vez de especificar um nome do computador com `Get-CimInstance`?
1. Como especificar um protocolo alternativo diferente do padrão para uso com `Get-CimInstance`?
1. Como fechar ou remover sessões CIM?

## <a name="recommended-reading"></a>Leitura recomendada

- [about_WMI][]
- [about_WMI_Cmdlets][]
- [about_WQL][]
- [Módulo CimCmdlets][]
- [Vídeo: Como usar cmdlets CIM e sessões CIM][]

<!-- link references -->
[about_WMI]: /powershell/module/microsoft.powershell.core/about/about_wmi
[about_WMI_Cmdlets]: /powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets
[about_WQL]: /powershell/module/microsoft.powershell.core/about/about_wql
[Módulo CimCmdlets]: /powershell/module/cimcmdlets/
[Vídeo: Como usar cmdlets CIM e sessões CIM]: https://mikefrobbins.com/2013/09/12/phillyposh-user-group-meeting-presentation-follow-up-powershell-second-hop-problem-with-cimsessions/
[Função do PowerShell para criar CimSessions a computadores remotos com fallback para DCOM]: https://mikefrobbins.com/2014/08/28/powershell-function-to-create-cimsessions-to-remote-computers-with-fallback-to-dcom/
