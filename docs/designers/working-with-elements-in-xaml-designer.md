---
title: Práce s prvky v Návrháři XAML
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a29690bf-f212-4ac6-a77a-adc53d14102e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 1dd5fc65c2770ce0491a91975600906aa82a266d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="working-with-elements-in-xaml-designer"></a>Práce s prvky v Návrháři XAML
Můžete přidat prvky – ovládací prvky, rozložení a obrazců – do vaší aplikace v jazyce XAML, v kódu, nebo pomocí návrháře XAML. Toto téma popisuje, jak pracovat s prvky v Návrháři XAML v sadě Visual Studio nebo Blend for Visual Studio.

## <a name="adding-an-element-to-a-layout"></a>Přidat element do rozložení
 *Rozložení* je proces Změna velikosti a rozmístění prvků v uživatelského rozhraní. Na pozici vizuální prvky, musíte umístit je v rozložení [Panel](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.panel.aspx). A `Panel` má vlastnost podřízené, což je kolekce z [FrameworkElement](http://msdn.microsoft.com/library/windows/apps/br208706.aspx) typy. Můžete použít různé `Panel` podřízené prvky, jako například [plátno](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.canvas.aspx), [StackPanel](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.stackpanel.aspx), a [mřížky](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.grid.aspx), která bude sloužit jako kontejnerů rozložení a k pozice a uspořádat prvky na stránce.

 Ve výchozím nastavení `Grid` panely slouží jako kontejner nejvyšší úrovně rozložení v rámci stránky nebo formuláře. Můžete přidat panelů rozložení, ovládací prvky nebo jiných prvků v rámci rozložení pro stránku nejvyšší úrovně.

#### <a name="to-add-an-element-to-a-layout"></a>Chcete-li přidat element do rozložení

-   V Návrháři XAML proveďte jednu z následujících akcí:

    -   Dvakrát klikněte na panel prvek v **sada nástrojů** (nebo v panelu nástrojů vyberte element a stiskněte klávesu Enter).

    -   Přetáhněte element z **sada nástrojů** na kreslicí plochu.

    -   V **sada nástrojů**, vyberte jednu z nástrojů pro kreslení (například [elipsy](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.shapes.ellipse.aspx) nebo [obdélníku](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.shapes.rectangle.aspx)) a pak vykreslení elementu active panelu.

## <a name="changing-the-layering-order-of-elements"></a>Změna rozvrstvení pořadí prvků
 Pokud existují dva elementy na návrhové plochy v Návrháři XAML, objeví se před druhý v pořadí rozvrstvení jeden element. V dolní části seznamu elementů v Osnova dokumentu – okno je přední krajní elementu (s výjimkou, kdy **ZIndex** nastavena pro element). Při vložení prvku do stránky, formulář nebo rozložení kontejneru, je před další prvky v elementu kontejner služby active automaticky umístí elementu. Chcete-li změnit pořadí prvků, můžete použít **pořadí** příkazy nebo přetáhněte elementy ve stromu objektů v okně Osnova dokumentu.

#### <a name="to-change-the-layering-order"></a>Chcete-li změnit pořadí vrstev

-   Proveďte jednu z těchto akcí:

    -   V **Osnova dokumentu** okně přetažením elementy nahoru nebo dolů k vytvoření požadované rozvrstvení pořadí.

    -   Klikněte pravým tlačítkem na element v okně Osnova dokumentu nebo návrhové plochy, pro kterou chcete změnit pořadí vrstev, přejděte na **pořadí**a pak klikněte na jednu z následujících akcí:

        -   **Přenést do popředí** aby element zcela na začátek pořadí.

        -   **Přenese dopředu** aby element předávat jednu úroveň v pořadí.

        -   **Odeslat zpětně** odeslat zpět jednu úroveň prvek v pořadí.

        -   **Přenést do pozadí** odeslat element zcela na zadní straně pořadí.

     Změna **ZIndex** vlastnost **rozložení** oddíl v okně Vlastnosti. Překrývajících se elementy, **ZIndex** vlastnost má přednost před pořadí prvků zobrazený v okně Osnova dokumentu. Element, který má nižší **ZIndex** se vyskytuje hodnota vpředu při prvky překrývat.

## <a name="changing-the-alignment-of-an-element"></a>Změna zarovnání elementu
 Elementy v kreslicí plochy můžete zarovnat pomocí příkazů nabídky nebo přetažením elementů na zarovnávací čáry.

 A *snapline* je vizuální upozornění, která vám pomůže zarovnat element relativně k další prvky v aplikaci.

#### <a name="to-align-two-or-more-elements-by-using-menu-commands"></a>Chcete-li zarovnat dva nebo více elementům pomocí příkazů nabídky

1.  Vyberte prvky, které chcete zarovnat. Stisknutím a podržením klávesy Ctrl a vyberte elementy můžete vybrat více než jeden element.

2.  Vyberte jednu z následujících vlastností v rámci **HorizontalAlignment –** v **rozložení** části okna vlastností: **doleva**, **Center**, **Vpravo**, nebo **Stretch**.

3.  Vyberte jednu z následujících vlastností v rámci **VerticalAlignment** v **rozložení** části okna vlastností: **horní**, **Center**, **Dolní**, nebo **Stretch**.

#### <a name="to-align-two-or-more-elements-by-using-snaplines"></a>Chcete-li zarovnat dva nebo více prvků pomocí zarovnávacích čar

-   V Návrháři XAML v rozložení, který obsahuje minimálně dva elementy přetáhněte nebo změňte velikost jednoho prvku tak, aby okraj je zarovnáno s jiný element.

     Když je zarovnán okrajů, *zarovnání hranic* se zobrazí k označení zarovnání. Zarovnání hranic je red přerušovaná čára. Zarovnání hranice zobrazí pouze tehdy, když **přichycení k zarovnávací čáry** je povoleno. Pro ilustraci návrhové plochy, který ukazuje hranici zarovnání, najdete v části [vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).

## <a name="changing-the-an-elements-margins"></a>Změna elementu okraje
 Okraje v Návrháři XAML určují množství volné místo, které je kolem elementu na návrhové plochy. Například okraje zadejte velikost místa mezi mimo hran elementu a hranice `Grid` panel, který obsahuje element. Okraje také určit množství místa mezi elementy, které jsou součástí `StackPanel`.

#### <a name="to-change-an-elements-margins-in-the-properties-window"></a>Chcete-li změnit okrajů elementu v okně vlastností

1.  Vyberte element, jehož okraje chcete změnit.

2.  V části **rozložení** v okně vlastností změňte hodnotu (v pixelech nebo jednotky nezávislé na zařízení, které jsou přibližně 1/96 palce) pro některý z **okraj** vlastnosti (**horní**, **Doleva**, **vpravo**, nebo **dolní**).

#### <a name="to-change-an-elements-margins-in-the-artboard"></a>Chcete-li změnit okrajů elementu v kreslicí plochy

-   Chcete-li změnit okraje elementu vzhledem k jejímu kontejneru rozložení, klikněte na tlačítko *okrajů ozdobného prvku* , při elementu je vybrán a v rámci kontejneru rozložení jsou kolem element v kreslicí plochy. Obrázek, který ukazuje ozdobného prvku okraj, najdete v části [vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).

     Pokud adorner okraj je otevřená, vodorovně nebo svisle, že marže není nastaven. Pokud je zavřená adorner okraj, že marže nastavena.

     Když otevřete adorner okraj a není nastaven strana okraje, strana okraje nastavena na správnou hodnotu podle umístění prvku v kreslicí plochy. Pro strana okraje, jako **doleva** a **vpravo** okraje, alespoň jednu vlastnost je vždycky nastavený.

    > [!IMPORTANT]
    >  Elementy umístěn uvnitř některé kontejnerů rozložení, například <xref:Windows.UI.Xaml.Controls.Canvas>, nemají ozdobného prvku okraj. Elementy umístěn uvnitř <xref:Windows.UI.Xaml.Controls.StackPanel> mít ozdobného prvku rozpětí pro buď levého a dolního okraje nebo horní a dolní okraj, v závislosti na orientaci `StackPanel`.

## <a name="grouping-and-ungrouping-elements"></a>Seskupení a oddělení elementy
 Seskupení dvou nebo více elementům v Návrháři XAML vytvoří nový kontejner rozložení a umístí tyto elementy v tomto kontejneru. Společně umístit dvě nebo více elementům v kontejneru rozložení umožňuje snadno vyberte, přesouvání a transformaci skupiny, jako kdyby elementů v této skupině jeden element. Seskupení je také užitečné pro identifikaci elementy, které se vztahují k sobě navzájem nějakým způsobem, jako jsou tlačítka, která tvoří prvek navigace. Když oddělíte elementy, který odstraňujete jednoduše rozložení kontejneru, která obsahovala elementy.

#### <a name="to-group-elements-into-a-new-layout-container"></a>Na elementy skupiny do nového kontejneru rozložení

1.  Vyberte prvky, které chcete seskupit. (Pokud chcete vybrat víc elementů, stiskněte a podržte klávesu Ctrl a klepněte na ně.)

2.  Klikněte pravým tlačítkem na vybrané elementy, přejděte na **skupiny do**a pak klikněte na typ rozložení kontejner, ve kterém chcete jsou umístěny na skupinu.

    > [!TIP]
    >  Pokud vyberete <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border>, nebo <xref:Windows.UI.Xaml.Controls.ScrollViewer> prvky vaši seskupíte elementy jsou umístěny v nové <xref:Windows.UI.Xaml.Controls.Grid> panelu v rámci <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border>, nebo <xref:Windows.UI.Xaml.Controls.ScrollViewer>. Pokud oddělíte prvky v jednom z těchto kontejnerů rozložení, jenom <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border>, nebo <xref:Windows.UI.Xaml.Controls.ScrollViewer> se odstraní a <xref:Windows.UI.Xaml.Controls.Grid> panelu zůstanou. Chcete-li odstranit `Grid` panelu, dojde k oddělení prvků znovu.

#### <a name="to-ungroup-elements-and-delete-the-layout"></a>Zrušit seskupení elementy a odstraňovat rozložení

-   Pravým tlačítkem na skupinu, kterou chcete rozdělit skupinu a klikněte na tlačítko **oddělit**.

 Můžete také seskupení nebo oddělení elementy kliknete pravým tlačítkem na vybrané položky v okně Osnova dokumentu a kliknutím na **skupiny do** nebo **oddělit**.

## <a name="resetting-the-element-layout"></a>Resetování rozložení – element
 Pomocí příkazů resetování rozložení můžete obnovit výchozí hodnoty pro vlastnosti konkrétní rozložení elementu. Pomocí tohoto příkazu můžete resetovat okraj, zarovnání, šířky, výšky a velikost elementu, jednotlivě nebo společně.

#### <a name="to-reset-the-element-layout"></a>Chcete-li obnovit rozložení – element

-   V okně Osnova dokumentu nebo návrhové plochy, klikněte pravým tlačítkem na element, zvolte **rozložení**, **resetovat** *PropertyName*, kde *PropertyName*je vlastnost, která chcete obnovit (nebo zvolte **rozložení**, **Obnovit vše** resetovat všechny vlastnosti rozložení pro element).

## <a name="see-also"></a>Viz také

- [Vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)