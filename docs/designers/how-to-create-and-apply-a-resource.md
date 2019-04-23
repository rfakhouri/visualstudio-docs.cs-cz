---
title: Vytvoření a použití prostředku
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
ms.openlocfilehash: 6622285d985d75c547428163b0b6cdaa8f699fe0
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60085685"
---
# <a name="how-to-create-and-apply-a-resource"></a>Vytvoření a použití prostředku
Styly a šablony pro elementy v Návrháři XAML jsou uloženy v opakovaně použitelné entity nazývané prostředky. Styly umožňují nastavit vlastnosti elementu a použít tato nastavení pro jednotný vzhled napříč více prvků. A [ControlTemplate](/uwp/api/Windows.UI.Xaml.Controls.ControlTemplate) definuje vzhled ovládacího prvku a mohou být použity také jako prostředek. Další informace najdete v tématu [rychlý start: Používání stylů pro ovládací prvky](http://go.microsoft.com/fwlink/?LinkID=248239) a [rychlý start: Ovládací prvek šablony](http://go.microsoft.com/fwlink/?LinkID=247982).

 Při každém vytvoření nového prostředku z existující vlastnosti [styl](/uwp/api/Windows.UI.Xaml.Style), nebo `ControlTemplate`, **vytvořit prostředek** dialogové okno umožňuje definovat prostředek na úrovni aplikace, úrovni dokumentu nebo na úrovni prvku. Tyto úrovně určit, kde lze prostředek použít. Například pokud definujete prostředek na úrovni prvku, prostředek je použít jenom na element, na kterém jste vytvořili. Také lze zvolit uložení prostředku do adresáře zdrojů, což je oddělený soubor, který lze znovu použít v jiném projektu.

### <a name="to-create-a-new-resource"></a>Chcete-li vytvořit nový prostředek

1. S XAML soubor otevřen v Návrháři XAML vytvořte element nebo zvolte prvek v okně osnovy dokumentu.

2. V okně Vlastnosti zvolte značku vlastnosti, které se zobrazí jako symbol políčka napravo od hodnoty vlastnosti, a klikněte na tlačítko **převést na nový prostředek**. Symbol bílé pole určuje výchozí hodnotu a symbol černé skříňky obvykle značí, že použití místního prostředku.

     Zobrazí se příslušné dialogové okno pro tvorbu prostředku. Při vytváření prostředku ze štětce, zobrazí se toto dialogové okno:

     ![Vytvořit prostředek – dialogové okno](../designers/media/xaml_create_resource.png)

3. V **název (klíč)** zadejte název klíče. Toto je název, který vám pomůže při dalších prvků, které odkazují na prostředek.

4. V části **definovat v**, zvolte možnost, která určuje, kde chcete prostředek, který chcete definovat:

    - Chcete-li být prostředek dostupný libovolnému dokumentu v aplikaci, zvolte **aplikace**.

    - Chcete-li být prostředek přístupný pouze v aktuálním dokumentu, zvolte **tento dokument**.

    - Chcete-li být prostředek přístupný pouze na prvek z jste vytvořili prostředek nebo na jeho podřízené prvky, zvolte **tento dokument**a v rozevíracím seznamu vyberte **element**: **název** .

    - Chcete-li definovat prostředek v souboru slovníku prostředků, který lze opětovně použít v jiných projektech, klikněte na tlačítko **slovník prostředků**a potom vyberte existující soubor slovníku prostředků, jako je například **StandardStyles.xaml**, v rozevíracím seznamu.

5. Zvolte **OK** tlačítko má prostředek vytvořit a použít ji k elementu, ze kterého jste vytvořili.

### <a name="to-apply-a-resource-to-an-element-or-property"></a>Chcete-li použít prostředek na element nebo vlastnost

1. V okně osnovy dokumentu zvolte element, na který chcete použít prostředek.

2. Proveďte jednu z těchto akcí:

   - Použití prostředku na vlastnost. V okně Vlastnosti vyberte značka vlastnosti vedle hodnoty vlastností, vyberte **místního prostředku** nebo **systémový prostředek**a pak zvolte ze seznamu, který se zobrazí dostupné zdroje.

      Pokud nevidíte prostředek, který byste měli vidět, může to být způsobeno typ prostředku neodpovídá typu vlastnosti.

   - Platí pro ovládací prvek prostředku šablony stylů nebo ovládací prvek. Otevřete zvolte v místní nabídce (kontextová nabídka) pro ovládací prvek v okně Osnova dokumentu **upravit šablonu** nebo **upravit další šablony**, zvolte **aplikovat zdroj**, a pak vyberte název šablony ovládacích prvků ze seznamu, který se zobrazí.

     > [!NOTE]
     > **Úprava šablony** použije šablony ovládacího prvku. **Upravit další šablony** platí jiné typy šablon.

     Prostředky můžete použít bez ohledu na to jsou kompatibilní. Například můžete použít na prostředek štětce **popředí** vlastnost <xref:Windows.UI.Xaml.Controls.TextBox> ovládacího prvku.

### <a name="to-edit-a-resource"></a>Chcete-li upravit prostředek

1. Vyberte prvek na návrhové ploše nebo v okně osnovy dokumentu.

2. Zvolte výchozí nebo místní vlastnost značky vpravo od vlastnosti v okně Vlastnosti a pak zvolte **upravit prostředek** otevřít **upravit prostředek** dialogové okno.

3. Změna možností pro prostředek.

## <a name="see-also"></a>Viz také:

- [Vytvoření uživatelského rozhraní pomocí Návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)