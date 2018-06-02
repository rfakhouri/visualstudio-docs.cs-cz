---
title: Nastavení jedinečné vlastnosti automatizace pro ovládací prvky UPW za účelem testování
ms.date: 05/31/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- uwp
author: gewarren
ms.openlocfilehash: fbb815dc17e8b71efcefee8410faa01df0914e35
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692353"
---
# <a name="set-a-unique-automation-property-for-uwp-controls-for-testing"></a>Nastavení jedinečné vlastnosti automatizace pro ovládací prvky UPW za účelem testování

Pokud chcete spustit programové testy uživatelského rozhraní pro aplikace UWP založených na XAML, musí být každý ovládací prvek identifikovaný jedinečné vlastnosti automatizace. Můžete přiřadit jedinečné vlastnosti automatizace na základě typu ovládacího prvku XAML ve vaší aplikaci.

## <a name="static-xaml-definition"></a>Statické definici XAML

Chcete-li určit jedinečné vlastnosti automatizace pro ovládací prvek, který je definován v souboru XAML, můžete nastavit **AutomationProperties.AutomationId** nebo **AutomationProperties.Name** implicitně nebo explicitně, jak je znázorněno v následující příklady. Některé z těchto hodnot nastavení umožňuje řízení jedinečný automatizace vlastnost, která slouží k identifikaci ovládacího prvku, když vytvoříte programové záznam testu nebo akce uživatelského rozhraní.

### <a name="set-the-property-implicitly"></a>Nastavte vlastnost implicitně

Nastavit **AutomationProperties.AutomationId** k **ButtonX** pomocí **název** vlastnost v jazyce XAML pro ovládací prvek.

```xaml
<Button Name="ButtonX" Height="31" HorizontalAlignment="Left" Margin="23,26,0,0"  VerticalAlignment="Top" Width="140" Click="ButtonX_Click" />
```

Nastavit **AutomationProperties.Name** k **ButtonY** pomocí **obsahu** vlastnost v jazyce XAML pro ovládací prvek.

```xaml
<Button Content="ButtonY" Height="31" HorizontalAlignment="Left" Margin="23,76,0,0" VerticalAlignment="Top" Width="140" Click="ButtonY_Click" />
```

### <a name="set-the-property-explicitly"></a>Nastavte vlastnost explicitně

Nastavit **AutomationProperties.AutomationId** k **ButtonX** explicitně v jazyce XAML pro ovládací prvek.

```xaml
<Button AutomationProperties.AutomationId="ButtonX" Height="31" HorizontalAlignment="Left" Margin="23,26,0,0"  VerticalAlignment="Top" Width="140" Click="ButtonX_Click" />
```

Nastavte **AutomationProperties.Name** k **ButtonY** explicitně v jazyce XAML pro ovládací prvek.

```
<Button AutomationProperties.Name="ButtonY" Height="31" HorizontalAlignment="Left" Margin="23,76,0,0" VerticalAlignment="Top" Width="140" Click="ButtonY_Click" />
```

## <a name="assign-unique-names"></a>Přiřazení jedinečných názvů

V programu Blend for Visual Studio můžete vybrat možnost přiřazení jedinečné názvy na interaktivní elementy např. tlačítka, seznamy, pole se seznamem a textových polí. Díky tomu jedinečné hodnoty pro ovládací prvky **AutomationProperties.Name**.

Pokud chcete přiřadit jedinečné názvy existujících ovládacích prvků, vyberte **nástroje** > **interaktivní elementy název**.

![Název interaktivní elementy v programu Blend for Visual Studio](../test/media/cuit_windowsstoreproperty_blend_1.png)

Chcete-li automaticky zadejte jedinečný název pro nové ovládací prvky, které přidáte, vyberte **nástroje** > **možnosti** otevřete **možnosti** dialogové okno. Vyberte **návrháře XAML** a pak vyberte **automaticky interaktivní prvky na vytvoření názvu**. Vyberte **OK** zavřete dialogové okno.

## <a name="use-a-data-template"></a>Použijte šablonu dat

Můžete definovat jednoduchý šablony pomocí **ItemTemplate** k vytvoření vazby hodnoty v seznamu proměnných:

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

Můžete také použít šablonu s **ItemContainerStyle** svázání hodnot proměnných:

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

Pro obě tyto příklady, je nutné pak přepsat **ToString()** metodu **ItemSource**, jak je znázorněno pomocí příkladu kódu, který následuje. Tento kód je zajištěno, že **AutomationProperties.Name** hodnota je nastavena a je jedinečný, protože nelze nastavit jedinečné vlastnosti automatizace pro každou položku seznamu vázané na data pomocí vazby. Nastavení pro jedinečnou hodnotu **automatizace Properties.Name** v takovém případě bude stačit.

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

## <a name="use-a-control-template"></a>Použijte šablonu ovládacího prvku

Šablony správy můžete použít tak, aby každá instance určitého typu získá jedinečné vlastnosti automatizace, když je definována v kódu. Vytvořit šablonu, aby **AutomationProperty** váže k jedinečné ID v instanci ovládacího prvku. Následující XAML ukazuje jeden ze způsobů vytvoření tuto vazbu pomocí šablony ovládacího prvku:

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

### <a name="dynamic-controls"></a>Dynamických ovládacích prvků

Pokud máte ovládací prvky, které se vytváří dynamicky z vašeho kódu a nebyla vytvořena staticky nebo prostřednictvím šablon v soubory XAML, je nutné nastavit **obsahu** nebo **název** vlastnosti pro ovládací prvek. Tím je zajištěno, že každý dynamické řízení má jedinečné vlastnosti automatizace. Například pokud máte zaškrtávací políčko, které musí být zobrazena, když vyberete položku seznamu, můžete nastavit tyto vlastnosti, jak je vidět tady:

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

## <a name="see-also"></a>Viz také:

- [Otestujte aplikace UWP v testech programového uživatelského rozhraní](../test/test-uwp-app-with-coded-ui-test.md)
