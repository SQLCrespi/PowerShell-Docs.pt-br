---
description: Descreve os arquivos de configuração de sessão, que são usados em uma configuração de sessão (também conhecida como "ponto de extremidade") para definir o ambiente de sessões que usam a configuração de sessão.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configuration_files?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configuration_Files
ms.openlocfilehash: 198a0aeb667c3c947bc7e202bc3c0d9832195b91
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195966"
---
# <a name="about-session-configuration-files"></a>Sobre arquivos de configuração de sessão

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve os arquivos de configuração de sessão, que são usados em uma configuração de sessão (também conhecida como "ponto de extremidade") para definir o ambiente de sessões que usam a configuração de sessão.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Um "arquivo de configuração de sessão" é um arquivo de texto com uma extensão de nome de arquivo. PSSC que contém uma tabela de hash de valores e propriedades de configuração de sessão. Você pode usar um arquivo de configuração de sessão para definir as propriedades de uma configuração de sessão. Isso define o ambiente de todas as sessões do Windows PowerShell que usam essa configuração de sessão.

Os arquivos de configuração de sessão facilitam a criação de configurações de sessão personalizadas sem usar módulos ou scripts C# complexos.

Uma "configuração de sessão" ou "ponto de extremidade" é uma coleção de configurações do computador local que determinam coisas como quais usuários podem criar sessões no computador; quais comandos os usuários podem executar nessas sessões; e se a sessão deve ser executada como uma conta virtual privilegiada. Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](about_Session_Configurations.md).

As configurações de sessão foram introduzidas no Windows PowerShell 2,0, e os arquivos de configuração de sessão foram introduzidos no Windows PowerShell 3,0. Você deve usar o Windows PowerShell 3,0 para incluir um arquivo de configuração de sessão em uma configuração de sessão. No entanto, os usuários do Windows PowerShell 2,0 (e posterior) são afetados pelas configurações na configuração de sessão.

## <a name="creating-custom-sessions"></a>Criando sessões personalizadas

Você pode personalizar muitos recursos de uma sessão do Windows PowerShell especificando propriedades de sessão em uma configuração de sessão. Você pode personalizar uma sessão escrevendo um programa em C# que define um runspace personalizado ou pode usar um arquivo de configuração de sessão para definir as propriedades das sessões criadas usando a configuração de sessão. Como regra geral, é mais fácil usar o arquivo de configuração de sessão do que escrever um programa em C#.

Você pode usar um arquivo de configuração de sessão para criar itens como sessões totalmente funcionais para usuários altamente confiáveis; sessões bloqueadas que permitem o acesso mínimo; sessões projetadas para particular e que contêm apenas os módulos necessários para essas tarefas; e sessões em que os usuários sem privilégios só podem executar comandos específicos como uma conta com privilégios.

Além disso, você pode gerenciar se os usuários da sessão podem usar elementos de linguagem do Windows PowerShell, como blocos de script, ou se eles só podem executar comandos. Você pode gerenciar a versão de usuários do Windows PowerShell que podem ser executados na sessão; gerenciar quais módulos são importados para a sessão; e gerenciar quais cmdlets, funções e aliases de sessão os usuários podem executar. Ao usar o campo RoleDefinitions, você pode fornecer aos usuários recursos diferentes na sessão com base na associação de grupo.

Para obter mais informações sobre RoleDefinitions e como definir esse valor, consulte o tópico da ajuda para o cmdlet New-PSRoleCapabilityFile.

## <a name="creating-a-session-configuration-file"></a>Criando um arquivo de configuração de sessão

A maneira mais fácil de criar um arquivo de configuração de sessão é usando o cmdlet New-PSSessionConfigurationFile. Esse cmdlet gera um arquivo que usa a sintaxe e o formato corretos e que verifica automaticamente muitos dos valores de Propriedade do arquivo de configuração.

Para obter descrições detalhadas das propriedades que podem ser definidas em um arquivo de configuração de sessão, consulte o tópico da ajuda para o cmdlet New-PSSessionConfigurationFile.

O comando a seguir cria um arquivo de configuração de sessão que usa os valores padrão. O arquivo de configuração resultante usa apenas os valores padrão porque nenhum parâmetro diferente do parâmetro de caminho (que especifica o caminho do arquivo) está incluído:

```powershell
New-PSSessionConfigurationFile -Path .\Defaults.pssc
```

