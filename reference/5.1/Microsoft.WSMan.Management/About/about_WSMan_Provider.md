---
description: WSMan
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_wsman_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor WSMan
ms.openlocfilehash: 962684fceaa8fdf16985df56fb4fcdb830bb828b
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196549"
---
# <a name="wsman-provider"></a>Provedor WSMan

## <a name="provider-name"></a>Nome do provedor

WSMan

## <a name="drives"></a>Unidades

`WSMan:`

## <a name="short-description"></a>Descrição breve

Fornece acesso a serviços Web para obter informações de configuração de gerenciamento (WS-Management).

## <a name="detailed-description"></a>Descrição detalhada

O provedor **WSMan** para PowerShell permite que você adicione, altere, apague e exclua WS-Management dados de configuração em computadores locais ou remotos.

O provedor **WSMan** expõe uma unidade do PowerShell com uma estrutura de diretório que corresponde a um agrupamento lógico de definições de configuração de WS-Management. Esses agrupamentos são conhecidos como contêineres.

A partir do Windows PowerShell 3,0, o provedor **WSMan** foi atualizado para dar suporte a novas propriedades para configurações de sessão, como **OutputBufferingMode** . As configurações de sessão aparecem como itens no diretório de plug-in da `WSMan:` unidade e as propriedades aparecem como itens em cada configuração de sessão.

O provedor **WSMan** dá suporte aos seguintes cmdlets, que são abordados neste artigo.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)

> [!NOTE]
> Você pode usar os comandos na `WSMan:` unidade para alterar os valores das novas propriedades. No entanto, você não pode usar a `WSMan:` unidade no PowerShell 2,0 para alterar as propriedades introduzidas no Windows PowerShell 3,0.
> Embora nenhum erro seja gerado, os comandos não são efetivos para alterar essas configurações, use a unidade **WSMan** no Windows PowerShell 3,0.

### <a name="organization-of-the-wsman-drive"></a>Organização da unidade WSMan:

- **Cliente** : você pode configurar vários aspectos do cliente WS-Management. As informações de configuração são armazenadas no Registro.

- **Serviço** : você pode configurar vários aspectos do serviço de WS-Management.
  As informações de configuração são armazenadas no Registro.
  > [!NOTE]
  > A configuração do serviço, às vezes, é chamada de configuração Server.

- **Shell** : você pode configurar vários aspectos do WS-Management Shell, como a configuração para permitir acesso de shell remoto ( **AllowRemoteShellAccess** ) e o número máximo de usuários simultâneos permitidos ( **MaxConcurrentUsers** ).

- **Ouvinte** : você pode criar e configurar um ouvinte. Um ouvinte é um serviço de gerenciamento que implementa o protocolo WS-Management para enviar e receber mensagens.

- **Plugin** : os plug-ins são carregados e usados pelo serviço de WS-Management para fornecer várias funções. Por padrão, o PowerShell fornece três plug-ins:
  - O plug-in de encaminhamento de eventos.
  - O plug-in do Microsoft. PowerShell.
  - O plug-in do provedor de Instrumentação de Gerenciamento do Windows (WMI).
  Esses três plug-ins dão suporte ao encaminhamento de eventos, à configuração e ao acesso WMI.

- **ClientCertificate** : você pode criar e configurar um certificado de cliente.
  Um certificado de cliente é usado quando o cliente do WS-Management está configurado para usar a autenticação de certificado.

### <a name="directory-hierarchy-of-the-wsman-provider"></a>Hierarquia de diretórios do provedor WSMan

A hierarquia de diretórios do provedor WSMan para o computador local é a seguinte.

```
WSMan:\localhost
--- Client
--- Service
--- Shell
--- Listener
------ <Specific_Listener>
--- Plugin
------ Event Forwarding Plugin
--------- InitializationParameters
--------- Resources
------------ Security
------ Microsoft.Powershell
--------- InitializationParameters
--------- Resources
------------ Security
------ WMI Provider
--------- InitializationParameters
--------- Resources
------------ Security
--- ClientCertificate
```

