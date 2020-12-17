---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Selecionando itens de uma caixa de listagem
description: Este artigo mostra como criar um controle de caixa de listagem usando os recursos de criação de formulário do .NET Framework no Windows PowerShell.
ms.openlocfilehash: d6f881f0b92f294da105ae7df5e25e8c20ce5094
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391231"
---
# <a name="selecting-items-from-a-list-box"></a><span data-ttu-id="9fa30-104">Selecionando itens de uma caixa de listagem</span><span class="sxs-lookup"><span data-stu-id="9fa30-104">Selecting Items from a List Box</span></span>

<span data-ttu-id="9fa30-105">Use o Windows PowerShell 3.0 e versões posteriores para criar uma caixa de diálogo que permite aos usuários selecionar itens de um controle de caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="9fa30-105">Use Windows PowerShell 3.0 and later releases to create a dialog box that lets users select items from a list box control.</span></span>

## <a name="create-a-list-box-control-and-select-items-from-it"></a><span data-ttu-id="9fa30-106">Criar um controle de caixa de listagem e selecionar itens dela</span><span class="sxs-lookup"><span data-stu-id="9fa30-106">Create a list box control, and select items from it</span></span>

<span data-ttu-id="9fa30-107">Copie e cole o seguinte no Windows PowerShell ISE e salve-o como um script do Windows PowerShell (.ps1).</span><span class="sxs-lookup"><span data-stu-id="9fa30-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

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

<span data-ttu-id="9fa30-108">O script começa carregando duas classes do .NET Framework: **System.Drawing** e **System.Windows.Forms**.</span><span class="sxs-lookup"><span data-stu-id="9fa30-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span> <span data-ttu-id="9fa30-109">Inicie uma nova instância da classe do .NET Framework **System.Windows.Forms.Form**, que fornece um formulário em branco ou janela ao qual você pode começar a adicionar controles.</span><span class="sxs-lookup"><span data-stu-id="9fa30-109">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
```

<span data-ttu-id="9fa30-110">Depois de criar uma instância da classe Form, atribua valores a três propriedades dessa classe.</span><span class="sxs-lookup"><span data-stu-id="9fa30-110">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="9fa30-111">**Text.**</span><span class="sxs-lookup"><span data-stu-id="9fa30-111">**Text.**</span></span> <span data-ttu-id="9fa30-112">Isso se torna o título da janela.</span><span class="sxs-lookup"><span data-stu-id="9fa30-112">This becomes the title of the window.</span></span>

- <span data-ttu-id="9fa30-113">**Size.**</span><span class="sxs-lookup"><span data-stu-id="9fa30-113">**Size.**</span></span> <span data-ttu-id="9fa30-114">Esse é o tamanho do formulário, em pixels.</span><span class="sxs-lookup"><span data-stu-id="9fa30-114">This is the size of the form, in pixels.</span></span> <span data-ttu-id="9fa30-115">O script anterior cria um formulário de 300 pixels de largura por 200 pixels de altura.</span><span class="sxs-lookup"><span data-stu-id="9fa30-115">The preceding script creates a form that's 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="9fa30-116">**StartingPosition.**</span><span class="sxs-lookup"><span data-stu-id="9fa30-116">**StartingPosition.**</span></span> <span data-ttu-id="9fa30-117">Esta propriedade opcional é definida para **CenterScreen** no script precedente.</span><span class="sxs-lookup"><span data-stu-id="9fa30-117">This optional property is set to **CenterScreen** in the preceding script.</span></span>
  <span data-ttu-id="9fa30-118">Se você não adicionar essa propriedade, o Windows selecionará um local quando o formulário for aberto.</span><span class="sxs-lookup"><span data-stu-id="9fa30-118">If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="9fa30-119">Ao configurar o **StartingPosition** para **CenterScreen**, você está exibindo automaticamente o formulário no meio da tela cada vez que ela é carregada.</span><span class="sxs-lookup"><span data-stu-id="9fa30-119">By setting the **StartingPosition** to **CenterScreen**, you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="9fa30-120">Em seguida, crie um botão **OK** para seu formulário.</span><span class="sxs-lookup"><span data-stu-id="9fa30-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="9fa30-121">Especifique o tamanho e comportamento do botão **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fa30-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="9fa30-122">Neste exemplo, a posição do botão é de 120 pixels da borda superior do formulário e 75 pixels da borda esquerda.</span><span class="sxs-lookup"><span data-stu-id="9fa30-122">In this example, the button position is 120 pixels from the form's top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="9fa30-123">A altura do botão é de 23 pixels, enquanto seu comprimento é de 75 pixels.</span><span class="sxs-lookup"><span data-stu-id="9fa30-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="9fa30-124">O script usa tipos predefinidos de formulários do Windows para determinar os comportamentos do botão.</span><span class="sxs-lookup"><span data-stu-id="9fa30-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

<span data-ttu-id="9fa30-125">Crie o botão **Cancelar** da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="9fa30-125">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="9fa30-126">O botão **Cancelar** fica a 120 pixels da parte superior e 150 pixels da borda esquerda da janela.</span><span class="sxs-lookup"><span data-stu-id="9fa30-126">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

<span data-ttu-id="9fa30-127">Em seguida, forneça o texto de rótulo na janela que descreve as informações que você deseja que os usuários forneçam.</span><span class="sxs-lookup"><span data-stu-id="9fa30-127">Next, provide label text on your window that describes the information you want users to provide.</span></span> <span data-ttu-id="9fa30-128">Nesse caso, é recomendável que os usuários selecionem um computador.</span><span class="sxs-lookup"><span data-stu-id="9fa30-128">In this case, you want users to select a computer.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)
```

