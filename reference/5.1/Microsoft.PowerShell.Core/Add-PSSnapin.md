---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PSSnapin
ms.openlocfilehash: a21c2974fd66a9b02929752ae487c8995579b8a7
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388817"
---
# Add-PSSnapin

## SINOPSE
Adiciona um ou mais snap-ins do Windows PowerShell à sessão atual.

## SYNTAX

```
Add-PSSnapin [-Name] <String[]> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

O `Add-PSSnapin` cmdlet adiciona snap-ins do Windows PowerShell registrados à sessão atual. Depois que os snap-ins são adicionados, você pode usar os cmdlets e provedores compatíveis com os snap-ins da sessão atual.

Para adicionar o snap-in a todas as sessões futuras do Windows PowerShell, adicione um `Add-PSSnapin` comando ao seu perfil do Windows PowerShell. Para obter mais informações, consulte [about_Profiles](about/about_Profiles.md).

A partir do Windows PowerShell 3.0, os comandos principais que estão incluídos no Windows PowerShell são empacotados em módulos. A exceção é o **Microsoft.PowerShell.Core** , que é um snap-in (PSSnapin).
Por padrão, somente o snap-in **Microsoft.PowerShell.Core** é adicionado à sessão. Os módulos são importados automaticamente no primeiro uso e você pode usar o cmdlet Import-Module para importá-los.

## EXEMPLOS

### Exemplo 1: Adicionar Snap-ins

```powershell
PS C:\> Add-PSSnapIn -Name Microsoft.Exchange, Microsoft.Windows.AD
```

Este comando adiciona os snap-ins do Microsoft Exchange e o Active Directory para a sessão atual.

### Exemplo 2: adicionar todos os snap-ins registrados

```powershell
PS C:\> Get-PSSnapin -Registered | Add-PSSnapin -Passthru
```

Este comando adiciona todos os snap-ins registrados do Windows PowerShell à sessão. Ele usa o cmdlet Get-PSSnapin com o parâmetro **Registered** para obter objetos que representam cada um dos snap-ins registrados. O operador de pipeline (|) passa o resultado para `Add-PSSnapin` , que os adiciona à sessão. O parâmetro **PassThru** retorna objetos que representam cada um dos snap-ins adicionados.

### Exemplo 3: registrar um snap-in e adicioná-lo

O primeiro comando obtém snap-ins que foram adicionados à sessão atual que incluem os snap-ins instalados com o Windows PowerShell. Neste exemplo, ManagementFeatures não é retornado. Isso indica que não foi adicionado à sessão.

O segundo comando obtém snap-ins que foram registrados no seu sistema, o que inclui aqueles que já foram adicionados à sessão. Ele não inclui os snap-ins instalados com o Windows PowerShell. Nesse caso, o comando não retorna nenhum snap-in. Isso indica que o snap-in ManagementFeatures não foi registrado no sistema.

O terceiro comando cria um alias, InstallUtil, para o caminho da ferramenta InstallUtil no .NET Framework.

O quarto comando usa a ferramenta InstallUtil para registrar o snap-in. O comando especifica o caminho do ManagementCmdlets.dll, o nome do arquivo ou do módulo do snap-in do.

O quinto comando é o mesmo que o segundo comando. Dessa vez, você vai usá-lo para verificar se o snap-in ManagementCmdlets está registrado.

O sexto comando usa o `Add-PSSnapin` cmdlet para adicionar o snap-in ManagementFeatures à sessão. Especifica o nome do snap-in, ManagementFeatures, não o nome do arquivo.

Para verificar se o snap-in foi adicionado à sessão, o sétimo comando usa o parâmetro **Module** do cmdlet Get-Command. Ele exibe os itens que foram adicionados à sessão por um snap-in ou módulo.

Você também pode usar a propriedade **PSSnapin** do objeto que o `Get-Command` cmdlet retorna para localizar o snap-in ou o módulo no qual um cmdlet foi originado. O oitavo comando usa a notação de ponto para localizar o valor da propriedade PSSnapin do cmdlet Set-Alias.

```powershell
PS C:\> Get-PSSnapin
PS C:\> Get-PSSnapin -Registered
PS C:\> Set-Alias installutil $env:windir\Microsoft.NET\Framework\v2.0.50727\installutil.exe
PS C:\> installutil C:\Dev\Management\ManagementCmdlets.dll
PS C:\> Get-PSSnapin -Registered
PS C:\> add-pssnapin ManagementFeatures
PS C:\> Get-Command -Module ManagementFeatures
PS C:\> (Get-Command Set-Alias).pssnapin
```

Este exemplo demonstra o processo de registrar um snap-in no seu sistema e, em seguida, adicioná-lo à sua sessão. Ele usa ManagementFeatures, um snap-in fictício implementado em um arquivo chamado ManagementCmdlets.dll.

## PARAMETERS

### -Name

Especifica o nome do snap-in do. Esse é o nome, não o AssemblyName ou ModuleName. Caracteres curinga são permitidos.

Para localizar os nomes dos snap-ins registrados em seu sistema, digite `Get-PSSnapin -Registered` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

Indica que esse cmdlet retorna um objeto que representa cada snap-in adicionado. Por padrão, este cmdlet não gera saída.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### Nenhum ou System. Management. Automation. PSSnapInInfo

Esse cmdlet retorna um objeto PSSnapInInfo que representa o snap-in se você especificar o parâmetro **PassThru** . Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

- A partir do Windows PowerShell 3.0, os comandos principais que são instalados com o Windows PowerShell são empacotados em módulos. No Windows PowerShell 2,0 e em programas de host que criam sessões de estilo mais antigo em versões posteriores do Windows PowerShell, os comandos principais são empacotados em snap-ins (PSSnapins). A exceção é **Microsoft. PowerShell. Core** , que sempre é um snap-in. Além disso, as sessões remotas, como as iniciadas pelo cmdlet New-PSSession, são sessões de estilo antigo que incluem snap-ins de núcleo.

  Para obter informações sobre o método **CreateDefault2** que cria sessões de estilo mais recente com módulos principais, consulte [método CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2#System_Management_Automation_Runspaces_InitialSessionState_CreateDefault2).

- Para obter mais informações sobre snap-ins, consulte [about_Pssnapins](About/about_PSSnapins.md) e [como criar um snap-in do Windows PowerShell](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in).
- `Add-PSSnapin` Adiciona o snap-in somente à sessão atual. Para adicionar o snap-in para todas as sessões do Windows PowerShell, adicione-o ao seu perfil do Windows PowerShell. Para obter mais informações, consulte about_Profiles.
- Você pode adicionar qualquer snap-in que tenha sido registrado usando o utilitário de instalação do Microsoft .NET Framework. Para obter mais informações, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).
- Para obter uma lista de snap-ins registrados no seu computador, digite `Get-PSSnapin -Registered` .
- Antes de adicionar um snap-in, `Add-PSSnapin` o verifica a versão do snap-in para verificar se ele é compatível com a versão atual do Windows PowerShell. Se o snap-in falha na verificação de versão, o Windows PowerShell relata um erro.

## LINKS RELACIONADOS

[Get-PSSnapin](Get-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
