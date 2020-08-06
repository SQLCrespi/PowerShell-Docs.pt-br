---
title: Exemplo de GetProcessSample01 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 84956fbafdd58623ca4f332efc940fb93b421c6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784241"
---
# <a name="getprocesssample01-sample"></a>Amostra GetProcessSample01

Este exemplo mostra como implementar um cmdlet que recupera os processos no computador local. Esse cmdlet é uma versão simplificada do `Get-Process` cmdlet que é fornecida pelo Windows PowerShell 2,0.

## <a name="how-to-build-the-sample-by-using-visual-studio"></a>Como criar o exemplo usando o Visual Studio.

1. Com o SDK do Windows PowerShell 2,0 instalado, navegue até a pasta GetProcessSample01. O local padrão é C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample01.

2. Clique duas vezes no ícone do arquivo da solução (. sln). Isso abre o projeto de exemplo no Microsoft Visual Studio.

3. No menu **Compilar**, selecione **Compilar Solução**.

  A biblioteca do exemplo será criada nas pastas \bin ou \bin\Debug padrão.

### <a name="how-to-run-the-sample"></a>Como executar a amostra

1. Abra uma janela de Prompt de Comando.

2. Navegue até o diretório que contém o arquivo. dll de exemplo.

3. Execute InstallUtil "GetProcessSample01.dll".

4. Inicie o Windows PowerShell.

5. Execute o comando a seguir para adicionar o snap-in ao shell.

   `Add-PSSnapin GetProcPSSnapIn01`

6. Digite o comando a seguir para executar o cmdlet. `get-proc`

   `get-proc`

   Este é um exemplo de saída resultante das seguintes etapas.

   ```output
   Id              Name            State      HasMoreData     Location             Command
   --              ----            -----      -----------     --------             -------
   1               26932870-d3b... NotStarted False                                 Write-Host "A f...

   ```

   ```powershell
   Set-Content $env:temp\test.txt "This is a test file"
   ```

   ```output
   A file was created in the TEMP directory
   ```

## <a name="requirements"></a>Requisitos

Este exemplo requer o Windows PowerShell 1,0 ou posterior.

## <a name="demonstrates"></a>Demonstra

Este exemplo demonstra o seguinte.

- Criando um cmdlet de exemplo básico.

- Definindo uma classe de cmdlet usando o atributo cmdlet.

- Criação de um snap-in que funciona com o Windows PowerShell 1,0 e o Windows PowerShell 2,0. Os exemplos subsequentes usam módulos em vez de snap-ins para que eles exijam o Windows PowerShell 2,0.

## <a name="example"></a>Exemplo

Este exemplo mostra como criar um cmdlet simples e seu snap-in.

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;             //Windows PowerShell namespace
using System.ComponentModel;

namespace Microsoft.Samples.PowerShell.Commands
{

   #region GetProcCommand

   /// <summary>
   /// This class implements the Get-Proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Cmdlet Overrides

      /// <summary>
      /// The ProcessRecord method calls the Process.GetProcesses
      /// method to retrieve the processes of the local computer.
      /// Then, the WriteObject method writes the associated processes
      /// to the pipeline.
      /// </summary>
      protected override void ProcessRecord()
      {
         // Retrieve the current processes.
         Process[] processes = Process.GetProcesses();

         // Write the processes to the pipeline to make them available
         // to the next cmdlet. The second argument (true) tells Windows
         // PowerShell to enumerate the array and to send one process
         // object at a time to the pipeline.
         WriteObject(processes, true);
      }

      #endregion Overrides

   } //GetProcCommand

   #endregion GetProcCommand

   #region PowerShell snap-in

   /// <summary>
   /// Create this sample as an PowerShell snap-in
   /// </summary>
   [RunInstaller(true)]
   public class GetProcPSSnapIn01 : PSSnapIn
   {
       /// <summary>
       /// Create an instance of the GetProcPSSnapIn01
       /// </summary>
       public GetProcPSSnapIn01()
           : base()
       {
       }

       /// <summary>
       /// Get a name for this PowerShell snap-in. This name will be used in registering
       /// this PowerShell snap-in.
       /// </summary>
       public override string Name
       {
           get
           {
               return "GetProcPSSnapIn01";
           }
       }

       /// <summary>
       /// Vendor information for this PowerShell snap-in.
       /// </summary>
       public override string Vendor
       {
           get
           {
               return "Microsoft";
           }
       }

       /// <summary>
       /// Gets resource information for vendor. This is a string of format:
       /// resourceBaseName,resourceName.
       /// </summary>
       public override string VendorResource
       {
           get
           {
               return "GetProcPSSnapIn01,Microsoft";
           }
       }

       /// <summary>
       /// Description of this PowerShell snap-in.
       /// </summary>
       public override string Description
       {
           get
           {
               return "This is a PowerShell snap-in that includes the get-proc cmdlet.";
           }
       }
   }

   #endregion PowerShell snap-in
}
```

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
