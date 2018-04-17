---
title: Postup vytvoření a použití prostředku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
f1_keywords:
- VS.XamlDesigner.CreateResource
- VS.XamlDesigner.EditResource
ms.assetid: 3ff4006d-659d-4073-9a41-06ff85e6cfdf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 60b832e1c4b1834e35cc2ab6427b2686f5d730a8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-and-apply-a-resource"></a>Postup vytvoření a použití prostředku
Styly a šablony pro elementy v Návrháři XAML jsou uloženy v opakovaně použitelné entity názvem prostředky. Styly umožňují nastavit vlastnosti elementu a znovu použít tato nastavení pro konzistentní vzhled napříč více elementů. A [ControlTemplate](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.controltemplate.aspx) definuje vzhledu ovládacího prvku a můžete také použít jako zdroj. Další informace najdete v tématu [rychlý start: ovládací prvky stylu](http://go.microsoft.com/fwlink/?LinkID=248239) a [rychlý start: řízení šablony](http://go.microsoft.com/fwlink/?LinkID=247982).  
  
 Pokaždé, když vytvoříte nový prostředek z existující vlastnost, [styl](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.style.aspx), nebo `ControlTemplate`, **vytvořit prostředek** dialogové okno umožňuje definovat prostředek na úrovni aplikace, úrovni dokumentu nebo na úrovni elementu. Tyto úrovně určit, kde můžete použít k prostředku. Například pokud je definován prostředek na úrovni element, prostředek lze použít pouze k elementu, na kterém jste ji vytvořili. Také lze zvolit uložení prostředku do adresáře zdrojů, což je oddělený soubor, který lze znovu použít v jiném projektu.  
  
### <a name="to-create-a-new-resource"></a>Chcete-li vytvořit nový prostředek  
  
1.  XAML souborem otevřít v Návrháři XAML vytvořte prvek, nebo zvolte element v okně Osnova dokumentu.  
  
2.  V okně vlastností zvolte značky vlastnost, která se zobrazí jako symbol pole napravo od hodnotu vlastnosti, a pak zvolte **převést na nový prostředek**. Symbol bílé pole určuje výchozí hodnotu a symbol černé políčko obvykle značí, že byla nainstalována místní prostředek  
  
     Zobrazí se příslušné dialogové okno pro tvorbu prostředku. Toto dialogové okno se zobrazí při vytváření prostředku z štětce:  
  
     ![Vytvořit prostředek – dialogové okno](../designers/media/xaml_create_resource.png "xaml_create_resource")  
  
3.  V **název (klíč)** zadejte název klíče. Toto je název, který můžete použít, pokud chcete další prvky tak, aby odkazovaly na prostředek.  
  
4.  V části **definovat v**, zvolte možnost, která určuje, kde má být definován prostředek:  
  
    -   Chcete-li prostředek k dispozici pro libovolného dokumentu ve vaší aplikaci, vyberte **aplikace**.  
  
    -   Chcete-li k dispozici pouze v aktuálním dokumentu prostředek, zvolte **tento dokument**.  
  
    -   Chcete-li byly prostředek k dispozici pouze element z jste vytvořili prostředek nebo na její podřízené elementy, zvolte **tento dokument**a v rozevíracím seznamu vyberte *element*: *název* .  
  
    -   Chcete-li definovat prostředku v souboru slovník prostředků, které můžete opakovaně použít v jiné projekty, klikněte na tlačítko **slovník prostředků**a potom vyberte existující soubor slovník prostředků, jako například **StandardStyles.xaml**, v rozevíracím seznamu.  
  
5.  Vyberte **OK** tlačítko vytvořit prostředek a použijte ho k elementu, ze kterého jste vytvořili.  
  
### <a name="to-apply-a-resource-to-an-element-or-property"></a>Chcete-li použít prostředek na prvek nebo vlastnost  
  
1.  V okně Osnova dokumentu zvolte elementu, který chcete použít prostředku.  
  
2.  Proveďte jednu z těchto akcí:  
  
    -   Platí pro vlastnost prostředku. V okně vlastností zvolte vlastnost značky vedle hodnota vlastnosti a potom vyberte **místní prostředek** nebo **systémový prostředek**a potom vyberte prostředek k dispozici v seznamu, který se zobrazí.  
  
         Pokud se nezobrazí na prostředek, který byste měli vidět, může to být způsobeno typ prostředku neshoduje s typem vlastnosti.  
  
    -   Použít styl nebo řízení prostředku šablony do ovládacího prvku. Otevřete vyberte kontextovou nabídku ovládacího prvku v okně Osnova dokumentu **upravit šablonu** nebo **upravit další šablony**, zvolte **použít prostředků**a potom vyberte Název šablony ovládací prvek seznamu, které se zobrazí.  
  
        > [!NOTE]
        >  **Úprava šablony** se používá k aplikování šablon ovládacích prvků. **Upravit další šablony** se používá k aplikování jiné typy šablon.  
  
     Prostředky je možné použít vždy, když jsou kompatibilní. Například prostředek štětce lze použít k **popředí** vlastnost <xref:Windows.UI.Xaml.Controls.TextBox> ovládacího prvku.  
  
### <a name="to-edit-a-resource"></a>Chcete-li upravit prostředek  
  
1.  Vyberte element na návrhové plochy nebo v okně Osnova dokumentu.  
  
2.  Zvolte výchozí nebo místní vlastnost značky vpravo od vlastnost v okně vlastností a pak zvolte **upravit prostředků** otevřete **upravit prostředků** dialogové okno.  
  
3.  Změna možností pro daný prostředek.  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)