---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Usando a expansão com Tab
ms.openlocfilehash: d96cbf848f464aff29a7bed9b70d0b6a000aa808
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "67031014"
---
# <a name="using-tab-expansion"></a>Usando a expansão com Tab

Shells de linha de comando geralmente fornecem uma maneira de preencher nomes longos de arquivos ou comandos automaticamente, acelerando a entrada de comandos e fornecendo dicas. O PowerShell permite preencher os nomes de arquivo e os nomes de cmdlet pressionando a tecla <kbd>Tab</kbd>.

> [!NOTE]
> A expansão da guia é controlada pelas funções internas TabExpansion ou TabExpansion2. Como essa função pode ser modificada ou substituída, essa discussão é um guia para o comportamento da configuração padrão do PowerShell.

Para preencher automaticamente um nome de arquivo ou um caminho com as opções disponíveis automaticamente, digite parte do nome e pressione a tecla <kbd>Tab</kbd>. O PowerShell expandirá automaticamente o nome para a primeira correspondência que encontrar. Pressionar a tecla <kbd>Tab</kbd> repetidamente percorrerá todas as opções disponíveis.

A expansão com Tab de nomes de cmdlet é ligeiramente diferente. Para usar a expansão com Tab em um nome de cmdlet, digite a primeira parte inteira do nome (o verbo) e o hífen que o segue. Você pode preencher mais do mesmo nome de uma correspondência parcial. Por exemplo, se você digitar `get-co` e pressionar a tecla <kbd>Tab</kbd>, o PowerShell o expandirá automaticamente para o cmdlet `Get-Command` (observe que ele também altera as letras maiúsculas e minúsculas para sua forma padrão). Se você pressionar a tecla <kbd>Tab</kbd> novamente, o PowerShell substitui isso pelo outro único nome de cmdlet correspondente, `Get-Content`.

Você pode usar a expansão com Tab várias vezes na mesma linha. Por exemplo, você pode usar a expansão de guias no nome do cmdlet `Get-Content` digitando:

```
PS> Get-Con<Tab>
```

Quando você pressiona a tecla <kbd>Tab</kbd>, o comando se expande para:

```
PS> Get-Content
```

Você pode especificar parcialmente o caminho para o arquivo de log Active Setup e usar a expansão com Tab novamente:

```
PS> Get-Content c:\windows\acts<Tab>
```

Quando você pressiona a tecla <kbd>Tab</kbd>, o comando se expande para:

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> Uma limitação do processo de expansão de guia é que as guias são sempre interpretadas como tentativas de preencher uma palavra. Se você copiar e colar os exemplos de comando em um console do PowerShell, verifique se o exemplo não contém guias; se contiver, os resultados serão imprevisíveis e certamente não serão o que você pretendia.