A hierarquia de diretórios do provedor WSMan para um computador remoto é a mesmo que para um computador local. No entanto, para acessar as configurações de um computador remoto, você precisa estabelecer uma conexão com o computador remoto usando [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan). Depois que uma conexão é feita para um computador remoto, o nome do computador remoto aparece no provedor.

```
WSMan:\<Remote_Computer_Name>
```

## <a name="navigating-the-wsman-drive"></a>Navegando na unidade WSMan:

Esse comando usa o `Set-Location` cmdlet para alterar o local atual para a `WSMan:` unidade.

```powershell
Set-Location WSMan:
```

Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade. Por exemplo, digite.

```powershell
Set-Location C:
```

### <a name="navigating-to-a-remote-system-store-location"></a>Navegando para um local de armazenamento do sistema remoto

Esse comando usa o `Set-Location` comando para alterar o local atual para o local raiz no local de armazenamento do sistema remoto. Use uma barra invertida ou uma barra invertida `\` `/` para indicar um nível da `WSMan:` unidade.

```powershell
Set-Location -Path  WSMan:\SERVER01
```

> [!NOTE]
> O comando acima pressupõe que uma conexão com o sistema remoto já exista.

## <a name="displaying-the-contents-of-the-wsman-drive"></a>Exibindo o conteúdo da unidade WSMan:

Esse comando usa o `Get-Childitem` cmdlet para exibir os repositórios de WS-Management no local de armazenamento do localhost.

```powershell
Get-ChildItem -path WSMan:\Localhost
```

Se você estiver na `WSMan:` unidade, poderá omitir o nome da unidade.

Esse comando usa o `Get-Childitem` cmdlet para exibir os repositórios de WS-Management no local de armazenamento "Server01" do computador remoto.

```powershell
Get-ChildItem -path WSMan:\SERVER01
```

> [!NOTE]
> O comando acima pressupõe que uma conexão com o sistema remoto já exista.

## <a name="setting-the-value-of-items-in-the--wsman-drive"></a>Definindo o valor de itens na unidade WSMAN:

Você pode usar o `Set-Item` cmdlet para alterar as definições de configuração na `WSMAN` unidade. O exemplo a seguir define o valor **TrustedHosts** para aceitar todos os hosts com o sufixo "contoso.com".

```powershell
# You do not need to specify the -Path parameter name when using Set-Item.
PS WSMAN:\localhost\Client> Set-Item .\TrustedHosts -Value "*.contoso.com"
```

O `Set-Item` cmdlet dá suporte a um parâmetro adicional `-Concatenate` que acrescenta um valor em vez de alterá-lo. O exemplo a seguir acrescentará um novo valor "*. domain2.com" ao valor antigo armazenado em `TrustedHost:`

```powershell
Set-Item WSMAN:\localhost\Client\TrustedHosts *.domain2.com -Concatenate
```

## <a name="creating-items-in-the-wsman-drive"></a>Criando itens na unidade WSMAN:

### <a name="creating-a-new-listener"></a>Criando um novo ouvinte

O `New-Item` cmdlet cria itens em uma unidade de provedor. Cada provedor tem diferentes tipos de item que você pode criar. Na `WSMAN:` unidade, você pode criar *ouvintes* que você configura para receber e responder a solicitações remotas. O comando a seguir cria um novo ouvinte HTTP usando o `New-Item` cmdlet.

```powershell
New-Item -Path WSMan:\localhost\Listener -Address * -Transport HTTP -force
```

### <a name="creating-a-new-plug-in"></a>Criando um novo plug-in

Este comando cria (registra) um plug-in para o serviço WS-Management.

```powershell
New-Item -Path WSMan:\localhost\Plugin `
         -Plugin TestPlugin `
         -FileName %systemroot%\system32\WsmWmiPl.dll `
         -Resource http://schemas.dmtf.org/wbem/wscim/2/cim-schema `
         -SDKVersion 1 `
         -Capability "Get","Put","Invoke","Enumerate" `
         -XMLRenderingType text
