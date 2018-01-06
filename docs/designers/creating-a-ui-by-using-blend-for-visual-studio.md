---
title: "Vytvoření uživatelského rozhraní pomocí nástroje Blend for Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Blend.Start.Dev12
ms.assetid: efd12263-cc2d-4081-a2bb-9a2cc17c442c
caps.latest.revision: "31"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: de2af589a92e401ecf549726dea1a5ae300a20bd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-ui-by-using-blend-for-visual-studio"></a>Vytvoření uživatelského rozhraní pomocí nástroje Blend for Visual Studio
Blend for Visual Studio vám pomůže návrhu založených na XAML Windows a webové aplikace. Poskytuje stejné prostředí základní XAML návrhu jako Visual Studio a přidá vizuální nástroje pro pokročilé úlohy, jako je například animace a chování. (Porovnání mezi nástroje najdete v tématu [navrhování XAML v sadě Visual Studio a nástroj Blend for Visual Studio](../designers/designing-xaml-in-visual-studio.md).)
  
Vzhledem k tomu, že Blend for Visual Studio jako součást sady Visual Studio, nemusíte ho stáhnout. Potřebujete vyberte ho v instalačním programu sady Visual Studio pro něj k instalaci v systému.  
 
Pokud jste ještě Blend for Visual Studio, pozorně se seznámit s jedinečné funkce pracovního prostoru. Toto téma přejdete na stručný přehled.  
  
> [!NOTE]
>  Prohlídka funkce sdílené návrh například návrhové plochy, Osnova dokumentu – okno a okno zařízení, najdete v části [vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).  
  
 **V tomto tématu**:  
  
