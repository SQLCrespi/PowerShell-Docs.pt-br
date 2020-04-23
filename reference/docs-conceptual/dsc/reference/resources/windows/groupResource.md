---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Group de DSC
ms.openlocfilehash: 695a914683c6daff44dd2a6c94b6353acf881030
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954653"
---
# <a name="dsc-group-resource"></a>Recurso Group de DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x

O recurso **Grupo** na DSC (Desired State Configuration) do Windows PowerShell fornece um mecanismo para gerenciar grupos locais no nó de destino.

## <a name="syntax"></a>Sintaxe

```Syntax
Group [string] #ResourceName
{
    GroupName = [string]
    [ Credential = [PSCredential] ]
    [ Description = [string[]] ]
    [ Members = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|GroupName |O nome do grupo para o qual você deseja garantir um estado específico. |
|Credencial |As credenciais necessárias para acessar recursos remotos. Essa conta deve ter as permissões apropriadas do Active Directory para adicionar todas as contas não locais ao grupo; caso contrário, ocorrerá um erro quando a configuração for executada no nó de destino.
|Descrição |A descrição do grupo. |
|Membros |Use essa propriedade para substituir a associação ao grupo pelos membros especificados. O valor dessa propriedade é uma matriz de cadeias de caracteres do formulário `Domain\UserName`. Se você definir essa propriedade em uma configuração, não use a propriedade **MembersToExclude** ou **MembersToInclude**. Isso gerará um erro. |
|MembersToExclude |Use essa propriedade para remover membros da associação existente do grupo. O valor dessa propriedade é uma matriz de cadeias de caracteres do formulário `Domain\UserName`. Se você definir essa propriedade em uma configuração, não use a propriedade **Membros**. Isso gerará um erro. |
|MembersToInclude |Use essa propriedade para adicionar membros à associação existente do grupo. O valor dessa propriedade é uma matriz de cadeias de caracteres do formulário `Domain\UserName`. Se você definir essa propriedade em uma configuração, não use a propriedade **Membros**. Isso vai gerar um erro. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Indica se o grupo existe. Defina essa propriedade como **Absent** para garantir que o grupo não exista. Ao defini-la como **Present**, você garante que o grupo exista. O valor padrão é **Present**. |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).

## <a name="example-1-ensure-group-is-not-present"></a>Exemplo 1: garanta que o grupo não esteja presente

O exemplo a seguir mostra como garantir que um grupo chamado "TestGroup" esteja ausente.

```powershell
Group GroupExample
{
    # This removes TestGroup, if present
    # To create a new group, set Ensure to "Present"
    Ensure = "Absent"
    GroupName = "TestGroup"
}
```

## <a name="example-2-add-domain-user-to-local-group"></a>Exemplo 2: adicione um usuário de domínio ao grupo local

O exemplo a seguir mostra como adicionar um usuário do Active Directory ao grupo de administradores locais como parte de um build de laboratório com vários computadores, em que você já está usando um PSCredential para a conta de Administrador Local. Como isso também é usado para a conta de administrador do domínio (após a promoção do domínio), devemos converter essa PSCredential existente em uma credencial de domínio amigável. Em seguida, podemos adicionar um usuário do domínio ao grupo de administradores local no servidor membro.

```powershell
@{
    AllNodes = @(
        @{
            NodeName = '*';
            DomainName = 'SubTest.contoso.com';
         }
        @{
            NodeName = 'Box2';
            AdminAccount = 'Admin-Dave_Alexanderson'
        }
    )
}

$domain = $node.DomainName.split('.')[0]
$DCredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList ("$domain\$($credential.Username)", $Credential.Password)

Group AddADUserToLocalAdminGroup {
    GroupName='Administrators'
    Ensure= 'Present'
    MembersToInclude= "$domain\$($Node.AdminAccount)"
    Credential = $dCredential
    PsDscRunAsCredential = $DCredential
}
```

## <a name="example-3"></a>Exemplo 3

O exemplo a seguir mostra como verificar se um grupo local, TigerTeamAdmins, no servidor TigerTeamSource.Contoso.Com, não contém uma conta de domínio específico, Contoso\JerryG.

```powershell
Configuration SecureTigerTeamSource {
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node TigerTeamSource.Contoso.Com {
        Group TigerTeamAdmins {
            GroupName        = 'TigerTeamAdmins'
            Ensure           = 'Present'
            MembersToExclude = "Contoso\JerryG"
        }
    }
}
```