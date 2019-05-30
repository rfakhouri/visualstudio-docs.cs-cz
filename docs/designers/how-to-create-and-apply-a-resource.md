---
title: Postup vytvoření a použití prostředku
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VS.XamlDesigner.CreateResource
- VS.XamlDesigner.EditResource
ms.assetid: 3ff4006d-659d-4073-9a41-06ff85e6cfdf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f9eee42d9e3a48f77153e5bd94f72a975ab27843
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/28/2019
ms.locfileid: "66263396"
---
# <a name="how-to-create-and-apply-a-resource"></a>Postup vytvoření a použití prostředku

Styly a šablony pro elementy v Návrháři XAML jsou uloženy v opakovaně použitelné entity nazývané prostředky. Styly umožňují nastavit vlastnosti elementu a použít tato nastavení pro jednotný vzhled napříč více prvků. A [ControlTemplate](/uwp/api/Windows.UI.Xaml.Controls.ControlTemplate) definuje vzhled ovládacího prvku a mohou být použity také jako prostředek. Další informace najdete v tématu [rychlý start: Používání stylů pro ovládací prvky](http://go.microsoft.com/fwlink/?LinkID=248239) a [rychlý start: Ovládací prvek šablony](http://go.microsoft.com/fwlink/?LinkID=247982).

Při každém vytvoření nového prostředku z existující vlastnosti [styl](/uwp/api/Windows.UI.Xaml.Style), nebo `ControlTemplate`, **vytvořit prostředek** dialogové okno umožňuje definovat prostředek na úrovni aplikace, úrovni dokumentu nebo na úrovni prvku. Tyto úrovně určit, kde lze prostředek použít. Například pokud definujete prostředek na úrovni prvku, prostředek je použít jenom na element, na kterém jste vytvořili. Můžete také zvolit uložení prostředku v [slovník prostředků](/windows/uwp/design/controls-and-patterns/resourcedictionary-and-xaml-resource-references), což je samostatný soubor, který lze znovu použít v jiném projektu.

## <a name="create-a-new-resource"></a>Vytvořit nový prostředek

1. S XAML soubor otevřen v Návrháři XAML vytvořte element nebo zvolte prvek v okně osnovy dokumentu.

2. V **vlastnosti** okna, vyberte vlastnost značky, které se zobrazí jako symbol políčka napravo od hodnoty vlastnosti, a pak zvolte **převést na nový prostředek**. Symbol bílé pole určuje výchozí hodnotu a symbol černé skříňky obvykle značí, že použití místního prostředku.

     Zobrazí se příslušné dialogové okno pro tvorbu prostředku. Při vytváření prostředku ze štětce, zobrazí se toto dialogové okno:

     ![Vytvořit prostředek – dialogové okno](../designers/media/xaml_create_resource.png)

3. V **název (klíč)** zadejte název klíče. Toto je název, který vám pomůže při dalších prvků, které odkazují na prostředek.

4. V části **definovat v**, zvolte možnost, která určuje, kde chcete prostředek, který chcete definovat:

    - Chcete-li být prostředek dostupný libovolnému dokumentu v aplikaci, zvolte **aplikace**.

    - Chcete-li být prostředek přístupný pouze v aktuálním dokumentu, zvolte **tento dokument**.

    - Chcete-li být prostředek přístupný pouze na prvek z jste vytvořili prostředek nebo na jeho podřízené prvky, zvolte **tento dokument**a v rozevíracím seznamu vyberte **element**: **název** .

    - Chcete-li definovat prostředek v [slovník prostředků](/windows/uwp/design/controls-and-patterns/resourcedictionary-and-xaml-resource-references) soubor, který lze opětovně použít v jiných projektech, klikněte na tlačítko **slovník prostředků**. Potom vyberte existující soubor slovníku prostředků, jako je například **StandardStyles.xaml**, v rozevíracím seznamu.

5. Zvolte **OK** tlačítko má prostředek vytvořit a použít ji k elementu, ze kterého jste vytvořili.

## <a name="apply-a-resource-to-an-element-or-property"></a>Použití prostředků na element nebo vlastnost

1. V okně osnovy dokumentu zvolte element, na který chcete použít prostředek.

2. Proveďte jednu z těchto akcí:

   - Použití prostředku na vlastnost. V **vlastnosti** okno, vyberte značku vlastnosti vedle hodnoty vlastností, vyberte **místního prostředku** nebo **systémový prostředek**a pak zvolte prostředek k dispozici ze seznamu, který se zobrazí.

      Pokud nevidíte prostředek, který byste měli vidět, může to být způsobeno typ prostředku neodpovídá typu vlastnosti.

   - Platí pro ovládací prvek prostředku šablony stylů nebo ovládací prvek. Otevřete zvolte v místní nabídce (kontextová nabídka) pro ovládací prvek v okně Osnova dokumentu **upravit šablonu** nebo **upravit další šablony**, zvolte **aplikovat zdroj**, a pak vyberte název šablony ovládacích prvků ze seznamu, který se zobrazí.

     > [!NOTE]
     > **Úprava šablony** použije šablony ovládacího prvku. **Upravit další šablony** platí jiné typy šablon.

     Prostředky můžete použít bez ohledu na to jsou kompatibilní. Například můžete použít na prostředek štětce **popředí** vlastnost <xref:Windows.UI.Xaml.Controls.TextBox> ovládacího prvku.

## <a name="edit-a-resource"></a>Úprava prostředku

1. Vyberte prvek na návrhové ploše nebo v okně osnovy dokumentu.

2. Zvolte výchozí nebo místní vlastnost značku napravo od vlastnost **vlastnosti** okna a klikněte na tlačítko **upravit prostředek** otevřete **upravit prostředek** dialogové okno.

3. Změna možností pro prostředek.

## <a name="see-also"></a>Viz také:

- [Vytvoření uživatelského rozhraní pomocí Návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)
