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
ms.assetid: 1a99aeae-c3ef-407d-ba79-b8055489a43d
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 4e2192a7fbcf2491a0e131ee6d6df0ead16238fd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-binding-to-data-in-xaml-designer"></a>Návod: Vytvoření vazby na data v Návrháři XAML
V Návrháři XAML můžete nastavit vlastnosti datové vazby pomocí návrhové plochy a v okně Vlastnosti. V příkladu v tomto průvodci ukazuje, jak k vytvoření vazby dat k ovládacímu prvku. Konkrétně návod ukazuje, jak vytvořit jednoduché nákupní košík třídy, která má [vlastnost DependencyProperty](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.dependencyproperty.aspx) s názvem `ItemCount`a pak vytvořte vazbu `ItemCount` vlastnost, která má **Text** vlastnost nástroje [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) ovládacího prvku.  
  
### <a name="to-create-a-class-to-use-as-a-data-source"></a>Pro vytvoření třídy použít jako zdroj dat  
  
1.  Na **soubor** nabídce zvolte **nový**, **projektu**.  
  
2.  V **nový projekt** dialogovém okně vyberte buď **Visual C#** nebo **jazyka Visual Basic** uzlu, rozbalte **Windows Desktop** uzlu a potom Vyberte **aplikaci WPF** šablony.  
  
3.  Název projektu **BindingTest**a potom zvolte **OK** tlačítko.  
  
4.  Otevřete soubor MainWindow.xaml.cs (nebo MainWindow.xaml.vb) a přidejte následující kód. V jazyce C#, přidat kód `BindingTest` obor názvů (před posledním kulaté závorky v souboru). V jazyce Visual Basic přidejte novou třídu.  
  
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
  
     Tento kód pomocí hodnoty 0 nastaví jako výchozí počet položek [PropertyMetadata](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.propertymetadata.aspx) objektu.  
  
5.  Na **souboru** nabídky, zvolte **sestavení**, **sestavit řešení**.  
  
### <a name="to-bind-the-itemcount-property-to-a-textblock-control"></a>Vazby ItemCount vlastnosti do ovládacího prvku TextBlock  
  
1.  V Průzkumníku řešení otevřete místní nabídku pro MainWindow.xaml a zvolte **Návrhář zobrazení**.  
  
2.  V panelu nástrojů vyberte [mřížky](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.grid.aspx) řízení a přidat jej do formuláře.  
  
3.  S `Grid` vybrali, v okně vlastností zvolte **nový** vedle položky **DataContext** vlastnost.  
  
4.  V **vyberte objekt** dialogové okno pole, ujistěte se, že **zobrazit ve všech sestaveních** není zaškrtnuté políčko, zvolte **ShoppingCart** pod **BindingTest** obor názvů a potom zvolte **OK** tlačítko.  
  
     Následující obrázek ukazuje **vyberte objekt** dialogové okno s **ShoppingCart** vybrané.  
  
     ![Dialogové okno Vybrat objekt](../designers/media/blendselectobject.PNG "BlendSelectObject")  
  
5.  V **sada nástrojů**, vyberte `TextBlock` ovládací prvek pro přidání do formuláře.  
  
6.  S `TextBlock` ovládací prvek vybrán, v okně vlastností zvolte vlastnost značky vpravo od **Text** vlastnost a potom zvolte **vytvoření datové vazby**. (Vlastnost značky vypadá malé pole.)  
  
7.  V datech vytvořit vazby dialogové okno, ve **cesta** , vyberte **ItemCount: (int32)** vlastnost a potom zvolte **OK** tlačítko.  
  
     Následující obrázek ukazuje **vytvoření datové vazby** dialogové okno s **ItemCount** vybrané vlastnosti.  
  
     ![Datové vazby dialogové okno vytvořit](../designers/media/xaml_create_data_binding.png "xaml_create_data_binding")  
  
8.  Stisknutím klávesy F5 a spusťte aplikaci.  
  
     `TextBlock` Ovládacího prvku by měl zobrazit výchozí hodnota 0 jako text.  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)   
 [Převaděč hodnoty dialogové okno Přidat](https://msdn.microsoft.com/en-us/c5f3d110-a541-4b55-8bca-928f77778af8)