-   [Prohlídka panelu nástrojů](#Tools)  
  
-   [Prohlídka panelu datové zdroje](#Assets)  
  
-   [Prohlídka objekty a časové osy panely](#Objects)  
  
-   [Prohlídka panelu Vlastnosti](#Properties)  
  
##  <a name="Tools"></a>Prohlídka panelu nástrojů  
 Můžete použít **nástroje** panely v programu Blend for Visual Studio k vytvoření a změně objektů v aplikaci. Při vytváření objektů výběrem nástroj a kreslení na návrhové plochy s myší.  
  
 ![Panel nástrojů](../designers/media/blend5toolspanel.png "Blend5Toolspanel")  
  
|||||  
|-|-|-|-|  
|![](../designers/media/b1_1.png "B1_1")|**Nástroje výběru** vyberte objekty a cesty.<br /><br /> Použití **přímý výběr** nástroj pro výběr vnořených objektů a segmenty cesty.|![Popisek A](../designers/media/b5_label_a.png "b5_label_A")|**Nástroje pro barevný přechod a štětce**|  
|![](../designers/media/b1_2.png "B1_2")|**Zobrazení nástroje** upravit zobrazení návrhové plochy, například pro posouvání a přibližování.|![Popisek B](../designers/media/b5_label_b.png "b5_label_B")|**Cesta nástroje**|  
|![](../designers/media/b1_3.png "B1_3")|**Zdokonalit nástroje** pracovat s visual atributy objektu, například transformace štětce, vykreslování objekt nebo vybrat atributy jeden objekt, který chcete použít je k jinému objektu.|![Popisek C](../designers/media/b5_label_c.png "b5_label_C")|**Nástroje pro kreslení tvarů**|  
|![](../designers/media/b1_4.png "B1_4")|**Objekt nástroje** kreslení nejběžnější objekty v návrhové plochy, jako je například cesty, tvarů, panelů rozložení, text a ovládací prvky.|![Popisek D](../designers/media/b5_label_d.png "b5_label_D")|**Panelů rozložení**|  
|![](../designers/media/b1_5.png "B1_5")|**Nástroje pro Asset** přístup **prostředky** panelu a zobrazíte naposledy použít asset z knihovny.|![Popisek E](../designers/media/b5_label_e.png "b5_label_E")|**Ovládacích prvků textu**|  
|||![F popisku](../designers/media/b5_label_f.png "b5_label_F")|**Běžné ovládací prvky**|  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [panelu nástrojů](https://www.youtube.com/watch?v=VkdUJcvoo54&list=PLBDF977B2F1DAB358&index=4).  
  
##  <a name="Assets"></a>Prohlídka panelu datové zdroje  
 Můžete najít všechny ovládací prvky v **prostředky** panelu, podobně jako **sada nástrojů** v sadě Visual Studio. Kromě ovládacích prvků, najdete zde můžete přidat do vaší návrhové plochy v **prostředky** panelu, včetně styly, média a chování a efekty.  
  
 ![Prostředky panely](../designers/media/blend5_assets_panel.png "Blend5_Assets_panel")  
  
|||  
|-|-|  
|![](../designers/media/b1_1.png "B1_1")|**Vyhledávací pole** zadejte **vyhledávání** pole pro filtrování seznamu prostředků.|  
|![](../designers/media/b1_2.png "B1_2")|**Mřížky režim a režim seznamu** přepínání **režimu mřížky** zobrazení a **režim seznamu** zobrazení prostředků.|  
|![](../designers/media/b1_3.png "B1_3")|**Kategorie prostředky** klikněte na tlačítko kategorie nebo podkategorie zobrazíte seznam prostředků do této kategorie spadají.|  
|![](../designers/media/b1_4.png "B1_4")|**Styly** zobrazit všechny styly, které jsou obsaženy ve slovníku prostředků.|  
|![](../designers/media/b1_5.png "B1_5")|**Popis** zobrazit popis vybrané prostředky kategorie nebo podkategorie.|  
  
##  <a name="Objects"></a>Prohlídka objekty a časové osy panely  
 Použijte tento panel pro uspořádání objektů na vaše návrhové plochy a, pokud chcete, je animace.  
  
 ![Objekt a časový horizont panel v režimu animace](../designers/media/b5_object_timeline_animation.png "b5_object_timeline_animation")  
  
|||  
|-|-|  
|![](../designers/media/b1_1.png "B1_1")|**Objekty zobrazení** zobrazit vizuálním stromu dokumentu. Můžete přejít na různé úrovně podrobností. Můžete také přidat vrstev a další uspořádání objektů na kreslicí plochy. Tímto způsobem můžete uzamknout a jejich skrytí jako skupina.|  
|![](../designers/media/b1_2.png "B1_2")|**Indikátor režimu záznamu** najdete v části zda nahráváte změny vlastností v časové ose.|  
|![](../designers/media/b1_3.png "B1_3")|**Výběr Storyboard** zobrazit seznam scénářů, které jste vytvořili.|  
|![](../designers/media/b1_4.png "B1_4")|**Zavřít storyboard** zavřete aktuální scénáře.|  
|![](../designers/media/b1_5.png "B1_5")|**Vytváření scénářů možnosti** vytvořit, duplicitní, zpětného, odstranění, přejmenování nebo zavřete scénáře.|  
|![](../designers/media/b1_6.png "B1_6")|**Ovládací prvky přehrávání** přejděte prostřednictvím časovou osu. Můžete také přetáhnout počátek přehrávání Procházet (nebo *procházet nástroje*) časovou osu.|  
|![](../designers/media/b1_7.png "B1_7")|**Vrátí obor** oboru objekty zobrazení zpět na předchozí kořenový objekt nebo předchozí oboru. Můžete to provést jenom v případě, že upravujete styl nebo šablony.|  
|![](../designers/media/b1_8.png "B1_8")|**Zaznamenejte klíčový** záznam snímek vlastnosti vybraného objektu k aktuálnímu bodu v čase.|  
|![](../designers/media/b1_9.png "B1_9")|**Možnosti přichycení** nastavit přichycení časové osy, snap řešení a vypněte přichycení časové osy.|  
|![](../designers/media/97fa60b9-0caf-4387-9225-b57510d32209.png "97fa60b9-0caf-4387-9225-b57510d32209")|**Zobrazit nebo skrýt**, **uzamčení** zobrazit nebo skrýt viditelnost a uzamyká možnosti pro objekty zobrazit.|  
|![](../designers/media/b1_11.png "B1_11")|**Pozice počátek přehrávání na časové ose** zobrazit aktuální čas v milisekundách. Rovněž lze pro přechod na konkrétní místo v čase zadat přímo do tohoto pole časovou hodnotu. Přesnost závisí na nastavení v rozlišení snap **možnosti přichycení**.|  
|![](../designers/media/b1_12.png "B1_12")|**Počátek přehrávání** zjistit, co bod v čase, animace v. Ukazatel pozice lze přetahovat po časové ose a zobrazovat tak náhled animace.|  
|![](../designers/media/b1_13.png "B1_13")|**Nastavit časové osy klíčových snímků** změnit hodnotu vlastnosti v určitém bodě v čase.|  
|![](../designers/media/d839d12c-07a1-4127-a830-4a8e7069f4fe.png "d839d12c-07a1-4127-a830-4a8e7069f4fe")|**Změna pořadí objektů** nastavit pořadí zobrazení objektů. Kliknutím na toto tlačítko umožňuje uspořádat objekty v zobrazení struktura pořadí vykreslování (přední zpátky) nebo podle pořadí značek (pořadí, ve kterém se zobrazí v **XAML** zobrazení).|  
|![](../designers/media/b1_15.png "B1_15")|**Časová osa přiblížení** nastavení přiblížení rozlišení časové osy. Přiblížení umožňuje upravovat animaci s více detaily a oddálení zobrazení ukáže větší přehled o tom, co se děje během delšího časového období. Pokud přiblížíte, ale nemůžete nastavit klíčový snímek na pozici v čase, který chcete, ověřte, zda je hodnota rozlišení intervalu klíčových snímků dostatečně vysoká.|  
|![Popisek 16](../designers/media/b5_label_16.png "b5_label_16")|**Časová osa složení oblasti** zobrazení časové osy a pohyb klíčových snímků je přetáhnete nebo pomocí jejich místních nabídek.|  
  
##  <a name="Properties"></a>Prohlídka panelu Vlastnosti  
 Použijte tento panel k zobrazení a úprava vlastností objektu. Můžete je také nastavit přímo na návrhové plochy. Pokud tak učiníte, změny vlastnost se projeví v **vlastnosti** panelu.  
  
 ![Panel vlastnosti](../designers/media/blend5_properties_panel.png "Blend5_properties_panel")  
  
 **Kategorie** rozbalení a sbalení kategorie vlastností. Klikněte na tlačítko **rozbalte** ![ ] (../designers/media/6375953d-074c-421a-bbb3-6f5055b67b64.png "6375953d-074c-421a-bbb3-6f5055b67b64") a **sbalit** ![sbalit] (../designers/media/b5_collapse_button.png "b5_collapse_button") zobrazit nebo skrýt podrobnosti kategorie.  
  
|||  
|-|-|  
|![](../designers/media/b1_1.png "B1_1")|**Název a typ** zobrazovat ikona, název a typ vybraného objektu.|  
|![](../designers/media/b1_2.png "B1_2")|**Uspořádat podle** uspořádání vlastností abecedně podle názvu, zdroje nebo kategorii.|  
|![](../designers/media/b1_3.png "B1_3")|**Zdokonalit vlastnosti** nastavit visual vlastnosti pro štětce například štětce výplně, tahu štětce a štětce popředí.|  
|![](../designers/media/b1_4.png "B1_4")|**Barva editor** plnou barvou a štětce přechodu.|  
|![](../designers/media/b1_5.png "B1_5")|**Výběr barvy** vybrat barvu.|  
|![](../designers/media/b1_6.png "B1_6")|**Barva čipy** zobrazit počáteční barvu, aktuální barva a poslední barev|  
|![](../designers/media/b1_7.png "B1_7")|**Kapátek** použít barvu libovolný element, na obrazovce. **Barva kapátko** je k dispozici, když **plnobarevné štětce** je vybrána. **Přechodu kapátko** je k dispozici, když **štětce přechodu** je vybrána.|  
|![](../designers/media/b1_8.png "B1_8")|**Vlastnosti a události** nastavte vlastnosti, nebo zvolte události pro vybraný prvek.|  
|![](../designers/media/b1_9.png "B1_9")|**Vyhledávací pole** hledání pro vlastnosti. Filtrovat vlastnosti, které se zobrazují zadáním **vyhledávání** pole.||  
|![](../designers/media/97fa60b9-0caf-4387-9225-b57510d32209.png "97fa60b9-0caf-4387-9225-b57510d32209")|**Zdokonalit editor karty** slouží k výběru štětce editor. Můžete zvolit **žádné štětce**, **plnobarevné štětce**, **štětce přechodu**, **dlaždici štětce**, nebo **zdokonalit prostředků**.|  
|![](../designers/media/b1_11.png "B1_11")|**Barva prostředky** použít přesně stejnou barvu na jiné vlastnosti. **Barva prostředky** karta obsahuje **místní prostředky** a **systémové prostředky**.|  
|![](../designers/media/b1_12.png "B1_12")|**RGB barevný prostor** změnit barvu úpravou hodnoty **R**, **G**, nebo **B** číslo editory (červená, zelená, modré).|  
|![](../designers/media/b1_13.png "B1_13")|**Alfa kanálu** pomocí editoru číslo vedle položky změňte hodnotu alfa **A**.|  
|![](../designers/media/d839d12c-07a1-4127-a830-4a8e7069f4fe.png "d839d12c-07a1-4127-a830-4a8e7069f4fe")|**Barva převést prostředek** převést vybrané barvy na barvu prostředků. Barva prostředky jsou k dispozici po kliknutí na kartě prostředky barvu.|  
|![](../designers/media/b1_15.png "B1_15")|**Šestnáctková hodnota** zobrazit šestnáctkové hodnoty barev zobrazí.|  
|![Popisek 16](../designers/media/b5_label_16.png "b5_label_16")|**Přechodu posuvníku** se zobrazí jenom v případě, že je vybraná štětce přechodu.|  
|![](../designers/media/d50027a1-6824-4ad8-8b4e-558b0756dcf8.png "d50027a1-6824-4ad8-8b4e-558b0756dcf8")|**Zobrazit upřesňující vlastnosti** kategorií vlastnosti, které jsou méně často používány zobrazení.|  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [panel vlastnosti](https://www.youtube.com/watch?v=HCqQfiobdag&list=PLBDF977B2F1DAB358&index=7).  
  
## <a name="see-also"></a>Viz také  
 [Vložení ovládacích prvků a změna jejich chování](../designers/insert-controls-and-modify-their-behavior-in-xaml-designer.md)   
 [Animace objektů](../designers/animate-objects-in-xaml-designer.md)   
 [Kreslení tvarů a cest](../designers/draw-shapes-and-paths.md)   
 [Navrhování XAML v sadě Visual Studio a nástroj Blend for Visual Studio](../designers/designing-xaml-in-visual-studio.md)