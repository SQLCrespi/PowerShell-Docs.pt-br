---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: 63a08958a1e22b29f914bfb9b4c6be05e6939b8d
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2021
ms.locfileid: "106274420"
---
# Add-Type

## SINOPSE
Adiciona uma classe de Microsoft .NET a uma sessão do PowerShell.

## SYNTAX

### From (padrão)

```
Add-Type [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### FromMember

```
Add-Type [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>]
 [-UsingNamespace <String[]>] [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### FromPath

```
Add-Type [-Path] <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### FromLiteralPath

```
Add-Type -LiteralPath <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### FromAssemblyName

```
Add-Type -AssemblyName <String[]> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

O `Add-Type` cmdlet permite que você defina uma classe de Microsoft .NET Core na sua sessão do PowerShell. Em seguida, você pode instanciar objetos usando o `New-Object` cmdlet e usar os objetos da mesma forma que usaria qualquer objeto .NET Core. Se você adicionar um `Add-Type` comando ao seu perfil do PowerShell, a classe estará disponível em todas as sessões do PowerShell.

Você pode especificar o tipo especificando um assembly existente ou arquivos de código-fonte, ou você pode especificar o código-fonte embutido ou salvo em uma variável. Você pode até mesmo especificar apenas um método e `Add-Type` define e gera a classe. No Windows, você pode usar esse recurso para fazer chamadas de invocação de plataforma (P/Invoke) para funções não gerenciadas no PowerShell. Se você especificar o código-fonte, `Add-Type` o compilará o código-fonte especificado e gerará um assembly na memória que contenha os novos tipos .NET Core.

Você pode usar os parâmetros de `Add-Type` para especificar um idioma alternativo e um compilador, C# é o padrão, opções de compilador, dependências de assembly, o namespace de classe, os nomes do tipo e o assembly resultante.

A partir do PowerShell 7, `Add-Type` o não compilará um tipo se já existir um tipo com o mesmo nome. Além disso, `Add-Type` o procura assemblies em uma `ref` pasta sob a pasta que contém `pwsh.dll` .

## EXEMPLOS

### Exemplo 1: adicionar um tipo .NET a uma sessão

Este exemplo adiciona a classe **BasicTest** à sessão especificando o código-fonte armazenado em uma variável. A classe **BasicTest** é usada para adicionar inteiros, criar um objeto e multiplicar inteiros.

```powershell
$Source = @"
public class BasicTest
{
  public static int Add(int a, int b)
    {
        return (a + b);
    }
  public int Multiply(int a, int b)
    {
    return (a * b);
    }
}
"@

Add-Type -TypeDefinition $Source
[BasicTest]::Add(4, 3)
$BasicTestObject = New-Object BasicTest
$BasicTestObject.Multiply(5, 2)
```

A `$Source` variável armazena o código-fonte da classe. O tipo tem um método estático chamado `Add` e um método não estático chamado `Multiply` .

O `Add-Type` cmdlet adiciona a classe à sessão. Como ele está usando código-fonte embutido, o comando usa o parâmetro **TypeDefinition** para especificar o código na `$Source` variável.

O `Add` método estático da classe **BasicTest** usa os caracteres de dois-pontos duplos ( `::` ) para especificar um membro estático da classe. Os inteiros são adicionados e a soma é exibida.

O `New-Object` cmdlet instancia uma instância da classe **BasicTest** . Ele salva o novo objeto na `$BasicTestObject` variável.

`$BasicTestObject` usa o `Multiply` método. Os inteiros são multiplicados e o produto é exibido.

### Exemplo 2: examinar um tipo adicionado

Este exemplo usa o `Get-Member` cmdlet para examinar os objetos que os `Add-Type` `New-Object` cmdlets e criados no **exemplo 1**.

```powershell
[BasicTest] | Get-Member
```

```Output
   TypeName: System.RuntimeType

Name                 MemberType Definition
----                 ---------- ----------
AsType               Method     type AsType()
Clone                Method     System.Object Clone(), System.Object ICloneable.Clone()
Equals               Method     bool Equals(System.Object obj), bool Equals(type o)
FindInterfaces       Method     type[] FindInterfaces(System.Reflection.TypeFilter filter...
...
```

```powershell
[BasicTest] | Get-Member -Static
```

```Output
  TypeName: BasicTest

Name            MemberType Definition
----            ---------- ----------
Add             Method     static int Add(int a, int b)
Equals          Method     static bool Equals(System.Object objA, System.Object objB)
new             Method     BasicTest new()
ReferenceEquals Method     static bool ReferenceEquals(System.Object objA, System.Object objB)
```

```powershell
$BasicTestObject | Get-Member
```

```Output
   TypeName: BasicTest

Name        MemberType Definition
----        ---------- ----------
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
Multiply    Method     int Multiply(int a, int b)
ToString    Method     string ToString()
```

O `Get-Member` cmdlet obtém o tipo e os membros da classe **BasicTest** que `Add-Type` foi adicionada à sessão. O `Get-Member` comando revela que é um objeto **System. RuntimeType** , que é derivado da classe **System. Object** .

O `Get-Member` parâmetro **static** Obtém as propriedades e os métodos estáticos da classe **BasicTest** . A saída mostra que o `Add` método está incluído.

O `Get-Member` cmdlet obtém os membros do objeto armazenado na `$BasicTestObject` variável.
`$BasicTestObject` foi criado usando o `New-Object` cmdlet com a classe **BasicTest** . A saída revela que o valor da `$BasicTestObject` variável é uma instância da classe **BasicTest** e que ela inclui um membro chamado `Multiply` .

### Exemplo 3: adicionar tipos de um assembly

Este exemplo adiciona as classes do `NJsonSchema.dll` assembly à sessão atual.

```powershell
Set-Location -Path $PSHOME
$AccType = Add-Type -AssemblyName *jsonschema* -PassThru
```

`Set-Location` usa o parâmetro **path** para especificar a `$PSHOME` variável. A variável faz referência ao diretório de instalação do PowerShell onde o arquivo DLL está localizado.

A `$AccType` variável armazena um objeto criado com o `Add-Type` cmdlet. `Add-Type` usa o parâmetro **AssemblyName** para especificar o nome do assembly. O `*` caractere curinga asterisco () permite que você obtenha o assembly correto mesmo quando não tiver certeza do nome ou de sua grafia. O parâmetro **PassThru** gera objetos que representam as classes que são adicionadas à sessão.

### Exemplo 4: chamar APIs nativas do Windows

Este exemplo demonstra como chamar APIs nativas do Windows no PowerShell. `Add-Type` usa o mecanismo de invocação de plataforma (P/Invoke) para chamar uma função no `User32.dll` do PowerShell. Este exemplo só funciona em computadores que executam o sistema operacional Windows.

```powershell
$Signature = @"
[DllImport("user32.dll")]public static extern bool ShowWindowAsync(IntPtr hWnd, int nCmdShow);
"@

$ShowWindowAsync = Add-Type -MemberDefinition $Signature -Name "Win32ShowWindowAsync" -Namespace Win32Functions -PassThru

# Minimize the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $pid).MainWindowHandle, 2)

# Restore the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $Pid).MainWindowHandle, 4)
```

A `$Signature` variável armazena a assinatura C# da `ShowWindowAsync` função. Para garantir que o método resultante seja visível em uma sessão do PowerShell, a `public` palavra-chave foi adicionada à assinatura padrão. Para obter mais informações, consulte [função ShowWindowAsync](/windows/win32/api/winuser/nf-winuser-showwindowasync).

A `$ShowWindowAsync` variável armazena o objeto criado pelo parâmetro `Add-Type` **PassThru** .
O `Add-Type` cmdlet adiciona a `ShowWindowAsync` função à sessão do PowerShell como um método estático. O comando usa o parâmetro **MemberDefinition** para especificar a definição de método salva na `$Signature` variável. O comando usa os parâmetros **Name** e **Namespace** para especificar um nome e um namespace para a classe. O parâmetro **PassThru** gera um objeto que representa os tipos.

O novo `ShowWindowAsync` método estático é usado nos comandos para minimizar e restaurar o console do PowerShell. O método usa dois parâmetros: o identificador de janela e um inteiro que especifica como a janela é exibida.

Para minimizar o console do PowerShell, o `ShowWindowAsync` usa o `Get-Process` cmdlet com a `$PID` variável automática para obter o processo que está hospedando a sessão atual do PowerShell. Em seguida, ele usa a propriedade **MainWindowHandle** do processo atual e um valor de `2` , que representa o `SW_MINIMIZE` valor.

Para restaurar a janela, o `ShowWindowAsync` usa um valor de `4` para a posição da janela, que representa o `SW_RESTORE` valor.

Para maximizar a janela, use o valor de `3` que representa `SW_MAXIMIZE` .

## PARAMETERS

### -AssemblyName

Especifica o nome de um assembly que inclui os tipos. `Add-Type` usa os tipos do assembly especificado. Esse parâmetro é necessário quando você está criando tipos com base em um nome de assembly.

Insira o nome completo ou simples, também conhecido como o nome parcial, de um assembly. Caracteres curinga são permitidos no nome do assembly. Se você inserir um nome simples ou parcial, `Add-Type` o o resolverá para o nome completo e, em seguida, usará o nome completo para carregar o assembly.

Esse parâmetro não aceita um caminho ou um nome de arquivo. Para inserir o caminho para o arquivo DLL (biblioteca de vínculo dinâmico) do assembly, use o parâmetro **path** .

```yaml
Type: System.String[]
Parameter Sets: FromAssemblyName
Aliases: AN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Compiladoroptions

Especifica as opções para o compilador de código fonte. Essas opções são enviadas sem revisão para o compilador.

Esse parâmetro permite que você direcione o compilador para gerar um arquivo executável, inserir recursos ou definir opções de linha de comando, como a `/unsafe` opção.

Você não pode usar os parâmetros **CompilerOptions** e **ReferencedAssemblies** no mesmo comando.

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreWarnings

Ignora os avisos do compilador. Use esse parâmetro para evitar o `Add-Type` tratamento de avisos do compilador como erros.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Idioma

Especifica a linguagem usada no código-fonte. O valor aceitável para esse parâmetro é **Csharp**.

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Especifica o caminho para arquivos de código fonte ou arquivos DLL de assembly que contêm os tipos. Ao contrário do **caminho**, o valor do parâmetro **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemberDefinition

Especifica novas propriedades ou métodos para a classe. `Add-Type` gera o código de modelo necessário para dar suporte às propriedades ou aos métodos.

No Windows, você pode usar esse recurso para fazer chamadas de invocação de plataforma (P/Invoke) para funções não gerenciadas no PowerShell.

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica o nome da classe a ser criada. Esse parâmetro é necessário ao gerar um tipo por meio de uma definição de membro.

O nome do tipo e o namespace devem ser exclusivos dentro de uma sessão. Você não pode descarregar um tipo ou alterá-lo.
Para alterar o código de um tipo, você deve alterar o nome ou iniciar uma nova sessão do PowerShell.
Caso contrário, o comando falhará.

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Especifica um namespace para o tipo.

Se esse parâmetro não estiver incluído no comando, o tipo será criado no namespace **Microsoft. PowerShell. Commands. AddType. AutoGeneratedTypes** . Se o parâmetro for incluído no comando com um valor de cadeia de caracteres vazio ou um valor de `$Null` , o tipo será gerado no namespace global.

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputAssembly

Gera um arquivo DLL para o assembly com o nome especificado no local. Insira um caminho e um nome de arquivo opcionais. Caracteres curinga são permitidos. Por padrão, `Add-Type` o gera o assembly somente na memória.

```yaml
Type: System.String
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -OutputType

Especifica o tipo de saída do assembly de saída. Por padrão, nenhum tipo de saída é especificado. Este parâmetro é válido somente quando um assembly de saída é especificado no comando. Para obter mais informações sobre os valores, consulte [Enumeração OutputAssemblyType](/dotnet/api/microsoft.powershell.commands.outputassemblytype).

Os valores aceitáveis para esse parâmetro são os seguintes:

- ConsoleApplication
- Biblioteca
- WindowsApplication

> [!IMPORTANT]
> A partir do PowerShell 7,1 `ConsoleApplication` e `WindowsApplication` não têm suporte e o PowerShell gera um erro de encerramento se ambos forem especificados como valores para o parâmetro **OutputType** .

```yaml
Type: Microsoft.PowerShell.Commands.OutputAssemblyType
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OT
Accepted values: ConsoleApplication, Library, WindowsApplication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto **System.Runtime** que representa os tipos adicionados. Por padrão, esse cmdlet não gera nenhuma saída.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho para arquivos de código fonte ou arquivos DLL de assembly que contêm os tipos.

Se você enviar arquivos de código-fonte, `Add-Type` o compilará o código nos arquivos e criará um assembly na memória dos tipos. A extensão de arquivo especificada no valor de **path** determina o compilador que o `Add-Type` usa.

Se você enviar um arquivo de assembly, `Add-Type` o usará os tipos do assembly. Para especificar um assembly na memória ou o cache de assembly global, use o parâmetro **AssemblyName**.

```yaml
Type: System.String[]
Parameter Sets: FromPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReferencedAssemblies

Especifica os assemblies dos quais depende o tipo. Por padrão, o `Add-Type` faz referência a `System.dll` e `System.Management.Automation.dll` . Os assemblies que você especificar usando esse parâmetro são referenciados além os assemblies padrão.

A partir do PowerShell 6, o **ReferencedAssemblies** não inclui os assemblies do .NET padrão. Você deve incluir uma referência específica a eles no valor passado para esse parâmetro.

Você não pode usar os parâmetros **CompilerOptions** e **ReferencedAssemblies** no mesmo comando.

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: RA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeDefinition

Especifica o código-fonte que contém as definições de tipo. Insira o código-fonte em uma cadeia de caracteres ou cadeia de caracteres here, ou insira uma variável que contenha o código-fonte. Para obter mais informações sobre as cadeias de caracteres aqui, consulte [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).

Inclua uma declaração de namespace em sua definição de tipo. Se você omitir a declaração de namespace, seu tipo pode ter o mesmo nome que outro tipo ou o atalho para outro tipo, causando uma substituição não intencional. Por exemplo, se você definir um tipo chamado **exceção**, os scripts que usam **exceção** como o atalho para **System. Exception** falharão.

```yaml
Type: System.String
Parameter Sets: FromSource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsingNamespace

Especifica outros namespaces que são necessários para a classe. Isso é muito parecido com a palavra-chave C#, `Using` .

Por padrão, `Add-Type` o faz referência ao namespace do **sistema** . Quando o parâmetro **MemberDefinition** é usado, `Add-Type` o também faz referência ao namespace **System. Runtime. InteropServices** por padrão. Os namespaces que você adiciona usando o parâmetro **UsingNamespace** são mencionados além dos namespaces padrão.

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases: Using

Required: False
Position: Named
Default value: System namespace
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Você não pode enviar objetos pelo pipeline para o `Add-Type` .

## SAÍDAS

### Nenhum ou System. Type

Quando você usa o parâmetro **PassThru** , `Add-Type` retorna um objeto **System. Type** que representa o novo tipo. Caso contrário, esse cmdlet não gerará nenhuma saída.

## OBSERVAÇÕES

Os tipos que você adiciona existem apenas na sessão atual. Para usar os tipos em todas as sessões, adicione-as ao seu perfil do PowerShell. Para obter mais informações sobre o perfil, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

Os nomes de tipo e namespaces devem ser exclusivos em uma sessão. Você não pode descarregar um tipo ou alterá-lo. Se você precisar alterar o código para um tipo, deverá alterar o nome ou iniciar uma nova sessão do PowerShell.
Caso contrário, o comando falhará.

No Windows PowerShell (versão 5,1 e inferior), você precisa usar o `Add-Type` para qualquer coisa que ainda não esteja carregada. Normalmente, isso se aplica a assemblies encontrados no GAC (cache de assembly global).
No PowerShell 6 e superior, não há nenhum GAC, portanto, o PowerShell instala seus próprios assemblies no `$PSHome` .
Esses assemblies são carregados automaticamente na solicitação, portanto, não é necessário usá `Add-Type` -los para carregá-los. No entanto, o uso `Add-Type` do ainda é permitido para permitir que os scripts sejam implicitamente compatíveis com qualquer versão do PowerShell.

Os assemblies no GAC podem ser carregados pelo nome do tipo, em vez de por caminho. O carregamento de assemblies de um caminho arbitrário requer `Add-Type` , pois esses assemblies não podem ser carregados automaticamente.

## LINKS RELACIONADOS

[about_Profiles](../Microsoft.PowerShell.Core/About/about_profiles.md)

[about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[Add-Member](Add-Member.md)

[New-Object](New-Object.md)

[OutputAssemblyType](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[Invocação de plataforma (P/Invoke)](/dotnet/standard/native-interop/pinvoke)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
