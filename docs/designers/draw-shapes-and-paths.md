---
title: Kreslení tvarů a cest
titleSuffix: Blend for Visual Studio
ms.date: 07/31/2019
ms.topic: conceptual
ms.assetid: d5378c59-e2e5-49f0-91f1-aa82d984a33c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 948f18ef9abbea1b54346a86b950b90a82ade1ba
ms.sourcegitcommit: 90c3187d804ad7544367829d07ed4b47d3f8a72d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821895"
---
# <a name="draw-shapes-and-paths"></a>Kreslení tvarů a cest

V Návrhář XAML je *tvar* přesně to, co byste očekávali. Například: obdélník, kruh nebo elipsa. *Cesta* je flexibilnější verze tvaru. Můžete provádět akce, jako je jejich změna tvaru nebo jejich kombinování, aby bylo možné vytvořit nové tvary.

Obrazce a cesty používají vektorovou grafiku, takže se na displeje s vysokým rozlišením zvětšují.

## <a name="draw-a-shape"></a>Nakreslit obrazec

V okně Assety vyhledejte obrazce.

![Kategorie Shapes v okně Assety](../designers/media/blend-shapes.png)

Přetáhněte libovolný tvar, který chcete na návrhovou plochu. Pak použijte táhla obrazce pro škálování, otočení, přesunutí nebo zkosení obrazce.

![Handles](../designers/media/84261e83-3091-4490-ab58-4218b188439e.png)

## <a name="draw-a-path"></a>Nakreslit cestu

Cesta je řada propojených čar a křivek. Použijte cestu k vytvoření zajímavých tvarů, které nejsou k dispozici v okně assety.

Můžete nakreslit cestu pomocí čáry, pera nebo tužky. Tyto nástroje můžete najít v okně **nástroje** .

### <a name="draw-a-straight-line"></a>Nakreslení rovné čáry

Použijte nástroj **pero** nebo nástroj **čára** .

**Použití nástroje pero**

Na návrhové ploše klikněte jednou, abyste definovali počáteční bod, a potom klikněte znovu na definovat konec řádku.

**Pomocí nástroje čára**

Na návrhové ploše přetáhněte z místa, kde má být řádek spuštěn, a potom uvolněte místo, kde má řádek končit.

### <a name="draw-a-curve"></a>Nakreslení křivky

Použijte nástroj **pero** .

Na návrhové ploše klikněte jednou a definujte počáteční bod řádku a potom klikněte a přetáhněte ukazatel myši k vytvoření požadované křivky.

Pokud chcete cestu zavřít, klikněte na první bod na řádku.

### <a name="change-the-shape-of-a-curve"></a>Změna tvaru křivky

Použijte nástroj **přímý výběr** .

Klikněte na tvar a potom přetažením libovolného bodu na tvaru změňte obrazce křivky.

### <a name="draw-a-free-form-path"></a>Nakreslení cesty volného tvaru

Použijte nástroj **Tužka** .

Na návrhové ploše nakreslete cestu k volnému formátu stejným způsobem jako při použití skutečné tužky.

### <a name="remove-part-of-a-path"></a>Odebrání části cesty

Použijte nástroj **přímý výběr** .

Vyberte cestu obsahující segment, který chcete odstranit, a potom klikněte na tlačítko **Odstranit** .

### <a name="remove-a-point-in-a-path"></a>Odebrání bodu v cestě

Pomocí nástroje **Výběr** vyberte cestu. Pak pomocí nástroje **pero** klikněte na bod, který chcete odebrat.

### <a name="add-a-point-to-a-path"></a>Přidat bod do cesty

Pomocí nástroje **Výběr** vyberte cestu. Pomocí nástroje **pero** klikněte na libovolné místo na cestě, kam chcete bod přidat.

## <a name="convert-a-shape-to-a-path"></a>Převod tvaru na cestu

Chcete-li upravit tvar stejným způsobem, jakým jste změnili cestu, převeďte tvar na cestu. Vyberte tvar a pak vyberte **Formát** > **převést na cestu** **cesta** > .

**Podívejte se na krátké video:** ![Konfigurace nainstalovaných](../designers/media/bldadminconsoleinitialconfigicon.png) funkcí [pracujících s cestami: Převod tvaru na cestu](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=147).

> [!NOTE]
> **Převést na cestu** není aktuálně k dispozici pro aplikace pro UWP, které `TargetPlatformVersion` mají minimálně 10.0.16299.0 nebo novější.

## <a name="combine-paths"></a>Kombinovat cesty

Cesty a tvary můžete zkombinovat do jedné cesty.

![Kombinovat cesty](../designers/media/2df17a5d-a338-4ef4-96c5-dae51cc1ca8a.png)

|||||
|-|-|-|-|
|![Dva obrazce před kombinováním](../designers/media/b1_1.png)|Dva obrazce před kombinováním|![Krývají](../designers/media/b1_4.png)|Krývají|
|![Toho](../designers/media/b1_2.png)|Toho|![Vyloučit překryv](../designers/media/b1_5.png)|Vyloučit překryv|
|![Rozdělovací](../designers/media/b1_3.png)|Rozdělovací|![Odečten](../designers/media/b1_6.png)|Odečten|

**Podívejte se na krátké video:** ![Konfigurace nainstalovaných](../designers/media/bldadminconsoleinitialconfigicon.png) funkcí [pracujících s cestami: Kombinování](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=195)cest.

## <a name="create-a-compound-path"></a>Vytvořit složenou cestu

Když vytváříte složenou cestu, všechny protínající se části cest odečtou od výsledku a výsledná cesta přebírá vizuální vlastnosti nejspodnější cesty.

Složenou cestu můžete kdykoli po vytvoření rozdělit do všech časových teček.

![Rozdělit složenou cestu](../designers/media/2157a8aa-d9a7-4de4-8de5-b10d28f08a84.png)

**Podívejte se na krátké video:** ![Konfigurace nainstalovaných](../designers/media/bldadminconsoleinitialconfigicon.png) funkcí [pracujících s cestami: Vytvořte složenou cestu](https://www.youtube.com/watch?v=Io5bC0-nH6Q).

## <a name="create-a-clipping-path"></a>Vytvořit ořezovou cestu

Ořezová cesta je cesta nebo tvar, který je použit na jiný objekt, skrývání částí maskovaného objektu, které spadají mimo ořezovou cestu.

![Ořezová cesta](../designers/media/22471e98-a841-4f39-a3ef-36090cf5a625.png)

**Podívejte se na krátké video:** ![Konfigurace nainstalovaných](../designers/media/bldadminconsoleinitialconfigicon.png) funkcí [pracujících s cestami: Vytvořte ořezovou cestu](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=232).