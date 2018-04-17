---
title: Uspořádání objektů do kontejnerů rozložení v Návrháři XAML
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 29c80c38-0fa3-48d6-b3a8-3b864f482e44
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 2a2f7824ed53daf61113a7c2656d0de69d53e5b9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="organize-objects-into-layout-containers-in-xaml-designer"></a>Uspořádání objektů do kontejnerů rozložení v Návrháři XAML

Tento článek popisuje panelů rozložení a ovládací prvky pro Návrhář XAML.

Představte si, kam chcete objekty, které se zobrazí na stránce. objekty, například bitové kopie, tlačítka a videa. Možná budete chtít zobrazit v řádků a sloupců na jediném řádku svisle nebo vodorovně nebo v pevné pozici.

Po vám, že možnost myslíte o tom, jak může vypadat stránky, vyberte panelu rozložení. Všechny stránky spustit s jedním, protože potřebujete něco přidat objekty do. Ve výchozím nastavení je **mřížky**, ale který, můžete změnit.

Panelů rozložení můžete uspořádat objekty na stránce, ale více než dělají. Jejich nápovědy, které návrhu pro jiné velikosti obrazovky a jejich řešení. Když uživatelé spustí aplikaci, všechno panelu rozložení změní velikost tak, aby odpovídaly nemovitosti obrazovky svého zařízení. Samozřejmě pokud nechcete, aby vaše rozložení k tomu, můžete přepsat toto chování pro součást rozložení nebo celý rozložení. K řízení, které můžete použít vlastností výšky a šířky.

## <a name="layout-panels"></a>Panely rozložení

Spusťte stránku volbou jedné z těchto panelů rozložení. Stránka může mít více než jednou. Například můžete začít s **mřížky** rozložení panelu a pak přidejte **StackPanel** oblasti v **mřížky** tak, aby můžete uspořádat ovládací prvky svisle v tomto elementu.

Jsou použité nejvíce často se používá následující panelů rozložení, ale existují i další. Můžete je vyhledat všechny v **prostředky** panelu.

- [Mřížka](#Grid)

- [UniformGrid](#UniformGrid)

- [Plátno](#Canvas)

- [StackPanel](#stackpanel)

- [WrapPanel](#wrappanel)

- [DockPanel](#dockpanel)

### <a name="grid"></a>Mřížka

Umožňuje uspořádejte objekty do řádků a sloupců.

![Panely rozložení mřížky](../designers/media/98b234b2-ac3b-441f-9136-98375fee87b7.png)

### <a name="uniformgrid"></a>UniformGrid

Umožňuje uspořádejte objekty na stejné nebo uniform, mřížky oblasti. Tento panel je skvělá pro uspořádání seznamu obrázků.

![Rozložení panelu UniformGrid](../designers/media/928b9284-a7e8-4678-875a-656b80b78076.png)

(K dispozici jenom pro projekty WPF).

### <a name="canvas"></a>Plátno

Umožňuje uspořádejte objekty požadovaným způsobem. Když uživatelé spustí aplikaci, bude mít tyto prvky pevnou pozic na obrazovce.

![Rozložení panelu plátno](../designers/media/e1ae27f0-3a57-454e-b580-877dcea8836d.png)

### <a name="stackpanel"></a>StackPanel

Umožňuje uspořádejte objekty v jeden řádek, vodorovně nebo svisle.

![Rozložení panelu StackPanel](../designers/media/a85a7b57-b0a8-495e-b985-f0291e41d093.png)

### <a name="wrappanel"></a>WrapPanel

Umožňuje uspořádejte objekty postupně zleva doprava. Pokud panelu dojde místo na hranici úplně vpravo ho *zabalí* obsah na další řádek, a tak dále z zleva doprava, shora dolů. Můžete také nastavit orientaci panelu wrap svislé tak, aby objekty toku z horní části dolů, zleva doprava.

(K dispozici jenom pro projekty WPF).

![Rozložení panelu WrapPanel](../designers/media/b1c415fb-9a32-4a18-aa0b-308fca994ac9.png)

### <a name="dockpanel"></a>DockPanel

Umožňuje uspořádat objekty tak, aby zůstanou, nebo *ukotvení*, jeden okraj panelu.

(K dispozici jenom pro projekty WPF).

![Rozložení panelu DockPanel](../designers/media/72d46b58-9a49-4dd5-8af7-6843c0440226.png)

**Podívejte se na krátké video:** ![tlačítko Přehrát akci](../designers/media/bldadminconsoleinitialconfigicon.PNG) [WPF - DockPanel](https://www.youtube.com/watch?v=EBH_OIM-zPo)

## <a name="layout-controls"></a>Rozložení ovládacích prvků

Přidáním vašich objektů k ovládacím prvkům rozložení také. Nejsou jako bohaté funkce jako panely rozložení, ale mohou být užitečné je pro určité scénáře.

Následující ovládací prvky rozložení jsou nejoblíbenější, ale existují i další. Můžete je vyhledat všechny v **prostředky** panelu.

- [Ohraničení](#Border)

- [Popup](#Popup)

- [ScrollViewer](#scrollviewer)

- [Viewbox](#viewbox)

### <a name="border"></a>Ohraničení

Vytvořte ohraničení, pozadí nebo obě kolem objektu. Můžete přidat pouze jeden objekt, který má **ohraničení**. Pokud chcete použít ohraničení nebo pozadí pro více než jeden objekt, přidejte rozložení panelu **ohraničení**. Pak přidáte objekty do tohoto panelu nebo ovládací prvek.

![Rozložení ohraničení ovládacího prvku](../designers/media/e761238b-99fd-43c5-bbc4-57538b8289ff.png)

### <a name="popup"></a>Překryvný

Zobrazte informace nebo možnosti pro uživatele v okně. Můžete přidat pouze jeden objekt, který má **místní**. Ve výchozím nastavení **místní** obsahuje **mřížky** , ale který, můžete změnit.

### <a name="scrollviewer"></a>ScrollViewer

Povolit používá k přejděte dolů na stránku nebo oblast stránky. Můžete přidat pouze jeden objekt, který má **ScrollViewer** tak umožňuje spoustu smysl přidejte například panely rozložení **mřížky** nebo **StackPanel**.

![Ovládací prvek ScrollViewer rozložení](../designers/media/06b326d4-f23d-41a6-b26b-e1aff37572a7.png)

### <a name="viewbox"></a>Viewbox

Změna velikosti objektů, podobně jako s ovládacím prvkem přiblížení. Můžete přidat pouze jeden objekt, který má **Viewbox**. Pokud chcete použít tento efekt více než jeden objekt, přidejte panelu rozložení **ViewBox**a pak přidejte do tohoto panelu rozložení vaše ovládací prvky.

(K dispozici jenom pro projekty WPF).

![Ovládací prvek ViewBox rozložení](../designers/media/f5b13c66-d918-4141-8a16-bd8f8628687a.png)

## <a name="see-also"></a>Viz také

- [Práce s prvky v Návrháři XAML](../designers/working-with-elements-in-xaml-designer.md)
- [Vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)