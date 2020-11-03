---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-psdrive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSDrive
ms.openlocfilehash: 04346a3bd324b2d7033405546f131d2d56c5a2bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193604"
---
# New-PSDrive

## SINOPSE
Cria unidades de rede mapeadas temporárias e persistentes.

## SYNTAX

### Tudo

```
New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Description <String>]
 [-Scope <String>] [-Persist] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `New-PSDrive` cmdlet cria unidades temporárias e persistentes que são mapeadas para ou associadas a um local em um armazenamento de dados, como uma unidade de rede, um diretório no computador local ou uma chave do registro, e unidades de rede persistentes mapeadas do Windows que estão associadas a um local do sistema de arquivos em um computador remoto.

As unidades temporárias existem somente na sessão atual do PowerShell e nas sessões que você cria na sessão atual. Eles podem ter qualquer nome que seja válido no PowerShell e possam ser mapeados para qualquer recurso local ou remoto. Você pode usar unidades temporárias do PowerShell para acessar dados no armazenamento de dados associado, assim como faria com qualquer unidade de rede mapeada. Você pode alterar os locais na unidade usando o `Set-Location` e acessar o conteúdo da unidade usando o `Get-Item` ou o `Get-ChildItem` .

Como as unidades temporárias são conhecidas apenas pelo PowerShell, você não pode acessá-las usando o explorador de arquivos, Instrumentação de Gerenciamento do Windows (WMI), Component Object Model (COM), Microsoft .NET estrutura ou com ferramentas como **net use** .

Os seguintes recursos foram adicionados ao `New-PSDrive` no PowerShell 3,0:

- Unidades de rede mapeadas. Você pode usar o parâmetro **Persist** de `New-PSDrive` para criar unidades de rede mapeada do Windows. Diferentemente das unidades temporárias do PowerShell, as unidades de rede mapeadas do Windows não são específicas da sessão. Eles são salvos no Windows e podem ser gerenciados usando ferramentas padrão do Windows, como o explorador de arquivos e o **net use** . Unidades de rede mapeadas devem ter um nome de letra da unidade e estar conectadas a um local de sistema de arquivos remoto. Quando o seu comando tem o escopo definido localmente, nenhum ponto de fornecimento, o parâmetro **Persist** não mantém a criação de um **PSDrive** além do escopo no qual o comando está em execução. Se você estiver executando `New-PSDrive` dentro de um script e quiser que a unidade persista indefinidamente, você deverá criar o código de origem do script. Para obter melhores resultados, para forçar uma nova unidade a persistir indefinidamente, adicione o parâmetro **Scope** ao comando e defina seu valor como **global** . Para obter mais informações sobre o fornecimento de pontos, consulte [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).
- Unidades externas. Quando uma unidade externa é conectada ao computador, o PowerShell adiciona automaticamente um **PSDrive** ao sistema de arquivos que representa a nova unidade. Você não precisa reiniciar o PowerShell. Da mesma forma, quando uma unidade externa é desconectada do computador, o PowerShell exclui automaticamente o **PSDrive** que representa a unidade removida.
- Credenciais para caminhos UNC (Convenção de nomenclatura universal).

Quando o valor do parâmetro **raiz** é um caminho UNC, como `\\Server\Share` , a credencial especificada no valor do parâmetro **Credential** é usada para criar o **PSDrive** . Caso contrário, a **credencial** não será eficaz quando você estiver criando novas unidades do sistema de arquivos.

Alguns exemplos de código usam nivelamento para reduzir o tamanho da linha e melhorar a legibilidade. Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

## EXEMPLOS

### Exemplo 1: criar uma unidade temporária mapeada para um compartilhamento de rede

Este exemplo cria uma unidade temporária do PowerShell mapeada para um compartilhamento de rede.

```powershell
New-PSDrive -Name "Public" -PSProvider "FileSystem" -Root "\\Server01\Public"
```

```Output
Name       Provider      Root
----       --------      ----
Public     FileSystem    \\Server01\Public
```

`New-PSDrive` usa o parâmetro **Name** para especificar a unidade do PowerShell denominada `Public` e o parâmetro **PSProvider** para especificar o provedor do PowerShell `FileSystem` . O parâmetro **raiz** especifica o caminho UNC do compartilhamento de rede.

Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path Public:`

### Exemplo 2: criar uma unidade temporária mapeada para um diretório local

Este exemplo cria uma unidade temporária do PowerShell que fornece acesso a um diretório no computador local.

```powershell
$parameters = @{
    Name = "MyDocs"
    PSProvider = "FileSystem"
    Root = "C:\Users\User01\Documents"
    Description = "Maps to my My Documents folder."
}
New-PSDrive @parameters
```

```Output
Name        Provider      Root
----        --------      ----
MyDocs      FileSystem    C:\Users\User01\Documents
```

