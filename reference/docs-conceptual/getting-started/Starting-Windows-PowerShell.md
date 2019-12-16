---
ms.date: 12/05/2019
keywords: powershell, cmdlet
title: Iniciando o Windows PowerShell
ms.openlocfilehash: 97b15a4cd79c77a391451ba917f985f9d99db3f5
ms.sourcegitcommit: 0e4c69d8b5cf71431592fe41da816dec9b70f1f9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "74953816"
---
# <a name="starting-windows-powershell"></a>Iniciando o Windows PowerShell

O Windows PowerShell é uma `.DLL` de mecanismo de script que é inserida em vários hosts. Os hosts mais comuns que você iniciará são a linha de comando interativa **powershell.exe** e o Ambiente de Script Integrado **powershell_ise.exe**.

Para iniciar o Windows PowerShell® no Windows Server® 2012 R2, no Windows® 8.1, no Windows Server 2012 e no Windows 8, confira [Tarefas comuns de gerenciamento e navegação no Windows](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11)).

## <a name="powershell-core-has-renamed-binary"></a>O PowerShell Core renomeou o binário

O PowerShell Core, conhecido como PowerShell, é a versão 6 e posterior que é de software livre e usa o .NET Core. As versões compatíveis estão disponíveis no Windows, no macOS e no Linux.

No PowerShell 6 em diante, o binário do PowerShell foi renomeado **pwsh.exe** para o Windows e **pwsh** para o macOS e o Linux. Você pode iniciar as versões prévias do PowerShell usando **pwsh-preview**. Para obter mais informações, confira [Novidades do PowerShell Core 6.0](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe) e [Sobre o pwsh](/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7).

Para encontrar a referência de cmdlet e a documentação de instalação do PowerShell 7, use os seguintes links:

| Documento | Link |
| ----- | ----- |
| Referência de cmdlet | [Navegador do Módulo do PowerShell](/powershell/module/?view=powershell-7) |
| Instalação do Windows | [Instalação do PowerShell Core no Windows](/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7) |
| Instalação do macOS | [Instalar o PowerShell Core no macOS](/powershell/scripting/install/installing-powershell-core-on-macos?view=powershell-7) |
| Instalação do Linux | [Instalar o PowerShell Core no Linux](/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7) |

Para exibir o conteúdo de outras versões do PowerShell, confira [Como usar a documentação do PowerShell](../how-to-use-docs.md).

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a>Como iniciar o Windows PowerShell em versões anteriores do Windows

Esta seção explica como iniciar o Windows PowerShell e o ISE (Ambiente de Script Integrado) do Windows PowerShell no Windows® 7, Windows Server® 2008 R2 e Windows Server® 2008. Também explica como habilitar o recurso opcional para o ISE do Windows PowerShell no Windows PowerShell 2.0 no Windows Server® 2008 R2 e Windows Server 2008.

Use qualquer um dos seguintes métodos para iniciar a versão instalada do Windows PowerShell 3.0 ou o Windows PowerShell 4.0, quando aplicável.

#### <a name="from-the-start-menu"></a>Do menu Iniciar

- Clique em **Iniciar**, digite **PowerShell** e clique em **Windows PowerShell**.
- No menu **Iniciar**, clique em **Iniciar**, **Todos os Programas**, **Acessórios**, clique na pasta **Windows PowerShell** e clique em **Windows PowerShell**.

#### <a name="at-the-command-prompt"></a>No prompt de comando

No **cmd.exe**, no Windows PowerShell ou no ISE do Windows PowerShell, para iniciar o Windows PowerShell, digite:

```
PowerShell
```

Use também os parâmetros do programa **powershell.exe** para personalizar a sessão. Para obter mais informações, consulte [Ajuda de linha de comando do PowerShell.exe](../core-powershell/console/PowerShell.exe-Command-Line-Help.md).

#### <a name="with-administrative-privileges-run-as-administrator"></a>Com privilégios administrativos (Executar como administrador)

Clique em **Iniciar**, digite **PowerShell**, clique com o botão direito do mouse em **Windows PowerShell** e depois clique em **Executar como administrador**.

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a>Como iniciar o ISE do Windows PowerShell em versões anteriores do Windows

Use qualquer um dos seguintes métodos para iniciar o ISE do Windows PowerShell.

#### <a name="from-the-start-menu"></a>Do menu Iniciar

- Clique em **Iniciar**, digite **ISE** e clique em **ISE do Windows PowerShell**.
- No menu **Iniciar**, clique em **Iniciar**, **Todos os Programas**, **Acessórios**, clique na pasta **Windows PowerShell** e clique em **ISE do Windows PowerShell**.

#### <a name="at-the-command-prompt"></a>No prompt de comando

No **cmd.exe**, no Windows PowerShell ou no ISE do Windows PowerShell, para iniciar o Windows PowerShell, digite:

