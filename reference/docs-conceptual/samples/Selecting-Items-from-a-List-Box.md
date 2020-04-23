---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Selecionando itens de uma caixa de listagem
ms.openlocfilehash: 048bccd403e01e2290a8930a0faba30d4c7caa73
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "77706165"
---
# <a name="selecting-items-from-a-list-box"></a>Selecionando itens de uma caixa de listagem

Use o Windows PowerShell 3.0 e versões posteriores para criar uma caixa de diálogo que permite aos usuários selecionar itens de um controle de caixa de listagem.

## <a name="create-a-list-box-control-and-select-items-from-it"></a>Criar um controle de caixa de listagem e selecionar itens dela

Copie e cole o seguinte no Windows PowerShell ISE e salve-o como um script do Windows PowerShell (.ps1).

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'

$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)

$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)

$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80

[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')

$form.Controls.Add($listBox)

$form.Topmost = $true

$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

O script começa carregando duas classes do .NET Framework: **System.Drawing** e **System.Windows.Forms**. Inicie uma nova instância da classe do .NET Framework **System.Windows.Forms.Form**, que fornece um formulário em branco ou janela ao qual você pode começar a adicionar controles.

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
```

Depois de criar uma instância da classe Form, atribua valores a três propriedades dessa classe.

- **Text.** Isso se torna o título da janela.

- **Size.** Esse é o tamanho do formulário, em pixels. O script anterior cria um formulário que possui 300 pixels de largura por 200 pixels de altura.

- **StartingPosition.** Esta propriedade opcional é definida para **CenterScreen** no script precedente.
  Se você não adicionar essa propriedade, o Windows seleciona um local quando o formulário aberto. Ao configurar o **StartingPosition** para **CenterScreen**, você está exibindo automaticamente o formulário no meio da tela cada vez que ela é carregada.

```powershell
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

Em seguida, crie um botão **OK** para seu formulário. Especifique o tamanho e comportamento do botão **OK**. Neste exemplo, a posição do botão é de 120 pixels a partir da borda superior do formulário e 75 pixels a partir da borda esquerda. A altura do botão é de 23 pixels, enquanto seu comprimento é de 75 pixels. O script usa tipos predefinidos de formulários do Windows para determinar os comportamentos do botão.

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

Crie o botão **Cancelar** da mesma maneira. O botão **Cancelar** fica a 120 pixels da parte superior e 150 pixels da borda esquerda da janela.

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

Em seguida, forneça o texto de rótulo na janela que descreve as informações que você deseja que os usuários forneçam. Nesse caso, é recomendável que os usuários selecionem um computador.

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)
```

Adicione o controle (no caso, uma caixa de listagem) que permite que os usuários forneçam as informações descritas no texto do rótulo. Há muitos outros controles que você pode aplicar além de caixas de listagem. Para ver mais controles, consulte [Namespace System.Windows.Forms](/dotnet/api/system.windows.forms) no MSDN.

```powershell
$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80
```

Na próxima seção, você deve especificar os valores que você deseja que a caixa de listagem mostre para os usuários.

> [!NOTE]
> A caixa de listagem criada por esse script permite somente uma seleção. Para criar um controle de caixa de listagem que permita várias seleções, especifique um valor para a propriedade **SelectionMode**, de forma semelhante à seguinte: `$listBox.SelectionMode = 'MultiExtended'`. Para obter mais informações, consulte [Caixas de listagem de seleção múltipla](Multiple-selection-List-Boxes.md).

```powershell
[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')
```

Adicione o controle de caixa de listagem ao formulário e instrua o Windows a abrir o formulário sobre outras janelas e caixas de diálogo quando ela é aberta.

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

Adicione a seguinte linha de código para exibir o formulário do Windows.

```powershell
$result = $form.ShowDialog()
```

Por fim, o código dentro do bloco **If** instrui o Windows sobre o que fazer com o formulário depois que os usuários selecionam uma opção na caixa de listagem e clicam no botão **OK** ou pressionam a tecla **Enter**.

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

## <a name="see-also"></a>Consulte Também

- [GitHub: WinFormsExampleUpdates do Dave Wyatt](https://github.com/dlwyatt/WinFormsExampleUpdates)
- [Windows PowerShell Tip of the Week: Selecting Items from a List Box](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10)) (Dica da semana do Windows PowerShell: selecionando itens de uma caixa de listagem)
