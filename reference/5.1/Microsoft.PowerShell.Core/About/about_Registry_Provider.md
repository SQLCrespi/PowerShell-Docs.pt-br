---
description: Registro
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_registry_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Registry
ms.openlocfilehash: a45513ca0ab4816793d52771ea1cfa56b239ecbf
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196164"
---
# <a name="registry-provider"></a>Provedor de registro

## <a name="provider-name"></a>Nome do provedor

Registro

## <a name="drives"></a>Unidades

`HKLM:`, `HKCU:`

## <a name="capabilities"></a>Funcionalidades

**ShouldProcess** , **UseTransactions**

## <a name="short-description"></a>Descrição breve

Fornece acesso às chaves, entradas e valores do registro no PowerShell.

## <a name="detailed-description"></a>Descrição detalhada

O provedor **do registro do** PowerShell permite que você obtenha, adicione, altere, apague e exclua chaves, entradas e valores do registro no PowerShell.

As unidades **do registro** são um namespace hierárquico que contém as chaves do registro e as subchaves em seu computador. Valores e entradas de Registro não são componentes dessa hierarquia. Em vez disso, eles são propriedades de cada uma das chaves.

O provedor de **registro** dá suporte aos seguintes cmdlets, que são abordados neste artigo.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Get-Acl](xref:Microsoft.PowerShell.Security.Get-Acl)
- [Set-Acl](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="types-exposed-by-this-provider"></a>Tipos expostos por este provedor

As chaves do registro são representadas como instâncias da classe [Microsoft. Win32. RegistryKey](/dotnet/api/microsoft.win32.registrykey) . As entradas do registro são representadas como instâncias da classe [PSCustomObject](/dotnet/api/system.management.automation.pscustomobject) .

## <a name="navigating-the-registry-drives"></a>Navegando pelas unidades do registro

O provedor de **registro** expõe seu armazenamento de dados como duas unidades padrão. O local do registro HKEY_LOCAL_MACHINE é mapeado para a `HKLM:` unidade e HKEY_CURRENT_USER é mapeado para a `HKCU:` unidade. Para trabalhar com o registro, você pode alterar seu local para a `HKLM:` unidade usando o comando a seguir.

```powershell
Set-Location HKLM:
```

Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade. Por exemplo, digite:

```powershell
Set-Location C:
```

Você também pode trabalhar com o provedor de **registro** de qualquer outra unidade do PowerShell. Para fazer referência a uma chave do registro de outro local, use o nome da unidade ( `HKLM:` , `HKCU:` ) no caminho. Use uma barra invertida ( \\ ) ou uma barra (/) para indicar um nível da unidade do **registro** .

```powershell
PS C:\> cd HKLM:\Software
```

> [!NOTE]
> O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor. Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

Este último exemplo mostra outra sintaxe de caminho que você pode usar para navegar pelo provedor de **registro** . Essa sintaxe usa o nome do provedor, seguida por dois dois-pontos `::` . Essa sintaxe permite que você use o nome completo do HIVE, em vez do nome da unidade mapeada `HKLM` .

```powershell
cd "Registry::HKEY_LOCAL_MACHINE\Software"
```

## <a name="displaying-the-contents-of-registry-keys"></a>Exibindo o conteúdo das chaves do registro

O registro é dividido em chaves, subchaves e entradas. Para obter mais informações sobre a estrutura do registro, consulte [estrutura do registro](/windows/desktop/sysinfo/structure-of-the-registry).

Em uma unidade de **registro** , cada chave é um contêiner. Uma chave pode conter qualquer número de chaves. Uma chave do registro que tem uma chave pai é chamada de subchave. Você pode usar `Get-ChildItem` para exibir as chaves do registro e `Set-Location` navegar até um caminho de chave.

Os valores do registro são atributos de uma chave do registro. Na unidade **do registro** , eles são chamados de **Propriedades de item** . Uma chave do registro pode ter as duas chaves filho e as propriedades do item.

Neste exemplo, a diferença entre `Get-Item` e `Get-ChildItem` é mostrada. Ao usar `Get-Item` a chave do registro "spooler", você pode exibir suas propriedades.

```
PS C:\ > Get-Item -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services


Name        Property
----        --------
Spooler     DependOnService    : {RPCSS, http}
            Description        : @%systemroot%\system32\spoolsv.exe,-2
            DisplayName        : @%systemroot%\system32\spoolsv.exe,-1
            ErrorControl       : 1
            FailureActions     : {16, 14, 0, 0...}
            Group              : SpoolerGroup
            ImagePath          : C:\WINDOWS\System32\spoolsv.exe
            ObjectName         : LocalSystem
            RequiredPrivileges : {SeTcbPrivilege, SeImpersonatePrivilege, ...
            ServiceSidType     : 1
            Start              : 2
            Type               : 27
```

Cada chave do registro também pode ter subchaves. Quando você usa `Get-Item` o em uma chave do registro, as subchaves não são exibidas. O `Get-ChildItem` cmdlet mostrará os itens filhos da chave "spooler", incluindo as propriedades de cada subchave. As propriedades de chaves pai não são mostradas ao usar `Get-ChildItem` .

```
PS C:\> Get-ChildItem -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Spooler


Name             Property
----             --------
Performance      Close           : PerfClose
                 Collect         : PerfCollect
                 Collect Timeout : 2000
                 Library         : C:\Windows\System32\winspool.drv
                 Object List     : 1450
                 Open            : PerfOpen
                 Open Timeout    : 4000
Security         Security : {1, 0, 20, 128...}
```

O `Get-Item` cmdlet também pode ser usado no local atual. O exemplo a seguir navega para a chave do registro "spooler" e obtém as propriedades do item.
O ponto `.` é usado para indicar o local atual.

```
PS C:\> cd HKLM:\System\CurrentControlSet\Services\Spooler
PS HKLM:\SYSTEM\CurrentControlSet\Services\Spooler> Get-Item .

    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services

Name             Property
----             --------
Spooler          DependOnService    : {RPCSS, http}
                 Description        : @%systemroot%\system32\spoolsv.exe,-2
...
```

Para obter mais informações sobre os cmdlets abordados nesta seção, consulte os artigos a seguir.

-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) 
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