```

### <a name="creating-a-new-resource-entry"></a>Criando uma nova entrada de recurso

Esse comando cria uma entrada de recurso no diretório de recursos de um TestPlugin. Esse comando pressupõe que um TestPlugin foi criado usando um comando separado.

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\Resources `
         -ResourceUri http://schemas.dmtf.org/wbem/wscim/3/cim-schema `
         -Capability "Enumerate"

```

### <a name="creating-a-new-security-entry-for-a-resource"></a>Criando uma nova entrada de segurança para um recurso

Este comando cria uma entrada de segurança no diretório Security do Resource_5967683 (um recurso específico). Esse comando pressupõe que a entrada de recurso tenha sido criada usando um comando separado.

```powershell
$path = "WSMan:\localhost\Plugin\TestPlugin\Resources\Resource_5967683"
New-Item -Path $path\Security `
         -Sddl "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GWGX;;;WD)"
```

### <a name="creating-a-new-client-certificate"></a>Criando um novo certificado de cliente

Esse comando cria a entrada **ClientCertificate** que pode ser usada pelo cliente de WS-Management. O novo **ClientCertificate** aparecerá no diretório **ClientCertificate** como "ClientCertificate_1234567890". Todos os parâmetros são obrigatórios. O **emissor** precisa ser impressão digital do certificado dos emissores.

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* `
         -Credential $cred;
```

### <a name="creating-a-new-initialization-parameter"></a>Criando um novo parâmetro de inicialização

Este comando cria um parâmetro de inicialização chamado "testparametername" no diretório "InitializationParameters". Esse comando pressupõe que "TestPlugin" foi criado usando um comando separado.

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\InitializationParameters `
         -ParamName testparametername `
         -ParamValue testparametervalue
