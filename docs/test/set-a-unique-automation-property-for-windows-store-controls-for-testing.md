---
title: Nastavení jedinečné vlastnosti automatizace pro ovládací prvky UWP pro testování v sadě Visual Studio | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- uwp
author: gewarren
ms.openlocfilehash: a27b3472080f1b22f0b07b01e92d6a0e5326396e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="set-a-unique-automation-property-for-uwp-controls-for-testing"></a>Nastavení jedinečné vlastnosti automatizace pro ovládací prvky UWP pro testování

Pokud chcete spustit programové testy uživatelského rozhraní pro aplikace UWP založených na XAML, musí mít jedinečné vlastnosti automatizace identifikující každý ovládací prvek.

 Můžete přiřadit jedinečné vlastnosti automatizace na základě typu ovládacího prvku XAML ve vaší aplikaci. Chcete-li přiřadit tento jedinečné vlastnosti automatizace v následujících situacích:

-   [Statické definici XAML ovládacích prvků](#UniquePropertyWindowsStoreControlsStaticXAML)

-   [Přiřazení jedinečné automatizace vlastností pomocí sady Visual Studio nebo Blendu pro Visual Studio](#UniquePropertyWindowsStoreControlsExpressionBlend)

-   [Použít šablonu DataTemplate](#UniquePropertyWindowsStoreControlsDataTemplate)

-   [Použijte šablonu ovládacího prvku](#UniquePropertyWindowsStoreControlsControlTemplate)

-   [Dynamických ovládacích prvků](#UniquePropertyWindowsStoreControlsDynamicControls)

## <a name="use-methods-to-assign-a-unique-automation-property"></a>K přiřazení jedinečné vlastnosti automatizace použít metody

###  <a name="UniquePropertyWindowsStoreControlsStaticXAML"></a> Statické definici XAML
 Chcete-li určit jedinečné vlastnosti automatizace pro ovládací prvek, který je definován v souboru XAML, můžete nastavit AutomationProperties.AutomationId nebo AutomationProperties.Name implicitně nebo explicitně, jak je uvedené v následující příklady. Některé z těchto hodnot nastavení umožňuje řízení jedinečný automatizace vlastnost, která slouží k identifikaci ovládacího prvku, když vytvoříte programové záznam testu nebo akce uživatelského rozhraní.

 **Nastavte vlastnost implicitně**

Nastavte AutomationProperties.AutomationId na **ButtonX** pomocí název vlastnosti v XAML pro ovládací prvek.

```xaml
<Button Name="ButtonX" Height="31" HorizontalAlignment="Left" Margin="23,26,0,0"  VerticalAlignment="Top" Width="140" Click="ButtonX_Click" />
```

Nastavte AutomationProperties.Name na **ButtonY** pomocí vlastnosti obsahu v XAML pro ovládací prvek.

```xaml
<Button Content="ButtonY" Height="31" HorizontalAlignment="Left" Margin="23,76,0,0" VerticalAlignment="Top" Width="140" Click="ButtonY_Click" />
```

 **Nastavte vlastnost explicitně**

 Nastavte AutomationProperties.AutomationId na **ButtonX** explicitně v jazyce XAML pro ovládací prvek.

```xaml
<Button AutomationProperties.AutomationId="ButtonX" Height="31" HorizontalAlignment="Left" Margin="23,26,0,0"  VerticalAlignment="Top" Width="140" Click="ButtonX_Click" />
```

 Nastavte AutomationProperties.Name na **ButtonY** explicitně v jazyce XAML pro ovládací prvek.

```
<Button AutomationProperties.Name="ButtonY" Height="31" HorizontalAlignment="Left" Margin="23,76,0,0" VerticalAlignment="Top" Width="140" Click="ButtonY_Click" />
```

###  <a name="UniquePropertyWindowsStoreControlsExpressionBlend"></a> Přiřazení jedinečné automatizace vlastností pomocí sady Visual Studio nebo Blendu pro Visual Studio
 Visual Studio nebo Blend for Visual Studio můžete použít k přiřazení jedinečné názvy na interaktivní elementy např. tlačítka, seznamy, pole se seznamem a textová pole. Ovládací prvek díky pro AutomationProperties.Name jedinečnou hodnotu.

 **Visual Studio:** na **nástroje** nabídky, přejděte na příkaz **možnosti** a potom zvolte **textového editoru**, pak **XAML**a v neposlední řadě **Různé**.

 Vyberte **automaticky interaktivní prvky na vytvoření názvu** a potom zvolte **OK**.

 ![XAML různé možnosti](../test/media/cuit_windowsstoreapp_b.png "CUIT_WindowsStoreApp_B")

 **Blend for Visual Studio:** použijte jednu z následujících metod k tomu blendu pro Visual Studio.

> [!NOTE]
>  Tuto metodu můžete použít pouze pro ovládací prvky, které jsou vytvořené pomocí staticky XAML.

 **Chcete-li zadejte jedinečný název stávající ovládací prvky**

 Na **nástroje** nabídce zvolte **interaktivní elementy název**, jak je vidět tady:

 ![Vyberte název interaktivní prvky v nabídce Nástroje pro](../test/media/cuit_windowsstoreproperty_blend_1.png "CUIT_WindowsStoreProperty_Blend_1")

 **Automaticky přidělit ovládací prvky, které vytvoříte jedinečný název**

 Na **nástroje** nabídky, přejděte na příkaz **možnosti**a potom zvolte **projektu**. Vyberte **automaticky interaktivní prvky na vytvoření názvu** a potom zvolte **OK**, jak je vidět tady:

 ![Sada projektu na název interaktivní elementy](../test/media/cuit_windowsstoreproeprty_blend_2.png "CUIT_WindowsStoreProeprty_Blend_2")

###  <a name="UniquePropertyWindowsStoreControlsDataTemplate"></a> Použijte šablonu dat
 Můžete definovat jednoduchou šablonu pomocí ItemTemplate k vytvoření vazby hodnoty v seznamu proměnných pomocí následující XAML.

```xaml
<ListBox Name="listBox1" ItemsSource="{Binding Source={StaticResource employees}}">
   <ListBox.ItemTemplate>
      <DataTemplate>
         <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding EmployeeName}" />
            <TextBlock Text="{Binding EmployeeID}" />
         </StackPanel>
      </DataTemplate>
   </ListBox.ItemTemplate>
</ListBox>
```

 Můžete také pomocí šablony s ItemContainerStyle k vytvoření vazby hodnoty proměnné pomocí následující XAML:

```xaml
      <ListBox Name="listBox1" ItemsSource="{Binding Source={StaticResource employees}}">
            <ListBox.ItemContainerStyle>
                <Style TargetType="ListBoxItem">
                    <Setter Property="Template">
                        <Setter.Value>
                            <ControlTemplate TargetType="ListBoxItem">
                                <Grid>
                                    <Button Content="{Binding EmployeeName}" AutomationProperties.AutomationId="{Binding EmployeeID}"/>
                                </Grid>
                            </ControlTemplate>
                        </Setter.Value>
                    </Setter>
                </Style>
            </ListBox.ItemContainerStyle>
        </ListBox>
```

 Pro obě tyto příklady musí pak přepsat metodu ToString() ItemSource, jak je znázorněno pomocí příkladu kódu, který následuje dále. Tento kód je zajištěno, že hodnota AutomationProperties.Name nastavena a je jedinečný, protože nelze nastavit jedinečné vlastnosti automatizace pro každou položku seznamu vázaného dat pomocí vazby. Nastavení jedinečnou hodnotu pro Properties.Name automatizace je dostatečná v tomto případě.

> [!NOTE]
> Tento přístup vnitřní obsah položce v seznamu je také možné nastavit na řetězec ve třídě zaměstnanec prostřednictvím vazby. Jak je znázorněno v příkladu, tlačítko ovládací prvek v rámci každá položka seznamu je přiřazen jedinečný automatizace id, které je číslo zaměstnance.

```csharp
Employee[] employees = new Employee[]
{
   new Employee("john", "4384"),
   new Employee("margaret", "7556"),
   new Employee("richard", "8688"),
   new Employee("george", "1293")
};

listBox1.ItemsSource = employees;

public override string ToString()
{
    return EmployeeName + EmployeeID; // Unique Identification to be set as the AutomationProperties.Name
}
```

###  <a name="UniquePropertyWindowsStoreControlsControlTemplate"></a> Použijte šablonu ovládacího prvku

Šablony správy můžete použít tak, aby každá instance určitého typu získá jedinečné vlastnosti automatizace, když je definována v kódu. Vytvořte šablonu, aby AutomationProperty váže k jedinečné ID v instanci ovládacího prvku. Následující XAML ukazuje jeden ze způsobů vytvoření tuto vazbu pomocí šablony ovládacího prvku.

```xaml
<Style x:Key="MyButton" TargetType="Button">
<Setter Property="Template">
   <Setter.Value>
<ControlTemplate TargetType="Button">
   <Grid>
      <CheckBox HorizontalAlignment="Left" AutomationProperties.AutomationId="{TemplateBinding Content}"></CheckBox>
      <Button Width="90" HorizontalAlignment="Right" Content="{TemplateBinding Content}" AutomationProperties.AutomationId="{TemplateBinding Content}"></Button>
   </Grid>
</ControlTemplate>
   </Setter.Value>
</Setter>
</Style>
```

 Když definujete dvě instance tlačítka pomocí této šablony ovládací prvek, id automatizace je nastaven na jedinečné obsahu řetězce pro ovládací prvky v šabloně, jak je znázorněno v následujícím XAML:

```xaml
<Button Content="Button1" Style="{StaticResource MyButton}" Width="140"/>
<Button Content="Button2" Style="{StaticResource MyButton}" Width="140"/>
```

###  <a name="UniquePropertyWindowsStoreControlsDynamicControls"></a> Dynamických ovládacích prvků
 Pokud máte ovládací prvky, které se vytváří dynamicky z vašeho kódu a nebyla vytvořena staticky nebo prostřednictvím šablon v soubory XAML, musíte nastavit obsah nebo název vlastnosti pro ovládací prvek. Tím je zajištěno, že každý dynamické řízení má jedinečné vlastnosti automatizace. Například pokud máte zaškrtávací políčko, které musí být zobrazena, když vyberete položku seznamu, můžete nastavit tyto vlastnosti, jak je vidět tady:

```csharp
private void CreateCheckBox(string txt, StackPanel panel)
   {
      CheckBox cb = new CheckBox();
      cb.Content = txt; // Sets the AutomationProperties.Name
      cb.Height = 50;
      cb.Width = 100;
      cb.Name = "DynamicCheckBoxAid"+ txt; // Sets the AutomationProperties.AutomationId
      panel.Children.Add(cb);
    }
```

## <a name="see-also"></a>Viz také

- [Testování aplikací pro UWP pomocí programových testů uživatelského rozhraní](../test/test-windows-store-8-1-apps-with-coded-ui-tests.md)