Para exibir o novo arquivo de configuração em seu editor de texto padrão, use o seguinte comando:

```powershell
Invoke-Item -Path .\Defaults.pssc
```

Para criar uma configuração de sessão para sessões em que o usuário pode executar comandos, mas não usar outros elementos da linguagem Windows PowerShell, digite:

```powershell
New-PSSessionConfigurationFile -LanguageMode NoLanguage
-Path .\NoLanguage.pssc
```

No comando anterior, definir o parâmetro Languagemode como nolanguage impede que os usuários façam coisas como gravar ou executar scripts ou usar variáveis.

Para criar uma configuração de sessão para sessões nas quais os usuários podem usar apenas cmdlets Get, digite:

```powershell
New-PSSessionConfigurationFile -VisibleCmdlets Get-*
-Path .\GetSessions.pssc
```

No exemplo anterior, definir o parâmetro VisibleCmdlets como Get-* limita os usuários aos cmdlets que têm nomes que começam com o valor de cadeia de caracteres "Get-".

Para criar uma configuração de sessão para sessões executadas em uma conta virtual privilegiada em vez das credenciais do usuário, digite:

```powershell
New-PSSessionConfigurationFile -RunAsVirtualAccount
-Path .\VirtualAccount.pssc
```

Para criar uma configuração de sessão para sessões em que os comandos visíveis para o usuário são especificados em um arquivo de recursos de função, digite:

```powershell
New-PSSessionConfigurationFile -RoleDefinitions
@{ 'CONTOSO\User' = @{ RoleCapabilities = 'Maintenance' }}
-Path .\Maintenance.pssc
```

### <a name="using-a-session-configuration-file"></a>Usando um arquivo de configuração de sessão

Você pode incluir um arquivo de configuração de sessão ao criar uma configuração de sessão ou adicionar. você pode adicionar um arquivo à configuração de sessão posteriormente.

Para incluir um arquivo de configuração de sessão ao criar uma configuração de sessão, use o parâmetro Path do cmdlet Register-PSSessionConfiguration.

Por exemplo, o comando a seguir usa o arquivo nolanguage. PSSC quando ele cria uma configuração de sessão nolanguage.

```powershell
Register-PSSessionConfiguration -Name NoLanguage
-Path .\NoLanguage.pssc
```

Quando uma nova sessão nolanguage for iniciada, os usuários terão acesso apenas aos comandos do Windows PowerShell.

Para adicionar um arquivo de configuração de sessão a uma configuração de sessão existente, use o cmdlet Set-PSSessionConfiguration e o parâmetro Path. Isso afeta todas as novas sessões criadas com a configuração de sessão especificada. Observe que o cmdlet Set-PSSessionConfiguration altera a sessão em si e não modifica o arquivo de configuração de sessão.

Por exemplo, o comando a seguir adiciona o arquivo nolanguage. PSSC à configuração de sessão LockedDown.

```powershell
Set-PSSessionConfiguration -Name LockedDown
-Path .\NoLanguage.pssc
```

Quando os usuários usam a configuração de sessão LockedDown para criar uma sessão, eles poderão executar cmdlets, mas não poderão criar ou usar variáveis, atribuir valores ou usar outros elementos de linguagem do Windows PowerShell.

O comando a seguir usa o cmdlet New-PSSession para criar uma sessão no computador Srv01 que usa a configuração de sessão LockedDown, salvando uma referência de objeto na sessão na variável $s. A ACL (lista de controle de acesso) da configuração de sessão determina quem pode usá-la para criar uma sessão.

```powershell
$s = New-PSSession -ComputerName Srv01
-ConfigurationName LockedDown
```

Como as restrições nolanguage foram adicionadas à configuração de sessão do LockedDown, os usuários em sessões do LockedDown só poderão executar os comandos e cmdlets do Windows PowerShell. Por exemplo, os dois comandos a seguir usam o cmdlet Invoke-Command para executar comandos na sessão referenciada na variável $s. O primeiro comando, que executa o cmdlet Get-UICulture e não usa nenhuma variável, é bem sucedido. O segundo comando, que obtém o valor da variável $PSUICulture, falha.

```
Invoke-Command -Session $s {Get-UICulture}
en-US

Invoke-Command -Session $s {$PSUICulture}
The syntax is not supported by this runspace. This might be
because it is in no-language mode.
+ CategoryInfo          : ParserError: ($PSUICulture:String) [],
ParseException
+ FullyQualifiedErrorId : ScriptsNotAllowed
```

