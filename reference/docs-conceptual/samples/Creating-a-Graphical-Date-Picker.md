---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Criando um seletor de data gráfico
description: Este artigo mostra como criar um controle no estilo calendário personalizado usando os recursos de criação de formulário do .NET Framework no Windows PowerShell.
ms.openlocfilehash: b73c9ba78817af7c38c20642402752765a7a3674
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500497"
---
# <a name="creating-a-graphical-date-picker"></a><span data-ttu-id="efd1f-104">Criando um seletor de data gráfico</span><span class="sxs-lookup"><span data-stu-id="efd1f-104">Creating a Graphical Date Picker</span></span>

<span data-ttu-id="efd1f-105">Use o Windows PowerShell 3.0 e versões posteriores para criar um formulário com um controle de calendário de estilo gráfico, que permite aos usuários selecionar um dia do mês.</span><span class="sxs-lookup"><span data-stu-id="efd1f-105">Use Windows PowerShell 3.0 and later releases to create a form with a graphical, calendar-style control that lets users select a day of the month.</span></span>

## <a name="create-a-graphical-date-picker-control"></a><span data-ttu-id="efd1f-106">Crie um controle de seletor de data gráfico</span><span class="sxs-lookup"><span data-stu-id="efd1f-106">Create a graphical date-picker control</span></span>

<span data-ttu-id="efd1f-107">Copie e cole o seguinte no Windows PowerShell ISE e salve-o como um script do Windows PowerShell (.ps1).</span><span class="sxs-lookup"><span data-stu-id="efd1f-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

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

<span data-ttu-id="efd1f-108">O script começa carregando duas classes do .NET Framework: **System.Drawing** e **System.Windows.Forms** .</span><span class="sxs-lookup"><span data-stu-id="efd1f-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms** .</span></span> <span data-ttu-id="efd1f-109">Inicie uma nova instância da classe do .NET Framework **Windows.Forms.Form** , que fornece um formulário em branco ou ao qual você pode começar a adicionar controles de janela.</span><span class="sxs-lookup"><span data-stu-id="efd1f-109">You then start a new instance of the .NET Framework class **Windows.Forms.Form** ; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}
```

<span data-ttu-id="efd1f-110">Este exemplo atribui valores a quatro propriedades dessa classe usando a propriedade **Property** e tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="efd1f-110">This example assigns values to four properties of this class by using the **Property** property and hashtable.</span></span>

1. <span data-ttu-id="efd1f-111">**StartPosition** : Se você não adicionar essa propriedade, o Windows selecionará um local quando o formulário for aberto.</span><span class="sxs-lookup"><span data-stu-id="efd1f-111">**StartPosition** : If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="efd1f-112">Ao configurar essa propriedade como **CenterScreen** , você está exibindo automaticamente o formulário no meio da tela cada vez que ela é carregada.</span><span class="sxs-lookup"><span data-stu-id="efd1f-112">By setting this property to **CenterScreen** , you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

2. <span data-ttu-id="efd1f-113">**Size** : Esse é o tamanho do formulário, em pixels.</span><span class="sxs-lookup"><span data-stu-id="efd1f-113">**Size** : This is the size of the form, in pixels.</span></span>
   <span data-ttu-id="efd1f-114">O script anterior cria um formulário de 243 pixels de largura por 230 pixels de altura.</span><span class="sxs-lookup"><span data-stu-id="efd1f-114">The preceding script creates a form that's 243 pixels wide by 230 pixels tall.</span></span>

3. <span data-ttu-id="efd1f-115">**Text** : Isso se torna o título da janela.</span><span class="sxs-lookup"><span data-stu-id="efd1f-115">**Text** : This becomes the title of the window.</span></span>

4. <span data-ttu-id="efd1f-116">**Topmost** : Definindo essa propriedade como `$true`, você poderá forçar a janela a abrir por cima de outras janelas e caixas de diálogo abertas.</span><span class="sxs-lookup"><span data-stu-id="efd1f-116">**Topmost** : By setting this property to `$true`, you can force the window to open atop other open windows and dialog boxes.</span></span>

<span data-ttu-id="efd1f-117">Em seguida, crie e adicione um controle de calendário ao seu formulário.</span><span class="sxs-lookup"><span data-stu-id="efd1f-117">Next, create and then add a calendar control in your form.</span></span>
<span data-ttu-id="efd1f-118">Neste exemplo, o dia atual não é realçado ou circulado.</span><span class="sxs-lookup"><span data-stu-id="efd1f-118">In this example, the current day is not highlighted or circled.</span></span>
<span data-ttu-id="efd1f-119">Os usuários podem selecionar somente um dia por vez no calendário.</span><span class="sxs-lookup"><span data-stu-id="efd1f-119">Users can select only one day on the calendar at one time.</span></span>

```powershell
$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)
```

<span data-ttu-id="efd1f-120">Em seguida, crie um botão **OK** para seu formulário.</span><span class="sxs-lookup"><span data-stu-id="efd1f-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="efd1f-121">Especifique o tamanho e comportamento do botão **OK** .</span><span class="sxs-lookup"><span data-stu-id="efd1f-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="efd1f-122">Neste exemplo, a posição do botão é de 165 pixels da borda superior do formulário e 38 pixels da borda esquerda.</span><span class="sxs-lookup"><span data-stu-id="efd1f-122">In this example, the button position is 165 pixels from the form's top edge, and 38 pixels from the left edge.</span></span> <span data-ttu-id="efd1f-123">A altura do botão é de 23 pixels, enquanto seu comprimento é de 75 pixels.</span><span class="sxs-lookup"><span data-stu-id="efd1f-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="efd1f-124">O script usa tipos predefinidos de formulários do Windows para determinar os comportamentos do botão.</span><span class="sxs-lookup"><span data-stu-id="efd1f-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

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

<span data-ttu-id="efd1f-125">Crie o botão **Cancelar** da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="efd1f-125">Similarly, you create a **Cancel** button.</span></span>
<span data-ttu-id="efd1f-126">O botão **Cancelar** fica a 165 pixels da parte superior e 113 pixels da borda esquerda da janela.</span><span class="sxs-lookup"><span data-stu-id="efd1f-126">The **Cancel** button is 165 pixels from the top, but 113 pixels from the left edge of the window.</span></span>

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

<span data-ttu-id="efd1f-127">Adicione a seguinte linha de código para exibir o formulário do Windows.</span><span class="sxs-lookup"><span data-stu-id="efd1f-127">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="efd1f-128">Por fim, o código dentro do bloco `if` instrui o Windows sobre o que fazer com o formulário depois que os usuários selecionam um dia no calendário e clicam no botão **OK** ou pressionam a tecla **Enter** .</span><span class="sxs-lookup"><span data-stu-id="efd1f-128">Finally, the code inside the `if` block instructs Windows what to do with the form after users select a day on the calendar, and then click the **OK** button or press the **Enter** key.</span></span> <span data-ttu-id="efd1f-129">O Windows PowerShell exibe as datas selecionadas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="efd1f-129">Windows PowerShell displays the selected date to users.</span></span>

```powershell
if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

## <a name="see-also"></a><span data-ttu-id="efd1f-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="efd1f-130">See Also</span></span>

- [<span data-ttu-id="efd1f-131">GitHub: WinFormsExampleUpdates do Dave Wyatt</span><span class="sxs-lookup"><span data-stu-id="efd1f-131">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="efd1f-132">[Dica da Semana do Windows PowerShell: criar um seletor de data gráfico](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730942(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="efd1f-132">[Windows PowerShell Tip of the Week:  Creating a Graphical Date Picker](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730942(v=technet.10))</span></span>