## <a name="viewing-registry-key-values"></a>Exibindo valores de chave do registro

Os valores de chave do registro são armazenados como propriedades de cada chave do registro. O `Get-ItemProperty` cmdlet exibe as propriedades da chave do registro usando o nome que você especificar. O resultado é um **PSCustomObject** que contém as propriedades que você especificar.

O exemplo a seguir usa o `Get-ItemProperty` cmdlet para exibir todas as propriedades. Armazenar o objeto resultante em uma variável permite que você acesse o valor da propriedade desejada.

```powershell
$p = Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler
$p.DependOnService
```

```output
RPCSS
http
```

A especificação de um valor para o `-Name` parâmetro seleciona as propriedades que você especificar e retorna o **PSCustomObject** .  O exemplo a seguir mostra a diferença na saída quando você usa o `-Name` parâmetro.

```
PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem

BUILD                      : 17134.1
Installation Directory     : C:\WINDOWS\system32\WBEM
MOF Self-Install Directory : C:\WINDOWS\system32\WBEM\MOF
PSPath                     : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath               : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName                : Wbem
PSDrive                    : HKLM
PSProvider                 : Microsoft.PowerShell.Core\Registry

PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD

BUILD        : 17134.1
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName  : Wbem
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
```

A partir do PowerShell 5,0, o `Get-ItemPropertyValue` cmdlet retorna apenas o valor da propriedade que você especificar.

```powershell
Get-ItemPropertyValue -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD
```

```output
17134.1
```

Para obter mais informações sobre os cmdlets usados nesta seção, consulte os artigos a seguir.

- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Get-ItemPropertyValue](xref:Microsoft.PowerShell.Management.Get-ItemProperty)

## <a name="changing-registry-key-values"></a>Alterando valores de chave do registro

O `Set-ItemProperty` cmdlet definirá atributos para chaves do registro. O exemplo a seguir usa `Set-ItemProperty` para alterar o tipo de início do serviço de spooler para manual. O exemplo altera o **StartType** de volta para *automático* usando o `Set-Service` cmdlet.

```
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler Automatic

PS C:\> $path = "HKLM:\SYSTEM\CurrentControlSet\Services\Spooler\"
PS C:\> Set-ItemProperty -Path $path -Name Start -Value 3
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler    Manual

PS C:\> Set-Service -Name Spooler -StartupType Automatic
```

