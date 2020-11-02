---
ms.date: 07/17/2020
ms.topic: reference
title: Recurso nxSshAuthorizedKeys de DSC para Linux
description: Recurso nxSshAuthorizedKeys de DSC para Linux
ms.openlocfilehash: 881e94aa583a745cdac7f01b6e445352ef4ca937
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662765"
---
# <a name="dsc-for-linux-nxsshauthorizedkeys-resource"></a>Recurso nxSshAuthorizedKeys de DSC para Linux

O recurso **nxAuthorizedKeys** na Configuração de Estado Desejado (DSC) do PowerShell fornece um mecanismo para gerenciar chaves ssh autorizadas para um usuário especificado.

## <a name="syntax"></a>Sintaxe

```Syntax
nxAuthorizedKeys <string> #ResourceName
{
    KeyComment = <string>
    [ Username = <string> ]
    [ Key = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |DESCRIÇÃO |
|---|---|
|KeyComment |Um comentário exclusivo para a chave. É usado para identificar as chaves com exclusividade. |
|Nome de Usuário |O nome de usuário para o qual as chaves ssh autorizadas serão gerenciadas. Se não for definido, o usuário padrão será **root** . |
|Chave |O conteúdo da chave. Será obrigatório se **Ensure** for definido como **Present** .|

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |DESCRIÇÃO |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Especifica se a chave foi definida. Defina essa propriedade como **Absent** para garantir que a chave não exista no arquivo de chaves autorizadas do usuário. Defina-a como **Present** para garantir que a chave seja definida no arquivo de chaves autorizadas do usuário. |

## <a name="example"></a>Exemplo

O exemplo a seguir define uma chave ssh pública autorizada para o usuário "monuser".

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxSshAuthorizedKeys myKey
    {
        KeyComment = "myKey"
        Ensure = "Present"
        Key = 'ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEA0b+0xSd07QXRifm3FXj7Pn/DblA6QI5VAkDm6OivFzj3U6qGD1VJ6AAxWPCyMl/qhtpRtxZJDu/TxD8AyZNgc8aN2CljN1hOMbBRvH2q5QPf/nCnnJRaGsrxIqZjyZdYo9ZEEzjZUuMDM5HI1LA9B99k/K6PK2Bc1NLivpu7nbtVG2tLOQs+GefsnHuetsRMwo/+c3LtwYm9M0XfkGjYVCLO4CoFuSQpvX6AB3TedUy6NZ0iuxC0kRGg1rIQTwSRcw+McLhslF0drs33fw6tYdzlLBnnzimShMuiDWiT37WqCRovRGYrGCaEFGTG2e0CN8Co8nryXkyWc6NSDNpMzw== rsa-key-20150401'
        UserName = "monuser"
    }
}
```