## <a name="editing-a-session-configuration-file"></a>Editando um arquivo de configuração de sessão

Todas as configurações em uma configuração de sessão, exceto para RunAsVirtualAccount e RunAsVirtualAccountGroups, podem ser modificadas editando o arquivo de configuração de sessão usado pela configuração de sessão. Para fazer isso, comece localizando a cópia ativa do arquivo de configuração de sessão.

Quando você usa um arquivo de configuração de sessão em uma configuração de sessão, o Windows PowerShell cria uma cópia ativa do arquivo de configuração de sessão e a armazena no \$ \\ diretório pshome SessionConfig no computador local.

O local da cópia ativa de um arquivo de configuração de sessão é armazenado na propriedade ConfigFilePath do objeto de configuração de sessão.

O comando a seguir obtém o local do arquivo de configuração de sessão para a configuração da sessão nolanguage.

```powershell
(Get-PSSessionConfiguration -Name NoLanguage).ConfigFilePath
```

Esse comando retorna um caminho de arquivo semelhante ao seguinte:

```
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

Você pode editar o arquivo. PSSC em qualquer editor de texto. Depois que o arquivo for salvo, ele será empregado por novas sessões que usam a configuração de sessão.

Se precisar modificar as configurações de RunAsVirtualAccount ou RunAsVirtualAccountGroups, você deverá cancelar o registro da configuração de sessão e registrar novamente um arquivo de configuração de sessão que inclui os valores editados.

## <a name="testing-a-session-configuration-file"></a>Testando um arquivo de configuração de sessão

Use o cmdlet Test-PSSessionConfigurationFile para testar arquivos de configuração de sessão editados manualmente. Isso é importante: se a sintaxe do arquivo e os valores não forem válidos, os usuários não poderão usar a configuração de sessão para criar uma sessão.

Por exemplo, o comando a seguir testa o arquivo de configuração de sessão ativa da configuração de sessão nolanguage.

```powershell
Test-PSSessionConfigurationFile -Path C:\WINDOWS\System32\
WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

Se a sintaxe e os valores no arquivo de configuração forem válidos Test-PSSessionConfigurationFile retornará true. Se a sintaxe e os valores não forem válidos, o cmdlet retornará false.

Você pode usar Test-PSSessionConfigurationFile para testar qualquer arquivo de configuração de sessão, incluindo os arquivos que o cmdlet New-PSSessionConfiguration cria. Para obter mais informações, consulte o tópico da ajuda para o cmdlet Test-PSSessionConfigurationFile.

## <a name="removing-a-session-configuration-file"></a>Removendo um arquivo de configuração de sessão

Não é possível remover um arquivo de configuração de sessão de uma configuração de sessão.
No entanto, você pode substituir o arquivo por um novo arquivo que usa as configurações padrão. Isso efetivamente cancela as configurações usadas pelo arquivo de configuração original.

Para substituir um arquivo de configuração de sessão, crie um novo arquivo de configuração de sessão que use as configurações padrão e, em seguida, use o cmdlet Set-PSSessionConfiguration para substituir o arquivo de configuração de sessão Personalizada pelo novo arquivo.

Por exemplo, os comandos a seguir criam um arquivo de configuração de sessão padrão e substituem o arquivo de configuração de sessão ativa na configuração de sessão nolanguage.

```powershell
New-PSSessionConfigurationFile -Path .\Default.pssc
Set-PSSessionConfiguration -Name NoLanguage
-Path .\Default.pssc
```

Quando esses comandos forem concluídos, a configuração da sessão nolanguage realmente fornecerá suporte completo a idiomas (a configuração padrão) para todas as sessões criadas com essa configuração de sessão.

Exibindo as propriedades de uma configuração de sessão os objetos de configuração de sessão que representam as configurações de sessão usando arquivos de configuração de sessão têm propriedades adicionais que facilitam a descoberta e a análise da configuração da sessão. (Observe que o nome do tipo mostrado abaixo inclui uma definição de exibição formatada.) Você pode exibir as propriedades executando o cmdlet Get-PSSessionConfiguration e canalizando os dados retornados para o cmdlet Get-Member:

```powershell
Get-PSSessionConfiguration NoLanguage | Get-Member
```

