---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: 53c06982abcf980897c049b6f6bd0c159f2eb4b5
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524681"
---
# Start-Process

## SINOPSE
Inicia um ou mais processos no computador local.

## SYNTAX

### Padrão (padrão)

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UseShellExecute

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Start-Process` cmdlet inicia um ou mais processos no computador local. Por padrão, `Start-Process` o cria um novo processo que herda todas as variáveis de ambiente definidas no processo atual.

Para especificar o programa que é executado no processo, insira um arquivo executável ou arquivo de script, ou um arquivo que pode ser aberto usando um programa no computador. Se você especificar um arquivo não executável, `Start-Process` o iniciará o programa associado ao arquivo, semelhante ao `Invoke-Item` cmdlet.

Você pode usar os parâmetros de `Start-Process` para especificar opções, como carregar um perfil de usuário, iniciar o processo em uma nova janela ou usar credenciais alternativas.

## EXEMPLOS

### Exemplo 1: iniciar um processo que usa valores padrão

Este exemplo inicia um processo que usa o `Sort.exe` arquivo na pasta atual. O comando usa todos os valores padrão, incluindo o estilo de janela padrão, a pasta de trabalho e as credenciais.

```powershell
Start-Process -FilePath "sort.exe"
```

### Exemplo 2: imprimir um arquivo de texto

Este exemplo inicia um processo que imprime o `C:\PS-Test\MyFile.txt` arquivo.

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### Exemplo 3: iniciar um processo para classificar itens em um novo arquivo

Este exemplo inicia um processo que classifica itens no `Testsort.txt` arquivo e retorna os itens classificados nos `Sorted.txt` arquivos. Todos os erros são gravados no `SortError.txt` arquivo.

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

O parâmetro **UseNewEnvironment** especifica que o processo é executado com suas próprias variáveis de ambiente.

### Exemplo 4: iniciar um processo em uma janela maximizada

Este exemplo inicia o `Notepad.exe` processo. Ele maximiza a janela e mantém a janela até que o processo seja concluído.

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### Exemplo 5: iniciar o PowerShell como administrador

Este exemplo inicia o PowerShell usando a opção **Executar como administrador** .

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### Exemplo 6: usando verbos diferentes para iniciar um processo

Este exemplo mostra como localizar os verbos que podem ser usados ao iniciar um processo. Os verbos disponíveis são determinados pela extensão de nome do arquivo que é executado no processo.

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

O exemplo usa `New-Object` para criar um objeto **System. Diagnostics. ProcessStartInfo** para **PowerShell.exe** , o arquivo que é executado no processo do PowerShell. A propriedade **verbos** do objeto **ProcessStartInfo** mostra que você pode usar os verbos **Open** e **runas** com `PowerShell.exe` , ou com qualquer processo que execute um `.exe` arquivo.

### Exemplo 7: especificando argumentos para o processo

Ambos os comandos iniciam o interpretador de comandos do Windows, emitindo um `dir` comando na `Program Files` pasta. Como this FolderName contém um espaço, o valor precisa ser circundado com aspas de escape.
Observe que o primeiro comando especifica uma cadeia de caracteres como **argumentolist**. O segundo comando é uma matriz de cadeia de caracteres.

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

### Exemplo 8: criar um processo desanexado no Linux

No Windows, `Start-Process` o cria um processo independente que permanece em execução independentemente do Shell de inicialização. Em plataformas não Windows, o processo recentemente iniciado é anexado ao shell que foi iniciado. Se o Shell de inicialização estiver fechado, o processo filho será encerrado.

Para evitar o encerramento do processo filho em plataformas semelhantes ao Unix, você pode combinar `Start-Process` com `nohup` . O exemplo a seguir inicia uma instância em segundo plano do PowerShell no Linux que permanece ativa mesmo depois que você fecha a sessão de inicialização. O `nohup` comando coleta a saída no arquivo `nohup.out` no diretório atual.

```powershell
# Runs for 2 minutes and appends output to ./nohup.out
Start-Process nohup 'pwsh -noprofile -c "1..120 | % { Write-Host . -NoNewline; sleep 1 }"'
```

Neste exemplo, `Start-Process` o executa o comando do Linux `nohup` , que é iniciado `pwsh` como um processo desanexado. Para obter mais informações, consulte a página do manual para [nohup](https://linux.die.net/man/1/nohup).

## PARAMETERS

### -ArgumentList

Especifica os parâmetros ou valores de parâmetro a serem usados quando esse cmdlet iniciar o processo. Os argumentos podem ser aceitos como uma única cadeia de caracteres com os argumentos separados por espaços ou como uma matriz de cadeias de caracteres separadas por vírgulas.

Se os parâmetros ou os valores de parâmetro contiverem um espaço, eles precisarão estar entre aspas duplas de escape. Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. Por padrão, o cmdlet usa as credenciais do usuário atual.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, você será solicitado a inserir a senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Default
Aliases: RunAs

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Especifica o caminho opcional e o nome do arquivo do programa que é executado no processo. Insira o nome de um arquivo executável ou de um documento, como um `.txt` arquivo ou `.doc` , que está associado a um programa no computador. Este parâmetro é necessário.

Se você especificar apenas um nome de arquivo, use o parâmetro **WorkingDirectory** para especificar o caminho.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadUserProfile

Indica que esse cmdlet carrega o perfil de usuário do Windows armazenado na `HKEY_USERS` chave do registro para o usuário atual. O parâmetro não se aplica a sistemas não Windows.

Esse parâmetro não afeta os perfis do PowerShell. Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: Lup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoNewWindow

Inicie o novo processo na janela do console atual. Por padrão no Windows, o PowerShell abre uma nova janela. Em sistemas não Windows, você nunca Obtém uma nova janela de terminal.

Você não pode usar os parâmetros **NoNewWindow** e **WindowStyle** no mesmo comando.

O parâmetro não se aplica a sistemas não Windows.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: nnw

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto de processo para cada processo que o cmdlet iniciou. Por padrão, este cmdlet não gera saída.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardError

Especifica um arquivo. Esse cmdlet envia todos os erros gerados pelo processo para um arquivo que você especificar.
Insira o caminho e o nome do arquivo. Por padrão, os erros são exibidos no console.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardInput

Especifica um arquivo. Esse cmdlet lê a entrada do arquivo especificado. Insira o caminho e o nome do arquivo de entrada. Por padrão, o processo obtém sua entrada do teclado.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardOutput

Especifica um arquivo. Esse cmdlet envia a saída gerada pelo processo para um arquivo que você especificar.
Insira o caminho e o nome do arquivo. Por padrão, a saída é exibida no console.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseNewEnvironment

Indica que esse cmdlet usa novas variáveis de ambiente especificadas para o processo. Por padrão, o processo iniciado é executado com as variáveis de ambiente herdadas do processo pai.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Verbo

Especifica um verbo a ser usado quando esse cmdlet iniciar o processo. Os verbos disponíveis são determinados pela extensão de nome do arquivo que é executado no processo.

A tabela a seguir mostra os verbos para alguns tipos de arquivos comuns do processo.

| Tipo de arquivo |                Verbos                |
| --------- | ----------------------------------- |
| .cmd      | Editar, abrir, imprimir, executar como, RunAsUser |
| .exe      | Abrir, RunAs, RunAsUser              |
| .txt      | Abrir, imprimir, imprimir em                |
| .wav      | Abrir, reproduzir                          |

Para localizar os verbos que podem ser usados com o arquivo que é executado em um processo, use o `New-Object` cmdlet para criar um objeto **System. Diagnostics. ProcessStartInfo** para o arquivo. Os verbos disponíveis estão na propriedade **verbos** do objeto **ProcessStartInfo** . Para obter detalhes, consulte os exemplos.

O parâmetro não se aplica a sistemas não Windows.

```yaml
Type: System.String
Parameter Sets: UseShellExecute
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Indica que esse cmdlet aguarda o processo especificado e seus descendentes serem concluídos antes de aceitar mais entrada. Esse parâmetro suprime o prompt de comando ou retém a janela até que os processos sejam concluídos.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowStyle

