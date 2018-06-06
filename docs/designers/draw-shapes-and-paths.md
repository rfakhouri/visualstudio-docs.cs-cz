---
title: Kreslení tvarů a cest
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: d5378c59-e2e5-49f0-91f1-aa82d984a33c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 95f3514b042b3fbe5ebbac5f79e00d235f9d8e88
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752343"
---
# <a name="draw-shapes-and-paths"></a>Kreslení tvarů a cest
V Návrháři XAML *tvar* právě co byste očekávali. Příklad: obdélníku, kruh nebo třemi tečkami. A *cesta* je flexibilnější verze obrazce. Můžete provést akce, jako je změna tvaru nebo v kombinaci společně pro nové obrazce formuláře.

 Tvarů a cest pomocí vektorové grafiky, škálovat a k zobrazení vysokém rozlišení. Pokud chcete získat další informace o vektorové grafiky, přečtěte si téma [co jsou vektorová grafika](https://www.youtube.com/watch?v=MoCSwF0n-io) nebo [vektorové grafiky](http://www.webopedia.com/TERM/V/vector_graphics.html).

 **V tomto tématu:**

-   [Kreslení obrazce](#Shape)

-   [Kreslení cesty](#Path)

-   [Převést obrazce na cestu](#Convert)

-   [Kombinovat cesty](#Combine)

-   [Vytvoření složené cesty](#Compound)

-   [Vytvoření cesty výstřižek](#Clipping)

##  <a name="Shape"></a> Kreslení obrazce
 Obrazce v najdete **prostředky** panelu.

 ![Kategorii tvarů na panelu datové zdroje](../designers/media/b4_shapes_assetspanel.png)

 Přetáhněte libovolný tvar, který chcete návrhové plochy. Potom můžete obslužné rutiny na tvar škálování, otáčet, přesuňte nebo zkreslit tvaru.

 ![](../designers/media/84261e83-3091-4490-ab58-4218b188439e.png)

##  <a name="Path"></a> Kreslení cesty
 Cestu je řadu připojené čar a křivek. Použijte cestu k vytvoření zajímavé tvarů, které nejsou k dispozici v **prostředky** panelu.

 Cestu můžete nakreslit pomocí řádku, pera nebo tužky. Můžete najít v těchto nástrojů **nástroje** panelu.

 ![](../designers/media/717956a8-b6a5-4e37-8af3-70bcfc78c82a.png)![](../designers/media/8fbbbb21-be83-4cf6-903b-3a49f00c9860.png)

### <a name="draw-a-straight-line"></a>Nakreslení rovné čáry
 Použití **pera** nástroj ![](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png), nebo **řádku** nástroj ![](../designers/media/eb618397-5283-48be-8396-3449be7b6fbf.png).

 **Pomocí nástroje pero** ![](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png)

 Na návrhové plochy klikněte na tlačítko jednou zadat počáteční bod a pak klikněte na tlačítko znovu definovat konec řádku.

 **Pomocí nástroje řádku** ![](../designers/media/eb618397-5283-48be-8396-3449be7b6fbf.png)

 Na návrhové plochy přetáhněte ze kterého má řádek pro spuštění a uvolněte v okamžiku, kdy chcete řádek na konec.

### <a name="draw-a-curve"></a>Nakreslení křivky
 Použití **pera** nástroj ![](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png).

 Na návrhové plochy klikněte na jednou definovat počáteční bod řádku a pak klikněte na tlačítko a přetáhněte ukazatel k vytvoření požadované křivku.

 Pokud chcete zavřít cestu, klikněte na první bod na řádek.

### <a name="change-the-shape-of-a-curve"></a>Změna tvaru křivky
 Použití **přímé výběr** nástroj ![](../designers/media/6dd6571f-c116-451d-8dd2-1f88b8406362.png).

 Klepněte na tvar a poté přetáhněte libovolného bodu na tvar, který má změnit křivky tvarů.

### <a name="draw-a-free-form-path"></a>Nakreslení cesty volného tvaru
 Použití **tužky** nástroj ![](../designers/media/509dc167-734f-46c9-b012-987ee63450cd.png).

 Na návrhové plochy Kreslení volného tvaru cesty, stejně jako s použitím skutečné tužky.

### <a name="remove-part-of-a-path"></a>Odebrat část cesty
 Použití **přímé výběr** nástroj ![](../designers/media/6dd6571f-c116-451d-8dd2-1f88b8406362.png).

 Vyberte cestu, která obsahuje segment, který chcete odstranit a klikněte **odstranit** tlačítko.

### <a name="remove-a-point-in-a-path"></a>Odebrání bodu v cestě
 Použití **výběr** nástroj ![](../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png)a **pera** nástroj ![](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png).

 Použití **výběr** nástroj ![](../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png) vyberte cestu. Potom použít **pera** nástroj ![](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png) kliknout na bod, který chcete odebrat.

### <a name="add-a-point-to-a-path"></a>Přidat bod na cestu
 Použití **výběr** nástroj ![](../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png)a **pera** nástroj ![](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png).

 Použití **výběr** nástroj ![](../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png) vyberte cestu. Použití **pera** nástroj ![](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png) klikněte na libovolné místo v cestě, ve které chcete přidat bod.

##  <a name="Convert"></a> Převést obrazce na cestu
 K úpravě obrazce stejným způsobem, že změníte cestu, převeďte na cestu tvaru.

 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.png) [práce s cesty: převést obrazce na cestu](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=147).

##  <a name="Combine"></a> Kombinovat cesty
 Zkombinováním cesty a obrazců do jednu cestu.

 ![](../designers/media/2df17a5d-a338-4ef4-96c5-dae51cc1ca8a.png)

|||||
|-|-|-|-|
|![](../designers/media/b1_1.png)|Dva obrazce před kombinování|![](../designers/media/b1_4.png)|Intersect|
|![](../designers/media/b1_2.png)|Sjednocení|![](../designers/media/b1_5.png)|Vyloučit překrývají|
|![](../designers/media/b1_3.png)|Dělení|![](../designers/media/b1_6.png)|Odečtena|

 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.png) [práce s cesty: Kombinovat cesty](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=195).

##  <a name="Compound"></a> Vytvoření složené cesty
 Při vytváření složené cesty všechny protínající částí cesty je odečten od výsledek a výsledné cesty získá visual vlastnosti nejspodnějších cesty.

 Musíte můžete rozdělit složené cesty kdykoli po jejím vytvoření.

 ![](../designers/media/2157a8aa-d9a7-4de4-8de5-b10d28f08a84.png)

 **Shlédnout krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.png) [práce s cesty: Vytvoření složeného cesty](https://www.youtube.com/watch?v=Io5bC0-nH6Q).

##  <a name="Clipping"></a> Vytvoření cesty výstřižek
 Výstřižek cesta je cesta nebo tvar, který se použije k jinému objektu, skrytí části maskovaného objektu, které spadal mimo výstřižek cestu.

 ![](../designers/media/22471e98-a841-4f39-a3ef-36090cf5a625.png)

 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.png) [práce cesty: vytvoření výstřižek cesty](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=232).

## <a name="see-also"></a>Viz také:

- [Vytvoření uživatelského rozhraní pomocí nástroje Blend pro Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)