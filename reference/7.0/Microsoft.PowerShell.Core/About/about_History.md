---
description: Descreve como obter e executar comandos no histórico de comandos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_history?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_History
ms.openlocfilehash: b9e8ab09553f8cd6452f4a891ecbaa1b914af895
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195900"
---
# <a name="about-history"></a>Sobre o histórico

## <a name="short-description"></a>Descrição breve
Descreve como obter e executar comandos no histórico de comandos.

## <a name="long-description"></a>Descrição longa

Quando você insere um comando no prompt de comando, o PowerShell salva o comando no histórico de comandos. Você pode usar os comandos no histórico como um registro do seu trabalho. E, você pode recuperar e executar os comandos no histórico de comandos.

O PowerShell tem dois provedores de histórico diferentes: o histórico interno e o histórico gerenciado pelo módulo **PSReadLine** . Os históricos são gerenciados separadamente, mas ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado.

## <a name="using-the-psreadline-history"></a>Usando o histórico de PSReadLine

O histórico de PSReadLine controla os comandos usados em todas as sessões do PowerShell.
O histórico é gravado em um arquivo central por host. Esse arquivo de histórico está disponível para todas as sessões e contém todo o histórico anterior. O histórico não é excluído quando a sessão termina. Além disso, esse histórico não pode ser gerenciado pelos `*-History` cmdlets. Para obter mais informações, consulte [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).

## <a name="using-the-built-in-session-history"></a>Usando o histórico de sessões internas

O histórico interno controla apenas os comandos usados na sessão atual. O histórico não está disponível para outras sessões e é excluído quando a sessão termina.

### <a name="history-cmdlets"></a>Cmdlets de histórico

O PowerShell tem um conjunto de cmdlets que gerenciam o histórico de comandos.

| Cmdlet           | Alias  | Descrição                                |
| ---------------- | ------ | ------------------------------------------ |
| `Get-History`    | `h`    | Obtém o histórico de comandos.                  |
| `Invoke-History` | `r`    | Executa um comando no histórico de comandos.     |
| `Add-History`    |        | Adiciona um comando ao histórico de comandos.     |
| `Clear-History`  | `clhy` | Exclui comandos do histórico de comandos. |

### <a name="keyboard-shortcuts-for-managing-history"></a>Atalhos de teclado para gerenciamento de histórico

No console do PowerShell, você pode usar os seguintes atalhos para gerenciar o histórico de comandos.

- <kbd>Upseta</kbd> – exibe o comando anterior.
- <kbd>Seta</kbd> -exibe o próximo comando.
- <kbd>F7</kbd> -exibe o histórico de comandos.
- <kbd>ESC</kbd> – para ocultar o histórico.
- <kbd>F8</kbd> -localiza um comando. Digite um ou mais caracteres e pressione <kbd>F8</kbd>. Pressione <kbd>F8</kbd> novamente na próxima instância.
- <kbd>F9</kbd> -localizar um comando por ID do histórico. Digite a ID do histórico e pressione <kbd>F9</kbd>. Pressione <kbd>F7</kbd> para localizar a ID.
- <kbd>#</kbd>`<string>`</kbd><kbd>Guia</kbd> – pesquise o histórico para `*<string>*` e retorna a correspondência mais recente. Se você pressionar <kbd>Tab</kbd> repetidamente, ela percorrerá os itens correspondentes em seu histórico.

> [!NOTE]
> Essas associações de chave são implementadas pelo aplicativo host do console. Outros aplicativos, como Visual Studio Code ou terminal do Windows, podem ter diferentes associações de chave. As associações podem ser substituídas pelo módulo PSReadLine. O PSReadLine é carregado automaticamente quando você inicia uma sessão do PowerShell.
> Com PSReadLine carregado, <kbd>F7</kbd> e <kbd>F9</kbd> não são associados a nenhuma função. PSReadLine não fornece funcionalidade equivalente. Para obter mais informações, consulte [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).

### <a name="maximumhistorycount"></a>MaximumHistoryCount

A `$MaximumHistoryCount` variável de preferência determina o número máximo de comandos que o PowerShell salva no histórico de comandos. O valor padrão é
4096.

Por exemplo, o comando a seguir reduz os `$MaximumHistoryCount` comandos para 100:

```powershell
$MaximumHistoryCount = 100
```

Para aplicar a configuração, reinicie o PowerShell.

Para salvar o novo valor de variável para todas as sessões do PowerShell, adicione a instrução de atribuição a um perfil do PowerShell. Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).

Para obter mais informações sobre a `$MaximumHistoryCount` variável de preferência, consulte [about_Preference_Variables](about_Preference_Variables.md).

### <a name="order-of-commands-in-the-history"></a>Ordem dos comandos no histórico

Os comandos são adicionados ao histórico quando o comando termina a execução, não quando o comando é inserido. Se os comandos levar algum tempo para serem concluídos ou se os comandos estiverem sendo executados em um prompt aninhado, os comandos poderão parecer estar fora de ordem no histórico. Os comandos que estão sendo executados em um prompt aninhado são concluídos somente quando você sai do nível do prompt.

## <a name="see-also"></a>Consulte Também

- [about_Line_Editing](about_Line_Editing.md)
- [about_Preference_Variables](about_Preference_Variables.md)
- [about_Profiles](about_Profiles.md)
- [about_Variables](about_Variables.md)
- [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md)
