---
title: Exemplo de Events01 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c7b0f759ca6f3c078649a462eac1713e8214a237
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774450"
---
# <a name="events01-sample"></a>Amostra Events01

Este exemplo mostra como criar um cmdlet que permite ao usuário se registrar para eventos que são gerados por [System. IO. FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).
Com esse cmdlet, os usuários podem registrar uma ação a ser executada quando um arquivo é criado em um diretório específico.
Este exemplo deriva da classe base [Microsoft. PowerShell. Commands. ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) .

## <a name="how-to-build-the-sample-by-using-visual-studio"></a>Como criar o exemplo usando o Visual Studio.

1. Com o SDK do Windows PowerShell 2,0 instalado, navegue até a pasta Events01.
   O local padrão é `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01`.

2. Clique duas vezes no ícone do arquivo da solução (. sln).
   Isso abre o projeto de exemplo no Microsoft Visual Studio.

3. No menu **Compilar**, selecione **Compilar Solução**.
   A biblioteca do exemplo será criada no padrão `\bin` ou `\bin\debug` nas pastas.

### <a name="how-to-run-the-sample"></a>Como executar a amostra

1. Crie a seguinte pasta de módulo:

    `[user]/documents/windowspowershell/modules/events01`

2. Copie o arquivo de biblioteca do exemplo para a pasta do módulo.

3. Inicie o Windows PowerShell.

4. Execute o seguinte comando para carregar o cmdlet no Windows PowerShell:

    ```powershell
    import-module events01
    ```

5. Use o cmdlet Register-FileSystemEvent para registrar uma ação que irá gravar uma mensagem quando um arquivo for criado no diretório temporário.

    ```powershell
    Register-FileSystemEvent $env:temp Created -filter "*.txt" -action { Write-Host "A file was created in the TEMP directory" }
    ```

6. Crie um arquivo no diretório TEMP e observe que a ação é executada (a mensagem é exibida).

Esta é uma saída de exemplo que resulta seguindo estas etapas.

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

Este exemplo requer o Windows PowerShell 2,0.

## <a name="demonstrates"></a>Demonstra

Este exemplo demonstra o seguinte.

### <a name="how-to-write-a-cmdlet-for-event-registration"></a>Como escrever um cmdlet para o registro de eventos

O cmdlet deriva da classe [Microsoft. PowerShell. Commands. ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) , que fornece suporte para parâmetros comuns aos `Register-*Event` cmdlets.
Os cmdlets que são derivados de [Microsoft. PowerShell. Commands. ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) precisam apenas definir seus parâmetros específicos e substituir `GetSourceObject` os `GetSourceObjectEventName` métodos e abstract.

## <a name="example"></a>Exemplo

Este exemplo mostra como registrar eventos gerados por [System. IO. FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).

```csharp
namespace Sample
{
    using System;
    using System.IO;
    using System.Management.Automation;
    using System.Management.Automation.Runspaces;
    using Microsoft.PowerShell.Commands;

    [Cmdlet(VerbsLifecycle.Register, "FileSystemEvent")]
    public class RegisterObjectEventCommand : ObjectEventRegistrationBase
    {
        /// <summary>The FileSystemWatcher that exposes the events.</summary>
        private FileSystemWatcher fileSystemWatcher = new FileSystemWatcher();

        /// <summary>Name of the event to which the cmdlet registers.</summary>
        private string eventName = null;

        /// <summary>
        /// Gets or sets the path that will be monitored by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = true, Position = 0)]
        public string Path
        {
            get
            {
                return this.fileSystemWatcher.Path;
            }

            set
            {
                this.fileSystemWatcher.Path = value;
            }
        }

        /// <summary>
        /// Gets or sets the name of the event to which the cmdlet registers.
        /// <para>
        /// Currently System.IO.FileSystemWatcher exposes 6 events: Changed, Created,
        /// Deleted, Disposed, Error, and Renamed. Check the MSDN documentation of
        /// FileSystemWatcher for details on each event.
        /// </para>
        /// </summary>
        [Parameter(Mandatory = true, Position = 1)]
        public string EventName
        {
            get
            {
                return this.eventName;
            }

            set
            {
                this.eventName = value;
            }
        }

        /// <summary>
        /// Gets or sets the filter that will be user by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = false)]
        public string Filter
        {
            get
            {
                return this.fileSystemWatcher.Filter;
            }

            set
            {
                this.fileSystemWatcher.Filter = value;
            }
        }

        /// <summary>
        /// Derived classes must implement this method to return the object that generates
        /// the events to be monitored.
        /// </summary>
        /// <returns> This sample returns an instance of System.IO.FileSystemWatcher</returns>
        protected override object GetSourceObject()
        {
            return this.fileSystemWatcher;
        }

        /// <summary>
        /// Derived classes must implement this method to return the name of the event to
        /// be monitored. This event must be exposed by the input object.
        /// </summary>
        /// <returns> This sample returns the event specified by the user with the -EventName parameter.</returns>
        protected override string GetSourceObjectEventName()
        {
            return this.eventName;
        }
    }
}
```

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](writing-a-windows-powershell-cmdlet.md)