Especifica o estado da janela que é usada para o novo processo. Os valores aceitáveis para esse parâmetro são: **normal** , **oculto** , **minimizado** e **maximizado**. O valor padrão é **normal**.

Você não pode usar os parâmetros **WindowStyle** e **NoNewWindow** no mesmo comando.

O parâmetro não se aplica a sistemas não Windows.

```yaml
Type: System.Diagnostics.ProcessWindowStyle
Parameter Sets: (All)
Aliases:
Accepted values: Normal, Hidden, Minimized, Maximized

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkingDirectory

Especifica o local em que o novo processo deve ser iniciado. O padrão é o local do arquivo executável ou do documento que está sendo iniciado. Não há suporte para caracteres curinga. O nome do caminho não deve conter caracteres que seriam interpretados como curingas.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Nenhum, System. Diagnostics. Process

Esse cmdlet gera um objeto **System. Diagnostics. Process** , se você especificar o parâmetro **PassThru** . Caso contrário, este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

- Esse cmdlet é implementado usando o método **Start** da classe **System. Diagnostics. Process** . Para obter mais informações sobre esse método, consulte o [método Process. Start](/dotnet/api/system.diagnostics.process.start#overloads).

- No Windows, quando você usa o **UseNewEnvironment** , o novo processo inicia apenas com as variáveis de ambiente padrão definidas para o escopo da **máquina** . Isso tem o lado de afetar que o `$env:USERNAME` está definido como **System**. Nenhuma das variáveis do escopo do **usuário** está incluída.

- No Windows, o caso de uso mais comum para o `Start-Process` é usar o parâmetro **Wait** para bloquear o progresso até que o novo processo saia. No sistema não Windows, raramente isso é necessário, pois o comportamento padrão para aplicativos de linha de comando é equivalente a `Start-Process -Wait` .

- Ao usar `Start-Process` em sistemas não Windows, você nunca Obtém uma nova janela de terminal.

## LINKS RELACIONADOS

[about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Service](Start-Service.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