```
PowerShell_ISE
```

ou

```
ISE
```

#### <a name="with-administrative-privileges-run-as-administrator"></a>Com privilégios administrativos (Executar como administrador)

Clique em **Iniciar**, digite **ISE**, clique com o botão direito do mouse em **ISE do Windows PowerShell** e depois clique em **Executar como administrador**.

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a>Como habilitar o ISE do Windows PowerShell em versões anteriores do Windows

No Windows PowerShell 4.0 e Windows PowerShell 3.0, o ISE do Windows PowerShell é habilitado por padrão em todas as versões do Windows. Se ele ainda não estiver habilitado, o Windows Management Framework 4.0 ou o Windows Management Framework 3.0 o habilitará.

No Windows PowerShell 2.0, o ISE do Windows PowerShell é habilitado por padrão no Windows 7. No entanto, no Windows Server 2008 R2 e no Windows Server 2008, esse é um recurso opcional.

Para habilitar o ISE do Windows PowerShell no Windows PowerShell 2.0 no Windows Server 2008 R2 ou Windows Server 2008, use o seguinte procedimento.

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a>Para habilitar o ISE (Ambiente de Script Integrado) do Windows PowerShell

1. Inicie o Gerenciador do Servidor.
2. Clique em **Recursos** e depois em **Adicionar Recursos**.
3. Em Selecionar Recursos, clique em ISE (Ambiente de Script Integrado) do Windows PowerShell.

## <a name="starting-the-32-bit-version-of-windows-powershell"></a>Iniciando a versão de 32 bits do Windows PowerShell

Quando você instala o Windows PowerShell em um computador de 64 bits, o **Windows PowerShell (x86)** , uma versão de 32 bits do Windows PowerShell é instalada com a versão de 64 bits. Quando você executa o Windows PowerShell, a versão de 64 bits é executada por padrão.

No entanto, ocasionalmente poderá ser necessário executar o **Windows PowerShell (x86)** , como quando você estiver usando um módulo que exija a versão de 32 bits ou quando você estiver se conectando remotamente a um computador de 32 bits.

Para iniciar uma versão de 32 bits do Windows PowerShell, use qualquer um dos procedimentos a seguir.

#### <a name="in-windows-server-2012-r2"></a>No Windows Server® 2012 R2

- Na tela **Iniciar**, clique em **Windows PowerShell (x86)** . Clique no bloco **Windows PowerShell x86**.
- Em **Gerenciador do Servidor**, no menu **Ferramentas**, selecione **Windows PowerShell (x86)** .
- Na área de trabalho, mova o cursor para o canto superior direito, clique em **Pesquisar**, digite **PowerShell x86** e clique em **Windows PowerShell (x86)** .
- Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`

#### <a name="in-windows-server-2012"></a>No Windows Server® 2012

- Na tela **Iniciar**, digite **PowerShell** e clique em **Windows PowerShell (x86)** .
- Em **Gerenciador do Servidor**, no menu **Ferramentas**, selecione **Windows PowerShell (x86)** .
- Na área de trabalho, mova o cursor para o canto superior direito, clique em **Pesquisar**, digite **PowerShell** e clique em **Windows PowerShell (x86)** .
- Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`

#### <a name="in-windows-81"></a>No Windows® 8.1

- Na tela **Iniciar**, clique em **Windows PowerShell (x86)** . Clique no bloco **Windows PowerShell x86**.
- Se estiver executando as [Ferramentas de Administração de Servidor Remoto](https://go.microsoft.com/fwlink/?LinkID=304145) para o Windows 8.1, abra também o Windows PowerShell x86 no menu **Ferramentas do Gerenciador do Servidor**. Selecione **Windows PowerShell (x86)** .
- Na área de trabalho, mova o cursor para o canto superior direito, clique em **Pesquisar**, digite **PowerShell x86** e clique em **Windows PowerShell (x86)** .
- Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`

#### <a name="in-windows-8"></a>No Windows® 8

- Na tela **Iniciar**, mova o cursor para o canto superior direito, clique em **Configurações**, **Blocos** e, em seguida, mova o controle deslizante **Mostrar Ferramentas Administrativas** para **Sim**. Em seguida, digite **PowerShell** e clique em **Windows PowerShell (x86)** .
- Se estiver executando as [Ferramentas de Administração de Servidor Remoto](https://www.microsoft.com/download/details.aspx?id=28972) para o Windows 8, abra também o Windows PowerShell x86 no menu **Ferramentas do Gerenciador do Servidor**. Selecione **Windows PowerShell (x86)** .
- Na tela **Iniciar** ou na área de trabalho, digite **PowerShell (x86)** e clique em **Windows PowerShell (x86)** .
- Por meio da linha de comando, digite: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`
