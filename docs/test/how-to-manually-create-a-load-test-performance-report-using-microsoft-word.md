---
title: Vytvoření sestavy výkon testu zatížení Visual Studio pomocí aplikace Microsoft Word | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, reporting
- load tests, creating Word reports
ms.assetid: 3b864c75-2699-48c1-a2b4-9651f108c267
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 6b7c48d46cfb795c4eb5f61cc970676816d568a0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-manually-create-a-load-test-performance-report-using-microsoft-word"></a>Postupy: Ruční vytvoření sestavy výkonnosti pro zátěžový test pomocí aplikace Microsoft Word

Můžete ručně vytvořit sestav Microsoft Word pro zátěžový test pomocí kopírování a vkládání dat ze zobrazení souhrnu načíst výsledky testu a zobrazení grafů. Při kopírování dat, která jsou uvedena v souhrnném zobrazení a zobrazení grafů, jsou tato data použita ve formátu HTML.

> [!TIP]
> Můžete zkopírovat prostý text ze zobrazení tabulek a snímky obrazovky v zobrazení Podrobnosti do aplikace Microsoft Word, ale není použita ve formátu HTML a bude vyžadovat další formátování a úpravy.

> [!TIP]
> Můžete taky Generovat sestavy uspořádány Microsoft Excel automaticky. Další informace najdete v tématu [postupy: vytvoření zatížení Test výkonu sestavy pomocí aplikace Microsoft Excel](../test/how-to-create-load-test-performance-reports-using-microsoft-excel.md).

## <a name="copy-summary-view-data"></a>Kopírování dat souhrnné zobrazení

1.  Ve výsledcích zátěžového testu Pokud se souhrnné zobrazení aktuálně nezobrazí, klikněte na tlačítko **souhrnné** na panelu nástrojů.

2.  Souhrnné zobrazení, klikněte pravým tlačítkem a vyberte **Vybrat vše**.

3.  Souhrnné zobrazení, klikněte pravým tlačítkem a vyberte **kopie**. Tím zkopírujete data souhrnného zobrazení ve formátu HTML do schránky.

4.  V aplikaci Microsoft Word vložte souhrnné zobrazení dat na požadované místo.

5.  Nyní lze upravit, formátovat a mazat aspekty zkopírovaného obsahu podle potřeb vytváření sestav.

## <a name="copy-graph-view-data"></a>Kopírování dat zobrazení grafu

1.  Ve výsledcích zátěžového testu, pokud zobrazení grafů není zobrazen, zvolte **grafy** na panelu nástrojů.

2.  (Volitelné) Přiblížení konkrétní grafu, který chcete zkopírovat do dokumentu Microsoft Wordu, jak je znázorněno na následujícím obrázku. Další informace najdete v tématu [postupy: přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

     ![Graf ovládání pro zvětšení zobrazení](../test/media/ltest_zoomcontrol.png "LTest_ZoomControl")

3.  V grafu, kterou chcete zkopírovat do dokumentu aplikace Microsoft Word, klikněte pravým tlačítkem a vyberte **kopie**.

4.  V aplikaci Microsoft Word vložte graf a přidruženou tabulkou data na požadované místo.

    > [!WARNING]
    > Graf nelze zkopírovat ze vzdálené plochy a vložit jej do jiného počítače, protože budou zkopírovány pouze informace o tabulce, která je přidružena ke grafu, a nikoli obraz grafu. Obraz grafu je uložen v dočasném adresáři v počítači, ze kterého byl zkopírován, a druhý počítač nemůže přes ukazatel přistoupit k tomuto adresáři.

## <a name="see-also"></a>Viz také

- [Vytváření sestav zatížení výsledků testů pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md)
- [Postupy: vytváření sestav výkonnosti pro zátěžový Test pomocí aplikace Microsoft Excel](../test/how-to-create-load-test-performance-reports-using-microsoft-excel.md)