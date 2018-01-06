---
title: "Uspořádání objektů do kontejnerů rozložení v Návrháři XAML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29c80c38-0fa3-48d6-b3a8-3b864f482e44
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 9c7b9c8f0f36435c2595a5df648daa54a614e278
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="organize-objects-into-layout-containers-in-xaml-designer"></a>Uspořádání objektů do kontejnerů rozložení v Návrháři XAML
Představte si, kam chcete objekty, které se zobrazí na stránce. objekty, například bitové kopie, tlačítka a videa. Možná budete chtít zobrazit v řádků a sloupců na jediném řádku svisle nebo vodorovně nebo v pevné pozici.  
  
 Po vám, že možnost myslíte o tom, jak může vypadat stránky, vyberte panelu rozložení. Všechny stránky spustit s jedním, protože potřebujete něco přidat objekty do. Ve výchozím nastavení je **mřížky** , ale který, můžete změnit.  
  
 Panelů rozložení můžete uspořádat objekty na stránce, ale více než dělají. Jejich nápovědy, které návrhu pro jiné velikosti obrazovky a jejich řešení. Když uživatelé spustí aplikaci, všechno panelu rozložení změní velikost tak, aby odpovídaly nemovitosti obrazovky svého zařízení. Samozřejmě pokud nechcete, aby vaše rozložení k tomu, můžete přepsat toto chování pro součást rozložení nebo celý rozložení. K řízení, které můžete použít vlastností výšky a šířky.  
  
 Tato stránka popisuje panelů rozložení a ovládací prvky a pak přesměruje, že vám krátké videa, která vám pomůže začít pracovat s nimi.  
  
> [!NOTE]
>  Některé z videí mohou odkazovat na Blend nebo Expression Blend, který použijete stejné návrháře XAML jako Visual Studio a nástroj Blend for Visual Studio.  
  
## <a name="layout-panels"></a>Panely rozložení  
 Spusťte stránku volbou jedné z těchto panelů rozložení. Stránka může mít více než jednou. Například můžete začít s **mřížky** rozložení panelu a pak přidejte **StackPanel** oblasti v **mřížky** tak, aby můžete uspořádat ovládací prvky svisle v tomto elementu.  
  
 Jsou použité nejvíce často se používá následující panelů rozložení, ale existují i další. Můžete je vyhledat všechny v **prostředky** panelu.  
  
