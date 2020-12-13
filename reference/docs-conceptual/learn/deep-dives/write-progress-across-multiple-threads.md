---
title: Mostrar o progresso durante o multi-threading
description: Como usar Write-Progress em vários threads com Foreach-Object -Parallel
ms.date: 08/02/2020
ms.openlocfilehash: 909fc1bbdeded8845b1955e3384fb55db7173030
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "89410835"
---
# <a name="writing-progress-across-multiple-threads-with-foreach-parallel"></a>Writing Progress em vários threads com Foreach Parallel

A partir do PowerShell 7.0, é possível trabalhar em vários threads simultaneamente usando o parâmetro **Parallel** no cmdlet [ForEach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object). No entanto, monitorar o progresso desses threads pode ser um desafio. Normalmente, você pode monitorar o progresso de um processo usando [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress).
No entanto, como o PowerShell usa um runspace separado para cada thread ao usar **Parallel**, enviar o progresso de volta ao host não é tão simples quanto o uso normal de `Write-Progress`.

## <a name="using-a-synced-hashtable-to-track-progress"></a>Usar uma tabela de hash sincronizada para acompanhar o progresso

Ao gravar o progresso de vários threads, o controle torna-se difícil porque, ao executar processos paralelos no PowerShell, cada processo tem seu próprio runspace. Para contornar isso, você pode usar uma [tabela de hash sincronizada](/dotnet/api/system.collections.hashtable.synchronized). Uma tabela de hash sincronizada é uma estrutura de dados thread-safe que pode ser modificada por vários threads simultaneamente, sem gerar um erro.

### <a name="set-up"></a>Configuração

Uma das desvantagens dessa abordagem é a configuração complexa, de certa forma, para garantir que tudo seja executado sem erros.

```powershell
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)
```

Esta seção cria três estruturas de dados diferentes, para três finalidades diferentes.

A variável `$dataSet` armazena uma matriz de tabelas de hash usada para coordenar as próximas etapas sem o risco de modificação. Se uma coleção de objetos for modificada durante a iteração pela coleção, o PowerShell vai gerar um erro. Você deve manter a coleção de objetos no loop, separada dos objetos que estão sendo modificados. A chave `Id` em cada tabela de hash é o identificador de um processo de simulação. A chave `Wait` simula a carga de trabalho de cada processo de simulação que está sendo rastreado.

A variável `$origin` armazena uma tabela de hash aninhada com cada chave sendo uma das IDs do processo de simulação.
Em seguida, ela é usada para hidratar a tabela de hash sincronizada armazenada na variável `$sync`. A variável `$sync` é responsável por relatar o progresso para o runspace pai, que exibe o progresso.

### <a name="running-the-processes"></a>Executar os processos

Esta seção executa os processos de várias threads e cria algumas das saídas usadas para exibir o progresso.

```powershell
$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}
```

Os processos de simulação são enviados para `Foreach-Object` e iniciados como trabalhos. O **ThrottleLimit** é definido como **3** para realçar a execução de vários processos em uma fila. Os trabalhos são armazenados na variável `$job` e nos permitem saber quando todos os processos foram concluídos posteriormente.

Ao usar a instrução `using:` para fazer referência a uma variável de escopo pai no PowerShell, você não pode usar expressões para torná-la dinâmica. Por exemplo, se você tentou criar a variável `$process` como essa, `$process = $using:sync.$($PSItem.id)`, você receberia um erro informando que não pode usar expressões ali. Portanto, criamos a variável `$syncCopy` para referenciar e modificar a variável `$sync` sem o risco de falhar.

Em seguida, criamos uma tabela de hash para representar o progresso do processo atualmente no loop usando a variável `$process` referenciando as chaves de tabela de hash sincronizadas. As chaves **Activity** e **Status** são usadas como valores de parâmetro para `Write-Progress` exibir o status de um processo de simulação específico na próxima seção.

O loop `foreach` é apenas uma forma de simular o funcionamento do processo e é aleatório com base no atributo `$dataSet` **Wait** para definir `Start-Sleep` usando milissegundos. A forma como você calcula o progresso do processo pode variar.

### <a name="displaying-the-progress-of-multiple-processes"></a>Exibir o progresso de vários processos

Agora que os processos de simulação estão sendo executados como trabalhos, podemos começar a gravar o progresso dos processos na janela do PowerShell.

```powershell
while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

A variável `$job` contém o trabalho **pai** e tem um trabalho **filho** para cada um dos processos de simulação. Embora qualquer um dos trabalhos filho ainda esteja em execução, o trabalho pai **State** permanecerá "Em execução". Isso permite usar o loop `while` para atualizar continuamente o progresso de cada processo até que todos sejam concluídos.

Dentro do loop while, fazemos um loop em cada uma das chaves na variável `$sync`. Como essa é uma tabela de hash sincronizada, ela é constantemente atualizada, mas ainda pode ser acessada sem gerar erros.

Há uma verificação para garantir que o processo relatado esteja realmente em execução com o método `IsNullOrEmpty()`. Se o processo não tiver sido iniciado, o loop não o relatará e passará para o próximo até chegar a um processo que foi iniciado. Se o processo for iniciado, a tabela de hash da chave atual será usada para fragmentar os parâmetros para `Write-Progress`.

### <a name="full-example"></a>Exemplo completo

```powershell
# Example workload
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)

$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}

while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

## <a name="related-links"></a>Links Relacionados

- [about_Jobs](/powershell/module/Microsoft.PowerShell.Core/About/about_Jobs)
- [about_Scopes](/powershell/module/Microsoft.PowerShell.Core/About/about_Scopes)
- [about_Splatting](/powershell/module/Microsoft.PowerShell.Core/About/about_Splatting)
