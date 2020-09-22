---
ms.date: 06/22/2020
keywords: DSC,powershell,configuração,serviço,instalação
title: Escrever, compilar e aplicar uma configuração
ms.openlocfilehash: 9acb2db882795d7150326fadb2964deb1105b2cc
ms.sourcegitcommit: 7eea0885dd7ac90ab36e5664501438a292217f7f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85295668"
---
# <a name="write-compile-and-apply-a-configuration"></a>Escrever, compilar e aplicar uma configuração

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0

Este exercício oferece instruções de como criar e aplicar uma configuração para a Configuração Estado Desejado (DSC) do início ao fim. No exemplo a seguir, você aprenderá como escrever e aplicar uma configuração muito simples. A configuração garantirá que um arquivo "HelloWorld.txt" existe em seu computador local.
Se você excluir o arquivo, a DSC o criará novamente em sua próxima atualização.

Para ter uma visão geral sobre o que é a DSC e como ela funciona, confira [Visão geral da Desired State Configuration para desenvolvedores](../overview/overview.md).

## <a name="requirements"></a>Requisitos

Para executar este exemplo, você precisará de um computador com o PowerShell 4.0 ou posterior.

## <a name="write-the-configuration"></a>Gravar a configuração

Uma [Configuração](configurations.md) DSC é uma função especial do PowerShell que define como você deseja configurar um ou mais computadores de destino (nós).

No ISE do PowerShell ou em outro editor do PowerShell, digite o seguinte:

```powershell
Configuration HelloWorld {

    # Import the module that contains the File resource.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets to compile MOF files for, when
    # this configuration is executed.
    Node 'localhost' {

        # The File resource can ensure the state of files, or copy them from a
        # source to a destination with persistent updates.
        File HelloWorld {
            DestinationPath = "C:\Temp\HelloWorld.txt"
            Ensure = "Present"
            Contents   = "Hello World from DSC!"
        }
    }
}
```

> [!IMPORTANT]
> Em cenários mais avançados, nos quais vários módulos precisam ser importados, para que você possa trabalhar com muitos Recursos de DSC na mesma configuração, coloque cada módulo em uma linha separada usando `Import-DscResource`. Assim é mais fácil manter no controle do código-fonte e é necessário ao trabalhar com a DSC na Configuração de Estado do Azure.
>
> ```powershell
>  Configuration HelloWorld {
>
>   # Import the module that contains the File resource.
>   Import-DscResource -ModuleName PsDesiredStateConfiguration
>   Import-DscResource -ModuleName xWebAdministration
>
> ```

Salve o arquivo como "HelloWorld.ps1".

Definir uma configuração é semelhante a definir uma função. O bloco **Nó** especifica o nó de destino a ser configurado, neste caso `localhost`.

A configuração chama um [recurso](../resources/resources.md), o recurso `File`. Os recursos fazem o trabalho de garantir que o nó de destino está no estado definido pela configuração.

## <a name="compile-the-configuration"></a>Compilar a configuração

Para que uma configuração DSC seja aplicada a um nó, ela deve primeiro ser compilada em um arquivo MOF. A execução da configuração, como no caso de uma função, compilará um arquivo `.mof` para cada Nó definido pelo bloco `Node`. Para executar a configuração, você precisa executar _dot source_ no script `HelloWorld.ps1` para o escopo atual. Para obter mais informações, confira [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).

<!-- markdownlint-disable MD038 -->
Execute _dot source_ no script `HelloWorld.ps1` digitando o caminho em que você o armazenou, após o `. ` (ponto, espaço). Em seguida, você poderá executar a configuração chamando-a como uma função. Você também pode invocar a função de configuração na parte inferior do script para que não seja necessário executar dot source.
<!-- markdownlint-enable MD038 -->

```powershell
. C:\Scripts\HelloWorld.ps1
HelloWorld
```

Isso gerará os seguintes resultados:

```Output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a>Aplicar a configuração

Agora que você tem o MOF compilado, é possível aplicar a configuração ao nó de destino (neste caso, o computador local) chamando o cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).

O cmdlet `Start-DscConfiguration` instrui o [LCM (Gerenciador de Configurações Local)](../managing-nodes/metaConfig.md), que é o mecanismo da DSC, a aplicar a configuração. O LCM realiza o trabalho de chamar os recursos de DSC para aplicar a configuração.

Use o código a seguir para executar o cmdlet `Start-DSCConfiguration`. Especifique o caminho do diretório no qual o `localhost.mof` está armazenado para o parâmetro **Path**. O cmdlet `Start-DSCConfiguration` examina o diretório especificado para qualquer arquivo `<computername>.mof`. O cmdlet `Start-DSCConfiguration` tenta aplicar cada arquivo `.mof` encontrado ao `computername` especificado pelo nome do ("localhost", "server01", "dc-02" etc.).

> [!NOTE]
> Se o parâmetro `-Wait` não for especificado, `Start-DSCConfiguration` criará um trabalho em segundo plano para executar a operação. Especificar o parâmetro `-Verbose` permite que você inspecione a saída **Detalhada** da operação. `-Wait` e `-Verbose` são parâmetros opcionais.

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a>Testar a configuração

Quando o cmdlet `Start-DSCConfiguration` for concluído, o arquivo `HelloWorld.txt` deverá estar no local especificado. Você pode verificar o conteúdo com o cmdlet [Get-Content](/powershell/module/microsoft.powershell.management/get-content).

Você também pode _testar_ o status atual usando [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).

A saída deverá ser `True` se o Nó estiver em conformidade no momento com a configuração aplicada.

```powershell
Test-DSCConfiguration
```

```Output
True
```

```powershell
Get-Content -Path C:\Temp\HelloWorld.txt
```

```Output
Hello World from DSC!
```

## <a name="re-applying-the-configuration"></a>Reaplicando a configuração

Para ver sua configuração ser aplicada novamente, você pode remover o arquivo de texto criado por ela. Em seguida, use o cmdlet `Start-DSCConfiguration` com o parâmetro `-UseExisting`. O parâmetro `-UseExisting` instrui `Start-DSCConfiguration` a reaplicar o arquivo "current.mof", que representa a configuração aplicada com sucesso mais recentemente.

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a>Próximas etapas

- Saiba mais sobre configurações de DSC em [Configurações de DSC](configurations.md).
- Veja quais recursos de DSC estão disponíveis e como criar recursos personalizados de DSC em [Recursos de DSC](../resources/resources.md).
- Localize as configurações e recursos de DSC na [Galeria do PowerShell](https://www.powershellgallery.com/).
