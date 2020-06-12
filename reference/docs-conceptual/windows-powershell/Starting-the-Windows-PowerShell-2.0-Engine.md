---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Com usar o Mecanismo Windows PowerShell 2.0
ms.openlocfilehash: e00fb71c7fc32f5b48bc17ef5b25f910a846c893
ms.sourcegitcommit: 1748b2bdfae81d98097962c6c25c25df4bced1d8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2020
ms.locfileid: "84262606"
---
# <a name="using-the-windows-powershell-20-engine"></a>Com usar o Mecanismo Windows PowerShell 2.0

O Windows PowerShell foi projetado para ser compatível com versões anteriores. Cmdlets, provedores, snap-ins, módulos e scripts escritos para o Windows PowerShell 2.0 são executados sem alteração em versões mais recentes do Windows PowerShell. No entanto, o Microsoft .NET Framework 4 alterou a política de ativação de runtime.
Os programas de host do Windows PowerShell escritos para o Windows PowerShell 2.0 e compilados com o CLR (Common Language Runtime) 2.0 não podem ser executados sem modificação nas novas versões do Windows PowerShell que são compiladas com o CLR 4.0 (ou superior).

O Mecanismo Windows PowerShell 2.0 deve ser usado somente quando um programa de script ou de host existente não pode ser executado, porque ele é incompatível com o Windows PowerShell 5.1. Exemplos disso incluem as versões mais antigas dos módulos do SQL Server ou do Exchange. Tais casos devem ser raros.

Muitos programas que exigem o Mecanismo Windows PowerShell 2.0 o inicia automaticamente. Essas instruções são incluídas para as raras situações em que você precisa iniciar o mecanismo manualmente.

## <a name="deprecation-and-security-concerns"></a>Reprovação e problemas de segurança

O Windows PowerShell 2.0 foi preterido em agosto de 2017. Para obter mais informações, confira o [comunicado][] no blog do PowerShell.

O Windows PowerShell 2.0 não tem uma quantidade significativa dos recursos de proteção e segurança adicionados às versões 3, 4 e 5. Recomendamos expressamente que os usuários não o usem, se possível. Para obter mais informações, confira [Uma comparação da segurança da linguagem de script e do shell][] e [PowerShell ♥ a Equipe Azul][blueteam].

## <a name="installing-and-enabling-required-programs"></a>Instalar e habilitar os programas necessários

Antes de iniciar o Mecanismo Windows PowerShell 2.0, habilite o Mecanismo Windows PowerShell 2.0 e o Microsoft .NET Framework 3.5 com o Service Pack 1. Para ver as instruções, consulte [Instalar o Windows PowerShell][].

Os sistemas nos quais o Windows Management Framework 3.0 ou superior está instalado têm todos os componentes necessários. Nenhuma outra configuração é necessária. Para obter informações sobre como instalar o Windows Management Framework, confira [Instalar e configurar o WMF][].

## <a name="how-to-start-the-windows-powershell-20-engine"></a>Como iniciar o Mecanismo Windows PowerShell 2.0

Ao iniciar o Windows PowerShell a versão mais recente é iniciada por padrão. Para iniciar o Windows PowerShell com o Mecanismo Windows PowerShell 2.0, use o parâmetro Version de `PowerShell.exe`. Você pode executar o comando no prompt de comando, incluindo o Windows PowerShell e Cmd.exe.

```
PowerShell.exe -Version 2
```

## <a name="how-to-start-a-remote-session-with-the-windows-powershell-20-engine"></a>Como iniciar uma sessão remota com o Mecanismo Windows PowerShell 2.0

Para executar o Mecanismo Windows PowerShell 2.0 em uma sessão remota, crie uma configuração de sessão (também conhecida como _ponto de extremidade_) no computador remoto que carrega o Mecanismo Windows PowerShell 2.0. A configuração da sessão é salva no computador remoto e pode ser usada por qualquer usuário autorizado para criar sessões que utilizam o Mecanismo Windows PowerShell 2.0.

Essa é uma tarefa avançada que normalmente é executada por um administrador do sistema.

O procedimento a seguir usa o parâmetro **PSVersion** do cmdlet [Register-PSSessionConfiguration][] para criar uma Mecanismo Windows PowerShell 2.0. Você também pode usar o parâmetro **PowerShellVersion** do cmdlet [New-PSSessionConfigurationFile][] para criar um arquivo de configuração de sessão para uma sessão que carrega o Mecanismo Windows PowerShell 2.0 e você pode usar o parâmetro **PSVersion** do parâmetro [Set-PSSessionConfiguration][] para alterar uma configuração de sessão para usar o Mecanismo Windows PowerShell 2.0.

Para obter mais informações sobre como criar arquivos de configuração, confira [about_Session_Configuration_Files][].
Para obter informações sobre as configurações de sessão, incluindo instalação e segurança, confira [about_Session_Configurations][].

### <a name="to-start-a-remote-windows-powershell-20-session"></a>Para iniciar uma sessão remota do Windows PowerShell 2.0

1. Para criar uma configuração de sessão que exige o Mecanismo Windows PowerShell 2.0, use o parâmetro **PSVersion** do cmdlet `Register-PSSessionConfiguration` com um valor igual a `2.0`.
   Execute este comando no computador no “lado do servidor” ou na extremidade de recebimento de uma conexão.

   O comando de exemplo a seguir cria a configuração de sessão PS2 no computador Server01. Para executar esse comando, inicie o Windows PowerShell com a opção **Executar como administrador**.

   ```powershell
   Register-PSSessionConfiguration -Name PS2 -PSVersion 2.0
   ```

1. Para criar uma sessão no computador Server01 que usa a configuração de sessão PS2, use o parâmetro **ConfigurationName** dos cmdlets que criam uma sessão remota, como o cmdlet New-PSSession.

   Quando uma sessão que usa a configuração de sessão é iniciada, o Mecanismo Windows PowerShell 2.0 é automaticamente carregado na sessão.

   O comando a seguir inicia uma sessão no computador Server01 que usa a configuração de sessão PS2. O comando salva a sessão na variável `$s`.

   ```powershell
   $s = New-PSSession -ComputerName Server01 -ConfigurationName PS2
   ```

## <a name="how-to-start-a-background-job-with-the-windows-powershell-20-engine"></a>Como iniciar um trabalho em segundo plano com o Mecanismo Windows PowerShell 2.0

Para iniciar um trabalho em segundo plano com o Mecanismo Windows PowerShell 2.0, use o parâmetro **PSVersion** do cmdlet [Start-Job][].

O comando a seguir inicia um trabalho em segundo plano com o Mecanismo Windows PowerShell 2.0

```powershell
Start-Job {Get-Process} -PSVersion 2.0
```

Para obter mais informações sobre trabalhos em segundo plano, consulte [about_Jobs][].

<!-- link references -->
[comunicado]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[Uma comparação da segurança da linguagem de script e do shell]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/
[blueteam]: https://devblogs.microsoft.com/powershell/powershell-the-blue-team/
[Instalar o Windows PowerShell]: install/Installing-Windows-PowerShell.md
[Instalar e configurar o WMF]: wmf/setup/install-configure.md
[Register-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration
[New-PSSessionConfigurationFile]: /powershell/module/Microsoft.PowerShell.Core/New-PSSessionConfiguration
[Set-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration
[about_Session_Configuration_Files]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configuration_Files
[about_Session_Configurations]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configurations
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[about_Jobs]: /powershell/module/microsoft.powershell.core/about/about_jobs