Nivelamento cria as chaves de parâmetro e valores. O parâmetro **Name** especifica o nome da unidade, **mydocs** . O parâmetro **PSProvider** especifica o provedor do PowerShell `FileSystem` . **Raiz** especifica o diretório do computador local. O parâmetro **Description** descreve a finalidade da unidade. `New-PSDrive` usa os parâmetros splatted para criar a `MyDocs` unidade.

Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path MyDocs:`

### Exemplo 3: criar uma unidade temporária para uma chave do registro

Este exemplo cria uma unidade temporária do PowerShell que fornece acesso a uma chave do registro. Ele cria uma unidade chamada MyCompany que é mapeada para a `HKLM:\Software\MyCompany` chave do registro.

```powershell
New-PSDrive -Name "MyCompany" -PSProvider "Registry" -Root "HKLM:\Software\MyCompany"
```

```Output
Name           Provider      Root
----           --------      ----
MyCompany      Registry      HKLM:\Software\MyCompany
```

`New-PSDrive` usa o parâmetro **Name** para especificar a unidade do PowerShell denominada `MyCompany` e o parâmetro **PSProvider** para especificar o provedor do PowerShell `Registry` . O parâmetro **raiz** especifica o local do registro.

Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path MyCompany:`

### Exemplo 4: criar uma unidade de rede mapeada persistente usando credenciais

Este exemplo mapeia uma unidade de rede que é autenticada com as credenciais de uma conta de serviço de domínio.
Para obter mais informações sobre o objeto **PSCredential** que armazena as credenciais e como as senhas são armazenadas como uma **SecureString** , consulte a descrição do parâmetro de **credencial** .

```powershell
$cred = Get-Credential -Credential Contoso\ServiceAccount
New-PSDrive -Name "S" -Root "\\Server01\Scripts" -Persist -PSProvider "FileSystem" -Credential $cred
Net Use
```

```Output
Status       Local     Remote                    Network
---------------------------------------------------------
OK           S:        \\Server01\Scripts        Microsoft Windows Network
```

> [!NOTE]
> Lembre-se de que, se você usar o trecho acima em um script, defina o valor do parâmetro de **escopo** como "global" para garantir que a unidade persiste fora do escopo atual.

A `$cred` variável armazena um objeto **PSCredential** que contém as credenciais da conta de serviço. `Get-Credential` solicita que você insira a senha que está armazenada em uma **SecureString** .

`New-PSDrive` cria a unidade de rede mapeada usando vários parâmetros. **Nome** especifica a `S` letra da unidade que o Windows aceita. e **root** define `\\Server01\Scripts` como o local em um computador remoto. **Persistir** cria uma unidade de rede mapeada do Windows que é salva no computador local. **PSProvider** especifica o `FileSystem` provedor. A **credencial** usa a `$cred` variável para obter as credenciais da conta de serviço para autenticação.

A unidade mapeada pode ser exibida no computador local em sessões do PowerShell, explorador de arquivos e com ferramentas como **net use** . Para exibir o conteúdo de uma sessão do PowerShell: `Get-ChildItem -Path S:`

### Exemplo 5: criar unidades persistentes e temporárias

Este exemplo mostra a diferença entre uma unidade de rede mapeada persistente e uma unidade temporária do PowerShell que é mapeada para o mesmo compartilhamento de rede.

Se você fechar a sessão do PowerShell e, em seguida, abrir uma nova sessão, o temporário `PSDrive:` não estará disponível, mas a `X:` unidade persistente estará disponível. Ao decidir qual método usar para mapear unidades de rede, considere como você usará a unidade. Por exemplo, se precisa ser persistente e se a unidade precisa estar visível para outros recursos do Windows.

```powershell
# Create a temporary PowerShell drive called PSDrive:
# that's mapped to the \\Server01\Public network share.
New-PSDrive -Name "PSDrive" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Use the Persist parameter of New-PSDrive to create the X: mapped network drive,
# which is also mapped to the \\Server01\Public network share.
New-PSDrive -Persist -Name "X" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Now, you can use the Get-PSDrive drive cmdlet to examine the two drives.
# The drives appear to be the same, although the network share name appears only
# in the root of the PSDrive: drive.
Get-PSDrive -Name "PSDrive", "X"
```

```Output
Name       Provider      Root
----       --------      ----

PsDrive    FileSystem    \\Server01\public
X          FileSystem    X:\
```

```powershell
# Get-Member cmdlet shows that the drives have the same object type,
# System.Management.Automation.PSDriveInfo.
Get-PSDrive "PSDrive", "x" | Get-Member
```

```Output
TypeName: System.Management.Automation.PSDriveInfo

Name                MemberType   Definition
----                ----------   ----------
CompareTo           Method       System.Int32 CompareTo(PSDriveInfo drive),
Equals              Method       System.Boolean Equals(Object obj),
GetHashCode         Method       System.Int32 GetHashCode()
...
```

```powershell
# Net Use and Get-CimInstance for the Win32_LogicalDisk class,
# and Win32_NetworkConnection class find only the persistent X: drive.
# PowerShell temporary drives are known only to PowerShell.
Net Use
Get-CimInstance Win32_LogicalDisk | Format-Table -Property DeviceID
Get-CimInstance Win32_NetworkConnection
```

