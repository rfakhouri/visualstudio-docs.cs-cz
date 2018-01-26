---
title: "Návod: Vytvoření vazby na data v Návrháři XAML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.XamlDesigner.DataBinding
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: ef8826fd01c0eec45f2daea5900c5e440a5cebb0
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="walkthrough-binding-to-data-in-xaml-designer"></a>Návod: Vytvoření vazby na data v Návrháři XAML

V Návrháři XAML můžete nastavit vlastnosti datové vazby pomocí návrhové plochy a v okně Vlastnosti. V příkladu v tomto průvodci ukazuje, jak k vytvoření vazby dat k ovládacímu prvku. Konkrétně návod ukazuje, jak vytvořit jednoduché nákupní košík třídy, která má [vlastnost DependencyProperty](/uwp/api/Windows.UI.Xaml.DependencyProperty) s názvem `ItemCount`a pak vytvořte vazbu `ItemCount` vlastnost, která má **Text** vlastnost nástroje [TextBlock](/uwp/api/Windows.UI.Xaml.Controls.TextBlock) ovládacího prvku.

## <a name="to-create-a-class-to-use-as-a-data-source"></a>Pro vytvoření třídy použít jako zdroj dat

1. Na **soubor** nabídce zvolte **nový**> **projektu**.

1. V **nový projekt** dialogovém okně vyberte buď **Visual C#** nebo **jazyka Visual Basic** uzlu, rozbalte **Windows Desktop** uzlu a potom Vyberte **aplikaci WPF** šablony.

1. Název projektu **BindingTest**a potom zvolte **OK** tlačítko.

1. Otevřete soubor MainWindow.xaml.cs (nebo MainWindow.xaml.vb) a přidejte následující kód. V jazyce C#, přidat kód `BindingTest` obor názvů (před posledním kulaté závorky v souboru). V jazyce Visual Basic přidejte novou třídu.

   ```csharp
   public class ShoppingCart : DependencyObject
   {
       public int ItemCount
       {
           get { return (int)GetValue(ItemCountProperty); }
           set { SetValue(ItemCountProperty, value); }
       }

       public static readonly DependencyProperty ItemCountProperty =
            DependencyProperty.Register("ItemCount", typeof(int),
            typeof(ShoppingCart), new PropertyMetadata(0));
   }
   ```

   ```vb
   Public Class ShoppingCart
       Inherits DependencyObject

       Public Shared ReadOnly ItemCountProperty As DependencyProperty = DependencyProperty.Register(
            "ItemCount", GetType(Integer), GetType(ShoppingCart), New PropertyMetadata(0))
       Public Property ItemCount As Integer
           Get
               ItemCount = CType(GetValue(ItemCountProperty), Integer)
           End Get
           Set(value As Integer)
               SetValue(ItemCountProperty, value)
           End Set
       End Property
   End Class
   ```

   Tento kód pomocí hodnoty 0 nastaví jako výchozí počet položek [PropertyMetadata](/uwp/api/Windows.UI.Xaml.PropertyMetadata) objektu.

1. Na **souboru** nabídky, zvolte **sestavení** > **sestavit řešení**.

## <a name="to-bind-the-itemcount-property-to-a-textblock-control"></a>Vazby ItemCount vlastnosti do ovládacího prvku TextBlock

1. V Průzkumníku řešení otevřete místní nabídku pro MainWindow.xaml a zvolte **Návrhář zobrazení**.

1. V panelu nástrojů vyberte [mřížky](/uwp/api/Windows.UI.Xaml.Controls.Grid) řízení a přidat jej do formuláře.

1. S `Grid` vybrali, v okně vlastností zvolte **nový** vedle položky **DataContext** vlastnost.

1. V **vyberte objekt** dialogové okno pole, ujistěte se, že **zobrazit ve všech sestaveních** není zaškrtnuté políčko, zvolte **ShoppingCart** pod **BindingTest** obor názvů a potom zvolte **OK** tlačítko.

     Následující obrázek ukazuje **vyberte objekt** dialogové okno s **ShoppingCart** vybrané.

     ![Dialogové okno Vyberte objekt](../designers/media/blendselectobject.PNG "BlendSelectObject")

1. V **sada nástrojů**, vyberte `TextBlock` ovládací prvek pro přidání do formuláře.

1. S `TextBlock` ovládací prvek vybrán, v okně vlastností zvolte vlastnost značky vpravo od **Text** vlastnost a potom zvolte **vytvoření datové vazby**. (Vlastnost značky vypadá malé pole.)

1. V datech vytvořit vazby dialogové okno, ve **cesta** , vyberte **ItemCount: (int32)** vlastnost a potom zvolte **OK** tlačítko.

     Následující obrázek ukazuje **vytvoření datové vazby** dialogové okno s **ItemCount** vybrané vlastnosti.

     ![Create Data Binding dialog box](../designers/media/xaml_create_data_binding.png "xaml_create_data_binding")

1. Stiskněte klávesu **F5** a spusťte aplikaci.

     `TextBlock` Ovládacího prvku by měl zobrazit výchozí hodnota 0 jako text.

## <a name="see-also"></a>Viz také

[Vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)  
[Převaděč hodnoty dialogové okno Přidat](https://msdn.microsoft.com/c5f3d110-a541-4b55-8bca-928f77778af8)