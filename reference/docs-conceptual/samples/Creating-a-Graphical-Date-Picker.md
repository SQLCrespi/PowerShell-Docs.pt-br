---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Criando um seletor de data gráfico
ms.openlocfilehash: b748e301b24ed643488079b547e2da1a5a7a6551
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "77706115"
---
# <a name="creating-a-graphical-date-picker"></a>Criando um seletor de data gráfico

Use o Windows PowerShell 3.0 e versões posteriores para criar um formulário com um controle de calendário de estilo gráfico, que permite aos usuários selecionar um dia do mês.

## <a name="create-a-graphical-date-picker-control"></a>Crie um controle de seletor de data gráfico

Copie e cole o seguinte no Windows PowerShell ISE e salve-o como um script do Windows PowerShell (.ps1).

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}

$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)

$okButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

$cancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)

$result = $form.ShowDialog()

if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

O script começa carregando duas classes do .NET Framework: **System.Drawing** e **System.Windows.Forms**. Inicie uma nova instância da classe do .NET Framework **Windows.Forms.Form**, que fornece um formulário em branco ou ao qual você pode começar a adicionar controles de janela.

```powershell
$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}
```

Este exemplo atribui valores a quatro propriedades dessa classe usando a propriedade **Property** e tabela de hash.

1. **StartPosition**: Se você não adicionar essa propriedade, o Windows seleciona um local quando o formulário aberto. Definindo essa propriedade como **CenterScreen**, você está exibindo automaticamente o formulário no meio da tela cada vez que ela é carregada.

2. **Size**: Esse é o tamanho do formulário, em pixels.
   O script anterior cria um formulário que possui 243 pixels de largura por 230 pixels de altura.

3. **Text**: Isso se torna o título da janela.

4. **Topmost**: Definindo essa propriedade como `$true`, você poderá forçar a janela a abrir por cima de outras janelas e caixas de diálogo abertas.

Em seguida, crie e adicione um controle de calendário ao seu formulário.
Neste exemplo, o dia atual não é realçado ou circulado.
Os usuários podem selecionar somente um dia por vez no calendário.

```powershell
$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)
```

Em seguida, crie um botão **OK** para seu formulário. Especifique o tamanho e comportamento do botão **OK**. Neste exemplo, a posição do botão é de 165 pixels a partir da borda superior do formulário e 38 pixels a partir da borda esquerda. A altura do botão é de 23 pixels, enquanto seu comprimento é de 75 pixels. O script usa tipos predefinidos de formulários do Windows para determinar os comportamentos do botão.

```powershell
$okButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

Crie o botão **Cancelar** da mesma maneira.
O botão **Cancelar** fica a 165 pixels da parte superior e 113 pixels da borda esquerda da janela.

```powershell
$cancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

Adicione a seguinte linha de código para exibir o formulário do Windows.

```powershell
$result = $form.ShowDialog()
```

Por fim, o código dentro do bloco `if` instrui o Windows sobre o que fazer com o formulário depois que os usuários selecionam um dia no calendário e clicam no botão **OK** ou pressionam a tecla **Enter**. O Windows PowerShell exibe as datas selecionadas para os usuários.

```powershell
if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

## <a name="see-also"></a>Consulte Também

- [GitHub: WinFormsExampleUpdates de Dave Wyatt](https://github.com/dlwyatt/WinFormsExampleUpdates)
- [Dica da semana para o Windows PowerShell:  criar um seletor de data gráfico](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730942(v=technet.10))