-   [Mřížka](#Grid)  
  
-   [UniformGrid](#Uniform)  
  
-   [Plátno](#Canvas)  
  
-   [StackPanel](#Stack)  
  
-   [WrapPanel](#Wrap)  
  
-   [DockPanel](#Dock)  
  
###  <a name="Grid"></a>Mřížky  
 Umožňuje uspořádejte objekty do řádků a sloupců.  
  
 ![](../designers/media/98b234b2-ac3b-441f-9136-98375fee87b7.png "98b234b2-ac3b-441F-9136-98375fee87b7")  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [pomocí mřížky](http://www.popscreen.com/v/6A4hj/Microsoft-Expression-Blend-Using-Grids)  
  
###  <a name="Uniform"></a>UniformGrid  
 Umožňuje uspořádejte objekty na stejné nebo uniform, mřížky oblasti. Tento panel je skvělá pro uspořádání seznamu obrázků.  
  
 ![](../designers/media/928b9284-a7e8-4678-875a-656b80b78076.png "928b9284-a7e8-4678-875a-656b80b78076")  
  
 (Dostupné pouze pro projekty WPF)  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [práce UniformGrid](http://www.popscreen.com/v/6A4iq/Microsoft-Expression-Blend-Working-with-a-UniformGrid)  
  
###  <a name="Canvas"></a>Plátno  
 Umožňuje uspořádejte objekty požadovaným způsobem. Když uživatelé spustí aplikaci, bude mít tyto prvky pevnou pozic na obrazovce.  
  
 ![](../designers/media/e1ae27f0-3a57-454e-b580-877dcea8836d.png "e1ae27f0-3a57-454e-b580-877dcea8836d")  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [práce na plátno](http://www.popscreen.com/v/6A4hT/Microsoft-Expression-Blend-Working-with-the-Canvas)  
  
###  <a name="Stack"></a>StackPanel  
 Umožňuje uspořádejte objekty v jeden řádek, vodorovně nebo svisle.  
  
 ![](../designers/media/a85a7b57-b0a8-495e-b985-f0291e41d093.png "a85a7b57-b0a8-495e-b985-f0291e41d093")  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [práce s StackPanel a WrapPanel](http://www.popscreen.com/v/6A4i5/Microsoft-Expression-Blend-Using-the-StackPanel-and-WrapPanel)  
  
###  <a name="Wrap"></a>WrapPanel  
 Umožňuje uspořádejte objekty postupně zleva doprava. Pokud panelu dojde místo na hranici úplně vpravo ho *zabalí* obsah na další řádek, a tak dále z zleva doprava, shora dolů. Můžete také nastavit orientaci panelu wrap svislé tak, aby objekty toku z horní části dolů, zleva doprava.  
  
 (Dostupné pouze pro projekty WPF)  
  
 ![](../designers/media/b1c415fb-9a32-4a18-aa0b-308fca994ac9.png "b1c415fb-9a32-4a18-aa0b-308fca994ac9")  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [práce s StackPanel a WrapPanel](http://www.popscreen.com/v/6A4i5/Microsoft-Expression-Blend-Using-the-StackPanel-and-WrapPanel)  
  
###  <a name="Dock"></a>DockPanel  
 Umožňuje uspořádat objekty tak, aby zůstanou, nebo *ukotvení*, jeden okraj panelu.  
  
 (Dostupné pouze pro projekty WPF)  
  
 ![](../designers/media/72d46b58-9a49-4dd5-8af7-6843c0440226.png "72d46b58-9a49-4dd5-8af7-6843c0440226")  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [WPF - DockPanel](https://www.youtube.com/watch?v=EBH_OIM-zPo)  
  
## <a name="layout-controls"></a>Rozložení ovládacích prvků  
 Přidáním vašich objektů k ovládacím prvkům rozložení také. Nejsou jako bohaté funkce jako panely rozložení, ale mohou být užitečné je pro určité scénáře.  
  
 Jsou použité nejvíce často se používá následující prvky rozložení, ale existují i další. Můžete je vyhledat všechny v **prostředky** panelu.  
  
-   [Ohraničení](#Border)  
  
-   [Popup](#Popup)  
  
-   [ScrollViewer](#Scroll)  
  
-   [UniformGrid](#Uniform)  
  
-   [Viewbox](#View)  
  
###  <a name="Border"></a>Ohraničení  
 Vytvořte ohraničení, pozadí nebo obě kolem objektu. Můžete přidat pouze jeden objekt, který má **ohraničení**. Pokud chcete použít ohraničení nebo pozadí pro více než jeden objekt, přidejte rozložení panelu **ohraničení**. Pak přidáte objekty do tohoto panelu nebo ovládací prvek.  
  
 ![](../designers/media/e761238b-99fd-43c5-bbc4-57538b8289ff.png "e761238b-99fd-43c5-bbc4-57538b8289ff")  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [práce s ohraničení](http://www.popscreen.com/v/6A4hB/Microsoft-Expression-Blend-Working-with-Borders)  
  
###  <a name="Popup"></a>Místní nabídka  
 Zobrazte informace nebo možnosti pro uživatele v okně. Můžete přidat pouze jeden objekt, který má **místní**. Ve výchozím nastavení **místní** obsahuje **mřížky** , ale který, můžete změnit.  
  
###  <a name="Scroll"></a>ScrollViewer  
 Povolit používá k přejděte dolů na stránku nebo oblast stránky. Můžete přidat pouze jeden objekt, který má **ScrollViewer** tak umožňuje spoustu smysl přidejte například panely rozložení **mřížky** nebo **StackPanel**.  
  
 ![](../designers/media/06b326d4-f23d-41a6-b26b-e1aff37572a7.png "06b326d4-f23d-41a6-b26b-e1aff37572a7")  
  
###  <a name="View"></a>Viewbox  
 Změna velikosti objektů, podobně jako s ovládacím prvkem přiblížení. Můžete přidat pouze jeden objekt, který má **Viewbox**. Pokud chcete použít tento efekt více než jeden objekt, přidejte panelu rozložení **ViewBox**a pak přidejte do tohoto panelu rozložení vaše ovládací prvky.  
  
 (Dostupné pouze pro projekty WPF)  
  
 ![](../designers/media/f5b13c66-d918-4141-8a16-bd8f8628687a.png "f5b13c66-d918-4141-8a16-bd8f8628687a")  
  
## <a name="see-also"></a>Viz také  
 [Práce s prvky v Návrháři XAML](../designers/working-with-elements-in-xaml-designer.md)   
 [Vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)