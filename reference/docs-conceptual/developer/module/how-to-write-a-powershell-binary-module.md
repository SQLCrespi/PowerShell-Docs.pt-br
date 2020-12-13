---
ms.date: 09/13/2016
ms.topic: reference
title: Como escrever um módulo binário do Windows PowerShell
description: Como escrever um módulo binário do Windows PowerShell
ms.openlocfilehash: 1d5cea474ac418f78cc782360b7c23b7614d6669
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663069"
---
# <a name="how-to-write-a-powershell-binary-module"></a>Como escrever um módulo binário do Windows PowerShell

Um módulo binário pode ser qualquer assembly (. dll) que contenha classes de cmdlet. Por padrão, todos os cmdlets no assembly são importados quando o módulo binário é importado. No entanto, você pode restringir os cmdlets que são importados criando um manifesto de módulo cujo módulo raiz é o assembly. (Por exemplo, a chave CmdletsToExport do manifesto pode ser usada para exportar somente os cmdlets necessários.) Além disso, um módulo binário pode conter arquivos adicionais, uma estrutura de diretório e outras informações de gerenciamento úteis que um único cmdlet não pode.

O procedimento a seguir descreve como criar e instalar um módulo binário do PowerShell.

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a>Como criar e instalar um módulo binário do PowerShell

1. Crie uma solução binária do PowerShell (como um cmdlet escrito em C#), com os recursos necessários e certifique-se de que ela seja executada corretamente.

   De uma perspectiva de código, o núcleo de um módulo binário é simplesmente um assembly de cmdlet. Na verdade, o PowerShell tratará um único assembly de cmdlet como um módulo, em termos de carregamento e descarregamento, sem esforço adicional por parte do desenvolvedor. Para obter mais informações sobre como escrever um cmdlet, consulte [escrevendo um cmdlet do Windows PowerShell](../cmdlet/writing-a-windows-powershell-cmdlet.md).

2. Se necessário, crie o restante da sua solução: (cmdlets adicionais, arquivos XML e assim por diante) e descreva-os com um manifesto de módulo.

   Além de descrever os assemblies de cmdlet em sua solução, um manifesto de módulo pode descrever como você deseja que seu módulo seja exportado e importado, quais cmdlets serão expostos e quais arquivos adicionais serão inseridos no módulo.
   Como mencionado anteriormente, o PowerShell pode tratar um cmdlet binário como um módulo sem esforço adicional.
   Dessa forma, um manifesto de módulo é útil principalmente para combinar vários arquivos em um único pacote ou para controlar explicitamente a publicação para um determinado assembly.
   Para obter mais informações, consulte [como escrever um manifesto de módulo do PowerShell](how-to-write-a-powershell-module-manifest.md).

   O código a seguir é um bloco de código C# extremamente simples que contém três cmdlets no mesmo arquivo que pode ser usado como um módulo.

   ```csharp
   using System.Management.Automation;           // Windows PowerShell namespace.

   namespace ModuleCmdlets
   {
     [Cmdlet(VerbsDiagnostic.Test,"BinaryModuleCmdlet1")]
     public class TestBinaryModuleCmdlet1Command : Cmdlet
     {
       protected override void BeginProcessing()
       {
         WriteObject("BinaryModuleCmdlet1 exported by the ModuleCmdlets module.");
       }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet2")]
     public class TestBinaryModuleCmdlet2Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet2 exported by the ModuleCmdlets module.");
         }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet3")]
     public class TestBinaryModuleCmdlet3Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet3 exported by the ModuleCmdlets module.");
         }
     }

   }
   ```

3. Empacote sua solução e salve o pacote em algum lugar no caminho do módulo do PowerShell.

   A `PSModulePath` variável de ambiente global descreve os caminhos padrão que o PowerShell usará para localizar o módulo. Por exemplo, um caminho comum para salvar um módulo em um sistema seria `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>` . Se você não usar os caminhos padrão, será necessário declarar explicitamente o local do seu módulo durante a instalação. Certifique-se de criar uma pasta na qual salvar o módulo, pois talvez seja necessário que a pasta armazene vários assemblies e arquivos para sua solução.

   Observe que, tecnicamente, não é necessário instalar seu módulo em qualquer lugar no `PSModulePath` -aqueles são simplesmente os locais padrão que o PowerShell procurará no seu módulo. No entanto, é considerado a prática recomendada fazer isso, a menos que você tenha um bom motivo para armazenar seu módulo em outro lugar. Para obter mais informações, consulte [instalando um módulo do PowerShell](./installing-a-powershell-module.md) e [modificando o caminho de instalação do módulo do PowerShell](./modifying-the-psmodulepath-installation-path.md).

4. Importe seu módulo no PowerShell com uma chamada para [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).

   Chamar para [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) carregará seu módulo na memória ativa. Se você estiver usando o PowerShell 3,0 e posterior, simplesmente chamar o nome do seu módulo no código também irá importá-lo; para obter mais informações, consulte [importando um módulo do PowerShell](./importing-a-powershell-module.md).

## <a name="importing-snap-in-assemblies-as-modules"></a>Importando assemblies de snap-in como módulos

Os cmdlets e provedores que existem em assemblies de snap-in podem ser carregados como módulos binários. Quando os assemblies de snap-in são carregados como módulos binários, os cmdlets e provedores no snap-in estão disponíveis para o usuário, mas a classe de snap-in no assembly é ignorada e o snap-in não é registrado. Como resultado, os cmdlets de snap-in fornecidos pelo Windows PowerShell não podem detectar o snap-in, embora os cmdlets e provedores estejam disponíveis para a sessão.

Além disso, todos os arquivos de formatação ou tipos que são referenciados pelo snap-in não podem ser importados como parte de um módulo binário.
Para importar os arquivos de formatação e tipos, você deve criar um manifesto de módulo.
Consulte [como escrever um manifesto de módulo do PowerShell](how-to-write-a-powershell-module-manifest.md).

## <a name="see-also"></a>Consulte Também

[Escrever um módulo do Windows PowerShell](./writing-a-windows-powershell-module.md)