```output
TypeName: Microsoft.PowerShell.Commands.PSSessionConfigurationCommands
#PSSessionConfiguration

Name                          MemberType     Definition
----                          ----------     ----------
Equals                        Method         bool Equals(System.O...
GetHashCode                   Method         int GetHashCode()
GetType                       Method         type GetType()
ToString                      Method         string ToString()
Architecture                  NoteProperty   System.String Archit...
Author                        NoteProperty   System.String Author...
AutoRestart                   NoteProperty   System.String AutoRe...
Capability                    NoteProperty   System.Object[] Capa...
CompanyName                   NoteProperty   System.String Compan...
configfilepath                NoteProperty   System.String config...
Copyright                     NoteProperty   System.String Copyri...
Enabled                       NoteProperty   System.String Enable...
ExactMatch                    NoteProperty   System.String ExactM...
ExecutionPolicy               NoteProperty   System.String Execut...
Filename                      NoteProperty   System.String Filena...
GUID                          NoteProperty   System.String GUID=0...
ProcessIdleTimeoutSec         NoteProperty   System.String Proces...
IdleTimeoutms                 NoteProperty   System.String IdleTi...
lang                          NoteProperty   System.String lang=e...
LanguageMode                  NoteProperty   System.String Langua...
MaxConcurrentCommandsPerShell NoteProperty   System.String MaxCon...
MaxConcurrentUsers            NoteProperty   System.String MaxCon...
MaxIdleTimeoutms              NoteProperty   System.String MaxIdl...
MaxMemoryPerShellMB           NoteProperty   System.String MaxMem...
MaxProcessesPerShell          NoteProperty   System.String MaxPro...
MaxShells                     NoteProperty   System.String MaxShells
MaxShellsPerUser              NoteProperty   System.String MaxShe...
Name                          NoteProperty   System.String Name=N...
PSVersion                     NoteProperty   System.String PSVersion
ResourceUri                   NoteProperty   System.String Resour...
RunAsPassword                 NoteProperty   System.String RunAsP...
RunAsUser                     NoteProperty   System.String RunAsUser
SchemaVersion                 NoteProperty   System.String Schema...
SDKVersion                    NoteProperty   System.String SDKVer...
OutputBufferingMode           NoteProperty   System.String Output...
SessionType                   NoteProperty   System.String Sessio...
UseSharedProcess              NoteProperty   System.String UseSha...
SupportsOptions               NoteProperty   System.String Suppor...
xmlns                         NoteProperty   System.String xmlns=...
XmlRenderingType              NoteProperty   System.String XmlRen...
Permission                    ScriptProperty System.Object Permis...
```

Essas propriedades facilitam a pesquisa de configurações de sessão específicas.
Por exemplo, você pode usar a propriedade ExecutionPolicy para encontrar uma configuração de sessão que dê suporte a sessões com a política de execução RemoteSigned.
Observe que, como a propriedade ExecutionPolicy existe somente em sessões que usam arquivos de configuração de sessão, o comando pode não retornar todas as configurações de sessão qualificadas.

```powershell
Get-PSSessionConfiguration |
where {$_.ExecutionPolicy -eq "RemoteSigned"}
```

O comando a seguir obtém as configurações de sessão nas quais RunAsUser é o administrador do Exchange.

```powershell
 Get-PSSessionConfiguration |
where {$_.RunAsUser -eq "Exchange01\Admin01"}
```

Para exibir informações sobre as definições de função associadas a uma configuração, use o cmdlet Get-PSSessionCapability. Esse cmdlet permite que você determine os comandos e o ambiente disponíveis para usuários específicos em pontos de extremidade específicos.

## <a name="notes"></a>OBSERVAÇÕES

As configurações de sessão também dão suporte a um tipo de sessão conhecido como uma sessão "vazia". Um tipo de sessão vazia permite que você crie sessões personalizadas com os comandos selecionados. Se você não adicionar módulos, funções ou scripts a uma sessão vazia, a sessão será limitada a expressões e talvez não seja de uso prático. A propriedade SessionType informa se você está trabalhando ou não com uma sessão vazia.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Session_Configurations](about_Session_Configurations.md)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Disable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[Disable-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[Get-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[New-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[Register-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[Set-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[Test-PSSessionConfigurationFile](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[Unregister-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

[Get-PSSessionCapability](xref:Microsoft.PowerShell.Core.Get-PSSessionCapability)

[New-PSRoleCapabilityFile](xref:Microsoft.PowerShell.Core.New-PSRoleCapabilityFile)