Cada chave do registro tem um valor *padrão* . Você pode alterar o valor *padrão* de uma chave do registro com um `Set-Item` ou `Set-ItemProperty` .

```powershell
Set-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name "(default)" -Value "one"
Set-Item -Path HKLM:\SOFTWARE\Contoso -Value "two"
```

Para obter mais informações sobre os cmdlets usados nesta seção, consulte os artigos a seguir.

- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="creating-registry-keys-and-values"></a>Criando chaves e valores do registro

O `New-Item` cmdlet criará chaves do registro com um nome que você fornecer.
Você também pode usar a `mkdir` função, que chama o `New-Item` cmdlet internamente.

```
PS HKLM:\SOFTWARE\> mkdir ContosoCompany

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
ContosoCompany
```

Você pode usar o `New-ItemProperty` cmdlet para criar valores em uma chave do registro que você especificar. O exemplo a seguir cria um novo valor DWORD na chave do registro ContosoCompany.

```powershell
$path = "HKLM:\SOFTWARE\ContosoCompany"
New-ItemProperty -Path  -Name Test -Type DWORD -Value 1
```

> [!NOTE]
> Examine a seção de parâmetros dinâmicos neste artigo para outros valores de tipo permitidos.

Para obter o uso detalhado do cmdlet, consulte [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).

## <a name="copying-registry-keys-and-values"></a>Copiando chaves e valores do registro

No provedor de **registro** , use o `Copy-Item` cmdlet para copiar valores e chaves do registro. Use o `Copy-ItemProperty` cmdlet para copiar somente valores de registro.
O comando a seguir copia a chave do registro "contoso" e suas propriedades para o local especificado "HKLM: \ Software\Fabrikam".

`Copy-Item` cria a chave de destino se ela não existir. Se a chave de destino existir, o `Copy-Item` criará uma duplicata da chave de origem como um item filho (subchave) da chave de destino.

```powershell
Copy-Item -Path  HKLM:\Software\Contoso -Destination HKLM:\Software\Fabrikam
```

O comando a seguir usa o `Copy-ItemProperty` cmdlet para copiar o valor "Server" da chave "contoso" para a chave "fabrikam".

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Copy-ItemProperty -Path $source -Destination $dest -Name Server
```

Para obter mais informações sobre os cmdlets usados nesta seção, consulte os artigos a seguir.

- [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item)
- [Copy-ItemProperty](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

## <a name="moving-registry-keys-and-values"></a>Movendo chaves e valores do registro

Os `Move-Item` `Move-ItemProperty` cmdlets e se comportam como suas contrapartes de "cópia". Se o destino existir, `Move-Item` o moverá a chave de origem para baixo da chave de destino. Se a chave de destino não existir, a chave de origem será movida para o caminho de destino.

O comando a seguir move a chave "contoso" para o caminho "HKLM: \ SOFTWARE\Fabrikam".

```powershell
Move-Item -Path HKLM:\SOFTWARE\Contoso -Destination HKLM:\SOFTWARE\Fabrikam
```

Esse comando move todas as propriedades de "HKLM: \ SOFTWARE\ContosoCompany" para "HKLM: \ SOFTWARE\Fabrikam".

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Move-ItemProperty -Path $source -Destination $dest -Name *
```

Para obter mais informações sobre os cmdlets usados nesta seção, consulte os artigos a seguir.

- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [Move-ItemProperty](xref:Microsoft.PowerShell.Management.Move-ItemProperty)

## <a name="renaming-registry-keys-and-values"></a>Renomeando chaves e valores do registro

Você pode renomear chaves e valores do registro da mesma forma que faria com arquivos e pastas.
`Rename-Item` renomeia as chaves do registro, enquanto `Rename-ItemProperty` renomeia os valores do registro.

```powershell
$path = "HKLM:\SOFTWARE\Contoso"
Rename-ItemProperty -Path $path -Name ContosoTest -NewName FabrikamTest
Rename-Item -Path $path -NewName Fabrikam
```

## <a name="changing-security-descriptors"></a>Alterando descritores de segurança

Você pode restringir o acesso a chaves do registro usando os `Get-Acl` `Set-Acl` cmdlets e. O exemplo a seguir adiciona um novo usuário com controle total à chave do registro "HKLM: \ SOFTWARE\Contoso".

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Contoso
$rule = New-Object System.Security.AccessControl.RegistryAccessRule `
("CONTOSO\jsmith", "FullControl", "Allow")
$acl.SetAccessRule($rule)
$acl | Set-Acl -Path HKLM:\SOFTWARE\Contoso
```