```Output
Status       Local     Remote                    Network
--------------------------------------------------------
OK           X:        \\contoso-pc\data         Microsoft Windows Network

deviceid
--------
C:
D:
X:

LocalName    RemoteName              ConnectionState          Status
---------    ----------              ---------------          ------
X:           \\products\public       Disconnected             Unavailable
```

## PARAMETERS

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O padrão é o usuário atual.

Desde o PowerShell 3,0, quando o valor do parâmetro **raiz** é um caminho UNC, você pode usar credenciais para criar unidades do sistema de arquivos.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, você será solicitado a inserir a senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description

Especifica uma breve descrição em texto da unidade. Digite qualquer cadeia de caracteres.

Para ver as descrições de todas as unidades de sessão, `Get-PSDrive | Format-Table Name, Description` .

Para ver a descrição de uma unidade específica, digite `(Get-PSDrive <DriveName>).Description` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica um nome para a nova unidade. Para unidades de rede mapeadas persistentes, use uma letra de unidade. Para unidades temporárias do PowerShell, você não está limitado a letras de unidade, use qualquer cadeia de caracteres válida.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Persistir

Indica que esse cmdlet cria uma unidade de rede mapeada do Windows. O parâmetro **Persist** só está disponível no Windows.

Unidades de rede mapeadas são salvos no Windows no computador local. Eles são persistentes, não específicos da sessão e podem ser exibidos e gerenciados no explorador de arquivos e em outras ferramentas.

Quando você faz o escopo do comando localmente, sem o fato de a Sourcing, o parâmetro **Persist** não mantém a criação de um **PSDrive** além do escopo no qual você executa o comando. Se você executar `New-PSDrive` dentro de um script e quiser que a nova unidade persista indefinidamente, você deverá criar o código-fonte do script. Para obter melhores resultados, para forçar uma nova unidade a persistir, especifique **global** como o valor do parâmetro de **escopo** e inclua **Persist** no comando.

O nome da unidade deve ser uma letra, como `D` ou `E` . O valor do parâmetro **raiz** deve ser um caminho UNC de um computador diferente. O valor do parâmetro **PSProvider** deve ser `FileSystem` .

Para desconectar uma unidade de rede mapeada do Windows, use o `Remove-PSDrive` cmdlet. Quando você desconecta uma unidade de rede mapeada do Windows, o mapeamento é excluído permanentemente do computador, não apenas da sessão atual.

Unidades de rede mapeadas são específicas para uma conta de usuário. Unidades mapeadas criadas em sessões ou sessões com privilégios elevados usando a credencial de outro usuário não são visíveis em sessões iniciadas usando credenciais diferentes.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSProvider

Especifica o provedor do PowerShell que oferece suporte a unidades desse tipo.

Por exemplo, se a unidade estiver associada a um compartilhamento de rede ou diretório de sistema de arquivos, o provedor do PowerShell será `FileSystem` . Se a unidade estiver associada a uma chave do registro, o provedor será `Registry` .

Unidades temporárias do PowerShell podem ser associadas a qualquer provedor do PowerShell. Unidades de rede mapeadas podem ser associadas somente ao `FileSystem` provedor.

Para ver uma lista dos provedores em sua sessão do PowerShell, use o `Get-PSProvider` cmdlet.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Raiz

Especifica o local do repositório de dados para o qual uma unidade do PowerShell é mapeada.

Por exemplo, especifique um compartilhamento de rede, como `\\Server01\Public` um diretório local, como `C:\Program Files` , ou uma chave do registro, como `HKLM:\Software\Microsoft` .

As unidades temporárias do PowerShell podem ser associadas a um local local ou remoto em qualquer unidade de provedor com suporte. Unidades de rede mapeadas podem ser associadas somente a um local de sistema de arquivos em um computador remoto.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Escopo

Especifica um escopo para a unidade. Os valores aceitáveis para esse parâmetro são: **global** , **local** e **script** , ou um número relativo ao escopo atual. O número de escopos é 0 com o número de escopos. O número de escopo atual é 0 e seu pai é 1. Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível pipeline de entrada para este cmdlet.

## SAÍDAS

### System.Management.Automation.PSDriveInfo

## OBSERVAÇÕES

`New-PSDrive` o é projetado para trabalhar com os dados expostos por qualquer provedor. Para listar os provedores disponíveis em sua sessão, use `Get-PSProvider` . Para obter mais informações sobre provedores, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

Unidades de rede mapeadas são específicas para uma conta de usuário. Unidades mapeadas criadas em sessões ou sessões com privilégios elevados usando a credencial de outro usuário não são visíveis em sessões iniciadas usando credenciais diferentes.

## LINKS RELACIONADOS

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Get-PSDrive](Get-PSDrive.md)

[Remove-PSDrive](Remove-PSDrive.md)