```

## <a name="dynamic-parameters"></a>Parâmetros dinâmicos

Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.

### <a name="address-string"></a>Address \<String\>

Especifica o endereço para o qual este ouvinte foi criado. O valor pode ser um dos seguintes:

- A cadeia de caracteres literal "*". (O caractere curinga ( `*` ) faz com que o comando vincule todos os endereços IP em todos os adaptadores de rede.)
- A cadeia de caracteres literal "IP:" seguida por um endereço IP válido em um formato decimal com ponto de IPv4 ou no formato hexadecimal clonado de IPv6.
- A cadeia de caracteres literal "MAC:" seguida pelo endereço MAC de um adaptador.
  Por exemplo: MAC: 32-a3-58 -90-ser-CC.

> [!NOTE]
> O valor Address é definido durante a criação de um Ouvinte.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="capability-enumeration"></a>Capability \<Enumeration\>

Ao trabalhar com *plug-ins,* esse parâmetro especifica uma operação com suporte neste Uniform Resource Identifier (URI). Você precisa criar uma entrada para cada tipo de operação ao qual o URI dá suporte. Você pode especificar qualquer atributo válido para uma determinada operação, se a operação oferecer suporte a ela.

Esses atributos incluem **SupportsFiltering** e **SupportsFragment** .

- **Create** : há suporte para operações Create no URI.
  - O atributo **SupportFragment**  será usado se a operação de criação der suporte ao conceito.
  - O atributo **SUPPORTFILTERING** não é válido para operações Create e deve ser definido como "false".
  > [!NOTE]
  > Essa operação não é válida para um URI se também há suporte para operações de Shell.
- **Delete** : há suporte para operações Delete no URI.
  - O atributo **SupportFragment** será usado se a operação de exclusão der suporte ao conceito.
  - O atributo **SUPPORTFILTERING** não é válido para operações Delete e deve ser definido como "false".
  > [!NOTE]
  > Essa operação não é válida para um URI se também há suporte para operações de Shell.
- **Enumerar** : as operações de enumeração têm suporte no URI.
  - O atributo **SUPPORTFRAGMENT** não tem suporte para operações de enumeração e deve ser definido como false.
  - O atributo **SupportFiltering** é válido e, se o plug-in der suporte à filtragem, esse atributo deverá ser definido como "true".
  > [!NOTE]
  > Essa operação não é válida para um URI se também há suporte para operações de Shell.
- **Get** : há suporte para operações Get no URI.
  - O atributo **SupportFragment** será usado se a operação get der suporte ao conceito.
  - O atributo **SUPPORTFILTERING** não é válido para operações Get e deve ser definido como "false".
  > [!NOTE]
  > Essa operação não é válida para um URI se também há suporte para operações de Shell.
- As operações **Invoke** : Invoke têm suporte no URI.
  - O atributo **SupportFragment** não tem suporte para operações Invoke e deve ser definido como false.
  - O atributo **SupportFiltering** não é válido e deve ser definido como "false".
  > [!NOTE]
  > Essa operação não é válida para um URI se também há suporte para operações de Shell.
- **Put** : as operações Put têm suporte no URI.
  - O atributo **SupportFragment** será usado se a operação Put der suporte ao conceito.
  - O atributo **SupportFiltering** não é válido para operações Put e deve ser definido como "false".
  > [!NOTE]
  > Essa operação não é válida para um URI se também há suporte para operações de Shell.
- **Assinar** : há suporte para operações de assinatura no URI.
  - O atributo **SupportFragment** não tem suporte para operações de assinatura e deve ser definido como false.
  - O atributo **SupportFiltering** não é válido para operações de assinatura e deve ser definido como "false".
  > [!NOTE]
  > Essa operação não é válida para um URI se também há suporte para operações de Shell.
- **Shell** : há suporte para operações de Shell no URI.
  - O atributo **SupportFragment** não tem suporte para operações de shell e deve ser definido como "false".
  - O atributo **SupportFiltering** não é válido para operações de shell e deve ser definido como "false".
  > [!NOTE]
  > Essa operação não será válida para um URI se qualquer outra operação também tiver suporte.
  > [!NOTE]
  > Se uma operação Shell estiver configurada para uma operação URI, Get, Put, Create, Delete, Invoke e Enumerate será processada internamente no serviço WS-Management (WinRM) para gerenciar os shells. Como resultado, o plug-in não pode manipular as operações.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="certificatethumbprint-string"></a>CertificateThumbprint \<String\>

Especifica a impressão digital do certificado de serviço.

Esse valor representa a cadeia de caracteres de valores de dois dígitos hexadecimais no campo Impressão digital do certificado. Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação. Os certificados são utilizados na autenticação baseada em certificado do cliente. Eles podem ser mapeados somente para contas de usuário locais; eles não funcionam com contas de domínio. Para obter uma impressão digital do certificado, use os `Get-Item` `Get-ChildItem` cmdlets ou na `Cert:` unidade do PowerShell.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="enabled-boolean"></a>Enabled \<Boolean\>

Especifica se o ouvinte está habilitado ou desabilitado. O padrão é True.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="filename-plugin-string"></a>FileName (Plugin) \<String\>

Especifica o nome do arquivo do plug-in de operações. Todas as variáveis de ambiente colocadas nessa entrada serão expandidas no contexto dos usuários quando uma solicitação for recebida. Como cada usuário pode ter uma versão diferente da mesma variável de ambiente, cada usuário poderia ter um plug-in diferente. Essa entrada não pode ficar em branco e deve apontar para um plug-in válido.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="hostname-string"></a>HostName \<String\>

Especifica o nome de host do computador no qual o serviço WS-Management (WinRM) está em execução.

O valor deve ser um nome de domínio totalmente qualificado, uma cadeia de caracteres literal IPv4 ou IPv6 ou um caractere curinga.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="issuer-string"></a>Issuer \<String\>

Especifica o nome da autoridade de certificação que emitiu o certificado.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="plugin--ws-management-plug-ins-are-native-dynamic-link-libraries-dlls"></a>\<\>Plug-ins de WS-Management do plug-in são DLLs (bibliotecas de vínculo dinâmico) nativas

que se conectam e estendem a funcionalidade do WS-Management. A API de plug-in do WSW-Management fornece funcionalidade que permite que um usuário escreva plug-ins implementando determinadas APIs para operações e URIs de recursos com suporte. Depois que os plug-ins estiverem configurados para o serviço WS-Management (WinRM) ou para Serviços de Informações da Internet (IIS), os plug-ins são carregados no host WS-Management ou no host IIS, respectivamente. As solicitações remotas são roteadas para esses pontos de entrada de plug-in para executar operações.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="port-unsigned-short-integer"></a>Port \<Unsigned Short Integer\>

Especifica a porta TCP para a qual este ouvinte é criado. Você pode especificar qualquer valor entre 1 e 65535.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a>Resource \<String\>

Especifica um ponto de extremidade que representa um tipo distinto de valor ou operação de gerenciamento. Um serviço expõe um ou mais recursos, e alguns recursos podem ter mais de uma instância. Um recurso de gerenciamento é semelhante a uma classe WMI ou a uma tabela de banco de dados e uma instância é semelhante a uma instância da classe ou a uma linha na tabela. Por exemplo, a classe **Win32_LogicalDisk** representa um recurso. `Win32_LogicalDisk="C:\\"` é uma instância específica do recurso.

Um identificador de recurso uniforme (URI) contém um prefixo e um caminho para um recurso.
Por exemplo:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a>Resource \<String\>

Especifica o Uniform Resource identificador (URI) que identifica um tipo de recurso, como um disco ou um processo, em um computador específico.

Um URI consiste em um prefixo e um caminho para um recurso. Por exemplo:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sdkversion-string"></a>SDKVersion \<String\>

Especifica a versão do SDK do plug-in do WS-Management. O único valor válido é
1.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="subject-string"></a>Subject \<String\>

Especifica a entidade que é identificada pelo certificado.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="transport-string"></a>Transport \<String\>

Especifica o transporte a ser usado para enviar e receber respostas e solicitações do protocolo WS-Management. O valor deve ser HTTP ou HTTPS.

Observação: o valor de transporte é definido durante a criação de um ouvinte.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="uri-string"></a>URI \<String\>

Identifica o URI para o qual o acesso é autorizado com base no valor do parâmetro Sddl.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="urlprefix-string"></a>URLPrefix \<String\>

Um prefixo de URL no qual aceitar solicitações de HTTP ou HTTPS. Esta é uma cadeia de caracteres que contém apenas os caracteres `[a-z]` , `[A-Z]` ,, `[9-0]` sublinhado ( `_` ) e barra invertida ( `/` ). A cadeia de caracteres não deve começar com ou terminar com uma barra invertida ( `/` ). Por exemplo, se o nome do computador for "SampleComputer", o cliente WS-Management especificaria `http://SampleMachine/URLPrefix` no endereço de destino.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="value-string"></a>Value \<String\>

Especifica o valor de um parâmetro de inicialização, que é um valor de plug-in específico usado para especificar opções de configuração.

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="xmlrenderingtype-string"></a>XMLRenderingType \<String\>

Especifica o formato em que o XML é passado aos plug-ins por meio do objeto **WSMAN_DATA** . Os seguintes valores são válidos:

- Text: os dados XML de entrada estão contidos em uma estrutura de **WSMAN_DATA_TYPE_TEXT** , que representa o XML como um buffer de memória **PCWSTR** .
- XMLReader: os dados XML de entrada estão contidos em uma estrutura de **WSMAN_DATA_TYPE_WS_XML_READER** , que representa o XML como um objeto **XmlReader** , que é definido no arquivo de cabeçalho "WebServices. h".

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a>Usando o pipeline

Os cmdlets do provedor aceitam a entrada do pipeline. Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.
Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.

## <a name="getting-help"></a>Obtendo ajuda

A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.

Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path wsman:
```

## <a name="see-also"></a>Confira também

[about_Providers](../../Microsoft.PowerShell.Core/About/about_Providers.md)
