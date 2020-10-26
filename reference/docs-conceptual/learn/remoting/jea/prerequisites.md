---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Pré-requisitos do JEA
description: Este artigo descreve os pré-requisitos que precisam ser atendidos para começar a usar o JEA.
ms.openlocfilehash: 5cc70a06887a2d0a840cc83117f865d3148056e1
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501721"
---
# <a name="prerequisites"></a>Pré-requisitos

O Just Enough Administration é um recurso incluído no PowerShell 5.0 e posterior. Este artigo descreve os pré-requisitos que precisam ser atendidos para começar a usar o JEA.

## <a name="check-which-version-of-powershell-is-installed"></a>Verificar qual versão do PowerShell que está instalada

Para verificar qual a versão do PowerShell que está instalada em seu sistema, verifique a variável `$PSVersionTable` em um prompt do Windows PowerShell.

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  1000
```

O JEA está disponível no PowerShell 5.0 e posterior. Para obter a funcionalidade completa, é recomendável que você instale a última versão do PowerShell disponível para seu sistema. A tabela a seguir descreve a disponibilidade do JEA no Windows Server:

| Sistema operacional de servidor |                Disponibilidade do JEA                |
| ----------------------- | ---------------------------------------------- |
| Windows Server 2016 e posterior    | Pré-instalado                                   |
| Windows Server 2012 R2  | Funcionalidade completa com o WMF 5.1                |
| Windows Server 2012     | Funcionalidade completa com o WMF 5.1                |
| Windows Server 2008 R2  | Funcionalidade reduzida<sup>1</sup> com WMF 5.1 |

Você também pode usar o JEA no seu computador residencial ou do trabalho:

| Sistema Operacional do Cliente |                   Disponibilidade do JEA                   |
| ----------------------- | ---------------------------------------------------- |
| Windows 10 1607+        | Pré-instalado                                         |
| Windows 10 1603, 1511   | Pré-instalado, com funcionalidade reduzida<sup>2</sup> |
| Windows 10 1507         | Não disponível                                        |
| Windows 8, 8.1          | Funcionalidade completa com o WMF 5.1                      |
| Windows 7               | Funcionalidade reduzida<sup>1</sup> com WMF 5.1       |

- <sup>1</sup> O JEA não pode ser configurado para usar contas de serviço gerenciado de grupo no Windows Server 2008 R2 ou no Windows 7. *Há suporte* para contas virtuais e outros recursos de JEA.

- <sup>2</sup> Os seguintes recursos do JEA não têm suporte no Windows 10 versões 1511 e 1603:

  - Execução como uma conta de serviço gerenciado de grupo
  - Regras de acesso condicional nas configurações de sessão
  - A unidade de usuário
  - Como permitir acesso às contas de usuário locais

  Para obter suporte para esses recursos, atualize o Windows para a versão 1607 (Atualização de Aniversário) ou superior.

### <a name="install-windows-management-framework"></a>Instalar o Windows Management Framework

Se estiver executando uma versão mais antiga do PowerShell, talvez você precise atualizar o sistema com a atualização mais recente do WMF (Windows Management Framework). Para obter mais informações, confira a documentação do [WMF](/powershell/scripting/wmf/overview).

É recomendável que você teste a compatibilidade da carga de trabalho com o WMF antes de atualizar todos os servidores.

Os usuários do Windows 10 devem instalar as atualizações mais recentes do recurso para obter a versão atual do Windows PowerShell.

## <a name="enable-powershell-remoting"></a>Habilitar a Comunicação Remota do PowerShell

A Comunicação Remota do PowerShell fornece a base na qual o JEA é criado. É necessário garantir que a comunicação remota do PowerShell esteja habilitada e devidamente protegida antes de usar o JEA. Para obter mais informações, confira [Segurança do WinRM](/powershell/scripting/learn/remoting/winrmsecurity).

A Comunicação Remota do PowerShell é habilitada por padrão no Windows Server 2012, 2012 R2 e 2016. Você pode habilitar a Comunicação Remota do PowerShell executando o seguinte comando em uma janela elevada do PowerShell.

```powershell
Enable-PSRemoting
```

## <a name="enable-powershell-module-and-script-block-logging-optional"></a>Habilitar o módulo do PowerShell e o registro em log de bloco de script (opcional)

As etapas a seguir habilitam o log para todas as ações do PowerShell em seu sistema. O Log de Módulo do PowerShell não é necessário para o JEA; no entanto, é recomendável que você ative o registro em log para garantir que os comandos executados pelos usuários sejam registrados em uma localização central.

Você pode configurar a política de Registro em Log do Módulo do PowerShell usando a Política de Grupo.

1. Abra o Editor de Política de Grupo Local em uma estação de trabalho ou um Objeto de Política de Grupo no Console de Gerenciamento de Política de Grupo em um Controlador de Domínio do Active Directory
2. Navegue até **Configuração do Computador\\Modelos Administrativos\\Componentes do Windows\\Windows PowerShell**
3. Clique duas vezes em **Ativar o Log de Módulo**
4. Clique em **Habilitado**
5. Na seção Opções, clique em **Mostrar** ao lado dos Nomes de Módulo
6. Digite `*` na janela pop-up para registrar em log os comandos de todos os módulos.
7. Clique em **OK** para definir a política
8. Clique duas vezes em **Ativar Log de Bloco de Script do PowerShell**
9. Clique em **Habilitado**
10. Clique em **OK** para definir a política
11. (Somente em computadores ingressados no domínio) Execute `gpupdate` ou aguarde a Política de Grupo processar a política atualizada e aplicar as configurações

Você também pode habilitar transcrição do PowerShell de todo o sistema por meio da Política de Grupo.

## <a name="next-steps"></a>Próximas etapas

[Criar um arquivo de capacidade de função](role-capabilities.md)

[Criar um arquivo de configuração de sessão](session-configurations.md)

## <a name="see-also"></a>Confira também

[Segurança do WinRM](/powershell/scripting/learn/remoting/winrmsecurity)

[PowerShell ♥ a equipe azul](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)