<span data-ttu-id="9fa30-129">Adicione o controle (no caso, uma caixa de listagem) que permite que os usuários forneçam as informações descritas no texto do rótulo.</span><span class="sxs-lookup"><span data-stu-id="9fa30-129">Add the control (in this case, a list box) that lets users provide the information you've described in your label text.</span></span> <span data-ttu-id="9fa30-130">Há muitos outros controles que você pode aplicar além de caixas de listagem. Para ver mais controles, confira [Namespace System.Windows.Forms](/dotnet/api/system.windows.forms).</span><span class="sxs-lookup"><span data-stu-id="9fa30-130">There are many other controls you can apply besides list boxes; for more controls, see [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms).</span></span>

```powershell
$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80
```

<span data-ttu-id="9fa30-131">Na próxima seção, você deve especificar os valores que você deseja que a caixa de listagem mostre para os usuários.</span><span class="sxs-lookup"><span data-stu-id="9fa30-131">In the next section, you specify the values you want the list box to display to users.</span></span>

> [!NOTE]
> <span data-ttu-id="9fa30-132">A caixa de listagem criada por esse script permite somente uma seleção.</span><span class="sxs-lookup"><span data-stu-id="9fa30-132">The list box created by this script allows only one selection.</span></span> <span data-ttu-id="9fa30-133">Para criar um controle de caixa de listagem que permita várias seleções, especifique um valor para a propriedade **SelectionMode**, de forma semelhante à seguinte: `$listBox.SelectionMode = 'MultiExtended'`.</span><span class="sxs-lookup"><span data-stu-id="9fa30-133">To create a list box control that allows multiple selections, specify a value for the **SelectionMode** property, similarly to the following: `$listBox.SelectionMode = 'MultiExtended'`.</span></span> <span data-ttu-id="9fa30-134">Para obter mais informações, consulte [Caixas de listagem de seleção múltipla](Multiple-selection-List-Boxes.md).</span><span class="sxs-lookup"><span data-stu-id="9fa30-134">For more information, see [Multiple-selection List Boxes](Multiple-selection-List-Boxes.md).</span></span>

```powershell
[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')
```

<span data-ttu-id="9fa30-135">Adicione o controle de caixa de listagem ao formulário e instrua o Windows a abrir o formulário sobre outras janelas e caixas de diálogo quando ela é aberta.</span><span class="sxs-lookup"><span data-stu-id="9fa30-135">Add the list box control to your form, and instruct Windows to open the form atop other windows and dialog boxes when it's opened.</span></span>

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

<span data-ttu-id="9fa30-136">Adicione a seguinte linha de código para exibir o formulário do Windows.</span><span class="sxs-lookup"><span data-stu-id="9fa30-136">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="9fa30-137">Por fim, o código dentro do bloco **If** instrui o Windows sobre o que fazer com o formulário depois que os usuários selecionam uma opção na caixa de listagem e clicam no botão **OK** ou pressionam a tecla **Enter**.</span><span class="sxs-lookup"><span data-stu-id="9fa30-137">Finally, the code inside the **If** block instructs Windows what to do with the form after users select an option from the list box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="9fa30-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9fa30-138">See Also</span></span>

- [<span data-ttu-id="9fa30-139">GitHub: WinFormsExampleUpdates do Dave Wyatt</span><span class="sxs-lookup"><span data-stu-id="9fa30-139">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="9fa30-140">[Dica da semana para o Windows PowerShell: selecionar itens em uma caixa de listagem](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9fa30-140">[Windows PowerShell Tip of the Week: Selecting Items from a List Box](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10))</span></span>