Para obter mais exemplos e detalhes de uso do cmdlet, consulte os artigos a seguir.

- [Get-Acl](xref:Microsoft.PowerShell.Security.Get-Acl)
- [Set-Acl](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="removing-and-clearing-registry-keys-and-values"></a>Removendo e limpando chaves e valores do registro

Você pode remover itens contidos usando **Remove-Item** , mas será solicitado que você confirme a remoção se o item contiver qualquer outra coisa. O exemplo a seguir tenta excluir uma chave "HKLM: \ SOFTWARE\Contoso".

```
PS C:\> dir HKLM:\SOFTWARE\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Contoso

Name                           Property
----                           --------
ChildKey

PS C:\> Remove-Item -Path HKLM:\SOFTWARE\Contoso

Confirm
The item at HKLM:\SOFTWARE\Contoso has children and the -Recurse
parameter was not specified. If you continue, all children will be removed
with the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

Para excluir os itens contidos sem avisar, especifique o `-Recurse` parâmetro.

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso -Recurse
```

Se você quisesse remover todos os itens dentro de "HKLM: \ SOFTWARE\Contoso", mas não "HKLM: \ SOFTWARE\Contoso", use uma barra invertida à direita `\` seguida por um caractere curinga.

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso\* -Recurse
```

Este comando exclui o valor do registro "ContosoTest" da chave do registro "HKLM: \ SOFTWARE\Contoso".

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name ContosoTest
```

`Clear-Item` limpa todos os valores de registro de uma chave. O exemplo a seguir limpa todos os valores da chave do registro "HKLM: \ SOFTWARE\Contoso". Para limpar apenas uma propriedade específica, use `Clear-ItemProperty` .

```
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name           Property
----           --------
Contoso        Server     : {a, b, c}
               HereString : {This is text which contains
               newlines. It also contains "quoted" strings}
               (default)  : 1

PS HKLM:\SOFTWARE\> Clear-Item .\Contoso\
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
Contoso
```

Para obter mais exemplos e detalhes de uso do cmdlet, consulte os artigos a seguir.

- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)

## <a name="dynamic-parameters"></a>Parâmetros dinâmicos

Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.

### <a name="type-microsoftwin32registryvaluekind"></a>Digite <Microsoft. Win32. RegistryValueKind>

Estabelece ou altera o tipo de dados de um valor do Registro. O padrão é `String` (REG_SZ).

Esse parâmetro funciona corretamente no cmdlet [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty). Ele também está disponível no cmdlet [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) em unidades de Registro, mas não tem nenhum efeito.

|Valor | Descrição |
| ---- | ----------- |
| `String` | Especifica uma cadeia de caracteres terminada em nulo. Equivalente a REG_SZ. |
| `ExpandString` | Especifica uma cadeia de caracteres terminada em nulo que contém não expandido |
|                | referências a variáveis de ambiente que são expandidas quando |
|                | o valor é recuperado. Equivalente ao REG_EXPAND_SZ. |
| `Binary` | Especifica os dados binários em qualquer formulário. Equivalente ao REG_BINARY. |
| `DWord` | Especifica um número binário de 32 bits. Equivalente ao REG_DWORD. |
| `MultiString` | Especifica uma matriz de cadeias de caracteres terminadas em nulo terminadas por |
|               | dois caracteres nulos. Equivalente ao REG_MULTI_SZ. |
| `QWord` | Especifica um número binário de 64 bits. Equivalente ao REG_QWORD. |
| `Unknown` | Indica um tipo de dados de registro sem suporte, como |
|           | REG_RESOURCE_LIST. |

#### <a name="cmdlets-supported"></a>Cmdlets com suporte

- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="using-the-pipeline"></a>Usando o pipeline

Os cmdlets do provedor aceitam a entrada do pipeline. Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor. Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.

## <a name="getting-help"></a>Obtendo ajuda

A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.

Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um `Get-Help` comando em uma unidade do sistema de arquivos ou use o parâmetro **Path** para especificar uma unidade do sistema de arquivos.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path HKLM:
```

## <a name="see-also"></a>Confira também

 [about_Providers](../About/about_Providers.md)
