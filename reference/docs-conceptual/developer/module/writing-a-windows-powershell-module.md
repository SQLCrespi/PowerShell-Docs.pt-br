---
title: Escrevendo um módulo do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bfbccc5b-2b2b-432a-a971-9f8ab503cdc3
caps.latest.revision: 17
ms.openlocfilehash: 0b7263ea19745e902fff04b993933e443d4d6333
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360615"
---
# <a name="writing-a-windows-powershell-module"></a>Escrever um módulo do Windows PowerShell

Este documento foi escrito para administradores, desenvolvedores de scripts e desenvolvedores de cmdlets que precisam empacotar e distribuir seus cmdlets do Windows PowerShell. Usando os módulos do Windows PowerShell, você pode empacotar e distribuir suas soluções do Windows PowerShell sem usar uma linguagem compilada.

Os módulos do Windows PowerShell permitem particionar, organizar e abstrair o código do Windows PowerShell em unidades independentes e reutilizáveis. Com essas unidades reutilizáveis, você pode facilmente compartilhar seus módulos diretamente com outras pessoas. Se você for um desenvolvedor de scripts, também poderá reempacotar módulos de terceiros para criar aplicativos personalizados baseados em script. Módulos, semelhantes a módulos em outras linguagens de script, como Perl e Python, permitem soluções de script prontas para produção que usam componentes reutilizáveis e redistribuíveis, com o benefício adicional de permitir que você reempacote e abstraia vários componentes para Crie soluções personalizadas.

No seu mais básico, o Windows PowerShell tratará qualquer código de script válido do Windows PowerShell salvo em um arquivo. psm1 como um módulo. O PowerShell também tratará automaticamente qualquer assembly de cmdlet binário como um módulo. No entanto, você também pode usar um módulo (ou mais especificamente um manifesto de módulo) para agrupar uma solução inteira. Os cenários a seguir descrevem usos típicos para módulos do Windows PowerShell.

### <a name="libraries"></a>Bibliotecas

Os módulos podem ser usados para empacotar e distribuir bibliotecas coesas de funções que executam tarefas comuns. Normalmente, os nomes dessas funções compartilham um ou mais substantivos que refletem a tarefa comum para a qual são usados. Essas funções também podem ser semelhantes a .NET Framework classes, pois podem ter membros públicos e privados. Por exemplo, uma biblioteca pode conter um conjunto de funções para transferências de arquivos. Nesse caso, o substantivo que reflete a tarefa comum pode ser "File".

### <a name="configuration"></a>Configuração

Os módulos podem ser usados para personalizar seu ambiente adicionando cmdlets, provedores, funções e variáveis específicos.

### <a name="compiled-code-development-and-distribution"></a>Desenvolvimento e distribuição de código compilados

Os desenvolvedores de cmdlets e provedores podem usar módulos para testar e distribuir seu código compilado sem a necessidade de criar snap-ins. Eles podem importar o assembly que contém o código compilado como um módulo (um módulo binário) sem a necessidade de criar e registrar snap-ins.

## <a name="see-also"></a>Consulte Também

[Noções básicas sobre um módulo do Windows PowerShell](./understanding-a-windows-powershell-module.md)

[Como escrever um módulo de script do PowerShell](./how-to-write-a-powershell-script-module.md)

[Como escrever um módulo binário do PowerShell](./how-to-write-a-powershell-binary-module.md)

[Como escrever um manifesto de módulo do PowerShell](how-to-write-a-powershell-module-manifest.md)

[Modificando o caminho de instalação do PSModulePath](./modifying-the-psmodulepath-installation-path.md)

[Importando um módulo do PowerShell](./importing-a-powershell-module.md)

[Instalando um módulo do PowerShell](./installing-a-powershell-module.md)
